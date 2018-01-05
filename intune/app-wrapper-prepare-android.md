---
title: "Intune アプリ ラッピング ツールで Android アプリをラップする"
description: "この記事の情報を使用して、アプリ自体のコードを変更することなく、Android アプリをラップする方法について説明します。 モバイル アプリ管理ポリシーを適用できるように、アプリを準備します。"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 07/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2a349595fc5711b8754d635d3cc1890e833b2701
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a><span data-ttu-id="d5e95-104">Intune アプリ ラッピング ツールでアプリ保護ポリシーを利用するために Android アプリを準備する</span><span class="sxs-lookup"><span data-stu-id="d5e95-104">Prepare Android apps for app protection policies with the Intune App Wrapping Tool</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="d5e95-105">Android 用 Microsoft Intune アプリ ラッピング ツールを使用して社内 Android アプリの動作を変更すれば、アプリ自体のコードを変更しなくてもアプリの機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-105">Use the Microsoft Intune App Wrapping Tool for Android to change the behavior of your in-house Android apps by restricting features of the app without changing the code of the app itself.</span></span>

<span data-ttu-id="d5e95-106">このツールは、PowerShell で実行される Windows のコマンドライン アプリケーションであり、Android アプリのラッパーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-106">The tool is a Windows command-line application that runs in PowerShell and creates a wrapper around your Android app.</span></span> <span data-ttu-id="d5e95-107">アプリがラッピングされた後は、Intune で[モバイル アプリケーション管理ポリシー](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)を構成することによって、アプリの機能を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-107">After the app is wrapped, you can change the app’s functionality by configuring [mobile application management policies](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) in Intune.</span></span>


<span data-ttu-id="d5e95-108">このツールを実行する前に、「[アプリ ラッピング ツールを実行するうえでのセキュリティ上の考慮事項](#security-considerations-for-running-the-app-wrapping-tool)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5e95-108">Before running the tool, review [Security considerations for running the App Wrapping Tool](#security-considerations-for-running-the-app-wrapping-tool).</span></span> <span data-ttu-id="d5e95-109">このツールをダウンロードするには、GitHub の「[Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android)」 (Android 用 Microsoft Intune アプリ ラッピング ツール) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="d5e95-109">To download the tool, go to the [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) on GitHub.</span></span>



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a><span data-ttu-id="d5e95-110">ラッピング ツールを使用するための前提条件を満たす</span><span class="sxs-lookup"><span data-stu-id="d5e95-110">Fulfill the prerequisites for using the App Wrapping Tool</span></span>

-   <span data-ttu-id="d5e95-111">Windows 7 以降を実行している Windows コンピューターでアプリ ラッピング ツールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-111">You must run the App Wrapping Tool on a Windows computer running Windows 7 or later.</span></span>

-   <span data-ttu-id="d5e95-112">入力アプリは、有効な Android アプリケーション パッケージであり、かつそのファイル拡張子が .apk であるだけでなく、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-112">Your input app must be a valid Android application package with the file extension .apk and:</span></span>

    -   <span data-ttu-id="d5e95-113">暗号化できない。</span><span class="sxs-lookup"><span data-stu-id="d5e95-113">It cannot be encrypted.</span></span>
    -   <span data-ttu-id="d5e95-114">Intune アプリ ラッピング ツールでまだラップされていない。</span><span class="sxs-lookup"><span data-stu-id="d5e95-114">It must not have previously been wrapped by the Intune App Wrapping Tool.</span></span>
    -   <span data-ttu-id="d5e95-115">Android 4.0 以降を対象に記述されている。</span><span class="sxs-lookup"><span data-stu-id="d5e95-115">It must be written for Android 4.0 or later.</span></span>

-   <span data-ttu-id="d5e95-116">このアプリは、自社で開発されているか、自社向けに開発されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-116">The app must be developed by or for your company.</span></span> <span data-ttu-id="d5e95-117">Google Play ストアからダウンロードしたアプリでこのツールを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5e95-117">You cannot use this tool on apps downloaded from the Google Play Store.</span></span>

-   <span data-ttu-id="d5e95-118">アプリ ラッピング ツールを実行するには、最新バージョンの [Java ランタイム環境](http://java.com/download/)をインストールし、Java の path 変数が Windows 環境変数で C:\ProgramData\Oracle\Java\javapath に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-118">To run the App Wrapping Tool, you must install the latest version of the [Java Runtime Environment](http://java.com/download/) and then ensure that the Java path variable has been set to C:\ProgramData\Oracle\Java\javapath in your Windows environment variables.</span></span> <span data-ttu-id="d5e95-119">詳細については、[Java のドキュメント](http://java.com/download/help/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5e95-119">For more help, see the [Java documentation](http://java.com/download/help/).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d5e95-120">場合によっては、32 ビット バージョンの Java を使用すると、メモリに関連した問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-120">In some cases, the 32-bit version of Java may result in memory issues.</span></span> <span data-ttu-id="d5e95-121">64 ビット バージョンをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d5e95-121">It's a good idea to install the 64-bit version.</span></span>

- <span data-ttu-id="d5e95-122">Android では、すべてのアプリ パッケージ (.apk) が署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-122">Android requires all app packages (.apk) to be signed.</span></span> <span data-ttu-id="d5e95-123">既存の証明書の**再利用**と署名証明書の全体的なガイダンスについては、「[署名証明書とラッピング アプリの再利用](https://docs.microsoft.com/en-us/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5e95-123">For **reusing** existing certificates and overall signing certificate guidance, see [Reusing signing certificates and wrapping apps](https://docs.microsoft.com/en-us/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps).</span></span> <span data-ttu-id="d5e95-124">ラッピングされた出力アプリへの署名に必要な**新しい**資格情報を生成するには、Java の実行可能ファイル keytool.exe を使います。</span><span class="sxs-lookup"><span data-stu-id="d5e95-124">The Java executable keytool.exe is used to generate **new** credentials needed to sign the wrapped output app.</span></span> <span data-ttu-id="d5e95-125">設定するパスワードはすべて安全である必要がありますが、後でアプリ ラッピング ツールを実行するときに必要になるので記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-125">Any passwords that are set must be secure, but make a note of them because they're needed to run the App Wrapping Tool.</span></span>

## <a name="install-the-app-wrapping-tool"></a><span data-ttu-id="d5e95-126">アプリ ラッピング ツールをインストールする</span><span class="sxs-lookup"><span data-stu-id="d5e95-126">Install the App Wrapping Tool</span></span>

1.  <span data-ttu-id="d5e95-127">[GitHub リポジトリ](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android)から Android 用 Intune アプリ ラッピング ツールのインストール ファイル InstallAWT.exe を Windows コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d5e95-127">From the [GitHub repository](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), download the installation file InstallAWT.exe for the Intune App Wrapping Tool for Android to a Windows computer.</span></span> <span data-ttu-id="d5e95-128">インストール ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-128">Open the installation file.</span></span>

2.  <span data-ttu-id="d5e95-129">ライセンス条項に同意し、インストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-129">Accept the license agreement, then finish the installation.</span></span>

<span data-ttu-id="d5e95-130">このツールをインストールしたフォルダーをメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-130">Note the folder to which you installed the tool.</span></span> <span data-ttu-id="d5e95-131">既定の場所は、C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool です。</span><span class="sxs-lookup"><span data-stu-id="d5e95-131">The default location is: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.</span></span>

## <a name="run-the-app-wrapping-tool"></a><span data-ttu-id="d5e95-132">アプリ ラッピング ツールを実行する</span><span class="sxs-lookup"><span data-stu-id="d5e95-132">Run the App Wrapping Tool</span></span>

1. <span data-ttu-id="d5e95-133">アプリ ラッピング ツールをインストールした Windows コンピューターで PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-133">On the Windows computer where you installed the App Wrapping Tool, open a PowerShell window.</span></span>

2. <span data-ttu-id="d5e95-134">ツールをインストールしたフォルダーから、アプリ ラッピング ツールの PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d5e95-134">From the folder where you installed the tool, import the App Wrapping Tool PowerShell module:</span></span>

   ```
   Import-Module .\IntuneAppWrappingTool.psm1
   ```

3. <span data-ttu-id="d5e95-135">**invoke-AppWrappingTool** コマンドを使用してツールを実行します。コマンドの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5e95-135">Run the tool by using the **invoke-AppWrappingTool** command, which has the following usage syntax:</span></span>
   ```
   Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
   -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
   ```

   <span data-ttu-id="d5e95-136">**invoke-AppWrappingTool** コマンドのプロパティの詳細を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-136">The following table details the properties of the **invoke-AppWrappingTool** command:</span></span>

|<span data-ttu-id="d5e95-137">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d5e95-137">Property</span></span>|<span data-ttu-id="d5e95-138">説明</span><span class="sxs-lookup"><span data-stu-id="d5e95-138">Information</span></span>|<span data-ttu-id="d5e95-139">例</span><span class="sxs-lookup"><span data-stu-id="d5e95-139">Example</span></span>|
|-------------|--------------------|---------|
|<span data-ttu-id="d5e95-140">**-InputPath**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="d5e95-140">**-InputPath**&lt;String&gt;</span></span>|<span data-ttu-id="d5e95-141">ソースの Android アプリ (.apk) のパス。</span><span class="sxs-lookup"><span data-stu-id="d5e95-141">Path of the source Android app (.apk).</span></span>| |
|<span data-ttu-id="d5e95-142">**-OutputPath**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="d5e95-142">**-OutputPath**&lt;String&gt;</span></span>|<span data-ttu-id="d5e95-143">出力先の Android のアプリへのパス。</span><span class="sxs-lookup"><span data-stu-id="d5e95-143">Path to the output Android app.</span></span> <span data-ttu-id="d5e95-144">InputPath と同じディレクトリ パスを指定した場合、パッケージ化は失敗します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-144">If this is the same directory path as InputPath, the packaging will fail.</span></span>| |
|<span data-ttu-id="d5e95-145">**-KeyStorePath**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="d5e95-145">**-KeyStorePath**&lt;String&gt;</span></span>|<span data-ttu-id="d5e95-146">署名用の公開/秘密キーのペアを含むキーストア ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="d5e95-146">Path to the keystore file that has the public/private key pair for signing.</span></span>|<span data-ttu-id="d5e95-147">既定では、キーストア ファイルは "C:\Program Files (x86)\Java\jreX.X.X_XX\bin" に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-147">By default, keystore files are stored in "C:\Program Files (x86)\Java\jreX.X.X_XX\bin."</span></span> |
|<span data-ttu-id="d5e95-148">**-KeyStorePassword**&lt;SecureString&gt;</span><span class="sxs-lookup"><span data-stu-id="d5e95-148">**-KeyStorePassword**&lt;SecureString&gt;</span></span>|<span data-ttu-id="d5e95-149">キーストアの暗号化を解除するために使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="d5e95-149">Password used to decrypt the keystore.</span></span> <span data-ttu-id="d5e95-150">Android では、すべてのアプリケーション パッケージ (.apk) に署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-150">Android requires all application packages (.apk) to be signed.</span></span> <span data-ttu-id="d5e95-151">Java キーツールを使用して KeyStorePassword を生成できます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-151">Use Java keytool to generate the KeyStorePassword.</span></span> <span data-ttu-id="d5e95-152">詳細については、こちらの Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5e95-152">Read more about Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) here.</span></span>| |
|<span data-ttu-id="d5e95-153">**-KeyAlias**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="d5e95-153">**-KeyAlias**&lt;String&gt;</span></span>|<span data-ttu-id="d5e95-154">署名に使用するキーの名前。</span><span class="sxs-lookup"><span data-stu-id="d5e95-154">Name of the key to be used for signing.</span></span>| |
|<span data-ttu-id="d5e95-155">**-KeyPassword**&lt;SecureString&gt;</span><span class="sxs-lookup"><span data-stu-id="d5e95-155">**-KeyPassword**&lt;SecureString&gt;</span></span>|<span data-ttu-id="d5e95-156">署名に使用する秘密キーの暗号化を解除するために使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="d5e95-156">Password used to decrypt the private key that will be used for signing.</span></span>| |
|<span data-ttu-id="d5e95-157">**-SigAlg**&lt;SecureString&gt;</span><span class="sxs-lookup"><span data-stu-id="d5e95-157">**-SigAlg**&lt;SecureString&gt;</span></span>| <span data-ttu-id="d5e95-158">(省略可能) 署名に使用する署名アルゴリズムの名前。</span><span class="sxs-lookup"><span data-stu-id="d5e95-158">(Optional) The name of the signature algorithm to be used for signing.</span></span> <span data-ttu-id="d5e95-159">アルゴリズムは秘密キーと互換性を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-159">The algorithm must be compatible with the private key.</span></span>|<span data-ttu-id="d5e95-160">例: SHA256withRSA、SHA1withRSA</span><span class="sxs-lookup"><span data-stu-id="d5e95-160">Examples: SHA256withRSA, SHA1withRSA</span></span>|
| <span data-ttu-id="d5e95-161">**&lt;CommonParameters&gt;**</span><span class="sxs-lookup"><span data-stu-id="d5e95-161">**&lt;CommonParameters&gt;**</span></span> | <span data-ttu-id="d5e95-162">(省略可能) コマンドは、verbose、debug などの一般的な PowerShell パラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d5e95-162">(Optional) The command supports common PowerShell parameters like verbose and debug.</span></span> |


- <span data-ttu-id="d5e95-163">共通パラメーターの一覧については、 [Microsoft スクリプト センター](https://technet.microsoft.com/library/hh847884.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5e95-163">For a list of common parameters, see the [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).</span></span>

- <span data-ttu-id="d5e95-164">ツールの詳細な使用方法を確認するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-164">To see detailed usage information for the tool, enter the command:</span></span>

    ```
    Help Invoke-AppWrappingTool
    ```

<span data-ttu-id="d5e95-165">**例:**</span><span class="sxs-lookup"><span data-stu-id="d5e95-165">**Example:**</span></span>

<span data-ttu-id="d5e95-166">PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d5e95-166">Import the PowerShell module.</span></span>
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
<span data-ttu-id="d5e95-167">ネイティブ アプリ HelloWorld.apk に対してアプリ ラッピング ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-167">Run the App Wrapping Tool on the native app HelloWorld.apk.</span></span>
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

<span data-ttu-id="d5e95-168">**KeyStorePassword** と **KeyPassword** の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-168">You will then be prompted for **KeyStorePassword** and **KeyPassword**.</span></span> <span data-ttu-id="d5e95-169">キーストア ファイルの作成に使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-169">Enter the credentials you used to create the key store file.</span></span>

<span data-ttu-id="d5e95-170">ラップされたアプリとログ ファイルが生成されて、指定した出力パスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-170">The wrapped app and a log file are generated and saved in the output path you specified.</span></span>

## <a name="reusing-signing-certificates-and-wrapping-apps"></a><span data-ttu-id="d5e95-171">署名証明書とラッピング アプリの再利用</span><span class="sxs-lookup"><span data-stu-id="d5e95-171">Reusing signing certificates and wrapping apps</span></span>
<span data-ttu-id="d5e95-172">Android では、Android デバイスにインストールするために、すべてのアプリを有効な証明書で署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-172">Android requires that all apps must be signed by a valid certificate in order to be installed on Android devices.</span></span>

<span data-ttu-id="d5e95-173">ラップされたアプリは、ラッピング処理の一部、または既存の署名ツール (ラッピングが破棄される前のアプリの署名情報) を使用したラッピングの*後*のいずれかに署名できます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-173">Wrapped apps can be signed either as part of the wrapping process or *after* wrapping using your existing signing tools (any signing information in the app before wrapping is discarded).</span></span>
 
<span data-ttu-id="d5e95-174">可能であれば、ビルド処理中に既に使用されている署名情報を、ラッピング中に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-174">If possible, the signing information that was already used during the build process should be used during wrapping.</span></span> <span data-ttu-id="d5e95-175">特定の組織では、キーストア情報 (例: アプリのビルド チーム) を所有するユーザーと共同作業する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-175">In certain organizations, this may require working with whoever owns the keystore information (ie. the app build team).</span></span> 

<span data-ttu-id="d5e95-176">以前の署名証明書を使用できない、またはアプリを以前に展開していない場合は、[Android 開発者ガイド](https://developer.android.com/studio/publish/app-signing.html#signing-manually)の手順に従って、新しい署名証明書を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-176">If the previous signing certificate cannot be used, or the app has not been deployed before, you may create a new signing certificate by following the instructions in the [Android Developer Guide](https://developer.android.com/studio/publish/app-signing.html#signing-manually).</span></span>

<span data-ttu-id="d5e95-177">アプリが別の署名証明書を使って以前に展開されている場合、アップグレード後にアプリを Intune にアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d5e95-177">If the app has been deployed previously with a different signing certificate, the app can't be uploaded to Intune after upgrade.</span></span> <span data-ttu-id="d5e95-178">アプリをビルドした証明書ではなく、別の証明書を使ってアプリが署名されている場合、アプリのアップグレード シナリオは中断されます。</span><span class="sxs-lookup"><span data-stu-id="d5e95-178">App upgrade scenarios will be broken if your app is signed with a different certificate than the one the app is built with.</span></span> <span data-ttu-id="d5e95-179">このように、新しい署名証明書は、アプリのアップグレード用に保持される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5e95-179">As such, any new signing certificates should be maintained for app upgrades.</span></span> 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a><span data-ttu-id="d5e95-180">アプリ ラッピング ツールを実行するうえでのセキュリティ上の考慮事項</span><span class="sxs-lookup"><span data-stu-id="d5e95-180">Security considerations for running the App Wrapping Tool</span></span>
<span data-ttu-id="d5e95-181">スプーフィング、情報漏えい、および権限の昇格攻撃の可能性を抑制するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d5e95-181">To prevent potential spoofing, information disclosure, and elevation of privilege attacks:</span></span>

-   <span data-ttu-id="d5e95-182">入力基幹業務 (LOB) アプリケーション、出力アプリケーション、Java KeyStore が、アプリ ラッピング ツールを実行している Windows コンピューター上に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-182">Ensure that the input line-of-business (LOB) application, output application, and Java KeyStore are on the same Windows computer where the App Wrapping Tool is running.</span></span>

-   <span data-ttu-id="d5e95-183">このツールを実行しているコンピューター上の Intune に出力アプリケーションをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d5e95-183">Import the output application to Intune on the same machine where the tool is running.</span></span> <span data-ttu-id="d5e95-184">Java キーツールについて詳しくは、[キーツール](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d5e95-184">See [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) for more about about Java keytool.</span></span>

-   <span data-ttu-id="d5e95-185">出力アプリケーションとツールが汎用名前付け規則 (UNC) パスにあり、ツールと入力ファイルを同じコンピューター上で実行していない場合、[インターネット プロトコル セキュリティ (IPsec)](http://wikipedia.org/wiki/IPsec) または[サーバー メッセージ ブロック (SMB) 署名](https://support.microsoft.com/kb/887429)を使用して環境をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-185">If the output application and the tool are on a Universal Naming Convention (UNC) path and you are not running the tool and input files on the same computer, set up the environment to be secure by using [Internet Protocol Security (IPsec)](http://wikipedia.org/wiki/IPsec) or [Server Message Block (SMB) signing](https://support.microsoft.com/kb/887429).</span></span>

-   <span data-ttu-id="d5e95-186">アプリケーションが信頼されたソースからのものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-186">Ensure that the application is coming from a trusted source.</span></span>

-   <span data-ttu-id="d5e95-187">ラップされたアプリが格納されている出力ディレクトリをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-187">Secure the output directory that has the wrapped app.</span></span> <span data-ttu-id="d5e95-188">出力にユーザー レベルのディレクトリを使用することを検討します。</span><span class="sxs-lookup"><span data-stu-id="d5e95-188">Consider using a user-level directory for the output.</span></span>

### <a name="see-also"></a><span data-ttu-id="d5e95-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5e95-189">See also</span></span>
- [<span data-ttu-id="d5e95-190">Microsoft Intune によるモバイル アプリケーション管理のためにアプリを準備する方法を決める</span><span class="sxs-lookup"><span data-stu-id="d5e95-190">Decide how to prepare apps for mobile application management with Microsoft Intune</span></span>](apps-prepare-mobile-application-management.md)

- [<span data-ttu-id="d5e95-191">SDK を使用してモバイル アプリケーション管理に対応する</span><span class="sxs-lookup"><span data-stu-id="d5e95-191">Use the SDK to enable apps for mobile application management</span></span>](/intune/classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
