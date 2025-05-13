Aqui está uma lista das bibliotecas essenciais para iniciar o backend do *Timeless* com **Node.js, TypeScript e foco no reagendamento inteligente** como parte do MVP:

---

## 🧱 Bibliotecas essenciais

### 🔧 Ferramentas básicas

| Biblioteca    | Função                                                  |
| ------------- | ------------------------------------------------------- |
| `express`     | Framework para criar rotas e lidar com requisições HTTP |
| `typescript`  | Tipagem estática para o projeto                         |
| `ts-node-dev` | Execução e reload automático em modo dev                |
| `dotenv`      | Leitura de variáveis de ambiente do arquivo `.env`      |
| `cors`        | Permitir comunicação entre frontend e backend           |
| `morgan`      | Logger de requisições HTTP (opcional, mas útil)         |

```bash
npm install express cors dotenv morgan
npm install -D typescript ts-node-dev @types/node @types/express
```

---

### 🛡️ Autenticação

| Biblioteca     | Função                              |
| -------------- | ----------------------------------- |
| `jsonwebtoken` | Geração e verificação de tokens JWT |
| `bcrypt`       | Criptografar senhas                 |

```bash
npm install jsonwebtoken bcrypt
npm install -D @types/jsonwebtoken @types/bcrypt
```

---

### 📚 Validação e utilitários

| Biblioteca     | Função                                         |
| -------------- | ---------------------------------------------- |
| `zod` ou `joi` | Validação de dados                             |
| `date-fns`     | Manipulação de datas (útil para reagendamento) |
| `uuid`         | Geração de IDs únicos                          |

```bash
npm install zod date-fns uuid
```

---

### ☁️ Banco de Dados (duas opções)

#### Opção 1: **Firebase (NoSQL) — mais simples para começar**

```bash
npm install firebase-admin
```

* Usar `Firestore` como banco
* Usar `Firebase Auth` se quiser integração com app mobile
* Também útil para notificações (via Firebase Cloud Messaging)

#### Opção 2: **PostgreSQL com Prisma (SQL) — mais estruturado**

```bash
npm install prisma @prisma/client
npx prisma init
```

* Requer PostgreSQL rodando localmente ou na nuvem (ex: Supabase, Neon, Render)
* Boa estrutura para relacionamentos (ex: tarefas, tags, usuários)

---

## 🧪 Exemplo de `package.json` (simplificado)

```json
{
  "scripts": {
    "dev": "ts-node-dev --respawn --transpile-only src/index.ts",
    "build": "tsc",
    "start": "node dist/index.js"
  }
}
```

---

Se quiser, posso te ajudar a gerar o `tsconfig.json`, a estrutura de pastas base e os arquivos iniciais (`index.ts`, rotas, etc.). Deseja isso agora?
