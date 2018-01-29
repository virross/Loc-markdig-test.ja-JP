---
title: "Intune を使用して Office 365 を macOS デバイスにインストールする"
titlesuffix: Azure portal
description: "Intune を使用して、Office 365 アプリを macOS デバイスに簡単にインストールする方法について説明します。"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cd071927955f5047067ba1d982e7078d89675cd0
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a><span data-ttu-id="56b17-103">Microsoft Intune を使用して Office 365 を macOS デバイスに割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="56b17-103">How to assign Office 365 to macOS devices with Microsoft Intune</span></span>

<span data-ttu-id="56b17-104">このアプリの種類では、Office 365 アプリを macOS デバイスに簡単に割り当てることできます。</span><span class="sxs-lookup"><span data-stu-id="56b17-104">This app type makes it easy for you to assign Office 365 apps to macOS devices.</span></span> <span data-ttu-id="56b17-105">この新しいアプリの種類では、Word、Excel、PowerPoint、Outlook、OneNote をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="56b17-105">This new app type allows you to install Word, Excel, PowerPoint, Outlook, and OneNote.</span></span> <span data-ttu-id="56b17-106">これらのアプリには Microsoft AutoUpdate (MAU) も付属しており、アプリをより安全かつ最新に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="56b17-106">These apps also come with the Microsoft AutoUpdate (MAU), to help keep the apps more secure and up-to-date.</span></span> <span data-ttu-id="56b17-107">必要なアプリは、Intune コンソールのアプリ一覧に 1 つのアプリとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="56b17-107">The apps you want appear as one app in the list of apps in the Intune console.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="56b17-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="56b17-108">Before you start</span></span>

- <span data-ttu-id="56b17-109">これらのアプリを展開するデバイスでは、macOS 10.10 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="56b17-109">Devices to which you deploy these apps must be running macOS 10.10 or later.</span></span>
- <span data-ttu-id="56b17-110">Intune は、Office 2016 for Mac スイートに含まれる Office アプリの追加のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="56b17-110">Intune only supports adding Office apps included with Office 2016 for Mac suite.</span></span>
- <span data-ttu-id="56b17-111">Intune でアプリ スイートをインストール中に Office アプリを開くと、エンド ユーザーは保存されていないファイルのデータを失う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="56b17-111">If any Office apps are opened when Intune installs the app suite, end users might lose data from unsaved files.</span></span>


## <a name="get-started"></a><span data-ttu-id="56b17-112">作業開始</span><span class="sxs-lookup"><span data-stu-id="56b17-112">Get started</span></span>
<span data-ttu-id="56b17-113">**[アプリ]** ブレードを使用して Office 365 を追加します。</span><span class="sxs-lookup"><span data-stu-id="56b17-113">Add Office 365 using the **Apps** blade.</span></span>
1.  <span data-ttu-id="56b17-114">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="56b17-114">Sign into the Azure portal.</span></span>
2.  <span data-ttu-id="56b17-115">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3.  <span data-ttu-id="56b17-116">**[Intune]** ブレードで、**[モバイル アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="56b17-116">On the **Intune** blade, choose **Mobile apps**.</span></span>
4.  <span data-ttu-id="56b17-117">**[モバイル アプリ]** ワークロードで、**[管理]** グループの **[アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-117">In the **Mobile apps** workload, choose **Apps** in the **Manage** group.</span></span> <span data-ttu-id="56b17-118">**[追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="56b17-118">Choose **Add**.</span></span>
5.  <span data-ttu-id="56b17-119">**[アプリの追加]** ブレードで、**[Office 365]** > **[macOS]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-119">On the **Add App** blade, choose **Office 365** > **macOS**.</span></span>
6.  <span data-ttu-id="56b17-120">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-120">Select **Add**.</span></span>

## <a name="configure-the-app-suite"></a><span data-ttu-id="56b17-121">アプリ スイートの構成</span><span class="sxs-lookup"><span data-stu-id="56b17-121">Configure the app suite</span></span>

<span data-ttu-id="56b17-122">アプリ スイートに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="56b17-122">Provide information about the app suite.</span></span> <span data-ttu-id="56b17-123">この情報は、アプリ スイートを Intune で識別したり、ユーザーが会社のポータル サイト アプリで探したりする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="56b17-123">This information helps you to identify it in Intune, and also helps users to find it in the Company Portal app.</span></span>

1.  <span data-ttu-id="56b17-124">**[アプリの追加]** ブレードで、**[アプリ スイートの情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-124">On the **Add App** blade, choose **App Suite Information**.</span></span>
2.  <span data-ttu-id="56b17-125">次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="56b17-125">Specify the following information:</span></span>
    - <span data-ttu-id="56b17-126">**[スイート名]** - 会社のポータルに表示される、アプリ スイートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="56b17-126">**Suite Name** - Enter the name of the app suite as it is displayed in the company portal.</span></span> <span data-ttu-id="56b17-127">使用するスイート名はすべて一意にします。</span><span class="sxs-lookup"><span data-stu-id="56b17-127">Make sure all suite names that you use are unique.</span></span> <span data-ttu-id="56b17-128">同じアプリ スイート名が 2 つ存在する場合、会社のポータルではそのアプリのいずれかのみがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="56b17-128">If the same app suite name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="56b17-129">**[スイートの説明]** - アプリ スイートの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="56b17-129">**Suite Description** - Enter a description for the app suite.</span></span>
    - <span data-ttu-id="56b17-130">**[発行者]** - Microsoft が発行者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="56b17-130">**Publisher** - Microsoft appears as the publisher.</span></span>
    - <span data-ttu-id="56b17-131">**[カテゴリ]** - 必要に応じて、1 つ以上の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-131">**Category** - Optionally, select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="56b17-132">この操作を行うと、会社のポータルを閲覧するときに、ユーザーがアプリ スイートを探しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="56b17-132">This makes it easier for users to find the app suite when they browse the company portal.</span></span>
    - <span data-ttu-id="56b17-133">**[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探すときに、会社のポータルのメイン ページでアプリ スイートを目立つように表示します。</span><span class="sxs-lookup"><span data-stu-id="56b17-133">**Display this as a featured app in the Company Portal** - This will display the app suite prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="56b17-134">**[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="56b17-134">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="56b17-135">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="56b17-135">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="56b17-136">**[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="56b17-136">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="56b17-137">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="56b17-137">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="56b17-138">**[開発者]** - Microsoft が開発者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="56b17-138">**Developer** - Microsoft appears as the developer.</span></span>
    - <span data-ttu-id="56b17-139">**[所有者]** - Microsoft が所有者として表示されます。</span><span class="sxs-lookup"><span data-stu-id="56b17-139">**Owner** - Microsoft appears as the owner.</span></span>
    - <span data-ttu-id="56b17-140">**[メモ]** - このアプリに関連付けるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="56b17-140">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="56b17-141">**[アイコンのアップロード]** - ユーザーが会社のポータルを参照するときに、アプリに表示されるアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="56b17-141">**Upload Icon** - Upload an icon that is displayed with the app when users browse the company portal.</span></span>
3.  <span data-ttu-id="56b17-142">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-142">Select **OK**.</span></span> <span data-ttu-id="56b17-143">アプリの一覧に、このスイートが 1 つのエントリとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="56b17-143">The suite appears in the list of apps as a single entry.</span></span>

## <a name="configure-app-assignments"></a><span data-ttu-id="56b17-144">アプリの割り当てを構成する</span><span class="sxs-lookup"><span data-stu-id="56b17-144">Configure app assignments</span></span>

<span data-ttu-id="56b17-145">この手順では、アプリ スイートの割り当てを構成します。</span><span class="sxs-lookup"><span data-stu-id="56b17-145">In this step, configure the assignments for the app suite.</span></span> <span data-ttu-id="56b17-146">使用可能なアプリの種類はまもなく公開されます。</span><span class="sxs-lookup"><span data-stu-id="56b17-146">Note that the available app type is coming soon.</span></span>

1. <span data-ttu-id="56b17-147">アプリの一覧でアプリのスイートを選択し、**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-147">Select the app suite in the list of apps, and select **Assignments**.</span></span>
2. <span data-ttu-id="56b17-148">**[グループの選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-148">Choose **Select groups**.</span></span>
3. <span data-ttu-id="56b17-149">選択したグループにスイートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="56b17-149">Assign the suite to the groups you choose.</span></span> <span data-ttu-id="56b17-150">詳細については、「[How to assign apps to groups with Microsoft Intune (Microsoft Intune を使ってアプリをグループに割り当てる方法)](/intune/apps-deploy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56b17-150">For more information, see [How to assign apps to groups with Microsoft Intune](/intune/apps-deploy).</span></span>
4. <span data-ttu-id="56b17-151">各グループに、**[Require Install]\(インストールが必要\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="56b17-151">For each group, you select **Require Install**.</span></span>
       >[!Note]
       > You cannot uninstall Office 365 through Intune.

5. <span data-ttu-id="56b17-152">**[保存]** を選択して割り当てを確定します。</span><span class="sxs-lookup"><span data-stu-id="56b17-152">Select **Save** to commit your assignments.</span></span>

## <a name="next-steps"></a><span data-ttu-id="56b17-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="56b17-153">Next steps</span></span>

<span data-ttu-id="56b17-154">Windows 10 デバイスに Office 365 アプリを追加する方法については、「[How to assign Office 365 ProPlus 2016 apps to Windows 10 devices with Microsoft Intune (Microsoft Intune で Windows 10 デバイスに Office 365 ProPlus 2016 アプリを割り当てる方法)](/intune/apps-add-office365)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="56b17-154">To learn about adding Office 365 apps to Windows 10 device, see [How to assign Office 365 ProPlus 2016 apps to Windows 10 devices with Microsoft Intune](/intune/apps-add-office365).</span></span>
