# Arquitetura N8N - Eugene Schwartz

## Workflow Combinado

```mermaid
graph TB
    Client[Cliente/Aplicação]

    subgraph "N8N Combined Workflow"
        WebhookVSL[Webhook VSL<br>/webhook/vsl-analysis-with-rewrite]
        WebhookChat[Webhook Chat<br>/webhook/chatbot-eugene]

        EugeneAnalyzer[Eugene Schwartz Analyzer<br>Grok-4-fast]
        EugeneChat[Eugene Schwartz AI Agent<br>OpenAI GPT-4]

        VectorStore[Supabase Vector Store<br>Knowledge Base]
        Memory[Simple Memory<br>10 mensagens]
    end

    Client --> WebhookVSL
    Client --> WebhookChat

    WebhookVSL --> EugeneAnalyzer
    WebhookChat --> EugeneChat

    EugeneChat --> VectorStore
    EugeneChat --> Memory
```

## Fluxos de Dados

### VSL Analysis
1. **Input** → Webhook → Normalize → Eugene Analyzer → Structured Parser → **Output JSON**

### Chatbot
2. **Input** → Webhook → Prepare → Eugene Agent → Vector Search + Memory → **Response JSON**

## Componentes Principais

| Componente | Função |
|------------|--------|
| **Webhooks** | `/webhook/vsl-analysis-with-rewrite` e `/webhook/chatbot-eugene` |
| **Eugene Schwartz Analyzer** | Análise VSL com Grok-4-fast |
| **Eugene AI Agent (Chat)** | Chatbot com OpenAI GPT-4 |
| **Supabase Vector Store** | Knowledge base Eugene Schwartz |
| **Simple Memory** | Contexto conversacional (10 mensagens) |
| **Structured Output Parser** | Garantia de JSON válido |

## Deploy

```mermaid
graph LR
    App[Aplicação] --> Internet((HTTPS)) --> N8N[N8N Instance]
    N8N --> Supabase[Supabase Vector DB]
    N8N --> OpenAI[OpenAI API]
    N8N --> OpenRouter[OpenRouter API]
```

---

**Workflow completo:** `[Vita_Science]Combined_Workflow_Eugene.json`