---
title: 'Vari&aacute;veis de ambiente do Firebird'
author: Erick Sasse
layout: post
permalink: /variveis-de-ambiente-do-firebird/
dsq_thread_id:
  - 262297394
categories:
  - Firebird
---
Se voc&ecirc; usa os utilit&aacute;rios de linha de comando do Firebird (gbak, gstat, gfix), j&aacute; deve estar enjoado de informar nome de usu&aacute;rio e senha todas as vezes que precisa executar um comando, n&atilde;o?

Para acabar com isso, voc&ecirc; pode definir as vari&aacute;veis de ambiente *isc_user* e *isc_password*, com o usu&aacute;rio e senha do seu banco. Os utilit&aacute;rios pesquisar&atilde;o a exist&ecirc;ncia destas vari&aacute;veis no ambiente e utilizar&atilde;o automaticamente sem que voc&ecirc; precise informa-las na linha de comando.

Lembre-se que isso deve ser usado apenas na sua m&aacute;quina de desenvolvimento, para n&atilde;o comprometer a seguran&ccedil;a do banco de produ&ccedil;&atilde;o.

Falando em Firebird, n&atilde;o esque&ccedil;a que este m&ecirc;s tem o [Firebird Developers Day][1] em Piracicaba, cidade vizinha daqui de Americana. &Eacute; um dos maiores eventos de Firebird do mundo, e conta inclusive com alguns palestrantes internacionais.

 [1]: http://www.firebirddevelopersday.com.br/