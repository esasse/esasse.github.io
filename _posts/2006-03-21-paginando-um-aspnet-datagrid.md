---
title: Paginando um ASP.NET DataGrid
author: Erick Sasse
layout: post
permalink: /paginando-um-aspnet-datagrid/
dsq_thread_id:
  - 262846851
categories:
  - .NET
  - Delphi
---
Hoje foi a primeira vez que precisei habilitar a pagina&ccedil;&atilde;o em um DataGrid em ASP.NET no Delphi. No ASP.NET 1.1, a pagina&ccedil;&atilde;o &eacute; semi-autom&aacute;tica. Voc&ecirc; precisa seguir os seguintes passos:

  1. Setar a propriedade AllowPaging do DataGrid para True.
  2. Implementar o evento PageIndexChanged do DataGrid com o seguinte c&oacute;digo:
`DataGrid1.CurrentPageIndex := e.NewPageIndex;<br />
DataBind;`</ol> 

F&aacute;cil, n&atilde;o? Seu DataGrid agora vai mostrar um rodap&eacute; com as p&aacute;ginas para serem clicadas.  
Al&eacute;m disso voc&ecirc; pode mudar a quantidade de registros mostrados em cada p&aacute;gina alterando a propriedade PageSize.