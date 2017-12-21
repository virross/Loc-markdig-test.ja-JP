---
title: "Intune のアクティビティの監査ログ"
description: "Intune のアクティビティを記録する監査ログを確認する方法をについてください。"
keywords: 
author: dougeby
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: 30067f60163a644f4347c51c249c25fb3428f8ba
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="audit-logs-for-intune-activities"></a><span data-ttu-id="1a123-103">Intune のアクティビティの監査ログ</span><span class="sxs-lookup"><span data-stu-id="1a123-103">Audit logs for Intune activities</span></span>
<span data-ttu-id="1a123-104">監査ログは、Microsoft Intune での変更を生成するアクティビティの記録を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a123-104">Audit logs provide you with a record of activities that generate a change in Microsoft Intune.</span></span> <span data-ttu-id="1a123-105">作成、更新 (編集) を削除し、アクション、またはリモート タスクを割り当てるには、確認できる監査イベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="1a123-105">Create, Update (edit), Delete, and Assign actions, or remote tasks, generate audit events that you can review.</span></span> <span data-ttu-id="1a123-106">Intune のほとんどのワークロードの監査ログを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a123-106">You can review audit logs for most Intune workloads.</span></span> 

## <a name="who-can-access-the-data"></a><span data-ttu-id="1a123-107">データにアクセスできるユーザーですか。</span><span class="sxs-lookup"><span data-stu-id="1a123-107">Who can access the data?</span></span>
<span data-ttu-id="1a123-108">次のアクセス許可を持つユーザーは、監査ログを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a123-108">Users with the following permissions can review audit logs:</span></span>
- <span data-ttu-id="1a123-109">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="1a123-109">Global Administrator</span></span>
- <span data-ttu-id="1a123-110">Intune サービス管理者</span><span class="sxs-lookup"><span data-stu-id="1a123-110">Intune Service Administrator</span></span>
- <span data-ttu-id="1a123-111">Intune の役割に割り当てられた管理者**監査データ** - **読み取り**アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1a123-111">Administrators assigned to an Intune role with **Audit data** - **Read** permissions</span></span>

## <a name="audit-logs-for-intune-workloads"></a><span data-ttu-id="1a123-112">Intune のワークロードの監査ログ</span><span class="sxs-lookup"><span data-stu-id="1a123-112">Audit logs for Intune workloads</span></span>
<span data-ttu-id="1a123-113">Intune で各ワークロードの監視グループにある監査ログを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="1a123-113">You can review audit logs in the Monitoring group for each Intune workload.</span></span>  
1. <span data-ttu-id="1a123-114">サインイン、 [Azure ポータル](https://portal.azure.com)します。</span><span class="sxs-lookup"><span data-stu-id="1a123-114">Sign into the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="1a123-115">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1a123-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="1a123-116">**Intune**ブレードで、監査ログを確認するワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a123-116">On the **Intune** blade, choose the workload for which you want to review audit logs.</span></span>
4. <span data-ttu-id="1a123-117">**監視**ワークロード グループで、選択**監査ログ**です。</span><span class="sxs-lookup"><span data-stu-id="1a123-117">In the **Monitoring** group for the workload, choose **Audit logs**.</span></span>

## <a name="review-audit-events"></a><span data-ttu-id="1a123-118">監査イベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a123-118">Review audit events</span></span>
<span data-ttu-id="1a123-119">![監査ログ](./media/monitor-audit-logs.png "監査ログ")</span><span class="sxs-lookup"><span data-stu-id="1a123-119">![Audit logs](./media/monitor-audit-logs.png "Audit logs")</span></span>

<span data-ttu-id="1a123-120">監査ログには、次の項目を表示する既定のリスト ビューがあります。</span><span class="sxs-lookup"><span data-stu-id="1a123-120">An audit log has a default list view that shows the following items:</span></span>    

- <span data-ttu-id="1a123-121">日付と時刻に見つかった位置の</span><span class="sxs-lookup"><span data-stu-id="1a123-121">date and time of the occurrence</span></span>
- <span data-ttu-id="1a123-122">(アクター) によって開始されます。</span><span class="sxs-lookup"><span data-stu-id="1a123-122">Initiated by (Actor)</span></span>
- <span data-ttu-id="1a123-123">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="1a123-123">Activity</span></span>
- <span data-ttu-id="1a123-124">ターゲット</span><span class="sxs-lookup"><span data-stu-id="1a123-124">Target(s)</span></span>
- <span data-ttu-id="1a123-125">Category</span><span class="sxs-lookup"><span data-stu-id="1a123-125">Category</span></span>
- <span data-ttu-id="1a123-126">状態</span><span class="sxs-lookup"><span data-stu-id="1a123-126">Status</span></span>

<span data-ttu-id="1a123-127">リスト ビュー内の項目をクリックすると、それに関するすべての利用可能な詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="1a123-127">By clicking an item in the list view, you get all available details about it.</span></span>

<span data-ttu-id="1a123-128">![監査ログ](./media/monitor-audit-log-detail.png "監査ログ")</span><span class="sxs-lookup"><span data-stu-id="1a123-128">![Audit logs](./media/monitor-audit-log-detail.png "Audit logs")</span></span>

> [!Note]    
> <span data-ttu-id="1a123-129">**(アクター) によって開始された**監査ログの詳細」セクションと実行された場所からアクティビティを実行したユーザーに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a123-129">The **Initiated by (actor)** section in the audit log details provides information about who performed the activity and from where it was performed.</span></span> <span data-ttu-id="1a123-130">たとえば、Azure ポータルで、Intune でアクティビティを実行する**アプリケーション**に常に表示**Microsoft Intune のポータルの拡張機能**と**アプリケーション ID**常に同じ GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a123-130">For example, if you perform the activity in Intune in the Azure portal, **Application** always lists **Microsoft Intune portal extension** and the **Application ID** always uses the same GUID.</span></span> 
>    
> <span data-ttu-id="1a123-131">**ターゲット**セクションでは、複数のターゲットと変更されたプロパティを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="1a123-131">The **Target(s)** section can list multiple targets and the properties that were changed.</span></span>  


## <a name="filter-audit-events"></a><span data-ttu-id="1a123-132">監査イベントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="1a123-132">Filter audit events</span></span>
<span data-ttu-id="1a123-133">各ワークロードには、あらかじめ、そのブレードに関連付けられている監査イベントのカテゴリをフィルター処理するメニュー項目があります。</span><span class="sxs-lookup"><span data-stu-id="1a123-133">Each workload has a menu item that pre-filters the category of audit events associated with that blade.</span></span> <span data-ttu-id="1a123-134">別個のフィルター オプションを使用して、別のカテゴリ、およびそのカテゴリ内のイベントのアクションの詳細を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1a123-134">A separate filter option lets you change to different categories, and event action details within that category.</span></span> <span data-ttu-id="1a123-135">UPN (たとえば、ユーザー アクションをでした) によって検索することができます。</span><span class="sxs-lookup"><span data-stu-id="1a123-135">You can search by UPN (for example, the user who did the action).</span></span> <span data-ttu-id="1a123-136">日付の範囲フィルターは、24 時間、7 日間、または 30 日間のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a123-136">A date range filter allows 24 hours, 7 days, or 30-day options.</span></span> <span data-ttu-id="1a123-137">既定では、過去 30 日の監査イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a123-137">By default, the last 30 days of audit events are displayed.</span></span>

## <a name="use-graph-api-to-retrieve-audit-events"></a><span data-ttu-id="1a123-138">Graph API を使用して、監査イベントを取得するには</span><span class="sxs-lookup"><span data-stu-id="1a123-138">Use Graph API to retrieve audit events</span></span>
<span data-ttu-id="1a123-139">Graph API を使用して、監査イベントの最長 1 年間を取得する方法に関する詳細については、「 [auditEvents を一覧表示](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list)です。</span><span class="sxs-lookup"><span data-stu-id="1a123-139">For details about how to use the graph API to retrieve up to one year of audit events, see [List auditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list).</span></span>