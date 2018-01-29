---
title: "Intune デバイス インベントリの表示"
titlesuffix: Azure portal
description: "Intune で管理するデバイスを表示して、ハードウェアとインストールされているアプリを把握する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 11/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a910c99454b9c8a7922af3368453feab94803501
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-view-intune-device-inventory"></a><span data-ttu-id="0f88b-103">Intune デバイス インベントリを表示する方法</span><span class="sxs-lookup"><span data-stu-id="0f88b-103">How to view Intune device inventory</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="0f88b-104">**デバイス** ワークロードでは、ハードウェアの機能やインストールされているアプリなど、管理するデバイスを把握することができます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-104">The **Devices** workload gives you insights into the devices you manage, including their hardware capabilities, and the apps installed on them.</span></span> 

<span data-ttu-id="0f88b-105">デバイス インベントリを表示するには、以下を行います。</span><span class="sxs-lookup"><span data-stu-id="0f88b-105">To view device inventory:</span></span>

1. <span data-ttu-id="0f88b-106">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0f88b-106">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="0f88b-107">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0f88b-107">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="0f88b-108">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f88b-108">On the **Intune** blade, choose **Devices**.</span></span>

<span data-ttu-id="0f88b-109">ここで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f88b-109">Now, choose one of the following options:</span></span>

- <span data-ttu-id="0f88b-110">**[概要]** 登録したデバイスと、各デバイスで実行されているオペレーティング システムについての情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-110">**Overview** Get information about devices you've enrolled, and the operating systems each device runs.</span></span>
- <span data-ttu-id="0f88b-111">**[管理]** - **[すべてのデバイス]** を選択すると、管理しているすべてのデバイスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-111">**Manage** - Choose **All Devices** to see a list of all the devices you manage.</span></span>
    <span data-ttu-id="0f88b-112">一覧からいずれかのデバイスを選択すると、[<*デバイス名*> **概要]** ブレードが開き、以下のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-112">Select one of those devices in the list to open the <*device name*> **Overview** blade where you can select one of:</span></span>
    - <span data-ttu-id="0f88b-113">**[概要]** - デバイスの名前、所有者、BYOD デバイスかどうか、最終チェックイン日時など、デバイスについての一般情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-113">**Overview**  - See general information about the device including its name, owner, whether it is a BYOD device, when it checked-in, and more.</span></span>
    - <span data-ttu-id="0f88b-114">**[ハードウェア]** - デバイスの記憶域の空き容量、モデル、製造元など、デバイスについてのさらに詳細な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-114">**Hardware** - See more detailed information about the device including its free storage space, model and manufacturer, and more.</span></span>
    - <span data-ttu-id="0f88b-115">**[検出されたアプリ]** - Intune でデバイスにインストールされていると判断されたすべてのアプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-115">**Discovered apps** - Displays a list of all apps that Intune found installed on the device.</span></span>
    - <span data-ttu-id="0f88b-116">**[デバイスのポリシー準拠]** - デバイスに割り当てられているすべてのコンプライアンス ポリシーのコンプライアンス対応状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-116">**Device compliance** - Displays the compliance state of all compliance policies that have been assigned to the device.</span></span>
    - <span data-ttu-id="0f88b-117">**[デバイス構成]** - デバイスに割り当てられているすべてのデバイス構成ポリシーのコンプライアンス対応状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-117">**Device configuration** - Displays the compliance state of all device configuration policies that have been assigned to the device.</span></span>
- <span data-ttu-id="0f88b-118">**[監視]** - **[デバイス アクション]** を選択すると、管理対象のデバイスで実行されたデバイス アクションの一覧と、その現在の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-118">**Monitor** Choose **Device Actions** to see a list of device actions that have been performed on devices you manage and their current state.</span></span>
- <span data-ttu-id="0f88b-119">**[セットアップ]** > **[TeamViewer Connector]** - TeamViewer のソフトウェアを使用して、デバイスのリモート管理を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-119">**Setup** > **TeamViewer Connector** - Let's you configure remote administration on devices using the TeamViewer software.</span></span> <span data-ttu-id="0f88b-120">詳細については、「[Intune 管理対象の Android デバイスにリモート アシスタンスを提供する](/intune/device-profile-android-teamviewer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f88b-120">For details, see [Provide remote assistance for Intune managed Android devices](/intune/device-profile-android-teamviewer).</span></span>

<span data-ttu-id="0f88b-121">Intune は会社所有のデバイスでのみアプリのインベントリを収集します。</span><span class="sxs-lookup"><span data-stu-id="0f88b-121">Intune collects app inventory only on corporate-owned devices.</span></span> <span data-ttu-id="0f88b-122">個人のデバイスではアプリがインベントリされません。</span><span class="sxs-lookup"><span data-stu-id="0f88b-122">Apps are not inventoried on personal devices.</span></span> <span data-ttu-id="0f88b-123">Windows 10 の PC の場合、最新のアプリのインベントリのみが会社所有のデバイスで収集されます。</span><span class="sxs-lookup"><span data-stu-id="0f88b-123">For Windows 10 PCs, only modern app inventory is collected on corporate-owned devices.</span></span> <span data-ttu-id="0f88b-124">Intune は、デバイス上の Win32 アプリに関する情報を収集しません。</span><span class="sxs-lookup"><span data-stu-id="0f88b-124">Intune does not collect information about Win32 apps on the device.</span></span> <span data-ttu-id="0f88b-125">デバイスで使用する通信事業者によっては、一部のインベントリ項目が収集されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f88b-125">Depending on the carrier you use with devices, not all inventory items might be collected.</span></span>
