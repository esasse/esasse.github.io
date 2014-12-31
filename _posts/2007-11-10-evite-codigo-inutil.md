---
title: Evite Código Inútil
author: Erick Sasse
layout: post
permalink: /evite-codigo-inutil/
dsq_thread_id:
  - 262150514
categories:
  - Delphi
  - Geral
tags:
  - Geral
---
Uma coisa que eu gosto de fazer é refatorar código antigo. Sempre encontro muita coisa inútil que pode ser removida. Incontáveis vezes eu já escrevi código do tipo:

<pre class="wp-code-highlight prettyprint">if not MeuDataSet.Active then
  MeuDataSet.Open;</pre>

O problema é que esse &#8220;if&#8221; é totalmente inútil. Se você olhar no código da classe TDataSet do Delphi vai ver que ele já faz essa checagem sempre que você chama Open. Outro código inútil que eu também já escrevi e continuo vendo muita gente repetir, é o seguinte:

<pre class="wp-code-highlight prettyprint">if ClientDataSet.ChangeCount &gt; 0 then
  ClientDataSet.ApplyUpdates(0);</pre>

Você também não precisa desse &#8220;if&#8221; pois a checagem também já é feita pelo ClientDataSet automaticamente.

Comece a olhar melhor para seu código e código de terceiros que você usa e certamente encontrará muita coisa que pode ser eliminada.