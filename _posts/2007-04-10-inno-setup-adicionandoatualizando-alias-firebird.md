---
title: 'Inno Setup &#8211; Adicionando/atualizando alias Firebird'
author: Erick Sasse
layout: post
permalink: /inno-setup-adicionandoatualizando-alias-firebird/
dsq_thread_id:
  - 262149975
categories:
  - Geral
tags:
  - Geral
---
O [Inno Setup][1] é uma ferramenta fantástica. Usamos ele há muito tempo aqui na Cadena e ele nunca nos deixou na mão. Ontem precisei montar um instalador rápido e um dos requisitos era adicionar ou atualizar um alias do Firebird:</p> 

<pre class="wp-code-highlight prettyprint">procedure SetFirebirdAlias;&lt;br /&gt;
var&lt;br /&gt;
  AliasesFile: string;&lt;br /&gt;
  Aliases: TArrayOfString;&lt;br /&gt;
  I: Integer;&lt;br /&gt;
begin&lt;br /&gt;
  AliasesFile := ExpandConstant(&#039;{pf}&#039;) + &#039;\\Firebird\\Firebird_2_0\\aliases.conf&#039;;&lt;br /&gt;
  LoadStringsFromFile(AliasesFile, Aliases);&lt;br /&gt;
  for I := 0 to GetArrayLength(Aliases) - 1 do&lt;br /&gt;
  begin&lt;br /&gt;
    if Pos(&#039;meualias&#039;, Aliases[I]) &gt; 0 then&lt;br /&gt;
    begin&lt;br /&gt;
      Aliases[I] := &#039;meualias = &#039; + GetCaminhoBanco;&lt;br /&gt;
      SaveStringsToFile(AliasesFile, Aliases, False);&lt;br /&gt;
      Exit;&lt;br /&gt;
    end;&lt;br /&gt;
  end;&lt;br /&gt;
  SaveStringToFile(AliasesFile, #13#10 + &#039;meualias = &#039; + GetCaminhoBanco + #13#10, True);&lt;br /&gt;
end;</pre>

 [1]: http://www.jrsoftware.org/isinfo.php