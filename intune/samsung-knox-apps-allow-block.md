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
ms.openlocfilehash: 2974ce27e2eeff66356d26f80b8844b42e6a83b1
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a><span data-ttu-id="16784-103">Microsoft Intune でカスタム ポリシーを使用して Samsung KNOX Standard デバイス用のアプリを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="16784-103">Use custom policies to allow and block apps for Samsung KNOX Standard devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="16784-104">次のいずれかを作成する Microsoft Intune のカスタム ポリシーを作成するには、このトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="16784-104">Use the procedures in this topic to create a Microsoft Intune custom policy that creates one of the following:</span></span>

- <span data-ttu-id="16784-105">デバイスでの実行をブロックするアプリの一覧。</span><span class="sxs-lookup"><span data-stu-id="16784-105">A list of apps that are blocked from running on the device.</span></span> <span data-ttu-id="16784-106">この一覧のアプリは、ポリシー適用時に既にインストールされていた場合でも、実行をブロックされます。</span><span class="sxs-lookup"><span data-stu-id="16784-106">Apps in this list are blocked from being run, even if they were already installed when the policy was applied.</span></span>
- <span data-ttu-id="16784-107">デバイスのユーザーが Google Play ストアからインストールできるアプリの一覧。</span><span class="sxs-lookup"><span data-stu-id="16784-107">A list of apps that users of the device are allowed to install from the Google Play store.</span></span> <span data-ttu-id="16784-108">一覧のアプリのみをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="16784-108">Only the apps you list can be installed.</span></span> <span data-ttu-id="16784-109">他のアプリはストアからインストールできません。</span><span class="sxs-lookup"><span data-stu-id="16784-109">No other apps can be installed from the store.</span></span>

<span data-ttu-id="16784-110">これらの設定は、Samsung KNOX Standard を実行するデバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="16784-110">These settings can only be used by devices that run Samsung KNOX Standard.</span></span>

## <a name="create-an-allowed-or-blocked-app-list"></a><span data-ttu-id="16784-111">許可されているアプリまたはブロックされているアプリの一覧の作成</span><span class="sxs-lookup"><span data-stu-id="16784-111">Create an allowed or blocked app list</span></span>

1. <span data-ttu-id="16784-112">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="16784-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="16784-113">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="16784-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="16784-114">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16784-114">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="16784-115">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="16784-115">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="16784-116">プロファイルの一覧ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16784-116">In the list of profiles blade, choose **Create Profile**.</span></span>
3. <span data-ttu-id="16784-117">**[プロファイルを作成します]** ブレードで、デバイス プロファイルの**名前**と省略可能な**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="16784-117">On the **Create Profile** blade, enter a **Name** and optional **Description** for this device profile.</span></span>
2. <span data-ttu-id="16784-118">**[プラットフォームの種類]** では **[Android]** を、[プロファイルの種類] では **[カスタム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16784-118">Choose a **Platform type** of **Android**, and a Profile type of **Custom**.</span></span>
3. <span data-ttu-id="16784-119">**[設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16784-119">Click **Settings**.</span></span>
3. <span data-ttu-id="16784-120">**[OMA-URI のカスタム設定]** ブレードで、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16784-120">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
4. <span data-ttu-id="16784-121">**[OMA-URI 設定の追加または編集]** ダイアログ ボックスで、以下を指定します。</span><span class="sxs-lookup"><span data-stu-id="16784-121">In the **Add or Edit OMA-URI Setting** dialog box, specify the following:</span></span>

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a><span data-ttu-id="16784-122">デバイスでの実行がブロックされているアプリの一覧の場合:</span><span class="sxs-lookup"><span data-stu-id="16784-122">For a list of apps that are blocked from running on the device:</span></span>

- <span data-ttu-id="16784-123">**[名前]** - 「**PreventStartPackages**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="16784-123">**Name** - Enter **PreventStartPackages**.</span></span>
- <span data-ttu-id="16784-124">**[説明]** - "実行されないようにブロックされているアプリの一覧" のような説明 (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="16784-124">**Description** - Enter an optional description like 'List of apps that are blocked from running.'</span></span>
-   <span data-ttu-id="16784-125">**[データ型]** - ドロップダウン リストで **[文字列]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16784-125">**Data type** - From the drop-down list, choose **String**.</span></span>
-   <span data-ttu-id="16784-126">**[OMA-URI]** - 「**./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**」と入力します</span><span class="sxs-lookup"><span data-stu-id="16784-126">**OMA-URI** - Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**</span></span>
-   <span data-ttu-id="16784-127">**[値]** - ブロックするアプリ パッケージ名の一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="16784-127">**Value** - Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="16784-128">区切り記号としては、**; : ,** **|** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="16784-128">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="16784-129">(例: package1;package2;)</span><span class="sxs-lookup"><span data-stu-id="16784-129">(Example: package1;package2;)</span></span>

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a><span data-ttu-id="16784-130">他のすべてのアプリの実行中にユーザーが Google Play ストアからインストールできるアプリの一覧の場合:</span><span class="sxs-lookup"><span data-stu-id="16784-130">For a list of apps that users are allowed to install from the Google Play store while excluding all other apps:</span></span>
- <span data-ttu-id="16784-131">**[名前]** - 「**AllowInstallPackages**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="16784-131">**Name** - Enter **AllowInstallPackages**.</span></span>
- <span data-ttu-id="16784-132">**[説明]**: "ユーザーが Google Play からインストールできるアプリの一覧" のような説明 (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="16784-132">**Description** - Enter an optional description like 'List of apps that users can install from Google Play.'</span></span>
- <span data-ttu-id="16784-133">**[データ型]** - ドロップダウン リストで **[文字列]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16784-133">**Data type** - From the drop-down list, choose **String**.</span></span>
- <span data-ttu-id="16784-134">**[OMA-URI]** - 「**./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**」と入力します</span><span class="sxs-lookup"><span data-stu-id="16784-134">**OMA-URI** - Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**</span></span>
- <span data-ttu-id="16784-135">**[値]** - 許可するアプリ パッケージ名の一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="16784-135">**Value** - Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="16784-136">区切り記号としては、**; : ,** **|** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="16784-136">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="16784-137">(例: package1;package2;)</span><span class="sxs-lookup"><span data-stu-id="16784-137">(Example: package1;package2;)</span></span>

4. <span data-ttu-id="16784-138">**[OK]** をクリックし、**[プロファイルを作成します]** ブレードで **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16784-138">Click **OK**, and then, on the **Create Profile** blade, choose **Create**.</span></span>

>[!TIP]
> <span data-ttu-id="16784-139">Google Play ストアでアプリを参照して、アプリのパッケージ ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="16784-139">You can find the package ID of an app by browsing to the app on the Google Play store.</span></span> <span data-ttu-id="16784-140">パッケージ ID は、アプリのページの URL に含まれます。</span><span class="sxs-lookup"><span data-stu-id="16784-140">The package ID is contained in the URL of the app's page.</span></span> <span data-ttu-id="16784-141">たとえば、Microsoft Word アプリのパッケージ ID は **com.microsoft.office.word** です。</span><span class="sxs-lookup"><span data-stu-id="16784-141">For example, the package ID of the Microsoft Word app is **com.microsoft.office.word**.</span></span>

<span data-ttu-id="16784-142">各対象デバイスの次のチェックイン時に、アプリの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="16784-142">The next time each targeted device checks in, the app settings will be applied.</span></span>


<!---## Assign the custom profile--->
