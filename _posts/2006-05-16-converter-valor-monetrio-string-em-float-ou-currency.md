---
title: 'Converter valor monet&aacute;rio string em float ou currency'
author: Erick Sasse
layout: post
permalink: /converter-valor-monetrio-string-em-float-ou-currency/
dsq_thread_id:
  - 262148913
categories:
  - Delphi
---
Se voc&ecirc; tiver uma string assim: &#8220;R$ 1.234,56&#8243; e precisar converter para currency ou float, voc&ecirc; precisa antes remover o s&iacute;mbolo da moeda &#8220;R$&#8221; e o separador de milhar.

Tenho utilizado essa fun&ccedil;&atilde;o para isso:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;function StrCurrToCurrDef(AString: string; Default: Currency): Currency;
begin
  AString := StringReplace(AString, ThousandSeparator, &#039;&#039;, [rfReplaceAll]);
  AString := StringReplace(AString, CurrencyString, &#039;&#039;, [rfReplaceAll]);
  Result := StrToCurrDef(AString, Default);
end;
&lt;/code&gt;</pre>

N&atilde;o lembro mais se foi eu quem a escrevi ou se peguei na web, ent&atilde;o os cr&eacute;ditos v&atilde;o ficar pendentes.

O primeiro par&acirc;metro que voc&ecirc; passa &eacute; a string a ser convertida e o segundo &eacute; um valor default, caso a convers&atilde;o n&atilde;o seja bem sucedida.