---
title: Atualizar o kernel do WSL 2 Linux
description: Instruções sobre como atualizar o kernel do WSL 2 Linux manualmente
keywords: wsl, windows, linux kernel, windows subsystem for linux, kernel
ms.date: 03/12/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 4ca1bde2f8dc36c85b0c998c01f7f77eafe5f695
ms.sourcegitcommit: fef5def707ccec57d6f0c5e9c89680754ea06411
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95416643"
---
# <a name="updating-the-wsl-2-linux-kernel"></a><span data-ttu-id="b6dcf-104">Atualizar o kernel do WSL 2 Linux</span><span class="sxs-lookup"><span data-stu-id="b6dcf-104">Updating the WSL 2 Linux kernel</span></span>

<span data-ttu-id="b6dcf-105">Para atualizar manualmente o kernel do Linux dentro do WSL2, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-105">To manually update the Linux kernel inside of WSL 2 please follow these steps.</span></span>

> [!NOTE] 
> <span data-ttu-id="b6dcf-106">Se o instalador não conseguir encontrar a WSL 1, clique com o botão direito do mouse no instalador de atualização do kernel do Linux e pressione "Desinstalar", então execute novamente o instalador.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-106">If the installer can't find WSL 1, right-click the Linux kernel update installer and press "Uninstall", then rerun the installer.</span></span>

## <a name="download-the-linux-kernel-update-package"></a><span data-ttu-id="b6dcf-107">Baixar o pacote de atualização do kernel do Linux</span><span class="sxs-lookup"><span data-stu-id="b6dcf-107">Download the Linux kernel update package</span></span>

<span data-ttu-id="b6dcf-108">[Baixe o pacote de atualização do último kernel do Linux para o WSL 2](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi) para computadores x64.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-108">Please [download the latest WSL2 Linux kernel](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi) update package for x64 machines.</span></span>

> [!NOTE]
> <span data-ttu-id="b6dcf-109">Se estiver usando um computador ARM64, baixe o [pacote ARM64](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi).</span><span class="sxs-lookup"><span data-stu-id="b6dcf-109">If you're using an ARM64 machine, please download the [ARM64 package](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi) instead.</span></span>

## <a name="install-the-linux-kernel-update-package"></a><span data-ttu-id="b6dcf-110">Instalar o pacote de atualização do kernel do Linux</span><span class="sxs-lookup"><span data-stu-id="b6dcf-110">Install the Linux kernel update package</span></span>

<span data-ttu-id="b6dcf-111">Para instalar o pacote de atualização do kernel do Linux:</span><span class="sxs-lookup"><span data-stu-id="b6dcf-111">To install the Linux kernel update package:</span></span>

  1. <span data-ttu-id="b6dcf-112">Execute o pacote de atualização baixado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-112">Run the update package downloaded in the previous step.</span></span>

  2. <span data-ttu-id="b6dcf-113">Você receberá uma solicitação para fornecer permissões elevadas, selecione 'Sim' para aprovar essa instalação.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-113">You will be prompted for elevated permissions, select ‘yes’ to approve this installation.</span></span>

  3. <span data-ttu-id="b6dcf-114">Quando a instalação for concluída, você estará pronto para começar a usar o WSL2!</span><span class="sxs-lookup"><span data-stu-id="b6dcf-114">Once the installation is complete, you are ready to begin using WSL2!</span></span>

## <a name="future-plans-for-updating-the-wsl2-linux-kernel"></a><span data-ttu-id="b6dcf-115">Planos futuros para atualizar o kernel do WSL2 Linux</span><span class="sxs-lookup"><span data-stu-id="b6dcf-115">Future plans for updating the WSL2 Linux kernel</span></span>

<span data-ttu-id="b6dcf-116">Para obter mais informações, leia o artigo [Alterações na atualização do kernel do Linux para o WSL 2](https://devblogs.microsoft.com/commandline/wsl2-will-be-generally-available-in-windows-10-version-2004), disponível no [blog da linha de comando do Windows](https://aka.ms/cliblog).</span><span class="sxs-lookup"><span data-stu-id="b6dcf-116">For more information, read the article [changes to updating the WSL2 Linux kernel](https://devblogs.microsoft.com/commandline/wsl2-will-be-generally-available-in-windows-10-version-2004), available on the [Windows Command Line Blog](https://aka.ms/cliblog).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b6dcf-117">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="b6dcf-117">Troubleshooting</span></span>

### <a name="this-update-only-applies-to-machines-with-the-windows-subsystem-for-linux"></a><span data-ttu-id="b6dcf-118">Essa atualização se aplica somente a computadores com o Subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="b6dcf-118">This update only applies to machines with the Windows Subsystem for Linux</span></span>
<span data-ttu-id="b6dcf-119">Para instalar o kernel do MSI, o WSL é necessário e deve ser habilitado primeiro.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-119">To install MSI kernel, WSL is required and should be enabled first.</span></span> <span data-ttu-id="b6dcf-120">Se ele falhar, você verá a mensagem: `This update only applies to machines with the Windows Subsystem for Linux`.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-120">If it fails, it you will see the message: `This update only applies to machines with the Windows Subsystem for Linux`.</span></span> 

<span data-ttu-id="b6dcf-121">Há três motivos possíveis para você ver essa mensagem:</span><span class="sxs-lookup"><span data-stu-id="b6dcf-121">There are three possible reason you see this message:</span></span>

1. <span data-ttu-id="b6dcf-122">Você ainda está usando uma versão antiga do Windows, que não dá suporte ao WSL 2.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-122">You are still in old version of Windows which doesn't support WSL 2.</span></span> <span data-ttu-id="b6dcf-123">Verifique os [requisitos do WSL 2](./install-win10.md#step-2---update-to-wsl-2) e faça as atualizações necessárias para usá-lo</span><span class="sxs-lookup"><span data-stu-id="b6dcf-123">Please check the [WSL 2 requirements](./install-win10.md#step-2---update-to-wsl-2) and upgrade to use WSL</span></span> 
2. 
2. <span data-ttu-id="b6dcf-124">O `Windows Subsystem for Linux` não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-124">`Windows Subsystem for Linux` is not enabled.</span></span> <span data-ttu-id="b6dcf-125">Siga o [guia de instalação do Subsistema do Windows para Linux](./install-win10.md#step-1---enable-the-windows-subsystem-for-linux).</span><span class="sxs-lookup"><span data-stu-id="b6dcf-125">Please follow the [Windows Subsystem for Linux Installation Guide](./install-win10.md#step-1---enable-the-windows-subsystem-for-linux).</span></span>
3. <span data-ttu-id="b6dcf-126">Depois que você habilitar o `Windows Subsystem for Linux`, uma reinicialização será necessária para que ele entre em vigor. Reinicialize o computador e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-126">After you enabled `Windows Subsystem for Linux`, a reboot is required to take into effect, please reboot your machine and try again.</span></span>

### `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`

<span data-ttu-id="b6dcf-127">Cada vez que o kernel estiver ausente em %SystemRoot%\system32\lxss\tools\,, você deverá encontrar o erro acima.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-127">Each time kernel is missing in %SystemRoot%\system32\lxss\tools\, you may run into the above error.</span></span>

<span data-ttu-id="b6dcf-128">Aqui estão algumas maneiras possíveis de solucioná-lo:</span><span class="sxs-lookup"><span data-stu-id="b6dcf-128">Here are some possible ways to resolve it:</span></span>

1. <span data-ttu-id="b6dcf-129">Instale o kernel do Linux manualmente seguindo as instruções nesta página.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-129">Install the Linux kernel manually following the instructions on this page.</span></span>
2. <span data-ttu-id="b6dcf-130">Desinstale o MSI em 'Adicionar ou Remover Programas' e instale-o novamente.</span><span class="sxs-lookup"><span data-stu-id="b6dcf-130">Uninstall the MSI from 'Add or Remove Programs', and install it again.</span></span>
