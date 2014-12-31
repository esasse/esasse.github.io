---
title: Livemarks do Firefox
author: Erick Sasse
layout: post
permalink: /livemarks-do-firefox/
dsq_thread_id:
  - 314409642
categories:
  - Geral
tags:
  - Geral
---
Se voc&ecirc; usa [Firefox][1] j&aacute; deve ter notado aquele &iacute;cone laranja que aparece na barra de status quando voc&ecirc; acessa algumas p&aacute;ginas. Ele indica que o Firefox detectou feeds RSS ou Atom para assinatura. Esse recurso &eacute; chamado Livemarks. Aqui no meu blog por exemplo, voc&ecirc; tem tr&ecirc;s op&ccedil;&otilde;es de feed, RSS 2.0, RSS .92 e Atom 0.3. N&atilde;o me pergunte a diferen&ccedil;a porque eu n&atilde;o sei, al&eacute;m de serem formatos diferentes, &eacute; claro.

No caso do meu blog, o WordPress, que &eacute; um &oacute;timo gerenciador, j&aacute; cria tudo isso automaticamente, mas caso seu blog tenha feeds RSS e o Firefox n&atilde;o est&aacute; identificando, basta adicionar uma linha como essa em suas p&aacute;ginas na se&ccedil;&atilde;o <head>:

`<link rel="alternate" type="application/rss+xml" title="Meu Blog" href="http://www.example.com/url_do_seu_feed.xml" />`

 [1]: http://www.getfirefox.com