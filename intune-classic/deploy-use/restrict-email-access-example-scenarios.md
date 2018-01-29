---
title: "電子メールの保護に関するシナリオ"
description: "いくつかのシナリオ例と、条件付きアクセスを使用した場合の実装方法。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3116cfdb6b1ea153d914630a23e0db82a8c31d85
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="protect-access-to-email-with-microsoft-intune-example-scenarios"></a><span data-ttu-id="93513-103">Microsoft Intune で電子メールへのアクセスを保護する: シナリオ例</span><span class="sxs-lookup"><span data-stu-id="93513-103">Protect access to email with Microsoft Intune: Example scenarios</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online"></a><span data-ttu-id="93513-104">シナリオ 1: 非準拠のデバイスを使用して Exchange Online にアクセスするユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="93513-104">Scenario 1: Block users from using noncompliant devices to access Exchange Online</span></span>
### <a name="scenario-requirements"></a><span data-ttu-id="93513-105">シナリオの要件</span><span class="sxs-lookup"><span data-stu-id="93513-105">Scenario requirements</span></span>
- <span data-ttu-id="93513-106">展開したコンプライアンス ポリシーにデバイスが準拠していない場合、**[アカウンティング]** Azure Active Directory セキュリティ グループ内のすべてのユーザーの Exchange Online へのアクセスをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93513-106">All users in the **Accounting** Azure Active Directory security group must be blocked from accessing Exchange Online if their device is not compliant with a compliance policy that you deployed.</span></span>
- <span data-ttu-id="93513-107">このグループ内に Intune によってデバイスがサポートされていないユーザーが存在する場合、それらのデバイスでのユーザーによる Exchange Online へのアクセスをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93513-107">If any users exist in this group whose devices are not supported by Intune, they must be blocked from accessing Exchange Online on that device.</span></span>
- <span data-ttu-id="93513-108">**[ファイナンス]** Azure Active Directory セキュリティ グループに属するユーザーはいずれも、さらに **[アカウンティング]** セキュリティ グループに属していたとしても、ポリシーから除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93513-108">Users in the **Finance** Azure Active Directory security group must be exempt from the policy, even if they're also in the **Accounting** security group.</span></span>

<span data-ttu-id="93513-109">これらを実現するためには、次の設定で Exchange Online の条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93513-109">To accomplish this, configure a conditional access policy for Exchange Online with the following settings:</span></span>

- <span data-ttu-id="93513-110">**[条件付きアクセス ポリシーを有効にする]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="93513-110">Choose **Enable conditional access policy**.</span></span>

- <span data-ttu-id="93513-111">先進認証を使用したアプリからのアクセスを許可するプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="93513-111">Choose the platforms that you want to allow access from apps with modern authentication.</span></span>
- <span data-ttu-id="93513-112">Exchange ActiveSync アプリの場合は、**[Microsoft Intune がサポートするプラットフォームの非準拠デバイスをブロックします]** と **[Microsoft Intune がサポートしていないプラットフォームにあるその他のデバイスをすべてブロックします]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="93513-112">For Exchange ActiveSync apps, choose **Block noncompliant devices on platforms supported by Microsoft Intune** and **Block all other devices on platforms not supported by Microsoft Intune.**</span></span>
-   <span data-ttu-id="93513-113">**[対象グループ]** セクションの **[選択されているセキュリティ グループ]** で、**[アカウンティング]** ユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="93513-113">In the **Targeted group** section, under **Selected security groups**, choose the **Accounting** user group.</span></span>

-   <span data-ttu-id="93513-114">**[例外グループ]** セクションの **[選択されているセキュリティ グループ]** で、**[ファイナンス]** ユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="93513-114">In the **Exempted group** section, under **Selected security groups**, choose the **Finance** user group.</span></span>


<span data-ttu-id="93513-115">このシナリオでは、Exchange Online にアクセスできるデバイスを決定するために、次のフローが使われています。</span><span class="sxs-lookup"><span data-stu-id="93513-115">The following flow is used in the scenario to decide which devices can access Exchange Online:</span></span>

![デバイス アクセス フロー](./media/ConditionalAccess8-5.png)

## <a name="scenario-2-all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune"></a><span data-ttu-id="93513-117">シナリオ 2: Exchange On-premises にアクセスするすべての iOS デバイスを Intune で管理する必要がある</span><span class="sxs-lookup"><span data-stu-id="93513-117">Scenario 2: All iOS devices that access Exchange on-premises must be managed by Intune</span></span>
### <a name="scenario-requirements"></a><span data-ttu-id="93513-118">シナリオの要件</span><span class="sxs-lookup"><span data-stu-id="93513-118">Scenario requirements</span></span>
- <span data-ttu-id="93513-119">iOS を実行しているデバイスだけが Exchange On-premises にアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93513-119">Only devices that run iOS should be allowed access to Exchange on-premises.</span></span>
- <span data-ttu-id="93513-120">デバイスを Exchange へのアクセスに使用するには、それらのデバイスが Intune に登録され、コンプライアンス ポリシーのルールに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="93513-120">The devices must also be enrolled in Intune and meet the compliance policy rules before they can be used to access Exchange.</span></span>

<span data-ttu-id="93513-121">これらを実現するためには、次の設定で Exchange On-premises の条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93513-121">To accomplish this, configure the following conditional access policy for Exchange on-premises with the following settings:</span></span>

- <span data-ttu-id="93513-122">**[デバイスが Microsoft Intune に準拠していない場合や、登録されていない場合に、電子メール アプリから Exchange On-premises へのアクセスをブロックします]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="93513-122">Choose the option **Block email apps from accessing Exchange on-premises if the device is noncompliant or not enrolled in Microsoft Intune**.</span></span> <span data-ttu-id="93513-123">このオプションを選択すると、条件付きアクセス ポリシーが有効になり、Exchange にアクセスするすべてのデバイスは、Microsoft Intune に登録され、コンプライアンス ポリシーのルールに準拠していることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="93513-123">By choosing this option, you enable the conditional access policy, which requires that all devices must be enrolled in Microsoft Intune and meet the compliancy policy rules before they can access Exchange.</span></span>

- <span data-ttu-id="93513-124">Exchange Active Sync の詳細設定で、以下を作成します。</span><span class="sxs-lookup"><span data-stu-id="93513-124">For advanced Exchange Active Sync settings, create:</span></span>

  -   <span data-ttu-id="93513-125">iOS を実行するデバイスで Exchange にアクセスできるプラットフォームの例外。</span><span class="sxs-lookup"><span data-stu-id="93513-125">A platform exception that allows devices that run iOS to access Exchange.</span></span>   

  -   <span data-ttu-id="93513-126">デバイスがプラットフォームの例外ルールの対象とならない場合は Exchange へのアクセスをブロックするよう指定する既定のルール。</span><span class="sxs-lookup"><span data-stu-id="93513-126">A default rule that specifies that when a device isn't covered by the platform exception rule, it should be blocked from accessing Exchange.</span></span> <span data-ttu-id="93513-127">このルールによって、iOS を実行していないデバイスは Exchange へのアクセスがブロックされるようになります。</span><span class="sxs-lookup"><span data-stu-id="93513-127">This rule makes sure that devices that aren't running iOS are blocked from accessing Exchange.</span></span>

<span data-ttu-id="93513-128">次のフローを使用して、Exchange にアクセスできるデバイスを決定します。</span><span class="sxs-lookup"><span data-stu-id="93513-128">You use the following flow to decide which devices can access Exchange:</span></span>

![デバイス アクセス フロー](./media/ConditionalAccess8-3.png)

## <a name="scenario-3-no-android-devices-can-access-exchange-on-premises"></a><span data-ttu-id="93513-130">シナリオ 3: Android デバイスは Exchange On-premises にアクセスできない</span><span class="sxs-lookup"><span data-stu-id="93513-130">Scenario 3: No Android devices can access Exchange on-premises</span></span>
### <a name="scenario-requirements"></a><span data-ttu-id="93513-131">シナリオの要件</span><span class="sxs-lookup"><span data-stu-id="93513-131">Scenario requirements</span></span>
- <span data-ttu-id="93513-132">すべての Android デバイスに対して Exchange へのアクセスをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93513-132">All Android devices should be blocked from accessing Exchange.</span></span>
- <span data-ttu-id="93513-133">その他すべてのサポートされるデバイスは、Intune で管理されている限り Exchange にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="93513-133">All other supported devices can access Exchange, as long as they're managed by Intune.</span></span>

<span data-ttu-id="93513-134">これらを実現するためには、次の設定で Exchange On-premises の条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93513-134">To accomplish this, configure a conditional access policy for Exchange on-premises with the following settings:</span></span>

-   <span data-ttu-id="93513-135">**[デバイスが Microsoft Intune に準拠していない場合や、登録されていない場合に、電子メール アプリから Exchange On-premises へのアクセスをブロックします]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="93513-135">Choose the option **Block email apps from accessing Exchange on-premises if the device is noncompliant or not enrolled in Microsoft Intune**.</span></span> <span data-ttu-id="93513-136">このオプションを選択すると、すべてのデバイスが Intune に登録され、コンプライアンス ポリシーのルールを満たしていることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="93513-136">By choosing this option, you require that any device must be enrolled in Intune and meet the compliance policy rules.</span></span>

- <span data-ttu-id="93513-137">Exchange Active Sync の詳細設定で、以下を作成します。</span><span class="sxs-lookup"><span data-stu-id="93513-137">For advanced Exchange Active Sync settings, create:</span></span>
  -   <span data-ttu-id="93513-138">Android を実行するデバイスが Exchange にアクセスできないようにブロックするプラットフォームの例外。</span><span class="sxs-lookup"><span data-stu-id="93513-138">A platform exception that blocks devices that run Android from accessing Exchange.</span></span> <span data-ttu-id="93513-139">このルールによって、Android デバイスは Exchange へのアクセスに使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="93513-139">This rule makes sure that Android devices can't be used to access Exchange.</span></span>

  -   <span data-ttu-id="93513-140">デバイスが他のルールの対象にならない場合に、Exchange へのアクセスが許可されることを指定する既定のルール。</span><span class="sxs-lookup"><span data-stu-id="93513-140">A default rule that specifies that when a device isn't covered by other rules, it should be allowed to access Exchange.</span></span> <span data-ttu-id="93513-141">この既定のルールによって、Android 以外のプラットフォームを実行していて、Microsoft Intune でサポートされているデバイスは、Exchange へのアクセスに使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="93513-141">This default rule makes sure that devices that run platforms other than Android, but are supported by Microsoft Intune, can be used to access Exchange.</span></span> <span data-ttu-id="93513-142">ただし、それらのデバイスは Intune に登録され、コンプライアンス ポリシーのルールを満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="93513-142">They must, however, be enrolled in Intune and meet the compliance policy rules.</span></span>

<span data-ttu-id="93513-143">次のフローを使用して、Exchange にアクセスできるデバイスを決定します。</span><span class="sxs-lookup"><span data-stu-id="93513-143">You use the following flow to decide which devices can access Exchange:</span></span>

![デバイス アクセス フロー](./media/ConditionalAccess8-4.png)
