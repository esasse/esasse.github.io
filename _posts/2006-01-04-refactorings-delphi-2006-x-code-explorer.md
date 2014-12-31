---
title: Refactoring Delphi 2006 x Code Explorer
author: Erick Sasse
layout: post
permalink: /refactorings-delphi-2006-x-code-explorer/
dsq_thread_id:
  - 262148621
categories:
  - Delphi
---
Ok, os refactorings melhoraram muito no Delphi 2006 e certamente são melhores do que nada, mas os do [Code Explorer ][1]são muito mais práticos e poderosos, veja dois exemplo:

**Declare Variable (Delphi 2006) / Add Local Var (Code Explorer)**

Tenho a seguinte linha de código:

`SL := TStringList.Create;`

Para eu consegui usar o refactoring do Delphi, eu preciso posicionar meu cursor no nome da variável, ou seja, no &#8220;S&#8221; ou no &#8220;L&#8221;. Se eu não posicionar no nome, ele nem habilita o refactoring. Além disso, quando eu disparo o refactoring do Delphi (Ctrl+Shift+V), ele não identifica o tipo (TStringList), sugerindo como TObject, então tenho que digitar o tipo manualmente:

[<img border="0" src="http://static.flickr.com/43/82270490_20face1bbd_m.jpg" />][2]

Já com o Code Explorer, o cursor pode estar em qualquer lugar da linha, ou seja, você não precisa se preocupar com isso. Disparo o Add Local Var (Ctrl+L) do Code Explorer e ele já faz tudo certinho, identificando o tipo perfeitamente:

[<img border="0" src="http://static.flickr.com/43/82270491_5d7f634be1_m.jpg" />][3]

Depois disso, basta um Enter, e pronto:

<img border="0" src="http://static.flickr.com/42/82270493_86ba218588_o.png" />

**Surround (Delphi 2006) / Try..Finally Wizard (Code Explorer)**

Aqui é pura covardia, o Code Explorer mata a pau. Adicionei uma linha no meu código e agora tenho isso na tela:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;procedure TForm10.FormCreate(Sender: TObject);
var
SL: TStringList;
begin
SL := TStringList.Create;
SL.Add(&#039;Refatorando&#039;);
end;&lt;/code&gt;</pre>

O Delphi 2006 tem um recurso chamado Surround, que lhe permite envolver o código dentro de uma nova estrutura, entre elas, try..finally. Para eu usar isso, eu preciso selecionar minha última linha (antes do end), clicar com o botão direito, selecionar Surround e depois tryf:

[<img border="0" src="http://static.flickr.com/37/82278640_ea25c59027.jpg" />  
][4]

O resultado mostrado abaixo precisa de uma leve formatação manual no código, e também da inclusão da instrução de liberação da variável (SL.Free):

<img border="0" src="http://static.flickr.com/36/82278642_57e1d393d4_o.png" />

Já no Code Explorer, basta eu posicionar na linha (não preciso nem selecionar):

![][5]

E teclar Ctrl+Alt+J, olhem o resultado:

<img border="0" src="http://static.flickr.com/41/82278643_6fff755cca_o.png" />

Perfeito, não? Inclusive a liberação da variável é incluída automaticamente. Show de bola!

**Update:** Para mais informações sobre estes refactorings do Code Explorer, dê uma olhada [aqui][6] e [aqui][7], onde eles são melhor explicados.

 [1]: http://www.modelmakertools.com/code-explorer/index.html
 [2]: http://static.flickr.com/43/82270490_20face1bbd_o.png
 [3]: http://static.flickr.com/43/82270491_5d7f634be1_o.png
 [4]: http://static.flickr.com/37/82278640_ea25c59027_o.png
 [5]: http://static.flickr.com/43/82283447_2903932711_o.png
 [6]: http://www.modelmakertools.com/articles/add-local-var.html
 [7]: http://www.modelmakertools.com/articles/try-finally-wizard.html