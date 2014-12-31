---
title: 'O bot&atilde;o &quot;Fechar&quot; que n&atilde;o fecha'
author: Erick Sasse
layout: post
permalink: /o-boto-fechar-que-no-fecha/
dsq_thread_id:
  - 262149559
categories:
  - Mobilidade
---
Se você tem um dispositivo com Windows Mobile já deve ter se perguntado porque o botão &#8220;Fechar&#8221; na verdade não fecha nada.

A [explicação foi publicada][1] no blog do Windows Mobile Team. A idéia é que o próprio Windows gerencie a memória do dispositivo e vá fechando os aplicativos que ficam em segundo plano conforme o sistema precisa de mais memória.

Eles fizeram isso na época para combater o PalmOS, que dominava totalmente o mercado e sempre teve (e continua tendo) uma performance absurdamente superior. O PalmOS troca de aplicativos com muita rapidez pois é um sistema imensamente mais simples. A idéia da equipe do Windows Mobile era manter os aplicativos na memória e restaurá-los com mais rapidez.

Infelizmente o gerenciamento automático da memória nem sempre funciona como deveria, e acabamos com o dispositivo cheio de aplicativos abertos e com falta de memória.

No meu Qtek S200 eu uso o [InClose][2], um aplicativo bem prático e que realmente fecha os aplicativos.

 [1]: http://blogs.msdn.com/windowsmobile/archive/2006/10/05/The-Emperor-Has-No-Close.aspx
 [2]: http://www.insoftwarehouse.com/products/inclose/index.php?l=en