---
title: SQL Server 2008 Express e a dependência do .NET 2.0 SP2
author: Erick Sasse
layout: post
permalink: /sql-server-2008-express-e-a-dependencia-do-net-20-sp2/
dsq_thread_id:
  - 262150908
categories:
  - .NET
  - SQL Server
tags:
  - .NET
  - SQL Server
---
Hoje tentei instalar o SQL Server 2008 Express em um servidor Windows 2008. Logo no início da instalação ele já para e dá o seguinte erro:

SQL Server 2008 Setup requires Microsoft .NET Framework 2.0 SP2 to be installed.

<span style="text-decoration: underline;"><a href="http://www.ericksasse.com.br/wp-content/uploads/2008/09/image_2.png"><img class="alignnone size-full wp-image-784" title="sql2008_net20sp2" src="http://www.ericksasse.com.br/wp-content/uploads/2008/09/image_2.png" alt="" width="487" height="202" /></a></span>

Lá fui eu a procura do tal .NET 2.0 SP2. Depois de algum tempo, percebi que não existe download do tal .NET 2.0 SP2. Achei estranho e comecei a pesquisar até encontrar [esse post][1] que explica a pegadinha.

Na verdade você deve baixar o [.NET Framework 3.5 SP1][2], que já contém o .NET Framework 2.0 SP2. <img src="http://www.ericksasse.com.br/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" />

 [1]: http://blogs.msdn.com/psssql/archive/2008/08/28/sql-server-2008-express-net-framework-2-0-sp2-and-3-5-sp1-explained.aspx
 [2]: http://go.microsoft.com/fwlink/?LinkId=120550