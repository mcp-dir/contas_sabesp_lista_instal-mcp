---
name: contas_sabesp_lista_instal-mcp
description: Skill da REST API do SABESP: Lista de Instalações na MCP.AI: 1 endpoint em /api/contas_sabesp_lista_instal. SABESP: Lista de Instalações, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SABESP: Lista de Instalações — REST API skill

Você tem acesso à **SABESP: Lista de Instalações** REST API na MCP.AI.

> SABESP: Lista de Instalações, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/contas_sabesp_lista_instal
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
curl -X POST https://api.mcp.ai/api/contas_sabesp_lista_instal/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"login_cpf":"...","login_senha":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/contas_sabesp_lista_instal/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `contas_sabesp_lista_instal_consultar`

SABESP: Lista de Instalações, consulta em fonte oficial. _(POST /api/contas_sabesp_lista_instal/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `login_cpf` | string | Sim | Parâmetro de consulta "login_cpf". |
| `login_senha` | string | Sim | Parâmetro de consulta "login_senha". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_contas_sabesp_lista_instal` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
