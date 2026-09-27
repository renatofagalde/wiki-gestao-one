# 5 · O plano de comissionamento

O plano é **o coração da coisa** — é onde a regra da sua corretora vira software.

!!! note "🖼️ Ilustração em construção"
    Os mockups das telas de **Operadoras** e **Planos** entram em breve.

## Antes: o catálogo

**Onde:** Comissões → **Operadoras**.

Cadastre a operadora (ex.: `PORTO SEGURO`) e seus produtos (`AUTO`,
`RESIDENCIAL`). Sem catálogo, o produto vira texto livre na venda — e
`PORTO SEGURO AUTO`, `Porto auto` e `porto seguro auto` viram três produtos no
relatório. O catálogo mantém o ranking honesto.

## O plano

**Onde:** Comissões → **Planos** → Novo plano.

Crie o plano: nome (`PLANO AUTO PADRÃO`), o produto do catálogo e o **desconto de
imposto** (ex.: 10%) — que sai do bruto **antes** de qualquer divisão.

Um plano é uma lista de **faixas de parcela**, e cada faixa tem **linhas de
rateio** que precisam somar exatamente **100%**.

### O nosso exemplo

**Faixa 1 — parcela 1:**

| Linha | % |
| --- | --- |
| Papel de time → `TIME SENNA` / `seller` | 100 |
| | **100 ✅** |

**Faixa 2 — parcela 2:**

| Linha | % |
| --- | --- |
| Papel de time → `TIME SENNA` / `seller` | 50 |
| Papel de time → `TIME SENNA` / `director` | 25 |
| Papel de time → `TIME SENNA` / `manager` | 25 |
| | **100 ✅** |

**Faixa 3 — da parcela 3 em diante:** marque **vitalício**. Sem essa faixa, da 3ª
parcela em diante ninguém recebe.

### Duas decisões que valem parar para pensar

1. **`seller` (papel de time) ou "Vendedor" (destinatário)?**
   *"Vendedor"* = quem fechou leva tudo (individual). Papel `seller` = divide
   entre todos os vendedores do time (coletivo). É política comercial, não técnica.
2. **Use o simulador.** Informe um prêmio de exemplo (ex.: R$ 1.200,00) e veja em
   reais quanto cada linha rende — antes de uma apólice real depender disso.

!!! warning "Plano é quase imutável"
    Não dá para editar/apagar uma linha isolada: remove-se a **faixa inteira** e
    monta de novo. Se o plano já tiver apólice emitida, a remoção é **bloqueada**.
    Para mudar a regra depois, crie um plano novo para as próximas vendas.

!!! success "Checkpoint"
    Todas as faixas com o selo verde de **100%** e o simulador batendo com o que
    você espera pagar.

→ Próximo: [Lead vira proposta](06-lead-proposta.md)
