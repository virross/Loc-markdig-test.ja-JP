---
title: "Microsoft Intune App SDK の概要"
description: "Microsoft Intune でモバイル アプリケーション管理 (MAM) 用のモバイル アプリをすぐに有効にできます。"
keywords: 
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7f5433dd7d938c8b3bdef71d0e847195ab7591b3
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="get-started-with-the-microsoft-intune-app-sdk"></a><span data-ttu-id="30d6b-103">Microsoft Intune アプリ SDK の概要</span><span class="sxs-lookup"><span data-stu-id="30d6b-103">Get started with the Microsoft Intune App SDK</span></span>

<span data-ttu-id="30d6b-104">このガイドを利用すると、Microsoft Intune でアプリ保護ポリシーに対してモバイル アプリをすぐに有効にできます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-104">This guide will help you quickly enable your mobile app for app protection policies with Microsoft Intune.</span></span> <span data-ttu-id="30d6b-105">まず、「[Intune アプリ SDK の概要](app-sdk.md)」で説明されている Intune アプリ SDK の利点を理解しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="30d6b-105">You may find it useful to first understand the benefits of the Intune App SDK, as explained in the [Intune App SDK overview](app-sdk.md).</span></span>

<span data-ttu-id="30d6b-106">Intune アプリ SDK は、iOS と Android で類似するシナリオをサポートしており、プラットフォーム全体にわたって一貫した操作性を IT 管理者に提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="30d6b-106">The Intune App SDK supports similar scenarios across iOS and Android, and is intended to create a consistent experience across the platforms for IT admins.</span></span> <span data-ttu-id="30d6b-107">ただし、各プラットフォームの制限により、特定機能のサポートについてわずかな相違点があります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-107">But there are small differences in the support of certain features, because of platform limitations.</span></span>

## <a name="register-your-store-app-with-microsoft"></a><span data-ttu-id="30d6b-108">Microsoft でのストア アプリの登録</span><span class="sxs-lookup"><span data-stu-id="30d6b-108">Register your store app with Microsoft</span></span>

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a><span data-ttu-id="30d6b-109">アプリが組織内向けであり、一般に公開できない場合:</span><span class="sxs-lookup"><span data-stu-id="30d6b-109">If your app is internal to your organization and will not be publicly available:</span></span>

<span data-ttu-id="30d6b-110">アプリを登録する*必要はありません*。</span><span class="sxs-lookup"><span data-stu-id="30d6b-110">You *do not need* to register your app.</span></span> <span data-ttu-id="30d6b-111">社内向け基幹業務アプリの場合、IT 管理者社内にアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-111">For internal line-of-business apps, the IT administrator will deploy the app internally.</span></span> <span data-ttu-id="30d6b-112">Intune は、アプリが SDK でビルドされたことを検出し、IT 管理者がアプリ保護ポリシーを適用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="30d6b-112">Intune will detect that the app has been built with the SDK, and will let the IT administrator apply app protection policy to it.</span></span> <span data-ttu-id="30d6b-113">「[アプリ保護ポリシーに対して iOS または Android アプリを有効にする](#enable-your-iOS-or-Android-app-for-app-protection-policy)」セクションに進んでください。</span><span class="sxs-lookup"><span data-stu-id="30d6b-113">You can skip to the section [Enable your iOS or Android app for app protection policy](#enable-your-iOS-or-Android-app-for-app-protection-policy).</span></span>

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a><span data-ttu-id="30d6b-114">Apple App Store や Google Play などのパブリック アプリ ストアにアプリをリリースする場合:</span><span class="sxs-lookup"><span data-stu-id="30d6b-114">If your app will be released to a public app store, like the Apple App Store or Google Play:</span></span>

<span data-ttu-id="30d6b-115">最初に Microsoft Intune にアプリを登録し、登録規約に同意する_**必要があります**_。</span><span class="sxs-lookup"><span data-stu-id="30d6b-115">You _**must**_ first register your app with Microsoft Intune and agree to the registration terms.</span></span> <span data-ttu-id="30d6b-116">その後、IT 管理者はアプリ保護ポリシーを対応アプリに適用できるようになり、そのアプリは Intune アプリ パートナーとしてリストされます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-116">IT administrators can then apply app protection policy to the enlightened app, which will be listed as an Intune app partner.</span></span>

<span data-ttu-id="30d6b-117">登録が完了し、Microsoft Intune チームによって確認されるまで、Intune 管理者はアプリ保護ポリシーをアプリのディープ リンクに適用できません。</span><span class="sxs-lookup"><span data-stu-id="30d6b-117">Until registration has been finished and confirmed by the Microsoft Intune team, Intune administrators will not have the option to apply app protection policy to your app's deep link.</span></span> <span data-ttu-id="30d6b-118">アプリは、[Microsoft Intune パートナーのページ](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)にも追加されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-118">Microsoft will also add your app to its [Microsoft Intune Partners page](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).</span></span> <span data-ttu-id="30d6b-119">ここには、Intune のアプリ保護ポリシーに対応していることを示すアプリのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-119">There, the app's icon will be displayed to show that it supports Intune app protection policies.</span></span>

<span data-ttu-id="30d6b-120">登録プロセスを開始するには、[Microsoft Intune アプリ パートナー アンケート](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)に記入します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-120">To begin the registration process, fill out the [Microsoft Intune App Partner Questionnaire](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).</span></span>

<span data-ttu-id="30d6b-121">Microsoft が、アンケートに入力された電子メール アドレスを使用してご連絡し、登録プロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-121">We will use the email addresses listed in your questionnaire response to reach out and continue the registration process.</span></span> <span data-ttu-id="30d6b-122">また、何らかの問題が発生した場合の連絡にも、登録電子メール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-122">Additionally, we use your registration email address to contact you if we have any concerns.</span></span>

> [!NOTE]
> <span data-ttu-id="30d6b-123">アンケートおよび Microsoft Intune チームとの電子メール通信で収集されたすべての情報は、[Microsoft のプライバシーに関する声明](https://www.microsoft.com/privacystatement/default.aspx)に従って処理されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-123">All information collected in the questionnaire and through email correspondence with the Microsoft Intune team will honor the [Microsoft Privacy Statement](https://www.microsoft.com/privacystatement/default.aspx).</span></span>

<span data-ttu-id="30d6b-124">**登録プロセスの流れ**:</span><span class="sxs-lookup"><span data-stu-id="30d6b-124">**What to expect in the registration process**:</span></span>

1. <span data-ttu-id="30d6b-125">アンケートを送信すると、正常に受信したことを確認するか、または登録を完了するための追加情報を要求する目的で、Microsoft から登録電子メール アドレスにご連絡します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-125">After you have submitted the questionnaire, we will contact you via your registration email address, to either confirm successful receipt or request additional information to finish the registration.</span></span>

2. <span data-ttu-id="30d6b-126">必要な情報をすべて受け取った後、Microsoft は署名のために Microsoft Intune アプリ パートナー契約をお送りします。</span><span class="sxs-lookup"><span data-stu-id="30d6b-126">After we receive all necessary information from you, we will send you the Microsoft Intune App Partner Agreement to sign.</span></span> <span data-ttu-id="30d6b-127">この契約には、Microsoft Intune アプリ パートナーになる上でお客様の会社が同意する必要のある条項が記載されています。</span><span class="sxs-lookup"><span data-stu-id="30d6b-127">This agreement describes the terms that your company must accept before it becomes a Microsoft Intune app partner.</span></span>

3. <span data-ttu-id="30d6b-128">また、アプリが正常に Microsoft Intune サービスに登録されたり、アプリが [Microsoft Intune パートナー](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)のサイトで推奨されたりした場合にも連絡があります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-128">You will be notified when your app is successfully registered with the Microsoft Intune service and when your app is featured on the [Microsoft Intune partners](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) site.</span></span>

4. <span data-ttu-id="30d6b-129">最後に、アプリのディープ リンクが、次の月の Intune サービス更新に追加されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-129">Finally, your app's deep link will be added to the next monthly Intune Service update.</span></span> <span data-ttu-id="30d6b-130">たとえば、7 月に登録情報を完了した場合、ディープ リンクのサポートは 8 月中旬になります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-130">For example, if the registration information is finished in July, the deep link will be supported in mid-August.</span></span>

<span data-ttu-id="30d6b-131">アプリのディープ リンクを今後変更する場合は、アプリを再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-131">If your app's deep link changes in the future, you will need to re-register your app.</span></span>

> [!NOTE]
> <span data-ttu-id="30d6b-132">新しいバージョンの Intune アプリ SDK を使用してアプリを更新する場合には、ご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="30d6b-132">Please inform us if you update your app with a new version of the Intune App SDK.</span></span>



## <a name="download-the-sdk-files"></a><span data-ttu-id="30d6b-133">SDK ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="30d6b-133">Download the SDK files</span></span>

<span data-ttu-id="30d6b-134">ネイティブ iOS 用および Android 用の Intune アプリ SDK は、Microsoft GitHub アカウントでホストされています。</span><span class="sxs-lookup"><span data-stu-id="30d6b-134">The Intune App SDKs for native iOS and Android are hosted on a Microsoft GitHub account.</span></span> <span data-ttu-id="30d6b-135">ネイティブ iOS 用および Android 用の SDK ファイルは、それぞれ以下のパブリック リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-135">These public repositories have the SDK files for native iOS and Android, respectively:</span></span>

* [<span data-ttu-id="30d6b-136">iOS 用 Intune App SDK</span><span class="sxs-lookup"><span data-stu-id="30d6b-136">Intune App SDK for iOS</span></span>](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [<span data-ttu-id="30d6b-137">Android 用 Intune アプリ SDK</span><span class="sxs-lookup"><span data-stu-id="30d6b-137">Intune App SDK for Android</span></span>](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

<span data-ttu-id="30d6b-138">アプリが Xamarin アプリまたは Cordova アプリの場合は、次の SDK バリアントを使用してください。</span><span class="sxs-lookup"><span data-stu-id="30d6b-138">If your app is a Xamarin or Cordova app, please use these SDK variants:</span></span>

* [<span data-ttu-id="30d6b-139">Intune App SDK Xamarin コンポーネント</span><span class="sxs-lookup"><span data-stu-id="30d6b-139">Intune App SDK Xamarin Component</span></span>](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [<span data-ttu-id="30d6b-140">Intune App SDK Cordova プラグイン</span><span class="sxs-lookup"><span data-stu-id="30d6b-140">Intune App SDK Cordova Plugin</span></span>](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

<span data-ttu-id="30d6b-141">リポジトリのフォークとプルに使用できる GitHub アカウントにサインアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="30d6b-141">It's a good idea to sign up for a GitHub account that you can use to fork and pull from our repositories.</span></span> <span data-ttu-id="30d6b-142">GitHub では、Microsoft 製品チームとのやり取り、問題の提出と迅速な応答、リリース ノートの表示、Microsoft へのフィードバックの提供が可能です。</span><span class="sxs-lookup"><span data-stu-id="30d6b-142">GitHub lets developers communicate with our product team, open issues and receive quick responses, view release notes, and provide feedback to Microsoft.</span></span> <span data-ttu-id="30d6b-143">Intune アプリ SDK GitHub についてご不明な点がある場合は、msintuneappsdk@microsoft.com にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="30d6b-143">For questions on the Intune App SDK GitHub, contact msintuneappsdk@microsoft.com.</span></span>





## <a name="enable-your-ios-or-android-app-for-app-protection-policy"></a><span data-ttu-id="30d6b-144">アプリ保護ポリシーに対して iOS または Android アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="30d6b-144">Enable your iOS or Android app for app protection policy</span></span>

<span data-ttu-id="30d6b-145">以下の開発者ガイドのいずれかが必要になります。これらは、Intune アプリ SDK をご使用のアプリに統合するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-145">You will need one of the following developer guides to help you integrate the Intune App SDK into your app:</span></span>

* <span data-ttu-id="30d6b-146">**[iOS 用 Intune アプリ SDK 開発者ガイド](app-sdk-ios.md)**: このドキュメントでは、Intune アプリ SDK を使用したネイティブ iOS アプリを有効にする方法について、段階的に説明しています。</span><span class="sxs-lookup"><span data-stu-id="30d6b-146">**[Intune App SDK for iOS Developer Guide](app-sdk-ios.md)**: This document will walk you step-by-step through enabling your native iOS app with the Intune App SDK.</span></span>

* <span data-ttu-id="30d6b-147">**[Android 用 Intune アプリ SDK 開発者ガイド](app-sdk-android.md)**: このドキュメントでは、Intune アプリ SDK を使用したネイティブ Android アプリを有効にする方法について、段階的に説明しています。</span><span class="sxs-lookup"><span data-stu-id="30d6b-147">**[Intune App SDK for Android Developer Guide](app-sdk-android.md)**: This document will walk you step-by-step through enabling your native Android app with the Intune App SDK.</span></span>

* <span data-ttu-id="30d6b-148">**[Intune App SDK Cordova プラグイン ガイド](app-sdk-cordova.md)**: このドキュメントは、iOS アプリと Android アプリを Cordova を使用してビルドし、Intune アプリ保護ポリシーを適用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-148">**[Intune App SDK Cordova Plugin guide](app-sdk-cordova.md)**: This document will help you build iOS and Android apps using Cordova for Intune app protection policies.</span></span>

* <span data-ttu-id="30d6b-149">**[Intune App SDK Xamarin コンポーネント ガイド](app-sdk-xamarin.md)**: このドキュメントは、iOS アプリと Android アプリを Cordova を使用してビルドし、Intune アプリ保護ポリシーを適用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-149">**[Intune App SDK Xamarin Component guide](app-sdk-xamarin.md)**: This document will help you build iOS and Android apps using Cordova for Intune app protection policies.</span></span>



## <a name="enable-your-ios-or-android-app-for-app-based-conditional-access"></a><span data-ttu-id="30d6b-150">アプリ ベースの条件付きアクセスに対して iOS または Android アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="30d6b-150">Enable your iOS or Android app for app based conditional access</span></span>
 
 <span data-ttu-id="30d6b-151">アプリの保護ポリシーに対してアプリを有効することに加えて、Azure Active Directory (AAD) アプリ ベースの条件付きアクセスでアプリが正常に機能するには、次の条件が必須です。</span><span class="sxs-lookup"><span data-stu-id="30d6b-151">In addition to enabling your app for app protection policy, the following is required for your app to properly function with Azure ActiveDirectory (AAD) app based conditional access:</span></span>
 
 * <span data-ttu-id="30d6b-152">アプリのビルドには [Azure Active Directory Authentication Library](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-authentication-libraries) が使用されていて、AAD ブローカー認証に対してアプリが有効になっている。</span><span class="sxs-lookup"><span data-stu-id="30d6b-152">App is built with the [Azure ActiveDirectory Authentication Library](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-authentication-libraries) and enabled for AAD broker authentication.</span></span>
 
 * <span data-ttu-id="30d6b-153">アプリの [AAD クライアント ID](https://docs.microsoft.com/en-us/azure/app-service/app-service-mobile-how-to-configure-active-directory-authentication#optional-configure-a-native-client-application) は、iOS および Android のプラットフォーム全体で一意である必要がある。</span><span class="sxs-lookup"><span data-stu-id="30d6b-153">The [AAD Client ID](https://docs.microsoft.com/en-us/azure/app-service/app-service-mobile-how-to-configure-active-directory-authentication#optional-configure-a-native-client-application) for your app must be unique across iOS and Android platforms.</span></span>
 
 
 

## <a name="configure-telemetry-for-your-app"></a><span data-ttu-id="30d6b-154">アプリの製品利用統計情報を構成する</span><span class="sxs-lookup"><span data-stu-id="30d6b-154">Configure Telemetry for your app</span></span>

<span data-ttu-id="30d6b-155">Microsoft Intune はアプリの利用統計データを収集します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-155">Microsoft Intune collects data on usage statistics for your app.</span></span>

* <span data-ttu-id="30d6b-156">**iOS 用 Intune アプリ SDK**: SDK により、既定では、使用状況イベントに関する SDK 製品利用統計情報がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-156">**Intune App SDK for iOS**: The SDK logs SDK telemetry data on usage events by default.</span></span> <span data-ttu-id="30d6b-157">このデータは、Microsoft Intune に送信されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-157">This data is sent to Microsoft Intune.</span></span>

    * <span data-ttu-id="30d6b-158">アプリから SDK の製品利用統計情報を Microsoft Intune に送信しない場合は、IntuneMAMSettings ディレクトリのプロパティ `MAMTelemetryDisabled` を "YES" に設定して、製品利用統計情報の送信を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-158">If you choose not to send SDK telemetry data to Microsoft Intune from your app, you must disable telemetry transmission by setting the property `MAMTelemetryDisabled` to "YES" in the IntuneMAMSettings dictionary.</span></span>

* <span data-ttu-id="30d6b-159">**Android 用 Intune アプリ SDK**: SDK によって製品利用統計情報データがログに記録されることはありません。</span><span class="sxs-lookup"><span data-stu-id="30d6b-159">**Intune App SDK for Android**: Telemetry data is not logged through the SDK.</span></span>

  <span data-ttu-id="30d6b-160">iOS と Android の基幹業務アプリのバージョン番号が表示可能 <!-- 1380712 --></span><span class="sxs-lookup"><span data-stu-id="30d6b-160">iOS and Android line-of-business app version number is visible <!-- 1380712 --></span></span>

## <a name="line-of-business-app-version-numbers"></a><span data-ttu-id="30d6b-161">基幹業務アプリのバージョン番号</span><span class="sxs-lookup"><span data-stu-id="30d6b-161">Line-of-business app version numbers</span></span>

<span data-ttu-id="30d6b-162">Intune では、iOS アプリと Android アプリを対象に、基幹業務アプリのバージョン番号が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="30d6b-162">Line-of-business apps in Intune now display the version number for iOS and Android apps.</span></span> <span data-ttu-id="30d6b-163">Azure Portal のアプリ一覧とアプリ概要ブレードで番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-163">The number displays in the Azure portal in the app list and in the app overview blade.</span></span> <span data-ttu-id="30d6b-164">エンド ユーザーは、ポータル サイト アプリと Web ポータルでアプリ番号を確認できます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-164">End users can see the app number in the Company Portal app and in the web portal.</span></span>

### <a name="full-version-number"></a><span data-ttu-id="30d6b-165">バージョン番号 (フル)</span><span class="sxs-lookup"><span data-stu-id="30d6b-165">Full version number</span></span>

<span data-ttu-id="30d6b-166">バージョン番号 (フル) は、アプリのリリースを特定する番号です。</span><span class="sxs-lookup"><span data-stu-id="30d6b-166">The full version number identifies a specific release of the app.</span></span> <span data-ttu-id="30d6b-167">この番号は _バージョン_(_ビルド_) の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-167">The number appears as _Version_(_Build_).</span></span> <span data-ttu-id="30d6b-168">たとえば、2.2(2.2.17560800) のようになります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-168">For example, 2.2(2.2.17560800)</span></span>

<span data-ttu-id="30d6b-169">バージョン番号 (フル) を構成する 2 つの要素:</span><span class="sxs-lookup"><span data-stu-id="30d6b-169">The full version number has two components:</span></span>

 - <span data-ttu-id="30d6b-170">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="30d6b-170">**Version**</span></span>  
   <span data-ttu-id="30d6b-171">バージョン番号は、人間が判読できるアプリのリリース番号です。</span><span class="sxs-lookup"><span data-stu-id="30d6b-171">The version number is the human-readable release number of the app.</span></span> <span data-ttu-id="30d6b-172">エンド ユーザーがアプリの各種リリースを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-172">This is used by end users to identify different releases of the app.</span></span>

 - <span data-ttu-id="30d6b-173">**ビルド番号**</span><span class="sxs-lookup"><span data-stu-id="30d6b-173">**Build Number**</span></span>  
    <span data-ttu-id="30d6b-174">ビルド番号は、アプリの検出に利用される内部番号です。また、プログラミングでアプリを管理するために利用されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-174">The build number is an internal number that can be used in app detection and to programmatically manage the app.</span></span> <span data-ttu-id="30d6b-175">ビルド番号は、コードの変更を参照するアプリのイテレーションを参照します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-175">The build number refers to an iteration of the app that references changes in the code.</span></span>

### <a name="version-and-build-number-in-android-and-ios"></a><span data-ttu-id="30d6b-176">Android と iOS のバージョンおよびビルド番号</span><span class="sxs-lookup"><span data-stu-id="30d6b-176">Version and build number in Android and iOS</span></span>

<span data-ttu-id="30d6b-177">Android と iOS はいずれもバージョンおよびビルド番号を利用してアプリを参照します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-177">Android and iOS both use version and build numbers in reference to apps.</span></span> <span data-ttu-id="30d6b-178">ただし、オペレーティング システムには OS 固有の意味があります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-178">However, both operating systems have meanings that are OS-specific.</span></span> <span data-ttu-id="30d6b-179">次の表で以上の用語の関連性を説明します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-179">The following table explains how these terms are related.</span></span>

<span data-ttu-id="30d6b-180">Intune で使用する基幹業務アプリを開発するときは、バージョン番号とビルド番号の両方を必ず使用してください。</span><span class="sxs-lookup"><span data-stu-id="30d6b-180">When you are developing a line-of-business application for use in Intune, remember to use both the version and the build number.</span></span> <span data-ttu-id="30d6b-181">Intune のアプリ管理機能では、意味のある **CFBundleVersion** (iOS の場合) と **PackageVersionCode** (Android の場合) が利用されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-181">Intune App management features rely on a meaningful **CFBundleVersion** (for iOS) and **PackageVersionCode** (for Android).</span></span> <span data-ttu-id="30d6b-182">これらの番号はアプリ マニフェストに含まれます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-182">These numbers are included in the app manifest.</span></span> 

<span data-ttu-id="30d6b-183">Intune</span><span class="sxs-lookup"><span data-stu-id="30d6b-183">Intune</span></span>|<span data-ttu-id="30d6b-184">iOS</span><span class="sxs-lookup"><span data-stu-id="30d6b-184">iOS</span></span>|<span data-ttu-id="30d6b-185">Android</span><span class="sxs-lookup"><span data-stu-id="30d6b-185">Android</span></span>|<span data-ttu-id="30d6b-186">説明</span><span class="sxs-lookup"><span data-stu-id="30d6b-186">Description</span></span>|
|---|---|---|---|
<span data-ttu-id="30d6b-187">バージョン番号</span><span class="sxs-lookup"><span data-stu-id="30d6b-187">Version number</span></span>|<span data-ttu-id="30d6b-188">CFBundleShortVersionString</span><span class="sxs-lookup"><span data-stu-id="30d6b-188">CFBundleShortVersionString</span></span>|<span data-ttu-id="30d6b-189">PackageVersionName</span><span class="sxs-lookup"><span data-stu-id="30d6b-189">PackageVersionName</span></span> |<span data-ttu-id="30d6b-190">この番号は、エンド ユーザー向けにアプリの特定のリリースを示します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-190">This number indicates a specific release of the app for end users.</span></span>|
<span data-ttu-id="30d6b-191">［ビルド番号］</span><span class="sxs-lookup"><span data-stu-id="30d6b-191">Build number</span></span>|<span data-ttu-id="30d6b-192">CFBundleVersion</span><span class="sxs-lookup"><span data-stu-id="30d6b-192">CFBundleVersion</span></span>|<span data-ttu-id="30d6b-193">PackageVersionCode</span><span class="sxs-lookup"><span data-stu-id="30d6b-193">PackageVersionCode</span></span> |<span data-ttu-id="30d6b-194">この番号は、アプリ コードのイテレーションを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-194">This number is used to indicate an iteration in the app code.</span></span>|

#### <a name="ios"></a><span data-ttu-id="30d6b-195">iOS</span><span class="sxs-lookup"><span data-stu-id="30d6b-195">iOS</span></span>

- <span data-ttu-id="30d6b-196">**CFBundleShortVersionString**</span><span class="sxs-lookup"><span data-stu-id="30d6b-196">**CFBundleShortVersionString**</span></span>  
    <span data-ttu-id="30d6b-197">バンドルのリリース バージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-197">Specifies the release version number of the bundle.</span></span> <span data-ttu-id="30d6b-198">この番号でアプリのリリース バージョンが識別されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-198">This number identifies a released version of the app.</span></span> <span data-ttu-id="30d6b-199">この番号はエンド ユーザーがアプリを参照するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-199">The number is used by end users to reference the app.</span></span> 
  - <span data-ttu-id="30d6b-200">**CFBundleVersion**</span><span class="sxs-lookup"><span data-stu-id="30d6b-200">**CFBundleVersion**</span></span>  
    <span data-ttu-id="30d6b-201">バンドルのビルド バージョン。バンドルのイテレーションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-201">The build version of the bundle, which identifies an iteration of the bundle.</span></span> <span data-ttu-id="30d6b-202">この番号でリリース バンドルまたは未リリース バンドルが識別されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-202">The number may be identify a release or unreleased bundle.</span></span> <span data-ttu-id="30d6b-203">この番号はアプリの検出に利用されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-203">The number is used for app detection.</span></span>

#### <a name="android"></a><span data-ttu-id="30d6b-204">Android</span><span class="sxs-lookup"><span data-stu-id="30d6b-204">Android</span></span>

 - <span data-ttu-id="30d6b-205">**PackageVersionName**</span><span class="sxs-lookup"><span data-stu-id="30d6b-205">**PackageVersionName**</span></span>  
    <span data-ttu-id="30d6b-206">ユーザーに表示されるバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="30d6b-206">The version number shown to users.</span></span> <span data-ttu-id="30d6b-207">この属性は、生文字列として、または文字列リソースの参照として設定できます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-207">This attribute can be set as a raw string or as a reference to a string resource.</span></span> <span data-ttu-id="30d6b-208">この文字列には、ユーザーに表示する以外の目的はありません。</span><span class="sxs-lookup"><span data-stu-id="30d6b-208">The string has no other purpose than to be displayed to users.</span></span>
 - <span data-ttu-id="30d6b-209">**PackageVersionCode**</span><span class="sxs-lookup"><span data-stu-id="30d6b-209">**PackageVersionCode**</span></span>  
    <span data-ttu-id="30d6b-210">内部バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="30d6b-210">An internal version number.</span></span> <span data-ttu-id="30d6b-211">この番号は、ある番号が別の番号より新しいかどうかを判断するためにのみ利用されます。番号が大きければ、より新しいバージョンとなります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-211">This number is used only to determine whether one version is more recent than another, with higher numbers indicating more recent versions.</span></span> <span data-ttu-id="30d6b-212">これはバージョンではありません。</span><span class="sxs-lookup"><span data-stu-id="30d6b-212">This is not the version</span></span> 

## <a name="next-steps-after-integration"></a><span data-ttu-id="30d6b-213">統合後の次の手順</span><span class="sxs-lookup"><span data-stu-id="30d6b-213">Next steps after integration</span></span>

### <a name="test-your-app"></a><span data-ttu-id="30d6b-214">アプリのテスト</span><span class="sxs-lookup"><span data-stu-id="30d6b-214">Test your app</span></span>
<span data-ttu-id="30d6b-215">iOS または Android アプリを Intune アプリ SDK と統合するために必要な手順を完了した後、すべてのアプリ保護ポリシーが、ユーザーと IT 管理者に対して有効化され、機能していることを確認する必要があります。統合されたアプリをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-215">After you finish the necessary steps to integrate your iOS or Android app with the Intune App SDK, you will need to ensure that all the app protection policies are enabled and functioning for the user and the IT admin. To test your integrated app, you will need the following:</span></span>

* <span data-ttu-id="30d6b-216">**Microsoft Intune のテスト アカウント**: Intune アプリ保護機能に対して Intune 対応アプリをテストするには、Microsoft Intune のアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="30d6b-216">**Microsoft Intune test account**: To test your Intune-enlightened app against Intune app protection features, you will need a Microsoft Intune account.</span></span>

    * <span data-ttu-id="30d6b-217">Intune アプリ保護ポリシーに対して iOS または Android ストア アプリを有効化している ISV の場合は、登録ステップで説明した Microsoft Intune での登録が完了すると、プロモーション コードを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-217">If you are an ISV enabling your iOS or Android store apps for Intune app protection policy, you will receive a promo code after you finish the registration with Microsoft Intune, as outlined in the registration step.</span></span> <span data-ttu-id="30d6b-218">プロモーション コードを使用すると、Microsoft Intune の 1 年間の拡張使用試用版にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-218">The promo code will let you sign up for a Microsoft Intune trial for one year of extended use.</span></span>

    * <span data-ttu-id="30d6b-219">ストアに出荷されない基幹業務アプリを開発している場合は、組織を介して Microsoft Intune へのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-219">If you are developing a line-of-business app that will not be shipped to the store, you are expected to have access to Microsoft Intune through your organization.</span></span> <span data-ttu-id="30d6b-220">この場合も、[Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) で、1 か月間の無料試用版にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-220">You can also sign up for a one-month free trial in [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).</span></span>

* <span data-ttu-id="30d6b-221">**Intune のアプリ保護ポリシー**: Intune のすべてのアプリ保護ポリシーに対して、ご使用のアプリをテストするには、ポリシー設定ごとに想定される動作を把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-221">**Intune app protection policies**: To test your app against all the Intune app protection policies, you should know what the expected behavior is for each policy setting.</span></span> <span data-ttu-id="30d6b-222">[iOS アプリ保護ポリシー](/intune-classic/deploy-use/ios-mam-policy-settings)と [Android アプリ保護ポリシー](/intune-classic/deploy-use/android-mam-policy-settings)の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30d6b-222">See the descriptions for [iOS app protection policies](/intune-classic/deploy-use/ios-mam-policy-settings) and [Android app protection policies](/intune-classic/deploy-use/android-mam-policy-settings).</span></span>

* <span data-ttu-id="30d6b-223">**トラブルシューティング**: アプリのユーザー操作を手動でテストしているときに問題が発生した場合は、「[モバイル アプリケーション管理に関するトラブルシューティング](/intune-classic/troubleshoot/troubleshoot-mam)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="30d6b-223">**Troubleshoot**: If you run into any issues while manually testing your app's user experience, check out the [Troubleshooting MAM](/intune-classic/troubleshoot/troubleshoot-mam).</span></span> <span data-ttu-id="30d6b-224">この記事では、Intune 対応アプリで発生する可能性のある一般的な問題と表示されるダイアログおよびエラー メッセージについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="30d6b-224">This article offers help for common issues, dialogs, and error messages that may be experienced in Intune-enlightened apps.</span></span> 

### <a name="badge-your-app-optional"></a><span data-ttu-id="30d6b-225">アプリにバッジを付ける (省略可能)</span><span class="sxs-lookup"><span data-stu-id="30d6b-225">Badge your app (optional)</span></span>

<span data-ttu-id="30d6b-226">Intune アプリ保護ポリシーがアプリで機能していることを確認したら、アプリ アイコンに Intune アプリ保護ロゴ バッジを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-226">After validating that Intune app protection policies work in your app, you can badge your app icon with the Intune app protection logo.</span></span>

<span data-ttu-id="30d6b-227">このバッジは、アプリに Intune アプリ保護ポリシーが適用されていることを、IT 管理者、エンド ユーザー、および Intune の見込み顧客に示すものです。</span><span class="sxs-lookup"><span data-stu-id="30d6b-227">This badge indicates to IT administrators, end-users, and potential Intune customers that your app works with Intune app protection policies.</span></span> <span data-ttu-id="30d6b-228">Intune の顧客によるアプリの使用と採用を促します。</span><span class="sxs-lookup"><span data-stu-id="30d6b-228">It encourages the usage and adoption of your app by Intune customers.</span></span>

<span data-ttu-id="30d6b-229">ブリーフケース アイコンのバッジは、次のサンプルのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="30d6b-229">The badge is a briefcase icon and can be seen in the samples below:</span></span>

![バッジの例 1](./media/badge-example-1.png) ![バッジの例 2](./media/badge-example-2.png)

<span data-ttu-id="30d6b-232">**アプリにバッジを付けるために必要なもの**:</span><span class="sxs-lookup"><span data-stu-id="30d6b-232">**What you'll need to badge your app**:</span></span>

* <span data-ttu-id="30d6b-233">**.eps** ファイルを読み取れるイメージ操作アプリケーション、または **.ai** ファイルを読み取れる Adobe アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="30d6b-233">An image manipulation application that can read **.eps** files, or an Adobe application that can read **.ai** files.</span></span>

* <span data-ttu-id="30d6b-234">[Intune アプリ バッジのアセットとガイドライン](https://github.com/msintuneappsdk/intune-app-partner-badge)は、Microsoft Intune GitHub にあります。</span><span class="sxs-lookup"><span data-stu-id="30d6b-234">You can find the [Intune app badge assets and guidelines](https://github.com/msintuneappsdk/intune-app-partner-badge) on the Microsoft Intune GitHub.</span></span>
