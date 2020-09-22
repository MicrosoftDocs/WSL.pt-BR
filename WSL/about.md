---
title: Sobre o Subsistema do Windows para Linux
description: Saiba mais sobre o Subsistema do Windows para Linux, incluindo informações sobre diferentes versões e de que maneira você pode usá-las.
keywords: BashOnWindows, bash, wsl, windows, windowssubsystem, gnu, linux
ms.date: 07/21/2020
ms.topic: article
ms.assetid: 3cefe0db-7616-4848-a2b6-9296746a178b
ms.localizationpriority: high
ms.openlocfilehash: 2b79473f620c39084bc9b7a385d4e16e3fe34d77
ms.sourcegitcommit: 69fc9d3ca22cf3f07622db4cdf80c8ec751fe620
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90818668"
---
# <a name="what-is-the-windows-subsystem-for-linux"></a><span data-ttu-id="87133-104">O que é o Subsistema do Windows para Linux?</span><span class="sxs-lookup"><span data-stu-id="87133-104">What is the Windows Subsystem for Linux?</span></span>

<span data-ttu-id="87133-105">O Subsistema do Windows para Linux permite que os desenvolvedores executem um ambiente GNU/Linux, incluindo a maioria das ferramentas de linha de comando, utilitários e aplicativos, diretamente no Windows, sem modificações e sem a sobrecarga de uma máquina virtual tradicional ou instalação dualboot.</span><span class="sxs-lookup"><span data-stu-id="87133-105">The Windows Subsystem for Linux lets developers run a GNU/Linux environment -- including most command-line tools, utilities, and applications -- directly on Windows, unmodified, without the overhead of a traditional virtual machine or dualboot setup.</span></span>

<span data-ttu-id="87133-106">Você pode:</span><span class="sxs-lookup"><span data-stu-id="87133-106">You can:</span></span>

* <span data-ttu-id="87133-107">Escolha sua distribuição do Linux/GNU favorita [na Microsoft Store](https://aka.ms/wslstore).</span><span class="sxs-lookup"><span data-stu-id="87133-107">Choose your favorite GNU/Linux distributions [from the Microsoft Store](https://aka.ms/wslstore).</span></span>
* <span data-ttu-id="87133-108">Execute as ferramentas de linha de comando comuns, como `grep`, `sed`, `awk` ou outros binários ELF-64.</span><span class="sxs-lookup"><span data-stu-id="87133-108">Run common command-line tools such as `grep`, `sed`, `awk`, or other ELF-64 binaries.</span></span>
* <span data-ttu-id="87133-109">Execute scripts de shell do Bash e aplicativos de linha de comando do GNU/Linux, incluindo:</span><span class="sxs-lookup"><span data-stu-id="87133-109">Run Bash shell scripts and GNU/Linux command-line applications including:</span></span>  
    * <span data-ttu-id="87133-110">Ferramentas: vim, emacs, tmux</span><span class="sxs-lookup"><span data-stu-id="87133-110">Tools: vim, emacs, tmux</span></span>
    * <span data-ttu-id="87133-111">Linguagens: [Node.js](https://docs.microsoft.com/windows/nodejs/setup-on-wsl2), Javascript, [Python](https://docs.microsoft.com/windows/python/web-frameworks), Ruby, C/C++, C# & F#, Rust, Go etc.</span><span class="sxs-lookup"><span data-stu-id="87133-111">Languages: [NodeJS](https://docs.microsoft.com/windows/nodejs/setup-on-wsl2), Javascript, [Python](https://docs.microsoft.com/windows/python/web-frameworks), Ruby, C/C++, C# & F#, Rust, Go, etc.</span></span>
    * <span data-ttu-id="87133-112">Serviços: SSHD, [MySQL](./tutorials/wsl-database.md), Apache, lighttpd, [MongoDB](./tutorials/wsl-database.md), [PostgreSQL](./tutorials/wsl-database.md).</span><span class="sxs-lookup"><span data-stu-id="87133-112">Services: SSHD, [MySQL](./tutorials/wsl-database.md), Apache, lighttpd, [MongoDB](./tutorials/wsl-database.md), [PostgreSQL](./tutorials/wsl-database.md).</span></span>
* <span data-ttu-id="87133-113">Instale o software adicional usando o seu próprio gerenciador de pacotes de distribuição do GNU/Linux.</span><span class="sxs-lookup"><span data-stu-id="87133-113">Install additional software using your own GNU/Linux distribution package manager.</span></span>
* <span data-ttu-id="87133-114">Invoque aplicativos do Windows usando um shell de linha de comando do UNIX.</span><span class="sxs-lookup"><span data-stu-id="87133-114">Invoke Windows applications using a Unix-like command-line shell.</span></span>
* <span data-ttu-id="87133-115">Invoque aplicativos do GNU/Linux no Windows.</span><span class="sxs-lookup"><span data-stu-id="87133-115">Invoke GNU/Linux applications on Windows.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="87133-116">Instalar o WSL</span><span class="sxs-lookup"><span data-stu-id="87133-116">Install WSL</span></span>](install-win10.md)

<br>

> [!VIDEO https://www.youtube.com/embed/48k317kOxqg]

## <a name="what-is-wsl-2"></a><span data-ttu-id="87133-117">O que é o WSL 2?</span><span class="sxs-lookup"><span data-stu-id="87133-117">What is WSL 2?</span></span>

<span data-ttu-id="87133-118">O WSL 2 é uma nova versão da arquitetura do Subsistema do Windows para Linux que capacita o Subsistema do Windows para Linux a executar binários ELF64 Linux no Windows.</span><span class="sxs-lookup"><span data-stu-id="87133-118">WSL 2 is a new version of the Windows Subsystem for Linux architecture that powers the Windows Subsystem for Linux to run ELF64 Linux binaries on Windows.</span></span> <span data-ttu-id="87133-119">As metas principais dele são **aumentar o desempenho do sistema de arquivos** e adicionar **compatibilidade completa com a chamada do sistema**.</span><span class="sxs-lookup"><span data-stu-id="87133-119">Its primary goals are to **increase file system performance**, as well as adding **full system call compatibility**.</span></span>

<span data-ttu-id="87133-120">Essa nova arquitetura altera como esses binários do Linux interagem com o Windows e o hardware do computador, mas ainda fornece a mesma experiência do usuário que no WSL 1 (a versão atual amplamente disponível).</span><span class="sxs-lookup"><span data-stu-id="87133-120">This new architecture changes how these Linux binaries interact with Windows and your computer's hardware, but still provides the same user experience as in WSL 1 (the current widely available version).</span></span>

<span data-ttu-id="87133-121">As distribuições individuais do Linux podem ser executadas com a arquitetura do WSL 1 ou do WSL 2.</span><span class="sxs-lookup"><span data-stu-id="87133-121">Individual Linux distributions can be run with either the WSL 1 or WSL 2 architecture.</span></span> <span data-ttu-id="87133-122">Cada distribuição pode passar por upgrade ou downgrade a qualquer momento e você pode executar distribuições do WSL 1 e do WSL 2 lado a lado.</span><span class="sxs-lookup"><span data-stu-id="87133-122">Each distribution can be upgraded or downgraded at any time and you can run WSL 1 and WSL 2 distributions side by side.</span></span> <span data-ttu-id="87133-123">O WSL 2 usa uma arquitetura totalmente nova que se beneficia do uso de um kernel Linux real.</span><span class="sxs-lookup"><span data-stu-id="87133-123">WSL 2 uses an entirely new architecture that benefits from running a real Linux kernel.</span></span>

<br>

> [!VIDEO https://www.youtube.com/embed/MrZolfGm8Zk]

## <a name="next-steps"></a><span data-ttu-id="87133-124">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="87133-124">Next steps</span></span>

* [<span data-ttu-id="87133-125">Instalar o WSL 1 e atualizar para o WSL 2</span><span class="sxs-lookup"><span data-stu-id="87133-125">Install WSL 1 and update to WSL 2</span></span>](./install-win10.md)

* [<span data-ttu-id="87133-126">Comparar o WSL 2 e o WSL 1</span><span class="sxs-lookup"><span data-stu-id="87133-126">Compare WSL 2 and WSL 1</span></span>](./compare-versions.md)

* [<span data-ttu-id="87133-127">Criar uma conta de usuário e uma senha para sua nova distribuição do Linux</span><span class="sxs-lookup"><span data-stu-id="87133-127">Create a user account and password for your new Linux distribution</span></span>](./user-support.md)

* [<span data-ttu-id="87133-128">Ler as perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="87133-128">Read Frequently Asked Questions</span></span>](./faq.md)

* [<span data-ttu-id="87133-129">Ler as perguntas frequentes sobre o WSL 2</span><span class="sxs-lookup"><span data-stu-id="87133-129">Read Frequently Asked Questions about WSL 2</span></span>](./wsl2-faq.md)

* [<span data-ttu-id="87133-130">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="87133-130">Troubleshooting</span></span>](./troubleshooting.md)

* [<span data-ttu-id="87133-131">Executar comandos de interoperabilidade entre o Windows e o Linux</span><span class="sxs-lookup"><span data-stu-id="87133-131">Run interoperability commands between Windows and Linux</span></span>](./interop.md)

* [<span data-ttu-id="87133-132">Executar comandos e configurações de inicialização</span><span class="sxs-lookup"><span data-stu-id="87133-132">Run launch commands and configurations</span></span>](./wsl-config.md)

* [<span data-ttu-id="87133-133">Configurar as permissões de arquivo</span><span class="sxs-lookup"><span data-stu-id="87133-133">Set up file permissions</span></span>](./file-permissions.md)

* [<span data-ttu-id="87133-134">Configurar o WSL para Empresas</span><span class="sxs-lookup"><span data-stu-id="87133-134">Set up WSL for Enterprise</span></span>](./enterprise.md)

* [<span data-ttu-id="87133-135">Comandos do WSL de referência</span><span class="sxs-lookup"><span data-stu-id="87133-135">Reference WSL commands</span></span>](./reference.md)

* [<span data-ttu-id="87133-136">Criar distribuições personalizadas</span><span class="sxs-lookup"><span data-stu-id="87133-136">Build custom distributions</span></span>](./build-custom-distro.md)

* [<span data-ttu-id="87133-137">Ler as notas sobre a versão do WSL</span><span class="sxs-lookup"><span data-stu-id="87133-137">Read the WSL Release Notes</span></span>](./release-notes.md)
