---
title: Bug ao chamar WebService em Win32
author: Erick Sasse
layout: post
permalink: /bug-ao-chamar-webservice-em-win32/
dsq_thread_id:
  - 262148024
categories:
  - Delphi
---
N&atilde;o adianta querer me crucificar por ficar reclamando de bugs no Delphi. Infelizmente achei mais um. 

Hoje apanhei por cerca de tr&ecirc;s horas at&eacute; identificar o lar&aacute;pio. Acontece o seguinte, quando eu fa&ccedil;o uma chamada a um webservice no meu aplicativo, uma das classes da VCL (TTypeTranslator da unit TypeTrans) envolvidas na chamada do WS simplesmente altera (no m&eacute;todo CastSoapToNative) o separador decimal padr&atilde;o da aplica&ccedil;&atilde;o para o formato americano (com ponto no lugar de v&iacute;rgula), detonando todas as opera&ccedil;&otilde;es num&eacute;ricas do aplicativo. 

Fiz uma pesquisa no QualityCentral da Borland e n&atilde;o encontrei este bug reportado, ent&atilde;o fiz minha parte e reportei: <http://qc.borland.com/wc/qcmain.aspx?d=16184>

Como alterar o c&oacute;digo da VCL &eacute; uma p&eacute;ssima id&eacute;ia em qualquer circunst&acirc;ncia, para resolver, eu salvo o DecimalSeparator atual antes de chamar o WebService e depois o restauro:

<pre class="wp-code-highlight prettyprint">&lt;code&gt;var
  CorrectDecimalSeparator: char;
begin
  CorrectDecimalSeparator := DecimalSeparator;
  try
      // Chamada aos m&eacute;todos do WS
  finally
    DecimalSeparator := CorrectDecimalSeparator;
  end;
end;&lt;/code&gt;</pre>

Esse problema est&aacute; presente no Delphi 7 e 2005. Espero que consigar ser corrigido j&aacute; no Dexter, mas n&atilde;o sei n&atilde;o&#8230;

Update: O Rodolfo apontou que o bug já foi reportado sim para a Borland, há mais de um ano atrás: <http://qc.borland.com/qc/wc/qcmain.aspx?d=8928>.