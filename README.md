# Kit de Automação N8N com Chatwoot e Evolution API

Um kit de automação pronto para uso centrado no N8N, que integra a plataforma de atendimento Chatwoot, a Evolution API para WhatsApp e o Redis.

O objetivo é fornecer um ambiente completo e robusto para criar soluções de automação e atendimento ao cliente, com o N8N orquestrando toda a comunicação. A stack também inclui suporte opcional para Inteligência Artificial local com Ollama.

## 🚀 Componentes do Kit

| Serviço | Papel no Kit |
| :--- | :--- |
| **N8N** | **[CORE]** Ferramenta de automação de workflows para conectar e orquestrar todos os outros serviços. |
| **Chatwoot** | Plataforma de atendimento ao cliente omni-channel para gerenciar conversas. |
| **Evolution API** | API não oficial que conecta o WhatsApp, permitindo automação de mensagens. |
| **Redis** | Utilizado pelo Chatwoot para gerenciar cache e tarefas em segundo plano, garantindo performance. |
| **PostgreSQL** | Banco de dados relacional para persistência de dados do Chatwoot e N8N. |
| **MongoDB** | Banco de dados NoSQL exigido pela Evolution API. |
| **Ollama** | **[OPCIONAL]** Permite executar modelos de linguagem (LLMs) localmente para IA generativa. |
| **Qdrant** | **[OPCIONAL]** Banco de dados vetorial para aplicações de IA, como assistentes com memória. |

## ✨ O que você pode construir?

* **Chatbots para WhatsApp**: Use o N8N para ouvir eventos da Evolution API e responder mensagens automaticamente.
* **Automação de Atendimento**: Crie tickets no Chatwoot, encaminhe conversas e envie respostas padronizadas, tudo via N8N.
* **Workflows Inteligentes**: Integre a IA do Ollama em seus fluxos do N8N para analisar o sentimento de mensagens ou gerar respostas contextuais.
* **Sincronização de Dados**: Mantenha seus dados de clientes sincronizados entre o Chatwoot e outras ferramentas via N8N.

---

## ⚙️ Guia Rápido de Instalação

