# Cookbook · SS2 (Agente)

Guia de **operação** do **agente SS2** — a ferramenta de monitoramento de
atividade do gestao.one, instalada nas máquinas corporativas (com consentimento
assinado).

Diferente dos outros cookbooks (que são de **uso do produto**), este é de
**instalação e operação do agente**: como rodar, com quais flags, como parar e
como remover — **separado por ambiente**.

!!! info "Um binário, vários modos"
    Tudo é feito com o **mesmo executável**. O **ambiente (dev/prd) é fixado no
    build** — o portal (módulo ss2) entrega o `.exe` certo. Não há tela de
    configuração: o agente se identifica por **MAC + usuário de rede** e o
    backend **autoriza**.

## Ambientes

| Sistema | Guia | Estado |
| --- | --- | --- |
| **[Windows](windows.md)** | Serviço do Windows (SCM) | **Disponível** |
| **macOS** | *(launchd)* | Em breve |
| **Linux** | *(systemd)* | Em breve |

Hoje o agente é **Windows-first**. macOS e Linux estão no horizonte (a biblioteca
de serviço usada — `kardianos/service` — já cobre launchd e systemd), mas os
coletores nativos ainda são do Windows. Comece por **[Windows](windows.md)**.

## O nome que importa

Ao longo de todo este guia aparecem dois nomes — não confunda:

| Nome | O que é |
| --- | --- |
| `app-ss2-agente.exe` | o **arquivo executável** (o que você baixa e roda) |
| `AppSS2Agente` | o **nome do serviço** registrado no Windows (o que `sc` e o `services.msc` enxergam) |
