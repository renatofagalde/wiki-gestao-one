# 2 · Sou usuário — aceitar o convite

Se você **não é o dono**, seu papel é aceitar o convite da corretora. Você não
cria nada — quem monta a corretora é o administrador. Esta página cobre **todos**
os passos, do login à corretora aparecendo no seu seletor.

## Pré-requisitos

- Ter uma [conta criada](01-criar-conta.md) com o **mesmo e-mail** que o
  administrador usou no convite.
- O administrador já ter [enviado o convite](03-convidar.md).

!!! info "Você não depende do e-mail de notificação"
    Mesmo que o e-mail de aviso não chegue, o convite aparece dentro do sistema,
    na tela **Meus convites**. É de lá que se aceita.

## A tela — Meus convites

**Onde:** menu lateral → **Meus convites**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 360" role="img"
     aria-label="Tela Meus convites com um convite pendente e os botões Aceitar e Recusar"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <!-- janela -->
  <rect x="4" y="4" width="752" height="352" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/>
  <text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one</text>

  <!-- sidebar -->
  <line x1="190" y1="38" x2="190" y2="356" stroke="currentColor" stroke-opacity="0.15"/>
  <text x="22" y="74" font-size="13" fill="currentColor" fill-opacity="0.7">Início</text>
  <rect x="8" y="86" width="176" height="28" rx="6" fill="currentColor" fill-opacity="0.08"/>
  <rect x="8" y="86" width="3" height="28" fill="currentColor" fill-opacity="0.55"/>
  <text x="22" y="105" font-size="13" font-weight="700" fill="currentColor">Meus convites</text>
  <text x="22" y="140" font-size="13" fill="currentColor" fill-opacity="0.7">Meu extrato</text>
  <text x="22" y="172" font-size="13" fill="currentColor" fill-opacity="0.7">Configurações</text>

  <!-- conteúdo -->
  <text x="210" y="72" font-size="17" font-weight="700" fill="currentColor">Meus convites</text>
  <text x="210" y="92" font-size="11.5" fill="currentColor" fill-opacity="0.55">Convites de corretoras para você participar.</text>

  <!-- card do convite -->
  <rect x="210" y="112" width="530" height="84" rx="9" fill="none" stroke="currentColor" stroke-opacity="0.2"/>
  <!-- ícone envelope (traços) -->
  <rect x="228" y="132" width="40" height="40" rx="8" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <rect x="236" y="143" width="24" height="17" rx="2" fill="none" stroke="currentColor" stroke-opacity="0.55"/>
  <polyline points="236,145 248,154 260,145" fill="none" stroke="currentColor" stroke-opacity="0.55"/>
  <text x="286" y="146" font-size="13.5" font-weight="700" fill="currentColor">Corretora Exemplo</text>
  <text x="286" y="167" font-size="11.5" fill="currentColor" fill-opacity="0.55">Convite pendente · convidado por Renato</text>
  <!-- botão Aceitar (preenchido leve) -->
  <rect x="548" y="136" width="88" height="32" rx="7" fill="currentColor" fill-opacity="0.14"/>
  <text x="592" y="157" font-size="12.5" font-weight="600" fill="currentColor" text-anchor="middle">Aceitar</text>
  <!-- botão Recusar (contorno) -->
  <rect x="644" y="136" width="82" height="32" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="685" y="157" font-size="12.5" fill="currentColor" fill-opacity="0.65" text-anchor="middle">Recusar</text>

  <!-- badges -->
  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="14" cy="100" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/>
    <text x="14" y="104" fill="currentColor">1</text>
    <circle cx="210" cy="112" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/>
    <text x="210" y="116" fill="currentColor">2</text>
    <circle cx="548" cy="136" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/>
    <text x="548" y="140" fill="currentColor">3</text>
  </g>
</svg>
<figcaption>Tela <strong>Meus convites</strong> com um convite pendente.</figcaption>
</figure>

## Passo a passo

| # | Onde | Ação | O que observar |
| --- | --- | --- | --- |
| **1** | Menu **Meus convites** | Abrir a tela | Se não houver nenhum, ver [Nenhum convite?](#nenhum-convite) |
| **2** | Card do convite | Conferir **corretora** e **quem convidou** | O status deve estar **Convite pendente** |
| **3** | Botão **Aceitar** | Confirmar | A corretora entra no seu seletor na hora |

### Estados de um convite

| Status | O que significa | O que aparece |
| --- | --- | --- |
| **Convite pendente** | Aguardando sua resposta | Botões **Aceitar** e **Recusar** |
| **Aceito** | Você já entrou | Selo "Aceito"; a corretora está no seletor |
| **Recusado** | Você declinou | Selo "Recusado"; um novo convite pode ser enviado depois |
| **Removido** | O acesso foi revogado pela corretora | Selo "Removido" |

## O que acontece ao aceitar

1. A corretora entra no **seletor de corretora** (topo da tela) — você passa a
   operar dentro dela.
2. O sistema recarrega suas permissões (o menu que você vê vem do servidor).
3. **Importante:** aceitar o convite te torna **membro**, mas **ainda não te dá
   telas**. O que você vê depende do **perfil de acesso** que o administrador vai
   te atribuir — ver [4 · Atribuir perfil de acesso](04-perfil-acesso.md).

!!! tip "Recusar por engano"
    Recusar pede confirmação e **não é definitivo**: o administrador pode reenviar
    o convite depois.

## Nenhum convite? {#nenhum-convite}

Se a tela diz **"Nenhum convite no momento"**, na ordem de probabilidade:

1. **E-mail diferente.** O administrador convidou um endereço que não é o da sua
   conta — um typo, ou um **ponto** a mais/menos. O Gmail ignora pontos
   (`joao.silva@` = `joaosilva@` na entrega), mas o sistema trata como
   **endereços diferentes**. Confirme com quem convidou o e-mail exato.
2. **Conta com outro e-mail.** Você criou a conta com um e-mail e foi convidado em
   outro (ex.: pessoal × corporativo).
3. **Convite ainda não enviado.** Alinhe com o administrador.

→ Próximo (para o dono): [3 · Convidar a equipe](03-convidar.md)
