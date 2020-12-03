---
title: Solução de problemas do Subsistema Windows para Linux
description: Fornece informações detalhadas sobre erros comuns e problemas que as pessoas têm ao executar o Linux no Subsistema Windows para Linux.
keywords: BashOnWindows, bash, wsl, windows, windowssubsystem, ubuntu
ms.date: 09/28/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: f4040cbe9faf5d55324b56974dd5677052224dd1
ms.sourcegitcommit: d5d3dd8b91e93d46653f9512bceafd8b5340255f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96443753"
---
# <a name="troubleshooting-windows-subsystem-for-linux"></a>Solução de problemas do Subsistema Windows para Linux

Para obter suporte com problemas relacionados ao WSL, confira o nosso [repositório do produto WSL no GitHub](https://github.com/Microsoft/wsl/issues).

## <a name="search-for-any-existing-issues-related-to-your-problem"></a>Procure problemas existentes relacionados ao seu problema

Para problemas técnicos, use o [repositório do produto](https://github.com/Microsoft/wsl/issues).

Para problemas relacionados ao conteúdo desta documentação, use o [repositório de documentos](https://github.com/MicrosoftDocs/wsl/issues).

## <a name="submit-a-bug-report"></a>Enviar um relatório de bugs

Para bugs relacionados a funções ou recursos do WSL, registre um problema no repositório do produto: https://github.com/Microsoft/wsl/issues

## <a name="submit-a-feature-request"></a>Enviar uma solicitação de recurso

Para solicitar um novo recurso relacionado à funcionalidade ou à compatibilidade do WSL, [registre um problema no repositório do produto](https://github.com/Microsoft/wsl/issues).

## <a name="contribute-to-the-docs"></a>Contribuir com os documentos

Para contribuir com a documentação do WSL, envie uma solicitação de pull no repositório de documentos: https://github.com/MicrosoftDocs/wsl/issues

## <a name="terminal-or-command-line"></a>Terminal ou Linha de comando

Por fim, se o problema estiver relacionado ao Terminal do Windows, ao console do Windows ou à interface do usuário da linha de comando, use o repositório de terminal do Windows: https://github.com/microsoft/terminal

## <a name="common-issues"></a>Problemas comuns

### <a name="im-on-windows-10-version-1903-and-i-still-do-not-see-options-for-wsl-2"></a>Estou usando o Windows 10, versão 1903, e ainda não vejo as opções relacionadas ao WSL 2

É provável que seu computador ainda não tenha feito o backport para o WSL 2. A maneira mais simples de resolver isso é indo até as Configurações do Windows e clicando em "Verificar Atualizações" para instalar as atualizações mais recentes no sistema. Veja as [instruções completas sobre como fazer o backport](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/#how-do-i-get-it).

Se você clicar em 'Verificar Atualizações' e ainda não receber a atualização, [instale a Base de Dados de Conhecimento KB4566116 manualmente](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4566116).  

### <a name="error-0x1bc-when-wsl---set-default-version-2"></a>Erro: 0x1bc quando `wsl --set-default-version 2`

Isso pode acontecer quando a configuração de 'Idioma de Exibição' ou 'Localidade do Sistema' não é inglês.

```powershell
wsl --set-default-version 2
Error: 0x1bc
For information on key differences with WSL 2 please visit https://aka.ms/wsl2
```

O erro real em `0x1bc` é:

```powershell
WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel
```

Para obter mais informações, veja o problema [5749](https://github.com/microsoft/WSL/issues/5749)

### <a name="cannot-access-wsl-files-from-windows"></a>Não é possível acessar arquivos do WSL por meio do Windows

Um servidor de arquivos do protocolo 9P fornece o serviço no lado do Linux para permitir que o Windows acesse o sistema de arquivos do Linux. Se você não conseguir acessar o WSL usando o `\\wsl$` no Windows, isso poderá ser devido a uma inicialização incorreta do 9P.

Para conferir isso, é possível verificar os logs de inicialização usando `dmesg |grep 9p`, o que mostra os erros existentes. Uma saída bem-sucedida tem a seguinte aparência:

```bash
[    0.363323] 9p: Installing v9fs 9p2000 file system support
[    0.363336] FS-Cache: Netfs '9p' registered for caching
[    0.398989] 9pnet: Installing 9P2000 support
```

Confira [este thread do GitHub](https://github.com/microsoft/wsl/issues/5307) para discussões mais aprofundadas sobre esse problema.

### <a name="cant-start-wsl-2-distribution-and-only-see-wsl-2-in-output"></a>Não é possível iniciar a distribuição do WSL 2 e apenas o texto 'WSL 2' é exibido na saída

Se seu idioma de exibição não for inglês, talvez você esteja vendo uma versão truncada de um texto de erro.

```powershell
C:\Users\me>wsl
WSL 2
```

Para resolver esse problema, visite `https://aka.ms/wsl2kernel` e instale o kernel manualmente, seguindo as instruções nessa página da documentação. 

### <a name="command-not-found-when-executing-windows-exe-in-linux"></a>`command not found` ao executar o Windows .exe no Linux

Os usuários podem executar os executáveis do Windows, como o notepad.exe, diretamente do Linux. Às vezes, a saída pode ser "command not found", como no seguinte exemplo: 

```Bash
$ notepad.exe
-bash: notepad.exe: command not found
```

Se não houver nenhum caminho do win32 no seu $PATH, a interoperabilidade não vai encontrar o .exe.
Você pode verificá-lo executando `echo $PATH` no Linux. Espera-se que você veja um caminho win32 (por exemplo, /mnt/c/Windows) na saída.
Se você não consegue ver nenhum caminho do Windows, é provável que PATH esteja sendo substituído pelo shell do Linux. 

Veja um exemplo em que /etc/profile no Debian contribuiu para o problema:

```Bash
if [ "`id -u`" -eq 0 ]; then
  PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
else
  PATH="/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games"
fi
```

No Debian, a maneira correta é remover as linhas acima.
Você também pode acrescentar $PATH durante a atribuição da maneira abaixo, mas isso resulta em alguns [outros problemas](https://salsa.debian.org/debian/WSL/-/commit/7611edba482fd0b3f67143aa0fc1e2cc1d4100a6) com o WSL e o VSCode.

Para obter mais informações, confira o problema [5296](https://github.com/microsoft/WSL/issues/5296) e o [5779](https://github.com/microsoft/WSL/issues/5779).

### <a name="error-0x80370102-the-virtual-machine-could-not-be-started-because-a-required-feature-is-not-installed"></a>"Error: 0x80370102. Não foi possível iniciar a máquina virtual porque um recurso necessário não está instalado. "

Habilite o recurso Plataforma de Máquina Virtual do Windows e verifique se a virtualização está habilitada na BIOS.

1. Verifique os [requisitos do sistema do Hyper-V](/windows-server/virtualization/hyper-v/system-requirements-for-hyper-v-on-windows#:~:text=on%20Windows%20Server.-,General%20requirements,the%20processor%20must%20have%20SLAT.)

2. Se o computador for uma VM, habilite a [virtualização aninhada](./wsl2-faq.md#can-i-run-wsl-2-in-a-virtual-machine) manualmente. Inicie o PowerShell com direitos de administrador e execute:

    ```powershell
    Set-VMProcessor -VMName <VMName> -ExposeVirtualizationExtensions $true
    ```

3. Siga as diretrizes do fabricante do seu PC sobre como habilitar a virtualização. Geralmente, isso envolve o uso da BIOS do sistema para garantir que esses recursos estejam habilitados em sua CPU. As instruções desse processo podem variar de acordo com o computador. Confira [este artigo](https://www.bleepingcomputer.com/tutorials/how-to-enable-cpu-virtualization-in-your-computer-bios/) do Bleeping Computer para obter um exemplo.

4. Reinicie o computador depois de habilitar o componente opcional `Virtual Machine Platform`.

### <a name="bash-loses-network-connectivity-once-connected-to-a-vpn"></a>O Bash perde conectividade de rede quando conectado a uma VPN

Se, depois de se conectar a uma VPN no Windows, o Bash perder a conectividade de rede, tente essa solução alternativa de dentro do Bash. Essa solução alternativa permitirá que você substitua manualmente a resolução DNS por meio do `/etc/resolv.conf`.

1. Anote o servidor DNS da VPN ao fazer `ipconfig.exe /all`
2. Faça uma cópia do `sudo cp /etc/resolv.conf /etc/resolv.conf.new` do resolv.conf existente
3. Desvincule o `sudo unlink /etc/resolv.conf` do resolv.conf atual
4. `sudo mv /etc/resolv.conf.new /etc/resolv.conf`
5. Abra `/etc/resolv.conf` e <br/>
   a. Exclua a primeira linha do arquivo, que diz "\# Este arquivo foi gerado automaticamente pelo WSL. Para interromper a geração automática deste arquivo, remova esta linha". <br/>
   b. Adicione a entrada DNS de (1) acima como a primeira entrada na lista de servidores DNS. <br/>
   c. Feche o arquivo. <br/>

Depois de desconectar a VPN, você precisará reverter as alterações para `/etc/resolv.conf`. Para isso, faça o seguinte:

1. `cd /etc`
2. `sudo mv resolv.conf resolv.conf.new`
3. `sudo ln -s ../run/resolvconf/resolv.conf resolv.conf`

### <a name="starting-wsl-or-installing-a-distribution-returns-an-error-code"></a>Iniciar o WSL ou instalar uma distribuição retorna um código de erro

Siga [estas instruções](https://github.com/Microsoft/WSL/blob/master/CONTRIBUTING.md#8-detailed-logs) para coletar logs detalhados e arquivar um problema em nosso GitHub.

### <a name="updating-bash-on-ubuntu-on-windows"></a>Como atualizar o Bash do Ubuntu no Windows

Há dois componentes do Bash do Ubuntu no Windows que podem exigir atualização.

1. O Subsistema Windows para Linux
  
   Atualizar essa parte do Bash do Ubuntu no Windows permitirá novas correções destacadas nas [notas sobre a versão](./release-notes.md). Certifique-se de que você está inscrito no Programa Windows Insider e que seu build está atualizado. Para obter um controle mais detalhado, incluindo a redefinição da instância do Ubuntu, confira a [página de referência de comando](./reference.md).

2. Os binários de usuário do Ubuntu

   A atualização dessa parte do Bash do Ubuntu no Windows instalará todas as atualizações nos binários de usuário do Ubuntu, incluindo os aplicativos que você instalou via apt-get. Para fazer isso, execute os seguintes comandos no Bash:
  
   1. `apt-get update`
   2. `apt-get upgrade`
  
### <a name="apt-get-upgrade-errors"></a>Erros de atualização do apt-get

Alguns pacotes usam recursos que ainda não implementamos. `udev`, por exemplo, ainda não é compatível e causa vários erros de `apt-get upgrade`.

Para corrigir problemas relacionados ao `udev`, siga as seguintes etapas:

1. Grave o seguinte no `/usr/sbin/policy-rc.d` e salve suas alterações.
  
   ```bash
   #!/bin/sh
   exit 101
   ```
  
2. Adicione permissões de execução a `/usr/sbin/policy-rc.d`:

   ```bash
   chmod +x /usr/sbin/policy-rc.d
   ```
  
3. Execute os comandos a seguir:

   ```bash
   dpkg-divert --local --rename --add /sbin/initctl
   ln -s /bin/true /sbin/initctl
   ```
  
### <a name="error-0x80040306-on-installation"></a>"Error: 0x80040306" na instalação

Isso tem a ver com o fato de não damos suporte ao console herdado.
Para desligar o console herdado:

1. Abra cmd.exe
1. Clique com o botão direito do mouse na barra de título-> Propriedades-> desmarque Usar console herdado
1. Clique em OK

### <a name="error-0x80040154-after-windows-update"></a>"Error: 0x80040154" após atualização do Windows

O recurso Subsistema Windows para Linux pode ser desabilitado durante uma atualização do Windows. Se isso acontecer, o recurso do Windows deverá ser habilitado novamente. As instruções para habilitar o Subsistema Windows para Linux podem ser encontradas no [Guia de instalação](./install-win10.md).

### <a name="changing-the-display-language"></a>Como alterar o idioma de exibição

A instalação do WSL tentará alterar automaticamente a localidade do Ubuntu para corresponder à localidade da instalação do Windows.  Se você não quiser esse comportamento, poderá executar esse comando para alterar a localidade do Ubuntu após a conclusão da instalação.  Você precisará reiniciar o bash.exe para que essa alteração entre em vigor.

O exemplo abaixo altera a localidade para en-US:

```bash
sudo update-locale LANG=en_US.UTF8
```

### <a name="installation-issues-after-windows-system-restore"></a>Problemas de instalação após a restauração do sistema do Windows

1. Exclua a pasta `%windir%\System32\Tasks\Microsoft\Windows\Windows Subsystem for Linux`. <br/>
  **Observação: Não faça isso se o recurso opcional estiver totalmente instalado e funcionando.**
2. Habilitar o recurso opcional do WSL (se ainda não estiver habilitado)
3. Reinicialização
4. lxrun /uninstall /full
5. Instale o Bash

### <a name="no-internet-access-in-wsl"></a>Sem acesso à Internet no WSL

Alguns usuários relataram problemas com aplicativos de firewall específicos que bloqueiam o acesso à Internet no WSL.  Os firewalls relatados são:

1. Kaspersky
2. AVG
3. Avast

Em alguns casos, desligar o firewall permite o acesso.  Em outros, simplesmente ter o firewall instalado bloqueia o acesso.

### <a name="permission-denied-error-when-using-ping"></a>Erro de permissão negada ao usar ping

Para a [Atualização de Aniversário do Windows, versão 1607](./release-notes.md#build-14388-to-windows-10-anniversary-update), são necessários **privilégios de administrador** no Windows para executar o ping no WSL.  Para executar o ping, execute o Bash do Ubuntu no Windows como administrador ou execute bash.exe em um prompt do CMD/PowerShell com privilégios de administrador.

Para versões posteriores do Windows, [Build 14926 e posteriores](./release-notes.md#build-14926), os privilégios de administrador não são mais necessários.

### <a name="bash-is-hung"></a>Bash suspenso

Se, ao trabalhar com o Bash, você descobrir que ele está suspenso (ou em deadlock) e não está respondendo às entradas, ajude-nos a diagnosticar o problema coletando e relatando um despejo de memória. Observe que essas etapas apresentarão falha no sistema. Não faça isso se não estiver familiarizado ou salve seu trabalho antes.

Para coletar um despejo de memória

1. Altere o tipo de despejo de memória para "despejo de memória completo". Ao alterar o tipo de despejo, anote seu tipo atual.

2. Use as [etapas](https://techcommunity.microsoft.com/t5/Core-Infrastructure-and-Security/How-to-Force-a-Diagnostic-Memory-Dump-When-a-Computer-Hangs/ba-p/257809) para configurar a falha usando o controle de teclado.

3. Reproduza o travamento ou o deadlock.

4. Cause uma falha no sistema usando a sequência de teclas de (2).

5. O sistema falhará e coletará o despejo de memória.

6. Após a reinicialização do sistema, relate o memory.dmp a secure@microsoft.com. A localização padrão do arquivo de despejo será %SystemRoot%\memory.dmp ou C:\Windows\memory.dmp se a unidade do sistema for C:. No email, observe que o despejo é para o WSL ou Bash na equipe do Windows.

7. Restaure o tipo de despejo de memória para a configuração original.

### <a name="check-your-build-number"></a>Verifique o número de build

Para encontrar a arquitetura do seu PC e o número de build do Windows, abra  
**Configurações** > **Sistema** > **Sobre**

Procure os campos **Build do SO** e **Tipo de Sistema**.  
    ![Captura de tela dos campos Build e Tipo de Sistema](media/system.png)

Para localizar o número de build do Windows Server, execute o seguinte no PowerShell:  

``` PowerShell
systeminfo | Select-String "^OS Name","^OS Version"
```

### <a name="confirm-wsl-is-enabled"></a>Confirme se o WSL está habilitado

É possível confirmar se o Subsistema Windows para Linux está habilitado executando o seguinte no PowerShell:  

``` PowerShell
Get-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

### <a name="openssh-server-connection-issues"></a>Problemas de conexão do servidor OpenSSH

Falha ao tentar conectar seu servidor SSH com o seguinte erro: "Conexão encerrada pela porta 22, 127.0.0.1".

1. Verifique se o servidor OpenSSH está em execução:

   ```bash
   sudo service ssh status
   ```

   e que você seguiu este tutorial: https://ubuntu.com/server/docs/service-openssh

2. Interrompa o serviço SSHD e inicie o SSHD no modo de depuração:

   ```bash
   sudo service ssh stop
   sudo /usr/sbin/sshd -d
   ```

3. Verifique os logs de inicialização e certifique-se de que as HostKeys estejam disponíveis e que você não veja mensagens de log, como:

   ```BASH
   debug1: sshd version OpenSSH_7.2, OpenSSL 1.0.2g  1 Mar 2016
   debug1: key_load_private: incorrect passphrase supplied to decrypt private key
   debug1: key_load_public: No such file or directory
   Could not load host key: /etc/ssh/ssh_host_rsa_key
   debug1: key_load_private: No such file or directory
   debug1: key_load_public: No such file or directory
   Could not load host key: /etc/ssh/ssh_host_dsa_key
   debug1: key_load_private: No such file or directory
   debug1: key_load_public: No such file or directory
   Could not load host key: /etc/ssh/ssh_host_ecdsa_key
   debug1: key_load_private: No such file or directory
   debug1: key_load_public: No such file or directory
   Could not load host key: /etc/ssh/ssh_host_ed25519_key
   ```

Se você vir essas mensagens e as chaves estiverem ausentes em `/etc/ssh/`, será necessário regenerar as chaves ou apenas limpar e instalar o servidor OpenSSH:

```BASH
sudo apt-get purge openssh-server
sudo apt-get install openssh-server
```

### <a name="the-referenced-assembly-could-not-be-found-when-enabling-the-wsl-optional-feature"></a>"Não foi possível encontrar o assembly referenciado." ao habilitar o recurso opcional WSL (Subsistema Windows para Linux)

Este erro está relacionado a um estado de instalação inadequado. Conclua as etapas a seguir para tentar corrigir esse problema:

- Se você estiver executando o comando Habilitar recurso WSL do PowerShell, tente usar a GUI em vez de abrir o menu Iniciar, pesquisando "Ativar ou desativar recursos do Windows" e, na lista, selecione "Subsistema do Windows para Linux", que instalará o componente opcional.

- Atualize sua versão do Windows acessando Configurações, Atualizações e clicando em "Verificar se há atualizações"

- Se ambas falharem e você precisar acessar o WSL, considere atualizar no local reinstalando o Windows 10 com uma mídia de instalação e selecionando "Manter Tudo" para que seus aplicativos e arquivos sejam preservados. É possível encontrar instruções para fazer isso na [página Reinstalar o Windows 10](https://support.microsoft.com/help/4000735/windows-10-reinstall).

### <a name="correct-ssh-related-permission-errors"></a>Erros de permissão corretos (relacionados a SSH)

Se você vir este erro:

```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0777 for '/home/artur/.ssh/private-key.pem' are too open.
```

Para corrigi-lo, acrescente o seguinte ao arquivo ```/etc/wsl.conf```:

```bash
[automount]
enabled = true
options = metadata,uid=1000,gid=1000,umask=0022
```

Ao adicionar esse comando, você incluirá metadados e modificará as permissões do arquivo nos arquivos Windows vistos em WSL. Confira as [Permissões do sistema de arquivos](./file-permissions.md) para saber mais.

### <a name="running-windows-commands-fails-inside-a-distribution"></a>Ocorre uma falha na execução de comandos do Windows dentro de uma distribuição

Algumas distribuições [disponíveis na Microsoft Store](install-win10.md#step-6---install-your-linux-distribution-of-choice) ainda não são totalmente compatíveis com a execução de comandos do Windows em um [Terminal](https://en.wikipedia.org/wiki/Linux_console) pronto para uso. Caso receba o erro `-bash: powershell.exe: command not found` ao executar `powershell.exe /c start .` ou outro comando do Windows, será possível resolvê-lo seguindo estas etapas:

1. Na distribuição de WSL, execute `echo $PATH`.  
   Caso ele não inclua `/mnt/c/Windows/system32`, isso significa que algo está redefinindo a variável PATH padrão.
2. Verifique as configurações de perfil com `cat /etc/profile`.  
   Caso ele contenha uma atribuição da variável PATH, edite o arquivo para fazer comentários no bloco de atribuição PATH com um caractere **#** .
3. Verifique se wsl.conf está presente em `cat /etc/wsl.conf` e se não contém `appendWindowsPath=false`. Caso contrário, faça um comentário.
4. Reinicie a distribuição digitando `wsl -t `, depois o nome da distribuição ou execute `wsl --shutdown` no cmd ou no PowerShell.

### <a name="unable-to-boot-after-installing-wsl-2"></a>Não foi possível realizar a inicialização após a instalação do WSL 2

Estamos cientes de um problema que afeta os usuários, no qual eles não conseguem realizar a inicialização após a instalação do WSL 2. Embora possamos diagnosticar totalmente esses problemas, os usuários relataram que [alterar o tamanho do buffer](https://github.com/microsoft/WSL/issues/4784#issuecomment-639219363) ou [instalar os drivers corretos](https://github.com/microsoft/WSL/issues/4784#issuecomment-675702244) pode ajudar a resolver isso. Exiba este [problema do GitHub](https://github.com/microsoft/WSL/issues/4784) para conferir as atualizações mais recentes sobre esse problema. 
