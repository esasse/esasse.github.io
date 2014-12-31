---
title: Lista de Inteiros
author: Erick Sasse
layout: post
permalink: /lista-de-inteiros/
dsq_thread_id:
  - 263977296
categories:
  - Delphi
---
Alguma vez voc&ecirc; j&aacute; precisou gerenciar uma lista de inteiros?  
Acabei de postar esta dica em uma das listas de Delphi que participo. A melhor classe que conhe&ccedil;o para isso &eacute; a TList.

<pre class="wp-code-highlight prettyprint">&lt;code&gt;procedure Foo;
var
  Lista: TList;
  I: Integer;

  function OrdenarDecrescente(Numero1, 
    Numero2: Pointer): Integer;
  begin
    Result := Integer(Numero2) - Integer(Numero1);
  end;

begin
  Lista := TList.Create;
  try
    for I := 1 to 10 do
      Lista.Add(Pointer(I));

    Lista.Sort(@OrdenarDecrescente);

    for I := 0 to Lista.Count - 1 do
      ShowMessage(IntToStr(Integer(Lista[I])));
  finally
    Lista.Free;
  end;
end;&lt;/code&gt;</pre>

A procedure acima adiciona 10 n&uacute;meros a uma lista e depois ordena em ordem decrescente.

O mais interessante seria encapsular essa l&oacute;gica em uma classe especializada com metodos para Sort crescente, decrescente, e que fosse fortemente tipada para que voc&ecirc; n&atilde;o precisasse executar o cast para Integer sempre que fosse acessar um item.