---
title: "アプリの展開を監視する"
description: "Intune を使用して展開したアプリを監視する方法について説明します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5daad56d-71c8-455b-8a55-f8b33e279a8a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2ffb84e4956885cbc892dec92c4687a2f8691082
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="monitor-app-deployments-in-microsoft-intune"></a><span data-ttu-id="0d8ee-103">Microsoft Intune でアプリの展開を監視する</span><span class="sxs-lookup"><span data-stu-id="0d8ee-103">Monitor app deployments in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="monitor-an-app-deployment"></a><span data-ttu-id="0d8ee-104">アプリの展開を監視する</span><span class="sxs-lookup"><span data-stu-id="0d8ee-104">Monitor an app deployment</span></span>
<span data-ttu-id="0d8ee-105">Intune 管理コンソールで管理対象アプリの展開の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-105">You can see the apps that you manage and the status of any deployments in the Intune administration console.</span></span> <!---App status is displayed in real-time. You don't have to wait for the device to check-in before you can see this.--->

### <a name="to-view-apps-that-you-manage-and-their-status"></a><span data-ttu-id="0d8ee-106">管理するアプリとその状態を確認するには</span><span class="sxs-lookup"><span data-stu-id="0d8ee-106">To view apps that you manage and their status</span></span>
<span data-ttu-id="0d8ee-107">**[アプリ]** ワークスペースで、**[アプリ]** ノードを選択し、**[アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-107">In the **Apps** workspace, choose the **Apps** node, and then choose **Apps**.</span></span>

<span data-ttu-id="0d8ee-108">管理しているアプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-108">The list of apps that you manage appears.</span></span> <span data-ttu-id="0d8ee-109">コンソール ウィンドウの下のウィンドウでアプリを選択すると、インストール状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-109">You can choose any app to see an installation status in the lower pane of the console windows.</span></span> <span data-ttu-id="0d8ee-110">さらに詳細を表示するには、この状態を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-110">Choose this status to see further details.</span></span> <span data-ttu-id="0d8ee-111">たとえば、状態に **[1 人のユーザーがこのソフトウェアを利用しています]** と表示されている場合、そのメッセージを選択すると、ユーザーの名前を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-111">For example, if the status shows **1 user has this software available**, you can choose the message to see the name of the user.</span></span>

> [!TIP]
> <span data-ttu-id="0d8ee-112">**[フィルター]** ドロップダウン リストを利用すると、インストールできなかったアプリや正常に展開されたアプリなど、指定した基準に一致するアプリのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-112">You can use the **Filters** drop-down list to show only apps that meet the criteria that you specify, like apps that failed to install or apps that were successfully deployed.</span></span>
>
> ![アプリ フィルターの例](./media/app-filters.png)

<span data-ttu-id="0d8ee-114">また、**[ダッシュボード]** ワークスペースには、アプリの状態の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-114">Additionally, the **Dashboard** workspace shows an overview of the status of your apps.</span></span> <span data-ttu-id="0d8ee-115">概要内のどこでもよいのでクリックすると、アプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-115">If you click anywhere in the overview, you'll be taken to the list of apps.</span></span>

## <a name="to-view-more-detailed-information-about-an-app"></a><span data-ttu-id="0d8ee-116">アプリに関する詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="0d8ee-116">To view more detailed information about an app</span></span>
<span data-ttu-id="0d8ee-117">アプリの一覧で、アプリを選択し、**[プロパティの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-117">In the list of apps, select any app, and then choose **View Properties**.</span></span>

<span data-ttu-id="0d8ee-118">アプリの **[ソフトウェア プロパティ]** ページで、次のいずれかのタブを選択します。**[全般]** - アプリとそのインストール状態に関する一般的な情報が表示されます。**[デバイス]** - アプリの対象となる展開が正常にインストールされているデバイスが表示されます。**[ユーザー]** - アプリの対象となる展開が正常にインストールされているデバイスのユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-118">On the **Software Properties** page for the app, choose one of these tabs: **General** - Shows general information about the app and its installation status, **Devices** - Shows the devices that successfully installed a targeted deployment of the app, and **Users** - Shows the users whose devices successfully installed a targeted deployment of the app.</span></span>

<span data-ttu-id="0d8ee-119">前述のように、**[フィルター]** ドロップダウン リストを利用し、各タブに表示される値を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0d8ee-119">As before, you can use the **Filters** drop-down list to configure the values shown on each of the tabs.</span></span>
