---
title: Configurando seu Aplicativo no Firewall do Windows com Inno Setup
author: Erick Sasse
layout: post
permalink: /configurando-seu-aplicativo-no-firewall-do-windows-com-inno-setup/
dsq_thread_id:
  - 262150672
categories:
  - Geral
tags:
  - Geral
---
Desde o XP SP2 (eu acho), o Windows tem seu próprio firewall, e isso é muito bom. Ele também está presente no Vista e nas versões Server. Eu sempre recomendo a todos manterem o firewall ativado, e fico desapontado quando profissionais de informática, e até mesmo programadores, muitas vezes reclamam que ele existe e desativam tudo. Isso acontece de forma ainda mais triste com o novo UAC do Windows Vista, que na minha opinião, é muito útil.

Acredito que esse tipo de comportamento seja mais por desconhecimento do sistema, do que por qualquer outra coisa. O bom desenvolvedor Windows precisa conhecer como esses componentes do sistema funcionam para poder trabalhar com eles de forma amigável.

Se você vai instalar seu servidor de aplicação ou seu servidor de banco de dados no Windows você vai precisar configurar seu aplicativo no firewall para que os usuários consigam conectar. E você pode fazer isso de forma automática e durante a instalação do aplicativo. Aqui na Cadena nós utilizamos o [Inno Setup][1], e [esta dica][2] nos ajudou muito quando precisamos incluir esse recurso em nossos instaladores.

A idéia é usar o utilitário de linha de comando **netsh**, que permite alterar praticamente qualquer configuração de rede do computador usando scripts ou comandos no prompt. Você pode encontrar [mais informação sobre ele][3] no site da Microsoft.

Testei esse script com sucesso no XP SP2, no Vista e no 2003 Server.

 [1]: http://www.jrsoftware.org/
 [2]: http://news.jrsoftware.org/news/innosetup/msg58347.html
 [3]: http://www.google.com/search?hl=pt-BR&#038;q=site%3Amicrosoft.com+netsh&#038;btnG=Pesquisa+Google&#038;lr=