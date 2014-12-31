---
title: Como Assinar Digitalmente Seus Aplicativos
author: Erick Sasse
layout: post
permalink: /como-assinar-digitalmente-seus-aplicativos/
dsq_thread_id:
  - 262151137
categories:
  - Geral
---
No Windows Vista, quando o usuário tem o UAC ativado e vai instalar um aplicativo, uma confirmação é solicitada. Se seu aplicativo não possuir uma assinatura digital, uma tela bem ameaçadora de aviso é mostrada ao usuário dizendo que um programa não identificado precisa da sua autorização para ser executado. Avisos parecidos também aparecem em diversos outros momentos, como quando se tenta executar um programa por uma caminho de rede.

Uma forma de amenizar esses alertas ao usuário é assinar digitalmente seus aplicativos. A assinatura digital teoricamente garante ao usuário que o arquivo veio realmente da empresa desenvolvedora, e mostra telas bem mais amigáveis, mostrando o nome da sua empresa como origem do aplicativo.

Isso mostra que toda empresa de software deveria assinar seus aplicativos. E foi isso que nós implementamos aqui nos últimos dias e vou dar algumas dicas de como fazer.

  * Você precisa comprar um certificado digital de uma [entidade certificadora de confiança][1] da Microsoft. Eu comprei da Comodo através da [K Software][2]. Segui os procedimentos descritos na própria página e foi tranquilo. Utilizei o Internet Explorer durante todo o processo, pois no Chrome não foi legal.
  * Após compra você vai receber um e-mail solicitando os documentos da empresa para comprovar que ela existe e que você é o responsável. Eu mandei o cartão CNPJ da empresa impresso em PDF pelo site da Receita Federal.
  * Eles também pedem um telefone pois dizem que vão te ligar, mas não me ligaram.
  * Depois de um ou dois dias recebi o e-mail dizendo que o certificado estava pronto, com o link para baixar. Utilizei o Internet Explorer 8 e seguindo as instruções, o certificado foi instalado na minha máquina.
  * Como eu iria fazer a assinatura durante nosso processo de build, precisava copiar o certificado para nossa máquina de build. Então exportei o certificado, entrando em Opções de Internet, Conteúdo, Certificados. Dessa forma foi gerado um arquivo .pfx, que é exatamente o que o FinalBuilder precisa na sua action Authenticode para aplicar assinaturas.
  * Também é necessária uma URL da entidade certificadora para aplicar timestamp nos arquivos. Isso geralmente está nas páginas de FAQ da entidade. Como [aqui][3] no caso da Comodo.
  * Copiei o arquivo .pfx para minha máquina de build, apontei o FinalBuilder para ele, configurei a URL de timestamp e pronto, meus arquivos (*.exe) estão todos assinados!
  * Que eu saiba não existe limite e você pode assinar quantos arquivos quiser durante a validade do seu certificado.
  * Nós assinamos todos executáveis (*.exe), incluindo instaladores.
  * Também é possível assinar outros tipos de arquivos, mas como eu não fiz, não tenho dicas a respeito.
  * Para quem não usa FinalBuilder, precisa pesquisar como fazer sem ele, pois eu não fui atrás disso. Na página da K Software existe propaganda de uma ferramenta para assinar, mas tenho certeza que ou existem aplicativos no próprio Windows para isso, ou gratuítos em algum lugar para baixar.

Espero que isso ajude um pouco.

 [1]: http://msdn.microsoft.com/en-us/library/ms995347.aspx
 [2]: http://www.ksoftware.net/code_signing.html
 [3]: http://www.instantssl.com/code-signing/code-signing-faq.html