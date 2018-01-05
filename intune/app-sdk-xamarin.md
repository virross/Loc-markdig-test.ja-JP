---
title: "Microsoft Intune App SDK Xamarin コンポーネント"
description: 
keywords: sdk, Xamarin, intune
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ed5b883b335bc3755f1bd4947d341c89fbda2dda
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a><span data-ttu-id="83acd-103">Microsoft Intune App SDK Xamarin コンポーネント</span><span class="sxs-lookup"><span data-stu-id="83acd-103">Microsoft Intune App SDK Xamarin Component</span></span>

> [!NOTE]
> <span data-ttu-id="83acd-104">最初に、[Intune アプリ SDK の概要](app-sdk-get-started.md)に関する記事に目を通すことをお勧めします。このガイドでは、サポートする各プラットフォームで統合のための準備をする方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="83acd-104">You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.</span></span>



## <a name="overview"></a><span data-ttu-id="83acd-105">概要</span><span class="sxs-lookup"><span data-stu-id="83acd-105">Overview</span></span>
<span data-ttu-id="83acd-106">[Intune App SDK Xamarin コンポーネント](https://components.xamarin.com/view/microsoft.intune.mam)を利用すると、Xamarin でビルドされた iOS アプリと Android アプリで [Intune アプリ SDK Xamarin コンポーネント](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)が有効になります。</span><span class="sxs-lookup"><span data-stu-id="83acd-106">The [Intune App SDK Xamarin component](https://components.xamarin.com/view/microsoft.intune.mam) enables [Intune app protection policy](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Xamarin.</span></span> <span data-ttu-id="83acd-107">このコンポーネントを利用すると、開発者は Intune のアプリ保護機能を Xamarin ベースのアプリに簡単に組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="83acd-107">The component allows developers to easily build in Intune app protection features into their Xamarin-based app.</span></span>

> [!NOTE]
> <span data-ttu-id="83acd-108">Intune SDK for Xamarin のサポートは現在、プレビュー版で利用できます。</span><span class="sxs-lookup"><span data-stu-id="83acd-108">Support for the Intune SDK for Xamarin is currently available in preview.</span></span> 

<span data-ttu-id="83acd-109">Microsoft Intune App SDK Xamarin コンポーネントを利用すると、Intune アプリ保護ポリシー (別名、APP または MAM ポリシー) を Xamarin で開発したアプリに組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="83acd-109">The Microsoft Intune App SDK Xamarin Component lets you incorporate Intune app protection policies (also known as APP or MAM policies) into your apps developed with Xamarin.</span></span> <span data-ttu-id="83acd-110">MAM 対応のアプリケーションが Intune App SDK に統合されています。</span><span class="sxs-lookup"><span data-stu-id="83acd-110">A MAM-enabled application is one that is integrated with the Intune App SDK.</span></span> <span data-ttu-id="83acd-111">Intune で積極的にアプリを管理している場合、IT 管理者はモバイル アプリにアプリ保護ポリシーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="83acd-111">IT administrators can deploy app protection policies to your mobile app when Intune actively manages the app.</span></span>

## <a name="whats-supported"></a><span data-ttu-id="83acd-112">サポートされる内容</span><span class="sxs-lookup"><span data-stu-id="83acd-112">What's supported?</span></span>

### <a name="developer-machines"></a><span data-ttu-id="83acd-113">開発者のコンピューター</span><span class="sxs-lookup"><span data-stu-id="83acd-113">Developer machines</span></span>
* <span data-ttu-id="83acd-114">macOS</span><span class="sxs-lookup"><span data-stu-id="83acd-114">macOS</span></span>


### <a name="mobile-app-platforms"></a><span data-ttu-id="83acd-115">モバイル アプリのプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="83acd-115">Mobile app platforms</span></span>
* <span data-ttu-id="83acd-116">Android</span><span class="sxs-lookup"><span data-stu-id="83acd-116">Android</span></span>
* <span data-ttu-id="83acd-117">iOS</span><span class="sxs-lookup"><span data-stu-id="83acd-117">iOS</span></span>


### <a name="intune-mobile-application-management-scenarios"></a><span data-ttu-id="83acd-118">Intune モバイル アプリケーション管理のシナリオ</span><span class="sxs-lookup"><span data-stu-id="83acd-118">Intune Mobile Application Management scenarios</span></span>

* <span data-ttu-id="83acd-119">Intune MDM 登録デバイス</span><span class="sxs-lookup"><span data-stu-id="83acd-119">Intune MDM-enrolled devices</span></span>
* <span data-ttu-id="83acd-120">サードパーティ製の EMM 登録デバイス</span><span class="sxs-lookup"><span data-stu-id="83acd-120">Third-party EMM-enrolled devices</span></span>
* <span data-ttu-id="83acd-121">管理されていないデバイス (MDM に登録されていない)</span><span class="sxs-lookup"><span data-stu-id="83acd-121">Unmanaged devices (not enrolled with any MDM)</span></span>

<span data-ttu-id="83acd-122">Intune App SDK Xamarin コンポーネントで開発された Xamarin アプリでは、モバイル デバイス管理 (MDM) に登録しているデバイスと登録していないデバイスの両方で、Intune アプリ保護ポリシーを受け取るようになりました。</span><span class="sxs-lookup"><span data-stu-id="83acd-122">Xamarin apps built with the Intune App SDK Xamarin Component can now receive Intune app protection policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83acd-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="83acd-123">Prerequisites</span></span>

* <span data-ttu-id="83acd-124">**[Android のみ]** 最新の Microsoft Intune Company Portal アプリをデバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83acd-124">**[Android only]** The latest Microsoft Intune Company Portal app must be installed on the device.</span></span>

## <a name="get-started"></a><span data-ttu-id="83acd-125">作業開始</span><span class="sxs-lookup"><span data-stu-id="83acd-125">Get started</span></span>

1.  <span data-ttu-id="83acd-126">**Xamarin-component.exe** を[ここ](https://components.xamarin.com/submit/xpkg)からダウンロードし、抽出します。</span><span class="sxs-lookup"><span data-stu-id="83acd-126">Download **Xamarin-component.exe** from [here](https://components.xamarin.com/submit/xpkg) and extract it.</span></span>

2. <span data-ttu-id="83acd-127">Microsoft Intune MAM Xamarin コンポーネントの[ライセンス条項](https://components.xamarin.com/license/microsoft.intune.mam)を読みます。</span><span class="sxs-lookup"><span data-stu-id="83acd-127">Read the [license terms](https://components.xamarin.com/license/microsoft.intune.mam) for the Microsoft Intune MAM Xamarin Component.</span></span>

3.  <span data-ttu-id="83acd-128">[GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) または [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) から Intune App SDK Xamarin コンポーネント フォルダーをダウンロードし、抽出します。</span><span class="sxs-lookup"><span data-stu-id="83acd-128">Download the Intune App SDK Xamarin Component folder from [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) or [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) and extract it.</span></span> <span data-ttu-id="83acd-129">手順 1 と手順 3 でダウンロードしたファイルを両方とも同じディレクトリ レベルに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83acd-129">Both files downloaded from step 1 and step 3 should be in the same directory level.</span></span>

4.  <span data-ttu-id="83acd-130">監理者として起動したコマンド ラインで、`Xamarin.Component.exe install <.xam> file` を実行します。</span><span class="sxs-lookup"><span data-stu-id="83acd-130">In the command line as an administrator, run `Xamarin.Component.exe install <.xam> file`.</span></span>

5.  <span data-ttu-id="83acd-131">Visual Studio で、前に作成した Xamarin プロジェクトの**コンポーネント**を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="83acd-131">In Visual Studio, right-click **components** in your previously created Xamarin project.</span></span>

6.  <span data-ttu-id="83acd-132">**[コンポーネントの編集]** を選択し、コンピューターにローカル ダウンロードした Intune App SDK コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="83acd-132">Select **Edit Components** and add the Intune App SDK component you’ve downloaded locally to your computer.</span></span>



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a><span data-ttu-id="83acd-133">iOS モバイル アプリで Intune アプリ保護ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="83acd-133">Enabling Intune app protection polices in your iOS mobile app</span></span>
1.  <span data-ttu-id="83acd-134">Intune App SDK を初期化するには、`AppDelegate.cs` クラスで何らかの API を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="83acd-134">In order to initialize the Intune App SDK, you need to make a call for any API in the `AppDelegate.cs` class.</span></span> <span data-ttu-id="83acd-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="83acd-135">For example:</span></span>

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  <span data-ttu-id="83acd-136">コンポーネントが追加され、初期化されたので、App SDK を iOS モバイル アプリに組み込むための一般的な手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="83acd-136">Now that the component is added and initialized, you can follow the general steps required for building the App SDK into an iOS mobile app.</span></span> <span data-ttu-id="83acd-137">ネイティブ iOS アプリを有効にする方法は、「[iOS 用 Intune アプリ SDK 開発者ガイド](app-sdk-ios.md)」にすべて記載されています。</span><span class="sxs-lookup"><span data-stu-id="83acd-137">You can find the full documentation for enabling native iOS apps in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md).</span></span>
3. <span data-ttu-id="83acd-138">**重要**: Xamarin 基盤の iOS アプリに固有の変更がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="83acd-138">**Important**: There are several modifications specific to Xamarin-based iOS apps.</span></span> <span data-ttu-id="83acd-139">たとえば、キーチェーン グループを有効にするとき、以下を追加し、コンポーネントに含めた Xamarin サンプル アプリを含めます。</span><span class="sxs-lookup"><span data-stu-id="83acd-139">For instance, when enabling keychain groups, you need to add the following to include the Xamarin sample app we included in the component.</span></span> <span data-ttu-id="83acd-140">以下は、キーチェーン アクセス グループで利用されるようなグループの例です。</span><span class="sxs-lookup"><span data-stu-id="83acd-140">Below is an example of the groups you would need to have in your Keychain Access groups:</span></span>

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

<span data-ttu-id="83acd-141">Xamarin 基盤の iOS アプリにコンポーネントを組み込むための手順が完了しました。</span><span class="sxs-lookup"><span data-stu-id="83acd-141">You have completed the steps necessary to build the component into your Xamarin-based iOS app.</span></span> <span data-ttu-id="83acd-142">プロジェクトの開発に Xcode を利用している場合、`Intune App SDK Settings.bundle` を利用できます。</span><span class="sxs-lookup"><span data-stu-id="83acd-142">If you are utilizing Xcode for building your project, you can use the `Intune App SDK Settings.bundle`.</span></span> <span data-ttu-id="83acd-143">プロジェクトを開発するとき、テストやデバッグのために Intune ポリシー設定のオン/オフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="83acd-143">This allows you to toggle Intune policy settings on and off as you build your project to test and debug.</span></span> <span data-ttu-id="83acd-144">このバンドルを活用するには、「[iOS 用 Intune アプリ SDK 開発者ガイド](app-sdk-ios.md)」の手順に従い、[Xcode デバッグ](app-sdk-ios.md#status-result-and-debug-notifications)に関するセクションをお読みください。</span><span class="sxs-lookup"><span data-stu-id="83acd-144">To take advantage of this bundle, follow the steps in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md) and read the section on [debugging in Xcode](app-sdk-ios.md#status-result-and-debug-notifications).</span></span>

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a><span data-ttu-id="83acd-145">Android モバイル アプリでアプリ保護ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="83acd-145">Enabling app protection policies in your Android mobile app</span></span>
<span data-ttu-id="83acd-146">UI フレームワークを利用しない Xamarin 基盤の Android アプリの場合、「[Android 用 Intune アプリ SDK 開発者ガイド](app-sdk-android.md)」をお読みいただき、それに沿う必要があります。</span><span class="sxs-lookup"><span data-stu-id="83acd-146">For Xamarin-based Android apps not using a UI framework, you need to read and follow the [Intune App SDK for Android Developer Guide](app-sdk-android.md).</span></span> <span data-ttu-id="83acd-147">Xamarin 基盤の Android アプリの場合、ガイドに含まれる[表](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent)に基づき、クラス、メソッド、アクティビティを MAM のそれらと置換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83acd-147">For your Xamarin-based Android app, you need to replace class, methods, and activities with their MAM equivalent based on the [table](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) included in the guide.</span></span> <span data-ttu-id="83acd-148">アプリで `android.app.Application` クラスが定義されない場合、それを作成し、`MAMApplication` から継承するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83acd-148">If your app doesn’t define an `android.app.Application` class, you need to create one and ensure that you inherit from `MAMApplication`.</span></span>

<span data-ttu-id="83acd-149">Xamarin Forms とその他の UI フレームワークの場合、「`MAM.Remapper`」と呼ばれているツールがあります。</span><span class="sxs-lookup"><span data-stu-id="83acd-149">For Xamarin Forms and other UI frameworks, we have provided a tool called `MAM.Remapper`.</span></span> <span data-ttu-id="83acd-150">このツールは、ユーザーに代わってクラス置換を実行します。</span><span class="sxs-lookup"><span data-stu-id="83acd-150">The tool accomplishes the class replacement for you.</span></span> <span data-ttu-id="83acd-151">ただし、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83acd-151">However, you need to do the following steps:</span></span>

1. <span data-ttu-id="83acd-152">`Microsoft.Intune.MAM.Remapper.Tasks` NuGet パッケージ バージョン 0.1.0.0 以降の参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="83acd-152">Add a reference to the `Microsoft.Intune.MAM.Remapper.Tasks` NuGet package version 0.1.0.0 or greater.</span></span>

2. <span data-ttu-id="83acd-153">Android csproj に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="83acd-153">Add the following line to your Android csproj:</span></span>
   ```xml
   <Import
   Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
   ```

3. <span data-ttu-id="83acd-154">追加した `remapping-config.json` ファイルのビルド アクションを **RemappingConfigFile** に設定します。</span><span class="sxs-lookup"><span data-stu-id="83acd-154">Set the build action of the added `remapping-config.json` file to **RemappingConfigFile**.</span></span> <span data-ttu-id="83acd-155">追加した `remapping-config.json` は、Xamarin.Forms とのみ連動します。</span><span class="sxs-lookup"><span data-stu-id="83acd-155">The included `remapping-config.json` only works with Xamarin.Forms.</span></span> <span data-ttu-id="83acd-156">その他の UI フレームワークの場合、Remapper NuGet に付属する Readme を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83acd-156">For other UI frameworks, refer to the Readme included with the Remapper NuGet package.</span></span>

## <a name="next-steps"></a><span data-ttu-id="83acd-157">次の手順</span><span class="sxs-lookup"><span data-stu-id="83acd-157">Next steps</span></span>

<span data-ttu-id="83acd-158">コンポーネントをアプリに組み込む基本的な手順を完了しました。</span><span class="sxs-lookup"><span data-stu-id="83acd-158">You have completed the basic steps of building the component into your app.</span></span> <span data-ttu-id="83acd-159">これで、Xamarin Android サンプル アプリに含まれている手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="83acd-159">Now you can follow the steps included in the Xamarin Android sample app.</span></span> <span data-ttu-id="83acd-160">サンプルは 2 つあります。Xamarin.Forms 用が 1 つ、Android 用が 1 つです。</span><span class="sxs-lookup"><span data-stu-id="83acd-160">We have provided two samples, one for Xamarin.Forms and another for Android.</span></span>
