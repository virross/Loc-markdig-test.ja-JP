---
title: "標準的な Intune 移行サイクルのしくみ"
description: "この記事では、Intune 移行サイクルのしくみを説明し、移行サイクルの対応方法の例を示します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 34e748e16449a99bad4c1f3e96c22dda6d8f3018
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="typical-migration-cycle"></a><span data-ttu-id="b52b2-103">標準的な移行サイクル</span><span class="sxs-lookup"><span data-stu-id="b52b2-103">Typical migration cycle</span></span>

<span data-ttu-id="b52b2-104">通常、組織は、IT 部門の一部のユーザーを対象とした、小規模なパイロットで Intune 移行を開始します。</span><span class="sxs-lookup"><span data-stu-id="b52b2-104">It’s common for an organization to start their Intune migration with a small pilot by targeting a subset of their users in the IT department.</span></span> <span data-ttu-id="b52b2-105">また、組織で変更に対するグループの意志、ユーザー数、複雑さ、要件、場所、およびビジネス上のリスクなどの要因について話し合い、移行期間の決定に役立てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52b2-105">Additionally, your organization may need to discuss such factors as the group’s willingness for change, number of users, complexity, requirements, location, and business risk to assist in determining the migration time-frame.</span></span>

<span data-ttu-id="b52b2-106">対象グループのスケジュール例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b52b2-106">Here’s an example of how your target groups could be scheduled:</span></span>

  | <span data-ttu-id="b52b2-107">**移行対象グループ**</span><span class="sxs-lookup"><span data-stu-id="b52b2-107">**Migration targeted groups**</span></span> | <span data-ttu-id="b52b2-108">**期間 1**</span><span class="sxs-lookup"><span data-stu-id="b52b2-108">**Time period 1**</span></span> | <span data-ttu-id="b52b2-109">**期間 2**</span><span class="sxs-lookup"><span data-stu-id="b52b2-109">**Time period 2**</span></span> | <span data-ttu-id="b52b2-110">**期間 3**</span><span class="sxs-lookup"><span data-stu-id="b52b2-110">**Time period 3**</span></span> | <span data-ttu-id="b52b2-111">**期間 4**</span><span class="sxs-lookup"><span data-stu-id="b52b2-111">**Time period 4**</span></span> | <span data-ttu-id="b52b2-112">**...**</span><span class="sxs-lookup"><span data-stu-id="b52b2-112">**...**</span></span>
|:---:|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="b52b2-113">限定パイロット運用の IT 部門 (50 ユーザー)</span><span class="sxs-lookup"><span data-stu-id="b52b2-113">Limited Pilot IT org (50 users)</span></span> | <span data-ttu-id="b52b2-114">計画の発表</span><span class="sxs-lookup"><span data-stu-id="b52b2-114">Announce Plan</span></span> | <span data-ttu-id="b52b2-115">登録の指示</span><span class="sxs-lookup"><span data-stu-id="b52b2-115">Instruct to enroll</span></span> | <span data-ttu-id="b52b2-116">期限の設定</span><span class="sxs-lookup"><span data-stu-id="b52b2-116">Give deadline</span></span> | <span data-ttu-id="b52b2-117">条件付きアクセスを強制的に適用</span><span class="sxs-lookup"><span data-stu-id="b52b2-117">Enforce conditional access</span></span> |  |                                                        
| <span data-ttu-id="b52b2-118">拡張パイロット運用の IT 部門 (200 ユーザー)</span><span class="sxs-lookup"><span data-stu-id="b52b2-118">Expanded Pilot IT org (200 users)</span></span> |  | <span data-ttu-id="b52b2-119">計画の発表</span><span class="sxs-lookup"><span data-stu-id="b52b2-119">Announce Plan</span></span> | <span data-ttu-id="b52b2-120">登録の指示</span><span class="sxs-lookup"><span data-stu-id="b52b2-120">Instruct to enroll</span></span> | <span data-ttu-id="b52b2-121">期限の設定</span><span class="sxs-lookup"><span data-stu-id="b52b2-121">Give deadline</span></span> | <span data-ttu-id="b52b2-122">条件付きアクセスを強制的に適用</span><span class="sxs-lookup"><span data-stu-id="b52b2-122">Enforce conditional access</span></span> |
| <span data-ttu-id="b52b2-123">移行フェーズ 1 技術に精通したユーザー (2000人)</span><span class="sxs-lookup"><span data-stu-id="b52b2-123">Migration phase 1 Tech-savvy users (2000)</span></span> |  |  | <span data-ttu-id="b52b2-124">計画の発表</span><span class="sxs-lookup"><span data-stu-id="b52b2-124">Announce Plan</span></span> | <span data-ttu-id="b52b2-125">登録の指示</span><span class="sxs-lookup"><span data-stu-id="b52b2-125">Instruct to enroll</span></span> | <span data-ttu-id="b52b2-126">期限の設定</span><span class="sxs-lookup"><span data-stu-id="b52b2-126">Give deadline</span></span> |
| <span data-ttu-id="b52b2-127">移行フェーズ 2 米国東部</span><span class="sxs-lookup"><span data-stu-id="b52b2-127">Migration phase 2 Eastern US</span></span> |  |  |  | <span data-ttu-id="b52b2-128">計画の発表</span><span class="sxs-lookup"><span data-stu-id="b52b2-128">Announce Plan</span></span> | <span data-ttu-id="b52b2-129">登録の指示</span><span class="sxs-lookup"><span data-stu-id="b52b2-129">Instruct to enroll</span></span> |
| <span data-ttu-id="b52b2-130">すべての地域</span><span class="sxs-lookup"><span data-stu-id="b52b2-130">All Regions</span></span> |  |  |  |  | <span data-ttu-id="b52b2-131">計画の発表</span><span class="sxs-lookup"><span data-stu-id="b52b2-131">Announce Plan</span></span> |

## <a name="customer-migration-case-study"></a><span data-ttu-id="b52b2-132">お客様の移行のケース スタディ</span><span class="sxs-lookup"><span data-stu-id="b52b2-132">Customer migration case study</span></span>

### <a name="adatum-corporation"></a><span data-ttu-id="b52b2-133">Adatum Corporation</span><span class="sxs-lookup"><span data-stu-id="b52b2-133">Adatum Corporation</span></span>

<span data-ttu-id="b52b2-134">[Adatum Corporation のサード パーティ MDM プロバイダーから Intune への移行プロセス](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b52b2-134">Check out [how Adatum Corporation went through the process of migration from a third-party MDM provider to Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).</span></span>

## <a name="monitoring-migration"></a><span data-ttu-id="b52b2-135">移行の監視</span><span class="sxs-lookup"><span data-stu-id="b52b2-135">Monitoring migration</span></span>

<span data-ttu-id="b52b2-136">Intune は、移行を監視する方法をいくつか用意しています。</span><span class="sxs-lookup"><span data-stu-id="b52b2-136">Intune provides several ways that you can monitor your migration:</span></span>

* <span data-ttu-id="b52b2-137">Intune ユーザー グループのビュー</span><span class="sxs-lookup"><span data-stu-id="b52b2-137">Intune user group views</span></span>

* <span data-ttu-id="b52b2-138">組み込みレポートのセット</span><span class="sxs-lookup"><span data-stu-id="b52b2-138">Set of built-in reports</span></span>

* <span data-ttu-id="b52b2-139">コンソール内のアラート</span><span class="sxs-lookup"><span data-stu-id="b52b2-139">In-console alerts</span></span>

<span data-ttu-id="b52b2-140">各フェーズ後にデバイスを登録したユーザー数を追跡することで、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="b52b2-140">Track how many users have enrolled devices after each phase so that you can:</span></span>

-   <span data-ttu-id="b52b2-141">情報伝達計画の効果を評価する。</span><span class="sxs-lookup"><span data-stu-id="b52b2-141">Evaluate the effectiveness of your communication plan.</span></span>

-   <span data-ttu-id="b52b2-142">条件付きアクセスの強制的な適用の影響を評価する。</span><span class="sxs-lookup"><span data-stu-id="b52b2-142">Estimate the impact of enforcing conditional access.</span></span>


## <a name="post-migration"></a><span data-ttu-id="b52b2-143">Post-migration</span><span class="sxs-lookup"><span data-stu-id="b52b2-143">Post-migration</span></span>

<span data-ttu-id="b52b2-144">Intune への移行後に、以前の MDM プロバイダーをインベントリから削除したり、サービスのサブスクリプションを解除したりします。</span><span class="sxs-lookup"><span data-stu-id="b52b2-144">Retire the previous MDM provider and unsubscribe from the service after migrating to Intune.</span></span> <span data-ttu-id="b52b2-145">また、MDM プロバイダーの指示に従って、不要なインフラストラクチャの要件を削除します。</span><span class="sxs-lookup"><span data-stu-id="b52b2-145">Additionally, remove any unneeded infrastructure requirements by following the MDM provider’s instructions.</span></span>
