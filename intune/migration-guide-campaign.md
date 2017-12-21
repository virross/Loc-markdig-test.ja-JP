---
title: "Intune 移行キャンペーンを開始する"
description: "この記事では、移行キャンペーンの開始方法に関するガイダンスを提供します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: a272d9c822a2c17592d7800c20278ce222d615bd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="phase-2-migration-campaign"></a><span data-ttu-id="94d17-103">フェーズ 2: 移行のキャンペーン</span><span class="sxs-lookup"><span data-stu-id="94d17-103">Phase 2: Migration campaign</span></span>

<span data-ttu-id="94d17-104">組織のニーズに最適な移行アプローチを選択し、組織固有の要件に基づいて導入戦略を調整します。</span><span class="sxs-lookup"><span data-stu-id="94d17-104">Choose a migration approach that is most suitable for your organization's needs and adjust implementation tactics based on your specific requirements.</span></span> <span data-ttu-id="94d17-105">このガイドの残りの部分では、ユーザーのデバイスを Intune に登録するという目標を達成するために必要な手段について説明します。</span><span class="sxs-lookup"><span data-stu-id="94d17-105">The remainder of this guide will equip you with the tools you need to achieve the goal of getting your users’ devices enrolled into Intune.</span></span>

## <a name="keys-to-a-successful-migration"></a><span data-ttu-id="94d17-106">移行を成功させるカギ</span><span class="sxs-lookup"><span data-stu-id="94d17-106">Keys to a successful migration</span></span>

<span data-ttu-id="94d17-107">サード パーティの MDM プロバイダーから Intune への移行を成功させるには、以下のことが重要です。</span><span class="sxs-lookup"><span data-stu-id="94d17-107">These are the keys to migrating successfully from a third-party MDM provider to Intune:</span></span>

-   <span data-ttu-id="94d17-108">明確で有益な通信は、エンドユーザーのダウンタイムと不満足を最小限に抑えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="94d17-108">Clear and helpful communication can minimize end-user downtime and dissatisfaction.</span></span>

-   <span data-ttu-id="94d17-109">個別的かつ具体的な移行指示を行うようにします。</span><span class="sxs-lookup"><span data-stu-id="94d17-109">Be sure to have specific and concrete migration instructions.</span></span>

-   <span data-ttu-id="94d17-110">Intune に登録する前に、すべての管理対象デバイスを既存の MDM プロバイダーから登録解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94d17-110">All managed devices must be unenrolled from your existing MDM provider before they can be enrolled in Intune.</span></span>

-   <span data-ttu-id="94d17-111">デバイスの登録解除の方法については、既存の MDM プロバイダーからのガイダンスをエンド ユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="94d17-111">Provide guidance from your existing MDM provider to end-users for how to unenroll their devices.</span></span>

-   <span data-ttu-id="94d17-112">段階的なアプローチを使用します。</span><span class="sxs-lookup"><span data-stu-id="94d17-112">Use a phased approach.</span></span> <span data-ttu-id="94d17-113">パイロット ユーザーで構成された小規模なグループで開始して、全面的な展開に達するまで段階的にユーザー グループを追加していきます。</span><span class="sxs-lookup"><span data-stu-id="94d17-113">Start with a small group of pilot users and incrementally add more groups of users until you reach full scale deployment.</span></span>

-   <span data-ttu-id="94d17-114">各サイクルで、ヘルプ デスクの負荷と登録の完了を監視します。</span><span class="sxs-lookup"><span data-stu-id="94d17-114">Monitor the helpdesk load and enrollment success of each cycle.</span></span> <span data-ttu-id="94d17-115">スケジュールに余裕を持たせ、各グループの成功基準を評価してから次のグループで移行を開始するようにします。</span><span class="sxs-lookup"><span data-stu-id="94d17-115">Leave time in the schedule to ensure success criteria can be evaluated for each group before migrating the next.</span></span> <span data-ttu-id="94d17-116">パイロット展開では次の点を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94d17-116">Your pilot deployment should validate the following:</span></span>

    -   <span data-ttu-id="94d17-117">登録の成功率と失敗率が想定内であること。</span><span class="sxs-lookup"><span data-stu-id="94d17-117">Enrollment success and failure rates are within expectations.</span></span>

    -   <span data-ttu-id="94d17-118">ユーザーの生産性:</span><span class="sxs-lookup"><span data-stu-id="94d17-118">User productivity:</span></span>

        -   <span data-ttu-id="94d17-119">VPN、Wi-Fi、電子メール、および証明書などの会社のリソースが機能している。</span><span class="sxs-lookup"><span data-stu-id="94d17-119">Corporate resources such as VPN, Wi-Fi, email, and certificates are working.</span></span>

        -   <span data-ttu-id="94d17-120">プロビジョニング済みのアプリにアクセスできる。</span><span class="sxs-lookup"><span data-stu-id="94d17-120">Provisioned apps are accessible.</span></span>

    -   <span data-ttu-id="94d17-121">データ セキュリティ:</span><span class="sxs-lookup"><span data-stu-id="94d17-121">Data security:</span></span>

        -   <span data-ttu-id="94d17-122">コンプライアンス レポートが行われる。</span><span class="sxs-lookup"><span data-stu-id="94d17-122">Compliance reporting is occurring.</span></span>

        -   <span data-ttu-id="94d17-123">モバイル アプリ保護が適用される。</span><span class="sxs-lookup"><span data-stu-id="94d17-123">Mobile app protections are enforced.</span></span>

<span data-ttu-id="94d17-124">移行の最初のフェーズに満足したら、次のフェーズの[移行サイクル](migration-guide-cycle.md)を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94d17-124">When you are satisfied with the first phase of migrations, repeat the [migration cycle](migration-guide-cycle.md) for the next phase.</span></span>

-   <span data-ttu-id="94d17-125">すべてのユーザーが Intune に移行するまで、段階的なサイクルを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94d17-125">Repeat phased cycles until all users are migrated to Intune.</span></span>

-   <span data-ttu-id="94d17-126">移行キャンペーン中に、ヘルプ デスク チームがエンド ユーザーに対応できているか確認します。</span><span class="sxs-lookup"><span data-stu-id="94d17-126">Ensure the helpdesk team is ready to support end users throughout the migration campaign.</span></span> <span data-ttu-id="94d17-127">サポート コールのワークロードを見積もることができるまでは、自主的な移行を実施します。</span><span class="sxs-lookup"><span data-stu-id="94d17-127">Run a voluntary migration until you can estimate support call workload.</span></span>

-   <span data-ttu-id="94d17-128">ヘルプ デスクが残りのユーザーに対応できるまでは、登録期限を設定しないようにします。</span><span class="sxs-lookup"><span data-stu-id="94d17-128">Don’t set deadlines for enrollment until the remaining population can be handled by your helpdesk</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94d17-129">Exchange や SharePoint Online などのリソースへのアクセス制御を適用するために、Intune と既存のサードパーティ MDM ソリューションの両方を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="94d17-129">Do not configure both Intune and your existing third party MDM solution to apply access controls to resources such as Exchange or SharePoint Online.</span></span> <span data-ttu-id="94d17-130">また、同時に複数のソリューションにデバイスを登録しないでください。</span><span class="sxs-lookup"><span data-stu-id="94d17-130">Additionally, devices should only be enrolled in one solution at a time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="94d17-131">次のステップ</span><span class="sxs-lookup"><span data-stu-id="94d17-131">Next steps</span></span>

<span data-ttu-id="94d17-132">[情報伝達計画](migration-guide-communication-plan.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="94d17-132">Create your [communication plan](migration-guide-communication-plan.md).</span></span>
