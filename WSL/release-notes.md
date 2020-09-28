---
title: Notas sobre a versão do subsistema Windows para Linux
description: Leia as notas sobre a versão do Subsistema do Windows para Linux. Essas notas sobre a versão incluem problemas corrigidos e são atualizadas semanalmente.
keywords: notas sobre a versão, wsl, windows, subsistema do windows para linux, windowssubsystem, ubuntu
author: benhillis
ms.date: 05/15/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: f79acbbc7f6436bae54c5160e769cababa76a341
ms.sourcegitcommit: 69fc9d3ca22cf3f07622db4cdf80c8ec751fe620
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90818688"
---
# <a name="release-notes-for-windows-subsystem-for-linux"></a>Notas sobre a versão do subsistema Windows para Linux

## <a name="build-20211"></a>Build 20211
Para obter informações gerais do Windows sobre o build 20211, visite o [blog do Windows](https://blogs.windows.com/windows-insider/2020/09/10/announcing-windows-10-insider-preview-build-20211/).

* Introduza `wsl.exe --mount` para montar discos físicos ou virtuais. Para obter mais informações, confira [Acessar sistemas de arquivos do Linux no Windows e no WSL 2](https://devblogs.microsoft.com/commandline/access-linux-filesystems-in-windows-and-wsl-2/).
* Conserte a falha no serviço LxssManager ao verificar se a VM está ociosa. [GH 5768]
* Suporte para arquivos VHD compactados. [GH 4103]
* Verifique se as bibliotecas de modo de usuário do Linux para c:\windows\system32\lxss\lib estão preservadas na atualização do sistema operacional. [GH 5848]
* A capacidade de listar as distribuições disponíveis que podem ser instaladas com `wsl --install --list-distributions` foi adicionada.
* Agora, as instâncias de WSL são encerradas quando o usuário faz logoff.

## <a name="build-20190"></a>Build 20190
Para obter informações gerais do Windows sobre o build 20190, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/08/12/announcing-windows-10-insider-preview-build-20190/).

* Consertar bug que impede a inicialização de instâncias WSL1. [GH 5633]
* Consertar o travamento ao redirecionar a saída do processo do Windows. [GH 5648]
* Adicionar a opção %userprofile%\\.wslconfig para controlar o tempo limite de ociosidade da VM (wsl2.vmIdleTimeout=<time_in_ms>).
* Dar suporte à inicialização de aliases de execução de aplicativo do WSL.
* O suporte para instalar as distribuições e o kernel do WSL2 em wsl.exe --install foi adicionado.

## <a name="build-20175"></a>Build 20175
Para obter informações gerais do Windows sobre o build 20175, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/07/22/announcing-windows-10-insider-preview-build-20175/).

* Ajuste a atribuição de memória padrão da VM WSL2 para ser 50% da memória do host ou 8 GB, o que for menor [GH 4166].
* Altere o prefixo \\\\wsl$ para \\\\wsl a fim de dar suporte à análise de URI. O antigo caminho \\\\wsl$ ainda é compatível.
* Habilite a virtualização aninhada para WSL2 por padrão em amd64. Você pode desabilitar isso por meio de %userprofile%\\.wslconfig ([wsl2] nestedVirtualization=false).
* Faça com que a demanda wsl.exe --update inicie o Microsoft Update.
* Dê suporte à renomeação em um arquivo somente leitura no DrvFs.
* Verifique se as mensagens de erro são sempre impressas na página de código correta.

## <a name="build-20150"></a>Build 20150
Para obter informações gerais do Windows sobre o build 20150, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/06/17/announcing-windows-10-insider-preview-build-20150/).

* Para obter informações sobre a computação GPU do WSL2, confira o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/06/17/announcing-windows-10-insider-preview-build-20150/).
* Introdução de wsl.exe – instalação da opção de linha de comando para configurar facilmente o WSL.
* Introdução de wsl.exe – atualização da opção de linha de comando para gerenciar atualizações do kernel WSL2. 
* Definição de WSL2 como o padrão.
* Aumento do tempo limite de desligamento normal da VM WSL2.
* Correção da condição de corrida virtio-9p ao mapear a memória do dispositivo.
* Não execução de um servidor 9p elevado se UAC estiver desabilitado.

## <a name="build-19640"></a>Build 19640
Para obter informações gerais do Windows sobre o build 19640, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/06/03/announcing-windows-10-insider-preview-build-19640/).

* [WSL2] Aprimoramentos de estabilidade para virtio-9p (drvfs).

## <a name="build-19555"></a>Build 19555
Para obter informações gerais do Windows sobre o build 19555, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2020/01/30/announcing-windows-10-insider-preview-build-19555/).

* [WSL2] Use um cgroup de memória para limitar a quantidade de memória usada pelas operações de instalação e conversão [GH 4669]
* Torne o wsl.exe presente quando o componente opcional do Subsistema do Windows para Linux não estiver habilitado para aprimorar a descoberta de recursos.
* Altere o wsl.exe para imprimir o texto de ajuda se o componente opcional do WSL não estiver instalado
* Corrija a condição de corrida ao criar instâncias
* Crie wslclient.dll que contém todas as funcionalidades de linha de comando
* Impeça falhas durante a interrupção do serviço LxssManagerUser
* Corrija a falha rápida wslapi.dll quando o parâmetro distroName for NULL

## <a name="build-19041"></a>Build 19041
Para obter informações gerais do Windows sobre o build 19041, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/12/10/announcing-windows-10-insider-preview-build-19041/).

* [WSL2] Limpe a máscara de sinal antes de iniciar os processos
* [WSL2] Atualize o kernel do Linux para 4.19.84
* Manipule a criação do symlink /etc/resolv.conf quando o symlink não for relativo

## <a name="build-19028"></a>Build 19028
Para obter informações gerais do Windows sobre o build 19028, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/11/19/announcing-windows-10-insider-preview-build-19028/).

* [WSL2] Atualização do kernel do Linux para 4.19.81
* [WSL2] Alteração da permissão padrão de /dev/net/tun para 0666 [GH 4629]
* [WSL2] Ajuste da quantidade padrão de memória atribuída à VM do Linux para 80% da memória do host
* [WSL2] Correção do servidor de interoperabilidade para lidar com as solicitações usando um tempo limite para que chamadores inválidos não possam interromper o servidor

## <a name="build-19018"></a>Build 19018
Para obter informações gerais do Windows sobre o build 19018, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/11/05/announcing-windows-10-insider-preview-build-19018/).

* [WSL2] Uso do cache=mmap como padrão em montagens 9p para corrigir aplicativos dotnet
* [WSL2] Correções para retransmissão de localhost [GH 4340]
* [WSL2] Introdução de uma montagem tmpfs compartilhada entre distribuições para compartilhar o estado entre elas
* Correção da restauração de uma unidade de rede persistente para \\\\wsl$

## <a name="build-19013"></a>Build 19013
Para obter informações gerais sobre o Windows no build 19013, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/10/29/announcing-windows-10-insider-preview-build-19013/).

* [WSL2] Melhorar o desempenho de memória da VM do utilitário WSL. A memória que não está mais em uso será liberada de volta para o host.
* [WSL2] Atualização da versão do kernel para 4.19.79. (adicione CONFIG_HIGH_RES_TIMERS, CONFIG_TASK_XACCT, CONFIG_TASK_IO_ACCOUNTING, CONFIG_SCHED_HRTICK e CONFIG_BRIDGE_VLAN_FILTERING).
* [WSL2] Corrija a retransmissão de entrada para lidar com casos em que stdin é um identificador de pipe que não está fechado [GH 4424]
* Faça a verificação de \\\\wsl$ case-insensitive.
```
[wsl2]
pageReporting = <bool>    # Enable or disable the free memory page reporting feature (default true).
idleThreshold = <integer> # Set the idle threshold for memory compaction, 0 disables the feature (default 1).
```

## <a name="build-19002"></a>Build 19002
Para obter informações gerais do Windows sobre o Build 19002, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/10/17/announcing-windows-10-insider-preview-build-19002/).

* [WSL] Correção de um problema com o tratamento de alguns caracteres Unicode: https://github.com/microsoft/terminal/issues/2770
* [WSL] Correção de casos raros em que distribuições podiam ter o registro cancelado se fossem iniciadas imediatamente após uma atualização de compilação a compilação.
* [WSL] Correção de um problema secundário com wsl.exe: desligamentos em que os timers de ociosidade da instância não foram cancelados.

## <a name="build-18995"></a>Build 18995
Para obter informações gerais do Windows sobre o build 18995, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/10/03/announcing-windows-10-insider-preview-build-18995/).

* [WSL2] Correção de um problema em que as montagens DrvFs pararam de funcionar após uma operação ter sido interrompida (por exemplo, ctrl-c) [GH 4377]
* [WSL2] Correção do tratamento de mensagens hvsocket muito grandes [GH 4105]
* [WSL2] Correção do problema com a interoperabilidade quando stdin é um arquivo [GH 4475]
* [WSL2] Correção da falha de serviço quando um estado de rede inesperado é encontrado [GH 4474]
* [WSL2] Consulta do nome da distribuição do servidor de interoperabilidade se o processo atual não tem a variável de ambiente
* [WSL2] Correção do problema com a interoperabilidade quando stdin é um arquivo
* [WSL2] Atualização da versão do kernel do Linux para 4.19.72
* [WSL2] Adição da capacidade de especificar outros parâmetros de linha de comando do kernel por meio de .wslconfig
```
[wsl2]
kernelCommandLine = <string> # Additional kernel command line arguments
```

## <a name="build-18990"></a>Build 18990
Para obter informações gerais do Windows sobre o Build 18990, acesse o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/09/24/announcing-windows-10-insider-preview-build-18990/).

* Melhora do desempenho das listagens de diretório em \\\\wsl$
* [WSL2] Injetar entropia de inicialização adicional [GH 4416]
* [WSL2] Correção para interoperabilidade do Windows ao usar su/sudo [GH 4465]

## <a name="build-18980"></a>Build 18980
Para obter informações gerais do Windows sobre o Build 18980, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/09/11/announcing-windows-10-insider-preview-build-18980/).

* Correção da leitura de symlinks que negam FILE_READ_DATA. Isso inclui todas as symlinks que o Windows cria para compatibilidade com versões anteriores, tais como "C:\Documentos e Configurações" e diversos symlinks no diretório de perfil do usuário
* Transformação do estado de sistema de arquivos inesperado em não fatal [GH 4334, 4305]
* [WSL2] Adição de suporte para arm64 se a CPU/firmware der suporte à virtualização
* [WSL2] Permissão para que usuários sem privilégios exibam o log do kernel
* [WSL2] Correção da retransmissão de saída quando os soquetes stdout/stderr tiverem sido fechados [GH 4375]
* [WSL2] Suporte para passagem de bateria e adaptador AC
* [WSL2] Atualização do kernel do Linux para 4.19.67
* Adição da capacidade de definir o nome de usuário padrão em /etc/wsl.conf:
```
[user]
default=<string>
```

## <a name="build-18975"></a>Build 18975
Para obter informações gerais do Windows sobre o Build 18975, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/09/06/announcing-windows-10-insider-preview-build-18975/).

* [WSL2] Corrigidos diversos problemas de confiabilidade do localhost [GH 4340]

## <a name="build-18970"></a>Build 18970
Para obter informações gerais do Windows sobre o Build 18970, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/08/29/announcing-windows-10-insider-preview-build-18970/).

* [WSL2] Sincronização da hora com a hora do host quando o sistema é retomado do estado de suspensão [GH 4245]
* [WSL2] Criar symlinks NT nos volumes do Windows quando possível.
* [WSL2] Criação de distribuições nos namespaces UTS, IPC, PID e Mount.
* [WSL2] Correção da retransmissão de porta localhost quando o servidor se associar ao localhost diretamente [GH 4353]
* [WSL2] Correção da interop quando a saída for redirecionada [GH 4337]
* [WSL2] Suporte à conversão de symlinks NT absolutos.
* [WSL2] Atualização do kernel para 4.19.59
* [WSL2] Definição correta da máscara de sub-rede para eth0.
* [WSL2] Alteração da lógica para interromper o loop de trabalho do console quando o evento de saída for sinalizado.
* [WSL2] Ejeção do vhd da distribuição quando a distribuição não está em execução.
* [WSL2] Correção da biblioteca de análise de configuração para manipular corretamente valores vazios.
* [WSL2] Dar suporte ao Docker Desktop criando montagens para múltiplas distribuições. Uma distribuição pode optar por adotar esse comportamento ao adicionar a linha a seguir ao arquivo /etc/wsl.conf:
```
[automount]
crossDistro = true
```

## <a name="build-18945"></a>Build 18945
Para obter informações gerais do Windows sobre o Build 18945, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/07/26/announcing-windows-10-insider-preview-build-18945/).

### <a name="wsl"></a>WSL
* [WSL2] Permissão para que soquetes TCP de escuta em WSL2 sejam acessíveis do host usando localhost:port
* [WSL2] Correções para falhas de instalação/conversão e diagnóstico adicional para rastrear problemas futuros [GH 4105] 
* [WSL2] Melhoria da capacidade de diagnóstico de problemas de rede WSL2
* [WSL2] Atualização da versão do kernel para 4.19.55
* [WSL2] Atualização do kernel com as opções de configuração necessárias para o Docker [GH 4165]
* [WSL2] Aumento do número de CPUs atribuídas à VM do utilitário leve para que seja o mesmo do host (anteriormente limitado em 8 por CONFIG_NR_CPUS na configuração do kernel) [GH 4137]
* [WSL2] Criação de um arquivo de permuta para a VM leve do WSL2
* [WSL2] Permissão para que as montagens de usuário fiquem visíveis por meio de \\\\wsl$\\distro (por exemplo, sshfs) [GH 4172]
* [WSL2] Melhoria do desempenho do sistema de arquivos 9p
* [WSL2] Garantia de que a ACL do VHD não aumente sem limite [GH 4126]
* [WSL2] Atualização da configuração do kernel para dar suporte a squashfs e xt_conntrack [GH 4107, 4123]
* [WSL2] Correção para a opção interop.enabled /etc/wsl.conf [GH 4140]
* [WSL2] Retorno de ENOTSUP se o sistema de arquivos não der suporte a EAs
* [WSL2] Correção do travamento de CopyFile com \\\\wsl$
* Alternância do umask padrão para 0022 e adição da configuração filesystem.umask a /etc/wsl.conf
* Correção de wslpath para resolver symlinks adequadamente, isso foi regredido em 19h1 [GH 4078]
* Introdução do arquivo %UserProfile%\\.wslconfig para ajuste de configurações WSL2
```
[wsl2]
kernel=<path>              # An absolute Windows path to a custom Linux kernel.
memory=<size>              # How much memory to assign to the WSL2 VM.
processors=<number>        # How many processors to assign to the WSL2 VM.
swap=<size>                # How much swap space to add to the WSL2 VM. 0 for no swap file.
swapFile=<path>            # An absolute Windows path to the swap vhd.
localhostForwarding=<bool> # Boolean specifying if ports bound to wildcard or localhost in the WSL2 VM should be connectable from the host via localhost:port (default true).

# <path> entries must be absolute Windows paths with escaped backslashes, for example C:\\Users\\Ben\\kernel
# <size> entries must be size followed by unit, for example 8GB or 512MB
```

## <a name="build-18917"></a>Build 18917
Para obter informações gerais do Windows sobre o Build 18917, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/06/12/announcing-windows-10-insider-preview-build-18917/).

### <a name="wsl"></a>WSL
* O WSL 2 já está disponível. Confira o [blog](https://devblogs.microsoft.com/commandline/wsl-2-is-now-available-in-windows-insiders/) para obter mais detalhes.
* Correção de uma regressão em que a inicialização de processos do Windows via symlinks não funcionou corretamente [GH 3999]
* Adição das opções wsl.exe --list --verbose, wsl.exe --list --quiet e wsl.exe --import --version a wsl.exe
* Adição da opção wsl.exe --shutdown
* Plano 9: Permissão para que a abertura de um diretório para gravação seja realizada com sucesso

## <a name="build-18890"></a>Build 18890
Para obter informações gerais do Windows sobre o Build 18890, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/05/01/announcing-windows-10-insider-preview-build-18890/).

### <a name="wsl"></a>WSL
* Vazamento de soquete sem bloqueio [GH 2913]
* A entrada de EOF para o terminal pode bloquear leituras subsequentes [GH 3421]
* Atualização do cabeçalho de resolv.conf para fazer referência a wsl.conf [discutido no GH 3928]
* Deadlock no código de exclusão de epoll [GH 3922]
* Manipulação de espaços em argumentos para --import e –export [GH 3932]
* A extensão de arquivos mmap não funciona corretamente [GH 3939]
* Correção do problema de o acesso ao ARM64 \\\\wsl$ não estar funcionando corretamente
* Adição de um ícone padrão melhor para wsl.exe

## <a name="build-18342"></a>Build 18342
Para obter informações gerais do Windows sobre o Build 18342, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/02/20/announcing-windows-10-insider-preview-build-18342/).

### <a name="wsl"></a>WSL
* Adicionamos a capacidade para os usuários acessarem arquivos do Linux em uma distribuição WSL do Windows. Esses arquivos podem ser acessados por meio da linha de comando e aplicativos do Windows (tais como Explorador de Arquivos, VSCode, etc.) também podem interagir com eles. Acesse seus arquivos navegando até \\\\wsl$\\<nome_da_distro> ou consulte uma lista de distribuições em execução navegando até \\\\wsl$
* Adição de marcas de informações de CPU adicionais e correção dos valores de Cpus_allowed[_list] [GH 2234]
* Suporte a exec de thread não líder [GH 3800]
* Tratamento de falhas de atualização de configuração como não fatais [GH 3785]
* Atualização de binfmt para lidar com deslocamentos adequadamente [GH 3768]
* Habilitação do mapeamento de unidades de rede para o Plano 9 [GH 3854]
* Suporte à conversão de caminhos Windows -> Linux e Linux -> Windows para montagens de associação
* Criação de seções somente leitura para mapeamentos em arquivos abertos como somente leitura

## <a name="build-18334"></a>Build 18334
Para obter informações gerais do Windows sobre o Build 18334, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2019/02/08/announcing-windows-10-insider-preview-build-18334/).

### <a name="wsl"></a>WSL
* Recriação da maneira como o fuso horário do Windows é mapeado para um fuso horário do Linux [GH 3747]
* Correção de vazamentos de memória e adição de novas funções de conversão de cadeia de caracteres [GH 3746]
* SIGCONT em um grupo de threads sem threads é um não operacional [GH 3741] 
* Exibição correta dos descritores de arquivo de epoll e de soquete em /proc/self/fd

## <a name="build-18305"></a>Build 18305
Para obter informações gerais do Windows sobre o Build 18305, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/12/19/announcing-windows-10-insider-preview-build-18305/).

### <a name="wsl"></a>WSL
* pthreads perdem o acesso a arquivos quando o thread primário sai [GH 3589]
* TIOCSCTTY deve ignorar o parâmetro "force", a menos que ele seja necessário [GH 3652]
* Melhorias na linha de comando do wsl.exe e adição de funcionalidade de importação/exportação.
```
Usage: wsl.exe [Argument] [Options...] [CommandLine]

Arguments to run Linux binaries:

    If no command line is provided, wsl.exe launches the default shell.

    --exec, -e <CommandLine>
        Execute the specified command without using the default Linux shell.

    --
        Pass the remaining command line as is.

Options:
    --distribution, -d <DistributionName>
        Run the specified distribution.

    --user, -u <UserName>
        Run as the specified user.

Arguments to manage Windows Subsystem for Linux:

    --export <DistributionName> <FileName>
        Exports the distribution to a tar file.
        The filename can be - for standard output.

    --import <DistributionName> <InstallLocation> <FileName>
        Imports the specified tar file as a new distribution.
        The filename can be - for standard input.

    --list, -l [Options]
        Lists distributions.

        Options:
            --all
                List all distributions, including distributions that are currently
                being installed or uninstalled.

            --running
                List only distributions that are currently running.

    -setdefault, -s <DistributionName>
        Sets the distribution as the default.

    --terminate, -t <DistributionName>
        Terminates the distribution.

    --unregister <DistributionName>
        Unregisters the distribution.

    --upgrade <DistributionName>
        Upgrades the distribution to the WslFs file system format.

    --help
        Display usage information.
```

## <a name="build-18277"></a>Build 18277
Para obter informações gerais do Windows sobre o Build 18277, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/11/07/announcing-windows-10-insider-preview-build-18277/).

### <a name="wsl"></a>WSL
* Correção do erro "essa interface não é compatível" introduzido no build 18272 [GH 3645]
* O sinalizador MNT_FORCE agora é ignorado para a syscall umount [GH 3605]
* Alternância da interop de WSL para usar a API CreatePseudoConsole oficial
* Nenhum valor de tempo limite mantido quando FUTEX_WAIT reinicializa

## <a name="build-18272"></a>Build 18272
Para obter informações gerais do Windows sobre o Build 18272, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/10/31/announcing-windows-10-insider-preview-build-18272/).

### <a name="wsl"></a>WSL
* **AVISO:** Há um problema nesse build que torna o WSL inoperante. Ao tentar iniciar a distribuição, você verá um erro "Não há suporte para essa interface". O problema foi corrigido e estará no build do Participante do Programa Windows Insider – Modo Rápido da próxima semana. Se você tiver instalado esse build, poderá reverter a versão para o build anterior do Windows usando "Voltar para a versão anterior do Windows 10" em Configurações->Atualização e Segurança->Recuperação.

## <a name="build-18267"></a>Build 18267
Para obter informações gerais do Windows sobre o Build 18267, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/10/24/announcing-windows-10-insider-preview-build-18267/).

### <a name="wsl"></a>WSL
* Correção do problema em que o processo zumbi pode não ser aproveitado e permanecer indefinidamente.
* WslRegisterDistribution trava se a mensagem de erro excede o comprimento máximo [GH 3592]
* Permissão para que o fsync tenha sucesso para arquivos somente leitura no DrvFs [GH 3556]
* Verificação de que os diretórios /bin e /sbin existem antes de criar symlinks internos [GH 3584]
* Adicionado um mecanismo de tempo limite de encerramento de instância para instâncias de WSL. O tempo limite está definido atualmente como 15 segundos, o que significa que a instância será encerrada 15 segundos após o último processo de WSL sair. Para encerrar uma distribuição imediatamente, use:
```
wslconfig.exe /terminate <DistributionName>
```

## <a name="build-17763-1809"></a>Build 17763 (1809)
Para obter informações gerais do Windows sobre o Build 17763, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).

### <a name="wsl"></a>WSL
* Verificação de permissão da syscall setpriority muito estrita para alterar a mesma prioridade de thread [GH 1838]
* Verificação de que o tempo de interrupção não polarizado é usado para o tempo de inicialização a fim de evitar retornar valores negativos para clock_gettime (CLOCK_BOOTTIME) [GH 3434]
* Manipulação de symlinks no interpretador binfmt de WSL [GH 3424]
* Melhor manipulação da limpeza do descritor de arquivo de líder do grupo de threads.
* Alternância do WSL para usar KeQueryInterruptTimePrecise em vez de KeQueryPerformanceCounter a fim de evitar o estouro [GH 3252]
* A anexação ptrace pode causar um valor retornado insatisfatório de chamadas do sistema [GH 1731]
* Correção de vários problemas relacionados ao AF_UNIX [GH 3371]
* Correção do problema que poderá causar falha de interop de WSL se o diretório de trabalho atual tiver menos de 5 caracteres [GH 3379]
* Impedimento de que um atraso de um segundo cause falhas em conexões de loopback para portas inexistentes [GH 3286]
* Adição do arquivo de stub /proc/sys/fs/file-max [GH 2893]
* Informações de escopo de IPV6 mais precisas.
* Suporte a PR_SET_PTRACER [GH 3053]
* O sistema de arquivos de pipe limpa inadvertidamente o evento epoll disparado da borda [GH 3276]
* O executável do Win32 iniciado via symlink NTFS não respeita o nome do symlink [GH 2909]
* Suporte a zumbis melhorado [GH 1353]
* Adição de entradas wsl.conf para controlar o comportamento de interop do Windows [GH 1493]
  ```
    [interop]

    enabled=false # enable launch of Windows binaries; default is true

    appendWindowsPath=false # append Windows path to $PATH variable; default is true
  ```
* Correção para getsockname nem sempre retornando tipo de família de soquetes UNIX [GH 1774]
* Adição de suporte para TIOCSTI [GH 1863]
* Soquetes sem bloqueio no processo de conexão devem retornar EAGAIN para tentativas de gravação [GH 2846]
* Suporte a interop em VHDs montados [GH 3246, 3291]
* Correção do problema de verificação de permissão na pasta raiz [GH 3304]
* Suporte limitado para os ioctls de teclado TTY KDGKBTYPE, KDGKBMODE e KDSKBMODE.
* Os aplicativos da interface do usuário do Windows devem ser executados mesmo quando iniciados em segundo plano.
* Adição da opção wsl-u ou --user [GH 1203]
* Correção de problemas de inicialização do WSL quando a inicialização rápida estiver habilitada [GH 2576]
* Os soquetes Unix precisam reter as credenciais de pares desconectados [GH 3183]
* Soquetes Unix sem bloqueio falhando indefinidamente com EAGAIN [GH 3191]
* case=off é o novo tipo de montagem de drvfs padrão [GH 2937, 3212, 3328]
    * Confira [blog](https://blogs.msdn.microsoft.com/commandline/2018/06/14/improved-per-directory-case-sensitivity-support-in-wsl/) para obter mais informações.
* Adição de wslconfig /terminate para interromper a execução de distribuições.
* Correção do problema com as entradas do menu de contexto do shell WSL que não manipulam corretamente caminhos com espaços.
* Exposição de diferenciação de maiúsculas e minúsculas por diretório como um atributo estendido
* ARM64: Emulação de operações de manutenção de cache. Resolução do [problema de dotnet](https://github.com/dotnet/core/issues/1561).
* DrvFs: apenas caracteres de escape de saída no intervalo privado que correspondem a um caractere de escape.
* Correção do erro OB1 (por um) na validação de tamanho do interpretador ELF [GH 3154]
* Timers absolutos do WSL com um tempo no passado não são disparados [GH 3091]
* Verificação de que os pontos de nova análise criados recentemente estão listados como tal no diretório pai.
* Criação de forma atômica de diretórios que diferenciam maiúsculas de minúsculas no DrvFs.
* Corrigido um problema adicional em que operações multi-threaded poderiam retornar ENOENT mesmo que o arquivo existisse. [GH 2712]
* Correção da falha de inicialização do WSL quando o UMCI está habilitado. [GH 3020]
* Adição do menu de contexto do Explorer para iniciar o WSL [GH 437, 603, 1836]. Para usá-lo, mantenha a tecla Shift pressionada e clique com o botão direito do mouse quando estiver em uma janela do Explorer.
* Correção do comportamento de não bloqueio de soquete do Unix [GH 2822, 3100]
* Correção do comando do NetLink suspenso, conforme relatado no GH 2026.
* Adição de suporte para os sinalizadores de propagação de montagem [GH 2911].
* Correção do problema com truncamento não causando eventos inotify [GH 2978].
* Adição da opção --exec para wsl.exe para invocar um único binário sem um shell.
* Adição da opção --distribution a wsl.exe para selecionar uma distribuição específica.
* Suporte limitado para dmesg. Os aplicativos agora podem fazer logon no dmesg. O driver do WSL registra informações limitadas no dmesg. No futuro, isso pode ser estendido para transportar outras informações/diagnósticos do driver.
    * Observação: atualmente, o dmesg é compatível por meio da interface do dispositivo `/dev/kmsg`. A interface syscall `syslog` ainda não é compatível. Assim sendo, algumas das opções de linha de comando de `dmesg`, tais como `-S` e `-C`, não funcionam.
* Alteração do GID e o modo padrão de dispositivos seriais para corresponder ao nativo [GH 3042]
* O DrvFs agora dá suporte a atributos estendidos.
    * Observação: O DrvFs tem algumas limitações sobre o nome dos atributos estendidos. Alguns caracteres (tais como '/', ': ' e '\*') não são permitidos e os nomes de atributos estendidos não diferenciam maiúsculas de minúsculas em DrvFs

## <a name="build-18252-skip-ahead"></a>Build 18252 (ignorar e prosseguir)
Para obter informações gerais do Windows sobre o Build 18252, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/10/03/announcing-windows-10-insider-preview-build-18252/).

### <a name="wsl"></a>WSL
* Mover os binários init e bsdtar para fora da dll do lxssmanager e para uma pasta de ferramentas separada
* Correção da corrida ao fechar o descritor de arquivo ao usar CLONE_FILES
* Manipulação de campos opcionais em /proc/pid/mountinfo ao converter caminhos do DrvFs
* Permissão para que o DrvFs mknod tenha êxito sem suporte de metadados para S_IFREG
* Os arquivos somente leitura criados no DrvFs devem ter o atributo readonly definido [GH 3411]
* Adição do auxiliar /sbin/mount.drvfs para lidar com a montagem do DrvFs
* Uso da renomeação POSIX no DrvFs.
* Permissão para a conversão de caminho em volumes sem um GUID de volume.

## <a name="build-17738-fast"></a>Build 17738 (rápido)
Para obter informações gerais do Windows sobre o Build 17738, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/08/14/announcing-windows-10-insider-preview-build-17738/).

### <a name="wsl"></a>WSL
* Verificação de permissão da syscall setpriority muito estrita para alterar a mesma prioridade de thread [GH 1838]
* Verificação de que o tempo de interrupção não polarizado é usado para o tempo de inicialização a fim de evitar retornar valores negativos para clock_gettime (CLOCK_BOOTTIME) [GH 3434]
* Manipulação de symlinks no interpretador binfmt de WSL [GH 3424]
* Melhor manipulação da limpeza do descritor de arquivo de líder do grupo de threads.

## <a name="build-17728-fast"></a>Build 17728 (rápido)
Para obter informações gerais do Windows sobre o Build 17728, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/07/31/announcing-windows-10-insider-preview-build-17728/).

### <a name="wsl"></a>WSL
* Alternância do WSL para usar KeQueryInterruptTimePrecise em vez de KeQueryPerformanceCounter a fim de evitar o estouro [GH 3252]
* A anexação ptrace pode causar um valor retornado insatisfatório de chamadas do sistema [GH 1731]
* Correção de vários problemas relacionados ao AF_UNIX [GH 3371]
* Correção do problema que poderá causar falha de interop de WSL se o diretório de trabalho atual tiver menos de 5 caracteres [GH 3379]

## <a name="build-18204-skip-ahead"></a>Build 18204 (ignorar e prosseguir)
Para obter informações gerais do Windows sobre o Build 18204, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/07/25/announcing-windows-10-insider-preview-build-17723-and-build-18204/).

### <a name="wsl"></a>WSL
* O sistema de arquivos de pipe limpa inadvertidamente o evento epoll disparado da borda [GH 3276]
* O executável do Win32 iniciado via symlink NTFS não respeita o nome do symlink [GH 2909]

## <a name="build-17723-fast"></a>Build 17723 (rápido)
Para obter informações gerais do Windows sobre o Build 17723, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/07/25/announcing-windows-10-insider-preview-build-17723-and-build-18204/).

### <a name="wsl"></a>WSL
* Impedimento de que um atraso de um segundo cause falhas em conexões de loopback para portas inexistentes [GH 3286]
* Adição do arquivo de stub /proc/sys/fs/file-max [GH 2893]
* Informações de escopo de IPV6 mais precisas.
* Suporte a PR_SET_PTRACER [GH 3053]
* O sistema de arquivos de pipe limpa inadvertidamente o evento epoll disparado da borda [GH 3276]
* O executável do Win32 iniciado via symlink NTFS não respeita o nome do symlink [GH 2909]

## <a name="build-17713"></a>Build 17713
Para obter informações gerais do Windows sobre o Build 17713, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/07/11/announcing-windows-10-insider-preview-build-17713/).

### <a name="wsl"></a>WSL
* Suporte a zumbis melhorado [GH 1353]
* Adição de entradas wsl.conf para controlar o comportamento de interop do Windows [GH 1493]
  ```
    [interop]

    enabled=false # enable launch of Windows binaries; default is true

    appendWindowsPath=false # append Windows path to $PATH variable; default is true
  ```
* Correção para getsockname nem sempre retornando tipo de família de soquetes UNIX [GH 1774]
* Adição de suporte para TIOCSTI [GH 1863]
* Soquetes sem bloqueio no processo de conexão devem retornar EAGAIN para tentativas de gravação [GH 2846]
* Suporte a interop em VHDs montados [GH 3246, 3291]
* Correção do problema de verificação de permissão na pasta raiz [GH 3304]
* Suporte limitado para os ioctls de teclado TTY KDGKBTYPE, KDGKBMODE e KDSKBMODE.
* Os aplicativos da interface do usuário do Windows devem ser executados mesmo quando iniciados em segundo plano.

## <a name="build-17704"></a>Build 17704
Para obter informações gerais do Windows sobre o Build 17704, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/06/27/announcing-windows-10-insider-preview-build-17704/).

### <a name="wsl"></a>WSL
* Adição da opção wsl-u ou --user [GH 1203]
* Correção de problemas de inicialização do WSL quando a inicialização rápida estiver habilitada [GH 2576]
* Os soquetes Unix precisam reter as credenciais de pares desconectados [GH 3183]
* Soquetes Unix sem bloqueio falhando indefinidamente com EAGAIN [GH 3191]
* case=off é o novo tipo de montagem de drvfs padrão [GH 2937, 3212, 3328]
    * Confira [blog](https://blogs.msdn.microsoft.com/commandline/2018/06/14/improved-per-directory-case-sensitivity-support-in-wsl/) para obter mais informações.
* Adição de wslconfig /terminate para interromper a execução de distribuições.

## <a name="build-17692"></a>Build 17692
Para obter informações gerais do Windows sobre o Build 17692, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/06/14/announcing-windows-10-insider-preview-build-17692).

### <a name="wsl"></a>WSL
* Correção do problema com as entradas do menu de contexto do shell WSL que não manipulam corretamente caminhos com espaços.
* Exposição de diferenciação de maiúsculas e minúsculas por diretório como um atributo estendido
* ARM64: Emulação de operações de manutenção de cache. Resolução do [problema de dotnet](https://github.com/dotnet/core/issues/1561).
* DrvFs: apenas caracteres de escape de saída no intervalo privado que correspondem a um caractere de escape.

## <a name="build-17686"></a>Build 17686
Para obter informações gerais do Windows sobre o Build 17686, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/06/06/announcing-windows-10-insider-preview-build-17686).

### <a name="wsl"></a>WSL
* Correção do erro OB1 (por um) na validação de tamanho do interpretador ELF [GH 3154]
* Timers absolutos do WSL com um tempo no passado não são disparados [GH 3091]
* Verificação de que os pontos de nova análise criados recentemente estão listados como tal no diretório pai.
* Criação de forma atômica de diretórios que diferenciam maiúsculas de minúsculas no DrvFs.

## <a name="build-17677"></a>Build 17677
Para obter informações gerais do Windows sobre o Build 17677, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/05/24/announcing-windows-10-insider-preview-build-17677/).

### <a name="wsl"></a>WSL
* Corrigido um problema adicional em que operações multi-threaded poderiam retornar ENOENT mesmo que o arquivo existisse. [GH 2712]
* Correção da falha de inicialização do WSL quando o UMCI está habilitado. [GH 3020]

## <a name="build-17666"></a>Build 17666
Para obter informações gerais do Windows sobre o Build 17666, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/05/09/announcing-windows-10-insider-preview-build-17666/).

### <a name="wsl"></a>WSL
#### <a name="warning-there-is-an-issue-preventing-wsl-from-running-on-some-amd-chipsets-gh-3134-a-fix-is-ready-and-making-its-way-to-the-insider-build-branch"></a>AVISO: Há um problema que impede a execução do WSL em alguns chipsets AMD [GH 3134]. Uma correção está pronta e preparando-se para o branch do Build do Insider.
* Adição do menu de contexto do Explorer para iniciar o WSL [GH 437, 603, 1836]. Para usá-lo, mantenha a tecla Shift pressionada e clique com o botão direito do mouse quando estiver em uma janela do Explorer.
* Correção do comportamento de não bloqueio de soquete do Unix [GH 2822, 3100]
* Correção do comando do NetLink suspenso, conforme relatado no GH 2026.
* Adição de suporte para os sinalizadores de propagação de montagem [GH 2911].
* Correção do problema com truncamento não causando eventos inotify [GH 2978].
* Adição da opção --exec para wsl.exe para invocar um único binário sem um shell.
* Adição da opção --distribution a wsl.exe para selecionar uma distribuição específica.

## <a name="build-17655-skip-ahead"></a>Build 17655 (ignorar e prosseguir)
Para obter informações gerais do Windows sobre o Build 17655, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/04/25/announcing-windows-10-insider-preview-build-17655-for-skip-ahead/).

### <a name="wsl"></a>WSL
* Suporte limitado para dmesg. Os aplicativos agora podem fazer logon no dmesg. O driver do WSL registra informações limitadas no dmesg. No futuro, isso pode ser estendido para transportar outras informações/diagnósticos do driver.
    * Observação: atualmente, o dmesg é compatível por meio da interface do dispositivo `/dev/kmsg`. A interface sycall `syslog` ainda não é compatível. Assim sendo, algumas das opções de linha de comando de `dmesg`, tais como `-S` e `-C`, não funcionam.
* Corrigido um problema em que operações multi-threaded poderiam retornar ENOENT mesmo que o arquivo existisse. [GH 2712]

## <a name="build-17639-skip-ahead"></a>Build 17639 (ignorar e prosseguir)
Para obter informações gerais do Windows sobre o Build 17639, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/04/04/announcing-windows-10-insider-preview-build-17639-for-skip-ahead/).

### <a name="wsl"></a>WSL
* Alteração do GID e o modo padrão de dispositivos seriais para corresponder ao nativo [GH 3042]
* O DrvFs agora dá suporte a atributos estendidos.
    * Observação: O DrvFs tem algumas limitações sobre o nome dos atributos estendidos. Em particular, alguns caracteres (tais como '/', ': ' e '\*') não são permitidos e os nomes de atributos estendidos não diferenciam maiúsculas de minúsculas em DrvFs

## <a name="build-17133-fast"></a>Build 17133 (rápido)
Para obter informações gerais do Windows sobre o Build 17133, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/03/27/announcing-windows-10-insider-preview-build-17133-for-fast/).

### <a name="wsl"></a>WSL
* Correção para o travamento no WSL. [GH 3039, 3034]

## <a name="build-17128-fast"></a>Build 17128 (rápido)
Para obter informações gerais do Windows sobre o Build 17128, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/03/23/announcing-windows-10-insider-preview-build-17128-for-fast/).

### <a name="wsl"></a>WSL
* Não

## <a name="build-17627-skip-ahead"></a>Build 17627 (ignorar e prosseguir)
Para obter informações gerais do Windows sobre o Build 17627, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/03/21/announcing-windows-10-insider-preview-build-17627-for-skip-ahead/).

### <a name="wsl"></a>WSL
* Adição de suporte para as operações que reconhecem o Futex PI. [GH 1006]
    * Observe que as prioridades não são atualmente um recurso WSL compatível para que haja limitações, mas o uso padrão deve ser desbloqueado.
* Suporte do Firewall do Windows a processos WSL. [GH 1852]
    * Por exemplo, para permitir que o processo Python WSL escute em qualquer porta, use o cmd do Windows com privilégios elevados: ```netsh.exe advfirewall firewall add rule name=wsl_python dir=in action=allow program="C:\users\<username>\appdata\local\packages\canonicalgrouplimited.ubuntuonwindows_79rhkp1fndgsc\localstate\rootfs\usr\bin\python2.7" enable=yes```
    * Para obter detalhes adicionais sobre como adicionar regras de firewall, confira este [link](https://support.microsoft.com/help/947709/how-to-use-the-netsh-advfirewall-firewall-context-instead-of-the-netsh)
* Respeitar o shell padrão do usuário ao usar wsl.exe. [GH 2372]
* Relatar todos os adaptadores de rede como Ethernet. [GH 2996]
* Melhor manipulação de arquivo /etc/passwd corrompido. [GH 3001]

### <a name="console"></a>Console
* Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17618-skip-ahead"></a>Build 17618 (ignorar e prosseguir)
Para obter informações gerais do Windows sobre o Build 17618, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/03/07/announcing-windows-10-insider-preview-build-17618-skip-ahead/).

### <a name="wsl"></a>WSL
* Introduzir a funcionalidade de pseudoconsole para interop NT [GH 988, 1366, 1433, 1542, 2370, 2406].
* O mecanismo de instalação herdado (lxrun. exe) foi preterido. O mecanismo compatível para a instalação de distribuições é por meio da Microsoft Store.

### <a name="console"></a>Console
* Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17110"></a>Build 17110
Para obter informações gerais do Windows sobre o Build 17110, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/02/27/announcing-windows-10-insider-preview-build-17110-fast/).

### <a name="wsl"></a>WSL
* Permitir que /init seja encerrado do Windows [GH 2928].
* Por padrão, o DrvFs agora usa a diferenciação de maiúsculas e minúsculas por diretório (equivalente à opção de montagem "case=dir").
    * O uso de "case=force" (o comportamento antigo) exige a configuração de uma chave do Registro. Execute o seguinte comando para habilitar "case=force" se você precisar usá-lo: reg add HKLM\SYSTEM\CurrentControlSet\Services\lxss /v DrvFsAllowForceCaseSensitivity /t REG_DWORD /d 1
    * Se você tiver diretórios existentes criados com WSL na versão anterior do Windows que precisem diferenciar maiúsculas de minúsculas, use fsutil.exe para marcá-los como com diferenciação de maiúsculas e minúsculas: fsutil.exe file setcasesensitiveinfo <path> enable
* Termine cadeias de caracteres retornadas da syscall uname com NULL.

### <a name="console"></a>Console
* Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17107"></a>Build 17107
Para obter informações gerais do Windows sobre o Build 17107, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/02/23/announcing-windows-10-insider-preview-build-17107-fast-ring/).

### <a name="wsl"></a>WSL
* Suporte a TCSETSF e TCSETSW nos pontos de extremidade mestre pty [GH 2552].
* A inicialização de processos de interop simultâneos pode resultar em EINVAL [GH 2813].
* Correção de PTRACE_ATTACH para mostrar o status de rastreamento adequado em/proc/pid/status.
* Correção da corrida em que os processos de curta duração clonados com os dois sinalizadores CLEARTID e SETTID podem ser encerrados sem limpar o endereço de TID.
* Exibir uma mensagem durante a atualização dos diretórios do sistema de arquivos do Linux ao mudar de um build anterior ao 17093. Para obter mais detalhes sobre as alterações do sistema de arquivos 17093, confira as notas sobre a versão para o [17093](https://github.com/MicrosoftDocs/WSL/blob/live/WSL/release-notes.md#build-17093).

### <a name="console"></a>Console
* Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17101"></a>Build 17101
Para obter informações gerais do Windows sobre o Build 17101, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/02/14/announcing-windows-10-insider-preview-build-17101-fast-build-17604-skip-ahead/).

### <a name="wsl"></a>WSL
* Suporte para signalfd. [GH 129]
* Suporte a nomes de arquivos que contêm caracteres NTFS ilícitos, codificando-os como caracteres Unicode privados. [GH 1514]
* A montagem automática fará fallback para somente leitura quando a gravação não for compatível. [GH 2603]
* Permissão para colagem de pares substitutos Unicode (como caracteres de Emoji). [GH 2765]
* Pseudoarquivos em /proc e /sys devem retornar prontidão para leitura e gravação de select, poll, epoll e outros. [GH 2838]
* Correção do problema que pode fazer com que o serviço entre em loop infinito quando o Registro foi adulterado ou está corrompido.
* Correção das mensagens do NetLink para trabalhar com a versão mais recente (upstream 4.14) do iproute2.

### <a name="console"></a>Console
* Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17093"></a>Build 17093
Para obter informações gerais do Windows sobre o Build 17093, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/02/07/announcing-windows-10-insider-preview-build-17093-pc/).

#### <a name="important"></a>Importante:
Ao iniciar o WSL pela primeira vez após atualizar para esse build, ele precisa executar um certo trabalho de atualização dos diretórios do sistema de arquivos do Linux. Isso pode levar vários minutos, então a inicialização do WSL pode parecer lenta. Isso só deve ocorrer uma vez para cada distribuição instalada por meio da loja.
* Suporte à diferenciação de maiúsculas e minúsculas melhorada no DrvFs.
    * O DrvFs agora dá suporte à diferenciação de maiúsculas e minúsculas por diretório. Esse é um novo sinalizador que pode ser definido em diretórios para indicar que todas as operações nesses diretórios devem ser tratadas como com diferenciação de maiúsculas de minúsculas, o que permite que até mesmo os aplicativos do Windows abram corretamente arquivos que diferem apenas por maiúsculas e minúsculas.
    * O DrvFs tem novas opções de montagem que controlam a diferenciação de maiúsculas e minúsculas em uma base por diretório
        * Case = Force: todos os diretórios são tratados como com diferenciação de maiúsculas de minúsculas (exceto a raiz da unidade). Os novos diretórios criados com o WSL são marcados como com diferenciação de maiúsculas de minúsculas. Esse é o comportamento herdado, exceto para marcação de novos diretórios como com diferenciação de maiúsculas de minúsculas.
        * case=dir: somente os diretórios com o sinalizador de diferenciação de maiúsculas e minúsculas por diretório são tratados como com diferenciação de maiúsculas e minúsculas; outros diretórios não diferenciam maiúsculas de minúsculas. Os novos diretórios criados com o WSL são marcados como com diferenciação de maiúsculas de minúsculas.
        * case=off: somente os diretórios com o sinalizador de diferenciação de maiúsculas e minúsculas por diretório são tratados como com diferenciação de maiúsculas e minúsculas; outros diretórios não diferenciam maiúsculas de minúsculas. Os novos diretórios criados com WSL são marcados como sem diferenciação de maiúsculas de minúsculas.
    * Observação: os diretórios criados pelo WSL em versões anteriores não têm esse sinalizador definido e, portanto, não serão tratados como diretórios que diferenciam maiúsculas de minúsculas se você usar a opção "case=dir". Uma maneira de definir esse sinalizador em diretórios existentes estará disponível em breve.
    * Exemplo de montagem com essas opções (para unidades existentes, você deve primeiro desmontar antes de poder montar com opções diferentes): sudo mount -t drvfs C: /mnt/c -o case=dir
    * Por enquanto, case=force ainda é a opção padrão. Isso será alterado para case=dir no futuro.
* Agora você pode usar barras invertidas em caminhos do Windows ao montar o DrvFs, por exemplo: sudo mount -t drvfs //server/share /mnt/share
* O WSL agora processa o arquivo/etc/fstab durante a inicialização da instância [GH 2636].
    * Isso é feito antes da montagem automática de unidades de DrvFs; todas as unidades que já foram montadas por fstab não serão remontadas automaticamente, permitindo que você altere o ponto de montagem de unidades específicas.
    * Esse comportamento pode ser desativado usando o wsl.conf.
* Os arquivos mount, mountinfo e mountstats em /proc escapam corretamente caracteres especiais, tais como barras invertidas e espaços [GH 2799]
* Arquivos especiais criados com o DrvFs, tais como links simbólicos do WSL, ou então FIFOs e soquetes quando os metadados estão habilitados, agora podem ser copiados e movidos do Windows.

#### <a name="wsl-is-more-configurable-with-wslconf"></a>O WSL é mais configurável com o wsl.conf
Adicionamos um método para que você configure automaticamente determinadas funcionalidades no WSL que serão aplicadas toda vez que você iniciar o subsistema. Isso inclui opções de montagem automática e configuração de rede. Saiba mais sobre isso em nossa postagem no blog em: https://aka.ms/wslconf

#### <a name="af_unix-allows-socket-connections-between-linux-processes-on-wsl-and-windows-native-processes"></a>O AF_UNIX permite conexões de soquete entre processos do Linux em WSL e em processos nativos do Windows
Os aplicativos do WSL e do Windows agora podem se comunicar entre si por meio de soquetes Unix. Imagine que você deseja executar um serviço no Windows e disponibilizá-lo para aplicativos do Windows e do WSL. Agora, isso é possível com os soquetes do UNIX. Leia mais em nossa postagem no blog em https://aka.ms/afunixinterop

### <a name="wsl"></a>WSL
* Suporte a mmap () com MAP_NORESERVE [GH 121, 2784]
* Suporte a CLONE_PTRACE e CLONE_UNTRACED [GH 121, 2781]
* Manipulação do sinal de encerramento não SIGCHLD no clone [GH 121, 2781]
* /proc/sys/fs/inotify/max_user_instances and /proc/sys/fs/inotify/max_user_watches de stub [GH 1705]
* Erro ao carregar binários ELF que contêm cabeçalhos de carga com deslocamentos diferentes de zero [GH 1884]
* Eliminação de todos os bytes de página à direita ao carregar imagens.
* Redução dos casos em que o execve encerra o processo silenciosamente

### <a name="console"></a>Console
* Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17083"></a>Build 17083
Para obter informações gerais do Windows sobre o Build 17083, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/01/24/announcing-windows-10-insider-preview-build-17083-for-pc/).

### <a name="wsl"></a>WSL
* Corrigida a verificação de bug relacionada a epoll [GH 2798, 2801, 2857]
* Corrigidos travamentos ao desativar a ASLR [GH 1185, 2870]
* Garantia de que as operações mmap parecem atômicas [GH 2732]

### <a name="console"></a>Console
* Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17074"></a>Build 17074
Para obter informações gerais do Windows sobre o Build 17074, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2018/01/11/announcing-windows-10-insider-preview-build-17074-pc/).

### <a name="wsl"></a>WSL
* Corrigido formato de armazenamento de metadados do DrvFs [GH 2777] </br>
**Importante:** Os metadados do DrvFs criados antes deste build serão exibidos incorretamente ou não serão exibidos em absoluto. Para corrigir os arquivos afetados, use chmod e chown para aplicar novamente os metadados.
* Corrigido o problema com vários sinais e syscalls reinicializáveis.

### <a name="console"></a>Console
* Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17063"></a>Build 17063
Para obter informações gerais do Windows sobre o Build 17063, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/12/19/announcing-windows-10-insider-preview-build-17063-pc/).

### <a name="wsl"></a>WSL
* O DrvFs dá suporte a metadados adicionais do Linux. Isso permite definir o proprietário e o modo de arquivos usando chmod/chown e também criar arquivos especiais, tais como FIFOs, soquetes Unix e arquivos de dispositivo. Por enquanto, isso é desabilitado por padrão, pois ainda é experimental.
**Observação**:  Corrigimos um bug no formato de metadados usado pelo DrvFs. Embora os metadados funcionem nesse Build para experimentação, os builds futuros não leem corretamente os metadados criados por esse build.  Talvez seja necessário atualizar manualmente o proprietário para arquivos modificados e os dispositivos com uma ID de dispositivo personalizada precisarão ser recriados.

  Para habilitar, monte o DrvFs com a opção de metadados (para habilitá-lo em uma montagem existente, você precisa primeiro desmontá-lo):

  ```bash
  mount -t drvfs C: /mnt/c -o metadata
  ```

  As permissões do Linux são adicionadas como metadados adicionais ao arquivo e não afetam as permissões do Windows.  Lembre-se de que a edição de um arquivo usando um editor do Windows pode remover os metadados. Nesse caso, o arquivo será revertido para as respectivas permissões padrão.

* Adicionadas opções de montagem ao DrvFs para controlar arquivos sem metadados.
  * uid: a ID de usuário usada para o proprietário de todos os arquivos.
  * gid: a ID de grupo usada para o proprietário de todos os arquivos.
  * umask: uma máscara octal de permissões a serem excluídas para todos os arquivos e diretórios.
  * fmask: uma máscara octal de permissões a serem excluídas para todos os arquivos regulares.
  * dmask: uma máscara octal de permissões a serem excluídas para todos os diretórios.

  Por exemplo:
  ```
  mount -t drvfs C: /mnt/c -o uid=1000,gid=1000,umask=22,fmask=111
  ```

  Combine com a opção de metadados para especificar permissões padrão para arquivos sem metadados.

* Introduziu uma nova variável de ambiente, `WSLENV`, para configurar o modo como as variáveis de ambiente fluem entre WSL e Win32.

  Por exemplo:

  ``` bash
  WSLENV=GOPATH/l:USERPROFILE/pu:DISPLAY
  ```

  `WSLENV` é uma lista delimitada por dois-pontos de variáveis de ambiente que pode ser incluída ao iniciar processos do WSL do Win32 ou vice-versa.  Cada variável pode ser sufixada com uma barra seguida por sinalizadores para especificar como ela é traduzida.
  * p: O valor é um caminho que deve ser traduzido entre caminhos WSL e Win32.
  * l: O valor é uma lista de caminhos. No WSL, é uma lista delimitada por dois-pontos. No Win32, é uma lista delimitada por ponto e vírgula.
  * u: O valor só deve ser incluído ao invocar o WSL do Win32
  * w: O valor só deve ser incluído ao invocar o Win32 do WSL

  Você pode definir `WSLENV` em. bashrc ou no ambiente personalizado do Windows para seu usuário.

* montagens do DrvFs preservam corretamente os carimbos de data/hora de tar, cp -p (GH 1939)
* symlinks do DrvFs relatam o tamanho correto (GH 2641)
* a leitura/gravação funciona para tamanhos de E/S muito grandes (GH 2653)
* waitpid trabalha com IDs de grupo de processos (GH 2534)
* desempenho de mmap significativamente melhorado para grandes regiões de reserva; melhora o desempenho do ghc (GH 1671)
* suporte a personalidades para READ_IMPLIES_EXEC; corrige maxima e clisp (GH 1185)
* mprotect dá suporte a PROT_GROWSDOWN; corrige o clisp (GH 1128)
* correções de falhas de página no modo de excesso de confirmação; corrige sbcl (GH 1128)
* o clone dá suporte a mais combinações de sinalizadores
* Dar suporte a select/epoll de arquivos epoll (anteriormente, algo não operacional).
* Notificar ptrace de syscalls não implementadas.
* Desconsideração de interfaces que não estão em funcionamento ao gerar nomes de servidor resolv.conf [GH 2694]
* Enumeração das interfaces de rede sem endereço físico. [GH 2685]
* Pequenas correções de bug e melhorias.

### <a name="linux-tools-available-to-developers-on-windows"></a>Ferramentas do Linux disponíveis para desenvolvedores no Windows

* A Cadeia de Ferramentas de Linha de Comando do Windows ferramentas inclui bsdtar (tar) e curl.
  Leia [este blog](https://aka.ms/tarcurlwindows) para saber mais sobre a adição dessas duas novas ferramentas e veja como elas estão moldando a experiência do desenvolvedor no Windows.

*   `AF_UNIX` está disponível no SDK do Participante do Programa Windows Insider (17061+).
  Leia [este blog](https://blogs.msdn.microsoft.com/commandline/2017/12/19/af_unix-comes-to-windows/) para saber mais sobre o `AF_UNIX` e como os desenvolvedores do Windows podem usá-lo.

### <a name="console"></a>Console
* Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.


## <a name="build-17046"></a>Build 17046

Para obter informações gerais do Windows sobre o Build 17046, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/11/22/announcing-windows-10-insider-preview-build-17046-pc).

### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Permissão para que processos sejam executados sem um terminal ativo. [GH 709, 1007, 1511, 2252, 2391 e outros]
- Melhor suporte a CLONE_VFORK e CLONE_VM. [GH 1878, 2615]
- Desconsideração de drivers de filtro de TDI para operações de rede WSL. [GH 1554]
- DrvFs cria NT symlinks quando determinadas condições são atendidas. [GH 353, 1475, 2602]
    - O destino do link precisa ser relativo, não pode cruzar nenhum ponto de montagem nem symlink e precisa existir.
    - O usuário deve ter SE_CREATE_SYMBOLIC_LINK_PRIVILEGE (isso normalmente requer que você inicie o wsl.exe com privilégios elevados), a menos que o modo de desenvolvedor esteja ativado.
    - Em todas as outras situações, o DrvFs ainda cria symlinks do WSL.
- Permissão para a execução de instâncias de WSL elevadas e não elevadas simultaneamente.
- Suporte a /proc/sys/kernel/yama/ptrace_scope
- Adição de wslpath para realizar conversões de caminho WSL<->Windows. [GH 522, 1243, 1834, 2327 e outros]
  ```
    wslpath usage:
      -a    force result to absolute path format
      -u    translate from a Windows path to a WSL path (default)
      -w    translate from a WSL path to a Windows path
      -m    translate from a WSL path to a Windows path, with '/' instead of '\\'

      EX: wslpath 'c:\users'
  ```
  #### <a name="console"></a>Console
- Sem correções.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.


## <a name="build-17040"></a>Build 17040

Para obter informações gerais do Windows sobre o Build 17040, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/11/16/announcing-windows-10-insider-preview-build-17040-pc).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Nenhuma correção desde o 17035.

#### <a name="console"></a>Console
- Nenhuma correção desde o 17035.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17035"></a>Build 17035

Para obter informações gerais do Windows sobre o Build 17035, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/11/08/announcing-windows-10-insider-preview-build-17035-pc).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- O acesso a arquivos no DrvFs pode ocasionalmente falhar com EINVAL. [GH 2448]

#### <a name="console"></a>Console
- Um pouco de perda de cor ao inserir/excluir linhas no modo VT.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17025"></a>Build 17025

Para obter informações gerais do Windows sobre o Build 17025, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/10/25/announcing-windows-10-insider-preview-build-17025-pc).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Inicialização dos processos iniciais em um novo grupo de processos de primeiro plano [GH 1653, 2510].
- Correções de entrega SIGHUP [GH 2496].
- Geração do nome de ponte virtual padrão se nenhum for fornecido [GH 2497].
- Implementação de /proc/sys/kernel/random/boot_id [GH 2518].
- Mais correções de pipe stdout/stderr de interop.
- Chamada do sistema syncfs de stub.

#### <a name="console"></a>Console
- Correção da conversão de VT de entrada para consoles de terceiros [GH 111]

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="build-17017"></a>Build 17017

Para obter informações gerais do Windows sobre o Build 17017, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/10/13/announcing-windows-10-insider-preview-build-17017-pc).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Desconsideração dos cabeçalhos de programa ELF vazios [GH 330].
- Permissão para que o LxssManager Crie instâncias do WSL para usuários não interativos (SSH e suporte a tarefas agendadas) [GH 777, 1602].
- Suporte a cenários de ("início") WSL-> Win32-> WSL [GH 1228].
- Suporte limitado para encerramento de aplicativos de console invocados via interop [GH 1614].
- Suporte a opções de montagem para devpts [GH 1948].
- Ptrace bloqueando a inicialização do filho [GH 2333].
- EPOLLET com alguns eventos ausentes [GH 2462].
- Retorno de mais dados para PTRACE_GETSIGINFO.
- Getdents com lseek fornece resultados incorretos.
- Correção de alguns travamentos do aplicativo de interop Win32, aguardando a entrada em um pipe que não tem mais dados.
- Suporte do O_ASYNC para arquivos tty/pty.
- Melhorias e correções de bugs adicionais

#### <a name="console"></a>Console
- Nenhuma alteração relacionada ao console nesta versão.

### <a name="ltp-results"></a>Resultados do LTP:
Testes em andamento.

## <a name="fall-creators-update"></a>Fall Creators Update

## <a name="build-16288"></a>Build 16288

Para obter informações gerais do Windows sobre o Build 16288, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/09/12/announcing-windows-10-insider-preview-build-16288-pc-build-15250-mobile/#7pLWQbj23JisfzV5.97/).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Inicialização e relatório corretos de UID, GID e modo para descritores de arquivo de soquete [GH 2490]
- Melhorias e correções de bugs adicionais

#### <a name="console"></a>Console
- Nenhuma alteração relacionada ao console nesta versão.

### <a name="ltp-results"></a>Resultados do LTP:
Nenhuma alteração desde o 16273

## <a name="build-16278"></a>Build 16278

Para obter informações gerais do Windows sobre o Build 162738, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/08/29/announcing-windows-10-insider-preview-build-16278-pc/#HMz6Xq7Su68WKi0t.97/).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Desmapeamento explícito de exibições mapeadas de seções com backup de arquivo ao dividir o estado LX MM [GH 2415]
- Melhorias e correções de bugs adicionais

#### <a name="console"></a>Console
- Nenhuma alteração relacionada ao console nesta versão.

### <a name="ltp-results"></a>Resultados do LTP:
Nenhuma alteração desde o 16273

## <a name="build-16275"></a>Build 16275

Para obter informações gerais do Windows sobre o Build 162735, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/08/25/announcing-windows-10-insider-preview-build-16275-pc-build-15245-mobile/#8QkxWqQbY37yZslV.97/).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Nenhuma alteração relacionada ao WSL nesta versão.

#### <a name="console"></a>Console
- Nenhuma alteração relacionada ao console nesta versão.

### <a name="ltp-results"></a>Resultados do LTP:
Nenhuma alteração desde o 16273

## <a name="build-16273"></a>Build 16273

Para obter informações gerais do Windows sobre o Build 16273, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/08/23/announcing-windows-10-insider-preview-build-16273-pc/).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Corrigido um problema em que o DrvFs às vezes relatava o tipo de arquivo errado para diretórios [GH 2392]
- Permissão para a criação de soquetes NETLINK_KOBJECT_UEVENT para desbloquear programas que usam uevent [GH 1121, 2293, 2242, 2295, 2235, 648, 637]
- Adição de suporte para conexão sem bloqueio [GH 903, 1391, 1584, 1585, 1829, 2290, 2314]
- Implementação do sinalizador de chamada do sistema de clone CLONE_FS [GH 2242]
- Correção de problemas relacionados à manipulação incorreta de guias ou aspas no interop NT [GH 1625, 2164]
- Resolução de erro de acesso negado ao tentar reinicializar instâncias de WSL [GH 651, 2095]
- Implementação das operações FUTEX_REQUEUE e FUTEX_CMP_REQUEUE do futex [GH 2242]
- Correção de permissões para vários arquivos SysFs [GH 2214]
- Correção do travamento da pilha do Haskell durante a instalação [GH 2290]
- Implementação dos sinalizadores 'C', 'O' e 'P' do binfmt_misc [GH 2103]
- Adição de /proc/sys/kernel/shmmax/shmmni e /threads-max [GH 1753]
- Adição de suporte parcial para chamada do sistema ioprio_set [GH 498]
- SO_REUSEPORT de stub e adicionar suporte para SO_PASSCRED para soquetes netlink [GH 69]
- Retorno de códigos de erro diferentes de RegisterDistribuiton se uma distribuição estiver sendo instalada ou desinstalada no momento.
- Permissão para o cancelamento de registro de distribuições de WSL parcialmente instaladas por meio de wslconfig.exe
- Correção do travamento do teste de soquete Python de udp::msg_peek
- Melhorias e correções de bugs adicionais

#### <a name="console"></a>Console
- Nenhuma alteração relacionada ao console nesta versão.

### <a name="ltp-results"></a>Resultados do LTP:
Total de testes: 1904<br/>
Total de testes ignorados: 209<br/>
Total de falhas: 229<br/>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/16273)<br/>

## <a name="build-16257"></a>Build 16257

Para obter informações gerais do Windows sobre o Build 16257, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/08/02/announcing-windows-10-insider-preview-build-16257-pc-build-15237-mobile/).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Implementação da chamada do sistema prlimit64
- Adição de suporte para ulimit -n (setrlimit RLIMIT_NOFILE) [GH 1688]
- MSG_MORE de stub para soquetes TCP [GH 2351]
- Correção do comportamento de vetor auxiliar AT_EXECFN inválido [GH 2133]
- Correção do comportamento de copiar/colar para console/TTY e adição de melhor manipulação de buffer completo [GH 2204, 2131]
- Definição de AT_SECURE em vetor auxiliar para os programas set-user-ID e set-group-ID [GH 2031]
- Ponto de extremidade mestre de pseudoterminal não manipulando TIOCPGRP [GH 1063]
- Correção do que o lseek faz para rebobinar diretórios no LxFs [GH 2310]
- /dev/ptmx trava após uso intenso [GH 1882]
- Melhorias e correções de bugs adicionais

#### <a name="console"></a>Console
- Correção para linhas horizontais/sublinhados em todos os lugares [GH 2168]
- Correção para a ordem de processo alterada, tornando o NPM mais difícil de fechar [GH 2170]
- Adicionado nosso novo esquema de cores: https://blogs.msdn.microsoft.com/commandline/2017/08/02/updating-the-windows-console-colors/

### <a name="ltp-results"></a>Resultados do LTP:
Nenhuma alteração desde o 16251

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`prlimit64`<br/>

### <a name="known-issues"></a>Problemas conhecidos
#### <a name="github-issue-2392-windows-folders-not-recognized-by-wsl-"></a>[Problema do GitHub n. 2392: Pastas do Windows não reconhecidas pelo WSL...](https://github.com/Microsoft/BashOnWindows/issues/2392)
No build 16257, o WSL tem problemas para enumerar arquivos/pastas do Windows via `/mnt/c/...`.
Esse problema foi corrigido e deve ser liberado no build do Insiders durante a semana que começa em 14/08/2017.

<br/>

## <a name="build-16251"></a>Build 16251

Para obter informações gerais do Windows sobre o Build 16251, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/07/26/announcing-windows-10-insider-preview-build-16251-pc-build-15235-mobile/).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Remova a tag beta do componente opcional do WSL, confira esta [postagem no blog](https://blogs.msdn.microsoft.com/commandline/2017/07/28/windows-subsystem-for-linux-out-of-beta/) para obter detalhes.
- Inicializar corretamente a UID e a GID salvas para os binários Set-User-ID e Set-Group-ID em exec [GH 962, 1415, 2072]
- Adicionado suporte para ptrace PTRACE_O_TRACEEXIT [GH 555]
- Adicionado suporte para ptrace PTRACE_GETFPREGS e PTRACE_GETREGSET com NT_FPREGSET [GH 555]
- Correção de ptrace para parar em sinais ignorados
- Melhorias e correções de bugs adicionais

#### <a name="console"></a>Console
- Nenhuma alteração relacionada ao console nesta versão.

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 768</br>
Número de testes reprovados: 244</br>
Número de testes ignorados: 96</br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/16251)<br/>

</br>

## <a name="build-16241"></a>Build 16241

Para obter informações gerais do Windows sobre o Build 16241, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/07/13/announcing-windows-10-insider-preview-build-16241-pc-build-15230-mobile/).<br/>


### <a name="fixed"></a>Fixo
#### <a name="wsl"></a>WSL
- Nenhuma alteração relacionada ao WSL nesta versão.

#### <a name="console"></a>Console
- Correção para a geração do caractere errado como saída para as linhas de cruzamento DEC, originalmente relatadas [aqui](https://www.reddit.com/r/Windows10/comments/6in82t/i_believe_ive_found_the_most_obscure_bug_ever/)
- Correção para nenhum texto de saída sendo exibido na página de código 65001 (utf8)
- Não transfira as alterações feitas aos valores RGB de uma cor para outras partes da paleta na alteração de seleção. Isso tornará a planilha de propriedades do console muito mais fácil de usar.
- Ctrl + S parece não funcionar corretamente
- Sem negrito/sem esmaecimento totalmente ausentes dos códigos de escape ANSI [GH 2174]
- O console não dá suporte corretamente a temas de cor Vim [GH 1706]
- Não é possível colar determinados caracteres [GH 2149]
- O redimensionamento de refluxo interage de acordo com o redimensionamento de uma janela do Bash quando as coisas estão na linha de comando/edição [GH ConEmu 1123]
- Ctrl + L deixa a tela suja [GH 1978]
- Bug de renderização do console ao exibir VT em HDPI [GH 1907]
- Caracteres japoneses parecem estranhos com o caractere Unicode U+30FB [GH 2146]
- Melhorias e correções de bugs adicionais

</br>

## <a name="build-16237"></a>Build 16237

Para obter informações gerais do Windows sobre o Build 16237, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/07/07/announcing-windows-10-insider-preview-build-16237-pc/).<br/>


### <a name="fixed"></a>Fixo
- Usar atributos padrão para arquivos sem EAs em lxfs (root, root, 0000)
- Adicionado suporte para distribuições que usam atributos estendidos
- Correção do preenchimento das entradas retornadas por getdents e getdents64
- Correção da verificação de permissões para a chamada do sistema shmctl SHM_STAT [GH 2068]
- Corrigido o estado de epoll inicial incorreto para ttys [GH 2231]
- Correção do DrvFs readdir não retornando todas as entradas [GH 2077]
- Correção do LxFs readdir quando os arquivos estão desvinculados [GH 2077]
- Permissão para que arquivos do DrvFs não vinculados sejam reabertos por meio do procfs
- Substituição da chave do Registro global adicionada para desabilitar os recursos do WSL (interop/montagem de unidade)
- Correção da contagem de blocos incorretos em "stat" para o DrvFs (e o LxFs) [GH 1894]
- Melhorias e correções de bugs adicionais

</br>

## <a name="build-16232"></a>Build 16232

Para obter informações gerais do Windows sobre o Build 16232, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/06/28/announcing-windows-10-insider-preview-build-16232-pc-build-15228-mobile/).<br/>


### <a name="fixed"></a>Fixo
- Nenhuma alteração relacionada ao WSL nesta versão.

</br>

## <a name="build-16226"></a>Build 16226

Para obter informações gerais do Windows sobre o Build 16226, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/06/21/announcing-windows-10-insider-preview-build-16226-pc/).<br/>


### <a name="fixed"></a>Fixo
- suporte a syscalls relacionadas a xattr (getxattr, setxattr, listxattr e removexattr).
- suporte a security.capablity xattr.
- Compatibilidade aprimorada com determinados sistemas de arquivos e filtros, incluindo servidores SMB não MS. [GH 1952]
- Suporte aprimorado para espaços reservados do OneDrive, espaços reservados do GVFS e arquivos compactados do SO Compacto.
- Melhorias e correções de bugs adicionais

</br>

## <a name="build-16215"></a>Build 16215

Para obter informações gerais do Windows sobre o Build 16215, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/06/08/announcing-windows-10-insider-preview-build-16215-pc-build-15222-mobile/).<br/>


### <a name="fixed"></a>Fixo
- O WSL não exige mais o modo de desenvolvedor.
- Suporte a junções de diretório no DrvFs.
- Manipulação da desinstalação de pacotes appx de distribuição do WSL.
- Atualização do procfs para mostrar mapeamentos privados e compartilhados.
- Adição de capacidade para o wslconfig.exe limpar as distribuições parcialmente instaladas ou desinstaladas.
- Adicionado suporte para IP_MTU_DISCOVER para soquetes TCP. [GH 1639, 2115, 2205]
- Inferência da família de protocolos para rotas para AF_INADDR.
- Aprimoramentos de dispositivo serial [GH 1929].

</br>

## <a name="build-16199"></a>Build 16199

Para obter informações gerais do Windows sobre o Build 16199, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/05/17/announcing-windows-10-insider-preview-build-16199-pc-build-15215-mobile/).<br/>


### <a name="fixed"></a>Fixo
- Nenhuma alteração relacionada ao WSL nestas versões.

</br>

## <a name="build-16193"></a>Build 16193

Para obter informações gerais do Windows sobre o Build 16193, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/05/11/announcing-windows-10-insider-preview-build-16193-pc-build-15213-mobile/).<br/>


### <a name="fixed"></a>Fixo
- Condição de corrida entre o envio de SIGCONT e um encerramento de um grupo de threads [GH 1973]
- alteração de dispositivos tty e pty para relatar FILE_DEVICE_NAMED_PIPE em vez de FILE_DEVICE_CONSOLE [GH 1840]
- Correção de SSH para IP_OPTIONS
- A montagem do DrvFs foi movida para o daemon init [GH 1862, 1968, 1767, 1933]
- Adicionado suporte no DrvFs para os symlinks NT a seguir.

</br>

## <a name="build-16184"></a>Build 16184

Para obter informações gerais do Windows sobre o Build 16184, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/04/28/announcing-windows-10-insider-preview-build-16184-pc-build-15208-mobile/).<br/>


### <a name="fixed"></a>Fixo
- Removida a tarefa de manutenção do pacote apt (lxrun.exe/update)
- Corrigido problema em que a saída não aparecia nos processos do Windows no Node.js [GH 1840]
- Flexibilização dos requisitos de alinhamento no lxcore [GH 1794]
- Corrigida a manipulação do sinalizador AT_EMPTY_PATH em um número de chamadas do sistema.
- Corrigido o problema em que a exclusão de arquivos do DrvFs com identificadores abertos fazia com que o arquivo apresentasse comportamento indefinido [GH 544, 966, 1357, 1535, 1615]
- O /etc/hosts agora herdará entradas do arquivo de hosts do Windows (%windir%\system32\drivers\etc\hosts) [GH 1495]

</br>

## <a name="build-16179"></a>Build 16179

Para obter informações gerais do Windows sobre o Build 16179, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/04/19/announcing-windows-10-insider-preview-build-16179-pc-build-15205-mobile/).<br/>


### <a name="fixed"></a>Fixo
- Nenhuma alteração de WSL nesta semana.

</br>

## <a name="build-16176"></a>Build 16176

Para obter informações gerais do Windows sobre o Build 16176, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/04/14/announcing-windows-10-insider-preview-build-16176-pc-build-15204-mobile/).<br/>


### <a name="fixed"></a>Fixo

- [Suporte serial habilitado](https://blogs.msdn.microsoft.com/wsl/2017/04/14/serial-support-on-the-windows-subsystem-for-linux/)
- Adicionada opção de soquete IP IP_OPTIONS [GH 1116]
- Função pwritev implementada (ao carregar o arquivo para nginx/PHP-FPM) [GH 1506]
- Adicionadas opções de soquete IP IP_MULTICAST_IF e IPV6_MULTICAST_IF [GH 990]
- Suporte para as opções de soquete IP_MULTICAST_LOOP e IPV6_MULTICAST_LOOP [GH 1678]
- Adicionada a opção de soquete IP(V6)_MTU para node, traceroute, dig, nslookup e host de aplicativos
- Adicionada a opção de soquete IP IPV6_UNICAST_HOPS
- [Aprimoramentos do sistema de arquivos](https://blogs.msdn.microsoft.com/wsl/2017/04/18/file-system-improvements-to-the-windows-subsystem-for-linux/)
    * Permitir a montagem de caminhos UNC
    * Habilitar o suporte a CDFS no DrvFs
    * Manipulação correta das permissões para sistemas de arquivos de rede no DrvFs
    * Adição de suporte para unidades remotas ao DrvFs
    * Habilitação do suporte a FAT no DrvFs
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP
Nenhuma alteração desde 15042

</br>

## <a name="build-16170"></a>Build 16170

Para obter informações gerais do Windows sobre o Build 16170, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/04/07/announcing-windows-10-insider-preview-build-16170-pc/).<br/>

Lançamos uma nova [postagem no blog](https://blogs.msdn.microsoft.com/wsl/2017/04/11/testing-the-windows-subsystem-for-linux/) discutindo nossos esforços para testar o WSL.

### <a name="fixed"></a>Fixo

- Suporte à opção de soquete IP_ADD_MEMBERSHIP e IPV6_ADD_MEMBERSHIP [GH 1678]
- Adição de suporte para PTRACE_OLDSETOPTIONS. [GH 1692]
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP
Nenhuma alteração desde 15042

</br>

## <a name="build-15046-to-windows-10-creators-update"></a>Build 15046 para a Atualização do Windows 10 para Criadores
Não há mais correções nem recursos do WSL planejados para inclusão na Atualização do Windows 10 para Criadores. As notas sobre a versão do WSL serão retomadas nas próximas semanas para as adições direcionadas à próxima atualização importante do Windows. Para obter informações gerais do Windows sobre o Build 15046 e futuras versões do Insider, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/02/28/announcing-windows-10-insider-preview-build-15046-pc/). <br/><br/>
 <br/>

## <a name="build-15042"></a>Build 15042

Para obter informações gerais do Windows sobre o Build 15042, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/02/24/announcing-windows-10-insider-preview-build-15042-pc-build-15043-mobile/).<br/>


### <a name="fixed"></a>Fixo

- Correção de um deadlock ao remover um caminho que termina em ".."
- Corrigido um problema em que FIONBIO não retornava 0 em caso de êxito [GH 1683]
- Corrigido um problema com leituras de comprimento zero de soquetes de datagrama inet
- Correção de um possível deadlock devido à condição de corrida na pesquisa de inode do DrvFs [GH 1675]
- Suporte estendido para dados complementares de soquete Unix; SCM_CREDENTIALS e SCM_RIGHTS [GH 514, 613, 1326]
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 737</br>
Número de não aprovados (com falha, ignorados, etc.): 255

</br>

## <a name="build-15031"></a>Build 15031

Para obter informações gerais do Windows sobre o Build 15031, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/02/08/announcing-windows-10-insider-preview-build-15031-pc/).<br/>


### <a name="fixed"></a>Fixo

- Corrigido um bug em que time(2) se comportava de maneira incorreta esporadicamente.
- Corrigido um problema em que syscalls *SIGPROCMASK poderiam corromper a máscara de sinal.
- Agora, retorne o comprimento de linha de comando completo na notificação de criação de processo do WSL. [GH 1632]
- O WSL agora relata a saída do thread por meio de ptrace para travamentos do GDB. [GH 1196]
- Corrigido o bug em que ptys travam após E/S intensa de tmux. [GH 1358]
- Correção da validação de tempo limite em muitas chamadas do sistema (futex, semtimedop, ppoll, sigtimedwait, itimer, timer_create)
- Adicionado suporte a eventfd EFD_SEMAPHORE [GH 452]
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 737</br>
Número de não aprovados (com falha, ignorados, etc.): 255 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15031)<br/>

<br/>

## <a name="build-15025"></a>Build 15025

Para obter informações gerais do Windows sobre o Build 15025, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/02/01/announcing-windows-10-insider-preview-build-15025-pc/).<br/>


### <a name="fixed"></a>Fixo

- Correção do bug que interrompeu o grep 2.27 [GH 1578]
- Implementado o sinalizador EFD_SEMAPHORE para a syscall eventfd2 [GH 452]
- Implementado /proc/[pid]/net/ipv6_route [GH 1608]
- Suporte de E/S controlada por sinal para soquetes de fluxo do Unix [GH 393, 68]
- Suporte a F_GETPIPE_SZ e F_SETPIPE_SZ [GH 1012]
- Implementação da syscall recvmmsg() [GH 1531]
- Corrigido o bug em que epoll_wait() não estava aguardando [GH 1609]
- Implementação de /proc/version_signature
- Tee syscall agora retornará uma falha se os dois descritores de arquivo se referirem ao mesmo pipe
- Implementação do comportamento correto para SO_PEERCRED para soquetes Unix
- Corrigido o tratamento de erro de parâmetro inválido da syscall tkill
- Alterações para aumentar o desempenho do DrvFs
- Correção secundária para bloqueio de E/S do Ruby
- Corrigido o erro em que recvmsg() retornava EINVAL para o sinalizador MSG_DONTWAIT para soquetes inet [GH 1296]
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 732</br>
Número de não aprovados (com falha, ignorados, etc.): 255 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15025)<br/>

<br/>

## <a name="build-15019"></a>Build 15019

Para obter informações gerais do Windows sobre o Build 15019, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/01/27/announcing-windows-10-insider-preview-build-15019-pc/).<br/>


### <a name="fixed"></a>Fixo

- Correção do bug que reportava incorretamente o uso da CPU em procfs para ferramentas como htop (GH 823, 945, 971)
- Ao chamar open() com O_TRUNC em um arquivo existente, INotifyPropertyChanged agora gera IN_MODIFY antes de IN_OPEN
- Correções para getsockopt SO_ERROR de soquetes Unix para habilitar postgress [GH 61, 1354]
- Implementação de /proc/sys/net/Core/SOMAXCONN para a linguagem GO
- A tarefa de atualização em segundo plano do pacote apt-get agora executa oculta
- Limpeza do escopo do localhost IPv6 (falha de Spring-Framework(Java)).
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 714 </br>
Número de não aprovados (com falha, ignorados, etc.): 249 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15019)<br/>

<br/>

## <a name="build-15014"></a>Build 15014

Para obter informações gerais do Windows sobre o Build 15014, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/01/19/announcing-windows-10-insider-preview-build-15014-for-pc-and-mobile-hello-windows-insiders-today-we-are-excited-to-be-releasing-windows-10-insider-preview-build-15014-for-pc-and-mobile).<br/>


### <a name="fixed"></a>Fixo

- Ctrl + C agora funciona conforme esperado
- htop e ps auxw agora mostram a utilização de recursos correta (GH 516)
- Conversão básica de exceções NT para sinais. (GH 513)
- agora, ao ficar sem espaço, fallocate falha com ENOSPC em vez de EINVAL (GH 1571)
- Adicionado /proc/sys/kernel/sem.
- Implementadas as chamadas de sistema semop e semtimedop
- Corrigidos os erros de nslookup com as opções de soquete IP_RECVTOS e IPV6_RECVTCLASS (GH 69)
- Suporte para as opções de soquete IP_RECVTTL e IPV6_RECVHOPLIMIT
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 709 </br>
Número de não aprovados (com falha, ignorados, etc.): 255 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15014)<br/>

### <a name="syscall-summary"></a>Resumo das syscalls
Total de syscalls: 384 </br>
Total de implementadas: 235 </br>
Total de fragmentadas: 22 </br>
Total de não implementadas: 127 </br>
[Detalhamento](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15014/Syscalls.txt)<br/>

<br/>

## <a name="build-15007"></a>Build 15007

Para obter informações gerais do Windows sobre o Build 15007, visite o [blog do Windows]( https://blogs.windows.com/windowsexperience/2017/01/12/announcing-windows-10-insider-preview-build-15007-pc-mobile).<br/>


### <a name="known-issue"></a>Problema conhecido

- Há um bug conhecido em que o console não reconhece alguma entrada Ctrl + <key>.  Isso inclui o comando Ctrl + C, que funcionará como um pressionamento comum da tecla 'C'.

  - Solução alternativa: Mapeamento de uma tecla alternativa para Ctrl + C. Por exemplo, para mapear Ctrl + K para Ctrl + C, faça isto: `stty intr \^k`.  Este mapeamento é por terminal e precisará ser realizado *toda* vez que o Bash for inicializado. Os usuários podem explorar a opção para incluir isto no `.bashrc` deles

### <a name="fixed"></a>Fixo

- Corrigido o problema em que executar o WSL consumiria 100% de um núcleo de CPU
- A opção de soquete IP_PKTINFO, IPV6_RECVPKTINFO agora é compatível. (GH 851, 987)
- Truncamento do endereço físico do adaptador de rede para 16 bytes em lxcore (GH 1452, 1414, 1343, 468, 308)
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 709 </br>
Número de não aprovados (com falha, ignorados, etc.): 255 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15007)<br/>

<br/>

## <a name="build-15002"></a>Build 15002

Para obter informações gerais do Windows sobre o Build 15002, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2017/01/09/announcing-windows-10-insider-preview-build-15002-pc/).<br/>


### <a name="known-issue"></a>Problema conhecido

Dois problemas conhecidos:
- Há um bug conhecido em que o console não reconhece alguma entrada Ctrl + <key>.  Isso inclui o comando Ctrl + C, que funcionará como um pressionamento comum da tecla 'C'.

  - Solução alternativa: Mapeamento de uma tecla alternativa para Ctrl + C. Por exemplo, para mapear Ctrl + K para Ctrl + C, faça isto: `stty intr \^k`.  Este mapeamento é por terminal e precisará ser realizado *toda* vez que o Bash for inicializado. Os usuários podem explorar a opção para incluir isto no `.bashrc` deles

- Enquanto o WSL estiver em execução, um thread do sistema consumirá 100% de um núcleo de CPU.  A causa raiz foi resolvida e corrigida internamente.

### <a name="fixed"></a>Fixo

- Todas as sessões do Bash agora devem ser criadas no mesmo nível de permissão.  Qualquer tentativa de iniciar uma sessão em um nível diferente será bloqueada.  Isso significa que consoles com e sem privilégios de administrador não podem executar simultaneamente. (GH 626)
<br/>
- Implementadas as mensagens NETLINK_ROUTE a seguir (requer administrador do Windows)
     - RTM_NEWADDR (dá suporte a `ip addr add`)
     - RTM_NEWROUTE (dá suporte a `ip route add`)
     - RTM_DELADDR (dá suporte a `ip addr del`)
     - RTM_DELROUTE (dá suporte a `ip route del`)
- A verificação de tarefa agendada para que os pacotes sejam atualizados não será mais executada em uma conexão limitada (GH #1371)
- Corrigido o erro em que o pipe fica preso, ou seja, bash -c "ls -alR /" | bash -c "cat" (GH 1214)
- Implementada a opção de soquete TCP_KEEPCNT (GH 843)
- Implementada a opção de soquete IP_MTU_DISCOVER INET (GH 720, 717, 170, 69)
- Funcionalidade herdada removida para executar binários NT por meio de init com a pesquisa de caminho de NT. (GH 1325)
- Correção do modo de /dev/kmsg para permitir o acesso de grupo/outro acesso de leitura (0644) (GH 1321)
- Implementado /proc/sys/kernel/random/uuid (GH 1092)
- Erro corrigido em que a hora de início do processo era mostrada como no ano 2432 (GH 974)
- Variável de ambiente TERM padrão alternada para xterm-256color (GH 1446)
- Modificado o modo como a confirmação do processo é calculada durante o fork do processo. (GH 1286)
- Implementado /proc/sys/vm/overcommit_memory. (GH 1286)
- Implementado /proc/net/route file (GH 69)
- Corrigido um erro em que o nome do atalho era localizado incorretamente (GH 696)
- Corrigida a lógica de análise de ELF que estava validando incorretamente os cabeçalhos de programa e precisava ser menor que (ou igual a) PATH_MAX. (GH 1048)
- Implementado retorno de chamada statfs para procfs, sysfs, cgroupfs e binfmtfs (GH 1378)
- Correção das janelas AptPackageIndexUpdate que não eram fechadas (GH 1184, também abordado em GH 1193)
- Adicionado suporte a ADDR_NO_RANDOMIZE de personalidade de ASLR. (GH 1148, 1128)
- Melhoria de PTRACE_GETSIGINFO e SIGSEGV para rastreamentos de pilha gdb apropriados durante o AV (GH #875)
- A análise de ELF não falha mais para binários patchelf. (GH 471)
- DNS de VPN propagado para /etc/resolv.conf (GH 416, 1350)
- Melhorias no fechamento de TCP para transferência de dados mais confiável. (GH 610, 616, 1025, 1335)
- Agora, o código de erro correto é retornado quando muitos arquivos estão abertos (EMFILE). (GH 1126, 2090)
- O log de auditoria do Windows agora relata o nome da imagem no processo create audit.
- Agora, falha normalmente ao iniciar bash.exe de dentro de uma janela do Bash
- Mensagem de erro adicionada quando a interop não consegue acessar um diretório de trabalho em LxFs (ou seja, notepad.exe. bashrc)
- Corrigido o problema em que o caminho do Windows era truncado no WSL
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 690 </br>
Número de não aprovados (com falha, ignorados, etc.): 274 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/15002)<br/>

<br/>

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`shmctl`<br/>
`shmget`<br/>
`shmdt`<br/>
`shmat`<br/>
<br/>

## <a name="build-14986"></a>Build 14986

Para obter informações gerais do Windows sobre o Build 14986, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/12/07/announcing-windows-10-insider-preview-build-14986-pc/).<br/>


### <a name="fixed"></a>Fixo

- Correção de verificações de bugs com NetLink e IOCTLs pty
- A versão do kernel agora relata 4.4.0-43 para consistência com o Xenial
- O bash.exe agora é iniciado quando a entrada é direcionada para 'nul:' (GH 1259)
- IDs de thread agora são relatadas corretamente em procfs (GH 967)
- Os sinalizadores IN_UNMOUNT | IN_Q_OVERFLOW | IN_IGNORED | IN_ISDIR agora são compatíveis com inotify_add_watch() (GH 1280)
- Implementado timer_create e chamadas de sistema relacionadas.  Isso habilita o suporte a GHC (GH 307)
- Corrigido o problema em que o ping retornava um tempo de 0,000 ms (GH 1296)
- O código de erro correto é retornado quando muitos arquivos estão abertos.
- Corrigido o problema no WSL em que a solicitação do NetLink para dados do adaptador de rede falharia com EINVAL se o endereço de hardware do adaptador fosse de 32 bytes (assim como na interface Teredo)
   - Observe que o utilitário "ip" do Linux contém um bug que faz com que ele falhe se o WSL relata um endereço de hardware de 32 bytes. Esse é um bug em "ip", não no WSL. O utilitário "ip" embute em código o tamanho do buffer de cadeia de caracteres usado para imprimir o endereço de hardware, e esse buffer é muito pequeno para imprimir um endereço de hardware de 32 bytes.
- Correções e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 669 </br>
Número de não aprovados (com falha, ignorados, etc.): 258 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14986)<br/>

<br/>

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`timer_create`<br/>
`timer_delete`<br/>
`timer_gettime`<br/>
`timer_settime`<br/>
<br/>

## <a name="build-14971"></a>Build 14971

Para obter informações gerais do Windows sobre o Build 14971, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/11/17/announcing-windows-10-insider-preview-build-14971-for-pc/).<br/>


### <a name="fixed"></a>Fixo

 - Devido a circunstâncias além do nosso controle, não há atualizações nesse build para o Subsistema do Windows para Linux.  As atualizações agendadas regularmente serão retomadas na próxima versão.

### <a name="ltp-results"></a>Resultados do LTP:
Inalterado desde o 14965 </br>
Número de testes aprovados: 664 </br>
Número de não aprovados (com falha, ignorados, etc.): 263 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14965)<br/>

<br/>

## <a name="build-14965"></a>Build 14965

Para obter informações gerais do Windows sobre o Build 14965, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/11/09/announcing-windows-10-insider-preview-build-14965-for-mobile-and-pc/).<br/>


### <a name="fixed"></a>Fixo

- Suporte para RTM_GETLINK e RTM_GETADDR do protocolo NETLINK_ROUTE de soquetes NetLink (GH 468)
  - Habilita os comandos ip e ifconfig para enumeração de rede
  - Mais informações podem ser encontradas em nossa [postagem no blog de rede WSL](https://blogs.msdn.microsoft.com/wsl/2016/11/08/225/).

- /sbin agora está no caminho do usuário por padrão
- O caminho de usuário do NT agora é acrescentado ao caminho do WSL por padrão (ou seja, agora você pode digitar notepad.exe sem adicionar System32 ao caminho do Linux)
- Adicionado suporte para /proc/sys/kernel/cap_last_cap
- Os binários do NT agora podem ser iniciados do WSL quando o diretório de trabalho atual contém caracteres não ANSI (GH 1254)
- Permissão para o desligamento no soquete de fluxo do Unix desconectado.
- Adicionado suporte para PR_GET_PDEATHSIG.
- Adicionado suporte para CLONE_PARENT
- Corrigido o erro em que o pipe fica preso, ou seja, bash -c "ls -alR /" | bash -c "cat" (GH 1214)
- Manipulação das solicitações para se conectar ao terminal atual.
- Marcação de /proc/<pid>/oom_score_adj como gravável.
- Adição da pasta/sys/fs/cgroup.
- sched_setaffinity deve retornar o número de máscara de bits de afinidade
- Correção da lógica de validação ELF que pressupõe incorretamente que os caminhos do interpretador devem ter menos de 64 caracteres. (GH 743)
- Descritores de arquivo abertos podem manter a janela do console aberta (GH 1187)
- Corrigido um erro em que rename() falhava com barra à direita no nome de destino (GH 1008)
- Implementação de /proc/net/dev file
- Corrigida a ocorrência de pings de 0,000 ms devido à resolução do timer.
- Implementado /proc/self/environ (GH 730)
- Correções de bug e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 664 </br>
Número de não aprovados (com falha, ignorados, etc.): 263 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14965)<br/>

<br/>

## <a name="build-14959"></a>Build 14959

Para obter informações gerais do Windows sobre o Build 14959, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/11/03/announcing-windows-10-insider-preview-build-14959-for-mobile-and-pc/#iI82GufJxMF3POU1.97).<br/>


### <a name="fixed"></a>Fixo

- Notificação de processo Pico aprimorada para Windows.  Informações adicionais encontradas no [blog do WSL](https://blogs.msdn.microsoft.com/wsl/2016/11/01/wsl-antivirus-and-firewall-compatibility/).
- Estabilidade aprimorada com a interop do Windows
- Corrigido o erro 0x80070057 ao iniciar o bash.exe quando a EDP (proteção de dados empresariais) está habilitada
- Correções de bug e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 665 </br>
Número de não aprovados (com falha, ignorados, etc.): 263 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14959)<br/>

<br/>

## <a name="build-14955"></a>Build 14955

Para obter informações gerais do Windows sobre o Build 14955, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/10/25/announcing-windows-10-insider-preview-build-14955-for-mobile-and-pc/#guGXQzKVFrZIDUYR.97).<br/>


### <a name="fixed"></a>Fixo

 - Devido a circunstâncias além do nosso controle, não há atualizações nesse build para o Subsistema do Windows para Linux.  As atualizações agendadas regularmente serão retomadas na próxima versão.

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 665 </br>
Número de não aprovados (com falha, ignorados, etc.): 263 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14955)<br/>

<br/>

## <a name="build-14951"></a>Build 14951

Para obter informações gerais do Windows sobre o Build 14951, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/10/19/announcing-windows-10-insider-preview-build-14951-for-mobile-and-pc/).<br/>


### <a name="new-feature-windows--ubuntu-interoperability"></a>Novo recurso: Interoperabilidade entre Windows/Ubuntu
Os binários do Windows agora podem ser chamados diretamente da linha de comando do WSL.  Isso dá aos usuários a capacidade de interagir com o ambiente e o sistema do Windows de uma maneira que não era possível.  Como um exemplo rápido, agora é possível que os usuários executem os seguintes comandos:

```bash
$ export PATH=$PATH:/mnt/c/Windows/System32
$ notepad.exe
$ ipconfig.exe | grep IPv4 | cut -d: -f2
$ ls -la | findstr.exe foo.txt
$ cmd.exe /c dir
```

Mais informações podem ser encontradas em:

- [Blog da equipe do WSL para interop](https://blogs.msdn.microsoft.com/wsl/2016/10/19/windows-and-ubuntu-interoperability/)<br/>
- [Documentação de interop do MSDN](https://msdn.microsoft.com/commandline/wsl/interop)<br/>

### <a name="fixed"></a>Fixo

- O Ubuntu 16.04 (Xenial) agora está instalado para todas as novas instâncias de WSL.  Os usuários com instâncias 14.04 (confiáveis) existentes não serão atualizados automaticamente.
- A localidade definida durante a instalação agora é exibida
- Melhorias de terminal, incluindo bugs em que o redirecionamento de um processo do WSL para um arquivo nem sempre funciona
- O tempo de vida do console deve estar vinculado ao tempo de vida do bash.exe
- O tamanho da janela do console deve usar um tamanho visível, não o tamanho do buffer
- Correções de bug e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 665 </br>
Número de não aprovados (com falha, ignorados, etc.): 263 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14951)<br/>

<br/>

## <a name="build-14946"></a>Build 14946

Para obter informações gerais do Windows sobre o Build 14946, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/10/13/announcing-windows-10-insider-preview-build-14946-for-pc-and-mobile/#xj8GdVooEqo4H7H7.97).<br/>


### <a name="fixed"></a>Fixo

- Corrigido um problema que impedia a criação de contas de usuário do WSL para usuários com nomes de usuário NT contendo espaços ou aspas. 
- Altere VolFs e DrvFs para retornar 0 para a contagem de links do diretório em stat
- Suporte à opção de soquete IPV6_MULTICAST_HOPS.
- Limite para um loop de E/S de console único por tty. Por exemplo, o comando a seguir é possível:
  - bash -c "echo data" | bash -c "ssh user@example.com 'cat > foo.txt'"

- substituição de espaços por tabulações em /proc/cpuinfo (GH 1115)
- O DrvFs agora aparece em mountinfo com um nome que corresponde ao volume do Windows montado
- /home e /root agora aparecem em mountinfo com os nomes corretos
- Correções de bug e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 665 </br>
Número de não aprovados (com falha, ignorados, etc.): 263 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14946)<br/>

<br/>

## <a name="build-14942"></a>Build 14942

Para obter informações gerais do Windows sobre o Build 14942, visite o [blog do Windows](https://aka.ms/onefourninefourtwoooooo).<br/>


### <a name="fixed"></a>Fixo

- Correção de várias verificações de bug, incluindo a falha de rede "TENTATIVA DE EXECUTAR A MEMÓRIA NOEXECUTE", que bloqueava o SSH
- o suporte do inotifiy para notificações geradas de aplicativos do Windows no DrvFs agora está em
- Implementação de TCP_KEEPIDLE e TCP_KEEPINTVL para mongod. (GH 695)
- Implementação da chamada do sistema pivot_root
- Implementar opção de soquete para SO_DONTROUTE
- Correções de bug e melhorias adicionais


### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 665 </br>
Número de não aprovados (com falha, ignorados, etc.): 263 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14942)<br/>

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`pivot_root`<br/>
<br/>

## <a name="build-14936"></a>Build 14936

Para obter informações gerais do Windows sobre o Build 14936, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/09/28/announcing-windows-10-insider-preview-build-14936-for-pc/).<br/>


Observação: O WSL instalará o Ubuntu versão 16.04 (Xenial) em vez do Ubuntu 14.04 (Trusty) em uma versão futura.  Essa alteração se aplicará a Participantes do Programa Windows Insider que estejam instalando novas instâncias (lxrun.exe /install ou primeira execução de bash.exe).  As instâncias existentes com Trusty não serão atualizadas automaticamente. Os usuários podem atualizar sua imagem do Trusty para Xenial usando o comando do-release-upgrade.

### <a name="known-issue"></a>Problema conhecido
O WSL está enfrentando um problema com algumas implementações de soquete.  A verificação de bug se manifesta como uma falha com o erro "TENTATIVA DE EXECUTAR A MEMÓRIA NOEXECUTE".  A manifestação mais comum desse problema é uma falha ao usar SSH.  A causa raiz é corrigida em builds internos e será enviada por push para pessoas na primeira oportunidade.

### <a name="fixed"></a>Fixo

- Implementada a chamada do sistema chroot
- Melhorias no inotifiy ~~incluindo suporte para notificações geradas de aplicativos do Windows no DrvFs~~
  - Correção: O suporte do INotifyPropertyChanged para alterações provenientes de aplicativos do Windows não estão disponíveis no momento.
- Associação de soquete a IPV6::<port n> agora dá suporte a IPV6_V6ONLY (GH 68, 157, 393, 460, 674, 740, 982, 996)
- Comportamento de WNOWAIT implementado para a chamada do sistema waitid (GH 638)
- Suporte para as opções de soquete de IP IP_HDRINCL e IP_TTL
- read() de tamanho zero deve retornar imediatamente (GH 975)
- Manipulação correta de nomes de arquivos e prefixos de nome de arquivo que não incluem um terminador nulo em um arquivo .tar.
- Suporte do epoll para/dev/null
- Correção da origem de tempo /dev/alarm
- Bash-c agora é capaz de redirecionar para um arquivo
- Correções de bug e melhorias adicionais

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 664 </br>
Número de não aprovados (com falha, ignorados, etc.): 264 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14936)<br/>

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`chroot`<br/>
<br/>

## <a name="build-14931"></a>Build 14931

Para obter informações gerais do Windows sobre o Build 14931, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/09/21/announcing-windows-10-insider-preview-build-14931-for-pc/).<br/>


### <a name="fixed"></a>Fixo

 - Devido a circunstâncias além do nosso controle, não há atualizações nesse build para o Subsistema do Windows para Linux.  As atualizações agendadas regularmente serão retomadas na próxima versão.

<br/>

## <a name="build-14926"></a>Build 14926

Para obter informações gerais do Windows sobre o Build 14926, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/09/14/announcing-windows-10-insider-preview-build-14926-for-pc-and-mobile/).<br/>


### <a name="fixed"></a>Fixo

- O ping agora funciona em consoles sem privilégios de administrador
- O Ping6 agora é compatível, inclusive quando sem privilégios de administrador
- Suporte a INotifyPropertyChanged para arquivos modificados por meio de WSL. (GH 216)
  - Sinalizadores compatíveis:
    - inotify_init1: LX_O_CLOEXEC, LX_O_NONBLOCK
    - Eventos de inotify_add_watch: LX_IN_ACCESS, LX_IN_MODIFY, LX_IN_ATTRIB, LX_IN_CLOSE_WRITE, LX_IN_CLOSE_NOWRITE, LX_IN_OPEN, LX_IN_MOVED_FROM, LX_IN_MOVED_TO, LX_IN_CREATE, LX_IN_DELETE, LX_IN_DELETE_SELF, LX_IN_MOVE_SELF
    - Atributos de inotify_add_watch: LX_IN_DONT_FOLLOW, LX_IN_EXCL_UNLINK, LX_IN_MASK_ADD, LX_IN_ONESHOT, LX_IN_ONLYDIR
    - saída de leitura: LX_IN_ISDIR, LX_IN_IGNORED
  - Problema conhecido: a modificação de arquivos de aplicativos do Windows não gera nenhum evento
- O soquete Unix agora dá suporte a SCM_CREDENTIALS

### <a name="ltp-results"></a>Resultados do LTP:
Número de testes aprovados: 651 </br>
Número de não aprovados (com falha, ignorados, etc.): 258 </br>
[Logs de execução de teste do LTP](https://github.com/Microsoft/CommandLine-Documentation/tree/live/LTP_Results/14926)<br/>

<br/>

## <a name="build-14915"></a>Build 14915

Para obter informações gerais do Windows sobre o Build 14915, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/08/31/announcing-windows-10-insider-preview-build-14915-for-pc-and-mobile).<br/>


### <a name="fixed"></a>Fixo
-  Par de soquetes para soquetes de datagramas Unix (GH 262)
- Suporte a soquetes Unix para SO_REUSEADDR
- Suporte a soquetes Unix para SO_BROADCAST (GH 568)
- Suporte a soquetes Unix para SOCK_SEQPACKET (GH 758, 546)
- Adição de suporte para envio, recebimento e desligamento de soquete de datagrama Unix
- Correção de verificação de bugs devido à validação de parâmetro mmap inválida para endereços não fixos. (GH 847)
- Suporte para suspensão/retomada de estados de terminal
- Suporte para ioctl TIOCPKT para desbloquear o utilitário de tela (GH 774)
    - Problema conhecido: Teclas de função não operacionais
- Correção de uma corrida em TimerFd que poderia fazer com que um membro 'ReaderReady' liberado fosse acessado pelo LxpTimerFdWorkerRoutine (GH 814)
- Habilitar suporte à chamada do sistema reiniciável para futex, poll e clock_nanosleep
- Adicionado suporte à montagem de associação
- suporte a descompartilhamento para namespace de montagem
    - Problema conhecido: Ao criar um novo namespace de montagem `unshare(CLONE_NEWNS)` com o diretório de trabalho atual, ele continuará a apontar para o namespace antigo
- Melhorias e correções de bugs adicionais

<br/>

## <a name="build-14905"></a>Build 14905

Para obter informações gerais do Windows sobre o Build 14905, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/08/17/announcing-windows-10-insider-preview-build-14905-for-pc-mobile/).<br/>


### <a name="fixed"></a>Fixo
- Agora, as chamadas reiniciáveis do sistema são compatíveis (GH 349, GH 520)
- Symlinks para diretórios que terminam em / agora estão operacionais (GH 650)
- Ioctl RNDGETENTCNT implementado para /dev/random
- Implementados os arquivos /proc/[pid]/mounts, /proc/[pid]/mountinfo e /proc/[pid]/mountstats
- Correções de bug e melhorias adicionais

</br>

## <a name="build-14901"></a>Build 14901
Primeiro build de Participante do Programa Windows Insider para a versão de Atualização de Aniversário do Windows 10.

Para obter informações gerais do Windows sobre o Build 14901, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/08/11/announcing-windows-10-insider-preview-build-14901-for-pc/).<br/>


### <a name="fixed"></a>Fixo
- Corrigido problema de barra à direita
    - Comandos como `$ mv a/c/ a/b/` agora funcionam
- A instalação agora avisa se a localidade do Ubuntu deve ser definida como a localidade do Windows
- Suporte do procfs para a pasta ns
- Adição de montagem e desmontagem para sistemas de arquivos tmpfs, procfs e sysfs
- Corrigir a assinatura da ABI de 32 bits mknod[at]
- Soquetes Unix movidos para o modelo de expedição
- O tamanho do buffer de recebimento do soquete INET definido usando o setsockopt deve ser respeitado
- Implementação do sinalizador de mensagem de recebimento do soquete do Unix MSG_CMSG_CLOEXEC
- Redirecionamento de pipe stdin/stdout de processo do Linux (GH 2)
    - Permite o pipe de comandos bash -c no cmd.  Exemplo: >dir | bash -c "grep foo"
- O Bash agora pode ser instalado em sistemas com diversos arquivos de paginação (GH 538, 358)
- O tamanho do buffer do soquete INET padrão deve corresponder ao da configuração padrão do Ubuntu
- Alinhamento de syscalls xattr a listxattr
- SIOCGIFCONF retorna apenas interfaces com um IPv4 válido
- Correção da ação padrão de sinal quando injetado por ptrace
- Implementação de /proc/sys/vm/min_free_kbytes
- Uso de valores de registro de contexto de computador ao restaurar o contexto em sigreturn
    - Isso resolve o problema em que java e javac estavam travando para alguns usuários
- Implementação de /proc/sys/kernel/hostname

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`waitid`<br/>
`epoll_pwait`<br/>

<br/>

## <a name="build-14388-to-windows-10-anniversary-update"></a>Build 14388 para Atualização de Aniversário do Windows 10
Para obter informações gerais do Windows sobre o Build 14388, visite o [blog do Windows](https://aka.ms/14388wip). <br/>

### <a name="fixed"></a>Fixo
- Correções para preparar para a Atualização de Aniversário do Windows 10 em 02/08
  - Mais informações sobre WSL na atualização de aniversário podem ser encontradas em nosso [blog](https://blogs.msdn.microsoft.com/wsl/)

<br/>

## <a name="build-14376"></a>Build 14376
Para obter informações gerais do Windows sobre o Build 14376, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/06/28/announcing-windows-10-insider-preview-build-14376-for-pc-and-mobile/). <br/>

### <a name="fixed"></a>Fixo
- Removidas algumas instâncias em que apt-get trava (GH 493)
- Corrigido um problema em que as montagens vazias não eram manipuladas corretamente
- Corrigido um problema em que ramdisks não eram montados corretamente
- Alteração da aceitação de soquete do Unix para dar suporte a sinalizadores (GH 451 parcial)
- Corrigida tela azul comum relacionada à rede
- Corrigida tela azul ao acessar /proc/[pid]/task (GH 523)
- Correção de alta utilização de CPU para alguns cenários de pty (GH 488, 504)
- Correções de bug e melhorias adicionais

<br/>

## <a name="build-14371"></a>Build 14371
Para obter informações gerais do Windows sobre o Build 14371, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/06/22/announcing-windows-10-insider-preview-build-14371-for-pc/). <br/>

### <a name="fixed"></a>Fixo
- Corrigida corrida de tempo com SIGCHLD e wait() ao usar ptrace
- Corrigido algum comportamento quando os caminhos têm uma / à direita (GH 432)
- Corrigido um problema de falha ao renomear/desvincular devido a identificadores abertos para filhos
- Correções de bug e melhorias adicionais

<br/>

## <a name="build-14366"></a>Build 14366
Para obter informações gerais do Windows sobre o Build 14366, visite o [blog do Windows](https://blogs.windows.com/windowsexperience/2016/06/14/announcing-windows-10-insider-preview-build-14366-mobile-build-14364/). <br/>

### <a name="fixed"></a>Fixo
- Correção na criação de arquivo por meio de symlinks
-   Adicionado listxattr para o Python (GH 385)
-   Correções de bug e melhorias adicionais

### <a name="syscall-support"></a>Suporte a syscall
-   Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`listxattr`<br/>
<br/>

## <a name="build-14361"></a>Build 14361
Para obter informações gerais do Windows sobre o Build 14361, visite o [blog do Windows](https://aka.ms/wip14361). <br/>

### <a name="fixed"></a>Fixo
- O DrvFs agora diferencia maiúsculas de minúsculas ao executar no Bash usando Ubuntu no Windows.
  - Os usuários podem usar case.txt e CASE.TXT nas respectivas unidades /mnt/c
  - A diferenciação de maiúsculas e minúsculas só é compatível no Bash usando Ubuntu no Windows. Quando fora do Bash, o NTFS relatará os arquivos corretamente, mas um comportamento inesperado poderá ocorrer ao interagir com os arquivos do Windows.
  - A raiz de cada volume (ou seja, /mnt/c) não diferencia maiúsculas e minúsculas
  - É possível encontrar mais informações sobre como manipular esses arquivos no Windows [aqui](https://support.microsoft.com/kb/100625).
- Suporte a pty/tty bastante aprimorado.  Aplicativos como TMUX agora são compatíveis (GH 40)
- Corrigido um problema de instalação em que as contas de usuário nem sempre eram criadas
- Estrutura de argumentos de linha de comando otimizada que permite uma lista de argumentos extremamente longa. (GH 153)
- Agora é possível excluir e usar chmod em arquivos read_only do DrvFs
- Corrigidas algumas instâncias em que o terminal travava ao desconectar (GH 43)
- chmod e chown agora funcionam em dispositivos tty
- Permissão para conexão a 0.0.0.0 e a :: como localhost (GH 388)
- Sendmsg/recvmsg agora aceitam um comprimento de vetor de E/S >1 (GH 376 parcial)
- Os usuários agora podem recusar o arquivo de hosts gerado automaticamente (GH #398)
- Correspondência automática da localidade do Linux à localidade do NT durante a instalação (GH 11)
- Adicionado o arquivo /proc/sys/VM/swappiness (GH 306)
- strace agora é encerrado corretamente
- Permissão para que os pipes sejam reabertos por meio de /proc/Self/FD (GH 222)
- Ocultação de diretórios em %LOCALAPPDATA%\lxss do DrvFs (GH 270)
- Melhor manipulação do bash.exe ~.  Agora, há suporte para comandos como "bash ~ -c ls" (GH 467)
- Os soquetes agora notificam que a leitura de epoll está disponível durante o desligamento (GH 271)
- lxrun /uninstall desempenha melhor a exclusão de arquivos e pastas
- ps-f corrigido (GH 246)
- Suporte aprimorado para aplicativos x11, tais como xEmacs (GH 481)
- Tamanho da pilha de thread inicial atualizado para corresponder à configuração padrão do Ubuntu e relatando o tamanho corretamente para a syscall get_rlimit (GH 172, 258)
- Relatório aprimorado de nomes de imagem de processo do pico (por exemplo, para auditoria)
- Implementado o /proc/mountinfo para o comando df
- Corrigido o código de erro de symlink para o nome do filho. e .
- Correções de bug e melhorias adicionais

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`GETTIMER`<br/>
`MKNODAT`<br/>
`RENAMEAT`<br/>
`SENDFILE`<br/>
`SENDFILE64`<br/>
`SYNC_FILE_RANGE`<br/>
<br/>

## <a name="build-14352"></a>Build 14352
Para obter informações gerais do Windows sobre o Build 14352, visite o [blog do Windows](https://aka.ms/wip14352).<br/>


### <a name="fixed"></a>Fixo
- Corrigido um problema em que arquivos grandes não eram baixados/criados corretamente.  Isso deve desbloquear o npm e outros cenários (GH 3, GH 313)
- Removidas algumas instâncias em que soquetes travavam
- Corrigidos alguns erros de ptrace
- Corrigido um problema com o WSL permitindo nomes de arquivo maiores do que 255 caracteres
- Suporte aprimorado para caracteres diferentes do inglês
- Adicionar os dados de fuso horário atual do Windows e definir como padrão
- Identificações de dispositivo exclusivas para cada ponto de montagem (correção do JRE – GH 49)
- Correção do problema com caminhos contendo "." e ".."
- Adicionado suporte a PEPS (GH 71)
- Atualizado formato de resolv.conf para corresponder ao formato nativo do Ubuntu
- Limpeza de alguns procfs
- Ping habilitado para consoles do administrador (GH 18)

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`FALLOCATE`<br/>
`EXECVE`<br/>
`LGETXATTR`<br/>
`FGETXATTR`<br/>
<br/>

## <a name="build-14342"></a>Build 14342
Para obter informações gerais do Windows sobre o Build 14342, visite o [blog do Windows](https://aka.ms/wip14342). <br/>

Informações sobre VolFs e DriveFs podem ser encontradas no [blog do WSL](https://blogs.msdn.microsoft.com/wsl). <br/>

### <a name="fixed"></a>Fixo
- Corrigido problema de instalação quando o usuário do Windows tinha caracteres Unicode no nome de usuário
- A solução alternativa apt-get update udev nas perguntas frequentes agora é fornecida por padrão na primeira execução
- Symlinks habilitados nos diretórios de DriveFs (/mnt/<drive>)
- Symlinks agora funcionam entre DriveFs e VolFs
- Problema de análise de caminho de nível superior resolvido: ls .// agora funcionará como esperado
- A instalação de npm no DriveFs e as opções -g agora estão funcionando
- Problema corrigido, impedindo a inicialização do servidor PHP
- Valores de ambiente padrão atualizados, tais como $PATH para corresponder melhor ao Ubuntu nativo
- Adicionada uma tarefa de manutenção semanal no Windows para atualizar o cache do pacote apt
- Corrigido um problema com a validação de cabeçalho ELF, o WSL agora dá suporte a todas as opções de Melkor
- O shell do zsh está funcional
- Binários do Go pré-compilados agora são compatíveis
- O aviso na primeira execução do bash.exe agora está localizado corretamente
- /proc/meminfo agora retorna informações corretas
- Os soquetes agora são compatíveis com o VFS
- /dev agora é montado como tempfs
- PEPS agora é compatível
- Sistemas de vários núcleos agora são mostrados corretamente em /proc/cpuinfo
- Aprimoramentos adicionais e mensagens de erro ao baixar durante a primeira execução
- Melhorias e correções de bug em syscall. Lista de syscalls compatíveis abaixo.
- Correções de bug e melhorias adicionais

### <a name="known-issues"></a>Problemas conhecidos
- Sem resolução para '..' corretamente no DriveFs em alguns casos

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls novas ou aprimoradas que têm alguma implementação no WSL. As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`FCHOWNAT`<br/>
`GETEUID`<br/>
`GETGID`<br/>
`GETRESUID`<br/>
`GETXATTR`<br/>
`PTRACE`<br/>
`SETGID`<br/>
`SETGROUPS`<br/>
`SETHOSTNAME`<br/>
`SETXATTR`<br/>
<br/>

## <a name="build-14332"></a>Build 14332

Para obter informações gerais do Windows sobre o Build 14332, visite o [blog do Windows](https://aka.ms/wip14332). <br/>


### <a name="fixed"></a>Fixo
- Melhor geração de resolv.conf, incluindo a priorização de entradas DNS
- Problema com a movimentação de arquivos e diretórios entre unidades/mnt e não /mnt
- Agora, os arquivos tar podem ser criados com symlinks
- Diretório /run/lock padrão adicionado na criação da instância
- Atualização de /dev/null para retornar informações de estado adequadas
- Erros adicionais ao baixar durante a primeira execução
- Melhorias e correções de bug em syscall. Lista de syscalls compatíveis abaixo.
- Correções de bug e melhorias adicionais

### <a name="syscall-support"></a>Suporte a syscall
Abaixo está a nova syscall que tem alguma implementação no WSL. A syscall nessa lista é compatível com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com ela no momento.

`READLINKAT`<br/>
<br/>

## <a name="build-14328"></a>Build 14328

Para obter informações gerais do Windows sobre o Build 14332, visite o [blog do Windows](https://aka.ms/wip14328). <br/>


### <a name="new-features"></a>Novos recursos
* Agora dão suporte a usuários do Linux.  A instalação do Bash usando o Ubuntu no Windows solicitará a criação de um usuário do Linux.  Para obter mais informações, visite https://aka.ms/wslusers
* O hostname agora está definido como o nome do computador Windows, não mais como @localhost
* Para obter mais informações sobre o build 14328, visite: https://aka.ms/wip14328

### <a name="fixed"></a>Fixo
* Aprimoramentos do symlink para arquivos não /mnt/<drive>
    * A instalação de npm agora funciona
    * Agora, o jdk/jre é instalável usando as instruções encontradas [aqui](https://xubuntugeek.blogspot.com/2012/09/how-to-install-oracle-jdk-7-manually-in.html).
    * problema conhecido: os symlinks não funcionam para montagens do Windows.  A funcionalidade estará disponível em um build posterior
* top e htop agora são exibidos
* Mensagens de erro adicionais para algumas falhas de instalação
* Melhorias e correções de bug em syscall.  Lista de syscalls compatíveis abaixo.
* Correções de bug e melhorias adicionais

### <a name="syscall-support"></a>Suporte a syscall
Veja abaixo uma lista de syscalls que têm alguma implementação no WSL.  As syscalls nessa lista são compatíveis com pelo menos um cenário, mas talvez nem todos os parâmetros sejam compatíveis com elas no momento.

`ACCEPT`<br/>
`ACCEPT4`<br/>
`ACCESS`<br/>
`ALARM`<br/>
`ARCH_PRCTL`<br/>
`BIND`<br/>
`BRK`<br/>
`CAPGET`<br/>
`CAPSET`<br/>
`CHDIR`<br/>
`CHMOD`<br/>
`CHOWN`<br/>
`CLOCK_GETRES`<br/>
`CLOCK_GETTIME`<br/>
`CLOCK_NANOSLEEP`<br/>
`CLONE`<br/>
`CLOSE`<br/>
`CONNECT`<br/>
`CREAT`<br/>
`DUP`<br/>
`DUP2`<br/>
`DUP3`<br/>
`EPOLL_CREATE`<br/>
`EPOLL_CREATE1`<br/>
`EPOLL_CTL`<br/>
`EPOLL_WAIT`<br/>
`EVENTFD`<br/>
`EVENTFD2`<br/>
`EXECVE`<br/>
`EXIT`<br/>
`EXIT_GROUP`<br/>
`FACCESSAT`<br/>
`FADVISE64`<br/>
`FCHDIR`<br/>
`FCHMOD`<br/>
`FCHMODAT`<br/>
`FCHOWN`<br/>
`FCHOWNAT`<br/>
`FCNTL64`<br/>
`FDATASYNC`<br/>
`FLOCK`<br/>
`FORK`<br/>
`FSETXATTR`<br/>
`FSTAT64`<br/>
`FSTATAT64`<br/>
`FSTATFS64`<br/>
`FSYNC`<br/>
`FTRUNCATE`<br/>
`FTRUNCATE64`<br/>
`FUTEX`<br/>
`GETCPU`<br/>
`GETCWD`<br/>
`GETDENTS`<br/>
`GETDENTS64`<br/>
`GETEGID`<br/>
`GETEGID16`<br/>
`GETEUID`<br/>
`GETEUID16`<br/>
`GETGID`<br/>
`GETGID16`<br/>
`GETGROUPS`<br/>
`GETPEERNAME`<br/>
`GETPGID`<br/>
`GETPGRP`<br/>
`GETPID`<br/>
`GETPPID`<br/>
`GETPRIORITY`<br/>
`GETRESGID`<br/>
`GETRESGID16`<br/>
`GETRESUID`<br/>
`GETRESUID16`<br/>
`GETRLIMIT`<br/>
`GETRUSAGE`<br/>
`GETSID`<br/>
`GETSOCKNAME`<br/>
`GETSOCKOPT`<br/>
`GETTID`<br/>
`GETTIMEOFDAY`<br/>
`GETUID`<br/>
`GETUID16`<br/>
`GETXATTR`<br/>
`GET_ROBUST_LIST`<br/>
`GET_THREAD_AREA`<br/>
`INOTIFY_ADD_WATCH`<br/>
`INOTIFY_INIT`<br/>
`INOTIFY_RM_WATCH`<br/>
`IOCTL`<br/>
`IOPRIO_GET`<br/>
`IOPRIO_SET`<br/>
`KEYCTL`<br/>
`KILL`<br/>
`LCHOWN`<br/>
`LINK`<br/>
`LINKAT`<br/>
`LISTEN`<br/>
`LLSEEK`<br/>
`LSEEK`<br/>
`LSTAT64`<br/>
`MADVISE`<br/>
`MKDIR`<br/>
`MKDIRAT`<br/>
`MKNOD`<br/>
`MLOCK`<br/>
`MMAP`<br/>
`MMAP2`<br/>
`MOUNT`<br/>
`MPROTECT`<br/>
`MREMAP`<br/>
`MSYNC`<br/>
`MUNLOCK`<br/>
`MUNMAP`<br/>
`NANOSLEEP`<br/>
`NEWUNAME`<br/>
`OPEN`<br/>
`OPENAT`<br/>
`PAUSE`<br/>
`PERF_EVENT_OPEN`<br/>
`PERSONALITY`<br/>
`PIPE`<br/>
`PIPE2`<br/>
`POLL`<br/>
`PPOLL`<br/>
`PRCTL`<br/>
`PREAD64`<br/>
`PROCESS_VM_READV`<br/>
`PROCESS_VM_WRITEV`<br/>
`PSELECT6`<br/>
`PTRACE`<br/>
`PWRITE64`<br/>
`READ`<br/>
`READLINK`<br/>
`READV`<br/>
`REBOOT`<br/>
`RECV`<br/>
`RECVFROM`<br/>
`RECVMSG`<br/>
`RENAME`<br/>
`RMDIR`<br/>
`RT_SIGACTION`<br/>
`RT_SIGPENDING`<br/>
`RT_SIGPROCMASK`<br/>
`RT_SIGRETURN`<br/>
`RT_SIGSUSPEND`<br/>
`RT_SIGTIMEDWAIT`<br/>
`SCHED_GETAFFINITY`<br/>
`SCHED_GETPARAM`<br/>
`SCHED_GETSCHEDULER`<br/>
`SCHED_GET_PRIORITY_MAX`<br/>
`SCHED_GET_PRIORITY_MIN`<br/>
`SCHED_SETAFFINITY`<br/>
`SCHED_SETPARAM`<br/>
`SCHED_SETSCHEDULER`<br/>
`SCHED_YIELD`<br/>
`SELECT`<br/>
`SEND`<br/>
`SENDMMSG`<br/>
`SENDMSG`<br/>
`SENDTO`<br/>
`SETDOMAINNAME`<br/>
`SETGID`<br/>
`SETGROUPS`<br/>
`SETHOSTNAME`<br/>
`SETITIMER`<br/>
`SETPGID`<br/>
`SETPRIORITY`<br/>
`SETREGID`<br/>
`SETRESGID`<br/>
`SETRESUID`<br/>
`SETREUID`<br/>
`SETRLIMIT`<br/>
`SETSID`<br/>
`SETSOCKOPT`<br/>
`SETTIMEOFDAY`<br/>
`SETUID`<br/>
`SETXATTR`<br/>
`SET_ROBUST_LIST`<br/>
`SET_THREAD_AREA`<br/>
`SET_TID_ADDRESS`<br/>
`SHUTDOWN`<br/>
`SIGACTION`<br/>
`SIGALTSTACK`<br/>
`SIGPENDING`<br/>
`SIGPROCMASK`<br/>
`SIGRETURN`<br/>
`SIGSUSPEND`<br/>
`SOCKET`<br/>
`SOCKETCALL`<br/>
`SOCKETPAIR`<br/>
`SPLICE`<br/>
`STAT64`<br/>
`STATFS64`<br/>
`SYMLINK`<br/>
`SYMLINKAT`<br/>
`SYNC`<br/>
`SYSINFO`<br/>
`TEE`<br/>
`TGKILL`<br/>
`TIME`<br/>
`TIMERFD_CREATE`<br/>
`TIMERFD_GETTIME`<br/>
`TIMERFD_SETTIME`<br/>
`TIMES`<br/>
`TKILL`<br/>
`TRUNCATE`<br/>
`TRUNCATE64`<br/>
`UMASK`<br/>
`UMOUNT`<br/>
`UMOUNT2`<br/>
`UNLINK`<br/>
`UNLINKAT`<br/>
`UNSHARE`<br/>
`UTIME`<br/>
`UTIMENSAT`<br/>
`UTIMES`<br/>
`VFORK`<br/>
`WAIT4`<br/>
`WAITPID`<br/>
`WRITE`<br/>
`WRITEV`<br/>
