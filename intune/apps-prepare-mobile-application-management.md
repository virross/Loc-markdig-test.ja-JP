---
title: "Microsoft Intune によるモバイル アプリケーション管理のためにアプリを準備する方法を決める"
description: "このトピックの情報は、カスタム基幹業務アプリでモバイル アプリ管理ポリシーを使用できるようにするために、アプリ ラッピング ツールとアプリ SDK を使用するタイミングを判断するときに役立ちます。"
keywords: 
author: mattbriggs
ms.author: mabriggs
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2d494dd0270cddac8ec449689357616c3ac7c48b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="prepare-line-of-business-apps-for-app-protection-policies"></a><span data-ttu-id="06aba-103">アプリ保護ポリシーを利用するために基幹業務アプリで準備を行う</span><span class="sxs-lookup"><span data-stu-id="06aba-103">Prepare line-of-business apps for app protection policies</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="06aba-104">Intune アプリ ラッピング ツールまたは Intune アプリ SDK のどちらかを使って、アプリでアプリ保護ポリシーを使えるようにできます。</span><span class="sxs-lookup"><span data-stu-id="06aba-104">You can enable your apps to use app protection policies by using either the Intune App Wrapping Tool or the Intune App SDK.</span></span> <span data-ttu-id="06aba-105">ここでは、これら 2 つの方法の内容と用途について説明します。</span><span class="sxs-lookup"><span data-stu-id="06aba-105">Use this information to learn about these two methods and when to use them.</span></span>

## <a name="intune-app-wrapping-tool"></a><span data-ttu-id="06aba-106">Intune アプリ ラッピング ツール</span><span class="sxs-lookup"><span data-stu-id="06aba-106">Intune App Wrapping Tool</span></span>
<span data-ttu-id="06aba-107">アプリ ラッピング ツールは、主として、内部基幹業務 (LOB) アプリケーションに使います。</span><span class="sxs-lookup"><span data-stu-id="06aba-107">The App Wrapping Tool is used primarily for internal line-of-business (LOB) apps.</span></span> <span data-ttu-id="06aba-108">このツールは、アプリのラッパーを作成するコマンド ライン アプリケーションです。このラッパーにより、アプリを Intune アプリ保護ポリシーで管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="06aba-108">The tool is a command-line application that creates a wrapper around the app, which then allows the app to be managed by an Intune app protection policy.</span></span>

<span data-ttu-id="06aba-109">このツールを使うためにソース コードは必要ありませんが、署名資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="06aba-109">You don't need the source code to use the tool, but you do need signing credentials.</span></span> <span data-ttu-id="06aba-110">署名資格情報の詳細については、[Intune のブログ](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06aba-110">For more about signing credentials, see the [Intune blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/).</span></span> <span data-ttu-id="06aba-111">アプリ ラッピング ツールのドキュメントとしては、[Android アプリ ラッピング ツール](app-wrapper-prepare-android.md)と [iOS アプリ ラッピング ツール](app-wrapper-prepare-ios.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="06aba-111">For the App Wrapping Tool documentation, see [Android App Wrapping Tool ](app-wrapper-prepare-android.md) and [iOS App Wrapping Tool](app-wrapper-prepare-ios.md).</span></span>

<span data-ttu-id="06aba-112">アプリ ラッピング ツールは、Apple App Store または Google Play ストアのアプリを**サポートしていません**。</span><span class="sxs-lookup"><span data-stu-id="06aba-112">The App Wrapping Tool does **not** support apps in the Apple App Store or Google Play Store.</span></span> <span data-ttu-id="06aba-113">また、開発ツールの統合が必要な一部の機能もサポートしていません (次の機能比較表を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="06aba-113">It also doesn't support certain features that require developer integration (see the following feature comparison table).</span></span>


<span data-ttu-id="06aba-114">Intune に登録されていないデバイスのアプリ保護ポリシー用アプリ ラッピング ツールの詳細については、「[Microsoft Intune に登録されていないデバイスの基幹業務アプリとデータを保護する](/intune-classic/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06aba-114">For more information about the App Wrapping Tool for app protection policies on devices that are not enrolled in Intune, see [Protect line-of-business apps and data on devices not enrolled in Microsoft Intune](/intune-classic/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune).</span></span>

### <a name="reasons-to-use-the-app-wrapping-tool"></a><span data-ttu-id="06aba-115">アプリ ラッピング ツールを使用する理由</span><span class="sxs-lookup"><span data-stu-id="06aba-115">Reasons to use the App Wrapping Tool</span></span>
* <span data-ttu-id="06aba-116">アプリに組み込みのデータ保護機能がない。</span><span class="sxs-lookup"><span data-stu-id="06aba-116">Your app does not have built-in data protection features</span></span>
* <span data-ttu-id="06aba-117">アプリが単純である。</span><span class="sxs-lookup"><span data-stu-id="06aba-117">Your app is simple</span></span>
* <span data-ttu-id="06aba-118">アプリが内部的に展開される。</span><span class="sxs-lookup"><span data-stu-id="06aba-118">Your app is deployed internally</span></span>
* <span data-ttu-id="06aba-119">アプリのソース コードにアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="06aba-119">You don't have access to the app's source code</span></span>
* <span data-ttu-id="06aba-120">自分で開発したアプリではない。</span><span class="sxs-lookup"><span data-stu-id="06aba-120">You didn't develop the app</span></span>
* <span data-ttu-id="06aba-121">アプリのユーザー認証エクスペリエンスが最小限である。</span><span class="sxs-lookup"><span data-stu-id="06aba-121">Your app has minimal user authentication experiences</span></span>


### <a name="supported-app-development-platforms"></a><span data-ttu-id="06aba-122">サポートされるアプリ開発プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="06aba-122">Supported app development platforms</span></span>

|<span data-ttu-id="06aba-123">**アプリ ラッピング ツール**</span><span class="sxs-lookup"><span data-stu-id="06aba-123">**App Wrapping Tool**</span></span> | <span data-ttu-id="06aba-124">**Xamarin**</span><span class="sxs-lookup"><span data-stu-id="06aba-124">**Xamarin**</span></span> |<span data-ttu-id="06aba-125">**Cordova**</span><span class="sxs-lookup"><span data-stu-id="06aba-125">**Cordova**</span></span> |
|------|----|----|
|<span data-ttu-id="06aba-126">**iOS**</span><span class="sxs-lookup"><span data-stu-id="06aba-126">**iOS**</span></span> |<span data-ttu-id="06aba-127">Yes</span><span class="sxs-lookup"><span data-stu-id="06aba-127">Yes</span></span>|<span data-ttu-id="06aba-128">Yes</span><span class="sxs-lookup"><span data-stu-id="06aba-128">Yes</span></span>|
|<span data-ttu-id="06aba-129">**Android**</span><span class="sxs-lookup"><span data-stu-id="06aba-129">**Android**</span></span>| <span data-ttu-id="06aba-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="06aba-130">No</span></span> |<span data-ttu-id="06aba-131">Yes</span><span class="sxs-lookup"><span data-stu-id="06aba-131">Yes</span></span>|

## <a name="intune-app-sdk"></a><span data-ttu-id="06aba-132">Intune App SDK</span><span class="sxs-lookup"><span data-stu-id="06aba-132">Intune App SDK</span></span>
<span data-ttu-id="06aba-133">App SDK は、主として、Apple App Store または Google Play ストアにあるアプリを Intune で管理できるようにするお客様向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="06aba-133">The App SDK is designed mainly for customers who have apps in the Apple App Store or Google Play Store, and want to be able to manage the apps with Intune.</span></span> <span data-ttu-id="06aba-134">ただし、どのようなアプリでも (基幹業務アプリでさえ)、SDK の統合を利用できます。</span><span class="sxs-lookup"><span data-stu-id="06aba-134">However, any app can take advantage of integrating the SDK, even line-of-business apps.</span></span>

<span data-ttu-id="06aba-135">SDK の詳細については、「[概要](app-sdk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06aba-135">To learn more about the SDK, see the [Overview](app-sdk.md).</span></span> <span data-ttu-id="06aba-136">SDK で作業を開始するには、「[Microsoft Intune App SDK を使ってみる](app-sdk-get-started.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06aba-136">To get started with the SDK, see [Getting Started With the Microsoft Intune App SDK](app-sdk-get-started.md).</span></span>

### <a name="reasons-to-use-the-sdk"></a><span data-ttu-id="06aba-137">SDK を使用する理由</span><span class="sxs-lookup"><span data-stu-id="06aba-137">Reasons to use the SDK</span></span>
* <span data-ttu-id="06aba-138">アプリに組み込みのデータ保護機能がない。</span><span class="sxs-lookup"><span data-stu-id="06aba-138">Your app does not have built-in data protection features</span></span>
* <span data-ttu-id="06aba-139">アプリが複雑で、多くのエクスペリエンスを含んでいる。</span><span class="sxs-lookup"><span data-stu-id="06aba-139">Your app is complex and contains many experiences</span></span>
* <span data-ttu-id="06aba-140">アプリが Google Play や Apple の App Store などのパブリック アプリ ストアに展開される。</span><span class="sxs-lookup"><span data-stu-id="06aba-140">Your app is deployed on a public app store such as Google Play or Apple's App Store</span></span>
* <span data-ttu-id="06aba-141">自分が開発したアプリであり、SDK を使用するための技術的な背景を備えている。</span><span class="sxs-lookup"><span data-stu-id="06aba-141">You are an app developer and have the technical background to use the SDK</span></span>
* <span data-ttu-id="06aba-142">アプリに他の SDK 統合がある。</span><span class="sxs-lookup"><span data-stu-id="06aba-142">Your app has other SDK integrations</span></span>
* <span data-ttu-id="06aba-143">アプリが頻繁に更新される。</span><span class="sxs-lookup"><span data-stu-id="06aba-143">Your app is frequently updated</span></span>

### <a name="supported-app-development-platforms"></a><span data-ttu-id="06aba-144">サポートされるアプリ開発プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="06aba-144">Supported app development platforms</span></span>

|<span data-ttu-id="06aba-145">**Intune App SDK**</span><span class="sxs-lookup"><span data-stu-id="06aba-145">**Intune App SDK**</span></span> |<span data-ttu-id="06aba-146">**Xamarin**</span><span class="sxs-lookup"><span data-stu-id="06aba-146">**Xamarin**</span></span> |<span data-ttu-id="06aba-147">**Cordova**</span><span class="sxs-lookup"><span data-stu-id="06aba-147">**Cordova**</span></span>
|------|----|----|
|<span data-ttu-id="06aba-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="06aba-148">**iOS**</span></span>|<span data-ttu-id="06aba-149">はい – [Intune App SDK Xamarin コンポーネント](app-sdk-xamarin.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="06aba-149">Yes – use the [Intune App SDK Xamarin Component](app-sdk-xamarin.md).</span></span>|<span data-ttu-id="06aba-150">はい – [Intune App SDK Cordova プラグイン](app-sdk-cordova.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="06aba-150">Yes – use the [Intune App SDK Cordova Plugin](app-sdk-cordova.md).</span></span>|
|<span data-ttu-id="06aba-151">**Android**</span><span class="sxs-lookup"><span data-stu-id="06aba-151">**Android**</span></span>| <span data-ttu-id="06aba-152">はい – [Intune App SDK Xamarin コンポーネント](app-sdk-xamarin.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="06aba-152">Yes - use the [Intune App SDK Xamarin Component](app-sdk-xamarin.md).</span></span>|<span data-ttu-id="06aba-153">はい – [Intune App SDK Cordova プラグイン](app-sdk-cordova.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="06aba-153">Yes – use the [Intune App SDK Cordova Plugin](app-sdk-cordova.md).</span></span>|

## <a name="feature-comparison"></a><span data-ttu-id="06aba-154">機能の比較</span><span class="sxs-lookup"><span data-stu-id="06aba-154">Feature comparison</span></span>
<span data-ttu-id="06aba-155">アプリ SDK とアプリ ラッピング ツールに対して利用できる設定を、次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="06aba-155">This table lists the settings that you can use for the App SDK and App Wrapping Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="06aba-156">アプリ ラッピング ツールは、スタンドアロンの Intune または Configuration Manager と統合した Intune で使用できます。</span><span class="sxs-lookup"><span data-stu-id="06aba-156">The App Wrapping Tool can be used with Intune standalone or Intune with Configuration Manager.</span></span>

|<span data-ttu-id="06aba-157">機能</span><span class="sxs-lookup"><span data-stu-id="06aba-157">Feature</span></span>|<span data-ttu-id="06aba-158">アプリ SDK</span><span class="sxs-lookup"><span data-stu-id="06aba-158">App SDK</span></span>|<span data-ttu-id="06aba-159">アプリ ラッピング ツール</span><span class="sxs-lookup"><span data-stu-id="06aba-159">App Wrapping Tool</span></span>|
|-----------|---------------------|-----------|
|<span data-ttu-id="06aba-160">[Web コンテンツを会社の管理対象ブラウザーで表示するように制限する]</span><span class="sxs-lookup"><span data-stu-id="06aba-160">Restrict web content to display in a corporate managed browser</span></span>|<span data-ttu-id="06aba-161">○</span><span class="sxs-lookup"><span data-stu-id="06aba-161">X</span></span>|<span data-ttu-id="06aba-162">○</span><span class="sxs-lookup"><span data-stu-id="06aba-162">X</span></span>|
|<span data-ttu-id="06aba-163">[Android、iTunes、iCloud のバックアップを禁止する]</span><span class="sxs-lookup"><span data-stu-id="06aba-163">Prevent Android, iTunes, or iCloud backups</span></span>|<span data-ttu-id="06aba-164">○</span><span class="sxs-lookup"><span data-stu-id="06aba-164">X</span></span>|<span data-ttu-id="06aba-165">○</span><span class="sxs-lookup"><span data-stu-id="06aba-165">X</span></span>|
|<span data-ttu-id="06aba-166">[アプリで他のアプリへのデータ転送を許可する]</span><span class="sxs-lookup"><span data-stu-id="06aba-166">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="06aba-167">○</span><span class="sxs-lookup"><span data-stu-id="06aba-167">X</span></span>|<span data-ttu-id="06aba-168">○</span><span class="sxs-lookup"><span data-stu-id="06aba-168">X</span></span>|
|<span data-ttu-id="06aba-169">[アプリで他のアプリからのデータの受信を許可する]</span><span class="sxs-lookup"><span data-stu-id="06aba-169">Allow app to receive data from other apps</span></span>|<span data-ttu-id="06aba-170">○</span><span class="sxs-lookup"><span data-stu-id="06aba-170">X</span></span>|<span data-ttu-id="06aba-171">○</span><span class="sxs-lookup"><span data-stu-id="06aba-171">X</span></span>|
|<span data-ttu-id="06aba-172">他のアプリとの間で切り取り、コピー、貼り付けを制限する</span><span class="sxs-lookup"><span data-stu-id="06aba-172">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="06aba-173">○</span><span class="sxs-lookup"><span data-stu-id="06aba-173">X</span></span>|<span data-ttu-id="06aba-174">○</span><span class="sxs-lookup"><span data-stu-id="06aba-174">X</span></span>|
|<span data-ttu-id="06aba-175">[アクセスには簡易暗証番号が必要]</span><span class="sxs-lookup"><span data-stu-id="06aba-175">Require simple PIN for access</span></span>|<span data-ttu-id="06aba-176">○</span><span class="sxs-lookup"><span data-stu-id="06aba-176">X</span></span>|<span data-ttu-id="06aba-177">○</span><span class="sxs-lookup"><span data-stu-id="06aba-177">X</span></span>|
|<span data-ttu-id="06aba-178">[組み込みアプリ PIN を Intune PIN で置き換える]</span><span class="sxs-lookup"><span data-stu-id="06aba-178">Replace built-in app PIN with Intune PIN</span></span>|<span data-ttu-id="06aba-179">○</span><span class="sxs-lookup"><span data-stu-id="06aba-179">X</span></span>||
|<span data-ttu-id="06aba-180">[PIN をリセットするまでの試行数を指定する]</span><span class="sxs-lookup"><span data-stu-id="06aba-180">Specify the number of attempts before PIN reset</span></span>|<span data-ttu-id="06aba-181">○</span><span class="sxs-lookup"><span data-stu-id="06aba-181">X</span></span>|<span data-ttu-id="06aba-182">○</span><span class="sxs-lookup"><span data-stu-id="06aba-182">X</span></span>|
|<span data-ttu-id="06aba-183">PIN の代わりに指紋を要求する</span><span class="sxs-lookup"><span data-stu-id="06aba-183">Allow fingerprint instead of PIN</span></span> |<span data-ttu-id="06aba-184">○</span><span class="sxs-lookup"><span data-stu-id="06aba-184">X</span></span>|<span data-ttu-id="06aba-185">○</span><span class="sxs-lookup"><span data-stu-id="06aba-185">X</span></span>|
|<span data-ttu-id="06aba-186">[アクセスには会社の資格情報が必要]</span><span class="sxs-lookup"><span data-stu-id="06aba-186">Require corporate credentials for access</span></span>|<span data-ttu-id="06aba-187">○</span><span class="sxs-lookup"><span data-stu-id="06aba-187">X</span></span>|<span data-ttu-id="06aba-188">○</span><span class="sxs-lookup"><span data-stu-id="06aba-188">X</span></span>|
|<span data-ttu-id="06aba-189">[脱獄またはルート化されたデバイスで管理対象アプリが実行されないようにブロックする]</span><span class="sxs-lookup"><span data-stu-id="06aba-189">Block managed apps from running on jailbroken or rooted devices</span></span>|<span data-ttu-id="06aba-190">○</span><span class="sxs-lookup"><span data-stu-id="06aba-190">X</span></span>|<span data-ttu-id="06aba-191">○</span><span class="sxs-lookup"><span data-stu-id="06aba-191">X</span></span>|
|<span data-ttu-id="06aba-192">[アプリ データの暗号化]</span><span class="sxs-lookup"><span data-stu-id="06aba-192">Encrypt app data</span></span>|<span data-ttu-id="06aba-193">○</span><span class="sxs-lookup"><span data-stu-id="06aba-193">X</span></span>|<span data-ttu-id="06aba-194">○</span><span class="sxs-lookup"><span data-stu-id="06aba-194">X</span></span>|
|<span data-ttu-id="06aba-195">[指定した時間 (分) 後にアクセス要件を再確認する]</span><span class="sxs-lookup"><span data-stu-id="06aba-195">Recheck the access requirements after a specified number of minutes</span></span>|<span data-ttu-id="06aba-196">○</span><span class="sxs-lookup"><span data-stu-id="06aba-196">X</span></span>|<span data-ttu-id="06aba-197">○</span><span class="sxs-lookup"><span data-stu-id="06aba-197">X</span></span>|
|<span data-ttu-id="06aba-198">[オフラインの猶予期間を指定する]</span><span class="sxs-lookup"><span data-stu-id="06aba-198">Specify the offline grace period</span></span>|<span data-ttu-id="06aba-199">○</span><span class="sxs-lookup"><span data-stu-id="06aba-199">X</span></span>|<span data-ttu-id="06aba-200">○</span><span class="sxs-lookup"><span data-stu-id="06aba-200">X</span></span>|
|<span data-ttu-id="06aba-201">[画面キャプチャをブロック (Android のみ)]</span><span class="sxs-lookup"><span data-stu-id="06aba-201">Block screen capture (Android only)</span></span>|<span data-ttu-id="06aba-202">○</span><span class="sxs-lookup"><span data-stu-id="06aba-202">X</span></span>|<span data-ttu-id="06aba-203">○</span><span class="sxs-lookup"><span data-stu-id="06aba-203">X</span></span>|
|<span data-ttu-id="06aba-204">デバイスの登録なしで MAM をサポート</span><span class="sxs-lookup"><span data-stu-id="06aba-204">Support for MAM without device enrollment</span></span>|<span data-ttu-id="06aba-205">○</span><span class="sxs-lookup"><span data-stu-id="06aba-205">X</span></span>|<span data-ttu-id="06aba-206">○</span><span class="sxs-lookup"><span data-stu-id="06aba-206">X</span></span>|
|<span data-ttu-id="06aba-207">完全なワイプ</span><span class="sxs-lookup"><span data-stu-id="06aba-207">Full Wipe</span></span>|<span data-ttu-id="06aba-208">○</span><span class="sxs-lookup"><span data-stu-id="06aba-208">X</span></span>|<span data-ttu-id="06aba-209">○</span><span class="sxs-lookup"><span data-stu-id="06aba-209">X</span></span>|
|<span data-ttu-id="06aba-210">選択的なワイプ</span><span class="sxs-lookup"><span data-stu-id="06aba-210">Selective Wipe</span></span> <br></br><span data-ttu-id="06aba-211">**注:** iOS では、管理プロファイルを削除するとアプリも削除されます。</span><span class="sxs-lookup"><span data-stu-id="06aba-211">**Note:** For iOS, when the management profile is removed, the app is also removed.</span></span>|<span data-ttu-id="06aba-212">○</span><span class="sxs-lookup"><span data-stu-id="06aba-212">X</span></span>||
|<span data-ttu-id="06aba-213">[[名前を付けて保存] を禁止する]</span><span class="sxs-lookup"><span data-stu-id="06aba-213">Prevent “Save as”</span></span> |<span data-ttu-id="06aba-214">○</span><span class="sxs-lookup"><span data-stu-id="06aba-214">X</span></span>||
|<span data-ttu-id="06aba-215">対象となるアプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="06aba-215">Targeted Application Configuration</span></span> |<span data-ttu-id="06aba-216">○</span><span class="sxs-lookup"><span data-stu-id="06aba-216">X</span></span>||
|<span data-ttu-id="06aba-217">[マルチ ID アプリのサポート]</span><span class="sxs-lookup"><span data-stu-id="06aba-217">Support for Multi-Identity</span></span>|<span data-ttu-id="06aba-218">○</span><span class="sxs-lookup"><span data-stu-id="06aba-218">X</span></span>||
|<span data-ttu-id="06aba-219">カスタマイズ可能なスタイル</span><span class="sxs-lookup"><span data-stu-id="06aba-219">Customizable Style</span></span> |<span data-ttu-id="06aba-220">○</span><span class="sxs-lookup"><span data-stu-id="06aba-220">X</span></span>|||
## <a name="next-steps"></a><span data-ttu-id="06aba-221">次のステップ</span><span class="sxs-lookup"><span data-stu-id="06aba-221">Next steps</span></span>

<span data-ttu-id="06aba-222">アプリ保護ポリシーと Intune の詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="06aba-222">To learn more about app protection policies and Intune, see the following topics:</span></span>

  -  [<span data-ttu-id="06aba-223">Android アプリ ラッピング ツール</span><span class="sxs-lookup"><span data-stu-id="06aba-223">Android app wrapping tool</span></span>](app-wrapper-prepare-android.md)</br>
  - [<span data-ttu-id="06aba-224">iOS アプリ ラッピング ツール</span><span class="sxs-lookup"><span data-stu-id="06aba-224">iOS app wrapping tool</span></span>](app-wrapper-prepare-ios.md)</br>
  - [<span data-ttu-id="06aba-225">SDK を使用してモバイル アプリケーション管理に対応する</span><span class="sxs-lookup"><span data-stu-id="06aba-225">Use the SDK to enable apps for mobile application management</span></span>](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)