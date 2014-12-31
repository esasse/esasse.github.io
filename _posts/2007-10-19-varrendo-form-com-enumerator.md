---
title: Varrendo componentes de um form com enumerator
author: Erick Sasse
layout: post
permalink: /varrendo-form-com-enumerator/
dsq_thread_id:
  - 262150461
categories:
  - Delphi
---
No Delphi é muito fácil varrer os componentes de um TForm usando enumerator e for in. Bem mais prático que usando for to. No exemplo abaixo, faço uma verradura por todos os componentes do form setando todos os TLabel como transparentes:

<pre class="wp-code-highlight prettyprint">var
  Component: TComponent;
begin
  for Component in Self do
    if Component is TLabel then
      TLabel(Component).Transparent := True;
end;</pre>