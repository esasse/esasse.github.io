---
title: Padrão Publish/Subscribe em Delphi
author: Erick Sasse
layout: post
permalink: /padrao-publishsubscribe-em-delphi/
dsq_thread_id:
  - 293756999
categories:
  - Delphi
---
Imagine que você tem o cadastro do mesmo cliente aberto em várias janelas usando datasets diferentes. Ao atualizar um deles, você quer disparar um refresh nos outros.

Um dos padrões que resolvem esse problema é o [Publish/Subscribe][1]. Ele permite que objetos interessados em uma mensagem, &#8220;assinem&#8221; notificações, de forma a serem avisados sempre que essa mensagem for disparada. A grande vantagem desse padrão é o desacoplamento, pois quem assina não necessariamente precisa conhecer quem publica e vice-versa.

Para utilizar esse padrão nos meus sistemas, implementei o [NotificationService][2].

Quando um objeto deseja ser notificado sobre um assunto, ele faz uma assinatura, passando o ID da mensagem que está interessado:

<pre class="wp-code-highlight prettyprint">GetNotificationService.Subscribe(MetodoASerExecutado, MsgUmClienteFoiAtualizado);</pre>

Onde MetodoASerExecutado é um TNotifyEvent, que já estamos carecas de usar no dia a dia em todos os componentes do Delphi. Ele será executado sempre que a mensagem MsgUmClienteFoiAtualizado for disparada por outro objeto.

Para enviar a mensagem a todos os interessados, também é muito simples, bastando o objeto que está gerando a mensagem chamar:

<pre class="wp-code-highlight prettyprint">GetNotificationService.SendMessage(Self, MsgUmClienteFoiAtualizado);</pre>

Nesse caso, ele passa um objeto como sender, que não necessariamente precisa ser ele mesmo (Self), e o ID da mensagem (MsgUmClienteFoiAtualizado). Feito isso, o NotificationService vai varrer a lista de assinantes, identificar quem está interessado nessa mensagem e disparar todos os métodos passando o mesmo sender.

Quando o objeto interessado na mensagem for destruído ou não desejar mais receber as notificações, basta cancelar a assinatura, chamando:

<pre class="wp-code-highlight prettyprint">GetNotificationService.UnSubscribe(MetodoASerExecutado);</pre>

Bem simples de usar e muito útil para resolver alguns problemas no dia a dia de desenvolvimento. O código fonte inclui um demo com mais detalhes.

O projeto está hospedado no BitBucket. Se quiser baixar os fontes, instale o [Mercurial][3] na sua máquina, abra uma linha de comando e digite:

<pre class="wp-code-highlight prettyprint">hg clone https://bitbucket.org/esasse/notificationservice</pre>

Um dos motivos em publicar esse projeto foi para conhecer os recursos do BitBucket e do Mercurial como DVCS. Por isso, se tiver alguma sugestão de melhoria no código ou simplesmente quiser fazer uma versão diferenciada, [faça um fork do projeto][4] no próprio BitBucket e fique a vontade!

Para mais informações sobre esses recursos de compartilhamento de código usando BitBucket e Mercurial, veja [meu post anterior][5].

 [1]: http://en.wikipedia.org/wiki/Publish/subscribe
 [2]: https://bitbucket.org/esasse/notificationservice
 [3]: http://mercurial.selenic.com/
 [4]: http://confluence.atlassian.com/display/BITBUCKET/Overview+-+Working+on+a+Copy+of+a+Bitbucket+Repository
 [5]: http://www.ericksasse.com.br/social-coding-e-dvcs/ "Social Coding e DVCS"