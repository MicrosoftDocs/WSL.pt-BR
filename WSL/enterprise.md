---
title: Subsistema do Windows para Linux for Enterprise
description: Recursos e instruções sobre como usar melhor o Subsistema do Windows para Linux em um ambiente empresarial.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, debian, suse, windows 10, enterprise, deployment, offline, packaging, store, distribution, installation, install
ms.date: 05/15/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: ac0025257ae70547c5b20d89535510a8b8bb006c
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413097"
---
# <a name="set-up-windows-subsystem-for-linux-for-your-enterprise-company"></a>Configurar o Subsistema do Windows para Linux para sua empresa

A Microsoft Store para Empresas oferece uma variedade de soluções para empresas que desejam implantar o WSL. Os [documentos da Microsoft Store para Empresas e Educação](/microsoft-store/) são um ótimo recurso para descobrir informações gerais sobre a experiência na Store.

Se a sua empresa pretende iniciar a implantação do WSL, siga estas etapas:

* [Inscreva-se na Microsoft Store para Empresas e comece a usá-la](/microsoft-store/sign-up-microsoft-store-for-business-overview)
* [Gerencie seus produtos e serviços (incluindo quem pode acessar quais aplicativos em seu repositório privado)](/microsoft-store/manage-apps-microsoft-store-for-business-overview). Aqui você pode adicionar as distribuições do WSL ao seu repositório e controlar quem pode instalá-las
* [Use um método de distribuição de sua escolha para implantar o software em sua empresa](/microsoft-store/distribute-apps-to-your-employees-microsoft-store-for-business)
* Comunique-se aos funcionários de sua empresa que eles podem usar este link de documentação para instalar o WSL: [Instalar o Subsistema do Windows para Linux](./install-win10.md)

## <a name="how-to-distribute-a-linux-distribution-on-windows-offline"></a>Como distribuir uma distribuição do Linux no Windows offline

Se os computadores de sua empresa não tiverem acesso à Microsoft Store ou à Microsoft Store para Empresas, você poderá baixar o instalador de uma distribuição do Linux que tenha uma licença offline seguindo estas etapas.

### <a name="set-up-an-azure-active-directory-account"></a>Configure uma conta do Azure Active Directory

Você precisa [inscrever-se em uma conta do Azure AD](/azure/active-directory/fundamentals/sign-up-organization?WT.mc_id=windows-c9-niner) e ser o administrador global de sua organização para obter o instalador dos aplicativos da Microsoft Store. Se você já tiver uma conta, pule esta etapa.

### <a name="set-up-wsl-using-your-microsoft-store-for-business-account"></a>Configurar o WSL usando sua conta da Microsoft Store para Empresas

As instruções para registrar uma conta podem ser encontradas aqui: https://docs.microsoft.com/microsoft-store/sign-up-microsoft-store-for-business

1. Entre na Store para Empresas e acesse a home page: https://www.microsoft.com/business-store

    ![Home page da MS Store para Empresas](media/offlineinstallscreens/1-screen.png)

2. Vá para Gerenciar > Configurações e habilite 'Mostrar aplicativos offline'.

    ![Página de configurações da MS Store para Empresas](media/offlineinstallscreens/2-screen.png)

3. Volte para a página principal selecionando 'Comprar para o meu grupo'.

    ![Home page da MS Store para Empresas](media/offlineinstallscreens/1-screen.png)

4. Pesquise a distribuição desejada e selecione-a.

    ![Home page da MS Store para Empresas com pesquisa ativa](media/offlineinstallscreens/3-screen.png)

5. Selecione uma licença 'Offline' no menu suspenso Tipo de licença e selecione 'Obter o aplicativo'. (Algumas distribuições do Linux podem não fornecer uma licença offline).

    ![Seleção do Ubuntu da MS Store para Empresas offline](media/offlineinstallscreens/4-screen.png)

6. Selecione o botão 'Gerenciar' para acessar a página do produto do aplicativo.

    ![Seleção para gerenciar do Ubuntu da MS Store para Empresas](media/offlineinstallscreens/5-screen.png)

7. Selecione sua arquitetura e baixe o pacote para uso offline.

    ![Seleção de arquitetura do Ubuntu da MS Store para Empresas](media/offlineinstallscreens/6-screen.png)

Esse instalador pode ser distribuído para qualquer computador em que você queira instalar o WSL.
