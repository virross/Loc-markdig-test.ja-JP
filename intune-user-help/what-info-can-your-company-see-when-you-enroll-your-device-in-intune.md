---
title: "デバイスを登録した場合に会社が確認できる情報 | Microsoft Docs"
description: "IT 管理者が管理対象デバイスについて確認できることとできないことのリスト。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 12655728-a1af-4d89-97bc-925fe36c0dc4
searchScope:
- User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.openlocfilehash: 91a6011f3391b908e583738366dcc215e61e8c14
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="what-information-can-my-company-see-when-i-enroll-my-device"></a><span data-ttu-id="b1676-104">デバイスを登録した場合に会社が確認できる情報</span><span class="sxs-lookup"><span data-stu-id="b1676-104">What information can my company see when I enroll my device?</span></span>

<span data-ttu-id="b1676-105">デバイスを管理対象として登録すると、デバイス上の特定の情報を表示する権限を会社に与えることになります。これは、デバイス上の会社のデータを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b1676-105">When you enroll a device into management, you are giving your company permission to view certain pieces of information on your device to help protect the corporate data on the device.</span></span>

<span data-ttu-id="b1676-106">**会社が確認できない情報**</span><span class="sxs-lookup"><span data-stu-id="b1676-106">**What your company can never see**</span></span>

- <span data-ttu-id="b1676-107">通話と Web 閲覧の履歴</span><span class="sxs-lookup"><span data-stu-id="b1676-107">Calling and web browsing history</span></span>
- <span data-ttu-id="b1676-108">電子メールとテキスト メッセージ</span><span class="sxs-lookup"><span data-stu-id="b1676-108">Email and text messages</span></span>
- <span data-ttu-id="b1676-109">連絡先</span><span class="sxs-lookup"><span data-stu-id="b1676-109">Contacts</span></span>
- <span data-ttu-id="b1676-110">予定表</span><span class="sxs-lookup"><span data-stu-id="b1676-110">Calendar</span></span>
-   <span data-ttu-id="b1676-111">パスワード</span><span class="sxs-lookup"><span data-stu-id="b1676-111">Passwords</span></span>
- <span data-ttu-id="b1676-112">フォト アプリやカメラ ロールの内容を含む、画像</span><span class="sxs-lookup"><span data-stu-id="b1676-112">Pictures, including what's in the photos app or camera roll</span></span>

<span data-ttu-id="b1676-113">**会社が常に確認できる情報**</span><span class="sxs-lookup"><span data-stu-id="b1676-113">**What your company can always see**</span></span>

- <span data-ttu-id="b1676-114">デバイス モデル (例: Google Pixel)</span><span class="sxs-lookup"><span data-stu-id="b1676-114">Device model, like Google Pixel</span></span>
- <span data-ttu-id="b1676-115">製造元 (例: Microsoft)</span><span class="sxs-lookup"><span data-stu-id="b1676-115">Manufacturer, like Microsoft</span></span>
- <span data-ttu-id="b1676-116">オペレーティング システム (例: iOS)</span><span class="sxs-lookup"><span data-stu-id="b1676-116">Operating system, like iOS</span></span>
- <span data-ttu-id="b1676-117">アプリ名 (例: Microsoft Word)</span><span class="sxs-lookup"><span data-stu-id="b1676-117">App names, like Microsoft Word</span></span>
- <span data-ttu-id="b1676-118">デバイスの所有者</span><span class="sxs-lookup"><span data-stu-id="b1676-118">Device owner</span></span>
- <span data-ttu-id="b1676-119">デバイス名</span><span class="sxs-lookup"><span data-stu-id="b1676-119">Device name</span></span>
- <span data-ttu-id="b1676-120">シリアル番号</span><span class="sxs-lookup"><span data-stu-id="b1676-120">Serial number</span></span>

<span data-ttu-id="b1676-121">**会社が確認できる場合がある情報**</span><span class="sxs-lookup"><span data-stu-id="b1676-121">**What your company might be able to see**</span></span>

-  <span data-ttu-id="b1676-122">電話番号: **会社**が所有するデバイスの場合は、ユーザーの電話番号を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b1676-122">Phone number: for **Corporate**-owned devices, your full phone number can be seen.</span></span> <span data-ttu-id="b1676-123">**個人**が所有するデバイスの場合は、会社が確認できるのは、ユーザーの電話番号の最後の 4 桁のみです。</span><span class="sxs-lookup"><span data-stu-id="b1676-123">For **Personal**-owned devices, just the last four digits of your phone number are visible to your company.</span></span> <span data-ttu-id="b1676-124">個々のデバイスの**所有権の種類**を確認するには、デバイスの **[デバイスの詳細]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1676-124">You can see the **Ownership Type** for each individual device  by opening that device's **Device Details** page.</span></span>
-  <span data-ttu-id="b1676-125">場所: 監視対象となっている iOS デバイスを紛失した場合を除き、会社はユーザーのデバイスの場所を確認できません。</span><span class="sxs-lookup"><span data-stu-id="b1676-125">Location: your company can never see your device's location, except if you have an iOS device that is supervised and has gotten lost.</span></span> [<span data-ttu-id="b1676-126">確認方法</span><span class="sxs-lookup"><span data-stu-id="b1676-126">How do I know?</span></span>](https://go.microsoft.com/fwlink/?linkid=853816)
- <span data-ttu-id="b1676-127">アプリ インベントリ: 会社で Mobile Threat Defense を使っている場合、iOS デバイス上のアプリの詳細を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="b1676-127">App inventory: if your company uses Mobile Threat Defense, they will be able to view what more details about the apps that are on your iOS device.</span></span> <span data-ttu-id="b1676-128">Mobile Threat Defense の詳細については、[こちら](you-are-prompted-to-install-mtd-ios.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1676-128">Find out more about [Mobile Threat Defense](you-are-prompted-to-install-mtd-ios.md).</span></span>
- <span data-ttu-id="b1676-129">ネットワーク情報: Android デバイスのネットワーク接続情報の一部は、社内サポートが確認できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1676-129">Network information: some information about network connections for Android devices may be available to your company support.</span></span> <span data-ttu-id="b1676-130">たとえば、デバイスを特定の建物内に維持するように会社が定めている場合、デバイスでは接続先のネットワークが識別されます。</span><span class="sxs-lookup"><span data-stu-id="b1676-130">For example, if your company requires devices to remain within a certain building, your device would identify the network where it is connected.</span></span> 
