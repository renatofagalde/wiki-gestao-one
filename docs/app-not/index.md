# app-not — visão geral

Módulo de **notificações / e-mail**. Consome eventos (ex.: `company_user.invited`
via SQS) e envia e-mail (SES).

- **Log group:** `/aws/lambda/app-not-dev`

!!! note "A preencher"
    Casos a documentar:

    - E-mail de convite não chega — sandbox SES restrito a domínio verificado em DEV.
    - Deduplicação por idempotency key (`company_user.invited:<company>:<user>`).
    - Reentrega SQS / DLQ.
