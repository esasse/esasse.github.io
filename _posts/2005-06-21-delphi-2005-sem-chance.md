---
title: 'Delphi 2005 &#8211; Sem chance'
author: Erick Sasse
layout: post
permalink: /delphi-2005-sem-chance/
dsq_thread_id:
  - 262147218
categories:
  - Delphi
---
Estou curioso para saber quem consegue usar o Delphi 2005 em produ&ccedil;&atilde;o. Ele tem muitos bugs absurdos. Alguns que eu detectei nesta minha &uacute;ltima tentativa de migrar do D7 para ele, j&aacute; com o Update 3 instalado:

  * ASP.NET n&atilde;o funciona em nenhum dos notebooks que tenho na empresa, incompatibilidade com placa de video ATI. (Problema antigo, j&aacute; reportado para a Borland h&aacute; mais de um ano. Vem desde o Delphi 8. J&aacute; comentei [aqui][1], [aqui][2] e [aqui][3])
  * Memory leaks absurdos, ontem por exemplo, por duas vezes minha m&aacute;quina estava consumindo 1,2GB de mem&oacute;ria virtual, estando apenas com o D2005 aberto. 
  * N&atilde;o consigo selecionar mais de um componente simultaneamente em um data module. Inacredit&aacute;vel.. 
  * O Enumerator do TObjectList n&atilde;o foi implementado e apenas herdou de TList, ent&atilde;o ele retorna Pointer e n&atilde;o TObject!!!!! 
  * Aplicativos com DBExpress geram erros estranhos em comandos SQL. Por exemplo, tenho uma consulta que dispara um SQL do tipo &#8220;SELECT CODIGO, NOME FROM CLIENTES WHERE BLOQUEADO = 1&#8243;. Quando eu abro esse dataset pela primeira vez, sem problemas, mas se eu dou um Close e um Open, ele simplesmente d&aacute; erro de &#8220;Token Unkown WHERE&#8221;. Isso simplesmente n&atilde;o acontece no Delphi 7.
  * Update: Quando abro um form Win32, os componentes não visuais simplesmente não aparecem. Eles estão lá, mas não aparecem. Tenho que clicar em um componente visual e mexer nele, meio que forçando um &#8220;refresh&#8221; do form para as vezes os componentes não visuais aparecerem. Usso também acontecia no Delphi 8. Pode ser algo relacionado a placa de video ATI do meu note.

Enfim, o neg&oacute;cio n&atilde;o tem condi&ccedil;&otilde;es de ser utilizado n&atilde;o.. algu&eacute;m aqui, que teve coragem de encarar, n&atilde;o teve problemas?

 [1]: http://www.ericksasse.com.br/?p=78
 [2]: http://www.ericksasse.com.br/?p=167
 [3]: http://www.ericksasse.com.br/?p=252