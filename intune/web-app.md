---
title: "Web アプリを Intune に追加する方法"
titleSuffix: Azure portal
description: "Web アプリを Intune に追加する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ebe4b31c85e0c0bc88f49d28e28ea7eac191951f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a><span data-ttu-id="b582f-103">Web アプリを Microsoft Intune に追加する方法</span><span class="sxs-lookup"><span data-stu-id="b582f-103">How to add web apps to Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b582f-104">管理し、ユーザーのアプリを割り当てることができます、前に、アプリを Intune に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b582f-104">Before you can manage and assign an app for your users, you must add the app to Intune.</span></span> <span data-ttu-id="b582f-105">Intune では、Web アプリなど、さまざまなアプリの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b582f-105">Intune supports a variety of app types including web apps.</span></span>

> [!Note]
> <span data-ttu-id="b582f-106">Web アプリは、Android for Work デバイスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b582f-106">Web apps are not supported on Android for Work devices.</span></span>

<span data-ttu-id="b582f-107">次の手順では web 上のアプリへのショートカットとしてアプリを Intune に追加することを許可します。</span><span class="sxs-lookup"><span data-stu-id="b582f-107">The following procedure will allow you to add an app to Intune as a shortcut to an app on the web:</span></span>

1. <span data-ttu-id="b582f-108">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b582f-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b582f-109">**[More resources]\(その他のリソース\)** で、**[Intune]** を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="b582f-109">Using **More resources**, search for and select **Intune**.</span></span>
3. <span data-ttu-id="b582f-110">**[Microsoft Intune]** ブレードで、**[モバイル アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b582f-110">On the **Microsoft Intune** blade, select **Mobile apps**.</span></span>
4. <span data-ttu-id="b582f-111">**[モバイル アプリ]** ブレードで、**[アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b582f-111">On the **Mobile apps** blade, select **Apps**.</span></span>
5. <span data-ttu-id="b582f-112">アプリの一覧の上にある **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b582f-112">Above the list of apps, select **Add**.</span></span> <span data-ttu-id="b582f-113">**追加アプリ**ブレードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b582f-113">The **Add app** blade will be displayed.</span></span>
6. <span data-ttu-id="b582f-114">**[アプリの追加]** ブレードで、**[アプリの種類]** ドロップダウン リストから **[Web アプリ]** という種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="b582f-114">In the **Add app** blade, select the **Web app** type from the **App type** drop-down list.</span></span>
7. <span data-ttu-id="b582f-115">**[構成]** オプションを選択して **[アプリ情報]** ブレードを表示します。</span><span class="sxs-lookup"><span data-stu-id="b582f-115">Select the **Configure** option to display the **App information** blade.</span></span>
8. <span data-ttu-id="b582f-116">**[アプリ情報]** ブレードで、以下の情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="b582f-116">In the **App information** blade, add the following information:</span></span>
    - <span data-ttu-id="b582f-117">**名前** - アプリの名前を入力します。この名前は会社のポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b582f-117">**Name** - Enter the name of the app as it will be displayed in the company portal.</span></span>
    - <span data-ttu-id="b582f-118">**説明** - アプリの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="b582f-118">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="b582f-119">これは会社のポータルでエンド ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b582f-119">This will be displayed to end users in the company portal.</span></span>
    - <span data-ttu-id="b582f-120">**[発行元]** - このアプリの発行元の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b582f-120">**Publisher** - Enter the name of the publisher of this app.</span></span>
    - <span data-ttu-id="b582f-121">**[アプリ URL]** - 割り当てるアプリをホストする Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="b582f-121">**App URL** - Enter the URL of the web site that hosts the app you want to assign.</span></span>
    - <span data-ttu-id="b582f-122">**[カテゴリ]** (省略可能) - 1 つ以上の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="b582f-122">**Category (optional)** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="b582f-123">会社のポータルを閲覧するとき、ユーザーにとってアプリを探すのが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="b582f-123">This will make it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="b582f-124">**[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。</span><span class="sxs-lookup"><span data-stu-id="b582f-124">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="b582f-125">**[このリンクを開くには Managed Browser が必要です]** - Web サイトまたは Web アプリへのリンクをユーザーに割り当てると、ユーザーは Intune Managed Browser でのみリンクを開くことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="b582f-125">**Require a managed browser to open this link** - When you assign a link to a website or web app to users, they will be able to open it only in the Intune managed browser.</span></span> <span data-ttu-id="b582f-126">このブラウザーをデバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b582f-126">This browser must be installed on their device.</span></span>
    - <span data-ttu-id="b582f-127">**ロゴ**-は、アプリに関連付けられるロゴをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="b582f-127">**Logo** - Upload an logo that will be associated with the app.</span></span> <span data-ttu-id="b582f-128">これは、ユーザーがポータル サイトを参照すると、アプリに表示されるロゴです。</span><span class="sxs-lookup"><span data-stu-id="b582f-128">This is the logo that will be displayed with the app when users browse the company portal.</span></span>
9. <span data-ttu-id="b582f-129">完了したら、**[情報の追加]** ブレードで、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b582f-129">When you are done, on the **Add information** blade, select **Ok**.</span></span>
10. <span data-ttu-id="b582f-130">次に、**[アプリの追加]** ブレードで **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b582f-130">Then, from the **Add app** blade, select **Add**.</span></span>

<span data-ttu-id="b582f-131">作成したアプリはアプリの一覧に表示され、選択したグループに割り当てることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="b582f-131">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="b582f-132">詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b582f-132">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>