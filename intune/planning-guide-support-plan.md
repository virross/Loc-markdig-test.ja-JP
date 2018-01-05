---
title: "サポート計画を作成する"
description: "この記事では、Microsoft Intune 展開の Intune サポート計画の作成を支援します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b9428769-4333-4778-b677-f23dea1f74da
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9ff8643e854f96f464a5a393bfd780f07ea74164
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="develop-a-support-plan"></a><span data-ttu-id="5b743-103">サポート計画を作成する</span><span class="sxs-lookup"><span data-stu-id="5b743-103">Develop a support plan</span></span>

<span data-ttu-id="5b743-104">Intune サポート計画を用意すると、Intune 関連の問題をより効果的に特定し、解決できます。</span><span class="sxs-lookup"><span data-stu-id="5b743-104">Having an Intune support plan can help you identify and resolve Intune related issues more effectively.</span></span> <span data-ttu-id="5b743-105">さらに、Intune の全体的な操作性が改善します。</span><span class="sxs-lookup"><span data-stu-id="5b743-105">This, in turn, improves your users' overall Intune experience.</span></span> <span data-ttu-id="5b743-106">次に、Intune サポート計画を立てる際に考慮する必要がある事項の例を示します。</span><span class="sxs-lookup"><span data-stu-id="5b743-106">Here are some questions to consider as you develop your Intune support plan:</span></span>

-   <span data-ttu-id="5b743-107">Intune のサポートを提供する担当チームはどこですか</span><span class="sxs-lookup"><span data-stu-id="5b743-107">Which teams will be responsible for providing Intune support?</span></span>

-   <span data-ttu-id="5b743-108">Intune のサポートを提供するためにどのようなプロセスを使用しますか</span><span class="sxs-lookup"><span data-stu-id="5b743-108">What process will be used to provide Intune support?</span></span>

-   <span data-ttu-id="5b743-109">Intune のサポート トレーニングはどのように計画しますか</span><span class="sxs-lookup"><span data-stu-id="5b743-109">How you plan to provide Intune support training?</span></span>

-   <span data-ttu-id="5b743-110">Intune 展開プロセスの初期段階で、どのような機会にサポート チームが参加できるでしょうか</span><span class="sxs-lookup"><span data-stu-id="5b743-110">What are the opportunities to involve the support team early in the Intune deployment process?</span></span>

<span data-ttu-id="5b743-111">それぞれの領域について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5b743-111">Let’s review each area in more detail.</span></span>

## <a name="which-teams-are-responsible-for-providing-support"></a><span data-ttu-id="5b743-112">Intune のサポートを提供する担当チーム</span><span class="sxs-lookup"><span data-stu-id="5b743-112">Which teams are responsible for providing support?</span></span>

<span data-ttu-id="5b743-113">組織には、複数階層/レベル (1 から 3) のサポートがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b743-113">Organizations may have different tiers or levels (1-3) of support.</span></span> <span data-ttu-id="5b743-114">たとえば、階層 1 と階層 2 はサポート チームに属し、階層 3 には Intune の展開を担当する MDM チームのメンバーが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b743-114">For example, tier 1 and 2 may be part of the support team, and tier 3 include members of the MDM team responsible for the deployment of Intune.</span></span>

<span data-ttu-id="5b743-115">通常、階層 1 は第 1 レベルのサポートであり、通常、ユーザーがサポート依頼で最初に連絡する階層です。</span><span class="sxs-lookup"><span data-stu-id="5b743-115">Tier 1 is normally the first level of support and typically the first tier to be contacted by the user for support requests.</span></span> <span data-ttu-id="5b743-116">階層 1 がエンド ユーザーの問題を解決できない場合、階層 2 にエスカレートされます。</span><span class="sxs-lookup"><span data-stu-id="5b743-116">If tier 1 is unable to resolve the end user’s issue, they escalate it to tier 2.</span></span> <span data-ttu-id="5b743-117">必要であれば、階層 2 から階層 3 にエスカレートされます。</span><span class="sxs-lookup"><span data-stu-id="5b743-117">Tier 2 escalates it to tier 3 if needed.</span></span> <span data-ttu-id="5b743-118">さらに、Microsoft サポートを階層 4 と考えることもできます。</span><span class="sxs-lookup"><span data-stu-id="5b743-118">In addition, Microsoft support may be considered as tier 4.</span></span>

<span data-ttu-id="5b743-119">[Intune のサポートの詳細についてはこちら](/intune/get-support)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b743-119">Learn more about [Intune support](/intune/get-support).</span></span>

## <a name="what-is-the-support-process"></a><span data-ttu-id="5b743-120">サポート プロセスの内容</span><span class="sxs-lookup"><span data-stu-id="5b743-120">What is the support process?</span></span>

<span data-ttu-id="5b743-121">運用ロールアウトの初期フェーズでは、3 つの階層すべてがブリッジまたは Skype 通話に参加するように指示することもあります。</span><span class="sxs-lookup"><span data-stu-id="5b743-121">For the initial production rollout phases, you could have all three tiers participating in a bridge or Skype call.</span></span> <span data-ttu-id="5b743-122">次に、組織での IT サポート/ヘルプデスクのワークフローの実施例を示します。</span><span class="sxs-lookup"><span data-stu-id="5b743-122">Here’s one example of how an organization could implement their IT support or helpdesk work-flows:</span></span>

1.  <span data-ttu-id="5b743-123">エンド ユーザーが、登録の問題について IT サポート/ヘルプデスク階層 1 に問い合わせます。</span><span class="sxs-lookup"><span data-stu-id="5b743-123">End-user contacts IT support or helpdesk tier 1 with an enrollment issue.</span></span>

2.  <span data-ttu-id="5b743-124">IT サポート/ヘルプデスク階層 1 は根本原因を特定できず、階層 2 に上申します。</span><span class="sxs-lookup"><span data-stu-id="5b743-124">IT support or helpdesk tier 1 is unable to determine the root cause and escalates to tier 2.</span></span>

3.  <span data-ttu-id="5b743-125">IT サポート/ヘルプデスク階層 2 は問題を調査しますが解決できず、階層 3 に上申し、調査に役立つ追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5b743-125">IT support or helpdesk tier 2 investigates, but is unable to resolve the issue and escalates to tier 3, providing additional information to assist with the investigation.</span></span>

4.  <span data-ttu-id="5b743-126">IT サポート/ヘルプデスク階層 3 はさらに調査し、根本原因を特定して、解決策を階層 2 と階層 1 に伝えます。</span><span class="sxs-lookup"><span data-stu-id="5b743-126">IT support or helpdesk tier 3 investigates further, determines the root cause, and communicates the resolution to tier 2 and 1.</span></span>

5.  <span data-ttu-id="5b743-127">IT サポート/ヘルプデスク階層 1 はユーザーに連絡し、問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="5b743-127">IT support/helpdesk tier 1 then contacts the customer and resolves their issue.</span></span>

<span data-ttu-id="5b743-128">このような方法では、特に Intune のロールアウトの初期段階で以下のような多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="5b743-128">This type of approach, especially in early stages of the Intune rollout, adds many benefits, including:</span></span>

-   <span data-ttu-id="5b743-129">技術学習と開始を支援する</span><span class="sxs-lookup"><span data-stu-id="5b743-129">Assisting in technology learning and ramp up.</span></span>

-   <span data-ttu-id="5b743-130">問題と解決策をすばやく特定する</span><span class="sxs-lookup"><span data-stu-id="5b743-130">Quickly identifying issues and resolution.</span></span>

-   <span data-ttu-id="5b743-131">全体的なユーザー エクスペリエンスを改善する</span><span class="sxs-lookup"><span data-stu-id="5b743-131">Improving the overall user experience.</span></span>

## <a name="how-you-plan-to-provide-intune-support-training"></a><span data-ttu-id="5b743-132">Intune のサポート トレーニングはどのように計画しますか</span><span class="sxs-lookup"><span data-stu-id="5b743-132">How you plan to provide Intune support training?</span></span>

<span data-ttu-id="5b743-133">IT サポート/ヘルプデスク スタッフ向けに、適切なレベルで、各サポート階層とその責任内容に合わせた Intune 技術トレーニングを用意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="5b743-133">It’s important to provide Intune technical training for your IT support or helpdesk staff so that the training is at an appropriate level and applies to the specific support tier and their responsibilities.</span></span> <span data-ttu-id="5b743-134">Intune MDM チームがサポート リーダーに対してこのトレーニングを実施してから (トレーナーのトレーニング)、サポート リーダーがサポート チーム メンバーにトレーニングを実施する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="5b743-134">You could have the Intune MDM team conduct this training to the support leads (training the trainer), then have the leads provide this training to their support team members.</span></span> <span data-ttu-id="5b743-135">このトレーニングの所要時間は、講義と演習を含めて一般的に 2 ～ 3 時間です。</span><span class="sxs-lookup"><span data-stu-id="5b743-135">This training can typically be provided in 2-3 hours, and it includes lecture and labs.</span></span>

<span data-ttu-id="5b743-136">Intune サポート トレーニングの課題例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5b743-136">An example of an Intune support training agenda is provided below.</span></span>

-   <span data-ttu-id="5b743-137">Intune サポート計画のレビュー</span><span class="sxs-lookup"><span data-stu-id="5b743-137">Intune support plan review</span></span>

-   <span data-ttu-id="5b743-138">Intune の概要</span><span class="sxs-lookup"><span data-stu-id="5b743-138">Intune overview</span></span>

-   <span data-ttu-id="5b743-139">一般的な問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5b743-139">Troubleshooting common issues</span></span>

-   <span data-ttu-id="5b743-140">ツールとリソース</span><span class="sxs-lookup"><span data-stu-id="5b743-140">Tools and resources</span></span>

-   <span data-ttu-id="5b743-141">Q & A</span><span class="sxs-lookup"><span data-stu-id="5b743-141">Q & A</span></span>

<span data-ttu-id="5b743-142">[Intune 文書](https://docs.microsoft.com/intune/)には、Intune 概要、詳細な機能説明、トラブルシューティング情報があります。</span><span class="sxs-lookup"><span data-stu-id="5b743-142">The [Intune documentation](https://docs.microsoft.com/intune/) provides an Intune overview,  detailed feature descriptions, and some troubleshooting information.</span></span> <span data-ttu-id="5b743-143">[Intune フォーラム](https://social.technet.microsoft.com/Forums/en-US/home)はコミュニティ基盤のリソースであり、Intune 文書にはない質問やトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="5b743-143">The [Intune forum](https://social.technet.microsoft.com/Forums/en-US/home) is a community-based resource for questions and topics not covered in the Intune documentation.</span></span>

## <a name="what-opportunities-are-there-to-involve-the-support-team-earlier"></a><span data-ttu-id="5b743-144">初期段階でサポート チームが参加できる機会</span><span class="sxs-lookup"><span data-stu-id="5b743-144">What opportunities are there to involve the support team earlier?</span></span>

<span data-ttu-id="5b743-145">IT サポート/ヘルプデスク スタッフが Intune 展開計画やパイロット運用の初期段階に参加することは、Intune 展開の改善につながり、エンド ユーザーは効率的に Intune を導入できます。</span><span class="sxs-lookup"><span data-stu-id="5b743-145">Involving your IT support/helpdesk staff in early stages of Intune deployment planning and pilot efforts can improve your Intune deployment and end-user adoption.</span></span> <span data-ttu-id="5b743-146">初期段階から関与する場合、サポート スタッフに Intune を公開し、貴重な体験を始めから与えることになります。</span><span class="sxs-lookup"><span data-stu-id="5b743-146">Early involvement provides your support staff with exposure to Intune and valuable experience from the beginning.</span></span> <span data-ttu-id="5b743-147">IT サポート/ヘルプデスク スタッフが組織の本格的な運用ロールアウトのサポートに備えることができます。</span><span class="sxs-lookup"><span data-stu-id="5b743-147">This helps prepare your IT support/helpdesk staff for supporting the organization's full production rollout.</span></span>

## <a name="next-step"></a><span data-ttu-id="5b743-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="5b743-148">Next step</span></span>

<span data-ttu-id="5b743-149">次のセクションは、[Intune の設計](planning-guide-design.md)に関するガイダンスです。</span><span class="sxs-lookup"><span data-stu-id="5b743-149">The next section provides guidance on [designing Intune](planning-guide-design.md).</span></span>
