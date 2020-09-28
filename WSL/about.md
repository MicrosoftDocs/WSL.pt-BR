---
title: Sobre o Subsistema do Windows para Linux
description: Saiba mais sobre o Subsistema do Windows para Linux, incluindo informações sobre diferentes versões e de que maneira você pode usá-las.
keywords: BashOnWindows, bash, wsl, windows, windowssubsystem, gnu, linux
ms.date: 07/21/2020
ms.topic: article
ms.assetid: 3cefe0db-7616-4848-a2b6-9296746a178b
ms.localizationpriority: high
ms.openlocfilehash: 0c6fa3d0c5483a7ffd1fb95f13ca62666a7c1e72
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413077"
---
# <a name="what-is-the-windows-subsystem-for-linux"></a>O que é o Subsistema do Windows para Linux?

O Subsistema do Windows para Linux permite que os desenvolvedores executem um ambiente GNU/Linux, incluindo a maioria das ferramentas de linha de comando, utilitários e aplicativos, diretamente no Windows, sem modificações e sem a sobrecarga de uma máquina virtual tradicional ou instalação dualboot.

Você pode:

* Escolha sua distribuição do Linux/GNU favorita [na Microsoft Store](https://aka.ms/wslstore).
* Execute as ferramentas de linha de comando comuns, como `grep`, `sed`, `awk` ou outros binários ELF-64.
* Execute scripts de shell do Bash e aplicativos de linha de comando do GNU/Linux, incluindo:  
    * Ferramentas: vim, emacs, tmux
    * Linguagens: [Node.js](/windows/nodejs/setup-on-wsl2), Javascript, [Python](/windows/python/web-frameworks), Ruby, C/C++, C# & F#, Rust, Go etc.
    * Serviços: SSHD, [MySQL](./tutorials/wsl-database.md), Apache, lighttpd, [MongoDB](./tutorials/wsl-database.md), [PostgreSQL](./tutorials/wsl-database.md).
* Instale o software adicional usando o seu próprio gerenciador de pacotes de distribuição do GNU/Linux.
* Invoque aplicativos do Windows usando um shell de linha de comando do UNIX.
* Invoque aplicativos do GNU/Linux no Windows.

> [!div class="nextstepaction"]
> [Instalar o WSL](install-win10.md)

<br>

> [!VIDEO https://www.youtube.com/embed/48k317kOxqg]

## <a name="what-is-wsl-2"></a>O que é o WSL 2?

O WSL 2 é uma nova versão da arquitetura do Subsistema do Windows para Linux que capacita o Subsistema do Windows para Linux a executar binários ELF64 Linux no Windows. As metas principais dele são **aumentar o desempenho do sistema de arquivos** e adicionar **compatibilidade completa com a chamada do sistema**.

Essa nova arquitetura altera como esses binários do Linux interagem com o Windows e o hardware do computador, mas ainda fornece a mesma experiência do usuário que no WSL 1 (a versão atual amplamente disponível).

As distribuições individuais do Linux podem ser executadas com a arquitetura do WSL 1 ou do WSL 2. Cada distribuição pode passar por upgrade ou downgrade a qualquer momento e você pode executar distribuições do WSL 1 e do WSL 2 lado a lado. O WSL 2 usa uma arquitetura totalmente nova que se beneficia do uso de um kernel Linux real.

<br>

> [!VIDEO https://www.youtube.com/embed/MrZolfGm8Zk]

## <a name="next-steps"></a>Próximas etapas

* [Instalar o WSL 1 e atualizar para o WSL 2](./install-win10.md)

* [Comparar o WSL 2 e o WSL 1](./compare-versions.md)

* [Criar uma conta de usuário e uma senha para sua nova distribuição do Linux](./user-support.md)

* [Ler as perguntas frequentes](./faq.md)

* [Ler as perguntas frequentes sobre o WSL 2](./wsl2-faq.md)

* [Solução de problemas](./troubleshooting.md)

* [Executar comandos de interoperabilidade entre o Windows e o Linux](./interop.md)

* [Executar comandos e configurações de inicialização](./wsl-config.md)

* [Configurar as permissões de arquivo](./file-permissions.md)

* [Configurar o WSL para Empresas](./enterprise.md)

* [Comandos do WSL de referência](./reference.md)

* [Criar distribuições personalizadas](./build-custom-distro.md)

* [Ler as notas sobre a versão do WSL](./release-notes.md)