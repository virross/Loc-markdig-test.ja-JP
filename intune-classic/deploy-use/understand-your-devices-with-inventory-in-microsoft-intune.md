---
title: "インベントリでデバイスを把握する"
description: "Intune を使用して、管理するデバイスのハードウェアに関する情報を表示します。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ccb5c17eeb3e965c8ac268dcfae18febd620b0c0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="understand-your-devices-with-inventory-in-microsoft-intune"></a><span data-ttu-id="0044d-103">Microsoft Intune でインベントリを使用してデバイスを把握する</span><span class="sxs-lookup"><span data-stu-id="0044d-103">Understand your devices with inventory in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="0044d-104">Microsoft Intune では、Intune クライアント ソフトウェアを実行している、登録済みデバイスと Windows PC のインベントリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0044d-104">Microsoft Intune lets you view the inventory of enrolled devices and Windows PCs that run the Intune client software.</span></span>
<span data-ttu-id="0044d-105">Intune は通常、7 日ごとに管理対象デバイスからインベントリを収集します。</span><span class="sxs-lookup"><span data-stu-id="0044d-105">Intune typically collects inventory from managed devices every 7 days.</span></span> <span data-ttu-id="0044d-106">このため、デバイス名の変更など、デバイスに対する最近の変更結果や記憶域の空き容量をレポートが表示する際に、遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0044d-106">Because of this, there might be a delay before reports show the results of any recent changes to devices, for example, a change to the device name, or free storage space.</span></span>

## <a name="whats-collected-from-enrolled-devices"></a><span data-ttu-id="0044d-107">登録済みデバイスから収集される情報</span><span class="sxs-lookup"><span data-stu-id="0044d-107">What's collected from enrolled devices?</span></span>
<span data-ttu-id="0044d-108">モバイル デバイスで収集されたインベントリを表示するには、[モバイル デバイスのインベントリ レポート](understand-microsoft-intune-operations-by-using-reports.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="0044d-108">To view the inventory that's collected by mobile devices, run the [Mobile Device Inventory Reports](understand-microsoft-intune-operations-by-using-reports.md).</span></span> <span data-ttu-id="0044d-109">Intune では、登録済みデバイスから次のインベントリを収集します。</span><span class="sxs-lookup"><span data-stu-id="0044d-109">Intune collects the following inventory from enrolled devices:</span></span>

|<span data-ttu-id="0044d-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0044d-110">Property</span></span>|<span data-ttu-id="0044d-111">デバイスの種類</span><span class="sxs-lookup"><span data-stu-id="0044d-111">Collected by</span></span>|
|------------|-----------------------|
|<span data-ttu-id="0044d-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="0044d-112">**Name**</span></span>|<span data-ttu-id="0044d-113">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-113">All devices</span></span>|
|<span data-ttu-id="0044d-114">**オペレーティング システム**</span><span class="sxs-lookup"><span data-stu-id="0044d-114">**Operating System**</span></span>|<span data-ttu-id="0044d-115">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-115">All devices</span></span>|
|<span data-ttu-id="0044d-116">**製造元**</span><span class="sxs-lookup"><span data-stu-id="0044d-116">**Manufacturer**</span></span>|<span data-ttu-id="0044d-117">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-117">All devices</span></span>|
|<span data-ttu-id="0044d-118">**モデル**</span><span class="sxs-lookup"><span data-stu-id="0044d-118">**Model**</span></span>|<span data-ttu-id="0044d-119">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-119">All devices</span></span>|
|<span data-ttu-id="0044d-120">**管理チャネル**</span><span class="sxs-lookup"><span data-stu-id="0044d-120">**Management Channel**</span></span>|<span data-ttu-id="0044d-121">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-121">All devices</span></span>|
|<span data-ttu-id="0044d-122">**AAD に登録済み**</span><span class="sxs-lookup"><span data-stu-id="0044d-122">**AAD Registered**</span></span>|<span data-ttu-id="0044d-123">Mac OS X を除くすべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-123">All devices except Mac OS X</span></span>|
|<span data-ttu-id="0044d-124">**対応**</span><span class="sxs-lookup"><span data-stu-id="0044d-124">**Compliant**</span></span>|<span data-ttu-id="0044d-125">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-125">All devices</span></span>|
|<span data-ttu-id="0044d-126">**EAS アクティブ化**</span><span class="sxs-lookup"><span data-stu-id="0044d-126">**EAS Activated**</span></span>|<span data-ttu-id="0044d-127">Mac OS X を除くすべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-127">All devices except Mac OS X</span></span>|
|<span data-ttu-id="0044d-128">**EAS アクティブ化 ID**</span><span class="sxs-lookup"><span data-stu-id="0044d-128">**EAS Activation ID**</span></span>|<span data-ttu-id="0044d-129">Mac OS X を除くすべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-129">All devices except Mac OS X</span></span>|
|<span data-ttu-id="0044d-130">**EAS アクティブ化時刻**</span><span class="sxs-lookup"><span data-stu-id="0044d-130">**EAS Activation Time**</span></span>|<span data-ttu-id="0044d-131">Mac OS X を除くすべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-131">All devices except Mac OS X</span></span>|
|<span data-ttu-id="0044d-132">**管理状態**</span><span class="sxs-lookup"><span data-stu-id="0044d-132">**Management State**</span></span>|<span data-ttu-id="0044d-133">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-133">All devices</span></span>|
|<span data-ttu-id="0044d-134">**電子メール アドレス**</span><span class="sxs-lookup"><span data-stu-id="0044d-134">**Email Address**</span></span>|<span data-ttu-id="0044d-135">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-135">All devices</span></span>|
|<span data-ttu-id="0044d-136">**Exchange ActiveSync ID**</span><span class="sxs-lookup"><span data-stu-id="0044d-136">**Exchange ActiveSync ID**</span></span>|<span data-ttu-id="0044d-137">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-137">All devices</span></span>|
|<span data-ttu-id="0044d-138">**脱獄またはルート化**</span><span class="sxs-lookup"><span data-stu-id="0044d-138">**Jailbroken or Rooted**</span></span>|<span data-ttu-id="0044d-139">iOS デバイスと Android デバイスのみ</span><span class="sxs-lookup"><span data-stu-id="0044d-139">iOS and Android devices only</span></span>|
|<span data-ttu-id="0044d-140">**一意のデバイス ID**</span><span class="sxs-lookup"><span data-stu-id="0044d-140">**Unique Device ID**</span></span>|<span data-ttu-id="0044d-141">Exchange ActiveSync を除くすべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-141">All devices except Exchange ActiveSync</span></span>|
|<span data-ttu-id="0044d-142">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="0044d-142">**Serial number**</span></span>|<span data-ttu-id="0044d-143">iOS、Mac OS X、Android、Windows 8.1、Windows 10 デスクトップ デバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-143">iOS, Mac OS X, Android, Windows 8.1, and Windows 10 desktop devices</span></span>|
|<span data-ttu-id="0044d-144">**記憶域の合計容量**</span><span class="sxs-lookup"><span data-stu-id="0044d-144">**Total Storage Space**</span></span>|<span data-ttu-id="0044d-145">iOS、Mac OS X、Windows 8.1、および Windows 10 デスクトップおよびモバイル デバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-145">iOS, Mac OS X, Windows 8.1, and Windows 10 desktop and Mobile devices</span></span>|
|<span data-ttu-id="0044d-146">**記憶域の空き容量**</span><span class="sxs-lookup"><span data-stu-id="0044d-146">**Free Storage Space**</span></span>|<span data-ttu-id="0044d-147">iOS、Mac OS X、Windows 8.1、および Windows 10 デスクトップ デバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-147">iOS, Mac OS X, Windows 8.1, and Windows 10 desktop devices</span></span>|
|<span data-ttu-id="0044d-148">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="0044d-148">**Phone Number**</span></span><br><span data-ttu-id="0044d-149">会社の所有として分類される電話は、完全な電話番号で識別されます (モバイル デバイスのインベントリ レポートを実行するときなど)。</span><span class="sxs-lookup"><span data-stu-id="0044d-149">Phones that are categorized as corporate are identified with their full phone number (for example, when you run a mobile device inventory report).</span></span> <span data-ttu-id="0044d-150">BYOD デバイスの電話番号は &#42; でマスクされ、表示されるのは最後の 4 桁のみとなります。</span><span class="sxs-lookup"><span data-stu-id="0044d-150">BYOD phone numbers are masked with &#42;, and only the last four digits are displayed.</span></span>|<span data-ttu-id="0044d-151">iOS、Android、Windows Phone の各デバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-151">iOS, Android, and Windows Phone devices</span></span>|
|<span data-ttu-id="0044d-152">**IMEI**</span><span class="sxs-lookup"><span data-stu-id="0044d-152">**IMEI**</span></span>|<span data-ttu-id="0044d-153">Exchange ActiveSync、iOS、Android、Windows Phone の各デバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-153">Exchange ActiveSync, iOS, Android, and Windows Phone devices</span></span>|
|<span data-ttu-id="0044d-154">**MEID**</span><span class="sxs-lookup"><span data-stu-id="0044d-154">**MEID**</span></span><br><span data-ttu-id="0044d-155">Mobile Equipment Identifier</span><span class="sxs-lookup"><span data-stu-id="0044d-155">Mobile Equipment Identifier</span></span>|<span data-ttu-id="0044d-156">iOS デバイスのみ</span><span class="sxs-lookup"><span data-stu-id="0044d-156">iOS devices only</span></span>|
|<span data-ttu-id="0044d-157">**Wi-Fi MAC**</span><span class="sxs-lookup"><span data-stu-id="0044d-157">**Wi-Fi MAC**</span></span>|<span data-ttu-id="0044d-158">Exchange ActiveSync を除くすべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-158">All devices except Exchange ActiveSync</span></span>|
|<span data-ttu-id="0044d-159">**通信事業者**</span><span class="sxs-lookup"><span data-stu-id="0044d-159">**Subscriber Carrier**</span></span>|<span data-ttu-id="0044d-160">iOS デバイスと Android デバイスのみ</span><span class="sxs-lookup"><span data-stu-id="0044d-160">iOS and Android devices only</span></span>|
|<span data-ttu-id="0044d-161">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="0044d-161">**Cellular Technology**</span></span>|<span data-ttu-id="0044d-162">iOS デバイスと Android デバイスのみ</span><span class="sxs-lookup"><span data-stu-id="0044d-162">iOS and Android devices only</span></span>|
|<span data-ttu-id="0044d-163">**監督下**</span><span class="sxs-lookup"><span data-stu-id="0044d-163">**Supervised**</span></span>|<span data-ttu-id="0044d-164">iOS デバイスのみ</span><span class="sxs-lookup"><span data-stu-id="0044d-164">iOS devices only</span></span>|
|<span data-ttu-id="0044d-165">**アクティブ化ロック状態**</span><span class="sxs-lookup"><span data-stu-id="0044d-165">**Activation Lock State**</span></span>|<span data-ttu-id="0044d-166">iOS デバイスのみ</span><span class="sxs-lookup"><span data-stu-id="0044d-166">iOS devices only</span></span>|
|<span data-ttu-id="0044d-167">**登録日**</span><span class="sxs-lookup"><span data-stu-id="0044d-167">**Enrolled Date**</span></span>|<span data-ttu-id="0044d-168">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-168">All devices</span></span>|
|<span data-ttu-id="0044d-169">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="0044d-169">**Last Updated**</span></span>|<span data-ttu-id="0044d-170">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-170">All devices</span></span>|
|<span data-ttu-id="0044d-171">**イーサネット MAC**</span><span class="sxs-lookup"><span data-stu-id="0044d-171">**Ethernet MAC**</span></span>|<span data-ttu-id="0044d-172">Mac OS X デバイスのみ</span><span class="sxs-lookup"><span data-stu-id="0044d-172">Mac OS X devices only</span></span>|
|<span data-ttu-id="0044d-173">**アクティブ化ロック有効**</span><span class="sxs-lookup"><span data-stu-id="0044d-173">**Activation Lock Enabled**</span></span>|<span data-ttu-id="0044d-174">iOS デバイスのみ</span><span class="sxs-lookup"><span data-stu-id="0044d-174">iOS devices only</span></span>|
|<span data-ttu-id="0044d-175">**暗号化有効**</span><span class="sxs-lookup"><span data-stu-id="0044d-175">**Encryption Enabled**</span></span>|<span data-ttu-id="0044d-176">All のいずれかのデバイス</span><span class="sxs-lookup"><span data-stu-id="0044d-176">All devices</span></span>|

>[!NOTE]
><span data-ttu-id="0044d-177">上記項目の一部は、デバイスで利用している通信事業者によっては収集されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0044d-177">Some of the above items might not be collected depending on the carrier you use with the device.</span></span>

## <a name="whats-collected-from-windows-pcs"></a><span data-ttu-id="0044d-178">Windows PC から収集される情報</span><span class="sxs-lookup"><span data-stu-id="0044d-178">What's collected from Windows PCs?</span></span>
> [!IMPORTANT]
> <span data-ttu-id="0044d-179">このセクションの情報は、Intune の Windows PC クライアント ソフトウェアを実行する Windows PC にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0044d-179">This section applies only to Windows PCs that run the Intune Windows PC client software.</span></span>

<span data-ttu-id="0044d-180">Windows PC で収集されたインベントリを表示するには、[コンピューター インベントリ レポート](understand-microsoft-intune-operations-by-using-reports.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="0044d-180">To view the inventory that's collected by Windows PCs, run the [Computer Inventory Reports](understand-microsoft-intune-operations-by-using-reports.md).</span></span> <span data-ttu-id="0044d-181">Intune では、Windows PC から次のインベントリを収集します。</span><span class="sxs-lookup"><span data-stu-id="0044d-181">Intune collects the following inventory from Windows PCs:</span></span>

-   <span data-ttu-id="0044d-182">**名前**</span><span class="sxs-lookup"><span data-stu-id="0044d-182">**Name**</span></span>

-   <span data-ttu-id="0044d-183">**シャーシの種類**</span><span class="sxs-lookup"><span data-stu-id="0044d-183">**Chassis Type**</span></span>

-   <span data-ttu-id="0044d-184">**製造元**</span><span class="sxs-lookup"><span data-stu-id="0044d-184">**Manufacturer**</span></span>

-   <span data-ttu-id="0044d-185">**モデル**</span><span class="sxs-lookup"><span data-stu-id="0044d-185">**Model**</span></span>

-   <span data-ttu-id="0044d-186">**オペレーティング システム**</span><span class="sxs-lookup"><span data-stu-id="0044d-186">**Operating System**</span></span>

-   <span data-ttu-id="0044d-187">**TPM バージョン**</span><span class="sxs-lookup"><span data-stu-id="0044d-187">**TPM Version**</span></span>

-   <span data-ttu-id="0044d-188">**ディスク領域の合計**</span><span class="sxs-lookup"><span data-stu-id="0044d-188">**Total Disk Space**</span></span>

-   <span data-ttu-id="0044d-189">**使用済みディスク領域**</span><span class="sxs-lookup"><span data-stu-id="0044d-189">**Used Disk Space**</span></span>

-   <span data-ttu-id="0044d-190">**ディスクの空き領域**</span><span class="sxs-lookup"><span data-stu-id="0044d-190">**Free Disk Space**</span></span>

-   <span data-ttu-id="0044d-191">**OS ディスク名**</span><span class="sxs-lookup"><span data-stu-id="0044d-191">**OS Disk Name**</span></span>

-   <span data-ttu-id="0044d-192">**OS ディスク領域**</span><span class="sxs-lookup"><span data-stu-id="0044d-192">**OS Disk Space**</span></span>

-   <span data-ttu-id="0044d-193">**OS ディスクの空き領域**</span><span class="sxs-lookup"><span data-stu-id="0044d-193">**OS Disk Free Space**</span></span>

-   <span data-ttu-id="0044d-194">**物理メモリ**</span><span class="sxs-lookup"><span data-stu-id="0044d-194">**Physical Memory**</span></span>

-   <span data-ttu-id="0044d-195">**プロセッサー名**</span><span class="sxs-lookup"><span data-stu-id="0044d-195">**Processor Name**</span></span>

-   <span data-ttu-id="0044d-196">**プロセッサーのアーキテクチャ**</span><span class="sxs-lookup"><span data-stu-id="0044d-196">**Processor Architecture**</span></span>

-   <span data-ttu-id="0044d-197">**CPU 速度**</span><span class="sxs-lookup"><span data-stu-id="0044d-197">**CPU Speed**</span></span>

-   <span data-ttu-id="0044d-198">**IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="0044d-198">**IP Address**</span></span>

-   <span data-ttu-id="0044d-199">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="0044d-199">**Serial number**</span></span>

-   <span data-ttu-id="0044d-200">**最終ログオン ユーザー**</span><span class="sxs-lookup"><span data-stu-id="0044d-200">**Last User to Log On**</span></span>

-   <span data-ttu-id="0044d-201">**割り当てられたユーザー**</span><span class="sxs-lookup"><span data-stu-id="0044d-201">**Assigned User**</span></span>

-   <span data-ttu-id="0044d-202">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="0044d-202">**Last Updated**</span></span>

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->
