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
# <a name="set-up-windows-subsystem-for-linux-for-your-enterprise-company"></a><span data-ttu-id="51ffa-104">Configurar o Subsistema do Windows para Linux para sua empresa</span><span class="sxs-lookup"><span data-stu-id="51ffa-104">Set up Windows Subsystem for Linux for your enterprise company</span></span>

<span data-ttu-id="51ffa-105">A Microsoft Store para Empresas oferece uma variedade de soluções para empresas que desejam implantar o WSL.</span><span class="sxs-lookup"><span data-stu-id="51ffa-105">The Microsoft Store for Business offers a variety of solutions to Enterprises who want to deploy WSL to their company.</span></span> <span data-ttu-id="51ffa-106">Os [documentos da Microsoft Store para Empresas e Educação](/microsoft-store/) são um ótimo recurso para descobrir informações gerais sobre a experiência na Store.</span><span class="sxs-lookup"><span data-stu-id="51ffa-106">The [Microsoft Store for Business and Education docs](/microsoft-store/) are a great resource to find out general information about the Store experience.</span></span>

<span data-ttu-id="51ffa-107">Se a sua empresa pretende iniciar a implantação do WSL, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="51ffa-107">If you're a company that's just looking to get set up to start deploying WSL, follow these steps:</span></span>

* [<span data-ttu-id="51ffa-108">Inscreva-se na Microsoft Store para Empresas e comece a usá-la</span><span class="sxs-lookup"><span data-stu-id="51ffa-108">Sign up for the Microsoft Store for Business and get started</span></span>](/microsoft-store/sign-up-microsoft-store-for-business-overview)
* <span data-ttu-id="51ffa-109">[Gerencie seus produtos e serviços (incluindo quem pode acessar quais aplicativos em seu repositório privado)](/microsoft-store/manage-apps-microsoft-store-for-business-overview).</span><span class="sxs-lookup"><span data-stu-id="51ffa-109">[Manage your products and services (including who can access which apps in your private store)](/microsoft-store/manage-apps-microsoft-store-for-business-overview).</span></span> <span data-ttu-id="51ffa-110">Aqui você pode adicionar as distribuições do WSL ao seu repositório e controlar quem pode instalá-las</span><span class="sxs-lookup"><span data-stu-id="51ffa-110">Here you can add WSL distros to your store and control who can install them</span></span>
* [<span data-ttu-id="51ffa-111">Use um método de distribuição de sua escolha para implantar o software em sua empresa</span><span class="sxs-lookup"><span data-stu-id="51ffa-111">Use a distribution method of your choice to deploy the software to your company</span></span>](/microsoft-store/distribute-apps-to-your-employees-microsoft-store-for-business)
* <span data-ttu-id="51ffa-112">Comunique-se aos funcionários de sua empresa que eles podem usar este link de documentação para instalar o WSL: [Instalar o Subsistema do Windows para Linux](./install-win10.md)</span><span class="sxs-lookup"><span data-stu-id="51ffa-112">Communicate to the employees of your company that they can use this documentation link to install WSL: [Install the Windows Subsystem for Linux](./install-win10.md)</span></span>

## <a name="how-to-distribute-a-linux-distribution-on-windows-offline"></a><span data-ttu-id="51ffa-113">Como distribuir uma distribuição do Linux no Windows offline</span><span class="sxs-lookup"><span data-stu-id="51ffa-113">How to distribute a Linux distribution on Windows offline</span></span>

<span data-ttu-id="51ffa-114">Se os computadores de sua empresa não tiverem acesso à Microsoft Store ou à Microsoft Store para Empresas, você poderá baixar o instalador de uma distribuição do Linux que tenha uma licença offline seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="51ffa-114">If the computers in your company don't have access to the Microsoft Store or the Microsoft Store for Business, then you can download the installer of a Linux distribution that has an offline license by following these steps.</span></span>

### <a name="set-up-an-azure-active-directory-account"></a><span data-ttu-id="51ffa-115">Configure uma conta do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="51ffa-115">Set up an Azure Active Directory account</span></span>

<span data-ttu-id="51ffa-116">Você precisa [inscrever-se em uma conta do Azure AD](/azure/active-directory/fundamentals/sign-up-organization?WT.mc_id=windows-c9-niner) e ser o administrador global de sua organização para obter o instalador dos aplicativos da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="51ffa-116">You need to [sign up for an Azure AD account](/azure/active-directory/fundamentals/sign-up-organization?WT.mc_id=windows-c9-niner) and be the global administrator for your organization to get the installer of Microsoft Store apps.</span></span> <span data-ttu-id="51ffa-117">Se você já tiver uma conta, pule esta etapa.</span><span class="sxs-lookup"><span data-stu-id="51ffa-117">If you already have an account, you can skip this step.</span></span>

### <a name="set-up-wsl-using-your-microsoft-store-for-business-account"></a><span data-ttu-id="51ffa-118">Configurar o WSL usando sua conta da Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="51ffa-118">Set up WSL using your Microsoft Store for Business account</span></span>

<span data-ttu-id="51ffa-119">As instruções para registrar uma conta podem ser encontradas aqui: https://docs.microsoft.com/microsoft-store/sign-up-microsoft-store-for-business</span><span class="sxs-lookup"><span data-stu-id="51ffa-119">The instructions to register an account are found here: https://docs.microsoft.com/microsoft-store/sign-up-microsoft-store-for-business</span></span>

1. <span data-ttu-id="51ffa-120">Entre na Store para Empresas e acesse a home page: https://www.microsoft.com/business-store</span><span class="sxs-lookup"><span data-stu-id="51ffa-120">Sign into the Store for Business and go to the homepage: https://www.microsoft.com/business-store</span></span>

    ![Home page da MS Store para Empresas](media/offlineinstallscreens/1-screen.png)

2. <span data-ttu-id="51ffa-122">Vá para Gerenciar > Configurações e habilite 'Mostrar aplicativos offline'.</span><span class="sxs-lookup"><span data-stu-id="51ffa-122">Go to Manage > Settings and enable 'Show offline apps'.</span></span>

    ![Página de configurações da MS Store para Empresas](media/offlineinstallscreens/2-screen.png)

3. <span data-ttu-id="51ffa-124">Volte para a página principal selecionando 'Comprar para o meu grupo'.</span><span class="sxs-lookup"><span data-stu-id="51ffa-124">Go back to the main page by selecting 'Shop for my group'.</span></span>

    ![Home page da MS Store para Empresas](media/offlineinstallscreens/1-screen.png)

4. <span data-ttu-id="51ffa-126">Pesquise a distribuição desejada e selecione-a.</span><span class="sxs-lookup"><span data-stu-id="51ffa-126">Search for your desired distribution and select it.</span></span>

    ![Home page da MS Store para Empresas com pesquisa ativa](media/offlineinstallscreens/3-screen.png)

5. <span data-ttu-id="51ffa-128">Selecione uma licença 'Offline' no menu suspenso Tipo de licença e selecione 'Obter o aplicativo'.</span><span class="sxs-lookup"><span data-stu-id="51ffa-128">Select an 'Offline' license in the License type dropdown menu and select 'Get the app'.</span></span> <span data-ttu-id="51ffa-129">(Algumas distribuições do Linux podem não fornecer uma licença offline).</span><span class="sxs-lookup"><span data-stu-id="51ffa-129">(Some Linux distributions may elect not to provide an offline license).</span></span>

    ![Seleção do Ubuntu da MS Store para Empresas offline](media/offlineinstallscreens/4-screen.png)

6. <span data-ttu-id="51ffa-131">Selecione o botão 'Gerenciar' para acessar a página do produto do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="51ffa-131">Select the 'Manage' button to get to the app's product page.</span></span>

    ![Seleção para gerenciar do Ubuntu da MS Store para Empresas](media/offlineinstallscreens/5-screen.png)

7. <span data-ttu-id="51ffa-133">Selecione sua arquitetura e baixe o pacote para uso offline.</span><span class="sxs-lookup"><span data-stu-id="51ffa-133">Select your architecture and download the package for offline use.</span></span>

    ![Seleção de arquitetura do Ubuntu da MS Store para Empresas](media/offlineinstallscreens/6-screen.png)

<span data-ttu-id="51ffa-135">Esse instalador pode ser distribuído para qualquer computador em que você queira instalar o WSL.</span><span class="sxs-lookup"><span data-stu-id="51ffa-135">This installer can then be distributed to any computer where you would like to install WSL.</span></span>
