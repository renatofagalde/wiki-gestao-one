# AWS — contas e switch role

!!! danger "Repositório público — não coloque números reais aqui"
    Número de conta AWS e nome de role de acesso **não** entram num repo público:
    facilitam enumeração de `assume-role`, sondagem de trust policy e phishing
    direcionado. Esta página documenta **o procedimento**; os valores reais ficam
    num cofre privado (SSM, gerenciador de senhas, ou um doc privado). Veja
    [Onde guardar os valores reais](#onde-guardar-os-valores-reais).

## Contas (template)

| Ambiente | Account ID | Perfil AWS local | Papel |
| --- | --- | --- | --- |
| Management / root | `<ACCOUNT_ROOT>` | `api-gestao-one` | conta pagadora / origem do switch role |
| DEV | `<ACCOUNT_DEV>` | `api-dev` | ambiente de desenvolvimento |
| PRD | `<ACCOUNT_PRD>` | `api-prd` | produção |

## Switch role (console AWS)

A partir da conta de origem (management/root), troca-se para a conta alvo
assumindo uma role de acesso cross-account:

1. Menu do usuário (canto superior direito) → **Switch role**.
2. Preencher:
   - **Account:** o Account ID do alvo (`<ACCOUNT_DEV>` ou `<ACCOUNT_PRD>`).
   - **Role:** o nome da role de acesso — `<SWITCH_ROLE_NAME>`
     (em orgs criadas pelo AWS Organizations, o padrão é
     `OrganizationAccountAccessRole`).
   - **Display name / Color:** rótulo para reconhecer a sessão.

## Switch role (CLI)

Configurar no `~/.aws/config` um profile que assume a role a partir de outro:

```ini
[profile dev-admin]
role_arn = arn:aws:iam::<ACCOUNT_DEV>:role/<SWITCH_ROLE_NAME>
source_profile = api-gestao-one
region = us-east-1

[profile prd-admin]
role_arn = arn:aws:iam::<ACCOUNT_PRD>:role/<SWITCH_ROLE_NAME>
source_profile = api-gestao-one
region = us-east-1
```

Depois:

```bash
aws sts get-caller-identity --profile dev-admin    # confirma que assumiu a role
```

## Onde guardar os valores reais

Substitua `<ACCOUNT_*>` e `<SWITCH_ROLE_NAME>` **fora** deste repo:

- **Parameter Store (SSM)** como `String`/`SecureString`, ou
- gerenciador de senhas do time, ou
- um doc **privado** (ex.: um repo privado de operação).

O `~/.aws/config` local de cada pessoa já contém os `role_arn` reais — ele é a
fonte da verdade da máquina, e não é versionado.
