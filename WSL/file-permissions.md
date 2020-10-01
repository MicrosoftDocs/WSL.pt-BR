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
# <a name="file-permissions-for-wsl"></a>Permissões de arquivo para WSL

Esta página detalha como as permissões de arquivo do Linux são interpretadas no Subsistema do Windows para Linux, especialmente ao acessar recursos dentro do Windows no sistema de arquivos NT. Esta documentação pressupõe uma compreensão básica da [estrutura de permissões do sistema de arquivos do Linux](https://wiki.archlinux.org/index.php/File_permissions_and_attributes) e do [comando umask](https://en.wikipedia.org/wiki/Umask).

Ao acessar arquivos do Windows do WSL, as permissões de arquivo são calculadas usando as permissões do Windows ou são lidas de metadados que foram adicionados ao arquivo pelo WSL. Esses metadados não são habilitados por padrão.

## <a name="wsl-metadata-on-windows-files"></a>Metadados do WSL em arquivos do Windows

Quando os metadados são habilitados como uma opção de montagem no WSL, os atributos estendidos em arquivos do Windows NT podem ser adicionados e interpretados para fornecer permissões do sistema de arquivos do Linux.

O WSL pode adicionar quatro atributos estendidos do NTFS:

| Nome do atributo | Descrição |
| --- | --- |
| $LXUID | ID de proprietário do usuário |
| $LXGID | ID de proprietário do grupo |
| $LXMOD | Modo de arquivo (tipo e octals de permissão de sistemas de arquivos, por exemplo: 0777) |
| $LXDEV | Dispositivo, se for um arquivo de dispositivo |

Além disso, um arquivo que não seja um arquivo ou diretório regular (por exemplo, symlinks, FIFOs, dispositivos de bloco, soquetes UNIX e dispositivos de caracteres) também tem um [ponto de nova análise](/windows/win32/fileio/reparse-points) do NTFS. Isso torna muito mais rápida a determinação do tipo de arquivo em um determinado diretório sem precisar consultar seus atributos estendidos.

## <a name="file-access-scenarios"></a>Cenários de acesso a arquivos

Abaixo está uma descrição de como as permissões são determinadas ao acessar arquivos de diferentes modos usando o Subsistema do Windows para Linux.

### <a name="accessing-files-in-the-windows-drive-file-system-drvfs-from-linux"></a>Como acessar arquivos no DrvFS (sistema de arquivos da unidade) do Windows no Linux

Esses cenários ocorrem quando você está acessando os arquivos do Windows no WSL, provavelmente por meio de `/mnt/c`.

#### <a name="reading-file-permissions-from-an-existing-windows-file"></a>Como ler permissões de arquivo de um arquivo existente do Windows

O resultado depende de se o arquivo já tem metadados existentes.

##### <a name="drvfs-file-does-not-have-metadata-default"></a>O arquivo do DrvFS não tem metadados (padrão)

Se o arquivo não tiver metadados associados a ele, converteremos as permissões efetivas do usuário do Windows para ler/gravar/executar bits e defini-los com o mesmo valor para usuário, grupo e outros. Por exemplo, se a sua conta de usuário do Windows tiver acesso de leitura e execução, mas não tiver acesso de gravação no arquivo, isso será mostrado como `r-x` para usuário, grupo e outros. Se o arquivo tiver o atributo 'Somente leitura' definido no Windows, não concederemos acesso de gravação no Linux.

##### <a name="the-file-has-metadata"></a>O arquivo tem metadados

Se o arquivo tiver metadados presentes, bastará usar esses valores de metadados em vez de converter as permissões efetivas do usuário do Windows.

#### <a name="changing-file-permissions-on-an-existing-windows-file-using-chmod"></a>Como alterar as permissões de arquivo de um arquivo existente do Windows usando chmod

O resultado depende de se o arquivo já tem metadados existentes.

##### <a name="chmod-file-does-not-have-metadata-default"></a>O arquivo do chmod não tem metadados (padrão)

O chmod terá apenas um efeito. Se você remover todos os atributos de gravação de um arquivo, o atributo 'somente leitura' no arquivo do Windows será definido, pois esse é o mesmo comportamento que o CIFS (Common Internet File System), que é o cliente SMB (Protocolo SMB) no Linux.

##### <a name="chmod-file-has-metadata"></a>O arquivo do chmod tem metadados

O chmod será alterado ou adicionará metadados dependendo dos metadados existentes no arquivo. 

Tenha em mente que você não pode dar a si mesmo mais acesso do que o que tem no Windows, mesmo que os metadados indiquem que é o caso. Por exemplo, você pode definir os metadados para exibir que você tem permissões de gravação em um arquivo usando `chmod 777`, mas, se você tentar acessar esse arquivo, não conseguirá gravar nele. Isso acontece por causa da interoperabilidade, pois comandos de leitura ou gravação para arquivos do Windows são roteados por meio de suas permissões de usuário do Windows.

#### <a name="creating-a-file-in-drivefs"></a>Como criar um arquivo no DriveFS

O resultado depende de se os metadados estão habilitados.

##### <a name="metadata-is-not-enabled-default"></a>Os metadados não estão habilitados (padrão)

As permissões do Windows do arquivo recém-criado serão as mesmas que seriam caso o arquivo tivesse sido criado no Windows sem um descritor de segurança específico; ele herdará as permissões do pai.

##### <a name="metadata-is-enabled"></a>Os metadados estão habilitados

Os bits de permissão do arquivo são definidos para seguir o umask do Linux e o arquivo será salvo com metadados.

#### <a name="which-linux-user-and-linux-group-owns-the-file"></a>Qual usuário e grupo do Linux é proprietário do arquivo? 

O resultado depende de se o arquivo já tem metadados existentes.

##### <a name="user-file-does-not-have-metadata-default"></a>O arquivo do usuário não tem metadados (padrão)

No cenário padrão, ao montar automaticamente as unidades do Windows, especificamos que a UID (ID de usuário) de qualquer arquivo é definida como a ID de usuário do seu usuário do WSL e a GID (ID do grupo) é definida como a ID do grupo principal do seu usuário do WSL.

##### <a name="user-file-has-metadata"></a>O arquivo do usuário tem metadados

A UID e a GID especificadas nos metadados são aplicadas como proprietário do usuário e proprietário do grupo do arquivo.

### <a name="accessing-linux-files-from-windows-using-wsl"></a>Como acessar arquivos do Linux no Windows usando `\\wsl$`

O acesso a arquivos do Linux via `\\wsl$` usará o usuário padrão da sua distribuição do WSL. Portanto, um aplicativo do Windows acessando os arquivos do Linux terá as mesmas permissões que o usuário padrão.

#### <a name="creating-a-new-file"></a>Como criar um arquivo

O umask padrão é aplicado ao criar um arquivo dentro de uma distribuição do WSL no Windows. O umask padrão é `022`, ou seja, ele concede todas as permissões exceto as permissões de gravação a grupos e outros. 

### <a name="accessing-files-in-the-linux-root-file-system-from-linux"></a>Como acessar arquivos no sistema de arquivos raiz do Linux no Linux

Todos os arquivos criados, modificados ou acessados no sistema de arquivos raiz do Linux seguem convenções padrão do Linux, como aplicação de umask a um arquivo recém-criado.

## <a name="configuring-file-permissions"></a>Como configurar permissões de arquivo

Você pode configurar suas permissões de arquivo dentro de suas unidades do Windows usando as opções de montagem em wsl.conf. As opções de montagem permitem que você defina as máscaras de permissões `umask`, `dmask` e `fmask`. A `umask` é aplicada a todos os arquivos, a `dmask` é aplicada apenas aos diretórios e a `fmask` é aplicada apenas aos arquivos. Essas máscaras de permissão passam por uma operação OR lógica antes de serem aplicadas a arquivos, por exemplo: Se você tiver um valor `umask` de `023` e um valor `fmask` de `022`, a máscara de permissões resultante para os arquivos será `023`.

Confira o artigo [Definir configurações de inicialização por distribuição com wslconf](./wsl-config.md#configure-per-distro-launch-settings-with-wslconf) para obter instruções sobre como fazer isso.