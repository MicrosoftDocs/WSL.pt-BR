---
title: Notas sobre a versão do subsistema Windows para Linux
description: Leia as notas sobre a versão do Subsistema do Windows para Linux. Essas notas sobre a versão incluem problemas corrigidos e são atualizadas semanalmente.
keywords: notas sobre a versão, wsl, windows, subsistema do windows para linux, windowssubsystem, ubuntu
author: benhillis
ms.date: 05/15/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: d7b868f959c62879524dcbdad20509ef35fecfce
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413267"
---
# <a name="release-notes-for-windows-subsystem-for-linux"></a><span data-ttu-id="1a9f1-105">Notas sobre a versão do subsistema Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="1a9f1-105">Release Notes for Windows Subsystem for Linux</span></span>

## <a name="build-20211"></a><span data-ttu-id="1a9f1-106">Build 20211</span><span class="sxs-lookup"><span data-stu-id="1a9f1-106">Build 20211</span></span>
<span data-ttu-id="1a9f1-107">Para obter informações gerais do Windows sobre o build 20211, visite o [blog do Windows](https://blogs.windows.com/windows-insider/2020/09/10/announcing-windows-10-insider-preview-build-20211/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-107">For general Windows information on build 20211 visit the [Windows blog](https://blogs.windows.com/windows-insider/2020/09/10/announcing-windows-10-insider-preview-build-20211/).</span></span>

* <span data-ttu-id="1a9f1-108">Introduza `wsl.exe --mount` para montar discos físicos ou virtuais.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-108">Introduce `wsl.exe --mount` for mounting physical or virtual disks.</span></span> <span data-ttu-id="1a9f1-109">Para obter mais informações, confira [Acessar sistemas de arquivos do Linux no Windows e no WSL 2](https://devblogs.microsoft.com/commandline/access-linux-filesystems-in-windows-and-wsl-2/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-109">For more information see [Access Linux filesystems in Windows and WSL 2](https://devblogs.microsoft.com/commandline/access-linux-filesystems-in-windows-and-wsl-2/).</span></span>
* <span data-ttu-id="1a9f1-110">Conserte a falha no serviço LxssManager ao verificar se a VM está ociosa.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-110">Fix crash in LxssManager service when checking if the VM is idle.</span></span> <span data-ttu-id="1a9f1-111">[GH 5768]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-111">[GH 5768]</span></span>
* <span data-ttu-id="1a9f1-112">Suporte para arquivos VHD compactados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-112">Support for compressed VHD files.</span></span> <span data-ttu-id="1a9f1-113">[GH 4103]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-113">[GH 4103]</span></span>
* <span data-ttu-id="1a9f1-114">Verifique se as bibliotecas de modo de usuário do Linux para c:\windows\system32\lxss\lib estão preservadas na atualização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-114">Ensure that Linux user mode libs installed to c:\windows\system32\lxss\lib are preserved across OS upgrade.</span></span> <span data-ttu-id="1a9f1-115">[GH 5848]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-115">[GH 5848]</span></span>
* <span data-ttu-id="1a9f1-116">A capacidade de listar as distribuições disponíveis que podem ser instaladas com `wsl --install --list-distributions` foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-116">Added the ability to list available distributions that can be installed with `wsl --install --list-distributions`.</span></span>
* <span data-ttu-id="1a9f1-117">Agora, as instâncias de WSL são encerradas quando o usuário faz logoff.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-117">WSL instances are now terminated when the user logs off.</span></span>

## <a name="build-20190"></a><span data-ttu-id="1a9f1-118">Build 20190</span><span class="sxs-lookup"><span data-stu-id="1a9f1-118">Build 20190</span></span>
<span data-ttu-id="1a9f1-119">Para obter informações gerais do Windows sobre o build 20190, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/08/12/announcing-windows-10-insider-preview-build-20190/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-119">For general Windows information on build 20190 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2020/08/12/announcing-windows-10-insider-preview-build-20190/).</span></span>

* <span data-ttu-id="1a9f1-120">Consertar bug que impede a inicialização de instâncias WSL1.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-120">Fix bug preventing WSL1 instances from launching.</span></span> <span data-ttu-id="1a9f1-121">[GH 5633]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-121">[GH 5633]</span></span>
* <span data-ttu-id="1a9f1-122">Consertar o travamento ao redirecionar a saída do processo do Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-122">Fix hang when redirecting Windows process output.</span></span> <span data-ttu-id="1a9f1-123">[GH 5648]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-123">[GH 5648]</span></span>
* <span data-ttu-id="1a9f1-124">Adicionar a opção %userprofile%\\.wslconfig para controlar o tempo limite de ociosidade da VM (wsl2.vmIdleTimeout=<time_in_ms>).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-124">Add %userprofile%\\.wslconfig option to control the VM idle timeout (wsl2.vmIdleTimeout=<time_in_ms>).</span></span>
* <span data-ttu-id="1a9f1-125">Dar suporte à inicialização de aliases de execução de aplicativo do WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-125">Support launching app execution aliases from WSL.</span></span>
* <span data-ttu-id="1a9f1-126">O suporte para instalar as distribuições e o kernel do WSL2 em wsl.exe --install foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-126">Added support for installing the WSL2 kernel and distributions to wsl.exe --install.</span></span>

## <a name="build-20175"></a><span data-ttu-id="1a9f1-127">Build 20175</span><span class="sxs-lookup"><span data-stu-id="1a9f1-127">Build 20175</span></span>
<span data-ttu-id="1a9f1-128">Para obter informações gerais do Windows sobre o build 20175, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/07/22/announcing-windows-10-insider-preview-build-20175/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-128">For general Windows information on build 20175 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2020/07/22/announcing-windows-10-insider-preview-build-20175/).</span></span>

* <span data-ttu-id="1a9f1-129">Ajuste a atribuição de memória padrão da VM WSL2 para ser 50% da memória do host ou 8 GB, o que for menor [GH 4166].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-129">Adjust default memory assignment of WSL2 VM to be 50% of host memory or 8GB, whichever is less [GH 4166].</span></span>
* <span data-ttu-id="1a9f1-130">Altere o prefixo \\\\wsl$ para \\\\wsl a fim de dar suporte à análise de URI.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-130">Change \\\\wsl$ prefix to \\\\wsl to support URI parsing.</span></span> <span data-ttu-id="1a9f1-131">O antigo caminho \\\\wsl$ ainda é compatível.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-131">The old \\\\wsl$ path is still supported.</span></span>
* <span data-ttu-id="1a9f1-132">Habilite a virtualização aninhada para WSL2 por padrão em amd64.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-132">Enable nested virtualization for WSL2 by default on amd64.</span></span> <span data-ttu-id="1a9f1-133">Você pode desabilitar isso por meio de %userprofile%\\.wslconfig ([wsl2] nestedVirtualization=false).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-133">You can disable this via %userprofile%\\.wslconfig ([wsl2] nestedVirtualization=false).</span></span>
* <span data-ttu-id="1a9f1-134">Faça com que a demanda wsl.exe --update inicie o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-134">Make wsl.exe --update demand start Microsoft Update.</span></span>
* <span data-ttu-id="1a9f1-135">Dê suporte à renomeação em um arquivo somente leitura no DrvFs.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-135">Support renaming over a read-only file in DrvFs.</span></span>
* <span data-ttu-id="1a9f1-136">Verifique se as mensagens de erro são sempre impressas na página de código correta.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-136">Ensure error messages are always printed in the correct codepage.</span></span>

## <a name="build-20150"></a><span data-ttu-id="1a9f1-137">Build 20150</span><span class="sxs-lookup"><span data-stu-id="1a9f1-137">Build 20150</span></span>
<span data-ttu-id="1a9f1-138">Para obter informações gerais do Windows sobre o build 20150, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/06/17/announcing-windows-10-insider-preview-build-20150/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-138">For general Windows information on build 20150 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2020/06/17/announcing-windows-10-insider-preview-build-20150/).</span></span>

* <span data-ttu-id="1a9f1-139">Para obter informações sobre a computação GPU do WSL2, confira o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/06/17/announcing-windows-10-insider-preview-build-20150/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-139">WSL2 GPU compute see [Windows blog](https://blogs.windows.com/windowsexperience/2020/06/17/announcing-windows-10-insider-preview-build-20150/) for more information.</span></span>
* <span data-ttu-id="1a9f1-140">Introdução de wsl.exe – instalação da opção de linha de comando para configurar facilmente o WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-140">Introduce wsl.exe --install command line option to easily set up WSL.</span></span>
* <span data-ttu-id="1a9f1-141">Introdução de wsl.exe – atualização da opção de linha de comando para gerenciar atualizações do kernel WSL2.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-141">Introduce wsl.exe --update command line option to manage updates to the WSL2 kernel.</span></span> 
* <span data-ttu-id="1a9f1-142">Definição de WSL2 como o padrão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-142">Set WSL2 as the default.</span></span>
* <span data-ttu-id="1a9f1-143">Aumento do tempo limite de desligamento normal da VM WSL2.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-143">Increase WSL2 vm graceful shutdown timeout.</span></span>
* <span data-ttu-id="1a9f1-144">Correção da condição de corrida virtio-9p ao mapear a memória do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-144">Fix virtio-9p race condition when mapping device memory.</span></span>
* <span data-ttu-id="1a9f1-145">Não execução de um servidor 9p elevado se UAC estiver desabilitado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-145">Don't run an elevated 9p server if UAC is disabled.</span></span>

## <a name="build-19640"></a><span data-ttu-id="1a9f1-146">Build 19640</span><span class="sxs-lookup"><span data-stu-id="1a9f1-146">Build 19640</span></span>
<span data-ttu-id="1a9f1-147">Para obter informações gerais do Windows sobre o build 19640, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/06/03/announcing-windows-10-insider-preview-build-19640/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-147">For general Windows information on build 19640 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2020/06/03/announcing-windows-10-insider-preview-build-19640/).</span></span>

* <span data-ttu-id="1a9f1-148">[WSL2] Aprimoramentos de estabilidade para virtio-9p (drvfs).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-148">[WSL2] Stability improvements for virtio-9p (drvfs).</span></span>

## <a name="build-19555"></a><span data-ttu-id="1a9f1-149">Build 19555</span><span class="sxs-lookup"><span data-stu-id="1a9f1-149">Build 19555</span></span>
<span data-ttu-id="1a9f1-150">Para obter informações gerais do Windows sobre o build 19555, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/01/30/announcing-windows-10-insider-preview-build-19555/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-150">For general Windows information on build 19555 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2020/01/30/announcing-windows-10-insider-preview-build-19555/).</span></span>

* <span data-ttu-id="1a9f1-151">[WSL2] Use um cgroup de memória para limitar a quantidade de memória usada pelas operações de instalação e conversão [GH 4669]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-151">[WSL2] Use a memory cgroup to limit the amount of memory used by install and conversion operations [GH 4669]</span></span>
* <span data-ttu-id="1a9f1-152">Torne o wsl.exe presente quando o componente opcional do Subsistema do Windows para Linux não estiver habilitado para aprimorar a descoberta de recursos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-152">Make wsl.exe present when the Windows Subsystem for Linux optional component is not enabled to improve feature discoverability.</span></span>
* <span data-ttu-id="1a9f1-153">Altere o wsl.exe para imprimir o texto de ajuda se o componente opcional do WSL não estiver instalado</span><span class="sxs-lookup"><span data-stu-id="1a9f1-153">Change wsl.exe to print help text if the WSL optional component is not installed</span></span>
* <span data-ttu-id="1a9f1-154">Corrija a condição de corrida ao criar instâncias</span><span class="sxs-lookup"><span data-stu-id="1a9f1-154">Fix race condition when creating instances</span></span>
* <span data-ttu-id="1a9f1-155">Crie wslclient.dll que contém todas as funcionalidades de linha de comando</span><span class="sxs-lookup"><span data-stu-id="1a9f1-155">Create wslclient.dll that contains all command line functionality</span></span>
* <span data-ttu-id="1a9f1-156">Impeça falhas durante a interrupção do serviço LxssManagerUser</span><span class="sxs-lookup"><span data-stu-id="1a9f1-156">Prevent crash during LxssManagerUser service stop</span></span>
* <span data-ttu-id="1a9f1-157">Corrija a falha rápida wslapi.dll quando o parâmetro distroName for NULL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-157">Fix wslapi.dll fast fail when distroName parameter is NULL</span></span>

## <a name="build-19041"></a><span data-ttu-id="1a9f1-158">Build 19041</span><span class="sxs-lookup"><span data-stu-id="1a9f1-158">Build 19041</span></span>
<span data-ttu-id="1a9f1-159">Para obter informações gerais do Windows sobre o build 19041, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/12/10/announcing-windows-10-insider-preview-build-19041/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-159">For general Windows information on build 19041 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/12/10/announcing-windows-10-insider-preview-build-19041/).</span></span>

* <span data-ttu-id="1a9f1-160">[WSL2] Limpe a máscara de sinal antes de iniciar os processos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-160">[WSL2] Clear the signal mask before launching the processes</span></span>
* <span data-ttu-id="1a9f1-161">[WSL2] Atualize o kernel do Linux para 4.19.84</span><span class="sxs-lookup"><span data-stu-id="1a9f1-161">[WSL2] Update Linux kernel to 4.19.84</span></span>
* <span data-ttu-id="1a9f1-162">Manipule a criação do symlink /etc/resolv.conf quando o symlink não for relativo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-162">Handle creation of /etc/resolv.conf symlink when the symlink is non-relative</span></span>

## <a name="build-19028"></a><span data-ttu-id="1a9f1-163">Build 19028</span><span class="sxs-lookup"><span data-stu-id="1a9f1-163">Build 19028</span></span>
<span data-ttu-id="1a9f1-164">Para obter informações gerais do Windows sobre o build 19028, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/11/19/announcing-windows-10-insider-preview-build-19028/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-164">For general Windows information on build 19028 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/11/19/announcing-windows-10-insider-preview-build-19028/).</span></span>

* <span data-ttu-id="1a9f1-165">[WSL2] Atualização do kernel do Linux para 4.19.81</span><span class="sxs-lookup"><span data-stu-id="1a9f1-165">[WSL2] Update Linux kernel to 4.19.81</span></span>
* <span data-ttu-id="1a9f1-166">[WSL2] Alteração da permissão padrão de /dev/net/tun para 0666 [GH 4629]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-166">[WSL2] Change the default permission of /dev/net/tun to 0666 [GH 4629]</span></span>
* <span data-ttu-id="1a9f1-167">[WSL2] Ajuste da quantidade padrão de memória atribuída à VM do Linux para 80% da memória do host</span><span class="sxs-lookup"><span data-stu-id="1a9f1-167">[WSL2] Tweak default amount of memory assigned to Linux VM to be 80% of host memory</span></span>
* <span data-ttu-id="1a9f1-168">[WSL2] Correção do servidor de interoperabilidade para lidar com as solicitações usando um tempo limite para que chamadores inválidos não possam interromper o servidor</span><span class="sxs-lookup"><span data-stu-id="1a9f1-168">[WSL2] fix interop server to handle requests with a timeout so bad callers cannot hang the server</span></span>

## <a name="build-19018"></a><span data-ttu-id="1a9f1-169">Build 19018</span><span class="sxs-lookup"><span data-stu-id="1a9f1-169">Build 19018</span></span>
<span data-ttu-id="1a9f1-170">Para obter informações gerais do Windows sobre o build 19018, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/11/05/announcing-windows-10-insider-preview-build-19018/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-170">For general Windows information on build 19018 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/11/05/announcing-windows-10-insider-preview-build-19018/).</span></span>

* <span data-ttu-id="1a9f1-171">[WSL2] Uso do cache=mmap como padrão em montagens 9p para corrigir aplicativos dotnet</span><span class="sxs-lookup"><span data-stu-id="1a9f1-171">[WSL2] Use cache=mmap as the default for 9p mounts to fix dotnet apps</span></span>
* <span data-ttu-id="1a9f1-172">[WSL2] Correções para retransmissão de localhost [GH 4340]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-172">[WSL2] Fixes for localhost relay [GH 4340]</span></span>
* <span data-ttu-id="1a9f1-173">[WSL2] Introdução de uma montagem tmpfs compartilhada entre distribuições para compartilhar o estado entre elas</span><span class="sxs-lookup"><span data-stu-id="1a9f1-173">[WSL2] Introduce a cross-distro shared tmpfs mount for sharing state between distros</span></span>
* <span data-ttu-id="1a9f1-174">Correção da restauração de uma unidade de rede persistente para \\\\wsl$</span><span class="sxs-lookup"><span data-stu-id="1a9f1-174">Fix restoring persistent network drive for \\\\wsl$</span></span>

## <a name="build-19013"></a><span data-ttu-id="1a9f1-175">Build 19013</span><span class="sxs-lookup"><span data-stu-id="1a9f1-175">Build 19013</span></span>
<span data-ttu-id="1a9f1-176">Para obter informações gerais sobre o Windows no build 19013, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/10/29/announcing-windows-10-insider-preview-build-19013/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-176">For general Windows information on build 19013 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/10/29/announcing-windows-10-insider-preview-build-19013/).</span></span>

* <span data-ttu-id="1a9f1-177">[WSL2] Melhorar o desempenho de memória da VM do utilitário WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-177">[WSL2] Improve memory performance of WSL utility VM.</span></span> <span data-ttu-id="1a9f1-178">A memória que não está mais em uso será liberada de volta para o host.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-178">Memory that is no longer in use will be freed back to the host.</span></span>
* <span data-ttu-id="1a9f1-179">[WSL2] Atualização da versão do kernel para 4.19.79.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-179">[WSL2] Update kernel version to 4.19.79.</span></span> <span data-ttu-id="1a9f1-180">(adicione CONFIG_HIGH_RES_TIMERS, CONFIG_TASK_XACCT, CONFIG_TASK_IO_ACCOUNTING, CONFIG_SCHED_HRTICK e CONFIG_BRIDGE_VLAN_FILTERING).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-180">(add CONFIG_HIGH_RES_TIMERS, CONFIG_TASK_XACCT, CONFIG_TASK_IO_ACCOUNTING, CONFIG_SCHED_HRTICK, and CONFIG_BRIDGE_VLAN_FILTERING).</span></span>
* <span data-ttu-id="1a9f1-181">[WSL2] Corrija a retransmissão de entrada para lidar com casos em que stdin é um identificador de pipe que não está fechado [GH 4424]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-181">[WSL2] Fix input relay to handle cases where stdin is a pipe handle that is not closed [GH 4424]</span></span>
* <span data-ttu-id="1a9f1-182">Faça a verificação de \\\\wsl$ case-insensitive.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-182">Make the check for \\\\wsl$ case-insensitive.</span></span>
```
[wsl2]
pageReporting = <bool>    # Enable or disable the free memory page reporting feature (default true).
idleThreshold = <integer> # Set the idle threshold for memory compaction, 0 disables the feature (default 1).
```

## <a name="build-19002"></a><span data-ttu-id="1a9f1-183">Build 19002</span><span class="sxs-lookup"><span data-stu-id="1a9f1-183">Build 19002</span></span>
<span data-ttu-id="1a9f1-184">Para obter informações gerais do Windows sobre o Build 19002, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/10/17/announcing-windows-10-insider-preview-build-19002/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-184">For general Windows information on build 19002 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/10/17/announcing-windows-10-insider-preview-build-19002/).</span></span>

* <span data-ttu-id="1a9f1-185">[WSL] Correção de um problema com o tratamento de alguns caracteres Unicode: https://github.com/microsoft/terminal/issues/2770</span><span class="sxs-lookup"><span data-stu-id="1a9f1-185">[WSL] Fix issue with handling of some Unicode characters: https://github.com/microsoft/terminal/issues/2770</span></span>
* <span data-ttu-id="1a9f1-186">[WSL] Correção de casos raros em que distribuições podiam ter o registro cancelado se fossem iniciadas imediatamente após uma atualização de compilação a compilação.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-186">[WSL] Fix rare cases where distros could be unregistered if launched immediately after a build-to-build upgrade.</span></span>
* <span data-ttu-id="1a9f1-187">[WSL] Correção de um problema secundário com wsl.exe: desligamentos em que os timers de ociosidade da instância não foram cancelados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-187">[WSL] Fix minor issue with wsl.exe --shutdown where instance idle timers were not cancelled.</span></span>

## <a name="build-18995"></a><span data-ttu-id="1a9f1-188">Build 18995</span><span class="sxs-lookup"><span data-stu-id="1a9f1-188">Build 18995</span></span>
<span data-ttu-id="1a9f1-189">Para obter informações gerais do Windows sobre o build 18995, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/10/03/announcing-windows-10-insider-preview-build-18995/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-189">For general Windows information on build 18995 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/10/03/announcing-windows-10-insider-preview-build-18995/).</span></span>

* <span data-ttu-id="1a9f1-190">[WSL2] Correção de um problema em que as montagens DrvFs pararam de funcionar após uma operação ter sido interrompida (por exemplo, ctrl-c) [GH 4377]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-190">[WSL2] Fix an issue where DrvFs mounts stopped working after an operation was interrupted (e.g. ctrl-c) [GH 4377]</span></span>
* <span data-ttu-id="1a9f1-191">[WSL2] Correção do tratamento de mensagens hvsocket muito grandes [GH 4105]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-191">[WSL2] Fix handling of very large hvsocket messages [GH 4105]</span></span>
* <span data-ttu-id="1a9f1-192">[WSL2] Correção do problema com a interoperabilidade quando stdin é um arquivo [GH 4475]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-192">[WSL2] Fix issue with interop when stdin is a file [GH 4475]</span></span>
* <span data-ttu-id="1a9f1-193">[WSL2] Correção da falha de serviço quando um estado de rede inesperado é encontrado [GH 4474]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-193">[WSL2] Fix service crash when unexpected network state is encountered [GH 4474]</span></span>
* <span data-ttu-id="1a9f1-194">[WSL2] Consulta do nome da distribuição do servidor de interoperabilidade se o processo atual não tem a variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="1a9f1-194">[WSL2] Query the distro name from the interop server if the current process does not have the environment variable</span></span>
* <span data-ttu-id="1a9f1-195">[WSL2] Correção do problema com a interoperabilidade quando stdin é um arquivo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-195">[WSL2] Fix issue with interop whe stdin is a file</span></span>
* <span data-ttu-id="1a9f1-196">[WSL2] Atualização da versão do kernel do Linux para 4.19.72</span><span class="sxs-lookup"><span data-stu-id="1a9f1-196">[WSL2] Update Linux kernel version to 4.19.72</span></span>
* <span data-ttu-id="1a9f1-197">[WSL2] Adição da capacidade de especificar outros parâmetros de linha de comando do kernel por meio de .wslconfig</span><span class="sxs-lookup"><span data-stu-id="1a9f1-197">[WSL2] Add ability to specify additional kernel command line parameters via .wslconfig</span></span>
```
[wsl2]
kernelCommandLine = <string> # Additional kernel command line arguments
```

## <a name="build-18990"></a><span data-ttu-id="1a9f1-198">Build 18990</span><span class="sxs-lookup"><span data-stu-id="1a9f1-198">Build 18990</span></span>
<span data-ttu-id="1a9f1-199">Para obter informações gerais do Windows sobre o Build 18990, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/09/24/announcing-windows-10-insider-preview-build-18990/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-199">For general Windows information on build 18990 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/09/24/announcing-windows-10-insider-preview-build-18990/).</span></span>

* <span data-ttu-id="1a9f1-200">Melhora do desempenho das listagens de diretório em \\\\wsl$</span><span class="sxs-lookup"><span data-stu-id="1a9f1-200">Improve the performance for directory listings in \\\\wsl$</span></span>
* <span data-ttu-id="1a9f1-201">[WSL2] Injetar entropia de inicialização adicional [GH 4416]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-201">[WSL2] Inject additional boot entropy [GH 4416]</span></span>
* <span data-ttu-id="1a9f1-202">[WSL2] Correção para interoperabilidade do Windows ao usar su/sudo [GH 4465]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-202">[WSL2] Fix for Windows interop when using su / sudo [GH 4465]</span></span>

## <a name="build-18980"></a><span data-ttu-id="1a9f1-203">Build 18980</span><span class="sxs-lookup"><span data-stu-id="1a9f1-203">Build 18980</span></span>
<span data-ttu-id="1a9f1-204">Para obter informações gerais do Windows sobre o Build 18980, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/09/11/announcing-windows-10-insider-preview-build-18980/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-204">For general Windows information on build 18980 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/09/11/announcing-windows-10-insider-preview-build-18980/).</span></span>

* <span data-ttu-id="1a9f1-205">Correção da leitura de symlinks que negam FILE_READ_DATA.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-205">Fix reading symlinks that deny FILE_READ_DATA.</span></span> <span data-ttu-id="1a9f1-206">Isso inclui todas as symlinks que o Windows cria para compatibilidade com versões anteriores, tais como "C:\Documentos e Configurações" e diversos symlinks no diretório de perfil do usuário</span><span class="sxs-lookup"><span data-stu-id="1a9f1-206">This includes all the symlinks Windows creates for backwards compatibility such as "C:\Document and Settings" and a bunch of symlinks in the user profile directory</span></span>
* <span data-ttu-id="1a9f1-207">Transformação do estado de sistema de arquivos inesperado em não fatal [GH 4334, 4305]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-207">Make unexpected filesystem state non-fatal [GH 4334, 4305]</span></span>
* <span data-ttu-id="1a9f1-208">[WSL2] Adição de suporte para arm64 se a CPU/firmware der suporte à virtualização</span><span class="sxs-lookup"><span data-stu-id="1a9f1-208">[WSL2] Add support for arm64 if your CPU / firmware supports virtualization</span></span>
* <span data-ttu-id="1a9f1-209">[WSL2] Permissão para que usuários sem privilégios exibam o log do kernel</span><span class="sxs-lookup"><span data-stu-id="1a9f1-209">[WSL2] Allow unprivileged users to view kernel log</span></span>
* <span data-ttu-id="1a9f1-210">[WSL2] Correção da retransmissão de saída quando os soquetes stdout/stderr tiverem sido fechados [GH 4375]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-210">[WSL2] Fix output relay when stdout / stderr sockets have been closed [GH 4375]</span></span>
* <span data-ttu-id="1a9f1-211">[WSL2] Suporte para passagem de bateria e adaptador AC</span><span class="sxs-lookup"><span data-stu-id="1a9f1-211">[WSL2] Support battery and AC adapter passthrough</span></span>
* <span data-ttu-id="1a9f1-212">[WSL2] Atualização do kernel do Linux para 4.19.67</span><span class="sxs-lookup"><span data-stu-id="1a9f1-212">[WSL2] Update Linux kernel to 4.19.67</span></span>
* <span data-ttu-id="1a9f1-213">Adição da capacidade de definir o nome de usuário padrão em /etc/wsl.conf:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-213">Add the ability to set default username in /etc/wsl.conf:</span></span>
```
[user]
default=<string>
```

## <a name="build-18975"></a><span data-ttu-id="1a9f1-214">Build 18975</span><span class="sxs-lookup"><span data-stu-id="1a9f1-214">Build 18975</span></span>
<span data-ttu-id="1a9f1-215">Para obter informações gerais do Windows sobre o Build 18975, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/09/06/announcing-windows-10-insider-preview-build-18975/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-215">For general Windows information on build 18975 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/09/06/announcing-windows-10-insider-preview-build-18975/).</span></span>

* <span data-ttu-id="1a9f1-216">[WSL2] Corrigidos diversos problemas de confiabilidade do localhost [GH 4340]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-216">[WSL2] Fixed a number of localhost reliability issues [GH 4340]</span></span>

## <a name="build-18970"></a><span data-ttu-id="1a9f1-217">Build 18970</span><span class="sxs-lookup"><span data-stu-id="1a9f1-217">Build 18970</span></span>
<span data-ttu-id="1a9f1-218">Para obter informações gerais do Windows sobre o Build 18970, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/08/29/announcing-windows-10-insider-preview-build-18970/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-218">For general Windows information on build 18970 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/08/29/announcing-windows-10-insider-preview-build-18970/).</span></span>

* <span data-ttu-id="1a9f1-219">[WSL2] Sincronização da hora com a hora do host quando o sistema é retomado do estado de suspensão [GH 4245]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-219">[WSL2] Sync time with host time when system resumes from sleep state [GH 4245]</span></span>
* <span data-ttu-id="1a9f1-220">[WSL2] Criar symlinks NT nos volumes do Windows quando possível.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-220">[WSL2] Create NT symlinks on the Windows volumes when possible.</span></span>
* <span data-ttu-id="1a9f1-221">[WSL2] Criação de distribuições nos namespaces UTS, IPC, PID e Mount.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-221">[WSL2] Create distros in UTS, IPC, PID, and Mount namespaces.</span></span>
* <span data-ttu-id="1a9f1-222">[WSL2] Correção da retransmissão de porta localhost quando o servidor se associar ao localhost diretamente [GH 4353]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-222">[WSL2] Fix localhost port relay when server binds to localhost directly [GH 4353]</span></span>
* <span data-ttu-id="1a9f1-223">[WSL2] Correção da interop quando a saída for redirecionada [GH 4337]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-223">[WSL2] Fix interop when output is redirected [GH 4337]</span></span>
* <span data-ttu-id="1a9f1-224">[WSL2] Suporte à conversão de symlinks NT absolutos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-224">[WSL2] Support translating absolute NT symlinks.</span></span>
* <span data-ttu-id="1a9f1-225">[WSL2] Atualização do kernel para 4.19.59</span><span class="sxs-lookup"><span data-stu-id="1a9f1-225">[WSL2] Update kernel to 4.19.59</span></span>
* <span data-ttu-id="1a9f1-226">[WSL2] Definição correta da máscara de sub-rede para eth0.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-226">[WSL2] Properly set subnet mask for eth0.</span></span>
* <span data-ttu-id="1a9f1-227">[WSL2] Alteração da lógica para interromper o loop de trabalho do console quando o evento de saída for sinalizado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-227">[WSL2] Change logic to break out of console worker loop when exit event is signaled.</span></span>
* <span data-ttu-id="1a9f1-228">[WSL2] Ejeção do vhd da distribuição quando a distribuição não está em execução.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-228">[WSL2] Eject distribution vhd when the distro is not running.</span></span>
* <span data-ttu-id="1a9f1-229">[WSL2] Correção da biblioteca de análise de configuração para manipular corretamente valores vazios.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-229">[WSL2] Fix config parsing library to correctly handle empty values.</span></span>
* <span data-ttu-id="1a9f1-230">[WSL2] Dar suporte ao Docker Desktop criando montagens para múltiplas distribuições.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-230">[WSL2] Support Docker Desktop by creating cross distro mounts.</span></span> <span data-ttu-id="1a9f1-231">Uma distribuição pode optar por adotar esse comportamento ao adicionar a linha a seguir ao arquivo /etc/wsl.conf:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-231">A distro can opt-in to this behavior by adding the following line to the /etc/wsl.conf file:</span></span>
```
[automount]
crossDistro = true
```

## <a name="build-18945"></a><span data-ttu-id="1a9f1-232">Build 18945</span><span class="sxs-lookup"><span data-stu-id="1a9f1-232">Build 18945</span></span>
<span data-ttu-id="1a9f1-233">Para obter informações gerais do Windows sobre o Build 18945, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/07/26/announcing-windows-10-insider-preview-build-18945/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-233">For general Windows information on build 18945 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/07/26/announcing-windows-10-insider-preview-build-18945/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-234">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-234">WSL</span></span>
* <span data-ttu-id="1a9f1-235">[WSL2] Permissão para que soquetes TCP de escuta em WSL2 sejam acessíveis do host usando localhost:port</span><span class="sxs-lookup"><span data-stu-id="1a9f1-235">[WSL2] Allow listening tcp sockets in WSL2 to be accessible from the host by using localhost:port</span></span>
* <span data-ttu-id="1a9f1-236">[WSL2] Correções para falhas de instalação/conversão e diagnóstico adicional para rastrear problemas futuros [GH 4105]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-236">[WSL2] Fixes for install / conversion failures and additional diagnostics to track down future issues [GH 4105]</span></span> 
* <span data-ttu-id="1a9f1-237">[WSL2] Melhoria da capacidade de diagnóstico de problemas de rede WSL2</span><span class="sxs-lookup"><span data-stu-id="1a9f1-237">[WSL2] Improve diagnosability of WSL2 network issues</span></span>
* <span data-ttu-id="1a9f1-238">[WSL2] Atualização da versão do kernel para 4.19.55</span><span class="sxs-lookup"><span data-stu-id="1a9f1-238">[WSL2] Update kernel version to 4.19.55</span></span>
* <span data-ttu-id="1a9f1-239">[WSL2] Atualização do kernel com as opções de configuração necessárias para o Docker [GH 4165]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-239">[WSL2] Update kernel with config options required for docker [GH 4165]</span></span>
* <span data-ttu-id="1a9f1-240">[WSL2] Aumento do número de CPUs atribuídas à VM do utilitário leve para que seja o mesmo do host (anteriormente limitado em 8 por CONFIG_NR_CPUS na configuração do kernel) [GH 4137]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-240">[WSL2] Increase the number of CPUs assigned to the lightweight utility VM to be the same as the host (was previously capped at 8 by CONFIG_NR_CPUS in the kernel config) [GH 4137]</span></span>
* <span data-ttu-id="1a9f1-241">[WSL2] Criação de um arquivo de permuta para a VM leve do WSL2</span><span class="sxs-lookup"><span data-stu-id="1a9f1-241">[WSL2] Create a swap file for the WSL2 lightweight VM</span></span>
* <span data-ttu-id="1a9f1-242">[WSL2] Permissão para que as montagens de usuário fiquem visíveis por meio de \\\\wsl$\\distro (por exemplo, sshfs) [GH 4172]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-242">[WSL2] Allow user mounts to be visible via \\\\wsl$\\distro (for example sshfs) [GH 4172]</span></span>
* <span data-ttu-id="1a9f1-243">[WSL2] Melhoria do desempenho do sistema de arquivos 9p</span><span class="sxs-lookup"><span data-stu-id="1a9f1-243">[WSL2] Improve 9p filesystem performance</span></span>
* <span data-ttu-id="1a9f1-244">[WSL2] Garantia de que a ACL do VHD não aumente sem limite [GH 4126]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-244">[WSL2] Ensure vhd ACL does not grow unbounded [GH 4126]</span></span>
* <span data-ttu-id="1a9f1-245">[WSL2] Atualização da configuração do kernel para dar suporte a squashfs e xt_conntrack [GH 4107, 4123]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-245">[WSL2] Update kernel config to support squashfs and xt_conntrack [GH 4107, 4123]</span></span>
* <span data-ttu-id="1a9f1-246">[WSL2] Correção para a opção interop.enabled /etc/wsl.conf [GH 4140]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-246">[WSL2] Fix for interop.enabled /etc/wsl.conf option [GH 4140]</span></span>
* <span data-ttu-id="1a9f1-247">[WSL2] Retorno de ENOTSUP se o sistema de arquivos não der suporte a EAs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-247">[WSL2] Return ENOTSUP if the file system does not support EAs</span></span>
* <span data-ttu-id="1a9f1-248">[WSL2] Correção do travamento de CopyFile com \\\\wsl$</span><span class="sxs-lookup"><span data-stu-id="1a9f1-248">[WSL2] Fix CopyFile hang with \\\\wsl$</span></span>
* <span data-ttu-id="1a9f1-249">Alternância do umask padrão para 0022 e adição da configuração filesystem.umask a /etc/wsl.conf</span><span class="sxs-lookup"><span data-stu-id="1a9f1-249">Switch default umask to 0022 and add filesystem.umask setting to /etc/wsl.conf</span></span>
* <span data-ttu-id="1a9f1-250">Correção de wslpath para resolver symlinks adequadamente, isso foi regredido em 19h1 [GH 4078]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-250">Fix wslpath to properly resolve symlinks, this was regressed in 19h1 [GH 4078]</span></span>
* <span data-ttu-id="1a9f1-251">Introdução do arquivo %UserProfile%\\.wslconfig para ajuste de configurações WSL2</span><span class="sxs-lookup"><span data-stu-id="1a9f1-251">Introduce %UserProfile%\\.wslconfig file for tweaking WSL2 settings</span></span>
```
[wsl2]
kernel=<path>              # An absolute Windows path to a custom Linux kernel.
memory=<size>              # How much memory to assign to the WSL2 VM.
processors=<number>        # How many processors to assign to the WSL2 VM.
swap=<size>                # How much swap space to add to the WSL2 VM. 0 for no swap file.
swapFile=<path>            # An absolute Windows path to the swap vhd.
localhostForwarding=<bool> # Boolean specifying if ports bound to wildcard or localhost in the WSL2 VM should be connectable from the host via localhost:port (default true).

# <path> entries must be absolute Windows paths with escaped backslashes, for example C:\\Users\\Ben\\kernel
# <size> entries must be size followed by unit, for example 8GB or 512MB
```

## <a name="build-18917"></a><span data-ttu-id="1a9f1-252">Build 18917</span><span class="sxs-lookup"><span data-stu-id="1a9f1-252">Build 18917</span></span>
<span data-ttu-id="1a9f1-253">Para obter informações gerais do Windows sobre o Build 18917, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/06/12/announcing-windows-10-insider-preview-build-18917/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-253">For general Windows information on build 18917 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/06/12/announcing-windows-10-insider-preview-build-18917/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-254">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-254">WSL</span></span>
* <span data-ttu-id="1a9f1-255">O WSL 2 já está disponível.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-255">WSL 2 is now available!</span></span> <span data-ttu-id="1a9f1-256">Confira o [blog](https://devblogs.microsoft.com/commandline/wsl-2-is-now-available-in-windows-insiders/) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-256">Please see [blog](https://devblogs.microsoft.com/commandline/wsl-2-is-now-available-in-windows-insiders/) for more details.</span></span>
* <span data-ttu-id="1a9f1-257">Correção de uma regressão em que a inicialização de processos do Windows via symlinks não funcionou corretamente [GH 3999]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-257">Fix a regression where launching Windows processes via symlinks did not work correctly [GH 3999]</span></span>
* <span data-ttu-id="1a9f1-258">Adição das opções wsl.exe --list --verbose, wsl.exe --list --quiet e wsl.exe --import --version a wsl.exe</span><span class="sxs-lookup"><span data-stu-id="1a9f1-258">Add wsl.exe --list --verbose, wsl.exe --list --quiet, and wsl.exe --import --version options to wsl.exe</span></span>
* <span data-ttu-id="1a9f1-259">Adição da opção wsl.exe --shutdown</span><span class="sxs-lookup"><span data-stu-id="1a9f1-259">Add wsl.exe --shutdown option</span></span>
* <span data-ttu-id="1a9f1-260">Plano 9: Permissão para que a abertura de um diretório para gravação seja realizada com sucesso</span><span class="sxs-lookup"><span data-stu-id="1a9f1-260">Plan 9: Allow opening a directory for write to succeed</span></span>

## <a name="build-18890"></a><span data-ttu-id="1a9f1-261">Build 18890</span><span class="sxs-lookup"><span data-stu-id="1a9f1-261">Build 18890</span></span>
<span data-ttu-id="1a9f1-262">Para obter informações gerais do Windows sobre o Build 18890, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/05/01/announcing-windows-10-insider-preview-build-18890/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-262">For general Windows information on build 18890 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/05/01/announcing-windows-10-insider-preview-build-18890/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-263">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-263">WSL</span></span>
* <span data-ttu-id="1a9f1-264">Vazamento de soquete sem bloqueio [GH 2913]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-264">Non-blocking socket leak [GH 2913]</span></span>
* <span data-ttu-id="1a9f1-265">A entrada de EOF para o terminal pode bloquear leituras subsequentes [GH 3421]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-265">EOF input to terminal can block subsequent reads [GH 3421]</span></span>
* <span data-ttu-id="1a9f1-266">Atualização do cabeçalho de resolv.conf para fazer referência a wsl.conf [discutido no GH 3928]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-266">Update resolv.conf header to refer to wsl.conf [discussed in GH 3928]</span></span>
* <span data-ttu-id="1a9f1-267">Deadlock no código de exclusão de epoll [GH 3922]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-267">Deadlock in epoll delete code [GH 3922]</span></span>
* <span data-ttu-id="1a9f1-268">Manipulação de espaços em argumentos para --import e –export [GH 3932]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-268">Handle spaces in arguments to --import and –export [GH 3932]</span></span>
* <span data-ttu-id="1a9f1-269">A extensão de arquivos mmap não funciona corretamente [GH 3939]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-269">Extending mmap'd files does not work properly [GH 3939]</span></span>
* <span data-ttu-id="1a9f1-270">Correção do problema de o acesso ao ARM64 \\\\wsl$ não estar funcionando corretamente</span><span class="sxs-lookup"><span data-stu-id="1a9f1-270">Fix issue with ARM64 \\\\wsl$ access not working properly</span></span>
* <span data-ttu-id="1a9f1-271">Adição de um ícone padrão melhor para wsl.exe</span><span class="sxs-lookup"><span data-stu-id="1a9f1-271">Add better default icon for wsl.exe</span></span>

## <a name="build-18342"></a><span data-ttu-id="1a9f1-272">Build 18342</span><span class="sxs-lookup"><span data-stu-id="1a9f1-272">Build 18342</span></span>
<span data-ttu-id="1a9f1-273">Para obter informações gerais do Windows sobre o Build 18342, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/02/20/announcing-windows-10-insider-preview-build-18342/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-273">For general Windows information on build 18342 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/02/20/announcing-windows-10-insider-preview-build-18342/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-274">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-274">WSL</span></span>
* <span data-ttu-id="1a9f1-275">Adicionamos a capacidade para os usuários acessarem arquivos do Linux em uma distribuição WSL do Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-275">We've added the ability for users to access Linux files in a WSL distro from Windows.</span></span> <span data-ttu-id="1a9f1-276">Esses arquivos podem ser acessados por meio da linha de comando e aplicativos do Windows (tais como Explorador de Arquivos, VSCode, etc.) também podem interagir com eles.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-276">These files can be accessed through the command line, and also Windows apps, like file explorer, VSCode, etc. can interact with these files.</span></span> <span data-ttu-id="1a9f1-277">Acesse seus arquivos navegando até \\\\wsl$\\<nome_da_distro> ou consulte uma lista de distribuições em execução navegando até \\\\wsl$</span><span class="sxs-lookup"><span data-stu-id="1a9f1-277">Access your files by navigating to \\\\wsl$\\<distro_name>, or see a list of running distributions by navigating to \\\\wsl$</span></span>
* <span data-ttu-id="1a9f1-278">Adição de marcas de informações de CPU adicionais e correção dos valores de Cpus_allowed[_list] [GH 2234]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-278">Add additional CPU info tags and fix Cpus_allowed[_list] values [GH 2234]</span></span>
* <span data-ttu-id="1a9f1-279">Suporte a exec de thread não líder [GH 3800]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-279">Support exec from non-leader thread [GH 3800]</span></span>
* <span data-ttu-id="1a9f1-280">Tratamento de falhas de atualização de configuração como não fatais [GH 3785]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-280">Treat configuration update failures as non-fatal [GH 3785]</span></span>
* <span data-ttu-id="1a9f1-281">Atualização de binfmt para lidar com deslocamentos adequadamente [GH 3768]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-281">Update binfmt to properly handle offsets [GH 3768]</span></span>
* <span data-ttu-id="1a9f1-282">Habilitação do mapeamento de unidades de rede para o Plano 9 [GH 3854]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-282">Enable mapping network drives for Plan 9 [GH 3854]</span></span>
* <span data-ttu-id="1a9f1-283">Suporte à conversão de caminhos Windows -> Linux e Linux -> Windows para montagens de associação</span><span class="sxs-lookup"><span data-stu-id="1a9f1-283">Support Windows -> Linux and Linux -> Windows path translation for bind mounts</span></span>
* <span data-ttu-id="1a9f1-284">Criação de seções somente leitura para mapeamentos em arquivos abertos como somente leitura</span><span class="sxs-lookup"><span data-stu-id="1a9f1-284">Create read-only sections for mappings on files opened read-only</span></span>

## <a name="build-18334"></a><span data-ttu-id="1a9f1-285">Build 18334</span><span class="sxs-lookup"><span data-stu-id="1a9f1-285">Build 18334</span></span>
<span data-ttu-id="1a9f1-286">Para obter informações gerais do Windows sobre o Build 18334, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/02/08/announcing-windows-10-insider-preview-build-18334/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-286">For general Windows information on build 18334 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2019/02/08/announcing-windows-10-insider-preview-build-18334/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-287">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-287">WSL</span></span>
* <span data-ttu-id="1a9f1-288">Recriação da maneira como o fuso horário do Windows é mapeado para um fuso horário do Linux [GH 3747]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-288">Redesign the way that Windows time zone is mapped to a  Linux time zone [GH 3747]</span></span>
* <span data-ttu-id="1a9f1-289">Correção de vazamentos de memória e adição de novas funções de conversão de cadeia de caracteres [GH 3746]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-289">Fix memory leaks and add new string translation functions [GH 3746]</span></span>
* <span data-ttu-id="1a9f1-290">SIGCONT em um grupo de threads sem threads é um não operacional [GH 3741]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-290">SIGCONT on a threadgroup with no threads is a no-op [GH 3741]</span></span> 
* <span data-ttu-id="1a9f1-291">Exibição correta dos descritores de arquivo de epoll e de soquete em /proc/self/fd</span><span class="sxs-lookup"><span data-stu-id="1a9f1-291">Correctly display socket and epoll file descriptors in /proc/self/fd</span></span>

## <a name="build-18305"></a><span data-ttu-id="1a9f1-292">Build 18305</span><span class="sxs-lookup"><span data-stu-id="1a9f1-292">Build 18305</span></span>
<span data-ttu-id="1a9f1-293">Para obter informações gerais do Windows sobre o Build 18305, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/12/19/announcing-windows-10-insider-preview-build-18305/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-293">For general Windows information on build 18305 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2018/12/19/announcing-windows-10-insider-preview-build-18305/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-294">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-294">WSL</span></span>
* <span data-ttu-id="1a9f1-295">pthreads perdem o acesso a arquivos quando o thread primário sai [GH 3589]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-295">pthreads lose access to files when the primary thread exits [GH 3589]</span></span>
* <span data-ttu-id="1a9f1-296">TIOCSCTTY deve ignorar o parâmetro "force", a menos que ele seja necessário [GH 3652]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-296">TIOCSCTTY should ignore the "force" parameter unless it is required [GH 3652]</span></span>
* <span data-ttu-id="1a9f1-297">Melhorias na linha de comando do wsl.exe e adição de funcionalidade de importação/exportação.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-297">wsl.exe command line improvements and addition of import / export functionality.</span></span>
```
Usage: wsl.exe [Argument] [Options...] [CommandLine]

Arguments to run Linux binaries:

    If no command line is provided, wsl.exe launches the default shell.

    --exec, -e <CommandLine>
        Execute the specified command without using the default Linux shell.

    --
        Pass the remaining command line as is.

Options:
    --distribution, -d <DistributionName>
        Run the specified distribution.

    --user, -u <UserName>
        Run as the specified user.

Arguments to manage Windows Subsystem for Linux:

    --export <DistributionName> <FileName>
        Exports the distribution to a tar file.
        The filename can be - for standard output.

    --import <DistributionName> <InstallLocation> <FileName>
        Imports the specified tar file as a new distribution.
        The filename can be - for standard input.

    --list, -l [Options]
        Lists distributions.

        Options:
            --all
                List all distributions, including distributions that are currently
                being installed or uninstalled.

            --running
                List only distributions that are currently running.

    -setdefault, -s <DistributionName>
        Sets the distribution as the default.

    --terminate, -t <DistributionName>
        Terminates the distribution.

    --unregister <DistributionName>
        Unregisters the distribution.

    --upgrade <DistributionName>
        Upgrades the distribution to the WslFs file system format.

    --help
        Display usage information.
```

## <a name="build-18277"></a><span data-ttu-id="1a9f1-298">Build 18277</span><span class="sxs-lookup"><span data-stu-id="1a9f1-298">Build 18277</span></span>
<span data-ttu-id="1a9f1-299">Para obter informações gerais do Windows sobre o Build 18277, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/11/07/announcing-windows-10-insider-preview-build-18277/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-299">For general Windows information on build 18277 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2018/11/07/announcing-windows-10-insider-preview-build-18277/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-300">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-300">WSL</span></span>
* <span data-ttu-id="1a9f1-301">Correção do erro "essa interface não é compatível" introduzido no build 18272 [GH 3645]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-301">Fix "no such interface supported" error introduced in build 18272 [GH 3645]</span></span>
* <span data-ttu-id="1a9f1-302">O sinalizador MNT_FORCE agora é ignorado para a syscall umount [GH 3605]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-302">Ignore the MNT_FORCE flag for umount syscall [GH 3605]</span></span>
* <span data-ttu-id="1a9f1-303">Alternância da interop de WSL para usar a API CreatePseudoConsole oficial</span><span class="sxs-lookup"><span data-stu-id="1a9f1-303">Switch WSL interop to use the official CreatePseudoConsole API</span></span>
* <span data-ttu-id="1a9f1-304">Nenhum valor de tempo limite mantido quando FUTEX_WAIT reinicializa</span><span class="sxs-lookup"><span data-stu-id="1a9f1-304">Maintain no timeout value when FUTEX_WAIT restarts</span></span>

## <a name="build-18272"></a><span data-ttu-id="1a9f1-305">Build 18272</span><span class="sxs-lookup"><span data-stu-id="1a9f1-305">Build 18272</span></span>
<span data-ttu-id="1a9f1-306">Para obter informações gerais do Windows sobre o Build 18272, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/10/31/announcing-windows-10-insider-preview-build-18272/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-306">For general Windows information on build 18272 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2018/10/31/announcing-windows-10-insider-preview-build-18272/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-307">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-307">WSL</span></span>
* <span data-ttu-id="1a9f1-308">**AVISO:** Há um problema nesse build que torna o WSL inoperante.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-308">**WARNING:** There is an issue in this build that makes WSL inoperable.</span></span> <span data-ttu-id="1a9f1-309">Ao tentar iniciar a distribuição, você verá um erro "Não há suporte para essa interface".</span><span class="sxs-lookup"><span data-stu-id="1a9f1-309">When trying to launch your distribution you will see a "No such interface supported" error.</span></span> <span data-ttu-id="1a9f1-310">O problema foi corrigido e estará no build do Participante do Programa Windows Insider – Modo Rápido da próxima semana.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-310">The issue has been fixed and will be in next week's Insider Fast build.</span></span> <span data-ttu-id="1a9f1-311">Se você tiver instalado esse build, poderá reverter a versão para o build anterior do Windows usando "Voltar para a versão anterior do Windows 10" em Configurações->Atualização e Segurança->Recuperação.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-311">If you've installed this build you can roll back to the previous Windows build using "Go back to the previous version of Windows 10" in Settings->Update & Security->Recovery.</span></span>

## <a name="build-18267"></a><span data-ttu-id="1a9f1-312">Build 18267</span><span class="sxs-lookup"><span data-stu-id="1a9f1-312">Build 18267</span></span>
<span data-ttu-id="1a9f1-313">Para obter informações gerais do Windows sobre o Build 18267, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/10/24/announcing-windows-10-insider-preview-build-18267/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-313">For general Windows information on build 18267 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2018/10/24/announcing-windows-10-insider-preview-build-18267/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-314">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-314">WSL</span></span>
* <span data-ttu-id="1a9f1-315">Correção do problema em que o processo zumbi pode não ser aproveitado e permanecer indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-315">Fix issue where zombie process may not be reaped and remain indefinitely.</span></span>
* <span data-ttu-id="1a9f1-316">WslRegisterDistribution trava se a mensagem de erro excede o comprimento máximo [GH 3592]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-316">WslRegisterDistribution hangs if error message exceeds max length [GH 3592]</span></span>
* <span data-ttu-id="1a9f1-317">Permissão para que o fsync tenha sucesso para arquivos somente leitura no DrvFs [GH 3556]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-317">Allow fsync to succeed for read-only files on DrvFs [GH 3556]</span></span>
* <span data-ttu-id="1a9f1-318">Verificação de que os diretórios /bin e /sbin existem antes de criar symlinks internos [GH 3584]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-318">Ensure that /bin and /sbin directories exist before creating symlinks inside [GH 3584]</span></span>
* <span data-ttu-id="1a9f1-319">Adicionado um mecanismo de tempo limite de encerramento de instância para instâncias de WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-319">Added an instance termination timeout mechanism for WSL instances.</span></span> <span data-ttu-id="1a9f1-320">O tempo limite está definido atualmente como 15 segundos, o que significa que a instância será encerrada 15 segundos após o último processo de WSL sair.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-320">The timeout is currently set to 15 seconds, meaning the instance will terminate 15 seconds after the last WSL process exits.</span></span> <span data-ttu-id="1a9f1-321">Para encerrar uma distribuição imediatamente, use:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-321">To terminate a distribution immediately, use:</span></span>
```
wslconfig.exe /terminate <DistributionName>
```

## <a name="build-17763-1809"></a><span data-ttu-id="1a9f1-322">Build 17763 (1809)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-322">Build 17763 (1809)</span></span>
<span data-ttu-id="1a9f1-323">Para obter informações gerais do Windows sobre o Build 17763, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-323">For general Windows information on build 17763 visit the [Windows blog](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-324">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-324">WSL</span></span>
* <span data-ttu-id="1a9f1-325">Verificação de permissão da syscall setpriority muito estrita para alterar a mesma prioridade de thread [GH 1838]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-325">Setpriority syscall permission check too strict for changing same thread priority [GH 1838]</span></span>
* <span data-ttu-id="1a9f1-326">Verificação de que o tempo de interrupção não polarizado é usado para o tempo de inicialização a fim de evitar retornar valores negativos para clock_gettime (CLOCK_BOOTTIME) [GH 3434]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-326">Ensure that unbiased interrupt time is used for boot time to avoid returning negative values for clock_gettime(CLOCK_BOOTTIME) [GH 3434]</span></span>
* <span data-ttu-id="1a9f1-327">Manipulação de symlinks no interpretador binfmt de WSL [GH 3424]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-327">Handle symlinks in the WSL binfmt interpreter [GH 3424]</span></span>
* <span data-ttu-id="1a9f1-328">Melhor manipulação da limpeza do descritor de arquivo de líder do grupo de threads.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-328">Better handling of threadgroup leader file descriptor cleanup.</span></span>
* <span data-ttu-id="1a9f1-329">Alternância do WSL para usar KeQueryInterruptTimePrecise em vez de KeQueryPerformanceCounter a fim de evitar o estouro [GH 3252]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-329">Switch WSL to use KeQueryInterruptTimePrecise instead of KeQueryPerformanceCounter to avoid overflow [GH 3252]</span></span>
* <span data-ttu-id="1a9f1-330">A anexação ptrace pode causar um valor retornado insatisfatório de chamadas do sistema [GH 1731]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-330">Ptrace attach may cause bad return value from system calls [GH 1731]</span></span>
* <span data-ttu-id="1a9f1-331">Correção de vários problemas relacionados ao AF_UNIX [GH 3371]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-331">Fix several AF_UNIX related issues [GH 3371]</span></span>
* <span data-ttu-id="1a9f1-332">Correção do problema que poderá causar falha de interop de WSL se o diretório de trabalho atual tiver menos de 5 caracteres [GH 3379]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-332">Fix issue that could cause WSL interop to fail if the current working directory is less than 5 characters long [GH 3379]</span></span>
* <span data-ttu-id="1a9f1-333">Impedimento de que um atraso de um segundo cause falhas em conexões de loopback para portas inexistentes [GH 3286]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-333">Avoid one second delay failing loopback connections to non-existent ports [GH 3286]</span></span>
* <span data-ttu-id="1a9f1-334">Adição do arquivo de stub /proc/sys/fs/file-max [GH 2893]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-334">Add /proc/sys/fs/file-max stub file [GH 2893]</span></span>
* <span data-ttu-id="1a9f1-335">Informações de escopo de IPV6 mais precisas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-335">More accurate IPV6 scope information.</span></span>
* <span data-ttu-id="1a9f1-336">Suporte a PR_SET_PTRACER [GH 3053]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-336">PR_SET_PTRACER support [GH 3053]</span></span>
* <span data-ttu-id="1a9f1-337">O sistema de arquivos de pipe limpa inadvertidamente o evento epoll disparado da borda [GH 3276]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-337">Pipe filesystem inadvertently clearing edge-triggered epoll event [GH 3276]</span></span>
* <span data-ttu-id="1a9f1-338">O executável do Win32 iniciado via symlink NTFS não respeita o nome do symlink [GH 2909]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-338">Win32 executable launched via NTFS symlink doesn't respect symlink name [GH 2909]</span></span>
* <span data-ttu-id="1a9f1-339">Suporte a zumbis melhorado [GH 1353]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-339">Improved zombie support [GH 1353]</span></span>
* <span data-ttu-id="1a9f1-340">Adição de entradas wsl.conf para controlar o comportamento de interop do Windows [GH 1493]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-340">Add wsl.conf entries for controlling Windows interop behavior [GH 1493]</span></span>
  ```
    [interop]

    enabled=false # enable launch of Windows binaries; default is true

    appendWindowsPath=false # append Windows path to $PATH variable; default is true
  ```
* <span data-ttu-id="1a9f1-341">Correção para getsockname nem sempre retornando tipo de família de soquetes UNIX [GH 1774]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-341">Fix for getsockname not always returning UNIX socket family type [GH 1774]</span></span>
* <span data-ttu-id="1a9f1-342">Adição de suporte para TIOCSTI [GH 1863]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-342">Add support for TIOCSTI [GH 1863]</span></span>
* <span data-ttu-id="1a9f1-343">Soquetes sem bloqueio no processo de conexão devem retornar EAGAIN para tentativas de gravação [GH 2846]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-343">Non-blocking sockets in the process of connecting should return EAGAIN for write attempts [GH 2846]</span></span>
* <span data-ttu-id="1a9f1-344">Suporte a interop em VHDs montados [GH 3246, 3291]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-344">Support interop on mounted VHDs [GH 3246, 3291]</span></span>
* <span data-ttu-id="1a9f1-345">Correção do problema de verificação de permissão na pasta raiz [GH 3304]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-345">Fix permission checking issue on root folder [GH 3304]</span></span>
* <span data-ttu-id="1a9f1-346">Suporte limitado para os ioctls de teclado TTY KDGKBTYPE, KDGKBMODE e KDSKBMODE.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-346">Limited support for TTY keyboard ioctls KDGKBTYPE, KDGKBMODE and KDSKBMODE.</span></span>
* <span data-ttu-id="1a9f1-347">Os aplicativos da interface do usuário do Windows devem ser executados mesmo quando iniciados em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-347">Windows UI apps should execute even when launched in the background.</span></span>
* <span data-ttu-id="1a9f1-348">Adição da opção wsl-u ou --user [GH 1203]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-348">Add wsl -u or --user option [GH 1203]</span></span>
* <span data-ttu-id="1a9f1-349">Correção de problemas de inicialização do WSL quando a inicialização rápida estiver habilitada [GH 2576]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-349">Fix WSL launch issues when fast startup is enabled [GH 2576]</span></span>
* <span data-ttu-id="1a9f1-350">Os soquetes Unix precisam reter as credenciais de pares desconectados [GH 3183]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-350">Unix sockets need to retain disconnected peer credentials [GH 3183]</span></span>
* <span data-ttu-id="1a9f1-351">Soquetes Unix sem bloqueio falhando indefinidamente com EAGAIN [GH 3191]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-351">Non-blocking Unix sockets failing indefinitely with EAGAIN [GH 3191]</span></span>
* <span data-ttu-id="1a9f1-352">case=off é o novo tipo de montagem de drvfs padrão [GH 2937, 3212, 3328]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-352">case=off is the new default drvfs mount type [GH 2937, 3212, 3328]</span></span>
    * <span data-ttu-id="1a9f1-353">Confira [blog](https://blogs.msdn.microsoft.com/commandline/2018/06/14/improved-per-directory-case-sensitivity-support-in-wsl/) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-353">See [blog](https://blogs.msdn.microsoft.com/commandline/2018/06/14/improved-per-directory-case-sensitivity-support-in-wsl/) for more information.</span></span>
* <span data-ttu-id="1a9f1-354">Adição de wslconfig /terminate para interromper a execução de distribuições.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-354">Add wslconfig /terminate to stop running distributions.</span></span>
* <span data-ttu-id="1a9f1-355">Correção do problema com as entradas do menu de contexto do shell WSL que não manipulam corretamente caminhos com espaços.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-355">Fix issue with the WSL shell context menu entries that do not correctly handle paths with spaces.</span></span>
* <span data-ttu-id="1a9f1-356">Exposição de diferenciação de maiúsculas e minúsculas por diretório como um atributo estendido</span><span class="sxs-lookup"><span data-stu-id="1a9f1-356">Expose per-directory case sensitivity as an extended attribute</span></span>
* <span data-ttu-id="1a9f1-357">ARM64: Emulação de operações de manutenção de cache.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-357">ARM64: Emulate cache maintenance operations.</span></span> <span data-ttu-id="1a9f1-358">Resolução do [problema de dotnet](https://github.com/dotnet/core/issues/1561).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-358">Resolve [dotnet issue](https://github.com/dotnet/core/issues/1561).</span></span>
* <span data-ttu-id="1a9f1-359">DrvFs: apenas caracteres de escape de saída no intervalo privado que correspondem a um caractere de escape.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-359">DrvFs: only unescape characters in the private range that correspond to an escaped character.</span></span>
* <span data-ttu-id="1a9f1-360">Correção do erro OB1 (por um) na validação de tamanho do interpretador ELF [GH 3154]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-360">Fix off-by-one error in ELF parser interpreter length validation [GH 3154]</span></span>
* <span data-ttu-id="1a9f1-361">Timers absolutos do WSL com um tempo no passado não são disparados [GH 3091]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-361">WSL absolute timers with a time in the past do not fire [GH 3091]</span></span>
* <span data-ttu-id="1a9f1-362">Verificação de que os pontos de nova análise criados recentemente estão listados como tal no diretório pai.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-362">Ensure newly created reparse points are listed as such in the parent directory.</span></span>
* <span data-ttu-id="1a9f1-363">Criação de forma atômica de diretórios que diferenciam maiúsculas de minúsculas no DrvFs.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-363">Atomically create case sensitive directories in DrvFs.</span></span>
* <span data-ttu-id="1a9f1-364">Corrigido um problema adicional em que operações multi-threaded poderiam retornar ENOENT mesmo que o arquivo existisse.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-364">Fixed an additional issue where multithreaded operations could return ENOENT even though the file exists.</span></span> <span data-ttu-id="1a9f1-365">[GH 2712]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-365">[GH 2712]</span></span>
* <span data-ttu-id="1a9f1-366">Correção da falha de inicialização do WSL quando o UMCI está habilitado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-366">Fixed WSL launch failure when UMCI is enabled.</span></span> <span data-ttu-id="1a9f1-367">[GH 3020]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-367">[GH 3020]</span></span>
* <span data-ttu-id="1a9f1-368">Adição do menu de contexto do Explorer para iniciar o WSL [GH 437, 603, 1836].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-368">Add explorer context menu to launch WSL [GH 437, 603, 1836].</span></span> <span data-ttu-id="1a9f1-369">Para usá-lo, mantenha a tecla Shift pressionada e clique com o botão direito do mouse quando estiver em uma janela do Explorer.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-369">To use, hold shift and right-click when in an explorer window.</span></span>
* <span data-ttu-id="1a9f1-370">Correção do comportamento de não bloqueio de soquete do Unix [GH 2822, 3100]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-370">Fix Unix socket non-blocking behavior [GH 2822, 3100]</span></span>
* <span data-ttu-id="1a9f1-371">Correção do comando do NetLink suspenso, conforme relatado no GH 2026.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-371">Fix hanging NETLINK command as reported in GH 2026.</span></span>
* <span data-ttu-id="1a9f1-372">Adição de suporte para os sinalizadores de propagação de montagem [GH 2911].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-372">Add support for mount propagation flags [GH 2911].</span></span>
* <span data-ttu-id="1a9f1-373">Correção do problema com truncamento não causando eventos inotify [GH 2978].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-373">Fix issue with truncate not causing inotify events [GH 2978].</span></span>
* <span data-ttu-id="1a9f1-374">Adição da opção --exec para wsl.exe para invocar um único binário sem um shell.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-374">Add --exec option for wsl.exe to invoke a single binary without a shell.</span></span>
* <span data-ttu-id="1a9f1-375">Adição da opção --distribution a wsl.exe para selecionar uma distribuição específica.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-375">Add --distribution option for wsl.exe to select a specific distro.</span></span>
* <span data-ttu-id="1a9f1-376">Suporte limitado para dmesg.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-376">Limited support for dmesg.</span></span> <span data-ttu-id="1a9f1-377">Os aplicativos agora podem fazer logon no dmesg.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-377">Applications can now log to dmesg.</span></span> <span data-ttu-id="1a9f1-378">O driver do WSL registra informações limitadas no dmesg.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-378">WSL driver logs limited information to dmesg.</span></span> <span data-ttu-id="1a9f1-379">No futuro, isso pode ser estendido para transportar outras informações/diagnósticos do driver.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-379">In future, this can be extended to carry other information/diagnostics from the driver.</span></span>
    * <span data-ttu-id="1a9f1-380">Observação: atualmente, o dmesg é compatível por meio da interface do dispositivo `/dev/kmsg`.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-380">Note: dmesg is currently supported through the `/dev/kmsg` device interface.</span></span> <span data-ttu-id="1a9f1-381">A interface syscall `syslog` ainda não é compatível.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-381">`syslog` syscall interface is not yet supported.</span></span> <span data-ttu-id="1a9f1-382">Assim sendo, algumas das opções de linha de comando de `dmesg`, tais como `-S` e `-C`, não funcionam.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-382">And, so, some of the `dmesg` command line options such as `-S`, `-C` don't work.</span></span>
* <span data-ttu-id="1a9f1-383">Alteração do GID e o modo padrão de dispositivos seriais para corresponder ao nativo [GH 3042]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-383">Change default gid and mode of serial devices to match native [GH 3042]</span></span>
* <span data-ttu-id="1a9f1-384">O DrvFs agora dá suporte a atributos estendidos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-384">DrvFs now supports extended attributes.</span></span>
    * <span data-ttu-id="1a9f1-385">Observação: O DrvFs tem algumas limitações sobre o nome dos atributos estendidos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-385">Note: DrvFs has some limitations on the name of extended attributes.</span></span> <span data-ttu-id="1a9f1-386">Alguns caracteres (tais como '/', ': ' e '\*') não são permitidos e os nomes de atributos estendidos não diferenciam maiúsculas de minúsculas em DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-386">Some characters (like '/', ':' and '\*') are not allowed, and extended attribute names are not case sensitive on DrvFs</span></span>

## <a name="build-18252-skip-ahead"></a><span data-ttu-id="1a9f1-387">Build 18252 (ignorar e prosseguir)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-387">Build 18252 (Skip Ahead)</span></span>
<span data-ttu-id="1a9f1-388">Para obter informações gerais do Windows sobre o Build 18252, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/10/03/announcing-windows-10-insider-preview-build-18252/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-388">For general Windows information on build 18252 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/10/03/announcing-windows-10-insider-preview-build-18252/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-389">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-389">WSL</span></span>
* <span data-ttu-id="1a9f1-390">Mover os binários init e bsdtar para fora da dll do lxssmanager e para uma pasta de ferramentas separada</span><span class="sxs-lookup"><span data-stu-id="1a9f1-390">Move init and bsdtar binaries out of lxssmanager dll and into a separate tools folder</span></span>
* <span data-ttu-id="1a9f1-391">Correção da corrida ao fechar o descritor de arquivo ao usar CLONE_FILES</span><span class="sxs-lookup"><span data-stu-id="1a9f1-391">Fix race around closing file descriptor when using CLONE_FILES</span></span>
* <span data-ttu-id="1a9f1-392">Manipulação de campos opcionais em /proc/pid/mountinfo ao converter caminhos do DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-392">Handle optional fields in /proc/pid/mountinfo when translating DrvFs paths</span></span>
* <span data-ttu-id="1a9f1-393">Permissão para que o DrvFs mknod tenha êxito sem suporte de metadados para S_IFREG</span><span class="sxs-lookup"><span data-stu-id="1a9f1-393">Allow DrvFs mknod to succeed without metadata support for S_IFREG</span></span>
* <span data-ttu-id="1a9f1-394">Os arquivos somente leitura criados no DrvFs devem ter o atributo readonly definido [GH 3411]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-394">Readonly files created on DrvFs should have the readonly attribute set [GH 3411]</span></span>
* <span data-ttu-id="1a9f1-395">Adição do auxiliar /sbin/mount.drvfs para lidar com a montagem do DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-395">Add /sbin/mount.drvfs helper to handle DrvFs mounting</span></span>
* <span data-ttu-id="1a9f1-396">Uso da renomeação POSIX no DrvFs.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-396">Use POSIX rename in DrvFs.</span></span>
* <span data-ttu-id="1a9f1-397">Permissão para a conversão de caminho em volumes sem um GUID de volume.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-397">Allow path translation on volumes without a volume GUID.</span></span>

## <a name="build-17738-fast"></a><span data-ttu-id="1a9f1-398">Build 17738 (rápido)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-398">Build 17738 (Fast)</span></span>
<span data-ttu-id="1a9f1-399">Para obter informações gerais do Windows sobre o Build 17738, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/08/14/announcing-windows-10-insider-preview-build-17738/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-399">For general Windows information on build 17738 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/08/14/announcing-windows-10-insider-preview-build-17738/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-400">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-400">WSL</span></span>
* <span data-ttu-id="1a9f1-401">Verificação de permissão da syscall setpriority muito estrita para alterar a mesma prioridade de thread [GH 1838]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-401">Setpriority syscall permission check too strict for changing same thread priority [GH 1838]</span></span>
* <span data-ttu-id="1a9f1-402">Verificação de que o tempo de interrupção não polarizado é usado para o tempo de inicialização a fim de evitar retornar valores negativos para clock_gettime (CLOCK_BOOTTIME) [GH 3434]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-402">Ensure that unbiased interrupt time is used for boot time to avoid returning negative values for clock_gettime(CLOCK_BOOTTIME) [GH 3434]</span></span>
* <span data-ttu-id="1a9f1-403">Manipulação de symlinks no interpretador binfmt de WSL [GH 3424]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-403">Handle symlinks in the WSL binfmt interpreter [GH 3424]</span></span>
* <span data-ttu-id="1a9f1-404">Melhor manipulação da limpeza do descritor de arquivo de líder do grupo de threads.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-404">Better handling of threadgroup leader file descriptor cleanup.</span></span>

## <a name="build-17728-fast"></a><span data-ttu-id="1a9f1-405">Build 17728 (rápido)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-405">Build 17728 (Fast)</span></span>
<span data-ttu-id="1a9f1-406">Para obter informações gerais do Windows sobre o Build 17728, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/07/31/announcing-windows-10-insider-preview-build-17728/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-406">For general Windows information on build 17728 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/07/31/announcing-windows-10-insider-preview-build-17728/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-407">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-407">WSL</span></span>
* <span data-ttu-id="1a9f1-408">Alternância do WSL para usar KeQueryInterruptTimePrecise em vez de KeQueryPerformanceCounter a fim de evitar o estouro [GH 3252]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-408">Switch WSL to use KeQueryInterruptTimePrecise instead of KeQueryPerformanceCounter to avoid overflow [GH 3252]</span></span>
* <span data-ttu-id="1a9f1-409">A anexação ptrace pode causar um valor retornado insatisfatório de chamadas do sistema [GH 1731]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-409">Ptrace attach may cause bad return value from system calls [GH 1731]</span></span>
* <span data-ttu-id="1a9f1-410">Correção de vários problemas relacionados ao AF_UNIX [GH 3371]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-410">Fix a number of AF_UNIX related issues [GH 3371]</span></span>
* <span data-ttu-id="1a9f1-411">Correção do problema que poderá causar falha de interop de WSL se o diretório de trabalho atual tiver menos de 5 caracteres [GH 3379]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-411">Fix issue that could cause WSL interop to fail if the current working directory is less than 5 characters long [GH 3379]</span></span>

## <a name="build-18204-skip-ahead"></a><span data-ttu-id="1a9f1-412">Build 18204 (ignorar e prosseguir)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-412">Build 18204 (Skip Ahead)</span></span>
<span data-ttu-id="1a9f1-413">Para obter informações gerais do Windows sobre o Build 18204, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/07/25/announcing-windows-10-insider-preview-build-17723-and-build-18204/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-413">For general Windows information on build 18204 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/07/25/announcing-windows-10-insider-preview-build-17723-and-build-18204/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-414">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-414">WSL</span></span>
* <span data-ttu-id="1a9f1-415">O sistema de arquivos de pipe limpa inadvertidamente o evento epoll disparado da borda [GH 3276]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-415">Pipe filesystem inadvertenly clearing edge-triggered epoll event [GH 3276]</span></span>
* <span data-ttu-id="1a9f1-416">O executável do Win32 iniciado via symlink NTFS não respeita o nome do symlink [GH 2909]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-416">Win32 executable launched via NTFS symlink doesn't respect symlink name [GH 2909]</span></span>

## <a name="build-17723-fast"></a><span data-ttu-id="1a9f1-417">Build 17723 (rápido)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-417">Build 17723 (Fast)</span></span>
<span data-ttu-id="1a9f1-418">Para obter informações gerais do Windows sobre o Build 17723, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/07/25/announcing-windows-10-insider-preview-build-17723-and-build-18204/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-418">For general Windows information on build 17723 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/07/25/announcing-windows-10-insider-preview-build-17723-and-build-18204/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-419">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-419">WSL</span></span>
* <span data-ttu-id="1a9f1-420">Impedimento de que um atraso de um segundo cause falhas em conexões de loopback para portas inexistentes [GH 3286]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-420">Avoid one second delay failing loopback connections to non-existent ports [GH 3286]</span></span>
* <span data-ttu-id="1a9f1-421">Adição do arquivo de stub /proc/sys/fs/file-max [GH 2893]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-421">Add /proc/sys/fs/file-max stub file [GH 2893]</span></span>
* <span data-ttu-id="1a9f1-422">Informações de escopo de IPV6 mais precisas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-422">More accurate IPV6 scope information.</span></span>
* <span data-ttu-id="1a9f1-423">Suporte a PR_SET_PTRACER [GH 3053]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-423">PR_SET_PTRACER support [GH 3053]</span></span>
* <span data-ttu-id="1a9f1-424">O sistema de arquivos de pipe limpa inadvertidamente o evento epoll disparado da borda [GH 3276]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-424">Pipe filesystem inadvertenly clearing edge-triggered epoll event [GH 3276]</span></span>
* <span data-ttu-id="1a9f1-425">O executável do Win32 iniciado via symlink NTFS não respeita o nome do symlink [GH 2909]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-425">Win32 executable launched via NTFS symlink doesn't respect symlink name [GH 2909]</span></span>

## <a name="build-17713"></a><span data-ttu-id="1a9f1-426">Build 17713</span><span class="sxs-lookup"><span data-stu-id="1a9f1-426">Build 17713</span></span>
<span data-ttu-id="1a9f1-427">Para obter informações gerais do Windows sobre o Build 17713, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/07/11/announcing-windows-10-insider-preview-build-17713/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-427">For general Windows information on build 17713 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/07/11/announcing-windows-10-insider-preview-build-17713/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-428">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-428">WSL</span></span>
* <span data-ttu-id="1a9f1-429">Suporte a zumbis melhorado [GH 1353]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-429">Improved zombie support [GH 1353]</span></span>
* <span data-ttu-id="1a9f1-430">Adição de entradas wsl.conf para controlar o comportamento de interop do Windows [GH 1493]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-430">Add wsl.conf entries for controlling Windows interop behavior [GH 1493]</span></span>
  ```
    [interop]

    enabled=false # enable launch of Windows binaries; default is true

    appendWindowsPath=false # append Windows path to $PATH variable; default is true
  ```
* <span data-ttu-id="1a9f1-431">Correção para getsockname nem sempre retornando tipo de família de soquetes UNIX [GH 1774]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-431">Fix for getsockname not always returning UNIX socket family type [GH 1774]</span></span>
* <span data-ttu-id="1a9f1-432">Adição de suporte para TIOCSTI [GH 1863]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-432">Add support for TIOCSTI [GH 1863]</span></span>
* <span data-ttu-id="1a9f1-433">Soquetes sem bloqueio no processo de conexão devem retornar EAGAIN para tentativas de gravação [GH 2846]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-433">Non-blocking sockets in the process of connecting should return EAGAIN for write attempts [GH 2846]</span></span>
* <span data-ttu-id="1a9f1-434">Suporte a interop em VHDs montados [GH 3246, 3291]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-434">Support interop on mounted VHDs [GH 3246, 3291]</span></span>
* <span data-ttu-id="1a9f1-435">Correção do problema de verificação de permissão na pasta raiz [GH 3304]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-435">Fix permission checking issue on root folder [GH 3304]</span></span>
* <span data-ttu-id="1a9f1-436">Suporte limitado para os ioctls de teclado TTY KDGKBTYPE, KDGKBMODE e KDSKBMODE.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-436">Limited support for TTY keyboard ioctls KDGKBTYPE, KDGKBMODE and KDSKBMODE.</span></span>
* <span data-ttu-id="1a9f1-437">Os aplicativos da interface do usuário do Windows devem ser executados mesmo quando iniciados em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-437">Windows UI apps should execute even when launched in the background.</span></span>

## <a name="build-17704"></a><span data-ttu-id="1a9f1-438">Build 17704</span><span class="sxs-lookup"><span data-stu-id="1a9f1-438">Build 17704</span></span>
<span data-ttu-id="1a9f1-439">Para obter informações gerais do Windows sobre o Build 17704, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/06/27/announcing-windows-10-insider-preview-build-17704/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-439">For general Windows information on build 17704 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/06/27/announcing-windows-10-insider-preview-build-17704/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-440">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-440">WSL</span></span>
* <span data-ttu-id="1a9f1-441">Adição da opção wsl-u ou --user [GH 1203]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-441">Add wsl -u or --user option [GH 1203]</span></span>
* <span data-ttu-id="1a9f1-442">Correção de problemas de inicialização do WSL quando a inicialização rápida estiver habilitada [GH 2576]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-442">Fix WSL launch issues when fast startup is enabled [GH 2576]</span></span>
* <span data-ttu-id="1a9f1-443">Os soquetes Unix precisam reter as credenciais de pares desconectados [GH 3183]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-443">Unix sockets need to retain disconnected peer credentials [GH 3183]</span></span>
* <span data-ttu-id="1a9f1-444">Soquetes Unix sem bloqueio falhando indefinidamente com EAGAIN [GH 3191]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-444">Non-blocking Unix sockets failing indefinitely with EAGAIN [GH 3191]</span></span>
* <span data-ttu-id="1a9f1-445">case=off é o novo tipo de montagem de drvfs padrão [GH 2937, 3212, 3328]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-445">case=off is the new default drvfs mount type [GH 2937, 3212, 3328]</span></span>
    * <span data-ttu-id="1a9f1-446">Confira [blog](https://blogs.msdn.microsoft.com/commandline/2018/06/14/improved-per-directory-case-sensitivity-support-in-wsl/) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-446">See [blog](https://blogs.msdn.microsoft.com/commandline/2018/06/14/improved-per-directory-case-sensitivity-support-in-wsl/) for more information.</span></span>
* <span data-ttu-id="1a9f1-447">Adição de wslconfig /terminate para interromper a execução de distribuições.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-447">Add wslconfig /terminate to stop running distributions.</span></span>

## <a name="build-17692"></a><span data-ttu-id="1a9f1-448">Build 17692</span><span class="sxs-lookup"><span data-stu-id="1a9f1-448">Build 17692</span></span>
<span data-ttu-id="1a9f1-449">Para obter informações gerais do Windows sobre o Build 17692, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/06/14/announcing-windows-10-insider-preview-build-17692).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-449">For general Windows information on build 17692 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/06/14/announcing-windows-10-insider-preview-build-17692).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-450">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-450">WSL</span></span>
* <span data-ttu-id="1a9f1-451">Correção do problema com as entradas do menu de contexto do shell WSL que não manipulam corretamente caminhos com espaços.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-451">Fix issue with the WSL shell context menu entries that do not correctly handle paths with spaces.</span></span>
* <span data-ttu-id="1a9f1-452">Exposição de diferenciação de maiúsculas e minúsculas por diretório como um atributo estendido</span><span class="sxs-lookup"><span data-stu-id="1a9f1-452">Expose per-directory case sensitivity as an extended attribute</span></span>
* <span data-ttu-id="1a9f1-453">ARM64: Emulação de operações de manutenção de cache.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-453">ARM64: Emulate cache maintenance operations.</span></span> <span data-ttu-id="1a9f1-454">Resolução do [problema de dotnet](https://github.com/dotnet/core/issues/1561).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-454">Resolve [dotnet issue](https://github.com/dotnet/core/issues/1561).</span></span>
* <span data-ttu-id="1a9f1-455">DrvFs: apenas caracteres de escape de saída no intervalo privado que correspondem a um caractere de escape.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-455">DrvFs: only unescape characters in the private range that correspond to an escaped character.</span></span>

## <a name="build-17686"></a><span data-ttu-id="1a9f1-456">Build 17686</span><span class="sxs-lookup"><span data-stu-id="1a9f1-456">Build 17686</span></span>
<span data-ttu-id="1a9f1-457">Para obter informações gerais do Windows sobre o Build 17686, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/06/06/announcing-windows-10-insider-preview-build-17686).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-457">For general Windows information on build 17686 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/06/06/announcing-windows-10-insider-preview-build-17686).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-458">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-458">WSL</span></span>
* <span data-ttu-id="1a9f1-459">Correção do erro OB1 (por um) na validação de tamanho do interpretador ELF [GH 3154]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-459">Fix off-by-one error in ELF parser interpreter length validation [GH 3154]</span></span>
* <span data-ttu-id="1a9f1-460">Timers absolutos do WSL com um tempo no passado não são disparados [GH 3091]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-460">WSL absolute timers with a time in the past do not fire [GH 3091]</span></span>
* <span data-ttu-id="1a9f1-461">Verificação de que os pontos de nova análise criados recentemente estão listados como tal no diretório pai.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-461">Ensure newly created reparse points are listed as such in the parent directory.</span></span>
* <span data-ttu-id="1a9f1-462">Criação de forma atômica de diretórios que diferenciam maiúsculas de minúsculas no DrvFs.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-462">Atomically create case sensitive directories in DrvFs.</span></span>

## <a name="build-17677"></a><span data-ttu-id="1a9f1-463">Build 17677</span><span class="sxs-lookup"><span data-stu-id="1a9f1-463">Build 17677</span></span>
<span data-ttu-id="1a9f1-464">Para obter informações gerais do Windows sobre o Build 17677, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/05/24/announcing-windows-10-insider-preview-build-17677/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-464">For general Windows information on build 17677 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/05/24/announcing-windows-10-insider-preview-build-17677/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-465">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-465">WSL</span></span>
* <span data-ttu-id="1a9f1-466">Corrigido um problema adicional em que operações multi-threaded poderiam retornar ENOENT mesmo que o arquivo existisse.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-466">Fixed an additional issue where multithreaded operations could return ENOENT even though the file exists.</span></span> <span data-ttu-id="1a9f1-467">[GH 2712]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-467">[GH 2712]</span></span>
* <span data-ttu-id="1a9f1-468">Correção da falha de inicialização do WSL quando o UMCI está habilitado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-468">Fixed WSL launch failure when UMCI is enabled.</span></span> <span data-ttu-id="1a9f1-469">[GH 3020]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-469">[GH 3020]</span></span>

## <a name="build-17666"></a><span data-ttu-id="1a9f1-470">Build 17666</span><span class="sxs-lookup"><span data-stu-id="1a9f1-470">Build 17666</span></span>
<span data-ttu-id="1a9f1-471">Para obter informações gerais do Windows sobre o Build 17666, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/05/09/announcing-windows-10-insider-preview-build-17666/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-471">For general Windows information on build 17666 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/05/09/announcing-windows-10-insider-preview-build-17666/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-472">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-472">WSL</span></span>
#### <a name="warning-there-is-an-issue-preventing-wsl-from-running-on-some-amd-chipsets-gh-3134-a-fix-is-ready-and-making-its-way-to-the-insider-build-branch"></a><span data-ttu-id="1a9f1-473">AVISO: Há um problema que impede a execução do WSL em alguns chipsets AMD [GH 3134].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-473">WARNING: There is an issue preventing WSL from running on some AMD chipsets [GH 3134].</span></span> <span data-ttu-id="1a9f1-474">Uma correção está pronta e preparando-se para o branch do Build do Insider.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-474">A fix is ready and making its way to the Insider Build branch.</span></span>
* <span data-ttu-id="1a9f1-475">Adição do menu de contexto do Explorer para iniciar o WSL [GH 437, 603, 1836].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-475">Add explorer context menu to launch WSL [GH 437, 603, 1836].</span></span> <span data-ttu-id="1a9f1-476">Para usá-lo, mantenha a tecla Shift pressionada e clique com o botão direito do mouse quando estiver em uma janela do Explorer.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-476">To use hold shift and right-click when in an explorer window.</span></span>
* <span data-ttu-id="1a9f1-477">Correção do comportamento de não bloqueio de soquete do Unix [GH 2822, 3100]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-477">Fix unix socket non-blocking behavior [GH 2822, 3100]</span></span>
* <span data-ttu-id="1a9f1-478">Correção do comando do NetLink suspenso, conforme relatado no GH 2026.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-478">Fix hanging NETLINK command as reported in GH 2026.</span></span>
* <span data-ttu-id="1a9f1-479">Adição de suporte para os sinalizadores de propagação de montagem [GH 2911].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-479">Add support for mount propagation flags [GH 2911].</span></span>
* <span data-ttu-id="1a9f1-480">Correção do problema com truncamento não causando eventos inotify [GH 2978].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-480">Fix issue with truncate not causing inotify events [GH 2978].</span></span>
* <span data-ttu-id="1a9f1-481">Adição da opção --exec para wsl.exe para invocar um único binário sem um shell.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-481">Add --exec option for wsl.exe to invoke a single binary without a shell.</span></span>
* <span data-ttu-id="1a9f1-482">Adição da opção --distribution a wsl.exe para selecionar uma distribuição específica.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-482">Add --distribution option for wsl.exe to select a specific distro.</span></span>

## <a name="build-17655-skip-ahead"></a><span data-ttu-id="1a9f1-483">Build 17655 (ignorar e prosseguir)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-483">Build 17655 (Skip Ahead)</span></span>
<span data-ttu-id="1a9f1-484">Para obter informações gerais do Windows sobre o Build 17655, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/04/25/announcing-windows-10-insider-preview-build-17655-for-skip-ahead/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-484">For general Windows information on build 17655 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/04/25/announcing-windows-10-insider-preview-build-17655-for-skip-ahead/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-485">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-485">WSL</span></span>
* <span data-ttu-id="1a9f1-486">Suporte limitado para dmesg.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-486">Limited support for dmesg.</span></span> <span data-ttu-id="1a9f1-487">Os aplicativos agora podem fazer logon no dmesg.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-487">Applications can now log to dmesg.</span></span> <span data-ttu-id="1a9f1-488">O driver do WSL registra informações limitadas no dmesg.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-488">WSL driver logs limited information to dmesg.</span></span> <span data-ttu-id="1a9f1-489">No futuro, isso pode ser estendido para transportar outras informações/diagnósticos do driver.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-489">In future, this can be extended to carry other information/diagnostics from the driver.</span></span>
    * <span data-ttu-id="1a9f1-490">Observação: atualmente, o dmesg é compatível por meio da interface do dispositivo `/dev/kmsg`.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-490">Note: dmesg is currently supported through the `/dev/kmsg` device interface.</span></span> <span data-ttu-id="1a9f1-491">A interface sycall `syslog` ainda não é compatível.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-491">`syslog` sycall interface is not yet supported.</span></span> <span data-ttu-id="1a9f1-492">Assim sendo, algumas das opções de linha de comando de `dmesg`, tais como `-S` e `-C`, não funcionam.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-492">And, so, some of the `dmesg` command line options such as `-S`, `-C` don't work.</span></span>
* <span data-ttu-id="1a9f1-493">Corrigido um problema em que operações multi-threaded poderiam retornar ENOENT mesmo que o arquivo existisse.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-493">Fixed an issue where multithreaded operations could return ENOENT even though the file exists.</span></span> <span data-ttu-id="1a9f1-494">[GH 2712]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-494">[GH 2712]</span></span>

## <a name="build-17639-skip-ahead"></a><span data-ttu-id="1a9f1-495">Build 17639 (ignorar e prosseguir)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-495">Build 17639 (Skip Ahead)</span></span>
<span data-ttu-id="1a9f1-496">Para obter informações gerais do Windows sobre o Build 17639, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/04/04/announcing-windows-10-insider-preview-build-17639-for-skip-ahead/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-496">For general Windows information on build 17639 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/04/04/announcing-windows-10-insider-preview-build-17639-for-skip-ahead/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-497">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-497">WSL</span></span>
* <span data-ttu-id="1a9f1-498">Alteração do GID e o modo padrão de dispositivos seriais para corresponder ao nativo [GH 3042]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-498">Change default gid and mode of serial devices to match native [GH 3042]</span></span>
* <span data-ttu-id="1a9f1-499">O DrvFs agora dá suporte a atributos estendidos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-499">DrvFs now supports extended attributes.</span></span>
    * <span data-ttu-id="1a9f1-500">Observação: O DrvFs tem algumas limitações sobre o nome dos atributos estendidos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-500">Note: DrvFs has some limitations on the name of extended attributes.</span></span> <span data-ttu-id="1a9f1-501">Em particular, alguns caracteres (tais como '/', ': ' e '\*') não são permitidos e os nomes de atributos estendidos não diferenciam maiúsculas de minúsculas em DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-501">In particular, some characters (like '/', ':' and '\*') are not allowed, and extended attribute names are not case sensitive on DrvFs</span></span>

## <a name="build-17133-fast"></a><span data-ttu-id="1a9f1-502">Build 17133 (rápido)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-502">Build 17133 (Fast)</span></span>
<span data-ttu-id="1a9f1-503">Para obter informações gerais do Windows sobre o Build 17133, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/03/27/announcing-windows-10-insider-preview-build-17133-for-fast/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-503">For general Windows information on build 17133 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/03/27/announcing-windows-10-insider-preview-build-17133-for-fast/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-504">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-504">WSL</span></span>
* <span data-ttu-id="1a9f1-505">Correção para o travamento no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-505">Fix for hang in WSL.</span></span> <span data-ttu-id="1a9f1-506">[GH 3039, 3034]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-506">[GH 3039, 3034]</span></span>

## <a name="build-17128-fast"></a><span data-ttu-id="1a9f1-507">Build 17128 (rápido)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-507">Build 17128 (Fast)</span></span>
<span data-ttu-id="1a9f1-508">Para obter informações gerais do Windows sobre o Build 17128, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/03/23/announcing-windows-10-insider-preview-build-17128-for-fast/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-508">For general Windows information on build 17128 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/03/23/announcing-windows-10-insider-preview-build-17128-for-fast/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-509">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-509">WSL</span></span>
* <span data-ttu-id="1a9f1-510">Não</span><span class="sxs-lookup"><span data-stu-id="1a9f1-510">None</span></span>

## <a name="build-17627-skip-ahead"></a><span data-ttu-id="1a9f1-511">Build 17627 (ignorar e prosseguir)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-511">Build 17627 (Skip Ahead)</span></span>
<span data-ttu-id="1a9f1-512">Para obter informações gerais do Windows sobre o Build 17627, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/03/21/announcing-windows-10-insider-preview-build-17627-for-skip-ahead/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-512">For general Windows information on build 17627 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/03/21/announcing-windows-10-insider-preview-build-17627-for-skip-ahead/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-513">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-513">WSL</span></span>
* <span data-ttu-id="1a9f1-514">Adição de suporte para as operações que reconhecem o Futex PI.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-514">Add support for the futex pi-aware operations.</span></span> <span data-ttu-id="1a9f1-515">[GH 1006]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-515">[GH 1006]</span></span>
    * <span data-ttu-id="1a9f1-516">Observe que as prioridades não são atualmente um recurso WSL compatível para que haja limitações, mas o uso padrão deve ser desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-516">Note that priorities are not currently a supported WSL feature so there are limitations, but standard usage should be unblocked.</span></span>
* <span data-ttu-id="1a9f1-517">Suporte do Firewall do Windows a processos WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-517">Windows firewall support for WSL processes.</span></span> <span data-ttu-id="1a9f1-518">[GH 1852]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-518">[GH 1852]</span></span>
    * <span data-ttu-id="1a9f1-519">Por exemplo, para permitir que o processo Python WSL escute em qualquer porta, use o cmd do Windows com privilégios elevados: ```netsh.exe advfirewall firewall add rule name=wsl_python dir=in action=allow program="C:\users\<username>\appdata\local\packages\canonicalgrouplimited.ubuntuonwindows_79rhkp1fndgsc\localstate\rootfs\usr\bin\python2.7" enable=yes```</span><span class="sxs-lookup"><span data-stu-id="1a9f1-519">For example, to allow the WSL python process to listen on any port, use the elevated Windows cmd: ```netsh.exe advfirewall firewall add rule name=wsl_python dir=in action=allow program="C:\users\<username>\appdata\local\packages\canonicalgrouplimited.ubuntuonwindows_79rhkp1fndgsc\localstate\rootfs\usr\bin\python2.7" enable=yes```</span></span>
    * <span data-ttu-id="1a9f1-520">Para obter detalhes adicionais sobre como adicionar regras de firewall, confira este [link](https://support.microsoft.com/help/947709/how-to-use-the-netsh-advfirewall-firewall-context-instead-of-the-netsh)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-520">For additional details on how to add firewall rules, see [link](https://support.microsoft.com/help/947709/how-to-use-the-netsh-advfirewall-firewall-context-instead-of-the-netsh)</span></span>
* <span data-ttu-id="1a9f1-521">Respeitar o shell padrão do usuário ao usar wsl.exe.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-521">Respect user's default shell when using wsl.exe.</span></span> <span data-ttu-id="1a9f1-522">[GH 2372]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-522">[GH 2372]</span></span>
* <span data-ttu-id="1a9f1-523">Relatar todos os adaptadores de rede como Ethernet.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-523">Report all network interfaces as ethernet.</span></span> <span data-ttu-id="1a9f1-524">[GH 2996]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-524">[GH 2996]</span></span>
* <span data-ttu-id="1a9f1-525">Melhor manipulação de arquivo /etc/passwd corrompido.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-525">Better handling of corrupt /etc/passwd file.</span></span> <span data-ttu-id="1a9f1-526">[GH 3001]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-526">[GH 3001]</span></span>

### <a name="console"></a><span data-ttu-id="1a9f1-527">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-527">Console</span></span>
* <span data-ttu-id="1a9f1-528">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-528">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-529">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-529">LTP Results:</span></span>
<span data-ttu-id="1a9f1-530">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-530">Testing in progress.</span></span>

## <a name="build-17618-skip-ahead"></a><span data-ttu-id="1a9f1-531">Build 17618 (ignorar e prosseguir)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-531">Build 17618 (Skip Ahead)</span></span>
<span data-ttu-id="1a9f1-532">Para obter informações gerais do Windows sobre o Build 17618, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/03/07/announcing-windows-10-insider-preview-build-17618-skip-ahead/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-532">For general Windows information on build 17618 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/03/07/announcing-windows-10-insider-preview-build-17618-skip-ahead/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-533">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-533">WSL</span></span>
* <span data-ttu-id="1a9f1-534">Introduzir a funcionalidade de pseudoconsole para interop NT [GH 988, 1366, 1433, 1542, 2370, 2406].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-534">Introduce pseudoconsole functionality for NT interop [GH 988, 1366, 1433, 1542, 2370, 2406].</span></span>
* <span data-ttu-id="1a9f1-535">O mecanismo de instalação herdado (lxrun. exe) foi preterido.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-535">The legacy install mechanism (lxrun.exe) has been deprecated.</span></span> <span data-ttu-id="1a9f1-536">O mecanismo compatível para a instalação de distribuições é por meio da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-536">The supported mechanism for installing distributions is through the Microsoft Store.</span></span>

### <a name="console"></a><span data-ttu-id="1a9f1-537">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-537">Console</span></span>
* <span data-ttu-id="1a9f1-538">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-538">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-539">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-539">LTP Results:</span></span>
<span data-ttu-id="1a9f1-540">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-540">Testing in progress.</span></span>

## <a name="build-17110"></a><span data-ttu-id="1a9f1-541">Build 17110</span><span class="sxs-lookup"><span data-stu-id="1a9f1-541">Build 17110</span></span>
<span data-ttu-id="1a9f1-542">Para obter informações gerais do Windows sobre o Build 17110, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/02/27/announcing-windows-10-insider-preview-build-17110-fast/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-542">For general Windows information on build 17110 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/02/27/announcing-windows-10-insider-preview-build-17110-fast/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-543">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-543">WSL</span></span>
* <span data-ttu-id="1a9f1-544">Permitir que /init seja encerrado do Windows [GH 2928].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-544">Allow /init to be terminated from Windows [GH 2928].</span></span>
* <span data-ttu-id="1a9f1-545">Por padrão, o DrvFs agora usa a diferenciação de maiúsculas e minúsculas por diretório (equivalente à opção de montagem "case=dir").</span><span class="sxs-lookup"><span data-stu-id="1a9f1-545">DrvFs now uses per-directory case sensitivity by default (equivalent to the "case=dir" mount option).</span></span>
    * <span data-ttu-id="1a9f1-546">O uso de "case=force" (o comportamento antigo) exige a configuração de uma chave do Registro.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-546">Using "case=force" (the old behavior) requires setting a registry key.</span></span> <span data-ttu-id="1a9f1-547">Execute o seguinte comando para habilitar "case=force" se você precisar usá-lo: reg add HKLM\SYSTEM\CurrentControlSet\Services\lxss /v DrvFsAllowForceCaseSensitivity /t REG_DWORD /d 1</span><span class="sxs-lookup"><span data-stu-id="1a9f1-547">Run the following command to enable "case=force" if you need to use it: reg add HKLM\SYSTEM\CurrentControlSet\Services\lxss /v DrvFsAllowForceCaseSensitivity /t REG_DWORD /d 1</span></span>
    * <span data-ttu-id="1a9f1-548">Se você tiver diretórios existentes criados com WSL na versão anterior do Windows que precisem diferenciar maiúsculas de minúsculas, use fsutil.exe para marcá-los como com diferenciação de maiúsculas e minúsculas: fsutil.exe file setcasesensitiveinfo <path> enable</span><span class="sxs-lookup"><span data-stu-id="1a9f1-548">If you have existing directories created with WSL in older version of Windows which need to be case sensitive, use fsutil.exe to mark them as case sensitive: fsutil.exe file setcasesensitiveinfo <path> enable</span></span>
* <span data-ttu-id="1a9f1-549">Termine cadeias de caracteres retornadas da syscall uname com NULL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-549">NULL terminate strings returned from the uname syscall.</span></span>

### <a name="console"></a><span data-ttu-id="1a9f1-550">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-550">Console</span></span>
* <span data-ttu-id="1a9f1-551">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-551">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-552">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-552">LTP Results:</span></span>
<span data-ttu-id="1a9f1-553">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-553">Testing in progress.</span></span>

## <a name="build-17107"></a><span data-ttu-id="1a9f1-554">Build 17107</span><span class="sxs-lookup"><span data-stu-id="1a9f1-554">Build 17107</span></span>
<span data-ttu-id="1a9f1-555">Para obter informações gerais do Windows sobre o Build 17107, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/02/23/announcing-windows-10-insider-preview-build-17107-fast-ring/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-555">For general Windows information on build 17107 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/02/23/announcing-windows-10-insider-preview-build-17107-fast-ring/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-556">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-556">WSL</span></span>
* <span data-ttu-id="1a9f1-557">Suporte a TCSETSF e TCSETSW nos pontos de extremidade mestre pty [GH 2552].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-557">Support TCSETSF and TCSETSW on master pty endpoints [GH 2552].</span></span>
* <span data-ttu-id="1a9f1-558">A inicialização de processos de interop simultâneos pode resultar em EINVAL [GH 2813].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-558">Starting simultaneous interop processes can result in EINVAL [GH 2813].</span></span>
* <span data-ttu-id="1a9f1-559">Correção de PTRACE_ATTACH para mostrar o status de rastreamento adequado em/proc/pid/status.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-559">Fix PTRACE_ATTACH to show proper tracing status in /proc/pid/status.</span></span>
* <span data-ttu-id="1a9f1-560">Correção da corrida em que os processos de curta duração clonados com os dois sinalizadores CLEARTID e SETTID podem ser encerrados sem limpar o endereço de TID.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-560">Fix race where short-lived processes cloned with both the CLEARTID and SETTID flags could exit without clearing the TID address.</span></span>
* <span data-ttu-id="1a9f1-561">Exibir uma mensagem durante a atualização dos diretórios do sistema de arquivos do Linux ao mudar de um build anterior ao 17093.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-561">Display a message when upgrading the Linux file system directories when moving from a pre-17093 build.</span></span> <span data-ttu-id="1a9f1-562">Para obter mais detalhes sobre as alterações do sistema de arquivos 17093, confira as notas sobre a versão para o [17093](https://github.com/MicrosoftDocs/WSL/blob/live/WSL/release-notes.md#build-17093).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-562">For more details on the 17093 file system changes, see the release notes for [17093](https://github.com/MicrosoftDocs/WSL/blob/live/WSL/release-notes.md#build-17093).</span></span>

### <a name="console"></a><span data-ttu-id="1a9f1-563">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-563">Console</span></span>
* <span data-ttu-id="1a9f1-564">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-564">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-565">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-565">LTP Results:</span></span>
<span data-ttu-id="1a9f1-566">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-566">Testing in progress.</span></span>

## <a name="build-17101"></a><span data-ttu-id="1a9f1-567">Build 17101</span><span class="sxs-lookup"><span data-stu-id="1a9f1-567">Build 17101</span></span>
<span data-ttu-id="1a9f1-568">Para obter informações gerais do Windows sobre o Build 17101, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/02/14/announcing-windows-10-insider-preview-build-17101-fast-build-17604-skip-ahead/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-568">For general Windows information on build 17101 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/02/14/announcing-windows-10-insider-preview-build-17101-fast-build-17604-skip-ahead/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-569">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-569">WSL</span></span>
* <span data-ttu-id="1a9f1-570">Suporte para signalfd.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-570">Support for signalfd.</span></span> <span data-ttu-id="1a9f1-571">[GH 129]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-571">[GH 129]</span></span>
* <span data-ttu-id="1a9f1-572">Suporte a nomes de arquivos que contêm caracteres NTFS ilícitos, codificando-os como caracteres Unicode privados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-572">Support file-names containing illegal NTFS characters by encoding them as private Unicode characters.</span></span> <span data-ttu-id="1a9f1-573">[GH 1514]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-573">[GH 1514]</span></span>
* <span data-ttu-id="1a9f1-574">A montagem automática fará fallback para somente leitura quando a gravação não for compatível.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-574">Auto mount will fallback to read-only when write is not supported.</span></span> <span data-ttu-id="1a9f1-575">[GH 2603]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-575">[GH 2603]</span></span>
* <span data-ttu-id="1a9f1-576">Permissão para colagem de pares substitutos Unicode (como caracteres de Emoji).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-576">Allow pasting of Unicode surrogate pairs (like emoji characters).</span></span> <span data-ttu-id="1a9f1-577">[GH 2765]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-577">[GH 2765]</span></span>
* <span data-ttu-id="1a9f1-578">Pseudoarquivos em /proc e /sys devem retornar prontidão para leitura e gravação de select, poll, epoll e outros. [GH 2838]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-578">Pseudo-files in /proc and /sys should return read and write ready from select, poll, epoll, et al. [GH 2838]</span></span>
* <span data-ttu-id="1a9f1-579">Correção do problema que pode fazer com que o serviço entre em loop infinito quando o Registro foi adulterado ou está corrompido.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-579">Fix issue that could cause service to go into infinite loop when the registry has been tampered with or is corrupt.</span></span>
* <span data-ttu-id="1a9f1-580">Correção das mensagens do NetLink para trabalhar com a versão mais recente (upstream 4.14) do iproute2.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-580">Fix netlink messages to work with newer (upstream 4.14) version of iproute2.</span></span>

### <a name="console"></a><span data-ttu-id="1a9f1-581">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-581">Console</span></span>
* <span data-ttu-id="1a9f1-582">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-582">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-583">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-583">LTP Results:</span></span>
<span data-ttu-id="1a9f1-584">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-584">Testing in progress.</span></span>

## <a name="build-17093"></a><span data-ttu-id="1a9f1-585">Build 17093</span><span class="sxs-lookup"><span data-stu-id="1a9f1-585">Build 17093</span></span>
<span data-ttu-id="1a9f1-586">Para obter informações gerais do Windows sobre o Build 17093, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/02/07/announcing-windows-10-insider-preview-build-17093-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-586">For general Windows information on build 17093 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/02/07/announcing-windows-10-insider-preview-build-17093-pc/).</span></span>

#### <a name="important"></a><span data-ttu-id="1a9f1-587">Importante:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-587">Important:</span></span>
<span data-ttu-id="1a9f1-588">Ao iniciar o WSL pela primeira vez após atualizar para esse build, ele precisa executar um certo trabalho de atualização dos diretórios do sistema de arquivos do Linux.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-588">When starting WSL for the first time after upgrading to this build, it needs to perform some work upgrading the Linux file system directories.</span></span> <span data-ttu-id="1a9f1-589">Isso pode levar vários minutos, então a inicialização do WSL pode parecer lenta.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-589">This may take up to several minutes, so WSL may appear to start slowly.</span></span> <span data-ttu-id="1a9f1-590">Isso só deve ocorrer uma vez para cada distribuição instalada por meio da loja.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-590">This should only happen once for each distribution you have installed from the store.</span></span>
* <span data-ttu-id="1a9f1-591">Suporte à diferenciação de maiúsculas e minúsculas melhorada no DrvFs.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-591">Improved case sensitivity support in DrvFs.</span></span>
    * <span data-ttu-id="1a9f1-592">O DrvFs agora dá suporte à diferenciação de maiúsculas e minúsculas por diretório.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-592">DrvFs now supports per-directory case sensitivity.</span></span> <span data-ttu-id="1a9f1-593">Esse é um novo sinalizador que pode ser definido em diretórios para indicar que todas as operações nesses diretórios devem ser tratadas como com diferenciação de maiúsculas de minúsculas, o que permite que até mesmo os aplicativos do Windows abram corretamente arquivos que diferem apenas por maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-593">This is a new flag that can be set on directories to indicate all operations in those directories should be treated as case sensitive, which allows even Windows applications to correctly open files that differ only by case.</span></span>
    * <span data-ttu-id="1a9f1-594">O DrvFs tem novas opções de montagem que controlam a diferenciação de maiúsculas e minúsculas em uma base por diretório</span><span class="sxs-lookup"><span data-stu-id="1a9f1-594">DrvFs has new mount options controlling case sensitivity on a per-directory basis</span></span>
        * <span data-ttu-id="1a9f1-595">Case = Force: todos os diretórios são tratados como com diferenciação de maiúsculas de minúsculas (exceto a raiz da unidade).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-595">case=force: all directories are treated as case sensitive (except for the drive root).</span></span> <span data-ttu-id="1a9f1-596">Os novos diretórios criados com o WSL são marcados como com diferenciação de maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-596">New directories created with WSL are marked as case sensitive.</span></span> <span data-ttu-id="1a9f1-597">Esse é o comportamento herdado, exceto para marcação de novos diretórios como com diferenciação de maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-597">This is the legacy behavior except for marking new directories case sensitive.</span></span>
        * <span data-ttu-id="1a9f1-598">case=dir: somente os diretórios com o sinalizador de diferenciação de maiúsculas e minúsculas por diretório são tratados como com diferenciação de maiúsculas e minúsculas; outros diretórios não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-598">case=dir: only directories with the per-directory case sensitivity flag are treated as case sensitive; other directories are case insensitive.</span></span> <span data-ttu-id="1a9f1-599">Os novos diretórios criados com o WSL são marcados como com diferenciação de maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-599">New directories created with WSL are marked as case sensitive.</span></span>
        * <span data-ttu-id="1a9f1-600">case=off: somente os diretórios com o sinalizador de diferenciação de maiúsculas e minúsculas por diretório são tratados como com diferenciação de maiúsculas e minúsculas; outros diretórios não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-600">case=off: only directories with the per-directory case sensitivity flag are treated as case sensitive; other directories are case insensitive.</span></span> <span data-ttu-id="1a9f1-601">Os novos diretórios criados com WSL são marcados como sem diferenciação de maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-601">New directories created with WSL are marked as case insensitive.</span></span>
    * <span data-ttu-id="1a9f1-602">Observação: os diretórios criados pelo WSL em versões anteriores não têm esse sinalizador definido e, portanto, não serão tratados como diretórios que diferenciam maiúsculas de minúsculas se você usar a opção "case=dir".</span><span class="sxs-lookup"><span data-stu-id="1a9f1-602">Note: directories created by WSL in previous releases do not have this flag set, so will not be treated as case sensitive if you use the "case=dir" option.</span></span> <span data-ttu-id="1a9f1-603">Uma maneira de definir esse sinalizador em diretórios existentes estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-603">A way to set this flag on existing directories is coming soon.</span></span>
    * <span data-ttu-id="1a9f1-604">Exemplo de montagem com essas opções (para unidades existentes, você deve primeiro desmontar antes de poder montar com opções diferentes): sudo mount -t drvfs C: /mnt/c -o case=dir</span><span class="sxs-lookup"><span data-stu-id="1a9f1-604">Example of mounting with these options (for existing drives, you must first unmount before you can mount with different options): sudo mount -t drvfs C: /mnt/c -o case=dir</span></span>
    * <span data-ttu-id="1a9f1-605">Por enquanto, case=force ainda é a opção padrão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-605">For now, case=force is still the default option.</span></span> <span data-ttu-id="1a9f1-606">Isso será alterado para case=dir no futuro.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-606">This will be changed to case=dir in the future.</span></span>
* <span data-ttu-id="1a9f1-607">Agora você pode usar barras invertidas em caminhos do Windows ao montar o DrvFs, por exemplo: sudo mount -t drvfs //server/share /mnt/share</span><span class="sxs-lookup"><span data-stu-id="1a9f1-607">You can now use forward slashes in Windows paths when mounting DrvFs, e.g.: sudo mount -t drvfs //server/share /mnt/share</span></span>
* <span data-ttu-id="1a9f1-608">O WSL agora processa o arquivo/etc/fstab durante a inicialização da instância [GH 2636].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-608">WSL now processes the /etc/fstab file during instance start [GH 2636].</span></span>
    * <span data-ttu-id="1a9f1-609">Isso é feito antes da montagem automática de unidades de DrvFs; todas as unidades que já foram montadas por fstab não serão remontadas automaticamente, permitindo que você altere o ponto de montagem de unidades específicas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-609">This is done prior to automatically mounting DrvFs drives; any drives that were already mounted by fstab will not be remounted automatically, allowing you to change the mount point for specific drives.</span></span>
    * <span data-ttu-id="1a9f1-610">Esse comportamento pode ser desativado usando o wsl.conf.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-610">This behavior can be turned off using wsl.conf.</span></span>
* <span data-ttu-id="1a9f1-611">Os arquivos mount, mountinfo e mountstats em /proc escapam corretamente caracteres especiais, tais como barras invertidas e espaços [GH 2799]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-611">The mount, mountinfo and mountstats files in /proc properly escape special characters like backslashes and spaces [GH 2799]</span></span>
* <span data-ttu-id="1a9f1-612">Arquivos especiais criados com o DrvFs, tais como links simbólicos do WSL, ou então FIFOs e soquetes quando os metadados estão habilitados, agora podem ser copiados e movidos do Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-612">Special files created with DrvFs such as WSL symbolic links, or fifos and sockets when metadata is enabled, can now be copied and moved from Windows.</span></span>

#### <a name="wsl-is-more-configurable-with-wslconf"></a><span data-ttu-id="1a9f1-613">O WSL é mais configurável com o wsl.conf</span><span class="sxs-lookup"><span data-stu-id="1a9f1-613">WSL is more configurable with wsl.conf</span></span>
<span data-ttu-id="1a9f1-614">Adicionamos um método para que você configure automaticamente determinadas funcionalidades no WSL que serão aplicadas toda vez que você iniciar o subsistema.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-614">We added a method for you to automatically configure certain functionality in WSL that will be applied every time you launch the subsystem.</span></span> <span data-ttu-id="1a9f1-615">Isso inclui opções de montagem automática e configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-615">This includes automount options and network configuration.</span></span> <span data-ttu-id="1a9f1-616">Saiba mais sobre isso em nossa postagem no blog em: https://aka.ms/wslconf</span><span class="sxs-lookup"><span data-stu-id="1a9f1-616">Learn more about it in our blog post at: https://aka.ms/wslconf</span></span>

#### <a name="af_unix-allows-socket-connections-between-linux-processes-on-wsl-and-windows-native-processes"></a><span data-ttu-id="1a9f1-617">O AF_UNIX permite conexões de soquete entre processos do Linux em WSL e em processos nativos do Windows</span><span class="sxs-lookup"><span data-stu-id="1a9f1-617">AF_UNIX allows socket connections between Linux processes on WSL and Windows native processes</span></span>
<span data-ttu-id="1a9f1-618">Os aplicativos do WSL e do Windows agora podem se comunicar entre si por meio de soquetes Unix.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-618">WSL and Windows applications can now communicate with each other over Unix sockets.</span></span> <span data-ttu-id="1a9f1-619">Imagine que você deseja executar um serviço no Windows e disponibilizá-lo para aplicativos do Windows e do WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-619">Imagine you want to run a service in Windows and make it available to both Windows and WSL apps.</span></span> <span data-ttu-id="1a9f1-620">Agora, isso é possível com os soquetes do UNIX.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-620">Now, that's possible with Unix sockets.</span></span> <span data-ttu-id="1a9f1-621">Leia mais em nossa postagem no blog em https://aka.ms/afunixinterop</span><span class="sxs-lookup"><span data-stu-id="1a9f1-621">Read more in our blog post at https://aka.ms/afunixinterop</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-622">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-622">WSL</span></span>
* <span data-ttu-id="1a9f1-623">Suporte a mmap () com MAP_NORESERVE [GH 121, 2784]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-623">Support mmap() with MAP_NORESERVE [GH 121, 2784]</span></span>
* <span data-ttu-id="1a9f1-624">Suporte a CLONE_PTRACE e CLONE_UNTRACED [GH 121, 2781]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-624">Support CLONE_PTRACE and CLONE_UNTRACED [GH 121, 2781]</span></span>
* <span data-ttu-id="1a9f1-625">Manipulação do sinal de encerramento não SIGCHLD no clone [GH 121, 2781]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-625">Handle non-SIGCHLD termination signal in clone [GH 121, 2781]</span></span>
* <span data-ttu-id="1a9f1-626">/proc/sys/fs/inotify/max_user_instances and /proc/sys/fs/inotify/max_user_watches de stub [GH 1705]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-626">Stub /proc/sys/fs/inotify/max_user_instances and /proc/sys/fs/inotify/max_user_watches [GH 1705]</span></span>
* <span data-ttu-id="1a9f1-627">Erro ao carregar binários ELF que contêm cabeçalhos de carga com deslocamentos diferentes de zero [GH 1884]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-627">Error loading ELF binaries that contain load headers with non-zero offsets [GH 1884]</span></span>
* <span data-ttu-id="1a9f1-628">Eliminação de todos os bytes de página à direita ao carregar imagens.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-628">Zero out trailing page bytes when loading images.</span></span>
* <span data-ttu-id="1a9f1-629">Redução dos casos em que o execve encerra o processo silenciosamente</span><span class="sxs-lookup"><span data-stu-id="1a9f1-629">Reduce cases where execve silently terminates process</span></span>

### <a name="console"></a><span data-ttu-id="1a9f1-630">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-630">Console</span></span>
* <span data-ttu-id="1a9f1-631">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-631">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-632">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-632">LTP Results:</span></span>
<span data-ttu-id="1a9f1-633">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-633">Testing in progress.</span></span>

## <a name="build-17083"></a><span data-ttu-id="1a9f1-634">Build 17083</span><span class="sxs-lookup"><span data-stu-id="1a9f1-634">Build 17083</span></span>
<span data-ttu-id="1a9f1-635">Para obter informações gerais do Windows sobre o Build 17083, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/01/24/announcing-windows-10-insider-preview-build-17083-for-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-635">For general Windows information on build 17083 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/01/24/announcing-windows-10-insider-preview-build-17083-for-pc/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-636">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-636">WSL</span></span>
* <span data-ttu-id="1a9f1-637">Corrigida a verificação de bug relacionada a epoll [GH 2798, 2801, 2857]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-637">Fixed bugcheck related to epoll [GH 2798, 2801, 2857]</span></span>
* <span data-ttu-id="1a9f1-638">Corrigidos travamentos ao desativar a ASLR [GH 1185, 2870]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-638">Fixed hangs when turning off ASLR [GH 1185, 2870]</span></span>
* <span data-ttu-id="1a9f1-639">Garantia de que as operações mmap parecem atômicas [GH 2732]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-639">Ensure mmap operations appear atomic [GH 2732]</span></span>

### <a name="console"></a><span data-ttu-id="1a9f1-640">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-640">Console</span></span>
* <span data-ttu-id="1a9f1-641">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-641">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-642">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-642">LTP Results:</span></span>
<span data-ttu-id="1a9f1-643">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-643">Testing in progress.</span></span>

## <a name="build-17074"></a><span data-ttu-id="1a9f1-644">Build 17074</span><span class="sxs-lookup"><span data-stu-id="1a9f1-644">Build 17074</span></span>
<span data-ttu-id="1a9f1-645">Para obter informações gerais do Windows sobre o Build 17074, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/01/11/announcing-windows-10-insider-preview-build-17074-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-645">For general Windows information on build 17074 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2018/01/11/announcing-windows-10-insider-preview-build-17074-pc/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-646">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-646">WSL</span></span>
* <span data-ttu-id="1a9f1-647">Corrigido formato de armazenamento de metadados do DrvFs [GH 2777]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-647">Fixed storage format of DrvFs metadata [GH 2777]</span></span> </br>
<span data-ttu-id="1a9f1-648">**Importante:** Os metadados do DrvFs criados antes deste build serão exibidos incorretamente ou não serão exibidos em absoluto.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-648">**Important:** DrvFs metadata created before this build will show up incorrectly or not at all.</span></span> <span data-ttu-id="1a9f1-649">Para corrigir os arquivos afetados, use chmod e chown para aplicar novamente os metadados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-649">To fix affected files, use chmod and chown to re-apply the metadata.</span></span>
* <span data-ttu-id="1a9f1-650">Corrigido o problema com vários sinais e syscalls reinicializáveis.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-650">Fixed issue with multiple signals and restartable syscalls.</span></span>

### <a name="console"></a><span data-ttu-id="1a9f1-651">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-651">Console</span></span>
* <span data-ttu-id="1a9f1-652">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-652">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-653">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-653">LTP Results:</span></span>
<span data-ttu-id="1a9f1-654">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-654">Testing in progress.</span></span>

## <a name="build-17063"></a><span data-ttu-id="1a9f1-655">Build 17063</span><span class="sxs-lookup"><span data-stu-id="1a9f1-655">Build 17063</span></span>
<span data-ttu-id="1a9f1-656">Para obter informações gerais do Windows sobre o Build 17063, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/12/19/announcing-windows-10-insider-preview-build-17063-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-656">For general Windows information on build 17063 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/12/19/announcing-windows-10-insider-preview-build-17063-pc/).</span></span>

### <a name="wsl"></a><span data-ttu-id="1a9f1-657">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-657">WSL</span></span>
* <span data-ttu-id="1a9f1-658">O DrvFs dá suporte a metadados adicionais do Linux.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-658">DrvFs supports additional Linux metadata.</span></span> <span data-ttu-id="1a9f1-659">Isso permite definir o proprietário e o modo de arquivos usando chmod/chown e também criar arquivos especiais, tais como FIFOs, soquetes Unix e arquivos de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-659">This allows setting the owner and mode of files using chmod/chown, and also the creation of special files such as fifos, unix sockets and device files.</span></span> <span data-ttu-id="1a9f1-660">Por enquanto, isso é desabilitado por padrão, pois ainda é experimental.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-660">This is disabled by default for now since it's still experimental.</span></span>
<span data-ttu-id="1a9f1-661">**Observação**:  Corrigimos um bug no formato de metadados usado pelo DrvFs.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-661">**Note:**  We fixed a bug in the metadata format used by DrvFs.</span></span> <span data-ttu-id="1a9f1-662">Embora os metadados funcionem nesse Build para experimentação, os builds futuros não leem corretamente os metadados criados por esse build.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-662">While metadata works on this build for experimentation, future builds will not correctly read metadata created by this build.</span></span>  <span data-ttu-id="1a9f1-663">Talvez seja necessário atualizar manualmente o proprietário para arquivos modificados e os dispositivos com uma ID de dispositivo personalizada precisarão ser recriados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-663">You might need to manually update owner for modified files and devices with a custom device ID will have to be recreated.</span></span>

  <span data-ttu-id="1a9f1-664">Para habilitar, monte o DrvFs com a opção de metadados (para habilitá-lo em uma montagem existente, você precisa primeiro desmontá-lo):</span><span class="sxs-lookup"><span data-stu-id="1a9f1-664">To enable, mount DrvFs with the metadata option (to enable it on an existing mount, you must first unmount it):</span></span>

  ```bash
  mount -t drvfs C: /mnt/c -o metadata
  ```

  <span data-ttu-id="1a9f1-665">As permissões do Linux são adicionadas como metadados adicionais ao arquivo e não afetam as permissões do Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-665">Linux permissions are added as additional metadata to the file; they do not affect the Windows permissions.</span></span>  <span data-ttu-id="1a9f1-666">Lembre-se de que a edição de um arquivo usando um editor do Windows pode remover os metadados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-666">Remember, editing a file using a Windows editor may remove the metadata.</span></span> <span data-ttu-id="1a9f1-667">Nesse caso, o arquivo será revertido para as respectivas permissões padrão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-667">In this case, the file will revert to its default permissions.</span></span>

* <span data-ttu-id="1a9f1-668">Adicionadas opções de montagem ao DrvFs para controlar arquivos sem metadados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-668">Added mount options to DrvFs to control files without metadata.</span></span>
  * <span data-ttu-id="1a9f1-669">uid: a ID de usuário usada para o proprietário de todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-669">uid: the user ID used for the owner of all files.</span></span>
  * <span data-ttu-id="1a9f1-670">gid: a ID de grupo usada para o proprietário de todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-670">gid: the group ID used for the owner of all files.</span></span>
  * <span data-ttu-id="1a9f1-671">umask: uma máscara octal de permissões a serem excluídas para todos os arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-671">umask: an octal mask of permissions to exclude for all files and directories.</span></span>
  * <span data-ttu-id="1a9f1-672">fmask: uma máscara octal de permissões a serem excluídas para todos os arquivos regulares.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-672">fmask: an octal mask of permissions to exclude for all regular files.</span></span>
  * <span data-ttu-id="1a9f1-673">dmask: uma máscara octal de permissões a serem excluídas para todos os diretórios.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-673">dmask: an octal mask of permissions to exclude for all directories.</span></span>

  <span data-ttu-id="1a9f1-674">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-674">For example:</span></span>
  ```
  mount -t drvfs C: /mnt/c -o uid=1000,gid=1000,umask=22,fmask=111
  ```

  <span data-ttu-id="1a9f1-675">Combine com a opção de metadados para especificar permissões padrão para arquivos sem metadados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-675">Combine with the metadata option to specify default permissions for files without metadata.</span></span>

* <span data-ttu-id="1a9f1-676">Introduziu uma nova variável de ambiente, `WSLENV`, para configurar o modo como as variáveis de ambiente fluem entre WSL e Win32.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-676">Introduced a new environment variable, `WSLENV`, to configure how environment variables flow between WSL and Win32.</span></span>

  <span data-ttu-id="1a9f1-677">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-677">For example:</span></span>

  ``` bash
  WSLENV=GOPATH/l:USERPROFILE/pu:DISPLAY
  ```

  <span data-ttu-id="1a9f1-678">`WSLENV` é uma lista delimitada por dois-pontos de variáveis de ambiente que pode ser incluída ao iniciar processos do WSL do Win32 ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-678">`WSLENV` is a colon-delimited list of environment variables that can be included when launching WSL processes from Win32 or Win32 processes from WSL.</span></span>  <span data-ttu-id="1a9f1-679">Cada variável pode ser sufixada com uma barra seguida por sinalizadores para especificar como ela é traduzida.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-679">Each variable can be suffixed with a slash followed by flags to specify how it is translated.</span></span>
  * <span data-ttu-id="1a9f1-680">p: O valor é um caminho que deve ser traduzido entre caminhos WSL e Win32.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-680">p: The value is a path that should be translated between WSL paths and Win32 paths.</span></span>
  * <span data-ttu-id="1a9f1-681">l: O valor é uma lista de caminhos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-681">l: The value is a list of paths.</span></span> <span data-ttu-id="1a9f1-682">No WSL, é uma lista delimitada por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-682">In WSL, it is a colon-delimited list.</span></span> <span data-ttu-id="1a9f1-683">No Win32, é uma lista delimitada por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-683">In Win32, it is a semicolon-delimited list.</span></span>
  * <span data-ttu-id="1a9f1-684">u: O valor só deve ser incluído ao invocar o WSL do Win32</span><span class="sxs-lookup"><span data-stu-id="1a9f1-684">u: The value should only be included when invoking WSL from Win32</span></span>
  * <span data-ttu-id="1a9f1-685">w: O valor só deve ser incluído ao invocar o Win32 do WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-685">w: The value should only be included when invoking Win32 from WSL</span></span>

  <span data-ttu-id="1a9f1-686">Você pode definir `WSLENV` em. bashrc ou no ambiente personalizado do Windows para seu usuário.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-686">You can set `WSLENV` in .bashrc or in the custom Windows environment for your user.</span></span>

* <span data-ttu-id="1a9f1-687">montagens do DrvFs preservam corretamente os carimbos de data/hora de tar, cp -p (GH 1939)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-687">drvfs mounts correctly preserves timestamps from tar, cp -p (GH 1939)</span></span>
* <span data-ttu-id="1a9f1-688">symlinks do DrvFs relatam o tamanho correto (GH 2641)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-688">drvfs symlinks report the correct size (GH 2641)</span></span>
* <span data-ttu-id="1a9f1-689">a leitura/gravação funciona para tamanhos de E/S muito grandes (GH 2653)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-689">read/write works for very large IO sizes (GH 2653)</span></span>
* <span data-ttu-id="1a9f1-690">waitpid trabalha com IDs de grupo de processos (GH 2534)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-690">waitpid works with process group IDs (GH 2534)</span></span>
* <span data-ttu-id="1a9f1-691">desempenho de mmap significativamente melhorado para grandes regiões de reserva; melhora o desempenho do ghc (GH 1671)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-691">significantly improved mmap performance for large reserve regions; improves ghc performance (GH 1671)</span></span>
* <span data-ttu-id="1a9f1-692">suporte a personalidades para READ_IMPLIES_EXEC; corrige maxima e clisp (GH 1185)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-692">personality supports for READ_IMPLIES_EXEC; fixes maxima and clisp (GH 1185)</span></span>
* <span data-ttu-id="1a9f1-693">mprotect dá suporte a PROT_GROWSDOWN; corrige o clisp (GH 1128)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-693">mprotect supports PROT_GROWSDOWN; fixes clisp (GH 1128)</span></span>
* <span data-ttu-id="1a9f1-694">correções de falhas de página no modo de excesso de confirmação; corrige sbcl (GH 1128)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-694">page fault fixes in overcommit mode; fixes sbcl (GH 1128)</span></span>
* <span data-ttu-id="1a9f1-695">o clone dá suporte a mais combinações de sinalizadores</span><span class="sxs-lookup"><span data-stu-id="1a9f1-695">clone supports more flags combinations</span></span>
* <span data-ttu-id="1a9f1-696">Dar suporte a select/epoll de arquivos epoll (anteriormente, algo não operacional).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-696">Support select/epoll of epoll files (previously a no-op).</span></span>
* <span data-ttu-id="1a9f1-697">Notificar ptrace de syscalls não implementadas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-697">Notify ptrace of unimplemented syscalls.</span></span>
* <span data-ttu-id="1a9f1-698">Desconsideração de interfaces que não estão em funcionamento ao gerar nomes de servidor resolv.conf [GH 2694]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-698">Ignore interfaces that are not up when generating resolv.conf nameservers [GH 2694]</span></span>
* <span data-ttu-id="1a9f1-699">Enumeração das interfaces de rede sem endereço físico.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-699">Enumerate network interfaces with no physical address.</span></span> <span data-ttu-id="1a9f1-700">[GH 2685]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-700">[GH 2685]</span></span>
* <span data-ttu-id="1a9f1-701">Pequenas correções de bug e melhorias.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-701">Additional bug fixes and improvements.</span></span>

### <a name="linux-tools-available-to-developers-on-windows"></a><span data-ttu-id="1a9f1-702">Ferramentas do Linux disponíveis para desenvolvedores no Windows</span><span class="sxs-lookup"><span data-stu-id="1a9f1-702">Linux tools available to developers on Windows</span></span>

* <span data-ttu-id="1a9f1-703">A Cadeia de Ferramentas de Linha de Comando do Windows ferramentas inclui bsdtar (tar) e curl.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-703">Windows Command line Toolchain includes bsdtar (tar) and curl.</span></span>
  <span data-ttu-id="1a9f1-704">Leia [este blog](https://aka.ms/tarcurlwindows) para saber mais sobre a adição dessas duas novas ferramentas e veja como elas estão moldando a experiência do desenvolvedor no Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-704">Read [this blog](https://aka.ms/tarcurlwindows) to learn more about the addition of these two new tools and see how they're shaping the developer experience on Windows.</span></span>

*   <span data-ttu-id="1a9f1-705">`AF_UNIX` está disponível no SDK do Participante do Programa Windows Insider (17061+).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-705">`AF_UNIX` is available in the Windows Insider SDK (17061+).</span></span>
  <span data-ttu-id="1a9f1-706">Leia [este blog](https://blogs.msdn.microsoft.com/commandline/2017/12/19/af_unix-comes-to-windows/) para saber mais sobre o `AF_UNIX` e como os desenvolvedores do Windows podem usá-lo.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-706">Read [this blog](https://blogs.msdn.microsoft.com/commandline/2017/12/19/af_unix-comes-to-windows/) to learn more about `AF_UNIX` and how developers on Windows can use it.</span></span>

### <a name="console"></a><span data-ttu-id="1a9f1-707">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-707">Console</span></span>
* <span data-ttu-id="1a9f1-708">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-708">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-709">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-709">LTP Results:</span></span>
<span data-ttu-id="1a9f1-710">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-710">Testing in progress.</span></span>


## <a name="build-17046"></a><span data-ttu-id="1a9f1-711">Build 17046</span><span class="sxs-lookup"><span data-stu-id="1a9f1-711">Build 17046</span></span>

<span data-ttu-id="1a9f1-712">Para obter informações gerais do Windows sobre o Build 17046, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/11/22/announcing-windows-10-insider-preview-build-17046-pc).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-712">For general Windows information on build 17046 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/11/22/announcing-windows-10-insider-preview-build-17046-pc).</span></span>

### <a name="fixed"></a><span data-ttu-id="1a9f1-713">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-713">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-714">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-714">WSL</span></span>
- <span data-ttu-id="1a9f1-715">Permissão para que processos sejam executados sem um terminal ativo.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-715">Allow processes to run without an active terminal.</span></span> <span data-ttu-id="1a9f1-716">[GH 709, 1007, 1511, 2252, 2391 e outros]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-716">[GH 709, 1007, 1511, 2252, 2391, et al.]</span></span>
- <span data-ttu-id="1a9f1-717">Melhor suporte a CLONE_VFORK e CLONE_VM.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-717">Better support of CLONE_VFORK and CLONE_VM.</span></span> <span data-ttu-id="1a9f1-718">[GH 1878, 2615]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-718">[GH 1878, 2615]</span></span>
- <span data-ttu-id="1a9f1-719">Desconsideração de drivers de filtro de TDI para operações de rede WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-719">Skip TDI filter drivers for WSL networking operations.</span></span> <span data-ttu-id="1a9f1-720">[GH 1554]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-720">[GH 1554]</span></span>
- <span data-ttu-id="1a9f1-721">DrvFs cria NT symlinks quando determinadas condições são atendidas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-721">DrvFs creates NT symlinks when certain conditions are met.</span></span> <span data-ttu-id="1a9f1-722">[GH 353, 1475, 2602]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-722">[GH 353, 1475, 2602]</span></span>
    - <span data-ttu-id="1a9f1-723">O destino do link precisa ser relativo, não pode cruzar nenhum ponto de montagem nem symlink e precisa existir.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-723">The link target must be relative, must not cross any mount points or symlinks, and must exist.</span></span>
    - <span data-ttu-id="1a9f1-724">O usuário deve ter SE_CREATE_SYMBOLIC_LINK_PRIVILEGE (isso normalmente requer que você inicie o wsl.exe com privilégios elevados), a menos que o modo de desenvolvedor esteja ativado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-724">The user must have SE_CREATE_SYMBOLIC_LINK_PRIVILEGE (this normally requires you to launch wsl.exe elevated), unless Developer Mode is turned on.</span></span>
    - <span data-ttu-id="1a9f1-725">Em todas as outras situações, o DrvFs ainda cria symlinks do WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-725">In all other situations, DrvFs still creates WSL symlinks.</span></span>
- <span data-ttu-id="1a9f1-726">Permissão para a execução de instâncias de WSL elevadas e não elevadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-726">Allow running elevated and non-elevated WSL instances simultaneously.</span></span>
- <span data-ttu-id="1a9f1-727">Suporte a /proc/sys/kernel/yama/ptrace_scope</span><span class="sxs-lookup"><span data-stu-id="1a9f1-727">Support /proc/sys/kernel/yama/ptrace_scope</span></span>
- <span data-ttu-id="1a9f1-728">Adição de wslpath para realizar conversões de caminho WSL<->Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-728">Add wslpath to do WSL<->Windows path conversions.</span></span> <span data-ttu-id="1a9f1-729">[GH 522, 1243, 1834, 2327 e outros]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-729">[GH 522, 1243, 1834, 2327, et al.]</span></span>
  ```
    wslpath usage:
      -a    force result to absolute path format
      -u    translate from a Windows path to a WSL path (default)
      -w    translate from a WSL path to a Windows path
      -m    translate from a WSL path to a Windows path, with '/' instead of '\\'

      EX: wslpath 'c:\users'
  ```
  #### <a name="console"></a><span data-ttu-id="1a9f1-730">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-730">Console</span></span>
- <span data-ttu-id="1a9f1-731">Sem correções.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-731">No fixes.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-732">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-732">LTP Results:</span></span>
<span data-ttu-id="1a9f1-733">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-733">Testing in progress.</span></span>


## <a name="build-17040"></a><span data-ttu-id="1a9f1-734">Build 17040</span><span class="sxs-lookup"><span data-stu-id="1a9f1-734">Build 17040</span></span>

<span data-ttu-id="1a9f1-735">Para obter informações gerais do Windows sobre o Build 17040, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/11/16/announcing-windows-10-insider-preview-build-17040-pc).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-735">For general Windows information on build 17040 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/11/16/announcing-windows-10-insider-preview-build-17040-pc).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-736">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-736">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-737">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-737">WSL</span></span>
- <span data-ttu-id="1a9f1-738">Nenhuma correção desde o 17035.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-738">No fixes since 17035.</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-739">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-739">Console</span></span>
- <span data-ttu-id="1a9f1-740">Nenhuma correção desde o 17035.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-740">No fixes since 17035.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-741">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-741">LTP Results:</span></span>
<span data-ttu-id="1a9f1-742">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-742">Testing in progress.</span></span>

## <a name="build-17035"></a><span data-ttu-id="1a9f1-743">Build 17035</span><span class="sxs-lookup"><span data-stu-id="1a9f1-743">Build 17035</span></span>

<span data-ttu-id="1a9f1-744">Para obter informações gerais do Windows sobre o Build 17035, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/11/08/announcing-windows-10-insider-preview-build-17035-pc).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-744">For general Windows information on build 17035 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/11/08/announcing-windows-10-insider-preview-build-17035-pc).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-745">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-745">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-746">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-746">WSL</span></span>
- <span data-ttu-id="1a9f1-747">O acesso a arquivos no DrvFs pode ocasionalmente falhar com EINVAL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-747">Accessing files on DrvFs could occasionally fail with EINVAL.</span></span> <span data-ttu-id="1a9f1-748">[GH 2448]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-748">[GH 2448]</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-749">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-749">Console</span></span>
- <span data-ttu-id="1a9f1-750">Um pouco de perda de cor ao inserir/excluir linhas no modo VT.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-750">Some color loss when inserting/deleting lines in VT mode.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-751">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-751">LTP Results:</span></span>
<span data-ttu-id="1a9f1-752">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-752">Testing in progress.</span></span>

## <a name="build-17025"></a><span data-ttu-id="1a9f1-753">Build 17025</span><span class="sxs-lookup"><span data-stu-id="1a9f1-753">Build 17025</span></span>

<span data-ttu-id="1a9f1-754">Para obter informações gerais do Windows sobre o Build 17025, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/10/25/announcing-windows-10-insider-preview-build-17025-pc).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-754">For general Windows information on build 17025 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/10/25/announcing-windows-10-insider-preview-build-17025-pc).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-755">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-755">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-756">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-756">WSL</span></span>
- <span data-ttu-id="1a9f1-757">Inicialização dos processos iniciais em um novo grupo de processos de primeiro plano [GH 1653, 2510].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-757">Start initial processes in a new foreground process group [GH 1653, 2510].</span></span>
- <span data-ttu-id="1a9f1-758">Correções de entrega SIGHUP [GH 2496].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-758">SIGHUP delivery fixes [GH 2496].</span></span>
- <span data-ttu-id="1a9f1-759">Geração do nome de ponte virtual padrão se nenhum for fornecido [GH 2497].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-759">Generate default virtual bridge name if none provided [GH 2497].</span></span>
- <span data-ttu-id="1a9f1-760">Implementação de /proc/sys/kernel/random/boot_id [GH 2518].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-760">Implement /proc/sys/kernel/random/boot_id [GH 2518].</span></span>
- <span data-ttu-id="1a9f1-761">Mais correções de pipe stdout/stderr de interop.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-761">More interop stdout/stderr pipe fixes.</span></span>
- <span data-ttu-id="1a9f1-762">Chamada do sistema syncfs de stub.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-762">Stub syncfs system call.</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-763">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-763">Console</span></span>
- <span data-ttu-id="1a9f1-764">Correção da conversão de VT de entrada para consoles de terceiros [GH 111]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-764">Fix input VT translation for third party consoles [GH 111]</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-765">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-765">LTP Results:</span></span>
<span data-ttu-id="1a9f1-766">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-766">Testing in progress.</span></span>

## <a name="build-17017"></a><span data-ttu-id="1a9f1-767">Build 17017</span><span class="sxs-lookup"><span data-stu-id="1a9f1-767">Build 17017</span></span>

<span data-ttu-id="1a9f1-768">Para obter informações gerais do Windows sobre o Build 17017, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/10/13/announcing-windows-10-insider-preview-build-17017-pc).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-768">For general Windows information on build 17017 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/10/13/announcing-windows-10-insider-preview-build-17017-pc).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-769">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-769">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-770">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-770">WSL</span></span>
- <span data-ttu-id="1a9f1-771">Desconsideração dos cabeçalhos de programa ELF vazios [GH 330].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-771">Ignore empty ELF program headers [GH 330].</span></span>
- <span data-ttu-id="1a9f1-772">Permissão para que o LxssManager Crie instâncias do WSL para usuários não interativos (SSH e suporte a tarefas agendadas) [GH 777, 1602].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-772">Allow LxssManager to create WSL instances for non-interactive users (ssh and scheduled task support) [GH 777, 1602].</span></span>
- <span data-ttu-id="1a9f1-773">Suporte a cenários de ("início") WSL-> Win32-> WSL [GH 1228].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-773">Support WSL->Win32->WSL ("inception") scenarios [GH 1228].</span></span>
- <span data-ttu-id="1a9f1-774">Suporte limitado para encerramento de aplicativos de console invocados via interop [GH 1614].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-774">Limited support for termination of console apps invoked via interop [GH 1614].</span></span>
- <span data-ttu-id="1a9f1-775">Suporte a opções de montagem para devpts [GH 1948].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-775">Support mount options for devpts [GH 1948].</span></span>
- <span data-ttu-id="1a9f1-776">Ptrace bloqueando a inicialização do filho [GH 2333].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-776">Ptrace blocking child startup [GH 2333].</span></span>
- <span data-ttu-id="1a9f1-777">EPOLLET com alguns eventos ausentes [GH 2462].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-777">EPOLLET missing some events [GH 2462].</span></span>
- <span data-ttu-id="1a9f1-778">Retorno de mais dados para PTRACE_GETSIGINFO.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-778">Return more data for PTRACE_GETSIGINFO.</span></span>
- <span data-ttu-id="1a9f1-779">Getdents com lseek fornece resultados incorretos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-779">Getdents with lseek gives incorrect results.</span></span>
- <span data-ttu-id="1a9f1-780">Correção de alguns travamentos do aplicativo de interop Win32, aguardando a entrada em um pipe que não tem mais dados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-780">Fix some Win32 interop app hangs, waiting for input on a pipe that has no more data.</span></span>
- <span data-ttu-id="1a9f1-781">Suporte do O_ASYNC para arquivos tty/pty.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-781">O_ASYNC support for tty/pty files.</span></span>
- <span data-ttu-id="1a9f1-782">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-782">Additional improvements and bug fixes</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-783">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-783">Console</span></span>
- <span data-ttu-id="1a9f1-784">Nenhuma alteração relacionada ao console nesta versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-784">No Console related changes in this release.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-785">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-785">LTP Results:</span></span>
<span data-ttu-id="1a9f1-786">Testes em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-786">Testing in progress.</span></span>

## <a name="fall-creators-update"></a><span data-ttu-id="1a9f1-787">Fall Creators Update</span><span class="sxs-lookup"><span data-stu-id="1a9f1-787">Fall Creators Update</span></span>

## <a name="build-16288"></a><span data-ttu-id="1a9f1-788">Build 16288</span><span class="sxs-lookup"><span data-stu-id="1a9f1-788">Build 16288</span></span>

<span data-ttu-id="1a9f1-789">Para obter informações gerais do Windows sobre o Build 16288, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/09/12/announcing-windows-10-insider-preview-build-16288-pc-build-15250-mobile/#7pLWQbj23JisfzV5.97/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-789">For general Windows information on build 16288 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/09/12/announcing-windows-10-insider-preview-build-16288-pc-build-15250-mobile/#7pLWQbj23JisfzV5.97/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-790">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-790">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-791">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-791">WSL</span></span>
- <span data-ttu-id="1a9f1-792">Inicialização e relatório corretos de UID, GID e modo para descritores de arquivo de soquete [GH 2490]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-792">Correctly initialize and report uid, gid, and mode for socket file descriptors [GH 2490]</span></span>
- <span data-ttu-id="1a9f1-793">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-793">Additional improvements and bug fixes</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-794">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-794">Console</span></span>
- <span data-ttu-id="1a9f1-795">Nenhuma alteração relacionada ao console nesta versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-795">No Console related changes in this release.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-796">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-796">LTP Results:</span></span>
<span data-ttu-id="1a9f1-797">Nenhuma alteração desde o 16273</span><span class="sxs-lookup"><span data-stu-id="1a9f1-797">No change since 16273</span></span>

## <a name="build-16278"></a><span data-ttu-id="1a9f1-798">Build 16278</span><span class="sxs-lookup"><span data-stu-id="1a9f1-798">Build 16278</span></span>

<span data-ttu-id="1a9f1-799">Para obter informações gerais do Windows sobre o Build 162738, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/08/29/announcing-windows-10-insider-preview-build-16278-pc/#HMz6Xq7Su68WKi0t.97/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-799">For general Windows information on build 162738 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/08/29/announcing-windows-10-insider-preview-build-16278-pc/#HMz6Xq7Su68WKi0t.97/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-800">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-800">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-801">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-801">WSL</span></span>
- <span data-ttu-id="1a9f1-802">Desmapeamento explícito de exibições mapeadas de seções com backup de arquivo ao dividir o estado LX MM [GH 2415]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-802">Explicitly unmap mapped views of file backed sections when tearing down LX MM state [GH 2415]</span></span>
- <span data-ttu-id="1a9f1-803">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-803">Additional improvements and bug fixes</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-804">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-804">Console</span></span>
- <span data-ttu-id="1a9f1-805">Nenhuma alteração relacionada ao console nesta versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-805">No Console related changes in this release.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-806">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-806">LTP Results:</span></span>
<span data-ttu-id="1a9f1-807">Nenhuma alteração desde o 16273</span><span class="sxs-lookup"><span data-stu-id="1a9f1-807">No change since 16273</span></span>

## <a name="build-16275"></a><span data-ttu-id="1a9f1-808">Build 16275</span><span class="sxs-lookup"><span data-stu-id="1a9f1-808">Build 16275</span></span>

<span data-ttu-id="1a9f1-809">Para obter informações gerais do Windows sobre o Build 162735, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/08/25/announcing-windows-10-insider-preview-build-16275-pc-build-15245-mobile/#8QkxWqQbY37yZslV.97/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-809">For general Windows information on build 162735 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/08/25/announcing-windows-10-insider-preview-build-16275-pc-build-15245-mobile/#8QkxWqQbY37yZslV.97/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-810">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-810">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-811">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-811">WSL</span></span>
- <span data-ttu-id="1a9f1-812">Nenhuma alteração relacionada ao WSL nesta versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-812">No WSL related changes in this release.</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-813">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-813">Console</span></span>
- <span data-ttu-id="1a9f1-814">Nenhuma alteração relacionada ao console nesta versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-814">No Console related changes in this release.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-815">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-815">LTP Results:</span></span>
<span data-ttu-id="1a9f1-816">Nenhuma alteração desde o 16273</span><span class="sxs-lookup"><span data-stu-id="1a9f1-816">No change since 16273</span></span>

## <a name="build-16273"></a><span data-ttu-id="1a9f1-817">Build 16273</span><span class="sxs-lookup"><span data-stu-id="1a9f1-817">Build 16273</span></span>

<span data-ttu-id="1a9f1-818">Para obter informações gerais do Windows sobre o Build 16273, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/08/23/announcing-windows-10-insider-preview-build-16273-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-818">For general Windows information on build 16273 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/08/23/announcing-windows-10-insider-preview-build-16273-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-819">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-819">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-820">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-820">WSL</span></span>
- <span data-ttu-id="1a9f1-821">Corrigido um problema em que o DrvFs às vezes relatava o tipo de arquivo errado para diretórios [GH 2392]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-821">Fixed an issue where DrvFs sometimes reported the wrong file type for directories [GH 2392]</span></span>
- <span data-ttu-id="1a9f1-822">Permissão para a criação de soquetes NETLINK_KOBJECT_UEVENT para desbloquear programas que usam uevent [GH 1121, 2293, 2242, 2295, 2235, 648, 637]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-822">Allow creation of NETLINK_KOBJECT_UEVENT sockets to unblock programs that use uevent [GH 1121, 2293, 2242, 2295, 2235, 648, 637]</span></span>
- <span data-ttu-id="1a9f1-823">Adição de suporte para conexão sem bloqueio [GH 903, 1391, 1584, 1585, 1829, 2290, 2314]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-823">Add support for non-blocking connect [GH 903, 1391, 1584, 1585, 1829, 2290, 2314]</span></span>
- <span data-ttu-id="1a9f1-824">Implementação do sinalizador de chamada do sistema de clone CLONE_FS [GH 2242]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-824">Implement CLONE_FS clone system call flag [GH 2242]</span></span>
- <span data-ttu-id="1a9f1-825">Correção de problemas relacionados à manipulação incorreta de guias ou aspas no interop NT [GH 1625, 2164]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-825">Fix issues around not handling tabs or quotes correctly in NT interop [GH 1625, 2164]</span></span>
- <span data-ttu-id="1a9f1-826">Resolução de erro de acesso negado ao tentar reinicializar instâncias de WSL [GH 651, 2095]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-826">Resolve access denied error when trying to re-launch WSL instances [GH 651, 2095]</span></span>
- <span data-ttu-id="1a9f1-827">Implementação das operações FUTEX_REQUEUE e FUTEX_CMP_REQUEUE do futex [GH 2242]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-827">Implement futex FUTEX_REQUEUE and FUTEX_CMP_REQUEUE operations [GH 2242]</span></span>
- <span data-ttu-id="1a9f1-828">Correção de permissões para vários arquivos SysFs [GH 2214]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-828">Fix permissions for various SysFs files [GH 2214]</span></span>
- <span data-ttu-id="1a9f1-829">Correção do travamento da pilha do Haskell durante a instalação [GH 2290]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-829">Fix Haskell stack hang during setup [GH 2290]</span></span>
- <span data-ttu-id="1a9f1-830">Implementação dos sinalizadores 'C', 'O' e 'P' do binfmt_misc [GH 2103]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-830">Implement binfmt_misc 'C' 'O' and 'P' flags [GH 2103]</span></span>
- <span data-ttu-id="1a9f1-831">Adição de /proc/sys/kernel/shmmax/shmmni e /threads-max [GH 1753]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-831">Add /proc/sys/kernel /shmmax /shmmni & /threads-max [GH 1753]</span></span>
- <span data-ttu-id="1a9f1-832">Adição de suporte parcial para chamada do sistema ioprio_set [GH 498]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-832">Add partial support for ioprio_set system call [GH 498]</span></span>
- <span data-ttu-id="1a9f1-833">SO_REUSEPORT de stub e adicionar suporte para SO_PASSCRED para soquetes netlink [GH 69]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-833">Stub SO_REUSEPORT & adding support for SO_PASSCRED for netlink sockets [GH 69]</span></span>
- <span data-ttu-id="1a9f1-834">Retorno de códigos de erro diferentes de RegisterDistribuiton se uma distribuição estiver sendo instalada ou desinstalada no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-834">Return different error codes from RegisterDistribuiton if a distribution is currently being installed or uninstalled.</span></span>
- <span data-ttu-id="1a9f1-835">Permissão para o cancelamento de registro de distribuições de WSL parcialmente instaladas por meio de wslconfig.exe</span><span class="sxs-lookup"><span data-stu-id="1a9f1-835">Allow unregistration of partially installed WSL distributions via wslconfig.exe</span></span>
- <span data-ttu-id="1a9f1-836">Correção do travamento do teste de soquete Python de udp::msg_peek</span><span class="sxs-lookup"><span data-stu-id="1a9f1-836">Fix python socket test hang from udp::msg_peek</span></span>
- <span data-ttu-id="1a9f1-837">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-837">Additional improvements and bug fixes</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-838">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-838">Console</span></span>
- <span data-ttu-id="1a9f1-839">Nenhuma alteração relacionada ao console nesta versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-839">No Console related changes in this release.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-840">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-840">LTP Results:</span></span>
<span data-ttu-id="1a9f1-841">Total de testes: 1904</span><span class="sxs-lookup"><span data-stu-id="1a9f1-841">Total Tests: 1904</span></span><br/>
<span data-ttu-id="1a9f1-842">Total de testes ignorados: 209</span><span class="sxs-lookup"><span data-stu-id="1a9f1-842">Total Skipped Tests: 209</span></span><br/>
<span data-ttu-id="1a9f1-843">Total de falhas: 229</span><span class="sxs-lookup"><span data-stu-id="1a9f1-843">Total Failures: 229</span></span><br/>
[<span data-ttu-id="1a9f1-844">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-844">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/16273)<br/>

## <a name="build-16257"></a><span data-ttu-id="1a9f1-845">Build 16257</span><span class="sxs-lookup"><span data-stu-id="1a9f1-845">Build 16257</span></span>

<span data-ttu-id="1a9f1-846">Para obter informações gerais do Windows sobre o Build 16257, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/08/02/announcing-windows-10-insider-preview-build-16257-pc-build-15237-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-846">For general Windows information on build 16257 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/08/02/announcing-windows-10-insider-preview-build-16257-pc-build-15237-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-847">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-847">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-848">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-848">WSL</span></span>
- <span data-ttu-id="1a9f1-849">Implementação da chamada do sistema prlimit64</span><span class="sxs-lookup"><span data-stu-id="1a9f1-849">Implement prlimit64 system call</span></span>
- <span data-ttu-id="1a9f1-850">Adição de suporte para ulimit -n (setrlimit RLIMIT_NOFILE) [GH 1688]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-850">Add support for ulimit -n (setrlimit RLIMIT_NOFILE) [GH 1688]</span></span>
- <span data-ttu-id="1a9f1-851">MSG_MORE de stub para soquetes TCP [GH 2351]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-851">Stub MSG_MORE for TCP sockets [GH 2351]</span></span>
- <span data-ttu-id="1a9f1-852">Correção do comportamento de vetor auxiliar AT_EXECFN inválido [GH 2133]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-852">Fix invalid AT_EXECFN auxiliary vector behavior [GH 2133]</span></span>
- <span data-ttu-id="1a9f1-853">Correção do comportamento de copiar/colar para console/TTY e adição de melhor manipulação de buffer completo [GH 2204, 2131]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-853">Fix copy/paste behavior for console/tty, and add better full buffer handling [GH 2204, 2131]</span></span>
- <span data-ttu-id="1a9f1-854">Definição de AT_SECURE em vetor auxiliar para os programas set-user-ID e set-group-ID [GH 2031]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-854">Set AT_SECURE in auxiliary vector for set-user-ID and set-group-ID programs [GH 2031]</span></span>
- <span data-ttu-id="1a9f1-855">Ponto de extremidade mestre de pseudoterminal não manipulando TIOCPGRP [GH 1063]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-855">Psuedo-terminal master endpoint not handling TIOCPGRP [GH 1063]</span></span>
- <span data-ttu-id="1a9f1-856">Correção do que o lseek faz para rebobinar diretórios no LxFs [GH 2310]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-856">Fix lseek does to rewind directories in LxFs [GH 2310]</span></span>
- <span data-ttu-id="1a9f1-857">/dev/ptmx trava após uso intenso [GH 1882]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-857">/dev/ptmx locks up after heavy usage [GH 1882]</span></span>
- <span data-ttu-id="1a9f1-858">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-858">Additional improvements and bug fixes</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-859">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-859">Console</span></span>
- <span data-ttu-id="1a9f1-860">Correção para linhas horizontais/sublinhados em todos os lugares [GH 2168]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-860">Fix for horizontal Lines/Underscores Everywhere [GH 2168]</span></span>
- <span data-ttu-id="1a9f1-861">Correção para a ordem de processo alterada, tornando o NPM mais difícil de fechar [GH 2170]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-861">Fix for process order changed making NPM harder to close [GH 2170]</span></span>
- <span data-ttu-id="1a9f1-862">Adicionado nosso novo esquema de cores: https://blogs.msdn.microsoft.com/commandline/2017/08/02/updating-the-windows-console-colors/</span><span class="sxs-lookup"><span data-stu-id="1a9f1-862">Added our new color scheme: https://blogs.msdn.microsoft.com/commandline/2017/08/02/updating-the-windows-console-colors/</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-863">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-863">LTP Results:</span></span>
<span data-ttu-id="1a9f1-864">Nenhuma alteração desde o 16251</span><span class="sxs-lookup"><span data-stu-id="1a9f1-864">No change since 16251</span></span>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-865">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-865">Syscall Support</span></span>
<span data-ttu-id="1a9f1-866">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-866">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-867">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-867">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`prlimit64`<br/>

### <a name="known-issues"></a><span data-ttu-id="1a9f1-868">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-868">Known Issues</span></span>
#### <a name="github-issue-2392-windows-folders-not-recognized-by-wsl-"></a>[<span data-ttu-id="1a9f1-869">Problema do GitHub n. 2392: Pastas do Windows não reconhecidas pelo WSL...</span><span class="sxs-lookup"><span data-stu-id="1a9f1-869">GitHub Issue 2392: Windows Folders not recognized by WSL ...</span></span>](https://github.com/Microsoft/BashOnWindows/issues/2392)
<span data-ttu-id="1a9f1-870">No build 16257, o WSL tem problemas para enumerar arquivos/pastas do Windows via `/mnt/c/...`.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-870">In build 16257, WSL has issues when enumerating Windows files/folders via `/mnt/c/...`.</span></span>
<span data-ttu-id="1a9f1-871">Esse problema foi corrigido e deve ser liberado no build do Insiders durante a semana que começa em 14/08/2017.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-871">This issue has been fixed and should be released in Insiders build during week commencing 8/14/2017.</span></span>

<br/>

## <a name="build-16251"></a><span data-ttu-id="1a9f1-872">Build 16251</span><span class="sxs-lookup"><span data-stu-id="1a9f1-872">Build 16251</span></span>

<span data-ttu-id="1a9f1-873">Para obter informações gerais do Windows sobre o Build 16251, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/07/26/announcing-windows-10-insider-preview-build-16251-pc-build-15235-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-873">For general Windows information on build 16251 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/07/26/announcing-windows-10-insider-preview-build-16251-pc-build-15235-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-874">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-874">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-875">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-875">WSL</span></span>
- <span data-ttu-id="1a9f1-876">Remova a tag beta do componente opcional do WSL, confira esta [postagem no blog](https://blogs.msdn.microsoft.com/commandline/2017/07/28/windows-subsystem-for-linux-out-of-beta/) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-876">Remove beta tag from WSL optional component, see [blog post](https://blogs.msdn.microsoft.com/commandline/2017/07/28/windows-subsystem-for-linux-out-of-beta/) for details.</span></span>
- <span data-ttu-id="1a9f1-877">Inicializar corretamente a UID e a GID salvas para os binários Set-User-ID e Set-Group-ID em exec [GH 962, 1415, 2072]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-877">Correctly initialize saved-set uid and gid for set-user-ID and set-group-ID binaries on exec [GH 962, 1415, 2072]</span></span>
- <span data-ttu-id="1a9f1-878">Adicionado suporte para ptrace PTRACE_O_TRACEEXIT [GH 555]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-878">Added support for ptrace PTRACE_O_TRACEEXIT [GH 555]</span></span>
- <span data-ttu-id="1a9f1-879">Adicionado suporte para ptrace PTRACE_GETFPREGS e PTRACE_GETREGSET com NT_FPREGSET [GH 555]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-879">Added support for ptrace PTRACE_GETFPREGS and PTRACE_GETREGSET with NT_FPREGSET [GH 555]</span></span>
- <span data-ttu-id="1a9f1-880">Correção de ptrace para parar em sinais ignorados</span><span class="sxs-lookup"><span data-stu-id="1a9f1-880">Fixed ptrace to stop on ignored signals</span></span>
- <span data-ttu-id="1a9f1-881">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-881">Additional improvements and bug fixes</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-882">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-882">Console</span></span>
- <span data-ttu-id="1a9f1-883">Nenhuma alteração relacionada ao console nesta versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-883">No Console related changes in this release.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-884">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-884">LTP Results:</span></span>
<span data-ttu-id="1a9f1-885">Número de testes aprovados: 768</span><span class="sxs-lookup"><span data-stu-id="1a9f1-885">Number of Passing Tests: 768</span></span></br>
<span data-ttu-id="1a9f1-886">Número de testes reprovados: 244</span><span class="sxs-lookup"><span data-stu-id="1a9f1-886">Number of Failing Tests: 244</span></span></br>
<span data-ttu-id="1a9f1-887">Número de testes ignorados: 96</span><span class="sxs-lookup"><span data-stu-id="1a9f1-887">Number of Skipped Tests: 96</span></span></br>
[<span data-ttu-id="1a9f1-888">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-888">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/16251)<br/>

</br>

## <a name="build-16241"></a><span data-ttu-id="1a9f1-889">Build 16241</span><span class="sxs-lookup"><span data-stu-id="1a9f1-889">Build 16241</span></span>

<span data-ttu-id="1a9f1-890">Para obter informações gerais do Windows sobre o Build 16241, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/07/13/announcing-windows-10-insider-preview-build-16241-pc-build-15230-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-890">For general Windows information on build 16241 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/07/13/announcing-windows-10-insider-preview-build-16241-pc-build-15230-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-891">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-891">Fixed</span></span>
#### <a name="wsl"></a><span data-ttu-id="1a9f1-892">WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-892">WSL</span></span>
- <span data-ttu-id="1a9f1-893">Nenhuma alteração relacionada ao WSL nesta versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-893">No WSL related changes in this release.</span></span>

#### <a name="console"></a><span data-ttu-id="1a9f1-894">Console</span><span class="sxs-lookup"><span data-stu-id="1a9f1-894">Console</span></span>
- <span data-ttu-id="1a9f1-895">Correção para a geração do caractere errado como saída para as linhas de cruzamento DEC, originalmente relatadas [aqui](https://www.reddit.com/r/Windows10/comments/6in82t/i_believe_ive_found_the_most_obscure_bug_ever/)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-895">Fix for outputting the wrong character for the crossing-lines DEC, originally reported [here](https://www.reddit.com/r/Windows10/comments/6in82t/i_believe_ive_found_the_most_obscure_bug_ever/)</span></span>
- <span data-ttu-id="1a9f1-896">Correção para nenhum texto de saída sendo exibido na página de código 65001 (utf8)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-896">Fix for no output text being displayed in codepage 65001 (utf8)</span></span>
- <span data-ttu-id="1a9f1-897">Não transfira as alterações feitas aos valores RGB de uma cor para outras partes da paleta na alteração de seleção.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-897">Do not transfer changes made to one color's RGB values to other parts of the palette on selection change.</span></span> <span data-ttu-id="1a9f1-898">Isso tornará a planilha de propriedades do console muito mais fácil de usar.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-898">This will make the console properties sheet a lot easier to use.</span></span>
- <span data-ttu-id="1a9f1-899">Ctrl + S parece não funcionar corretamente</span><span class="sxs-lookup"><span data-stu-id="1a9f1-899">Ctrl+S doesn't appear to work correctly</span></span>
- <span data-ttu-id="1a9f1-900">Sem negrito/sem esmaecimento totalmente ausentes dos códigos de escape ANSI [GH 2174]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-900">Un-Bold/-Dim completely absent from ANSI escape codes [GH 2174]</span></span>
- <span data-ttu-id="1a9f1-901">O console não dá suporte corretamente a temas de cor Vim [GH 1706]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-901">Console doesn't correctly support Vim color themes [GH 1706]</span></span>
- <span data-ttu-id="1a9f1-902">Não é possível colar determinados caracteres [GH 2149]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-902">Cannot paste particular characters [GH 2149]</span></span>
- <span data-ttu-id="1a9f1-903">O redimensionamento de refluxo interage de acordo com o redimensionamento de uma janela do Bash quando as coisas estão na linha de comando/edição [GH ConEmu 1123]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-903">Reflow resize interacts strangely with resizing a bash window when stuff is on the edit/command line [GH ConEmu 1123]</span></span>
- <span data-ttu-id="1a9f1-904">Ctrl + L deixa a tela suja [GH 1978]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-904">Ctrl-L leaves the screen dirty [GH 1978]</span></span>
- <span data-ttu-id="1a9f1-905">Bug de renderização do console ao exibir VT em HDPI [GH 1907]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-905">Console rendering bug when displaying VT on HDPI [GH 1907]</span></span>
- <span data-ttu-id="1a9f1-906">Caracteres japoneses parecem estranhos com o caractere Unicode U+30FB [GH 2146]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-906">Japansese characters look strange with Unicode Character U+30FB [GH 2146]</span></span>
- <span data-ttu-id="1a9f1-907">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-907">Additional improvements and bug fixes</span></span>

</br>

## <a name="build-16237"></a><span data-ttu-id="1a9f1-908">Build 16237</span><span class="sxs-lookup"><span data-stu-id="1a9f1-908">Build 16237</span></span>

<span data-ttu-id="1a9f1-909">Para obter informações gerais do Windows sobre o Build 16237, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/07/07/announcing-windows-10-insider-preview-build-16237-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-909">For general Windows information on build 16237 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/07/07/announcing-windows-10-insider-preview-build-16237-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-910">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-910">Fixed</span></span>
- <span data-ttu-id="1a9f1-911">Usar atributos padrão para arquivos sem EAs em lxfs (root, root, 0000)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-911">Use default attributes for files without EAs in lxfs (root, root, 0000)</span></span>
- <span data-ttu-id="1a9f1-912">Adicionado suporte para distribuições que usam atributos estendidos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-912">Added support for distributions that use extended attributes</span></span>
- <span data-ttu-id="1a9f1-913">Correção do preenchimento das entradas retornadas por getdents e getdents64</span><span class="sxs-lookup"><span data-stu-id="1a9f1-913">Fix padding for entries returned by getdents and getdents64</span></span>
- <span data-ttu-id="1a9f1-914">Correção da verificação de permissões para a chamada do sistema shmctl SHM_STAT [GH 2068]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-914">Fix permissions check for the shmctl SHM_STAT system call [GH 2068]</span></span>
- <span data-ttu-id="1a9f1-915">Corrigido o estado de epoll inicial incorreto para ttys [GH 2231]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-915">Fixed incorrect initial epoll state for ttys [GH 2231]</span></span>
- <span data-ttu-id="1a9f1-916">Correção do DrvFs readdir não retornando todas as entradas [GH 2077]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-916">Fix DrvFs readdir not returning all entries [GH 2077]</span></span>
- <span data-ttu-id="1a9f1-917">Correção do LxFs readdir quando os arquivos estão desvinculados [GH 2077]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-917">Fix LxFs readdir when files are unlinked [GH 2077]</span></span>
- <span data-ttu-id="1a9f1-918">Permissão para que arquivos do DrvFs não vinculados sejam reabertos por meio do procfs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-918">Allow unlinked drvfs files to be reopened through procfs</span></span>
- <span data-ttu-id="1a9f1-919">Substituição da chave do Registro global adicionada para desabilitar os recursos do WSL (interop/montagem de unidade)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-919">Added global registry key override for disabling WSL features (interop / drive mounting)</span></span>
- <span data-ttu-id="1a9f1-920">Correção da contagem de blocos incorretos em "stat" para o DrvFs (e o LxFs) [GH 1894]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-920">Fix incorrect block count in "stat" for DrvFs (and LxFs) [GH 1894]</span></span>
- <span data-ttu-id="1a9f1-921">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-921">Additional improvements and bug fixes</span></span>

</br>

## <a name="build-16232"></a><span data-ttu-id="1a9f1-922">Build 16232</span><span class="sxs-lookup"><span data-stu-id="1a9f1-922">Build 16232</span></span>

<span data-ttu-id="1a9f1-923">Para obter informações gerais do Windows sobre o Build 16232, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/06/28/announcing-windows-10-insider-preview-build-16232-pc-build-15228-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-923">For general Windows information on build 16232 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/06/28/announcing-windows-10-insider-preview-build-16232-pc-build-15228-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-924">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-924">Fixed</span></span>
- <span data-ttu-id="1a9f1-925">Nenhuma alteração relacionada ao WSL nesta versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-925">No WSL related changes in this release.</span></span>

</br>

## <a name="build-16226"></a><span data-ttu-id="1a9f1-926">Build 16226</span><span class="sxs-lookup"><span data-stu-id="1a9f1-926">Build 16226</span></span>

<span data-ttu-id="1a9f1-927">Para obter informações gerais do Windows sobre o Build 16226, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/06/21/announcing-windows-10-insider-preview-build-16226-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-927">For general Windows information on build 16226 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/06/21/announcing-windows-10-insider-preview-build-16226-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-928">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-928">Fixed</span></span>
- <span data-ttu-id="1a9f1-929">suporte a syscalls relacionadas a xattr (getxattr, setxattr, listxattr e removexattr).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-929">xattr related syscalls support (getxattr, setxattr, listxattr, removexattr).</span></span>
- <span data-ttu-id="1a9f1-930">suporte a security.capablity xattr.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-930">security.capablity xattr support.</span></span>
- <span data-ttu-id="1a9f1-931">Compatibilidade aprimorada com determinados sistemas de arquivos e filtros, incluindo servidores SMB não MS.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-931">Improved compatibility with certain file systems and filters, including non-MS SMB servers.</span></span> <span data-ttu-id="1a9f1-932">[GH 1952]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-932">[GH #1952]</span></span>
- <span data-ttu-id="1a9f1-933">Suporte aprimorado para espaços reservados do OneDrive, espaços reservados do GVFS e arquivos compactados do SO Compacto.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-933">Improved support for OneDrive placeholders, GVFS placeholders, and Compact OS compressed files.</span></span>
- <span data-ttu-id="1a9f1-934">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-934">Additional improvements and bug fixes</span></span>

</br>

## <a name="build-16215"></a><span data-ttu-id="1a9f1-935">Build 16215</span><span class="sxs-lookup"><span data-stu-id="1a9f1-935">Build 16215</span></span>

<span data-ttu-id="1a9f1-936">Para obter informações gerais do Windows sobre o Build 16215, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/06/08/announcing-windows-10-insider-preview-build-16215-pc-build-15222-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-936">For general Windows information on build 16215 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/06/08/announcing-windows-10-insider-preview-build-16215-pc-build-15222-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-937">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-937">Fixed</span></span>
- <span data-ttu-id="1a9f1-938">O WSL não exige mais o modo de desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-938">WSL no longer requires developer mode.</span></span>
- <span data-ttu-id="1a9f1-939">Suporte a junções de diretório no DrvFs.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-939">Support directory junctions in drvfs.</span></span>
- <span data-ttu-id="1a9f1-940">Manipulação da desinstalação de pacotes appx de distribuição do WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-940">Handle uninstalling of WSL distribution appx packages.</span></span>
- <span data-ttu-id="1a9f1-941">Atualização do procfs para mostrar mapeamentos privados e compartilhados.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-941">Update procfs to show private and shared mappings.</span></span>
- <span data-ttu-id="1a9f1-942">Adição de capacidade para o wslconfig.exe limpar as distribuições parcialmente instaladas ou desinstaladas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-942">Add ability for wslconfig.exe to clean up distributions that are partially installed or uninstalled.</span></span>
- <span data-ttu-id="1a9f1-943">Adicionado suporte para IP_MTU_DISCOVER para soquetes TCP.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-943">Added support for IP_MTU_DISCOVER for TCP sockets.</span></span> <span data-ttu-id="1a9f1-944">[GH 1639, 2115, 2205]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-944">[GH 1639, 2115, 2205]</span></span>
- <span data-ttu-id="1a9f1-945">Inferência da família de protocolos para rotas para AF_INADDR.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-945">Infer protocol family for routes to AF_INADDR.</span></span>
- <span data-ttu-id="1a9f1-946">Aprimoramentos de dispositivo serial [GH 1929].</span><span class="sxs-lookup"><span data-stu-id="1a9f1-946">Serial device improvements [GH 1929].</span></span>

</br>

## <a name="build-16199"></a><span data-ttu-id="1a9f1-947">Build 16199</span><span class="sxs-lookup"><span data-stu-id="1a9f1-947">Build 16199</span></span>

<span data-ttu-id="1a9f1-948">Para obter informações gerais do Windows sobre o Build 16199, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/05/17/announcing-windows-10-insider-preview-build-16199-pc-build-15215-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-948">For general Windows information on build 16199 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/05/17/announcing-windows-10-insider-preview-build-16199-pc-build-15215-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-949">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-949">Fixed</span></span>
- <span data-ttu-id="1a9f1-950">Nenhuma alteração relacionada ao WSL nestas versões.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-950">No WSL related changes in these releases.</span></span>

</br>

## <a name="build-16193"></a><span data-ttu-id="1a9f1-951">Build 16193</span><span class="sxs-lookup"><span data-stu-id="1a9f1-951">Build 16193</span></span>

<span data-ttu-id="1a9f1-952">Para obter informações gerais do Windows sobre o Build 16193, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/05/11/announcing-windows-10-insider-preview-build-16193-pc-build-15213-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-952">For general Windows information on build 16193 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/05/11/announcing-windows-10-insider-preview-build-16193-pc-build-15213-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-953">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-953">Fixed</span></span>
- <span data-ttu-id="1a9f1-954">Condição de corrida entre o envio de SIGCONT e um encerramento de um grupo de threads [GH 1973]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-954">Race condition between sending SIGCONT and a threadgroup terminating [GH 1973]</span></span>
- <span data-ttu-id="1a9f1-955">alteração de dispositivos tty e pty para relatar FILE_DEVICE_NAMED_PIPE em vez de FILE_DEVICE_CONSOLE [GH 1840]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-955">change tty and pty devices to report FILE_DEVICE_NAMED_PIPE instead of FILE_DEVICE_CONSOLE [GH 1840]</span></span>
- <span data-ttu-id="1a9f1-956">Correção de SSH para IP_OPTIONS</span><span class="sxs-lookup"><span data-stu-id="1a9f1-956">SSH fix for IP_OPTIONS</span></span>
- <span data-ttu-id="1a9f1-957">A montagem do DrvFs foi movida para o daemon init [GH 1862, 1968, 1767, 1933]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-957">Moved DrvFs mounting to init daemon [GH 1862, 1968, 1767, 1933]</span></span>
- <span data-ttu-id="1a9f1-958">Adicionado suporte no DrvFs para os symlinks NT a seguir.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-958">Added support in DrvFs for following NT symlinks.</span></span>

</br>

## <a name="build-16184"></a><span data-ttu-id="1a9f1-959">Build 16184</span><span class="sxs-lookup"><span data-stu-id="1a9f1-959">Build 16184</span></span>

<span data-ttu-id="1a9f1-960">Para obter informações gerais do Windows sobre o Build 16184, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/04/28/announcing-windows-10-insider-preview-build-16184-pc-build-15208-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-960">For general Windows information on build 16184 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/04/28/announcing-windows-10-insider-preview-build-16184-pc-build-15208-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-961">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-961">Fixed</span></span>
- <span data-ttu-id="1a9f1-962">Removida a tarefa de manutenção do pacote apt (lxrun.exe/update)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-962">Removed apt package maintenance task (lxrun.exe /update)</span></span>
- <span data-ttu-id="1a9f1-963">Corrigido problema em que a saída não aparecia nos processos do Windows no Node.js [GH 1840]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-963">Fixed output not showing up in from Windows processes in node.js [GH 1840]</span></span>
- <span data-ttu-id="1a9f1-964">Flexibilização dos requisitos de alinhamento no lxcore [GH 1794]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-964">Relax alignment requirements in lxcore [GH 1794]</span></span>
- <span data-ttu-id="1a9f1-965">Corrigida a manipulação do sinalizador AT_EMPTY_PATH em um número de chamadas do sistema.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-965">Fixed handling of the AT_EMPTY_PATH flag in a numer of system calls.</span></span>
- <span data-ttu-id="1a9f1-966">Corrigido o problema em que a exclusão de arquivos do DrvFs com identificadores abertos fazia com que o arquivo apresentasse comportamento indefinido [GH 544, 966, 1357, 1535, 1615]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-966">Fixed issue where deleting DrvFs files with open handles will cause the file to exhibit undefined behavior [GH 544,966,1357,1535,1615]</span></span>
- <span data-ttu-id="1a9f1-967">O /etc/hosts agora herdará entradas do arquivo de hosts do Windows (%windir%\system32\drivers\etc\hosts) [GH 1495]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-967">/etc/hosts will now inherit entries from the Windows hosts file (%windir%\system32\drivers\etc\hosts) [GH 1495]</span></span>

</br>

## <a name="build-16179"></a><span data-ttu-id="1a9f1-968">Build 16179</span><span class="sxs-lookup"><span data-stu-id="1a9f1-968">Build 16179</span></span>

<span data-ttu-id="1a9f1-969">Para obter informações gerais do Windows sobre o Build 16179, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/04/19/announcing-windows-10-insider-preview-build-16179-pc-build-15205-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-969">For general Windows information on build 16179 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/04/19/announcing-windows-10-insider-preview-build-16179-pc-build-15205-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-970">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-970">Fixed</span></span>
- <span data-ttu-id="1a9f1-971">Nenhuma alteração de WSL nesta semana.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-971">No WSL changes this week.</span></span>

</br>

## <a name="build-16176"></a><span data-ttu-id="1a9f1-972">Build 16176</span><span class="sxs-lookup"><span data-stu-id="1a9f1-972">Build 16176</span></span>

<span data-ttu-id="1a9f1-973">Para obter informações gerais do Windows sobre o Build 16176, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/04/14/announcing-windows-10-insider-preview-build-16176-pc-build-15204-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-973">For general Windows information on build 16176 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/04/14/announcing-windows-10-insider-preview-build-16176-pc-build-15204-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-974">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-974">Fixed</span></span>

- [<span data-ttu-id="1a9f1-975">Suporte serial habilitado</span><span class="sxs-lookup"><span data-stu-id="1a9f1-975">Enabled serial support</span></span>](/archive/blogs/wsl/serial-support-on-the-windows-subsystem-for-linux)
- <span data-ttu-id="1a9f1-976">Adicionada opção de soquete IP IP_OPTIONS [GH 1116]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-976">Added IP socket option IP_OPTIONS [GH 1116]</span></span>
- <span data-ttu-id="1a9f1-977">Função pwritev implementada (ao carregar o arquivo para nginx/PHP-FPM) [GH 1506]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-977">Implemented pwritev function (while uploading file to nginx/PHP-FPM) [GH 1506]</span></span>
- <span data-ttu-id="1a9f1-978">Adicionadas opções de soquete IP IP_MULTICAST_IF e IPV6_MULTICAST_IF [GH 990]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-978">Added IP socket options IP_MULTICAST_IF & IPV6_MULTICAST_IF [GH 990]</span></span>
- <span data-ttu-id="1a9f1-979">Suporte para as opções de soquete IP_MULTICAST_LOOP e IPV6_MULTICAST_LOOP [GH 1678]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-979">Support for socket option IP_MULTICAST_LOOP & IPV6_MULTICAST_LOOP [GH 1678]</span></span>
- <span data-ttu-id="1a9f1-980">Adicionada a opção de soquete IP(V6)_MTU para node, traceroute, dig, nslookup e host de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-980">Added IP(V6)_MTU socket option for apps node, traceroute, dig, nslookup, host</span></span>
- <span data-ttu-id="1a9f1-981">Adicionada a opção de soquete IP IPV6_UNICAST_HOPS</span><span class="sxs-lookup"><span data-stu-id="1a9f1-981">Added IP socket option IPV6_UNICAST_HOPS</span></span>
- [<span data-ttu-id="1a9f1-982">Aprimoramentos do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-982">Filesystem Improvements</span></span>](/archive/blogs/wsl/file-system-improvements-to-the-windows-subsystem-for-linux)
    * <span data-ttu-id="1a9f1-983">Permitir a montagem de caminhos UNC</span><span class="sxs-lookup"><span data-stu-id="1a9f1-983">Allow mounting of UNC paths</span></span>
    * <span data-ttu-id="1a9f1-984">Habilitar o suporte a CDFS no DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-984">Enable CDFS support in drvfs</span></span>
    * <span data-ttu-id="1a9f1-985">Manipulação correta das permissões para sistemas de arquivos de rede no DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-985">Correctly handle permissions for network file systems in drvfs</span></span>
    * <span data-ttu-id="1a9f1-986">Adição de suporte para unidades remotas ao DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-986">Add support for remote drives to drvfs</span></span>
    * <span data-ttu-id="1a9f1-987">Habilitação do suporte a FAT no DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-987">Enable FAT support in drvfs</span></span>
- <span data-ttu-id="1a9f1-988">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-988">Additional fixes and Improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-989">Resultados do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-989">LTP Results</span></span>
<span data-ttu-id="1a9f1-990">Nenhuma alteração desde 15042</span><span class="sxs-lookup"><span data-stu-id="1a9f1-990">No changes since 15042</span></span>

</br>

## <a name="build-16170"></a><span data-ttu-id="1a9f1-991">Build 16170</span><span class="sxs-lookup"><span data-stu-id="1a9f1-991">Build 16170</span></span>

<span data-ttu-id="1a9f1-992">Para obter informações gerais do Windows sobre o Build 16170, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/04/07/announcing-windows-10-insider-preview-build-16170-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-992">For general Windows information on build 16170 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/04/07/announcing-windows-10-insider-preview-build-16170-pc/).</span></span><br/>

<span data-ttu-id="1a9f1-993">Lançamos uma nova [postagem no blog](/archive/blogs/wsl/testing-the-windows-subsystem-for-linux) discutindo nossos esforços para testar o WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-993">We released a new [blog post](/archive/blogs/wsl/testing-the-windows-subsystem-for-linux) discussing our efforts to test WSL.</span></span>

### <a name="fixed"></a><span data-ttu-id="1a9f1-994">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-994">Fixed</span></span>

- <span data-ttu-id="1a9f1-995">Suporte à opção de soquete IP_ADD_MEMBERSHIP e IPV6_ADD_MEMBERSHIP [GH 1678]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-995">Support socket option IP_ADD_MEMBERSHIP & IPV6_ADD_MEMBERSHIP [GH 1678]</span></span>
- <span data-ttu-id="1a9f1-996">Adição de suporte para PTRACE_OLDSETOPTIONS.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-996">Add support for PTRACE_OLDSETOPTIONS.</span></span> <span data-ttu-id="1a9f1-997">[GH 1692]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-997">[GH 1692]</span></span>
- <span data-ttu-id="1a9f1-998">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-998">Additional fixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-999">Resultados do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-999">LTP Results</span></span>
<span data-ttu-id="1a9f1-1000">Nenhuma alteração desde 15042</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1000">No changes since 15042</span></span>

</br>

## <a name="build-15046-to-windows-10-creators-update"></a><span data-ttu-id="1a9f1-1001">Build 15046 para a Atualização do Windows 10 para Criadores</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1001">Build 15046 to Windows 10 Creators Update</span></span>
<span data-ttu-id="1a9f1-1002">Não há mais correções nem recursos do WSL planejados para inclusão na Atualização do Windows 10 para Criadores.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1002">There are no more WSL fixes or features planned for inclusion in the Creators Update to Windows 10.</span></span> <span data-ttu-id="1a9f1-1003">As notas sobre a versão do WSL serão retomadas nas próximas semanas para as adições direcionadas à próxima atualização importante do Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1003">Release notes for WSL will resume in the coming weeks for additions targeting the next major Windows Update.</span></span> <span data-ttu-id="1a9f1-1004">Para obter informações gerais do Windows sobre o Build 15046 e futuras versões do Insider, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/02/28/announcing-windows-10-insider-preview-build-15046-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1004">For general Windows information on build 15046 and future Insider releases visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/02/28/announcing-windows-10-insider-preview-build-15046-pc/).</span></span> <br/><br/>
 <br/>

## <a name="build-15042"></a><span data-ttu-id="1a9f1-1005">Build 15042</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1005">Build 15042</span></span>

<span data-ttu-id="1a9f1-1006">Para obter informações gerais do Windows sobre o Build 15042, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/02/24/announcing-windows-10-insider-preview-build-15042-pc-build-15043-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1006">For general Windows information on build 15042 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/02/24/announcing-windows-10-insider-preview-build-15042-pc-build-15043-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1007">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1007">Fixed</span></span>

- <span data-ttu-id="1a9f1-1008">Correção de um deadlock ao remover um caminho que termina em ".."</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1008">Fix for a deadlock when removing a path ending in ".."</span></span>
- <span data-ttu-id="1a9f1-1009">Corrigido um problema em que FIONBIO não retornava 0 em caso de êxito [GH 1683]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1009">Fixed an issue where FIONBIO not returning 0 on success [GH 1683]</span></span>
- <span data-ttu-id="1a9f1-1010">Corrigido um problema com leituras de comprimento zero de soquetes de datagrama inet</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1010">Fixed issue with zero-length reads of inet datagram sockets</span></span>
- <span data-ttu-id="1a9f1-1011">Correção de um possível deadlock devido à condição de corrida na pesquisa de inode do DrvFs [GH 1675]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1011">Fix possible deadlock due to race condition in drvfs inode lookup [GH 1675]</span></span>
- <span data-ttu-id="1a9f1-1012">Suporte estendido para dados complementares de soquete Unix; SCM_CREDENTIALS e SCM_RIGHTS [GH 514, 613, 1326]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1012">Extended support for unix socket ancillary data; SCM_CREDENTIALS and SCM_RIGHTS [GH 514, 613, 1326]</span></span>
- <span data-ttu-id="1a9f1-1013">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1013">Additional fixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1014">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1014">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1015">Número de testes aprovados: 737</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1015">Number of Passing Test: 737</span></span></br>
<span data-ttu-id="1a9f1-1016">Número de não aprovados (com falha, ignorados, etc.): 255</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1016">Number of non-Passing (failing, skipped, etc…): 255</span></span>

</br>

## <a name="build-15031"></a><span data-ttu-id="1a9f1-1017">Build 15031</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1017">Build 15031</span></span>

<span data-ttu-id="1a9f1-1018">Para obter informações gerais do Windows sobre o Build 15031, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/02/08/announcing-windows-10-insider-preview-build-15031-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1018">For general Windows information on build 15031 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/02/08/announcing-windows-10-insider-preview-build-15031-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1019">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1019">Fixed</span></span>

- <span data-ttu-id="1a9f1-1020">Corrigido um bug em que time(2) se comportava de maneira incorreta esporadicamente.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1020">Fixed a bug where time(2) would sporadically misbehave.</span></span>
- <span data-ttu-id="1a9f1-1021">Corrigido um problema em que syscalls \*SIGPROCMASK poderiam corromper a máscara de sinal.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1021">Fixed and issue where \*SIGPROCMASK syscalls could corrupt signal mask.</span></span>
- <span data-ttu-id="1a9f1-1022">Agora, retorne o comprimento de linha de comando completo na notificação de criação de processo do WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1022">Now return full command line length in WSL process creation notification.</span></span> <span data-ttu-id="1a9f1-1023">[GH 1632]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1023">[GH 1632]</span></span>
- <span data-ttu-id="1a9f1-1024">O WSL agora relata a saída do thread por meio de ptrace para travamentos do GDB.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1024">WSL now reports thread exit through ptrace for GDB hangs.</span></span> <span data-ttu-id="1a9f1-1025">[GH 1196]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1025">[GH 1196]</span></span>
- <span data-ttu-id="1a9f1-1026">Corrigido o bug em que ptys travam após E/S intensa de tmux.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1026">Fixed bug where ptys would hang after heavy tmux IO.</span></span> <span data-ttu-id="1a9f1-1027">[GH 1358]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1027">[GH 1358]</span></span>
- <span data-ttu-id="1a9f1-1028">Correção da validação de tempo limite em muitas chamadas do sistema (futex, semtimedop, ppoll, sigtimedwait, itimer, timer_create)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1028">Fixed timeout validation in many system calls (futex, semtimedop, ppoll, sigtimedwait, itimer, timer_create)</span></span>
- <span data-ttu-id="1a9f1-1029">Adicionado suporte a eventfd EFD_SEMAPHORE [GH 452]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1029">Added eventfd EFD_SEMAPHORE support [GH 452]</span></span>
- <span data-ttu-id="1a9f1-1030">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1030">Additional fixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1031">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1031">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1032">Número de testes aprovados: 737</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1032">Number of Passing Test: 737</span></span></br>
<span data-ttu-id="1a9f1-1033">Número de não aprovados (com falha, ignorados, etc.): 255</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1033">Number of non-Passing (failing, skipped, etc…): 255</span></span> </br>
[<span data-ttu-id="1a9f1-1034">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1034">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15031)<br/>

<br/>

## <a name="build-15025"></a><span data-ttu-id="1a9f1-1035">Build 15025</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1035">Build 15025</span></span>

<span data-ttu-id="1a9f1-1036">Para obter informações gerais do Windows sobre o Build 15025, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/02/01/announcing-windows-10-insider-preview-build-15025-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1036">For general Windows information on build 15025 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/02/01/announcing-windows-10-insider-preview-build-15025-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1037">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1037">Fixed</span></span>

- <span data-ttu-id="1a9f1-1038">Correção do bug que interrompeu o grep 2.27 [GH 1578]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1038">Fix for bug that broke grep 2.27 [GH 1578]</span></span>
- <span data-ttu-id="1a9f1-1039">Implementado o sinalizador EFD_SEMAPHORE para a syscall eventfd2 [GH 452]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1039">Implemented EFD_SEMAPHORE flag for eventfd2 syscall [GH 452]</span></span>
- <span data-ttu-id="1a9f1-1040">Implementado /proc/[pid]/net/ipv6_route [GH 1608]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1040">Implemented /proc/[pid]/net/ipv6_route [GH 1608]</span></span>
- <span data-ttu-id="1a9f1-1041">Suporte de E/S controlada por sinal para soquetes de fluxo do Unix [GH 393, 68]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1041">Signal driven IO support for unix stream sockets [GH 393, 68]</span></span>
- <span data-ttu-id="1a9f1-1042">Suporte a F_GETPIPE_SZ e F_SETPIPE_SZ [GH 1012]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1042">Support F_GETPIPE_SZ and F_SETPIPE_SZ [GH 1012]</span></span>
- <span data-ttu-id="1a9f1-1043">Implementação da syscall recvmmsg() [GH 1531]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1043">Implement recvmmsg() syscall [GH 1531]</span></span>
- <span data-ttu-id="1a9f1-1044">Corrigido o bug em que epoll_wait() não estava aguardando [GH 1609]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1044">Fixed bug where epoll_wait() wasn't waiting [GH 1609]</span></span>
- <span data-ttu-id="1a9f1-1045">Implementação de /proc/version_signature</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1045">Implement /proc/version_signature</span></span>
- <span data-ttu-id="1a9f1-1046">Tee syscall agora retornará uma falha se os dois descritores de arquivo se referirem ao mesmo pipe</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1046">Tee syscall now returns failure if both file descriptors refer to the same pipe</span></span>
- <span data-ttu-id="1a9f1-1047">Implementação do comportamento correto para SO_PEERCRED para soquetes Unix</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1047">Implemented correct behavior for SO_PEERCRED for Unix sockets</span></span>
- <span data-ttu-id="1a9f1-1048">Corrigido o tratamento de erro de parâmetro inválido da syscall tkill</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1048">Fixed tkill syscall invalid parameter handling</span></span>
- <span data-ttu-id="1a9f1-1049">Alterações para aumentar o desempenho do DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1049">Changes to increase the preformace of drvfs</span></span>
- <span data-ttu-id="1a9f1-1050">Correção secundária para bloqueio de E/S do Ruby</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1050">Minor fix for Ruby IO blocking</span></span>
- <span data-ttu-id="1a9f1-1051">Corrigido o erro em que recvmsg() retornava EINVAL para o sinalizador MSG_DONTWAIT para soquetes inet [GH 1296]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1051">Fixed recvmsg() returning EINVAL for the MSG_DONTWAIT flag for inet sockets [GH 1296]</span></span>
- <span data-ttu-id="1a9f1-1052">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1052">Additional fixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1053">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1053">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1054">Número de testes aprovados: 732</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1054">Number of Passing Test: 732</span></span></br>
<span data-ttu-id="1a9f1-1055">Número de não aprovados (com falha, ignorados, etc.): 255</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1055">Number of non-Passing (failing, skipped, etc…): 255</span></span> </br>
[<span data-ttu-id="1a9f1-1056">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1056">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15025)<br/>

<br/>

## <a name="build-15019"></a><span data-ttu-id="1a9f1-1057">Build 15019</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1057">Build 15019</span></span>

<span data-ttu-id="1a9f1-1058">Para obter informações gerais do Windows sobre o Build 15019, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/01/27/announcing-windows-10-insider-preview-build-15019-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1058">For general Windows information on build 15019 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/01/27/announcing-windows-10-insider-preview-build-15019-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1059">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1059">Fixed</span></span>

- <span data-ttu-id="1a9f1-1060">Correção do bug que reportava incorretamente o uso da CPU em procfs para ferramentas como htop (GH 823, 945, 971)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1060">Fixed bug that incorrectly reported CPU usage in procfs for tools like htop (GH 823, 945, 971)</span></span>
- <span data-ttu-id="1a9f1-1061">Ao chamar open() com O_TRUNC em um arquivo existente, INotifyPropertyChanged agora gera IN_MODIFY antes de IN_OPEN</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1061">When calling open() with O_TRUNC on an existing file inotify now generates IN_MODIFY before IN_OPEN</span></span>
- <span data-ttu-id="1a9f1-1062">Correções para getsockopt SO_ERROR de soquetes Unix para habilitar postgress [GH 61, 1354]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1062">Fixes to unix socket getsockopt SO_ERROR to enable postgress [GH 61, 1354]</span></span>
- <span data-ttu-id="1a9f1-1063">Implementação de /proc/sys/net/Core/SOMAXCONN para a linguagem GO</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1063">Implement /proc/sys/net/core/somaxconn for the GO language</span></span>
- <span data-ttu-id="1a9f1-1064">A tarefa de atualização em segundo plano do pacote apt-get agora executa oculta</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1064">Apt-get package update background task now runs hidden from view</span></span>
- <span data-ttu-id="1a9f1-1065">Limpeza do escopo do localhost IPv6 (falha de Spring-Framework(Java)).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1065">Clear scope for ipv6 localhost (Spring-Framework(Java) failure).</span></span>
- <span data-ttu-id="1a9f1-1066">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1066">Additional fixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1067">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1067">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1068">Número de testes aprovados: 714</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1068">Number of Passing Test: 714</span></span> </br>
<span data-ttu-id="1a9f1-1069">Número de não aprovados (com falha, ignorados, etc.): 249</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1069">Number of non-Passing (failing, skipped, etc…): 249</span></span> </br>
[<span data-ttu-id="1a9f1-1070">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1070">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15019)<br/>

<br/>

## <a name="build-15014"></a><span data-ttu-id="1a9f1-1071">Build 15014</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1071">Build 15014</span></span>

<span data-ttu-id="1a9f1-1072">Para obter informações gerais do Windows sobre o Build 15014, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/01/19/announcing-windows-10-insider-preview-build-15014-for-pc-and-mobile-hello-windows-insiders-today-we-are-excited-to-be-releasing-windows-10-insider-preview-build-15014-for-pc-and-mobile).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1072">For general Windows information on build 15014 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/01/19/announcing-windows-10-insider-preview-build-15014-for-pc-and-mobile-hello-windows-insiders-today-we-are-excited-to-be-releasing-windows-10-insider-preview-build-15014-for-pc-and-mobile).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1073">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1073">Fixed</span></span>

- <span data-ttu-id="1a9f1-1074">Ctrl + C agora funciona conforme esperado</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1074">Ctrl+C now works as intended</span></span>
- <span data-ttu-id="1a9f1-1075">htop e ps auxw agora mostram a utilização de recursos correta (GH 516)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1075">htop and ps auxw now show correct resource utilization (GH #516)</span></span>
- <span data-ttu-id="1a9f1-1076">Conversão básica de exceções NT para sinais.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1076">Basic translation of NT exceptions to signals.</span></span> <span data-ttu-id="1a9f1-1077">(GH 513)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1077">(GH #513)</span></span>
- <span data-ttu-id="1a9f1-1078">agora, ao ficar sem espaço, fallocate falha com ENOSPC em vez de EINVAL (GH 1571)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1078">fallocate now fails with ENOSPC  when running out of space instead of EINVAL (GH #1571)</span></span>
- <span data-ttu-id="1a9f1-1079">Adicionado /proc/sys/kernel/sem.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1079">Added /proc/sys/kernel/sem.</span></span>
- <span data-ttu-id="1a9f1-1080">Implementadas as chamadas de sistema semop e semtimedop</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1080">Implemented semop and semtimedop system calls</span></span>
- <span data-ttu-id="1a9f1-1081">Corrigidos os erros de nslookup com as opções de soquete IP_RECVTOS e IPV6_RECVTCLASS (GH 69)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1081">Fixed nslookup errors with IP_RECVTOS & IPV6_RECVTCLASS socket option (GH 69)</span></span>
- <span data-ttu-id="1a9f1-1082">Suporte para as opções de soquete IP_RECVTTL e IPV6_RECVHOPLIMIT</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1082">Support for socket options IP_RECVTTL and IPV6_RECVHOPLIMIT</span></span>
- <span data-ttu-id="1a9f1-1083">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1083">Additional fixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1084">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1084">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1085">Número de testes aprovados: 709</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1085">Number of Passing Test: 709</span></span> </br>
<span data-ttu-id="1a9f1-1086">Número de não aprovados (com falha, ignorados, etc.): 255</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1086">Number of non-Passing (failing, skipped, etc…): 255</span></span> </br>
[<span data-ttu-id="1a9f1-1087">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1087">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15014)<br/>

### <a name="syscall-summary"></a><span data-ttu-id="1a9f1-1088">Resumo das syscalls</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1088">Syscall Summary</span></span>
<span data-ttu-id="1a9f1-1089">Total de syscalls: 384</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1089">Total Syscalls: 384</span></span> </br>
<span data-ttu-id="1a9f1-1090">Total de implementadas: 235</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1090">Total Implemented: 235</span></span> </br>
<span data-ttu-id="1a9f1-1091">Total de fragmentadas: 22</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1091">Total Stubbed: 22</span></span> </br>
<span data-ttu-id="1a9f1-1092">Total de não implementadas: 127</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1092">Total Unimplemented: 127</span></span> </br>
[<span data-ttu-id="1a9f1-1093">Detalhamento</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1093">Detailed Breakdown</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15014/Syscalls.txt)<br/>

<br/>

## <a name="build-15007"></a><span data-ttu-id="1a9f1-1094">Build 15007</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1094">Build 15007</span></span>

<span data-ttu-id="1a9f1-1095">Para obter informações gerais do Windows sobre o Build 15007, visite o [blog do Windows]( https://blogs.windows.com/windowsexperience/2017/01/12/announcing-windows-10-insider-preview-build-15007-pc-mobile).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1095">For general Windows information on build 15007 visit the [Windows Blog]( https://blogs.windows.com/windowsexperience/2017/01/12/announcing-windows-10-insider-preview-build-15007-pc-mobile).</span></span><br/>


### <a name="known-issue"></a><span data-ttu-id="1a9f1-1096">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1096">Known Issue</span></span>

- <span data-ttu-id="1a9f1-1097">Há um bug conhecido em que o console não reconhece alguma entrada Ctrl + <key>.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1097">There is a known bug where the console does not recognize some Ctrl + <key> input.</span></span>  <span data-ttu-id="1a9f1-1098">Isso inclui o comando Ctrl + C, que funcionará como um pressionamento comum da tecla 'C'.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1098">This includes the ctrl-c command which will act as a normal 'c' keypress.</span></span>

  - <span data-ttu-id="1a9f1-1099">Solução alternativa: Mapeamento de uma tecla alternativa para Ctrl + C.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1099">Workaround: Map an alternate key to Ctrl+C.</span></span> <span data-ttu-id="1a9f1-1100">Por exemplo, para mapear Ctrl + K para Ctrl + C, faça isto: `stty intr \^k`.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1100">For example, to map Ctrl+K to Ctrl+C do: `stty intr \^k`.</span></span>  <span data-ttu-id="1a9f1-1101">Este mapeamento é por terminal e precisará ser realizado *toda* vez que o Bash for inicializado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1101">This mapping is per terminal and will have to be done *every* time bash is launched.</span></span> <span data-ttu-id="1a9f1-1102">Os usuários podem explorar a opção para incluir isto no `.bashrc` deles</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1102">Users can explore the option to include this in their `.bashrc`</span></span>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1103">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1103">Fixed</span></span>

- <span data-ttu-id="1a9f1-1104">Corrigido o problema em que executar o WSL consumiria 100% de um núcleo de CPU</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1104">Corrected the issue where running WSL would consume 100% of a CPU core</span></span>
- <span data-ttu-id="1a9f1-1105">A opção de soquete IP_PKTINFO, IPV6_RECVPKTINFO agora é compatível.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1105">Socket option IP_PKTINFO, IPV6_RECVPKTINFO now supported.</span></span> <span data-ttu-id="1a9f1-1106">(GH 851, 987)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1106">(GH #851, 987)</span></span>
- <span data-ttu-id="1a9f1-1107">Truncamento do endereço físico do adaptador de rede para 16 bytes em lxcore (GH 1452, 1414, 1343, 468, 308)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1107">Truncate network interface physical address to 16 bytes in lxcore (GH #1452, 1414, 1343, 468, 308)</span></span>
- <span data-ttu-id="1a9f1-1108">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1108">Additional fixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1109">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1109">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1110">Número de testes aprovados: 709</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1110">Number of Passing Test: 709</span></span> </br>
<span data-ttu-id="1a9f1-1111">Número de não aprovados (com falha, ignorados, etc.): 255</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1111">Number of non-Passing (failing, skipped, etc…): 255</span></span> </br>
[<span data-ttu-id="1a9f1-1112">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1112">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15007)<br/>

<br/>

## <a name="build-15002"></a><span data-ttu-id="1a9f1-1113">Build 15002</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1113">Build 15002</span></span>

<span data-ttu-id="1a9f1-1114">Para obter informações gerais do Windows sobre o Build 15002, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/01/09/announcing-windows-10-insider-preview-build-15002-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1114">For general Windows information on build 15002 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2017/01/09/announcing-windows-10-insider-preview-build-15002-pc/).</span></span><br/>


### <a name="known-issue"></a><span data-ttu-id="1a9f1-1115">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1115">Known Issue</span></span>

<span data-ttu-id="1a9f1-1116">Dois problemas conhecidos:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1116">Two known issues:</span></span>
- <span data-ttu-id="1a9f1-1117">Há um bug conhecido em que o console não reconhece alguma entrada Ctrl + <key>.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1117">There is a known bug where the console does not recognize some Ctrl + <key> input.</span></span>  <span data-ttu-id="1a9f1-1118">Isso inclui o comando Ctrl + C, que funcionará como um pressionamento comum da tecla 'C'.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1118">This includes the ctrl-c command which will act as a normal 'c' keypress.</span></span>

  - <span data-ttu-id="1a9f1-1119">Solução alternativa: Mapeamento de uma tecla alternativa para Ctrl + C.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1119">Workaround: Map an alternate key to Ctrl+C.</span></span> <span data-ttu-id="1a9f1-1120">Por exemplo, para mapear Ctrl + K para Ctrl + C, faça isto: `stty intr \^k`.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1120">For example, to map Ctrl+K to Ctrl+C do: `stty intr \^k`.</span></span>  <span data-ttu-id="1a9f1-1121">Este mapeamento é por terminal e precisará ser realizado *toda* vez que o Bash for inicializado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1121">This mapping is per terminal and will have to be done *every* time bash is launched.</span></span> <span data-ttu-id="1a9f1-1122">Os usuários podem explorar a opção para incluir isto no `.bashrc` deles</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1122">Users can explore the option to include this in their `.bashrc`</span></span>

- <span data-ttu-id="1a9f1-1123">Enquanto o WSL estiver em execução, um thread do sistema consumirá 100% de um núcleo de CPU.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1123">While WSL is running a system thread will consume 100% of a CPU core.</span></span>  <span data-ttu-id="1a9f1-1124">A causa raiz foi resolvida e corrigida internamente.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1124">The root cause has been addressed and fixed internally.</span></span>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1125">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1125">Fixed</span></span>

- <span data-ttu-id="1a9f1-1126">Todas as sessões do Bash agora devem ser criadas no mesmo nível de permissão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1126">All bash sessions must now be created at the same permission level.</span></span>  <span data-ttu-id="1a9f1-1127">Qualquer tentativa de iniciar uma sessão em um nível diferente será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1127">Attempting to start a session at a different level will be blocked.</span></span>  <span data-ttu-id="1a9f1-1128">Isso significa que consoles com e sem privilégios de administrador não podem executar simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1128">This means admin and non-admin consoles cannot run at the same time.</span></span> <span data-ttu-id="1a9f1-1129">(GH 626)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1129">(GH #626)</span></span>
<br/>
- <span data-ttu-id="1a9f1-1130">Implementadas as mensagens NETLINK_ROUTE a seguir (requer administrador do Windows)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1130">Implemented the following NETLINK_ROUTE messages (requires Windows admin)</span></span>
     - <span data-ttu-id="1a9f1-1131">RTM_NEWADDR (dá suporte a `ip addr add`)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1131">RTM_NEWADDR (supports `ip addr add`)</span></span>
     - <span data-ttu-id="1a9f1-1132">RTM_NEWROUTE (dá suporte a `ip route add`)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1132">RTM_NEWROUTE (supports `ip route add`)</span></span>
     - <span data-ttu-id="1a9f1-1133">RTM_DELADDR (dá suporte a `ip addr del`)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1133">RTM_DELADDR (supports `ip addr del`)</span></span>
     - <span data-ttu-id="1a9f1-1134">RTM_DELROUTE (dá suporte a `ip route del`)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1134">RTM_DELROUTE (supports `ip route del`)</span></span>
- <span data-ttu-id="1a9f1-1135">A verificação de tarefa agendada para que os pacotes sejam atualizados não será mais executada em uma conexão limitada (GH #1371)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1135">Scheduled task checking for packages to update will no longer run on a metered connection (GH #1371)</span></span>
- <span data-ttu-id="1a9f1-1136">Corrigido o erro em que o pipe fica preso, ou seja, bash -c "ls -alR /" | bash -c "cat" (GH 1214)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1136">Fixed error where piping gets stuck i.e. bash -c "ls -alR /" | bash -c "cat" (GH #1214)</span></span>
- <span data-ttu-id="1a9f1-1137">Implementada a opção de soquete TCP_KEEPCNT (GH 843)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1137">Implemented TCP_KEEPCNT socket option (GH #843)</span></span>
- <span data-ttu-id="1a9f1-1138">Implementada a opção de soquete IP_MTU_DISCOVER INET (GH 720, 717, 170, 69)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1138">Implemented IP_MTU_DISCOVER INET socket option (GH #720, 717, 170, 69)</span></span>
- <span data-ttu-id="1a9f1-1139">Funcionalidade herdada removida para executar binários NT por meio de init com a pesquisa de caminho de NT.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1139">Removed legacy functionality to run NT binaries from init with NT path lookup.</span></span> <span data-ttu-id="1a9f1-1140">(GH 1325)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1140">(GH #1325)</span></span>
- <span data-ttu-id="1a9f1-1141">Correção do modo de /dev/kmsg para permitir o acesso de grupo/outro acesso de leitura (0644) (GH 1321)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1141">Fix mode of /dev/kmsg to allow group / other read access (0644) (GH #1321)</span></span>
- <span data-ttu-id="1a9f1-1142">Implementado /proc/sys/kernel/random/uuid (GH 1092)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1142">Implemented /proc/sys/kernel/random/uuid  (GH #1092)</span></span>
- <span data-ttu-id="1a9f1-1143">Erro corrigido em que a hora de início do processo era mostrada como no ano 2432 (GH 974)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1143">Corrected error where process start time was showing as year 2432 (GH #974)</span></span>
- <span data-ttu-id="1a9f1-1144">Variável de ambiente TERM padrão alternada para xterm-256color (GH 1446)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1144">Switched default TERM environment variable to xterm-256color (GH #1446)</span></span>
- <span data-ttu-id="1a9f1-1145">Modificado o modo como a confirmação do processo é calculada durante o fork do processo.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1145">Modified the way that process commit is calculated during process fork.</span></span> <span data-ttu-id="1a9f1-1146">(GH 1286)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1146">(GH #1286)</span></span>
- <span data-ttu-id="1a9f1-1147">Implementado /proc/sys/vm/overcommit_memory.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1147">Implemented /proc/sys/vm/overcommit_memory.</span></span> <span data-ttu-id="1a9f1-1148">(GH 1286)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1148">(GH #1286)</span></span>
- <span data-ttu-id="1a9f1-1149">Implementado /proc/net/route file (GH 69)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1149">Implemented /proc/net/route file (GH #69)</span></span>
- <span data-ttu-id="1a9f1-1150">Corrigido um erro em que o nome do atalho era localizado incorretamente (GH 696)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1150">Fixed error where shortcut name was incorrectly localized (GH #696)</span></span>
- <span data-ttu-id="1a9f1-1151">Corrigida a lógica de análise de ELF que estava validando incorretamente os cabeçalhos de programa e precisava ser menor que (ou igual a) PATH_MAX.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1151">Fixed elf parsing logic that is incorrectly validating the program headers must be less than (or equal to) PATH_MAX.</span></span> <span data-ttu-id="1a9f1-1152">(GH 1048)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1152">(GH #1048)</span></span>
- <span data-ttu-id="1a9f1-1153">Implementado retorno de chamada statfs para procfs, sysfs, cgroupfs e binfmtfs (GH 1378)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1153">Implemented statfs callback for procfs, sysfs, cgroupfs, and binfmtfs (GH #1378)</span></span>
- <span data-ttu-id="1a9f1-1154">Correção das janelas AptPackageIndexUpdate que não eram fechadas (GH 1184, também abordado em GH 1193)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1154">Fixed AptPackageIndexUpdate windows that won't close (GH #1184, also discussed in GH #1193)</span></span>
- <span data-ttu-id="1a9f1-1155">Adicionado suporte a ADDR_NO_RANDOMIZE de personalidade de ASLR.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1155">Added ASLR personality  ADDR_NO_RANDOMIZE support.</span></span> <span data-ttu-id="1a9f1-1156">(GH 1148, 1128)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1156">(GH #1148, 1128)</span></span>
- <span data-ttu-id="1a9f1-1157">Melhoria de PTRACE_GETSIGINFO e SIGSEGV para rastreamentos de pilha gdb apropriados durante o AV (GH #875)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1157">Improved PTRACE_GETSIGINFO, SIGSEGV, for proper gdb stack traces during AV (GH #875)</span></span>
- <span data-ttu-id="1a9f1-1158">A análise de ELF não falha mais para binários patchelf.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1158">Elf parsing no longer fails for patchelf binaries.</span></span> <span data-ttu-id="1a9f1-1159">(GH 471)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1159">(GH #471)</span></span>
- <span data-ttu-id="1a9f1-1160">DNS de VPN propagado para /etc/resolv.conf (GH 416, 1350)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1160">VPN DNS propagated to /etc/resolv.conf (GH #416, 1350)</span></span>
- <span data-ttu-id="1a9f1-1161">Melhorias no fechamento de TCP para transferência de dados mais confiável.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1161">Improvements to TCP close for more reliable data transfer.</span></span> <span data-ttu-id="1a9f1-1162">(GH 610, 616, 1025, 1335)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1162">(GH #610, 616, 1025, 1335)</span></span>
- <span data-ttu-id="1a9f1-1163">Agora, o código de erro correto é retornado quando muitos arquivos estão abertos (EMFILE).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1163">Now return correct error code when too many files are opened (EMFILE).</span></span> <span data-ttu-id="1a9f1-1164">(GH 1126, 2090)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1164">(GH #1126, 2090)</span></span>
- <span data-ttu-id="1a9f1-1165">O log de auditoria do Windows agora relata o nome da imagem no processo create audit.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1165">Windows Audit log now reports the image name in process create audit.</span></span>
- <span data-ttu-id="1a9f1-1166">Agora, falha normalmente ao iniciar bash.exe de dentro de uma janela do Bash</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1166">Now gracefully fail when launching bash.exe from within a bash window</span></span>
- <span data-ttu-id="1a9f1-1167">Mensagem de erro adicionada quando a interop não consegue acessar um diretório de trabalho em LxFs (ou seja, notepad.exe. bashrc)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1167">Added error message when interop is unable to access a working directory under LxFs (i.e. notepad.exe .bashrc)</span></span>
- <span data-ttu-id="1a9f1-1168">Corrigido o problema em que o caminho do Windows era truncado no WSL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1168">Fixed issue where Windows path was truncated in WSL</span></span>
- <span data-ttu-id="1a9f1-1169">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1169">Additional fixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1170">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1170">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1171">Número de testes aprovados: 690</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1171">Number of Passing Test: 690</span></span> </br>
<span data-ttu-id="1a9f1-1172">Número de não aprovados (com falha, ignorados, etc.): 274</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1172">Number of non-Passing (failing, skipped, etc…): 274</span></span> </br>
[<span data-ttu-id="1a9f1-1173">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1173">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15002)<br/>

<br/>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1174">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1174">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1175">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1175">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1176">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1176">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`shmctl`<br/>
`shmget`<br/>
`shmdt`<br/>
`shmat`<br/>
<br/>

## <a name="build-14986"></a><span data-ttu-id="1a9f1-1177">Build 14986</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1177">Build 14986</span></span>

<span data-ttu-id="1a9f1-1178">Para obter informações gerais do Windows sobre o Build 14986, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/12/07/announcing-windows-10-insider-preview-build-14986-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1178">For general Windows information on build 14986 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/12/07/announcing-windows-10-insider-preview-build-14986-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1179">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1179">Fixed</span></span>

- <span data-ttu-id="1a9f1-1180">Correção de verificações de bugs com NetLink e IOCTLs pty</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1180">Fixed bugchecks with Netlink and Pty IOCTLs</span></span>
- <span data-ttu-id="1a9f1-1181">A versão do kernel agora relata 4.4.0-43 para consistência com o Xenial</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1181">Kernel version now reports 4.4.0-43 for consistency with Xenial</span></span>
- <span data-ttu-id="1a9f1-1182">O bash.exe agora é iniciado quando a entrada é direcionada para 'nul:' (GH 1259)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1182">Bash.exe now launches when input directed to 'nul:' (GH #1259)</span></span>
- <span data-ttu-id="1a9f1-1183">IDs de thread agora são relatadas corretamente em procfs (GH 967)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1183">Thread IDs now reported correctly in procfs (GH #967)</span></span>
- <span data-ttu-id="1a9f1-1184">Os sinalizadores IN_UNMOUNT | IN_Q_OVERFLOW | IN_IGNORED | IN_ISDIR agora são compatíveis com inotify_add_watch() (GH 1280)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1184">IN_UNMOUNT | IN_Q_OVERFLOW | IN_IGNORED | IN_ISDIR flags now supported in inotify_add_watch() (GH #1280)</span></span>
- <span data-ttu-id="1a9f1-1185">Implementado timer_create e chamadas de sistema relacionadas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1185">Implement timer_create and related system calls.</span></span>  <span data-ttu-id="1a9f1-1186">Isso habilita o suporte a GHC (GH 307)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1186">This enables GHC support (GH #307)</span></span>
- <span data-ttu-id="1a9f1-1187">Corrigido o problema em que o ping retornava um tempo de 0,000 ms (GH 1296)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1187">Fixed issue where ping returned a time of 0.000ms (GH #1296)</span></span>
- <span data-ttu-id="1a9f1-1188">O código de erro correto é retornado quando muitos arquivos estão abertos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1188">Return correct error code when too many files are opened.</span></span>
- <span data-ttu-id="1a9f1-1189">Corrigido o problema no WSL em que a solicitação do NetLink para dados do adaptador de rede falharia com EINVAL se o endereço de hardware do adaptador fosse de 32 bytes (assim como na interface Teredo)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1189">Fixed issue in WSL where Netlink request for network interface data would fail with EINVAL if the interface's hardware address is 32-bytes (such as the Teredo interface)</span></span>
   - <span data-ttu-id="1a9f1-1190">Observe que o utilitário "ip" do Linux contém um bug que faz com que ele falhe se o WSL relata um endereço de hardware de 32 bytes.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1190">Note that the Linux "ip" utility contains a bug where it will crash if WSL reports a 32-byte hardware address.</span></span> <span data-ttu-id="1a9f1-1191">Esse é um bug em "ip", não no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1191">This is a bug in "ip", not WSL.</span></span> <span data-ttu-id="1a9f1-1192">O utilitário "ip" embute em código o tamanho do buffer de cadeia de caracteres usado para imprimir o endereço de hardware, e esse buffer é muito pequeno para imprimir um endereço de hardware de 32 bytes.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1192">The "ip" utility hard-codes the length of the string buffer used to print the hardware address, and that buffer is too small to print a 32-byte hardware address.</span></span>
- <span data-ttu-id="1a9f1-1193">Correções e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1193">Additional fixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1194">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1194">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1195">Número de testes aprovados: 669</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1195">Number of Passing Test: 669</span></span> </br>
<span data-ttu-id="1a9f1-1196">Número de não aprovados (com falha, ignorados, etc.): 258</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1196">Number of non-Passing (failing, skipped, etc…): 258</span></span> </br>
[<span data-ttu-id="1a9f1-1197">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1197">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14986)<br/>

<br/>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1198">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1198">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1199">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1199">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1200">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1200">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`timer_create`<br/>
`timer_delete`<br/>
`timer_gettime`<br/>
`timer_settime`<br/>
<br/>

## <a name="build-14971"></a><span data-ttu-id="1a9f1-1201">Build 14971</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1201">Build 14971</span></span>

<span data-ttu-id="1a9f1-1202">Para obter informações gerais do Windows sobre o Build 14971, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/11/17/announcing-windows-10-insider-preview-build-14971-for-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1202">For general Windows information on build 14971 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/11/17/announcing-windows-10-insider-preview-build-14971-for-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1203">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1203">Fixed</span></span>

 - <span data-ttu-id="1a9f1-1204">Devido a circunstâncias além do nosso controle, não há atualizações nesse build para o Subsistema do Windows para Linux.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1204">Due to circumstances beyond our control there are no updates in this build for the Windows Subsystem for Linux.</span></span>  <span data-ttu-id="1a9f1-1205">As atualizações agendadas regularmente serão retomadas na próxima versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1205">Regularly scheduled updates will resume on the next release.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1206">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1206">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1207">Inalterado desde o 14965</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1207">Unchanged from 14965</span></span> </br>
<span data-ttu-id="1a9f1-1208">Número de testes aprovados: 664</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1208">Number of Passing Test: 664</span></span> </br>
<span data-ttu-id="1a9f1-1209">Número de não aprovados (com falha, ignorados, etc.): 263</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1209">Number of non-Passing (failing, skipped, etc…): 263</span></span> </br>
[<span data-ttu-id="1a9f1-1210">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1210">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14965)<br/>

<br/>

## <a name="build-14965"></a><span data-ttu-id="1a9f1-1211">Build 14965</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1211">Build 14965</span></span>

<span data-ttu-id="1a9f1-1212">Para obter informações gerais do Windows sobre o Build 14965, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/11/09/announcing-windows-10-insider-preview-build-14965-for-mobile-and-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1212">For general Windows information on build 14965 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/11/09/announcing-windows-10-insider-preview-build-14965-for-mobile-and-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1213">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1213">Fixed</span></span>

- <span data-ttu-id="1a9f1-1214">Suporte para RTM_GETLINK e RTM_GETADDR do protocolo NETLINK_ROUTE de soquetes NetLink (GH 468)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1214">Support for Netlink sockets NETLINK_ROUTE protocol's RTM_GETLINK and RTM_GETADDR (GH #468)</span></span>
  - <span data-ttu-id="1a9f1-1215">Habilita os comandos ip e ifconfig para enumeração de rede</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1215">Enables ifconfig and ip commands for network enumeration</span></span>
  - <span data-ttu-id="1a9f1-1216">Mais informações podem ser encontradas em nossa [postagem no blog de rede WSL](https://blogs.msdn.microsoft.com/wsl/2016/11/08/225/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1216">More information can be found in our [WSL Networking blog post](https://blogs.msdn.microsoft.com/wsl/2016/11/08/225/).</span></span>

- <span data-ttu-id="1a9f1-1217">/sbin agora está no caminho do usuário por padrão</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1217">/sbin is now in the user's path by default</span></span>
- <span data-ttu-id="1a9f1-1218">O caminho de usuário do NT agora é acrescentado ao caminho do WSL por padrão (ou seja, agora você pode digitar notepad.exe sem adicionar System32 ao caminho do Linux)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1218">NT user path now appended to the WSL path by default (i.e. you can now type notepad.exe without adding System32 to the Linux path)</span></span>
- <span data-ttu-id="1a9f1-1219">Adicionado suporte para /proc/sys/kernel/cap_last_cap</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1219">Added support for /proc/sys/kernel/cap_last_cap</span></span>
- <span data-ttu-id="1a9f1-1220">Os binários do NT agora podem ser iniciados do WSL quando o diretório de trabalho atual contém caracteres não ANSI (GH 1254)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1220">NT Binaries can now be launched from WSL when the current working directory contains non-ansi characters (GH #1254)</span></span>
- <span data-ttu-id="1a9f1-1221">Permissão para o desligamento no soquete de fluxo do Unix desconectado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1221">Allow shutdown on disconnected unix stream socket.</span></span>
- <span data-ttu-id="1a9f1-1222">Adicionado suporte para PR_GET_PDEATHSIG.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1222">Added support for PR_GET_PDEATHSIG.</span></span>
- <span data-ttu-id="1a9f1-1223">Adicionado suporte para CLONE_PARENT</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1223">Added support for CLONE_PARENT</span></span>
- <span data-ttu-id="1a9f1-1224">Corrigido o erro em que o pipe fica preso, ou seja, bash -c "ls -alR /" | bash -c "cat" (GH 1214)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1224">Fixed error where piping gets stuck i.e. bash -c "ls -alR /" | bash -c "cat" (GH #1214)</span></span>
- <span data-ttu-id="1a9f1-1225">Manipulação das solicitações para se conectar ao terminal atual.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1225">Handle requests to connect to the current terminal.</span></span>
- <span data-ttu-id="1a9f1-1226">Marcação de /proc/<pid>/oom_score_adj como gravável.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1226">Mark /proc/<pid>/oom_score_adj as writable.</span></span>
- <span data-ttu-id="1a9f1-1227">Adição da pasta/sys/fs/cgroup.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1227">Add /sys/fs/cgroup folder.</span></span>
- <span data-ttu-id="1a9f1-1228">sched_setaffinity deve retornar o número de máscara de bits de afinidade</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1228">sched_setaffinity should return number of affinity bits mask</span></span>
- <span data-ttu-id="1a9f1-1229">Correção da lógica de validação ELF que pressupõe incorretamente que os caminhos do interpretador devem ter menos de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1229">Fix ELF validation logic which incorrectly assumes interpreter paths must be less than 64 characters long.</span></span> <span data-ttu-id="1a9f1-1230">(GH 743)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1230">(GH #743)</span></span>
- <span data-ttu-id="1a9f1-1231">Descritores de arquivo abertos podem manter a janela do console aberta (GH 1187)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1231">Open file descriptors can keep console window open (GH #1187)</span></span>
- <span data-ttu-id="1a9f1-1232">Corrigido um erro em que rename() falhava com barra à direita no nome de destino (GH 1008)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1232">Fixeed error where rename() failed with trailing slash on target name (GH #1008)</span></span>
- <span data-ttu-id="1a9f1-1233">Implementação de /proc/net/dev file</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1233">Implement /proc/net/dev file</span></span>
- <span data-ttu-id="1a9f1-1234">Corrigida a ocorrência de pings de 0,000 ms devido à resolução do timer.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1234">Fixed 0.000ms pings due to timer resolution.</span></span>
- <span data-ttu-id="1a9f1-1235">Implementado /proc/self/environ (GH 730)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1235">Implemented /proc/self/environ (GH #730)</span></span>
- <span data-ttu-id="1a9f1-1236">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1236">Additional bugfixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1237">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1237">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1238">Número de testes aprovados: 664</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1238">Number of Passing Test: 664</span></span> </br>
<span data-ttu-id="1a9f1-1239">Número de não aprovados (com falha, ignorados, etc.): 263</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1239">Number of non-Passing (failing, skipped, etc…): 263</span></span> </br>
[<span data-ttu-id="1a9f1-1240">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1240">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14965)<br/>

<br/>

## <a name="build-14959"></a><span data-ttu-id="1a9f1-1241">Build 14959</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1241">Build 14959</span></span>

<span data-ttu-id="1a9f1-1242">Para obter informações gerais do Windows sobre o Build 14959, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/11/03/announcing-windows-10-insider-preview-build-14959-for-mobile-and-pc/#iI82GufJxMF3POU1.97).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1242">For general Windows information on build 14959 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/11/03/announcing-windows-10-insider-preview-build-14959-for-mobile-and-pc/#iI82GufJxMF3POU1.97).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1243">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1243">Fixed</span></span>

- <span data-ttu-id="1a9f1-1244">Notificação de processo Pico aprimorada para Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1244">Improved Pico Process notification for Windows.</span></span>  <span data-ttu-id="1a9f1-1245">Informações adicionais encontradas no [blog do WSL](/archive/blogs/wsl/wsl-antivirus-and-firewall-compatibility).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1245">Additional information found on the [WSL Blog](/archive/blogs/wsl/wsl-antivirus-and-firewall-compatibility).</span></span>
- <span data-ttu-id="1a9f1-1246">Estabilidade aprimorada com a interop do Windows</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1246">Improved stability with Windows interoperability</span></span>
- <span data-ttu-id="1a9f1-1247">Corrigido o erro 0x80070057 ao iniciar o bash.exe quando a EDP (proteção de dados empresariais) está habilitada</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1247">Fixed error 0x80070057 when launching bash.exe when Enterprise Data Protection (EDP) is enabled</span></span>
- <span data-ttu-id="1a9f1-1248">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1248">Additional bugfixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1249">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1249">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1250">Número de testes aprovados: 665</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1250">Number of Passing Test: 665</span></span> </br>
<span data-ttu-id="1a9f1-1251">Número de não aprovados (com falha, ignorados, etc.): 263</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1251">Number of non-Passing (failing, skipped, etc…): 263</span></span> </br>
[<span data-ttu-id="1a9f1-1252">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1252">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14959)<br/>

<br/>

## <a name="build-14955"></a><span data-ttu-id="1a9f1-1253">Build 14955</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1253">Build 14955</span></span>

<span data-ttu-id="1a9f1-1254">Para obter informações gerais do Windows sobre o Build 14955, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/10/25/announcing-windows-10-insider-preview-build-14955-for-mobile-and-pc/#guGXQzKVFrZIDUYR.97).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1254">For general Windows information on build 14955 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/10/25/announcing-windows-10-insider-preview-build-14955-for-mobile-and-pc/#guGXQzKVFrZIDUYR.97).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1255">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1255">Fixed</span></span>

 - <span data-ttu-id="1a9f1-1256">Devido a circunstâncias além do nosso controle, não há atualizações nesse build para o Subsistema do Windows para Linux.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1256">Due to circumstances beyond our control there are no updates in this build for the Windows Subsystem for Linux.</span></span>  <span data-ttu-id="1a9f1-1257">As atualizações agendadas regularmente serão retomadas na próxima versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1257">Regularly scheduled updates will resume on the next release.</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1258">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1258">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1259">Número de testes aprovados: 665</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1259">Number of Passing Test: 665</span></span> </br>
<span data-ttu-id="1a9f1-1260">Número de não aprovados (com falha, ignorados, etc.): 263</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1260">Number of non-Passing (failing, skipped, etc…): 263</span></span> </br>
[<span data-ttu-id="1a9f1-1261">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1261">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14955)<br/>

<br/>

## <a name="build-14951"></a><span data-ttu-id="1a9f1-1262">Build 14951</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1262">Build 14951</span></span>

<span data-ttu-id="1a9f1-1263">Para obter informações gerais do Windows sobre o Build 14951, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/10/19/announcing-windows-10-insider-preview-build-14951-for-mobile-and-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1263">For general Windows information on build 14951 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/10/19/announcing-windows-10-insider-preview-build-14951-for-mobile-and-pc/).</span></span><br/>


### <a name="new-feature-windows--ubuntu-interoperability"></a><span data-ttu-id="1a9f1-1264">Novo recurso: Interoperabilidade entre Windows/Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1264">New Feature: Windows / Ubuntu Interoperability</span></span>
<span data-ttu-id="1a9f1-1265">Os binários do Windows agora podem ser chamados diretamente da linha de comando do WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1265">Windows binaries can now be invoked directly from the WSL command line.</span></span>  <span data-ttu-id="1a9f1-1266">Isso dá aos usuários a capacidade de interagir com o ambiente e o sistema do Windows de uma maneira que não era possível.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1266">This gives users the ability to interact with their Windows environment and system in a way that has not been possible.</span></span>  <span data-ttu-id="1a9f1-1267">Como um exemplo rápido, agora é possível que os usuários executem os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1267">As a quick example, it is now possible for users to run the following commands:</span></span>

```bash
$ export PATH=$PATH:/mnt/c/Windows/System32
$ notepad.exe
$ ipconfig.exe | grep IPv4 | cut -d: -f2
$ ls -la | findstr.exe foo.txt
$ cmd.exe /c dir
```

<span data-ttu-id="1a9f1-1268">Mais informações podem ser encontradas em:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1268">More information can be found at:</span></span>

- [<span data-ttu-id="1a9f1-1269">Blog da equipe do WSL para interop</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1269">WSL Team Blog for Interop</span></span>](/archive/blogs/wsl/windows-and-ubuntu-interoperability)<br/>
- [<span data-ttu-id="1a9f1-1270">Documentação de interop do MSDN</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1270">MSDN Interop Documentation</span></span>](./interop.md)<br/>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1271">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1271">Fixed</span></span>

- <span data-ttu-id="1a9f1-1272">O Ubuntu 16.04 (Xenial) agora está instalado para todas as novas instâncias de WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1272">Ubuntu 16.04 (Xenial) is now installed for all new WSL instances.</span></span>  <span data-ttu-id="1a9f1-1273">Os usuários com instâncias 14.04 (confiáveis) existentes não serão atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1273">Users with existing 14.04 (Trusty) instances will not be automatically upgraded.</span></span>
- <span data-ttu-id="1a9f1-1274">A localidade definida durante a instalação agora é exibida</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1274">Locale set during install is now displayed</span></span>
- <span data-ttu-id="1a9f1-1275">Melhorias de terminal, incluindo bugs em que o redirecionamento de um processo do WSL para um arquivo nem sempre funciona</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1275">Terminal improvements including bug where redirecting a WSL process to a file does not always work</span></span>
- <span data-ttu-id="1a9f1-1276">O tempo de vida do console deve estar vinculado ao tempo de vida do bash.exe</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1276">Console lifetime should be tied to bash.exe lifetime</span></span>
- <span data-ttu-id="1a9f1-1277">O tamanho da janela do console deve usar um tamanho visível, não o tamanho do buffer</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1277">Console window size should use visible size, not buffer size</span></span>
- <span data-ttu-id="1a9f1-1278">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1278">Additional bugfixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1279">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1279">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1280">Número de testes aprovados: 665</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1280">Number of Passing Test: 665</span></span> </br>
<span data-ttu-id="1a9f1-1281">Número de não aprovados (com falha, ignorados, etc.): 263</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1281">Number of non-Passing (failing, skipped, etc…): 263</span></span> </br>
[<span data-ttu-id="1a9f1-1282">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1282">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14951)<br/>

<br/>

## <a name="build-14946"></a><span data-ttu-id="1a9f1-1283">Build 14946</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1283">Build 14946</span></span>

<span data-ttu-id="1a9f1-1284">Para obter informações gerais do Windows sobre o Build 14946, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/10/13/announcing-windows-10-insider-preview-build-14946-for-pc-and-mobile/#xj8GdVooEqo4H7H7.97).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1284">For general Windows information on build 14946 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/10/13/announcing-windows-10-insider-preview-build-14946-for-pc-and-mobile/#xj8GdVooEqo4H7H7.97).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1285">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1285">Fixed</span></span>

- <span data-ttu-id="1a9f1-1286">Corrigido um problema que impedia a criação de contas de usuário do WSL para usuários com nomes de usuário NT contendo espaços ou aspas.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1286">Fixed an issue that prevented creating WSL user accounts for users with NT usernames that contain spaces or quotes.</span></span> 
- <span data-ttu-id="1a9f1-1287">Altere VolFs e DrvFs para retornar 0 para a contagem de links do diretório em stat</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1287">Change VolFs and DrvFs to return 0 for directory's link count in stat</span></span>
- <span data-ttu-id="1a9f1-1288">Suporte à opção de soquete IPV6_MULTICAST_HOPS.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1288">Support IPV6_MULTICAST_HOPS socket option.</span></span>
- <span data-ttu-id="1a9f1-1289">Limite para um loop de E/S de console único por tty.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1289">Limit to a single console I/O loop per tty.</span></span> <span data-ttu-id="1a9f1-1290">Por exemplo, o comando a seguir é possível:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1290">Example: the following command is possible:</span></span>
  - <span data-ttu-id="1a9f1-1291">bash -c "echo data" | bash -c "ssh user@example.com 'cat > foo.txt'"</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1291">bash -c "echo data" | bash -c "ssh user@example.com 'cat > foo.txt'"</span></span>

- <span data-ttu-id="1a9f1-1292">substituição de espaços por tabulações em /proc/cpuinfo (GH 1115)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1292">replace spaces with tabs in /proc/cpuinfo (GH #1115)</span></span>
- <span data-ttu-id="1a9f1-1293">O DrvFs agora aparece em mountinfo com um nome que corresponde ao volume do Windows montado</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1293">DrvFs now appears in mountinfo with a name that matches mounted Windows volume</span></span>
- <span data-ttu-id="1a9f1-1294">/home e /root agora aparecem em mountinfo com os nomes corretos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1294">/home and /root now appear in mountinfo with correct names</span></span>
- <span data-ttu-id="1a9f1-1295">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1295">Additional bugfixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1296">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1296">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1297">Número de testes aprovados: 665</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1297">Number of Passing Test: 665</span></span> </br>
<span data-ttu-id="1a9f1-1298">Número de não aprovados (com falha, ignorados, etc.): 263</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1298">Number of non-Passing (failing, skipped, etc…): 263</span></span> </br>
[<span data-ttu-id="1a9f1-1299">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1299">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14946)<br/>

<br/>

## <a name="build-14942"></a><span data-ttu-id="1a9f1-1300">Build 14942</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1300">Build 14942</span></span>

<span data-ttu-id="1a9f1-1301">Para obter informações gerais do Windows sobre o Build 14942, visite o [blog do Windows](https://aka.ms/onefourninefourtwoooooo).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1301">For general Windows information on build 14942 visit the [Windows Blog](https://aka.ms/onefourninefourtwoooooo).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1302">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1302">Fixed</span></span>

- <span data-ttu-id="1a9f1-1303">Correção de várias verificações de bug, incluindo a falha de rede "TENTATIVA DE EXECUTAR A MEMÓRIA NOEXECUTE", que bloqueava o SSH</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1303">A number of bugchecks addressed, including the "ATTEMPTED EXECUTE OF NOEXECUTE MEMORY" networking crash which was blocking SSH</span></span>
- <span data-ttu-id="1a9f1-1304">o suporte do inotifiy para notificações geradas de aplicativos do Windows no DrvFs agora está em</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1304">inotifiy support for notifications generated from Windows applications on DrvFs is now in</span></span>
- <span data-ttu-id="1a9f1-1305">Implementação de TCP_KEEPIDLE e TCP_KEEPINTVL para mongod.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1305">Implement TCP_KEEPIDLE and TCP_KEEPINTVL for mongod.</span></span> <span data-ttu-id="1a9f1-1306">(GH 695)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1306">(GH #695)</span></span>
- <span data-ttu-id="1a9f1-1307">Implementação da chamada do sistema pivot_root</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1307">Implement the pivot_root system call</span></span>
- <span data-ttu-id="1a9f1-1308">Implementar opção de soquete para SO_DONTROUTE</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1308">Implement socket option for SO_DONTROUTE</span></span>
- <span data-ttu-id="1a9f1-1309">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1309">Additional bugfixes and improvements</span></span>


### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1310">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1310">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1311">Número de testes aprovados: 665</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1311">Number of Passing Test: 665</span></span> </br>
<span data-ttu-id="1a9f1-1312">Número de não aprovados (com falha, ignorados, etc.): 263</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1312">Number of non-Passing (failing, skipped, etc…): 263</span></span> </br>
[<span data-ttu-id="1a9f1-1313">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1313">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14942)<br/>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1314">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1314">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1315">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1315">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1316">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1316">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`pivot_root`<br/>
<br/>

## <a name="build-14936"></a><span data-ttu-id="1a9f1-1317">Build 14936</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1317">Build 14936</span></span>

<span data-ttu-id="1a9f1-1318">Para obter informações gerais do Windows sobre o Build 14936, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/09/28/announcing-windows-10-insider-preview-build-14936-for-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1318">For general Windows information on build 14936 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/09/28/announcing-windows-10-insider-preview-build-14936-for-pc/).</span></span><br/>


<span data-ttu-id="1a9f1-1319">Observação: O WSL instalará o Ubuntu versão 16.04 (Xenial) em vez do Ubuntu 14.04 (Trusty) em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1319">Note: WSL will install Ubuntu version 16.04 (Xenial) instead of Ubuntu 14.04 (Trusty) in an upcoming release.</span></span>  <span data-ttu-id="1a9f1-1320">Essa alteração se aplicará a Participantes do Programa Windows Insider que estejam instalando novas instâncias (lxrun.exe /install ou primeira execução de bash.exe).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1320">This change will apply to Insiders installing new instances (lxrun.exe /install or first run of bash.exe).</span></span>  <span data-ttu-id="1a9f1-1321">As instâncias existentes com Trusty não serão atualizadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1321">Existing instances with Trusty will not be upgraded automatically.</span></span> <span data-ttu-id="1a9f1-1322">Os usuários podem atualizar sua imagem do Trusty para Xenial usando o comando do-release-upgrade.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1322">Users can upgrade their Trusty image to Xenial using the do-release-upgrade command.</span></span>

### <a name="known-issue"></a><span data-ttu-id="1a9f1-1323">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1323">Known Issue</span></span>
<span data-ttu-id="1a9f1-1324">O WSL está enfrentando um problema com algumas implementações de soquete.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1324">WSL is experiencing an issue with some socket implementations.</span></span>  <span data-ttu-id="1a9f1-1325">A verificação de bug se manifesta como uma falha com o erro "TENTATIVA DE EXECUTAR A MEMÓRIA NOEXECUTE".</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1325">The bugcheck manifests itself as a crash with the error "ATTEMPTED EXECUTE OF NOEXECUTE MEMORY".</span></span>  <span data-ttu-id="1a9f1-1326">A manifestação mais comum desse problema é uma falha ao usar SSH.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1326">The most common manifestation of this issue is a crash when using ssh.</span></span>  <span data-ttu-id="1a9f1-1327">A causa raiz é corrigida em builds internos e será enviada por push para pessoas na primeira oportunidade.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1327">The root cause is fixed on internal builds and will be pushed to Insiders at the earliest opportunity.</span></span>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1328">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1328">Fixed</span></span>

- <span data-ttu-id="1a9f1-1329">Implementada a chamada do sistema chroot</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1329">Implemented the chroot system call</span></span>
- <span data-ttu-id="1a9f1-1330">Melhorias no inotifiy ~~incluindo suporte para notificações geradas de aplicativos do Windows no DrvFs~~</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1330">Improvements in inotify ~~including support for notifications generated from Windows applications on DrvFs~~</span></span>
  - <span data-ttu-id="1a9f1-1331">Correção: O suporte do INotifyPropertyChanged para alterações provenientes de aplicativos do Windows não estão disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1331">Correction: Inotify support for changes originating from Windows applications not available at this time.</span></span>
- <span data-ttu-id="1a9f1-1332">Associação de soquete a IPV6::<port n> agora dá suporte a IPV6_V6ONLY (GH 68, 157, 393, 460, 674, 740, 982, 996)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1332">Socket binding to IPV6::<port n> now supports IPV6_V6ONLY  (GH #68, #157, #393, #460, #674, #740, #982, #996)</span></span>
- <span data-ttu-id="1a9f1-1333">Comportamento de WNOWAIT implementado para a chamada do sistema waitid (GH 638)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1333">WNOWAIT behavior for waitid systemcall implemented (GH #638)</span></span>
- <span data-ttu-id="1a9f1-1334">Suporte para as opções de soquete de IP IP_HDRINCL e IP_TTL</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1334">Support for IP socket options IP_HDRINCL and IP_TTL</span></span>
- <span data-ttu-id="1a9f1-1335">read() de tamanho zero deve retornar imediatamente (GH 975)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1335">Zero-length read() should return immediately (GH #975)</span></span>
- <span data-ttu-id="1a9f1-1336">Manipulação correta de nomes de arquivos e prefixos de nome de arquivo que não incluem um terminador nulo em um arquivo .tar.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1336">Correctly handle filenames and filename prefixes that don't include a NULL terminator in a .tar file.</span></span>
- <span data-ttu-id="1a9f1-1337">Suporte do epoll para/dev/null</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1337">epoll support for /dev/null</span></span>
- <span data-ttu-id="1a9f1-1338">Correção da origem de tempo /dev/alarm</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1338">Fix /dev/alarm time source</span></span>
- <span data-ttu-id="1a9f1-1339">Bash-c agora é capaz de redirecionar para um arquivo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1339">Bash -c now able to redirect to a file</span></span>
- <span data-ttu-id="1a9f1-1340">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1340">Additional bugfixes and improvements</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1341">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1341">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1342">Número de testes aprovados: 664</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1342">Number of Passing Test: 664</span></span> </br>
<span data-ttu-id="1a9f1-1343">Número de não aprovados (com falha, ignorados, etc.): 264</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1343">Number of non-Passing (failing, skipped, etc…): 264</span></span> </br>
[<span data-ttu-id="1a9f1-1344">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1344">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14936)<br/>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1345">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1345">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1346">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1346">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1347">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1347">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`chroot`<br/>
<br/>

## <a name="build-14931"></a><span data-ttu-id="1a9f1-1348">Build 14931</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1348">Build 14931</span></span>

<span data-ttu-id="1a9f1-1349">Para obter informações gerais do Windows sobre o Build 14931, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/09/21/announcing-windows-10-insider-preview-build-14931-for-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1349">For general Windows information on build 14931 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/09/21/announcing-windows-10-insider-preview-build-14931-for-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1350">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1350">Fixed</span></span>

 - <span data-ttu-id="1a9f1-1351">Devido a circunstâncias além do nosso controle, não há atualizações nesse build para o Subsistema do Windows para Linux.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1351">Due to circumstances beyond our control there are no updates in this build for the Windows Subsystem for Linux.</span></span>  <span data-ttu-id="1a9f1-1352">As atualizações agendadas regularmente serão retomadas na próxima versão.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1352">Regularly scheduled updates will resume in the next release.</span></span>

<br/>

## <a name="build-14926"></a><span data-ttu-id="1a9f1-1353">Build 14926</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1353">Build 14926</span></span>

<span data-ttu-id="1a9f1-1354">Para obter informações gerais do Windows sobre o Build 14926, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/09/14/announcing-windows-10-insider-preview-build-14926-for-pc-and-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1354">For general Windows information on build 14926 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/09/14/announcing-windows-10-insider-preview-build-14926-for-pc-and-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1355">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1355">Fixed</span></span>

- <span data-ttu-id="1a9f1-1356">O ping agora funciona em consoles sem privilégios de administrador</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1356">Ping now works in consoles which do not have administrator privileges</span></span>
- <span data-ttu-id="1a9f1-1357">O Ping6 agora é compatível, inclusive quando sem privilégios de administrador</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1357">Ping6 now supported, also without administrator privileges</span></span>
- <span data-ttu-id="1a9f1-1358">Suporte a INotifyPropertyChanged para arquivos modificados por meio de WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1358">Inotify support for files modified through WSL.</span></span> <span data-ttu-id="1a9f1-1359">(GH 216)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1359">(GH #216)</span></span>
  - <span data-ttu-id="1a9f1-1360">Sinalizadores compatíveis:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1360">Flags supported:</span></span>
    - <span data-ttu-id="1a9f1-1361">inotify_init1: LX_O_CLOEXEC, LX_O_NONBLOCK</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1361">inotify_init1: LX_O_CLOEXEC, LX_O_NONBLOCK</span></span>
    - <span data-ttu-id="1a9f1-1362">Eventos de inotify_add_watch: LX_IN_ACCESS, LX_IN_MODIFY, LX_IN_ATTRIB, LX_IN_CLOSE_WRITE, LX_IN_CLOSE_NOWRITE, LX_IN_OPEN, LX_IN_MOVED_FROM, LX_IN_MOVED_TO, LX_IN_CREATE, LX_IN_DELETE, LX_IN_DELETE_SELF, LX_IN_MOVE_SELF</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1362">inotify_add_watch events: LX_IN_ACCESS, LX_IN_MODIFY, LX_IN_ATTRIB, LX_IN_CLOSE_WRITE, LX_IN_CLOSE_NOWRITE, LX_IN_OPEN, LX_IN_MOVED_FROM, LX_IN_MOVED_TO, LX_IN_CREATE, LX_IN_DELETE, LX_IN_DELETE_SELF, LX_IN_MOVE_SELF</span></span>
    - <span data-ttu-id="1a9f1-1363">Atributos de inotify_add_watch: LX_IN_DONT_FOLLOW, LX_IN_EXCL_UNLINK, LX_IN_MASK_ADD, LX_IN_ONESHOT, LX_IN_ONLYDIR</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1363">inotify_add_watch attributes: LX_IN_DONT_FOLLOW, LX_IN_EXCL_UNLINK, LX_IN_MASK_ADD, LX_IN_ONESHOT, LX_IN_ONLYDIR</span></span>
    - <span data-ttu-id="1a9f1-1364">saída de leitura: LX_IN_ISDIR, LX_IN_IGNORED</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1364">read output: LX_IN_ISDIR, LX_IN_IGNORED</span></span>
  - <span data-ttu-id="1a9f1-1365">Problema conhecido: a modificação de arquivos de aplicativos do Windows não gera nenhum evento</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1365">Known issue: Modifying files from Windows applications does not generate any events</span></span>
- <span data-ttu-id="1a9f1-1366">O soquete Unix agora dá suporte a SCM_CREDENTIALS</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1366">Unix socket now supports SCM_CREDENTIALS</span></span>

### <a name="ltp-results"></a><span data-ttu-id="1a9f1-1367">Resultados do LTP:</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1367">LTP Results:</span></span>
<span data-ttu-id="1a9f1-1368">Número de testes aprovados: 651</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1368">Number of Passing Test: 651</span></span> </br>
<span data-ttu-id="1a9f1-1369">Número de não aprovados (com falha, ignorados, etc.): 258</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1369">Number of non-Passing (failing, skipped, etc…): 258</span></span> </br>
[<span data-ttu-id="1a9f1-1370">Logs de execução de teste do LTP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1370">LTP Test Run Logs</span></span>](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14926)<br/>

<br/>

## <a name="build-14915"></a><span data-ttu-id="1a9f1-1371">Build 14915</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1371">Build 14915</span></span>

<span data-ttu-id="1a9f1-1372">Para obter informações gerais do Windows sobre o Build 14915, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/08/31/announcing-windows-10-insider-preview-build-14915-for-pc-and-mobile).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1372">For general Windows information on build 14915 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/08/31/announcing-windows-10-insider-preview-build-14915-for-pc-and-mobile).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1373">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1373">Fixed</span></span>
-  <span data-ttu-id="1a9f1-1374">Par de soquetes para soquetes de datagramas Unix (GH 262)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1374">Socketpair for unix datagram sockets (GH #262)</span></span>
- <span data-ttu-id="1a9f1-1375">Suporte a soquetes Unix para SO_REUSEADDR</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1375">Unix socket support for SO_REUSEADDR</span></span>
- <span data-ttu-id="1a9f1-1376">Suporte a soquetes Unix para SO_BROADCAST (GH 568)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1376">UNIX socket support for SO_BROADCAST (GH #568)</span></span>
- <span data-ttu-id="1a9f1-1377">Suporte a soquetes Unix para SOCK_SEQPACKET (GH 758, 546)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1377">Unix socket support for SOCK_SEQPACKET (GH #758, #546)</span></span>
- <span data-ttu-id="1a9f1-1378">Adição de suporte para envio, recebimento e desligamento de soquete de datagrama Unix</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1378">Adding support for unix datagram socket send, recv and shutdown</span></span>
- <span data-ttu-id="1a9f1-1379">Correção de verificação de bugs devido à validação de parâmetro mmap inválida para endereços não fixos.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1379">Fix bugcheck due to invalid mmap parameter validation for non-fixed addresses.</span></span> <span data-ttu-id="1a9f1-1380">(GH 847)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1380">(GH #847)</span></span>
- <span data-ttu-id="1a9f1-1381">Suporte para suspensão/retomada de estados de terminal</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1381">Support for suspend / resume of terminal states</span></span>
- <span data-ttu-id="1a9f1-1382">Suporte para ioctl TIOCPKT para desbloquear o utilitário de tela (GH 774)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1382">Support for TIOCPKT ioctl to unblock the Screen utility (GH #774)</span></span>
    - <span data-ttu-id="1a9f1-1383">Problema conhecido: Teclas de função não operacionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1383">Known issue: Function keys not operational</span></span>
- <span data-ttu-id="1a9f1-1384">Correção de uma corrida em TimerFd que poderia fazer com que um membro 'ReaderReady' liberado fosse acessado pelo LxpTimerFdWorkerRoutine (GH 814)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1384">Corrected a race in TimerFd that could cause a freed member 'ReaderReady' to be accessed by LxpTimerFdWorkerRoutine (GH #814)</span></span>
- <span data-ttu-id="1a9f1-1385">Habilitar suporte à chamada do sistema reiniciável para futex, poll e clock_nanosleep</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1385">Enable restartable system call support for futex, poll, and clock_nanosleep</span></span>
- <span data-ttu-id="1a9f1-1386">Adicionado suporte à montagem de associação</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1386">Added bind mount support</span></span>
- <span data-ttu-id="1a9f1-1387">suporte a descompartilhamento para namespace de montagem</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1387">unshare for mount namespace support</span></span>
    - <span data-ttu-id="1a9f1-1388">Problema conhecido: Ao criar um novo namespace de montagem `unshare(CLONE_NEWNS)` com o diretório de trabalho atual, ele continuará a apontar para o namespace antigo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1388">Known issue: When creating a new mount namespace with `unshare(CLONE_NEWNS)` the current working directory will continue to point to the old namespace</span></span>
- <span data-ttu-id="1a9f1-1389">Melhorias e correções de bugs adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1389">Additional improvements and bug fixes</span></span>

<br/>

## <a name="build-14905"></a><span data-ttu-id="1a9f1-1390">Build 14905</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1390">Build 14905</span></span>

<span data-ttu-id="1a9f1-1391">Para obter informações gerais do Windows sobre o Build 14905, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/08/17/announcing-windows-10-insider-preview-build-14905-for-pc-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1391">For general Windows information on build 14905 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/08/17/announcing-windows-10-insider-preview-build-14905-for-pc-mobile/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1392">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1392">Fixed</span></span>
- <span data-ttu-id="1a9f1-1393">Agora, as chamadas reiniciáveis do sistema são compatíveis (GH 349, GH 520)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1393">Restartable system calls are now supported (GH #349, GH #520)</span></span>
- <span data-ttu-id="1a9f1-1394">Symlinks para diretórios que terminam em / agora estão operacionais (GH 650)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1394">Symlinks to directories ending in / now operational (GH #650)</span></span>
- <span data-ttu-id="1a9f1-1395">Ioctl RNDGETENTCNT implementado para /dev/random</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1395">Implemented RNDGETENTCNT ioctl for /dev/random</span></span>
- <span data-ttu-id="1a9f1-1396">Implementados os arquivos /proc/[pid]/mounts, /proc/[pid]/mountinfo e /proc/[pid]/mountstats</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1396">Implemented the /proc/[pid]/mounts, /proc/[pid]/mountinfo and /proc/[pid]/mountstats files</span></span>
- <span data-ttu-id="1a9f1-1397">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1397">Additional bugfixes and improvements</span></span>

</br>

## <a name="build-14901"></a><span data-ttu-id="1a9f1-1398">Build 14901</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1398">Build 14901</span></span>
<span data-ttu-id="1a9f1-1399">Primeiro build de Participante do Programa Windows Insider para a versão de Atualização de Aniversário do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1399">First Insider build for the post Windows 10 Anniversary Update release.</span></span>

<span data-ttu-id="1a9f1-1400">Para obter informações gerais do Windows sobre o Build 14901, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/08/11/announcing-windows-10-insider-preview-build-14901-for-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1400">For general Windows information on build 14901 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/08/11/announcing-windows-10-insider-preview-build-14901-for-pc/).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1401">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1401">Fixed</span></span>
- <span data-ttu-id="1a9f1-1402">Corrigido problema de barra à direita</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1402">Fixed trailing slash issue</span></span>
    - <span data-ttu-id="1a9f1-1403">Comandos como `$ mv a/c/ a/b/` agora funcionam</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1403">Commands such as `$ mv a/c/ a/b/` now work</span></span>
- <span data-ttu-id="1a9f1-1404">A instalação agora avisa se a localidade do Ubuntu deve ser definida como a localidade do Windows</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1404">Installing now prompts if Ubuntu locale should be set to Windows locale</span></span>
- <span data-ttu-id="1a9f1-1405">Suporte do procfs para a pasta ns</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1405">Procfs support for ns folder</span></span>
- <span data-ttu-id="1a9f1-1406">Adição de montagem e desmontagem para sistemas de arquivos tmpfs, procfs e sysfs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1406">Added mount and unmount for tmpfs, procfs and sysfs file systems</span></span>
- <span data-ttu-id="1a9f1-1407">Corrigir a assinatura da ABI de 32 bits mknod[at]</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1407">Fix mknod[at] 32-bit ABI signature</span></span>
- <span data-ttu-id="1a9f1-1408">Soquetes Unix movidos para o modelo de expedição</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1408">Unix sockets moved to dispatch model</span></span>
- <span data-ttu-id="1a9f1-1409">O tamanho do buffer de recebimento do soquete INET definido usando o setsockopt deve ser respeitado</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1409">INET socket recv buffer size set using the setsockopt should be honored</span></span>
- <span data-ttu-id="1a9f1-1410">Implementação do sinalizador de mensagem de recebimento do soquete do Unix MSG_CMSG_CLOEXEC</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1410">Implement MSG_CMSG_CLOEXEC unix socket receive message flag</span></span>
- <span data-ttu-id="1a9f1-1411">Redirecionamento de pipe stdin/stdout de processo do Linux (GH 2)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1411">Linux process stdin/stdout pipe redirection (GH #2)</span></span>
    - <span data-ttu-id="1a9f1-1412">Permite o pipe de comandos bash -c no cmd.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1412">Allows for piping of bash -c commands in CMD.</span></span>  <span data-ttu-id="1a9f1-1413">Exemplo: >dir | bash -c "grep foo"</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1413">Example:  >dir | bash -c "grep foo"</span></span>
- <span data-ttu-id="1a9f1-1414">O Bash agora pode ser instalado em sistemas com diversos arquivos de paginação (GH 538, 358)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1414">Bash can now be installed on systems with multiple pagefiles (GH #538, #358)</span></span>
- <span data-ttu-id="1a9f1-1415">O tamanho do buffer do soquete INET padrão deve corresponder ao da configuração padrão do Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1415">Default INET Socket buffer size should match that of default Ubuntu setup</span></span>
- <span data-ttu-id="1a9f1-1416">Alinhamento de syscalls xattr a listxattr</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1416">Align xattr syscalls to listxattr</span></span>
- <span data-ttu-id="1a9f1-1417">SIOCGIFCONF retorna apenas interfaces com um IPv4 válido</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1417">Only return interfaces with a valid IPv4 address from SIOCGIFCONF</span></span>
- <span data-ttu-id="1a9f1-1418">Correção da ação padrão de sinal quando injetado por ptrace</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1418">Fix signal default action when injected by ptrace</span></span>
- <span data-ttu-id="1a9f1-1419">Implementação de /proc/sys/vm/min_free_kbytes</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1419">implement /proc/sys/vm/min_free_kbytes</span></span>
- <span data-ttu-id="1a9f1-1420">Uso de valores de registro de contexto de computador ao restaurar o contexto em sigreturn</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1420">Use machine context register values when restoring context in sigreturn</span></span>
    - <span data-ttu-id="1a9f1-1421">Isso resolve o problema em que java e javac estavam travando para alguns usuários</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1421">This resolves the issue where java and javac were hanging for some users</span></span>
- <span data-ttu-id="1a9f1-1422">Implementação de /proc/sys/kernel/hostname</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1422">Implement /proc/sys/kernel/hostname</span></span>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1423">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1423">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1424">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1424">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1425">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1425">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`waitid`<br/>
`epoll_pwait`<br/>

<br/>

## <a name="build-14388-to-windows-10-anniversary-update"></a><span data-ttu-id="1a9f1-1426">Build 14388 para Atualização de Aniversário do Windows 10</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1426">Build 14388 to Windows 10 Anniversary Update</span></span>
<span data-ttu-id="1a9f1-1427">Para obter informações gerais do Windows sobre o Build 14388, visite o [blog do Windows](https://aka.ms/14388wip).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1427">For general Windows information on build 14388 visit the [Windows Blog](https://aka.ms/14388wip).</span></span> <br/>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1428">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1428">Fixed</span></span>
- <span data-ttu-id="1a9f1-1429">Correções para preparar para a Atualização de Aniversário do Windows 10 em 02/08</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1429">Fixes to prepare for the Windows 10 Anniversary Update on 8/2</span></span>
  - <span data-ttu-id="1a9f1-1430">Mais informações sobre WSL na atualização de aniversário podem ser encontradas em nosso [blog](/archive/blogs/wsl/)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1430">More information about WSL in the Anniversary Update can be found on our [blog](/archive/blogs/wsl/)</span></span>

<br/>

## <a name="build-14376"></a><span data-ttu-id="1a9f1-1431">Build 14376</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1431">Build 14376</span></span>
<span data-ttu-id="1a9f1-1432">Para obter informações gerais do Windows sobre o Build 14376, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/06/28/announcing-windows-10-insider-preview-build-14376-for-pc-and-mobile/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1432">For general Windows information on build 14376 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/06/28/announcing-windows-10-insider-preview-build-14376-for-pc-and-mobile/).</span></span> <br/>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1433">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1433">Fixed</span></span>
- <span data-ttu-id="1a9f1-1434">Removidas algumas instâncias em que apt-get trava (GH 493)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1434">Removed some instances where apt-get hangs (GH #493)</span></span>
- <span data-ttu-id="1a9f1-1435">Corrigido um problema em que as montagens vazias não eram manipuladas corretamente</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1435">Fixed an issue where empty mounts were not handled correctly</span></span>
- <span data-ttu-id="1a9f1-1436">Corrigido um problema em que ramdisks não eram montados corretamente</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1436">Fixed an issue where ramdisks were not mounted correctly</span></span>
- <span data-ttu-id="1a9f1-1437">Alteração da aceitação de soquete do Unix para dar suporte a sinalizadores (GH 451 parcial)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1437">Change unix socket accept to support flags (partial GH #451)</span></span>
- <span data-ttu-id="1a9f1-1438">Corrigida tela azul comum relacionada à rede</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1438">Fixed common network related bluescreen</span></span>
- <span data-ttu-id="1a9f1-1439">Corrigida tela azul ao acessar /proc/[pid]/task (GH 523)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1439">Fixed bluescreen when accessing /proc/[pid]/task (GH #523)</span></span>
- <span data-ttu-id="1a9f1-1440">Correção de alta utilização de CPU para alguns cenários de pty (GH 488, 504)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1440">Fixed high CPU utilization for some pty scenarios (GH #488, #504)</span></span>
- <span data-ttu-id="1a9f1-1441">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1441">Additional bugfixes and improvements</span></span>

<br/>

## <a name="build-14371"></a><span data-ttu-id="1a9f1-1442">Build 14371</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1442">Build 14371</span></span>
<span data-ttu-id="1a9f1-1443">Para obter informações gerais do Windows sobre o Build 14371, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/06/22/announcing-windows-10-insider-preview-build-14371-for-pc/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1443">For general Windows information on build 14371 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/06/22/announcing-windows-10-insider-preview-build-14371-for-pc/).</span></span> <br/>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1444">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1444">Fixed</span></span>
- <span data-ttu-id="1a9f1-1445">Corrigida corrida de tempo com SIGCHLD e wait() ao usar ptrace</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1445">Corrected timing race with SIGCHLD and wait() when using ptrace</span></span>
- <span data-ttu-id="1a9f1-1446">Corrigido algum comportamento quando os caminhos têm uma / à direita (GH 432)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1446">Corrected some behavior when paths have a trailing /  (GH #432)</span></span>
- <span data-ttu-id="1a9f1-1447">Corrigido um problema de falha ao renomear/desvincular devido a identificadores abertos para filhos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1447">Fixed issue with rename/unlink failing due to open handles to children</span></span>
- <span data-ttu-id="1a9f1-1448">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1448">Additional bugfixes and improvements</span></span>

<br/>

## <a name="build-14366"></a><span data-ttu-id="1a9f1-1449">Build 14366</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1449">Build 14366</span></span>
<span data-ttu-id="1a9f1-1450">Para obter informações gerais do Windows sobre o Build 14366, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/06/14/announcing-windows-10-insider-preview-build-14366-mobile-build-14364/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1450">For general Windows information on build 14366 visit the [Windows Blog](https://blogs.windows.com/windowsexperience/2016/06/14/announcing-windows-10-insider-preview-build-14366-mobile-build-14364/).</span></span> <br/>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1451">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1451">Fixed</span></span>
- <span data-ttu-id="1a9f1-1452">Correção na criação de arquivo por meio de symlinks</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1452">Fix in file creation through symlinks</span></span>
-   <span data-ttu-id="1a9f1-1453">Adicionado listxattr para o Python (GH 385)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1453">Added listxattr for Python (GH 385)</span></span>
-   <span data-ttu-id="1a9f1-1454">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1454">Additional bugfixes and improvements</span></span>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1455">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1455">Syscall Support</span></span>
-   <span data-ttu-id="1a9f1-1456">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1456">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1457">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1457">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`listxattr`<br/>
<br/>

## <a name="build-14361"></a><span data-ttu-id="1a9f1-1458">Build 14361</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1458">Build 14361</span></span>
<span data-ttu-id="1a9f1-1459">Para obter informações gerais do Windows sobre o Build 14361, visite o [blog do Windows](https://aka.ms/wip14361).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1459">For general Windows information on build 14361 visit the [Windows Blog](https://aka.ms/wip14361).</span></span> <br/>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1460">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1460">Fixed</span></span>
- <span data-ttu-id="1a9f1-1461">O DrvFs agora diferencia maiúsculas de minúsculas ao executar no Bash usando Ubuntu no Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1461">DrvFs is now case sensitive when running in Bash on Ubuntu on Windows.</span></span>
  - <span data-ttu-id="1a9f1-1462">Os usuários podem usar case.txt e CASE.TXT nas respectivas unidades /mnt/c</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1462">Users may case.txt and CASE.TXT on their /mnt/c drives</span></span>
  - <span data-ttu-id="1a9f1-1463">A diferenciação de maiúsculas e minúsculas só é compatível no Bash usando Ubuntu no Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1463">Case sensitivity is only supported within Bash on Ubuntu on Windows.</span></span> <span data-ttu-id="1a9f1-1464">Quando fora do Bash, o NTFS relatará os arquivos corretamente, mas um comportamento inesperado poderá ocorrer ao interagir com os arquivos do Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1464">When outside of Bash NTFS will report the files correctly, but unexpected behavior may occur interacting with the files from Windows.</span></span>
  - <span data-ttu-id="1a9f1-1465">A raiz de cada volume (ou seja, /mnt/c) não diferencia maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1465">The root of each volume (i.e. /mnt/c) is not case sensitive</span></span>
  - <span data-ttu-id="1a9f1-1466">É possível encontrar mais informações sobre como manipular esses arquivos no Windows [aqui](https://support.microsoft.com/kb/100625).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1466">More information on handling these files in Windows can be found [here](https://support.microsoft.com/kb/100625).</span></span>
- <span data-ttu-id="1a9f1-1467">Suporte a pty/tty bastante aprimorado.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1467">Greatly enhanced pty / tty support.</span></span>  <span data-ttu-id="1a9f1-1468">Aplicativos como TMUX agora são compatíveis (GH 40)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1468">Applications like TMUX now supported (GH #40)</span></span>
- <span data-ttu-id="1a9f1-1469">Corrigido um problema de instalação em que as contas de usuário nem sempre eram criadas</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1469">Fixed install issue where user accounts not always created</span></span>
- <span data-ttu-id="1a9f1-1470">Estrutura de argumentos de linha de comando otimizada que permite uma lista de argumentos extremamente longa.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1470">Optimized command line arg structure allowing for extremely long argument list.</span></span> <span data-ttu-id="1a9f1-1471">(GH 153)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1471">(GH #153)</span></span>
- <span data-ttu-id="1a9f1-1472">Agora é possível excluir e usar chmod em arquivos read_only do DrvFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1472">Now able to delete and chmod read_only files from DrvFs</span></span>
- <span data-ttu-id="1a9f1-1473">Corrigidas algumas instâncias em que o terminal travava ao desconectar (GH 43)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1473">Fixed some instances where the terminal hangs on disconnect (GH #43)</span></span>
- <span data-ttu-id="1a9f1-1474">chmod e chown agora funcionam em dispositivos tty</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1474">chmod and chown now work on tty devices</span></span>
- <span data-ttu-id="1a9f1-1475">Permissão para conexão a 0.0.0.0 e a :: como localhost (GH 388)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1475">Allow connection to 0.0.0.0 and :: as localhost (GH #388)</span></span>
- <span data-ttu-id="1a9f1-1476">Sendmsg/recvmsg agora aceitam um comprimento de vetor de E/S >1 (GH 376 parcial)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1476">Sendmsg/recvmsg now handle an IO vector length of >1 (partial GH #376)</span></span>
- <span data-ttu-id="1a9f1-1477">Os usuários agora podem recusar o arquivo de hosts gerado automaticamente (GH #398)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1477">Users can now opt-out of auto-generated hosts file (GH #398)</span></span>
- <span data-ttu-id="1a9f1-1478">Correspondência automática da localidade do Linux à localidade do NT durante a instalação (GH 11)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1478">Automatically match Linux locale to the NT locale during install (GH #11)</span></span>
- <span data-ttu-id="1a9f1-1479">Adicionado o arquivo /proc/sys/VM/swappiness (GH 306)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1479">Added the /proc/sys/vm/swappiness file (GH #306)</span></span>
- <span data-ttu-id="1a9f1-1480">strace agora é encerrado corretamente</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1480">strace now exits correctly</span></span>
- <span data-ttu-id="1a9f1-1481">Permissão para que os pipes sejam reabertos por meio de /proc/Self/FD (GH 222)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1481">Allow pipes to be reopened through /proc/self/fd (GH #222)</span></span>
- <span data-ttu-id="1a9f1-1482">Ocultação de diretórios em %LOCALAPPDATA%\lxss do DrvFs (GH 270)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1482">Hide directories under %LOCALAPPDATA%\lxss from DrvFs (GH #270)</span></span>
- <span data-ttu-id="1a9f1-1483">Melhor manipulação do bash.exe ~.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1483">Better handling of bash.exe ~.</span></span>  <span data-ttu-id="1a9f1-1484">Agora, há suporte para comandos como "bash ~ -c ls" (GH 467)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1484">Commands like "bash ~ -c ls" now supported (GH #467)</span></span>
- <span data-ttu-id="1a9f1-1485">Os soquetes agora notificam que a leitura de epoll está disponível durante o desligamento (GH 271)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1485">Sockets now notify epoll read available during shutdown (GH #271)</span></span>
- <span data-ttu-id="1a9f1-1486">lxrun /uninstall desempenha melhor a exclusão de arquivos e pastas</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1486">lxrun /uninstall does a better job of deleting the files and folders</span></span>
- <span data-ttu-id="1a9f1-1487">ps-f corrigido (GH 246)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1487">Corrected ps -f (GH #246)</span></span>
- <span data-ttu-id="1a9f1-1488">Suporte aprimorado para aplicativos x11, tais como xEmacs (GH 481)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1488">Improved support for x11 apps such as xEmacs (GH #481)</span></span>
- <span data-ttu-id="1a9f1-1489">Tamanho da pilha de thread inicial atualizado para corresponder à configuração padrão do Ubuntu e relatando o tamanho corretamente para a syscall get_rlimit (GH 172, 258)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1489">Updated initial thread stack size to match default Ubuntu setting and reporting the size correctly to the get_rlimit syscall (GH #172, #258)</span></span>
- <span data-ttu-id="1a9f1-1490">Relatório aprimorado de nomes de imagem de processo do pico (por exemplo, para auditoria)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1490">Improved reporting of pico process image names (e.g., for auditing)</span></span>
- <span data-ttu-id="1a9f1-1491">Implementado o /proc/mountinfo para o comando df</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1491">Implemented /proc/mountinfo for df command</span></span>
- <span data-ttu-id="1a9f1-1492">Corrigido o código de erro de symlink para o nome do filho.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1492">Fixed symlink error code for child name .</span></span> <span data-ttu-id="1a9f1-1493">e .</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1493">and ..</span></span>
- <span data-ttu-id="1a9f1-1494">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1494">Additional improvements bugfixes and improvements</span></span>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1495">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1495">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1496">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1496">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1497">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1497">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`GETTIMER`<br/>
`MKNODAT`<br/>
`RENAMEAT`<br/>
`SENDFILE`<br/>
`SENDFILE64`<br/>
`SYNC_FILE_RANGE`<br/>
<br/>

## <a name="build-14352"></a><span data-ttu-id="1a9f1-1498">Build 14352</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1498">Build 14352</span></span>
<span data-ttu-id="1a9f1-1499">Para obter informações gerais do Windows sobre o Build 14352, visite o [blog do Windows](https://aka.ms/wip14352).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1499">For general Windows information on build 14352 visit the [Windows Blog](https://aka.ms/wip14352).</span></span><br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1500">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1500">Fixed</span></span>
- <span data-ttu-id="1a9f1-1501">Corrigido um problema em que arquivos grandes não eram baixados/criados corretamente.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1501">Fixed issue where large files were not downloaded / created correctly.</span></span>  <span data-ttu-id="1a9f1-1502">Isso deve desbloquear o npm e outros cenários (GH 3, GH 313)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1502">This should unblock npm and other scenarios (GH #3, GH #313)</span></span>
- <span data-ttu-id="1a9f1-1503">Removidas algumas instâncias em que soquetes travavam</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1503">Removed some instances where sockets hang</span></span>
- <span data-ttu-id="1a9f1-1504">Corrigidos alguns erros de ptrace</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1504">Corrected some ptrace errors</span></span>
- <span data-ttu-id="1a9f1-1505">Corrigido um problema com o WSL permitindo nomes de arquivo maiores do que 255 caracteres</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1505">Fixed issue with WSL allowing filenames longer than 255 characters</span></span>
- <span data-ttu-id="1a9f1-1506">Suporte aprimorado para caracteres diferentes do inglês</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1506">Improved support for non-English characters</span></span>
- <span data-ttu-id="1a9f1-1507">Adicionar os dados de fuso horário atual do Windows e definir como padrão</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1507">Add current Windows timezone data and set as default</span></span>
- <span data-ttu-id="1a9f1-1508">Identificações de dispositivo exclusivas para cada ponto de montagem (correção do JRE – GH 49)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1508">Unique device id's for each mount point (jre fix – GH #49)</span></span>
- <span data-ttu-id="1a9f1-1509">Correção do problema com caminhos contendo "." e ".."</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1509">Correct issue with paths containing "." and ".."</span></span>
- <span data-ttu-id="1a9f1-1510">Adicionado suporte a PEPS (GH 71)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1510">Added Fifo support (GH #71)</span></span>
- <span data-ttu-id="1a9f1-1511">Atualizado formato de resolv.conf para corresponder ao formato nativo do Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1511">Updated format of resolv.conf to match native Ubuntu format</span></span>
- <span data-ttu-id="1a9f1-1512">Limpeza de alguns procfs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1512">Some procfs cleanup</span></span>
- <span data-ttu-id="1a9f1-1513">Ping habilitado para consoles do administrador (GH 18)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1513">Enabled ping for Administrator consoles (GH #18)</span></span>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1514">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1514">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1515">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1515">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1516">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1516">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`FALLOCATE`<br/>
`EXECVE`<br/>
`LGETXATTR`<br/>
`FGETXATTR`<br/>
<br/>

## <a name="build-14342"></a><span data-ttu-id="1a9f1-1517">Build 14342</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1517">Build 14342</span></span>
<span data-ttu-id="1a9f1-1518">Para obter informações gerais do Windows sobre o Build 14342, visite o [blog do Windows](https://aka.ms/wip14342).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1518">For general Windows information on build 14342 the [Windows Blog](https://aka.ms/wip14342).</span></span> <br/>

<span data-ttu-id="1a9f1-1519">Informações sobre VolFs e DriveFs podem ser encontradas no [blog do WSL](/archive/blogs/wsl/).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1519">Information on VolFs and DriveFs can be found on the [WSL Blog](/archive/blogs/wsl/).</span></span> <br/>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1520">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1520">Fixed</span></span>
- <span data-ttu-id="1a9f1-1521">Corrigido problema de instalação quando o usuário do Windows tinha caracteres Unicode no nome de usuário</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1521">Fixed install issue when the Windows user had Unicode characters in the username</span></span>
- <span data-ttu-id="1a9f1-1522">A solução alternativa apt-get update udev nas perguntas frequentes agora é fornecida por padrão na primeira execução</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1522">The apt-get update udev workaround in the FAQ is now provided by default on first run</span></span>
- <span data-ttu-id="1a9f1-1523">Symlinks habilitados nos diretórios de DriveFs (/mnt/<drive>)</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1523">Enabled symlinks in DriveFs (/mnt/<drive>) directories</span></span>
- <span data-ttu-id="1a9f1-1524">Symlinks agora funcionam entre DriveFs e VolFs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1524">Symlinks now work between DriveFs and VolFs</span></span>
- <span data-ttu-id="1a9f1-1525">Problema de análise de caminho de nível superior resolvido: ls .// agora funcionará como esperado</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1525">Addressed top level path parsing issue: ls .// will now work as expected</span></span>
- <span data-ttu-id="1a9f1-1526">A instalação de npm no DriveFs e as opções -g agora estão funcionando</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1526">npm install on DriveFs and the -g options are now working</span></span>
- <span data-ttu-id="1a9f1-1527">Problema corrigido, impedindo a inicialização do servidor PHP</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1527">Fixed issue preventing PHP server from launching</span></span>
- <span data-ttu-id="1a9f1-1528">Valores de ambiente padrão atualizados, tais como $PATH para corresponder melhor ao Ubuntu nativo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1528">Updated default environment values, such as $PATH to closer match native Ubuntu</span></span>
- <span data-ttu-id="1a9f1-1529">Adicionada uma tarefa de manutenção semanal no Windows para atualizar o cache do pacote apt</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1529">Added a weekly maintenance task in Windows to update the apt package cache</span></span>
- <span data-ttu-id="1a9f1-1530">Corrigido um problema com a validação de cabeçalho ELF, o WSL agora dá suporte a todas as opções de Melkor</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1530">Fixed issue with ELF header validation, WSL now supports all Melkor options</span></span>
- <span data-ttu-id="1a9f1-1531">O shell do zsh está funcional</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1531">Zsh shell is functional</span></span>
- <span data-ttu-id="1a9f1-1532">Binários do Go pré-compilados agora são compatíveis</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1532">Precompiled Go binaries are now supported</span></span>
- <span data-ttu-id="1a9f1-1533">O aviso na primeira execução do bash.exe agora está localizado corretamente</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1533">Prompting on Bash.exe first run is now localized correctly</span></span>
- <span data-ttu-id="1a9f1-1534">/proc/meminfo agora retorna informações corretas</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1534">/proc/meminfo now returns correct information</span></span>
- <span data-ttu-id="1a9f1-1535">Os soquetes agora são compatíveis com o VFS</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1535">Sockets now supported in VFS</span></span>
- <span data-ttu-id="1a9f1-1536">/dev agora é montado como tempfs</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1536">/dev now mounted as tempfs</span></span>
- <span data-ttu-id="1a9f1-1537">PEPS agora é compatível</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1537">Fifo now supported</span></span>
- <span data-ttu-id="1a9f1-1538">Sistemas de vários núcleos agora são mostrados corretamente em /proc/cpuinfo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1538">Multi-core systems now showing correctly in /proc/cpuinfo</span></span>
- <span data-ttu-id="1a9f1-1539">Aprimoramentos adicionais e mensagens de erro ao baixar durante a primeira execução</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1539">Additional improvements and error messages downloading during first run</span></span>
- <span data-ttu-id="1a9f1-1540">Melhorias e correções de bug em syscall.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1540">Syscall improvements and bugfixes.</span></span> <span data-ttu-id="1a9f1-1541">Lista de syscalls compatíveis abaixo.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1541">Supported syscall list below.</span></span>
- <span data-ttu-id="1a9f1-1542">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1542">Additional bugfixes and improvements</span></span>

### <a name="known-issues"></a><span data-ttu-id="1a9f1-1543">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1543">Known Issues</span></span>
- <span data-ttu-id="1a9f1-1544">Sem resolução para '..'</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1544">Not resolving '..'</span></span> <span data-ttu-id="1a9f1-1545">corretamente no DriveFs em alguns casos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1545">correctly on DriveFs in some cases</span></span>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1546">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1546">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1547">Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1547">Below are a list of new or enhanced syscalls that have some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1548">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1548">The syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`FCHOWNAT`<br/>
`GETEUID`<br/>
`GETGID`<br/>
`GETRESUID`<br/>
`GETXATTR`<br/>
`PTRACE`<br/>
`SETGID`<br/>
`SETGROUPS`<br/>
`SETHOSTNAME`<br/>
`SETXATTR`<br/>
<br/>

## <a name="build-14332"></a><span data-ttu-id="1a9f1-1549">Build 14332</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1549">Build 14332</span></span>

<span data-ttu-id="1a9f1-1550">Para obter informações gerais do Windows sobre o Build 14332, visite o [blog do Windows](https://aka.ms/wip14332).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1550">For general Windows information on build 14332 visit the [Windows Blog](https://aka.ms/wip14332).</span></span> <br/>


### <a name="fixed"></a><span data-ttu-id="1a9f1-1551">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1551">Fixed</span></span>
- <span data-ttu-id="1a9f1-1552">Melhor geração de resolv.conf, incluindo a priorização de entradas DNS</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1552">Better resolv.conf generation including prioritizing DNS entries</span></span>
- <span data-ttu-id="1a9f1-1553">Problema com a movimentação de arquivos e diretórios entre unidades/mnt e não /mnt</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1553">Issue with moving files and directories between /mnt and non-/mnt drives</span></span>
- <span data-ttu-id="1a9f1-1554">Agora, os arquivos tar podem ser criados com symlinks</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1554">Tar files can now be created with symlinks</span></span>
- <span data-ttu-id="1a9f1-1555">Diretório /run/lock padrão adicionado na criação da instância</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1555">Added default /run/lock directory on instance creation</span></span>
- <span data-ttu-id="1a9f1-1556">Atualização de /dev/null para retornar informações de estado adequadas</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1556">Update /dev/null to return proper stat info</span></span>
- <span data-ttu-id="1a9f1-1557">Erros adicionais ao baixar durante a primeira execução</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1557">Additional errors when downloading during first run</span></span>
- <span data-ttu-id="1a9f1-1558">Melhorias e correções de bug em syscall.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1558">Syscall improvements and bugfixes.</span></span> <span data-ttu-id="1a9f1-1559">Lista de syscalls compatíveis abaixo.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1559">Supported syscall list below.</span></span>
- <span data-ttu-id="1a9f1-1560">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1560">Additional improvements bugfixes and improvements</span></span>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1561">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1561">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1562">Abaixo está a nova syscall que tem alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1562">Below is the new syscall that has some implementation in WSL.</span></span> <span data-ttu-id="1a9f1-1563">A syscall nessa lista é compatível com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com ela no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1563">The syscall on this list is supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`READLINKAT`<br/>
<br/>

## <a name="build-14328"></a><span data-ttu-id="1a9f1-1564">Build 14328</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1564">Build 14328</span></span>

<span data-ttu-id="1a9f1-1565">Para obter informações gerais do Windows sobre o Build 14332, visite o [blog do Windows](https://aka.ms/wip14328).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1565">For general Windows information on build 14332 visit the [Windows Blog](https://aka.ms/wip14328).</span></span> <br/>


### <a name="new-features"></a><span data-ttu-id="1a9f1-1566">Novos recursos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1566">New Features</span></span>
* <span data-ttu-id="1a9f1-1567">Agora dão suporte a usuários do Linux.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1567">Now support Linux users.</span></span>  <span data-ttu-id="1a9f1-1568">A instalação do Bash usando o Ubuntu no Windows solicitará a criação de um usuário do Linux.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1568">Installing Bash on Ubuntu on Windows will prompt for creation of a Linux user.</span></span>  <span data-ttu-id="1a9f1-1569">Para obter mais informações, visite https://aka.ms/wslusers</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1569">For more information, visit https://aka.ms/wslusers</span></span>
* <span data-ttu-id="1a9f1-1570">O hostname agora está definido como o nome do computador Windows, não mais como @localhost</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1570">Hostname is now set to the Windows computer name, no more @localhost</span></span>
* <span data-ttu-id="1a9f1-1571">Para obter mais informações sobre o build 14328, visite: https://aka.ms/wip14328</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1571">For more information on build 14328, visit: https://aka.ms/wip14328</span></span>

### <a name="fixed"></a><span data-ttu-id="1a9f1-1572">Fixo</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1572">Fixed</span></span>
* <span data-ttu-id="1a9f1-1573">Aprimoramentos do symlink para arquivos não /mnt/<drive></span><span class="sxs-lookup"><span data-stu-id="1a9f1-1573">Symlink improvements for non /mnt/<drive> files</span></span>
    * <span data-ttu-id="1a9f1-1574">A instalação de npm agora funciona</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1574">npm install now works</span></span>
    * <span data-ttu-id="1a9f1-1575">Agora, o jdk/jre é instalável usando as instruções encontradas [aqui](https://xubuntugeek.blogspot.com/2012/09/how-to-install-oracle-jdk-7-manually-in.html).</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1575">jdk / jre now installable using instructions found [here](https://xubuntugeek.blogspot.com/2012/09/how-to-install-oracle-jdk-7-manually-in.html).</span></span>
    * <span data-ttu-id="1a9f1-1576">problema conhecido: os symlinks não funcionam para montagens do Windows.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1576">known issue: symlinks do not work for Windows mounts.</span></span>  <span data-ttu-id="1a9f1-1577">A funcionalidade estará disponível em um build posterior</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1577">Functionality will be available in a later build</span></span>
* <span data-ttu-id="1a9f1-1578">top e htop agora são exibidos</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1578">top and htop now display</span></span>
* <span data-ttu-id="1a9f1-1579">Mensagens de erro adicionais para algumas falhas de instalação</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1579">Additional error messages for some install failures</span></span>
* <span data-ttu-id="1a9f1-1580">Melhorias e correções de bug em syscall.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1580">Syscall improvements and bugfixes.</span></span>  <span data-ttu-id="1a9f1-1581">Lista de syscalls compatíveis abaixo.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1581">Supported syscall list below.</span></span>
* <span data-ttu-id="1a9f1-1582">Correções de bug e melhorias adicionais</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1582">Additional improvements bugfixes and improvements</span></span>

### <a name="syscall-support"></a><span data-ttu-id="1a9f1-1583">Suporte a syscall</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1583">Syscall Support</span></span>
<span data-ttu-id="1a9f1-1584">Veja abaixo uma lista de syscalls que têm alguma implementação no WSL.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1584">Below is a list of syscalls that have some implementation in WSL.</span></span>  <span data-ttu-id="1a9f1-1585">As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.</span><span class="sxs-lookup"><span data-stu-id="1a9f1-1585">Syscalls on this list are supported in at least one scenario, but may not have all parameters supported at this time.</span></span>

`ACCEPT`<br/>
`ACCEPT4`<br/>
`ACCESS`<br/>
`ALARM`<br/>
`ARCH_PRCTL`<br/>
`BIND`<br/>
`BRK`<br/>
`CAPGET`<br/>
`CAPSET`<br/>
`CHDIR`<br/>
`CHMOD`<br/>
`CHOWN`<br/>
`CLOCK_GETRES`<br/>
`CLOCK_GETTIME`<br/>
`CLOCK_NANOSLEEP`<br/>
`CLONE`<br/>
`CLOSE`<br/>
`CONNECT`<br/>
`CREAT`<br/>
`DUP`<br/>
`DUP2`<br/>
`DUP3`<br/>
`EPOLL_CREATE`<br/>
`EPOLL_CREATE1`<br/>
`EPOLL_CTL`<br/>
`EPOLL_WAIT`<br/>
`EVENTFD`<br/>
`EVENTFD2`<br/>
`EXECVE`<br/>
`EXIT`<br/>
`EXIT_GROUP`<br/>
`FACCESSAT`<br/>
`FADVISE64`<br/>
`FCHDIR`<br/>
`FCHMOD`<br/>
`FCHMODAT`<br/>
`FCHOWN`<br/>
`FCHOWNAT`<br/>
`FCNTL64`<br/>
`FDATASYNC`<br/>
`FLOCK`<br/>
`FORK`<br/>
`FSETXATTR`<br/>
`FSTAT64`<br/>
`FSTATAT64`<br/>
`FSTATFS64`<br/>
`FSYNC`<br/>
`FTRUNCATE`<br/>
`FTRUNCATE64`<br/>
`FUTEX`<br/>
`GETCPU`<br/>
`GETCWD`<br/>
`GETDENTS`<br/>
`GETDENTS64`<br/>
`GETEGID`<br/>
`GETEGID16`<br/>
`GETEUID`<br/>
`GETEUID16`<br/>
`GETGID`<br/>
`GETGID16`<br/>
`GETGROUPS`<br/>
`GETPEERNAME`<br/>
`GETPGID`<br/>
`GETPGRP`<br/>
`GETPID`<br/>
`GETPPID`<br/>
`GETPRIORITY`<br/>
`GETRESGID`<br/>
`GETRESGID16`<br/>
`GETRESUID`<br/>
`GETRESUID16`<br/>
`GETRLIMIT`<br/>
`GETRUSAGE`<br/>
`GETSID`<br/>
`GETSOCKNAME`<br/>
`GETSOCKOPT`<br/>
`GETTID`<br/>
`GETTIMEOFDAY`<br/>
`GETUID`<br/>
`GETUID16`<br/>
`GETXATTR`<br/>
`GET_ROBUST_LIST`<br/>
`GET_THREAD_AREA`<br/>
`INOTIFY_ADD_WATCH`<br/>
`INOTIFY_INIT`<br/>
`INOTIFY_RM_WATCH`<br/>
`IOCTL`<br/>
`IOPRIO_GET`<br/>
`IOPRIO_SET`<br/>
`KEYCTL`<br/>
`KILL`<br/>
`LCHOWN`<br/>
`LINK`<br/>
`LINKAT`<br/>
`LISTEN`<br/>
`LLSEEK`<br/>
`LSEEK`<br/>
`LSTAT64`<br/>
`MADVISE`<br/>
`MKDIR`<br/>
`MKDIRAT`<br/>
`MKNOD`<br/>
`MLOCK`<br/>
`MMAP`<br/>
`MMAP2`<br/>
`MOUNT`<br/>
`MPROTECT`<br/>
`MREMAP`<br/>
`MSYNC`<br/>
`MUNLOCK`<br/>
`MUNMAP`<br/>
`NANOSLEEP`<br/>
`NEWUNAME`<br/>
`OPEN`<br/>
`OPENAT`<br/>
`PAUSE`<br/>
`PERF_EVENT_OPEN`<br/>
`PERSONALITY`<br/>
`PIPE`<br/>
`PIPE2`<br/>
`POLL`<br/>
`PPOLL`<br/>
`PRCTL`<br/>
`PREAD64`<br/>
`PROCESS_VM_READV`<br/>
`PROCESS_VM_WRITEV`<br/>
`PSELECT6`<br/>
`PTRACE`<br/>
`PWRITE64`<br/>
`READ`<br/>
`READLINK`<br/>
`READV`<br/>
`REBOOT`<br/>
`RECV`<br/>
`RECVFROM`<br/>
`RECVMSG`<br/>
`RENAME`<br/>
`RMDIR`<br/>
`RT_SIGACTION`<br/>
`RT_SIGPENDING`<br/>
`RT_SIGPROCMASK`<br/>
`RT_SIGRETURN`<br/>
`RT_SIGSUSPEND`<br/>
`RT_SIGTIMEDWAIT`<br/>
`SCHED_GETAFFINITY`<br/>
`SCHED_GETPARAM`<br/>
`SCHED_GETSCHEDULER`<br/>
`SCHED_GET_PRIORITY_MAX`<br/>
`SCHED_GET_PRIORITY_MIN`<br/>
`SCHED_SETAFFINITY`<br/>
`SCHED_SETPARAM`<br/>
`SCHED_SETSCHEDULER`<br/>
`SCHED_YIELD`<br/>
`SELECT`<br/>
`SEND`<br/>
`SENDMMSG`<br/>
`SENDMSG`<br/>
`SENDTO`<br/>
`SETDOMAINNAME`<br/>
`SETGID`<br/>
`SETGROUPS`<br/>
`SETHOSTNAME`<br/>
`SETITIMER`<br/>
`SETPGID`<br/>
`SETPRIORITY`<br/>
`SETREGID`<br/>
`SETRESGID`<br/>
`SETRESUID`<br/>
`SETREUID`<br/>
`SETRLIMIT`<br/>
`SETSID`<br/>
`SETSOCKOPT`<br/>
`SETTIMEOFDAY`<br/>
`SETUID`<br/>
`SETXATTR`<br/>
`SET_ROBUST_LIST`<br/>
`SET_THREAD_AREA`<br/>
`SET_TID_ADDRESS`<br/>
`SHUTDOWN`<br/>
`SIGACTION`<br/>
`SIGALTSTACK`<br/>
`SIGPENDING`<br/>
`SIGPROCMASK`<br/>
`SIGRETURN`<br/>
`SIGSUSPEND`<br/>
`SOCKET`<br/>
`SOCKETCALL`<br/>
`SOCKETPAIR`<br/>
`SPLICE`<br/>
`STAT64`<br/>
`STATFS64`<br/>
`SYMLINK`<br/>
`SYMLINKAT`<br/>
`SYNC`<br/>
`SYSINFO`<br/>
`TEE`<br/>
`TGKILL`<br/>
`TIME`<br/>
`TIMERFD_CREATE`<br/>
`TIMERFD_GETTIME`<br/>
`TIMERFD_SETTIME`<br/>
`TIMES`<br/>
`TKILL`<br/>
`TRUNCATE`<br/>
`TRUNCATE64`<br/>
`UMASK`<br/>
`UMOUNT`<br/>
`UMOUNT2`<br/>
`UNLINK`<br/>
`UNLINKAT`<br/>
`UNSHARE`<br/>
`UTIME`<br/>
`UTIMENSAT`<br/>
`UTIMES`<br/>
`VFORK`<br/>
`WAIT4`<br/>
`WAITPID`<br/>
`WRITE`<br/>
`WRITEV`<br/>