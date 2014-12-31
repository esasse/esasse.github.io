---
title: Social Coding e DVCS
author: Erick Sasse
layout: post
permalink: /social-coding-e-dvcs/
dsq_thread_id:
  - 282031845
categories:
  - Controle de Versão
tags:
  - DVCS
---
Muita gente usa Orkut e Facebook, mas vocês conhecem as redes sociais para programadores?

Os mais conhecidos são [GitHub][1] e [BitBucket][2]. Eles permitem que você publique e compartilhe seus códigos com controle de versão, siga e seja seguido por outros desenvolvedores, acompanhe e participe de outros projetos, etc. A idéia já tomou proporções tão grandes que muitas empresas, pelo menos lá fora, tem até utilizado o histórico desses sites para avaliar a contratação de programadores.

Uma característica importante desses sites é que são baseados em DVCS, ou seja, Controle de Versão Distribuído. E a principal diferença entre o GitHub e o BitBucket, é exatamente o sistema de controle de versão usado. No GitHub é o [Git][3] e no BitBucket é o [Mercurial][4].

Algum tempo atrás eu já havia me decidido que se eu fosse migrar do Subversion para um sistema distribuído, seria o Mercurial por ser mais amigável no Windows do que o Git, e também por ter sido a ferramenta adotada no [Kiln][5], ferramenta que se integra totalmente ao FogBugz, que já usamos na empresa.

Abri uma conta no BitBucket e procurei projetos Delphi. Encontrei vários e escolhi o [DelphiClean][6] do Nick Hodges para fazer um fork e entender como funcionava o processo.

Quando se faz um fork, você tem um cópia de todo o repositório do projeto original no seu novo projeto, incluindo todo histórico de commits, etc. O mais interessante é que ele não perde o &#8220;parentesco&#8221; com o projeto original, e esse é um dos grandes benefícios, porque você pode fazer alterações, comitar no seu repositório e depois se for uma correção de bug ou uma melhoria, pode oferecer ao dono do outro projeto puxar suas alterações para o projeto original através do &#8220;pull request&#8221;.

Se vocês observarem o meu fork, que nomeei [MyDelphiCleaner][7], poderão observar que ele tem exatamente o mesmo histórico de commits do [DelphiClean][6] original, além de um commit meu, realizado após o fork. Repare também que o site mostra que o meu projeto é fork do DelphiClean do Nick.

O meu commit foi remover uma linha de código que estava comentada e por isso só estava sujando o código. Como isso é uma melhoria no código, enviei um &#8220;pull request&#8221; para o Nick, mas ainda não foi incorporada ao projeto original porque ele me respondeu dizendo que não sabe como fazer. Hehe.

Esse tipo de compartilhamento de código, puxa, empurra, fork em repositório, são as grandes vantagens dos DVCS, e o que me faz concluir que grande parte do sucesso desses sites se deve em muito ao DVCS. Acho que seria muito difícil, construir um site desse tipo usando Subversion por exemplo.

Enfim, ainda sou bem iniciante nisso também, mas acho que vale a pena investir um tempo para entender como funciona, principalmente para aprender melhor o funcionamento dos DVCS, e quem sabe no caminho contribuir com outros desenvolvedores fazendo forks de seus projetos e mandando melhorias. Quer começar? Abra uma conta no [BitBucket][2], baixe o [Mercurial][4] e faça um fork do meu projeto [NotificationService][8], que é uma classe de notificação em Delphi, da qual falarei em um futuro post.

 [1]: https://github.com/
 [2]: https://bitbucket.org/
 [3]: http://git-scm.com/
 [4]: http://mercurial.selenic.com/
 [5]: http://www.fogcreek.com/kiln/
 [6]: https://bitbucket.org/NickHodges/delphiclean
 [7]: https://bitbucket.org/esasse/mydelphicleaner
 [8]: https://bitbucket.org/esasse/notificationservice