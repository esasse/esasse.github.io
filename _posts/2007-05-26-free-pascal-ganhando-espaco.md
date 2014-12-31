---
title: Free Pascal ganhando espaço
author: Erick Sasse
layout: post
permalink: /free-pascal-ganhando-espaco/
dsq_thread_id:
  - 262150077
categories:
  - Delphi
  - Free Pascal
  - Geral
  - Open Source
  - RemObjects
tags:
  - Geral
---
Provavelmente você já ouviu falar do [Free Pascal][1]. Acho que nunca comentei sobre ele aqui. É um compilador Pascal open source que suporta várias plataformas. Intel x86, Amd64/x86_64, PowerPC, Sparc. Linux, FreeBSD, Mac OS, DOS, Win32, OS/2, Netware e MorphOS. Impressionante, não?

Eu já tinha ouvido falar muito em FPC, mas nunca me interessei de verdade. Porém, aos poucos isso foi mudando:

  * Vi uma palestra sobre ele na Firebird Conference em Praga ano passado.
  * A RemObjects [anunciou][2] que as novas versões do SDK e do DataAbstract suportarão oficialmente FPC no lugar do abandonado Kylix.
  * Simon Kissel, autor do [CrossKylix][3], disse que vai investir pesado no projeto [CrossFPC][4] (colocando desenvolvedores dedicados), que nos permitirá compilar projetos FPC usando a IDE do Delphi.
  * [Jazz][5] suporta FPC.
  * A nova versão 2.1.4 do FPC já suporta generics! (não testei, mas vi no [release notes][6])

Essas novidades geraram até uma boa discussão no news da CodeGear. Alguém sugeriu que a CodeGear deixasse o compilador Delphi de lado e usasse o FPC, focando apenas na IDE. Pra mim até que faz algum sentido. Atualmente a CodeGear tem IDE para Delphi, C++, C#, Java, PHP e muito breve Ruby. De todos esses, eles só mantêm o compilador para Delphi e C++, os outros compiladores são gratuitos.

O Free Pascal tem sua própria IDE open source, o [Lazarus][7], mas ainda é muito inferior ao Delphi. Por isso acho que vale a pena ficar atento no projeto CrossFPC do Simon Kissel. Me parece que ele esta muito motivado a levar o Free Pascal para frente dentro do Delphi, e pretende investir de verdade.

Com o suporte da RemObjects ao FPC, escrever servidores de aplicação que rodam em Linux voltou a se tornar uma realidade viável. Pretendo iniciar testes em breve.

 [1]: http://www.freepascal.org/
 [2]: http://blogs.remobjects.com/blogs/mh?p=146&more=1&c=1&tb=1&pb=1
 [3]: http://crosskylix.untergrund.net/
 [4]: http://crossfpc.untergrund.net/
 [5]: http://code.google.com/p/jazz-sdk/
 [6]: http://svn.freepascal.org/svn/fpcbuild/tags/release_2_1_4/install/doc/readme.txt
 [7]: http://www.lazarus.freepascal.org/