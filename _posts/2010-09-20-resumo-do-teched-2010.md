---
title: Resumo do TechEd 2010
author: Erick Sasse
layout: post
permalink: /resumo-do-teched-2010/
dsq_thread_id:
  - 262151502
categories:
  - Microsoft
---
Na semana passada aconteceu no Expo Center Norte em São Paulo o [TechEd][1], maior evento da Microsoft no Brasil. Eu estive lá e vou tentar resumir os principais assuntos que acompanhei.

Pela primeira vez (acredito eu), a abertura do evento foi transmitida ao vivo pela Internet, o que é bem legal para quem não pôde estar lá. Só no final da cortaram a transmissão online antes da demo do Kinect, que era exclusiva para os presentes. Provavelmente quiseram valorizar quem pagou (caro) para estar lá, mas na minha opinião não era necessário, a experiência de ver ao vivo já foi muito superior e perderam uma ótima oportunidade de muito mais gente ver o Kinect.

O foco principal do evento foi computação nas nuvens (ou Cloud Computing) e a plataforma [Windows Azure][2], que a Microsoft oferece como solução nessa área. Eu assisti várias palestras focadas no Azure e achei bem interessante. Pra quem não sabe, Windows Azure permite que você rode seus aplicativos e/ou bancos de dados nos data centers da Microsoft.

Alias, estes data centers são [um show a parte][3], estado da arte em TI. Todos os servidores são montados dentro de containers, sendo que cada um destes containers pode ter até 2500 servidores. Um data center pode ter cerca de 50 containers, então estamos falando de algo em torno de 125.000 servidores em um único prédio. Não é brincadeira. A Microsoft está construindo os maiores data centers do planeta, investindo pesadíssimo.

Em particular achei bem interessante o [SQL Azure][4], que depois de criado, você acessa exatamente como se fosse um SQL Server normal. Usando os mesmos métodos de acesso que já estamos acostumados. Você pode abrir seu SSMS, configurar a conexão e sair usando numa boa. Ainda não fiz testes com Delphi, mas pelo que vi lá, acredito que seja totalmente transparente acessar um banco no SQL Azure usando os mesmos drivers e componentes que já estamos acostumados. Bem interessante.

Além disso assisti um [ótima palestra do Luciano Moreira][5], sobre cache de plano de execução, com muitas dicas interessantes de analise de performance, inclusive com importantes alertas para os que acreditam que as stored procedures são sempre a melhor opção.

Outro assunto que me interessei foi Entity Framework 4, que acredito ser hoje o framework mais promovido pela MS para acesso a dados. Ele realmente vem evoluindo bastante nos últimos anos e quem tem oportunidade de usar, deveria dar uma atenção especial a ele. Aliado ao LINQ, formam uma dupla fantástica para acesso a dados usando classes de negócio ao invés de datasets.

Também procurei assistir algumas palestras de tecnologias que não conheço nada como Windows Workflow Foundation (que achei muito interessante) e outras. No caso do Workflow Foundation me parece uma grande quebra de paradigma no desenvolvimento de aplicativos. Pretendo pesquisar melhor e ver se encontro casos de sucesso, para ter uma idéia de como estão aplicando.

Evitei palestras sobre WPF e Silverlight, pois são duas tecnologias que realmente não me vejo aplicando em nada. O único caso onde eu usaria Silverlight seria para brincar um pouco com desenvolvimento para Windows Phone 7, porque aparentemente é a melhor opção nesta plataforma. Aliás vi uma palestra sobre desenvolvimento para Windows Phone 7 e parece bem legal, mas não me vejo trocando meu iPhone por ele.

Uma oportunidade interessante que tive foi testar o [Kinect][6], o novo acessório de reconhecimento de movimentos para o Xbox 360. Pra mim a tecnologia do Kinect é muito incrível. Ele consegue mapear seu esqueleto e monitorar toda a movimentação do corpo em tempo real sem nenhuma calibração. É impressionante. Escrevi todos os [detalhes no meu outro blog][7] sobre games.

Tinha wifi gratuito mas era limitado a alguns locais e funcionava muito precariamente, então acabei não usando, fiquei no 3G do celular que funcionava bem melhor.

Eles ainda não conseguiram criar um guia prático para que você consiga ver todas as palestras em determinado horário. Muitas vezes você muda de idéia sobre a palestra que quer assistir, e era bem chato ficar olhando nas diversas páginas do guia de palestras para achar as outras que estavam no mesmo horário.

Mas no geral o evento estava bem melhor que no ano anterior. Se alguém que lê meu blog foi, diga aí o que achou.

 [1]: http://www.teched.com.br/
 [2]: http://www.microsoft.com/windowsazure/
 [3]: http://news.cnet.com/8301-13860_3-10371840-56.html?tag=rtcol;txt
 [4]: http://www.microsoft.com/sqlazure
 [5]: http://luticm.blogspot.com/2010/09/teched-brasil-2010-dbp402-material-da.html
 [6]: http://www.xbox.com/kinect
 [7]: http://jogador76.com/testei-o-kinect-primeiras-impressoes