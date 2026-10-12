# 12 · Proposta e emissão da apólice

A proposta liga o **lead convertido** a um **plano de comissão**. Quando o cliente
aceita, você **Aceita** a proposta — e o sistema gera a **apólice** e as **parcelas
de comissão**. É o momento em que a venda vira contrato.

## A tela — Nova proposta

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
  <rect x="228" y="126" width="494" height="28" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="242" y="145" font-size="12" fill="currentColor" fill-opacity="0.9">PLANO AUTO PORTO</text>
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
    <circle cx="228" cy="228" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="228" y="232" fill="currentColor">3</text>
    <circle cx="368" cy="228" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="368" y="232" fill="currentColor">4</text>
  </g>
</svg>
<figcaption>Formulário <strong>Nova proposta</strong> e os botões <strong>Enviar</strong>/<strong>Aceitar</strong>.</figcaption>
</figure>

## Passo a passo

| # | Onde | Ação | Detalhe |
| --- | --- | --- | --- |
| **1** | **Nova proposta** | Escolher o **lead convertido** e o **plano** | Sem lead convertido, não há o que escolher |
| **2** | **Prêmio / Parcelas** | ex.: `1200,00` em `12`x | Prêmio é decimal (4 casas); parcelas definem quantas comissões nascem |
| **3** | Botão **Enviar** | Marcar como **enviada** ao cliente | Estado intermediário, ainda sem apólice |
| **4** | Botão **Aceitar** | Fechar a venda | Gera a **apólice** e as parcelas — **irreversível** |

## Os estados da proposta

| Estado | O que significa |
| --- | --- |
| **rascunho** | Criada, ainda não enviada |
| **enviada** | Mandada ao cliente, aguardando resposta |
| **aceita** | Cliente fechou → nasce a **apólice** |
| **cancelada** | Não fechou |

## O que o aceite congela

Ao aceitar, o sistema tira um **snapshot**: operadora, produto e as faixas do plano
ficam **gravados na apólice**. Mexer no plano depois **não** altera apólices já
emitidas — cada venda carrega a regra que valia no dia.

!!! danger "Aceitar não tem volta"
    No aceite, o sistema gera a **apólice**, cria as **12 parcelas** (bruto, imposto,
    líquido) e **congela** o plano. Confira o prêmio e o plano **antes** de
    confirmar.

!!! success "Checkpoint"
    A apólice aparece e suas parcelas estão como **pendentes**, prontas para
    confirmação.

→ Próximo: [13 · Confirmar as comissões](13-confirmar-comissoes.md)
