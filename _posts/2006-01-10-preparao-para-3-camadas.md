---
title: 'Prepara&ccedil;&atilde;o para 3 Camadas'
author: Erick Sasse
layout: post
permalink: /preparao-para-3-camadas/
dsq_thread_id:
  - 262148646
categories:
  - Delphi
---
Como já comentei aqui anteriormente, iniciamos a migração de nossos aplicativos de 2 camadas para 3 camadas. Isso permitirá que os aplicativos rodem acessando os dados via Internet com ótima performance. Se você pretende fazer o mesmo com algum aplicativo seu no futuro, segue aqui algumas dicas:

**Utilize apenas ClientDataSets para acesso a seus dados**  
O CDS é o componente chave para manipulação de dados na camada do usuário, e é ele que você vai usar em aplicativos 3 camadas. Felizmente ele é muito últil em qualquer aplicativo, então é provável que você já o utilize.

**Não utilize SimpleDataSet**  
Este componente só funciona em 2 camadas. Ele pode parecer prático pois não te obriga a usar um DataSet, um Provider e um ClientDataSet separado, mas a praticidade não vale a pena. Não utilize este componente, pois quando for migrar para 3 camadas, terá que substitui-lo pelos 3 citados acima.

<strike>**Mantenha o DataSet e o Provider juntos em um DataModule, porém separados do ClientDataSet**</strike>  
Ao contrário do que pensei, isso não é possível. Você precisa deixá-los no mesmo DataModule, senão o ClientDataSet não enxerga o Provider.

**Evite enviar instruções SQL diretas ao banco**  
A camada cliente deve saber o mínimo possível sobre o banco, então não utilize comandos SQL diretos ao banco de dados a partir desta camada. Em algumas situações nós usávamos o ExecuteDirect do SQLConnection para disparar SQL direto no banco quando não precisávamos de retorno. Isso está sendo remodelado na migração 3 camadas, pois você não tem mais acesso a conexão com o banco a partir da camada cliente.

São algumas dicas que se seguidas, ajudarão bastante na migração para 3 camadas.