---
title: Matriz de Dependência para Pascal
author: Erick Sasse
layout: post
permalink: /matriz-de-dependencia-para-pascal/
dsq_thread_id:
  - 262150793
categories:
  - Delphi
---
A ModelMakerTools e a Lattix, trazem uma ferramenta muito interessante para o nosso querido Pascal.

O [Lattix LDM for Delphi Pascal][1] analisa a estrutura de aplicativos Pascal baseado nas units e nas dependências entre elas para criar uma [Dependency Structure Matrix][2] (DSM ou Matriz de Dependência para simplificar).

A primeira vez que vi essa matriz foi com o [NDepend][3] para .NET e fiquei com inveja por não ter algo assim para Delphi Win32. Com essa matriz fica muito mais fácil analisar a arquitetura de grandes projetos e identificar pontos onde ele precisa ser melhorado.

Para entender melhor, existem alguns webcasts úteis [aqui][4].

 [1]: http://www.lattix.com/products/LDMforDelphiPascal.php
 [2]: http://www.lattix.com/technology/whatisdsm.php
 [3]: http://www.ndepend.com/
 [4]: http://www.lattix.com/dl/demo/demo10.html