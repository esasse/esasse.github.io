---
title: 'SQL Server 2008: Resolvendo erro &#8220;filegroup is full&#8221;'
author: Erick Sasse
layout: post
permalink: /sql-server-2008-resolvendo-erro-filegroup-is-full/
dsq_thread_id:
  - 1402599355
categories:
  - SQL Server
---
Ontem um banco de dados SQL Server 2008 Express começou a dar a seguinte mensagem de erro:

> System.Data.OleDb.OleDbException: Could not allocate space for object &#8216;XXX&#8217; in database &#8216;XXX&#8217; because the &#8216;PRIMARY&#8217; filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.

Obviamente a primeira coisa que eu fiz foi verificar as configurações dos arquivos do banco. E estava tudo certo, ou seja, crescimento dos arquivos irrestrito, autogrowth ativado, etc. Verifiquei espaço em disco e existiam dezenas de gigas livres.

Depois de uma pesquisada na Internet encontrei alguém que teve <a href="http://stackoverflow.com/questions/1951647/primary-filegroup-is-full-in-sql-server-2008-standard-for-no-apparent-reason" target="_blank">o mesmo problema</a> que eu, e resolveu apenas desfragmentando o disco onde o banco de dados estava.

Pois bem, parei o SQL Server e mandei desfragmentar o disco. Quando terminou, reiniciei o serviço do banco e pronto, problema resolvido! Eu achei bem estranho, algo que eu provavelmente não tentaria se não tivesse achado alguma dica, então achei que era algo que valia a pena compartilhar.

**UPDATE:** Alguns dias depois o problema voltou. Achei estranho porque depois do primeiro caso, agendamos o defrag automático dos discos durante a madrugada.  A mensagem era a mesma e não ajudava muito. Olhando nos logs do Windows fomos descobrir o real problema.

> CREATE DATABASE or ALTER DATABASE failed because the resulting cumulative database size would exceed your licensed limit of 4096 MB per database.

Alguém matou? Isso mesmo. Estávamos usando o SQL Server 2008 Express que é limitado a bancos de apenas 4GB e nosso banco tinha acabado de chegar nesse limite. Foi só atualizar para 2008 R2, que tem limite de 10GB, e o problema estava resolvido. Espero que desta vez em definitivo. Ou pelo menos até nosso banco chegar aos 10GB. <img src="http://www.ericksasse.com.br/wp-includes/images/smilies/icon_wink.gif" alt=";)" class="wp-smiley" />