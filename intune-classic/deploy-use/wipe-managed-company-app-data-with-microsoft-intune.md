---
title: "管理対象の業務用アプリのデータをワイプする"
description: "リモートでデバイスから会社のデータを選択的に削除する方法について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9aeee6e35c820778b11f00d59a5afe364b9774bd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="wipe-company-app-data-with-intune-mam"></a><span data-ttu-id="8e3aa-103">業務用アプリのデータを Intune MAM でワイプする</span><span class="sxs-lookup"><span data-stu-id="8e3aa-103">Wipe company app data with Intune MAM</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="8e3aa-104">デバイスが紛失や盗難にあった場合、または従業員が離職した場合、会社のアプリのデータがデバイスから削除されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-104">When a device is lost or stolen, or if the employee leaves your company, you want to make sure company app data is removed from the device.</span></span> <span data-ttu-id="8e3aa-105">ただし、個人のデータをデバイスから削除するのは好ましくありません。そのデバイスの所有者が従業員である場合はなおさらです。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-105">But you might not want to remove personal data on the device, especially if this is an employee-owned device.</span></span>

<span data-ttu-id="8e3aa-106">会社のアプリ データを選択して削除するには、このトピックの手順を使用してワイプ要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-106">To selectively remove company app data, create a wipe request by using the steps in this topic.</span></span> <span data-ttu-id="8e3aa-107">ワイプ要求の完了後、次にデバイス上でアプリが実行されると、そのアプリから会社のデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-107">After the request is finished, the next time the app runs on the device, company data is removed from the app.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="8e3aa-108">アプリケーションからネイティブ アドレス帳に直接同期された連絡先が削除されます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-108">Contacts synced directly from the app to the native address book are removed.</span></span> <span data-ttu-id="8e3aa-109">ネイティブ アドレス帳から別の外部ソースに同期された連絡先はワイプできません。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-109">Any contacts synced from the native address book to another external source cannot be wiped.</span></span> <span data-ttu-id="8e3aa-110">現在、これは Microsoft Outlook アプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-110">Currently, this only applies to the Microsoft Outlook app.</span></span>

## <a name="create-a-wipe-request"></a><span data-ttu-id="8e3aa-111">ワイプ要求の作成</span><span class="sxs-lookup"><span data-stu-id="8e3aa-111">Create a wipe request</span></span>

1.  <span data-ttu-id="8e3aa-112">[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-112">Sign in to the [Azure portal](https://portal.azure.com).</span></span>

2.  <span data-ttu-id="8e3aa-113">**[その他のサービス]** を選択し、フィルター ボックスに「**Intune**」と入力して、**[Intune App Protection (Intune アプリ保護)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-113">Choose **More Services**, type **Intune** in the filter textbox, and select **Intune App Protection**.</span></span> <span data-ttu-id="8e3aa-114">[Intune モバイル アプリケーション管理] ブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-114">The Intune mobile application management blade opens.</span></span>

    ![[新しいワイプ要求] ブレードのスクリーンショット](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  <span data-ttu-id="8e3aa-116">**[設定]** ブレードで、**[ワイプ要求]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-116">On the **Settings** blade, choose **Wipe requests**.</span></span>

3.  <span data-ttu-id="8e3aa-117">**[新しいワイプ要求]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-117">Choose  **New wipe request**.</span></span> <span data-ttu-id="8e3aa-118">**[新しいワイプ要求]** ブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-118">The **New wipe request** blade opens.</span></span>

    ![[新しいワイプ要求] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  <span data-ttu-id="8e3aa-120">**[ユーザー]** を選択して **[ユーザー]** ブレードを開き、アプリ データをワイプするユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-120">Choose **User** to open the **User** blade, and select the user whose app data you want to wipe.</span></span>

5.  <span data-ttu-id="8e3aa-121">**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-121">Choose **Device**.</span></span> <span data-ttu-id="8e3aa-122">これにより **[デバイス]** ブレードが開き、選択したユーザーに関連付けられているデバイスの一覧が表示されます。また、このブレードには 2 つの列があり、デバイス名 (ユーザーによって定義されるフレンドリ名) とデバイスの種類 (デバイスのプラットフォーム) が示されます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-122">This opens the **Device** blade that lists all the devices associated with the selected user, and also provides two columns, the device name, which is a friendly name defined by the user, and the device type, its device platform.</span></span> <span data-ttu-id="8e3aa-123">ワイプするデバイスを選びます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-123">Select the device you want to wipe.</span></span>

6.  <span data-ttu-id="8e3aa-124">**[新しいワイプ要求]** ブレードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-124">You are now back on the **New wipe request** blade.</span></span> <span data-ttu-id="8e3aa-125">**[OK]** を選択してワイプ要求を行います。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-125">Choose **Ok** to make a wipe request.</span></span> 

<span data-ttu-id="8e3aa-126">サービスでは、デバイス上の保護されているアプリごとにワイプ要求が作成および追跡され、そのワイプ要求にはユーザーが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-126">The service creates and tracks a separate wipe request for each protected app on the device, and the user associated with the wipe request.</span></span>

>[!NOTE]
> <span data-ttu-id="8e3aa-127">[Intune モバイル アプリケーション管理] ブレードで **[ワイプ要求]** タイルをクリックして、**ワイプ要求**を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-127">You can also create **Wipe requests** by clicking on the **Wipe request tile** from the Intune mobile application management blade.</span></span>

## <a name="monitor-your-wipe-requests"></a><span data-ttu-id="8e3aa-128">ワイプ要求を監視する</span><span class="sxs-lookup"><span data-stu-id="8e3aa-128">Monitor your wipe requests</span></span>

<span data-ttu-id="8e3aa-129">ワイプ要求の全体的状態、保留中の要求の数、失敗の数がまとめてある概要レポートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-129">You can have a summarized report that shows the overall status of the wipe request, and includes the number of pending requests and failures.</span></span> <span data-ttu-id="8e3aa-130">さらに詳しい情報が必要な場合、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-130">To get more details, follow these steps:</span></span>

1.  <span data-ttu-id="8e3aa-131">[Intune モバイル アプリケーション管理] ブレードで **[ワイプ要求]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-131">On the Intune mobile application management blade, click on the **Wipe requests** tile.</span></span>

2.  <span data-ttu-id="8e3aa-132">**[ワイプ要求]** ブレードで、**[ワイプ要求]** タイルを選択し、**[ワイプ要求]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-132">On the **Wipe request** blade, choose the **Wipe request** tile to open the **Wipe request** blade.</span></span>

3.  <span data-ttu-id="8e3aa-133">**[ワイプ要求]** ブレードでは、要求をユーザー別にグループ化して一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-133">On the **Wipe request** blade, you can see the list of your requests grouped by users.</span></span> <span data-ttu-id="8e3aa-134">ワイプ要求はデバイスで実行されている保護アプリごとに作成されるため、1 ユーザーに対する要求が複数ある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-134">Because the system creates a wipe request for each protected app running on the device, you might see multiple requests for a user.</span></span> <span data-ttu-id="8e3aa-135">状態は、ワイプ要求が **[保留中]**、**[失敗]**、または **[成功]**のいずれかであることを示します。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-135">The status indicates whether a wipe request is **pending**, **failed**, or **successful**.</span></span>

    ![[新しいワイプ要求] ブレードのスクリーンショット](../media/AppManagement/wipe-request-status-1.png)

<span data-ttu-id="8e3aa-137">さらに、デバイス名とそのデバイスの種類を確認することもできます。これは、レポートを読み取るときに役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-137">Additionally, you'll be able to see the device name, and its device type, which can be helpful when reading the reports.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="8e3aa-138">ワイプを実行するにはユーザーがアプリを開く必要があるため、ワイプには要求後最大で 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-138">The user must open the app for the wipe to occur, and the wipe may take up to 30 minutes after the request was made.</span></span>

## <a name="delete-a-wipe-request"></a><span data-ttu-id="8e3aa-139">ワイプ要求の削除</span><span class="sxs-lookup"><span data-stu-id="8e3aa-139">Delete a wipe request</span></span>

<span data-ttu-id="8e3aa-140">[保留中] 状態のワイプは、手動で削除するまで表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-140">Wipes with pending status are displayed until you manually delete them.</span></span>  <span data-ttu-id="8e3aa-141">ワイプ要求を手動で削除するには、次の手順を実行します</span><span class="sxs-lookup"><span data-stu-id="8e3aa-141">To manually delete a wipe request</span></span>

1.  <span data-ttu-id="8e3aa-142">[Intune モバイル アプリケーション管理] ブレードで **[ワイプ要求]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-142">On the Intune mobile application management blade, click on the **Wipe requests** tile.</span></span>

2.  <span data-ttu-id="8e3aa-143">**[ワイプ要求]** ブレードで、**[ワイプ要求]** タイルを選択し、**[ワイプ要求]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-143">On the **Wipe request** blade, choose the **Wipe request** tile to open the **Wipe request** blade.</span></span>

3.  <span data-ttu-id="8e3aa-144">削除するワイプ要求を右クリックし、**[Delete wipe request (ワイプ要求の削除)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-144">Right-click on the wipe request you want to delete, then choose **Delete wipe request**.</span></span>

    ![[新しいワイプ要求] ブレードのスクリーンショット](../media/AppManagement/delete-wipe-request.png)

4.  <span data-ttu-id="8e3aa-146">削除を確認するメッセージが表示されたら、**[はい]** または **[いいえ]** を選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e3aa-146">You're prompted to confirm the deletion, choose **Yes** or **No**, then click **OK**.</span></span>


### <a name="see-also"></a><span data-ttu-id="8e3aa-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e3aa-147">See also</span></span>
[<span data-ttu-id="8e3aa-148">モバイル アプリケーション管理ポリシーを使用してデータを保護する</span><span class="sxs-lookup"><span data-stu-id="8e3aa-148">Protect app data using mobile app management policies </span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[<span data-ttu-id="8e3aa-149">Azure Portal の使用</span><span class="sxs-lookup"><span data-stu-id="8e3aa-149">Using the Azure portal</span></span>](azure-portal-for-microsoft-intune-mam-policies.md)
