---
title: Introdução ao uso do git no subsistema do Windows para Linux
description: Saiba como configurar o Git para controle de versão no subsistema do Windows para Linux.
keywords: WSL, Windows, windowssubsystem, GNU, Linux, Bash, git, GitHub, controle de versão
ms.date: 06/04/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 2d05e83d4c87b1b03028856bcec9d5205205535a
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413347"
---
# <a name="get-started-using-git-on-windows-subsystem-for-linux"></a>Introdução ao uso do git no subsistema do Windows para Linux

O Git é o sistema de controle de versão mais comumente usado. Com o Git, você pode controlar as alterações feitas nos arquivos, de modo que tem um registro do que foi feito e ter a capacidade de reverter para versões anteriores dos arquivos, se necessário. O Git também facilita a colaboração, permitindo que as alterações feitas por várias pessoas sejam mescladas em uma fonte.

## <a name="git-can-be-installed-on-windows-and-on-wsl"></a>O Git pode ser instalado no Windows e no WSL

Uma consideração importante: ao habilitar o WSL e instalar uma distribuição do Linux, você está instalando um novo sistema de arquivos, separado do Windows NTFS C:\ em seu computador. No Linux, as unidades não recebem letras. Eles recebem pontos de montagem. A raiz do sistema de arquivos `/` é o ponto de montagem de sua partição raiz, ou pasta, no caso do WSL. Nem tudo `/` está sob a mesma unidade. Por exemplo, em meu laptop, instalei duas versões do Ubuntu (20, 4 e 18, 4), bem como debian. Se eu abrir essas distribuições, selecionar o diretório raiz com o comando `cd ~` e, em seguida, inserir o comando `explorer.exe .` , o explorador de arquivos do Windows será aberto e mostrarei o caminho do diretório para essa distribuição.

| Distribuição Linux | Caminho do Windows para acessar a pasta base |
| ----------- | ----------- |
| Ubuntu 20.04 | `\\wsl$\Ubuntu-20.04\home\username` |
| Ubuntu 18.04 | `\\wsl$\Ubuntu-18.04\home\username` |
| Debian | `\\wsl$\Debian\home\username` |
| Windows PowerShell | `C:\Users\username` |

> [!TIP]
> Se você estiver procurando acessar o diretório de arquivos do Windows de sua linha de comando de distribuição WSL, em vez de `C:\Users\username` , o diretório será acessado usando `/mnt/c/Users/username` , pois a distribuição do Linux exibe o sistema de arquivos do Windows como uma unidade montada.

Será necessário instalar o Git em cada sistema de arquivos com o qual você pretende usá-lo.

![Mostrando versões do git por distribuição](../media/git-versions.gif)

## <a name="installing-git"></a>Instalando o Git

O Git já vem instalado com a maioria das distribuições do subsistema do Windows para Linux, no entanto, talvez você queira atualizar para a versão mais recente. Também será necessário configurar o arquivo de configuração do git.

Para instalar o Git, consulte o [download do git para o site do Linux](https://git-scm.com/download/linux) . Cada distribuição do Linux tem seu próprio Gerenciador de pacotes e comando de instalação.

Para a versão mais recente do git estável no Ubuntu/Debian, insira o comando:

```bash
sudo apt-get install git
```

> [!NOTE]
> Você também pode querer [instalar o Git para Windows](https://git-scm.com/download/win) se ainda não tiver feito isso.

## <a name="git-config-file-setup"></a>Configuração do arquivo de configuração git

Para configurar o arquivo de configuração do git, abra uma linha de comando para a distribuição na qual você está trabalhando e defina seu nome com esse comando (substituindo "seu nome" pelo seu nome de usuário do git):

```bash
git config --global user.name "Your Name"
```

Defina seu email com este comando (substituindo " youremail@domain.com " pelo email que você usa em sua conta do git):

```bash
git config --global user.email "youremail@domain.com"
```

> [!TIP]
> Se você ainda não tiver uma conta do Git, poderá [se inscrever em uma no GitHub](https://github.com/join). Se você nunca trabalhou com o Git antes, os [Guias do GitHub](https://guides.github.com/) podem ajudar você a começar a usá-lo. Se você precisar editar o git config, poderá fazer isso com um editor de texto interno como o nano: `nano ~/.gitconfig`.

Recomendamos que você [proteja sua conta com a autenticação de dois fatores (2FA)](https://help.github.com/en/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa).

## <a name="git-credential-manager-setup"></a>Instalação do git Credential Manager

O Gerenciador de credenciais do git permite autenticar um servidor git remoto, mesmo que você tenha um padrão de autenticação complexo, como autenticação de dois fatores, Azure Active Directory ou usando URLs remotas SSH que exigem uma senha de chave SSH para cada Push do git. O Gerenciador de Credenciais do Git se integra ao fluxo de autenticação para serviços como o GitHub e, uma vez que você está autenticado no provedor de hospedagem, solicita um novo token de autenticação. Em seguida, ele armazena o token com segurança no [Gerenciador de credenciais do Windows](https://support.microsoft.com/help/4026814/windows-accessing-credential-manager). Após a primeira vez, você pode usar o Git para se comunicar com seu provedor de hospedagem sem a necessidade de uma nova autenticação. Ele só acessará o token no Gerenciador de Credenciais do Windows.

Para configurar o Gerenciador de Credenciais do Git para uso com uma distribuição do WSL, abra a distribuição e insira este comando:

```Bash
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe"
```

Agora, todas as operações de git realizadas na distribuição do WSL usarão o Gerenciador de Credenciais. Se você já tiver credenciais armazenadas em cache para um host, elas serão acessadas do Gerenciador de Credenciais. Caso contrário, você receberá uma resposta em uma caixa de diálogo solicitando suas credenciais, mesmo que esteja em um console do Linux.

> [!NOTE]
> Se você estiver usando uma chave GPG para segurança de assinatura de código, talvez seja necessário [associar sua chave GPG ao seu email do GitHub](https://help.github.com/en/github/authenticating-to-github/associating-an-email-with-your-gpg-key).

## <a name="adding-a-git-ignore-file"></a>Adicionando um arquivo de ignorar git

É recomendável adicionar um [arquivo. gitignore](https://help.github.com/en/articles/ignoring-files) a seus projetos. O GitHub oferece [uma coleção de modelos. gitignore úteis](https://github.com/github/gitignore) com as configurações de arquivo. gitignore recomendadas organizadas de acordo com seu caso de uso. Por exemplo, aqui está [o modelo de gitignore padrão do GitHub para um projeto Node.js](https://github.com/github/gitignore/blob/master/Node.gitignore).

Se você optar por [criar um novo repositório usando o site do GitHub](https://help.github.com/articles/create-a-repo), há caixas de seleção disponíveis para inicializar o repositório com um arquivo Leiame, o arquivo. gitignore configurado para o tipo de projeto específico e as opções para adicionar uma licença se você precisar de uma.

## <a name="git-and-vs-code"></a>Git e VS Code

O Visual Studio Code vem com suporte interno para git, incluindo uma guia de controle do código-fonte que mostrará suas alterações e tratará uma variedade de comandos git para você. Saiba mais sobre o [suporte ao git de vs Code](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support).

## <a name="git-line-endings"></a>Terminações de linha git

Se você estiver trabalhando com a mesma pasta de repositório entre Windows, WSL ou um contêiner, certifique-se de configurar as terminações de linha consistentes.

Como o Windows e o Linux usam diferentes terminações de linha padrão, o Git pode relatar um grande número de arquivos modificados que não têm nenhuma diferença além das suas terminações de linha. Para evitar que isso aconteça, você pode desabilitar a conversão de terminação de linha usando um `.gitattributes` arquivo ou globalmente no lado do Windows. Consulte este [vs Code doc sobre como resolver problemas de finalização de linha do git](https://code.visualstudio.com/docs/remote/troubleshooting#_resolving-git-line-ending-issues-in-containers-resulting-in-many-modified-files).

## <a name="additional-resources"></a>Recursos adicionais

* [WSL & VS Code](./wsl-vscode.md)
* [Laboratório de aprendizado do GitHub: cursos online](https://lab.github.com/)
* [Ferramenta de visualização do git](http://git-school.github.io/visualizing-git/)
* [Ferramentas git – armazenamento de credenciais](https://git-scm.com/book/it/v2/Git-Tools-Credential-Storage)
