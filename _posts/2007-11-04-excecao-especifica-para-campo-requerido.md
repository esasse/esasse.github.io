---
title: Exceção Específica para Campo Requerido
author: Erick Sasse
layout: post
permalink: /excecao-especifica-para-campo-requerido/
dsq_thread_id:
  - 262150467
categories:
  - Delphi
---
Quando você tenta postar um registro num TClientDataSet deixando algum campo requerido sem valor, você obtém a seguinte exceção:

EDatabaseError: Field &#8216;XXX&#8217; must have a value.

EDatabaseError é uma exceção genérica para erros de banco de dados, portanto se quisermos incluir código para tratar apenas exceções de campos requeridos teríamos que tratar a mensagem de erro, que é uma técnica que cheira muito mal. Além disso, a mensagem mostra o DisplayLabel do campo, então se você quiser saber o nome do campo que gerou a exceção você precisa extrair o DisplayLabel da mensagem e fazer um loop em todos os campos do DataSet para descobrir, ou seja, um baita trabalhão e muito propenso a erro.

Uma outra abordagem para tratar isso é não deixar essa exceção do Delphi ser levantada nunca, evitando que um post seja feito caso algum campo esteja vazio. Para isso você teria que fazer um loop nos campos gerando sua própria exceção durante o BeforePost por exemplo. O problema é acrescentar essa verificação em todos seus ClientDataSets. A melhor solução aqui talvez seria criar seu descendente de TClientDataSet com essa checagem adicional.

Mas o melhor mesmo seria que o componente original do Delphi já tivesse esse recurso facilitando ainda mais a nossa vida. Por isso abri a solicitação [QC#54379][1].

Aproveitando o embalo, abri o [QC#54380][2] sobre a mensagem &#8220;Field Value Required&#8221; que é normalmente levantada quando apenas o TField no servidor está marcado como Required e o ClientDataSet tenta postar o campo nulo. Essa mensagem simplesmente não diz em qual campo está o problema, então temos que ir um por um checando, verificando o código, etc.

Se você quer que o Delphi evolua, não deixe de participar no QC, abrindo solicitações, votando nas suas preferidas, etc.

 [1]: http://qc.codegear.com/wc/qcmain.aspx?d=54379
 [2]: http://qc.codegear.com/wc/qcmain.aspx?d=54380