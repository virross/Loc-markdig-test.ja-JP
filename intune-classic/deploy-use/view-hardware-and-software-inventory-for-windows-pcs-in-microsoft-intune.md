---
title: "Windows PC のハードウェアとソフトウェアのインベントリを表示する"
description: "Intune ソフトウェア クライアントで PC として管理する Windows デスクトップに関するハードウェアとソフトウェアの情報を表示する方法。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3c10f4c9-520b-4864-92fc-a45a9f640ad4
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d985da553637e684f4773848fa8832e4aadd1775
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="view-hardware-and-software-inventory-for-windows-pcs"></a><span data-ttu-id="787dc-103">Windows PC のハードウェアとソフトウェアのインベントリを表示する</span><span class="sxs-lookup"><span data-stu-id="787dc-103">View hardware and software inventory for Windows PCs</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="787dc-104">Intune は、Intune ソフトウェア クライアントを使用して PC として管理されるデスクトップのハードウェアおよびソフトウェアに関する詳細情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="787dc-104">Intune collects detailed information about the hardware and software of desktops that you manage as PCs by using the Intune software client.</span></span> <span data-ttu-id="787dc-105">以下の手順を参照して、次の項目を作成する方法を確認してください:</span><span class="sxs-lookup"><span data-stu-id="787dc-105">Use the information in the following procedures to learn how to create:</span></span>

-   <span data-ttu-id="787dc-106">管理する PC のハードウェア性能に関する情報を一覧にしたレポート。</span><span class="sxs-lookup"><span data-stu-id="787dc-106">A report that lists information about the hardware capabilities of PCs you manage.</span></span>

-   <span data-ttu-id="787dc-107">各 PC にインストールされているソフトウェアを一覧にしたレポート。</span><span class="sxs-lookup"><span data-stu-id="787dc-107">A report that lists the software installed on each PC.</span></span>

-   <span data-ttu-id="787dc-108">PC のインベントリを更新して、レポートのデータを最新の状態に保つ方法。</span><span class="sxs-lookup"><span data-stu-id="787dc-108">How to refresh a PCs inventory to ensure that the data in the report is current.</span></span>

## <a name="to-display-information-about-pcs-you-manage"></a><span data-ttu-id="787dc-109">管理する PC に関する情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="787dc-109">To display information about PCs you manage</span></span>

1.  <span data-ttu-id="787dc-110">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[レポート]** &gt; **[コンピューター インベントリ レポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="787dc-110">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Reports** &gt; **Computer Inventory Reports**.</span></span>

2.  <span data-ttu-id="787dc-111">**[新しいレポートの作成]** ページで、既定値をそのまま使用するか、カスタマイズして、レポートで返される結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="787dc-111">On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report.</span></span> <span data-ttu-id="787dc-112">たとえば、Windows 8.1 を実行する PC だけをレポートに表示するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="787dc-112">For example, you could select that only PCs that run Windows 8.1 will be displayed in the report.</span></span>

3.  <span data-ttu-id="787dc-113">**[レポートの表示]** を選択すると、**[コンピューター インベントリ レポート]** が新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="787dc-113">Choose **View Report** to open the **Computer Inventory Report** in a new window.</span></span>

    <span data-ttu-id="787dc-114">レポートは、列見出し (**[名前]**、**[シャーシの種類]**、**[製造元]** など) を選択して並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="787dc-114">You can sort the report by any of the columns, like **Name**, **Chassis Type** or **Manufacturer** by selecting each column heading.</span></span>

## <a name="to-display-software-installed-on-pcs-you-manage"></a><span data-ttu-id="787dc-115">管理する PC にインストールされているソフトウェアを表示するには</span><span class="sxs-lookup"><span data-stu-id="787dc-115">To display software installed on PCs you manage</span></span>

1.  <span data-ttu-id="787dc-116">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[レポート]** &gt; **[検出されたソフトウェアのレポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="787dc-116">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Reports** &gt; **Detected Software Reports**.</span></span>

2.  <span data-ttu-id="787dc-117">**[新しいレポートの作成]** ページで、既定値をそのまま使用するか、カスタマイズして、レポートで返される結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="787dc-117">On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report.</span></span> <span data-ttu-id="787dc-118">たとえば、Microsoft が発行したソフトウェアだけをレポートに表示するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="787dc-118">For example, you could select that only software published by Microsoft will be displayed in the report.</span></span>

3.  <span data-ttu-id="787dc-119">**[レポートの表示]** を選択すると、**[検出されたソフトウェアのレポート]** が新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="787dc-119">Choose **View Report** to open the **Detected Software Report** in a new window.</span></span>

    <span data-ttu-id="787dc-120">レポートは、列見出し (**[名前]**、**[発行元]**、**[カテゴリ]** など) を選択して並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="787dc-120">You can sort the report by any of the columns, like **Name**, **Publisher** or **Category** by selecting each column heading.</span></span> <span data-ttu-id="787dc-121">一覧の項目に付いている矢印を選択すると、一覧が展開して、更新プログラムの詳細 (更新プログラムがインストールされている PC など) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="787dc-121">You can expand the updates in the list to show more detail (such as the PCs on which it is installed) by choosing the directional arrow next to the list item.</span></span>

## <a name="to-refresh-computer-inventory-to-ensure-it-is-current"></a><span data-ttu-id="787dc-122">コンピューターのインベントリを更新して最新の状態に保つには</span><span class="sxs-lookup"><span data-stu-id="787dc-122">To refresh computer inventory to ensure it is current</span></span>

1.  <span data-ttu-id="787dc-123">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** &gt; **[すべてのデバイス]** (または、インベントリを更新する PC が含まれる別のグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="787dc-123">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC for which you want to refresh inventory).</span></span>

2.  <span data-ttu-id="787dc-124">PC を 1 台選択するか、**Ctrl** キーを押しながら複数選択します。</span><span class="sxs-lookup"><span data-stu-id="787dc-124">Select a PC, or press and hold **Ctrl** to select multiple PCs.</span></span>

3.  <span data-ttu-id="787dc-125">タスク バーで、**[リモート タスク]** &gt; **[インベントリの更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="787dc-125">On the taskbar, choose **Remote Tasks** &gt; **Refresh Inventory**.</span></span>

4.  <span data-ttu-id="787dc-126">タスクの状態を表示するには、ページの右下隅にある **[リモート タスク]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="787dc-126">To view the task status, choose **Remote Tasks** in the bottom right corner of the page.</span></span>

    <span data-ttu-id="787dc-127">**[タスクの状態]** ダイアログ ボックスが開き、現在のリモート タスク、タスクの状態、デバイス名、発生したエラーと、該当する場合は、トラブルシューティング情報へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="787dc-127">The **Task Status** dialog box displays showing current remote tasks, task status, device name, and any reported errors, and provides a link to troubleshooting information.</span></span>

### <a name="see-also"></a><span data-ttu-id="787dc-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="787dc-128">See also</span></span>

[<span data-ttu-id="787dc-129">Intune ソフトウェア クライアントを使用した一般的な Windows PC 管理タスク</span><span class="sxs-lookup"><span data-stu-id="787dc-129">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)