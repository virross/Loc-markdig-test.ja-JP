---
title: "Windows Defender をオンにする | Microsoft Docs"
description: "Windows Defender をオンにし、会社のリソースにアクセスする方法について説明します。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d16dd2de-3ed5-474f-a04b-36dcd350162c
searchScope: User help
ROBOTS: 
ms.reviewer: shburbid
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 06471a8d929dc2708917d4860510ba5cbab10fb1
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="turn-on-windows-defender-to-access-company-resources"></a><span data-ttu-id="3f755-103">Windows Defender をオンにし、会社のリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="3f755-103">Turn on Windows Defender to access company resources</span></span>

<span data-ttu-id="3f755-104">学校や職場は、そのリソースにアクセスするデバイスが確実にセキュリティで保護されるようにしたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="3f755-104">Your work or school wants to ensure that devices accessing their resources are secured.</span></span> <span data-ttu-id="3f755-105">悪意のあるソフトウェアに対して Windows 内蔵の保護機能である [Windows Defender](https://www.microsoft.com/safety/pc-security/windows-defender.aspx) を適用する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="3f755-105">There are a few ways that they can use [Windows Defender](https://www.microsoft.com/safety/pc-security/windows-defender.aspx), Windows' built-in protection for malicious software.</span></span>

<span data-ttu-id="3f755-106">アクセスに問題があり、それを解消するには、Windows Defender でいくつかの設定を変更しなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="3f755-106">There are a few settings you may need to change on your Windows Defender to fix any access issues.</span></span> <span data-ttu-id="3f755-107">以下の手順では、場合によっては、コンピューター上のまざま場所に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f755-107">These steps may require you to go to a couple of different places on your computer.</span></span>

## <a name="turn-on-windows-defender"></a><span data-ttu-id="3f755-108">Windows Defender をオンにする</span><span class="sxs-lookup"><span data-stu-id="3f755-108">Turn on Windows Defender</span></span>

1. <span data-ttu-id="3f755-109">**[スタート]** で **[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f755-109">In **Start**, open **Control Panel**.</span></span>
2. <span data-ttu-id="3f755-110">**[管理ツール]**、**[グループ ポリシーの編集]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="3f755-110">Open **Administrative Tools** > **Edit group policy**.</span></span> <span data-ttu-id="3f755-111">新しいウィンドウで **[ローカル グループ ポリシー エディター]** が開きます。</span><span class="sxs-lookup"><span data-stu-id="3f755-111">This will open the **Local Group Policy Editor** in a new window.</span></span>
3. <span data-ttu-id="3f755-112">**[コンピューターの構成]**、**[管理テンプレート]**、**[Windows コンポーネント]**、**[Windows Defender ウイルス対策]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="3f755-112">Open **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Windows Defender Antivirus**.</span></span> <span data-ttu-id="3f755-113">**[Windows Defender ウイルス対策を無効にします]** という設定がその他の設定のフォルダーの下にあります。</span><span class="sxs-lookup"><span data-stu-id="3f755-113">The setting **Turn off Windows Defender Antivirus** is underneath the folders of other settings.</span></span> 
4. <span data-ttu-id="3f755-114">**[Windows Defender ウイルス対策を無効にします]** を開き、**[無効]** または **[未構成]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f755-114">Open **Turn off Windows Defender Antivirus** and make sure it's set to **Disabled** or **Not configured**.</span></span>

## <a name="turn-on-real-time-protection"></a><span data-ttu-id="3f755-115">リアルタイム保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="3f755-115">Turn on Real-time Protection</span></span>

<span data-ttu-id="3f755-116">リアルタイム保護がオンになっていることを確認します。**[スタート]** に移動し、**[Windows Defender セキュリティ センター]** を検索します。</span><span class="sxs-lookup"><span data-stu-id="3f755-116">Check to make sure that Real-time Protection is turned on by going to **Start** and searching for **Windows Defender Security Center**.</span></span> <span data-ttu-id="3f755-117">**[ウイルスと脅威の防止の設定]** を選択し、**[リアルタイム保護]** と **[クラウドによる保護]** の両方が **[オン]** になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f755-117">Select **Virus and threat protection settings** and confirm that both **Real-time protection** and **Cloud-delivered protection** are switched to **On**.</span></span> <span data-ttu-id="3f755-118">これらのオプションが表示されない場合、次の手順で有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f755-118">If these options aren't appearing, do the following to enable them:</span></span>

1. <span data-ttu-id="3f755-119">**[スタート]** で **[コントロール パネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f755-119">In **Start**, open **Control Panel**.</span></span>
2. <span data-ttu-id="3f755-120">**[管理ツール]**、**[グループ ポリシーの編集]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="3f755-120">Open **Administrative Tools** > **Edit group policy**.</span></span> <span data-ttu-id="3f755-121">新しいウィンドウで **[ローカル グループ ポリシー エディター]** が開きます。</span><span class="sxs-lookup"><span data-stu-id="3f755-121">This will open the **Local Group Policy Editor** in a new window.</span></span>
3. <span data-ttu-id="3f755-122">**[コンピューターの構成]**、**[管理テンプレート]**、**[Windows コンポーネント]**、**[Windows Defender セキュリティ センター]**、**[ウイルスと脅威の防止]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="3f755-122">Open **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Windows Defender Security Center** > **Virus and threat protection**.</span></span>
4. <span data-ttu-id="3f755-123">**[Virus and threat protection area]\(ウイルスと脅威の防止の領域\)** という設定を開き、**[無効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3f755-123">Open the setting **Virus and threat protection area** and set it to **Disabled**.</span></span>

## <a name="update-your-antivirus-definitions"></a><span data-ttu-id="3f755-124">ウイルス対策定義を更新する</span><span class="sxs-lookup"><span data-stu-id="3f755-124">Update your antivirus definitions</span></span>

<span data-ttu-id="3f755-125">ウイルス対策定義が最新の状態になっていることを確認します。**[スタート]** に移動し、**[Windows Defender セキュリティ センター]** を検索します。</span><span class="sxs-lookup"><span data-stu-id="3f755-125">Check to make sure that your antivirus definitions are up to date by going to **Start** and searching for **Windows Defender Security Center**.</span></span> <span data-ttu-id="3f755-126">**[保護の更新]** と **[更新プログラムの確認]** を選択し、現行のウイルス対策保護がデバイスに適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f755-126">Select **Protection updates** and **Check for updates** to make sure that your device has current protection against viruses.</span></span> <span data-ttu-id="3f755-127">このオプションが表示されない場合、「[リアルタイム保護を有効にする](turn-on-defender-windows.md#turn-on-real-time-protection)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f755-127">If this option doesn't appear, follow the steps in [Turn on Real-time Protection](turn-on-defender-windows.md#turn-on-real-time-protection)</span></span>

<span data-ttu-id="3f755-128">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="3f755-128">Still need help?</span></span> <span data-ttu-id="3f755-129">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="3f755-129">Contact your company support.</span></span> <span data-ttu-id="3f755-130">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="3f755-130">For their contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
