# 4 · Atribuir perfil de acesso

Aceitar o convite torna a pessoa **membro** da corretora — mas ainda **sem telas**.
Quem decide o que cada um vê e faz é o **perfil de acesso**. Aqui você coloca a
pessoa no "grupo de permissão" certo.

!!! note "Dois papéis diferentes — não confunda"
    - **Perfil de acesso** (`admin`, `gerente`, `vendedor`, …) = **o que a pessoa
      vê e faz** nas telas. É o desta página.
    - **Papel de time** (`director`, `manager`, `seller`) = **quanto ela ganha** no
      rateio. É o do [Passo 5](05-time.md).

## Pré-requisito

A pessoa precisa ter **aceitado o convite** (status **ativo** em
[Usuários](03-convidar.md)). Quem está só **convidado** ainda não pode receber
perfil.

## Os perfis disponíveis

Os perfis vêm do servidor (RBAC) e têm nomes em português:

| Perfil (`slug`) | Para quem | Enxerga, em geral |
| --- | --- | --- |
| `admin` | Dono / administrador | Tudo |
| `access_manager` | Gestor de acesso | Gestão de usuários e perfis |
| `gerente` | Gerência | Comercial, planos, recebíveis |
| `financeiro` | Financeiro | Comissões, conta corrente |
| `operacional` | Operação | Cadastros e apoio |
| `vendedor` | Vendedor | Seus leads, propostas e recebíveis |

## A tela — Usuários do perfil

**Onde:** menu → **Perfis** → abrir um perfil (ex.: **Vendedor**) → **Usuários do
perfil**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 470" role="img"
     aria-label="Tela Usuários do perfil com listas Com acesso e Sem acesso e botões de conceder"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="462" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/>
  <text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>

  <line x1="190" y1="38" x2="190" y2="466" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="74"  font-size="13" fill="currentColor" fill-opacity="0.7">Início</text>
  <text x="22" y="106" font-size="13" fill="currentColor" fill-opacity="0.7">Usuários</text>
  <rect x="8" y="120" width="176" height="28" rx="6" fill="currentColor" fill-opacity="0.08"/>
  <rect x="8" y="120" width="3" height="28" fill="currentColor" fill-opacity="0.55"/>
  <text x="22" y="139" font-size="13" font-weight="700" fill="currentColor">Perfis</text>
  <text x="22" y="174" font-size="13" fill="currentColor" fill-opacity="0.7">Comissões</text>
  <text x="22" y="206" font-size="13" fill="currentColor" fill-opacity="0.7">Configurações</text>

  <!-- conteúdo -->
  <text x="210" y="64" font-size="11" fill="currentColor" fill-opacity="0.5">‹ Voltar aos perfis</text>
  <text x="210" y="90" font-size="17" font-weight="700" fill="currentColor">Usuários do perfil</text>
  <text x="210" y="110" font-size="11.5" fill="currentColor" fill-opacity="0.55">Quem tem o perfil Vendedor em Corretora Exemplo.</text>

  <!-- unidade -->
  <text x="210" y="138" font-size="11.5" fill="currentColor" fill-opacity="0.7">Unidade</text>
  <rect x="210" y="146" width="300" height="32" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="224" y="167" font-size="12.5" fill="currentColor" fill-opacity="0.9">Matriz — SP</text>
  <path d="M494 158 l6 6 l6 -6" fill="none" stroke="currentColor" stroke-opacity="0.5"/>
  <text x="210" y="194" font-size="10.5" fill="currentColor" fill-opacity="0.5">O acesso é concedido nesta unidade.</text>

  <!-- busca -->
  <rect x="210" y="206" width="530" height="32" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="224" y="227" font-size="12.5" fill="currentColor" fill-opacity="0.45">Nome ou e-mail</text>

  <!-- com acesso -->
  <text x="210" y="264" font-size="11" font-weight="700" fill="currentColor" fill-opacity="0.6">COM ACESSO (1)</text>
  <rect x="210" y="272" width="530" height="40" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.18"/>
  <circle cx="232" cy="292" r="11" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <text x="232" y="296" font-size="11" font-weight="700" fill="currentColor" fill-opacity="0.7" text-anchor="middle">B</text>
  <text x="252" y="296" font-size="12.5" fill="currentColor">Bruno Vendas · bruno@corretora.com.br</text>
  <rect x="636" y="279" width="90" height="26" rx="6" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="681" y="296" font-size="11.5" fill="currentColor" fill-opacity="0.65" text-anchor="middle">Remover</text>

  <!-- sem acesso -->
  <text x="210" y="346" font-size="11" font-weight="700" fill="currentColor" fill-opacity="0.6">SEM ACESSO (2)</text>
  <rect x="210" y="354" width="530" height="40" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.18"/>
  <circle cx="232" cy="374" r="11" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <text x="232" y="378" font-size="11" font-weight="700" fill="currentColor" fill-opacity="0.7" text-anchor="middle">C</text>
  <text x="252" y="378" font-size="12.5" fill="currentColor">Carla Vendas · carla@corretora.com.br</text>
  <rect x="636" y="361" width="90" height="26" rx="6" fill="currentColor" fill-opacity="0.14"/>
  <text x="681" y="378" font-size="11.5" font-weight="600" fill="currentColor" text-anchor="middle">Conceder</text>

  <rect x="210" y="404" width="530" height="40" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.18"/>
  <circle cx="232" cy="424" r="11" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <text x="232" y="428" font-size="11" font-weight="700" fill="currentColor" fill-opacity="0.7" text-anchor="middle">M</text>
  <text x="252" y="428" font-size="12.5" fill="currentColor">Marina Gerência · marina.vendas@corretora.com.br</text>
  <rect x="636" y="411" width="90" height="26" rx="6" fill="currentColor" fill-opacity="0.14"/>
  <text x="681" y="428" font-size="11.5" font-weight="600" fill="currentColor" text-anchor="middle">Conceder</text>

  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="210" cy="146" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/>
    <text x="210" y="150" fill="currentColor">1</text>
    <circle cx="210" cy="346" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/>
    <text x="210" y="350" fill="currentColor">2</text>
    <circle cx="636" cy="361" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/>
    <text x="636" y="365" fill="currentColor">3</text>
  </g>
</svg>
<figcaption>Tela <strong>Usuários do perfil</strong> — duas listas e um botão por linha.</figcaption>
</figure>

## Passo a passo

| # | Onde | Ação | Detalhe |
| --- | --- | --- | --- |
| **1** | Seletor **Unidade** | Escolher a unidade | O acesso é **por unidade** — a pessoa pode ter o perfil numa filial e não em outra |
| **2** | Lista **Sem acesso** | Localizar a pessoa | Use a **Busca** (nome ou e-mail) se a lista for grande |
| **3** | Botão **Conceder** | Conceder o perfil | A pessoa passa para **Com acesso** na hora |

Para **tirar** o acesso, use **Remover** na lista "Com acesso" (some da lista de
quem enxerga aquele perfil naquela unidade).

!!! info "Por que o seletor de unidade importa"
    O vínculo mora em `user_profile` e é **por unidade**, não por empresa. Sem
    prestar atenção na unidade, dá para conceder acesso no **site errado** sem
    perceber. O padrão é a unidade ativa no topo.

## O resultado

- A pessoa passa a **ver o menu** correspondente ao perfil (um `vendedor`, por
  exemplo, passa a ver Leads, Propostas e Seus recebíveis — e **não** vê planos
  nem conta corrente da corretora).
- O que ela pode fazer em cada tela (criar, editar, excluir) também vem do RBAC;
  botões sem permissão aparecem **desabilitados**.

!!! tip "Faça o combo certo por pessoa"
    No exemplo: Marina recebe o perfil **`gerente`**; Bruno e Carla, **`vendedor`**.
    Isso é **acesso** — o quanto cada um ganha vem depois, no [time](05-time.md).

!!! success "Checkpoint"
    Cada pessoa aparece em **Com acesso** no perfil certo, na unidade certa.

→ Próximo: [5 · Criar um time e distribuir papéis](05-time.md)
