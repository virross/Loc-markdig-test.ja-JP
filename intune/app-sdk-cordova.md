---
title: "Microsoft Intune App SDK Cordova プラグイン"
description: 
keywords: sdk, Cordova, intune
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4292976d948d10f1172cf59c5180bd6f7345b512
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a><span data-ttu-id="deae5-103">Microsoft Intune App SDK Cordova プラグイン</span><span class="sxs-lookup"><span data-stu-id="deae5-103">Microsoft Intune App SDK Cordova Plugin</span></span>

> [!NOTE]
> <span data-ttu-id="deae5-104">最初に、[Intune アプリ SDK の概要](app-sdk-get-started.md)に関する記事に目を通すことをお勧めします。このガイドでは、サポートする各プラットフォームで統合のための準備をする方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="deae5-104">You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.</span></span>

## <a name="overview"></a><span data-ttu-id="deae5-105">概要</span><span class="sxs-lookup"><span data-stu-id="deae5-105">Overview</span></span>

<span data-ttu-id="deae5-106">iOS アプリおよび Android アプリの [Intune App SDK Cordova プラグイン](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) は、Cordova を使用してビルドされています。</span><span class="sxs-lookup"><span data-stu-id="deae5-106">The [Intune App SDK Cordova Plugin](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Cordova.</span></span> <span data-ttu-id="deae5-107">このプラグインを開発者が利用すると、Intune のアプリとデータの保護機能を Cordova 基盤のアプリに統合できます。</span><span class="sxs-lookup"><span data-stu-id="deae5-107">The plugin allows developers to integrate Intune app and data protection features into their Cordova-based app.</span></span>

<span data-ttu-id="deae5-108">SDK の機能は、アプリの動作を変更せずに有効にできます。</span><span class="sxs-lookup"><span data-stu-id="deae5-108">You will find that you can enable SDK features without changing your app's behavior.</span></span> <span data-ttu-id="deae5-109">iOS または Android アプリにプラグインを組み込むと、Microsoft Intune 管理者は Intune アプリの保護ポリシーを展開できるようになります。保護ポリシーは多様なデータ保護機能で構成されます。</span><span class="sxs-lookup"><span data-stu-id="deae5-109">Once you have built the plugin into your iOS or Android app, the Microsoft Intune administrator will be able to deploy Intune app protection policy, which consists of a variety of data protection features.</span></span> <span data-ttu-id="deae5-110">このプラグインは、Cordova ビルド プロセスで多くの手順が自動的に実行されるように開発されました。</span><span class="sxs-lookup"><span data-stu-id="deae5-110">The plugin is built so that most of the steps are automatically performed in the Cordova build process.</span></span> <span data-ttu-id="deae5-111">そのため、アプリの保護をすぐに有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="deae5-111">As a result, you should be able to get your app enabled for Intune app protection quickly.</span></span> <span data-ttu-id="deae5-112">最初に、対象プラットフォームに基づき、下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="deae5-112">To get started, follow the steps below based on your target platform.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="deae5-113">サポートされるプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="deae5-113">Supported Platforms</span></span>

* <span data-ttu-id="deae5-114">このプラグインは、Windows、Mac、Linux OS で動作します。</span><span class="sxs-lookup"><span data-stu-id="deae5-114">The plugin works on Windows, Mac and Linux OS</span></span>
* <span data-ttu-id="deae5-115">このプラグインは、`minSdkVersion` が 14 以上、`targetSdkVersion` が 24 以下の Android アプリで動作します。</span><span class="sxs-lookup"><span data-stu-id="deae5-115">The plugin works for Android apps with `minSdkVersion` >= 14 and `targetSdkVersion` <= 24</span></span>
* <span data-ttu-id="deae5-116">このプラグインは 9.0 以降の iOS をターゲットとする iOS アプリで動作します。</span><span class="sxs-lookup"><span data-stu-id="deae5-116">The plugin works for iOS apps targeted for iOS 9.0 and above.</span></span>

## <a name="intune-mobile-application-management-scenarios"></a><span data-ttu-id="deae5-117">Intune モバイル アプリケーション管理のシナリオ</span><span class="sxs-lookup"><span data-stu-id="deae5-117">Intune Mobile Application Management scenarios</span></span>

* <span data-ttu-id="deae5-118">Intune MDM 登録デバイス</span><span class="sxs-lookup"><span data-stu-id="deae5-118">Intune MDM-enrolled devices</span></span>
* <span data-ttu-id="deae5-119">サードパーティ製の EMM 登録デバイス</span><span class="sxs-lookup"><span data-stu-id="deae5-119">Third-party EMM-enrolled devices</span></span>
* <span data-ttu-id="deae5-120">管理されていないデバイス (MDM に登録されていない)</span><span class="sxs-lookup"><span data-stu-id="deae5-120">Unmanaged devices (not enrolled with any MDM)</span></span>

<span data-ttu-id="deae5-121">Intune App SDK Cordova プラグインで開発された Cordova アプリでは、モバイル デバイス管理 (MDM) に登録しているデバイスと登録していないデバイスの両方で、Intune アプリ保護ポリシーを受け取るようになりました。</span><span class="sxs-lookup"><span data-stu-id="deae5-121">Cordova apps built with the Intune App SDK Cordova Plugin can now receive Intune app protection policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="deae5-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="deae5-122">Prerequisites</span></span>

### <a name="android"></a><span data-ttu-id="deae5-123">Android</span><span class="sxs-lookup"><span data-stu-id="deae5-123">Android</span></span>

* <span data-ttu-id="deae5-124">常に最新の Microsoft Intune Company Portal アプリをデバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="deae5-124">The latest Microsoft Intune Company Portal app must always be installed on the device.</span></span>
* <span data-ttu-id="deae5-125">このプラグインを使用する場合、Cordova ビルドを実行するパス上に Java 7 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="deae5-125">Java 7 at minimum must be on the path where you will execute Cordova build when using the plugin.</span></span>

### <a name="ios"></a><span data-ttu-id="deae5-126">iOS</span><span class="sxs-lookup"><span data-stu-id="deae5-126">iOS</span></span>

* <span data-ttu-id="deae5-127">MDM 機能を使用するには、最新の Microsoft Intune Company Portal アプリをデバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="deae5-127">The latest Microsoft Intune Company Portal app must be installed on the device for MDM features.</span></span> <span data-ttu-id="deae5-128">デバイス登録機能を使用しない場合、Intune アプリ保護ポリシーには必要*ありません*。</span><span class="sxs-lookup"><span data-stu-id="deae5-128">It is *not* needed for Intune app protection policy without device enrollment features.</span></span>

### <a name="both-platforms"></a><span data-ttu-id="deae5-129">両方のプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="deae5-129">Both platforms</span></span>

* <span data-ttu-id="deae5-130">[Cordova 向け Azure Active Directory 認証ライブラリ (ADAL) プラグイン](https://github.com/AzureAD/azure-activedirectory-library-for-cordova)のバージョン 0.8.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="deae5-130">Version 0.8.0+ of the [Azure Active Directory Authentication Libraries (ADAL) plugin for Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) is required.</span></span>

> [!NOTE]
> <span data-ttu-id="deae5-131">[ここ](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22)に提出されている Apache Cordova バグに起因し、プラグイン依存性が既に存在するアプリの場合、要求したバージョンにプラグインが自動アップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="deae5-131">Due to an Apache Cordova bug the filed [here](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), apps that already have the plugin dependency will not automatically upgrade the plugin to the requested version.</span></span>



## <a name="quick-start"></a><span data-ttu-id="deae5-132">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="deae5-132">Quick start</span></span>

1. <span data-ttu-id="deae5-133">ADAL のバージョンを更新する:</span><span class="sxs-lookup"><span data-stu-id="deae5-133">Update your version of ADAL:</span></span>

   ```shell
   cordova plugin remove cordova-plugin-ms-adal
   cordova plugin add cordova-plugin-ms-adal@0.8.x
   ```

2. <span data-ttu-id="deae5-134">Cordova 向け Intune App SDK プラグインを追加する:</span><span class="sxs-lookup"><span data-stu-id="deae5-134">Add the Intune App SDK for Cordova plugin:</span></span>

   ```shell
   cordova plugin add cordova-plugin-ms-intune-mam
   ```

## <a name="build-the-plugin-into-your-ios-app"></a><span data-ttu-id="deae5-135">iOS アプリにプラグインを組み込む</span><span class="sxs-lookup"><span data-stu-id="deae5-135">Build the plugin into your iOS app</span></span>

<span data-ttu-id="deae5-136">アプリで Intune アプリ保護ポリシーを使用できるようにするには、いくつかの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="deae5-136">You'll need to complete some steps for your app to be enabled for Intune app protection policy.</span></span> <span data-ttu-id="deae5-137">便宜上、これらの手順はビルド前フックとして Cordova ビルド プロセスで自動実行されます。</span><span class="sxs-lookup"><span data-stu-id="deae5-137">For convenience, these steps are performed automatically in the Cordova build process as a pre-build hook.</span></span> <span data-ttu-id="deae5-138">結果として、この自動手順により、プロジェクト構成に関連付けられている `*.pbxproj`、`*-Info.plist`、`*.entitlements` ファイルが変更されます。</span><span class="sxs-lookup"><span data-stu-id="deae5-138">As a result, the automated steps will modify your `*.pbxproj` , `*-Info.plist`, and `*.entitlements` files that are associated with a project configuration.</span></span> <span data-ttu-id="deae5-139">プロジェクトに権利ファイルが含まれていない場合、プラグインにより権利ファイルが自動作成されます。</span><span class="sxs-lookup"><span data-stu-id="deae5-139">If your project doesn't contain an entitlements file, the plugin will create one automatically.</span></span>

<span data-ttu-id="deae5-140">このセットアップでサポートされる対象は 1 つだけです。複数の対象が見つかった場合、最初の対象で構成が実行されます。</span><span class="sxs-lookup"><span data-stu-id="deae5-140">This setup only supports a single target and will perform the configuration on the first target found if there are multiple targets.</span></span> <span data-ttu-id="deae5-141">プロセスが失敗した場合、次を確認してください。</span><span class="sxs-lookup"><span data-stu-id="deae5-141">If the process fails, check that:</span></span>

1. <span data-ttu-id="deae5-142">アプリの Xcode プロジェクトは `[name].xcodeproj` です。`[name]` は `config.xml` に定義されている値です。</span><span class="sxs-lookup"><span data-stu-id="deae5-142">Your app's Xcode project is `[name].xcodeproj` where `[name]` is the value defined in `config.xml`</span></span>
2. <span data-ttu-id="deae5-143">プロジェクトで[標準の Cordova アプリ ディレクトリ構造](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure)が利用されます。</span><span class="sxs-lookup"><span data-stu-id="deae5-143">Your project uses the [standard Cordova app directory structure](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).</span></span>

## <a name="build-the-plugin-into-your-android-app"></a><span data-ttu-id="deae5-144">Android アプリにプラグインを組み込む</span><span class="sxs-lookup"><span data-stu-id="deae5-144">Build the plugin into your Android app</span></span>

1. <span data-ttu-id="deae5-145">最新の Cordova ツールでこのプラグインをインポートします。</span><span class="sxs-lookup"><span data-stu-id="deae5-145">Import this plugin with the latest Cordova tools.</span></span> <span data-ttu-id="deae5-146">このプラグインは `after_compile` 手順として自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="deae5-146">The plugin will be automatically invoked as an `after_compile` step.</span></span>

2. <span data-ttu-id="deae5-147">このプラグインでは、ビルド プロセスの終わりに、ビルド APK の Intune 対応バージョン (Android API 14 以降) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="deae5-147">The plugin will create a Intune-enabled version of a built apk (Android API 14+) at the end of the build process.</span></span> <span data-ttu-id="deae5-148">ビルド出力には `[Project]-intunewrapped-[Build_Configuration].apk` が含まれます (例: `helloWorld-intunewrapped-debug.apk`)。</span><span class="sxs-lookup"><span data-stu-id="deae5-148">The build output will contain a `[Project]-intunewrapped-[Build_Configuration].apk` (e.g. `helloWorld-intunewrapped-debug.apk`).</span></span>

> [!NOTE]
> <span data-ttu-id="deae5-149">このプラグインは、Gradle ビルドにのみ対応しています。</span><span class="sxs-lookup"><span data-stu-id="deae5-149">The plugin only supports gradle builds.</span></span>

<span data-ttu-id="deae5-150">[ここ](https://issues.apache.org/jira/browse/CB-9434)に提出されている Cordova バグに起因し、`cordova run` で一部の Cordova フックが無視されるため、ラップされたアプリをコマンド ラインから実行するには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="deae5-150">Due to a Cordova bug filed [here](https://issues.apache.org/jira/browse/CB-9434) that causes certain Cordova hooks to be ignored on `cordova run`, to run the wrapped app from the command line, you must do the following:</span></span>

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a><span data-ttu-id="deae5-151">Android アプリの署名</span><span class="sxs-lookup"><span data-stu-id="deae5-151">Sign your Android app</span></span>

<span data-ttu-id="deae5-152">このプラグインで、次の場所の Cordova に提供した署名情報が自動的に認識されます。</span><span class="sxs-lookup"><span data-stu-id="deae5-152">The plugin automatically recognizes signing information you have provided to Cordova at the following locations:</span></span>

* <span data-ttu-id="deae5-153">platforms/android/debug-signing.properties</span><span class="sxs-lookup"><span data-stu-id="deae5-153">platforms/android/debug-signing.properties</span></span>
* <span data-ttu-id="deae5-154">platforms/android/release-signing.properties</span><span class="sxs-lookup"><span data-stu-id="deae5-154">platforms/android/release-signing.properties</span></span>
* <span data-ttu-id="deae5-155">res/native/android/ant.properties</span><span class="sxs-lookup"><span data-stu-id="deae5-155">res/native/android/ant.properties</span></span>

<span data-ttu-id="deae5-156">使用できる書式については、「[Cordova gradle signing information](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle)」(Cordova gradle の署名情報) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deae5-156">See [the Cordova gradle signing information](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) for more information about the expected format.</span></span>

<span data-ttu-id="deae5-157">現在、Cordova ビルドへのパラメーターを使用して、`build.json` で署名情報または任意の場所情報を提供する機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="deae5-157">We currently don't support the ability to provide signing information in `build.json` or arbitrary locations provided via parameters to Cordova build.</span></span>

## <a name="debugging-from-visual-studio"></a><span data-ttu-id="deae5-158">Visual Studio からデバッグする</span><span class="sxs-lookup"><span data-stu-id="deae5-158">Debugging from Visual Studio</span></span>

<span data-ttu-id="deae5-159">アプリを初めて起動すると、アプリが Intune で管理されていることを知らせるダイアログが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="deae5-159">After launching the app for the first time you should see a dialog notifying you that the app is managed by Intune.</span></span> <span data-ttu-id="deae5-160">"次からは表示しない" を押し、VS からデバッグ/実行ボタンをもう一度クリックし、ブレークポイントにヒットさせます。</span><span class="sxs-lookup"><span data-stu-id="deae5-160">Hit "Don't show again" and click the debug/run button again from VS for breakpoints to be hit.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="deae5-161">既知の制限</span><span class="sxs-lookup"><span data-stu-id="deae5-161">Known Limitations</span></span>

### <a name="android"></a><span data-ttu-id="deae5-162">Android</span><span class="sxs-lookup"><span data-stu-id="deae5-162">Android</span></span>

* <span data-ttu-id="deae5-163">MultiDex のサポートが不完全です。</span><span class="sxs-lookup"><span data-stu-id="deae5-163">MultiDex support is incomplete.</span></span>
* <span data-ttu-id="deae5-164">アプリには 14 以上の `minSdkVersion`、および 24 以下の `targetSdkVersion` が必要です。</span><span class="sxs-lookup"><span data-stu-id="deae5-164">App must have `minSdkVersion` of 14 and `targetSdkVersion` of 24 or below.</span></span> <span data-ttu-id="deae5-165">現在、API 25 をターゲットとするアプリはサポートしてません。</span><span class="sxs-lookup"><span data-stu-id="deae5-165">We currently don't support apps targeting API 25</span></span>
* <span data-ttu-id="deae5-166">V2 署名方式で署名されたアプリに再署名することはできません。</span><span class="sxs-lookup"><span data-stu-id="deae5-166">We cannot re-sign apps that were signed with the V2 Signature Scheme.</span></span> <span data-ttu-id="deae5-167">V2 で署名されたアプリをプラグインでラップすると、ラップされた出力の .apk は署名なしになります。</span><span class="sxs-lookup"><span data-stu-id="deae5-167">When V2-signed apps are wrapped by the plugin, the wrapped output .apk will be unsigned.</span></span>
  *
  * <span data-ttu-id="deae5-168">Cordova の既定の V2 署名を無効にするには、以下を `build-extras.gradle` ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="deae5-168">You can disable Cordova's default V2 Signing by adding the following to your `build-extras.gradle` file:</span></span>

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a><span data-ttu-id="deae5-169">iOS</span><span class="sxs-lookup"><span data-stu-id="deae5-169">iOS</span></span>

* <span data-ttu-id="deae5-170">**Info.plist** ファイルの **CFBundleDocumentTypes** ノードの下で UTI の一覧を変更した場合、再構築する前に、同じ plist ファイル (**UTImportedTypeDeclarations** node) のインポートされた UTI セクションで Intune UTI を消去する必要があります。</span><span class="sxs-lookup"><span data-stu-id="deae5-170">Whenever you modify the list of UTI's under the **CFBundleDocumentTypes** node of the **Info.plist** file, you must clear the Intune UTI's in the Imported UTI's section of the same plist file (**UTImportedTypeDeclarations** node) before building again.</span></span> <span data-ttu-id="deae5-171">Intune UTI はすべてプレフィックス `com.microsoft.intune.mam` で始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="deae5-171">All of the Intune UTI's will start with the prefix `com.microsoft.intune.mam`.</span></span>

* <span data-ttu-id="deae5-172">Cordova プロジェクトから Cordova 用 Intune App SDK プラグインを削除する場合、iOS プラットフォームも削除し、もう一度追加し、.xcodeproj ファイルと .plist ファイルで一部の Intune 設定を元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="deae5-172">If you want to remove the Intune App SDK for Cordova plugin from your Cordova project, you must also remove the iOS platform and re-add it, in order to undo some of the Intune configuration in the .xcodeproj and .plist files.</span></span>
