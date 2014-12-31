---
title: 'ECO e ASP.NET: Armazenando Objetos na Sessão do Usuário'
author: Erick Sasse
layout: post
permalink: /eco-e-aspnet-armazenando-objetos-na-sessao-do-usuario/
dsq_thread_id:
  - 262148379
categories:
  - Delphi
---
Você não deve armazenar objetos inteiros na sessão do usuário, pois como o ECO trabalha com um pool de EcoSpaces, entre diferentes requisições você pode obter EcoSpaces diferentes, e cada instância de objeto pertence a um EcoSpace específico. Para resolver isso, você deve armazenar apenas o Id do objeto e resgatar o objeto pelo Id quando necessário:

Salvando na sessão:  
`Session['ClienteID'] := IdForObject(MeuCliente);`

Resgatando da sessão:  
`MeuCliente := ObjectForId(Session['ClienteID'] .ToString).AsObject as Cliente;`