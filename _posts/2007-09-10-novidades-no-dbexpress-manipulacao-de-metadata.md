---
title: 'Novidades no dbExpress: Manipulação de MetaData'
author: Erick Sasse
layout: post
permalink: /novidades-no-dbexpress-manipulacao-de-metadata/
dsq_thread_id:
  - 266776229
categories:
  - Delphi
---
Fazia tempo que eu não gostava tanto de ler algo em um blog da CodeGear. [Esse post][1] do Steve Shaughnessy mostrou uma novidade muito, muito legal. É a possibilidade de manipular a estrutura do banco de dados de forma genérica. Ou seja, você diz para o DBExpress criar uma tabela e ele delega isso para o driver fornecer o script SQL compatível com o banco utilizado no momento.  E a manipulação do metadata é todo via object pascal, nada de ficar quebrando a cabeça com comandos SQL.

Gostei muito! Só espero que isso seja implementado realmente de uma forma que funcione na prática. Pois tudo é muito bonito na teoria. O dbExpres sempre prometeu abstração do banco de dados, mas para você conseguir isso hoje, precisa fazer muito malabarismo.

 [1]: http://blogs.codegear.com/steveshaughnessy/archive/2007/09/07.aspx