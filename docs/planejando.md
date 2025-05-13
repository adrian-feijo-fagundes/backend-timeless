Ótimo! Se o **reagendamento automático inteligente** for parte do **MVP** do *Timeless*, o guia precisa ser reestruturado com essa funcionalidade no centro. Abaixo está uma **nova versão do guia para criação do backend**, considerando isso desde o início.

---

## 🚀 Guia para Criar o Backend do *Timeless* com Reagendamento Inteligente no MVP

---

### ✅ 1. **Defina o MVP (foco mínimo para lançar)**

Inclua desde o início:

1. **Cadastro e login de usuários**
2. **CRUD de tarefas com campos inteligentes**
3. **CRUD de tags**
4. **Detecção de horários livres**
5. **Reagendamento automático quando uma tarefa for adiada**
6. **Notificações básicas (pode ser local no começo)**
7. **Armazenamento na nuvem**

---

### ✅ 2. **Tecnologias recomendadas**

| Componente             | Stack sugerido                                     |
| ---------------------- | -------------------------------------------------- |
| Linguagem              | TypeScript                                         |
| Backend                | Node.js + Express                                  |
| Banco de dados         | Firebase Firestore (ou PostgreSQL se preferir SQL) |
| Autenticação           | Firebase Auth ou JWT + Bcrypt                      |
| Notificações           | Firebase Cloud Messaging (FCM)                     |
| Agendamento de tarefas | node-cron, agenda.js ou Firebase Cloud Functions   |
| Hospedagem             | Render, Railway ou Firebase Functions              |

---

### ✅ 3. **Modelagem do Banco de Dados (para Firestore)**

```bash
/users/{userId}
/tasks/{taskId}
/tags/{tagId}
```

### 📦 Exemplo de documento `task`

```json
{
  "userId": "abc123",
  "title": "Estudar React",
  "description": "Focar nos hooks",
  "tags": ["estudo", "programação"],
  "expectedStart": "2025-05-13T14:00:00Z",
  "expectedEnd": "2025-05-13T15:30:00Z",
  "status": "pendente", // concluida, adiada
  "rescheduleCount": 1,
  "lastReschedule": "2025-05-12T17:00:00Z",
  "wasPostponed": true,
  "actualStart": null,
  "actualEnd": null
}
```

---

### ✅ 4. **Endpoints da API para o MVP**

#### 📌 Autenticação

* `POST /auth/register`
* `POST /auth/login`

#### 📌 Tarefas

* `GET /tasks` — Lista todas as tarefas do usuário
* `POST /tasks` — Cria nova tarefa
* `PUT /tasks/:id` — Edita uma tarefa
* `POST /tasks/:id/postpone` — Adia e **ativa o reagendamento inteligente**
* `DELETE /tasks/:id` — Remove tarefa

#### 📌 Tags

* `GET /tags`
* `POST /tags`
* `DELETE /tags/:id`

#### 📌 Sugestões/Reagendamento

* `POST /tasks/:id/suggest-reschedule` — Sugere novo horário
* `GET /user/free-time` — Retorna blocos de tempo livre estimados

---

### ✅ 5. **Lógica básica do Reagendamento Inteligente**

```ts
// utils/reschedule.ts
function sugerirNovoHorario(tarefa, blocosLivres) {
  const duracao = tarefa.expectedEnd - tarefa.expectedStart;

  const candidatos = blocosLivres.filter(
    bloco => bloco.duracao >= duracao
  );

  const ordenados = ordenarPorPreferenciaDoUsuario(candidatos, tarefa.userId);

  return ordenados[0]?.inicio || null;
}
```

---

### ✅ 6. **Exemplo: Endpoint para reagendamento**

```ts
// routes/tasks.ts
router.post('/tasks/:id/postpone', async (req, res) => {
  const taskId = req.params.id;
  const userId = req.user.id;

  const tarefa = await getTask(taskId, userId);
  if (!tarefa) return res.status(404).send({ error: "Tarefa não encontrada" });

  const blocosLivres = await obterHorariosLivres(userId);
  const novoHorario = sugerirNovoHorario(tarefa, blocosLivres);

  if (!novoHorario) {
    return res.status(400).send({ message: "Sem horários disponíveis" });
  }

  tarefa.expectedStart = novoHorario;
  tarefa.expectedEnd = addMinutes(novoHorario, calcularDuracao(tarefa));
  tarefa.rescheduleCount += 1;
  tarefa.lastReschedule = new Date().toISOString();
  tarefa.wasPostponed = true;

  await updateTask(tarefa);
  res.send({ message: "Tarefa reagendada com sucesso", tarefa });
});
```

---

### ✅ 7. **Organização da Estrutura do Projeto**

```
timeless-backend/
├── src/
│   ├── controllers/
│   ├── routes/
│   ├── services/
│   ├── models/
│   ├── utils/
│   └── index.ts
├── .env
├── tsconfig.json
├── package.json
```

---

### ✅ 8. **Próximos recursos após MVP**

* Reconhecimento de padrões e estatísticas simples
* IA para sugestões personalizadas
* Sistema de recompensas
* Exportação de calendário (Google, Outlook)
* Visualizações e relatórios

---

Quer que eu gere a estrutura de pastas e arquivos inicial para esse projeto com código base?
