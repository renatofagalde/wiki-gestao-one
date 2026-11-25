# SS2 · Linux

!!! note "Em breve"
    O suporte a **Linux** está no horizonte. Hoje o agente é **Windows-first**.

**O que falta:** os coletores nativos (janela ativa, métricas, screenshot,
watchers de dispositivo) ainda são implementados só para Windows. A biblioteca de
serviço usada (`kardianos/service`) já cobre o **systemd** do Linux, então os
comandos de serviço (`install`/`start`/`stop`/`restart`/`uninstall`) devem
funcionar quando os coletores de Linux existirem.

Quando disponível, este guia terá o mesmo formato do
[guia de Windows](windows.md): rodar com privilégio (`sudo`), flags, como parar
(`systemctl stop` vs o `stop` do binário) e como remover.
