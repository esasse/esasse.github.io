---
title: Criando Atributos de Validação Customizados no ASP.NET MVC
author: Erick Sasse
layout: post
permalink: /criando-atributos-de-validacao-customizados-no-asp-net-mvc/
dsq_thread_id:
  - 262412257
categories:
  - .NET
  - ASP.NET
  - 'C#'
  - MVC
---
Andei estudando um pouco de ASP.NET MVC, e para quem conhece, sabe que um dos recursos básicos que se vê logo de início é como usar atributos para validação dos modelos.

As validações básicas como campos requeridos, tamanho, expressão regular entre outros, já existem no próprio framework. Então para você determinar que um campo é requerido por exemplo, você decora a propriedade desta forma:

<pre class="wp-code-highlight prettyprint">public class Pessoa
{
    [Required]
    public string Nome { get; set; }
}</pre>

Mas eu estava interessado em criar alguns customizados, pois seria bem prático poder decorar campos como CNPJ, CPF, CEP  e obter a validação específica direto no modelo.

Felizmente isso é muito fácil. Basta criar uma classe derivada de System.ComponentModel.DataAnnotations.ValidationAttribute e sobrescrever o método IsValid retornando true ou false. Veja como ficaria para o atributo CPF:

<pre class="wp-code-highlight prettyprint">public class CPFAttribute : ValidationAttribute
{
    public override bool IsValid(object value)
    {
        var cpf = Convert.ToString(value);

        if (String.IsNullOrEmpty(cpf))
            return true;

        return CPF.Validate(cpf); // Aqui chamada para sua função de validar CPF
    }
}</pre>

Feito isso, basta decorar a propriedade específica da classe:

<pre class="wp-code-highlight prettyprint">public class Pessoa
{
    [Required]
    public string Nome { get; set; }
    [CPF]
    public string CPF { get; set; }
}</pre>

O único detalhe é que essas validações ocorrem apenas no servidor, e não no cliente, como é o padrão (pelo menos no MVC3) da maioria das validações já presentes no framework. Então você vai precisar verificar o ModelState.IsValid no controller.

Esse código foi testado no ASP.NET MVC 3, então não sei se funciona em versões anteriores.