---
title: "Exchange ActiveSync ポリシー設定"
description: "Intune Exchange ActiveSync ポリシーを使用して、Exchange ActiveSync で管理されているデバイスのさまざまな機能を制御できる設定を構成します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 88d37763094766ce37da6b58c8426f754103a750
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="exchange-activesync-policy-settings-in-microsoft-intune"></a><span data-ttu-id="28f20-103">Microsoft Intune の Exchange ActiveSync ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="28f20-103">Exchange ActiveSync policy settings in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="28f20-104">Microsoft Intune **Exchange ActiveSync** ポリシーを使用して、Exchange ActiveSync で管理されているデバイスのさまざまな機能を制御する設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="28f20-104">Use the Microsoft Intune **Exchange ActiveSync** policy to configure settings that control a range of features and functionality on devices that are managed by Exchange ActiveSync.</span></span>


## <a name="password-settings"></a><span data-ttu-id="28f20-105">パスワードの設定</span><span class="sxs-lookup"><span data-stu-id="28f20-105">Password settings</span></span>

|<span data-ttu-id="28f20-106">設定の名前</span><span class="sxs-lookup"><span data-stu-id="28f20-106">Setting name</span></span>|<span data-ttu-id="28f20-107">説明</span><span class="sxs-lookup"><span data-stu-id="28f20-107">Details</span></span>
|----------------|---|
|<span data-ttu-id="28f20-108">**モバイル デバイスのロックを解除するパスワードを要求する**</span><span class="sxs-lookup"><span data-stu-id="28f20-108">**Require a password to unlock mobile devices**</span></span>|<span data-ttu-id="28f20-109">パスワードを使用してデバイスをロックする必要があるかどうかを指定します </span><span class="sxs-lookup"><span data-stu-id="28f20-109">Specifies whether devices must be locked by using a password.</span></span><br><span data-ttu-id="28f20-110">(Windows RT を実行するデバイスには適用されません)。</span><span class="sxs-lookup"><span data-stu-id="28f20-110">(not applicable to devices running Windows RT).</span></span>|
|<span data-ttu-id="28f20-111">**必要なパスワードの種類**</span><span class="sxs-lookup"><span data-stu-id="28f20-111">**Required password type**</span></span>|<span data-ttu-id="28f20-112">数値のみや英数字など、必要なパスワードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-112">Specifies the type of password that will be required, such as numeric only or alphanumeric.</span></span>|
|<span data-ttu-id="28f20-113">**最小のパスワードの長さ**</span><span class="sxs-lookup"><span data-stu-id="28f20-113">**Minimum password length**</span></span>|<span data-ttu-id="28f20-114">デバイスのパスワードに必要な最小文字数を指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-114">Specifies the minimum number of required characters in the device password.</span></span>|
|<span data-ttu-id="28f20-115">**単純なパスワードを許可する**</span><span class="sxs-lookup"><span data-stu-id="28f20-115">**Allow simple passwords**</span></span>|<span data-ttu-id="28f20-116">"0000" や "1234" などの単純なパスワードを使えるようにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-116">Specifies whether you can use simple passwords, which include ‘0000’ and ‘1234’.</span></span>|
|<span data-ttu-id="28f20-117">**デバイスをワイプするまでの連続サインイン エラーの数**</span><span class="sxs-lookup"><span data-stu-id="28f20-117">**Number of repeated sign-in failures to allow before the device is wiped**</span></span>|<span data-ttu-id="28f20-118">間違ったパスワードをユーザーが何回入力すると、そのデバイスをワイプするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-118">Specifies the number of times that a user can enter an incorrect password before the device is wiped.</span></span>|
|<span data-ttu-id="28f20-119">**パスワードの有効期限 (日)**</span><span class="sxs-lookup"><span data-stu-id="28f20-119">**Password expiration (days)**</span></span>|<span data-ttu-id="28f20-120">デバイスのパスワードの変更が必要になるまでの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-120">Specifies the number of days after which the device password must be changed.</span></span>
|<span data-ttu-id="28f20-121">**パスワードの履歴を記憶する**</span><span class="sxs-lookup"><span data-stu-id="28f20-121">**Remember password history**</span></span>|<span data-ttu-id="28f20-122">以前に使用されていたパスワードの使用を許可しないかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-122">Specifies whether to not allow the use of previously used passwords.</span></span>|
|<span data-ttu-id="28f20-123">**パスワードの履歴を保存する** - **前のパスワードを再利用できないようにする**</span><span class="sxs-lookup"><span data-stu-id="28f20-123">**Remember password history** – **Prevent reuse of previous passwords**</span></span>|<span data-ttu-id="28f20-124">再び使用できない以前に使用していたパスワードの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-124">Specifies the number of previously used passwords that can't be used again.</span></span>|
|<span data-ttu-id="28f20-125">**パスワードが必要になるまでの非アクティブ状態の時間 (分)**</span><span class="sxs-lookup"><span data-stu-id="28f20-125">**Minutes of inactivity before password is required**</span></span>|<span data-ttu-id="28f20-126">デバイスがどれだけの時間アイドル状態であると、画面がロックされるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-126">Specifies the amount of time that a device must be idle before the screen is locked.</span></span>

## <a name="encryption-settings"></a><span data-ttu-id="28f20-127">暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="28f20-127">Encryption settings</span></span>

|                           <span data-ttu-id="28f20-128">設定の名前</span><span class="sxs-lookup"><span data-stu-id="28f20-128">Setting name</span></span>                           |                                                                                                                                    <span data-ttu-id="28f20-129">説明</span><span class="sxs-lookup"><span data-stu-id="28f20-129">Details</span></span>                                                                                                                                    |
|------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="28f20-130"><strong>モバイル デバイスの暗号化を要求する</strong><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="28f20-130"><strong>Require encryption on mobile device</strong><sup>1</sup></span></span> | <span data-ttu-id="28f20-131">サポートされている場合にデバイス上のデータの暗号化を要求します。</span><span class="sxs-lookup"><span data-stu-id="28f20-131">Requires the data on a device to be encrypted when supported.</span></span><br><br><span data-ttu-id="28f20-132">Windows Phone 8 デバイスの場合、これを <strong>[はい]</strong>に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28f20-132">For Windows Phone 8 devices, you must set this to <strong>Yes</strong>.</span></span><br /><br /><span data-ttu-id="28f20-133">iOS デバイスでの暗号化を有効にするには、<strong>[モバイル デバイスのロック解除にパスワードを必要とする]</strong> 設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="28f20-133">To enable encryption on iOS devices, enable the <strong>Require a password to unlock mobile devices</strong> setting.</span></span> |
|       <span data-ttu-id="28f20-134"><strong>メモリ カードの暗号化を必要とする</strong></span><span class="sxs-lookup"><span data-stu-id="28f20-134"><strong>Require encryption on storage cards</strong></span></span>       |                                                                                  <span data-ttu-id="28f20-135">(サポートされているデバイス上で) SD カードなどの外部ストレージに保存されたデータの暗号化を要求します。</span><span class="sxs-lookup"><span data-stu-id="28f20-135">Requires data that is stored on external storage such as an SD card to be encrypted (on supported devices).</span></span>                                                                                  |

<span data-ttu-id="28f20-136"><sup>1</sup> Windows 8.1 が実行されているデバイスの追加情報</span><span class="sxs-lookup"><span data-stu-id="28f20-136"><sup>1</sup> Additional information for devices that run Windows 8.1</span></span>

-   <span data-ttu-id="28f20-137">Windows 8.1 搭載デバイスで暗号化を適用する場合は、[Windows の 2014 年 12 月付け MDM クライアント更新プログラム](https://support.microsoft.com/kb/3013816)を各デバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28f20-137">If you want to enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](https://support.microsoft.com/kb/3013816) on each device.</span></span>

-   <span data-ttu-id="28f20-138">Windows 8.1 デバイスに対してこの設定を有効にすると、デバイスのすべてのユーザーに Microsoft アカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="28f20-138">If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.</span></span>

-   <span data-ttu-id="28f20-139">Windows 8.1 デバイスで暗号化を機能させる場合は、デバイスが Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) ハードウェア認定要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="28f20-139">If you want encryption to work for Windows 8.1 devices, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.</span></span>

-   <span data-ttu-id="28f20-140">Windows 8.1 デバイスで暗号化を適用すると、回復キーは、ユーザーの Microsoft アカウントからのみアクセスできるようになり、ユーザーの OneDrive アカウントからアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="28f20-140">If you enforce encryption on a Windows 8.1 device, the recovery key is only accessible from the user's Microsoft account, which is accessed from the user's OneDrive account.</span></span> <span data-ttu-id="28f20-141">ユーザーの代わりにこのキーを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="28f20-141">You cannot recover this key on behalf of a user.</span></span>

## <a name="email-settings"></a><span data-ttu-id="28f20-142">電子メールの設定</span><span class="sxs-lookup"><span data-stu-id="28f20-142">Email settings</span></span>

|<span data-ttu-id="28f20-143">設定の名前</span><span class="sxs-lookup"><span data-stu-id="28f20-143">Setting name</span></span>|<span data-ttu-id="28f20-144">説明</span><span class="sxs-lookup"><span data-stu-id="28f20-144">Details</span></span>
|----------------|---|
|<span data-ttu-id="28f20-145">**ユーザーが電子メールの添付ファイルをダウンロードできるようにする**</span><span class="sxs-lookup"><span data-stu-id="28f20-145">**Allow users to download email attachments**</span></span>|<span data-ttu-id="28f20-146">電子メールの添付ファイルをデバイスにダウンロードできるようにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-146">Specifies whether email attachments can be downloaded to the device.</span></span>|
|<span data-ttu-id="28f20-147">**電子メールを同期する期間**</span><span class="sxs-lookup"><span data-stu-id="28f20-147">**Email synchronization period**</span></span>|<span data-ttu-id="28f20-148">受信した電子メールをデバイスと同期する日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-148">Specifies the number of days of received email that will be synchronized to the device.</span></span>
|<span data-ttu-id="28f20-149">**Exchange ActiveSync を完全にサポートしていないモバイル デバイスによる Exchange との同期を許可する**</span><span class="sxs-lookup"><span data-stu-id="28f20-149">**Allow mobile devices that don’t fully support Exchange ActiveSync settings to synchronize with Exchange**</span></span>|<span data-ttu-id="28f20-150">1 つまたは複数の Exchange ActiveSync 設定をサポートしないデバイスで Exchange へのアクセスを許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-150">Specifies whether to allow Exchange access on devices that don't support one or more Exchange ActiveSync settings.</span></span>

## <a name="browser-settings"></a><span data-ttu-id="28f20-151">ブラウザー設定</span><span class="sxs-lookup"><span data-stu-id="28f20-151">Browser settings</span></span>

|<span data-ttu-id="28f20-152">設定の名前</span><span class="sxs-lookup"><span data-stu-id="28f20-152">Setting name</span></span>|<span data-ttu-id="28f20-153">説明</span><span class="sxs-lookup"><span data-stu-id="28f20-153">Details</span></span>
|----------------|---|
|<span data-ttu-id="28f20-154">**Web ブラウザーを許可する**</span><span class="sxs-lookup"><span data-stu-id="28f20-154">**Allow web browser**</span></span>|<span data-ttu-id="28f20-155">デバイスの Web ブラウザーを使用できるようにするかどうかを指定します </span><span class="sxs-lookup"><span data-stu-id="28f20-155">Specifies whether the web browser on the device can be used.</span></span><br><span data-ttu-id="28f20-156">(Windows RT または Windows Phone では使用できません)。</span><span class="sxs-lookup"><span data-stu-id="28f20-156">(Not available for Windows RT or Windows Phone).</span></span>

## <a name="hardware-settings"></a><span data-ttu-id="28f20-157">ハードウェア設定</span><span class="sxs-lookup"><span data-stu-id="28f20-157">Hardware settings</span></span>

|<span data-ttu-id="28f20-158">設定の名前</span><span class="sxs-lookup"><span data-stu-id="28f20-158">Setting name</span></span>|<span data-ttu-id="28f20-159">説明</span><span class="sxs-lookup"><span data-stu-id="28f20-159">Details</span></span>
|----------------|---|
|<span data-ttu-id="28f20-160">**カメラを許可する**</span><span class="sxs-lookup"><span data-stu-id="28f20-160">**Allow camera**</span></span>|<span data-ttu-id="28f20-161">デバイスのカメラを使用できるようにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f20-161">Specifies whether the camera on the device can be used.</span></span><br><span data-ttu-id="28f20-162">(Windows RT または Windows Phone では使用できません)。</span><span class="sxs-lookup"><span data-stu-id="28f20-162">(Not available for Windows RT or Windows Phone).</span></span>



### <a name="see-also"></a><span data-ttu-id="28f20-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="28f20-163">See also</span></span>
[<span data-ttu-id="28f20-164">Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する</span><span class="sxs-lookup"><span data-stu-id="28f20-164">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
