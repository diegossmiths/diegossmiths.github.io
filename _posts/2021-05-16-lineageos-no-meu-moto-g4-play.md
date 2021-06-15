---
layout: post
title: LineageOS no Moto G4 Play
description: "O que é o LineageOS? Um pouco do sistema operacional móvel, seus recursos, sua história, vantagens e desvantagens"
keywords: lineageos, android, moto, g4, play, motorola, custom, rom
updated: 2021-06-11 22:30:00 -0300
---

> Anteriormente, na primeira versão escrita, havia um tutorial de como instalar o LineageOS no Moto G4 Play. Acontece que tutoriais deste tipo mudam bastante de modelo para modelo. Soma-se ao fato de que, conforme os desenvolvedores vão modificando o sistema os tutoriais oficiais também vão sendo atualizados. Baseado nisso, resolvi retirar o tutorial. Na página oficial da distribuição, todos os aparelhos contam com tutoriais oficiais.  Não tinha sentido eu fazer algo exatamente semelhante sendo que as únicas diferenças seriam a linguagem utilizada (lá inglês, aqui português) e a forma como foi escrito. Confesso que o meu parecia mais detalhado, mas mesmo assim resolvi retirar. Me sinto melhor assim.

## O que é o LineageOS?

O LineageOS é um sistema operacional gratuito e de código aberto para *smartphones*, *tablets* e *set-top boxes*. É desenvolvido e mantido por uma comunidade de programadores, *designers*, tradutores e demais pessoas que queiram ajudar no projeto. Ele é construído sobre a plataforma móvel Android.

O Android, por sua vez, é um *software* livre e também de código aberto desenvolvido internamente pela Google. Depois que todas as mudanças e atualizações de uma determinada versão foram feitas, o código fonte é aberto e lançado para a comunidade através do [AOSP](https://source.android.com/) (Android Open Source Project) num modelo chamado de [catedral](https://pt.wikipedia.org/wiki/A_Catedral_e_o_Bazar#Modelos_de_Desenvolvimento).

O que a comunidade do LineageOS faz é pegar o código fonte do Android liberado pela Google e adaptá-lo para os mais diferentes aparelhos com o objetivo de oferecer recursos e opções que não existiam na versão oficial distribuída pela fabricante ou estender a vida útil dos aparelhos através de um suporte de longo prazo. O *Privacy Guard*, recurso exclusivo, garante à você escolher de forma muito mais detalhada o que um aplicativo pode ou não fazer. Todas as dependências dos serviços da Google ficam de fora, assim como aquele monte de tralhas que as fabricantes e operadoras colocam, o que faz dele um sistema extremamente privativo, não invasivo e enxuto. Também é possível ter um controle muito maior das coisas todas. Temos a opção de instalar praticamente tudo o que queremos e desinstalar tudo o que não queremos.

A equipe de desenvolvimento costuma manter um cronograma de atualizações bastante eficiente e não é nada fora do comum termos novidades semanais. O processo de atualização é OTA (*over-the-air*), que é um método de distribuição de atualizações através da rede sem fio, portanto basta o aparelho estar conectado na *internet* para receber e instalar novos recursos e correções de segurança.

## Sua história

Em 2009 um sujeito chamado Steve Kondik começou um projeto com o nome de CyanogenMod. O CyanogenMod era um sistema operacional baseado no Android, totalmente de código aberto, **mantido por uma comunidade de desenvolvedores** e que tinha como objetivo manter aparelhos antigos atualizados. Já em 2013, com o avanço do projeto, um outro sujeito, este chamado Kirt McMaster se aproximou de Steve e juntos conseguiram levantar capital de investidores para fundar uma empresa chamada Cyanogen Inc. Ela passou a abrigar dois projetos, o já falado CyanogenMod e o CyanogenOS. CyanogenOS era o **braço comercial da empresa**. Ele era **desenvolvido por empregados** e era o que eles comercializavam junto à outras companhias, licenciando seu software para fabricantes de celulares interessadas. E este possuía mais partes do código que eram fechadas e patenteadas (incluindo aí o nome).

Já em 2016, Steve, percebeu que a empresa não estava atingindo o sucesso que ele almejava. Chegou o momento que ambos começaram a discordar dos rumos que deveriam ser seguidos, contratos ruins foram assinados e Kirt começou a soltar um monte de abobrinhas em entrevistas, o que começou a "pegar mal" para a empresa. Steve foi demitido do posto de CEO e uma grande reestruturação foi feita. A partir daí a coisa foi ladeira a baixo. A confusão toda começou em julho de 2016, e em dezembro tudo acabou.

A solução encontrada por Steve Kondik para que seu projeto não morresse com o fim da Cyanogen Inc. foi criar um *fork* do CyanogenMod. Aqui, um adendo: um *fork* nada mais é quando um desenvolvedor, ou um grupo deles, criam um projeto independente com base no código de outro projeto já existente, ou seja, eles pegam o código de um *software* que já existe e o modificam para adequar aos seus interesses, mesmo que o original, que serviu como base, ainda esteja ativo e em desenvolvimento. Assim, temos 2 *softwares* similares, com uma mesma base, mas que, com o tempo, tendem a tomar rumos diferentes.

Com o fim da Cyanogen Inc. e de seus projetos, nascia aí o LineageOS. No inglês, *lineage* significa "linhagem", isto é, uma série de gerações de uma família. A comunidade que já desenvolvia o CyanogenMod abraçou a causa e continuou seus serviços com o LineageOS, criando assim um legado.

Essa é a história contada de forma resumida.

## Minha opinião sobre

Fiz esse artigo com o objetivo de ajudar qualquer pessoa que queira se livrar, um pouco, das amarras da Google e das fabricantes, ficando livre para usar seu aparelho com uma liberdade muito maior. Também para dar uma vida nova àquele celular que todos temos atirado em algum canto da gaveta.

Do **ponto de vista de segurança**, tudo muito bom, um sistema operacional moderno e com atualizações semanais. Menos [*backdoors*](https://pt.wikipedia.org/wiki/Backdoor) também.

Do **ponto de vista da usabilidade**, quase perfeito. Todos os recursos funcionam super bem. Câmera, GPS, Bluetooth... Inclusive agora o LED frontal que indica o carregamento da bateria também passou a funcionar. Falando nela, notei que a bateria começou a durar mais. Usando uma bateria nova (e original) que recém comprei, ele chegou a aguentar 9 dias longe da tomada. Claro que o tempo de uso é bem baixo, pouco mais de 3 horas de tela, mas ainda assim mostra a eficiência energética do LineageOS, mesmo com os serviços da *Play Store* rodando ao fundo.

Optei por instalar o Open GApps. O Open GApss é uma compilação dos aplicativos e serviços da Google para a instalação em um aparelho qualquer. Dessa maneira, o resultado final será um sistema operacional muito semelhante ao encontrado nos telefones vendidos por aí, contando com a *Play Store*, *Gmail*, *Maps*, *Drive*, etc. Ele permitiu uma compatibilidade muito grande com aplicativos de terceiros. Testei o aplicativo do Banco do Brasil e do Banco Inter, meus únicos dois bancos, e ambos executaram sem nenhum problema. WhatsApp, também. Não testei aplicativos como o Spotify e Nubank, mas creio que também funcionarão. Apesar de não ter testado, sei que Netflix **não** funciona (e nem me fará falta). Algum outro também pode não funcionar, principalmente os de bancos.

Agora, do **ponto de vista da privacidade** temos um problema, pois, ao ganharmos usabilidade com o Open GApss, perdemos privacidade, visto que é necessário termos uma conta Google para poder ter acesso ao ecossistema Android. Com isso, nossos passos voltam a ser rastreados e novamente somos usados como mercadorias. É uma faca de dois gumes.

Enfim, colocando tudo na balança, na minha opinião a instalação do LineageOS vale a pena.  Temos um sistema operacional moderno que permite inúmeros novos recursos, mais segurança e muito mais privacidade, tudo rodando de forma bastante satisfatória num aparelho antigo e fraco. O uso do Open GApps é quase imprescindível para a maioria das pessoas.

Se ficou alguma dúvida, por favor, entre em contato diretamente comigo através do meu *e-mail*. Ele pode ser acessado no rodapé da página clicando no ícone envelope.

Obrigado. =]

