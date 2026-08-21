# Ferramentas

Bsoft TMS expõe 45 ferramentas.

### 1. `bsoft_list_accounts`
**Input**: `account` (opcional)

Lista os tenants (domínios) Bsoft conectados a este install — id, label e domínio.

### 2. `bsoft_documentos_fiscais`
**Input**: `account` (opcional), `kind`, `tipo`, `query` (opcional), `body` (opcional)

Documentos fiscais eletrônicos do Bsoft (e-Doc) — o caso de uso principal.

### 3. `bsoft_documentos_fiscais_evento`
**Input**: `account` (opcional), `tipo`, `body`

Registrar EVENTO de documento fiscal no Bsoft (CT-e ou MDF-e): cancelamento, carta de correção, encerramento etc.

### 4. `bsoft_transporte`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `offset` (opcional), `limit` (opcional), `query` (opcional), `ids` (opcional), `parent_ids` (opcional)

Transporte no Bsoft TMS (leitura).

### 5. `bsoft_transporte_write_create`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Transporte no Bsoft TMS (escrita: cria/atualiza/remove).

### 6. `bsoft_transporte_write_create_lote`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Transporte no Bsoft TMS (escrita: cria/atualiza/remove).

### 7. `bsoft_transporte_write_update`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Transporte no Bsoft TMS (escrita: cria/atualiza/remove).

### 8. `bsoft_transporte_write_patch`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Transporte no Bsoft TMS (escrita: cria/atualiza/remove).

### 9. `bsoft_transporte_write_delete`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Transporte no Bsoft TMS (escrita: cria/atualiza/remove).

### 10. `bsoft_financeiro`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `offset` (opcional), `limit` (opcional), `query` (opcional), `ids` (opcional), `parent_ids` (opcional)

Financeiro no Bsoft TMS (leitura).

### 11. `bsoft_financeiro_write_create`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove).

### 12. `bsoft_financeiro_write_create_lote`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove).

### 13. `bsoft_financeiro_write_update`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove).

### 14. `bsoft_financeiro_write_patch`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove).

### 15. `bsoft_financeiro_write_delete`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Financeiro no Bsoft TMS (escrita: cria/atualiza/remove).

### 16. `bsoft_controle_viagens`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `offset` (opcional), `limit` (opcional), `query` (opcional), `ids` (opcional), `parent_ids` (opcional)

Controle de Viagens no Bsoft TMS (leitura).

### 17. `bsoft_controle_viagens_write_create`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove).

### 18. `bsoft_controle_viagens_write_create_lote`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove).

### 19. `bsoft_controle_viagens_write_update`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove).

### 20. `bsoft_controle_viagens_write_patch`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove).

### 21. `bsoft_controle_viagens_write_delete`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Controle de Viagens no Bsoft TMS (escrita: cria/atualiza/remove).

### 22. `bsoft_pessoas`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `offset` (opcional), `limit` (opcional), `query` (opcional), `ids` (opcional), `parent_ids` (opcional)

Pessoas no Bsoft TMS (leitura).

### 23. `bsoft_pessoas_write_create`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove).

### 24. `bsoft_pessoas_write_create_lote`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove).

### 25. `bsoft_pessoas_write_update`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove).

### 26. `bsoft_pessoas_write_patch`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove).

### 27. `bsoft_pessoas_write_delete`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Pessoas no Bsoft TMS (escrita: cria/atualiza/remove).

### 28. `bsoft_manutencao`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `offset` (opcional), `limit` (opcional), `query` (opcional), `ids` (opcional), `parent_ids` (opcional)

Manutenção / Frota no Bsoft TMS (leitura).

### 29. `bsoft_manutencao_write_create`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove).

### 30. `bsoft_manutencao_write_create_lote`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove).

### 31. `bsoft_manutencao_write_update`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove).

### 32. `bsoft_manutencao_write_patch`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove).

### 33. `bsoft_manutencao_write_delete`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Manutenção / Frota no Bsoft TMS (escrita: cria/atualiza/remove).

### 34. `bsoft_os`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `offset` (opcional), `limit` (opcional), `query` (opcional), `ids` (opcional), `parent_ids` (opcional)

Ordem de Serviço no Bsoft TMS (leitura).

### 35. `bsoft_os_write_create`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove).

### 36. `bsoft_os_write_create_lote`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove).

### 37. `bsoft_os_write_update`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove).

### 38. `bsoft_os_write_patch`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove).

### 39. `bsoft_os_write_delete`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Ordem de Serviço no Bsoft TMS (escrita: cria/atualiza/remove).

### 40. `bsoft_recursos`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `offset` (opcional), `limit` (opcional), `query` (opcional), `ids` (opcional), `parent_ids` (opcional)

Recursos (usuários do sistema) no Bsoft TMS (leitura).

### 41. `bsoft_recursos_write_create`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove).

### 42. `bsoft_recursos_write_create_lote`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove).

### 43. `bsoft_recursos_write_update`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove).

### 44. `bsoft_recursos_write_patch`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove).

### 45. `bsoft_recursos_write_delete`
**Input**: `account` (opcional), `resource`, `id` (opcional), `parent_id` (opcional), `body` (opcional), `ids` (opcional), `parent_ids` (opcional)

Recursos (usuários do sistema) no Bsoft TMS (escrita: cria/atualiza/remove).

## Prompts de exemplo

```
Liste os CT-e emitidos deste mês e me traga as chaves de acesso
Quais títulos a pagar vencem esta semana no financeiro?
Mostre as viagens em aberto e os adiantamentos dos motoristas
```
