---
title: Subversion x JediVCS
author: Erick Sasse
layout: post
permalink: /subversion-x-jedivcs/
dsq_thread_id:
  - 262148932
categories:
  - Geral
tags:
  - Geral
---
Carlson, um dos leitores do meu blog, gostaria de saber qual sistema de controle de vers&atilde;o estou usando e qual a minha opini&atilde;o entre [Subversion][1] e [JediVCS][2].

Minha primeira experi&ecirc;ncia com controle de vers&atilde;o foi com o [FreeVCS][3], aplicativo que deu origem ao atual JediVCS. Eles s&atilde;o desenvolvidos em Delphi e eu inclusive cheguei a contribuir com algumas corre&ccedil;oes de bugs enquanto era usu&aacute;rio. Nesta &eacute;poca, existiam apenas 2 desenvolvedores investindo parte de seu tempo livre no desenvolvimento da ferramenta, que na &eacute;poca tinha muitos bugs e poucos interessados em ajudar.

O FreeVCS foi um divisor de &aacute;guas pra mim. At&eacute; ent&atilde;o eu n&atilde;o tinha nenhum controle de vers&atilde;o, era tudo muito amador, para n&atilde;o dizer prec&aacute;rio. Felizmente isso foi h&aacute; muitos anos atr&aacute;s.

O FreeVCS atendeu muito bem durante muito tempo at&eacute; que come&ccedil;ou a incomodar. Era chato para configurar o servidor como servi&ccedil;o, n&atilde;o suportava Firebird 1.5 (me obrigava a manter o 1.0 instalado no servidor paralelamente ao 1.5), tinha alguns bugs graves e principalmente, muitas limita&ccedil;&otilde;es, como n&atilde;o suportar branches, algo absolutamente obrigat&oacute;rio para qualquer VCS hoje em dia.

Quando participei de um curso de [SCM][4] um dos companheiros de curso comentou sobre um tal de Subversion, que ainda estava em vers&atilde;o beta mas que ele estava testando e gostando muito. Ele disse que resolvia v&aacute;rios problemas do famoso CVS, que eu nunca tinha usado, mas sabia ser o mais usado no mundo.

Resolvi conhecer a ferramenta. Baixei ele junto com o [TortoiseSVN][5], que o integra totalmente ao shell do Windows, estudei o livro online &#8220;[Controle de Vers&atilde;o com Subversion][6]&#8221; (que h&aacute; pouco tempo come&ccedil;ou a ser traduzido para portugu&ecirc;s) e percebi que ele era realmente muito mais poderoso que o FreeVCS.

Uma coisa incomodava, ele parecia ser ainda mais chato de instalar e manter do que o FreeVCS. Ent&atilde;o resolvi esse problema terceirizando. Contratei um servidor Subversion fora da empresa, hospedado na Internet, com links muito r&aacute;pidos, servidores redundantes, backups automatizados e garantia de 99,99% de uptime. Acha que custa caro? Eu pago US$20 por m&ecirc;s. Foi a melhor coisa que eu poderia ter feito.

Meu [host de Subversion][7] ainda oferece integra&ccedil;&atilde;o com o [Trac][8], um sistema de gerenciamento de configura&ccedil;&atilde;o de software com Wiki, BugTracking e algumas visualiza&ccedil;&otilde;es fant&aacute;sticas como [TimeLine][9], que mostra um hist&oacute;rico do que est&aacute; acontecendo no c&oacute;digo, ou o [ChangeSet][10], que permite revis&atilde;o de cada commit, mostrando exatamente o que foi alterado. Uso isso todo dia para revisar o c&oacute;digo comitado pelos outros desenvolvedores.

Resumindo, quando sa&iacute; do FreeVCS foi uma evolu&ccedil;&atilde;o imensa. Certamente nunca voltarei para ele e n&atilde;o o recomendo para ningu&eacute;m. Sei que existem muitos desenvolvedores usando com sucesso, mas provavelmente &eacute; porque nunca usaram o Subversion. Tamb&eacute;m n&atilde;o sei em que situa&ccedil;&atilde;o est&aacute; o JediVCS hoje, mas me parece que evoluiu muito pouco pois acredito que ainda dependa de tempo livre de poucos volunt&aacute;rios. J&aacute; estou usando o Subversion h&aacute; uns 2 anos, e muito antes disso o JediVCS j&aacute; estava migrando o FreeVCS e me parece que isso terminou apenas esse ano.

J&aacute; o Subversion, est&aacute; se tornando o padr&atilde;o em controle de vers&atilde;o pelo mundo. A grande maioria que usa controle de vers&atilde;o free/open source, usa Subversion. Inclusive o SourceForge j&aacute; est&aacute; oferecendo Subversion para todos os projetos que antes usavam apenas o CVS. Sei tamb&eacute;m que o Subversion tem alguns desenvolvedores em tempo integral, remunerados apenas para desenvolvimento do produto. Ele tamb&eacute;m roda em servidores Linux, ao contr&aacute;rio do JediVCS, que deve ser apenas Windows.

Enfim, o Subversion, na minha opini&atilde;o, &eacute; a melhor op&ccedil;&atilde;o sem sombra de d&uacute;vida.

 [1]: http://subversion.tigris.org/
 [2]: http://jedivcs.sourceforge.net/
 [3]: http://www.freevcs.org/
 [4]: http://en.wikipedia.org/wiki/SCM
 [5]: http://tortoisesvn.tigris.org/
 [6]: http://svnbook.red-bean.com/
 [7]: http://www.wush.net/
 [8]: http://www.edgewall.com/trac/
 [9]: http://www.edgewall.com/gfx/screenshots/timeline.png
 [10]: http://www.edgewall.com/gfx/screenshots/changeset.png