---
title: "iOS 用 Microsoft Intune App SDK 開発者ガイド"
description: "iOS 用 Microsoft Intune App SDK を使用すると、モバイル アプリ管理 (MAM) という形式で iOS アプリに Intune アプリ保護ポリシーを組み込むことができます。"
keywords: 
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f16830b365246cec16fa4d05c62f7f65130de10d
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a><span data-ttu-id="92a51-103">iOS 用 Microsoft Intune アプリ SDK 開発者ガイド</span><span class="sxs-lookup"><span data-stu-id="92a51-103">Microsoft Intune App SDK for iOS developer guide</span></span>

> [!NOTE]
> <span data-ttu-id="92a51-104">最初に、[Intune アプリ SDK ガイドの概要](app-sdk-get-started.md)に関する記事に目を通すことをお勧めします。このガイドでは、サポートする各プラットフォームで統合のための準備をする方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="92a51-104">You might want to first read the [Get Started with Intune App SDK Guide](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.</span></span>

<span data-ttu-id="92a51-105">iOS 用 Microsoft Intune App SDK を使用すると、ネイティブ iOS アプリに Intune アプリ保護ポリシー (**APP** ポリシーまたは **MAM** ポリシーともいう) を組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-105">The Microsoft Intune App SDK for iOS lets you incorporate Intune app protection policies (also known as **APP** or **MAM policies**) into your native iOS app.</span></span> <span data-ttu-id="92a51-106">MAM 対応のアプリケーションが Intune アプリ SDK に統合されています。</span><span class="sxs-lookup"><span data-stu-id="92a51-106">A MAM-enabled application is one that is integrated with the Intune App SDK.</span></span> <span data-ttu-id="92a51-107">Intune で積極的にアプリを管理している場合、IT 管理者はモバイル アプリにアプリ保護ポリシーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-107">IT administrators can deploy app protection policies to your mobile app when Intune actively manages the app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92a51-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="92a51-108">Prerequisites</span></span>

* <span data-ttu-id="92a51-109">OS X 10.8.5 以降を実行し、Xcode 8 以降がインストールされている Mac OS コンピューターが必要になります。</span><span class="sxs-lookup"><span data-stu-id="92a51-109">You will need a Mac OS computer that runs OS X 10.8.5 or later and has the Xcode 8 or later installed.</span></span>

* <span data-ttu-id="92a51-110">アプリは iOS 9 以降を対象としている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-110">Your app must be targeted for iOS 9 or above.</span></span>

* <span data-ttu-id="92a51-111">[iOS 用の Intune アプリ SDK のライセンス条項](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf)を読みます。</span><span class="sxs-lookup"><span data-stu-id="92a51-111">Review the [Intune App SDK for iOS License Terms](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf).</span></span> <span data-ttu-id="92a51-112">記録としてライセンス条項を印刷し、保管します。</span><span class="sxs-lookup"><span data-stu-id="92a51-112">Print and retain a copy of the license terms for your records.</span></span> <span data-ttu-id="92a51-113">iOS 用の Intune App SDK をダウンロードし、使用すると、このライセンス条項に同意したことになります。</span><span class="sxs-lookup"><span data-stu-id="92a51-113">By downloading and using the Intune App SDK for iOS, you agree to such license terms.</span></span>  <span data-ttu-id="92a51-114">本ライセンス条項に同意されない場合、本ソフトウェアを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="92a51-114">If you do not accept them, do not use the software.</span></span>

* <span data-ttu-id="92a51-115">[GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios) で iOS 用 Intune アプリ SDK のファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="92a51-115">Download the files for the Intune App SDK for iOS on [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).</span></span>

## <a name="whats-in-the-sdk"></a><span data-ttu-id="92a51-116">SDK の機能</span><span class="sxs-lookup"><span data-stu-id="92a51-116">What’s in the SDK</span></span>

<span data-ttu-id="92a51-117">iOS 用 Intune App SDK には、スタティック ライブラリ、リソース ファイル、API ヘッダー、デバッグ設定 plist ファイルおよび構成ツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="92a51-117">The Intune App SDK for iOS includes a static library, resource files, API headers, a debug settings .plist file, and a configurator tool.</span></span> <span data-ttu-id="92a51-118">ほとんどのポリシー適用では、モバイル アプリに単にリソース ファイルを含め、ライブラリに静的にリンクできます。</span><span class="sxs-lookup"><span data-stu-id="92a51-118">Mobile apps might simply include the resource files and statically link to the libraries for most policy enforcement.</span></span> <span data-ttu-id="92a51-119">高度な Intune MAM 機能は、API を介して適用されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-119">Advanced Intune MAM features are enforced through APIs.</span></span>

<span data-ttu-id="92a51-120">このガイドでは、iOS 用 Intune App SDK の次のコンポーネントの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="92a51-120">This guide covers the use of the following components of the Intune App SDK for iOS:</span></span>

* <span data-ttu-id="92a51-121">**libIntuneMAM.a**: Intune アプリ SDK の静的ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="92a51-121">**libIntuneMAM.a**: The Intune App SDK static library.</span></span> <span data-ttu-id="92a51-122">アプリで拡張機能を使用しない場合は、このライブラリをプロジェクトにリンクして、アプリで Intune モバイル アプリケーション管理を行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="92a51-122">If your app does not use extensions, link this library to your project to enable your app for Intune mobile application management.</span></span>

* <span data-ttu-id="92a51-123">**IntuneMAM.framework**: Intune アプリ SDK フレームワーク。</span><span class="sxs-lookup"><span data-stu-id="92a51-123">**IntuneMAM.framework**: The Intune App SDK framework.</span></span> <span data-ttu-id="92a51-124">アプリで Intune モバイル アプリケーション管理を行えるようにするには、このフレームワークをプロジェクトにリンクします。</span><span class="sxs-lookup"><span data-stu-id="92a51-124">Link this framework to your project to enable your app for Intune mobile application management.</span></span> <span data-ttu-id="92a51-125">アプリで拡張機能を使用する場合は、スタティック ライブラリではなくフレームワークを使用して、プロジェクトがスタティック ライブラリの複数のコピーを作成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="92a51-125">Use the framework instead of the static library if your app uses extensions, so that your project does not create multiple copies of the static library.</span></span>

* <span data-ttu-id="92a51-126">**IntuneMAMResources.bundle**: SDK が依存するリソースが含まれているリソース バンドル。</span><span class="sxs-lookup"><span data-stu-id="92a51-126">**IntuneMAMResources.bundle**: A resource bundle that has resources that the SDK relies on.</span></span>

* <span data-ttu-id="92a51-127">**ヘッダー**: Intune アプリ SDK の API を表示します。</span><span class="sxs-lookup"><span data-stu-id="92a51-127">**Headers**: Exposes the Intune App SDK APIs.</span></span> <span data-ttu-id="92a51-128">API を使用する場合は、API を含むヘッダー ファイルをインクルードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-128">If you use an API, you will need to include the header file that contains the API.</span></span> <span data-ttu-id="92a51-129">次のヘッダー ファイルには、Intune App SDK から開発者に提供されている API、データ型、プロトコルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="92a51-129">The following header files include the APIs, data types, and protocols which the Intune App SDK makes available to developers:</span></span>

    * <span data-ttu-id="92a51-130">IntuneMAMAppConfig.h</span><span class="sxs-lookup"><span data-stu-id="92a51-130">IntuneMAMAppConfig.h</span></span>
    * <span data-ttu-id="92a51-131">IntuneMAMAppConfigManager.h</span><span class="sxs-lookup"><span data-stu-id="92a51-131">IntuneMAMAppConfigManager.h</span></span>
    * <span data-ttu-id="92a51-132">IntuneMAMDataProtectionInfo.h</span><span class="sxs-lookup"><span data-stu-id="92a51-132">IntuneMAMDataProtectionInfo.h</span></span>
    * <span data-ttu-id="92a51-133">IntuneMAMDataProtectionManager.h</span><span class="sxs-lookup"><span data-stu-id="92a51-133">IntuneMAMDataProtectionManager.h</span></span>
    * <span data-ttu-id="92a51-134">IntuneMAMDefs.h</span><span class="sxs-lookup"><span data-stu-id="92a51-134">IntuneMAMDefs.h</span></span>
    * <span data-ttu-id="92a51-135">IntuneMAMEnrollmentDelegate.h</span><span class="sxs-lookup"><span data-stu-id="92a51-135">IntuneMAMEnrollmentDelegate.h</span></span>
    * <span data-ttu-id="92a51-136">IntuneMAMEnrollmentManager.h</span><span class="sxs-lookup"><span data-stu-id="92a51-136">IntuneMAMEnrollmentManager.h</span></span>
    * <span data-ttu-id="92a51-137">IntuneMAMEnrollmentStatus.h</span><span class="sxs-lookup"><span data-stu-id="92a51-137">IntuneMAMEnrollmentStatus.h</span></span>
    * <span data-ttu-id="92a51-138">IntuneMAMFileProtectionInfo.h</span><span class="sxs-lookup"><span data-stu-id="92a51-138">IntuneMAMFileProtectionInfo.h</span></span>
    * <span data-ttu-id="92a51-139">IntuneMAMFileProtectionManager.h</span><span class="sxs-lookup"><span data-stu-id="92a51-139">IntuneMAMFileProtectionManager.h</span></span>
    * <span data-ttu-id="92a51-140">IntuneMAMLogger.h</span><span class="sxs-lookup"><span data-stu-id="92a51-140">IntuneMAMLogger.h</span></span>
    * <span data-ttu-id="92a51-141">IntuneMAMPolicy.h</span><span class="sxs-lookup"><span data-stu-id="92a51-141">IntuneMAMPolicy.h</span></span>
    * <span data-ttu-id="92a51-142">IntuneMAMPolicyDelegate.h</span><span class="sxs-lookup"><span data-stu-id="92a51-142">IntuneMAMPolicyDelegate.h</span></span>
    * <span data-ttu-id="92a51-143">IntuneMAMPolicyManager.h</span><span class="sxs-lookup"><span data-stu-id="92a51-143">IntuneMAMPolicyManager.h</span></span>
    * <span data-ttu-id="92a51-144">IntuneMAMVersionInfo.h</span><span class="sxs-lookup"><span data-stu-id="92a51-144">IntuneMAMVersionInfo.h</span></span>

<span data-ttu-id="92a51-145">開発者は、IntuneMAM.h をインポートするだけで上記のすべてのヘッダーの内容が使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-145">Developers can make the contents of all the above headers available by just importing IntuneMAM.h</span></span>


## <a name="how-the-intune-app-sdk-works"></a><span data-ttu-id="92a51-146">Intune アプリ SDK のしくみ</span><span class="sxs-lookup"><span data-stu-id="92a51-146">How the Intune App SDK works</span></span>

<span data-ttu-id="92a51-147">iOS 用 Intune アプリ SDK の目的は、最小限のコード変更で iOS アプリケーションに管理機能を追加することです。</span><span class="sxs-lookup"><span data-stu-id="92a51-147">The objective of the Intune App SDK for iOS is to add management capabilities to iOS applications with minimal code changes.</span></span> <span data-ttu-id="92a51-148">コードの変更が少ないほど、モバイル アプリケーションの一貫性と安定性に与える影響がなくなり、短期間で製品化できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-148">The fewer the code changes, the less time to market--without affecting the consistency and stability of your mobile application.</span></span>


## <a name="build-the-sdk-into-your-mobile-app"></a><span data-ttu-id="92a51-149">モバイル アプリとして SDK をビルドする</span><span class="sxs-lookup"><span data-stu-id="92a51-149">Build the SDK into your mobile app</span></span>

<span data-ttu-id="92a51-150">Intune アプリ SDK を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="92a51-150">To enable the Intune App SDK, follow these steps:</span></span>

1. <span data-ttu-id="92a51-151">**オプション 1 (推奨)**: `IntuneMAM.framework` をプロジェクトにリンクします。</span><span class="sxs-lookup"><span data-stu-id="92a51-151">**Option 1 (recommended)**: Link `IntuneMAM.framework` to your project.</span></span> <span data-ttu-id="92a51-152">プロジェクトのターゲットの **[Embedded Binaries]** (埋め込みバイナリ) の一覧に `IntuneMAM.framework` をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="92a51-152">Drag `IntuneMAM.framework` to the **Embedded Binaries** list of the project target.</span></span>

    > [!NOTE]
    > <span data-ttu-id="92a51-153">フレームワークを使用する場合は、アプリ ストアにアプリを送信する前に、ユニバーサル フレームワークからシミュレーター アーキテクチャを手動で除去する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-153">If you use the framework, you must manually strip out the simulator architectures from the universal framework before you submit your app to the App Store.</span></span> <span data-ttu-id="92a51-154">詳細については、「[iOS 用 Microsoft Intune App SDK 開発者ガイド](#Submit-your-app-to-the-App-Store)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-154">See [Submit your app to the App Store](#Submit-your-app-to-the-App-Store) for more details.</span></span>

2. <span data-ttu-id="92a51-155">**オプション 2**: `libIntuneMAM.a` ライブラリにリンクします。</span><span class="sxs-lookup"><span data-stu-id="92a51-155">**Option 2**: Link to the `libIntuneMAM.a` library.</span></span> <span data-ttu-id="92a51-156">`libIntuneMAM.a` ライブラリをプロジェクト ターゲットの **[Linked Frameworks and Libraries]** (リンク先フレームワークおよびライブラリ) ボックスの一覧にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="92a51-156">Drag the `libIntuneMAM.a` library to the **Linked Frameworks and Libraries** list of the project target.</span></span>

    ![Intune App SDK iOS: リンク先フレームワークおよびライブラリ](./media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    <span data-ttu-id="92a51-158">`-force_load {PATH_TO_LIB}/libIntuneMAM.a` を次のいずれかに追加して、`{PATH_TO_LIB}` を Intune アプリ SDK の場所に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="92a51-158">Add `-force_load {PATH_TO_LIB}/libIntuneMAM.a` to either of the following, replacing `{PATH_TO_LIB}` with the Intune App SDK location:</span></span>
   * <span data-ttu-id="92a51-159">プロジェクトの `OTHER_LDFLAGS` ビルド構成設定</span><span class="sxs-lookup"><span data-stu-id="92a51-159">The project’s `OTHER_LDFLAGS` build configuration setting</span></span>
   * <span data-ttu-id="92a51-160">UI の **その他のリンカー フラグ**</span><span class="sxs-lookup"><span data-stu-id="92a51-160">The UI’s **Other Linker Flags**</span></span>

     > [!NOTE]
     > <span data-ttu-id="92a51-161">`PATH_TO_LIB` を検索するには、`libIntuneMAM.a` ファイルを選択し、**[ファイル]** メニューの **[情報の取得]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="92a51-161">To find `PATH_TO_LIB`, select the file `libIntuneMAM.a` and choose **Get Info** from the **File** menu.</span></span> <span data-ttu-id="92a51-162">**[Info]** (情報 ) ウィンドウの **[General]** (全般) セクションから、**[Where]** (場所) 情報 (パス) をコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="92a51-162">Copy and paste the **Where** information (the path) from the **General** section of the **Info** window.</span></span>

     <span data-ttu-id="92a51-163">**[ビルド フェーズ]** の **[Copy Bundle Resources]** (バンドル リソースのコピー) にあるリソース バンドルをドラッグして、`IntuneMAMResources.bundle` リソース バンドルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-163">Add the `IntuneMAMResources.bundle` resource bundle to the project by dragging the resource bundle under **Copy Bundle Resources** within **Build Phases**.</span></span>

     ![Intune App SDK iOS: バンドル リソースのコピー](./media/intune-app-sdk-ios-copy-bundle-resources.png)

3. <span data-ttu-id="92a51-165">次の iOS フレームワークをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-165">Add these iOS frameworks to the project:</span></span>
    * <span data-ttu-id="92a51-166">MessageUI.framework</span><span class="sxs-lookup"><span data-stu-id="92a51-166">MessageUI.framework</span></span>
    * <span data-ttu-id="92a51-167">Security.framework</span><span class="sxs-lookup"><span data-stu-id="92a51-167">Security.framework</span></span>
    * <span data-ttu-id="92a51-168">MobileCoreServices.framework</span><span class="sxs-lookup"><span data-stu-id="92a51-168">MobileCoreServices.framework</span></span>
    * <span data-ttu-id="92a51-169">SystemConfiguration.framework</span><span class="sxs-lookup"><span data-stu-id="92a51-169">SystemConfiguration.framework</span></span>
    * <span data-ttu-id="92a51-170">libsqlite3.tbd</span><span class="sxs-lookup"><span data-stu-id="92a51-170">libsqlite3.tbd</span></span>
    * <span data-ttu-id="92a51-171">libc++.tbd</span><span class="sxs-lookup"><span data-stu-id="92a51-171">libc++.tbd</span></span>
    * <span data-ttu-id="92a51-172">ImageIO.framework</span><span class="sxs-lookup"><span data-stu-id="92a51-172">ImageIO.framework</span></span>
    * <span data-ttu-id="92a51-173">LocalAuthentication.framework</span><span class="sxs-lookup"><span data-stu-id="92a51-173">LocalAuthentication.framework</span></span>
    * <span data-ttu-id="92a51-174">AudioToolbox.framework</span><span class="sxs-lookup"><span data-stu-id="92a51-174">AudioToolbox.framework</span></span>

4. <span data-ttu-id="92a51-175">モバイル アプリの Info.plist ファイルでメイン Nib またはストーリーボード ファイルが定義されている場合、**メイン ストーリーボード**または**メイン Nib** フィールドを切り取ります。</span><span class="sxs-lookup"><span data-stu-id="92a51-175">If your mobile app defines a main nib or storyboard file in its Info.plist file, cut the **Main Storyboard** or **Main Nib** field(s).</span></span> <span data-ttu-id="92a51-176">必要に応じて、Info.plist でこれらのフィールドと相当する値を **IntuneMAMSettings** という名前の新しいディクショナリの下に次のキー名で貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="92a51-176">In Info.plist, paste these fields and their corresponding values under a new dictionary named **IntuneMAMSettings** with the following key names, as applicable:</span></span>
   * <span data-ttu-id="92a51-177">MainStoryboardFile</span><span class="sxs-lookup"><span data-stu-id="92a51-177">MainStoryboardFile</span></span>
   * <span data-ttu-id="92a51-178">MainStoryboardFile~ipad</span><span class="sxs-lookup"><span data-stu-id="92a51-178">MainStoryboardFile~ipad</span></span>
   * <span data-ttu-id="92a51-179">MainNibFile</span><span class="sxs-lookup"><span data-stu-id="92a51-179">MainNibFile</span></span>
   * <span data-ttu-id="92a51-180">MainNibFile~ipad</span><span class="sxs-lookup"><span data-stu-id="92a51-180">MainNibFile~ipad</span></span>
     > [!NOTE]
     > <span data-ttu-id="92a51-181">モバイル アプリの Info.plist ファイルでメイン nib またはストーリーボードが定義されない場合、これらの設定は不要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-181">If your mobile app doesn’t define a main nib or storyboard file in its Info.plist file, these settings are not required.</span></span>

     <span data-ttu-id="92a51-182">(キー名を確認するために) Info.plist を未処理の形式で表示するには、ドキュメント本文の任意の場所を右クリックし、ビューの種類を **[Show Raw Keys/Values]** (生のキー/値の表示) に変更します。</span><span class="sxs-lookup"><span data-stu-id="92a51-182">You can view Info.plist in raw format (to see the key names) by right-clicking anywhere in the document body and changing the view type to **Show Raw Keys/Values**.</span></span>

5. <span data-ttu-id="92a51-183">各プロジェクト ターゲットの **[機能]** を選択し、**[Keychain Sharing]** (キーチェーン共有) スイッチを有効にして、キーチェーン共有を有効にします (まだ有効になっていない場合)。</span><span class="sxs-lookup"><span data-stu-id="92a51-183">Enable keychain sharing (if it isn't already enabled) by choosing **Capabilities** in each project target and enabling the **Keychain Sharing** switch.</span></span> <span data-ttu-id="92a51-184">次の手順に進むには、キーチェーン共有が必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-184">Keychain sharing is required for you to proceed to the next step.</span></span>

   > [!NOTE]
   > <span data-ttu-id="92a51-185">プロビジョニング プロファイルで新しいキーチェーン共有値がサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-185">Your provisioning profile needs to support new keychain sharing values.</span></span> <span data-ttu-id="92a51-186">キーチェーン アクセス グループは、ワイルドカード文字をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-186">The keychain access groups should support a wildcard character.</span></span> <span data-ttu-id="92a51-187">これを確認するには、テキスト エディターで .mobileprovision ファイルを開いて **keychain-access-groups** を検索し、ワイルド カードがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92a51-187">You can check this by opening the .mobileprovision file in a text editor, searching for **keychain-access-groups**, and ensuring that you have a wildcard.</span></span> <span data-ttu-id="92a51-188">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92a51-188">For example:</span></span>
   >  ```xml
   >  <key>keychain-access-groups</key>
   >  <array>
   >  <string>YOURBUNDLESEEDID.*</string>
   >  </array>
   >  ```

6. <span data-ttu-id="92a51-189">キーチェーン共有を有効にした後、次の手順に従って、Intune App SDK がデータを格納する個別のアクセス グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="92a51-189">After you enable keychain sharing, follow these steps to create a separate access group in which the Intune App SDK will store its data.</span></span> <span data-ttu-id="92a51-190">キーチェーン アクセス グループを作成するには、UI を使用するか、権利ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="92a51-190">You can create a keychain access group by using the UI or by using the entitlements file.</span></span> <span data-ttu-id="92a51-191">キーチェーン アクセス グループを作成する UI を使用している場合、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-191">If you are using the UI to create the keychain access group, make sure to follow the steps below:</span></span>

   1. <span data-ttu-id="92a51-192">モバイル アプリでキーチェーン アクセス グループが定義されていない場合は、アプリのバンドル ID を最初のグループとして追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-192">If your mobile app does not have any keychain access groups defined, add the app’s bundle ID as the first group.</span></span>

   2. <span data-ttu-id="92a51-193">共有キーチェーン グループ `com.microsoft.intune.mam` を既存のアクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-193">Add the shared keychain group `com.microsoft.intune.mam` to your existing access groups.</span></span> <span data-ttu-id="92a51-194">このアクセス グループは、Intune アプリ SDK でデータを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-194">The Intune App SDK uses this access group to store data.</span></span>

   3. <span data-ttu-id="92a51-195">`com.microsoft.adalcache` を既存のアクセス グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-195">Add `com.microsoft.adalcache` to your existing access groups.</span></span>

       ![Intune App SDK iOS: キーチェーン共有](./media/intune-app-sdk-ios-keychain-sharing.png)

   4. <span data-ttu-id="92a51-197">前に示したキーチェーン アクセス グループを作成する Xcode UI を使用するのではなく、権利ファイルを直接編集している場合、キーチェーン アクセス グループの先頭に `$(AppIdentifierPrefix)` を追加します (Xcode ではこの処理が自動的に行われます)。</span><span class="sxs-lookup"><span data-stu-id="92a51-197">If you are editing the entitlements file directly, rather than using the Xcode UI shown above to create the keychain access groups, prepend the keychain access groups with `$(AppIdentifierPrefix)` (Xcode handles this automatically).</span></span> <span data-ttu-id="92a51-198">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="92a51-198">For example:</span></span>

           * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
           * `$(AppIdentifierPrefix)com.microsoft.adalcache`

      > [!NOTE]
      > <span data-ttu-id="92a51-199">権利ファイルとは、モバイル アプリケーションに固有の XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="92a51-199">An entitlements file is an XML file that's unique to your mobile application.</span></span> <span data-ttu-id="92a51-200">iOS アプリで特別なアクセス許可と機能を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-200">It is used to specify special permissions and capabilities in your iOS app.</span></span> <span data-ttu-id="92a51-201">お使いのアプリにあらかじめ権利ファイルが無かった場合、キーチェーンの共有 (手順 6) を有効にすると Xcode によってアプリ用に権利ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-201">If your app did not previously have an entitlements file, enabling keychain sharing (step 6) should have caused Xcode to generate one for your app.</span></span>

7. <span data-ttu-id="92a51-202">アプリの Info.plist ファイルで URL スキームが定義されている場合は、`-intunemam` サフィックスを指定して別のスキームを各 URL スキームに追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-202">If the app defines URL schemes in its Info.plist file, add another scheme, with a `-intunemam` suffix, for each URL scheme.</span></span>

8. <span data-ttu-id="92a51-203">アプリで、その Info.plist ファイルにドキュメント型が定義されている場合は、各アイテムの "ドキュメントのコンテンツ タイプの UTI" 配列の各文字列に "com.microsoft.intune.mam" プレフィックスの重複エントリを</span><span class="sxs-lookup"><span data-stu-id="92a51-203">If the app defines Document types in its Info.plist file, for each item's "Document Content Type UTIs" array, add a duplicate entry for each string with a "com.microsoft.intune.mam."</span></span> <span data-ttu-id="92a51-204">追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-204">prefix.</span></span>

9. <span data-ttu-id="92a51-205">iOS 9 以降用に開発されたモバイル アプリの場合は、アプリが `UIApplication canOpenURL` に渡す各プロトコルを、アプリの Info.plist ファイルの `LSApplicationQueriesSchemes` 配列に含めます。</span><span class="sxs-lookup"><span data-stu-id="92a51-205">For mobile apps developed on iOS 9+, include each protocol that your app passes to `UIApplication canOpenURL` in the `LSApplicationQueriesSchemes` array of your app's Info.plist file.</span></span> <span data-ttu-id="92a51-206">さらに、表示されているプロトコルごとに新しいプロトコルを追加し、それに `-intunemam` を付加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-206">Additionally, for each protocol listed, add a new protocol and append it with `-intunemam`.</span></span> <span data-ttu-id="92a51-207">`http-intunemam`、`https-intunemam`、および `ms-outlook-intunemam` を配列に含める必要もあります。</span><span class="sxs-lookup"><span data-stu-id="92a51-207">You must also include `http-intunemam`, `https-intunemam`, and `ms-outlook-intunemam` in the array.</span></span>

10. <span data-ttu-id="92a51-208">アプリケの権利でアプリ グループが定義されている場合は、それらのグループを **IntuneMAMSettings** ディクショナリの `AppGroupIdentifiers` キーの下に文字列の配列として追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-208">If the app has app groups defined in its entitlements, add these groups to the **IntuneMAMSettings** dictionary under the `AppGroupIdentifiers` key as an array of strings.</span></span>

## <a name="using-the-intune-mam-configurator-tool"></a><span data-ttu-id="92a51-209">Intune MAM 構成ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="92a51-209">Using the Intune MAM Configurator Tool</span></span>

<span data-ttu-id="92a51-210">SDK の手動統合に必要なすべての info.plist 操作が Intune MAM 構成ツールで処理されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="92a51-210">The Intune MAM Configurator Tool now handles all info.plist manipulation that is needed to integrate our SDK manually.</span></span> <span data-ttu-id="92a51-211">Intune App SDK for iOS のリポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="92a51-211">You can find it in the repo for the Intune App SDK for iOS.</span></span> <span data-ttu-id="92a51-212">マルチ ID、AAD 設定など、その他のアプリ固有の設定はこのツールでは処理されません。</span><span class="sxs-lookup"><span data-stu-id="92a51-212">Any additional app specific settings such as multi-ID, AAD settings, etc are not handled by this tool.</span></span> <span data-ttu-id="92a51-213">このツールには 3 つのパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="92a51-213">The tool has 3 parameters:</span></span>

|<span data-ttu-id="92a51-214">プロパティ</span><span class="sxs-lookup"><span data-stu-id="92a51-214">Property</span></span>|<span data-ttu-id="92a51-215">使用方法</span><span class="sxs-lookup"><span data-stu-id="92a51-215">How to use it</span></span>|
|---------------|--------------------------------|
|<span data-ttu-id="92a51-216">- i</span><span class="sxs-lookup"><span data-stu-id="92a51-216">- i</span></span> |  `<Path to the input plist>` |
|<span data-ttu-id="92a51-217">- e</span><span class="sxs-lookup"><span data-stu-id="92a51-217">- e</span></span> | <span data-ttu-id="92a51-218">権利ファイル</span><span class="sxs-lookup"><span data-stu-id="92a51-218">The entitlements files</span></span> |
|<span data-ttu-id="92a51-219">- o</span><span class="sxs-lookup"><span data-stu-id="92a51-219">- o</span></span> |  <span data-ttu-id="92a51-220">(省略可能) `<Path for the changed input plist>`</span><span class="sxs-lookup"><span data-stu-id="92a51-220">(Optional) `<Path for the changed input plist>`</span></span> |

<span data-ttu-id="92a51-221">Intune MAM 構成ツールは次の更新に利用できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-221">The Intune MAM Configurator Tool can be used to update:</span></span>
* <span data-ttu-id="92a51-222">アプリのメイン ストーリーボード ファイルやメイン Nib ファイルを IntuneMAMSettings に更新します。</span><span class="sxs-lookup"><span data-stu-id="92a51-222">Any of your app's Main Storyboard and/or Main Nib files into the IntuneMAMSettings.</span></span>
* <span data-ttu-id="92a51-223">Info.plist ファイルに定義されているアプリの URL スキームを、URL スキームごとに、-intunemam サフィックスで更新します。</span><span class="sxs-lookup"><span data-stu-id="92a51-223">Any of your app's defined URL schemes in its Info.plist file with the -intunemam suffix, for each URL scheme.</span></span>
* <span data-ttu-id="92a51-224">アプリでその Info.plist ファイルにドキュメント型が定義されている場合は、各アイテムの "ドキュメントのコンテンツ タイプの UTI" 配列の各文字列に "com.microsoft.intune.mam" プレフィックスの重複エントリを</span><span class="sxs-lookup"><span data-stu-id="92a51-224">Any of your app's defined Document types in its Info.plist file, for each item's "Document Content Type UTIs" array, add a duplicate entry for each string with a "com.microsoft.intune.mam."</span></span> <span data-ttu-id="92a51-225">追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-225">prefix.</span></span>
* <span data-ttu-id="92a51-226">アプリの権利でアプリ グループが定義されている場合は、それらのグループを IntuneMAMSettings ディクショナリの AppGroupIdentifiers キーの下に文字列の配列として追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-226">Any of your app's app groups defined in its entitlements, add these groups to the IntuneMAMSettings dictionary under the AppGroupIdentifiers key as an array of strings.</span></span>

> [!Note]
> <span data-ttu-id="92a51-227">手動の info.plist 操作ではなく、このツールを使用する場合は、アプリの info.plist か権利が変更されるたびに再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92a51-227">If you decide to use this tool instead of manual info.plist manipulation, we recommend it be rerun whenever changes to your app's info.plist or entitlements have been made.</span></span>

## <a name="configure-azure-active-directory-authentication-library-adal"></a><span data-ttu-id="92a51-228">Azure Active Directory Authentication Library (ADAL) の構成</span><span class="sxs-lookup"><span data-stu-id="92a51-228">Configure Azure Active Directory Authentication Library (ADAL)</span></span>

<span data-ttu-id="92a51-229">Intune App SDK は、認証と条件に基づく起動シナリオに [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="92a51-229">The Intune App SDK uses [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc) for its authentication and conditional launch scenarios.</span></span> <span data-ttu-id="92a51-230">また、デバイスを登録せずに管理するために MAM サービスにユーザー ID を登録する場合も、ADAL を利用します。</span><span class="sxs-lookup"><span data-stu-id="92a51-230">It also relies on ADAL to register the user identity with the MAM service for management without device enrollment scenarios.</span></span>

<span data-ttu-id="92a51-231">通常、ADAL では、アプリに付与されるトークンのセキュリティを保証するために、アプリを Azure Active Directory (AAD) に登録し、一意の ID (クライアント ID) と他の識別子を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-231">Typically, ADAL requires apps to register with Azure Active Directory (AAD) and get a unique ID (Client ID) and other identifiers, to guarantee the security of the tokens granted to the app.</span></span> <span data-ttu-id="92a51-232">Intune App SDK では、指定していない限り、Azure AD に接続するときに既定の登録値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-232">Unless otherwise specified, the Intune App SDK uses default registration values when it contacts Azure AD.</span></span>  

<span data-ttu-id="92a51-233">アプリでユーザーの認証に ADAL が使用している場合、アプリではその既存登録値を利用し、Intune App SDK 既定値を上書きする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-233">If your app already uses ADAL to authenticate users, the app must use its existing registration values and override the Intune App SDK default values.</span></span> <span data-ttu-id="92a51-234">これにより、ユーザーに認証が 2 回 (Intune アプリ SDK で 1 回、アプリで 1 回) 求められることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="92a51-234">This ensures that users are not prompted for authentication twice (once by the Intune App SDK and once by the app).</span></span>

### <a name="recommendations"></a><span data-ttu-id="92a51-235">推奨事項</span><span class="sxs-lookup"><span data-stu-id="92a51-235">Recommendations</span></span>

<span data-ttu-id="92a51-236">アプリからは、マスター ブランチ上の[最新バージョンの ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) にリンクすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92a51-236">It is recommended that your app links to the [latest version of ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) on its master branch.</span></span> <span data-ttu-id="92a51-237">現在、Intune App SDK は、条件付きアクセスを必要とするアプリをサポートするために、ADAL のブローカー ブランチを使用しています。</span><span class="sxs-lookup"><span data-stu-id="92a51-237">The Intune App SDK currently uses the broker branch of ADAL to support apps that require conditional access.</span></span> <span data-ttu-id="92a51-238">(したがって、このようなアプリは Microsoft Authenticator アプリに依存します。)ただし、SDK には ADAL のマスター ブランチとの互換性もまだあります。</span><span class="sxs-lookup"><span data-stu-id="92a51-238">(These apps therefore depend on the Microsoft Authenticator app.) But the SDK is still compatible with the master branch of ADAL.</span></span> <span data-ttu-id="92a51-239">アプリに適合するブランチを使用してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-239">Use the branch that is appropriate for your app.</span></span>

### <a name="link-to-adal-binaries"></a><span data-ttu-id="92a51-240">ADAL バイナリへのリンク</span><span class="sxs-lookup"><span data-stu-id="92a51-240">Link to ADAL binaries</span></span>

<span data-ttu-id="92a51-241">以下の手順に従って、アプリを ADAL バイナリにリンクしてください。</span><span class="sxs-lookup"><span data-stu-id="92a51-241">Follow the steps below to link your app to the ADAL binaries:</span></span>

1. <span data-ttu-id="92a51-242">GitHub から [Azure Active Directory Authentication Library (ADAL) for Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) をダウンロードし、[手順](https://github.com/AzureAD/azure-activedirectory-library-for-objc/blob/master/README.md)に従って、Git サブモジュールまたは CocoaPods を使用してダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="92a51-242">Download the [Azure Active Directory Authentication Library (ADAL) for Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) from GitHub, then follow the [instructions](https://github.com/AzureAD/azure-activedirectory-library-for-objc/blob/master/README.md) on how to download ADAL using Git submodules or CocoaPods.</span></span>

2. <span data-ttu-id="92a51-243">**[Build Phases]** (ビルド フェーズ) の **[Copy Bundle Resources]** (バンドル リソースのコピー) にあるリソース バンドルをドラッグして、`ADALiOSBundle.bundle` リソース バンドルをプロジェクトに含めます。</span><span class="sxs-lookup"><span data-stu-id="92a51-243">Include the `ADALiOSBundle.bundle` resource bundle in the project by dragging the resource bundle under **Copy Bundle Resources** within **Build Phases**.</span></span>

3. <span data-ttu-id="92a51-244">`-force_load {PATH_TO_LIB}/libADALiOS.a` をプロジェクトの `OTHER_LDFLAGS` ビルド構成設定または UI の **[Other Linker Flags]** (その他のリンカー フラグ) に追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-244">Add `-force_load {PATH_TO_LIB}/libADALiOS.a` to the project’s `OTHER_LDFLAGS` build configuration setting or **Other Linker Flags** in the UI.</span></span> <span data-ttu-id="92a51-245">`PATH_TO_LIB` は、ADAL バイナリの場所に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-245">`PATH_TO_LIB` should be replaced with the location of the ADAL binaries.</span></span>



### <a name="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile"></a><span data-ttu-id="92a51-246">同じプロビジョニング プロファイルを使用して署名されている他のアプリと ADAL トークン キャッシュを共有する**</span><span class="sxs-lookup"><span data-stu-id="92a51-246">Share the ADAL token cache with other apps signed with the same provisioning profile?**</span></span>

<span data-ttu-id="92a51-247">同じプロビジョニング プロファイルで署名されたアプリ間で ADAL トークンを共有する場合、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="92a51-247">Follow the instructions below if you want to share ADAL tokens between apps signed with the same provisioning profile:</span></span>

1. <span data-ttu-id="92a51-248">アプリでキーチェーン アクセス グループが定義されていない場合は、アプリのバンドル ID を最初のグループとして追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-248">If your app does not have any keychain access groups defined, add the app’s bundle ID as the first group.</span></span>

2. <span data-ttu-id="92a51-249">キーチェーン権利に `com.microsoft.adalcache` および `com.microsoft.workplacejoin` アクセス グループを追加することによって、ADAL シングル サインオン (SSO) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="92a51-249">Enable ADAL single sign-on (SSO) by adding `com.microsoft.adalcache` and `com.microsoft.workplacejoin` access groups in the keychain entitlements.</span></span>

3. <span data-ttu-id="92a51-250">ADAL 共有キャッシュ キーチェーン グループを明示的に設定している場合は、`<app_id_prefix>.com.microsoft.adalcache` に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92a51-250">If you are explicitly setting the ADAL shared cache keychain group, make sure it is set to `<app_id_prefix>.com.microsoft.adalcache`.</span></span> <span data-ttu-id="92a51-251">上書きしない限り ADAL はこれを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-251">ADAL will set this for you unless you override it.</span></span> <span data-ttu-id="92a51-252">カスタム キーチェーン グループを指定して `com.microsoft.adalcache` を置き換える場合は、Info.plist ファイルの IntuneMAMSettings でキー `ADALCacheKeychainGroupOverride` を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-252">If you want to specify a custom keychain group to replace `com.microsoft.adalcache`, specify that in the Info.plist file under IntuneMAMSettings, by using the key `ADALCacheKeychainGroupOverride`.</span></span>

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a><span data-ttu-id="92a51-253">Intune App SDK の ADAL 設定を構成する</span><span class="sxs-lookup"><span data-stu-id="92a51-253">Configure ADAL settings for the Intune App SDK</span></span>

<span data-ttu-id="92a51-254">アプリで既に認証用に ADAL を使用し、独自の ADAL 設定がある場合、Azure Active Directory に対して認証するときは同じ設定を使用するように Intune App SDK を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-254">If your app already uses ADAL for authentication and has its own ADAL settings, you can force the Intune App SDK to use the same settings during authentication against Azure Active Directory.</span></span> <span data-ttu-id="92a51-255">これで、アプリがユーザーに重複して認証を求めないようになります。</span><span class="sxs-lookup"><span data-stu-id="92a51-255">This ensures that the app will not double-prompt the user for authentication.</span></span> <span data-ttu-id="92a51-256">次の設定の構成については、「[Intune App SDK の設定を構成する](#configure-settings-for-the-intune-app-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-256">See [Configure settings for the Intune App SDK](#configure-settings-for-the-intune-app-sdk) for information on populating the following settings:</span></span>  

* <span data-ttu-id="92a51-257">ADALClientId</span><span class="sxs-lookup"><span data-stu-id="92a51-257">ADALClientId</span></span>
* <span data-ttu-id="92a51-258">ADALAuthority</span><span class="sxs-lookup"><span data-stu-id="92a51-258">ADALAuthority</span></span>
* <span data-ttu-id="92a51-259">ADALRedirectUri</span><span class="sxs-lookup"><span data-stu-id="92a51-259">ADALRedirectUri</span></span>
* <span data-ttu-id="92a51-260">ADALRedirectScheme</span><span class="sxs-lookup"><span data-stu-id="92a51-260">ADALRedirectScheme</span></span>
* <span data-ttu-id="92a51-261">ADALCacheKeychainGroupOverride</span><span class="sxs-lookup"><span data-stu-id="92a51-261">ADALCacheKeychainGroupOverride</span></span>

<span data-ttu-id="92a51-262">アプリが既に ADAL を使用している場合、次の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-262">If your app already uses ADAL, the following configurations are required:</span></span>

1. <span data-ttu-id="92a51-263">プロジェクトの Info.plist ファイルの **IntuneMAMSettings** ディクショナリで、キー名 `ADALClientId` を使用して、ADAL 呼び出しに使用するクライアント ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-263">In the project’s Info.plist file, under the **IntuneMAMSettings** dictionary with the key name `ADALClientId`, specify the client ID to be used for ADAL calls.</span></span>

2. <span data-ttu-id="92a51-264">また、**IntuneMAMSettings** ディクショナリで、キー名 `ADALAuthority` を使用して Azure AD 機関を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-264">Also under the **IntuneMAMSettings** dictionary with the key name `ADALAuthority`, specify the Azure AD authority.</span></span>

3. <span data-ttu-id="92a51-265">さらに、**IntuneMAMSettings** ディクショナリで、キー名 `ADALRedirectUri` を使用して、ADAL 呼び出しに使用するリダイレクト URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-265">Also under the **IntuneMAMSettings** dictionary with the key name `ADALRedirectUri`, specify the redirect URI to be used for ADAL calls.</span></span> <span data-ttu-id="92a51-266">アプリのリダイレクト URI の形式によっては、`ADALRedirectScheme` も指定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-266">You might also need to specify `ADALRedirectScheme`, depending on the format of your app’s redirect URI.</span></span>


<span data-ttu-id="92a51-267">また、Azure AD 機関 URL を実行時に指定されるテナント固有の URL で上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-267">Additionally, you can override the Azure AD Authority URL with a tenant-specific URL at runtime.</span></span> <span data-ttu-id="92a51-268">上書きするには、`IntuneMAMPolicyManager` インスタンスの `aadAuthorityUriOverride` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-268">To do this, simply set the `aadAuthorityUriOverride` property on the `IntuneMAMPolicyManager` instance.</span></span>

> [!NOTE]
> <span data-ttu-id="92a51-269">AAD 機関 URL の設定は、[デバイス登録のない APP](#App-protection-policy-without-device-enrollment) で、アプリによってフェッチされる ADAL 更新トークンを SDK が再利用するために必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-269">Setting the AAD Authority URL is required for [APP without device enrollment](#App-protection-policy-without-device-enrollment) to let the SDK reuse the ADAL refresh token fetched by the app.</span></span>

<span data-ttu-id="92a51-270">この値をクリアまたは変更しない場合、SDK はポリシーの更新およびその後の登録要求に対して引き続きこの機関 URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="92a51-270">The SDK will continue to use this authority URL for policy refresh and any subsequent enrollment requests, unless the value is cleared or changed.</span></span>  <span data-ttu-id="92a51-271">したがって、管理対象ユーザーがアプリからサインアウトするときにこの値をクリアし、新しい管理対象ユーザーがサインインするときに値をリセットすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-271">Therefore, it is important to clear the value when a managed user signs out of the app and to reset the value when a new managed user signs in.</span></span>

### <a name="if-your-app-does-not-use-adal"></a><span data-ttu-id="92a51-272">アプリが ADAL を使用していない場合</span><span class="sxs-lookup"><span data-stu-id="92a51-272">If your app does not use ADAL</span></span>

<span data-ttu-id="92a51-273">アプリで ADAL を使用していない場合、Intune アプリ SDK が ADAL パラメーターの既定値を提供し、Azure AD に対する認証を処理します。</span><span class="sxs-lookup"><span data-stu-id="92a51-273">If your app does not use ADAL, the Intune App SDK will provide default values for ADAL parameters and handle authentication against Azure AD.</span></span> <span data-ttu-id="92a51-274">上記の ADAL 設定の値は指定する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="92a51-274">You do not have to specify any values for the ADAL settings listed above.</span></span>

## <a name="app-protection-policy-without-device-enrollment"></a><span data-ttu-id="92a51-275">デバイス登録が不要なアプリの保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="92a51-275">App protection policy without device enrollment</span></span>

### <a name="overview"></a><span data-ttu-id="92a51-276">概要</span><span class="sxs-lookup"><span data-stu-id="92a51-276">Overview</span></span>
<span data-ttu-id="92a51-277">デバイス登録のない Intune アプリ保護ポリシー (**APP-WE** または MAM-WE とも呼ばれる) では、デバイスが Intune モバイル デバイス管理 (MDM) に登録されていなくても Intune でアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-277">Intune app protection policy without device enrollment, also known as **APP-WE** or MAM-WE, allows apps to be managed by Intune without the need for the device to be enrolled Intune mobile device management (MDM).</span></span> <span data-ttu-id="92a51-278">この新しい機能をサポートするために、アプリを管理用のユーザー アカウントに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-278">To support this new functionality, the app must participate to register user accounts for management.</span></span> <span data-ttu-id="92a51-279">新しい API を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="92a51-279">To use the new APIs, follow these steps:</span></span>

1. <span data-ttu-id="92a51-280">デバイス登録の有無にかかわらずアプリの管理をサポートする、Intune App SDK の最新リリースを使用します。</span><span class="sxs-lookup"><span data-stu-id="92a51-280">Use the latest release of the Intune App SDK, which supports management of apps with or without device enrollment.</span></span>

2. <span data-ttu-id="92a51-281">API を呼び出すすべてのファイルに IntuneMAMEnrollment.h を追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-281">Add IntuneMAMEnrollment.h to any files that will call the APIs.</span></span>

### <a name="register-user-accounts"></a><span data-ttu-id="92a51-282">ユーザー アカウントを登録する</span><span class="sxs-lookup"><span data-stu-id="92a51-282">Register user accounts</span></span>

<span data-ttu-id="92a51-283">指定されたユーザー アカウントの代わりにアプリが APP-WE サービスに登録されている場合、アプリは Intune サービスからアプリ保護ポリシーを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-283">An app can receive app protection policy from the Intune service if the app enrolls with the APP-WE service on behalf of a specified user account.</span></span> <span data-ttu-id="92a51-284">新しくサインインしたユーザーを SDK に登録するのはアプリの役目です。</span><span class="sxs-lookup"><span data-stu-id="92a51-284">The app is responsible for registering any newly signed-in user with the SDK.</span></span> <span data-ttu-id="92a51-285">新しいユーザー アカウントが認証された後、アプリは Headers/IntuneMAMEnrollment.h の `registerAndEnrollAccount` メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-285">After the new user account has been authenticated, the app should call the `registerAndEnrollAccount` method in Headers/IntuneMAMEnrollment.h:</span></span>

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;
```
<span data-ttu-id="92a51-286">`registerAndEnrollAccount` メソッドを呼び出すことにより、SDK はユーザー アカウントを登録し、このアカウントの代わりにアプリを登録しようとします。</span><span class="sxs-lookup"><span data-stu-id="92a51-286">By calling the `registerAndEnrollAccount` method, the SDK will register the user account and attempt to enroll the app on behalf of this account.</span></span> <span data-ttu-id="92a51-287">何らかの理由で登録が失敗した場合、SDK は 24 時間後に自動的に登録を再試行します。</span><span class="sxs-lookup"><span data-stu-id="92a51-287">If the enrollment fails for any reason, the SDK will automatically retry the enrollment 24 hours later.</span></span> <span data-ttu-id="92a51-288">デバッグのため、アプリは登録要求の結果についての通知をデリゲート経由で受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-288">For debugging purposes, the app can receive notifications, via a delegate, about the results of any enrollment requests.</span></span>

<span data-ttu-id="92a51-289">この API が呼び出された後、アプリは通常どおりに機能し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-289">After this API has been invoked, the app can continue to function as normal.</span></span> <span data-ttu-id="92a51-290">登録が成功した場合、SDK はアプリの再起動が必要であることをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="92a51-290">If the enrollment succeeds, the SDK will notify the user that an app restart is required.</span></span> <span data-ttu-id="92a51-291">その時点で、ユーザーはすぐにアプリを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-291">At that time, the user can immediately restart the app.</span></span>

### <a name="deregister-user-accounts"></a><span data-ttu-id="92a51-292">ユーザー アカウントの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="92a51-292">Deregister user accounts</span></span>

<span data-ttu-id="92a51-293">ユーザーがアプリからサインアウトする前に、アプリは SDK からユーザーを登録解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-293">Before a user is signed out of an app, the app should deregister the user from the SDK.</span></span> <span data-ttu-id="92a51-294">これにより次のことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-294">This will ensure:</span></span>

1. <span data-ttu-id="92a51-295">そのユーザーのアカウントに対して登録の再試行が行われなくなります。</span><span class="sxs-lookup"><span data-stu-id="92a51-295">Enrollment retries will no longer happen for the user’s account.</span></span>

2. <span data-ttu-id="92a51-296">アプリ保護ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-296">App protection policy will be removed.</span></span>

3. <span data-ttu-id="92a51-297">アプリが選択的ワイプ (オプション) を開始すると、企業データはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-297">If the app initiates a selective wipe (optional), any corporate data is deleted.</span></span>

<span data-ttu-id="92a51-298">ユーザーがサインアウトする前に、`Headers/IntuneMAMEnrollment.h` にある次の API がアプリによって呼び出される必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-298">Before the user is signed out, the app should call the following API in `Headers/IntuneMAMEnrollment.h`:</span></span>

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */

(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

<span data-ttu-id="92a51-299">ユーザー アカウントの Azure AD トークンが削除される前に、このメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-299">This method must be called before the user account’s Azure AD tokens are deleted.</span></span> <span data-ttu-id="92a51-300">SDK はユーザーの代わりに、ユーザー アカウントの AAD トークンで APP-WE サービスに対する特定の要求を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-300">The SDK needs the user account’s AAD token(s) to make specific requests to the APP-WE service on behalf of the user.</span></span>

<span data-ttu-id="92a51-301">アプリ自体がユーザーの企業データを削除する場合は、`doWipe` フラグを false に設定できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-301">If the app will delete the user’s corporate data on its own, the `doWipe` flag can be set to false.</span></span> <span data-ttu-id="92a51-302">設定しない場合、アプリで SDK による選択的ワイプの開始が可能になります。</span><span class="sxs-lookup"><span data-stu-id="92a51-302">Otherwise, the app can have the SDK initiate a selective wipe.</span></span> <span data-ttu-id="92a51-303">結果的に、アプリの選択的ワイプのデリゲートが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-303">This will result in a call to the app's selective wipe delegate.</span></span>

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### <a name="apps-that-do-not-use-adal"></a><span data-ttu-id="92a51-304">ADAL を使用していないアプリ</span><span class="sxs-lookup"><span data-stu-id="92a51-304">Apps that do not use ADAL</span></span>

<span data-ttu-id="92a51-305">ADAL を使用してユーザーをサインインしないアプリでも、API を呼び出して SDK にその認証を処理させることにより、Intune サービスからアプリ保護ポリシーを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-305">Apps that do not sign in the user using ADAL can still receive app protection policy from the Intune service by calling the API to have the SDK handle that authentication.</span></span> <span data-ttu-id="92a51-306">Azure AD でユーザーを認証していないが、データを保護するためにアプリ保護ポリシーを受け取る必要がある場合は、アプリでこの手法を利用してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-306">Apps should use this technique when they have not authenticated a user with Azure AD but still need to retrieve app protection policy to help protect data.</span></span> <span data-ttu-id="92a51-307">たとえば、別の認証サービスがアプリのサインインに使用されている場合やアプリがサインインにまったく対応していない場合です。</span><span class="sxs-lookup"><span data-stu-id="92a51-307">An example is if another authentication service is being used for app sign-in, or if the app does not support signing in at all.</span></span> <span data-ttu-id="92a51-308">これを行うには、アプリケーションで Headers/IntuneMAMEnrollment.h にある`loginAndEnrollAccount` メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-308">To do this, the application should call the `loginAndEnrollAccount`  method in Headers/IntuneMAMEnrollment.h:</span></span>

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;
```

<span data-ttu-id="92a51-309">このメソッドを呼び出すと、既存のトークンが見つからない場合、SDK はユーザーに資格情報を求めます。</span><span class="sxs-lookup"><span data-stu-id="92a51-309">By calling this method, the SDK will prompt the user for credentials if no existing token can be found.</span></span> <span data-ttu-id="92a51-310">次に SDK は、提供されたユーザー アカウントの代わりに、アプリを APP-WE サービスに登録しようとします。</span><span class="sxs-lookup"><span data-stu-id="92a51-310">The SDK will then try to enroll the app with the APP-WE service on behalf of the supplied user account.</span></span> <span data-ttu-id="92a51-311">このメソッドは ID に "nil" を指定して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-311">The method can be called with "nil" as the identity.</span></span> <span data-ttu-id="92a51-312">そうすると、SDK は、デバイス上の既存の管理されたユーザーで登録するか、または既存ユーザーが見つからない場合はユーザーにユーザー名の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="92a51-312">In that case, the SDK will enroll with the existing managed user on the device, or prompt the user for a user name if no existing user is found.</span></span>

<span data-ttu-id="92a51-313">登録が失敗した場合、エラーの詳細によっては、アプリは後で再びこの API を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-313">If the enrollment fails, the app should consider calling this API again at a future time, depending on the details of the failure.</span></span> <span data-ttu-id="92a51-314">アプリは登録要求の結果についての[通知](#Status-result-and-debug-notifications)をデリゲート経由で受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-314">The app can receive [notifications](#Status-result-and-debug-notifications), via a delegate, about the results of any enrollment requests.</span></span>

<span data-ttu-id="92a51-315">この API が呼び出された後、アプリは通常どおりに機能し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-315">After this API has been invoked, the app can continue functioning as normal.</span></span> <span data-ttu-id="92a51-316">登録が成功した場合、SDK はアプリの再起動が必要であることをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="92a51-316">If the enrollment succeeds, the SDK will notify the user that an app restart is required.</span></span>

## <a name="status-result-and-debug-notifications"></a><span data-ttu-id="92a51-317">状態、結果、およびデバッグ通知</span><span class="sxs-lookup"><span data-stu-id="92a51-317">Status, result, and debug notifications</span></span>

<span data-ttu-id="92a51-318">アプリは、Intune MAM サービスに対する次の要求についての状態、結果、およびデバッグ通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-318">The app can receive status, result, and debug notifications about the following requests to the Intune MAM service:</span></span>

 - <span data-ttu-id="92a51-319">登録要求</span><span class="sxs-lookup"><span data-stu-id="92a51-319">Enrollment requests</span></span>
 - <span data-ttu-id="92a51-320">ポリシー更新要求</span><span class="sxs-lookup"><span data-stu-id="92a51-320">Policy update requests</span></span>
 - <span data-ttu-id="92a51-321">登録解除要求</span><span class="sxs-lookup"><span data-stu-id="92a51-321">Unenrollment requests</span></span>

<span data-ttu-id="92a51-322">通知は、`Headers/IntuneMAMEnrollmentDelegate.h` にあるデリゲート メソッドを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-322">The notifications are presented via delegate methods in `Headers/IntuneMAMEnrollmentDelegate.h`:</span></span>

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;
```

<span data-ttu-id="92a51-323">これらのデリゲート メソッドは、次の情報を含む `IntuneMAMEnrollmentStatus` オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="92a51-323">These delegate methods return an `IntuneMAMEnrollmentStatus` object that has the following information:</span></span>

- <span data-ttu-id="92a51-324">要求に関連付けられているアカウントの ID</span><span class="sxs-lookup"><span data-stu-id="92a51-324">The identity of the account associated with the request</span></span>
- <span data-ttu-id="92a51-325">要求の結果を示す状態コード</span><span class="sxs-lookup"><span data-stu-id="92a51-325">A status code that indicates the result of the request</span></span>
- <span data-ttu-id="92a51-326">エラー文字列とステータス コードの説明</span><span class="sxs-lookup"><span data-stu-id="92a51-326">An error string with a description of the status code</span></span>
- <span data-ttu-id="92a51-327">`NSError` オブジェクト</span><span class="sxs-lookup"><span data-stu-id="92a51-327">An `NSError` object</span></span>

<span data-ttu-id="92a51-328">このオブジェクトは、返される可能性のある特定のステータス コードと共に `IntuneMAMEnrollmentStatus.h` で定義されています。</span><span class="sxs-lookup"><span data-stu-id="92a51-328">This object is defined in `IntuneMAMEnrollmentStatus.h`, along with the specific status codes that can be returned.</span></span>


### <a name="sample-code"></a><span data-ttu-id="92a51-329">サンプル コード</span><span class="sxs-lookup"><span data-stu-id="92a51-329">Sample code</span></span>

<span data-ttu-id="92a51-330">デリゲート メソッドの実装例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="92a51-330">These are example implementations of the delegate methods:</span></span>

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}
```

## <a name="app-restart"></a><span data-ttu-id="92a51-331">アプリの再起動</span><span class="sxs-lookup"><span data-stu-id="92a51-331">App restart</span></span>

<span data-ttu-id="92a51-332">アプリはアプリ保護ポリシーを初めて受け取ったときに、必要なフックを適用するために再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-332">When an app receives app protection policies for the first time, it must restart to apply the required hooks.</span></span> <span data-ttu-id="92a51-333">再起動が必要になった場合に、これをアプリに通知するメソッドは、Headers/IntuneMAMPolicyDelegate.h で SDK によりデリゲート メソッドが提供されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-333">To notify the app that a restart needs to happen, the SDK provides a delegate method in Headers/IntuneMAMPolicyDelegate.h.</span></span>

```objc
 - (BOOL) restartApplication
```
<span data-ttu-id="92a51-334">このメソッドの戻り値は SDK に、アプリケーションが必要な再起動を処理する必要があるかどうかを通知します。</span><span class="sxs-lookup"><span data-stu-id="92a51-334">The return value of this method tells the SDK if the application must handle the required restart:</span></span>   

 - <span data-ttu-id="92a51-335">true が返された場合は、アプリケーションは再起動を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-335">If true is returned, the application must handle the restart.</span></span>   

 - <span data-ttu-id="92a51-336">false が返された場合は、SDK はこのメソッドから返った後でアプリケーションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="92a51-336">If false is returned, the SDK will restart the application after this method returns.</span></span> <span data-ttu-id="92a51-337">SDK はすぐにダイアログ ボックスを表示し、アプリケーションを再起動するようにユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="92a51-337">The SDK will immediately show a dialog box that tells the user to restart the application.</span></span>

## <a name="customize-your-apps-behavior"></a><span data-ttu-id="92a51-338">アプリの動作をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="92a51-338">Customize your app's behavior</span></span>

<span data-ttu-id="92a51-339">Intune App SDK にはいくつかの API が用意されています。これらを呼び出すことで、アプリに展開されている Intune アプリ保護ポリシーに関する情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-339">The Intune App SDK has several APIs you can call to get information about the Intune app protection policy deployed to the app.</span></span> <span data-ttu-id="92a51-340">このデータを使用して、アプリの動作をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-340">You can use this data to customize your app's behavior.</span></span> <span data-ttu-id="92a51-341">アプリ保護ポリシーのほとんどの設定は、アプリケーションではなく、SDK で自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-341">Most app protection policy settings are automatically enforced by the SDK and not the application.</span></span> <span data-ttu-id="92a51-342">アプリで実装する必要がある設定は、名前を付けて保存のコントロールのみです。</span><span class="sxs-lookup"><span data-stu-id="92a51-342">The only setting that the app should implement is the Save-as control.</span></span>

### <a name="get-app-protection-policy"></a><span data-ttu-id="92a51-343">アプリ保護ポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="92a51-343">Get app protection policy</span></span>

#### <a name="intunemampolicymanagerh"></a><span data-ttu-id="92a51-344">IntuneMAMPolicyManager.h</span><span class="sxs-lookup"><span data-stu-id="92a51-344">IntuneMAMPolicyManager.h</span></span>
<span data-ttu-id="92a51-345">IntuneMAMPolicyManager クラスでは、アプリケーションに展開された Intune アプリ保護ポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="92a51-345">The IntuneMAMPolicyManager class exposes the Intune app protection policy deployed to the application.</span></span> <span data-ttu-id="92a51-346">特に、[複数 ID を有効にする](#-enable-multi-identity-optional)のに役立つ API を公開します。</span><span class="sxs-lookup"><span data-stu-id="92a51-346">Notably, it exposes APIs that are useful for [Enabling multi-identity](#-enable-multi-identity-optional).</span></span>

#### <a name="intunemampolicyh"></a><span data-ttu-id="92a51-347">IntuneMAMPolicy.h</span><span class="sxs-lookup"><span data-stu-id="92a51-347">IntuneMAMPolicy.h</span></span>
<span data-ttu-id="92a51-348">IntuneMAMPolicy クラスでは、アプリケーションに展開された Intune アプリ保護ポリシーを公開します。</span><span class="sxs-lookup"><span data-stu-id="92a51-348">The IntuneMAMPolicy class exposes the Intune app protection policy deployed to the application.</span></span> <span data-ttu-id="92a51-349">このクラスで公開されるほとんどのポリシー設定は SDK で適用されますが、ポリシー設定の適用方法に基づいて、アプリの動作をいつでもカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-349">Most the policy settings exposed in this class are enforced by the SDK, but you can always customize your app's behavior based on how policy settings are enforced.</span></span>

<span data-ttu-id="92a51-350">このクラスでは、名前を付けて保存コントロールの実装に必要ないくつかの API を公開します。これについては、次のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="92a51-350">This class exposes some APIs needed to implement save-as controls, detailed in the next section.</span></span>

### <a name="implement-save-as-controls"></a><span data-ttu-id="92a51-351">名前を付けて保存コントロールの実装</span><span class="sxs-lookup"><span data-stu-id="92a51-351">Implement save-as controls</span></span>

<span data-ttu-id="92a51-352">IT 管理者は Intune を使用して、管理対象アプリでのデータの保存先として利用可能な記憶域の場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-352">Intune lets IT admins select which storage locations a managed app can save data to.</span></span> <span data-ttu-id="92a51-353">アプリでは **isSaveToAllowedForLocation** API を使用して、**IntuneMAMPolicy.h** で定義されている、許可された記憶域の場所を Intune App SDK に照会することができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-353">Apps can query the Intune App SDK for allowed storage locations by using the **isSaveToAllowedForLocation** API, defined in **IntuneMAMPolicy.h**.</span></span>

<span data-ttu-id="92a51-354">アプリで管理対象データをクラウドの記憶域またはローカルの場所に保存するには、**isSaveToAllowedForLocation** API を使用し、IT 管理者がその場所にデータを保存できるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-354">Before apps can save managed data to a cloud-storage or local location, they must check with the **isSaveToAllowedForLocation** API to know if the IT admin has allowed data to be saved there.</span></span>

<span data-ttu-id="92a51-355">アプリで **isSaveToAllowedForLocation** API を使用する場合、記憶域の場所の UPN を渡す必要があります (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="92a51-355">When apps use the **isSaveToAllowedForLocation** API, they must pass in the UPN for the storage location, if it is available.</span></span>

#### <a name="supported-save-locations"></a><span data-ttu-id="92a51-356">サポートされている保存場所</span><span class="sxs-lookup"><span data-stu-id="92a51-356">Supported save locations</span></span>

<span data-ttu-id="92a51-357">**isSaveToAllowedForLocation** API は、IntuneMAMPolicy.h で定義されている次の場所にデータを保存することを IT 監理者が許可しているかどうかを確認するための定数を提供します。</span><span class="sxs-lookup"><span data-stu-id="92a51-357">The **isSaveToAllowedForLocation** API provides constants to check whether the IT admin permits data to be saved to the following locations defined in IntuneMAMPolicy.h:</span></span>

* <span data-ttu-id="92a51-358">IntuneMAMSaveLocationOther</span><span class="sxs-lookup"><span data-stu-id="92a51-358">IntuneMAMSaveLocationOther</span></span>
* <span data-ttu-id="92a51-359">IntuneMAMSaveLocationOneDriveForBusiness</span><span class="sxs-lookup"><span data-stu-id="92a51-359">IntuneMAMSaveLocationOneDriveForBusiness</span></span>
* <span data-ttu-id="92a51-360">IntuneMAMSaveLocationSharePoint</span><span class="sxs-lookup"><span data-stu-id="92a51-360">IntuneMAMSaveLocationSharePoint</span></span>
* <span data-ttu-id="92a51-361">IntuneMAMSaveLocationLocalDrive</span><span class="sxs-lookup"><span data-stu-id="92a51-361">IntuneMAMSaveLocationLocalDrive</span></span>

<span data-ttu-id="92a51-362">アプリでは、**isSaveToAllowedForLocation** API で定数を使用して、OneDrive for Business などの "管理対象" の場所、または "個人用" の場所にデータを保存できるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-362">Apps should use the constants in the **isSaveToAllowedForLocation** API to check if data can be saved to locations considered "managed," like OneDrive for Business, or "personal."</span></span> <span data-ttu-id="92a51-363">さらに、アプリが場所について "管理対象" か "個人用" かを確認できない場合は、API を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-363">Additionally, the API should be used when the app can't check whether a location is "managed" or "personal."</span></span>

<span data-ttu-id="92a51-364">"個人用" と認識される場所は、`IntuneMAMSaveLocationOther` 定数で表されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-364">Locations known to be "personal" are represented by the `IntuneMAMSaveLocationOther` constant.</span></span>

<span data-ttu-id="92a51-365">アプリでデータをローカル デバイス上の任意の場所に保存する場合は、`IntuneMAMSaveLocationLocalDrive` 定数を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-365">The `IntuneMAMSaveLocationLocalDrive` constant should be used when the app is saving data to any location on the local device.</span></span>

## <a name="configure-settings-for-the-intune-app-sdk"></a><span data-ttu-id="92a51-366">Intune App SDK の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="92a51-366">Configure settings for the Intune App SDK</span></span>

<span data-ttu-id="92a51-367">アプリケーションの Info.plist ファイルの **IntuneMAMSettings** ディクショナリを使用し、Intune App SDK をセットアップして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-367">You can use the **IntuneMAMSettings** dictionary in the application’s Info.plist file to set up and configure the Intune App SDK.</span></span> <span data-ttu-id="92a51-368">IntuneMAMSettings ディクショナリが Info.plist file に表示されない場合は、アプリの Info.plist に "IntuneMAMSettings" の名前でディクショナリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-368">If the IntuneMAMSettings dictionary is not seen in your Info.plist file, you should create a dictionary in your app's Info.plist with the field name "IntuneMAMSettings."</span></span>

<span data-ttu-id="92a51-369">IntuneMAMSettings ディクショナリの下に、構成設定のキー列/値列を追加して SDK を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-369">Under the IntuneMAMSettings dictionary, you can add key/value rows of configuration settings to configure the SDK.</span></span> <span data-ttu-id="92a51-370">サポートされているすべての設定の一覧を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="92a51-370">The table below lists all supported settings.</span></span>

<span data-ttu-id="92a51-371">これらの設定の一部は前のセクションで説明しています。一部の設定はすべてのアプリには適用されません。</span><span class="sxs-lookup"><span data-stu-id="92a51-371">Some of these settings might have been covered in previous sections, and some do not apply to all apps.</span></span>

<span data-ttu-id="92a51-372">Setting</span><span class="sxs-lookup"><span data-stu-id="92a51-372">Setting</span></span>  | <span data-ttu-id="92a51-373">型</span><span class="sxs-lookup"><span data-stu-id="92a51-373">Type</span></span>  | <span data-ttu-id="92a51-374">定義</span><span class="sxs-lookup"><span data-stu-id="92a51-374">Definition</span></span> | <span data-ttu-id="92a51-375">必須</span><span class="sxs-lookup"><span data-stu-id="92a51-375">Required?</span></span>
--       |  --   |   --       |  --
<span data-ttu-id="92a51-376">ADALClientId</span><span class="sxs-lookup"><span data-stu-id="92a51-376">ADALClientId</span></span>  | <span data-ttu-id="92a51-377">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-377">String</span></span>  | <span data-ttu-id="92a51-378">アプリの Azure AD クライアント識別子。</span><span class="sxs-lookup"><span data-stu-id="92a51-378">The app’s Azure AD client identifier.</span></span> | <span data-ttu-id="92a51-379">アプリが ADAL を使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-379">Required if the app uses ADAL.</span></span> |
<span data-ttu-id="92a51-380">ADALAuthority</span><span class="sxs-lookup"><span data-stu-id="92a51-380">ADALAuthority</span></span> | <span data-ttu-id="92a51-381">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-381">String</span></span> | <span data-ttu-id="92a51-382">使用されているアプリの Azure AD 機関。</span><span class="sxs-lookup"><span data-stu-id="92a51-382">The app's Azure AD authority in use.</span></span> <span data-ttu-id="92a51-383">AAD アカウントが構成されている独自の環境を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-383">You should use your own environment where AAD accounts have been configured.</span></span> | <span data-ttu-id="92a51-384">アプリが ADAL を使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-384">Required if the app uses ADAL.</span></span> <span data-ttu-id="92a51-385">この値が存在しない場合は、Intune の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-385">If this value is absent, an Intune default is used.</span></span>|
<span data-ttu-id="92a51-386">ADALRedirectUri</span><span class="sxs-lookup"><span data-stu-id="92a51-386">ADALRedirectUri</span></span>  | <span data-ttu-id="92a51-387">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-387">String</span></span>  | <span data-ttu-id="92a51-388">アプリの Azure AD リダイレクト URI。</span><span class="sxs-lookup"><span data-stu-id="92a51-388">The app’s Azure AD redirect URI.</span></span> | <span data-ttu-id="92a51-389">アプリが ADAL を使用する場合は、ADALRedirectUri または ADALRedirectScheme が必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-389">ADALRedirectUri or ADALRedirectScheme is required if the app uses ADAL.</span></span>  |
<span data-ttu-id="92a51-390">ADALRedirectScheme</span><span class="sxs-lookup"><span data-stu-id="92a51-390">ADALRedirectScheme</span></span>  | <span data-ttu-id="92a51-391">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-391">String</span></span>  | <span data-ttu-id="92a51-392">アプリの Azure AD リダイレクト スキーム。</span><span class="sxs-lookup"><span data-stu-id="92a51-392">The app's Azure AD redirect scheme.</span></span> <span data-ttu-id="92a51-393">アプリケーションのリダイレクト URI が `scheme://bundle_id` 形式の場合は、ADALRedirectUri の代わりにこれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-393">This can be used in place of ADALRedirectUri if the application's redirect URI is in the format `scheme://bundle_id`.</span></span> | <span data-ttu-id="92a51-394">アプリが ADAL を使用する場合は、ADALRedirectUri または ADALRedirectScheme が必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-394">ADALRedirectUri or ADALRedirectScheme is required if the app uses ADAL.</span></span> |
<span data-ttu-id="92a51-395">ADALLogOverrideDisabled</span><span class="sxs-lookup"><span data-stu-id="92a51-395">ADALLogOverrideDisabled</span></span> | <span data-ttu-id="92a51-396">ブール型</span><span class="sxs-lookup"><span data-stu-id="92a51-396">Boolean</span></span>  | <span data-ttu-id="92a51-397">SDK がすべての ADAL ログ (アプリからの ADAL 呼び出しがある場合はこれを含む) をログ ファイルにルーティングするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-397">Specifies whether the SDK will route all ADAL logs (including ADAL calls from the app, if any) to its own log file.</span></span> <span data-ttu-id="92a51-398">既定は [いいえ] です。</span><span class="sxs-lookup"><span data-stu-id="92a51-398">Defaults to NO.</span></span> <span data-ttu-id="92a51-399">アプリで独自の ADAL ログ コールバックを設定する場合は [はい] に設定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-399">Set to YES if the app will set its own ADAL log callback.</span></span> | <span data-ttu-id="92a51-400">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-400">Optional.</span></span> |
<span data-ttu-id="92a51-401">ADALCacheKeychainGroupOverride</span><span class="sxs-lookup"><span data-stu-id="92a51-401">ADALCacheKeychainGroupOverride</span></span> | <span data-ttu-id="92a51-402">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-402">String</span></span>  | <span data-ttu-id="92a51-403">"com.microsoft.adalcache" の代わりに ADAL キャッシュに使用するキーチェーン グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-403">Specifies the keychain group to use for the ADAL cache, instead of “com.microsoft.adalcache."</span></span> <span data-ttu-id="92a51-404">これにはアプリ ID プレフィックスは含まれないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-404">Note that this doesn’t have the app-id prefix.</span></span> <span data-ttu-id="92a51-405">実行時に指定された文字列の前に付加されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-405">That will be prefixed to the provided string at runtime.</span></span> | <span data-ttu-id="92a51-406">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-406">Optional.</span></span> |
<span data-ttu-id="92a51-407">AppGroupIdentifiers</span><span class="sxs-lookup"><span data-stu-id="92a51-407">AppGroupIdentifiers</span></span> | <span data-ttu-id="92a51-408">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="92a51-408">Array of string</span></span>  | <span data-ttu-id="92a51-409">アプリの権利 com.apple.security.application-groups セクションのアプリケーション グループの配列。</span><span class="sxs-lookup"><span data-stu-id="92a51-409">Array of app groups from the app’s entitlements com.apple.security.application-groups section.</span></span> | <span data-ttu-id="92a51-410">アプリでアプリケーション グループを使用する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="92a51-410">Required if the app uses application groups.</span></span> |
<span data-ttu-id="92a51-411">ContainingAppBundleId</span><span class="sxs-lookup"><span data-stu-id="92a51-411">ContainingAppBundleId</span></span> | <span data-ttu-id="92a51-412">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-412">String</span></span> | <span data-ttu-id="92a51-413">アプリケーションを含む拡張機能のバンドル ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-413">Specifies the bundle ID of the extension’s containing application.</span></span> | <span data-ttu-id="92a51-414">iOS の拡張機能に必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-414">Required for iOS extensions.</span></span> |
<span data-ttu-id="92a51-415">DebugSettingsEnabled</span><span class="sxs-lookup"><span data-stu-id="92a51-415">DebugSettingsEnabled</span></span>| <span data-ttu-id="92a51-416">ブール型</span><span class="sxs-lookup"><span data-stu-id="92a51-416">Boolean</span></span> | <span data-ttu-id="92a51-417">YES に設定すると、Settings バンドル内のテスト ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-417">If set to YES, test policies within the Settings bundle can be applied.</span></span> <span data-ttu-id="92a51-418">この設定を有効にしたままアプリケーションを出荷しては*なりません*。</span><span class="sxs-lookup"><span data-stu-id="92a51-418">Applications should *not* be shipped with this setting enabled.</span></span> | <span data-ttu-id="92a51-419">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-419">Optional.</span></span> |
<span data-ttu-id="92a51-420">MainNibFile</span><span class="sxs-lookup"><span data-stu-id="92a51-420">MainNibFile</span></span><br><span data-ttu-id="92a51-421">MainNibFile~ipad</span><span class="sxs-lookup"><span data-stu-id="92a51-421">MainNibFile~ipad</span></span>  | <span data-ttu-id="92a51-422">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-422">String</span></span>  | <span data-ttu-id="92a51-423">この設定には、アプリケーションのメイン nib ファイル名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-423">This setting should have the application’s main nib file name.</span></span>  | <span data-ttu-id="92a51-424">アプリケーションの Info.plist で MainNibFile が定義されている場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="92a51-424">Required if the application defines MainNibFile in Info.plist.</span></span> |
<span data-ttu-id="92a51-425">MainStoryboardFile</span><span class="sxs-lookup"><span data-stu-id="92a51-425">MainStoryboardFile</span></span><br><span data-ttu-id="92a51-426">MainStoryboardFile~ipad</span><span class="sxs-lookup"><span data-stu-id="92a51-426">MainStoryboardFile~ipad</span></span>  | <span data-ttu-id="92a51-427">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-427">String</span></span>  | <span data-ttu-id="92a51-428">この設定には、アプリケーションのメインのストーリーボードのファイル名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-428">This setting should have the application’s main storyboard file name.</span></span> | <span data-ttu-id="92a51-429">アプリケーションの Info.plist で UIMainStoryboardFile が定義されている場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="92a51-429">Required if the application defines UIMainStoryboardFile in Info.plist.</span></span> |
<span data-ttu-id="92a51-430">AutoEnrollOnLaunch</span><span class="sxs-lookup"><span data-stu-id="92a51-430">AutoEnrollOnLaunch</span></span>| <span data-ttu-id="92a51-431">ブール型</span><span class="sxs-lookup"><span data-stu-id="92a51-431">Boolean</span></span>| <span data-ttu-id="92a51-432">既存の管理対象の ID が検出され、それがまだ登録されていない場合、起動時に自動登録を試みるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-432">Specifies whether the app should attempt to automatically enroll on launch if an existing managed identity is detected and it has not yet done so.</span></span> <span data-ttu-id="92a51-433">既定は [いいえ] です。</span><span class="sxs-lookup"><span data-stu-id="92a51-433">Defaults to NO.</span></span> <br><br> <span data-ttu-id="92a51-434">注意: 管理対象の ID が検出されない場合、またはその ID に対する有効なトークンが ADAL キャッシュ内に存在しない場合、アプリで MAMPolicyRequired も YES に設定されていなければ、資格情報を求めることなく登録の試みは失敗します。</span><span class="sxs-lookup"><span data-stu-id="92a51-434">Notes: If no managed identity is found or no valid token for the identity is available in the ADAL cache, the enrollment attempt will silently fail without prompting for credentials, unless the app has also set MAMPolicyRequired to YES.</span></span> | <span data-ttu-id="92a51-435">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-435">Optional.</span></span> |
<span data-ttu-id="92a51-436">MAMPolicyRequired</span><span class="sxs-lookup"><span data-stu-id="92a51-436">MAMPolicyRequired</span></span>| <span data-ttu-id="92a51-437">ブール型</span><span class="sxs-lookup"><span data-stu-id="92a51-437">Boolean</span></span>| <span data-ttu-id="92a51-438">アプリに Intune アプリ保護ポリシーがない場合に、アプリの起動をブロックするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-438">Specifies whether the app will be blocked from starting if the app does not have an Intune app protection policy.</span></span> <span data-ttu-id="92a51-439">既定は [いいえ] です。</span><span class="sxs-lookup"><span data-stu-id="92a51-439">Defaults to NO.</span></span> <br><br> <span data-ttu-id="92a51-440">注: MAMPolicyRequired を YES にした状態でアプリを App Store に送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="92a51-440">Notes: Apps cannot be submitted to the App Store with MAMPolicyRequired set to YES.</span></span> <span data-ttu-id="92a51-441">MAMPolicyRequired を YES に設定した場合は、AutoEnrollOnLaunch も YES に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-441">When setting MAMPolicyRequired to YES, AutoEnrollOnLaunch should also be set to YES.</span></span> | <span data-ttu-id="92a51-442">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-442">Optional.</span></span> |
<span data-ttu-id="92a51-443">MAMPolicyWarnAbsent</span><span class="sxs-lookup"><span data-stu-id="92a51-443">MAMPolicyWarnAbsent</span></span> | <span data-ttu-id="92a51-444">ブール型</span><span class="sxs-lookup"><span data-stu-id="92a51-444">Boolean</span></span>| <span data-ttu-id="92a51-445">アプリに Intune アプリ保護ポリシーがない場合に、アプリの起動時にユーザーに警告するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-445">Specifies whether the app will warn the user during launch if the app does not have an Intune app protection policy.</span></span> <br><br> <span data-ttu-id="92a51-446">注: ユーザーは警告を無視しても、ポリシーなしでアプリの使用が許可されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-446">Note: Users will still be allowed to use the app without policy after dismissing the warning.</span></span> | <span data-ttu-id="92a51-447">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-447">Optional.</span></span> |
<span data-ttu-id="92a51-448">MultiIdentity</span><span class="sxs-lookup"><span data-stu-id="92a51-448">MultiIdentity</span></span> | <span data-ttu-id="92a51-449">ブール型</span><span class="sxs-lookup"><span data-stu-id="92a51-449">Boolean</span></span>| <span data-ttu-id="92a51-450">アプリが複数 ID 対応かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-450">Specifies whether the app is multi-identity aware.</span></span> | <span data-ttu-id="92a51-451">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-451">Optional.</span></span> |
<span data-ttu-id="92a51-452">SplashIconFile</span><span class="sxs-lookup"><span data-stu-id="92a51-452">SplashIconFile</span></span> <br><span data-ttu-id="92a51-453">SplashIconFile~ipad</span><span class="sxs-lookup"><span data-stu-id="92a51-453">SplashIconFile~ipad</span></span> | <span data-ttu-id="92a51-454">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-454">String</span></span>  | <span data-ttu-id="92a51-455">Intune スプラッシュ (起動) アイコン ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-455">Specifies the Intune splash (startup) icon file.</span></span> | <span data-ttu-id="92a51-456">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-456">Optional.</span></span> |
<span data-ttu-id="92a51-457">SplashDuration</span><span class="sxs-lookup"><span data-stu-id="92a51-457">SplashDuration</span></span> | <span data-ttu-id="92a51-458">数値</span><span class="sxs-lookup"><span data-stu-id="92a51-458">Number</span></span> | <span data-ttu-id="92a51-459">アプリケーションの起動時に Intune 起動画面が表示される最短時間 (秒)。</span><span class="sxs-lookup"><span data-stu-id="92a51-459">Minimum amount of time, in seconds, that the Intune startup screen will be shown at application launch.</span></span> <span data-ttu-id="92a51-460">既定値は 1.5 です。</span><span class="sxs-lookup"><span data-stu-id="92a51-460">Defaults to 1.5.</span></span> | <span data-ttu-id="92a51-461">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-461">Optional.</span></span> |
<span data-ttu-id="92a51-462">BackgroundColor</span><span class="sxs-lookup"><span data-stu-id="92a51-462">BackgroundColor</span></span>| <span data-ttu-id="92a51-463">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-463">String</span></span>| <span data-ttu-id="92a51-464">起動画面と PIN 画面の背景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-464">Specifies the background color for the startup and PIN screens.</span></span> <span data-ttu-id="92a51-465">#XXXXXX の形式の 16 進 RGB 文字列を受け付けます。X には 0 ～ 9 または A ～ F を使用できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-465">Accepts a hexadecimal RGB string in the form of #XXXXXX, where X can range from 0-9 or A-F.</span></span> <span data-ttu-id="92a51-466">シャープ記号は省略してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="92a51-466">The pound sign might be omitted.</span></span>   | <span data-ttu-id="92a51-467">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-467">Optional.</span></span> <span data-ttu-id="92a51-468">既定値は明るい灰色です。</span><span class="sxs-lookup"><span data-stu-id="92a51-468">Defaults to light grey.</span></span> |
<span data-ttu-id="92a51-469">ForegroundColor</span><span class="sxs-lookup"><span data-stu-id="92a51-469">ForegroundColor</span></span>| <span data-ttu-id="92a51-470">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-470">String</span></span>| <span data-ttu-id="92a51-471">テキストの色など、起動画面と PIN 画面の前景色を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-471">Specifies the foreground color for the startup and PIN screens, like text color.</span></span> <span data-ttu-id="92a51-472">#XXXXXX の形式の 16 進 RGB 文字列を受け付けます。X には 0 ～ 9 または A ～ F を使用できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-472">Accepts a hexadecimal RGB string in the form of #XXXXXX, where X can range from 0-9 or A-F.</span></span> <span data-ttu-id="92a51-473">シャープ記号は省略してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="92a51-473">The pound sign might be omitted.</span></span>  | <span data-ttu-id="92a51-474">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-474">Optional.</span></span> <span data-ttu-id="92a51-475">既定値は黒です。</span><span class="sxs-lookup"><span data-stu-id="92a51-475">Defaults to black.</span></span> |
<span data-ttu-id="92a51-476">AccentColor</span><span class="sxs-lookup"><span data-stu-id="92a51-476">AccentColor</span></span> | <span data-ttu-id="92a51-477">文字列型</span><span class="sxs-lookup"><span data-stu-id="92a51-477">String</span></span>| <span data-ttu-id="92a51-478">PIN 画面のアクセント カラーを指定します。ボタン テキストの色やボックスの強調表示色などです。</span><span class="sxs-lookup"><span data-stu-id="92a51-478">Specifies the accent color for the PIN screen, like button text color and box highlight color.</span></span> <span data-ttu-id="92a51-479">#XXXXXX の形式の 16 進 RGB 文字列を受け付けます。X には 0 ～ 9 または A ～ F を使用できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-479">Accepts a hexadecimal RGB string in the form of #XXXXXX, where X can range from 0-9 or A-F.</span></span> <span data-ttu-id="92a51-480">シャープ記号は省略してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="92a51-480">The pound sign might be omitted.</span></span>| <span data-ttu-id="92a51-481">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-481">Optional.</span></span> <span data-ttu-id="92a51-482">既定値はシステムの青です。</span><span class="sxs-lookup"><span data-stu-id="92a51-482">Defaults to system blue.</span></span> |
<span data-ttu-id="92a51-483">MAMTelemetryDisabled</span><span class="sxs-lookup"><span data-stu-id="92a51-483">MAMTelemetryDisabled</span></span>| <span data-ttu-id="92a51-484">ブール型</span><span class="sxs-lookup"><span data-stu-id="92a51-484">Boolean</span></span>| <span data-ttu-id="92a51-485">SDK に製品利用統計情報データをバックエンドに送信させないかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-485">Specifies if the SDK will not send any telemetry data to its back end.</span></span>| <span data-ttu-id="92a51-486">任意。</span><span class="sxs-lookup"><span data-stu-id="92a51-486">Optional.</span></span> |
<span data-ttu-id="92a51-487">WebViewHandledURLSchemes</span><span class="sxs-lookup"><span data-stu-id="92a51-487">WebViewHandledURLSchemes</span></span> | <span data-ttu-id="92a51-488">文字列の配列</span><span class="sxs-lookup"><span data-stu-id="92a51-488">Array of Strings</span></span> | <span data-ttu-id="92a51-489">アプリの WebView で処理する URL スキームを指定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-489">Specifies the URL schemes that your app's WebView handles.</span></span> | <span data-ttu-id="92a51-490">リンクや JavaScript で URL を処理する WebView をアプリが使用する場合は、必須です。</span><span class="sxs-lookup"><span data-stu-id="92a51-490">Required if your app uses a WebView that handles URLs via links and/or javascript.</span></span> |  

> [!NOTE]
> <span data-ttu-id="92a51-491">アプリが App Store にリリースされる場合は、App Store の標準に従って、`MAMPolicyRequired` を "NO" に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-491">If your app will be released to the App Store, `MAMPolicyRequired` must be set to "NO," per App Store standards.</span></span>

## <a name="enabling-mam-targeted-configuration-for-your-ios-applications"></a><span data-ttu-id="92a51-492">iOS アプリケーションの MAM 対象の構成を有効にする</span><span class="sxs-lookup"><span data-stu-id="92a51-492">Enabling MAM targeted configuration for your iOS applications</span></span>
<span data-ttu-id="92a51-493">MAM 対象の構成により、アプリは Intune App SDK から構成データを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-493">MAM targeted configuration allows an app to receive configuration data through the Intune App SDK.</span></span> <span data-ttu-id="92a51-494">このデータの形式とバリエーションは、アプリケーションの所有者/開発者が定義して Intune のユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-494">The format and variants of this data must be defined and communicated to Intune customers by the application owner/developer.</span></span> <span data-ttu-id="92a51-495">Intune の管理者は、Intune Azure Portal を使って、構成データの対象設定と展開を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-495">Intune administrators can target and deploy configuration data via the Intune Azure portal.</span></span> <span data-ttu-id="92a51-496">Intune App SDK for iOS (v 7.0.1) の一部として、MAM 対象構成に入っているアプリに MAM サービス経由で MAM 対象構成データを与えることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-496">As of the Intune App SDK for iOS (v 7.0.1), apps that are participating in MAM targeted configuration can be provded MAM targeted configuration data via the MAM Service.</span></span> <span data-ttu-id="92a51-497">アプリケーション構成データは、MDM チャネルではなく MAM サービスを通して直接アプリにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="92a51-497">The application configuration data is pushed through our MAM Service directly to the app instead of through the MDM channel.</span></span> <span data-ttu-id="92a51-498">Intune App SDK は、これらのコンソールから取得されたデータにアクセスするためのクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="92a51-498">The Intune App SDK provides a class to access the data retrieved from these consoles.</span></span> <span data-ttu-id="92a51-499">次を前提条件として考慮してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-499">Consider the following as prerequisites:</span></span> <br>
* <span data-ttu-id="92a51-500">MAM 対象構成 UI にアクセスする前に、アプリを MAM-WE 登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-500">The app needs to be MAM-WE enrolled before you access the MAM targeted config UI.</span></span> <span data-ttu-id="92a51-501">MAM-WE に関する詳細については、Intune App SDK ガイドの「[デバイス登録が不要なアプリの保護ポリシー](https://docs.microsoft.com/en-us/intune/app-sdk-ios#app-protection-policy-without-device-enrollment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-501">For more information about MAM-WE, see [App protection policy without device enrollment in the Intune App SDK guide](https://docs.microsoft.com/en-us/intune/app-sdk-ios#app-protection-policy-without-device-enrollment).</span></span>
* <span data-ttu-id="92a51-502">アプリのソース ファイルに ```IntuneMAMAppConfigManager.h``` を追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-502">Include ```IntuneMAMAppConfigManager.h``` in your app's source file.</span></span>
* <span data-ttu-id="92a51-503">```[[IntuneMAMAppConfig instance] appConfigForIdentity:]``` を呼び出し、アプリ構成オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="92a51-503">Call ```[[IntuneMAMAppConfig instance] appConfigForIdentity:]``` to get the App Config Object.</span></span>
* <span data-ttu-id="92a51-504">```IntuneMAMAppConfig``` オブジェクトで適切なセレクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="92a51-504">Call the appropriate selector on ```IntuneMAMAppConfig``` object.</span></span> <span data-ttu-id="92a51-505">たとえば、アプリケーションのキーが文字列の場合、```stringValueForKey``` や ```allStringsForKey``` を使用します。</span><span class="sxs-lookup"><span data-stu-id="92a51-505">For example, if your application's key is a string, you'd want to use ```stringValueForKey``` or ```allStringsForKey```.</span></span> <span data-ttu-id="92a51-506">```IntuneMAMAppConfig.h header``` ファイルには、戻り値/エラー条件が記載されています。</span><span class="sxs-lookup"><span data-stu-id="92a51-506">The ```IntuneMAMAppConfig.h header``` file talks about return values/error conditions.</span></span>

<span data-ttu-id="92a51-507">MAM 対象の構成値に関する Graph API の機能について詳しくは、[Graph API リファレンスの MAM 対象の構成](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92a51-507">For more information about the capabilities of the Graph API with respect to the MAM targeted configuration values, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span></span> <br>

<span data-ttu-id="92a51-508">iOS で MAM 対象アプリ構成ポリシーを作成する方法については、「[iOS 用 Microsoft Intune アプリ構成ポリシーを使用する方法](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-ios)」の MAM 対象アプリ構成セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-508">For more information about how to create a MAM targeted app configuration policy in iOS, see the section on MAM targeted app config in [How to use Microsoft Intune app configuration policies for iOS](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-ios).</span></span>

## <a name="telemetry"></a><span data-ttu-id="92a51-509">製品利用統計情報</span><span class="sxs-lookup"><span data-stu-id="92a51-509">Telemetry</span></span>

<span data-ttu-id="92a51-510">iOS 用 Intune App SDK では、既定で、次の使用状況イベントに関する製品利用統計情報がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-510">By default, the Intune App SDK for iOS logs telemetry data on the following usage events.</span></span> <span data-ttu-id="92a51-511">このデータは、Microsoft Intune に送信されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-511">This data is sent to Microsoft Intune.</span></span>

* <span data-ttu-id="92a51-512">**アプリの起動:** Microsoft Intune が MAM 対応アプリの使用状況を管理タイプ別に確認するために役立ちます (MDM を使用した MAM、MDM 登録を使用しない MAM など)。</span><span class="sxs-lookup"><span data-stu-id="92a51-512">**App launch**: To help Microsoft Intune learn about MAM-enabled app usage by management type (MAM with MDM, MAM without MDM enrollment, and so on).</span></span>

* <span data-ttu-id="92a51-513">**登録呼び出し:** Microsoft Intune がクライアント側から開始された登録呼び出しの成功率と他のパフォーマンス指標を確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="92a51-513">**Enrollment calls**: To help Microsoft Intune learn about success rate and other performance metrics of enrollment calls initiated from the client side.</span></span>

> [!NOTE]
> <span data-ttu-id="92a51-514">モバイル アプリケーションから Intune App SDK の製品利用統計情報を Microsoft Intune に送信しない場合は、Intune App SDK 製品利用統計情報のキャプチャを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-514">If you choose not to send Intune App SDK telemetry data to Microsoft Intune from your mobile application, you must disable Intune App SDK telemetry capture.</span></span> <span data-ttu-id="92a51-515">IntuneMAMSettings ディクショナリで、プロパティ `MAMTelemetryDisabled` を [はい] に設定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-515">Set the property `MAMTelemetryDisabled` to YES in the IntuneMAMSettings dictionary.</span></span>

## <a name="enable-multi-identity-optional"></a><span data-ttu-id="92a51-516">複数 ID を有効にする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="92a51-516">Enable multi-identity (optional)</span></span>

<span data-ttu-id="92a51-517">既定では、SDK はポリシーをアプリ全体に適用します。</span><span class="sxs-lookup"><span data-stu-id="92a51-517">By default, the SDK applies a policy to the app as a whole.</span></span> <span data-ttu-id="92a51-518">複数 ID は、ID 別レベルでのポリシー適用を可能にする MAM の機能です。</span><span class="sxs-lookup"><span data-stu-id="92a51-518">Multi-identity is a MAM feature that you can enable to apply a policy on a per-identity level.</span></span> <span data-ttu-id="92a51-519">これには、他の MAM 機能より多くのアプリの参加が必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-519">This requires more app participation than other MAM features.</span></span>

<span data-ttu-id="92a51-520">アプリは、アクティブな ID を変更するときにアプリ SDK に通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-520">The app must inform the app SDK when it intends to change the active identity.</span></span> <span data-ttu-id="92a51-521">また、SDK は ID の変更が必要なときにもアプリに通知します。</span><span class="sxs-lookup"><span data-stu-id="92a51-521">The SDK also notifies the app when an identity change is required.</span></span> <span data-ttu-id="92a51-522">現時点では、サポートされる管理対象 ID は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="92a51-522">Currently, only one managed identity is supported.</span></span> <span data-ttu-id="92a51-523">ユーザーがデバイスまたはアプリを登録すると、SDK はこの ID を使用し、それをプライマリ管理対象 ID であると判断します。</span><span class="sxs-lookup"><span data-stu-id="92a51-523">After the user enrolls the device or the app, the SDK uses this identity and considers it the primary managed identity.</span></span> <span data-ttu-id="92a51-524">アプリの他のユーザーは、無制限のポリシー設定を持つ管理対象外として扱われます。</span><span class="sxs-lookup"><span data-stu-id="92a51-524">Other users in the app will be treated as unmanaged with unrestricted policy settings.</span></span>

<span data-ttu-id="92a51-525">ID は文字列として簡単に定義されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-525">Note that an identity is simply defined as a string.</span></span> <span data-ttu-id="92a51-526">ID の大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="92a51-526">Identities are case-insensitive.</span></span> <span data-ttu-id="92a51-527">SDK に ID を要求すると返される ID は、大文字と小文字の使い分けが ID 設定時の本来のものと異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-527">Requests to the SDK for an identity might not return the same casing that was originally used when the identity was set.</span></span>

### <a name="identity-overview"></a><span data-ttu-id="92a51-528">ID の概要</span><span class="sxs-lookup"><span data-stu-id="92a51-528">Identity overview</span></span>

<span data-ttu-id="92a51-529">ID は、単にアカウントのユーザー名です (例: user@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="92a51-529">An identity is simply the user name of an account (for example, user@contoso.com).</span></span> <span data-ttu-id="92a51-530">開発者は、次のレベルでアプリの ID を設定できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-530">Developers can set the identity of the app on the following levels:</span></span>

* <span data-ttu-id="92a51-531">**プロセス ID**: プロセス全体に通用する ID を設定し、主として単一の ID アプリケーションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-531">**Process identity**: Sets the process-wide identity and is mainly used for single identity applications.</span></span> <span data-ttu-id="92a51-532">この ID は、すべてのタスク、ファイル、UI に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-532">This identity affects all tasks, files, and UI.</span></span>

* <span data-ttu-id="92a51-533">**UI ID**: 切り取り/コピー/貼り付け、PIN、認証、データ共有など、メイン スレッドでの UI タスクに適用されるポリシーを決定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-533">**UI identity**: Determines what policies are applied to UI tasks on the main thread, like cut/copy/paste, PIN, authentication, and data sharing.</span></span> <span data-ttu-id="92a51-534">UI ID は、ファイル タスク (暗号化やバックアップなど) には適用されません。</span><span class="sxs-lookup"><span data-stu-id="92a51-534">The UI identity does not affect file tasks like encryption and backup.</span></span>

* <span data-ttu-id="92a51-535">**スレッド ID**: 現在のスレッドに適用されるポリシーを決定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-535">**Thread identity**: Affects what policies are applied on the current thread.</span></span> <span data-ttu-id="92a51-536">この ID は、すべてのタスク、ファイル、UI に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-536">This identity affects all tasks, files, and UI.</span></span>

<span data-ttu-id="92a51-537">ユーザーが管理されているかどうかにかかわらず、アプリは ID を適切に設定する役目を担います。</span><span class="sxs-lookup"><span data-stu-id="92a51-537">The app is responsible for setting the identities appropriately, whether or not the user is managed.</span></span>

<span data-ttu-id="92a51-538">常に、すべてのスレッドは UI タスクとファイル タスクのための有効な ID を持っています。</span><span class="sxs-lookup"><span data-stu-id="92a51-538">At any time, every thread has an effective identity for UI tasks and file tasks.</span></span> <span data-ttu-id="92a51-539">これは、適用する必要があるポリシー (ある場合) を確認するために使用される ID です。</span><span class="sxs-lookup"><span data-stu-id="92a51-539">This is the identity that's used to check what policies, if any, should be applied.</span></span> <span data-ttu-id="92a51-540">ID が "ID なし" の場合、またはユーザーが管理されていない場合は、ポリシーは適用されません。</span><span class="sxs-lookup"><span data-stu-id="92a51-540">If the identity is "no identity" or the user is not managed, no policies will be applied.</span></span> <span data-ttu-id="92a51-541">次の図は、有効な ID がどのように特定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="92a51-541">The diagrams below show how the effective identities are determined.</span></span>

  ![Intune App SDK iOS: リンク先フレームワークおよびライブラリ](./media/ios-thread-identities.png)

### <a name="thread-queues"></a><span data-ttu-id="92a51-543">スレッド キュー</span><span class="sxs-lookup"><span data-stu-id="92a51-543">Thread queues</span></span>

<span data-ttu-id="92a51-544">アプリは、多くの場合、スレッド キューに対して非同期タスクと同期タスクをディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="92a51-544">Apps often dispatch asynchronous and synchronous tasks to thread queues.</span></span> <span data-ttu-id="92a51-545">SDK は、Grand Central Dispatch (GCD) 呼び出しをインターセプトして、現在のスレッド ID をディスパッチされたタスクに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="92a51-545">The SDK intercepts Grand Central Dispatch (GCD) calls and associates the current thread identity with the dispatched tasks.</span></span> <span data-ttu-id="92a51-546">タスクの完了時に、SDK はスレッド ID をタスクに関連付けられた ID に一時的に変更し、タスクを完了してから、元のスレッド ID に戻します。</span><span class="sxs-lookup"><span data-stu-id="92a51-546">When the tasks are finished, the SDK temporarily changes the thread identity to the identity associated with the tasks, finishes the tasks, then restores the original thread identity.</span></span>


<span data-ttu-id="92a51-547">`NSOperationQueue` は GCD を基にして作成されているので、`NSOperations` はタスクが `NSOperationQueue` に追加されるときにスレッドの ID で実行されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-547">Because `NSOperationQueue` is built on top of GCD, `NSOperations` will run on the identity of the thread at the time the tasks are added to `NSOperationQueue`.</span></span> <span data-ttu-id="92a51-548">GCD を直接使用してディスパッチされた `NSOperations` または関数も、実行時に現在のスレッド ID を変更できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-548">`NSOperations` or functions dispatched directly through GCD can also change the current thread identity as they are running.</span></span> <span data-ttu-id="92a51-549">この ID は、ディスパッチ スレッドから継承された ID を上書きします。</span><span class="sxs-lookup"><span data-stu-id="92a51-549">This identity will override the identity inherited from the dispatching thread.</span></span>

### <a name="file-owner"></a><span data-ttu-id="92a51-550">ファイルの所有者</span><span class="sxs-lookup"><span data-stu-id="92a51-550">File owner</span></span>

<span data-ttu-id="92a51-551">SDK は、ローカル ファイル所有者の ID を追跡し、適宜、ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="92a51-551">The SDK tracks the identities of local file owners and applies policies accordingly.</span></span> <span data-ttu-id="92a51-552">ファイルの所有者は、ファイルが作成されるとき、またはファイルが切り捨てモードで開かれるときに、設定されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-552">A file owner is established when a file is created or when a file is opened in truncate mode.</span></span> <span data-ttu-id="92a51-553">所有者は、タスクを実行するスレッドの有効なファイル タスク ID に設定されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-553">The owner is set to the effective file task identity of the thread that's performing the task.</span></span>

<span data-ttu-id="92a51-554">または、アプリで `IntuneMAMFilePolicyManager` を使用してファイル所有者 ID を明示的に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="92a51-554">Alternatively, apps can set the file owner identity explicitly by using `IntuneMAMFilePolicyManager`.</span></span> <span data-ttu-id="92a51-555">アプリでは、`IntuneMAMFilePolicyManager` を使用してファイルの所有者を取得し、ファイルの内容を表示する前に UI ID を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-555">Apps can use `IntuneMAMFilePolicyManager` to retrieve the file owner and set the UI identity before showing the file contents.</span></span>

### <a name="shared-data"></a><span data-ttu-id="92a51-556">共有データ</span><span class="sxs-lookup"><span data-stu-id="92a51-556">Shared data</span></span>

<span data-ttu-id="92a51-557">管理対象ユーザーと管理対象外ユーザーの両方のデータを含むファイルをアプリが作成する場合、管理対象ユーザーのデータの暗号化はアプリで行います。</span><span class="sxs-lookup"><span data-stu-id="92a51-557">If the app creates files that have data from both managed and unmanaged users, the app is responsible for encrypting the managed user’s data.</span></span> <span data-ttu-id="92a51-558">`IntuneMAMDataProtectionManager` で `protect` API と `unprotect` API を利用し、データを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-558">You can encrypt data by using the `protect` and `unprotect` APIs in `IntuneMAMDataProtectionManager`.</span></span>

<span data-ttu-id="92a51-559">`protect` メソッドに渡す ID は、管理対象ユーザーまたは管理対象外ユーザーのどちらでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="92a51-559">The `protect` method accepts an identity that can be a managed or unmanaged user.</span></span> <span data-ttu-id="92a51-560">ユーザーが管理されている場合、データは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-560">If the user is managed, the data will be encrypted.</span></span> <span data-ttu-id="92a51-561">ユーザーが管理されていない場合は、ヘッダーがデータに追加されて ID はエンコードされますが、データは暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="92a51-561">If the user is unmanaged, a header will be added to the data that's encoding the identity, but the data will not be encrypted.</span></span> <span data-ttu-id="92a51-562">`protectionInfo` メソッドを使用し、データの所有者を取得できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-562">You can use the `protectionInfo` method to retrieve the data’s owner.</span></span>

### <a name="share-extensions"></a><span data-ttu-id="92a51-563">共有拡張機能</span><span class="sxs-lookup"><span data-stu-id="92a51-563">Share extensions</span></span>

<span data-ttu-id="92a51-564">アプリに共有拡張機能が含まれている場合、`IntuneMAMDataProtectionManager` の `protectionInfoForItemProvider` メソッドを使用して共有対象アイテムの所有者を取得できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-564">If the app has a share extension, the owner of the item being shared can be retrieved through the  `protectionInfoForItemProvider` method in `IntuneMAMDataProtectionManager`.</span></span> <span data-ttu-id="92a51-565">共有対象アイテムがファイルの場合は、SDK がファイル所有者の設定を処理します。</span><span class="sxs-lookup"><span data-stu-id="92a51-565">If the shared item is a file, the SDK will handle setting the file owner.</span></span> <span data-ttu-id="92a51-566">共有対象アイテムがデータの場合、そのデータがファイルに保持される場合にファイル所有者を設定することとそのデータを UI に表示する前に `setUIPolicyIdentity` API を呼び出すことがアプリの役目になります。</span><span class="sxs-lookup"><span data-stu-id="92a51-566">If the shared item is data, the app is responsible for setting the file owner if this data is persisted to a file, and for calling the `setUIPolicyIdentity` API before showing this data in the UI.</span></span>

### <a name="turning-on-multi-identity"></a><span data-ttu-id="92a51-567">複数の ID を有効にする</span><span class="sxs-lookup"><span data-stu-id="92a51-567">Turning on multi-identity</span></span>

<span data-ttu-id="92a51-568">既定では、アプリは単一 ID として見なされます。</span><span class="sxs-lookup"><span data-stu-id="92a51-568">By default, apps are considered single identity.</span></span> <span data-ttu-id="92a51-569">SDK は、登録ユーザーにプロセス ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-569">The SDK sets the process identity to the enrolled user.</span></span> <span data-ttu-id="92a51-570">複数 ID のサポートを有効にするには、アプリの Info.plist ファイルの IntuneMAMSettings ディクショナリに名前が `MultiIdentity`、値が YES のブール型設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-570">To enable multi-identity support, add a Boolean setting with the name `MultiIdentity` and a value of YES to the IntuneMAMSettings dictionary in the app's Info.plist file.</span></span>

> [!NOTE]
> <span data-ttu-id="92a51-571">複数 ID を有効にすると、プロセス ID、UI ID、スレッド ID は nil に設定されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-571">When multi-identity is enabled, the process identity, UI identity, and thread identities are set to nil.</span></span> <span data-ttu-id="92a51-572">これらを適切に設定する役目をアプリが担います。</span><span class="sxs-lookup"><span data-stu-id="92a51-572">The app is responsible for setting them appropriately.</span></span>

### <a name="switching-identities"></a><span data-ttu-id="92a51-573">ID の切り替え</span><span class="sxs-lookup"><span data-stu-id="92a51-573">Switching identities</span></span>

* <span data-ttu-id="92a51-574">**アプリで開始する ID の切り替え**:</span><span class="sxs-lookup"><span data-stu-id="92a51-574">**App-initiated identity switch**:</span></span>

    <span data-ttu-id="92a51-575">複数 ID アプリは、起動時には、不明の管理対象外アカウントで実行されているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="92a51-575">At launch, multi-identity apps are considered to be running under an unknown, unmanaged account.</span></span> <span data-ttu-id="92a51-576">条件付き起動 UI は実行せず、アプリに対してポリシーは適用されません。</span><span class="sxs-lookup"><span data-stu-id="92a51-576">The conditional launch UI will not run, and no policies will be enforced on the app.</span></span> <span data-ttu-id="92a51-577">ID を変更する必要があるときは常に、アプリが SDK に通知します。</span><span class="sxs-lookup"><span data-stu-id="92a51-577">The app is responsible for notifying the SDK whenever the identity should be changed.</span></span> <span data-ttu-id="92a51-578">通常、この処理は、アプリが特定のユーザー アカウントのデータを表示するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="92a51-578">Typically, this will happen whenever the app is about to show data for a specific user account.</span></span>

    <span data-ttu-id="92a51-579">たとえば、ユーザーがドキュメント、メールボックス、またはノートブックのタブを開こうとしたときなどです。</span><span class="sxs-lookup"><span data-stu-id="92a51-579">An example is when the user attempts to open a document, a mailbox, or a tab in a notebook.</span></span> <span data-ttu-id="92a51-580">アプリは、ファイル、メールボックス、またはタブが実際に開かれる前に、SDK に通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-580">The app needs to notify the SDK before the file, mailbox, or tab is actually opened.</span></span> <span data-ttu-id="92a51-581">これを行うには、`IntuneMAMPolicyManager` の API `setUIPolicyIdentity` を使用します。</span><span class="sxs-lookup"><span data-stu-id="92a51-581">This is done through the `setUIPolicyIdentity` API in `IntuneMAMPolicyManager`.</span></span> <span data-ttu-id="92a51-582">ユーザーが管理されているかどうかにかかわらず、この API を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-582">This API should be called whether or not the user is managed.</span></span> <span data-ttu-id="92a51-583">ユーザーが管理されている場合、SDK は条件付き起動確認を行います (改造の検出、PIN、認証など)。</span><span class="sxs-lookup"><span data-stu-id="92a51-583">If the user is managed, the SDK will perform the conditional launch checks, like jailbreak detection, PIN, and authentication.</span></span>

    <span data-ttu-id="92a51-584">ID 切り替えの結果は、完了ハンドラーを介して非同期的にアプリに返されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-584">The result of the identity switch is returned to the app asynchronously through a completion handler.</span></span> <span data-ttu-id="92a51-585">アプリは、ドキュメント、メールボックス、タブを開くのを、成功結果コードが返されるまで延期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-585">The app should postpone opening the document, mailbox, or tab until a success result code is returned.</span></span> <span data-ttu-id="92a51-586">ID の切り替えが失敗した場合、アプリはタスクをキャンセルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-586">If the identity switch failed, the app should cancel the task.</span></span>

* <span data-ttu-id="92a51-587">**SDK によって開始される ID の切り替え**:</span><span class="sxs-lookup"><span data-stu-id="92a51-587">**SDK-initiated identity switch**:</span></span>

    <span data-ttu-id="92a51-588">SDK が特定の ID への切り替えをアプリに要求することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-588">Sometimes, the SDK needs to ask the app to switch to a specific identity.</span></span> <span data-ttu-id="92a51-589">複数 ID アプリは、この要求を処理するために `IntuneMAMPolicyDelegate` の `identitySwitchRequired` メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-589">Multi-identity apps must implement the `identitySwitchRequired` method in `IntuneMAMPolicyDelegate` to handle this request.</span></span>

    <span data-ttu-id="92a51-590">このメソッドが呼び出されるとき、指定された ID への切り替え要求をアプリが処理できる場合、アプリは `IntuneMAMAddIdentityResultSuccess` を完了ハンドラーに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-590">When this method is called, if the app can handle the request to switch to the specified identity, it should pass `IntuneMAMAddIdentityResultSuccess` into the completion handler.</span></span> <span data-ttu-id="92a51-591">ID の切り替えを処理できない場合、アプリは完了ハンドラーに `IntuneMAMAddIdentityResultFailed` を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-591">If it can't handle switching the identity, the app should pass `IntuneMAMAddIdentityResultFailed` into the completion handler.</span></span>

    <span data-ttu-id="92a51-592">アプリは、この呼び出しに応答して `setUIPolicyIdentity` を呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="92a51-592">The app does not have to call `setUIPolicyIdentity` in response to this call.</span></span> <span data-ttu-id="92a51-593">アプリが管理されていないユーザー アカウントに切り替える必要がある場合は、`identitySwitchRequired` の呼び出しに空の文字列が渡されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-593">If the SDK needs the app to switch to an unmanaged user account, the empty string will be passed into the `identitySwitchRequired` call.</span></span>

* <span data-ttu-id="92a51-594">**選択的ワイプ**:</span><span class="sxs-lookup"><span data-stu-id="92a51-594">**Selective wipe**:</span></span>

    <span data-ttu-id="92a51-595">アプリが選択的にワイプされる場合、SDK は `IntuneMAMPolicyDelegate` の `wipeDataForAccount` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="92a51-595">When the app is selectively wiped, the SDK will call the `wipeDataForAccount` method in `IntuneMAMPolicyDelegate`.</span></span> <span data-ttu-id="92a51-596">アプリは、指定されたユーザーのアカウントとそれに関連付けられているすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-596">The app is responsible for removing the specified user’s account and any data associated with it.</span></span> <span data-ttu-id="92a51-597">SDK は、ユーザーが所有するすべてのファイルを削除できます。アプリが `wipeDataForAccount` の呼び出しから FALSE を返した場合はすべてのファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="92a51-597">The SDK is capable of removing all files owned by the user and will do so if the app returns FALSE from the `wipeDataForAccount` call.</span></span>

    <span data-ttu-id="92a51-598">このメソッドはバックグラウンド スレッドから呼び出されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-598">Note that this method is called from a background thread.</span></span> <span data-ttu-id="92a51-599">(アプリが FALSE を返す場合のファイルを除き) ユーザーのすべてのデータが削除されるまでアプリは値を返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="92a51-599">The app should not return a value until all data for the user has been removed (with the exception of files if the app returns FALSE).</span></span>

## <a name="test-app-protection-policy-settings-in-xcode"></a><span data-ttu-id="92a51-600">Xcode のアプリ保護ポリシー設定をテストする</span><span class="sxs-lookup"><span data-stu-id="92a51-600">Test app protection policy settings in Xcode</span></span>

<span data-ttu-id="92a51-601">運用環境で Intune 対応アプリを手動でテストする前に、Xcode で Settings.bundle ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-601">Before you manually test your Intune-enlightened app in production, you can use a Settings.bundle file while in Xcode.</span></span> <span data-ttu-id="92a51-602">この方法で、Intune に接続することなく、アプリの保護ポリシーを設定し、テストすることができます。</span><span class="sxs-lookup"><span data-stu-id="92a51-602">This will let you set app protection policies for testing without requiring a connection to Intune.</span></span>

### <a name="enable-policy-testing"></a><span data-ttu-id="92a51-603">ポリシー テストを有効にする</span><span class="sxs-lookup"><span data-stu-id="92a51-603">Enable policy testing</span></span>

<span data-ttu-id="92a51-604">以下の手順を実行し、Xcode でポリシー テストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="92a51-604">Follow the steps below to enable policy testing in Xcode:</span></span>

1. <span data-ttu-id="92a51-605">この操作は、デバッグ ビルドで実行してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-605">Make sure to be in a debug build.</span></span> <span data-ttu-id="92a51-606">プロジェクトの最上位フォルダーを右クリックして Settings.bundle ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-606">Add a Settings.bundle file by right-clicking the top-level folder in your project.</span></span> <span data-ttu-id="92a51-607">メニューから **[追加]** > **[新しいファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="92a51-607">Choose **Add** > **New File** from the menu.</span></span> <span data-ttu-id="92a51-608">**[リソース]** の下で、**[設定バンドル]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="92a51-608">Under **Resources**, choose the **Settings Bundle** template.</span></span>

2.  <span data-ttu-id="92a51-609">次のブロックをデバッグ ビルドの Settings.bundle/**Root.plist** ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="92a51-609">Copy the following block to the Settings.bundle/**Root.plist** file for the debug build:</span></span>
    ```xml
    <key>PreferenceSpecifiers</key>
    <array>
        <dict>
            <key>Type</key>
            <string>PSChildPaneSpecifier</string>
            <key>Title</key>
            <string>MDM Debug Settings</string>
            <key>Key</key>
            <string>MAMDebugSettings</string>
            <key>File</key>
            <string>MAMDebugSettings</string>
        </dict>
    </array>
    ```

3. <span data-ttu-id="92a51-610">アプリの Info.plist の **IntuneMAMSettings** ディクショナリで、"DebugSettingsEnabled" というブール値を追加します。</span><span class="sxs-lookup"><span data-stu-id="92a51-610">In the **IntuneMAMSettings** dictionary in the app's Info.plist, add a boolean called "DebugSettingsEnabled."</span></span> <span data-ttu-id="92a51-611">DebugSettingsEnabled の値を "YES" に設定します。</span><span class="sxs-lookup"><span data-stu-id="92a51-611">Set the value of DebugSettingsEnabled to "YES."</span></span>



### <a name="app-protection-policy-settings"></a><span data-ttu-id="92a51-612">アプリ保護ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="92a51-612">App protection policy settings</span></span>

<span data-ttu-id="92a51-613">以下の表は、MAMDebugSettings.plist を使用してテストできるアプリ保護ポリシー設定についてまとめた一覧です。</span><span class="sxs-lookup"><span data-stu-id="92a51-613">The table below describes the app protection policy settings that you can test using MAMDebugSettings.plist.</span></span> <span data-ttu-id="92a51-614">設定を有効にするには、MAMDebugSettings.plist に追加してください。</span><span class="sxs-lookup"><span data-stu-id="92a51-614">To turn on a setting, add it in MAMDebugSettings.plist.</span></span>


| <span data-ttu-id="92a51-615">ポリシー設定の名前</span><span class="sxs-lookup"><span data-stu-id="92a51-615">Policy setting name</span></span> | <span data-ttu-id="92a51-616">説明</span><span class="sxs-lookup"><span data-stu-id="92a51-616">Description</span></span> | <span data-ttu-id="92a51-617">設定可能な値</span><span class="sxs-lookup"><span data-stu-id="92a51-617">Possible values</span></span> |
| -- | -- | -- |
| <span data-ttu-id="92a51-618">AccessRecheckOfflineTimeout</span><span class="sxs-lookup"><span data-stu-id="92a51-618">AccessRecheckOfflineTimeout</span></span> | <span data-ttu-id="92a51-619">認証が有効な場合に、アプリがオフラインになって Intune がアプリの起動や再開をブロックできる期間 (分)</span><span class="sxs-lookup"><span data-stu-id="92a51-619">The length of time in minutes the app can be offline before Intune blocks the app from launching or resuming if authentication is enabled.</span></span> | <span data-ttu-id="92a51-620">0 よりも大きい任意の整数</span><span class="sxs-lookup"><span data-stu-id="92a51-620">Any integer greater than 0</span></span> |
|   <span data-ttu-id="92a51-621">AccessRecheckOnlineTimeout</span><span class="sxs-lookup"><span data-stu-id="92a51-621">AccessRecheckOnlineTimeout</span></span> | <span data-ttu-id="92a51-622">起動または再開時に、ユーザーが PIN または認証情報の入力を求められるまでに、アプリを起動できる分数 (アクセスに認証または PIN が有効な場合)。</span><span class="sxs-lookup"><span data-stu-id="92a51-622">The length of time in minutes the app can run before the user is prompted for PIN or authentication at launch or resume (if authentication or PIN for access is enabled).</span></span> | <span data-ttu-id="92a51-623">0 よりも大きい任意の整数</span><span class="sxs-lookup"><span data-stu-id="92a51-623">Any integer greater than 0</span></span> |
| <span data-ttu-id="92a51-624">AppSharingFromLevel</span><span class="sxs-lookup"><span data-stu-id="92a51-624">AppSharingFromLevel</span></span> | <span data-ttu-id="92a51-625">このアプリがデータを受け取ることができることを示します。</span><span class="sxs-lookup"><span data-stu-id="92a51-625">Specifies which apps this app can accept data from.</span></span> | <span data-ttu-id="92a51-626">0 =</span><span class="sxs-lookup"><span data-stu-id="92a51-626">0 =</span></span> |

## <a name="ios-best-practices"></a><span data-ttu-id="92a51-627">iOS ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="92a51-627">iOS best practices</span></span>

<span data-ttu-id="92a51-628">iOS 向けの開発に推奨されるベスト プラクティスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="92a51-628">Here are recommended best practices for developing for iOS:</span></span>

* <span data-ttu-id="92a51-629">iOS ファイル システムでは大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-629">The iOS file system is case-sensitive.</span></span> <span data-ttu-id="92a51-630">`libIntuneMAM.a` や `IntuneMAMResources.bundle` のようなファイル名で大文字/小文字の使い方が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="92a51-630">Ensure that the case is correct for file names like `libIntuneMAM.a` and `IntuneMAMResources.bundle`.</span></span>

* <span data-ttu-id="92a51-631">Xcode で `libIntuneMAM.a` が見つからない場合は、リンカー検索パスにこのライブラリへのパスを追加して問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-631">If Xcode has trouble finding `libIntuneMAM.a`, you can fix the problem by adding the path to this library into the linker search paths.</span></span>

## <a name="faqs"></a><span data-ttu-id="92a51-632">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="92a51-632">FAQs</span></span>


<span data-ttu-id="92a51-633">**すべての API は、ネイティブ Swift または Objective-C と Swift の相互運用で指定可能ですか?**</span><span class="sxs-lookup"><span data-stu-id="92a51-633">**Are all of the APIs addressable through native Swift or the Objective-C and Swift interoperability?**</span></span>

<span data-ttu-id="92a51-634">Intune App SDK の API は、Objective-C でのみ使用でき、**ネイティブ** Swift はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="92a51-634">The Intune App SDK APIs are in Objective-C only and do not support **native** Swift.</span></span> <span data-ttu-id="92a51-635">Objective-C との相互運用性が必要です。</span><span class="sxs-lookup"><span data-stu-id="92a51-635">Swift interoperability with Objective-C is required.</span></span>


<span data-ttu-id="92a51-636">**アプリケーションのすべてのユーザーを APP-WE サービスに登録する必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="92a51-636">**Do all users of my application need to be registered with the APP-WE service?**</span></span>

<span data-ttu-id="92a51-637">いいえ。</span><span class="sxs-lookup"><span data-stu-id="92a51-637">No.</span></span> <span data-ttu-id="92a51-638">実際には、Intune アプリ SDK に登録する必要があるのは職場または学校アカウントのみです。</span><span class="sxs-lookup"><span data-stu-id="92a51-638">In fact, only work or school accounts should be registered with the Intune App SDK.</span></span> <span data-ttu-id="92a51-639">アプリでは、職場または学校のコンテキストでアカウントが使用されるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-639">Apps are responsible for determining if an account is used in a work or school context.</span></span>   

<span data-ttu-id="92a51-640">**アプリケーションに既にサインインしているユーザーはどうなりますか?登録する必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="92a51-640">**What about users that have already signed in to the application? Do they need to be enrolled?**</span></span>

<span data-ttu-id="92a51-641">ユーザーが正常に認証されると、アプリによりユーザーが登録されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-641">The application is responsible for enrolling users after they have been successfully authenticated.</span></span> <span data-ttu-id="92a51-642">アプリケーションが MDM のない MAM 機能を使用する前に存在していた可能性がある既存のアカウントの登録もアプリケーションが行います。</span><span class="sxs-lookup"><span data-stu-id="92a51-642">The application is also responsible for enrolling any existing accounts that might have been present before the application had MDM-less MAM functionality.</span></span>   

<span data-ttu-id="92a51-643">これを行うには、アプリケーションは `registeredAccounts:` メソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-643">To do this, the application should make use of the `registeredAccounts:` method.</span></span> <span data-ttu-id="92a51-644">このメソッドは、Intune MAM サービスに登録されているすべてのアカウントを含む NSDictionary を返します。</span><span class="sxs-lookup"><span data-stu-id="92a51-644">This method returns an NSDictionary that has all of the accounts registered into the Intune MAM service.</span></span> <span data-ttu-id="92a51-645">アプリケーションの既存のアカウントがこの一覧に存在しない場合、アプリケーションは `registerAndEnrollAccount:` を使用してそれらのアカウントを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-645">If any existing accounts in the application are not in the list, the application should register and enroll those accounts via `registerAndEnrollAccount:`.</span></span>

<span data-ttu-id="92a51-646">**SDK はどのような頻度で登録を再試行しますか。**</span><span class="sxs-lookup"><span data-stu-id="92a51-646">**How often does the SDK retry enrollments?**</span></span>

<span data-ttu-id="92a51-647">SDK は、以前に失敗したすべての登録を 24 時間ごとに自動的に再試行します。</span><span class="sxs-lookup"><span data-stu-id="92a51-647">The SDK will automatically retry all previously failed enrollments on a 24-hour interval.</span></span> <span data-ttu-id="92a51-648">SDK はこれにより、ユーザーがアプリケーションにサインインした後でユーザーの組織が MAM を有効にしてあり、ユーザーが正常に登録してポリシーを受け取れるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="92a51-648">The SDK does this to ensure that if a user’s organization enabled MAM after the user signed in to the application, the user will successfully enroll and receive policies.</span></span>

<span data-ttu-id="92a51-649">ユーザーがアプリケーションを正常に登録したことを検出した場合、SDK は再試行を停止します。</span><span class="sxs-lookup"><span data-stu-id="92a51-649">The SDK will stop retrying when it detects that a user has successfully enrolled the application.</span></span> <span data-ttu-id="92a51-650">これは、アプリケーションを登録できるのは一度に 1 人のユーザーだけであるためです。</span><span class="sxs-lookup"><span data-stu-id="92a51-650">This is because only one user can enroll an application at a particular time.</span></span> <span data-ttu-id="92a51-651">ユーザーが登録解除された場合、同じ 24 時間間隔で再試行が開始されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-651">If the user is unenrolled, the retries will begin again on the same 24-hour interval.</span></span>

<span data-ttu-id="92a51-652">**ユーザーを登録解除する必要があるのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="92a51-652">**Why does the user need to be deregistered?**</span></span>

<span data-ttu-id="92a51-653">SDK は、次の操作をバックグラウンドで定期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="92a51-653">The SDK will take these actions in the background periodically:</span></span>

 - <span data-ttu-id="92a51-654">アプリケーションがまだ登録されていない場合、SDK は 24 時間ごとにリストにあるすべてのアカウントの登録を試みます。</span><span class="sxs-lookup"><span data-stu-id="92a51-654">If the application is not yet enrolled, it will try to enroll all registered accounts every 24 hours.</span></span>
 - <span data-ttu-id="92a51-655">アプリケーションが登録されている場合、SDK は 8 時間ごとにアプリ保護ポリシーの更新を確認します。</span><span class="sxs-lookup"><span data-stu-id="92a51-655">If the application is enrolled, the SDK will check for app protection policy updates every 8 hours.</span></span>

<span data-ttu-id="92a51-656">ユーザーを登録解除すると、ユーザーがアプリケーションを使用しなくなり、そのユーザー アカウントに対する定期的イベントを SDK は停止できることが SDK に通知されます。</span><span class="sxs-lookup"><span data-stu-id="92a51-656">Deregistering a user notifies the SDK that the user will no longer use the application, and the SDK can stop any of the periodic events for that user account.</span></span> <span data-ttu-id="92a51-657">また、必要に応じて、アプリの登録解除と選択的ワイプもトリガーします。</span><span class="sxs-lookup"><span data-stu-id="92a51-657">It also triggers an app unenroll and selective wipe if necessary.</span></span>

<span data-ttu-id="92a51-658">**登録解除メソッドでは doWipe フラグを true に設定する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="92a51-658">**Should I set the doWipe flag to true in the deregister method?**</span></span>

<span data-ttu-id="92a51-659">このメソッドは、ユーザーがアプリケーションからサインアウトする前に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-659">This method should be called before the user is signed out of the application.</span></span>  <span data-ttu-id="92a51-660">サインアウトの一環としてユーザーのデータがアプリケーションから削除される場合は、`doWipe` を false に設定できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-660">If the user’s data is deleted from the application as part of the sign-out, `doWipe` can be set to false.</span></span> <span data-ttu-id="92a51-661">ただし、アプリケーションがユーザーのデータを削除しない場合は、SDK がデータを削除できるように、`doWipe` を true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92a51-661">But if the application does not remove the user’s data, `doWipe` should be set to true so that the SDK can delete the data.</span></span>

<span data-ttu-id="92a51-662">**アプリケーションを登録解除できる他の方法はありますか。**</span><span class="sxs-lookup"><span data-stu-id="92a51-662">**Are there any other ways that an application can be un-enrolled?**</span></span>

<span data-ttu-id="92a51-663">はい。IT 管理者は選択的ワイプ コマンドをアプリケーションに送信できます。</span><span class="sxs-lookup"><span data-stu-id="92a51-663">Yes, the IT admin can send a selective wipe command to the application.</span></span> <span data-ttu-id="92a51-664">このコマンドを送信すると、ユーザーは登録を解除されて、ユーザーのデータはワイプされます。</span><span class="sxs-lookup"><span data-stu-id="92a51-664">This will deregister and unenroll the user, and it will wipe the user’s data.</span></span> <span data-ttu-id="92a51-665">SDK は自動的にこのシナリオを処理し、登録解除デリゲート メソッドで通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="92a51-665">The SDK automatically handles this scenario and sends a notification via the unenroll delegate method.</span></span>



## <a name="submit-your-app-to-the-app-store"></a><span data-ttu-id="92a51-666">App Store にアプリを送信する</span><span class="sxs-lookup"><span data-stu-id="92a51-666">Submit your app to the App Store</span></span>

<span data-ttu-id="92a51-667">Intune App SDK の静的ライブラリおよびフレームワークのビルドはどちらもユニバーサル バイナリです。</span><span class="sxs-lookup"><span data-stu-id="92a51-667">Both the static library and framework builds of the Intune App SDK are universal binaries.</span></span> <span data-ttu-id="92a51-668">これはデバイスとシミュレーターのすべてのアーキテクチャ用のコードが含まれていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="92a51-668">This means they have code for all device and simulator architectures.</span></span> <span data-ttu-id="92a51-669">Apple は、App Store に送信されたアプリにシミュレーターのコードが含まれていると、そのアプリを拒否します。</span><span class="sxs-lookup"><span data-stu-id="92a51-669">Apple will reject apps submitted to the App Store if they have simulator code.</span></span> <span data-ttu-id="92a51-670">デバイス専用ビルドのスタティック ライブラリ用にコンパイルするとき、リンカーは自動的にシミュレーター コードを削除します。</span><span class="sxs-lookup"><span data-stu-id="92a51-670">When compiling against the static library for device-only builds, the linker will automatically strip out the simulator code.</span></span> <span data-ttu-id="92a51-671">以下の手順に従って、アプリ ストアにアプリをアップロードする前にすべてのシミュレーター コードが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92a51-671">Follow the steps below to ensure all simulator code is removed before you upload your app to the App Store.</span></span>

1. <span data-ttu-id="92a51-672">`IntuneMAM.framework` がデスクトップにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92a51-672">Make sure `IntuneMAM.framework` is on your desktop.</span></span>

2. <span data-ttu-id="92a51-673">これらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92a51-673">Run these commands:</span></span>

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    <span data-ttu-id="92a51-674">最初のコマンドは、フレームワークの DYLIB ファイルからシミュレーター アーキテクチャを削除します。</span><span class="sxs-lookup"><span data-stu-id="92a51-674">The first command strips the simulator architectures from the framework's DYLIB file.</span></span> <span data-ttu-id="92a51-675">2 番目のコマンドは、デバイス専用の DYLIB ファイルをフレームワークのディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="92a51-675">The second command copies the device-only DYLIB file back into the framework directory.</span></span>
