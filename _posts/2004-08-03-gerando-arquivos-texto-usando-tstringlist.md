---
title: Gerando arquivos texto usando TStringList
author: Erick Sasse
layout: post
permalink: /gerando-arquivos-texto-usando-tstringlist/
dsq_thread_id:
  - 262142541
categories:
  - Delphi
---
Antigamente para criar arquivos texto no Delphi eu usava vari&aacute;veis TextFile em conjunto com AssignFile, WriteLn e coisas do tipo. Hoje uso a classe TStringList, que al&eacute;m de muitas outras fun&ccedil;&otilde;es, tamb&eacute;m serve para isso:

`var<br />
&nbsp;&nbsp;Texto: TStringList;<br />
begin<br />
&nbsp;&nbsp;Texto := TStringList.Create;<br />
&nbsp;&nbsp;try<br />
&nbsp;&nbsp;&nbsp;&nbsp;Texto.Add('Linha 1');<br />
&nbsp;&nbsp;&nbsp;&nbsp;Texto.Add('Linha 2');<br />
&nbsp;&nbsp;&nbsp;&nbsp;Texto.SaveToFile('c:\teste.txt');<br />
&nbsp;&nbsp;finally<br />
&nbsp;&nbsp;&nbsp;&nbsp;Texto.Free;<br />
&nbsp;&nbsp;end;<br />
end;`

Na verdade a classe TStringList &eacute; uma classe subestimada no Delphi. Acho que ela deveria ser muito mais comentada. Ela &eacute; um verdadeiro canivete sui&ccedil;o, cheia de fun&ccedil;&otilde;es muito interessantes. Vale a pena dar uma estudada com calma nesta classe, vai te ajudar muito no futuro a n&atilde;o quebrar a cabe&ccedil;a reinventando a roda.