---
title: Migrando Win32 para .NET com RemObjects Hydra
author: Erick Sasse
layout: post
permalink: /migrando-win32-para-net-de-forma-suave-com-remobjects-hydra/
dsq_thread_id:
  - 278827915
categories:
  - .NET
  - 'C#'
  - Chrome
  - Delphi
  - Visual Studio
---
A [RemObjects][1] está trabalhando na versão 3 do seu framework de plugins e a principal novidade é a integração absurdamente fácil de módulos Win32 e .NET. Você pode por exemplo, desenvolver módulos do seu aplicativo em .NET e usá-los sem nenhum esforço nos aplicativos Win32. E isso funciona inclusive para componentes visuais!

Se você não tem idéia do que estou falando, dê uma olhada neste aplicativo Delphi Win32:

<img border="0" src="http://static.flickr.com/98/213195512_af3849aa1a_o.png" />

Tá vendo esse ListBox, o Edit e o botão Add? Então, eles são componentes WinForms .NET, desenvolvidos em Chrome usando Visual Studio. Mas poderia ser Delphi .NET usando BDS mesmo, C# ou até VB.NET. Detalhe, eles estão dentro de um TForm comum, da VCL Win32 do Delphi.

Show de bola, não? Então dê uma olhada [neste artigo][2] da RemObjects que explica melhor como isso é possível. Pra quem deseja migrar os aplicativos para .NET aos poucos, o Hydra 3 parece ser uma ótima solução.

 [1]: http://www.remobjects.com
 [2]: http://www.remobjects.com?hy07