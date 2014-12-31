---
title: Agregação x Composição
author: Erick Sasse
layout: post
permalink: /agregao-x-composio/
dsq_thread_id:
  - 262142986
categories:
  - Geral
tags:
  - Geral
---
Em modelagem orientada a objetos existem dois termos que geralmente me confundem: Agrega&ccedil;&atilde;o e Composi&ccedil;&atilde;o. Decidi escrever esse post para quando eu mesmo estiver em d&uacute;vida vir at&eacute; aqui e consultar. Pr&aacute;tico, n&atilde;o? <img src="http://www.ericksasse.com.br/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" />

Ambos descrevem rela&ccedil;&otilde;es entre objetos, por&eacute;m com uma diferen&ccedil;a simples.

**Agrega&ccedil;&atilde;o**

  * Um objeto cont&eacute;m uma lista de outros objetos.
  * Os objetos contidos podem existir sem serem parte do objeto que os cont&eacute;m.
  * Exemplo: Carro -> Rodas. Voc&ecirc; pode tirar as rodas do carro antes de destru&iacute;-lo e elas podem ser colocadas em outro carro.

**Composi&ccedil;&atilde;o**

  * Um objeto cont&eacute;m uma lista de outros objetos.
  * Os objetos contidos n&atilde;o fazem sentido fora do contexto do objeto que os cont&eacute;m.
  * Exemplo: Pedido -> Itens. Se voc&ecirc; destruir o pedido, os itens s&atilde;o destruidos junto, eles n&atilde;o tem sentido fora do pedido.