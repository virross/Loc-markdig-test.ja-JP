---
title: "モバイル デバイス管理のために Intune を準備する"
description: "Intune に移行する前に、ビジネス要件と技術的な要件を評価します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 2c32a5cc45714b929535e0af0f0f664b0d8bad41
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a><span data-ttu-id="db429-103">フェーズ 1: モバイル デバイス管理 (MDM) に Intune を準備する</span><span class="sxs-lookup"><span data-stu-id="db429-103">Phase 1: Prepare Intune for mobile device management (MDM)</span></span>

<span data-ttu-id="db429-104">Intune の設定の詳細について説明する前に、組織のモバイル デバイス管理の要件を確認しておきましょう。</span><span class="sxs-lookup"><span data-stu-id="db429-104">Before diving into the details of setting up Intune, let’s review the mobile device management requirements of your organization.</span></span> <span data-ttu-id="db429-105">現在の MDM プロバイダーでアクティブなユーザーのレポートを実行して重要なユーザー グループを識別すると役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="db429-105">It might be helpful to run reports of active users in your current MDM provider to identify the critical user groups.</span></span> <span data-ttu-id="db429-106">その後、「[MDM 要件を評価する](migration-guide-prepare.md#assess-mdm-requirements)」セクションの質問に答えることができます。</span><span class="sxs-lookup"><span data-stu-id="db429-106">Then you can begin addressing the questions in the [Assess MDM requirements ](migration-guide-prepare.md#assess-mdm-requirements) section.</span></span>

## <a name="assess-mdm-requirements"></a><span data-ttu-id="db429-107">MDM 要件を評価する</span><span class="sxs-lookup"><span data-stu-id="db429-107">Assess MDM requirements</span></span>

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a><span data-ttu-id="db429-108">管理が必要なデバイスの種類について</span><span class="sxs-lookup"><span data-stu-id="db429-108">What kinds of devices do you need to manage?</span></span>

-   <span data-ttu-id="db429-109">どの[プラットフォーム](supported-devices-browsers.md)をサポートする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="db429-109">Which [platforms](supported-devices-browsers.md) do you need to support?</span></span>

-   <span data-ttu-id="db429-110">サポートする必要があるのは、企業所有デバイスですか個人のデバイスですか。</span><span class="sxs-lookup"><span data-stu-id="db429-110">Are the devices you need to support corporate-owned or personal devices?</span></span>

-   <span data-ttu-id="db429-111">どのような種類の接続を使用しますか。</span><span class="sxs-lookup"><span data-stu-id="db429-111">What kind of connectivity do you use?</span></span> <span data-ttu-id="db429-112">Wi-Fi、移動体通信、VPN ですか。</span><span class="sxs-lookup"><span data-stu-id="db429-112">Wi-Fi, cellular, VPN?</span></span>

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a><span data-ttu-id="db429-113">管理対象デバイスでユーザーが行う作業</span><span class="sxs-lookup"><span data-stu-id="db429-113">What do your users need to do on managed devices?</span></span>

-   <span data-ttu-id="db429-114">エンド ユーザーにアプリをプロビジョニングする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="db429-114">Do you need to provision apps to your end-users?</span></span>

-   <span data-ttu-id="db429-115">カスタムの基幹業務アプリを使用しますか。</span><span class="sxs-lookup"><span data-stu-id="db429-115">Do you use custom line-of-business apps?</span></span> <span data-ttu-id="db429-116">それともパブリックなストア アプリのみ必要ですか。</span><span class="sxs-lookup"><span data-stu-id="db429-116">Or do you only need public store apps?</span></span>

-   <span data-ttu-id="db429-117">電子メール アカウントをプロビジョニングする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="db429-117">Do you need to provision email accounts?</span></span>

### <a name="what-kinds-of-users"></a><span data-ttu-id="db429-118">ユーザーの種類について</span><span class="sxs-lookup"><span data-stu-id="db429-118">What kinds of users?</span></span>

-   <span data-ttu-id="db429-119">1 つのデバイスを使用するユーザー数は何人ですか。</span><span class="sxs-lookup"><span data-stu-id="db429-119">How many users will use a single device?</span></span>

-   <span data-ttu-id="db429-120">どのような使用条件が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="db429-120">What terms of use do you need?</span></span>

    -   <span data-ttu-id="db429-121">これについては早い段階で法務部門が関与するようにします。</span><span class="sxs-lookup"><span data-stu-id="db429-121">Make sure to involve your legal department early in this.</span></span>
    -   <span data-ttu-id="db429-122">どのようなローカライズが必要ですか。</span><span class="sxs-lookup"><span data-stu-id="db429-122">What localization is required?</span></span>

-   <span data-ttu-id="db429-123">一般的に、ユーザーは技術と IT についてよく理解していますか。</span><span class="sxs-lookup"><span data-stu-id="db429-123">Are the users familiar with technology and IT in general?</span></span>

### <a name="what-is-your-device-security-policy"></a><span data-ttu-id="db429-124">デバイスのセキュリティ ポリシーについて</span><span class="sxs-lookup"><span data-stu-id="db429-124">What is your device security policy?</span></span>

- <span data-ttu-id="db429-125">デバイス レベルの暗号化が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="db429-125">Do you need device-level encryption?</span></span>

- <span data-ttu-id="db429-126">現在のデバイスのパスコード/PIN コードはどれくらいの長さですか。</span><span class="sxs-lookup"><span data-stu-id="db429-126">What are your current device passcode/pin code lengths?</span></span>

- <span data-ttu-id="db429-127">デバイスの機能を無効にしたり、特定のデバイスの動作を制限する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="db429-127">Do you need to disable device features, or restrict certain device behaviors?</span></span> <span data-ttu-id="db429-128">デバイス構成プロファイルを使用して、プラットフォーム固有のさまざまな設定を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="db429-128">You can control a variety of platform-specific settings with device configuration profiles, for example:</span></span>
    - <span data-ttu-id="db429-129">カメラの無効化</span><span class="sxs-lookup"><span data-stu-id="db429-129">Disable camera</span></span>
    - <span data-ttu-id="db429-130">単一アプリ モードにロック</span><span class="sxs-lookup"><span data-stu-id="db429-130">Lock to single-app mode</span></span><br/>

- <span data-ttu-id="db429-131">どのような種類の認証をサポートする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="db429-131">What kinds of authentication must you support?</span></span> <span data-ttu-id="db429-132">証明書ベースの認証が必要な場合、どのような種類の証明書をプロビジョニングする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="db429-132">If you need certificate-based authentication, what kinds of certificates must be provisioned?</span></span>
  - <span data-ttu-id="db429-133">Intune では、リソース アクセス プロファイルを使用して、登録されたデバイスに証明書をプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="db429-133">Intune can provision certificates with resource access profiles for enrolled devices.</span></span>
  -   <span data-ttu-id="db429-134">どのような種類の公開キー基盤 (PKI) インフラをサポートする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="db429-134">What kind of Public Key Infrastructure (PKI) infra do you need to support?</span></span>
  <br></br>
- <span data-ttu-id="db429-135">デバイスまたはアプリケーション レベルで、仮想プライベート ネットワーク (VPN) をサポートする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="db429-135">Do you need to support Virtual Private Network (VPN) at the device or app level?</span></span>

  -   <span data-ttu-id="db429-136">Intune では、サードパーティ VPN プロバイダー向けの VPN 構成をプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="db429-136">Intune can provision VPN configurations for third-party VPN providers.</span></span>
  <br/><br/>
- <span data-ttu-id="db429-137">ダウンタイムを回避するために、特定の要件に対して一時的な例外を設定できますか。</span><span class="sxs-lookup"><span data-stu-id="db429-137">Can temporary exceptions be made for certain requirements to avoid downtime?</span></span> <span data-ttu-id="db429-138">それともアクセスが許可されたデバイスは、常にすべてのセキュリティ要件を遵守する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="db429-138">Or must devices with access always comply with all security requirements?</span></span>

## <a name="next-steps"></a><span data-ttu-id="db429-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="db429-139">Next steps</span></span>
<span data-ttu-id="db429-140">さまざまな業界セクターの[ケース スタディ](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune)を参照して、モバイル デバイス管理の要件をどのように評価したかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="db429-140">Read these [case studies](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) from different industry sectors to see how organizations assessed their requirements for mobile device management.</span></span>

<span data-ttu-id="db429-141">[Intune の基本的なセットアップ](migration-guide-setup.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="db429-141">Review the [basic Intune setup](migration-guide-setup.md).</span></span>
