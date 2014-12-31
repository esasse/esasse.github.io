---
title: Validando Datasets na Estrutura do Banco de Dados
author: Erick Sasse
layout: post
permalink: /validando-datasets-na-estrutura-do-banco-de-dados/
dsq_thread_id:
  - 262150289
categories:
  - Delphi
  - RemObjects
---
Durante essa semana estive modificando o nome de alguns campos do banco de dados de um dos nossos maiores projetos. Um dos campos era relativamente importante, de uma das principais tabelas do sistema e estava sendo usado no SQL de muitos datasets.

Qual seria a melhor forma de localizar todos os locais que o campo é utilizado? A primeira idéia que me veio a cabeça foi usar o ótimo Grep Search do GExperts e pesquisar todos os arquivos do projeto, incluindo os DFM. O problema dessa solução é que a pesquisa traz muito lixo junto, pois o nome do campo era comum e várias tabelas tinham outros campos com o mesmo nome. Então tive que ir item por item encontrado, analisar o código, identificar se era da tabela que eu estava modificando e então modificar o SQL.

Conclusão, foi uma tarefa demorada, chata e com muita chance de deixar algo passar e só dar pau quando o cliente for usar o sistema.

E o que me motivou a contar isso aqui, é que só tive essa dificuldade porque esse sistema ainda está usando DataSnap padrão do Delphi com muitos TSQLDataSet e TSQLQuery espalhados nos data modules do servidor. Em breve pretendo iniciar a migração dele para [DataAbstract][1], que fornece uma ferramenta ótima para facilitar a nossa vida nesse tipo de situação.

No DataAbstract, todos os datasets que utilizamos no sistema são criados e mantidos através do [Schema Modeler][2], portanto temos um local centralizado para todo o SQL que escrevemos no sistema. O interessante é que a qualquer momento você pode pedir para o Schema Modeler validar todos os datasets com a estrutura do banco. O que ele faz é conectar ao banco e verificar se todos os seus comandos SQL ainda são válidos na estrutura atual do banco. Não é show?

E tem mais! Se seu sistema suportar mais de um banco ao mesmo tempo. Por exemplo, Firebird e SQL Server, o Schema Modeler conecta aos dois e valida os comandos nos dois bancos.

Enfim, é uma ferramenta muito poderosa e que pode nos economizar muito tempo na manutenção de nossos aplicativos.

 [1]: http://www.remobjects.com?da
 [2]: http://www.remobjects.com?da03