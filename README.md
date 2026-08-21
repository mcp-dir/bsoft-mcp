# Bsoft TMS

### Bsoft TMS para Claude, ChatGPT e agentes de IA

API oficial do Bsoft TMS, sistema líder de gestão de transportadoras do Brasil (Bsoft by nstech). Emissão e consulta de CT-e, MDF-e e NF-e, chaves de acesso, XML e PDF dos documentos fiscais, financeiro (títulos a pagar/receber, pagamentos, recebimentos, contratos, conciliação), frota e manutenção, fretes e conhecimentos, controle de viagens e cadastros de pessoas. Conecte com as credenciais do seu domínio Bsoft (domínio, usuário com perfil de integração e senha).

- 📊 **45 ferramentas**
- ✏️ **Leitura e escrita**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Bsoft TMS` e **URL** `https://api.mcp.ai/p_bsoft`.

### Cursor

[➕ Instalar Bsoft TMS no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=bsoft&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9ic29mdCJ9)

### VS Code (Copilot Chat)

[➕ Instalar Bsoft TMS no VS Code](vscode:mcp/install?name=bsoft&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_bsoft%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_bsoft
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Liste os CT-e emitidos deste mês e me traga as chaves de acesso
Quais títulos a pagar vencem esta semana no financeiro?
Mostre as viagens em aberto e os adiantamentos dos motoristas
```

---

## 45 ferramentas disponíveis

| Tool | Descrição |
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

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Sub-processadores**: Bsoft (Bsoft Internetworks / nstech), o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_bsoft`.


---

## Suporte

- 📧 [bsoft@mcp.ai](mailto:bsoft@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/bsoft-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_bsoft` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
