---
title: Interfaces
author: Erick Sasse
layout: post
permalink: /interfaces/
dsq_thread_id:
  - 262147168
categories:
  - Geral
tags:
  - Geral
---
At&eacute; hoje usei muito pouco Interfaces devido a complexidade de sua utiliza&ccedil;&atilde;o com Delphi Win32. J&aacute; tive muita dor de cabe&ccedil;a ao tentar us&aacute;-las mais amplamente em meu c&oacute;digo. O principal problema das Interfaces no Delphi Win32 s&atilde;o as contagens de refer&ecirc;ncia, que s&atilde;o controladas automaticamente pelas classes TInterfacedObject e suas derivadas. Por&eacute;m esse &#8220;automaticamente&#8221;, requer que voc&ecirc; tome uma s&eacute;rie de cuidados na utiliza&ccedil;&atilde;o, que eu confesso at&eacute; hoje n&atilde;o ter entendido completamente.

Por&eacute;m, ao que me parece, toda essa dificuldade desaparece no .NET, tornando o uso de Interfaces t&atilde;o simples quanto o uso de uma classe qualquer. Como ainda n&atilde;o migrei praticamente nenhum projeto meu para .NET, ainda n&atilde;o pude tirar proveito disso, mas deixo aqui a dica para voc&ecirc;s realmente entenderem como elas funcionam e tirarem muito proveito das Interfaces, pois &eacute; um recurso muito poderoso, deixa seu c&oacute;digo muito mais limpo e flex&iacute;vel.

N&atilde;o vejo a hora de come&ccedil;ar a usar!