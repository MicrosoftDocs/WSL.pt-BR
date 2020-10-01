---
title: Inicializar uma nova distribuição do Linux no WSL
description: Depois de instalar uma distribuição do Linux no WSL, conclua a inicialização seguindo estas etapas simples
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, debian, suse, windows 10
ms.date: 07/24/2018
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 11dc84d3a58b51241c7c63e8ca35eba94a12508b
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413207"
---
# <a name="initializing-a-newly-installed-distribution"></a><span data-ttu-id="a8d0f-104">Como inicializar uma distribuição recém-instalada</span><span class="sxs-lookup"><span data-stu-id="a8d0f-104">Initializing a newly installed distribution</span></span>

<span data-ttu-id="a8d0f-105">Depois que a distribuição for baixada e instalada, você precisará concluir a inicialização da nova distribuição:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-105">Once your distribution has been downloaded and installed, you'll need to complete initialization of the new distribution:</span></span>

## <a name="launch-a-distribution"></a><span data-ttu-id="a8d0f-106">Iniciar uma distribuição</span><span class="sxs-lookup"><span data-stu-id="a8d0f-106">Launch a distribution</span></span>

<span data-ttu-id="a8d0f-107">Para concluir a inicialização da distribuição recém-instalada, inicie uma nova instância.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-107">To complete the initialization of your newly installed distribution, launch a new instance.</span></span> <span data-ttu-id="a8d0f-108">Faça isso clicando no botão "Iniciar" no aplicativo da Microsoft Store ou iniciando a distribuição no menu Iniciar:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-108">You can do this by clicking the "launch" button in the Microsoft Store app, or launching the distribution from the Start menu:</span></span>

> <span data-ttu-id="a8d0f-109">Dica: fixe as distribuições usadas com mais frequência no menu Iniciar e/ou na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-109">Tip: You might want to pin your most frequently used distributions to your Start menu, and/or to your taskbar!</span></span>

![Iniciar as distribuições por meio do menu Iniciar](media/start-menu.png)

> <span data-ttu-id="a8d0f-111">No Windows Server, inicie o executável `<distribution>.exe` do inicializador da distribuição na pasta de instalação da distribuição.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-111">On Windows Server, you can launch your distribution's launcher executable `<distribution>.exe` from the distribution installation folder.</span></span>

<span data-ttu-id="a8d0f-112">Na primeira vez em que uma distribuição recém-instalada for executada, uma janela de console será aberta e você precisará aguardar alguns minutos para que a instalação seja concluída.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-112">The first time a newly installed distribution runs, a Console window will open, and you'll be asked to wait for a minute or two for the installation to complete.</span></span>

> <span data-ttu-id="a8d0f-113">Durante essa fase final da instalação, os arquivos da distribuição são descompactados e armazenados no seu computador, prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-113">During this final stage of installation, the distribution's files are de-compressed and stored on your PC, ready for use.</span></span> <span data-ttu-id="a8d0f-114">Isso pode levar cerca de um minuto ou mais, dependendo do desempenho dos dispositivos de armazenamento de seu computador.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-114">This may take around a minute or more depending on the performance of your PC's storage devices.</span></span> <span data-ttu-id="a8d0f-115">Essa fase de instalação inicial só é necessária quando uma distribuição é instalada de modo limpo; todas as futuras inicializações deverão levar menos de um segundo.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-115">This initial installation phase is only required when a distribution is clean-installed - all future launches should take less than a second.</span></span>

## <a name="setting-up-a-new-linux-user-account"></a><span data-ttu-id="a8d0f-116">Como configurar uma nova conta de usuário do Linux</span><span class="sxs-lookup"><span data-stu-id="a8d0f-116">Setting up a new Linux user account</span></span>

<span data-ttu-id="a8d0f-117">Quando a instalação for concluída, você será solicitado a criar uma nova conta de usuário (e sua senha).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-117">Once installation is complete, you will be prompted to create a new user account (and its password).</span></span>

![Desempacotamento do Ubuntu no console do Windows](media/UbuntuInstall.png)

<span data-ttu-id="a8d0f-119">Essa conta de usuário destina-se ao usuário não administrador normal como o qual você estará conectado por padrão ao iniciar uma distribuição.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-119">This user account is for the normal non-admin user that you'll be logged-in as by default when launching a distribution.</span></span>

> <span data-ttu-id="a8d0f-120">Você pode escolher qualquer nome de usuário e senha que desejar – eles não têm nenhuma influência sobre seu nome de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-120">You can choose any username and password you wish - they have no bearing on your Windows username.</span></span>

<span data-ttu-id="a8d0f-121">Quando você abrir uma nova instância da distribuição, não precisará inserir sua senha, mas **se elevar um processo usando o `sudo`, precisará inseri-la**. Portanto, escolha uma senha fácil de ser lembrada.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-121">When you open a new distribution instance, you won't be prompted for your password, but **if you elevate a process using `sudo`, you will need to enter your password**, so make sure you choose a password you can easily remember!</span></span> <span data-ttu-id="a8d0f-122">Consulte a página [Suporte ao usuário](user-support.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-122">See the [User Support](user-support.md) page for more info.</span></span>

## <a name="update--upgrade-your-distributions-packages"></a><span data-ttu-id="a8d0f-123">Atualizar pacotes da distribuição e fazer upgrade deles</span><span class="sxs-lookup"><span data-stu-id="a8d0f-123">Update & upgrade your distribution's packages</span></span>

<span data-ttu-id="a8d0f-124">A maioria das distribuições é fornecida com um catálogo de pacotes vazio/mínimo.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-124">Most distributions ship with an empty/minimal package catalog.</span></span> <span data-ttu-id="a8d0f-125">Recomendamos expressamente que você atualize com regularidade o catálogo de pacotes e faça upgrade dos pacotes instalados usando seu gerenciador de pacotes preferencial da distribuição.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-125">We strongly recommend regularly updating your package catalog, and upgrading your installed packages using your distribution's preferred package manager.</span></span> <span data-ttu-id="a8d0f-126">No Debian/Ubuntu, você usa apt:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-126">On Debian/Ubuntu, you use apt:</span></span>

```bash
sudo apt update && sudo apt upgrade
```

> <span data-ttu-id="a8d0f-127">O Windows não atualiza as distribuições do Linux nem faz upgrade delas automaticamente: Essa é uma tarefa que os usuários do Linux preferem controlar por conta própria.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-127">Windows does not automatically update or upgrade your Linux distribution(s): This is a task that the Linux users prefer to control themselves.</span></span>

<span data-ttu-id="a8d0f-128">Concluído!</span><span class="sxs-lookup"><span data-stu-id="a8d0f-128">You're done!</span></span> <span data-ttu-id="a8d0f-129">Aproveite sua nova distribuição do Linux no WSL!</span><span class="sxs-lookup"><span data-stu-id="a8d0f-129">Enjoy using your new Linux distribution on WSL!</span></span> <span data-ttu-id="a8d0f-130">Para saber mais sobre o WSL, examine os outros [documentos do WSL](./index.md) ou a [página de recursos de aprendizagem do WSL](https://aka.ms/learnwsl).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-130">To learn more about WSL, review the other [WSL docs](./index.md), or the [WSL learning resources page](https://aka.ms/learnwsl).</span></span>

![Aproveite o uso do Linux no WSL](media/linux-on-wsl.png)

## <a name="troubleshooting"></a><span data-ttu-id="a8d0f-132">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="a8d0f-132">Troubleshooting</span></span>

<span data-ttu-id="a8d0f-133">Veja abaixo erros relacionados e correções sugeridas.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-133">Below are related errors and suggested fixes.</span></span> <span data-ttu-id="a8d0f-134">Consulte a [página de solução de problemas do WSL](troubleshooting.md) para ver outros erros comuns e suas soluções.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-134">Refer to the [WSL troubleshooting page](troubleshooting.md) for other common errors and their solutions.</span></span>

> <span data-ttu-id="a8d0f-135">**Falha na instalação com o erro 0x8007007e** Esse erro ocorre quando o sistema não é compatível com o Linux na loja.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-135">**Installation failed with error 0x8007007e** This error occurs when your system doesn't support Linux from the store.</span></span>  <span data-ttu-id="a8d0f-136">Certifique-se de que:</span><span class="sxs-lookup"><span data-stu-id="a8d0f-136">Make sure that:</span></span>
> * <span data-ttu-id="a8d0f-137">Você está executando o Windows Build 16215 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-137">You're running Windows build 16215 or later.</span></span> <span data-ttu-id="a8d0f-138">[Verifique seu build](troubleshooting.md#check-your-build-number).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-138">[Check your build](troubleshooting.md#check-your-build-number).</span></span>
> * <span data-ttu-id="a8d0f-139">O componente opcional do Subsistema Windows para Linux está habilitado e o computador foi reiniciado.</span><span class="sxs-lookup"><span data-stu-id="a8d0f-139">The Windows Subsystem for Linux optional component is enabled and the computer has restarted.</span></span>  <span data-ttu-id="a8d0f-140">[Verifique se o WSL está habilitado](troubleshooting.md#confirm-wsl-is-enabled).</span><span class="sxs-lookup"><span data-stu-id="a8d0f-140">[Make sure WSL is enabled](troubleshooting.md#confirm-wsl-is-enabled).</span></span>