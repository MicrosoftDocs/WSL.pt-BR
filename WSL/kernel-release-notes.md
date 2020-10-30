---
title: Notas sobre a versão do kernel do Subsistema do Windows para Linux
description: Notas sobre a versão do subsistema Windows para Linux.  Atualizadas mensalmente.
keywords: notas sobre a versão, wsl, windows, subsistema do windows para linux, windowssubsystem, ubuntu, kernel
ms.date: 06/09/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 0ab1e7e85ce9d601bd8eb602d98e3487e8202e03
ms.sourcegitcommit: 609850fadd20687636b8486264e87af47c538111
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2020
ms.locfileid: "92444814"
---
# <a name="release-notes-for-windows-subsystem-for-linux-kernel"></a><span data-ttu-id="5ee83-105">Notas sobre a versão do kernel do Subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="5ee83-105">Release Notes for Windows Subsystem for Linux kernel</span></span>

<span data-ttu-id="5ee83-106">Adicionamos suporte para distribuições do WSL 2, [que usam um kernel completo do Linux](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/).</span><span class="sxs-lookup"><span data-stu-id="5ee83-106">We've added support for WSL 2 distributions, [which use a full Linux kernel](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/).</span></span> <span data-ttu-id="5ee83-107">Este kernel do Linux é de software livre, com o código-fonte disponível no repositório [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel).</span><span class="sxs-lookup"><span data-stu-id="5ee83-107">This Linux kernel is open source, with its source code available at the [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel) repository.</span></span> <span data-ttu-id="5ee83-108">Esse kernel do Linux é entregue ao seu computador por meio de Microsoft Update e segue uma agenda de lançamento separada para o Subsistema do Windows para Linux, que é fornecido como parte da imagem do Windows.</span><span class="sxs-lookup"><span data-stu-id="5ee83-108">This Linux kernel is delivered to your machine via Microsoft Update, and follows a separate release schedule to the Windows Subsystem for Linux which is delivered as part of the Windows image.</span></span>

## <a name="5451-microsoft-standard"></a><span data-ttu-id="5ee83-109">5.4.51-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="5ee83-109">5.4.51-microsoft-standard</span></span>
<span data-ttu-id="5ee83-110">*Data de lançamento* : Pré-lançamento – 22/10/2020</span><span class="sxs-lookup"><span data-stu-id="5ee83-110">*Release Date* : Prerelease - 10/22/2020</span></span>

<span data-ttu-id="5ee83-111">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/linux-msft-5.4.51).</span><span class="sxs-lookup"><span data-stu-id="5ee83-111">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/linux-msft-5.4.51).</span></span>

* <span data-ttu-id="5ee83-112">Versão estável da 5.4.51</span><span class="sxs-lookup"><span data-stu-id="5ee83-112">Stable release of 5.4.51</span></span>

## <a name="419128-microsoft-standard"></a><span data-ttu-id="5ee83-113">4.19.128-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="5ee83-113">4.19.128-microsoft-standard</span></span>
<span data-ttu-id="5ee83-114">*Data de lançamento* : 15/09/2020</span><span class="sxs-lookup"><span data-stu-id="5ee83-114">*Release Date* : 09/15/2020</span></span>

<span data-ttu-id="5ee83-115">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="5ee83-115">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).</span></span>

* <span data-ttu-id="5ee83-116">Essa é uma versão estável de 4.19.128</span><span class="sxs-lookup"><span data-stu-id="5ee83-116">This is a stable release of 4.19.128</span></span>
* <span data-ttu-id="5ee83-117">Correção do corrompimento de memória do IOCTL do driver dxgkrnl</span><span class="sxs-lookup"><span data-stu-id="5ee83-117">Fix dxgkrnl driver IOCTL memory corruption</span></span>

## <a name="419121-microsoft-standard"></a><span data-ttu-id="5ee83-118">4.19.121-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="5ee83-118">4.19.121-microsoft-standard</span></span>
<span data-ttu-id="5ee83-119">*Data de lançamento* : pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="5ee83-119">*Release Date* : Prerelease</span></span>

<span data-ttu-id="5ee83-120">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="5ee83-120">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).</span></span>

* <span data-ttu-id="5ee83-121">Drivers: hv: vmbus: hook up dxgkrnl</span><span class="sxs-lookup"><span data-stu-id="5ee83-121">Drivers: hv: vmbus: hook up dxgkrnl</span></span>
* <span data-ttu-id="5ee83-122">Suporte adicionado para a computação GPU</span><span class="sxs-lookup"><span data-stu-id="5ee83-122">Added support for GPU Compute</span></span>

## <a name="419104-microsoft-standard"></a><span data-ttu-id="5ee83-123">4.19.104-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="5ee83-123">4.19.104-microsoft-standard</span></span>
<span data-ttu-id="5ee83-124">*Data de lançamento* : 09/06/2020</span><span class="sxs-lookup"><span data-stu-id="5ee83-124">*Release Date* : 06/09/2020</span></span> 

<span data-ttu-id="5ee83-125">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="5ee83-125">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).</span></span>

* <span data-ttu-id="5ee83-126">Atualizar configuração do WSL para 4.19.104</span><span class="sxs-lookup"><span data-stu-id="5ee83-126">Update WSL config for 4.19.104</span></span>

## <a name="41984-microsoft-standard"></a><span data-ttu-id="5ee83-127">4.19.84-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="5ee83-127">4.19.84-microsoft-standard</span></span>
<span data-ttu-id="5ee83-128">*Data de lançamento* : 12/11/2019</span><span class="sxs-lookup"><span data-stu-id="5ee83-128">*Release Date* : 11/12/2019</span></span> 

<span data-ttu-id="5ee83-129">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="5ee83-129">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).</span></span>

* <span data-ttu-id="5ee83-130">Esta é a versão estável 4.19.84</span><span class="sxs-lookup"><span data-stu-id="5ee83-130">This is the 4.19.84 stable release</span></span>

