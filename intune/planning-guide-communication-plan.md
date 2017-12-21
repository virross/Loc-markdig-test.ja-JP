---
title: "ロールアウト コミュニケーション計画の作成"
description: "この記事は、Intune を展開するためのロールアウト コミュニケーション計画を作成する場合に役立ちます。"
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 393ebe75-d001-485a-b81c-6361c8b5e6ee
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d690dc82da56836e4bc338e77b9744f0ab690e87
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="develop-a-rollout-communication-plan"></a><span data-ttu-id="afd23-103">ロールアウト コミュニケーション計画の作成</span><span class="sxs-lookup"><span data-stu-id="afd23-103">Develop a rollout communication plan</span></span>

<span data-ttu-id="afd23-104">適切な変更管理が行えるかどうかは、今後の変更に関する明確で有益な情報伝達にかかっています。</span><span class="sxs-lookup"><span data-stu-id="afd23-104">Good change management relies on clear and helpful communications about the upcoming changes.</span></span> <span data-ttu-id="afd23-105">Intune の展開を円滑に進めるには、ロールアウト コミュニケーション計画に次の 4 つの領域を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="afd23-105">To smooth the path of your Intune deployment, your rollout communication plan should include four areas:</span></span>

-   <span data-ttu-id="afd23-106">伝達する情報</span><span class="sxs-lookup"><span data-stu-id="afd23-106">What information is to be communicated</span></span>

-   <span data-ttu-id="afd23-107">伝達に使用する配信方法</span><span class="sxs-lookup"><span data-stu-id="afd23-107">The delivery method used for the communications</span></span>

-   <span data-ttu-id="afd23-108">情報を受け取るユーザー</span><span class="sxs-lookup"><span data-stu-id="afd23-108">Who receives the communications</span></span>

-   <span data-ttu-id="afd23-109">情報伝達のタイムライン</span><span class="sxs-lookup"><span data-stu-id="afd23-109">The timeline for communications</span></span>

<span data-ttu-id="afd23-110">それぞれの領域について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="afd23-110">Let’s review each area in more detail.</span></span>

## <a name="what-needs-to-be-communicated"></a><span data-ttu-id="afd23-111">伝達する必要がある情報</span><span class="sxs-lookup"><span data-stu-id="afd23-111">What needs to be communicated?</span></span>

<span data-ttu-id="afd23-112">伝達する情報は、Intune ロールアウト プロセスのどの段階で伝達するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="afd23-112">Determining what information to be communicated depends on when in the Intune rollout process you are communicating.</span></span> <span data-ttu-id="afd23-113">組織によっては、Intune ロールアウトのキックオフ、登録前、登録後の順に、組織グループとユーザーに段階的に伝達する場合があります。</span><span class="sxs-lookup"><span data-stu-id="afd23-113">You might decide to communicate in waves to your organizational groups and users, starting with an Intune rollout kickoff, followed by pre-enrollment, and follow up with post-enrollment.</span></span> <span data-ttu-id="afd23-114">各段階で伝達される可能性がある情報の種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="afd23-114">Let’s discuss the type of information that could be communicated in each wave.</span></span>

<span data-ttu-id="afd23-115">**キックオフ段階**</span><span class="sxs-lookup"><span data-stu-id="afd23-115">**Kickoff wave**</span></span> <br/><span data-ttu-id="afd23-116">Intune プロジェクト自体を紹介する広範な情報伝達。</span><span class="sxs-lookup"><span data-stu-id="afd23-116">Broad communications that introduce the Intune project itself.</span></span> <span data-ttu-id="afd23-117">Intune の概要や Intune を採用する理由 (組織やユーザーにとっての利点) などの質問に答え、展開とロールアウトに関する計画の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="afd23-117">It should answer questions like what is Intune, why the organization is adopting Intune (benefits to the organization and users), and provide a high-level plan of the deployment and rollout.</span></span>

<span data-ttu-id="afd23-118">**登録前段階**</span><span class="sxs-lookup"><span data-stu-id="afd23-118">**Pre-enrollment wave**</span></span><br/> <span data-ttu-id="afd23-119">Intune と補助的なサービス (Office、Outlook、OneDrive など) に関する情報、組織グループとユーザーが Intune を受け取る予定に関するユーザー リソースと具体的なタイムラインを含む広範な情報伝達。</span><span class="sxs-lookup"><span data-stu-id="afd23-119">Broad communications that include additional information about Intune and complementary offerings (for example, Office, Outlook, OneDrive), user resources, and specific timelines for when organization groups and users are scheduled to receive Intune.</span></span>

<span data-ttu-id="afd23-120">**登録段階**</span><span class="sxs-lookup"><span data-stu-id="afd23-120">**Enrollment wave**</span></span><br/> <span data-ttu-id="afd23-121">Intune を受け取る予定の組織グループ/ユーザーを対象にした情報伝達。</span><span class="sxs-lookup"><span data-stu-id="afd23-121">Communications targeting organization groups and users that are scheduled to receive Intune.</span></span> <span data-ttu-id="afd23-122">Intune を受け取る準備が整ったことをユーザーに知らせ、登録手順と、サポートや質問の窓口に関する情報を伝えます。</span><span class="sxs-lookup"><span data-stu-id="afd23-122">These should inform the users that they are ready to receive Intune and provide enrollment instructions along with contact information for getting assistance or asking questions.</span></span>

<span data-ttu-id="afd23-123">**登録後段階**</span><span class="sxs-lookup"><span data-stu-id="afd23-123">**Post enrollment wave**</span></span><br/> <span data-ttu-id="afd23-124">Intune に登録された組織グループ/ユーザーを対象とする情報伝達。</span><span class="sxs-lookup"><span data-stu-id="afd23-124">Communications targeting organization groups and users that have enrolled in Intune.</span></span> <span data-ttu-id="afd23-125">ユーザーに役立つ追加のリソースを提供し、登録時と登録後の使用感に関するフィードバックを収集します。</span><span class="sxs-lookup"><span data-stu-id="afd23-125">These should provide additional resources that might be helpful to the user, and collect feedback about their experience during and after enrollment.</span></span>

<span data-ttu-id="afd23-126">こちらの [エンドユーザー登録ガイド](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) もお役立てください。</span><span class="sxs-lookup"><span data-stu-id="afd23-126">You may find this [end-user enrollment guide](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) helpful.</span></span> <span data-ttu-id="afd23-127">そのまま使用することも、組織に合わせて変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="afd23-127">You can use it as is or modify for your organization.</span></span>

## <a name="communication-delivery-methods"></a><span data-ttu-id="afd23-128">情報の配信方法</span><span class="sxs-lookup"><span data-stu-id="afd23-128">Communication delivery methods</span></span>

<span data-ttu-id="afd23-129">Intune ロールアウトに関する情報を対象となる組織グループとユーザーに伝達するには、いくつかの配信方法があります。</span><span class="sxs-lookup"><span data-stu-id="afd23-129">There are several delivery methods you can use to communicate Intune rollout information to your targeted organizational groups and users.</span></span> <span data-ttu-id="afd23-130">次の一覧では、情報の配信方法の例とその方法を使用する段階を示しています。</span><span class="sxs-lookup"><span data-stu-id="afd23-130">The following list shows some examples and the wave you can use the method with:</span></span>

-   <span data-ttu-id="afd23-131">組織全体を対象にした対面の会議または Skype 会議 (キックオフ段階)</span><span class="sxs-lookup"><span data-stu-id="afd23-131">Organizational-wide in-person or Skype meetings used for kickoff wave</span></span>

-   <span data-ttu-id="afd23-132">電子メール (登録前段階、登録段階、登録後段階)</span><span class="sxs-lookup"><span data-stu-id="afd23-132">Email used for pre-enrollment, enrollment, and post-enrollment waves</span></span>

-   <span data-ttu-id="afd23-133">組織の Web サイト (すべての段階)</span><span class="sxs-lookup"><span data-stu-id="afd23-133">Organization web sites used for all waves</span></span>

-   <span data-ttu-id="afd23-134">Yammer、ポスター、チラシ (キックオフ段階、登録前段階)</span><span class="sxs-lookup"><span data-stu-id="afd23-134">Yammer, posters, and flyers used for kickoff and pre-enrollment waves</span></span>

## <a name="communications-timeline"></a><span data-ttu-id="afd23-135">情報伝達のタイムライン</span><span class="sxs-lookup"><span data-stu-id="afd23-135">Communications timeline</span></span>

<span data-ttu-id="afd23-136">伝達する必要がある内容と使用する情報伝達方法を決めたら、次の手順は、情報を伝達するタイミングと相手など、情報伝達のタイムラインを決めることです。</span><span class="sxs-lookup"><span data-stu-id="afd23-136">After determining what you need to communicate and the methods you will use, determine the timeline for your communications that includes when and who would receive the communications.</span></span>

<span data-ttu-id="afd23-137">たとえば、最初の Intune プロジェクト キックオフの情報伝達は、組織全体または一部のみを対象にして、Intune ロールアウトを開始する数週間前に行います。</span><span class="sxs-lookup"><span data-stu-id="afd23-137">For example, the initial Intune project kickoff communications can target the entire organization or just a subset, and take place over several weeks before the Intune rollout begins.</span></span> <span data-ttu-id="afd23-138">次に、Intune ロールアウト スケジュールに合わせて組織グループとユーザーに段階的に伝えます。</span><span class="sxs-lookup"><span data-stu-id="afd23-138">After that, information could be communicated in waves to organizational groups and users, aligned with their Intune rollout schedule.</span></span> <span data-ttu-id="afd23-139">次の例は、Intune ロールアウトの情報伝達の大まかな計画のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="afd23-139">The following example is a sample high-level Intune rollout communications plan:</span></span>

  | <span data-ttu-id="afd23-140">**情報伝達計画**</span><span class="sxs-lookup"><span data-stu-id="afd23-140">**Communication plan**</span></span> | <span data-ttu-id="afd23-141">**7 月**</span><span class="sxs-lookup"><span data-stu-id="afd23-141">**July**</span></span> | <span data-ttu-id="afd23-142">**8 月**</span><span class="sxs-lookup"><span data-stu-id="afd23-142">**August**</span></span> | <span data-ttu-id="afd23-143">**9 月**</span><span class="sxs-lookup"><span data-stu-id="afd23-143">**September**</span></span> | <span data-ttu-id="afd23-144">**10 月**</span><span class="sxs-lookup"><span data-stu-id="afd23-144">**October**</span></span> |
|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="afd23-145">段階 1</span><span class="sxs-lookup"><span data-stu-id="afd23-145">Wave 1</span></span>  | <span data-ttu-id="afd23-146">すべて</span><span class="sxs-lookup"><span data-stu-id="afd23-146">All</span></span> |  |  |  |                                                         
| <span data-ttu-id="afd23-147">キックオフ会議</span><span class="sxs-lookup"><span data-stu-id="afd23-147">Kickoff meeting</span></span> | <span data-ttu-id="afd23-148">第 1 週</span><span class="sxs-lookup"><span data-stu-id="afd23-148">First week</span></span> |  |  |  |                                                         
| <span data-ttu-id="afd23-149">段階 2</span><span class="sxs-lookup"><span data-stu-id="afd23-149">Wave 2</span></span> | <span data-ttu-id="afd23-150">IT 部門</span><span class="sxs-lookup"><span data-stu-id="afd23-150">IT</span></span> | <span data-ttu-id="afd23-151">営業/マーケティング</span><span class="sxs-lookup"><span data-stu-id="afd23-151">Sales and Marketing</span></span> | <span data-ttu-id="afd23-152">小売</span><span class="sxs-lookup"><span data-stu-id="afd23-152">Retail</span></span> | <span data-ttu-id="afd23-153">人事、財務、幹部</span><span class="sxs-lookup"><span data-stu-id="afd23-153">HR, Finance, and Executives</span></span> |
| <span data-ttu-id="afd23-154">ロールアウト前電子メール 1</span><span class="sxs-lookup"><span data-stu-id="afd23-154">Pre-rollout Email 1</span></span> | <span data-ttu-id="afd23-155">第 1 週</span><span class="sxs-lookup"><span data-stu-id="afd23-155">First week</span></span> | <span data-ttu-id="afd23-156">第 1 週</span><span class="sxs-lookup"><span data-stu-id="afd23-156">First week</span></span> | <span data-ttu-id="afd23-157">第 1 週</span><span class="sxs-lookup"><span data-stu-id="afd23-157">First week</span></span> | <span data-ttu-id="afd23-158">第 1 週</span><span class="sxs-lookup"><span data-stu-id="afd23-158">First week</span></span> |
| <span data-ttu-id="afd23-159">段階 3</span><span class="sxs-lookup"><span data-stu-id="afd23-159">Wave 3</span></span> | <span data-ttu-id="afd23-160">IT 部門</span><span class="sxs-lookup"><span data-stu-id="afd23-160">IT</span></span> | <span data-ttu-id="afd23-161">営業/マーケティング</span><span class="sxs-lookup"><span data-stu-id="afd23-161">Sales and Marketing</span></span> | <span data-ttu-id="afd23-162">小売</span><span class="sxs-lookup"><span data-stu-id="afd23-162">Retail</span></span> | <span data-ttu-id="afd23-163">人事、財務、幹部</span><span class="sxs-lookup"><span data-stu-id="afd23-163">HR, Finance, and Executives</span></span> |
| <span data-ttu-id="afd23-164">ロールアウト前電子メール 2</span><span class="sxs-lookup"><span data-stu-id="afd23-164">Pre-rollout Email 2</span></span> | <span data-ttu-id="afd23-165">第 2 週</span><span class="sxs-lookup"><span data-stu-id="afd23-165">Second week</span></span> | <span data-ttu-id="afd23-166">第 2 週</span><span class="sxs-lookup"><span data-stu-id="afd23-166">Second week</span></span> | <span data-ttu-id="afd23-167">第 2 週</span><span class="sxs-lookup"><span data-stu-id="afd23-167">Second week</span></span> | <span data-ttu-id="afd23-168">第 2 週</span><span class="sxs-lookup"><span data-stu-id="afd23-168">Second week</span></span> |
| <span data-ttu-id="afd23-169">段階 4</span><span class="sxs-lookup"><span data-stu-id="afd23-169">Wave 4</span></span> | <span data-ttu-id="afd23-170">IT 部門</span><span class="sxs-lookup"><span data-stu-id="afd23-170">IT</span></span> | <span data-ttu-id="afd23-171">営業/マーケティング</span><span class="sxs-lookup"><span data-stu-id="afd23-171">Sales and Marketing</span></span> | <span data-ttu-id="afd23-172">小売</span><span class="sxs-lookup"><span data-stu-id="afd23-172">Retail</span></span> | <span data-ttu-id="afd23-173">人事、財務、幹部</span><span class="sxs-lookup"><span data-stu-id="afd23-173">HR, Finance, and Executives</span></span> |
| <span data-ttu-id="afd23-174">登録電子メール</span><span class="sxs-lookup"><span data-stu-id="afd23-174">Enrollment email</span></span> | <span data-ttu-id="afd23-175">第 3 週</span><span class="sxs-lookup"><span data-stu-id="afd23-175">Third week</span></span> | <span data-ttu-id="afd23-176">第 3 週</span><span class="sxs-lookup"><span data-stu-id="afd23-176">Third week</span></span> | <span data-ttu-id="afd23-177">第 3 週</span><span class="sxs-lookup"><span data-stu-id="afd23-177">Third week</span></span> | <span data-ttu-id="afd23-178">第 3 週</span><span class="sxs-lookup"><span data-stu-id="afd23-178">Third week</span></span> |
| <span data-ttu-id="afd23-179">段階 5</span><span class="sxs-lookup"><span data-stu-id="afd23-179">Wave 5</span></span> | <span data-ttu-id="afd23-180">IT 部門</span><span class="sxs-lookup"><span data-stu-id="afd23-180">IT</span></span> | <span data-ttu-id="afd23-181">営業/マーケティング</span><span class="sxs-lookup"><span data-stu-id="afd23-181">Sales and Marketing</span></span> | <span data-ttu-id="afd23-182">小売</span><span class="sxs-lookup"><span data-stu-id="afd23-182">Retail</span></span> | <span data-ttu-id="afd23-183">人事、財務、幹部</span><span class="sxs-lookup"><span data-stu-id="afd23-183">HR, Finance, and Executives</span></span> |
| <span data-ttu-id="afd23-184">登録後電子メール</span><span class="sxs-lookup"><span data-stu-id="afd23-184">Post-enrollment email</span></span> | <span data-ttu-id="afd23-185">第 4 週</span><span class="sxs-lookup"><span data-stu-id="afd23-185">Fourth week</span></span> | <span data-ttu-id="afd23-186">第 4 週</span><span class="sxs-lookup"><span data-stu-id="afd23-186">Fourth week</span></span> | <span data-ttu-id="afd23-187">第 4 週</span><span class="sxs-lookup"><span data-stu-id="afd23-187">Fourth week</span></span> | <span data-ttu-id="afd23-188">第 4 週</span><span class="sxs-lookup"><span data-stu-id="afd23-188">Fourth week</span></span> |

<span data-ttu-id="afd23-189">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) してコミュニケーション計画を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="afd23-189">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to develop your communication plan.</span></span>

## <a name="next-step"></a><span data-ttu-id="afd23-190">次の手順</span><span class="sxs-lookup"><span data-stu-id="afd23-190">Next step</span></span>

<span data-ttu-id="afd23-191">次のセクションは、[サポート計画](planning-guide-support-plan.md)を立てる場合のガイダンスです。</span><span class="sxs-lookup"><span data-stu-id="afd23-191">The next section provides guidance on [developing a support plan](planning-guide-support-plan.md).</span></span>
