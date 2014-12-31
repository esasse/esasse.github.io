---
title: Backup SQL Server Express via linha de comando
author: Erick Sasse
layout: post
permalink: /backup-sql-server-express-via-linha-de-comando/
dsq_thread_id:
  - 262151163
categories:
  - SQL Server
tags:
  - Backup
  - SQL Server
---
Uma das desvantagens das versões Express do SQL Server é não ter o SQL Agent, que te permite agendar backups e outras tarefas administrativas nos seus bancos de dados.

No caso do backup, você pode facilmente automatizar usando o agendador de tarefas e um arquivo .bat com os comandos abaixo, que já inclui a compactação usando [7-Zip][1]:

`sqlcmd.exe -S (local)\SQLExpress -Q "BACKUP DATABASE MeuBanco TO DISK='d:\backup\meubanco.bak' WITH FORMAT"<br /> `

`"c:\program files\7-zip\7z.exe" a d:\backup\meubanco.7z d:\backup\meubanco.bak`

É uma dica simples, mas que pode ser usada como ponto de partida para um script mais avançado e que atenda outras necessidades. Afinal, todo mundo precisa agendar backups de uma forma ou de outra.

E não esqueça de manter o backup bem longe do servidor. <img src="http://www.ericksasse.com.br/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" />

[![Não deixe para amanhã][2]][3]

 [1]: http://www.7-zip.org
 [2]: http://farm1.static.flickr.com/35/68017710_123de4638c_m.jpg
 [3]: http://www.flickr.com/photos/roadhunter/68017710/