# Clone Digital Eugene Schwartz - N8N

Sistema N8N completo que implementa o clone digital de Eugene Schwartz através de um workflow unificado.

## 🌐 **SISTEMA EM PRODUÇÃO**

**Acesse em:** [copyoracle.com](https://copyoracle.com)
**Apresentação:** [Ver demonstração](https://share.descript.com/view/Z7AAywXqDPz)

- ✅ **Análise VSL completa** - Insights acionáveis
- ✅ **Chatbot Eugene Schwartz** - Interação em tempo real
- ✅ **Histórico de análises** - Armazenamento local
- ✅ **Interface web responsiva** - Next.js + Tailwind

## Workflow

| Arquivo                                       | Endpoints                                                         | Função                                |
| --------------------------------------------- | ----------------------------------------------------------------- | ------------------------------------- |
| `[Vita_Science]Combined_Workflow_Eugene.json` | `/webhook/vsl-analysis-with-rewrite`<br>`/webhook/chatbot-eugene` | Análise VSL e chatbot Eugene Schwartz |

## Pré-requisitos

### Infraestrutura

- **OpenRouter API** - Grok-4-fast para análises
- **OpenAI API** - GPT-4 e embeddings
- **Supabase** - Vector store com livro "Breakthrough Advertising"

## Instalação

1. **Import Workflow**

   ```
   N8N > Settings > Import > [Vita_Science]Combined_Workflow_Eugene.json
   ```

2. **Configure Credentials**

   - OpenRouter account
   - OpenAI account
   - Supabase account

3. **Ative o Workflow**

## Uso

### Análise VSL

```bash
curl -X POST "$N8N_URL/webhook/vsl-analysis-with-rewrite" \
  -H "Content-Type: application/json" \
  -d '{"vsl_content":"Seu texto VSL aqui..."}'
```

### Chatbot Eugene

```bash
curl -X POST "$N8N_URL/webhook/chatbot-eugene" \
  -H "Content-Type: application/json" \
  -d '{"message":"Como aplico os 5 níveis de consciência?"}'
```

## Componentes

- **Eugene Schwartz Analyzer** - Análise VSL (Grok-4-fast)
- **Eugene AI Agent** - Chatbot (OpenAI GPT-4)
- **Supabase Vector Store** - Knowledge base Eugene
- **Structured Output Parser** - JSON válido
- **Simple Memory** - Contexto conversacional

## Outputs

### Análise VSL

```json
{
  "analise_eugene_schwartz": {
    "nivel_de_consciencia": {"nivel": "3", "justificativa_eugene": "..."},
    "pontos_de_melhoria": [...],
    "novos_angulos_criativos": [...]
  }
}
```

### Chatbot

```json
{
  "response": "Resposta do Eugene...",
  "status": "success",
  "metadata": { "vector_search_used": true }
}
```

## Documentação

- **`CONCEPCAO_PROJETO.md`** — Processo de desenvolvimento
- **`DIAGRAMA_ARQUITETURA.md`** — Diagramas do workflow
- **`PROMPTS_DOCUMENTATION.md`** — Prompts dos agentes
- **`ESTRUTURA_BANCO_DADOS.md`** — Schema Supabase

---

**Sistema N8N autossuficiente** para análise VSL e chatbot Eugene Schwartz
