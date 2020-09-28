---
title: Criar e atualizar contas de usuário para distribuições do Linux
description: Referência para contas de usuário e gerenciamento de permissões com o Subsistema Windows para Linux.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, user accounts
ms.date: 05/12/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 7f1ad56a6f4261ad0455ee93bdeb5e31d0ed10d1
ms.sourcegitcommit: 69fc9d3ca22cf3f07622db4cdf80c8ec751fe620
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90818718"
---
# <a name="create-a-user-account-and-password-for-your-new-linux-distribution"></a><span data-ttu-id="0034b-104">Criar uma conta de usuário e uma senha para sua nova distribuição do Linux</span><span class="sxs-lookup"><span data-stu-id="0034b-104">Create a user account and password for your new Linux distribution</span></span>

<span data-ttu-id="0034b-105">Depois que você [habilitar o WSL e instalar uma distribuição do Linux da Microsoft Store](./install-win10.md), a primeira etapa a ser realizada ao abrir a distribuição do Linux recém-instalada será a criação de uma conta, incluindo um **Nome de Usuário** e **Senha**.</span><span class="sxs-lookup"><span data-stu-id="0034b-105">Once you have [enabled WSL and installed a Linux distribution from the Microsoft Store](./install-win10.md), the first step you will be asked to complete when opening your newly installed Linux distribution is to create an account, including a **User Name** and **Password**.</span></span>

- <span data-ttu-id="0034b-106">O **Nome de Usuário** e a **Senha** são específicos de cada distribuição do Linux separada que você instala e não têm nenhuma influência sobre o seu nome de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="0034b-106">This **User Name** and **Password** is specific to each separate Linux distribution that you install and has no bearing on your Windows user name.</span></span>

- <span data-ttu-id="0034b-107">Depois de criar um **Nome de Usuário** e uma **Senha**, a conta será o usuário padrão para a distribuição e será conectada automaticamente ao iniciar.</span><span class="sxs-lookup"><span data-stu-id="0034b-107">Once you create a **User Name** and **Password**, the account will be your default user for the distribution and automatically sign-in on launch.</span></span>

- <span data-ttu-id="0034b-108">Essa conta será considerada o administrador do Linux, com a capacidade de executar comandos administrativos `sudo` (Super User Do).</span><span class="sxs-lookup"><span data-stu-id="0034b-108">This account will be considered the Linux administrator, with the ability to run `sudo` (Super User Do) administrative commands.</span></span>

- <span data-ttu-id="0034b-109">Cada distribuição do Linux em execução no Subsistema Windows para Linux tem suas próprias contas de usuário e senhas do Linux.</span><span class="sxs-lookup"><span data-stu-id="0034b-109">Each Linux distribution running on the Windows Subsystem for Linux has its own Linux user accounts and passwords.</span></span>  <span data-ttu-id="0034b-110">Você precisará configurar uma conta de usuário do Linux sempre que adicionar uma distribuição, reinstalação ou redefinição.</span><span class="sxs-lookup"><span data-stu-id="0034b-110">You will have to configure a Linux user account every time you add a distribution, reinstall, or reset.</span></span>

![Desempacotamento do Ubuntu no console do Windows](media/UbuntuInstall.png)

## <a name="update-and-upgrade-packages"></a><span data-ttu-id="0034b-112">Pacotes de atualização e upgrade</span><span class="sxs-lookup"><span data-stu-id="0034b-112">Update and upgrade packages</span></span>

<span data-ttu-id="0034b-113">A maioria das distribuições é fornecida com um catálogo de pacotes vazio ou mínimo.</span><span class="sxs-lookup"><span data-stu-id="0034b-113">Most distributions ship with an empty or minimal package catalog.</span></span> <span data-ttu-id="0034b-114">É altamente recomendável atualizar regularmente seu catálogo de pacotes e fazer upgrade de seus pacotes instalados usando o gerenciador de pacotes preferencial da distribuição.</span><span class="sxs-lookup"><span data-stu-id="0034b-114">We strongly recommend regularly updating your package catalog and upgrading your installed packages using your distribution's preferred package manager.</span></span> <span data-ttu-id="0034b-115">No Debian/Ubuntu, use apt:</span><span class="sxs-lookup"><span data-stu-id="0034b-115">For Debian/Ubuntu, use apt:</span></span>

```bash
sudo apt update && sudo apt upgrade
```

<span data-ttu-id="0034b-116">O Windows não atualiza ou faz upgrade automaticamente de suas distribuições do Linux.</span><span class="sxs-lookup"><span data-stu-id="0034b-116">Windows does not automatically update or upgrade your Linux distribution(s).</span></span> <span data-ttu-id="0034b-117">Essa é uma tarefa que a maioria dos usuários do Linux prefere controlar por conta própria.</span><span class="sxs-lookup"><span data-stu-id="0034b-117">This is a task that most Linux users prefer to control themselves.</span></span>

## <a name="reset-your-linux-password"></a><span data-ttu-id="0034b-118">Redefinir sua senha do Linux</span><span class="sxs-lookup"><span data-stu-id="0034b-118">Reset your Linux password</span></span>

<span data-ttu-id="0034b-119">Para alterar sua senha, abra a distribuição do Linux (Ubuntu, por exemplo) e insira o comando: `passwd`</span><span class="sxs-lookup"><span data-stu-id="0034b-119">To change your password, open your Linux distribution (Ubuntu for example) and enter the command: `passwd`</span></span>

<span data-ttu-id="0034b-120">Você será solicitado a inserir a senha atual, inserir a nova senha e, em seguida, confirmar a nova senha.</span><span class="sxs-lookup"><span data-stu-id="0034b-120">You will be asked to enter your current password, then asked to enter your new password, and then to confirm your new password.</span></span>

## <a name="forgot-your-password"></a><span data-ttu-id="0034b-121">Esqueceu sua senha</span><span class="sxs-lookup"><span data-stu-id="0034b-121">Forgot your password</span></span>

<span data-ttu-id="0034b-122">Se você esqueceu a senha da sua distribuição do Linux:</span><span class="sxs-lookup"><span data-stu-id="0034b-122">If you forgot the password for your Linux distribution:</span></span>

1. <span data-ttu-id="0034b-123">Abra o PowerShell e insira a raiz da distribuição do WSL padrão usando o comando: `wsl -u root`</span><span class="sxs-lookup"><span data-stu-id="0034b-123">Open PowerShell and enter the root of your default WSL distribution using the command: `wsl -u root`</span></span>

    > <span data-ttu-id="0034b-124">Se você precisa atualizar a senha que foi esquecida em uma distribuição que não seja a padrão, use o comando: `wsl -d Debian -u root`, substituindo `Debian` pelo nome da sua distribuição direcionada.</span><span class="sxs-lookup"><span data-stu-id="0034b-124">If you need to update the forgotten password on a distribution that is not your default, use the command: `wsl -d Debian -u root`, replacing `Debian` with the name of your targeted distribution.</span></span>

2. <span data-ttu-id="0034b-125">Após a distribuição do WSL ter sido aberta no nível raiz dentro do PowerShell, você poderá usar este comando para atualizar a senha: `passwd <WSLUsername>`, em que `<WSLUsername>` é o nome de usuário da conta da distribuição cuja senha você esqueceu.</span><span class="sxs-lookup"><span data-stu-id="0034b-125">Once your WSL distribution has been opened at the root level inside PowerShell, you can use this command to update your password: `passwd <WSLUsername>` where `<WSLUsername>` is the username of the account in the DISTRO whose password you've forgotten.</span></span>

3. <span data-ttu-id="0034b-126">Você será solicitado a inserir uma nova senha do UNIX e, em seguida, confirmar essa senha.</span><span class="sxs-lookup"><span data-stu-id="0034b-126">You will be prompted to enter a new UNIX password and then confirm that password.</span></span> <span data-ttu-id="0034b-127">Depois da informação de que a senha foi atualizada com êxito, feche o WSL dentro do PowerShell usando o comando: `exit`</span><span class="sxs-lookup"><span data-stu-id="0034b-127">Once you're told that the password has updated successfully, close WSL inside of PowerShell using the command: `exit`</span></span>

> [!NOTE]
> <span data-ttu-id="0034b-128">Se você está executando uma versão anterior do sistema operacional Windows, como a 1703 (Atualização do Windows 10 para Criadores) ou a 1709 (Windows 10 Fall Creators Update), consulte a [versão arquivada deste documento de atualização de conta de usuário](./user-support-archived.md).</span><span class="sxs-lookup"><span data-stu-id="0034b-128">If you are running an early version of Windows operating system, like 1703 (Creators Update) or 1709 (Fall Creators Update), see the [archived version of this user account update doc](./user-support-archived.md).</span></span>
