---
title: Intune Mobile Threat Defense
description: "デバイスのリスクに基づいて、会社のリソースへのアクセスを保護します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08d87906-8158-4d5e-a49d-ad919efef3d1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f565ab0bca4fd2c283a4c8251f78c44ccd304065
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="intune-mobile-threat-defense-connectors"></a><span data-ttu-id="eb853-103">Intune Mobile Threat Defense コネクター</span><span class="sxs-lookup"><span data-stu-id="eb853-103">Intune Mobile Threat Defense connectors</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="eb853-104">Intune Mobile Threat Defense コネクターを使用すると、選択した Mobile Threat Defense ベンダーをコンプライアンス ポリシーと条件付きアクセス規則の情報ソースとして活用できます。</span><span class="sxs-lookup"><span data-stu-id="eb853-104">Intune Mobile Threat Defense connectors allow you to leverage your chosen Mobile Threat Defense vendor as a source of information for your compliance policies and conditional access rules.</span></span> <span data-ttu-id="eb853-105">これにより、IT 管理者が、具体的に危険にさらさモバイル デバイスから、Exchange、Sharepoint などの企業リソースに保護レイヤーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="eb853-105">This allows IT Administrators to add a layer of protection to their corporate resources such as Exchange and Sharepoint, specifically from compromised mobile devices.</span></span>

## <a name="what-problem-does-this-solve"></a><span data-ttu-id="eb853-106">どのような問題がこれにより解決されますか?</span><span class="sxs-lookup"><span data-stu-id="eb853-106">What problem does this solve?</span></span>

<span data-ttu-id="eb853-107">会社は物理的な脅威、アプリ ベースの脅威、ネットワーク ベースの脅威などの新種の脅威やオペレーティング システムの脆弱性から機密データを守る必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb853-107">Companies need to protect sensitive data from emerging threats including physical, app-based, and network-based threats, as well as operating system vulnerabilities.</span></span>
<span data-ttu-id="eb853-108">これまで、企業は PC の防御を積極的に行ってきましたが、モバイル デバイスは監視や保護のない状態が続いています。</span><span class="sxs-lookup"><span data-stu-id="eb853-108">Historically, companies have been proactive when protecting PCs from attack, while mobile devices go un-monitored and unprotected.</span></span> <span data-ttu-id="eb853-109">モバイル プラットフォームには、アプリの分離や検証済みコンシューマー アプリ ストアなどの防御手法が組み込まれていますが、依然として高度な攻撃を受けやすい状態にあります。</span><span class="sxs-lookup"><span data-stu-id="eb853-109">Mobile platforms have built-in protection such as app isolation and vetted consumer app stores, but these platforms remain vulnerable to sophisticated attacks.</span></span> <span data-ttu-id="eb853-110">現在、モバイル デバイスを仕事に利用し、機密情報にアクセスする社員が増えています。</span><span class="sxs-lookup"><span data-stu-id="eb853-110">Today, more employees use devices for work and need access to sensitive information.</span></span> <span data-ttu-id="eb853-111">増え続ける高度な攻撃からモバイル デバイスを守る必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb853-111">Devices need to be protected from increasingly sophisticated attacks.</span></span>

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a><span data-ttu-id="eb853-112">Intune Mobile Threat Defense コネクターのしくみ</span><span class="sxs-lookup"><span data-stu-id="eb853-112">How the Intune Mobile Threat Defense connectors work?</span></span>

<span data-ttu-id="eb853-113">このコネクターは、Intune と選択した Mobile Threat Defense ベンダーの間の通信チャネルを作成することで、会社のリソースを保護します。</span><span class="sxs-lookup"><span data-stu-id="eb853-113">The connector protects company resources by creating a channel of communication between Intune and your chosen Mobile Threat Defense vendor.</span></span> <span data-ttu-id="eb853-114">Intune Mobile Threat Defense パートナーは、直感的で簡単に展開できるモバイル デバイス向けアプリケーションを提供します。これらのアプリケーションは、脅威情報を積極的にスキャンして分析し、レポートや強制を目的として Intune と共有します。</span><span class="sxs-lookup"><span data-stu-id="eb853-114">Intune Mobile Threat Defense partners offer intuitive, easy to deploy applications for mobile devices which actively scan and analyze threat information to share with Intune, for either reporting or enforcement purposes.</span></span> <span data-ttu-id="eb853-115">たとえば、Mobile Threat Defense アプリが、電話またはネットワークが Man in the Middle 攻撃に対して脆弱なネットワークに接続されていることを Mobile Threat Defense ベンダーに報告した場合、この情報は共有されて適切なリスク レベル (低/中/高) に分類されます。その後、Intune で構成済みのリスク レベル許容度と比較されて、デバイスが侵害されたときに選択した特定のリソースへのアクセスを無効にする必要があるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="eb853-115">For example, if a connected Mobile Threat Defense app reports to the Mobile Threat Defense vendor that a phone on your network is currently connected to a network which is vulnerable to Man in the Middle attacks, this information is shared with and categorized to an appropriate risk level (low/medium/high) – which can then be compared with your configured risk level allowances in Intune to determine if access to certain resources of your choice should be revoked while the device is compromised.</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="eb853-116">サンプル事例</span><span class="sxs-lookup"><span data-stu-id="eb853-116">Sample scenarios</span></span>

<span data-ttu-id="eb853-117">Mobile Threat Defense ソリューションによってデバイスが感染したと見なされた場合</span><span class="sxs-lookup"><span data-stu-id="eb853-117">When a device is considered infected by the Mobile Threat Defense solution:</span></span>

![Mobile Threat Defense と感染しているデバイス](../media/mtp/MTD-image-1.png)

<span data-ttu-id="eb853-119">デバイスが修復されたときにアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="eb853-119">Access is granted when the device is remediated:</span></span>

![Mobile Threat Defense とアクセス付与](../media/mtp/MTD-image-2.png)

## <a name="mobile-threat-defense-partners"></a><span data-ttu-id="eb853-121">Mobile Threat Defense パートナー</span><span class="sxs-lookup"><span data-stu-id="eb853-121">Mobile Threat Defense partners</span></span>

<span data-ttu-id="eb853-122">デバイス、ネットワーク、アプリケーションのリスクに基づいて、会社のリソースへのアクセスを保護する方法について説明します。次のものを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb853-122">Learn how to protect access to company resource based on device, network, and application risk with:</span></span>

- [<span data-ttu-id="eb853-123">Lookout</span><span class="sxs-lookup"><span data-stu-id="eb853-123">Lookout</span></span>](/intune-classic/deploy-use/lookout-mobile-threat-defense-connector)
- [<span data-ttu-id="eb853-124">Skycure</span><span class="sxs-lookup"><span data-stu-id="eb853-124">Skycure</span></span>](/intune-classic/deploy-use/skycure-mobile-threat-defense-connector)
