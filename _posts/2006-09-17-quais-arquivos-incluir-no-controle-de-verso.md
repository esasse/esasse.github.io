---
title: 'Quais arquivos incluir no controle de vers&atilde;o'
author: Erick Sasse
layout: post
permalink: /quais-arquivos-incluir-no-controle-de-verso/
dsq_thread_id:
  - 262149381
categories:
  - Geral
tags:
  - Geral
---
Alguns leitores me pediram para descrever quais arquivos eu incluo no controle de versão (no meu caso, [Subversion][1]).

Basicamente eu incluo tudo que não pode ser gerado automaticamente. Todo o código fonte, o script para criação do instalador, o script para criação do banco de dados, o script de build, o arquivo de projeto do gerador de help e manual, ícones e gráficos usados pelo aplicativo e algum arquivo com documentação técnica adicional.

Não incluo código de terceiros, como componentes e bibliotecas que não são mantidos por mim. Isso é uma opção minha, algumas pessoas controlam a versão de componentes de terceiros também. Eu não senti necessidade disso até hoje.

Agora existem arquivos que você realmente não deve incluir, pois são gerados a partir dos outros já inclusos. Exemplo: DCU, EXE, FDB (banco de dados Firebird), BPL, DLL, HLP, CHM, etc. 

Claro que cada empresa tem uma realidade. Já vi gente que inclui até EXE no controle de versão. Eu acho absurdo. A melhor forma de decidir o que você vai incluir no controle de versão é saber exatamente a função de cada arquivo que você está incluindo e verificar se é realmente necessário.

 [1]: http://en.wikipedia.org/wiki/Subversion_(software)