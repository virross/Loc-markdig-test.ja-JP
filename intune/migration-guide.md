---
title: "Intune モバイル デバイス管理の移行ガイド"
description: "このガイドは、サードパーティの MDM プロバイダーからの Microsoft Intune への移行に関連したさまざまな詳細情報を説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: d86260872230bb0a9274fa302acac5caeaa682a7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="intune-migration-guide"></a><span data-ttu-id="ededc-103">Intune 移行ガイド</span><span class="sxs-lookup"><span data-stu-id="ededc-103">Intune migration guide</span></span>

![Intune MDM 移行ガイド図](./media/MDM-migration-guide-art.PNG)

<span data-ttu-id="ededc-105">Intune への移行を成功させるには、まず現在のモバイル デバイス管理 (MDM) 環境、ビジネスの目標、および技術面の要件を考慮した、しっかりした計画を立てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ededc-105">A successful migration to Intune starts with a solid plan that factors in your current mobile device management (MDM) environment, business goals, and technical requirements.</span></span> <span data-ttu-id="ededc-106">また、移行計画を支援し協力する関係者を確保することも重要です。</span><span class="sxs-lookup"><span data-stu-id="ededc-106">Additionally, you need to have the key stakeholders whose will support and collaborate with your migration plan.</span></span>

<span data-ttu-id="ededc-107">このガイドは、サードパーティの MDM プロバイダーからの Intune への移行に関連したさまざまな詳細情報を説明します。</span><span class="sxs-lookup"><span data-stu-id="ededc-107">This guide walks you through the various details involved in migrating from a third-party MDM provider to Intune.</span></span>

## <a name="whats-included-in-this-guide"></a><span data-ttu-id="ededc-108">このガイドに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="ededc-108">What’s included in this guide?</span></span>

<span data-ttu-id="ededc-109">このガイドは移行を 2 つのフェーズに分けます。各フェーズには、Intune MDM への移行プロセス全体を理解するうえで役立つタスク、戦略、および戦術的ガイダンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ededc-109">This guide breaks down the migration into two phases, both of which include tasks, strategies, and tactical guidance that will help you step through the end-to-end process of migrating to Intune MDM.</span></span>

-   [<span data-ttu-id="ededc-110">フェーズ 1: モバイル デバイス管理の Intune を準備する</span><span class="sxs-lookup"><span data-stu-id="ededc-110">Phase 1: Prepare Intune for mobile device management</span></span>](migration-guide-prepare.md)

    -   [<span data-ttu-id="ededc-111">MDM 移行要件を評価する</span><span class="sxs-lookup"><span data-stu-id="ededc-111">Assess your MDM migration requirements</span></span>](migration-guide-prepare.md#assess-mdm-requirements)

    -   [<span data-ttu-id="ededc-112">基本的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="ededc-112">Basic setup</span></span>](migration-guide-setup.md)

    -   [<span data-ttu-id="ededc-113">デバイスおよびアプリ管理のポリシー</span><span class="sxs-lookup"><span data-stu-id="ededc-113">Configure device and app management policies</span></span>](migration-guide-configure-policies.md)

    -   [<span data-ttu-id="ededc-114">アプリ保護ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="ededc-114">Configure app protection policies</span></span>](migration-guide-app-protection-policies.md)

    -   [<span data-ttu-id="ededc-115">特殊な移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ededc-115">Special migration considerations</span></span>](migration-guide-considerations.md)

-   [<span data-ttu-id="ededc-116">フェーズ 2: 移行のキャンペーン</span><span class="sxs-lookup"><span data-stu-id="ededc-116">Phase 2: Migration campaign</span></span>](migration-guide-campaign.md)

    -   [<span data-ttu-id="ededc-117">情報伝達計画</span><span class="sxs-lookup"><span data-stu-id="ededc-117">Communication plan</span></span>](migration-guide-communication-plan.md)

    -   [<span data-ttu-id="ededc-118">条件付きアクセスでエンド ユーザーの導入を推進する</span><span class="sxs-lookup"><span data-stu-id="ededc-118">Drive end-user adoption with conditional access</span></span>](migration-guide-drive-adoption.md)

    -   [<span data-ttu-id="ededc-119">標準的な移行サイクル</span><span class="sxs-lookup"><span data-stu-id="ededc-119">Typical migration cycle</span></span>](migration-guide-cycle.md)
        -   [<span data-ttu-id="ededc-120">移行の監視</span><span class="sxs-lookup"><span data-stu-id="ededc-120">Monitoring migration</span></span>](migration-guide-cycle.md#monitoring-migration)
        -   [<span data-ttu-id="ededc-121">移行後</span><span class="sxs-lookup"><span data-stu-id="ededc-121">Post migration</span></span>](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a><span data-ttu-id="ededc-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="ededc-122">Assumptions</span></span>

-   <span data-ttu-id="ededc-123">概念実証 (PoC) 環境で既に Intune を評価し、組織で MDM ソリューションとして使用することを決定している。</span><span class="sxs-lookup"><span data-stu-id="ededc-123">You've already evaluated Intune in a proof of concept (PoC) environment, and have decided to use it as the MDM solution in your organization.</span></span>

-   <span data-ttu-id="ededc-124">Intune とその機能について、既によく理解している。</span><span class="sxs-lookup"><span data-stu-id="ededc-124">You are already familiar with Intune and its features.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ededc-125">始める前に</span><span class="sxs-lookup"><span data-stu-id="ededc-125">Before you begin</span></span>

<span data-ttu-id="ededc-126">新しい Intune 展開は、以前の MDM 展開とは異なる可能性があることを認識することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ededc-126">It's important to recognize that your new Intune deployment might be different from your old MDM deployment.</span></span> <span data-ttu-id="ededc-127">従来の MDM サービスとは異なり、Intune では ID ドリブンのアクセス制御に重点を置いているため、組織のネットワーク境界外で使用されるモバイル デバイスから企業データへのアクセスを制御するネットワーク プロキシ アプライアンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="ededc-127">Unlike traditional MDM services, Intune centers on identity-driven access control, and so does not require a network proxy appliance to control access to corporate data from mobile devices outside the organization's network perimeter.</span></span> <span data-ttu-id="ededc-128">Microsoft は、密接に統合されたクラウド サービス スイートである "Enterprise Mobility + Security" を通じて、クラウド内のデータ サービスを保護するソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="ededc-128">Microsoft offers solutions to secure data services within the cloud itself through a suite of tightly integrated cloud services, collectively referred to as the Enterprise Client + Security offering.</span></span>

-   <span data-ttu-id="ededc-129">[Intune の一般的な使用方法](common-scenarios.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ededc-129">Review the [common ways to use Intune](common-scenarios.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ededc-130">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ededc-130">Next steps</span></span>

[<span data-ttu-id="ededc-131">フェーズ 1: モバイル デバイス管理の Intune を準備する</span><span class="sxs-lookup"><span data-stu-id="ededc-131">Phase 1: Prepare Intune for mobile device management</span></span>](migration-guide-prepare.md)
