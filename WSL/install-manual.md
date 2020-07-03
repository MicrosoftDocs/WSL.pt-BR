---
title: Baixar manualmente as distribuições do WSL (Subsistema do Windows para Linux)
description: Instruções sobre como baixar manualmente as distribuições do Subsistema do Windows para Linux.
keywords: wsl, subsistema do Windows para Linux, instalação manual, instalar manualmente, microsoft store, windows 10s, ondulação, Add-AppxPackage, manutenção de longo prazo, LTSC
ms.date: 05/28/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: d948ce9d304314bdd15b98136b8a99ca35723139
ms.sourcegitcommit: e67eb4aedff57a304188ca3360aba25605f8bdb1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2020
ms.locfileid: "84746272"
---
# <a name="manually-download-windows-subsystem-for-linux-distro-packages"></a><span data-ttu-id="326d2-104">Baixar manualmente os pacotes de distribuição do Subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="326d2-104">Manually download Windows Subsystem for Linux distro packages</span></span>

<span data-ttu-id="326d2-105">Há vários cenários nos quais você pode não conseguir (ou desejar) instalar as distribuições do WSL para Linux por meio da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="326d2-105">There are several scenarios in which you may not be able (or want) to, install WSL Linux distros via the Microsoft Store.</span></span> <span data-ttu-id="326d2-106">Especificamente, você pode estar executando um SKU do sistema operacional da área de trabalho do Windows Server ou de LTSC (Manutenção em Longo Prazo) que não é compatível com a Microsoft Store ou suas políticas de rede corporativa e/ou administradores não permitem o uso da Microsoft Store em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="326d2-106">Specifically, you may be running a Windows Server or Long-Term Servicing (LTSC) desktop OS SKU that doesn't support Microsoft Store, or your corporate network policies and/or admins to not permit Microsoft Store usage in your environment.</span></span>

<span data-ttu-id="326d2-107">Nesses casos, embora o WSL em si esteja disponível, como baixar e instalar as distribuições do Linux no WSL se você não puder acessar a loja?</span><span class="sxs-lookup"><span data-stu-id="326d2-107">In these cases, while WSL itself is available, how do you download and install Linux distros in WSL if you can't access the store?</span></span>

> <span data-ttu-id="326d2-108">Observação: **ambientes de Shell de linha de comando, incluindo distribuições de Cmd, PowerShell e Linux/WSL, não têm permissão para serem executados no Windows 10 no modo S**.</span><span class="sxs-lookup"><span data-stu-id="326d2-108">Note: **Command-line shell environments including Cmd, PowerShell, and Linux/WSL distros are not permitted to run on Windows 10 S Mode**.</span></span> <span data-ttu-id="326d2-109">Essa restrição existe para garantir a integridade e as metas de segurança que o modo S fornece: Para obter mais informações, leia [esta postagem](https://blogs.msdn.microsoft.com/commandline/2017/05/18/will-linux-distros-run-on-windows-10-s/).</span><span class="sxs-lookup"><span data-stu-id="326d2-109">This restriction exists in order to ensure the integrity and safety goals that S Mode delivers: Read [this post](https://blogs.msdn.microsoft.com/commandline/2017/05/18/will-linux-distros-run-on-windows-10-s/) for more information.</span></span>

## <a name="downloading-distros"></a><span data-ttu-id="326d2-110">Como baixar as distribuições</span><span class="sxs-lookup"><span data-stu-id="326d2-110">Downloading distros</span></span>

<span data-ttu-id="326d2-111">Se o aplicativo Microsoft Store não estiver disponível, você poderá baixar e instalar manualmente as distribuições do Linux clicando nestes links:</span><span class="sxs-lookup"><span data-stu-id="326d2-111">If the Microsoft Store app is not available, you can download and manually install Linux distros by clicking these links:</span></span>
* [<span data-ttu-id="326d2-112">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="326d2-112">Ubuntu 20.04</span></span>](https://aka.ms/wslubuntu2004)
* [<span data-ttu-id="326d2-113">Ubuntu 20.04 ARM</span><span class="sxs-lookup"><span data-stu-id="326d2-113">Ubuntu 20.04 ARM</span></span>](https://aka.ms/wslubuntu2004arm)
* [<span data-ttu-id="326d2-114">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="326d2-114">Ubuntu 18.04</span></span>](https://aka.ms/wsl-ubuntu-1804)
* [<span data-ttu-id="326d2-115">Ubuntu 18.04 ARM</span><span class="sxs-lookup"><span data-stu-id="326d2-115">Ubuntu 18.04 ARM</span></span>](https://aka.ms/wsl-ubuntu-1804-arm)
* [<span data-ttu-id="326d2-116">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="326d2-116">Ubuntu 16.04</span></span>](https://aka.ms/wsl-ubuntu-1604)
* [<span data-ttu-id="326d2-117">Debian GNU/Linux</span><span class="sxs-lookup"><span data-stu-id="326d2-117">Debian GNU/Linux</span></span>](https://aka.ms/wsl-debian-gnulinux)
* [<span data-ttu-id="326d2-118">Kali Linux</span><span class="sxs-lookup"><span data-stu-id="326d2-118">Kali Linux</span></span>](https://aka.ms/wsl-kali-linux-new)
* [<span data-ttu-id="326d2-119">OpenSUSE Leap 42</span><span class="sxs-lookup"><span data-stu-id="326d2-119">OpenSUSE Leap 42</span></span>](https://aka.ms/wsl-opensuse-42)
* [<span data-ttu-id="326d2-120">SUSE Linux Enterprise Server 12</span><span class="sxs-lookup"><span data-stu-id="326d2-120">SUSE Linux Enterprise Server 12</span></span>](https://aka.ms/wsl-sles-12)
* [<span data-ttu-id="326d2-121">Fedora Remix para WSL</span><span class="sxs-lookup"><span data-stu-id="326d2-121">Fedora Remix for WSL</span></span>](https://github.com/WhitewaterFoundry/WSLFedoraRemix/releases/)

<span data-ttu-id="326d2-122">Isso fará com que os pacotes `<distro>.appx` sejam baixados em uma pasta de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="326d2-122">This will cause the `<distro>.appx` packages to download to a folder of your choosing.</span></span> <span data-ttu-id="326d2-123">Siga as [instruções de instalação](#installing-your-distro) para instalar suas distribuições baixadas.</span><span class="sxs-lookup"><span data-stu-id="326d2-123">Follow the [installation instructions](#installing-your-distro) to install your downloaded distro(s).</span></span>

## <a name="downloading-distros-via-the-command-line"></a><span data-ttu-id="326d2-124">Baixar as distribuições usando a linha de comando</span><span class="sxs-lookup"><span data-stu-id="326d2-124">Downloading distros via the command line</span></span>
<span data-ttu-id="326d2-125">Se preferir, você também poderá baixar suas distribuições preferenciais usando a linha de comando:</span><span class="sxs-lookup"><span data-stu-id="326d2-125">If you prefer, you can also download your preferred distro(s) via the command line:</span></span>

 ### <a name="download-using-powershell"></a><span data-ttu-id="326d2-126">Baixar usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="326d2-126">Download using PowerShell</span></span>
 <span data-ttu-id="326d2-127">Para baixar as distribuições usando o PowerShell, use o cmdlet [Invoke-WebRequest](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1).</span><span class="sxs-lookup"><span data-stu-id="326d2-127">To download distros using PowerShell, use the [Invoke-WebRequest](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-5.1) cmdlet.</span></span> <span data-ttu-id="326d2-128">Aqui está um exemplo de instrução para baixar o Ubuntu 16.04.</span><span class="sxs-lookup"><span data-stu-id="326d2-128">Here's a sample instruction to download Ubuntu 16.04.</span></span>

```powershell
Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1604 -OutFile Ubuntu.appx -UseBasicParsing
```

> [!TIP]
> <span data-ttu-id="326d2-129">Se o download estiver demorando muito, desligue a barra de progresso definindo `$ProgressPreference = 'SilentlyContinue'`</span><span class="sxs-lookup"><span data-stu-id="326d2-129">If the download is taking a long time, turn off the progress bar by setting `$ProgressPreference = 'SilentlyContinue'`</span></span>

### <a name="download-using-curl"></a><span data-ttu-id="326d2-130">Baixar usando curl</span><span class="sxs-lookup"><span data-stu-id="326d2-130">Download using curl</span></span>
<span data-ttu-id="326d2-131">A atualização do Windows 10 Spring 2018 (ou posterior) inclui o popular [utilitário de linha de comando curl](https://curl.haxx.se/) com o qual você pode invocar solicitações da Web (ou seja, comandos HTTP GET, POST, PUT etc.) na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="326d2-131">Windows 10 Spring 2018 Update (or later) includes the popular [curl command-line utility](https://curl.haxx.se/) with which you can invoke web requests (i.e. HTTP GET, POST, PUT, etc. commands) from the command line.</span></span> <span data-ttu-id="326d2-132">Você pode usar `curl.exe` para baixar as distribuições acima:</span><span class="sxs-lookup"><span data-stu-id="326d2-132">You can use `curl.exe` to download the above distros:</span></span>

```console
curl.exe -L -o ubuntu-1604.appx https://aka.ms/wsl-ubuntu-1604
```

<span data-ttu-id="326d2-133">No exemplo acima, `curl.exe` é executado (não apenas `curl`) para verificar se, no PowerShell, o executável curl real é invocado, não o alias curl do PowerShell para [Invoke-WebRequest](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-6)</span><span class="sxs-lookup"><span data-stu-id="326d2-133">In the above example, `curl.exe` is executed (not just `curl`) to ensure that, in PowerShell, the real curl executable is invoked, not the PowerShell curl alias for [Invoke-WebRequest](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-6)</span></span>

> <span data-ttu-id="326d2-134">Observação: usar `curl` poderá ser preferível se você precisar invocar/gerar script de etapas de download usando o shell Cmd e/ou scripts `.bat` / `.cmd`.</span><span class="sxs-lookup"><span data-stu-id="326d2-134">Note: Using `curl` might be preferable if you have to invoke/script download steps using Cmd shell and/or `.bat` / `.cmd` scripts.</span></span>

## <a name="installing-your-distro"></a><span data-ttu-id="326d2-135">Instalar sua distribuição</span><span class="sxs-lookup"><span data-stu-id="326d2-135">Installing your distro</span></span>
<span data-ttu-id="326d2-136">Se você estiver usando o Windows 10, poderá instalar a distribuição com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="326d2-136">If you're using Windows 10 you can install your distro with PowerShell.</span></span> <span data-ttu-id="326d2-137">Basta navegar até a pasta que contém a distribuição baixada acima e, nesse diretório, executar o comando a seguir, em que `app_name` é o nome do seu arquivo de distribuição .appx.</span><span class="sxs-lookup"><span data-stu-id="326d2-137">Simply navigate to folder containing the distro downloaded from above, and in that directory run the following command where `app_name` is the name of your distro .appx file.</span></span>  
```Powershell
Add-AppxPackage .\app_name.appx
```

<span data-ttu-id="326d2-138">Se você estiver usando um servidor do Windows, poderá encontrar as instruções de instalação na página de documentação do [Windows Server](install-on-server.md).</span><span class="sxs-lookup"><span data-stu-id="326d2-138">If you are using Windows server you can find the install instructions on the [Windows Server](install-on-server.md) documentation page.</span></span>

<span data-ttu-id="326d2-139">Após instalar sua distribuição, siga as instruções normais para [atualizar para WSL 2](./install-win10.md#update-to-wsl-2) ou [criar uma conta e senha de usuário](./user-support.md).</span><span class="sxs-lookup"><span data-stu-id="326d2-139">Once your distribution is installed, follow the normal instructions to [update to WSL 2](./install-win10.md#update-to-wsl-2) or [create a new user account and password](./user-support.md).</span></span>
