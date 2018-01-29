---
title: "Windows 8.1 の Intune デバイス制限設定"
titleSuffix: Azure portal
description: "Windows 8.1 デバイスでデバイスの設定と機能を制御するために使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fe5785e9-8d35-4ad7-95e8-d50f8d87154a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 90bf12356ffccde5303c64a0675f046459d7dc82
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="windows-81-and-later-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="49a0c-103">Microsoft Intune での Windows 8.1 以降のデバイスの制限設定</span><span class="sxs-lookup"><span data-stu-id="49a0c-103">Windows 8.1 and later device restriction settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="general"></a><span data-ttu-id="49a0c-104">全般</span><span class="sxs-lookup"><span data-stu-id="49a0c-104">General</span></span>

-   <span data-ttu-id="49a0c-105">**[診断データの送信]** - デバイスが Microsoft に診断情報を送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-105">**Diagnostic data submission** - Enables the device to submit diagnostic information to Microsoft.</span></span>
-   <span data-ttu-id="49a0c-106">**[ファイアウォール]** - Windows ファイアウォールを有効にすることを要求します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-106">**Firewall** - Requires that the Windows Firewall is turned on.</span></span>
-   <span data-ttu-id="49a0c-107">**[ユーザー アカウント制御]** - デバイス上のユーザー アカウント制御 (UAC) の使用を必須とします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-107">**User Account Control** - Requires the use of User Account Control (UAC) on devices.</span></span>

## <a name="password"></a><span data-ttu-id="49a0c-108">パスワード</span><span class="sxs-lookup"><span data-stu-id="49a0c-108">Password</span></span>
-   <span data-ttu-id="49a0c-109">**[必要なパスワードの種類]** - エンド ユーザーがデバイスにアクセスする際にパスワードの入力を要求します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-109">**Required password type** - Require the end user to enter a password to access the device.</span></span>
-   <span data-ttu-id="49a0c-110">**[パスワードの最小文字数]** - パスワードに必要な最小の長さ (文字数) を構成します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-110">**Minimum password length** - Configures the minimum required length (in characters) for the password.</span></span>
-   <span data-ttu-id="49a0c-111">**[デバイスがワイプされるまでのサインイン失敗回数]** - サインインの試みがこの回数だけ失敗した場合は、デバイスがワイプされます。</span><span class="sxs-lookup"><span data-stu-id="49a0c-111">**Number of sign-in failures before wiping device** - Wipes the device if the sign-in attempts fail this number of times.</span></span>
-   <span data-ttu-id="49a0c-112">**[画面がロックされるまでの非アクティブな最長時間 (分)]** - デバイスのアイドル状態が許容される時間 (分) を指定します。この時間を超えると、ロックを解除するためにパスワードが必要となります。</span><span class="sxs-lookup"><span data-stu-id="49a0c-112">**Maximum minutes of inactivity until screen locks** - Specifies the number of minutes a device must be idle before a password is required to unlock it.</span></span>
-   <span data-ttu-id="49a0c-113">**[パスワードの有効期限 (日数)]** - デバイスのパスワードの変更が必要になるまでの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-113">**Password expiration (days)** - Specifies the number of days before the device password must be changed.</span></span>
-   <span data-ttu-id="49a0c-114">**[Prevent reuse of previous passwords (前のパスワードを再利用できないようにする)]** - 過去に使用したパスワードをユーザーが構成できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-114">**Prevent reuse of previous passwords** - Specifies whether the user can configure previously used passwords.</span></span>
-   <span data-ttu-id="49a0c-115">**[ピクチャ パスワードと PIN]** - ピクチャ パスワードと PIN を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-115">**Picture password and PIN** - Enables the use of a picture password and PIN.</span></span> <span data-ttu-id="49a0c-116">ピクチャ パスワードが許可されている場合、ユーザーは画像に対するジェスチャーでサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="49a0c-116">A picture password lets the user sign in with gestures on a picture.</span></span> <span data-ttu-id="49a0c-117">PIN が許可されている場合、ユーザーは 4 桁のコードを使用してすばやくサインインできます。</span><span class="sxs-lookup"><span data-stu-id="49a0c-117">A PIN lets users quickly sign in with a four-digit code.</span></span>
-   <span data-ttu-id="49a0c-118">**[暗号化]** - デバイス上のファイルを暗号化することを要求します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-118">**Encryption** - Requires that files on the device are encrypted.</span></span><br><span data-ttu-id="49a0c-119">Windows 8.1 が実行されているデバイスで暗号化を適用するには、 [Windows の 2014 年 12 月付け MDM クライアント更新プログラム](https://support.microsoft.com/kb/3013816) を各デバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49a0c-119">To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](https://support.microsoft.com/kb/3013816) on each device.</span></span>
<span data-ttu-id="49a0c-120">Windows 8.1 デバイスに対してこの設定を有効にすると、デバイスのすべてのユーザーに Microsoft アカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="49a0c-120">If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.</span></span>
<span data-ttu-id="49a0c-121">暗号化を機能させるには、デバイスが Microsoft [InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97) ハードウェア認定要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="49a0c-121">For encryption to work, the device must meet the [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97) hardware certification requirements.</span></span>
<span data-ttu-id="49a0c-122">デバイスで暗号化を適用すると、回復キーは、ユーザーの Microsoft アカウントからしかアクセスできなくなります。また、OneDrive アカウントからアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49a0c-122">When you enforce encryption on a device, the recovery key is only accessible from the user's Microsoft account, which is accessed from their OneDrive account.</span></span> <span data-ttu-id="49a0c-123">ユーザーの代わりにこのキーを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="49a0c-123">You cannot recover this key on behalf of a user.</span></span>     



## <a name="browser"></a><span data-ttu-id="49a0c-124">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="49a0c-124">Browser</span></span>
-   <span data-ttu-id="49a0c-125">**[オートフィル]** - ユーザーがブラウザーのオートコンプリートの設定を変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-125">**Autofill** - Enables users to change autocomplete settings in the browser.</span></span>
-   <span data-ttu-id="49a0c-126">**[不正行為の警告]** - 詐欺目的の疑いがある Web サイトの警告を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-126">**Fraud warnings** - Enables or disables warnings for potential fraudulent websites.</span></span>
-   <span data-ttu-id="49a0c-127">**[SmartScreen]** - 詐欺目的の疑いがある Web サイトの警告を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-127">**SmartScreen** - Enables or disables warnings for potential fraudulent websites.</span></span>
-   <span data-ttu-id="49a0c-128">**[JavaScript]** - ブラウザーで JavaScript などのスクリプトを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-128">**JavaScript** - Enables the browser to run scripts, such as Java script.</span></span>
-   <span data-ttu-id="49a0c-129">**[ポップアップ]** - ブラウザーのポップアップ ブロックを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-129">**Pop-ups** - Enables or disables the browser pop-up blocker.</span></span>
-   <span data-ttu-id="49a0c-130">**[トラッキング拒否ヘッダーを送信する]** - Internet Explorer で、訪問したサイトに Do Not Track ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-130">**Send do-not-track headers** - Sends a do not track header to visited sites in Internet Explorer.</span></span>
-   <span data-ttu-id="49a0c-131">**[プラグイン]** - ユーザーが Internet Explorer にプラグインを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-131">**Plugins** - Enables users to add plug-ins to Internet Explorer.</span></span>
-   <span data-ttu-id="49a0c-132">**[イントラネット サイトにおける 1 単語の入力]** - Bing など、1 つの単語を使用して Internet Explorer に移動先の Web サイトを指示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-132">**Single word entry on intranet site** - Enables use of a single word to direct Internet Explorer to a web site, such as Bing.</span></span>
-   <span data-ttu-id="49a0c-133">**[イントラネット サイトの自動検出]** - Internet Explorer でイントラネット サイト用にセキュリティを構成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-133">**Auto detect of intranet site** - Helps configure security for intranet sites in Internet Explorer.</span></span>
-   <span data-ttu-id="49a0c-134">**[インターネット セキュリティ レベル]** - インターネット サイトに対する Internet Explorer のセキュリティ レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-134">**Internet security level** - Sets the Internet Explorer security level for Internet sites.</span></span>
-   <span data-ttu-id="49a0c-135">**[Intranet security level (イントラネット セキュリティ レベル)]** - イントラネット サイトに対する Internet Explorer のセキュリティ レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-135">**Intranet security level** - Sets the Internet Explorer security level for intranet sites.</span></span>
-   <span data-ttu-id="49a0c-136">**[信頼されているサイトのセキュリティ レベル]** - 信頼済みサイト ゾーンのセキュリティ レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-136">**Trusted sites security level** - Configures the security level for the trusted sites zone.</span></span>
-   <span data-ttu-id="49a0c-137">**[制限付きサイトの高度なセキュリティ]** - 制限付きサイト ゾーンのセキュリティ レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-137">**High security for restricted sites** - Configures the security level for the restricted sites zone.</span></span>
-   <span data-ttu-id="49a0c-138">**[エンタープライズ モード メニュー アクセス]** - Internet Explorer からエンタープライズ モード メニュー オプションへのアクセスをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-138">**Enterprise mode menu access** - Lets users access the Enterprise Mode menu options from Internet Explorer.</span></span>
<span data-ttu-id="49a0c-139">この設定を選択した場合は、さらに **[ログ レポートの場所]** を指定できます。これは、エンタープライズ モード アクセスが有効にされた Web サイトの記録となるレポートの URL を表します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-139">If you select this setting, you can also specify a **Logging report location**, which contains a URL to a report that shows websites for which users have turned on Enterprise Mode access.</span></span>
-   <span data-ttu-id="49a0c-140">**[エンタープライズ モードのサイト一覧の場所]** - エンタープライズ モードがアクティブな場合に使用する Web サイトの一覧の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="49a0c-140">**Enterprise mode site list location** - Specifies the location of the list of websites that will use Enterprise Mode when it is active.</span></span>

## <a name="cellular"></a><span data-ttu-id="49a0c-141">移動体通信</span><span class="sxs-lookup"><span data-stu-id="49a0c-141">Cellular</span></span>
-   <span data-ttu-id="49a0c-142">**[データ ローミング]** - デバイスが移動体通信ネットワーク上にある場合はデータ ローミングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-142">**Data roaming** - Enables data roaming when the device is on a cellular network.</span></span>

## <a name="cloud-and-storage"></a><span data-ttu-id="49a0c-143">クラウドとストレージ</span><span class="sxs-lookup"><span data-stu-id="49a0c-143">Cloud and Storage</span></span>
-   <span data-ttu-id="49a0c-144">**[作業フォルダーの URL]** - 作業フォルダーの URL を設定して、デバイス間でドキュメントを同期できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-144">**Work folders URL** - Sets the URL of the work folder to allow documents to be synchronized across devices.</span></span>
-   <span data-ttu-id="49a0c-145">**[Microsoft アカウントを使用せずに Windows Mail アプリにアクセスする]** - Microsoft アカウントを使用せずに Windows メール アプリケーションにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a0c-145">**Access to Windows Mail app without a Microsoft account** - Enables access to the Windows Mail application without a Microsoft account.</span></span>    
