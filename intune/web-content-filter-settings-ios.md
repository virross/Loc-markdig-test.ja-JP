---
title: "iOS デバイス用の Intune Web コンテンツ フィルター設定"
titlesuffix: Azure portal
description: "iOS デバイスからの Web サイトへのアクセスの許可とブロックに使用できる設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 7/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89641cee439d7da9f73d56c2ab3d6d8299164700
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="web-content-filter-settings-for-ios-devices"></a><span data-ttu-id="b86b4-103">iOS デバイス用の Web コンテンツ フィルター設定</span><span class="sxs-lookup"><span data-stu-id="b86b4-103">Web content filter settings for iOS devices</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b86b4-104">これらの設定を使用して、Web ブラウザーのエンド ユーザーが iOS デバイス上でアクセスできる、またはできない URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="b86b4-104">Use these settings to configure URLs that end users of web browsers, on iOS devices, can, or cannot visit.</span></span> <span data-ttu-id="b86b4-105">URL を構成する方法には 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="b86b4-105">There are two methods you can use to do configure URLs:</span></span>

- <span data-ttu-id="b86b4-106">**URL の構成** - Apple の組み込み Web フィルターを使用します。不適切または性的に露骨な言語といった成人向け用語を探すものです。</span><span class="sxs-lookup"><span data-stu-id="b86b4-106">**Configure URLs** - Use Apple’s built-in web filter that looks for adult terms like profanity or sexually explicit language.</span></span> <span data-ttu-id="b86b4-107">この関数は、各 Web ページを読み込みながら評価し、不適切なコンテンツの識別とブロックを試みます。</span><span class="sxs-lookup"><span data-stu-id="b86b4-107">This function evaluates each web page as it is loaded and attempts to identify and block unsuitable content.</span></span> <span data-ttu-id="b86b4-108">フィルターでチェックされない URL、またはフィルター設定に関係なくブロックされる URL を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b86b4-108">You can also configure URLs that are not checked by the filter, or URLs that are blocked, regardless of the filter settings.</span></span>

- <span data-ttu-id="b86b4-109">**特定の Web サイトのみ** (Safari Web ブラウザーのみ) - これらの URL は Safari ブラウザーのブックマークに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b86b4-109">**Specific websites only** (for the Safari web browser only) - These URLs are added to the Safari browser’s bookmarks.</span></span> <span data-ttu-id="b86b4-110">ユーザーはこれらのサイトに**のみ**アクセスが許可され、他のサイトにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b86b4-110">The user is **only** allowed to visit these sites; no other sites can be accessed.</span></span> <span data-ttu-id="b86b4-111">このオプションは、ユーザーがアクセスできる URL の正確な一覧がわかっている場合にのみ使います。</span><span class="sxs-lookup"><span data-stu-id="b86b4-111">Use this option only if you know the exact list of URLs that users can access.</span></span>
<span data-ttu-id="b86b4-112">URL を指定しない場合、エンド ユーザーは、microsoft.com、microsoft.net、apple.com 以外の Web サイトにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b86b4-112">If you do not specify any URLs, then end users cannot access any websites except for microsoft.com, microsoft.net, and apple.com.</span></span>



## <a name="get-started"></a><span data-ttu-id="b86b4-113">作業開始</span><span class="sxs-lookup"><span data-stu-id="b86b4-113">Get started</span></span>

1. <span data-ttu-id="b86b4-114">[デバイス機能] ブレードで、**[Web コンテンツ フィルター (監視モードのみ)]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="b86b4-114">On the Device features blade, choose **Web Content Filter (supervised only)**.</span></span>
2. <span data-ttu-id="b86b4-115">**[Web コンテンツ フィルター]** ブレードで、構成する **[フィルターの種類]** を以下から選択します。</span><span class="sxs-lookup"><span data-stu-id="b86b4-115">On the **Web Content Filter** blade, choose the **Filter type** you want to configure from:</span></span>
    - <span data-ttu-id="b86b4-116">**[未構成]** - フィルター処理は行われていません。</span><span class="sxs-lookup"><span data-stu-id="b86b4-116">**Not Configured** - No filtering is performed.</span></span>
    - <span data-ttu-id="b86b4-117">**[Configure URLs]**(URL の構成)</span><span class="sxs-lookup"><span data-stu-id="b86b4-117">**Configure URLs**</span></span>
    - <span data-ttu-id="b86b4-118">**[Specific websites only]**(特定の Web サイトのみ)</span><span class="sxs-lookup"><span data-stu-id="b86b4-118">**Specific websites only**</span></span>
3. <span data-ttu-id="b86b4-119">次に、使っているフィルターの種類に応じて、次のいずれかの手順を使います。</span><span class="sxs-lookup"><span data-stu-id="b86b4-119">Next, depending on the filter type you are using, use one of the following procedures:</span></span>


## <a name="configure-urls"></a><span data-ttu-id="b86b4-120">URL の構成</span><span class="sxs-lookup"><span data-stu-id="b86b4-120">Configure URLs</span></span>

1. <span data-ttu-id="b86b4-121">**[Web コンテンツ フィルター]** ブレードで、必要に応じて次のいずれかの設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="b86b4-121">On the **Web Content Filter** blade, choose one of the following settings as required:</span></span>
    - <span data-ttu-id="b86b4-122">**許可された URL** - **[Permitted URLs]**(許可された URL) ブレードで、許可する URL (Apple Web フィルターをバイパスする) を入力し、それぞれの後に Enter を押します。</span><span class="sxs-lookup"><span data-stu-id="b86b4-122">**Permitted URLs** - On the **Permitted URLs** blade, enter the URLs you want to allow (bypassing the Apple web filter), and choose enter after each.</span></span>
    - <span data-ttu-id="b86b4-123">**ブロックされた URL** - **[Blocked URLs]**(ブロックされた URL) ブレードで、ブロックする URL を (Apple Web フィルター設定にかかわらず) 入力し、それぞれの後に Enter を押します。</span><span class="sxs-lookup"><span data-stu-id="b86b4-123">**Blocked URLs** - On the **Blocked URLs** blade, enter the URLs you want to block (regardless of the Apple web filter settings), and choose enter after each.</span></span>
2. <span data-ttu-id="b86b4-124">操作が完了したら、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b86b4-124">When you are finished, click **OK**.</span></span>


## <a name="specific-websites-only"></a><span data-ttu-id="b86b4-125">特定の Web サイトのみ</span><span class="sxs-lookup"><span data-stu-id="b86b4-125">Specific websites only</span></span>

1. <span data-ttu-id="b86b4-126">**[Web コンテンツ フィルター]** ブレードで、許可する Web サイトごとに、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b86b4-126">On the **Web Content Filter** blade, for each web site you want to permit, configure the following settings:</span></span>
    - <span data-ttu-id="b86b4-127">**[URL]** - 許可する Web サイトの URL (たとえば **http://www.contoso.com**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b86b4-127">**URL** - Enter the URL of the website you want to permit, for example, **http://www.contoso.com**.</span></span>
    - <span data-ttu-id="b86b4-128">**[Bookmark Path]**(ブックマークのパス) - ブックマークを保存するパス (たとえば **/Contoso/Business Apps**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b86b4-128">**Bookmark Path** - Enter the path to where you want to store the bookmark, for example **/Contoso/Business Apps**.</span></span> <span data-ttu-id="b86b4-129">パスを追加しないと、デバイス上の既定のブックマーク フォルダーにブックマークが追加されます。</span><span class="sxs-lookup"><span data-stu-id="b86b4-129">If you don't add a path, the bookmark is added to the default bookmark folder on the device.</span></span>
    - <span data-ttu-id="b86b4-130">**[タイトル]** - ブックマークのわかりやすいタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="b86b4-130">**Title** - Enter a descriptive title for the bookmark.</span></span>
2. <span data-ttu-id="b86b4-131">各 Web サイトの情報を入力したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b86b4-131">Click **Add** after you enter the information for each website.</span></span>
3. <span data-ttu-id="b86b4-132">操作が完了したら、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b86b4-132">When you are finished, click **OK**.</span></span>

>[!IMPORTANT] 
> <span data-ttu-id="b86b4-133">次の URL は、Intune によって自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="b86b4-133">The following URLs are permitted automatically by Intune.</span></span>
> - <span data-ttu-id="b86b4-134">www.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b86b4-134">www.microsoft.com</span></span>
> - <span data-ttu-id="b86b4-135">www.microsoft.net</span><span class="sxs-lookup"><span data-stu-id="b86b4-135">www.microsoft.net</span></span>
> - <span data-ttu-id="b86b4-136">www.apple.com</span><span class="sxs-lookup"><span data-stu-id="b86b4-136">www.apple.com</span></span>

## <a name="finish-up"></a><span data-ttu-id="b86b4-137">完了</span><span class="sxs-lookup"><span data-stu-id="b86b4-137">Finish up</span></span>

<span data-ttu-id="b86b4-138">**[OK]** を選択して **[プロファイルの作成]** ブレードに戻り、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b86b4-138">Choose **OK** to return to the **Create Profile** blade, and then choose **Create**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b86b4-139">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b86b4-139">Next steps</span></span>

<span data-ttu-id="b86b4-140">選択したグループにデバイス プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b86b4-140">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="b86b4-141">詳しくは、「[デバイス プロファイルを割り当てる方法](device-profile-assign.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b86b4-141">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
