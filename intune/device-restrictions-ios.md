---
title: "iOS の Intune デバイス制限設定"
titleSuffix: Azure portal
description: "iOS デバイスでデバイスの設定と機能を制御するために使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a51d1b9c2b5390900daffdd0bf9722ce601ec1bb
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="ios-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="2d9f3-103">Microsoft Intune での iOS デバイスの制限設定</span><span class="sxs-lookup"><span data-stu-id="2d9f3-103">iOS device restriction settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="general"></a><span data-ttu-id="2d9f3-104">全般</span><span class="sxs-lookup"><span data-stu-id="2d9f3-104">General</span></span>

-   <span data-ttu-id="2d9f3-105">**[診断データの送信]** - デバイスから Apple への診断データの送信を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-105">**Diagnostic data submission** - Allow or block the device from submitting diagnostic data to Apple.</span></span>
-   <span data-ttu-id="2d9f3-106">**[画面キャプチャ]** - ユーザーが画面のコンテンツを画像としてキャプチャできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-106">**Screen capture** - Allow the user to capture the contents of the screen as an image.</span></span>
    - <span data-ttu-id="2d9f3-107">**[Classroom アプリによるリモート画面の監視 (監視のみ)]** - Apple の Classroom アプリが iOS デバイス上の画面を監視することを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-107">**Remote screen observation by Classroom app (supervised only)** - Allow or block the Apple Classroom app from viewing the screen of iOS devices.</span></span>
    - <span data-ttu-id="2d9f3-108">**[Classroom アプリによるプロンプトなしの画面監視 (監視モードのみ)]** - 許可すると、学生に知られることなく Classroom アプリを使用して学生の iOS デバイスの画面を黙って監視することができます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-108">**Unprompted screen observation by Classroom app (supervised only)** - If allowed, teachers can silently observe the screen of students iOS devices  using the Classroom app without the students knowledge.</span></span>
-   <span data-ttu-id="2d9f3-109">**[信頼できない TLS 証明書]** - デバイスで信頼されていないトランスポート層セキュリティ (TLS) 証明書を許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-109">**Untrusted TLS certificates** - Allow untrusted Transport Layer Security certificates on the device.</span></span>
-   <span data-ttu-id="2d9f3-110">**[エンタープライズ アプリの信頼]** - アプリ ストアからダウンロードされたのではないアプリを信頼するようにユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-110">**Enterprise app trust** - Lets the user select to trust apps that were not downloaded from the app store.</span></span>
- <span data-ttu-id="2d9f3-111">**アカウント変更 (監視のみ)** - ブロックされているとき、ユーザーは iOS 設定アプリからデバイス固有設定を変更できなくなります。デバイス アカウントの新規作成、ユーザー名やパスワードの変更などが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-111">**Account modification (supervised only)** - When blocked, this prevents the user from modifying device-specific settings from the iOS settings app, like creating new device accounts, and changing the user name or password.</span></span>
<span data-ttu-id="2d9f3-112">これは、メール、連絡先、予定表、Facebook、Twitter など、iOS 設定アプリからアクセスできる設定にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-112">This also applies to settings accessible from the iOS settings app like Mail, Contacts, Calendar, Facebook, and Twitter.</span></span> <span data-ttu-id="2d9f3-113">Microsoft Outlook アプリなど、アカウント設定が iOS 設定アプリから構成できないアプリには適用されません。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-113">This does not apply to apps with account settings that are not configurable from the iOS settings app, for example, the Microsoft Outlook app.</span></span>
- <span data-ttu-id="2d9f3-114">**[デバイス設定での制限の有効化 (監視モードのみ)]** - ユーザーがデバイスにデバイス制限 (保護者による制限) を構成することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-114">**Enabling restrictions in the device settings (supervised only)** - Allow the user to configure device restrictions (parental controls) on the device.</span></span>
- <span data-ttu-id="2d9f3-115">**[デバイスでの [すべてのコンテンツと設定を消去] オプションの使用 (監視モードのみ)]** - ユーザーがデバイスのすべてのコンテンツと設定を消去するオプションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-115">**Use of the erase all content and settings option on the device (supervised only)** - Allow the user to use the option of erasing all content and settings on the device.</span></span>
- <span data-ttu-id="2d9f3-116">**[デバイス名の変更 (監視モードのみ)]** - ユーザーがデバイスの名前を変更することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-116">**Device name modification (supervised only)** - Allow the user to change the name of the device.</span></span>
- <span data-ttu-id="2d9f3-117">**[通知設定の変更 (監視モードのみ)]** - ユーザーがデバイスの通知設定を変更することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-117">**Notification settings modification (supervised only)** - Allow the user to change the device notification settings.</span></span>
- <span data-ttu-id="2d9f3-118">**[壁紙の変更 (監視モードのみ)]** - ユーザーがデバイスの壁紙を変更することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-118">**Wallpaper modification (supervised only)** - Allow the user to change the device wallpaper.</span></span>
- <span data-ttu-id="2d9f3-119">**[エンタープライズ アプリの信頼設定の変更 (監視モードのみ)]** - アプリ ストアからダウンロードされたのではないアプリを信頼するようにユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-119">**Enterprise app trust settings modification (supervised only)** - Lets the user select to trust apps that were not downloaded from the app store.</span></span>
- <span data-ttu-id="2d9f3-120">**[構成プロファイルの変更 (監視モードのみ)]** - ユーザーが構成プロファイルをインストールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-120">**Configuration profile changes (supervised only)** - Allow the user to install configuration profiles.</span></span>
- <span data-ttu-id="2d9f3-121">**[アクティベーション ロック (監視下のみ)]** - 監視されている iOS デバイスでアクティベーション ロックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-121">**Activation Lock (supervised only)** - Enable Activation Lock on supervised iOS devices.</span></span>

## <a name="configurations-requiring-supervision"></a><span data-ttu-id="2d9f3-122">監視を必要とする構成</span><span class="sxs-lookup"><span data-stu-id="2d9f3-122">Configurations requiring supervision</span></span>

<span data-ttu-id="2d9f3-123">iOS 監視モードは、Apple の Device Enrollment Program または Apple Configurator を使用し、デバイスの初期セットアップ中にのみ有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-123">iOS supervised mode can only be enabled during initial device setup through Apple’s Device Enrollment Program, or by using Apple Configurator.</span></span> <span data-ttu-id="2d9f3-124">監視モードを有効にすると、Intune では、次の機能でデバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-124">Once supervised mode is enabled, Intune can configure a device with the following functionality:</span></span>

- <span data-ttu-id="2d9f3-125">アプリ ロック (シングル アプリ モード)</span><span class="sxs-lookup"><span data-stu-id="2d9f3-125">App Lock (Single App Mode)</span></span> 
- <span data-ttu-id="2d9f3-126">グローバル HTTP プロキシ</span><span class="sxs-lookup"><span data-stu-id="2d9f3-126">Global HTTP Proxy</span></span> 
- <span data-ttu-id="2d9f3-127">アクティベーション ロックのバイパス</span><span class="sxs-lookup"><span data-stu-id="2d9f3-127">Activation Lock Bypass</span></span> 
- <span data-ttu-id="2d9f3-128">自律的シングル App モード</span><span class="sxs-lookup"><span data-stu-id="2d9f3-128">Autonomous Single App Mode</span></span> 
- <span data-ttu-id="2d9f3-129">Web コンテンツ フィルター</span><span class="sxs-lookup"><span data-stu-id="2d9f3-129">Web Content Filter</span></span> 
- <span data-ttu-id="2d9f3-130">背景およびロック画面の設定</span><span class="sxs-lookup"><span data-stu-id="2d9f3-130">Set background and lock screen</span></span> 
- <span data-ttu-id="2d9f3-131">アプリのサイレント プッシュ</span><span class="sxs-lookup"><span data-stu-id="2d9f3-131">Silent App Push</span></span> 
- <span data-ttu-id="2d9f3-132">常時接続 VPN</span><span class="sxs-lookup"><span data-stu-id="2d9f3-132">Always-On VPN</span></span> 
- <span data-ttu-id="2d9f3-133">管理対象アプリのインストールを排他的に許可</span><span class="sxs-lookup"><span data-stu-id="2d9f3-133">Allow managed app installation exclusively</span></span> 
- <span data-ttu-id="2d9f3-134">iBookstore</span><span class="sxs-lookup"><span data-stu-id="2d9f3-134">iBookstore</span></span> 
- <span data-ttu-id="2d9f3-135">iMessages</span><span class="sxs-lookup"><span data-stu-id="2d9f3-135">iMessages</span></span> 
- <span data-ttu-id="2d9f3-136">Game Center</span><span class="sxs-lookup"><span data-stu-id="2d9f3-136">Game Center</span></span> 
- <span data-ttu-id="2d9f3-137">AirDrop</span><span class="sxs-lookup"><span data-stu-id="2d9f3-137">AirDrop</span></span> 
- <span data-ttu-id="2d9f3-138">AirPlay</span><span class="sxs-lookup"><span data-stu-id="2d9f3-138">AirPlay</span></span> 
- <span data-ttu-id="2d9f3-139">ホスト ペアリング</span><span class="sxs-lookup"><span data-stu-id="2d9f3-139">Host pairing</span></span> 
- <span data-ttu-id="2d9f3-140">クラウドの同期</span><span class="sxs-lookup"><span data-stu-id="2d9f3-140">Cloud Sync</span></span> 
- <span data-ttu-id="2d9f3-141">スポットライト検索</span><span class="sxs-lookup"><span data-stu-id="2d9f3-141">Spotlight search</span></span> 
- <span data-ttu-id="2d9f3-142">ハンドオフ</span><span class="sxs-lookup"><span data-stu-id="2d9f3-142">Handoff</span></span> 
- <span data-ttu-id="2d9f3-143">デバイスの消去</span><span class="sxs-lookup"><span data-stu-id="2d9f3-143">Erase device</span></span> 
- <span data-ttu-id="2d9f3-144">制限事項 UI</span><span class="sxs-lookup"><span data-stu-id="2d9f3-144">Restrictions UI</span></span> 
- <span data-ttu-id="2d9f3-145">UI による構成プロファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="2d9f3-145">Installation of configuration profiles by UI</span></span> 
- <span data-ttu-id="2d9f3-146">News</span><span class="sxs-lookup"><span data-stu-id="2d9f3-146">News</span></span> 
- <span data-ttu-id="2d9f3-147">キーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="2d9f3-147">Keyboard shortcuts</span></span> 
- <span data-ttu-id="2d9f3-148">パスコードの変更</span><span class="sxs-lookup"><span data-stu-id="2d9f3-148">Passcode modifications</span></span> 
- <span data-ttu-id="2d9f3-149">デバイス名の変更</span><span class="sxs-lookup"><span data-stu-id="2d9f3-149">Device name changes</span></span> 
- <span data-ttu-id="2d9f3-150">壁紙の変更</span><span class="sxs-lookup"><span data-stu-id="2d9f3-150">Wallpaper changes</span></span> 
- <span data-ttu-id="2d9f3-151">アプリの自動ダウンロード</span><span class="sxs-lookup"><span data-stu-id="2d9f3-151">Automatic app downloads</span></span> 
- <span data-ttu-id="2d9f3-152">エンタープライズ アプリケーションの信頼に対する変更</span><span class="sxs-lookup"><span data-stu-id="2d9f3-152">Changes to enterprise app trust</span></span> 
- <span data-ttu-id="2d9f3-153">Apple Music</span><span class="sxs-lookup"><span data-stu-id="2d9f3-153">Apple Music</span></span> 
- <span data-ttu-id="2d9f3-154">メール ドロップ</span><span class="sxs-lookup"><span data-stu-id="2d9f3-154">Mail Drop</span></span> 
- <span data-ttu-id="2d9f3-155">Apple Watch とのペアリング</span><span class="sxs-lookup"><span data-stu-id="2d9f3-155">Pair with Apple Watch</span></span> 

> [!NOTE]
> <span data-ttu-id="2d9f3-156">Apple は、2018 年に特定の設定を "監視対象モードのみ" に移行することを確定しました。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-156">Apple confirmed that certain settings will move to supervised-only in 2018.</span></span> <span data-ttu-id="2d9f3-157">Apple が特定の設定を "監視対象モードのみ" に移行するのを待つのではなく、該当する設定を使用する際に、その変更が行われることを考慮に入れることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-157">We recommend taking this into consideration when using these settings instead of waiting for Apple to migrate them to supervised-only:</span></span>
> - <span data-ttu-id="2d9f3-158">エンド ユーザーによるアプリのインストール</span><span class="sxs-lookup"><span data-stu-id="2d9f3-158">App installation by end users</span></span>
> - <span data-ttu-id="2d9f3-159">アプリの削除</span><span class="sxs-lookup"><span data-stu-id="2d9f3-159">App removal</span></span>
> - <span data-ttu-id="2d9f3-160">FaceTime</span><span class="sxs-lookup"><span data-stu-id="2d9f3-160">FaceTime</span></span>
> - <span data-ttu-id="2d9f3-161">Safari</span><span class="sxs-lookup"><span data-stu-id="2d9f3-161">Safari</span></span>
> - <span data-ttu-id="2d9f3-162">iTunes</span><span class="sxs-lookup"><span data-stu-id="2d9f3-162">iTunes</span></span>
> - <span data-ttu-id="2d9f3-163">明示的なコンテンツ</span><span class="sxs-lookup"><span data-stu-id="2d9f3-163">Explicit content</span></span>
> - <span data-ttu-id="2d9f3-164">iCloud のドキュメントおよびデータ</span><span class="sxs-lookup"><span data-stu-id="2d9f3-164">iCloud documents and data</span></span>
> - <span data-ttu-id="2d9f3-165">マルチプレイヤー ゲーム</span><span class="sxs-lookup"><span data-stu-id="2d9f3-165">Multiplayer gaming</span></span>
> - <span data-ttu-id="2d9f3-166">Game Center のフレンドの追加</span><span class="sxs-lookup"><span data-stu-id="2d9f3-166">Add Game Center friends</span></span>

## <a name="password"></a><span data-ttu-id="2d9f3-167">パスワード</span><span class="sxs-lookup"><span data-stu-id="2d9f3-167">Password</span></span>
-   <span data-ttu-id="2d9f3-168">**[パスワード]** - エンド ユーザーがデバイスにアクセスする際にパスワードの入力を要求します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-168">**Password** - Require the end user to enter a password to access the device.</span></span>
    -   <span data-ttu-id="2d9f3-169">**[単純なパスワード]** - 0000 や 1234 などの単純なパスワードを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-169">**Simple passwords** - Allow simple passwords like 0000 and 1234.</span></span>
    -   <span data-ttu-id="2d9f3-170">**[必要なパスワードの種類]** - 数字のみや英数字など、必要なパスワードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-170">**Required password type** - Specify the type of password that will be required, such as numeric only or alphanumeric.</span></span>
    -   <span data-ttu-id="2d9f3-171">**[パスワードに使用する英数字以外の文字数]** - パスワードに含める必要がある記号 (**#** や **@** など) の個数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-171">**Number of non-alphanumeric characters in password** - Specify the number of symbol characters (like **#** or **@**) that must be included in the password.</span></span>
    -   <span data-ttu-id="2d9f3-172">**[パスワードの最小文字数]** - パスワードの最小文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-172">**Minimum password length** - Specify the minimum number of characters in the password.</span></span>
    -   <span data-ttu-id="2d9f3-173">**[デバイスがワイプされるまでのサインイン失敗回数]** - ログイン試行の失敗を許容する回数を指定します。この回数を超えると、デバイスはワイプされます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-173">**Number of sign-in failures before wiping device** - Specify the number of failed login attempts before this setting wipes the device.</span></span>
    -   <span data-ttu-id="2d9f3-174">**[画面ロック後にパスワードが要求されるまでの最長時間 (分)]**<sup>1</sup> - デバイスのアイドル状態が許容される時間を指定します。この時間を超えると、ユーザーはパスワードを再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-174">**Maximum minutes after screen lock before password is required**<sup>1</sup> - Specify how long the device can remain idle before the user must re-enter their password.</span></span>
    -   <span data-ttu-id="2d9f3-175">**[画面がロックされるまでの非アクティブな最長時間 (分)]**<sup>1</sup> - デバイス ディスプレイがオフになるまでの時間を分単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-175">**Maximum minutes of inactivity until screen locks**<sup>1</sup> - Specify the number of minutes before the device display is turned off.</span></span>
    -   <span data-ttu-id="2d9f3-176">**[パスワードの有効期限 (日数)]** - デバイス パスワードの変更が必要になるまでの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-176">**Password expiration (days)** - Specify the number of days before the device password must be changed.</span></span>
    -   <span data-ttu-id="2d9f3-177">**[Prevent reuse of previous passwords (前のパスワードを再利用できないようにする)]** - デバイスで記憶される、以前に使用したパスワードの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-177">**Prevent reuse of previous passwords** - Specify the number of previously used passwords that the device remembers.</span></span>
    -   <span data-ttu-id="2d9f3-178">**[指紋によるロック解除]** - 指紋を使用して互換性のあるデバイスのロックを解除できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-178">**Fingerprint unlock** - Allow using a fingerprint to unlock compatible devices.</span></span>
- <span data-ttu-id="2d9f3-179">**[パスコードの変更 (監視モードのみ)]** - パスコードの変更、追加、削除を停止します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-179">**Passcode modification (supervised only)** - Stops the passcode from being changed, added, or removed.</span></span>
    - <span data-ttu-id="2d9f3-180">**[指紋の変更 (管理モードのみ)]** - ユーザーによる TouchID 設定の変更、追加、削除を停止します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-180">**Fingerprint modification (supervised only)** - Stops the user from changing, adding, or removing TouchID settings.</span></span>

<span data-ttu-id="2d9f3-181"><sup>1</sup> **[画面がロックされるまでの非アクティブな最長時間 (分)]** と **[画面ロック後にパスワードが要求されるまでの最長時間 (分)]** の設定を構成した場合、これらの設定は順番に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-181"><sup>1</sup>When you configure the settings **Maximum minutes of inactivity until screen locks** and **Maximum minutes after screen lock before password is required**, they are applied in sequence.</span></span> <span data-ttu-id="2d9f3-182">たとえば、両方の設定値を「 **5** 」分に設定すると、5 分後に画面が自動的にオフになり、さらに 5 分後にデバイスがロックされます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-182">For example, if you set the value for both settings to **5** minutes, the screen will turn off automatically after 5 minutes, and the device will be locked after an additional 5 minutes.</span></span> <span data-ttu-id="2d9f3-183">ただし、ユーザーが手動で画面をオフにした場合、2 つ目の設定は即時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-183">However, if the user turns off the screen manually, the second setting is immediately applied.</span></span> <span data-ttu-id="2d9f3-184">同じ例で、ユーザーが画面をオフにした後、デバイスは 5 分後にロックされます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-184">In the same example, after the user turns off the screen, the device will lock 5 minutes later.</span></span>

## <a name="locked-screen-experience"></a><span data-ttu-id="2d9f3-185">ロック画面</span><span class="sxs-lookup"><span data-stu-id="2d9f3-185">Locked Screen Experience</span></span>

-   <span data-ttu-id="2d9f3-186">**[デバイスのロック中のコントロール センターへのアクセス]** - デバイスがロックされているときにユーザーがコントロール センター アプリにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-186">**Control Center access while device locked** - Allow the user to access the control center app when the device is locked.</span></span>
-   <span data-ttu-id="2d9f3-187">**[デバイスのロック中の通知]** - ユーザーがデバイスのロックを解除せずに通知ビューにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-187">**Notifications while device locked** - Allow the user to access the notifications view without unlocking the device.</span></span>
-   <span data-ttu-id="2d9f3-188">**[デバイスのロック中の Passbook]** - ユーザーがデバイスのロック中に Passbook アプリにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-188">**Passbook while device locked** - Allow the user to access the Passbook app while the device is locked.</span></span>
-   <span data-ttu-id="2d9f3-189">**[デバイスがロックされているときの [今日] ビュー]** - ユーザーがデバイスのロック中に [今日] ビューを表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-189">**Today view while device locked** - Allow the user to see the Today view when the device is locked.</span></span>

## <a name="app-store-doc-viewing-gaming"></a><span data-ttu-id="2d9f3-190">アプリ ストア、ドキュメント表示、ゲーム</span><span class="sxs-lookup"><span data-stu-id="2d9f3-190">App Store, Doc Viewing, Gaming</span></span>


-   <span data-ttu-id="2d9f3-191">**[アプリ ストア]** - 監視対象のデバイスでアプリ ストアへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-191">**App store** - Block access to the app store on supervised devices.</span></span>
    - <span data-ttu-id="2d9f3-192">**[App Store からのアプリのインストール (監視モードのみ)]** - デバイスのホーム画面からアプリ ストアにアクセスできないようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-192">**Installing apps from App Store (supervised only)** - Blocks the app store from the device home screen.</span></span> <span data-ttu-id="2d9f3-193">エンド ユーザーは、iTunes または Apple Configurator を使用して引き続きアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-193">End users can continue to use iTunes or the Apple Configurator to install apps.</span></span>
    - <span data-ttu-id="2d9f3-194">**[アプリの自動ダウンロード (監視モードのみ)]** - 別の iOS デバイスで購入したアプリがこのデバイスにダウンロードされないようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-194">**Automatic app downloads (supervised only)** - Stops apps that were purchased on another iOS device from being downloaded to this device.</span></span>
-   <span data-ttu-id="2d9f3-195">**[アプリ ストアにアクセスするためのパスワード]** - アプリ ストアにアクセスしようとするユーザーにパスワードの入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-195">**Password to access app store** - Require the user to enter a password before they can visit the app store.</span></span>
-   <span data-ttu-id="2d9f3-196">**[アプリ内購入]** - 実行中のアプリ内からのストアでの購入を許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-196">**In-app purchases** - Allow store purchases to be made from within a running app.</span></span>
-   <span data-ttu-id="2d9f3-197">**[成人指定の iTunes ミュージック、ポッドキャスト、またはニュース コンテンツ (監視下のみ)]** - デバイスでストアからアダルト コンテンツとして評価されているコンテンツにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-197">**Explicit iTunes music, podcast, or news content (supervised only)** - Allow the device to access content rated as adult from the store.</span></span>
-   <span data-ttu-id="2d9f3-198">**['アダルト' のフラグが付いているコンテンツを iBook ストアからダウンロードします]** - "アダルト" カテゴリのブックをユーザーがダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-198">**Download content from iBook store flagged as 'Erotica'** - Allow the user to download books with the "Erotica" category.</span></span>
-   <span data-ttu-id="2d9f3-199">**[管理対象ではないアプリで会社のドキュメントを表示]** - 任意のアプリで会社のドキュメントを表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-199">**Viewing corporate documents in unmanaged apps** - Allow corporate documents to be viewed in any app.</span></span><br><span data-ttu-id="2d9f3-200">**例:** ユーザーが OneDrive アプリから Dropbox にファイルを保存できないようにする場合。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-200">**Example:** You want to prevent users from saving files from the OneDrive app to Dropbox.</span></span> <span data-ttu-id="2d9f3-201">この設定を "いいえ" として構成します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-201">Configure this setting as no.</span></span> <span data-ttu-id="2d9f3-202">デバイスがポリシーを受信した後 (たとえば、再起動後)、保存は許可されなくなります。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-202">After the device receives the policy (for example, after a restart), it will no longer allow saving.</span></span>
-   <span data-ttu-id="2d9f3-203">**[社内アプリでの社外ドキュメントの表示]** - 会社の管理対象アプリで任意のドキュメントを表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-203">**Viewing non-corporate documents in corporate apps** - Allow any document to be viewed in corporate managed apps.</span></span>
-   <span data-ttu-id="2d9f3-204">**[Airdrop を管理対象外として扱います]** - 管理対象アプリが Airdrop 経由でデータを送信できないようにします</span><span class="sxs-lookup"><span data-stu-id="2d9f3-204">**Treat AirDrop as an unmanaged destination** - Stops managed apps from being able to send data via.</span></span> <span data-ttu-id="2d9f3-205">。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-205">Airdrop.</span></span>
-   <span data-ttu-id="2d9f3-206">**[ゲーム センターの友だちの追加 (監視下のみ)]** - ユーザーがゲーム センターの友だちを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-206">**Adding Game Center friends (supervised only)** - Allow the user to add friends in Game Center.</span></span>
-   <span data-ttu-id="2d9f3-207">**[Game Center (監視モードのみ)]** - Game Center アプリの使用をブロックまたは許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-207">**Game Center (supervised only)** - Block or enable the use of the Game Center app.</span></span>
-   <span data-ttu-id="2d9f3-208">**[マルチプレイヤー ゲーム (監視下のみ)]** - ユーザーがデバイスでマルチプレイヤー ゲームをプレイできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-208">**Multiplayer gaming (supervised only)** - Allow the user to play multiplayer games on the device.</span></span>
-   <span data-ttu-id="2d9f3-209">**[年齢区分の地域]** - 許可するダウンロードを構成する年齢区分の地域を選択し、次に **[映画]** と **[テレビ番組]** の許可する年齢区分を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-209">**Ratings region** - Choose the ratings region for which you want to configure allowed downloads, then choose the allowed ratings for **Movies** and **TV Shows**.</span></span>
-   <span data-ttu-id="2d9f3-210">**[アプリ]** - ユーザーがダウンロードできるアプリに関して許可する年齢区分を選択するか、**[すべてのアプリを許可する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-210">**Apps** - Choose the allowed age rating of apps that users will be able to download, or you can choose **Allow All Apps**.</span></span>

## <a name="built-in-apps"></a><span data-ttu-id="2d9f3-211">組み込みアプリ</span><span class="sxs-lookup"><span data-stu-id="2d9f3-211">Built-in Apps</span></span>

-   <span data-ttu-id="2d9f3-212">**[カメラ]** - デバイスのカメラを使用できるようにするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-212">**Camera** - Select whether the camera on the device can be used.</span></span>
    -   <span data-ttu-id="2d9f3-213">**[FaceTime]** - FaceTime アプリをデバイスで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-213">**FaceTime** - Allow the FaceTime app to be used on the device.</span></span>
-   <span data-ttu-id="2d9f3-214">**[Siri]** - デバイスで Siri 音声アシスタントを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-214">**Siri** - Allow use of the Siri voice assistant on the device.</span></span>
    -   <span data-ttu-id="2d9f3-215">**[デバイスがロックされている間の Siri]** - デバイスのロック中に Siri 音声アシスタントを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-215">**Siri while device is locked** - Allow use of the Siri voice assistant on the device while it is locked.</span></span>
    -   <span data-ttu-id="2d9f3-216">**[Siri の不適切な単語フィルター (監視のみ)]** - Siri が不適切な言葉をディクテーションまたは読み上げないようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-216">**Siri profanity filter (supervised only)** - Prevents Siri from dictating, or speaking profane language.</span></span>
    -   <span data-ttu-id="2d9f3-217">**[ユーザーが生成したインターネットのコンテンツを照会するための Siri (監視のみ)]** - Siri が Web サイトにアクセスして質問に回答することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-217">**Siri to query user-generated content from the internet (supervised only)** - Allow Siri to access websites to answer questions.</span></span>
- <span data-ttu-id="2d9f3-218">**[Apple News (監視モードのみ)]** - Apple News アプリの使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-218">**Apple News (supervised only)** - Allow use of the Apple News app.</span></span>
- <span data-ttu-id="2d9f3-219">**[iBooks ストア (監視モードのみ)]** - ユーザーが iBooks ストアを閲覧してブックを購入することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-219">**iBooks store (supervised only)** - Allow the user to browse and purchase books from the iBooks store.</span></span>
- <span data-ttu-id="2d9f3-220">**[デバイス上のメッセージ アプリ (監視モードのみ)]** - メッセージ アプリを使用してテキストメッセージを送信したり読んだりできます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-220">**Messages app on the device (supervised only)** - Allow use of the Messages app to send and read text messages.</span></span>
- <span data-ttu-id="2d9f3-221">**[ポッドキャスト (監視モードのみ)]** - ポッドキャスト アプリの使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-221">**Podcasts (supervised only)** - Allow use of the Podcasts app.</span></span>
- <span data-ttu-id="2d9f3-222">**[Music サービス (監視モードのみ)]** - Apple Music アプリの使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-222">**Music service (supervised only)** - Allow use of the Apple Music app.</span></span>
- <span data-ttu-id="2d9f3-223">**[iTunes Radio サービス (監視モードのみ)]** - iTunes Radio アプリの使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-223">**iTunes Radio service (supervised only)** - Allow use of the iTunes Radio app.</span></span>
- <span data-ttu-id="2d9f3-224">**["友達を探す" アプリの設定の変更 (監視モードのみ)]** - ユーザーが " 友達を探す" アプリの設定を変更することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-224">**Changes to the Find My Friends app settings (supervised only)** - Allow the user to change settings for the Find My Friends app.</span></span>
- <span data-ttu-id="2d9f3-225">**[インターネットからの結果を返すスポットライト検索 (監視のみ)]** - スポットライト検索でインターネットに接続してさらに多くの検索結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-225">**Spotlight search to return results from internet (supervised only)** - Let Spotlight search connect to the Internet to provide further results.</span></span>

## <a name="restricted-apps"></a><span data-ttu-id="2d9f3-226">制限付きアプリ</span><span class="sxs-lookup"><span data-stu-id="2d9f3-226">Restricted apps</span></span>

<span data-ttu-id="2d9f3-227">制限付きアプリの一覧では、次の一覧のいずれかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-227">In the restricted apps list, you can configure one of the following lists:</span></span>

- <span data-ttu-id="2d9f3-228">**[禁止されているアプリ]** の一覧 - ユーザーによるインストールと実行が許可されていないアプリ (Intune で管理されていない) アプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-228">A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.</span></span> <span data-ttu-id="2d9f3-229">ユーザーは禁止されたアプリもインストールできますが、インストールした場合、そのことが報告されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-229">Users are not prevented from installing a prohibited app, but if they do so, this will be reported to you.</span></span>
- <span data-ttu-id="2d9f3-230">**[承認済みアプリ]** の一覧 - ユーザーによるインストールが許可されているアプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-230">An **Approved apps** list - List the apps that users are allowed to install.</span></span> <span data-ttu-id="2d9f3-231">ユーザーは一覧表示されていないアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-231">Users must not install apps that are not listed.</span></span> <span data-ttu-id="2d9f3-232">管理対象アプリは Intune で自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-232">Apps that are managed by Intune are automatically allowed.</span></span> <span data-ttu-id="2d9f3-233">ユーザーは承認済みリストにないアプリもインストールできますが、インストールした場合、そのことが報告されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-233">Users are not prevented from installing an app that is not on the approved list, but if they do so, this will be reported to you.</span></span>

<span data-ttu-id="2d9f3-234">この一覧を構成するには、**[追加]** をクリックし、任意の名前、アプリの発行元 (省略可能)、アプリ ストアでのアプリの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-234">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.</span></span>

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a><span data-ttu-id="2d9f3-235">ストアにおけるアプリの URL を指定する方法</span><span class="sxs-lookup"><span data-stu-id="2d9f3-235">How to specify the URL to an app in the store</span></span>

<span data-ttu-id="2d9f3-236">アプリの一覧でアプリの URL を指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-236">To specify an app URL in the apps list, use the following format:</span></span>

<span data-ttu-id="2d9f3-237">検索エンジンを使用して、iTunes App Store で使用するアプリを検索し、アプリのページを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-237">Using a search engine, find the app that you want to use in the iTunes App Store and open the page for the app.</span></span>
<span data-ttu-id="2d9f3-238">ページの URL をコピーして、許可されているアプリまたは禁止されているアプリの一覧、またはキオスク モードで実行するアプリを構成する URL として使用します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-238">Copy the URL of the page and use this as the URL to configure the allowed or prohibited apps list or an app that you want to run in kiosk mode.</span></span>
<span data-ttu-id="2d9f3-239">制限付きアプリの設定を含むデバイス プロファイルは、ユーザーのグループに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-239">Device profiles that contain restricted app settings must be assigned to groups of users.</span></span>

<span data-ttu-id="2d9f3-240">例: Microsoft Word for iPad を検索します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-240">Example: Search for Microsoft Word for iPad.</span></span> <span data-ttu-id="2d9f3-241">https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8 という URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-241">The URL that you use will be https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.</span></span>

> [!Note]
> <span data-ttu-id="2d9f3-242">iTunes を使用してアプリを検索し、**[リンクのコピー]** コマンドを使用してアプリの URL を入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-242">You can also use iTunes to find the app and then use the **Copy Link** command to get the app URL.</span></span>

### <a name="additional-options"></a><span data-ttu-id="2d9f3-243">追加オプション</span><span class="sxs-lookup"><span data-stu-id="2d9f3-243">Additional options</span></span>

<span data-ttu-id="2d9f3-244">**[インポート]** をクリックして "<*アプリ URL*>, <*アプリ名*>, <*アプリの発行元*>" 形式の csv ファイルから一覧に値を設定したり、**[エクスポート]** をクリックして、制限付きアプリの一覧の内容を含む csv ファイルを同じ形式で作成したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-244">You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the restricted apps list in the same format.</span></span>

## <a name="show-or-hide-apps-supervised-only"></a><span data-ttu-id="2d9f3-245">アプリの表示/非表示 (監視のみ)</span><span class="sxs-lookup"><span data-stu-id="2d9f3-245">Show or hide apps (supervised only)</span></span>

<span data-ttu-id="2d9f3-246">"アプリの表示/非表示" の一覧では、次のいずれかの一覧を構成できます (iOS 9.3 以降を実行している監視対象のデバイスが必要です)。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-246">In the show or hide apps list, you can configure one of the following lists (requires supervised devices running iOS 9.3 or later).</span></span>

<span data-ttu-id="2d9f3-247">**[非表示のアプリ]** の一覧 - ユーザーに表示されないアプリの一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-247">A **Hidden apps** list - Specify a list of apps that will be hidden from users.</span></span> <span data-ttu-id="2d9f3-248">ユーザーはこのようなアプリを表示または起動できません。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-248">Users cannot view, or launch these apps.</span></span>
<span data-ttu-id="2d9f3-249">**[表示するアプリ]** の一覧 - ユーザーが表示および起動できるアプリの一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-249">An **Visible apps** list - Specify a list of apps that users can view and launch.</span></span> <span data-ttu-id="2d9f3-250">他のアプリは表示または起動できません。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-250">No other apps can be viewed or launched.</span></span>

<span data-ttu-id="2d9f3-251">この一覧を構成するには、**[追加]** をクリックし、任意の名前、アプリの発行元 (省略可能)、アプリ ストアでのアプリの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-251">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.</span></span>

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a><span data-ttu-id="2d9f3-252">ストアにおけるアプリの URL を指定する方法</span><span class="sxs-lookup"><span data-stu-id="2d9f3-252">How to specify the URL to an app in the store</span></span>

<span data-ttu-id="2d9f3-253">アプリの一覧でアプリの URL を指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-253">To specify an app URL in the apps list, use the following format:</span></span>

<span data-ttu-id="2d9f3-254">検索エンジンを使用して、iTunes App Store で使用するアプリを検索し、アプリのページを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-254">Using a search engine, find the app that you want to use in the iTunes App Store and open the page for the app.</span></span>
<span data-ttu-id="2d9f3-255">ページの URL をコピーして、許可されているアプリまたは禁止されているアプリの一覧、またはキオスク モードで実行するアプリを構成する URL として使用します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-255">Copy the URL of the page and use this as the URL to configure the allowed or prohibited apps list or an app that you want to run in kiosk mode.</span></span>

<span data-ttu-id="2d9f3-256">例: Microsoft Word for iPad を検索します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-256">Example: Search for Microsoft Word for iPad.</span></span> <span data-ttu-id="2d9f3-257">https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8 という URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-257">The URL that you use will be https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.</span></span>

> [!Note]
> <span data-ttu-id="2d9f3-258">iTunes ソフトウェアを使用してアプリを検索し、**[リンクのコピー]** コマンドを使用してアプリの URL を入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-258">You can also use the iTunes software to find the app and then use the **Copy Link** command to get the app URL.</span></span>

### <a name="additional-options"></a><span data-ttu-id="2d9f3-259">追加オプション</span><span class="sxs-lookup"><span data-stu-id="2d9f3-259">Additional options</span></span>

<span data-ttu-id="2d9f3-260">**[インポート]** をクリックして "<*アプリ URL*>, <*アプリ名*>, <*アプリの発行元*>" 形式の csv ファイルから一覧に値を設定したり、**[エクスポート]** をクリックして、非表示のアプリまたは表示するアプリの一覧の内容を含む csv ファイルを同じ形式で作成したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-260">You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the hidden or visible apps list in the same format.</span></span>


## <a name="wireless"></a><span data-ttu-id="2d9f3-261">ワイヤレス</span><span class="sxs-lookup"><span data-stu-id="2d9f3-261">Wireless</span></span>
-   <span data-ttu-id="2d9f3-262">**[データ ローミング]** - デバイスが移動体通信ネットワーク上にある場合はデータ ローミングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-262">**Data roaming** - Allow data roaming when the device is on a cellular network.</span></span>
-   <span data-ttu-id="2d9f3-263">**[ローミング中のグローバルな Background Fetch]** - デバイスが移動体通信ネットワークでのローミング中に、電子メールなどのデータをフェッチできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-263">**Global background fetch while roaming** - Allow the device to fetch data such as email while it is roaming on a cellular network.</span></span>
-   <span data-ttu-id="2d9f3-264">**[音声ダイヤル]** - デバイスで音声による発信機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-264">**Voice dialing** - Allow use of the voice dialing feature on the device.</span></span>
-   <span data-ttu-id="2d9f3-265">**[音声通話ローミング]** - デバイスが移動体通信ネットワーク上にある場合は音声通話ローミングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-265">**Voice roaming** - Allow voice roaming when the device is on a cellular network.</span></span>
-   <span data-ttu-id="2d9f3-266">**[アプリの携帯データ ネットワークの使用設定に対する変更 (監視モードのみ)]** - 携帯データ ネットワークの使用が許可されているアプリをユーザーが管理することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-266">**Changes to app cellular data usage settings (supervised only)** - Allow the user to control which apps are allowed to use cellular data.</span></span>
-   <span data-ttu-id="2d9f3-267">**[個人用ホット スポット]** - デバイスを個人用ホット スポットとして使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-267">**Personal Hotspot** - Don't allow the device to be used as a personal hotspot.</span></span> <span data-ttu-id="2d9f3-268">この設定は、一部の通信事業者とは互換性がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-268">This setting might not be compatible with some carriers.</span></span>
-   <span data-ttu-id="2d9f3-269">**[必ず構成プロファイルを使用して Wi-Fi ネットワークに参加する (監視モードのみ)]** - デバイスに、Intune の Wi-Fi プロファイルを使用して構成されている Wi-Fi ネットワークへの参加のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-269">**Join Wi-Fi networks only using configuration profiles (supervised only)** - Only allow the device to join Wi-Fi networks that have been configured with an Intune Wi-Fi profile.</span></span>

- <span data-ttu-id="2d9f3-270">**[携帯ネットワークの使用規則 (管理対象アプリのみ)]** - 管理対象アプリが携帯ネットワークで使用できるデータの種類を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-270">**Cellular usage rules (managed apps only)** - Lets you define the data types that managed apps can use when on cellular networks.</span></span> <span data-ttu-id="2d9f3-271">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-271">Choose from:</span></span>
    - <span data-ttu-id="2d9f3-272">**[携帯データ ネットワークの使用をブロックする]**</span><span class="sxs-lookup"><span data-stu-id="2d9f3-272">**Block use of cellular data**</span></span>
    - <span data-ttu-id="2d9f3-273">**[ローミング時に携帯データ ネットワークの使用をブロックする]**</span><span class="sxs-lookup"><span data-stu-id="2d9f3-273">**Block use of cellular data when roaming**</span></span>

## <a name="connected-devices"></a><span data-ttu-id="2d9f3-274">接続されたデバイス</span><span class="sxs-lookup"><span data-stu-id="2d9f3-274">Connected Devices</span></span>

-   <span data-ttu-id="2d9f3-275">**[AirDrop (監視のみ)]** - 近くにあるデバイスとコンテンツを交換する AirDrop 機能の使用をユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-275">**AirDrop (supervised only)** - Allow use of the AirDrop feature to exchange content with nearby devices.</span></span>
-   <span data-ttu-id="2d9f3-276">**[Apple Watch のペアリング (監視モードのみ)]** - デバイスと Apple Watch とのペアリングを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-276">**Apple Watch pairing (supervised only)** - Allow the device to pair with an Apple Watch.</span></span>
-   <span data-ttu-id="2d9f3-277">**[ペアリングされている Apple Watch の手首検出]** - 有効にすると、Apple Watch が装着されていないときには Apple Watch に通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-277">**Wrist detection for paired Apple watch** - When enabled, the Apple Watch won't display notifications when it is not being worn.</span></span>
-   <span data-ttu-id="2d9f3-278">**[Bluetooth の変更 (監視モードのみ)]** - エンド ユーザーがデバイスの Bluetooth 設定を変更できないようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-278">**Bluetooth modification (supervised only)** - Block the end user from changing Bluetooth settings on the device.</span></span>
-   <span data-ttu-id="2d9f3-279">**[iOS デバイスとペアリングできるデバイスのホスト ペアリングによる制御 (監視モードのみ)]** - ホスト ペアリングを使用して管理者が iOS デバイスとペアリングできるデバイスを制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-279">**Host pairing to control the devices an iOS device can pair with (supervised only)** - Allow host pairing to let the administrator control which devices an iOS device can pair with.</span></span>
-   <span data-ttu-id="2d9f3-280">**[AirPlay 送信要求のペアリング パスワードが必須]** - ユーザーが AirPlay を使用して他の Apple デバイスにコンテンツをストリーミングするときに、ペアリング パスワードを要求します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-280">**Require AirPlay outgoing requests pairing password** - Require a pairing password when the user uses AirPlay to stream content to other Apple devices.</span></span>

## <a name="keyboard-and-dictionary"></a><span data-ttu-id="2d9f3-281">キーボードと辞書</span><span class="sxs-lookup"><span data-stu-id="2d9f3-281">Keyboard and Dictionary</span></span>

-   <span data-ttu-id="2d9f3-282">**[単語の定義の検索 (監視のみ)]** - 単語を強調表示し、その定義を検索できる iOS 機能の使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-282">**Word definition lookup (supervised only)** - Allow the iOS feature that lets you highlight a word and look up it's definition.</span></span>
-   <span data-ttu-id="2d9f3-283">**[予測表示キーボード (監視のみ)]** - 予測表示キーボードを使用して、ユーザーが入力していると思われる単語の提案を許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-283">**Predictive keyboards (supervised only)** - Allow the use of predictive keyboards that suggest words the user might want.</span></span>
-   <span data-ttu-id="2d9f3-284">**[自動修正 (監視のみ)]** - デバイスで自動的にスペル ミスの単語が修正されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-284">**Auto-correction (supervised only)** - Lets the device automatically correct misspelled words.</span></span>
-   <span data-ttu-id="2d9f3-285">**[キーボード スペル チェック (監視のみ)]** - デバイスのスペル チェック機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-285">**Keyboard spell-check (supervised only)** - Allows the device spell checker.</span></span>
-   <span data-ttu-id="2d9f3-286">**[キーボード ショートカット (監視のみ)]** - キーボード ショートカットを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-286">**Keyboard shortcuts (supervised only)** - Allows use of keyboard shortcuts.</span></span>
-   <span data-ttu-id="2d9f3-287">**[ディクテーション (監視モードのみ)]** - ユーザーが音声入力を使用してテキストを入力できないようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-287">**Dictation (supervised only)** - Stops the user from using voice input to enter text.</span></span>

## <a name="cloud-and-storage"></a><span data-ttu-id="2d9f3-288">クラウドとストレージ</span><span class="sxs-lookup"><span data-stu-id="2d9f3-288">Cloud and Storage</span></span>
-   <span data-ttu-id="2d9f3-289">**[iCloud へのバックアップ]** - ユーザーが iCloud にデバイスをバックアップできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-289">**Backup to iCloud** - Allow the user to back up the device to iCloud.</span></span>
-   <span data-ttu-id="2d9f3-290">**[iCloud へのドキュメントの同期 (監視下のみ)]** - ドキュメントとキー値を iCloud 記憶域スペースに同期できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-290">**Document sync to iCloud (supervised only)** - Allow document and key-value synchronization to your iCloud storage space.</span></span>
-   <span data-ttu-id="2d9f3-291">**[iCloud へのフォト ストリームの同期]** - ユーザーがデバイスの **[My Photo Stream (マイ フォト ストリーム)]** を有効にできるようにします。有効にすると、写真は iCloud と同期され、すべてのユーザー デバイスで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-291">**Photo stream syncing to iCloud** - Lets users enable **My Photo Stream** on their device which allow photos to sync to iCloud and be available on all the users devices.</span></span>
-   <span data-ttu-id="2d9f3-292">**[暗号化されたバックアップ]** - すべてのデバイス バックアップの暗号化を必須にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-292">**Encrypted backup** - Require any device backups to be encrypted.</span></span>
-   <span data-ttu-id="2d9f3-293">**[iCloud フォトライブラリ]** - **[いいえ]** に設定すると、ユーザーがクラウドに写真やビデオを保存できる iCloud フォトライブラリが使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-293">**iCloud Photo Library** - If set to **No**, disables the use of iCloud photo library which lets users store photos and videos in the cloud.</span></span>    <span data-ttu-id="2d9f3-294">これを **[いいえ]** に設定すると、iCloud フォト ライブラリからデバイスに完全にダウンロードされていない写真はすべてデバイスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-294">Any photos not fully downloaded from iCloud Photo Library to the device will be removed from the device if this is set to **No**.</span></span>
-   <span data-ttu-id="2d9f3-295">**[管理対象アプリのクラウドへの同期]** - Intune で管理するアプリがユーザーの iCloud アカウントにデータを同期することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-295">**Managed apps sync to cloud** - Allow apps that you manage with Intune to sync data to the user's iCloud account.</span></span>
-   <span data-ttu-id="2d9f3-296">**[共有フォト ストリーム]** - デバイスの **[iCloud Photo Sharing (iCloud の写真共有)]** を無効にするには、**[いいえ]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-296">**Shared photo stream** - Set to **No** to disable **iCloud Photo Sharing** on the device..</span></span>
-   <span data-ttu-id="2d9f3-297">**[アクティビティの継続]** - ユーザーがある iOS デバイスで開始した作業を別の iOS または macOS デバイスで続行できるようにします (Handoff)。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-297">**Activity continuation** - Allow the user to continue work that they started on an iOS device on another iOS or macOS device (Handoff).</span></span>

## <a name="autonomous-single-app-mode-supervised-only"></a><span data-ttu-id="2d9f3-298">自律的シングル App モード (監視モードのみ)</span><span class="sxs-lookup"><span data-stu-id="2d9f3-298">Autonomous single app mode (supervised only)</span></span>

<span data-ttu-id="2d9f3-299">これらの設定を使用して、自律的シングル App モードで指定したアプリを実行するように iOS デバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-299">Use these settings to configure iOS devices to run specified apps in autonomous single app mode.</span></span> <span data-ttu-id="2d9f3-300">このモードを構成した場合、指定したアプリが実行されると、デバイスはそのアプリだけを実行できるようにロックされます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-300">When this mode is configured, and the app is run, the device is locked so that it can only run that app.</span></span> <span data-ttu-id="2d9f3-301">たとえば、ユーザーがデバイスでテストを受けられるようにアプリを構成するような場合です。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-301">An example of this is when you configure an app that lets users take a test on the device.</span></span> <span data-ttu-id="2d9f3-302">アプリのアクションが完了した場合、または管理者がこのポリシーを削除した場合、デバイスは通常の状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-302">When the apps actions are complete, or you remove this policy, the device returns to its normal state.</span></span>

### <a name="settings"></a><span data-ttu-id="2d9f3-303">Settings</span><span class="sxs-lookup"><span data-stu-id="2d9f3-303">Settings</span></span>

- <span data-ttu-id="2d9f3-304">**[アプリ名]** - このブレードのアプリ一覧に表示される通りにアプリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-304">**App name** - Enter the name of the app as it will appear in the apps list on this blade.</span></span>
- <span data-ttu-id="2d9f3-305">**[アプリ バンドル ID]** - アプリのバンドル ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-305">**App Bundle ID** - Enter the bundle ID of the app.</span></span> <span data-ttu-id="2d9f3-306">詳細については、このトピックの「**組み込み iOS アプリのバンドル ID リファレンス**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-306">For help, see **Bundle ID reference for built-in iOS apps** in this topic.</span></span>

<span data-ttu-id="2d9f3-307">アプリ名とバンドル ID をそれぞれ指定したら、**[追加]** を選択して一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-307">After you specify each app name and bundle ID, choose **Add** to append it to the list.</span></span>

- <span data-ttu-id="2d9f3-308">**[インポート]** - アプリ名とそれに関連付けられているバンドル ID の一覧を含むコンマ区切り値 (.csv) ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-308">**Import** - Import a comma-separated values (.csv) file containing a list of app names, and their associated bundle IDs.</span></span>
- <span data-ttu-id="2d9f3-309">**[エクスポート]** - 構成したアプリ名とそれに関連付けられているバンドル ID を、コンマ区切り値 (.csv) ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-309">**Export** - Export the app names, and associated bundle IDs you have configured to a comma-separated values (.csv) file.</span></span>

### <a name="bundle-id-reference-for-built-in-ios-apps"></a><span data-ttu-id="2d9f3-310">組み込み iOS アプリのバンドル ID リファレンス</span><span class="sxs-lookup"><span data-stu-id="2d9f3-310">Bundle ID reference for built-in iOS apps</span></span>

<span data-ttu-id="2d9f3-311">この一覧は、一般的な組み込み iOS アプリのバンドル ID を示しています。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-311">This list shows the bundle ID of some common built-in iOS apps.</span></span> <span data-ttu-id="2d9f3-312">他のアプリのバンドル ID を調べるには、ソフトウェア ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-312">To find the bundle ID of other apps, contact your software vendor.</span></span>

```
,com.apple.AppStore,App Store,Apple
,com.apple.calculator,Calculator,Apple
,com.apple.mobilecal,Calendar,Apple
,com.apple.camera,Camera,Apple
,com.apple.mobiletimer,Clock,Apple
,com.apple.compass,Compass,Apple
,com.apple.MobileAddressBook,Contacts,Apple
,com.apple.facetime,FaceTime,Apple
,com.apple.mobileme.fmf1,Find Friends,Apple
,com.apple.mobileme.fmip1,Find iPhone,Apple
,com.apple.gamecenter,Game Center,Apple
,com.apple.mobilegarageband,GarageBand,Apple
,com.apple.Health,Health,Apple
,com.apple.iBooks,iBooks,Apple
,com.apple.MobileStore,iTunes Store,Apple
,com.apple.itunesu,iTunes U,Apple
,com.apple.Keynote,Keynote,Apple
,com.apple.mobilemail,Mail,Apple
,com.apple.MapsMaps,Apple
,com.apple.MobileSMS,Messages,Apple
,com.apple.Music,Music,Apple
,com.apple.news,News,Apple
,com.apple.mobilenotes,Notes,Apple
,com.apple.Numbers,Numbers,Apple
,com.apple.Pages,Pages,Apple
,com.apple.Photo-Booth,Photo Booth,Apple
,com.apple.mobileslideshow,Photos,Apple
,com.apple.podcasts,Podcasts,Apple
,com.apple.reminders,Reminders,Apple
,com.apple.MobileSafari,Safari,Apple
,com.apple.Preferences,Settings,Apple
,com.apple.stocks,Stocks,Apple
,com.apple.tips,Tips,Apple
,com.apple.videos,Videos,Apple
,com.apple.VoiceMemos,VoiceMemos,Apple
,com.apple.Passbook,Wallet,Apple
,com.apple.Bridge,Watch,Apple
,com.apple.weather,Weather,Apple
```


## <a name="kiosk-supervised-only"></a><span data-ttu-id="2d9f3-313">キオスク (監視モードのみ)</span><span class="sxs-lookup"><span data-stu-id="2d9f3-313">Kiosk (supervised only)</span></span>
-   <span data-ttu-id="2d9f3-314">**[キオスク モードで実行されるアプリ]** - **[管理対象アプリ]** を選択して Intune に追加したアプリケーションを選択するか、**[ストア アプリ]** を選択してストア内のアプリの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-314">**App that runs in kiosk mode** - Choose **Managed App** to select an app you've added to Intune, or **Store App** to specify the URL to an app in the store.</span></span> <span data-ttu-id="2d9f3-315">他のアプリはデバイスでの実行が許可されません。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-315">No other apps will be allowed to run on the device.</span></span> <span data-ttu-id="2d9f3-316">詳細については、このトピックで後述する「アプリ ストアの URL を指定する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-316">For more help, see "How to specify URLs to app stores" later in this topic.</span></span>
    -   <span data-ttu-id="2d9f3-317">**[Assistive touch]** - ユーザー補助の設定の **[Assistive Touch]** を有効または無効にします。Assistive Touch は、ユーザーが実行しにくい可能性のある画面の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-317">**Assistive touch** - Enable or disable the **Assistive Touch** accessibility setting, which helps the user perform on-screen gestures that might be difficult for them to perform.</span></span>
    -   <span data-ttu-id="2d9f3-318">**[色の反転]** - 視覚障碍を持つユーザーを支援するためにディスプレイを調整するユーザー補助の設定 [色の反転] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-318">**Invert colors** - Enable or disable the Invert Colors accessibility setting, which adjusts the display to help users with visual impairments.</span></span>
    -   <span data-ttu-id="2d9f3-319">**[モノ オーディオ]** - ユーザー補助の設定の [モノ オーディオ] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-319">**Mono audio** - Enable or disable the accessibility setting Mono audio.</span></span>
    -   <span data-ttu-id="2d9f3-320">**[VoiceOver]** ユーザー補助の設定の **[VoiceOver]** を有効または無効にします。VoiceOver はデバイスのディスプレイ上のテキストを音読します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-320">**VoiceOver** - Enable or disable the accessibility setting **VoiceOver**, which reads aloud text on the device display.</span></span>
    -   <span data-ttu-id="2d9f3-321">**[ズーム]** - ユーザー補助の設定の **[ズーム]** を有効または無効にします。[ズーム] により、ユーザーはタッチすることでデバイスのディスプレイにズーム インできます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-321">**Zoom** - Enable or disable the **Zoom** accessibility setting, which lets the user use touch to zoom in to the device display.</span></span>
    -   <span data-ttu-id="2d9f3-322">**[自動ロック]** - デバイスの自動ロックを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-322">**Auto lock** - Enable or disable automatic locking of the device.</span></span>
    -   <span data-ttu-id="2d9f3-323">**[着信音スイッチ]** - デバイスの着信音 (ミュート) スイッチを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-323">**Ringer switch** - Enable or disable the ringer (mute) switch on the device.</span></span>
    -   <span data-ttu-id="2d9f3-324">**[画面の回転]** - ユーザーがデバイスを回転するときの画面の向きの変更を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-324">**Screen rotation** - Enable or disable changing the screen orientation when the user rotates the device.</span></span>
    -   <span data-ttu-id="2d9f3-325">**[画面スリープ ボタン]** - デバイスの画面スリープ ウェイク ボタンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-325">**Screen sleep button** - Enable or disable the screen sleep wake button on the device.</span></span>
    -   <span data-ttu-id="2d9f3-326">**[タッチ]** - デバイスのタッチスクリーンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-326">**Touch** - Enable or disable the touchscreen on the device.</span></span>
    -   <span data-ttu-id="2d9f3-327">**[音量ボタン]** - デバイスの音量ボタンの使用を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-327">**Volume buttons** - Enable or disable the use of the volume buttons on the device.</span></span>
    -   <span data-ttu-id="2d9f3-328">**[Assistive Touch の制御]** - Assistive Touch の調整を有効または無効にします。Assistive Touch の調整により、ユーザーは Assistive Touch 機能を調整できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-328">**Assistive touch control** - Enable or disable assistive touch adjustments, which let the user adjust the assistive touch function.</span></span>
    -   <span data-ttu-id="2d9f3-329">**[色の反転の制御]** - 色の反転の調整を有効または無効にします。色の反転の調整により、ユーザーは色の反転機能を調整できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-329">**Invert colors control** - Enable or disable invert colors adjustments, which let the user adjust the invert colors function.</span></span>
    -   <span data-ttu-id="2d9f3-330">**[選択したテキストを読み上げる]** - ユーザー補助の設定の [Speak Selection (選択範囲を話す)] を有効または無効にします。[Speak Selection (選択範囲を話す)] により、ユーザーが選択したテキストを読み上げることができます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-330">**Speak on selected text** - Enable or disable the Speak Selection accessibility settings, which can read aloud the text that the user selects.</span></span>
    -   <span data-ttu-id="2d9f3-331">**[VoiceOver 制御]** - ボイス オーバーの調整を有効または無効にします。ボイス オーバーの調整により、ユーザーはボイス オーバー機能を調整できます (画面に表示されるテキストの読み上げ速度など)。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-331">**VoiceOver control** - Enable or disable voiceover adjustments, which let the user adjust the VoiceOver function (for example, how fast on-screen text is read aloud).</span></span>
    -   <span data-ttu-id="2d9f3-332">**[ズーム コントロール]** - ズームの調整を有効または無効にします。ズームの調整により、ユーザーはズーム機能を調整できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-332">**Zoom control** - Enable or disable zoom adjustments, which let the user adjust the zoom function.</span></span>

>[!NOTE]
> <span data-ttu-id="2d9f3-333">iOS デバイスをキオスク モードに構成する前に、Apple Configurator ツールまたは Apple デバイス登録プログラムを使用して、デバイスを監視下モードにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-333">Before you can configure an iOS device for kiosk mode, you must use the Apple Configurator tool or the Apple Device Enrollment Program to put the device into supervised mode.</span></span> <span data-ttu-id="2d9f3-334">Apple Configurator ツールの詳細については、Apple のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-334">For more information about the Apple Configurator tool, see your Apple documentation.</span></span>
><span data-ttu-id="2d9f3-335">プロファイルの割り当て後に、指定した iOS のアプリがインストールされる場合、デバイスは再起動後にキオスク モードになります。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-335">If the iOS app that you specify is installed after you assign the profile, the device will not enter kiosk mode until after it is restarted.</span></span>

## <a name="safari"></a><span data-ttu-id="2d9f3-336">Safari</span><span class="sxs-lookup"><span data-stu-id="2d9f3-336">Safari</span></span>
-   <span data-ttu-id="2d9f3-337">**[Safari (監視下のみ)]** - Safari ブラウザーをデバイスで使用できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-337">**Safari (supervised only)** - Specify whether the Safari browser can be used on the device.</span></span>
-   <span data-ttu-id="2d9f3-338">**[オートフィル]** - ユーザーがブラウザーのオートコンプリートの設定を変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-338">**Autofill** - Allow the user to change autocomplete settings in the browser.</span></span>
-   <span data-ttu-id="2d9f3-339">**[Cookie]** - ブラウザーで Cookie を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-339">**Cookies** - Allow the browser to use cookies.</span></span>
-   <span data-ttu-id="2d9f3-340">**[JavaScript]** - JavaScript をブラウザーで実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-340">**JavaScript** - Allow Java scripts to run in the browser.</span></span>
-   <span data-ttu-id="2d9f3-341">**[不正行為の警告]** - ブラウザーで不正行為の警告を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-341">**Fraud warnings** - Allow fraud warnings in the browser.</span></span>
-   <span data-ttu-id="2d9f3-342">**[ポップアップ]** - ブラウザーのポップアップ ブロックを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-342">**Pop-ups** - Enable or disable the browser pop-up blocker.</span></span>


## <a name="domains"></a><span data-ttu-id="2d9f3-343">Domains</span><span class="sxs-lookup"><span data-stu-id="2d9f3-343">Domains</span></span>

### <a name="unmarked-email-domains"></a><span data-ttu-id="2d9f3-344">マークされていないメール ドメイン</span><span class="sxs-lookup"><span data-stu-id="2d9f3-344">Unmarked email domains</span></span>

<span data-ttu-id="2d9f3-345">**[メール ドメイン URL]** フィールドで、1 つ以上の URL を一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-345">In the **Email Domain URL** field, add one or more URLs to the list.</span></span> <span data-ttu-id="2d9f3-346">構成したドメイン以外のドメインからのメールをエンド ユーザーが受信すると、そのメールは iOS のメール アプリで信頼されていないメールとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-346">When end users receive an email from a domain other than those you configured, the email will be marked as untrusted in the iOS Mail app.</span></span>


### <a name="managed-web-domains"></a><span data-ttu-id="2d9f3-347">管理された Web ドメイン</span><span class="sxs-lookup"><span data-stu-id="2d9f3-347">Managed web domains</span></span>

<span data-ttu-id="2d9f3-348">**[Web ドメイン URL]** フィールドで、1 つ以上の URL を一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-348">In the **Web Domain URL** field, add one or more URLs to the list.</span></span> <span data-ttu-id="2d9f3-349">指定したドメインからダウンロードされたドキュメントは、管理されているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-349">When documents are downloaded from the domains you specify, they will be considered managed.</span></span> <span data-ttu-id="2d9f3-350">この設定は、Safari ブラウザーを使用してダウンロードされたドキュメントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-350">This setting applies only to documents downloaded using the Safari browser.</span></span>


### <a name="safari-password-autofill-domains"></a><span data-ttu-id="2d9f3-351">Safari パスワードの自動入力ドメイン</span><span class="sxs-lookup"><span data-stu-id="2d9f3-351">Safari password autofill domains</span></span>

<span data-ttu-id="2d9f3-352">**[ドメイン URL]** フィールドで、1 つ以上の URL を一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-352">In the **Domain URL** field, add one or more URLs to the list.</span></span> <span data-ttu-id="2d9f3-353">ユーザーは、この一覧の URL からの Web パスワードのみを保存できます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-353">Users can only save web passwords from URLs in this list.</span></span> <span data-ttu-id="2d9f3-354">この設定は、Safari ブラウザー、および iOS 9.3 以降の監視モードのデバイスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-354">This setting applies only to the Safari browser, and to iOS 9.3 and later devices in supervised mode.</span></span> <span data-ttu-id="2d9f3-355">URL を指定しないと、すべての Web サイトからのパスワードが保存されます。</span><span class="sxs-lookup"><span data-stu-id="2d9f3-355">If you don't specify any URLs, then passwords can be saved from all web sites.</span></span>
