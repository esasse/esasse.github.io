---
title: O professor que não gostava do Break
author: Erick Sasse
layout: post
permalink: /o-professor-que-nao-gostava-do-break/
dsq_thread_id:
  - 262148394
categories:
  - Delphi
  - Geral
tags:
  - Geral
---
Eu uso o comando `<strong>break</strong>` em código que eu escrevo com alguma frequência. E essa semana ao usá-lo me lembrei de um professor que tive não me lembro se foi na faculdade ou no colégio técnico, mas ele dizia aos alunos que não deveriam nunca usar o `<strong>break</strong>`, pois era uma prática errada na programação, pouco &#8220;elegante&#8221;, pois dificulta a visualização do fluxo do código. 

Não concordo muito com ele, acho que o comando pode ser aplicado de forma útil e clara, desde que o programador tenha bom senso. O mesmo vale para o famoso e muito mais polêmico `<strong>with</strong>`. Se você não souber usar, seu código fica uma bagunça só, mas se souber, ele pode ser bem útil.

Por exemplo, tenho uma classe base de forms modais que gerenciam sua criação e destruição automaticamente e o código para criar, exibir e destruir é esse:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;class function TFormCdnExec.Executar: Boolean;
begin
  with Self.Create(nil) do
  try
    Result := (ShowModal = idOK);
  finally
    Free;
  end;
end;
&lt;/code&gt;</pre>

Existe motivo para não usar `<strong>with</strong>` aqui? Eu acho que não. O código fica mais extenso, sem praticamente nenhum ganho:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;class function TFormCdnExec.Executar: Boolean;
var
  F: TFormCdnExec;
begin
  F := Self.Create(nil);
  try
    Result := (F.ShowModal = idOK);
  finally
    F.Free;
  end;
end;
&lt;/code&gt;</pre>

Moral da história é, use com bom senso e tire proveito de cada recurso da linguagem.