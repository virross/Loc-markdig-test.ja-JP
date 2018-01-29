---
title: "電子メールおよび Office 365 を保護する"
description: "このトピックでは、条件付きアクセスを使用し、準拠デバイスのみに SharePoint Online およびその他のサービスの会社の電子メールや会社データへのアクセスを許可する方法について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e121a3aaf4988bd92c36eb79131b2205263fb309
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="protect-access-to-email-office-365-and-other-services-with-microsoft-intune"></a><span data-ttu-id="11aa3-103">Microsoft Intune で電子メール、Office 365、およびその他のサービスへのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="11aa3-103">Protect access to email, Office 365, and other services with Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="11aa3-104">会社の電子メールへのアクセス、**Exchange On-premises**、**Exchange Online**、**Exchange Online Dedicated**、**SharePoint Online**、**Skype for Business Online** のような Office 365 サービスへのアクセス、その他のサービスへのアクセスを Enterprise Mobility + Security (EMS) 条件付きアクセスで保護できます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-104">You can protect access to your company email, Office 365 services like **Exchange On-premises**, **Exchange Online**, **Exchange Online Dedicated**,  **SharePoint Online**, **Skype for Business Online**, and other services by using Enterprise Mobility + Security (EMS) Conditional Access.</span></span> <span data-ttu-id="11aa3-105">この機能では、会社の電子メールや Office 365 サービスへのアクセスを、Intune 管理コンソールまたは Azure クラシック ポータルで設定した条件付きアクセス ルールに準拠するデバイスに限定できます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-105">This capability allows you to make sure that access to your company email and Office 365 services is restricted to devices that are compliant with the conditional access rules that you set either in the Intune admin console, or Azure classic portal.</span></span>
## <a name="how-does-conditional-access-work"></a><span data-ttu-id="11aa3-106">条件付きアクセスのしくみ</span><span class="sxs-lookup"><span data-stu-id="11aa3-106">How does conditional access work?</span></span>
<span data-ttu-id="11aa3-107">コンプライアンス ポリシーの設定を利用し、デバイスのコンプライアンスを評価できます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-107">You can use compliance policy settings to evaluate the compliance of a device.</span></span> <span data-ttu-id="11aa3-108">条件付きアクセス ポリシーは、この評価を使用して、特定のサービスへのアクセスを制限または許可します。</span><span class="sxs-lookup"><span data-stu-id="11aa3-108">A conditional access policy uses the evaluation to restrict or allow access to a specific service.</span></span> <span data-ttu-id="11aa3-109">条件付きアクセス ポリシーがデバイス コンプライアンス ポリシーとの組み合わせで使用される場合、準拠するデバイスのみがサービスへのアクセスを許可されます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-109">When you use a conditional access policy in combination with a device compliance policy, only compliant devices are allowed to access the service.</span></span> <span data-ttu-id="11aa3-110">コンプライアンス ポリシーと条件付きアクセス ポリシーはユーザーに対して展開されます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-110">The compliance policy and the conditional access policy are deployed to the user.</span></span> <span data-ttu-id="11aa3-111">サービスへのアクセスにユーザーが使用するすべてのデバイスは、ポリシーによってコンプライアンスがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-111">Any device that the user uses to access the services is checked for compliance with the policies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11aa3-112">デバイスを使用しているユーザーは、デバイスのコンプライアンスを評価するため、ユーザーにコンプライアンス ポリシーを展開しておく必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="11aa3-112">Keep in mind that the user who is using the device must have a compliance policy that is deployed to them in order for the device to be evaluated for compliance.</span></span>
> <span data-ttu-id="11aa3-113">コンプライアンス ポリシーがユーザーに展開されていない場合、デバイスは準拠したものと見なされ、アクセス制限は適用されません。</span><span class="sxs-lookup"><span data-stu-id="11aa3-113">If no compliance policy is deployed to the user, the device is treated as compliant, and no access restrictions are applied.</span></span>

<span data-ttu-id="11aa3-114">ポリシーに設定した条件をデバイスが満たしていない場合、デバイスの登録と、デバイスが準拠デバイスとなることを妨げている問題の修正を行うプロセスがエンド ユーザーに案内されます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-114">When devices don't meet the conditions that are set in the policies, the end user is guided though the process of enrolling the device and fixing the issue that prevents the device from being compliant.</span></span>

<span data-ttu-id="11aa3-115">条件付きアクセスの一般的なフロー:</span><span class="sxs-lookup"><span data-stu-id="11aa3-115">A typical flow of conditional access:</span></span>

![図は、デバイスがサービスへのアクセスを許可されているか、またはブロックされているかを決定するために使用する判断ポイントを示しています](../media/ConditionalAccess4.png)

## <a name="setup-considerations"></a><span data-ttu-id="11aa3-117">セットアップに関する注意点</span><span class="sxs-lookup"><span data-stu-id="11aa3-117">Setup considerations</span></span>

### <a name="licensing"></a><span data-ttu-id="11aa3-118">ライセンス</span><span class="sxs-lookup"><span data-stu-id="11aa3-118">Licensing</span></span>

<span data-ttu-id="11aa3-119">Microsoft Intune と Azure Active Directory (Azure AD) Premium はシームレスに連動し、EMS 条件付きアクセスで複数のコントロール層を提供します。Intune で条件付きアクセス ポリシーを展開する場合、両方の製品のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="11aa3-119">Microsoft Intune and Azure Active Directory (Azure AD) Premium work seamlessly together to provide multiple layers of control through EMS conditional access, if you want to deploy conditional access policies using Intune, you're required to have license for both products.</span></span>

<span data-ttu-id="11aa3-120">**Azure AD Premium ライセンス**はスタンドアロン サービスとして購入するか、Enterprise Agreement の一部として (Intune と共に) 購入できます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-120">**Azure AD Premium licenses** can be purchased as a standalone service or can be purchased (along with Intune) as part of the Enterprise agreement.</span></span> <span data-ttu-id="11aa3-121">Intune で条件付きアクセス ポリシーを展開した場合、適切な Azure AD Premium または **EMS のライセンス**を取得していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="11aa3-121">If you have deployed conditional access policies with Intune, please ensure that you have obtained the proper Azure AD Premium or **EMS licenses**.</span></span>

- <span data-ttu-id="11aa3-122">詳細については、[Enterprise Mobility の価格に関するページ](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing)または [Azure Active Directory の価格に関するページ](https://azure.microsoft.com/pricing/details/active-directory/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11aa3-122">Learn more about [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

<span data-ttu-id="11aa3-123">また、条件付きアクセス ポリシーを適用する予定のユーザーに [Azure AD Premium または EMS のライセンスが割り当てられている](/intune/licenses-assign)ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="11aa3-123">Additionally, make sure the users you plan to apply conditional access policies are [assigned with the Azure AD Premium or EMS licenses](/intune/licenses-assign).</span></span>

### <a name="device-compliance-settings"></a><span data-ttu-id="11aa3-124">デバイス コンプライアンス設定</span><span class="sxs-lookup"><span data-stu-id="11aa3-124">Device compliance settings</span></span>

<span data-ttu-id="11aa3-125">条件付きアクセスを設定するには、デバイスのコンプライアンス ポリシーと条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="11aa3-125">To set up conditional access, configure a device compliance policy and a conditional access policy.</span></span> <span data-ttu-id="11aa3-126">コンプライアンス ポリシーには、パスコード、暗号化、デバイスの脱獄の有無といった設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="11aa3-126">The compliance policy includes settings like passcode, encryption, and whether or not a device is jailbroken.</span></span> <span data-ttu-id="11aa3-127">準拠したデバイスと見なされるには、これらの規則を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="11aa3-127">The device must meet these rules in order to be considered compliant.</span></span>

- <span data-ttu-id="11aa3-128">[デバイス コンプライアンス ポリシーとそのしくみについて理解する](introduction-to-device-compliance-policies-in-microsoft-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="11aa3-128">Learn more about [device compliance policy and how it works](introduction-to-device-compliance-policies-in-microsoft-intune.md).</span></span>

### <a name="conditional-access-policy"></a><span data-ttu-id="11aa3-129">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="11aa3-129">Conditional access policy</span></span>

<span data-ttu-id="11aa3-130">次に基づいてアクセスを保護するための条件付きアクセス ポリシーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-130">You can set a conditional access policy to protect access based on:</span></span>
- <span data-ttu-id="11aa3-131">デバイスのコンプライアンス状態。</span><span class="sxs-lookup"><span data-stu-id="11aa3-131">The device compliance status.</span></span>
- <span data-ttu-id="11aa3-132">デバイスで実行されているプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="11aa3-132">The platform that is running on the device.</span></span>
- <span data-ttu-id="11aa3-133">サービスにアクセスするために使用するアプリの種類。</span><span class="sxs-lookup"><span data-stu-id="11aa3-133">The type of apps that are used to access the services.</span></span>

<span data-ttu-id="11aa3-134">他の Intune ポリシーとは異なり、条件付きアクセス ポリシーは展開しません。</span><span class="sxs-lookup"><span data-stu-id="11aa3-134">Unlike other Intune policies, you don't deploy conditional access policies.</span></span> <span data-ttu-id="11aa3-135">代わりに、ポリシーを構成して、そのポリシーが必要なユーザーを選択すると、ポリシーがすべての対象ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="11aa3-135">Instead, after you configure the policy and select the users that should have the policy, the policy is applied to all targeted users.</span></span> <span data-ttu-id="11aa3-136">ユーザーがポリシーの対象となる場合、ユーザーに使用される各デバイスがリソースにアクセスするには、ポリシーを遵守している必要があります。</span><span class="sxs-lookup"><span data-stu-id="11aa3-136">When a user is targeted by a policy, each device they use must be compliant in order for them to access resources.</span></span>


## <a name="next-steps"></a><span data-ttu-id="11aa3-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="11aa3-137">Next steps</span></span>


2. <span data-ttu-id="11aa3-138">[デバイス コンプライアンス ポリシーの作成](create-a-device-compliance-policy-in-microsoft-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="11aa3-138">[Create a device compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md).</span></span>

3. <span data-ttu-id="11aa3-139">次の Microsoft クラウド サービス/製品のいずれかの条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="11aa3-139">Create a conditional access policy for one of the following Microsoft cloud services/product:</span></span>

   - [<span data-ttu-id="11aa3-140">Exchange Online の条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="11aa3-140">Create a conditional access policy for Exchange Online</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)
   - [<span data-ttu-id="11aa3-141">Exchange On-premises の条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="11aa3-141">Create a conditional access policy for Exchange On-premises</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
   - [<span data-ttu-id="11aa3-142">Exchange Online Dedicated の条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="11aa3-142">Create a conditional access policy for new Exchange Online Dedicated</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)
   - [<span data-ttu-id="11aa3-143">古い Exchange Online Dedicated の条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="11aa3-143">Create a conditional access policy for legacy Exchange Online Dedicated</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
   - [<span data-ttu-id="11aa3-144">SharePoint Online の条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="11aa3-144">Create a conditional access policy for SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
   - [<span data-ttu-id="11aa3-145">Skype for Business Online の条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="11aa3-145">Create a conditional access policy for Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
   - [<span data-ttu-id="11aa3-146">Dynamics CRM Online の条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="11aa3-146">Create a conditional access policy for Dynamics CRM Online</span></span>](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
