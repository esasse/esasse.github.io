---
title: ModelMaker Code Explorer
author: Erick Sasse
layout: post
permalink: /modelmaker-code-explorer/
dsq_thread_id:
  - 262148448
categories:
  - Delphi
---
H&aacute; algum tempo tenho usado o [Code Explorer][1], um plug in para o Delphi que facilita muito a vida de qualquer desenvolvedor.

A partir do Delphi 2005, come&ccedil;amos a ter alguns refactorings dispon&iacute;veis na IDE do Delphi, mas o Code Explorer j&aacute; oferece isso desde muito antes, e para muitas vers&otilde;es do Delphi (5, 6, 7, 2005 e 2006). Para quem ainda usa os Delphis anteriores ao 2005, n&atilde;o tem nada de refactoring na IDE, e depois que voc&ecirc; acostuma com essas facilidades, fica dif&iacute;cil ficar sem elas.

[Nestes screenshots][2] voc&ecirc; pode ter uma no&ccedil;&atilde;o da quantidade de op&ccedil;&otilde;es que ele te oferece.

Por exemplo, uma das coisas mais chatas do Pascal &eacute; ter que manter as se&ccedil;&otilde;es de interface a implementation iguais. Se voc&ecirc; deseja adicionar um par&acirc;metro em um m&eacute;todo, voc&ecirc; precisa editar a interface e a implementation. Se voc&ecirc; estiver usando o MMX (abrevia&ccedil;&atilde;o de ModelMaker Code Explorer), basta voc&ecirc; editar uma das se&ccedil;&otilde;es e teclar Ctrl+Shift+Y e o MMX atualiza a outra se&ccedil;&atilde;o automaticamente para voc&ecirc;.

Renomear membros &eacute; ainda mais f&aacute;cil, pois o MMX cria um painel lateral que mostra todos os membros da classe atualmente selecionada. Para renomear pasta teclar F2 e digitar o novo nome.

Quer mover uma procedure/fun&ccedil;&atilde;o de uma unit para outra? Basta seleciar a procedure/fun&ccedil;&atilde;o no painel do MMX, teclar Ctrl+X, abrir a outra unit e teclar Ctrl+V no painel do MMX. Ele se encarrega de remover/colocar a declara&ccedil;&atilde;o da fun&ccedil;&atilde;o/procedure no local certo. &Eacute; realmente muito pr&aacute;tico.

Por hoje &eacute; s&oacute;, mas estarei escrevendo mais sobre o MMX.

 [1]: http://www.modelmakertools.com/code-explorer/index.html
 [2]: http://www.modelmakertools.com/code-explorer/screenshots.html