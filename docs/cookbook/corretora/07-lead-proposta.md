# 7 · Lead vira proposta (e nasce a apólice)

A venda percorre três telas: **Clientes** (a pessoa), **Leads** (a oportunidade) e
**Propostas** (que, ao ser aceita, vira **apólice** e gera as comissões).

## 7.1 · Cliente (Clientes)

**Onde:** menu → **Clientes**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 290" role="img"
     aria-label="Tela Clientes com busca por aproximação e lista de pessoas"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="282" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>
  <line x1="190" y1="38" x2="190" y2="286" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="13" fill="currentColor" fill-opacity="0.7">Início</text>
  <rect x="8" y="78" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="78" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="22" y="96" font-size="12.5" font-weight="700" fill="currentColor">Clientes</text>
  <text x="22" y="122" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.45">COMISSÕES</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Pessoas</text>
  <rect x="628" y="52" width="112" height="30" rx="7" fill="currentColor" fill-opacity="0.14"/><text x="684" y="72" font-size="12.5" font-weight="600" fill="currentColor" text-anchor="middle">Adicionar</text>
  <rect x="210" y="92" width="530" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <circle cx="228" cy="107" r="6" fill="none" stroke="currentColor" stroke-opacity="0.5"/><line x1="232" y1="111" x2="236" y2="115" stroke="currentColor" stroke-opacity="0.5"/>
  <text x="246" y="111" font-size="12" fill="currentColor" fill-opacity="0.45">Buscar por nome ou documento...</text>
  <rect x="210" y="132" width="530" height="38" rx="8" fill="none" stroke="currentColor" stroke-opacity="0.2"/><text x="228" y="155" font-size="12.5" fill="currentColor">JOÃO DA SILVA SANTOS · 123.456.789-00</text>
  <rect x="210" y="178" width="530" height="38" rx="8" fill="none" stroke="currentColor" stroke-opacity="0.2"/><text x="228" y="201" font-size="12.5" fill="currentColor">MARIA OLIVEIRA · 987.654.321-00</text>
  <text x="210" y="250" font-size="11.5" fill="currentColor" fill-opacity="0.6">Busca por aproximação: 3+ letras acham por semelhança (acento/typo não atrapalham).</text>
  <g font-size="12" font-weight="700" text-anchor="middle"><circle cx="210" cy="92" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="210" y="96" fill="currentColor">1</text></g>
</svg>
<figcaption>Tela <strong>Pessoas</strong>: cadastro e busca por aproximação.</figcaption>
</figure>

Cadastre com nome e CPF/CNPJ (dígito verificador validado). A **busca por
aproximação** acha por semelhança — `joao silva` encontra `JOÃO DA SILVA SANTOS`.

## 7.2 · Lead (a oportunidade)

**Onde:** menu → **Comissões** → **Leads**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 280" role="img"
     aria-label="Tela Leads com um lead e o botão Converter"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="272" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>
  <line x1="190" y1="38" x2="190" y2="276" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.45">COMISSÕES</text>
  <rect x="8" y="76" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="76" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="32" y="94" font-size="12.5" font-weight="700" fill="currentColor">Leads</text>
  <text x="32" y="120" font-size="12.5" fill="currentColor" fill-opacity="0.7">Propostas</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Leads</text>
  <rect x="628" y="52" width="112" height="30" rx="7" fill="currentColor" fill-opacity="0.14"/><text x="642" y="72" font-size="18" fill="currentColor" fill-opacity="0.7">+</text><text x="658" y="71" font-size="12.5" font-weight="600" fill="currentColor">Novo lead</text>
  <rect x="210" y="98" width="530" height="66" rx="8" fill="none" stroke="currentColor" stroke-opacity="0.2"/>
  <text x="228" y="124" font-size="13" font-weight="700" fill="currentColor">JOÃO DA SILVA SANTOS · auto</text>
  <text x="228" y="144" font-size="11.5" fill="currentColor" fill-opacity="0.6">Vendedor: Bruno · em negociação</text>
  <rect x="628" y="116" width="94" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="675" y="136" font-size="12" fill="currentColor" fill-opacity="0.8" text-anchor="middle">Converter</text>
  <text x="210" y="196" font-size="11.5" fill="currentColor" fill-opacity="0.6">Converter libera o lead para virar proposta. É irreversível, mas não cria nada ainda.</text>
  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="628" cy="52" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="628" y="56" fill="currentColor">1</text>
    <circle cx="628" cy="116" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="628" y="120" fill="currentColor">2</text>
  </g>
</svg>
<figcaption>Tela <strong>Leads</strong> com o botão <strong>Converter</strong>.</figcaption>
</figure>

O lead liga **uma pessoa** a **um produto**, com o vendedor responsável (Bruno).
Ao fechar, clique **Converter**.

## 7.3 · Proposta (e a apólice)

**Onde:** menu → **Comissões** → **Propostas** → **Nova proposta**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 360" role="img"
     aria-label="Formulário Nova proposta e os botões Enviar e Aceitar"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="352" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>
  <line x1="190" y1="38" x2="190" y2="356" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="66" font-size="10.5" font-weight="700" fill="currentColor" fill-opacity="0.45">COMISSÕES</text>
  <text x="32" y="92" font-size="12.5" fill="currentColor" fill-opacity="0.7">Leads</text>
  <rect x="8" y="102" width="176" height="26" rx="6" fill="currentColor" fill-opacity="0.08"/><rect x="8" y="102" width="3" height="26" fill="currentColor" fill-opacity="0.55"/>
  <text x="32" y="120" font-size="12.5" font-weight="700" fill="currentColor">Propostas</text>

  <text x="210" y="66" font-size="17" font-weight="700" fill="currentColor">Propostas</text>
  <rect x="620" y="52" width="120" height="30" rx="7" fill="currentColor" fill-opacity="0.14"/><text x="634" y="72" font-size="18" fill="currentColor" fill-opacity="0.7">+</text><text x="650" y="71" font-size="12.5" font-weight="600" fill="currentColor">Nova proposta</text>

  <rect x="210" y="92" width="530" height="180" rx="9" fill="currentColor" fill-opacity="0.03" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="228" y="118" font-size="12" fill="currentColor" fill-opacity="0.7">Plano de comissão</text>
  <rect x="228" y="126" width="494" height="28" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="242" y="145" font-size="12" fill="currentColor" fill-opacity="0.9">PLANO AUTO PADRÃO</text>
  <text x="228" y="174" font-size="12" fill="currentColor" fill-opacity="0.7">Prêmio mensal (R$)</text>
  <rect x="228" y="182" width="240" height="28" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="242" y="201" font-size="12" fill="currentColor" fill-opacity="0.9">1200,00</text>
  <text x="484" y="174" font-size="12" fill="currentColor" fill-opacity="0.7">Parcelas</text>
  <rect x="484" y="182" width="238" height="28" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="498" y="201" font-size="12" fill="currentColor" fill-opacity="0.9">12</text>
  <rect x="228" y="228" width="130" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="293" y="248" font-size="12" fill="currentColor" fill-opacity="0.75" text-anchor="middle">Enviar</text>
  <rect x="368" y="228" width="130" height="30" rx="7" fill="currentColor" fill-opacity="0.14"/><text x="433" y="248" font-size="12" font-weight="600" fill="currentColor" text-anchor="middle">Aceitar</text>

  <text x="210" y="300" font-size="11.5" fill="currentColor" fill-opacity="0.6">Aceitar gera a apólice + 12 parcelas de comissão e congela o plano. Não tem volta.</text>
  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="620" cy="52" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="620" y="56" fill="currentColor">1</text>
    <circle cx="228" cy="182" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="228" y="186" fill="currentColor">2</text>
    <circle cx="368" cy="228" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="368" y="232" fill="currentColor">3</text>
  </g>
</svg>
<figcaption>Formulário <strong>Nova proposta</strong> e os botões <strong>Enviar</strong>/<strong>Aceitar</strong>.</figcaption>
</figure>

| # | Onde | Ação |
| --- | --- | --- |
| **1** | **Nova proposta** | Escolha o **lead convertido** e o **plano** |
| **2** | **Prêmio / Parcelas** | ex.: `1200,00` em `12`x |
| **3** | **Enviar** → **Aceitar** | Aceitar gera a **apólice** |

!!! danger "Aceitar não tem volta"
    No aceite o sistema gera a **apólice**, cria as **12 parcelas** (bruto, imposto,
    líquido) e **congela** o plano. Confira antes.

!!! success "Checkpoint"
    A apólice aparece e as parcelas estão como **pendentes**.

→ Próximo: [Confirmar e ver o dinheiro chegar](08-confirmar-resultado.md)
