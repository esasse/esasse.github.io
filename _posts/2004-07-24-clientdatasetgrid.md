---
title: ClientDataSetGrid
author: Erick Sasse
layout: post
permalink: /clientdatasetgrid/
dsq_thread_id:
  - 271535707
categories:
  - Delphi
---
[John Kaster][1] disponibilizou uma grid descendente da DBGrid padr&atilde;o do Delphi com alguns recursos bem legais para quem usa ClientDataSet. A [TClientDataSetGrid][2] permite ordenar o ClientDataSet em mem&oacute;ria quando se clica no cabe&ccedil;alho da coluna. At&eacute; aqui nada demais. O que &eacute; legal mesmo &eacute; que se voc&ecirc; clicar em outras colunas mantendo o Shift apertado, ele vai ordenando na sequ&ecirc;ncia, ou seja, clicou na Cidade do cliente, depois no Nome mantendo o Shift apertado, ela ordena pela Cidade e depois por Nome, e coloca setas com n&uacute;meros nas colunas, indicando a dire&ccedil;&atilde;o de cada ordena&ccedil;&atilde;o (crescente ou decrescente) e a ordem das colunas. Bem interessante.

 [1]: http://blogs.borland.com/johnk/archive/2004/07/20/889.aspx
 [2]: http://cc.borland.com/codecentral/ccweb.exe/listing?id=15099