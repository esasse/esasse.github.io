---
title: Bug dbExpress Delphi 2005
author: Erick Sasse
layout: post
permalink: /bug-dbexpress-delphi-2005/
dsq_thread_id:
  - 262147248
categories:
  - Delphi
---
Pessoal, essa foi a gota d&#8217;&aacute;gua. Descobri um novo bug, esse me afeta em cheio. Se voc&ecirc; usa dbExpress e Firebird, fique muito atento a isso. Para reproduzir siga os seguintes passos:

1. Coloque em um form um SQLConnection, SQLQuery, DataSetProvider, ClientDataSet, DataSource, DBGrid, Button e um Edit. Conecte todos os objetos de dados para que possamos ver o resultado do CDS na grid.

2. Conecte o SQLConnection no banco employee.gdb que acompanha os demos do Delphi (..\BDS\3.0\Demos\CSharp\Applications\CalendarQuery\employee.gdb).

3. No bot&atilde;o, coloque o seguinte c&oacute;digo:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;  ClientDataSet1.Close;
  SQLQuery1.SQL.Text := &#039;SELECT * FROM CUSTOMER WHERE STATE_PROVINCE = :STATE&#039;;
  SQLQuery1.ParamByName(&#039;STATE&#039;).AsString := Edit1.Text;
  ClientDataSet1.Open;
&lt;/code&gt;</pre>

4. Agora digite &#8220;ON&#8221; no edit e clique no bot&atilde;o. Um registro ser&aacute; mostrado.

5. Agora digite &#8220;CA&#8221; no edit e clique novamente no bot&atilde;o. Se voc&ecirc; estiver usando o D7, novos registros ser&atilde;o mostrados, mas se voc&ecirc; estiver usando o D2005, **NADA ACONTECE!**

Na minha opini&atilde;o &eacute; um bug absurdo, que afeta muita gente.

E o pior!!! Ele j&aacute; foi reportado para a Borland em janeiro! Veja aqui no [QC#10708][1]. Antes do Update 2 do Delphi 2005 e nada de solu&ccedil;&atilde;o at&eacute; agora, mesmo depois de dois updates!!! 

Sei que j&aacute; est&aacute; rolando o field test para o Dexter, a nova vers&atilde;o do Delphi, mas e esses problemas?? E quem comprou o Delphi 2005?? Ter&aacute; que comprar o 2006 para ter o bug resolvido? Acho isso uma grande falta de respeito com os clientes.. Parece brincadeira da Borland.

 [1]: http://qc.borland.com/wc/qcmain.aspx?d=10708