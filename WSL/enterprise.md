---
title: WSL para Empresas
description: Recursos e instruções sobre como usar melhor o WSL em um ambiente Enterprise.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, debian, suse, windows 10, enterprise, deployment, offline, packaging, store, distribution, installation, install
ms.date: 12/14/2020
ms.topic: article
ms.assetid: 7afaeacf-435a-4e58-bff0-a9f0d75b8a51
ms.custom: seodec18
ms.openlocfilehash: 8c5e1c84767423a2d415709d184c9e96a5a3de47
ms.sourcegitcommit: 17d5ea1fe571274c224202544f61035971d6e0e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2021
ms.locfileid: "100551012"
---
# <a name="windows-subsystem-for-linux-for-enterprise"></a><span data-ttu-id="5a331-104">Subsistema do Windows para Linux for Enterprise</span><span class="sxs-lookup"><span data-stu-id="5a331-104">Windows Subsystem for Linux for Enterprise</span></span>

<span data-ttu-id="5a331-105">Como administrador ou gerente, você pode exigir que todos os desenvolvedores usem o mesmo software aprovado.</span><span class="sxs-lookup"><span data-stu-id="5a331-105">As an administrator or manager, you may require all developers to use the same approved software.</span></span> <span data-ttu-id="5a331-106">Essa consistência ajuda a criar um ambiente de trabalho bem definido.</span><span class="sxs-lookup"><span data-stu-id="5a331-106">This consistency helps to create a well-defined work environment.</span></span> <span data-ttu-id="5a331-107">O Subsistema do Windows para Linux auxilia nessa consistência permitindo que você importe e exporte imagens WSL personalizadas de um computador para o próximo.</span><span class="sxs-lookup"><span data-stu-id="5a331-107">The Windows Subsystem for Linux aids in this consistency by allowing you to import and export custom WSL images from one machine to the next.</span></span> <span data-ttu-id="5a331-108">Leia o guia abaixo para saber mais sobre como:</span><span class="sxs-lookup"><span data-stu-id="5a331-108">Read the guide below to learn more about:</span></span>

* [<span data-ttu-id="5a331-109">Como criar uma imagem do WSL personalizada</span><span class="sxs-lookup"><span data-stu-id="5a331-109">Creating a custom WSL image</span></span>](#creating-a-custom-wsl-image)
* [<span data-ttu-id="5a331-110">Como distribuir uma imagem do WSL</span><span class="sxs-lookup"><span data-stu-id="5a331-110">Distributing a WSL image</span></span>](#distributing-your-wsl-image)
* [<span data-ttu-id="5a331-111">Atualizar distribuições e pacotes do Linux e aplicar patch deles</span><span class="sxs-lookup"><span data-stu-id="5a331-111">Update and patch Linux distributions and packages</span></span>](#update-and-patch-linux-distributions-and-packages)
* [<span data-ttu-id="5a331-112">Opções de segurança e controle do Enterprise</span><span class="sxs-lookup"><span data-stu-id="5a331-112">Enterprise security and control options</span></span>](#enterprise-security-and-control-options)

## <a name="creating-a-custom-wsl-image"></a><span data-ttu-id="5a331-113">Como criar uma imagem do WSL personalizada</span><span class="sxs-lookup"><span data-stu-id="5a331-113">Creating a custom WSL image</span></span>

<span data-ttu-id="5a331-114">O que é comumente denominado "imagem" é simplesmente um instantâneo do seu software e dos componentes dele salvos em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="5a331-114">What is commonly referred to as an "image", is simply a snapshot of your software and its components saved to a file.</span></span> <span data-ttu-id="5a331-115">No caso do Subsistema do Windows para Linux, sua imagem seria composta pelo subsistema, as distribuições dele e o software e os pacotes instalados na distribuição.</span><span class="sxs-lookup"><span data-stu-id="5a331-115">In the case of the Windows Subsystem for Linux, your image would consist of the subsystem, its distributions, and whatever software and packages are installed on the distribution.</span></span>

<span data-ttu-id="5a331-116">Para começar a criar sua imagem do WSL, primeiro [instale o Subsistema do Windows para Linux](./install-win10.md).</span><span class="sxs-lookup"><span data-stu-id="5a331-116">To begin creating your WSL image, first [install the Windows Subsystem for Linux](./install-win10.md).</span></span>

<span data-ttu-id="5a331-117">Depois de instalado, use o Microsoft Store para Empresas para baixar e instalar a distribuição do Linux ideal para você.</span><span class="sxs-lookup"><span data-stu-id="5a331-117">Once installed, use The Microsoft Store for Business to download and install the Linux distribution that’s right for you.</span></span> <span data-ttu-id="5a331-118">Crie uma conta com o [Microsoft Store para Empresas](https://docs.microsoft.com/microsoft-store/sign-up-microsoft-store-for-business.)</span><span class="sxs-lookup"><span data-stu-id="5a331-118">Create an account with the [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/sign-up-microsoft-store-for-business.)</span></span>

### <a name="exporting-your-wsl-image"></a><span data-ttu-id="5a331-119">Como exportar sua imagem do WSL</span><span class="sxs-lookup"><span data-stu-id="5a331-119">Exporting your WSL image</span></span>

<span data-ttu-id="5a331-120">Exporte sua imagem do WSL personalizada executando wsl --export `<Distro> <FileName>`, que encapsulará sua imagem em um arquivo tar e a deixará pronta para distribuição para outros computadores.</span><span class="sxs-lookup"><span data-stu-id="5a331-120">Export your custom WSL image by running wsl --export `<Distro> <FileName>`, which will wrap your image in a tar file and make it ready for distribution on to other machines.</span></span>

## <a name="distributing-your-wsl-image"></a><span data-ttu-id="5a331-121">Como distribuir sua imagem do WSL</span><span class="sxs-lookup"><span data-stu-id="5a331-121">Distributing your WSL image</span></span>

<span data-ttu-id="5a331-122">Distribua a imagem do WSL de um dispositivo de compartilhamento ou de armazenamento executando wsl --import `<Distro> <InstallLocation> <FileName>`, que importará o arquivo tar especificado como uma nova distribuição.</span><span class="sxs-lookup"><span data-stu-id="5a331-122">Distribute the WSL image from a share or storage device by running wsl --import `<Distro> <InstallLocation> <FileName>`, which will import the specified tar file as a new distribution.</span></span>

## <a name="update-and-patch-linux-distributions-and-packages"></a><span data-ttu-id="5a331-123">Atualizar distribuições e pacotes do Linux e aplicar patch deles</span><span class="sxs-lookup"><span data-stu-id="5a331-123">Update and patch Linux distributions and packages</span></span>

<span data-ttu-id="5a331-124">Recomenda-se usar o gerenciador de configuração do Linux para monitorar e gerenciar o espaço do usuário do Linux.</span><span class="sxs-lookup"><span data-stu-id="5a331-124">Using Linux configuration manager tools is strongly recommended for monitoring and managing Linux user space.</span></span> <span data-ttu-id="5a331-125">Há um host de configuração do Linux no qual os gerentes podem escolher.</span><span class="sxs-lookup"><span data-stu-id="5a331-125">There are a host of Linux configuration managers to choose from.</span></span> <span data-ttu-id="5a331-126">Confira esta [postagem no blog](http://www.craigloewen.com/blog/2019/12/04/running-puppet-quickly-in-wsl2/) sobre como instalar o Puppet no WSL 2.</span><span class="sxs-lookup"><span data-stu-id="5a331-126">Check out this [blog post](http://www.craigloewen.com/blog/2019/12/04/running-puppet-quickly-in-wsl2/) on how to install Puppet in WSL 2.</span></span>

## <a name="enterprise-security-and-control-options"></a><span data-ttu-id="5a331-127">Opções de segurança e controle do Enterprise</span><span class="sxs-lookup"><span data-stu-id="5a331-127">Enterprise security and control options</span></span>

<span data-ttu-id="5a331-128">No momento, o WSL oferece mecanismos de controle limitado para modificar a experiência do usuário em um cenário Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5a331-128">Currently, WSL offers limited control mechanisms in regard to modifying the user experience in an Enterprise scenario.</span></span> <span data-ttu-id="5a331-129">Os recursos Enterprise continuam em desenvolvimento. Veja abaixo as áreas de recursos com e sem suporte.</span><span class="sxs-lookup"><span data-stu-id="5a331-129">Enterprise features continue in development however, below are the areas of supported and unsupported features.</span></span> <span data-ttu-id="5a331-130">Para solicitar um novo recurso que não consta na lista, registre um problema no [repositório GitHub](https://github.com/microsoft/WSL/issues?q=is%3Aissue+is%3Aopen+enterprise).</span><span class="sxs-lookup"><span data-stu-id="5a331-130">To request a new feature not covered in this list, file an issue in our [GitHub repo](https://github.com/microsoft/WSL/issues?q=is%3Aissue+is%3Aopen+enterprise).</span></span>

### <a name="supported"></a><span data-ttu-id="5a331-131">Com suporte</span><span class="sxs-lookup"><span data-stu-id="5a331-131">Supported</span></span>

* <span data-ttu-id="5a331-132">Compartilhar uma imagem aprovada internamente usando `wsl --import` e `wsl --export`</span><span class="sxs-lookup"><span data-stu-id="5a331-132">Sharing an approved image internally using `wsl --import` and `wsl --export`</span></span>
* <span data-ttu-id="5a331-133">Criar sua distribuição WSL para seu Enterprise usando o [repositório WSL Distro Launcher](https://github.com/microsoft/WSL-DistroLauncher)</span><span class="sxs-lookup"><span data-stu-id="5a331-133">Creating your own WSL distro for your Enterprise using the [WSL Distro Launcher repo](https://github.com/microsoft/WSL-DistroLauncher)</span></span>

<span data-ttu-id="5a331-134">Esta é uma lista de recursos para os quais nós ainda não temos suporte, mas estamos investigando.</span><span class="sxs-lookup"><span data-stu-id="5a331-134">Here's a list of features for which we don't yet have support for, but are investigating.</span></span>

### <a name="currently-unsupported"></a><span data-ttu-id="5a331-135">Não há suporte no momento</span><span class="sxs-lookup"><span data-stu-id="5a331-135">Currently unsupported</span></span>

<span data-ttu-id="5a331-136">Veja abaixo uma lista de recursos comumente solicitados que atualmente não têm suporte no WSL.</span><span class="sxs-lookup"><span data-stu-id="5a331-136">Below is a list of commonly asked features that are currently unsupported within WSL.</span></span> <span data-ttu-id="5a331-137">Essas solicitações estão em nossa lista de pendências, e estamos investigando maneiras de adicioná-las.</span><span class="sxs-lookup"><span data-stu-id="5a331-137">These requests are on our backlog and we are investigating ways to add them.</span></span> 

* <span data-ttu-id="5a331-138">Sincronizar o usuário dentro do WSL com o usuário do Windows no computador host</span><span class="sxs-lookup"><span data-stu-id="5a331-138">Synchronizing the user inside WSL with the Windows user on the host machine</span></span>
* <span data-ttu-id="5a331-139">Gerenciar atualizações e aplicar patch de pacotes e distribuições do Linux usando ferramentas do Windows</span><span class="sxs-lookup"><span data-stu-id="5a331-139">Managing updates and patching of the Linux distributions and packages using Windows tools</span></span>
* <span data-ttu-id="5a331-140">Fazer o Windows Update atualizar também o conteúdo da distribuição WSL</span><span class="sxs-lookup"><span data-stu-id="5a331-140">Having Windows update also update WSL distro contents</span></span>
* <span data-ttu-id="5a331-141">Controlar quais distribuições os usuários em seu Enterprise podem acessar</span><span class="sxs-lookup"><span data-stu-id="5a331-141">Controlling which distributions users in your Enterprise can access</span></span>
* <span data-ttu-id="5a331-142">Executar serviços obrigatórios (registrar ou monitorar) dentro do WSL</span><span class="sxs-lookup"><span data-stu-id="5a331-142">Running mandatory services (logging or monitoring) inside of WSL</span></span>
* <span data-ttu-id="5a331-143">Monitorar instâncias do Linux usando as ferramentas do gerenciador de configuração do Windows como o SCCM ou o Intune</span><span class="sxs-lookup"><span data-stu-id="5a331-143">Monitoring Linux instances using Windows configuration manager tools such as SCCM or Intune</span></span>
* <span data-ttu-id="5a331-144">Suporte do McAfee</span><span class="sxs-lookup"><span data-stu-id="5a331-144">McAfee support</span></span>
