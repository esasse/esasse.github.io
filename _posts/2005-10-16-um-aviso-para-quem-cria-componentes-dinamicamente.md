---
title: Um aviso para quem cria componentes dinamicamente
author: Erick Sasse
layout: post
permalink: /um-aviso-para-quem-cria-componentes-dinamicamente/
dsq_thread_id:
  - 262148289
categories:
  - Delphi
---
[Este artigo][1] do site About Delphi atenta para um detalhe que, como eu, muitos devem deixar passar despercebido.

Se voc&ecirc; cria e destroi seus componentes dinamicamente, deve passar sempre **nil** como owner. Isso vai otimizar seu aplicativo.

 [1]: http://delphi.about.com/b/a/203912.htm