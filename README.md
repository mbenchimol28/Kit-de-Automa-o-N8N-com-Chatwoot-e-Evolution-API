# Kit de Automação N8N com Chatwoot e Evolution API

Um kit de automação pronto para uso centrado no N8N, que integra a plataforma de
atendimento Chatwoot, a Evolution API para WhatsApp e o Redis.

O objetivo é fornecer um ambiente completo e robusto para criar soluções de automação e
atendimento ao cliente, com o N8N orquestrando toda a comunicação. A stack também
inclui suporte opcional para Inteligência Artificial local com Ollama.

## 🚀 Componentes do Kit

| Serviço | Papel no Kit |
| :--- | :--- |
| **N8N** | **[CORE]** Ferramenta de automação de workflows para conectar e orquestrar
todos os outros serviços. |
| **Chatwoot** | Plataforma de atendimento ao cliente omni-channel para gerenciar
conversas. |
| **Evolution API** | API não oficial que conecta o WhatsApp, permitindo automação de
mensagens. |
| **Redis** | Utilizado pelo Chatwoot para gerenciar cache e tarefas em segundo plano,
garantindo performance. |
| **PostgreSQL** | Banco de dados relacional para persistência de dados do Chatwoot e
N8N. |
| **MongoDB** | Banco de dados NoSQL exigido pela Evolution API. |
| **Ollama** | **[OPCIONAL]** Permite executar modelos de linguagem (LLMs) localmente
para IA generativa. |
| **Qdrant** | **[OPCIONAL]** Banco de dados vetorial para aplicações de IA, como
assistentes com memória. |

## ✨ O que você pode construir?

* **Chatbots para WhatsApp**: Use o N8N para ouvir eventos da Evolution API e responder
mensagens automaticamente.
* **Automação de Atendimento**: Crie tickets no Chatwoot, encaminhe conversas e envie
respostas padronizadas, tudo via N8N.
* **Workflows Inteligentes**: Integre a IA do Ollama em seus fluxos do N8N para analisar o
sentimento de mensagens ou gerar respostas contextuais.
* **Sincronização de Dados**: Mantenha seus dados de clientes sincronizados entre o
Chatwoot e outras ferramentas via N8N.

---

## ⚙ Guia Rápido de Instalação

Siga estes 3 passos para iniciar o ambiente.

### Passo 1: Clone o Repositório
```sh


git clone
[https://github.com/seu-usuario/seu-repositorio.git](https://github.com/seu-usuario/seu-reposi
torio.git)
cd seu-repositorio

## Passo 2: Crie e Preencha o Arquivo .env

Copie o conteúdo abaixo para um novo arquivo chamado .env na raiz do projeto.

Snippet de código
# -----------------------------------------------------------------
# ARQUIVO DE CONFIGURAÇÃO - Preencha as variáveis abaixo
# -----------------------------------------------------------------
# Para gerar chaves seguras, você pode usar o seguinte comando no terminal:
# openssl rand -hex 32
# -----------------------------------------------------------------

# PostgreSQL (usado pelo Chatwoot e N8N)
POSTGRES_HOST=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=CHANGEME
POSTGRES_DB=chatwoot

# Chatwoot
CHATWOOT_POSTGRES_DATABASE=chatwoot
SECRET_KEY_BASE=CHANGEME
FRONTEND_URL=http://localhost:
MAILER_SENDER_EMAIL=Chatwoot <noreply@chatwoot.local>

# Redis
REDIS_PASSWORD=CHANGEME

# Evolution API + MongoDB
MONGO_ROOT_USER=mongo_user
MONGO_ROOT_PASSWORD=CHANGEME
EVOLUTION_API_KEY=CHANGEME

# N8N
N8N_ENCRYPTION_KEY=CHANGEME
N8N_USER_MANAGEMENT_JWT_SECRET=CHANGEME
N8N_DATABASE_DB=${POSTGRES_DB} # Usa o mesmo banco de dados do Postgres

# Ollama (endereço interno do container)
OLLAMA_HOST=ollama:


**Importante** : Altere todos os valores CHANGEME por chaves seguras e únicas antes de
prosseguir.

## Passo 3: Inicie os Serviços com Docker Compose

O docker-compose.yml usa perfis para ativar serviços opcionais.

**Para iniciar o kit essencial (N8N, Chatwoot, Evolution):**

Bash
docker-compose --profile n8n up -d

**Para iniciar o kit completo com IA (usando CPU):**

Bash
docker-compose --profile n8n --profile ai --profile cpu up -d

_O download do modelo de IA (llama3.2) pode levar algum tempo na primeira inicialização._

# 🌐 Acessando os Serviços

Após os contêineres estarem em execução, as interfaces estarão disponíveis nos seguintes
endereços:

```
Serviço URL Porta
Exposta
```
**N8N** (^) [http://localhost:](http://localhost:)
5678

### 5678:

**Chatwoot** (^) [http://localhost:](http://localhost:)
3000

### 3000:

**Evolution API** (^) [http://localhost:](http://localhost:)
8080

### 8080:

**Ollama API** (^) [http://localhost:](http://localhost:)
11434

### 11434:

### 4

**Qdrant API** (^) [http://localhost:](http://localhost:)
6333

### 6333:

**PostgreSQL** (^) localhost 5432:
**Redis** (^) localhost 6379:


Exportar para as Planilhas

# 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue para relatar bugs ou
sugerir novas funcionalidades, ou um pull request com melhorias.

# 📄 Licença

Este projeto é distribuído sob a licença MIT.

