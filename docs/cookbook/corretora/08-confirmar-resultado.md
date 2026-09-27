# 8 · Confirmar e ver o dinheiro chegar

É aqui que tudo se fecha: a comissão sai de "pendente" e **cai na conta de cada
pessoa** — e o vendedor vê isso na tela dele.

## 8.1 · Comissões a confirmar

**Onde:** menu → **Comissões** → **A confirmar**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 330" role="img"
     aria-label="Tela Comissões a confirmar com parcelas selecionáveis e o botão Confirmar selecionadas"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="322" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>
  <line x1="190" y1="38" x2="190" y2="326" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.45">COMISSÕES</text>
  <rect x="8" y="76" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="76" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="32" y="94" font-size="12.5" font-weight="700" fill="currentColor">A confirmar</text>
  <text x="32" y="120" font-size="12.5" fill="currentColor" fill-opacity="0.7">Recebíveis</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Comissões a confirmar</text>
  <!-- cabeçalho de colunas -->
  <text x="252" y="96" font-size="10.5" fill="currentColor" fill-opacity="0.55">Parcela</text>
  <text x="470" y="96" font-size="10.5" fill="currentColor" fill-opacity="0.55" text-anchor="end">Bruto</text>
  <text x="570" y="96" font-size="10.5" fill="currentColor" fill-opacity="0.55" text-anchor="end">Imposto</text>
  <text x="700" y="96" font-size="10.5" fill="currentColor" fill-opacity="0.55" text-anchor="end">Líquido</text>
  <!-- linhas -->
  <g font-size="12">
    <rect x="228" y="108" width="14" height="14" rx="3" fill="currentColor" fill-opacity="0.14" stroke="currentColor" stroke-opacity="0.4"/>
    <text x="252" y="120" fill="currentColor">Parcela 1 / 12</text><text x="470" y="120" fill="currentColor" text-anchor="end">100,00</text><text x="570" y="120" fill="currentColor" text-anchor="end">10,00</text><text x="700" y="120" fill="currentColor" text-anchor="end">90,00</text>
    <rect x="228" y="132" width="14" height="14" rx="3" fill="currentColor" fill-opacity="0.14" stroke="currentColor" stroke-opacity="0.4"/>
    <text x="252" y="144" fill="currentColor">Parcela 2 / 12</text><text x="470" y="144" fill="currentColor" text-anchor="end">100,00</text><text x="570" y="144" fill="currentColor" text-anchor="end">10,00</text><text x="700" y="144" fill="currentColor" text-anchor="end">90,00</text>
    <rect x="228" y="156" width="14" height="14" rx="3" fill="none" stroke="currentColor" stroke-opacity="0.4"/>
    <text x="252" y="168" fill="currentColor" fill-opacity="0.7">Parcela 3 / 12</text><text x="470" y="168" fill="currentColor" fill-opacity="0.7" text-anchor="end">100,00</text><text x="570" y="168" fill="currentColor" fill-opacity="0.7" text-anchor="end">10,00</text><text x="700" y="168" fill="currentColor" fill-opacity="0.7" text-anchor="end">90,00</text>
  </g>
  <rect x="536" y="196" width="186" height="34" rx="7" fill="currentColor" fill-opacity="0.14"/><text x="629" y="218" font-size="12.5" font-weight="600" fill="currentColor" text-anchor="middle">Confirmar selecionadas</text>
  <text x="210" y="268" font-size="11.5" fill="currentColor" fill-opacity="0.6">Confirmar = a operadora pagou → o sistema roda o rateio e credita cada um.</text>
  <text x="210" y="288" font-size="11.5" fill="currentColor" fill-opacity="0.6">Não existe estorno pela interface. A divisão aparece em Recebíveis.</text>
  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="228" cy="115" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="228" y="119" fill="currentColor">1</text>
    <circle cx="536" cy="196" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="536" y="200" fill="currentColor">2</text>
  </g>
</svg>
<figcaption>Tela <strong>Comissões a confirmar</strong>: bruto − imposto = líquido.</figcaption>
</figure>

| # | Onde | Ação |
| --- | --- | --- |
| **1** | Caixas de seleção | Marcar as parcelas pagas pela operadora |
| **2** | **Confirmar selecionadas** | Roda o rateio; o lote **não é tudo-ou-nada** |

- Parcela 1 (100% `seller`) → vai para Bruno e Carla.
- Parcela 2 (50/25/25) → vendedores, Renato e Marina.

## 8.2 · Recebíveis — a visão do dono

**Onde:** menu → **Comissões** → **Recebíveis**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 300" role="img"
     aria-label="Tela Recebíveis do dono, total da corretora por beneficiário"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="292" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one — dono (admin)</text>
  <line x1="190" y1="38" x2="190" y2="296" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.45">COMISSÕES</text>
  <text x="32" y="92" font-size="12.5" fill="currentColor" fill-opacity="0.7">A confirmar</text>
  <rect x="8" y="102" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="102" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="32" y="120" font-size="12.5" font-weight="700" fill="currentColor">Recebíveis</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Recebíveis</text>
  <text x="210" y="92" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.55">CORRETORA — POR BENEFICIÁRIO</text>
  <g font-size="12.5">
    <text x="228" y="120" fill="currentColor">Bruno (seller)</text><text x="700" y="120" text-anchor="end" fill="currentColor">R$ 90,00</text>
    <text x="228" y="146" fill="currentColor">Carla (seller)</text><text x="700" y="146" text-anchor="end" fill="currentColor">R$ 90,00</text>
    <text x="228" y="172" fill="currentColor">Renato (director)</text><text x="700" y="172" text-anchor="end" fill="currentColor">R$ 22,50</text>
    <text x="228" y="198" fill="currentColor">Marina (manager)</text><text x="700" y="198" text-anchor="end" fill="currentColor">R$ 22,50</text>
    <text x="228" y="224" fill="currentColor" fill-opacity="0.7">Casa (corretora)</text><text x="700" y="224" text-anchor="end" fill="currentColor" fill-opacity="0.7">R$ 0,00</text>
  </g>
  <line x1="210" y1="240" x2="730" y2="240" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="210" y="268" font-size="11.5" fill="currentColor" fill-opacity="0.6">O dono vê o total da corretora por pessoa: o que ficou na casa e o que foi pra equipe.</text>
</svg>
<figcaption>Tela <strong>Recebíveis</strong> — visão do dono, por beneficiário.</figcaption>
</figure>

## 8.3 · Recebíveis — a visão do vendedor

O mesmo caminho, logado como **Bruno**: ele vê **só o dele**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 250" role="img"
     aria-label="Tela Recebíveis do vendedor, mostrando só os valores dele"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="242" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="300" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one — Bruno (vendedor)</text>
  <line x1="190" y1="38" x2="190" y2="246" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="13" fill="currentColor" fill-opacity="0.7">Início</text>
  <rect x="8" y="78" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="78" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="22" y="96" font-size="12.5" font-weight="700" fill="currentColor">Seus recebíveis</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Seus recebíveis</text>
  <g font-size="12.5">
    <text x="228" y="102" fill="currentColor" fill-opacity="0.7">Total recebido</text><text x="700" y="102" text-anchor="end" font-weight="700" fill="currentColor">R$ 90,00</text>
    <text x="228" y="128" fill="currentColor" fill-opacity="0.7">A receber</text><text x="700" y="128" text-anchor="end" fill="currentColor">R$ 990,00</text>
  </g>
  <line x1="210" y1="144" x2="730" y2="144" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="210" y="168" font-size="11" font-weight="700" fill="currentColor" fill-opacity="0.55">POR APÓLICE</text>
  <text x="228" y="190" font-size="12" fill="currentColor">Apólice #1024 · Parcela 1 · seller (100%)</text><text x="700" y="190" font-size="12" text-anchor="end" fill="currentColor">R$ 90,00</text>
  <text x="210" y="224" font-size="11.5" fill="currentColor" fill-opacity="0.6">Confirme mais uma parcela no navegador do dono e recarregue: este valor sobe.</text>
</svg>
<figcaption>Tela <strong>Seus recebíveis</strong> — o vendedor vê só o dele.</figcaption>
</figure>

## O teste dos dois navegadores

1. **Navegador 1 — dono**, em **Recebíveis**: vê o total por beneficiário.
2. **Navegador 2 (anônimo) — Bruno**, em **Seus recebíveis**: vê só o dele.
3. Confirme mais uma parcela no navegador 1 e **recarregue** o 2: **o valor do
   Bruno sobe.** É a demonstração mais convincente do produto.

## Conta corrente

- **Saldo e movimentos** (gestão): saldo da corretora e todos os movimentos.
- **Meu extrato** (todos): os lançamentos da própria pessoa.

Recebíveis mostra o **direito**; a conta corrente mostra o **caixa**.

!!! success "Fim do roteiro"
    Do **zero** (uma conta) ao **dinheiro distribuído** por uma regra que você
    desenhou. Esse é o ciclo completo da Corretora.
