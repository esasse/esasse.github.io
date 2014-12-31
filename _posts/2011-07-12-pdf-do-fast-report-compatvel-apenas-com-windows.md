---
title: 'PDF do Fast Report compat&iacute;vel apenas com Windows'
author: Erick Sasse
layout: post
permalink: /pdf-do-fast-report-compatvel-apenas-com-windows/
dsq_thread_id:
  - 1014146091
categories:
  - Delphi
tags:
  - Delphi
  - Fast Report
---
O [Fast Report][1] é com certeza um dos principais gerenciadores de relatório usado pelos desenvolvedores Delphi. É também o que eu uso em meus sistemas.

O [formato PDF][2], que, pra quem não sabe, significa Portable Document Format, tem como seu principal objetivo ser um formato para troca de arquivos com “formatação rica”. Ou seja, quando você usa este formato, o objetivo é saber que seu documento vai manter a aparência visual não importa em qual aplicativo ou plataforma ele for aberto.

Infelizmente, para nossa surpresa, descobrimos que não é bem assim. Pelo menos não com os PDF gerados pelo Fast Report.

Alguns dias atrás um cliente entrou em contato nos reportando que um relatório gerado em PDF pelo nosso sistema não estava sendo visualizado corretamente no MacBook. Como eu mesmo tenho um MacBook, fui testar e confirmei o problema. Realmente os textos em negrito e as imagens do relatório simplesmente não apareciam no leitor nativo do Mac OS X. 

Mais um pouco de testes e percebi que o problema não era exclusivo do Mac OS, mas também acontecia no iOS (iPad/iPhone/iPod) e no Android. Ou seja, só funcionava corretamente mesmo no Windows.

Apesar do Windows ser ainda a plataforma dominante, a cada dia temos mais usuários nas outras plataformas. Principalmente iOS com com iPad/iPhone e Android, com uma infinidade de aparelhos rodando esse sistema. Por isso não era um problema que poderia ser tratado com pouca importância.

Entramos em contato com o suporte do Fast Report e a primeira resposta que obtivemos foi de que teríamos que embutir as fontes no PDF. Fizemos o que nos pediram e o PDF subiu de 40K para 900K. Isso para um simples relatório de uma página com bem pouco texto. Fizemos testes com PDF gerados por outros aplicativos, usando a mesma fonte do nosso relatório (Arial) e em todos os casos os PDF funcionavam perfeitamente nas outras plataformas sem embutir a fonte. Ou seja, alguma coisa estava errada com o PDF do Fast Report.

Pressionamos mais um pouco o suporte do Fast Report e obtivemos a seguinte resposta:

> …you should also understand that pdf is not a simple format and only its more complicated version is really portable. At the moment our pdf produces documents targeted for Windows. We are making steps towards more portability, for example we are developing pdf/a version of the export, but I can&#8217;t estimate when really portable pdf export is ready.

Ou seja, os PDFs gerados pelo FR são para Windows apenas e eles não sabem quando uma versão realmente portável estará disponível.

Nós obviamente já estamos procurando outras soluções. Infelizmente temos muitos relatórios em Fast Report, e mesmo diante desse absurdo, por mais que eu gostaria, inicialmente não estamos pensando em trocar de componente de relatório, mas apenas achar uma solução melhor para gerar os PDFs.

Portanto se você usa ou está pensando em usar Fast Report, fique atento com esse detalhe, que na minha opinião, é uma falha monstruosa do componente. Principalmente por saberem disso e não alertarem os clientes, simplesmente divulgando que geram os relatórios em PDF, sem especificar que é um PDF bizarro que vai de encontro ao principal motivo pelo qual o formato foi criado.

 [1]: http://www.fast-report.com
 [2]: http://www.adobe.com/br/products/acrobat/adobepdf.html