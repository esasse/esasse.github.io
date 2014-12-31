---
title: Problemas com Delphi no Windows 7
author: Erick Sasse
layout: post
permalink: /problema-com-delphi-no-windows-7/
dsq_thread_id:
  - 262151021
categories:
  - Delphi
  - Microsoft
tags:
  - Delphi
  - windows
---
Depois de realizar mais testes, cheguei a conclusão que infelizmente o Windows 7 ainda não é uma boa opção para quem trabalha com Delphi.

Rodando o Delphi 2009 encontrei problemas na hora de usar o debugger em aplicativos com mais de uma thread. Quando uma exception é levantada, não é possível dar um break e resetar o aplicativo (Ctrl+F2) e você precisa reiniciar a IDE.

Já notifiquei o pessoal da CodeGear, mas como essa é uma versão beta e não suportada do Windows, não posso querer que eles resolvam.

Fica aí o alerta para os desenvolvedores Delphi.