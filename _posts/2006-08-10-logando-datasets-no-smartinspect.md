---
title: Logando DataSets no SmartInspect
author: Erick Sasse
layout: post
permalink: /logando-datasets-no-smartinspect/
dsq_thread_id:
  - 289446083
categories:
  - Delphi
---
Alguns dias atr&aacute;s [comentei][1] que estou usando o [SmartInspect][2] para log e aux&iacute;lio ao debug dos meus aplicativos. 

Um dos recursos mais poderosos na minha opini&atilde;o &eacute; o recurso de logar DataSets. Ele permite logar, a qualquer momento, DataSets inteiros. Ele tira um retrato do DataSet e voc&ecirc; pode visualizar a situa&ccedil;&atilde;o exata do DataSet e todos seus registros no momento em que foi logado. 

Esse recurso &eacute; muito &uacute;til quando trabalhamos com processamentos que envolvem DataSets ocultos. Quantas vezes j&aacute; n&atilde;o quisemos ter um grid ligado a um DataSet oculto para termos certeza que ele est&aacute; da forma que esperamos que esteja?

Para logar um DataSet, &eacute; bem simples. Uma linha de c&oacute;digo:

`SiMain.LogDataSet('BioLife ao criar o form', Table1);`

E j&aacute; posso ver no SI Console:

[<img src="http://static.flickr.com/78/212130029_80e804d485_m.jpg" title="" border="0" />][3]

 [1]: http://www.ericksasse.com.br/?p=517
 [2]: http://www.gurock.com/products/smartinspect/
 [3]: http://static.flickr.com/78/212130029_80e804d485_o.jpg