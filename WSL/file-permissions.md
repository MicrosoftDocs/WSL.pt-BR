---
title: Permissões de arquivo
description: Como o WSL determina as permissões de arquivo no Windows
keywords: BashOnWindows, bash, wsl, wsl2, windows, windows subsystem for linux, windowssubsystem, ubuntu, debian, suse, windows 10, file, permissions
ms.date: 01/14/2020
ms.topic: article
ms.assetid: 7afaeacf-435a-4e58-bff0-a9f0d75b8a51
ms.localizationpriority: high
ms.openlocfilehash: 3de8553baf616ee8d5d45f0738615f83df952942
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413217"
---
# <a name="file-permissions-for-wsl"></a><span data-ttu-id="dbe42-104">Permissões de arquivo para WSL</span><span class="sxs-lookup"><span data-stu-id="dbe42-104">File Permissions for WSL</span></span>

<span data-ttu-id="dbe42-105">Esta página detalha como as permissões de arquivo do Linux são interpretadas no Subsistema do Windows para Linux, especialmente ao acessar recursos dentro do Windows no sistema de arquivos NT.</span><span class="sxs-lookup"><span data-stu-id="dbe42-105">This page details how Linux file permissions are interpreted across the Windows Subsystem for Linux, especially when accessing resources inside of Windows on the NT file system.</span></span> <span data-ttu-id="dbe42-106">Esta documentação pressupõe uma compreensão básica da [estrutura de permissões do sistema de arquivos do Linux](https://wiki.archlinux.org/index.php/File_permissions_and_attributes) e do [comando umask](https://en.wikipedia.org/wiki/Umask).</span><span class="sxs-lookup"><span data-stu-id="dbe42-106">This documentation assumes a basic understanding of the [Linux file system permissions structure](https://wiki.archlinux.org/index.php/File_permissions_and_attributes) and the [umask command](https://en.wikipedia.org/wiki/Umask).</span></span>

<span data-ttu-id="dbe42-107">Ao acessar arquivos do Windows do WSL, as permissões de arquivo são calculadas usando as permissões do Windows ou são lidas de metadados que foram adicionados ao arquivo pelo WSL.</span><span class="sxs-lookup"><span data-stu-id="dbe42-107">When accessing Windows files from WSL the file permissions are either calculated from Windows permissions, or are read from metadata that has been added to the file by WSL.</span></span> <span data-ttu-id="dbe42-108">Esses metadados não são habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="dbe42-108">This metadata is not enabled by default.</span></span>

## <a name="wsl-metadata-on-windows-files"></a><span data-ttu-id="dbe42-109">Metadados do WSL em arquivos do Windows</span><span class="sxs-lookup"><span data-stu-id="dbe42-109">WSL metadata on Windows files</span></span>

<span data-ttu-id="dbe42-110">Quando os metadados são habilitados como uma opção de montagem no WSL, os atributos estendidos em arquivos do Windows NT podem ser adicionados e interpretados para fornecer permissões do sistema de arquivos do Linux.</span><span class="sxs-lookup"><span data-stu-id="dbe42-110">When metadata is enabled as a mount option in WSL, extended attributes on Windows NT files can be added and interpreted to supply Linux file system permissions.</span></span>

<span data-ttu-id="dbe42-111">O WSL pode adicionar quatro atributos estendidos do NTFS:</span><span class="sxs-lookup"><span data-stu-id="dbe42-111">WSL can add four NTFS extended attributes:</span></span>

| <span data-ttu-id="dbe42-112">Nome do atributo</span><span class="sxs-lookup"><span data-stu-id="dbe42-112">Attribute Name</span></span> | <span data-ttu-id="dbe42-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="dbe42-113">Description</span></span> |
| --- | --- |
| <span data-ttu-id="dbe42-114">$LXUID</span><span class="sxs-lookup"><span data-stu-id="dbe42-114">$LXUID</span></span> | <span data-ttu-id="dbe42-115">ID de proprietário do usuário</span><span class="sxs-lookup"><span data-stu-id="dbe42-115">User Owner ID</span></span> |
| <span data-ttu-id="dbe42-116">$LXGID</span><span class="sxs-lookup"><span data-stu-id="dbe42-116">$LXGID</span></span> | <span data-ttu-id="dbe42-117">ID de proprietário do grupo</span><span class="sxs-lookup"><span data-stu-id="dbe42-117">Group Owner ID</span></span> |
| <span data-ttu-id="dbe42-118">$LXMOD</span><span class="sxs-lookup"><span data-stu-id="dbe42-118">$LXMOD</span></span> | <span data-ttu-id="dbe42-119">Modo de arquivo (tipo e octals de permissão de sistemas de arquivos, por exemplo: 0777)</span><span class="sxs-lookup"><span data-stu-id="dbe42-119">File mode (File systems permission octals and type, e.g: 0777)</span></span> |
| <span data-ttu-id="dbe42-120">$LXDEV</span><span class="sxs-lookup"><span data-stu-id="dbe42-120">$LXDEV</span></span> | <span data-ttu-id="dbe42-121">Dispositivo, se for um arquivo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="dbe42-121">Device, if it is a device file</span></span> |

<span data-ttu-id="dbe42-122">Além disso, um arquivo que não seja um arquivo ou diretório regular (por exemplo, symlinks, FIFOs, dispositivos de bloco, soquetes UNIX e dispositivos de caracteres) também tem um [ponto de nova análise](/windows/win32/fileio/reparse-points) do NTFS.</span><span class="sxs-lookup"><span data-stu-id="dbe42-122">Additionally, any file that is not a regular file or directory (e.g: symlinks, FIFOs, block devices, unix sockets, and character devices) also have an NTFS [reparse point](/windows/win32/fileio/reparse-points).</span></span> <span data-ttu-id="dbe42-123">Isso torna muito mais rápida a determinação do tipo de arquivo em um determinado diretório sem precisar consultar seus atributos estendidos.</span><span class="sxs-lookup"><span data-stu-id="dbe42-123">This makes it much faster to determine the kind of file in a given directory without having to query its extended attributes.</span></span>

## <a name="file-access-scenarios"></a><span data-ttu-id="dbe42-124">Cenários de acesso a arquivos</span><span class="sxs-lookup"><span data-stu-id="dbe42-124">File Access Scenarios</span></span>

<span data-ttu-id="dbe42-125">Abaixo está uma descrição de como as permissões são determinadas ao acessar arquivos de diferentes modos usando o Subsistema do Windows para Linux.</span><span class="sxs-lookup"><span data-stu-id="dbe42-125">Below is a description of how permissions are determined when accessing files in different ways using the Windows Subsystem for Linux.</span></span>

### <a name="accessing-files-in-the-windows-drive-file-system-drvfs-from-linux"></a><span data-ttu-id="dbe42-126">Como acessar arquivos no DrvFS (sistema de arquivos da unidade) do Windows no Linux</span><span class="sxs-lookup"><span data-stu-id="dbe42-126">Accessing Files in the Windows drive file system (DrvFS) from Linux</span></span>

<span data-ttu-id="dbe42-127">Esses cenários ocorrem quando você está acessando os arquivos do Windows no WSL, provavelmente por meio de `/mnt/c`.</span><span class="sxs-lookup"><span data-stu-id="dbe42-127">These scenarios occur when you are accessing your Windows files from WSL, most likely via `/mnt/c`.</span></span>

#### <a name="reading-file-permissions-from-an-existing-windows-file"></a><span data-ttu-id="dbe42-128">Como ler permissões de arquivo de um arquivo existente do Windows</span><span class="sxs-lookup"><span data-stu-id="dbe42-128">Reading file permissions from an existing Windows file</span></span>

<span data-ttu-id="dbe42-129">O resultado depende de se o arquivo já tem metadados existentes.</span><span class="sxs-lookup"><span data-stu-id="dbe42-129">The result depends on if the file already has existing metadata.</span></span>

##### <a name="drvfs-file-does-not-have-metadata-default"></a><span data-ttu-id="dbe42-130">O arquivo do DrvFS não tem metadados (padrão)</span><span class="sxs-lookup"><span data-stu-id="dbe42-130">DrvFS file does not have metadata (default)</span></span>

<span data-ttu-id="dbe42-131">Se o arquivo não tiver metadados associados a ele, converteremos as permissões efetivas do usuário do Windows para ler/gravar/executar bits e defini-los com o mesmo valor para usuário, grupo e outros.</span><span class="sxs-lookup"><span data-stu-id="dbe42-131">If the file has no metadata associated with it then we translate the effective permissions of the Windows user to read/write/execute bits and set them to the this as the same value for user, group, and other.</span></span> <span data-ttu-id="dbe42-132">Por exemplo, se a sua conta de usuário do Windows tiver acesso de leitura e execução, mas não tiver acesso de gravação no arquivo, isso será mostrado como `r-x` para usuário, grupo e outros.</span><span class="sxs-lookup"><span data-stu-id="dbe42-132">For example, if your Windows user account has read and execute access but not write access to the file then this will be shown as `r-x` for user, group and other.</span></span> <span data-ttu-id="dbe42-133">Se o arquivo tiver o atributo 'Somente leitura' definido no Windows, não concederemos acesso de gravação no Linux.</span><span class="sxs-lookup"><span data-stu-id="dbe42-133">If the file has the 'Read Only' attribute set in Windows then we do not grant write access in Linux.</span></span>

##### <a name="the-file-has-metadata"></a><span data-ttu-id="dbe42-134">O arquivo tem metadados</span><span class="sxs-lookup"><span data-stu-id="dbe42-134">The file has metadata</span></span>

<span data-ttu-id="dbe42-135">Se o arquivo tiver metadados presentes, bastará usar esses valores de metadados em vez de converter as permissões efetivas do usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="dbe42-135">If the file has metadata present, we simply use those metadata values instead of translating effective permissions of the Windows user.</span></span>

#### <a name="changing-file-permissions-on-an-existing-windows-file-using-chmod"></a><span data-ttu-id="dbe42-136">Como alterar as permissões de arquivo de um arquivo existente do Windows usando chmod</span><span class="sxs-lookup"><span data-stu-id="dbe42-136">Changing file permissions on an existing Windows file using chmod</span></span>

<span data-ttu-id="dbe42-137">O resultado depende de se o arquivo já tem metadados existentes.</span><span class="sxs-lookup"><span data-stu-id="dbe42-137">The result depends on if the file already has existing metadata.</span></span>

##### <a name="chmod-file-does-not-have-metadata-default"></a><span data-ttu-id="dbe42-138">O arquivo do chmod não tem metadados (padrão)</span><span class="sxs-lookup"><span data-stu-id="dbe42-138">chmod file does not have metadata (default)</span></span>

<span data-ttu-id="dbe42-139">O chmod terá apenas um efeito. Se você remover todos os atributos de gravação de um arquivo, o atributo 'somente leitura' no arquivo do Windows será definido, pois esse é o mesmo comportamento que o CIFS (Common Internet File System), que é o cliente SMB (Protocolo SMB) no Linux.</span><span class="sxs-lookup"><span data-stu-id="dbe42-139">Chmod will only have one effect, if you remove all the write attributes of a file then the 'read only' attribute on the Windows file will be set, since this is the same behaviour as CIFS (Common Internet File System) which is the SMB (Server Message Block) client in Linux.</span></span>

##### <a name="chmod-file-has-metadata"></a><span data-ttu-id="dbe42-140">O arquivo do chmod tem metadados</span><span class="sxs-lookup"><span data-stu-id="dbe42-140">chmod file has metadata</span></span>

<span data-ttu-id="dbe42-141">O chmod será alterado ou adicionará metadados dependendo dos metadados existentes no arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbe42-141">Chmod will change or add metadata depending on the file's already existing metadata.</span></span> 

<span data-ttu-id="dbe42-142">Tenha em mente que você não pode dar a si mesmo mais acesso do que o que tem no Windows, mesmo que os metadados indiquem que é o caso.</span><span class="sxs-lookup"><span data-stu-id="dbe42-142">Please keep in mind that you cannot give yourself more access than what you have on Windows, even if the metadata says that is the case.</span></span> <span data-ttu-id="dbe42-143">Por exemplo, você pode definir os metadados para exibir que você tem permissões de gravação em um arquivo usando `chmod 777`, mas, se você tentar acessar esse arquivo, não conseguirá gravar nele.</span><span class="sxs-lookup"><span data-stu-id="dbe42-143">For example, you could set the metadata to display that you have write permissions to a file using `chmod 777`, but if you tried to access that file you would still not be able to write to it.</span></span> <span data-ttu-id="dbe42-144">Isso acontece por causa da interoperabilidade, pois comandos de leitura ou gravação para arquivos do Windows são roteados por meio de suas permissões de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="dbe42-144">This is thanks to interopability, as any read or write commands to Windows files are routed through your Windows user permissions.</span></span>

#### <a name="creating-a-file-in-drivefs"></a><span data-ttu-id="dbe42-145">Como criar um arquivo no DriveFS</span><span class="sxs-lookup"><span data-stu-id="dbe42-145">Creating a file in DriveFS</span></span>

<span data-ttu-id="dbe42-146">O resultado depende de se os metadados estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="dbe42-146">The result depends on if metadata is enabled.</span></span>

##### <a name="metadata-is-not-enabled-default"></a><span data-ttu-id="dbe42-147">Os metadados não estão habilitados (padrão)</span><span class="sxs-lookup"><span data-stu-id="dbe42-147">Metadata is not enabled (default)</span></span>

<span data-ttu-id="dbe42-148">As permissões do Windows do arquivo recém-criado serão as mesmas que seriam caso o arquivo tivesse sido criado no Windows sem um descritor de segurança específico; ele herdará as permissões do pai.</span><span class="sxs-lookup"><span data-stu-id="dbe42-148">The Windows permissions of the newly created file will be the same as if you created the file in Windows without a specific security descriptor, it will inherit the parent's permissions.</span></span>

##### <a name="metadata-is-enabled"></a><span data-ttu-id="dbe42-149">Os metadados estão habilitados</span><span class="sxs-lookup"><span data-stu-id="dbe42-149">Metadata is enabled</span></span>

<span data-ttu-id="dbe42-150">Os bits de permissão do arquivo são definidos para seguir o umask do Linux e o arquivo será salvo com metadados.</span><span class="sxs-lookup"><span data-stu-id="dbe42-150">The file's permission bits are set to follow the Linux umask, and the file will be saved with metadata.</span></span>

#### <a name="which-linux-user-and-linux-group-owns-the-file"></a><span data-ttu-id="dbe42-151">Qual usuário e grupo do Linux é proprietário do arquivo?</span><span class="sxs-lookup"><span data-stu-id="dbe42-151">Which Linux user and Linux group owns the file?</span></span> 

<span data-ttu-id="dbe42-152">O resultado depende de se o arquivo já tem metadados existentes.</span><span class="sxs-lookup"><span data-stu-id="dbe42-152">The result depends on if the file already has existing metadata.</span></span>

##### <a name="user-file-does-not-have-metadata-default"></a><span data-ttu-id="dbe42-153">O arquivo do usuário não tem metadados (padrão)</span><span class="sxs-lookup"><span data-stu-id="dbe42-153">User file does not have metadata (default)</span></span>

<span data-ttu-id="dbe42-154">No cenário padrão, ao montar automaticamente as unidades do Windows, especificamos que a UID (ID de usuário) de qualquer arquivo é definida como a ID de usuário do seu usuário do WSL e a GID (ID do grupo) é definida como a ID do grupo principal do seu usuário do WSL.</span><span class="sxs-lookup"><span data-stu-id="dbe42-154">In the default scenario, when automounting Windows drives, we specify that the user ID (UID) for any file is set to the user ID of your WSL user and the group ID (GID) is set to the principal group ID of your WSL user.</span></span>

##### <a name="user-file-has-metadata"></a><span data-ttu-id="dbe42-155">O arquivo do usuário tem metadados</span><span class="sxs-lookup"><span data-stu-id="dbe42-155">User file has metadata</span></span>

<span data-ttu-id="dbe42-156">A UID e a GID especificadas nos metadados são aplicadas como proprietário do usuário e proprietário do grupo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbe42-156">The UID and GID specified in the metadata is applied as the user owner and group owner of the file.</span></span>

### <a name="accessing-linux-files-from-windows-using-wsl"></a><span data-ttu-id="dbe42-157">Como acessar arquivos do Linux no Windows usando `\\wsl$`</span><span class="sxs-lookup"><span data-stu-id="dbe42-157">Accessing Linux files from Windows using `\\wsl$`</span></span>

<span data-ttu-id="dbe42-158">O acesso a arquivos do Linux via `\\wsl$` usará o usuário padrão da sua distribuição do WSL.</span><span class="sxs-lookup"><span data-stu-id="dbe42-158">Accessing Linux files via `\\wsl$` will use the default user of your WSL distribution.</span></span> <span data-ttu-id="dbe42-159">Portanto, um aplicativo do Windows acessando os arquivos do Linux terá as mesmas permissões que o usuário padrão.</span><span class="sxs-lookup"><span data-stu-id="dbe42-159">Therefore any Windows app accessing Linux files will have the same permissions as the default user.</span></span>

#### <a name="creating-a-new-file"></a><span data-ttu-id="dbe42-160">Como criar um arquivo</span><span class="sxs-lookup"><span data-stu-id="dbe42-160">Creating a new file</span></span>

<span data-ttu-id="dbe42-161">O umask padrão é aplicado ao criar um arquivo dentro de uma distribuição do WSL no Windows.</span><span class="sxs-lookup"><span data-stu-id="dbe42-161">The default umask is applied when creating a new file inside of a WSL distribution from Windows.</span></span> <span data-ttu-id="dbe42-162">O umask padrão é `022`, ou seja, ele concede todas as permissões exceto as permissões de gravação a grupos e outros.</span><span class="sxs-lookup"><span data-stu-id="dbe42-162">The default umask is `022`, or in other words it allows all permissions except write permissions to groups and others.</span></span> 

### <a name="accessing-files-in-the-linux-root-file-system-from-linux"></a><span data-ttu-id="dbe42-163">Como acessar arquivos no sistema de arquivos raiz do Linux no Linux</span><span class="sxs-lookup"><span data-stu-id="dbe42-163">Accessing files in the Linux root file system from Linux</span></span>

<span data-ttu-id="dbe42-164">Todos os arquivos criados, modificados ou acessados no sistema de arquivos raiz do Linux seguem convenções padrão do Linux, como aplicação de umask a um arquivo recém-criado.</span><span class="sxs-lookup"><span data-stu-id="dbe42-164">Any files created, modified, or accessed in the Linux root file system follow standard Linux conventions, such as applying the umask to a newly created file.</span></span>

## <a name="configuring-file-permissions"></a><span data-ttu-id="dbe42-165">Como configurar permissões de arquivo</span><span class="sxs-lookup"><span data-stu-id="dbe42-165">Configuring file permissions</span></span>

<span data-ttu-id="dbe42-166">Você pode configurar suas permissões de arquivo dentro de suas unidades do Windows usando as opções de montagem em wsl.conf.</span><span class="sxs-lookup"><span data-stu-id="dbe42-166">You can configure your file permissions inside of your Windows drives using the mount options in wsl.conf.</span></span> <span data-ttu-id="dbe42-167">As opções de montagem permitem que você defina as máscaras de permissões `umask`, `dmask` e `fmask`.</span><span class="sxs-lookup"><span data-stu-id="dbe42-167">The mount options allow you to set `umask`, `dmask` and `fmask` permissions masks.</span></span> <span data-ttu-id="dbe42-168">A `umask` é aplicada a todos os arquivos, a `dmask` é aplicada apenas aos diretórios e a `fmask` é aplicada apenas aos arquivos.</span><span class="sxs-lookup"><span data-stu-id="dbe42-168">The `umask` is applied to all files, the `dmask` is applied just to directories and the `fmask` is applied just to files.</span></span> <span data-ttu-id="dbe42-169">Essas máscaras de permissão passam por uma operação OR lógica antes de serem aplicadas a arquivos, por exemplo: Se você tiver um valor `umask` de `023` e um valor `fmask` de `022`, a máscara de permissões resultante para os arquivos será `023`.</span><span class="sxs-lookup"><span data-stu-id="dbe42-169">These permission masks are then put through a logical OR operation when being applied to files, e.g: If you have a `umask` value of `023` and an `fmask` value of `022` then the resulting permissions mask for files will be `023`.</span></span>

<span data-ttu-id="dbe42-170">Confira o artigo [Definir configurações de inicialização por distribuição com wslconf](./wsl-config.md#configure-per-distro-launch-settings-with-wslconf) para obter instruções sobre como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="dbe42-170">Please see the [Configure per distro launch settings with wslconf](./wsl-config.md#configure-per-distro-launch-settings-with-wslconf) article for instructions on how to do this.</span></span>