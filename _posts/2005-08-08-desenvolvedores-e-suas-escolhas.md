---
title: Desenvolvedores e suas escolhas
author: Erick Sasse
layout: post
permalink: /desenvolvedores-e-suas-escolhas/
dsq_thread_id:
  - 262147564
categories:
  - Geral
tags:
  - Geral
---
Ser desenvolvedor nos dias de hoje n&atilde;o &eacute; nada f&aacute;cil. Novas tecnologias surgem a todo momento e voc&ecirc; vive constantemente tomando decis&otilde;es. Vou desenvolver em Windows ou Web? ASP.NET ou PHP? WebForms ou VCL? .Net ou Win32? Intraweb ou WebBroker? Report Builder ou Rave? Firebird ou SQLServer? Delphi ou C#? 

Enfim, voc&ecirc; precisa tomar muitas decis&otilde;es e estas decis&otilde;es s&atilde;o important&iacute;ssimas. Se voc&ecirc; trabalha em uma grande empresa, que tem algu&eacute;m que toma essas decis&otilde;es por voc&ecirc; e as imp&otilde;e, por pior que seja, j&aacute; tirou uma grande bucha das suas costas. Agora se voc&ecirc; &eacute; o respons&aacute;vel por tomar estas decis&otilde;es, tem que estar preparado. Algumas dessas decis&otilde;es podem significar meses ou at&eacute; anos de trabalho envolvido, sem falar no dinheiro direto investido em ferramentas, licen&ccedil;as, etc.

Alguns dias atr&aacute;s joguei uma pergunta para alguns amigos desenvolvedores (maioria Delpheiros): &#8220;Na sua opini&atilde;o, qual a melhor tecnologia para iniciar um projeto Windows (n&atilde;o web) que ser&aacute; mantido por anos a fio?&#8221;. As op&ccedil;&otilde;es eram:

  * VCL Win32
  * VCL.Net
  * WinForms
  * XAML WinFX (nova tecnologia que vir&aacute; com o Windows Vista)

Obtive poucas respostas, infelizmente, mas basicamente o concenso foi: &#8220;Se fosse um projeto com prazo curto, utilizaria VCL Win32, pois &eacute; a tecnologia que j&aacute; domino, mas se fosse prazo longo, faria em WinForms.&#8221; Além disso, duas outras opiniões me chamaram a aten&ccedil;&atilde;o:

1. VCL.Net foi muito mal cotado  
2. Para fazer em WinForms, o Delphi já não é tão atrativo

De fato, tenho observado os newsgroups da Borland sobre VCL.Net e pouqu&iacute;ssimas mensagens circulam por l&aacute;, o que aponta um grande desinteresse geral pela tecnologia. Sobre qual IDE usar para WinForms, confesso que tenho testado o Visual Studio j&aacute; h&aacute; algum tempo e ele est&aacute; melhorando muito. Em estabilidade, se comparado ao Delphi 2005, o Visual Studio est&aacute; muito a frente. 

Precisei usar o VS pela primeira algum tempo atr&aacute;s em um pequeno projeto, devido a um bug revoltante no D8 e D2005, que n&atilde;o cria projetos ASP.NET em nenhum dos notebooks HP aqui da empresa. Foi minha primeira experi&ecirc;ncia com C#. E gostei.

Agora resolvi come&ccedil;ar um novo projeto piloto usando VS 2005, C# e WinForms, e uma abordagem totalmente orientado a objetos, ou seja, sem usar datasets. Usando objetos de neg&oacute;cios para representar as entidades do meu sistema, al&eacute;m de um OPF (ou OR Mapper) para gerenciar o mapeamento de minhas classes com o banco de dados.

Estarei desenvolvendo o projeto nas horas vagas, e descrevendo o andamento aqui. Al&eacute;m disso, sempre que poss&iacute;vel estarei comparando o processo com o desenvolvimento Delphi VCL Win32, que &eacute; onde eu tenho mais conhecimento.

Para facilitar quem acompanha ou acompanhar&aacute; isso no futuro, estarei criando uma nova categoria para meus posts: Visual Studio, onde colocarei pontos relacionados a IDE de modo geral. T&oacute;picos relacionados a C# j&aacute; tem sua pr&oacute;pria categoria.