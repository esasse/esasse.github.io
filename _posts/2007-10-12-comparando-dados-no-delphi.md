---
title: Comparando dados no Delphi
author: Erick Sasse
layout: post
permalink: /comparando-dados-no-delphi/
dsq_thread_id:
  - 262150446
categories:
  - Delphi
---
O Delphi fornece algumas funções bem úteis para comparar dados. Infelizmente parece que a maioria dos desenvolvedores não as conhecem. Tenho visto com muita freqüência o pessoal comparar strings assim:

if UpperCase(S1) = UpperCase(S2) then&#8230;

Você pode usar a função AnsiSameText para facilitar:

if AnsiSameText(S1, S2) then&#8230;

A comparação desconsidera maiúsculas e minúsculas e trata caracteres internacionais de acordo com o idioma do usuário.