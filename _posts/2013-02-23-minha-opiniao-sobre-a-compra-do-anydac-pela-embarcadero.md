---
title: Minha opinião sobre a compra do AnyDAC pela Embarcadero
author: Erick Sasse
layout: post
permalink: /minha-opiniao-sobre-a-compra-do-anydac-pela-embarcadero/
dsq_thread_id:
  - 1402602921
categories:
  - Delphi
---
No início a Borland criou a [BDE][1]. Apostamos nela, desenvolvemos nosso sistemas com ela e tudo estava caminhando.

Em determinado momento, decidiram que a BDE não servia mais, então simplesmente criaram outro framework preferido para acesso a dados no Delphi, o dbExpress, que era &#8220;[uma nova visão][2]&#8221; e resolvia todos os problemas anteriores.

Concordo que o dbExpress sempre foi simples e vinha evoluindo em passos de tartaruga, mas funciona de forma aceitável. Sempre usei com drivers de terceiros, pois os da Borland/Embarcadero são sofríveis. E se os drivers de terceiros funcionavam bem, fica claro uma questão de relaxo com os drivers nativos.

Além de ele servir para acesso aos bancos de dados, o dbExpress também foi estranhamente utilizado como base para todo o novo framework de comunicação DataSnap, e isso o tornou uma parte ainda mais importante no Delphi.

De repente, do nada, a Embarcadero anuncia, estrondosamente, que comprou um pacote de componentes de acesso a dados. Componente este que tem exatamente a mesma função do dbExpress. E agora? Qual mensagem isso passa para nós?

Marco Cantu, o novo responsável pelo Delphi, [postou em seu blog][3] que essa novidade é uma excelente notícia para os desenvolvedores Delphi, e que o dbExpress nunca chegou a ser o que deveria, etc.

Infelizmente pra mim é o seguinte: É mais barato para a Embarcadero comprar algo pronto que funciona do que melhorar o dbExpress. Deixando o custo de migração de um framework para outro para os clientes. Lógico que eles vão esconder isso com a desculpa de que estão oferecendo algo muito melhor do que antes. Mas e o custo de migrar? E o tempo investigo no dbExpress? O tempo que nós perdemos migrando de um framework para outro é tempo não investido em entregar valor para nossos clientes. Isso não é proteger nosso investimento como eles tanto gostam de dizer.

Talvez vocês achem que isso não é um problema pois o dbExpress certamente vai continuar por aí, assim como a BDE está. Mas duvido muito que teremos mais melhorias nele, com muita sorte talvez resolvam bugs mais graves, mas certamente tentarão forçar a migração para o AnyDAC, que é o novo preferido.

Junto com o AnyDAC, parece que contrataram o único desenvolvedor responsável pelo produto, para continuar evoluindo ele. Ok, mas e quando esse cara sair? O que vai acontecer? Porque mais cedo ou mais tarde isso pode acontecer. Será que vão investir para continuarem evoluindo o produto ou vão deixar ele parado até acharem outro para comprar, enquanto nós ficamos com o abacaxi de migrar nossos sistemas?

O que dizem é que depois que o Steve Shaughnessy deixou a Embarcadero, o dbExpress ficou sem rumo, pois ele era o cara que direcionava o desenvolvimento desta área. Quem nos garante que o mesmo não vai acontecer com o AnyDAC daqui alguns anos?

Mas o que me deixa mais inseguro com tudo isso, é que ninguém garante que este tipo de atitude não vai acontecer em outras áreas do Delphi. E se amanhã eles decidem que o DataSnap não é mais legal e compram um outro pacote de componentes &#8220;melhor&#8221;? Tudo o que investimos de tempo no DataSnap vai praticamente para o ralo.

E isso também nos leva a outro questionamento: será que realmente não era possível evoluir a VCL para multi-plataforma? Ou era difícil e caro demais? Mais fácil comprar algo pronto (FireMonkey), mesmo que capenga e ir melhorando conforme os clientes tentassem usar e começassem a reclamar porque nada funcionava?

E que fique claro que eu não sou contra evolução, mesmo que se precise quebrar uma coisa aqui ou ali, mas com uma boa razão, acho perfeitamente justificável. Mas trocar por completo o framework acho pura falta de comprometimento com os clientes.

UPDATE: O AnyDAC foi lançado pela Embarcadero com o nome FireDAC.

 [1]: http://pt.wikipedia.org/wiki/Borland_Database_Engine
 [2]: http://edn.embarcadero.com/article/images/29106/migrating_bde_applications_to_dbexpress.pdf
 [3]: http://blog.marcocantu.com/blog/embarcadero_buys_anydac.html