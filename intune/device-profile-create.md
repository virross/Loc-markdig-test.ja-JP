---
title: "Intune デバイス構成プロファイルを作成する"
titlesuffix: Azure portal
description: "Intune デバイス構成プロファイルを作成する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f08818585d02cf0c27357cf4b43dd06e9f8e89c5
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a><span data-ttu-id="fecc1-103">Microsoft Intune でデバイス構成プロファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="fecc1-103">How to create device configuration profiles in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. <span data-ttu-id="fecc1-104">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="fecc1-104">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="fecc1-105">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="fecc1-105">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="fecc1-106">**[Intune]** ブレードで、**[デバイスの構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fecc1-106">On the **Intune** blade, choose **Configure devices**.</span></span>
2. <span data-ttu-id="fecc1-107">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="fecc1-107">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="fecc1-108">プロファイルの一覧が表示されているブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fecc1-108">On the blade showing the list of profiles, choose **Create Profile**.</span></span>
3. <span data-ttu-id="fecc1-109">**[プロファイルの作成]** ブレードで、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="fecc1-109">On the **Create Profile** blade, specify the following items:</span></span>
    - <span data-ttu-id="fecc1-110">**[名前]** - 新しいプロファイルのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fecc1-110">**Name** - Enter a descriptive name for the new profile.</span></span>
    - <span data-ttu-id="fecc1-111">**[説明]** - プロファイルの説明を入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="fecc1-111">**Description** -  Enter an optional description for the profile.</span></span>
    - <span data-ttu-id="fecc1-112">**[プラットフォーム]** - 作成するプロファイルのプラットフォームの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="fecc1-112">**Platform** -  Select the platform type for the profile you want to create.</span></span>
    - <span data-ttu-id="fecc1-113">**[プロファイルの種類]** - 作成するプロファイルの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="fecc1-113">**Profile type** - Select the type of profile you want to create.</span></span> <span data-ttu-id="fecc1-114">選択可能な種類の一覧は、選択したプラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fecc1-114">The list of available types differs depending on the platform you chose.</span></span>
    - <span data-ttu-id="fecc1-115">**[設定]** - プロファイルの種類ごとの設定に関する情報については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fecc1-115">**Settings** - See the following topics for information about the settings for each profile type:</span></span>
        -  [<span data-ttu-id="fecc1-116">デバイス機能設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-116">Device feature settings</span></span>](device-features-configure.md)
        -  [<span data-ttu-id="fecc1-117">デバイスの制限設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-117">Device restriction settings</span></span>](device-restrictions-configure.md)
        -  [<span data-ttu-id="fecc1-118">電子メールの設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-118">Email settings</span></span>](email-settings-configure.md)
        -  [<span data-ttu-id="fecc1-119">VPN 設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-119">VPN settings</span></span>](vpn-settings-configure.md)
        -  [<span data-ttu-id="fecc1-120">Wi-Fi 設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-120">Wi-Fi settings</span></span>](wi-fi-settings-configure.md)
        -  [<span data-ttu-id="fecc1-121">Windows 10 エディションのアップグレード設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-121">Windows 10 edition upgrade settings</span></span>](edition-upgrade-configure-windows-10.md)
        -  [<span data-ttu-id="fecc1-122">証明書の設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-122">Certificate settings</span></span>](certificates-configure.md)
        -  [<span data-ttu-id="fecc1-123">Windows 情報保護の設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-123">Windows Information Protection settings</span></span>](windows-information-protection-configure.md)
        -  [<span data-ttu-id="fecc1-124">教育設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-124">Education settings</span></span>](education-settings-configure.md)
        -  [<span data-ttu-id="fecc1-125">カスタム設定</span><span class="sxs-lookup"><span data-stu-id="fecc1-125">Custom settings</span></span>](custom-settings-configure.md)

    ![デバイス プロファイルの作成](./media/create-device-profile.png)
4. <span data-ttu-id="fecc1-127">設定の構成が完了したら、**[プロファイルを作成します]** ブレードで、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fecc1-127">Once you are done configuring settings, on the **Create Profile** blade, choose **Create**.</span></span>

<span data-ttu-id="fecc1-128">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fecc1-128">The profile is created and appears on the profiles list blade.</span></span>
<span data-ttu-id="fecc1-129">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fecc1-129">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>


### <a name="next-steps"></a><span data-ttu-id="fecc1-130">次のステップ</span><span class="sxs-lookup"><span data-stu-id="fecc1-130">Next steps</span></span>
<span data-ttu-id="fecc1-131">デバイス プロファイルを割り当てる方法については、[Microsoft Intune でデバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fecc1-131">For information about how to assign device profiles, see [How to assign device profiles with Microsoft Intune](device-profile-assign.md).</span></span>
