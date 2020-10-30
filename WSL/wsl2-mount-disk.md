---
title: Introdução à montagem de um disco do Linux no WSL 2 (visualização)
description: Saiba como configurar uma montagem de disco no WSL 2 e como acessá-la.
keywords: WSL, Windows, windowssubsystem, GNU, Linux, Bash, disco, ext4, FileSystem, Mount
ms.date: 06/08/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 9ee71d7f76a9fd0e6b20293ef30b0808d56c43a1
ms.sourcegitcommit: cfb6c254322b8eb9c2c26e19ce970d4c046bc352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "93035722"
---
# <a name="get-started-mounting-a-linux-disk-in-wsl-2-preview"></a>Introdução à montagem de um disco do Linux no WSL 2 (visualização)

Se você quiser acessar um formato de disco do Linux que não tem suporte do Windows, poderá usar o WSL 2 para montar o disco e acessar seu conteúdo.

Este tutorial abordará as etapas para identificar o disco e a partição que serão anexados ao WSL2, como montá-los e como acessá-los.

> [!NOTE]
> Você precisará estar no Windows 10 Build 20211 ou superior para acessar esse recurso. Você pode ingressar no [programa Windows insiders](https://insider.windows.com/) para obter as versões prévias mais recentes.
> O acesso de administrador é necessário para anexar um disco ao WSL 2.

## <a name="identify-the-disk"></a>Identificar o disco

Para listar os discos disponíveis no Windows, execute:

```powershell
wmic diskdrive list brief
```

Os caminhos dos discos estão disponíveis nas colunas ' DeviceID '. Geralmente sob o `\\.\PHYSICALDRIVE*` formato.

## <a name="list-and-select-the-partitions-to-mount-in-wsl-2"></a>Listar e selecionar as partições a serem montadas no WSL 2

Depois que o disco for identificado, execute:

```powershell
wsl --mount <DiskPath> --bare
```

Isso tornará o disco disponível no WSL 2.

Uma vez anexado, a partição pode ser listada executando o seguinte comando dentro de WSL 2:

```powershell
lsblk
```

Isso exibirá os dispositivos de bloco disponíveis e suas partições.

Dentro do Linux, um dispositivo de bloco é identificado como  `/dev/<Device><Partition>` . Por exemplo,/dev/sdb3, é o número de partição 3 do disco `sdb` .

Saída de exemplo:

```powershell
NAME   MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sdb      8:16   0    1G  0 disk
├─sdb2   8:18   0   50M  0 part
├─sdb3   8:19   0  873M  0 part
└─sdb1   8:17   0  100M  0 part
sdc      8:32   0  256G  0 disk /
sda      8:0    0  256G  0 disk
```

## <a name="identifying-the-filesystem-type"></a>Identificando o tipo de sistema de arquivos

Se você não souber o tipo de sistema de arquivos de um disco ou partição, poderá usar este comando:

```powershell
blkid <BlockDevice>
```

Isso produzirá o tipo de sistema de arquivos detectado (no `TYPE="<Filesystem>"` formato).

## <a name="mount-the-selected-partitions"></a>Montar as partições selecionadas

Depois de identificar as partições que você deseja montar, execute este comando em cada partição: 

```powershell
wsl --mount <DiskPath> --partition <PartitionNumber> --type <Filesystem>
```

> [!NOTE]
> Se você quiser montar todo o disco como um único volume (ou seja, se o disco não estiver particionado), `--partition` poderá ser omitido.
> 
> Se omitido, o tipo de sistema de arquivos padrão será "ext4".

## <a name="access-the-disk-content"></a>Acessar o conteúdo do disco

Uma vez montado, o disco pode ser acessado sob o caminho apontado pelo valor de configuração: `automount.root` . O valor padrão é `/mnt/wsl`.

No Windows, o disco pode ser acessado no explorador de arquivos navegando até: `\\wsl$\\<Distro>\\<Mountpoint>` (escolha qualquer distribuição do Linux).

## <a name="unmount-the-disk"></a>Desmonte o disco

Se você quiser desmontar e desanexar o disco do WSL 2, execute:

```powershell
wsl --unmount <DiskPath>
```

## <a name="command-line-reference"></a>Referência de linha de comando

### <a name="mouting-a-specific-filesystem"></a>Montagem um sistema de arquivos específico

Por padrão, o WSL 2 tentará montar o dispositivo como ext4. Para especificar outro sistema de arquivos, execute:

```powershell
wsl --mount <DiskPath> -t <FileSystem>
```

Por exemplo, para montar um disco como Fat, execute:

```
wsl --mount <Diskpath> -t vfat
```

> [!NOTE]
> Para listar os sistemas de filedisponíveis no WSL2, execute: `cat /proc/filesystems`

### <a name="mouting-a-specific-partition"></a>Montagem uma partição específica

Por padrão, o WSL 2 tenta montar o disco inteiro. Para montar uma partição específica, execute:

```
wsl --mount <Diskpath> -p <PartitionIndex>
```

Isso só funcionará se o disco for MBR (registro mestre de inicialização) ou GPT (tabela de partição GUID). [Leia sobre estilos de partição – MBR e GPT](/windows-server/storage/disk-management/initialize-new-disks#about-partition-styles---gpt-and-mbr).

### <a name="specifying-mount-options"></a>Especificando opções de montagem

Para especificar opções de montagem, execute:

```powershell
wsl --mount <DiskPath> -o <MountOptions>
```

Exemplo:

```powershell
wsl --mount <DiskPath> -o "data=ordered"
```

> [!NOTE]
> Somente as opções específicas do sistema de arquivos têm suporte no momento. Opções genéricas como `ro, rw, noatime, ...` não são suportadas.

### <a name="attaching-the-disk-without-mounting-it"></a>Anexando o disco sem montá-lo

Se o esquema de disco não tiver suporte de nenhuma das opções acima, você poderá anexar o disco ao WSL 2 sem montá-lo executando:

```powershell
wsl --mount <DiskPath> --bare
```

Isso tornará o dispositivo de bloco disponível no WSL 2 para que ele possa ser montado manualmente a partir daí. Use `lsblk` para listar os dispositivos de bloco disponíveis dentro do WSL 2.

### <a name="detaching-a-disk"></a>Desanexando um disco

Para desanexar um disco do WSL 2, execute:

```powershell
wsl --unmount [DiskPath]
```

Se `Diskpath` for omitido, todos os discos anexados serão desmontados e desanexados.

> [!NOTE]
> Se um disco falhar ao desmontar, o WSL 2 poderá ser forçado a sair executando `wsl --shutdown` , o que desanexará o disco.

## <a name="limitations"></a>Limitações

- Neste momento, somente discos inteiros podem ser anexados ao WSL 2, o que significa que não é possível anexar apenas uma partição. Concretamente, isso significa que não é possível usar o `wsl --mount` para ler uma partição no dispositivo de inicialização, pois esse dispositivo não pode ser desanexado do Windows.

- As unidades flash USB não têm suporte no momento e não serão anexadas ao WSL 2. No entanto, os discos USB têm suporte.

- Somente os sistemas de sistema com suporte nativo no kernel podem ser montados pelo `wsl --mount` . Isso significa que não é possível usar drivers de sistema de arquivos instalados (como NTFS-3G, por exemplo) chamando `wsl --mount` .
