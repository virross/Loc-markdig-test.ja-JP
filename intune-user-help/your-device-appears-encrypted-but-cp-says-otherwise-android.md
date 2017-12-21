---
title: "Android デバイスが暗号化されているように見える | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: f9c91c85b4a93fb211b5cd278dd82277a58cb08e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a><span data-ttu-id="ca8db-102">Android デバイスは暗号化されるように見えるが、ポータル サイトではそのように認識されていない</span><span class="sxs-lookup"><span data-stu-id="ca8db-102">Your Android device seems to be encrypted, but Company Portal says otherwise</span></span>

<span data-ttu-id="ca8db-103">デバイスを暗号化する場合、自分しか知らない秘密キーを使ってデバイス上の情報をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="ca8db-103">When you encrypt a device, you are encoding the information on it using a secret key that is known only to you.</span></span> <span data-ttu-id="ca8db-104">これにより、承認されていないユーザーはデバイスにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ca8db-104">This prevents unauthorized people from accessing it.</span></span> <span data-ttu-id="ca8db-105">多くの組織では、会社のファイル、メール、またはデータにアクセスするのに、Android デバイスの暗号化を義務づけています。</span><span class="sxs-lookup"><span data-stu-id="ca8db-105">Many organizations require their users to encrypt their Android devices before they can access company files, email, or data.</span></span>

## <a name="common-issues"></a><span data-ttu-id="ca8db-106">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="ca8db-106">Common issues</span></span>

<span data-ttu-id="ca8db-107">新しいバージョンの Android、特に v7.0 以降では、デバイスが完全に暗号化されているかどうかを確認するスタートアップ パスコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca8db-107">Newer versions of Android, particularly starting with v7.0, require a startup passcode to make sure that your device is fully encrypted.</span></span> <span data-ttu-id="ca8db-108">デバイスの製造元によって、スタートアップ パスコードに関する説明と場所は異なります。</span><span class="sxs-lookup"><span data-stu-id="ca8db-108">Different device manufacturers have varying descriptions and locations for the startup passcode.</span></span> <span data-ttu-id="ca8db-109">ほとんどの場合、この設定は "安全な起動" と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="ca8db-109">Most of the time, this setting is referred to as "Secure Startup."</span></span> 

## <a name="solutions"></a><span data-ttu-id="ca8db-110">ソリューション</span><span class="sxs-lookup"><span data-stu-id="ca8db-110">Solutions</span></span>

### <a name="add-a-startup-pin"></a><span data-ttu-id="ca8db-111">スタートアップ PIN の追加</span><span class="sxs-lookup"><span data-stu-id="ca8db-111">Add a startup PIN</span></span>

<span data-ttu-id="ca8db-112">いくつかの Android デバイスでは、デバイスがセキュリティ保護されていることを確認するためにスタートアップ PIN を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8db-112">Certain Android devices require you to create a startup PIN to make sure that your device is secure.</span></span> <span data-ttu-id="ca8db-113">異なる製造元によるさまざまな Android のバージョンが存在します。</span><span class="sxs-lookup"><span data-stu-id="ca8db-113">There are many versions of Android from many different manufacturers.</span></span> <span data-ttu-id="ca8db-114">このオプションを有効にする設定アプリで場所を見つけることにより、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="ca8db-114">You can try to fix this issue by finding a location in your settings app to enable this option.</span></span> <span data-ttu-id="ca8db-115">たとえば、Samsung Galaxy S7 では、**[設定]** > **[ロック画面とセキュリティ]** > **[安全な起動]** と移動して、安全なスタートアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ca8db-115">For example, on the Samsung Galaxy S7, you enable Secure Startup by going to **Settings** > **Lock Screen and Security** > **Secure Startup**.</span></span>  

### <a name="downgrade-your-version-of-android"></a><span data-ttu-id="ca8db-116">Android のバージョンのダウングレード</span><span class="sxs-lookup"><span data-stu-id="ca8db-116">Downgrade your version of Android</span></span>

<span data-ttu-id="ca8db-117">デバイスで Android 6.0 以降にダウングレードできる場合は、ダウングレードします。</span><span class="sxs-lookup"><span data-stu-id="ca8db-117">If your device offers you the option to downgrade to Android 6.0+, then do so.</span></span> <span data-ttu-id="ca8db-118">デバイスのダウングレードには、データ損失のリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="ca8db-118">There is a risk of data loss if you should try to downgrade your device.</span></span> <span data-ttu-id="ca8db-119">そのため、会社のサポートに問い合わせて、この問題を解決することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca8db-119">Otherwise, we recommend that you contact your company support to resolve this issue.</span></span> <span data-ttu-id="ca8db-120">会社のサポートの連絡先情報は、[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="ca8db-120">You can get contact information for your company support at the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) for contact information.</span></span>

### <a name="encrypt-the-entire-device"></a><span data-ttu-id="ca8db-121">デバイス全体を暗号化します</span><span class="sxs-lookup"><span data-stu-id="ca8db-121">Encrypt the entire device</span></span>

<span data-ttu-id="ca8db-122">一部のデバイスでは、デバイス全体と使用済み領域のみのどちらを暗号化するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="ca8db-122">Some devices will give you a choice between encrypting the entire device or just the used space.</span></span> <span data-ttu-id="ca8db-123">"使用済み領域のみ" ではなく、デバイス全体の暗号化を選んでください。</span><span class="sxs-lookup"><span data-stu-id="ca8db-123">Choose the option to encrypt the entire device rather than "only used space."</span></span> <span data-ttu-id="ca8db-124">既に使用済み領域のみを暗号化している場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ca8db-124">If you have already encrypted only the used space:</span></span>

1. [<span data-ttu-id="ca8db-125">ポータル サイトからこのデバイスを削除します</span><span class="sxs-lookup"><span data-stu-id="ca8db-125">Remove this device from the Company Portal</span></span>](unenroll-your-device-from-intune-android.md)
2. <span data-ttu-id="ca8db-126">使用済み領域の暗号化を解除します</span><span class="sxs-lookup"><span data-stu-id="ca8db-126">Decrypt the used space</span></span>
3. <span data-ttu-id="ca8db-127">デバイス全体を暗号化します</span><span class="sxs-lookup"><span data-stu-id="ca8db-127">Encrypt the entire device</span></span>
4. <span data-ttu-id="ca8db-128">デバイスを再度登録します</span><span class="sxs-lookup"><span data-stu-id="ca8db-128">Re-enroll the device</span></span>

## <a name="specific-manufacturer-issues"></a><span data-ttu-id="ca8db-129">特定の製造元の問題</span><span class="sxs-lookup"><span data-stu-id="ca8db-129">Specific manufacturer issues</span></span>

<span data-ttu-id="ca8db-130">バージョン 7.0 以上の一部の Android デバイスでは、特定の Android プラットフォームの標準に準拠していない方法でデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ca8db-130">Some Android devices on version 7.0+ encrypt data in ways that are inconsistent with certain Android platform standards.</span></span> <span data-ttu-id="ca8db-131">これらのデバイスは、まったく新しい場合でも暗号化されているものとして表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ca8db-131">These devices may appear encrypted even when they are brand new.</span></span> <span data-ttu-id="ca8db-132">Intune では、これらのデバイスの暗号化方法はデバイスの情報を危険にさらすものとして認識します。</span><span class="sxs-lookup"><span data-stu-id="ca8db-132">Intune recognizes that these devices' encryption methods put the device's information at risk.</span></span> <span data-ttu-id="ca8db-133">このリスクの原因は主として、デバイスに物理的にアクセスできる悪意のあるユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ca8db-133">This risk primarily stems from malicious users who have physical access to the device.</span></span>

> [!Note]
> <span data-ttu-id="ca8db-134">Microsoft は製造元と協力して、テスト中に見つけた問題やユーザーから報告された問題に対処しています。</span><span class="sxs-lookup"><span data-stu-id="ca8db-134">Microsoft works with manufacturers to address any issues we find while testing, or that users report to us.</span></span> <span data-ttu-id="ca8db-135">新しい情報が得られたらこの記事の内容を更新します。</span><span class="sxs-lookup"><span data-stu-id="ca8db-135">We update this article whenever new information is available.</span></span> 

## <a name="known-devices"></a><span data-ttu-id="ca8db-136">既知のデバイス</span><span class="sxs-lookup"><span data-stu-id="ca8db-136">Known devices</span></span>

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a><span data-ttu-id="ca8db-137">更新によってこの問題を解決できる既知のデバイス</span><span class="sxs-lookup"><span data-stu-id="ca8db-137">Known devices that can be updated to fix this issue</span></span>

<span data-ttu-id="ca8db-138">以下のデバイスのいずれかをお使いの場合は、デバイスを最新バージョンの Android に更新していない場合にこの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca8db-138">If you have one of the following devices, you may experience this issue if you have not updated your device to the most recent version of Android.</span></span> <span data-ttu-id="ca8db-139">**[設定]** > **[更新]** と移動して、これらのデバイスの更新プログラムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ca8db-139">You can install the updates for these devices by going to **Settings** > **Update**.</span></span> 

- [<span data-ttu-id="ca8db-140">Huawei Honor 8</span><span class="sxs-lookup"><span data-stu-id="ca8db-140">Huawei Honor 8</span></span>](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [<span data-ttu-id="ca8db-141">Huawei P9</span><span class="sxs-lookup"><span data-stu-id="ca8db-141">Huawei P9</span></span>](http://consumer.huawei.com/en/phones/p9/)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a><span data-ttu-id="ca8db-142">更新によってこの問題を解決できない既知のデバイス</span><span class="sxs-lookup"><span data-stu-id="ca8db-142">Known devices that currently cannot be updated to fix this issue</span></span>

<span data-ttu-id="ca8db-143">以下のデバイスについてはこの問題を解決できません。</span><span class="sxs-lookup"><span data-stu-id="ca8db-143">You cannot resolve this issue for the devices below.</span></span> <span data-ttu-id="ca8db-144">会社のリソースにアクセスするには別のデバイスを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8db-144">You may need to use a different device to access company resources.</span></span> 

- [<span data-ttu-id="ca8db-145">Huawei Mate 8</span><span class="sxs-lookup"><span data-stu-id="ca8db-145">Huawei Mate 8</span></span>](https://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [<span data-ttu-id="ca8db-146">OPPO デバイス</span><span class="sxs-lookup"><span data-stu-id="ca8db-146">OPPO devices</span></span>](http://www.oppo.com/en/smartphones)
- [<span data-ttu-id="ca8db-147">Vivo デバイス</span><span class="sxs-lookup"><span data-stu-id="ca8db-147">Vivo devices</span></span>](https://www.vivo.co.in)
- [<span data-ttu-id="ca8db-148">Xiaomi Mi スマートフォン</span><span class="sxs-lookup"><span data-stu-id="ca8db-148">Xiaomi Mi smartphones</span></span>](https://xiaomi-mi.com/mi-smartphones/)
