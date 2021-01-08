---
title: Instalar o WSL (Subsistema Windows para Linux) no Windows 10
description: Saiba como instalar as distribuições do Linux no seu computador Windows 10 com um terminal Bash, incluindo Ubuntu, Debian, SUSE, Kali, Fedora, Pengwin e Alpine.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, debian, suse, windows 10, install, enable, WSL2, version 2
ms.date: 09/15/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: cbfd1f1aab99bc1965e569c4e818bd1663aa2878
ms.sourcegitcommit: f5b14630947ee9cf3438e9ba502bfbe85ed72cd1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97957687"
---
# <a name="windows-subsystem-for-linux-installation-guide-for-windows-10"></a><span data-ttu-id="4637a-104">Guia de instalação do Subsistema Windows para Linux para Windows 10</span><span class="sxs-lookup"><span data-stu-id="4637a-104">Windows Subsystem for Linux Installation Guide for Windows 10</span></span>

<span data-ttu-id="4637a-105">Há duas opções disponíveis para instalar o WSL (Subsistema do Windows para Linux):</span><span class="sxs-lookup"><span data-stu-id="4637a-105">There are two options available for installing Windows Subsystem for Linux (WSL):</span></span>

- <span data-ttu-id="4637a-106">**[Instalação simplificada](#simplified-installation-for-windows-insiders)** *(versão prévia)* : `wsl --install`</span><span class="sxs-lookup"><span data-stu-id="4637a-106">**[Simplified install](#simplified-installation-for-windows-insiders)** *(preview release)*: `wsl --install`</span></span>

    <span data-ttu-id="4637a-107">O comando de instalação simplificada de `wsl --install` requer que você entre no [Programa Windows Insiders](https://insider.windows.com/getting-started) e instale uma versão prévia do Windows 10 (build do sistema operacional 20262 ou superior), mas elimina a necessidade de seguir as etapas de instalação manual.</span><span class="sxs-lookup"><span data-stu-id="4637a-107">The `wsl --install` simplified install command requires that you join the [Windows Insiders Program](https://insider.windows.com/getting-started) and install a preview build of Windows 10 (OS build 20262 or higher), but eliminates the need to follow the manual install steps.</span></span> <span data-ttu-id="4637a-108">Tudo o que você precisa fazer é abrir uma janela de comando com privilégios de administrador e executar `wsl --install`. Após uma reinicialização, você estará pronto para usar o WSL.</span><span class="sxs-lookup"><span data-stu-id="4637a-108">All you need to do is open a command window with administrator privileges and run `wsl --install`, after a restart you will be ready to use WSL.</span></span>

- <span data-ttu-id="4637a-109">**[Instalação manual](#manual-installation-steps)** : Siga as seis etapas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="4637a-109">**[Manual install](#manual-installation-steps)**: Follow the six steps listed below.</span></span>

    <span data-ttu-id="4637a-110">As etapas de instalação manual para WSL estão listadas abaixo e podem ser usadas para instalar o Linux em qualquer versão do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4637a-110">The manual install steps for WSL are listed below and can be used to install Linux on any version of Windows 10.</span></span>

## <a name="simplified-installation-for-windows-insiders"></a><span data-ttu-id="4637a-111">Instalação simplificada para Participantes do Programa Windows Insider</span><span class="sxs-lookup"><span data-stu-id="4637a-111">Simplified Installation for Windows Insiders</span></span>

<span data-ttu-id="4637a-112">O processo de instalação do Subsistema do Windows para Linux foi bastante aprimorado nas versões prévias mais recentes de Participantes do Programa Windows Insider do Windows 10, substituindo as etapas manuais abaixo por um único comando.</span><span class="sxs-lookup"><span data-stu-id="4637a-112">The installation process for Windows Subsystem for Linux has been significantly improved in the latest Windows Insiders preview builds of Windows 10, replacing the manual steps below with a single command.</span></span>

<span data-ttu-id="4637a-113">Para usar o comando de instalação simplificada de `wsl --install`, você precisa:</span><span class="sxs-lookup"><span data-stu-id="4637a-113">In order to use the `wsl --install` simplified install command, you must:</span></span>

- <span data-ttu-id="4637a-114">Inscrever-se no [Programa Windows Insider](https://insider.windows.com/getting-started)</span><span class="sxs-lookup"><span data-stu-id="4637a-114">Join the [Windows Insiders Program](https://insider.windows.com/getting-started)</span></span>
- <span data-ttu-id="4637a-115">Instalar uma versão prévia do Windows 10 (build do sistema operacional 20262 ou superior).</span><span class="sxs-lookup"><span data-stu-id="4637a-115">Install a preview build of Windows 10 (OS build 20262 or higher).</span></span>
- <span data-ttu-id="4637a-116">Abra uma janela de linha de comando com privilégios de Administrador</span><span class="sxs-lookup"><span data-stu-id="4637a-116">Open a command line windows with Administrator privileges</span></span>

<span data-ttu-id="4637a-117">Assim que esses requisitos forem atendidos, para instalar o WSL:</span><span class="sxs-lookup"><span data-stu-id="4637a-117">Once those requirements are met, to install WSL:</span></span>

- <span data-ttu-id="4637a-118">Insira este comando na linha de comando que você abriu no modo Admin: `wsl.exe --install`</span><span class="sxs-lookup"><span data-stu-id="4637a-118">Enter this command in the command line you've opened in Admin mode: `wsl.exe --install`</span></span>
- <span data-ttu-id="4637a-119">Reinicie o computador</span><span class="sxs-lookup"><span data-stu-id="4637a-119">Restart your machine</span></span>

<span data-ttu-id="4637a-120">Na primeira vez que você iniciar uma distribuição do Linux recém-instalada, uma janela de console será aberta e será solicitado que você aguarde para que os arquivos sejam descompactados e armazenados em seu PC.</span><span class="sxs-lookup"><span data-stu-id="4637a-120">The first time you launch a newly installed Linux distribution, a console window will open and you'll be asked to wait for files to de-compress and be stored on your PC.</span></span> <span data-ttu-id="4637a-121">Todas as futuras inicializações deverão levar menos de um segundo.</span><span class="sxs-lookup"><span data-stu-id="4637a-121">All future launches should take less than a second.</span></span>

<span data-ttu-id="4637a-122">Em seguida, você precisará [criar uma conta de usuário e uma senha para sua nova distribuição do Linux](./user-support.md).</span><span class="sxs-lookup"><span data-stu-id="4637a-122">You will then need to [create a user account and password for your new Linux distribution](./user-support.md).</span></span>

<span data-ttu-id="4637a-123">**PARABÉNS! Você instalou e configurou com êxito uma distribuição do Linux totalmente integrada ao seu sistema operacional Windows.**</span><span class="sxs-lookup"><span data-stu-id="4637a-123">**CONGRATULATIONS! You've successfully installed and set up a Linux distribution that is completely integrated with your Windows operating system!**</span></span>

<span data-ttu-id="4637a-124">O comando --install executa as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="4637a-124">The --install command performs the following actions:</span></span>

- <span data-ttu-id="4637a-125">Habilita os componentes opcionais WSL e Plataforma de Máquina Virtual</span><span class="sxs-lookup"><span data-stu-id="4637a-125">Enables the optional WSL and Virtual Machine Platform components</span></span>
- <span data-ttu-id="4637a-126">Baixa e instala o kernel do Linux mais recente</span><span class="sxs-lookup"><span data-stu-id="4637a-126">Downloads and installs the latest Linux kernel</span></span>
- <span data-ttu-id="4637a-127">Define WSL 2 como o padrão</span><span class="sxs-lookup"><span data-stu-id="4637a-127">Sets WSL 2 as the default</span></span>
- <span data-ttu-id="4637a-128">Faz download e instala uma distribuição do Linux *(talvez seja necessário fazer a reinicialização)*</span><span class="sxs-lookup"><span data-stu-id="4637a-128">Downloads and installs a Linux distribution *(reboot may be required)*</span></span>

<span data-ttu-id="4637a-129">Por padrão, a distribuição do Linux instalada será o Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="4637a-129">By default, the installed Linux distribution will be Ubuntu.</span></span> <span data-ttu-id="4637a-130">Isso pode ser alterado usando `wsl --install -d <Distribution Name>`.</span><span class="sxs-lookup"><span data-stu-id="4637a-130">This can be changed using `wsl --install -d <Distribution Name>`.</span></span> <span data-ttu-id="4637a-131">*(Substituindo `<Distribution Name>` pelo nome da distribuição desejada.)* Outras distribuições do Linux poderão ser adicionadas ao computador após a instalação inicial usando o comando `wsl --install -d <Distribution Name>`.</span><span class="sxs-lookup"><span data-stu-id="4637a-131">*(Replacing `<Distribution Name>` with the name of your desired distribution.)* Additional Linux distributions may be added to your machine after the initial install using the `wsl --install -d <Distribution Name>` command.</span></span>

<span data-ttu-id="4637a-132">Para ver uma lista de distribuições do Linux disponíveis, insira `wsl --list --online`.</span><span class="sxs-lookup"><span data-stu-id="4637a-132">To see a list of available Linux distributions, enter `wsl --list --online`.</span></span>

## <a name="manual-installation-steps"></a><span data-ttu-id="4637a-133">Etapas de instalação manual</span><span class="sxs-lookup"><span data-stu-id="4637a-133">Manual Installation Steps</span></span>

<span data-ttu-id="4637a-134">Se você não estiver em um build dos Participantes do Programa Windows Insider do Windows Insiders, os recursos necessários para WSL precisarão ser habilitados manualmente seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="4637a-134">If you are not on a Windows Insiders build, the features required for WSL will need to be enabled manually following the steps below.</span></span>

## <a name="step-1---enable-the-windows-subsystem-for-linux"></a><span data-ttu-id="4637a-135">Etapa 1 – Habilitar o Subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="4637a-135">Step 1 - Enable the Windows Subsystem for Linux</span></span>

<span data-ttu-id="4637a-136">Antes de instalar qualquer distribuição do Linux no Windows, você precisará primeiro habilitar o recurso opcional "Subsistema do Windows para Linux".</span><span class="sxs-lookup"><span data-stu-id="4637a-136">You must first enable the "Windows Subsystem for Linux" optional feature before installing any Linux distributions on Windows.</span></span>

<span data-ttu-id="4637a-137">Abra o PowerShell como administrador e execute:</span><span class="sxs-lookup"><span data-stu-id="4637a-137">Open PowerShell as Administrator and run:</span></span>

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

<span data-ttu-id="4637a-138">Agora, é recomendável passar para a etapa 2, de atualização para o WSL 2. Mas, se você desejar instalar apenas o WSL 1, será possível **reiniciar** o computador e passar para a [Etapa 6 – Instalar a distribuição do Linux de sua escolha](./install-win10.md#step-6---install-your-linux-distribution-of-choice).</span><span class="sxs-lookup"><span data-stu-id="4637a-138">We recommend now moving on to step #2, updating to WSL 2, but if you wish to only install WSL 1, you can now **restart** your machine and move on to [Step 6 - Install your Linux distribution of choice](./install-win10.md#step-6---install-your-linux-distribution-of-choice).</span></span> <span data-ttu-id="4637a-139">Para atualizar para o WSL 2, **aguarde o seu computador ser reiniciado** e passe para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="4637a-139">To update to WSL 2, **wait to restart** your machine and move on to the next step.</span></span>

## <a name="step-2---check-requirements-for-running-wsl-2"></a><span data-ttu-id="4637a-140">Etapa 2 – Verificar os requisitos para executar o WSL 2</span><span class="sxs-lookup"><span data-stu-id="4637a-140">Step 2 - Check requirements for running WSL 2</span></span>

<span data-ttu-id="4637a-141">Para atualizar para o WSL 2, você precisa estar executando o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4637a-141">To update to WSL 2, you must be running Windows 10.</span></span>

- <span data-ttu-id="4637a-142">Para sistemas x64: **Versão 1903** ou superiores, com o **Build 18362** ou superiores.</span><span class="sxs-lookup"><span data-stu-id="4637a-142">For x64 systems: **Version 1903** or higher, with **Build 18362** or higher.</span></span>
- <span data-ttu-id="4637a-143">Para sistemas ARM64: **Versão 2004** ou superiores, com o **Build 19041** ou superiores.</span><span class="sxs-lookup"><span data-stu-id="4637a-143">For ARM64 systems: **Version 2004** or higher, with **Build 19041** or higher.</span></span>
- <span data-ttu-id="4637a-144">Os builds inferiores a 18362 não dão suporte a WSL 2.</span><span class="sxs-lookup"><span data-stu-id="4637a-144">Builds lower than 18362 do not support WSL 2.</span></span> <span data-ttu-id="4637a-145">Use o [Assistente do Windows Update](https://www.microsoft.com/software-download/windows10) para atualizar a sua versão do Windows.</span><span class="sxs-lookup"><span data-stu-id="4637a-145">Use the [Windows Update Assistant](https://www.microsoft.com/software-download/windows10) to update your version of Windows.</span></span>

<span data-ttu-id="4637a-146">Para verificar a sua versão e o número de build, selecione a **tecla do logotipo do Windows + R**, digite **winver** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4637a-146">To check your version and build number, select **Windows logo key + R**, type **winver**, select **OK**.</span></span> <span data-ttu-id="4637a-147">(Ou digite o comando `ver` no prompt de comando do Windows).</span><span class="sxs-lookup"><span data-stu-id="4637a-147">(Or enter the `ver` command in Windows Command Prompt).</span></span> <span data-ttu-id="4637a-148">[Atualize para a versão mais recente do Windows](ms-settings:windowsupdate) no menu Configurações.</span><span class="sxs-lookup"><span data-stu-id="4637a-148">[Update to the latest Windows version](ms-settings:windowsupdate) in the Settings menu.</span></span>

> [!NOTE]
> <span data-ttu-id="4637a-149">Se você estiver executando o Windows 10 versão 1903 ou 1909, abra "Configurações" no menu do Windows, navegue até "Atualizações e Segurança" e selecione "Verificar Atualizações".</span><span class="sxs-lookup"><span data-stu-id="4637a-149">If you are running Windows 10 version 1903 or 1909, open "Settings" from your Windows menu, navigate to "Update & Security" and select "Check for Updates".</span></span> <span data-ttu-id="4637a-150">O número de Build precisa ser 18362.1049+ ou 18363.1049+ e o nº do build secundário deve ser maior que .1049.</span><span class="sxs-lookup"><span data-stu-id="4637a-150">Your Build number must be 18362.1049+ or 18363.1049+, with the minor build # over .1049.</span></span> <span data-ttu-id="4637a-151">Leia mais: [O suporte a WSL 2 estará disponível em breve nas Versões 1903 e 1909 do Windows 10](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/).</span><span class="sxs-lookup"><span data-stu-id="4637a-151">Read more: [WSL 2 Support is coming to Windows 10 Versions 1903 and 1909](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/).</span></span> <span data-ttu-id="4637a-152">Confira as [instruções de solução de problemas](./troubleshooting.md#im-on-windows-10-version-1903-and-i-still-do-not-see-options-for-wsl-2).</span><span class="sxs-lookup"><span data-stu-id="4637a-152">See the [troubleshooting instructions](./troubleshooting.md#im-on-windows-10-version-1903-and-i-still-do-not-see-options-for-wsl-2).</span></span>

## <a name="step-3---enable-virtual-machine-feature"></a><span data-ttu-id="4637a-153">Etapa 3 – Habilitar o recurso de Máquina Virtual</span><span class="sxs-lookup"><span data-stu-id="4637a-153">Step 3 - Enable Virtual Machine feature</span></span>

<span data-ttu-id="4637a-154">Antes de instalar o WSL 2, você precisa habilitar o recurso opcional **Plataforma de Máquina Virtual**.</span><span class="sxs-lookup"><span data-stu-id="4637a-154">Before installing WSL 2, you must enable the **Virtual Machine Platform** optional feature.</span></span>

<span data-ttu-id="4637a-155">Abra o PowerShell como administrador e execute:</span><span class="sxs-lookup"><span data-stu-id="4637a-155">Open PowerShell as Administrator and run:</span></span>

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

<span data-ttu-id="4637a-156">**Reinicie** o computador para concluir a instalação do WSL e a atualização para o WSL 2.</span><span class="sxs-lookup"><span data-stu-id="4637a-156">**Restart** your machine to complete the WSL install and update to WSL 2.</span></span>

## <a name="step-4---download-the-linux-kernel-update-package"></a><span data-ttu-id="4637a-157">Etapa 4 – Baixar o pacote de atualização do kernel do Linux</span><span class="sxs-lookup"><span data-stu-id="4637a-157">Step 4 - Download the Linux kernel update package</span></span>

1. <span data-ttu-id="4637a-158">Baixar o pacote mais recente:</span><span class="sxs-lookup"><span data-stu-id="4637a-158">Download the latest package:</span></span>
    - [<span data-ttu-id="4637a-159">Pacote de atualização do kernel do Linux do WSL2 para computadores x64</span><span class="sxs-lookup"><span data-stu-id="4637a-159">WSL2 Linux kernel update package for x64 machines</span></span>](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

    > [!NOTE]
    > <span data-ttu-id="4637a-160">Se estiver usando um computador ARM64, baixe o [pacote ARM64](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi).</span><span class="sxs-lookup"><span data-stu-id="4637a-160">If you're using an ARM64 machine, please download the [ARM64 package](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi) instead.</span></span> <span data-ttu-id="4637a-161">Se você não tiver certeza do tipo do seu computador, abra o Prompt de Comando ou o PowerShell e insira: `systeminfo | find "System Type"`.</span><span class="sxs-lookup"><span data-stu-id="4637a-161">If you're not sure what kind of machine you have, open Command Prompt or PowerShell and enter: `systeminfo | find "System Type"`.</span></span>

2. <span data-ttu-id="4637a-162">Execute o pacote de atualização baixado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="4637a-162">Run the update package downloaded in the previous step.</span></span> <span data-ttu-id="4637a-163">(Clique duas vezes para executar. Você receberá uma solicitação para fornecer permissões elevadas; selecione 'sim' para aprovar essa instalação.)</span><span class="sxs-lookup"><span data-stu-id="4637a-163">(Double-click to run - you will be prompted for elevated permissions, select ‘yes’ to approve this installation.)</span></span>

<span data-ttu-id="4637a-164">Depois que a instalação for concluída, vá para a próxima etapa: configurar o WSL 2 como a sua versão padrão ao instalar novas distribuições do Linux</span><span class="sxs-lookup"><span data-stu-id="4637a-164">Once the installation is complete, move on to the next step - setting WSL 2 as your default version when installing new Linux distributions.</span></span> <span data-ttu-id="4637a-165">(ignore essa etapa se você quiser que as novas instalações do Linux sejam definidas como WSL 1).</span><span class="sxs-lookup"><span data-stu-id="4637a-165">(Skip this step if you want your new Linux installs to be set to WSL 1).</span></span>

> [!NOTE]
> <span data-ttu-id="4637a-166">Para obter mais informações, leia o artigo [Alterações na atualização do kernel do Linux para o WSL 2](https://devblogs.microsoft.com/commandline/wsl2-will-be-generally-available-in-windows-10-version-2004), disponível no [blog da linha de comando do Windows](https://aka.ms/cliblog).</span><span class="sxs-lookup"><span data-stu-id="4637a-166">For more information, read the article [changes to updating the WSL2 Linux kernel](https://devblogs.microsoft.com/commandline/wsl2-will-be-generally-available-in-windows-10-version-2004), available on the [Windows Command Line Blog](https://aka.ms/cliblog).</span></span>

## <a name="step-5---set-wsl-2-as-your-default-version"></a><span data-ttu-id="4637a-167">Etapa 5 – Definir o WSL 2 como a sua versão padrão</span><span class="sxs-lookup"><span data-stu-id="4637a-167">Step 5 - Set WSL 2 as your default version</span></span>

<span data-ttu-id="4637a-168">Abra o PowerShell e execute este comando para definir o WSL 2 como a versão padrão ao instalar uma nova distribuição do Linux:</span><span class="sxs-lookup"><span data-stu-id="4637a-168">Open PowerShell and run this command to set WSL 2 as the default version when installing a new Linux distribution:</span></span>

```powershell
wsl --set-default-version 2
```

## <a name="step-6---install-your-linux-distribution-of-choice"></a><span data-ttu-id="4637a-169">Etapa 6 – Instalar a distribuição do Linux de sua escolha</span><span class="sxs-lookup"><span data-stu-id="4637a-169">Step 6 - Install your Linux distribution of choice</span></span>

1. <span data-ttu-id="4637a-170">Abra a [Microsoft Store](https://aka.ms/wslstore) e escolha sua distribuição do Linux favorita.</span><span class="sxs-lookup"><span data-stu-id="4637a-170">Open the [Microsoft Store](https://aka.ms/wslstore) and select your favorite Linux distribution.</span></span>

    ![Exibição das distribuições do Linux na Microsoft Store](media/store.png)

    <span data-ttu-id="4637a-172">Os links a seguir abrirão a página da Microsoft Store para cada distribuição:</span><span class="sxs-lookup"><span data-stu-id="4637a-172">The following links will open the Microsoft store page for each distribution:</span></span>

    - [<span data-ttu-id="4637a-173">Ubuntu 16.04 LTS</span><span class="sxs-lookup"><span data-stu-id="4637a-173">Ubuntu 16.04 LTS</span></span>](https://www.microsoft.com/store/apps/9pjn388hp8c9)
    - [<span data-ttu-id="4637a-174">Ubuntu 18.04 LTS</span><span class="sxs-lookup"><span data-stu-id="4637a-174">Ubuntu 18.04 LTS</span></span>](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
    - [<span data-ttu-id="4637a-175">Ubuntu 20.04 LTS</span><span class="sxs-lookup"><span data-stu-id="4637a-175">Ubuntu 20.04 LTS</span></span>](https://www.microsoft.com/store/apps/9n6svws3rx71)
    - [<span data-ttu-id="4637a-176">OpenSUSE Leap 15.1</span><span class="sxs-lookup"><span data-stu-id="4637a-176">openSUSE Leap 15.1</span></span>](https://www.microsoft.com/store/apps/9NJFZK00FGKV)
    - [<span data-ttu-id="4637a-177">SUSE Linux Enterprise Server 12 SP5</span><span class="sxs-lookup"><span data-stu-id="4637a-177">SUSE Linux Enterprise Server 12 SP5</span></span>](https://www.microsoft.com/store/apps/9MZ3D1TRP8T1)
    - [<span data-ttu-id="4637a-178">SUSE Linux Enterprise Server 15 SP1</span><span class="sxs-lookup"><span data-stu-id="4637a-178">SUSE Linux Enterprise Server 15 SP1</span></span>](https://www.microsoft.com/store/apps/9PN498VPMF3Z)
    - [<span data-ttu-id="4637a-179">Kali Linux</span><span class="sxs-lookup"><span data-stu-id="4637a-179">Kali Linux</span></span>](https://www.microsoft.com/store/apps/9PKR34TNCV07)
    - [<span data-ttu-id="4637a-180">Debian GNU/Linux</span><span class="sxs-lookup"><span data-stu-id="4637a-180">Debian GNU/Linux</span></span>](https://www.microsoft.com/store/apps/9MSVKQC78PK6)
    - [<span data-ttu-id="4637a-181">Fedora Remix para WSL</span><span class="sxs-lookup"><span data-stu-id="4637a-181">Fedora Remix for WSL</span></span>](https://www.microsoft.com/store/apps/9n6gdm4k2hnc)
    - [<span data-ttu-id="4637a-182">Pengwin</span><span class="sxs-lookup"><span data-stu-id="4637a-182">Pengwin</span></span>](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
    - [<span data-ttu-id="4637a-183">Pengwin Enterprise</span><span class="sxs-lookup"><span data-stu-id="4637a-183">Pengwin Enterprise</span></span>](https://www.microsoft.com/store/apps/9N8LP0X93VCP)
    - [<span data-ttu-id="4637a-184">Alpine WSL</span><span class="sxs-lookup"><span data-stu-id="4637a-184">Alpine WSL</span></span>](https://www.microsoft.com/store/apps/9p804crf0395)

2. <span data-ttu-id="4637a-185">Na página da distribuição, selecione "Obter".</span><span class="sxs-lookup"><span data-stu-id="4637a-185">From the distribution's page, select "Get".</span></span>

    ![Distribuições do Linux na Microsoft Store](media/UbuntuStore.png)

<span data-ttu-id="4637a-187">Na primeira vez que você iniciar uma distribuição do Linux recém-instalada, uma janela de console será aberta e será solicitado que você aguarde um ou dois minutos para que os arquivos sejam descompactados e armazenados em seu PC.</span><span class="sxs-lookup"><span data-stu-id="4637a-187">The first time you launch a newly installed Linux distribution, a console window will open and you'll be asked to wait for a minute or two for files to de-compress and be stored on your PC.</span></span> <span data-ttu-id="4637a-188">Todas as futuras inicializações deverão levar menos de um segundo.</span><span class="sxs-lookup"><span data-stu-id="4637a-188">All future launches should take less than a second.</span></span>

<span data-ttu-id="4637a-189">Em seguida, você precisará [criar uma conta de usuário e uma senha para sua nova distribuição do Linux](./user-support.md).</span><span class="sxs-lookup"><span data-stu-id="4637a-189">You will then need to [create a user account and password for your new Linux distribution](./user-support.md).</span></span>

![Desempacotamento do Ubuntu no console do Windows](media/UbuntuInstall.png)

<span data-ttu-id="4637a-191">**PARABÉNS! Você instalou e configurou com êxito uma distribuição do Linux totalmente integrada ao seu sistema operacional Windows.**</span><span class="sxs-lookup"><span data-stu-id="4637a-191">**CONGRATULATIONS! You've successfully installed and set up a Linux distribution that is completely integrated with your Windows operating system!**</span></span>

## <a name="install-windows-terminal-optional"></a><span data-ttu-id="4637a-192">Instalar o Terminal do Windows (opcional)</span><span class="sxs-lookup"><span data-stu-id="4637a-192">Install Windows Terminal (optional)</span></span>

<span data-ttu-id="4637a-193">O Terminal do Windows permite habilitar várias guias (para alternar rapidamente entre as linhas de comando do Linux, o Prompt de Comando do Windows, o PowerShell, a CLI do Azure etc.), criar associações de chave personalizadas (teclas de atalho para abrir ou fechar guias, copiar e colar etc.), usar o recurso de pesquisa e configurar temas personalizados (esquemas de cores, estilos e tamanhos de fonte, imagem de tela de fundo/desfoque/transparência).</span><span class="sxs-lookup"><span data-stu-id="4637a-193">Windows Terminal enables multiple tabs (quickly switch between multiple Linux command lines, Windows Command Prompt, PowerShell, Azure CLI, etc), create custom key bindings (shortcut keys for opening or closing tabs, copy+paste, etc.), use the search feature, and custom themes (color schemes, font styles and sizes, background image/blur/transparency).</span></span> [<span data-ttu-id="4637a-194">Saiba mais.</span><span class="sxs-lookup"><span data-stu-id="4637a-194">Learn more.</span></span>](/windows/terminal)

<span data-ttu-id="4637a-195">[Instalar o Terminal do Windows](/windows/terminal/get-started).</span><span class="sxs-lookup"><span data-stu-id="4637a-195">[Install Windows Terminal](/windows/terminal/get-started).</span></span>

  ![Terminal do Windows](media/terminal.png)

## <a name="set-your-distribution-version-to-wsl-1-or-wsl-2"></a><span data-ttu-id="4637a-197">Definir a versão de distribuição para WSL 1 ou WSL 2</span><span class="sxs-lookup"><span data-stu-id="4637a-197">Set your distribution version to WSL 1 or WSL 2</span></span>

<span data-ttu-id="4637a-198">Verifique a versão do WSL atribuída a cada uma das distribuições do Linux instaladas abrindo a linha de comando do PowerShell e inserindo o comando (disponível somente no [Windows Build 18362 ou superior](ms-settings:windowsupdate)): `wsl -l -v`</span><span class="sxs-lookup"><span data-stu-id="4637a-198">You can check the WSL version assigned to each of the Linux distributions you have installed by opening the PowerShell command line and entering the command (only available in [Windows Build 18362 or higher](ms-settings:windowsupdate)): `wsl -l -v`</span></span>

```powershell
wsl --list --verbose
```

<span data-ttu-id="4637a-199">Para definir uma distribuição para ter suporte de qualquer versão do WSL, execute:</span><span class="sxs-lookup"><span data-stu-id="4637a-199">To set a distribution to be backed by either version of WSL please run:</span></span>

```powershell
wsl --set-version <distribution name> <versionNumber>
```

<span data-ttu-id="4637a-200">Assegure-se de substituir `<distribution name>` pelo nome real da sua distribuição e `<versionNumber>` pelo número '1' ou '2'.</span><span class="sxs-lookup"><span data-stu-id="4637a-200">Make sure to replace `<distribution name>` with the actual name of your distribution and `<versionNumber>` with the number '1' or '2'.</span></span> <span data-ttu-id="4637a-201">Você pode retornar ao WSL 1 a qualquer momento executando o mesmo comando acima, mas substituindo “2” por “1”.</span><span class="sxs-lookup"><span data-stu-id="4637a-201">You can change back to WSL 1 at anytime by running the same command as above but replacing the '2' with a '1'.</span></span>

> [!NOTE]
> <span data-ttu-id="4637a-202">A atualização da WSL 1 para a WSL 2 pode levar vários minutos para ser concluída, dependendo do tamanho da sua distribuição alvo.</span><span class="sxs-lookup"><span data-stu-id="4637a-202">The update from WSL 1 to WSL 2 may take several minutes to complete depending on the size of your targeted distribution.</span></span> <span data-ttu-id="4637a-203">Se você estiver executando uma instalação mais antiga (herdada) do WSL 1 da Atualização para Criadores ou da Atualização de Aniversário do Windows 10, poderá encontrar um erro de atualização.</span><span class="sxs-lookup"><span data-stu-id="4637a-203">If you are running an older (legacy) installation of WSL 1 from Windows 10 Anniversary Update or Creators Update, you may encounter an update error.</span></span> <span data-ttu-id="4637a-204">Siga estas instruções para [desinstalar e remover as distribuições herdadas](./install-legacy.md#uninstallingremoving-the-legacy-distro).</span><span class="sxs-lookup"><span data-stu-id="4637a-204">Follow these instructions to [uninstall and remove any legacy distributions](./install-legacy.md#uninstallingremoving-the-legacy-distro).</span></span>
>
> <span data-ttu-id="4637a-205">Se `wsl --set-default-version` resultar como um comando inválido, insira `wsl --help`.</span><span class="sxs-lookup"><span data-stu-id="4637a-205">If `wsl --set-default-version` results as an invalid command, enter `wsl --help`.</span></span> <span data-ttu-id="4637a-206">Se `--set-default-version` não estiver listado, isso significa que o sistema operacional não é compatível com ele, e você precisará atualizá-lo para a versão 1903, Build 18362 ou superior.</span><span class="sxs-lookup"><span data-stu-id="4637a-206">If the `--set-default-version` is not listed, it means that your OS doesn't support it and you need to update to version 1903, Build 18362 or higher.</span></span>
>
> <span data-ttu-id="4637a-207">Você verá esta mensagem depois de executar o comando: `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`.</span><span class="sxs-lookup"><span data-stu-id="4637a-207">If you see this message after running the command: `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`.</span></span> <span data-ttu-id="4637a-208">Você ainda precisa instalar o pacote de atualização MSI do kernel do Linux.</span><span class="sxs-lookup"><span data-stu-id="4637a-208">You still need to install the MSI Linux kernel update package.</span></span>

<span data-ttu-id="4637a-209">Além disso, se quiser tornar o WSL 2 sua arquitetura padrão, você poderá fazê-lo com este comando:</span><span class="sxs-lookup"><span data-stu-id="4637a-209">Additionally, if you want to make WSL 2 your default architecture you can do so with this command:</span></span>

```powershell
wsl --set-default-version 2
```

<span data-ttu-id="4637a-210">Isso definirá a versão de qualquer nova distribuição instalada no WSL 2.</span><span class="sxs-lookup"><span data-stu-id="4637a-210">This will set the version of any new distribution installed to WSL 2.</span></span>

## <a name="troubleshooting-installation"></a><span data-ttu-id="4637a-211">Como solucionar problemas de instalação</span><span class="sxs-lookup"><span data-stu-id="4637a-211">Troubleshooting installation</span></span>

<span data-ttu-id="4637a-212">Veja abaixo erros relacionados e correções sugeridas.</span><span class="sxs-lookup"><span data-stu-id="4637a-212">Below are related errors and suggested fixes.</span></span> <span data-ttu-id="4637a-213">Consulte a [página de solução de problemas do WSL](troubleshooting.md) para ver outros erros comuns e suas soluções.</span><span class="sxs-lookup"><span data-stu-id="4637a-213">Refer to the [WSL troubleshooting page](troubleshooting.md) for other common errors and their solutions.</span></span>

- <span data-ttu-id="4637a-214">**Falha na instalação com o erro 0x80070003**</span><span class="sxs-lookup"><span data-stu-id="4637a-214">**Installation failed with error 0x80070003**</span></span>
  - <span data-ttu-id="4637a-215">O Subsistema Windows para Linux é executado somente na unidade do sistema (normalmente, a unidade `C:`).</span><span class="sxs-lookup"><span data-stu-id="4637a-215">The Windows Subsystem for Linux only runs on your system drive (usually this is your `C:` drive).</span></span> <span data-ttu-id="4637a-216">Verifique se as distribuições estão armazenadas na unidade do sistema:</span><span class="sxs-lookup"><span data-stu-id="4637a-216">Make sure that distributions are stored on your system drive:</span></span>  
  - <span data-ttu-id="4637a-217">Abra **Configurações** -> \*\*Sistema –> **Armazenamento** -> **Mais Configurações de Armazenamento: Altere onde o novo conteúdo é salvo**
    ![Imagem das configurações do sistema para instalar aplicativos na unidade C:](media/AppStorage.png)</span><span class="sxs-lookup"><span data-stu-id="4637a-217">Open **Settings** -> \*\*System --> **Storage** -> **More Storage Settings: Change where new content is saved**
![Picture of system settings to install apps on C: drive](media/AppStorage.png)</span></span>

- <span data-ttu-id="4637a-218">**WslRegisterDistribution falhou com o erro 0x8007019e**</span><span class="sxs-lookup"><span data-stu-id="4637a-218">**WslRegisterDistribution failed with error 0x8007019e**</span></span>
  - <span data-ttu-id="4637a-219">O componente opcional do Subsistema Windows para Linux não está habilitado:</span><span class="sxs-lookup"><span data-stu-id="4637a-219">The Windows Subsystem for Linux optional component is not enabled:</span></span>
  - <span data-ttu-id="4637a-220">Abra **Painel de Controle** -> **Programas e Recursos** -> **Ativar ou Desativar Recursos do Windows** -> Selecione **Subsistema do Windows para Linux** ou use o cmdlet PowerShell mencionado no início deste artigo.</span><span class="sxs-lookup"><span data-stu-id="4637a-220">Open **Control Panel** -> **Programs and Features** -> **Turn Windows Feature on or off** -> Check **Windows Subsystem for Linux** or using the PowerShell cmdlet mentioned at the beginning of this article.</span></span>

- <span data-ttu-id="4637a-221">**Ocorreu falha na instalação com o erro 0x80070003 ou 0x80370102**</span><span class="sxs-lookup"><span data-stu-id="4637a-221">**Installation failed with error 0x80070003 or error 0x80370102**</span></span>
  - <span data-ttu-id="4637a-222">Verifique se a virtualização está habilitada dentro do BIOS do seu computador.</span><span class="sxs-lookup"><span data-stu-id="4637a-222">Please make sure that virtualization is enabled inside of your computer's BIOS.</span></span> <span data-ttu-id="4637a-223">As instruções para fazer isso variam de um computador para o outro e muito provavelmente estarão sob opções relacionadas à CPU.</span><span class="sxs-lookup"><span data-stu-id="4637a-223">The instructions on how to do this will vary from computer to computer, and will most likely be under CPU related options.</span></span>

- <span data-ttu-id="4637a-224">**Erro ao tentar fazer upgrade: `Invalid command line option: wsl --set-version Ubuntu 2`**</span><span class="sxs-lookup"><span data-stu-id="4637a-224">**Error when trying to upgrade: `Invalid command line option: wsl --set-version Ubuntu 2`**</span></span>
  - <span data-ttu-id="4637a-225">Verifique se você tem o Subsistema do Windows para Linux habilitado e se está usando o Windows versão do Build 18362 ou superior.</span><span class="sxs-lookup"><span data-stu-id="4637a-225">Enure that you have the Windows Subsystem for Linux enabled, and that you're using Windows Build version 18362 or higher.</span></span> <span data-ttu-id="4637a-226">Para habilitar o WSL, execute este comando em um prompt do PowerShell com privilégios de administrador: `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`.</span><span class="sxs-lookup"><span data-stu-id="4637a-226">To enable WSL run this command in a PowerShell prompt with admin privileges: `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`.</span></span>

- <span data-ttu-id="4637a-227">**A operação solicitada não pôde ser concluída devido a uma limitação do sistema de disco virtual. Os arquivos do disco rígido virtual devem ser descompactados e descriptografados e não devem ser esparsos.**</span><span class="sxs-lookup"><span data-stu-id="4637a-227">**The requested operation could not be completed due to a virtual disk system limitation. Virtual hard disk files must be uncompressed and unencrypted and must not be sparse.**</span></span>
  - <span data-ttu-id="4637a-228">Desmarque "Compactar conteúdo" (bem como "Criptografar conteúdo", se estiver marcado) abrindo a pasta de perfil da sua distribuição do Linux.</span><span class="sxs-lookup"><span data-stu-id="4637a-228">Deselect “Compress contents” (as well as “Encrypt contents” if that’s checked) by opening the profile folder for your Linux distribution.</span></span> <span data-ttu-id="4637a-229">Ela deve estar localizada em uma pasta no sistema de arquivos do Windows, algo como: `USERPROFILE%\AppData\Local\Packages\CanonicalGroupLimited...`</span><span class="sxs-lookup"><span data-stu-id="4637a-229">It should be located in a folder on your Windows file system, something like: `USERPROFILE%\AppData\Local\Packages\CanonicalGroupLimited...`</span></span>
  - <span data-ttu-id="4637a-230">Nesse perfil de distribuição do Linux, deve haver uma pasta LocalState.</span><span class="sxs-lookup"><span data-stu-id="4637a-230">In this Linux distro profile, there should be a LocalState folder.</span></span> <span data-ttu-id="4637a-231">Clique com o botão direito do mouse nessa pasta para exibir um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="4637a-231">Right-click this folder to display a menu of options.</span></span> <span data-ttu-id="4637a-232">Selecione Propriedades > Avançado e, em seguida, verifique se as caixas de seleção "Compactar conteúdo para economizar espaço em disco" e "Criptografar conteúdo para proteger dados" estão desmarcadas (não selecionadas).</span><span class="sxs-lookup"><span data-stu-id="4637a-232">Select Properties > Advanced and then ensure that the “Compress contents to save disk space” and “Encrypt contents to secure data” checkboxes are unselected (not checked).</span></span> <span data-ttu-id="4637a-233">Se for solicitado que você aplique isso apenas à pasta atual ou a todas as subpastas e arquivos, selecione "somente esta pasta" porque você só vai limpar o sinalizador de compactação.</span><span class="sxs-lookup"><span data-stu-id="4637a-233">If you are asked whether to apply this to just to the current folder or to all subfolders and files, select “just this folder” because you are only clearing the compress flag.</span></span> <span data-ttu-id="4637a-234">Depois disso, o comando `wsl --set-version` deve funcionar.</span><span class="sxs-lookup"><span data-stu-id="4637a-234">After this, the `wsl --set-version` command should work.</span></span>

![Captura de tela das configurações da propriedade de distribuição do WSL](media/troubleshooting-virtualdisk-compress.png)

> [!NOTE]
> <span data-ttu-id="4637a-236">No meu caso, a pasta LocalState da minha distribuição do Ubuntu 18.04 estava localizada em C:\Users\<my-user-name>\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc</span><span class="sxs-lookup"><span data-stu-id="4637a-236">In my case, the LocalState folder for my Ubuntu 18.04 distribution was located at C:\Users\<my-user-name>\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc</span></span>
>
> <span data-ttu-id="4637a-237">Para obter informações atualizadas, verifique o [thread 4103 do GitHub dos documentos do WSL](https://github.com/microsoft/WSL/issues/4103) em que esse problema está sendo acompanhado.</span><span class="sxs-lookup"><span data-stu-id="4637a-237">Check [WSL Docs GitHub thread #4103](https://github.com/microsoft/WSL/issues/4103) where this issue is being tracked for updated information.</span></span>

- <span data-ttu-id="4637a-238">**O termo 'wsl' não é reconhecido como nome de um cmdlet, uma função, um arquivo de script ou um programa operável.**</span><span class="sxs-lookup"><span data-stu-id="4637a-238">**The term 'wsl' is not recognized as the name of a cmdlet, function, script file, or operable program.**</span></span>
  - <span data-ttu-id="4637a-239">Verifique se o [componente opcional do Subsistema do Windows para Linux está instalado](./install-win10.md#step-3---enable-virtual-machine-feature).</span><span class="sxs-lookup"><span data-stu-id="4637a-239">Ensure that the [Windows Subsystem for Linux Optional Component is installed](./install-win10.md#step-3---enable-virtual-machine-feature).</span></span> <span data-ttu-id="4637a-240">Além disso, se você estiver usando um dispositivo ARM64 e executar esse comando no PowerShell, receberá esse erro.</span><span class="sxs-lookup"><span data-stu-id="4637a-240">Additionally, if you are using an ARM64 device and running this command from PowerShell, you will receive this error.</span></span> <span data-ttu-id="4637a-241">Em vez disso, execute `wsl.exe` no [PowerShell Core](/powershell/scripting/install/installing-powershell-core-on-windows) ou no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4637a-241">Instead run `wsl.exe` from [PowerShell Core](/powershell/scripting/install/installing-powershell-core-on-windows), or Command Prompt.</span></span>

- <span data-ttu-id="4637a-242">**Erro: esta atualização se aplica somente a computadores com o Subsistema do Windows para Linux.**</span><span class="sxs-lookup"><span data-stu-id="4637a-242">**Error: This update only applies to machines with the Windows Subsystem for Linux.**</span></span>
  - <span data-ttu-id="4637a-243">Para instalar o pacote MSI de atualização do kernel do Linux, o WSL é exigido e deve ser habilitado primeiro.</span><span class="sxs-lookup"><span data-stu-id="4637a-243">To install the Linux kernel update MSI package, WSL is required and should be enabled first.</span></span> <span data-ttu-id="4637a-244">Se ele falhar, você verá a mensagem: `This update only applies to machines with the Windows Subsystem for Linux`.</span><span class="sxs-lookup"><span data-stu-id="4637a-244">If it fails, it you will see the message: `This update only applies to machines with the Windows Subsystem for Linux`.</span></span>
  - <span data-ttu-id="4637a-245">Há três motivos possíveis para você ver essa mensagem:</span><span class="sxs-lookup"><span data-stu-id="4637a-245">There are three possible reason you see this message:</span></span>

  1. <span data-ttu-id="4637a-246">Você ainda está usando uma versão antiga do Windows, que não dá suporte ao WSL 2.</span><span class="sxs-lookup"><span data-stu-id="4637a-246">You are still in old version of Windows which doesn't support WSL 2.</span></span> <span data-ttu-id="4637a-247">Confira a etapa nº 2 para obter os requisitos de versão e os links a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="4637a-247">See step #2 for version requirements and links to update.</span></span>

  2. <span data-ttu-id="4637a-248">O WSL não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="4637a-248">WSL is not enabled.</span></span> <span data-ttu-id="4637a-249">Você precisará retornar à etapa nº 1 e verificar se o recurso opcional do WSL está habilitado no seu computador.</span><span class="sxs-lookup"><span data-stu-id="4637a-249">You will need to return to step #1 and ensure that the optional WSL feature is enabled on your machine.</span></span>

  3. <span data-ttu-id="4637a-250">Depois que você habilitar o WSL, uma reinicialização será exigida para que ele entre em vigor. Reinicialize o computador e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="4637a-250">After you enabled WSL, a reboot is required for it to take effect, reboot your machine and try again.</span></span>

- <span data-ttu-id="4637a-251">**Erro: o WSL 2 exige uma atualização do componente kernel. Para obter mais informações, visite https://aka.ms/wsl2kernel.**</span><span class="sxs-lookup"><span data-stu-id="4637a-251">**Error: WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel .**</span></span>
  - <span data-ttu-id="4637a-252">Se o pacote do kernel do Linux está ausente na pasta %SystemRoot%\system32\lxss\tools, você encontra esse erro.</span><span class="sxs-lookup"><span data-stu-id="4637a-252">If the Linux kernel package is missing in the %SystemRoot%\system32\lxss\tools folder, you will encounter this error.</span></span> <span data-ttu-id="4637a-253">Resolva-o instalando o pacote MSI de atualização do kernel do Linux na etapa nº 4 das instruções de instalação.</span><span class="sxs-lookup"><span data-stu-id="4637a-253">Resolve it by installing the Linux kernel update MSI package in step #4 of these installation instructions.</span></span> <span data-ttu-id="4637a-254">Talvez você precise desinstalar o MSI em ['Adicionar ou Remover Programas'](ms-settings:appsfeatures-app) e instalar ele novamente.</span><span class="sxs-lookup"><span data-stu-id="4637a-254">You may need to uninstall the MSI from ['Add or Remove Programs'](ms-settings:appsfeatures-app), and install it again.</span></span>
