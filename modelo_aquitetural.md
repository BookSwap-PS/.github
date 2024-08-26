# Modelo Arquitetural BookSwap

![logo](https://github.com/user-attachments/assets/f4c41849-31d1-43dc-b9be-26cc731e0b18)

- Índice
  - [Descrição do produto](#descrição-do-produto)
  - [Time](#time)
  - [Django](#django)
  - [Django REST framework](#django-rest-framework)
  - [React Native com Expo](#react-native-com-expo)
  - [PostgreSQL](#postgresql)
  - [Outras Tecnologias](#outras-tecnologias)

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

Exemplos de códigos disponíveis no repositório [BookSwap-BackEnd
](https://github.com/BookSwap-PS/BookSwap-BackEnd).

## Django REST framework

O Django REST framework (DRF) é uma poderosa ferramenta que se integra ao Django para construir APIs RESTful de forma rápida e eficiente. Ele leva o padrão MTV do Django um passo adiante, oferecendo um conjunto de ferramentas e recursos específicos para o desenvolvimento de interfaces de programação de aplicações.

### Entendendo cada camada:

O DRF se baseia no padrão MTV do Django, mas introduz algumas camadas adicionais para lidar especificamente com as APIs:

* **Serializadores:** Mapeiam os modelos do Django para representações JSON ou outros formatos, definindo quais campos serão incluídos e como eles serão serializados.
* **Views:** As views do DRF são especializadas para lidar com requisições HTTP e retornar respostas formatadas em JSON.
* **Routers:** Organizam as URLs da API e mapeiam as requisições HTTP para as views correspondentes.

Exemplos de códigos disponíveis no repositório [BookSwap-BackEnd
](https://github.com/BookSwap-PS/BookSwap-BackEnd).

## React Native com Expo

O React Native, em conjunto com o Expo, oferece uma base sólida para o desenvolvimento de aplicações mobile multiplataforma. Embora não haja um padrão arquitetural rígido imposto, algumas práticas e estruturas são comumente adotadas para organizar o código e facilitar a manutenção de projetos de maior porte.

* **Componentes:** A base do React Native são os componentes funcionais e de classe. A organização desses componentes em uma estrutura hierárquica é fundamental para a construção da interface do usuário.
* **Redux ou Context API:** Para gerenciar o estado da aplicação, Redux ou Context API são as ferramentas mais utilizadas. Redux oferece um fluxo de estado unidirecional, enquanto o Context API é uma solução mais simples para estados globais.
* **Navegação:** Bibliotecas como React Navigation ou Navigation Container permitem criar fluxos de navegação entre as diferentes telas da aplicação.
* **Styled Components:** Essa biblioteca permite escrever CSS dentro dos componentes JavaScript, facilitando o estilo visual da aplicação.
* **Testes:** É fundamental escrever testes unitários e de integração para garantir a qualidade do código.

### Arquitetura Comum

Uma arquitetura comum para aplicações React Native com Expo pode seguir a seguinte estrutura:

* **Componentes:**
    * **Componentes atômicos:** Elementos básicos da interface, como botões, inputs, etc.
    * **Componentes moleculares:** Combinações de componentes atômicos para formar elementos mais complexos, como cards, headers, etc.
    * **Componentes de página:** Representam as telas da aplicação, combinando componentes moleculares e atômicos.
* **Containers:** Contêm a lógica de negócio e gerenciam o estado dos componentes.
* **Redux ou Context API:** Centraliza o estado da aplicação.
* **Navegação:** Define os fluxos de navegação entre as telas.
* **Serviços:** Encapsulam a lógica de comunicação com APIs externas ou o armazenamento local.
* **Utils:** Contém funções auxiliares e utilitárias.

### Padrões de Projeto

* **Composição de Componentes:** Construir componentes complexos a partir de componentes mais simples.
* **Single Responsibility Principle (SRP):** Cada componente deve ter uma única responsabilidade.
* **Don't Repeat Yourself (DRY):** Evitar a duplicação de código.
* **KISS (Keep It Simple, Stupid):** Manter o código simples e fácil de entender.

Exemplos de códigos disponíveis no repositório [BookSwap-FrontEnd](https://github.com/BookSwap-PS/BookSwap-FrontEnd).

## PostgreSQL

O PostgreSQL, como um poderoso sistema gerenciador de bancos de dados relacionais, oferece uma gama de recursos que permitem a implementação de diversos padrões de projeto. Ao aplicar esses padrões, pode-se otimizar o desempenho, aumentar a segurança e a manutenibilidade do seu banco de dados.

### Padrões de projeto no PostgreSQL

* **Organização:** Estrutura o banco de dados de forma lógica e consistente.
* **Reusabilidade:** Permite criar componentes reutilizáveis.
* **Manutenibilidade:** Facilita a compreensão e a modificação do banco de dados.
* **Escalabilidade:** Aumenta a capacidade do banco de dados de lidar com cargas crescentes.

Exemplos de códigos disponíveis no repositório [BookSwap-BackEnd
](https://github.com/BookSwap-PS/BookSwap-BackEnd).

## Outras Tecnologias

### Git

O Git é uma ferramenta essencial para desenvolvedores, especialmente para aqueles que trabalham em equipe. Ele permite rastrear as alterações feitas em um projeto ao longo do tempo, facilitando a colaboração e a gestão de versões. Com o Git, pode-se voltar para versões anteriores do código, comparar diferentes versões e trabalhar em conjunto com outros desenvolvedores de forma eficiente. É como um histórico completo das modificações do seu projeto, garantindo que nada se perca e permitindo que você volte atrás se precisar.

### GitHub

O GitHub é uma plataforma de hospedagem de repositórios Git que facilita a colaboração entre desenvolvedores. Ele permite que armazene, gerencie e compartilhe seu código-fonte, além de acompanhar o histórico de alterações. Com o GitHub, pode-se criar ramificações para experimentar novas ideias sem afetar o código principal, realizar revisões de código e colaborar com outros desenvolvedores em projetos de código aberto ou privados.

### Git Flow

O Git Flow é uma metodologia que estabelece um conjunto de regras para organizar o desenvolvimento de software utilizando o sistema de controle de versão Git. Ele define ramificações específicas (como master, develop, feature, release e hotfix) e um fluxo de trabalho padronizado para gerenciar o ciclo de vida de um projeto. Através do Git Flow, as equipes podem trabalhar de forma mais organizada, separando o desenvolvimento de novas funcionalidades, correções de bugs e releases, reduzindo o risco de erros e facilitando a colaboração entre os membros da equipe. Essa metodologia, embora não seja obrigatória, proporciona uma estrutura sólida para projetos que exigem um alto nível de controle sobre as versões do software.