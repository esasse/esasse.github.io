---
title: Horário de Verão
author: Erick Sasse
layout: post
permalink: /horario-de-verao/
dsq_thread_id:
  - 262150486
categories:
  - Microsoft
---
O horário de verão sempre foi uma dor de cabeça para o pessoal de informática. Principalmente para aqueles responsáveis por servidores e sistemas que rodam 24&#215;7 e dependem do horário do sistema. Com minha máquina pessoal normalmente não tenho problema, mas esse foi meu primeiro horário de verão rodando Vista, e infelizmente tive problemas.

Esse ano a MS até caprichou, criou [um site][1] só para explicar como atualizar o Windows para o horário de verão. Na semana passada entrei no site, segui todas as instruções, especifiquei minha versão do Windows corretamente (Windows Vista Ultimate) além de todos os outros campos. Verifiquei um por um antes de mandar. Os dados estavam corretos. Algumas horas depois recebi um e-mail em inglês dizendo que meu hotfix estava pronto para download e uma senha para descompactar o arquivo. Ao executar o arquivo ele pediu um caminho para descompactar, forneci o caminho e a senha. Depois fui até o local do arquivo e encontrei lá: *WindowsServer2003-KB943000-x86-PTB.exe*. Na hora pensei &#8220;meu Windows não é o Server2003, tem algo errado&#8221;. Naturalmente não consegui instalar a atualização.

Ontem após a virada, tentei usar o famoso tzedit.exe, que sempre usei nas outras versões do Windows, mas no Vista aparentemente não funciona. Fiquei com o relógio errado. Hoje pela manhã falei com o Fábio que trabalha comigo na Cadena e ele disse que tinha conseguido instalar sem problemas o hotfix que recebeu da Microsoft. Ele me encaminhou o e-mail que recebeu da Microsoft e era totalmente diferente do meu. O dele estava em português e tinha links para todas as versões do Windows. Cliquei no link para o Vista Ultimate, baixei o pacote, repeti os passos e funcionou perfeitamente.

Por que eu recebi um e-mail totalmente diferente e com o arquivo errado? Provavelmente nunca saberemos, mas as dúvidas que ficam sobre isso tudo são:

  * Por que a Microsoft deixou o processo tão complicado? Ter que preencher um formulário, receber um e-mail, baixar um arquivo, usar uma senha para descompactar esse arquivo, procurar ele no HD e executar. Isso é algo tranqüilo para nós, técnicos, fazermos, mas e o resto dos usuários? Certamente não devem ter feito, por mais que a MS tenha detalhado os passos no site, não é algo que simples usuários fazem. E pior, no e-mail está dizendo que a senha para descompactar os arquivos vencem no dia 15/10. Se o usuário não aplicar até amanhã, terá que entrar no site da MS e solicitar o arquivo novamente, preenchendo o formulário, etc.
  * Por que a Microsoft não colocou essa atualização no próprio Windows Update para que todos recebessem automaticamente? Seria a forma mais perfeita. O usuário não tem que se preocupar com nada.
  * Por que o governo muda o horário de verão todo ano? Essa me parece a questão mais importante de todas. Por que raios o governo precisa mudar o início e fim do horário de verão? Eu quero acreditar que eles tenham um bom motivo e gostaria de saber qual.

Fiquei curioso para saber como o Ubuntu lidou com o horário de verão. Muita coisa nele é mais fácil que no Windows, mas tem coisas que são bem mais difíceis também.

 [1]: http://www.microsoft.com/brasil/windows/products/windowsvista/verao.mspx