---
title: "Intune ポリシーによる Samsung KNOX 用アプリの許可/禁止"
titlesuffix: Azure portal
description: "カスタム プロファイルを作成して、Samsung KNOX Standard デバイス用のアプリを許可またはブロックします。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef1855d99694947604f2bc58c5d1d3fe558aabea
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a><span data-ttu-id="b63d3-103">Microsoft Intune でカスタム ポリシーを使用して Samsung KNOX Standard デバイス用のアプリを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="b63d3-103">Use custom policies to allow and block apps for Samsung KNOX Standard devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b63d3-104">次のいずれかを作成する Microsoft Intune のカスタム ポリシーを作成するには、このトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-104">Use the procedures in this topic to create a Microsoft Intune custom policy that creates one of the following:</span></span>

- <span data-ttu-id="b63d3-105">デバイスでの実行をブロックするアプリの一覧。</span><span class="sxs-lookup"><span data-stu-id="b63d3-105">A list of apps that are blocked from running on the device.</span></span> <span data-ttu-id="b63d3-106">この一覧のアプリは、ポリシー適用時に既にインストールされていた場合でも、実行をブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b63d3-106">Apps in this list are blocked from being run, even if they were already installed when the policy was applied.</span></span>
- <span data-ttu-id="b63d3-107">デバイスのユーザーが Google Play ストアからインストールできるアプリの一覧。</span><span class="sxs-lookup"><span data-stu-id="b63d3-107">A list of apps that users of the device are allowed to install from the Google Play store.</span></span> <span data-ttu-id="b63d3-108">一覧のアプリのみをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b63d3-108">Only the apps you list can be installed.</span></span> <span data-ttu-id="b63d3-109">他のアプリはストアからインストールできません。</span><span class="sxs-lookup"><span data-stu-id="b63d3-109">No other apps can be installed from the store.</span></span>

<span data-ttu-id="b63d3-110">これらの設定は、Samsung KNOX Standard を実行するデバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b63d3-110">These settings can only be used by devices that run Samsung KNOX Standard.</span></span>

## <a name="create-an-allowed-or-blocked-app-list"></a><span data-ttu-id="b63d3-111">許可されているアプリまたはブロックされているアプリの一覧の作成</span><span class="sxs-lookup"><span data-stu-id="b63d3-111">Create an allowed or blocked app list</span></span>

1. <span data-ttu-id="b63d3-112">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b63d3-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b63d3-113">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="b63d3-114">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-114">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="b63d3-115">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-115">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="b63d3-116">プロファイルの一覧ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-116">In the list of profiles blade, choose **Create Profile**.</span></span>
3. <span data-ttu-id="b63d3-117">**[プロファイルを作成します]** ブレードで、デバイス プロファイルの**名前**と省略可能な**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-117">On the **Create Profile** blade, enter a **Name** and optional **Description** for this device profile.</span></span>
2. <span data-ttu-id="b63d3-118">**[プラットフォームの種類]** では **[Android]** を、[プロファイルの種類] では **[カスタム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-118">Choose a **Platform type** of **Android**, and a Profile type of **Custom**.</span></span>
3. <span data-ttu-id="b63d3-119">**[設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b63d3-119">Click **Settings**.</span></span>
3. <span data-ttu-id="b63d3-120">**[OMA-URI のカスタム設定]** ブレードで、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-120">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
4. <span data-ttu-id="b63d3-121">**[OMA-URI 設定の追加または編集]** ダイアログ ボックスで、以下を指定します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-121">In the **Add or Edit OMA-URI Setting** dialog box, specify the following:</span></span>

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a><span data-ttu-id="b63d3-122">デバイスでの実行がブロックされているアプリの一覧の場合:</span><span class="sxs-lookup"><span data-stu-id="b63d3-122">For a list of apps that are blocked from running on the device:</span></span>

- <span data-ttu-id="b63d3-123">**[名前]** - 「**PreventStartPackages**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-123">**Name** - Enter **PreventStartPackages**.</span></span>
- <span data-ttu-id="b63d3-124">**[説明]** - "実行されないようにブロックされているアプリの一覧" のような説明 (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-124">**Description** - Enter an optional description like 'List of apps that are blocked from running.'</span></span>
-   <span data-ttu-id="b63d3-125">**[データ型]** - ドロップダウン リストで **[文字列]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-125">**Data type** - From the drop-down list, choose **String**.</span></span>
-   <span data-ttu-id="b63d3-126">**[OMA-URI]** - 「**./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**」と入力します</span><span class="sxs-lookup"><span data-stu-id="b63d3-126">**OMA-URI** - Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**</span></span>
-   <span data-ttu-id="b63d3-127">**[値]** - ブロックするアプリ パッケージ名の一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-127">**Value** - Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="b63d3-128">区切り記号としては、**; : ,** **|** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b63d3-128">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="b63d3-129">(例: package1;package2;)</span><span class="sxs-lookup"><span data-stu-id="b63d3-129">(Example: package1;package2;)</span></span>

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a><span data-ttu-id="b63d3-130">他のすべてのアプリの実行中にユーザーが Google Play ストアからインストールできるアプリの一覧の場合:</span><span class="sxs-lookup"><span data-stu-id="b63d3-130">For a list of apps that users are allowed to install from the Google Play store while excluding all other apps:</span></span>
- <span data-ttu-id="b63d3-131">**[名前]** - 「**AllowInstallPackages**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-131">**Name** - Enter **AllowInstallPackages**.</span></span>
- <span data-ttu-id="b63d3-132">**[説明]**: "ユーザーが Google Play からインストールできるアプリの一覧" のような説明 (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-132">**Description** - Enter an optional description like 'List of apps that users can install from Google Play.'</span></span>
- <span data-ttu-id="b63d3-133">**[データ型]** - ドロップダウン リストで **[文字列]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-133">**Data type** - From the drop-down list, choose **String**.</span></span>
- <span data-ttu-id="b63d3-134">**[OMA-URI]** - 「**./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**」と入力します</span><span class="sxs-lookup"><span data-stu-id="b63d3-134">**OMA-URI** - Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**</span></span>
- <span data-ttu-id="b63d3-135">**[値]** - 許可するアプリ パッケージ名の一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-135">**Value** - Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="b63d3-136">区切り記号としては、**; : ,** **|** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b63d3-136">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="b63d3-137">(例: package1;package2;)</span><span class="sxs-lookup"><span data-stu-id="b63d3-137">(Example: package1;package2;)</span></span>

4. <span data-ttu-id="b63d3-138">**[OK]** をクリックし、**[プロファイルを作成します]** ブレードで **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b63d3-138">Click **OK**, and then, on the **Create Profile** blade, choose **Create**.</span></span>

>[!TIP]
> <span data-ttu-id="b63d3-139">Google Play ストアでアプリを参照して、アプリのパッケージ ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b63d3-139">You can find the package ID of an app by browsing to the app on the Google Play store.</span></span> <span data-ttu-id="b63d3-140">パッケージ ID は、アプリのページの URL に含まれます。</span><span class="sxs-lookup"><span data-stu-id="b63d3-140">The package ID is contained in the URL of the app's page.</span></span> <span data-ttu-id="b63d3-141">たとえば、Microsoft Word アプリのパッケージ ID は **com.microsoft.office.word** です。</span><span class="sxs-lookup"><span data-stu-id="b63d3-141">For example, the package ID of the Microsoft Word app is **com.microsoft.office.word**.</span></span>

<span data-ttu-id="b63d3-142">各対象デバイスの次のチェックイン時に、アプリの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b63d3-142">The next time each targeted device checks in, the app settings will be applied.</span></span>


<!---## Assign the custom profile--->
