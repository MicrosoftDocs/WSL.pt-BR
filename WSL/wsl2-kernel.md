---
title: Atualizar o kernel do WSL 2 Linux
description: Instruções sobre como atualizar o kernel do WSL 2 Linux manualmente
keywords: wsl, windows, linux kernel, windows subsystem for linux, kernel
ms.date: 03/12/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 7bf2ef606d0bd23083f323117348aeea87c52b10
ms.sourcegitcommit: 609850fadd20687636b8486264e87af47c538111
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2020
ms.locfileid: "92444802"
---
# <a name="updating-the-wsl-2-linux-kernel"></a>Atualizar o kernel do WSL 2 Linux

Para atualizar manualmente o kernel do Linux dentro do WSL2, siga estas etapas.

> [!NOTE] 
> Se o instalador não conseguir encontrar a WSL 1, clique com o botão direito do mouse no instalador de atualização do kernel do Linux e pressione "Desinstalar", então execute novamente o instalador.

## <a name="download-the-linux-kernel-update-package"></a>Baixar o pacote de atualização do kernel do Linux

[Baixe o pacote de atualização do último kernel do Linux para o WSL 2](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi) para computadores x64.

> [!NOTE]
> Se estiver usando um computador ARM64, baixe o [pacote ARM64](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi).

## <a name="install-the-linux-kernel-update-package"></a>Instalar o pacote de atualização do kernel do Linux

Para instalar o pacote de atualização do kernel do Linux:

  1. Execute o pacote de atualização baixado na etapa anterior.

  2. Você receberá uma solicitação para fornecer permissões elevadas, selecione 'Sim' para aprovar essa instalação.

  3. Quando a instalação for concluída, você estará pronto para começar a usar o WSL2!

## <a name="future-plans-for-updating-the-wsl2-linux-kernel"></a>Planos futuros para atualizar o kernel do WSL2 Linux

Para obter mais informações, leia o artigo [Alterações na atualização do kernel do Linux para o WSL 2](https://devblogs.microsoft.com/commandline/wsl2-will-be-generally-available-in-windows-10-version-2004), disponível no [blog da linha de comando do Windows](https://aka.ms/cliblog).

## <a name="troubleshooting"></a>Solução de problemas

### <a name="this-update-only-applies-to-machines-with-the-windows-subsystem-for-linux"></a>Essa atualização se aplica somente a computadores com o Subsistema do Windows para Linux
Para instalar o kernel do MSI, o WSL é necessário e deve ser habilitado primeiro. Se ele falhar, você verá a mensagem: `This update only applies to machines with the Windows Subsystem for Linux`. 

Há três motivos possíveis para você ver essa mensagem:

1. Você ainda está usando uma versão antiga do Windows, que não dá suporte ao WSL 2. Verifique os [requisitos do WSL 2](https://docs.microsoft.com/windows/wsl/install-win10#update-to-wsl-2) e faça as atualizações necessárias para usá-lo. 
2. O `Windows Subsystem for Linux` não está habilitado. Siga o [guia de instalação do Subsistema do Windows para Linux](https://docs.microsoft.com/windows/wsl/install-win10).
3. Depois que você habilitar o `Windows Subsystem for Linux`, uma reinicialização será necessária para que ele entre em vigor. Reinicialize o computador e tente novamente.

### `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`

Cada vez que o kernel estiver ausente em %SystemRoot%\system32\lxss\tools\,, você deverá encontrar o erro acima.

Aqui estão algumas maneiras possíveis de solucioná-lo:

1. Instale o kernel do Linux manualmente seguindo as instruções nesta página.
2. Desinstale o MSI em 'Adicionar ou Remover Programas' e instale-o novamente.