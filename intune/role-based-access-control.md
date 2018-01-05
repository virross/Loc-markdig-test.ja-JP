---
title: "Intune での RBAC"
titleSuffix: Azure portal
description: "Intune Azure プレビュー: RBAC を使用して、アクションを実行できるユーザーや変更できるユーザーを制御する方法について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9e40e5ffc938058d2a0a32162ff39adc89485c5b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="role-based-administration-control-rbac-with-intune"></a><span data-ttu-id="1f740-103">Intune でのロール ベースの管理制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="1f740-103">Role-based administration control (RBAC) with Intune</span></span>

<span data-ttu-id="1f740-104">RBAC を使用して、組織内で Intune のさまざまなタスクを実行できるユーザーと、それらのタスクが適用されるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="1f740-104">RBAC helps you control who can perform various Intune tasks within your organization, and who those tasks apply to.</span></span> <span data-ttu-id="1f740-105">一般的な Intune シナリオを対象とする組み込みロールを使用するか、独自のロールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1f740-105">You can either use the built-in roles that cover some common Intune scenarios, or you can create your own roles.</span></span> <span data-ttu-id="1f740-106">ロールは、次によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="1f740-106">A role is defined by:</span></span>

- <span data-ttu-id="1f740-107">**ロールの定義**: ロールの名前、ロールが管理するリソース、各リソースに関して付与されるアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="1f740-107">**Role definition**: The name of a role, the resources it manages, and the permissions granted for each resource.</span></span>
- <span data-ttu-id="1f740-108">**メンバー**: アクセス許可が付与されるユーザー グループ。</span><span class="sxs-lookup"><span data-stu-id="1f740-108">**Members**: The user groups that are granted the permissions.</span></span>
- <span data-ttu-id="1f740-109">**スコープ**: メンバーが管理できるユーザーまたはデバイスのグループ。</span><span class="sxs-lookup"><span data-stu-id="1f740-109">**Scope**: The user or device groups that the members can manage.</span></span>
- <span data-ttu-id="1f740-110">**割り当て**: 定義、メンバー、スコープが構成されている場合に、ロールが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1f740-110">**Assignment**: When the definition, members, and scope have been configured, the role is assigned.</span></span>

![Intune での RBAC の例](./media/intune-rbac-1.PNG)

<span data-ttu-id="1f740-112">新しい Azure Portal では、Intune で使用できる 2 つのディレクトリ ロールが **Azure Active Directory (Azure AD)** で提供されます。</span><span class="sxs-lookup"><span data-stu-id="1f740-112">Starting at the new Azure portal, **Azure Active Directory (Azure AD)** provides two Directory Roles which can be used with Intune.</span></span> <span data-ttu-id="1f740-113">これらのロールには、Intune のすべてのアクティビティを実行できる完全なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="1f740-113">These roles are granted full permission to perform all activities in Intune:</span></span>

- <span data-ttu-id="1f740-114">**グローバル管理者:** このロールが割り当てられたユーザーは、Azure AD のすべての管理機能だけでなく、Azure AD にフェデレーションされたサービス (Exchange Online、SharePoint Online、Skype for Business Online など) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1f740-114">**Global Administrator:** Users with this role have access to all administrative features in Azure AD, as well as services that federate to Azure AD like Exchange Online, SharePoint Online, and Skype for Business Online.</span></span> <span data-ttu-id="1f740-115">Azure AD テナントにサインアップするユーザーはグローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="1f740-115">The person who signs up for the Azure AD tenant becomes a global administrator.</span></span> <span data-ttu-id="1f740-116">グローバル管理者のみが Azure AD の他の管理者ロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1f740-116">Only global administrators can assign other Azure AD administrator roles.</span></span> <span data-ttu-id="1f740-117">組織は複数のグローバル管理者を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="1f740-117">There can be more than one global administrator at your organization.</span></span> <span data-ttu-id="1f740-118">グローバル管理者は、すべてのユーザーと他のすべての管理者のパスワードをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="1f740-118">Global admins can reset the password for any user and all other administrators.</span></span>

- <span data-ttu-id="1f740-119">**Intune サービス管理者:** このロールが割り当てられたユーザーは、サービスが存在する場合に Intune 内のグローバル アクセス許可を持ちます。</span><span class="sxs-lookup"><span data-stu-id="1f740-119">**Intune Service Administrator:** Users with this role have global permissions within Intune when the service is present.</span></span> <span data-ttu-id="1f740-120">また、Azure の制限事項の置き換えの他に、このロールはユーザーとデバイスを管理し、Intune グループを作成および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="1f740-120">Additionally, other than any superseding Azure restrictions, this role provides the ability to manage users, devices, and create and manage Intune groups.</span></span>

- <span data-ttu-id="1f740-121">**条件付きアクセス管理者:** このロールが割り当てられたユーザーは、条件付きアクセス ポリシーを表示、作成、修正、削除するアクセス許可を有するのみとなります。</span><span class="sxs-lookup"><span data-stu-id="1f740-121">**Conditional Access Administrator:** Users with this role only have permissions to view, create, modify, and delete conditional access policies.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1f740-122">Intune サービス管理者のロールでは、Azure AD の条件付きアクセスの設定を管理できません。</span><span class="sxs-lookup"><span data-stu-id="1f740-122">The Intune Service Administrator role does not provide the ability to manage Azure AD’s conditional access settings.</span></span>

    > [!TIP]
    > <span data-ttu-id="1f740-123">また Intune では、Azure AD の 3 つの拡張機能 (**ユーザー**、**グループ**、Azure AD RBAC を使用して制御される**条件付きアクセス**) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f740-123">Intune also shows three Azure AD extensions: **Users**, **Groups**, and **Conditional access**, which are controlled using Azure AD RBAC.</span></span> <span data-ttu-id="1f740-124">また、**ユーザーアカウント管理者**は AAD ユーザー/グループのアクティビティのみを実行します。Intune のすべてのアクティビティを実行する完全なアクセス許可はありません。</span><span class="sxs-lookup"><span data-stu-id="1f740-124">Additionally, the **User Account Administrator** only performs AAD user/group activities and does not have full permissions to perform all activities in Intune.</span></span> <span data-ttu-id="1f740-125">詳細については、[Azure AD での RBAC](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1f740-125">Refer to [RBAC with Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) for more details.</span></span>

## <a name="roles-created-in-the-intune-classic-portal"></a><span data-ttu-id="1f740-126">Intune クラシック ポータルで作成されたロール</span><span class="sxs-lookup"><span data-stu-id="1f740-126">Roles created in the Intune classic portal</span></span>

<span data-ttu-id="1f740-127">"完全な" アクセス許可を付与された Intune **サービス管理者**のユーザーのみが、Intune クラシック ポータルから Azure Portal の Intune に移行されます。</span><span class="sxs-lookup"><span data-stu-id="1f740-127">Only Intune **Service Administrators** users with "Full" permissions get migrated from the Intune classic portal to Intune in the Azure portal.</span></span> <span data-ttu-id="1f740-128">Intune **サービス管理者**のユーザーに、Azure Portal の Intune のロールへの "読み取り専用" または "ヘルプデスク" のアクセス権を再度割り当てて、クラシック ポータルからサービス管理者を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f740-128">You need to re-assign Intune **Service Administrators** users with "Read-Only" or "Helpdesk" access into the Intune roles in the Azure portal, and remove them from the classic portal.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f740-129">Intune での PC の使用を管理するために管理者のアクセスが必要な場合は、Intune サービス管理者のクラシック ポータルへのアクセス権を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f740-129">You might need to keep the Intune Service Administrator access in the classic portal if your admins still need access to manage PC’s using with Intune.</span></span>

## <a name="built-in-roles"></a><span data-ttu-id="1f740-130">組み込みロール</span><span class="sxs-lookup"><span data-stu-id="1f740-130">Built-in roles</span></span>

<span data-ttu-id="1f740-131">Intune には次のロールが組み込まれており、追加の構成なしでこれらのロールをグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1f740-131">The following roles are built into Intune and you can assign them to groups with no further configuration:</span></span>

- <span data-ttu-id="1f740-132">**ヘルプ デスク オペレーター**: ユーザーとデバイスに対するリモート タスクを実行し、ユーザーやデバイスにアプリケーションやポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1f740-132">**Help Desk Operator**: Performs remote tasks on users and devices, and can assign applications or policies to users or devices.</span></span>
- <span data-ttu-id="1f740-133">**ポリシーおよびプロファイル マネージャー**: コンプライアンス ポリシー、構成プロファイル、Apple の登録、企業デバイスの識別子を管理します。</span><span class="sxs-lookup"><span data-stu-id="1f740-133">**Policy and Profile Manager**: Manages compliance policy, configuration profiles, Apple enrollment, and corporate device identifiers.</span></span>
- <span data-ttu-id="1f740-134">**読み取り専用オペレーター**: ユーザー、デバイス、登録、構成、アプリケーション情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f740-134">**Read Only Operator**: Views user, device, enrollment, configuration, and application information.</span></span> <span data-ttu-id="1f740-135">Intune に変更を加えることはできません。</span><span class="sxs-lookup"><span data-stu-id="1f740-135">Cannot make changes to Intune.</span></span>
- <span data-ttu-id="1f740-136">**アプリケーション マネージャー**: モバイルと管理対象アプリケーションを管理し、デバイス情報を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1f740-136">**Application Manager**: Manages mobile and managed applications, and can read device information.</span></span>

### <a name="to-assign-a-built-in-role"></a><span data-ttu-id="1f740-137">組み込みロールを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="1f740-137">To assign a built-in role</span></span>

1. <span data-ttu-id="1f740-138">**[Intune の役割]** で、割り当てる組み込みロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-138">On the **Intune roles**, choose the built-in role you want to assign.</span></span>

2. <span data-ttu-id="1f740-139">**[プロパティ]** ブレードの <*ロール名*> で、**[管理]**、**[割り当て]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-139">On the <*role name*> - **Properties** blade, choose **Manage**, then **Assignments**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f740-140">組み込みロールの削除や編集はできません</span><span class="sxs-lookup"><span data-stu-id="1f740-140">You cannot delete or edit the built-in roles</span></span>

3. <span data-ttu-id="1f740-141">[カスタム ロール] ブレードで、**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-141">On the custom role blade, choose **Assign**.</span></span>

4. <span data-ttu-id="1f740-142">**[ロールの割り当て]** ブレードで、割り当ての**名前**と省略可能な**説明**を入力し、次を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-142">On the **Role Assignments** blade, enter a **Name** and optional **Description** for the assignment, and then choose the following:</span></span>
    - <span data-ttu-id="1f740-143">**[メンバー]** - アクセス許可を付与するユーザーを含むグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-143">**Members** - Select a group that contains the user you want to give the permissions to.</span></span>
    - <span data-ttu-id="1f740-144">**[スコープ]** - 上記のメンバーが管理できるユーザーを含むグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-144">**Scope** - Select a group containing the users who the member above will be allowed to manage.</span></span>
<br></br>
5. <span data-ttu-id="1f740-145">終了したら、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f740-145">When you are done, click **OK**.</span></span> <span data-ttu-id="1f740-146">新しい割り当てが割り当ての一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f740-146">The new assignment is displayed in the list of assignments.</span></span>

### <a name="intune-rbac-table"></a><span data-ttu-id="1f740-147">Intune RBAC テーブル</span><span class="sxs-lookup"><span data-stu-id="1f740-147">Intune RBAC table</span></span>

- <span data-ttu-id="1f740-148">[Intune RBAC テーブル](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a)をダウンロードして、各ロールが実行できる操作の詳細をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="1f740-148">Download the [Intune RBAC table](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) to see more details on what each role can do.</span></span>

## <a name="custom-roles"></a><span data-ttu-id="1f740-149">カスタム ロール</span><span class="sxs-lookup"><span data-stu-id="1f740-149">Custom roles</span></span>

<span data-ttu-id="1f740-150">特定のジョブ機能に必要なアクセス許可を含むカスタム ロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f740-150">You can create a custom role that includes any permissions required for a specific job function.</span></span> <span data-ttu-id="1f740-151">たとえば、IT 部門の 1 つのグループがアプリケーション、ポリシー、構成プロファイルを管理している場合は、これらのアクセス許可をすべて 1 つのカスタム ロールに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1f740-151">For example, if an IT department group manages applications, policies, and configuration profiles, you can add all those permissions together in one custom role.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f740-152">ロールを作成、編集、または割り当てるには、アカウントに Azure AD の次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f740-152">To create, edit, or assign roles, your account must have one of the following permissions in Azure AD:</span></span>
> - <span data-ttu-id="1f740-153">**グローバル管理者**</span><span class="sxs-lookup"><span data-stu-id="1f740-153">**Global Administrator**</span></span>
> - <span data-ttu-id="1f740-154">**Intune サービス管理者**</span><span class="sxs-lookup"><span data-stu-id="1f740-154">**Intune Service Administrator**</span></span>

### <a name="to-create-a-custom-role"></a><span data-ttu-id="1f740-155">カスタム ロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="1f740-155">To create a custom role</span></span>

1. <span data-ttu-id="1f740-156">Intune 資格情報で [Azure Portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1f740-156">Sign into the [Azure portal](https://portal.azure.com) with your Intune credentials.</span></span>

2. <span data-ttu-id="1f740-157">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1f740-157">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="1f740-158">**[Intune]** を選択して Intune ダッシュボードを開き、**[Intune の役割]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-158">Choose **Intune**, the Intune Dashboard opens, choose **Intune roles**.</span></span>

4. <span data-ttu-id="1f740-159">**[Intune の役割]** ブレードで **[Intune の役割]** を選択し、**[カスタムの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-159">On the **Intune roles** blade, choose **Intune roles**, choose **Add custom**.</span></span>

5. <span data-ttu-id="1f740-160">**[カスタム ロールの追加]** ブレードで、新しいロールの名前と説明を入力し、**[アクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f740-160">On the **Add Custom Role** blade, enter a name and description for the new role, then click **Permissions**.</span></span>

3. <span data-ttu-id="1f740-161">**[アクセス許可]** ブレードで、このロールで使用するアクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-161">On the **Permissions** blade, choose the permissions you want to use with this role.</span></span> <span data-ttu-id="1f740-162">[Intune RBAC テーブル](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a)を使用すると、適用するアクセス許可を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1f740-162">Use the [Intune RBAC table](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) to help you decide which permissions you want to apply.</span></span>

4. <span data-ttu-id="1f740-163">終了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-163">When you are done, choose **OK**.</span></span>

5. <span data-ttu-id="1f740-164">**[カスタム ロールの追加]** ブレードで、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f740-164">On the **Add Custom Role** blade, click **Create**.</span></span> <span data-ttu-id="1f740-165">新しいロールが **[Intune の役割]** ブレードの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f740-165">The new role is displayed in the list on the **Intune roles** blade.</span></span>

### <a name="to-assign-a-custom-role"></a><span data-ttu-id="1f740-166">カスタム ロールを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="1f740-166">To assign a custom role</span></span>

1. <span data-ttu-id="1f740-167">**[Intune の役割]** で、割り当てるカスタム ロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-167">On the **Intune roles**, choose the custom role you want to assign.</span></span>

2. <span data-ttu-id="1f740-168">**[プロパティ]** ブレードの <*ロール名*> で、**[管理]**、**[割り当て]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-168">On the <*role name*> - **Properties** blade, choose **Manage**, then **Assignments**.</span></span> <span data-ttu-id="1f740-169">このブレードで、既存のロールを編集または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f740-169">On this blade, you can also edit or delete existing roles.</span></span>

3. <span data-ttu-id="1f740-170">[カスタム ロール] ブレードで、**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-170">On the custom role blade, choose **Assign**.</span></span>

4. <span data-ttu-id="1f740-171">**[ロールの割り当て]** ブレードで、割り当ての**名前**と省略可能な**説明**を入力し、次を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-171">On the **Role Assignments** blade, enter a **Name** and optional **Description** for the assignment, and then choose the following:</span></span>
    - <span data-ttu-id="1f740-172">**[メンバー]** - アクセス許可を付与するユーザーを含むグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-172">**Members** - Select a group that contains the user you want to give the permissions to.</span></span>
    - <span data-ttu-id="1f740-173">**[スコープ]** - 上記のメンバーが管理できるユーザーを含むグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f740-173">**Scope** - Select a group containing the users who the member above will be allowed to manage.</span></span>
<br></br>
5. <span data-ttu-id="1f740-174">終了したら、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f740-174">When you are done, click **OK**.</span></span> <span data-ttu-id="1f740-175">新しい割り当てが割り当ての一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f740-175">The new assignment is displayed in the list of assignments.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1f740-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="1f740-176">Next steps</span></span>

[<span data-ttu-id="1f740-177">トラブルシューティング ポータルで Intune ヘルプデスク オペレーター ロールを使用する</span><span class="sxs-lookup"><span data-stu-id="1f740-177">Use the Intune Helpdesk operator role with the troubleshooting portal</span></span>](help-desk-operators.md)

## <a name="see-also"></a><span data-ttu-id="1f740-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f740-178">See also</span></span>

[<span data-ttu-id="1f740-179">Azure AD でロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1f740-179">Assign roles using Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
