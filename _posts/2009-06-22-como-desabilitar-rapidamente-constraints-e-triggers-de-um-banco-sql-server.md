---
title: Como desabilitar rapidamente constraints e triggers de um banco SQL Server
author: Erick Sasse
layout: post
permalink: /como-desabilitar-rapidamente-constraints-e-triggers-de-um-banco-sql-server/
dsq_thread_id:
  - 262151106
categories:
  - SQL Server
tags:
  - SQL Server
---
Quando se está importando dados para um banco, as constraints e triggers podem ser um chato obstáculo. Em alguns casos poder ser muito mais fácil desabilitar tudo e reativar no final do processo. Pesquisando sobre isso, encontrei essa [ótima dica][1] no StackOverflow.

**Para desabilitar todas as constraints e triggers de todas as tabelas do banco:**

`exec sp_msforeachtable "ALTER TABLE ? NOCHECK CONSTRAINT ALL"<br />
exec sp_msforeachtable "ALTER TABLE ? DISABLE TRIGGER ALL"`

**Para habilitar:**

`exec sp_msforeachtable "ALTER TABLE ? WITH CHECK CHECK CONSTRAINT ALL"<br />
exec sp_msforeachtable "ALTER TABLE ? ENABLE TRIGGER ALL"`

Alias, essa **sp_msforeachtable** é muito interessante e pode ser explorada de muitas formas diferentes. Testei no SQL Server 2008, mas deve funcionar no 2005 pelo menos.

Um detalhe a ser observado é que esse comando não desabilita constraint de PK nem UNIQUE.

 [1]: http://stackoverflow.com/questions/123558/sql-server-2005-t-sql-to-temporarily-disable-a-trigger/123966#123966