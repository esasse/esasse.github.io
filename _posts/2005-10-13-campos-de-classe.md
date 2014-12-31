---
title: Campos de classe
author: Erick Sasse
layout: post
permalink: /campos-de-classe/
dsq_thread_id:
  - 262148264
categories:
  - Delphi
---
Um dos novos recursos do Delphi em .NET s&atilde;o os campos de classe (tamb&eacute;m conhecidos como est&aacute;ticos). Em Win32 &eacute; poss&iacute;vel ter m&eacute;todos de classe, mas n&atilde;o campos.

M&eacute;todos ou campos de classe podem ser acessados sem uma inst&acirc;ncia da classe.

Em .NET podemos fazer isso:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;type
&nbsp;&nbsp;&nbsp;TMinhaClasse = class
&nbsp;&nbsp;&nbsp;public
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;class var
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Var1: Integer;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var2: string;
&nbsp;&nbsp;&nbsp;end;&lt;/code&gt;</pre>

E acessar pelo nome da classe assim:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;TMinhaClasse.Var1 := 0;
TMinhaClasse.Var2 := &#039;Ol&aacute; Mundo!&#039;;&lt;/code&gt;</pre>