---
title: "ユース ケース シナリオの要件の決定"
description: "この記事は、Microsoft Intune クラウドのみの実装に関する Intune ユース ケース シナリオとサブ ユース ケース シナリオの要件の決定について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d4e7b28b137a12111347a7cbe619c5fa81ec8503
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="determine-use-case-scenario-requirements"></a><span data-ttu-id="c76d2-103">ユース ケース シナリオの要件の決定</span><span class="sxs-lookup"><span data-stu-id="c76d2-103">Determine use-case scenario requirements</span></span>

<span data-ttu-id="c76d2-104">このセクションでは、各ユース ケース シナリオ内の組織グループごとに要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="c76d2-104">In this section, you determine the requirements for each organizational group within each use-case scenario.</span></span> <span data-ttu-id="c76d2-105">このプロセスは、アーキテクチャとデザイン、オンボード、ロールアウトなど、その他の Intune 展開の計画を準備するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c76d2-105">This process helps you prepare for the other Intune deployment planning areas like architecture and design, onboarding, and rollout.</span></span> <span data-ttu-id="c76d2-106">また、Intune 展開プロジェクトに関連する潜在的なギャップと課題の特定にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c76d2-106">It can also help identify potential gaps and challenges related to your Intune deployment project.</span></span>

<span data-ttu-id="c76d2-107">ユース ケースとサブ ユース ケースの各シナリオ、関連する組織グループとモバイル デバイス プラットフォームについて、異なる要件を持つことになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c76d2-107">You might have different sets of requirements for each of your use-case and sub-use-case scenarios, and their associated organizational groups and mobile device platforms.</span></span> <span data-ttu-id="c76d2-108">たとえば、企業のユース ケース シナリオの要件では、6 文字の PIN や無効なクラウド バックアップといった、より制限の厳しいデバイス設定で Intune にデバイスを登録する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c76d2-108">For example, your corporate use-case scenario requirements might require devices to enroll into Intune with a more restrictive set of device settings, like a PIN of 6 characters or disabled cloud backup.</span></span> <span data-ttu-id="c76d2-109">"Bring Your Own Device"(BYOD) ユース ケース シナリオはより制限が少なく、4 文字の PIN とクラウド バックアップを許可する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c76d2-109">Your "bring your own device" (BYOD) use-case scenario, may be less restrictive and allow a 4-character PIN and cloud backup.</span></span>

<span data-ttu-id="c76d2-110">また、企業のユース ケース シナリオが適した組織グループが複数あり、それぞれが異なる要件セット (たとえば、PIN 設定、Wi-Fi または VPN プロファイル、展開されるアプリ) を持つという場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c76d2-110">You may also have organizational groups for the corporate use-case scenario that have different sets of requirements (for example, PIN settings, Wi-Fi or VPN profile, apps deployed).</span></span> <span data-ttu-id="c76d2-111">要件はまた、モバイル デバイス プラットフォームの機能 (たとえば、指紋認証、電子メール プロファイル) によって判断できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c76d2-111">Your requirements may also be determined by the capabilities of the mobile device platform (for example, finger print reader, email profile).</span></span>

<span data-ttu-id="c76d2-112">組織のユース ケースの要件の例を次に示します。ここでは、各ユース ケースとサブ ユース ケースのシナリオ、組織グループ、モバイル デバイス プラットフォームに対する異なる要件セットを示します。</span><span class="sxs-lookup"><span data-stu-id="c76d2-112">Here are a few examples of an organization’s use-case requirements showing different sets of requirements for each use-case and sub-use-case scenario, organizational group, and mobile device platform.</span></span> <span data-ttu-id="c76d2-113">次の表を使用して、組織のユース ケースの要件を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="c76d2-113">You can also use the following table to enter your organization’s use-case requirements:</span></span>

| <span data-ttu-id="c76d2-114">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="c76d2-114">**Use cases**</span></span> | <span data-ttu-id="c76d2-115">**サブ ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="c76d2-115">**Sub-use cases**</span></span> | <span data-ttu-id="c76d2-116">**グループ**</span><span class="sxs-lookup"><span data-stu-id="c76d2-116">**Groups**</span></span> | <span data-ttu-id="c76d2-117">**デバイス プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="c76d2-117">**Device platforms**</span></span> | <span data-ttu-id="c76d2-118">**要件**</span><span class="sxs-lookup"><span data-stu-id="c76d2-118">**Requirements**</span></span> |
|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="c76d2-119">企業</span><span class="sxs-lookup"><span data-stu-id="c76d2-119">Corporate</span></span> | <span data-ttu-id="c76d2-120">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="c76d2-120">Information worker</span></span> | <span data-ttu-id="c76d2-121">人事、財務</span><span class="sxs-lookup"><span data-stu-id="c76d2-121">HR, Finance</span></span> | <span data-ttu-id="c76d2-122">iOS</span><span class="sxs-lookup"><span data-stu-id="c76d2-122">iOS</span></span> | <span data-ttu-id="c76d2-123">電子メールのセキュリティ保護、デバイスの設定、プロファイル、アプリ</span><span class="sxs-lookup"><span data-stu-id="c76d2-123">Secure e-mail, device settings, profiles, apps</span></span> |                                                          
| <span data-ttu-id="c76d2-124">企業</span><span class="sxs-lookup"><span data-stu-id="c76d2-124">Corporate</span></span> | <span data-ttu-id="c76d2-125">役員</span><span class="sxs-lookup"><span data-stu-id="c76d2-125">Executives</span></span> | <span data-ttu-id="c76d2-126">人事、財務</span><span class="sxs-lookup"><span data-stu-id="c76d2-126">HR, Finance</span></span> | <span data-ttu-id="c76d2-127">iOS</span><span class="sxs-lookup"><span data-stu-id="c76d2-127">iOS</span></span> | <span data-ttu-id="c76d2-128">電子メールのセキュリティ保護、デバイスの設定、プロファイル、アプリ</span><span class="sxs-lookup"><span data-stu-id="c76d2-128">Secure e-mail, device settings, profiles, apps</span></span> |                                                         
| <span data-ttu-id="c76d2-129">企業</span><span class="sxs-lookup"><span data-stu-id="c76d2-129">Corporate</span></span> | <span data-ttu-id="c76d2-130">キオスク</span><span class="sxs-lookup"><span data-stu-id="c76d2-130">Kiosk</span></span> | <span data-ttu-id="c76d2-131">小売</span><span class="sxs-lookup"><span data-stu-id="c76d2-131">Retail</span></span> | <span data-ttu-id="c76d2-132">Android</span><span class="sxs-lookup"><span data-stu-id="c76d2-132">Android</span></span> | <span data-ttu-id="c76d2-133">デバイスの設定、プロファイル、アプリ</span><span class="sxs-lookup"><span data-stu-id="c76d2-133">Device settings, profiles, apps</span></span> |
| <span data-ttu-id="c76d2-134">BYOD</span><span class="sxs-lookup"><span data-stu-id="c76d2-134">BYOD</span></span> | <span data-ttu-id="c76d2-135">インフォメーション ワーカー</span><span class="sxs-lookup"><span data-stu-id="c76d2-135">Information worker</span></span> | <span data-ttu-id="c76d2-136">マーケティング、営業</span><span class="sxs-lookup"><span data-stu-id="c76d2-136">Marketing, Sales</span></span> | <span data-ttu-id="c76d2-137">iOS</span><span class="sxs-lookup"><span data-stu-id="c76d2-137">iOS</span></span> | <span data-ttu-id="c76d2-138">電子メールのセキュリティ保護、デバイスの設定、プロファイル、アプリ</span><span class="sxs-lookup"><span data-stu-id="c76d2-138">Secure e-mail, device settings, profiles, apps</span></span> |                                                         
| <span data-ttu-id="c76d2-139">BYOD</span><span class="sxs-lookup"><span data-stu-id="c76d2-139">BYOD</span></span> | <span data-ttu-id="c76d2-140">役員</span><span class="sxs-lookup"><span data-stu-id="c76d2-140">Executives</span></span> | <span data-ttu-id="c76d2-141">マーケティング、営業</span><span class="sxs-lookup"><span data-stu-id="c76d2-141">Marketing, Sales</span></span> | <span data-ttu-id="c76d2-142">iOS</span><span class="sxs-lookup"><span data-stu-id="c76d2-142">iOS</span></span> | <span data-ttu-id="c76d2-143">電子メールのセキュリティ保護、デバイスの設定、プロファイル、アプリ</span><span class="sxs-lookup"><span data-stu-id="c76d2-143">Secure e-mail, device settings, profiles, apps</span></span> |

<span data-ttu-id="c76d2-144">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、お客様の組織のユース ケースとサブ ユース ケースの要件を入力できます。</span><span class="sxs-lookup"><span data-stu-id="c76d2-144">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to enter your organization’s use-case and sub-use-case requirements.</span></span>


## <a name="examples-of-requirements"></a><span data-ttu-id="c76d2-145">要件の例</span><span class="sxs-lookup"><span data-stu-id="c76d2-145">Examples of requirements</span></span>

<span data-ttu-id="c76d2-146">"要件" 列に使用できる追加の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c76d2-146">Here are a few more examples that can be used in the "Requirements" column:</span></span>

- <span data-ttu-id="c76d2-147">**電子メールのセキュリティ保護**</span><span class="sxs-lookup"><span data-stu-id="c76d2-147">**Secure e-mail**</span></span>
    - <span data-ttu-id="c76d2-148">Exchange Online / On-Premises の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="c76d2-148">Conditional access for Exchange Online / on-premises</span></span>
    - <span data-ttu-id="c76d2-149">Outlook アプリの保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="c76d2-149">Outlook app protection policies</span></span>

- <span data-ttu-id="c76d2-150">**デバイスの設定**</span><span class="sxs-lookup"><span data-stu-id="c76d2-150">**Device settings**</span></span>
    - <span data-ttu-id="c76d2-151">4 桁、6 桁の PIN 設定</span><span class="sxs-lookup"><span data-stu-id="c76d2-151">PIN setting with four, six characters</span></span>
    - <span data-ttu-id="c76d2-152">クラウド バックアップの制限</span><span class="sxs-lookup"><span data-stu-id="c76d2-152">Restrict cloud backup</span></span>

- <span data-ttu-id="c76d2-153">**プロファイル**</span><span class="sxs-lookup"><span data-stu-id="c76d2-153">**Profiles**</span></span>
    - <span data-ttu-id="c76d2-154">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c76d2-154">Wi-Fi</span></span>
    - <span data-ttu-id="c76d2-155">VPN</span><span class="sxs-lookup"><span data-stu-id="c76d2-155">VPN</span></span>
    - <span data-ttu-id="c76d2-156">電子メール (Windows 10 Mobile)</span><span class="sxs-lookup"><span data-stu-id="c76d2-156">Email (Windows 10 mobile)</span></span>

- <span data-ttu-id="c76d2-157">**アプリ**</span><span class="sxs-lookup"><span data-stu-id="c76d2-157">**Apps**</span></span>
    - <span data-ttu-id="c76d2-158">アプリの保護ポリシー付きの Office 365</span><span class="sxs-lookup"><span data-stu-id="c76d2-158">Office 365 with app protection policies</span></span>
    - <span data-ttu-id="c76d2-159">アプリの保護ポリシー付きの基幹業務 (LOB)</span><span class="sxs-lookup"><span data-stu-id="c76d2-159">Line of business (LOB) with app protection policies</span></span>

## <a name="next-steps"></a><span data-ttu-id="c76d2-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="c76d2-160">Next steps</span></span>

<span data-ttu-id="c76d2-161">次のセクションでは、[Intune ロールアウト計画を作成する方法](planning-guide-rollout-plan.md)についてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c76d2-161">The next section provides guidance on [how to develop an Intune rollout plan](planning-guide-rollout-plan.md).</span></span>
