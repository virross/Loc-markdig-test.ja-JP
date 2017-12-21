---
title: "デバイスを管理する方法を選択する"
description: "デバイスを登録および管理するさまざまな方法について説明します。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/16/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 48bba8210c1b66f951c62bbe3a014b67b0c665f0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="choose-how-to-manage-devices"></a><span data-ttu-id="2f6a0-103">デバイスを管理する方法を選択する</span><span class="sxs-lookup"><span data-stu-id="2f6a0-103">Choose how to manage devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="2f6a0-104">アプリのデプロイやデバイス設定の制御など、Intune が提供する多くの機能を活用するには、デバイスを*管理*する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-104">To take advantage of the many features that Intune offers, such as app deployment and control of device settings, your devices must be *managed*.</span></span> <span data-ttu-id="2f6a0-105">デバイスを管理する方法は、使用する Intune の機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-105">How you manage devices depends on the Intune capabilities you want to use.</span></span> <span data-ttu-id="2f6a0-106">このトピックは、ニーズを満たす方法の選択に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-106">This topic helps you choose the method that meets your needs.</span></span>

<span data-ttu-id="2f6a0-107">iOS、Mac OS X、Android、または Windows Phone を実行するデバイスを管理するために、デバイスを*登録*します。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-107">To manage devices that run iOS, Mac OS X, Android, or Windows Phone, you must *enroll* them.</span></span>

<span data-ttu-id="2f6a0-108">Windows PC を管理するには、2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-108">To manage Windows PCs, you have two choices:</span></span>

1. <span data-ttu-id="2f6a0-109">デバイスを登録する。**または、**</span><span class="sxs-lookup"><span data-stu-id="2f6a0-109">Enroll the device **or**</span></span>
2. <span data-ttu-id="2f6a0-110">*Intune ソフトウェア クライアント*をインストールする。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-110">Install the *Intune software client*.</span></span>

## <a name="decide-which-method-to-use"></a><span data-ttu-id="2f6a0-111">どの方法を使用するか判断する</span><span class="sxs-lookup"><span data-stu-id="2f6a0-111">Decide which method to use</span></span>
<span data-ttu-id="2f6a0-112">このフローでどのようにデバイスを管理するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-112">Use this decision flow to decide how to get your devices managed.</span></span>

![デバイス管理の開始方法の決定フロー](./media/choose-manage-method.png)

<span data-ttu-id="2f6a0-114">ほとんどの機能を利用するために Windows PC を登録します。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-114">Enroll Windows PCs to get the most functionality.</span></span> <span data-ttu-id="2f6a0-115">ただし、Intune ソフトウェア クライアントは、以下により適している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-115">However, the Intune software client might be more suitable for:</span></span>

- <span data-ttu-id="2f6a0-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="2f6a0-116">Windows 7</span></span>
- <span data-ttu-id="2f6a0-117">Windows のソフトウェア更新プログラムとライセンス使用状況</span><span class="sxs-lookup"><span data-stu-id="2f6a0-117">Windows software updates and license usage</span></span>
- <span data-ttu-id="2f6a0-118">Endpoint Protection および Windows ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="2f6a0-118">Endpoint Protection and Windows Firewall</span></span>
- <span data-ttu-id="2f6a0-119">TeamViewer ソフトウェアを使用したユーザーへのリモート アシスタンス</span><span class="sxs-lookup"><span data-stu-id="2f6a0-119">Remote assistance to users using the TeamViewer software</span></span>

<span data-ttu-id="2f6a0-120">それぞれの方法での管理機能の詳細については、モバイル デバイスの管理に関するページを参照してください (/intune/supported-devices-browserssoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-120">For a detailed listing of the management capabilities you'll get with each method, see [Mobile device managem/intune/supported-devices-browserssoft-intune).</span></span>
<span data-ttu-id="2f6a0-121">Intune がサポートしているデバイスと PC については、「[サポートされるモバイル デバイスとコンピューター](/intune/supported-devices-browsers#intune-supported-devices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6a0-121">For information about the devices and PCs that Intune supports, see [Supported mobile devices and computers](/intune/supported-devices-browsers#intune-supported-devices).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2f6a0-122">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2f6a0-122">Next steps</span></span>

- [<span data-ttu-id="2f6a0-123">モバイル デバイスの登録方法の選択</span><span class="sxs-lookup"><span data-stu-id="2f6a0-123">Choose how to enroll mobile devices</span></span>](/intune-classic/get-started/choose-how-to-enroll-devices1)
- [<span data-ttu-id="2f6a0-124">Intune PC クライアント ソフトウェアを使用して Windows PC を管理する</span><span class="sxs-lookup"><span data-stu-id="2f6a0-124">Manage Windows PCs with Intune PC client software</span></span>](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune)
- <span data-ttu-id="2f6a0-125">[Microsoft Intune を使用した Exchange ActiveSync モバイル デバイスの管理](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="2f6a0-125">[Exchange ActiveSync mobile device management with Microsoft Intune](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).</span></span>
