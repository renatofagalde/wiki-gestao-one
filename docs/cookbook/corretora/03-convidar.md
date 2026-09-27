# 3 · Sou dono — convidar a equipe

Com a corretora criada, o primeiro passo é **colocar as pessoas dentro dela**. A
equipe precisa existir como **usuário da corretora** antes de qualquer coisa — sem
isso, ninguém entra num time nem recebe comissão.

No exemplo: convide **Marina**, **Bruno** e **Carla**.

## Pré-requisitos

- Você é **dono/administrador** da corretora (perfil com permissão de convidar).
- A pessoa convidada **já tem conta** no sistema, com um e-mail conhecido.

!!! warning "Convidar só funciona para quem já tem conta"
    O convite é amarrado a uma **conta existente**. Se o e-mail não tem conta, o
    sistema **não avisa** (resposta neutra, por segurança). Peça para a pessoa
    [criar a conta](01-criar-conta.md) antes, e confirme o e-mail exato.

## A tela — Usuários

**Onde:** menu lateral → **Usuários** → botão **Convidar**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 460" role="img"
     aria-label="Tela Usuários com o formulário de convite aberto e três etapas numeradas"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="452" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/>
  <text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>

  <line x1="190" y1="38" x2="190" y2="456" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="74"  font-size="13" fill="currentColor" fill-opacity="0.7">Início</text>
  <text x="22" y="106" font-size="13" fill="currentColor" fill-opacity="0.7">Clientes</text>
  <rect x="8" y="120" width="176" height="28" rx="6" fill="currentColor" fill-opacity="0.08"/>
  <rect x="8" y="120" width="3" height="28" fill="currentColor" fill-opacity="0.55"/>
  <text x="22" y="139" font-size="13" font-weight="700" fill="currentColor">Usuários</text>
  <text x="22" y="174" font-size="13" fill="currentColor" fill-opacity="0.7">Comissões</text>
  <text x="22" y="206" font-size="13" fill="currentColor" fill-opacity="0.7">Conta corrente</text>
  <text x="22" y="238" font-size="13" fill="currentColor" fill-opacity="0.7">Configurações</text>

  <text x="210" y="72" font-size="17" font-weight="700" fill="currentColor">Usuários</text>
  <text x="210" y="92" font-size="11.5" fill="currentColor" fill-opacity="0.55">Quem tem acesso a Corretora Exemplo.</text>
  <!-- botão Convidar -->
  <rect x="612" y="58" width="126" height="32" rx="7" fill="currentColor" fill-opacity="0.14"/>
  <rect x="624" y="67" width="15" height="11" rx="1" fill="none" stroke="currentColor" stroke-opacity="0.7"/>
  <polyline points="624,68 631.5,74 639,68" fill="none" stroke="currentColor" stroke-opacity="0.7"/>
  <text x="648" y="79" font-size="12.5" font-weight="600" fill="currentColor">Convidar</text>

  <!-- painel -->
  <rect x="210" y="118" width="530" height="250" rx="9" fill="currentColor" fill-opacity="0.03" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="230" y="150" font-size="14" font-weight="700" fill="currentColor">Convidar usuário</text>
  <text x="230" y="182" font-size="12" fill="currentColor" fill-opacity="0.7">E-mail do convidado</text>
  <rect x="230" y="192" width="410" height="36" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="244" y="215" font-size="12.5" fill="currentColor" fill-opacity="0.9">marina.vendas@corretora.com.br</text>
  <text x="230" y="248" font-size="11" fill="currentColor" fill-opacity="0.55">Use o e-mail exato da conta da pessoa — pontos contam.</text>
  <rect x="230" y="268" width="150" height="36" rx="7" fill="currentColor" fill-opacity="0.14"/>
  <text x="305" y="291" font-size="12.5" font-weight="600" fill="currentColor" text-anchor="middle">Enviar convite</text>
  <rect x="392" y="268" width="88" height="36" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="436" y="291" font-size="12.5" fill="currentColor" fill-opacity="0.65" text-anchor="middle">Fechar</text>

  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="612" cy="58" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/>
    <text x="612" y="62" fill="currentColor">1</text>
    <circle cx="640" cy="210" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/>
    <text x="640" y="214" fill="currentColor">2</text>
    <circle cx="230" cy="268" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/>
    <text x="230" y="272" fill="currentColor">3</text>
  </g>
</svg>
<figcaption>Tela <strong>Usuários</strong> com o formulário de convite aberto.</figcaption>
</figure>

## Passo a passo

| # | Onde clicar | O que preencher | Regra |
| --- | --- | --- | --- |
| **1** | Botão **Convidar** (topo direito) | — | Abre o formulário |
| **2** | Campo **E-mail do convidado** | E-mail **exato** da conta. Ex.: `marina.vendas@corretora.com.br` | Precisa ter `@` e domínio válido |
| **3** | Botão **Enviar convite** | — | Fica **desabilitado** até o e-mail ser válido |

Repita para cada pessoa (Marina, Bruno, Carla). Depois, feche o formulário no
botão **Fechar**.

## O resultado

Cada convidado passa a aparecer na lista de **Usuários** com o status
**convidado**:

| Estado na lista | Significado |
| --- | --- |
| **convidado** | Convite enviado, aguardando a pessoa aceitar |
| **ativo** | A pessoa [aceitou](02-esperar-convite.md) — já pode entrar num time e receber perfil |

!!! danger "O erro nº 1 — e-mail com typo"
    Convidar um e-mail **sem conta não retorna erro** na tela (é anti-enumeração).
    Se a pessoa diz que o convite "não apareceu", quase sempre é a grafia —
    inclusive **pontos** (`joao.silva@` ≠ `joaosilva@` para o sistema). Confirme o
    endereço e reenvie.

!!! success "Checkpoint"
    As três pessoas aparecem em **Usuários**. Antes de montar o time, confirme que
    elas **aceitaram** (status **ativo**) — os próximos passos dependem disso.

→ Próximo: [4 · Atribuir perfil de acesso](04-perfil-acesso.md)
