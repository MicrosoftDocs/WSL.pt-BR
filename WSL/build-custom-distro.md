---
title: Criar um distribuição Linux personalizado para o WSL
description: Saiba como criar uma distribuição personalizada do Linux para o subsistema do Windows para Linux.
keywords: BashOnWindows, Bash, WSL, Windows, subsistema do Windows, distribuição, personalizado
ms.date: 09/15/2020
ms.topic: article
ms.openlocfilehash: 2882cccac6c34cd52529dbf7e42c8d35907d8241
ms.sourcegitcommit: 69fc9d3ca22cf3f07622db4cdf80c8ec751fe620
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90818698"
---
# <a name="creating-a-custom-linux-distribution-for-wsl"></a><span data-ttu-id="be94a-104">Criando uma distribuição personalizada do Linux para WSL</span><span class="sxs-lookup"><span data-stu-id="be94a-104">Creating a Custom Linux Distribution for WSL</span></span>

<span data-ttu-id="be94a-105">Use nosso exemplo de WSL de software livre para criar pacotes WSL distribuição para o Microsoft Store e/ou para criar pacotes personalizados do Linux distribuição para Sideload.</span><span class="sxs-lookup"><span data-stu-id="be94a-105">Use our open source WSL sample to build WSL distro packages for the Microsoft Store and/or to create custom Linux distro packages for sideloading.</span></span> <span data-ttu-id="be94a-106">Você pode encontrar o [repositório do iniciador distribuição](https://github.com/Microsoft/WSL-DistroLauncher) no github.</span><span class="sxs-lookup"><span data-stu-id="be94a-106">You can find the [distro launcher repo](https://github.com/Microsoft/WSL-DistroLauncher) on GitHub.</span></span>

<span data-ttu-id="be94a-107">Este projeto permite:</span><span class="sxs-lookup"><span data-stu-id="be94a-107">This project enables:</span></span>

- <span data-ttu-id="be94a-108">Os mantenedores de distribuição do Linux para empacotar e enviar uma distribuição do Linux como um Appx executado no WSL</span><span class="sxs-lookup"><span data-stu-id="be94a-108">Linux distribution maintainers to package and submit a Linux distribution as an appx that runs on WSL</span></span>
- <span data-ttu-id="be94a-109">Desenvolvedores para criar distribuições personalizadas do Linux que podem ser sideloaddas em sua máquina de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="be94a-109">Developers to create custom Linux distributions that can be sideloaded onto their dev machine</span></span>

## <a name="background"></a><span data-ttu-id="be94a-110">Tela de fundo</span><span class="sxs-lookup"><span data-stu-id="be94a-110">Background</span></span>

<span data-ttu-id="be94a-111">Distribuímos o Linux distribuições para WSL como aplicativos UWP por meio do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="be94a-111">We distribute Linux distros for WSL as UWP applications through the Microsoft Store.</span></span> <span data-ttu-id="be94a-112">Você pode instalar os aplicativos que serão executados em WSL-o subsistema que reside no kernel do Windows.</span><span class="sxs-lookup"><span data-stu-id="be94a-112">You can install those applications that will then run on WSL - the subsystem that sits in the Windows kernel.</span></span> <span data-ttu-id="be94a-113">Esse mecanismo de entrega tem muitos benefícios como discutidos em uma [postagem no blog anterior](https://blogs.msdn.microsoft.com/commandline/2017/07/10/ubuntu-now-available-from-the-windows-store/).</span><span class="sxs-lookup"><span data-stu-id="be94a-113">This delivery mechanism has many benefits as discussed in an [earlier blog post](https://blogs.msdn.microsoft.com/commandline/2017/07/10/ubuntu-now-available-from-the-windows-store/).</span></span>

## <a name="sideloading-a-custom-linux-distro-package"></a><span data-ttu-id="be94a-114">Sideload de um pacote personalizado de distribuição do Linux</span><span class="sxs-lookup"><span data-stu-id="be94a-114">Sideloading a Custom Linux Distro Package</span></span>

<span data-ttu-id="be94a-115">Você pode criar um pacote personalizado do Linux distribuição como um aplicativo para Sideload em seu computador pessoal.</span><span class="sxs-lookup"><span data-stu-id="be94a-115">You can create a custom Linux distro package as an application to sideload on your personal machine.</span></span> <span data-ttu-id="be94a-116">Observe que seu pacote personalizado não seria distribuído por meio do Microsoft Store, a menos que você envie como um mantenedor de distribuição.</span><span class="sxs-lookup"><span data-stu-id="be94a-116">Please note that your custom package would not be distributed through the Microsoft Store unless you submit as a distribution maintainer.</span></span>
<span data-ttu-id="be94a-117">Para configurar seu computador para aplicativos Sideload, você precisará habilitá-lo nas configurações do sistema em "para desenvolvedores".</span><span class="sxs-lookup"><span data-stu-id="be94a-117">To set up your machine to sideload apps, you will need to enable this in the system settings under “For Developers”.</span></span>  <span data-ttu-id="be94a-118">Certifique-se de ter o modo de desenvolvedor ou aplicativos Sideload selecionados</span><span class="sxs-lookup"><span data-stu-id="be94a-118">Be sure to either have developer mode, or sideload apps selected</span></span>

## <a name="for-linux-distro-maintainers"></a><span data-ttu-id="be94a-119">Para os mantenedores do Linux distribuição</span><span class="sxs-lookup"><span data-stu-id="be94a-119">For Linux Distro Maintainers</span></span>

<span data-ttu-id="be94a-120">Para enviar para a loja, você precisará trabalhar conosco para receber aprovação de publicação.</span><span class="sxs-lookup"><span data-stu-id="be94a-120">To submit to the Store, you will need to work with us to receive publishing approval.</span></span> <span data-ttu-id="be94a-121">Se você for um proprietário de distribuição do Linux interessado em adicionar sua distribuição ao Microsoft Store, entre em contato com wslpartners@microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="be94a-121">If you are a Linux distribution owner interested in adding your distribution to the Microsoft Store, please contact wslpartners@microsoft.com.</span></span>

## <a name="getting-started"></a><span data-ttu-id="be94a-122">Introdução</span><span class="sxs-lookup"><span data-stu-id="be94a-122">Getting Started</span></span>

<span data-ttu-id="be94a-123">Siga as instruções no [repositório GitHub do iniciador do distribuição](https://github.com/Microsoft/WSL-DistroLauncher) para criar um pacote personalizado do distribuição do Linux.</span><span class="sxs-lookup"><span data-stu-id="be94a-123">Follow the instructions on the [Distro Launcher GitHub repo](https://github.com/Microsoft/WSL-DistroLauncher) to create a custom Linux distro package.</span></span>

## <a name="team-blogs"></a><span data-ttu-id="be94a-124">Blogs da equipe</span><span class="sxs-lookup"><span data-stu-id="be94a-124">Team Blogs</span></span>

-  [<span data-ttu-id="be94a-125">Abrir o fornecimento de um exemplo de WSL para os mantenedores de distribuição do Linux e distribuição personalizada do Linux de Sideload</span><span class="sxs-lookup"><span data-stu-id="be94a-125">Open Sourcing a WSL Sample for Linux Distribution Maintainers and Sideloading Custom Linux Distributions</span></span>](https://blogs.msdn.microsoft.com/commandline/2018/03/26/wsl-distro-launcher/)
- [<span data-ttu-id="be94a-126">Blog de linha de comando</span><span class="sxs-lookup"><span data-stu-id="be94a-126">Command-Line blog</span></span>](https://blogs.msdn.microsoft.com/commandline/)

## <a name="provide-feedback"></a><span data-ttu-id="be94a-127">Forneça comentários</span><span class="sxs-lookup"><span data-stu-id="be94a-127">Provide Feedback</span></span>

- [<span data-ttu-id="be94a-128">Repositório GitHub do iniciador distribuição</span><span class="sxs-lookup"><span data-stu-id="be94a-128">Distro Launcher GitHub repo</span></span>](https://github.com/Microsoft/WSL-DistroLauncher)
- [<span data-ttu-id="be94a-129">Rastreador de problemas do GitHub para WSL</span><span class="sxs-lookup"><span data-stu-id="be94a-129">GitHub issue tracker for WSL</span></span>](https://github.com/Microsoft/BashOnWindows/issues)
