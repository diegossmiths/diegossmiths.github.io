---
layout: post
title: Congelamentos no Fedora 42
description: Resolvendo um probleminha de congelamento no meu computador
keywords: lenovo, thinkpad, z13, amd, radeon, amdpgu, amdgpu_cs_query_fence_status
date: 2025-07-27 02:09:49 -0300
---

Desde que comprei meu notebook, um Lenovo ThinkPad Z13 Gen 2, em fevereiro do ano passado, tudo estava rodando perfeitamente bem, sem nenhum problema, com todos os dispositivos funcionando perfeitamente, com atualizações constantes de firmwares através do fwupd, drivers estáveis e um sistema super responsivo. Acontece que, quando o sistema foi atualizado para esta última versão (Fedora 42 com GNOME 48), algo aconteceu, e muitas vezes em que o computador hibernava, ele não voltava a vida. Haviam vezes que eu estava trabalhando e, do nada, ele congelava.

Primeiramente eu suspeitei de erro de memória, e confesso que fiquei um pouco receoso, visto que a RAM dele é soldada na placa. Fiz um teste de memória com o [Memtest86+](https://memtest.org/) e nada de anormal foi detectado. Além disso, ele tem 3 anos de garantia, então até aí tudo bem.

Num determinado dia, enquanto trabalhava e ouvia música, o sistema novamente travou, porém a música continuou executando, então eu pensei, "o que trava é somente a parte gráfica, não o sistema por completo". Reiniciei forçadamente e tentei analisar o log. Não consegui ver nada de errado até onde consegui, porém tive uma ideia. Na próxima vez na qual o PC desse problema, eu ia conectar nele via SSH para analisar em tempo real. Não demorou muito para que isso acontecesse novamente, foi na mesma manhã. Peguei meu celular, abri o [termux](https://termux.dev/en/) e fiz um SSH para o computador. Consegui logar. Como não é muito bom usar o terminal num aparelho celular, peguei um notebook velho que eu tinha aqui e fiz um SSH para o ThinkPad. Comecei a analisar os logs e finalmente consegui ver o que estava acontecendo.

O erro era basicamente esse

> Apr 12 10:12:26 tppinkepank kernel: amdgpu 0000:04:00.0: amdgpu: GPU reset begin!
> Apr 12 10:12:28 tppinkepank gnome-shell[2613]: amdgpu: amdgpu_cs_query_fence_status failed.
> Apr 12 10:12:28 tppinkepank gnome-shell[2613]: amdgpu: The CS has been rejected (-125), but the context isn't robust.
> Apr 12 10:12:28 tppinkepank gnome-shell[2613]: amdgpu: The process will be terminated.

Saí a cata do que poderia ser e acabei encontrando algumas postagens em fóruns sobre isso, inclusive no fórum oficial do Fedora. A saída? Adicionar o parâmetro ´´´amdgpu.dcdebugmask=0x10´´´ nas configurações do GRUB. Um parte do meu arquivo de inicialização localizado em /etc/default/grub ficou assim:

> ...
> GRUB_CMDLINE_LINUX="... amdgpu.dcdebugmask=0x10"
> ...

Logo após é necessário atualizar o inicializador com o comando ´´´sudo grub2-mkconfig -o /boot/grub2/grub.cfg´´´. Depois do processo terminado, é hora de fazer um ´´´sudo reboot´´´.

Se tudo ocorreu bem, o sistema vai iniciar normalmente. Após o login, abra o terminal e digite ´´´sudo cat /sys/kernel/debug/dri/1/eDP-1/psr_capability´´´. A saída do comando deve ser:

> Sink support: yes [0x03]
> Driver support: no [0xffffff]

Em seguida, digite ´´´sudo cat /sys/kernel/debug/dri/1/eDP-1/psr_state´´´. Essa saída deverá ser o número 0 (zero).

De tudo o que eu li por aí, pelo que pude entender, o problema é no PSR (Panel Self Refresh), uma função que supostamente reduz o consumo de energia do painel. Para ser sincero não notei grande diferença na autonomia do computador, se houve, foi pouca.

Daqui um tempo irei remover esse parâmetro para saber se o bug foi corrigido. Se foi, atualizarei aqui.

Espero que isso um dia ajude alguém.
