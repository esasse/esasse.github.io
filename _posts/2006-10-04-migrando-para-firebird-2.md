---
title: Migrando para Firebird 2
author: Erick Sasse
layout: post
permalink: /migrando-para-firebird-2/
dsq_thread_id:
  - 262149439
categories:
  - Firebird
---
<img style="margin: 5px" src="http://www.firebase.com.br/fb/custimg/livro-fb2.jpg" align="right" />Já iniciamos o processo de adaptação dos nossos aplicativos para o Firebird 2 aqui na Cadena. Hoje saiu o [RC5][1], que tem grandes chances de ser a versão final.

O único ajuste necessário que encontramos até agora foi corrigir os comandos SQL que não usavam o alias das tabelas corretamente, o que no Firebird 2 é obrigatório. Exemplo:

<pre class="wp-code-highlight prettyprint">SELECT C.NOME, V.DATA, V.VALOR
  FROM VENDAS V
  JOIN CLIENTES C ON CLIENTES.CODIGO = VENDAS.CLIENTE
</pre>

Esse comando funcionaria no FB 1.x, mas não funciona no FB 2, pois você está definindo um alias para as tabelas, mas em outro local (nesse caso no JOIN) está usando o nome completo da tabela.

No FB 2, quando você declara um alias para uma tabela, você é obrigado a utilizá-lo em todo o SQL. Eu gostei dessa imposição, pois acaba deixar as instruções SQL mais organizadas.

Então essa instrução acima ficaria assim no FB 2:

<pre class="wp-code-highlight prettyprint">SELECT C.NOME, V.DATA, V.VALOR
  FROM VENDAS V
  JOIN CLIENTES C ON C.CODIGO = V.CLIENTE</pre>

Uma ótima referência para a migração e que está nos ajudando muito é o [livro Firebird 2 do Cantu][2]&nbsp;(foto acima).&nbsp;Ele traz todas as novidades e destaca as diferenças para quem está migrando.&nbsp; Se você trabalha com FB profissionalmente, é um investimento valioso.

 [1]: https://sourceforge.net/project/showfiles.php?group_id=9028&release_id=452742
 [2]: http://www.warmboot.com.br/fb/livro/fb2/