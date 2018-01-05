---
title: "ユース ケース シナリオを特定する"
description: "この記事は、Microsoft Intune クラウドのみの実装に関する Intune ユース ケース シナリオとサブ ユース ケース シナリオの特定について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 864f99f52e0c8b46307f1ec24d11da51d8f52662
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="identify-mobile-device-management-use-case-scenarios"></a><span data-ttu-id="d86ef-103">モバイル デバイス管理のユース ケース シナリオを特定する</span><span class="sxs-lookup"><span data-stu-id="d86ef-103">Identify mobile device management use-case scenarios</span></span>

<span data-ttu-id="d86ef-104">ユース ケース シナリオの特定は、正常な Intune 展開のための計画プロセスにおいて重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="d86ef-104">Identifying your use-case scenarios is an important part of the planning process for a successful Intune deployment.</span></span> <span data-ttu-id="d86ef-105">ユース ケース シナリオが役立つのは、ユーザーの種類またはロール、ユーザーのデバイス (たとえば、会社または個人) の所有権によって、ユーザーを管理しやすいグループに分割できるからです。</span><span class="sxs-lookup"><span data-stu-id="d86ef-105">Use-case scenarios are helpful because they let you segment your users into manageable groups by user type or role, and the ownership of the user's device (for example, company or personal).</span></span>

<span data-ttu-id="d86ef-106">組織が Intune ユース ケース シナリオ、組織グループ、そして各ユース ケースに関連付けられるモバイル デバイス プラットフォームなどを特定するのに役立つ、いくつかの例について説明します。</span><span class="sxs-lookup"><span data-stu-id="d86ef-106">Let’s discuss a few examples to help your organization identify Intune use-case scenarios, as well as organizational groups, and mobile device platforms associated with each use case.</span></span>

## <a name="device-ownership"></a><span data-ttu-id="d86ef-107">デバイスの所有権</span><span class="sxs-lookup"><span data-stu-id="d86ef-107">Device ownership</span></span>
<span data-ttu-id="d86ef-108">お客様の展開向けの主なユース ケース シナリオを特定するには、組織の Intune 展開の目標と目的を確認することから始めます。</span><span class="sxs-lookup"><span data-stu-id="d86ef-108">You can begin by referring to your organization's Intune deployment goals and objectives to help identity the main use-case scenarios for your deployment.</span></span> <span data-ttu-id="d86ef-109">Intune 展開計画の範囲内で、以下の質問にお答えください。</span><span class="sxs-lookup"><span data-stu-id="d86ef-109">Within the scope of your Intune deployment plan, answer the following questions:</span></span>

-   <span data-ttu-id="d86ef-110">会社所有のデバイスをサポートする予定ですか。</span><span class="sxs-lookup"><span data-stu-id="d86ef-110">Are you planning to support corporate owned devices?</span></span>

-   <span data-ttu-id="d86ef-111">個人所有のデバイス (BYOD) をサポートする予定ですか。</span><span class="sxs-lookup"><span data-stu-id="d86ef-111">Are you planning to support personally owned devices (BYOD)?</span></span>

<span data-ttu-id="d86ef-112">これらの質問はどちらか 1 つを選択する類のものではありません。</span><span class="sxs-lookup"><span data-stu-id="d86ef-112">These are not either/or options.</span></span> <span data-ttu-id="d86ef-113">両方の形式のデバイス所有権をサポートして組織の目標を果たす必要があると気付く場合があります。</span><span class="sxs-lookup"><span data-stu-id="d86ef-113">You may find you need to support both forms of device ownership to meet your organizational goals.</span></span> <span data-ttu-id="d86ef-114">サブ ユース ケースは、異なるデバイス管理ポリシーを適用する場所を明らかにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d86ef-114">The sub-use-cases will help clarify where to apply the different device management policies.</span></span>

### <a name="user-type-or-device-role"></a><span data-ttu-id="d86ef-115">ユーザーの種類またはデバイスのロール</span><span class="sxs-lookup"><span data-stu-id="d86ef-115">User type or device role</span></span>

<span data-ttu-id="d86ef-116">各ユース ケース シナリオにサブ ユース ケースが含まれるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d86ef-116">Determine if each use-case scenario also includes sub-use-cases.</span></span> <span data-ttu-id="d86ef-117">たとえば、組織が会社のユース ケース シナリオをサポートするための要件を特定していて、そのシナリオに、以下のようなユーザーの種類またはデバイスのロールに基づいた追加のサブ ユース ケースが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="d86ef-117">For example, your organization may have identified requirements to support a corporate use-case scenario that includes additional sub-use-cases based on user type or device role, such as:</span></span>

-   <span data-ttu-id="d86ef-118">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="d86ef-118">Information worker</span></span>

-   <span data-ttu-id="d86ef-119">役員</span><span class="sxs-lookup"><span data-stu-id="d86ef-119">Executive</span></span>

-   <span data-ttu-id="d86ef-120">キオスク</span><span class="sxs-lookup"><span data-stu-id="d86ef-120">Kiosk</span></span>

<span data-ttu-id="d86ef-121">ユース ケース シナリオとサブ ユース ケース シナリオのいくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d86ef-121">Here are a few examples of use-case and sub-use-case scenarios:</span></span>

| <span data-ttu-id="d86ef-122">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="d86ef-122">**Use cases**</span></span> | <span data-ttu-id="d86ef-123">**サブ ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="d86ef-123">**Sub-use cases**</span></span> |
|:---:|:---:|
| <span data-ttu-id="d86ef-124">企業</span><span class="sxs-lookup"><span data-stu-id="d86ef-124">Corporate</span></span> | <span data-ttu-id="d86ef-125">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="d86ef-125">Information worker</span></span> |              
| <span data-ttu-id="d86ef-126">企業</span><span class="sxs-lookup"><span data-stu-id="d86ef-126">Corporate</span></span> | <span data-ttu-id="d86ef-127">役員</span><span class="sxs-lookup"><span data-stu-id="d86ef-127">Executives</span></span> |           
| <span data-ttu-id="d86ef-128">企業</span><span class="sxs-lookup"><span data-stu-id="d86ef-128">Corporate</span></span> | <span data-ttu-id="d86ef-129">キオスク</span><span class="sxs-lookup"><span data-stu-id="d86ef-129">Kiosk</span></span> |
| <span data-ttu-id="d86ef-130">BYOD</span><span class="sxs-lookup"><span data-stu-id="d86ef-130">BYOD</span></span> | <span data-ttu-id="d86ef-131">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="d86ef-131">Information worker</span></span> |           
| <span data-ttu-id="d86ef-132">BYOD</span><span class="sxs-lookup"><span data-stu-id="d86ef-132">BYOD</span></span> | <span data-ttu-id="d86ef-133">役員</span><span class="sxs-lookup"><span data-stu-id="d86ef-133">Executives</span></span> |

<span data-ttu-id="d86ef-134">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、お客様の組織のユース ケース シナリオとサブ ユース ケース シナリオを入力できます。</span><span class="sxs-lookup"><span data-stu-id="d86ef-134">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to enter your organization’s use-case and sub-use-case scenarios.</span></span>

## <a name="organizational-groups-for-your-scenarios"></a><span data-ttu-id="d86ef-135">シナリオ用の組織のグループ</span><span class="sxs-lookup"><span data-stu-id="d86ef-135">Organizational groups for your scenarios</span></span>

<span data-ttu-id="d86ef-136">次に、各ユース ケースとサブ ユース ケース シナリオに関連付けられている組織グループを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d86ef-136">Now you need to identify the organizational groups that are associated with each use-case and sub-use-case scenario.</span></span> <span data-ttu-id="d86ef-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d86ef-137">For example:</span></span>

| <span data-ttu-id="d86ef-138">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="d86ef-138">**Use cases**</span></span> | <span data-ttu-id="d86ef-139">**サブ ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="d86ef-139">**Sub-use cases**</span></span> | <span data-ttu-id="d86ef-140">**組織グループ**</span><span class="sxs-lookup"><span data-stu-id="d86ef-140">**Organizational groups**</span></span> |
|:---:|:---:|:---:|
| <span data-ttu-id="d86ef-141">企業</span><span class="sxs-lookup"><span data-stu-id="d86ef-141">Corporate</span></span> | <span data-ttu-id="d86ef-142">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="d86ef-142">Information worker</span></span> | <span data-ttu-id="d86ef-143">人事、財務</span><span class="sxs-lookup"><span data-stu-id="d86ef-143">HR, Finance</span></span> |               
| <span data-ttu-id="d86ef-144">企業</span><span class="sxs-lookup"><span data-stu-id="d86ef-144">Corporate</span></span> | <span data-ttu-id="d86ef-145">役員</span><span class="sxs-lookup"><span data-stu-id="d86ef-145">Executive</span></span> | <span data-ttu-id="d86ef-146">人事、財務</span><span class="sxs-lookup"><span data-stu-id="d86ef-146">HR, Finance</span></span> |            
| <span data-ttu-id="d86ef-147">企業</span><span class="sxs-lookup"><span data-stu-id="d86ef-147">Corporate</span></span> | <span data-ttu-id="d86ef-148">キオスク</span><span class="sxs-lookup"><span data-stu-id="d86ef-148">Kiosk</span></span> | <span data-ttu-id="d86ef-149">小売</span><span class="sxs-lookup"><span data-stu-id="d86ef-149">Retail</span></span> |
| <span data-ttu-id="d86ef-150">BYOD</span><span class="sxs-lookup"><span data-stu-id="d86ef-150">BYOD</span></span> | <span data-ttu-id="d86ef-151">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="d86ef-151">Information worker</span></span> | <span data-ttu-id="d86ef-152">マーケティング、営業</span><span class="sxs-lookup"><span data-stu-id="d86ef-152">Marketing, Sales</span></span> |            
| <span data-ttu-id="d86ef-153">BYOD</span><span class="sxs-lookup"><span data-stu-id="d86ef-153">BYOD</span></span> | <span data-ttu-id="d86ef-154">役員</span><span class="sxs-lookup"><span data-stu-id="d86ef-154">Executive</span></span> | <span data-ttu-id="d86ef-155">マーケティング、営業</span><span class="sxs-lookup"><span data-stu-id="d86ef-155">Marketing, Sales</span></span> |


## <a name="mobile-device-platforms-for-your-scenarios"></a><span data-ttu-id="d86ef-156">シナリオに合ったモバイル デバイス プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="d86ef-156">Mobile device platforms for your scenarios</span></span>

<span data-ttu-id="d86ef-157">次に、各ユース ケース シナリオに関連付けられているモバイル デバイス プラットフォームを特定します。</span><span class="sxs-lookup"><span data-stu-id="d86ef-157">The next step is to identify the mobile device platforms associated with each use-case scenario.</span></span> <span data-ttu-id="d86ef-158">候補が複数存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d86ef-158">There may be more than one.</span></span>

<span data-ttu-id="d86ef-159">たとえば、会社のユース ケース シナリオでは、iOS と Android Samsung KNOX デバイスのプラットフォームをサポートする場合があります。</span><span class="sxs-lookup"><span data-stu-id="d86ef-159">For example, your corporate use-case scenario may support iOS and Android Samsung KNOX device platforms.</span></span> <span data-ttu-id="d86ef-160">BYOD ポリシーには、Android (Samsung KNOX 以外) と Windows 10 Mobile のようなモバイル デバイス プラットフォームの追加に関するサポートが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d86ef-160">Your BYOD policy may include support for additional mobile device platforms like Android (non-Samsung KNOX) and Windows 10 Mobile.</span></span> <span data-ttu-id="d86ef-161">前述の例に基づき、モバイル デバイス プラットフォームと各ユース ケース シナリオを関連付けています。</span><span class="sxs-lookup"><span data-stu-id="d86ef-161">Building on the preceding examples, we've associated mobile device platforms with each use-case scenario.</span></span>

| <span data-ttu-id="d86ef-162">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="d86ef-162">**Use cases**</span></span> | <span data-ttu-id="d86ef-163">**サブ ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="d86ef-163">**Sub-use cases**</span></span> | <span data-ttu-id="d86ef-164">**グループ**</span><span class="sxs-lookup"><span data-stu-id="d86ef-164">**Groups**</span></span> | <span data-ttu-id="d86ef-165">**デバイス プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="d86ef-165">**Device platforms**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="d86ef-166">企業</span><span class="sxs-lookup"><span data-stu-id="d86ef-166">Corporate</span></span> | <span data-ttu-id="d86ef-167">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="d86ef-167">Information worker</span></span> | <span data-ttu-id="d86ef-168">人事、財務</span><span class="sxs-lookup"><span data-stu-id="d86ef-168">HR, Finance</span></span> | <span data-ttu-id="d86ef-169">iOS</span><span class="sxs-lookup"><span data-stu-id="d86ef-169">iOS</span></span> |                                                           
| <span data-ttu-id="d86ef-170">企業</span><span class="sxs-lookup"><span data-stu-id="d86ef-170">Corporate</span></span> | <span data-ttu-id="d86ef-171">役員</span><span class="sxs-lookup"><span data-stu-id="d86ef-171">Executives</span></span> | <span data-ttu-id="d86ef-172">人事、財務</span><span class="sxs-lookup"><span data-stu-id="d86ef-172">HR, Finance</span></span> | <span data-ttu-id="d86ef-173">iOS</span><span class="sxs-lookup"><span data-stu-id="d86ef-173">iOS</span></span> |                                                           
| <span data-ttu-id="d86ef-174">企業</span><span class="sxs-lookup"><span data-stu-id="d86ef-174">Corporate</span></span> | <span data-ttu-id="d86ef-175">キオスク</span><span class="sxs-lookup"><span data-stu-id="d86ef-175">Kiosk</span></span> | <span data-ttu-id="d86ef-176">小売</span><span class="sxs-lookup"><span data-stu-id="d86ef-176">Retail</span></span> | <span data-ttu-id="d86ef-177">Android</span><span class="sxs-lookup"><span data-stu-id="d86ef-177">Android</span></span> |
| <span data-ttu-id="d86ef-178">BYOD</span><span class="sxs-lookup"><span data-stu-id="d86ef-178">BYOD</span></span> | <span data-ttu-id="d86ef-179">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="d86ef-179">Information worker</span></span> | <span data-ttu-id="d86ef-180">マーケティング、営業</span><span class="sxs-lookup"><span data-stu-id="d86ef-180">Marketing, Sales</span></span> | <span data-ttu-id="d86ef-181">iOS</span><span class="sxs-lookup"><span data-stu-id="d86ef-181">iOS</span></span> |                                                           
| <span data-ttu-id="d86ef-182">BYOD</span><span class="sxs-lookup"><span data-stu-id="d86ef-182">BYOD</span></span> | <span data-ttu-id="d86ef-183">役員</span><span class="sxs-lookup"><span data-stu-id="d86ef-183">Executives</span></span> | <span data-ttu-id="d86ef-184">マーケティング、営業</span><span class="sxs-lookup"><span data-stu-id="d86ef-184">Marketing, Sales</span></span> | <span data-ttu-id="d86ef-185">iOS</span><span class="sxs-lookup"><span data-stu-id="d86ef-185">iOS</span></span> |

## <a name="next-steps"></a><span data-ttu-id="d86ef-186">次の手順</span><span class="sxs-lookup"><span data-stu-id="d86ef-186">Next steps</span></span>

<span data-ttu-id="d86ef-187">次のセクションでは、[各ユース ケース シナリオの Intune 要件を特定する方法](planning-guide-requirements.md)についてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d86ef-187">The next section provides guidance on [how to identify the Intune requirements for each use case scenario](planning-guide-requirements.md).</span></span>
