# app-cam — Logs & CloudWatch

Log group: `/aws/lambda/app-cam-dev`. Perfil: `--profile api-dev --region us-east-1`.

## O que cada linha traz

- `msg:"request completed"` → uma requisição HTTP. Tem `path`, `method`,
  `status`, `user_id`, `company_id`, `site_id`, `correlation_id`, `request_body`
  e `response_body`. É a linha mais útil.
- Linhas de SQL (ORM/gorm) mostram a query real com valores e `[rows:N]`. **Não**
  carregam `correlation_id` — não dá para casar por correlação; use o horário.

## Receitas via CLI (`filter-log-events`)

Comece definindo a janela:

```bash
START=$(( ($(date +%s) - 21600) * 1000 ))   # últimas 6h
```

**1. Tudo que menciona um e-mail/nome** (login, criação de conta, convite).
Revela `INSERT INTO "yuser"`, os `SELECT ... WHERE email = ...` e os
`request_body:{"email":...}` dos convites.

```bash
aws logs filter-log-events --log-group-name /aws/lambda/app-cam-dev \
  --profile api-dev --region us-east-1 --start-time $START \
  --filter-pattern 'pessoa.exemplo' \
  --query 'events[].message' --output text
```

**2. Chamadas a um endpoint** (ex.: consultas de convite):

```bash
aws logs filter-log-events --log-group-name /aws/lambda/app-cam-dev \
  --profile api-dev --region us-east-1 --start-time $START \
  --filter-pattern '"me/invitations"' \
  --query 'events[].message' --output text
```

**3. Resposta de um usuário específico** (recorte com `grep` depois):

```bash
aws logs filter-log-events --log-group-name /aws/lambda/app-cam-dev \
  --profile api-dev --region us-east-1 --start-time $START \
  --filter-pattern '"me/invitations"' \
  --query 'events[].message' --output text \
  | grep '<USER_ID>' | grep -o '"response_body":"[^"]*"'
# ex.:  "response_body":"[]"   -> a lista veio vazia (convite não bate com a conta)
```

**4. Erros de login social** (o motivo real vive só no log; a resposta HTTP é
genérica de propósito):

```bash
aws logs filter-log-events --log-group-name /aws/lambda/app-cam-dev \
  --profile api-dev --region us-east-1 --start-time $START \
  --filter-pattern '?"id_token rejected" ?"code exchange failed" ?"state mismatch"' \
  --query 'events[].message' --output text
```

**5. Quais tabelas sofreram INSERT na janela** (mapa rápido do que aconteceu):

```bash
aws logs filter-log-events --log-group-name /aws/lambda/app-cam-dev \
  --profile api-dev --region us-east-1 --start-time $START \
  --filter-pattern 'INSERT' \
  --query 'events[].message' --output text \
  | grep -oiE 'INSERT INTO "[a-z_]+"' | sort | uniq -c
```

## Filtros no console (Logs Insights)

CloudWatch → **Logs Insights** → log group `/aws/lambda/app-cam-dev` → ajuste o
período no topo (sem epoch) e rode:

**Rastrear um e-mail em tudo:**

```
fields @timestamp, @message
| filter @message like /pessoa.exemplo/
| sort @timestamp asc
| limit 100
```

**Requisições de um usuário, só as colunas úteis:**

```
fields @timestamp, method, path, status, request_body, response_body
| filter user_id = "<USER_ID>"
| sort @timestamp asc
```

**Convites recebidos por uma conta (resposta vazia = não bate):**

```
fields @timestamp, user_id, status, response_body
| filter path = "/cam/me/invitations"
| filter user_id = "<USER_ID>"
| sort @timestamp asc
```

**Só erros (status >= 400):**

```
fields @timestamp, method, path, status, user_id, response_body
| filter status >= 400
| sort @timestamp desc
| limit 50
```

!!! tip
    Na busca simples do CloudWatch Logs (aba **Log events**, sem Insights) vale a
    **mesma sintaxe** do `--filter-pattern` do CLI.
