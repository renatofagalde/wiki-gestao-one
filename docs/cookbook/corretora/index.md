# Cookbook · Corretora

Roteiro do **zero até a comissão paga**, montando uma corretora de exemplo. Serve
como **treinamento** (siga na ordem) e como **roteiro de demo**.

Esta é a **visão geral**. Cada tela do sistema é um **passo próprio**, na ordem em
que você realmente executa — veja a lista em [Os passos](#os-passos).

## O elenco do exemplo

Três pessoas, uma corretora: **Senna Racing Seguros**.

| Pessoa | Faz o quê | Perfil de acesso | Papel no time | E-mail |
| --- | --- | --- | --- | --- |
| **Senna** | dono | `admin` | `director` (diretor) | `senna@f1.test` |
| **Barrichello** | gerente comercial | `gerente` | `manager` (gerente) | `barrichello@f1.test` |
| **Massa** | vendedor | `vendedor` | `seller` (vendedor) | `massa@f1.test` |

!!! warning "Os dois papéis não se misturam"
    - **Perfil de acesso** (`admin`, `gerente`, `vendedor`) = **o que a pessoa vê
      e faz** nas telas.
    - **Papel de time** (`director`, `manager`, `seller`) = **quanto a pessoa
      ganha** no rateio da comissão.

    Uma pessoa pode ser `gerente` no acesso e `seller` no time — decisões
    independentes. Confundir os dois é o erro nº 1.

## A ordem importa

O sistema tem dependências duras: cada etapa só existe porque a anterior existe.

```
Conta
  ├─ dono:    cria a corretora (onboarding)
  └─ usuário: aceita o convite
                  ↓
        Equipe convidada → Perfil de acesso → Time (papéis)
                  ↓
        Catálogo → Plano de comissão → Faixas de rateio
                  ↓
        Cliente → Lead → Proposta → APÓLICE
                  ↓
        Confirmar comissões → Recebíveis (o dinheiro)
```

## Convenções que valem em todo o sistema

Três regras aparecem em quase toda tela — entenda-as uma vez:

| Convenção | O que significa na prática |
| --- | --- |
| **Texto em MAIÚSCULO** | Nome, operadora, produto e afins são gravados em **maiúsculo**. A tela mostra em caixa alta; não é "grito", é o padrão do dado. |
| **Dinheiro é decimal, não número** | Valores têm **4 casas** (`NUMERIC(15,4)`). Digite `1500,00`; o sistema guarda o valor exato, sem arredondar por conta própria. |
| **O menu vem do servidor** | O que cada pessoa vê é definido pelo **perfil de acesso** (RBAC). Botão sem permissão aparece **desabilitado** — não é bug, é o acesso. |

## Os passos

Cada passo é **uma tela**. Mostra **onde clicar**, **o que preencher** e **o
resultado** — o que muda no sistema e quem passa a enxergar o quê.

1. [Criar sua conta](01-criar-conta.md)
2. [Sou usuário — aceitar o convite](02-aceitar-convite.md)
3. [Sou dono — criar a corretora (onboarding)](03-criar-corretora.md)
4. [Convidar a equipe](04-convidar.md)
5. [Atribuir perfil de acesso](05-perfil-acesso.md)
6. [Montar o time comercial](06-time.md)
7. [Catálogo — operadoras e produtos](07-operadoras.md)
8. [Criar o plano de comissão](08-criar-plano.md)
9. [Montar as faixas e o rateio](09-faixas-rateio.md)
10. [Cadastrar o cliente](10-cliente.md)
11. [Abrir e converter o lead](11-lead.md)
12. [Proposta e emissão da apólice](12-proposta-apolice.md)
13. [Confirmar as comissões](13-confirmar-comissoes.md)
14. [Recebíveis — o dinheiro distribuído](14-recebiveis.md)

!!! tip "Dois caminhos no começo"
    Os passos 1–3 se dividem por papel: quem **é convidado** segue para o passo 2
    (aceitar o convite); quem **monta a corretora** segue para o passo 3
    (onboarding). Do passo 4 em diante, o roteiro é do **dono**.
