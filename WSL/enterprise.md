---
title: WSL para Empresas
description: Recursos e instruções sobre como usar melhor o WSL em um ambiente Enterprise.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, debian, suse, windows 10, enterprise, deployment, offline, packaging, store, distribution, installation, install
ms.date: 12/14/2020
ms.topic: article
ms.assetid: 7afaeacf-435a-4e58-bff0-a9f0d75b8a51
ms.custom: seodec18
ms.openlocfilehash: a210268fb460a793fec2047c6d6678f92869ea16
ms.sourcegitcommit: 0523e6a2ca99f5f3b188d526afed3ce6ad7e3abb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "98766862"
---
# <a name="windows-subsystem-for-linux-for-enterprise"></a>Subsistema do Windows para Linux for Enterprise

Como administrador ou gerente, você pode exigir que todos os desenvolvedores usem o mesmo software aprovado. Essa consistência ajuda a criar um ambiente de trabalho bem definido. O Subsistema do Windows para Linux auxilia nessa consistência permitindo que você importe e exporte imagens WSL personalizadas de um computador para o próximo. Leia o guia abaixo para saber mais sobre como:

* [Como criar uma imagem do WSL personalizada](#creating-a-custom-wsl-image)
* [Como distribuir uma imagem do WSL](#distributing-your-wsl-image)
* [Atualizar distribuições e pacotes do Linux e aplicar patch deles](#update-and-patch-linux-distributions-and-packages)
* [Opções de segurança e controle do Enterprise](#enterprise-security-and-control-options)

## <a name="creating-a-custom-wsl-image"></a>Como criar uma imagem do WSL personalizada

O que é comumente denominado "imagem" é simplesmente um instantâneo do seu software e dos componentes dele salvos em um arquivo. No caso do Subsistema do Windows para Linux, sua imagem seria composta pelo subsistema, as distribuições dele e o software e os pacotes instalados na distribuição.

Para começar a criar sua imagem do WSL, primeiro [instale o Subsistema do Windows para Linux](./install-win10.md).

Depois de instalado, use o Microsoft Store para Empresas para baixar e instalar a distribuição do Linux ideal para você. Crie uma conta com o [Microsoft Store para Empresas](https://docs.microsoft.com/microsoft-store/sign-up-microsoft-store-for-business.)

### <a name="exporting-your-wsl-image"></a>Como exportar sua imagem do WSL

Exporte sua imagem do WSL personalizada executando wsl --export `<Distro> <FileName>`, que encapsulará sua imagem em um arquivo tar e a deixará pronta para distribuição para outros computadores.

## <a name="distributing-your-wsl-image"></a>Como distribuir sua imagem do WSL

Distribua a imagem do WSL de um dispositivo de compartilhamento ou de armazenamento executando wsl --import `<Distro> <InstallLocation> <FileName>`, que importará o arquivo tar especificado como uma nova distribuição.

## <a name="update-and-patch-linux-distributions-and-packages"></a>Atualizar distribuições e pacotes do Linux e aplicar patch deles

Recomenda-se usar o gerenciador de configuração do Linux para monitorar e gerenciar o espaço do usuário do Linux. Há um host de configuração do Linux no qual os gerentes podem escolher. Confira esta [postagem no blog](http://www.craigloewen.com/blog/2019/12/04/running-puppet-quickly-in-wsl2/) sobre como instalar o Puppet no WSL 2.

## <a name="enterprise-security-and-control-options"></a>Opções de segurança e controle do Enterprise

No momento, o WSL oferece mecanismos de controle limitado para modificar a experiência do usuário em um cenário Enterprise. Os recursos Enterprise continuam em desenvolvimento. Veja abaixo as áreas de recursos com e sem suporte. Para solicitar um novo recurso que não consta na lista, registre um problema no [repositório GitHub](https://github.com/microsoft/WSL/issues?q=is%3Aissue+is%3Aopen+enterprise).

### <a name="supported"></a>Com suporte

* Compartilhar uma imagem aprovada internamente usando `wsl --import` e `wsl --export`
* Criar sua distribuição WSL para seu Enterprise usando o [repositório WSL Distro Launcher](https://github.com/microsoft/WSL-DistroLauncher)

Esta é uma lista de recursos para os quais nós ainda não temos suporte, mas estamos investigando.

### <a name="unsupported"></a>Sem suporte

* Sincronizar o usuário dentro do WSL com o usuário do Windows no computador host
* Gerenciar atualizações e aplicar patch de pacotes e distribuições do Linux usando ferramentas do Windows
* Fazer o Windows Update atualizar também o conteúdo da distribuição WSL
* Controlar quais distribuições os usuários em seu Enterprise podem acessar
* Executar serviços obrigatórios (registrar ou monitorar) dentro do WSL
* Monitorar instâncias do Linux usando as ferramentas do gerenciador de configuração do Windows como o SCCM ou o Intune
* Suporte do McAfee
