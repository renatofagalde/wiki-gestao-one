# SS2 · Windows

Operação completa do agente no **Windows**: rodar como Administrador, todas as
flags e comandos, como **parar**, como fazer ele **não rodar mais**, e a
diferença entre `app-ss2-agente.exe stop` e `sc stop AppSS2Agente`.

!!! abstract "Os dois nomes"
    - **Executável:** `app-ss2-agente.exe` — o arquivo que você baixa e roda.
    - **Serviço:** `AppSS2Agente` — o nome registrado no Windows (o que `sc`,
      `Get-Service` e o `services.msc` enxergam).

    O display name no painel de serviços é **“App SS2 Agente”**.

---

## 1. Rodar como Administrador (obrigatório)

Qualquer coisa que **mexe no serviço** (instalar, iniciar, parar, remover)
precisa de um terminal **elevado**. Sem elevação, o Windows nega a operação no
Service Control Manager (SCM) e você vê `Access is denied`.

=== "PowerShell (recomendado)"

    1. Menu Iniciar → digite **PowerShell**.
    2. Clique com o **botão direito** → **Executar como administrador**.
    3. Aceite o prompt do UAC.
    4. `cd` para a pasta onde está o `.exe`:
       ```powershell
       cd C:\gestao-one\ss2
       ```

=== "CMD"

    1. Menu Iniciar → digite **cmd**.
    2. **Botão direito** → **Executar como administrador**.
    3. `cd /d C:\gestao-one\ss2`

=== "Duplo clique"

    Dar **duplo clique** no `.exe` **como Administrador** (botão direito →
    *Executar como administrador*) equivale a rodar **sem argumento**: se o
    serviço ainda não existir, ele **se auto-instala e inicia** (ver §3).

!!! tip "Como saber se o terminal está elevado"
    O título da janela começa com **“Administrador:”**. Na dúvida:
    ```powershell
    ([Security.Principal.WindowsPrincipal][Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole([Security.Principal.WindowsBuiltInRole]::Administrator)
    ```
    Retorna `True` se estiver elevado.

---

## 2. Onde conseguir o `.exe`

Baixe pelo **portal (módulo ss2)**. O pipeline publica o binário privado no S3 e
o portal entrega um link presignado. O **ambiente (dev/prd) vem fixo no binário**
— não há o que configurar depois do download. O agente **não se auto-atualiza**:
trocar de versão é sempre `uninstall` → apagar o `.exe` → baixar o novo → instalar
(ver §7).

---

## 3. Modos de execução

Todos usam o **mesmo binário**. O que ele faz depende de **como** você o chama:

| Como você roda | O que acontece |
| --- | --- |
| **Admin, sem argumento** e o serviço **ainda não existe** | Auto-instala como serviço `AppSS2Agente` (**start automático no boot**), **inicia** e sai. Nada mais a configurar. |
| **Admin, sem argumento** e o serviço **já existe** | Não faz nada: imprime `serviço "AppSS2Agente" já instalado` e sai. Use os comandos da §4 ou `--foreground`. |
| **`--foreground`** | Roda a coleta **no próprio terminal** (primeiro plano), **sem instalar serviço**. Mostra a identidade (usuário, host, MAC, IP) e os logs ao vivo. Encerra com **`Ctrl+C`**. É o modo de teste/depuração. |
| **Rodando como serviço** (pelo Windows, após instalado) | Executa o loop de coleta em background, sob a conta de sistema (**LocalSystem**), no boot. |

!!! note "O usuário monitorado é o da sessão, não o LocalSystem"
    O serviço roda como **LocalSystem**, mas o agente identifica o **usuário
    real logado no console** (via Windows Terminal Services) — não reporta a
    conta de serviço.

---

## 4. Comandos de serviço (palavra solta)

São **palavras soltas**, **sem `--`**, passadas ao próprio executável. Cada uma
fala com o SCM do Windows.

| Comando | O que faz |
| --- | --- |
| `app-ss2-agente.exe install` | **Registra** o serviço (start automático no boot). **Não inicia.** |
| `app-ss2-agente.exe start` | **Inicia** o serviço já instalado. |
| `app-ss2-agente.exe stop` | **Para** o serviço em execução. |
| `app-ss2-agente.exe restart` | **Para e reinicia** o serviço. |
| `app-ss2-agente.exe uninstall` | **Remove** (desregistra) o serviço do Windows. |

!!! danger "`uninstall` ≠ `--uninstall`"
    O traço quebra tudo. **`uninstall`** funciona; **`--uninstall`** **não** —
    ele cai no modo “sem argumento” e **não remove nada** (se o serviço já
    existir, só imprime “já instalado” e sai). Apenas **`--foreground`** e
    **`--url=`** levam traços. Os comandos de serviço são sempre **palavra
    solta**.

---

## 5. Flags (levam `--`)

| Flag | O que faz |
| --- | --- |
| `--foreground` | Roda a coleta **em primeiro plano**, sem instalar serviço. Encerra com `Ctrl+C`. Modo de teste/depuração. |
| `--url=<base>` | **Sobrescreve** a URL do backend embutida no build. Só para teste local; combina com `--foreground`. Ex.: `--url=http://localhost:8080`. |

Exemplo de teste local apontando para um backend na própria máquina:

```powershell
app-ss2-agente.exe --foreground --url=http://localhost:8080
```

!!! info "Resumo: quando leva traço e quando não"
    - **Palavra solta** (SCM): `install`, `start`, `stop`, `restart`, `uninstall`.
    - **Com `--`** (comportamento): `--foreground`, `--url=`.

---

## 6. Parar o serviço

Parar é **temporário**: o serviço continua **instalado** e, por ser
**start automático**, **volta no próximo boot** (e tem `OnFailure=restart`, então
o SCM pode reerguê-lo após falha). Para que ele **não volte**, veja a §7.

Três formas de parar — todas pedem terminal **Administrador**:

=== "Pelo agente"

    ```powershell
    app-ss2-agente.exe stop
    ```
    Você **não precisa** saber o nome do serviço: o binário já o conhece.

=== "Pelo SCM (sc)"

    ```powershell
    sc stop AppSS2Agente
    ```
    Comando nativo do Windows. Exige o **nome exato** do serviço.

=== "PowerShell nativo"

    ```powershell
    Stop-Service AppSS2Agente
    ```
    Equivalente ao `sc stop`, mas espera o serviço chegar em “parado”.

---

## 7. Fazer ele **não rodar mais** (remover de vez)

Como o serviço é **start automático** (e com auto-restart em falha), só `stop`
**não basta** — no próximo boot ele sobe de novo. Há dois caminhos:

### 7a. Desativar (sem remover)

Mantém o serviço registrado, mas **impede de iniciar** (inclusive no boot):

```powershell
app-ss2-agente.exe stop                 # para agora
sc config AppSS2Agente start= disabled  # não sobe mais no boot (note o espaço após "start=")
```

Para religar depois: `sc config AppSS2Agente start= auto` e `app-ss2-agente.exe start`.

### 7b. Remover de vez (uninstall + apagar o `.exe`)

```powershell
app-ss2-agente.exe stop        # para o serviço (recomendado)
app-ss2-agente.exe uninstall   # desregistra o serviço do Windows
```

!!! tip "Mensagens inofensivas ao parar/remover"
    - Se o `stop` responder **`Failed to stop ... O serviço não foi iniciado.`**,
      **ignore**: só quer dizer que já estava parado. Siga para o `uninstall`.
    - Se mais adiante o `Stop-Process` disser **`Não é possível localizar um
      processo com o nome "app-ss2-agente"`**, **ignore**: nada estava travando o
      arquivo.

O `uninstall` **desregistra** o serviço, mas o processo que rodava como SYSTEM
pode continuar vivo e **manter o `.exe` travado** — aí `Remove-Item` falha com
*Access Denied*. Rode a sequência (serve também de garantia mesmo sem processo
vivo):

```powershell
sc stop AppSS2Agente                       # para o serviço, se ainda rodando
Stop-Process -Name app-ss2-agente -Force   # mata o processo que trava o arquivo
Remove-Item .\app-ss2-agente.exe           # agora o arquivo apaga
```

Se ainda assim não apagar (raro), **reinicie a máquina** e apague — o “marcado
para remoção” some no boot.

### Trocar por uma versão nova

O agente **não se auto-atualiza**. A troca é sempre:

```
uninstall  →  apagar o .exe  →  baixar o novo (portal)  →  install / rodar o novo
```

Depois de baixar o novo, duas formas equivalentes de subir:

```powershell
app-ss2-agente.exe install     # registra (start automático no boot)
app-ss2-agente.exe start       # inicia agora, sem esperar o boot
```

Ou **duplo clique no `.exe` novo como Admin** (sem argumento): auto-instala,
inicia e sai.

---

## 8. `app-ss2-agente.exe stop` **vs** `sc stop AppSS2Agente`

Esta é a dúvida mais comum. **Os dois param o mesmo serviço, pelo mesmo
caminho** (o SCM do Windows) — a diferença está em *quem dispara* e em *como cada
um espera o fim*.

```
app-ss2-agente.exe stop ─┐
                         ├─►  SCM (Service Control Manager)  ─►  para "App SS2 Agente"
sc stop AppSS2Agente ────┘                                          (graceful: drena e sai)
```

| | `app-ss2-agente.exe stop` | `sc stop AppSS2Agente` |
| --- | --- | --- |
| **Caminho** | Pede ao **SCM** para parar o serviço | Pede ao **SCM** para parar o serviço |
| **Precisa saber o nome do serviço?** | **Não** — o binário já sabe que é `AppSS2Agente` | **Sim** — você digita o nome exato |
| **Precisa do `.exe` presente?** | **Sim** — você chama o próprio executável | **Não** — `sc` é do Windows; funciona mesmo se o `.exe` sumiu/foi renomeado |
| **Espera terminar?** | **Sim** — aguarda o loop **drenar** e sair | **Não** — envia o sinal STOP e **retorna na hora** (assíncrono) |
| **Precisa ser Admin?** | Sim | Sim |

**Como cada um se comporta na prática:**

- **`app-ss2-agente.exe stop`** — usa a biblioteca de serviço do próprio agente.
  Ele resolve o nome `AppSS2Agente` sozinho, manda o STOP e **espera o
  encerramento limpo** (o agente cancela o contexto e aguarda a coleta
  finalizar). É o **jeito preferido no dia a dia**: menos chance de erro de
  digitação, e você tem certeza de que parou de verdade.
- **`sc stop AppSS2Agente`** — é a ferramenta **nativa e de baixo nível** do
  Windows. Útil quando **o `.exe` não está à mão** (foi apagado/renomeado) ou em
  **script/automação** que só conhece o nome do serviço. Como é **assíncrono**,
  logo após o `sc stop` o serviço pode ainda estar em “stopping” por um instante
  — confirme com `sc query` (abaixo).

!!! warning "E o `Stop-Process`? É outra coisa"
    ```powershell
    Stop-Process -Name app-ss2-agente -Force
    ```
    **Não** passa pelo SCM: **mata o processo direto** (hard kill), sem
    encerramento limpo. Use **só** como último recurso — tipicamente quando o
    `.exe` ficou **travado** e nem `stop` nem `sc stop` liberaram o arquivo para
    apagar (§7b). Não é o jeito normal de parar o serviço.

**Regra de bolso:** no dia a dia use **`app-ss2-agente.exe stop`**. Use **`sc
stop`** quando não tiver o binário ou estiver em script. Use **`Stop-Process`**
só para destravar o arquivo antes de apagar.

---

## 9. Conferir o estado

| Quero… | Comando |
| --- | --- |
| Estado do serviço (nativo) | `sc query AppSS2Agente` |
| Estado (PowerShell) | `Get-Service AppSS2Agente` |
| Config de inicialização (auto/disabled) | `sc qc AppSS2Agente` |
| Ver no painel gráfico | `services.msc` → procure **“App SS2 Agente”** |

No `sc query`, o campo **`STATE`** mostra `RUNNING`, `STOPPED` ou `STOP_PENDING`.

!!! info "Onde ficam os problemas: Windows Event Log"
    O agente é uma ferramenta corporativa e **não grava status em arquivo no
    disco** (o usuário monitorado não pode ler nem adulterar). Falhas e eventos
    importantes vão para o **Windows Event Log**, não para um `.log` na pasta.
    Para investigar, use o **Visualizador de Eventos** (`eventvwr.msc`) ou:
    ```powershell
    Get-EventLog -LogName Application -Source AppSS2Agente -Newest 20
    ```

---

## 10. Tabela-resumo

| Ação | Comando (Admin) |
| --- | --- |
| Instalar e iniciar (1ª vez) | duplo clique como Admin, **ou** `install` + `start` |
| Só registrar (sem iniciar) | `app-ss2-agente.exe install` |
| Iniciar | `app-ss2-agente.exe start` |
| Parar (preferido) | `app-ss2-agente.exe stop` |
| Parar (nativo / sem o `.exe`) | `sc stop AppSS2Agente` |
| Reiniciar | `app-ss2-agente.exe restart` |
| Desativar sem remover | `sc config AppSS2Agente start= disabled` |
| Remover de vez | `stop` → `uninstall` → apagar o `.exe` |
| Destravar o arquivo p/ apagar | `Stop-Process -Name app-ss2-agente -Force` |
| Testar em primeiro plano | `app-ss2-agente.exe --foreground` |
| Apontar p/ backend local | `app-ss2-agente.exe --foreground --url=http://localhost:8080` |
| Ver estado | `sc query AppSS2Agente` |
