---
title: "Intune のテストと検証"
description: "環境内のクラウド専用 Intune ソリューションをテストおよび検証するときに考慮する必要のある詳細について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.openlocfilehash: f10b4b0e7c48e921eb92392edf95bfcfaa83db9f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="intune-testing-and-validation"></a><span data-ttu-id="44755-103">Intune のテストと検証</span><span class="sxs-lookup"><span data-stu-id="44755-103">Intune testing and validation</span></span>

<span data-ttu-id="44755-104">テスト フェーズは、実装フェーズの途中と後に発生します。</span><span class="sxs-lookup"><span data-stu-id="44755-104">The testing phase occurs both during and after the implementation phase.</span></span> <span data-ttu-id="44755-105">前に特定したすべての必要な IT (管理者) シナリオとエンド ユーザー (ユース ケース) シナリオをテストするには、テスト用のアカウント、グループ、デバイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="44755-105">You need test accounts, groups, and devices for testing all required IT (admin) and end user (use case) scenarios you have previously identified.</span></span>

<span data-ttu-id="44755-106">サポート ドキュメントが作成され、IT サポートやヘルプデスクのスタッフが快適に製品をサポートできるように、IT サポート/ヘルプデスクのスタッフをテスト段階に組み入れることが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="44755-106">We recommend that you incorporate your IT support and helpdesk staff in the testing phase so that support documentation is created, and the IT support and helpdesk staff become comfortable supporting the product.</span></span> <span data-ttu-id="44755-107">部品やシナリオがユース ケースに基づいて機能しない場合、必要な変更を記録し、変更が行われた理由を追加してください。</span><span class="sxs-lookup"><span data-stu-id="44755-107">If a component or scenario does not function based on the use cases, make sure to document the necessary changes, and include the reason a change was made.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="44755-108">始める前に</span><span class="sxs-lookup"><span data-stu-id="44755-108">Before you begin</span></span>

<span data-ttu-id="44755-109">次の内容を文書化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44755-109">We recommend that you document the following:</span></span>

-   <span data-ttu-id="44755-110">**テスト条件:** 測定水準とするベンチマークを特定します。</span><span class="sxs-lookup"><span data-stu-id="44755-110">**Test criteria:** Identify the benchmarks to be measured against.</span></span>

-   <span data-ttu-id="44755-111">**設計部品:** 1 つ以上のテスト条件に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44755-111">**Design components:** Must exist in at least one testing criteria.</span></span>

<span data-ttu-id="44755-112">ある設計部品が、要件またはシナリオに合わせて調整される 1 つ以上のテスト条件に存在しない場合、その設計部品が必要かどうかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="44755-112">If a design component does not exist in at least one test criteria that aligns to a requirement or scenario, consider whether the design component is required or not.</span></span> <span data-ttu-id="44755-113">また、次の項目を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44755-113">In addition, make sure to have the following items:</span></span>

-   <span data-ttu-id="44755-114">**アカウント:** あらゆるユース ケース シナリオをテストするために EMS や Office 365 にライセンス供与されているテスト アカウント。</span><span class="sxs-lookup"><span data-stu-id="44755-114">**Accounts:** Test accounts that are licensed for EMS and Office 365 to test all use-case scenarios.</span></span>

-   <span data-ttu-id="44755-115">**デバイス:** ワイプまたは工場出荷時の既定値へのリセットが可能なテスト デバイス。</span><span class="sxs-lookup"><span data-stu-id="44755-115">**Devices:** Test devices that can be wiped or reset to factory defaults.</span></span>

-   <span data-ttu-id="44755-116">**統合コンポーネント:** あらゆる統合コンポーネント (Certificate Connector、ホスト型 Exchange 用 Intune Service to Service Connector、Intune On-Premises Exchange Connector) を必要に応じてインストールし、構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44755-116">**Integration components:** All integration components (certificate connector, Intune service-to-service connector for hosted Exchange, and Intune on-premises Exchange connector) should be installed and configured if needed.</span></span>

<span data-ttu-id="44755-117">予想外の問題に対処するために、設計を変更しなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="44755-117">You may need design changes to accommodate unforeseen difficulties.</span></span> <span data-ttu-id="44755-118">また、設計変更はすべて、その理由と共に完全に記録してください。</span><span class="sxs-lookup"><span data-stu-id="44755-118">In addition, all design changes should be fully documented with the reason for each change.</span></span> <span data-ttu-id="44755-119">たとえば、次のような変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="44755-119">Here's an example to illustrate what a change could be:</span></span>

<blockquote><span data-ttu-id="44755-120">Network Device Enrollment Service (NDES) の要件が満たされないことに気付きましたが、VPN プロファイルと Wi-Fi プロファイルをルート CA で構成すれば、NDES を実装しなくても同じ要件を満たせることを知ります。</span><span class="sxs-lookup"><span data-stu-id="44755-120">You realize that you don’t meet the requirements of Network Device Enrollment Service (NDES), and you also learn that the VPN and Wi-Fi profiles can be configured with a root CA satisfying the same requirements without an NDES implementation.</span></span></blockquote>

<span data-ttu-id="44755-121">テストや検証のプロセスで、技術的な指南や特別なトラブルシューティングが必要な問題に遭遇することがあります。</span><span class="sxs-lookup"><span data-stu-id="44755-121">You might experience challenges or issues that require technical guidance or specialized troubleshooting during the testing and validation process.</span></span> <span data-ttu-id="44755-122">Microsoft サポート チャンネルのサポートを利用することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="44755-122">We recommend that you seek assistance through the Microsoft support channels.</span></span>

-   [<span data-ttu-id="44755-123">Intune サポートの利用方法の詳細</span><span class="sxs-lookup"><span data-stu-id="44755-123">Learn how to get Intune support</span></span>](get-support.md)

-   [<span data-ttu-id="44755-124">Microsoft Intune のサポートの電話番号</span><span class="sxs-lookup"><span data-stu-id="44755-124">Contact assisted phone support for Microsoft Intune</span></span>](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a><span data-ttu-id="44755-125">機能検証テスト</span><span class="sxs-lookup"><span data-stu-id="44755-125">Functional validation testing</span></span>

<span data-ttu-id="44755-126">機能検証では、各要素と構成をテストし、それが適切に動作していることを確認する作業が行われます。</span><span class="sxs-lookup"><span data-stu-id="44755-126">Functional validation consists of testing each component and configuration to determine if it is working correctly.</span></span> <span data-ttu-id="44755-127">検証テストの例が下の表にあります。</span><span class="sxs-lookup"><span data-stu-id="44755-127">An example of validation testing is in the table below.</span></span>

![セクション 9 表 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a><span data-ttu-id="44755-129">ユース ケース検証テスト</span><span class="sxs-lookup"><span data-stu-id="44755-129">Use-case validation testing</span></span>

<span data-ttu-id="44755-130">ユース ケース検証テストを実行し、シナリオが完全であり、機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="44755-130">Perform use-case validation testing to verify the scenarios are complete and functional.</span></span> <span data-ttu-id="44755-131">ユース ケース シナリオには 2 つの種類があります。IT 管理者とエンド ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="44755-131">There are two types of use-case scenarios: IT admin and end user.</span></span>

### <a name="it-admin"></a><span data-ttu-id="44755-132">IT 管理者</span><span class="sxs-lookup"><span data-stu-id="44755-132">IT admin</span></span>

<span data-ttu-id="44755-133">IT 管理者の検証テストを実行し、あるデバイスまたはユーザーに対して実行した管理アクションが正しく動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="44755-133">Perform IT admin validation testing to validate that administrative actions performed on a device or user function correctly.</span></span> <span data-ttu-id="44755-134">下は、IT 管理者のエンドツーエンド検証シナリオの例です。</span><span class="sxs-lookup"><span data-stu-id="44755-134">Below is an example of an IT admin end-to-end validation scenario.</span></span>

![セクション 9 表 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a><span data-ttu-id="44755-136">エンド ユーザー</span><span class="sxs-lookup"><span data-stu-id="44755-136">End user</span></span>

<span data-ttu-id="44755-137">エンド ユーザー検証テストを実行し、エンド ユーザー側の操作性が予想どおりであり、あらゆるユーザー コミュニケーションで正しく表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="44755-137">Perform end-user validation testing to validate that the end-user experience is as expected and presented correctly in all user communications.</span></span> <span data-ttu-id="44755-138">エンド ユーザー エクスペリエンスが正しいことを検証することが重要です。</span><span class="sxs-lookup"><span data-stu-id="44755-138">It is important to validate that the end-user experience is correct.</span></span> <span data-ttu-id="44755-139">検証に失敗した場合、普及率が低下し、ヘルプデスクへの問い合わせが増える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="44755-139">If you fail to validate, it can lead to lower adoption rates and higher volumes of helpdesk calls.</span></span>

![セクション 9 表 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a><span data-ttu-id="44755-141">次のステップ</span><span class="sxs-lookup"><span data-stu-id="44755-141">Next steps</span></span>

<span data-ttu-id="44755-142">Intune の動作とユース ケース シナリオをテストし、確認しました。これで [Intune 運用のロールアウト](planning-guide-rollout-plan.md)に移ることができます。</span><span class="sxs-lookup"><span data-stu-id="44755-142">Now that you have tested and validated your Intune functional and use-case scenarios, you're ready for your [Intune production rollout](planning-guide-rollout-plan.md).</span></span>

<span data-ttu-id="44755-143">他の計画テンプレートと情報については、[追加リソース](planning-guide-resources.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44755-143">See [additional resources](planning-guide-resources.md) for more planning templates and information.</span></span>
