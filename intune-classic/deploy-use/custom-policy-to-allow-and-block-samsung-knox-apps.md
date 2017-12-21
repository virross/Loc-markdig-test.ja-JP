---
title: "KNOX が許可するアプリとブロックするアプリ"
description: "KNOX が許可するアプリとブロックするアプリの一覧を作成するためのカスタム プロファイル。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cf5953aa59dca5247eef7d49b8f17b26a745ce69
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a><span data-ttu-id="4cccb-103">カスタム ポリシーを使用して、Samsung KNOX Standard デバイス用のアプリを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="4cccb-103">Use custom policies to allow and block apps for Samsung KNOX Standard devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4cccb-104">次のいずれかを作成する Microsoft Intune のカスタム ポリシーを作成するには、このトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-104">Use the procedures in this topic to create a Microsoft Intune custom policy that creates one of the following:</span></span>

- <span data-ttu-id="4cccb-105">デバイスでの実行をブロックするアプリの一覧。</span><span class="sxs-lookup"><span data-stu-id="4cccb-105">A list of apps that are blocked from running on the device.</span></span> <span data-ttu-id="4cccb-106">この一覧のアプリは、ポリシー適用時に既にインストールされていた場合でも、実行をブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-106">Apps in this list are blocked from being run, even if they were already installed when the policy was applied.</span></span>
- <span data-ttu-id="4cccb-107">デバイスのユーザーが Google Play ストアからインストールできるアプリの一覧。</span><span class="sxs-lookup"><span data-stu-id="4cccb-107">A list of apps that users of the device are allowed to install from the Google Play store.</span></span> <span data-ttu-id="4cccb-108">一覧のアプリのみをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-108">Only the apps you list can be installed.</span></span> <span data-ttu-id="4cccb-109">他のアプリはストアからインストールできません。</span><span class="sxs-lookup"><span data-stu-id="4cccb-109">No other apps can be installed from the store.</span></span>

<span data-ttu-id="4cccb-110">これらの設定は、Samsung KNOX Standard を実行するデバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-110">These settings can only be used by devices that run Samsung KNOX Standard.</span></span>

## <a name="to-create-an-allowed-or-blocked-app-list"></a><span data-ttu-id="4cccb-111">許可するアプリ一覧またはブロックするアプリ一覧を作成するには</span><span class="sxs-lookup"><span data-stu-id="4cccb-111">To create an allowed or blocked app list</span></span>

1. <span data-ttu-id="4cccb-112">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[ポリシー]、** &gt; **[構成ポリシー]** &gt; **[追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-112">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Policy** &gt; **Configuration Policies** &gt; **Add**.</span></span>
2. <span data-ttu-id="4cccb-113">**[新しいポリシーの作成]** ダイアログ ボックスで、**[Android]** を展開し、**[カスタム構成]** を選んで、**[ポリシーを作成する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-113">In the **Create a New Policy** dialog box, expand **Android**, choose **Custom Configuration**, and then choose **Create Policy**.</span></span>
3. <span data-ttu-id="4cccb-114">ポリシーの名前と説明 (オプション) を指定し、**[OMA-URI 設定]** セクションで **[追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-114">Provide a name and optional description for the policy and then, in the **OMA-URI Settings** section, choose **Add**.</span></span>
4. <span data-ttu-id="4cccb-115">**[OMA-URI 設定の追加または編集]** ダイアログ ボックスで以下を指定します。デバイスでの実行をブロックするアプリの一覧の場合:</span><span class="sxs-lookup"><span data-stu-id="4cccb-115">In the **Add or Edit OMA-URI Setting** dialog box, specify the following:  For a list of apps that are blocked from running on the device:</span></span>
    
    - <span data-ttu-id="4cccb-116">**設定の名前。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-116">**Setting name.**</span></span> <span data-ttu-id="4cccb-117">「**PreventStartPackages**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-117">Enter **PreventStartPackages**.</span></span>
    - <span data-ttu-id="4cccb-118">**設定の説明。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-118">**Setting description.**</span></span> <span data-ttu-id="4cccb-119">"実行をブロックするアプリの一覧" のようなオプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-119">Enter an optional description like 'List of apps that are blocked from running.'</span></span>
    -   <span data-ttu-id="4cccb-120">**データ型。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-120">**Data type.**</span></span> <span data-ttu-id="4cccb-121">ドロップダウン リストで **[文字列]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-121">From the drop-down list, choose **String**.</span></span>
    -   <span data-ttu-id="4cccb-122">**OMA-URI。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-122">**OMA-URI.**</span></span> <span data-ttu-id="4cccb-123">「**./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-123">Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**</span></span>
    -   <span data-ttu-id="4cccb-124">**値。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-124">**Value.**</span></span> <span data-ttu-id="4cccb-125">ブロックするアプリ パッケージ名の一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-125">Enter a list of the app package names you want to block.</span></span> <span data-ttu-id="4cccb-126">区切り記号としては、**; : ,** **|** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-126">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="4cccb-127">(例: package1;package2;)</span><span class="sxs-lookup"><span data-stu-id="4cccb-127">(Example: package1;package2;)</span></span>

    <span data-ttu-id="4cccb-128">他のすべてのアプリの実行中にユーザーが Google Play ストアからインストールできるアプリの一覧の場合:</span><span class="sxs-lookup"><span data-stu-id="4cccb-128">For a list of apps that users are allowed to install from the Google Play store while excluding all other apps:</span></span>

    - <span data-ttu-id="4cccb-129">**設定の名前。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-129">**Setting name.**</span></span> <span data-ttu-id="4cccb-130">「**AllowInstallPackages**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-130">Enter **AllowInstallPackages**.</span></span>
    - <span data-ttu-id="4cccb-131">**設定の説明。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-131">**Setting description.**</span></span> <span data-ttu-id="4cccb-132">"ユーザーが Google Play からインストールできるアプリの一覧" といったオプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-132">Enter an optional description like 'List of apps that users can install from Google Play.'</span></span>
    - <span data-ttu-id="4cccb-133">**データ型。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-133">**Data type.**</span></span> <span data-ttu-id="4cccb-134">ドロップダウン リストで **[文字列]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-134">From the drop-down list, choose **String**.</span></span>
    - <span data-ttu-id="4cccb-135">**OMA-URI。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-135">**OMA-URI.**</span></span> <span data-ttu-id="4cccb-136">「**./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-136">Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**</span></span>
    - <span data-ttu-id="4cccb-137">**値。**</span><span class="sxs-lookup"><span data-stu-id="4cccb-137">**Value.**</span></span> <span data-ttu-id="4cccb-138">ブロックするアプリ パッケージ名の一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="4cccb-138">Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="4cccb-139">区切り記号としては、**; : ,** **|** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-139">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="4cccb-140">(例: package1;package2;)</span><span class="sxs-lookup"><span data-stu-id="4cccb-140">(Example: package1;package2;)</span></span>

4. <span data-ttu-id="4cccb-141">**[OK]** をクリックし、**[ポリシーの保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cccb-141">Click **OK**, and then click **Save Policy**.</span></span> 

>[!TIP]
> <span data-ttu-id="4cccb-142">Google Play ストアでアプリを参照して、アプリのパッケージ ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-142">You can find the package ID of an app by browsing to the app on the Google Play store.</span></span> <span data-ttu-id="4cccb-143">パッケージ ID は、アプリのページの URL に含まれます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-143">The package ID is contained in the URL of the app's page.</span></span> <span data-ttu-id="4cccb-144">たとえば、Microsoft Word アプリのパッケージ ID は **com.microsoft.office.word** です。</span><span class="sxs-lookup"><span data-stu-id="4cccb-144">For example, the package ID of the Microsoft Word app is **com.microsoft.office.word**.</span></span>

<span data-ttu-id="4cccb-145">各対象デバイスの次のチェックイン時に、アプリの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-145">The next time each targeted device checks in, the app settings will be applied.</span></span>


## <a name="deploy-the-policy"></a><span data-ttu-id="4cccb-146">ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="4cccb-146">Deploy the policy</span></span>

1.  <span data-ttu-id="4cccb-147">**[ポリシー]** ワークスペースで、展開するポリシーを選択し、 **[展開の管理]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cccb-147">In the **Policy** workspace, select the policy you want to deploy, then click **Manage Deployment**.</span></span>

2.  <span data-ttu-id="4cccb-148">**[展開の管理]** ダイアログ ボックスで、ポリシーを展開するユーザー グループを 1 つまたは複数選び、**[追加]** &gt; **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cccb-148">In the **Manage Deployment** dialog box, select one or more groups to which you want to deploy the policy, then click **Add** &gt; **OK**.</span></span>

 
<span data-ttu-id="4cccb-149">展開済みポリシーを選択すると、ポリシー一覧の下部に展開についての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cccb-149">When you select a deployed policy, you can view further information about the deployment in the lower part of the policies list.</span></span>

### <a name="see-also"></a><span data-ttu-id="4cccb-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cccb-150">See also</span></span>
[<span data-ttu-id="4cccb-151">Microsoft Intune の Android および Samsung KNOX ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="4cccb-151">Android and Samsung KNOX policy settings in Microsoft Intune</span></span>](android-policy-settings-in-microsoft-intune.md)
