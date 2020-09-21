---
title: Introdução ao uso de contêineres do Docker com o subsistema do Windows para Linux
description: Saiba como configurar contêineres do Docker no subsistema do Windows para Linux.
keywords: WSL, Windows, windowssubsystem, Windows 10, Docker, contêineres
ms.date: 08/28/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 2ae9da815335f99a9b4a75334a02d2730ddd08c6
ms.sourcegitcommit: 69fc9d3ca22cf3f07622db4cdf80c8ec751fe620
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90818748"
---
# <a name="get-started-with-docker-remote-containers-on-wsl-2"></a>Introdução aos contêineres remotos do Docker no WSL 2

Este guia passo a passo ajudará você a começar a desenvolver com contêineres remotos **Configurando o Docker desktop para Windows com WSL 2** (subsistema do Windows para Linux, versão 2).

O Docker desktop para Windows está disponível gratuitamente e fornece um ambiente de desenvolvimento para a criação, o envio e a execução de aplicativos Docker. Habilitando o mecanismo baseado em WSL 2, você pode executar contêineres do Linux e do Windows no Docker desktop no mesmo computador.

## <a name="overview-of-docker-containers"></a>Visão geral dos contêineres do Docker

O Docker é uma ferramenta usada para criar, implantar e executar aplicativos usando contêineres. Os contêineres permitem que os desenvolvedores Empacotem um aplicativo com todas as partes de que precisa (bibliotecas, estruturas, dependências etc.) e enviam tudo isso como um pacote. O uso de um contêiner garante que o aplicativo será executado da mesma forma, independentemente de quaisquer configurações personalizadas ou de bibliotecas instaladas anteriormente no computador que o executa, o que poderia ser diferente do computador usado para gravar e testar o código do aplicativo. Isso permite que os desenvolvedores se concentrem em escrever código sem se preocupar com o sistema no qual o código será executado.

Os contêineres do Docker são semelhantes às máquinas virtuais, mas não criam um sistema operacional virtual inteiro. Em vez disso, o Docker permite que o aplicativo use o mesmo kernel do Linux que o sistema em que ele está sendo executado. Isso permite que o pacote do aplicativo exija apenas as partes que ainda não estão no computador host, reduzindo o tamanho do pacote e melhorando o desempenho.

A disponibilidade contínua, usando contêineres do Docker com ferramentas como [kubernetes](https://docs.microsoft.com/azure/aks/), é outro motivo para a popularidade dos contêineres. Isso permite que várias versões do seu contêiner de aplicativo sejam criadas em momentos diferentes. Em vez de precisar desativar um sistema inteiro para atualizações ou manutenção, cada contêiner (e seus microserviços específicos) pode ser substituído de forma dinâmica. Você pode preparar um novo contêiner com todas as suas atualizações, configurar o contêiner para produção e apenas apontar para o novo contêiner quando ele estiver pronto. Você também pode arquivar versões diferentes do seu aplicativo usando contêineres e mantê-los em execução como um fallback de segurança, se necessário.

Para saber mais, faça checkout da [introdução aos contêineres do Docker](https://docs.microsoft.com/learn/modules/intro-to-docker-containers/) em Microsoft learn.

## <a name="prerequisites"></a>Pré-requisitos

- Verifique se o computador está executando o Windows 10, [atualizado para a versão 2004](ms-settings:windowsupdate), **Build 18362** ou superior.
- [Habilite o WSL, instale uma distribuição do Linux e atualize para o WSL 2](https://docs.microsoft.com/windows/wsl/install-win10).
- [Baixe e instale o pacote de atualização do kernel do Linux](https://docs.microsoft.com/windows/wsl/wsl2-kernel).
- [Instalar Visual Studio Code](https://code.visualstudio.com/download) *(opcional)*. Isso fornecerá a melhor experiência, incluindo a capacidade de codificar e depurar dentro de um contêiner remoto do Docker e conectado à sua distribuição do Linux.
- [Instale o terminal do Windows](https://docs.microsoft.com/windows/terminal/get-started) *(opcional)*. Isso fornecerá a melhor experiência, incluindo a capacidade de personalizar e abrir vários terminais na mesma interface (incluindo Ubuntu, Debian, PowerShell, CLI do Azure ou o que você preferir usar).
- [Inscreva-se para obter uma ID do Docker no Hub do Docker](https://hub.docker.com/signup) *(opcional)*.

> [!NOTE]
> WSL pode executar distribuições no modo WSL versão 1 ou WSL 2. Você pode verificar isso abrindo o PowerShell e inserindo: `wsl -l -v` . Verifique se a sua distribuição está definida para usar o WSL 2 digitando: `wsl --set-version  <distro> 2` . Substitua `<distro>` pelo nome do distribuição (por exemplo, Ubuntu 18, 4).
> 
> No WSL versão 1, devido a diferenças fundamentais entre o Windows e o Linux, o mecanismo do Docker não podia ser executado diretamente dentro do WSL, portanto, a equipe do Docker desenvolveu uma solução alternativa usando VMs do Hyper-V e LinuxKit. No entanto, como o WSL 2 agora é executado em um kernel do Linux com capacidade completa de chamada do sistema, o Docker pode ser executado totalmente no WSL 2. Isso significa que os contêineres do Linux podem ser executados nativamente sem emulação, resultando em melhor desempenho e interoperabilidade entre suas ferramentas do Windows e do Linux.

## <a name="install-docker-desktop"></a>Instalar o Docker Desktop

Com o back-end WSL 2 com suporte no Docker desktop para Windows, você pode trabalhar em um ambiente de desenvolvimento baseado em Linux e criar contêineres baseados em Linux, ao usar Visual Studio Code para edição e depuração de código e executar o contêiner no navegador Microsoft Edge no Windows.

Para instalar o Docker (depois de já [instalar o WSL 2](https://docs.microsoft.com/windows/wsl/install-win10)):

1. Baixe o [Docker desktop](https://docs.docker.com/docker-for-windows/wsl/#download) e siga as instruções de instalação.

2. Depois de instalado, inicie o Docker desktop no menu Iniciar do Windows e selecione o ícone do Docker no menu de ícones ocultos da barra de tarefas. Clique com o botão direito do mouse no ícone para exibir o menu de comandos do Docker e selecione "configurações".
    ![Ícone painel de área de trabalho do Docker](../media/docker-starting.png)

3. Verifique se "usar o mecanismo baseado em WSL 2" está marcado em **configurações**  >  **geral**.
    ![Configurações gerais do Docker desktop](../media/docker-running.png)

4. Selecione as distribuições do WSL 2 instaladas das quais você deseja habilitar a integração com o Docker acessando: **configurações**  >  **recursos**  >  **integração de WSL**.
    ![Configurações de recurso de área de trabalho do Docker](../media/docker-dashboard.png)

5. Para confirmar se o Docker foi instalado, abra uma distribuição WSL (por exemplo, Ubuntu) e exiba a versão e o número da compilação digitando: `docker --version`

6. Teste se a instalação funciona corretamente executando uma imagem interna do Docker simples usando: `docker run hello-world`

> [!TIP]
> Aqui estão alguns comandos úteis do Docker para saber:
>
> - Liste os comandos disponíveis na CLI do Docker digitando: `docker`
> - Listar informações para um comando específico com: `docker <COMMAND> --help`
> - Liste as imagens do Docker em seu computador (que é apenas a imagem Hello-World neste ponto), com: `docker image ls --all`
> - Listar os contêineres em seu computador, com: `docker container ls --all` ou `docker ps -a` (sem o sinalizador-a mostrar todos, somente contêineres em execução serão exibidos)
> - Listar informações de todo o sistema sobre a instalação do Docker, incluindo estatísticas e recursos (CPU & memória) disponíveis no contexto WSL 2, com: `docker info`

## <a name="develop-in-remote-containers-using-vs-code"></a>Desenvolver em contêineres remotos usando VS Code

Para começar a desenvolver aplicativos usando o Docker com o WSL 2, é recomendável usar VS Code, juntamente com a extensão WSL e a extensão do Docker.

- [Instale o vs Code extensão Remote-WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl). Essa extensão permite que você abra seu projeto do Linux em execução no WSL no VS Code (não há necessidade de se preocupar com problemas de caminhos, compatibilidade binária ou outros desafios entre sistemas operacionais).

- [Instale a extensão de contêineres remotos do vs Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers). Essa extensão permite que você abra a pasta do projeto ou o repositório dentro de um contêiner, aproveitando o conjunto de recursos completo do Visual Studio Code para fazer seu trabalho de desenvolvimento dentro do contêiner.

- [Instale a extensão do docker vs Code](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker). Essa extensão adiciona a funcionalidade para compilar, gerenciar e implantar aplicativos em contêineres de dentro VS Code. (Você precisa da extensão de contêiner remoto para realmente usar o contêiner como seu ambiente de desenvolvimento.)

Vamos usar o Docker para criar um contêiner de desenvolvimento para um projeto de aplicativo existente.

1. Para este exemplo, usarei o código-fonte do meu [tutorial de Olá, mundo para Django](https://docs.microsoft.com/windows/python/web-frameworks#hello-world-tutorial-for-django) no ambiente de desenvolvimento do Python configurar documentos. Você pode ignorar esta etapa se preferir usar seu próprio código-fonte do projeto. Para baixar meu aplicativo Web HelloWorld-Django do GitHub, abra um terminal WSL (Ubuntu, por exemplo) e digite: `git clone https://github.com/mattwojo/helloworld-django.git`

    > [!NOTE]
    > Sempre armazene seu código no mesmo sistema de arquivos no qual você está usando ferramentas. Isso resultará em um desempenho mais rápido de acesso a arquivos. Neste exemplo, estamos usando um Linux distribuição (Ubuntu) e desejamos armazenar nossos arquivos de projeto no sistema de arquivos WSL `\\wsl\` . O armazenamento de arquivos de projeto no sistema de arquivos do Windows reduziria significativamente as coisas ao usar as ferramentas do Linux no WSL para acessar esses arquivos.

2. No terminal do WSL, altere os diretórios para a pasta de código-fonte deste projeto:

    ```bash
    cd helloworld-django
    ```

3. Abra o projeto no VS Code em execução no servidor de extensão de WSL remoto local digitando:

    ```bash
    code .
    ```

    Confirme se você está conectado ao WSL Linux distribuição verificando o indicador remoto verde no canto inferior esquerdo da sua instância de VS Code.

    ![Indicador remoto do VS Code WSL](../media/vscode-remote-indicator.png)

4. Na VS Code do comando Pallette (Ctrl + Shift + P), digite: **contêineres remotos: abrir pasta no contêiner...** Se esse comando não for exibido conforme você começar a digitá-lo, verifique se você instalou a extensão de contêiner remoto vinculada acima.

    ![VS Code comando de contêiner remoto](../media/docker-extension.png)

5. Selecione a pasta do projeto que você deseja colocar em contêineres. No meu caso, isso é `\\wsl\Ubuntu-20.04\home\mattwojo\repos\helloworld-django\`

    ![VS Code pasta de contêiner remoto](../media/docker-extension2.png)

6. Uma lista de definições de contêiner será exibida, pois não há nenhuma configuração de DevContainer na pasta do projeto (repositório) ainda. A lista de definições de configuração de contêiner que aparece é filtrada com base em seu tipo de projeto. Para meu projeto Django, selecionarei o Python 3.

    ![VS Code definições de configuração de contêiner remoto](../media/docker-extension3.png)

7. Uma nova instância do VS Code será aberta, começará a criar nossa nova imagem e, depois que a compilação for concluída, iniciará nosso contêiner. Você verá que uma nova `.devcontainer` pasta apareceu com informações de configuração de contêiner dentro de `Dockerfile` um `devcontainer.json` arquivo e.  

    ![Pasta VS Code. devcontainer](../media/docker-extension4.png)

8. Para confirmar que seu projeto ainda está conectado a ambos os WSL e dentro de um contêiner, abra o terminal integrado VS Code (Ctrl + Shift + ~). Verifique o sistema operacional digitando: `uname` e a versão do Python com: `python3 --version` . Você pode ver que uname voltou a "Linux", então você ainda está conectado ao mecanismo WSL 2 e o número de versão do Python será baseado na configuração do contêiner que pode ser diferente da versão do Python instalada em sua distribuição do WSL.

9. Para executar e depurar seu aplicativo dentro do contêiner usando Visual Studio Code, primeiro abra o menu **executar** (Ctrl + Shift + D ou selecione a guia na barra de menus da extrema esquerda). Em seguida, selecione **executar e depurar** para selecionar uma configuração de depuração e escolha a configuração que melhor suites seu projeto (no meu exemplo, será "Django"). Isso criará um `launch.json` arquivo na `.vscode` pasta do seu projeto com instruções sobre como executar seu aplicativo.

    ![VS Code executar a configuração de depuração](../media/vscode-run-config.png)

10. De dentro vs Code, selecione **executar**  >  **Iniciar Depuração** (ou apenas pressione a tecla **F5** ). Isso abrirá um terminal dentro de VS Code e você verá um resultado que diz algo como: "Iniciando o servidor de desenvolvimento em http://127.0.0.1:8000/ sair do servidor com Control-C". Mantenha a tecla Control pressionada e selecione o endereço exibido para abrir seu aplicativo no navegador da Web padrão e veja seu projeto em execução dentro de seu contêiner.

    ![VS Code executando um contêiner do Docker](../media/vscode-running-in-container.png)

Agora você configurou com êxito um contêiner de desenvolvimento remoto usando o Docker desktop, equipado com o back-end WSL 2, que pode ser codificado, compilado, executado, implantado ou depure usando VS Code!

## <a name="troubleshooting"></a>Solução de problemas

### <a name="wsl-docker-context-deprecated"></a>Contexto do Docker WSL preterido

Se você estava usando uma versão prévia de Tech do Docker para WSL, você pode ter um contexto de Docker chamado "WSL" que agora está preterido e não mais usado. Você pode verificar com o comando: `docker context ls` . Você pode remover esse contexto "WSL" para evitar erros com o comando: `docker context rm wsl` como você deseja usar o contexto padrão para Windows e WSL2.

Possíveis erros que você pode encontrar com esse contexto WSL preterido incluem: `docker wsl open //./pipe/docker_wsl: The system cannot find the file specified.` ou `error during connect: Get http://%2F%2F.%2Fpipe%2Fdocker_wsl/v1.40/images/json?all=1: open //./pipe/docker_wsl: The system cannot find the file specified.`

Para obter mais informações sobre esse problema, consulte [como configurar o Docker no sistema Windows para Linux (WSL2) no Windows 10](https://www.hanselman.com/blog/HowToSetUpDockerWithinWindowsSystemForLinuxWSL2OnWindows10.aspx).

### <a name="trouble-finding-docker-image-storage-folder"></a>Problema ao localizar a pasta de armazenamento de imagem do Docker

O Docker cria duas pastas distribuição para armazenar dados:
- \\WSL $ \docker-desktop
- \\WSL $ \docker-desktop-data

Você pode encontrar essas pastas abrindo sua distribuição do WSL Linux e inserindo: `explorer.exe .` para exibir a pasta no explorador de arquivos do Windows. Enter: `\\wsl\<distro name>\mnt\wsl` substituindo `<distro name>` pelo nome da sua distribuição (por ex. Ubuntu-20, 4) para ver essas pastas.

Saiba mais sobre como localizar locais de armazenamento do Docker no WSL, consulte esse [problema no repositório do WSL](https://github.com/microsoft/WSL/issues/4176) ou nesta [postagem de StackOverlow](https://stackoverflow.com/questions/62380124/where-docker-image-is-stored-with-docker-desktop-for-windows).

Para obter mais ajuda com problemas de solução de problemas gerais no WSL, consulte o documento de [solução de problemas](../troubleshooting.md) .

## <a name="additional-resources"></a>Recursos adicionais

- [Documentos do Docker: práticas recomendadas para área de trabalho do Docker com WSL 2](https://docs.docker.com/docker-for-windows/wsl/#best-practices)
- [Comentários para o Docker desktop para Windows: arquivo um problema](https://github.com/docker/for-win/issues)
- [Blog VS Code: Diretrizes para escolher um ambiente de desenvolvimento](https://code.visualstudio.com/docs/containers/choosing-dev-environment#_guidelines-for-choosing-a-development-environment)
- [Blog VS Code: usando o Docker no WSL 2](https://code.visualstudio.com/blogs/2020/03/02/docker-in-wsl2)
- [Blog VS Code: usando contêineres remotos no WSL 2](https://code.visualstudio.com/blogs/2020/07/01/containers-wsl)
- [Podcast Hanselminutes: tornando o Docker adorável para desenvolvedores com Simon Ferquel](https://hanselminutes.com/736/making-docker-lovely-for-developers-with-simon-ferquel)
