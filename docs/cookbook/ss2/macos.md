# SS2 · macOS

!!! note "Em breve"
    O suporte a **macOS** está no horizonte. Hoje o agente é **Windows-first**.

**O que falta:** os coletores nativos (janela ativa, métricas, screenshot,
watchers de dispositivo) ainda são implementados só para Windows. A biblioteca de
serviço usada (`kardianos/service`) já cobre o **launchd** do macOS, então os
comandos de serviço (`install`/`start`/`stop`/`restart`/`uninstall`) devem
funcionar quando os coletores de macOS existirem.

Quando disponível, este guia terá o mesmo formato do
[guia de Windows](windows.md): rodar com privilégio, flags, como parar e como
remover.
