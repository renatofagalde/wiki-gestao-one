# Cookbook · Corretora

Roteiro do **zero até a comissão paga**, montando uma corretora de exemplo. Serve
como **treinamento** (siga na ordem) e como **roteiro de demo**.

## O elenco do exemplo

| Pessoa | Faz o quê | Perfil de acesso | Papel no time |
| --- | --- | --- | --- |
| Renato | dono | `admin` | `director` (diretor) |
| Marina | gerente comercial | `gerente` | `manager` (gerente) |
| Bruno | vendedor | `vendedor` | `seller` |
| Carla | vendedora | `vendedor` | `seller` |

!!! warning "Os dois papéis não se misturam"
    - **Perfil de acesso** (`admin`, `gerente`, `vendedor`) = **o que a pessoa vê
      e faz** nas telas.
    - **Papel de time** (`director`, `manager`, `seller`) = **quanto a pessoa
      ganha** no rateio.

    Marina pode ser `gerente` no acesso e `seller` no time — decisões
    independentes. Confundir os dois é o erro nº 1.

## A ordem importa

O sistema tem dependências duras: cada etapa só existe porque a anterior existe.

```
Conta → Convite → Time → Plano de comissão
                              ↓
     Cliente → Lead → Proposta → APÓLICE
                              ↓
             Comissões pendentes → confirmar
                              ↓
                    Recebíveis (o dinheiro)
```

## Os passos

1. [Criar sua conta](01-criar-conta.md)
2. [Sou usuário — esperar o convite](02-esperar-convite.md)
3. [Sou dono — convidar a equipe](03-convidar.md)
4. [Criar um time e distribuir papéis](04-time.md)
5. [O plano de comissionamento](05-plano.md)
6. [Lead vira proposta (e nasce a apólice)](06-lead-proposta.md)
7. [Confirmar e ver o dinheiro chegar](07-confirmar-resultado.md)

Cada passo mostra **onde clicar**, **o que preencher** e **o resultado** — o que
muda no sistema e quem passa a enxergar o quê.
