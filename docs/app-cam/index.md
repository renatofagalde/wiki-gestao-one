# app-cam — visão geral

Módulo de **autenticação e acesso**: contas de usuário (`yuser`), identidades
sociais (`user_identity`), diretório de membros e **convites** de corretora
(`company_user`) e RBAC (`/cam/users/me/access`).

- **Log group:** `/aws/lambda/app-cam-dev`
- **Banco:** PostgreSQL — tabelas principais `yuser`, `user_identity`,
  `company`, `company_user`.

## Nesta seção

- [Logs & CloudWatch](logs-cloudwatch.md) — receitas de CLI e filtros de console.
- [Consultas SQL](consultas-sql.md) — localizar conta, convite, membros.
- [Casos resolvidos](casos.md) — diagnósticos ponta a ponta.

## Conceitos que mais geram dúvida

**Convite exige conta já existente.** `company_user.user_id` é
`NOT NULL REFERENCES yuser(id)`. Só é possível convidar quem já é usuário do
sistema.

**Convidar por e-mail é anti-enumeração.** Se o e-mail não tem conta, o endpoint
responde **201 neutro** e **não cria nada** — para não revelar se o e-mail
existe. Efeito colateral operacional: **convidar e-mail errado não dá erro na
tela**. Ver [Casos resolvidos › Convite não aparece](casos.md#convite-nao-aparece).

**Restrições de domínio em DEV** existem, mas afetam coisas diferentes:

- *Envio de e-mail* fica no sandbox SES, restrito a um **domínio verificado** —
  afeta só a notificação, não a lista de convites.
- *Login social (Google)* em modo "Teste" só aceita e-mails cadastrados como
  usuários de teste — afeta o login, não o convite.

**E-mail é chave literal.** O sistema casa e-mail por **string exata**. O Gmail
ignora pontos no local-part (`joao.silva@` = `joaosilva@` na entrega), mas para o
app são endereços diferentes.
