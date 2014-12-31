---
title: Extrair primeiro nome usando SQL v2.0
author: Erick Sasse
layout: post
permalink: /extrair-primeiro-nome-usando-sql-v2-0/
dsq_thread_id:
  - 262151543
categories:
  - Firebird
  - SQL Server
---
Fiz o refactoring aplicando as ótimas dicas que recebi do pessoal [no post anterior][1] e a versão 2.0 da consulta ficou assim:

**Firebird**

`SELECT LEFT(NOME_COMPLETO, POSITION(' ' IN (NOME_COMPLETO || ' '))) FROM TABELA`

**SQL Server**

`SELECT LEFT(NOME_COMPLETO, CHARINDEX(' ', NOME_COMPLETO + ' ') ) FROM TABELA`

Muito melhor! Obrigado pelas dicas.

 [1]: http://www.ericksasse.com.br/extrair-primeiro-nome-usando-sql/