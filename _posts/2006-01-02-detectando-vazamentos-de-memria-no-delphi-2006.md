---
title: Detectando vazamentos de memória no Delphi 2006
author: Erick Sasse
layout: post
permalink: /detectando-vazamentos-de-memria-no-delphi-2006/
dsq_thread_id:
  - 262148548
categories:
  - Delphi
---
Uma das ótimas melhorias do Delphi 2006 foi trazer o FastMM como seu novo gerenciador de memória. Isso tornou a IDE muito mais rápida, assim como os aplicativos compilados nela.

Uma dos recursos do FastMM é detectar vazamentos de memória (ou memory leaks), que são objetos criados pelo aplicativo, mas não propriamente destruídos.

Para sentir o poder deste recurso, crie um novo projeto VCL Win32 e no OnCreate do form principal coloque:

`TStringList.Create;`

Execute o aplicativo e feche. Nada acontece, mas houve um vazamento de memória porque você criou um objeto e não o destruiu. Agora adicione ao evento a seguinte linha:

`ReportMemoryLeaksOnShutdown := True;`

Execute o aplicativo novamente, e feche. Você verá um aviso que houve um vazamento de memória:

<img border="0" src="http://static.flickr.com/42/81174561_97834992d3_o.png" />

Esse recurso é simplesmente fantástico. Ele me ajudou a eliminar muitos memory leaks dos meus aplicativos. E não adianta. Por mais que você tenha familiaridade com criação e destruição de objetos, você sempre esquece de alguma coisa e vazamentos passam despercebidos. Com este recurso, eles não passarão mais. <img src="http://www.ericksasse.com.br/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" />

Quer deixar ainda melhor? Então ao invés de deixarmos o aviso de memory leak ativado o tempo todo, talvez seja mais interessante que sejamos avisados apenas se estivermos executando o aplicativo dentro do Delphi, não? Você não vai querer usuários seus recebendo estes avisos. Para isso, basta mudar o código para:

`ReportMemoryLeaksOnShutdown := DebugHook  <> 0;`

E se você ainda não está usando o Delphi 2006, pode usá-lo com outras versões do Delphi, só vai ter um pouco mais de trabalho. O [FastMM][1] é um projeto OpenSource mantido no SourceForge, criado e mantido pelo fera Pierre Le Riche, que inclusive ganhou o prêmio Spirit Of Delphi, na última BorCon, pela criação do FastMM.

 [1]: http://sourceforge.net/projects/fastmm/