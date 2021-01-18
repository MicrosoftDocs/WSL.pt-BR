---
title: Notas sobre a versão do kernel do Subsistema do Windows para Linux
description: Notas sobre a versão do subsistema Windows para Linux.  Atualizadas mensalmente.
keywords: notas sobre a versão, wsl, windows, subsistema do windows para linux, windowssubsystem, ubuntu, kernel
ms.date: 06/09/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 07488d61ad1c01f85c1d78789274aa3afbc9e1d8
ms.sourcegitcommit: e2d586925b314ce4517773b9c78736450a9f75d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97977101"
---
# <a name="release-notes-for-windows-subsystem-for-linux-kernel"></a><span data-ttu-id="86fb9-105">Notas sobre a versão do kernel do Subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="86fb9-105">Release Notes for Windows Subsystem for Linux kernel</span></span>

<span data-ttu-id="86fb9-106">Adicionamos suporte para distribuições do WSL 2, [que usam um kernel completo do Linux](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/).</span><span class="sxs-lookup"><span data-stu-id="86fb9-106">We've added support for WSL 2 distributions, [which use a full Linux kernel](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/).</span></span> <span data-ttu-id="86fb9-107">Este kernel do Linux é de software livre, com o código-fonte disponível no repositório [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel).</span><span class="sxs-lookup"><span data-stu-id="86fb9-107">This Linux kernel is open source, with its source code available at the [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel) repository.</span></span> <span data-ttu-id="86fb9-108">Esse kernel do Linux é entregue ao seu computador por meio de Microsoft Update e segue uma agenda de lançamento separada para o Subsistema do Windows para Linux, que é fornecido como parte da imagem do Windows.</span><span class="sxs-lookup"><span data-stu-id="86fb9-108">This Linux kernel is delivered to your machine via Microsoft Update, and follows a separate release schedule to the Windows Subsystem for Linux which is delivered as part of the Windows image.</span></span>

## <a name="5472"></a><span data-ttu-id="86fb9-109">5.4.72</span><span class="sxs-lookup"><span data-stu-id="86fb9-109">5.4.72</span></span>
<span data-ttu-id="86fb9-110">*Data de lançamento*: Pré-lançamento – 10/11/2020</span><span class="sxs-lookup"><span data-stu-id="86fb9-110">*Release Date*: Prerelease - 11/10/2020</span></span>

[<span data-ttu-id="86fb9-111">Link da versão oficial do GitHub</span><span class="sxs-lookup"><span data-stu-id="86fb9-111">Official Github release link</span></span>](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/linux-msft-5.4.72)

* <span data-ttu-id="86fb9-112">Correção de configuração para 5.4.72</span><span class="sxs-lookup"><span data-stu-id="86fb9-112">Fix config for 5.4.72</span></span>

## <a name="5451-microsoft-standard"></a><span data-ttu-id="86fb9-113">5.4.51-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="86fb9-113">5.4.51-microsoft-standard</span></span>
<span data-ttu-id="86fb9-114">*Data de lançamento*: Pré-lançamento – 22/10/2020</span><span class="sxs-lookup"><span data-stu-id="86fb9-114">*Release Date*: Prerelease - 10/22/2020</span></span>

<span data-ttu-id="86fb9-115">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/linux-msft-5.4.51).</span><span class="sxs-lookup"><span data-stu-id="86fb9-115">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/linux-msft-5.4.51).</span></span>

* <span data-ttu-id="86fb9-116">Versão estável da 5.4.51</span><span class="sxs-lookup"><span data-stu-id="86fb9-116">Stable release of 5.4.51</span></span>

## <a name="419128-microsoft-standard"></a><span data-ttu-id="86fb9-117">4.19.128-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="86fb9-117">4.19.128-microsoft-standard</span></span>
<span data-ttu-id="86fb9-118">*Data de lançamento*: 15/09/2020</span><span class="sxs-lookup"><span data-stu-id="86fb9-118">*Release Date*: 09/15/2020</span></span>

<span data-ttu-id="86fb9-119">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="86fb9-119">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).</span></span>

* <span data-ttu-id="86fb9-120">Essa é uma versão estável de 4.19.128</span><span class="sxs-lookup"><span data-stu-id="86fb9-120">This is a stable release of 4.19.128</span></span>
* <span data-ttu-id="86fb9-121">Correção do corrompimento de memória do IOCTL do driver dxgkrnl</span><span class="sxs-lookup"><span data-stu-id="86fb9-121">Fix dxgkrnl driver IOCTL memory corruption</span></span>

## <a name="419121-microsoft-standard"></a><span data-ttu-id="86fb9-122">4.19.121-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="86fb9-122">4.19.121-microsoft-standard</span></span>
<span data-ttu-id="86fb9-123">*Data de lançamento*: pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="86fb9-123">*Release Date*: Prerelease</span></span>

<span data-ttu-id="86fb9-124">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="86fb9-124">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).</span></span>

* <span data-ttu-id="86fb9-125">Drivers: hv: vmbus: hook up dxgkrnl</span><span class="sxs-lookup"><span data-stu-id="86fb9-125">Drivers: hv: vmbus: hook up dxgkrnl</span></span>
* <span data-ttu-id="86fb9-126">Suporte adicionado para a computação GPU</span><span class="sxs-lookup"><span data-stu-id="86fb9-126">Added support for GPU Compute</span></span>

## <a name="419104-microsoft-standard"></a><span data-ttu-id="86fb9-127">4.19.104-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="86fb9-127">4.19.104-microsoft-standard</span></span>
<span data-ttu-id="86fb9-128">*Data de lançamento*: 09/06/2020</span><span class="sxs-lookup"><span data-stu-id="86fb9-128">*Release Date*: 06/09/2020</span></span> 

<span data-ttu-id="86fb9-129">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="86fb9-129">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).</span></span>

* <span data-ttu-id="86fb9-130">Atualizar configuração do WSL para 4.19.104</span><span class="sxs-lookup"><span data-stu-id="86fb9-130">Update WSL config for 4.19.104</span></span>

## <a name="41984-microsoft-standard"></a><span data-ttu-id="86fb9-131">4.19.84-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="86fb9-131">4.19.84-microsoft-standard</span></span>
<span data-ttu-id="86fb9-132">*Data de lançamento*: 12/11/2019</span><span class="sxs-lookup"><span data-stu-id="86fb9-132">*Release Date*: 11/12/2019</span></span> 

<span data-ttu-id="86fb9-133">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="86fb9-133">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).</span></span>

* <span data-ttu-id="86fb9-134">Esta é a versão estável 4.19.84</span><span class="sxs-lookup"><span data-stu-id="86fb9-134">This is the 4.19.84 stable release</span></span>

