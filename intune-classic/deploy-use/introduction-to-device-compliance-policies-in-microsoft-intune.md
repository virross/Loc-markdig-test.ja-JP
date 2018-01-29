---
title: "デバイス コンプライアンス ポリシー"
description: "このトピックでは、デバイス コンプライアンス ポリシーの内容とそのしくみについて説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 69c987ac9e5ed2bc3eae7ebe19e62893b40a9eb6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="device-compliance-policies-in-microsoft-intune"></a><span data-ttu-id="f2afc-103">Microsoft Intune のデバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="f2afc-103">Device compliance policies in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="what-is-a-compliance-policy"></a><span data-ttu-id="f2afc-104">コンプライアンス ポリシーとは</span><span class="sxs-lookup"><span data-stu-id="f2afc-104">What is a compliance policy?</span></span>
<span data-ttu-id="f2afc-105">会社のデータを容易に保護できるようにするには、会社のアプリとデータへのアクセスに使用されるデバイスが特定のルールに準拠していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2afc-105">To help protect company data, you need to make sure that the devices used to access company apps and data comply with certain rules.</span></span> <span data-ttu-id="f2afc-106">これらのルールには、PIN を使用するデバイスへのアクセスと、デバイスに格納されているデータの暗号化に関するものが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2afc-106">These rules might include using a PIN to access devices and encrypting data stored on devices.</span></span> <span data-ttu-id="f2afc-107">このような一連のルールは、コンプライアンス ポリシーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f2afc-107">A set of such rules is called a compliance policy.</span></span>

## <a name="how-should-i-use-compliance-policies"></a><span data-ttu-id="f2afc-108">コンプライアンス ポリシーの使用方法</span><span class="sxs-lookup"><span data-stu-id="f2afc-108">How should I use compliance policies?</span></span>
<span data-ttu-id="f2afc-109">コンプライアンス ポリシーは、コンプライアンス ポリシー ルールに準拠しているデバイスにのみ電子メールや他のサービスへのアクセスを許可する条件付きアクセス ポリシーと一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2afc-109">You can use compliance policies with conditional access policies to allow only devices that comply with compliance policy rules to access email and other services.</span></span> <span data-ttu-id="f2afc-110">2 つのポリシーを組み合わせて使用する方法については、「[電子メールと O365 サービスへのアクセスを制限する](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2afc-110">To learn how the two policies can be used together, read the [Restrict access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

<span data-ttu-id="f2afc-111">また、条件付きアクセスと独立してコンプライアンス ポリシーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2afc-111">You can also use compliance policies independently of conditional access.</span></span> <span data-ttu-id="f2afc-112">コンプライアンス ポリシーを単独で使用した場合、対象のデバイスが評価され、コンプライアンス ステータスを含めて報告されます。</span><span class="sxs-lookup"><span data-stu-id="f2afc-112">When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status.</span></span> <span data-ttu-id="f2afc-113">たとえば、暗号化されていないデバイスの数、脱獄またはルート化されたデバイスに関するレポートを必要とすることがあります。</span><span class="sxs-lookup"><span data-stu-id="f2afc-113">For example, you might want to report about how many devices are not encrypted, or which devices are jailbroken or rooted.</span></span> <span data-ttu-id="f2afc-114">ただし、コンプライアンス ポリシーを単独で使用した場合、会社のリソースへのアクセス制限が設定されません。</span><span class="sxs-lookup"><span data-stu-id="f2afc-114">But when you use compliance policies independently, no access restrictions to company resources are in place.</span></span>

<span data-ttu-id="f2afc-115">コンプライアンス ポリシーをユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="f2afc-115">You deploy compliance policies to users.</span></span> <span data-ttu-id="f2afc-116">コンプライアンス ポリシーがユーザーに展開されると、ユーザーのデバイスのコンプライアンスがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="f2afc-116">When a compliance policy is deployed to a user, the user's devices are checked for compliance.</span></span>
<span data-ttu-id="f2afc-117">ポリシーの展開後にモバイル デバイスがポリシーを取得できるようになるまでの時間の詳細については、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2afc-117">To learn about how long it takes for mobile devices to get a policy after the policy is deployed, see [Manage settings and features on your devices](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies).</span></span>

<span data-ttu-id="f2afc-118">次の表に、コンプライアンス ポリシーでサポートされるデバイスの種類をリストします。</span><span class="sxs-lookup"><span data-stu-id="f2afc-118">The following table lists the device types that compliance policies support.</span></span> <span data-ttu-id="f2afc-119">この表では、条件付きアクセス ポリシーとコンプライアンス ポリシーを使用する場合に非準拠設定をどのように管理するかについても説明しています。</span><span class="sxs-lookup"><span data-stu-id="f2afc-119">The table also describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.</span></span>

-----------------------------

|<span data-ttu-id="f2afc-120">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="f2afc-120">Policy setting</span></span>| <span data-ttu-id="f2afc-121">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="f2afc-121">Windows 8.1 and later</span></span>| <span data-ttu-id="f2afc-122">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="f2afc-122">Windows Phone 8.1 and later</span></span>| <span data-ttu-id="f2afc-123">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="f2afc-123">iOS 8.0 and later</span></span>|<span data-ttu-id="f2afc-124">Android 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="f2afc-124">Android 4.0 and later</span></span><br/><span data-ttu-id="f2afc-125">Samsung KNOX Standard 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="f2afc-125">Samsung Knox Standard 4.0 and later</span></span>|
|-----|----|----|----|----|
|<span data-ttu-id="f2afc-126">**PIN またはパスワードの構成**</span><span class="sxs-lookup"><span data-stu-id="f2afc-126">**PIN or password configuration**</span></span> |<span data-ttu-id="f2afc-127">修復</span><span class="sxs-lookup"><span data-stu-id="f2afc-127">Remediated</span></span>|<span data-ttu-id="f2afc-128">修復</span><span class="sxs-lookup"><span data-stu-id="f2afc-128">Remediated</span></span>|<span data-ttu-id="f2afc-129">修復</span><span class="sxs-lookup"><span data-stu-id="f2afc-129">Remediated</span></span>|<span data-ttu-id="f2afc-130">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-130">Quarantined</span></span>|
|<span data-ttu-id="f2afc-131">**デバイスの暗号化**</span><span class="sxs-lookup"><span data-stu-id="f2afc-131">**Device encryption**</span></span>|<span data-ttu-id="f2afc-132">該当なし</span><span class="sxs-lookup"><span data-stu-id="f2afc-132">Not applicable</span></span>|<span data-ttu-id="f2afc-133">修復</span><span class="sxs-lookup"><span data-stu-id="f2afc-133">Remediated</span></span>|<span data-ttu-id="f2afc-134">修復 (PIN の設定による)</span><span class="sxs-lookup"><span data-stu-id="f2afc-134">Remediated (by setting PIN)</span></span>|<span data-ttu-id="f2afc-135">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-135">Quarantined</span></span>|
|<span data-ttu-id="f2afc-136">**脱獄またはルート化されたデバイス**</span><span class="sxs-lookup"><span data-stu-id="f2afc-136">**Jailbroken or rooted device**</span></span>|<span data-ttu-id="f2afc-137">適用できません</span><span class="sxs-lookup"><span data-stu-id="f2afc-137">Not applicable</span></span>|<span data-ttu-id="f2afc-138">適用できません</span><span class="sxs-lookup"><span data-stu-id="f2afc-138">Not applicable</span></span>|<span data-ttu-id="f2afc-139">検疫済み (設定ではありません)</span><span class="sxs-lookup"><span data-stu-id="f2afc-139">Quarantined (not a setting)</span></span>|<span data-ttu-id="f2afc-140">検疫済み (設定ではありません)</span><span class="sxs-lookup"><span data-stu-id="f2afc-140">Quarantined (not a setting)</span></span>|
|<span data-ttu-id="f2afc-141">**電子メールのプロファイル**</span><span class="sxs-lookup"><span data-stu-id="f2afc-141">**Email profile**</span></span>|<span data-ttu-id="f2afc-142">適用できません</span><span class="sxs-lookup"><span data-stu-id="f2afc-142">Not applicable</span></span>|<span data-ttu-id="f2afc-143">適用できません</span><span class="sxs-lookup"><span data-stu-id="f2afc-143">Not applicable</span></span>|<span data-ttu-id="f2afc-144">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-144">Quarantined</span></span>|<span data-ttu-id="f2afc-145">適用できません</span><span class="sxs-lookup"><span data-stu-id="f2afc-145">Not applicable</span></span>|
|<span data-ttu-id="f2afc-146">**最小 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="f2afc-146">**Minimum OS version**</span></span>|<span data-ttu-id="f2afc-147">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-147">Quarantined</span></span>|<span data-ttu-id="f2afc-148">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-148">Quarantined</span></span>|<span data-ttu-id="f2afc-149">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-149">Quarantined</span></span>|<span data-ttu-id="f2afc-150">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-150">Quarantined</span></span>|
|<span data-ttu-id="f2afc-151">**最大 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="f2afc-151">**Maximum OS version**</span></span>|<span data-ttu-id="f2afc-152">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-152">Quarantined</span></span>|<span data-ttu-id="f2afc-153">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-153">Quarantined</span></span>|<span data-ttu-id="f2afc-154">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-154">Quarantined</span></span>|<span data-ttu-id="f2afc-155">検疫済み</span><span class="sxs-lookup"><span data-stu-id="f2afc-155">Quarantined</span></span>|
|<span data-ttu-id="f2afc-156">**Windows 正常性構成証明書**</span><span class="sxs-lookup"><span data-stu-id="f2afc-156">**Windows health attestation**</span></span>|<span data-ttu-id="f2afc-157">検疫済み: Windows 10 および Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="f2afc-157">Quarantined: Windows 10 and Windows 10 Mobile</span></span><br /><br /><span data-ttu-id="f2afc-158">該当なし: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f2afc-158">Not applicable: Windows 8.1</span></span>|<span data-ttu-id="f2afc-159">適用できません</span><span class="sxs-lookup"><span data-stu-id="f2afc-159">Not applicable</span></span>|<span data-ttu-id="f2afc-160">適用できません</span><span class="sxs-lookup"><span data-stu-id="f2afc-160">Not applicable</span></span>|<span data-ttu-id="f2afc-161">適用できません</span><span class="sxs-lookup"><span data-stu-id="f2afc-161">Not applicable</span></span>|

------------------------------

<span data-ttu-id="f2afc-162">**修復** = デバイス オペレーティング システムによって準拠が強制されます </span><span class="sxs-lookup"><span data-stu-id="f2afc-162">**Remediated** = The device operating system enforces compliance.</span></span> <span data-ttu-id="f2afc-163">(たとえば、ユーザーは PIN を設定するように強制されます)。</span><span class="sxs-lookup"><span data-stu-id="f2afc-163">(For example, the user is forced to set a PIN.)</span></span>

<span data-ttu-id="f2afc-164">**検疫済み** = デバイス オペレーティング システムによって準拠が強制されません </span><span class="sxs-lookup"><span data-stu-id="f2afc-164">**Quarantined** = The device operating system does not enforce compliance.</span></span> <span data-ttu-id="f2afc-165">(たとえば、Android デバイスでは、ユーザーはデバイスの暗号化を強制されません)。デバイスが準拠していない場合、次のアクションが行われます。</span><span class="sxs-lookup"><span data-stu-id="f2afc-165">(For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:</span></span>

-   <span data-ttu-id="f2afc-166">ユーザーに条件付きアクセス ポリシーを適用すると、デバイスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f2afc-166">The device is blocked if a conditional access policy applies to the user.</span></span>

-   <span data-ttu-id="f2afc-167">ポータル サイトは、コンプライアンスの問題をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f2afc-167">The company portal notifies the user about any compliance problems.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f2afc-168">次の手順</span><span class="sxs-lookup"><span data-stu-id="f2afc-168">Next steps</span></span>
[<span data-ttu-id="f2afc-169">デバイス コンプライアンス ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="f2afc-169">Create a device compliance policy</span></span>](create-a-device-compliance-policy-in-microsoft-intune.md)

[<span data-ttu-id="f2afc-170">デバイス コンプライアンス ポリシーの展開と監視</span><span class="sxs-lookup"><span data-stu-id="f2afc-170">Deploy and monitor a device compliance policy</span></span>](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a><span data-ttu-id="f2afc-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2afc-171">See also</span></span>
[<span data-ttu-id="f2afc-172">電子メールと O365 サービスへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="f2afc-172">Restrict access to email and O365 services</span></span>](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
