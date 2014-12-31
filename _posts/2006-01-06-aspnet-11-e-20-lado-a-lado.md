---
title: ASP.NET 1.1 e 2.0 lado a lado
author: Erick Sasse
layout: post
permalink: /aspnet-11-e-20-lado-a-lado/
dsq_thread_id:
  - 
categories:
  - .NET
  - 'C#'
  - Delphi
---
Hoje precisei pela primeira vez colocar um aplicativo ASP.NET 2.0 em produção. Foi um pequeno aplicativo que usa Mobile WebForms, ou seja, para ser acessado por celulares e PDAs. Fiz com o Visual Studio 2005 com C#, pois no Delphi tentei usando Intraweb e só quebrei a cara. O interessante é que este aplicativo consome um WebService de um outro aplicativo meu, ASP.NET 1.1, feito em ECO no Delphi 2006, acessando Firebird.

Tudo isso rodando no mesmo servidor. Parece uma salada, não? Pois bem, quando coloquei tudo no servidor, comecei a receber a mensagem de erro:

*It is not possible to run two different versions of ASP.NET in the same IIS process. Please use the IIS Administration Tool to reconfigure your server to run the application in a separate process.*

A mensagem diz que preciso rodar aplicativos de diferentes versões do ASP.NET em processos diferentes. Acho que isso só acontece no IIS 6.

Recorri ao nosso amigo Google, e encontrei [aqui passo a passo][1] como criar um Pool diferente para meu aplicativo ASP.NET 2.0 e tudo funcionou. Fica a dica, caso alguém enfrente o mesmo problema.

 [1]: http://msdn.microsoft.com/library/default.asp?url=/library/en-us/cpguide/html/cpconconfiguringaspnetapplicationforaspnetversion.asp