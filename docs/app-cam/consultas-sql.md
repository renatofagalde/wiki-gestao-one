# app-cam — Consultas SQL

Rodar no cliente SQL contra o banco do ambiente. Tabelas reais: `public.yuser`,
`public.user_identity`, `public.company`, `public.company_user`.

!!! warning "Repositório público"
    Os e-mails/ids abaixo são **exemplos** (`pessoa.exemplo@gmail.com`,
    `01a0e300-…`). Troque pelos valores reais só na sua sessão — não commite dado
    de cliente.

## A pessoa tem conta?

O convite **exige** conta já existente (`company_user.user_id` é
`NOT NULL REFERENCES yuser(id)`). Primeiro confirme que a conta existe e com qual
grafia de e-mail:

```sql
SELECT id, hash, email, name,
       (password = '!social') AS is_social,
       email_verified, is_active, created_at
FROM public.yuser
WHERE email = 'pessoa.exemplo@gmail.com';
```

## Localizar o convite de uma pessoa numa corretora

```sql
SELECT cu.hash          AS invite_hash,
       cu.status,                       -- invited | accepted | declined | removed
       cu.invited_at,
       cu.accepted_at,
       c.name           AS company_name,
       u.email          AS invited_email,
       inv.email        AS invited_by_email
FROM public.company_user cu
JOIN public.yuser   u   ON u.id  = cu.user_id
JOIN public.company c   ON c.id  = cu.company_id
LEFT JOIN public.yuser inv ON inv.id = cu.invited_by
WHERE u.email = 'pessoa.exemplo@gmail.com'
  AND cu.deleted_at IS NULL;
```

Resultado vazio = o convite **não virou linha** (típico de e-mail digitado errado;
ver [Casos](casos.md#convite-nao-aparece)).

## Membros/convites de uma corretora

Pelo `hash` da company (o mesmo que aparece no header `X-Company-ID`):

```sql
SELECT u.email, u.name, cu.status, cu.invited_at, cu.accepted_at
FROM public.company_user cu
JOIN public.yuser   u ON u.id = cu.user_id
JOIN public.company c ON c.id = cu.company_id
WHERE c.hash = '<COMPANY_HASH>'
  AND cu.deleted_at IS NULL
ORDER BY cu.status, u.email;
```

## Caçar variação de e-mail (typo, ponto do Gmail)

O app casa e-mail por string exata; esta busca aproximada acha o "quase igual":

```sql
SELECT id, email, name, created_at
FROM public.yuser
WHERE email ILIKE '%exemplo%';
```

## Identidade social de uma conta

```sql
SELECT i.provider, i.provider_user_id, u.email, i.created_at
FROM public.user_identity i
JOIN public.yuser u ON u.id = i.user_id
WHERE u.email = 'pessoa.exemplo@gmail.com';
```
