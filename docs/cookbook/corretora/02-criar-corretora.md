# 2 · Sou dono — criar a corretora (onboarding)

Se você **é o dono**, o passo depois de criar a conta é **montar a corretora**. É o
onboarding: uma tela só, com os dados da empresa e da primeira unidade. A partir
daqui você passa a administrar tudo.

No exemplo, é o **Senna** criando a **Senna Racing Seguros**.

!!! note "Criar conta ≠ ter corretora"
    Criar a conta (passo 1) só cria **você**. A corretora é um vínculo que nasce
    aqui — por isso o onboarding é uma **opção no menu**, nunca algo forçado. Quem
    foi convidado pula este passo e vai para [aceitar o convite](04-aceitar-convite.md).

## Pré-requisito

- Ter uma [conta criada](01-criar-conta.md) e estar logado.
- Ter o **CNPJ** da corretora em mãos (o dígito verificador é validado na tela).

## A tela — Criar sua corretora

**Onde:** menu → **Configurações** → **Onboarding** → botão **Criar corretora**.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 760 440" role="img"
     aria-label="Formulário de onboarding com razão social, e-mail, CNPJ, nome da unidade e código"
     style="width:100%;height:auto;color:var(--md-default-fg-color);font-family:var(--md-text-font-family,system-ui,sans-serif)">
  <rect x="4" y="4" width="752" height="432" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.35"/>
  <line x1="4" y1="38" x2="756" y2="38" stroke="currentColor" stroke-opacity="0.2"/>
  <circle cx="24" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <circle cx="38" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <circle cx="52" cy="21" r="4" fill="currentColor" fill-opacity="0.4"/>
  <rect x="80" y="11" width="280" height="20" rx="10" fill="none" stroke="currentColor" stroke-opacity="0.25"/>
  <text x="94" y="25" font-size="11" fill="currentColor" fill-opacity="0.55">webd.gestao.one/onboarding</text>

  <!-- card central -->
  <rect x="190" y="62" width="380" height="366" rx="12" fill="currentColor" fill-opacity="0.03" stroke="currentColor" stroke-opacity="0.18"/>
  <text x="212" y="98" font-size="16" font-weight="700" fill="currentColor">Criar sua corretora</text>
  <text x="212" y="118" font-size="11" fill="currentColor" fill-opacity="0.55">Os dados da empresa e da primeira unidade.</text>

  <text x="212" y="146" font-size="11" fill="currentColor" fill-opacity="0.7">Razão social</text>
  <rect x="212" y="154" width="336" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="226" y="174" font-size="12" fill="currentColor" fill-opacity="0.9">SENNA RACING SEGUROS</text>

  <text x="212" y="202" font-size="11" fill="currentColor" fill-opacity="0.7">E-mail principal</text>
  <rect x="212" y="210" width="336" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="226" y="230" font-size="12" fill="currentColor" fill-opacity="0.9">contato@sennaracing.test</text>

  <text x="212" y="258" font-size="11" fill="currentColor" fill-opacity="0.7">CNPJ</text>
  <rect x="212" y="266" width="336" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="226" y="286" font-size="12" fill="currentColor" fill-opacity="0.9">11.222.333/0001-81</text>

  <text x="212" y="314" font-size="11" fill="currentColor" fill-opacity="0.7">Nome da unidade</text>
  <rect x="212" y="322" width="210" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="226" y="342" font-size="12" fill="currentColor" fill-opacity="0.9">BOX SENNA</text>
  <text x="438" y="314" font-size="11" fill="currentColor" fill-opacity="0.7">Código</text>
  <rect x="438" y="322" width="110" height="30" rx="7" fill="none" stroke="currentColor" stroke-opacity="0.3"/>
  <text x="452" y="342" font-size="12" fill="currentColor" fill-opacity="0.9">SEN</text>

  <rect x="212" y="378" width="160" height="34" rx="7" fill="currentColor" fill-opacity="0.14"/>
  <text x="292" y="400" font-size="12.5" font-weight="600" fill="currentColor" text-anchor="middle">Criar corretora</text>
  <text x="392" y="400" font-size="12" fill="currentColor" fill-opacity="0.55">Cancelar</text>

  <g font-size="12" font-weight="700" text-anchor="middle">
    <circle cx="212" cy="154" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="212" y="158" fill="currentColor">1</text>
    <circle cx="212" cy="266" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="212" y="270" fill="currentColor">2</text>
    <circle cx="212" cy="322" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="212" y="326" fill="currentColor">3</text>
    <circle cx="212" cy="378" r="12" fill="none" stroke="currentColor" stroke-width="1.5"/><text x="212" y="382" fill="currentColor">4</text>
  </g>
</svg>
<figcaption>Formulário <strong>Criar sua corretora</strong>.</figcaption>
</figure>

## Passo a passo

| # | Campo | O que preencher | Regra |
| --- | --- | --- | --- |
| **1** | **Razão social** / **E-mail principal** | `SENNA RACING SEGUROS` · `contato@sennaracing.test` | Gravado em **maiúsculo** |
| **2** | **CNPJ** | `11.222.333/0001-81` | A máscara e o **dígito verificador** são validados na hora — CNPJ inválido bloqueia o botão |
| **3** | **Nome da unidade** / **Código** | `BOX SENNA` · `SEN` | A primeira unidade (a "matriz"); o código é curto e único |
| **4** | Botão **Criar corretora** | — | Fica habilitado só quando tudo é válido |

## O resultado

- A corretora é provisionada com você como **dono** (perfil `admin`).
- A **primeira unidade** (`BOX SENNA`) já nasce junto — toda corretora opera em
  pelo menos uma unidade.
- A corretora passa a aparecer no **seletor** no topo da tela, já selecionada.
- O menu completo de administração aparece (Usuários, Comissões, Conta corrente…).

!!! warning "CNPJ é validado de verdade"
    O dígito verificador é conferido na tela **e** no servidor. Digitar um CNPJ
    "quase certo" não passa — confira antes de insistir.

!!! success "Checkpoint"
    A **Senna Racing Seguros** aparece no seletor e você vê o menu de dono. Agora
    é hora de trazer a equipe.

→ Próximo: [3 · Convidar a equipe](03-convidar.md)
