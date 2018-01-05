---
title: "Lookout for Work アプリを展開する"
description: "Android 用の Lookout for Work アプリを構成して展開します。"
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9f20eef15807766fd8bd83174140205050681a16
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="configure-and-deploy-lookout-for-work-app"></a><span data-ttu-id="a39c6-103">Lookout for Work アプリを構成して展開する</span><span class="sxs-lookup"><span data-stu-id="a39c6-103">Configure and deploy Lookout for Work app</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="a39c6-104">この記事では、Android デバイスと iOS デバイス用に Lookout for Work アプリを構成し、展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-104">This article explains how to configure and deploy the Lookout for Work app for Android and iOS devices.</span></span>

## <a name="android-google-play-store-app"></a><span data-ttu-id="a39c6-105">Android (Google Play ストア アプリ)</span><span class="sxs-lookup"><span data-stu-id="a39c6-105">Android (Google Play Store app)</span></span>

1. <span data-ttu-id="a39c6-106">[Microsoft Intune 管理者コンソール](https://manage.microsoft.com)で、**[アプリ]** に移動し、**[アプリの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-106">In the [Microsoft Intune administrator console](https://manage.microsoft.com), go to **Apps** and choose **Add Apps**.</span></span>
2. <span data-ttu-id="a39c6-107">発行元の **[ソフトウェア セットアップ]** ページで、**[外部リンク]** を選択し、URL "https://play.google.com/store/apps/details?id=com.lookout.enterprise" を指定します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-107">On the **Software Setup** page of the publisher, choose **External link**, and specify the following URL:  https://play.google.com/store/apps/details?id=com.lookout.enterprise</span></span>
   >[!NOTE]
   ><span data-ttu-id="a39c6-108">Managed Browser を要求するボックスをオンにしないでください。</span><span class="sxs-lookup"><span data-stu-id="a39c6-108">Do not click the box for requiring a managed browser.</span></span>

3. <span data-ttu-id="a39c6-109">**[ソフトウェアの説明]** ページで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-109">On the **Software description** page fill in the following information:</span></span>
   * <span data-ttu-id="a39c6-110">**[発行元]:** Lookout Mobile Security</span><span class="sxs-lookup"><span data-stu-id="a39c6-110">**Publisher:** Lookout Mobile Security</span></span>
   * <span data-ttu-id="a39c6-111">**[名前]:**   Lookout for Work</span><span class="sxs-lookup"><span data-stu-id="a39c6-111">**Name:**   Lookout for Work</span></span>
   * <span data-ttu-id="a39c6-112">**[説明]:**  Lookout はモバイルの脅威に対する最適な保護を提供し、モバイル デバイスの安全を保ちます。</span><span class="sxs-lookup"><span data-stu-id="a39c6-112">**Description:**  Lookout offers the best protection against mobile threats to keep your device safe.</span></span> <span data-ttu-id="a39c6-113">デバイスにインストールされた Lookout アプリは、デバイスを脅威から保護し、検出された脅威を管理者に通知します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-113">When the Lookout app is installed on the device, the app protects your device from threats and will alert you, and your company administrator, if any are found.</span></span>
   * <span data-ttu-id="a39c6-114">**[カテゴリ]:** コンピューターの管理</span><span class="sxs-lookup"><span data-stu-id="a39c6-114">**Category:** Computer Management</span></span>

4. <span data-ttu-id="a39c6-115">正常に完了すると、**[Microsoft Intune にデータが正常にアップロードされました]** というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a39c6-115">Upon successful completion you see a message **Upload of data to Microsoft Intune successfully completed**.</span></span>

   <span data-ttu-id="a39c6-116">Intune コンソールで **[アプリ]** をクリックすると、**Lookout for Work** アプリが一覧に表示されます。![Intune 管理者コンソールのアプリ ページの一覧に表示された Lookout for Work アプリのスクリーンショット](../media/mtp/lookout-app-listed-intune-console.png)</span><span class="sxs-lookup"><span data-stu-id="a39c6-116">In the Intune Console when you click on the **Apps** you will now see the **Lookout for Work** app in the list ![screenshot of Intune admin console apps page showing the Lookout for work apps in the list](../media/mtp/lookout-app-listed-intune-console.png)</span></span>

5. <span data-ttu-id="a39c6-117">アプリをユーザーに展開するには、Lookout for Work アプリを選択し、**[展開の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-117">Deploy the app to users by selecting the Lookout for Work app and choosing  **Manage Deployment**.</span></span>

   <span data-ttu-id="a39c6-118">Lookout MTP コンソールの 「Enrollment Management」 (登録管理) オプションで追加したものと同じユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a39c6-118">You must select the same users added in to the Enrollment Management option in the Lookout MTP console.</span></span>  <span data-ttu-id="a39c6-119">Lookout MTP へのユーザー グループの追加の詳細については、「[Lookout MTP でサブスクリプションを構成する](configure-deploy-lookout-for-work-app.md)」セクションの手順 3 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a39c6-119">See Step 3 in the [configure your subscription with Lookout MTP section](configure-deploy-lookout-for-work-app.md) for information about adding user groups to Lookout MTP.</span></span>

   >[!IMPORTANT]
   > <span data-ttu-id="a39c6-120">Intune アプリ展開ウィザードは Azure AD のユーザー グループを認識せず、代わりに Intune のユーザー グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-120">The Intune app deployment Wizard is not aware of the Azure AD user groups and uses the Intune user groups instead.</span></span> <span data-ttu-id="a39c6-121">したがって、Lookout MTP コンソールで登録されている Azure AD のユーザー グループに基づいて Intune のユーザー グループを作成する必要があります ([こちら](plan-your-user-and-device-groups.md)のトピックを参照)。</span><span class="sxs-lookup"><span data-stu-id="a39c6-121">So you must create an Intune user group based on the Azure AD user group that is enrolled in the Lookout MTP console as described in [this](plan-your-user-and-device-groups.md)topic.</span></span>

6. <span data-ttu-id="a39c6-122">**[必須のインストール]** オプションを選択し、Lookout アプリがユーザーのデバイスに必ずインストールされるようにします。</span><span class="sxs-lookup"><span data-stu-id="a39c6-122">Choose the **Required Install** option to require that the Lookout app be installed on the user’s device.</span></span>

## <a name="ios-enterprise-signed-version-of-lookout-app"></a><span data-ttu-id="a39c6-123">iOS (Enterprise 署名バージョンの Lookout アプリ)</span><span class="sxs-lookup"><span data-stu-id="a39c6-123">iOS (Enterprise-signed version of Lookout app)</span></span>

1. <span data-ttu-id="a39c6-124">**iOS 管理**がデバイスにセットアップされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-124">Make sure **iOS management** is set up on your device.</span></span> <span data-ttu-id="a39c6-125">デバイスで iOS 管理をセットアップする手順については、「[iOS および Mac のデバイス管理をセットアップする](set-up-ios-and-mac-management-with-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a39c6-125">For instructions on how to set up your device for iOS management, see [Set up iOS and Mac device management](set-up-ios-and-mac-management-with-microsoft-intune.md).</span></span>

2. <span data-ttu-id="a39c6-126">Lookout for Work iOS アプリに**再署名**します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-126">**Re-sign** the Lookout for Work iOS app.</span></span> <span data-ttu-id="a39c6-127">Lookout は、iOS App Store 以外の場所で Lookout for Work iOS アプリを配布しています。</span><span class="sxs-lookup"><span data-stu-id="a39c6-127">Lookout distributes its Lookout for Work iOS app outside of the iOS App Store.</span></span> <span data-ttu-id="a39c6-128">**アプリを配布する前に**、iOS Enterprise Developer Certificate でアプリに再署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a39c6-128">**Before distributing the app**, you must re-sign the app with your iOS Enterprise Developer Certificate.</span></span> <span data-ttu-id="a39c6-129">Lookout for Work アプリに再署名する詳細な手順については、Lookout サイトの「[Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714)」(Lookout for Work iOS アプリの再署名プロセス) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a39c6-129">For detailed instructions to re-sign the Lookout for Work iOS apps, see [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) on the Lookout site.</span></span>

3. <span data-ttu-id="a39c6-130">次の手順を実行して、iOS ユーザーの Azure Active Directory 認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a39c6-130">Enable Azure Active Directory authentication for the iOS users by doing the following:</span></span>
   1.  <span data-ttu-id="a39c6-131">[Azure Active Directory 管理ポータル](https://manage.windowsazure.com)にログインし、アプリケーション ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-131">Login to the [Azure Active Directory management portal](https://manage.windowsazure.com), and navigate to the application page.</span></span>
   2.  <span data-ttu-id="a39c6-132">**Lookout for Work iOS アプリ**を**ネイティブ クライアント アプリケーション**として追加します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-132">Add the **Lookout for Work iOS app** as a **native client application**.</span></span>
   <span data-ttu-id="a39c6-133">![ネイティブ クライアント アプリ オプションが表示されたアプリの追加ダイアログのスクリーンショット](../media/mtp/aad-add-app.png)</span><span class="sxs-lookup"><span data-stu-id="a39c6-133">![screenshot of the add apps dialog showing the native client app option](../media/mtp/aad-add-app.png)</span></span>
   3. <span data-ttu-id="a39c6-134">**com.lookout.enterprise.yourcompanyname** は、IPA に署名したときに選択したカスタマー バンドル ID で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a39c6-134">Replace the **com.lookout.enterprise.yourcompanyname** with the customer bundle ID you selected when you signed the IPA.</span></span>
   4.  <span data-ttu-id="a39c6-135">リダイレクト URI を追加します。**&lt;companyportal://code/>** の後に、元のリダイレクト URI を URL エンコードしたバージョンを続けます。</span><span class="sxs-lookup"><span data-stu-id="a39c6-135">Add additional redirect URI: **&lt;companyportal://code/>** followed by a URLencoded version of your original redirect URI.</span></span>
   5.  <span data-ttu-id="a39c6-136">アプリに**委任されたアクセス許可**を追加します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-136">Add **Delegated Permissions** to your app.</span></span>

   <span data-ttu-id="a39c6-137">詳細については、「[ネイティブ クライアント アプリケーションの構成](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a39c6-137">For more details, see [Configure a native client application](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).</span></span>

4. <span data-ttu-id="a39c6-138">[Microsoft Intune でのモバイル デバイスのアプリの追加](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)に関するトピックの説明に従って、再署名した .ipa ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a39c6-138">Upload the re-signed .ipa file as described in the [Add app for mobile devices in Microsoft Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) topic.</span></span> <span data-ttu-id="a39c6-139">最小 OS バージョンを iOS 8.0 以降に設定します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-139">Set the minimum OS version to iOS 8.0 or later.</span></span>

   ![アプリの一覧に Lookout for Work アプリが表示された Intune 管理コンソールのアプリ ページのスクリーンショット](../media/mtp/ios-app-uploaded-intune.png)

5. <span data-ttu-id="a39c6-141">「[Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)」 (Microsoft Intune でのモバイル アプリ構成ポリシーを使用した iOS アプリの構成) の説明に従って、管理対象アプリの構成ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-141">Create the managed app configuration policy as described in the [Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) topic.</span></span>

   ![iOS 8.0 以降のアプリ構成ポリシーが強調表示された新しいポリシーの作成ウィザードのスクリーンショット](../media/mtp/ios-app-config.png)

6. <span data-ttu-id="a39c6-143">**アプリをユーザーに展開する**には、Lookout for Work アプリを選択し、**[展開の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a39c6-143">**To deploy the app to users**, select the Lookout for Work app, and choose **Manage Deployment**.</span></span>

   <span data-ttu-id="a39c6-144">Lookout コンソールの 「Enrollment Management」 (登録管理) オプションで追加したのと同じユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a39c6-144">You must select the same users that were added to the Enrollment Management option in the Lookout  console.</span></span>  <span data-ttu-id="a39c6-145">Lookout MTP へのユーザー グループの追加の詳細については、「[Lookout サブスクリプションを構成する](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps)」セクションの手順 3 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a39c6-145">See Step 3 in the [configure your Lookout subscription section](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps) for information about adding user groups to Lookout MTP.</span></span>

   >[!IMPORTANT]
   > <span data-ttu-id="a39c6-146">Intune アプリ展開ウィザードでは、Azure AD ユーザー グループは認識されず、代わりに Intune ユーザー グループが使用されます。このため、[こちら](plan-your-user-and-device-groups.md)のトピックの説明に従って Lookout コンソールで登録した Azure AD ユーザー グループに基づいて Intune ユーザー グループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a39c6-146">The Intune app deployment wizard is not aware of the Azure AD user groups and uses the Intune user groups instead, so you must create an Intune user group based on the Azure AD user group that is enrolled in the Lookout console as described in [this](plan-your-user-and-device-groups.md) topic.</span></span>

   <span data-ttu-id="a39c6-147">**[必須のインストール]** オプションを選択し、Lookout アプリがユーザーのデバイスに必ずインストールされるようにします。</span><span class="sxs-lookup"><span data-stu-id="a39c6-147">Choose the **Required Install** option to require that the Lookout app be installed on the user’s device.</span></span>

## <a name="what-happens-when-the-deployed-app-is-opened-on-the-device"></a><span data-ttu-id="a39c6-148">展開したアプリがデバイスで開かれている場合はどうなりますか</span><span class="sxs-lookup"><span data-stu-id="a39c6-148">What happens when the deployed app is opened on the device</span></span>
<span data-ttu-id="a39c6-149">https://github.com/Microsoft/Docs/blob/master/ContributorGuide/index.md ユーザーがデバイスで Lookout for Work を開くと、アプリをアクティブ化し、[Sign in with Azure Active Directory (Azure Active Directory でサインインする)] オプションを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a39c6-149">https://github.com/Microsoft/Docs/blob/master/ContributorGuide/index.md When the user opens the Lookout for Work on the device they are prompted to activate the app, and choose the Sign in with Azure Active Directory option.</span></span> <span data-ttu-id="a39c6-150">エンド ユーザーの詳細な手順については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a39c6-150">A detailed walkthrough with the end-user flow can be found in the following topics:</span></span>

* [<span data-ttu-id="a39c6-151">Android デバイスで Lookout for Work のインストールを求められる</span><span class="sxs-lookup"><span data-stu-id="a39c6-151">You are prompted to install Lookout for Work on your Android device</span></span>](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)

* [<span data-ttu-id="a39c6-152">Lookout for Work が Android デバイスで検出した脅威を解決する必要がある</span><span class="sxs-lookup"><span data-stu-id="a39c6-152">You need to resolve a threat that Lookout for Work found on your Android device</span></span>](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <a name="next-steps"></a><span data-ttu-id="a39c6-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="a39c6-153">Next steps</span></span>
* [<span data-ttu-id="a39c6-154">Intune での Lookout デバイス コンプライアンス ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="a39c6-154">Create Lookout device compliance policy in Intune</span></span>](https://docs.microsoft.com/sccm/protect/deploy-use/enable-device-threat-protection-rule-compliance-policy)
