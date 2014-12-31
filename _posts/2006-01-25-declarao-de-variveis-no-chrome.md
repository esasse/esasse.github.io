---
title: 'Declara&ccedil;&atilde;o de vari&aacute;veis no Chrome'
author: Erick Sasse
layout: post
permalink: /declarao-de-variveis-no-chrome/
dsq_thread_id:
  - 268719688
categories:
  - Chrome
---
O Chrome &eacute; bem flex&iacute;vel e pr&aacute;tico na declara&ccedil;&atilde;o de vari&aacute;veis. Ele permite que voc&ecirc; utilize como no Delphi, declarando todas as vari&aacute;veis no in&iacute;cio de cada bloco, na se&ccedil;&atilde;o &#8220;var&#8221;, mas tamb&eacute;m suporta o estilo C#, onde voc&ecirc; declara a vari&aacute;vel onde quiser.

<pre class="wp-code-highlight prettyprint">&lt;code&gt;class method ConsoleApp.Calculo;
var
  A, B, C: Integer;
begin
  A := 1;
  B := 2;
  C := B + A;
end;

class method ConsoleApp.Calculo2; 
begin
  var A : Integer := 1;
  var B := 2;
  var C := B + A;
end;
&lt;/code&gt;</pre>

O primeiro trecho &eacute; igual ao Delphi, j&aacute; o segundo usa declara&ccedil;&atilde;o inline e infer&ecirc;ncia de tipo, ou seja, a vari&aacute;vel B &eacute; automaticamente declarada como Integer devido ao valor que voc&ecirc; est&aacute; atribuindo a ela. O mesmo acontece para a vari&aacute;vel C. No caso da vari&aacute;vel A n&atilde;o usei infer&ecirc;ncia, especifiquei o tipo.

Qual a melhor forma? Dificil responder. Como eu procuro manter m&eacute;todos sempre bem pequenos, acho que n&atilde;o faz muita diferen&ccedil;a pra mim, pois n&atilde;o &eacute; dificil de identificar as vari&aacute;veis em pequenos trechos de c&oacute;digo. A &uacute;nica vantagem imediata que vejo da declara&ccedil;&atilde;o inline &eacute; que voc&ecirc; acaba escrevendo menos c&oacute;digo, mas nesse caso, a diferen&ccedil;a &eacute; muito pouca.