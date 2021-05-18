---
layout: post
title: Vamos falar sobre LineageOS
description: "O que é o LineageOS? Conheça um pouco do sistema operacional móvel, seus recursos, sua história e saiba como usá-lo."
keywords: lineageos, android, moto, g4, play, motorola, custom, rom
updated: 2021-05-17 23:05:00 -0300
---

## O que é o LineageOS?

O LineageOS é um sistema operacional gratuito e de código aberto para *smartphones*, *tablets* e *set-top boxes*. É desenvolvido e mantido por uma comunidade de programadores, *designers*, tradutores e demais pessoas que queiram ajudar no projeto. Ele é construído sobre a plataforma móvel Android.

O Android, por sua vez, é um *software* livre e também de código aberto desenvolvido internamente pela Google. Depois que todas as mudanças e atualizações de uma determinada versão foram feitas, o código fonte é aberto e lançado para a comunidade através do [AOSP](https://source.android.com/) (Android Open Source Project) num modelo chamado de [catedral](https://pt.wikipedia.org/wiki/A_Catedral_e_o_Bazar#Modelos_de_Desenvolvimento).

O que a comunidade do LineageOS faz é pegar o código fonte do Android liberado pela Google e adaptá-lo para os mais diferentes aparelhos com o objetivo de oferecer recursos e opções que não existiam na versão oficial distribuída pela fabricante ou estender a vida útil dos aparelhos através de um suporte de longo prazo. O *Privacy Guard*, recurso exclusivo, garante à você escolher de forma muito mais detalhada o que um aplicativo pode ou não fazer. Todas as dependências dos serviços da Google ficam de fora, assim como aquele monte de tralhas que as fabricantes e operadoras colocam, o que faz dele um sistema extremamente privativo, não invasivo e enxuto. Também é possível ter um controle muito maior das coisas todas. Temos a opção de instalar praticamente tudo o que queremos e desinstalar tudo o que não queremos.

A equipe de desenvolvimento costuma manter um cronograma de atualizações bastante eficiente e não é nada fora do comum termos novidades semanais. O processo de atualização é OTA (*over-the-air*), que é um método de distribuição de atualizações através da rede sem fio, portanto basta o aparelho estar conectado a *internet* para receber e instalar novos recursos e correções de segurança.

## Sua história

Em 2009 um sujeito chamado Steve Kondik começou um projeto chamado CyanogenMod. O CyanogenMod era um sistema operacional baseado no Android, totalmente de código aberto, **mantido por uma comunidade de desenvolvedores** e que tinha como objetivo manter aparelhos antigos atualizados. Já em 2013, com o avanço do projeto, um outro sujeito, este chamado Kirt McMaster se aproximou de Steve e juntos conseguiram levantar capital de investidores para fundar uma empresa chamada Cyanogen Inc. Ela passou a abrigar dois projetos, o já falado CyanogenMod e o CyanogenOS. CyanogenOS era o **braço comercial da empresa**. Ele era **desenvolvido por empregados** e era o que eles comercializavam junto à outras companhias, licenciando seu software para fabricantes de celulares interessadas. E este possuía mais partes do código fechadas e patenteadas (incluindo aí o nome).

Já em 2016, Steve, na sua visão, percebeu que a empresa não estava atingindo o sucesso que ele vislumbrava. Chegou o momento que ambos começaram a discordar dos rumos que deveriam ser seguidos, contratos ruins foram assinados e McMaster começou a soltar um monte de abobrinhas em entrevistas, o que começou a "pegar mal" para a empresa. Steve foi demitido do posto de CEO e uma grande reestruturação foi feita. A partir daí a coisa foi ladeira a baixo. A confusão toda começou em julho de 2016, e em dezembro tudo acabou.

A solução encontrada por Kondik para que seu projeto não morresse com o fim da Cyanogen Inc. foi criar um *fork* do CyanogenMod. Aqui, um adendo: um *fork* nada mais é quando um desenvolvedor, ou um grupo deles, criam um projeto independente com base no código de outro projeto já existente, ou seja, eles pegam o código de um *software* que já existe e o modificam para adequar aos seus interesses, mesmo o que original, que serviu como base, ainda esteja ativo e em desenvolvimento. Assim, temos 2 *softwares* similares, com uma mesma base, mas que, com o tempo, tendem a tomar rumos diferentes.

Com o fim da Cyanogen Inc. e de seus projetos, nascia aí o LineageOS. No inglês, *lineage* significa "linhagem", isto é, uma série de gerações de uma família. A comunidade que já desenvolvia o CyanogenMod abraçou a causa e continuou seus serviços com o LineageOS. Assim, donos de aparelhos legados, deixados a ver navios pelas fabricantes, conseguiriam manter seus sistemas atualizados.

Essa é a história contada de forma resumida.

Agora que já sabemos de fato o que é o LineageOS e como ele surgiu, vamos instalá-lo em um aparelho.

## Notas

Antes de mais nada, gostaria de dizer que este manual foi escrito entre os dias **18 de abril e 16 de maio de 2021**. Portanto, algumas coisas podem estar diferentes na data que você estiver lendo. Por isso é importante acessar a [página oficial](https://lineageos.org/) do projeto. Ali, é possível encontrar todos os aparelhos mantidos pela comunidade, assim como tutoriais (como este, mas em inglês), os instaladores e notas de cada versão lançada. Verifique se seu aparelho consta na lista dos compatíveis.

Neste exemplo, usarei o [Motorola Moto G4 Play](https://www.gsmarena.com/motorola_moto_g4_play-8104.php) como base. É um aparelho que foi lançado em agosto de 2016, possui um processador de baixo custo e relativamente pouca memória RAM. Utilizava-o para uso pessoal, mas comprei um aparelho novo e deixei este exclusivamente para a marcenaria. Para outras marcas e modelos podem haver algumas diferenças, mas se houver, será muito pouca coisa. No computador de mesa, utilizo o [elementaryOS](https://elementary.io/) versão 5.1.7, um sistema GNU/Linux baseado no [Ubuntu](https://ubuntu.com/) versão 18.04.4 LTS.

É interessante também que você tenha uma noção de como funciona um terminal, neste caso o [*bash*](https://pt.wikipedia.org/wiki/Bash).

Nunca, em nenhum momento, desconecte o cabo USB do computador durante o processo.

Apenas deixando claro que, ao instalar o LineageOS a **garantia será perdida**. Além disso, **eu não me responsabilizo por qualquer dano ao seu aparelho**. Tudo será por sua conta e risco.

E lembrando que **tudo será apagado permanentemente**. Portanto, faça backup de todos os dados que você deseja.

Se você concordar com tudo o que foi dito até aqui, siga em frente.

## Processo de instalação
1. [Preparando o aparelho](#preparando)
2. [Baixando o necessário](#baixando)
3. [Instalando o adb-fastboot](#fastboot)
4. [Desbloqueando o bootloader](#bootloader)
5. [Instalando o arquivo de recuperação e o sistema operacional](#instalando_os)
6. [Etapa opcional - Instalando o Open GApss](#opengapps)
7. [Terminando a instalação](#terminando)

## Preparando o aparelho {#preparando}

Como disse anteriormente, este documento é baseado no Moto G4 Play. Antes de mais nada, ele deve estar rodando o Android na versão 7.1.1. Para verificar, vá em "*Configurações -> Sobre o dispositivo*" e cheque a versão do sistema. Se não estiver, faça a atualização junto a Motorola. É possível achar a opção nas configurações do aparelho em "*Configurações -> Sobre o dispositivo -> Atualização do sistema*".

Feito, devemos ativar o "*Modo desenvolvedor*". Para isso, volte em "*Configurações -> Sobre o dispositivo*" e clique **7 vezes** sobre "*Número da versão*". Quando for o suficiente, uma *pop-up* aparecerá indicando que o modo foi habilitado.

Volte para o menu anterior e veja que agora apareceu um item novo chamado "*Programador*". Clique nele.

Dentro deste menu, role a página até chegar na sessão "*Depuração*". Habilite a opção "*Depuração USB*".

Pronto, o aparelho já está pronto para receber o LineageOS.

## Baixando o necessário {#baixando}

Antes de mais nada, eu recomendo ao leitor criar uma pasta chamada *Lineage* dentro da sua pasta de documentos. Você irá baixar e salvar ali todos os arquivos necessários para o procedimento e os manterá de forma organizada.

Na página oficial do [LineageOS](https://download.lineageos.org/), navegue entre os aparelhos mantidos pela comunidade e escolha o seu. Sempre é mostrada na primeira linha da tabela a versão mais nova do sistema. Ali, baixe os **dois** arquivos necessários para a instalação, um arquivo *.zip* e a imagem de recuperação *.img* correspondente.

É também necessário baixar o *adb-fastboot*. O ADB, sigla para *Android Debug Bridge*, e o *fastboot* são ferramentas presentes no *Android SDK Platform Tools*, desenvolvidas pela Google para facilitar a comunicação entre um PC e um aparelho Android. O ADB é uma ferramenta de linha de comando para instalar, desinstalar, depurar aplicativos, transferir arquivos e acessar o console de um dispositivo. O *fastboot* é um protocolo de comunicação e uma ferramenta de mesmo nome que tem o objetivo modificar o sistema de arquivos de um aparelho Android via conexão USB.

Como disse anteriormente, esse tutorial é feito para computadores rodando GNU/Linux, mais precisamente sistemas baseados no Debian/Ubuntu. Portanto, baixemos o arquivo mais recente disponibilizado pela Google [neste link](https://dl.google.com/android/repository/platform-tools-latest-linux.zip).

Apenas lembrando que o LineageOS não possui os aplicativos da Google, portanto, se você quiser ter a *Play Store, Gmail, Maps, Drive* ou qualquer outro programa desenvolvido pela empresa é necessário baixar o pacote [Open GApps](https://opengapps.org/). Para isso, siga até a página oficial do projeto (link acima) e selecione a versão desejada. Neste caso marque as caixas ARM, Android 10.0 e escolha em uma das opções os pacotes que irão vir junto. A opção padrão é a nano, que contém o mínimo para a *Play Store* funcionar e mais alguns extras. Baixe o arquivo e salve no PC. Existem outras opções além do Open GApps, mas ficaremos com esta.

Pronto, já reunimos todo o material necessário.

## Instalando o adb-fastboot {#fastboot}

Clique no *platform-tools-lateste-linux.zip* e faça a extração dos arquivos num diretório a sua escolha. Eu recomendo criar um diretório chamado *adb-fastboot* dentro da *home* do seu usuário. Feito, adicione o seguinte comando no terminal:

```
if [ -d "$HOME/adb-fastboot/platform-tools" ] ; then
export PATH="$HOME/adb-fastboot/platform-tools:$PATH"
fi
```

Após concluir, saia e entre novamente em sua conta para que as variáveis adicionadas sejam carregadas no sistema. Não é preciso reiniciar o computador.

É necessário também configurar as regras do *udev*. O *udev* é um administrador de dispositivos para Linux, isto é, é ele o responsável por detectar e montar todos os dispositivos que ligamos no PC. Para simplificar as coisas, simplesmente copie e cole cada um destes comandos no terminal:

```
git clone https://github.com/M0Rf30/android-udev-rules.git
cd android-udev-rules
sudo cp -v 51-android.rules /etc/udev/rules.d/51-android.rules
sudo chmod a+r /etc/udev/rules.d/51-android.rules
groupdel adbusers
sudo mkdir -p /usr/lib/sysusers.d/ && sudo cp android-udev.conf /usr/lib/sysusers.d/
sudo systemd-sysusers
sudo usermod -a -G adbusers $(whoami)
sudo udevadm control --reload-rules
sudo service udev restart
adb kill-server
```

Agora, ligue seu celular no PC através de um cabo USB. Feito isto, digite `adb devices`.

Uma caixa de diálogo aparecerá no seu celular perguntando se você deseja permitir a depuração pelo computador. Marque a caixa "*Sempre permitir a partir deste computador*" e clique em "*Ok*". Você verá a identificação do seu dispositivo.

Volte no terminal e digite `adb reboot bootloader` para carregar as opções de desenvolvedor do Android. O aparelho vai entrar numa tela preta com informações do *hardware*.

Digite `fastboot devices` e o terminal deverá responder com o código do aparelho. Se aparecer o código, significa que está tudo funcionando da maneira correta. Sigamos.

### Desbloqueando o bootloader {#bootloader}

Para podermos instalar o LineageOS, devemos desbloquear o *bootloader*. O *bootloader* nada mais é que um pequeno programa que é encarregado de "chamar" o sistema operacional quando um aparelho eletrônico é ligado, seja ele um celular, um computador de mesa ou até mesmo um aparelho de TV moderno.

Como medida de segurança, dispositivos Android saem de fábrica com o *bootloader* bloqueado. Portanto é necessário desbloquear para que possamos instalar um novo sistema operacional. Este procedimento varia de fabricante para fabricante, portanto você terá que pesquisar como proceder para desbloquear o seu aparelho.

No caso da Motorola, devemos acessar a página de suporte. O endereço está [aqui](http://motorola-global-portal.custhelp.com/app/standalone/bootloader/unlock-your-device-a), É necessário fazer um cadastro e seguir os passos descritos nela.

Após fazer o cadastro, somos levados para uma tela com vários modelos listados. O modelo deste artigo, um Moto G4 Play, não está listado, portanto devemos clicar no primeiro link da página ou [aqui](https://motorola-global-portal.custhelp.com/app/standalone/bootloader/unlock-your-device-a/action/auth). Na próxima etapa, a Motorola irá avisar de todos os riscos envolvendo a desbloqueio do *bootloader*, apenas desça até o final e clique em "*Next*".

E finalmente chegamos onde queremos. Para que possamos prosseguir, a página pede um código específico do aparelho. Para isso, voltamos no terminal do PC e digitamos o seguinte comando `fastboot oem get_unlock_data`. O terminal vai responder com 5 linhas, todas elas iniciando com *(bootloader)* e um código logo após. Copiaremos apenas o código, retirando o *(bootloader)* e o espaço e juntaremos as 5 linhas em uma só. Com esse código gigante em mãos, colaremos ele no campo apropriado da página da Motorola (no item 6). Após colocarmos o código completo no campo, clique no botão azul que diz "*Can my device be unlocked?*" Se ele for elegível, na parte de baixo da página irá aparecer um botão azul "*Request unlock key*". Concordaremos com o contrato clicando em "*I agree*" e clicaremos no botão em questão.

Um e-mail será enviado para o endereço do registro e irá conter o código de desbloqueio. Copie este código.

Volte ao terminal e digite `fastboot oem unlock CHAVE-ÚNICA`, substituindo *CHAVE-ÚNICA* pela chave informada no e-mail. Este código é caso sensitivo, portanto, devemos respeitar as letras maiúsculas e minúsculas.

Se tudo der certo, o terminal responderá com uma mensagem dizendo que o aparelho foi desbloqueado (e na tela do aparelho também aparecerá a confirmação com os dizeres "*Device is UNLOCKED*" em amarelo).

## Instalando o arquivo de recuperação e o sistema operacional {#instalando_os}

Com o terminal aberto, navegue até a pasta onde está o arquivo de imagem do LineageOS (como disse anteriormente, é necessário um mínimo de conhecimento dos comandos do terminal), digite `fastboot flash recovery NOME-DO-ARQUIVO.img` e dê enter. Substitua *NOME-DO-ARQUIVO* pelo nome do arquivo *.img* que você baixou lá no início deste artigo.

Após a operação ser concluída, pegue o aparelho, e através dos  botões laterais, navegue pelas opções apertando <kbd>Volume -</kbd> e <kbd>Volume +</kbd>, vá até "*Recovery*" e aperte o botão <kbd>Ligar/Desligar</kbd> para selecionar uma opção.

Desça até "*Factory Reset*", então "*Format data / factory reset*". Ele irá perguntar se você deseja realmente formatar o aparelho. **Atenção**. A partir daqui não tem volta. O aparelho será formatado e **tudo** dentro dele será apagado. Se concorda, clique em *Format data*.

Quando tudo tiver sido concluído (demora 3 segundos) a tela retornará para a opção "*Factory reset*". Volte para a tela inicial clicando na setinha no canto superior esquerdo.

Clique em "*Apply update*" e em seguida "*Apply from ADB*".

Retorne ao computador e no terminal digite `adb sideload NOME-DO-ARQUIVO-LINEAGEOS.zip`. Substitua *NOME-DO-ARQUIVO-LINEAGEOS* pelo nome do arquivo *.zip* que você baixou lá no início deste artigo. Aguarde carregar os dados para o celular. Demora cerca de 2 minutos para concluir a transferência.

A resposta do terminal é "*Total xfer: 1.00x*".

## Etapa opcional - Instalando o Open GApss {#opengapps}

Se você desejar continuar nas garras do Google, siga estes passos para instalar o Open GApss. No aparelho celular, clique novamente em "*Apply update*" e em seguida "*Apply from ADB*".

No terminal, na pasta onde foi feito o *download* do instalador, digite `adb sideload NOME-DO-ARQUIVO-OPENGAPPS.zip`. Substitua *NOME-DO-ARQUIVO-OPENGAPPS* pelo nome do arquivo *.zip* que você baixou lá no início deste artigo. Demora cerca de 2 minutos para concluir a transferência.

A resposta do terminal é novamente "*Total xfer: 1.00x*".

## Terminando a instalação {#terminando}

No aparelho celular, volte na setinha até a tela inicial e clique em "*Reboot system now*".

Pronto. Agora é só esperar o sistema reiniciar. O LineageOS está instalado no seu aparelho.

## Conclusão

Fiz esse artigo com o objetivo de ajudar a qualquer um que queira se livrar das amarras da Google e das fabricantes, ficando livre para usar seu aparelho com uma liberdade muito maior. Também para dar uma vida nova àquele celular que todos temos atirado em algum canto da gaveta.

Notei que a bateria do meu aparelho começou a durar um pouco mais. Apesar da sua idade, ela chega tranquilamente a 4 ou 5 dias. Reconheço que o uso é mínimo, mas mesmo assim o Android original que vinha de fábrica durava exatamente isso quando a bateria era nova.

Além disso, todos os recursos funcionam perfeitamente. Câmera, GPS, Bluetooth... Inclusive agora o LED frontal que indica carregamento da bateria também passou a funcionar. Alguns aplicativos de bancos podem não funcionar devido ao sistema não ser o original do aparelho. Testei o do Banco do Brasil e do Banco Inter, meus únicos dois bancos, e ambos executam sem nenhum problema. Não testei aplicativos como o Netflix, Spotify e Nubank.

Enfim, na minha opinião a instalação do LineageOS vale muito a pena. Temos um sistema operacional moderno que permite inúmeros novos recursos, mais segurança e muito mais privacidade, tudo rodando de forma bastante satisfatória num aparelho antigo e fraco.

Se ficou alguma dúvida, por favor, entre em contato diretamente comigo através do meu *e-mail*. Ele pode ser acessado no rodapé da página clicando no ícone envelope.

Obrigado. =]
