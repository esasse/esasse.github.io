---
title: Monitorando comunicação com o banco de dados no RemObjects DataAbstract
author: Erick Sasse
layout: post
permalink: /monitorando-comunicacao-com-o-banco-de-dados-no-remobjects-dataabstract/
dsq_thread_id:
  - 262150600
categories:
  - Delphi
  - RemObjects
---
Durante o desenvolvimento, eu sempre monitoro toda comunicação do aplicativo com o banco de dados. Isso ajuda muito a melhorar o aplicativo e otimizar a comunicação.

No [DataAbstract][1] é muito fácil monitorar essa comunicação. No componente DriverManager (TDADriverManager), basta setar a propriedade TraceActive para True, marcar todos os tipos de comandos que deseja logar na propriedade TraceFlags e implementar um handler para o evento OnTraceEvent que é disparado a cada comunicação com o banco.

Eu monitoro tudo usando a Debug Window do [GExperts][2], perfeita para esse tipo de coisa.

 [1]: http://www.remobjects.com/da
 [2]: http://www.gexperts.org/tour/index.html?debug_window.html