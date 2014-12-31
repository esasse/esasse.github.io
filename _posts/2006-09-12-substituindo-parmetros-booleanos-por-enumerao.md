---
title: 'Substituindo par&acirc;metros booleanos por enumera&ccedil;&atilde;o'
author: Erick Sasse
layout: post
permalink: /substituindo-parmetros-booleanos-por-enumerao/
dsq_thread_id:
  - 262149361
categories:
  - Delphi
---
Responda rápido, qual a diferença entre estes dois comandos:

` `

CopyFile(&#8216;arq1.txt&#8217;, &#8216;arq2.txt&#8217;, True);

CopyFile(&#8216;arq1.txt&#8217;, &#8216;arq2.txt&#8217;, False);

Eu não saberia dizer para que serve esse terceiro parâmetro booleano sem usar o tooltip do Delphi ou ler a documentação.

E se fosse assim?

`CopyFile('arq1.txt', 'arq2.txt', cmFailIfExists);`

Melhor não?

Pois é, a outra opção poderia ser algo como:

`CopyFile('arq1.txt', 'arq2.txt', cmOverwrite); `

Há algum tempo atrás [li uma dica][1] que venho aplicando desde então: substituir parametros booleanos por enumerações. O código fica muito mais fácil de ler e entender.

No exemplo acima usei uma função da API Win32 para exemplificar, mas se fossemos reescrever a função CopyFile, ficaria algo assim:

`type<br />
TCopyMode = (cmFailIfExists, cmOverwrite); `

procedure MyCopyFile(const Source, Dest: string; CopyMode: TCopyMode);

 [1]: http://blogs.msdn.com/brada/archive/2005/10/26/475085.aspx