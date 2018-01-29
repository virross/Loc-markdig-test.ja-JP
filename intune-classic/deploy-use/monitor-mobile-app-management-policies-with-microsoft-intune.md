---
title: "Microsoft Intune で MAM ポリシーを監視する"
description: "ポリシーを持つユーザー数を確認し、詳細を調べるためにドリルダウンします。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f42f76b1c7ab830ab7afda031a18187206b39b72
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="monitor-app-protection-policies-with-microsoft-intune"></a><span data-ttu-id="b4f0d-103">Microsoft Intune でアプリ保護ポリシーを監視する</span><span class="sxs-lookup"><span data-stu-id="b4f0d-103">Monitor app protection policies with Microsoft Intune</span></span>
<span data-ttu-id="b4f0d-104">ユーザーに適用したアプリ保護ポリシーのコンプライアンス状態を監視できます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-104">You can monitor the compliance status of the app protection policies that you've applied to users.</span></span> <span data-ttu-id="b4f0d-105">アプリ保護ポリシーによって影響を受けるユーザー、コンプライアンスの状態、ユーザーに対して発生する可能性がある問題に関する情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-105">You'll be able to find information about the users affected by the app protection policies, its compliance status, and any issues that your users might be experiencing.</span></span>

<span data-ttu-id="b4f0d-106">コンプライアンス状態は 3 つの異なる場所で監視できます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-106">There are three different places to monitor the compliance status:</span></span>

-   <span data-ttu-id="b4f0d-107">概要ビュー</span><span class="sxs-lookup"><span data-stu-id="b4f0d-107">Summary view</span></span>

-   <span data-ttu-id="b4f0d-108">詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="b4f0d-108">Detailed view</span></span>

-   <span data-ttu-id="b4f0d-109">レポート ビュー</span><span class="sxs-lookup"><span data-stu-id="b4f0d-109">Reporting view</span></span>

## <a name="summary-view"></a><span data-ttu-id="b4f0d-110">概要ビュー</span><span class="sxs-lookup"><span data-stu-id="b4f0d-110">Summary view</span></span>

<span data-ttu-id="b4f0d-111">概要ビューは、次の 3 つの手順で開きます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-111">Follow the three steps below to open the Summary view:</span></span>

1. <span data-ttu-id="b4f0d-112">[Azure Portal](https://portal.azure.com) に移動し、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-112">Go to the [Azure portal](https://portal.azure.com), and enter your credentials.</span></span>
2. <span data-ttu-id="b4f0d-113">**[その他のサービス]** を選択し、フィルター ボックスに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-113">Choose **More Services**, and type **Intune** in the filter textbox.</span></span>
3. <span data-ttu-id="b4f0d-114">**[Intune アプリ保護]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-114">Choose **Intune App Protection**.</span></span>

<span data-ttu-id="b4f0d-115">**[Intune モバイル アプリケーション管理]** ブレードでは、コンプライアンス状態の概要を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-115">On **Intune mobile application management** blade, you can see a summary of the compliance status:</span></span>

![[Intune モバイル アプリケーション管理] ブレードの [概要] タイル](../media/mam-azure-portal-user-status-summary.png)

-   <span data-ttu-id="b4f0d-117">**[ユーザー]**: 作業コンテキストのポリシーに関連付けられているアプリを使っている社内ユーザーの合計数。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-117">**Users**: The total number of users in your company who are using an app which is associated with a policy in a work context.</span></span>

-   <span data-ttu-id="b4f0d-118">**[ポリシーによって管理されています]**: 作業コンテキストで割り当てられたポリシーがある、アプリを使ったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-118">**MANAGED BY POLICY**: The number of users who have used an app who have a policy assigned to them in a work context.</span></span>

-   <span data-ttu-id="b4f0d-119">**[ポリシーなし]**: 作業コンテキストのポリシーのターゲットになっていないアプリを使っているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-119">**NO POLICY**: The number of users who are using an app that is not targeted by any policy in a work context.</span></span> <span data-ttu-id="b4f0d-120">これらのユーザーをポリシーに追加することを検討できます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-120">You might consider adding these users to the policy.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b4f0d-121">プラットフォームごとに複数のポリシーがある場合、少なくとも 1 つのポリシーが割り当てられていると、ユーザーはポリシーによって管理されているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-121">If you have multiple policies per platform, a user will be considered managed by policy when they have at least one policy assigned to them.</span></span>

- <span data-ttu-id="b4f0d-122">**[フラグ付きのユーザー]**: 問題が発生しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-122">**Flagged users**: The number of users who are experiencing issues.</span></span> <span data-ttu-id="b4f0d-123">**[フラグ付きのユーザー]** では、現時点で脱獄されたデバイスを使用しているユーザーのみが報告されます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-123">Currently, only users with jailbroken devices are reported under **Flagged users**.</span></span>


## <a name="detailed-view"></a><span data-ttu-id="b4f0d-124">詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="b4f0d-124">Detailed view</span></span>
<span data-ttu-id="b4f0d-125">**[ユーザーの状態]** タイル (デバイス OS プラットフォームに基づく) と **[フラグ付きのユーザー]** タイルを選択すると、概要の詳細ビューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-125">You can get to the detailed view of the summary by choosing the **User status** tile (based on device OS platform), and the **Flagged users** tile.</span></span>

### <a name="user-status"></a><span data-ttu-id="b4f0d-126">ユーザーの状態</span><span class="sxs-lookup"><span data-stu-id="b4f0d-126">User status</span></span>
<span data-ttu-id="b4f0d-127">1 人のユーザーを検索し、そのユーザーのコンプライアンス状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-127">You can search for a single user and check the compliance status for that user.</span></span> <span data-ttu-id="b4f0d-128">**[アプリ レポート]** ブレードには、選択したユーザーの次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-128">The **App reporting** blade shows the following information for a selected user:</span></span>
- <span data-ttu-id="b4f0d-129">ユーザー アカウントに関連付けられているデバイス</span><span class="sxs-lookup"><span data-stu-id="b4f0d-129">Devices that are associated with the user account</span></span>

- <span data-ttu-id="b4f0d-130">デバイスのアプリとアプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="b4f0d-130">Apps with an app protection policy on the device</span></span>

- <span data-ttu-id="b4f0d-131">状態:</span><span class="sxs-lookup"><span data-stu-id="b4f0d-131">Status:</span></span>

  - <span data-ttu-id="b4f0d-132">**[チェックイン済み]**: ポリシーはユーザーに展開され、アプリが 1 回以上作業コンテキストで使用されました。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-132">**Checked in**: The policy was deployed to the user, and the app was used in the work context at least once.</span></span>

  - <span data-ttu-id="b4f0d-133">**[チェックインされていません]**: ポリシーはユーザーに展開されましたが、それ以降にアプリが作業コンテキストで使用されていません。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-133">**Not checked in**: The policy was deployed to the user, but the app has not been used in the work context since then.</span></span>

>[!NOTE]
> <span data-ttu-id="b4f0d-134">検索したユーザーにアプリ保護ポリシーが展開されていない場合は、そのユーザーがいずれのアプリ保護ポリシーの対象でもないことを知らせるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-134">If the users you searched for does not have the app protection policy deployed to them, you'll see a message informing you that the user is not targeted by any app protection policies.</span></span>

<span data-ttu-id="b4f0d-135">ユーザーのレポートを表示するには次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-135">To see the reporting for a user, follow these steps:</span></span>

1.  <span data-ttu-id="b4f0d-136">ユーザーを選択するには、**[概要]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-136">To select a user, choose the **Summary** tile.</span></span>

    ![スクリーンショット 3](../media/MAM-reporting-6.png)

2. <span data-ttu-id="b4f0d-138">表示される **[アプリ レポート]** ブレードで、**[ユーザーの選択]** を選択して Azure Active Directory ユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-138">On the **App reporting** blade that opens, choose **Select user** to search for an Azure Active Directory user.</span></span>

    ![[アプリ レポート] ブレードのユーザー選択オプション](../media/MAM-reporting-2.png)

3. <span data-ttu-id="b4f0d-140">リストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-140">Select the user from the list.</span></span> <span data-ttu-id="b4f0d-141">そのユーザーのコンプライアンス状態の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-141">You will see the details of the compliance status for that user.</span></span>

### <a name="flagged-users"></a><span data-ttu-id="b4f0d-142">フラグ付きのユーザー</span><span class="sxs-lookup"><span data-stu-id="b4f0d-142">Flagged users</span></span>
<span data-ttu-id="b4f0d-143">詳細ビューには、エラー メッセージ、エラー発生時にアクセスされていたアプリ、影響を受けたデバイス OS プラットフォーム、タイムスタンプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-143">The detailed view shows the error message, the app that was accessed when the error happened, the device OS platform affected, and a time stamp.</span></span>

## <a name="reporting-view"></a><span data-ttu-id="b4f0d-144">レポート ビュー</span><span class="sxs-lookup"><span data-stu-id="b4f0d-144">Reporting view</span></span>

<span data-ttu-id="b4f0d-145">詳細ビューと同じレポートと追加のレポートがあります。アプリ保護ポリシーのコンプライアンス状態の確認に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-145">You can find the same reports from the Detailed view, and additional reports to help you with the app protection policy compliance status:</span></span>

![スクリーンショット 4](../media/MAM-reporting-7.png)

-   <span data-ttu-id="b4f0d-147">**アプリ保護ユーザー レポート:** 上の「詳細ビュー」セクションの**ユーザーの状態**レポートと同じ情報がまとめられています。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-147">**App protection user report:** It outlines the same information you can find at the **User status** report under the Detailed view section above.</span></span>

-   <span data-ttu-id="b4f0d-148">**アプリ保護アプリ レポート:** 2 つの異なるアプリ保護状態があります。管理者はいずれかを選択し、レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-148">**App protection app report:** It provides two different app protection statuses that admins can select before generating the report.</span></span> <span data-ttu-id="b4f0d-149">状態には、保護と非保護があります。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-149">The statuses can be protected or unprotected.</span></span>

    -   <span data-ttu-id="b4f0d-150">管理対象 MAM アクティビティ (保護) のユーザーの状態: このレポートには、管理対象 MAM アプリ別のアクティビティがユーザー別にまとめられています。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-150">User status for managed MAM activity (Protected): This report outlines the activity of each managed MAM app, on a per user basis.</span></span>

        -   <span data-ttu-id="b4f0d-151">アプリ保護ポリシーの対象になっているすべてのアプリがユーザーごとに表示されます。アプリ保護ポリシーでチェックインしたときの各アプリの状態が分析されます。または、アプリ保護ポリシーの対象ではあっても、アプリがチェックインされていないことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-151">It shows all apps targeted by app protection policies for each user, and break down the status of each app as checked in with app protection policies, or that was targeted with an app protection policy but the app was never checked in.</span></span>
<br></br>
    -   <span data-ttu-id="b4f0d-152">非管理対象 MAM アクティビティ (非保護) のユーザーの状態: このレポートには、現在管理対象ではない MAM 対応アプリのアクティビティがユーザーごとにまとめられています。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-152">User status for unmanaged MAM activity (Unprotected): This report outlines the activity of MAM-enabled apps that are currently unmanaged, on a per user basis.</span></span> <span data-ttu-id="b4f0d-153">次の理由で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-153">This might happen according to the following reasons:</span></span>

        -   <span data-ttu-id="b4f0d-154">これらのアプリは、現在のところ、アプリ保護ポリシーの対象になっていないユーザーまたはアプリにより使われています。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-154">These apps are either being used by a user or an app that is not currently targeted by an app protection policy.</span></span>

        -   <span data-ttu-id="b4f0d-155">すべてのアプリがチェックインされていますが、アプリ保護ポリシーが与えられていません。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-155">All apps are checked in, but aren't getting any app protection policies.</span></span>

![スクリーンショット 2](../media/MAM-reporting-4.png)

## <a name="table-grouping"></a><span data-ttu-id="b4f0d-157">テーブルのグループ化</span><span class="sxs-lookup"><span data-stu-id="b4f0d-157">Table grouping</span></span>

<span data-ttu-id="b4f0d-158">**アプリ保護のユーザー レポート**のデータが表示されたら、次でデータを集計できます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-158">Once the **App protection user report** data shows up, you can aggregate data by the following:</span></span>

- <span data-ttu-id="b4f0d-159">**[検証結果]**: アプリ保護の状態 (エラー、警告、または成功) 別にグループ化されてデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-159">**Validation result:** The data shows up grouped by app protection status, which can be failure, warning or success.</span></span>
- <span data-ttu-id="b4f0d-160">**[アプリ名]**: アプリ (実際のアプリ名) とエラー、警告、または成功別にグループ化されてデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-160">**App name:** The data shows up grouped by apps (the actual app name) with failure, warning or success.</span></span>

## <a name="export-app-protection-activities-to-csv"></a><span data-ttu-id="b4f0d-161">CSV へのアプリ保護アクティビティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="b4f0d-161">Export app protection activities to CSV</span></span>

<span data-ttu-id="b4f0d-162">アプリ保護ポリシーのすべてのアクティビティを 1 つの .csv ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-162">You can export all your app protection policy activities to a single .csv file.</span></span> <span data-ttu-id="b4f0d-163">これは、ユーザーから報告されたアプリ保護のすべての状態を分析するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-163">This can be helpful to analyze all the app protection statuses reported from the users.</span></span>

<span data-ttu-id="b4f0d-164">アプリ保護レポートを生成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-164">Follow these steps to generate the App protection report:</span></span>

1. <span data-ttu-id="b4f0d-165">[Intune モバイル アプリケーション管理] ブレードで [App protection report (アプリ保護レポート)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-165">On the Intune mobile application management blade, choose App protection report.</span></span>

    ![スクリーンショット 6](../media/app-protection-report-csv-2.png)

2. <span data-ttu-id="b4f0d-167">[はい] を選択して、レポートを保存します。次に、[名前を付けて保存] を選択し、レポートを保存するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4f0d-167">Choose Yes to save your report, then choose Save As and select the folder you want to save the report in.</span></span>

    ![スクリーンショット 7](../media/app-protection-report-csv-1.png)

## <a name="see-also"></a><span data-ttu-id="b4f0d-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4f0d-169">See also</span></span>
[<span data-ttu-id="b4f0d-170">iOS アプリ間のデータ転送を管理する</span><span class="sxs-lookup"><span data-stu-id="b4f0d-170">Manage data transfer between iOS apps</span></span>](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [<span data-ttu-id="b4f0d-171">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="b4f0d-171">What to expect when your Android app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-android)
* [<span data-ttu-id="b4f0d-172">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="b4f0d-172">What to expect when your iOS app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-ios)
