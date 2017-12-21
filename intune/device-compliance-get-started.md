---
title: "Intune のデバイス コンプライアンス ポリシー"
titleSuffix: Azure portal
description: "このトピックでは、Microsoft Intune でのデバイス コンプライアンスについて説明します\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa78383233950e342c5ab0f83095bba3c8fda1f9
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-intune-device-compliance-policies"></a><span data-ttu-id="773d9-103">Intune のデバイス コンプライアンス ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="773d9-103">Get started with Intune device compliance policies</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a><span data-ttu-id="773d9-104">Intune でのデバイス コンプライアンスとは</span><span class="sxs-lookup"><span data-stu-id="773d9-104">What is device compliance in Intune?</span></span>

<span data-ttu-id="773d9-105">Intune のデバイス コンプライアンス ポリシーは、デバイスが Intune によって "準拠している" と見なされるために遵守する必要がある規則および設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="773d9-105">Intune device compliance policies define the rules and settings that a device must comply with in order to be considered compliant by Intune.</span></span>

<span data-ttu-id="773d9-106">この規則には次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="773d9-106">These rules include the following:</span></span>

- <span data-ttu-id="773d9-107">パスワードを使用したデバイスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="773d9-107">Use a password to access devices</span></span>

- <span data-ttu-id="773d9-108">暗号化</span><span class="sxs-lookup"><span data-stu-id="773d9-108">Encryption</span></span>

- <span data-ttu-id="773d9-109">デバイスが脱獄またはルート化されているかどうか</span><span class="sxs-lookup"><span data-stu-id="773d9-109">Whether the device is jail-broken or rooted</span></span>

- <span data-ttu-id="773d9-110">必要な最小 OS バージョン</span><span class="sxs-lookup"><span data-stu-id="773d9-110">Minimum OS version required</span></span>

- <span data-ttu-id="773d9-111">許可される最大 OS バージョン</span><span class="sxs-lookup"><span data-stu-id="773d9-111">Maximum OS version allowed</span></span>

- <span data-ttu-id="773d9-112">デバイスが Mobile Threat Defense レベル以下であることが必要</span><span class="sxs-lookup"><span data-stu-id="773d9-112">Require the device to be at or under the Mobile Threat Defense level</span></span>

<span data-ttu-id="773d9-113">デバイス コンプライアンス ポリシーを使用して、デバイス コンプライアンスの状態を監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="773d9-113">You can also use device compliance policies to monitor the compliance status in your devices.</span></span>

### <a name="device-compliance-requirements"></a><span data-ttu-id="773d9-114">デバイス コンプライアンスの要件</span><span class="sxs-lookup"><span data-stu-id="773d9-114">Device compliance requirements</span></span>

<span data-ttu-id="773d9-115">コンプライアンス要件とは、基本的にはデバイスの PIN または暗号化を要求するようなルールであり、コンプライアンス ポリシーに対して必要か不要かを指定できます。</span><span class="sxs-lookup"><span data-stu-id="773d9-115">Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.</span></span>

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="pre-requisites"></a><span data-ttu-id="773d9-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="773d9-116">Pre-requisites</span></span>

<span data-ttu-id="773d9-117">Intune でデバイス コンプライアンス ポリシーを使用するには、次のサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="773d9-117">You need to have the following subscriptions to use device compliance policies with Intune:</span></span>

- <span data-ttu-id="773d9-118">Intune EMS</span><span class="sxs-lookup"><span data-stu-id="773d9-118">Intune EMS</span></span>

- <span data-ttu-id="773d9-119">Azure AD プレミアム</span><span class="sxs-lookup"><span data-stu-id="773d9-119">Azure AD Premium</span></span>

###  <a name="supported-platforms"></a><span data-ttu-id="773d9-120">サポートされているプラットフォーム:</span><span class="sxs-lookup"><span data-stu-id="773d9-120">Supported Platforms:</span></span>

-   <span data-ttu-id="773d9-121">Android</span><span class="sxs-lookup"><span data-stu-id="773d9-121">Android</span></span>

-   <span data-ttu-id="773d9-122">iOS</span><span class="sxs-lookup"><span data-stu-id="773d9-122">iOS</span></span>

-   <span data-ttu-id="773d9-123">macOS (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="773d9-123">macOS (preview)</span></span>

-   <span data-ttu-id="773d9-124">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="773d9-124">Windows 8.1</span></span>

-   <span data-ttu-id="773d9-125">Windows Phone 8。1</span><span class="sxs-lookup"><span data-stu-id="773d9-125">Windows Phone 8.1</span></span>

-   <span data-ttu-id="773d9-126">Windows 10</span><span class="sxs-lookup"><span data-stu-id="773d9-126">Windows 10</span></span>

> [!IMPORTANT]
> <span data-ttu-id="773d9-127">デバイス コンプライアンスの状態をレポートするには、Intune にデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="773d9-127">Devices must be enrolled into Intune to report their compliance statuses.</span></span>

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a><span data-ttu-id="773d9-128">Azure AD で Intune のデバイス コンプライアンス ポリシーを操作する方法</span><span class="sxs-lookup"><span data-stu-id="773d9-128">How Intune device compliance policies work with Azure AD</span></span>

<span data-ttu-id="773d9-129">デバイスが Intune に登録されると、Azure AD の登録プロセスが発生し、デバイスの属性が Azure AD への詳細な情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="773d9-129">When a device is enrolled into Intune, the Azure AD registration process happens, which updates the device atributes with more information into Azure AD.</span></span> <span data-ttu-id="773d9-130">キーのデバイス情報の 1 つは、デバイス コンプライアンスの状態で、電子メールと他の企業リソースへのアクセスをブロックまたは許可するための条件付きアクセス ポリシーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="773d9-130">One of the key device information is the device compliance status, which is used by conditional access policies to block or allow access to e-mail and other corporate resources.</span></span>

- <span data-ttu-id="773d9-131">詳細については、[Azure Active Directory の登録プロセス](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="773d9-131">Learn more about [Azure AD registration process](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).</span></span>

##  <a name="ways-to-use-device-compliance-policies"></a><span data-ttu-id="773d9-132">デバイス コンプライアンス ポリシーを使用する方法</span><span class="sxs-lookup"><span data-stu-id="773d9-132">Ways to use device compliance policies</span></span>

### <a name="with-conditional-access"></a><span data-ttu-id="773d9-133">条件付きアクセスあり</span><span class="sxs-lookup"><span data-stu-id="773d9-133">With conditional access</span></span>
<span data-ttu-id="773d9-134">コンプライアンス ポリシーは、条件付きアクセスと一緒に使用することで、1 つ以上のデバイス コンプライアンス ポリシー ルールに準拠しているデバイスにのみ電子メールや他の企業リソースへのアクセスを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="773d9-134">You can use compliance policy with conditional access to allow only devices that comply with one or more device compliance policy rules to access email and other corporate resources.</span></span>

### <a name="without-conditional-access"></a><span data-ttu-id="773d9-135">条件付きアクセスなし</span><span class="sxs-lookup"><span data-stu-id="773d9-135">Without conditional access</span></span>
<span data-ttu-id="773d9-136">条件付きアクセスと独立してデバイス コンプライアンス ポリシーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="773d9-136">You can also use device compliance policies independently of conditional access.</span></span> <span data-ttu-id="773d9-137">コンプライアンス ポリシーを単独で使用した場合、対象のデバイスが評価され、コンプライアンス ステータスを含めて報告されます。</span><span class="sxs-lookup"><span data-stu-id="773d9-137">When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status.</span></span> <span data-ttu-id="773d9-138">たとえば、暗号化されていないデバイスの数や脱獄またはルート化されたデバイスに関するレポートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="773d9-138">For example, you can get a report on how many devices are not encrypted, or which devices are jail-broken or rooted.</span></span> <span data-ttu-id="773d9-139">ただし、コンプライアンス ポリシーを単独で使用した場合、会社のリソースへのアクセス制限が設定されません。</span><span class="sxs-lookup"><span data-stu-id="773d9-139">But when you use compliance policies independently, no access restrictions to company resources are in place.</span></span>

<span data-ttu-id="773d9-140">コンプライアンス ポリシーはユーザーに展開して使用します。</span><span class="sxs-lookup"><span data-stu-id="773d9-140">You deploy compliance policy to users.</span></span> <span data-ttu-id="773d9-141">コンプライアンス ポリシーがユーザーに展開されると、ユーザーのデバイスのコンプライアンスがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="773d9-141">When a compliance policy is deployed to a user, the user's devices are checked for compliance.</span></span> <span data-ttu-id="773d9-142">ポリシーの展開後にモバイル デバイスがポリシーを取得できるようになるまでにかかる時間については、デバイスでの設定と機能の管理に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="773d9-142">To learn about how long it takes for mobile devices to get a policy after the policy is deployed, see Manage settings and features on your devices.</span></span>

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a><span data-ttu-id="773d9-143">Intune のクラシック ポータルとAzure Portal を比較してデバイス コンプライアンス ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="773d9-143">Using device compliance policies in the Intune classic portal vs. Azure portal</span></span>

<span data-ttu-id="773d9-144">Azure Portal での新しいデバイス コンプライアンス ポリシーのワーク フローへの移行に役立つ主な相違点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="773d9-144">Note the main differences to help you transition to the new device compliance policy work-flow in the Azure portal.</span></span>

- <span data-ttu-id="773d9-145">Azure Portal では、コンプライアンス ポリシーがサポート対象のプラットフォームごとに個別に作成されます。</span><span class="sxs-lookup"><span data-stu-id="773d9-145">In the Azure portal, the compliance policies are created separately for each supported platform.</span></span>
- <span data-ttu-id="773d9-146">Intune クラシック ポータルでは、すべてのサポート対象プラットフォームで 1 つのデバイス コンプライアンス ポリシーが共有されていました。</span><span class="sxs-lookup"><span data-stu-id="773d9-146">In the Intune classic portal, one device compliance policy was common to all supported platforms.</span></span>

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a><span data-ttu-id="773d9-147">デバイス コンプライアンス ポリシーを Intune クラシック ポータルから Azure Portal に移行する</span><span class="sxs-lookup"><span data-stu-id="773d9-147">Migrate device compliance policies from the Intune classic portal to the Azure portal</span></span>

<span data-ttu-id="773d9-148">[Intune クラシック ポータル](https://manage.microsoft.com)で作成したデバイス コンプライアンス ポリシーは、新しい [Intune Azure Portal](https://portal.azure.com) では表示されません。</span><span class="sxs-lookup"><span data-stu-id="773d9-148">Device compliance policies created in the [Intune classic portal](https://manage.microsoft.com) will not appear in the new [Intune Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="773d9-149">ただし、これらのポリシーは引き続きユーザーを対象とし、Intune クラシック ポータルで管理できます。</span><span class="sxs-lookup"><span data-stu-id="773d9-149">However, they’re still targeted to users and manageable via the Intune classic portal.</span></span>

<span data-ttu-id="773d9-150">Azure Portal の新しいデバイス コンプライアンスに関連した機能を活用するには、Azure Portal で新しいデバイス コンプライアンス ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="773d9-150">If you want to take advantage of the new device compliance related features in the Azure portal, you need to create new device compliance policies in the Azure portal itself.</span></span> <span data-ttu-id="773d9-151">Intune クラシック ポータルのデバイス コンプライアンス ポリシーが既に割り当てられているユーザーに Azure Portal の新しいデバイス コンプライアンス ポリシーを割り当てると、Intune クラシック ポータルで作成されたポリシーよりも Intune Azure Portal のデバイス コンプライアンス ポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="773d9-151">If you assign a new device compliance policy in the Azure portal to a user who also has been assigned with a device compliance policy from the Intune classic portal, the device compliance policies from the Intune Azure portal takes precedence over the ones created in the Intune classic portal.</span></span>

##  <a name="next-steps"></a><span data-ttu-id="773d9-152">次のステップ</span><span class="sxs-lookup"><span data-stu-id="773d9-152">Next steps</span></span>

<span data-ttu-id="773d9-153">以下のプラットフォームに対してデバイス コンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="773d9-153">Create a device compliance policy for the following platforms:</span></span>

- [<span data-ttu-id="773d9-154">Android</span><span class="sxs-lookup"><span data-stu-id="773d9-154">Android</span></span>](compliance-policy-create-android.md)
- [<span data-ttu-id="773d9-155">Android for Work</span><span class="sxs-lookup"><span data-stu-id="773d9-155">Android for work</span></span>](compliance-policy-create-android-for-work.md)
- [<span data-ttu-id="773d9-156">iOS</span><span class="sxs-lookup"><span data-stu-id="773d9-156">iOS</span></span>](compliance-policy-create-ios.md)
- [<span data-ttu-id="773d9-157">macOS</span><span class="sxs-lookup"><span data-stu-id="773d9-157">macOS</span></span>](compliance-policy-create-mac-os.md)
- [<span data-ttu-id="773d9-158">Windows</span><span class="sxs-lookup"><span data-stu-id="773d9-158">Windows</span></span>](compliance-policy-create-windows.md)
