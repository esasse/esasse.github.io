---
title: 'Microsoft Innovation Days: LINQ'
author: Erick Sasse
layout: post
permalink: /microsoft-innovation-days-linq/
dsq_thread_id:
  - 262149895
categories:
  - .NET
  - 'C#'
---
Hoje participei do Innovation Days na Microsoft em SP, um evento que promete ser mensal para parceiros Microsoft. Foram 4 horas de palestras com desenvolvedores da Microsoft apresentando o [LINQ][1] (Language Integrated Query) e as novidades do [C# 3.0][2]. Palestras avançadas com conteúdo realmente muito interessante e com palestrantes competentes.

É satisfatório ver a evolução do C# e do .NET framework e ao mesmo tempo frustrante por não ser minha plataforma principal de desenvolvimento. Já estou começando a invejar os desenvolvedores que podem tirar proveito de todas essas novidades no dia-a-dia e sempre torcendo para que [minha ferramenta principal][3] evolua mais rapidamente.

Em .NET não tenho mais dúvida, é Visual Studio e C# mesmo e não tem pra ninguém. Os caras estão levando muito a sério isso e tanto a IDE como a linguagem estão ficando (ou já são) imbatíveis. Eu acho que até existem linguagens melhores que o C#, como o [Chrome][4] por exemplo, mas o C# é de fato o padrão em .NET. Praticamente tudo que se encontra na Internet está em C#. Componentes, exemplos, livros, etc, e isso queira ou não, acaba pesando na escolha da linguagem.

Se você ainda não conhece o LINQ, vale a pena dar uma pesquisada. Eu já sabia bem do que se tratava antes do evento, mas não tinha testado pessoalmente. Ele permite usar comandos muito parecidos com SQL direto no código em qualquer coleção de objetos .NET, banco de dados ou arquivo XML. Você poderia por exemplo consultar no seu banco de dados todos os clientes da cidade de Americana usando o sequinte comando:

<pre class="wp-code-highlight prettyprint">&lt;p class="Code"&gt;&lt;span lang="EN-US"&gt;&lt;/span&gt;&lt;span style="color: blue"&gt;var&lt;/span&gt; q =
&lt;span style="color: blue"&gt;  from&lt;/span&gt; c &lt;span style="color: blue"&gt;in&lt;/span&gt; Clientes
&lt;span style="color: blue"&gt;  where&lt;/span&gt; c.Cidade == &lt;span style="color: #993300"&gt;"Americana"&lt;/span&gt;
&lt;span style="color: blue"&gt;  select&lt;/span&gt; c;&lt;/p&gt;</pre>

Isso seria traduzido para SQL, enviado para o banco e retornada uma coleção de objetos Cliente contendo somente os clientes que forem de Americana. Veja que tudo isso é verificado pelo compilador, com Intellisense e tudo o que temos direito. É realmente algo fantástico.

Alguns dos próximos Innovation Days devem falar de [WCF][5] (que me interessa muito) e [WWF][6].

 [1]: http://msdn2.microsoft.com/en-us/netframework/aa904594.aspx
 [2]: http://msdn2.microsoft.com/en-us/vcsharp/aa336745.aspx
 [3]: http://www.ericksasse.com.br/nao-escreverei-mais-sobre-delphi/
 [4]: http://www.chromesville.com/
 [5]: http://msdn2.microsoft.com/en-us/netframework/aa663324.aspx
 [6]: http://msdn2.microsoft.com/en-us/netframework/aa663328.aspx