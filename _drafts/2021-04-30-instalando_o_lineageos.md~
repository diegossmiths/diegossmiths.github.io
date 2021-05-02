---
layout: post
title: Instalando o LineageOS
author: Diego Schild Smiths
description:
keywords:
---

## A historinha

Antes, talvez o mais importante, um pouco de história para nos situarmos.

Resumindo de forma bem resumida. O LineageOS nasceu como um sucessor espiritual do CyanogenMod. Em 2009 um sujeito chamado Steve Kondik fundou uma empresa chamada Cyanogen Inc. junto com outro sujeito chamado Kirt McMaster. Num determinado momento, ambos começaram a discordar dos rumos que deveriam ser seguidos, contratos ruins foram assinados e McMaster começou a soltar um monte de abobrinhas em entrevistas, o que começou a "pegar mal" para a empresa. A partir daí a coisa foi ladeira a baixo. A confusão toda começou em julho de 2016, e em dezembro tudo acabou.

Tentando explicar melhor. A Cyanogen Inc. abrigava dois projetos dentro dela, o CyanogenMod e o CyanogenOS. O CyanogenMod era um sistema operacional baseado no Android, totalmente de código aberto e que era mantido pela comunidade de desenvolvedores que tinha como objetivo manter aparelhos antigos atualizados. CyanogenOS era baseado no "mod", mas era mantido pelos empregados da empresa e era o que eles comercializavam junto à outras companhias, e este possuía partes do código fechadas e patenteadas (incluindo aí o nome).

A solução encontrada por Kondik para que seu projeto não morresse com o fim da Cyanogem Inc. foi criar um _fork_ do CyanogenMod. Aqui, um adendo: um _fork_ nada mais é quando um desenvolvedor, ou um grupo deles, criam um projeto independente com base no código de outro projeto já existente, ou seja, eles pegam o código de um _software_ que já existe e o modificam para adequar aos seus interesses, mesmo o que original, que serviu como base, ainda esteja ativo e em desenvolvimento. Assim, temos 2 softwares similares, com uma mesma base, mas que, com o tempo, tendem a tomar rumos diferentes.

Com o fim da Cyanogen Inc. e de seus projetos, nascia aí o LineageOS. No inglês, _lineage_ significa "linhagem", isto é, uma série de gerações de uma família. A comunidade que já desenvolvia o CyanogenMod abraçou a causa e continuou seus serviços com o LineageOS. Assim, donos de aparelhos legados, deixados a ver navios pelas fabricantes, conseguiriam manter seus sistemas atualizados.

Portanto, esse é o resumo da história. Então vamos para a parte prática.

## Notas

Antes de mais nada, convido o leitor a acessar a [página oficial](https://lineageos.org/) do projeto. Ali, é possível encontrar todos os aparelhos mantidos pela comunidade, assim como tutoriais (como este), os instaladores e notas de cada versão lançada. Verifique se seu aparelho consta na lista dos compatíveis. Se sim, já aproveite e baixe os dois arquivos necessários para a instalação do LineageOS, o último arquivo _.zip_ e a imagem de recuperação _.img_ correspondente.

Neste exemplo, usarei o [Motorola Moto G4 Play](https://www.gsmarena.com/motorola_moto_g4_play-8104.php) como base. É um aparelho que foi lançado em agosto de 2016, possui um processador de baixo custo e relativamente pouca memória RAM. Podem haver algumas diferenças entre marcas e modelos, mas se houver, será muito pouca coisa. No computador de mesa, utilizo o [elementaryOS](https://elementary.io/) versão 5.1.7, um sistema GNU/Linux baseado no [Ubuntu](https://ubuntu.com/).

É interessante também que você tenha uma leve noção de como funciona um terminal, neste caso o [_bash_](https://pt.wikipedia.org/wiki/Bash).

Apenas deixando claro que, ao instalar o LineageOS a **garantia será perdida**. Além disso, **eu não me responsabilizo por qualquer dano ao seu aparelho**. Tudo será por sua conta e risco.

Se você concordar com tudo o que foi dito até aqui, siga em frente.

## Preparando o aparelho

Como disse anteriormente, este documento é baseado no Moto G4 Play. Antes de mais nada, ele deve estar rodando o Android na versão 7.1.1. Para verificar, vá em "Configurações > Sobre o dispositivo" e cheque a versão do sistema. Se não estiver, faça a atualização junto a Motorola. É possível achar a opção nas configurações do aparelho em "Configurações > Sobre o dispositivo > Atualização do sistema".

Feito, devemos ativar o "Modo desenvolvedor". Para isso, volte em "Configurações > Sobre o dispositivo" e clique *7 vezes* sobre "Número da versão". Quando for o suficiente, uma _pop-up_ aparecerá indicando que o modo foi habilitado.

Volte para o menu anterior e veja que agora apareceu um item novo chamado "Programador". Clique nele.

Dentro deste menu, role a página até chegar na sessão "Depuração". Habilite a opção "Depuração USB".

Pronto, o aparelho já está pronto para receber o LineageOS.

## Baixando e instalando o adb-fastboot

Em primeiro lugar, é necessário baixar o _adb-fastboot_. O ADB, sigla para _Android Debug Bridge_, e o _fastboot_ são ferramentas presentes no _Android SDK Platform Tools_, desenvolvidas pela Google para facilitar a comunicação entre um PC e um aparelho Android. O ADB é como um canivete suíço, possui inúmeras funções que auxiliam o desenvolvedor. O _fastboot_ é um protocolo de comunicação e uma ferramenta de mesmo nome que tem o objetivo modificar o sistema de arquivos de um aparelho Android via conexão USB.

Como disse anteriormente, esse tutorial é feito para computadores rodando GNU/Linux, mais precisamente sistemas baseados no Debian/Ubuntu. Portanto, baixemos o arquivo mais recente disponibilizado pela Google [neste link](https://dl.google.com/android/repository/platform-tools-latest-linux.zip).

Faça a extração dos arquivos num diretório a sua escolha. Eu recomendo criar um diretório chamado _adb-fastboot_ dentro da _home_ do seu usuário. Feito, adicione o seguinte comando no terminal:

>if [ -d "$HOME/adb-fastboot/platform-tools" ] ; then \\
> export PATH="$HOME/adb-fastboot/platform-tools:$PATH" \\
>fi

Após concluir, saia e entre novamente em sua conta para que as variáveis adicionadas sejam carregadas no sistema. Não é preciso reinicar o computador.

É necessário também configurar as regras do _udev_. O _udev_ é um administrador de dispositivos para _kernel_ Linux, isto é, é ele o responsável por detectar e montar todos os dispositivos que ligamos no PC. Para simplificar as coisas, simplesmente copie e cole cada um destes comandos no terminal:

>git clone https://github.com/M0Rf30/android-udev-rules.git \\
>cd android-udev-rules \\
>sudo cp -v 51-android.rules /etc/udev/rules.d/51-android.rules \\
>sudo chmod a+r /etc/udev/rules.d/51-android.rules \\
>groupdel adbusers \\
>sudo mkdir -p /usr/lib/sysusers.d/ && sudo cp android-udev.conf /usr/lib/sysusers.d/ \\
>sudo systemd-sysusers \\
>sudo usermod -a -G adbusers $(whoami) \\
>sudo udevadm control --reload-rules \\
>sudo service udev restart \\
>adb kill-server

Agora, antes de terminar, ligue seu aparelho no PC através de um cabo USB. Feito isto, digite:

>adb devices

Uma caixa de diálogo aparecerá no seu celular perguntando se vocês deseja permitir a depuração pelo computador. Marque a caixa "Sempre permitir a partir deste computador" e clique em "Ok". Você verá a identificação do seu dispositivo.

Digite _adb reboot bootloader_ para carregar as opções de desenvolvedor do Android. O aparelho vai entrar numa tela preta com informações do hardware.

digite _fastboot devices_ para o terminal responder com o código do aparelho.

Se aparecer um código, significa que está tudo funcionando da maneira correta. Sigamos.

### Desbloqueando o bootloader

Para podermos instalar o LineageOS, devemos desbloquear o _bootloader_. O _bootloader_ nada mais é que um pequeno programa que é encarregado de "chamar" o sistema operacional de um aparelho, seja ele um celular, um computador de mesa ou até mesmo um aparelho de TV moderno.

Como medida de segurança, dispositivos Android saem de fábrica com o _bootloader_ bloqueado. Portanto é necessário desbloquear para que possamos instalar um novo sistema operacional. Para isso, devemos acessar a página de suporte da Motorola. O endereço está [aqui](http://motorola-global-portal.custhelp.com/app/standalone/bootloader/unlock-your-device-a), É necessário fazer um cadastro e seguir os passos descritos nela.

Após fazer o cadastro, somos levados para uma tela com vários modelos listados. O modelo deste artigo, um Moto G4 Play, não está listado, portanto devemos clicar no primeiro link da página ou [aqui](https://motorola-global-portal.custhelp.com/app/standalone/bootloader/unlock-your-device-a/action/auth). Na próxima etapa, a Motorola irá avisar de todos os riscos envolvendo a desbloqueio do _bootloader_, apenas desça até o final e clique em "Next".

E finalmente chegamos onde queremos. Para que possamos prosseguir, o site pede um código específico do teu aparelho. Para isso, voltamos no terminal do PC e digitamos o seguinte comando _fastboot oem get_unlock_data_. O terminal vai responder com 5 linhas, todas elas iniciando com (bootloader) e um código logo após. Copiaremos apenas o código, retirando o _(bootloader)_ e o espaço e juntaremos as 5 linhas em uma só. Com esse código gigante em mãos, colaremos ele no campo apropriado do site da Motorola (no item 6). Após colarmos o código no campo, clique no botão azul que diz "Can my device be ubnlocked?" Se ele for elegível, na parte de baixo da página irá aparecer um botão azul "Request unlock key". Concordaremos com o contrato clicando em "I agree" e clicaremos no botão em questão.

Um email será enviado para o endereço do registro e irá conter o código de desbloqueio. Copie este código.

Volte ao terminal e digite _fastboot oem unlock CHAVE-ÚNICA_, substituindo _CHAVE-ÚNICA_ pela chave informada no email. Este código é caso-sensitivo, portanto, devemos respeitar as letras maiúsculas e minúsculas.

Se tudo der certo, o terminal responderá com uma mensagem dizendo que o aparelho foi desbloqueado (e na tela do aparelho também aparecerá a confirmação com os dizeres "Device is UNLOCKED" em amarelo).

## Instalando o arquivo de recuperação e o sistema operacional

Com o terminal aberto e estando na pasta onde está o arquivo de imagem do LineageOS (como disse anteriormente, é necessário um mínimo de conhecimento dos comandos do terminal), digite _fastboot flash recovery NOME-DO-ARQUIVO.img_ e dê enter. Subistitua NOME-DO-ARQUIVO pelo nome do arquivo que você baixou lá no início deste artigo.

Após a operação ser concluída, aperte o botão de _"volume baixo"_, vá até _Recovery_ e aperte o botão de _POWER_ para selecionar a opção. Uma tela semelhante a esta aparecerá (VER FOTO)

Desça até _Factory Reset_, então _Format data / factory reset_. Ele irá perguntar se vocês deseja realmente formatar o aparelho. Atenção. A partir daqui não tem volta. O aparelho será formatado e **tudo** dentro dele será apagado. Se concorda, clique em _Format data_.

Quando tudo tiver sido concluído (demora 3 segundos) a tela retornará para a opção _Facotry reset_. Volte para a tela incial clicando na setinha no canto superior esquedro.

Clique em _Apply update_ e em seguida _Apply from ADB_.

Retorne ao computador e no terminal digite _adb sideload NOME-DO-ARQUIVO.zip_. Aguarde carregar os dados para o celular. Demora cerca de 2 minutos para concluir a transferência.
A resposta do celular é FOTO e a do terminal é "Total xfer: 1.00x"

## Etapa opcional

Se vocês quiser ter os aplicativos da Google, além do suporte à _Play Store_, é hora de instalar o pacote [Open GApps](https://opengapps.org/). Para isso, siga até a página e selecione a versão correspondente. Neste caso marque as caixas ARM, Android 10.0 e escolha uma das opções os pacotes que irão vir junto. A opção padrão é a nano, que contém o mínimo para a Play Store funcionar e mais alguns extras. Baixe o arquivo e salve no PC.

No aparelho celular, clique novamente em _Apply update_ e em seguida _Apply from ADB_.

No terminal, navegue até a pasta onde foi feito o _download_ do instalador e digite _adb sideload NOME-DO-ARQUIVO.zip_. Demora cerca de 2 minutos para concluir a transferência.
A resposta do celular é FOTO e a do terminal é "Total xfer: 1.00x"

## Terminando a instalação

Volte na setinha até a tela inicial e clique em _Reboot system now_.

Pronto. O LineageOS está instalado no seu aparelho. Só desfrutar.

