---
title: Free vs. FreeAndNil vs. Release
author: Erick Sasse
layout: post
permalink: /free-vs-freeandnil-vs-release/
dsq_thread_id:
  - 262147530
categories:
  - Delphi
---
Durante minha palestra sobre OO no ClubeDelphi TW v&aacute;rias pessoas me perguntaram sobre a diferen&ccedil;a entre Free, FreeAndNil e Release. Como eu n&atilde;o sabia, pois sempre usei Free e nunca tive problemas, fiquei de pesquisar e comentar o que encontrasse. Portanto aqui est&atilde;o meus coment&aacute;rios a respeito:

O Release s&oacute; serve para forms, pois &eacute; introduzido na classe TCustomForm. Ele deve ser usado se voc&ecirc; quer liberar um form de dentro dele mesmo, por exemplo, no evento OnClick de um bot&atilde;o no pr&oacute;prio form. O Release posta uma mensagem CM_RELEASE para o form (veja TCustomForm.Release na unit Forms), que quando processada, dispara o Free. A diferen&ccedil;a &eacute; que o Release processa todas as mensagens e eventos que estiverem na fila do form antes que ele seja destruido. Disparar um Free de dentro do form, pode gerar um AV.

O Free deve ser usado quando voc&ecirc; quer libera o form fora do contexto do form, por exemplo, isto est&aacute; correto:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;Form := TForm1.Create(Application);
Form.ShowModal;
Form.Free;&lt;/code&gt;</pre>

Usar o Release de fora do form tamb&eacute;m gera o mesmo resultado, por&eacute;m de forma menos otimizada, pois a mensagem &eacute; postada para o form que depois chama o Free.

<pre class="wp-code-highlight prettyprint">&lt;code&gt;Form := TForm1.Create(Application);
Form.ShowModal;
Form.Release;&lt;/code&gt;</pre>

O FreeAndNil &eacute; apenas uma procedure que atribui nil a vari&aacute;vel de inst&acirc;ncia e na sequ&ecirc;ncia chama um Free, conforme se pode ver no seu c&oacute;digo ultra-simples em SysUtils:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;procedure FreeAndNil(var Obj);
var
  Temp: TObject;
begin
  Temp := TObject(Obj);
  Pointer(Obj) := nil;
  Temp.Free;
end;&lt;/code&gt;</pre>

Ele s&oacute; &eacute; interessante de ser usado quando voc&ecirc; precisa testar se o objeto est&aacute; instanciado usando o Assigned. Se voc&ecirc; chama apenas o Free a mem&oacute;ria &eacute; liberada da mesma forma, sem vest&iacute;gios, por&eacute;m, se a vari&aacute;vel n&atilde;o for reutilizada e ainda estiver dentro do escopo, continuar&aacute; apontando para um endere&ccedil;o inv&aacute;lido. Isso n&atilde;o consome mais mem&oacute;ria, e isso n&atilde;o &eacute; um problema se voc&ecirc; n&atilde;o precisa mais da vari&aacute;vel. Por isso aconselho sempre a usar vari&aacute;veis com o menor escopo poss&iacute;vel, pois dessa forma, voc&ecirc; quase nunca precisa se preocupar com esse tipo de problema.

Exemplo 1: Vari&aacute;vel implicita:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;procedure TForm1.Button5Click(Sender: TObject);
begin
  with TForm2.Create(nil) do
  try
    ShowModal;
  finally
    Free;
  end;
end;&lt;/code&gt;</pre>

Neste caso voc&ecirc; nem precisa se preocupar com vari&aacute;vel nenhuma. Sei que muita gente odeia o *with*, mas em pequenos trechos como esse, n&atilde;o vejo desvantagens, e ele ainda me economiza a declara&ccedil;&atilde;o da vari&aacute;vel para o form. N&atilde;o preciso usar Release pois estou liberando o form fora dele, e n&atilde;o preciso do FreeAndNil porque em nenhum momento preciso testar vari&aacute;vel nenhuma para saber se existe uma inst&acirc;ncia.

Exemplo 2: Vari&aacute;vel local:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;procedure TForm1.Button4Click(Sender: TObject);
var
  Form: TForm2;
begin
  Form := TForm2.Create(Application);
  Form.ShowModal;
  Form.Free;
end;&lt;/code&gt;</pre>

O resultado &eacute; o mesmo do exemplo 1, por&eacute;m usando uma vari&aacute;vel local. N&atilde;o precisamos do Release pelo mesmo motivo do anterior e n&atilde;o precisamos do FreeAndNil, pois ao final da procedure, a vari&aacute;vel Form sai do escopo e morre. N&atilde;o precisamos nos preocupar em atribuir nil a ela.

Exemplo 3: Form n&atilde;o destruido ao fechar

<pre class="wp-code-highlight prettyprint">&lt;code&gt;type
  TMeuForm = class(TForm)
  public
    class procedure Mostrar;
  end;

implementation

var
  Form: TMeuForm;

{$R *.dfm}

{ TForm2 }

class procedure TMeuForm.Mostrar;
begin
  if not Assigned(Form) then
    Form := TMeuForm.Create(Application);
  Form.Show;
end;
&lt;/code&gt;</pre>

Se voc&ecirc; precisa que um form fique na mem&oacute;ria, pode usar este c&oacute;digo acima. Ao ser chamado pela primeira vez, o Mostrar testa para ver se o form j&aacute; est&aacute; criado, Se n&atilde;o estiver ele cria e mostra, se j&aacute; estiver criado, ele apenas mostra. Este form tem como owner o aplicativo, portanto ao finalizar seu aplicativo, o form ser&aacute; finalizado juntamente e voc&ecirc; n&atilde;o precisa se preocupar com mais nada.

Exemplo 4: Form sem vari&aacute;vel

Um form sem vari&aacute;vel pode ser facilmente mostrado assim:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;TMeuForm.Create(Application).Show;&lt;/code&gt;</pre>

ou assim:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;TMeuForm.Create(Application).ShowModal;&lt;/code&gt;</pre>

E no OnClose do form, basta colocar:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;procedure TMeuForm.FormClose(Sender: TObject; var Action: TCloseAction);
begin
  Action := caFree;
end;&lt;/code&gt;</pre>

Com isso o form &eacute; liberado assim que for fechado.

Enfim, esses quatro exemplos atendem todas as minhas necessidades sem usar Release nem FreeAndNil. Felizmente eu j&aacute; estava no caminho certo.