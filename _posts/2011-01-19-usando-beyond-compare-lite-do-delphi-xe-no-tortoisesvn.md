---
title: Usando Beyond Compare Lite do Delphi XE no TortoiseSVN
author: Erick Sasse
layout: post
permalink: /usando-beyond-compare-lite-do-delphi-xe-no-tortoisesvn/
dsq_thread_id:
  - 262151583
categories:
  - Delphi
---
Há um bom tempo eu tenho usado a própria ferramenta de diff que acompanha o TortoiseSVN e estou satisfeito.

Mas hoje lembrei que no Delphi XE você recebe a versão Lite do Beyond Compare e decidi testar. Como não uso a integração da IDE com o SVN, decidi trocar no Tortoise.

Basta ir em Settings, External Programs, Diff Viewer, setar para External e colocar a linha de comando abaixo fazendo os devidos ajustes para a pasta onde você tem o Delphi XE instalado:

`C:\Program Files (x86)\Embarcadero\RAD Studio\8.0\bin\BCompareLite.exe %base %mine /title1=%bname /title2=%yname /leftreadonly`

[<img class="size-full wp-image-1125 alignnone" title="TortoiseDiff" src="http://www.ericksasse.com.br/wp-content/uploads/2011/01/TortoiseDiff.jpg" alt="" width="699" height="464" />][1]

Não sei se dá pra usar para Merge também, isso vou deixar para ver depois, se gostar do diff dele.

 [1]: http://www.ericksasse.com.br/wp-content/uploads/2011/01/TortoiseDiff.jpg