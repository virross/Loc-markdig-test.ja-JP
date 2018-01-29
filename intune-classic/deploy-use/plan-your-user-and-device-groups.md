---
title: "ユーザーとデバイス グループを計画する"
description: "組織のニーズを満たすグループを計画します。"
keywords: 
author: sanchusa
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 679399f306f3837a010cc01799c7567c1e5b5b39
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="plan-your-user-and-device-groups"></a><span data-ttu-id="bc7b6-103">ユーザーとデバイス グループを計画する</span><span class="sxs-lookup"><span data-stu-id="bc7b6-103">Plan your user and device groups</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="bc7b6-104">Intune の [グループ] を使用すると、デバイスとユーザーを柔軟に管理できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-104">Groups in Intune give you great flexibility when you're managing your devices and users.</span></span> <span data-ttu-id="bc7b6-105">次の条件に従って、組織のニーズに適合するグループをセットアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-105">You can set up groups to suit your organizational needs according to:</span></span>

- <span data-ttu-id="bc7b6-106">地理的な場所</span><span class="sxs-lookup"><span data-stu-id="bc7b6-106">geographic location</span></span>
- <span data-ttu-id="bc7b6-107">department</span><span class="sxs-lookup"><span data-stu-id="bc7b6-107">department</span></span>
- <span data-ttu-id="bc7b6-108">ハードウェアの特性</span><span class="sxs-lookup"><span data-stu-id="bc7b6-108">hardware characteristics</span></span>
- <span data-ttu-id="bc7b6-109">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="bc7b6-109">operating system</span></span>
- <span data-ttu-id="bc7b6-110">デバイスはユーザー所有のものか、それとも会社所有のものか</span><span class="sxs-lookup"><span data-stu-id="bc7b6-110">whether the device is user-owned or company-owned</span></span>


## <a name="how-intune-groups-work"></a><span data-ttu-id="bc7b6-111">Intune グループのしくみ</span><span class="sxs-lookup"><span data-stu-id="bc7b6-111">How Intune groups work</span></span>


<span data-ttu-id="bc7b6-112">次に示すのは、Intune 管理コンソールの **[グループ]** ノードの既定のビューです。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-112">This is the default view of the **Groups** node in the Intune admin console:</span></span>

![Intune コンソールの [グループ] ノードの既定のビューのスナップショット](../media/Intune_Planning_Groups_Default_small.png)

<span data-ttu-id="bc7b6-114">ポリシーがグループ上に展開されるため、グループの階層は設計上の重要な考慮事項の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-114">Policies are deployed to groups, so group hierarchy is one of your key design considerations.</span></span> <span data-ttu-id="bc7b6-115">グループを作成した後ではグループの親グループを変更できないことを理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-115">It's important to know that you cannot change a group’s parent group after you've created the group.</span></span> <span data-ttu-id="bc7b6-116">グループの設計方法は、Intune サービスの使用を開始する時点から非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-116">How you design your groups is critically important from the moment you start using the Intune service.</span></span> <span data-ttu-id="bc7b6-117">ここでは、組織のニーズに基づくグループ階層を設計する上でお勧めする方法をいくつか説明します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-117">Some recommended practices for designing a group hierarchy based on your organizational needs are described here.</span></span>

## <a name="group-membership-rules"></a><span data-ttu-id="bc7b6-118">グループ メンバーシップの規則</span><span class="sxs-lookup"><span data-stu-id="bc7b6-118">Group membership rules</span></span>

- <span data-ttu-id="bc7b6-119">1 つのグループに、ユーザーのみ、またはデバイスのみを含めることができます。両方を混ぜることはできません。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-119">A group can contain either users or devices, but not both.</span></span>

    * <span data-ttu-id="bc7b6-120">**デバイス グループ**。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-120">**Device groups**.</span></span> <span data-ttu-id="bc7b6-121">コンピューターとモバイル デバイスを含みます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-121">This includes computers and mobile devices.</span></span> <span data-ttu-id="bc7b6-122">コンピューターをグループに追加する前に、グループを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-122">Before you can add a computer to a group, it must be enrolled.</span></span> <span data-ttu-id="bc7b6-123">モバイル デバイスをグループに追加する前に、モバイル デバイスをサポートするように環境を構成し、デバイスを登録するか、Exchange ActiveSync から検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-123">Before you can add a mobile device to a group, your environment must be configured to support mobile devices, and the device must be enrolled or discovered in Exchange ActiveSync.</span></span>

    * <span data-ttu-id="bc7b6-124">**ユーザー グループ**。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-124">**User groups**.</span></span> <span data-ttu-id="bc7b6-125">グループはセキュリティ グループからのユーザーを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-125">A group can have users from security groups.</span></span> <span data-ttu-id="bc7b6-126">セキュリティ グループは Active Directory のインスタンスと同期します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-126">Security groups sync with your instance of Active Directory.</span></span> <span data-ttu-id="bc7b6-127">Active Directory と同期しない場合は、手動でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-127">If you do not sync with Active Directory, you can manually create these groups.</span></span>

- <span data-ttu-id="bc7b6-128">1 台のデバイスまたは 1 人のユーザーを、複数のグループに所属させることができます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-128">A device or a user can belong to more than one group.</span></span>

- <span data-ttu-id="bc7b6-129">グループには、次のメンバーシップの規則に基づいて追加および除外することができます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-129">A group can include and exclude members based on the following membership rules:</span></span>

    * <span data-ttu-id="bc7b6-130">**メンバーシップの基準**。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-130">**Criteria Membership**.</span></span> <span data-ttu-id="bc7b6-131">Intune がメンバーの追加または除外に使用する動的な規則です。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-131">These are dynamic rules that Intune runs to include or exclude members.</span></span> <span data-ttu-id="bc7b6-132">これらの基準では、Active Directory のローカル インスタンスと同期されたセキュリティ グループとその他の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-132">These criteria use security groups and other information synced with your local instance of Active Directory.</span></span> <span data-ttu-id="bc7b6-133">セキュリティ グループまたはデータが変更されると、Active Directory と同期したときにグループのメンバーシップも変わります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-133">When the security group or data changes, the group membership changes when you sync with Active Directory.</span></span>

    * <span data-ttu-id="bc7b6-134">**ダイレクト メンバーシップ**。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-134">**Direct Membership**.</span></span> <span data-ttu-id="bc7b6-135">明示的にメンバーを追加または除外する静的な規則です。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-135">These are static rules that explicitly add or exclude members.</span></span> <span data-ttu-id="bc7b6-136">メンバーシップの一覧は静的です。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-136">The membership list is static.</span></span>

-   <span data-ttu-id="bc7b6-137">ユーザーまたはコンピューターを含むユーザー グループまたはデバイス グループを作成するときは、Active Directory ドメイン サービス (AD DS) は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-137">Active Directory Domain Services (AD DS) is not required when you create user groups or device groups that include users or computers.</span></span> <span data-ttu-id="bc7b6-138">ただし、デバイス グループがモバイル デバイスを含む場合は、モバイル デバイスをサポートするように環境を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-138">But, for device groups to include mobile devices, your environment must be configured to support mobile devices.</span></span>

    <span data-ttu-id="bc7b6-139">また、デバイスを検出し、Intune に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-139">Additionally, the devices must be discovered and added to Intune.</span></span>

## <a name="group-relationship-rules"></a><span data-ttu-id="bc7b6-140">グループ関係のルール</span><span class="sxs-lookup"><span data-stu-id="bc7b6-140">Group relationship rules</span></span>

- <span data-ttu-id="bc7b6-141">作成する各グループには親グループが必要です。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-141">Each group you create must have a parent group.</span></span> <span data-ttu-id="bc7b6-142">グループを作成した後では、グループの親グループを変更できません。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-142">You cannot change a group’s parent group after you've created the group.</span></span>

- <span data-ttu-id="bc7b6-143">ユーザーまたはデバイスを子グループに追加する場合:</span><span class="sxs-lookup"><span data-stu-id="bc7b6-143">When you add users or devices to a child group:</span></span>

    * <span data-ttu-id="bc7b6-144">子グループは、常に親グループのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-144">The child group is always a subset of the parent group.</span></span>

    * <span data-ttu-id="bc7b6-145">子グループに追加した新規メンバーは、グループの親グループにも自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-145">New members you add to a child group are automatically added to that group’s parent group.</span></span>

    * <span data-ttu-id="bc7b6-146">親グループから除外したメンバーを子グループに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-146">You cannot add a member to a child group when that member is excluded from the parent group.</span></span>

- <span data-ttu-id="bc7b6-147">親グループのメンバーシップによって、子グループのメンバーになれるユーザーやデバイスが決まります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-147">The membership of a parent group defines the available membership for the child group.</span></span>

- <span data-ttu-id="bc7b6-148">親グループを削除すると、すべての子グループが削除されます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-148">When you delete a parent group, all child groups are deleted.</span></span>

- <span data-ttu-id="bc7b6-149">親グループにはコンテンツとポリシーを展開できますが、子グループへの展開は除きます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-149">You can deploy content and policies to a parent group but exclude the deployment to child groups.</span></span>

- <span data-ttu-id="bc7b6-150">親グループのメンバーではない特定のユーザーまたはデバイスを、子グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-150">You can add a specific user or device to a child group if the user or device is not already a member of the parent group.</span></span> <span data-ttu-id="bc7b6-151">これを行うと、子グループの新しいメンバーが親グループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-151">If you do this, the new member of the child group will be added to the parent group.</span></span>

    <span data-ttu-id="bc7b6-152">ただし、メンバーが親グループから除外された場合は、そのメンバーを子グループに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-152">However, you cannot add a member to a child group if the member is excluded from the parent group.</span></span>

- <span data-ttu-id="bc7b6-153">グループ メンバーシップは再帰的です。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-153">Group membership is recursive.</span></span> <span data-ttu-id="bc7b6-154">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-154">For example:</span></span>

    * <span data-ttu-id="bc7b6-155">**佐藤** さんは、 **Laptop Users** セキュリティ グループというグループにのみ属するメンバーです。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-155">**Pat** is a member of only one group, the **Laptop Users** security group.</span></span>

    * <span data-ttu-id="bc7b6-156">**Laptop Users** グループは、 **Approved Users** セキュリティ グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-156">The **Laptop Users** group is a member of the **Approved Users** security group.</span></span>

    * <span data-ttu-id="bc7b6-157">Intune で、**Approved Users** グループのメンバーを含む動的メンバーシップのクエリを使用するグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-157">You create a group in Intune that uses a dynamic membership query that includes the members of the **Approved Users** group.</span></span> <span data-ttu-id="bc7b6-158">結果として、Intune ユーザー グループに**佐藤**さんが追加されます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-158">The result is that your Intune user group includes **Pat**.</span></span>

> [!TIP]
> <span data-ttu-id="bc7b6-159">グループを作成するときは、ポリシーを適用する方法を考慮します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-159">When you create groups, think about how you will apply policy.</span></span> <span data-ttu-id="bc7b6-160">たとえば、デバイスのオペレーティング システムに固有のポリシー、または Active Directory サービスで既に定義してあるさまざまなロールまたは組織単位に固有のポリシーがあるものとします。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-160">For example, you might have policies that are specific to device operating systems, or policies that are specific to different roles or organizational units you've already defined in your Active Directory service.</span></span> <span data-ttu-id="bc7b6-161">iOS、Android、および Windows に固有のデバイス グループを作成すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-161">Some admins find it useful to create device groups that are specific to iOS, Android, and Windows.</span></span> <span data-ttu-id="bc7b6-162">これは、各組織ロールのユーザー グループの作成に対する追加です。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-162">This is in addition to creating user groups for each organizational role.</span></span>

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization. Then, you create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful when you name your policies, so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy, you'll want to communicate it to your users. After you create the more general groups and policies, pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## <a name="built-in-groups"></a><span data-ttu-id="bc7b6-163">組み込みグループ</span><span class="sxs-lookup"><span data-stu-id="bc7b6-163">Built-in groups</span></span>
<span data-ttu-id="bc7b6-164">Intune には、編集または削除できない組み込みのグループが 9 個用意されています。<!--maybe a screen shot would be best?--></span><span class="sxs-lookup"><span data-stu-id="bc7b6-164">Intune has nine built-in groups that you cannot edit or delete: <!--maybe a screen shot would be best?--></span></span>

-   <span data-ttu-id="bc7b6-165">**すべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="bc7b6-165">**All Users**</span></span>
    -   <span data-ttu-id="bc7b6-166">グループに属していないユーザー</span><span class="sxs-lookup"><span data-stu-id="bc7b6-166">Ungrouped Users</span></span>
-   <span data-ttu-id="bc7b6-167">**すべてのデバイス**</span><span class="sxs-lookup"><span data-stu-id="bc7b6-167">**All Devices**</span></span>
    -   <span data-ttu-id="bc7b6-168">すべてのコンピューター</span><span class="sxs-lookup"><span data-stu-id="bc7b6-168">All Computers</span></span>
    -   <span data-ttu-id="bc7b6-169">すべてのモバイル デバイス</span><span class="sxs-lookup"><span data-stu-id="bc7b6-169">All Mobile Devices</span></span>
        -   <span data-ttu-id="bc7b6-170">ダイレクト管理されているすべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="bc7b6-170">All Direct Managed Devices</span></span>
        -   <span data-ttu-id="bc7b6-171">Exchange ActiveSync で管理されているすべてのデバイス</span><span class="sxs-lookup"><span data-stu-id="bc7b6-171">All Exchange ActiveSync Managed Devices</span></span>
    -   <span data-ttu-id="bc7b6-172">すべての企業所有のデバイス</span><span class="sxs-lookup"><span data-stu-id="bc7b6-172">All Corporate-owned Devices</span></span>
    -   <span data-ttu-id="bc7b6-173">グループに属していないデバイス</span><span class="sxs-lookup"><span data-stu-id="bc7b6-173">Ungrouped Devices</span></span>

> [!NOTE]
> <span data-ttu-id="bc7b6-174">"*シンプルに*" をモットーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-174">Let your motto be: *keep it simple*.</span></span> <span data-ttu-id="bc7b6-175">以下のセクションに説明するような特定のニーズが組織にはない場合、設計を単純にし、既定のグループ構造とポリシーを採用します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-175">If your organization does not have specific needs like those described in the following sections, keep it simple and go with the default group structure and policies.</span></span> <span data-ttu-id="bc7b6-176">こうすると、長期に渡ってより管理しやすいサービスになります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-176">This will make the service more manageable in the long term.</span></span> <span data-ttu-id="bc7b6-177">ユーザーを一様に扱うことができれば、メンテナンスが容易になります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-177">Maintenance will be easier if you can treat your users uniformly.</span></span> <span data-ttu-id="bc7b6-178">グループ単位の差別化が小さければ、維持するポリシーが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-178">With little differentiation by group, you'll have fewer policies to maintain.</span></span>


### <a name="all-users-and-devices-in-your-organization"></a><span data-ttu-id="bc7b6-179">組織内のすべてのユーザーとデバイス</span><span class="sxs-lookup"><span data-stu-id="bc7b6-179">All users and devices in your organization</span></span>
<span data-ttu-id="bc7b6-180">組織内のすべてのユーザーとデバイスの親グループを定義します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-180">Define a parent group for all users and devices in your organization.</span></span> <span data-ttu-id="bc7b6-181">すべてに適用するポリシーがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-181">You are likely to have policies that will apply to all.</span></span> <span data-ttu-id="bc7b6-182">Intune の既定の**すべてのユーザー** グループと**すべてのデバイス** グループをそのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-182">You can use the Intune default **All Users** and **All devices** groups for this purpose.</span></span> <span data-ttu-id="bc7b6-183">ユーザー所有のデバイス (BYOD) を取り込む場合のグループや企業所有 (CO) デバイス用のグループなど、詳細に従ってデバイスを整理するサブグループは、**すべてのユーザー**親グループおよび**すべてのデバイス**親グループの子グループとすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-183">Sub-groups that organize devices by specifics, like a group for bring your own device (BYOD) and one for corporate-owned (CO) devices, can be child groups of the **All Users** and **All devices** parent groups.</span></span>

## <a name="customize-groups-for-your-organization"></a><span data-ttu-id="bc7b6-184">組織に合わせてグループをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="bc7b6-184">Customize groups for your organization</span></span>

### <a name="byod-and-corporate-owned-devices"></a><span data-ttu-id="bc7b6-185">BYOD および企業所有デバイス</span><span class="sxs-lookup"><span data-stu-id="bc7b6-185">BYOD and corporate-owned devices</span></span>
<span data-ttu-id="bc7b6-186">組織が、従業員に個人所有デバイスを使用することを許可するか、企業所有デバイスを提供するか、またはその両方の組み合わせとする場合、これらのデバイス カテゴリに異なるポリシーを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-186">If your organization allows employees to use their own devices, provides company-owned devices, or has a combination of both, we recommend that you apply separate policies for these categories of devices.</span></span>

<span data-ttu-id="bc7b6-187">BYOD または混在のケースでは、ローカル プライバシー規則を侵害しないようにポリシーを慎重に計画してください。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-187">In the case of BYOD or a mix, be careful to plan policies that do not infringe on local privacy regulations.</span></span> <span data-ttu-id="bc7b6-188">個人所有のデバイスを持ち込むすべてのユーザーに対する親グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-188">Create a parent group for all users who will be bringing their own devices.</span></span> <span data-ttu-id="bc7b6-189">このグループを使用して、このカテゴリに属するすべてのユーザーに適用されるポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-189">You can use this group to apply policies that are applicable to all users in this category.</span></span>

![BYOD 親グループの作成](../media/Intune_Planning_Groups_BYOD_small.png)

<span data-ttu-id="bc7b6-191">同様に、組織内の CO デバイス ユーザーに対するグループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-191">Similarly, you can create a group for the CO device users in your organization:</span></span>

![BYOD デバイスと CO デバイスの兄弟ユーザー グループ](../media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### <a name="groups-for-geographic-regions"></a><span data-ttu-id="bc7b6-193">地理的領域のグループ</span><span class="sxs-lookup"><span data-stu-id="bc7b6-193">Groups for geographic regions</span></span>
<span data-ttu-id="bc7b6-194">組織が特定の地域に対するポリシーを必要としている場合、地理的領域に基づいてグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-194">If your organization needs policies for specific regions, you can create groups based on geographic region.</span></span> <span data-ttu-id="bc7b6-195">既に Active Directory のインスタンスで作成して Azure Active Directory サービスと同期してある領域グループを基にできます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-195">You can base them on regional groups that you might have already created in your instance of Active Directory, and sync them with your Azure Active Directory service.</span></span> <span data-ttu-id="bc7b6-196">Azure Active Directory で領域グループを直接作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-196">You also can create regional groups directly in Azure Active Directory.</span></span>

<span data-ttu-id="bc7b6-197">次のスクリーンショットでは、オンプレミスの Active Directory インスタンスと同期されたグループに基づいて Intune グループを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-197">The next screenshots show you how to create Intune groups based on groups synced with your on-premises Active Directory instance.</span></span> <span data-ttu-id="bc7b6-198">この例では、"**US Users Group**" と呼ばれる Active Directory セキュリティ グループがあると想定しています。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-198">These examples assume that you have an Active Directory security group called **US Users Group**.</span></span>

<span data-ttu-id="bc7b6-199">まず、一般的な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-199">First, provide general information.</span></span>

![[グループの編集] 領域のスクリーン ショット](../media/Intune_Planning_Groups_AD_General_small.png)

<span data-ttu-id="bc7b6-201">**[メンバーシップの基準]** で、メンバーシップ規則の下で使用するセキュリティ グループとして、Active Directory と同期された "**US Users Group**" を選びます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-201">Under **Membership criteria**, select **US Users Group**, synced with Active Directory, as the security group to use under membership rules.</span></span>

![[グループの編集] ダイアログ ボックスのスクリーン ショット](../media/Intune_Planning_Groups_AD_Criteria_small.png)

<span data-ttu-id="bc7b6-203">入力内容を確認し、**[完了]** を選んでグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-203">Review your entries, and then choose **Finish** to create the group.</span></span>

![[グループの編集] ダイアログ ボックスのスクリーン ショット](../media/Intune_Planning_Groups_AD_Summary_small.png)

<span data-ttu-id="bc7b6-205">この例では、中東とアジアの **MEA**と呼ばれるグループも作成しました。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-205">In our example, we’ve also created a group called **MEA**, for the Middle East and Asia.</span></span>

> [!NOTE]
> <span data-ttu-id="bc7b6-206">グループのメンバーシップがセキュリティ グループ メンバーシップに基づいて設定されていない場合は、Intune ライセンスをグループ メンバーに割り当てたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-206">If group membership is not populated based on security group membership, make sure that you have assigned Intune licenses to group members.</span></span>

### <a name="groups-for-specific-hardware"></a><span data-ttu-id="bc7b6-207">特定のハードウェア用のグループ</span><span class="sxs-lookup"><span data-stu-id="bc7b6-207">Groups for specific hardware</span></span>
<span data-ttu-id="bc7b6-208">特定のハードウェアの種類に適用するポリシーが組織で必要な場合、この要件に基づくグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-208">If your organization requires policies that apply to specific hardware types, you can create groups based on this requirement.</span></span> <span data-ttu-id="bc7b6-209">Active Directory のオンプレミスのインスタンスで既に作成してある特定のグループを基にしてポリシーを作成した後、Azure Active Directory と同期することができます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-209">You can base the policies on specific groups that you have already created in your on-premises instance of Active Directory, and then sync them with Azure Active Directory.</span></span> <span data-ttu-id="bc7b6-210">Azure Active Directory でグループを直接作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-210">You also can create groups directly in Azure Active Directory.</span></span> <span data-ttu-id="bc7b6-211">この例では、"**US Users Group**" を "**Laptop Users**" グループに対する親グループとして使用します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-211">In this example, we use **US Users Group** as the parent group for the **Laptop Users** group.</span></span>

![[セキュリティ グループの選択] ダイアログ ボックス](../media/Intune_Planning_Groups_Laptop_small.png)

<span data-ttu-id="bc7b6-213">この時点で、グループの階層構造は次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-213">At this point, your group's hierarchy should look similar to the next screenshot.</span></span> <span data-ttu-id="bc7b6-214">Intune グループ "**Laptop Users**" にメンバーが含まれることがわかります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-214">You can see that there are now members in the Intune group **Laptop Users**.</span></span> <span data-ttu-id="bc7b6-215">このグループに適用されるどのポリシーも、米国地域の BYOD ノート PC ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-215">Any policies applied to this group will be applied to BYOD laptop users from the U.S. region.</span></span>

![ノート PC ユーザー グループの表示](../media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### <a name="groups-for-specific-operating-systems"></a><span data-ttu-id="bc7b6-217">特定のオペレーティング システム用のグループ</span><span class="sxs-lookup"><span data-stu-id="bc7b6-217">Groups for specific operating systems</span></span>
<span data-ttu-id="bc7b6-218">Android、iOS、Windows などの特定のオペレーティング システムに適用するポリシーが組織で必要な場合は、この要件に基づくグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-218">If your organization requires policies that apply to specific operating systems like Android, iOS, or Windows, you can create groups based on this requirement.</span></span> <span data-ttu-id="bc7b6-219">前の例のように、Active Directory のオンプレミスのインスタンスで既に作成してある OS 固有のグループを基にしてポリシーを作成し、Azure Active Directory と同期することができます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-219">As in earlier examples, you can base them on OS-specific groups that you have already created in your on-premises instance of Active Directory, and sync them with Azure Active Directory.</span></span> <span data-ttu-id="bc7b6-220">Azure Active Directory のインスタンスで直接作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-220">You also can create them directly in your instance of Azure Active Directory.</span></span>

<span data-ttu-id="bc7b6-221">前の例と同じ方法を使用することで、特定のオペレーティング システム プラットフォームを使用するユーザー <!--devices?-->に基づいてグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-221">By using the same method from earlier examples, you can create groups based on users <!--devices?--> who use specific operating system platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="bc7b6-222">複数のモバイル プラットフォームまたはオペレーティング システムを使用しているユーザーがいるものの、Android ユーザー、iOS ユーザー、Windows ユーザーとして自動的に分類する方法がない場合、デバイス レベルでポリシーを適用することを検討します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-222">If you have users who use multiple mobile platforms or operating systems and you do not have an automated way to categorize users as Android users, iOS users, or Windows users, consider applying policies at the device level.</span></span> <span data-ttu-id="bc7b6-223">このようにすると、オペレーティング システムに固有のポリシーを適用する柔軟性が向上します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-223">This will give you more flexibility to apply policies that are specific to an operating system.</span></span>
>
> <span data-ttu-id="bc7b6-224">デバイスのオペレーティング システムに基づくグループを動的にプロビジョニングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-224">You cannot provision groups dynamically based on the operating system of the device.</span></span> <span data-ttu-id="bc7b6-225">代わりに、Active Directory または Azure Active Directory のセキュリティ グループを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-225">Instead, do this by using Active Directory or Azure Active Directory security groups.</span></span>

![ラップトップ ユーザー グループ](../media/Intune_Planning_Groups_OS_Hierachy_small.png)

<span data-ttu-id="bc7b6-227">これらの組織の要件に基づいて、すべてのユーザー グループを設定した後、グループ階層は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-227">After all of your user groups are populated based on your organizational requirements, your group hierarchy should look something like this:</span></span>

![グループ階層ビュー](../media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

<span data-ttu-id="bc7b6-229">この階層を使用して、組織のポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-229">You can use this hierarchy to apply the organization's policies.</span></span>

### <a name="device-groups"></a><span data-ttu-id="bc7b6-230">Device groups</span><span class="sxs-lookup"><span data-stu-id="bc7b6-230">Device groups</span></span>
<span data-ttu-id="bc7b6-231">次に示すように、BYOD のシナリオで、従業員が所有するすべてのデバイスを含む広範なグループから始めて、デバイス用の類似したグループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-231">You also can create similar groups for devices as shown here, starting with a broad group that includes all employee-owned devices, for the BYOD scenario.</span></span>

![[グループの作成] ダイアログ ボックス](../media/Intune_Planning_Groups_Device_General_small.png)

<span data-ttu-id="bc7b6-233">グループにすべての BYO デバイスが含まれるように、**[すべてのデバイス (コンピューターとモバイル)]** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-233">Make sure that you select **All devices (computers and mobile)** so that the group will include all BYO devices:</span></span>

![[メンバーシップの基準の定義] ページ](../media/Intune_Planning_Groups_Device_Criteria_small.png)

<span data-ttu-id="bc7b6-235">入力内容を確認し、**[完了]** を選んで BYOD グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-235">Review your entries, and then choose **Finish** to create the BYOD group.</span></span>

![[グループの作成] ダイアログ ボックス](../media/Intune_Planning_Groups_Device_Summary_small.png)

<span data-ttu-id="bc7b6-237">デバイス グループの作成を続けて、ユーザー グループ階層と同様のデバイス グループの階層を完成させます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-237">Continue to create device groups until you have a device group hierarchy that is similar to the user group hierarchy.</span></span> <span data-ttu-id="bc7b6-238">完成すると、Intune コンソールでグループ ノードは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-238">Your group node in the Intune console will look similar to this:</span></span>

![Intune グループ階層ビュー](../media/Intune_Groups_Hierarchy_Final_Small.png)

## <a name="group-hierarchies-and-naming-conventions"></a><span data-ttu-id="bc7b6-240">グループ階層と名前付け規則</span><span class="sxs-lookup"><span data-stu-id="bc7b6-240">Group hierarchies and naming conventions</span></span>
<span data-ttu-id="bc7b6-241">ポリシーの管理を容易にするために、各ポリシーに適用される目的、プラットフォーム、範囲に基づいて名前を付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-241">To make policy management easier, we recommend that you name each policy according to the purpose, platform, and scope to which you apply it.</span></span> <span data-ttu-id="bc7b6-242">ポリシーを適用する準備をしたときに作成したグループ構造に従った名前付け標準を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-242">Use a naming standard that follows the group structure that you created when you prepared to apply your policies.</span></span>

<span data-ttu-id="bc7b6-243">たとえば、適用範囲が全社、Android モバイル デバイス、米国地域レベルの Android ポリシーは、**CO_US_Mob_Android_General** と名付けることができます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-243">For instance, for an Android policy that applies to all corporate, Android, mobile devices at the U.S. regional level, you might name the policy **CO_US_Mob_Android_General**.</span></span>

![Android 用のポリシーの作成](../media/Intune_planning_policy_android_small.png)

<span data-ttu-id="bc7b6-245">この方法でポリシーに名前を付けると、**[ポリシー]** ノードから、ポリシー、その使用目的、範囲を次のようにすばやく識別できます。</span><span class="sxs-lookup"><span data-stu-id="bc7b6-245">When you name your policies this way, you can quickly identify policies and their intended use and scope in the **Policies** node, like this:</span></span>

![Intune ポリシー一覧](../media/Intune_planning_policy_view_small.png)

## <a name="next-steps"></a><span data-ttu-id="bc7b6-247">次の手順</span><span class="sxs-lookup"><span data-stu-id="bc7b6-247">Next steps</span></span>
[<span data-ttu-id="bc7b6-248">グループの作成</span><span class="sxs-lookup"><span data-stu-id="bc7b6-248">Create groups</span></span>](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
