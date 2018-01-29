---
title: "Android - Pulse Secure 用のアプリ別の VPN プロファイル"
titlesuffix: Azure portal
description: "Intune で管理する Android デバイス用にアプリごとの VPN プロファイルを作成する方法について説明します。\""
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
ms.openlocfilehash: 4151280509f225a4434d5813ac0405653b8929b6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a><span data-ttu-id="8b7cf-103">Microsoft Intune のカスタム プロファイルを使って、Android デバイス用にアプリごとの VPN プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="8b7cf-103">Use a Microsoft Intune custom profile to create a per-app VPN profile for Android devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="8b7cf-104">Intune で管理する、アプリごとの VPN プロファイルを Android 5.0 以降のデバイスに作成できます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-104">You can create a per-app VPN profile for Android 5.0 and later devices that are managed by Intune.</span></span> <span data-ttu-id="8b7cf-105">最初に、Pulse Secure 接続の種類を使用する VPN プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-105">First, create a VPN profile that uses the Pulse Secure connection type.</span></span> <span data-ttu-id="8b7cf-106">次に、特定のアプリと VPN プロファイルを関連付けるカスタム構成ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-106">Then, create a custom configuration policy that associates the VPN profile with specific apps.</span></span>

<span data-ttu-id="8b7cf-107">Android デバイスまたはユーザー グループにポリシーを割り当てた後、ユーザーは PulseSecure VPN を開始します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-107">After you assign the policy to your Android device or user groups, users should start the PulseSecure VPN.</span></span> <span data-ttu-id="8b7cf-108">その後 PulseSecure は、指定されたアプリからのトラフィックのみに OpenVPN 接続の使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-108">PulseSecure then allows only traffic from the specified apps to use the open VPN connection.</span></span>

> [!NOTE]
>
> <span data-ttu-id="8b7cf-109">このプロファイルに対しては Pulse Secure 接続タイプのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-109">Only the Pulse Secure connection type is supported for this profile.</span></span>


## <a name="step-1-create-a-vpn-profile"></a><span data-ttu-id="8b7cf-110">手順 1: VPN プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="8b7cf-110">Step 1: Create a VPN profile</span></span>


1. <span data-ttu-id="8b7cf-111">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-111">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="8b7cf-112">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-112">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="8b7cf-113">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-113">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="8b7cf-114">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-114">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="8b7cf-115">プロファイルの一覧ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-115">On the list of profiles blade, choose **Create Profile**.</span></span>
3. <span data-ttu-id="8b7cf-116">**[プロファイルを作成します]** ブレードで、VPN プロファイルの**名前**と省略可能な**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-116">On the **Create Profile** blade, enter a **Name** and optional **Description** for the VPN profile.</span></span>
4. <span data-ttu-id="8b7cf-117">**[プラットフォーム]** ドロップダウン リストで、**[Android]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-117">From the **Platform** drop-down list, choose **Android**.</span></span>
5. <span data-ttu-id="8b7cf-118">**[プロファイルの種類]** ドロップダウン リストで、**[VPN]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-118">From the **Profile type** drop-down list, choose **VPN**.</span></span>
3. <span data-ttu-id="8b7cf-119">**[設定]** > **[構成]** の順に選択し、[VPN 設定を構成する方法](vpn-settings-configure.md)に関する記事および [Android デバイス用の Intune VPN 設定](vpn-settings-android.md)に関する記事の設定に従って VPN プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-119">Choose **Settings** > **Configure** and then configure the VPN profile as per the settings in [How to configure VPN settings](vpn-settings-configure.md) and [Intune VPN settings for Android devices](vpn-settings-android.md).</span></span>

<span data-ttu-id="8b7cf-120">VPN プロファイルの作成時に指定した**接続名**の値を書き留めてください。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-120">Take note of the **Connection Name** value you specify when creating the VPN profile.</span></span> <span data-ttu-id="8b7cf-121">この名前は次の手順で必要になります。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-121">This name will be needed in the next step.</span></span> <span data-ttu-id="8b7cf-122">たとえば、**MyAppVpnProfile** です。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-122">For example, **MyAppVpnProfile**.</span></span>

## <a name="step-2-create-a-custom-configuration-policy"></a><span data-ttu-id="8b7cf-123">手順 2: カスタム構成ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8b7cf-123">Step 2: Create a custom configuration policy</span></span>

1. <span data-ttu-id="8b7cf-124">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-124">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="8b7cf-125">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-125">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="8b7cf-126">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-126">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="8b7cf-127">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-127">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="8b7cf-128">[プロファイル] ブレードで、**[プロファイルを作成します]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-128">On the profiles blade, click **Create Profile**.</span></span>
4. <span data-ttu-id="8b7cf-129">**[プロファイルを作成します]** ブレードで、カスタム プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-129">On the **Create Profile** blade, enter a **Name** and **Description** for the custom profile.</span></span>
5. <span data-ttu-id="8b7cf-130">**[プラットフォーム]** ドロップダウン リストで、**[Android]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-130">From the **Platform** drop-down list, choose **Android**.</span></span>
6. <span data-ttu-id="8b7cf-131">**[プロファイルの種類]** ドロップダウン リストで、**[カスタム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-131">From the **Profile type** drop-down list, choose **Custom**.</span></span>
7. <span data-ttu-id="8b7cf-132">**[設定]** > **[構成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-132">Choose **Settings** > **Configure**.</span></span>
3. <span data-ttu-id="8b7cf-133">**[OMA-URI のカスタム設定]** ブレードで、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-133">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
    - <span data-ttu-id="8b7cf-134">設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-134">Enter a setting name.</span></span>
    - <span data-ttu-id="8b7cf-135">**[データ型]** に **[文字列]** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-135">For **Data type**, specify **String**.</span></span>
    - <span data-ttu-id="8b7cf-136">**OMA-URI**、この文字列を指定: **./Vendor/MSFT/VPN/Profile/*名前*/PackageList**ここで、*名前*は、VPN プロファイル名手順 1. で説明します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-136">For **OMA-URI**, specify this string: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="8b7cf-137">この例では、文字列は **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList** になります。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-137">In this example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.</span></span>
    - <span data-ttu-id="8b7cf-138">**[値]** には、プロファイルと関連付けるセミコロンで区切られたパッケージの一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-138">For **Value**, create a semicolon-separated list of packages to associate with the profile.</span></span> <span data-ttu-id="8b7cf-139">たとえば、Excel と Google Chrome ブラウザーで VPN 接続を使用するには、「**com.microsoft.office.excel;com.android.chrome**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-139">For example, if you want Excel and the Google Chrome browser to use the VPN connection, enter **com.microsoft.office.excel;com.android.chrome**.</span></span>

![Android のアプリごとの VPN カスタム ポリシーの例](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a><span data-ttu-id="8b7cf-141">アプリの一覧をブラックリストまたはホワイトリストとして設定する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="8b7cf-141">Set your app list to blacklist or whitelist (optional)</span></span>
  <span data-ttu-id="8b7cf-142">**BLACKLIST** 値を使用すると、VPN 接続を使用*できない*アプリの一覧を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-142">You can specify a list of apps that *cannot* use the VPN connection by using the **BLACKLIST** value.</span></span> <span data-ttu-id="8b7cf-143">その他のすべてのアプリは、VPN 経由で接続します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-143">All other apps connect through the VPN.</span></span>
<span data-ttu-id="8b7cf-144">または、**WHITELIST** 値を使用して、VPN 接続を使用*できる*アプリの一覧を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-144">Alternatively, you can use the **WHITELIST** value to specify a list of apps that *can* use the VPN connection.</span></span> <span data-ttu-id="8b7cf-145">一覧に含まれないアプリは、VPN 経由で接続しません。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-145">Apps that are not on the list do not connect through the VPN.</span></span>
  1.    <span data-ttu-id="8b7cf-146">**[OMA-URI のカスタム設定]** ブレードで、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-146">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
  2.    <span data-ttu-id="8b7cf-147">設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-147">Enter a setting name.</span></span>
  3.    <span data-ttu-id="8b7cf-148">**[データ型]** に **[文字列]** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-148">For **Data type**, specify **String**.</span></span>
  4.    <span data-ttu-id="8b7cf-149">**OMA-URI**、この文字列を使用して: **./Vendor/MSFT/VPN/Profile/*名前*/Mode**ここで、*名前*手順でメモした VPN プロファイル名を指定1。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-149">For **OMA-URI**, use this string: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="8b7cf-150">この例では、文字列は **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode** になります。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-150">In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.</span></span>
  5.    <span data-ttu-id="8b7cf-151">**[値]** には、「**BLACKLIST**」または「**WHITELIST**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-151">For **Value**, enter **BLACKLIST** or **WHITELIST**.</span></span>



## <a name="step-3-assign-both-policies"></a><span data-ttu-id="8b7cf-152">手順 3: 両方のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8b7cf-152">Step 3: Assign both policies</span></span>

<span data-ttu-id="8b7cf-153">[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事の指示に従って、必要なユーザーまたはデバイスに両方のプロファイルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-153">Use the instructions in [How to assign device profiles](device-profile-assign.md) to assign both profiles to the required users or devices.</span></span>
