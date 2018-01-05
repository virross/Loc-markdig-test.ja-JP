---
title: "Windows Phone 8.1 ポリシー設定"
description: "Intune には、Windows Phone 8.1 デバイスで構成できるさまざまな全般設定が組み込まれています。 また、OMA-URI 値を指定して、Intune にはないユーザー設定を作成できます。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 257ddad44af6a6f83303c486ec5bdb3a3f01a690
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="windows-phone-81-policy-settings-in-microsoft-intune"></a><span data-ttu-id="16be1-104">Microsoft Intune の Windows Phone 8.1 ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="16be1-104">Windows Phone 8.1 policy settings in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="16be1-105">Intune には、Windows Phone 8.1 デバイスで構成できるさまざまな全般設定が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="16be1-105">Intune supplies a range of built-in general settings that you can configure on Windows Phone 8.1 devices.</span></span> <span data-ttu-id="16be1-106">また、Open Mobile Alliance Uniform Resource Identifier (OMA-URI) 値を指定して、Intune にはないユーザー設定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="16be1-106">Additionally, you can specify Open Mobile Alliance Uniform Resource Identifier (OMA-URI) values to create custom settings that are not available from Intune.</span></span>

## <a name="general-configuration-settings"></a><span data-ttu-id="16be1-107">全般構成設定</span><span class="sxs-lookup"><span data-stu-id="16be1-107">General configuration settings</span></span>

<span data-ttu-id="16be1-108">Microsoft Intune の **Windows Phone 全般構成ポリシー (Windows Phone 8.1 以降)** を使用して、Windows Phone 8.1 デバイスに次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="16be1-108">Use the Microsoft Intune **Windows Phone general configuration policy (Windows Phone 8.1 and later)** to configure the following settings for Windows Phone 8.1 devices:</span></span>

-   <span data-ttu-id="16be1-109">**モバイル デバイスのセキュリティ設定** – デバイスのさまざまな機能を制御できる定義済みの設定の一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="16be1-109">**Mobile device security settings** – Choose from a list of predefined settings that let you control a range of features and functionality on the device.</span></span>

-   <span data-ttu-id="16be1-110">**準拠しているアプリと非準拠アプリ** - 社内の準拠アプリまたは非準拠アプリの一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-110">**Compliant and noncompliant apps** - Specify a list of apps that are compliant or not compliant in your company.</span></span> <span data-ttu-id="16be1-111">Windows Phone デバイスは、これらのアプリのインストールをブロックまたは許可することができます。</span><span class="sxs-lookup"><span data-stu-id="16be1-111">Windows Phone devices can block or allow installation of these apps.</span></span>

### <a name="applicability-settings"></a><span data-ttu-id="16be1-112">適用性の設定</span><span class="sxs-lookup"><span data-stu-id="16be1-112">Applicability settings</span></span>

|<span data-ttu-id="16be1-113">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-113">Setting name</span></span>|<span data-ttu-id="16be1-114">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-114">Details</span></span>|
|----------------|----------------------------------|
|<span data-ttu-id="16be1-115">**Windows 10 にすべての構成を適用する**</span><span class="sxs-lookup"><span data-stu-id="16be1-115">**Apply all configurations to Windows 10**</span></span>|<span data-ttu-id="16be1-116">Windows Phone 8.1 デバイスに加え、Windows 10 Mobile デバイスに、このポリシーの設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="16be1-116">Enables settings in this policy to be applied to Windows 10 Mobile devices in addition to Windows Phone 8.1 devices.</span></span>|

### <a name="password-settings"></a><span data-ttu-id="16be1-117">パスワードの設定</span><span class="sxs-lookup"><span data-stu-id="16be1-117">Password settings</span></span>

|<span data-ttu-id="16be1-118">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-118">Setting name</span></span>|<span data-ttu-id="16be1-119">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-119">Details</span></span>|
|----------------|------|
|<span data-ttu-id="16be1-120">**モバイル デバイスのロックを解除するパスワードを要求する**</span><span class="sxs-lookup"><span data-stu-id="16be1-120">**Require a password to unlock mobile devices**</span></span>|<span data-ttu-id="16be1-121">ユーザーがデバイスにアクセスする際にパスワードを入力する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-121">Specifies whether users must enter a password to access their devices.</span></span>|
|<span data-ttu-id="16be1-122">**必要なパスワードの種類**</span><span class="sxs-lookup"><span data-stu-id="16be1-122">**Required password type**</span></span>|<span data-ttu-id="16be1-123">英数字や数値のみなど、必要なパスワードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-123">Specifies the type of password that will be required, such as alphanumeric or numeric only.</span></span>|
|<span data-ttu-id="16be1-124">**必要なパスワードの種類 - 文字セットの最小数**</span><span class="sxs-lookup"><span data-stu-id="16be1-124">**Required password type – Minimum number of character sets**</span></span>|<span data-ttu-id="16be1-125">パスワードに含める必要がある文字セットの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-125">Specifies how many different character sets must be included in the password.</span></span> <span data-ttu-id="16be1-126">文字セットには、小文字、大文字、数字、および記号の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="16be1-126">There are four character sets: lowercase letters, uppercase letters, numbers, and symbols.</span></span> <span data-ttu-id="16be1-127">ただし、iOS デバイスの場合は、この設定でパスワードに含める必要がある記号の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-127">However, for iOS devices, this specifies the number of symbols that must be included in the password.</span></span>|
|<span data-ttu-id="16be1-128">**最小のパスワードの長さ**</span><span class="sxs-lookup"><span data-stu-id="16be1-128">**Minimum password length**</span></span>|<span data-ttu-id="16be1-129">パスワードに必要な最小文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-129">Specifies the minimum number of characters that are required in the password.</span></span>|
|<span data-ttu-id="16be1-130">**単純なパスワードを許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-130">**Allow simple passwords**</span></span>|<span data-ttu-id="16be1-131">"0000" や "1234" などの単純なパスワードを使用できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-131">Specifies that simple passwords such as ‘0000’ and ‘1234’ can be used.</span></span>|
|<span data-ttu-id="16be1-132">**デバイスをワイプするまでの連続サインイン エラーの数**</span><span class="sxs-lookup"><span data-stu-id="16be1-132">**Number of repeated sign-in failures to allow before the device is wiped**</span></span>|<span data-ttu-id="16be1-133">間違ったパスワードをユーザーが何回入力すると、そのデバイスをワイプするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-133">Specifies the number of times an incorrect password can be entered before the device is wiped.</span></span>|
|<span data-ttu-id="16be1-134">**画面がオフになるまでの非アクティブな時間 (分)**</span><span class="sxs-lookup"><span data-stu-id="16be1-134">**Minutes of inactivity before the screen turns off**</span></span>|<span data-ttu-id="16be1-135">デバイスがどれだけの時間アイドル状態であると、画面が自動的にロックされるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-135">Specifies the amount of time a device must remain idle before the screen is automatically locked.</span></span>|
|<span data-ttu-id="16be1-136">**パスワードの有効期限 (日)**</span><span class="sxs-lookup"><span data-stu-id="16be1-136">**Password expiration (days)**</span></span>|<span data-ttu-id="16be1-137">デバイスのパスワードの変更が必要になるまでの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-137">Specifies the number of days before the device password must be changed.</span></span>|<span data-ttu-id="16be1-138">はい</span><span class="sxs-lookup"><span data-stu-id="16be1-138">Yes</span></span>|<span data-ttu-id="16be1-139">はい</span><span class="sxs-lookup"><span data-stu-id="16be1-139">Yes</span></span>|
|<span data-ttu-id="16be1-140">**パスワードの履歴を記憶する**</span><span class="sxs-lookup"><span data-stu-id="16be1-140">**Remember password history**</span></span>|<span data-ttu-id="16be1-141">ユーザーが同じパスワードを再度使用できないよう、過去に使用されたパスワードを記憶するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-141">Specifies whether previously used passwords are remembered to prevent the user from using them again.</span></span>|
|<span data-ttu-id="16be1-142">**パスワードの履歴を保存する** - **前のパスワードを再利用できないようにする**</span><span class="sxs-lookup"><span data-stu-id="16be1-142">**Remember password history** – **Prevent reuse of previous passwords**</span></span>|<span data-ttu-id="16be1-143">過去に使用されたパスワードの記憶件数を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-143">Specifies how many previously used passwords are remembered.</span></span>|

### <a name="encryption-settings"></a><span data-ttu-id="16be1-144">暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="16be1-144">Encryption settings</span></span>

|<span data-ttu-id="16be1-145">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-145">Setting name</span></span>|<span data-ttu-id="16be1-146">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-146">Details</span></span>|
|----------------|------|
|<span data-ttu-id="16be1-147">**モバイル デバイスの暗号化を要求する**</span><span class="sxs-lookup"><span data-stu-id="16be1-147">**Require encryption on mobile device**</span></span>|<span data-ttu-id="16be1-148">サポートされているモバイル デバイス上のデータの暗号化を要求します。</span><span class="sxs-lookup"><span data-stu-id="16be1-148">Requires that the data on supported mobile devices be encrypted.</span></span>|

### <a name="system-settings"></a><span data-ttu-id="16be1-149">システムの設定</span><span class="sxs-lookup"><span data-stu-id="16be1-149">System settings</span></span>

|<span data-ttu-id="16be1-150">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-150">Setting name</span></span>|<span data-ttu-id="16be1-151">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-151">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="16be1-152">**画面のキャプチャを許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-152">**Allow screen capture**</span></span>|<span data-ttu-id="16be1-153">ユーザーが画面のコンテンツを画像ファイルとしてキャプチャできるようにします。</span><span class="sxs-lookup"><span data-stu-id="16be1-153">Lets the user capture the contents of the screen as an image file.</span></span>|
|<span data-ttu-id="16be1-154">**診断データの送信を使用する**</span><span class="sxs-lookup"><span data-stu-id="16be1-154">**Allow diagnostic data submission**</span></span>|<span data-ttu-id="16be1-155">デバイスが Microsoft に診断情報を送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="16be1-155">Enables the device to submit diagnostic information to Microsoft.</span></span>|

### <a name="cloud-settings--accounts-and-synchronization"></a><span data-ttu-id="16be1-156">クラウドの設定 – アカウントおよび同期</span><span class="sxs-lookup"><span data-stu-id="16be1-156">Cloud settings – accounts and synchronization</span></span>

|<span data-ttu-id="16be1-157">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-157">Setting name</span></span>|<span data-ttu-id="16be1-158">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-158">Details</span></span>|
|----------------|------|
|<span data-ttu-id="16be1-159">**Microsoft アカウントを許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-159">**Allow Microsoft account**</span></span>|<span data-ttu-id="16be1-160">Microsoft アカウントをデバイスにリンクできるようにします。</span><span class="sxs-lookup"><span data-stu-id="16be1-160">Enables a Microsoft account to be linked to the device.</span></span>|

### <a name="email-settings"></a><span data-ttu-id="16be1-161">電子メールの設定</span><span class="sxs-lookup"><span data-stu-id="16be1-161">Email settings</span></span>

|<span data-ttu-id="16be1-162">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-162">Setting name</span></span>|<span data-ttu-id="16be1-163">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-163">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="16be1-164">**カスタム電子メール アカウントを許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-164">**Allow custom email accounts**</span></span>|<span data-ttu-id="16be1-165">Microsoft 以外の電子メール アカウントにデバイスが接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="16be1-165">Enables the device to connect to non-Microsoft email accounts.</span></span>|

### <a name="application-settings---browser"></a><span data-ttu-id="16be1-166">アプリケーションの設定 - ブラウザー</span><span class="sxs-lookup"><span data-stu-id="16be1-166">Application settings - browser</span></span>

|<span data-ttu-id="16be1-167">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-167">Setting name</span></span>|<span data-ttu-id="16be1-168">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-168">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="16be1-169">**Web ブラウザーを許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-169">**Allow web browser**</span></span>|<span data-ttu-id="16be1-170">デバイス上の組み込みの Web ブラウザーを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="16be1-170">Enables or blocks the built-in web browser on devices.</span></span>|

### <a name="application-settings---apps"></a><span data-ttu-id="16be1-171">アプリケーションの設定 - アプリケーション</span><span class="sxs-lookup"><span data-stu-id="16be1-171">Application settings - apps</span></span>

|<span data-ttu-id="16be1-172">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-172">Setting name</span></span>|<span data-ttu-id="16be1-173">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-173">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="16be1-174">**アプリケーション ストアを許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-174">**Allow application store**</span></span>|<span data-ttu-id="16be1-175">デバイスからアプリ ストアへの接続をユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="16be1-175">Lets users connect to the app store from the device.</span></span>|

### <a name="device-capabilities-settings---hardware"></a><span data-ttu-id="16be1-176">デバイス機能の設定 - ハードウェア</span><span class="sxs-lookup"><span data-stu-id="16be1-176">Device capabilities settings - hardware</span></span>

|<span data-ttu-id="16be1-177">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-177">Setting name</span></span>|<span data-ttu-id="16be1-178">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-178">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="16be1-179">**カメラを許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-179">**Allow camera**</span></span>|<span data-ttu-id="16be1-180">デバイスのカメラを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="16be1-180">Enables or blocks the device's camera.</span></span>|
|<span data-ttu-id="16be1-181">**リムーバブル記憶域を許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-181">**Allow removable storage**</span></span>|<span data-ttu-id="16be1-182">リムーバブル記憶域 (SD カードなど) の使用をデバイスに許可します。</span><span class="sxs-lookup"><span data-stu-id="16be1-182">Lets the device use removable storage such as SD cards.</span></span>|
|<span data-ttu-id="16be1-183">**Wi-Fi を許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-183">**Allow Wi-Fi**</span></span>|<span data-ttu-id="16be1-184">デバイスの Wi-Fi 機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="16be1-184">Enables or disables the Wi-Fi functionality of the device.</span></span>|
|<span data-ttu-id="16be1-185">**Wi-Fi テザリングを許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-185">**Allow Wi-Fi tethering**</span></span>|<span data-ttu-id="16be1-186">デバイスで Wi-Fi テザリングを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="16be1-186">Enables the use of Wi-Fi tethering on the device.</span></span>|
|<span data-ttu-id="16be1-187">**無料 Wi-Fi スポットへの自動接続を許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-187">**Allow automatic connection to free Wi-Fi hotspots**</span></span>|<span data-ttu-id="16be1-188">無料の Wi-Fi ホットスポットに自動的に接続し、使用条件に自動的に同意することをデバイスに許可します。</span><span class="sxs-lookup"><span data-stu-id="16be1-188">Enables the device to automatically connect to free Wi-Fi hotspots and automatically accept any terms of use.</span></span>|
|<span data-ttu-id="16be1-189">**Wi-Fi スポットの報告を許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-189">**Allow Wi-Fi hotspot reporting**</span></span>|<span data-ttu-id="16be1-190">ユーザーが近くにある接続を検出するのに役立つ、Wi-Fi 接続に関する情報を送信します。</span><span class="sxs-lookup"><span data-stu-id="16be1-190">Sends information about Wi-Fi connections to help the user discover nearby connections.</span></span>|
|<span data-ttu-id="16be1-191">**位置情報を許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-191">**Allow geolocation**</span></span>|<span data-ttu-id="16be1-192">デバイスで位置情報を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="16be1-192">Enables the device to utilize location information.</span></span>|
|<span data-ttu-id="16be1-193">**NFC を許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-193">**Allow NFC**</span></span>|<span data-ttu-id="16be1-194">近距離無線通信を使用する操作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="16be1-194">Enables operations that use near field communication.</span></span>|
|<span data-ttu-id="16be1-195">**Bluetooth を許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-195">**Allow Bluetooth**</span></span>|<span data-ttu-id="16be1-196">デバイスの Bluetooth 機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="16be1-196">Enables or disables the Bluetooth functionality of the device.</span></span>|

### <a name="device-capabilities-settings---features"></a><span data-ttu-id="16be1-197">デバイス機能の設定 - 機能</span><span class="sxs-lookup"><span data-stu-id="16be1-197">Device capabilities settings - features</span></span>

|<span data-ttu-id="16be1-198">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-198">Setting name</span></span>|<span data-ttu-id="16be1-199">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-199">Details</span></span>|
|----------------|----|
|<span data-ttu-id="16be1-200">**コピーと貼り付けを許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-200">**Allow copy and paste**</span></span>|<span data-ttu-id="16be1-201">デバイスでコピー/貼り付け機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="16be1-201">Enables copy and paste functionality on devices.</span></span>|

### <a name="settings-for-allowed-and-blocked-apps"></a><span data-ttu-id="16be1-202">許可されるアプリとブロックされるアプリの設定</span><span class="sxs-lookup"><span data-stu-id="16be1-202">Settings for allowed and blocked apps</span></span>
<span data-ttu-id="16be1-203">**許可されているアプリとブロックされているアプリ**の一覧で、次の情報を使用して許可またはブロックするアプリの一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-203">In the **Allowed and blocked apps** list, specify a list of apps that you want to allow or block by using the following information:</span></span>

> [!NOTE]
> <span data-ttu-id="16be1-204">1 つのポリシーでは、許可するアプリの一覧のみ、またはブロックするアプリの一覧のみを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="16be1-204">A single policy can only contain a list of allowed or blocked apps.</span></span> <span data-ttu-id="16be1-205">両方を同じポリシーに指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="16be1-205">You cannot specify both in the same policy.</span></span>

|<span data-ttu-id="16be1-206">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-206">Setting name</span></span>|<span data-ttu-id="16be1-207">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-207">Details</span></span>|
|----------------|--------------------|
|<span data-ttu-id="16be1-208">**一覧に表示されているアプリをデバイスが開く操作をブロックする**</span><span class="sxs-lookup"><span data-stu-id="16be1-208">**Block devices from opening the listed apps**</span></span>|<span data-ttu-id="16be1-209">ユーザーによるインストールと実行が許可されていない、Intune で管理していないアプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="16be1-209">Lists the apps that are not managed by Intune, and which users are not allowed to install and run.</span></span>|
|<span data-ttu-id="16be1-210">**一覧に表示されているアプリのみインストールすることをデバイスに許可する**</span><span class="sxs-lookup"><span data-stu-id="16be1-210">**Allow devices to install only the listed apps**</span></span>|<span data-ttu-id="16be1-211">ユーザーによるインストールが許可されているアプリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="16be1-211">Lists the apps that users are allowed to install.</span></span> <span data-ttu-id="16be1-212">ユーザーはその他のアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="16be1-212">Users cannot install any other apps.</span></span> <span data-ttu-id="16be1-213">管理対象アプリは Intune で自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="16be1-213">Apps that are managed by Intune are automatically allowed.</span></span>|
|<span data-ttu-id="16be1-214">**[追加]**</span><span class="sxs-lookup"><span data-stu-id="16be1-214">**Add**</span></span>|<span data-ttu-id="16be1-215">選択した一覧にアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="16be1-215">Adds an app to the selected list.</span></span> <span data-ttu-id="16be1-216">選択した名前、App Store でのアプリの URL、アプリの発行元 (省略可能) を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-216">Specify a name of your choice, the URL to the app in the app store, and the app publisher (optional).</span></span> <span data-ttu-id="16be1-217">詳細については、このトピックで後述する「アプリ ストアの URL を指定する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16be1-217">For more help, see How to specify URLs to app stores later in this topic.</span></span>
|<span data-ttu-id="16be1-218">**アプリをインポートする**</span><span class="sxs-lookup"><span data-stu-id="16be1-218">**Import Apps**</span></span>|<span data-ttu-id="16be1-219">コンマ区切り値ファイルで指定したアプリの一覧をインポートします。</span><span class="sxs-lookup"><span data-stu-id="16be1-219">Imports a list of apps that you have specified in a comma-separated values file.</span></span> <span data-ttu-id="16be1-220">ファイルの形式、アプリケーション名、発行者、およびアプリの URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="16be1-220">Use the format, application name, publisher, and app URL in the file.</span></span>|
|<span data-ttu-id="16be1-221">**編集**</span><span class="sxs-lookup"><span data-stu-id="16be1-221">**Edit**</span></span>|<span data-ttu-id="16be1-222">選択したアプリの名前、発行者、および URL を編集します。</span><span class="sxs-lookup"><span data-stu-id="16be1-222">Lets you edit the name, publisher, and URL of the selected app.</span></span>|
|<span data-ttu-id="16be1-223">**削除**</span><span class="sxs-lookup"><span data-stu-id="16be1-223">**Delete**</span></span>|<span data-ttu-id="16be1-224">選択したアプリを一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="16be1-224">Deletes the selected app from the list.</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="16be1-225">Windows Phone 8.1 のデバイス向けに許可されているアプリの一覧を指定する場合、この一覧にポータル サイトのアプリを追加する必要があります。追加しない場合はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="16be1-225">If you specify a list of allowed apps for Windows Phone 8.1 devices, you must add the Company Portal app to this list or it will be blocked.</span></span>


### <a name="reference-information-for-allowed-and-blocked-apps"></a><span data-ttu-id="16be1-226">許可されるアプリとブロックされるアプリのリファレンス情報</span><span class="sxs-lookup"><span data-stu-id="16be1-226">Reference information for allowed and blocked apps</span></span>

#### <a name="how-to-specify-urls-to-app-stores"></a><span data-ttu-id="16be1-227">アプリ ストアの URL を指定する方法</span><span class="sxs-lookup"><span data-stu-id="16be1-227">How to specify URLs to app stores</span></span>
<span data-ttu-id="16be1-228">許可されるアプリおよびブロックされるアプリの一覧でアプリの URL を指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="16be1-228">To specify an app URL in the allowed and blocked apps list, use the following format:</span></span>

<span data-ttu-id="16be1-229">[Windows Phone アプリ+ゲーム](http://www.windowsphone.com/store/overview)のページで、使用するアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="16be1-229">From the [Windows Phone Apps+Games](http://www.windowsphone.com/store/overview) page, search for the app that you want to use.</span></span>

<span data-ttu-id="16be1-230">アプリのページを開き、URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="16be1-230">Open the app’s page, and copy the URL to the clipboard.</span></span> <span data-ttu-id="16be1-231">許可されているアプリまたはブロックされているアプリの一覧で、これを URL として使用できます。</span><span class="sxs-lookup"><span data-stu-id="16be1-231">You can now use this as the URL in either the allowed or blocked apps list.</span></span>

<span data-ttu-id="16be1-232">**例:** Skype アプリのストアを検索します。</span><span class="sxs-lookup"><span data-stu-id="16be1-232">**Example:** Search the store for the Skype app.</span></span> <span data-ttu-id="16be1-233">**http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51** という URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="16be1-233">The URL you use will be **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.</span></span>

## <a name="custom-policy-settings"></a><span data-ttu-id="16be1-234">カスタム ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="16be1-234">Custom policy settings</span></span>
<span data-ttu-id="16be1-235">Microsoft Intune **Windows Phone カスタム構成ポリシー**を使用して、**Windows Phone 8.1 デバイス**で各機能の制御に使用できる OMA-URI 設定を展開します。</span><span class="sxs-lookup"><span data-stu-id="16be1-235">Use the Microsoft Intune **Windows Phone custom configuration policy** to deploy OMA-URI settings that can be used to control features on **Windows Phone 8.1 devices**.</span></span> <span data-ttu-id="16be1-236">これらの設定は、多くのデバイス製造元がデバイスの機能を制御するために使用する標準の設定です。</span><span class="sxs-lookup"><span data-stu-id="16be1-236">These are standard settings that many mobile device manufacturers use to control device features.</span></span>

<span data-ttu-id="16be1-237">この機能は、Intune 全般構成ポリシーで構成できない Windows Phone 設定を展開できるようにします。</span><span class="sxs-lookup"><span data-stu-id="16be1-237">This capability enables you to deploy Windows Phone settings that are not configurable with an Intune general configuration policy.</span></span> <span data-ttu-id="16be1-238">これらのポリシーで構成できる設定については、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16be1-238">For information about the settings you can configure with these policies, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

<span data-ttu-id="16be1-239">Windows Phone デバイスの OMA-URI 設定の作成については、[Windows Phone 8.1 の MDM プロトコルのドキュメント](http://technet.microsoft.com/library/dn499787.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16be1-239">For help creating OMA-URI settings for Windows Phone devices, see [Windows Phone 8.1 MDM protocol documentation](http://technet.microsoft.com/library/dn499787.aspx).</span></span>

### <a name="general-settings"></a><span data-ttu-id="16be1-240">全般設定</span><span class="sxs-lookup"><span data-stu-id="16be1-240">General settings</span></span>

|<span data-ttu-id="16be1-241">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-241">Setting name</span></span>|<span data-ttu-id="16be1-242">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-242">Details</span></span>|
|----------------|--------------------|
|<span data-ttu-id="16be1-243">**名前**</span><span class="sxs-lookup"><span data-stu-id="16be1-243">**Name**</span></span>|<span data-ttu-id="16be1-244">ポリシーの一意の名前を入力すると、Intune コンソール内で容易に識別できます。</span><span class="sxs-lookup"><span data-stu-id="16be1-244">Enter a unique name for the policy to help you identify it in the Intune console.</span></span>|
|<span data-ttu-id="16be1-245">**説明**</span><span class="sxs-lookup"><span data-stu-id="16be1-245">**Description**</span></span>|<span data-ttu-id="16be1-246">ポリシーの概要や、ポリシーを特定するのに役立つその他の関連情報についての説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="16be1-246">Provide a description that gives an overview of the policy and other relevant information that helps you to locate it.</span></span>|

### <a name="oma-uri-settings"></a><span data-ttu-id="16be1-247">OMA-URI 設定</span><span class="sxs-lookup"><span data-stu-id="16be1-247">OMA-URI settings</span></span>

<span data-ttu-id="16be1-248">**[OMA-URI 設定]** セクションで **[追加]** をクリックして設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="16be1-248">In the **OMA-URI Settings** section, click **Add** to add a setting.</span></span> <span data-ttu-id="16be1-249">既存の設定を編集または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="16be1-249">You can also edit or delete an existing setting.</span></span>

<span data-ttu-id="16be1-250">**[OMA-URI 設定の追加または編集]** ダイアログ ボックスで、以下の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-250">In the **Add or Edit OMA-URI Setting** dialog box, specify the following information:</span></span>

|<span data-ttu-id="16be1-251">設定の名前</span><span class="sxs-lookup"><span data-stu-id="16be1-251">Setting name</span></span>|<span data-ttu-id="16be1-252">説明</span><span class="sxs-lookup"><span data-stu-id="16be1-252">Details</span></span>|
    |--------|--------------------|
    |<span data-ttu-id="16be1-253">**設定の名前**</span><span class="sxs-lookup"><span data-stu-id="16be1-253">**Setting name**</span></span>|<span data-ttu-id="16be1-254">OMA-URI 設定の一意の名前を入力すると、設定リスト内で容易に識別できます。</span><span class="sxs-lookup"><span data-stu-id="16be1-254">Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.</span></span>|
    |<span data-ttu-id="16be1-255">**設定の説明**</span><span class="sxs-lookup"><span data-stu-id="16be1-255">**Setting description**</span></span>|<span data-ttu-id="16be1-256">設定の概要と、それを特定するために役立つその他の関連情報についての説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="16be1-256">Provide a description that gives an overview of the setting and other relevant information to help you locate it.</span></span>|
    |<span data-ttu-id="16be1-257">**データ型**</span><span class="sxs-lookup"><span data-stu-id="16be1-257">**Data type**</span></span>|<span data-ttu-id="16be1-258">この OMA-URI 設定を指定するデータ型を選択します。</span><span class="sxs-lookup"><span data-stu-id="16be1-258">Select the data type in which you will specify this OMA-URI setting.</span></span> <span data-ttu-id="16be1-259">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="16be1-259">Choose from:</span></span><br /><br /><span data-ttu-id="16be1-260">-   **文字列**</span><span class="sxs-lookup"><span data-stu-id="16be1-260">-   **String**</span></span><br /><span data-ttu-id="16be1-261">-   **文字列 (XML)**</span><span class="sxs-lookup"><span data-stu-id="16be1-261">-   **String (XML)**</span></span><br /><span data-ttu-id="16be1-262">-   **日付と時刻**</span><span class="sxs-lookup"><span data-stu-id="16be1-262">-   **Date and time**</span></span><br /><span data-ttu-id="16be1-263">-   **整数型**</span><span class="sxs-lookup"><span data-stu-id="16be1-263">-   **Integer**</span></span><br /><span data-ttu-id="16be1-264">-   **浮動小数点**</span><span class="sxs-lookup"><span data-stu-id="16be1-264">-   **Floating point**</span></span><br /><span data-ttu-id="16be1-265">-   **ブール型**</span><span class="sxs-lookup"><span data-stu-id="16be1-265">-   **Boolean**</span></span>|
    |<span data-ttu-id="16be1-266">**OMA-URI (大文字と小文字を区別する)**</span><span class="sxs-lookup"><span data-stu-id="16be1-266">**OMA-URI (case sensitive)**</span></span>|<span data-ttu-id="16be1-267">設定対象の OMA-URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-267">Specify the OMA-URI for which you want to supply a setting.</span></span>|
    |<span data-ttu-id="16be1-268">**値**</span><span class="sxs-lookup"><span data-stu-id="16be1-268">**Value**</span></span>|<span data-ttu-id="16be1-269">以前に指定した OMA-URI に関連付ける値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16be1-269">Specify the value to associate with the OMA-URI that you specified previously.</span></span>|

### <a name="see-also"></a><span data-ttu-id="16be1-270">関連項目</span><span class="sxs-lookup"><span data-stu-id="16be1-270">See also</span></span>
[<span data-ttu-id="16be1-271">Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する</span><span class="sxs-lookup"><span data-stu-id="16be1-271">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
