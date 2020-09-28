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
# <a name="gpu-accelerated-machine-learning-training-in-the-windows-subsystem-for-linux"></a><span data-ttu-id="4608c-104">Treinamento de Machine Learning acelerado por GPU no subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="4608c-104">GPU accelerated machine learning training in the Windows Subsystem for Linux</span></span>

<span data-ttu-id="4608c-105">O suporte para computação de GPU, o #1 recurso mais solicitado do WSL, agora está disponível para visualização por meio do programa Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="4608c-105">Support for GPU compute, the #1 most requested WSL feature, is now available for preview via the Windows Insider program.</span></span> <span data-ttu-id="4608c-106">[Ler a postagem do blog](https://blogs.windows.com/windowsdeveloper/?p=55781).</span><span class="sxs-lookup"><span data-stu-id="4608c-106">[Read the blog post](https://blogs.windows.com/windowsdeveloper/?p=55781).</span></span>

## <a name="what-is-gpu-compute"></a><span data-ttu-id="4608c-107">O que é computação GPU?</span><span class="sxs-lookup"><span data-stu-id="4608c-107">What is GPU compute?</span></span>

<span data-ttu-id="4608c-108">A utilização da aceleração de GPU para tarefas de computação intensiva é geralmente conhecida como "computação de GPU".</span><span class="sxs-lookup"><span data-stu-id="4608c-108">Leveraging GPU acceleration for compute-intensive tasks is generally referred  to as "GPU compute".</span></span> <span data-ttu-id="4608c-109">A computação GPU aproveita a GPU (unidade de processamento gráfico) para acelerar cargas de trabalho de matemática pesada e usa seu processamento paralelo para concluir os cálculos necessários com mais rapidez, em muitos casos, do que utilizar apenas uma CPU.</span><span class="sxs-lookup"><span data-stu-id="4608c-109">GPU computing leverages the GPU (graphics processing unit) to accelerate math heavy workloads and uses its parallel processing to complete the required calculations faster, in many cases, than utilizing only a CPU.</span></span> <span data-ttu-id="4608c-110">Essa paralelização permite melhorias significativas na velocidade de processamento para essas cargas de trabalho de matemática pesadas, quando executadas em uma CPU.</span><span class="sxs-lookup"><span data-stu-id="4608c-110">This parallelization enables significant processing speed improvements for these math heavy workloads then when running on a CPU.</span></span> <span data-ttu-id="4608c-111">O treinamento de modelos de aprendizado de máquina é um ótimo exemplo em que a computação GPU pode acelerar significativamente o tempo para concluir essa tarefa computacionalmente dispendiosa.</span><span class="sxs-lookup"><span data-stu-id="4608c-111">Training machine learning models is a great example in which GPU compute can significantly accelerate the time to complete this computationally expensive task.</span></span>

## <a name="install-and-set-up"></a><span data-ttu-id="4608c-112">Instalar e configurar</span><span class="sxs-lookup"><span data-stu-id="4608c-112">Install and set up</span></span>

<span data-ttu-id="4608c-113">Saiba mais sobre o suporte do WSL 2 e como começar a treinar modelos de aprendizado de máquina no [Guia de treinamento acelerado da GPU](/windows/win32/direct3d12/gpu-accelerated-training) dentro do documentos do DirectML. Este guia aborda:</span><span class="sxs-lookup"><span data-stu-id="4608c-113">Learn more about WSL 2 support and how to start training machine learning models in the [GPU Accelerated Training guide](/windows/win32/direct3d12/gpu-accelerated-training) inside the DirectML docs. This guide covers:</span></span>

* <span data-ttu-id="4608c-114">Diretrizes para iniciantes ou alunos para configurar o TensorFlow com o DirectML</span><span class="sxs-lookup"><span data-stu-id="4608c-114">Guidance for beginners or students to set up TensorFlow with DirectML</span></span>
* <span data-ttu-id="4608c-115">Diretrizes para profissionais para começar a executar seus fluxos de trabalho de ML CUDA existentes</span><span class="sxs-lookup"><span data-stu-id="4608c-115">Guidance for professionals to start running their exisiting CUDA ML workflows</span></span>