---
title: Gerenciar as distribuições do Linux
description: Listagem de referência e configuração de várias distribuições do Linux em execução no Subsistema Windows para Linux.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, wsl.conf, wslconfig
ms.date: 05/12/2020
ms.topic: article
ms.openlocfilehash: 0a127d376a8606a1a13ea88c9efed161e18a161d
ms.sourcegitcommit: 69fc9d3ca22cf3f07622db4cdf80c8ec751fe620
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90818728"
---
# <a name="wsl-commands-and-launch-configurations"></a>Comandos do WSL e configurações de inicialização

## <a name="ways-to-run-wsl"></a>Maneiras de executar o WSL

Há várias maneiras de executar uma distribuição do Linux com o WSL depois que ele é [instalado](install-win10.md).

1. Abra sua distribuição do Linux visitando o menu Iniciar do Windows e digitando o nome de suas distribuições instaladas. Por exemplo: "Ubuntu".
2. No prompt de comando do Windows ou no PowerShell, insira o nome da sua distribuição instalada. Por exemplo: `ubuntu`
3. No prompt de comando do Windows ou no PowerShell, para abrir sua distribuição do Linux padrão dentro da linha de comando atual, digite: `wsl.exe` .
4. No prompt de comando do Windows ou no PowerShell, para abrir sua distribuição do Linux padrão dentro da linha de comando atual, digite: `wsl [command]` .

Qual método deve ser usado depende do que você está fazendo. Se você tiver aberto uma linha de comando WSL em um prompt do Windows ou janela do PowerShell e quiser sair, insira o comando: `exit` .

## <a name="launch-wsl-by-distribution"></a>Iniciar o WSL por distribuição

A execução de uma distribuição usando o aplicativo específico da distribuição inicia essa distribuição na própria janela do console.

![Iniciar o WSL no menu Iniciar](media/start-launch.png)

É o mesmo que clicar em "Iniciar" na Microsoft Store.

![Iniciar o WSL usando a Microsoft Store](media/store-launch.png)

Você também pode executar a distribuição na linha de comando executando `[distribution].exe`.

A desvantagem de executar uma distribuição da linha de comando dessa forma é que ela alterará automaticamente seu diretório de trabalho do diretório atual para o diretório base da distribuição.

**Exemplo: (usando o PowerShell)**

```console
PS C:\Users\sarah> pwd

Path
----
C:\Users\sarah

PS C:\Users\sarah> ubuntu

scooley@scooley-elmer:~$ pwd
/home/scooley
scooley@scooley-elmer:~$ exit
logout

PS C:\Users\sarah>
```

### <a name="wsl-and-wsl-command"></a>wsl e wsl [comando]

A melhor maneira de executar o WSL na linha de comando é usando o `wsl.exe`.

**Exemplo: (usando o PowerShell)**

```console
PS C:\Users\sarah> pwd

Path
----
C:\Users\sarah

PS C:\Users\sarah> wsl

scooley@scooley-elmer:/mnt/c/Users/sarah$ pwd
/mnt/c/Users/sarah
```

O `wsl` não apenas mantém o diretório de trabalho atual em vigor, como também permite que você execute um único comando ao longo dos comandos do Windows.

**Exemplo: (usando o PowerShell)**

```console
PS C:\Users\sarah> Get-Date

Sunday, March 11, 2018 7:54:05 PM

PS C:\Users\sarah> wsl
scooley@scooley-elmer:/mnt/c/Users/sarah$ date
Sun Mar 11 19:55:47 DST 2018
scooley@scooley-elmer:/mnt/c/Users/sarah$ exit
logout

PS C:\Users\sarah> wsl date
Sun Mar 11 19:56:57 DST 2018
```

**Exemplo: (usando o PowerShell)**

```console
PS C:\Users\sarah> Get-VM

Name            State CPUUsage(%) MemoryAssigned(M) Uptime   Status
----            ----- ----------- ----------------- ------   ------
Server17093     Off   0           0                 00:00:00 Opera...
Ubuntu          Off   0           0                 00:00:00 Opera...
Ubuntu (bionic) Off   0           0                 00:00:00 Opera...
Windows         Off   0           0                 00:00:00 Opera...


PS C:\Users\sarah> Get-VM | wsl grep "Ubuntu"
Ubuntu          Off   0           0                 00:00:00 Opera...
Ubuntu (bionic) Off   0           0                 00:00:00 Opera...
PS C:\Users\sarah>
```

## <a name="managing-multiple-linux-distributions"></a>Como gerenciar várias distribuições do Linux

No Windows 10 versão 1903 [e posterior](ms-settings:windowsupdate), você pode usar o `wsl.exe` para gerenciar suas distribuições no subsistema do Windows para Linux (WSL), incluindo a listagem de distribuições disponíveis, a definição de uma distribuição padrão e a desinstalação de distribuições.

Cada distribuição do Linux gerencia de forma independente suas próprias configurações. Para ver comandos específicos de distribuição, execute `[distro.exe] /?`.  Por exemplo, `ubuntu /?`.

## <a name="list-distributions"></a>Listar distribuições

`wsl -l` , `wsl --list`  
Lista as distribuições do Linux disponíveis para WSL.  Se uma distribuição estiver listada, ela será instalada e estará pronta para uso.

`wsl --list --all` Lista todas as distribuições, incluindo aquelas que não são utilizáveis no momento.  Elas podem estar no processo de instalação, desinstalação ou em um estado desfeito.  

`wsl --list --running` Lista todas as distribuições que estão em execução no momento.

## <a name="set-a-default-distribution"></a>Definir uma distribuição padrão

A distribuição do WSL padrão é aquela que é executada quando você executa `wsl` em uma linha de comando.

`wsl -s <DistributionName>`, `wsl --setdefault <DistributionName>`

Define uma distribuição padrão para `<DistributionName>`.

**Exemplo: (usando o PowerShell)**  
`wsl -s Ubuntu` definiria minha distribuição padrão como Ubuntu.  Agora, quando eu executar o `wsl npm init`, ele será executado no Ubuntu.  Se eu executar `wsl`, ele abrirá uma sessão do Ubuntu.

## <a name="unregister-and-reinstall-a-distribution"></a>Cancelar o registro e reinstalar uma distribuição

Embora as distribuições do Linux possam ser instaladas por meio da Microsoft Store, elas não podem ser desinstaladas usando a loja.  O WSL Config permite que as distribuições tenham o registro cancelado/sejam desinstaladas.

O cancelamento do registro também permite que as distribuições sejam reinstaladas.

> **Cuidado:** Após o registro, todos os dados, as configurações e os softwares associados a essa distribuição serão permanentemente perdidos.  A reinstalação pela loja instalará uma cópia limpa da distribuição.

`wsl --unregister <DistributionName>`  
Cancela o registro da distribuição do WSL para que possa ser reinstalado ou limpo.

Por exemplo, `wsl --unregister Ubuntu` removeria o Ubuntu das distribuições disponíveis no WSL.  Quando eu executar `wsl --list`, ele não será listado.

Para reinstalar, localize a distribuição na Microsoft Store e selecione "Iniciar".

## <a name="run-as-a-specific-user"></a>Execute como um usuário específico

`wsl -u <Username>`, `wsl --user <Username>`

Execute o WSL como o usuário especificado. Observe que o usuário deve existir dentro da distribuição do WSL.

## <a name="change-the-default-user-for-a-distribution"></a>Alterar o usuário padrão para uma distribuição

`<DistributionName> config --default-user <Username>`

Altere o usuário padrão para o seu logon de distribuição. O usuário já deve existir dentro da distribuição para se tornar o usuário padrão. 

Por exemplo: `ubuntu config --default-user johndoe` alteraria o usuário padrão para a distribuição do Ubuntu para o usuário "davibarros".

> [!NOTE]
> Se você estiver tendo problemas para descobrir o nome da sua distribuição, consulte [listar distribuições](https://docs.microsoft.com/windows/wsl/wsl-config#list-distributions) para o comando para listar o nome oficial das distribuições instaladas. 

## <a name="run-a-specific-distribution"></a>Executar uma distribuição específica

`wsl -d <DistributionName>`, `wsl --distribution <DistributionName>`

A execução de uma distribuição especificada do WSL pode ser usada para enviar comandos para uma distribuição específica sem precisar alterar o padrão.

## <a name="managing-multiple-linux-distributions-in-earlier-windows-versions"></a>Gerenciando várias distribuições Linux em versões anteriores do Windows

No Windows 10 antes da versão 1903, a ferramenta de linha de comando WSL config ( `wslconfig.exe` ) deve ser usada para gerenciar as distribuições do Linux em execução no subsistema do Windows para Linux (WSL).  Ele permite que você liste as distribuições disponíveis, defina uma distribuição padrão e desinstale as distribuições.

Embora o WSL Config seja útil para configurações que abrangem ou coordenam distribuições, cada distribuição do Linux gerencia de forma independente suas próprias configurações.  Para ver comandos específicos de distribuição, execute `[distro.exe] /?`.  Por exemplo, `ubuntu /?`.

Para ver todas as opções disponíveis para wslconfig, execute: `wslconfig /?`

```console
wslconfig.exe
Performs administrative operations on Windows Subsystem for Linux

Usage:
    /l, /list [/all] - Lists registered distributions.
        /all - Optionally list all distributions, including distributions that
               are currently being installed or uninstalled.
    /s, /setdefault <DistributionName> - Sets the specified distribution as the default.
    /u, /unregister <DistributionName> - Unregisters a distribution.
```

Para listar distribuições, use:

`wslconfig /list`  
Lista as distribuições do Linux disponíveis para WSL.  Se uma distribuição estiver listada, ela será instalada e estará pronta para uso.

`wslconfig /list /all`  
Lista todas as distribuições, incluindo aquelas que não são utilizáveis no momento.  Elas podem estar no processo de instalação, desinstalação ou em um estado desfeito.  

Para definir uma distribuição padrão que é executada quando você executa `wsl` em uma linha de comando:

`wslconfig /setdefault <DistributionName>` Define a distribuição padrão como `<DistributionName>` .

**Exemplo: (usando o PowerShell)**  
`wslconfig /setdefault Ubuntu` definiria minha distribuição padrão como Ubuntu.  Agora, quando eu executar o `wsl npm init`, ele será executado no Ubuntu.  Se eu executar `wsl`, ele abrirá uma sessão do Ubuntu.

Para cancelar o registro e reinstalar uma distribuição:

`wslconfig /unregister <DistributionName>`  
Cancela o registro da distribuição do WSL para que possa ser reinstalado ou limpo.

Por exemplo, `wslconfig /unregister Ubuntu` removeria o Ubuntu das distribuições disponíveis no WSL.  Quando eu executar `wslconfig /list`, ele não será listado.

Para reinstalar, localize a distribuição na Microsoft Store e selecione "Iniciar".

## <a name="configure-per-distro-launch-settings-with-wslconf"></a>Definir configurações de inicialização por distribuição com wslconf

> **Disponível no Windows Build 17093 e posterior**

Configure automaticamente determinadas funcionalidades no WSL que serão aplicadas toda vez que você iniciar o subsistema usando `wsl.conf`.

No momento, isso inclui opções de montagem automática e configuração de rede.

`wsl.conf` está localizado em cada distribuição do Linux no `/etc/wsl.conf`. Se o arquivo não estiver lá, você mesmo poderá criá-lo. O WSL detectará a existência do arquivo e lerá seu conteúdo. Se o arquivo estiver ausente ou malformado (ou seja, formatação de marcação inadequada), o WSL continuará a ser iniciado normalmente.

Aqui está um arquivo de exemplo `wsl.conf` que você pode adicionar a suas distribuições:

```console
# Enable extra metadata options by default
[automount]
enabled = true
root = /windir/
options = "metadata,umask=22,fmask=11"
mountFsTab = false

# Enable DNS – even though these are turned on by default, we'll specify here just to be explicit.
[network]
generateHosts = true
generateResolvConf = true
```

### <a name="configuration-options"></a>Opções de configuração

Para manter as convenções .ini, as chaves são declaradas em uma seção. 

O WSL é compatível com duas seções: `automount` e `network`.

#### <a name="automount"></a>montagem automática

Seção: `[automount]`

| key        | value                          | default      | observações                                                                                                                                                                                                                                                                                                                          |
|:-----------|:-------------------------------|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| habilitado    | booliano                        | verdadeiro         | `true` causa unidades fixas (ou seja, `C:/` ou `D:/`) a ser montado automaticamente com DrvFs em `/mnt`.  `false` significa que as unidades não serão montadas automaticamente, mas você ainda poderá montá-las manualmente ou por meio do `fstab` .                                                                                                             |
| mountFsTab | booliano                        | verdadeiro         | O `true` define o `/etc/fstab` para ser processado no início do WSL. /etc/fstab é um arquivo no qual você pode declarar outros sistemas de arquivos, como um compartilhamento SMB. Assim, você pode montar esses sistemas de arquivos automaticamente no WSL na inicialização.                                                                                                                |
| raiz       | Cadeia de caracteres                         | `/mnt/`      | Define o diretório em que as unidades fixas serão montadas automaticamente. Por exemplo, se tiver um diretório no WSL no `/windir/` e especificá-lo como a raiz, você poderá esperar ver suas unidades fixas montadas em `/windir/c`                                                                                              |
| opções    | lista de valores separados por vírgulas | cadeia de caracteres vazia | Esse valor é acrescentado à cadeia de caracteres de opções padrão de montagem DrvFs. **Somente opções específicas do DrvFs podem ser especificadas.** As opções que o binário de montagem normalmente analisa em um sinalizador não são compatíveis. Se você quiser especificar explicitamente essas opções, deverá incluir todas as unidades para as quais deseja fazer isso em /etc/fstab. |

Por padrão, o WSL define o UID e o GID como o valor do usuário padrão (na distribuição do Ubuntu, o usuário padrão é criado com UID = 1.000, GID = 1.000). Se o usuário especificar uma opção GID ou UID explicitamente por meio dessa chave, o valor associado será substituído. Caso contrário, o valor padrão será sempre acrescentado.

**Observação**: Essas opções são aplicadas como opções de montagem para todas as unidades montadas automaticamente. Para alterar as opções somente para uma unidade específica, use/etc/fstab.

#### <a name="mount-options"></a>Opções de montagem

A configuração de diferentes opções de montagem para unidades do Windows (DrvFs) pode controlar como as permissões de arquivos são calculadas para arquivos do Windows. As seguintes opções estão disponíveis:

| Chave | Descrição | Padrão |
|:----|:----|:----|
|uid| A ID de usuário usada para o proprietário de todos os arquivos | A ID de usuário padrão de sua distribuição WSL (na primeira instalação, o padrão dela é 1000)
|gid| A ID de grupo usada para o proprietário de todos os arquivos | A ID de grupo padrão de sua distribuição WSL (na primeira instalação, o padrão dela é 1000)
|umask | Uma máscara octal de permissões a serem excluídas para todos os arquivos e diretórios | 000
|fmask | Uma máscara octal de permissões a serem excluídas para todos os arquivos | 000
|dmask | Uma máscara octal de permissões a serem excluídas para todos os diretórios | 000

**Observação**: as máscaras de permissão passam por uma operação OR lógica antes de serem aplicadas a arquivos ou diretórios. 

#### <a name="network"></a>rede

Rótulo da seção: `[network]`

| key | value | default | observações|
|:----|:----|:----|:----|
| generateHosts | booliano | `true` | O `true` define o WSL para gerar `/etc/hosts`. O arquivo `hosts` contém um mapa estático do endereço IP correspondente de nomes de host. |
| generateResolvConf | booliano | `true` | O `true` define o WSL para gerar `/etc/resolv.conf`. O `resolv.conf` contém uma lista DNS que é capaz de resolver um determinado nome de host para seu endereço IP. | 

#### <a name="interop"></a>interop

Rótulo da seção: `[interop]`

Essas opções estão disponíveis no Insider Build 17713 e posterior.

| key | value | default | observações|
|:----|:----|:----|:----|
| habilitado | booliano | `true` | Definir essa chave determinará se o WSL dará suporte à inicialização de processos do Windows. |
| appendWindowsPath | booliano | `true` | Definir essa chave determinará se o WSL adicionará elementos de caminho do Windows à variável de ambiente $PATH. |

#### <a name="user"></a>usuário

Rótulo da seção: `[user]`

Essas opções estão disponíveis no Build 18980 e posterior.

| chave | value | default | HDInsight|
|:----|:----|:----|:----|
| default | string | O nome de usuário inicial criado na primeira execução | Definir essa chave especifica qual usuário executar como ao iniciar pela primeira vez uma sessão WSL. |

## <a name="configure-global-options-with-wslconfig"></a>Configurar opções globais com. wslconfig

> **Disponível no Windows Build 19041 e posterior**

Você pode configurar opções de WSL globais colocando um `.wslconfig` arquivo no diretório raiz da pasta Users: `C:\Users\<yourUserName>\.wslconfig` . Muitos desses arquivos estão relacionados ao WSL 2, tenha em mente que talvez seja necessário executar `wsl --shutdown` para desligar a VM do WSL 2 e reiniciar sua instância do WSL para que essas alterações entrem em vigor.

Aqui está um arquivo. wslconfig de exemplo:

```console
[wsl2]
kernel=C:\\temp\\myCustomKernel
memory=4GB # Limits VM memory in WSL 2 to 4 GB
processors=2 # Makes the WSL 2 VM use two virtual processors
```

Esse arquivo pode conter as seguintes opções:

### <a name="wsl-2-settings"></a>Configurações do WSL 2

Rótulo da seção: `[wsl2]`

Essas configurações afetam a VM que alimenta qualquer distribuição WSL 2.

| chave | value | default | HDInsight|
|:----|:----|:----|:----|
| kernel | string | A caixa de entrada fornecida pelo kernel criado pela Microsoft | Um caminho absoluto do Windows para um kernel personalizado do Linux. |
| memória | tamanho | 50% da memória total no Windows ou 8 GB, o que for menor; em builds antes de 20175:80% da memória total no Windows | A quantidade de memória a ser atribuída à VM WSL 2. |
| processadores | número | O mesmo número de processadores no Windows | Quantos processadores atribuir à VM WSL 2. |
| localhostForwarding | booleano | `true` | Booliano especificando se as portas vinculadas ao curinga ou localhost na VM WSL 2 devem ser conectadas do host via localhost: Port. |
| kernelCommandLine | string | Em branco | Argumentos de linha de comando de kernel adicionais. |
| swap | tamanho | 25% do tamanho da memória no Windows arredondado para os GB mais próximos | Quanto espaço de permuta adicionar à VM WSL 2, 0 para nenhum arquivo de permuta. |
| Permuta | string | %USERPROFILE%\AppData\Local\Temp\swap.vhdx | Um caminho absoluto do Windows para o disco rígido virtual de permuta. |

* Observação: esse valor é verdadeiro para a compilação 19041 do Windows e pode ser diferente no Windows Builds no programa pessoas internas

As entradas com o `path` valor devem ser caminhos do Windows com barras invertidas de escape, por exemplo: `C:\\Temp\\myCustomKernel`

As entradas com o `size` valor devem ser um tamanho seguido por uma unidade, por exemplo, `8GB` ou `512MB` .
