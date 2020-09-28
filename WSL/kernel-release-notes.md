---
title: Notas sobre a versão do kernel do Subsistema do Windows para Linux
description: Notas sobre a versão do subsistema Windows para Linux.  Atualizadas mensalmente.
keywords: notas sobre a versão, wsl, windows, subsistema do windows para linux, windowssubsystem, ubuntu, kernel
ms.date: 06/09/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: eb93135355384013b93b4b5c4af03a582280febf
ms.sourcegitcommit: ba3399a5ffeffd23551315acd04ea6848d30693b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90719115"
---
# <a name="release-notes-for-windows-subsystem-for-linux-kernel"></a>Notas sobre a versão do kernel do Subsistema do Windows para Linux

Adicionamos suporte para distribuições do WSL 2, [que usam um kernel completo do Linux](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/). Este kernel do Linux é de software livre, com o código-fonte disponível no repositório [WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel). Esse kernel do Linux é entregue ao seu computador por meio de Microsoft Update e segue uma agenda de lançamento separada para o Subsistema do Windows para Linux, que é fornecido como parte da imagem do Windows.

## <a name="419128-microsoft-standard"></a>4.19.128-microsoft-standard
*Data de lançamento*: 15/09/2020

[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.128-microsoft-standard).

* Essa é uma versão estável de 4.19.128
* Correção do corrompimento de memória do IOCTL do driver dxgkrnl

## <a name="419121-microsoft-standard"></a>4.19.121-microsoft-standard
*Data de lançamento*: pré-lançamento

[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.121-microsoft-standard).

* Drivers: hv: vmbus: hook up dxgkrnl
* Suporte adicionado para a computação GPU

## <a name="419104-microsoft-standard"></a>4.19.104-microsoft-standard
*Data de lançamento*: 09/06/2020 

[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.104-microsoft-standard).

* Atualizar configuração do WSL para 4.19.104

## <a name="41984-microsoft-standard"></a>4.19.84-microsoft-standard
*Data de lançamento*: 12/11/2019 

[Link da versão oficial do Github](https://github.com/microsoft/WSL2-Linux-Kernel/releases/tag/4.19.84-microsoft-standard).

* Esta é a versão estável 4.19.84

