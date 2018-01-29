---
title: "MTD アプリを追加して Intune に割り当てる"
titleSuffix: Azure portal
description: "Azure Portal 内の Intune で MTD アプリ、Microsoft Authenticator アプリ、iOS 構成ポリシーを追加する"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9aabfd0f879415ce8fa68bad0f8ee91f2413d075
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a><span data-ttu-id="a0c97-103">Intune で Mobile Threat Defense (MTD) アプリを追加して割り当てる</span><span class="sxs-lookup"><span data-stu-id="a0c97-103">Add and assign Mobile Threat Defense (MTD) apps with Intune</span></span>

> [!NOTE] 
> <span data-ttu-id="a0c97-104">このトピックは、すべての Mobile Threat Defense パートナーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-104">This topic applies to all Mobile Threat Defense partners.</span></span>

<span data-ttu-id="a0c97-105">脅威がモバイル デバイスで特定されたときにエンドユーザーが通知を受け取れるように、また、脅威を除去するための手引きが受けられるように、Intune を利用して MTD アプリを追加して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-105">You can use Intune to add and deploy MTD apps so end-users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.</span></span>

<span data-ttu-id="a0c97-106">iOS デバイスでは、Azure AD によってチェックされた ID がユーザーに与えられるように、[Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) が必要です。</span><span class="sxs-lookup"><span data-stu-id="a0c97-106">For iOS devices, you need the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) so users can have their identities checked by Azure AD.</span></span> <span data-ttu-id="a0c97-107">さらに、Intune で使用するには MTD の iOS アプリが通知される iOS アプリ構成ポリシーも必要です。</span><span class="sxs-lookup"><span data-stu-id="a0c97-107">Additionally, you need the iOS app configuration policy which signals the MTD iOS app to use with Intune.</span></span>

> [!TIP]
> <span data-ttu-id="a0c97-108">Intune ポータル サイトは Android デバイスでブローカーとして機能するため、ユーザーに Azure AD によってチェックされた ID が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-108">The Intune company portal works as the broker on Android devices so users can have their identities checked by Azure AD.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a0c97-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="a0c97-109">Before you begin</span></span>

-   <span data-ttu-id="a0c97-110">[Azure Portal](https://portal.azure.com/) で以下の手順を完了しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c97-110">The below steps need to be completed in the [Azure portal](https://portal.azure.com/).</span></span>

-   <span data-ttu-id="a0c97-111">次のプロセスをよく理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c97-111">Make sure you’re familiar with the process of:</span></span>

    -   <span data-ttu-id="a0c97-112">[Intune にアプリを追加する](apps-add.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c97-112">[Adding an app into Intune](apps-add.md).</span></span>

    -   <span data-ttu-id="a0c97-113">[iOS アプリ構成ポリシーを Intune に追加する](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="a0c97-113">[Adding an iOS app configuration policy into Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="a0c97-114">[Intune でアプリを割り当てる](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="a0c97-114">[Assigning an app with Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="a0c97-115">[iOS アプリ構成ポリシーを追加する](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="a0c97-115">[ Adding an iOS app configuration policy](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

## <a name="to-add-apps"></a><span data-ttu-id="a0c97-116">アプリを追加するには</span><span class="sxs-lookup"><span data-stu-id="a0c97-116">To add apps</span></span>

### <a name="all-mtd-partners"></a><span data-ttu-id="a0c97-117">すべての MTD パートナー</span><span class="sxs-lookup"><span data-stu-id="a0c97-117">All MTD partners</span></span>

#### <a name="microsoft-authenticator-app-for-ios"></a><span data-ttu-id="a0c97-118">iOS 向け Microsoft Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="a0c97-118">Microsoft Authenticator app for iOS</span></span>

- <span data-ttu-id="a0c97-119">iOS ストア アプリを Microsoft Intune に追加する方法については、[こちら](store-apps-ios.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-119">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="a0c97-120">「**アプリ情報を構成する**」セクションの**手順 5** には、この [Microsoft Authenticator アプリ ストア URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-120">Use this [Microsoft Authenticator app store URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) on **step 5** under the **Configure app information** section.</span></span>

### <a name="lookout"></a><span data-ttu-id="a0c97-121">Lookout</span><span class="sxs-lookup"><span data-stu-id="a0c97-121">Lookout</span></span>

#### <a name="android"></a><span data-ttu-id="a0c97-122">Android</span><span class="sxs-lookup"><span data-stu-id="a0c97-122">Android</span></span>
- <span data-ttu-id="a0c97-123">Android ストア アプリを Microsoft Intune に追加する方法については、[こちら](store-apps-android.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-123">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="a0c97-124">**手順 7** には、この [Lookout for work の Google アプリ ストア URL](https://play.google.com/store/apps/details?id=com.lookout.enterprise) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-124">Use this [Lookout for work Google app store URL](https://play.google.com/store/apps/details?id=com.lookout.enterprise) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="a0c97-125">iOS</span><span class="sxs-lookup"><span data-stu-id="a0c97-125">iOS</span></span>

- <span data-ttu-id="a0c97-126">iOS ストア アプリを Microsoft Intune に追加する方法については、[こちら](store-apps-ios.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-126">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="a0c97-127">「**アプリ情報を構成する**」セクションの**手順 5** には、この [Lookout for Work iOS アプリ ストア URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-127">Use this [Lookout for Work iOS app store URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) on **step 5** under the **Configure app information** section.</span></span>

#### <a name="lookout-for-work-app-outside-the-apple-store"></a><span data-ttu-id="a0c97-128">Apple ストア以外の Lookout for Work アプリ</span><span class="sxs-lookup"><span data-stu-id="a0c97-128">Lookout for Work app outside the Apple store</span></span>

<span data-ttu-id="a0c97-129">Lookout for Work iOS アプリに再署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c97-129">You need to re-sign the Lookout for Work iOS app.</span></span> <span data-ttu-id="a0c97-130">Lookout は、iOS App Store 以外の場所で Lookout for Work iOS アプリを配布しています。</span><span class="sxs-lookup"><span data-stu-id="a0c97-130">Lookout distributes its Lookout for Work iOS app outside of the iOS App Store.</span></span> <span data-ttu-id="a0c97-131">アプリを配布する前に、iOS Enterprise Developer Certificate でアプリに再署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c97-131">Before distributing the app, you must re-sign the app with your iOS Enterprise Developer Certificate.</span></span>

<span data-ttu-id="a0c97-132">Lookout for Work iOS アプリに再署名する詳細な手順については、Lookout の Web サイトの「[Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714)」(Lookout for Work iOS アプリの再署名プロセス) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-132">For detailed instructions to re-sign the Lookout for Work iOS apps, see [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) on the Lookout website.</span></span>

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a><span data-ttu-id="a0c97-133">Lookout for Work iOS アプリで Azure AD 認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="a0c97-133">Enable Azure AD authentication for Lookout for Work iOS app</span></span>

<span data-ttu-id="a0c97-134">次の手順を実行して、iOS ユーザーの Azure Active Directory 認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a0c97-134">Enable Azure Active Directory authentication for the iOS users by doing the following:</span></span>

1. <span data-ttu-id="a0c97-135">[Azure Portal](https://portal.sazure.com) に移動し、資格情報でサインインして、アプリケーションのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a0c97-135">Go to the [Azure portal](https://portal.sazure.com), sign in with your credentials, then navigate to the application page.</span></span>

2. <span data-ttu-id="a0c97-136">**ネイティブ クライアント アプリケーション**として **Lookout for Work iOS アプリ**を追加します。</span><span class="sxs-lookup"><span data-stu-id="a0c97-136">Add the **Lookout for Work iOS app** as a **native client application**.</span></span>

3. <span data-ttu-id="a0c97-137">**com.lookout.enterprise.yourcompanyname** は、IPA に署名したときに選択したカスタマー バンドル ID で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-137">Replace the **com.lookout.enterprise.yourcompanyname** with the customer bundle ID you selected when you signed the IPA.</span></span>

4.  <span data-ttu-id="a0c97-138">リダイレクト URI を追加します。**&lt;companyportal://code/>** の後に、元のリダイレクト URI を URL エンコードしたバージョンを続けます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-138">Add additional redirect URI: **&lt;companyportal://code/>** followed by a URL encoded version of your original redirect URI.</span></span>

5.  <span data-ttu-id="a0c97-139">アプリに**デリゲートされたアクセス許可**を追加します。</span><span class="sxs-lookup"><span data-stu-id="a0c97-139">Add **Delegated Permissions** to your app.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="a0c97-140">詳細については、「[ネイティブ クライアント アプリケーションの構成](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-140">See [configure a native client application with Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) for more details.</span></span>

##### <a name="add-the-lookout-for-work-ipa-file"></a><span data-ttu-id="a0c97-141">Lookout for Work の ipa ファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="a0c97-141">Add the Lookout for Work ipa file</span></span>

- <span data-ttu-id="a0c97-142">[Intune での iOS LOB アプリの追加](lob-apps-ios.md)に関するトピックの説明に従って、再署名した .ipa ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a0c97-142">Upload the re-signed .ipa file as described in the [Add iOS LOB apps with Intune](lob-apps-ios.md) topic.</span></span> <span data-ttu-id="a0c97-143">また、最小 OS バージョンを iOS 8.0 以降に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c97-143">You also need to set the minimum OS version to iOS 8.0 or later.</span></span>

### <a name="skycure"></a><span data-ttu-id="a0c97-144">Skycure</span><span class="sxs-lookup"><span data-stu-id="a0c97-144">Skycure</span></span>

#### <a name="android"></a><span data-ttu-id="a0c97-145">Android</span><span class="sxs-lookup"><span data-stu-id="a0c97-145">Android</span></span>

- <span data-ttu-id="a0c97-146">Android ストア アプリを Microsoft Intune に追加する方法については、[こちら](store-apps-android.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-146">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="a0c97-147">**手順 7**には、この [Skycure アプリ ストア URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-147">Use this [Skycure app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="a0c97-148">iOS</span><span class="sxs-lookup"><span data-stu-id="a0c97-148">iOS</span></span>

- <span data-ttu-id="a0c97-149">iOS ストア アプリを Microsoft Intune に追加する方法については、[こちら](store-apps-ios.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-149">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="a0c97-150">「**アプリ情報を構成する**」セクションの**手順 5** には、この [Skycure アプリ ストア URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-150">Use this [Skycure app store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) on **step 5** under the **Configure app information** section.</span></span>

### <a name="check-point-sandblast-mobile"></a><span data-ttu-id="a0c97-151">Check Point SandBlast Mobile</span><span class="sxs-lookup"><span data-stu-id="a0c97-151">Check Point SandBlast Mobile</span></span>

#### <a name="android"></a><span data-ttu-id="a0c97-152">Android</span><span class="sxs-lookup"><span data-stu-id="a0c97-152">Android</span></span>

- <span data-ttu-id="a0c97-153">Android ストア アプリを Microsoft Intune に追加する方法については、[こちら](store-apps-android.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-153">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="a0c97-154">**手順 7** には、この [Check Point SandBlast Mobile のアプリ ストア URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-154">Use this [Check Point SandBlast Mobile app store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="a0c97-155">iOS</span><span class="sxs-lookup"><span data-stu-id="a0c97-155">iOS</span></span>

- <span data-ttu-id="a0c97-156">[Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/) に連絡して iOS アプリを取得してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-156">Contact [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/) to get the iOS app.</span></span> <span data-ttu-id="a0c97-157">[iOS ストア アプリを Microsoft Intune に追加する](store-apps-ios.md)手順を確認し、「**アプリ情報を構成する**」セクションの**手順 5** で、Apple ストアの URL を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-157">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md), then use the Apple store URL on **step 5** under the **Configure app information** section.</span></span>

### <a name="zimperium"></a><span data-ttu-id="a0c97-158">Zimperium</span><span class="sxs-lookup"><span data-stu-id="a0c97-158">Zimperium</span></span>

#### <a name="android"></a><span data-ttu-id="a0c97-159">Android</span><span class="sxs-lookup"><span data-stu-id="a0c97-159">Android</span></span>

- <span data-ttu-id="a0c97-160">Android ストア アプリを Microsoft Intune に追加する方法については、[こちら](store-apps-android.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-160">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="a0c97-161">**手順 7** には、この [Zimperium アプリ ストア URL](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-161">Use this [Zimperium app store URL](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="a0c97-162">iOS</span><span class="sxs-lookup"><span data-stu-id="a0c97-162">iOS</span></span>

- <span data-ttu-id="a0c97-163">iOS ストア アプリを Microsoft Intune に追加する方法については、[こちら](store-apps-ios.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-163">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="a0c97-164">「**アプリ情報を構成する**」セクションの**手順 5** には、この [Zimperium アプリ ストア URL](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-164">Use this [Zimperium app store URL](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) on **step 5** under the **Configure app information** section.</span></span>

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a><span data-ttu-id="a0c97-165">MTD アプリを iOS アプリ構成ポリシーと関連付けるには</span><span class="sxs-lookup"><span data-stu-id="a0c97-165">To associate the MTD app with an iOS app configuration policy</span></span>

### <a name="for-lookout"></a><span data-ttu-id="a0c97-166">Lookout の場合</span><span class="sxs-lookup"><span data-stu-id="a0c97-166">For Lookout</span></span>

- <span data-ttu-id="a0c97-167">[iOS アプリ構成ポリシーの使用](app-configuration-policies-use-ios.md)に関するトピックの説明に従って、iOS アプリ構成ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0c97-167">Create the iOS app configuration policy as described in the [using iOS app configuration policy](app-configuration-policies-use-ios.md) topic.</span></span>

### <a name="for-skycure"></a><span data-ttu-id="a0c97-168">Skycure の場合</span><span class="sxs-lookup"><span data-stu-id="a0c97-168">For Skycure</span></span>

-   <span data-ttu-id="a0c97-169">[Skycure 管理コンソール](https://aad.skycure.com)で以前に構成したものと同じ Azure AD アカウントを使います。これは、Intune クラシック ポータルにログインするためのものと同じアカウントにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c97-169">Use the same Azure AD account previously configured in the [Skycure Management console](https://aad.skycure.com), which should be the same account used to log in to the Intune classic portal.</span></span>

-   <span data-ttu-id="a0c97-170">iOS アプリ構成ポリシーのファイルは次のようにして**ダウンロードする**必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c97-170">You need to **download** the iOS app configuration policy file:</span></span> 
    -   <span data-ttu-id="a0c97-171">[Skycure Management コンソール](https://aad.skycure.com)に移動して、管理者資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="a0c97-171">Go to [Skycure Management console](https://aad.skycure.com) and sign in with your admin credentials.</span></span>

    -   <span data-ttu-id="a0c97-172">**[設定]** &gt; **[Device Management Integrations (デバイス管理統合)]** &gt; **[EMM Integration Selection (EMM 統合選択)]** の順に進み、**[Microsoft Intune]** を選択し、選択を保存します。</span><span class="sxs-lookup"><span data-stu-id="a0c97-172">Go to **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection**, choose **Microsoft Intune**, then save your selection.</span></span>

    -   <span data-ttu-id="a0c97-173">**[Integration setup files (統合セットアップ ファイル)]** リンクをクリックし、生成された \*.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a0c97-173">Click on the **Integration setup files** link and save the generated \*.zip file.</span></span> <span data-ttu-id="a0c97-174">この .zip ファイルには **skycure\_configuration.plist** ファイルが含まれます。このファイルを利用し、Intune で iOS アプリ構成ポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-174">The .zip file contains the **skycure\_configuration.plist** file, which will be used to create the iOS app configuration policy in Intune.</span></span>

    -   <span data-ttu-id="a0c97-175">[iOS 用 Microsoft Intune アプリ構成ポリシーを使用する](app-configuration-policies-use-ios.md)手順に従って、Skycure iOS アプリ構成ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0c97-175">See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Skycure iOS app configuration policy.</span></span>

    - <span data-ttu-id="a0c97-176">**手順 8** で、**[XML データを入力する]** オプションを使用して内容を **skycure_configuration.plist** ファイルからコピーして、構成ポリシーの本文に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-176">On **step 8**, use the option **Enter XML data**, copy the content from the **skycure_configuration.plist** file and paste its content into the configuration policy body.</span></span>

<span data-ttu-id="a0c97-177">**skycure_configuration.plist** の内容は以下からコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-177">You can also copy the **skycure_configuration.plist** content from here:</span></span>

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>
```
### <a name="for-check-point-sandblast-mobile"></a><span data-ttu-id="a0c97-178">Check Point SandBlast Mobile の場合</span><span class="sxs-lookup"><span data-stu-id="a0c97-178">For Check Point SandBlast Mobile</span></span>

- <span data-ttu-id="a0c97-179">[iOS 用 Microsoft Intune アプリ構成ポリシーを使用する](app-configuration-policies-use-ios.md)手順に従って、Check Point SandBlast Mobile iOS アプリ構成ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0c97-179">See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Check Point SandBlast Mobile iOS app configuration policy.</span></span>
    - <span data-ttu-id="a0c97-180">**手順 8** で、**[XML データを入力する]** オプションを使用して以下の内容をコピーし、構成ポリシーの本文に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-180">On **step 8**, use the option **Enter XML data**, copy the content below and paste it into the configuration policy body.</span></span>

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="for-zimperium"></a><span data-ttu-id="a0c97-181">Zimperium の場合</span><span class="sxs-lookup"><span data-stu-id="a0c97-181">For Zimperium</span></span>

- <span data-ttu-id="a0c97-182">[iOS 用 Microsoft Intune アプリ構成ポリシーを使用する](app-configuration-policies-use-ios.md)手順に従って、Zimperium iOS アプリ構成ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0c97-182">See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Zimperium iOS app configuration policy.</span></span>
    - <span data-ttu-id="a0c97-183">**手順 8** で、**[XML データを入力する]** オプションを使用して以下の内容をコピーし、構成ポリシーの本文に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a0c97-183">On **step 8**, use the option **Enter XML data**, copy the content below and paste it into the configuration policy body.</span></span>

```
<dict>
<key>provider</key><string>Intune</string>
<key>userprincipalname</key><string>{{userprincipalname}}</string>
<key>deviceid</key>
<string>{{deviceid}}</string>
<key>serialnumber</key>
<string>{{serialnumber}}</string>
<key>udidlast4digits</key>
<string>{{udidlast4digits}}</string>
</dict>
```

## <a name="to-assign-apps-all-mtd-partners"></a><span data-ttu-id="a0c97-184">アプリを割り当てるには (すべての MTD パートナー)</span><span class="sxs-lookup"><span data-stu-id="a0c97-184">To assign apps (All MTD partners)</span></span>

- <span data-ttu-id="a0c97-185">[Intune でアプリをグループに割り当てる](apps-deploy.md)手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c97-185">See instructions for [assigning apps to groups with Intune](apps-deploy.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a0c97-186">次の手順</span><span class="sxs-lookup"><span data-stu-id="a0c97-186">Next steps</span></span>

- [<span data-ttu-id="a0c97-187">MTD のデバイス コンプライアンス ポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="a0c97-187">Add device compliance policy for MTD</span></span>](mtd-device-compliance-policy-create.md)
