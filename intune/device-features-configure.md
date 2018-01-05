---
title: "Intune デバイス機能設定の構成"
titleSuffix: Azure portal
description: "Intune を使用して管理対象デバイスの機能を構成する方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 382a410fee9abdcb2a3b5670563f25264d477540
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a><span data-ttu-id="b35ee-103">Microsoft Intune でデバイスの機能設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b35ee-103">How to configure device feature settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b35ee-104">デバイス制約では、AirPrint、通知、共有デバイス構成など、iOS デバイスと macOS デバイスの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="b35ee-104">Device restrictions let you control features on iOS and macOS devices like AirPrint, notifications, and shared device configurations.</span></span>

<span data-ttu-id="b35ee-105">このトピックでは、デバイスの機能プロファイルを構成する基本的な方法について説明します。その後、デバイスごとの詳細については、各プラットフォームのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35ee-105">Use the information in this topic to learn the basics about configuring device feature profiles, and then read further topics for each platform to learn about device specifics.</span></span>

## <a name="create-a-device-profile-containing-device-restriction-settings"></a><span data-ttu-id="b35ee-106">デバイスの制限設定を含むデバイス プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="b35ee-106">Create a device profile containing device restriction settings</span></span>

1. <span data-ttu-id="b35ee-107">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b35ee-107">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b35ee-108">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b35ee-108">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="b35ee-109">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b35ee-109">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="b35ee-110">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b35ee-110">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="b35ee-111">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b35ee-111">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="b35ee-112">**[プロファイルを作成します]** ブレードで、デバイスの機能プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="b35ee-112">On the **Create Profile** blade, enter a **Name** and **Description** for the device features profile.</span></span>
5. <span data-ttu-id="b35ee-113">**[プラットフォーム]** ドロップダウン リストで、設定を適用するデバイス プラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="b35ee-113">From the **Platform** drop-down list, select the device platform to which you want to apply the settings.</span></span> <span data-ttu-id="b35ee-114">現時点では、デバイス機能に対応している次のいずれかのプラットフォームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b35ee-114">Currently, you can choose one of the following platforms for device features:</span></span>
    - <span data-ttu-id="b35ee-115">**Android**</span><span class="sxs-lookup"><span data-stu-id="b35ee-115">**iOS**</span></span>
    - <span data-ttu-id="b35ee-116">**macOS**</span><span class="sxs-lookup"><span data-stu-id="b35ee-116">**macOS**</span></span>
6. <span data-ttu-id="b35ee-117">**[プロファイルの種類]** ドロップダウン リストで、**[デバイス機能]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b35ee-117">From the **Profile type** drop-down list, choose **Device features**.</span></span> 
7. <span data-ttu-id="b35ee-118">選択したプラットフォームによって構成できる設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="b35ee-118">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="b35ee-119">各プラットフォームの詳細な設定については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35ee-119">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="b35ee-120">iOS および macOS 用 AirPrint の設定</span><span class="sxs-lookup"><span data-stu-id="b35ee-120">AirPrint settings for iOS and MacOS</span></span>](air-print-settings-ios-macos.md)
    - [<span data-ttu-id="b35ee-121">iOS 用 AirPlay の設定</span><span class="sxs-lookup"><span data-stu-id="b35ee-121">AirPlay settings for iOS</span></span>](airplay-settings-ios.md)
    - [<span data-ttu-id="b35ee-122">iOS 用ホーム画面のレイアウト設定</span><span class="sxs-lookup"><span data-stu-id="b35ee-122">Home screen layout settings for iOS</span></span>](home-screen-settings-ios.md)
    - [<span data-ttu-id="b35ee-123">iOS 用アプリの通知設定</span><span class="sxs-lookup"><span data-stu-id="b35ee-123">App notification settings for iOS</span></span>](app-notification-settings-ios.md)
    - [<span data-ttu-id="b35ee-124">iOS 用共有デバイス構成設定</span><span class="sxs-lookup"><span data-stu-id="b35ee-124">Shared device configuration settings for iOS</span></span>](shared-device-settings-ios.md)
    - [<span data-ttu-id="b35ee-125">iOS 用 Intune のデバイス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="b35ee-125">Configure Intune for iOS device Single Sign-on</span></span>](sso-ios.md)
    - [<span data-ttu-id="b35ee-126">iOS 用 Web コンテンツ フィルター設定</span><span class="sxs-lookup"><span data-stu-id="b35ee-126">Web content filter settings for iOS</span></span>](web-content-filter-settings-ios.md)

8. <span data-ttu-id="b35ee-127">完了したら、**[プロファイルの作成]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b35ee-127">When you're done, go back to the **Create Profile** blade, and click **Create**.</span></span>

<span data-ttu-id="b35ee-128">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b35ee-128">The profile is created and appears on the profiles list blade.</span></span>
<span data-ttu-id="b35ee-129">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35ee-129">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>



