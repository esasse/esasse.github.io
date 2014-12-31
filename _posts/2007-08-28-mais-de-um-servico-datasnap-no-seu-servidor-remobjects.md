---
title: Mais de um serviço DataSnap no seu servidor RemObjects
author: Erick Sasse
layout: post
permalink: /mais-de-um-servico-datasnap-no-seu-servidor-remobjects/
dsq_thread_id:
  - 262150299
categories:
  - Delphi
  - RemObjects
---
Meu [post][1] sobre como criar um servidor DataSnap passo a passo com o RemObjects SDK foi muito bem aceito, fiquei bem satisfeito. O pessoal precisava disso mais do que eu pensava. <img src="http://www.ericksasse.com.br/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" />

Uma pergunta que surgiu mais de uma vez depois da publicação do artigo foi sobre como colocar mais de um DataModule no servidor. E é bem simples de se fazer. Basta adicionar novos serviços descendentes de AppServer no servidor utilizando o Service Builder do RemObjects. Depois disso, para cada serviço novo no servidor você precisa de um novo RODataSnapConnection no cliente com o ServerName preenchido com o mesmo nome do serviço.

É bem normal ter mais de um serviço DataSnap no servidor. Normalmente essa divisão se dá por áreas funcionais do aplicativo como por exemplo, Controle de Estoque, Financeiro, etc. Mas naturalmente você pode dividir da forma que preferir.

 [1]: /passo-a-passo-remobjects-sdk-e-datasnap/