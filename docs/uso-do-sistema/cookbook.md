# Cookbook — do zero à comissão paga

Tutorial guiado do fluxo completo do gestao.one, montando uma corretora de
exemplo do zero até o dinheiro aparecer na conta de cada pessoa.

Use este doc de duas formas: como **treinamento** (siga na ordem, é um roteiro
executável em DEV) e como **roteiro de demo** para dono de corretora (o resumo
de 15 minutos está no fim).

---

## O elenco do exemplo

Uma corretora com quatro pessoas:

| Pessoa | Faz o quê | Perfil de acesso | Papel no time |
| --- | --- | --- | --- |
| Renato | dono | `admin` | `director` (diretor) |
| Marina | gerente comercial | `gerente` | `manager` (gerente) |
| Bruno | vendedor | `vendedor` | `seller` |
| Carla | vendedora | `vendedor` | `seller` |

E o plano de comissão que queremos:

| Faixa | Rateio |
| --- | --- |
| Parcela 1 | 100% para os vendedores |
| Parcela 2 | 50% vendedores · 25% dono · 25% gerente |

> **Atenção ao conceito central:** existem **dois** conjuntos de papéis no
> sistema, e eles não se misturam.
>
> - **Perfil de acesso** (`admin`, `gerente`, `vendedor`) = **o que a pessoa
>   pode ver e fazer** nas telas. Vem do módulo de acesso.
> - **Papel de time** (`director`, `manager`, `seller`) = **quanto a pessoa
>   ganha** no rateio da comissão.
>
> Marina pode ser `gerente` no acesso e `seller` no time — são decisões
> independentes. Confundir os dois é o erro nº 1 de quem está montando o
> primeiro plano.

---

## Ordem de montagem (e por que essa ordem)

O sistema tem dependências duras: cada etapa só existe porque a anterior
existe. Montar fora de ordem trava.

```
Usuários  →  Times  →  Catálogo  →  Plano de comissão
                                          ↓
   Pessoa (cliente)  →  Lead  →  Proposta  →  APÓLICE
                                          ↓
                          Comissões pendentes → confirmar
                                          ↓
                     Recebíveis + Conta corrente (o dinheiro)
```

Campanha é o único bloco que corre em paralelo — não bloqueia nada.

---

# Parte 1 — Montar a estrutura (uma vez só)

## Passo 1 · Colocar as pessoas dentro da corretora

**Onde:** menu → membros da empresa / convites.

O time precisa existir como **usuário da corretora** antes de qualquer coisa.
Convide Marina, Bruno e Carla. Cada um recebe um convite, cria a senha e entra.

Duas regras que confundem:

- **Criar conta ≠ ter corretora.** Quem se cadastra sozinho no gestao.one fica
  sem corretora até ser convidado. É esperado.
- O perfil de acesso (`vendedor`, `gerente`) define o menu que a pessoa vê.
  Bruno logado **não enxerga** as telas de plano e de conta corrente da
  corretora — e é assim que tem que ser.

> **Convite não aparece para a pessoa?** Quase sempre é e-mail digitado errado:
> convidar um e-mail sem conta **não dá erro na tela** (é anti-enumeração).
> Confira a grafia — inclusive pontos, que o Gmail ignora mas o sistema não.

✅ **Checkpoint:** as 4 pessoas aparecem em Membros da empresa.

## Passo 2 · Criar o time e distribuir os papéis

**Onde:** Comissões → **Times**.

Crie um time — ex.: `TIME SENNA`. Abra o time e adicione os quatro membros,
cada um com seu papel:

| Membro | Papel |
| --- | --- |
| Renato | `director` |
| Marina | `manager` |
| Bruno | `seller` |
| Carla | `seller` |

**Por que o dono e o gerente entram no time?** Porque o plano só sabe pagar
três tipos de destinatário:

| Destinatário | Quem recebe |
| --- | --- |
| **Vendedor** | o vendedor **daquela venda específica** (quem fechou) |
| **Corretora (casa)** | fica com a empresa, não com pessoa nenhuma |
| **Papel de time** | todo mundo que tem aquele papel no time escolhido |

Não existe "pagar direto para o Renato". Para pagar uma pessoa específica, ela
precisa ter um **papel que só ela tem** no time. Foi exatamente a sua intuição:
*"grupos de um usuário"*. O papel `director` é o grupo-de-um do dono; `manager`,
o da gerente.

⚠️ **A pegadinha silenciosa:** se o plano tem uma linha para o papel `director`
e ninguém no time tem esse papel, aquele pedaço da comissão **distribui zero,
sem erro nenhum**. A tela avisa, mas só se os membros já estiverem cadastrados.
Monte o time **antes** do plano.

✅ **Checkpoint:** o time mostra 4 membros, com os 4 papéis preenchidos.

## Passo 3 · Catálogo de operadoras e produtos

**Onde:** Comissões → **Operadoras**.

Cadastre a operadora (ex.: `PORTO SEGURO`) e seus produtos (ex.: `AUTO`,
`RESIDENCIAL`).

Parece burocracia, mas é o que faz o gráfico "Onde estão as vendas" funcionar:
sem catálogo, o produto é texto livre digitado na venda — e `PORTO SEGURO AUTO`,
`Porto auto` e `porto seguro auto` viram três produtos diferentes no relatório.
O catálogo é o que mantém o ranking honesto.

## Passo 4 · O plano de comissão — o coração da coisa

**Onde:** Comissões → **Planos** → Novo plano.

Crie o plano: nome (`PLANO AUTO PADRÃO`), o produto do catálogo e o
**desconto de imposto** (ex.: 10%). Esse imposto sai do valor bruto **antes** de
qualquer divisão — é por isso que o líquido é menor que o bruto.

Abra o plano. Um plano é uma lista de **faixas de parcela**, e cada faixa tem
suas **linhas de rateio** que precisam somar exatamente 100%.

### Montando o nosso exemplo

**Faixa 1 — da parcela 1 até a 1:**

| Linha | % |
| --- | --- |
| Papel de time → `TIME SENNA` / `seller` | 100 |
| | **100 ✅** |

**Faixa 2 — da parcela 2 até a 2:**

| Linha | % |
| --- | --- |
| Papel de time → `TIME SENNA` / `seller` | 50 |
| Papel de time → `TIME SENNA` / `director` | 25 |
| Papel de time → `TIME SENNA` / `manager` | 25 |
| | **100 ✅** |

**Faixa 3 — da parcela 3 em diante (vitalício):** marque a opção de vitalício
em vez de informar a parcela final. Sem essa faixa, da 3ª parcela em diante
ninguém recebe nada.

### Duas decisões que valem parar para pensar

**1. `seller` (papel de time) ou "Vendedor" (destinatário)?** São coisas
diferentes e a escolha muda o negócio:

- **"Vendedor"** = quem fechou a venda leva tudo. Comissão individual, incentiva
  a competição.
- **Papel `seller` do time** = divide entre todos os vendedores do time. Comissão
  coletiva, incentiva a cooperação.

Você pediu *"100% para o time de vendedores"* — então é o papel de time. Se a
ideia for premiar quem vendeu, troque por "Vendedor". É uma escolha de política
comercial, não técnica.

**2. Use o simulador antes de sair vendendo.** No fim da tela do plano, informe
um prêmio de exemplo (ex.: R$ 1.200,00) e veja em reais quanto cada linha rende.
É o momento de descobrir que a conta não fecha como você imaginava — antes de
uma apólice real depender dela.

⚠️ **Plano é quase imutável.** Não dá para editar uma linha nem apagar uma linha
isolada: remove-se a **faixa inteira** e monta de novo. E se o plano já tiver
apólice emitida, a remoção é **bloqueada** — mexer no rateio mudaria comissões
que já estão pendentes. Para mudar a regra depois disso, crie um plano novo para
as próximas vendas.

✅ **Checkpoint:** todas as faixas com o selo verde de 100% e o simulador
batendo com o que você espera pagar.

## Passo 5 · Campanha (opcional, roda em paralelo)

**Onde:** Comissões → **Campanhas**.

Campanha é **incentivo por meta**, não faz parte do rateio: "quem vender 10
apólices de auto entre 01/09 e 31/10 ganha R$ 500". Você define produto,
período, meta (quantidade) e bônus (valor fixo ou percentual).

O acompanhamento é automático — conforme as apólices são emitidas, o sistema
gera as metas por vendedor. Você só acompanha o progresso.

⚠️ Campanha **não pode ser editada nem excluída**. Confira as datas antes de
salvar.

---

# Parte 2 — Fazer uma venda acontecer

## Passo 6 · Cadastrar o cliente (Pessoas)

**Onde:** menu → **Clientes**.

Tudo começa numa pessoa. Cadastre o cliente com nome e CPF/CNPJ (o dígito
verificador é validado — documento inválido não passa).

**A busca por aproximação** é o detalhe que os corretores mais gostam: digite
**pelo menos 3 letras** e ela encontra por semelhança, não por igualdade. Buscar
`joao silva` acha `JOÃO DA SILVA SANTOS`; erro de digitação e acento não
atrapalham. Também funciona por documento.

Na ficha da pessoa você ainda tem: **documentos** (anexos), **interações**
(histórico de contato) e **vínculos** (relação entre pessoas — cônjuge,
dependente, empresa/sócio).

> Excluir uma pessoa apenas **desativa**: some das listas, nada é perdido.

## Passo 7 · Lead — a oportunidade

**Onde:** Comissões → **Leads**.

O lead liga **uma pessoa** a **um produto**, com o vendedor responsável. É onde
a oportunidade vive enquanto está em negociação — anote as conversas no campo de
notas.

No nosso exemplo: lead do cliente com o Bruno como vendedor.

Quando o cliente decide fechar, clique em **Converter**. Isso libera o lead para
virar proposta. É irreversível — mas só marca o lead, não cria nada ainda.

> A pessoa precisa existir antes. O lead não cadastra cliente.

## Passo 8 · Proposta — e o nascimento da apólice

**Onde:** Comissões → **Propostas**.

Crie a proposta escolhendo:

- o **lead convertido**;
- o **plano de comissão** (aqui é onde a regra do Passo 4 entra na venda);
- o **prêmio** e o **número de parcelas** (ex.: R$ 1.200,00 em 12x).

Ciclo de vida:

```
rascunho ──Enviar──> enviada ──Aceitar──> APÓLICE ATIVA
    └────────── Cancelar ──────────┘
```

**"Aceitar" é o momento mágico.** Nesse clique o sistema:

1. gera a **apólice**;
2. gera as **12 parcelas de comissão**, cada uma com bruto, imposto e líquido;
3. congela o plano de comissão naquela apólice.

⚠️ **Aceitar não tem volta.** Confira prêmio, parcelas e plano antes.

✅ **Checkpoint:** a apólice aparece e as parcelas estão listadas como pendentes.

---

# Parte 3 — O dinheiro

## Passo 9 · Dar baixa nas comissões

**Onde:** Comissões → **Pendentes** (visão da gestão/financeiro).

Cada linha é uma parcela: **bruto − imposto = líquido**. Enquanto está
`pendente`, ninguém recebeu nada — o valor existe, mas não foi distribuído.

**Confirmar** uma parcela = a operadora pagou aquela parcela → o sistema roda o
rateio do plano e credita cada beneficiário.

Confirmando a **parcela 1** da nossa apólice (100% para o papel `seller`), o
valor líquido vai para os vendedores do time. Confirmando a **parcela 2**, o
mesmo líquido se divide 50/25/25 entre vendedores, Renato e Marina.

Dá para selecionar várias e usar **Confirmar selecionadas** — vão uma a uma e
sai um relatório no fim. O lote **não é tudo-ou-nada**: parcela já confirmada
volta marcada como tal e o resto segue normalmente.

⚠️ **Não existe estorno pela interface.** Confirmar em lote sem conferir é o
jeito mais rápido de criar dor de cabeça. E a tela de confirmação **não mostra a
divisão** — o rateio aparece só em Recebíveis.

## Passo 10 · Ver o rateio chegar (o teste dos dois navegadores)

Este é o passo que fecha o entendimento. Faça exatamente assim:

**Navegador 1 — você (dono/admin), em Comissões → Recebíveis:**
vê o **total da corretora por beneficiário**. Quanto ficou na casa, quanto foi
para cada pessoa, o que já entrou e o que ainda está por vir.

**Navegador 2 (janela anônima) — logado como o Bruno, mesma tela:**
Bruno vê **só o dele**. Total recebido, total a receber, e apólice por apólice
quanto ele ganha em cada parcela — com o percentual e a origem (veio como
vendedor da venda? como papel de time?).

Confirme mais uma parcela no navegador 1 e recarregue o navegador 2: o valor do
Bruno sobe. É a demonstração mais convincente do produto inteiro.

> Se o valor de uma parcela para outra muda, está certo: é o plano aplicando
> percentuais diferentes por faixa.

## Passo 11 · Conta corrente

- **Saldo e movimentos** (gestão): o saldo da corretora e **todos** os
  movimentos, de todos os beneficiários. Vermelho é saída.
- **Meu extrato** (todo mundo): os lançamentos da própria pessoa. É onde o
  vendedor confere o que recebeu.

Enquanto Recebíveis mostra o **direito** (quanto a apólice te rende), a conta
corrente mostra o **caixa** (o que entrou e saiu de fato).

> Corretora recém-criada pode mostrar "em provisionamento" — a conta é criada
> automaticamente logo depois do cadastro. Atualize em alguns instantes.

---

# Parte 4 — A home, para apresentar ao dono

A visão geral se monta **pelo que cada usuário pode ver**: quem não tem
permissão num bloco simplesmente não recebe aquele bloco. O dono vê tudo; o
vendedor vê essencialmente "Seus recebíveis".

| Bloco | Mostra | Responde a pergunta |
| --- | --- | --- |
| **Dinheiro da corretora** | Já entrou · A receber · Ficou na casa · Pago à equipe | "Quanto a corretora ganhou e quanto sobrou pra mim depois de pagar o time?" |
| **Por unidade** | Recebido e a receber por filial | "Qual unidade está performando?" |
| **Comercial** | Leads novos, propostas em aberto, fechadas, prêmio fechado, ticket médio e a curva dos **últimos 6 meses** | "Estou vendendo mais ou menos que no mês passado?" |
| **Onde estão as vendas** | Ranking por **operadora** e por **produto** | "Meu negócio depende de qual operadora? Que produto fecha mais?" |
| **A confirmar** | Fila do financeiro: quantas parcelas, bruto, imposto, líquido | "Quanto tem parado esperando baixa?" |
| **Seus recebíveis** | Extrato pessoal + maiores apólices | "Quanto eu, pessoalmente, vou receber?" |
| **Estrutura** | Contagem de planos, times, campanhas ativas e clientes | "A operação está configurada?" |

O argumento de venda para o dono está no bloco **Dinheiro da corretora**: a
separação **casa × equipe**. É a resposta que ele normalmente só tem depois de
uma tarde de planilha.

---

# Roteiro de demo — 15 minutos

Com a estrutura já montada (Passos 1 a 5 feitos antes):

1. **Home** (2 min) — comece pelo dinheiro: casa × equipe, curva de 6 meses,
   ranking por operadora.
2. **Plano de comissão** (3 min) — abra o plano e mostre o **simulador**. "A
   regra da sua corretora vira isso aqui, e você vê em reais antes de vender."
3. **Cliente → Lead → Proposta** (4 min) — mostre a busca por aproximação, crie o
   lead, converta, crie a proposta e **aceite**. Aponte as 12 parcelas nascendo.
4. **Confirmar a parcela 1** (2 min) — bruto, imposto, líquido.
5. **Os dois navegadores** (3 min) — o dono vê o total da corretora; o vendedor
   vê só o dele, e o valor sobe na frente do cliente. **Este é o clímax.**
6. **Campanha** (1 min) — o incentivo por meta, rodando sozinho.

---

# Colinha de pegadinhas

| Situação | O que está acontecendo |
| --- | --- |
| Convite não aparece para a pessoa | E-mail digitado errado — convidar e-mail sem conta não dá erro. Confira a grafia. |
| Faixa do plano não salva | As linhas não somam 100%. |
| Linha de papel de time paga zero | Nenhum membro do time tem aquele papel. Ajuste em Times. |
| Não consigo remover a faixa | O plano já tem apólice emitida. Crie um plano novo. |
| Nenhum lead para escolher na proposta | O lead existe mas não foi **convertido**. |
| Não acho a pessoa na busca | Menos de 3 letras — ou ela não foi cadastrada ainda. |
| Erro de documento duplicado | Já existe pessoa com esse CPF/CNPJ nesta corretora. |
| Confirmei a comissão e não vi a divisão | A divisão aparece em **Recebíveis**, não na confirmação. |
| Vendedor diz que a tela "não existe" | O perfil de acesso dele não tem aquele item. É controle de acesso, não bug. |

**Sem volta:** converter lead · aceitar proposta · confirmar comissão · criar
campanha. Confira antes de clicar.

---

## Para ir mais fundo

- Cada tela tem **ajuda contextual** com passos e perguntas frequentes — é a
  mesma linguagem deste doc, no momento do uso.
- Detalhe técnico (logs, SQL, contratos por módulo, AWS) fica numa wiki separada e
  **privada** — a `wiki-gestao-one-tecnica`.
