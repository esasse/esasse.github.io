---
title: Prova do Google Developer Day em Delphi
author: Erick Sasse
layout: post
permalink: /prova-do-google-developer-day-em-delphi/
dsq_thread_id:
  - 1014145551
categories:
  - Delphi
  - Google
---
Essa foi a primeira vez que decidi resolver a prova proposta pelo Google para quem quer participar do <a href="http://www.google.com/events/developerday/2011/sao-paulo/" target="_blank">Google Developer Day</a>.

Basicamente você tinha que escrever código para ler e extrair informações de um texto. Palavras que tem tamanho X e começam com letras específicas, palavras que tem tamanho Y e não possuem determinada letra, converter palavras em números usando uma formula maluca deles, ordenar o texto usando uma ordem de alfabeto totalmente diferente do nosso. Coisas desse tipo.

O mais interessante é que eles deram dois textos, em um deles já informando as respostas e o outro é o que você tinha que usar para responder. Isso facilitou muito.

Decidi usar <a href="http://pt.wikipedia.org/wiki/Test_Driven_Development" target="_blank">TDD</a>. Criei <a href="https://bitbucket.org/esasse/gdd2011/src/tip/GooglonParser.pas" target="_blank">minha classe</a> para fazer a leitura do texto com os métodos e propriedades que ela precisaria expor para me informar as respostas e antes de codificar a classe, já escrevi os testes baseados nas respostas do texto A. Rodei os testes e obviamente todos falharam, a partir daí comecei a codificar para cada um dos testes passar. Depois dos testes passarem, fiz um segundo projeto com interface visual, permitindo que o usuário digitasse qualquer texto em &#8220;Googlon&#8221;, que seria automaticamente processado pelo meu parser.

O bom desse tipo de abordagem é que depois você pode refatorar o código sem medo, pois está protegido pelos testes. Se caso você quebre alguma coisa, vai saber imediatamente. Tanto que quando estava escrevendo esse post, percebi que eu tinha uma lista totalmente desnecessária na minha classe. <a href="https://bitbucket.org/esasse/gdd2011/changeset/8c2ebd2c9de8" target="_blank">Removi</a> e rodei os testes. Todos passaram, o que quer dizer que não quebrei nada. Não precisei sequer rodar o projeto com a interface visual para testar a mudança. Ou seja, além de tranquilidade, TDD te dá muito mais produtividade, pois você consegue alterar o código com muito mais rapidez.

As duas coisas que deram mais trabalho na solução do problema em Delphi foram:

  * Ordenar a string usando um alfabeto ordenado de forma diferente do nosso. Eu tinha certeza que existia algum algoritmo testado e comprovado para isso, pois é algo que já deve ter sido feito milhões de vezes. Perdi tempo procurando. Por fim não encontrei e fiz o meu mesmo. Ele vai comparando letra por letra e quando a letra é igual, compara a próxima. Se não existir a próxima letra em uma das palavras, ela é menor.
  * Perceber que o Delphi estava silenciosamente informando valores inválidos quando estourava a capacidade do tipo Integer. Isso eu achei bem estranho, pois esperava que fosse levantada uma exception em caso de estourar o tipo. <del>Por algum motivo que ainda não descobri, o código que eu escrevi para converter a palavra para valor numérico não levanta nada, simplesmente informa o valor errado se você usar Integer.</del> O que acontece é que, não sei por qual motivo, o Delphi vem por padrão com &#8220;Range Checking&#8221; desativado (valeu <a href="http://twitter.com/cesarliws" target="_blank">Cesar</a>!). Ativando esta opção, o código quebra e você consegue perceber o problema imediatamente. Troquei para Int64 e resolveu.

Enfim, levei duas ou três horas para resolver os problemas e acho que valeu o desafio. Principalmente para ficar ainda mais atento com as limitações dos tipos (como no caso do Integer) e o tal do Range Checking desativado por padrão.

Acho que vale a pena tentar resolver, principalmente porque a prova é diferente para cada um. Esse é o <a href="http://developerquiz.appspot.com/?lang=pt" target="_blank">link para a prova</a>, e você pode fazer mesmo que não pretenda participar do evento. Meu projeto completo está <a href="https://bitbucket.org/esasse/gdd2011/" target="_blank">aqui</a>, mas recomendo você fazer o seu antes de analisar o meu. Quem sabe você não tem idéias muito melhores?