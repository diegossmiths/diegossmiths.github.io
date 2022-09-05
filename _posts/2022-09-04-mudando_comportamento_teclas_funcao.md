---
layout: post
title: Teclas de função + Fedora + MacBook
description: Mudando o comportamento das teclas de função do MacBook rodando Fedora 36.
keywords: fn, teclas, função, macbook, fedora
date: 2022-09-04 21:30:00 -0300
---

Recentemente meu computador, conhecido carinhosamente por Noah (ou Noé, em português) veio a falecer. A placa-mãe, que já não andava muito bem, resolveu não "andar" mais. Com isso fiquei sem PC...

Eis que minha salvação estava bem aqui em casa. Minha namorada tinha um MacBook Pro guardado na gaveta, ela não usava mais por achar ele muito grande (modelo de 13"). Pedi emprestado e ela prontamente cedeu ele para mim. Retirei o SSD e coloquei o meu no lugar.

Formatei a máquina com o Fedora 36. Tudo ocorreu de forma tranquila, com excessão do adapatador wi-fi, o que já era esperado e foi facilmente resolvido.

Eis que eu estava tranquilamente trabalhando, quando em um determinado momento tento renomear um arquivo apertando F2. E o que acontece? O brilho da tela aumenta. Ok, ok... já sei, terei que apertar a tecla "fn" para poder ter as teclas de função ativas novamente. Mas eu detesto isso, prefiro ter as teclas F[1-12] como padrão e quando quiser que elas sirvam como teclas de controle aperto "fn", isto é, o inverso da configuração nativa.

E o que fazer para desativá-las e retornar ao padrão? Segue o tutorial:

1. Em primeiro lugar, para alterar estes parâmetros na seção ativa, digite:

´´´sudo nano /sys/module/hid_apple/parameters/fnmode´´´

Com isso o arquivo de configuração das teclas fn dos dispositivos Apple irá abrir através do Nano.
Dentro do arquivo troque o número 1 (padrão) para o número 2.

O numero 1 significa que as teclas agem como teclas de controle. O número 2 significa que as teclas agem como funções. Se colocarmos o número 0 desativaremos as teclas.

Depois disso, para que essa configuração fique salva como padrão na máquina, deveremos gravar estas opções dentro do arquivo ´´´/etc/modprobe.d/hid_apple.conf´´´

Como o arquivo não existe, criaremos ele. Digite:

´´´sudo > /etc/modprobe.d/hid_apple.conf´´´

O caracter > faz com que um arquivo vazio seja gerado.

Logo após, abra o arquivo:

´´´sudo nano /etc/modprobe.d/hid_apple.conf´´´

E adicione a seguinte linha:

´´´options hid_apple fnmode=2´´´

Logo após devemos gravar no initramfs com o comando:

´´´sudo update-initramfs -u (Ubuntu)
sudo dracut --regenerate-all --force´´´

