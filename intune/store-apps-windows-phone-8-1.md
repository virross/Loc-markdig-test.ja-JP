---
title: "Windows Phone 8.1 ストア アプリを Intune に追加する方法"
titleSuffix: Azure portal
description: "Windows Phone 8.1 ストア アプリを Intune に追加する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 23ecc73f62ac0558abb83ff6bb93055f07e69b37
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-add-windows-phone-81-store-apps-to-microsoft-intune"></a><span data-ttu-id="60c59-103">Windows Phone 8.1 ストア アプリを Microsoft Intune に追加する方法</span><span class="sxs-lookup"><span data-stu-id="60c59-103">How to add Windows Phone 8.1 store apps to Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

1. <span data-ttu-id="60c59-104">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="60c59-104">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="60c59-105">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="60c59-105">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="60c59-106">**[Intune]** ブレードで、**[アプリの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="60c59-106">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="60c59-107">**[モバイル アプリ]** ワークロードで、**[管理]** > **[アプリ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="60c59-107">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="60c59-108">アプリの一覧の上にある **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="60c59-108">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="60c59-109">**[アプリの追加]** ブレードで、**[アプリ情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="60c59-109">In the **Add App** blade, choose **App Information**.</span></span>
7. <span data-ttu-id="60c59-110">**[アプリの編集]** ブレードで、以下の情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="60c59-110">In the **Edit App** blade, configure the following information.</span></span> <span data-ttu-id="60c59-111">構成が終わったら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c59-111">Once you are done, click **Add**.</span></span> <span data-ttu-id="60c59-112">選択したアプリによっては、このブレード内の一部の値が自動的に入力されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="60c59-112">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="60c59-113">**[アプリ名]** - アプリの名前を入力します。この名前は会社のポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="60c59-113">**App Name** - Enter the name of the app as it will be displayed in the company portal.</span></span> <span data-ttu-id="60c59-114">使用するアプリ名はすべて一意にします。</span><span class="sxs-lookup"><span data-stu-id="60c59-114">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="60c59-115">同じアプリ名が 2 つ存在する場合、会社のポータルではそのいずれかのみがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="60c59-115">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="60c59-116">**[アプリの説明]** - アプリの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="60c59-116">**App Description** - Enter a description for the app.</span></span> <span data-ttu-id="60c59-117">これは会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="60c59-117">This will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="60c59-118">**[発行元]** - アプリの発行元の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="60c59-118">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="60c59-119">**[アプリ ストア URL]** - 作成するアプリのアプリ ストア URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="60c59-119">**App store URL** - Enter the app store URL of the app you want to create.</span></span>
    - <span data-ttu-id="60c59-120">**[オペレーティング システムの最小要件]** - アプリをインストールできる最小限のオペレーティング システム バージョンを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="60c59-120">**Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed.</span></span> <span data-ttu-id="60c59-121">これよりも前のオペレーティング システムがアプリの割り当て先デバイスにインストールされている場合、そのアプリはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="60c59-121">If you assign the app to a device with an earlier operating system, it will not be installed.</span></span>
    - <span data-ttu-id="60c59-122">**[カテゴリ]** (省略可能) - 1 つ以上の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="60c59-122">**Category (optional)** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="60c59-123">会社のポータルを閲覧するとき、ユーザーにとってアプリを探すのが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="60c59-123">This will make it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="60c59-124">**[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。</span><span class="sxs-lookup"><span data-stu-id="60c59-124">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="60c59-125">**[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="60c59-125">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="60c59-126">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="60c59-126">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="60c59-127">**[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="60c59-127">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="60c59-128">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="60c59-128">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="60c59-129">**[開発者]** - 必要に応じて、アプリ開発者の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="60c59-129">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="60c59-130">**[所有者]** - 必要に応じて、このアプリの所有者の名前 ("**人事部**" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="60c59-130">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="60c59-131">**[メモ]** - このアプリに関連付けるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="60c59-131">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="60c59-132">**[アップロード アイコン]** - アプリに関連付けるアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="60c59-132">**Upload Icon** - Upload an icon that will be associated with the app.</span></span> <span data-ttu-id="60c59-133">ユーザーが会社のポータルを参照するとき、アプリにこのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60c59-133">This is the icon that will be displayed with the app when users browse the company portal.</span></span>
8. <span data-ttu-id="60c59-134">構成が終了したら、**[アプリの追加]** ブレードで、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="60c59-134">When you are done, on the **Add App** blade, choose **Save**.</span></span>

<span data-ttu-id="60c59-135">作成したアプリはアプリの一覧に表示され、選択したグループに割り当てることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="60c59-135">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="60c59-136">詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c59-136">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>