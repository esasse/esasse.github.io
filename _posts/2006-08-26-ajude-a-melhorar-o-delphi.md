---
title: Ajude a melhorar o Delphi
author: Erick Sasse
layout: post
permalink: /ajude-a-melhorar-o-delphi/
dsq_thread_id:
  - 262149328
categories:
  - Chrome
  - Delphi
---
Conforme vamos conhecendo outras linguagens sempre encontramos coisas legais que podem ser incorporadas ao Delphi.

Já comentei aqui de outros recursos do [Chrome][1] e vou comentar mais um que acho bem prático. 

Eu escrevo muito código parecido com esse dentro de funções:

`
<p>if (algumacoisa) then<br />begin<br />&nbsp;&nbsp;Result := True;<br />&nbsp;&nbsp;Exit;<br />end;</p>
<p>` 

Em Chrome, o Exit suporta&nbsp;um parâmetro de retorno, que é sempre&nbsp;do mesmo tipo de retorno da função, então&nbsp;eu não preciso atribuir o valor de retorno ao Result e depois chamar Exit.&nbsp;Eu simplesmente chamo o&nbsp;Exit passando o valor de retorno. Assim:

`
<p>if (algumacoisa) then<br />&nbsp; Exit(True);</p>
<p>` 

Prático, não? Pois é. Felizmente alguém já fez a solicitação para incluirem exatamente esse recurso no Delphi. Veja aqui no [QC#7201][2]. 

Toda essa introdução foi para justificar o título deste post. O QC da Borland permite que você vote nos principais recursos que gostaria de ver no Delphi. Eu por exemplo já deixei meu voto nesse ai e em vários outros.

Vocês tem que participar, tem que agitar as coisas por lá, sugerindo, comentando, votando. Para que o pessoal saiba direcionar melhor o produto de acordo com as nossas necessidades.

No futuro quero dedicar uma reunião do [DUG Campinas][3] para mostrar o QC em detalhes e estimular o pessoal a participar. Mas você já pode começar participando desde já. 

Gostou desse recurso que mostrei do Chrome? Vá no QC e coloque seu voto nele, para que apareça bem colocado na lista de recursos sugeridos e seja implementado&nbsp;o quanto antes&nbsp;pela DevCo.

 [1]: http://www.chromesville.com/
 [2]: http://qc.borland.com/wc/qcmain.aspx?d=7201
 [3]: http://www.dugcampinas.com.br