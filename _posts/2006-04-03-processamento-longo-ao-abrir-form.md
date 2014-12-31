---
title: Processamento longo ao abrir form
author: Erick Sasse
layout: post
permalink: /processamento-longo-ao-abrir-form/
dsq_thread_id:
  - 262148790
categories:
  - Delphi
---
Quando voc&ecirc; precisa realizar um longo processo automaticamente (sem necessidade do usu&aacute;rio disparar) ao abrir um form, e deseja mostrar o progresso no pr&oacute;prio form, como voc&ecirc; faz?

Os eventos OnCreate, OnShow, OnActivate do TForm s&atilde;o processados antes do form estar completamente mostrado, o que n&atilde;o serve para essa fun&ccedil;&atilde;o. Eu quero que ao finalizar a &#8220;pintura&#8221; do form, incluindo todos seus controles, um m&eacute;todo meu seja iniciado.

Pedindo ajuda no news da Borland, eu consegui solucionar da seguinte forma:

No OnShow do form, eu incluo uma mensagem customizada na fila de mensagens do meu form usando o PostMessage:

`PostMessage(Handle, (WM_USER + 100), 0, 0);`

Depois preciso implementar minha vers&atilde;o da procedure WndProc, respons&aacute;vel por processar as mensagens do form. Para isso adiciono ela a se&ccedil;&atilde;o protected do form e dou um override:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;type
  TForm1 = class(TForm)
  private
    { Private declarations }
  protected
    procedure WndProc(var Message: TMessage); override;
  public
    { Public declarations }
  end;&lt;/code&gt;</pre>

Na implementa&ccedil;&atilde;o da procedure, eu verifico se recebi a minha mensagem customizada e ent&atilde;o disparo o c&oacute;digo desejado:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;procedure TForm1.WndProc(var Message: TMessage);
begin
  if Message.Msg = (WM_USER + 100) then
    MinhaProcedureDemorada;

  inherited;
end;&lt;/code&gt;</pre>

O resultado final foi &oacute;timo. Ficou exatamente como eu queria. 

Imagino at&eacute; que n&atilde;o seria dif&iacute;cil criar um novo evento no TForm que fosse disparado apenas quando ele terminasse de ser mostrado. T&aacute; algo que poderia ser sugerido para o pessoal da Borland.