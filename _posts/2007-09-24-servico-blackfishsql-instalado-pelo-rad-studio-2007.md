---
title: Serviço BlackFishSQL instalado pelo RAD Studio 2007
author: Erick Sasse
layout: post
permalink: /servico-blackfishsql-instalado-pelo-rad-studio-2007/
dsq_thread_id:
  - 262150394
categories:
  - Delphi
---
Se você optou por instalar o &#8220;[PeixePreto][1]&#8221; da CodeGear durante a instalação do seu RAD Studio 2007, observe que ele registra um serviço no Windows com inicialização automática. Se você não pretende usar ele com freqüência, pode ser uma boa idéia mudar a inicialização dele para manual e inicializá-lo somente quando necessário. Isso deve salvar alguns recursos da sua máquina.

Basta procurar por BlackFishSQL na sua lista de serviços, ele vai estar lá.

Alias, eu tenho o SQL Server na minha máquina e uso de vez em nunca, também deixo todos os serviços no manual. Só o Firebird mesmo fica no automático, porque uso quase o tempo todo.

 [1]: http://www.codegear.com/products/blackfish