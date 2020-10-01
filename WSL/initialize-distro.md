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
# <a name="initializing-a-newly-installed-distribution"></a>Como inicializar uma distribuição recém-instalada

Depois que a distribuição for baixada e instalada, você precisará concluir a inicialização da nova distribuição:

## <a name="launch-a-distribution"></a>Iniciar uma distribuição

Para concluir a inicialização da distribuição recém-instalada, inicie uma nova instância. Faça isso clicando no botão "Iniciar" no aplicativo da Microsoft Store ou iniciando a distribuição no menu Iniciar:

> Dica: fixe as distribuições usadas com mais frequência no menu Iniciar e/ou na barra de tarefas.

![Iniciar as distribuições por meio do menu Iniciar](media/start-menu.png)

> No Windows Server, inicie o executável `<distribution>.exe` do inicializador da distribuição na pasta de instalação da distribuição.

Na primeira vez em que uma distribuição recém-instalada for executada, uma janela de console será aberta e você precisará aguardar alguns minutos para que a instalação seja concluída.

> Durante essa fase final da instalação, os arquivos da distribuição são descompactados e armazenados no seu computador, prontos para uso. Isso pode levar cerca de um minuto ou mais, dependendo do desempenho dos dispositivos de armazenamento de seu computador. Essa fase de instalação inicial só é necessária quando uma distribuição é instalada de modo limpo; todas as futuras inicializações deverão levar menos de um segundo.

## <a name="setting-up-a-new-linux-user-account"></a>Como configurar uma nova conta de usuário do Linux

Quando a instalação for concluída, você será solicitado a criar uma nova conta de usuário (e sua senha).

![Desempacotamento do Ubuntu no console do Windows](media/UbuntuInstall.png)

Essa conta de usuário destina-se ao usuário não administrador normal como o qual você estará conectado por padrão ao iniciar uma distribuição.

> Você pode escolher qualquer nome de usuário e senha que desejar – eles não têm nenhuma influência sobre seu nome de usuário do Windows.

Quando você abrir uma nova instância da distribuição, não precisará inserir sua senha, mas **se elevar um processo usando o `sudo`, precisará inseri-la**. Portanto, escolha uma senha fácil de ser lembrada. Consulte a página [Suporte ao usuário](user-support.md) para obter mais informações.

## <a name="update--upgrade-your-distributions-packages"></a>Atualizar pacotes da distribuição e fazer upgrade deles

A maioria das distribuições é fornecida com um catálogo de pacotes vazio/mínimo. Recomendamos expressamente que você atualize com regularidade o catálogo de pacotes e faça upgrade dos pacotes instalados usando seu gerenciador de pacotes preferencial da distribuição. No Debian/Ubuntu, você usa apt:

```bash
sudo apt update && sudo apt upgrade
```

> O Windows não atualiza as distribuições do Linux nem faz upgrade delas automaticamente: Essa é uma tarefa que os usuários do Linux preferem controlar por conta própria.

Concluído! Aproveite sua nova distribuição do Linux no WSL! Para saber mais sobre o WSL, examine os outros [documentos do WSL](./index.md) ou a [página de recursos de aprendizagem do WSL](https://aka.ms/learnwsl).

![Aproveite o uso do Linux no WSL](media/linux-on-wsl.png)

## <a name="troubleshooting"></a>Solução de problemas

Veja abaixo erros relacionados e correções sugeridas. Consulte a [página de solução de problemas do WSL](troubleshooting.md) para ver outros erros comuns e suas soluções.

> **Falha na instalação com o erro 0x8007007e** Esse erro ocorre quando o sistema não é compatível com o Linux na loja.  Certifique-se de que:
> * Você está executando o Windows Build 16215 ou posterior. [Verifique seu build](troubleshooting.md#check-your-build-number).
> * O componente opcional do Subsistema Windows para Linux está habilitado e o computador foi reiniciado.  [Verifique se o WSL está habilitado](troubleshooting.md#confirm-wsl-is-enabled).