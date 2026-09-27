# 5 · Criar um time e distribuir papéis

O **time** é o que permite pagar comissão para **grupos de pessoas** por papel
(diretor, gerente, vendedores). Aqui você cria o time e coloca cada membro no seu
papel.

!!! note "Papel de time ≠ perfil de acesso"
    Aqui é **quanto a pessoa ganha** (`director`, `manager`, `seller`). O que ela
    **vê** foi definido no [Passo 4](04-perfil-acesso.md).

## A tela — Times

**Onde:** menu → **Comissões** → **Times**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 400" role="img"
     aria-label="Tela Times com um time e seus membros, e a linha de adicionar membro"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="392" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/>
  <text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>

  <line x1="190" y1="38" x2="190" y2="396" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="70" font-size="13" fill="currentColor" fill-opacity="0.7">Início</text>
  <text x="22" y="98" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.45">COMISSÕES</text>
  <rect x="8" y="108" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="108" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="32" y="126" font-size="12.5" font-weight="700" fill="currentColor">Times</text>
  <text x="32" y="152" font-size="12.5" fill="currentColor" fill-opacity="0.7">Planos</text>
  <text x="32" y="178" font-size="12.5" fill="currentColor" fill-opacity="0.7">Leads</text>
  <text x="32" y="204" font-size="12.5" fill="currentColor" fill-opacity="0.7">Propostas</text>
  <text x="32" y="230" font-size="12.5" fill="currentColor" fill-opacity="0.7">Recebíveis</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Times</text>
  <rect x="628" y="52" width="112" height="30" rx="7" fill="currentColor" fill-opacity="0.14"/>
  <text x="642" y="72" font-size="18" fill="currentColor" fill-opacity="0.7">+</text>
  <text x="658" y="71" font-size="12.5" font-weight="600" fill="currentColor">Novo time</text>

  <!-- card do time -->
  <rect x="210" y="92" width="530" height="288" rx="9" fill="currentColor" fill-opacity="0.02" stroke="currentColor" stroke-opacity="0.2"/>
  <text x="228" y="120" font-size="14" font-weight="700" fill="currentColor">TIME SENNA</text>

  <!-- membros -->
  <g font-size="12.5">
    <text x="228" y="150" fill="currentColor">Renato</text>
    <rect x="600" y="138" width="118" height="20" rx="6" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="659" y="152" fill="currentColor" fill-opacity="0.8" text-anchor="middle">director</text>
    <text x="228" y="178" fill="currentColor">Marina</text>
    <rect x="600" y="166" width="118" height="20" rx="6" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="659" y="180" fill="currentColor" fill-opacity="0.8" text-anchor="middle">manager</text>
    <text x="228" y="206" fill="currentColor">Bruno</text>
    <rect x="600" y="194" width="118" height="20" rx="6" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="659" y="208" fill="currentColor" fill-opacity="0.8" text-anchor="middle">seller</text>
    <text x="228" y="234" fill="currentColor">Carla</text>
    <rect x="600" y="222" width="118" height="20" rx="6" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="659" y="236" fill="currentColor" fill-opacity="0.8" text-anchor="middle">seller</text>
  </g>

  <line x1="228" y1="256" x2="722" y2="256" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="228" y="284" font-size="11" fill="currentColor" fill-opacity="0.6">Adicionar membro</text>
  <rect x="228" y="294" width="240" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="242" y="314" font-size="12" fill="currentColor" fill-opacity="0.5">Escolher membro…</text>
  <rect x="478" y="294" width="120" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="492" y="314" font-size="12" fill="currentColor" fill-opacity="0.5">director</text>
  <rect x="608" y="294" width="110" height="30" rx="7" fill="currentColor" fill-opacity="0.14"/><text x="663" y="314" font-size="12" font-weight="600" fill="currentColor" text-anchor="middle">Adicionar</text>

  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="628" cy="52" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="628" y="56" fill="currentColor">1</text>
    <circle cx="478" cy="294" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="478" y="298" fill="currentColor">2</text>
    <circle cx="608" cy="294" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="608" y="298" fill="currentColor">3</text>
  </g>
</svg>
<figcaption>Tela <strong>Times</strong> com um time, seus membros e a linha de adicionar membro.</figcaption>
</figure>

## Passo a passo

| # | Onde | Ação | Detalhe |
| --- | --- | --- | --- |
| **1** | Botão **Novo time** | Criar o time | Nome (ex.: `TIME SENNA`) + descrição opcional → **Criar time** |
| **2** | **Escolher membro** + **papel** | Selecionar a pessoa e digitar o papel | Papel: `director`, `manager`, `seller`, … |
| **3** | Botão **Adicionar** | Incluir no time | A pessoa aparece na lista com o papel |

Repita o passo 2–3 para cada membro:

| Membro | Papel |
| --- | --- |
| Renato | `director` |
| Marina | `manager` |
| Bruno | `seller` |
| Carla | `seller` |

## Por que o dono e o gerente entram no time?

O plano só sabe pagar **três tipos de destinatário**:

| Destinatário | Quem recebe |
| --- | --- |
| **Vendedor** | o vendedor **daquela venda** (quem fechou) |
| **Corretora (casa)** | fica com a empresa |
| **Papel de time** | todos que têm aquele papel no time |

Para pagar **uma pessoa específica**, ela precisa de um **papel que só ela tem** —
o `director` é o "grupo de um" do dono; o `manager`, o da gerente.

!!! warning "Pegadinha silenciosa"
    Se o plano tem uma linha para `director` e **ninguém** no time tem esse papel,
    aquele pedaço **distribui zero, sem erro**. Monte o time **antes** do plano.

!!! success "Checkpoint"
    O time mostra os 4 membros, com os 4 papéis preenchidos.

→ Próximo: [O plano de comissionamento](06-plano.md)
