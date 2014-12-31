---
title: SourceGear DiffMerge
author: Erick Sasse
layout: post
permalink: /sourcegear-diffmerge/
dsq_thread_id:
  - 262150740
categories:
  - Geral
  - Reviews
---
Há algum tempo me aborreci com a ferramenta de diff (comparação de arquivos) embutida no TortoiseSVN por ela não suportar alteração do arquivo na própria tela de diff e decidi que precisava de uma ferramenta melhor.

Depois de pesquisar e testar algumas ferramentas (inclusive algumas comerciais), escolhi o [DiffMerge][1] da SourceGear. É uma ferramenta gratuita e que atende perfeitamente minha necessidade. No próprio help você encontra as instruções de como configurar ela no TortoiseSVN e funciona que é uma beleza.

Um dos diferenciais do DiffMerge é que ele suporta [merge de 3 arquivos][2], ou seja, quando mais de um desenvolvedor altera um arquivo. Dessa forma ele tem que considerar o arquivo base e as duas versões alteradas e te ajudar a resolver os conflitos. Poucas ferramentas (inclusive comerciais) suportam isso.

Além disso ele também faz comparação de diretórios e se integra ao menu de contexto do Windows Explorer.

Outro detalhe que pode ser útil para alguns,  é o suporte multi-plataforma. Windows, Mac OS X e Unix.

 [1]: http://www.sourcegear.com/diffmerge/
 [2]: http://en.wikipedia.org/wiki/Merge_(revision_control)#Three-way_merge