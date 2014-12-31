---
title: Multi-thread com banco de dados
author: Erick Sasse
layout: post
permalink: /multi-thread-com-banco-de-dados/
dsq_thread_id:
  - 262143159
categories:
  - Delphi
  - Firebird
---
H&aacute; pouco tempo comecei a trabalhar com multi-thread em meus aplicativos. Quando usado de forma correta, os resultados s&atilde;o muito bons. 

Mas como tudo que &eacute; novo, voc&ecirc; nem sempre come&ccedil;a fazendo a coisa da forma correta. 

Eu tenho threads em alguns aplicativos que importam dados em background, sem interferencia do usu&aacute;rio, e enquanto ele trabalha em outras partes do sistema. A thread de importa&ccedil;&atilde;o usava a conex&atilde;o do banco de dados para importar os dados, e a thread principal do aplicativo tamb&eacute;m usava a conex&atilde;o para atender o usu&aacute;rio. 

O problema &eacute; que eu n&atilde;o sabia que cada thread que acessa banco de dados precisa de uma conex&atilde;o independente ao banco e eu compartilhava a mesma conex&atilde;o com todas as threads. O resultado disso eram v&aacute;rias mensagens de erros estranhas, que n&atilde;o apontavam com clareza o problema. 

Todos estes erros abaixo eram decorrentes desse problema:

* 

  * SQL Server Error: SQLDA missing or incorrect version, or incorrect number/type of variables.
  * SQL Server Error: Error reading data from the connection.
  * SQL Server Error: Attempt to reclose a closed cursor.
  * SQL Server Error: Incorrect values within SQLDA structure.
  * SQL Server Error: unassigned code.
  * SQL Server Error: deadlockdeadlockupdate conflicts with concurrent update.
  * Access violation in module &#8216;FBCLIENT.DLL&#8217;.
  * dbExpress Error: [0x0002]: Insufficient Memory for OperationSQL Server Error: unassigned code.
  * InternalDataSet: Cursor not returned from Query.

</em>

No meu caso, eu uso dbExpress (com Firebird), ent&atilde;o preciso de uma inst&acirc;ncia do SQLConnection para cada thread que acessa o banco de dados, dessa forma elas n&atilde;o conflitam quando tentam acessar o banco ao mesmo tempo.

N&atilde;o esque&ccedil;a disso, e voc&ecirc; poupar&aacute; muitas horas de dor de cabe&ccedil;a. E n&atilde;o tenha medo de usar threads, o resultado &eacute; show de bola!