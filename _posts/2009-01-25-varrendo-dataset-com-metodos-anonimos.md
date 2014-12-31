---
title: Varrendo DataSet com Métodos Anônimos
author: Erick Sasse
layout: post
permalink: /varrendo-dataset-com-metodos-anonimos/
dsq_thread_id:
  - 262151099
categories:
  - Delphi
tags:
  - Delphi
---
Métodos anônimos é um dos novos recursos trazidos pelo Delphi 2009. De início ele parece meio estranho e podemos levar um tempo para nos acostumar com a sintaxe, mas podem ser bem úteis em alguns casos como o que eu vou mostrar agora.

Quantas vezes você já não precisou escrever código para varrer um dataset do início ao fim?

<pre class="wp-code-highlight prettyprint">DataSet.First;
while not DataSet.Eof do
begin
  //
  // Faz alguma coisa com o registro atual
  //
  DataSet.Next;
end;</pre>

Isso pode ficar ainda maior se você precisar usar DisableControls ou ainda restaurar o ponteiro do registro do DataSet após a varredura:

<pre class="wp-code-highlight prettyprint">var
  Bookmark: TBookmark;
begin
  DataSet.DisableControls;
  try
    Bookmark := DataSet.Bookmark;
    DataSet.First;
    while not DataSet.Eof do
    begin
      //
      // Faz alguma coisa com o registro atual
      //
      DataSet.Next;
    end;
    DataSet.Bookmark := Bookmark;
  finally
    DataSet.EnableControls;
  end;
end;</pre>

Esse código todo é praticamente repetido em todas as varreduras que precisamos fazer em um DataSet. Então seria muito útil se pudéssemos extrair esse código e trocar apenas a parte que &#8220;faz alguma coisa com o registro atual&#8221;. 

É aqui que os métodos anônimos nos ajudam muito.

Na unit SysUtils do Delphi, existe um tipo TProc declarado desta forma:

<pre class="wp-code-highlight prettyprint">type
  TProc = reference to procedure;</pre>

E vamos usá-lo para criar uma procedure que recebe um dataset e um método anônimo como parâmetros:

<pre class="wp-code-highlight prettyprint">procedure ForEach(DataSet: TDataSet; Proc: TProc);
var
  Bookmark: TBookmark;
begin
  DataSet.DisableControls;
  try
    Bookmark := DataSet.Bookmark;
    DataSet.First;
    while not DataSet.Eof do
    begin
      Proc;
      DataSet.Next;
    end;
    DataSet.Bookmark := Bookmark;
  finally
    DataSet.EnableControls;
  end;
end;</pre>

E com isso podemos chamar a procedure dessa forma:

<pre class="wp-code-highlight prettyprint">ForEach(Table1,
  procedure
  begin
    ShowMessage(Table1NAME.Value)
  end);</pre>

Como eu disse, a sintaxe inicialmente é meio estranha, mas com o tempo você acostuma. No exemplo acima eu codifiquei uma procedure sem nome e sem parâmetros e passei para ser executado em cada registro. Eu tinha um dataset chamado Table1 no form. ShowMessage será chamado para cada registro. Além disso, ele desativa os controles conectados ao dataset e restaura o ponteiro no final.

Perceberam como isso facilita nossa vida? Então pronto, pode ir remover o monte de código duplicado que você tem em seus aplicativos. <img src="http://www.ericksasse.com.br/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" />

Existe ainda uma idéia mais legal que é transformar esse recurso em um helper para a classe TDataSet, mas isso eu vou deixar para vocês como lição de casa ou para um próximo post aqui no blog.

**Update:** Eu já estava prevendo que alguém comentasse isso. Sim, eu sei que já era possível antes com ponteiros de funções, mas com métodos anônimos é muito mais legal e é uma forma de tirar proveito dessa novidade do Delphi 2009. Para quem ainda não tem o Delphi 2009, vale a dica do amigo Marcos Douglas, postada nos comentários.