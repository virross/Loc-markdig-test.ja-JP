---
title: "管理者の役割用のコンソール ビューをカスタマイズする"
description: "このトピックは、Intune 管理コンソール ビューをフィルター処理して、管理者がそれぞれの役割に応じて必要な項目のみが表示されるように設定するときに役立ちます。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 757d1b0405e757af3a90c38778a3b1fea85c026c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="customize-intune-console-views-according-to-admin-roles"></a><span data-ttu-id="cea2f-103">管理者の役割に応じて Intune コンソール ビューをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="cea2f-103">Customize Intune console views according to admin roles</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="cea2f-104">Microsoft Intune 管理コンソール ビューをフィルター処理して、管理者がそれぞれの役割に応じて確認する必要がある項目のみが表示されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="cea2f-104">You can filter the Microsoft Intune administration console view to allow your admins to see only the items they need to see for their role.</span></span> <span data-ttu-id="cea2f-105">たとえば、管理コンソールのオペレーターにのみ、マルウェア定義の更新やデバイスのパスコードのリセットを許可できます。</span><span class="sxs-lookup"><span data-stu-id="cea2f-105">For example, you can allow only admin console operators to update malware definitions or reset the passcode on devices.</span></span> <span data-ttu-id="cea2f-106">これは、特定のユーザーに割り当てる事前設定された**指定**を使用することで行います。</span><span class="sxs-lookup"><span data-stu-id="cea2f-106">You do this by using preset **designations** that you assign to specific users.</span></span> <span data-ttu-id="cea2f-107">これらのユーザーが管理コンソールにアクセスすると、そのユーザーに対する指定に応じて、特定のアイテムだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cea2f-107">When these users access the admin console, they can only see items that are specific to their designation.</span></span>

## <a name="to-create-a-custom-view"></a><span data-ttu-id="cea2f-108">カスタム ビューを作成するには</span><span class="sxs-lookup"><span data-stu-id="cea2f-108">To create a custom view</span></span>

1. <span data-ttu-id="cea2f-109">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理]** &gt; **[サービス管理者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cea2f-109">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **Service Administrators**.</span></span>

2. <span data-ttu-id="cea2f-110">サービス管理者の一覧から、指定を変更するユーザーを選択し、**[アクセスの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cea2f-110">From the list of service administrators, choose the user whose designation you want to change, and then choose **Manage Access**.</span></span>

3. <span data-ttu-id="cea2f-111">**[アクセスの管理]** ダイアログ ボックスで、選択したユーザーに付与するアクセス レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="cea2f-111">In the **Manage Access** dialog box, choose the level of access that you want to give the selected user.</span></span> <span data-ttu-id="cea2f-112">次の項目から選択できます。</span><span class="sxs-lookup"><span data-stu-id="cea2f-112">You can choose from:</span></span>

   -   <span data-ttu-id="cea2f-113">**フル アクセス**</span><span class="sxs-lookup"><span data-stu-id="cea2f-113">**Full access**</span></span>
   -   <span data-ttu-id="cea2f-114">**読み取り専用アクセス**</span><span class="sxs-lookup"><span data-stu-id="cea2f-114">**Read-only access**</span></span>
   -   <span data-ttu-id="cea2f-115">**ヘルプデスク - グループ ノード**</span><span class="sxs-lookup"><span data-stu-id="cea2f-115">**Helpdesk - Groups node**</span></span>

   <span data-ttu-id="cea2f-116">フル アクセスと読み取り専用アクセスは、特に説明することはありません。</span><span class="sxs-lookup"><span data-stu-id="cea2f-116">Full access and read-only access are self-explanatory.</span></span> <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the Intune admin console:--->

   <span data-ttu-id="cea2f-117">**ヘルプデスク - グループ ノード**は、次に示す管理者が確認できる項目と実行できる操作を制限します。</span><span class="sxs-lookup"><span data-stu-id="cea2f-117">**Helpdesk - Groups Node** restricts what the admin can see and do to the following:</span></span>

   -   <span data-ttu-id="cea2f-118">ユーザーとデバイスの一覧を表示する。</span><span class="sxs-lookup"><span data-stu-id="cea2f-118">See lists of users and devices.</span></span> <span data-ttu-id="cea2f-119">管理者は、フィルターを使用してビューを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cea2f-119">The admin cannot use filters to modify the view.</span></span> <span data-ttu-id="cea2f-120">ただし、グループ フィルターを使用して、管理者に表示される内容を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cea2f-120">However, you can use group filtering to modify what the admin can see.</span></span> <span data-ttu-id="cea2f-121">詳しくは、「[Microsoft Intune でユーザーとデバイスの管理にグループを使用する](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cea2f-121">For more information, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span></span>

   -   <span data-ttu-id="cea2f-122">ユーザーとデバイスの一覧を印刷する。</span><span class="sxs-lookup"><span data-stu-id="cea2f-122">Print the list of users and devices</span></span>

   -   <span data-ttu-id="cea2f-123">ユーザーとデバイスの一覧をエクスポートする。</span><span class="sxs-lookup"><span data-stu-id="cea2f-123">Export the list of users and devices</span></span>

   -   <span data-ttu-id="cea2f-124">ユーザーまたはデバイスのプロパティを表示する。</span><span class="sxs-lookup"><span data-stu-id="cea2f-124">View the properties of a user or device</span></span>

   -   <span data-ttu-id="cea2f-125">次のリモート タスクを実行する。</span><span class="sxs-lookup"><span data-stu-id="cea2f-125">Perform the following remote tasks:</span></span>

       -   <span data-ttu-id="cea2f-126">マルウェアのフル スキャンの実行</span><span class="sxs-lookup"><span data-stu-id="cea2f-126">Run a full malware scan</span></span>

       -   <span data-ttu-id="cea2f-127">マルウェアのクイック スキャンの実行</span><span class="sxs-lookup"><span data-stu-id="cea2f-127">Run a quick malware scan</span></span>

       -   <span data-ttu-id="cea2f-128">コンピューターの再起動</span><span class="sxs-lookup"><span data-stu-id="cea2f-128">Restart a computer</span></span>

       -   <span data-ttu-id="cea2f-129">マルウェア定義の更新</span><span class="sxs-lookup"><span data-stu-id="cea2f-129">Update malware definitions</span></span>

       -   <span data-ttu-id="cea2f-130">ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="cea2f-130">Refresh policies</span></span>

       -   <span data-ttu-id="cea2f-131">インベントリの更新</span><span class="sxs-lookup"><span data-stu-id="cea2f-131">Refresh inventory</span></span>

       -   <span data-ttu-id="cea2f-132">デバイスのリモート ロック</span><span class="sxs-lookup"><span data-stu-id="cea2f-132">Lock a device remotely</span></span>

       -   <span data-ttu-id="cea2f-133">パスコードのリセット</span><span class="sxs-lookup"><span data-stu-id="cea2f-133">Reset a passcode</span></span>

<span data-ttu-id="cea2f-134">構成した管理者が次に Intune 管理コンソールを開いたとき、指定したアクセス レベルが与えられます。</span><span class="sxs-lookup"><span data-stu-id="cea2f-134">When the admin that you configured next opens the Intune admin console, they will be given the level of access that you designated.</span></span>
