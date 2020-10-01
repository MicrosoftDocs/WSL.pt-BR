---
title: Perguntas frequentes (FAQ)
description: Encontre respostas para perguntas frequentes sobre o Subsistema do Windows para Linux, como 'O que posso fazer com o WSL?'.
keywords: BashOnWindows, bash, wsl, windows, windowssubsystem, faq
ms.date: 09/15/2020
ms.topic: article
ms.assetid: 129101ed-b88a-43c2-b6a2-cd2c4ff6fee1
ms.localizationpriority: high
ms.openlocfilehash: f769261bab35619b034e2a84e4f308eeb0a93cb4
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413236"
---
# <a name="frequently-asked-questions-about-windows-subsystem-for-linux"></a><span data-ttu-id="29217-104">Perguntas frequentes sobre o Subsistema Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="29217-104">Frequently Asked Questions about Windows Subsystem for Linux</span></span>

## <a name="what-is-windows-subsystem-for-linux-wsl"></a><span data-ttu-id="29217-105">O que é o WSL (Subsistema Windows para Linux)?</span><span class="sxs-lookup"><span data-stu-id="29217-105">What is Windows Subsystem for Linux (WSL)?</span></span>

<span data-ttu-id="29217-106">O Subsistema Windows para Linux (WSL) é um novo recurso do Windows 10 que habilita e execução de ferramentas de linha de comando nativas do Linux diretamente no Windows, juntamente com sua área de trabalho tradicional do Windows e os aplicativos de loja modernos.</span><span class="sxs-lookup"><span data-stu-id="29217-106">The Windows Subsystem for Linux (WSL) is a new Windows 10 feature that enables you to run native Linux command-line tools directly on Windows, alongside your traditional Windows desktop and modern store apps.</span></span>

<span data-ttu-id="29217-107">Consulte a [página Sobre](./about.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="29217-107">See the [about page](./about.md) for more details.</span></span>

## <a name="who-is-wsl-for"></a><span data-ttu-id="29217-108">Para quem é o WSL?</span><span class="sxs-lookup"><span data-stu-id="29217-108">Who is WSL for?</span></span>

<span data-ttu-id="29217-109">Ela é basicamente uma ferramenta para desenvolvedores – especialmente desenvolvedores da Web e aqueles que trabalham em ou com projetos de software livre.</span><span class="sxs-lookup"><span data-stu-id="29217-109">This is primarily a tool for developers -- especially web developers and those who work on or with open source projects.</span></span> <span data-ttu-id="29217-110">Isso permite que aqueles que desejam/precisam usar Bash, ferramentas comuns do Linux (`sed`, `awk`, etc.) e muitas linguagens para Linux (Ruby, Python, etc.) usem suas cadeias de ferramentas no Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-110">This allows those who want/need to use Bash, common Linux tools (`sed`, `awk`, etc.) and many Linux-first tools (Ruby, Python, etc.) to use their toolchain on Windows.</span></span>

## <a name="what-can-i-do-with-wsl"></a><span data-ttu-id="29217-111">O que posso fazer com o WSL?</span><span class="sxs-lookup"><span data-stu-id="29217-111">What can I do with WSL?</span></span>

<span data-ttu-id="29217-112">O WSL fornece um aplicativo chamado Bash.exe que, quando iniciado, abre um console do Windows que executa o shell Bash.</span><span class="sxs-lookup"><span data-stu-id="29217-112">WSL provides an application called Bash.exe that, when started, opens a Windows console running the Bash shell.</span></span> <span data-ttu-id="29217-113">Usando o Bash, você pode executar aplicativos e ferramentas de linha de comando do Linux.</span><span class="sxs-lookup"><span data-stu-id="29217-113">Using Bash, you can run command-line Linux tools and apps.</span></span> <span data-ttu-id="29217-114">Por exemplo, digite `lsb_release -a` e pressione Enter. Você verá os detalhes da distribuição do Linux em execução no momento:</span><span class="sxs-lookup"><span data-stu-id="29217-114">For example, type `lsb_release -a` and hit enter; you’ll see details of the Linux distro currently running:</span></span>

![Captura de tela dos detalhes da distribuição](media/distro.png)

<span data-ttu-id="29217-116">Você também pode acessar o sistema de arquivos do computador local de dentro do shell do Linux Bash – você encontrará as unidades locais montadas na pasta `/mnt`.</span><span class="sxs-lookup"><span data-stu-id="29217-116">You can also access your local machine’s filesystem from within the Linux Bash shell – you’ll find your local drives mounted under the `/mnt` folder.</span></span> <span data-ttu-id="29217-117">Por exemplo, sua unidade `C:` está montada em `/mnt/c`:</span><span class="sxs-lookup"><span data-stu-id="29217-117">For example, your `C:` drive is mounted under `/mnt/c`:</span></span>  

![Captura de tela da unidade C montada](media/ls.png)

## <a name="could-you-describe-a-typical-development-workflow-that-incorporates-wsl"></a><span data-ttu-id="29217-119">Você poderia descrever um fluxo de trabalho de desenvolvimento típico que incorpora o WSL?</span><span class="sxs-lookup"><span data-stu-id="29217-119">Could you describe a typical development workflow that incorporates WSL?</span></span>

<span data-ttu-id="29217-120">O WSL é destinado a desenvolvedores, com a intenção de ser usado como parte de um loop de desenvolvimento interno.</span><span class="sxs-lookup"><span data-stu-id="29217-120">WSL targets a developer audience with the intent to be used as part of an inner development loop.</span></span> <span data-ttu-id="29217-121">Digamos que Pedro esteja criando um pipeline de CI/CD (integração contínua e entrega contínua) e queira testá-lo primeiro em um computador local (laptop) antes de implantá-lo na nuvem.</span><span class="sxs-lookup"><span data-stu-id="29217-121">Let's say that Sam is creating a CI/CD pipeline (Continuous Integration & Continuous Delivery) and wants to test it first on a local machine (laptop) before deploying it to the cloud.</span></span> <span data-ttu-id="29217-122">O Pedro poderá habilitar o WSL (e o WSL 2 para melhorar a velocidade e o desempenho) e, em seguida, usar uma instância do Linux Ubuntu autêntica localmente (no laptop) com quaisquer comandos e ferramentas de bash que preferir.</span><span class="sxs-lookup"><span data-stu-id="29217-122">Sam can enable WSL (& WSL 2 to improve speed and performance), and then use a genuine Linux Ubuntu instance locally (on the laptop) with whatever Bash commands and tools they prefer.</span></span> <span data-ttu-id="29217-123">Depois de verificar o pipeline de desenvolvimento localmente, Pedro pode enviar por push esse pipeline de CI/CD para a nuvem (ou seja, para o Azure), colocando-o em um contêiner do Docker e enviando o contêiner para uma instância de nuvem em que ele é executado em uma VM Ubuntu pronta para produção.</span><span class="sxs-lookup"><span data-stu-id="29217-123">Once the development pipeline is verified locally, Sam can then push that CI/CD pipeline up to the cloud (ie Azure) by making it into a Docker container and pushing the container to a cloud instance where it runs on a production-ready Ubuntu VM.</span></span>

## <a name="what-is-bash"></a><span data-ttu-id="29217-124">O que é o Bash?</span><span class="sxs-lookup"><span data-stu-id="29217-124">What is Bash?</span></span>

<span data-ttu-id="29217-125">O [Bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) é uma linguagem de comando e shell baseado em texto popular.</span><span class="sxs-lookup"><span data-stu-id="29217-125">[Bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) is a popular text-based shell and command-language.</span></span> <span data-ttu-id="29217-126">É o shell padrão incluído no Ubuntu e em outras distribuições do Linux e no macOS.</span><span class="sxs-lookup"><span data-stu-id="29217-126">It is the default shell included within Ubuntu and other Linux distros, and in macOS.</span></span> <span data-ttu-id="29217-127">Os usuários digitam comandos em um shell para executar scripts e/ou executar comandos e ferramentas para realizar muitas tarefas.</span><span class="sxs-lookup"><span data-stu-id="29217-127">Users type commands into a shell to execute scripts and/or run commands and tools to accomplish many tasks.</span></span>

## <a name="how-does-this-work"></a><span data-ttu-id="29217-128">Como isso funciona?</span><span class="sxs-lookup"><span data-stu-id="29217-128">How does this work?</span></span>

<span data-ttu-id="29217-129">Confira nosso [blog](/archive/blogs/wsl/) com os detalhes sobre a tecnologia subjacente.</span><span class="sxs-lookup"><span data-stu-id="29217-129">Check out our [blog](/archive/blogs/wsl/) where we go into detail about the underlying technology.</span></span>

## <a name="why-would-i-use-wsl-rather-than-linux-in-a-vm"></a><span data-ttu-id="29217-130">Por que usar o WSL em vez do Linux em uma VM?</span><span class="sxs-lookup"><span data-stu-id="29217-130">Why would I use WSL rather than Linux in a VM?</span></span>

<span data-ttu-id="29217-131">O WSL requer menos recursos (CPU, memória e armazenamento) do que uma máquina virtual completa.</span><span class="sxs-lookup"><span data-stu-id="29217-131">WSL requires fewer resources (CPU, memory, and storage) than a full virtual machine.</span></span> <span data-ttu-id="29217-132">O WSL também permite que você execute aplicativos e ferramentas de linha de comando do Linux juntamente com os aplicativos de linha de comando, da área de trabalho e da loja do Windows, além de acessar os arquivos do Windows de dentro do Linux.</span><span class="sxs-lookup"><span data-stu-id="29217-132">WSL also allows you to run Linux command-line tools and apps alongside your Windows command-line, desktop and store apps, and to access your Windows files from within Linux.</span></span> <span data-ttu-id="29217-133">Isso habilita você a usar aplicativos do Windows e ferramentas de linha de comando do Linux no mesmo conjunto de arquivos, se desejar.</span><span class="sxs-lookup"><span data-stu-id="29217-133">This enables you to use Windows apps and Linux command-line tools on the same set of files if you wish.</span></span>

## <a name="why-would-i-use-for-example-ruby-on-linux-instead-of-on-windows"></a><span data-ttu-id="29217-134">Por que eu usaria, por exemplo, o Ruby no Linux em vez de no Windows?</span><span class="sxs-lookup"><span data-stu-id="29217-134">Why would I use, for example, Ruby on Linux instead of on Windows?</span></span>

<span data-ttu-id="29217-135">Algumas ferramentas multiplataforma foram criadas supondo que o ambiente no qual elas são executadas se comporta como o Linux.</span><span class="sxs-lookup"><span data-stu-id="29217-135">Some cross-platform tools were built assuming that the environment in which they run behaves like Linux.</span></span> <span data-ttu-id="29217-136">Por exemplo, algumas ferramentas pressupõem que elas são capazes de acessar caminhos de arquivo muito longos ou que arquivos/pastas específicos existam.</span><span class="sxs-lookup"><span data-stu-id="29217-136">For example, some tools assume that they are able to access very long file paths or that specific files/folders exist.</span></span> <span data-ttu-id="29217-137">Isso geralmente causa problemas no Windows que, com frequência, se comporta de forma diferente do Linux.</span><span class="sxs-lookup"><span data-stu-id="29217-137">This often causes problems on Windows which often behaves differently from Linux.</span></span>

<span data-ttu-id="29217-138">Muitas linguagens, como Ruby e Node, costumam ser modeladas e funcionam muito bem no Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-138">Many languages like Ruby and node are often ported to, and run great, on Windows.</span></span> <span data-ttu-id="29217-139">No entanto, nem todos os proprietários do Ruby Gem ou de bibliotecas do Node/NPM têm suas bibliotecas para dar suporte ao Windows e muitos têm dependências específicas do Linux.</span><span class="sxs-lookup"><span data-stu-id="29217-139">However, not all of the Ruby Gem or node/NPM library owners port their libraries to support Windows, and many have Linux-specific dependencies.</span></span> <span data-ttu-id="29217-140">Isso geralmente pode resultar em sistemas criados usando ferramentas e bibliotecas com problemas de build e, às vezes, erros de runtime ou comportamentos indesejados no Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-140">This can often result in systems built using such tools and libraries suffering from build and sometimes runtime errors or unwanted behaviors on Windows.</span></span>

<span data-ttu-id="29217-141">Esses são apenas alguns dos problemas que fizeram com que muitas pessoas pedissem à Microsoft para aprimorar as ferramentas de linha de comando do Windows e o que nos levou a fazer parcerias com a Canonical para habilitar as ferramentas de linha de comando do Linux e do Bash nativas para serem executadas no Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-141">These are just some of issues that caused many people to ask Microsoft to improve Windows’ command-line tools and what drove us to partner with Canonical to enable native Bash and Linux command-line tools to run on Windows.</span></span>

## <a name="what-does-this-mean-for-powershell"></a><span data-ttu-id="29217-142">O que isso significa para o PowerShell?</span><span class="sxs-lookup"><span data-stu-id="29217-142">What does this mean for PowerShell?</span></span>

<span data-ttu-id="29217-143">Ao trabalhar com projetos OSS, há inúmeros cenários em que é imensamente útil entrar no Bash usando um prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29217-143">While working with OSS projects, there are numerous scenarios where it’s immensely useful to drop into Bash from a PowerShell prompt.</span></span> <span data-ttu-id="29217-144">O suporte para Bash é complementar e fortalece o valor da linha de comando no Windows, permitindo que o PowerShell e a comunidade do PowerShell aproveitem outras tecnologias populares.</span><span class="sxs-lookup"><span data-stu-id="29217-144">Bash support is complementary and strengthens the value of the command-line on Windows, allowing PowerShell and the PowerShell community to leverage other popular technologies.</span></span>

<span data-ttu-id="29217-145">Leia mais no blog da equipe do PowerShell – [Bash para Windows: por que é incrível e o que significa para o PowerShell](https://blogs.msdn.microsoft.com/powershell/2016/04/01/bash-for-windows-why-its-awesome-and-what-it-means-for-powershell/)</span><span class="sxs-lookup"><span data-stu-id="29217-145">Read more on the PowerShell team blog -- [Bash for Windows: Why it’s awesome and what it means for PowerShell](https://blogs.msdn.microsoft.com/powershell/2016/04/01/bash-for-windows-why-its-awesome-and-what-it-means-for-powershell/)</span></span>

## <a name="can-i-run-all-linux-apps-in-wsl"></a><span data-ttu-id="29217-146">Posso executar TODOS os aplicativos do Linux no WSL?</span><span class="sxs-lookup"><span data-stu-id="29217-146">Can I run ALL Linux apps in WSL?</span></span>

<span data-ttu-id="29217-147">Não.</span><span class="sxs-lookup"><span data-stu-id="29217-147">No!</span></span> <span data-ttu-id="29217-148">O WSL é uma ferramenta que habilita os usuários a executar as principais ferramentas de linha de comando do Bash e do Linux no Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-148">WSL is a tool aimed at enabling users who need them to run Bash and core Linux command-line tools on Windows.</span></span>

<span data-ttu-id="29217-149">O WSL **NÃO** é compatível com aplicativos ou áreas de trabalho de GUI (por exemplo, Gnome, KDE, etc.)</span><span class="sxs-lookup"><span data-stu-id="29217-149">WSL does **not** aim to support GUI desktops or applications (e.g. Gnome, KDE, etc.)</span></span>  

<span data-ttu-id="29217-150">Além disso, embora você possa executar muitos aplicativos de servidor populares (por exemplo, Redis), não recomendamos o WSL para hospedar serviços de produção – a Microsoft oferece uma variedade de soluções para executar cargas de trabalho de produção do Linux no Azure, no Hyper-V e no Docker.</span><span class="sxs-lookup"><span data-stu-id="29217-150">Also, even though you will be able to run many popular server applications (e.g. Redis), we do not recommend WSL for hosting production services – Microsoft offers a variety of solutions for running production Linux workloads in Azure, Hyper-V, and Docker.</span></span> 

## <a name="what-windows-skus-is-wsl-included-in"></a><span data-ttu-id="29217-151">Em quais SKUs do Windows o WSL está incluído?</span><span class="sxs-lookup"><span data-stu-id="29217-151">What Windows SKUs is WSL included in?</span></span>

<span data-ttu-id="29217-152">O Subsistema Windows para Linux está disponível na versão de área de trabalho do Windows para a Atualização de Aniversário do Windows 10 e a Atualização do Windows 10 para Criadores ou posterior.</span><span class="sxs-lookup"><span data-stu-id="29217-152">Windows Subsystem for Linux is available on the desktop version of Windows for Windows 10 Anniversary and Creators update or later.</span></span>

<span data-ttu-id="29217-153">Iniciando na Fall Creators Update, o WSL estará disponível nas SKUs de desktop e de servidor do Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-153">Beginning in the Fall Creators update WSL will be available on both the desktop and server SKUs of Windows.</span></span>

## <a name="what-processors-does-wsl-support"></a><span data-ttu-id="29217-154">Com quais processadores o WSL é compatível?</span><span class="sxs-lookup"><span data-stu-id="29217-154">What processors does WSL support?</span></span>

<span data-ttu-id="29217-155">O WSL é compatível com CPUs x64 e ARM.</span><span class="sxs-lookup"><span data-stu-id="29217-155">WSL supports x64 and ARM CPUs.</span></span>

## <a name="how-do-i-access-my-c-drive"></a><span data-ttu-id="29217-156">Como acesso minha unidade C:?</span><span class="sxs-lookup"><span data-stu-id="29217-156">How do I access my C: drive?</span></span>

<span data-ttu-id="29217-157">Pontos de montagem para discos rígidos no computador local são criados automaticamente e fornecem acesso fácil ao sistema de arquivos do Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-157">Mount points for hard drives on the local machine are automatically created and provide easy access to the Windows filesystem.</span></span>

<span data-ttu-id="29217-158">**/mnt/\<drive letter>/**</span><span class="sxs-lookup"><span data-stu-id="29217-158">**/mnt/\<drive letter>/**</span></span>

<span data-ttu-id="29217-159">Um uso de exemplo seria `cd /mnt/c` para acessar c:</span><span class="sxs-lookup"><span data-stu-id="29217-159">Example usage would be `cd /mnt/c` to access c:</span></span>\

## <a name="how-do-i-set-up-git-credential-manager-how-do-i-use-my-windows-git-permissions-in-wsl"></a><span data-ttu-id="29217-160">Como configurar o Gerenciador de Credenciais do Git?</span><span class="sxs-lookup"><span data-stu-id="29217-160">How do I set up Git Credential Manager?</span></span> <span data-ttu-id="29217-161">(Como usar as permissões do Git do Windows no WSL?)</span><span class="sxs-lookup"><span data-stu-id="29217-161">(How do I use my Windows Git permissions in WSL?)</span></span> 

<span data-ttu-id="29217-162">O Gerenciador de Credenciais do Git permite autenticar um servidor Git remoto, mesmo se você tem um padrão de autenticação complexo como o Azure Active Directory ou a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="29217-162">Git Credential Manager enables you to authenticate a remote Git server, even if you have a complex authentication pattern like Azure Active Directory or two-factor authentication.</span></span> <span data-ttu-id="29217-163">O Gerenciador de Credenciais do Git se integra ao fluxo de autenticação para serviços como o GitHub e, uma vez que você está autenticado no provedor de hospedagem, solicita um novo token de autenticação.</span><span class="sxs-lookup"><span data-stu-id="29217-163">Git Credential Manager integrates into the authentication flow for services like GitHub and, once you're authenticated to your hosting provider, requests a new authentication token.</span></span> <span data-ttu-id="29217-164">Em seguida, armazena o token com segurança no Gerenciador de Credenciais do Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-164">It then stores the token securely in the Windows Credential Manager.</span></span> <span data-ttu-id="29217-165">Após a primeira vez, você pode usar o Git para se comunicar com seu provedor de hospedagem sem a necessidade de uma nova autenticação.</span><span class="sxs-lookup"><span data-stu-id="29217-165">After the first time, you can use git to talk to your hosting provider without needing to re-authenticate.</span></span> <span data-ttu-id="29217-166">Ele só acessará o token no Gerenciador de Credenciais do Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-166">It will just access the token in the Windows Credential Manager.</span></span>

<span data-ttu-id="29217-167">Para configurar o Gerenciador de Credenciais do Git para uso com uma distribuição do WSL, abra a distribuição e insira este comando:</span><span class="sxs-lookup"><span data-stu-id="29217-167">To set up Git Credential Manager for use with a WSL distribution, open your distribution and enter this command:</span></span>

```Bash
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe"
```

<span data-ttu-id="29217-168">Agora, todas as operações de git realizadas na distribuição do WSL usarão o Gerenciador de Credenciais.</span><span class="sxs-lookup"><span data-stu-id="29217-168">Now any git operation you perform within your WSL distribution will use the credential manager.</span></span> <span data-ttu-id="29217-169">Se você já tiver credenciais armazenadas em cache para um host, elas serão acessadas do Gerenciador de Credenciais.</span><span class="sxs-lookup"><span data-stu-id="29217-169">If you already have credentials cached for a host, it will access them from the credential manager.</span></span> <span data-ttu-id="29217-170">Caso contrário, você receberá uma resposta em uma caixa de diálogo solicitando suas credenciais, mesmo que esteja em um console do Linux.</span><span class="sxs-lookup"><span data-stu-id="29217-170">If not, you'll receive a dialog response requesting your credentials, even if you're in a Linux console.</span></span>

<span data-ttu-id="29217-171">Esse suporte depende da [interoperabilidade entre o Subsistema do Windows para Linux e o próprio Windows](./interop.md).</span><span class="sxs-lookup"><span data-stu-id="29217-171">This support relies on the [interoperability between Windows Subsystem for Linux and Windows itself](./interop.md).</span></span>

## <a name="how-do-i-use-a-windows-file-with-a-linux-app"></a><span data-ttu-id="29217-172">Como uso um arquivo do Windows com um aplicativo do Linux?</span><span class="sxs-lookup"><span data-stu-id="29217-172">How do I use a Windows file with a Linux app?</span></span>

<span data-ttu-id="29217-173">Um dos benefícios do WSL é a capacidade de acessar seus arquivos por meio de aplicativos ou ferramentas do Windows e do Linux.</span><span class="sxs-lookup"><span data-stu-id="29217-173">One of the benefits of WSL is being able to access your files via both Windows and Linux apps or tools.</span></span> 

<span data-ttu-id="29217-174">O WSL monta as unidades fixas do computador na pasta `/mnt/<drive>` em suas distribuições do Linux.</span><span class="sxs-lookup"><span data-stu-id="29217-174">WSL mounts your machine's fixed drives under the `/mnt/<drive>` folder in your Linux distros.</span></span> <span data-ttu-id="29217-175">Por exemplo, sua unidade `C:` está montada em `/mnt/c/`</span><span class="sxs-lookup"><span data-stu-id="29217-175">For example, your `C:` drive is mounted under `/mnt/c/`</span></span>

<span data-ttu-id="29217-176">Usando suas unidades montadas, você pode editar o código, por exemplo, `C:\dev\myproj\` usando o [Visual Studio](https://visualstudio.microsoft.com/vs/) ou o [VS Code](https://code.visualstudio.com/), e criar/testar esse código no Linux acessando os mesmos arquivos por meio do `/mnt/c/dev/myproj`.</span><span class="sxs-lookup"><span data-stu-id="29217-176">Using your mounted drives, you can edit code in, for example, `C:\dev\myproj\` using [Visual Studio](https://visualstudio.microsoft.com/vs/) / or [VS Code](https://code.visualstudio.com/), and build/test that code in Linux by accessing the same files via `/mnt/c/dev/myproj`.</span></span>

> <span data-ttu-id="29217-177">**OBSERVAÇÃO IMPORTANTE**: Uma das principais limitações do uso do WSL é que o acesso/alteração direta de arquivos em seu sistema de arquivos das distribuições do Linux usando aplicativos ou ferramentas do Windows não é compatível.</span><span class="sxs-lookup"><span data-stu-id="29217-177">**IMPORTANT NOTE**: One of the key limitations of using WSL is that directly accessing/changing files in your Linux distros' filesystem using Windows apps or tools is not supported.</span></span> <span data-ttu-id="29217-178">Consulte: [Não altere os arquivos do Linux usando ferramentas e aplicativos do Windows](https://blogs.msdn.microsoft.com/commandline/2016/11/17/do-not-change-linux-files-using-windows-apps-and-tools/)</span><span class="sxs-lookup"><span data-stu-id="29217-178">See: [Do not change Linux files using Windows apps and tools](https://blogs.msdn.microsoft.com/commandline/2016/11/17/do-not-change-linux-files-using-windows-apps-and-tools/)</span></span>

## <a name="are-files-in-the-linux-drive-different-from-the-mounted-windows-drive"></a><span data-ttu-id="29217-179">Os arquivos na unidade do Linux são diferentes da unidade montada do Windows?</span><span class="sxs-lookup"><span data-stu-id="29217-179">Are files in the Linux drive different from the mounted Windows drive?</span></span>

1. <span data-ttu-id="29217-180">Os arquivos na raiz do Linux (por exemplo, `/`) são controlados pelo WSL, que imita o comportamento específico do Linux, incluindo, sem limitações:</span><span class="sxs-lookup"><span data-stu-id="29217-180">Files under the Linux root (i.e. `/`) are controlled by WSL which mimics Linux specific behavior, including but not limited to:</span></span>
   * <span data-ttu-id="29217-181">Arquivos que contêm caracteres de nome de arquivo do Windows inválidos</span><span class="sxs-lookup"><span data-stu-id="29217-181">Files which contain invalid Windows filename characters</span></span>
   * <span data-ttu-id="29217-182">Symlinks criados para usuários não administradores</span><span class="sxs-lookup"><span data-stu-id="29217-182">Symlinks created for non-admin users</span></span>
   * <span data-ttu-id="29217-183">Como alterar atributos de arquivo usando chmod e chown</span><span class="sxs-lookup"><span data-stu-id="29217-183">Changing file attributes through chmod and chown</span></span>
   * <span data-ttu-id="29217-184">Diferenciação de maiúsculas e minúsculas de arquivo/pasta</span><span class="sxs-lookup"><span data-stu-id="29217-184">File/folder case sensitivity</span></span>

2. <span data-ttu-id="29217-185">Os arquivos em unidades montadas são controlados pelo Windows e têm os seguintes comportamentos:</span><span class="sxs-lookup"><span data-stu-id="29217-185">Files in mounted drives are controlled by Windows and have the following behaviors:</span></span>
   * <span data-ttu-id="29217-186">Suporte à diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="29217-186">Support case sensitivity</span></span>
   * <span data-ttu-id="29217-187">Todas as permissões são definidas para refletir melhor as permissões do Windows</span><span class="sxs-lookup"><span data-stu-id="29217-187">All permissions are set to best reflect the Windows permissions</span></span>

## <a name="why-are-there-so-many-errors-when-i-run-apt-get-upgrade"></a><span data-ttu-id="29217-188">Por que há muitos erros quando executo a atualização apt-get?</span><span class="sxs-lookup"><span data-stu-id="29217-188">Why are there so many errors when I run apt-get upgrade?</span></span>

<span data-ttu-id="29217-189">Alguns pacotes usam recursos que ainda não implementamos.</span><span class="sxs-lookup"><span data-stu-id="29217-189">Some packages use features that we haven't implemented yet.</span></span> <span data-ttu-id="29217-190">`udev`, por exemplo, ainda não é compatível e causa vários erros de `apt-get upgrade`.</span><span class="sxs-lookup"><span data-stu-id="29217-190">`udev`, for example, isn't supported yet and causes several `apt-get upgrade` errors.</span></span>

<span data-ttu-id="29217-191">Para corrigir problemas relacionados ao `udev`, siga as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="29217-191">To fix issues related to `udev`, follow the following steps:</span></span>

1. <span data-ttu-id="29217-192">Grave o seguinte no `/usr/sbin/policy-rc.d` e salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="29217-192">Write the following to `/usr/sbin/policy-rc.d` and save your changes.</span></span>

    ```bash
    #!/bin/sh
    exit 101
    ```

2. <span data-ttu-id="29217-193">Adicione permissões de execução a `/usr/sbin/policy-rc.d`</span><span class="sxs-lookup"><span data-stu-id="29217-193">Add execute permissions to `/usr/sbin/policy-rc.d`</span></span>

    ```bash
    chmod +x /usr/sbin/policy-rc.d
    ```
  
3. <span data-ttu-id="29217-194">Execute os comandos a seguir</span><span class="sxs-lookup"><span data-stu-id="29217-194">Run the following commands</span></span>

    ```bash
    dpkg-divert --local --rename --add /sbin/initctl
    ln -s /bin/true /sbin/initctl
    ```

## <a name="how-do-i-uninstall-a-wsl-distribution"></a><span data-ttu-id="29217-195">Como desinstalar uma distribuição WSL?</span><span class="sxs-lookup"><span data-stu-id="29217-195">How do I uninstall a WSL Distribution?</span></span>

<span data-ttu-id="29217-196">Em builds anteriores ao 1709 (16299), abra um prompt de comando e execute:</span><span class="sxs-lookup"><span data-stu-id="29217-196">On builds prior to 1709 (16299) open a command prompt and run:</span></span>

  ```batchfile
  lxrun /uninstall /full
  ```
  
<span data-ttu-id="29217-197">As distribuições do WSL instaladas no repositório podem ser desinstaladas como qualquer outro aplicativo do Windows clicando com o botão direito do mouse no bloco do aplicativo e clicando em Desinstalar ou por meio do PowerShell usando o cmdlet [`Remove-AppxPackage`](/previous-versions//hh856038(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="29217-197">WSL distributions installed from the store can be uninstalled like any other Windows app, by right-clicking on the app tile and clicking Uninstall, or via PowerShell using the [`Remove-AppxPackage` cmdlet](/previous-versions//hh856038(v=technet.10)).</span></span>

## <a name="why-does-ping-generate-permission-denied-errors"></a><span data-ttu-id="29217-198">Por que o ping gera erros de permissão negada?</span><span class="sxs-lookup"><span data-stu-id="29217-198">Why does ping generate permission denied errors?</span></span>

<span data-ttu-id="29217-199">Nos builds do WLS anteriores ao 14926, o ping exigia que o WSL fosse executado usando um console elevado.</span><span class="sxs-lookup"><span data-stu-id="29217-199">In WSL builds < 14926, ping required WSL to run via an elevated Console.</span></span> <span data-ttu-id="29217-200">Esse problema foi corrigido no Build 14926 e posterior.</span><span class="sxs-lookup"><span data-stu-id="29217-200">This issue was fixed in Build 14926 and later.</span></span>

## <a name="how-do-i-run-an-openssh-server"></a><span data-ttu-id="29217-201">Como executar um servidor OpenSSH?</span><span class="sxs-lookup"><span data-stu-id="29217-201">How do I run an OpenSSH server?</span></span>

<span data-ttu-id="29217-202">São necessários privilégios de administrador no Windows para executar o OpenSSH no WSL.</span><span class="sxs-lookup"><span data-stu-id="29217-202">Administrator privileges in Windows are required to run OpenSSH in WSL.</span></span> <span data-ttu-id="29217-203">Para executar o servidor OpenSSH, execute o Bash do Ubuntu no Windows como administrador ou execute bash.exe em um prompt do CMD/PowerShell com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="29217-203">To run an OpenSSH server, run Bash on Ubuntu on Windows as an administrator, or run bash.exe from a CMD/PowerShell prompt with administrator privileges.</span></span>

## <a name="why-do-i-get-error-0x80040306-when-i-try-to-install"></a><span data-ttu-id="29217-204">Por que obtenho "Erro: 0x80040306"quando tento instalar?</span><span class="sxs-lookup"><span data-stu-id="29217-204">Why do I get "Error: 0x80040306" when I try to install?</span></span>

<span data-ttu-id="29217-205">O WSL não é compatível com a execução em um console herdado.</span><span class="sxs-lookup"><span data-stu-id="29217-205">WSL does not support running in a legacy console.</span></span> <span data-ttu-id="29217-206">Para desligar o console herdado:</span><span class="sxs-lookup"><span data-stu-id="29217-206">To turn off legacy console:</span></span>

1. <span data-ttu-id="29217-207">Abra o WSL, o PowerShell ou o Cmd</span><span class="sxs-lookup"><span data-stu-id="29217-207">Open WSL, PowerShell, or Cmd</span></span>
1. <span data-ttu-id="29217-208">Clique com o botão direito do mouse na barra de título-> Propriedades-> desmarque “Usar console herdado”</span><span class="sxs-lookup"><span data-stu-id="29217-208">Right click title bar -> Properties -> Uncheck "Use legacy console"</span></span>
1. <span data-ttu-id="29217-209">Clique em OK</span><span class="sxs-lookup"><span data-stu-id="29217-209">Click OK</span></span>

## <a name="why-do-i-get-error-0x80040154-when-i-run-bashexe-after-upgrading-windows"></a><span data-ttu-id="29217-210">Por que obtenho "Erro: 0x80040154" quando executo o bash.exe após a atualização do Windows?</span><span class="sxs-lookup"><span data-stu-id="29217-210">Why do I get "Error: 0x80040154" when I run bash.exe after upgrading Windows?</span></span>

<span data-ttu-id="29217-211">O recurso “Subsistema Windows para Linux” pode ser desabilitado durante uma atualização do Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-211">The "Windows Subsystem for Linux" feature may be disabled during a Windows update.</span></span> <span data-ttu-id="29217-212">Se isso acontecer, o recurso do Windows deverá ser habilitado novamente.</span><span class="sxs-lookup"><span data-stu-id="29217-212">If this happens the Windows feature must be re-enabled.</span></span> <span data-ttu-id="29217-213">As instruções para habilitar o recurso “Subsistema Windows para Linux” podem ser encontradas no [Guia de instalação](./install-win10.md).</span><span class="sxs-lookup"><span data-stu-id="29217-213">Instructions for enabling the "Windows Subsystem for Linux" feature can be found in the [Installation Guide](./install-win10.md).</span></span>

## <a name="how-do-i-change-the-display-language-of-wsl"></a><span data-ttu-id="29217-214">Como alterar o idioma de exibição do WSL?</span><span class="sxs-lookup"><span data-stu-id="29217-214">How do I change the display language of WSL?</span></span>

<span data-ttu-id="29217-215">A instalação do WSL tentará alterar automaticamente a localidade do Ubuntu para corresponder à localidade da instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-215">WSL install will try to automatically change the Ubuntu locale to match the locale of your Windows install.</span></span> <span data-ttu-id="29217-216">Se você não quiser esse comportamento, poderá executar esse comando para alterar a localidade do Ubuntu após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="29217-216">If you do not want this behavior you can run this command to change the Ubuntu locale after install completes.</span></span> <span data-ttu-id="29217-217">Você precisará reiniciar o bash.exe para que essa alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="29217-217">You will have to relaunch bash.exe for this change to take effect.</span></span>

<span data-ttu-id="29217-218">O exemplo abaixo altera a localidade para en-US:</span><span class="sxs-lookup"><span data-stu-id="29217-218">The below example changes to locale to en-US:</span></span>

```bash
sudo update-locale LANG=en_US.UTF8
```

## <a name="why-do-i-not-have-internet-access-from-wsl"></a><span data-ttu-id="29217-219">Por que não tenho acesso à Internet do WSL?</span><span class="sxs-lookup"><span data-stu-id="29217-219">Why do I not have internet access from WSL?</span></span>

<span data-ttu-id="29217-220">Alguns usuários relataram problemas com aplicativos de firewall específicos que bloqueiam o acesso à Internet no WSL.</span><span class="sxs-lookup"><span data-stu-id="29217-220">Some users have reported issues with specific firewall applications blocking internet access in WSL.</span></span> <span data-ttu-id="29217-221">Os firewalls relatados são:</span><span class="sxs-lookup"><span data-stu-id="29217-221">The firewalls reported are:</span></span>

1. <span data-ttu-id="29217-222">Kaspersky</span><span class="sxs-lookup"><span data-stu-id="29217-222">Kaspersky</span></span>
1. <span data-ttu-id="29217-223">AVG</span><span class="sxs-lookup"><span data-stu-id="29217-223">AVG</span></span>
1. <span data-ttu-id="29217-224">Avast</span><span class="sxs-lookup"><span data-stu-id="29217-224">Avast</span></span>

<span data-ttu-id="29217-225">Em alguns casos, desligar o firewall permite o acesso.</span><span class="sxs-lookup"><span data-stu-id="29217-225">In some cases turning off the firewall allows for access.</span></span> <span data-ttu-id="29217-226">Em outros, simplesmente ter o firewall instalado bloqueia o acesso.</span><span class="sxs-lookup"><span data-stu-id="29217-226">In some cases simply having the firewall installed looks to block access.</span></span>

## <a name="how-do-i-access-a-port-from-wsl-in-windows"></a><span data-ttu-id="29217-227">Como acessar uma porta do WSL no Windows?</span><span class="sxs-lookup"><span data-stu-id="29217-227">How do I access a port from WSL in Windows?</span></span>
<span data-ttu-id="29217-228">O WSL compartilha o endereço IP do Windows, pois ele é executado no Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-228">WSL shares the IP address of Windows, as it is running on Windows.</span></span> <span data-ttu-id="29217-229">Assim, você pode acessar qualquer porta no localhost, por exemplo, se você tivesse conteúdo da Web na porta 1234, poderia https://localhost:1234 no seu navegador do Windows.</span><span class="sxs-lookup"><span data-stu-id="29217-229">As such you can access any ports on localhost e.g. if you had web content on port 1234 you could https://localhost:1234 into your Windows browser.</span></span>

## <a name="how-can-i-back-up-my-wsl-distros-or-move-them-from-one-drive-to-another"></a><span data-ttu-id="29217-230">Como fazer backup das distribuições do WSL ou movê-las de uma unidade para outra?</span><span class="sxs-lookup"><span data-stu-id="29217-230">How can I back up my WSL distros, or move them from one drive to another?</span></span>

<span data-ttu-id="29217-231">A melhor maneira de fazer backup das distribuições ou movê-las é por meio dos comandos de exportação/importação disponíveis no Windows, versão 1809 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="29217-231">The best way to backup or move your distros is via the export/import commands available in Windows Version 1809 and later.</span></span> <span data-ttu-id="29217-232">Você pode exportar toda a distribuição para um tarball usando o comando `wsl --export`.</span><span class="sxs-lookup"><span data-stu-id="29217-232">You can export your entire distribution to a tarball using the `wsl --export` command.</span></span> <span data-ttu-id="29217-233">Em seguida, importe essa distribuição novamente para o WSL usando o comando `wsl --import`, que pode nomear um novo local de unidade para a importação, permitindo que você faça backup dos estados das distribuições do WSL ou salve-os (ou mova-os).</span><span class="sxs-lookup"><span data-stu-id="29217-233">You can then import this distro back into WSL using the `wsl --import` command, which can name a new drive location for the import, allowing you to backup and save states of (or move) your WSL distributions.</span></span> 

<span data-ttu-id="29217-234">Observe que os serviços de backup tradicionais que fazem backup de arquivos em suas pastas AppData (como o backup do Windows) não corromperão os arquivos do Linux.</span><span class="sxs-lookup"><span data-stu-id="29217-234">Please note that traditional backup services that backup files in your Appdata folders (like Windows Backup) will not corrupt your Linux files.</span></span>

## <a name="where-can-i-provide-feedback"></a><span data-ttu-id="29217-235">Onde posso fornecer comentários?</span><span class="sxs-lookup"><span data-stu-id="29217-235">Where can I provide feedback?</span></span>

<span data-ttu-id="29217-236">É possível compartilhar comentários e fazer perguntas por meio de vários canais.</span><span class="sxs-lookup"><span data-stu-id="29217-236">You can share feedback and ask questions through multiple channels.</span></span>

<span data-ttu-id="29217-237">Se você tiver problemas técnicos ou desejar solicitar novos recursos, acesse o rastreador de problemas do GitHub:</span><span class="sxs-lookup"><span data-stu-id="29217-237">If you have technical issues, or want to request new features please go to our Github issue tracker:</span></span>

* [<span data-ttu-id="29217-238">Rastreador de problemas do GitHub</span><span class="sxs-lookup"><span data-stu-id="29217-238">GitHub issue tracker</span></span>](https://github.com/Microsoft/BashOnWindows/issues)

<span data-ttu-id="29217-239">Se você quiser ficar por dentro das últimas notícias do WSL, acesse:</span><span class="sxs-lookup"><span data-stu-id="29217-239">If you'd like to stay up to date with the latest WSL news you can do so with:</span></span>

* <span data-ttu-id="29217-240">Nosso [blog da equipe de linha de comando](https://blogs.msdn.microsoft.com/commandline/)</span><span class="sxs-lookup"><span data-stu-id="29217-240">Our [command-line team blog](https://blogs.msdn.microsoft.com/commandline/)</span></span>
* <span data-ttu-id="29217-241">O Twitter.</span><span class="sxs-lookup"><span data-stu-id="29217-241">Twitter.</span></span> <span data-ttu-id="29217-242">Siga [@craigaloewen](https://twitter.com/craigaloewen) no Twitter para saber mais sobre as novidades, atualizações, etc.</span><span class="sxs-lookup"><span data-stu-id="29217-242">Please follow [@craigaloewen](https://twitter.com/craigaloewen) on Twitter to learn of news, updates, etc.</span></span>