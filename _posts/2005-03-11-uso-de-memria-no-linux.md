---
title: Uso de memória no Linux
author: Erick Sasse
layout: post
permalink: /uso-de-memria-no-linux/
dsq_thread_id:
  - 262143297
categories:
  - Geral
tags:
  - Geral
---
Este post estréia a nova categoria &#8220;Linux&#8221; que criei para o blog. Não tenho muita certeza se estas categorias servem para alguma coisa, mas já que elas estão aí, vamos usar, né? Hahah.. 

Em dezembro passado instalei um servidor Linux bem legal em um cliente. Pentium 4, 3 GHz, 1 GB RAM, HD 120GB SATA, montado num gabinete para rack. Instalei [Fedora Core 3][1] nele, Firebird e Samba, mais nada, nem interface gr&aacute;fica. Ficou um canh&atilde;o, servindo pouco mais de 20 esta&ccedil;&otilde;es, j&aacute; era de se esperar, n&eacute;? A performance ficou muito melhor do que quando testo meus aplicativos rodando Firebird localmente. M&ecirc;s passado instalei outro id&ecirc;ntico em outro cliente.

Um comando que uso com frequ&ecirc;ncia &eacute; o &#8220;top&#8221;, para consultar o uso de mem&oacute;ria, processador, etc. Hoje fui dar uma olhada e percebi que ambos os servidores estavam com muito pouca mem&oacute;ria livre, por&eacute;m todos os processos somados n&atilde;o estavam ocupando quase nada de mem&oacute;ria. Veja o resultado do comando em um deles:

`
<pre class="wp-code-highlight prettyprint"><font size=-2>
top - 22:07:39 up 103 days, 12:19,  1 user,  load average: 0.00, 0.01, 0.00
Tasks:  76 total,   1 running,  75 sleeping,   0 stopped,   0 zombie
Cpu(s):  5.0% us,  0.2% sy,  0.0% ni, 94.7% id,  0.0% wa,  0.0% hi,  0.2% si
Mem:   1033208k total,   902928k used,   130280k free,    98156k buffers
Swap:  2031608k total,      160k used,  2031448k free,   584604k cached

  PID USER      PR  NI  VIRT  RES  SHR S %CPU %MEM    TIME+  COMMAND
15655 root      16   0  106m  42m 5616 S  0.3  4.2  46:20.71 fbserver
    1 root      16   0  1956  512 1408 S  0.0  0.0   0:01.50 init
    2 root      RT   0     0    0    0 S  0.0  0.0   0:00.65 migration/0
    3 root      34  19     0    0    0 S  0.0  0.0   0:00.09 ksoftirqd/0
    4 root      RT   0     0    0    0 S  0.0  0.0   0:00.53 migration/1
    5 root      34  19     0    0    0 S  0.0  0.0   0:00.10 ksoftirqd/1
    6 root       5 -10     0    0    0 S  0.0  0.0   0:00.00 events/0
    7 root       5 -10     0    0    0 S  0.0  0.0   0:00.00 events/1
    8 root       5 -10     0    0    0 S  0.0  0.0   0:00.00 khelper
    9 root      15 -10     0    0    0 S  0.0  0.0   0:00.00 kacpid
   28 root       5 -10     0    0    0 S  0.0  0.0   0:00.00 kblockd/0
   29 root       5 -10     0    0    0 S  0.0  0.0   0:00.00 kblockd/1
   39 root      15   0     0    0    0 S  0.0  0.0   0:01.19 pdflush
   40 root      15   0     0    0    0 S  0.0  0.0   0:11.37 pdflush
   42 root      13 -10     0    0    0 S  0.0  0.0   0:00.00 aio/0
   43 root       9 -10     0    0    0 S  0.0  0.0   0:00.00 aio/1
   30 root      15   0     0    0    0 S  0.0  0.0   0:00.00 khubd
</font></pre>
<p>`

Claro, agora n&atilde;o existe nenhum usu&aacute;rio na empresa, ent&atilde;o o servidor est&aacute; praticamente parado, mas repare que o servidor est&aacute; usando quase 900MB de mem&oacute;ria, e menos de 130MB est&atilde;o livres. 

Quando vi isso pela primeira vez, fiquei assustado. 5 minutos de pesquisa na Internet me aliviaram. Descobri que o que importa &eacute; o uso de swap, que neste caso foi usado apenas 160K, ou seja, praticamente nada. Isso quer dizer que a mem&oacute;ria fisica est&aacute; atendendo bem a necessidade. Mesmo em hor&aacute;rios de pico de uso, o swap n&atilde;o foi usado, pois fiquei monitorando isso. Descobri tamb&eacute;m que o Linux n&atilde;o se importa em liberar mem&oacute;ria que j&aacute; n&atilde;o est&aacute; mais em uso, ele j&aacute; toma posse da mem&oacute;ria e vai usando conforme precisa. Dai o motivo pelo qual existe pouca mem&oacute;ria f&iacute;sica livre.

 [1]: http://www.fedora.redhat.com/