---
title: "ポリシーを使用して Windows PC 管理を簡略化する"
description: "Windows PC 管理ポリシーと Microsoft Intune Center の設定について説明します。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 479656b54c98e673e11066305da2440da53a802b
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-policies-to-simplify-windows-pc-management"></a><span data-ttu-id="a9b28-103">ポリシーを使用して Windows PC 管理を簡略化する</span><span class="sxs-lookup"><span data-stu-id="a9b28-103">Use policies to simplify Windows PC management</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="a9b28-104">Intune ソフトウェア クライアントを実行することにより Windows デスクトップを PC として管理するには、Intune 管理コンソールの **[コンピューターの管理]** ポリシーにあるポリシーだけを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9b28-104">To manage Windows desktops as PCs, by running the Intune software client on them, you can use only the policies that are under **Computer Management** policies in the Intune admin console.</span></span> <span data-ttu-id="a9b28-105">管理コンソールに表示される他のすべてのポリシーは、モバイル デバイス専用です。</span><span class="sxs-lookup"><span data-stu-id="a9b28-105">All of the other policies listed in the admin console are for mobile devices only.</span></span> <span data-ttu-id="a9b28-106">**[コンピューターの管理]** のポリシーを使用して、Microsoft Intune Center で設定を構成し、PC の更新を制御し、PC の Windows ファイアウォールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a9b28-106">Using the **Computer Management** policies, you can configure the settings in the Microsoft Intune Center, control updates to PCs, and configure Windows Firewall for PCs.</span></span>

![Windows PC のポリシー テンプレート](../media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a><span data-ttu-id="a9b28-108">Microsoft Intune Center の管理</span><span class="sxs-lookup"><span data-stu-id="a9b28-108">Manage the Microsoft Intune Center</span></span>
<span data-ttu-id="a9b28-109">ユーザーは、Intune ソフトウェア クライアントを **Microsoft Intune Center** として確認します。</span><span class="sxs-lookup"><span data-stu-id="a9b28-109">Users see the Intune software client as the **Microsoft Intune Center**.</span></span> <span data-ttu-id="a9b28-110">Microsoft Intune Center を使用してユーザーは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a9b28-110">The Microsoft Intune Center lets users:</span></span>

-   <span data-ttu-id="a9b28-111">ポータル サイトからアプリケーションを取得する。</span><span class="sxs-lookup"><span data-stu-id="a9b28-111">Get applications from the company portal.</span></span>

-   <span data-ttu-id="a9b28-112">更新プログラムを確認する。</span><span class="sxs-lookup"><span data-stu-id="a9b28-112">Check for updates.</span></span>

-   <span data-ttu-id="a9b28-113">Microsoft Intune Endpoint Protection を管理する。</span><span class="sxs-lookup"><span data-stu-id="a9b28-113">Manage Microsoft Intune Endpoint Protection.</span></span>

-  <span data-ttu-id="a9b28-114">リモート アシスタンスを要求する。</span><span class="sxs-lookup"><span data-stu-id="a9b28-114">Request remote assistance.</span></span>

<span data-ttu-id="a9b28-115">Microsoft Intune Center は、管理されているすべてコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a9b28-115">The Microsoft Intune Center is installed on all managed computers.</span></span> <span data-ttu-id="a9b28-116">Intune ポリシーで次の設定を構成でき、各設定は Microsoft Intune Center でユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9b28-116">You can configure the following settings in an Intune policy, and these are displayed to users in the Microsoft Intune Center:</span></span>

|<span data-ttu-id="a9b28-117">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="a9b28-117">Policy setting</span></span>|<span data-ttu-id="a9b28-118">説明</span><span class="sxs-lookup"><span data-stu-id="a9b28-118">Details</span></span>|
|------------------|--------------------|
|<span data-ttu-id="a9b28-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="a9b28-119">**Name**</span></span>|<span data-ttu-id="a9b28-120">コンピューターを管理する管理者の名前。</span><span class="sxs-lookup"><span data-stu-id="a9b28-120">The name of the administrator who manages the computer.</span></span><br /><span data-ttu-id="a9b28-121">最大文字数:40 字</span><span class="sxs-lookup"><span data-stu-id="a9b28-121">Maximum length: 40 characters</span></span>|
|<span data-ttu-id="a9b28-122">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="a9b28-122">**Phone number**</span></span>|<span data-ttu-id="a9b28-123">コンピューターを管理する管理者の電話番号。</span><span class="sxs-lookup"><span data-stu-id="a9b28-123">The telephone number of the administrator who manages the computer.</span></span><br /><span data-ttu-id="a9b28-124">最大文字数:20 字</span><span class="sxs-lookup"><span data-stu-id="a9b28-124">Maximum length: 20 characters</span></span>|
|<span data-ttu-id="a9b28-125">**電子メール アドレス**</span><span class="sxs-lookup"><span data-stu-id="a9b28-125">**Email address**</span></span>|<span data-ttu-id="a9b28-126">コンピューターを管理する管理者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="a9b28-126">The email address of the administrator who manages the computer.</span></span><br /><span data-ttu-id="a9b28-127">最大文字数:40 字</span><span class="sxs-lookup"><span data-stu-id="a9b28-127">Maximum length: 40 characters</span></span>|
|<span data-ttu-id="a9b28-128">**Web サイト名**</span><span class="sxs-lookup"><span data-stu-id="a9b28-128">**Web site name**</span></span>|<span data-ttu-id="a9b28-129">ユーザー向けのサポート Web サイトの名前。</span><span class="sxs-lookup"><span data-stu-id="a9b28-129">The name of your support website for users.</span></span><br /><span data-ttu-id="a9b28-130">最大文字数:40 字</span><span class="sxs-lookup"><span data-stu-id="a9b28-130">>Maximum length: 40 characters</span></span>|
|<span data-ttu-id="a9b28-131">**Web サイトの URL**</span><span class="sxs-lookup"><span data-stu-id="a9b28-131">**Web site URL**</span></span>|<span data-ttu-id="a9b28-132">サポート Web サイトの URL。</span><span class="sxs-lookup"><span data-stu-id="a9b28-132">The URL of your support website.</span></span><br /><span data-ttu-id="a9b28-133">最大文字数:150 字</span><span class="sxs-lookup"><span data-stu-id="a9b28-133">Maximum length: 150 characters</span></span>|
|<span data-ttu-id="a9b28-134">**メモ**</span><span class="sxs-lookup"><span data-stu-id="a9b28-134">**Notes**</span></span>|<span data-ttu-id="a9b28-135">ユーザーに表示されるメモ。</span><span class="sxs-lookup"><span data-stu-id="a9b28-135">A note that is displayed to users.</span></span><br /><span data-ttu-id="a9b28-136">最大文字数:120 字</span><span class="sxs-lookup"><span data-stu-id="a9b28-136">Maximum length: 120 characters</span></span>|

<span data-ttu-id="a9b28-137">Windows PC で構成できるポリシーと設定の詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b28-137">See the following resources for information about policies and settings that you can configure for Windows PCs:</span></span>

- <span data-ttu-id="a9b28-138">[Microsoft Intune でソフトウェア更新プログラムを使用して Windows PC を最新の状態に保つ](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) - 管理対象コンピューターで Microsoft やサード パーティのソフトウェア更新プログラムを確認し、ダウンロードするように指示するポリシーについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="a9b28-138">[Keep Windows PCs up to date with software updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) - These policies make managed computers check for, and download software updates from, Microsoft and from third parties.</span></span> <span data-ttu-id="a9b28-139">この更新プログラムには、OS のアップグレード (Windows 7 から Windows 10 へのアップグレードまたは Windows 10 のあるバージョンからそれ以降のバージョンへのアップグレード) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="a9b28-139">These updates do not include OS upgrades (e.g., upgrading from Windows 7 to Windows 10, or upgrades from one Windows 10 version to a later version).</span></span>

- <span data-ttu-id="a9b28-140">[Microsoft Intune の Endpoint Protection を使用して Windows PC を保護する](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) - スキャンのスケジュール、マルウェアが検出されたときに実行するアクションなどの設定について説明しています。</span><span class="sxs-lookup"><span data-stu-id="a9b28-140">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) - These settings include scan schedules and actions to take when malware is detected.</span></span>

- <span data-ttu-id="a9b28-141">[Microsoft Intune で Windows ファイアウォール ポリシーを使用して Windows PC を保護する](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) - 管理対象のコンピューターで Windows ファイアウォール設定の管理を簡易化するポリシーについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="a9b28-141">[Help protect Windows PCs using Windows Firewall policies in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) - These policies simplify the administration of Windows Firewall settings on managed computers.</span></span>


### <a name="see-also"></a><span data-ttu-id="a9b28-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9b28-142">See also</span></span>

[<span data-ttu-id="a9b28-143">Intune ソフトウェア クライアントを使用した一般的な Windows PC 管理タスク</span><span class="sxs-lookup"><span data-stu-id="a9b28-143">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
