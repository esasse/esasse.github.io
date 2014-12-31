---
title: 'Propriedades Simples em C# 3.0'
author: Erick Sasse
layout: post
permalink: /propriedades-simples-em-c-30/
dsq_thread_id:
  - 262149902
categories:
  - 'C#'
---
Algum tempo atrás eu comentei sobre as [propriedades implícitas][1] que o Chrome oferece. É uma mão na roda.

Na nova versão do C#, poderemos declarar propriedades simples da seguinte forma:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;class Pessoa
{
public string Nome { get; set; }
public int Idade { get; set; }
}&lt;/code&gt;</pre>

O que gera um código muito menos poluído do que o código em C# 2.0:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;class Pessoa
{
private string nome;
public string Nome
{
get { return nome; }
set { nome = value; }
}

private int idade;
public int Idade
{
get { return idade; }
set { idade = value; }
}
}&lt;/code&gt;</pre>

Me parece que o nome desse recurso é auto-implemented properties. Gostei.

 [1]: /chrome-propriedades-implicitas/