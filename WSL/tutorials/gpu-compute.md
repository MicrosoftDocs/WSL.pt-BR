---
title: Treinamento de Machine Learning acelerado por GPU no subsistema do Windows para Linux
description: Saiba mais sobre o suporte do WSL 2 para NVIDIA CUDA, DirectML, Tensorflow e PyTorch.
keywords: WSL, Windows, subsistema do Windows, computação GPU, aceleração de GPU, NVIDIA, CUDA, DirectML, Tensorflow, PyTorch, NVIDIA CUDA Preview, Driver de GPU, kit de ferramentas de contêiner NVIDIA, Docker
ms.date: 06/17/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: bc20f2d3f1da646ba01dcdc00de8eca6c3825ec8
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413307"
---
# <a name="gpu-accelerated-machine-learning-training-in-the-windows-subsystem-for-linux"></a>Treinamento de Machine Learning acelerado por GPU no subsistema do Windows para Linux

O suporte para computação de GPU, o #1 recurso mais solicitado do WSL, agora está disponível para visualização por meio do programa Windows Insider. [Ler a postagem do blog](https://blogs.windows.com/windowsdeveloper/?p=55781).

## <a name="what-is-gpu-compute"></a>O que é computação GPU?

A utilização da aceleração de GPU para tarefas de computação intensiva é geralmente conhecida como "computação de GPU". A computação GPU aproveita a GPU (unidade de processamento gráfico) para acelerar cargas de trabalho de matemática pesada e usa seu processamento paralelo para concluir os cálculos necessários com mais rapidez, em muitos casos, do que utilizar apenas uma CPU. Essa paralelização permite melhorias significativas na velocidade de processamento para essas cargas de trabalho de matemática pesadas, quando executadas em uma CPU. O treinamento de modelos de aprendizado de máquina é um ótimo exemplo em que a computação GPU pode acelerar significativamente o tempo para concluir essa tarefa computacionalmente dispendiosa.

## <a name="install-and-set-up"></a>Instalar e configurar

Saiba mais sobre o suporte do WSL 2 e como começar a treinar modelos de aprendizado de máquina no [Guia de treinamento acelerado da GPU](/windows/win32/direct3d12/gpu-accelerated-training) dentro do documentos do DirectML. Este guia aborda:

* Diretrizes para iniciantes ou alunos para configurar o TensorFlow com o DirectML
* Diretrizes para profissionais para começar a executar seus fluxos de trabalho de ML CUDA existentes