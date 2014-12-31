---
title: 'Chrome: Propriedades Impl&iacute;citas'
author: Erick Sasse
layout: post
permalink: /chrome-propriedades-implicitas/
dsq_thread_id:
  - 290968799
categories:
  - Chrome
---
Uma das facilidades que o [Chrome][1] nos oferece &eacute; o recurso de propriedades impl&iacute;citas. Veja a classe abaixo em Delphi:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;Pessoa = class
private
  FIdade: Integer;
  FNome: String;
public
  property Nome: String read FNome write FNome;
  property Idade: Integer read FIdade write FIdade;
end;&lt;/code&gt;</pre>

Em C# seria algo assim:

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

Em Chrome, a mesma classe, tirando proveito das propriedades impl&iacute;citas, poderia ser escrita assim:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;Pessoa = class
public
  property Nome: String;
  property Idade: Integer;
end;&lt;/code&gt;</pre>

Ou seja, um ter&ccedil;o do n&uacute;mero de linhas se comparado a C# e quase a metade das linhas comparada a Delphi.

 [1]: http://www.chromesville.com/