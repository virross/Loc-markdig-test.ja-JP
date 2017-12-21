---
title: "Mobile Threat Defense と Intune"
titleSuffix: Azure portal
description: "デバイスのリスクに基づいて、会社のリソースへのアクセスを保護します"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16402b30895e61d9a4ff8393fd4d4c6efa061e9e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="mobile-threat-defense-integration-with-intune"></a><span data-ttu-id="14d1f-103">Mobile Threat Defense の Intune との統合</span><span class="sxs-lookup"><span data-stu-id="14d1f-103">Mobile Threat Defense integration with Intune</span></span>


<span data-ttu-id="14d1f-104">Intune Mobile Threat Defense コネクターを使用すると、選択した Mobile Threat Defense ベンダーをコンプライアンス ポリシーと条件付きアクセス規則の情報ソースとして活用できます。</span><span class="sxs-lookup"><span data-stu-id="14d1f-104">Intune Mobile Threat Defense connectors allow you to leverage your chosen Mobile Threat Defense vendor as a source of information for your compliance policies and conditional access rules.</span></span> <span data-ttu-id="14d1f-105">これにより、IT 管理者が、特に危険にさらされたモバイル デバイスから、Exchange、Sharepoint などの企業リソースに保護レイヤーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="14d1f-105">This allows IT administrators to add a layer of protection to their corporate resources such as Exchange and Sharepoint, specifically from compromised mobile devices.</span></span>

## <a name="what-problem-does-this-solve"></a><span data-ttu-id="14d1f-106">どのような問題がこれにより解決されますか?</span><span class="sxs-lookup"><span data-stu-id="14d1f-106">What problem does this solve?</span></span>

<span data-ttu-id="14d1f-107">会社は物理的な脅威、アプリ ベースの脅威、ネットワーク ベースの脅威などの新種の脅威やオペレーティング システムの脆弱性から機密データを守る必要があります。</span><span class="sxs-lookup"><span data-stu-id="14d1f-107">Companies need to protect sensitive data from emerging threats including physical, app-based, and network-based threats, as well as operating system vulnerabilities.</span></span>

<span data-ttu-id="14d1f-108">これまで、企業は PC の防御を積極的に行ってきましたが、モバイル デバイスは監視や保護のない状態が続いています。</span><span class="sxs-lookup"><span data-stu-id="14d1f-108">Historically, companies have been proactive when protecting PCs from attack, while mobile devices go un-monitored and unprotected.</span></span> <span data-ttu-id="14d1f-109">モバイル プラットフォームには、アプリの分離や検証済みコンシューマー アプリ ストアなどの防御手法が組み込まれていますが、依然として高度な攻撃を受けやすい状態にあります。</span><span class="sxs-lookup"><span data-stu-id="14d1f-109">Mobile platforms have built-in protection such as app isolation and vetted consumer app stores, but these platforms remain vulnerable to sophisticated attacks.</span></span> <span data-ttu-id="14d1f-110">現在、モバイル デバイスを仕事に利用し、機密情報にアクセスする社員が増えています。</span><span class="sxs-lookup"><span data-stu-id="14d1f-110">Today, more employees use devices for work and need access to sensitive information.</span></span> <span data-ttu-id="14d1f-111">増え続ける高度な攻撃からモバイル デバイスを守る必要があります。</span><span class="sxs-lookup"><span data-stu-id="14d1f-111">Devices need to be protected from increasingly sophisticated attacks.</span></span>

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a><span data-ttu-id="14d1f-112">Intune Mobile Threat Defense コネクターのしくみ</span><span class="sxs-lookup"><span data-stu-id="14d1f-112">How the Intune Mobile Threat Defense connectors work?</span></span>

<span data-ttu-id="14d1f-113">このコネクターは、Intune と選択した Mobile Threat Defense ベンダーの間の通信チャネルを作成することで、会社のリソースを保護します。</span><span class="sxs-lookup"><span data-stu-id="14d1f-113">The connector protects company resources by creating a channel of communication between Intune and your chosen Mobile Threat Defense vendor.</span></span> <span data-ttu-id="14d1f-114">Intune Mobile Threat Defense パートナーは、直感的で簡単に展開できるモバイル デバイス向けアプリケーションを提供します。これらのアプリケーションは、脅威情報を積極的にスキャンして分析し、レポートや強制を目的として Intune と共有します。</span><span class="sxs-lookup"><span data-stu-id="14d1f-114">Intune Mobile Threat Defense partners offer intuitive, easy to deploy applications for mobile devices which actively scan and analyze threat information to share with Intune, for either reporting or enforcement purposes.</span></span> 

<span data-ttu-id="14d1f-115">たとえば、Mobile Threat Defense アプリが、電話またはネットワークが Man in the Middle 攻撃に対して脆弱なネットワークに接続されていることを Mobile Threat Defense ベンダーに報告した場合、この情報は共有されて適切なリスク レベル (低/中/高) に分類されます。その後、Intune で構成済みのリスク レベル許容度と比較されて、デバイスが侵害されたときに選択した特定のリソースへのアクセスを無効にする必要があるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="14d1f-115">For example, if a connected Mobile Threat Defense app reports to the Mobile Threat Defense vendor that a phone on your network is currently connected to a network which is vulnerable to Man in the Middle attacks, this information is shared with and categorized to an appropriate risk level (low/medium/high) – which can then be compared with your configured risk level allowances in Intune to determine if access to certain resources of your choice should be revoked while the device is compromised.</span></span>

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a><span data-ttu-id="14d1f-116">Intune は Mobile Threat Defense のためにどのようなデータを収集しますか?</span><span class="sxs-lookup"><span data-stu-id="14d1f-116">What data does Intune collect for Mobile Threat Defense?</span></span>

<span data-ttu-id="14d1f-117">Intune は個人のデバイスと会社所有のデバイスの両方からアプリ インベントリ情報を収集し、Lookout for Work など、MTD (Mobile Thread Defense) プロバイダーが取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="14d1f-117">Intune collects app inventory information from both personal and corporate-owned devices and makes it available for Mobile Thread Defense (MTD) providers to fetch, such as Lookout for Work.</span></span> <span data-ttu-id="14d1f-118">iOS 11 以降のデバイスを所有するユーザーからアプリ インベントリを収集できます。</span><span class="sxs-lookup"><span data-stu-id="14d1f-118">You can collect an app inventory from the users of iOS 11+ devices.</span></span>

<span data-ttu-id="14d1f-119">**アプリ インベントリ**</span><span class="sxs-lookup"><span data-stu-id="14d1f-119">**App inventory**</span></span>  
<span data-ttu-id="14d1f-120">iOS 11 以降を内蔵した会社所有デバイスと個人所有デバイスの両方からのインベントリが MTD サービス プロバイダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="14d1f-120">Inventories from both corporate-owned iOS 11+ and personally owned devices are sent to your MTD service provider.</span></span> <span data-ttu-id="14d1f-121">アプリ インベントリのデータ:</span><span class="sxs-lookup"><span data-stu-id="14d1f-121">Data in the app inventory includes:</span></span>

 - <span data-ttu-id="14d1f-122">アプリ ID</span><span class="sxs-lookup"><span data-stu-id="14d1f-122">App ID</span></span>
 - <span data-ttu-id="14d1f-123">アプリ バージョン</span><span class="sxs-lookup"><span data-stu-id="14d1f-123">App Version</span></span>
 - <span data-ttu-id="14d1f-124">アプリ バージョン (短い形式)</span><span class="sxs-lookup"><span data-stu-id="14d1f-124">App Short Version</span></span>
 - <span data-ttu-id="14d1f-125">アプリ名</span><span class="sxs-lookup"><span data-stu-id="14d1f-125">App Name</span></span>
 - <span data-ttu-id="14d1f-126">アプリ バンドル サイズ</span><span class="sxs-lookup"><span data-stu-id="14d1f-126">App Bundle Size</span></span>
 - <span data-ttu-id="14d1f-127">アプリの動的サイズ</span><span class="sxs-lookup"><span data-stu-id="14d1f-127">App Dynamic Size</span></span>
 - <span data-ttu-id="14d1f-128">アプリの有効性が確認されているかどうか</span><span class="sxs-lookup"><span data-stu-id="14d1f-128">App is validated or not</span></span>
 - <span data-ttu-id="14d1f-129">アプリが管理されているかどうか</span><span class="sxs-lookup"><span data-stu-id="14d1f-129">App is managed or not</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="14d1f-130">サンプル事例</span><span class="sxs-lookup"><span data-stu-id="14d1f-130">Sample scenarios</span></span>

<span data-ttu-id="14d1f-131">Mobile Threat Defense ソリューションによってデバイスが感染したと見なされた場合</span><span class="sxs-lookup"><span data-stu-id="14d1f-131">When a device is considered infected by the Mobile Threat Defense solution:</span></span>

![Mobile Threat Defense と感染しているデバイス](./media/MTD-image-1.png)

<span data-ttu-id="14d1f-133">デバイスが修復されたときにアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="14d1f-133">Access is granted when the device is remediated:</span></span>

![Mobile Threat Defense とアクセス付与](./media/MTD-image-2.png)

> [!NOTE] 
> <span data-ttu-id="14d1f-135">Intune で複数の Mobile Threat Defense ベンダーを使用することは、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="14d1f-135">Using multiple Mobile Threat Defense vendors with Intune is not supported.</span></span> <span data-ttu-id="14d1f-136">複数の MTD ツールが有効になると、すべての MTD アプリがインストールされ、脅威を検出するためにデバイスにまたがるスキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="14d1f-136">Having multiple MTD tools enabled will force all MTD apps to be installed and scan across devices for threats.</span></span>

## <a name="mobile-threat-defense-partners"></a><span data-ttu-id="14d1f-137">Mobile Threat Defense パートナー</span><span class="sxs-lookup"><span data-stu-id="14d1f-137">Mobile Threat Defense partners</span></span>

<span data-ttu-id="14d1f-138">デバイス、ネットワーク、アプリケーションのリスクに基づいて、会社のリソースへのアクセスを保護する方法について説明します。次のものを使用します。</span><span class="sxs-lookup"><span data-stu-id="14d1f-138">Learn how to protect access to company resource based on device, network, and application risk with:</span></span>

- [<span data-ttu-id="14d1f-139">Lookout</span><span class="sxs-lookup"><span data-stu-id="14d1f-139">Lookout</span></span>](lookout-mobile-threat-defense-connector.md)
- [<span data-ttu-id="14d1f-140">Skycure</span><span class="sxs-lookup"><span data-stu-id="14d1f-140">Skycure</span></span>](skycure-mobile-threat-defense-connector.md)
- [<span data-ttu-id="14d1f-141">Check Point SandBlast Mobile</span><span class="sxs-lookup"><span data-stu-id="14d1f-141">Check Point SandBlast Mobile</span></span>](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [<span data-ttu-id="14d1f-142">Zimperium</span><span class="sxs-lookup"><span data-stu-id="14d1f-142">Zimperium</span></span>](zimperium-mobile-threat-defense-connector.md)
