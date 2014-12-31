---
title: Copiando arquivos sem a estrutura de pastas
author: Erick Sasse
layout: post
permalink: /copiando-arquivos-sem-a-estrutura-de-pastas/
dsq_thread_id:
  - 263170430
categories:
  - Linha de Comando
tags:
  - Linha de Comando
---
Esse comando me foi tão útil hoje que precisava compartilhar para tentar ajudar mais alguém.

Eu tinha uma árvore imensa de diretórios no Windows com arquivos espalhados em todas as pastas de todos os níveis. Precisava consolidar todos os arquivos em uma única pasta.

Pesquisei um pouco e cheguei a [essa dica][1] que resolveu meu problema em apenas uma linha de comando:

<pre class="wp-code-highlight prettyprint">For /r "c:\origem" %d in (*) do copy "%d" "E:\destino"</pre>

Esse comando varre toda a estrutura de pastas em c:\origem e copia para a pasta e:\destino. Como eu precisava mover os arquivos, fiz uma pequena adaptação:

<pre class="wp-code-highlight prettyprint">For /r "c:\origem" %d in (*) do move /Y "%d" "d:\destino"</pre>

Foi só deixar executando e algum tempo depois estava tudo como eu precisava. Fantástico. Espero que ajude mais alguém.

 [1]: http://geekswithblogs.net/chrishan/archive/2010/01/06/137373.aspx