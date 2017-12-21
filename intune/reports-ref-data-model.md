---
title: "データ ウェアハウス データ モデル | Microsoft Docs"
description: "Intune データ ウェアハウスは、データを毎日サンプリングし、常に変化するモバイル環境の履歴ビューを提供します。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 29825c58febc813c7b11072699d06106725584d3
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="data-warehouse-data-model"></a><span data-ttu-id="c9c1b-104">データ ウェアハウス データ モデル</span><span class="sxs-lookup"><span data-stu-id="c9c1b-104">Data Warehouse data model</span></span>

<span data-ttu-id="c9c1b-105">Intune データ ウェアハウスは、データを毎日サンプリングし、常に変化するモバイル デバイス環境の履歴ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-105">The Intune Data Warehouse samples data daily to provide a historical view of your continually changing environment of mobile devices.</span></span> <span data-ttu-id="c9c1b-106">ビューは時間に関連のあるデータで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-106">The view is composed of related things in time.</span></span>

## <a name="things-entity-sets"></a><span data-ttu-id="c9c1b-107">データ: エンティティ セット</span><span class="sxs-lookup"><span data-stu-id="c9c1b-107">Things: Entity sets</span></span>

<span data-ttu-id="c9c1b-108">このウェアハウスは、次の上位領域のデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-108">The warehouse exposes data in the following high-level areas:</span></span>

  -  <span data-ttu-id="c9c1b-109">アプリ保護が有効なアプリと使用状況</span><span class="sxs-lookup"><span data-stu-id="c9c1b-109">App protection enabled apps and usage</span></span>
  -  <span data-ttu-id="c9c1b-110">登録済みデバイス、プロパティ、インベントリ</span><span class="sxs-lookup"><span data-stu-id="c9c1b-110">Enrolled devices, properties, and inventory</span></span>
  -  <span data-ttu-id="c9c1b-111">アプリとソフトウェアのインベントリ</span><span class="sxs-lookup"><span data-stu-id="c9c1b-111">Apps and software inventory</span></span>
  -  <span data-ttu-id="c9c1b-112">デバイスの構成とコンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="c9c1b-112">Device configuration and compliance policies</span></span>

<span data-ttu-id="c9c1b-113">これらの領域には、エンティティ、つまり Intune 環境にとって重要なデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-113">These areas contain the entities, or things, that are meaningful to your Intune environment.</span></span> <span data-ttu-id="c9c1b-114">エンティティ セットの詳細については、次の各トピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-114">You find details about the entity sets in the following topics:</span></span>

  -  [<span data-ttu-id="c9c1b-115">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c9c1b-115">Application</span></span>](reports-ref-application.md)
  -  [<span data-ttu-id="c9c1b-116">日付</span><span class="sxs-lookup"><span data-stu-id="c9c1b-116">Date</span></span>](reports-ref-date.md)
  -  [<span data-ttu-id="c9c1b-117">デバイス</span><span class="sxs-lookup"><span data-stu-id="c9c1b-117">Devices</span></span>](reports-ref-devices.md)
  -  [<span data-ttu-id="c9c1b-118">Intune の管理拡張</span><span class="sxs-lookup"><span data-stu-id="c9c1b-118">Intune Management Extension</span></span>](reports-ref-intunemanagementextension.md)
  -  [<span data-ttu-id="c9c1b-119">ポリシー</span><span class="sxs-lookup"><span data-stu-id="c9c1b-119">Policy</span></span>](reports-ref-policy.md)
  -  [<span data-ttu-id="c9c1b-120">モバイル アプリ管理 (MAM)</span><span class="sxs-lookup"><span data-stu-id="c9c1b-120">Mobile App Management (MAM)</span></span>](reports-ref-mobile-app-management.md)
  -  [<span data-ttu-id="c9c1b-121">ユーザー</span><span class="sxs-lookup"><span data-stu-id="c9c1b-121">User</span></span>](reports-ref-user.md)
  -  [<span data-ttu-id="c9c1b-122">現在のユーザー</span><span class="sxs-lookup"><span data-stu-id="c9c1b-122">Current User</span></span>](reports-ref-current-user.md)
  -  [<span data-ttu-id="c9c1b-123">ユーザー デバイスの関連付け</span><span class="sxs-lookup"><span data-stu-id="c9c1b-123">User Device Associations</span></span>](reports-ref-user-device.md)

## <a name="relationships-star-schema-model"></a><span data-ttu-id="c9c1b-124">リレーションシップ: スタースキーマ モデル</span><span class="sxs-lookup"><span data-stu-id="c9c1b-124">Relationships: Star-schema model</span></span>

<span data-ttu-id="c9c1b-125">このウェアハウスでは、エンティティがリレーションシップに分類されます。リレーションシップは、尋ねる質問の種類に応じたものです。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-125">The warehouse organizes the entities in relationships that are meaningful to the type of questions you want to ask.</span></span> <span data-ttu-id="c9c1b-126">たとえば、社内で開発された Android アプリケーションのインストールの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-126">For example, you can review the number of installations of an in-house developed Android application.</span></span> <span data-ttu-id="c9c1b-127">データ ウェアハウスの構造を使用して、モバイル環境を分析できます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-127">The structure of the data warehouse enables you to gain insight into your mobile environment.</span></span> <span data-ttu-id="c9c1b-128">また、Microsoft Power BI などの分析ツールでデータ ウェアハウス データ モデルを使用して、視覚化と動的ダッシュボードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-128">In turn, analytics tools, such as Microsoft Power BI, can use the Data Warehouse data model to create visualizations and dynamic dashboards.</span></span>

<span data-ttu-id="c9c1b-129">エンティティとリレーションシップは、スタースキーマ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-129">The entities and relationships use a star-schema model.</span></span> <span data-ttu-id="c9c1b-130">スタースキーマは、時間のディメンションを超えてファクトを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-130">A star-schema correlates facts over the dimension of time.</span></span> <span data-ttu-id="c9c1b-131">モデルのコンテキストで*ファクト*とは、デバイス数、アプリ数、登録時間などの量的単位です。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-131">A *fact* in the context of the model is a quantitative measurement such as the number of devices, number of apps, or time of enrollment.</span></span> <span data-ttu-id="c9c1b-132">ファクト テーブルには大量のデータが保存されます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-132">Fact tables store a lot of data.</span></span> <span data-ttu-id="c9c1b-133">ファクト テーブルは非常に大きくなる場合があるため、通常、情報が 30 日間に制限されます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-133">They can get very large, and so they typically limit information to 30 days.</span></span> <span data-ttu-id="c9c1b-134">*ディメンション*はファクトにコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-134">A *dimension* provides context to the facts.</span></span> <span data-ttu-id="c9c1b-135">ファクトが発生した事象を測定し、ディメンションが誰に対して発生したかを示します。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-135">Where the fact measures what happened, the dimensions indicate to whom it happened.</span></span> <span data-ttu-id="c9c1b-136">**ユーザー** テーブルなどのディメンション テーブルは小さくなり、ファクト テーブルよりも長期間データをリトレインできます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-136">Dimension tables, such as the like the **User** table are smaller and can retrain data for longer periods of time= than fact tables.</span></span> 

<span data-ttu-id="c9c1b-137">スタースキーマ モデルは、柔軟性とデータ分析に合わせて最適化されているため、進化するモバイル環境を理解するために必要なレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-137">A star-schema model is optimized for flexibility and data analysis so that you can create the reports needed to understand your evolving mobile environment.</span></span>

## <a name="time-daily-snapshots"></a><span data-ttu-id="c9c1b-138">時間: 毎日のスナップショット</span><span class="sxs-lookup"><span data-stu-id="c9c1b-138">Time: Daily snapshots</span></span>

<span data-ttu-id="c9c1b-139">このウェアハウスは、Intune データのダウンストリームです。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-139">The warehouse is downstream from your Intune data.</span></span> <span data-ttu-id="c9c1b-140">Intune では、午前 0 時 (UTC) に毎日のスナップショットを取得し、ウェアハウスにスナップショットを保存します。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-140">Intune takes a daily snapshot at Midnight UTC and stores the snapshot in the warehouse.</span></span> <span data-ttu-id="c9c1b-141">スナップショットの保有期間はファクト テーブルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-141">The duration of held snapshots vary from fact table to fact table.</span></span> <span data-ttu-id="c9c1b-142">7 日間や 30 日間、またはさらに長い期間のものもあります。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-142">Some may hold seven days, others 30 days, and some even longer durations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9c1b-143">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c9c1b-143">Next steps</span></span>

 - <span data-ttu-id="c9c1b-144">データ ウェアハウスで Intune のユーザーの有効期間を追跡する方法の詳細については、「[Intune データ ウェアハウスのユーザー有効期間の表記](reports-ref-user-timeline.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-144">To learn more more about how the data warehouse tracks a user's lifetime in Intune, see [User lifetime representation in the Intune Data Warehouse](reports-ref-user-timeline.md).</span></span>
 - <span data-ttu-id="c9c1b-145">データ ウェアハウスの操作に関する詳細については、[最初のデータ ウェアハウスの作成](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-145">To learn more more about working with data warehouses in the [Create First Data WareHouse](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse).</span></span>
 - <span data-ttu-id="c9c1b-146">Power BI とデータ ウェアハウスの操作の詳細については、[データセットをインポートして新しい Power BI レポートを作成する](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c9c1b-146">To learn more about working with Power BI and a data warehouse in [Create a new Power BI report by importing a dataset](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/).</span></span> 
