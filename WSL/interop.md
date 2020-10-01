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
# <a name="windows-interoperability-with-linux"></a><span data-ttu-id="0bdf5-103">Interoperabilidade do Windows com o Linux</span><span class="sxs-lookup"><span data-stu-id="0bdf5-103">Windows interoperability with Linux</span></span>

<span data-ttu-id="0bdf5-104">O WSL (Subsistema Windows para Linux) está melhorando continuamente a integração entre o Windows e o Linux.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-104">The Windows Subsystem for Linux (WSL) is continuously improving integration between Windows and Linux.</span></span>  <span data-ttu-id="0bdf5-105">Você pode:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-105">You can:</span></span>

* <span data-ttu-id="0bdf5-106">Executar as ferramentas do Windows (por exemplo, notepad.exe) de uma linha de comando do Linux (por exemplo, Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="0bdf5-106">Run Windows tools (ie. notepad.exe) from a Linux command line (ie. Ubuntu).</span></span>
* <span data-ttu-id="0bdf5-107">Executar ferramentas do Linux (por exemplo, grep) de uma linha de comando do Windows (por exemplo, PowerShell).</span><span class="sxs-lookup"><span data-stu-id="0bdf5-107">Run Linux tools (ie. grep) from a Windows command line (ie. PowerShell).</span></span>
* <span data-ttu-id="0bdf5-108">Compartilhar variáveis de ambiente entre o Linux e o Windows.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-108">Share environment variables between Linux and Windows.</span></span> <span data-ttu-id="0bdf5-109">(Build 17063e posteriores)</span><span class="sxs-lookup"><span data-stu-id="0bdf5-109">(Build 17063+)</span></span>

> [!NOTE]
> <span data-ttu-id="0bdf5-110">Se você estiver executando a Atualização para Criadores (outubro de 2017, Build 16299) ou a Atualização de Aniversário (agosto de 2016, Build 14393), vá para as [versões anteriores do Windows 10](#earlier-versions-of-windows-10).</span><span class="sxs-lookup"><span data-stu-id="0bdf5-110">If you're running Creators Update (Oct 2017, Build 16299) or Anniversary Update (Aug 2016, Build 14393), jump to the [Earlier versions of Windows 10](#earlier-versions-of-windows-10).</span></span>

## <a name="run-linux-tools-from-a-windows-command-line"></a><span data-ttu-id="0bdf5-111">Execute ferramentas do Linux usando uma linha de comando do Windows</span><span class="sxs-lookup"><span data-stu-id="0bdf5-111">Run Linux tools from a Windows command line</span></span>

<span data-ttu-id="0bdf5-112">Execute binários do Linux no prompt de comando do Windows (CMD) ou PowerShell usando o `wsl <command>` (ou `wsl.exe <command>`).</span><span class="sxs-lookup"><span data-stu-id="0bdf5-112">Run Linux binaries from the Windows Command Prompt (CMD) or PowerShell using `wsl <command>` (or `wsl.exe <command>`).</span></span>

<span data-ttu-id="0bdf5-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-113">For example:</span></span>

```powershell
C:\temp> wsl ls -la
<- contents of C:\temp ->
```

<span data-ttu-id="0bdf5-114">Binários invocados desta maneira:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-114">Binaries invoked in this way:</span></span>

* <span data-ttu-id="0bdf5-115">Use o mesmo diretório de trabalho que o prompt do CMD ou do PowerShell atual.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-115">Use the same working directory as the current CMD or PowerShell prompt.</span></span>
* <span data-ttu-id="0bdf5-116">Execute como usuário padrão do WSL.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-116">Run as the WSL default user.</span></span>
* <span data-ttu-id="0bdf5-117">Tenha os mesmos direitos administrativos do Windows que o processo de chamada e o terminal.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-117">Have the same Windows administrative rights as the calling process and terminal.</span></span>

<span data-ttu-id="0bdf5-118">O comando do Linux após `wsl` (ou `wsl.exe`) é tratado como qualquer comando executado no WSL.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-118">The Linux command following `wsl` (or `wsl.exe`) is handled like any command run in WSL.</span></span>  <span data-ttu-id="0bdf5-119">Coisas como sudo, piping e redirecionamento de arquivo funcionam.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-119">Things such as sudo, piping, and file redirection work.</span></span>

<span data-ttu-id="0bdf5-120">Exemplo usando o sudo para atualizar sua distribuição padrão do Linux:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-120">Example using sudo to update your default Linux distribution:</span></span>

```powershell
C:\temp> wsl sudo apt-get update
```

<span data-ttu-id="0bdf5-121">Seu nome de usuário de distribuição do Linux padrão será listado após a execução desse comando e você será solicitado a fornecer sua senha.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-121">Your default Linux distribution user name will be listed after running this command and you will be asked for your password.</span></span> <span data-ttu-id="0bdf5-122">Depois de inserir sua senha corretamente, sua distribuição baixará as atualizações.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-122">After entering your password correctly, your distribution will download updates.</span></span>

## <a name="mixing-linux-and-windows-commands"></a><span data-ttu-id="0bdf5-123">Como mesclar comandos do Windows e do Linux</span><span class="sxs-lookup"><span data-stu-id="0bdf5-123">Mixing Linux and Windows commands</span></span>

<span data-ttu-id="0bdf5-124">Aqui estão alguns exemplos de como mesclar comandos do Linux e do Windows usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-124">Here are a few examples of mixing Linux and Windows commands using PowerShell.</span></span>

<span data-ttu-id="0bdf5-125">Para usar o comando `ls -la` do Linux para listar arquivos e o comando `findstr` do PowerShell para filtrar os resultados de palavras que contenham "git", combine os comandos:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-125">To use the Linux command `ls -la` to list files and the PowerShell command `findstr` to filter the results for words containing "git", combine the commands:</span></span>

```powershell
wsl ls -la | findstr "git"
```

<span data-ttu-id="0bdf5-126">Para usar o comando `dir` do PowerShell para listar arquivos e o comando `grep` do Linux para filtrar os resultados de palavras que contenham "git", combine os comandos:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-126">To use the PowerShell command `dir` to list files and the Linux command `grep` to filter the results for words containing "git", combine the commands:</span></span>

```powershell
C:\temp> dir | wsl grep git
```

<span data-ttu-id="0bdf5-127">Para usar o comando `ls -la` do Linux para listar arquivos e o comando `> out.txt` do PowerShell para imprimir a lista em um arquivo de texto chamado "out.txt", combine os comandos:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-127">To use the Linux command `ls -la` to list files and the PowerShell command `> out.txt` to print that list to a text file named "out.txt", combine the commands:</span></span>

```powershell
C:\temp> wsl ls -la > out.txt
```

<span data-ttu-id="0bdf5-128">Os comandos passados para `wsl.exe` são encaminhados para o processo do WSL sem modificação.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-128">The commands passed into `wsl.exe` are forwarded to the WSL process without modification.</span></span>  <span data-ttu-id="0bdf5-129">Os caminhos de arquivo devem ser especificados no formato do WSL.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-129">File paths must be specified in the WSL format.</span></span>

<span data-ttu-id="0bdf5-130">Para usar o comando `ls -la` do Linux para listar arquivos no caminho do sistema de arquivos `/proc/cpuinfo` do Linux usando o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-130">To use the Linux command `ls -la` to list files in the `/proc/cpuinfo` Linux file system path, using PowerShell:</span></span>

```powershell
C:\temp> wsl ls -la /proc/cpuinfo
```

<span data-ttu-id="0bdf5-131">Para usar o comando `ls -la` do Linux para listar arquivos no caminho do sistema de arquivos `C:\Program Files` do Windows usando o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-131">To use the Linux command `ls -la` to list files in the `C:\Program Files` Windows file system path, using PowerShell:</span></span>

```powershell
C:\temp> wsl ls -la "/mnt/c/Program Files"
```

## <a name="run-windows-tools-from-linux"></a><span data-ttu-id="0bdf5-132">Executar ferramentas do Windows no Linux</span><span class="sxs-lookup"><span data-stu-id="0bdf5-132">Run Windows tools from Linux</span></span>

<span data-ttu-id="0bdf5-133">O WSL pode executar as ferramentas do Windows diretamente da linha de comando do WSL usando `[tool-name].exe`.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-133">WSL can run Windows tools directly from the WSL command line using `[tool-name].exe`.</span></span>  <span data-ttu-id="0bdf5-134">Por exemplo, `notepad.exe`.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-134">For example, `notepad.exe`.</span></span>

<!-- Craig - could you help add a section with an example here to explain this scenario: "To access your Linux files using a Windows tool, use `\\wsl$\<distroName>\'` as the file path." Currently it I can just enter `notepad.exe foo.txt` and it seems to work fine, so explaining a situation where the file path is needed would be helpful. -->

<span data-ttu-id="0bdf5-135">Os aplicativos executados dessa maneira têm as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-135">Applications run this way have the following properties:</span></span>

* <span data-ttu-id="0bdf5-136">Mantenha o diretório de trabalho como o prompt de comando do WSL (em grande parte – as exceções são explicadas abaixo).</span><span class="sxs-lookup"><span data-stu-id="0bdf5-136">Retain the working directory as the WSL command prompt (for the most part -- exceptions are explained below).</span></span>
* <span data-ttu-id="0bdf5-137">Tenha os mesmos direitos de permissão que o processo do WSL.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-137">Have the same permission rights as the WSL process.</span></span>
* <span data-ttu-id="0bdf5-138">Execute como usuário ativo do Windows.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-138">Run as the active Windows user.</span></span>
* <span data-ttu-id="0bdf5-139">É exibido no Gerenciador de Tarefas do Windows como se fosse executado diretamente no prompt do CMD.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-139">Appear in the Windows Task Manager as if directly executed from the CMD prompt.</span></span>

<span data-ttu-id="0bdf5-140">Os executáveis do Windows executados no WSL são tratados de forma semelhante aos executáveis do Linux nativos – piping, redirecionamentos e até mesmo o trabalho em segundo plano conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-140">Windows executables run in WSL are handled similarly to native Linux executables -- piping, redirects, and even backgrounding work as expected.</span></span>

<span data-ttu-id="0bdf5-141">Para executar a ferramenta `ipconfig.exe` do Windows, use a ferramenta `grep` do Linux para filtrar os resultados de "IPv4", e use a ferramenta `cut` do Linux para remover os campos de coluna. De uma distribuição do Linux (por exemplo, Ubuntu), insira:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-141">To run the Windows tool `ipconfig.exe`, use the Linux tool `grep` to filter the "IPv4" results, and use the Linux tool `cut` to remove the column fields, from a Linux distribution (for example, Ubuntu) enter:</span></span>

```bash
ipconfig.exe | grep IPv4 | cut -d: -f2
```

<span data-ttu-id="0bdf5-142">Vamos tentar mesclar comandos do Windows e do Linux.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-142">Let's try an example mixing Windows and Linux commands.</span></span> <span data-ttu-id="0bdf5-143">Abra sua distribuição do Linux (por exemplo, Ubuntu) e crie um arquivo de texto: `touch foo.txt`.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-143">Open your Linux distribution (ie. Ubuntu) and create a text file: `touch foo.txt`.</span></span> <span data-ttu-id="0bdf5-144">Agora, use o comando `ls -la` do Linux para listar os arquivos diretos e seus detalhes de criação, além da ferramenta `findstr.exe` do Windows PowerShell para filtrar os resultados para que apenas o arquivo `foo.txt` seja exibido nos resultados:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-144">Now use the Linux command `ls -la` to list the direct files and their creation details, plus the Windows PowerShell tool `findstr.exe` to filter the results so only your `foo.txt` file shows in the results:</span></span>

```bash
ls -la | findstr.exe foo.txt
```

<span data-ttu-id="0bdf5-145">As ferramentas do Windows devem incluir a extensão do arquivo, corresponder o caso do arquivo e ser executáveis.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-145">Windows tools must include the file extension, match the file case, and be executable.</span></span>  <span data-ttu-id="0bdf5-146">Não executáveis, incluindo scripts do lote.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-146">Non-executables including batch scripts.</span></span>  <span data-ttu-id="0bdf5-147">Comandos nativos do CMD, como `dir`, podem ser executados com o comando `cmd.exe /C`.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-147">CMD native commands like `dir` can be run with `cmd.exe /C` command.</span></span>

<span data-ttu-id="0bdf5-148">Por exemplo, liste o conteúdo de seu diretório C:\ do sistema de arquivos do Windows, digitando:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-148">For example, list the contents of your Windows files system C:\ directory, by entering:</span></span>

```bash
cmd.exe /C dir
```

<span data-ttu-id="0bdf5-149">Ou use o comando `ping` para enviar uma solicitação de eco para o site microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-149">Or use the `ping` command to send an echo request to the microsoft.com website:</span></span>

```bash
ping.exe www.microsoft.com
```

<span data-ttu-id="0bdf5-150">Os parâmetros são passados para o binário do Windows não modificado.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-150">Parameters are passed to the Windows binary unmodified.</span></span> <span data-ttu-id="0bdf5-151">Por exemplo, o seguinte comando abrirá `C:\temp\foo.txt` no `notepad.exe`:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-151">As an example, the following command will open `C:\temp\foo.txt` in `notepad.exe`:</span></span>

```bash
notepad.exe "C:\temp\foo.txt"
```

<span data-ttu-id="0bdf5-152">Isso também funcionará:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-152">This will also work:</span></span>

```bash
notepad.exe C:\\temp\\foo.txt
```

## <a name="share-environment-variables-between-windows-and-wsl"></a><span data-ttu-id="0bdf5-153">Compartilhar variáveis de ambiente entre o Windows e o WSL</span><span class="sxs-lookup"><span data-stu-id="0bdf5-153">Share environment variables between Windows and WSL</span></span>

<span data-ttu-id="0bdf5-154">O WSL e o Windows compartilham o `WSLENV`, uma variável de ambiente especial criada para vincular distribuições do Windows e do Linux em execução no WSL.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-154">WSL and Windows share a special environment variable, `WSLENV`, created to bridge Windows and Linux distributions running on WSL.</span></span>

<span data-ttu-id="0bdf5-155">Propriedades da variável `WSLENV`:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-155">Properties of `WSLENV` variable:</span></span>

* <span data-ttu-id="0bdf5-156">Ele é compartilhado e existe em ambientes do Windows e do WSL.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-156">It is shared; it exists in both Windows and WSL environments.</span></span>
* <span data-ttu-id="0bdf5-157">É uma lista de variáveis de ambiente a serem compartilhadas entre o Windows e o WSL.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-157">It is a list of environment variables to share between Windows and WSL.</span></span>
* <span data-ttu-id="0bdf5-158">Pode formatar variáveis de ambiente para funcionamento no Windows e no WSL.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-158">It can format environment variables to work well in Windows and WSL.</span></span>
* <span data-ttu-id="0bdf5-159">Pode auxiliar no fluxo entre o WSL e o Win32.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-159">It can assist in the flow between WSL and Win32.</span></span>

> [!NOTE]
> <span data-ttu-id="0bdf5-160">Antes do 17063, a única variável de ambiente do Windows que o WSL podia acessar era `PATH` (portanto, era possível iniciar os executáveis do Win32 no WSL).</span><span class="sxs-lookup"><span data-stu-id="0bdf5-160">Prior to 17063, only Windows environment variable that WSL could access was `PATH` (so you could launch Win32 executables from under WSL).</span></span> <span data-ttu-id="0bdf5-161">O `WSLENV` passa a ter suporte no 17063 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-161">Starting in 17063, `WSLENV` begins being supported.</span></span>
> <span data-ttu-id="0bdf5-162">O WSLENV diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-162">WSLENV is case sensitive.</span></span>

## <a name="wslenv-flags"></a><span data-ttu-id="0bdf5-163">Sinalizadores de WSLENV</span><span class="sxs-lookup"><span data-stu-id="0bdf5-163">WSLENV flags</span></span>

<span data-ttu-id="0bdf5-164">Há quatro sinalizadores disponíveis no `WSLENV` para influenciar como essa variável de ambiente é convertida.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-164">There are four flags available in `WSLENV` to influence how the environment variable is translated.</span></span>

<span data-ttu-id="0bdf5-165">`WSLENV` sinalizadores:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-165">`WSLENV` flags:</span></span>

* <span data-ttu-id="0bdf5-166">`/p` – converte o caminho entre os caminhos do estilo WSL/Linux e os caminhos do Win32.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-166">`/p` - translates the path between WSL/Linux style paths and Win32 paths.</span></span>
* <span data-ttu-id="0bdf5-167">`/l` – indica que a variável de ambiente é uma lista de caminhos.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-167">`/l` - indicates the environment variable is a list of paths.</span></span>
* <span data-ttu-id="0bdf5-168">`/u` – indica que essa variável de ambiente só deve ser incluída ao executar o WSL usando o Win32.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-168">`/u` - indicates that this environment variable should only be included when running WSL from Win32.</span></span>
* <span data-ttu-id="0bdf5-169">`/w` – indica que essa variável de ambiente só deve ser incluída ao executar o Win32 usando o WSL.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-169">`/w` - indicates that this environment variable should only be included when running Win32 from WSL.</span></span>

<span data-ttu-id="0bdf5-170">Os sinalizadores podem ser combinados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-170">Flags can be combined as needed.</span></span>

<span data-ttu-id="0bdf5-171">[Leia mais sobre WSLENV](https://devblogs.microsoft.com/commandline/share-environment-vars-between-wsl-and-windows/), incluindo perguntas frequentes e exemplos de como definir o valor de WSLENV para uma concatenação de outras variáveis de ambiente predefinidas, cada uma delas com uma barra seguida de sinalizadores para especificar como o valor deve ser traduzido, e de como passar variáveis com um script.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-171">[Read more about WSLENV](https://devblogs.microsoft.com/commandline/share-environment-vars-between-wsl-and-windows/), including FAQs and examples of setting the value of WSLENV to a concatenation of other pre-defined environment vars, each suffixed with a slash followed by flags to specify how the value should be translated and passing variables with a script.</span></span> <span data-ttu-id="0bdf5-172">Este artigo também inclui um exemplo para configurar um ambiente de desenvolvimento com a [linguagem de programação Go](https://golang.org/), configurada para compartilhar um GOPATH entre WSL e Win32.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-172">This article also includes an example for setting up a dev environment with the [Go programming language](https://golang.org/), configured to share a GOPATH between WSL and Win32.</span></span>

## <a name="disable-interoperability"></a><span data-ttu-id="0bdf5-173">Desabilitar interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="0bdf5-173">Disable interoperability</span></span>

<span data-ttu-id="0bdf5-174">Os usuários podem desabilitar a capacidade de executar ferramentas do Windows para uma sessão do WSL executando o seguinte comando como raiz:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-174">Users may disable the ability to run Windows tools for a single WSL session by running the following command as root:</span></span>

```bash
echo 0 > /proc/sys/fs/binfmt_misc/WSLInterop
```

<span data-ttu-id="0bdf5-175">Para reabilitar os binários do Windows, saia de todas as sessões do WSL e execute o bash.exe novamente ou execute o seguinte comando como raiz:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-175">To re-enable Windows binaries, exit all WSL sessions and re-run bash.exe or run the following command as root:</span></span>

```bash
echo 1 > /proc/sys/fs/binfmt_misc/WSLInterop
```

<span data-ttu-id="0bdf5-176">Desabilitar a interoperabilidade não persistirá entre as sessões do WSL – a interoperabilidade será habilitada novamente quando uma nova sessão for iniciada.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-176">Disabling interop will not persist between WSL sessions -- interop will be enabled again when a new session is launched.</span></span>

## <a name="earlier-versions-of-windows-10"></a><span data-ttu-id="0bdf5-177">Versões anteriores do Windows 10</span><span class="sxs-lookup"><span data-stu-id="0bdf5-177">Earlier versions of Windows 10</span></span>

<span data-ttu-id="0bdf5-178">Há várias diferenças nos comandos de interoperabilidade em versões anteriores do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-178">There are several differences for the interoperability commands on earlier Windows 10 versions.</span></span> <span data-ttu-id="0bdf5-179">Se você estiver executando uma Atualização para Criadores (outubro de 2017, Build 16299) ou uma Atualização de Aniversário (agosto de 2016, Build 14393) do Windows 10, recomendamos que você [atualize para a versão mais recente do Windows](ms-settings:windowsupdate), mas, se isso não for possível, descrevemos algumas das diferenças de interoperabilidade abaixo.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-179">If you're running a Creators Update (Oct 2017, Build 16299), or Anniversary Update (Aug 2016, Build 14393) version of Windows 10, we recommend you [update to the latest Windows version](ms-settings:windowsupdate), but if that's not possible, we have outlined some of the interop differences below.</span></span>

<span data-ttu-id="0bdf5-180">Resumo:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-180">Summary:</span></span>

* <span data-ttu-id="0bdf5-181">`bash.exe` foi substituído por `wsl.exe`.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-181">`bash.exe` has been replaced with `wsl.exe`.</span></span>
* <span data-ttu-id="0bdf5-182">A opção `-c` para executar um único comando não é necessária com o `wsl.exe`.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-182">`-c` option for running a single command isn't needed with `wsl.exe`.</span></span>
* <span data-ttu-id="0bdf5-183">O caminho do Windows está incluído no WSL `$PATH`.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-183">Windows path is included in the WSL `$PATH`.</span></span>
* <span data-ttu-id="0bdf5-184">O processo para desabilitar a interoperabilidade não é alterado.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-184">The process for disabling interop is unchanged.</span></span>

<span data-ttu-id="0bdf5-185">Os comandos do Linux podem ser executados no prompt de comando do Windows ou no PowerShell, mas, para versões anteriores do Windows, você precisa usar o comando `bash`.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-185">Linux commands can be run from the Windows Command Prompt or from PowerShell, but for early Windows versions, you man need to use the `bash` command.</span></span> <span data-ttu-id="0bdf5-186">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-186">For example:</span></span>

```powershell
C:\temp> bash -c "ls -la"
```

<span data-ttu-id="0bdf5-187">Coisas como inserção, piping e redirecionamento de arquivo funcionam.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-187">Things such as input, piping, and file redirection work as expected.</span></span>

<span data-ttu-id="0bdf5-188">Os comandos do WSL passados para `bash -c` são encaminhados para o processo do WSL sem modificação.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-188">The WSL commands passed into `bash -c` are forwarded to the WSL process without modification.</span></span>  <span data-ttu-id="0bdf5-189">Os caminhos de arquivo devem ser especificados no formato do WSL e é necessário ter cuidado com os caracteres de escape relevantes.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-189">File paths must be specified in the WSL format and care must be taken to escape relevant characters.</span></span> <span data-ttu-id="0bdf5-190">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-190">Example:</span></span>

```console
C:\temp> bash -c "ls -la /proc/cpuinfo"
```

<span data-ttu-id="0bdf5-191">Ou...</span><span class="sxs-lookup"><span data-stu-id="0bdf5-191">Or...</span></span>

```powershell
C:\temp> bash -c "ls -la \"/mnt/c/Program Files\""
```

<span data-ttu-id="0bdf5-192">Ao chamar uma ferramenta do Windows de uma distribuição do WSL em uma versão anterior do Windows 10, será necessário especificar o caminho do diretório.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-192">When calling a Windows tool from a WSL distribution in an earlier version of Windows 10, you will need to specify the directory path.</span></span> <span data-ttu-id="0bdf5-193">Por exemplo, na linha de comando do WSL, digite:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-193">For example, from your WSL command line, enter:</span></span>

```bash
/mnt/c/Windows/System32/notepad.exe
```

<span data-ttu-id="0bdf5-194">No WSL, esses executáveis são tratados de forma semelhante aos executáveis do Linux nativos.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-194">In WSL, these executables are handled similar to native Linux executables.</span></span>  <span data-ttu-id="0bdf5-195">Isso significa que adicionar diretórios ao piping e ao caminho do Linux entre comandos funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-195">This means adding directories to the Linux path and piping between commands works as expected.</span></span>  <span data-ttu-id="0bdf5-196">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-196">For example:</span></span>

```bash
export PATH=$PATH:/mnt/c/Windows/System32
```
<span data-ttu-id="0bdf5-197">Ou</span><span class="sxs-lookup"><span data-stu-id="0bdf5-197">Or</span></span>

```bash
ipconfig.exe | grep IPv4 | cut -d: -f2
```

<span data-ttu-id="0bdf5-198">O binário do Windows deve incluir a extensão do arquivo, corresponder o caso do arquivo e ser executável.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-198">The Windows binary must include the file extension, match the file case, and be executable.</span></span>  <span data-ttu-id="0bdf5-199">Os não executáveis, incluindo scripts do lote e comandos como `dir`, podem ser executados com o comando `/mnt/c/Windows/System32/cmd.exe /C`.</span><span class="sxs-lookup"><span data-stu-id="0bdf5-199">Non-executables including batch scripts and command like `dir` can be run with `/mnt/c/Windows/System32/cmd.exe /C` command.</span></span> <span data-ttu-id="0bdf5-200">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0bdf5-200">For example:</span></span>

```bash
/mnt/c/Windows/System32/cmd.exe /C dir
```

## <a name="additional-resources"></a><span data-ttu-id="0bdf5-201">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0bdf5-201">Additional resources</span></span>

* [<span data-ttu-id="0bdf5-202">Postagem do blog do WSL sobre interoperabilidade de 2016</span><span class="sxs-lookup"><span data-stu-id="0bdf5-202">WSL blog post on interoperability from 2016</span></span>](/archive/blogs/wsl/windows-and-ubuntu-interoperability)