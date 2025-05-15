# backend-timeless

## Tecnologias

* **Linguagem**: TypeScript
* **Frameworks**: Express, TypeORM
* **Banco de dados**: MySQL

---

## Etapas de Desenvolvimento

### 🧱 1. Planejamento Inicial

* Definir a **arquitetura do projeto** (MVC ou alguma variação com camadas como Service, Repository).
* Entender como funciona uma **API RESTful**.
* Definir o **modelo de dados** (quais tabelas vão existir):

  * Usuário (registro e login)
  * Preferências do usuário
  * Tarefas
  * Tags personalizadas

### 🛠️ 2. Configuração do Ambiente

* Criar o projeto com `Express + TypeScript`.
* Configurar `TypeORM` e o banco `MySQL`.
* Criar arquivos de configuração e conexões (ex: `.env`, `ormconfig`).

### 🧩 3. Implementação de Funcionalidades Básicas

#### Usuários

* Registro
* Login com autenticação (JWT ou session)
* CRUD de perfil

#### Tarefas

* CRUD (Criar, Ler, Atualizar, Deletar)
* Relacionar com usuário

#### Tags

* CRUD de tags
* Relacionar com tarefas

#### Preferências

* Permitir personalização por usuário
* Ex: notificação, temas, horários produtivos

### 🌐 4. Rotas da API

* Organizar rotas por recurso (`/users`, `/tasks`, `/tags`)
* Usar os métodos corretos (GET, POST, PUT, DELETE)
* Retornar status HTTP adequados

### 🧪 5. Testes e Validações

* Validar entrada de dados (ex: com `zod` ou `joi`)
* Testar endpoints (ex: com `Insomnia` ou `Postman`)
* Escrever testes automatizados (opcional no início)

### 🤖 6. Fase de Inteligência (Extra / MVP 2)

* Pesquisar bibliotecas de IA e análise de dados
* Implementar:

  * Agendamento inteligente
  * Sugestões baseadas em hábitos
  * Geração de relatórios de produtividade

---

Se quiser, posso gerar um quadro Kanban com essas tarefas para você colar no Trello ou Notion. Deseja isso?
