---
title: WSL atualizações de conta de usuário em versões anteriores do Windows
description: Referência para versões anteriores do Windows para atualizar contas de usuário do Linux com o subsistema do Windows para Linux.
ms.date: 01/20/2020
ms.topic: article
ROBOTS: NOINDEX
ms.openlocfilehash: 33a42c8f3bd518fa45df2874a6c59b76cd8ec80a
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413357"
---
# <a name="wsl-user-account-updates-on-previous-windows-versions"></a><span data-ttu-id="0f7b9-103">WSL atualizações de conta de usuário em versões anteriores do Windows</span><span class="sxs-lookup"><span data-stu-id="0f7b9-103">WSL User Account updates on Previous Windows Versions</span></span>

<span data-ttu-id="0f7b9-104">Esse conteúdo é arquivado para usuários de versões anteriores do sistema operacional Windows que dão suporte ao subsistema para Linux e precisam de suporte com a atualização de contas de usuário do Linux.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-104">This content is archived for users of earlier versions of Windows operating system that support the subsystem for Linux and need support with updating Linux user accounts.</span></span>

<span data-ttu-id="0f7b9-105">Para obter a documentação atual, consulte [contas de usuário para o subsistema do Windows para Linux](./user-support.md).</span><span class="sxs-lookup"><span data-stu-id="0f7b9-105">For current documentation, see [User Accounts for Windows Subsystem for Linux](./user-support.md).</span></span>

### <a name="for-creators-update-version-of-windows-and-earlier"></a><span data-ttu-id="0f7b9-106">Versão de atualização do para criadores do Windows e versões anteriores</span><span class="sxs-lookup"><span data-stu-id="0f7b9-106">For Creators Update version of Windows and earlier</span></span>

<span data-ttu-id="0f7b9-107">Se você estiver executando a Atualização do Windows 10 para Criadores ou anterior, poderá alterar o usuário Bash padrão executando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-107">If you're running Windows 10 Creators update or earlier, you can change the default Bash user by running the following commands:</span></span>

1. <span data-ttu-id="0f7b9-108">Altere o usuário padrão para `root`:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-108">Change the default user to `root`:</span></span>

    ```console
    C:\> lxrun /setdefaultuser root
    ```

1. <span data-ttu-id="0f7b9-109">Execute `bash.exe` para agora fazer logon como `root`:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-109">Run `bash.exe` to now login as `root`:</span></span>

    ```console
    C:\> bash.exe
    ```

1. <span data-ttu-id="0f7b9-110">Redefina sua senha usando o comando de senha da distribuição e feche o console do Linux:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-110">Reset your password using the distribution's password command, and close the Linux Console:</span></span>

    ```BASH
    $ passwd username
    $ exit
    ```

1. <span data-ttu-id="0f7b9-111">No CMD do Windows, redefina o usuário padrão de volta para sua conta de usuário Linux normal:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-111">From Windows CMD, reset your default user back to your normal Linux user account:</span></span>

    ```console
    C:\> lxrun.exe /setdefaultuser username
    ```

### <a name="for-fall-creators-update-and-later"></a><span data-ttu-id="0f7b9-112">Para o Fall Creators Update e posteriores</span><span class="sxs-lookup"><span data-stu-id="0f7b9-112">For Fall Creators Update and later</span></span>

<span data-ttu-id="0f7b9-113">Para ver quais comandos estão disponíveis para uma determinada distribuição, execute `[distro.exe] /?`.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-113">To see what commands are available for a particular distribution, run `[distro.exe] /?`.</span></span>
    
<span data-ttu-id="0f7b9-114">Por exemplo, com o Ubuntu instalado:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-114">For example, with Ubuntu installed:</span></span>

```console
C:\> ubuntu.exe /?

Launches or configures a linux distribution.

Usage:
    <no args>
      - Launches the distro's default behavior. By default, this launches your default shell.

    run <command line>
      - Run the given command line in that distro, using the default configuration.
      - Everything after `run ` is passed to the linux LaunchProcess cal

    config [setting [value]]
      - Configure certain settings for this distro.
      - Settings are any of the following (by default)
        - `--default-user <username>`: Set the default user for this distro to <username>

    clean
      - Uninstalls the distro. The appx remains on your machine. This can be
        useful for "factory resetting" your instance. This removes the linux
        filesystem from the disk, but not the app from your PC, so you don't
        need to redownload the entire tar.gz again.

    help
      - Print this usage message.
```

<span data-ttu-id="0f7b9-115">Instruções passo a passo usando o Ubuntu:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-115">Step by step instructions using Ubuntu:</span></span>

1. <span data-ttu-id="0f7b9-116">Abra o CMD</span><span class="sxs-lookup"><span data-stu-id="0f7b9-116">Open CMD</span></span>
1. <span data-ttu-id="0f7b9-117">Defina o usuário padrão do Linux como `root`:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-117">Set the default Linux user to `root`:</span></span>

    ```console
    C:\> ubuntu config --default-user root
    ```    

1. <span data-ttu-id="0f7b9-118">Inicie sua distribuição do Linux (`ubuntu`).</span><span class="sxs-lookup"><span data-stu-id="0f7b9-118">Launch your Linux distribution (`ubuntu`).</span></span>  <span data-ttu-id="0f7b9-119">Você fará logon automaticamente como `root`:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-119">You will automatically login as `root`:</span></span>

1. <span data-ttu-id="0f7b9-120">Redefina sua senha usando o comando `passwd`:</span><span class="sxs-lookup"><span data-stu-id="0f7b9-120">Reset your password using the `passwd` command:</span></span>

    ```BASH
    $ passwd username
    ```

1. <span data-ttu-id="0f7b9-121">No CMD do Windows, redefina o usuário padrão de volta para sua conta de usuário Linux normal.</span><span class="sxs-lookup"><span data-stu-id="0f7b9-121">From Windows CMD, reset your default user back to your normal Linux user account.</span></span>

    ```console
    C:\> ubuntu config --default-user username
    ```
