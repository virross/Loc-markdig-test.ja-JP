---
title: "アプリ保護ポリシーを監視する方法"
titleSuffix: Azure portal
description: "ポリシーを持つユーザー数を確認し、詳細を調べるためにドリルダウンします。\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ddb9deaae8fed504daa8e4ba5250208c6458506
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-monitor-app-protection-policies"></a><span data-ttu-id="a0334-103">アプリ保護ポリシーを監視する方法</span><span class="sxs-lookup"><span data-stu-id="a0334-103">How to monitor app protection policies</span></span>
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a0334-104">このトピックでは、**Azure Portal を使用していない場合に**、Intune クラシック ポータルで[アプリ保護ポリシーを作成する方法](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0334-104">**If you are not in the Azure portal**, this topic explains [how to create app protection policies](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) in the Intune classic portal.</span></span>


<span data-ttu-id="a0334-105">[Azure Portal](https://portal.azure.com) の Intune アプリ保護ブレードでユーザーに適用したモバイル アプリ管理 (MAM) ポリシーのコンプライアンス状態を監視できます。</span><span class="sxs-lookup"><span data-stu-id="a0334-105">You can monitor the compliance status of the mobile app management (MAM) policies that you've applied to users at the Intune app protection blade on the [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="a0334-106">MAM ポリシーによって影響を受けるユーザー、コンプライアンスの状態、ユーザーに対して発生する可能性がある問題に関する情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a0334-106">You'll be able to find information about the users affected by the MAM policies, its compliance status, and any issues that your users might be experiencing.</span></span>

<span data-ttu-id="a0334-107">コンプライアンス状態は 3 つの異なる場所で監視できます。</span><span class="sxs-lookup"><span data-stu-id="a0334-107">There are three different places to monitor the compliance status:</span></span>

-   <span data-ttu-id="a0334-108">概要ビュー</span><span class="sxs-lookup"><span data-stu-id="a0334-108">Summary view</span></span>

-   <span data-ttu-id="a0334-109">詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="a0334-109">Detailed view</span></span>

-   <span data-ttu-id="a0334-110">レポート ビュー</span><span class="sxs-lookup"><span data-stu-id="a0334-110">Reporting view</span></span>

## <a name="summary-view"></a><span data-ttu-id="a0334-111">概要ビュー</span><span class="sxs-lookup"><span data-stu-id="a0334-111">Summary view</span></span>

1. <span data-ttu-id="a0334-112">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a0334-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a0334-113">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a0334-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="a0334-114">**[Intune]** ブレードで、**[モバイル アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a0334-114">On the **Intune** blade, choose **Mobile apps**.</span></span>
4. <span data-ttu-id="a0334-115">**[モバイル アプリ]** ワークロードで、**[監視]** > **[アプリ保護ユーザー状態]** の順に選択して、概要ビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0334-115">In the **Mobile apps** workload, choose **Monitor** > **App protection user status**, to see the summary view:</span></span>

![[Intune モバイル アプリケーション管理] ブレードの [概要] タイル](./media/app-protection-user-status-summary.png)

-   <span data-ttu-id="a0334-117">**[ユーザー]**: 作業コンテキストのポリシーに関連付けられているアプリを使っている社内ユーザーの合計数。</span><span class="sxs-lookup"><span data-stu-id="a0334-117">**Users**: The total number of users in your company who are using an app which is associated with a policy in a work context.</span></span>

-   <span data-ttu-id="a0334-118">**[ポリシーによって管理されています]**: 作業コンテキストで割り当てられたポリシーがある、アプリを使ったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="a0334-118">**MANAGED BY POLICY**: The number of users who have used an app who have a policy assigned to them in a work context.</span></span>

-   <span data-ttu-id="a0334-119">**[ポリシーなし]**: 作業コンテキストのポリシーのターゲットになっていないアプリを使っているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="a0334-119">**NO POLICY**: The number of users who are using an app that is not targeted by any policy in a work context.</span></span> <span data-ttu-id="a0334-120">これらのユーザーをポリシーに追加することを検討できます。</span><span class="sxs-lookup"><span data-stu-id="a0334-120">You might consider adding these users to the policy.</span></span>
    > [!NOTE]
    > <span data-ttu-id="a0334-121">プラットフォームごとに複数のポリシーがある場合、少なくとも 1 つのポリシーが割り当てられていると、ユーザーはポリシーによって管理されているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a0334-121">If you have multiple policies per platform, a user will be considered managed by policy when they have at least one policy assigned to them.</span></span>

- <span data-ttu-id="a0334-122">**[フラグ付きのユーザー]**: 問題が発生しているユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="a0334-122">**Flagged users**: The number of users who are experiencing issues.</span></span> <span data-ttu-id="a0334-123">**[フラグ付きのユーザー]** では、現時点で脱獄されたデバイスを使用しているユーザーのみが報告されます。</span><span class="sxs-lookup"><span data-stu-id="a0334-123">Currently, only users with jailbroken devices are reported under **Flagged users**.</span></span>


## <a name="detailed-view"></a><span data-ttu-id="a0334-124">詳細ビュー</span><span class="sxs-lookup"><span data-stu-id="a0334-124">Detailed view</span></span>
<span data-ttu-id="a0334-125">**[ユーザーの状態]** タイル (デバイス OS プラットフォームに基づく) と **[フラグ付きのユーザー]** タイルを選択すると、概要の詳細ビューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a0334-125">You can get to the detailed view of the summary by choosing the **User status** tile (based on device OS platform), and the **Flagged users** tile.</span></span>

### <a name="user-status"></a><span data-ttu-id="a0334-126">ユーザーの状態</span><span class="sxs-lookup"><span data-stu-id="a0334-126">User status</span></span>
<span data-ttu-id="a0334-127">1 人のユーザーを検索し、そのユーザーのコンプライアンス状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a0334-127">You can search for a single user and check the compliance status for that user.</span></span> <span data-ttu-id="a0334-128">**[アプリ レポート]** ブレードには、選択したユーザーの次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0334-128">The **App reporting** blade shows the following information for a selected user:</span></span>
- <span data-ttu-id="a0334-129">ユーザー アカウントに関連付けられているデバイス</span><span class="sxs-lookup"><span data-stu-id="a0334-129">Devices that are associated with the user account</span></span>

- <span data-ttu-id="a0334-130">デバイスのアプリと MAM ポリシー</span><span class="sxs-lookup"><span data-stu-id="a0334-130">Apps with a MAM policy on the device</span></span>

- <span data-ttu-id="a0334-131">状態:</span><span class="sxs-lookup"><span data-stu-id="a0334-131">Status:</span></span>

  - <span data-ttu-id="a0334-132">**[チェックイン済み]**: ポリシーはユーザーに展開され、アプリが 1 回以上作業コンテキストで使用されました。</span><span class="sxs-lookup"><span data-stu-id="a0334-132">**Checked in**: The policy was deployed to the user, and the app was used in the work context at least once.</span></span>

  - <span data-ttu-id="a0334-133">**[チェックインされていません]**: ポリシーはユーザーに展開されましたが、それ以降にアプリが作業コンテキストで使用されていません。</span><span class="sxs-lookup"><span data-stu-id="a0334-133">**Not checked in**: The policy was deployed to the user, but the app has not been used in the work context since then.</span></span>

>[!NOTE]
> <span data-ttu-id="a0334-134">検索したユーザーに MAM ポリシーが展開されていない場合は、そのユーザーがいずれの MAM ポリシーの対象でもないことを知らせるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0334-134">If the users you searched for does not have the MAM policy deployed to them, you'll see a message informing you that the user is not targeted by any MAM policies.</span></span>

<span data-ttu-id="a0334-135">ユーザーのレポートを表示するには次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a0334-135">To see the reporting for a user, follow these steps:</span></span>

1.  <span data-ttu-id="a0334-136">ユーザーを選択するには、**[概要]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0334-136">To select a user, choose the **Summary** tile.</span></span>

    ![スクリーンショット 3](./media/MAM-reporting-6.png)

2. <span data-ttu-id="a0334-138">表示される **[アプリ レポート]** ブレードで、**[ユーザーの選択]** を選択して Azure Active Directory ユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="a0334-138">On the **App reporting** blade that opens, choose **Select user** to search for an Azure Active Directory user.</span></span>

    ![[アプリ レポート] ブレードのユーザー選択オプション](./media/MAM-reporting-2.png)

3. <span data-ttu-id="a0334-140">リストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0334-140">Select the user from the list.</span></span> <span data-ttu-id="a0334-141">そのユーザーのコンプライアンス状態の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0334-141">You will see the details of the compliance status for that user.</span></span>

### <a name="flagged-users"></a><span data-ttu-id="a0334-142">フラグ付きのユーザー</span><span class="sxs-lookup"><span data-stu-id="a0334-142">Flagged users</span></span>
<span data-ttu-id="a0334-143">詳細ビューには、エラー メッセージ、エラー発生時にアクセスされていたアプリ、影響を受けたデバイス OS プラットフォーム、タイムスタンプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0334-143">The detailed view shows the error message, the app that was accessed when the error happened, the device OS platform affected, and a time stamp.</span></span>

## <a name="reporting-view"></a><span data-ttu-id="a0334-144">レポート ビュー</span><span class="sxs-lookup"><span data-stu-id="a0334-144">Reporting view</span></span>

<span data-ttu-id="a0334-145">詳細ビューと同じレポートと追加のレポートがあります。MAM ポリシーのコンプライアンス状態の確認に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a0334-145">You can find the same reports from the Detailed view, and additional reports to help you with the MAM policy compliance status:</span></span>

![スクリーンショット 4](./media/MAM-reporting-7.png)

-   <span data-ttu-id="a0334-147">**アプリ保護ユーザー レポート:** 上の「詳細ビュー」セクションの**ユーザーの状態**レポートと同じ情報がまとめられています。</span><span class="sxs-lookup"><span data-stu-id="a0334-147">**App protection user report:** It outlines the same information you can find at the **User status** report under the Detailed view section above.</span></span>

-   <span data-ttu-id="a0334-148">**アプリ保護アプリ レポート:** 2 つの異なるアプリ保護状態があります。管理者はいずれかを選択し、レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="a0334-148">**App protection app report:** It provides two different app protection statuses that admins can select before generating the report.</span></span> <span data-ttu-id="a0334-149">状態には、保護と非保護があります。</span><span class="sxs-lookup"><span data-stu-id="a0334-149">The statuses can be protected or unprotected.</span></span>

    -   <span data-ttu-id="a0334-150">管理対象 MAM アクティビティ (保護) のユーザーの状態: このレポートには、管理対象 MAM アプリ別のアクティビティがユーザー別にまとめられています。</span><span class="sxs-lookup"><span data-stu-id="a0334-150">User status for managed MAM activity (Protected): This report outlines the activity of each managed MAM app, on a per user basis.</span></span>

        -   <span data-ttu-id="a0334-151">MAM ポリシーの対象になっているすべてのアプリがユーザーごとに表示されます。MAM ポリシーでチェックインしたときの各アプリの状態が分析されます。あるいは、MAM ポリシーの対象ではあるが、アプリがチェックインしていないことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0334-151">It shows all apps targeted by MAM policies for each user, and break down the status of each app as checked in with MAM policies, or that was targeted with a MAM policy but the app was never checked in.</span></span>
<br></br>
    -   <span data-ttu-id="a0334-152">非管理対象 MAM アクティビティ (非保護) のユーザーの状態: このレポートには、現在管理対象ではない MAM 対応アプリのアクティビティがユーザーごとにまとめられています。</span><span class="sxs-lookup"><span data-stu-id="a0334-152">User status for unmanaged MAM activity (Unprotected): This report outlines the activity of MAM-enabled apps that are currently unmanaged, on a per user basis.</span></span> <span data-ttu-id="a0334-153">次の理由で発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a0334-153">This might happen according to the following reasons:</span></span>

        -   <span data-ttu-id="a0334-154">これらのアプリは、現在のところ、MAM ポリシーの対象になっていないユーザーまたはアプリにより使用されています。</span><span class="sxs-lookup"><span data-stu-id="a0334-154">These apps are either being used by a user or an app that is not currently targeted by a MAM policy.</span></span>

        -   <span data-ttu-id="a0334-155">すべてのアプリがチェックインされているが、MAM ポリシーが与えられていません。</span><span class="sxs-lookup"><span data-stu-id="a0334-155">All apps are checked in, but aren't getting any MAM policies.</span></span>

![スクリーンショット 2](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a><span data-ttu-id="a0334-157">テーブルのグループ化</span><span class="sxs-lookup"><span data-stu-id="a0334-157">Table grouping</span></span>

<span data-ttu-id="a0334-158">**アプリ保護のユーザー レポート**のデータが表示されたら、次でデータを集計できます。</span><span class="sxs-lookup"><span data-stu-id="a0334-158">Once the **App protection user report** data shows up, you can aggregate data by the following:</span></span>

- <span data-ttu-id="a0334-159">**[検証結果]**: アプリ保護の状態 (エラー、警告、または成功) 別にグループ化されてデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0334-159">**Validation result:** The data shows up grouped by app protection status, which can be failure, warning or success.</span></span>
- <span data-ttu-id="a0334-160">**[アプリ名]**: アプリ (実際のアプリ名) とエラー、警告、または成功別にグループ化されてデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0334-160">**App name:** The data shows up grouped by apps (the actual app name) with failure, warning or success.</span></span>

## <a name="export-app-protection-activities-to-csv"></a><span data-ttu-id="a0334-161">CSV へのアプリ保護アクティビティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="a0334-161">Export app protection activities to CSV</span></span>

<span data-ttu-id="a0334-162">アプリ保護ポリシーのすべてのアクティビティを 1 つの .csv ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="a0334-162">You can export all your app protection policy activities to a single .csv file.</span></span> <span data-ttu-id="a0334-163">これは、ユーザーから報告されたアプリ保護のすべての状態を分析するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a0334-163">This can be helpful to analyze all the app protection statuses reported from the users.</span></span>

<span data-ttu-id="a0334-164">アプリ保護レポートを生成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a0334-164">Follow these steps to generate the App protection report:</span></span>

1. <span data-ttu-id="a0334-165">[Intune モバイル アプリケーション管理] ブレードで [App protection report (アプリ保護レポート)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0334-165">On the Intune mobile application management blade, choose App protection report.</span></span>

    ![スクリーンショット 6](./media/app-protection-report-csv-2.png)

2. <span data-ttu-id="a0334-167">[はい] を選択して、レポートを保存します。次に、[名前を付けて保存] を選択し、レポートを保存するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0334-167">Choose Yes to save your report, then choose Save As and select the folder you want to save the report in.</span></span>

    ![スクリーンショット 7](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a><span data-ttu-id="a0334-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0334-169">See also</span></span>
[<span data-ttu-id="a0334-170">iOS アプリ間のデータ転送を管理する</span><span class="sxs-lookup"><span data-stu-id="a0334-170">Manage data transfer between iOS apps</span></span>](data-transfer-between-apps-manage-ios.md)

* [<span data-ttu-id="a0334-171">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="a0334-171">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
* [<span data-ttu-id="a0334-172">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="a0334-172">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)
