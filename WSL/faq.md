---
title: Perguntas frequentes (FAQ)
description: Encontre respostas para perguntas frequentes sobre o Subsistema do Windows para Linux, como 'O que posso fazer com o WSL?'.
keywords: BashOnWindows, bash, wsl, windows, windowssubsystem, faq
ms.date: 09/15/2020
ms.topic: article
ms.assetid: 129101ed-b88a-43c2-b6a2-cd2c4ff6fee1
ms.localizationpriority: high
ms.openlocfilehash: f769261bab35619b034e2a84e4f308eeb0a93cb4
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413236"
---
# <a name="frequently-asked-questions-about-windows-subsystem-for-linux"></a>Perguntas frequentes sobre o Subsistema Windows para Linux

## <a name="what-is-windows-subsystem-for-linux-wsl"></a>O que é o WSL (Subsistema Windows para Linux)?

O Subsistema Windows para Linux (WSL) é um novo recurso do Windows 10 que habilita e execução de ferramentas de linha de comando nativas do Linux diretamente no Windows, juntamente com sua área de trabalho tradicional do Windows e os aplicativos de loja modernos.

Consulte a [página Sobre](./about.md) para obter mais detalhes.

## <a name="who-is-wsl-for"></a>Para quem é o WSL?

Ela é basicamente uma ferramenta para desenvolvedores – especialmente desenvolvedores da Web e aqueles que trabalham em ou com projetos de software livre. Isso permite que aqueles que desejam/precisam usar Bash, ferramentas comuns do Linux (`sed`, `awk`, etc.) e muitas linguagens para Linux (Ruby, Python, etc.) usem suas cadeias de ferramentas no Windows.

## <a name="what-can-i-do-with-wsl"></a>O que posso fazer com o WSL?

O WSL fornece um aplicativo chamado Bash.exe que, quando iniciado, abre um console do Windows que executa o shell Bash. Usando o Bash, você pode executar aplicativos e ferramentas de linha de comando do Linux. Por exemplo, digite `lsb_release -a` e pressione Enter. Você verá os detalhes da distribuição do Linux em execução no momento:

![Captura de tela dos detalhes da distribuição](media/distro.png)

Você também pode acessar o sistema de arquivos do computador local de dentro do shell do Linux Bash – você encontrará as unidades locais montadas na pasta `/mnt`. Por exemplo, sua unidade `C:` está montada em `/mnt/c`:  

![Captura de tela da unidade C montada](media/ls.png)

## <a name="could-you-describe-a-typical-development-workflow-that-incorporates-wsl"></a>Você poderia descrever um fluxo de trabalho de desenvolvimento típico que incorpora o WSL?

O WSL é destinado a desenvolvedores, com a intenção de ser usado como parte de um loop de desenvolvimento interno. Digamos que Pedro esteja criando um pipeline de CI/CD (integração contínua e entrega contínua) e queira testá-lo primeiro em um computador local (laptop) antes de implantá-lo na nuvem. O Pedro poderá habilitar o WSL (e o WSL 2 para melhorar a velocidade e o desempenho) e, em seguida, usar uma instância do Linux Ubuntu autêntica localmente (no laptop) com quaisquer comandos e ferramentas de bash que preferir. Depois de verificar o pipeline de desenvolvimento localmente, Pedro pode enviar por push esse pipeline de CI/CD para a nuvem (ou seja, para o Azure), colocando-o em um contêiner do Docker e enviando o contêiner para uma instância de nuvem em que ele é executado em uma VM Ubuntu pronta para produção.

## <a name="what-is-bash"></a>O que é o Bash?

O [Bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) é uma linguagem de comando e shell baseado em texto popular. É o shell padrão incluído no Ubuntu e em outras distribuições do Linux e no macOS. Os usuários digitam comandos em um shell para executar scripts e/ou executar comandos e ferramentas para realizar muitas tarefas.

## <a name="how-does-this-work"></a>Como isso funciona?

Confira nosso [blog](/archive/blogs/wsl/) com os detalhes sobre a tecnologia subjacente.

## <a name="why-would-i-use-wsl-rather-than-linux-in-a-vm"></a>Por que usar o WSL em vez do Linux em uma VM?

O WSL requer menos recursos (CPU, memória e armazenamento) do que uma máquina virtual completa. O WSL também permite que você execute aplicativos e ferramentas de linha de comando do Linux juntamente com os aplicativos de linha de comando, da área de trabalho e da loja do Windows, além de acessar os arquivos do Windows de dentro do Linux. Isso habilita você a usar aplicativos do Windows e ferramentas de linha de comando do Linux no mesmo conjunto de arquivos, se desejar.

## <a name="why-would-i-use-for-example-ruby-on-linux-instead-of-on-windows"></a>Por que eu usaria, por exemplo, o Ruby no Linux em vez de no Windows?

Algumas ferramentas multiplataforma foram criadas supondo que o ambiente no qual elas são executadas se comporta como o Linux. Por exemplo, algumas ferramentas pressupõem que elas são capazes de acessar caminhos de arquivo muito longos ou que arquivos/pastas específicos existam. Isso geralmente causa problemas no Windows que, com frequência, se comporta de forma diferente do Linux.

Muitas linguagens, como Ruby e Node, costumam ser modeladas e funcionam muito bem no Windows. No entanto, nem todos os proprietários do Ruby Gem ou de bibliotecas do Node/NPM têm suas bibliotecas para dar suporte ao Windows e muitos têm dependências específicas do Linux. Isso geralmente pode resultar em sistemas criados usando ferramentas e bibliotecas com problemas de build e, às vezes, erros de runtime ou comportamentos indesejados no Windows.

Esses são apenas alguns dos problemas que fizeram com que muitas pessoas pedissem à Microsoft para aprimorar as ferramentas de linha de comando do Windows e o que nos levou a fazer parcerias com a Canonical para habilitar as ferramentas de linha de comando do Linux e do Bash nativas para serem executadas no Windows.

## <a name="what-does-this-mean-for-powershell"></a>O que isso significa para o PowerShell?

Ao trabalhar com projetos OSS, há inúmeros cenários em que é imensamente útil entrar no Bash usando um prompt do PowerShell. O suporte para Bash é complementar e fortalece o valor da linha de comando no Windows, permitindo que o PowerShell e a comunidade do PowerShell aproveitem outras tecnologias populares.

Leia mais no blog da equipe do PowerShell – [Bash para Windows: por que é incrível e o que significa para o PowerShell](https://blogs.msdn.microsoft.com/powershell/2016/04/01/bash-for-windows-why-its-awesome-and-what-it-means-for-powershell/)

## <a name="can-i-run-all-linux-apps-in-wsl"></a>Posso executar TODOS os aplicativos do Linux no WSL?

Não. O WSL é uma ferramenta que habilita os usuários a executar as principais ferramentas de linha de comando do Bash e do Linux no Windows.

O WSL **NÃO** é compatível com aplicativos ou áreas de trabalho de GUI (por exemplo, Gnome, KDE, etc.)  

Além disso, embora você possa executar muitos aplicativos de servidor populares (por exemplo, Redis), não recomendamos o WSL para hospedar serviços de produção – a Microsoft oferece uma variedade de soluções para executar cargas de trabalho de produção do Linux no Azure, no Hyper-V e no Docker. 

## <a name="what-windows-skus-is-wsl-included-in"></a>Em quais SKUs do Windows o WSL está incluído?

O Subsistema Windows para Linux está disponível na versão de área de trabalho do Windows para a Atualização de Aniversário do Windows 10 e a Atualização do Windows 10 para Criadores ou posterior.

Iniciando na Fall Creators Update, o WSL estará disponível nas SKUs de desktop e de servidor do Windows.

## <a name="what-processors-does-wsl-support"></a>Com quais processadores o WSL é compatível?

O WSL é compatível com CPUs x64 e ARM.

## <a name="how-do-i-access-my-c-drive"></a>Como acesso minha unidade C:?

Pontos de montagem para discos rígidos no computador local são criados automaticamente e fornecem acesso fácil ao sistema de arquivos do Windows.

**/mnt/\<drive letter>/**

Um uso de exemplo seria `cd /mnt/c` para acessar c:\

## <a name="how-do-i-set-up-git-credential-manager-how-do-i-use-my-windows-git-permissions-in-wsl"></a>Como configurar o Gerenciador de Credenciais do Git? (Como usar as permissões do Git do Windows no WSL?) 

O Gerenciador de Credenciais do Git permite autenticar um servidor Git remoto, mesmo se você tem um padrão de autenticação complexo como o Azure Active Directory ou a autenticação de dois fatores. O Gerenciador de Credenciais do Git se integra ao fluxo de autenticação para serviços como o GitHub e, uma vez que você está autenticado no provedor de hospedagem, solicita um novo token de autenticação. Em seguida, armazena o token com segurança no Gerenciador de Credenciais do Windows. Após a primeira vez, você pode usar o Git para se comunicar com seu provedor de hospedagem sem a necessidade de uma nova autenticação. Ele só acessará o token no Gerenciador de Credenciais do Windows.

Para configurar o Gerenciador de Credenciais do Git para uso com uma distribuição do WSL, abra a distribuição e insira este comando:

```Bash
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe"
```

Agora, todas as operações de git realizadas na distribuição do WSL usarão o Gerenciador de Credenciais. Se você já tiver credenciais armazenadas em cache para um host, elas serão acessadas do Gerenciador de Credenciais. Caso contrário, você receberá uma resposta em uma caixa de diálogo solicitando suas credenciais, mesmo que esteja em um console do Linux.

Esse suporte depende da [interoperabilidade entre o Subsistema do Windows para Linux e o próprio Windows](./interop.md).

## <a name="how-do-i-use-a-windows-file-with-a-linux-app"></a>Como uso um arquivo do Windows com um aplicativo do Linux?

Um dos benefícios do WSL é a capacidade de acessar seus arquivos por meio de aplicativos ou ferramentas do Windows e do Linux. 

O WSL monta as unidades fixas do computador na pasta `/mnt/<drive>` em suas distribuições do Linux. Por exemplo, sua unidade `C:` está montada em `/mnt/c/`

Usando suas unidades montadas, você pode editar o código, por exemplo, `C:\dev\myproj\` usando o [Visual Studio](https://visualstudio.microsoft.com/vs/) ou o [VS Code](https://code.visualstudio.com/), e criar/testar esse código no Linux acessando os mesmos arquivos por meio do `/mnt/c/dev/myproj`.

> **OBSERVAÇÃO IMPORTANTE**: Uma das principais limitações do uso do WSL é que o acesso/alteração direta de arquivos em seu sistema de arquivos das distribuições do Linux usando aplicativos ou ferramentas do Windows não é compatível. Consulte: [Não altere os arquivos do Linux usando ferramentas e aplicativos do Windows](https://blogs.msdn.microsoft.com/commandline/2016/11/17/do-not-change-linux-files-using-windows-apps-and-tools/)

## <a name="are-files-in-the-linux-drive-different-from-the-mounted-windows-drive"></a>Os arquivos na unidade do Linux são diferentes da unidade montada do Windows?

1. Os arquivos na raiz do Linux (por exemplo, `/`) são controlados pelo WSL, que imita o comportamento específico do Linux, incluindo, sem limitações:
   * Arquivos que contêm caracteres de nome de arquivo do Windows inválidos
   * Symlinks criados para usuários não administradores
   * Como alterar atributos de arquivo usando chmod e chown
   * Diferenciação de maiúsculas e minúsculas de arquivo/pasta

2. Os arquivos em unidades montadas são controlados pelo Windows e têm os seguintes comportamentos:
   * Suporte à diferenciação de maiúsculas e minúsculas
   * Todas as permissões são definidas para refletir melhor as permissões do Windows

## <a name="why-are-there-so-many-errors-when-i-run-apt-get-upgrade"></a>Por que há muitos erros quando executo a atualização apt-get?

Alguns pacotes usam recursos que ainda não implementamos. `udev`, por exemplo, ainda não é compatível e causa vários erros de `apt-get upgrade`.

Para corrigir problemas relacionados ao `udev`, siga as seguintes etapas:

1. Grave o seguinte no `/usr/sbin/policy-rc.d` e salve suas alterações.

    ```bash
    #!/bin/sh
    exit 101
    ```

2. Adicione permissões de execução a `/usr/sbin/policy-rc.d`

    ```bash
    chmod +x /usr/sbin/policy-rc.d
    ```
  
3. Execute os comandos a seguir

    ```bash
    dpkg-divert --local --rename --add /sbin/initctl
    ln -s /bin/true /sbin/initctl
    ```

## <a name="how-do-i-uninstall-a-wsl-distribution"></a>Como desinstalar uma distribuição WSL?

Em builds anteriores ao 1709 (16299), abra um prompt de comando e execute:

  ```batchfile
  lxrun /uninstall /full
  ```
  
As distribuições do WSL instaladas no repositório podem ser desinstaladas como qualquer outro aplicativo do Windows clicando com o botão direito do mouse no bloco do aplicativo e clicando em Desinstalar ou por meio do PowerShell usando o cmdlet [`Remove-AppxPackage`](/previous-versions//hh856038(v=technet.10)).

## <a name="why-does-ping-generate-permission-denied-errors"></a>Por que o ping gera erros de permissão negada?

Nos builds do WLS anteriores ao 14926, o ping exigia que o WSL fosse executado usando um console elevado. Esse problema foi corrigido no Build 14926 e posterior.

## <a name="how-do-i-run-an-openssh-server"></a>Como executar um servidor OpenSSH?

São necessários privilégios de administrador no Windows para executar o OpenSSH no WSL. Para executar o servidor OpenSSH, execute o Bash do Ubuntu no Windows como administrador ou execute bash.exe em um prompt do CMD/PowerShell com privilégios de administrador.

## <a name="why-do-i-get-error-0x80040306-when-i-try-to-install"></a>Por que obtenho "Erro: 0x80040306"quando tento instalar?

O WSL não é compatível com a execução em um console herdado. Para desligar o console herdado:

1. Abra o WSL, o PowerShell ou o Cmd
1. Clique com o botão direito do mouse na barra de título-> Propriedades-> desmarque “Usar console herdado”
1. Clique em OK

## <a name="why-do-i-get-error-0x80040154-when-i-run-bashexe-after-upgrading-windows"></a>Por que obtenho "Erro: 0x80040154" quando executo o bash.exe após a atualização do Windows?

O recurso “Subsistema Windows para Linux” pode ser desabilitado durante uma atualização do Windows. Se isso acontecer, o recurso do Windows deverá ser habilitado novamente. As instruções para habilitar o recurso “Subsistema Windows para Linux” podem ser encontradas no [Guia de instalação](./install-win10.md).

## <a name="how-do-i-change-the-display-language-of-wsl"></a>Como alterar o idioma de exibição do WSL?

A instalação do WSL tentará alterar automaticamente a localidade do Ubuntu para corresponder à localidade da instalação do Windows. Se você não quiser esse comportamento, poderá executar esse comando para alterar a localidade do Ubuntu após a conclusão da instalação. Você precisará reiniciar o bash.exe para que essa alteração entre em vigor.

O exemplo abaixo altera a localidade para en-US:

```bash
sudo update-locale LANG=en_US.UTF8
```

## <a name="why-do-i-not-have-internet-access-from-wsl"></a>Por que não tenho acesso à Internet do WSL?

Alguns usuários relataram problemas com aplicativos de firewall específicos que bloqueiam o acesso à Internet no WSL. Os firewalls relatados são:

1. Kaspersky
1. AVG
1. Avast

Em alguns casos, desligar o firewall permite o acesso. Em outros, simplesmente ter o firewall instalado bloqueia o acesso.

## <a name="how-do-i-access-a-port-from-wsl-in-windows"></a>Como acessar uma porta do WSL no Windows?
O WSL compartilha o endereço IP do Windows, pois ele é executado no Windows. Assim, você pode acessar qualquer porta no localhost, por exemplo, se você tivesse conteúdo da Web na porta 1234, poderia https://localhost:1234 no seu navegador do Windows.

## <a name="how-can-i-back-up-my-wsl-distros-or-move-them-from-one-drive-to-another"></a>Como fazer backup das distribuições do WSL ou movê-las de uma unidade para outra?

A melhor maneira de fazer backup das distribuições ou movê-las é por meio dos comandos de exportação/importação disponíveis no Windows, versão 1809 e posteriores. Você pode exportar toda a distribuição para um tarball usando o comando `wsl --export`. Em seguida, importe essa distribuição novamente para o WSL usando o comando `wsl --import`, que pode nomear um novo local de unidade para a importação, permitindo que você faça backup dos estados das distribuições do WSL ou salve-os (ou mova-os). 

Observe que os serviços de backup tradicionais que fazem backup de arquivos em suas pastas AppData (como o backup do Windows) não corromperão os arquivos do Linux.

## <a name="where-can-i-provide-feedback"></a>Onde posso fornecer comentários?

É possível compartilhar comentários e fazer perguntas por meio de vários canais.

Se você tiver problemas técnicos ou desejar solicitar novos recursos, acesse o rastreador de problemas do GitHub:

* [Rastreador de problemas do GitHub](https://github.com/Microsoft/BashOnWindows/issues)

Se você quiser ficar por dentro das últimas notícias do WSL, acesse:

* Nosso [blog da equipe de linha de comando](https://blogs.msdn.microsoft.com/commandline/)
* O Twitter. Siga [@craigaloewen](https://twitter.com/craigaloewen) no Twitter para saber mais sobre as novidades, atualizações, etc.