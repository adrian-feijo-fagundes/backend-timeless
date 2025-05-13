Este artigo apresenta o "Timeless", um aplicativo inovador para gestão do tempo e priorização de tarefas utilizando inteligência artificial. O sistema fornece sugestões personalizadas para melhorar a produtividade, evitar a procrastinação e promover um equilíbrio entre trabalho e lazer. A arquitetura do sistema, suas principais funcionalidades e os benefícios para os usuários são discutidos.

# Funcionalidades Principais

### Questionamentos importantes
- Qual é o MVP (Minímo produto viável) do Projeto?
- Quais informações podem tornar o aplicativo mais preciso?
- Como pequenas informações podem tornar o aplicativo mais preciso?
- Como fazer o aplicativo ser simples?
- Como tornar a gamificação algo agradável?
- Funcionalidades extras de acordo com o tempo de uso?
- O app vai ficar rodando o tempo todo para conseguir mandar as notificações para os usuários
- Como tornar o acesso ao calendário e as notificações algo agradável?
- Usar widgets?

#### To-do List
- Tarefas vão ter recorrência?
- Podem ser divididas em partes?
- Seria legal ter algo como "Concluir Depois"?
- Utilizar KANBAN? talvez ser algo opcional?
- Como as tarefas serão armazenadas no banco de dados? Vão existir várias tabelas?

#### Calendário/Agenda das Tarefas
- Como vamos identificar os horários livres do usuário?
- Vale a pena identificar os horários ocupados?
- O usuário vai apenas informar o tempo livre dele?
- Como evitar a "sobrecarga de tarefas" do usuário?
- Como enviar notificações para o usuário?
- Como fazer importação de calendários externos (Google, Outlook)?
- Existem api/libs que facilitam a implementação de calendários e agendas?

## To-Do List Inteligente com Tags

- Cada tarefa pode conter **multiplas tags**
- Tags **personalizadas**
    - CRUD de Tags
    - Nomes únicos
- Organização Buscar tarefas por tags
- Organização por prioridade
    - Urgente (3)
    - Quero realizar logo (2)
    - Por enquanto ta tudo tranquilo (1)

- Duração prevista para atividade
    - Depois de concluir a tarefa poderiamos implementar algo como:
        - "Isso foi bem rápido"
        - "Conclui mas teve um imprevisto"
        - O aplicativo usar a hora do aplicativo para reconhecer se foi concluída antes do horário previsto
        
Esboço propriedades:
- Titulo
- Texto
- Duração
- Priopridade
- Tags
- Data marcada
- Horário marcado
- Dia de conclusão
- Horário de conclusão
- Horário de inicio?
- Horário de inicio esperado?
- Horário de conclusão esperado?
- Tempo de Tolerância?

"Métodos":
- CRUD tarefas
- CRUD tags
- buscarPorTags(tag1, tag2...)
- remarcar()
- ajustarPrioridade?

## 📅 Calendário Integrado à Rotina e Compromissos

- Lembretes 
- A IA organiza sua rotina ao redor desses eventos, sugerindo preparação e evitando sobrecarga.
- As tarefas são *agendadas automaticamente* de acordo com o tempo-livre do usuário (O Usuário continua com a *possibilidade de configurar*)
- Reconhecimento de indisponibilidade: o app entende quando você está ocupado ou indisposto e se ajusta
- As tarefas devem ser marcadas considerando uma **margem de "erro"**
- Relatório de produtividade

"Métodos":
obterHorariosLivres()
ajustarNaRotina()
exibirLembrete()

## 🧠 IA Adaptativa e Sugestiva
(Não precisa ser especificamente uma IA para todas as funções, mas sim algoritmos de estatistica por exemplo para detectar padrões de horarios tags e outras informações)
- Aprende com seu comportamento e ajusta as sugestões com base no que você realmente faz.
- Sugere atividades com base em hobbies cadastrados (filmes, esportes, descanso, leitura, etc).
- Redefine prioridades se você adiar ou pular tarefas com frequência.
- Após o adiamento de uma tarefa, a IA propõe um novo horário ou dia mais apropriado, com base na sua rotina.
Exemplo: “⏱️ Notamos que esse horário não funcionou. Que tal tentar amanhã às 10h?”

## ⌛ Reconhecimento de Tempo Livre
A IA identifica blocos de tempo vazios e propõe ações úteis ou prazerosas.
Ex: “Você tem 45 minutos — que tal um episódio da sua série favorita ou revisar uma tarefa curta?”

## 📈 Relatórios de Produtividade e Bem-Estar
- Visualização clara de tarefas concluídas por dia, semana e mês.
- Média de tempo gasto por tipo de tarefa (usando tags).
- Gráficos comparativos com seus próprios dados anteriores, para autoconhecimento.

## 🏆 Sistema de Recompensas e Motivação
- Ganha badges/insígnias ao atingir metas (ex: 50 tarefas seguidas sem falhar).
Desbloqueio de novos temas visuais, sons, mascotes e conteúdos exclusivos.
- Mascote humanizado (relógio de bolso estilizado, estilo Duolingo) te acompanha com mensagens motivadoras e divertidas:
“⏱️ Você concluiu 3 tarefas hoje. Bora fechar com chave de ouro?”

## 🔔 Notificações
- Lembretes com tom positivo para motivar, lembrar e encorajar.
- Mensagens envolventes como:
 “✨ Hora de cuidar de você: 15 minutos de lazer sugeridos!”
- Opção de adiar diretamente pela notificação:
- Quando você adia uma tarefa, a IA aprende com isso e reagenda de forma inteligente.
Exemplo: “Reagendamos sua leitura para amanhã às 18h — costuma ser um bom horário para você relaxar.”

## ⚙️ Configurações Personalizadas
- Temas visuais (modo claro/escuro, minimalista, inspirador).
- Sons/músicas relaxantes ou motivacionais durante períodos de foco.
- Personalização completa: tags, metas, recompensas, mascotes e tipo de notificações.

## 🔐 Perfil Seguro e Sincronizado
- Login com senha e proteção de dados.
- Dados sincronizados na nuvem, acessíveis de qualquer dispositivo.