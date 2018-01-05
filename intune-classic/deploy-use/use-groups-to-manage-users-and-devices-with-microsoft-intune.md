---
title: "ユーザーとデバイスの管理にグループを使用する"
description: "グループ ワークスペースを使用してグループを作成および管理します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7137e8e95375f9cdb2d25ddd632b7e775fc8bbd5
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="use-groups-to-manage-users-and-devices-in-microsoft-intune"></a><span data-ttu-id="10364-103">Microsoft Intune でユーザーとデバイスの管理にグループを使用する</span><span class="sxs-lookup"><span data-stu-id="10364-103">Use groups to manage users and devices in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="10364-104">ここでは、Intune でグループを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10364-104">This topic describes how to create groups in Intune.</span></span> <span data-ttu-id="10364-105">また、今後数か月間におけるグループ管理の変更予定についても説明します。</span><span class="sxs-lookup"><span data-stu-id="10364-105">It also provides information about how the management of groups is going to change over the coming months.</span></span> 

>[!IMPORTANT]
>
><span data-ttu-id="10364-106">Intune ポータルでグループ ワークスペースを開き、Azure Active Directory (Azure AD) ポータルへのリンクを確認すると、Intune でのグループ管理に*新しい* Azure AD セキュリティ グループのアプローチが使用されています (「[Azure Active Directory グループへの移行](migrating-groups-to-azure-active-directory.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="10364-106">If you open the Groups workspace in the Intune portal and see a link to the Azure active directory (Azure AD) portal, then you are using the *new* Azure AD security groups approach to group management in Intune, described in [Migrating groups to Azure Active Directory](migrating-groups-to-azure-active-directory.md).</span></span> <span data-ttu-id="10364-107">グループを作成して管理するには、Azure AD ポータルへのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="10364-107">Click the link to the Azure AD portal to create and manage your groups.</span></span>
>
>![Azure グループの管理へのリンクのスクリーン ショット](../media/groups-link-azure.png) 
>
><span data-ttu-id="10364-109">Azure AD ポータルへのリンクが表示されない場合は、まだ*現在の*グループ管理アプローチを使用しています (このトピックの「[グループの作成](#create-groups)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="10364-109">If you do not see the link to the Azure AD portal, you are still using the *current* approach to group management, described in [Create groups](#create-groups) in this topic.</span></span>

<span data-ttu-id="10364-110">このトピックでは、Intune 管理コンソールで Intune グループを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10364-110">This topic describes how to create Intune groups in the Intune administration console.</span></span>

<span data-ttu-id="10364-111">Microsoft Intune 管理コンソールの **[グループ]** ワークスペースで、グループを作成して管理できます。</span><span class="sxs-lookup"><span data-stu-id="10364-111">You can create and manage groups in the **Groups** workspace in the Microsoft Intune admin console.</span></span> <span data-ttu-id="10364-112">**[グループの概要]** ページに表示される状態の概要を参照して、注意が必要な問題を特定し、優先順位を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="10364-112">The **Groups Overview** page shows status summaries that can help you identify and prioritize issues that require your attention.</span></span> <span data-ttu-id="10364-113">状態の概要には以下の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10364-113">Status summaries cover these areas:</span></span>

-   <span data-ttu-id="10364-114">アラート</span><span class="sxs-lookup"><span data-stu-id="10364-114">Alerts</span></span>
-   <span data-ttu-id="10364-115">ソフトウェア更新プログラム</span><span class="sxs-lookup"><span data-stu-id="10364-115">Software updates</span></span>
-   <span data-ttu-id="10364-116">Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="10364-116">Endpoint Protection</span></span>
-   <span data-ttu-id="10364-117">ポリシー</span><span class="sxs-lookup"><span data-stu-id="10364-117">Policy</span></span>
-   <span data-ttu-id="10364-118">ソフトウェアの管理</span><span class="sxs-lookup"><span data-stu-id="10364-118">Software management</span></span>

<span data-ttu-id="10364-119">また、選択されたグループのメンバーの問題を特定して解決しやすいよう、グループ階層にも状態の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10364-119">Your group hierarchy also shows status summaries to help you identify and resolve problems for members of a selected group.</span></span>

## <a name="create-groups"></a><span data-ttu-id="10364-120">グループの作成</span><span class="sxs-lookup"><span data-stu-id="10364-120">Create groups</span></span>

> [!TIP]
> <span data-ttu-id="10364-121">グループを作成するときは、ポリシーを適用する方法を考慮します。</span><span class="sxs-lookup"><span data-stu-id="10364-121">When you create groups, consider how you will apply policies.</span></span> <span data-ttu-id="10364-122">たとえば、デバイスのオペレーティング システムに固有のポリシー、組織のさまざまなロールに固有のポリシー、Active Directory で既に定義されている組織単位に固有のポリシーなどがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="10364-122">For example, you might have policies that are specific to a device operating system, and policies that are specific to different roles in your organization, or to organizational units that you've already defined in Active Directory.</span></span> <span data-ttu-id="10364-123">iOS、Android、Windows で異なるデバイス グループや、組織のロールごとのユーザー グループを作成すると、便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="10364-123">It might be useful to have separate device groups for iOS, Android, and Windows, as well as a user group for each organizational role.</span></span>
>
> <span data-ttu-id="10364-124">また通常は、すべてのグループとデバイスに適用される既定のポリシーを作成して、組織の基本的なコンプライアンス要件を確立します。</span><span class="sxs-lookup"><span data-stu-id="10364-124">You'll probably also want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization.</span></span> <span data-ttu-id="10364-125">その後は、ユーザーやデバイスの広範なカテゴリに個別のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="10364-125">Then, you can create more specific policies for the broadest categories of users and devices.</span></span> <span data-ttu-id="10364-126">たとえば、デバイスのオペレーティング システムごとに電子メール ポリシーを作成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="10364-126">For example, you might create email policies for each of the device operating systems.</span></span>
>
> <span data-ttu-id="10364-127">後で簡単に識別できるように、注意してポリシーに名前を付けてください。</span><span class="sxs-lookup"><span data-stu-id="10364-127">Be careful when you name your policies so that you can easily identify them later.</span></span> <span data-ttu-id="10364-128">たとえば、"**会社全体の WP 電子メール ポリシー**" などはわかりやすいポリシー名の例です。</span><span class="sxs-lookup"><span data-stu-id="10364-128">For example, a good descriptive policy name is **WP Email Policy for Entire Company**.</span></span>
>
> <span data-ttu-id="10364-129">制限の厳しいポリシーを作成する場合は、その都度ユーザーとのやり取りが必要になります。</span><span class="sxs-lookup"><span data-stu-id="10364-129">Each time you create a restrictive policy, you'll want to communicate it to your users.</span></span> <span data-ttu-id="10364-130">一般的なグループとポリシーを作成した後でより小さなグループを作成する場合は、不要なやり取りを減らせるように、注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="10364-130">After you create the more general groups and policies, pay attention to how you create smaller groups, so that you can reduce unnecessary communication.</span></span>

## <a name="to-create-a-device-group"></a><span data-ttu-id="10364-131">デバイス グループを作成するには</span><span class="sxs-lookup"><span data-stu-id="10364-131">To create a device group</span></span>

1.  <span data-ttu-id="10364-132">Intune 管理コンソールで、**[グループ]** &gt; **[概要]** &gt; **[グループの作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-132">In the Intune admin console, choose **Groups** &gt; **Overview** &gt; **Create Group**.</span></span>

2.  <span data-ttu-id="10364-133">グループの名前と説明 (省略可能) を入力し、デバイス グループを親グループとして選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-133">Enter a name and a description (optional) for the group, and then select a device group as the parent group.</span></span> <span data-ttu-id="10364-134">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-134">Choose **Next**.</span></span>

3.  <span data-ttu-id="10364-135">**[メンバーシップの基準の定義]** ページで、グループに含めるデバイスの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-135">On the **Define Membership Criteria** page, select the type of devices to include in the group.</span></span> <span data-ttu-id="10364-136">選択したデバイスの種類に基づく追加のグループ構成オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="10364-136">You have additional group configuration options based on the types of devices you choose to include:</span></span>

    -   <span data-ttu-id="10364-137">**コンピューター**。</span><span class="sxs-lookup"><span data-stu-id="10364-137">**Computer**.</span></span> <span data-ttu-id="10364-138">親グループのすべてのメンバーを含めるかどうか、追加または除外する組織単位、追加または除外するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-138">Select whether to include all members of the parent group; the organizational units you want to include or exclude; and domains you want to include or exclude.</span></span> <span data-ttu-id="10364-139">コンピューターの組織単位とドメインの情報は、インベントリから取得できます。</span><span class="sxs-lookup"><span data-stu-id="10364-139">You can get organizational unit and domain information for a computer from inventory.</span></span>

    -   <span data-ttu-id="10364-140">**モバイル**。</span><span class="sxs-lookup"><span data-stu-id="10364-140">**Mobile**.</span></span> <span data-ttu-id="10364-141">Intune で管理されているモバイル デバイスのみ、Exchange ActiveSync で管理されているモバイル デバイスのみ、またはその両方を含めるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-141">Select whether to include mobile devices that are managed by Intune, mobile devices that are managed by Exchange ActiveSync, or both.</span></span>

    -   <span data-ttu-id="10364-142">**すべてのデバイス**。</span><span class="sxs-lookup"><span data-stu-id="10364-142">**All devices**.</span></span> <span data-ttu-id="10364-143">条件に基づいて除外せず、すべてのデバイスを含めます。</span><span class="sxs-lookup"><span data-stu-id="10364-143">This option includes all devices, with no exclusions based on any criteria.</span></span>

4.  <span data-ttu-id="10364-144">**[ダイレクト メンバーシップの定義]** ページで、**[参照]** をクリックして追加または除外する個々のデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-144">On the **Define Direct Membership** page, choose **Browse** to select individual devices to include or exclude.</span></span> <span data-ttu-id="10364-145">指定した親グループに含まれないデバイスを選択すると、そのデバイスは親グループに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="10364-145">If you select devices that are not in the parent group that you specified, Intune automatically adds those devices to the parent group.</span></span>

5.  <span data-ttu-id="10364-146">**[概要]** ページで選択内容を確認して、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10364-146">On the **Summary** page, review your selections, and then choose **Finish**.</span></span>

<span data-ttu-id="10364-147">新しく作成したグループは、**[グループ]** ワークスペースの **[グループ]** 一覧の、親グループの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="10364-147">The newly created group is shown in the **Groups** list, in the **Groups** workspace, under the parent group.</span></span> <span data-ttu-id="10364-148">ここからは、グループを編集または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="10364-148">That's also where you can edit or delete the group.</span></span>

## <a name="to-create-a-user-group"></a><span data-ttu-id="10364-149">ユーザー グループを作成するには</span><span class="sxs-lookup"><span data-stu-id="10364-149">To create a user group</span></span>

1.  <span data-ttu-id="10364-150">Intune 管理コンソールで、**[グループ]** &gt; **[概要]** &gt; **[グループの作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-150">In the Intune admin console, choose **Groups** &gt; **Overview** &gt; **Create Group**.</span></span>

2.  <span data-ttu-id="10364-151">グループの名前と説明 (省略可能) を入力し、ユーザー グループを親グループとして選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-151">Enter a name and a description (optional) for the group, and then select a user group as the parent group.</span></span> <span data-ttu-id="10364-152">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-152">Choose **Next**.</span></span>

3.  <span data-ttu-id="10364-153">**[メンバーシップの基準の定義]** ページで、親グループのすべてのメンバーを含めるか、空のグループから始めるかを選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-153">On the **Define Membership Criteria** page, choose whether to include all members of the parent group or to start with an empty group.</span></span> <span data-ttu-id="10364-154">次に、[Office 365 管理センター](http://go.microsoft.com/fwlink/?LinkId=698854)で手動で構成したユーザーまたは Active Directory から同期したユーザーのセキュリティ グループに基づいて、メンバーを追加または除外します。</span><span class="sxs-lookup"><span data-stu-id="10364-154">Then, include or exclude members based on the security groups of users that you either manually configure in the [Office 365 admin center](http://go.microsoft.com/fwlink/?LinkId=698854), or sync from Active Directory.</span></span> <span data-ttu-id="10364-155">セキュリティ グループのメンバーシップを変更すると、そのセキュリティ グループに基づくユーザー グループのメンバーシップも変わります。</span><span class="sxs-lookup"><span data-stu-id="10364-155">If the membership of a security group changes, the membership of user groups based on that security group also might change.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="10364-156">現時点では、グループに特定のセキュリティ グループまたはマネージャー グループのメンバーが含まれる場合、一部のグループからメンバーを除外すると、最初に含まれていたメンバーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="10364-156">Currently, if your group includes members from specific security groups or manager groups and you exclude members from some groups, the members you initially included will be removed.</span></span> <span data-ttu-id="10364-157">追加するメンバーと除外するメンバー両方のグループを作成するには、追加するメンバーの親グループを最初に作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10364-157">To create a group that has both included members and excluded members, we recommend that first you create a parent group that has the included members.</span></span> <span data-ttu-id="10364-158">次に、その親グループの子グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="10364-158">Then, create a child group for that parent group.</span></span> <span data-ttu-id="10364-159">新しい子グループで、除外するメンバーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="10364-159">In the new child group, list the excluded members.</span></span> <span data-ttu-id="10364-160">その後、その子グループを使用して、Intune のポリシー、プロファイル、アプリの配信を管理します。</span><span class="sxs-lookup"><span data-stu-id="10364-160">Then, use that child group to manage Intune policies, profiles, and app distribution.</span></span>

    > [!NOTE]
    > <span data-ttu-id="10364-161">Azure ポータルでは、ユーザーの報告先のマネージャーに基づいてグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="10364-161">In the Azure portal, you can create groups based on the managers who users report to.</span></span> <span data-ttu-id="10364-162">この種のグループは動的で、Azure Active Directory でマネージャーのチームの従業員が追加または削除されると変更されます。</span><span class="sxs-lookup"><span data-stu-id="10364-162">This type of group is dynamic, and it will change as employees are added to or removed from a manager's team in Azure Active Directory.</span></span> <span data-ttu-id="10364-163">マネージャーの名前に基づいて Azure のグループを作成する方法については、「[属性を使用した高度なルールの作成](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)」の「**“Manager” グループとしてグループを構成するには**」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="10364-163">How to create an Azure group based on manager name is described in [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/), in the section **To configure a group as a “Manager” group**.</span></span>

4.  <span data-ttu-id="10364-164">**[ダイレクト メンバーシップの定義]** ページで、**[参照]** をクリックして追加または除外する個々のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-164">On the **Define Direct Membership** page, choose **Browse** to select individual users to include or exclude.</span></span> <span data-ttu-id="10364-165">指定した親グループに含まれていないユーザーを選択した場合、そのユーザーは親グループに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="10364-165">If you select users that are not in the parent group that you specified, those devices are automatically added to the parent group.</span></span> <span data-ttu-id="10364-166">ユーザーを手動で追加するオプションは、**[メンバーの選択]** ダイアログ ボックスの一番下にあります。</span><span class="sxs-lookup"><span data-stu-id="10364-166">The option to manually add a user is at the bottom of the **Select Members** dialog box.</span></span> <span data-ttu-id="10364-167">これはまだ登録済みのデバイスのないユーザーを追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="10364-167">This is helpful if you want to add a user who does not yet have an enrolled device.</span></span>

5.  <span data-ttu-id="10364-168">**[概要]** ページで選択内容を確認して、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10364-168">On the **Summary** page, review your selections, and then choose **Finish**.</span></span>

<span data-ttu-id="10364-169">新しく作成したグループは、**[グループ]** ワークスペースの **[グループ]** 一覧の、親グループの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="10364-169">The newly created group is shown in the **Groups** list, in the **Groups** workspace, under the parent group.</span></span> <span data-ttu-id="10364-170">ここからは、グループを編集または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="10364-170">That's also where you can edit or delete the group.</span></span>

> [!TIP]
> <span data-ttu-id="10364-171">セキュリティ グループは、ユーザー グループを設定するときに使用するのに適したリソースです。</span><span class="sxs-lookup"><span data-stu-id="10364-171">Security groups are a good resource to use when you populate user groups.</span></span> <span data-ttu-id="10364-172">セキュリティ グループではどのユーザーがどのリソースにアクセスできるかが定義されているので、セキュリティ グループは Intune ユーザー グループに変換できます。</span><span class="sxs-lookup"><span data-stu-id="10364-172">Because security groups define who can access which resources, security groups can translate well to Intune user groups.</span></span> <span data-ttu-id="10364-173">Active Directory から Azure Active Directory に同期されたセキュリティ グループや、Office 365 管理センター、または Azure ポータルで Azure Active Directory に直接作成されたセキュリティ グループは、Intune でユーザー グループを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="10364-173">Security groups that are synced from Active Directory to Azure Active Directory, or which you create directly in Azure Active Directory through the Office 365 admin center or the Azure portal are available to you to use when you create user groups in Intune.</span></span>

## <a name="filter-admin-views-by-role"></a><span data-ttu-id="10364-174">ロールで管理ビューをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="10364-174">Filter admin views by role</span></span>
<span data-ttu-id="10364-175">フィルター処理されたグループ ビューでは、IT 管理者が見ることのできる内容を管理者のロールに基づいて調整できます。</span><span class="sxs-lookup"><span data-stu-id="10364-175">In filtered group views, you can tailor what an IT admin can see based on the admin's role.</span></span> <span data-ttu-id="10364-176">また、各 IT 管理者が管理できるグループを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="10364-176">You also can restrict which groups each IT admin can manage.</span></span> <span data-ttu-id="10364-177">これは次のような場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="10364-177">This can be useful when:</span></span>

-   <span data-ttu-id="10364-178">IT 管理者が特定のユーザーとデバイスだけにアイテムを展開できるようにする</span><span class="sxs-lookup"><span data-stu-id="10364-178">You want your IT admins to be able to deploy items only to specific users and devices</span></span>
-   <span data-ttu-id="10364-179">IT 管理者が管理に関連するグループのみを表示できるようにする</span><span class="sxs-lookup"><span data-stu-id="10364-179">You want your IT admins to see only the groups that are relevant to that admin</span></span>

<span data-ttu-id="10364-180">サービス管理者用のフィルター選択されたグループ ビューは、Intune 管理コンソールで構成できます。</span><span class="sxs-lookup"><span data-stu-id="10364-180">You can configure filtered group views for service admins in the Intune admin console.</span></span> <span data-ttu-id="10364-181">詳細については、「[Microsoft Intune を使い始める前に](/intune/supported-devices-browsers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10364-181">For details, see [What to know before you start Microsoft Intune](/intune/supported-devices-browsers).</span></span>

<span data-ttu-id="10364-182">サービス管理者用のフィルター処理されたグループ ビューが設定された後では、管理者は、ソフトウェアまたはポリシーの展開時またはレポートの実行時に、指定されているグループのみを表示および選択できます。</span><span class="sxs-lookup"><span data-stu-id="10364-182">After you set up filtered group views for a service admin, when the admin deploys software or policies, or runs reports, the admin can view and select only the groups that you specified.</span></span> <span data-ttu-id="10364-183">管理コンソールの次のページでは状態情報も表示されません。</span><span class="sxs-lookup"><span data-stu-id="10364-183">The admin also doesn't see status information on these pages of the admin console:</span></span>

-   <span data-ttu-id="10364-184">**システムの概要**</span><span class="sxs-lookup"><span data-stu-id="10364-184">**System Overview**</span></span>
-   <span data-ttu-id="10364-185">**グループの概要**</span><span class="sxs-lookup"><span data-stu-id="10364-185">**Groups Overview**</span></span>
-   <span data-ttu-id="10364-186">**Endpoint Protection の概要**</span><span class="sxs-lookup"><span data-stu-id="10364-186">**Endpoint Protection Overview**</span></span>
-   <span data-ttu-id="10364-187">**アラートの概要**</span><span class="sxs-lookup"><span data-stu-id="10364-187">**Alerts Overview**</span></span>
-   <span data-ttu-id="10364-188">**ソフトウェアの概要**</span><span class="sxs-lookup"><span data-stu-id="10364-188">**Software Overview**</span></span>
-   <span data-ttu-id="10364-189">**ポリシーの概要**</span><span class="sxs-lookup"><span data-stu-id="10364-189">**Policy Overview**</span></span>

### <a name="to-create-a-filtered-group-view"></a><span data-ttu-id="10364-190">フィルター選択されたグループ ビューを作成するには</span><span class="sxs-lookup"><span data-stu-id="10364-190">To create a filtered group view</span></span>

1.  <span data-ttu-id="10364-191">Intune 管理コンソールで、**[管理者]** &gt; **[管理者の管理]** &gt; **[サービス管理者]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-191">In the Intune admin console, choose **Admin** &gt; **Administrator Management** &gt; **Service Administrators**.</span></span>

2.  <span data-ttu-id="10364-192">フィルター処理されたグループ ビューを作成するサービス管理者を選択し、**[グループの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-192">Select the service admin who you want to create a filtered group view for, and then choose **Manage Groups**.</span></span>

3.  <span data-ttu-id="10364-193">**[このサービスの管理者に表示するグループの選択]** ダイアログ ボックスで、サービス管理者がアクセスできるグループを追加し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10364-193">In the **Select the groups that will be visible to this service administrator** dialog box, add the groups that the service admin will be able to access, and then choose **OK**.</span></span>

<span data-ttu-id="10364-194">フィルター選択されたグループ ビューをセットアップした後は、IT 管理者は指定されたグループしか表示および選択できなくなります。</span><span class="sxs-lookup"><span data-stu-id="10364-194">After you've set up the filtered group views, the IT admin will be able to view and select only the groups you've indicated.</span></span>

## <a name="manage-your-groups"></a><span data-ttu-id="10364-195">グループを管理する</span><span class="sxs-lookup"><span data-stu-id="10364-195">Manage your groups</span></span>
<span data-ttu-id="10364-196">グループを作成した後は、組織のニーズに合わせてグループを継続して管理できます。</span><span class="sxs-lookup"><span data-stu-id="10364-196">After you create your groups, you can continue to manage them according to the needs of your organization.</span></span>

<span data-ttu-id="10364-197">グループを編集して、名前と説明や、グループに属するユーザーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="10364-197">You can edit your group to change its name or description, or who belongs to the group.</span></span>

<span data-ttu-id="10364-198">組織のニーズを満たさなくなったグループを削除できます。</span><span class="sxs-lookup"><span data-stu-id="10364-198">You can delete a group that no longer serves the needs of your organization.</span></span> <span data-ttu-id="10364-199">グループを削除しても、そのグループに属するユーザーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="10364-199">Deleting a group does not delete the users that belong to that group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="10364-200">次の手順</span><span class="sxs-lookup"><span data-stu-id="10364-200">Next steps</span></span>
<span data-ttu-id="10364-201">グループとポリシーを設定した後、**[想定値]** と **[状態]** を見て、設計後の実際の影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="10364-201">After you set up your groups and policies, review **Intended Value** and **Status** to check the practical implications of your design.</span></span>

### <a name="to-check-your-design"></a><span data-ttu-id="10364-202">設計を確認するには</span><span class="sxs-lookup"><span data-stu-id="10364-202">To check your design</span></span>

1. <span data-ttu-id="10364-203">デバイス グループから任意のデバイスを選択し、ページ上部の情報のカテゴリを参照します。</span><span class="sxs-lookup"><span data-stu-id="10364-203">Select any device from a device group and browse through the categories of information at the top of the page.</span></span>
2. <span data-ttu-id="10364-204">**[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="10364-204">Choose **Policy**.</span></span> <span data-ttu-id="10364-205">このスクリーン ショットのように Android デバイスのポリシー設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10364-205">You'll see something like this screenshot of an Android device's policy settings.</span></span>

![Android の設定ポリシーの例](../media/Intune-Device-Policy-v.2.jpg)

<span data-ttu-id="10364-207">各ポリシーには、 **[想定値]** と **[状態]**があります。</span><span class="sxs-lookup"><span data-stu-id="10364-207">Each policy has an **Intended Value** and a **Status**.</span></span> <span data-ttu-id="10364-208">[想定値] は、ポリシーを割り当てるときに実現しようとした内容です。</span><span class="sxs-lookup"><span data-stu-id="10364-208">The intended value is what you intended to achieve when you assigned the policy.</span></span> <span data-ttu-id="10364-209">[状態] は、ハードウェアとオペレーティング システムの制限事項と要件だけでなく、デバイスに適用されるすべてのポリシーがまとめて考慮されたときに実現される内容です。</span><span class="sxs-lookup"><span data-stu-id="10364-209">The status is what you achieve when all of the policies that apply to the device, as well as the restrictions and requirements of the hardware and operating system are considered together.</span></span> <span data-ttu-id="10364-210">スクリーンショットには、よくわかる 2 つの例が示されています。</span><span class="sxs-lookup"><span data-stu-id="10364-210">In this screenshot you can see two clear examples:</span></span>

-   <span data-ttu-id="10364-211">**[想定値]** 列に表示されているように、 **[単純なパスワードを使用する]**が **[はい]** に設定されていますが、その **[状態]** は **[該当なし]**になっています。</span><span class="sxs-lookup"><span data-stu-id="10364-211">**Allow simple passwords** is set to **Yes**, as shown in the **Intended Value** column, but its **Status** is **Not applicable**.</span></span> <span data-ttu-id="10364-212">これは、Android デバイスでは単純なパスワードがサポートされていないことが原因です。</span><span class="sxs-lookup"><span data-stu-id="10364-212">This is because simple passwords are not supported for Android devices.</span></span>
-   <span data-ttu-id="10364-213">同様に、拡張ポリシー アイテム **[iOS デバイス用電子メールの設定]** は、このデバイスが Android デバイスであるため適用されません。</span><span class="sxs-lookup"><span data-stu-id="10364-213">Similarly, the expanded policy item **Email settings for iOS devices** is not applied to this device because it is an Android device.</span></span>

> [!NOTE]
> <span data-ttu-id="10364-214">制限レベルが異なる 2 つのポリシーを同じデバイスまたはユーザーに適用すると、より厳しい方のポリシーが実際に適用されます。</span><span class="sxs-lookup"><span data-stu-id="10364-214">Remember that when two policies that have different levels of restriction apply to the same device or user, the more restrictive policy applies in practice.</span></span>
