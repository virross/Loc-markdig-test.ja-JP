---
title: "Pulse Secure を使用した Android のアプリごとの VPN"
description: "Intune で管理する、アプリごとの VPN プロファイルを Android デバイスに作成できます。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 283818c9e83d123d336ef7ad99c6225f4f783d7e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-a-custom-policy-to-create-a-per-app-vpn-profile-for-android-devices"></a><span data-ttu-id="09fb0-103">カスタム ポリシーを使用して、Android デバイスにアプリごとの VPN プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="09fb0-103">Use a custom policy to create a per-app VPN profile for Android devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="09fb0-104">Intune で管理する、アプリごとの VPN プロファイルを Android 5.0 以降のデバイスに作成できます。</span><span class="sxs-lookup"><span data-stu-id="09fb0-104">You can create a per-app VPN profile for Android 5.0 and later devices that are managed by Intune.</span></span> <span data-ttu-id="09fb0-105">最初に、Pulse Secure または Citrix 接続の種類を使用する VPN プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-105">First, create a VPN profile that uses the Pulse Secure or Citrix connection type.</span></span> <span data-ttu-id="09fb0-106">次に、特定のアプリと VPN プロファイルを関連付けるカスタム構成ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-106">Then, create a custom configuration policy that associates the VPN profile with specific apps.</span></span> 

<span data-ttu-id="09fb0-107">Android デバイスまたはユーザー グループにポリシーをデプロイした後、ユーザーは Pulse Secure または Citrix VPN を開始します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-107">After you deploy the policy to your Android device or user groups, users should start the Pulse Secure or Citrix VPN.</span></span> <span data-ttu-id="09fb0-108">この接続は、特定のアプリからのトラフィックのみに OpenVPN 接続の使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-108">The connection will then allow traffic only from the specified apps to use the open VPN connection.</span></span>

> [!NOTE]
>
> <span data-ttu-id="09fb0-109">このプロファイルに対しては Pulse Secure 接続タイプと Citrix 接続タイプのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="09fb0-109">Only the Pulse Secure and Citrix connection types are supported for this profile.</span></span>


### <a name="step-1-create-a-vpn-profile"></a><span data-ttu-id="09fb0-110">手順 1: VPN プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="09fb0-110">Step 1: Create a VPN profile</span></span>

1. <span data-ttu-id="09fb0-111">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]**  >  **[ポリシーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-111">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Add Policy**.</span></span>
2. <span data-ttu-id="09fb0-112">新しいポリシー用のテンプレートを選ぶには、**[Android]** を展開し、**[VPN プロファイル (Android 4 以降)]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="09fb0-112">To select a template for the new policy, expand **Android**, and then choose **VPN Profile (Android 4 and later)**.</span></span>
3. <span data-ttu-id="09fb0-113">テンプレートの **[接続の種類]** に **[Pulse Secure]** または **[Citrix]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-113">In the template, for **Connection type**, choose **Pulse Secure** or **Citrix**.</span></span>
4. <span data-ttu-id="09fb0-114">VPN プロファイルの作成を終了して保存します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-114">Finish and save the VPN profile.</span></span> <span data-ttu-id="09fb0-115">VPN プロファイルの詳細については、「[VPN 接続](../deploy-use/vpn-connections-in-microsoft-intune.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09fb0-115">For more details about VPN profiles, see [VPN connections](../deploy-use/vpn-connections-in-microsoft-intune.md).</span></span>

> [!NOTE]
>
> <span data-ttu-id="09fb0-116">VPN プロファイルの作成時に指定した**VPN 接続名 (ユーザーに表示される)** の値を書き留めてください。</span><span class="sxs-lookup"><span data-stu-id="09fb0-116">Take note of the **VPN Connection name (displayed to users):** value you specify when creating the VPN profile.</span></span> <span data-ttu-id="09fb0-117">これは次の手順で必要になります。</span><span class="sxs-lookup"><span data-stu-id="09fb0-117">This will be needed in the next step.</span></span> <span data-ttu-id="09fb0-118">たとえば、**MyAppVpnProfile** です。</span><span class="sxs-lookup"><span data-stu-id="09fb0-118">For example, **MyAppVpnProfile**.</span></span>

### <a name="step-2-create-a-custom-configuration-policy"></a><span data-ttu-id="09fb0-119">手順 2: カスタム構成ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="09fb0-119">Step 2: Create a custom configuration policy</span></span>

   1. <span data-ttu-id="09fb0-120">Intune 管理コンソールで、**[ポリシー]** > **[ポリシーの追加]** > **[Android]** > **[カスタム構成]** > **[ポリシーの作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-120">In the Intune admin console, choose **Policy** > **Add Policy** > **Android** > **Custom configuration** > **Create Policy**.</span></span>
   2. <span data-ttu-id="09fb0-121">ポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-121">Enter a name for the policy.</span></span>
   3. <span data-ttu-id="09fb0-122">**[OMA-URI 設定]**で **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-122">Under **OMA-URI settings**, choose **Add**.</span></span>
   4. <span data-ttu-id="09fb0-123">設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-123">Enter a setting name.</span></span>
   5. <span data-ttu-id="09fb0-124">**[データ型]** に **[文字列]** を指定します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-124">For **Data type**, specify **String**.</span></span>
   6. <span data-ttu-id="09fb0-125">**OMA-URI**、この文字列を指定: **./Vendor/MSFT/VPN/Profile/*名前*/PackageList**ここで、*名前*は、VPN プロファイル名手順 1. で説明します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-125">For **OMA-URI**, specify this string: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="09fb0-126">この例では、文字列は **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList** になります。</span><span class="sxs-lookup"><span data-stu-id="09fb0-126">In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.</span></span>
   7.   <span data-ttu-id="09fb0-127">**[値]** には、プロファイルと関連付けるセミコロンで区切られたパッケージの一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-127">For **Value**, create a semicolon-separated list of packages to associate with the profile.</span></span> <span data-ttu-id="09fb0-128">たとえば、Excel と Google Chrome ブラウザーで VPN 接続を使用するには、「**com.microsoft.office.excel;com.android.chrome**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-128">For example, if you want Excel and the Google Chrome browser to use the VPN connection, enter **com.microsoft.office.excel;com.android.chrome**.</span></span>

![Android のアプリごとの VPN カスタム ポリシーの例](./media/android_per_app_vpn_oma_uri.png)

#### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a><span data-ttu-id="09fb0-130">アプリの一覧をブラックリストまたはホワイトリストとして設定する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="09fb0-130">Set your app list to blacklist or whitelist (optional)</span></span>
  <span data-ttu-id="09fb0-131">**BLACKLIST** 値を使用すると、VPN 接続を使用*できない*アプリの一覧を指定できます。</span><span class="sxs-lookup"><span data-stu-id="09fb0-131">You can specify a list of apps that *cannot* use the VPN connection by using the **BLACKLIST** value.</span></span> <span data-ttu-id="09fb0-132">他のすべてのアプリは、VPN を使用して接続されます。</span><span class="sxs-lookup"><span data-stu-id="09fb0-132">All other apps will connect through the VPN.</span></span>
<span data-ttu-id="09fb0-133">または、**WHITELIST** 値を使用して、VPN 接続を使用*できる*アプリの一覧を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="09fb0-133">Alternatively, you can use the **WHITELIST** value to specify a list of apps that *can* use the VPN connection.</span></span> <span data-ttu-id="09fb0-134">一覧に含まれないアプリは、VPN 経由で接続しません。</span><span class="sxs-lookup"><span data-stu-id="09fb0-134">Apps that are not on the list will not connect through the VPN.</span></span>
  1.    <span data-ttu-id="09fb0-135">**[OMA-URI 設定]**で **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-135">Under **OMA-URI** settings, choose **Add**.</span></span>
  2.    <span data-ttu-id="09fb0-136">設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-136">Enter a setting name.</span></span>
  3.    <span data-ttu-id="09fb0-137">**[データ型]** に **[文字列]** を指定します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-137">For **Data type**, specify **String**.</span></span>
  4.    <span data-ttu-id="09fb0-138">**OMA-URI**、この文字列を使用して: **./Vendor/MSFT/VPN/Profile/*名前*/Mode**ここで、*名前*手順でメモした VPN プロファイル名を指定1。</span><span class="sxs-lookup"><span data-stu-id="09fb0-138">For **OMA-URI**, use this string: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="09fb0-139">この例では、文字列は **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode** になります。</span><span class="sxs-lookup"><span data-stu-id="09fb0-139">In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.</span></span>
  5.    <span data-ttu-id="09fb0-140">**[値]** には、「**BLACKLIST**」または「**WHITELIST**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-140">For **Value**, enter **BLACKLIST** or **WHITELIST**.</span></span>



### <a name="step-3-deploy-both-policies"></a><span data-ttu-id="09fb0-141">手順 3: 両方のポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="09fb0-141">Step 3: Deploy both policies</span></span>

<span data-ttu-id="09fb0-142">*両方*のポリシーは、*同じ* Intune グループに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09fb0-142">You must deploy *both* policies to the *same* Intune groups.</span></span>

1.  <span data-ttu-id="09fb0-143">**[ポリシー]** ワークスペースで、展開するポリシーを選び、**[展開の管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="09fb0-143">In the **Policy** workspace, select the policy that you want to deploy, and then choose **Manage Deployment**.</span></span>
2.  <span data-ttu-id="09fb0-144">**[展開の管理]** ダイアログ ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-144">In the **Manage Deployment** dialog box:</span></span>
    -   <span data-ttu-id="09fb0-145">**ポリシーを展開するには**、ポリシーを展開する 1 つ以上のグループを選択して、**[追加]** > **[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-145">**To deploy the policy**, select one or more groups to deploy the policy to, then choose **Add** > **OK**.</span></span>
    -   <span data-ttu-id="09fb0-146">**ポリシーを展開せずにダイアログ ボックスを閉じるには**、**[キャンセル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="09fb0-146">**To close the dialog box without deploying the policy**, choose **Cancel**.</span></span>

<span data-ttu-id="09fb0-147">**[ポリシー]** ワークスペースの **[概要]** ページに表示されるステータスの概要とアラートを見ると、注意が必要なポリシーの問題を識別できます。</span><span class="sxs-lookup"><span data-stu-id="09fb0-147">A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention.</span></span> <span data-ttu-id="09fb0-148">ステータスの概要は **[ダッシュボード]** ワークスペースにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="09fb0-148">A status summary also appears in the **Dashboard** workspace.</span></span>
