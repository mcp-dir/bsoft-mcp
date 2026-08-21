# Bsoft TMS

### Bsoft TMS for Claude, ChatGPT and AI agents

Official Bsoft TMS API, the leading transportation management system for Brazilian carriers (Bsoft by nstech). Issue and query CT-e, MDF-e and NF-e, access keys, XML and PDF of fiscal documents, finance (payables/receivables, payments, receipts, contracts, reconciliation), fleet and maintenance, freight and bills of lading, trip control and party records. Connect with your Bsoft domain credentials (domain, integration-profile user and password).

- 📊 **45 tools**
- ✏️ **Read and write**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Bsoft TMS`, URL `https://api.mcp.ai/p_bsoft`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=bsoft&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9ic29mdCJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=bsoft&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_bsoft%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_bsoft
```

---

## 45 tools

| Tool | Description |
|---|---|
| `bsoft_list_accounts` | Lista os tenants (domínios) Bsoft conectados a este install — id, label e domínio. |
| `bsoft_documentos_fiscais` | Documentos fiscais eletrônicos do Bsoft (e-Doc) — o caso de uso principal. |
| `bsoft_documentos_fiscais_evento` | Registrar EVENTO de documento fiscal no Bsoft (CT-e ou MDF-e): cancelamento, carta de correção, encerramento etc. |
| `bsoft_transporte` | Transporte no Bsoft TMS (leitura). |
| `bsoft_transporte_write_create` | Transporte no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_transporte_write_create_lote` | Transporte no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_transporte_write_update` | Transporte no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_transporte_write_patch` | Transporte no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_transporte_write_delete` | Transporte no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_financeiro` | Financeiro no Bsoft TMS (leitura). |
| `bsoft_financeiro_write_create` | Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_financeiro_write_create_lote` | Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_financeiro_write_update` | Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_financeiro_write_patch` | Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_financeiro_write_delete` | Financeiro no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_controle_viagens` | Controle de Viagens no Bsoft TMS (leitura). |
| `bsoft_controle_viagens_write_create` | Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_controle_viagens_write_create_lote` | Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_controle_viagens_write_update` | Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_controle_viagens_write_patch` | Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_controle_viagens_write_delete` | Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_pessoas` | Pessoas no Bsoft TMS (leitura). |
| `bsoft_pessoas_write_create` | Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_pessoas_write_create_lote` | Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_pessoas_write_update` | Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_pessoas_write_patch` | Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_pessoas_write_delete` | Pessoas no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_manutencao` | Manutenção / Frota no Bsoft TMS (leitura). |
| `bsoft_manutencao_write_create` | Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_manutencao_write_create_lote` | Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_manutencao_write_update` | Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_manutencao_write_patch` | Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_manutencao_write_delete` | Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_os` | Ordem de Serviço no Bsoft TMS (leitura). |
| `bsoft_os_write_create` | Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_os_write_create_lote` | Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_os_write_update` | Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_os_write_patch` | Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_os_write_delete` | Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_recursos` | Recursos (usuários do sistema) no Bsoft TMS (leitura). |
| `bsoft_recursos_write_create` | Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_recursos_write_create_lote` | Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_recursos_write_update` | Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_recursos_write_patch` | Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). |
| `bsoft_recursos_write_delete` | Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove). |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_bsoft` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
