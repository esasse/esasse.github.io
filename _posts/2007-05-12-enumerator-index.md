---
title: Enumerator Index
author: Erick Sasse
layout: post
permalink: /enumerator-index/
dsq_thread_id:
  - 272540954
categories:
  - Chrome
  - Delphi
  - RemObjects
---
Depois que li esta ótima série de [artigos sobre enumerators][1] no Delphi, comecei a implementar enumerators para minhas listas tipadas. Isso simplificou muito meu código de loop em listas, mas em alguns casos eu simplesmente não pude usar o for..in pois eu precisava saber o índice de cada item durante o loop, então tinha que usar o for normal.

Agora acabo de ver um [post do Marc][2] mostrando um novo recurso no [Chrome][3] que resolve exatamente este problema. No Chrome 2.0 você pode definir uma variável para índice em um for each. Ficaria assim:

`<span style="font-weight: bold">for each</span> Item <span style="font-weight: bold">in</span> MinhaLista <span style="font-weight: bold">index</span> I: Int32 <span style="font-weight: bold">do</span><br />
...<code />`

E dentro do loop você pode usar a variável I sempre que precisar saber o índice do item atual. Muito útil. Seria muito útil no Delphi.

 [1]: http://17slon.com/blogs/gabr/2007/03/fun-with-enumerators.html
 [2]: http://blogs.remobjects.com/blogs/mh/?p=141
 [3]: http://www.chromesville.com/