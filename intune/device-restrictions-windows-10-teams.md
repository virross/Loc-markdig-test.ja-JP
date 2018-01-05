---
title: "Windows 10 Team 向けの Intune デバイス制限"
titlesuffix: Azure portal
description: "Windows 10 Team デバイスで使用できるデバイス制限について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 776fe5e67e99ea50798813717c90d9e52cb7812a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="771ca-103">Microsoft Intune での Windows 10 Team デバイスの制限設定</span><span class="sxs-lookup"><span data-stu-id="771ca-103">Windows 10 Team device restriction settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="apps-and-experience"></a><span data-ttu-id="771ca-104">アプリとエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="771ca-104">Apps and experience</span></span>

- <span data-ttu-id="771ca-105">**[ユーザーの入室時に画面のスリープ状態を解除する]** - 部屋にだれかがいるとセンサーで検出したときに、デバイスのスリープ状態を自動的に解除します。</span><span class="sxs-lookup"><span data-stu-id="771ca-105">**Wake screen when someone in room** - Allows the device to wake automatically when its sensor detects someone in the room.</span></span>
- <span data-ttu-id="771ca-106">**[ようこそ画面に表示される会議情報]** - このオプションを有効にすると、ようこそ画面の [Meetings (会議)] タイルに表示される情報を選択できます。</span><span class="sxs-lookup"><span data-stu-id="771ca-106">**Meeting information displayed on welcome screen** - Enable this option to choose the information that is displayed on the Meetings tile of the Welcome screen.</span></span> <span data-ttu-id="771ca-107">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="771ca-107">You can:</span></span>
    - <span data-ttu-id="771ca-108">**[開催者と時刻のみの表示]**</span><span class="sxs-lookup"><span data-stu-id="771ca-108">**Show organizer and time only**</span></span>
    - <span data-ttu-id="771ca-109">**[開催者、時刻、議題の表示 (非公開なミーティングの場合は議題を非表示)]**</span><span class="sxs-lookup"><span data-stu-id="771ca-109">**Show organizer, time, and subject (subject hidden for private meetings)**</span></span>
- <span data-ttu-id="771ca-110">**[ようこそ画面の背景画像の URL]** - Windows 10 Team デバイスの**ようこそ**画面に指定した URL のカスタム背景を表示する場合は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="771ca-110">**Welcome screen background image URL** - Enable this setting to display a custom background on the **Welcome** screen of Windows 10 Team devices from the URL you specify.</span></span><br><span data-ttu-id="771ca-111">画像は PNG 形式である必要があり、URL は **https://** で始まっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="771ca-111">The image must be in PNG format and the URL must begin with **https://**.</span></span>

## <a name="azure-operational-insights"></a><span data-ttu-id="771ca-112">Azure Operational Insights</span><span class="sxs-lookup"><span data-stu-id="771ca-112">Azure operational insights</span></span>

- <span data-ttu-id="771ca-113">**[Azure Operational Insights]** - Microsoft Operations Manager Suite の一部である Azure Operational Insights は、Windows 10 Team デバイスからログ ファイルのデータを収集、格納、分析します。</span><span class="sxs-lookup"><span data-stu-id="771ca-113">**Azure Operational Insights** - Azure Operational Insights, part of the Microsoft Operations Manager suite collects, stores, and analyzes log file data from Windows 10 Team devices.</span></span>
<span data-ttu-id="771ca-114">Azure Operational insights に接続するには、**ワークスペース ID** と **ワークスペース キー**を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="771ca-114">To connect to Azure Operational insights, you must specify a **Workspace ID** and a **Workspace Key**.</span></span>

## <a name="maintenance"></a><span data-ttu-id="771ca-115">メンテナンス</span><span class="sxs-lookup"><span data-stu-id="771ca-115">Maintenance</span></span>

- <span data-ttu-id="771ca-116">**[更新プログラムのメンテナンス期間]** - デバイスで更新を実行する期間を構成します。</span><span class="sxs-lookup"><span data-stu-id="771ca-116">**Maintenance window for updates** - Configures the window when updates can take place to the device.</span></span> <span data-ttu-id="771ca-117">期間の **[開始時刻]** と **[期間 (時間単位)]** (1 時間から 5 時間) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="771ca-117">You can configure the **Start time** of the window and the **Duration in hours** (from 1-5 hours).</span></span>

## <a name="wireless-projection"></a><span data-ttu-id="771ca-118">ワイヤレス投影</span><span class="sxs-lookup"><span data-stu-id="771ca-118">Wireless projection</span></span>

- <span data-ttu-id="771ca-119">**[ワイヤレス投影の PIN]** - デバイスのワイヤレス投影機能を使用する前に暗証番号 (PIN) を入力しなければならないかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="771ca-119">**PIN for wireless projection** - Specifies whether you must enter a PIN before you can use the wireless projection capabilities of the device.</span></span>
- <span data-ttu-id="771ca-120">**[Miracast ワイヤレス投影]** - Windows 10 Team デバイスで Miracast が有効になっているデバイスを使用して投影する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="771ca-120">**Miracast wireless projection** - If you want to let the Windows 10 Team device use Miracast enabled devices to project, select this option.</span></span>
- <span data-ttu-id="771ca-121">**[Miracast ワイヤレス投影チャネル]** - 接続を確立するために使用される Miracast チャネルを選択します。</span><span class="sxs-lookup"><span data-stu-id="771ca-121">**Miracast wireless projection channel** - Choose the Miracast channel that will be used to establish the connection.</span></span>


## <a name="next-steps"></a><span data-ttu-id="771ca-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="771ca-122">Next steps</span></span>

<span data-ttu-id="771ca-123">「[Microsoft Intune でデバイスの制限設定を構成する方法](device-restrictions-configure.md)」の情報を使って、プロファイルを保存し、ユーザーとデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="771ca-123">Use the information in [How to configure device restriction settings](device-restrictions-configure.md) to save, and assign the profile to users and devices.</span></span>
