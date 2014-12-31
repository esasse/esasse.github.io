---
title: 'Regras de Negócio: No BD ou no aplicativo?'
author: Erick Sasse
layout: post
permalink: /regras-de-negcio-no-bd-ou-no-aplicativo/
dsq_thread_id:
  - 262145203
categories:
  - Firebird
  - Geral
  - Mobilidade
tags:
  - Geral
---
Quando eu sai do MS Access e descobri o Interbase (pai do Firebird), fiquei maravilhado com os recursos, principalmente triggers e stored procedures. Percebi que com isso eu conseguiria transportar grande parte da l&oacute;gica do meu aplicativo para o servidor, liberando a esta&ccedil;&atilde;o de algumas tarefas e deixando o aplicativo mais simples. 

Minhas aplica&ccedil;&otilde;es s&atilde;o Cliente-Servidor 2 camadas apenas, ent&atilde;o meu relato aqui &eacute; baseado nesse tipo de aplicativo.

Ent&atilde;o passei a criar SPs indiscriminadamente para qualquer &#8220;opera&ccedil;&atilde;ozinha&#8221; que n&atilde;o teria ganho nenhum usando SP. N&atilde;o sei porque, mas eu pensava: &#8220;Ah, mas se a l&oacute;gica dessa opera&ccedil;&atilde;o mudar, eu n&atilde;o precisarei recompilar o aplicativo, apenas alterar a SP no banco! Que beleza! Todos os meus problemas acabaram!&#8221;. 

Hoje eu penso nisso e dou risada. Essa id&eacute;ia se mostrou totalmente errada. &Eacute; muito mais simples eu alterar o aplicativo, gerar um novo release e enviar para o cliente do que modificar a estrutura do BD dele. L&oacute;gico que alterar a estrutura de forma automatizada &eacute; poss&iacute;vel, mas mesmo assim, voc&ecirc; esbarra numa s&eacute;rie de probleminhas muito mais chatos do que simplesmente substituir o aplicativo pela nova vers&atilde;o. Muitas vezes voc&ecirc; n&atilde;o consegue modificar a estrutura com usu&aacute;rios logados, ai seu cliente tem que tirar todo mundo do sistema. Em grandes empresas isso pode ser bem complicado. Al&eacute;m disso, acontece com frequ&ecirc;ncia de voc&ecirc; n&atilde;o conseguir modificar a estrutura mesmo quando todos os usu&aacute;rios sairam do sistema, ent&atilde;o voc&ecirc; tem que reiniciar o servi&ccedil;o do BD, e por ai vai.

Outro detalhe &eacute; que se voc&ecirc; usar uma boa orienta&ccedil;&atilde;o a objetos no seu aplicativo, a tend&ecirc;ncia &eacute; deixar todas as regras de neg&oacute;cio nos seus objetos de neg&oacute;cio e n&atilde;o no BD, afinal &eacute; pra isso que os objetos servem. Perceber&aacute; que o banco de dados vai atuar como um simples meio de persist&ecirc;ncia dos dados, muitas vezes n&atilde;o utilizando nenhum dos seus principais recursos como triggers, integridade referencial, etc. &Eacute; muito comum ver BDs de aplicativos orientados a objeto com nenhum relacionamento entre as tabelas, nem nada.

Outra vantagem de colocar pouca l&oacute;gica no BD, &eacute; que voc&ecirc; acaba ficando menos dependente do banco de dados. N&atilde;o que voc&ecirc; consiga ficar totalmente independente, mas isso certamente ajudar&aacute;.

L&oacute;gico que em muitas situa&ccedil;&otilde;es, a melhor coisa &eacute; tirar proveito do poder do banco. Eu tenho muitos relat&oacute;rios processados inteiramente em SPs, controle de estoque gerenciado por triggers (muito bom), etc. O ideal &eacute; saber dosar a quantidade certa de um e de outro.

Por&eacute;m, existem casos que deixar o m&aacute;ximo de l&oacute;gica no banco &eacute; a melhor solu&ccedil;&atilde;o. 

Estou trabalhando em um aplicativo bem interessante para a plataforma PalmOS. O aplicativo vai rodar em equipamentos [Tungsten C][1], acessando banco de dados Firebird via Wi-Fi. O meu aplicativo PalmOS &eacute; apenas uma das interfaces de acesso ao sistema do cliente, cuja interface principal &eacute; toda web e foi criada por outra empresa. Este sistema j&aacute; est&aacute; rodando no cliente e n&oacute;s temos que estudar como ele funciona para desenvolvermos o m&oacute;dulo PalmOS. Existem v&aacute;rias regras, algumas bem complexas, que n&oacute;s n&atilde;o precisamos nem ter conhecimento se elas estiverem programadas no banco. 

Por exemplo, se o cliente compra acima do seu limite, o pedido entra na fila de aprova&ccedil;&atilde;o por um gerente. O m&oacute;dulo Palm n&atilde;o precisa saber disso, basta ele inserir o pedido. Neste momento um trigger &eacute; disparado, consulta o limite do cliente, o valor do pedido e seta o flag no pedido para ficar pendente de aprova&ccedil;&atilde;o ou liberado. Essa &eacute; uma forma inteligente de centralizar a l&oacute;gica no banco. Se a empresa que faz o sistema mudar a l&oacute;gica de aprova&ccedil;&atilde;o do pedido, eles nem precisam acionar a minha empresa para atualizar o m&oacute;dulo Palm.

A forma mais profissional de resolver isso seria ter uma camada intermedi&aacute;ria acessada tanto pelo aplicativo web, como pelo aplicativo Palm, e a l&oacute;gica ficaria somente neste aplicativo e ter&iacute;amos uma solu&ccedil;&atilde;o multi-camadas. Mas isto n&atilde;o &eacute; poss&iacute;vel, visto que o aplicativo web de retaguarda &eacute; duas camadas e j&aacute; est&aacute; pronto.

Se estivessemos falando de aplicativos desenvolvidos em .NET e o m&oacute;dulo port&aacute;til usando PocketPC (que suporta .NET Compact Framework), poder&iacute;amos compartilhar classes de neg&oacute;cio, o que poderia ser usado para evitar colocar muita l&oacute;gica no BD, mas esse n&atilde;o &eacute; o caso.

 [1]: http://www.palmone.com/us/products/handhelds/tungsten-c/