---
title: Synchronization Services for ADO.NET
author: Erick Sasse
layout: post
permalink: /synchronization-services-for-adonet/
categories:
  - .NET
---
Hoje tomei conhecimento de mais um novo recurso que fará parte do Visual Studio &#8220;Orcas&#8221;: [Synchronization Services for ADO.NET][1]. Esse recurso tem por objetivo permitir aplicativos trabalharem offline ou em redes lentas, fazendo cache local dos dados e sincronismo praticamente automático.

[Steve Lasker][2] publicou [dois screencasts][3] mostrando esse recurso. O primeiro usando conexão em 2 camadas e o segundo em 3 camadas através de um serviço WCF (antigo Indigo, que também é bem interessante e pretendo falar mais em breve).

 [1]: http://www.microsoft.com/downloads/details.aspx?FamilyId=75FEF59F-1B5E-49BC-A21A-9EF4F34DE6FC&#038;displaylang=en
 [2]: http://blogs.msdn.com/stevelasker/
 [3]: http://blogs.msdn.com/stevelasker/archive/2007/03/23/going-n-tier-w-wcf-synchronizing-data-using-sync-services-for-ado-net-and-sql-server-compact-edition.aspx