---
title: Extraindo metadata de um banco Firebird
author: Erick Sasse
layout: post
permalink: /extraindo-metadata-de-um-banco-firebird/
dsq_thread_id:
  - 262142926
categories:
  - Firebird
---
Hoje precisei incluir no script de build de um projeto a extra&ccedil;&atilde;o autom&aacute;tica de metadata do banco de dados de desenvolvimento. Normalmente eu realizo esse processo manualmente atrav&eacute;s do IBExpert e n&atilde;o me lembrava como fazer isso via linha de comando. Um pouco de pesquisa na documenta&ccedil;&atilde;o do Interbase 6 (que ainda &eacute; a maior documenta&ccedil;&atilde;o dispon&iacute;vel para o Firebird, visto que este se originou a partir do IB6) e achei:

`isql -extract -o [nome arquivo] [banco de dados]`

Exemplo:

`isql -extract -o metadata.sql banco.fdb`

Onde *metadata.sql* &eacute; o arquivo que ser&aacute; gerado, e *banco.fdb* &eacute; meu banco Firebird supondo que ele est&aacute; no diret&oacute;rio atual. Claro que a pasta bin do Firebird tem que estar no path, pois &eacute; l&aacute; que o isql se encontra.

Uma das utilidades deste recurso &eacute; por exemplo incluir no seu build a extra&ccedil;&atilde;o de metadata e atualiza&ccedil;&atilde;o deste no controle de vers&atilde;o.