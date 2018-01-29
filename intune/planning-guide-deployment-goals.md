---
title: "展開の目標、目的、課題を判別する"
description: "この記事は、Microsoft Intune のクラウド専用実装における展開の目標、目的、課題の判別に役立ちます。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93607152cfe007fb13e8695301debd87c9384394
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="determine-deployment-goals-objectives-and-challenges"></a><span data-ttu-id="5566e-103">展開の目標、目的、課題を判別する</span><span class="sxs-lookup"><span data-stu-id="5566e-103">Determine deployment goals, objectives, and challenges</span></span>

<span data-ttu-id="5566e-104">適切な展開を計画するには、潜在的な課題と共に、組織の展開の目標および目的を特定することから始まります。</span><span class="sxs-lookup"><span data-stu-id="5566e-104">Having a good deployment plan begins with first identifying your organization’s deployment goals and objectives, along with potential challenges.</span></span> <span data-ttu-id="5566e-105">それぞれの領域について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5566e-105">Let’s discuss each area in more detail.</span></span>

## <a name="deployment-goals"></a><span data-ttu-id="5566e-106">展開の目標</span><span class="sxs-lookup"><span data-stu-id="5566e-106">Deployment goals</span></span>

<span data-ttu-id="5566e-107">展開の目標は、組織に Intune を展開することで得られるであろう長期的な実績です。</span><span class="sxs-lookup"><span data-stu-id="5566e-107">Deployment goals are the long-term achievements you intend to gain by deploying Intune in your organization.</span></span> <span data-ttu-id="5566e-108">次の一覧では、そのような目標の例と、目標の説明およびビジネス価値を示します。</span><span class="sxs-lookup"><span data-stu-id="5566e-108">Listed below are some examples of such goals along with the description and business value for each.</span></span>

-   <span data-ttu-id="5566e-109">**Office 365 と統合し、Office モバイル アプリの使用をサポートする**</span><span class="sxs-lookup"><span data-stu-id="5566e-109">**Integrate with Office 365 and support the use of Office mobile apps**</span></span>

    -   <span data-ttu-id="5566e-110">**説明:** Office 365 との緊密な統合、およびアプリ保護付きの Office モバイル アプリの使用を提供します。</span><span class="sxs-lookup"><span data-stu-id="5566e-110">**Description:** Provide tight integration with Office 365 and the use of Office mobile apps with app protection.</span></span>

    -   <span data-ttu-id="5566e-111">**ビジネス価値:** ユーザーが使い慣れた好みのアプリの使用を許可して、セキュリティで保護し、ユーザー エクスペリエンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="5566e-111">**Business value:** Secure and improved user experience by allowing users to use apps they are familiar with and prefer.</span></span>

-   <span data-ttu-id="5566e-112">**モバイル デバイスで社内サービスへのアクセスを有効にする**</span><span class="sxs-lookup"><span data-stu-id="5566e-112">**Enable access to internal corporate services on mobile devices**</span></span>

    -   <span data-ttu-id="5566e-113">**説明:** 従業員が必要に応じてどこからでも、最も適切なデバイスを使用して、生産性を向上できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5566e-113">**Description:** Enable employees to be productive wherever they need to work from, and with whichever device is most appropriate for them.</span></span> <span data-ttu-id="5566e-114">このプロジェクトは、安全な方法でモバイルの生産性と企業データへのアクセスを可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-114">This project should look to enable mobile productivity and access to corporate data in a safe manner.</span></span>

    -   <span data-ttu-id="5566e-115">**ビジネス価値:** 従業員が必要な場所から機敏に作業でき、ビジネスの競争力を高め、満足感のある作業環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="5566e-115">**Business value:** Enabling employees to be agile and work from where they need allows the business to be more competitive and to provide a more rewarding working environment.</span></span>

-   <span data-ttu-id="5566e-116">**モバイル デバイスのデータ保護を提供する**</span><span class="sxs-lookup"><span data-stu-id="5566e-116">**Provide data protection on mobile devices**</span></span>

    -   <span data-ttu-id="5566e-117">**説明:** データがモバイル デバイスに保存されている場合、悪意による損失や偶発的な損失または共有から保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-117">**Description:** When data is stored on a mobile device, it should be protected from malicious and accidental loss or sharing.</span></span>

    -   <span data-ttu-id="5566e-118">**ビジネス価値:** データ保護では、確実に競争力を維持し、クライアントおよびクライアントのデータを最大限の努力を払って扱うことが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="5566e-118">**Business value:** Data protection is vital to ensure that we remain competitive, and that we treat our clients and their data with the utmost diligence.</span></span>

-   <span data-ttu-id="5566e-119">**コストの削減**</span><span class="sxs-lookup"><span data-stu-id="5566e-119">**Reduce costs**</span></span>

    -   <span data-ttu-id="5566e-120">**説明:** 可能な場合、プロジェクトでは展開コストおよび運用コストを削減します。</span><span class="sxs-lookup"><span data-stu-id="5566e-120">**Description:** When possible, the project reduces deployment and operating costs.</span></span>

    -    <span data-ttu-id="5566e-121">**ビジネス価値:** リソースを効率的に使用すると、ビジネスでの他の領域での投資、競争力の効率化、およびクライアントへの適切なサービスの提供を可能にします。</span><span class="sxs-lookup"><span data-stu-id="5566e-121">**Business value:** The efficient use of resources enables the business to invest in other areas, compete more effectively, and provide better service to clients.</span></span>

## <a name="deployment-objectives"></a><span data-ttu-id="5566e-122">展開の目的</span><span class="sxs-lookup"><span data-stu-id="5566e-122">Deployment objectives</span></span>

<span data-ttu-id="5566e-123">展開の目的は、組織が Intune 展開の目標を達成するために行う具体的な行動です。</span><span class="sxs-lookup"><span data-stu-id="5566e-123">Deployment objectives are the actions your organization can take to reach its Intune deployment goals.</span></span> <span data-ttu-id="5566e-124">次の一覧では、展開の目的の例と、その目的の達成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5566e-124">Below are listed some examples of deployment objectives, and how each would be accomplished.</span></span>

-   <span data-ttu-id="5566e-125">**デバイス管理ソリューションの数を減らす**</span><span class="sxs-lookup"><span data-stu-id="5566e-125">**Reduce the number of device management solutions**</span></span>

    -   <span data-ttu-id="5566e-126">**実装:** アプリとデバイスの企業データを保護するために、Microsoft Intune という単一のモバイル デバイス管理ソリューションに統合します。</span><span class="sxs-lookup"><span data-stu-id="5566e-126">**Implementation:** Consolidate to a single mobile device management solution: Microsoft Intune for corporate data protection of apps and devices.</span></span>

-   <span data-ttu-id="5566e-127">**セキュリティで保護された、Exchange および SharePoint Online へのアクセスを提供する**</span><span class="sxs-lookup"><span data-stu-id="5566e-127">**Provide secure access to Exchange and SharePoint Online**</span></span>

    -   <span data-ttu-id="5566e-128">**実装:** Exchange および SharePoint Online に条件付きアクセスを適用します。</span><span class="sxs-lookup"><span data-stu-id="5566e-128">**Implementation:** Apply conditional access for Exchange and SharePoint Online.</span></span>

-   <span data-ttu-id="5566e-129">**企業データがモバイル デバイスで社外サービスに格納または転送されないようにする**</span><span class="sxs-lookup"><span data-stu-id="5566e-129">**Prevent corporate data from being stored or forwarded to non-corporate services on the mobile device**</span></span>

    -   <span data-ttu-id="5566e-130">**実行:** Microsoft Office および LOB アプリに Intune アプリ保護ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="5566e-130">**Implementation:** Apply Intune app protection policies for Microsoft Office and line-of-business apps.</span></span>

-   <span data-ttu-id="5566e-131">**デバイスからの企業データのワイプ機能を提供する**</span><span class="sxs-lookup"><span data-stu-id="5566e-131">**Provide capability to wipe corporate data from the device**</span></span>

    -   <span data-ttu-id="5566e-132">**実装:** Intune にデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="5566e-132">**Implementation:** Enroll devices into Intune.</span></span> <span data-ttu-id="5566e-133">これにより、適切なタイミングで企業のデータやリソースをリモート ワイプできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5566e-133">This gives you the capability to perform a remote wipe of corporate data and resources when appropriate.</span></span>

## <a name="deployment-challenges"></a><span data-ttu-id="5566e-134">展開の課題</span><span class="sxs-lookup"><span data-stu-id="5566e-134">Deployment challenges</span></span>

<span data-ttu-id="5566e-135">展開の課題は、組織が最も関心を寄せる問題で、それにより展開に悪影響が及ぶ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-135">Deployment challenges are issues that are top of mind for an organization and that may have a negative impact on deployment.</span></span> <span data-ttu-id="5566e-136">課題は、以前のプロジェクトで発生した、回避すべき過去の問題に関連していることもあれば、現在の展開での取り組みに関する新しい問題に関連していることもあります。</span><span class="sxs-lookup"><span data-stu-id="5566e-136">Sometimes they are related to past issues from previous projects that you would like to avoid or new issues related to the current deployment effort.</span></span> <span data-ttu-id="5566e-137">次の一覧では、Intune 展開の課題の例と、可能性のある対策を示します。</span><span class="sxs-lookup"><span data-stu-id="5566e-137">Listed below are some examples of Intune deployment challenges along with potential mitigations.</span></span>

-   <span data-ttu-id="5566e-138">サポートの準備やエンド ユーザー エクスペリエンスは、最初のプロジェクト スコープには含まれません。</span><span class="sxs-lookup"><span data-stu-id="5566e-138">Support readiness and end-user experience are not included in an initial project scope.</span></span> <span data-ttu-id="5566e-139">このため、エンド ユーザーに採用されにくいといった問題やサポート組織の課題が生じています。</span><span class="sxs-lookup"><span data-stu-id="5566e-139">This leads to poor end-user adoption and challenges for your support organization.</span></span>

    -   <span data-ttu-id="5566e-140">**対策:** サポート トレーニングを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="5566e-140">**Mitigation:** Incorporate support training.</span></span> <span data-ttu-id="5566e-141">展開計画で定めた成功の指標を使用して、エンド ユーザー エクスペリエンスを検証します。</span><span class="sxs-lookup"><span data-stu-id="5566e-141">Validate the end-user experience with success metrics in your deployment plan.</span></span>

-   <span data-ttu-id="5566e-142">目標や成功の指標が明確に定義されていないため、成果が目に見えません。</span><span class="sxs-lookup"><span data-stu-id="5566e-142">Lack of clearly defined goals and success metrics leads to intangible results.</span></span> <span data-ttu-id="5566e-143">問題が発生した場合、組織の対応が後手に回る可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="5566e-143">It may also shift your organization into reactive mode when issues arise.</span></span>

    -   <span data-ttu-id="5566e-144">**対策:** プロジェクト スコープの早い段階で目標と成功の判断基準を定義し、それらのデータ ポイントを利用し、他のロールアウト フェーズを具体化します。</span><span class="sxs-lookup"><span data-stu-id="5566e-144">**Mitigation:** Define your goals and success metrics early in your project scope, and use these data points to flesh out your other rollout phases.</span></span> <span data-ttu-id="5566e-145">目標は SMART (Specific (具体的な)、Measurable (測定可能な)、Attainable (達成可能な)、Realistic (現実的な)、Timely (時宜にかなった)) ものになるように設定します。</span><span class="sxs-lookup"><span data-stu-id="5566e-145">Make sure goals are SMART (Specific, Measurable, Attainable, Realistic, and Timely).</span></span> <span data-ttu-id="5566e-146">ロールアウト計画が順調に進行するように各フェーズの目標に合わせて指標を設定します。</span><span class="sxs-lookup"><span data-stu-id="5566e-146">Plan to measure against your goals at each phase and to ensure your rollout project stays on track.</span></span>

-   <span data-ttu-id="5566e-147">組織の理解を得られるような明瞭な価値提案を作成し、その正当性を立証し、積極的に伝える努力を怠ると、</span><span class="sxs-lookup"><span data-stu-id="5566e-147">You neglect to create, validate, and aggressively share a clear value proposition that resonates for your organization.</span></span> <span data-ttu-id="5566e-148">多くの場合、導入が制限され、十分な投資収益率 (ROI) が得られません。</span><span class="sxs-lookup"><span data-stu-id="5566e-148">This often leads to limited adoption and a lack of return on investment (ROI).</span></span>

    -   <span data-ttu-id="5566e-149">**対策:** プロジェクトにあわてて取りかからず、目標と目的が明確に定義されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5566e-149">**Mitigation:** While you may be excited to jump into your project, ensure you have clearly-defined your goals and objectives.</span></span> <span data-ttu-id="5566e-150">新機能の認知やトレーニングにはこれらの目標や目的を取り入れ、Intune を組織が選択した理由をユーザーに理解してもらいます。</span><span class="sxs-lookup"><span data-stu-id="5566e-150">Include these in all awareness and training activities to help ensure users understand why your organization selected Intune.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5566e-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="5566e-151">Next steps</span></span>

<span data-ttu-id="5566e-152">これで、展開の目標、目的、および潜在的な課題を識別しました。次のセクション「[Intune ユース ケース シナリオの特定](planning-guide-scenarios.md)」に移動しましょう。</span><span class="sxs-lookup"><span data-stu-id="5566e-152">Now that you have identified your deployment goals, objectives, and potential challenges, let’s move to the next section: [Identify use case scenarios](planning-guide-scenarios.md).</span></span>
