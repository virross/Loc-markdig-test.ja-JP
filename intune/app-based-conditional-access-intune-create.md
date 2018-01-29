---
title: "Intune を使用したアプリ ベースの条件付きアクセス ポリシー"
description: "このトピックでは、Intune を使用したアプリベースの条件付きアクセス ポリシーを構成する方法について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1e48effd28d1e0598abbdfbf1c48298366c07a4f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="set-up-app-based-conditional-access-policies"></a><span data-ttu-id="c3e8a-103">アプリベースの条件付きアクセス ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="c3e8a-103">Set up app-based conditional access policies</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="c3e8a-104">このトピックでは、承認済みアプリに含まれるアプリにアプリベースの条件付きアクセス ポリシーを設定する方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-104">This topic provides instructions on how to set up app-based conditional access policies for apps that are part of the list of approved apps.</span></span> <span data-ttu-id="c3e8a-105">承認済みのアプリの一覧は、Microsoft によってテストされたアプリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-105">The list of approved apps consists of apps that were tested by Microsoft.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3e8a-106">このトピックでは、Exchange Online を利用し、アプリベースの条件付きアクセス ポリシーを追加する手順について段階的に説明しますが、SharePoint Online や Microsoft Teams など、他のアプリを承認済みアプリの一覧から追加するときでも同じ手順を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-106">This topic walks through the steps to add an app-based conditional access policy using Exchange Online, but you can use the same steps when adding other apps like SharePoint Online, Microsoft Teams, etc. from the list of approved apps.</span></span>

## <a name="to-create-an-app-based-conditional-access-policy"></a><span data-ttu-id="c3e8a-107">アプリベースの条件付きアクセス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="c3e8a-107">To create an app-based conditional access policy</span></span>
1.  <span data-ttu-id="c3e8a-108">[Azure Portal](https://portal.azure.com) に移動し、自分の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-108">Go the [Azure portal](https://portal.azure.com) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="c3e8a-109">**[その他のサービス]** を選択し、"Intune" と入力します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-109">Choose **More services**, and type: "Intune".</span></span>

3.  <span data-ttu-id="c3e8a-110">**[Intune アプリ保護]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-110">Choose **Intune App Protection**.</span></span>

4.  <span data-ttu-id="c3e8a-111">**[Intune モバイル アプリケーション管理]** ブレードで **[すべての設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-111">On the **Intune mobile application management** blade choose **All Settings**.</span></span>

5.  <span data-ttu-id="c3e8a-112">**[条件付きアクセス]** セクションで、**[Exchange Online]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-112">On the **Conditional access** section, choose **Exchange Online**.</span></span>

    ![[条件付きアクセス] セクションの [Exchange Online] オプションが強調表示された設定ブレードのスクリーンショット](./media/MAM-conditional-access-1.png)

6. <span data-ttu-id="c3e8a-114">**[許可されているアプリ]** ブレードの **[Allow apps that support Intune app policies]** (Intune アプリ ポリシーをサポートするアプリを許可する) オプションを選択して、Exchange Online へのアクセスを Intune アプリ保護ポリシーでサポートされているアプリにのみ許可します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-114">On the **Allowed apps** blade, choose the **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies to have the ability to access Exchange Online.</span></span> <span data-ttu-id="c3e8a-115">このオプションを選択すると、サポートされるアプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-115">When you select this option, the list of supported apps is displayed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3e8a-116">iOS と Android の組み込みのメール クライアントを含め、Exchange Online に接続するすべての Exchange Active Sync メール クライアントは、電子メールを送受信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-116">All Exchange Active Sync mail clients, including the built-in mail clients on iOS and Android that connect to Exchange Online, will be prevented from sending or receiving email.</span></span> <span data-ttu-id="c3e8a-117">ユーザーには、Outlook メール アプリを使用する必要があることを知らせる 1 通の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-117">Users will instead receive a single email informing them that they need to use the Outlook mail app.</span></span>

7. <span data-ttu-id="c3e8a-118">このポリシーをユーザーに適用するには、**[制限対象のユーザー グループ]** ブレードを開き、**[ユーザー グループの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-118">To apply this policy to users, open the **Restricted user groups** blade, and choose **Add user group**.</span></span> <span data-ttu-id="c3e8a-119">このポリシーを適用する 1 つまたは複数のユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-119">Select one or more user groups that should get this policy.</span></span>

    ![[ユーザー グループの追加] オプションが強調表示されている [制限対象のユーザー グループ] ブレードのスクリーンショット](./media/mam-ca-add-user-group.png)

8. <span data-ttu-id="c3e8a-121">前の手順で選択したユーザー グループのうち、このポリシーの影響を受けないようにするユーザーがいるとします。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-121">You may want some users in the user group you selected in the previous step not to be affected by this policy.</span></span> <span data-ttu-id="c3e8a-122">このような場合、ユーザーのグループを除外ユーザー グループ一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-122">In such cases, add the group of users to the exempted user groups list.</span></span> <span data-ttu-id="c3e8a-123">**[Exchange Online]** ブレードで、**[Exempted user groups]** (除外するユーザー グループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-123">From the **Exchange Online** blade, choose **Exempted user groups**.</span></span> <span data-ttu-id="c3e8a-124">**[ユーザー グループの追加]** を選択してユーザー グループの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-124">Choose **Add user group** to open the list of user groups.</span></span> <span data-ttu-id="c3e8a-125">このポリシーから除外するグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-125">Select the groups you want to exempt from this policy.</span></span>

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a><span data-ttu-id="c3e8a-126">既存のアプリベースの CA ポリシーからユーザー グループを変更または削除するには</span><span class="sxs-lookup"><span data-stu-id="c3e8a-126">To modify or delete user groups from an existing app-based CA policy</span></span>

1. <span data-ttu-id="c3e8a-127">**[制限対象のユーザー グループ]** ブレードを開き、削除するユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-127">Open the **Restricted user groups** blade, then highlight the user group you want to delete.</span></span>
2. <span data-ttu-id="c3e8a-128">省略記号をクリックすると、削除のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-128">Click on the ellipse to see the delete options.</span></span>
3. <span data-ttu-id="c3e8a-129">**[削除]** を選択すると、一覧からユーザー グループが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-129">Choose **Delete** to remove the user group from the list.</span></span>

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a><span data-ttu-id="c3e8a-130">Azure AD ワークロードでアプリベースの条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c3e8a-130">Create app-based conditional access policies in Azure AD workload</span></span>

<span data-ttu-id="c3e8a-131">Intune 1708 リリース以降、IT 管理者は Azure AD ワークロードからアプリベースの条件付きアクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-131">Beginning with Intune 1708 release, IT admins can create app-based conditional access policies from the Azure AD workload.</span></span> <span data-ttu-id="c3e8a-132">Azure と Intune のワークロードを切り替える必要がなくなり、便利です。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-132">This gives convenience so you don't need to switch between the Azure and the Intune workloads.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3e8a-133">Intune Azure Portal から Azure AD の条件付きアクセス ポリシーを作成するには、Azure AD Premium ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-133">You need to have an Azure AD Premium license to create Azure AD conditional access policies from the Intune Azure portal.</span></span>

### <a name="to-create-an-app-based-conditional-access-policy"></a><span data-ttu-id="c3e8a-134">アプリベースの条件付きアクセス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="c3e8a-134">To create an app-based conditional access policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3e8a-135">アプリベースの条件付きアクセス ポリシーを利用するには、先に、[Intune アプリ保護ポリシー](app-protection-policies.md)をアプリに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-135">You need to have [Intune app protection policies](app-protection-policies.md) applied to your apps before using app-based conditional access policies.</span></span>

1. <span data-ttu-id="c3e8a-136">**Intune ダッシュボード**で、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-136">In the **Intune Dashboard**, choose **Conditional access**.</span></span>

2. <span data-ttu-id="c3e8a-137">**[ポリシー]** ブレードで、**[新しいポリシー]** を選択し、新しいアプリベースの条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-137">In the **Policies** blade, choose **New policy** to create your new app-based conditional access policy.</span></span>

4. <span data-ttu-id="c3e8a-138">ポリシー名を入力し、**[割り当て]** セクションで利用できる設定を構成したら、**[アクセスの制御]** セクションで **[許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-138">Once you enter a policy name and configure the settings available in the **Assignments** section, then choose **Grant** under the **Access controls** section.</span></span>

5. <span data-ttu-id="c3e8a-139">**[承認されたクライアント アプリが必要です]** を選択し、**[選択]** を選択し、**[OK]** を選択して新しいポリシーを保存します。</span><span class="sxs-lookup"><span data-stu-id="c3e8a-139">Choose **Require approved client app**, choose **Select**, then choose **OK** to save the new policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c3e8a-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="c3e8a-140">Next steps</span></span>
[<span data-ttu-id="c3e8a-141">最新の認証を使用していないアプリをブロックする</span><span class="sxs-lookup"><span data-stu-id="c3e8a-141">Block apps that do not have modern authentication</span></span>](app-modern-authentication-block.md)

### <a name="see-also"></a><span data-ttu-id="c3e8a-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3e8a-142">See also</span></span>

<span data-ttu-id="c3e8a-143">[アプリ保護ポリシーでアプリ データを保護する](app-protection-policies.md)
[Azure Active Directory の条件付きアクセス](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)</span><span class="sxs-lookup"><span data-stu-id="c3e8a-143">[Protect app data with app protection policies](app-protection-policies.md)
[Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)</span></span>
