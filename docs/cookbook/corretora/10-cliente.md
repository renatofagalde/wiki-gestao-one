# 10 · Cadastrar o cliente

A venda começa pela **pessoa**: o cliente precisa existir no cadastro antes de
virar um lead. Esta tela é o cadastro de **Pessoas** (clientes) da corretora.

## A tela — Pessoas

**Onde:** menu → **Pessoas**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 290" role="img"
     aria-label="Tela Pessoas com busca por aproximação e lista de pessoas"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="282" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>
  <line x1="190" y1="38" x2="190" y2="286" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="13" fill="currentColor" fill-opacity="0.7">Visão geral</text>
  <rect x="8" y="78" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="78" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="22" y="96" font-size="12.5" font-weight="700" fill="currentColor">Pessoas</text>
  <text x="22" y="122" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.45">COMISSÕES</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Pessoas</text>
  <rect x="628" y="52" width="112" height="30" rx="7" fill="currentColor" fill-opacity="0.14"/><text x="684" y="72" font-size="12.5" font-weight="600" fill="currentColor" text-anchor="middle">Adicionar</text>
  <rect x="210" y="92" width="530" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <circle cx="228" cy="107" r="6" fill="none" stroke="currentColor" stroke-opacity="0.5"/><line x1="232" y1="111" x2="236" y2="115" stroke="currentColor" stroke-opacity="0.5"/>
  <text x="246" y="111" font-size="12" fill="currentColor" fill-opacity="0.45">Buscar por nome ou documento...</text>
  <rect x="210" y="132" width="530" height="38" rx="8" fill="none" stroke="currentColor" stroke-opacity="0.2"/><text x="228" y="155" font-size="12.5" fill="currentColor">JOÃO DA SILVA SANTOS · 123.456.789-00</text>
  <rect x="210" y="178" width="530" height="38" rx="8" fill="none" stroke="currentColor" stroke-opacity="0.2"/><text x="228" y="201" font-size="12.5" fill="currentColor">MARIA OLIVEIRA · 987.654.321-00</text>
  <text x="210" y="250" font-size="11.5" fill="currentColor" fill-opacity="0.6">Busca por aproximação: 3+ letras acham por semelhança (acento/typo não atrapalham).</text>
  <g font-size="12" font-weight="700" text-anchor="middle"><circle cx="628" cy="52" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="628" y="56" fill="currentColor">1</text><circle cx="210" cy="92" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="210" y="96" fill="currentColor">2</text></g>
</svg>
<figcaption>Tela <strong>Pessoas</strong>: cadastro e busca por aproximação.</figcaption>
</figure>

## Passo a passo

| # | Onde | Ação | Regra |
| --- | --- | --- | --- |
| **1** | Botão **Adicionar** | Cadastrar a pessoa | Nome e **CPF/CNPJ** (o dígito verificador é validado) |
| **2** | Campo de **busca** | Encontrar alguém já cadastrado | **Aproximação**: `joao silva` acha `JOÃO DA SILVA SANTOS` |

- O nome é gravado em **maiúsculo**.
- **CPF** (pessoa física) ou **CNPJ** (jurídica) são validados — documento inválido
  é recusado antes de salvar.
- A **busca por aproximação** aceita 3+ letras e ignora acento/typo — você não
  precisa digitar o nome exato.

!!! info "Por que cadastrar a pessoa antes?"
    O lead do próximo passo liga **uma pessoa** a **um produto**. Ele só enxerga
    quem **já existe** aqui — por isso o cliente vem primeiro.

!!! success "Checkpoint"
    O cliente aparece na lista de **Pessoas** e é encontrável pela busca.

→ Próximo: [11 · Abrir e converter o lead](11-lead.md)
