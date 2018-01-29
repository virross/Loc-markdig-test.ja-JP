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
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: 08d4d40241456c0941d5d9aa11e20827da6201b9
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a><span data-ttu-id="850d0-103">モバイル デバイスの登録方法の選択</span><span class="sxs-lookup"><span data-stu-id="850d0-103">Choose how to enroll mobile devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="850d0-104">次の一連の質問に答えることで、管理するデバイスの最適な登録方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="850d0-104">Your answers to this series of questions will help determine the best enrollment method for the devices you manage.</span></span>

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a><span data-ttu-id="850d0-105">**企業所有の専用デバイスはどのような方法で管理しますか。**</span><span class="sxs-lookup"><span data-stu-id="850d0-105">**How will you manage dedicated, corporate-owned devices?**</span></span>

> [!div class="button"]
> [<span data-ttu-id="850d0-106">iOS DEP ></span><span class="sxs-lookup"><span data-stu-id="850d0-106">iOS DEP ></span></span>](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
> [<span data-ttu-id="850d0-107">iOS のセットアップ アシスタント ></span><span class="sxs-lookup"><span data-stu-id="850d0-107">iOS Setup Assistant ></span></span>](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
> [<span data-ttu-id="850d0-108">IMEI によるタグ付け ></span><span class="sxs-lookup"><span data-stu-id="850d0-108">Tag with IMEI ></span></span>](/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  <span data-ttu-id="850d0-109">次のようにして、会社が所有するデバイスを専用ユーザーに登録できます。</span><span class="sxs-lookup"><span data-stu-id="850d0-109">You can enroll corporate-owned devices with dedicated users in the following ways:</span></span>

  - <span data-ttu-id="850d0-110">**Apple のデバイス登録プログラム (DEP)** - DEP で購入し、管理している iOS デバイスが対象となります。登録プロファイルが利用されます。</span><span class="sxs-lookup"><span data-stu-id="850d0-110">**Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile.</span></span> <span data-ttu-id="850d0-111">利用者がデバイスの電源を初めて入れると、デバイスは DEP プロファイルをダウンロードして、Intune に登録します。</span><span class="sxs-lookup"><span data-stu-id="850d0-111">When users power on their devices for the first time, the device downloads the DEP profile and enrolls with Intune.</span></span>

  - <span data-ttu-id="850d0-112">**Mac の Apple Configurator** - Apple Configurator は Mac PC で実行される Apple アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="850d0-112">**Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC.</span></span> <span data-ttu-id="850d0-113">USB ケーブルで iOS デバイスを Mac に接続し、デバイスに登録プロファイルをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="850d0-113">You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device.</span></span> <span data-ttu-id="850d0-114">デバイスを工場出荷時にリセットして登録できる場合、セットアップ アシスタント登録を使用します。</span><span class="sxs-lookup"><span data-stu-id="850d0-114">If you can factory reset devices to enroll them use Setup Assistant enrollment.</span></span>

  - <span data-ttu-id="850d0-115">**IMEI 番号でのタグ付け** - 会社所有デバイスの IMEI (携帯機器の国際的な識別番号) をインポートすることで、Intune でデバイスに会社所有のタグを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="850d0-115">**Tag with IMEI number** - By importing the international mobile equipment identity (IMEI) numbers of company-owned devices you can tag them as company-owned devices in Intune.</span></span> <span data-ttu-id="850d0-116">これは、専用の ("シングル ユーザー" の) Windows および Android デバイスを会社所有として識別する唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="850d0-116">This is the only way to identify dedicated ("single-user") Windows and Android devices as corporate-owned.</span></span> <span data-ttu-id="850d0-117">Apple のデバイス登録プログラムまたは Apple Configurator に登録されない iOS デバイスを、IMEI 番号でタグ付けすることもできます。</span><span class="sxs-lookup"><span data-stu-id="850d0-117">iOS devices that won't be enrolled with Apple's device enrollment program or Apple Configurator can also be tagged with an IMEI number.</span></span> <span data-ttu-id="850d0-118">デバイスを事前宣言することで "会社" としてタグ付けした後で、ユーザーに配布できます。</span><span class="sxs-lookup"><span data-stu-id="850d0-118">After predeclaring the device so it will be tagged as "corporate", you can distribute devices to users.</span></span> <span data-ttu-id="850d0-119">その後、ユーザーがポータル サイトをインストールすることで自分のデバイスを専用デバイスとして登録し、電子メール、アプリ、データなど、会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="850d0-119">Users can then enroll their devices as a dedicated devices by installing the Company Portal to access company resources such as email, apps, and data.</span></span>

> [!div class="button"]
> [<span data-ttu-id="850d0-120">< 戻る</span><span class="sxs-lookup"><span data-stu-id="850d0-120">< Back</span></span>](choose-how-to-enroll-devices3.md)
