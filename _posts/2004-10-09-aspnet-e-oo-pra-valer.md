---
title: ASP.NET e OO pra valer
author: Erick Sasse
layout: post
permalink: /aspnet-e-oo-pra-valer/
dsq_thread_id:
  - 263288595
categories:
  - Microsoft
---
Ontem trabalhei o dia todo em meu primeiro projeto real em ASP.NET. Adoraria ter utilizado o Delphi 8 para isso, mas um [conhecido bug][1] me impede de utiliz&aacute;-lo no meu notebook. Minha esperan&ccedil;a &eacute; que o Diamondback n&atilde;o venha com esse problema.

Bom, mas voltando ao projeto, os requisitos eram simples. Apenas incluir um sistema de not&iacute;cias din&acirc;micas em um site j&aacute; existente, algo bem parecido com um blog. Na p&aacute;gina principal do site, o t&iacute;tulo das &uacute;ltimas not&iacute;cias seriam listadas. Ao clicar no t&iacute;tulo, uma p&aacute;gina com a not&iacute;cia completa seria exibida. Al&eacute;m disso, precisaria existir uma &aacute;rea administrativa restrita onde o jornalista pudesse gerenciar as not&iacute;cias.

Utilizei Visual Studio .NET 2003 e C#. Confesso que foi muito mais simples do que pensei. Achei que teria dificuldades em inserir c&oacute;digo ASP.NET em p&aacute;ginas HTML j&aacute; prontas e formatadas com tables, flash, e todas essas coisas que eu n&atilde;o gosto. Mas para converter uma p&aacute;gina HTML em ASPX (extens&atilde;o das p&aacute;ginas ASP.NET) bastava incluir a p&aacute;gina no projeto do VS (Visual Studio) e renomear a extens&atilde;o. O VS detecta que a p&aacute;gina n&atilde;o tem uma classe derivada de WebForm e cria uma automaticamente para voc&ecirc;.

N&atilde;o tinha experi&ecirc;ncia com Visual Studio e nem C# al&eacute;m dos testes e treinamentos MSDN que realizei. Inicialmente pensei em tirar proveito de tudo que a IDE pudesse gerar automaticamente para mim, pois n&atilde;o podia investir muito tempo nesse projeto. Mas depois, percebi que n&atilde;o era uma boa, pois estava ficando com v&aacute;rios componentes duplicados entre as p&aacute;ginas e n&atilde;o estava gostando disso. Por exemplo, se voc&ecirc; adotar o &#8220;m&eacute;todo f&aacute;cil&#8221;, arrastando para as p&aacute;ginas a tabela do banco de dados que voc&ecirc; quer acessar, a IDE cria todos os componentes para acesso: OleDBConnection, etc. Ent&atilde;o para cada p&aacute;gina voc&ecirc; teria todo o conjunto de objetos de conex&atilde;o repetidos. Isso seria um inferno para manter. Decidi abandonar tudo e usar uma abordagem mais orientada a objetos, que recomendo a todos.

O novo design do aplicativo envolveu praticamente duas classes principais, uma que representa as noticias chamada Noticia e outra que faz a persist&ecirc;ncia do objeto Noticia no banco de dados Access chamada NoticiaDAO (DAO = Data Access Object).

Uma r&aacute;pida engenharia reversao do c&oacute;digo no Visio me retornou esse modelo das duas classes:

<img src="/erick/imagens/webnews.png" alt="" border="0" />

Com essa abordagem ficou tudo muito f&aacute;cil. Quando quero listar as noticias, simplesmente instancio um objeto DAO e executo o m&eacute;todo ListarNoticias, que me retorna um ArrayList (parecido com o TObjectList do Delphi) com objetos Noticia. Quando uma noticia &eacute; alterada ou inclu&iacute;da, executo o m&eacute;todo SalvarNoticia do DAO e a noticia &eacute; salva no banco. O mesmo para exclus&atilde;o. 

Ou seja, toda a l&oacute;gica e componentes de acesso ao banco de dados ficam internos a classe DAO, e n&atilde;o espalhados pelo aplicativo. Isso facilita a manuten&ccedil;&atilde;o de forma absurda. Imagine que amanh&atilde; quero utilizar Firebird ao inv&eacute;s de Access. Onde preciso mexer? Somente na classe DAO. Ou ent&atilde;o quero salvar em XML e n&atilde;o usar mais banco de dados. Onde preciso mexer? Somente na classe DAO. Notou a facilidade? Se eu tivesse usado a primeira abordagem, teria que alterar TODAS as p&aacute;ginas para modificar o meio de persist&ecirc;ncia.

E em .NET essa abordagem &eacute; ainda mais f&aacute;cil de ser utilizada pois o DataGrid por exemplo, aceita um ArrayList como DataSource e simplesmente lista todos seus objetos na grid, sem nenhuma codifica&ccedil;&atilde;o adicional! &Eacute; fant&aacute;stico. O bom &eacute; que isso vale para Delphi .NET tamb&eacute;m!

Claro, esse &eacute; um exemplo extremamente simplista, mas n&atilde;o deixa de mostrar como voc&ecirc; pode facilitar sua vida e produzir software de melhor qualidade utilizando objetos de neg&oacute;cio.

 [1]: http://www.cadena.com.br/erick/archives/000077.html