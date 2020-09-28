---
title: Introdução ao uso de VS Code com o subsistema do Windows para Linux
description: Saiba como configurar VS Code para criar e depurar código usando o subsistema do Windows para Linux.
keywords: WSL, Windows, windowssubsystem, GNU, Linux, Bash, vs Code, extensão remota, depuração, caminho, Visual Studio
ms.date: 05/28/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: b39b34644040354df44bf62ec7b878e3f5d667e6
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413337"
---
# <a name="get-started-using-visual-studio-code-with-windows-subsystem-for-linux"></a>Introdução ao uso de Visual Studio Code com o subsistema do Windows para Linux

Visual Studio Code, juntamente com a extensão Remote-WSL, permite que você use o WSL como seu ambiente de desenvolvimento em tempo integral diretamente do VS Code. Você pode:

* desenvolva em um ambiente baseado em Linux
* usar cadeias e utilitários específicos do Linux
* Execute e depure seus aplicativos baseados em Linux do conforto do Windows mantendo o acesso a ferramentas de produtividade como o Outlook e o Office
* Use o VS Code terminal interno para executar sua distribuição do Linux de sua escolha
* Aproveite os recursos de VS Code como a [conclusão de código do IntelliSense](https://code.visualstudio.com/docs/editor/intellisense), a reutilização, o [suporte à depuração](https://code.visualstudio.com/docs/nodejs/nodejs-debugging), os [trechos de código](https://code.visualstudio.com/docs/editor/userdefinedsnippets)e os testes de [unidade](https://code.visualstudio.com/docs/python/testing) [linting](https://code.visualstudio.com/docs/python/linting)
* Gerencie facilmente seu controle de versão com o suporte interno a [git](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support) do vs Code
* executar comandos e extensões de VS Code diretamente em seus projetos do WSL
* Edite arquivos em seu sistema operacional Windows Linux ou montado (por exemplo/mnt/c) sem se preocupar com problemas de caminhos, compatibilidade binária ou outros desafios entre sistemas operacionais

## <a name="install-vs-code-and-the-remote-wsl-extension"></a>Instalar VS Code e a extensão WSL remota

* Visite a [página de instalação do vs Code](https://code.visualstudio.com/download) e selecione o instalador de 32 ou 64 bits. Instale o Visual Studio Code no Windows (não em seu sistema de arquivos WSL).

* Quando solicitado a **selecionar tarefas adicionais** durante a instalação, certifique-se de marcar a opção **Adicionar ao caminho** para que você possa abrir facilmente uma pasta no WSL usando o comando de código.

* Instale o [pacote de extensão de desenvolvimento remoto](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack). Esse pacote de extensão inclui a extensão WSL remota, além das extensões SSH remota e contêineres remotos, permitindo que você abra qualquer pasta em um contêiner, em um computador remoto ou em WSL.

> [!IMPORTANT]
> Para instalar a extensão Remote-WSL, você precisará da versão [1,35 pode ser lançada](https://code.visualstudio.com/updates/v1_35) ou posterior do vs Code. Não recomendamos o uso de WSL em VS Code sem a extensão WSL remota, pois você perderá o suporte para preenchimento automático, depuração, refiapo, etc. Fatos divertidos: essa extensão WSL é instalada em $HOME/.vscode/Extensions (Insira o comando `ls $HOME\.vscode\extensions\` no PowerShell).

## <a name="update-your-linux-distribution"></a>Atualizar sua distribuição do Linux

Algumas distribuições do Linux WSL são bibliotecas que são necessárias para que o servidor de VS Code seja inicializado. Você pode adicionar bibliotecas adicionais à sua distribuição do Linux usando seu Gerenciador de pacotes.

Por exemplo, para atualizar o Debian ou Ubuntu, use:

```bash
sudo apt-get update
```

Para adicionar wget (para recuperar o conteúdo de servidores Web) e certificados de CA (para permitir que aplicativos baseados em SSL verifiquem a autenticidade das conexões SSL), digite:

```bash
sudo apt-get install wget ca-certificates
```

## <a name="open-a-wsl-project-in-visual-studio-code"></a>Abra um projeto do WSL no Visual Studio Code

### <a name="from-the-command-line"></a>Na linha de comando

Para abrir um projeto da sua distribuição do WSL, abra a linha de comando da distribuição e digite: `code .`

![Abrir o projeto WSL com o servidor remoto VS Code](../media/wsl-open-vs-code.gif)

### <a name="from-vs-code"></a>De VS Code

Você também pode acessar mais VS Code opções remotas usando o atalho: `CTRL+SHIFT+P` em vs Code para abrir a paleta de comandos. Se você digitar, `VSCODE-REMOTE` verá todas as vs Code opções remotas disponíveis, permitindo que você reabra a pasta em uma sessão remota, especifique a distribuição que deseja abrir e muito mais.

![Paleta de comandos do VS Code](../media/vscode-remote-command-palette.png)

## <a name="extensions-inside-of-vs-code-remote"></a>Extensões dentro de VS Code remotas

A extensão Remote-WSL divide VS Code em uma arquitetura de "cliente-servidor", com o cliente (a interface do usuário) em execução no computador com Windows e no servidor (seu código, git, plug-ins, etc) em execução remota.

Ao executar VS Code remoto, a seleção da guia ' extensões ' exibirá uma lista de extensões divididas entre o computador local e sua distribuição WSL.

A instalação de uma extensão local, como um [tema](https://marketplace.visualstudio.com/search?target=VSCode&category=Themes&sortBy=Installs), só precisa ser instalada uma vez.

Algumas extensões, como a [extensão do Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python) ou qualquer coisa que manipule coisas como refazer o pano ou a depuração, devem ser instaladas separadamente em cada distribuição de WSL remota. VS Code exibirá um ícone de aviso ⚠ , junto com um botão "instalar no WSL" verde, se você tiver uma extensão instalada localmente que não esteja instalada em seu WSL remoto.

![VS Code com extensões remotas do WSL vs. extensões locais](../media/vscode-remote-wsl-extensions.png)

Para obter mais informações, consulte o VS Code docs:

* Quando VS Code Remote é iniciado no WSL, nenhum script de inicialização do Shell é executado. Consulte o [artigo script de configuração de ambiente avançado](https://code.visualstudio.com/docs/remote/wsl#_advanced-environment-setup-script) para obter mais informações sobre como executar comandos adicionais ou modificar o ambiente.

* Problemas ao iniciar o VS Code na linha de comando do WSL? Este [Guia de solução de problemas](https://code.visualstudio.com/docs/remote/troubleshooting#_fixing-problems-with-the-code-command-not-working) inclui dicas sobre como alterar variáveis de caminho, resolver erros de extensão sobre dependências ausentes, resolver problemas de finalização de linha do git, instalar um VSIX local em um computador remoto, iniciar uma janela do navegador, porta de localhost do bloqueador, soquetes da Web não funcionando, erros de armazenamento de dados de extensão e muito mais.

## <a name="install-git-optional"></a>Instalar o Git (opcional)

Se você pretende colaborar com outras pessoas ou hospedar seu projeto em um site de software livre (como o GitHub), o VS Code é compatível com o [controle de versão com o Git](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support). A guia Controle do Código-fonte no VS Code acompanha todas as alterações e tem comandos Git comuns (add, commit, push e pull) incorporados diretamente na interface do usuário.

Para instalar o Git, consulte [Configurar o Git para funcionar com o subsistema do Windows para Linux](./wsl-git.md).

## <a name="install-windows-terminal-optional"></a>Instalar o Terminal do Windows (opcional)

O novo terminal do Windows permite várias guias (alternar rapidamente entre o prompt de comando, o PowerShell ou várias distribuições do Linux), associações de chave personalizadas (crie suas próprias teclas de atalho para abrir ou fechar guias, copiar + colar, etc.), emojis ☺ e temas personalizados (esquemas de cores, estilos e tamanhos de fonte, imagem de plano de fundo/desfoque Saiba mais nos [documentos de terminal do Windows](/windows/terminal).

1. Obtenha o [Terminal do Windows na Microsoft Store](https://www.microsoft.com/store/apps/9n0dx20hk701): Ao instalar por meio da loja, as atualizações serão manipuladas automaticamente.

2. Depois de instalado, abra o Terminal do Windows e selecione **Configurações** para personalizar o terminal usando o arquivo `profile.json`.

## <a name="additional-resources"></a>Recursos adicionais

* [Desenvolvimento VS Code remoto](https://code.visualstudio.com/docs/remote/remote-overview)
* [Dicas e truques de desenvolvimento remoto](https://code.visualstudio.com/docs/remote/troubleshooting)
* [Tutorial de desenvolvimento remoto com WSL](https://code.visualstudio.com/remote-tutorials/wsl/getting-started)
* [Usando o Docker com WSL 2 e VS Code](https://code.visualstudio.com/blogs/2020/03/02/docker-in-wsl2)
* [Usando C++ e WSL no VS Code](https://code.visualstudio.com/docs/cpp/config-wsl)
* [Serviço R Remoto para Linux](/visualstudio/rtvs/setting-up-remote-r-service-on-linux)

Algumas extensões adicionais que talvez você queira considerar incluem:

* [Mapas de teclas de outros editores](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads): essas extensões poderão ajudar na familiaridade com seu ambiente se você estiver fazendo a transição de outro editor de texto (como Atom, Sublime, Vim, eMacs, Notepad++ etc.).
* [Sincronização de configurações](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync): permite que você sincronize suas configurações do VS Code em diferentes instalações usando o GitHub. Se você trabalha em diferentes computadores, isso ajuda a manter seu ambiente consistente entre eles.
* [Depurador para Chrome](https://code.visualstudio.com/blogs/2016/02/23/introducing-chrome-debugger-for-vs-code): depois de concluir o desenvolvimento no lado do servidor com o Linux, você precisará desenvolver e testar o lado do cliente. Essa extensão integra seu editor do VS Code ao serviço de depuração do navegador Chrome, tornando as coisas um pouco mais eficientes.
