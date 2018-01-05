---
title: "Exchange Online のアプリのアクセス権"
description: "このトピックでは、MAM アプリの条件付きアクセス ポリシーを構成する方法について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2528bee69ca93ae63219e89f2acf9582bca653c1
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="create-an-exchange-online-conditional-access-to-only-allow-apps-supported-by-mam"></a><span data-ttu-id="7617a-103">MAM でサポートされているアプリのみを許可する Exchange Online の条件付きアクセスを作成する</span><span class="sxs-lookup"><span data-stu-id="7617a-103">Create an Exchange Online conditional access to only allow apps supported by MAM</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="7617a-104">このトピックでは、Intune アプリ保護ポリシーをサポートするモバイル アプリのみを許可するように Exchange Online の条件付きアクセスをセットアップする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="7617a-104">This topic gives you step-by-step instructions on how to set up conditional access for  Exchange Online to only allow mobile apps that support Intune app protection policies.</span></span>


## <a name="create-an-exchange-online-policy"></a><span data-ttu-id="7617a-105">Exchange Online ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="7617a-105">Create an Exchange Online policy</span></span>
1.  <span data-ttu-id="7617a-106">アプリのアクセス機能が含まれる [Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7617a-106">Sign into the [Azure portal](https://portal.azure.com) that includes the app access feature.</span></span> <span data-ttu-id="7617a-107">Azure ポータルを初めて使用する場合は、[アプリ保護ポリシーの Azure ポータル](azure-portal-for-microsoft-intune-mam-policies.md)に関するトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7617a-107">If you are new to the Azure portal experience read the [Azure portal for app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) topic.</span></span>

2.  <span data-ttu-id="7617a-108">**[その他のサービス]** を選択し、"Intune" と入力します。</span><span class="sxs-lookup"><span data-stu-id="7617a-108">Choose **More services**, and type: "Intune".</span></span>

3.  <span data-ttu-id="7617a-109">**[Intune アプリ保護]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7617a-109">Choose **Intune App Protection**.</span></span>

4.  <span data-ttu-id="7617a-110">**[Intune モバイル アプリケーション管理]** ブレードで **[すべての設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7617a-110">On the **Intune mobile application management** blade choose **All Settings**.</span></span>

5.  <span data-ttu-id="7617a-111">**[条件付きアクセス]** セクションで、**[Exchange Online]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7617a-111">On the **Conditional access** section, choose **Exchange Online**.</span></span>

    ![[条件付きアクセス] セクションの [Exchange Online] オプションが強調表示された設定ブレードのスクリーンショット](../media/MAM-conditional-access-1.png)

6. <span data-ttu-id="7617a-113">**[許可されているアプリ]** ブレードの **[Allow apps that support Intune app policies]** (Intune アプリ ポリシーをサポートするアプリを許可する) オプションを選択して、Exchange Online へのアクセスを Intune アプリ保護ポリシーでサポートされているアプリにのみ許可します。</span><span class="sxs-lookup"><span data-stu-id="7617a-113">On the **Allowed apps** blade, choose the **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies to have the ability to access Exchange Online.</span></span> <span data-ttu-id="7617a-114">このオプションを選択すると、サポートされるアプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7617a-114">When you select this option, the list of supported apps is displayed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7617a-115">iOS と Android の組み込みのメール クライアントを含め、Exchange Online に接続するすべての Exchange Active Sync メール クライアントは、電子メールを送受信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7617a-115">All Exchange Active Sync mail clients, including the built-in mail clients on iOS and >Android that connect to Exchange Online, will be prevented from sending or receiving >email.</span></span> <span data-ttu-id="7617a-116">ユーザーには、Outlook メール アプリを使用する必要があることを知らせる 1 通の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="7617a-116">Users will instead receive a single email informing them that they need to use the >Outlook mail app.</span></span>

7. <span data-ttu-id="7617a-117">このポリシーをユーザーに適用するには、**[制限対象のユーザー グループ]** ブレードを開き、**[ユーザー グループの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7617a-117">To apply this policy to users, open the **Restricted user groups** blade, and choose **Add user group**.</span></span> <span data-ttu-id="7617a-118">このポリシーを適用する 1 つまたは複数のユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="7617a-118">Select one or more user groups that should get this policy.</span></span>

    ![[ユーザー グループの追加] オプションが強調表示されている [制限対象のユーザー グループ] ブレードのスクリーンショット](../media/mam-ca-add-user-group.png)

8. <span data-ttu-id="7617a-120">前の手順で選択したユーザー グループのうち、このポリシーの影響を受けないようにするユーザーがいるとします。</span><span class="sxs-lookup"><span data-stu-id="7617a-120">You may want some users in the user group you selected in the previous step not to be affected by this policy.</span></span> <span data-ttu-id="7617a-121">このような場合、ユーザーのグループを除外ユーザー グループ一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="7617a-121">In such cases, add the group of users to the exempted user groups list.</span></span> <span data-ttu-id="7617a-122">**[Exchange Online]** ブレードで、**[Exempted user groups]** (除外するユーザー グループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="7617a-122">From the **Exchange Online** blade, choose **Exempted user groups**.</span></span> <span data-ttu-id="7617a-123">**[ユーザー グループの追加]** を選択してユーザー グループの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="7617a-123">Choose **Add user group** to open the list of user groups.</span></span> <span data-ttu-id="7617a-124">このポリシーから除外するグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="7617a-124">Select the groups you want to exempt from this policy.</span></span>  

## <a name="modify-an-existing-policy"></a><span data-ttu-id="7617a-125">既存のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="7617a-125">Modify an existing policy</span></span>
### <a name="add-or-delete-user-groups"></a><span data-ttu-id="7617a-126">ユーザー グループを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="7617a-126">Add or delete user groups</span></span>

<span data-ttu-id="7617a-127">**[制限対象のユーザー グループ]** 一覧から**ユーザー グループを削除**するには、**[制限対象のユーザー グループ]** ブレードを開き、削除するユーザー グループを選択し、**省略記号 (...)** をクリックします。**[削除]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7617a-127">To **delete a user group** from the **restricted user groups** list, open the **Restricted user groups** blade, highlight the user group you want to delete, and click on the **ellipses(...)** to see the **Delete** option.</span></span> <span data-ttu-id="7617a-128">**[削除]** を選択すると、一覧からユーザー グループが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7617a-128">Choose **Delete** to remove the user group from the list.</span></span> <span data-ttu-id="7617a-129">手順は、**[制限対象のユーザー グループ]** 一覧からユーザー グループを削除する手順と同じです。</span><span class="sxs-lookup"><span data-stu-id="7617a-129">You can follow the same procedure to remove a user group from the **exempted user group** list.</span></span>


## <a name="next-steps"></a><span data-ttu-id="7617a-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="7617a-130">Next steps</span></span>
[<span data-ttu-id="7617a-131">最新の認証を使用していないアプリをブロックする</span><span class="sxs-lookup"><span data-stu-id="7617a-131">Block apps that do not have modern authentication</span></span>](block-apps-with-no-modern-authentication.md)
### <a name="see-also"></a><span data-ttu-id="7617a-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="7617a-132">See also</span></span>
[<span data-ttu-id="7617a-133">アプリ保護ポリシーを使用したアプリ データの保護</span><span class="sxs-lookup"><span data-stu-id="7617a-133">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
