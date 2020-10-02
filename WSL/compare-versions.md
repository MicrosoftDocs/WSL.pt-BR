---
title: Comparação entre o WSL 2 e o WSL 1
description: 'Compare as versões 1 e 2 do Subsistema do Windows para Linux. Saiba o que há de novo no WSL 2: kernel real do Linux, velocidade mais rápida, compatibilidade total com chamadas do sistema. O WSL 1 funcionará melhor se você estiver armazenando arquivos em sistemas de arquivos operacionais. Você pode expandir o tamanho do seu VHD (Disco de Hardware Virtual) do WSL 2.'
keywords: BashOnWindows, bash, wsl, windows, windowssubsystem, gnu, linux, ubuntu, debian, suse, windows 10, UX changes, WSL 2, linux kernel, network applications, localhost, IPv6, Virtual Hardware Disk, VHD, VHD limitations, VHD error
ms.date: 09/15/2020
ms.topic: conceptual
ms.localizationpriority: high
ms.custom: contperfq1
ms.openlocfilehash: 5aa37c632fe1e02680bdef307a5923d05dfb3f60
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413111"
---
# <a name="comparing-wsl-1-and-wsl-2"></a>Comparação entre o WSL 1 e o WSL 2

A principal diferença e os motivos para atualizar o Subsistema do Windows para Linux do WSL 1 para o WSL 2 são:

- **aumentar o desempenho do sistema de arquivos**,
- **dar suporte à compatibilidade total com chamadas do sistema**.

O WSL 2 usa a mais recente e melhor tecnologia de virtualização para executar um kernel do Linux dentro de uma VM (máquina virtual) do utilitário leve. No entanto, o WSL 2 não é uma experiência de VM tradicional.

> [!div class="nextstepaction"]
> [Instalar o WSL 1 e atualizar para o WSL 2](install-win10.md)

## <a name="comparing-features"></a>Comparação de recursos

Recurso | WSL 1 | WSL 2
--- | --- | ---
 Integração entre o Windows e o Linux| ✅|✅
 Tempos de inicialização rápidos| ✅ | ✅
 Volume de recursos pequeno| ✅ |✅
 É executado com as versões atuais do VMware e do VirtualBox| ✅ | ✅
 VM gerenciada| ❌ | ✅
 Kernel do Linux completo| ❌ |✅
 Compatibilidade total com a chamada do sistema| ❌ | ✅
 Desempenho entre sistemas de arquivos do sistema operacional| ✅ | ❌

Como você pode ver na tabela de comparação acima, a arquitetura WSL 2 tem um desempenho melhor que o WSL 1 de várias maneiras, com exceção do desempenho entre sistemas de arquivos do sistema operacional.

## <a name="performance-across-os-file-systems"></a>Desempenho entre sistemas de arquivos do sistema operacional

Não recomendamos trabalhar em sistemas operacionais com os seus arquivos, a menos que você tenha um motivo específico para fazer isso. Para a velocidade de desempenho mais rápida, armazene os seus arquivos no sistema de arquivos WSL se você estiver trabalhando em uma linha de comando do Linux (Ubuntu, OpenSUSE etc.). Se estiver trabalhando em uma linha de comando do Windows (PowerShell, Prompt de Comando), armazene os arquivos no sistema de arquivos do Windows.

Por exemplo, ao armazenar seus arquivos de projeto do WSL:

- Use o diretório raiz do sistema de arquivos do Linux: `\\wsl$\Ubuntu-18.04\home\<user name>\Project`
- Não o diretório raiz do sistema de arquivos do Windows: `C:\Users\<user name>\Project`

Você pode acessar o sistema de arquivos raiz do Linux com aplicativos e ferramentas do Windows, como o Explorador de Arquivos. Tente abrir uma distribuição do Linux (como o Ubuntu), verifique se você está no diretório base do Linux digitando este comando: `cd ~`. Em seguida, abra o sistema de arquivos do Linux no Explorador de Arquivos digitando *(não se esqueça do ponto no final)* : `explorer.exe .`

O WSL 2 só está disponível no Windows 10, versão 1903, Build 18362 ou superior. Verifique sua versão do Windows selecionando a **tecla do logotipo do Windows + R**, digite **winver**, selecione **OK**. (Ou digite o comando `ver` no prompt de comando do Windows). Você pode precisar [atualizar para a última versão do Windows](ms-settings:windowsupdate). Para builds inferiores ao 18362, não há nenhum suporte para o WSL.

> [!NOTE]
> O WSL 2 funcionará com o [VMware 15.5.5+](https://blogs.vmware.com/workstation/2020/05/vmware-workstation-now-supports-hyper-v-mode.html) e o [VirtualBox 6+](https://www.virtualbox.org/wiki/Changelog-6.0). Saiba mais nas [Perguntas frequentes do WSL 2.](./wsl2-faq.md#will-i-be-able-to-run-wsl-2-and-other-3rd-party-virtualization-tools-such-as-vmware-or-virtualbox)

## <a name="whats-new-in-wsl-2"></a>Novidades no WSL 2

O WSL 2 é uma importante revisão da arquitetura subjacente e usa a tecnologia de virtualização e um kernel do Linux para habilitar os novos recursos. As metas principais dessa atualização são aumentar o desempenho do sistema de arquivos e adicionar compatibilidade total com chamadas do sistema.

- [Requisitos de sistema do WSL 2](./install-win10.md#step-2---update-to-wsl-2)
- [Atualizar do WSL 1 para o WSL 2](./install-win10.md#step-2---update-to-wsl-2)
- [Perguntas frequentes sobre o WSL 2](./wsl2-faq.md)

### <a name="wsl-2-architecture"></a>Arquitetura do WSL 2

Uma experiência de VM tradicional poderá ter inicialização lenta, ser isolada, consumir muitos recursos e exigir o seu tempo para gerenciá-la. O WSL 2 não tem esses atributos.

O WSL 2 fornece os benefícios do WSL 1, incluindo integração direta entre o Windows e o Linux, tempos de inicialização rápidos, um pequeno volume de recursos e não requer nenhuma configuração ou gerenciamento de VM. Embora o WSL 2 use uma VM, ele é gerenciado e executado nos bastidores, deixando você com a mesma experiência do usuário que o WSL 1.

### <a name="full-linux-kernel"></a>Kernel do Linux completo

O kernel do Linux no WSL 2 é criado pela Microsoft usando a ramificação estável mais recente, com base na origem disponível em kernel.org. Esse kernel foi especialmente ajustado para o WSL 2, otimizando o tamanho e o desempenho para fornecer uma experiência incrível do Linux no Windows. O kernel será atendido pelas atualizações do Windows, o que significa que você obterá as correções de segurança e aprimoramentos de kernel mais recentes sem precisar gerenciá-las por conta própria.

O [kernel do Linux do WSL 2 é de software livre](https://github.com/microsoft/WSL2-Linux-Kernel). Se você quiser saber mais, confira a postagem no blog [Como enviar um kernel do Linux com o Windows](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/) escrito pela equipe que o criou.

### <a name="increased-file-io-performance"></a>Maior desempenho de E/S de arquivo

Operações com uso intensivo de arquivo, como comandos git clone, npm install, apt update, apt upgrade e muito mais, são visivelmente mais rápidas com o WSL 2.

O aumento da velocidade real dependerá de qual aplicativo você está executando e de como ele está interagindo com o sistema de arquivos. As versões iniciais do WSL 2 são executadas até 20 vezes mais rapidamente em comparação com o WSL 1 ao desempacotar um tarball compactado e de duas a cinco vezes mais rapidamente ao usar os comandos git clone, npm install e cmake em vários projetos.

### <a name="full-system-call-compatibility"></a>Compatibilidade total com a chamada do sistema

Os binários do Linux usam chamadas do sistema para executar funções, como acessar arquivos, solicitar memória, criar processos e muito mais. Enquanto o WSL 1 usava uma camada de conversão criada pela equipe do WSL, o WSL 2 inclui o próprio kernel Linux com compatibilidade total com a chamada do sistema. Os benefícios incluem:

- Um conjunto totalmente novo de aplicativos que você pode executar dentro do WSL, como o **[Docker](tutorials/wsl-containers.md)** e muito mais.

- Todas as atualizações para o kernel do Linux estão imediatamente prontas para uso. (Você não precisa esperar que a equipe do WSL implemente atualizações e adicione as alterações).

### <a name="wsl-2-uses-a-smaller-amount-of-memory-on-startup"></a>O WSL 2 usa uma quantidade menor de memória na inicialização

O WSL 2 usa uma VM de utilitário leve em um kernel real do Linux com um pequeno volume de memória. O utilitário alocará a memória com suporte de endereço virtual na inicialização. Ela é configurada para começar com uma pequena proporção da memória total em comparação com a necessária para o WSL 1.

## <a name="exceptions-for-using-wsl-1-rather-than-wsl-2"></a>Exceções para uso do WSL 1 em vez do WSL 2

Recomendamos que você use o WSL 2, pois ele oferece desempenho mais rápido e 100% de compatibilidade com a chamada do sistema. No entanto, há alguns cenários específicos em que você pode preferir usar o WSL 1. Considere usar o WSL 1 se:

- Seus arquivos de projeto devem ser armazenados no sistema de arquivos do Windows. O WSL 1 oferece acesso mais rápido aos arquivos montados no Windows.
  - Se estiver usando sua distribuição do WSL no Linux para acessar arquivos de projeto no sistema de arquivos do Windows e esses arquivos não puderem ser armazenados no sistema de arquivos do Linux, você obterá um desempenho melhor nos sistemas de arquivos do sistema operacional usando o WSL 1.
- Um projeto que requer compilação cruzada usando as ferramentas do Windows e do Linux nos mesmos arquivos.
  - O desempenho de arquivos entre os sistemas operacionais do Windows e do Linux é mais rápido no WSL 1 do que no WSL 2, portanto, se estiver usando aplicativos do Windows para acessar arquivos do Linux, você obterá um desempenho melhor com o WSL 1.

> [!NOTE]
> Considere usar a [Extensão Remota do WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) do VS Code para permitir que você armazene seus arquivos de projeto no sistema de arquivos do Linux, usando as ferramentas de linha de comando do Linux, mas também usando o VS Code no Windows para criar, editar, depurar ou executar seu projeto em um navegador da Internet sem a lentidão de desempenho associada ao trabalho nos sistemas de arquivos Linux e Windows. [Saiba mais](tutorials/wsl-vscode.md).

## <a name="accessing-network-applications"></a>Acessar aplicativos de rede

### <a name="accessing-linux-networking-apps-from-windows-localhost"></a>Como acessar aplicativos de rede do Linux no Windows (localhost)

Se você estiver criando um aplicativo de rede (por exemplo, um aplicativo em execução em um NodeJS ou SQL Server) em sua distribuição do Linux, poderá acessá-lo de um aplicativo do Windows (como seu navegador de Internet Microsoft Edge ou Chrome) usando `localhost` (assim como faria normalmente).

No entanto, se você estiver executando uma versão mais antiga do Windows (Build 18945 ou anterior), será necessário obter o endereço IP da VM host do Linux (ou [atualizar para a versão mais recente do Windows](ms-settings:windowsupdate)).

Para localizar o endereço IP da máquina virtual que está capacitando sua distribuição do Linux:

- Em sua distribuição do WSL (por exemplo, Ubuntu), execute o comando: `ip addr`
- Localize e copie o endereço no valor `inet` da interface `eth0`.
- Se você tiver a ferramenta grep instalada, encontre-a mais facilmente filtrando a saída com o comando: `ip addr | grep eth0`
- Conecte-se ao seu servidor Linux usando esse endereço IP.

A imagem abaixo mostra um exemplo disso por meio da conexão com um servidor Node.js usando o navegador Edge.

![Conectar-se ao servidor NodeJS com o Edge](media/wsl2-network-w2l.jpg)

### <a name="accessing-windows-networking-apps-from-linux-host-ip"></a>Como acessar aplicativos de rede do Windows no Linux (IP do host)

Se quiser acessar um aplicativo de rede em execução no Windows (por exemplo, um aplicativo em execução em um NodeJS ou SQL Server) de sua distribuição do Linux (por exemplo, Ubuntu), você precisará usar o endereço IP do seu computador host. Embora esse não seja um cenário comum, você pode seguir estas etapas para fazê-lo funcionar.
    - Obtenha o endereço IP do seu computador host executando este comando da sua distribuição do Linux: `cat /etc/resolv.conf`
    - Copie o endereço IP após o termo: `nameserver`.
    - Conecte-se a qualquer servidor Windows usando o endereço IP copiado.

A imagem abaixo mostra um exemplo disso por meio da conexão com um servidor Node.js em execução no Windows via curl.

![Conectar-se ao servidor NodeJS no Windows via Curl](media/wsl2-network-l2w.png)

### <a name="additional-networking-considerations"></a>Considerações adicionais de rede

#### <a name="connecting-via-remote-ip-addresses"></a>Conectar-se via endereços IP remotos

Ao usar endereços IP remotos para se conectar aos seus aplicativos, eles serão tratados como conexões de LAN (rede local). Isso significa que você precisará verificar se seu aplicativo pode aceitar conexões de LAN.

Por exemplo, talvez seja necessário associar seu aplicativo a `0.0.0.0` em vez de `127.0.0.1`. No exemplo de um aplicativo Python usando Flask, isso pode ser feito com o comando: `app.run(host='0.0.0.0')`. Tenha em mente a segurança ao fazer essas alterações, pois isso permitirá conexões de sua LAN.

#### <a name="accessing-a-wsl-2-distribution-from-your-local-area-network-lan"></a>Como acessar uma distribuição do WSL 2 usando a LAN (rede local)

Ao usar uma distribuição do WSL 1, se o computador tiver sido configurado para ser acessado pela sua LAN, os aplicativos executados no WSL também poderão ser acessados em sua LAN.

Esse não é o caso padrão no WSL 2. O WSL 2 tem um adaptador Ethernet virtualizado com um endereço IP exclusivo. No momento, para habilitar esse fluxo de trabalho, será necessário percorrer as mesmas etapas que você faria para uma máquina virtual normal. (Estamos analisando maneiras de aprimorar essa experiência.)

Veja um comando do PowerShell de exemplo para adicionar um proxy de porta que escuta na porta 4000 no host e o conecta à porta 4000 para a VM do WSL 2 com o endereço IP 192.168.101.100.

```powershell
netsh interface portproxy add v4tov4 listenport=4000 listenaddress=0.0.0.0 connectport=4000 connectaddress=192.168.101.100
```

#### <a name="ipv6-access"></a>Acesso IPv6

Atualmente, as distribuições do WSL 2 não conseguem acessar endereços IPv6. Estamos trabalhando para adicionar esse recurso.

## <a name="expanding-the-size-of-your-wsl-2-virtual-hardware-disk"></a>Como expandir o tamanho do seu Disco de Hardware Virtual do WSL 2

O WSL 2 usa um VHD (Disco de Hardware Virtual) para armazenar seus arquivos do Linux. Se o tamanho máximo for atingido, talvez seja necessário expandi-lo.

O VHD do WSL 2 usa o sistema de arquivos ext4. Esse VHD é redimensionado automaticamente para atender às suas necessidades de armazenamento e tem um tamanho máximo inicial de 256 GB. Se a sua distribuição aumentar de tamanho para exceder 256 GB, você verá erros informando que você ficou sem espaço em disco. Para corrigir esse erro, expanda o tamanho do VHD.

Para expandir o tamanho máximo do VHD para mais de 256 GB:

1. Termine todas as instâncias do WSL usando o comando: `wsl --shutdown`

2. Localize o nome do pacote de instalação da distribuição ('PackageFamilyName')
    - Usando o PowerShell (em que 'distro' é o nome da distribuição), insira o comando:
    - `Get-AppxPackage -Name "*<distro>*" | Select PackageFamilyName`

3. Localize arquivo VHD `fullpath` usado pela sua instalação do WSL 2, que será o seu `pathToVHD`:
     - `%LOCALAPPDATA%\Packages\<PackageFamilyName>\LocalState\<disk>.vhdx`

4. Redimensione o VHD do WSL 2 concluindo os seguintes comandos:
   - Abra o prompt de comando do Windows com privilégios de administrador e digite:
      - `diskpart`
      - `Select vdisk file="<pathToVHD>"`
      - `expand vdisk maximum="<sizeInMegaBytes>"`

5. Inicie sua distribuição do WSL (Ubuntu, por exemplo).

6. Informe ao WSL que ele pode expandir o tamanho do sistema de arquivos executando esses comandos na linha de comando de distribuição do Linux:
    - `sudo mount -t devtmpfs none /dev`
    - `mount | grep ext4`
    - Copie o nome dessa entrada, que terá a seguinte aparência: `/dev/sdXX` (com o X representando qualquer outro caractere)
    - `sudo resize2fs /dev/sdXX`
    - Use o valor que você copiou anteriormente. Talvez você também precise instalar o resize2fs: `apt install resize2fs`

> [!NOTE]
> em geral, não modifique, mova ou acesse os arquivos relacionados ao WSL localizados dentro da sua pasta AppData usando as ferramentas ou os editores do Windows. Isso pode fazer com que a distribuição do Linux fique corrompida.
