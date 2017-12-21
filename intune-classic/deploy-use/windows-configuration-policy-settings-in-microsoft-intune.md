---
title: "Windows ポリシー設定"
description: "Intune の Windows 全般構成ポリシー (Windows 8.1 以降) を使用して、登録済みの Windows 8 および Windows 8.1 デバイスの設定を構成します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 059665094379435381d62a2c45af189bef0289d2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="windows-policy-settings-in-microsoft-intune"></a><span data-ttu-id="60126-103">Microsoft Intune の Windows ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="60126-103">Windows policy settings in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="60126-104">Microsoft Intune の **Windows 全般構成ポリシー (Windows 8.1 以降)** を使用して、登録済みの Windows 8、Windows 8.1、および Windows RT 8.1 デバイスの以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="60126-104">Use the Microsoft Intune **Windows general configuration policy (Windows 8.1 and later)** to configure the following settings for enrolled Windows 8, Windows 8.1, and Windows RT 8.1 devices:</span></span>

## <a name="applicability-settings"></a><span data-ttu-id="60126-105">適用性の設定</span><span class="sxs-lookup"><span data-stu-id="60126-105">Applicability settings</span></span>

|<span data-ttu-id="60126-106">設定の名前</span><span class="sxs-lookup"><span data-stu-id="60126-106">Setting name</span></span>|<span data-ttu-id="60126-107">説明</span><span class="sxs-lookup"><span data-stu-id="60126-107">Details</span></span>|
|----------------|----------------------------------|
|<span data-ttu-id="60126-108">**Windows 10 にすべての構成を適用する**</span><span class="sxs-lookup"><span data-stu-id="60126-108">**Apply all configurations to Windows 10**</span></span>|<span data-ttu-id="60126-109">Windows 8、および Windows 8.1 デバイスに加え、Windows 10 デバイスに、このポリシーの設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="60126-109">Enables settings in this policy to be applied to Windows 10 devices, in addition to Windows 8 and Windows 8.1 devices.</span></span>|

## <a name="security-settings"></a><span data-ttu-id="60126-110">セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="60126-110">Security settings</span></span>

|<span data-ttu-id="60126-111">設定の名前</span><span class="sxs-lookup"><span data-stu-id="60126-111">Setting name</span></span>|<span data-ttu-id="60126-112">説明</span><span class="sxs-lookup"><span data-stu-id="60126-112">Details</span></span>|
|----------------|------|
|<span data-ttu-id="60126-113">**必要なパスワードの種類**</span><span class="sxs-lookup"><span data-stu-id="60126-113">**Required password type**</span></span>|<span data-ttu-id="60126-114">英数字や数値のみなど、必要なパスワードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="60126-114">Specifies the type of password that's required, such as alphanumeric or numeric only.</span></span>|
|<span data-ttu-id="60126-115">**必要なパスワードの種類 - 文字セットの最小数**</span><span class="sxs-lookup"><span data-stu-id="60126-115">**Required password type – Minimum number of character sets**</span></span>|<span data-ttu-id="60126-116">パスワードに含める必要がある文字セットの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="60126-116">Specifies how many different character sets must be included in the password.</span></span> <span data-ttu-id="60126-117">文字セットには、小文字、大文字、数字、および記号の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="60126-117">There are four character sets: lowercase letters, uppercase letters, numbers, and symbols.</span></span> <span data-ttu-id="60126-118">ただし、iOS デバイスの場合は、この設定でパスワードに含める必要がある記号の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="60126-118">However, for iOS devices, this setting specifies the number of symbols that must be included in the password.</span></span>|
|<span data-ttu-id="60126-119">**最小のパスワードの長さ**</span><span class="sxs-lookup"><span data-stu-id="60126-119">**Minimum password length**</span></span>|<span data-ttu-id="60126-120">パスワードに必要な最小の長さ (文字数) を構成します。</span><span class="sxs-lookup"><span data-stu-id="60126-120">Configures the minimum required length (in characters) for the password.</span></span>|
|<span data-ttu-id="60126-121">**デバイスをワイプするまでの連続サインイン エラーの数**</span><span class="sxs-lookup"><span data-stu-id="60126-121">**Number of repeated sign-in failures to allow before the device is wiped**</span></span>|<span data-ttu-id="60126-122">サインインの試みがこの回数だけ失敗した場合は、デバイスがワイプされます。</span><span class="sxs-lookup"><span data-stu-id="60126-122">Wipes the device if the sign-in attempts fail this number of times.</span></span>|
|<span data-ttu-id="60126-123">**画面がオフになるまでの非アクティブな時間 (分)**</span><span class="sxs-lookup"><span data-stu-id="60126-123">**Minutes of inactivity before screen turns off**</span></span>|<span data-ttu-id="60126-124">デバイスのアイドル状態が許容される時間 (分) を指定します。この時間を超えると、ロックを解除するためにパスワードが必要となります。</span><span class="sxs-lookup"><span data-stu-id="60126-124">Specifies the number of minutes a device must be idle before a password is required to unlock it.</span></span>|
|<span data-ttu-id="60126-125">**パスワードの有効期限 (日)**</span><span class="sxs-lookup"><span data-stu-id="60126-125">**Password expiration (days)**</span></span>|<span data-ttu-id="60126-126">デバイスのパスワードの変更が必要になるまでの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="60126-126">Specifies the number of days before the device password must be changed.</span></span>|
|<span data-ttu-id="60126-127">**パスワードの履歴を記憶する**</span><span class="sxs-lookup"><span data-stu-id="60126-127">**Remember password history**</span></span>|<span data-ttu-id="60126-128">過去に使用したパスワードをユーザーが構成できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="60126-128">Specifies whether the user can configure previously used passwords.</span></span>|
|<span data-ttu-id="60126-129">**パスワードの履歴を保存する** - **前のパスワードを再利用できないようにする**</span><span class="sxs-lookup"><span data-stu-id="60126-129">**Remember password history** – **Prevent reuse of previous passwords**</span></span>|<span data-ttu-id="60126-130">デバイスで記憶される、以前に使用したパスワードの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="60126-130">Specifies the number of previously used passwords that are remembered by the device.</span></span>|
|<span data-ttu-id="60126-131">**ピクチャ パスワードと PIN を許可する**</span><span class="sxs-lookup"><span data-stu-id="60126-131">**Allow picture password and PIN**</span></span>|<span data-ttu-id="60126-132">ピクチャ パスワードと PIN を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-132">Enables the use of a picture password and PIN.</span></span> <span data-ttu-id="60126-133">ピクチャ パスワードが許可されている場合、ユーザーは画像に対するジェスチャーでサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="60126-133">A picture password lets the user sign in with gestures on a picture.</span></span> <span data-ttu-id="60126-134">PIN が許可されている場合、ユーザーは 4 桁のコードを使用してすばやくサインインできます。</span><span class="sxs-lookup"><span data-stu-id="60126-134">A PIN lets users quickly sign in with a four-digit code.</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="60126-135">暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="60126-135">Encryption settings</span></span>

|<span data-ttu-id="60126-136">設定の名前</span><span class="sxs-lookup"><span data-stu-id="60126-136">Setting name</span></span>|<span data-ttu-id="60126-137">説明</span><span class="sxs-lookup"><span data-stu-id="60126-137">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="60126-138">**モバイル デバイスの暗号化を要求する**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="60126-138">**Require encryption on mobile device**<sup>1</sup></span></span>|<span data-ttu-id="60126-139">デバイス上のファイルを必ず暗号化するようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-139">Requires that files on the device are encrypted.</span></span>|
<span data-ttu-id="60126-140"><sup>1</sup> Windows 8.1 が実行されているデバイスの追加情報</span><span class="sxs-lookup"><span data-stu-id="60126-140"><sup>1</sup> Additional information for devices that run Windows 8.1</span></span>

-   <span data-ttu-id="60126-141">Windows 8.1 が実行されているデバイスで暗号化を適用するには、 [Windows の 2014 年 12 月付け MDM クライアント更新プログラム](http://support.microsoft.com/kb/3013816) を各デバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60126-141">To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.</span></span>

-   <span data-ttu-id="60126-142">Windows 8.1 デバイスに対してこの設定を有効にすると、デバイスのすべてのユーザーに Microsoft アカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="60126-142">If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.</span></span>

-   <span data-ttu-id="60126-143">暗号化を機能させるには、デバイスが Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) ハードウェア認定要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="60126-143">For encryption to work, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.</span></span>

-   <span data-ttu-id="60126-144">デバイスで暗号化を適用すると、回復キーは、ユーザーの Microsoft アカウントからしかアクセスできなくなります。また、OneDrive アカウントからアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60126-144">When you enforce encryption on a device, the recovery key is only accessible from the user's Microsoft account, which is accessed from their OneDrive account.</span></span> <span data-ttu-id="60126-145">ユーザーの代わりにこのキーを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="60126-145">You cannot recover this key on behalf of a user.</span></span>

## <a name="malware-settings"></a><span data-ttu-id="60126-146">マルウェアの設定</span><span class="sxs-lookup"><span data-stu-id="60126-146">Malware settings</span></span>

|<span data-ttu-id="60126-147">設定の名前</span><span class="sxs-lookup"><span data-stu-id="60126-147">Setting name</span></span>|<span data-ttu-id="60126-148">説明</span><span class="sxs-lookup"><span data-stu-id="60126-148">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="60126-149">**ネットワーク ファイアウォールを必須にする**</span><span class="sxs-lookup"><span data-stu-id="60126-149">**Require network firewall**</span></span>|<span data-ttu-id="60126-150">Windows ファイアウォールを有効にすることを要求します。</span><span class="sxs-lookup"><span data-stu-id="60126-150">Requires that the Windows Firewall is turned on.</span></span>|
|<span data-ttu-id="60126-151">**SmartScreen を有効にする**</span><span class="sxs-lookup"><span data-stu-id="60126-151">**Enable SmartScreen**</span></span>|<span data-ttu-id="60126-152">Windows SmartScreen の使用を必須とします。</span><span class="sxs-lookup"><span data-stu-id="60126-152">Requires the use of Windows SmartScreen.</span></span>|

## <a name="system-settings"></a><span data-ttu-id="60126-153">システムの設定</span><span class="sxs-lookup"><span data-stu-id="60126-153">System settings</span></span>

|<span data-ttu-id="60126-154">設定の名前</span><span class="sxs-lookup"><span data-stu-id="60126-154">Setting name</span></span>|<span data-ttu-id="60126-155">説明</span><span class="sxs-lookup"><span data-stu-id="60126-155">Details</span></span>|
|----------------|-------|
|<span data-ttu-id="60126-156">**自動更新を必須にする**</span><span class="sxs-lookup"><span data-stu-id="60126-156">**Require automatic updates**</span></span>|<span data-ttu-id="60126-157">デバイス上の自動更新設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="60126-157">Turns on the automatic updates setting on devices.</span></span>|
|<span data-ttu-id="60126-158">**自動更新を必須にする – 自動的にインストールする更新プログラムの最低限の分類。**</span><span class="sxs-lookup"><span data-stu-id="60126-158">**Require automatic updates – Minimum classification of updates to install automatically**</span></span>|<span data-ttu-id="60126-159">自動的にインストールする更新プログラムの分類を選択します。</span><span class="sxs-lookup"><span data-stu-id="60126-159">Chooses the classification of updates that will be installed automatically:</span></span><br /><br /><span data-ttu-id="60126-160">-   **重要** – 重要として分類されたすべての更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="60126-160">-   **Important** – Installs all updates that are classified as important.</span></span><br /><span data-ttu-id="60126-161">-   **推奨** – 重要または推奨として分類されたすべての更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="60126-161">-   **Recommended** – Installs all updates that are classified as important or recommended.</span></span>|
|<span data-ttu-id="60126-162">**ユーザー アカウント コントロール**</span><span class="sxs-lookup"><span data-stu-id="60126-162">**User Account Control**</span></span>|<span data-ttu-id="60126-163">デバイス上のユーザー アカウント制御 (UAC) の使用を必須とします。</span><span class="sxs-lookup"><span data-stu-id="60126-163">Requires the use of User Account Control (UAC) on devices.</span></span>|
|<span data-ttu-id="60126-164">**診断データの送信を使用する**</span><span class="sxs-lookup"><span data-stu-id="60126-164">**Allow diagnostic data submission**</span></span>|<span data-ttu-id="60126-165">デバイスが Microsoft に診断情報を送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-165">Enables the device to submit diagnostic information to Microsoft.</span></span>|


## <a name="cloud-settings--documents-and-data"></a><span data-ttu-id="60126-166">クラウドの設定 – ドキュメントおよびデータ</span><span class="sxs-lookup"><span data-stu-id="60126-166">Cloud settings – documents and data</span></span>

|<span data-ttu-id="60126-167">設定の名前</span><span class="sxs-lookup"><span data-stu-id="60126-167">Setting name</span></span>|<span data-ttu-id="60126-168">説明</span><span class="sxs-lookup"><span data-stu-id="60126-168">Details</span></span>|
|----------------|------|
|<span data-ttu-id="60126-169">**作業フォルダーの URL**</span><span class="sxs-lookup"><span data-stu-id="60126-169">**Work Folders URL**</span></span>|<span data-ttu-id="60126-170">作業フォルダーの URL を設定して、デバイス間でドキュメントを同期できるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-170">Sets the URL of the work folder to allow documents to be synchronized across devices.</span></span>|

## <a name="email-settings"></a><span data-ttu-id="60126-171">電子メールの設定</span><span class="sxs-lookup"><span data-stu-id="60126-171">Email settings</span></span>

|<span data-ttu-id="60126-172">設定の名前</span><span class="sxs-lookup"><span data-stu-id="60126-172">Setting name</span></span>|<span data-ttu-id="60126-173">説明</span><span class="sxs-lookup"><span data-stu-id="60126-173">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="60126-174">**Windows メール アプリケーションで Microsoft アカウントをオプションにする**</span><span class="sxs-lookup"><span data-stu-id="60126-174">**Make Microsoft account optional in Windows Mail application**</span></span>|<span data-ttu-id="60126-175">Microsoft アカウントを使用せずに Windows メール アプリケーションにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-175">Enables access to the Windows Mail application without a Microsoft account.</span></span>|

## <a name="application-settings---browser"></a><span data-ttu-id="60126-176">アプリケーションの設定 - ブラウザー</span><span class="sxs-lookup"><span data-stu-id="60126-176">Application settings - browser</span></span>

|<span data-ttu-id="60126-177">設定の名前</span><span class="sxs-lookup"><span data-stu-id="60126-177">Setting name</span></span>|<span data-ttu-id="60126-178">説明</span><span class="sxs-lookup"><span data-stu-id="60126-178">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="60126-179">**オートコンプリートを使用する**</span><span class="sxs-lookup"><span data-stu-id="60126-179">**Allow autofill**</span></span>|<span data-ttu-id="60126-180">ユーザーがブラウザーのオートコンプリートの設定を変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-180">Enables users to change autocomplete settings in the browser.</span></span>|
|<span data-ttu-id="60126-181">**ポップアップ ブロックを使用する**</span><span class="sxs-lookup"><span data-stu-id="60126-181">**Allow pop-up blocker**</span></span>|<span data-ttu-id="60126-182">ブラウザーのポップアップ ブロックを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="60126-182">Enables or disables the browser pop-up blocker.</span></span>|
|<span data-ttu-id="60126-183">**プラグインを使用する**</span><span class="sxs-lookup"><span data-stu-id="60126-183">**Allow plug-ins**</span></span>|<span data-ttu-id="60126-184">ユーザーが Internet Explorer にプラグインを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-184">Enables users to add plug-ins to Internet Explorer.</span></span>|
|<span data-ttu-id="60126-185">**アクティブ スクリプティングを使用する**</span><span class="sxs-lookup"><span data-stu-id="60126-185">**Allow active scripting**</span></span>|<span data-ttu-id="60126-186">ブラウザーで Active X スクリプトなどのスクリプトを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-186">Enables the browser to run scripts, such as Active X scripts.</span></span>|
|<span data-ttu-id="60126-187">**不正行為の警告を使用する**</span><span class="sxs-lookup"><span data-stu-id="60126-187">**Allow fraud warning**</span></span>|<span data-ttu-id="60126-188">詐欺目的の疑いがある Web サイトの警告を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="60126-188">Enables or disables warnings for potential fraudulent websites.</span></span>|
|<span data-ttu-id="60126-189">**1 単語の入力でイントラネット サイトにアクセスできるようにする**</span><span class="sxs-lookup"><span data-stu-id="60126-189">**Allow intranet site for single word entry**</span></span>|<span data-ttu-id="60126-190">Bing など、1 つの単語を使用して Internet Explorer に移動先の Web サイトを指示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-190">Enables use of a single word to direct Internet Explorer to a web site, such as Bing.</span></span>|
|<span data-ttu-id="60126-191">**イントラネット ネットワークの自動検出を使用する**</span><span class="sxs-lookup"><span data-stu-id="60126-191">**Allow automatic detection of intranet network**</span></span>|<span data-ttu-id="60126-192">Internet Explorer でイントラネット サイト用にセキュリティを構成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-192">Helps configure security for intranet sites in Internet Explorer.</span></span>|
|<span data-ttu-id="60126-193">**インターネットのセキュリティ レベル**</span><span class="sxs-lookup"><span data-stu-id="60126-193">**Security level for Internet**</span></span>|<span data-ttu-id="60126-194">インターネット サイトに使用する Internet Explorer のセキュリティ レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="60126-194">Sets the Internet Explorer security level for Internet sites.</span></span>|
|<span data-ttu-id="60126-195">**イントラネットのセキュリティ レベル**</span><span class="sxs-lookup"><span data-stu-id="60126-195">**Security level for intranet**</span></span>|<span data-ttu-id="60126-196">イントラネット サイトに使用する Internet Explorer のセキュリティ レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="60126-196">Sets the Internet Explorer security level for intranet sites.</span></span>|
|<span data-ttu-id="60126-197">**信頼済みサイトのセキュリティ レベル**</span><span class="sxs-lookup"><span data-stu-id="60126-197">**Security level for trusted sites**</span></span>|<span data-ttu-id="60126-198">信頼済みサイト ゾーンのセキュリティ レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="60126-198">Configures the security level for the trusted sites zone.</span></span>|
|<span data-ttu-id="60126-199">**制限付きサイトのセキュリティ レベル**</span><span class="sxs-lookup"><span data-stu-id="60126-199">**Security level for restricted sites**</span></span>|<span data-ttu-id="60126-200">制限付きサイト ゾーンのセキュリティ レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="60126-200">Configures the security level for the restricted sites zone.</span></span>|
|<span data-ttu-id="60126-201">**Do Not Track ヘッダーを送信する**</span><span class="sxs-lookup"><span data-stu-id="60126-201">**Send Do Not Track header**</span></span>|<span data-ttu-id="60126-202">Internet Explorer で、訪問したサイトに Do Not Track ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="60126-202">Sends  a do not track header to visited sites in Internet Explorer.</span></span>|
|<span data-ttu-id="60126-203">**エンタープライズ モード メニューへのアクセスを許可する**</span><span class="sxs-lookup"><span data-stu-id="60126-203">**Allow Enterprise Mode menu access**</span></span>|<span data-ttu-id="60126-204">Internet Explorer からエンタープライズ モード メニュー オプションへのアクセスをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="60126-204">Lets users access the Enterprise Mode menu options from Internet Explorer.</span></span><br><span data-ttu-id="60126-205">この設定を選択した場合は、さらに **[ログ レポートの場所]** を指定できます。これは、エンタープライズ モード アクセスが有効にされた Web サイトの記録となるレポートの URL を表します。</span><span class="sxs-lookup"><span data-stu-id="60126-205">If you select this setting, you can also specify a **Logging report location**, which contains a URL to a report that shows websites for which users have turned on Enterprise Mode access.</span></span>|
|<span data-ttu-id="60126-206">**エンタープライズ モード サイト リストの場所**</span><span class="sxs-lookup"><span data-stu-id="60126-206">**Enterprise Mode site list location**</span></span>|<span data-ttu-id="60126-207">エンタープライズ モードがアクティブな場合に、エンタープライズ モードを使用する Web サイトの一覧の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="60126-207">Specifies the location of the list of websites that will use Enterprise Mode when it is active.</span></span>|

## <a name="device-capabilities-settings---cellular"></a><span data-ttu-id="60126-208">デバイス機能の設定 - 移動体通信</span><span class="sxs-lookup"><span data-stu-id="60126-208">Device capabilities settings - cellular</span></span>

|<span data-ttu-id="60126-209">設定の名前</span><span class="sxs-lookup"><span data-stu-id="60126-209">Setting name</span></span>|<span data-ttu-id="60126-210">説明</span><span class="sxs-lookup"><span data-stu-id="60126-210">Details</span></span>|
|----------------|----|
|<span data-ttu-id="60126-211">**データ ローミングを許可する**</span><span class="sxs-lookup"><span data-stu-id="60126-211">**Allow data roaming**</span></span>|<span data-ttu-id="60126-212">デバイスが移動体通信ネットワーク上にある場合はデータ ローミングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="60126-212">Enables data roaming when the device is on a cellular network.</span></span>|



### <a name="see-also"></a><span data-ttu-id="60126-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="60126-213">See also</span></span>
[<span data-ttu-id="60126-214">Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する</span><span class="sxs-lookup"><span data-stu-id="60126-214">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
