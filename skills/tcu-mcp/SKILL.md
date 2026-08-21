---
name: tcu-mcp
description: Skill da REST API do TCU Jurisprudência na MCP.AI: 2 endpoints em /api/tcu. Pesquisa pública da jurisprudência do Tribunal de Contas da União (TCU): busca por palavra-chave nos entendimentos exarados em acórdãos, na jurisprudência selecionada (enunciados) e nas súmulas, com sumário, trechos destacados, relator e links pro inteiro teor. Também lista os acórdãos mais recentes. Hospedado pela plataforma, sem credenciais. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# TCU Jurisprudência — REST API skill

Você tem acesso à **TCU Jurisprudência** REST API na MCP.AI.

> Pesquisa pública da jurisprudência do Tribunal de Contas da União (TCU): busca por palavra-chave nos entendimentos exarados em acórdãos, na jurisprudência selecionada (enunciados) e nas súmulas, com sumário, trechos destacados, relator e links pro inteiro teor. Também lista os acórdãos mais recentes. Hospedado pela plataforma, sem credenciais.

## Base URL

```
https://api.mcp.ai/api/tcu
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/tcu/acordaos/recentes \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/tcu/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (2)

#### `tcu_acordaos_recentes`

Lista os acórdãos mais recentes do TCU (dados abertos oficiais), paginado, sem palavra-chave: sumário, relator, colegiado, data da sessão e links. _(POST /api/tcu/acordaos/recentes)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `inicio` | integer | Não | Offset de paginação (default 0). |
| `quantidade` | integer | Não | Quantidade (default 10, máx 50). |

#### `tcu_buscar`

Busca textual (por palavra-chave) na jurisprudência do TCU. _(POST /api/tcu/buscar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `termo` | string | Sim | Palavra-chave/tema (ex.: 'fraude em licitação', 'dispensa indevida'). |
| `base` | string | Não | Base a pesquisar. Default 'acordaos'. (acordaos, jurisprudencia, sumulas) |
| `inicio` | integer | Não | Offset de paginação (default 0). |
| `tamanho` | integer | Não | Quantidade por página (default 10, máx 50). |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_tcu` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
