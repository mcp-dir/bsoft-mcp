---
name: bsoft-mcp
description: Skill da REST API do Bsoft TMS na MCP.AI: 45 endpoints em /api/bsoft. API oficial do Bsoft TMS, sistema líder de gestão de transportadoras do Brasil (Bsoft by nstech). Emissão e consulta de CT-e, MDF-e e NF-e, chaves de acesso, XML e PDF dos documentos fiscais, financeiro (títulos a pagar/receber, pagamentos, recebimentos, contratos, conciliação), frota e manutenção, fretes e conhecimentos, controle de viagens e cadastros de pessoas. Conecte com as credenciais do seu domínio Bsoft (domínio, usuário com perfil de integração e senha). Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Bsoft TMS — REST API skill

Você tem acesso à **Bsoft TMS** REST API na MCP.AI.

> API oficial do Bsoft TMS, sistema líder de gestão de transportadoras do Brasil (Bsoft by nstech). Emissão e consulta de CT-e, MDF-e e NF-e, chaves de acesso, XML e PDF dos documentos fiscais, financeiro (títulos a pagar/receber, pagamentos, recebimentos, contratos, conciliação), frota e manutenção, fretes e conhecimentos, controle de viagens e cadastros de pessoas. Conecte com as credenciais do seu domínio Bsoft (domínio, usuário com perfil de integração e senha).

## Base URL

```
https://api.mcp.ai/api/bsoft
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
curl -X POST https://api.mcp.ai/api/bsoft/controle/viagens \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"resource":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/bsoft/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (45)

#### `bsoft_controle_viagens`

Controle de Viagens no Bsoft TMS (leitura). _(POST /api/bsoft/controle/viagens)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a consultar. (adiantamentos, despesas, despesas/configuracoes/tipos_item, despesas/modelos, devolucoes, documentos, recebimentos, receitas, viagens, viagens/classificacoes, viagens/documentos, viagens/manifestos) |
| `id` | string | Não | Obter um registro específico por id. |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `offset` | integer | Não | Paginação: registro inicial (offset, base 0). Vira ?limit=offset,limit. |
| `limit` | integer | Não | Paginação: quantidade de registros (default 20, máx 100). |
| `query` | string | Não | Filtros como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Ex.: {"data_inicial":"2025-01-01"}. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_controle_viagens_write_create`

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/controle/viagens/write/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (adiantamentos, despesas, despesas/configuracoes/tipos_item, despesas/modelos, devolucoes, documentos, recebimentos, receitas, viagens, viagens/classificacoes, viagens/documentos, viagens/manifestos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_controle_viagens_write_create_lote`

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/controle/viagens/write/create/lote)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (adiantamentos, despesas, despesas/configuracoes/tipos_item, despesas/modelos, devolucoes, documentos, recebimentos, receitas, viagens, viagens/classificacoes, viagens/documentos, viagens/manifestos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_controle_viagens_write_delete`

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/controle/viagens/write/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (adiantamentos, despesas, despesas/configuracoes/tipos_item, despesas/modelos, devolucoes, documentos, recebimentos, receitas, viagens, viagens/classificacoes, viagens/documentos, viagens/manifestos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_controle_viagens_write_patch`

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/controle/viagens/write/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (adiantamentos, despesas, despesas/configuracoes/tipos_item, despesas/modelos, devolucoes, documentos, recebimentos, receitas, viagens, viagens/classificacoes, viagens/documentos, viagens/manifestos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_controle_viagens_write_update`

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/controle/viagens/write/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (adiantamentos, despesas, despesas/configuracoes/tipos_item, despesas/modelos, devolucoes, documentos, recebimentos, receitas, viagens, viagens/classificacoes, viagens/documentos, viagens/manifestos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_documentos_fiscais`

Documentos fiscais eletrônicos do Bsoft (e-Doc) — o caso de uso principal. _(POST /api/bsoft/documentos/fiscais)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `kind` | string | Sim | Formato: pdf, chaves ou xml. (pdf, chaves, xml) |
| `tipo` | string | Sim | Tipo de documento fiscal. (CTesEmitidos, CTesRecebidos, MDFe, NFesEmitidas, NFesRecebidas) |
| `query` | string | Não | Filtros GET como JSON (ex.: {"data_inicial":"2025-01-01","data_final":"2025-01-31"}). |
| `body` | string | Não | Filtro para kind=xml como JSON string (ex.: chaves ou período). |

#### `bsoft_documentos_fiscais_evento`

Registrar EVENTO de documento fiscal no Bsoft (CT-e ou MDF-e): cancelamento, carta de correção, encerramento etc. _(POST /api/bsoft/documentos/fiscais/evento)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `tipo` | string | Sim | Documento do evento. (CTe, MDFe) |
| `body` | string | Sim | Dados do evento como JSON string (campos na doc do Bsoft). |

#### `bsoft_financeiro`

Financeiro no Bsoft TMS (leitura). _(POST /api/bsoft/financeiro)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a consultar. (centrosDeCusto, condicoesPagamento, configuracoes/diasVencimento, contasFinanceiras, contratos, contratos/itensContratos, empresas, familiaProdutosServicos, formasPagamento, modelosNotas, pagamentos, planoDeContasFiscal, planoDeContasGerencial, rateios, recebimentos, servicos, tiposDocumentos, tiposPagamentos, tiposSuspensoesCobrancas, tiposTransacoes, titulosPagar, titulosReceber, transferencia) |
| `id` | string | Não | Obter um registro específico por id. |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `offset` | integer | Não | Paginação: registro inicial (offset, base 0). Vira ?limit=offset,limit. |
| `limit` | integer | Não | Paginação: quantidade de registros (default 20, máx 100). |
| `query` | string | Não | Filtros como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Ex.: {"data_inicial":"2025-01-01"}. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_financeiro_write_create`

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/financeiro/write/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (centrosDeCusto, conciliacao, contasFinanceiras, contratos, contratos/finalizar, contratos/itensContratos, contratos/itensContratos/cancelar, contratos/itensContratos/finalizar, contratos/itensContratos/suspender, formasPagamento, pagamentos, planoDeContasGerencial, recebimentos, tiposPagamentos, tiposTransacoes, titulosPagar, titulosReceber, transferencia) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_financeiro_write_create_lote`

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/financeiro/write/create/lote)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (centrosDeCusto, conciliacao, contasFinanceiras, contratos, contratos/finalizar, contratos/itensContratos, contratos/itensContratos/cancelar, contratos/itensContratos/finalizar, contratos/itensContratos/suspender, formasPagamento, pagamentos, planoDeContasGerencial, recebimentos, tiposPagamentos, tiposTransacoes, titulosPagar, titulosReceber, transferencia) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_financeiro_write_delete`

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/financeiro/write/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (centrosDeCusto, conciliacao, contasFinanceiras, contratos, contratos/finalizar, contratos/itensContratos, contratos/itensContratos/cancelar, contratos/itensContratos/finalizar, contratos/itensContratos/suspender, formasPagamento, pagamentos, planoDeContasGerencial, recebimentos, tiposPagamentos, tiposTransacoes, titulosPagar, titulosReceber, transferencia) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_financeiro_write_patch`

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/financeiro/write/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (centrosDeCusto, conciliacao, contasFinanceiras, contratos, contratos/finalizar, contratos/itensContratos, contratos/itensContratos/cancelar, contratos/itensContratos/finalizar, contratos/itensContratos/suspender, formasPagamento, pagamentos, planoDeContasGerencial, recebimentos, tiposPagamentos, tiposTransacoes, titulosPagar, titulosReceber, transferencia) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_financeiro_write_update`

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/financeiro/write/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (centrosDeCusto, conciliacao, contasFinanceiras, contratos, contratos/finalizar, contratos/itensContratos, contratos/itensContratos/cancelar, contratos/itensContratos/finalizar, contratos/itensContratos/suspender, formasPagamento, pagamentos, planoDeContasGerencial, recebimentos, tiposPagamentos, tiposTransacoes, titulosPagar, titulosReceber, transferencia) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_list_accounts`

Lista os tenants (domínios) Bsoft conectados a este install — id, label e domínio. _(POST /api/bsoft/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |

#### `bsoft_manutencao`

Manutenção / Frota no Bsoft TMS (leitura). _(POST /api/bsoft/manutencao)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a consultar. (abastecimentos, abastecimentosProprios, combustiveis, equipamentos, marcas, modelos, ordensServico, pneus, tamanhos, tipos) |
| `id` | string | Não | Obter um registro específico por id. |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `offset` | integer | Não | Paginação: registro inicial (offset, base 0). Vira ?limit=offset,limit. |
| `limit` | integer | Não | Paginação: quantidade de registros (default 20, máx 100). |
| `query` | string | Não | Filtros como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Ex.: {"data_inicial":"2025-01-01"}. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_manutencao_write_create`

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/manutencao/write/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (abastecimentos, abastecimentosProprios, pneus) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_manutencao_write_create_lote`

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/manutencao/write/create/lote)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (abastecimentos, abastecimentosProprios, pneus) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_manutencao_write_delete`

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/manutencao/write/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (abastecimentos, abastecimentosProprios, pneus) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_manutencao_write_patch`

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/manutencao/write/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (abastecimentos, abastecimentosProprios, pneus) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_manutencao_write_update`

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/manutencao/write/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (abastecimentos, abastecimentosProprios, pneus) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_os`

Ordem de Serviço no Bsoft TMS (leitura). _(POST /api/bsoft/os)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a consultar. (categorias, ordensServico, ordensServico/acao, ordensServico/agendamentos, ordensServico/historicos, ordensServico/materiais, ordensServico/produtosServicos, status, tipos) |
| `id` | string | Não | Obter um registro específico por id. |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `offset` | integer | Não | Paginação: registro inicial (offset, base 0). Vira ?limit=offset,limit. |
| `limit` | integer | Não | Paginação: quantidade de registros (default 20, máx 100). |
| `query` | string | Não | Filtros como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Ex.: {"data_inicial":"2025-01-01"}. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_os_write_create`

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/os/write/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (ordensServico, ordensServico/acao) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_os_write_create_lote`

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/os/write/create/lote)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (ordensServico, ordensServico/acao) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_os_write_delete`

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/os/write/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (ordensServico, ordensServico/acao) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_os_write_patch`

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/os/write/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (ordensServico, ordensServico/acao) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_os_write_update`

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/os/write/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (ordensServico, ordensServico/acao) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_pessoas`

Pessoas no Bsoft TMS (leitura). _(POST /api/bsoft/pessoas)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a consultar. (pessoas/arquivos, pessoas/contasDepositos, pessoas/contatos, pessoas/enderecos, pessoas/fisicas, pessoas/fisicas/profissoes, pessoas/grupos/geral, pessoas/juridicas) |
| `id` | string | Não | Obter um registro específico por id. |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `offset` | integer | Não | Paginação: registro inicial (offset, base 0). Vira ?limit=offset,limit. |
| `limit` | integer | Não | Paginação: quantidade de registros (default 20, máx 100). |
| `query` | string | Não | Filtros como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Ex.: {"data_inicial":"2025-01-01"}. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_pessoas_write_create`

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/pessoas/write/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (pessoas/arquivos, pessoas/contasDepositos, pessoas/contatos, pessoas/enderecos, pessoas/estrangeiras, pessoas/fisicas, pessoas/juridicas) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_pessoas_write_create_lote`

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/pessoas/write/create/lote)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (pessoas/arquivos, pessoas/contasDepositos, pessoas/contatos, pessoas/enderecos, pessoas/estrangeiras, pessoas/fisicas, pessoas/juridicas) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_pessoas_write_delete`

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/pessoas/write/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (pessoas/arquivos, pessoas/contasDepositos, pessoas/contatos, pessoas/enderecos, pessoas/estrangeiras, pessoas/fisicas, pessoas/juridicas) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_pessoas_write_patch`

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/pessoas/write/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (pessoas/arquivos, pessoas/contasDepositos, pessoas/contatos, pessoas/enderecos, pessoas/estrangeiras, pessoas/fisicas, pessoas/juridicas) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_pessoas_write_update`

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/pessoas/write/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (pessoas/arquivos, pessoas/contasDepositos, pessoas/contatos, pessoas/enderecos, pessoas/estrangeiras, pessoas/fisicas, pessoas/juridicas) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_recursos`

Recursos (usuários do sistema) no Bsoft TMS (leitura). _(POST /api/bsoft/recursos)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a consultar. (recursos, recursos/grupos, recursos/inatividades, recursos/ipsAcesso) |
| `id` | string | Não | Obter um registro específico por id. |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `offset` | integer | Não | Paginação: registro inicial (offset, base 0). Vira ?limit=offset,limit. |
| `limit` | integer | Não | Paginação: quantidade de registros (default 20, máx 100). |
| `query` | string | Não | Filtros como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Ex.: {"data_inicial":"2025-01-01"}. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_recursos_write_create`

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/recursos/write/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (recursos, recursos/adicionarGrupo, recursos/ativar, recursos/inativar, recursos/inatividades, recursos/ipsAcesso, recursos/removerGrupo) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_recursos_write_create_lote`

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/recursos/write/create/lote)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (recursos, recursos/adicionarGrupo, recursos/ativar, recursos/inativar, recursos/inatividades, recursos/ipsAcesso, recursos/removerGrupo) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_recursos_write_delete`

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/recursos/write/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (recursos, recursos/adicionarGrupo, recursos/ativar, recursos/inativar, recursos/inatividades, recursos/ipsAcesso, recursos/removerGrupo) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_recursos_write_patch`

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/recursos/write/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (recursos, recursos/adicionarGrupo, recursos/ativar, recursos/inativar, recursos/inatividades, recursos/ipsAcesso, recursos/removerGrupo) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_recursos_write_update`

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/recursos/write/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (recursos, recursos/adicionarGrupo, recursos/ativar, recursos/inativar, recursos/inatividades, recursos/ipsAcesso, recursos/removerGrupo) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_transporte`

Transporte no Bsoft TMS (leitura). _(POST /api/bsoft/transporte)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a consultar. (agencias, apolicesSeguro, categoriasVeiculos, conhecimentos, conhecimentos/obterDacte, conhecimentos/obterDAMDFe, conjuntoVeiculos, contratosFrete, contratosFrete/operadorasCredito, contratosFrete/pdf, contratosFrete/valores, cotacoesFrete, especies, faturamentos, gruposVeiculos, manifestos, manifestos/obterDAMDFe, marcaVeiculos, naturezaCargas, naturezasOperacao, nfePreCadastrada, nfePreCadastrada/obterDANFE, ocorrencias, ocorrencias/anexos, ordensCarregamento, ordensCarregamento/mercadorias, ordensCarregamento/obterOC, paramCriaCteViaNFe, parametroCriacaoManifesto, pedidos, pedidos/mercadorias, pedidosConteiner, statusPedidos, tagsCTe, tiposOcorrencias, tiposOperacoesTMS, tiposTaloes, tiposValoresOutros, veiculos) |
| `id` | string | Não | Obter um registro específico por id. |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `offset` | integer | Não | Paginação: registro inicial (offset, base 0). Vira ?limit=offset,limit. |
| `limit` | integer | Não | Paginação: quantidade de registros (default 20, máx 100). |
| `query` | string | Não | Filtros como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Ex.: {"data_inicial":"2025-01-01"}. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_transporte_write_create`

Transporte no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/transporte/write/create)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (agencias, apolicesSeguro, conhecimentos, conhecimentos/viaNFe, conhecimentos/viaXML, conjuntoVeiculos, contratosFrete, especies, faturamentos, gruposVeiculos, manifestos/encerrar, manifestos/fechar, manifestos/reabrir, manifestos/viaXML, nfePreCadastrada, nfePreCadastrada/viaXML, ocorrencias, ocorrencias/anexos, statusPedidos, tagsCTe, tiposOperacoesTMS, tiposValoresOutros, veiculos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_transporte_write_create_lote`

Transporte no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/transporte/write/create/lote)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (agencias, apolicesSeguro, conhecimentos, conhecimentos/viaNFe, conhecimentos/viaXML, conjuntoVeiculos, contratosFrete, especies, faturamentos, gruposVeiculos, manifestos/encerrar, manifestos/fechar, manifestos/reabrir, manifestos/viaXML, nfePreCadastrada, nfePreCadastrada/viaXML, ocorrencias, ocorrencias/anexos, statusPedidos, tagsCTe, tiposOperacoesTMS, tiposValoresOutros, veiculos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_transporte_write_delete`

Transporte no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/transporte/write/delete)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (agencias, apolicesSeguro, conhecimentos, conhecimentos/viaNFe, conhecimentos/viaXML, conjuntoVeiculos, contratosFrete, especies, faturamentos, gruposVeiculos, manifestos/encerrar, manifestos/fechar, manifestos/reabrir, manifestos/viaXML, nfePreCadastrada, nfePreCadastrada/viaXML, ocorrencias, ocorrencias/anexos, statusPedidos, tagsCTe, tiposOperacoesTMS, tiposValoresOutros, veiculos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_transporte_write_patch`

Transporte no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/transporte/write/patch)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (agencias, apolicesSeguro, conhecimentos, conhecimentos/viaNFe, conhecimentos/viaXML, conjuntoVeiculos, contratosFrete, especies, faturamentos, gruposVeiculos, manifestos/encerrar, manifestos/fechar, manifestos/reabrir, manifestos/viaXML, nfePreCadastrada, nfePreCadastrada/viaXML, ocorrencias, ocorrencias/anexos, statusPedidos, tagsCTe, tiposOperacoesTMS, tiposValoresOutros, veiculos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

#### `bsoft_transporte_write_update`

Transporte no Bsoft TMS (escrita: cria/atualiza/remove). _(POST /api/bsoft/transporte/write/update)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Opcional quando há vários tenants Bsoft conectados (id, label ou domínio). Veja bsoft_list_accounts; omita se só houver um. |
| `resource` | string | Sim | Recurso do módulo a gravar. (agencias, apolicesSeguro, conhecimentos, conhecimentos/viaNFe, conhecimentos/viaXML, conjuntoVeiculos, contratosFrete, especies, faturamentos, gruposVeiculos, manifestos/encerrar, manifestos/fechar, manifestos/reabrir, manifestos/viaXML, nfePreCadastrada, nfePreCadastrada/viaXML, ocorrencias, ocorrencias/anexos, statusPedidos, tagsCTe, tiposOperacoesTMS, tiposValoresOutros, veiculos) |
| `id` | string | Não | Id do registro (update/patch/delete). |
| `parent_id` | string | Não | Id do registro-pai para recursos aninhados (ex.: id da viagem). |
| `body` | string | Não | Corpo da requisição como JSON string (campos conforme a doc do Bsoft; datas Y-m-d). Em create_lote, use uma lista JSON. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |
| `parent_ids` | string[] | Não | Bulk mode: multiple values for parent_id |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_bsoft` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
