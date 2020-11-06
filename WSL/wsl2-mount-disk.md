---
title: Introdução à montagem de um disco do Linux no WSL 2 (visualização)
description: Saiba como configurar uma montagem de disco no WSL 2 e como acessá-la.
keywords: WSL, Windows, windowssubsystem, GNU, Linux, Bash, disco, ext4, FileSystem, Mount
ms.date: 11/04/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 828f796839ff272261e98e88ca54a1af76471958
ms.sourcegitcommit: 70ce8f7472167b6d8d760d0c54dbaab67904f2a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2020
ms.locfileid: "93413681"
---
# <a name="get-started-mounting-a-linux-disk-in-wsl-2-preview"></a><span data-ttu-id="f82e0-104">Introdução à montagem de um disco do Linux no WSL 2 (visualização)</span><span class="sxs-lookup"><span data-stu-id="f82e0-104">Get started mounting a Linux disk in WSL 2 (preview)</span></span>

<span data-ttu-id="f82e0-105">Se você quiser acessar um formato de disco do Linux que não tem suporte do Windows, poderá usar o WSL 2 para montar o disco e acessar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f82e0-105">If you want to access a Linux disk format that isn't supported by Windows, you can use WSL 2 to mount your disk and access its content.</span></span>

<span data-ttu-id="f82e0-106">Este tutorial abordará as etapas para identificar o disco e a partição que serão anexados ao WSL2, como montá-los e como acessá-los.</span><span class="sxs-lookup"><span data-stu-id="f82e0-106">This tutorial will cover the steps to identify the disk and partition to attach to WSL2, how to mount them, and how to access them.</span></span>

> [!NOTE]
> <span data-ttu-id="f82e0-107">Você precisará estar no Windows 10 Build 20211 ou superior para acessar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="f82e0-107">You will need to be on Windows 10 Build 20211 or higher to access this feature.</span></span> <span data-ttu-id="f82e0-108">Você pode ingressar no [programa Windows insiders](https://insider.windows.com/) para obter as versões prévias mais recentes.</span><span class="sxs-lookup"><span data-stu-id="f82e0-108">You can join the [Windows Insiders Program](https://insider.windows.com/) to get the latest preview builds.</span></span>
> <span data-ttu-id="f82e0-109">O acesso de administrador é necessário para anexar um disco ao WSL 2.</span><span class="sxs-lookup"><span data-stu-id="f82e0-109">Administrator access is required to attach a disk to WSL 2.</span></span>

## <a name="identify-the-disk"></a><span data-ttu-id="f82e0-110">Identificar o disco</span><span class="sxs-lookup"><span data-stu-id="f82e0-110">Identify the disk</span></span>

<span data-ttu-id="f82e0-111">Para listar os discos disponíveis no Windows, execute:</span><span class="sxs-lookup"><span data-stu-id="f82e0-111">To list the available disks in Windows, run:</span></span>

```powershell
wmic diskdrive list brief
```

<span data-ttu-id="f82e0-112">Os caminhos dos discos estão disponíveis nas colunas ' DeviceID '.</span><span class="sxs-lookup"><span data-stu-id="f82e0-112">The disks paths are available under the 'DeviceID' columns.</span></span> <span data-ttu-id="f82e0-113">Geralmente sob o `\\.\PHYSICALDRIVE*` formato.</span><span class="sxs-lookup"><span data-stu-id="f82e0-113">Usually under the `\\.\PHYSICALDRIVE*` format.</span></span>

## <a name="list-and-select-the-partitions-to-mount-in-wsl-2"></a><span data-ttu-id="f82e0-114">Listar e selecionar as partições a serem montadas no WSL 2</span><span class="sxs-lookup"><span data-stu-id="f82e0-114">List and select the partitions to mount in WSL 2</span></span>

<span data-ttu-id="f82e0-115">Depois que o disco for identificado, execute:</span><span class="sxs-lookup"><span data-stu-id="f82e0-115">Once the disk is identified, run:</span></span>

```powershell
wsl --mount <DiskPath> --bare
```

<span data-ttu-id="f82e0-116">Isso tornará o disco disponível no WSL 2.</span><span class="sxs-lookup"><span data-stu-id="f82e0-116">This will make the disk available in WSL 2.</span></span>

<span data-ttu-id="f82e0-117">Uma vez anexado, a partição pode ser listada executando o seguinte comando dentro de WSL 2:</span><span class="sxs-lookup"><span data-stu-id="f82e0-117">Once attached, the partition can be listed by running the following command inside WSL 2:</span></span>

```powershell
lsblk
```

<span data-ttu-id="f82e0-118">Isso exibirá os dispositivos de bloco disponíveis e suas partições.</span><span class="sxs-lookup"><span data-stu-id="f82e0-118">This will display the available block devices and their partitions.</span></span>

<span data-ttu-id="f82e0-119">Dentro do Linux, um dispositivo de bloco é identificado como  `/dev/<Device><Partition>` .</span><span class="sxs-lookup"><span data-stu-id="f82e0-119">Inside Linux, a block device is identified as  `/dev/<Device><Partition>`.</span></span> <span data-ttu-id="f82e0-120">Por exemplo,/dev/sdb3, é o número de partição 3 do disco `sdb` .</span><span class="sxs-lookup"><span data-stu-id="f82e0-120">For example, /dev/sdb3, is the partition number 3 of disk `sdb`.</span></span>

<span data-ttu-id="f82e0-121">Saída de exemplo:</span><span class="sxs-lookup"><span data-stu-id="f82e0-121">Example output:</span></span>

```powershell
NAME   MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sdb      8:16   0    1G  0 disk
├─sdb2   8:18   0   50M  0 part
├─sdb3   8:19   0  873M  0 part
└─sdb1   8:17   0  100M  0 part
sdc      8:32   0  256G  0 disk /
sda      8:0    0  256G  0 disk
```

## <a name="identifying-the-filesystem-type"></a><span data-ttu-id="f82e0-122">Identificando o tipo de sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="f82e0-122">Identifying the filesystem type</span></span>

<span data-ttu-id="f82e0-123">Se você não souber o tipo de sistema de arquivos de um disco ou partição, poderá usar este comando:</span><span class="sxs-lookup"><span data-stu-id="f82e0-123">If you don't know the type of filesystem of a disk or partition, you can use this command:</span></span>

```powershell
blkid <BlockDevice>
```

<span data-ttu-id="f82e0-124">Isso produzirá o tipo de sistema de arquivos detectado (no `TYPE="<Filesystem>"` formato).</span><span class="sxs-lookup"><span data-stu-id="f82e0-124">This will output the detected filesystem type (under the `TYPE="<Filesystem>"` format).</span></span>

## <a name="mount-the-selected-partitions"></a><span data-ttu-id="f82e0-125">Montar as partições selecionadas</span><span class="sxs-lookup"><span data-stu-id="f82e0-125">Mount the selected partitions</span></span>

<span data-ttu-id="f82e0-126">Depois de identificar as partições que você deseja montar, execute este comando em cada partição:</span><span class="sxs-lookup"><span data-stu-id="f82e0-126">Once you have identified the partitions you want to mount, run this command on each partition:</span></span> 

```powershell
wsl --mount <DiskPath> --partition <PartitionNumber> --type <Filesystem>
```

> [!NOTE]
> <span data-ttu-id="f82e0-127">Se você quiser montar todo o disco como um único volume (ou seja, se o disco não estiver particionado), `--partition` poderá ser omitido.</span><span class="sxs-lookup"><span data-stu-id="f82e0-127">If you wish to mount the entire disk as a single volume (i.e. if the disk isn't partitioned), `--partition` can be omitted.</span></span>
> 
> <span data-ttu-id="f82e0-128">Se omitido, o tipo de sistema de arquivos padrão será "ext4".</span><span class="sxs-lookup"><span data-stu-id="f82e0-128">If omitted, the default filesystem type is "ext4".</span></span>

## <a name="access-the-disk-content"></a><span data-ttu-id="f82e0-129">Acessar o conteúdo do disco</span><span class="sxs-lookup"><span data-stu-id="f82e0-129">Access the disk content</span></span>

<span data-ttu-id="f82e0-130">Uma vez montado, o disco pode ser acessado sob o caminho apontado pelo valor de configuração: `automount.root` .</span><span class="sxs-lookup"><span data-stu-id="f82e0-130">Once mounted, the disk can be accessed under the path pointed to by the config value: `automount.root`.</span></span> <span data-ttu-id="f82e0-131">O valor padrão é `/mnt/wsl`.</span><span class="sxs-lookup"><span data-stu-id="f82e0-131">The default value is `/mnt/wsl`.</span></span>

<span data-ttu-id="f82e0-132">No Windows, o disco pode ser acessado no explorador de arquivos navegando até: `\\wsl$\\<Distro>\\<Mountpoint>` (escolha qualquer distribuição do Linux).</span><span class="sxs-lookup"><span data-stu-id="f82e0-132">From Windows, the disk can be accessed from File Explorer by navigating to: `\\wsl$\\<Distro>\\<Mountpoint>` (pick any Linux distribution).</span></span>

## <a name="unmount-the-disk"></a><span data-ttu-id="f82e0-133">Desmonte o disco</span><span class="sxs-lookup"><span data-stu-id="f82e0-133">Unmount the disk</span></span>

<span data-ttu-id="f82e0-134">Se você quiser desmontar e desanexar o disco do WSL 2, execute:</span><span class="sxs-lookup"><span data-stu-id="f82e0-134">If you want to unmount and detach the disk from WSL 2, run:</span></span>

```powershell
wsl --unmount <DiskPath>
```

## <a name="command-line-reference"></a><span data-ttu-id="f82e0-135">Referência de linha de comando</span><span class="sxs-lookup"><span data-stu-id="f82e0-135">Command line reference</span></span>

### <a name="mounting-a-specific-filesystem"></a><span data-ttu-id="f82e0-136">Montando um sistema de arquivos específico</span><span class="sxs-lookup"><span data-stu-id="f82e0-136">Mounting a specific filesystem</span></span>

<span data-ttu-id="f82e0-137">Por padrão, o WSL 2 tentará montar o dispositivo como ext4.</span><span class="sxs-lookup"><span data-stu-id="f82e0-137">By default, WSL 2 will attempt to mount the device as ext4.</span></span> <span data-ttu-id="f82e0-138">Para especificar outro sistema de arquivos, execute:</span><span class="sxs-lookup"><span data-stu-id="f82e0-138">To specify another filesystem, run:</span></span>

```powershell
wsl --mount <DiskPath> -t <FileSystem>
```

<span data-ttu-id="f82e0-139">Por exemplo, para montar um disco como Fat, execute:</span><span class="sxs-lookup"><span data-stu-id="f82e0-139">For example, to mount a disk as fat, run:</span></span>

```
wsl --mount <Diskpath> -t vfat
```

> [!NOTE]
> <span data-ttu-id="f82e0-140">Para listar os sistemas de filedisponíveis no WSL2, execute: `cat /proc/filesystems`</span><span class="sxs-lookup"><span data-stu-id="f82e0-140">To list the available filesystems in WSL2, run: `cat /proc/filesystems`</span></span>

### <a name="mounting-a-specific-partition"></a><span data-ttu-id="f82e0-141">Montando uma partição específica</span><span class="sxs-lookup"><span data-stu-id="f82e0-141">Mounting a specific partition</span></span>

<span data-ttu-id="f82e0-142">Por padrão, o WSL 2 tenta montar o disco inteiro.</span><span class="sxs-lookup"><span data-stu-id="f82e0-142">By default, WSL 2 attempts to mount the entire disk.</span></span> <span data-ttu-id="f82e0-143">Para montar uma partição específica, execute:</span><span class="sxs-lookup"><span data-stu-id="f82e0-143">To mount a specific partition, run:</span></span>

```
wsl --mount <Diskpath> -p <PartitionIndex>
```

<span data-ttu-id="f82e0-144">Isso só funcionará se o disco for MBR (registro mestre de inicialização) ou GPT (tabela de partição GUID).</span><span class="sxs-lookup"><span data-stu-id="f82e0-144">This only works if the disk is either MBR (Master Boot Record) or GPT (GUID Partition Table).</span></span> <span data-ttu-id="f82e0-145">[Leia sobre estilos de partição – MBR e GPT](/windows-server/storage/disk-management/initialize-new-disks#about-partition-styles---gpt-and-mbr).</span><span class="sxs-lookup"><span data-stu-id="f82e0-145">[Read about partition styles - MBR and GPT](/windows-server/storage/disk-management/initialize-new-disks#about-partition-styles---gpt-and-mbr).</span></span>

### <a name="specifying-mount-options"></a><span data-ttu-id="f82e0-146">Especificando opções de montagem</span><span class="sxs-lookup"><span data-stu-id="f82e0-146">Specifying mount options</span></span>

<span data-ttu-id="f82e0-147">Para especificar opções de montagem, execute:</span><span class="sxs-lookup"><span data-stu-id="f82e0-147">To specify mount options, run:</span></span>

```powershell
wsl --mount <DiskPath> -o <MountOptions>
```

<span data-ttu-id="f82e0-148">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="f82e0-148">Example:</span></span>

```powershell
wsl --mount <DiskPath> -o "data=ordered"
```

> [!NOTE]
> <span data-ttu-id="f82e0-149">Somente as opções específicas do sistema de arquivos têm suporte no momento.</span><span class="sxs-lookup"><span data-stu-id="f82e0-149">Only filesystem specific options are supported at this time.</span></span> <span data-ttu-id="f82e0-150">Opções genéricas como `ro, rw, noatime, ...` não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="f82e0-150">Generic options such as `ro, rw, noatime, ...` are not supported.</span></span>

### <a name="attaching-the-disk-without-mounting-it"></a><span data-ttu-id="f82e0-151">Anexando o disco sem montá-lo</span><span class="sxs-lookup"><span data-stu-id="f82e0-151">Attaching the disk without mounting it</span></span>

<span data-ttu-id="f82e0-152">Se o esquema de disco não tiver suporte de nenhuma das opções acima, você poderá anexar o disco ao WSL 2 sem montá-lo executando:</span><span class="sxs-lookup"><span data-stu-id="f82e0-152">If the disk scheme isn't supported by any of the above options, you can attach the disk to WSL 2 without mounting it by running:</span></span>

```powershell
wsl --mount <DiskPath> --bare
```

<span data-ttu-id="f82e0-153">Isso tornará o dispositivo de bloco disponível no WSL 2 para que ele possa ser montado manualmente a partir daí.</span><span class="sxs-lookup"><span data-stu-id="f82e0-153">This will make the block device available inside WSL 2 so it can be mounted manually from there.</span></span> <span data-ttu-id="f82e0-154">Use `lsblk` para listar os dispositivos de bloco disponíveis dentro do WSL 2.</span><span class="sxs-lookup"><span data-stu-id="f82e0-154">Use `lsblk` to list the available block devices inside WSL 2.</span></span>

### <a name="detaching-a-disk"></a><span data-ttu-id="f82e0-155">Desanexando um disco</span><span class="sxs-lookup"><span data-stu-id="f82e0-155">Detaching a disk</span></span>

<span data-ttu-id="f82e0-156">Para desanexar um disco do WSL 2, execute:</span><span class="sxs-lookup"><span data-stu-id="f82e0-156">To detach a disk from WSL 2, run:</span></span>

```powershell
wsl --unmount [DiskPath]
```

<span data-ttu-id="f82e0-157">Se `Diskpath` for omitido, todos os discos anexados serão desmontados e desanexados.</span><span class="sxs-lookup"><span data-stu-id="f82e0-157">If `Diskpath` is omitted, all attached disks are unmounted and detached.</span></span>

> [!NOTE]
> <span data-ttu-id="f82e0-158">Se um disco falhar ao desmontar, o WSL 2 poderá ser forçado a sair executando `wsl --shutdown` , o que desanexará o disco.</span><span class="sxs-lookup"><span data-stu-id="f82e0-158">If one disk fails to unmount, WSL 2 can be forced to exit by running `wsl --shutdown`, which will detach the disk.</span></span>

## <a name="mount-a-vhd-in-wsl"></a><span data-ttu-id="f82e0-159">Montar um VHD no WSL</span><span class="sxs-lookup"><span data-stu-id="f82e0-159">Mount a VHD in WSL</span></span>

<span data-ttu-id="f82e0-160">Você também pode montar arquivos de disco rígido virtual (VHD) em WSL usando `wsl --mount` .</span><span class="sxs-lookup"><span data-stu-id="f82e0-160">You can also mount virtual hard disk files (VHD) into WSL using `wsl --mount`.</span></span> <span data-ttu-id="f82e0-161">Para fazer isso, primeiro você precisa montar o VHD no Windows usando o [`Mount-VHD`](https://docs.microsoft.com/powershell/module/hyper-v/mount-vhd) comando no Windows.</span><span class="sxs-lookup"><span data-stu-id="f82e0-161">To do this, you first need to mount the VHD into Windows using the [`Mount-VHD`](https://docs.microsoft.com/powershell/module/hyper-v/mount-vhd) command in Windows.</span></span> <span data-ttu-id="f82e0-162">Certifique-se de executar esse comando em uma janela com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="f82e0-162">Be sure to run this command in a window with administrator privileges.</span></span> <span data-ttu-id="f82e0-163">Abaixo está um exemplo em que usamos esse comando e também geramos o caminho do disco</span><span class="sxs-lookup"><span data-stu-id="f82e0-163">Below is an example where we use this command, and also output the disk path</span></span> 

```powershell
Write-Output "\.\\PhysicalDrive$((Mount-VHD -Path .\ext4.vhdx -PassThru | Get-Disk).Number)"
```

<span data-ttu-id="f82e0-164">Você pode usar a saída acima para obter o caminho do disco para esse VHD e montá-lo em WSL seguindo as instruções na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="f82e0-164">You can use the output above to obtain the disk path for this VHD and mount that into WSL following the instructions in the previous section.</span></span>

<span data-ttu-id="f82e0-165">Você também pode usar essa técnica para montar e interagir com os discos rígidos virtuais de outros WSL distribuições, já que cada WSL 2 distribuição é armazenado por meio de um arquivo de disco rígido virtual chamado: `ext4.vhdx` .</span><span class="sxs-lookup"><span data-stu-id="f82e0-165">You can also use this technique to mount and interact with the virtual hard disks of other WSL distros, as each WSL 2 distro is stored via a virtual hard disk file called: `ext4.vhdx`.</span></span> <span data-ttu-id="f82e0-166">Por padrão, os VHDs para WSL 2 distribuições são armazenados neste caminho: `C:\Users\[user]\AppData\Local\Packages\[distro]\LocalState\[distroPackageName]` , tenha cuidado ao acessar esses arquivos de sistema, esse é um fluxo de trabalho de usuário avançado.</span><span class="sxs-lookup"><span data-stu-id="f82e0-166">By default the VHDs for WSL 2 distros are stored in this path: `C:\Users\[user]\AppData\Local\Packages\[distro]\LocalState\[distroPackageName]`, please exercise caution accessing these system files, this is a power user workflow.</span></span>

## <a name="limitations"></a><span data-ttu-id="f82e0-167">Limitações</span><span class="sxs-lookup"><span data-stu-id="f82e0-167">Limitations</span></span>

- <span data-ttu-id="f82e0-168">Neste momento, somente discos inteiros podem ser anexados ao WSL 2, o que significa que não é possível anexar apenas uma partição.</span><span class="sxs-lookup"><span data-stu-id="f82e0-168">At this time, only entire disks can be attached to WSL 2, meaning that it's not possible to attach only a partition.</span></span> <span data-ttu-id="f82e0-169">Concretamente, isso significa que não é possível usar o `wsl --mount` para ler uma partição no dispositivo de inicialização, pois esse dispositivo não pode ser desanexado do Windows.</span><span class="sxs-lookup"><span data-stu-id="f82e0-169">Concretely, this means that it's not possible to use `wsl --mount` to read a partition on the boot device, because that device can't be detached from Windows.</span></span>

- <span data-ttu-id="f82e0-170">As unidades flash USB não têm suporte no momento e não serão anexadas ao WSL 2.</span><span class="sxs-lookup"><span data-stu-id="f82e0-170">USB flash drives are not supported at this time and will fail to attach to WSL 2.</span></span> <span data-ttu-id="f82e0-171">No entanto, os discos USB têm suporte.</span><span class="sxs-lookup"><span data-stu-id="f82e0-171">USB disks are supported though.</span></span>

- <span data-ttu-id="f82e0-172">Somente os sistemas de sistema com suporte nativo no kernel podem ser montados pelo `wsl --mount` .</span><span class="sxs-lookup"><span data-stu-id="f82e0-172">Only filesystems that are natively supported in the kernel can be mounted by `wsl --mount`.</span></span> <span data-ttu-id="f82e0-173">Isso significa que não é possível usar drivers de sistema de arquivos instalados (como NTFS-3G, por exemplo) chamando `wsl --mount` .</span><span class="sxs-lookup"><span data-stu-id="f82e0-173">This means that it's not possible to use installed filesystem drivers (such as ntfs-3g for example) by calling `wsl --mount`.</span></span>
