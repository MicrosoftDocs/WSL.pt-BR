---
title: Comparação entre o WSL 2 e o WSL 1
description: 'Compare as versões 1 e 2 do Subsistema do Windows para Linux. Saiba o que há de novo no WSL 2: kernel real do Linux, velocidade mais rápida, compatibilidade total com chamadas do sistema. O WSL 1 funcionará melhor se você estiver armazenando arquivos em sistemas de arquivos operacionais. Você pode expandir o tamanho do seu VHD (Disco de Hardware Virtual) do WSL 2.'
keywords: BashOnWindows, bash, wsl, windows, windowssubsystem, gnu, linux, ubuntu, debian, suse, windows 10, UX changes, WSL 2, linux kernel, network applications, localhost, IPv6, Virtual Hardware Disk, VHD, VHD limitations, VHD error
ms.date: 09/28/2020
ms.topic: conceptual
ms.localizationpriority: high
ms.custom: contperfq1
ms.openlocfilehash: be0cd21b65705e455f29bfd1666ce74078a21baa
ms.sourcegitcommit: cfb6c254322b8eb9c2c26e19ce970d4c046bc352
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "93035732"
---
# <a name="comparing-wsl-1-and-wsl-2"></a><span data-ttu-id="bd008-107">Comparação entre o WSL 1 e o WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-107">Comparing WSL 1 and WSL 2</span></span>

<span data-ttu-id="bd008-108">A principal diferença e os motivos para atualizar o Subsistema do Windows para Linux do WSL 1 para o WSL 2 são:</span><span class="sxs-lookup"><span data-stu-id="bd008-108">The primary difference and reasons for updating the Windows Subsystem for Linux from WSL 1 to WSL 2 are to:</span></span>

- <span data-ttu-id="bd008-109">**aumentar o desempenho do sistema de arquivos** ,</span><span class="sxs-lookup"><span data-stu-id="bd008-109">**increase file system performance** ,</span></span>
- <span data-ttu-id="bd008-110">**dar suporte à compatibilidade total com chamadas do sistema**.</span><span class="sxs-lookup"><span data-stu-id="bd008-110">**support full system call compatibility**.</span></span>

<span data-ttu-id="bd008-111">O WSL 2 usa a mais recente e melhor tecnologia de virtualização para executar um kernel do Linux dentro de uma VM (máquina virtual) do utilitário leve.</span><span class="sxs-lookup"><span data-stu-id="bd008-111">WSL 2 uses the latest and greatest in virtualization technology to run a Linux kernel inside of a lightweight utility virtual machine (VM).</span></span> <span data-ttu-id="bd008-112">No entanto, o WSL 2 não é uma experiência de VM tradicional.</span><span class="sxs-lookup"><span data-stu-id="bd008-112">However, WSL 2 is not a traditional VM experience.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bd008-113">Instalar o WSL 1 e atualizar para o WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-113">Install WSL 1 and update to WSL 2</span></span>](install-win10.md)

## <a name="comparing-features"></a><span data-ttu-id="bd008-114">Comparação de recursos</span><span class="sxs-lookup"><span data-stu-id="bd008-114">Comparing features</span></span>

<span data-ttu-id="bd008-115">Recurso</span><span class="sxs-lookup"><span data-stu-id="bd008-115">Feature</span></span> | <span data-ttu-id="bd008-116">WSL 1</span><span class="sxs-lookup"><span data-stu-id="bd008-116">WSL 1</span></span> | <span data-ttu-id="bd008-117">WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-117">WSL 2</span></span>
--- | --- | ---
 <span data-ttu-id="bd008-118">Integração entre o Windows e o Linux</span><span class="sxs-lookup"><span data-stu-id="bd008-118">Integration between Windows and Linux</span></span>| ✅|✅
 <span data-ttu-id="bd008-119">Tempos de inicialização rápidos</span><span class="sxs-lookup"><span data-stu-id="bd008-119">Fast boot times</span></span>| ✅ | ✅
 <span data-ttu-id="bd008-120">Volume de recursos pequeno</span><span class="sxs-lookup"><span data-stu-id="bd008-120">Small resource foot print</span></span>| ✅ |✅
 <span data-ttu-id="bd008-121">É executado com as versões atuais do VMware e do VirtualBox</span><span class="sxs-lookup"><span data-stu-id="bd008-121">Runs with current versions of VMware and VirtualBox</span></span>| ✅ | ✅
 <span data-ttu-id="bd008-122">VM gerenciada</span><span class="sxs-lookup"><span data-stu-id="bd008-122">Managed VM</span></span>| ❌ | ✅
 <span data-ttu-id="bd008-123">Kernel do Linux completo</span><span class="sxs-lookup"><span data-stu-id="bd008-123">Full Linux Kernel</span></span>| ❌ |✅
 <span data-ttu-id="bd008-124">Compatibilidade total com a chamada do sistema</span><span class="sxs-lookup"><span data-stu-id="bd008-124">Full system call compatibility</span></span>| ❌ | ✅
 <span data-ttu-id="bd008-125">Desempenho entre sistemas de arquivos do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="bd008-125">Performance across OS file systems</span></span>| ✅ | ❌

<span data-ttu-id="bd008-126">Como você pode ver na tabela de comparação acima, a arquitetura WSL 2 tem um desempenho melhor que o WSL 1 de várias maneiras, com exceção do desempenho entre sistemas de arquivos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="bd008-126">As you can tell from the comparison table above, the WSL 2 architecture outperforms WSL 1 in several ways, with the exception of performance across OS file systems.</span></span>

## <a name="performance-across-os-file-systems"></a><span data-ttu-id="bd008-127">Desempenho entre sistemas de arquivos do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="bd008-127">Performance across OS file systems</span></span>

<span data-ttu-id="bd008-128">Não recomendamos trabalhar em sistemas operacionais com os seus arquivos, a menos que você tenha um motivo específico para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="bd008-128">We recommend against working across operating systems with your files, unless you have a specific reason for doing so.</span></span> <span data-ttu-id="bd008-129">Para a velocidade de desempenho mais rápida, armazene os seus arquivos no sistema de arquivos WSL se você estiver trabalhando em uma linha de comando do Linux (Ubuntu, OpenSUSE etc.).</span><span class="sxs-lookup"><span data-stu-id="bd008-129">For the fastest performance speed, store your files in the WSL file system if you are working in a Linux command line (Ubuntu, OpenSUSE, etc).</span></span> <span data-ttu-id="bd008-130">Se estiver trabalhando em uma linha de comando do Windows (PowerShell, Prompt de Comando), armazene os arquivos no sistema de arquivos do Windows.</span><span class="sxs-lookup"><span data-stu-id="bd008-130">If you're working in a Windows command line (PowerShell, Command Prompt), store your files in the Windows file system.</span></span>

<span data-ttu-id="bd008-131">Por exemplo, ao armazenar seus arquivos de projeto do WSL:</span><span class="sxs-lookup"><span data-stu-id="bd008-131">For example, when storing your WSL project files:</span></span>

- <span data-ttu-id="bd008-132">Use o diretório raiz do sistema de arquivos do Linux: `\\wsl$\Ubuntu-18.04\home\<user name>\Project`</span><span class="sxs-lookup"><span data-stu-id="bd008-132">Use the Linux file system root directory: `\\wsl$\Ubuntu-18.04\home\<user name>\Project`</span></span>
- <span data-ttu-id="bd008-133">Não o diretório raiz do sistema de arquivos do Windows: `C:\Users\<user name>\Project`</span><span class="sxs-lookup"><span data-stu-id="bd008-133">Not the Windows file system root directory: `C:\Users\<user name>\Project`</span></span>

<span data-ttu-id="bd008-134">Todas as distribuições atualmente em execução (`wsl -l`) podem ser acessadas por meio de uma conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="bd008-134">All currently running distributions (`wsl -l`) are accessible via network connection.</span></span> <span data-ttu-id="bd008-135">Para isso, execute um comando \[WIN+R\] (atalho de teclado) ou digite `\\wsl$` na barra de endereços do Explorador de Arquivos para localizar os respectivos nomes de distribuição e acessar os sistemas de arquivos raiz.</span><span class="sxs-lookup"><span data-stu-id="bd008-135">To get there run a command \[WIN+R\] (keyboard shortcut) or type in File Explorer address bar `\\wsl$` to find respective distribution names and access their root file systems.</span></span>

<span data-ttu-id="bd008-136">Também será possível usar comandos do Windows dentro do [Terminal](https://en.wikipedia.org/wiki/Linux_console) Linux do WSL.</span><span class="sxs-lookup"><span data-stu-id="bd008-136">You can also use windows commands inside WSL's Linux [Terminal](https://en.wikipedia.org/wiki/Linux_console).</span></span> <span data-ttu-id="bd008-137">Tente abrir uma distribuição do Linux (como o Ubuntu) e verifique se você está no diretório base do Linux digitando este comando: `cd ~`.</span><span class="sxs-lookup"><span data-stu-id="bd008-137">Try opening a Linux distribution (ie Ubuntu), be sure that you are in the Linux home directory by entering this command: `cd ~`.</span></span> <span data-ttu-id="bd008-138">Em seguida, abra o sistema de arquivos do Linux no Explorador de Arquivos digitando *(não se esqueça do ponto no final)* : `powershell.exe /c start .`</span><span class="sxs-lookup"><span data-stu-id="bd008-138">Then open your Linux file system in File Explorer by entering *(don't forget the period at the end)* : `powershell.exe /c start .`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd008-139">Caso encontre este erro: **-bash: powershell.exe: comando não encontrado** , veja a [página de solução de problemas de WSL](troubleshooting.md#running-windows-commands-fails-inside-a-distribution) para resolvê-lo.</span><span class="sxs-lookup"><span data-stu-id="bd008-139">If you experience an error **-bash: powershell.exe: command not found** please refer to the [WSL troubleshooting page](troubleshooting.md#running-windows-commands-fails-inside-a-distribution) to resolve it.</span></span>

<span data-ttu-id="bd008-140">O WSL 2 só está disponível no Windows 10, versão 1903, Build 18362 ou superior.</span><span class="sxs-lookup"><span data-stu-id="bd008-140">WSL 2 is only available in Windows 10, Version 1903, Build 18362 or higher.</span></span> <span data-ttu-id="bd008-141">Verifique sua versão do Windows selecionando a **tecla do logotipo do Windows + R** , digite **winver** , selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd008-141">Check your Windows version by selecting the **Windows logo key + R** , type **winver** , select **OK**.</span></span> <span data-ttu-id="bd008-142">(Ou digite o comando `ver` no prompt de comando do Windows).</span><span class="sxs-lookup"><span data-stu-id="bd008-142">(Or enter the `ver` command in Windows Command Prompt).</span></span> <span data-ttu-id="bd008-143">Você pode precisar [atualizar para a última versão do Windows](ms-settings:windowsupdate).</span><span class="sxs-lookup"><span data-stu-id="bd008-143">You may need to [update to the latest Windows version](ms-settings:windowsupdate).</span></span> <span data-ttu-id="bd008-144">Para builds inferiores ao 18362, não há nenhum suporte para o WSL.</span><span class="sxs-lookup"><span data-stu-id="bd008-144">For builds lower than 18362, WSL is not supported at all.</span></span>

> [!NOTE]
> <span data-ttu-id="bd008-145">O WSL 2 funcionará com o [VMware 15.5.5+](https://blogs.vmware.com/workstation/2020/05/vmware-workstation-now-supports-hyper-v-mode.html) e o [VirtualBox 6+](https://www.virtualbox.org/wiki/Changelog-6.0).</span><span class="sxs-lookup"><span data-stu-id="bd008-145">WSL 2 will work with [VMware 15.5.5+](https://blogs.vmware.com/workstation/2020/05/vmware-workstation-now-supports-hyper-v-mode.html) and [VirtualBox 6+](https://www.virtualbox.org/wiki/Changelog-6.0).</span></span> <span data-ttu-id="bd008-146">Saiba mais nas [Perguntas frequentes do WSL 2.](./wsl2-faq.md#will-i-be-able-to-run-wsl-2-and-other-3rd-party-virtualization-tools-such-as-vmware-or-virtualbox)</span><span class="sxs-lookup"><span data-stu-id="bd008-146">Learn more in our [WSL 2 FAQs.](./wsl2-faq.md#will-i-be-able-to-run-wsl-2-and-other-3rd-party-virtualization-tools-such-as-vmware-or-virtualbox)</span></span>

## <a name="whats-new-in-wsl-2"></a><span data-ttu-id="bd008-147">Novidades no WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-147">What's new in WSL 2</span></span>

<span data-ttu-id="bd008-148">O WSL 2 é uma importante revisão da arquitetura subjacente e usa a tecnologia de virtualização e um kernel do Linux para habilitar os novos recursos.</span><span class="sxs-lookup"><span data-stu-id="bd008-148">WSL 2 is a major overhaul of the underlying architecture and uses virtualization technology and a Linux kernel to enable new features.</span></span> <span data-ttu-id="bd008-149">As metas principais dessa atualização são aumentar o desempenho do sistema de arquivos e adicionar compatibilidade total com chamadas do sistema.</span><span class="sxs-lookup"><span data-stu-id="bd008-149">The primary goals of this update are to increase file system performance and add full system call compatibility.</span></span>

- [<span data-ttu-id="bd008-150">Requisitos de sistema do WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-150">WSL 2 system requirements</span></span>](./install-win10.md#step-2---update-to-wsl-2)
- [<span data-ttu-id="bd008-151">Atualizar do WSL 1 para o WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-151">Update from WSL 1 to WSL 2</span></span>](./install-win10.md#step-2---update-to-wsl-2)
- [<span data-ttu-id="bd008-152">Perguntas frequentes sobre o WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-152">Frequently Asked Questions about WSL 2</span></span>](./wsl2-faq.md)

### <a name="wsl-2-architecture"></a><span data-ttu-id="bd008-153">Arquitetura do WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-153">WSL 2 architecture</span></span>

<span data-ttu-id="bd008-154">Uma experiência de VM tradicional poderá ter inicialização lenta, ser isolada, consumir muitos recursos e exigir o seu tempo para gerenciá-la.</span><span class="sxs-lookup"><span data-stu-id="bd008-154">A traditional VM experience can be slow to boot up, is isolated, consumes a lot of resources, and requires your time to manage it.</span></span> <span data-ttu-id="bd008-155">O WSL 2 não tem esses atributos.</span><span class="sxs-lookup"><span data-stu-id="bd008-155">WSL 2 does not have these attributes.</span></span>

<span data-ttu-id="bd008-156">O WSL 2 fornece os benefícios do WSL 1, incluindo integração direta entre o Windows e o Linux, tempos de inicialização rápidos, um pequeno volume de recursos e não requer nenhuma configuração ou gerenciamento de VM.</span><span class="sxs-lookup"><span data-stu-id="bd008-156">WSL 2 provides the benefits of WSL 1, including seamless integration between Windows and Linux, fast boot times, a small resource footprint, and requires no VM configuration or management.</span></span> <span data-ttu-id="bd008-157">Embora o WSL 2 use uma VM, ele é gerenciado e executado nos bastidores, deixando você com a mesma experiência do usuário que o WSL 1.</span><span class="sxs-lookup"><span data-stu-id="bd008-157">While WSL 2 does use a VM, it is managed and run behind the scenes, leaving you with the same user experience as WSL 1.</span></span>

### <a name="full-linux-kernel"></a><span data-ttu-id="bd008-158">Kernel do Linux completo</span><span class="sxs-lookup"><span data-stu-id="bd008-158">Full Linux kernel</span></span>

<span data-ttu-id="bd008-159">O kernel do Linux no WSL 2 é criado pela Microsoft usando a ramificação estável mais recente, com base na origem disponível em kernel.org. Esse kernel foi especialmente ajustado para o WSL 2, otimizando o tamanho e o desempenho para fornecer uma experiência incrível do Linux no Windows.</span><span class="sxs-lookup"><span data-stu-id="bd008-159">The Linux kernel in WSL 2 is built by Microsoft from the latest stable branch, based on the source available at kernel.org. This kernel has been specially tuned for WSL 2, optimizing for size and performance to provide an amazing Linux experience on Windows.</span></span> <span data-ttu-id="bd008-160">O kernel será atendido pelas atualizações do Windows, o que significa que você obterá as correções de segurança e aprimoramentos de kernel mais recentes sem precisar gerenciá-las por conta própria.</span><span class="sxs-lookup"><span data-stu-id="bd008-160">The kernel will be serviced by Windows updates, which means you will get the latest security fixes and kernel improvements without needing to manage it yourself.</span></span>

<span data-ttu-id="bd008-161">O [kernel do Linux do WSL 2 é de software livre](https://github.com/microsoft/WSL2-Linux-Kernel).</span><span class="sxs-lookup"><span data-stu-id="bd008-161">The [WSL 2 Linux kernel is open source](https://github.com/microsoft/WSL2-Linux-Kernel).</span></span> <span data-ttu-id="bd008-162">Se você quiser saber mais, confira a postagem no blog [Como enviar um kernel do Linux com o Windows](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/) escrito pela equipe que o criou.</span><span class="sxs-lookup"><span data-stu-id="bd008-162">If you'd like to learn more, check out the blog post [Shipping a Linux Kernel with Windows](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/) written by the team that built it.</span></span>

### <a name="increased-file-io-performance"></a><span data-ttu-id="bd008-163">Maior desempenho de E/S de arquivo</span><span class="sxs-lookup"><span data-stu-id="bd008-163">Increased file IO performance</span></span>

<span data-ttu-id="bd008-164">Operações com uso intensivo de arquivo, como comandos git clone, npm install, apt update, apt upgrade e muito mais, são visivelmente mais rápidas com o WSL 2.</span><span class="sxs-lookup"><span data-stu-id="bd008-164">File intensive operations like git clone, npm install, apt update, apt upgrade, and more are all noticeably faster with WSL 2.</span></span>

<span data-ttu-id="bd008-165">O aumento da velocidade real dependerá de qual aplicativo você está executando e de como ele está interagindo com o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bd008-165">The actual speed increase will depend on which app you're running and how it is interacting with the file system.</span></span> <span data-ttu-id="bd008-166">As versões iniciais do WSL 2 são executadas até 20 vezes mais rapidamente em comparação com o WSL 1 ao desempacotar um tarball compactado e de duas a cinco vezes mais rapidamente ao usar os comandos git clone, npm install e cmake em vários projetos.</span><span class="sxs-lookup"><span data-stu-id="bd008-166">Initial versions of WSL 2 run up to 20x faster compared to WSL 1 when unpacking a zipped tarball, and around 2-5x faster when using git clone, npm install and cmake on various projects.</span></span>

### <a name="full-system-call-compatibility"></a><span data-ttu-id="bd008-167">Compatibilidade total com a chamada do sistema</span><span class="sxs-lookup"><span data-stu-id="bd008-167">Full system call compatibility</span></span>

<span data-ttu-id="bd008-168">Os binários do Linux usam chamadas do sistema para executar funções, como acessar arquivos, solicitar memória, criar processos e muito mais.</span><span class="sxs-lookup"><span data-stu-id="bd008-168">Linux binaries use system calls to perform functions such as accessing files, requesting memory, creating processes, and more.</span></span> <span data-ttu-id="bd008-169">Enquanto o WSL 1 usava uma camada de conversão criada pela equipe do WSL, o WSL 2 inclui o próprio kernel Linux com compatibilidade total com a chamada do sistema.</span><span class="sxs-lookup"><span data-stu-id="bd008-169">Whereas WSL 1 used a translation layer that was built by the WSL team, WSL 2 includes its own Linux kernel with full system call compatibility.</span></span> <span data-ttu-id="bd008-170">Os benefícios incluem:</span><span class="sxs-lookup"><span data-stu-id="bd008-170">Benefits include:</span></span>

- <span data-ttu-id="bd008-171">Um conjunto totalmente novo de aplicativos que você pode executar dentro do WSL, como o **[Docker](tutorials/wsl-containers.md)** e muito mais.</span><span class="sxs-lookup"><span data-stu-id="bd008-171">A whole new set of apps that you can run inside of WSL, such as **[Docker](tutorials/wsl-containers.md)** and more.</span></span>

- <span data-ttu-id="bd008-172">Todas as atualizações para o kernel do Linux estão imediatamente prontas para uso.</span><span class="sxs-lookup"><span data-stu-id="bd008-172">Any updates to the Linux kernel are immediately ready for use.</span></span> <span data-ttu-id="bd008-173">(Você não precisa esperar que a equipe do WSL implemente atualizações e adicione as alterações).</span><span class="sxs-lookup"><span data-stu-id="bd008-173">(You don't have to wait for the WSL team to implement updates and add the changes).</span></span>

### <a name="wsl-2-uses-a-smaller-amount-of-memory-on-startup"></a><span data-ttu-id="bd008-174">O WSL 2 usa uma quantidade menor de memória na inicialização</span><span class="sxs-lookup"><span data-stu-id="bd008-174">WSL 2 uses a smaller amount of memory on startup</span></span>

<span data-ttu-id="bd008-175">O WSL 2 usa uma VM de utilitário leve em um kernel real do Linux com um pequeno volume de memória.</span><span class="sxs-lookup"><span data-stu-id="bd008-175">WSL 2 uses a lightweight utility VM on a real Linux kernel with a small memory footprint.</span></span> <span data-ttu-id="bd008-176">O utilitário alocará a memória com suporte de endereço virtual na inicialização.</span><span class="sxs-lookup"><span data-stu-id="bd008-176">The utility will allocate Virtual Address backed memory on startup.</span></span> <span data-ttu-id="bd008-177">Ela é configurada para começar com uma pequena proporção da memória total em comparação com a necessária para o WSL 1.</span><span class="sxs-lookup"><span data-stu-id="bd008-177">It is configured to start with a smaller proportion of your total memory that what was required for WSL 1.</span></span>

## <a name="exceptions-for-using-wsl-1-rather-than-wsl-2"></a><span data-ttu-id="bd008-178">Exceções para uso do WSL 1 em vez do WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-178">Exceptions for using WSL 1 rather than WSL 2</span></span>

<span data-ttu-id="bd008-179">Recomendamos que você use o WSL 2, pois ele oferece desempenho mais rápido e 100% de compatibilidade com a chamada do sistema.</span><span class="sxs-lookup"><span data-stu-id="bd008-179">We recommend that you use WSL 2 as it offers faster performance and 100% system call compatibility.</span></span> <span data-ttu-id="bd008-180">No entanto, há alguns cenários específicos em que você pode preferir usar o WSL 1.</span><span class="sxs-lookup"><span data-stu-id="bd008-180">However, there are a few specific scenarios where you might prefer using WSL 1.</span></span> <span data-ttu-id="bd008-181">Considere usar o WSL 1 se:</span><span class="sxs-lookup"><span data-stu-id="bd008-181">Consider using WSL 1 if:</span></span>

- <span data-ttu-id="bd008-182">Seus arquivos de projeto devem ser armazenados no sistema de arquivos do Windows.</span><span class="sxs-lookup"><span data-stu-id="bd008-182">Your project files must be stored in the Windows file system.</span></span> <span data-ttu-id="bd008-183">O WSL 1 oferece acesso mais rápido aos arquivos montados no Windows.</span><span class="sxs-lookup"><span data-stu-id="bd008-183">WSL 1 offers faster access to files mounted from Windows.</span></span>
  - <span data-ttu-id="bd008-184">Se estiver usando sua distribuição do WSL no Linux para acessar arquivos de projeto no sistema de arquivos do Windows e esses arquivos não puderem ser armazenados no sistema de arquivos do Linux, você obterá um desempenho melhor nos sistemas de arquivos do sistema operacional usando o WSL 1.</span><span class="sxs-lookup"><span data-stu-id="bd008-184">If you will be using your WSL Linux distribution to access project files on the Windows file system, and these files cannot be stored on the Linux file system, you will achieve faster performance across the OS files systems by using WSL 1.</span></span>
- <span data-ttu-id="bd008-185">Um projeto que requer compilação cruzada usando as ferramentas do Windows e do Linux nos mesmos arquivos.</span><span class="sxs-lookup"><span data-stu-id="bd008-185">A project which requires cross-compilation using both Windows and Linux tools on the same files.</span></span>
  - <span data-ttu-id="bd008-186">O desempenho de arquivos entre os sistemas operacionais do Windows e do Linux é mais rápido no WSL 1 do que no WSL 2, portanto, se estiver usando aplicativos do Windows para acessar arquivos do Linux, você obterá um desempenho melhor com o WSL 1.</span><span class="sxs-lookup"><span data-stu-id="bd008-186">File performance across the Windows and Linux operating systems is faster in WSL 1 than WSL 2, so if you are using Windows applications to access Linux files, you will currently achieve faster performance with WSL 1.</span></span>

> [!NOTE]
> <span data-ttu-id="bd008-187">Considere usar a [Extensão Remota do WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) do VS Code para permitir que você armazene seus arquivos de projeto no sistema de arquivos do Linux, usando as ferramentas de linha de comando do Linux, mas também usando o VS Code no Windows para criar, editar, depurar ou executar seu projeto em um navegador da Internet sem a lentidão de desempenho associada ao trabalho nos sistemas de arquivos Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="bd008-187">Consider trying the VS Code [Remote WSL Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) to enable you to store your project files on the Linux file system, using Linux command line tools, but also using VS Code on Windows to author, edit, debug, or run your project in an internet browser without any of the performance slow-downs associated with working across the Linux and Windows file systems.</span></span> <span data-ttu-id="bd008-188">[Saiba mais](tutorials/wsl-vscode.md).</span><span class="sxs-lookup"><span data-stu-id="bd008-188">[Learn more](tutorials/wsl-vscode.md).</span></span>

## <a name="accessing-network-applications"></a><span data-ttu-id="bd008-189">Acessar aplicativos de rede</span><span class="sxs-lookup"><span data-stu-id="bd008-189">Accessing network applications</span></span>

### <a name="accessing-linux-networking-apps-from-windows-localhost"></a><span data-ttu-id="bd008-190">Como acessar aplicativos de rede do Linux no Windows (localhost)</span><span class="sxs-lookup"><span data-stu-id="bd008-190">Accessing Linux networking apps from Windows (localhost)</span></span>

<span data-ttu-id="bd008-191">Se você estiver criando um aplicativo de rede (por exemplo, um aplicativo em execução em um NodeJS ou SQL Server) em sua distribuição do Linux, poderá acessá-lo de um aplicativo do Windows (como seu navegador de Internet Microsoft Edge ou Chrome) usando `localhost` (assim como faria normalmente).</span><span class="sxs-lookup"><span data-stu-id="bd008-191">If you are building a networking app (for example an app running on a NodeJS or SQL server) in your Linux distribution, you can access it from a Windows app (like your Edge or Chrome internet browser) using `localhost` (just like you normally would).</span></span>

<span data-ttu-id="bd008-192">No entanto, se você estiver executando uma versão mais antiga do Windows (Build 18945 ou anterior), será necessário obter o endereço IP da VM host do Linux (ou [atualizar para a versão mais recente do Windows](ms-settings:windowsupdate)).</span><span class="sxs-lookup"><span data-stu-id="bd008-192">However, if you are running an older version of Windows (Build 18945 or less), you will need to get the IP address of the Linux host VM (or [update to the latest Windows version](ms-settings:windowsupdate)).</span></span>

<span data-ttu-id="bd008-193">Para localizar o endereço IP da máquina virtual que está capacitando sua distribuição do Linux:</span><span class="sxs-lookup"><span data-stu-id="bd008-193">To find the IP address of the virtual machine powering your Linux distribution:</span></span>

- <span data-ttu-id="bd008-194">Em sua distribuição do WSL (por exemplo, Ubuntu), execute o comando: `ip addr`</span><span class="sxs-lookup"><span data-stu-id="bd008-194">From your WSL distribution (ie Ubuntu), run the command: `ip addr`</span></span>
- <span data-ttu-id="bd008-195">Localize e copie o endereço no valor `inet` da interface `eth0`.</span><span class="sxs-lookup"><span data-stu-id="bd008-195">Find and copy the address under the `inet` value of the `eth0` interface.</span></span>
- <span data-ttu-id="bd008-196">Se você tiver a ferramenta grep instalada, encontre-a mais facilmente filtrando a saída com o comando: `ip addr | grep eth0`</span><span class="sxs-lookup"><span data-stu-id="bd008-196">If you have the grep tool installed, find this more easily by filtering the output with the command: `ip addr | grep eth0`</span></span>
- <span data-ttu-id="bd008-197">Conecte-se ao seu servidor Linux usando esse endereço IP.</span><span class="sxs-lookup"><span data-stu-id="bd008-197">Connect to your Linux server using this IP address.</span></span>

<span data-ttu-id="bd008-198">A imagem abaixo mostra um exemplo disso por meio da conexão com um servidor Node.js usando o navegador Edge.</span><span class="sxs-lookup"><span data-stu-id="bd008-198">The picture below shows an example of this by connecting to a Node.js server using the Edge browser.</span></span>

![Conectar-se ao servidor NodeJS com o Edge](media/wsl2-network-w2l.jpg)

### <a name="accessing-windows-networking-apps-from-linux-host-ip"></a><span data-ttu-id="bd008-200">Como acessar aplicativos de rede do Windows no Linux (IP do host)</span><span class="sxs-lookup"><span data-stu-id="bd008-200">Accessing Windows networking apps from Linux (host IP)</span></span>

<span data-ttu-id="bd008-201">Se quiser acessar um aplicativo de rede em execução no Windows (por exemplo, um aplicativo em execução em um NodeJS ou SQL Server) de sua distribuição do Linux (por exemplo, Ubuntu), você precisará usar o endereço IP do seu computador host.</span><span class="sxs-lookup"><span data-stu-id="bd008-201">If you want to access a networking app running on Windows (for example an app running on a NodeJS or SQL server) from your Linux distribution (ie Ubuntu), then you need to use the IP address of your host machine.</span></span> <span data-ttu-id="bd008-202">Embora esse não seja um cenário comum, você pode seguir estas etapas para fazê-lo funcionar.</span><span class="sxs-lookup"><span data-stu-id="bd008-202">While this is not a common scenario, you can follow these steps to make it work.</span></span>

1. <span data-ttu-id="bd008-203">Obtenha o endereço IP do seu computador host executando este comando da sua distribuição do Linux: `cat /etc/resolv.conf`</span><span class="sxs-lookup"><span data-stu-id="bd008-203">Obtain the IP address of your host machine by running this command from your Linux distribution: `cat /etc/resolv.conf`</span></span>
2. <span data-ttu-id="bd008-204">Copie o endereço IP após o termo: `nameserver`.</span><span class="sxs-lookup"><span data-stu-id="bd008-204">Copy the IP address following the term: `nameserver`.</span></span>
3. <span data-ttu-id="bd008-205">Conecte-se a qualquer servidor Windows usando o endereço IP copiado.</span><span class="sxs-lookup"><span data-stu-id="bd008-205">Connect to any Windows server using the copied IP address.</span></span>

<span data-ttu-id="bd008-206">A imagem abaixo mostra um exemplo disso por meio da conexão com um servidor Node.js em execução no Windows via curl.</span><span class="sxs-lookup"><span data-stu-id="bd008-206">The picture below shows an example of this by connecting to a Node.js server running in Windows via curl.</span></span>

![Conectar-se ao servidor NodeJS no Windows via Curl](media/wsl2-network-l2w.png)

### <a name="additional-networking-considerations"></a><span data-ttu-id="bd008-208">Considerações adicionais de rede</span><span class="sxs-lookup"><span data-stu-id="bd008-208">Additional networking considerations</span></span>

#### <a name="connecting-via-remote-ip-addresses"></a><span data-ttu-id="bd008-209">Conectar-se via endereços IP remotos</span><span class="sxs-lookup"><span data-stu-id="bd008-209">Connecting via remote IP addresses</span></span>

<span data-ttu-id="bd008-210">Ao usar endereços IP remotos para se conectar aos seus aplicativos, eles serão tratados como conexões de LAN (rede local).</span><span class="sxs-lookup"><span data-stu-id="bd008-210">When using remote IP addresses to connect to your applications, they will be treated as connections from the Local Area Network (LAN).</span></span> <span data-ttu-id="bd008-211">Isso significa que você precisará verificar se seu aplicativo pode aceitar conexões de LAN.</span><span class="sxs-lookup"><span data-stu-id="bd008-211">This means that you will need to make sure your application can accept LAN connections.</span></span>

<span data-ttu-id="bd008-212">Por exemplo, talvez seja necessário associar seu aplicativo a `0.0.0.0` em vez de `127.0.0.1`.</span><span class="sxs-lookup"><span data-stu-id="bd008-212">For example, you may need to bind your application to `0.0.0.0` instead of `127.0.0.1`.</span></span> <span data-ttu-id="bd008-213">No exemplo de um aplicativo Python usando Flask, isso pode ser feito com o comando: `app.run(host='0.0.0.0')`.</span><span class="sxs-lookup"><span data-stu-id="bd008-213">In the example of a Python app using Flask, this can be done with the command: `app.run(host='0.0.0.0')`.</span></span> <span data-ttu-id="bd008-214">Tenha em mente a segurança ao fazer essas alterações, pois isso permitirá conexões de sua LAN.</span><span class="sxs-lookup"><span data-stu-id="bd008-214">Please keep security in mind when making these changes as this will allow connections from your LAN.</span></span>

#### <a name="accessing-a-wsl-2-distribution-from-your-local-area-network-lan"></a><span data-ttu-id="bd008-215">Como acessar uma distribuição do WSL 2 usando a LAN (rede local)</span><span class="sxs-lookup"><span data-stu-id="bd008-215">Accessing a WSL 2 distribution from your local area network (LAN)</span></span>

<span data-ttu-id="bd008-216">Ao usar uma distribuição do WSL 1, se o computador tiver sido configurado para ser acessado pela sua LAN, os aplicativos executados no WSL também poderão ser acessados em sua LAN.</span><span class="sxs-lookup"><span data-stu-id="bd008-216">When using a WSL 1 distribution, if your computer was set up to be accessed by your LAN, then applications run in WSL could be accessed on your LAN as well.</span></span>

<span data-ttu-id="bd008-217">Esse não é o caso padrão no WSL 2.</span><span class="sxs-lookup"><span data-stu-id="bd008-217">This isn't the default case in WSL 2.</span></span> <span data-ttu-id="bd008-218">O WSL 2 tem um adaptador Ethernet virtualizado com um endereço IP exclusivo.</span><span class="sxs-lookup"><span data-stu-id="bd008-218">WSL 2 has a virtualized ethernet adapter with its own unique IP address.</span></span> <span data-ttu-id="bd008-219">No momento, para habilitar esse fluxo de trabalho, será necessário percorrer as mesmas etapas que você faria para uma máquina virtual normal.</span><span class="sxs-lookup"><span data-stu-id="bd008-219">Currently, to enable this workflow you will need to go through the same steps as you would for a regular virtual machine.</span></span> <span data-ttu-id="bd008-220">(Estamos analisando maneiras de aprimorar essa experiência.)</span><span class="sxs-lookup"><span data-stu-id="bd008-220">(We are looking into ways to improve this experience.)</span></span>

<span data-ttu-id="bd008-221">Veja um comando do PowerShell de exemplo para adicionar um proxy de porta que escuta na porta 4000 no host e o conecta à porta 4000 para a VM do WSL 2 com o endereço IP 192.168.101.100.</span><span class="sxs-lookup"><span data-stu-id="bd008-221">Here's an example PowerShell command to add a port proxy that listens on port 4000 on the host and connects it to port 4000 to the WSL 2 VM with IP address 192.168.101.100.</span></span>

```powershell
netsh interface portproxy add v4tov4 listenport=4000 listenaddress=0.0.0.0 connectport=4000 connectaddress=192.168.101.100
```

#### <a name="ipv6-access"></a><span data-ttu-id="bd008-222">Acesso IPv6</span><span class="sxs-lookup"><span data-stu-id="bd008-222">IPv6 access</span></span>

<span data-ttu-id="bd008-223">Atualmente, as distribuições do WSL 2 não conseguem acessar endereços IPv6.</span><span class="sxs-lookup"><span data-stu-id="bd008-223">WSL 2 distributions currently cannot reach IPv6-only addresses.</span></span> <span data-ttu-id="bd008-224">Estamos trabalhando para adicionar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="bd008-224">We are working on adding this feature.</span></span>

## <a name="expanding-the-size-of-your-wsl-2-virtual-hard-disk"></a><span data-ttu-id="bd008-225">Como expandir o tamanho do seu Disco Rígido Virtual do WSL 2</span><span class="sxs-lookup"><span data-stu-id="bd008-225">Expanding the size of your WSL 2 Virtual Hard Disk</span></span>

<span data-ttu-id="bd008-226">O WSL 2 usa um VHD (Disco Rígido Virtual) para armazenar os seus arquivos do Linux.</span><span class="sxs-lookup"><span data-stu-id="bd008-226">WSL 2 uses a Virtual Hard Disk (VHD) to store your Linux files.</span></span> <span data-ttu-id="bd008-227">No WSL 2, um VHD é representado no seu disco rígido do Windows como um arquivo *.vhdx*.</span><span class="sxs-lookup"><span data-stu-id="bd008-227">In WSL 2, a VHD is represented on your Windows hard drive as a *.vhdx* file.</span></span>

<span data-ttu-id="bd008-228">O VHD do WSL 2 usa o sistema de arquivos ext4.</span><span class="sxs-lookup"><span data-stu-id="bd008-228">The WSL 2 VHD uses the ext4 file system.</span></span> <span data-ttu-id="bd008-229">Esse VHD é redimensionado automaticamente para atender às suas necessidades de armazenamento e tem um tamanho máximo inicial de 256 GB.</span><span class="sxs-lookup"><span data-stu-id="bd008-229">This VHD automatically resizes to meet your storage needs and has an initial maximum size of 256GB.</span></span> <span data-ttu-id="bd008-230">Se o espaço de armazenamento exigido pelos seus arquivos do Linux exceder esse tamanho, talvez seja necessário expandi-lo.</span><span class="sxs-lookup"><span data-stu-id="bd008-230">If the storage space required by your Linux files exceeds this size you may need to expand it.</span></span> <span data-ttu-id="bd008-231">Se a sua distribuição aumentar de tamanho para exceder 256 GB, você verá erros informando que você ficou sem espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="bd008-231">If your distribution grows in size to be greater than 256GB, you will see errors stating that you've run out of disk space.</span></span> <span data-ttu-id="bd008-232">Para corrigir esse erro, expanda o tamanho do VHD.</span><span class="sxs-lookup"><span data-stu-id="bd008-232">You can fix this error by expanding the VHD size.</span></span>

<span data-ttu-id="bd008-233">Para expandir o tamanho máximo do VHD para mais de 256 GB:</span><span class="sxs-lookup"><span data-stu-id="bd008-233">To expand your maximum VHD size beyond 256GB:</span></span>

1. <span data-ttu-id="bd008-234">Termine todas as instâncias do WSL usando o comando: `wsl --shutdown`</span><span class="sxs-lookup"><span data-stu-id="bd008-234">Terminate all WSL instances using the command: `wsl --shutdown`</span></span>

2. <span data-ttu-id="bd008-235">Localize o nome do pacote de instalação da distribuição ('PackageFamilyName')</span><span class="sxs-lookup"><span data-stu-id="bd008-235">Find your distribution installation package name ('PackageFamilyName')</span></span>
    - <span data-ttu-id="bd008-236">Usando o PowerShell (em que 'distro' é o nome da distribuição), insira o comando:</span><span class="sxs-lookup"><span data-stu-id="bd008-236">Using PowerShell (where 'distro' is your distribution name) enter the command:</span></span>
    - `Get-AppxPackage -Name "*<distro>*" | Select PackageFamilyName`

3. <span data-ttu-id="bd008-237">Localize arquivo VHD `fullpath` usado pela sua instalação do WSL 2, que será o seu `pathToVHD`:</span><span class="sxs-lookup"><span data-stu-id="bd008-237">Locate the VHD file `fullpath` used by your WSL 2 installation, this will be your `pathToVHD`:</span></span>
     - `%LOCALAPPDATA%\Packages\<PackageFamilyName>\LocalState\<disk>.vhdx`

4. <span data-ttu-id="bd008-238">Redimensione o VHD do WSL 2 concluindo os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="bd008-238">Resize your WSL 2 VHD by completing the following commands:</span></span>
   - <span data-ttu-id="bd008-239">Abra o prompt de comando do Windows com privilégios de administrador e digite:</span><span class="sxs-lookup"><span data-stu-id="bd008-239">Open Windows Command Prompt with admin privileges and enter:</span></span>

      ```powershell
      diskpart
      DISKPART> Select vdisk file="<pathToVHD>"
      DISKPART> detail vdisk
      ```

   - <span data-ttu-id="bd008-240">Examine o resultado do comando **detail**.</span><span class="sxs-lookup"><span data-stu-id="bd008-240">Examine the output of the **detail** command.</span></span>  <span data-ttu-id="bd008-241">A saída incluirá um valor para **Tamanho virtual**.</span><span class="sxs-lookup"><span data-stu-id="bd008-241">The output will include a value for **Virtual size**.</span></span>  <span data-ttu-id="bd008-242">Esse é o valor máximo atual.</span><span class="sxs-lookup"><span data-stu-id="bd008-242">This is the current maximum.</span></span>  <span data-ttu-id="bd008-243">Converta-o em megabytes.</span><span class="sxs-lookup"><span data-stu-id="bd008-243">Convert this value to megabytes.</span></span>  <span data-ttu-id="bd008-244">O novo valor após o redimensionamento precisa ser maior que esse valor.</span><span class="sxs-lookup"><span data-stu-id="bd008-244">The new value after resizing must be greater than this value.</span></span>  <span data-ttu-id="bd008-245">Por exemplo, se a saída de **detail** mostrar **Tamanho virtual: 256 GB** , você precisará especificar um valor maior que **256000**.</span><span class="sxs-lookup"><span data-stu-id="bd008-245">For example, if the **detail** output shows **Virtual size: 256 GB** , then you must specify a value greater than **256000**.</span></span>  <span data-ttu-id="bd008-246">Quando você tiver o seu novo tamanho em megabytes, insira o seguinte comando em **diskpart** :</span><span class="sxs-lookup"><span data-stu-id="bd008-246">Once you have your new size in megabytes, enter the following command in **diskpart** :</span></span>

      ```powershell
      DISKPART> expand vdisk maximum=<sizeInMegaBytes>
      ```

   - <span data-ttu-id="bd008-247">Saia de **diskpart**</span><span class="sxs-lookup"><span data-stu-id="bd008-247">Exit **diskpart**</span></span>

      ```powershell
      DISKPART> exit
      ```

5. <span data-ttu-id="bd008-248">Inicie sua distribuição do WSL (Ubuntu, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="bd008-248">Launch your WSL distribution (Ubuntu, for example).</span></span>

6. <span data-ttu-id="bd008-249">Informe ao WSL que ele pode expandir o tamanho do sistema de arquivos executando esses comandos na linha de comando de distribuição do Linux.</span><span class="sxs-lookup"><span data-stu-id="bd008-249">Make WSL aware that it can expand its file system's size by running these commands from your Linux distribution command line.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bd008-250">Você pode ver essa mensagem em resposta ao primeiro comando **mount** : **/dev: none already mounted on /dev**.</span><span class="sxs-lookup"><span data-stu-id="bd008-250">You may see this message in response to the first **mount** command: **/dev: none already mounted on /dev**.</span></span>  <span data-ttu-id="bd008-251">Essa mensagem pode ser ignorada com segurança.</span><span class="sxs-lookup"><span data-stu-id="bd008-251">This message can safely be ignored.</span></span>

   ```powershell
      sudo mount -t devtmpfs none /dev
      mount | grep ext4
   ```

   <span data-ttu-id="bd008-252">Copie o nome dessa entrada, que terá a seguinte aparência: `/dev/sdX` (em que X representa qualquer outro caractere).</span><span class="sxs-lookup"><span data-stu-id="bd008-252">Copy the name of this entry, which will look like: `/dev/sdX` (with the X representing any other character).</span></span>  <span data-ttu-id="bd008-253">No seguinte exemplo, o valor de **X** é **b** :</span><span class="sxs-lookup"><span data-stu-id="bd008-253">In the following example the value of **X** is **b** :</span></span>

   ```powershell
      sudo resize2fs /dev/sdb <sizeInMegabytes>M
   ```

   > [!NOTE]
   > <span data-ttu-id="bd008-254">Talvez você também precise instalar o **resize2fs**.</span><span class="sxs-lookup"><span data-stu-id="bd008-254">You may need to install **resize2fs**.</span></span>  <span data-ttu-id="bd008-255">Nesse caso, você pode usar esse comando para instalá-lo: `sudo apt install resize2fs`.</span><span class="sxs-lookup"><span data-stu-id="bd008-255">If so, you can use this command to install it:  `sudo apt install resize2fs`.</span></span>

   <span data-ttu-id="bd008-256">A saída terá esta aparência:</span><span class="sxs-lookup"><span data-stu-id="bd008-256">The output will look similar to the following:</span></span>

   ```bash
      resize2fs 1.44.1 (24-Mar-2018)
      Filesystem at /dev/sdb is mounted on /; on-line resizing required
      old_desc_blocks = 32, new_desc_blocks = 38
      The filesystem on /dev/sdb is now 78643200 (4k) blocks long.
      ```

> [!NOTE]
> <span data-ttu-id="bd008-257">em geral, não modifique, mova ou acesse os arquivos relacionados ao WSL localizados dentro da sua pasta AppData usando as ferramentas ou os editores do Windows.</span><span class="sxs-lookup"><span data-stu-id="bd008-257">In general do not modify, move, or access the WSL related files located inside of your AppData folder using Windows tools or editors.</span></span> <span data-ttu-id="bd008-258">Isso pode fazer com que a distribuição do Linux fique corrompida.</span><span class="sxs-lookup"><span data-stu-id="bd008-258">Doing so could cause your Linux distribution to become corrupted.</span></span>
