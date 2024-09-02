# Modelo Arquitetural BookSwap

![logo](https://github.com/user-attachments/assets/f4c41849-31d1-43dc-b9be-26cc731e0b18)

- Índice
  - [Descrição do produto](#descrição-do-produto)
  - [Time](#time)
  - [Django](#django)
    - [Entendendo cada camada](#entendendo-cada-camada)
    - [Boas Práticas](#boas-práticas)
  - [React Native com Expo](#react-native-com-expo)
    - [Boas Práticas](#boas-práticas-1)
  - [PostgreSQL](#postgresql)
    - [Boas Práticas](#boas-práticas-2)
  - [Outras Tecnologias](#outras-tecnologias)
    - [Git](#git)
    - [Git Flow](#git-flow)
    - [GitHub](#github)

## Descrição do produto

BookSwap é uma plataforma online que conecta amantes de livros, facilitando a troca de títulos e a construção de uma comunidade literária. Crie um perfil, adicione seus livros à biblioteca virtual e explore o catálogo de outros usuários para encontrar o próximo livro para ler.

## Time

### Antonio André Barcelos Chagas - [@andrebarceloschagas](https://github.com/andrebarceloschagas)
### Caio Santos Silva - [@CaioSantdev](https://github.com/CaioSantdev)
### Eduardo Henrique Coelho Ramos - [@KiwiProgamador](https://github.com/KiwiProgamador)
### Laura Barbosa Henrique - [@tinywin](https://github.com/tinywin)
### Lucas José de Sousa Gomes - [@Yamatosz](https://github.com/Yamatosz)
### Luiz Carlos Porto do Carmo - [@LuizCPorto](https://github.com/LuizCPorto)

---

### [Projeto de Sistemas 2024/2](https://github.com/disciplinas-prof-Edeilson-UFT/proj-sist-2024-2) - Professor Edeilson

---

## Tecnologias que facilitarão o desenvolvimento do BookSwap

## Django

O Django, um poderoso framework Python para desenvolvimento web, adota o padrão **MTV (Model, Template, View)**. Essa arquitetura é uma variação do conhecido MVC (Model, View, Controller) e se encaixa perfeitamente para o desenvolvimento de aplicações web robustas e escaláveis.

### Entendendo cada camada:

* **Model:** Representa a estrutura dos dados da aplicação. É aqui que se define os modelos de dados (tabelas do banco de dados) utilizando a ORM (Object-Relational Mapper) do Django. Essa camada se comunica diretamente com o banco de dados, abstraindo a complexidade das operações SQL.
* **Template:** Responsável pela interface do usuário. Os templates são arquivos HTML que podem conter lógica de apresentação, mas não lógica de negócio. O Django utiliza um sistema de templates poderoso e flexível, permitindo a criação de interfaces dinâmicas e personalizáveis.
* **View:** Atua como intermediária entre os modelos e os templates. As views recebem as requisições HTTP, processam os dados (utilizando os modelos) e escolhem o template adequado para renderizar a resposta.

### Boas Práticas:

Seguir boas práticas no desenvolvimento com Django é essencial para garantir a manutenção, escalabilidade e segurança do seu projeto. Aqui estão algumas recomendações:

* **Estrutura de Projetos:** Organize o projeto de forma modular, utilizando a estrutura de aplicativos (apps) do Django. Isso facilita a manutenção e a reutilização de código.

      myproject/
        manage.py
        myproject/
            __init__.py
            settings.py
            urls.py
            wsgi.py
        app_one/
            migrations/
            __init__.py
            admin.py
            apps.py
            models.py
            tests.py
            views.py
        app_two/
            migrations/
            __init__.py
            admin.py
            apps.py
            models.py
            tests.py
            views.py

* **Configurações Seguras:** Nunca exponha informações sensíveis, como chaves secretas e credenciais de banco de dados, no código-fonte. Utilize variáveis de ambiente para gerenciar essas configurações.

      # settings.py
      import os
      
      SECRET_KEY = os.getenv('DJANGO_SECRET_KEY', 'default-secret-key')
      DATABASES = {
          'default': {
              'ENGINE': 'django.db.backends.postgresql',
              'NAME': os.getenv('DB_NAME'),
              'USER': os.getenv('DB_USER'),
              'PASSWORD': os.getenv('DB_PASSWORD'),
              'HOST': os.getenv('DB_HOST'),
              'PORT': os.getenv('DB_PORT'),
          }
      }

* **Utilização de Class-Based Views (CBVs):** Prefira o uso de Class-Based Views (CBVs) ao invés de Function-Based Views (FBVs) para aproveitar a reutilização de código e a organização.

      # views.py
      from django.views.generic import ListView, DetailView
      from .models import MyModel

      class MyModelListView(ListView):
          model = MyModel
          template_name = 'app_one/mymodel_list.html'

      class MyModelDetailView(DetailView):
          model = MyModel
          template_name = 'app_one/mymodel_detail.html'

* **Serialização e Validação:** Utilize os Serializers do Django REST framework para serializar e validar dados de forma eficiente.

      # serializers.py
      from rest_framework import serializers
      from .models import MyModel

      class MyModelSerializer(serializers.ModelSerializer):
          class Meta:
              model = MyModel
              fields = '__all__'

* **Testes Automatizados:** Escreva testes automatizados para garantir que seu código funcione conforme esperado e para facilitar a detecção de regressões.

      # tests.py
      from django.test import TestCase
      from .models import MyModel
      
      class MyModelTestCase(TestCase):
          def setUp(self):
              MyModel.objects.create(name="Test Model")
      
          def test_model_creation(self):
              model = MyModel.objects.get(name="Test Model")
              self.assertEqual(model.name, "Test Model")

* **Documentação:** Documente seu código e APIs utilizando ferramentas como Django REST framework's browsable API e docstrings.

      # views.py
      from rest_framework.views import APIView
      from rest_framework.response import Response
      
      class MyAPIView(APIView):
          """
          API endpoint that allows users to be viewed or edited.
          """
          def get(self, request, format=None):
              return Response({"message": "Hello, world!"})

## React Native com Expo

O React Native, em conjunto com o Expo, oferece uma base sólida para o desenvolvimento de aplicações mobile multiplataforma. Embora não haja um padrão arquitetural rígido imposto, algumas práticas e estruturas são comumente adotadas para organizar o código e facilitar a manutenção de projetos de maior porte.

* **Componentes:** A base do React Native são os componentes funcionais e de classe. A organização desses componentes em uma estrutura hierárquica é fundamental para a construção da interface do usuário.

* **Redux ou Context API:** Para gerenciar o estado da aplicação, Redux ou Context API são as ferramentas mais utilizadas. Redux oferece um fluxo de estado unidirecional, enquanto o Context API é uma solução mais simples para estados globais.

* **Navegação:** Bibliotecas como React Navigation ou Navigation Container permitem criar fluxos de navegação entre as diferentes telas da aplicação.

* **Styled Components:** Essa biblioteca permite escrever CSS dentro dos componentes JavaScript, facilitando o estilo visual da aplicação.

* **Testes:** É fundamental escrever testes unitários e de integração para garantir a qualidade do código.

### Boas Práticas:

* **Estrutura de Pastas:** Organize seu projeto de forma clara e lógica. Uma estrutura comum é:

      /src
        /components
        /screens
        /navigation
        /assets
        /services
      App.js

* **Componentes Funcionais e Hooks:** Prefira componentes funcionais e hooks ao invés de componentes de classe.

      // JavaScript
      import React, { useState } from 'react';
      import { View, Text, Button } from 'react-native';

      const MyComponent = () => {
        const [count, setCount] = useState(0);

        return (
          <View>
            <Text>Você clicou {count} vezes</Text>
            <Button title="Clique aqui" onPress={() => setCount(count + 1)} />
          </View>
        );
      };

      export default MyComponent;

* **Estilos Consistentes:** Use StyleSheet para definir estilos e mantenha-os consistentes.

      // JavaScript
      import { StyleSheet } from 'react-native';

      const styles = StyleSheet.create({
        container: {
          flex: 1,
          justifyContent: 'center',
          alignItems: 'center',
        },
        text: {
          fontSize: 18,
          color: 'blue',
        },
      });

      export default styles;

* **Navegação:** Utilize a biblioteca react-navigation para gerenciar a navegação.

      // JavaScript
      import { NavigationContainer } from '@react-navigation/native';
      import { createStackNavigator } from '@react-navigation/stack';
      import HomeScreen from './screens/HomeScreen';
      import DetailsScreen from './screens/DetailsScreen';

      const Stack = createStackNavigator();

      const App = () => {
        return (
          <NavigationContainer>
            <Stack.Navigator initialRouteName="Home">
              <Stack.Screen name="Home" component={HomeScreen} />
              <Stack.Screen name="Details" component={DetailsScreen} />
            </Stack.Navigator>
          </NavigationContainer>
        );
      };

      export default App;

* **Gerenciamento de Estado:** Para projetos maiores, considere usar Redux ou Context API para gerenciamento de estado.

      // JavaScript
      import React, { createContext, useReducer } from 'react';

      const initialState = { count: 0 };
      const reducer = (state, action) => {
        switch (action.type) {
          case 'increment':
            return { count: state.count + 1 };
          case 'decrement':
            return { count: state.count - 1 };
          default:
            return state;
        }
      };

      export const CountContext = createContext();

      const App = () => {
        const [state, dispatch] = useReducer(reducer, initialState);

        return (
          <CountContext.Provider value={{ state, dispatch }}>
            <MyComponent />
          </CountContext.Provider>
        );
      };

      export default App;

* **Uso de Expo CLI:** Utilize o Expo CLI para facilitar o desenvolvimento e a construção do aplicativo.

      # Para iniciar um novo projeto
      expo init my-new-project

      # Para rodar o projeto
      expo start

* **Testes:** Escreva testes para seus componentes usando Jest e React Native Testing Library.
  
      // JavaScript
      import React from 'react';
      import { render, fireEvent } from '@testing-library/react-native';
      import MyComponent from '../MyComponent';

      test('incrementa contador ao clicar no botão', () => {
        const { getByText } = render(<MyComponent />);
        const button = getByText('Clique aqui');
        fireEvent.press(button);
        expect(getByText('Você clicou 1 vezes')).toBeTruthy();
      });

## PostgreSQL

O PostgreSQL, como um poderoso sistema gerenciador de bancos de dados relacionais, oferece uma gama de recursos que permitem a implementação de diversos padrões de projeto. Ao aplicar esses padrões, pode-se otimizar o desempenho, aumentar a segurança e a manutenibilidade do seu banco de dados.

* **Organização:** Estrutura o banco de dados de forma lógica e consistente.

* **Reusabilidade:** Permite criar componentes reutilizáveis.

* **Manutenibilidade:** Facilita a compreensão e a modificação do banco de dados.

* **Escalabilidade:** Aumenta a capacidade do banco de dados de lidar com cargas crescentes.

### Boas Práticas:

* **Estrutura de Tabelas:** Organize suas tabelas de forma lógica e consistente. Use nomes descritivos e siga uma convenção de nomenclatura.

      CREATE TABLE users (
          user_id SERIAL PRIMARY KEY,
          username VARCHAR(50) NOT NULL UNIQUE,
          email VARCHAR(100) NOT NULL UNIQUE,
          created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
      );

* **Índices:** Crie índices para melhorar o desempenho das consultas. No entanto, evite criar índices desnecessários, pois eles podem degradar a performance de inserções e atualizações.

      CREATE INDEX idx_users_username ON users(username);

* **Normalização:** Normalize suas tabelas para reduzir redundâncias e melhorar a integridade dos dados. Utilize chaves estrangeiras para manter relacionamentos entre tabelas.

      CREATE TABLE orders (
          order_id SERIAL PRIMARY KEY,
          user_id INT REFERENCES users(user_id),
          order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
      );

* **Backup e Recuperação:** Implemente uma estratégia de backup regular para garantir que seus dados possam ser recuperados em caso de falha.

      # Backup
      pg_dump -U username -F c -b -v -f mydatabase.backup mydatabase

      # Restauração
      pg_restore -U username -d mydatabase -v mydatabase.backup

* **Segurança:** Restrinja o acesso ao banco de dados e utilize roles e permissões para controlar o que cada usuário pode fazer.

      CREATE ROLE readonly;
      GRANT CONNECT ON DATABASE mydatabase TO readonly;
      GRANT USAGE ON SCHEMA public TO readonly;
      GRANT SELECT ON ALL TABLES IN SCHEMA public TO readonly;

* **Monitoramento:** Monitore o desempenho do seu banco de dados utilizando ferramentas como pg_stat_statements para identificar consultas lentas e gargalos.

      -- Instalar a extensão
      CREATE EXTENSION pg_stat_statements;

      -- Consultar estatísticas
      SELECT * FROM pg_stat_statements ORDER BY total_time DESC LIMIT 5;

* **Transações:** Utilize transações para garantir a integridade dos dados em operações que envolvem múltiplas etapas.

      BEGIN;

      INSERT INTO users (username, email) VALUES ('johndoe', 'john@example.com');
      INSERT INTO orders (user_id, order_date) VALUES (currval('users_user_id_seq'), NOW());

      COMMIT;

## Outras Tecnologias

### Git:

O Git é uma ferramenta essencial para desenvolvedores, especialmente para aqueles que trabalham em equipe. Ele permite rastrear as alterações feitas em um projeto ao longo do tempo, facilitando a colaboração e a gestão de versões. Com o Git, pode-se voltar para versões anteriores do código, comparar diferentes versões e trabalhar em conjunto com outros desenvolvedores de forma eficiente. É como um histórico completo das modificações do seu projeto, garantindo que nada se perca e permitindo que você volte atrás se precisar.


### Git Flow:

O Git Flow é uma metodologia que estabelece um conjunto de regras para organizar o desenvolvimento de software utilizando o sistema de controle de versão Git. Ele define ramificações específicas (como master, develop, feature, release e hotfix) e um fluxo de trabalho padronizado para gerenciar o ciclo de vida de um projeto. Através do Git Flow, as equipes podem trabalhar de forma mais organizada, separando o desenvolvimento de novas funcionalidades, correções de bugs e releases, reduzindo o risco de erros e facilitando a colaboração entre os membros da equipe. Essa metodologia, embora não seja obrigatória, proporciona uma estrutura sólida para projetos que exigem um alto nível de controle sobre as versões do software.

### GitHub:

O GitHub é uma plataforma de hospedagem de repositórios Git que facilita a colaboração entre desenvolvedores. Ele permite que armazene, gerencie e compartilhe seu código-fonte, além de acompanhar o histórico de alterações. Com o GitHub, pode-se criar ramificações para experimentar novas ideias sem afetar o código principal, realizar revisões de código e colaborar com outros desenvolvedores em projetos de código aberto ou privados.
