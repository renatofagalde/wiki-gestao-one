# 14 · Recebíveis — o dinheiro distribuído

É aqui que tudo se fecha: a comissão **confirmada** aparece **creditada a cada
pessoa**. A gestão vê o total da corretora por beneficiário; o vendedor vê **só o
dele**. Recebíveis é a tela que mostra o **rateio** — a confirmação não mostra.

## 14.1 · A visão do dono — por beneficiário

**Onde:** menu → **Comissões** → **Recebíveis**.

Valores do exemplo, depois de confirmar as **parcelas 1 e 2** (líquido de R$ 90,00
cada):

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 300" role="img"
     aria-label="Tela Recebíveis do dono, total da corretora por beneficiário"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="292" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="300" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one — Senna (dono/admin)</text>
  <line x1="190" y1="38" x2="190" y2="296" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.45">COMISSÕES</text>
  <text x="32" y="92" font-size="12.5" fill="currentColor" fill-opacity="0.7">A confirmar</text>
  <rect x="8" y="102" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="102" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="32" y="120" font-size="12.5" font-weight="700" fill="currentColor">Recebíveis</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Recebíveis</text>
  <text x="210" y="92" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.55">CORRETORA — POR BENEFICIÁRIO</text>
  <g font-size="12.5">
    <text x="228" y="120" fill="currentColor">Massa (seller)</text><text x="700" y="120" text-anchor="end" fill="currentColor">R$ 135,00</text>
    <text x="228" y="146" fill="currentColor">Senna (director)</text><text x="700" y="146" text-anchor="end" fill="currentColor">R$ 13,50</text>
    <text x="228" y="172" fill="currentColor">Barrichello (manager)</text><text x="700" y="172" text-anchor="end" fill="currentColor">R$ 9,00</text>
    <text x="228" y="198" fill="currentColor" fill-opacity="0.7">Casa (corretora)</text><text x="700" y="198" text-anchor="end" fill="currentColor" fill-opacity="0.7">R$ 22,50</text>
  </g>
  <line x1="210" y1="214" x2="730" y2="214" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="210" y="242" font-size="11.5" fill="currentColor" fill-opacity="0.6">O dono vê o total da corretora por pessoa: o que foi pra equipe e o que ficou na casa.</text>
  <text x="210" y="262" font-size="11" fill="currentColor" fill-opacity="0.5">P1: Massa 90,00 (100%). P2: Massa 45,00 · Senna 13,50 · Barrichello 9,00 · casa 22,50.</text>
</svg>
<figcaption>Tela <strong>Recebíveis</strong> — visão do dono, por beneficiário.</figcaption>
</figure>

A conta bate com a [matriz do plano](09-faixas-rateio.md): a **P1** foi 100% do
vendedor; a **P2** dividiu `50 / 15 / 10 / 25` sobre o líquido.

## 14.2 · A visão do vendedor — só o dele

O mesmo caminho, logado como **Massa**: ele vê **Seus recebíveis** — apenas os
valores dele, sem o agregado da corretora.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 250" role="img"
     aria-label="Tela Recebíveis do vendedor, mostrando só os valores dele"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="242" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="300" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one — Massa (vendedor)</text>
  <line x1="190" y1="38" x2="190" y2="246" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="13" fill="currentColor" fill-opacity="0.7">Início</text>
  <rect x="8" y="78" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="78" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="22" y="96" font-size="12.5" font-weight="700" fill="currentColor">Seus recebíveis</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Seus recebíveis</text>
  <g font-size="12.5">
    <text x="228" y="102" fill="currentColor" fill-opacity="0.7">Total recebido</text><text x="700" y="102" text-anchor="end" font-weight="700" fill="currentColor">R$ 135,00</text>
    <text x="228" y="128" fill="currentColor" fill-opacity="0.7">A receber</text><text x="700" y="128" text-anchor="end" fill="currentColor">R$ 27,00</text>
  </g>
  <line x1="210" y1="144" x2="730" y2="144" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="210" y="168" font-size="11" font-weight="700" fill="currentColor" fill-opacity="0.55">POR APÓLICE</text>
  <text x="228" y="190" font-size="12" fill="currentColor">Apólice #1024 · Parcela 1 · seller (100%)</text><text x="700" y="190" font-size="12" text-anchor="end" fill="currentColor">R$ 90,00</text>
  <text x="228" y="210" font-size="12" fill="currentColor">Apólice #1024 · Parcela 2 · seller (50%)</text><text x="700" y="210" font-size="12" text-anchor="end" fill="currentColor">R$ 45,00</text>
  <text x="210" y="234" font-size="11" fill="currentColor" fill-opacity="0.5">Confirme mais uma parcela no navegador do dono e recarregue: este valor sobe.</text>
</svg>
<figcaption>Tela <strong>Seus recebíveis</strong> — o vendedor vê só o dele.</figcaption>
</figure>

!!! info "Por que o valor muda a cada parcela"
    O plano define percentuais diferentes por faixa (a P1 paga 100% ao vendedor; da
    P3 em diante entra o rateio vitalício). Por isso o valor por parcela **não é
    constante**.

## O teste dos dois navegadores

A demonstração mais convincente do produto:

1. **Navegador 1 — Senna (dono)**, em **Recebíveis**: vê o total por beneficiário.
2. **Navegador 2 (anônimo) — Massa (vendedor)**, em **Seus recebíveis**: vê só o
   dele.
3. Confirme mais uma parcela no navegador 1 e **recarregue** o 2: **o valor do
   Massa sobe**. O vendedor nunca enxerga o agregado da corretora — só o próprio.

## Conta corrente (o caixa)

Fora do ciclo de vendas, mas logo ao lado:

- **Conta corrente** (gestão): saldo da corretora e todos os movimentos.
- **Meu extrato** (todos): os lançamentos da própria pessoa.

Recebíveis mostra o **direito** (quanto cada um tem a receber); a conta corrente
mostra o **caixa** (o que efetivamente entrou e saiu).

!!! success "Fim do roteiro"
    Do **zero** (uma conta) ao **dinheiro distribuído** por uma regra que você mesmo
    desenhou. Esse é o ciclo completo da Corretora — os 14 passos, uma tela de cada
    vez.
