---
title: "デバイスの防御ルールを有効にする"
description: "デバイスのコンプライアンス ポリシーでモバイル脅威防御ルールを有効にします。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5f2717a48943c28c8e3a56d50f71d43df456db80
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="create-lookout-device-compliance-policy-in-intune"></a><span data-ttu-id="7b5a2-103">Intune での Lookout デバイス コンプライアンス ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="7b5a2-103">Create Lookout device compliance policy in Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="7b5a2-104">Intune と Lookout Mobile Threat Defense を使用することで、モバイル デバイスの脅威を検出し、デバイスのリスクを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-104">Intune with Lookout Mobile Threat Defense lets you detect threats on mobile devices and assess risk on those devices.</span></span> <span data-ttu-id="7b5a2-105">リスクを評価するコンプライアンス ポリシー ルールを作成すれば、デバイスがポリシーに準拠しているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-105">You can create a compliance policy rule that assesses risk to determine if the device is compliant.</span></span> <span data-ttu-id="7b5a2-106">条件付きアクセス ポリシーを使用すれば、デバイスのコンプライアンスに基づいて、サービスへのアクセスを禁止できます。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-106">You can then use conditional access policy to block access to services based on device compliance.</span></span>

<span data-ttu-id="7b5a2-107">Lookout Mobile Threat Defense を含むコンプライアンス ポリシーに関する前提条件:</span><span class="sxs-lookup"><span data-stu-id="7b5a2-107">Prerequisites for compliance policy with Lookout Mobile Threat Defense:</span></span>

- [<span data-ttu-id="7b5a2-108">Lookout Mobile Threat Defense サブスクリプションを設定する</span><span class="sxs-lookup"><span data-stu-id="7b5a2-108">Set up Lookout Mobile Threat Defense subscription</span></span>](setup-your-lookout-mtd-subscription.md)
- [<span data-ttu-id="7b5a2-109">Intune で Lookout の接続を有効にする</span><span class="sxs-lookup"><span data-stu-id="7b5a2-109">Enable the Lookout connection in Intune</span></span>](enable-lookout-mtd-connection.md)
- [<span data-ttu-id="7b5a2-110">Lookout for Work アプリを構成して展開する</span><span class="sxs-lookup"><span data-stu-id="7b5a2-110">Configure and deploy the Lookout for work app</span></span>](configure-deploy-lookout-for-work-app.md)

<span data-ttu-id="7b5a2-111">Lookout Mobile Threat Defense をセットアップするときに、[Lookout コンソール](https://aad.lookout.com)で、さまざまな脅威を高、中、低として分類するポリシーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-111">As part of the Lookout Mobile Threat Defense setup, in the [Lookout console](https://aad.lookout.com), you created a policy that classifies various threats as high, medium and low.</span></span> <span data-ttu-id="7b5a2-112">Intune のコンプライアンス ポリシーでは、許容される最大脅威レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-112">In the Intune compliance policy, you set the maximum allowed threat level.</span></span>

1. <span data-ttu-id="7b5a2-113">[Intune 管理者コンソール](https://manage.microsoft.com)で、**[コンプライアンス ポリシー]** ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-113">In the [Intune administrator console](https://manage.microsoft.com), go to the **Compliance Policies** page.</span></span> <span data-ttu-id="7b5a2-114">既存のコンプライアンス ポリシーを使用することも、新たに作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-114">You can either use an existing compliance policy or create a new one.</span></span> <span data-ttu-id="7b5a2-115">**[デバイスのヘルス]** に移動して、**[デバイス脅威保護]** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-115">Go to **Device Health** and enable **Device Threat Protection**.</span></span>
  <span data-ttu-id="7b5a2-116">![デバイス脅威防御ルールの設定を示すスクリーンショット ](../media/mtp/mtp-compliance-policy-rule.png)</span><span class="sxs-lookup"><span data-stu-id="7b5a2-116">![screenshot showing the device threat protection rule setting in ](../media/mtp/mtp-compliance-policy-rule.png)</span></span>

2. <span data-ttu-id="7b5a2-117">**[許容される驚異の最大レベル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-117">Select the **Maximum allowed threat level**:</span></span>
  * <span data-ttu-id="7b5a2-118">**[なし (セキュリティ保護)]**: これはセキュリティ上最も安全です。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-118">**None (Secured)**: This is the most secure.</span></span>  <span data-ttu-id="7b5a2-119">デバイスにいかなる脅威も存在できず、デバイスからは引き続き会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-119">The device cannot have any threats present and still access company resources.</span></span>  <span data-ttu-id="7b5a2-120">いずれかの脅威が見つかった場合、デバイスは非準拠と評価されます。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-120">If any threats are found, the device is evaluated as non-compliant.</span></span>  
  * <span data-ttu-id="7b5a2-121">**[低]**: 存在する脅威が低レベルの場合のみ、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-121">**Low**: The device is compliant if only low level threats are present.</span></span> <span data-ttu-id="7b5a2-122">低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-122">Anything higher puts the device in a non-compliant status.</span></span>
  * <span data-ttu-id="7b5a2-123">**[中]**: デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-123">**Medium**: The device is compliant if the threats found on the device are low or medium level.</span></span> <span data-ttu-id="7b5a2-124">高レベルの脅威が検出された場合は、デバイスは非準拠と判定されます。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-124">If high level threats are detected, the device is determined as non-compliant.</span></span>
  * <span data-ttu-id="7b5a2-125">**[High]** (高): 最も安全性の低い状態です。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-125">**High**: This is the least secure.</span></span> <span data-ttu-id="7b5a2-126">この場合、すべての脅威レベルが許可され、レポート目的のみで Lookout Mobile Threat Protection が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-126">This allows all threat levels, and uses Lookout mobile threat protection for reporting purposes only.</span></span>

![デバイス脅威防御ルール設定の脅威レベル オプションを示すスクリーンショット](../media/mtp/mtp-compliance-policy-setting.png)

<span data-ttu-id="7b5a2-128">Office 365 またはその他のサービスに対する条件付きアクセス ポリシーを作成すると、このコンプライアンス評価が適用され、非準拠デバイスは脅威が解決されるまでサービスへのアクセスは禁止されます。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-128">If you create conditional access policies for Office 365 or other services, this compliance evaluation is assessed and non-compliant devices are blocked from accessing those services until the threat is resolved.</span></span>

## <a name="monitor-device-threats"></a><span data-ttu-id="7b5a2-129">デバイス脅威の監視</span><span class="sxs-lookup"><span data-stu-id="7b5a2-129">Monitor device threats</span></span>
<span data-ttu-id="7b5a2-130">デバイスのコンプライアンス状態を確認するには、**Intune 管理者コンソール**に移動し、[[すべてのデバイス]](https://manage.microsoft.com) を表示します。</span><span class="sxs-lookup"><span data-stu-id="7b5a2-130">To see the compliance state of a device, go to the [Intune administrator console](https://manage.microsoft.com) and view **All Devices**.</span></span>

![デバイスのコンプライアンス状態が表示されている Intune 管理者コンソールのデバイス ページのスクリーンショット](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a><span data-ttu-id="7b5a2-132">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7b5a2-132">Next steps</span></span>
* <span data-ttu-id="7b5a2-133">条件付きアクセス ポリシーを作成します</span><span class="sxs-lookup"><span data-stu-id="7b5a2-133">Create conditional access policy</span></span>
  * [<span data-ttu-id="7b5a2-134">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7b5a2-134">Exchange Online</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [<span data-ttu-id="7b5a2-135">Exchange On-premises</span><span class="sxs-lookup"><span data-stu-id="7b5a2-135">Exchange On-premises</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [<span data-ttu-id="7b5a2-136">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7b5a2-136">SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [<span data-ttu-id="7b5a2-137">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7b5a2-137">Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [<span data-ttu-id="7b5a2-138">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="7b5a2-138">Dynamics CRM</span></span>](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
