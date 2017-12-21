---
title: "Intune の計画と設計の概要"
description: "この記事では、Intune の計画、設計および実装に関するすべてのセクションの概要を示します。 目標、ユース ケースのシナリオと要件の決定、ロールアウト計画とコミュニケーション計画、サポート、テスト、検証の計画の作成に役立つツールです。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a65efa6e-4a48-47f3-8f6e-34a85ca64ced
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 754c38a33fa6e08a6022c726f6e1eb8088b82e94
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="intune-deployment-planning-design-and-implementation-guide"></a><span data-ttu-id="b262b-104">Intune の展開計画、設計および実装ガイド</span><span class="sxs-lookup"><span data-stu-id="b262b-104">Intune deployment planning, design, and implementation guide</span></span>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="b262b-105">Intune を正常に展開するには、まず、適切に計画し、設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b262b-105">A successful Intune deployment starts with having a good plan and design.</span></span> <span data-ttu-id="b262b-106">このガイドの目的は、展開計画の作成、設計の作成、Intune のオンボーディング、および運用環境へのロールアウトの実施プロセスを段階的に説明することです。</span><span class="sxs-lookup"><span data-stu-id="b262b-106">The purpose of this guide is to step you through the process of developing a deployment plan, creating a design, onboarding Intune, and conducting a production rollout.</span></span>

## <a name="whats-included-in-this-guide"></a><span data-ttu-id="b262b-107">このガイドに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="b262b-107">What’s included in this guide?</span></span>

<span data-ttu-id="b262b-108">このガイドには、Intune の展開のエンド ツー エンド プロセスを説明するセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b262b-108">This guide includes sections that will walk you through the end-to-end process of deploying Intune.</span></span> <span data-ttu-id="b262b-109">最初にセクション 1 で、目標、目的、課題を確認します。</span><span class="sxs-lookup"><span data-stu-id="b262b-109">Start with Section 1 to clarify your goals, objectives, and challenges.</span></span> <span data-ttu-id="b262b-110">次に、お客様のニーズに最適な順で、セクション 2 から 7 を実行します。</span><span class="sxs-lookup"><span data-stu-id="b262b-110">Then move on to Sections 2 – 7 in the order that best meets your needs.</span></span> <span data-ttu-id="b262b-111">セクション 2 から 7 は順に実行する必要はなく、並行して実行できます。</span><span class="sxs-lookup"><span data-stu-id="b262b-111">You don't need to work through these sections sequentially; you can complete them in parallel.</span></span>

-   [<span data-ttu-id="b262b-112">セクション 1: 展開の目標、目的、課題を決定する</span><span class="sxs-lookup"><span data-stu-id="b262b-112">Section 1: Determine deployment goals, objectives, and challenges</span></span>](planning-guide-deployment-goals.md)

-   [<span data-ttu-id="b262b-113">セクション 2: ユース ケース シナリオを特定する</span><span class="sxs-lookup"><span data-stu-id="b262b-113">Section 2: Identify use case scenarios</span></span>](planning-guide-scenarios.md)

-   [<span data-ttu-id="b262b-114">セクション 3: ユース ケースの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="b262b-114">Section 3: Determine use case requirements</span></span>](planning-guide-requirements.md)

-   [<span data-ttu-id="b262b-115">セクション 4: ロールアウト計画を作成する</span><span class="sxs-lookup"><span data-stu-id="b262b-115">Section 4: Develop a rollout plan</span></span>](planning-guide-rollout-plan.md)

-   [<span data-ttu-id="b262b-116">セクション 5: ロールアウト コミュニケーション計画を作成する</span><span class="sxs-lookup"><span data-stu-id="b262b-116">Section 5: Develop a rollout communication plan</span></span>](planning-guide-communication-plan.md)

-   [<span data-ttu-id="b262b-117">セクション 6: サポート計画を作成する</span><span class="sxs-lookup"><span data-stu-id="b262b-117">Section 6: Develop a support plan</span></span>](planning-guide-support-plan.md)

-   [<span data-ttu-id="b262b-118">セクション 7: Intune の設計を作成する</span><span class="sxs-lookup"><span data-stu-id="b262b-118">Section 7: Create an Intune design</span></span>](planning-guide-design.md)

-   [<span data-ttu-id="b262b-119">セクション 8: Intune を実装する</span><span class="sxs-lookup"><span data-stu-id="b262b-119">Section 8: Intune implementation</span></span>](planning-guide-onboarding.md)

-   [<span data-ttu-id="b262b-120">セクション 9: テストと検証</span><span class="sxs-lookup"><span data-stu-id="b262b-120">Section 9: Testing and validation</span></span>](planning-guide-test-validation.md)

<span data-ttu-id="b262b-121">このガイドでは、Intune の展開計画、設計および実装プロセスを支援するために使用可能な追加の技術情報とテーブル テンプレートも提供されます。</span><span class="sxs-lookup"><span data-stu-id="b262b-121">This guide also provides additional technical information and table templates that can be used to assist you with the Intune deployment planning, design, and implementation process.</span></span>

-   [<span data-ttu-id="b262b-122">その他のリソース: リンクとテーブル テンプレート</span><span class="sxs-lookup"><span data-stu-id="b262b-122">Additional resources: Links and table templates</span></span>](planning-guide-resources.md)

## <a name="assumptions"></a><span data-ttu-id="b262b-123">前提条件</span><span class="sxs-lookup"><span data-stu-id="b262b-123">Assumptions</span></span>

-   <span data-ttu-id="b262b-124">概念実証 (PoC) 環境で既に Intune を評価し、組織でモバイル デバイス管理ソリューションとして使用することを決定している。</span><span class="sxs-lookup"><span data-stu-id="b262b-124">You've already evaluated Intune in a proof of concept (PoC) environment, and have decided to use it as the mobile device management solution in your organization.</span></span>

-   <span data-ttu-id="b262b-125">Intune とその機能について、既によく理解している。</span><span class="sxs-lookup"><span data-stu-id="b262b-125">You're already familiar with Intune and its features.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b262b-126">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b262b-126">Next steps</span></span>

<span data-ttu-id="b262b-127">最初のセクションの「[展開の目標、目的、課題を決定する](planning-guide-deployment-goals.md)」に取りかかりましょう。</span><span class="sxs-lookup"><span data-stu-id="b262b-127">Let’s get started with the first section: [Determine deployment goals, objectives, and challenges](planning-guide-deployment-goals.md).</span></span>
