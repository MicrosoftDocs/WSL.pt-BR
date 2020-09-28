---
title: Perguntas frequentes sobre o WSL 2
description: Encontre respostas para perguntas frequentes sobre o Subsistema do Windows para Linux 2, como 'Posso executar o WSL 2 em uma máquina virtual?'.
keywords: BashOnWindows, Bash, WSL, WSL 2, Windows, subsistema do Windows para Linux, subsistema do Windows, Ubuntu, Debian, Suse, Windows 10, instalar
ms.date: 05/30/2019
ms.topic: article
ms.assetid: 7afaeacf-435a-4e58-bff0-a9f0d75b8a51
ms.custom: seodec18
ms.localizationpriority: high
ms.openlocfilehash: 458aadc89e0f8e63e7d7bad780ed8c5fad0de702
ms.sourcegitcommit: 69fc9d3ca22cf3f07622db4cdf80c8ec751fe620
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90818677"
---
# <a name="wsl-2-faqs"></a>Perguntas frequentes sobre o WSL 2

Veja abaixo uma lista de perguntas frequentes sobre o Subsistema do Windows para Linux 2.

## <a name="does-wsl-2-use-hyper-v-will-it-be-available-on-windows-10-home"></a>O WSL 2 usa o Hyper-V? Ele estará disponível no Windows 10 Home?

O WSL 2 está disponível em todos os SKUs nos quais o WSL está disponível no momento, incluindo o Windows 10 Home.

A versão mais recente do WSL usa a arquitetura do Hyper-V para habilitar a virtualização. Essa arquitetura estará disponível no componente opcional “Plataforma de máquina virtual”. Esse componente opcional estará disponível em todos os SKUs. Você pode esperar ver mais detalhes sobre essa experiência perto do lançamento do WSL 2.

## <a name="what-will-happen-to-wsl-1-will-it-be-abandoned"></a>O que acontecerá com o WSL 1? Ele será abandonado?

No momento, não temos planos para substituir o WSL 1. Você pode executar as distribuições do WSL 1 e do WSL 2 lado a lado e pode atualizar e fazer downgrade de qualquer distribuição a qualquer momento. Adicionar o WSL 2 como uma nova arquitetura proporciona uma plataforma melhor para a equipe do WSL fornecer recursos que tornam o WSL um modo incrível de executar um ambiente Linux no Windows.

## <a name="will-i-be-able-to-run-wsl-2-and-other-3rd-party-virtualization-tools-such-as-vmware-or-virtualbox"></a>Poderei executar o WSL 2 e outras ferramentas de virtualização de terceiros, como VMware ou VirtualBox?

Alguns aplicativos de terceiros não funcionam quando o Hyper-V está em uso, o que significa que eles não poderão ser executados quando o WSL 2 estiver habilitado, como VMware e VirtualBox. No entanto, recentemente, o VirtualBox e o VMware lançaram versões compatíveis com Hyper-V e WSL2. Saiba mais sobre as [alterações no VirtualBox aqui][1] e as [alterações no VMware aqui][4]. Para solucionar problemas, dê uma olhada nas [discussões sobre problemas do VirtualBox no repositório WSL no GitHub](https://github.com/MicrosoftDocs/WSL/issues?q=is%3Aissue+virtualbox+sort%3Acomments-desc).

Estamos trabalhando consistentemente em soluções para dar suporte à integração de terceiros do Hyper-V. Por exemplo, expomos um conjunto de APIs, chamado [Plataforma de Hipervisor][2] que provedores de virtualização de terceiros podem usar para tornar o software compatível com o Hyper-V. Isso permite que os aplicativos usem a arquitetura do Hyper-V para emulação, como [o Google Android Emulator][3] e o VirtualBox 6 e superiores, que agora são compatíveis com o Hyper-V.

## <a name="can-i-access-the-gpu-in-wsl-2-are-there-plans-to-increase-hardware-support"></a>Posso acessar a GPU no WSL 2? Há planos para aumentar o suporte a hardware?

Liberamos o suporte para acessar a GPU dentro de distribuições do WSL 2. Isso significa que agora você poderá usar o WSL para cenários de aprendizado de máquina, inteligência artificial e ciência de dados mais facilmente quando conjuntos de Big Data estiverem envolvidos. Confira o tutorial [Introdução ao suporte a GPU](./tutorials/gpu-compute.md). A partir de agora, o WSL 2 não inclui suporte serial ou suporte a dispositivos USB. Estamos investigando a melhor maneira de adicionar esses recursos.

## <a name="will-wsl-2-be-able-to-use-networking-applications"></a>O WSL 2 será capaz de usar aplicativos de rede?

Sim, em geral, os aplicativos de rede serão mais rápidos e funcionarão melhor, pois temos compatibilidade total com a chamada do sistema. No entanto, a nova arquitetura usa componentes de rede virtualizados. Isso significa que, em builds iniciais de versão prévia, o WSL 2 se comportará de modo semelhante a uma máquina virtual, por exemplo, o WSL 2 terá um endereço IP diferente do computador host. Estamos comprometidos em fazer com que o WSL 2 tenha a mesma aparência do WSL 1 e isso inclui aprimorar nossa história de rede. 

## <a name="can-i-run-wsl-2-in-a-virtual-machine"></a>Posso executar o WSL 2 em uma máquina virtual?

Sim! Você precisa verificar se a máquina virtual tem a virtualização aninhada habilitada. Isso pode ser habilitado em seu host do Hyper-V pai executando o seguinte comando em uma janela do PowerShell com privilégios de administrador:

`Set-VMProcessor -VMName <VMName> -ExposeVirtualizationExtensions $true`

Substitua '&lt;VMName&gt;' pelo nome da máquina virtual.

## <a name="can-i-use-wslconf-in-wsl-2"></a>Posso usar wsl.conf no WSL 2?

O WSL 2 é compatível com o mesmo arquivo wsl.conf que o WSL 1 usa. Isso significa que todas as opções de configuração que você definiu em uma distribuição do WSL 1 (como a montagem automática de unidades do Windows, a habilitação ou desabilitação da interoperabilidade, a alteração do diretório em que as unidades do Windows serão montadas etc.) funcionarão dentro do WSL 2. Saiba mais sobre as opções de configuração do WSL na página [Gerenciamento da distribuição](./wsl-config.md).

 [1]: https://www.virtualbox.org/wiki/Changelog-6.0
 [2]: https://docs.microsoft.com/virtualization/api/
 [3]: https://devblogs.microsoft.com/visualstudio/hyper-v-android-emulator-support/
 [4]: https://blogs.vmware.com/workstation/2020/01/vmware-workstation-tech-preview-20h1.html
