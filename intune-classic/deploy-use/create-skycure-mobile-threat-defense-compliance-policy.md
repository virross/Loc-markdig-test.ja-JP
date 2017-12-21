---
title: "Skycure Mobile Threat Defense コンプライアンス ポリシーを作成する"
description: "Intune クラシック ポータルで Skycure Mobile Threat Defense コンプライアンス ポリシーを作成します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4b63f98d914309c2101baf1992c72a562c33cfb4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a><span data-ttu-id="3c297-103">Skycure Mobile Threat Defense コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3c297-103">Create Skycure Mobile Threat Defense compliance policy</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="3c297-104">Intune と Skycure Mobile Threat Defense を使用することで、モバイル デバイスの脅威を検出し、デバイスのリスクを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="3c297-104">Intune with Skycure Mobile Threat Defense lets you detect threats on mobile devices and assess risk on those devices.</span></span> <span data-ttu-id="3c297-105">リスクを評価する Intune コンプライアンス ポリシー ルールを作成すれば、デバイスがポリシーに準拠しているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="3c297-105">You can create an Intune compliance policy rule that assesses risk to determine if the device is compliant.</span></span> <span data-ttu-id="3c297-106">条件付きアクセス ポリシーを使用すれば、デバイスのコンプライアンスに基づいて、サービスへのアクセスを禁止できます。</span><span class="sxs-lookup"><span data-stu-id="3c297-106">You can then use conditional access policy to block access to services based on device compliance.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3c297-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="3c297-107">Before you begin</span></span>

<span data-ttu-id="3c297-108">Skycure デバイス脅威保護を含むコンプライアンス ポリシーに関する前提条件:</span><span class="sxs-lookup"><span data-stu-id="3c297-108">Prerequisites for compliance policy with Skycure device threat protection:</span></span>

-   [<span data-ttu-id="3c297-109">Skycure と Intune の統合をセットアップする</span><span class="sxs-lookup"><span data-stu-id="3c297-109">Set up Skycure integration with Intune</span></span>](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [<span data-ttu-id="3c297-110">Intune で Skycure の接続を有効にする</span><span class="sxs-lookup"><span data-stu-id="3c297-110">Enable the Skycure connection in Intune</span></span>](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

<span data-ttu-id="3c297-111">Skycure Mobile Threat Defense をセットアップするときに、Skycure コンソールで、さまざまな脅威を高、中、低として分類するポリシーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="3c297-111">As part of the Skycure Mobile Threat Defense setup, in the Skycure console, you created a policy that classifies various threats as high, medium and low.</span></span> <span data-ttu-id="3c297-112">Intune コンプライアンス ポリシーでは、許容される最大脅威レベルを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c297-112">You now need to set the maximum allowed threat level in the Intune compliance policy.</span></span>

## <a name="to-create-skycure-compliance-policy"></a><span data-ttu-id="3c297-113">Skycure コンプライアンス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="3c297-113">To create Skycure compliance policy</span></span>

1.  <span data-ttu-id="3c297-114">[Intune クラシック ポータル](https://manage.microsoft.com/)に進み、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3c297-114">Go to the [Intune classic portal](https://manage.microsoft.com/) then enter your credentials.</span></span>

2.  <span data-ttu-id="3c297-115">**[ポリシー]** &gt; **[コンプライアンス ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3c297-115">Choose **Policy** &gt; **Compliance Policies**.</span></span> <span data-ttu-id="3c297-116">既存のコンプライアンス ポリシーを使用することも、新たに作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c297-116">You can either use an existing compliance policy or create a new one.</span></span>

3.  <span data-ttu-id="3c297-117">**[追加]** &gt; **[デバイスのヘルス]** の順に選択し、**[デバイス脅威保護]** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3c297-117">Choose **Add** &gt; **Device Health**, then enable **Device Threat Protection**.</span></span>

4.  <span data-ttu-id="3c297-118">**[許容される驚異の最大レベル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c297-118">Select the **Maximum allowed threat level**:</span></span>

    <span data-ttu-id="3c297-119">a.</span><span class="sxs-lookup"><span data-stu-id="3c297-119">a.</span></span>  <span data-ttu-id="3c297-120">**[なし (セキュリティ保護)]**: これはセキュリティ上最も安全です。</span><span class="sxs-lookup"><span data-stu-id="3c297-120">**None (Secured)**: This is the most secure.</span></span> <span data-ttu-id="3c297-121">デバイスにいかなる脅威も存在できず、デバイスからは引き続き会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3c297-121">The device cannot have any threats present and still access company resources.</span></span> <span data-ttu-id="3c297-122">いずれかの脅威が見つかった場合、デバイスは非準拠と評価されます。</span><span class="sxs-lookup"><span data-stu-id="3c297-122">If any threats are found, the device is evaluated as non-compliant.</span></span>

    <span data-ttu-id="3c297-123">b.</span><span class="sxs-lookup"><span data-stu-id="3c297-123">b.</span></span>  <span data-ttu-id="3c297-124">**[低]**: 存在する脅威が低レベルの場合のみ、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="3c297-124">**Low**: The device is compliant if only low level threats are present.</span></span> <span data-ttu-id="3c297-125">低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。</span><span class="sxs-lookup"><span data-stu-id="3c297-125">Anything higher puts the device in a non-compliant status.</span></span>

    <span data-ttu-id="3c297-126">c.</span><span class="sxs-lookup"><span data-stu-id="3c297-126">c.</span></span>  <span data-ttu-id="3c297-127">**[中]**: デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="3c297-127">**Medium**: The device is compliant if the threats found on the device are low or medium level.</span></span> <span data-ttu-id="3c297-128">高レベルの脅威が検出された場合は、デバイスは非準拠と判定されます。</span><span class="sxs-lookup"><span data-stu-id="3c297-128">If high level threats are detected, the device is determined as non-compliant.</span></span>

    <span data-ttu-id="3c297-129">d.</span><span class="sxs-lookup"><span data-stu-id="3c297-129">d.</span></span>  <span data-ttu-id="3c297-130">**[High]** (高): 最も安全性の低い状態です。</span><span class="sxs-lookup"><span data-stu-id="3c297-130">**High**: This is the least secure.</span></span> <span data-ttu-id="3c297-131">この場合、すべての脅威レベルが許可され、レポート目的のみで Skycure Mobile Threat Defense が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c297-131">This allows all threat levels, and uses Skycure mobile threat defense for reporting purposes only.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c297-132">Office 365 またはその他のサービスに対する条件付きアクセス ポリシーを作成すると、このコンプライアンス評価が適用され、非準拠デバイスは脅威が解決されるまでサービスへのアクセスは禁止されます。</span><span class="sxs-lookup"><span data-stu-id="3c297-132">If you create conditional access policies for Office 365 or other services, this compliance evaluation is assessed and non-compliant devices are blocked from accessing those services until the threat is resolved.</span></span>

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span data-ttu-id="3c297-133"><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>次の手順</span><span class="sxs-lookup"><span data-stu-id="3c297-133"><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Next steps</span></span>

-   <span data-ttu-id="3c297-134">次の条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c297-134">Create a conditional access policy for:</span></span>

    -   [<span data-ttu-id="3c297-135">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3c297-135">Exchange Online</span></span>](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [<span data-ttu-id="3c297-136">Exchange On-premises</span><span class="sxs-lookup"><span data-stu-id="3c297-136">Exchange On-premises</span></span>](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [<span data-ttu-id="3c297-137">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3c297-137">SharePoint Online</span></span>](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [<span data-ttu-id="3c297-138">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3c297-138">Skype for Business Online</span></span>](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [<span data-ttu-id="3c297-139">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="3c297-139">Dynamics CRM</span></span>](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)
