---
title: 'Subversion: Apenas um repositório para todos os projetos'
author: Erick Sasse
layout: post
permalink: /subversion-apenas-um-repositorio-para-todos-os-projetos/
dsq_thread_id:
  - 262150966
  - 262150966
categories:
  - Geral
tags:
  - Subversion
---
Quando migrei meus projetos para o Subversion, tive aquela dúvida natural se deveria usar apenas um repositório para todos os projetos ou um repositório para cada projeto. Essa dúvida normalmente aparece devido ao número de revisão do repositório ser global e ser incrementado a cada commit.

Acabei optando por usar apenas um repositório para tudo, o que se mostrou uma ótima decisão pois algum tempo atrás passamos a usar o número da revisão do repositório como o número do build dos nossos projetos. Então quando vejo por exemplo uma versão 8.0.1.10423 sei que ela foi compilada com a revisão 10423 do nosso repositório. 

Isso é muito útil pois com esse número de revisão eu consigo ver exatamente a versão de cada um dos arquivos que foram utilizados nesse build, incluindo todas as bibliotecas compartilhadas, components, etc.

Fica aí a dica para quem está com a dúvida de um ou mais repositórios.