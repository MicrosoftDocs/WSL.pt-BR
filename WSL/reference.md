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
# <a name="command-reference-for-windows-subsystem-for-linux"></a><span data-ttu-id="121b5-104">Referência de comandos para o Subsistema Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="121b5-104">Command Reference for Windows Subsystem for Linux</span></span>

<span data-ttu-id="121b5-105">A melhor maneira de interagir com o Subsistema Windows para Linux é usar o comando `wsl.exe`.</span><span class="sxs-lookup"><span data-stu-id="121b5-105">The best way to interact with the Windows Subsystem for Linux is to use the `wsl.exe` command.</span></span>

## <a name="set-wsl-2-as-your-default-version"></a><span data-ttu-id="121b5-106">Definir o WSL 2 como sua versão padrão</span><span class="sxs-lookup"><span data-stu-id="121b5-106">Set WSL 2 as your default version</span></span>

<span data-ttu-id="121b5-107">Execute o seguinte comando no PowerShell para definir o WSL 2 como a versão padrão ao instalar uma nova distribuição do Linux:</span><span class="sxs-lookup"><span data-stu-id="121b5-107">Run the following command in Powershell to set WSL 2 as the default version when installing a new Linux distribution:</span></span>

```powershell
wsl --set-default-version 2
```

## <a name="set-your-distribution-version-to-wsl-1-or-wsl-2"></a><span data-ttu-id="121b5-108">Definir a versão de distribuição para WSL 1 ou WSL 2</span><span class="sxs-lookup"><span data-stu-id="121b5-108">Set your distribution version to WSL 1 or WSL 2</span></span>

<span data-ttu-id="121b5-109">Verifique a versão do WSL atribuída a cada uma das distribuições do Linux instaladas abrindo a linha de comando do PowerShell e inserindo o comando (disponível somente no [Windows Build 19041 ou superiores](ms-settings:windowsupdate)): `wsl -l -v`</span><span class="sxs-lookup"><span data-stu-id="121b5-109">You can check the WSL version assigned to each of the Linux distributions you have installed by opening the PowerShell command line and entering the command (only available in [Windows Build 19041 or higher](ms-settings:windowsupdate)): `wsl -l -v`</span></span>

```bash
wsl --list --verbose
```

<span data-ttu-id="121b5-110">Para definir uma distribuição para ter suporte de qualquer versão do WSL, execute:</span><span class="sxs-lookup"><span data-stu-id="121b5-110">To set a distribution to be backed by either version of WSL please run:</span></span>

```bash
wsl --set-version <distribution name> <versionNumber>
```

<span data-ttu-id="121b5-111">Assegure-se de substituir `<distribution name>` pelo nome real da sua distribuição e `<versionNumber>` pelo número '1' ou '2'.</span><span class="sxs-lookup"><span data-stu-id="121b5-111">Make sure to replace `<distribution name>` with the actual name of your distribution and `<versionNumber>` with the number '1' or '2'.</span></span> <span data-ttu-id="121b5-112">Você pode retornar ao WSL 1 a qualquer momento executando o mesmo comando acima, mas substituindo “2” por “1”.</span><span class="sxs-lookup"><span data-stu-id="121b5-112">You can change back to WSL 1 at anytime by running the same command as above but replacing the '2' with a '1'.</span></span>

<span data-ttu-id="121b5-113">Além disso, se quiser tornar o WSL 2 sua arquitetura padrão, você poderá fazê-lo com este comando:</span><span class="sxs-lookup"><span data-stu-id="121b5-113">Additionally, if you want to make WSL 2 your default architecture you can do so with this command:</span></span>

```bash
wsl --set-default-version 2
```

<span data-ttu-id="121b5-114">Isso definirá a versão de qualquer nova distribuição instalada no WSL 2.</span><span class="sxs-lookup"><span data-stu-id="121b5-114">This will set the version of any new distribution installed to WSL 2.</span></span>

## `wsl.exe`

<span data-ttu-id="121b5-115">Abaixo está uma lista que contém todas as opções ao usar o `wsl.exe` da versão 1903 do Windows.</span><span class="sxs-lookup"><span data-stu-id="121b5-115">Below is a list containing all options when using `wsl.exe` as of Windows Version 1903.</span></span>

<span data-ttu-id="121b5-116">Usando: `wsl [Argument] [Options...] [CommandLine]`</span><span class="sxs-lookup"><span data-stu-id="121b5-116">Using: `wsl [Argument] [Options...] [CommandLine]`</span></span>

### <a name="arguments-for-running-linux-commands"></a><span data-ttu-id="121b5-117">Argumentos para executar comandos do Linux</span><span class="sxs-lookup"><span data-stu-id="121b5-117">Arguments for running Linux commands</span></span>

* <span data-ttu-id="121b5-118">**Sem argumentos**</span><span class="sxs-lookup"><span data-stu-id="121b5-118">**Without arguments**</span></span>

  <span data-ttu-id="121b5-119">Se nenhuma linha de comando for fornecida, o wsl.exe iniciará o shell padrão.</span><span class="sxs-lookup"><span data-stu-id="121b5-119">If no command line is provided, wsl.exe launches the default shell.</span></span>

* <span data-ttu-id="121b5-120">**--exec, -e \<CommandLine>**</span><span class="sxs-lookup"><span data-stu-id="121b5-120">**--exec, -e \<CommandLine>**</span></span>
  
  <span data-ttu-id="121b5-121">Execute o comando especificado sem usar o shell do Linux padrão.</span><span class="sxs-lookup"><span data-stu-id="121b5-121">Execute the specified command without using the default Linux shell.</span></span>

* **--**
  
  <span data-ttu-id="121b5-122">Passe a linha de comando restante do modo como ela está.</span><span class="sxs-lookup"><span data-stu-id="121b5-122">Pass the remaining command line as is.</span></span>

<span data-ttu-id="121b5-123">Os comandos acima também aceitam as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="121b5-123">The above commands also accept the following options:</span></span>

* <span data-ttu-id="121b5-124">**--distribution, -d \<Distro>**</span><span class="sxs-lookup"><span data-stu-id="121b5-124">**--distribution, -d \<Distro>**</span></span>

  <span data-ttu-id="121b5-125">Execute a distribuição especificada.</span><span class="sxs-lookup"><span data-stu-id="121b5-125">Run the specified distribution.</span></span>

* <span data-ttu-id="121b5-126">**--user, -u \<UserName>**</span><span class="sxs-lookup"><span data-stu-id="121b5-126">**--user, -u \<UserName>**</span></span>

  <span data-ttu-id="121b5-127">Execute como o usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="121b5-127">Run as the specified user.</span></span>

### <a name="arguments-for-managing-windows-subsystem-for-linux"></a><span data-ttu-id="121b5-128">Argumentos para gerenciar o Subsistema Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="121b5-128">Arguments for managing Windows Subsystem for Linux</span></span>

* <span data-ttu-id="121b5-129">**--export \<Distro> \<FileName>**</span><span class="sxs-lookup"><span data-stu-id="121b5-129">**--export \<Distro> \<FileName>**</span></span>
  
  <span data-ttu-id="121b5-130">Exporta a distribuição para um arquivo tar.</span><span class="sxs-lookup"><span data-stu-id="121b5-130">Exports the distribution to a tar file.</span></span> <span data-ttu-id="121b5-131">O nome de arquivo pode ser "-" para a saída padrão.</span><span class="sxs-lookup"><span data-stu-id="121b5-131">The filename can be - for standard output.</span></span>

* <span data-ttu-id="121b5-132">**--import \<Distro> \<InstallLocation> \<FileName>**</span><span class="sxs-lookup"><span data-stu-id="121b5-132">**--import \<Distro> \<InstallLocation> \<FileName>**</span></span>
  
  <span data-ttu-id="121b5-133">Importa o arquivo tar especificado como uma nova distribuição.</span><span class="sxs-lookup"><span data-stu-id="121b5-133">Imports the specified tar file as a new distribution.</span></span> <span data-ttu-id="121b5-134">O nome de arquivo pode ser "-" para a entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="121b5-134">The filename can be - for standard input.</span></span>

* <span data-ttu-id="121b5-135">**--list, -l [Options]**</span><span class="sxs-lookup"><span data-stu-id="121b5-135">**--list, -l [Options]**</span></span>
  
  <span data-ttu-id="121b5-136">Lista as distribuições.</span><span class="sxs-lookup"><span data-stu-id="121b5-136">Lists distributions.</span></span>

  <span data-ttu-id="121b5-137">Opções:</span><span class="sxs-lookup"><span data-stu-id="121b5-137">Options:</span></span>
  * <span data-ttu-id="121b5-138">**--all**</span><span class="sxs-lookup"><span data-stu-id="121b5-138">**--all**</span></span>

    <span data-ttu-id="121b5-139">Liste todas as distribuições, incluindo distribuições que estão sendo instaladas ou desinstaladas no momento.</span><span class="sxs-lookup"><span data-stu-id="121b5-139">List all distributions, including distributions that are currently being installed or uninstalled.</span></span>

  * <span data-ttu-id="121b5-140">**--running**</span><span class="sxs-lookup"><span data-stu-id="121b5-140">**--running**</span></span>

    <span data-ttu-id="121b5-141">Liste somente as distribuições que estão em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="121b5-141">List only distributions that are currently running.</span></span>

* <span data-ttu-id="121b5-142">**--set-default, -s \<Distro>**</span><span class="sxs-lookup"><span data-stu-id="121b5-142">**--set-default, -s \<Distro>**</span></span>
  
  <span data-ttu-id="121b5-143">Define a distribuição como o padrão.</span><span class="sxs-lookup"><span data-stu-id="121b5-143">Sets the distribution as the default.</span></span>

* <span data-ttu-id="121b5-144">**--terminate, -t \<Distro>**</span><span class="sxs-lookup"><span data-stu-id="121b5-144">**--terminate, -t \<Distro>**</span></span>
  
  <span data-ttu-id="121b5-145">Termina a distribuição especificada.</span><span class="sxs-lookup"><span data-stu-id="121b5-145">Terminates the specified distribution.</span></span>

* <span data-ttu-id="121b5-146">**--unregister \<Distro>**</span><span class="sxs-lookup"><span data-stu-id="121b5-146">**--unregister \<Distro>**</span></span>
  
  <span data-ttu-id="121b5-147">Cancelar o registro da distribuição.</span><span class="sxs-lookup"><span data-stu-id="121b5-147">Un-register the distribution.</span></span>

* <span data-ttu-id="121b5-148">**--help** Exiba as informações de uso.</span><span class="sxs-lookup"><span data-stu-id="121b5-148">**--help** Display usage information.</span></span>

## <a name="additional-commands"></a><span data-ttu-id="121b5-149">Comandos adicionais</span><span class="sxs-lookup"><span data-stu-id="121b5-149">Additional Commands</span></span>

<span data-ttu-id="121b5-150">Também há comandos históricos para interagir com o Subsistema Windows para Linux.</span><span class="sxs-lookup"><span data-stu-id="121b5-150">There are also historic commands to interact with the Windows Subsystem for Linux.</span></span> <span data-ttu-id="121b5-151">Sua funcionalidade é englobada no `wsl.exe`, mas ainda estão disponíveis para uso.</span><span class="sxs-lookup"><span data-stu-id="121b5-151">Their functionality is encompassed within `wsl.exe`, but they are still available for use.</span></span>

### `wslconfig.exe`

<span data-ttu-id="121b5-152">Esse comando permite que você configure a distribuição do WSL.</span><span class="sxs-lookup"><span data-stu-id="121b5-152">This command lets you configure your WSL distribution.</span></span> <span data-ttu-id="121b5-153">Veja abaixo uma lista das opções.</span><span class="sxs-lookup"><span data-stu-id="121b5-153">Below is a list of its options.</span></span>

<span data-ttu-id="121b5-154">Usando: `wslconfig [Argument] [Options...]`</span><span class="sxs-lookup"><span data-stu-id="121b5-154">Using: `wslconfig [Argument] [Options...]`</span></span>

#### <a name="arguments"></a><span data-ttu-id="121b5-155">Argumentos</span><span class="sxs-lookup"><span data-stu-id="121b5-155">Arguments</span></span>

* <span data-ttu-id="121b5-156">**/l, /list [Options]**</span><span class="sxs-lookup"><span data-stu-id="121b5-156">**/l, /list [Options]**</span></span>
  
  <span data-ttu-id="121b5-157">Lista as distribuições registradas.</span><span class="sxs-lookup"><span data-stu-id="121b5-157">Lists registered distributions.</span></span>
  
<span data-ttu-id="121b5-158">Opções:</span><span class="sxs-lookup"><span data-stu-id="121b5-158">Options:</span></span>

* <span data-ttu-id="121b5-159">**/all** Como opção, liste todas as distribuições, incluindo distribuições que estão sendo instaladas ou desinstaladas no momento.</span><span class="sxs-lookup"><span data-stu-id="121b5-159">**/all** Optionally list all distributions, including distributions that are currently being installed or uninstalled.</span></span>

* <span data-ttu-id="121b5-160">**/running** Liste somente as distribuições que estão em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="121b5-160">**/running** List only distributions that are currently running.</span></span>

* <span data-ttu-id="121b5-161">**/s, /setdefault \<Distro>** Define a distribuição como o padrão.</span><span class="sxs-lookup"><span data-stu-id="121b5-161">**/s, /setdefault \<Distro>** Sets the distribution as the default.</span></span>

* <span data-ttu-id="121b5-162">**/t, /terminate \<Distro>** Encerra a distribuição.</span><span class="sxs-lookup"><span data-stu-id="121b5-162">**/t, /terminate \<Distro>** Terminates the distribution.</span></span>

* <span data-ttu-id="121b5-163">**/u, /unregister \<Distro>** Cancela o registro da distribuição.</span><span class="sxs-lookup"><span data-stu-id="121b5-163">**/u, /unregister \<Distro>** Un-registers the distribution.</span></span>

* <span data-ttu-id="121b5-164">**/upgrade \<Distro>** Atualiza a distribuição para o formato do sistema de arquivos WslFs.</span><span class="sxs-lookup"><span data-stu-id="121b5-164">**/upgrade \<Distro>** Upgrades the distribution to the WslFs file system format.</span></span>

### `bash.exe`

<span data-ttu-id="121b5-165">Esse comando é usado para iniciar um shell Bash.</span><span class="sxs-lookup"><span data-stu-id="121b5-165">This command is used to start a bash shell.</span></span> <span data-ttu-id="121b5-166">Abaixo estão as opções que você pode usar com este comando.</span><span class="sxs-lookup"><span data-stu-id="121b5-166">Below are the options you can use with this command.</span></span>

<span data-ttu-id="121b5-167">Usando: `bash [Options...]`</span><span class="sxs-lookup"><span data-stu-id="121b5-167">Using: `bash [Options...]`</span></span>

* <span data-ttu-id="121b5-168">**Nenhuma opção fornecida**</span><span class="sxs-lookup"><span data-stu-id="121b5-168">**No Option given**</span></span>
  
  <span data-ttu-id="121b5-169">Inicia o shell Bash no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="121b5-169">Launches the Bash shell in the current directory.</span></span> <span data-ttu-id="121b5-170">Se o shell Bash não estiver instalado automaticamente, ele executará o `lxrun /install`</span><span class="sxs-lookup"><span data-stu-id="121b5-170">If the Bash shell is not installed automatically runs `lxrun /install`</span></span>

* **~**
  
  <span data-ttu-id="121b5-171">`bash ~` inicia o shell Bash no diretório base do usuário.</span><span class="sxs-lookup"><span data-stu-id="121b5-171">`bash ~` launches the bash shell into the user's home directory.</span></span>  <span data-ttu-id="121b5-172">Semelhante à execução de `cd ~`.</span><span class="sxs-lookup"><span data-stu-id="121b5-172">Similar to running `cd ~`.</span></span>

* <span data-ttu-id="121b5-173">**-c "\<command>"**</span><span class="sxs-lookup"><span data-stu-id="121b5-173">**-c "\<command>"**</span></span>
  
  <span data-ttu-id="121b5-174">Executa o comando, imprime a saída e sai de volta para o prompt de comando do Windows.</span><span class="sxs-lookup"><span data-stu-id="121b5-174">Runs the command, prints the output and exits back to the Windows command prompt.</span></span>

  <span data-ttu-id="121b5-175">Exemplo: `bash -c "ls"`.</span><span class="sxs-lookup"><span data-stu-id="121b5-175">Example:  `bash -c "ls"`.</span></span>

## <a name="deprecated-commands"></a><span data-ttu-id="121b5-176">Comandos preteridos</span><span class="sxs-lookup"><span data-stu-id="121b5-176">Deprecated Commands</span></span>

<span data-ttu-id="121b5-177">O `lxrun.exe` foi o primeiro comando usado para instalar e gerenciar o Subsistema Windows para Linux.</span><span class="sxs-lookup"><span data-stu-id="121b5-177">The `lxrun.exe` was the first command used to install and manage the Windows Subsystem for Linux.</span></span> <span data-ttu-id="121b5-178">Ele foi preterido no Windows 10 1803 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="121b5-178">It is deprecated as of Windows 10 1803 and later.</span></span>

<span data-ttu-id="121b5-179">O comando `lxrun.exe` pode ser usado para interagir diretamente com o WSL (Subsistema Windows para Linux).</span><span class="sxs-lookup"><span data-stu-id="121b5-179">The command `lxrun.exe` can be used to interact with the Windows Subsystem for Linux (WSL) directly.</span></span>  <span data-ttu-id="121b5-180">Esses comandos são instalados no diretório `\Windows\System32` e podem ser executados em um prompt de comando do Windows ou no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="121b5-180">These commands are installed into the `\Windows\System32` directory and may be run within a Windows command prompt or in PowerShell.</span></span>

| <span data-ttu-id="121b5-181">Comando</span><span class="sxs-lookup"><span data-stu-id="121b5-181">Command</span></span>                     | <span data-ttu-id="121b5-182">Descrição</span><span class="sxs-lookup"><span data-stu-id="121b5-182">Description</span></span>                     |
|:----------------------------|:---------------------------|
| `lxrun`                     | <span data-ttu-id="121b5-183">O comando lxrun é usado para gerenciar a instância do WSL.</span><span class="sxs-lookup"><span data-stu-id="121b5-183">The lxrun command is used to manage the WSL instance.</span></span> |
| `lxrun /install`            | <span data-ttu-id="121b5-184">Inicia o processo de download e instalação.</span><span class="sxs-lookup"><span data-stu-id="121b5-184">Starts the download and install process.</span></span> <br/> <span data-ttu-id="121b5-185">**/y** pode ser adicionado para ignorar todos os prompts.</span><span class="sxs-lookup"><span data-stu-id="121b5-185">**/y** may be added to bypass all prompts.</span></span>  <span data-ttu-id="121b5-186">O prompt de confirmação é automaticamente aceito e o usuário padrão é definido como raiz.</span><span class="sxs-lookup"><span data-stu-id="121b5-186">The confirmation prompt is automatically accepted and the default user is set to root.</span></span>          |
| `lxrun /uninstall`          | <span data-ttu-id="121b5-187">Desinstala e exclui a imagem do Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="121b5-187">Uninstalls and deletes the Ubuntu image.</span></span>  <span data-ttu-id="121b5-188">Por padrão, isso não remove o diretório base do Ubuntu do usuário.</span><span class="sxs-lookup"><span data-stu-id="121b5-188">By default this does not remove the user's Ubuntu home directory.</span></span> <br/> <span data-ttu-id="121b5-189">**/y** pode ser adicionado para aceitar automaticamente o prompt de confirmação</span><span class="sxs-lookup"><span data-stu-id="121b5-189">**/y** may be added to automatically accept the confirmation prompt</span></span> <br/><span data-ttu-id="121b5-190">**/full** desinstala e exclui o diretório base do Ubuntu do usuário</span><span class="sxs-lookup"><span data-stu-id="121b5-190">**/full** uninstalls and deletes the user's Ubuntu home directory</span></span>         |
| `lxrun /setdefaultuser <userName>`     | <span data-ttu-id="121b5-191">Define o Bash padrão no usuário do Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="121b5-191">Sets the default Bash on Ubuntu user.</span></span> <span data-ttu-id="121b5-192">Solicitará uma senha se o usuário especificado não existir.</span><span class="sxs-lookup"><span data-stu-id="121b5-192">Will prompt for a password if the specified user does not exist.</span></span>  <span data-ttu-id="121b5-193">Para obter mais informações, confira https://aka.ms/wslusers.</span><span class="sxs-lookup"><span data-stu-id="121b5-193">For more information visit: https://aka.ms/wslusers.</span></span> <br/> <span data-ttu-id="121b5-194">**/y** ignora a solicitação de senha.</span><span class="sxs-lookup"><span data-stu-id="121b5-194">**/y** Bypasses promping for the password.</span></span>  <span data-ttu-id="121b5-195">O usuário será criado sem uma senha.</span><span class="sxs-lookup"><span data-stu-id="121b5-195">The user will be created without a password.</span></span>|
| `lxrun /update`            | <span data-ttu-id="121b5-196">Atualiza o índice do pacote do subsistema</span><span class="sxs-lookup"><span data-stu-id="121b5-196">Updates the subsystem's package index</span></span>          |
