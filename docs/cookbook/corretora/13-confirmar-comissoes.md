# 13 · Confirmar as comissões

Ao emitir a apólice, as parcelas nascem **pendentes**. Confirmar uma parcela
significa "a operadora pagou esta" — e aí o sistema **roda o rateio** e credita
cada beneficiário. É o passo que transforma a regra do plano em dinheiro creditado.

## A tela — Comissões a confirmar

**Onde:** menu → **Comissões** → **Comissões pendentes** (a tela abre com o título
**Comissões a confirmar**).

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
  <text x="32" y="94" font-size="12.5" font-weight="700" fill="currentColor">Comissões pendentes</text>
  <text x="32" y="120" font-size="12.5" fill="currentColor" fill-opacity="0.7">Recebiveis da corretora</text>

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

## Passo a passo

| # | Onde | Ação | Detalhe |
| --- | --- | --- | --- |
| **1** | Caixas de seleção | Marcar as parcelas que a operadora **pagou** | Cada linha mostra bruto, imposto e líquido |
| **2** | **Confirmar selecionadas** | Rodar o rateio das marcadas | O lote vai uma a uma, com **relatório no fim** — **não** é tudo-ou-nada |

## Onde o dinheiro cai (pela matriz do exemplo)

- **Parcela 1** (`seller` 100%) → vai inteira para o **Massa**.
- **Parcela 2** (50 / 15 / 10 / 25) → **Massa** (50%), **Senna** (diretor, 15%),
  **Barrichello** (gerente, 10%) e a **corretora** (25%).
- **Parcela 3 em diante** (vitalício, 3 / 25 / 25 / 47) → segue creditando enquanto
  o cliente pagar.

!!! info "Confirmar não mostra a divisão"
    A confirmação apenas **libera** a parcela. O quanto cada beneficiário recebeu
    aparece na [tela de Recebíveis](14-recebiveis.md), não aqui.

!!! danger "Não há estorno pela interface"
    Confirmar é um caminho só de ida pela tela. Confira antes de confirmar em lote;
    em caso de erro, fale com o suporte.

!!! success "Checkpoint"
    As parcelas marcadas saem de **pendente**. O rateio já pode ser visto em
    Recebíveis.

→ Próximo: [14 · Recebíveis — o dinheiro distribuído](14-recebiveis.md)
