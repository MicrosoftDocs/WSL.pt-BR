---
title: Notas sobre a versão do kernel do Subsistema do Windows para Linux
description: Notas sobre a versão do subsistema Windows para Linux.  Atualizadas mensalmente.
keywords: notas sobre a versão, wsl, windows, subsistema do windows para linux, windowssubsystem, ubuntu, kernel
ms.date: 06/09/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: ffec37d179005eb7015a8f9af8de0ac185710bec
ms.sourcegitcommit: fb79750bd71d6ebaed5203b3de71ba85a67227b1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88866113"
---
# <a name="release-notes-for-windows-subsystem-for-linux-kernel"></a><span data-ttu-id="1a4c1-105">Notas sobre a versão do kernel do Subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="1a4c1-105">Release Notes for Windows Subsystem for Linux kernel</span></span>

<span data-ttu-id="1a4c1-106">Adicionamos suporte para distribuições do WSL 2, [que usam um kernel completo do Linux](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/).</span><span class="sxs-lookup"><span data-stu-id="1a4c1-106">We've added support for WSL 2 distributions, [which use a full Linux kernel](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/).</span></span> <span data-ttu-id="1a4c1-107">Este kernel do Linux é de software livre, com o código-fonte disponível no repositório [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel).</span><span class="sxs-lookup"><span data-stu-id="1a4c1-107">This Linux kernel is open source, with its source code available at the [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel) repository.</span></span> <span data-ttu-id="1a4c1-108">Esse kernel do Linux é entregue ao seu computador por meio de Microsoft Update e segue uma agenda de lançamento separada para o Subsistema do Windows para Linux, que é fornecido como parte da imagem do Windows.</span><span class="sxs-lookup"><span data-stu-id="1a4c1-108">This Linux kernel is delivered to your machine via Microsoft Update, and follows a separate release schedule to the Windows Subsystem for Linux which is delivered as part of the Windows image.</span></span>

## <a name="419128-microsoft-standard"></a><span data-ttu-id="1a4c1-109">4.19.128-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="1a4c1-109">4.19.128-microsoft-standard</span></span>
<span data-ttu-id="1a4c1-110">*Data de lançamento*: pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="1a4c1-110">*Release Date*: Prerelease</span></span>

<span data-ttu-id="1a4c1-111">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="1a4c1-111">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).</span></span>

* <span data-ttu-id="1a4c1-112">Essa é uma versão estável de 4.19.128</span><span class="sxs-lookup"><span data-stu-id="1a4c1-112">This is a stable release of 4.19.128</span></span>
* <span data-ttu-id="1a4c1-113">Correção do corrompimento de memória do IOCTL do driver dxgkrnl</span><span class="sxs-lookup"><span data-stu-id="1a4c1-113">Fix dxgkrnl driver IOCTL memory corruption</span></span>

## <a name="419121-microsoft-standard"></a><span data-ttu-id="1a4c1-114">4.19.121-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="1a4c1-114">4.19.121-microsoft-standard</span></span>
<span data-ttu-id="1a4c1-115">*Data de lançamento*: pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="1a4c1-115">*Release Date*: Prerelease</span></span>

<span data-ttu-id="1a4c1-116">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="1a4c1-116">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).</span></span>

* <span data-ttu-id="1a4c1-117">Drivers: hv: vmbus: hook up dxgkrnl</span><span class="sxs-lookup"><span data-stu-id="1a4c1-117">Drivers: hv: vmbus: hook up dxgkrnl</span></span>
* <span data-ttu-id="1a4c1-118">Suporte adicionado para a computação GPU</span><span class="sxs-lookup"><span data-stu-id="1a4c1-118">Added support for GPU Compute</span></span>

## <a name="419104-microsoft-standard"></a><span data-ttu-id="1a4c1-119">4.19.104-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="1a4c1-119">4.19.104-microsoft-standard</span></span>
<span data-ttu-id="1a4c1-120">*Data de lançamento*: 09/06/2020</span><span class="sxs-lookup"><span data-stu-id="1a4c1-120">*Release Date*: 06/09/2020</span></span> 

<span data-ttu-id="1a4c1-121">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="1a4c1-121">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).</span></span>

* <span data-ttu-id="1a4c1-122">Atualizar configuração do WSL para 4.19.104</span><span class="sxs-lookup"><span data-stu-id="1a4c1-122">Update WSL config for 4.19.104</span></span>

## <a name="41984-microsoft-standard"></a><span data-ttu-id="1a4c1-123">4.19.84-microsoft-standard</span><span class="sxs-lookup"><span data-stu-id="1a4c1-123">4.19.84-microsoft-standard</span></span>
<span data-ttu-id="1a4c1-124">*Data de lançamento*: 12/11/2019</span><span class="sxs-lookup"><span data-stu-id="1a4c1-124">*Release Date*: 11/12/2019</span></span> 

<span data-ttu-id="1a4c1-125">[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).</span><span class="sxs-lookup"><span data-stu-id="1a4c1-125">[Official Github release link](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).</span></span>

* <span data-ttu-id="1a4c1-126">Esta é a versão estável 4.19.84</span><span class="sxs-lookup"><span data-stu-id="1a4c1-126">This is the 4.19.84 stable release</span></span>

