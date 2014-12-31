---
title: Migração VMWare Server para Hyper-V
author: Erick Sasse
layout: post
permalink: /migracao-vmware-server-para-hyper-v/
dsq_thread_id:
  - 262167240
categories:
  - Microsoft
tags:
  - Hyper-V
  - Microsoft
  - VMWare
---
Aqui na Cadena nossa máquina de build é virtual. Isso é absurdamente prático e recomendo a todos. Nosso &#8220;builder&#8221; já rodou em umas 4 ou 5 máquinas host diferentes aqui, desde Linux a Windows XP e 2003 Server. Sendo que o único trabalho foi fechar a VM, copiar a pasta e abrir em outra máquina.

Essa semana compramos um novo servidor, um Core 2 Duo E8500 3.16 GHz com 4GB de RAM. Instalei o Windows Server 2008 Standard 64 bits nele e resolvi testar o Hyper-V, que é a nova tecnologia de virtualização da Microsoft.

Para minha surpresa foi muito simples migrar uma máquina do VMWare para o Hyper-V. Achei [este post do Ken Schaefer][1] que ajudou bastante. Basicamente o que fiz foi:

  1. Desinstalei o VMWare Tools da VM antes de desligá-la.
  2. Utilizei [o conversor da vmToolKit][2] para converter o disco virtual do VMWare para o formato de disco virtual da Microsoft.
  3. Criei uma nova máquina virtual no Hyper-V mandando utilizar o disco convertido.
  4. Bootei a VM e instalei o &#8220;Integration Services&#8221;, que é o VMWare Tools do Hyper-V, através do menu &#8220;Action -> Insert Integration Services Setup Disk&#8221;.

Simples assim. E já está rodando no Hyper-V perfeitamente e muito mais rápida. O tempo dos nossos builds foram reduzidos em 50%. Porém esse ganho de performance certamente está muito mais ligado ao upgrade no hardware do host do que na mudança de plataforma de virtualização.

Segue um screenshot do console de gerenciamento do Hyper-V:

<div id="attachment_774" style="width: 310px" class="wp-caption alignnone">
  <a href="http://www.ericksasse.com.br/wp-content/uploads/2008/08/hyper-v-manager.png"><img class="size-medium wp-image-774" title="hyper-v-manager" src="http://www.ericksasse.com.br/wp-content/uploads/2008/08/hyper-v-manager-300x231.png" alt="Hyper-V Manager" width="300" height="231" /></a>
  
  <p class="wp-caption-text">
    Hyper-V Manager
  </p>
</div>

 [1]: http://www.adopenstatic.com/cs/blogs/ken/archive/2008/03/23/16710.aspx
 [2]: http://vmtoolkit.com/files/folders/converters/entry8.aspx