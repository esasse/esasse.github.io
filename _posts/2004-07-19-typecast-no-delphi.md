---
title: Typecast no Delphi
author: Erick Sasse
layout: post
permalink: /typecast-no-delphi/
dsq_thread_id:
  - 262142476
categories:
  - Delphi
---
Hoje uma d&uacute;vida me atormentou e resolvi acabar com ela de uma vez por todas. Existem duas formas b&aacute;sicas de se fazer typecast em Delphi: TMinhaClasse(Objeto) ou (Objeto as TMinhaClass). A d&uacute;vida &eacute; que eu n&atilde;o sabia de verdade qual era a diferen&ccedil;a entre as duas. Fui aos newsgroups da Borland, que &eacute; sem d&uacute;vida a melhor fonte de informa&ccedil;&atilde;o sobre Delphi existente na Internet.

A diferen&ccedil;a &eacute; o seguinte, quando voc&ecirc; usa TMinhaClasse(Objeto) o compilador n&atilde;o verifica se sua chamada &eacute; v&aacute;lida, ou seja, ele n&atilde;o verifica se Objeto pode ser tratado como um objeto da classe TMinhaClasse. &Eacute; um &#8220;hard cast&#8221;. S&oacute; deve ser usado se voc&ecirc; tem certeza absoluta que NUNCA vai passar um objeto errado para o cast, pois se isso acontecer, voc&ecirc; poder&aacute; obter todo tipo de erro estranho, como access violations e coisas do tipo, sem realmente saber qual &eacute; o problema, pois ele n&atilde;o ser&aacute; indicado. O hard cast tem melhor performance, pois n&atilde;o verifica se a chamada &eacute; v&aacute;lida, mas deve ser usado com cautela. Voc&ecirc; pode testar o objeto antes usando o operador &#8220;is&#8221;, desta forma:

if (Objeto is TMinhaClasse) then  
&nbsp;&nbsp;&nbsp;TMinhaClasse(Objeto)&#8230;

Agora quando usamos (Objeto as TMinhaClasse), uma verifica&ccedil;&atilde;o &eacute; feita em runtime para verificar se a chamada &eacute; v&aacute;lida. Caso n&atilde;o seja, uma exce&ccedil;&atilde;o ser&aacute; gerada. Essa op&ccedil;&atilde;o &eacute; mais segura, pois caso voc&ecirc; cometa um engano, saber&aacute; exatamente o problema assim que ele acontecer, evitando maiores dores de cabe&ccedil;a.

No Delphi 8, existe uma pequena diferen&ccedil;a, a primeira forma TMinhaClasse(Objeto) retorna nil se n&atilde;o for uma chamada v&aacute;lida. Isso facilita um pouco o rastreamento de erros, pois provavelmente gerar&aacute; uma exce&ccedil;&atilde;o logo que voc&ecirc; tentar utilizar o objeto resultado do typecast.