---
title: Novidades do Delphi XE (2011)
author: Erick Sasse
layout: post
permalink: /novidades-do-delphi-xe-2011/
dsq_thread_id:
  - 262151428
categories:
  - Delphi
---
A nova versão do Delphi foi lançada oficialmente. Ela é parte do pacote RAD Studio XE, que incluí os produtos Delphi XE, C++ Builder XE, Delphi Prism XE e RadPHP XE.

Comentarei aqui apenas sobre o Delphi XE, pois é o que eu uso. Sobre os outros produtos a única coisa que notei, mas nem sei se é novidade nessa versão, é terem removido o nome Delphi da IDE para PHP. Finalmente corrigiram esse erro. Era muito estranho &#8220;Delphi for PHP&#8221;.

Então o que realmente há de novo no Delphi?

A [página oficial das novidades][1] relaciona os itens e tentei investigar e comentar cada um, mas como muito poucos detalhes foram divulgados, ficou meio difícil.

**DataSnap**

  * **Novos wizards para criação de clientes e servidores:** É útil, pois com certeza facilita a criação de projetos que dependem de vários componentes e acaba ajudando quem não está acostumado com a tecnologia e não saberia bem como começar um projeto do zero.
  * **Suporte a protocolos Javascript, REST, HTTP e HTTPS:** HTTP é bem básico, não tinha ainda? O resto é bem vindo.
  * **Filtros para compactação e criptografia dos dados:** Essencial.
  * **&#8220;User roles&#8221; para autenticação:** Não encontrei detalhes, mas aparentemente é apenas uma interface para autenticação de acesso. Isso realmente quero saber mais detalhes.

**Cloud Computing**

  * **Componentes para acesso a Windows Azure:** É interessante ver a Embarcadero abraçando uma tecnologia ainda tão pouco utilizada, além do que os serviços suportados (blobs, queues e tables) estão todos disponíveis via REST, o que torna a necessidade destes componentes um pouco duvidosa, pois em teoria são apenas requisições HTTP. De qualquer forma, quem pretende trabalhar com Azure já teve a vida um pouco facilitada.
  * **Distribuição fácil para Amazon EC2:** Mais um recurso que acredito atender uma parcela muito pequena de usuários. Procurei e não achei detalhes. Sempre achei que o Amazon EC2 fossem servidores padrão e para fazer um deploy fosse apenas questão de transferir os arquivos. Preciso entender melhor quais são essas facilidades incluídas para dar uma opinião melhor sobre o recurso.

**Integração com Subversion**

  * Esse recurso já comentei que não pretendo utilizar. Além de código fonte, trabalho com muito mais arquivos do que adiciono no projeto do Delphi, então prefiro controlar tudo usando apenas uma ferramenta, que é o TortoiseSVN. Parece também que a integração vai suportar apenas as tarefas mais comuns como import, update, commit e show log. Apesar de esses serem os mais usados, eu com certa frequência uso outros e teria que manter o TortoiseSVN para eles.

**Alta Produtivida e &#8220;Code Intelligence&#8221;**

  * **Melhoria na geração de código a partir de modelos:** Pra quem usa modelagem visual é bom, eu não uso.
  * **Geração de diagrama de sequência:** Idem acima.
  * **Melhorias no formatador de código:** Até hoje não consegui usar o formatador do Delphi porque ele nunca funcionou do jeito que eu queria. Confesso que nunca investi muito tempo para customizar ele, mas nessa segunda versão pretendo dar uma nova chance a ele. Porém já li alguns comentários negativos nos forums.
  * **Melhoradas pesquisas e IDE Insight:** Para pesquisar em código fonte uso o Grep Search do GExperts, que sempre foi muito superior ao da IDE. O IDE Insight é um recurso que gostei muito quando foi anunciado, mas acabei nunca usando. Já conheço praticamente todos os atalhos para as funções que uso na IDE. Mas também não encontrei detalhes sobre o que foi melhorado.
  * **Novos atalhos para navegar em código modificado:** Atalhos são sempre bem-vindos, mas não achei detalhes.

**Linguagem, Compilador e Bibliotecas**

  * **Atualizações na VCL, RTL e STL**: Aqui provavelmente são bugs corrigidos e pequenas melhorias, pois não encontrei detalhes. Só não sei o que é STL.
  * **Expressões regulares na RTL:** Isso é bem legal, expressões regulares são bem úteis principalmente para validação de dados.
  * **Melhorias em TStrings e Date/Time:** Isso deveria estar incluido já no tópico de atualizações na VCL/RTL, colocado separadamente parece que estão querendo apenas ter mais items. De qualquer forma, TStrings é uma das classes mais importantes do Delphi e tem que estar mesmo em constante melhoria.
  * **Suporte para abas internas na OpenTools API:** Melhorias na OTAPI são importantes para permitir melhor integração de ferramentas de terceiros na IDE.
  * **Melhoria na performace do compilador:** Velocidade do compilador é importante pois impacta diretamente na produtividade do desenvolvedor, então este é outro ponto que deveria mesmo receber atenção em todos os releases.

Até aqui são as reais melhorias no produto. Pare um pouco e analise novamente as novidades acima. Na minha opinião, tem pouca coisa que justifique o upgrade até aqui. Não achei nenhuma melhoria na linguagem por exemplo.

Acho que a Embarcadero também percebeu isso. E então resolveu adicionar uma série de ferramentas de terceiros no pacote:

**FinalBuilder**

Ferramenta para automatizar seus builds. Simplesmente fantástica. Sou usuário há anos e recomendo a todo mundo. Já até palestrei sobre ele em algum evento sobre Delphi. Automatizar os builds na minha opinião é totalmente essencial para qualquer desenvolvimento, mesmo que você trabalhe sozinho. E por ser a minha ferramenta preferida para isso, fiquei muito satisfeito em ver ela adicionada ao Delphi.

Por outro lado, é um atrativo que para mim não faz diferença, pois eu já tenho as licenças e pago independente do Delphi. Talvez eu consiga usar a licença do Delphi ao invés de pagar por uma separada? Ainda não sei.

Importante observar que está disponível apenas na versão Enterprise ou acima.

**AQTime**

Ferramenta para analisar a performance do seu código, facilitando descobrir os gargalos, permitindo otimizações mais precisas mostrando onde realmente está o problema. AQTime é o profiler lider há anos entre os desenvolvedores Delphi. Já baixei trials várias vezes e é uma ferramenta que sempre quis adotar no meu dia-a-dia, mas até hoje fui adiando. Agora ninguém terá desculpas, ter uma ferramenta dessa na mão e não usar é um tremendo desperdício. Disponível inclusive na versão Pro do Delphi.

**CodeSite**

Ferramenta para adicionar logs no seu código. Ele é concorrente do [SmartInspect][2], outra ferramenta que uso há anos e é minha ferramenta preferida para log. Também considero ferramenta essencial no desenvolvimento, principalmente para entender o comportamento do seu aplicativo internamente. Muitas vezes você acha que sabe o que ele está fazendo, mas vai ficar surpreso quando começar a logar tudo e monitorar.

**Beyond Compare**

Ferramenta para comparar arquivos. Não considero muito importante essa adição, mas ele também sempre foi popular entre os desenvolvedores Delphi. Pra mim outras ferramentas free sempre me atenderam o suficiente. Eles provavelmente adicionaram o BC ao pacote devido a integração com Subversion, para terem uma boa ferramenta para diff e merge. Melhor isso do que desenvolver alguma coisa simples demais.

**IP*Works**

Pacote de componentes para suporte a protocolos IP. Concorrente direto do Indy, que está meio largado, mantido pelo trabalho voluntário de alguns poucos corajosos. Esse pacote só conheço de nome, mas parece ser bom.

**Conclusão**

Na minha opinião essa versão veio muito fraca de novidades no produto, mas totalmente recheada de ferramentas extremamente úteis de terceiros. Se você somar tudo, é um upgrade que acaba valendo a pena, principalmente se você ainda não usa Finalbuilder ou AQTime.

Eu farei o upgrade por vários motivos:

  * Gosto de usar e fornecer as melhores e mais novas ferramentas para minha equipe.
  * Quero começar a usar novos recursos do DataSnap.
  * Quero começar a usar o AQTime.
  * Estou fazendo minha parte para garantir a manutenção e continuidade do produto que utilizo e dependo diariamente.

 [1]: http://www.embarcadero.com/br/products/delphi/whats-new
 [2]: http://www.gurock.com/smartinspect/