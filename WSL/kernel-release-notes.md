---
title: Notas sobre a versão do kernel do Subsistema do Windows para Linux
description: Notas sobre a versão do subsistema Windows para Linux.  Atualizadas mensalmente.
keywords: notas sobre a versão, wsl, windows, subsistema do windows para linux, windowssubsystem, ubuntu, kernel
ms.date: 06/09/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 977b64b9b963d28c0291166cf2bad799bad4a6fe
ms.sourcegitcommit: c0478193f16efd4f8221016301ef7a1fd67713e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98671948"
---
# <a name="release-notes-for-windows-subsystem-for-linux-kernel"></a><span data-ttu-id="e3d25-105">Notas sobre a versão do kernel do Subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="e3d25-105">Release Notes for Windows Subsystem for Linux kernel</span></span>

<span data-ttu-id="e3d25-106">Adicionamos suporte para distribuições do WSL 2, [que usam um kernel completo do Linux](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/).</span><span class="sxs-lookup"><span data-stu-id="e3d25-106">We've added support for WSL 2 distributions, [which use a full Linux kernel](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/).</span></span> <span data-ttu-id="e3d25-107">Este kernel do Linux é de software livre, com o código-fonte disponível no repositório [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel).</span><span class="sxs-lookup"><span data-stu-id="e3d25-107">This Linux kernel is open source, with its source code available at the [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel) repository.</span></span> <span data-ttu-id="e3d25-108">Esse kernel do Linux é entregue ao seu computador por meio de Microsoft Update e segue uma agenda de lançamento separada para o Subsistema do Windows para Linux, que é fornecido como parte da imagem do Windows.</span><span class="sxs-lookup"><span data-stu-id="e3d25-108">This Linux kernel is delivered to your machine via Microsoft Update, and follows a separate release schedule to the Windows Subsystem for Linux which is delivered as part of the Windows image.</span></span>

## <a name="5472"></a><span data-ttu-id="e3d25-109">5.4.72</span><span class="sxs-lookup"><span data-stu-id="e3d25-109">5.4.72</span></span>
<span data-ttu-id="e3d25-110">*Data de lançamento*: 21/01/2021</span><span class="sxs-lookup"><span data-stu-id="e3d25-110">*Release Date*: 2021/01/21</span></span>

[<span data-ttu-id="e3d25-111">Link da versão oficial do GitHub</span><span class="sxs-lookup"><span data-stu-id="e3d25-111">Official Github release link</span></span>](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/linux-msft-5.4.72)

* <span data-ttu-id="e3d25-112">Correção de configuração para 5.4.72</span><span class="sxs-lookup"><span data-stu-id="e3d25-112">Fix config for 5.4.72</span></span>

## <a name="5451-microsoft-standard"></a><span data-ttu-id="e3d25-113">5.4.51-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="e3d25-113">5.4.51-microsoft-standard</span></span>
<span data-ttu-id="e3d25-114">*Data de lançamento*: Pré-lançamento – 22/10/2020</span><span class="sxs-lookup"><span data-stu-id="e3d25-114">*Release Date*: Prerelease - 2020/10/22</span></span>

<span data-ttu-id="e3d25-115">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/linux-msft-5.4.51).</span><span class="sxs-lookup"><span data-stu-id="e3d25-115">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/linux-msft-5.4.51).</span></span>

* <span data-ttu-id="e3d25-116">Versão estável da 5.4.51</span><span class="sxs-lookup"><span data-stu-id="e3d25-116">Stable release of 5.4.51</span></span>

## <a name="419128-microsoft-standard"></a><span data-ttu-id="e3d25-117">4.19.128-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="e3d25-117">4.19.128-microsoft-standard</span></span>
<span data-ttu-id="e3d25-118">*Data de lançamento*: 15/09/2020</span><span class="sxs-lookup"><span data-stu-id="e3d25-118">*Release Date*: 2020/09/15</span></span>

<span data-ttu-id="e3d25-119">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="e3d25-119">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).</span></span>

* <span data-ttu-id="e3d25-120">Essa é uma versão estável de 4.19.128</span><span class="sxs-lookup"><span data-stu-id="e3d25-120">This is a stable release of 4.19.128</span></span>
* <span data-ttu-id="e3d25-121">Correção do corrompimento de memória do IOCTL do driver dxgkrnl</span><span class="sxs-lookup"><span data-stu-id="e3d25-121">Fix dxgkrnl driver IOCTL memory corruption</span></span>

## <a name="419121-microsoft-standard"></a><span data-ttu-id="e3d25-122">4.19.121-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="e3d25-122">4.19.121-microsoft-standard</span></span>
<span data-ttu-id="e3d25-123">*Data de lançamento*: pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="e3d25-123">*Release Date*: Prerelease</span></span>

<span data-ttu-id="e3d25-124">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="e3d25-124">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).</span></span>

* <span data-ttu-id="e3d25-125">Drivers: hv: vmbus: hook up dxgkrnl</span><span class="sxs-lookup"><span data-stu-id="e3d25-125">Drivers: hv: vmbus: hook up dxgkrnl</span></span>
* <span data-ttu-id="e3d25-126">Suporte adicionado para a computação GPU</span><span class="sxs-lookup"><span data-stu-id="e3d25-126">Added support for GPU Compute</span></span>

## <a name="419104-microsoft-standard"></a><span data-ttu-id="e3d25-127">4.19.104-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="e3d25-127">4.19.104-microsoft-standard</span></span>
<span data-ttu-id="e3d25-128">*Data de lançamento*: 09/06/2020</span><span class="sxs-lookup"><span data-stu-id="e3d25-128">*Release Date*: 2020/06/09</span></span>

<span data-ttu-id="e3d25-129">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="e3d25-129">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).</span></span>

* <span data-ttu-id="e3d25-130">Atualizar configuração do WSL para 4.19.104</span><span class="sxs-lookup"><span data-stu-id="e3d25-130">Update WSL config for 4.19.104</span></span>

## <a name="41984-microsoft-standard"></a><span data-ttu-id="e3d25-131">4.19.84-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="e3d25-131">4.19.84-microsoft-standard</span></span>
<span data-ttu-id="e3d25-132">*Data de lançamento*: 11/12/2019</span><span class="sxs-lookup"><span data-stu-id="e3d25-132">*Release Date*: 2019/12/11</span></span>

<span data-ttu-id="e3d25-133">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="e3d25-133">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).</span></span>

* <span data-ttu-id="e3d25-134">Esta é a versão estável 4.19.84</span><span class="sxs-lookup"><span data-stu-id="e3d25-134">This is the 4.19.84 stable release</span></span>

