---
title: Subsistema Windows para referência de comandos do Linux
description: Confira uma lista de comandos que gerenciam o Subsistema do Windows para Linux, como os argumentos para execução de comandos do Linux.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu
ms.date: 09/15/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 6f98cb7b238e4b38c1a931a0e77e419efbcc319d
ms.sourcegitcommit: ba3399a5ffeffd23551315acd04ea6848d30693b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90719164"
---
# <a name="command-reference-for-windows-subsystem-for-linux"></a>Referência de comandos para o Subsistema Windows para Linux

A melhor maneira de interagir com o Subsistema Windows para Linux é usar o comando `wsl.exe`.

## <a name="set-wsl-2-as-your-default-version"></a>Definir o WSL 2 como sua versão padrão

Execute o seguinte comando no PowerShell para definir o WSL 2 como a versão padrão ao instalar uma nova distribuição do Linux:

```powershell
wsl --set-default-version 2
```

## <a name="set-your-distribution-version-to-wsl-1-or-wsl-2"></a>Definir a versão de distribuição para WSL 1 ou WSL 2

Verifique a versão do WSL atribuída a cada uma das distribuições do Linux instaladas abrindo a linha de comando do PowerShell e inserindo o comando (disponível somente no [Windows Build 19041 ou superiores](ms-settings:windowsupdate)): `wsl -l -v`

```bash
wsl --list --verbose
```

Para definir uma distribuição para ter suporte de qualquer versão do WSL, execute:

```bash
wsl --set-version <distribution name> <versionNumber>
```

Assegure-se de substituir `<distribution name>` pelo nome real da sua distribuição e `<versionNumber>` pelo número '1' ou '2'. Você pode retornar ao WSL 1 a qualquer momento executando o mesmo comando acima, mas substituindo “2” por “1”.

Além disso, se quiser tornar o WSL 2 sua arquitetura padrão, você poderá fazê-lo com este comando:

```bash
wsl --set-default-version 2
```

Isso definirá a versão de qualquer nova distribuição instalada no WSL 2.

## `wsl.exe`

Abaixo está uma lista que contém todas as opções ao usar o `wsl.exe` da versão 1903 do Windows.

Usando: `wsl [Argument] [Options...] [CommandLine]`

### <a name="arguments-for-running-linux-commands"></a>Argumentos para executar comandos do Linux

* **Sem argumentos**

  Se nenhuma linha de comando for fornecida, o wsl.exe iniciará o shell padrão.

* **--exec, -e \<CommandLine>**
  
  Execute o comando especificado sem usar o shell do Linux padrão.

* **--**
  
  Passe a linha de comando restante do modo como ela está.

Os comandos acima também aceitam as seguintes opções:

* **--distribution, -d \<Distro>**

  Execute a distribuição especificada.

* **--user, -u \<UserName>**

  Execute como o usuário especificado.

### <a name="arguments-for-managing-windows-subsystem-for-linux"></a>Argumentos para gerenciar o Subsistema Windows para Linux

* **--export \<Distro> \<FileName>**
  
  Exporta a distribuição para um arquivo tar. O nome de arquivo pode ser "-" para a saída padrão.

* **--import \<Distro> \<InstallLocation> \<FileName>**
  
  Importa o arquivo tar especificado como uma nova distribuição. O nome de arquivo pode ser "-" para a entrada padrão.

* **--list, -l [Options]**
  
  Lista as distribuições.

  Opções:
  * **--all**

    Liste todas as distribuições, incluindo distribuições que estão sendo instaladas ou desinstaladas no momento.

  * **--running**

    Liste somente as distribuições que estão em execução no momento.

* **--set-default, -s \<Distro>**
  
  Define a distribuição como o padrão.

* **--terminate, -t \<Distro>**
  
  Termina a distribuição especificada.

* **--unregister \<Distro>**
  
  Cancelar o registro da distribuição.

* **--help** Exiba as informações de uso.

## <a name="additional-commands"></a>Comandos adicionais

Também há comandos históricos para interagir com o Subsistema Windows para Linux. Sua funcionalidade é englobada no `wsl.exe`, mas ainda estão disponíveis para uso.

### `wslconfig.exe`

Esse comando permite que você configure a distribuição do WSL. Veja abaixo uma lista das opções.

Usando: `wslconfig [Argument] [Options...]`

#### <a name="arguments"></a>Argumentos

* **/l, /list [Options]**
  
  Lista as distribuições registradas.
  
Opções:

* **/all** Como opção, liste todas as distribuições, incluindo distribuições que estão sendo instaladas ou desinstaladas no momento.

* **/running** Liste somente as distribuições que estão em execução no momento.

* **/s, /setdefault \<Distro>** Define a distribuição como o padrão.

* **/t, /terminate \<Distro>** Encerra a distribuição.

* **/u, /unregister \<Distro>** Cancela o registro da distribuição.

* **/upgrade \<Distro>** Atualiza a distribuição para o formato do sistema de arquivos WslFs.

### `bash.exe`

Esse comando é usado para iniciar um shell Bash. Abaixo estão as opções que você pode usar com este comando.

Usando: `bash [Options...]`

* **Nenhuma opção fornecida**
  
  Inicia o shell Bash no diretório atual. Se o shell Bash não estiver instalado automaticamente, ele executará o `lxrun /install`

* **~**
  
  `bash ~` inicia o shell Bash no diretório base do usuário.  Semelhante à execução de `cd ~`.

* **-c "\<command>"**
  
  Executa o comando, imprime a saída e sai de volta para o prompt de comando do Windows.

  Exemplo: `bash -c "ls"`.

## <a name="deprecated-commands"></a>Comandos preteridos

O `lxrun.exe` foi o primeiro comando usado para instalar e gerenciar o Subsistema Windows para Linux. Ele foi preterido no Windows 10 1803 e versões posteriores.

O comando `lxrun.exe` pode ser usado para interagir diretamente com o WSL (Subsistema Windows para Linux).  Esses comandos são instalados no diretório `\Windows\System32` e podem ser executados em um prompt de comando do Windows ou no PowerShell.

| Comando                     | Descrição                     |
|:----------------------------|:---------------------------|
| `lxrun`                     | O comando lxrun é usado para gerenciar a instância do WSL. |
| `lxrun /install`            | Inicia o processo de download e instalação. <br/> **/y** pode ser adicionado para ignorar todos os prompts.  O prompt de confirmação é automaticamente aceito e o usuário padrão é definido como raiz.          |
| `lxrun /uninstall`          | Desinstala e exclui a imagem do Ubuntu.  Por padrão, isso não remove o diretório base do Ubuntu do usuário. <br/> **/y** pode ser adicionado para aceitar automaticamente o prompt de confirmação <br/>**/full** desinstala e exclui o diretório base do Ubuntu do usuário         |
| `lxrun /setdefaultuser <userName>`     | Define o Bash padrão no usuário do Ubuntu. Solicitará uma senha se o usuário especificado não existir.  Para obter mais informações, confira https://aka.ms/wslusers. <br/> **/y** ignora a solicitação de senha.  O usuário será criado sem uma senha.|
| `lxrun /update`            | Atualiza o índice do pacote do subsistema          |
