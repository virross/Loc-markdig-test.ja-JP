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
ms.openlocfilehash: ccd5bd201de59537dbf99ea9e19d84dbf80c1a20
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="windows-policy-settings-in-microsoft-intune"></a><span data-ttu-id="ed5ae-103">Microsoft Intune の Windows ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="ed5ae-103">Windows policy settings in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ed5ae-104">Microsoft Intune の **Windows 全般構成ポリシー (Windows 8.1 以降)** を使用して、登録済みの Windows 8、Windows 8.1、および Windows RT 8.1 デバイスの以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-104">Use the Microsoft Intune **Windows general configuration policy (Windows 8.1 and later)** to configure the following settings for enrolled Windows 8, Windows 8.1, and Windows RT 8.1 devices:</span></span>

## <a name="applicability-settings"></a><span data-ttu-id="ed5ae-105">適用性の設定</span><span class="sxs-lookup"><span data-stu-id="ed5ae-105">Applicability settings</span></span>

|<span data-ttu-id="ed5ae-106">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ed5ae-106">Setting name</span></span>|<span data-ttu-id="ed5ae-107">説明</span><span class="sxs-lookup"><span data-stu-id="ed5ae-107">Details</span></span>|
|----------------|----------------------------------|
|<span data-ttu-id="ed5ae-108">**Windows 10 にすべての構成を適用する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-108">**Apply all configurations to Windows 10**</span></span>|<span data-ttu-id="ed5ae-109">Windows 8、および Windows 8.1 デバイスに加え、Windows 10 デバイスに、このポリシーの設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-109">Enables settings in this policy to be applied to Windows 10 devices, in addition to Windows 8 and Windows 8.1 devices.</span></span>|

## <a name="security-settings"></a><span data-ttu-id="ed5ae-110">セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="ed5ae-110">Security settings</span></span>

|<span data-ttu-id="ed5ae-111">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ed5ae-111">Setting name</span></span>|<span data-ttu-id="ed5ae-112">説明</span><span class="sxs-lookup"><span data-stu-id="ed5ae-112">Details</span></span>|
|----------------|------|
|<span data-ttu-id="ed5ae-113">**必要なパスワードの種類**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-113">**Required password type**</span></span>|<span data-ttu-id="ed5ae-114">英数字や数値のみなど、必要なパスワードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-114">Specifies the type of password that's required, such as alphanumeric or numeric only.</span></span>|
|<span data-ttu-id="ed5ae-115">**必要なパスワードの種類 - 文字セットの最小数**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-115">**Required password type – Minimum number of character sets**</span></span>|<span data-ttu-id="ed5ae-116">パスワードに含める必要がある文字セットの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-116">Specifies how many different character sets must be included in the password.</span></span> <span data-ttu-id="ed5ae-117">文字セットには、小文字、大文字、数字、および記号の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-117">There are four character sets: lowercase letters, uppercase letters, numbers, and symbols.</span></span> <span data-ttu-id="ed5ae-118">ただし、iOS デバイスの場合は、この設定でパスワードに含める必要がある記号の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-118">However, for iOS devices, this setting specifies the number of symbols that must be included in the password.</span></span>|
|<span data-ttu-id="ed5ae-119">**最小のパスワードの長さ**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-119">**Minimum password length**</span></span>|<span data-ttu-id="ed5ae-120">パスワードに必要な最小の長さ (文字数) を構成します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-120">Configures the minimum required length (in characters) for the password.</span></span>|
|<span data-ttu-id="ed5ae-121">**デバイスをワイプするまでの連続サインイン エラーの数**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-121">**Number of repeated sign-in failures to allow before the device is wiped**</span></span>|<span data-ttu-id="ed5ae-122">サインインの試みがこの回数だけ失敗した場合は、デバイスがワイプされます。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-122">Wipes the device if the sign-in attempts fail this number of times.</span></span>|
|<span data-ttu-id="ed5ae-123">**画面がオフになるまでの非アクティブな時間 (分)**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-123">**Minutes of inactivity before screen turns off**</span></span>|<span data-ttu-id="ed5ae-124">デバイスのアイドル状態が許容される時間 (分) を指定します。この時間を超えると、ロックを解除するためにパスワードが必要となります。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-124">Specifies the number of minutes a device must be idle before a password is required to unlock it.</span></span>|
|<span data-ttu-id="ed5ae-125">**パスワードの有効期限 (日)**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-125">**Password expiration (days)**</span></span>|<span data-ttu-id="ed5ae-126">デバイスのパスワードの変更が必要になるまでの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-126">Specifies the number of days before the device password must be changed.</span></span>|
|<span data-ttu-id="ed5ae-127">**パスワードの履歴を記憶する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-127">**Remember password history**</span></span>|<span data-ttu-id="ed5ae-128">過去に使用したパスワードをユーザーが構成できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-128">Specifies whether the user can configure previously used passwords.</span></span>|
|<span data-ttu-id="ed5ae-129">**パスワードの履歴を保存する** - **前のパスワードを再利用できないようにする**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-129">**Remember password history** – **Prevent reuse of previous passwords**</span></span>|<span data-ttu-id="ed5ae-130">デバイスで記憶される、以前に使用したパスワードの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-130">Specifies the number of previously used passwords that are remembered by the device.</span></span>|
|<span data-ttu-id="ed5ae-131">**ピクチャ パスワードと PIN を許可する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-131">**Allow picture password and PIN**</span></span>|<span data-ttu-id="ed5ae-132">ピクチャ パスワードと PIN を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-132">Enables the use of a picture password and PIN.</span></span> <span data-ttu-id="ed5ae-133">ピクチャ パスワードが許可されている場合、ユーザーは画像に対するジェスチャーでサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-133">A picture password lets the user sign in with gestures on a picture.</span></span> <span data-ttu-id="ed5ae-134">PIN が許可されている場合、ユーザーは 4 桁のコードを使用してすばやくサインインできます。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-134">A PIN lets users quickly sign in with a four-digit code.</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="ed5ae-135">暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="ed5ae-135">Encryption settings</span></span>

|                           <span data-ttu-id="ed5ae-136">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ed5ae-136">Setting name</span></span>                           |                     <span data-ttu-id="ed5ae-137">説明</span><span class="sxs-lookup"><span data-stu-id="ed5ae-137">Details</span></span>                      |
|------------------------------------------------------------------|--------------------------------------------------|
| <span data-ttu-id="ed5ae-138"><strong>モバイル デバイスの暗号化を要求する</strong><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ed5ae-138"><strong>Require encryption on mobile device</strong><sup>1</sup></span></span> | <span data-ttu-id="ed5ae-139">デバイス上のファイルを必ず暗号化するようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-139">Requires that files on the device are encrypted.</span></span> |

<span data-ttu-id="ed5ae-140"><sup>1</sup> Windows 8.1 が実行されているデバイスの追加情報</span><span class="sxs-lookup"><span data-stu-id="ed5ae-140"><sup>1</sup> Additional information for devices that run Windows 8.1</span></span>

-   <span data-ttu-id="ed5ae-141">Windows 8.1 が実行されているデバイスで暗号化を適用するには、 [Windows の 2014 年 12 月付け MDM クライアント更新プログラム](http://support.microsoft.com/kb/3013816) を各デバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-141">To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.</span></span>

-   <span data-ttu-id="ed5ae-142">Windows 8.1 デバイスに対してこの設定を有効にすると、デバイスのすべてのユーザーに Microsoft アカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-142">If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.</span></span>

-   <span data-ttu-id="ed5ae-143">暗号化を機能させるには、デバイスが Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) ハードウェア認定要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-143">For encryption to work, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.</span></span>

-   <span data-ttu-id="ed5ae-144">デバイスで暗号化を適用すると、回復キーは、ユーザーの Microsoft アカウントからしかアクセスできなくなります。また、OneDrive アカウントからアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-144">When you enforce encryption on a device, the recovery key is only accessible from the user's Microsoft account, which is accessed from their OneDrive account.</span></span> <span data-ttu-id="ed5ae-145">ユーザーの代わりにこのキーを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-145">You cannot recover this key on behalf of a user.</span></span>

## <a name="malware-settings"></a><span data-ttu-id="ed5ae-146">マルウェアの設定</span><span class="sxs-lookup"><span data-stu-id="ed5ae-146">Malware settings</span></span>

|<span data-ttu-id="ed5ae-147">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ed5ae-147">Setting name</span></span>|<span data-ttu-id="ed5ae-148">説明</span><span class="sxs-lookup"><span data-stu-id="ed5ae-148">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="ed5ae-149">**ネットワーク ファイアウォールを必須にする**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-149">**Require network firewall**</span></span>|<span data-ttu-id="ed5ae-150">Windows ファイアウォールを有効にすることを要求します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-150">Requires that the Windows Firewall is turned on.</span></span>|
|<span data-ttu-id="ed5ae-151">**SmartScreen を有効にする**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-151">**Enable SmartScreen**</span></span>|<span data-ttu-id="ed5ae-152">Windows SmartScreen の使用を必須とします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-152">Requires the use of Windows SmartScreen.</span></span>|

## <a name="system-settings"></a><span data-ttu-id="ed5ae-153">システムの設定</span><span class="sxs-lookup"><span data-stu-id="ed5ae-153">System settings</span></span>

|<span data-ttu-id="ed5ae-154">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ed5ae-154">Setting name</span></span>|<span data-ttu-id="ed5ae-155">説明</span><span class="sxs-lookup"><span data-stu-id="ed5ae-155">Details</span></span>|
|----------------|-------|
|<span data-ttu-id="ed5ae-156">**自動更新を必須にする**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-156">**Require automatic updates**</span></span>|<span data-ttu-id="ed5ae-157">デバイス上の自動更新設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-157">Turns on the automatic updates setting on devices.</span></span>|
|<span data-ttu-id="ed5ae-158">**自動更新を必須にする – 自動的にインストールする更新プログラムの最低限の分類。**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-158">**Require automatic updates – Minimum classification of updates to install automatically**</span></span>|<span data-ttu-id="ed5ae-159">自動的にインストールする更新プログラムの分類を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-159">Chooses the classification of updates that will be installed automatically:</span></span><br /><br /><span data-ttu-id="ed5ae-160">-   **重要** – 重要として分類されたすべての更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-160">-   **Important** – Installs all updates that are classified as important.</span></span><br /><span data-ttu-id="ed5ae-161">-   **推奨** – 重要または推奨として分類されたすべての更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-161">-   **Recommended** – Installs all updates that are classified as important or recommended.</span></span>|
|<span data-ttu-id="ed5ae-162">**ユーザー アカウント コントロール**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-162">**User Account Control**</span></span>|<span data-ttu-id="ed5ae-163">デバイス上のユーザー アカウント制御 (UAC) の使用を必須とします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-163">Requires the use of User Account Control (UAC) on devices.</span></span>|
|<span data-ttu-id="ed5ae-164">**診断データの送信を使用する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-164">**Allow diagnostic data submission**</span></span>|<span data-ttu-id="ed5ae-165">デバイスが Microsoft に診断情報を送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-165">Enables the device to submit diagnostic information to Microsoft.</span></span>|


## <a name="cloud-settings--documents-and-data"></a><span data-ttu-id="ed5ae-166">クラウドの設定 – ドキュメントおよびデータ</span><span class="sxs-lookup"><span data-stu-id="ed5ae-166">Cloud settings – documents and data</span></span>

|<span data-ttu-id="ed5ae-167">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ed5ae-167">Setting name</span></span>|<span data-ttu-id="ed5ae-168">説明</span><span class="sxs-lookup"><span data-stu-id="ed5ae-168">Details</span></span>|
|----------------|------|
|<span data-ttu-id="ed5ae-169">**作業フォルダーの URL**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-169">**Work Folders URL**</span></span>|<span data-ttu-id="ed5ae-170">作業フォルダーの URL を設定して、デバイス間でドキュメントを同期できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-170">Sets the URL of the work folder to allow documents to be synchronized across devices.</span></span>|

## <a name="email-settings"></a><span data-ttu-id="ed5ae-171">電子メールの設定</span><span class="sxs-lookup"><span data-stu-id="ed5ae-171">Email settings</span></span>

|<span data-ttu-id="ed5ae-172">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ed5ae-172">Setting name</span></span>|<span data-ttu-id="ed5ae-173">説明</span><span class="sxs-lookup"><span data-stu-id="ed5ae-173">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="ed5ae-174">**Windows メール アプリケーションで Microsoft アカウントをオプションにする**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-174">**Make Microsoft account optional in Windows Mail application**</span></span>|<span data-ttu-id="ed5ae-175">Microsoft アカウントを使用せずに Windows メール アプリケーションにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-175">Enables access to the Windows Mail application without a Microsoft account.</span></span>|

## <a name="application-settings---browser"></a><span data-ttu-id="ed5ae-176">アプリケーションの設定 - ブラウザー</span><span class="sxs-lookup"><span data-stu-id="ed5ae-176">Application settings - browser</span></span>

|<span data-ttu-id="ed5ae-177">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ed5ae-177">Setting name</span></span>|<span data-ttu-id="ed5ae-178">説明</span><span class="sxs-lookup"><span data-stu-id="ed5ae-178">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="ed5ae-179">**オートコンプリートを使用する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-179">**Allow autofill**</span></span>|<span data-ttu-id="ed5ae-180">ユーザーがブラウザーのオートコンプリートの設定を変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-180">Enables users to change autocomplete settings in the browser.</span></span>|
|<span data-ttu-id="ed5ae-181">**ポップアップ ブロックを使用する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-181">**Allow pop-up blocker**</span></span>|<span data-ttu-id="ed5ae-182">ブラウザーのポップアップ ブロックを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-182">Enables or disables the browser pop-up blocker.</span></span>|
|<span data-ttu-id="ed5ae-183">**プラグインを使用する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-183">**Allow plug-ins**</span></span>|<span data-ttu-id="ed5ae-184">ユーザーが Internet Explorer にプラグインを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-184">Enables users to add plug-ins to Internet Explorer.</span></span>|
|<span data-ttu-id="ed5ae-185">**アクティブ スクリプティングを使用する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-185">**Allow active scripting**</span></span>|<span data-ttu-id="ed5ae-186">ブラウザーで Active X スクリプトなどのスクリプトを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-186">Enables the browser to run scripts, such as Active X scripts.</span></span>|
|<span data-ttu-id="ed5ae-187">**不正行為の警告を使用する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-187">**Allow fraud warning**</span></span>|<span data-ttu-id="ed5ae-188">詐欺目的の疑いがある Web サイトの警告を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-188">Enables or disables warnings for potential fraudulent websites.</span></span>|
|<span data-ttu-id="ed5ae-189">**1 単語の入力でイントラネット サイトにアクセスできるようにする**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-189">**Allow intranet site for single word entry**</span></span>|<span data-ttu-id="ed5ae-190">Bing など、1 つの単語を使用して Internet Explorer に移動先の Web サイトを指示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-190">Enables use of a single word to direct Internet Explorer to a web site, such as Bing.</span></span>|
|<span data-ttu-id="ed5ae-191">**イントラネット ネットワークの自動検出を使用する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-191">**Allow automatic detection of intranet network**</span></span>|<span data-ttu-id="ed5ae-192">Internet Explorer でイントラネット サイト用にセキュリティを構成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-192">Helps configure security for intranet sites in Internet Explorer.</span></span>|
|<span data-ttu-id="ed5ae-193">**インターネットのセキュリティ レベル**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-193">**Security level for Internet**</span></span>|<span data-ttu-id="ed5ae-194">インターネット サイトに使用する Internet Explorer のセキュリティ レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-194">Sets the Internet Explorer security level for Internet sites.</span></span>|
|<span data-ttu-id="ed5ae-195">**イントラネットのセキュリティ レベル**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-195">**Security level for intranet**</span></span>|<span data-ttu-id="ed5ae-196">イントラネット サイトに使用する Internet Explorer のセキュリティ レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-196">Sets the Internet Explorer security level for intranet sites.</span></span>|
|<span data-ttu-id="ed5ae-197">**信頼済みサイトのセキュリティ レベル**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-197">**Security level for trusted sites**</span></span>|<span data-ttu-id="ed5ae-198">信頼済みサイト ゾーンのセキュリティ レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-198">Configures the security level for the trusted sites zone.</span></span>|
|<span data-ttu-id="ed5ae-199">**制限付きサイトのセキュリティ レベル**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-199">**Security level for restricted sites**</span></span>|<span data-ttu-id="ed5ae-200">制限付きサイト ゾーンのセキュリティ レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-200">Configures the security level for the restricted sites zone.</span></span>|
|<span data-ttu-id="ed5ae-201">**Do Not Track ヘッダーを送信する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-201">**Send Do Not Track header**</span></span>|<span data-ttu-id="ed5ae-202">Internet Explorer で、訪問したサイトに Do Not Track ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-202">Sends  a do not track header to visited sites in Internet Explorer.</span></span>|
|<span data-ttu-id="ed5ae-203">**エンタープライズ モード メニューへのアクセスを許可する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-203">**Allow Enterprise Mode menu access**</span></span>|<span data-ttu-id="ed5ae-204">Internet Explorer からエンタープライズ モード メニュー オプションへのアクセスをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-204">Lets users access the Enterprise Mode menu options from Internet Explorer.</span></span><br><span data-ttu-id="ed5ae-205">この設定を選択した場合は、さらに **[ログ レポートの場所]** を指定できます。これは、エンタープライズ モード アクセスが有効にされた Web サイトの記録となるレポートの URL を表します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-205">If you select this setting, you can also specify a **Logging report location**, which contains a URL to a report that shows websites for which users have turned on Enterprise Mode access.</span></span>|
|<span data-ttu-id="ed5ae-206">**エンタープライズ モード サイト リストの場所**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-206">**Enterprise Mode site list location**</span></span>|<span data-ttu-id="ed5ae-207">エンタープライズ モードがアクティブな場合に、エンタープライズ モードを使用する Web サイトの一覧の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-207">Specifies the location of the list of websites that will use Enterprise Mode when it is active.</span></span>|

## <a name="device-capabilities-settings---cellular"></a><span data-ttu-id="ed5ae-208">デバイス機能の設定 - 移動体通信</span><span class="sxs-lookup"><span data-stu-id="ed5ae-208">Device capabilities settings - cellular</span></span>

|<span data-ttu-id="ed5ae-209">設定の名前</span><span class="sxs-lookup"><span data-stu-id="ed5ae-209">Setting name</span></span>|<span data-ttu-id="ed5ae-210">説明</span><span class="sxs-lookup"><span data-stu-id="ed5ae-210">Details</span></span>|
|----------------|----|
|<span data-ttu-id="ed5ae-211">**データ ローミングを許可する**</span><span class="sxs-lookup"><span data-stu-id="ed5ae-211">**Allow data roaming**</span></span>|<span data-ttu-id="ed5ae-212">デバイスが移動体通信ネットワーク上にある場合はデータ ローミングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5ae-212">Enables data roaming when the device is on a cellular network.</span></span>|



### <a name="see-also"></a><span data-ttu-id="ed5ae-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed5ae-213">See also</span></span>
[<span data-ttu-id="ed5ae-214">Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する</span><span class="sxs-lookup"><span data-stu-id="ed5ae-214">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
