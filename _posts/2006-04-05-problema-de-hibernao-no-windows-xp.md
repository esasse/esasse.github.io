---
title: 'Problema de Hiberna&ccedil;&atilde;o no Windows XP'
author: Erick Sasse
layout: post
permalink: /problema-de-hibernao-no-windows-xp/
dsq_thread_id:
  - 262147950
categories:
  - Geral
tags:
  - Geral
---
Frequentemente quando eu tentava hibernar minha m&aacute;quina eu recebia essa mensagem:

**Recursos de sistema insuficientes para completar a API.**

Eu achava estranho, porque minha m&aacute;quina tem 1,25GB de RAM, n&atilde;o deveria faltar recursos. Mas acabei nunca indo atr&aacute;s do problema at&eacute; que vi [este post][1] do Coding Horror falando sobre isso.

Resumindo, &eacute; um bug no Windows XP SP2 e que j&aacute; foi [identificado][2] e corrigido pela Microsoft. O &uacute;nico detalhe &eacute; que o download da corre&ccedil;&atilde;o n&atilde;o &eacute; p&uacute;blico, obrigando voc&ecirc; a entrar em contato com o suporte da Microsoft solicitando. 

Entrei em contato com a Microsoft e fiquei surpreso com a rapidez no atendimento de suporte deles. No primeiro momento n&atilde;o quiseram me disponibilizar a atualiza&ccedil;&atilde;o porque a licen&ccedil;a do meu Windows &eacute; de uma assinatura MSDN (!?). Fiquei estupefato e bati o p&eacute;. Como que uma empresa de desenvolvimento, assinante da MSDN, n&atilde;o poderia receber a corre&ccedil;&atilde;o? Hehe.. alguns minutos depois a URL e senha para baixar j&aacute; estavam no meu e-mail.

Atualiza&ccedil;&atilde;o instalada, s&oacute; esperar para ver se o problema n&atilde;o acontece novamente.

 [1]: http://www.codinghorror.com/blog/archives/000555.html
 [2]: http://support.microsoft.com/?kbid=909095