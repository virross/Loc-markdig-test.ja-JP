---
title: "ロールアウト対象とするグループと期間を決める"
description: "この記事では、Intune にロールアウトするグループと展開の期間を決める方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6edb71b7d97ac3c20b4207d2cac42669ac35c4c0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="develop-a-rollout-plan"></a><span data-ttu-id="80373-103">ロールアウト計画を作成する</span><span class="sxs-lookup"><span data-stu-id="80373-103">Develop a rollout plan</span></span>

<span data-ttu-id="80373-104">ロールアウト計画では、Intune ロールアウトの対象となる組織グループ、各グループのロールアウト期間、使用する登録方法を特定します。</span><span class="sxs-lookup"><span data-stu-id="80373-104">Your rollout plan identifies the organizational groups you want to target for your Intune rollout, the rollout timeframe for each group, and the enrollment approaches you will use.</span></span>

## <a name="targeted-groups-and-timeframes"></a><span data-ttu-id="80373-105">対象とするグループと期間</span><span class="sxs-lookup"><span data-stu-id="80373-105">Targeted groups and timeframes</span></span>

<span data-ttu-id="80373-106">最初に、Intune ロールアウトの対象とするグループと、[ユース ケース シナリオ](planning-guide-scenarios.md)で特定したグループを確認します。</span><span class="sxs-lookup"><span data-stu-id="80373-106">First, review the groups that are targeted with your Intune rollout and that you identified in your [use-case scenarios](planning-guide-scenarios.md).</span></span>

<span data-ttu-id="80373-107">次に、対象とする各グループの期間を決めます。</span><span class="sxs-lookup"><span data-stu-id="80373-107">Second, determine the time frame for each targeted group.</span></span> <span data-ttu-id="80373-108">この作業では通常、Intune 展開チームと対象となるグループが話し合い、各グループの最適なロールアウト期間を決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="80373-108">This task typically requires a discussion between the Intune deployment team and the targeted groups to determine the most appropriate rollout time frame for each group.</span></span> <span data-ttu-id="80373-109">こうした話し合いでは次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="80373-109">Points to cover in such a discussion include:</span></span>
* <span data-ttu-id="80373-110">変更に対するグループの意思</span><span class="sxs-lookup"><span data-stu-id="80373-110">The group’s willingness for change</span></span>
* <span data-ttu-id="80373-111">ユーザーとデバイスの数</span><span class="sxs-lookup"><span data-stu-id="80373-111">The number of users and devices</span></span>
* <span data-ttu-id="80373-112">デバイス プラットフォームの種類</span><span class="sxs-lookup"><span data-stu-id="80373-112">Types of device platforms</span></span>
* <span data-ttu-id="80373-113">要件</span><span class="sxs-lookup"><span data-stu-id="80373-113">Requirements</span></span>
* <span data-ttu-id="80373-114">地理的な場所</span><span class="sxs-lookup"><span data-stu-id="80373-114">Geographic location</span></span>
* <span data-ttu-id="80373-115">ビジネス リスク</span><span class="sxs-lookup"><span data-stu-id="80373-115">Business risk</span></span>

## <a name="rollout-phases"></a><span data-ttu-id="80373-116">ロールアウト フェーズ</span><span class="sxs-lookup"><span data-stu-id="80373-116">Rollout phases</span></span>
<span data-ttu-id="80373-117">一般的に、組織では、まず IT 部門の少数のユーザー グループを対象にしたパイロット運用として Intune ロールアウトを開始します。</span><span class="sxs-lookup"><span data-stu-id="80373-117">Organizations commonly choose to start the Intune rollout with an initial pilot, targeting a small group of users in the IT department.</span></span> <span data-ttu-id="80373-118">パイロット運用の対象を拡大して、さらに多くの IT 部門や他の組織グループのユーザーを加えてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="80373-118">The pilot can be expanded to include a broader set of IT users and may include participation from other organizational groups.</span></span>

### <a name="pilot"></a><span data-ttu-id="80373-119">パイロット運用</span><span class="sxs-lookup"><span data-stu-id="80373-119">Pilot</span></span>
<span data-ttu-id="80373-120">ロールアウトの最初のフェーズはパイロット ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="80373-120">The first phase to rollout should be to pilot users.</span></span> <span data-ttu-id="80373-121">パイロット ユーザーは、新しいソリューションの最初のユーザーであることを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80373-121">The pilot users should understand they are the first users in a new solution.</span></span> <span data-ttu-id="80373-122">構成、ドキュメント、通知を改善するためのフィードバックを提供し、その後のロールアウト フェーズで対象となる他のすべてのユーザーの負担を軽減できるよう積極的に取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="80373-122">They must be willing to provide feedback to help improve configuration, documentation, notifications, and ease the way for all other users in later rollout phases.</span></span> <span data-ttu-id="80373-123">幹部や重要な人物はパイロット ユーザーにしないでください。</span><span class="sxs-lookup"><span data-stu-id="80373-123">These users should not be executives or VIPs.</span></span>

<span data-ttu-id="80373-124">パイロット運用は、[課題](planning-guide-deployment-goals.md)をテストしたり、それまでに集めた[要件](planning-guide-requirements.md)を詳細化したりする良い機会になります。</span><span class="sxs-lookup"><span data-stu-id="80373-124">The pilot is a good opportunity for you to test the [challenges](planning-guide-deployment-goals.md) and refine [requirements](planning-guide-requirements.md) you gathered earlier.</span></span>

<span data-ttu-id="80373-125">[情報伝達](planning-guide-communication-plan.md)計画や[サポート](planning-guide-support-plan.md)計画も視野に入れて、ユーザーに与える影響が小さいうちに[テストと検証](planning-guide-test-validation.md)を行って問題を解決しましょう。</span><span class="sxs-lookup"><span data-stu-id="80373-125">Include your [communication](planning-guide-communication-plan.md) plan, [support](planning-guide-support-plan.md) plan, and [testing and validation](planning-guide-test-validation.md) to work out any problems while the impact to users is still small.</span></span>

### <a name="production-rollout"></a><span data-ttu-id="80373-126">運用ロールアウト</span><span class="sxs-lookup"><span data-stu-id="80373-126">Production rollout</span></span>
<span data-ttu-id="80373-127">パイロット運用が無事に終わったら、次は残りの組織グループを対象にして本格的な運用ロールアウトに取り掛かります。</span><span class="sxs-lookup"><span data-stu-id="80373-127">After a successful pilot, you're ready to start a full production rollout, targeting the rest of your organization’s groups.</span></span> <span data-ttu-id="80373-128">さまざまなロールアウト グループとフェーズの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="80373-128">Some examples of different rollout groups and phases are:</span></span>

-   <span data-ttu-id="80373-129">**部門**</span><span class="sxs-lookup"><span data-stu-id="80373-129">**Departments**</span></span> <br/><span data-ttu-id="80373-130">各部門を 1 つのロールアウト フェーズにすることができます。</span><span class="sxs-lookup"><span data-stu-id="80373-130">Each department can be a rollout phase.</span></span> <span data-ttu-id="80373-131">一度に部門全体を対象にします。</span><span class="sxs-lookup"><span data-stu-id="80373-131">You target an entire department at a time.</span></span> <span data-ttu-id="80373-132">この種類のロールアウトでは、各部門のユーザーはモバイル デバイスを同じようなやり方で使用し、同じアプリケーションにアクセスする傾向があります。</span><span class="sxs-lookup"><span data-stu-id="80373-132">In this type of rollout, users in each department tend to use the mobile device in the same way and access the same applications.</span></span> <span data-ttu-id="80373-133">ユーザーが同じ種類のポリシーを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80373-133">Users will likely have the same types of policies.</span></span>

-   <span data-ttu-id="80373-134">**地理的場所**</span><span class="sxs-lookup"><span data-stu-id="80373-134">**Geography**</span></span> <br/><span data-ttu-id="80373-135">この方法では、特定の地域内 (同じ大陸、国、地域、同じ会社の建物など) のすべてのユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="80373-135">In this approach, you deploy to all users in a specific geography whether it’s the same continent, country, region, or same company’s building.</span></span> <span data-ttu-id="80373-136">この種類の段階的展開では、特定の場所のユーザーに集中することができます。</span><span class="sxs-lookup"><span data-stu-id="80373-136">This type of phased deployment lets you focus on the specific location of users.</span></span> <span data-ttu-id="80373-137">Intune を同時に展開する場所の数を軽減できるため、より多くの[ホワイト グローブ](#user-assisted-enrollment) アプローチを提供できます。</span><span class="sxs-lookup"><span data-stu-id="80373-137">This could let you provide more of a  [white glove](#user-assisted-enrollment) approach because the number of locations deploying Intune at the same time is reduced.</span></span> <span data-ttu-id="80373-138">1 つの場所に複数の部門やユース ケースが存在する可能性があるため、同時に複数のユース ケースが展開される場合があります。</span><span class="sxs-lookup"><span data-stu-id="80373-138">Because there are chances of different departments or use cases being at the same location, different use cases might be deployed at the same time.</span></span>

-   <span data-ttu-id="80373-139">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="80373-139">**Platform**</span></span> <br/><span data-ttu-id="80373-140">この種類の展開では、複数の類似したプラットフォームを同時に展開します。</span><span class="sxs-lookup"><span data-stu-id="80373-140">This type of deployment consists of deploying similar platforms at the same time.</span></span> <span data-ttu-id="80373-141">たとえば、1 か月目にすべての iOS デバイス、翌月に Android、その翌月に Windows などです。</span><span class="sxs-lookup"><span data-stu-id="80373-141">An example might be all iOS devices the first month, followed by Android, followed by Windows.</span></span> <span data-ttu-id="80373-142">この種類の段階的展開では、ヘルプデスクは一度に 1 つのプラットフォームだけをサポートすれば良いため、サポートしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="80373-142">This type of phased deployment helps simplify helpdesk support because helpdesk would only have to support a single platform at a time.</span></span>

<span data-ttu-id="80373-143">対象となるグループと期間を含む Intune ロールアウト計画の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="80373-143">Here’s an example of an Intune rollout plan that includes targeted groups and timelines:</span></span>

| <span data-ttu-id="80373-144">**ロールアウト フェーズ**</span><span class="sxs-lookup"><span data-stu-id="80373-144">**Rollout phase**</span></span> | <span data-ttu-id="80373-145">**7 月**</span><span class="sxs-lookup"><span data-stu-id="80373-145">**July**</span></span> | <span data-ttu-id="80373-146">**8 月**</span><span class="sxs-lookup"><span data-stu-id="80373-146">**August**</span></span> | <span data-ttu-id="80373-147">**9 月**</span><span class="sxs-lookup"><span data-stu-id="80373-147">**September**</span></span> | <span data-ttu-id="80373-148">**10 月**</span><span class="sxs-lookup"><span data-stu-id="80373-148">**October**</span></span> |
|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="80373-149">限定パイロット運用</span><span class="sxs-lookup"><span data-stu-id="80373-149">Limited Pilot</span></span> | <span data-ttu-id="80373-150">IT 部門 (50 ユーザー)</span><span class="sxs-lookup"><span data-stu-id="80373-150">IT (50 users)</span></span> |  |  |  |                                                         
| <span data-ttu-id="80373-151">拡張パイロット運用</span><span class="sxs-lookup"><span data-stu-id="80373-151">Expanded Pilot</span></span> | <span data-ttu-id="80373-152">IT 部門 (200 ユーザー)、IT 部門の幹部 (10 ユーザー)</span><span class="sxs-lookup"><span data-stu-id="80373-152">IT (200 users), IT Executives (10 users)</span></span> |  |  |  |                                                         
| <span data-ttu-id="80373-153">運用ロールアウト フェーズ 1</span><span class="sxs-lookup"><span data-stu-id="80373-153">Production rollout phase 1</span></span> |  | <span data-ttu-id="80373-154">営業/マーケティング (2,000 ユーザー)</span><span class="sxs-lookup"><span data-stu-id="80373-154">Sales and Marketing (2000 users)</span></span> |  |  |
| <span data-ttu-id="80373-155">運用ロールアウト フェーズ 2</span><span class="sxs-lookup"><span data-stu-id="80373-155">Production rollout phase 2</span></span> |  |  | <span data-ttu-id="80373-156">小売 (1,000 ユーザー)</span><span class="sxs-lookup"><span data-stu-id="80373-156">Retail (1000 users)</span></span> |  |
| <span data-ttu-id="80373-157">運用ロールアウト フェーズ 3</span><span class="sxs-lookup"><span data-stu-id="80373-157">Production rollout phase 3</span></span> |  |  |  | <span data-ttu-id="80373-158">人事 (50 ユーザー)、財務 (40 ユーザー)、幹部 (30 ユーザー)</span><span class="sxs-lookup"><span data-stu-id="80373-158">HR (50 users), Finance (40 users), Executives (30 users)</span></span> |

<span data-ttu-id="80373-159">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、組織のロールアウト フェーズを入力できます。</span><span class="sxs-lookup"><span data-stu-id="80373-159">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to enter your organization’s rollout phases.</span></span>
## <a name="match-rollout-groups-to-enrollment-approaches"></a><span data-ttu-id="80373-160">ロールアウト グループと登録方法のマッチング</span><span class="sxs-lookup"><span data-stu-id="80373-160">Match rollout groups to enrollment approaches</span></span>

<span data-ttu-id="80373-161">Intune ロールアウトの対象となるグループと期間を決めたら、次の手順では各グループに最適な Intune 登録方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="80373-161">Now that you have determined the targeted groups and time frames for your Intune rollout, the next step is to choose the most appropriate Intune enrollment approach for each group.</span></span> <span data-ttu-id="80373-162">以下のようなさまざまな登録方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="80373-162">There are different enrollment approaches you can use including:</span></span>
* <span data-ttu-id="80373-163">ユーザーのセルフサービス</span><span class="sxs-lookup"><span data-stu-id="80373-163">User self-service</span></span>
* <span data-ttu-id="80373-164">ユーザー支援型登録</span><span class="sxs-lookup"><span data-stu-id="80373-164">User assisted-enrollment</span></span>
* <span data-ttu-id="80373-165">IT 技術説明会</span><span class="sxs-lookup"><span data-stu-id="80373-165">IT tech fair</span></span>

### <a name="user-self-service"></a><span data-ttu-id="80373-166">ユーザーのセルフサービス</span><span class="sxs-lookup"><span data-stu-id="80373-166">User self-service</span></span>

<span data-ttu-id="80373-167">ここでは、ユーザーが責任を持って自分のデバイスを登録します。通常、IT 部門の指示に従って登録します。</span><span class="sxs-lookup"><span data-stu-id="80373-167">In this case, the user is responsible for enrolling their own device, usually following enrollment instructions provided by their IT organization.</span></span> <span data-ttu-id="80373-168">この方法は組織で最もよく使用されており、ユーザー支援型登録よりもスケーラブルな方法です。</span><span class="sxs-lookup"><span data-stu-id="80373-168">This approach is most commonly used in organizations and is more scalable than user-assisted enrollment.</span></span>

### <a name="user-assisted-enrollment"></a><span data-ttu-id="80373-169">ユーザー支援型登録</span><span class="sxs-lookup"><span data-stu-id="80373-169">User-assisted enrollment</span></span>

<span data-ttu-id="80373-170">これは ”ホワイト グローブ” アプローチと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="80373-170">This is known as a "white glove" approach.</span></span> <span data-ttu-id="80373-171">IT 部門のメンバーが直接、または Skype を使用して、ユーザーの登録作業をサポートします。</span><span class="sxs-lookup"><span data-stu-id="80373-171">An IT team member helps the user through the enrollment process, in person or with Skype.</span></span> <span data-ttu-id="80373-172">この方法は通常、幹部や、登録プロセスで特に支援が必要と思われるグループに使用されます。</span><span class="sxs-lookup"><span data-stu-id="80373-172">This approach is commonly used with executive staff and other groups that might need more assistance during the enrollment process.</span></span>

### <a name="it-tech-fair"></a><span data-ttu-id="80373-173">IT 技術説明会</span><span class="sxs-lookup"><span data-stu-id="80373-173">IT tech fair</span></span>

<span data-ttu-id="80373-174">Intune のユーザー登録のもう 1 つの選択肢は、IT 技術説明会を開くことです。</span><span class="sxs-lookup"><span data-stu-id="80373-174">Another option for Intune user enrollment is to have an IT technical fair.</span></span> <span data-ttu-id="80373-175">このイベントでは、IT 部門が Intune 登録サポート ブースを設置します。ユーザーはそこで Intune 登録に関する情報を入手し、不明な点を聞き、登録プロセスについてサポートを受けることができます。</span><span class="sxs-lookup"><span data-stu-id="80373-175">At this event, the IT group sets up an Intune enrollment assistance booth where users could receive information on Intune enrollment, ask questions, and receive assistance with the enrollment process.</span></span> <span data-ttu-id="80373-176">この選択肢は、Intune ロールアウトの初期フェーズでは特に、IT 部門とユーザーの両方に利点があります。</span><span class="sxs-lookup"><span data-stu-id="80373-176">This option can be beneficial for both the IT group and users, especially during early phases of Intune rollout.</span></span>

<span data-ttu-id="80373-177">上記の Intune ロールアウト計画の例を、登録方法も含めて以下にまとめます。</span><span class="sxs-lookup"><span data-stu-id="80373-177">Here’s an updated example of the above Intune rollout plan to include enrollment approaches:</span></span>

| <span data-ttu-id="80373-178">**ロールアウト フェーズ**</span><span class="sxs-lookup"><span data-stu-id="80373-178">**Rollout phase**</span></span> | <span data-ttu-id="80373-179">**7 月**</span><span class="sxs-lookup"><span data-stu-id="80373-179">**July**</span></span> | <span data-ttu-id="80373-180">**8 月**</span><span class="sxs-lookup"><span data-stu-id="80373-180">**August**</span></span> | <span data-ttu-id="80373-181">**9 月**</span><span class="sxs-lookup"><span data-stu-id="80373-181">**September**</span></span> | <span data-ttu-id="80373-182">**10 月**</span><span class="sxs-lookup"><span data-stu-id="80373-182">**October**</span></span> |
|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="80373-183">限定パイロット運用</span><span class="sxs-lookup"><span data-stu-id="80373-183">Limited Pilot</span></span> |  |  |  |  |                                                         
| <span data-ttu-id="80373-184">セルフサービス</span><span class="sxs-lookup"><span data-stu-id="80373-184">Self-service</span></span> | <span data-ttu-id="80373-185">IT 部門</span><span class="sxs-lookup"><span data-stu-id="80373-185">IT</span></span> |  |  |  |
| <span data-ttu-id="80373-186">拡張パイロット運用</span><span class="sxs-lookup"><span data-stu-id="80373-186">Expanded Pilot</span></span> |  |  |  |  |                                                         
| <span data-ttu-id="80373-187">セルフサービス</span><span class="sxs-lookup"><span data-stu-id="80373-187">Self-service</span></span> | <span data-ttu-id="80373-188">IT 部門</span><span class="sxs-lookup"><span data-stu-id="80373-188">IT</span></span> |  |  |  |
| <span data-ttu-id="80373-189">ホワイト グローブ</span><span class="sxs-lookup"><span data-stu-id="80373-189">White glove</span></span> | <span data-ttu-id="80373-190">IT 部門の幹部</span><span class="sxs-lookup"><span data-stu-id="80373-190">IT Executives</span></span> |  |  |  |
| <span data-ttu-id="80373-191">運用ロールアウト フェーズ 1</span><span class="sxs-lookup"><span data-stu-id="80373-191">Production rollout phase 1</span></span> |  | <span data-ttu-id="80373-192">営業/マーケティング</span><span class="sxs-lookup"><span data-stu-id="80373-192">Sales, Marketing</span></span> |  |  |
| <span data-ttu-id="80373-193">セルフサービス</span><span class="sxs-lookup"><span data-stu-id="80373-193">Self-service</span></span> |  | <span data-ttu-id="80373-194">営業/マーケティング</span><span class="sxs-lookup"><span data-stu-id="80373-194">Sales and Marketing</span></span> |  |  |
| <span data-ttu-id="80373-195">運用ロールアウト フェーズ 2</span><span class="sxs-lookup"><span data-stu-id="80373-195">Production rollout phase 2</span></span> |  |  | <span data-ttu-id="80373-196">小売</span><span class="sxs-lookup"><span data-stu-id="80373-196">Retail</span></span> |  |
| <span data-ttu-id="80373-197">セルフサービス</span><span class="sxs-lookup"><span data-stu-id="80373-197">Self-service</span></span> |  |  |  |  |
| <span data-ttu-id="80373-198">運用ロールアウト フェーズ 3</span><span class="sxs-lookup"><span data-stu-id="80373-198">Production rollout phase 3</span></span> |  |  | <span data-ttu-id="80373-199">小売</span><span class="sxs-lookup"><span data-stu-id="80373-199">Retail</span></span> |  |
| <span data-ttu-id="80373-200">セルフサービス</span><span class="sxs-lookup"><span data-stu-id="80373-200">Self-service</span></span> |  |  |  | <span data-ttu-id="80373-201">人事、財務</span><span class="sxs-lookup"><span data-stu-id="80373-201">HR, Finance</span></span> |
| <span data-ttu-id="80373-202">ホワイト グローブ</span><span class="sxs-lookup"><span data-stu-id="80373-202">White glove</span></span> |  |  |  | <span data-ttu-id="80373-203">役員</span><span class="sxs-lookup"><span data-stu-id="80373-203">Executives</span></span> |

## <a name="next-steps"></a><span data-ttu-id="80373-204">次の手順</span><span class="sxs-lookup"><span data-stu-id="80373-204">Next steps</span></span>

<span data-ttu-id="80373-205">次のセクションは、[Intune ロールアウトの情報伝達計画を立てる](planning-guide-communication-plan.md)場合のガイダンスです。</span><span class="sxs-lookup"><span data-stu-id="80373-205">The next section provides guidance on [developing an Intune rollout communication plan](planning-guide-communication-plan.md).</span></span>
