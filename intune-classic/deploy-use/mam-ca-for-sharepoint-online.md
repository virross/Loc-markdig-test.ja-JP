---
title: "SharePoint Online のアプリベースの条件付きアクセス ポリシーを作成する"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 2a85caee417e766712f48c78278ad6608c7332a3
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a><span data-ttu-id="efd3f-102">SharePoint Online のアプリベースの条件付きアクセス (CA) ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="efd3f-102">Set up app-based conditional access (CA) policies for SharePoint Online</span></span>

[!INCLUDE [note for both-portals](../includes/note-for-both-portals.md)]

<span data-ttu-id="efd3f-103">ここでは、SharePoint Online のアプリベースの条件付きアクセス ポリシーを設定する方法のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-103">This topic provides guidance on how to set up app-based conditional access policy for SharePoint Online.</span></span> <span data-ttu-id="efd3f-104">管理者は、アプリベースの CA を使用して、Intune App 保護ポリシーが適用されているモバイル アプリのみを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="efd3f-104">App-based CA helps admins to only allow mobile apps that have Intune app protection policies applied to.</span></span>

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a><span data-ttu-id="efd3f-105">SharePoint Online のアプリベースの CA ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="efd3f-105">To create the app-based CA policy for SharePoint Online</span></span>

1. <span data-ttu-id="efd3f-106">[Azure Portal](https://portal.azure.com) に移動し、自分の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="efd3f-106">Go the [Azure portal](https://portal.azure.com) and sign in with your credentials.</span></span>

    > [!NOTE]
    > <span data-ttu-id="efd3f-107">Azure Portal を初めて使用する場合は、[アプリ保護ポリシーの Azure Portal](azure-portal-for-microsoft-intune-mam-policies.md) に関するトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="efd3f-107">If you're new to the Azure portal experience read the [Azure portal for app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) topic.</span></span>

2. <span data-ttu-id="efd3f-108">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-108">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="efd3f-109">**[Intune アプリ保護]** > **[Intune モバイル アプリケーション管理]** > **[すべての設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-109">Choose **Intune App Protection** > **Intune mobile application management** > **All Settings**.</span></span>

4. <span data-ttu-id="efd3f-110">[Intune モバイル アプリケーション管理] ブレードで [SharePoint Online] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-110">On the Intune mobile application management blade, choose the SharePoint Online tile.</span></span>

5. <span data-ttu-id="efd3f-111">**[許可されているアプリ]** ブレードの **[Intune アプリ ポリシーをサポートするアプリを許可する]** オプションを選択して、Intune アプリ保護ポリシーでサポートされているアプリにのみ許可します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-111">On the **Allowed apps** blade, choose **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="efd3f-112">Intune アプリ保護ポリシーでサポートされているアプリのみを許可するオプションを選択すると、サポートされているアプリ**のみ**を含む一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efd3f-112">When you select the option to only allow apps that are supported by Intune app protection policies, a list containing **only** the supported apps is displayed.</span></span>

    ![アプリの一覧を示す [許可されたアプリ] ブレードのスクリーンショット](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a><span data-ttu-id="efd3f-114">アプリベースの CA ポリシーをユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="efd3f-114">To assign app-based CA policies to your users</span></span>

1. <span data-ttu-id="efd3f-115">**[制限対象のユーザー グループ]** ブレードを開き、**[ユーザー グループの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-115">Open the **Restricted user groups** blade, then choose **Add user group**.</span></span>

2. <span data-ttu-id="efd3f-116">このポリシーを適用する 1 つまたは複数のユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-116">Select one or more user groups that should get this policy.</span></span>

    ![[ユーザー グループの追加] オプションが強調表示されている [制限対象のユーザー グループ] ブレードのスクリーンショット](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="efd3f-118">前の手順で選択したユーザー グループのうち、このポリシーの影響を受けないようにするユーザーがいるとします。</span><span class="sxs-lookup"><span data-stu-id="efd3f-118">You may want some users in the user group you selected in the previous step not to be affected by this policy.</span></span> <span data-ttu-id="efd3f-119">このような場合、ユーザーのグループを除外ユーザー グループ一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-119">In such cases, add the group of users to the exempted user groups list.</span></span> 

3. <span data-ttu-id="efd3f-120">**[SharePoint Online]** ブレードの **[Exempted user groups] \(除外するユーザー グループ)** を選択し、**[ユーザー グループの追加]** を選択してユーザー グループの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="efd3f-120">On the **SharePoint Online** blade, choose **Exempted user groups**, then choose **Add user group** to open the list of user groups.</span></span>

4. <span data-ttu-id="efd3f-121">このポリシーから除外するグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-121">Select the groups you want to exempt from this policy.</span></span>  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a><span data-ttu-id="efd3f-122">既存のアプリベースの CA ポリシーからユーザー グループを変更または削除するには</span><span class="sxs-lookup"><span data-stu-id="efd3f-122">To modify or delete user groups from an existing app-based CA policy</span></span>

1. <span data-ttu-id="efd3f-123">**[制限対象のユーザー グループ]** ブレードを開き、削除するユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="efd3f-123">Open the **Restricted user groups** blade, then highlight the user group you want to delete.</span></span>
2. <span data-ttu-id="efd3f-124">省略記号をクリックすると、削除のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efd3f-124">Click on the ellipse to see the delete options.</span></span>
3. <span data-ttu-id="efd3f-125">**[削除]** を選択すると、一覧からユーザー グループが削除されます。</span><span class="sxs-lookup"><span data-stu-id="efd3f-125">Choose **Delete** to remove the user group from the list.</span></span>

> [!NOTE] 
> <span data-ttu-id="efd3f-126">手順は、**[制限対象のユーザー グループ]** 一覧からユーザー グループを削除する手順と同じです。</span><span class="sxs-lookup"><span data-stu-id="efd3f-126">You can follow the steps procedure to remove a user group from the **Exempted user group** list.</span></span>

## <a name="next-steps"></a><span data-ttu-id="efd3f-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="efd3f-127">Next steps</span></span>

[<span data-ttu-id="efd3f-128">最新の認証を使用していないアプリをブロックする</span><span class="sxs-lookup"><span data-stu-id="efd3f-128">Block apps that do not use modern authentication</span></span>](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a><span data-ttu-id="efd3f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="efd3f-129">See also</span></span>

[<span data-ttu-id="efd3f-130">アプリ保護ポリシーを使用したアプリ データの保護</span><span class="sxs-lookup"><span data-stu-id="efd3f-130">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[<span data-ttu-id="efd3f-131">Exchange Online のアプリベースの CA を構成する</span><span class="sxs-lookup"><span data-stu-id="efd3f-131">Configure app-based CA for Exchange Online</span></span>](mam-ca-for-exchange-online.md)
