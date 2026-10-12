# 8 · Criar o plano de comissão

O plano é **o coração da coisa** — é onde a regra da sua corretora vira software.
Este passo cria o **cabeçalho** do plano (nome, produto e imposto). As faixas de
rateio vêm no [passo seguinte](09-faixas-rateio.md).

## Pré-requisito

Ter identificado, no [catálogo](07-operadoras.md), o **produto** que o plano vai
cobrir (ex.: `AUTO` da `PORTO SEGURO`). A operadora é **derivada do produto** — você
não a escolhe à mão.

## A tela — Novo plano

**Onde:** menu → **Comissões** → **Planos** → **Novo plano**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 360" role="img"
     aria-label="Formulário Novo plano com nome, tipo de produto e desconto de imposto"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="352" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>
  <line x1="190" y1="38" x2="190" y2="356" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.45">COMISSÕES</text>
  <text x="32" y="92" font-size="12.5" fill="currentColor" fill-opacity="0.7">Operadoras</text>
  <rect x="8" y="102" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="102" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="32" y="120" font-size="12.5" font-weight="700" fill="currentColor">Planos</text>
  <text x="32" y="146" font-size="12.5" fill="currentColor" fill-opacity="0.7">Times</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Planos de comissão</text>
  <rect x="628" y="52" width="112" height="30" rx="7" fill="currentColor" fill-opacity="0.14"/><text x="642" y="72" font-size="18" fill="currentColor" fill-opacity="0.7">+</text><text x="658" y="71" font-size="12.5" font-weight="600" fill="currentColor">Novo plano</text>

  <rect x="210" y="92" width="530" height="248" rx="9" fill="currentColor" fill-opacity="0.03" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="228" y="120" font-size="12" fill="currentColor" fill-opacity="0.7">Nome</text>
  <rect x="228" y="128" width="494" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="242" y="148" font-size="12" fill="currentColor" fill-opacity="0.9">PLANO AUTO PORTO</text>
  <text x="228" y="180" font-size="12" fill="currentColor" fill-opacity="0.7">Produto (do catálogo)</text>
  <rect x="228" y="188" width="240" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="242" y="208" font-size="12" fill="currentColor" fill-opacity="0.9">PORTO SEGURO · AUTO</text>
  <text x="484" y="180" font-size="12" fill="currentColor" fill-opacity="0.7">Desconto de imposto (%)</text>
  <rect x="484" y="188" width="238" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="498" y="208" font-size="12" fill="currentColor" fill-opacity="0.9">10</text>
  <rect x="228" y="290" width="150" height="34" rx="7" fill="currentColor" fill-opacity="0.14"/><text x="303" y="312" font-size="12.5" font-weight="600" fill="currentColor" text-anchor="middle">Criar plano</text>

  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="628" cy="52" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="628" y="56" fill="currentColor">1</text>
    <circle cx="228" cy="188" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="228" y="192" fill="currentColor">2</text>
    <circle cx="484" cy="188" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="484" y="192" fill="currentColor">3</text>
    <circle cx="228" cy="290" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="228" y="294" fill="currentColor">4</text>
  </g>
</svg>
<figcaption>Formulário <strong>Novo plano</strong>.</figcaption>
</figure>

## Passo a passo

| # | Campo | Exemplo | Detalhe |
| --- | --- | --- | --- |
| **1** | Botão **Novo plano** | — | Abre o formulário |
| **2** | **Produto** | `PORTO SEGURO · AUTO` | Escolhido do catálogo; a **operadora é derivada** dele |
| **3** | **Desconto de imposto (%)** | `10` | Sai do **bruto antes** de qualquer divisão |
| **4** | Botão **Criar plano** | — | Salva o cabeçalho; as faixas vêm a seguir |

!!! info "Um plano por produto"
    Cada plano cobre **um** produto. Se você vende `AUTO` e `RESIDENCIAL`, são dois
    planos — cada um com suas próprias faixas de rateio.

!!! note "O imposto explica o 'líquido menor'"
    O desconto de imposto sai do valor **bruto** antes de ratear. Por isso, lá na
    frente, o **líquido** de cada parcela é menor que o bruto: `bruto − imposto =
    líquido`.

!!! success "Checkpoint"
    O plano aparece na lista de **Planos**, ainda **sem faixas**. Abra-o para montar
    o rateio.

→ Próximo: [9 · Montar as faixas e o rateio](09-faixas-rateio.md)
