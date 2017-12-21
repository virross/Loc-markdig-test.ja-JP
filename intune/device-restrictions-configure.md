---
title: "Intune デバイス制限設定の構成"
titleSuffix: Azure portal
description: "Intune を使用して、管理対象デバイスの設定と機能を構成する方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0f51cb0ef85c772392458b8df328408657a84af8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="36088-103">Microsoft Intune でデバイスの制限設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="36088-103">How to configure device restriction settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="36088-104">デバイスの制限では、セキュリティ、ブラウザー、ハードウェア、データ共有設定を含む広範なカテゴリにわたって、管理対象のさまざまな設定と機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="36088-104">Device restrictions let you control a wide range of settings and features you manage across a range of categories including security, browser, hardware, and data sharing settings.</span></span> <span data-ttu-id="36088-105">たとえば、iOS デバイスのユーザーがデバイスのカメラにアクセスできないようにするデバイスの制限プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="36088-105">For example, you could create a device restriction profile that prevents users of iOS devices from accessing the device camera.</span></span>

<span data-ttu-id="36088-106">このトピックでは、デバイスの制限プロファイルを構成する基本的な方法について説明します。その後、デバイスごとの詳細については、各プラットフォームのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36088-106">Use the information in this topic to learn the basics about configuring device restriction profiles, and then read further topics for each platform to learn about device specifics.</span></span>

<span data-ttu-id="36088-107">デバイスの制限設定を含むデバイス プロファイルを作成するには:</span><span class="sxs-lookup"><span data-stu-id="36088-107">To create a device profile containing device restriction settings:</span></span>

1. <span data-ttu-id="36088-108">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="36088-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="36088-109">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36088-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="36088-110">**[Intune]** ブレードで、**[デバイスの構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36088-110">On the **Intune** blade, choose **Configure devices**.</span></span>
2. <span data-ttu-id="36088-111">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="36088-111">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="36088-112">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36088-112">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="36088-113">**[プロファイルを作成します]** ブレードで、デバイスの制限プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="36088-113">On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.</span></span>
5. <span data-ttu-id="36088-114">**[プラットフォーム]** ドロップダウン リストで、カスタム設定を適用するデバイス プラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="36088-114">From the **Platform** drop-down list, select the device platform to which you want to apply custom settings.</span></span> <span data-ttu-id="36088-115">現時点では、デバイスの制限設定に対応している次のいずれかのプラットフォームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="36088-115">Currently, you can choose one of the following platforms for device restriction settings:</span></span>
    - <span data-ttu-id="36088-116">**Android**</span><span class="sxs-lookup"><span data-stu-id="36088-116">**Android**</span></span>
    - <span data-ttu-id="36088-117">**iOS**</span><span class="sxs-lookup"><span data-stu-id="36088-117">**iOS**</span></span>
    - <span data-ttu-id="36088-118">**macOS**</span><span class="sxs-lookup"><span data-stu-id="36088-118">**macOS**</span></span>
    - <span data-ttu-id="36088-119">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="36088-119">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="36088-120">**Windows 8.1 以降**</span><span class="sxs-lookup"><span data-stu-id="36088-120">**Windows 8.1 and later**</span></span>
    - <span data-ttu-id="36088-121">**Windows 10 以降**</span><span class="sxs-lookup"><span data-stu-id="36088-121">**Windows 10 and later**</span></span>
6. <span data-ttu-id="36088-122">**[プロファイルの種類]** ドロップダウン リストで、**[デバイスの制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36088-122">From the **Profile type** type drop-down list, choose **Device restrictions**.</span></span> <span data-ttu-id="36088-123">Surface Hub などの Windows 10 Team デバイス用のデバイスの制限プロファイルを作成する場合は、**[デバイスの制限 (Windows 10 Team)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36088-123">If you want to create a device restrictions profile for Windows 10 Team devices like a Surface Hub, choose **Device restrictions (Windows 10 Team)**.</span></span>
7. <span data-ttu-id="36088-124">選択したプラットフォームによって構成できる設定が異なります。</span><span class="sxs-lookup"><span data-stu-id="36088-124">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="36088-125">各プラットフォームの詳細な設定については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36088-125">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="36088-126">Android の設定</span><span class="sxs-lookup"><span data-stu-id="36088-126">Android settings</span></span>](device-restrictions-android.md)
    - [<span data-ttu-id="36088-127">iOS の設定</span><span class="sxs-lookup"><span data-stu-id="36088-127">iOS settings</span></span>](device-restrictions-ios.md)
    - [<span data-ttu-id="36088-128">macOS の設定</span><span class="sxs-lookup"><span data-stu-id="36088-128">macOS settings</span></span>](device-restrictions-macos.md)
    - [<span data-ttu-id="36088-129">Windows Phone 8.1 の設定</span><span class="sxs-lookup"><span data-stu-id="36088-129">Windows Phone 8.1 settings</span></span>](device-restrictions-windows-phone-8-1.md)
    - [<span data-ttu-id="36088-130">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="36088-130">Windows 8.1</span></span>](device-restrictions-windows-8-1.md)
    - [<span data-ttu-id="36088-131">Windows 10 の設定</span><span class="sxs-lookup"><span data-stu-id="36088-131">Windows 10 settings</span></span>](device-restrictions-windows-10.md)
    - [<span data-ttu-id="36088-132">Windows 10 Team の設定</span><span class="sxs-lookup"><span data-stu-id="36088-132">Windows 10 Team settings</span></span>](device-restrictions-windows-10-teams.md)
    - [<span data-ttu-id="36088-133">Android for Work の設定</span><span class="sxs-lookup"><span data-stu-id="36088-133">Android for Work settings</span></span>](device-restrictions-android-for-work.md)
8. <span data-ttu-id="36088-134">完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36088-134">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="36088-135">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="36088-135">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="36088-136">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36088-136">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->