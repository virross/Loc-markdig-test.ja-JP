---
title: "アプリから会社のデータのみをワイプする方法"
titleSuffix: Azure portal
description: "Microsoft Intune でアプリを選択的にワイプする方法について説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 67d3333a7c6c56b032a9f0e1800b453924d677eb
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a><span data-ttu-id="18885-103">Intune で管理されているアプリから会社のデータをワイプする方法</span><span class="sxs-lookup"><span data-stu-id="18885-103">How to wipe only corporate data from Intune-managed apps</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="18885-104">デバイスが紛失や盗難にあった場合、または従業員が離職した場合、会社のアプリのデータがデバイスから削除されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18885-104">When a device is lost or stolen, or if the employee leaves your company, you want to make sure company app data is removed from the device.</span></span> <span data-ttu-id="18885-105">ただし、個人のデータをデバイスから削除するのは好ましくありません。そのデバイスの所有者が従業員である場合はなおさらです。</span><span class="sxs-lookup"><span data-stu-id="18885-105">But you might not want to remove personal data on the device, especially if this is an employee-owned device.</span></span>

>[!NOTE]
> <span data-ttu-id="18885-106">現在、Intune 管理対象アプリから会社のデータをワイプできるプラットフォームは、iOS と Android の 2 つです。</span><span class="sxs-lookup"><span data-stu-id="18885-106">The iOS and Android platforms are the two platforms currently supported for wiping corporate data from Intune managed apps.</span></span>

<span data-ttu-id="18885-107">会社のアプリ データを選択して削除するには、このトピックの手順を使用してワイプ要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="18885-107">To selectively remove company app data, create a wipe request by using the steps in this topic.</span></span> <span data-ttu-id="18885-108">ワイプ要求の完了後、次にデバイス上でアプリが実行されると、そのアプリから会社のデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="18885-108">After the request is finished, the next time the app runs on the device, company data is removed from the app.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="18885-109">アプリケーションからネイティブ アドレス帳に直接同期された連絡先が削除されます。</span><span class="sxs-lookup"><span data-stu-id="18885-109">Contacts synced directly from the app to the native address book are removed.</span></span> <span data-ttu-id="18885-110">ネイティブ アドレス帳から別の外部ソースに同期された連絡先はワイプできません。</span><span class="sxs-lookup"><span data-stu-id="18885-110">Any contacts synced from the native address book to another external source cannot be wiped.</span></span> <span data-ttu-id="18885-111">現在、これは Microsoft Outlook アプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="18885-111">Currently, this only applies to the Microsoft Outlook app.</span></span>

## <a name="create-a-wipe-request"></a><span data-ttu-id="18885-112">ワイプ要求の作成</span><span class="sxs-lookup"><span data-stu-id="18885-112">Create a wipe request</span></span>

1.  <span data-ttu-id="18885-113">[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="18885-113">Sign in to the [Azure portal](https://portal.azure.com).</span></span>

2.  <span data-ttu-id="18885-114">**[その他のサービス]** を選択し、フィルター ボックスに「**Intune**」と入力して、**[Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="18885-114">Choose **More Services**, type **Intune** in the filter textbox, and select **Intune**.</span></span> <span data-ttu-id="18885-115">Intune ブレードが開いたら、**[モバイル アプリ]** ブレードを選びます。</span><span class="sxs-lookup"><span data-stu-id="18885-115">The Intune blade opens, choose the **Mobile apps** blade.</span></span>

    ![Microsoft Intune ブレードのスクリーンショット](./media/apps-selective-wipe01.png)

3.  <span data-ttu-id="18885-117">**[Mobile Apps]** ブレードで、**[アプリの選択的ワイプ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="18885-117">On the **Mobile apps blade**, choose **App selective wipe**.</span></span>

4.  <span data-ttu-id="18885-118">**[新しいワイプ要求]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="18885-118">Choose  **New wipe request**.</span></span> <span data-ttu-id="18885-119">**[新しいワイプ要求]** ブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="18885-119">The **New wipe request** blade opens.</span></span>

    ![[新しいワイプ要求] ブレードのスクリーンショット](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  <span data-ttu-id="18885-121">**[ユーザー]** を選択して **[ユーザー]** ブレードを開き、アプリ データをワイプするユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="18885-121">Choose **User** to open the **User** blade, and select the user whose app data you want to wipe.</span></span>

6.  <span data-ttu-id="18885-122">次に、**[新しいワイプ要求]** ブレードで **[デバイス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="18885-122">Next, choose **Device** from the **New wipe request** blade.</span></span> <span data-ttu-id="18885-123">**[デバイスの選択]** ブレードが開き、選んだユーザーに関連付けられているデバイスの一覧が表示されます。また、このブレードには 2 つの列があり、デバイス名 (ユーザーによって定義されるフレンドリ名) とデバイスの種類 (デバイスのプラットフォーム) が示されます。</span><span class="sxs-lookup"><span data-stu-id="18885-123">This opens the **Select Device** blade that lists all the devices associated with the selected user, and also provides two columns, the device name, which is a friendly name defined by the user, and the device type, its device platform.</span></span> <span data-ttu-id="18885-124">ワイプするデバイスを選びます。</span><span class="sxs-lookup"><span data-stu-id="18885-124">Select the device you want to wipe.</span></span>

7.  <span data-ttu-id="18885-125">**[新しいワイプ要求]** ブレードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="18885-125">You are now back on the **New wipe request** blade.</span></span> <span data-ttu-id="18885-126">**[OK]** を選択してワイプ要求を行います。</span><span class="sxs-lookup"><span data-stu-id="18885-126">Choose **Ok** to make a wipe request.</span></span>

<span data-ttu-id="18885-127">サービスでは、デバイス上の保護されているアプリごとにワイプ要求が作成および追跡され、そのワイプ要求にはユーザーが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="18885-127">The service creates and tracks a separate wipe request for each protected app on the device, and the user associated with the wipe request.</span></span>

## <a name="monitor-your-wipe-requests"></a><span data-ttu-id="18885-128">ワイプ要求を監視する</span><span class="sxs-lookup"><span data-stu-id="18885-128">Monitor your wipe requests</span></span>

<span data-ttu-id="18885-129">ワイプ要求の全体的状態、保留中の要求の数、失敗の数がまとめてある概要レポートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="18885-129">You can have a summarized report that shows the overall status of the wipe request, and includes the number of pending requests and failures.</span></span> <span data-ttu-id="18885-130">さらに詳しい情報が必要な場合、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="18885-130">To get more details, follow these steps:</span></span>

1.  <span data-ttu-id="18885-131">**[Mobile Apps] - [アプリの選択的ワイプ]** ブレードでは、要求をユーザー別にグループ化して一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="18885-131">On the **Mobile Apps - App selective wipe** blade, you can see the list of your requests grouped by users.</span></span> <span data-ttu-id="18885-132">ワイプ要求はデバイスで実行されている保護アプリごとに作成されるため、1 ユーザーに対する要求が複数ある場合があります。</span><span class="sxs-lookup"><span data-stu-id="18885-132">Because the system creates a wipe request for each protected app running on the device, you might see multiple requests for a user.</span></span> <span data-ttu-id="18885-133">状態は、ワイプ要求が **[保留中]**、**[失敗]**、または **[成功]**のいずれかであることを示します。</span><span class="sxs-lookup"><span data-stu-id="18885-133">The status indicates whether a wipe request is **pending**, **failed**, or **successful**.</span></span>

    ![[アプリの選択的ワイプ] ブレードでのワイプ要求の状態のスクリーンショット](./media/wipe-request-status-1.png)

<span data-ttu-id="18885-135">さらに、デバイス名とそのデバイスの種類を確認することもできます。これは、レポートを読み取るときに役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="18885-135">Additionally, you'll be able to see the device name, and its device type, which can be helpful when reading the reports.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="18885-136">ワイプを実行するにはユーザーがアプリを開く必要があるため、ワイプには要求後最大で 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="18885-136">The user must open the app for the wipe to occur, and the wipe may take up to 30 minutes after the request was made.</span></span>

## <a name="delete-a-wipe-request"></a><span data-ttu-id="18885-137">ワイプ要求の削除</span><span class="sxs-lookup"><span data-stu-id="18885-137">Delete a wipe request</span></span>

<span data-ttu-id="18885-138">[保留中] 状態のワイプは、手動で削除するまで表示されます。</span><span class="sxs-lookup"><span data-stu-id="18885-138">Wipes with pending status are displayed until you manually delete them.</span></span>  <span data-ttu-id="18885-139">ワイプ要求を手動で削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="18885-139">To manually delete a wipe request:</span></span>

1.  <span data-ttu-id="18885-140">**[Mobile Apps] - [アプリの選択的ワイプ]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="18885-140">On the **Mobile Apps - App selective wipe** blade.</span></span>

2.  <span data-ttu-id="18885-141">一覧で削除するワイプ要求を右クリックし、**[ワイプ要求の削除]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="18885-141">From the list, right-click on the wipe request you want to delete, then choose **Delete wipe request**.</span></span>

    ![[アプリの選択的ワイプ] ブレードでのワイプ要求の一覧のスクリーンショット](./media/delete-wipe-request.png)

3.  <span data-ttu-id="18885-143">削除を確認するメッセージが表示されたら、**[はい]** または **[いいえ]** を選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18885-143">You're prompted to confirm the deletion, choose **Yes** or **No**, then click **OK**.</span></span>

### <a name="see-also"></a><span data-ttu-id="18885-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="18885-144">See also</span></span>
[<span data-ttu-id="18885-145">アプリ保護ポリシーとは</span><span class="sxs-lookup"><span data-stu-id="18885-145">What's app protection policy</span></span>](app-protection-policy.md)

[<span data-ttu-id="18885-146">アプリ管理とは</span><span class="sxs-lookup"><span data-stu-id="18885-146">What's app management</span></span>](app-management.md)
