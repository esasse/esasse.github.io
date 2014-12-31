---
title: Posicionando Janelas em Mais de Um Monitor
author: Erick Sasse
layout: post
permalink: /posicionando-janelas-em-mais-de-um-monitor/
dsq_thread_id:
  - 262317421
categories:
  - Delphi
---
Todo form da VCL tem uma propriedade Position, que &eacute; a posi&ccedil;&atilde;o onde o form aparece quando for mostrado. Se voc&ecirc; estiver usando dois monitores na mesma m&aacute;quina e selecionar poDesktopCenter na Position, seu form ficar&aacute; dividido entre os dois monitores, ou seja, metade em um, e metade em outro. Bizarro. <img src="http://www.ericksasse.com.br/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" />

Se voc&ecirc; deseja centralizar o form no monitor que seu aplicativo estiver sendo mostrado, utilize poScreenCenter. Como a maioria dos desenvolvedores ainda n&atilde;o usa mais de um monitor, quando colocamos poDesktopCenter, o form aparece no centro da tela e pensamos que est&aacute; tudo ok, pois nossa &aacute;rea de desktop &eacute; a mesma &aacute;rea da nossa tela. Quando voc&ecirc; tem mais de um monitor, seu desktop &eacute; extendido, passando a ser virtualmente muito maior.