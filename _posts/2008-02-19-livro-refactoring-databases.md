---
title: Livro Refactoring Databases
author: Erick Sasse
layout: post
permalink: /livro-refactoring-databases/
dsq_thread_id:
  - 262150779
categories:
  - Livros
  - Reviews
tags:
  - banco de dados
  - livro
  - refactoring
  - review
---
<img src="http://www.ericksasse.com.br/wp-content/uploads/2008/02/51szmehjyel_aa240_.jpg" alt="Capa Livro Refactoring Databases" align="right" />Alguns dias atrás eu terminei de ler Refactoring Databases &#8211; Evolutionary Database Design ([Amazon][1]). Um dos autores do livro é o [Scott Ambler][2], muito conhecido por aqueles que se interessam mais por OO. O livro também é parte da série [Signature][3] do Martin Fowler.

Esse livro me foi indicado quando eu procurava definir um design para sistemas dinâmicos, ou seja, um sistema que fosse construído conectando módulos reutilizáveis de outros sistemas. Infelizmente o livro não me ajudou nada nisso. <img src="http://www.ericksasse.com.br/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" />

A concepção do livro é praticamente idêntica ao famoso livro de [Refactoring][4] do Martin Fowler, porém é direcionado a refatorar a estrutura de bancos de dados.

Existem dezenas de refactorings catalogados e separados em diferentes tipos como *structural refactorings, data quality refactorings, referencial integrity refactorings*, etc.

Para cada refactoring ele descreve a motivação, os problemas que você pode enfrentar durantes o processo, quais as tarefas para modificação da estrutura e migração dos dados.

Para servir de exemplo, vamos pegar o primeiro structural refactoring: *Drop Column*.

  * Motivação: A principal motivação para este refactoring é quando uma coluna não é mais usada.
  * Problemas: A coluna sendo removida pode conter dados importantes e você pode precisar preservar os dados.
  * Modificação da estrutura (schema): Remover coluna, constraints e foreign keys (se existirem).
  * Migração dos dados: Caso seja necessário manter os dados (para referência futura ou compatibilidade com outros aplicativos), a sugestão é criar uma tabela auxiliar com a chave primária da tabela e a coluna removida.

Grande parte do livro trata de manter compatibilidade e disponibilidade do banco. Por exemplo, se você tem vários aplicativos acessando o banco, sendo que estes aplicativos não são seus e você não pode alterá-los, a cada modificação na estrutura você deve manter um período de transição e compatibilidade, e o livro detalha várias técnicas para fazer isso.

Como meus bancos são sempre acessados apenas por meus aplicativos, todo esse conteúdo, apesar de interessante, não me foi de grande utilidade. E fora essa parte, o resto é tudo meio óbvio. Por isso não encontrei muita coisa que me ajudasse no livro.

Recomendo o livro especialmente para quem mantem grandes bancos de dados, acessado por muitos aplicativos. Se você mantem um banco de dados acessado apenas pelo seu aplicativo, acredito que não vai encontrar muita coisa útil no livro.

 [1]: http://www.amazon.com/exec/obidos/ASIN/0321293533
 [2]: http://www.ambysoft.com/
 [3]: http://www.martinfowler.com/books.html#series
 [4]: http://www.martinfowler.com/books.html#refactoring