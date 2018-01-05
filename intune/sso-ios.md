---
title: "iOS 用 Intune のデバイス シングル サインオンを構成する"
titlesuffix: Azure portal
description: "iOS デバイスのシングル サインオン用に Intune を構成します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff71239a360b09ca831a6e99f5f7a759b08f5d56
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="configure-intune-for-ios-device-single-sign-on"></a><span data-ttu-id="50270-103">iOS 用 Intune のデバイス シングル サインオンを構成する</span><span class="sxs-lookup"><span data-stu-id="50270-103">Configure Intune for iOS device single sign-on</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="50270-104">ほとんどの基幹業務 (LOB) アプリでは、セキュリティに対応するために、何らかのレベルのユーザー認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="50270-104">Most Line of Business (LOB) apps require some level of user authentication to support security.</span></span> <span data-ttu-id="50270-105">多くの場合、ユーザーはそのために同じ資格情報を何回も入力する必要があり、ストレスを感じることがあります。</span><span class="sxs-lookup"><span data-stu-id="50270-105">In many cases this requires the user to type the same credentials multiple times, which can be frustrating for users.</span></span> <span data-ttu-id="50270-106">ユーザーの操作環境を改善するため、開発者はシングル サインオンを使うアプリを作成し、ユーザーが資格情報を入力する必要のある回数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="50270-106">To improve the user experience, developers can create apps that use single sign-on, reducing the number of times a user must provide credentials.</span></span>

<span data-ttu-id="50270-107">iOS デバイスのシングル サインオンを利用するには、次の条件が満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50270-107">To take advantage of iOS device Single Sign-on, you must have the following conditions:</span></span>

- <span data-ttu-id="50270-108">iOS デバイス上のシングル サインオン ペイロードでユーザー資格情報ストアを探すようにアプリがコーディングされていること。</span><span class="sxs-lookup"><span data-stu-id="50270-108">An app coded to look for the user credential store in the single sign-on payload on the iOS device.</span></span>
- <span data-ttu-id="50270-109">iOS デバイスのシングル サインオン用に Intune が構成されていること。</span><span class="sxs-lookup"><span data-stu-id="50270-109">Intune configured for iOS device single sign-on.</span></span>

## <a name="to-configure-intune-for-ios-device-single-sign-on"></a><span data-ttu-id="50270-110">iOS デバイスのシングル サインオン用に Intune を構成するには</span><span class="sxs-lookup"><span data-stu-id="50270-110">To configure Intune for iOS device single sign-on</span></span>


1. <span data-ttu-id="50270-111">サインイン、 [Azure ポータル](https://portal.azure.com)します。</span><span class="sxs-lookup"><span data-stu-id="50270-111">Sign into the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="50270-112">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="50270-112">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="50270-113">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50270-113">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="50270-114">**[デバイス構成]** ブレードで、**[プロファイル]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="50270-114">On the **Device configuration** blade, choose **Profiles**.</span></span>
3. <span data-ttu-id="50270-115">プロファイル ブレードで **[プロファイルの作成]** を選び、名前と説明を指定して、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="50270-115">On the profiles blade, choose **Create Profile**, provide a name and description, and configure the following settings:</span></span>
   - <span data-ttu-id="50270-116">**[プラットフォーム]**: **[iOS]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="50270-116">**Platform**: Choose **iOS**.</span></span> 
   - <span data-ttu-id="50270-117">**[プロファイルの種類]**: **[デバイス機能]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="50270-117">**Profile type**: Choose **Device features**.</span></span>
4. <span data-ttu-id="50270-118">**[デバイス機能]** ブレードで、**[シングル サインオン]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="50270-118">On the **Device features** blade, choose **Single Sign On**.</span></span>

   ![[シングル サインオン] ブレード](./media/sso-blade.png)

2. <span data-ttu-id="50270-120">次の表にまとめた情報を参考にして、**[シングル サインオン]** ブレードのフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="50270-120">Use the following summary table to help you fill in the fields on the **Single Sign On** blade.</span></span> <span data-ttu-id="50270-121">詳しくは、表の後の説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50270-121">For details, see the sections after the table.</span></span>
   
   |<span data-ttu-id="50270-122">フィールド</span><span class="sxs-lookup"><span data-stu-id="50270-122">Field</span></span>  |<span data-ttu-id="50270-123">注</span><span class="sxs-lookup"><span data-stu-id="50270-123">Notes</span></span>|
   |---------|---------|
   |<span data-ttu-id="50270-124">**AAD からのユーザー名の属性**</span><span class="sxs-lookup"><span data-stu-id="50270-124">**Username attribute from AAD**</span></span>|<span data-ttu-id="50270-125">デバイスにインストールされる XML ペイロードを生成する前に、Intune が AAD で各ユーザーについて調べて対応するフィールド (UPN など) に設定する属性です。</span><span class="sxs-lookup"><span data-stu-id="50270-125">The attribute that Intune looks at for each user in AAD and populates the respective field (such as UPN) before generating the XML payload that gets installed on the device.</span></span>|
   |<span data-ttu-id="50270-126">**領域**</span><span class="sxs-lookup"><span data-stu-id="50270-126">**Realm**</span></span>|<span data-ttu-id="50270-127">URL のドメイン部分です。</span><span class="sxs-lookup"><span data-stu-id="50270-127">The domain portion of the URL.</span></span>|
   |<span data-ttu-id="50270-128">**シングル サインオンを使用する URL プレフィックス**</span><span class="sxs-lookup"><span data-stu-id="50270-128">**URL prefixes that will use Single Sign On**</span></span>|<span data-ttu-id="50270-129">ユーザーのシングル サインオン認証を必要とする、組織内の URL です。</span><span class="sxs-lookup"><span data-stu-id="50270-129">Any URLs in your organization that require user single sign-on authentication</span></span>|
   |<span data-ttu-id="50270-130">**シングル サインオンを使用するアプリ**</span><span class="sxs-lookup"><span data-stu-id="50270-130">**Apps that will use Single Sign On**</span></span>|<span data-ttu-id="50270-131">シングル サインオン ペイロードを使用する、エンド ユーザーのデバイス上のアプリです。</span><span class="sxs-lookup"><span data-stu-id="50270-131">Apps on end user’s device that use the single sign-on payload.</span></span>|
   |<span data-ttu-id="50270-132">**資格情報更新証明書**</span><span class="sxs-lookup"><span data-stu-id="50270-132">**Credential renewal certificate**</span></span>|<span data-ttu-id="50270-133">認証に資格情報を使う場合は、認証証明書としてユーザーに展開される SCEP または PFX 証明書を選びます。</span><span class="sxs-lookup"><span data-stu-id="50270-133">If using certificates for authentication, select the SCEP or PFX certificate that is deployed to the user as the authentication certificate.</span></span>|

<span data-ttu-id="50270-134">以下のセクションでは、各シングル サインオン フィールドについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="50270-134">The following sections provide more details about each of the single sign-on fields.</span></span>

### <a name="username-attribute-from-aad-and-realm"></a><span data-ttu-id="50270-135">AAD からのユーザー名の属性と領域</span><span class="sxs-lookup"><span data-stu-id="50270-135">Username attribute from AAD and Realm</span></span>

- <span data-ttu-id="50270-136">このフィールドに対して **[ユーザー原則名]** を選ぶと、次のような方法で解析されます。</span><span class="sxs-lookup"><span data-stu-id="50270-136">If **User Principle Name** is selected for this field, it is parsed in the following way:</span></span>

   ![ユーザー名属性](media/User-name-attribute.png)

   <span data-ttu-id="50270-138">また、**[領域]** テキスト ボックスに入力したテキストで領域を上書きすることもできます。</span><span class="sxs-lookup"><span data-stu-id="50270-138">You also have the choice to overwrite the realm with the text you type in the **Realm** text box.</span></span>

   <span data-ttu-id="50270-139">たとえば、Contoso にはヨーロッパ、アジア、北米などのサブ領域があり、</span><span class="sxs-lookup"><span data-stu-id="50270-139">For example, Contoso might have several subregions such as Europe, Asia, and North America.</span></span> <span data-ttu-id="50270-140">アジアのユーザーは SSO ペイロードを使って、アプリは *username@asia.contoso.com* の形式の UPN を要求するものとします。この場合、**[ユーザー原則名]** を選ぶと、既定で各ユーザーの領域は AAD から取得されますが、それは単に *contoso.com* のようなものかもしれません。そのため、アジアのユーザーについては、このペイロードを作成し、領域を値 *asia.contoso.com* で上書きすることができます。結果として、エンド ユーザーの UPN は、*username@contoso.com* ではなく *username@asia.contoso.com* になります。</span><span class="sxs-lookup"><span data-stu-id="50270-140">They might want their users in Asia to use the SSO payload, and the app requires the UPN in the form *username@asia.contoso.com*. In this case, if you select **User Principle Name**, by default the realm for each user is taken from AAD that may be just *contoso.com*. So for users in Asia specially, you can create this payload and overwrite the realm with the value *asia.contoso.com*. Now the end user's UPN becomes *username@asia.contoso.com* and not *username@contoso.com*.</span></span>

- <span data-ttu-id="50270-141">**[デバイス ID]** を選ぶと、Intune は自動的に Intune デバイス ID を選びます。</span><span class="sxs-lookup"><span data-stu-id="50270-141">If you select **Device ID**, Intune automatically selects the Intune Device ID.</span></span>

   <span data-ttu-id="50270-142">既定では、アプリで使う必要があるのはデバイス ID だけです。</span><span class="sxs-lookup"><span data-stu-id="50270-142">By default, apps only need to use the device ID.</span></span> <span data-ttu-id="50270-143">ただし、アプリがデバイス ID に加えて領域を使う場合は、**[領域]** テキスト ボックスに領域を入力できます。</span><span class="sxs-lookup"><span data-stu-id="50270-143">But if your app uses the realm in addition to the device ID, you can type the realm in the **Realm** text box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="50270-144">既定では、デバイス ID を使う場合は領域を空のままにします。</span><span class="sxs-lookup"><span data-stu-id="50270-144">By default keep the realm empty if you use device ID.</span></span>

### <a name="url-prefixes-that-will-use-single-sign-on"></a><span data-ttu-id="50270-145">シングル サインオンを使用する URL プレフィックス</span><span class="sxs-lookup"><span data-stu-id="50270-145">URL prefixes that will use Single Sign On</span></span>

<span data-ttu-id="50270-146">組織に存在していてユーザー認証を必要とする URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="50270-146">Type any URLs here that exist in your organization that require user authentication.</span></span>

<span data-ttu-id="50270-147">たとえば、ユーザーがそのようなサイトに接続すると、iOS デバイスはシングル サインオンの資格情報を使うので、ユーザーは資格情報をさらに入力する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="50270-147">For example, when a user connects to any of these sites, the iOS device uses the single sign-on credentials and the user does not need to enter any additional credentials.</span></span> <span data-ttu-id="50270-148">ただし、多要素認証が有効になっている場合は、ユーザーは第 2 の認証情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50270-148">However, if you have multi-factor authentication enabled, users are required to enter the second authentication.</span></span>

> [!NOTE]
> <span data-ttu-id="50270-149">これらの URL は、適切な形式の FQDN である必要があります。</span><span class="sxs-lookup"><span data-stu-id="50270-149">These URLs must be properly formatted FQDN.</span></span> <span data-ttu-id="50270-150">Apple で要求されている形式は `http://<yourURL.domain>` です。</span><span class="sxs-lookup"><span data-stu-id="50270-150">Apple requires these to be in the form `http://<yourURL.domain>`</span></span>

<span data-ttu-id="50270-151">URL の一致パターンは、`http://` または `https://` で始まっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50270-151">The URL matching patterns must begin with either `http://` or `https://`.</span></span> <span data-ttu-id="50270-152">単純な文字列一致が実行されるので、URL プレフィックス `http://www.contoso.com/` は `http://www.contoso.com:80/` とは一致しません。</span><span class="sxs-lookup"><span data-stu-id="50270-152">A simple string match is performed, so the URL prefix `http://www.contoso.com/` does not match `http://www.contoso.com:80/`.</span></span> <span data-ttu-id="50270-153">ただし、iOS 9.0 以降では、単一のワイルドカード * を使って、一致するすべての値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="50270-153">With iOS 9.0 or later, however, a single wildcard * may be used to specify all matching values.</span></span> <span data-ttu-id="50270-154">たとえば、`http://*.contoso.com/` は `http://store.contoso.com/` と `http://www.contoso.com` の両方と一致します。</span><span class="sxs-lookup"><span data-stu-id="50270-154">For example, `http://*.contoso.com/`  matches both `http://store.contoso.com/` and `http://www.contoso.com`.</span></span>
<span data-ttu-id="50270-155">パターン `http://.com` はすべての HTTP URL と一致し、`https://.com` はすべての HTTPS URL と一致します。</span><span class="sxs-lookup"><span data-stu-id="50270-155">The patterns `http://.com` and `https://.com` match all HTTP and HTTPS URLs, respectively.</span></span>

### <a name="apps-that-will-use-single-sign-on"></a><span data-ttu-id="50270-156">シングル サインオンを使用するアプリ</span><span class="sxs-lookup"><span data-stu-id="50270-156">Apps that will use Single Sign On</span></span>

<span data-ttu-id="50270-157">エンド ユーザーのデバイス上のアプリで、シングル サインオン ペイロードを使うことができるものを示します。</span><span class="sxs-lookup"><span data-stu-id="50270-157">Indicate which apps on an end user’s device that can use the Single Sign on payload.</span></span>

<span data-ttu-id="50270-158">`AppIdentifierMatches` 配列には、アプリ バンドル ID と一致する文字列が含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="50270-158">The `AppIdentifierMatches` array must contain strings that match app bundle IDs.</span></span> <span data-ttu-id="50270-159">これらの文字列では、完全に一致する値 (例: `com.contoso.myapp`) を指定するか、ワイルドカード文字 * を使ってバンドル ID のプレフィックス一致を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="50270-159">These strings may be exact matches (for example: `com.contoso.myapp`) or may specify a prefix match on the bundle ID by using the * wildcard character.</span></span> <span data-ttu-id="50270-160">ワイルドカード文字は、ピリオド文字 (.) の後に指定する必要があり、文字列の最後で 1 回だけ使えます (例: `com.contoso.*`)。</span><span class="sxs-lookup"><span data-stu-id="50270-160">The wildcard character must appear after a period character (.), and may appear only once, at the end of the string (for example: `com.contoso.*`).</span></span> <span data-ttu-id="50270-161">ワイルドカードが含まれる場合は、バンドル ID がプレフィックスで始まるすべてのアプリが、アカウントへのアクセスを許可されます。</span><span class="sxs-lookup"><span data-stu-id="50270-161">When a wildcard is included, any app whose bundle ID begins with the prefix is granted access to the account.</span></span>

<span data-ttu-id="50270-162">**[アプリ名]** フィールドは、バンドル ID の識別を容易にするわかりやすい名前を追加するために使われます。</span><span class="sxs-lookup"><span data-stu-id="50270-162">The **App Name** field is used to add a user-friendly name to help you identify the bundle ID.</span></span>

### <a name="credential-renewal-certificate"></a><span data-ttu-id="50270-163">資格情報更新証明書</span><span class="sxs-lookup"><span data-stu-id="50270-163">Credential renewal certificate</span></span>

<span data-ttu-id="50270-164">エンド ユーザーを (パスワードではなく) 証明書で認証する場合は、このフィールドを使って、認証証明書としてユーザーに展開される SCEP 証明書または PFX 証明書を選びます。</span><span class="sxs-lookup"><span data-stu-id="50270-164">If you authenticate your end users with certificates (not passwords), then use this field to select the SCEP or PFX certificate that is deployed to the user as the authentication certificate.</span></span> <span data-ttu-id="50270-165">通常、これは VPN、WiFi、電子メールなどの他のプロファイル用にユーザーに展開されるものと同じ証明書です。</span><span class="sxs-lookup"><span data-stu-id="50270-165">Typically, this is the same certificate that is deployed to the user for other profiles such as VPN, WiFi, or Email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="50270-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="50270-166">Next steps</span></span>

<span data-ttu-id="50270-167">デバイスの機能の構成について詳しくは、「[Microsoft Intune でデバイスの機能設定を構成する方法](device-features-configure.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50270-167">For additional device feature configuration information, see [How to configure device feature settings in Microsoft Intune](device-features-configure.md).</span></span>