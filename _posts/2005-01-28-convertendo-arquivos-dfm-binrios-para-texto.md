---
title: Convertendo arquivos DFM binários para texto
author: Erick Sasse
layout: post
permalink: /convertendo-arquivos-dfm-binrios-para-texto/
dsq_thread_id:
  - 262142866
categories:
  - Delphi
---
Os arquivos .DFM no Delphi s&atilde;o arquivos que mantem as informa&ccedil;&otilde;es dos componentes presentes em cada form. Informa&ccedil;&otilde;es como posicionamento dos componentes, tamanho, valor das propriedades, etc. Esses arquivos eram no in&iacute;cio bin&aacute;rios e em certo ponto da evolu&ccedil;&atilde;o do Delphi, ele come&ccedil;ou a suportar estes arquivos em texto puro.

Por que isso &eacute; bom? Isso &eacute; &oacute;timo na verdade para sistemas de controle de vers&atilde;o. Se tenho um form com 100 componentes o DFM vai ficar gigante, com centenas de linhas. Se eu mudo apenas um componente de lugar no form, mesmo que seja um componente n&atilde;o visual, o DFM &eacute; atualizado. Em casos como esse, apenas uma ou duas linhas do DFM s&atilde;o alteradas. Se ele estiver no formato texto, os sistemas de controle de vers&atilde;o mais inteligentes como o [SubVersion][1] armazenam apenas as modifica&ccedil;&otilde;es realizadas de uma revis&atilde;o para outra, ou seja, uma ou duas linhas. Se o arquivo &eacute; bin&aacute;rio, ele n&atilde;o consegue comparar, e tem que copiar novamente o arquivo inteiro para seu reposit&oacute;rio. Deu pra imaginar o tamanho da economia, n&atilde;o?

Mas outra grande vantagem &eacute; que as vers&otilde;es do seu DFM tamb&eacute;m poder&atilde;o ser comparadas por softwares que comparam c&oacute;digo fonte, e voc&ecirc; poder&aacute; ver com facilidade as mudan&ccedil;as em propriedades dos seus componentes de uma vers&atilde;o para outra.

Resumindo, escrevi tudo isso s&oacute; pra falar que hoje descobri que um utilit&aacute;rio que acompanha o Delphi que converte arquivos DFM. Tando de bin&aacute;rio para texto, como ao contr&aacute;rio. Eu tinha alguns forms ainda com DFM bin&aacute;rio. Geralmente estes forms vem de vers&otilde;es antigas do Delphi, que vamos migrando, e converti todos em uma tacada s&oacute;:

`convert -t -i -s *.dfm`

Esse c&oacute;digo converte todos os arquivos .dfm para texto, a partir do diret&oacute;rio que voc&ecirc; estiver e todos os subdiret&oacute;rios. Caso queira apenas no diret&oacute;rio atual, remova o &#8220;-s&#8221;.

Mas aten&ccedil;&atilde;o, se voc&ecirc; converter seus forms para texto n&atilde;o conseguir&aacute; mais abr&iacute;-lo em vers&otilde;es do Delphi que n&atilde;o suportam isso. N&atilde;o me lembro em qual vers&atilde;o esse recurso foi introduzido, portanto, saiba o que est&aacute; fazendo.

Al&eacute;m disso, para garantir que seus novos forms s&atilde;o criados em texto, no Delphi 7 verifique a op&ccedil;&atilde;o em *Tools -> Environment Options -> Designer -> New forms as text*. No Delphi 2005 em *Tools -> Options -> VCL Designer*.

 [1]: http://subversion.tigris.org