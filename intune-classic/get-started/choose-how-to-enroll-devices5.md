---
title: "モバイル デバイスの登録方法の選択"
description: "いくつかの簡単な質問に答えることによって、Intune でモバイル デバイスを登録する方法を決定する"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: d5c9daa7621b343324fcf3d255bc9bfe05f50de9
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a><span data-ttu-id="a4191-103">モバイル デバイスの登録方法の選択</span><span class="sxs-lookup"><span data-stu-id="a4191-103">Choose how to enroll mobile devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="a4191-104">次の一連の質問に答えることで、管理するデバイスの最適な登録方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="a4191-104">Your answers to this series of questions will help determine the best enrollment method for the devices you manage.</span></span>

## <a name="how-will-you-manage-shared-ios-devices"></a><span data-ttu-id="a4191-105">**共有 iOS デバイスはどのような方法で管理しますか。**</span><span class="sxs-lookup"><span data-stu-id="a4191-105">**How will you manage shared iOS devices?**</span></span>

> [!div class="button"]
> [<span data-ttu-id="a4191-106">iOS の DEP 登録 ></span><span class="sxs-lookup"><span data-stu-id="a4191-106">iOS DEP Enrollment ></span></span>](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]
> [<span data-ttu-id="a4191-107">iOS の直接登録 ></span><span class="sxs-lookup"><span data-stu-id="a4191-107">iOS Direct enrollment ></span></span>](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
> [!div class="button"]
> [<span data-ttu-id="a4191-108">DEM 登録 ></span><span class="sxs-lookup"><span data-stu-id="a4191-108">DEM enrollment ></span></span>](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - <span data-ttu-id="a4191-109">**Apple のデバイス登録プログラム (DEP)** - DEP で購入し、管理している iOS デバイスが対象となります。登録プロファイルが利用されます。</span><span class="sxs-lookup"><span data-stu-id="a4191-109">**Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile.</span></span> <span data-ttu-id="a4191-110">利用者がデバイスの電源を初めて入れると、デバイスが DEP プロファイルをダウンロードし、プロファイル DEP で登録します。</span><span class="sxs-lookup"><span data-stu-id="a4191-110">When users power on their devices for the first time, the device downloads the DEP profile and enrolls with the profile DEP.</span></span>

  - <span data-ttu-id="a4191-111">**Mac の Apple Configurator** - Apple Configurator は Mac PC で実行される Apple アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="a4191-111">**Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC.</span></span> <span data-ttu-id="a4191-112">USB ケーブルで iOS デバイスを Mac に接続し、デバイスに登録プロファイルをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a4191-112">You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device.</span></span> <span data-ttu-id="a4191-113">デバイスを工場出荷時にリセットして登録できる場合、セットアップ アシスタント登録を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4191-113">If you can factory reset devices to enroll them use Setup Assistant enrollment.</span></span> <span data-ttu-id="a4191-114">デバイスを工場出荷時にリセットしない場合、直接登録を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4191-114">If you don't want to factory reset devices, use Direct enrollment.</span></span>

  - <span data-ttu-id="a4191-115">**デバイス登録マネージャー** - Intune のデバイス登録マネージャー (DEM) を使用して、管理者は 1 つのユーザー アカウントに多数のモバイル デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="a4191-115">**Device Enrollment Manager** - Intune's device enrollment manager (DEM) allows a manager or administrator to enroll many mobile devices with a single user account.</span></span> <span data-ttu-id="a4191-116">これらのデバイスは、ユーザー アフィニティ (つまり専用ユーザー) を持つことはできず、ポータル サイト アプリをインストールしてサインインすることで登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4191-116">These devices cannot have user affinity (i.e. dedicated users) and must enroll by installing and signing in to the Company Portal app.</span></span>

> [!div class="button"]
> [<span data-ttu-id="a4191-117">< 戻る</span><span class="sxs-lookup"><span data-stu-id="a4191-117">< Back</span></span>](choose-how-to-enroll-devices3.md)
