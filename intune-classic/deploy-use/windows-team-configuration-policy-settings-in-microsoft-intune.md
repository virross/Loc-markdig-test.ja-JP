---
title: "Windows Team 構成ポリシー設定"
description: "Microsoft Intune **Windows 10 Team 全般構成ポリシー**を使用して、Microsoft Surface Hub などの登録済みの Windows 10 Team デバイスの設定を構成します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc7b2ea782fb6e8b29815192a3401cd00a02f781
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a><span data-ttu-id="b0b8b-103">Microsoft Intune の Windows Team 構成ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="b0b8b-103">Windows Team configuration policy settings in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b0b8b-104">Microsoft Intune **Windows 10 Team 全般構成ポリシー**を使用して、Microsoft Surface Hub などの登録済みの Windows 10 Team デバイスの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-104">Use the Microsoft Intune **Windows 10 Team general configuration policy** to configure settings for enrolled Windows 10 Team devices such as the Microsoft Surface Hub.</span></span>


|<span data-ttu-id="b0b8b-105">設定の名前</span><span class="sxs-lookup"><span data-stu-id="b0b8b-105">Setting name</span></span>|<span data-ttu-id="b0b8b-106">説明</span><span class="sxs-lookup"><span data-stu-id="b0b8b-106">Details</span></span>|
|----------------|-----------|
|<span data-ttu-id="b0b8b-107">**部屋にだれかがいるときに画面のスリープ状態を自動的に解除する**</span><span class="sxs-lookup"><span data-stu-id="b0b8b-107">**Allow screen to wake automatically when someone in the room**</span></span>|<span data-ttu-id="b0b8b-108">部屋にだれかがいるとセンサーで検出したときに、デバイスのスリープ状態を自動的に解除します。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-108">Allows the device to wake automatically when its sensor detects someone in the room.</span></span>|
|<span data-ttu-id="b0b8b-109">**ワイヤレス投影には PIN を必要とする**</span><span class="sxs-lookup"><span data-stu-id="b0b8b-109">**Require PIN for wireless projection**</span></span>|<span data-ttu-id="b0b8b-110">デバイスのワイヤレス投影機能を使用する前に暗証番号 (PIN) を入力しなければならないかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-110">Specifies whether you must enter a PIN before you can use the wireless projection capabilities of the device.</span></span>|
|<span data-ttu-id="b0b8b-111">**デバイスの更新プログラムのメンテナンス期間を設定する**</span><span class="sxs-lookup"><span data-stu-id="b0b8b-111">**Set a maintenance window for device updates**</span></span>|<span data-ttu-id="b0b8b-112">デバイスで更新を実行する期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-112">Configures the window when updates can take place to the device.</span></span> <span data-ttu-id="b0b8b-113">期間の開始時刻と長さ (1 ~ 5 時間) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-113">You can configure the start time of the window and the duration (from 1-5 hours).</span></span>|
|<span data-ttu-id="b0b8b-114">**Azure Operational Insights を有効にする**</span><span class="sxs-lookup"><span data-stu-id="b0b8b-114">**Enable Azure Operational Insights**</span></span>|<span data-ttu-id="b0b8b-115">Microsoft Operations Manager Suite の一部である Azure Operational Insights は、Windows 10 Team デバイスからログ ファイルのデータを収集、格納、分析します。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-115">Azure Operational Insights , part of the Microsoft Operations Manager suite collects, stores, and analyzes log file data from Windows 10 Team devices.</span></span><br /><br /><span data-ttu-id="b0b8b-116">Azure Operational insights に接続するには、**ワークスペース ID** と **ワークスペース キー**を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-116">To connect to Azure Operational insights, you must specify a **Workspace ID** and a **Workspace Key**.</span></span>|
|<span data-ttu-id="b0b8b-117">**Miracast ワイヤレス投影を有効にする**</span><span class="sxs-lookup"><span data-stu-id="b0b8b-117">**Enable Miracast wireless projection**</span></span>|<span data-ttu-id="b0b8b-118">Windows 10 Team デバイスで Miracast が有効になっているデバイスを使用して投影する場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-118">Enable this option if you want to let the Windows 10 Team device use Miracast enabled devices to project.</span></span><br /><br /><span data-ttu-id="b0b8b-119">このオプションを有効にする場合は、「**Miracast チャネル**」から、コンテンツの投影に使用する Miracast チャネルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-119">If you enable this option, from **Choose Miracast channel** select the Miracast channel used to project content.</span></span>|
|<span data-ttu-id="b0b8b-120">**[ようこそ] 画面に表示される会議の情報を選択する**</span><span class="sxs-lookup"><span data-stu-id="b0b8b-120">**Choose the meeting information displayed on the welcome screen**</span></span>|<span data-ttu-id="b0b8b-121">このオプションを有効にすると、**[ようこそ]** 画面の **[会議]** タイルに表示される情報を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-121">If you enable this option, you can choose the information that will be displayed on the **Meetings** tile of the **Welcome** screen.</span></span> <span data-ttu-id="b0b8b-122">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-122">You can:</span></span><br /><br /><span data-ttu-id="b0b8b-123">-   **開催者と時刻のみを表示する**</span><span class="sxs-lookup"><span data-stu-id="b0b8b-123">-   **Show organizer and time only**</span></span><br /><span data-ttu-id="b0b8b-124">-   **開催者、時刻、議題を表示する (非公開なミーティングの場合は議題を非表示)**</span><span class="sxs-lookup"><span data-stu-id="b0b8b-124">-   **Show organizer, time and subject (subject hidden for private meetings)**</span></span>|
|<span data-ttu-id="b0b8b-125">**ロック画面の背景画像 URL**</span><span class="sxs-lookup"><span data-stu-id="b0b8b-125">**Lockscreen background image URL**</span></span>|<span data-ttu-id="b0b8b-126">Windows 10 Team デバイスの **[ようこそ]** 画面に指定した URL のカスタム背景を表示する場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-126">Enable this setting to display a custom background on the **Welcome** screen of Windows 10 Team devices from the URL you specify.</span></span><br /><br /><span data-ttu-id="b0b8b-127">画像は PNG 形式である必要があり、URL は **https://** で始まっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0b8b-127">The image must be in PNG format and the URL must begin with **https://**.</span></span>|


### <a name="see-also"></a><span data-ttu-id="b0b8b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0b8b-128">See also</span></span>
[<span data-ttu-id="b0b8b-129">Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する</span><span class="sxs-lookup"><span data-stu-id="b0b8b-129">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

