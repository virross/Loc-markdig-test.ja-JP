---
title: "Azure Portal の概要"
titlesuffix: Azure portal
description: "Azure Portal の Intune でダッシュボードを作成し、共有する方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 917c0eed-96d0-49d8-8db8-a6ba13ad0e1f
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cce99fb69abd5f99a4a1eae0c6fbe0e5178af450
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="getting-started-with-intune-in-the-azure-portal"></a><span data-ttu-id="0ceb3-103">Azure Portal で Intune を始める</span><span class="sxs-lookup"><span data-stu-id="0ceb3-103">Getting started with Intune in the Azure portal</span></span>

<span data-ttu-id="0ceb3-104">Azure Portal は、Intune サービスのある場所です。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-104">The Azure portal is where you can find the Intune service.</span></span> <span data-ttu-id="0ceb3-105">Azure にはたくさんのサービスがありますが、その多くはおそらく、日常的に使用されることがありません。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-105">There are a lot of services in Azure, many of which you may not use on a regular basis.</span></span> <span data-ttu-id="0ceb3-106">ダッシュボードとサイドバーをカスタマイズすれば、いつログインしても必要な情報がすぐに見つかり、Intune でデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-106">Customizing your dashboard and sidebar can help you find the right information quickly every time you log in to manage devices with Intune.</span></span>

## <a name="changing-the-sidebar"></a><span data-ttu-id="0ceb3-107">サイドバーを変更する</span><span class="sxs-lookup"><span data-stu-id="0ceb3-107">Changing the sidebar</span></span>

<span data-ttu-id="0ceb3-108">Azure Portal の左側にある__サイドバー__には、利用できるすべての Azure サービスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-108">The __sidebar__ on the left side of the Azure portal shows you a list of all available Azure services.</span></span> <span data-ttu-id="0ceb3-109">この包括的な一覧は既定以外の表示に変更できます。自分にとって最も重要なサービスを常に表示しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-109">This comprehensive list can be changed from the default view so that you can keep a persistent view of the services that matter most to you.</span></span> <span data-ttu-id="0ceb3-110">サービスの例として Intune を利用し、一覧の一番上に追加します。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-110">We'll use Intune as the example of a service to add to the top of the list.</span></span>

![あるユーザーが "その他のサービス" 一覧で Intune を探しています。](./media/azure-add-intune1.png)

1. <span data-ttu-id="0ceb3-112">ページの左側にあるサイドバーの一番下から **[その他のサービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-112">Select **More services** from the bottom of the sidebar on the left side of the page.</span></span>
2. <span data-ttu-id="0ceb3-113">フィルター ボックスで **Intune** を検索します。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-113">Search for **Intune** in the filter box.</span></span>
3. <span data-ttu-id="0ceb3-114">**星**マークを選択し、お気に入りサービス一覧の一番下に Intune を追加します。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-114">Select the **star** to add Intune to the bottom of the list of your favorite services.</span></span>
4. <span data-ttu-id="0ceb3-115">Intune サービスの上にカーソルを合わせます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-115">Hover over the Intune service.</span></span> <span data-ttu-id="0ceb3-116">Intune を選択してドラッグします。サービス名の右側にある **3 つの垂直ドット**を利用します。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-116">Select and drag Intune using the **three vertical dots** on the right side of the service name.</span></span>

## <a name="changing-the-dashboard"></a><span data-ttu-id="0ceb3-117">ダッシュボードの変更</span><span class="sxs-lookup"><span data-stu-id="0ceb3-117">Changing the dashboard</span></span>

<span data-ttu-id="0ceb3-118">既定のランディング ページは**ダッシュボード**です。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-118">Your default landing page is the **dashboard**.</span></span> <span data-ttu-id="0ceb3-119">このダッシュボードでタイルをカスタマイズし、自分にとって最も重要な情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-119">This is where you'll customize your tiles to show information that is most relevant to you.</span></span>

![一般的な新しいダッシュボードのイメージ。](./media/azure-default-dashboard.png)

<span data-ttu-id="0ceb3-123">現在のダッシュボードを変更するには、**[ダッシュボードの編集]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-123">To modify your current dashboard, select the **Edit dashboard** button.</span></span> <span data-ttu-id="0ceb3-124">既定のダッシュボードを変更しなくても、**新しいダッシュボード**を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-124">If you don't want to change your default dashboard, you can also create a **New dashboard**.</span></span> <span data-ttu-id="0ceb3-125">新しいダッシュボードを作成すると、**タイル ギャラリー**の付いた空のプライベート ダッシュボードが与えられます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-125">Creating a new dashboard gives you an empty, private dashboard with the **Tile Gallery**.</span></span> <span data-ttu-id="0ceb3-126">タイルを追加したり、並べ換えたりできます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-126">This lets you add or rearrange tiles.</span></span> <span data-ttu-id="0ceb3-127">**全般**カテゴリや**種類**に基づいて、あるいは**検索**、**リソース グループ**、**タグ**を利用してタイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-127">You can find tiles by their **General** category, **Type**, through **Search**, and through a **Resource group** or **Tag**.</span></span>

<span data-ttu-id="0ceb3-128">また、**省略記号**ボタンからダッシュボードに直接、タイルを追加できます。**[ダッシュボードにピン留めする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-128">You can also add tiles directly to your dashboard from any **ellipsis** button and selecting **Pin to dashboard**.</span></span>

![Intune の [ユーザーとグループ - すべてのグループ] の拡大画面。グループの右端で "ダッシュボードにピン留めする" オプションを確認できます。](./media/azure-pin-to-dashboard.png)

<span data-ttu-id="0ceb3-130">ここは、グループやユーザーなど、Intune にコンテンツを追加した後に重要になります。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-130">This will be more relevant after you've added more content, like groups and users, to Intune.</span></span>

## <a name="using-services"></a><span data-ttu-id="0ceb3-131">サービスの使用</span><span class="sxs-lookup"><span data-stu-id="0ceb3-131">Using services</span></span>

<span data-ttu-id="0ceb3-132">Intune やその他のサービスを Azure で開くたびに、サービスは**ブレード**に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-132">Whenever you open Intune or any other service in Azure, the service is displayed in a **blade**.</span></span> <span data-ttu-id="0ceb3-133">**ユーザー**、**グループ**、**モバイル アプリ**など、Intune で最初に使用するワークロードはすべて、全画面ブレードで表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-133">Some of the first workloads you use in Intune, like **Users**, **Groups**, and **Mobile apps**, all appear in a full screen blade.</span></span> <span data-ttu-id="0ceb3-134">ワークロードを選択すると、そのブレードが全画面で開きます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-134">When you select the workload, it opens that blade in the full page.</span></span> <span data-ttu-id="0ceb3-135">他のブレードは開くときにブレードの右側から引き出され、メイン ブレードの下で折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-135">Other blades slide out from the right side of the blade when they open, and collapse underneath the main blade that they came from.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0ceb3-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0ceb3-136">Next steps</span></span>

* <span data-ttu-id="0ceb3-137">[ユーザー管理の概要](get-started-users.md) - Intune にユーザーを追加し、モバイル デバイスで会社のリソースにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="0ceb3-137">[Get started with managing users](get-started-users.md) - Add a user to Intune to allow them to access company resources on mobile devices.</span></span>
