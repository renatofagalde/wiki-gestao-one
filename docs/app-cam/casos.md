# app-cam — Casos resolvidos

## Convite não aparece {#convite-nao-aparece}

**Sintoma.** O dono convida alguém; a pessoa loga no console e a tela **Meus
convites** fica vazia.

### Suspeito descartado — não é o domínio

Existem restrições de domínio em DEV, mas **nenhuma** esvazia a lista de convites:

- **Envio de e-mail** fica no sandbox SES, restrito a um domínio verificado —
  afeta só a *notificação por e-mail*, não a lista `/cam/me/invitations`.
- **Google OAuth em modo "Teste"** só deixa logar quem está na lista de usuários
  de teste — barra o *login*, não o convite.

### Causa real — typo no e-mail

Exemplo (anonimizado):

- Conta da pessoa (login Google OK): `pessoa.exemplo@gmail.com` **com ponto**.
- Convite enviado para: `pessoaexemplo@gmail.com` **sem ponto**.

Nos logs: `SELECT * FROM "yuser" WHERE email = 'pessoaexemplo@gmail.com'` →
`[rows:0]`, e mesmo assim `response_body:{"status":"invitation_processed"}` com
**201**. As chamadas `/cam/me/invitations` da conta voltaram `[]`.

### Por que 201 mesmo sem achar ninguém?

É **anti-enumeração por design**. O `Invite` faz `GetByEmail`; se o e-mail não
existe, o handler devolve um 201 neutro para **não revelar** se aquele e-mail tem
conta. Consequência prática: **convidar e-mail errado não dá erro na tela** — por
isso o typo passa despercebido. Confirmação no schema: `company_user.user_id` é
`NOT NULL REFERENCES yuser(id)` — sem usuário, não há linha de convite.

### Roteiro de confirmação

1. A conta existe e com qual grafia? → SQL
   [*A pessoa tem conta?*](consultas-sql.md#a-pessoa-tem-conta) +
   [*caçar variação*](consultas-sql.md#cacar-variacao-de-e-mail-typo-ponto-do-gmail).
2. O convite virou linha? → SQL
   [*localizar o convite*](consultas-sql.md#localizar-o-convite-de-uma-pessoa-numa-corretora)
   (vazio = não criou).
3. O que a conta recebe? → [receita 3 do CLI](logs-cloudwatch.md#receitas-via-cli-filter-log-events)
   ou a query de Insights *"convites recebidos"* (resposta `[]` = não bate).

### Correção

Reenviar o convite usando **exatamente** o e-mail da conta. Assim que casar,
aparece na hora em Meus convites — independe de o e-mail chegar.
