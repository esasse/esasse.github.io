---
title: Extrair primeiro nome usando SQL
author: Erick Sasse
layout: post
permalink: /extrair-primeiro-nome-usando-sql/
dsq_thread_id:
  - 262151505
categories:
  - Firebird
  - SQL Server
---
Você tem um campo string onde guarda o nome completo e precisa escrever uma consulta que traga apenas o primeiro nome.

Eu cheguei ao resultado abaixo, não conseguindo uma consulta que funcionasse ao mesmo tempo com Firebird e SQL Server.

**Firebird**

`SELECT `<span style="font-family: monospace;">IIF(POSITION(&#8216; &#8216; IN NOME_COMPLETO) > 0, SUBSTRING(NOME_COMPLETO FROM 1 FOR POSITION(&#8216; &#8216; IN NOME_COMPLETO) &#8211; 1), NOME_COMPLETO) </span><span style="font-family: monospace;">FROM TABELA</span>

**SQL Server**

`SELECT CASE WHEN CHARINDEX(' ', NOME_COMPLETO) > 0 THEN SUBSTRING(NOME_COMPLETO, 1, CHARINDEX(' ', NOME_COMPLETO) - 1) ELSE NOME_COMPLETO END FROM TABELA`

Qualquer idéia melhor é bem-vinda.

UPDATE: Baseado no feedback recebido, refatorei a consulta, [veja aqui a versão 2][1].

 [1]: http://www.ericksasse.com.br/extrair-primeiro-nome-usando-sql-v2-0/