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
# <a name="wsl-user-account-updates-on-previous-windows-versions"></a>WSL atualizações de conta de usuário em versões anteriores do Windows

Esse conteúdo é arquivado para usuários de versões anteriores do sistema operacional Windows que dão suporte ao subsistema para Linux e precisam de suporte com a atualização de contas de usuário do Linux.

Para obter a documentação atual, consulte [contas de usuário para o subsistema do Windows para Linux](./user-support.md).

### <a name="for-creators-update-version-of-windows-and-earlier"></a>Versão de atualização do para criadores do Windows e versões anteriores

Se você estiver executando a Atualização do Windows 10 para Criadores ou anterior, poderá alterar o usuário Bash padrão executando os seguintes comandos:

1. Altere o usuário padrão para `root`:

    ```console
    C:\> lxrun /setdefaultuser root
    ```

1. Execute `bash.exe` para agora fazer logon como `root`:

    ```console
    C:\> bash.exe
    ```

1. Redefina sua senha usando o comando de senha da distribuição e feche o console do Linux:

    ```BASH
    $ passwd username
    $ exit
    ```

1. No CMD do Windows, redefina o usuário padrão de volta para sua conta de usuário Linux normal:

    ```console
    C:\> lxrun.exe /setdefaultuser username
    ```

### <a name="for-fall-creators-update-and-later"></a>Para o Fall Creators Update e posteriores

Para ver quais comandos estão disponíveis para uma determinada distribuição, execute `[distro.exe] /?`.
    
Por exemplo, com o Ubuntu instalado:

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

Instruções passo a passo usando o Ubuntu:

1. Abra o CMD
1. Defina o usuário padrão do Linux como `root`:

    ```console
    C:\> ubuntu config --default-user root
    ```    

1. Inicie sua distribuição do Linux (`ubuntu`).  Você fará logon automaticamente como `root`:

1. Redefina sua senha usando o comando `passwd`:

    ```BASH
    $ passwd username
    ```

1. No CMD do Windows, redefina o usuário padrão de volta para sua conta de usuário Linux normal.

    ```console
    C:\> ubuntu config --default-user username
    ```
