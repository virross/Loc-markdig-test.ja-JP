---
title: "ポータル サイト Web サイトからデバイスをリセットする | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3182a85-328b-45b4-bf7a-9f6249984641
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 3ef122b5e22b1bf562ed4d75c726e697f08abbe5
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="reset-your-device-from-the-company-portal-website"></a><span data-ttu-id="e37c3-102">ポータル サイト Web サイトからデバイスをリセットする</span><span class="sxs-lookup"><span data-stu-id="e37c3-102">Reset your device from the Company Portal website</span></span>

<span data-ttu-id="e37c3-103">デバイスが紛失した、または盗難にあった場合は、データへの不正なアクセスを防ぐため、デバイスを出荷時の状態にリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="e37c3-103">If your device gets lost or stolen, you might want to reset it to its factory default settings to prevent unauthorized access to your data.</span></span> <span data-ttu-id="e37c3-104">[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)を使用してデバイスをリモートでリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="e37c3-104">You can reset your device remotely by using the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span> <span data-ttu-id="e37c3-105">ポータル サイト Web サイトは、Intune で登録したコンピューターとデバイスの管理に使用できる Web ページです。</span><span class="sxs-lookup"><span data-stu-id="e37c3-105">The Company Portal website is a web page that you can use to manage computers and devices that you have enrolled in Intune.</span></span> <span data-ttu-id="e37c3-106">この Web サイトを使用すると、ポータル サイト アプリを使用して実行できるタスクのほとんどを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e37c3-106">You can use this website to do most of the same tasks that you can do when using your Company Portal app.</span></span>

<span data-ttu-id="e37c3-107">デバイスをリセットすると、そのデバイスはポータル サイトに表示されなくなり、出荷時の状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="e37c3-107">If you reset your device, it will no longer be listed in the Company Portal, and the device will be reset to its factory default settings.</span></span>

> [!Note]
> <span data-ttu-id="e37c3-108">登録済みの別のデバイスで以下の手順を実行することもできます。その場合は、該当するデバイスでポータル サイト アプリを開き、リセットの場合と同様の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e37c3-108">You can also perform the following steps from another device that you've enrolled by opening the Company Portal app on that device and going through similar steps to complete the reset.</span></span> 

<span data-ttu-id="e37c3-109">デバイスをリセットするには:</span><span class="sxs-lookup"><span data-stu-id="e37c3-109">To reset your device:</span></span>

1. <span data-ttu-id="e37c3-110">[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)で、__[メニュー]__ ボタンをタップし、__[デバイス]__ を選択します。</span><span class="sxs-lookup"><span data-stu-id="e37c3-110">On the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog), tap the __menu__ button, then select __My Devices__.</span></span>

2. <span data-ttu-id="e37c3-111">__[デバイス]__ ページで、名前を変更するデバイスの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e37c3-111">On the __My Devices__ page, select the name of the device you want to rename.</span></span>

   ![リスト表示されていないデバイスの登録または不明なデバイスの識別を求めるバナーの上に 2 つの不明なデバイスが示された、[デバイス] ページのスクリーンショット。](./media/macOS_enroll_002_tap_here_banner.png)

3. <span data-ttu-id="e37c3-113">デバイスがポップアップ ウィンドウに開きます。</span><span class="sxs-lookup"><span data-stu-id="e37c3-113">The device will open in a popup window.</span></span> <span data-ttu-id="e37c3-114">**[リセット]** ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="e37c3-114">Tap the **Reset** button.</span></span>

   ![<span data-ttu-id="e37c3-115">[名前の変更]、[削除]、[デバイスのリセット]、[パスコードのリセット]、[リモート ロック] を含む、ポータル Web サイト上の選択されたデバイスに対するすべてのオプション。</span><span class="sxs-lookup"><span data-stu-id="e37c3-115">All options for a selected device on the Company Portal website, including Rename, Remove, Reset Device, Reset Passcode, and Remote Lock.</span></span> ](./media/iwp-screen-with-all-options.png)

4. <span data-ttu-id="e37c3-116">出荷時の状態に戻し、デバイスのすべてのコンテンツを消去しようとしていることを知らせる警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e37c3-116">A warning message will appear to let you know that you are about to erase all content on your device by resetting it to the factory default settings.</span></span> <span data-ttu-id="e37c3-117">操作を続行しても問題がない場合は、**[リセット]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="e37c3-117">Tap **Reset** to confirm that this is what you want to do.</span></span>

<span data-ttu-id="e37c3-118">これでデバイスがリセットされました。</span><span class="sxs-lookup"><span data-stu-id="e37c3-118">Your device has now been reset.</span></span>

<span data-ttu-id="e37c3-119">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="e37c3-119">Still need help?</span></span> <span data-ttu-id="e37c3-120">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="e37c3-120">Contact your company support.</span></span> <span data-ttu-id="e37c3-121">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="e37c3-121">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
