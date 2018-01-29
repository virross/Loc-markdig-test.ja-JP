---
title: "Android 用 Microsoft Intune アプリ SDK 開発者ガイド"
description: "Android 用 Microsoft Intune アプリ SDK を使用すると、Android アプリに Intune モバイル アプリ管理 (MAM) を組み込むことができます。"
keywords: SDK
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5422d18f241a027bf6c9731a87a60470191dad77
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a><span data-ttu-id="4f338-104">Android 用 Microsoft Intune アプリ SDK 開発者ガイド</span><span class="sxs-lookup"><span data-stu-id="4f338-104">Microsoft Intune App SDK for Android developer guide</span></span>

> [!NOTE]
> <span data-ttu-id="4f338-105">まず、[Intune アプリ SDK の概要](app-sdk.md)に目を通すことをお勧めします。このガイドでは、SDK の最新機能と、サポートされる各プラットフォームで統合のための準備をする方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="4f338-105">You might want to first read the [Intune App SDK overview](app-sdk.md), which covers the current features of the SDK and describes how to prepare for integration on each supported platform.</span></span>

<span data-ttu-id="4f338-106">Android 用 Microsoft Intune アプリ SDK を使用すると、ネイティブ Android アプリに Intune アプリ保護ポリシー (**APP** または MAM ポリシー) を組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-106">The Microsoft Intune App SDK for Android lets you incorporate Intune app protection policies (also known as **APP** or MAM policies) into your native Android app.</span></span> <span data-ttu-id="4f338-107">Intune 対応アプリケーションが Intune App SDK に統合されています。</span><span class="sxs-lookup"><span data-stu-id="4f338-107">An Intune-enlightened application is one that is integrated with the Intune App SDK.</span></span> <span data-ttu-id="4f338-108">Intune で積極的にアプリを管理している場合、IT 管理者は Intune 対応アプリにアプリ保護ポリシーを簡単に展開できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-108">Intune administrators can easily deploy app protection policies to your Intune-enlightened app when Intune actively manages the app.</span></span>


## <a name="whats-in-the-sdk"></a><span data-ttu-id="4f338-109">SDK の機能</span><span class="sxs-lookup"><span data-stu-id="4f338-109">What's in the SDK</span></span>

<span data-ttu-id="4f338-110">Intune App SDK は、次のファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-110">The Intune App SDK consists of the following files:</span></span>  

* <span data-ttu-id="4f338-111">**Microsoft.Intune.MAM.SDK.aar**: Support.V4 と Support.V7 JAR ファイルを除く SDK コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4f338-111">**Microsoft.Intune.MAM.SDK.aar**: The SDK components, with the exception of the Support.V4 and Support.V7 JAR files.</span></span> <span data-ttu-id="4f338-112">このファイルは、ビルド システムが AAR ファイルをサポートしている場合、個々のコンポーネントの代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-112">This file can be used in place of the individual components if your build system supports AAR files.</span></span>
* <span data-ttu-id="4f338-113">**Microsoft.Intune.MAM.SDK.Support.v4.jar**: Android v4 サポート ライブラリを使用するアプリで MAM を有効にするために必要なインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4f338-113">**Microsoft.Intune.MAM.SDK.Support.v4.jar**: The interfaces necessary to enable MAM in apps that use the Android v4 support library.</span></span> <span data-ttu-id="4f338-114">このサポートを必要とするアプリは、JAR ファイルを直接参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-114">Apps that need this support must reference the JAR file directly.</span></span>
* <span data-ttu-id="4f338-115">**Microsoft.Intune.MAM.SDK.Support.v7.jar**: Android v7 サポート ライブラリを使用するアプリで MAM を有効にするために必要なインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4f338-115">**Microsoft.Intune.MAM.SDK.Support.v7.jar**: The interfaces necessary to enable MAM in apps that use the Android v7 support library.</span></span> <span data-ttu-id="4f338-116">このサポートを必要とするアプリは、JAR ファイルを直接参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-116">Apps that need this support must reference the JAR file directly.</span></span>
* <span data-ttu-id="4f338-117">**Microsoft.Intune.MDM.SDK.DownlevelStubs.jar**: この jar には、新しいデバイス上にのみ存在し、MAMActivity 内のメソッドによって参照される Android システム クラスのためのスタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f338-117">**Microsoft.Intune.MDM.SDK.DownlevelStubs.jar**: This jar contains stubs for Android system classes which are present only on newer devices but which are referenced by methods in MAMActivity.</span></span> <span data-ttu-id="4f338-118">新しいデバイスでは、これらのスタブ クラスを無視します。</span><span class="sxs-lookup"><span data-stu-id="4f338-118">Newer devices will ignore these stub classes.</span></span> <span data-ttu-id="4f338-119">この jar が必要になるのは、MAMActivity から派生したクラスに対してリフレクションを実行する場合のみであり、ほとんどのアプリにはこの jar を含める必要がありません。</span><span class="sxs-lookup"><span data-stu-id="4f338-119">This jar is necessary only if your app performs reflection on classes deriving from MAMActivity, and most apps do not need to include it.</span></span> <span data-ttu-id="4f338-120">この jar を使用している場合、そのすべてのクラスを ProGuard から除外する操作は慎重に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-120">If you use this jar, you must be careful to exclude all its classes from ProGuard.</span></span> <span data-ttu-id="4f338-121">それはすべて "android" ルート パッケージの下にあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-121">They will all be under the "android" root package</span></span>
* <span data-ttu-id="4f338-122">**proguard.txt**: ProGuard を使用してビルドする場合に適用する必要がある ProGuard ルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f338-122">**proguard.txt**: Contains ProGuard rules which must be applied if building with ProGuard.</span></span>
* <span data-ttu-id="4f338-123">**CHANGELOG.txt**: 各 SDK バージョンに加えた変更の記録を提供します。</span><span class="sxs-lookup"><span data-stu-id="4f338-123">**CHANGELOG.txt**: Provides a record of changes made in each SDK version.</span></span>
* <span data-ttu-id="4f338-124">**THIRDPARTYNOTICES.TXT**:  アプリにコンパイルされるサード パーティや OSS のコードを確認する属性通知です。</span><span class="sxs-lookup"><span data-stu-id="4f338-124">**THIRDPARTYNOTICES.TXT**:  An attribution notice that acknowledges third-party and/or OSS code that will be compiled into your app.</span></span>

<span data-ttu-id="4f338-125">ビルド システムが AAR ファイルをサポートしていない場合は、Microsoft.Intune.MAM.SDK.aar の代わりに、次のファイルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-125">If your build system does not support AAR files, you may use the following files in place of Microsoft.Intune.MAM.SDK.aar.</span></span>
* <span data-ttu-id="4f338-126">**Microsoft.Intune.MAM.SDK.jar**: Intune ポータル サイト アプリとの相互運用性および MAM を有効にするために必要なインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4f338-126">**Microsoft.Intune.MAM.SDK.jar**: The interfaces necessary to enable MAM and interoperability with the Intune Company Portal app.</span></span> <span data-ttu-id="4f338-127">アプリでこれを Android ライブラリ参照として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-127">Apps must specify it as an Android library reference.</span></span>
* <span data-ttu-id="4f338-128">**res ディレクトリ**: SDK が依存するリソース (文字列など)。</span><span class="sxs-lookup"><span data-stu-id="4f338-128">**The res directory**: The resources (like strings) on which the SDK relies.</span></span>
* <span data-ttu-id="4f338-129">**AndroidManifest.xml**: エントリ ポイントとライブラリの要件です。</span><span class="sxs-lookup"><span data-stu-id="4f338-129">**AndroidManifest.xml**: Entry points and the library requirements.</span></span>


## <a name="requirements"></a><span data-ttu-id="4f338-130">要件</span><span class="sxs-lookup"><span data-stu-id="4f338-130">Requirements</span></span>

<span data-ttu-id="4f338-131">Intune アプリ SDK は、コンパイル済みの Android プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="4f338-131">The Intune App SDK is a compiled Android project.</span></span> <span data-ttu-id="4f338-132">その結果、最小またはターゲットの API バージョンに関して、アプリが使用する Android のバージョンにはほとんど影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="4f338-132">As a result, it is largely unaffected by the version of Android that the app uses for its minimum or target API versions.</span></span> <span data-ttu-id="4f338-133">この SDK は Android API 19 (Android 4.4 以降) から Android API 26 (Android 8.0) までをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4f338-133">The SDK supports Android API 19 (Android 4.4+) through Android API 26 (Android 8.0).</span></span>


### <a name="company-portal-app"></a><span data-ttu-id="4f338-134">ポータル サイト アプリ</span><span class="sxs-lookup"><span data-stu-id="4f338-134">Company Portal app</span></span>
<span data-ttu-id="4f338-135">Android 用の Intune アプリ SDK でアプリ保護ポリシーを有効にするには、デバイスに[ポータル サイト](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) アプリが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-135">The Intune App SDK for Android relies on the presence of the [Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) app on the device to enable app protection policies.</span></span> <span data-ttu-id="4f338-136">ポータル サイトは、Intune サービスからアプリ保護ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="4f338-136">The Company Portal retrieves app protection policies from the Intune service.</span></span> <span data-ttu-id="4f338-137">アプリが初期化されるときに、ポータル サイトからポリシーとコードを読み込み、そのポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="4f338-137">When the app initializes, it loads policy and code to enforce that policy from the Company Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="4f338-138">ポータル サイト アプリがデバイス上にない場合は、Intune 対応アプリが Intune アプリ保護ポリシーをサポートしていない通常のアプリケーションと同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="4f338-138">When the Company Portal app is not on the device, an Intune-enlightened app behaves the same as a normal app that does not support Intune app protection policies.</span></span>

<span data-ttu-id="4f338-139">デバイス登録が不要なアプリ保護の場合は、ユーザーがポータル サイト アプリを使用してデバイスを登録する必要は_**ありません**_。</span><span class="sxs-lookup"><span data-stu-id="4f338-139">For app protection without device enrollment, the user is _**not**_ required to enroll the device by using the Company Portal app.</span></span>

## <a name="sdk-integration"></a><span data-ttu-id="4f338-140">SDK 統合</span><span class="sxs-lookup"><span data-stu-id="4f338-140">SDK Integration</span></span>

### <a name="build-integration"></a><span data-ttu-id="4f338-141">ビルドの統合</span><span class="sxs-lookup"><span data-stu-id="4f338-141">Build integration</span></span>

<span data-ttu-id="4f338-142">Intune アプリ SDK は、外部依存関係のない標準の Android ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="4f338-142">The Intune App SDK is a standard Android library with no external dependencies.</span></span> <span data-ttu-id="4f338-143">**Microsoft.Intune.MAM.SDK.jar** には、アプリ保護ポリシーの有効化に必要なインターフェイスと Microsoft Intune ポータル サイト アプリとの対話操作に必要なコードの両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f338-143">**Microsoft.Intune.MAM.SDK.jar** contains both the interfaces necessary for an app protection policy enablement and the code necessary to interoperate with the Microsoft Intune Company Portal app.</span></span>

<span data-ttu-id="4f338-144">**Microsoft.Intune.MAM.SDK.jar** は、Android ライブラリの参照として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-144">**Microsoft.Intune.MAM.SDK.jar** must be specified as an Android library reference.</span></span> <span data-ttu-id="4f338-145">これを行うには、Android Studio でアプリ プロジェクトを開き、**[File]**、New、New module の順に選択し、**[Import .JAR/.AAR Package]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f338-145">To do this, open your app project in Android Studio and go to **File > New > New module** and select **Import .JAR/.AAR Package**.</span></span> <span data-ttu-id="4f338-146">Android アーカイブ パッケージ Microsoft.Intune.MAM.SDK.aar を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f338-146">Select our Android archive package Microsoft.Intune.MAM.SDK.aar.</span></span>

<span data-ttu-id="4f338-147">さらに、**Microsoft.Intune.MAM.SDK.Support.v4** と **Microsoft.Intune.MAM.SDK.Support.v7** に Intune バリエーション `android.support.v4` と `android.support.v7` がそれぞれ含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f338-147">Additionally, **Microsoft.Intune.MAM.SDK.Support.v4** and **Microsoft.Intune.MAM.SDK.Support.v7** contain Intune variants of `android.support.v4` and `android.support.v7` respectively.</span></span> <span data-ttu-id="4f338-148">それらは、アプリがサポート ライブラリをインクルードしたくない場合に備えて、Microsoft.Intune.MAM.SDK.aar には組み込まれていません。</span><span class="sxs-lookup"><span data-stu-id="4f338-148">They are not built into Microsoft.Intune.MAM.SDK.aar in case an app does not want to include the support libraries.</span></span> <span data-ttu-id="4f338-149">それらは、Android ライブラリ プロジェクトではなく標準の JAR ファイルです。</span><span class="sxs-lookup"><span data-stu-id="4f338-149">They are standard JAR files instead of Android library projects.</span></span>

#### <a name="proguard"></a><span data-ttu-id="4f338-150">ProGuard</span><span class="sxs-lookup"><span data-stu-id="4f338-150">ProGuard</span></span>

<span data-ttu-id="4f338-151">[ProGuard](http://proguard.sourceforge.net/) (またはその他の圧縮/難読化メカニズム) をビルドのステップとして使用している場合、Intune SDK クラスを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-151">If [ProGuard](http://proguard.sourceforge.net/) (or any other shrinking/obfuscation mechanism) is used as a build step, Intune SDK classes must be excluded.</span></span> <span data-ttu-id="4f338-152">ProGuard の場合、これは、SDK と共に配布される proguard.txt ファイルからのルールを含めることによって実現できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-152">For ProGuard, this can be accomplished by including the rules from the proguard.txt file distributed with the SDK.</span></span>

<span data-ttu-id="4f338-153">Azure Active Directory 認証ライブラリ (ADAL) には、独自の ProGuard の制限がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-153">The Azure Active Directory Authentication Libraries (ADAL) may have its own ProGuard restrictions.</span></span> <span data-ttu-id="4f338-154">アプリが ADAL を統合する場合、これらの制限について ADAL のドキュメントに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-154">If your app integrates ADAL, you must follow the ADAL documentation on these restrictions.</span></span>

### <a name="entry-points"></a><span data-ttu-id="4f338-155">エントリ ポイント</span><span class="sxs-lookup"><span data-stu-id="4f338-155">Entry points</span></span>

<span data-ttu-id="4f338-156">Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) では、仲介型認証を実行する場合にこれらのアクセス許可が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-156">The Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) requires these permissions to perform brokered authentication.</span></span> <span data-ttu-id="4f338-157">これらのアクセス許可がアプリに付与されていない場合や、ユーザーによって取り消された場合、ブローカー (ポータル サイト アプリ) を必要とする認証フローは無効になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-157">If these permissions are not granted to the app or are revoked by the user, authentication flows that require the broker (the Company Portal app) will be disabled.</span></span>

<span data-ttu-id="4f338-158">Intune アプリ SDK では、Intune アプリ保護ポリシーを有効にするために、アプリのソース コードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-158">The Intune App SDK requires changes to an app's source code to enable Intune app protection policies.</span></span> <span data-ttu-id="4f338-159">このことは、Android の基底クラスを同等の Intune の基底クラス (名前にプレフィックス **MAM** が付いている) に置き換えることで行われます。</span><span class="sxs-lookup"><span data-stu-id="4f338-159">This is done through the replacement of the Android base classes with equivalent Intune base classes, whose names have the prefix **MAM**.</span></span> <span data-ttu-id="4f338-160">SDK クラスは、Android の基底クラスと、アプリ独自のそのクラスの派生バージョンの間に位置します。</span><span class="sxs-lookup"><span data-stu-id="4f338-160">The SDK classes live between the Android base class and the app's own derived version of that class.</span></span> <span data-ttu-id="4f338-161">例としてアクティビティを使用すると、最終的な継承階層は、`Activity` > `MAMActivity` > `AppSpecificActivity` のようになります。</span><span class="sxs-lookup"><span data-stu-id="4f338-161">Using an activity as an example, you end up with an inheritance hierarchy that looks like: `Activity` > `MAMActivity` > `AppSpecificActivity`.</span></span>

<span data-ttu-id="4f338-162">たとえば、`AppSpecificActivity` がその親と対話する場合 (たとえば、`super.onCreate()` を呼び出して)、`MAMActivity` がスーパー クラスとなります。</span><span class="sxs-lookup"><span data-stu-id="4f338-162">For example, when `AppSpecificActivity` interacts with its parent (for example, calling `super.onCreate()`), `MAMActivity` is the super class.</span></span>

<span data-ttu-id="4f338-163">標準的な Android アプリはモードが 1 つで、[**コンテキスト**](https://developer.android.com/reference/android/content/Context.html) オブジェクトを使用してシステムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4f338-163">Typical Android apps have a single mode and can access the system through their [**Context**](https://developer.android.com/reference/android/content/Context.html) object.</span></span> <span data-ttu-id="4f338-164">一方、Intune アプリ SDK が統合されたアプリはデュアル モードになります。</span><span class="sxs-lookup"><span data-stu-id="4f338-164">Apps that have integrated the Intune App SDK, on the other hand, have dual modes.</span></span> <span data-ttu-id="4f338-165">これらのアプリは引き続き `Context` オブジェクトを通じてシステムにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4f338-165">These apps continue to access the system through the `Context` object.</span></span> <span data-ttu-id="4f338-166">使用する基本 `Activity` に応じて、`Context` オブジェクトが Android によって提供されるか、システムの制限付きビューと Android から提供される `Context` の間でインテリジェントに多重化されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-166">Depending on the base `Activity` used, the `Context` object will be provided by Android or will intelligently multiplex between a restricted view of the system and the Android-provided `Context`.</span></span> <span data-ttu-id="4f338-167">MAM のエントリ ポイントのいずれかから派生させた後、通常どおり `Context` を使用できます (たとえば、`Activity` クラスを開始して `PackageManager` を使用する場合など)。</span><span class="sxs-lookup"><span data-stu-id="4f338-167">After you derive from one of the MAM entry points, it's safe to use `Context` as you would normally -- for example, starting `Activity` classes and using `PackageManager`.</span></span>


## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent"></a><span data-ttu-id="4f338-168">クラス、メソッド、およびアクティビティを、同等の MAM に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4f338-168">Replace classes, methods, and activities with their MAM equivalent</span></span>

<span data-ttu-id="4f338-169">Android の基底クラスを、それぞれ対応する同等の MAM に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-169">Android base classes must be replaced with their respective MAM equivalents.</span></span> <span data-ttu-id="4f338-170">これを行うには、次の表にリスト表示されているクラスのすべてのインスタンスを見つけて同等の Intune アプリ SDK に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4f338-170">To do so, find all instances of the classes listed in the following table and replace them with the Intune App SDK equivalent.</span></span> <span data-ttu-id="4f338-171">これらの大部分は、アプリ クラスが継承するクラスとなりますが、一部にはアプリが継承なしで使用するクラス (MediaPlayer など) もあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-171">Most of these are classes which your app classes will inherit from, but some (e.g. MediaPlayer) will be classes your app uses without deriving.</span></span>

| <span data-ttu-id="4f338-172">Android の基底クラス</span><span class="sxs-lookup"><span data-stu-id="4f338-172">Android base class</span></span> | <span data-ttu-id="4f338-173">Intune アプリ SDK の代替物</span><span class="sxs-lookup"><span data-stu-id="4f338-173">Intune App SDK replacement</span></span> |
|--|--|
| <span data-ttu-id="4f338-174">とroid.app.Activity</span><span class="sxs-lookup"><span data-stu-id="4f338-174">android.app.Activity</span></span> | <span data-ttu-id="4f338-175">MAMActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-175">MAMActivity</span></span> |
| <span data-ttu-id="4f338-176">とroid.app.ActivityGroup</span><span class="sxs-lookup"><span data-stu-id="4f338-176">android.app.ActivityGroup</span></span> | <span data-ttu-id="4f338-177">MAMActivityGroup</span><span class="sxs-lookup"><span data-stu-id="4f338-177">MAMActivityGroup</span></span> |
| <span data-ttu-id="4f338-178">とroid.app.AliasActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-178">android.app.AliasActivity</span></span> | <span data-ttu-id="4f338-179">MAMAliasActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-179">MAMAliasActivity</span></span> |
| <span data-ttu-id="4f338-180">とroid.app.Application</span><span class="sxs-lookup"><span data-stu-id="4f338-180">android.app.Application</span></span> | <span data-ttu-id="4f338-181">MAMApplication</span><span class="sxs-lookup"><span data-stu-id="4f338-181">MAMApplication</span></span> |
| <span data-ttu-id="4f338-182">とroid.app.DialogFragment</span><span class="sxs-lookup"><span data-stu-id="4f338-182">android.app.DialogFragment</span></span> | <span data-ttu-id="4f338-183">MAMDialogFragment</span><span class="sxs-lookup"><span data-stu-id="4f338-183">MAMDialogFragment</span></span> |
| <span data-ttu-id="4f338-184">とroid.app.ExpとableListActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-184">android.app.ExpandableListActivity</span></span> | <span data-ttu-id="4f338-185">MAMExpとableListActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-185">MAMExpandableListActivity</span></span> |
| <span data-ttu-id="4f338-186">とroid.app.Fragment</span><span class="sxs-lookup"><span data-stu-id="4f338-186">android.app.Fragment</span></span> | <span data-ttu-id="4f338-187">MAMFragment</span><span class="sxs-lookup"><span data-stu-id="4f338-187">MAMFragment</span></span> |
| <span data-ttu-id="4f338-188">とroid.app.IntentService</span><span class="sxs-lookup"><span data-stu-id="4f338-188">android.app.IntentService</span></span> | <span data-ttu-id="4f338-189">MAMIntentService</span><span class="sxs-lookup"><span data-stu-id="4f338-189">MAMIntentService</span></span> |
| <span data-ttu-id="4f338-190">とroid.app.LauncherActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-190">android.app.LauncherActivity</span></span> | <span data-ttu-id="4f338-191">MAMLauncherActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-191">MAMLauncherActivity</span></span> |
| <span data-ttu-id="4f338-192">とroid.app.ListActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-192">android.app.ListActivity</span></span> | <span data-ttu-id="4f338-193">MAMListActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-193">MAMListActivity</span></span> |
| <span data-ttu-id="4f338-194">とroid.app.NativeActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-194">android.app.NativeActivity</span></span> | <span data-ttu-id="4f338-195">MAMNativeActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-195">MAMNativeActivity</span></span> |
| <span data-ttu-id="4f338-196">とroid.app.PendingIntent</span><span class="sxs-lookup"><span data-stu-id="4f338-196">android.app.PendingIntent</span></span> | <span data-ttu-id="4f338-197">MAMPendingIntent (「[PendingIntent](#pendingintent)」を参照)</span><span class="sxs-lookup"><span data-stu-id="4f338-197">MAMPendingIntent (see [Pending Intent](#pendingintent))</span></span> |
| <span data-ttu-id="4f338-198">とroid.app.Service</span><span class="sxs-lookup"><span data-stu-id="4f338-198">android.app.Service</span></span> | <span data-ttu-id="4f338-199">MAMService</span><span class="sxs-lookup"><span data-stu-id="4f338-199">MAMService</span></span> |
| <span data-ttu-id="4f338-200">とroid.app.TabActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-200">android.app.TabActivity</span></span> | <span data-ttu-id="4f338-201">MAMTabActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-201">MAMTabActivity</span></span> |
| <span data-ttu-id="4f338-202">とroid.app.TaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="4f338-202">android.app.TaskStackBuilder</span></span> | <span data-ttu-id="4f338-203">MAMTaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="4f338-203">MAMTaskStackBuilder</span></span> |
| <span data-ttu-id="4f338-204">とroid.app.backup.BackupAgent</span><span class="sxs-lookup"><span data-stu-id="4f338-204">android.app.backup.BackupAgent</span></span> | <span data-ttu-id="4f338-205">MAMBackupAgent</span><span class="sxs-lookup"><span data-stu-id="4f338-205">MAMBackupAgent</span></span> |
| <span data-ttu-id="4f338-206">とroid.app.backup.BackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-206">android.app.backup.BackupAgentHelper</span></span> | <span data-ttu-id="4f338-207">MAMBackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-207">MAMBackupAgentHelper</span></span> |
| <span data-ttu-id="4f338-208">とroid.app.backup.FileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-208">android.app.backup.FileBackupHelper</span></span> | <span data-ttu-id="4f338-209">MAMFileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-209">MAMFileBackupHelper</span></span> |
| <span data-ttu-id="4f338-210">とroid.app.backup.SharePreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-210">android.app.backup.SharePreferencesBackupHelper</span></span> | <span data-ttu-id="4f338-211">MAMSharedPreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-211">MAMSharedPreferencesBackupHelper</span></span> |
| <span data-ttu-id="4f338-212">とroid.content.BroadcastReceiver</span><span class="sxs-lookup"><span data-stu-id="4f338-212">android.content.BroadcastReceiver</span></span> | <span data-ttu-id="4f338-213">MAMBroadcastReceiver</span><span class="sxs-lookup"><span data-stu-id="4f338-213">MAMBroadcastReceiver</span></span> |
| <span data-ttu-id="4f338-214">とroid.content.ContentProvider</span><span class="sxs-lookup"><span data-stu-id="4f338-214">android.content.ContentProvider</span></span> | <span data-ttu-id="4f338-215">MAMContentProvider</span><span class="sxs-lookup"><span data-stu-id="4f338-215">MAMContentProvider</span></span> |
| <span data-ttu-id="4f338-216">とroid.os.Binder</span><span class="sxs-lookup"><span data-stu-id="4f338-216">android.os.Binder</span></span> | <span data-ttu-id="4f338-217">MAMBinder (Android インターフェイス定義言語 (AIDL) インターフェイスから Binder が生成されない場合にのみ必要)</span><span class="sxs-lookup"><span data-stu-id="4f338-217">MAMBinder (Only necessary if the Binder is not generated from an Android Interface Definition Language (AIDL) interface)</span></span> |
| <span data-ttu-id="4f338-218">android.media.MediaPlayer</span><span class="sxs-lookup"><span data-stu-id="4f338-218">android.media.MediaPlayer</span></span> | <span data-ttu-id="4f338-219">MAMMediaPlayer</span><span class="sxs-lookup"><span data-stu-id="4f338-219">MAMMediaPlayer</span></span> |
| <span data-ttu-id="4f338-220">android.media.MediaMetadataRetriever</span><span class="sxs-lookup"><span data-stu-id="4f338-220">android.media.MediaMetadataRetriever</span></span> | <span data-ttu-id="4f338-221">MAMMediaMetadataRetriever</span><span class="sxs-lookup"><span data-stu-id="4f338-221">MAMMediaMetadataRetriever</span></span> |
| <span data-ttu-id="4f338-222">とroid.provider.DocumentsProvider</span><span class="sxs-lookup"><span data-stu-id="4f338-222">android.provider.DocumentsProvider</span></span> | <span data-ttu-id="4f338-223">MAMDocumentsProvider</span><span class="sxs-lookup"><span data-stu-id="4f338-223">MAMDocumentsProvider</span></span> |
| <span data-ttu-id="4f338-224">とroid.preference.PreferenceActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-224">android.preference.PreferenceActivity</span></span> | <span data-ttu-id="4f338-225">MAMPreferenceActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-225">MAMPreferenceActivity</span></span> |

> [!NOTE]
> <span data-ttu-id="4f338-226">アプリケーションが独自に派生した `Application` クラスを必要としていなくても、下記の「[`MAMApplication`](#mamapplication)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-226">Even if your application does not have a need for its own derived `Application` class, [see `MAMApplication` below](#mamapplication)</span></span>

### <a name="microsoftintunemamsdksupportv4jar"></a><span data-ttu-id="4f338-227">Microsoft.Intune.MAM.SDK.Support.v4.jar:</span><span class="sxs-lookup"><span data-stu-id="4f338-227">Microsoft.Intune.MAM.SDK.Support.v4.jar:</span></span>

| <span data-ttu-id="4f338-228">Android クラス Intune MAM</span><span class="sxs-lookup"><span data-stu-id="4f338-228">Android Class Intune MAM</span></span> | <span data-ttu-id="4f338-229">Intune アプリ SDK の代替物</span><span class="sxs-lookup"><span data-stu-id="4f338-229">Intune App SDK replacement</span></span> |
|--|--|
| <span data-ttu-id="4f338-230">とroid.suppまたはt.v4.app.DialogFragment</span><span class="sxs-lookup"><span data-stu-id="4f338-230">android.support.v4.app.DialogFragment</span></span> | <span data-ttu-id="4f338-231">MAMDialogFragment</span><span class="sxs-lookup"><span data-stu-id="4f338-231">MAMDialogFragment</span></span>
| <span data-ttu-id="4f338-232">とroid.suppまたはt.v4.app.FragmentActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-232">android.support.v4.app.FragmentActivity</span></span> | <span data-ttu-id="4f338-233">MAMFragmentActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-233">MAMFragmentActivity</span></span>
| <span data-ttu-id="4f338-234">とroid.suppまたはt.v4.app.Fragment</span><span class="sxs-lookup"><span data-stu-id="4f338-234">android.support.v4.app.Fragment</span></span> | <span data-ttu-id="4f338-235">MAMFragment</span><span class="sxs-lookup"><span data-stu-id="4f338-235">MAMFragment</span></span>
| <span data-ttu-id="4f338-236">android.support.v4.app.JobIntentService</span><span class="sxs-lookup"><span data-stu-id="4f338-236">android.support.v4.app.JobIntentService</span></span> | <span data-ttu-id="4f338-237">MAMJobIntentService</span><span class="sxs-lookup"><span data-stu-id="4f338-237">MAMJobIntentService</span></span>
| <span data-ttu-id="4f338-238">とroid.suppまたはt.v4.app.TaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="4f338-238">android.support.v4.app.TaskStackBuilder</span></span> | <span data-ttu-id="4f338-239">MAMTaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="4f338-239">MAMTaskStackBuilder</span></span>
| <span data-ttu-id="4f338-240">とroid.suppまたはt.v4.content.FileProvider</span><span class="sxs-lookup"><span data-stu-id="4f338-240">android.support.v4.content.FileProvider</span></span> | <span data-ttu-id="4f338-241">MAMFileProvider</span><span class="sxs-lookup"><span data-stu-id="4f338-241">MAMFileProvider</span></span>

### <a name="microsoftintunemamsdksupportv7jar"></a><span data-ttu-id="4f338-242">Microsoft.Intune.MAM.SDK.Support.v7.jar:</span><span class="sxs-lookup"><span data-stu-id="4f338-242">Microsoft.Intune.MAM.SDK.Support.v7.jar:</span></span>

|<span data-ttu-id="4f338-243">Android クラス</span><span class="sxs-lookup"><span data-stu-id="4f338-243">Android Class</span></span> | <span data-ttu-id="4f338-244">Intune アプリ SDK の代替物</span><span class="sxs-lookup"><span data-stu-id="4f338-244">Intune App SDK replacement</span></span> |
|--|--|
|<span data-ttu-id="4f338-245">android.support.v7.app.AppCompatActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-245">android.support.v7.app.AppCompatActivity</span></span> | <span data-ttu-id="4f338-246">MAMAppCompatActivity</span><span class="sxs-lookup"><span data-stu-id="4f338-246">MAMAppCompatActivity</span></span> |

### <a name="renamed-methods"></a><span data-ttu-id="4f338-247">名前が変更されたメソッド</span><span class="sxs-lookup"><span data-stu-id="4f338-247">Renamed Methods</span></span>


<span data-ttu-id="4f338-248">多くの場合、Android のクラスで使用できるメソッドが、MAM の置換クラスで最終版としてマークされています。</span><span class="sxs-lookup"><span data-stu-id="4f338-248">In many cases, a method available in the Android class has been marked as final in the MAM replacement class.</span></span> <span data-ttu-id="4f338-249">この場合、MAM 置換クラスによって、似た名前のメソッド (通常は `MAM` というサフィックスが付いている) が提供され、これをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-249">In this case, the MAM replacement class provides a similarly named method (generally suffixed with `MAM`) that you should override instead.</span></span> <span data-ttu-id="4f338-250">たとえば、`MAMActivity` から派生する場合は、`onCreate()` をオーバーライドして `super.onCreate()` を呼び出すのではなく、`Activity` で `onMAMCreate()` をオーバーライドし、`super.onMAMCreate()` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-250">For example, when deriving from `MAMActivity`, instead of overriding `onCreate()` and calling `super.onCreate()`, `Activity` must override `onMAMCreate()` and call `super.onMAMCreate()`.</span></span> <span data-ttu-id="4f338-251">同等の MAM でなく、元のメソッドが偶発的にオーバーライドされることを防ぐために、Java コンパイラによって、最終的な制限が強制されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-251">The Java compiler should enforce the final restrictions to prevent accidental override of the original method instead of the MAM equivalent.</span></span>

### <a name="mamapplication"></a><span data-ttu-id="4f338-252">MAMApplication</span><span class="sxs-lookup"><span data-stu-id="4f338-252">MAMApplication</span></span>
<span data-ttu-id="4f338-253">MAM SDK 内での制約のため、`com.microsoft.intune.mam.client.app.MAMApplication` のサブクラスを作成し、それを、マニフェスト内で使用する `Application` クラスの名前として設定する**必要**があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-253">Due to constraints within the MAM SDK, you **must** create a subclass of `com.microsoft.intune.mam.client.app.MAMApplication` and set it as the name of the `Application` class used in your manifest.</span></span> <span data-ttu-id="4f338-254">`MAMApplication` は抽象型であり、`byte[] getADALSecretKey` のオーバーライドを必要とします。この関数を実装する方法の詳細については、その Javadoc を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-254">`MAMApplication` is abstract and requires an override for `byte[] getADALSecretKey`, please see the Javadoc on that function for more information about how to implement it.</span></span>
### <a name="pendingintent"></a><span data-ttu-id="4f338-255">PendingIntent</span><span class="sxs-lookup"><span data-stu-id="4f338-255">PendingIntent</span></span>
<span data-ttu-id="4f338-256">`PendingIntent.get*` の代わりに `MAMPendingIntent.get*` メソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-256">Instead of `PendingIntent.get*`, you must use the `MAMPendingIntent.get*` method.</span></span> <span data-ttu-id="4f338-257">その後、通常どおり、結果の `PendingIntent` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-257">After this, you can use the resultant `PendingIntent` as usual.</span></span>

### <a name="manifest-replacements"></a><span data-ttu-id="4f338-258">マニフェストの置換</span><span class="sxs-lookup"><span data-stu-id="4f338-258">Manifest Replacements</span></span>
<span data-ttu-id="4f338-259">場合によっては、マニフェストと共に Java コードでも上記の一部のクラスの置換を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-259">Please note that it may be necessary to perform some of the above class replacements in the manifest as well as in Java code.</span></span> <span data-ttu-id="4f338-260">注意: </span><span class="sxs-lookup"><span data-stu-id="4f338-260">Of special note:</span></span>
* <span data-ttu-id="4f338-261">`android.support.v4.content.FileProvider` を参照するマニフェストは、`com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider` に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-261">Manifest references to `android.support.v4.content.FileProvider` must be replaced with `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.</span></span>
* <span data-ttu-id="4f338-262">アプリケーションに独自の派生アプリケーション クラスの必要がない場合、`com.microsoft.intune.mam.client.app.MAMApplication` をマニフェストで使用されるアプリケーション クラスの名前として設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-262">If your application does not have a need for its own derived Application class, `com.microsoft.intune.mam.client.app.MAMApplication` must be set as the name of the Application class used in the manifest.</span></span>

## <a name="sdk-permissions"></a><span data-ttu-id="4f338-263">SDK のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4f338-263">SDK permissions</span></span>

<span data-ttu-id="4f338-264">Intune アプリ SDK では、統合するアプリに対する次の 3 つの [Android システムのアクセス許可](https://developer.android.com/guide/topics/security/permissions.html)が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-264">The Intune App SDK requires three [Android system permissions](https://developer.android.com/guide/topics/security/permissions.html) on apps that integrate it:</span></span>

* <span data-ttu-id="4f338-265">`android.permission.GET_ACCOUNTS`  (必要に応じて実行時に要求)</span><span class="sxs-lookup"><span data-stu-id="4f338-265">`android.permission.GET_ACCOUNTS`  (requested at runtime if required)</span></span>

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

<span data-ttu-id="4f338-266">Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) では、仲介型認証を実行する場合にこれらのアクセス許可が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-266">The Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) requires these permissions to perform brokered authentication.</span></span> <span data-ttu-id="4f338-267">これらのアクセス許可がアプリに付与されていない場合や、ユーザーによって取り消された場合、ブローカー (ポータル サイト アプリ) を必要とする認証フローは無効になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-267">If these permissions are not granted to the app or are revoked by the user, authentication flows that require the broker (the Company Portal app) will be disabled.</span></span>

## <a name="logging"></a><span data-ttu-id="4f338-268">ログ記録</span><span class="sxs-lookup"><span data-stu-id="4f338-268">Logging</span></span>

<span data-ttu-id="4f338-269">ログに記録されたデータを最も有効に活用するには、ログを早い段階で初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-269">Logging should be initialized early to get the most value out of logged data.</span></span> <span data-ttu-id="4f338-270">一般的にログを初期化するには、`Application.onMAMCreate()` が最も効果的です。</span><span class="sxs-lookup"><span data-stu-id="4f338-270">`Application.onMAMCreate()` is typically the best place to initialize logging.</span></span>

<span data-ttu-id="4f338-271">アプリで MAM ログを受信するには、[Java ハンドラー](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html)を作成、それを `MAMLogHandlerWrapper` に追加します。</span><span class="sxs-lookup"><span data-stu-id="4f338-271">To receive MAM logs in your app, create a [Java Handler](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) and add it to the `MAMLogHandlerWrapper`.</span></span> <span data-ttu-id="4f338-272">これにより、すべてのログ メッセージに対してアプリケーション ハンドラーで `publish()` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f338-272">This will invoke `publish()` on the application handler for every log message.</span></span>

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```



## <a name="enable-features-that-require-app-participation"></a><span data-ttu-id="4f338-273">アプリによる処理を必要とする機能の有効化</span><span class="sxs-lookup"><span data-stu-id="4f338-273">Enable features that require app participation</span></span>

<span data-ttu-id="4f338-274">アプリケーション保護ポリシーの中には、SDK 自体に実装できないものがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-274">There are several app protection policies the SDK cannot implement on its own.</span></span> <span data-ttu-id="4f338-275">アプリではいくつかの API を使用して、これらの機能を実行するために動作を制御することができます。この API は以下の `AppPolicy` インターフェイスで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-275">The app can control its behavior to achieve these features by using several APIs that you can find in the following `AppPolicy` interface.</span></span> <span data-ttu-id="4f338-276">`AppPolicy` インスタンスを取得するには、`MAMPolicyManager.getPolicy` を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f338-276">To retrieve an `AppPolicy` instance, use `MAMPolicyManager.getPolicy`.</span></span>

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * This method is intended for diagnostic/telemetry purposes only. It can be used to discover whether
 * file encryption is in use. File encryption is transparent to the app, and the app should not need
 * to make any business logic decisions based on this.
 * 
 * @return True if file encryption is in use.
 */
boolean diagnosticIsFileEncryptionInUse();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}
```

> [!NOTE]
> <span data-ttu-id="4f338-277">`MAMPolicyManager.getPolicy` は、デバイスまたはアプリが Intune 管理ポリシーに従わない場合でも、常に null 以外のアプリ ポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="4f338-277">`MAMPolicyManager.getPolicy` will always return a non-null App Policy, even if the device or app is not under an Intune management policy.</span></span>

### <a name="example-determine-if-pin-is-required-for-the-app"></a><span data-ttu-id="4f338-278">例: PIN がアプリケーションに必要なかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f338-278">Example: Determine if PIN is required for the app</span></span>

<span data-ttu-id="4f338-279">アプリケーションに独自の PIN ユーザー エクスペリエンスがあり、IT 管理者がアプリの PIN の入力を求めるように SDK を構成している場合は、それを無効にしたいことがあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-279">If the app has its own PIN user experience, you might want to disable it if the IT administrator has configured the SDK to prompt for an app PIN.</span></span> <span data-ttu-id="4f338-280">IT 管理者が、現在のエンドユーザーのアプリ PIN ポリシーをこのアプリに展開したかどうかを判断するには、次のメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f338-280">To determine if the IT administrator has deployed the app PIN policy to this app, for the current end user, call the following method:</span></span>

```java

MAMPolicyManager.getPolicy(currentActivity).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a><span data-ttu-id="4f338-281">例: プライマリ Intune ユーザーを判別します。</span><span class="sxs-lookup"><span data-stu-id="4f338-281">Example: Determine the primary Intune user</span></span>

<span data-ttu-id="4f338-282">AppPolicy で公開される API に加えて、ユーザー プリンシパル名で (**UPN**) も `MAMUserInfo`インターフェイス内で定義された `getPrimaryUser()` API によって公開されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-282">In addition to the APIs exposed in AppPolicy, the user principal name (**UPN**) is also exposed by the `getPrimaryUser()` API defined inside the `MAMUserInfo` interface.</span></span> <span data-ttu-id="4f338-283">UPN を取得するには、次のように呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f338-283">To get the UPN, call the following:</span></span>

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

<span data-ttu-id="4f338-284">MAMUserInfo インターフェイスの完全な定義を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-284">The full definition of the MAMUserInfo interface is below:</span></span>

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a><span data-ttu-id="4f338-285">例: デバイスまたはクラウド ストレージへの保存が許可されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="4f338-285">Example: Determine if saving to device or cloud storage is permitted</span></span>

<span data-ttu-id="4f338-286">多くのアプリでは、エンドユーザーがローカルまたはクラウド ストレージ サービスにファイルを保存する機能を実装しています。</span><span class="sxs-lookup"><span data-stu-id="4f338-286">Many apps implement features that allow the end user to save files locally or to a cloud storage service.</span></span> <span data-ttu-id="4f338-287">Intune アプリ SDK を使用することで、データの漏えいを防ぐために、IT 管理者が組織に合ったポリシー制限を適用できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-287">The Intune App SDK allows IT administrators to protect against data leakage by applying policy restrictions as they see fit in their organization.</span></span>  <span data-ttu-id="4f338-288">IT 部門で制御できるポリシーの 1 つとして、エンドユーザーが "個人用" の管理対象外データ ストアに保存できるかどうかというものがあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-288">One of the policies that IT can control is whether the end user can save to a "personal," unmanaged data store.</span></span> <span data-ttu-id="4f338-289">これには、ローカルの場所、SD カード、またはサード パーティ バックアップ サービスへの保存が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f338-289">This includes saving to a local location, SD card, or third-party backup services.</span></span>

<span data-ttu-id="4f338-290">**この機能を有効にするには、アプリによる処理が必要です。**</span><span class="sxs-lookup"><span data-stu-id="4f338-290">**App participation is needed to enable the feature.**</span></span> <span data-ttu-id="4f338-291">アプリから直接個人またはクラウドの場所に保存することをアプリで許可する場合は、IT 管理者がある場所への保存を許可するかどうか制御できるように、この機能を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-291">If your app allows saving to personal or cloud locations directly from the app, you must implement this feature to ensure that the IT administrator can control whether saving to a location is allowed.</span></span> <span data-ttu-id="4f338-292">次の API では、現在の Intune 管理者のポリシーに従い、個人用ストアへの保存が許可されるかどうかを、アプリに知らせています。</span><span class="sxs-lookup"><span data-stu-id="4f338-292">The API below lets the app know whether saving to a personal store is allowed by the current Intune administrator's policy.</span></span> <span data-ttu-id="4f338-293">これにより、エンドユーザーがアプリを介して個人のデータ ストアを使用できることをアプリで認識できるため、アプリでポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-293">The app can then enforce the policy, since it is aware of personal data store available to the end user through the app.</span></span>  

<span data-ttu-id="4f338-294">ポリシーが適用されているかどうかを判断するために、次の呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="4f338-294">To determine if the policy is enforced, make the following call:</span></span>

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(
SaveLocation service, String username);
``````

<span data-ttu-id="4f338-295">`service` には、次の SaveLocations のうちいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f338-295">... where `service` is one of the following SaveLocations:</span></span>


    * <span data-ttu-id="4f338-296">SaveLocation.ONEDRIVE_FOR_BUSINESS</span><span class="sxs-lookup"><span data-stu-id="4f338-296">SaveLocation.ONEDRIVE_FOR_BUSINESS</span></span>
    * <span data-ttu-id="4f338-297">SaveLocation.LOCAL</span><span class="sxs-lookup"><span data-stu-id="4f338-297">SaveLocation.LOCAL</span></span>
    * <span data-ttu-id="4f338-298">SaveLocation.SHAREPOINT</span><span class="sxs-lookup"><span data-stu-id="4f338-298">SaveLocation.SHAREPOINT</span></span>

<span data-ttu-id="4f338-299">ユーザーのポリシーがさまざまな場所にデータを保存することを許可するかどうかを判断する前のメソッドは、同じ **AppPolicy** クラス内の `getIsSaveToPersonalAllowed()` です。</span><span class="sxs-lookup"><span data-stu-id="4f338-299">The previous method of determining whether a user’s policy allowed them to save data to various locations was `getIsSaveToPersonalAllowed()` within the same **AppPolicy** class.</span></span> <span data-ttu-id="4f338-300">この関数は現在**非推奨**になっており、使用しないようにする必要があります。次の呼び出しは `getIsSaveToPersonalAllowed()` と同じです。</span><span class="sxs-lookup"><span data-stu-id="4f338-300">This function is now **deprecated** and should not be used, the following invocation is equivalent to `getIsSaveToPersonalAllowed()`:</span></span>

```java

MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> <span data-ttu-id="4f338-301">問題の場所が、**SaveLocations** 列挙型に表示されない場合は、`SaveLocation.OTHER` を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f338-301">Use `SaveLocation.OTHER` if the location in question is not listed in the **SaveLocations** enum.</span></span>


## <a name="register-for-notifications-from-the-sdk"></a><span data-ttu-id="4f338-302">SDK からの通知への登録</span><span class="sxs-lookup"><span data-stu-id="4f338-302">Register for notifications from the SDK</span></span>

### <a name="overview"></a><span data-ttu-id="4f338-303">概要</span><span class="sxs-lookup"><span data-stu-id="4f338-303">Overview</span></span>
<span data-ttu-id="4f338-304">Intune アプリ SDK を使用すると、IT 管理者が選択的ワイプなどの特定のポリシーを展開したときに、アプリで動作を制御することできます。</span><span class="sxs-lookup"><span data-stu-id="4f338-304">The Intune App SDK allows your app to control the behavior of certain policies, such as selective wipe, when they are deployed by the IT administrator.</span></span> <span data-ttu-id="4f338-305">IT 管理者がそのようなポリシーを展開すると、Intune サービスは SDK に通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="4f338-305">When an IT administrator deploys such a policy, the Intune service sends down a notification to the SDK.</span></span>

<span data-ttu-id="4f338-306">アプリは、`MAMNotificationReceiver` を作成して `MAMNotificationReceiverRegistry` に登録することで、SDK からの通知に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-306">Your app must register for notifications from the SDK by creating a `MAMNotificationReceiver` and  registering it with `MAMNotificationReceiverRegistry`.</span></span> <span data-ttu-id="4f338-307">これは、次の例に示すように、受信側と、`App.onCreate` で必要な通知の種類を指定することで行います。</span><span class="sxs-lookup"><span data-stu-id="4f338-307">This is done by providing the receiver and the type of notification desired in  `App.onCreate`, as the example below illustrates:</span></span>

```java
@Override
public void onCreate() {
  super.onCreate();
  MAMComponents.get(MAMNotificationReceiverRegistry.class)
    .registerReceiver(
      new ToastNotificationReceiver(),
      MAMNotificationType.WIPE_USER_DATA);
  }
``````

### <a name="mamnotificationreceiver"></a><span data-ttu-id="4f338-308">MAMNotificationReceiver</span><span class="sxs-lookup"><span data-stu-id="4f338-308">MAMNotificationReceiver</span></span>

<span data-ttu-id="4f338-309">`MAMNotificationReceiver` インターフェイスでは、単に Intune サービスからの通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="4f338-309">The `MAMNotificationReceiver` interface simply receives notifications from the Intune service.</span></span> <span data-ttu-id="4f338-310">通知の中には、SDK によって直接処理されるものと、アプリによる処理が必要なものがあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-310">Some notifications are handled by the SDK directly, while others require the app's participation.</span></span> <span data-ttu-id="4f338-311">アプリでは、通知から true または false を返す**必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4f338-311">An app **must** return either true or false from a notification.</span></span> <span data-ttu-id="4f338-312">通知の結果として実行しようとした何らかのアクションが失敗した場合を除き、常に true を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-312">It must always return true unless some action it tried to take as a result of the notification failed.</span></span>

* <span data-ttu-id="4f338-313">この失敗は、Intune サービスにレポートされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-313">This failure may be reported to the Intune service.</span></span> <span data-ttu-id="4f338-314">レポートのシナリオ例として、IT 管理者がワイプを開始した後に、アプリがユーザー データのワイプに失敗した場合などがあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-314">An example of a scenario to report is if the app fails to wipe user data after the IT administrator initiates a wipe.</span></span>

>[!NOTE]
> <span data-ttu-id="4f338-315">`MAMNotificationReceiver.onReceive` でブロックすることが安全です。これは、このコールバックは UI スレッドで実行されないためです。</span><span class="sxs-lookup"><span data-stu-id="4f338-315">It is safe to block in `MAMNotificationReceiver.onReceive` because its callback is not running on the UI thread.</span></span>

<span data-ttu-id="4f338-316">SDK で定義されている `MAMNotificationReceiver` インターフェイスを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-316">The `MAMNotificationReceiver` interface as defined in the SDK is included below :</span></span>

```java
/**
 * The SDK is signaling that a MAM event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}
```

### <a name="types-of-notifications"></a><span data-ttu-id="4f338-317">通知の種類</span><span class="sxs-lookup"><span data-stu-id="4f338-317">Types of notifications</span></span>

<span data-ttu-id="4f338-318">アプリに次の通知が送信されます。その一部によって、アプリによる処理が要求される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-318">The following notifications are sent to the app and some of them may require app participation:</span></span>

* <span data-ttu-id="4f338-319">**WIPE_USER_DATA**: この通知は、`MAMUserNotification` クラスで送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-319">**WIPE_USER_DATA**: This notification is sent in a `MAMUserNotification` class.</span></span> <span data-ttu-id="4f338-320">この通知を受信すると、アプリでは `MAMUserNotification` で渡された "企業" ID に関連するすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-320">When this notification is received, the app is expected to delete all data associated with the "corporate" identity passed with the `MAMUserNotification`.</span></span> <span data-ttu-id="4f338-321">この通知は、現在、APP-WE サービスの登録解除中に送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-321">This notification is currently sent during APP-WE service unenrollment.</span></span> <span data-ttu-id="4f338-322">ユーザーのプライマリ名は、通常、登録プロセス中に指定されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-322">The user's primary name is typically specified during the enrollment process.</span></span> <span data-ttu-id="4f338-323">この通知に登録する場合、アプリがすべてのユーザー データが削除されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-323">If you register for this notification, your app must ensure that all the user's data has been deleted.</span></span> <span data-ttu-id="4f338-324">登録しない場合、既定の選択的ワイプの動作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-324">If you don't register for it, the default selective wipe behavior will be performed.</span></span>

* <span data-ttu-id="4f338-325">**WIPE_USER_AUXILIARY_DATA**: Intune アプリ SDK に対して既定の選択的ワイプの実行を求めるが、ワイプが発生したときにいくつかの補助的なデータを削除する必要があるアプリは、この通知に登録できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-325">**WIPE_USER_AUXILIARY_DATA**: Apps can register for this notification if they'd like the Intune App SDK to perform the default selective wipe behavior, but would still like to remove some auxiliary data when the wipe occurs.</span></span>

* <span data-ttu-id="4f338-326">**REFRESH_POLICY**: この通知は、`MAMUserNotification` で送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-326">**REFRESH_POLICY**: This notification is sent in a `MAMUserNotification`.</span></span> <span data-ttu-id="4f338-327">この通知を受信した場合、キャッシュ済みの Intune ポリシーを無効にして更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-327">When this notification is received, any cached Intune policy must be invalidated and updated.</span></span> <span data-ttu-id="4f338-328">これは一般に SDK によって処理されますが、何らかの永続的な方法で、ポリシーを使用する場合は、アプリによって処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-328">This is generally handled by the SDK; however, it should be handled by the app if the policy is used in any persistent way.</span></span>

* <span data-ttu-id="4f338-329">**MANAGEMENT_REMOVED**: この通知は、`MAMUserNotification` で送信され、管理対象外になることをアプリに直前に通知します。</span><span class="sxs-lookup"><span data-stu-id="4f338-329">**MANAGEMENT_REMOVED**: This notification is sent in a `MAMUserNotification` and informs the app that it is about to become unmanaged.</span></span> <span data-ttu-id="4f338-330">管理対象外になると、暗号化されたファイルの読み取り、MAMDataProtectionManager で暗号化されたデータの読み取り、暗号化されたクリップボードとの対話、それ以外の管理対象アプリのエコシステムへの参加ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="4f338-330">Once unmanaged, it will no longer be able to read encrypted files, read data encrypted with MAMDataProtectionManager, interact with the encrypted clipboard, or otherwise participate in the managed-app ecosystem.</span></span>


> [!NOTE]
> <span data-ttu-id="4f338-331">アプリは `WIPE_USER_DATA` と `WIPE_USER_AUXILIARY_DATA` の両方の通知に登録することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f338-331">An app should never register for both the `WIPE_USER_DATA` and `WIPE_USER_AUXILIARY_DATA` notifications.</span></span>


## <a name="configure-azure-active-directory-authentication-library-adal"></a><span data-ttu-id="4f338-332">Azure Active Directory Authentication Library (ADAL) の構成</span><span class="sxs-lookup"><span data-stu-id="4f338-332">Configure Azure Active Directory Authentication Library (ADAL)</span></span>

<span data-ttu-id="4f338-333">最初に、[ADAL GitHub のリポジトリ](https://github.com/AzureAD/azure-activedirectory-library-for-android)にある ADAL の統合のガイドラインを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-333">First, please read the ADAL integration guidelines found in the [ADAL repository on GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-android).</span></span>

<span data-ttu-id="4f338-334">SDK では[認証](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/)と条件付き起動シナリオを [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) に依存するため、アプリを [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-334">The SDK relies on [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) for its [authentication](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) and conditional launch scenarios, which require apps to be configured with [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/).</span></span> <span data-ttu-id="4f338-335">構成値は、AndroidManifest メタデータを使用して SDK に伝達されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-335">The configuration values are communicated to the SDK via AndroidManifest metadata.</span></span>

<span data-ttu-id="4f338-336">アプリを構成して適切な認証を有効にするには、AndroidManifest.xml のアプリのノードに次の内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="4f338-336">To configure your app and enable proper authentication, add the following to the app node in AndroidManifest.xml.</span></span> <span data-ttu-id="4f338-337">これらの構成の中には、アプリで通常の認証に ADAL が使用される場合にのみ必要となるものがあります。この場合、アプリによって AAD への登録に使用される特定の値が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-337">Some of these configurations are only required if your app uses ADAL for authentication in general; in that case, you will need the specific values your app uses to register itself with AAD.</span></span> <span data-ttu-id="4f338-338">これにより、AAD により 2 つ (アプリと SDK から 1 つずつ) の個別の登録値が認識されることによってエンドユーザーに対して認証が 2 回求められることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="4f338-338">This is done to ensure that the end user does not get prompted for authentication twice, due to AAD recognizing two separate registration values: one from the app and one from the SDK.</span></span>

```xml
<meta-data
    android:name="com.microsoft.intune.mam.aad.Authority"
    android:value="https://AAD authority/" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.ClientID"
    android:value="your-client-ID-GUID" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
    android:value="your-redirect-URI" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.SkipBroker"
    android:value="[true | false]" />
```

### <a name="adal-metadata"></a><span data-ttu-id="4f338-339">ADAL メタデータ</span><span class="sxs-lookup"><span data-stu-id="4f338-339">ADAL metadata</span></span>

* <span data-ttu-id="4f338-340">**Authority** は、使用中の現在の AAD 機関です。</span><span class="sxs-lookup"><span data-stu-id="4f338-340">**Authority** is the current AAD authority in use.</span></span> <span data-ttu-id="4f338-341">存在する場合、AAD アカウントが構成されている独自の環境を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-341">If present, you should use your own environment where AAD accounts have been configured.</span></span> <span data-ttu-id="4f338-342">この値が存在しない場合は、Intune の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-342">If this value is absent, an Intune default is used.</span></span>

* <span data-ttu-id="4f338-343">**ClientID** は、使用する AAD ClientID です。</span><span class="sxs-lookup"><span data-stu-id="4f338-343">**ClientID** is the AAD ClientID to be used.</span></span> <span data-ttu-id="4f338-344">Azure AD に登録されている場合は、独自のアプリの ClientID を使用してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-344">You should use your own app's ClientID if it is registered with Azure AD.</span></span> <span data-ttu-id="4f338-345">この値が存在しない場合は、Intune の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-345">If this value is absent, an Intune default is used.</span></span>

* <span data-ttu-id="4f338-346">**NonBrokerRedirectURI** は、ブローカーを使用しない場合に使用する AAD リダイレクト URI です。</span><span class="sxs-lookup"><span data-stu-id="4f338-346">**NonBrokerRedirectURI** is the AAD redirect URI to use in broker-less cases.</span></span> <span data-ttu-id="4f338-347">指定しない場合は、既定値の `urn:ietf:wg:oauth:2.0:oob` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-347">If none is specified, a default value of `urn:ietf:wg:oauth:2.0:oob` is used.</span></span> <span data-ttu-id="4f338-348">この既定値は、ほとんどのアプリケーションに適しています。</span><span class="sxs-lookup"><span data-stu-id="4f338-348">This default is suitable for most apps.</span></span>

* <span data-ttu-id="4f338-349">**SkipBroker** は、ブローカーのリダイレクト URI を使用するように ClientID が構成されていない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-349">**SkipBroker** is used in case the ClientID has not been configured to use the broker redirect URI.</span></span> <span data-ttu-id="4f338-350">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="4f338-350">The default value is "false."</span></span>
    * <span data-ttu-id="4f338-351">**ADAL を統合しない**アプリおよび**デバイス全体の仲介型の認証/SSO に参加しないアプリ**の場合、このプロパティを "true" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-351">For apps that **do not integrate ADAL** and **do not want to participate in device-wide brokered authentication/SSO**, this should be set to "true."</span></span> <span data-ttu-id="4f338-352">この値が "true" の場合は、使用されるリダイレクト URI は、NonBrokerRedirectURI のみです。</span><span class="sxs-lookup"><span data-stu-id="4f338-352">When this value is "true," the only redirect URI that will be used is NonBrokerRedirectURI.</span></span>

    * <span data-ttu-id="4f338-353">デバイス全体にわたる SSO ブローカーをサポートしているアプリの場合、これを "false" にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-353">For apps that do support device-wide SSO brokering, this should be "false."</span></span> <span data-ttu-id="4f338-354">値が "false" の場合、SDK はシステムでのブローカーの可用性を基にして、[`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) の結果と NonBrokerRedirectURI の間のブローカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f338-354">When the value is "false," the SDK will select a broker between the result of [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) and NonBrokerRedirectURI, based on the availability of the broker on the system.</span></span> <span data-ttu-id="4f338-355">一般に、ブローカーはポータル サイト アプリまたは Azure Authenticator アプリから利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-355">In general, the broker will be available from the Company Portal app or Azure Authenticator app.</span></span>

### <a name="common-adal-configurations"></a><span data-ttu-id="4f338-356">ADAL の一般的な構成</span><span class="sxs-lookup"><span data-stu-id="4f338-356">Common ADAL configurations</span></span>

<span data-ttu-id="4f338-357">ADAL を使用してアプリを構成する一般的な方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-357">The following are common ways an app can be configured with ADAL.</span></span> <span data-ttu-id="4f338-358">アプリの構成を検索し、ADAL メタデータ パラメーター (上述) を必要な値に設定したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f338-358">Find your app's configuration and make sure to set the ADAL metadata parameters (explained above) to the necessary values.</span></span>

1. <span data-ttu-id="4f338-359">**アプリに ADAL が統合されない場合:**</span><span class="sxs-lookup"><span data-stu-id="4f338-359">**App does not integrate ADAL:**</span></span>

    | <span data-ttu-id="4f338-360">必須の ADAL パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f338-360">Required ADAL parameter</span></span> | <span data-ttu-id="4f338-361">値</span><span class="sxs-lookup"><span data-stu-id="4f338-361">Value</span></span> |
    |--|--|
    | <span data-ttu-id="4f338-362">Authority</span><span class="sxs-lookup"><span data-stu-id="4f338-362">Authority</span></span> | <span data-ttu-id="4f338-363">AAD アカウントが構成されている必要な環境</span><span class="sxs-lookup"><span data-stu-id="4f338-363">Desired environment where AAD accounts have been configured</span></span> |
    | <span data-ttu-id="4f338-364">SkipBroker</span><span class="sxs-lookup"><span data-stu-id="4f338-364">SkipBroker</span></span> | <span data-ttu-id="4f338-365">True</span><span class="sxs-lookup"><span data-stu-id="4f338-365">True</span></span> |

2. <span data-ttu-id="4f338-366">**アプリに ADAL が統合される場合:**</span><span class="sxs-lookup"><span data-stu-id="4f338-366">**App integrates ADAL:**</span></span>

    |<span data-ttu-id="4f338-367">必須の ADAL パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f338-367">Required ADAL parameter</span></span>| <span data-ttu-id="4f338-368">値</span><span class="sxs-lookup"><span data-stu-id="4f338-368">Value</span></span> |
    |--|--|
    | <span data-ttu-id="4f338-369">Authority</span><span class="sxs-lookup"><span data-stu-id="4f338-369">Authority</span></span> | <span data-ttu-id="4f338-370">AAD アカウントが構成されている必要な環境</span><span class="sxs-lookup"><span data-stu-id="4f338-370">Desired environment where AAD accounts have been configured</span></span> |
    | <span data-ttu-id="4f338-371">ClientID</span><span class="sxs-lookup"><span data-stu-id="4f338-371">ClientID</span></span> | <span data-ttu-id="4f338-372">アプリの ClientID (アプリが登録されるときに Azure AD によって生成される)</span><span class="sxs-lookup"><span data-stu-id="4f338-372">The app's ClientID (generated by Azure AD when the app is registered)</span></span> |
    | <span data-ttu-id="4f338-373">NonBrokerRedirectURI</span><span class="sxs-lookup"><span data-stu-id="4f338-373">NonBrokerRedirectURI</span></span> | <span data-ttu-id="4f338-374">アプリの有効なリダイレクト URI または既定値の `urn:ietf:wg:oauth:2.0:oob`。</span><span class="sxs-lookup"><span data-stu-id="4f338-374">A valid redirect URI for the app, or `urn:ietf:wg:oauth:2.0:oob`by default.</span></span> <br><br> <span data-ttu-id="4f338-375">アプリの ClientID の許容されるリダイレクト URI として値を構成したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-375">Make sure to configure the value as an acceptable redirect URI for your app's ClientID.</span></span>
    | <span data-ttu-id="4f338-376">SkipBroker</span><span class="sxs-lookup"><span data-stu-id="4f338-376">SkipBroker</span></span> | <span data-ttu-id="4f338-377">False</span><span class="sxs-lookup"><span data-stu-id="4f338-377">False</span></span> |


3. <span data-ttu-id="4f338-378">**アプリは ADAL を統合しますが、仲介型認証/デバイス全体にわたる SSO をサポートしていません。**</span><span class="sxs-lookup"><span data-stu-id="4f338-378">**App integrates ADAL but does not support brokered authentication/device-wide SSO:**</span></span>

    |<span data-ttu-id="4f338-379">必須の ADAL パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f338-379">Required ADAL parameter</span></span>| <span data-ttu-id="4f338-380">値</span><span class="sxs-lookup"><span data-stu-id="4f338-380">Value</span></span> |
    |--|--|
    | <span data-ttu-id="4f338-381">Authority</span><span class="sxs-lookup"><span data-stu-id="4f338-381">Authority</span></span> | <span data-ttu-id="4f338-382">AAD アカウントが構成されている必要な環境</span><span class="sxs-lookup"><span data-stu-id="4f338-382">Desired environment where AAD accounts have been configured</span></span> |
    | <span data-ttu-id="4f338-383">ClientID</span><span class="sxs-lookup"><span data-stu-id="4f338-383">ClientID</span></span> | <span data-ttu-id="4f338-384">アプリの ClientID (アプリが登録されるときに Azure AD によって生成される)</span><span class="sxs-lookup"><span data-stu-id="4f338-384">The app's ClientID (generated by Azure AD when the app is registered)</span></span> |
    | <span data-ttu-id="4f338-385">NonBrokerRedirectURI</span><span class="sxs-lookup"><span data-stu-id="4f338-385">NonBrokerRedirectURI</span></span> | <span data-ttu-id="4f338-386">アプリの有効なリダイレクト URI または既定値の `urn:ietf:wg:oauth:2.0:oob`。</span><span class="sxs-lookup"><span data-stu-id="4f338-386">A valid redirect URI for the app, or `urn:ietf:wg:oauth:2.0:oob` by default.</span></span> <br><br> <span data-ttu-id="4f338-387">アプリの ClientID の許容されるリダイレクト URI として値を構成したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-387">Make sure to configure the value as an acceptable redirect URI for your app's ClientID.</span></span>
    | <span data-ttu-id="4f338-388">SkipBroker</span><span class="sxs-lookup"><span data-stu-id="4f338-388">SkipBroker</span></span> | <span data-ttu-id="4f338-389">**True**</span><span class="sxs-lookup"><span data-stu-id="4f338-389">**True**</span></span> |

## <a name="app-protection-policy-without-device-enrollment"></a><span data-ttu-id="4f338-390">デバイス登録が不要なアプリの保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="4f338-390">App protection policy without device enrollment</span></span>

### <a name="overview"></a><span data-ttu-id="4f338-391">概要</span><span class="sxs-lookup"><span data-stu-id="4f338-391">Overview</span></span>
<span data-ttu-id="4f338-392">デバイス登録のない Intune アプリ保護ポリシー (APP-WE または MAM-WE とも呼ばれる) では、デバイスが Intune MDM に登録されていなくても Intune でアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-392">Intune app protection policy without device enrollment, also known as APP-WE or MAM-WE, allows apps to be managed by Intune without the need for the device to be enrolled Intune MDM.</span></span> <span data-ttu-id="4f338-393">デバイス登録の有無にかかわらず、APP-WE は動作します。</span><span class="sxs-lookup"><span data-stu-id="4f338-393">APP-WE works with or without device enrollment.</span></span> <span data-ttu-id="4f338-394">ポータル サイトは、デバイスにインストールするために必要ですが、ユーザーがポータル サイトにサインインし、デバイスを登録する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f338-394">The Company Portal is still required to be installed on the device, but the user does not need to sign into the Company Portal and enroll the device.</span></span>

> [!NOTE]
> <span data-ttu-id="4f338-395">すべてのアプリは、デバイスの登録なしで、アプリの保護ポリシーをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-395">All apps are required to support app protection policy without device enrollment.</span></span>

### <a name="workflow"></a><span data-ttu-id="4f338-396">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="4f338-396">Workflow</span></span>

<span data-ttu-id="4f338-397">アプリでは、新しいユーザー アカウントを作成するときにIntune アプリ SDK で管理するためにアカウントを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-397">When an app creates a new user account, it should register the account for management with the Intune App SDK.</span></span> <span data-ttu-id="4f338-398">SDK は、APP-WE サービスでのアプリの登録の詳細を処理し、失敗した場合は、必要に応じて適切な時間間隔で登録を再試行します。</span><span class="sxs-lookup"><span data-stu-id="4f338-398">The SDK will handle the details of enrolling the app in the APP-WE service; if necessary, it will retry any enrollments at appropriate time intervals if failures occur.</span></span>

<span data-ttu-id="4f338-399">アプリは、Intune App SDK に対するクエリを実行して、登録済みユーザーのステータスを調べ、ユーザーが会社のコンテンツへのアクセスをブロックするかどうかを判断することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f338-399">The app can also query the Intune App SDK for the status of a registered user to determine if the user should be blocked from accessing corporate content.</span></span> <span data-ttu-id="4f338-400">複数のアカウントを管理のために登録できますが、現在 APP-WE サービスに一度にアクティブに登録できるのは 1 つのアカウントのみです。</span><span class="sxs-lookup"><span data-stu-id="4f338-400">Multiple accounts may be registered for management, but currently only one account can be actively enrolled with the APP-WE service at a time.</span></span> <span data-ttu-id="4f338-401">つまり、アプリでアプリ保護ポリシーを受け取ることができるのは一度に 1 つのアカウントのみです。</span><span class="sxs-lookup"><span data-stu-id="4f338-401">This means only one account on the app can receive app protection policy at a time.</span></span>

<span data-ttu-id="4f338-402">SDK の代わりに Azure Active Directory Authentication Library (ADAL) から適切なアクセス トークンを取得するコールバックを提供するには、アプリが必要です。</span><span class="sxs-lookup"><span data-stu-id="4f338-402">The app is required to provide a callback to acquire the appropriate access token from the Azure Active Directory Authentication Library (ADAL) on behalf of the SDK.</span></span> <span data-ttu-id="4f338-403">アプリがユーザー認証および独自のアクセス トークンを取得するために既に ADAL を使用していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="4f338-403">It is assumed that the app already uses ADAL for user authentication and to acquire its own access tokens.</span></span>

<span data-ttu-id="4f338-404">アプリがアカウントを完全に削除するときは、アプリがそのユーザーのポリシーをこれ以上適用しないことを示すためにそのアカウントを登録解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-404">When the app removes an account completely, it should unregister that account to indicate that the app should no longer apply policy for that user.</span></span> <span data-ttu-id="4f338-405">MAM サービスにユーザーが登録されていた場合、ユーザーの登録が解除され、アプリは消去されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-405">If the user was enrolled in the MAM service, the user will be unenrolled and the app will be wiped.</span></span>


### <a name="overview-of-app-requirements"></a><span data-ttu-id="4f338-406">アプリの要件の概要</span><span class="sxs-lookup"><span data-stu-id="4f338-406">Overview of app requirements</span></span>

<span data-ttu-id="4f338-407">APP-WE 統合を実装するには、アプリが MAM SDK にユーザー アカウントを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-407">To implement APP-WE integration, your app must register the user account with the MAM SDK:</span></span>

1. <span data-ttu-id="4f338-408">アプリは、`MAMServiceAuthenticationCallback` インターフェイスのインスタンスを実装および登録_する必要があります_。</span><span class="sxs-lookup"><span data-stu-id="4f338-408">The app _must_ implement and register an instance of the `MAMServiceAuthenticationCallback` interface.</span></span> <span data-ttu-id="4f338-409">コールバック インスタンスをアプリケーションのライフ サイクルでできるだけ早い段階で登録する必要があります (通常はアプリケーション クラスの `onMAMCreate()` メソッド)。</span><span class="sxs-lookup"><span data-stu-id="4f338-409">The callback instance should be registered as early as possible in the app's lifecycle (typically in the `onMAMCreate()` method of the application class).</span></span>

2. <span data-ttu-id="4f338-410">ユーザー アカウントが作成され、ユーザーが正常に ADAL にサインインしたときに、アプリは、`registerAccountForMAM()` を呼び出す_必要があります_。</span><span class="sxs-lookup"><span data-stu-id="4f338-410">When a user account is created and the user successfully signs in with ADAL, the app _must_ call the `registerAccountForMAM()`.</span></span>

3. <span data-ttu-id="4f338-411">ユーザー アカウントが完全に削除されたときには、アプリは、`unregisterAccountForMAM()` を呼び出して Intune 管理からアカウントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-411">When a user account is completely removed, the app should call `unregisterAccountForMAM()` to remove the account from Intune management.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f338-412">ユーザーがアプリから一時的にサインアウトする場合、アプリは `unregisterAccountForMAM()` を呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f338-412">If a user signs out of the app temporarily, the app does not need to call `unregisterAccountForMAM()`.</span></span> <span data-ttu-id="4f338-413">呼び出しでは、ユーザーの会社のデータを完全に削除するワイプを開始できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-413">The call may initiate a wipe to completely remove corporate data for the user.</span></span>


### <a name="mamenrollmentmanager"></a><span data-ttu-id="4f338-414">MAMEnrollmentManager</span><span class="sxs-lookup"><span data-stu-id="4f338-414">MAMEnrollmentManager</span></span>

<span data-ttu-id="4f338-415">すべての必要な認証および登録 API は、`MAMEnrollmentManager` インターフェイスにあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-415">All the necessary authentication and registration APIs can be found in the `MAMEnrollmentManager` interface.</span></span> <span data-ttu-id="4f338-416">`MAMEnrollmentManager` の参照は、次のように取得できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-416">A reference to the `MAMEnrollmentManager` can be obtained as follows:</span></span>

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr
```

<span data-ttu-id="4f338-417">返された `MAMEnrollmentManager` インスタンスは、null ではないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-417">The `MAMEnrollmentManager` instance returned is guaranteed not to be null.</span></span> <span data-ttu-id="4f338-418">API メソッドは、**認証**と**アカウント登録**という 2 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-418">The API methods fall into two categories: **authentication** and **account registration**.</span></span>

> [!NOTE]
> <span data-ttu-id="4f338-419">`MAMEnrollmentManager` には、すぐに非推奨になる API メソッドがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f338-419">`MAMEnrollmentManager` contains some API methods that will be deprecated soon.</span></span> <span data-ttu-id="4f338-420">わかりやすくするために、次のコード ブロックでは、関連するメソッドと結果のコードのみを示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-420">For clarity, only the relevant methods and result codes are shown in the code block below.</span></span>

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a><span data-ttu-id="4f338-421">アカウントの認証</span><span class="sxs-lookup"><span data-stu-id="4f338-421">Account authentication</span></span>

<span data-ttu-id="4f338-422">このセクションでは、`MAMEnrollmentManager` の認証 API メソッドとそれらの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f338-422">This section describes the authentication API methods in `MAMEnrollmentManager` and how to use them.</span></span>

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. <span data-ttu-id="4f338-423">アプリは、`MAMServiceAuthenticationCallback` インターフェイスを実装し、SDK が特定のユーザーの ADAL トークンとリソース ID を要求できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-423">The app must implement the `MAMServiceAuthenticationCallback` interface to allow the SDK to request an ADAL token for the given user and resource ID.</span></span> <span data-ttu-id="4f338-424">`registerAuthenticationCallback()` メソッドを呼び出すことでコールバック インスタンスを `MAMEnrollmentManager` に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-424">The callback instance must be provided to the `MAMEnrollmentManager` by calling its `registerAuthenticationCallback()` method.</span></span> <span data-ttu-id="4f338-425">アプリのライフサイクルの非常に早い段階で、登録の再試行またはアプリ保護ポリシーの更新チェックインのためにトークンが必要になることがあるので、コールバックの登録の理想的な場所は、アプリの `MAMApplication` サブクラスの `onMAMCreate()` メソッドです。</span><span class="sxs-lookup"><span data-stu-id="4f338-425">A token may be needed very early in the app lifecycle for enrollment retries or app protection policy refresh check-ins, so the ideal place to register the callback is in the `onMAMCreate()` method of the app's `MAMApplication` subclass.</span></span>

2. <span data-ttu-id="4f338-426">`acquireToken()` メソッドは、特定のユーザーの要求されたリソース ID のアクセス トークンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-426">The `acquireToken()` method should acquire the access token for the requested resource ID for the given user.</span></span> <span data-ttu-id="4f338-427">要求されたトークンを取得できない場合は、null を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-427">If it can't acquire the requested token, it should return null.</span></span>

3. <span data-ttu-id="4f338-428">SDK が `acquireToken()` を呼び出すときにアプリがトークンを提供することができない場合 (たとえば、サイレント認証が失敗し、UI を表示するには不都合な期間である場合)、アプリは、`updateToken()` メソッドを呼び出すことによって後でトークンを提供できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-428">In case the app is unable to provide a token when the SDK calls `acquireToken()`  -- for example, if silent authentication fails and it is an inconvenient time to show a UI -- the app can provide a token at a later time by calling the `updateToken()` method.</span></span> <span data-ttu-id="4f338-429">`acquireToken()` の前回の呼び出しで要求されたものと同じ UPN、AAD ID、およびリソース ID を最後に取得されたトークンと合わせて `updateToken()` に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-429">The same UPN, AAD ID, and resource ID that were requested by the prior call to `acquireToken()` must be passed to `updateToken()`, along with the token that was finally acquired.</span></span> <span data-ttu-id="4f338-430">アプリは、指定されたコールバックから null が戻された後に、できるだけ早く、このメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-430">The app should call this method as soon as possible after returning null from the provided callback.</span></span>

> [!NOTE]
> <span data-ttu-id="4f338-431">SDK は、トークンを取得するために `acquireToken()` を定期的に呼び出すので、`updateToken()` の呼び出しは厳密には必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="4f338-431">The SDK will call `acquireToken()` periodically to get the token, so calling `updateToken()` is not strictly required.</span></span> <span data-ttu-id="4f338-432">ただし、これは登録とアプリ保護ポリシーのチェックインを適切なタイミングで完了するためには役立つので推奨されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-432">However, it is recommended as it can help enrollments and app protection policy check-ins complete in a timely manner.</span></span>


### <a name="account-registration"></a><span data-ttu-id="4f338-433">アカウント登録</span><span class="sxs-lookup"><span data-stu-id="4f338-433">Account registration</span></span>

<span data-ttu-id="4f338-434">このセクションでは、`MAMEnrollmentManager` のアカウント登録 API メソッドとそれらの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f338-434">This section describes the account registration API methods in `MAMEnrollmentManager` and how to use them.</span></span>

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. <span data-ttu-id="4f338-435">アカウントを管理用に登録するには、アプリで `registerAccountForMAM()` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-435">To register an account for management, the app should call `registerAccountForMAM()`.</span></span> <span data-ttu-id="4f338-436">ユーザー アカウントは UPN と AAD ユーザー ID の両方で識別されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-436">A user account is identified by both its UPN and its AAD user ID.</span></span> <span data-ttu-id="4f338-437">登録データをユーザーの AAD テナントと関連付けるには、テナント ID も必要です。</span><span class="sxs-lookup"><span data-stu-id="4f338-437">The tenant ID is also required to associate enrollment data with the user's AAD tenant.</span></span> <span data-ttu-id="4f338-438">SDK は MAM サービスで特定のユーザー向けにアプリを登録しようとする場合があります。登録が失敗した場合、アカウントが登録されるまで定期的に登録を再試行します。</span><span class="sxs-lookup"><span data-stu-id="4f338-438">The SDK may attempt to enroll the app for the given user in the MAM service; if enrollment fails, it will periodically retry enrollment until the account is unregistered.</span></span> <span data-ttu-id="4f338-439">再試行の期間は通常 12 ～ 24 時間です。</span><span class="sxs-lookup"><span data-stu-id="4f338-439">The retry period will typically be 12-24 hours.</span></span> <span data-ttu-id="4f338-440">SDK は、通知を使用して非同期的に登録の試行の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-440">The SDK provides the status of enrollment attempts asynchronously via notifications.</span></span>

2. <span data-ttu-id="4f338-441">AAD 認証が必要なため、ユーザー アカウントを登録する最適なタイミングは、ユーザーがアプリケーションにサインインし、ADAL を使用して正常に認証した後です。</span><span class="sxs-lookup"><span data-stu-id="4f338-441">Because AAD authentication is required, the best time to register the user account is after the user has signed into the app and is successfully authenticated using ADAL.</span></span>
    * <span data-ttu-id="4f338-442">[`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android) オブジェクトの一部として、ユーザーの AAD ID とテナント ID が ADAL 認証呼び出しから返されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-442">The user's AAD ID and tenant ID are returned from the ADAL authentication call as part of the [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android) object.</span></span> <span data-ttu-id="4f338-443">テナント ID は、`AuthenticationResult.getTenantID()` メソッドから取得されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-443">The tenant ID comes from the `AuthenticationResult.getTenantID()` method.</span></span>
    * <span data-ttu-id="4f338-444">ユーザーに関する情報は、`AuthenticationResult.getUserInfo()` から取得される `UserInfo` 型のサブオブジェクトで見つかり、AAD ユーザー ID は `UserInfo.getUserId()` を呼び出すオブジェクトから取得されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-444">Information about the user is found in a sub-object of type `UserInfo` that comes from `AuthenticationResult.getUserInfo()`, and the AAD user ID is retrieved from that object by calling `UserInfo.getUserId()`.</span></span>

3. <span data-ttu-id="4f338-445">アカウントを Intune 管理から登録解除するには、アプリで `unregisterAccountForMAM()` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-445">To unregister an account from Intune management, the app should call `unregisterAccountForMAM()`.</span></span> <span data-ttu-id="4f338-446">アカウントが正常に登録されて管理される場合、SDK は、アカウントの登録を解除し、そのデータを消去します。</span><span class="sxs-lookup"><span data-stu-id="4f338-446">If the account has been successfully enrolled and is managed, the SDK will unenroll the account and wipe its data.</span></span> <span data-ttu-id="4f338-447">アカウントの定期的な登録の再試行は停止されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-447">Periodic enrollment retries for the account will be stopped.</span></span> <span data-ttu-id="4f338-448">SDK は、通知を使用して非同期的に登録の試行の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-448">The SDK provides the status of unenrollment request asynchronously via notifications.</span></span>

### <a name="important-implementation-notes"></a><span data-ttu-id="4f338-449">実装に関する重要なメモ</span><span class="sxs-lookup"><span data-stu-id="4f338-449">Important implementation notes</span></span>

#### <a name="authentication"></a><span data-ttu-id="4f338-450">認証</span><span class="sxs-lookup"><span data-stu-id="4f338-450">Authentication</span></span>

* <span data-ttu-id="4f338-451">アプリが `registerAccountForMAM()` を呼び出したときに、`MAMServiceAuthenticationCallback` インターフェイスで直後に異なるスレッドでコールバックを受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-451">When the app calls `registerAccountForMAM()`, it may receive a callback on its `MAMServiceAuthenticationCallback` interface shortly thereafter, on a different thread.</span></span> <span data-ttu-id="4f338-452">**MAMService トークン**の取得を早めるために、アプリがアカウントを登録する前に ADAL から専用のトークンを取得しているの理想的です。</span><span class="sxs-lookup"><span data-stu-id="4f338-452">Ideally, the app acquired its own token from ADAL prior to registering the account to expedite the acquisition of the **MAMService token**.</span></span> <span data-ttu-id="4f338-453">アプリが、コールバックから有効なトークンを返す場合は、登録処理が続行され、アプリが通知を使用して最終的な結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="4f338-453">IF the app returns a valid token from the callback, enrollment will proceed and the app will get the final result via a notification.</span></span>

* <span data-ttu-id="4f338-454">アプリが有効な AAD トークンを返さない場合、登録の試行の最終的な結果は `AUTHENTICATION_NEEDED` になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-454">If the app doesn't return a valid AAD token, the final result from the enrollment attempt will be `AUTHENTICATION_NEEDED`.</span></span> <span data-ttu-id="4f338-455">アプリが通知を介してこの結果を受信する場合、アプリは、**MAMService トークン**を取得して `updateToken()` メソッドを呼び出してもう一度登録プロセスを開始することで登録プロセスを早めます。</span><span class="sxs-lookup"><span data-stu-id="4f338-455">If the app receives this Result via notification, it can expedite the enrollment process by acquiring the **MAMService token** and calling the `updateToken()` method to initiate the enrollment process again.</span></span> <span data-ttu-id="4f338-456">ただし、SDK は登録を定期的に再試行してトークンを取得するためのコールバックを呼び出すので、これは確実な要件_ではありません_。</span><span class="sxs-lookup"><span data-stu-id="4f338-456">This is _not_ a firm requirement, however, since the SDK retries enrollment periodically and invokes the callback to acquire the token.</span></span>

* <span data-ttu-id="4f338-457">アプリの登録済みの `MAMServiceAuthenticationCallback` は、定期的なアプリ保護ポリシー更新チェックイン時にトークンを取得するためにも呼び出されます。アプリが要求されたときにトークンを提供できない場合、通知は得られませんが、トークンの取得を試行する必要があり、チェックイン プロセスの時間を短縮するために次の便利な時刻に `updateToken()` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-457">The app's registered `MAMServiceAuthenticationCallback` will also be called to acquire a token for periodic app protection policy refresh check-ins. If the app is unable to provide a token when requested, it will not get a notification, but it should attempt to acquire a token and call `updateToken()` at the next convenient time to expedite the check-in process.</span></span> <span data-ttu-id="4f338-458">トークンが提供されていない場合、次のチェックインの試行時にコールバックも引き続き呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-458">If a token is not provided, the callback will still be called at the next check-in attempt.</span></span>

#### <a name="registration"></a><span data-ttu-id="4f338-459">登録</span><span class="sxs-lookup"><span data-stu-id="4f338-459">Registration</span></span>

* <span data-ttu-id="4f338-460">参考までに、登録メソッドはべき等です。たとえば、`registerAccountForMAM()` はアカウントのみを登録し、アカウントがまだ登録されていない場合はアプリを登録しようとします。`unregisterAccountForMAM()` はアカウントが現在登録されている場合にのみ登録解除します。</span><span class="sxs-lookup"><span data-stu-id="4f338-460">For your convenience, the registration methods are idempotent; for example, `registerAccountForMAM()`will only register an account and attempt to enroll the app if the account is not already registered, and `unregisterAccountForMAM()` will only unregister an account if it is currently registered.</span></span> <span data-ttu-id="4f338-461">後続の呼び出しは操作不要なので、これらのメソッドを複数回呼び出しても弊害はありません。</span><span class="sxs-lookup"><span data-stu-id="4f338-461">Subsequent calls are no-ops, so there is no harm in calling these methods more than once.</span></span> <span data-ttu-id="4f338-462">さらに、これらのメソッドの呼び出しと結果の通知の対応は保証されません。つまり、既に登録されている ID のために `registerAccountForMAM` が呼び出された場合、その ID の通知は再び送信されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-462">Additionally, correspondence between calls to these methods and notifications of results are not guaranteed: i.e. if `registerAccountForMAM` is called for an identity that is already registered, the notification may not be sent again for that identity.</span></span> <span data-ttu-id="4f338-463">SDK では、バック グラウンドで定期的に登録を試みることがあり、登録は、Intune サービスから受信したワイプ要求によって発生する可能性があるので、これらのメソッドへの呼び出しに対応していない通知が送信される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-463">It is possible that notifications are sent that don't correspond to any calls to these methods, since the SDK may periodically try enrollments in the background, and unenrollments may be triggered by wipe requests received from the Intune service.</span></span>

* <span data-ttu-id="4f338-464">登録メソッドは、任意の数の異なる ID のために呼び出すことができますが、現在、正常に登録できるのは、1 つのユーザー アカウントだけです。</span><span class="sxs-lookup"><span data-stu-id="4f338-464">The registration methods can be called for any number of different identities, but currently only one user account can become successfully enrolled.</span></span> <span data-ttu-id="4f338-465">Intune のライセンスが付与され、アプリの保護ポリシーの対象となる複数のユーザー アカウントが登録される場合、またはほとんど同じ時刻に登録される場合、どのアカウントが競合に勝つかは保証されていません。</span><span class="sxs-lookup"><span data-stu-id="4f338-465">If multiple user accounts that are licensed for Intune and targeted by app protection policy are registered at or near the same time, there is no guarantee on which one will win the race.</span></span>

* <span data-ttu-id="4f338-466">最後に、`MAMEnrollmentManager` に対してクエリを実行し、特定のアカウントが登録されているかどうかを確認し、`getRegisteredAccountStatus` メソッドを使用して現在のステータスを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-466">Finally, you can query the `MAMEnrollmentManager` to see if a particular account is registered and to get its current status using the `getRegisteredAccountStatus` method.</span></span> <span data-ttu-id="4f338-467">指定したアカウントが登録されていない場合、このメソッドは **null** を返します。</span><span class="sxs-lookup"><span data-stu-id="4f338-467">If the provided account is not registered, this method will return **null**.</span></span> <span data-ttu-id="4f338-468">アカウントが登録されている場合、このメソッドは、`MAMEnrollmentManager.Result` 列挙のいずれかのメンバーとしてアカウントのステータスを返します。</span><span class="sxs-lookup"><span data-stu-id="4f338-468">If the account is registered, this method will return the account's status as one of the members of the `MAMEnrollmentManager.Result` enumeration.</span></span>

### <a name="result-and-status-codes"></a><span data-ttu-id="4f338-469">結果とステータス コード</span><span class="sxs-lookup"><span data-stu-id="4f338-469">Result and status codes</span></span>

<span data-ttu-id="4f338-470">アカウントが最初に登録されているときに、`PENDING` 状態で始まり、最初の MAM サービスの登録の試行が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-470">When an account is first registered, it begins in the `PENDING` state, indicating that the initial MAM service enrollment attempt is incomplete.</span></span> <span data-ttu-id="4f338-471">登録の試行が終了すると、次の表の結果コードのいずれかで通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-471">After the enrollment attempt finishes, a notification will be sent with one of the Result codes in the table below.</span></span> <span data-ttu-id="4f338-472">さらに、`getRegisteredAccountStatus()` メソッドは、アカウントのステータスを返すので、アプリは、そのユーザーの会社のコンテンツへのアクセスがブロックされているかどうかを常に特定できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-472">In addition, the `getRegisteredAccountStatus()` method will return the account's status so the app can always determine if access to corporate content is blocked for that user.</span></span> <span data-ttu-id="4f338-473">登録の試行に失敗した場合、アカウントのステータスは、バック グラウンドで SDK が登録を再試行するときに随時変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-473">If the enrollment attempt fails, the account's status may change over time as the SDK retries enrollment in the background.</span></span>

|<span data-ttu-id="4f338-474">結果コード</span><span class="sxs-lookup"><span data-stu-id="4f338-474">Result code</span></span> | <span data-ttu-id="4f338-475">説明</span><span class="sxs-lookup"><span data-stu-id="4f338-475">Explanation</span></span> |
| -- | -- |
|<span data-ttu-id="4f338-476">AUTHORIZATION_NEEDED</span><span class="sxs-lookup"><span data-stu-id="4f338-476">AUTHORIZATION_NEEDED</span></span> | <span data-ttu-id="4f338-477">この結果は、トークンがアプリの登録済みの `MAMServiceAuthenticationCallback` インスタンスによって提供されていないこと、または指定されたトークンが無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-477">This result indicates that a token was not provided by the app’s registered `MAMServiceAuthenticationCallback` instance, or the provided token was invalid.</span></span>  <span data-ttu-id="4f338-478">アプリは、可能な場合は、有効なトークンを取得し、`updateToken()` を呼び出す必要があります</span><span class="sxs-lookup"><span data-stu-id="4f338-478">The app should acquire a valid token and call `updateToken()` if possible.</span></span> |
| <span data-ttu-id="4f338-479">NOT_LICENSED</span><span class="sxs-lookup"><span data-stu-id="4f338-479">NOT_LICENSED</span></span> | <span data-ttu-id="4f338-480">Intune で、ユーザーがライセンスされていない、または Intune MAM サービスへの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4f338-480">The user is not licensed for Intune, or the attempt to contact the Intune MAM service failed.</span></span>  <span data-ttu-id="4f338-481">管理されていない (標準の) 状態で、アプリが続行され、ユーザーがブロックされていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-481">The app should continue in an unmanaged (normal) state and the user should not be blocked.</span></span>  <span data-ttu-id="4f338-482">将来的にユーザーがライセンスされる場合、登録が定期的に再試行されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-482">Enrollments will be retried periodically in case the user becomes licensed in the future.</span></span> |
| <span data-ttu-id="4f338-483">ENROLLMENT_SUCCEEDED</span><span class="sxs-lookup"><span data-stu-id="4f338-483">ENROLLMENT_SUCCEEDED</span></span> | <span data-ttu-id="4f338-484">登録の試行が成功したか、ユーザーが既に登録されています。</span><span class="sxs-lookup"><span data-stu-id="4f338-484">The enrollment attempt succeeded, or the user is already enrolled.</span></span>  <span data-ttu-id="4f338-485">登録に成功する場合は、この通知の前にポリシーの更新通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-485">In the case of a successful enrollment, a policy refresh notification will be sent before this notification.</span></span>  <span data-ttu-id="4f338-486">会社のデータへのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-486">Access to corporate data should be allowed.</span></span> |
| <span data-ttu-id="4f338-487">ENROLLMENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="4f338-487">ENROLLMENT_FAILED</span></span> | <span data-ttu-id="4f338-488">登録の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4f338-488">The enrollment attempt failed.</span></span>  <span data-ttu-id="4f338-489">さらに詳細な情報がデバイス ログにあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-489">Further details can be found in the device logs.</span></span>  <span data-ttu-id="4f338-490">ユーザーが Intune にライセンスされていることが以前に判断されたために、アプリはこの状態で、会社へのアクセスを許可しません。</span><span class="sxs-lookup"><span data-stu-id="4f338-490">The app should not allow access to corporate in this state, since it was previously determined that the user is licensed for Intune.</span></span>|
| <span data-ttu-id="4f338-491">WRONG_USER</span><span class="sxs-lookup"><span data-stu-id="4f338-491">WRONG_USER</span></span> | <span data-ttu-id="4f338-492">デバイスごとに 1 つのユーザーだけが、MAM サービスにアプリを登録できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-492">Only one user per device can enroll an app with the MAM service.</span></span>  <span data-ttu-id="4f338-493">別のユーザーとして正常に登録するためには、登録されているすべてのアプリが最初に登録解除される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-493">In order to enroll successfully as a different user, all enrolled apps must be unenrolled first.</span></span>  <span data-ttu-id="4f338-494">それ以外の場合、このアプリは、プライマリ ユーザーとして登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-494">Otherwise, this app must enroll as the primary user.</span></span>  <span data-ttu-id="4f338-495">このチェックは、ライセンスチェックの後に実行されるので、アプリが正常に登録されるまで、ユーザーは企業データへのアクセスをブロックされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-495">This check happens after the license check, so the user should be blocked from accessing corporate data until the app is successfully enrolled.</span></span>|
| <span data-ttu-id="4f338-496">UNENROLLMENT_SUCCEEDED</span><span class="sxs-lookup"><span data-stu-id="4f338-496">UNENROLLMENT_SUCCEEDED</span></span> | <span data-ttu-id="4f338-497">登録解除が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="4f338-497">Unenrollment was successful.</span></span>|
| <span data-ttu-id="4f338-498">UNENROLLMENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="4f338-498">UNENROLLMENT_FAILED</span></span> | <span data-ttu-id="4f338-499">登録解除要求が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4f338-499">The unenrollment request failed.</span></span>  <span data-ttu-id="4f338-500">さらに詳細な情報がデバイス ログにあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-500">Further details can be found in the device logs.</span></span> |
| <span data-ttu-id="4f338-501">PENDING</span><span class="sxs-lookup"><span data-stu-id="4f338-501">PENDING</span></span> | <span data-ttu-id="4f338-502">ユーザーの初期登録の試行が進行中です。</span><span class="sxs-lookup"><span data-stu-id="4f338-502">The initial enrollment attempt for the user is in progress.</span></span>  <span data-ttu-id="4f338-503">アプリは、登録の結果がわかるまで、会社のデータへのアクセスをブロックできますが、この処理は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="4f338-503">The app can block access to corporate data until the enrollment result is known, but is not required to do so.</span></span> |
| <span data-ttu-id="4f338-504">COMPANY_PORTAL_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="4f338-504">COMPANY_PORTAL_REQUIRED</span></span> | <span data-ttu-id="4f338-505">Intune でユーザーがライセンスされていますが、ポータル サイト アプリがデバイスにインストールされるまで、アプリを登録することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f338-505">The user is licensed for Intune, but the app cannot be enrolled until the Company Portal app is installed on the device.</span></span> <span data-ttu-id="4f338-506">Intune アプリ SDK は、特定のユーザーのアプリへのアクセスをブロックし、ポータル サイト アプリ (詳細については以下を参照してください) をインストールすることをユーザーに指示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-506">The Intune App SDK will attempt to block access to the app for the given user and direct them to install the Company Portal app (see below for details).</span></span> |


### <a name="company-portal-requirement-prompt-override-optional"></a><span data-ttu-id="4f338-507">ポータル サイトの要件のプロンプトの上書き (省略可能)</span><span class="sxs-lookup"><span data-stu-id="4f338-507">Company Portal requirement prompt override (optional)</span></span>

<span data-ttu-id="4f338-508">`COMPANY_PORTAL_REQUIRED` の結果が受信された場合、SDK は登録が要求された対象の ID を使用したアクティビティの使用をブロックします。</span><span class="sxs-lookup"><span data-stu-id="4f338-508">If the `COMPANY_PORTAL_REQUIRED` Result is received, the SDK will block use of activities that use the identity for which enrollment was requested.</span></span> <span data-ttu-id="4f338-509">代わりに、SDK は、それらアクティビティでポータル サイトをダウンロードするためのプロンプトを表示させます。</span><span class="sxs-lookup"><span data-stu-id="4f338-509">Instead, the SDK will cause those activities to display a prompt to download the Company Portal.</span></span> <span data-ttu-id="4f338-510">アプリでこの動作を回避する場合は、アクティビティで `MAMActivity.onMAMCompanyPortalRequired` を実装できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-510">If you want to prevent this behavior in your app, activities may implement `MAMActivity.onMAMCompanyPortalRequired`.</span></span>

<span data-ttu-id="4f338-511">このメソッドは、SDK が既定の UI のブロックを表示する前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-511">This method is called before the SDK displays its default blocking UI.</span></span> <span data-ttu-id="4f338-512">アプリが、アクティビティ ID を変更するか、登録しようとしたユーザーの登録を解除した場合、SDK は、アクティビティはブロックしません。</span><span class="sxs-lookup"><span data-stu-id="4f338-512">If the app changes the activity identity or unregisters the user who attempted to enroll, the SDK will not block the activity.</span></span> <span data-ttu-id="4f338-513">この場合、会社のデータのリークを防ぐことはアプリの責任です。</span><span class="sxs-lookup"><span data-stu-id="4f338-513">In this situation, it is up to the app to avoid leaking corporate data.</span></span>

### <a name="notifications"></a><span data-ttu-id="4f338-514">通知</span><span class="sxs-lookup"><span data-stu-id="4f338-514">Notifications</span></span>

<span data-ttu-id="4f338-515">登録要求が完了したことをアプリに通知するために新しい種類の `MAMNotification` が追加されました。</span><span class="sxs-lookup"><span data-stu-id="4f338-515">A new type of `MAMNotification` has been added in order to inform the app that the enrollment request has completed.</span></span>  <span data-ttu-id="4f338-516">「[SDK からの通知の登録](#register-for-notifications-from-the-sdk)」 セクションで説明されているように、`MAMNotificationReceiver` インターフェイスから `MAMEnrollmentNotification` を受信します。</span><span class="sxs-lookup"><span data-stu-id="4f338-516">The `MAMEnrollmentNotification` will be received through the `MAMNotificationReceiver` interface as described in the [Register for notifications from the SDK](#register-for-notifications-from-the-sdk) section.</span></span>

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}
```

<span data-ttu-id="4f338-517">`getEnrollmentResult()` メソッドは、登録要求の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="4f338-517">The `getEnrollmentResult()` method returns the result of the enrollment request.</span></span>  <span data-ttu-id="4f338-518">`MAMEnrollmentNotification` は、`MAMUserNotification` を拡張するので、登録が試行されたユーザーの ID も利用できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-518">Since `MAMEnrollmentNotification` extends `MAMUserNotification`, the identity of the user for whom the enrollment was attempted is also available.</span></span> <span data-ttu-id="4f338-519">アプリは、これらの通知を受信するために `MAMNotificationReceiver` インターフェイスを実装する必要があります。詳細については、「[SDK からの通知の登録](#Register-for-notifications-from-the-SDK)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-519">The app must implement the `MAMNotificationReceiver` interface to receive these notifications, detailed in the [Register for notifications from the SDK](#Register-for-notifications-from-the-SDK) section.</span></span>

<span data-ttu-id="4f338-520">登録通知を受け取ると、登録済みユーザーのアカウントのステータスが変更されることがありますが、場合によっては変更されないことがあります (たとえば、`WRONG_USER` などのより多くの情報がある結果の後に `AUTHORIZATION_NEEDED` 通知を受信した場合、より多くの情報がある結果がアカウントのステータスとして維持されます)。</span><span class="sxs-lookup"><span data-stu-id="4f338-520">The registered user account's status may change when an enrollment notification is received, but it will not change in some cases (e.g. if `AUTHORIZATION_NEEDED` notification is received after a more informative result such as `WRONG_USER`, the more informative result will be maintained as the account's status)</span></span>


## <a name="protecting-backup-data"></a><span data-ttu-id="4f338-521">バックアップ データの保護</span><span class="sxs-lookup"><span data-stu-id="4f338-521">Protecting Backup data</span></span>

<span data-ttu-id="4f338-522">Android Marshmallow (API 23) 以降、Android ではアプリのデータをバックアップする方法が 2 つになりました。</span><span class="sxs-lookup"><span data-stu-id="4f338-522">As of Android Marshmallow (API 23), Android has two ways for an app to back up its data.</span></span> <span data-ttu-id="4f338-523">各オプションはアプリで使用でき、Intune データ保護が正しく実装されていることを確認するには異なる手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-523">Each option is available to your app and requires different steps to ensure that Intune data protection is correctly implemented.</span></span> <span data-ttu-id="4f338-524">適切なデータ保護の動作に必要な、対応するアクションについては、次の表で確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-524">You can review the table below on corresponding actions required for correct data protection behavior.</span></span>  <span data-ttu-id="4f338-525">バックアップ方法の詳細については、[Android API ガイド](http://developer.android.com/guide/topics/data/backup.html)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-525">You can read more about the backup methods in the [Android API guide](http://developer.android.com/guide/topics/data/backup.html).</span></span>

### <a name="auto-backup-for-apps"></a><span data-ttu-id="4f338-526">アプリの自動バックアップ</span><span class="sxs-lookup"><span data-stu-id="4f338-526">Auto Backup for Apps</span></span>

<span data-ttu-id="4f338-527">Android では、アプリのターゲット API に関係なく、Android Marshmallow デバイス上のアプリのために、[自動完全バックアップ](https://developer.android.com/guide/topics/data/autobackup.html)が Google Drive に提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4f338-527">Android began offering [automatic full backups](https://developer.android.com/guide/topics/data/autobackup.html) to Google Drive for apps on Android Marshmallow devices, regardless of the app's target API.</span></span> <span data-ttu-id="4f338-528">AndroidManifest.xml で、明示的に `android:allowBackup` を **false** に設定すると、アプリは Android でバックアップのためにキューに入れられなくなり、"企業" データはアプリ内に残ります。</span><span class="sxs-lookup"><span data-stu-id="4f338-528">In your AndroidManifest.xml, if you explicitly set `android:allowBackup` to **false**, then your app will never be queued for backups by Android and "corporate" data will stay within the app.</span></span> <span data-ttu-id="4f338-529">この場合、これ以上何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f338-529">In this case, no further action is necessary.</span></span>

<span data-ttu-id="4f338-530">ただし、`android:allowBackup` がマニフェスト ファイルで指定されていない場合でも、`android:allowBackup` 属性は既定で true に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-530">However, by default the `android:allowBackup` attribute is set to true, even if `android:allowBackup` isn't specified in the manifest file.</span></span> <span data-ttu-id="4f338-531">つまり、すべてのアプリ データがユーザーの Google ドライブ アカウントに自動的にバックアップされます。これは既定の動作で、**データ漏えいのリスク**を引き起こすものです。</span><span class="sxs-lookup"><span data-stu-id="4f338-531">This means all app data is automatically backed up to the user's Google Drive account, a default behavior that poses a **data leak risk**.</span></span> <span data-ttu-id="4f338-532">したがって、データ保護が適用されるようにするために、SDK を変更する必要があります。その概要について以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-532">Therefore, the SDK requires the changes outlined below to ensure that data protection is applied.</span></span>  <span data-ttu-id="4f338-533">アプリを Android Marshmallow デバイスで実行する場合は、以下のガイドラインに従って、顧客データを適切に保護することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4f338-533">It is important to follow the guidelines  below to protect customer data properly if you want your app to run on Android Marshmallow devices.</span></span>  

<span data-ttu-id="4f338-534">Intune では、XML でカスタム ルールを定義する機能など、Android から利用可能な[自動バックアップ機能](https://developer.android.com/guide/topics/data/autobackup.html)を利用できますが、データを保護するには以下の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-534">Intune allows you to utilize all the [Auto Backup features](https://developer.android.com/guide/topics/data/autobackup.html) available from Android, including the ability to define custom rules in XML, but you must follow the steps below to secure your data:</span></span>

1. <span data-ttu-id="4f338-535">アプリで専用のカスタム BackupAgent を使用**しない**場合、既定の MAMBackupAgent を使用して、Intune ポリシー準拠の自動完全バックアップを可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-535">If your app does **not** use its own custom BackupAgent, use the default MAMBackupAgent to allow for automatic full backups that are Intune policy compliant.</span></span> <span data-ttu-id="4f338-536">これを行う場合は、このバックアップ エージェントには適用されない `android:fullBackupOnly` マニフェスト属性を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-536">If you do this, you can ignore the `android:fullBackupOnly` manifest attribute, as it’s not applicable for our backup agent.</span></span> <span data-ttu-id="4f338-537">アプリのマニフェストに次を配置します。</span><span class="sxs-lookup"><span data-stu-id="4f338-537">Place the following in the app manifest:</span></span>

    ```xml
   android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```


2. <span data-ttu-id="4f338-538">**[省略可能]** 省略可能なカスタム BackupAgent を実装した場合は、MAMBackupAgent または MAMBackupAgentHelper を使用することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-538">**[Optional]** If you implemented an optional custom BackupAgent, you need to make sure to use MAMBackupAgent or MAMBackupAgentHelper.</span></span> <span data-ttu-id="4f338-539">次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-539">See the following sections.</span></span> <span data-ttu-id="4f338-540">Android M 以上でのバックアップが簡易化される、Intune の **MAMDefaultFullBackupAgent** (手順 1 で説明) の使用に切り替えることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-540">Consider switching to using Intune's **MAMDefaultFullBackupAgent** (described in step 1) which provides easy back up on Android M and above.</span></span>

3. <span data-ttu-id="4f338-541">アプリで受信する必要がある完全バックアップの種類 (フィルター適用なし、フィルター適用、なし) を決定する際に、アプリで属性 `android:fullBackupContent` を true、false、または XML リソースに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-541">When you decide which type of full backup your app should receive (unfiltered, filtered, or none) you'll need to set the attribute `android:fullBackupContent`  to true, false, or an XML resource in your app.</span></span>

4. <span data-ttu-id="4f338-542">その後で、マニフェストで `android:fullBackupContent` に配置するものはすべて、`com.microsoft.intune.mam.FullBackupContent` という名前のメタデータにコピー_**する必要があります**_。</span><span class="sxs-lookup"><span data-stu-id="4f338-542">Then, you _**must**_ copy whatever you put into `android:fullBackupContent` into a metadata tag named `com.microsoft.intune.mam.FullBackupContent` in the manifest.</span></span>

    <span data-ttu-id="4f338-543">**例 1**: 例外なしにアプリで完全バックアップを実行する場合、`android:fullBackupContent` 属性と `com.microsoft.intune.mam.FullBackupContent` メタデータ タグの両方を **true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4f338-543">**Example 1**: If you want your app to have full backups without exclusions, set both the `android:fullBackupContent` attribute and `com.microsoft.intune.mam.FullBackupContent` metadata tag to **true**:</span></span>

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    <span data-ttu-id="4f338-544">**例 2**: アプリでカスタム BackupAgent を使用して、完全な Intune ポリシー互換の自動バックアップを停止する場合は、この属性とメタデータ タグを **false** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-544">**Example 2**: If you want your app to use its custom BackupAgent and opt out of full, Intune policy compliant, automatic backups, you must set the attribute and metadata tag to **false**:</span></span>

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    <span data-ttu-id="4f338-545">**例 3**: アプリで XML ファイルで定義したカスタム ルールに従って完全バックアップを使用する場合は、この属性とメタデータ タグを同じ XML リソースに設定してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-545">**Example 3**: If you want your app to have full backups according to your custom rules defined in an XML file, please set the attribute and metadata tag to the same XML resource:</span></span>

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <a name="keyvalue-backup"></a><span data-ttu-id="4f338-546">キー/値のバックアップ</span><span class="sxs-lookup"><span data-stu-id="4f338-546">Key/Value Backup</span></span>

<span data-ttu-id="4f338-547">すべての API 8+ で[キー/値のバックアップ](https://developer.android.com/guide/topics/data/keyvaluebackup.html) オプションを使用して、アプリ データを [Android バックアップ サービス](https://developer.android.com/google/backup/index.html)にアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-547">The [Key/Value Backup](https://developer.android.com/guide/topics/data/keyvaluebackup.html) option is available to all APIs 8+ and uploads app data to the [Android Backup Service](https://developer.android.com/google/backup/index.html).</span></span> <span data-ttu-id="4f338-548">アプリのユーザーごとのデータの量は 5 MB に制限されています。</span><span class="sxs-lookup"><span data-stu-id="4f338-548">The amount of data per user of your app is limited to 5MB.</span></span> <span data-ttu-id="4f338-549">キー/値のバックアップを使用する場合、**BackupAgentHelper** または **BackupAgent** を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-549">If you use Key/Value Backup, you must use a **BackupAgentHelper** or a **BackupAgent**.</span></span>

### <a name="backupagenthelper"></a><span data-ttu-id="4f338-550">BackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-550">BackupAgentHelper</span></span>

<span data-ttu-id="4f338-551">Android のネイティブな機能と Intune MAM 統合の両方の面で、BackupAgentHelper の実装は BackupAgent よりも簡単です。</span><span class="sxs-lookup"><span data-stu-id="4f338-551">BackupAgentHelper is easier to implement than BackupAgent both in terms of native Android functionality and Intune MAM integration.</span></span> <span data-ttu-id="4f338-552">BackupAgentHelper を使用すると、開発者は、**FileBackupHelper** および **SharedPreferencesBackupHelper** に、それぞれ、ファイル全体または共有の設定を登録することができ、これらは、作成時に BackupAgentHelper に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-552">BackupAgentHelper allows the developer to register entire files and shared preferences to a **FileBackupHelper** and **SharedPreferencesBackupHelper** (respectively) which are then added to the BackupAgentHelper upon creation.</span></span> <span data-ttu-id="4f338-553">Intune MAM で、BackupAgentHelper を使用するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4f338-553">Follow the steps below to use a BackupAgentHelper with Intune MAM:</span></span>

1. <span data-ttu-id="4f338-554">BackupAgentHelper で従って、複数 ID のバックアップを使用するには、「[Extending BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper)」(BackupAgent の拡張) についての Android のガイドに従います。</span><span class="sxs-lookup"><span data-stu-id="4f338-554">To utilize multi-identity backup with a BackupAgentHelper, follow the Android guide to [Extending BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper).</span></span>

2. <span data-ttu-id="4f338-555">クラスで BackupAgentHelper、FileBackupHelper、および SharedPreferencesBackupHelper と同等の MAM を拡張します。</span><span class="sxs-lookup"><span data-stu-id="4f338-555">Have your class extend the MAM equivalent of BackupAgentHelper, FileBackupHelper, and SharedPreferencesBackupHelper.</span></span>

|<span data-ttu-id="4f338-556">Android クラス</span><span class="sxs-lookup"><span data-stu-id="4f338-556">Android class</span></span> | <span data-ttu-id="4f338-557">MAM の同等クラス</span><span class="sxs-lookup"><span data-stu-id="4f338-557">MAM equivalent</span></span> |
|--|--|
|<span data-ttu-id="4f338-558">BackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-558">BackupAgentHelper</span></span> |<span data-ttu-id="4f338-559">MAMBackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-559">MAMBackupAgentHelper</span></span> |
|<span data-ttu-id="4f338-560">FileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-560">FileBackupHelper</span></span> | <span data-ttu-id="4f338-561">MAMFileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-561">MAMFileBackupHelper</span></span>
|<span data-ttu-id="4f338-562">SharedPreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-562">SharedPreferencesBackupHelper</span></span>| <span data-ttu-id="4f338-563">MAMSharedPreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="4f338-563">MAMSharedPreferencesBackupHelper</span></span>|

<span data-ttu-id="4f338-564">複数 ID のバックアップと復元を正常に実行するために、以下のガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="4f338-564">Following these guidelines will lead to a successful multi-identity backup and restore.</span></span>

### <a name="backupagent"></a><span data-ttu-id="4f338-565">BackupAgent</span><span class="sxs-lookup"><span data-stu-id="4f338-565">BackupAgent</span></span>

<span data-ttu-id="4f338-566">BackupAgent を使用すると、バックアップの対象とするデータをより明示的に指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-566">A BackupAgent allows you to be much more explicit about what data is backed up.</span></span> <span data-ttu-id="4f338-567">実装に対する開発者の責任が大きくなるため、Intune からの適切なデータ保護を適用するために必要となる手順が増加します。</span><span class="sxs-lookup"><span data-stu-id="4f338-567">Because the developer is fairly responsible for the implementation, there are more steps required to ensure appropriate data protection from Intune.</span></span> <span data-ttu-id="4f338-568">開発者が作業のほとんどを担うことで、Intune 統合は少し複雑になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-568">Since most of the work is pushed onto you, the developer, Intune integration is slightly more involved.</span></span>

<span data-ttu-id="4f338-569">**MAM の統合:**</span><span class="sxs-lookup"><span data-stu-id="4f338-569">**Integrate MAM:**</span></span>

1. <span data-ttu-id="4f338-570">[キー/値のバックアップ](https://developer.android.com/guide/topics/data/keyvaluebackup.html)に関する Android ガイド (特に「[Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent)」 (BackupAgent の拡張) セクション) をよく読み、BackupAgent の実装が Android のガイドラインに従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-570">Please carefully read the Android guide for [Key/Value Backup](https://developer.android.com/guide/topics/data/keyvaluebackup.html) and specifically [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) to ensure your BackupAgent implementation follows Android guidelines.</span></span>

2. <span data-ttu-id="4f338-571">クラスで `MAMBackupAgent` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="4f338-571">Have your class extend `MAMBackupAgent`.</span></span>

<span data-ttu-id="4f338-572">**複数 ID のバックアップ:**</span><span class="sxs-lookup"><span data-stu-id="4f338-572">**Multi-identity Backup:**</span></span>

1. <span data-ttu-id="4f338-573">バックアップを開始する前に、バックアップする予定のファイルまたはデータのバッファーの**複数 ID によるバックアップが実際に IT 管理者によって許可されている**ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-573">Before beginning your backup, check that the files or data buffers you plan to back up are indeed **permitted by the IT administrator to be backed up** in multi-identity scenarios.</span></span> <span data-ttu-id="4f338-574">これを判断するために、`MAMFileProtectionManager` および `MAMDataProtectionManager` で `isBackupAllowed` 関数を提供しています。</span><span class="sxs-lookup"><span data-stu-id="4f338-574">We provide you with the `isBackupAllowed` function in `MAMFileProtectionManager` and `MAMDataProtectionManager` to determine this.</span></span> <span data-ttu-id="4f338-575">ファイルまたはデータ バッファーのバックアップが許可されていない場合、バックアップに引き続き含まれないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-575">If the file or data buffer is not allowed to be backed up, then you should not continue including it in your backup.</span></span>

2. <span data-ttu-id="4f338-576">バックアップ中のある時点で、手順 1 で確認したファイルの ID をバックアップする場合は、データの抽出元ファイルで `backupMAMFileIdentity(BackupDataOutput data, File … files)` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-576">At some point during your backup, if you want to back up the identities for the files you checked in step 1, you must call `backupMAMFileIdentity(BackupDataOutput data, File … files)` with the files from which you plan to extract data.</span></span> <span data-ttu-id="4f338-577">これにより、自動的に新しいバックアップ エンティティが作成され、 `BackupDataOutput` に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4f338-577">This will automatically create new backup entities and write them to the `BackupDataOutput` for you.</span></span> <span data-ttu-id="4f338-578">これらのエンティティは、復元時に自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-578">These entities will be automatically consumed upon restore.</span></span>

<span data-ttu-id="4f338-579">**複数 ID による復元:**</span><span class="sxs-lookup"><span data-stu-id="4f338-579">**Multi-identity Restore:**</span></span>

<span data-ttu-id="4f338-580">データのバックアップ ガイドは、アプリケーションのデータを復元するための一般的なアルゴリズムを指定し、「[Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent)」(BackupAgent の拡張) セクションでサンプル コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f338-580">The Data Backup guide specifies a general algorithm for restoring your application’s data and provides a code sample in the [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) section.</span></span> <span data-ttu-id="4f338-581">複数 ID による復元を正常に実行するは、次の点に特に注意して、このコード サンプルで提供される一般的な構造に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-581">In order to have a successful multi-identity restore, you must follow the general structure provided in this code sample with special attention to the following:</span></span>

1.  <span data-ttu-id="4f338-582">`while(data.readNextHeader())`\* ループを使用して、バックアップ エンティティを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-582">You must utilize a `while(data.readNextHeader())`\* loop to go through the backup entities.</span></span>

2.  <span data-ttu-id="4f338-583">`data.getKey()`* が `onBackup` で記述したキーに一致しない場合は、`data.skipEntityData()`* を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-583">You must call `data.skipEntityData()`* if `data.getKey()`* does not match the key you wrote in `onBackup`.</span></span> <span data-ttu-id="4f338-584">この手順を実行しないと、復元が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-584">Without performing this step, your restores may not succeed.</span></span>

3.  <span data-ttu-id="4f338-585">自動的に記述するエンティティが失われるので、`while(data.readNextHeader())`\* 構造体内のバックアップのエンティティを消費しているときに返されないようにします。</span><span class="sxs-lookup"><span data-stu-id="4f338-585">Avoid returning while consuming backup entities in the `while(data.readNextHeader())`\* construct, as the entities we automatically write will be lost.</span></span>

* <span data-ttu-id="4f338-586">ここで `data` は、復元時にアプリに渡す **BackupDataInput** のローカル変数の名前です。</span><span class="sxs-lookup"><span data-stu-id="4f338-586">Where `data` is the local variable name for the **BackupDataInput** that is passed to your app upon restore.</span></span>

## <a name="multi-identity-optional"></a><span data-ttu-id="4f338-587">複数 ID (省略可能)</span><span class="sxs-lookup"><span data-stu-id="4f338-587">Multi-identity (optional)</span></span>

### <a name="overview"></a><span data-ttu-id="4f338-588">概要</span><span class="sxs-lookup"><span data-stu-id="4f338-588">Overview</span></span>
<span data-ttu-id="4f338-589">既定では、Intune アプリ SDK は、ポリシーをアプリ全体に適用します。</span><span class="sxs-lookup"><span data-stu-id="4f338-589">By default, the Intune App SDK will apply policy to the app as a whole.</span></span> <span data-ttu-id="4f338-590">複数 ID は、ID 単位のレベルでポリシーを適用できるようにするオプションの Intune アプリ保護機能です。</span><span class="sxs-lookup"><span data-stu-id="4f338-590">Multi-identity is an optional Intune app protection feature which can be enabled to allow policy to be applied on a per-identity level.</span></span> <span data-ttu-id="4f338-591">これには、他のアプリ保護機能よりはるかに多くのアプリの参加が必要です。</span><span class="sxs-lookup"><span data-stu-id="4f338-591">This requires significantly more app participation than other app protection features.</span></span>

<span data-ttu-id="4f338-592">アプリは、アクティブな ID を変更しようとするときに、SDK に通知する*必要があります*。</span><span class="sxs-lookup"><span data-stu-id="4f338-592">The app *must* inform the SDK when it intends to change the active identity.</span></span> <span data-ttu-id="4f338-593">また、場合によっては、SDK は ID の変更が必要なときにもアプリに通知します。</span><span class="sxs-lookup"><span data-stu-id="4f338-593">In some cases, the SDK will also notify the app when an identity change is required.</span></span> <span data-ttu-id="4f338-594">ただし、ほとんどの場合、MAM は UI で表示されているデータまたは指定された時刻のスレッドに使用されるデータを把握することはできません。データのリークを避けるために、適切な ID の設定はアプリに依存します。</span><span class="sxs-lookup"><span data-stu-id="4f338-594">In most cases, however, MAM cannot know what data is being displayed in the UI or used on a thread at a given time and relies on the app to set the correct identity in order to avoid data leak.</span></span> <span data-ttu-id="4f338-595">後続のセクションでは、アプリのアクションを必要とするいくつかの特定のシナリオが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-595">In the sections that follow, some particular scenarios which require app action will be called out.</span></span>

> [!NOTE]
>  <span data-ttu-id="4f338-596">適切なアプリの参加が不足していると、データのリークや他のセキュリティの問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-596">A lack of the correct app participation can result in data leaks and other security issues.</span></span>

<span data-ttu-id="4f338-597">ユーザーがデバイスまたはアプリを登録すると、SDK はこの ID を登録し、それをプライマリ Intune 管理対象 ID であると判断します。</span><span class="sxs-lookup"><span data-stu-id="4f338-597">Once the user enrolls the device or the app, the SDK registers this identity and considers it the primary Intune managed identity.</span></span> <span data-ttu-id="4f338-598">アプリの他のユーザーは、無制限のポリシー設定を持つ管理対象外として扱われます。</span><span class="sxs-lookup"><span data-stu-id="4f338-598">Other users in the app will be treated as unmanaged, with unrestricted policy settings.</span></span>

> [!NOTE]
> <span data-ttu-id="4f338-599">現時点では、サポートされる Intune 管理対象 ID はデバイスあたり 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="4f338-599">Currently, only one Intune managed identity is supported per device.</span></span>

<span data-ttu-id="4f338-600">ID は文字列として簡単に定義されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-600">Note that an identity is simply defined as a string.</span></span> <span data-ttu-id="4f338-601">ID は**大文字と小文字を区別されず**、SDK に ID を要求すると返される ID は、大文字と小文字の使い分けが ID 設定時の本来のものと異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-601">Identities are **case-insensitive**, and requests to the SDK for an identity may not return the same casing that was originally used when setting the identity.</span></span>

### <a name="enabling-multi-identity"></a><span data-ttu-id="4f338-602">複数 ID を有効にする</span><span class="sxs-lookup"><span data-stu-id="4f338-602">Enabling Multi-identity</span></span>

<span data-ttu-id="4f338-603">既定では、すべてのアプリが単一 ID アプリと見なされます。</span><span class="sxs-lookup"><span data-stu-id="4f338-603">By default, all apps are considered to be single-identity apps.</span></span> <span data-ttu-id="4f338-604">AndroidManifest.xml に次のメタデータを配置することでアプリが複数 ID に対応していることを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-604">You can declare an app to be multi-identity aware by placing the following metadata in AndroidManifest.xml.</span></span>

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a><span data-ttu-id="4f338-605">ID の設定</span><span class="sxs-lookup"><span data-stu-id="4f338-605">Setting the Identity</span></span>

<span data-ttu-id="4f338-606">開発者は、次のレベルで降順にアプリ ユーザーの ID を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-606">Developers can set the identity of the app user on the following levels in descending priority:</span></span>

  1. <span data-ttu-id="4f338-607">スレッド レベル</span><span class="sxs-lookup"><span data-stu-id="4f338-607">Thread level</span></span>
  2. <span data-ttu-id="4f338-608">コンテキスト (通常はアクティビティ) レベル</span><span class="sxs-lookup"><span data-stu-id="4f338-608">Context  (generally Activity) level</span></span>
  3. <span data-ttu-id="4f338-609">プロセス レベル</span><span class="sxs-lookup"><span data-stu-id="4f338-609">Process level</span></span>

<span data-ttu-id="4f338-610">スレッド レベルで設定された ID は、プロセス レベルで設定された ID よりも優先されるコンテキスト レベルで設定された ID よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-610">An identity set at the thread level supersedes an identity set at the Context level, which supersedes an identity set at the process level.</span></span> <span data-ttu-id="4f338-611">コンテキストで設定された ID は、適切な関連するシナリオにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-611">An identity set on a Context is only used in appropriate associated scenarios.</span></span> <span data-ttu-id="4f338-612">ファイル IO 操作などにコンテキストは関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="4f338-612">File IO operations, for example, do not have an associated Context.</span></span> <span data-ttu-id="4f338-613">ほとんどの場合、アプリはアクティビティのコンテキスト ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="4f338-613">Most commonly, apps will set the Context identity on an Activity.</span></span> <span data-ttu-id="4f338-614">アプリは、アクティビティの ID が同じ ID に設定されない限り、管理されている ID のデータを表示*できません*。</span><span class="sxs-lookup"><span data-stu-id="4f338-614">An app *must* not display data for a managed identity unless the Activity's identity is set to that same identity.</span></span> <span data-ttu-id="4f338-615">一般に、プロセス レベル ID は、アプリがすべてのスレッドで一度に単一のユーザーだけが操作する場合にのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4f338-615">In general, the process-level identity is only useful if the app works only with a single user at a time on all threads.</span></span> <span data-ttu-id="4f338-616">多くのアプリは、この ID を利用する必要がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-616">Many apps may not need to make use of it.</span></span>

<span data-ttu-id="4f338-617">`MAMPolicyManager` の次のメソッドは、ID を設定し、以前に設定された ID 値を取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-617">The following methods in `MAMPolicyManager` may be used to set the identity and retrieve the identity values previously set.</span></span>

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

/**
   * Get the current app policy. This does NOT take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use the overload below.
   */
  public static AppPolicy getPolicy();

  /**
  * Get the current app policy. This DOES take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use this function.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);
  ```

>[!NOTE]
> <span data-ttu-id="4f338-618">null に設定することで、アプリの ID をクリアすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-618">You can clear the identity of the app by setting it to null.</span></span>
>
> <span data-ttu-id="4f338-619">アプリ保護ポリシーがない ID として空の文字列を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-619">The empty string may be used as an identity that will never have app protection policy.</span></span>

#### <a name="results"></a><span data-ttu-id="4f338-620">結果</span><span class="sxs-lookup"><span data-stu-id="4f338-620">Results</span></span>
<span data-ttu-id="4f338-621">ID を設定するために使用されるすべてのメソッドは、`MAMIdentitySwitchResult` を使用して結果の値を返します。</span><span class="sxs-lookup"><span data-stu-id="4f338-621">All the methods used to set the identity report back result values via `MAMIdentitySwitchResult`.</span></span> <span data-ttu-id="4f338-622">返される値は次の 4 つです。</span><span class="sxs-lookup"><span data-stu-id="4f338-622">There are four values that can be returned:</span></span>

| <span data-ttu-id="4f338-623">戻り値</span><span class="sxs-lookup"><span data-stu-id="4f338-623">Return value</span></span> | <span data-ttu-id="4f338-624">通信の種類</span><span class="sxs-lookup"><span data-stu-id="4f338-624">Scenario</span></span> |
|--|--|
| <span data-ttu-id="4f338-625">SUCCEEDED</span><span class="sxs-lookup"><span data-stu-id="4f338-625">SUCCEEDED</span></span> | <span data-ttu-id="4f338-626">ID 変更が正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="4f338-626">The identity change was successful.</span></span> |
| <span data-ttu-id="4f338-627">NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="4f338-627">NOT_ALLOWED</span></span> | <span data-ttu-id="4f338-628">ID は変更できません。</span><span class="sxs-lookup"><span data-stu-id="4f338-628">The identity change is not allowed.</span></span> <span data-ttu-id="4f338-629">ID は変更できません。</span><span class="sxs-lookup"><span data-stu-id="4f338-629">The identity change is not allowed.</span></span> <span data-ttu-id="4f338-630">これは、現在のスレッドに別の ID が設定されているときに、UI (コンテキスト) ID を設定しようした場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="4f338-630">This occurs if an attempt is made to set the UI (Context) identity when a different identity is set on the current thread.</span></span> |
| <span data-ttu-id="4f338-631">CANCELLED</span><span class="sxs-lookup"><span data-stu-id="4f338-631">CANCELLED</span></span> | <span data-ttu-id="4f338-632">ユーザーが ID 変更を取り消しました。通常、この取り消しは、PIN または認証プロンプトで [戻る] ボタンを押して行われます。</span><span class="sxs-lookup"><span data-stu-id="4f338-632">The user cancelled the identity change, generally by pressing the back button on a PIN or authentication prompt.</span></span> |
| <span data-ttu-id="4f338-633">FAILED</span><span class="sxs-lookup"><span data-stu-id="4f338-633">FAILED</span></span> | <span data-ttu-id="4f338-634">不明な理由により、ID 変更が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4f338-634">The identity change failed for an unspecified reason.</span></span>|

<span data-ttu-id="4f338-635">アプリは、企業データを表示または使用する前に、ID の切り替えが成功していることを確認する*必要があります*。</span><span class="sxs-lookup"><span data-stu-id="4f338-635">The app *must* ensure that an identity switch is successful before displaying or using corporate data.</span></span> <span data-ttu-id="4f338-636">現時点では、プロセスとスレッド ID の切り替えは、常に複数の ID が有効なアプリに対して成功しますが、エラー条件を追加するための権限を予約します。</span><span class="sxs-lookup"><span data-stu-id="4f338-636">Currently, process and thread identity switches will always succeed for a multi-identity-enabled app, however we reserve the right to add failure conditions.</span></span> <span data-ttu-id="4f338-637">UI ID の切り替えは、スレッド ID と競合している場合、またはユーザーが条件付きの起動要件によって取り消した場合に (PIN 画面で戻るボタンを押すなど)、無効な引数で失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-637">The UI identity switch may fail for invalid arguments, if it would conflict with the thread identity, or if the user cancels out of conditional launch requirements (e.g. presses the back button on the PIN screen).</span></span>


<span data-ttu-id="4f338-638">コンテキスト ID を設定する場合、結果は非同期的にレポートされます。</span><span class="sxs-lookup"><span data-stu-id="4f338-638">In the case of setting a Context identity, the result is reported asynchronously.</span></span> <span data-ttu-id="4f338-639">コンテキストがアクティビティの場合、ユーザーが PIN または企業資格情報の入力が必要になる可能性がある条件付きの起動が実行されるまで、SDK は ID 変更が正常に行われたかどうかがわかりません。</span><span class="sxs-lookup"><span data-stu-id="4f338-639">If the Context is an Activity, the SDK doesn't know if the identity change succeeded until after conditional launch is performed -- which may require the user to enter a PIN or corporate credentials.</span></span> <span data-ttu-id="4f338-640">アプリはこの結果を受信するために `MAMSetUIIdentityCallback` の実装が必要になります。このパラメーターに null を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-640">The app is expected to implement a `MAMSetUIIdentityCallback` to receive this result, you can pass null for this parameter.</span></span>

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

<span data-ttu-id="4f338-641">アクティビティの ID は、`MAMActivity` を呼び出す代わりに `MAMPolicyManager.setUIPolicyIdentity` のメソッドを使用して直接設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f338-641">You can also set the identity of an activity directly through a method in `MAMActivity` instead of calling `MAMPolicyManager.setUIPolicyIdentity`.</span></span> <span data-ttu-id="4f338-642">これを行うには、次のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f338-642">Use following method to do so:</span></span>

```java
     public final void switchMAMIdentity(final String newIdentity);
```

<span data-ttu-id="4f338-643">アプリでアクティビティの ID 変更の試行結果通知を受ける必要がある場合は、`MAMActivity` のメソッドを上書きすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4f338-643">You can also override a method in `MAMActivity` if you want the app to be notified of the result of attempts to change the identity of that activity.</span></span>

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

>[!NOTE]
> <span data-ttu-id="4f338-644">ID の切り替えには、アクティビティの再作成が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-644">Switching the identity may require recreating the activity.</span></span> <span data-ttu-id="4f338-645">その場合、`onSwitchMAMIdentityComplete` コールバックはアクティビティの新しいインスタンスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-645">In this case, the `onSwitchMAMIdentityComplete` callback will be delivered to the new instance of the activity.</span></span>


### <a name="implicit-identity-changes"></a><span data-ttu-id="4f338-646">暗黙的な ID 変更</span><span class="sxs-lookup"><span data-stu-id="4f338-646">Implicit Identity Changes</span></span>

<span data-ttu-id="4f338-647">アプリで ID を設定できるだけでなく、スレッドまたはコンテキストの ID は、アプリ保護ポリシーが適用されている別の Intune 対応アプリからのデータに基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-647">In addition to the app's ability to set the identity, a thread or a context's identity may change based on data ingress from another Intune-enlightened app that has app protection policy.</span></span>

#### <a name="examples"></a><span data-ttu-id="4f338-648">例</span><span class="sxs-lookup"><span data-stu-id="4f338-648">Examples</span></span>

  1. <span data-ttu-id="4f338-649">アクティビティが別の MAM アプリによって送信された`Intent`から起動された場合、そのアクティビティの ID は、`Intent`の送信時に他のアプリで有効な ID に基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-649">If an activity is launched from an `Intent` sent by another MAM app, the activity’s identity will be set based on the effective identity in the other app at the point the `Intent` was sent.</span></span>

  2.  <span data-ttu-id="4f338-650">サービスについては、スレッドの ID は、`onStart` または `onBind` 呼び出しの期間に同様に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-650">For services, the thread identity will be set similarly for the duration of an `onStart` or `onBind` call.</span></span> <span data-ttu-id="4f338-651">`onBind` から返される `Binder` の呼び出しでも、スレッド ID が一時的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-651">Calls into the `Binder` returned from `onBind` will also temporarily set the thread identity.</span></span>

  3. <span data-ttu-id="4f338-652">`ContentProvider` の呼び出しでは同様に、それらの期間にスレッド ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="4f338-652">Calls into a `ContentProvider` will similarly set the thread identity for their duration.</span></span>


  <span data-ttu-id="4f338-653">さらに、アクティビティとのユーザー対話により、暗黙的な ID 切り替えが行われる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-653">In addition, user interaction with an activity may cause an implicit identity switch.</span></span>

  <span data-ttu-id="4f338-654">**例:** ユーザーが `Resume` 中に認証プロンプトを取り消した場合、空の ID に暗黙的に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="4f338-654">**Example:** A user canceling out of an authorization prompt during `Resume` will result in an implicit switch to an empty identity.</span></span>

  <span data-ttu-id="4f338-655">アプリはこれらの変更を認識し、必要に応じて禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-655">The app is given an opportunity to be made aware of these changes, and, if it must, the app can forbid them.</span></span> <span data-ttu-id="4f338-656">`MAMService` および `MAMContentProvider` は、サブクラスで上書きできる以下のメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="4f338-656">`MAMService` and `MAMContentProvider` expose the following method that subclasses may override:</span></span>

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
  ```

  <span data-ttu-id="4f338-657">`MAMActivity` クラスでは、メソッドには次の追加のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-657">In the `MAMActivity` class , an additional parameter is present in the method:</span></span>

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
  ```

  * <span data-ttu-id="4f338-658">`AppIdentitySwitchReason` は、暗黙的な切り替えのソースをキャプチャし、値 `CREATE`、`RESUME_CANCELLED`、および `NEW_INTENT` を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-658">The `AppIdentitySwitchReason` captures the source of the implicit switch, and can accept the values `CREATE`, `RESUME_CANCELLED`, and `NEW_INTENT`.</span></span>  <span data-ttu-id="4f338-659">`RESUME_CANCELLED` の理由は、アクティビティの再開時に、PIN、認証、または他のコンプライアンス UI が表示され、ユーザーがその UI を取り消そうとした場合 (通常は、[戻る] ボタンを使用) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-659">The `RESUME_CANCELLED` reason is used when activity resume causes PIN, authentication, or other compliance UI to be displayed and the user attempts to cancel out of that UI, generally though use of the back button.</span></span>


  * <span data-ttu-id="4f338-660">`AppIdentitySwitchResultCallback` は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f338-660">The `AppIdentitySwitchResultCallback` is as follows:</span></span>

    ```java
    public interface AppIdentitySwitchResultCallback {
        /**
         * @param result
         *            whether the identity switch can proceed.
         */
        void reportIdentitySwitchResult(AppIdentitySwitchResult result);
    }
    ```

    <span data-ttu-id="4f338-661">ここで ```AppIdentitySwitchResult``` は SUCCESS または FAILURE です。</span><span class="sxs-lookup"><span data-stu-id="4f338-661">Where ```AppIdentitySwitchResult``` is either SUCCESS or FAILURE.</span></span>

<span data-ttu-id="4f338-662">`MAMService.onMAMBind` から返される Binder によるものを除く、すべての暗黙的な ID 変更に対してメソッド `onMAMIdentitySwitchRequired` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-662">The method `onMAMIdentitySwitchRequired` is called for all implicit identity changes except for those made through a Binder returned from `MAMService.onMAMBind`.</span></span> <span data-ttu-id="4f338-663">`onMAMIdentitySwitchRequired` の既定の実装は次のメソッドを直ちに呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f338-663">The default implementations of `onMAMIdentitySwitchRequired` immediately call:</span></span>

* <span data-ttu-id="4f338-664">理由が RESUME_CANCELLED の場合は `reportIdentitySwitchResult(FAILURE)`。</span><span class="sxs-lookup"><span data-stu-id="4f338-664">`reportIdentitySwitchResult(FAILURE)` when the reason is RESUME_CANCELLED.</span></span>

* <span data-ttu-id="4f338-665">他のすべての場合は `reportIdentitySwitchResult(SUCCESS)`。</span><span class="sxs-lookup"><span data-stu-id="4f338-665">`reportIdentitySwitchResult(SUCCESS)` in all other cases.</span></span>

  <span data-ttu-id="4f338-666">ほとんどのアプリでは別の方法で ID 切り替えをブロックしたり、遅延させたりする必要はありませんが、アプリで必要な場合は次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-666">It is not expected that most apps will need to block or delay an identity switch in a different manner, but if an app needs to do so, the following points must be considered:</span></span>

  * <span data-ttu-id="4f338-667">ID 切り替えがブロックされている場合、`Receive` 共有設定でデータ受信が禁止されている場合と同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-667">If an identity switch is blocked, the result is the same as if `Receive` sharing settings had prohibited the data ingress.</span></span>

  * <span data-ttu-id="4f338-668">サービスがメイン スレッドで実行されている場合、`reportIdentitySwitchResult` を同期的に呼び出す**必要があります**。そうしないと、UI スレッドがハングします。</span><span class="sxs-lookup"><span data-stu-id="4f338-668">If a Service is running on the main thread, `reportIdentitySwitchResult` **must** be called synchronously or the UI thread will hang.</span></span>

  * <span data-ttu-id="4f338-669">**アクティビティ**作成の場合、`onMAMCreate` の前に `onMAMIdentitySwitchRequired` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-669">For **Activity** creation, `onMAMIdentitySwitchRequired` will be called before `onMAMCreate`.</span></span> <span data-ttu-id="4f338-670">アプリで ID 切り替えを許可するかどうかを判断するために UI を表示する必要がある場合、その UI を*別*のアクティビティを使用して表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-670">If the app must show UI to determine whether to allow the identity switch, that UI must be shown using a *different* activity.</span></span>

  * <span data-ttu-id="4f338-671">**アクティビティ**では、RESUME_CANCELLED という理由で空の ID への切り替えが要求された場合、アプリは再開されたアクティビティを変更し、その ID 切り替えに適したデータを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-671">In an **Activity**, when a switch to the empty identity is requested with the reason as RESUME_CANCELLED, the app must modify the resumed activity to display data consistent with that identity switch.</span></span>  <span data-ttu-id="4f338-672">これができない場合、アプリは切り替えを拒否する必要があり、ユーザーは再開 ID のポリシーへの準拠を再度求められます (たとえば、アプリの PIN 入力画面が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="4f338-672">If this is not possible, the app should refuse the switch, and the user will be asked again to comply with policy for the resuming identity (e.g. by being presented with the app PIN entry screen).</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f338-673">複数 ID のアプリは常に、管理対象と管理対象外の両方のアプリからデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="4f338-673">A multi-identity app will always receive incoming data from both managed and unmanaged apps.</span></span> <span data-ttu-id="4f338-674">アプリは、管理された方法で管理対象 ID からのデータを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-674">It is the responsibility of the app to treat data from managed identities in a managed manner.</span></span>

  <span data-ttu-id="4f338-675">要求された ID が管理対象 (`MAMPolicyManager.getIsIdentityManaged` を使用して確認します) であるが、アプリでそのアカウントを使用できない場合 (電子メール アカウントなどのアカウントはアプリで最初にセットアップする必要があるなどの理由で)、ID 切り替えを拒否する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-675">If a requested identity is managed (use `MAMPolicyManager.getIsIdentityManaged` to check), but the app is not able to use that account (e.g. because accounts, such as email accounts, must be set up in the app first) then the identity switch should be refused.</span></span>

### <a name="preserving-identity-in-async-operations"></a><span data-ttu-id="4f338-676">非同期操作での ID の保持</span><span class="sxs-lookup"><span data-stu-id="4f338-676">Preserving Identity In Async Operations</span></span>
<span data-ttu-id="4f338-677">UI スレッドに対する操作は、バック グラウンド タスクを別のスレッドにディスパッチするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="4f338-677">It is common for operations on the UI thread to dispatch background tasks to another thread.</span></span> <span data-ttu-id="4f338-678">マルチ ID アプリでは、このようなバック グラウンド タスクが適切な ID で動作していることを確認する必要があります。多くの場合は、バック グラウンド タスクをディスパッチしたアクティビティで使用される ID と同じものになります。</span><span class="sxs-lookup"><span data-stu-id="4f338-678">A multi-identity app will want to make sure that these background tasks operate with the appropriate identity, which is often the same identity used by the activity which dispatched them.</span></span> <span data-ttu-id="4f338-679">MAM SDK では、ID を保持するのに便利な機能として `MAMAsyncTask` と `MAMIdentityExecutors` を提供しています。</span><span class="sxs-lookup"><span data-stu-id="4f338-679">The MAM SDK provides `MAMAsyncTask` and `MAMIdentityExecutors` as a convenience to aid in preserving the identity.</span></span>
#### <a name="mamasynctask"></a><span data-ttu-id="4f338-680">MAMAsyncTask</span><span class="sxs-lookup"><span data-stu-id="4f338-680">MAMAsyncTask</span></span>

<span data-ttu-id="4f338-681">`MAMAsyncTask` を使用するには、AsyncTask ではなく MAMAsyncTask を継承し、`doInBackground` の上書きを `doInBackgroundMAM` に、`onPreExecute` の上書きを `onPreExecuteMAM` に置換するだけです。</span><span class="sxs-lookup"><span data-stu-id="4f338-681">To use `MAMAsyncTask`, simply inherit from it instead of AsyncTask and replace overrides of `doInBackground` and `onPreExecute` with `doInBackgroundMAM` and `onPreExecuteMAM` respectively.</span></span> <span data-ttu-id="4f338-682">`MAMAsyncTask` コンストラクターは、アクティビティ コンテキストを取ります。</span><span class="sxs-lookup"><span data-stu-id="4f338-682">The `MAMAsyncTask` constructor takes an activity context.</span></span> <span data-ttu-id="4f338-683">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-683">For example:</span></span>

```java
  AsyncTask<Object, Object, Object> task = new MAMAsyncTask<Object, Object, Object>(thisActivity) {

    @Override
    protected Object doInBackgroundMAM(final Object[] params) {
        // Do operations.
    }

    @Override
    protected void onPreExecuteMAM() {
        // Do setup.
    };
```

### <a name="mamidentityexecutors"></a><span data-ttu-id="4f338-684">MAMIdentityExecutors</span><span class="sxs-lookup"><span data-stu-id="4f338-684">MAMIdentityExecutors</span></span>
<span data-ttu-id="4f338-685">`MAMIdentityExecutors` では、`wrapExecutor` メソッドと `wrapExecutorService` メソッドを使用して、既存の `Executor` インスタンスまたは `ExecutorService` インスタンスを ID 保持 `Executor`/`ExecutorService` としてラップすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-685">`MAMIdentityExecutors` allows you to wrap an existing `Executor` or `ExecutorService` instance as an identity-preserving `Executor`/`ExecutorService` with `wrapExecutor` and `wrapExecutorService` methods.</span></span> <span data-ttu-id="4f338-686">例</span><span class="sxs-lookup"><span data-stu-id="4f338-686">For example</span></span>

```java
  Executor wrappedExecutor = MAMIdentityExecutors.wrapExecutor(originalExecutor, activity);
  ExecutorService wrappedService = MAMIdentityExecutors.wrapExecutorService(originalExecutorService, activity);
```

  ### <a name="file-protection"></a><span data-ttu-id="4f338-687">ファイル保護</span><span class="sxs-lookup"><span data-stu-id="4f338-687">File Protection</span></span>

  <span data-ttu-id="4f338-688">すべてのファイルに、スレッドとプロセス ID に基づいて作成時に関連付けられた ID があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-688">Every file has an identity associated with it at the time of creation, based on thread and process identity.</span></span> <span data-ttu-id="4f338-689">この ID は、ファイルの暗号化と選択的ワイプの両方に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-689">This identity will be used for both file encryption and selective wipe.</span></span> <span data-ttu-id="4f338-690">ID が管理され、暗号化を必要とするポリシーがあるファイルのみが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-690">Only files whose identity is managed and has policy requiring encryption will be encrypted.</span></span> <span data-ttu-id="4f338-691">SDK の既定の選択機能ワイプでは、ワイプが要求されている管理対象の ID に関連付けられたファイルのみがワイプされます。</span><span class="sxs-lookup"><span data-stu-id="4f338-691">The SDK's default selective functionality wipe will only wipe files associated with the managed identity for which a wipe has been requested.</span></span> <span data-ttu-id="4f338-692">アプリでは `MAMFileProtectionManager` クラスを使用して、ファイルの ID の照会または変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-692">The app may query or change a file’s identity using the `MAMFileProtectionManager` class.</span></span>

  ```java
    public final class MAMFileProtectionManager {
    /**
         * Protect a file. This will synchronously trigger whatever protection is required for the 
           file, and will tag the file for future protection changes.

         *
         * @param identity
         *            Identity to set.
         * @param file
         *            File to protect.
         * @throws IOException
         *             If the file cannot be changed.
         */
        public static void protect(final File file, final String identity) throws IOException;

        /**
        * Protect a file obtained from a content provider. This is intended to be used for
        * sdcard (whether internal or removable) files accessed through the Storage Access Framework.
        * It may also be used with descriptors referring to private files owned by this app.
        * It is not intended to be used for files owned by other apps and such usage will fail. If
        * creating a new file via a content provider exposed by another MAM-integrated app, the new
        * file identity will automatically be set correctly if the ContentResolver in use was
        * obtained via a Context with an identity or if the thread identity is set.
        *
        * This will synchronously trigger whatever protection is required for the file, and will tag
        * the file for future protection changes. If an identity is set on a directory, it is set
        * recursively on all files and subdirectories. If MAM is operating in offline mode, this
        * method will silently do nothing.
        *
        * @param identity
        *       Identity to set.
        * @param file
        *       File to protect.
        *
        * @throws IOException
        *       If the file cannot be protected.

        */
        public static void protect(final ParcelFileDescriptor file, final String identity) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File or directory to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

    }

    public interface MAMFileProtectionInfo {
        String getIdentity();
    }
  ```
#### <a name="app-responsibility"></a><span data-ttu-id="4f338-693">アプリの責任</span><span class="sxs-lookup"><span data-stu-id="4f338-693">App Responsibility</span></span>
<span data-ttu-id="4f338-694">MAM では、読み取られているファイルと `Activity` に表示されているデータの関係を自動的に推測することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f338-694">MAM cannot automatically infer a relationship between files being read and data being displayed in an `Activity`.</span></span> <span data-ttu-id="4f338-695">アプリは、企業データを表示する前に、UI ID を適切に設定する*必要があります*。</span><span class="sxs-lookup"><span data-stu-id="4f338-695">Apps *must* set the UI identity appropriately before displaying corporate data.</span></span> <span data-ttu-id="4f338-696">これには、ファイルから読み取られたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f338-696">This includes data read from files.</span></span> <span data-ttu-id="4f338-697">ファイルがアプリの外部 (`ContentProvider` または公開されている書き込み可能な場所のいずれか) からのものである場合、アプリはファイルから読み取った情報を表示する前に、(`MAMFileProtectionManager.getProtectionInfo` を使用して) ファイル ID の判断を試みる*必要があります*。</span><span class="sxs-lookup"><span data-stu-id="4f338-697">If a file comes from outside the app (either from a `ContentProvider` or read from a publicly writable location), the app *must* attempt to determine the file identity (using `MAMFileProtectionManager.getProtectionInfo`) before displaying information read from the file.</span></span> <span data-ttu-id="4f338-698">`getProtectionInfo` が null 以外 (空ではない ID) をレポートする場合は、UI ID を (`MAMActivity.switchMAMIdentity` または `MAMPolicyManager.setUIPolicyIdentity` を使用して) この ID に一致するように設定する*必要があります*。</span><span class="sxs-lookup"><span data-stu-id="4f338-698">If `getProtectionInfo` reports a non-null, non-empty identity, the UI identity *must* be set to match this identity (using `MAMActivity.switchMAMIdentity` or `MAMPolicyManager.setUIPolicyIdentity`).</span></span> <span data-ttu-id="4f338-699">ID の切り替えが失敗した場合、ファイルのデータは表示*できません*。</span><span class="sxs-lookup"><span data-stu-id="4f338-699">If the identity switch fails, data from the file *must not* be displayed.</span></span>

<span data-ttu-id="4f338-700">フローの例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4f338-700">An example flow might look something like the following:</span></span>
  * <span data-ttu-id="4f338-701">ユーザーが、アプリで開くドキュメントを選択します</span><span class="sxs-lookup"><span data-stu-id="4f338-701">User selects a document to open in the app</span></span>
  * <span data-ttu-id="4f338-702">開いているフローで、ディスクからデータを読み取る前に、アプリはコンテンツを表示するために使用する ID を確認します</span><span class="sxs-lookup"><span data-stu-id="4f338-702">During the open flow, prior to reading data from disk, the app confirms the identity that should be used to display the content</span></span>
    * <span data-ttu-id="4f338-703">MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)</span><span class="sxs-lookup"><span data-stu-id="4f338-703">MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)</span></span>
    * <span data-ttu-id="4f338-704">if(info)   MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback)</span><span class="sxs-lookup"><span data-stu-id="4f338-704">if(info)   MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback)</span></span>
    * <span data-ttu-id="4f338-705">アプリは、結果がコールバックにレポートされるまで待機します</span><span class="sxs-lookup"><span data-stu-id="4f338-705">The app waits until a result is reported to callback</span></span>
    * <span data-ttu-id="4f338-706">レポートされた結果が失敗の場合、アプリでドキュメントが表示されません</span><span class="sxs-lookup"><span data-stu-id="4f338-706">If the reported result is a failure, the app does not display the document.</span></span>
  * <span data-ttu-id="4f338-707">アプリを開き、ファイルが表示されます</span><span class="sxs-lookup"><span data-stu-id="4f338-707">The app opens and renders the file</span></span>

## <a name="offline-scenarios"></a><span data-ttu-id="4f338-708">オフラインのシナリオ</span><span class="sxs-lookup"><span data-stu-id="4f338-708">Offline Scenarios</span></span>

<span data-ttu-id="4f338-709">ファイルの ID タグ付けはオフライン モードに依存します。</span><span class="sxs-lookup"><span data-stu-id="4f338-709">File identity tagging is sensitive to offline mode.</span></span> <span data-ttu-id="4f338-710">次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-710">The following points should be taken into account:</span></span>

  * <span data-ttu-id="4f338-711">ポータル サイトをインストールしていない場合は、ファイルに ID タグを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="4f338-711">If the Company Portal is not installed, files cannot be identity-tagged.</span></span>

  * <span data-ttu-id="4f338-712">ポータル サイトをインストールしていても、アプリに Intune MAM ポリシーがない場合は、ファイルに確実に ID タグを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="4f338-712">If the Company Portal is installed, but the app does not have Intune MAM policy, files cannot be reliably tagged with identity.</span></span>

  * <span data-ttu-id="4f338-713">ファイルに ID タグを付けられるようになると、以前に作成されたすべてのファイルは、アプリが単一 ID で管理されるアプリとしてインストールされている (ファイルが登録済みユーザーに属するものとして扱われる) 場合を除き、個人用/管理対象外 (空の文字列 ID に属する) として扱われます。</span><span class="sxs-lookup"><span data-stu-id="4f338-713">When file identity tagging becomes available, all previously created files are treated as personal/unmanaged (belonging to the empty-string identity) unless the app was previously installed as a single-identity managed app in which case they are treated as belonging to the enrolled user.</span></span>

### <a name="directory-protection"></a><span data-ttu-id="4f338-714">ディレクトリの保護</span><span class="sxs-lookup"><span data-stu-id="4f338-714">Directory Protection</span></span>

<span data-ttu-id="4f338-715">ファイルを保護するのと同じ `protect` メソッドを使用して、ディレクトリを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-715">Directories may be protected using the same `protect` method used to protect files.</span></span> <span data-ttu-id="4f338-716">ディレクトリの保護は、そのディレクトリ含まれているすべてのファイルとサブディレクトリおよびディレクトリ内で作成された新しいファイルに再帰的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-716">Please note that directory protection applies recursively to all files and subdirectories contained in the directory, and to new files created within the directory.</span></span> <span data-ttu-id="4f338-717">ディレクトリ保護は再帰的に適用されるので、非常に大きなディレクトリの場合、`protect` の呼び出しの完了に時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-717">Because directory protection is applied recursively, the `protect` call can take some time to complete for very large directories.</span></span> <span data-ttu-id="4f338-718">そのため、多数のファイルが含まれるディレクトリに保護を適用するアプリでは、バックグラウンドのスレッドで `protect` を非同期的に実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f338-718">For that reason, apps applying protection to a directory that contains a large number of files might wish to run `protect` asynchronously on a background thread.</span></span>

### <a name="data-protection"></a><span data-ttu-id="4f338-719">データ保護</span><span class="sxs-lookup"><span data-stu-id="4f338-719">Data Protection</span></span>

<span data-ttu-id="4f338-720">複数 ID に属しているものとしてファイルにタグを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="4f338-720">It is not possible to tag a file as belonging to multiple identities.</span></span> <span data-ttu-id="4f338-721">同じファイル内の別のユーザーに属しているデータを格納する必要があるアプリでは、`MAMDataProtectionManager` で提供される機能を使用して手動でこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-721">Apps that must store data belonging to different users in the same file can do so manually, using the features provided by `MAMDataProtectionManager`.</span></span> <span data-ttu-id="4f338-722">これにより、アプリではデータを暗号化し、特定のユーザーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-722">This allows the app to encrypt data and tie it to a particular user.</span></span> <span data-ttu-id="4f338-723">暗号化されたデータは、ファイルのディスクへの格納に適しています。</span><span class="sxs-lookup"><span data-stu-id="4f338-723">The encrypted data is suitable for storing to disk in a file.</span></span> <span data-ttu-id="4f338-724">ID に関連付けられているデータを照会することができ、後でデータの暗号化を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-724">You can query the data associated with the identity and the data can be unecrypted later.</span></span>

<span data-ttu-id="4f338-725">`MAMDataProtectionManager` を使用するアプリは、`MANAGEMENT_REMOVED` 通知のレシーバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-725">Apps which make use of `MAMDataProtectionManager` should implement a receiver for the `MANAGEMENT_REMOVED` notification.</span></span> <span data-ttu-id="4f338-726">このクラスを使用してバッファーが保護されていたときにファイルの暗号化が有効になっていた場合、この通知が完了した後に、保護されていたバッファーは読み取りできなくなります。</span><span class="sxs-lookup"><span data-stu-id="4f338-726">After this notification completes, buffers which were protected via this class will no longer be readable if file encryption was enabled when the buffers were protected.</span></span> <span data-ttu-id="4f338-727">アプリは、この通知中にすべてのバッファーで MAMDataProtectionManager.unprotect を呼び出すことによってこのような状況を修復することができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-727">An app can remediate this situation by calling MAMDataProtectionManager.unprotect on all buffers during this notification.</span></span> <span data-ttu-id="4f338-728">ID 情報を保持する必要がある場合、この通知中に保護を呼び出しても安全です。暗号化は通知中に無効になることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-728">Note that it is also safe to call protect during this notification if it is desired to preserve identity information -- encryption is guaranteed to be disabled during the notification.</span></span>

```java

public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
     * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
     *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
     *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
     *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
     *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
     * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
     *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
     *            Otherwise it will be impossible to get protection info
     *            without advancing the stream position. The stream must be
     *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
     *            returned by a previous call to protect() or a copy of
     *            such bytes.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```

### <a name="content-providers"></a><span data-ttu-id="4f338-729">コンテンツ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="4f338-729">Content Providers</span></span>

<span data-ttu-id="4f338-730">アプリが **ContentProvider** を通じて **ParcelFileDescriptor** 以外の会社データを提供する場合、アプリは `MAMContentProvider` でメソッド `isProvideContentAllowed(String)` を呼び出し、コンテンツの所有者 ID の UPN (ユーザー プリンシパル名) を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-730">If the app provides corporate data other than a **ParcelFileDescriptor** through a **ContentProvider**, the app must call the method `isProvideContentAllowed(String)` in `MAMContentProvider`, passing the owner identity's UPN (user principal name) for the content.</span></span> <span data-ttu-id="4f338-731">この関数で false が返されると、コンテンツを呼び出し元に返すことは "*できません*"。</span><span class="sxs-lookup"><span data-stu-id="4f338-731">If this function returns false, the content *must not* be returned to the caller.</span></span> <span data-ttu-id="4f338-732">コンテンツ プロバイダーから返されたファイル記述子は、ファイル ID に基づいて自動的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-732">File descriptors returned through a content provider are handled automatically based on the file identity.</span></span>

### <a name="selective-wipe"></a><span data-ttu-id="4f338-733">選択的なワイプ</span><span class="sxs-lookup"><span data-stu-id="4f338-733">Selective Wipe</span></span>

<span data-ttu-id="4f338-734">アプリを `WIPE_USER_DATA` 通知に登録すると、SDK の既定の選択的ワイプ動作の利点が得られなくなります。</span><span class="sxs-lookup"><span data-stu-id="4f338-734">If an app registers for the `WIPE_USER_DATA` notification, it will not receive the benefit of the SDK's default selective wipe behavior.</span></span> <span data-ttu-id="4f338-735">複数 ID 対応アプリの場合、MAM の既定の選択的ワイプではワイプ対象の ID のファイルのみがワイプされるため、この損失がとても重要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="4f338-735">For multi-identity aware apps, this loss may be more significant since MAM default selective wipe will wipe only files whose identity is targeted by a wipe.</span></span>

<span data-ttu-id="4f338-736">複数 ID 対応アプリケーションで MAM の既定の選択的ワイプを実行し、_**さらに**_独自のアクションを実行する場合、`WIPE_USER_AUXILIARY_DATA` 通知に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-736">If a multi-identity aware application wishes MAM default selective wipe to be done _**and**_ wishes to perform its own actions on wipe, it should register for `WIPE_USER_AUXILIARY_DATA` notifications.</span></span> <span data-ttu-id="4f338-737">この通知は、MAM の既定の選択的ワイプを実行する直前に SDK によって送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-737">This notification will be sent immediately by the SDK before it performs the MAM default selective wipe.</span></span> <span data-ttu-id="4f338-738">アプリは、WIPE_USER_DATA と WIPE_USER_AUXILIARY_DATA の両方に登録しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-738">An app should never register for both WIPE_USER_DATA and WIPE_USER_AUXILIARY_DATA.</span></span>

## <a name="enabling-mam-targeted-configuration-for-your-android-applications-optional"></a><span data-ttu-id="4f338-739">Android アプリケーションの MAM 対象の構成を有効にする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="4f338-739">Enabling MAM targeted configuration for your Android applications (optional)</span></span>
<span data-ttu-id="4f338-740">アプリケーション固有のキーと値のペアは、Intune コンソールで構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f338-740">Application-specific key-value pairs may be configured in the Intune console.</span></span> <span data-ttu-id="4f338-741">これらのキーと値のペアが、Intune で解釈されることはありませんが、単にアプリに渡されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-741">These key-value pairs are not interpreted by Intune at all, but are simply passed on to the app.</span></span> <span data-ttu-id="4f338-742">このような構成を受信する必要があるアプリケーションは、この操作を行うために `MAMAppConfigManager` と `MAMAppConfig` クラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-742">Applications which want to receive such configuration can use the `MAMAppConfigManager` and `MAMAppConfig` classes to do so.</span></span> <span data-ttu-id="4f338-743">複数のポリシーが同じアプリで対象となっている場合は、同じキーに使用できる複数の値が競合している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-743">If multiple policies are targeted at the same app, there may be multiple conflicting values available for the same key.</span></span>

### <a name="example"></a><span data-ttu-id="4f338-744">例</span><span class="sxs-lookup"><span data-stu-id="4f338-744">Example</span></span>
```
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
LOGGER.info("App Config Data = " + (appConfig == null ? "null" : appConfig.getFullData()));
String valueToUse = null;
if (appConfig.hasConflict("foo")) {
    List<String> values = appConfig.getAllStringsForKey("foo");
    for (String value : values) {
        if (isCorrectValue(value)) {
            valueToUse = value;
        }
    }
} else {
    valueToUse = appConfig.getStringForKey("foo", MAMAppConfig.StringQueryType.Any);
}
LOGGER.info("Found value " + valueToUse);
```

### <a name="mamappconfig-reference"></a><span data-ttu-id="4f338-745">MAMAppConfig 参照</span><span class="sxs-lookup"><span data-stu-id="4f338-745">MAMAppConfig Reference</span></span>

```
public interface MAMAppConfig {
    /**
     * Conflict resolution types for Boolean values.
     */
    enum BooleanQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns true if any of the values are true.
         */
        Or,
        /**
         * In case of conflict, returns false if any of the values are false.
         */
        And
    }

    /**
     * Conflict resolution types for integer and double values.
     */
    enum NumberQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns the minimum Integer.
         */
        Min,
        /**
         * In case of conflict, returns the maximum Integer.
         */
        Max
    }

    /**
     * Conflict resolution types for Strings.
     */
    enum StringQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns the first result ordered alphabetically.
         */
        Min,
        /**
         * In case of conflict, returns the last result ordered alphabetically.
         */
        Max
    }

    /**
     * Retrieve the List of Dictionaries containing all the custom
     *  config data sent by the MAMService. This will return every
     * Application Configuration setting available for this user, one
     *  mapping for each policy applied to the user.
     */
    List<Map<String, String>> getFullData();

    /**
     * Returns true if there is more than one targeted custom config setting for the key provided. 
     */
    boolean hasConflict(String key);

    /**
     * @return a Boolean value for the given key if it can be coerced into a Boolean, or 
     * null if none exists or it cannot be coerced.
     */
    Boolean getBooleanForKey(String key, BooleanQueryType queryType);

    /**
     * @return a Long value for the given key if it can be coerced into a Long, or null if none exists or it cannot be coerced.
     */
    Long getIntegerForKey(String key, NumberQueryType queryType);

    /**
     * @return a Double value for the given key if it can be coerced into a Double, or null if none exists or it cannot be coerced.
     */
    Double getDoubleForKey(String key, NumberQueryType queryType);

    /**
     * @return a String value for the given key, or null if none exists.
     */
    String getStringForKey(String key, StringQueryType queryType);

    /**
     * Like getBooleanForKey except returns all values if multiple are present.
     */
    List<Boolean> getAllBooleansForKey(String key);

    /**
     * Like getIntegerForKey except returns all values if multiple are present.
     */
    List<Long> getAllIntegersForKey(String key);

    /**
     * Like getDoubleForKey except returns all values if multiple are present.
     */
    List<Double> getAllDoublesForKey(String key);

    /**
     * Like getStringForKey except returns all values if multiple are present.
     */
    List<String> getAllStringsForKey(String key);
}
```

### <a name="notification"></a><span data-ttu-id="4f338-746">通知</span><span class="sxs-lookup"><span data-stu-id="4f338-746">Notification</span></span>
<span data-ttu-id="4f338-747">アプリの構成で新しい通知の種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="4f338-747">App config adds a new notification type:</span></span>
* <span data-ttu-id="4f338-748">**REFRESH_APP_CONFIG**: この通知は、`MAMUserNotification` で送信され、アプリに新しいアプリの構成データを使用できることを通知します。</span><span class="sxs-lookup"><span data-stu-id="4f338-748">**REFRESH_APP_CONFIG**: This notification is sent in a `MAMUserNotification` and informs the app that new app config data is available.</span></span>

<span data-ttu-id="4f338-749">MAM 対象の構成値に関する Graph API の機能について詳しくは、[Graph API リファレンスの MAM 対象の構成](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f338-749">For more information about the capabilities of the Graph API with respect to the MAM targeted configuration values, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span></span> <br>


<span data-ttu-id="4f338-750">Android で MAM 対象アプリ構成ポリシーを作成する方法については、「[Android for Work の Microsoft Intune アプリ構成ポリシーを使用する方法](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-android)」の MAM 対象アプリ構成セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f338-750">For more information about how to create a MAM targeted app configuration policy in Android, see the section on MAM targeted app config in [How to use Microsoft Intune app configuration policies for Android](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-android).</span></span>

## <a name="style-customization-optional"></a><span data-ttu-id="4f338-751">スタイルのカスタマイズ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="4f338-751">Style Customization (optional)</span></span>

<span data-ttu-id="4f338-752">MAM SDK によって生成されるビューは、統合されたアプリとより厳密に一致するように視覚的にカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4f338-752">Views generated by the MAM SDK can be visually customized to more closely match the app in which it is integrated.</span></span> <span data-ttu-id="4f338-753">アプリのロゴのサイズに加え、プライマリ、セカンダリ、および背景の色をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-753">You can customize primary, secondary, and background colors, as well as the size of the app logo.</span></span> <span data-ttu-id="4f338-754">このスタイルのカスタマイズは省略可能であり、カスタム スタイルが構成されていない場合、既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-754">This style customization is optional and defaults will be used if no custom style is configured.</span></span>


### <a name="how-to-customize"></a><span data-ttu-id="4f338-755">カスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="4f338-755">How to customize</span></span>
<span data-ttu-id="4f338-756">スタイルの変更を Intune MAM のビューに適用するには、まず、スタイルの上書きの XML ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-756">In order to have style changes apply to the Intune MAM views, you must first create a style override XML file.</span></span> <span data-ttu-id="4f338-757">このファイルは、アプリの "res/xml" ディレクトリに配置する必要があり、自由に名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4f338-757">This file should be placed in the “/res/xml” directory of your app and you may name it whatever you like.</span></span> <span data-ttu-id="4f338-758">このファイルが従う必要がある形式の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-758">Below is an example of the format this file needs to follow.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>
```

<span data-ttu-id="4f338-759">アプリ内に既に存在するリソースを再利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-759">You must reuse resources that already exist within your app.</span></span> <span data-ttu-id="4f338-760">たとえば、colors.xml ファイルで緑の色を定義し、ここで参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-760">For example, you must define the color green in the colors.xml file and reference it here.</span></span> <span data-ttu-id="4f338-761">16 進カラー コード "#0000ff" を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f338-761">You cannot use the Hex color code “#0000ff."</span></span> <span data-ttu-id="4f338-762">アプリのロゴの最大サイズは、110 dip (dp) です。</span><span class="sxs-lookup"><span data-stu-id="4f338-762">The maximum size for the app logo is 110 dip (dp).</span></span> <span data-ttu-id="4f338-763">小さなロゴの画像を使用することができますが、最大サイズに準拠すると、最適な結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="4f338-763">You may use a smaller logo image, but adhering to the maximum size will yield the best looking results.</span></span> <span data-ttu-id="4f338-764">110 dip の制限を超えると、画像は縮小され、ぼやけた画像になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-764">If you exceed the 110 dip limit, the image will scale down and possibly cause blurring.</span></span>

<span data-ttu-id="4f338-765">以下に、許可されているスタイル属性、それらで制御する UI 要素、XML 属性の項目名、およびそれぞれに必要なリソースの種類の完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="4f338-765">Below is the complete list of allowed style attributes, the UI elements they control, their XML attribute item names, and the type of resource expected for each.</span></span>

|<span data-ttu-id="4f338-766">スタイル属性</span><span class="sxs-lookup"><span data-stu-id="4f338-766">Style attribute</span></span> | <span data-ttu-id="4f338-767">影響を受ける UI 要素</span><span class="sxs-lookup"><span data-stu-id="4f338-767">UI elements affected</span></span> | <span data-ttu-id="4f338-768">属性項目名</span><span class="sxs-lookup"><span data-stu-id="4f338-768">Attribute item name</span></span> | <span data-ttu-id="4f338-769">必要なリソースの種類</span><span class="sxs-lookup"><span data-stu-id="4f338-769">Expected resource type</span></span> |
| -- | -- | -- | -- |
| <span data-ttu-id="4f338-770">背景の色</span><span class="sxs-lookup"><span data-stu-id="4f338-770">Background color</span></span> | <span data-ttu-id="4f338-771">PIN 画面の背景色</span><span class="sxs-lookup"><span data-stu-id="4f338-771">PIN screen background color</span></span> <Br><span data-ttu-id="4f338-772">PIN ボックスの塗りつぶしの色</span><span class="sxs-lookup"><span data-stu-id="4f338-772">PIN box fill color</span></span> | <span data-ttu-id="4f338-773">background_color</span><span class="sxs-lookup"><span data-stu-id="4f338-773">background_color</span></span> | <span data-ttu-id="4f338-774">色</span><span class="sxs-lookup"><span data-stu-id="4f338-774">Color</span></span> |
| <span data-ttu-id="4f338-775">背景色</span><span class="sxs-lookup"><span data-stu-id="4f338-775">Foreground color</span></span> | <span data-ttu-id="4f338-776">背景のテキストの色</span><span class="sxs-lookup"><span data-stu-id="4f338-776">Foreground text color</span></span> <br> <span data-ttu-id="4f338-777">PIN ボックスの枠線の既定の状態</span><span class="sxs-lookup"><span data-stu-id="4f338-777">PIN box border in default state</span></span> <br> <span data-ttu-id="4f338-778">ユーザーが PIN を入力するときの PIN ボックスの文字 (暗号化された文字を含む)</span><span class="sxs-lookup"><span data-stu-id="4f338-778">Characters (including obfuscated characters) in PIN box when user enters a PIN</span></span>| <span data-ttu-id="4f338-779">foreground_color</span><span class="sxs-lookup"><span data-stu-id="4f338-779">foreground_color</span></span> | <span data-ttu-id="4f338-780">色</span><span class="sxs-lookup"><span data-stu-id="4f338-780">Color</span></span>|
| <span data-ttu-id="4f338-781">アクセント カラー</span><span class="sxs-lookup"><span data-stu-id="4f338-781">Accent color</span></span> | <span data-ttu-id="4f338-782">強調表示したときの PIN ボックスの枠線</span><span class="sxs-lookup"><span data-stu-id="4f338-782">PIN box border when highlighted</span></span> <br> <span data-ttu-id="4f338-783">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="4f338-783">Hyperlinks</span></span> |<span data-ttu-id="4f338-784">accent_color</span><span class="sxs-lookup"><span data-stu-id="4f338-784">accent_color</span></span> | <span data-ttu-id="4f338-785">色</span><span class="sxs-lookup"><span data-stu-id="4f338-785">Color</span></span> |
| <span data-ttu-id="4f338-786">アプリのロゴ</span><span class="sxs-lookup"><span data-stu-id="4f338-786">App logo</span></span> | <span data-ttu-id="4f338-787">Intune アプリの PIN 画面に表示される大きなアイコン</span><span class="sxs-lookup"><span data-stu-id="4f338-787">Large icon that appears in the Intune app PIN screen</span></span> | <span data-ttu-id="4f338-788">logo_image</span><span class="sxs-lookup"><span data-stu-id="4f338-788">logo_image</span></span> | <span data-ttu-id="4f338-789">Drawable</span><span class="sxs-lookup"><span data-stu-id="4f338-789">Drawable</span></span> |

## <a name="limitations"></a><span data-ttu-id="4f338-790">制限事項</span><span class="sxs-lookup"><span data-stu-id="4f338-790">Limitations</span></span>

### <a name="file-size-limitations"></a><span data-ttu-id="4f338-791">ファイル サイズの制限</span><span class="sxs-lookup"><span data-stu-id="4f338-791">File Size limitations</span></span>

<span data-ttu-id="4f338-792">[ProGuard](http://proguard.sourceforge.net/) なしに実行される大規模なコード ベースにおいて Dalvik 実行可能ファイル形式の制限が問題になります。</span><span class="sxs-lookup"><span data-stu-id="4f338-792">For large code bases that run without [ProGuard](http://proguard.sourceforge.net/), the limitations of the Dalvik executable file format become an issue.</span></span> <span data-ttu-id="4f338-793">具体的には、次の制限事項が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-793">Specifically, the following limitations may occur:</span></span>

1.  <span data-ttu-id="4f338-794">フィールドの 65 K の制限。</span><span class="sxs-lookup"><span data-stu-id="4f338-794">The 65K limit on fields.</span></span>
2.  <span data-ttu-id="4f338-795">メソッドの 65 K の制限。</span><span class="sxs-lookup"><span data-stu-id="4f338-795">The 65K limit on methods.</span></span>

### <a name="policy-enforcement-limitations"></a><span data-ttu-id="4f338-796">ポリシーの適用の制限事項</span><span class="sxs-lookup"><span data-stu-id="4f338-796">Policy enforcement limitations</span></span>

* <span data-ttu-id="4f338-797">**画面キャプチャ**: SDK は Activity.onCreate が既に終了したアクティビティに対し、新しい画面キャプチャの設定値を適用することができません。</span><span class="sxs-lookup"><span data-stu-id="4f338-797">**Screen Capture**: The SDK is unable to enforce a new screen capture setting value in Activities that have already gone through Activity.onCreate.</span></span> <span data-ttu-id="4f338-798">これにより、アプリがスクリーン ショットを無効にするよう構成されているものの、スクリーン ショットを引き続き実行できる期間が発生します。</span><span class="sxs-lookup"><span data-stu-id="4f338-798">This can result in a period of time where the app has been configured to disable screenshots but screenshots can still be taken.</span></span>

* <span data-ttu-id="4f338-799">**コンテンツ リゾルバーの使用**: "転送ポリシーまたは受信" Intune ポリシーにより、別のアプリのコンテンツ プロバイダーにアクセスするためのコンテンツ リゾルバーの使用がブロックされるか、部分的にブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-799">**Using Content Resolvers**: The "transfer or receive" Intune policy may block or partially block the use of a content resolver to access the content provider in another app.</span></span> <span data-ttu-id="4f338-800">これにより、ContentResolver メソッドによって null が返されるか、失敗値がスローされます (例: ブロックされている場合、 `openOutputStream` によって `FileNotFoundException` がスローされる)。</span><span class="sxs-lookup"><span data-stu-id="4f338-800">This will cause ContentResolver methods to return null or throw a failure value (e.g. `openOutputStream` will throw `FileNotFoundException` if blocked).</span></span> <span data-ttu-id="4f338-801">アプリでは、次の呼び出しを行って、コンテンツ リゾルバーを介したデータの書き込みのエラーが、ポリシーによって発生した (またはポリシーによって発生する) かどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4f338-801">The app can determine whether a failure to write data through a content resolver was caused by policy (or would be caused by policy) by making the call:</span></span>
    ```java
    MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(contentURI);
    ```
    <span data-ttu-id="4f338-802">または、関連するアクティビティがない場合</span><span class="sxs-lookup"><span data-stu-id="4f338-802">or if there is no associated activity</span></span>

    ```java
    MAMPolicyManager.getPolicy().getIsSaveToLocationAllowed(contentURI);
    ```

    <span data-ttu-id="4f338-803">この 2 番目のケースでは、複数の ID のアプリは、スレッド ID を適切に設定する (または、明示的に ID を `getPolicy` 呼び出しに渡す) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-803">In this second case, multi-identity apps must take care to set the thread identity appropriately (or pass an explicit identity to the `getPolicy` call).</span></span>

### <a name="exported-services"></a><span data-ttu-id="4f338-804">エクスポートされたサービス</span><span class="sxs-lookup"><span data-stu-id="4f338-804">Exported services</span></span>

 <span data-ttu-id="4f338-805">Intune アプリ SDK に含まれる AndroidManifest.xml ファイルには **MAMNotificationReceiverService** が含まれます。これは、ポータル サイト アプリから対応のアプリに通知を送信できるようにする、エクスポートされたサービスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-805">The AndroidManifest.xml file included in the Intune App SDK contains **MAMNotificationReceiverService**, which must be an exported service to allow the Company Portal to send notifications to an enlightened app.</span></span> <span data-ttu-id="4f338-806">このサービスでは、ポータル サイト アプリのみが通知の送信を許可されるように、呼び出し元を確認します。</span><span class="sxs-lookup"><span data-stu-id="4f338-806">The service checks the caller to ensure that only the Company Portal is allowed to send notifications.</span></span>

### <a name="reflection-limitations"></a><span data-ttu-id="4f338-807">リフレクションの制限事項</span><span class="sxs-lookup"><span data-stu-id="4f338-807">Reflection limitations</span></span>
<span data-ttu-id="4f338-808">MAM の基底クラス (MAMActivity、MAMDocumentsProvider など) の一部には、特定の API レベルより上にあるパラメーターまたは戻り値の型のみを使用するメソッド (Android の元の基底クラスに基づく) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f338-808">Some of the MAM base classes (e.g. MAMActivity, MAMDocumentsProvider) contain methods (based on the original Android base classes) which use parameter or return types only present above certain API levels.</span></span> <span data-ttu-id="4f338-809">このため、リフレクションを使用して、常にアプリ コンポーネントのすべてのメソッドを列挙できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="4f338-809">For this reason, it may not always be possible to use reflection to enumerate all methods of app components.</span></span> <span data-ttu-id="4f338-810">この制限は MAM に限定されるものではなく、アプリ自体が、Android 基底クラスからのこのようなメソッドを実装する場合にも同じ制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-810">This restriction is not limited to MAM, it is the same restriction which would apply if the app itself implemented these methods from the Android base classes.</span></span>
## <a name="expectations-of-the-sdk-consumer"></a><span data-ttu-id="4f338-811">SDK コンシューマーの要望</span><span class="sxs-lookup"><span data-stu-id="4f338-811">Expectations of the SDK consumer</span></span>

<span data-ttu-id="4f338-812">Intune SDK は Android API によって提供されるコントラクトを維持します。ただし、ポリシーの適用の結果として、エラー状態がより頻繁にトリガーされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-812">The Intune SDK maintains the contract provided by the Android API, though failure conditions may be triggered more frequently as a result of policy enforcement.</span></span> <span data-ttu-id="4f338-813">これらの Android のベスト プラクティスにより、エラーの可能性が減少します。</span><span class="sxs-lookup"><span data-stu-id="4f338-813">These Android best practices will reduce the likelihood of failure:</span></span>

* <span data-ttu-id="4f338-814">null を返す可能性のある android SDK 関数で、null が返される可能性が高くなりました。</span><span class="sxs-lookup"><span data-stu-id="4f338-814">Android SDK functions that may return null have a higher likelihood of being null now.</span></span>  <span data-ttu-id="4f338-815">問題を最小限に抑えるため、null チェックが適切な場所にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f338-815">To minimize issues, ensure that null checks are in the right places.</span></span>

* <span data-ttu-id="4f338-816">チェックできる機能は、MAM 置換 API を介してチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-816">Features that can be checked for must be checked for through their MAM replacement APIs.</span></span>

* <span data-ttu-id="4f338-817">すべての派生関数はそのスーパークラスのバージョンを介して呼び出しを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-817">Any derived functions must call through to their super class versions.</span></span>

* <span data-ttu-id="4f338-818">あいまいな方法で API を使用することを回避します。</span><span class="sxs-lookup"><span data-stu-id="4f338-818">Avoid use of any API in an ambiguous way.</span></span> <span data-ttu-id="4f338-819">たとえば、requestCode を確認しないで `Activity.startActivityForResult` を使用すると、予想外の動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="4f338-819">For example, using `Activity.startActivityForResult` without checking the requestCode will cause strange behavior.</span></span>

## <a name="telemetry"></a><span data-ttu-id="4f338-820">製品利用統計情報</span><span class="sxs-lookup"><span data-stu-id="4f338-820">Telemetry</span></span>

<span data-ttu-id="4f338-821">Intune App SDK for Android は、アプリからのデータ収集を制御しません。</span><span class="sxs-lookup"><span data-stu-id="4f338-821">The Intune App SDK for Android does not control data collection from your app.</span></span> <span data-ttu-id="4f338-822">ポータル サイト アプリケーションでは、既定で、製品利用統計情報がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-822">The Company Portal application logs telemetry data by default.</span></span> <span data-ttu-id="4f338-823">このデータは、Microsoft Intune に送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-823">This data is sent to Microsoft Intune.</span></span> <span data-ttu-id="4f338-824">Microsoft ポリシーに基づき、個人を特定できる情報 (PII) は収集しません。</span><span class="sxs-lookup"><span data-stu-id="4f338-824">As per Microsoft Policy, we do not collect any personally identifiable information (PII).</span></span>

> [!NOTE]
> <span data-ttu-id="4f338-825">エンド ユーザーがこのデータの送信を選択しない場合、ポータル サイト アプリの [設定] で製品利用統計情報をオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f338-825">If end users choose not to send this data, they must turn off telemetry under Settings on the Company Portal app.</span></span> <span data-ttu-id="4f338-826">詳しくは、「[Microsoft による使用状況データの収集を無効にする](https://docs.microsoft.com/en-us/intune-user-help/turn-off-microsoft-usage-data-collection-android)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f338-826">To learn more, see [Turn off Microsoft usage data collection](https://docs.microsoft.com/en-us/intune-user-help/turn-off-microsoft-usage-data-collection-android).</span></span> 

## <a name="recommended-android-best-practices"></a><span data-ttu-id="4f338-827">推奨される Android のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="4f338-827">Recommended Android best practices</span></span>

* <span data-ttu-id="4f338-828">ライブラリのすべてのプロジェクトで、可能な限り同じ android:package を共有するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4f338-828">All library projects should share the same android:package where possible.</span></span> <span data-ttu-id="4f338-829">これにより、実行時に散発的に失敗することはありません。これは純粋にビルド時の問題です。</span><span class="sxs-lookup"><span data-stu-id="4f338-829">This will not sporadically fail in run-time; this is purely a build-time problem.</span></span> <span data-ttu-id="4f338-830">Intune アプリ SDK の新しいバージョンでは、冗長性のいくつか削除されます。</span><span class="sxs-lookup"><span data-stu-id="4f338-830">Newer versions of the Intune App SDK will remove some of the redundancy.</span></span>

* <span data-ttu-id="4f338-831">最新の Android SDK ビルド ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f338-831">Use the newest Android SDK build tools.</span></span>

* <span data-ttu-id="4f338-832">使用しない不要なすべてのライブラリ (例: android.support.v4) を削除します。</span><span class="sxs-lookup"><span data-stu-id="4f338-832">Remove all unnecessary and unused libraries (e.g. android.support.v4)</span></span>
