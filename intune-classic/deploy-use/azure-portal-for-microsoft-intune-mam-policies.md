---
title: "Azure ポータルの MAM ポリシー対応"
description: "Azure ポータルを使用してモバイル アプリ管理ポリシーを作成します。 ここで作成したポリシーは、Intune に登録されているデバイスにも未登録のデバイスにも適用できます。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3ac0ad32c8dc66ef1cb7878f67290c89df31a64b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="azure-portal-for-intune-app-protection-policies"></a><span data-ttu-id="02d46-104">Intune アプリ保護ポリシーの Azure ポータル</span><span class="sxs-lookup"><span data-stu-id="02d46-104">Azure portal for Intune app protection policies</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="02d46-105">Azure ポータルを使用して、次のようなアプリに対してアプリ保護ポリシー作成して管理できます。</span><span class="sxs-lookup"><span data-stu-id="02d46-105">The Azure portal is used to create and manage app protection policies for:</span></span>

- <span data-ttu-id="02d46-106">**Intune で登録および管理されている**デバイスで実行中のアプリ</span><span class="sxs-lookup"><span data-stu-id="02d46-106">Apps running on devices that are **enrolled and managed in Intune**.</span></span>

- <span data-ttu-id="02d46-107">どの MDM ソリューションにも**登録していない**デバイスで実行中のアプリ</span><span class="sxs-lookup"><span data-stu-id="02d46-107">Apps running on devices that are **not enrolled** in any MDM solution.</span></span>
- <span data-ttu-id="02d46-108">**サード パーティの MDM ソリューションに登録済み**のデバイスで実行中のアプリ</span><span class="sxs-lookup"><span data-stu-id="02d46-108">Apps running on devices that are **enrolled in a third-party MDM solution**.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="02d46-109">Azure ポータルはアプリ保護ポリシーを作成するための新しい管理コンソールです。ただし、MDM シナリオの [Intune 管理コンソール](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)を利用し、Intune に登録したデバイスのアプリをサポートするアプリ保護ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="02d46-109">The Azure portal is the new admin console for creating app protection policies, but you can also create an app protection policy that supports apps for devices enrolled into Intune by using the [Intune admin console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) for MDM scenarios.</span></span>

> <span data-ttu-id="02d46-110">Intune 管理コンソールでは、アプリ保護ポリシー設定の一部が利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02d46-110">You might not see all the app protection policy settings available on the Intune admin console.</span></span> <span data-ttu-id="02d46-111">また、Intune 管理コンソールと Azure ポータルの両方でアプリ保護ポリシーを作成した場合、Azure ポータルで作成されたポリシーは、Intune 管理コンソールで作成されたポリシーに優先します。</span><span class="sxs-lookup"><span data-stu-id="02d46-111">Additionally, if you create app protection policies both on the Intune admin console and in the Azure portal, the policies created in the Azure portal will override the ones created on the Intune admin console.</span></span> <span data-ttu-id="02d46-112">このシナリオでは、Azure ポータルアプリ保護ポリシーはアプリに適用され、ユーザーにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="02d46-112">In this scenario, the Azure portal app protection policies will be applied to the apps and deployed to users.</span></span>


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a><span data-ttu-id="02d46-113">Azure ポータルにサインインし、スタート ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="02d46-113">Sign in to the Azure portal and customize your start page</span></span>

1.  <span data-ttu-id="02d46-114">[Azure Portal](https://portal.azure.com) に移動し、Intune 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="02d46-114">Go to the [Azure portal](https://portal.azure.com) and sign in with your Intune credentials.</span></span>

    ![Azure ポータルのサインイン ページのスクリーンショット](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  <span data-ttu-id="02d46-116">正常にサインインすると、**ダッシュボード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="02d46-116">After you've successfully signed in, you see the **Dashboard**.</span></span> <span data-ttu-id="02d46-117">**ダッシュボード** ページはカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="02d46-117">The **Dashboard** page can be customized.</span></span>

    ![Azure ポータルのダッシュボードのスクリーンショット](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  <span data-ttu-id="02d46-119">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="02d46-119">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

    ![[参照] メニューのスクリーンショット、[Intune] が強調表示されています](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  <span data-ttu-id="02d46-121">**[Intune アプリ保護]** > **[Intune モバイル アプリケーション管理]** > **[すべての設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="02d46-121">Choose **Intune App Protection** > **Intune mobile application management** > **All Settings**.</span></span>

    ![[Intune モバイル アプリケーション管理] ブレードのスクリーンショット](../media/AppManagement/MAM-Azure-Portal-2.png)

5. <span data-ttu-id="02d46-123">(任意): ブレードを **[開始]** ページにピン留めするには、ブレードの **[ピン留め]** オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02d46-123">(Optional): To pin a blade to the **Start** page, you can use the **pin** option on the blade.</span></span> <span data-ttu-id="02d46-124">**[Intune モバイル アプリケーション管理ブレード]**のピン アイコンをクリックして、そのブレードを **[開始]** ページにピン留めします。</span><span class="sxs-lookup"><span data-stu-id="02d46-124">Click the pin icon on the **Intune mobile application management blade** to pin that blade to the **Start** page.</span></span>

    ![ピン アイコンが強調表示されている [Intune モバイル アプリケーション管理] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Intune タイルが固定されているダッシュボードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a><span data-ttu-id="02d46-127">次のステップ</span><span class="sxs-lookup"><span data-stu-id="02d46-127">Next steps</span></span>
[<span data-ttu-id="02d46-128">アプリ保護ポリシーを構成する準備をする</span><span class="sxs-lookup"><span data-stu-id="02d46-128">Get ready to configure app protection policies</span></span>](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
