# Docs técnicas do gestao.one

Base de conhecimento técnico e de **operação** do gestao.one, organizada por
módulo. Serve para investigar comportamento em DEV/PRD sem adivinhação: achar o
que uma Lambda fez, cruzar com o banco e explicar o resultado.

!!! warning "Repositório público"
    Nunca coloque dado real aqui — e-mail de pessoa, `user_id`, `hash` de
    corretora, IP, token. Use placeholders (`pessoa.exemplo@gmail.com`,
    `01a0e300-0000-…`). Comandos e queries, sim; dados de cliente, não.

## Módulos

| Módulo | Assunto |
| --- | --- |
| [app-cam](app-cam/index.md) | Autenticação, contas, identidades sociais, convites, RBAC |
| [app-not](app-not/index.md) | Notificações / e-mail |
| [app-cms](app-cms/index.md) | Conteúdo |

## Convenções (todos os módulos)

**Log group por app/ambiente:** `/aws/lambda/<app>-<ambiente>` — ex.:
`/aws/lambda/app-cam-dev`.

**Perfil e região (DEV):** `--profile api-dev --region us-east-1`.

**Janela de tempo.** O `--start-time` do `filter-log-events` é **epoch em
milissegundos**:

```bash
START=$(( ($(date +%s) - 21600) * 1000 ))   # últimas 6h
START=$(( ($(date +%s) -   900) * 1000 ))   # últimos 15min
```

**Sintaxe do `--filter-pattern`.**

- Termo solto (`company_user`) → substring no texto do evento.
- Termo com barra/pontuação → **entre aspas**: `'"me/invitations"'`.
- OU entre termos: `'?"state mismatch" ?"code exchange failed"'`.

**Extrair só a mensagem:** `--query 'events[].message' --output text`.

**Limpar cores ANSI do log de SQL:** `... | sed 's/\x1b\[[0-9;]*m//g'`.
