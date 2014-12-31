---
title: Comportamento estranho do SQLConnection.ExecuteDirect
author: Erick Sasse
layout: post
permalink: /comportamento-estranho-do-sqlconnectionexecutedirect/
dsq_thread_id:
  - 262149052
categories:
  - Delphi
---
Hoje me deparei com um comportamento no mínimo estranho no dbExpress. Se você usa essa engine, é bom estar ciente.

O componente SQLConnection tem um método ExecuteDirect que lhe permite enviar comandos diretos para o banco de dados sem ter que criar um SQLDataSet ou coisas do tipo. Pois bem, venho usando este método há um bom tempo já, mas só hoje percebi esse detalhe.

Mesmo que você não tenha uma conexão válida com o banco de dados, ele não retorna nenhum erro. Você pode enviar quantos comandos quiser, que nenhuma exception é gerada. A única forma de saber se o comando foi bem sucedido ou não é verificando o resultado da chamada, que retorna um inteiro. Mas aqui tem outro problema. O help do Delphi diz que ele retorna zero se o comando foi bem sucedido, mas o [help está errado][1]. Ele retorna o número de registros afetados pelo comando que você enviou. Quando não existe conexão com o banco, retorna sempre zero, e daí você pode tratar da forma que preferir.

Mas o que eu gostaria mesmo (pois na minha opinião faz muito mais sentido) é que uma exception fosse gerada quando não existisse uma conexão válida e retornasse zero apenas se o comando foi enviado com sucesso ao banco e nada foi afetado.

PS: Isso acontece com o dbExpress (D7 e D2006) acessando Firebird 1.5.3, usando fbclient.dll.  Não testei com outros bancos.

 [1]: http://qc.borland.com/wc/qcmain.aspx?d=4043