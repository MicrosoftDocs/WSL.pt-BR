---
title: Interoperabilidade do Windows com o Linux
description: Descreve a interoperabilidade do Windows com distribuições do Linux em execução no Subsistema Windows para Linux.
ms.date: 05/12/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 8e3568e4ca94f9b381b7827a237c2b637b97ae57
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413067"
---
# <a name="windows-interoperability-with-linux"></a>Interoperabilidade do Windows com o Linux

O WSL (Subsistema Windows para Linux) está melhorando continuamente a integração entre o Windows e o Linux.  Você pode:

* Executar as ferramentas do Windows (por exemplo, notepad.exe) de uma linha de comando do Linux (por exemplo, Ubuntu).
* Executar ferramentas do Linux (por exemplo, grep) de uma linha de comando do Windows (por exemplo, PowerShell).
* Compartilhar variáveis de ambiente entre o Linux e o Windows. (Build 17063e posteriores)

> [!NOTE]
> Se você estiver executando a Atualização para Criadores (outubro de 2017, Build 16299) ou a Atualização de Aniversário (agosto de 2016, Build 14393), vá para as [versões anteriores do Windows 10](#earlier-versions-of-windows-10).

## <a name="run-linux-tools-from-a-windows-command-line"></a>Execute ferramentas do Linux usando uma linha de comando do Windows

Execute binários do Linux no prompt de comando do Windows (CMD) ou PowerShell usando o `wsl <command>` (ou `wsl.exe <command>`).

Por exemplo:

```powershell
C:\temp> wsl ls -la
<- contents of C:\temp ->
```

Binários invocados desta maneira:

* Use o mesmo diretório de trabalho que o prompt do CMD ou do PowerShell atual.
* Execute como usuário padrão do WSL.
* Tenha os mesmos direitos administrativos do Windows que o processo de chamada e o terminal.

O comando do Linux após `wsl` (ou `wsl.exe`) é tratado como qualquer comando executado no WSL.  Coisas como sudo, piping e redirecionamento de arquivo funcionam.

Exemplo usando o sudo para atualizar sua distribuição padrão do Linux:

```powershell
C:\temp> wsl sudo apt-get update
```

Seu nome de usuário de distribuição do Linux padrão será listado após a execução desse comando e você será solicitado a fornecer sua senha. Depois de inserir sua senha corretamente, sua distribuição baixará as atualizações.

## <a name="mixing-linux-and-windows-commands"></a>Como mesclar comandos do Windows e do Linux

Aqui estão alguns exemplos de como mesclar comandos do Linux e do Windows usando o PowerShell.

Para usar o comando `ls -la` do Linux para listar arquivos e o comando `findstr` do PowerShell para filtrar os resultados de palavras que contenham "git", combine os comandos:

```powershell
wsl ls -la | findstr "git"
```

Para usar o comando `dir` do PowerShell para listar arquivos e o comando `grep` do Linux para filtrar os resultados de palavras que contenham "git", combine os comandos:

```powershell
C:\temp> dir | wsl grep git
```

Para usar o comando `ls -la` do Linux para listar arquivos e o comando `> out.txt` do PowerShell para imprimir a lista em um arquivo de texto chamado "out.txt", combine os comandos:

```powershell
C:\temp> wsl ls -la > out.txt
```

Os comandos passados para `wsl.exe` são encaminhados para o processo do WSL sem modificação.  Os caminhos de arquivo devem ser especificados no formato do WSL.

Para usar o comando `ls -la` do Linux para listar arquivos no caminho do sistema de arquivos `/proc/cpuinfo` do Linux usando o PowerShell:

```powershell
C:\temp> wsl ls -la /proc/cpuinfo
```

Para usar o comando `ls -la` do Linux para listar arquivos no caminho do sistema de arquivos `C:\Program Files` do Windows usando o PowerShell:

```powershell
C:\temp> wsl ls -la "/mnt/c/Program Files"
```

## <a name="run-windows-tools-from-linux"></a>Executar ferramentas do Windows no Linux

O WSL pode executar as ferramentas do Windows diretamente da linha de comando do WSL usando `[tool-name].exe`.  Por exemplo, `notepad.exe`.

<!-- Craig - could you help add a section with an example here to explain this scenario: "To access your Linux files using a Windows tool, use `\\wsl$\<distroName>\'` as the file path." Currently it I can just enter `notepad.exe foo.txt` and it seems to work fine, so explaining a situation where the file path is needed would be helpful. -->

Os aplicativos executados dessa maneira têm as seguintes propriedades:

* Mantenha o diretório de trabalho como o prompt de comando do WSL (em grande parte – as exceções são explicadas abaixo).
* Tenha os mesmos direitos de permissão que o processo do WSL.
* Execute como usuário ativo do Windows.
* É exibido no Gerenciador de Tarefas do Windows como se fosse executado diretamente no prompt do CMD.

Os executáveis do Windows executados no WSL são tratados de forma semelhante aos executáveis do Linux nativos – piping, redirecionamentos e até mesmo o trabalho em segundo plano conforme o esperado.

Para executar a ferramenta `ipconfig.exe` do Windows, use a ferramenta `grep` do Linux para filtrar os resultados de "IPv4", e use a ferramenta `cut` do Linux para remover os campos de coluna. De uma distribuição do Linux (por exemplo, Ubuntu), insira:

```bash
ipconfig.exe | grep IPv4 | cut -d: -f2
```

Vamos tentar mesclar comandos do Windows e do Linux. Abra sua distribuição do Linux (por exemplo, Ubuntu) e crie um arquivo de texto: `touch foo.txt`. Agora, use o comando `ls -la` do Linux para listar os arquivos diretos e seus detalhes de criação, além da ferramenta `findstr.exe` do Windows PowerShell para filtrar os resultados para que apenas o arquivo `foo.txt` seja exibido nos resultados:

```bash
ls -la | findstr.exe foo.txt
```

As ferramentas do Windows devem incluir a extensão do arquivo, corresponder o caso do arquivo e ser executáveis.  Não executáveis, incluindo scripts do lote.  Comandos nativos do CMD, como `dir`, podem ser executados com o comando `cmd.exe /C`.

Por exemplo, liste o conteúdo de seu diretório C:\ do sistema de arquivos do Windows, digitando:

```bash
cmd.exe /C dir
```

Ou use o comando `ping` para enviar uma solicitação de eco para o site microsoft.com:

```bash
ping.exe www.microsoft.com
```

Os parâmetros são passados para o binário do Windows não modificado. Por exemplo, o seguinte comando abrirá `C:\temp\foo.txt` no `notepad.exe`:

```bash
notepad.exe "C:\temp\foo.txt"
```

Isso também funcionará:

```bash
notepad.exe C:\\temp\\foo.txt
```

## <a name="share-environment-variables-between-windows-and-wsl"></a>Compartilhar variáveis de ambiente entre o Windows e o WSL

O WSL e o Windows compartilham o `WSLENV`, uma variável de ambiente especial criada para vincular distribuições do Windows e do Linux em execução no WSL.

Propriedades da variável `WSLENV`:

* Ele é compartilhado e existe em ambientes do Windows e do WSL.
* É uma lista de variáveis de ambiente a serem compartilhadas entre o Windows e o WSL.
* Pode formatar variáveis de ambiente para funcionamento no Windows e no WSL.
* Pode auxiliar no fluxo entre o WSL e o Win32.

> [!NOTE]
> Antes do 17063, a única variável de ambiente do Windows que o WSL podia acessar era `PATH` (portanto, era possível iniciar os executáveis do Win32 no WSL). O `WSLENV` passa a ter suporte no 17063 e posteriores.
> O WSLENV diferencia maiúsculas de minúsculas.

## <a name="wslenv-flags"></a>Sinalizadores de WSLENV

Há quatro sinalizadores disponíveis no `WSLENV` para influenciar como essa variável de ambiente é convertida.

`WSLENV` sinalizadores:

* `/p` – converte o caminho entre os caminhos do estilo WSL/Linux e os caminhos do Win32.
* `/l` – indica que a variável de ambiente é uma lista de caminhos.
* `/u` – indica que essa variável de ambiente só deve ser incluída ao executar o WSL usando o Win32.
* `/w` – indica que essa variável de ambiente só deve ser incluída ao executar o Win32 usando o WSL.

Os sinalizadores podem ser combinados conforme necessário.

[Leia mais sobre WSLENV](https://devblogs.microsoft.com/commandline/share-environment-vars-between-wsl-and-windows/), incluindo perguntas frequentes e exemplos de como definir o valor de WSLENV para uma concatenação de outras variáveis de ambiente predefinidas, cada uma delas com uma barra seguida de sinalizadores para especificar como o valor deve ser traduzido, e de como passar variáveis com um script. Este artigo também inclui um exemplo para configurar um ambiente de desenvolvimento com a [linguagem de programação Go](https://golang.org/), configurada para compartilhar um GOPATH entre WSL e Win32.

## <a name="disable-interoperability"></a>Desabilitar interoperabilidade

Os usuários podem desabilitar a capacidade de executar ferramentas do Windows para uma sessão do WSL executando o seguinte comando como raiz:

```bash
echo 0 > /proc/sys/fs/binfmt_misc/WSLInterop
```

Para reabilitar os binários do Windows, saia de todas as sessões do WSL e execute o bash.exe novamente ou execute o seguinte comando como raiz:

```bash
echo 1 > /proc/sys/fs/binfmt_misc/WSLInterop
```

Desabilitar a interoperabilidade não persistirá entre as sessões do WSL – a interoperabilidade será habilitada novamente quando uma nova sessão for iniciada.

## <a name="earlier-versions-of-windows-10"></a>Versões anteriores do Windows 10

Há várias diferenças nos comandos de interoperabilidade em versões anteriores do Windows 10. Se você estiver executando uma Atualização para Criadores (outubro de 2017, Build 16299) ou uma Atualização de Aniversário (agosto de 2016, Build 14393) do Windows 10, recomendamos que você [atualize para a versão mais recente do Windows](ms-settings:windowsupdate), mas, se isso não for possível, descrevemos algumas das diferenças de interoperabilidade abaixo.

Resumo:

* `bash.exe` foi substituído por `wsl.exe`.
* A opção `-c` para executar um único comando não é necessária com o `wsl.exe`.
* O caminho do Windows está incluído no WSL `$PATH`.
* O processo para desabilitar a interoperabilidade não é alterado.

Os comandos do Linux podem ser executados no prompt de comando do Windows ou no PowerShell, mas, para versões anteriores do Windows, você precisa usar o comando `bash`. Por exemplo:

```powershell
C:\temp> bash -c "ls -la"
```

Coisas como inserção, piping e redirecionamento de arquivo funcionam.

Os comandos do WSL passados para `bash -c` são encaminhados para o processo do WSL sem modificação.  Os caminhos de arquivo devem ser especificados no formato do WSL e é necessário ter cuidado com os caracteres de escape relevantes. Exemplo:

```console
C:\temp> bash -c "ls -la /proc/cpuinfo"
```

Ou...

```powershell
C:\temp> bash -c "ls -la \"/mnt/c/Program Files\""
```

Ao chamar uma ferramenta do Windows de uma distribuição do WSL em uma versão anterior do Windows 10, será necessário especificar o caminho do diretório. Por exemplo, na linha de comando do WSL, digite:

```bash
/mnt/c/Windows/System32/notepad.exe
```

No WSL, esses executáveis são tratados de forma semelhante aos executáveis do Linux nativos.  Isso significa que adicionar diretórios ao piping e ao caminho do Linux entre comandos funciona conforme o esperado.  Por exemplo:

```bash
export PATH=$PATH:/mnt/c/Windows/System32
```
Ou

```bash
ipconfig.exe | grep IPv4 | cut -d: -f2
```

O binário do Windows deve incluir a extensão do arquivo, corresponder o caso do arquivo e ser executável.  Os não executáveis, incluindo scripts do lote e comandos como `dir`, podem ser executados com o comando `/mnt/c/Windows/System32/cmd.exe /C`. Por exemplo:

```bash
/mnt/c/Windows/System32/cmd.exe /C dir
```

## <a name="additional-resources"></a>Recursos adicionais

* [Postagem do blog do WSL sobre interoperabilidade de 2016](/archive/blogs/wsl/windows-and-ubuntu-interoperability)