---
title: "Intune カスタム デバイス設定を構成する方法"
titleSuffix: Azure portal
description: "Intune を使用して管理対象デバイスのカスタム設定を構成する方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3b44cb606f0764fb655651a441889862fcbbe62
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a><span data-ttu-id="3db7c-103">Microsoft Intune でカスタム デバイス設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="3db7c-103">How to configure custom device settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a><span data-ttu-id="3db7c-104">カスタム設定を使用する状況</span><span class="sxs-lookup"><span data-stu-id="3db7c-104">When to use custom settings</span></span>

<span data-ttu-id="3db7c-105">カスタム デバイス設定は、構成する設定が Intune に組み込まれていない場合に便利で、他のデバイス プロファイルから利用できます。</span><span class="sxs-lookup"><span data-stu-id="3db7c-105">Custom device settings can be useful when Intune doesn't have the settings you want to configure built-in, and available from other device profiles.</span></span>
<span data-ttu-id="3db7c-106">カスタム設定は、プラットフォームごとに構成が異なります。</span><span class="sxs-lookup"><span data-stu-id="3db7c-106">Custom settings are configured differently for each platform.</span></span> <span data-ttu-id="3db7c-107">たとえば、Android および Windows デバイスでは、デバイスの機能を制御する Open Mobile Alliance Uniform Resource Identifier (OMA-URI) 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3db7c-107">For example, with Android and Windows devices, you can specify Open Mobile Alliance Uniform Resource Identifier (OMA-URI) values to control features on devices.</span></span> <span data-ttu-id="3db7c-108">Apple デバイスでは、[Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) で作成したファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="3db7c-108">For Apple devices, you can import a file you created with the [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).</span></span>

<span data-ttu-id="3db7c-109">このトピックでは、カスタム設定を含むプロファイルを構成する基本的な方法について説明します。その後、デバイスごとの詳細については、各プラットフォームのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3db7c-109">Use the information in this topic to learn the basics about configuring profiles with custom settings, and then read further topics for each platform to learn about device specifics.</span></span>

## <a name="create-a-device-profile-containing-custom-settings"></a><span data-ttu-id="3db7c-110">カスタム設定を含むデバイス プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="3db7c-110">Create a device profile containing custom settings</span></span>

1. <span data-ttu-id="3db7c-111">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3db7c-111">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="3db7c-112">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3db7c-112">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="3db7c-113">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3db7c-113">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="3db7c-114">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3db7c-114">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="3db7c-115">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3db7c-115">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="3db7c-116">**[プロファイルを作成します]** ブレードで、カスタム プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="3db7c-116">On the **Create Profile** blade, enter a **Name** and **Description** for the custom profile.</span></span>
5. <span data-ttu-id="3db7c-117">**[プラットフォーム]** ドロップダウン リストで、カスタム設定を適用するデバイス プラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="3db7c-117">From the **Platform** drop-down list, select the device platform to which you want to apply custom settings.</span></span> <span data-ttu-id="3db7c-118">現時点では、カスタム デバイス設定に対応している次のいずれかのプラットフォームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3db7c-118">Currently, you can choose one of the following platforms for custom device settings:</span></span>
    - <span data-ttu-id="3db7c-119">**Android**</span><span class="sxs-lookup"><span data-stu-id="3db7c-119">**Android**</span></span>
    - <span data-ttu-id="3db7c-120">**Android**</span><span class="sxs-lookup"><span data-stu-id="3db7c-120">**iOS**</span></span>
    - <span data-ttu-id="3db7c-121">**macOS**</span><span class="sxs-lookup"><span data-stu-id="3db7c-121">**macOS**</span></span>
    - <span data-ttu-id="3db7c-122">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="3db7c-122">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="3db7c-123">**Windows 10 以降**</span><span class="sxs-lookup"><span data-stu-id="3db7c-123">**Windows 10 and later**</span></span>
6. <span data-ttu-id="3db7c-124">**[プロファイルの種類]** ドロップダウン リストで、**[カスタム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3db7c-124">From the **Profile** type drop-down list, choose **Custom**.</span></span>
7. <span data-ttu-id="3db7c-125">選択したプラットフォームによって構成できる設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="3db7c-125">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="3db7c-126">各プラットフォームの詳細な設定については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3db7c-126">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="3db7c-127">Android の設定</span><span class="sxs-lookup"><span data-stu-id="3db7c-127">Android settings</span></span>](custom-settings-android.md)
    - [<span data-ttu-id="3db7c-128">iOS の設定</span><span class="sxs-lookup"><span data-stu-id="3db7c-128">iOS settings</span></span>](custom-settings-ios.md)
    - [<span data-ttu-id="3db7c-129">macOS の設定</span><span class="sxs-lookup"><span data-stu-id="3db7c-129">macOS settings</span></span>](custom-settings-macos.md)
    - [<span data-ttu-id="3db7c-130">Windows Phone 8.1 の設定</span><span class="sxs-lookup"><span data-stu-id="3db7c-130">Windows Phone 8.1 settings</span></span>](custom-settings-windows-phone-8-1.md)
    - [<span data-ttu-id="3db7c-131">Windows 10 の設定</span><span class="sxs-lookup"><span data-stu-id="3db7c-131">Windows 10 settings</span></span>](custom-settings-windows-10.md)
    - [<span data-ttu-id="3db7c-132">Android for Work の設定</span><span class="sxs-lookup"><span data-stu-id="3db7c-132">Android for Work settings</span></span>](custom-settings-android-for-work.md)
8. <span data-ttu-id="3db7c-133">完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3db7c-133">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="3db7c-134">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3db7c-134">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="3db7c-135">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3db7c-135">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>
