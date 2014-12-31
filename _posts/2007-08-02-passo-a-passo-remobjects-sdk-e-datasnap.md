---
title: 'Passo a Passo: RemObjects SDK e DataSnap'
author: Erick Sasse
layout: post
permalink: /passo-a-passo-remobjects-sdk-e-datasnap/
dsq_thread_id:
  - 262150328
categories:
  - Delphi
  - RemObjects
---
Para ajudar quem deseja utilizar o RemObjects SDK como camada de comunicação de um aplicativo DataSnap, substituindo o BSS, aqui vai um passo a passo usando Delphi 2006 e RemObjects SDK 5 para criação de um servidor Combo (que pode funcionar como serviço ou como aplicativo standalone):

File, New, Other. Em Delphi Projects, procure por RemObjects SDK e selecione Combo Service/Standalone.

[![ro1.JPG][1]][2]

O wizard do RO aparece. Escolha uma pasta para o projeto, as outras configurações não precisam ser alteradas. Clique OK.

[![ro2.JPG][3]][4]

Nesse momento você já tem um servidor e um cliente prontos, organizados em um grupo de projetos na IDE.

[![ro3.JPG][5]][6]

Vamos criar um novo serviço no servidor que exponha nossos DataSetProviders do DataSnap. Dê um clique duplo no NewProject.exe para selecionar o servido de aplicação e no menu RemObjects da IDE selecione &#8220;Edit Service Library&#8221; ou Ctrl+Alt+U. Isso vai abrir o Service Builder já mostrando que seu servidor tem um serviço denominado &#8220;NewService&#8221;.

[![ro4.JPG][7]][8]

Para criar um serviço DataSnap, precisamos incluir um RODL que já acompanha o RO e que possui todas as definições da interface padrão de servidores DataSnap. Para isso, estando no Service Builder, selecione o menu Edit, Use Existing RODL e depois selecione DataSnap. Agora o nome &#8220;uRODataSnap&#8221; já deve aparecer na treeview ao lado esquerdo.

[![ro5.JPG][9]][10]

Agora crie o novo serviço clicando no botão Service e dê o nome de &#8220;DataSnapService&#8221;. Na combo Ancestor selecione AppServer. Isso diz para o RO que esse serviço é descendente de AppServer, que é a interface de servidores DataSnap.

[![ro6.JPG][11]][12]

Feche o Service Builder, e tente compilar o servidor (Ctrl+F9). Neste momento uma nova tela do RO aparece perguntando como você deseja implementar o novo DataSnapService. Utilize a opção recomendada, &#8220;RemObjects SDK Remote Datamodule&#8221;.

[![ro7.JPG][13]][14]

Agora você já tem um DataModule onde pode colocar seus componentes de dados e o DataSetProvider.

[![ro12.JPG][15]][16]

Coloque alguns, compile o servidor e execute usando a opção Launch Server Executable do menu RemObjects SDK na IDE ou usando o atalho Ctrl+Alt+F9. Seu servidor já está rodando.

![ro9.JPG][17]

Dê um duplo clique no NewProjectClient.exe para selecionar o cliente. Abra o form do cliente, apague o componente RORemoteService, que não utlizaremos e coloque um componente TRODataSnapConnection. Selecione o componente e ligue com o ROChannel e a ROMessage que já estão no form. Na propriedade ServerName, coloque o nome do serviço DataSnap que criamos no servidor, ou seja, &#8220;DataSnapService&#8221;.

[![ro10.JPG][18]][19]

Coloque um ClientDataSet no form, ligue ele ao RODataSnapConnection usando a propriedade RemoteServer e selecione o provider na propriedade ProviderName.

[![ro11.JPG][20]][21]

Pronto! Você já tem um aplicativo em 3 camadas DataSnap usando RO como camada de comunicação. Se desejar rodar o servidor como serviço do Windows, basta registrar o serviço usando &#8220;NewProject.exe /install&#8221; na linha de comando.

 [1]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro1.thumbnail.JPG
 [2]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro1.JPG "ro1.JPG"
 [3]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro2.thumbnail.JPG
 [4]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro2.JPG "ro2.JPG"
 [5]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro3.thumbnail.JPG
 [6]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro3.JPG "ro3.JPG"
 [7]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro4.thumbnail.JPG
 [8]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro4.JPG "ro4.JPG"
 [9]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro5.thumbnail.JPG
 [10]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro5.JPG "ro5.JPG"
 [11]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro6.thumbnail.JPG
 [12]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro6.JPG "ro6.JPG"
 [13]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro7.thumbnail.JPG
 [14]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro7.JPG "ro7.JPG"
 [15]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro12.thumbnail.JPG
 [16]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro12.JPG "ro12.JPG"
 [17]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro9.JPG
 [18]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro10.thumbnail.JPG
 [19]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro10.JPG "ro10.JPG"
 [20]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro11.thumbnail.JPG
 [21]: http://www.ericksasse.com.br/wp-content/uploads/2007/08/ro11.JPG "ro11.JPG"