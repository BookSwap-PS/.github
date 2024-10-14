# Sprint 2 - Planejamento e User Stories

## Objetivos Principais:
- Concluir funcionalidades importantes para Filtrar Livros, Biblioteca, e Edição de Livros no BackEnd.
- Implementar e finalizar tarefas de Autenticação, Botão de Detalhe do Livro, e Refatoração de Telas no FrontEnd.
- Garantir que as funcionalidades estejam bem integradas e com testes adequados.

### Tarefas do BackEnd

#### 1. Finalizar Filtrar Livros (Serializer)
**User Story**: 
  - Como um usuário, eu gostaria de poder filtrar os livros na tela de busca, para encontrar o que preciso rapidamente.

**Critérios de Aceitação**:
  - O sistema deve permitir a filtragem por múltiplos critérios.
  - A resposta deve estar paginada e ser eficiente.

#### 2. Finalizar Biblioteca
**User Story**:
  - Como um usuário, eu gostaria de ter uma visão clara de todos os livros na minha biblioteca para gerenciar o acervo.

**Critérios de Aceitação**:
  - A biblioteca deve listar todos os livros com detalhes como título, autor, data de publicação, e uma breve descrição.
  - A biblioteca deve ser capaz de lidar com grandes quantidades de dados eficientemente.

#### 3. Editar Livro
**User Story**:
  - Como um administrador, eu gostaria de poder editar os detalhes de um livro existente, para manter as informações atualizadas.

**Critérios de Aceitação**:
  - O sistema deve permitir a edição de detalhes do livro, como título, autor, ano, e categoria.
  - A edição deve ser validada e atualizada no banco de dados.

---

### Tarefas do FrontEnd

#### 1. Finalizar Filtrar Livros
**User Story**:
  - Como um usuário, eu gostaria de ter uma interface intuitiva para filtrar livros na biblioteca online.

**Critérios de Aceitação**:
  - A UI deve ter campos de filtro para autor, ano, e gênero.
  - A filtragem deve ser eficiente e os resultados devem aparecer em tempo real (com debounce para otimização de chamadas API).

#### 2. Botão DetailLivro
**User Story**:
  - Como um usuário, eu gostaria de clicar em um livro na lista para ver mais detalhes sobre ele, incluindo uma descrição completa e links para ações (como editar ou excluir, se for admin).

**Critérios de Aceitação**:
  - O botão deve abrir uma visualização de detalhes em modal ou nova página.
  - Deve incluir o título, autor, sinopse, e botões de ação (como editar, excluir, ou voltar).

#### 3. Autenticação
**User Story**:
  - Como um usuário, eu gostaria de poder me autenticar no sistema, para acessar áreas restritas e gerenciar meu conteúdo.

**Critérios de Aceitação**:
  - O sistema deve permitir login e logout.
  - As credenciais devem ser validadas com segurança (JWT ou outra forma de token).
  - Feedback adequado deve ser dado ao usuário em caso de erro.

#### 4. Refresh de Sessão
**User Story**:
  - Como um usuário autenticado, eu gostaria de ter minha sessão automaticamente atualizada para não precisar fazer login várias vezes.

**Critérios de Aceitação**:
  - O token de autenticação deve ser renovado automaticamente enquanto o usuário interage com o sistema.
  - Aviso ao usuário caso a sessão expire após um longo período de inatividade.

#### 5. Refatoração de Telas da 1ª Sprint
**User Story**:
  - Como desenvolvedor, eu gostaria de refatorar o código da interface para garantir sua escalabilidade e manutenibilidade.

**Critérios de Aceitação**:
  - A interface deve seguir boas práticas de design (componentização, reutilização de código).
  - O layout e a responsividade devem ser revisados para consistência e otimização.

---

### Objetivos de Entrega para a Segunda Sprint
1. **BackEnd**:
   - Funções de filtragem finalizadas e otimizadas.
   - Edição e visualização de livros implementada.
   - Testes adequados para garantir a funcionalidade do sistema.

2. **FrontEnd**:
   - Implementação da autenticação e manutenção de sessão (refresh).
   - Detalhamento e visualização de livros com filtros funcionais.
   - Refatoração de componentes da interface para manter escalabilidade e facilitar futuras alterações.

# Sprint 3 - Relação dos Usuários com Perfis

O objetivo desta sprint é desenvolver funcionalidades que permitam aos usuários interagir com perfis de outros usuários na plataforma.

## Funcionalidades

### 1. Acessar perfis de outros usuários

**Descrição:**  
Como usuário, eu gostaria de acessar o perfil de outros usuários para ver detalhes como:

- Biblioteca de livros
- Seguidores
- Pessoas que estão seguindo

**Critérios de aceitação:**
- Usuário pode acessar o perfil de outro usuário ao clicar em seu nome ou avatar.
- O perfil deve exibir a biblioteca de livros do usuário, seguidores e a lista de pessoas que ele segue.

### 2. Seguir e ser seguido

**Descrição:**  
Como usuário, eu gostaria de seguir outras pessoas e também poder ser seguido, para acompanhar o que estão lendo.

**Critérios de aceitação:**
- Usuário pode seguir e deixar de seguir outros usuários.
- Usuário pode ser seguido por outros.
- O número de seguidores e pessoas seguidas deve ser exibido no perfil.

### 3. Pesquisar Usuário

**Descrição:**  
Como usuário, eu gostaria de pesquisar por um usuário específico, utilizando o username, facilitando a busca de perfis.

**Critérios de aceitação:**
- O usuário pode realizar uma pesquisa por username.
- A busca deve exibir uma lista de resultados relevantes com base no username pesquisado.

### 4. Tela de Perfis Seguindo

**Descrição:**  
Como usuário, eu gostaria de ter uma tela específica para ver as atualizações apenas das pessoas que sigo.

**Critérios de aceitação:**
- Exibir uma página dedicada com as atualizações (como livros adicionados à biblioteca ou posts) das pessoas que o usuário segue.
- Interface clara e filtrada apenas para as atividades dos perfis seguidos.

### 5. Adicionar resenhas de livros

**Descrição:**  
Como usuário, eu gostaria de poder adicionar resenhas a livros que li, para compartilhar minha opinião e experiência com outros usuários.

**Critérios de aceitação:**
- O usuário pode adicionar uma resenha a qualquer livro presente em sua biblioteca.
- As resenhas devem ser visíveis para outros usuários que acessarem o livro.
- O usuário pode editar ou excluir sua resenha.

### 6. Curtir livros de outras pessoas

**Descrição:**  
Como usuário, eu gostaria de curtir os livros que outras pessoas estão lendo, para demonstrar interesse e engajamento.

**Critérios de aceitação:**
- O usuário pode curtir livros da biblioteca de outras pessoas.
- O número de curtidas de cada livro deve ser exibido.
- O usuário pode remover sua curtida a qualquer momento.

### 7. Comentar livros de outras pessoas

**Descrição:**  
Como usuário, eu gostaria de comentar os livros de outras pessoas, para discutir sobre a leitura e compartilhar minhas ideias.

**Critérios de aceitação:**
- O usuário pode adicionar comentários nos livros da biblioteca de outros usuários.
- O usuário pode responder a comentários.
- O sistema deve permitir a exclusão ou edição dos comentários pelos próprios autores.

## Tarefas Técnicas

- Implementar página de perfil do usuário.
- Desenvolver funcionalidade de seguir e deixar de seguir.
- Implementar pesquisa de usuários por username.
- Criar tela de atualizações das pessoas seguidas.
- Implementar funcionalidade de adicionar resenhas aos livros.
- Implementar funcionalidade de curtir livros de outros usuários.
- Implementar funcionalidade de comentar em livros de outros usuários.

##

# Sprint 4: Sistema de Chat, Troca de Livros e Recuperação de Senha

**Valor**: Permitir que os usuários conversem via chat, visualizem livros disponíveis para troca, proponham trocas, recuperem suas senhas e desfrute de todas funcionalidades da aplicação.

---

## User Stories e Regras de Negócio

### **RF1: Sistema de Chat**

**User Stories:**
Como um usuário, eu quero poder enviar e receber mensagens via chat com outros usuários, para facilitar a comunicação sobre trocas e interações.

**Regra de Negócio**  
Somente usuários autenticados podem utilizar o chat.

**Tarefas**:  
- **Backend**: Implementar a funcionalidade de enviar e receber mensagens no sistema.  
- **Frontend**: 
  - Criar a interface do chat.  
  - Implementar a lógica de envio e recebimento de mensagens.  

**Critérios de Aceitação**:
- O sistema deve permitir a troca de mensagens em tempo real.
- Somente usuários autenticados podem iniciar conversas.

**Prototipação da Tela de Chat**  
![Tela chat](https://github.com/user-attachments/assets/8a467d61-cc06-49bf-974f-407ec0f3fd65)


---

### **RF2: Livros Disponíveis para Troca**

**User Stories:**
Como um usuário, eu quero visualizar uma lista de livros disponíveis para troca, para encontrar possíveis opções de troca de livros.

**Regra de Negócio**  
Apenas livros marcados como "Disponíveis para Troca" devem aparecer na lista.

**Tarefas**:  
- **Backend**: Implementar a funcionalidade para listar livros disponíveis para troca.  
- **Frontend**: 
  - Criar uma interface para exibir os livros disponíveis.  
  - Implementar lógica de filtro para exibir apenas livros disponíveis para troca.  

**Critérios de Aceitação**:
- Somente livros marcados como disponíveis para troca devem aparecer.
- A lista deve ser atualizada conforme a disponibilidade dos livros.

**Prototipação da Tela de Livros Disponíveis para Troca**  
![Tela disponíveis para troca](https://github.com/user-attachments/assets/8e7ad1a3-7941-462f-8819-8b788cccb75f)

---

### **RF3: Recuperação de Senha**

**User Stories:**
Como um usuário, eu quero poder recuperar minha senha, para que eu possa restaurar o acesso à minha conta caso eu esqueça minha senha.

**Regra de Negócio**  
O sistema deve enviar um e-mail para redefinição de senha somente para usuários autenticados.

**Tarefas**:  
- **Backend**: Implementar a funcionalidade de recuperação de senha e envio de e-mails.  
- **Frontend**: 
  - Criar interface para solicitar recuperação de senha.  
  - Implementar lógica de envio de solicitação de recuperação.  

**Critérios de Aceitação**:
- O sistema deve permitir a solicitação de redefinição de senha via e-mail.
- A recuperação de senha deve ser concluída com sucesso após o envio do link.

**Prototipação da Tela de Recuperação de Senha**  
![email](https://github.com/user-attachments/assets/cabcd6b6-a3e7-48a7-9d67-683682307940)


---

### **FX 4: Funcionalidades Pendentes de Sprints Anteriores**

**User Stories:**
 Como um usuário, eu quero que todas as funcionalidades prometidas estejam finalizadas, para garantir uma experiência completa e funcional.

**Regra de Negócio**  
As funcionalidades pendentes devem ser priorizadas e finalizadas.

**Tarefas**:  
- **Backend** e **Frontend**: Revisar e finalizar as funcionalidades pendentes.  

**Critérios de Aceitação**:
- Todas as funcionalidades das sprints anteriores devem estar operacionais e testadas.


