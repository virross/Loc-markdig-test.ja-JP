---
title: "Android の管理をセットアップする"
description: "Microsoft Intune を使用して Android および KNOX Standard デバイスのモバイル デバイス管理 (MDM) を有効にします。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d1245f5644b24d258f8542252f8910789b63ba02
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="set-up-android-device-management"></a><span data-ttu-id="0e9dd-103">Android デバイスの管理をセットアップする</span><span class="sxs-lookup"><span data-stu-id="0e9dd-103">Set up Android device management</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="0e9dd-104">Intune 管理者は、ポータル サイトから Samsung Knox Standard デバイスなどの Android デバイスの管理を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-104">As an Intune administrator, you can enable management of Android devices, including Samsung Knox Standard devices, from the Company Portal.</span></span> <span data-ttu-id="0e9dd-105">ユーザーが、Google Play から入手できるポータル サイト アプリを使用してデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-105">Users can then enroll their devices using the Company Portal app that is available from Google Play.</span></span>

<span data-ttu-id="0e9dd-106">既定では、Android デバイスを Intune に登録することができます。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-106">By default, Android devices are allowed to enroll in Intune.</span></span> <span data-ttu-id="0e9dd-107">Android デバイスの登録をブロックするには、管理者資格情報を使用して [Microsoft Intune 管理ポータル](https://manage.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-107">To block Android devices from enrolling, sign to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials.</span></span> <span data-ttu-id="0e9dd-108">**[管理]** > **[モバイル デバイス管理]** > **[登録ルール]** の順に選択し、**[Android デバイスを許可する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-108">Choose **Admin** > **Mobile Device Management** > **Enrollment Rules** and then clear the **Allow Android devices** check box.</span></span>

1. <span data-ttu-id="0e9dd-109">**Intune をセットアップする**</span><span class="sxs-lookup"><span data-stu-id="0e9dd-109">**Set up Intune**</span></span><br>
   <span data-ttu-id="0e9dd-110">**Microsoft Intune** を[モバイル デバイス管理機関に設定](prerequisites-for-enrollment.md#step-2-set-mdm-authority)して、MDM の設定を行うことにより、モバイル デバイス管理を準備します (この作業をまだ行っていない場合)。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-110">If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#step-2-set-mdm-authority) as **Microsoft Intune** and setting up MDM.</span></span>

2. <span data-ttu-id="0e9dd-111">**Android の登録が有効になる**</span><span class="sxs-lookup"><span data-stu-id="0e9dd-111">**Android enrollment enabled**</span></span><br>
   <span data-ttu-id="0e9dd-112">Android モバイル デバイスの登録を有効にするために、Intune コンソールで追加の構成を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-112">No additional configurations in the Intune console are needed to enable Android mobile device enrollment.</span></span>

3. <span data-ttu-id="0e9dd-113">**デバイスを登録して会社のリソースへのアクセスを取得する方法をユーザーに知らせる**</span><span class="sxs-lookup"><span data-stu-id="0e9dd-113">**Tell your users how to enroll their devices to get access to company resources.**</span></span>

   <span data-ttu-id="0e9dd-114">エンドユーザー用の登録手順については、「[Intune に Android デバイスを登録する](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-114">For end-user enrollment instructions, see [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).</span></span> <span data-ttu-id="0e9dd-115">登録プロセスでは、登録により可能になる操作、および IT 管理者が見ることのできるデバイス上のデータと見られないデータについての説明が行われます。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-115">The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.</span></span>

   <span data-ttu-id="0e9dd-116">その他のエンドユーザー タスクの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-116">For information about other end-user tasks, see these articles:</span></span>
   - [<span data-ttu-id="0e9dd-117">Microsoft Intune を使用したエンドユーザー エクスペリエンスに関するリソース</span><span class="sxs-lookup"><span data-stu-id="0e9dd-117">Resources about the end-user experience with Microsoft Intune</span></span>](/intune/end-user-educate)
   - [<span data-ttu-id="0e9dd-118">Android デバイス向けエンド ユーザー ガイダンス</span><span class="sxs-lookup"><span data-stu-id="0e9dd-118">End user guidance for Android devices</span></span>](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

<span data-ttu-id="0e9dd-119">中国には Google Play ストアがないので、Android デバイスは中国のアプリ マーケットプレースからポータル サイトを入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-119">Due to the absence of Google Play Store in China, Android devices must obtain the Company Portal from Chinese app marketplaces.</span></span> <span data-ttu-id="0e9dd-120">Android 用ポータル サイト アプリは、以下のストアでダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-120">The Company Portal app for Android will be available for download on the following stores:</span></span>
* [<span data-ttu-id="0e9dd-121">Baidu</span><span class="sxs-lookup"><span data-stu-id="0e9dd-121">Baidu</span></span>](https://go.microsoft.com/fwlink/?linkid=836946)
* [<span data-ttu-id="0e9dd-122">Huawei</span><span class="sxs-lookup"><span data-stu-id="0e9dd-122">Huawei</span></span>](https://go.microsoft.com/fwlink/?linkid=836948)
* [<span data-ttu-id="0e9dd-123">Tencent</span><span class="sxs-lookup"><span data-stu-id="0e9dd-123">Tencent</span></span>](https://go.microsoft.com/fwlink/?linkid=836949)
* [<span data-ttu-id="0e9dd-124">Wandoujia</span><span class="sxs-lookup"><span data-stu-id="0e9dd-124">Wandoujia</span></span>](https://go.microsoft.com/fwlink/?linkid=836950)
* [<span data-ttu-id="0e9dd-125">Xiaomi</span><span class="sxs-lookup"><span data-stu-id="0e9dd-125">Xiaomi</span></span>](https://go.microsoft.com/fwlink/?linkid=836947)

<span data-ttu-id="0e9dd-126">Android 用ポータル サイト アプリは、Google Play 開発者サービスを使って Microsoft Intune サービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-126">The Company Portal app for Android uses Google Play Services to communicate with the Microsoft Intune service.</span></span> <span data-ttu-id="0e9dd-127">中国では Google Play 開発者サービスをまだ利用できないので、次のタスクには最大 8 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="0e9dd-127">Since Google Play Services are not yet available in China, performing any of the following tasks can take up to 8 hours to complete.</span></span> 

|<span data-ttu-id="0e9dd-128">Intune 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="0e9dd-128">Intune Admin Console</span></span>| <span data-ttu-id="0e9dd-129">Android 用 Intune ポータル サイト アプリ</span><span class="sxs-lookup"><span data-stu-id="0e9dd-129">Intune Company Portal app for Android</span></span> |<span data-ttu-id="0e9dd-130">Intune ポータル サイト Web サイト</span><span class="sxs-lookup"><span data-stu-id="0e9dd-130">Intune Company Portal Website</span></span>|   
|---|---|---|
|<span data-ttu-id="0e9dd-131">フル ワイプ</span><span class="sxs-lookup"><span data-stu-id="0e9dd-131">Full wipe</span></span>| <span data-ttu-id="0e9dd-132">リモート デバイスの削除</span><span class="sxs-lookup"><span data-stu-id="0e9dd-132">Remove a remote device</span></span>| <span data-ttu-id="0e9dd-133">デバイスの削除 (ローカルおよびリモート)</span><span class="sxs-lookup"><span data-stu-id="0e9dd-133">Remove device (local and remote)</span></span>|
|<span data-ttu-id="0e9dd-134">選択的ワイプ</span><span class="sxs-lookup"><span data-stu-id="0e9dd-134">Selective wipe</span></span>| <span data-ttu-id="0e9dd-135">デバイスのリセット</span><span class="sxs-lookup"><span data-stu-id="0e9dd-135">Reset device</span></span>| <span data-ttu-id="0e9dd-136">デバイスのリセット</span><span class="sxs-lookup"><span data-stu-id="0e9dd-136">Reset device</span></span>|
|<span data-ttu-id="0e9dd-137">新規アプリまたは更新アプリの展開</span><span class="sxs-lookup"><span data-stu-id="0e9dd-137">New or updated app deployments</span></span>| <span data-ttu-id="0e9dd-138">使用可能な基幹業務アプリのインストール</span><span class="sxs-lookup"><span data-stu-id="0e9dd-138">Install available line-of-business apps</span></span>| <span data-ttu-id="0e9dd-139">デバイスのパスコードのリセット</span><span class="sxs-lookup"><span data-stu-id="0e9dd-139">Device passcode reset</span></span>|
|<span data-ttu-id="0e9dd-140">リモート ロック</span><span class="sxs-lookup"><span data-stu-id="0e9dd-140">Remote lock</span></span>|||
|<span data-ttu-id="0e9dd-141">パスコードのリセット</span><span class="sxs-lookup"><span data-stu-id="0e9dd-141">Passcode reset</span></span>|||

### <a name="see-also"></a><span data-ttu-id="0e9dd-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e9dd-142">See also</span></span>
[<span data-ttu-id="0e9dd-143">Microsoft Intune でデバイスを登録するための前提条件</span><span class="sxs-lookup"><span data-stu-id="0e9dd-143">Prerequisites to enrolling devices in Microsoft Intune</span></span>](prerequisites-for-enrollment.md)
