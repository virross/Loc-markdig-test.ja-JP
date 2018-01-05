---
title: "Azure Active Directory グループへ移行する"
description: "Intune から Azure AD へのグループの移行方法"
keywords: 
author: arob98
ms.author: angrobe
manager: angerobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: b4716a542c7bfb4b735a1bad68a1cbb226f5b1f7
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="a-new-way-of-using-groups-in-intune"></a><span data-ttu-id="fad5e-103">Intune でグループを使う新しい方法</span><span class="sxs-lookup"><span data-stu-id="fad5e-103">A new way of using groups in Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="fad5e-104">ユーザーからのフィードバックに対応して、Microsoft Intune でグループを操作する方法にいくつかの変更が行われています。</span><span class="sxs-lookup"><span data-stu-id="fad5e-104">We've heard your feedback and are making some changes to how you work with groups in Microsoft Intune.</span></span>
<span data-ttu-id="fad5e-105">お客様のすべての Intune グループを Azure Active Directory セキュリティ グループに移行する作業を行っています。</span><span class="sxs-lookup"><span data-stu-id="fad5e-105">We are in the process of migrating all of our customers Intune groups to Azure Active Directory security groups.</span></span>

<span data-ttu-id="fad5e-106">お客様にとってのメリットは、すべての Enterprise Mobility + Security と Azure AD アプリで同じグループ エクスペリエンスを使えるようになることです。</span><span class="sxs-lookup"><span data-stu-id="fad5e-106">The benefit to you is that you will now use the same groups experience across all of you Enterprise Mobility + Security, and Azure AD apps.</span></span> <span data-ttu-id="fad5e-107">さらに、PowerShell と Graph API を使って、この新しい機能を拡張およびカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-107">Additionally, you'll be able to use PowerShell and Graph API to extend and customize this new functionality.</span></span>

<span data-ttu-id="fad5e-108">Azure AD セキュリティ グループは、ユーザーとデバイスの両方に対するあらゆる種類の Intune 展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="fad5e-108">Azure AD security groups support all types of Intune deployments to both users and devices.</span></span> <span data-ttu-id="fad5e-109">さらに、ユーザーが指定した属性に基づいて自動的に更新する Azure AD の動的グループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-109">Additionally, you can use Azure AD dynamic groups that automatically update based on the attributes you supply.</span></span> <span data-ttu-id="fad5e-110">たとえば、iOS 9 搭載デバイスのグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-110">For example, you could create a group of devices that run iOS 9.</span></span> <span data-ttu-id="fad5e-111">IOS 9 を搭載している新しいデバイスが登録されると常に、動的グループに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-111">Whenever a new device that runs iOS 9 is enrolled, it will be automatically added to the dynamic group.</span></span>

## <a name="when-is-this-happening"></a><span data-ttu-id="fad5e-112">移行の時期</span><span class="sxs-lookup"><span data-stu-id="fad5e-112">When is this happening?</span></span>

<span data-ttu-id="fad5e-113">移行プロセスは現在進行中です。</span><span class="sxs-lookup"><span data-stu-id="fad5e-113">The migration process is underway right now.</span></span> <span data-ttu-id="fad5e-114">お客様には、実際に移行が行われる前に通知されます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-114">You'll be notified before we migrate you.</span></span>
<span data-ttu-id="fad5e-115">既に移行が済んだお客様には、従来の Intune コンソールからグループにアクセスしようとすると次のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-115">If you've already been migrated, you'll see a message similar to this when you try to access groups from the classic Intune console:</span></span>

![グループが移行されたことを示すメッセージ。](http://i.imgur.com/72KRaXj.png)

## <a name="what-wont-be-available"></a><span data-ttu-id="fad5e-117">使用できなくなる機能</span><span class="sxs-lookup"><span data-stu-id="fad5e-117">What won't be available?</span></span>

<span data-ttu-id="fad5e-118">Intune グループの既存機能の一部は、Azure AD では利用できません。</span><span class="sxs-lookup"><span data-stu-id="fad5e-118">Some existing capabilities of Intune groups are not available in Azure AD:</span></span>

- <span data-ttu-id="fad5e-119">Intune の**グループに属していないユーザー** グループと**グループに属していないデバイス** グループは、移行されません。</span><span class="sxs-lookup"><span data-stu-id="fad5e-119">The **Ungrouped Users** and **Ungrouped Devices** Intune groups won't be migrated.</span></span>
- <span data-ttu-id="fad5e-120">現在 Intune コンソールに存在する、グループから**特定のメンバーを除外**するオプションは、Azure ポータルにはありません。</span><span class="sxs-lookup"><span data-stu-id="fad5e-120">The option to **Exclude specific members** from a group that currently exists in the Intune console does not exist in the Azure portal.</span></span> <span data-ttu-id="fad5e-121">ただし、Azure AD セキュリティ グループと高度なルールを使って、この動作を複製できます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-121">However, you can use an Azure AD security group with advanced rules to replicate this behavior.</span></span> <span data-ttu-id="fad5e-122">たとえば、次の高度なルールを使うことで、肩書に "Assistant" が付いているユーザーを除く、営業部内のすべてのユーザーをセキュリティ グループに含めることが可能です`(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`。</span><span class="sxs-lookup"><span data-stu-id="fad5e-122">For example, you could create an advanced rule that includes all people in your Sales department in a security group, but not those who have the word "Assistant" in their title, by using this advanced rule: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.</span></span>
- <span data-ttu-id="fad5e-123">Intune コンソールに組み込まれている **Exchange ActiveSync で管理されているすべてのデバイス** グループは、Azure AD には移行されません。</span><span class="sxs-lookup"><span data-stu-id="fad5e-123">The **All Exchange ActiveSync Managed Devices** group that's built-in to the Intune console will not be migrated to Azure AD.</span></span> <span data-ttu-id="fad5e-124">ただし、EAS で管理されたデバイスに関する情報には、Azure ポータルからもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-124">However, you can still access information about EAS managed devices from the Azure portal.</span></span>
- <span data-ttu-id="fad5e-125">従来の Intune コンソールでグループによりレポートをフィルター処理することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="fad5e-125">You won't be able to filter reports by groups in the classic Intune console.</span></span>
  <!--- - Custom group targeting of notification rules will not be available. ROB I took this out as I couldn't replicate the behavior. --->

## <a name="how-to-get-ready"></a><span data-ttu-id="fad5e-126">準備する方法</span><span class="sxs-lookup"><span data-stu-id="fad5e-126">How to get ready</span></span>

- <span data-ttu-id="fad5e-127">Azure AD のセキュリティ グループとそのしくみの詳細については、次の Azure AD トピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fad5e-127">Read the following Azure AD topics to learn about Azure AD security groups and how they work:</span></span>
    -  <span data-ttu-id="fad5e-128">[Azure Active Directory グループを利用したリソースへのアクセス管理](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/)</span><span class="sxs-lookup"><span data-stu-id="fad5e-128">[Managing access to resources with Azure Active Directory groups](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).</span></span>
    -  <span data-ttu-id="fad5e-129">[Azure Active Directory でのグループの管理](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)</span><span class="sxs-lookup"><span data-stu-id="fad5e-129">[Managing groups in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).</span></span>
    -  <span data-ttu-id="fad5e-130">[属性を利用した高度なルールの作成](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)</span><span class="sxs-lookup"><span data-stu-id="fad5e-130">[Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).</span></span>
- <span data-ttu-id="fad5e-131">移行が行われる前に、使われなくなった Intune グループを削除することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fad5e-131">Consider removing any Intune groups you no longer use before you migrate.</span></span>
-  <span data-ttu-id="fad5e-132">グループを作成する必要があるすべての管理者が、**Intune サービス管理者** Azure AD ロールに追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fad5e-132">Make sure that any admins who need to create groups are added to the **Intune Service Administrator** Azure AD role.</span></span> <span data-ttu-id="fad5e-133">Azure AD サービス管理者ロールには**グループの管理**アクセス許可がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fad5e-133">Note that the Azure AD Service Admin role does not have **Manage Group** permissions.</span></span>
-  <span data-ttu-id="fad5e-134">**[特定のメンバーを除外]** オプションが有効なグループを使っている場合は、除外を必要としないようにグループを再設計できるかどうか、または Azure AD クエリの高度なルールを使って同じ結果を実現できるかどうかを、検討してください。</span><span class="sxs-lookup"><span data-stu-id="fad5e-134">If you use groups with the option **Exclude specific members**, consider whether you can redesign these groups to not need exclusions, or whether you can use advanced rules in your Azure AD query to achieve the same result.</span></span>


## <a name="what-happens-to-intune-groups"></a><span data-ttu-id="fad5e-135">Intune グループに対する移行処理の内容</span><span class="sxs-lookup"><span data-stu-id="fad5e-135">What happens to Intune groups?</span></span>

| <span data-ttu-id="fad5e-136">Intune のグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-136">Groups in Intune</span></span>|<span data-ttu-id="fad5e-137">Azure AD のグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-137">Group in Azure AD</span></span>|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|<span data-ttu-id="fad5e-138">静的なユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-138">Static user group</span></span>|<span data-ttu-id="fad5e-139">静的な Azure AD セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-139">Static Azure AD security group</span></span>|
|<span data-ttu-id="fad5e-140">動的なユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-140">Dynamic user group</span></span>|<span data-ttu-id="fad5e-141">Azure AD セキュリティ グループの階層構造を持つ静的な Azure AD セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-141">Static Azure AD security groups with an Azure AD security group hierarchy</span></span>|
|<span data-ttu-id="fad5e-142">静的なデバイス グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-142">Static device group</span></span>|<span data-ttu-id="fad5e-143">静的な Azure AD セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-143">Static Azure AD security group</span></span>|
|<span data-ttu-id="fad5e-144">動的なデバイス グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-144">Dynamic device group</span></span>|<span data-ttu-id="fad5e-145">静的な Azure AD セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-145">Dynamic Azure AD security group</span></span>|
|<span data-ttu-id="fad5e-146">"含める条件" 付きのグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-146">A group with an include condition</span></span>|<span data-ttu-id="fad5e-147">Intune の "含める条件" のすべての静的メンバーまたは動的メンバーを含む静的な Azure AD セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-147">Static Azure AD security group containing any static or dynamic members from the include condition in Intune.</span></span>|
|<span data-ttu-id="fad5e-148">"除外条件" 付きのグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-148">A group with an exclude condition</span></span>|<span data-ttu-id="fad5e-149">移行されません</span><span class="sxs-lookup"><span data-stu-id="fad5e-149">Not migrated</span></span>|
|<span data-ttu-id="fad5e-150">組み込みグループ: **すべてのユーザー**、**グループに属していないユーザー**、**すべてのデバイス**、**グループに属していないデバイス**、**すべてのコンピューター**、**すべてのモバイル デバイス**、**MDM で管理されているすべてのデバイス**、**EAS で管理されているすべてのデバイス**</span><span class="sxs-lookup"><span data-stu-id="fad5e-150">The built-in groups, **All Users**, **Ungrouped Users**, **All Devices**, **Ungrouped devices**, **All Computers**, **All Mobile Devices**, **All MDM managed devices**, and **All EAS managed devices**</span></span>|<span data-ttu-id="fad5e-151">Azure AD セキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="fad5e-151">Azure AD security groups.</span></span>|

<span data-ttu-id="fad5e-152">Intune では、すべてのグループに親グループが必要です。</span><span class="sxs-lookup"><span data-stu-id="fad5e-152">In Intune, all groups have to have a parent group.</span></span> <span data-ttu-id="fad5e-153">グループには、親グループのメンバーのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-153">Groups can only contain members from their parent group.</span></span> <span data-ttu-id="fad5e-154">Azure AD の子グループには、親グループに含まれないメンバーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-154">In Azure AD, child groups can contain members that the parent group does not have.</span></span>

<span data-ttu-id="fad5e-155">属性は、グループの定義時に使用できるデバイス プロパティです。</span><span class="sxs-lookup"><span data-stu-id="fad5e-155">Attributes are device properties that may be used in defining groups.</span></span> <span data-ttu-id="fad5e-156">次の表では、条件を Azure AD セキュリティ グループに移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fad5e-156">This table describes how those criteria will be migrated to Azure AD security groups.</span></span>

| <span data-ttu-id="fad5e-157">Intune での属性</span><span class="sxs-lookup"><span data-stu-id="fad5e-157">Attribute in Intune</span></span>|<span data-ttu-id="fad5e-158">Azure AD での属性</span><span class="sxs-lookup"><span data-stu-id="fad5e-158">Attribute in Azure AD</span></span>|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|<span data-ttu-id="fad5e-159">デバイス グループの組織単位 (OU) 属性</span><span class="sxs-lookup"><span data-stu-id="fad5e-159">Organizational Unit (OU) attribute for device groups</span></span>|<span data-ttu-id="fad5e-160">動的なグループの OU 属性。</span><span class="sxs-lookup"><span data-stu-id="fad5e-160">OU attribute for dynamic groups.</span></span>|
|<span data-ttu-id="fad5e-161">デバイス グループのドメイン名属性</span><span class="sxs-lookup"><span data-stu-id="fad5e-161">Domain name attribute for device groups</span></span>|<span data-ttu-id="fad5e-162">動的なグループのドメイン名属性。</span><span class="sxs-lookup"><span data-stu-id="fad5e-162">Domain Name attribute for dynamic groups.</span></span>|
|<span data-ttu-id="fad5e-163">ユーザー グループの属性としてセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-163">Security group as an attribute for user groups</span></span>|<span data-ttu-id="fad5e-164">Azure AD の動的クエリで属性を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fad5e-164">Groups cannot be attributes in Azure AD dynamic queries.</span></span> <span data-ttu-id="fad5e-165">動的なグループには、ユーザーまたはデバイス固有の属性のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-165">Dynamic groups can only contain user or device specific attributes.</span></span>|
|<span data-ttu-id="fad5e-166">ユーザー グループに対するマネージャー属性</span><span class="sxs-lookup"><span data-stu-id="fad5e-166">Manager attribute for user groups</span></span>|<span data-ttu-id="fad5e-167">動的グループの *manager* 属性に対する高度なルール</span><span class="sxs-lookup"><span data-stu-id="fad5e-167">Advanced Rule for *manager* attribute in dynamic groups</span></span>|
|<span data-ttu-id="fad5e-168">親ユーザー グループのすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="fad5e-168">All users from the parent user group</span></span>|<span data-ttu-id="fad5e-169">そのグループをメンバーとして含む静的なグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-169">Static group with that group as a member</span></span>|
|<span data-ttu-id="fad5e-170">親デバイス グループのすべてのモバイル デバイス</span><span class="sxs-lookup"><span data-stu-id="fad5e-170">All mobile devices from the parent device group</span></span>|<span data-ttu-id="fad5e-171">そのグループをメンバーとして含む静的なグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-171">Static group with that group as a member</span></span>|
|<span data-ttu-id="fad5e-172">Intune によって管理されているすべてのモバイル デバイス</span><span class="sxs-lookup"><span data-stu-id="fad5e-172">All mobile devices managed by Intune</span></span>|<span data-ttu-id="fad5e-173">動的なグループの値として 'MDM' が使用される Management Type 属性</span><span class="sxs-lookup"><span data-stu-id="fad5e-173">Management Type attribute with ‘MDM’ as value for dynamic group</span></span>|
|<span data-ttu-id="fad5e-174">静的なグループ内で入れ子になったグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-174">Nested groups within static groups</span></span> |<span data-ttu-id="fad5e-175">静的なグループ内で入れ子になったグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-175">Nested groups within static groups</span></span>|
|<span data-ttu-id="fad5e-176">動的なグループ内で入れ子になったグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-176">Nested groups within dynamic groups</span></span>|<span data-ttu-id="fad5e-177">入れ子のレベルが 1 である動的なグループ</span><span class="sxs-lookup"><span data-stu-id="fad5e-177">Dynamic group with one level of nesting</span></span>|

## <a name="what-happens-to-policies-and-apps-youve-already-deployed"></a><span data-ttu-id="fad5e-178">既に展開されているポリシーおよびアプリに対する処理</span><span class="sxs-lookup"><span data-stu-id="fad5e-178">What happens to policies and apps you've already deployed?</span></span>

<span data-ttu-id="fad5e-179">ポリシーとアプリは、移行前と同じように、引き続きグループに展開されます。</span><span class="sxs-lookup"><span data-stu-id="fad5e-179">Policies and apps continue to be deployed to groups, just like before.</span></span> <span data-ttu-id="fad5e-180">ただし、これらのグループの管理は、従来の Intune コンソールではなく、Azure ポータルから行うようになります。</span><span class="sxs-lookup"><span data-stu-id="fad5e-180">However, you'll now manage these groups from the Azure portal, instead of the classic Intune console.</span></span>
 
