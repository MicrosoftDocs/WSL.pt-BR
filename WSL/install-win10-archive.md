---
title: Instalar o WSL (Subsistema Windows para Linux) no Windows 10
description: Instruções de instalação para o Subsistema Windows para Linux no Windows 10.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, debian, suse, windows 10, install
ms.date: 07/23/2018
ms.topic: article
ms.assetid: 7afaeacf-435a-4e58-bff0-a9f0d75b8a51
ms.custom: seodec18
ms.localizationpriority: high
ms.openlocfilehash: 9cd38fbe3781fd0cd45bcd52c278de548d3da38f
ms.sourcegitcommit: 3fb40fd65b34a5eb26b213a0df6a3b2746b7a9b4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83270544"
---
# <a name="install-windows-subsystem-for-linux"></a><span data-ttu-id="7f28b-104">Instalar o Subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="7f28b-104">Install Windows Subsystem for Linux</span></span>

<span data-ttu-id="7f28b-105">O guia a seguir abordará as etapas necessárias para instalar o WSL (Subsistema do Windows para Linux) em um computador que executa o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7f28b-105">The following guide will walk through the steps required to install the Windows Subsystem for Linux (WSL) on a computer running Windows 10.</span></span>

## <a name="enable-the-windows-subsystem-for-linux-optional-feature"></a><span data-ttu-id="7f28b-106">Habilitar o recurso opcional Subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="7f28b-106">Enable the Windows Subsystem for Linux optional feature</span></span>

<span data-ttu-id="7f28b-107">Antes de instalar uma distribuição do Linux, habilite o recurso opcional "Subsistema do Windows para Linux" no Windows 10:</span><span class="sxs-lookup"><span data-stu-id="7f28b-107">Before installing a Linux distribution, you must enable the "Windows Subsystem for Linux" optional feature on Windows 10:</span></span>

1. <span data-ttu-id="7f28b-108">Abra o PowerShell como administrador e insira este script:</span><span class="sxs-lookup"><span data-stu-id="7f28b-108">Open PowerShell as Administrator and enter this script:</span></span>

```powershell
    Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

1. <span data-ttu-id="7f28b-109">Reinicie seu computador quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="7f28b-109">Restart your computer when prompted.</span></span>

## <a name="install-a-linux-distribution"></a><span data-ttu-id="7f28b-110">Instalar uma distribuição do Linux</span><span class="sxs-lookup"><span data-stu-id="7f28b-110">Install a Linux distribution</span></span>

<span data-ttu-id="7f28b-111">Há três maneiras de baixar e instalar suas distribuições preferidas do Linux:</span><span class="sxs-lookup"><span data-stu-id="7f28b-111">There are three ways to download and install your preferred Linux distribution(s):</span></span>

- <span data-ttu-id="7f28b-112">Baixe e instale usando a Microsoft Store (consulte abaixo)</span><span class="sxs-lookup"><span data-stu-id="7f28b-112">Download and install from the Microsoft Store (see below)</span></span>
- [<span data-ttu-id="7f28b-113">Baixar e instalar a distribuição manualmente por meio da linha de comando</span><span class="sxs-lookup"><span data-stu-id="7f28b-113">Download and manually install from command line</span></span>](install-manual.md)
- <span data-ttu-id="7f28b-114">[Instalação no Windows Server]] (install-on-server.md)</span><span class="sxs-lookup"><span data-stu-id="7f28b-114">[Install on Windows Server]](install-on-server.md)</span></span>

### <a name="install-from-the-microsoft-store"></a><span data-ttu-id="7f28b-115">Instale usando a Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="7f28b-115">Install from the Microsoft Store</span></span>

<span data-ttu-id="7f28b-116">As distribuições do Linux podem ser instaladas por meio da Microsoft Store no Windows 10 (Build 16215 e posteriores).</span><span class="sxs-lookup"><span data-stu-id="7f28b-116">Linux distributions can be installed from the Microsoft Store on Windows 10 (Build 16215+).</span></span>

> [!NOTE]
> <span data-ttu-id="7f28b-117">Siga estas etapas para [verificar o número de build do Windows 10](troubleshooting.md#check-your-build-number).</span><span class="sxs-lookup"><span data-stu-id="7f28b-117">Follow these steps to [check your Windows 10 build number](troubleshooting.md#check-your-build-number).</span></span>

1. <span data-ttu-id="7f28b-118">Abra a Microsoft Store e escolha sua distribuição do Linux favorita.</span><span class="sxs-lookup"><span data-stu-id="7f28b-118">Open the Microsoft Store and choose your favorite Linux distribution.</span></span>

    ![Exibição das distribuições do Linux na Microsoft Store](media/store.png)

    <span data-ttu-id="7f28b-120">Os links a seguir abrirão a página da Microsoft Store para cada distribuição:</span><span class="sxs-lookup"><span data-stu-id="7f28b-120">The following links will open the Microsoft store page for each distribution:</span></span>

    - [<span data-ttu-id="7f28b-121">Ubuntu 16.04 LTS</span><span class="sxs-lookup"><span data-stu-id="7f28b-121">Ubuntu 16.04 LTS</span></span>](https://www.microsoft.com/store/apps/9pjn388hp8c9)
    - [<span data-ttu-id="7f28b-122">Ubuntu 18.04 LTS</span><span class="sxs-lookup"><span data-stu-id="7f28b-122">Ubuntu 18.04 LTS</span></span>](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
    - [<span data-ttu-id="7f28b-123">OpenSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7f28b-123">OpenSUSE Leap 15</span></span>](https://www.microsoft.com/store/apps/9n1tb6fpvj8c)
    - [<span data-ttu-id="7f28b-124">OpenSUSE Leap 42</span><span class="sxs-lookup"><span data-stu-id="7f28b-124">OpenSUSE Leap 42</span></span>](https://www.microsoft.com/store/apps/9njvjts82tjx)
    - [<span data-ttu-id="7f28b-125">SUSE Linux Enterprise Server 12</span><span class="sxs-lookup"><span data-stu-id="7f28b-125">SUSE Linux Enterprise Server 12</span></span>](https://www.microsoft.com/store/apps/9p32mwbh6cns)
    - [<span data-ttu-id="7f28b-126">SUSE Linux Enterprise Server 15</span><span class="sxs-lookup"><span data-stu-id="7f28b-126">SUSE Linux Enterprise Server 15</span></span>](https://www.microsoft.com/store/apps/9pmw35d7fnlx)
    - [<span data-ttu-id="7f28b-127">Kali Linux</span><span class="sxs-lookup"><span data-stu-id="7f28b-127">Kali Linux</span></span>](https://www.microsoft.com/store/apps/9PKR34TNCV07)
    - [<span data-ttu-id="7f28b-128">Debian GNU/Linux</span><span class="sxs-lookup"><span data-stu-id="7f28b-128">Debian GNU/Linux</span></span>](https://www.microsoft.com/store/apps/9MSVKQC78PK6)
    - [<span data-ttu-id="7f28b-129">Fedora Remix para WSL</span><span class="sxs-lookup"><span data-stu-id="7f28b-129">Fedora Remix for WSL</span></span>](https://www.microsoft.com/store/apps/9n6gdm4k2hnc)
    - [<span data-ttu-id="7f28b-130">Pengwin</span><span class="sxs-lookup"><span data-stu-id="7f28b-130">Pengwin</span></span>](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
    - [<span data-ttu-id="7f28b-131">Pengwin Enterprise</span><span class="sxs-lookup"><span data-stu-id="7f28b-131">Pengwin Enterprise</span></span>](https://www.microsoft.com/store/apps/9N8LP0X93VCP)
    - [<span data-ttu-id="7f28b-132">Alpine WSL</span><span class="sxs-lookup"><span data-stu-id="7f28b-132">Alpine WSL</span></span>](https://www.microsoft.com/store/apps/9p804crf0395)

1. <span data-ttu-id="7f28b-133">Selecione "Obter" e, depois que a distribuição for baixada, selecione "Iniciar".</span><span class="sxs-lookup"><span data-stu-id="7f28b-133">Select "Get" and once the distribution has finished downloading, select "Launch".</span></span>

    ![Exibição das distribuições do Linux na Microsoft Store](media/UbuntuStore.png)

## <a name="complete-initialization-of-your-distro"></a><span data-ttu-id="7f28b-135">Conclua a inicialização de sua distribuição</span><span class="sxs-lookup"><span data-stu-id="7f28b-135">Complete initialization of your distro</span></span>

<span data-ttu-id="7f28b-136">Depois de iniciar a distribuição do Linux, siga as instruções na tela para inicializar a distribuição.</span><span class="sxs-lookup"><span data-stu-id="7f28b-136">After launching your Linux distribution, follow the onscreen instructions to initialize your distro.</span></span>

> [!NOTE]
> <span data-ttu-id="7f28b-137">Para o Windows Server, inicie a distribuição usando o executável, `<distro>.exe`, na pasta de instalação.</span><span class="sxs-lookup"><span data-stu-id="7f28b-137">For Windows Server, launch your distribution using the executable, `<distro>.exe`, in the installation folder.</span></span>

<span data-ttu-id="7f28b-138">Na primeira vez em que uma distribuição recém-instalada for executada, uma janela de console será aberta e você precisará aguardar alguns minutos para que a instalação seja concluída.</span><span class="sxs-lookup"><span data-stu-id="7f28b-138">The first time a newly installed distribution runs, a console window will open and you'll be asked to wait for a minute or two for the installation to complete.</span></span> <span data-ttu-id="7f28b-139">Durante essa fase final da instalação, os arquivos da distribuição são descompactados e armazenados em seu computador, prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="7f28b-139">During this final stage of installation, the distro's files are de-compressed and stored on your PC, ready for use.</span></span> <span data-ttu-id="7f28b-140">Isso pode levar cerca de um minuto ou mais, dependendo do desempenho dos dispositivos de armazenamento de seu computador.</span><span class="sxs-lookup"><span data-stu-id="7f28b-140">This may take around a minute or more depending on the performance of your PC's storage devices.</span></span> <span data-ttu-id="7f28b-141">Essa fase de instalação inicial só é necessária quando uma distribuição é instalada de modo limpo – todas as futuras inicializações deverão levar menos de um segundo.</span><span class="sxs-lookup"><span data-stu-id="7f28b-141">This initial installation phase is only required when a distro is clean-installed - all future launches should take less than a second.</span></span>

## <a name="set-up-a-new-linux-user-account"></a><span data-ttu-id="7f28b-142">Configurar uma nova conta de usuário do Linux</span><span class="sxs-lookup"><span data-stu-id="7f28b-142">Set up a new Linux user account</span></span>

<span data-ttu-id="7f28b-143">Quando a instalação for concluída, você será solicitado a criar uma nova conta de usuário (e sua senha).</span><span class="sxs-lookup"><span data-stu-id="7f28b-143">Once installation is complete, you will be prompted to create a new user account (and its password).</span></span>

![Desempacotamento do Ubuntu no console do Windows](media/UbuntuInstall.png)

<span data-ttu-id="7f28b-145">Essa conta de usuário destina-se ao usuário não administrador normal como o qual você estará conectado por padrão ao iniciar uma distribuição.</span><span class="sxs-lookup"><span data-stu-id="7f28b-145">This user account is for the normal non-admin user that you'll be logged-in as by default when launching a distribution.</span></span> <span data-ttu-id="7f28b-146">Você pode escolher qualquer nome de usuário e senha que desejar – eles não têm nenhuma influência sobre seu nome de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="7f28b-146">You can choose any username and password you wish - they have no bearing on your Windows username.</span></span>

<span data-ttu-id="7f28b-147">Quando você abrir uma nova instância da distribuição, não será solicitada sua senha, mas **se você elevar um processo usando `sudo`, precisará inserir sua senha**, portanto, certifique-se de escolher uma senha que você possa lembrar facilmente!</span><span class="sxs-lookup"><span data-stu-id="7f28b-147">When you open a new distro instance, you won't be prompted for your password, but **if you elevate a process using `sudo`, you will need to enter your password**, so make sure you choose a password you can easily remember!</span></span> <span data-ttu-id="7f28b-148">Consulte a página [Suporte ao usuário](user-support.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7f28b-148">See the [User Support](user-support.md) page for more info.</span></span>

## <a name="update--upgrade-packages"></a><span data-ttu-id="7f28b-149">Atualizar pacotes e fazer upgrade deles</span><span class="sxs-lookup"><span data-stu-id="7f28b-149">Update & upgrade packages</span></span>

<span data-ttu-id="7f28b-150">A maioria das distribuições é fornecida com um catálogo de pacotes vazio ou mínimo.</span><span class="sxs-lookup"><span data-stu-id="7f28b-150">Most distributions ship with an empty or minimal package catalog.</span></span> <span data-ttu-id="7f28b-151">Recomendamos expressamente que você atualize regularmente o catálogo de pacotes e faça upgrade dos pacotes instalados usando seu gerenciador de pacotes preferencial da distribuição.</span><span class="sxs-lookup"><span data-stu-id="7f28b-151">We strongly recommend regularly updating your package catalog and upgrading your installed packages using your distro's preferred package manager.</span></span> <span data-ttu-id="7f28b-152">No Debian/Ubuntu, use apt:</span><span class="sxs-lookup"><span data-stu-id="7f28b-152">For Debian/Ubuntu, use apt:</span></span>

```bash
sudo apt update && sudo apt upgrade
```

<span data-ttu-id="7f28b-153">O Windows não atualiza as distribuições do Linux nem faz upgrade delas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f28b-153">Windows does not automatically update or upgrade your Linux distro(s).</span></span> <span data-ttu-id="7f28b-154">Essa é uma tarefa que a maioria dos usuários do Linux prefere controlar por conta própria.</span><span class="sxs-lookup"><span data-stu-id="7f28b-154">This is a task that the most Linux users prefer to control themselves.</span></span>

<span data-ttu-id="7f28b-155">Aproveite o uso de sua nova distribuição do Linux no WSL!</span><span class="sxs-lookup"><span data-stu-id="7f28b-155">Enjoy using your new Linux distro on WSL!</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7f28b-156">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="7f28b-156">Troubleshooting</span></span>

<span data-ttu-id="7f28b-157">Veja abaixo os erros de instalação relacionados e as correções sugeridas.</span><span class="sxs-lookup"><span data-stu-id="7f28b-157">Below are related installation errors and suggested fixes.</span></span> <span data-ttu-id="7f28b-158">Consulte a [página de solução de problemas do WSL](troubleshooting.md) para ver outros erros comuns e suas soluções.</span><span class="sxs-lookup"><span data-stu-id="7f28b-158">Refer to the [WSL troubleshooting page](troubleshooting.md) for other common errors and their solutions.</span></span>

### <a name="installation-failed-with-error-0x8007007e"></a><span data-ttu-id="7f28b-159">Falha na instalação com o erro 0x8007007e</span><span class="sxs-lookup"><span data-stu-id="7f28b-159">Installation failed with error 0x8007007e</span></span>

<span data-ttu-id="7f28b-160">Esse erro ocorre quando o sistema não dá suporte ao Linux por meio da loja.</span><span class="sxs-lookup"><span data-stu-id="7f28b-160">This error occurs when your system doesn't support Linux from the store.</span></span>  <span data-ttu-id="7f28b-161">Certifique-se de que:</span><span class="sxs-lookup"><span data-stu-id="7f28b-161">Make sure that:</span></span>

- <span data-ttu-id="7f28b-162">Você está executando o Windows Build 16215 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="7f28b-162">You're running Windows build 16215 or later.</span></span> <span data-ttu-id="7f28b-163">[Verifique seu build](troubleshooting.md#check-your-build-number).</span><span class="sxs-lookup"><span data-stu-id="7f28b-163">[Check your build](troubleshooting.md#check-your-build-number).</span></span>
- <span data-ttu-id="7f28b-164">O componente opcional do Subsistema Windows para Linux está habilitado e o computador foi reiniciado.</span><span class="sxs-lookup"><span data-stu-id="7f28b-164">The Windows Subsystem for Linux optional component is enabled and the computer has restarted.</span></span>  <span data-ttu-id="7f28b-165">[Verifique se o WSL está habilitado](troubleshooting.md#confirm-wsl-is-enabled).</span><span class="sxs-lookup"><span data-stu-id="7f28b-165">[Make sure WSL is enabled](troubleshooting.md#confirm-wsl-is-enabled).</span></span>

### <a name="installation-failed-with-error-0x80070003"></a><span data-ttu-id="7f28b-166">Falha na instalação com o erro 0x80070003</span><span class="sxs-lookup"><span data-stu-id="7f28b-166">Installation failed with error 0x80070003</span></span>

<span data-ttu-id="7f28b-167">O Subsistema Windows para Linux é executado somente na unidade do sistema (normalmente, a unidade `C:`).</span><span class="sxs-lookup"><span data-stu-id="7f28b-167">The Windows Subsystem for Linux only runs on your system drive (usually this is your `C:` drive).</span></span> <span data-ttu-id="7f28b-168">Verifique se as distribuições estão armazenadas na unidade do sistema:</span><span class="sxs-lookup"><span data-stu-id="7f28b-168">Make sure that distros are stored on your system drive:</span></span>

- <span data-ttu-id="7f28b-169">Abra **Configurações** -> **Armazenamento** -> **Mais configurações de armazenamento: Alterar o local em que o novo conteúdo é salvo**</span><span class="sxs-lookup"><span data-stu-id="7f28b-169">Open **Settings** -> **Storage** -> **More Storage Settings: Change where new content is saved**</span></span>
  
    ![Imagem das configurações do sistema para instalar aplicativos na unidade C:](media/AppStorage.png)

### <a name="wslregisterdistribution-failed-with-error-0x8007019e"></a><span data-ttu-id="7f28b-171">Falha de WslRegisterDistribution com o erro 0x8007019e</span><span class="sxs-lookup"><span data-stu-id="7f28b-171">WslRegisterDistribution failed with error 0x8007019e</span></span>

<span data-ttu-id="7f28b-172">O componente opcional do Subsistema Windows para Linux não está habilitado:</span><span class="sxs-lookup"><span data-stu-id="7f28b-172">The Windows Subsystem for Linux optional component is not enabled:</span></span>

- <span data-ttu-id="7f28b-173">Abra **Painel de Controle** -> **Programas e Recursos** -> **Ativar ou desativar recursos do Windows** -> marque **Subsistema Windows para Linux** ou use o cmdlet do PowerShell mencionado no início deste artigo.</span><span class="sxs-lookup"><span data-stu-id="7f28b-173">Open **Control Panel** -> **Programs and Features** -> **Turn Windows Feature on or off** -> Check **Windows Subsystem for Linux** or using the PowerShell cmdlet mentioned at the begining of this article.</span></span>