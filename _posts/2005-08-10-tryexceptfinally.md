---
title: try..except..finally vs. try..catch..finally
author: Erick Sasse
layout: post
permalink: /tryexceptfinally/
dsq_thread_id:
  - 262147615
categories:
  - 'C#'
  - Delphi
---
Isso &eacute; poss&iacute;vel no C#:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;try
{
  ...
}
catch
{
  ...
}
finally
{
  ...
}
&lt;/code&gt;</pre>

No Delphi, eu preciso de dois blocos try. Um para o except e outro para o finally:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;try
  try
    ...
  except
    ...
  end;
finally
  ...
end;&lt;/code&gt;</pre>

Ta&iacute; uma coisa simples que seria muito legal se fosse suportado no Delphi. Ficaria mais simples:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;try
  ...
except
  ...
finally
  ...
end;&lt;/code&gt;</pre>