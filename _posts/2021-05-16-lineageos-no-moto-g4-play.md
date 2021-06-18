---
layout: post
title: LineageOS no Moto G4 Play
description: "O que é o LineageOS? Um pouco do sistema operacional móvel, seus recursos, sua história, vantagens e desvantagens."
keywords: lineageos, android, moto, g4, play, motorola, custom, rom
date: 2021-05-16 08:35:19 -0300
updated: 2021-06-17 21:27:00 -0300
---

> Anteriormente, na primeira versão escrita, havia um tutorial de como instalar o LineageOS no [Moto G4 Play](https://www.gsmarena.com/motorola_moto_g4_play-8104.php#xt16030). Acontece que tutoriais deste tipo podem ser bastante diferentes dependendo do modelo de aparelho. Soma-se ao fato de que, conforme os desenvolvedores vão modificando o sistema os tutoriais oficiais também vão sendo atualizados. Baseado nisso, resolvi retirar o meu. Na página oficial da distribuição, todos os aparelhos contam com tutoriais oficiais.  Não tinha sentido eu fazer algo semelhante sendo que as únicas diferenças seriam a linguagem utilizada (lá inglês, aqui português) e a forma como foram escritos. Confesso que o meu parecia mais detalhado, mas mesmo assim resolvi retirar. Me sinto melhor assim.

## O que é o LineageOS?

O [LineageOS](https://lineageos.org/) é um sistema operacional gratuito e de código aberto para *smartphones*, *tablets* e *set-top boxes*. É desenvolvido e mantido por uma comunidade de programadores, *designers*, tradutores e demais pessoas que queiram ajudar no projeto. Ele é construído sobre a plataforma móvel Android.

O Android, por sua vez, é um *software* livre e também de código aberto desenvolvido internamente pela Google. Depois que todas as mudanças e atualizações de uma determinada versão foram feitas, o código fonte é aberto e lançado para a comunidade através do [AOSP (Android Open Source Project)](https://source.android.com/) num modelo chamado de [catedral](https://pt.wikipedia.org/wiki/A_Catedral_e_o_Bazar#Modelos_de_Desenvolvimento).

O que a comunidade do LineageOS faz é pegar o código fonte do Android liberado pela Google e adaptá-lo para os mais diferentes aparelhos com o objetivo de oferecer recursos e opções que não existiam na versão oficial distribuída pela fabricante ou estender a vida útil dos aparelhos através de um suporte de longo prazo. O *Privacy Guard*, recurso exclusivo, garante à você escolher de forma muito mais detalhada o que um aplicativo pode ou não fazer. Todas as dependências dos serviços da Google ficam de fora, assim como aquele monte de tralhas que as fabricantes e operadoras colocam, o que faz dele um sistema extremamente privativo, não invasivo e enxuto. Também é possível ter um controle muito maior das coisas todas. Temos a opção de instalar praticamente tudo o que queremos e desinstalar tudo o que não queremos.

A equipe de desenvolvimento costuma manter um cronograma de atualizações bastante eficiente e não é nada fora do comum termos novidades semanais. O processo de atualização é OTA (*over-the-air*), que é um método de distribuição de atualizações através da rede sem fio, portanto basta o aparelho estar conectado na *internet* para receber e instalar novos recursos e correções de segurança.

## Sua história

Em 2009 um sujeito chamado Steve Kondik começou um projeto com o nome de CyanogenMod. O CyanogenMod era um sistema operacional baseado no Android, totalmente de código aberto, **mantido por uma comunidade de desenvolvedores** e que tinha como objetivo manter aparelhos antigos atualizados. Já em 2013, com o avanço do projeto, um outro sujeito, este chamado Kirt McMaster se aproximou de Steve e juntos conseguiram levantar capital de investidores para fundar uma empresa chamada Cyanogen Inc. Ela passou a abrigar dois projetos, o já falado CyanogenMod e o CyanogenOS. CyanogenOS era o **braço comercial da empresa**. Ele era **desenvolvido por empregados** e era o que eles comercializavam junto à outras companhias, licenciando seu software para fabricantes de celulares interessadas. E este possuía mais partes do código que eram fechadas e patenteadas (incluindo aí o nome).

Já em 2016, Steve, percebeu que a empresa não estava atingindo o sucesso que ele almejava. Chegou o momento que ambos começaram a discordar dos rumos que deveriam ser seguidos, contratos ruins foram assinados e Kirt começou a soltar um monte de abobrinhas em entrevistas, o que começou a "pegar mal" para a empresa. Steve foi demitido do posto de CEO e uma grande reestruturação foi feita. A partir daí a coisa foi ladeira a baixo. A confusão toda começou em julho de 2016, e em dezembro tudo acabou.

A solução encontrada por Steve Kondik para que seu projeto não morresse com o fim da Cyanogen Inc. foi criar um *fork* do CyanogenMod. Aqui, um adendo: um *fork* nada mais é quando um desenvolvedor, ou um grupo deles, criam um projeto independente com base no código de outro projeto já existente, ou seja, eles pegam o código de um *software* que já existe e o modificam para adequar aos seus interesses, mesmo que o original, que serviu como base, ainda esteja ativo e em desenvolvimento. Assim, temos 2 *softwares* similares, com uma mesma base, mas que, com o tempo, tendem a tomar rumos diferentes.

Com o fim da Cyanogen Inc. e de seus projetos, nascia aí o LineageOS. No inglês, *lineage* significa "linhagem", isto é, uma série de gerações de uma família. A comunidade que já desenvolvia o CyanogenMod abraçou a causa e continuou seus serviços com o LineageOS, criando assim um legado.

Essa é a história contada de forma resumida.

## Minha opinião sobre

Para que eu possa dar minha opinião, temos que entrar um pouquinho no campo técnico da coisa.

Nativamente, o LineageOS é quase o Android puro (também chamado de *Android Vanilla*), isto é, ele **não** inclui o famoso *Google Mobile Services*, que contém os [aplicativos desenvolvidos pela Google](https://play.google.com/store/apps/dev?id=5700313618786177705) (*Play Store*, *Gmail*, *Maps*, *Drive*, *Youtube*, etc) e muitas [bibliotecas proprietárias](https://pt.wikipedia.org/wiki/Biblioteca_(computa%C3%A7%C3%A3o)). De forma bem resumida, bibliotecas são pequenos programas que tem como função auxiliar programadores em seus projetos, fazendo com que partes nativas de um sistema sejam integrados aos seus programas. Um exemplo para deixar mais claro. Um programador deseja que o usuário importe uma foto para dentro do seu programa. Ele não precisa escrever o código da janela que será aberta para que o usuário navegue entre pastas e escolha a imagem. Para isso, o desenvolvedor chama uma biblioteca do sistema que se encarrega de mostrar a janela e enviar para seu *software* a foto escolhida. Este método, além de deixar as coisas mais fáceis para o programador, deixa seu *software* mais coeso com o sistema onde está rodando, tanto em termos visual quanto funcional. No *Windows* são os famosos `.dll` e `.lib`, nos sistemas *Unix-like* são os arquivos `.a` e `.so`.

No caso das bibliotecas proprietárias da Google, elas não fazem parte do sistema operacional em si. Como já foi dito, o Android é um sistema de código aberto, mas as bibliotecas da Google são de código fechado. É nesse ponto que a Google ganha (ainda mais) dinheiro. Acontece que grande parte dos aplicativos para Android faz uso extenso destas bibliotecas, e se uma fabricante opta por não licenciá-las ela irá vender um aparelho no qual não será possível ao usuário instalar a maioria dos aplicativos "famosos" (dentre eles Facebook, Instagram, WhatsApp, Snapchat entre outros). Por exemplo, aplicativos como Uber, 99, Strava, Garmin Connect usam e abusam das bibliotecas de localização e mapas (onde o *Maps* é baseado). Se as bibliotecas da Google não estiverem presentes estes aplicativos não funcionam, alguns nem abrem. E isso vale para vários outros, também. As notificações do sistema sequer funcionam sem o *GMS* presente. Para tentar contornar isso, existem dois projetos que são mantidos pela comunidade.

O pimeiro é o [microG](https://microg.org/). Surgido em 2017, ele já contou com apoio financeiro da [PrototypeFund](https://prototypefund.de/project/microg/), um fundo de incentivo do [Bundesministerium für Bildung und Forschung (Ministério Federal de Educação e Pesquisa da Alemanha)](https://www.bmbf.de/en/index.html). Atualmente é patrocinado pela [/e/ Foundation](https://e.foundation). O projeto tem como objetivo reimplementar, em código aberto, os principais serviços proprietários da Google fazendo com que de forma alguma dependam de seus servidores. Provê somente os pacotes necessários para que aplicativos de terceiros funcionem de maneira correta (sistema de telemetria, de notificações, etc). O projeto ainda é bastante imaturo e não raramente acontecem problemas de compatibilidade. Por ser um aparelho que iria compartilhar com meu irmão, e sabendo o quanto ele é atrapalhado com esse tipo de coisa, optei por não utilizar o microG.

A segunda saída é o [Open GApps](https://opengapps.org/). Ele é uma compilação dos aplicativos e serviços oficiais da Google para a instalação em um aparelho qualquer. Apesar dos aplicativos serem os oficiais da Google, de código fechado e de propriedade da empresa, o *open* do nome vem do *script* utilizado para a criação do pacote de instalação, *script* este de código aberto. Com o Open GApps, podemos escolher quais pacotes instalar, desde o básico até o pacote completo dos aplicativos da Google. Dessa maneira, o resultado final será um sistema operacional muito semelhante ao encontrado nos telefones vendidos por aí, podendo contar com a *Play Store*, *Gmail*, *Maps*, *Drive*, etc. Optei por instalar o *Open GApps* (variante Nano) no aparelho da empresa.

Agora, com a parte técnica explicada, vamos para a minha breve análise do **LineageOS 17.1 + Open GApps**.

Do **ponto de vista de segurança**, melhor do que a instalação original da Motorola. Com o LineageOS passei a ter um sistema operacional mais moderno e com atualizações semanais. Os (poucos) entulhos que a Motorola havia posto no sistema original ficaram de fora. Algumas [*backdoors*](https://pt.wikipedia.org/wiki/Backdoor) também foram fechadas com isso.

Do **ponto de vista da usabilidade**, quase perfeito. Todos os recursos funcionam super bem. Câmera, GPS, Bluetooth... Inclusive agora o LED frontal que indica o carregamento da bateria também passou a funcionar. Falando nela, notei que a bateria começou a durar mais. Usando uma bateria nova (e original) recém comprada, ele chegou a aguentar 9 dias longe da tomada. Claro que o tempo de uso é bem baixo, pouco mais de 3 horas de tela, mas ainda assim mostra a eficiência energética do LineageOS, mesmo com os serviços da *Google Mobile Services* rodando ao fundo.

A instalação do *Open GApps*, me permitiu uma compatibilidade muito grande com aplicativos de terceiros. Testei o aplicativo do Banco do Brasil e do Banco Inter, meus únicos dois bancos, e ambos executaram sem nenhum problema. WhatsApp e Instagram, também. Não testei aplicativos como o Spotify e Nubank, mas creio que também funcionarão. Apesar de não ter testado, sei que Netflix **não** funciona (e nem me fará falta). Outros também podem não funcionar, principalmente alguns de bancos e que caiam no problema de exibição de mídias com direitos autorais.

Agora, do **ponto de vista da privacidade** temos um problema, pois, ao ganharmos usabilidade com o *Open GApps*, perdemos privacidade, visto que é necessário termos uma conta Google para poder ter acesso ao ecossistema do Android. Com isso, nossos passos voltam a ser rastreados e novamente somos usados como mercadorias. É uma faca de dois gumes.

Enfim, colocando tudo na balança, na minha opinião a instalação do LineageOS vale a pena. Temos um sistema operacional moderno que permite inúmeros novos recursos, mais segurança e muito mais privacidade (desde que não seja instalado com o Open GApps). Tudo rodando de forma bastante satisfatória num aparelho antigo e fraco. O uso do Open GApps é quase imprescindível para a maioria das pessoas.

Num futuro próximo, pretendo instalar no meu [Moto X4](https://www.gsmarena.com/motorola_moto_x4-8634.php#xt1900-6) o LineageOS 18.1 (baseado no Android 11) com o microG. Quando fizer, irei escrever outro artigo.

Se ficou alguma dúvida, por favor, entre em contato diretamente comigo através do meu *e-mail*. Ele pode ser acessado no rodapé da página clicando no ícone envelope.

Obrigado. =]

