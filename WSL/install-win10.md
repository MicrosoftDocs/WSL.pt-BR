---
title: Instalar o WSL (Subsistema Windows para Linux) no Windows 10
description: Guia de instalação do WSL no Windows 10 com um terminal Bash, incluindo Ubuntu, Debian, SUSE, Kali, Fedora, Pengwin e Alpine.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, debian, suse, windows 10, install, enable, WSL2, version 2
ms.date: 09/15/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 58375484d57e7cb65a807e7156a5dcdf166dac2e
ms.sourcegitcommit: 17d5ea1fe571274c224202544f61035971d6e0e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2021
ms.locfileid: "100551032"
---
# <a name="windows-subsystem-for-linux-installation-guide-for-windows-10"></a>Guia de instalação do Subsistema Windows para Linux para Windows 10

Há duas opções disponíveis para instalar o WSL (Subsistema do Windows para Linux):

- **[Instalação simplificada](#simplified-installation-for-windows-insiders)** *(versão prévia)* : `wsl --install`

    O comando de instalação simplificada de `wsl --install` requer que você entre no [Programa Windows Insiders](https://insider.windows.com/getting-started) e instale uma versão prévia do Windows 10 (build do sistema operacional 20262 ou superior), mas elimina a necessidade de seguir as etapas de instalação manual. Tudo o que você precisa fazer é abrir uma janela de comando com privilégios de administrador e executar `wsl --install`. Após uma reinicialização, você estará pronto para usar o WSL.

- **[Instalação manual](#manual-installation-steps)** : Siga as seis etapas listadas abaixo.

    As etapas de instalação manual para WSL estão listadas abaixo e podem ser usadas para instalar o Linux em qualquer versão do Windows 10.

> [!NOTE]
> Se você encontrar um problema durante o processo de instalação, verifique a seção [Solução de problemas de instalação](#troubleshooting-installation) na parte inferior desta página.

## <a name="simplified-installation-for-windows-insiders"></a>Instalação simplificada para Participantes do Programa Windows Insider

O processo de instalação do Subsistema do Windows para Linux foi bastante aprimorado nas versões prévias mais recentes de Participantes do Programa Windows Insider do Windows 10, substituindo as etapas manuais abaixo por um único comando.

Para usar o comando de instalação simplificada de `wsl --install`, você precisa:

- Inscrever-se no [Programa Windows Insider](https://insider.windows.com/getting-started)
- Instalar uma versão prévia do Windows 10 (build do sistema operacional 20262 ou superior).
- Abra uma janela de linha de comando com privilégios de Administrador

Assim que esses requisitos forem atendidos, para instalar o WSL:

- Insira este comando na linha de comando que você abriu no modo Admin: `wsl.exe --install`
- Reinicie o computador

Na primeira vez que você iniciar uma distribuição do Linux recém-instalada, uma janela de console será aberta e será solicitado que você aguarde para que os arquivos sejam descompactados e armazenados em seu PC. Todas as futuras inicializações deverão levar menos de um segundo.

Em seguida, você precisará [criar uma conta de usuário e uma senha para sua nova distribuição do Linux](./user-support.md).

**PARABÉNS! Você instalou e configurou com êxito uma distribuição do Linux totalmente integrada ao seu sistema operacional Windows.**

O comando --install executa as seguintes ações:

- Habilita os componentes opcionais WSL e Plataforma de Máquina Virtual
- Baixa e instala o kernel do Linux mais recente
- Define WSL 2 como o padrão
- Faz download e instala uma distribuição do Linux *(talvez seja necessário fazer a reinicialização)*

Por padrão, a distribuição do Linux instalada será o Ubuntu. Isso pode ser alterado usando `wsl --install -d <Distribution Name>`. *(Substituindo `<Distribution Name>` pelo nome da distribuição desejada.)* Outras distribuições do Linux poderão ser adicionadas ao computador após a instalação inicial usando o comando `wsl --install -d <Distribution Name>`.

Para ver uma lista de distribuições do Linux disponíveis, insira `wsl --list --online`.

## <a name="manual-installation-steps"></a>Etapas de instalação manual

Se você não estiver em um build dos Participantes do Programa Windows Insider do Windows Insiders, os recursos necessários para WSL precisarão ser habilitados manualmente seguindo as etapas abaixo.

## <a name="step-1---enable-the-windows-subsystem-for-linux"></a>Etapa 1 – Habilitar o Subsistema do Windows para Linux

Antes de instalar qualquer distribuição do Linux no Windows, você precisará primeiro habilitar o recurso opcional "Subsistema do Windows para Linux".

Abra o PowerShell como administrador e execute:

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

Agora, é recomendável passar para a etapa 2, de atualização para o WSL 2. Mas, se você desejar instalar apenas o WSL 1, será possível **reiniciar** o computador e passar para a [Etapa 6 – Instalar a distribuição do Linux de sua escolha](./install-win10.md#step-6---install-your-linux-distribution-of-choice). Para atualizar para o WSL 2, **aguarde o seu computador ser reiniciado** e passe para a próxima etapa.

## <a name="step-2---check-requirements-for-running-wsl-2"></a>Etapa 2 – Verificar os requisitos para executar o WSL 2

Para atualizar para o WSL 2, você precisa estar executando o Windows 10.

- Para sistemas x64: **Versão 1903** ou superiores, com o **Build 18362** ou superiores.
- Para sistemas ARM64: **Versão 2004** ou superiores, com o **Build 19041** ou superiores.
- Os builds inferiores a 18362 não dão suporte a WSL 2. Use o [Assistente do Windows Update](https://www.microsoft.com/software-download/windows10) para atualizar a sua versão do Windows.

Para verificar a sua versão e o número de build, selecione a **tecla do logotipo do Windows + R**, digite **winver** e selecione **OK**. (Ou digite o comando `ver` no prompt de comando do Windows). [Atualize para a versão mais recente do Windows](ms-settings:windowsupdate) no menu Configurações.

> [!NOTE]
> Se você estiver executando o Windows 10 versão 1903 ou 1909, abra "Configurações" no menu do Windows, navegue até "Atualizações e Segurança" e selecione "Verificar Atualizações". O número de Build precisa ser 18362.1049+ ou 18363.1049+ e o nº do build secundário deve ser maior que .1049. Leia mais: [O suporte a WSL 2 estará disponível em breve nas Versões 1903 e 1909 do Windows 10](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/). Confira as [instruções de solução de problemas](./troubleshooting.md#im-on-windows-10-version-1903-and-i-still-do-not-see-options-for-wsl-2).

## <a name="step-3---enable-virtual-machine-feature"></a>Etapa 3 – Habilitar o recurso de Máquina Virtual

Antes de instalar o WSL 2, você precisa habilitar o recurso opcional **Plataforma de Máquina Virtual**. Seu computador exigirá [funcionalidades de virtualização](https://docs.microsoft.com/windows/wsl/troubleshooting#error-0x80370102-the-virtual-machine-could-not-be-started-because-a-required-feature-is-not-installed) para usar esse recurso.

Abra o PowerShell como administrador e execute:

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

**Reinicie** o computador para concluir a instalação do WSL e a atualização para o WSL 2.

## <a name="step-4---download-the-linux-kernel-update-package"></a>Etapa 4 – Baixar o pacote de atualização do kernel do Linux

1. Baixar o pacote mais recente:
    - [Pacote de atualização do kernel do Linux do WSL2 para computadores x64](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

    > [!NOTE]
    > Se estiver usando um computador ARM64, baixe o [pacote ARM64](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi). Se você não tiver certeza do tipo do seu computador, abra o Prompt de Comando ou o PowerShell e insira: `systeminfo | find "System Type"`.

2. Execute o pacote de atualização baixado na etapa anterior. (Clique duas vezes para executar. Você receberá uma solicitação para fornecer permissões elevadas; selecione 'sim' para aprovar essa instalação.)

Depois que a instalação for concluída, vá para a próxima etapa: configurar o WSL 2 como a sua versão padrão ao instalar novas distribuições do Linux (ignore essa etapa se você quiser que as novas instalações do Linux sejam definidas como WSL 1).

> [!NOTE]
> Para obter mais informações, leia o artigo [Alterações na atualização do kernel do Linux para o WSL 2](https://devblogs.microsoft.com/commandline/wsl2-will-be-generally-available-in-windows-10-version-2004), disponível no [blog da linha de comando do Windows](https://aka.ms/cliblog).

## <a name="step-5---set-wsl-2-as-your-default-version"></a>Etapa 5 – Definir o WSL 2 como a sua versão padrão

Abra o PowerShell e execute este comando para definir o WSL 2 como a versão padrão ao instalar uma nova distribuição do Linux:

```powershell
wsl --set-default-version 2
```

## <a name="step-6---install-your-linux-distribution-of-choice"></a>Etapa 6 – Instalar a distribuição do Linux de sua escolha

1. Abra a [Microsoft Store](https://aka.ms/wslstore) e escolha sua distribuição do Linux favorita.

    ![Exibição das distribuições do Linux na Microsoft Store](media/store.png)

    Os links a seguir abrirão a página da Microsoft Store para cada distribuição:

    - [Ubuntu 16.04 LTS](https://www.microsoft.com/store/apps/9pjn388hp8c9)
    - [Ubuntu 18.04 LTS](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
    - [Ubuntu 20.04 LTS](https://www.microsoft.com/store/apps/9n6svws3rx71)
    - [OpenSUSE Leap 15.1](https://www.microsoft.com/store/apps/9NJFZK00FGKV)
    - [SUSE Linux Enterprise Server 12 SP5](https://www.microsoft.com/store/apps/9MZ3D1TRP8T1)
    - [SUSE Linux Enterprise Server 15 SP1](https://www.microsoft.com/store/apps/9PN498VPMF3Z)
    - [Kali Linux](https://www.microsoft.com/store/apps/9PKR34TNCV07)
    - [Debian GNU/Linux](https://www.microsoft.com/store/apps/9MSVKQC78PK6)
    - [Fedora Remix para WSL](https://www.microsoft.com/store/apps/9n6gdm4k2hnc)
    - [Pengwin](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
    - [Pengwin Enterprise](https://www.microsoft.com/store/apps/9N8LP0X93VCP)
    - [Alpine WSL](https://www.microsoft.com/store/apps/9p804crf0395)

2. Na página da distribuição, selecione "Obter".

    ![Distribuições do Linux na Microsoft Store](media/UbuntuStore.png)

Na primeira vez que você iniciar uma distribuição do Linux recém-instalada, uma janela de console será aberta e será solicitado que você aguarde um ou dois minutos para que os arquivos sejam descompactados e armazenados em seu PC. Todas as futuras inicializações deverão levar menos de um segundo.

Em seguida, você precisará [criar uma conta de usuário e uma senha para sua nova distribuição do Linux](./user-support.md).

![Desempacotamento do Ubuntu no console do Windows](media/UbuntuInstall.png)

**PARABÉNS! Você instalou e configurou com êxito uma distribuição do Linux totalmente integrada ao seu sistema operacional Windows.**

## <a name="install-windows-terminal-optional"></a>Instalar o Terminal do Windows (opcional)

O Terminal do Windows permite habilitar várias guias (para alternar rapidamente entre as linhas de comando do Linux, o Prompt de Comando do Windows, o PowerShell, a CLI do Azure etc.), criar associações de chave personalizadas (teclas de atalho para abrir ou fechar guias, copiar e colar etc.), usar o recurso de pesquisa e configurar temas personalizados (esquemas de cores, estilos e tamanhos de fonte, imagem de tela de fundo/desfoque/transparência). [Saiba mais.](/windows/terminal)

[Instalar o Terminal do Windows](/windows/terminal/get-started).

  ![Terminal do Windows](media/terminal.png)

## <a name="set-your-distribution-version-to-wsl-1-or-wsl-2"></a>Definir a versão de distribuição para WSL 1 ou WSL 2

Verifique a versão do WSL atribuída a cada uma das distribuições do Linux instaladas abrindo a linha de comando do PowerShell e inserindo o comando (disponível somente no [Windows Build 18362 ou superior](ms-settings:windowsupdate)): `wsl -l -v`

```powershell
wsl --list --verbose
```

Para definir uma distribuição para ter suporte de qualquer versão do WSL, execute:

```powershell
wsl --set-version <distribution name> <versionNumber>
```

Assegure-se de substituir `<distribution name>` pelo nome real da sua distribuição e `<versionNumber>` pelo número '1' ou '2'. Você pode retornar ao WSL 1 a qualquer momento executando o mesmo comando acima, mas substituindo “2” por “1”.

> [!NOTE]
> A atualização da WSL 1 para a WSL 2 pode levar vários minutos para ser concluída, dependendo do tamanho da sua distribuição alvo. Se você estiver executando uma instalação mais antiga (herdada) do WSL 1 da Atualização para Criadores ou da Atualização de Aniversário do Windows 10, poderá encontrar um erro de atualização. Siga estas instruções para [desinstalar e remover as distribuições herdadas](./install-legacy.md#uninstallingremoving-the-legacy-distro).
>
> Se `wsl --set-default-version` resultar como um comando inválido, insira `wsl --help`. Se `--set-default-version` não estiver listado, isso significa que o sistema operacional não é compatível com ele, e você precisará atualizá-lo para a versão 1903, Build 18362 ou superior.
>
> Você verá esta mensagem depois de executar o comando: `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`. Você ainda precisa instalar o pacote de atualização MSI do kernel do Linux.

Além disso, se quiser tornar o WSL 2 sua arquitetura padrão, você poderá fazê-lo com este comando:

```powershell
wsl --set-default-version 2
```

Isso definirá a versão de qualquer nova distribuição instalada no WSL 2.

## <a name="troubleshooting-installation"></a>Como solucionar problemas de instalação

Veja abaixo erros relacionados e correções sugeridas. Consulte a [página de solução de problemas do WSL](troubleshooting.md) para ver outros erros comuns e suas soluções.

- **Falha na instalação com o erro 0x80070003**
  - O Subsistema Windows para Linux é executado somente na unidade do sistema (normalmente, a unidade `C:`). Verifique se as distribuições estão armazenadas na unidade do sistema:  
  - Abra **Configurações** -> **Sistema –> **Armazenamento** -> **Mais Configurações de Armazenamento: Altere onde o novo conteúdo é salvo**
    ![Imagem das configurações do sistema para instalar aplicativos na unidade C:](media/AppStorage.png)

- **WslRegisterDistribution falhou com o erro 0x8007019e**
  - O componente opcional do Subsistema Windows para Linux não está habilitado:
  - Abra **Painel de Controle** -> **Programas e Recursos** -> **Ativar ou Desativar Recursos do Windows** -> Selecione **Subsistema do Windows para Linux** ou use o cmdlet PowerShell mencionado no início deste artigo.

- **Ocorreu falha na instalação com o erro 0x80070003 ou 0x80370102**
  - Verifique se a virtualização está habilitada dentro do BIOS do seu computador. As instruções para fazer isso variam de um computador para o outro e muito provavelmente estarão sob opções relacionadas à CPU.

- **Erro ao tentar fazer upgrade: `Invalid command line option: wsl --set-version Ubuntu 2`**
  - Verifique se você tem o Subsistema do Windows para Linux habilitado e se está usando o Windows versão do Build 18362 ou superior. Para habilitar o WSL, execute este comando em um prompt do PowerShell com privilégios de administrador: `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`.

- **A operação solicitada não pôde ser concluída devido a uma limitação do sistema de disco virtual. Os arquivos do disco rígido virtual devem ser descompactados e descriptografados e não devem ser esparsos.**
  - Desmarque "Compactar conteúdo" (bem como "Criptografar conteúdo", se estiver marcado) abrindo a pasta de perfil da sua distribuição do Linux. Ela deve estar localizada em uma pasta no sistema de arquivos do Windows, algo como: `USERPROFILE%\AppData\Local\Packages\CanonicalGroupLimited...`
  - Nesse perfil de distribuição do Linux, deve haver uma pasta LocalState. Clique com o botão direito do mouse nessa pasta para exibir um menu de opções. Selecione Propriedades > Avançado e, em seguida, verifique se as caixas de seleção "Compactar conteúdo para economizar espaço em disco" e "Criptografar conteúdo para proteger dados" estão desmarcadas (não selecionadas). Se for solicitado que você aplique isso apenas à pasta atual ou a todas as subpastas e arquivos, selecione "somente esta pasta" porque você só vai limpar o sinalizador de compactação. Depois disso, o comando `wsl --set-version` deve funcionar.

![Captura de tela das configurações da propriedade de distribuição do WSL](media/troubleshooting-virtualdisk-compress.png)

> [!NOTE]
> No meu caso, a pasta LocalState da minha distribuição do Ubuntu 18.04 estava localizada em C:\Users\<my-user-name>\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc
>
> Para obter informações atualizadas, verifique o [thread 4103 do GitHub dos documentos do WSL](https://github.com/microsoft/WSL/issues/4103) em que esse problema está sendo acompanhado.

- **O termo 'wsl' não é reconhecido como nome de um cmdlet, uma função, um arquivo de script ou um programa operável.**
  - Verifique se o [componente opcional do Subsistema do Windows para Linux está instalado](./install-win10.md#step-3---enable-virtual-machine-feature). Além disso, se você estiver usando um dispositivo ARM64 e executar esse comando no PowerShell, receberá esse erro. Em vez disso, execute `wsl.exe` no [PowerShell Core](/powershell/scripting/install/installing-powershell-core-on-windows) ou no prompt de comando.

- **Erro: esta atualização se aplica somente a computadores com o Subsistema do Windows para Linux.**
  - Para instalar o pacote MSI de atualização do kernel do Linux, o WSL é exigido e deve ser habilitado primeiro. Se ele falhar, você verá a mensagem: `This update only applies to machines with the Windows Subsystem for Linux`.
  - Há três motivos possíveis para você ver essa mensagem:

  1. Você ainda está usando uma versão antiga do Windows, que não dá suporte ao WSL 2. Confira a etapa nº 2 para obter os requisitos de versão e os links a serem atualizados.

  2. O WSL não está habilitado. Você precisará retornar à etapa nº 1 e verificar se o recurso opcional do WSL está habilitado no seu computador.

  3. Depois que você habilitar o WSL, uma reinicialização será exigida para que ele entre em vigor. Reinicialize o computador e tente novamente.

- **Erro: o WSL 2 exige uma atualização do componente kernel. Para obter mais informações, visite https://aka.ms/wsl2kernel.**
  - Se o pacote do kernel do Linux está ausente na pasta %SystemRoot%\system32\lxss\tools, você encontra esse erro. Resolva-o instalando o pacote MSI de atualização do kernel do Linux na etapa nº 4 das instruções de instalação. Talvez você precise desinstalar o MSI em ['Adicionar ou Remover Programas'](ms-settings:appsfeatures-app) e instalar ele novamente.
