# 9 · Montar as faixas e o rateio

Com o [plano criado](08-criar-plano.md), abra-o para montar o **rateio**. Cada
**faixa** cobre um intervalo de parcelas e tem **linhas** que precisam somar
**100%**. É aqui que você escreve a regra "quem ganha quanto, e em qual parcela".

## A tela — Detalhe do plano

**Onde:** menu → **Comissões** → **Planos** → abrir o plano.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 400" role="img"
     aria-label="Detalhe do plano com uma faixa, linhas somando cem por cento e simulador"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="392" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/><circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/><text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>

  <text x="28" y="72" font-size="17" font-weight="700" fill="currentColor">PLANO AUTO PORTO</text>

  <!-- faixa 2 -->
  <rect x="28" y="92" width="700" height="172" rx="9" fill="currentColor" fill-opacity="0.02" stroke="currentColor" stroke-opacity="0.2"/>
  <text x="46" y="118" font-size="13" font-weight="700" fill="currentColor">Faixa · parcela 2 até 2</text>
  <line x1="46" y1="128" x2="710" y2="128" stroke="currentColor" stroke-opacity="0.12"/>
  <g font-size="12.5">
    <text x="46" y="150" fill="currentColor">Vendedor (da venda)</text>
    <text x="690" y="150" fill="currentColor" text-anchor="end">50%</text>
    <text x="46" y="174" fill="currentColor">Papel de time → TIME SENNA / director</text>
    <text x="690" y="174" fill="currentColor" text-anchor="end">15%</text>
    <text x="46" y="198" fill="currentColor">Papel de time → TIME SENNA / manager</text>
    <text x="690" y="198" fill="currentColor" text-anchor="end">10%</text>
    <text x="46" y="222" fill="currentColor">Corretora (casa)</text>
    <text x="690" y="222" fill="currentColor" text-anchor="end">25%</text>
  </g>
  <line x1="46" y1="234" x2="710" y2="234" stroke="currentColor" stroke-opacity="0.12"/>
  <text x="46" y="254" font-size="12.5" font-weight="700" fill="currentColor">Total</text>
  <rect x="646" y="241" width="64" height="20" rx="10" fill="currentColor" fill-opacity="0.14"/><text x="678" y="255" font-size="12" font-weight="700" fill="currentColor" text-anchor="middle">100% ✓</text>

  <!-- simulador -->
  <rect x="28" y="280" width="700" height="100" rx="9" fill="none" stroke="currentColor" stroke-opacity="0.2"/>
  <text x="46" y="306" font-size="13" font-weight="700" fill="currentColor">Simulador</text>
  <text x="46" y="330" font-size="11.5" fill="currentColor" fill-opacity="0.7">Prêmio de exemplo</text>
  <rect x="46" y="338" width="160" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/><text x="60" y="358" font-size="12" fill="currentColor" fill-opacity="0.9">1500,00</text>
  <text x="230" y="358" font-size="12" fill="currentColor" fill-opacity="0.6">→ veja em reais quanto cada linha rende antes de vender</text>

  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="700" cy="150" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="700" y="154" fill="currentColor">1</text>
    <circle cx="646" cy="251" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="646" y="255" fill="currentColor">2</text>
    <circle cx="46" cy="338" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="46" y="342" fill="currentColor">3</text>
  </g>
</svg>
<figcaption>Uma <strong>faixa</strong> com linhas somando 100% e o <strong>simulador</strong>.</figcaption>
</figure>

## A matriz do exemplo

Três faixas, cobrindo da 1ª parcela ao vitalício:

| Faixa | Parcelas | Vendedor | Diretor | Gerente | Corretora |
| --- | --- | ---: | ---: | ---: | ---: |
| **P1** | 1 | 100% | — | — | — |
| **P2** | 2 | 50% | 15% | 10% | 25% |
| **P3+** | 3 em diante (**vitalício**) | 3% | 25% | 25% | 47% |

- **P1** paga **só o vendedor** — o incentivo de fechar a venda.
- **P2** começa a dividir com o time e a casa.
- **P3+** é o **vitalício**: enquanto o cliente pagar, o rateio continua, agora
  pesando mais para diretor, gerente e corretora.

## Passo a passo (por faixa)

| # | Onde | Ação |
| --- | --- | --- |
| **1** | Linha da faixa | Diga de qual parcela até qual ela vale (ou marque **vitalício** para valer daí em diante) e some os destinatários (**vendedor**, **corretora** ou **papel de time**) |
| **2** | Selo **Total** | A faixa **só salva quando bate 100%** |
| **3** | **Simulador** | Informe um prêmio (ex.: `1500,00`) e confira, em reais, quanto cada linha rende |

Repita para as três faixas (parcela 1, parcela 2, da 3ª em diante).

!!! warning "A linha por papel de time pode distribuir zero"
    Se a faixa tem uma linha para `director` e **ninguém no time** tem esse papel,
    aquele pedaço **distribui zero, sem erro** — o sistema só avisa com um alerta na
    linha. Por isso o [time](06-time.md) vem antes do plano.

!!! danger "Plano é quase imutável"
    Não dá para editar/apagar uma linha isolada: remove-se a **faixa inteira**. Se
    já houver **apólice emitida**, a remoção é **bloqueada** (mexer nas faixas
    mudaria comissões já pendentes) — crie um plano novo para as próximas vendas.

!!! success "Checkpoint"
    As três faixas com **100%** cada, e o simulador batendo com o esperado.

→ Próximo: [10 · Cadastrar o cliente](10-cliente.md)
