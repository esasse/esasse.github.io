---
title: Manipulando datas em arquivos batch do Windows
author: Erick Sasse
layout: post
permalink: /manipulando-datas-em-arquivos-batch-do-windows/
categories:
  - Geral
tags:
  - Geral
---
Olhem s&oacute; o script que montei ap&oacute;s algumas pesquisas na web e a impag&aacute;vel ajuda do amigo [Cantu][1]:

`FOR /f "tokens=2-4 skip=1 delims=(-)" %%G IN ('echo.^|date') DO (<br />
&nbsp;&nbsp;FOR /f "tokens=2 delims= " %%A IN ('date /t') DO (<br />
&nbsp;&nbsp;&nbsp;&nbsp;SET v_all=%%A<br />
&nbsp;&nbsp;)<br />
)<br />
SET dia=%v_all:~0,2%<br />
SET mes=%v_all:~3,2%<br />
SET ano=%v_all:~6,4%<br />
gbak -b banco.fdb %ano%%mes%%dia%.fbk`

Esse script gera backup de um banco de dados Firebird, usando a data atual para montar o nome do arquivo de destino.

Basta incluir esse script em um arquivo .BAT ou .CMD e programar no agendador de tarefas do Windows para ter um backup peri&oacute;dico automatizado.

Espero que ajude algu&eacute;m.

 [1]: http://www.firebase.com.br