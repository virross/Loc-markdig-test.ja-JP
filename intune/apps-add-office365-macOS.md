---
title: "Intune を使用して macOS デバイスに Office 365 をインストールします。"
titlesuffix: Azure portal
description: "MacOS デバイスに Office 365 アプリをインストールするが容易に Intune を使用する方法について説明します。"
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
ms.openlocfilehash: 5e0ad0b99a2c8a602b5e542530a1d437065461b2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a><span data-ttu-id="e6920-103">Office 365 を Microsoft Intune で macOS デバイスに割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="e6920-103">How to assign Office 365 to macOS devices with Microsoft Intune</span></span>

<span data-ttu-id="e6920-104">このアプリの種類を簡単に Office 365 アプリを macOS デバイスに割り当てることできます。</span><span class="sxs-lookup"><span data-stu-id="e6920-104">This app type makes it easy for you to assign Office 365 apps to macOS devices.</span></span> <span data-ttu-id="e6920-105">この新しいアプリの種類では、Word、Excel、PowerPoint、Outlook、および OneNote をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e6920-105">This new app type allows you to install Word, Excel, PowerPoint, Outlook, and OneNote.</span></span> <span data-ttu-id="e6920-106">これらのアプリで、Microsoft の自動更新 (MAU)、アプリをより安全かつ最新に保つためにも付属しています。</span><span class="sxs-lookup"><span data-stu-id="e6920-106">These apps also come with the Microsoft AutoUpdate (MAU), to help keep the apps more secure and up-to-date.</span></span> <span data-ttu-id="e6920-107">必要なアプリは、Intune コンソールのアプリ一覧に 1 つのアプリとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6920-107">The apps you want appear as one app in the list of apps in the Intune console.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="e6920-108">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="e6920-108">Before you start</span></span>

- <span data-ttu-id="e6920-109">これらのアプリを展開するデバイスは、macOS 10.10 またはそれ以降を実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6920-109">Devices to which you deploy these apps must be running macOS 10.10 or later.</span></span>
- <span data-ttu-id="e6920-110">Intune は、Mac のスイートの Office 2016 に含まれている追加の Office アプリのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e6920-110">Intune only supports adding Office apps included with Office 2016 for Mac suite.</span></span>
- <span data-ttu-id="e6920-111">Intune アプリ suite のインストール時に Office のすべてのアプリを開くと、エンドユーザーは、保存されていないファイルからデータを失う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e6920-111">If any Office apps are opened when Intune installs the app suite, end users might lose data from unsaved files.</span></span>


## <a name="get-started"></a><span data-ttu-id="e6920-112">作業開始</span><span class="sxs-lookup"><span data-stu-id="e6920-112">Get started</span></span>
<span data-ttu-id="e6920-113">Office 365 を使用して追加、**アプリ**ブレードです。</span><span class="sxs-lookup"><span data-stu-id="e6920-113">Add Office 365 using the **Apps** blade.</span></span>
1.  <span data-ttu-id="e6920-114">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="e6920-114">Sign into the Azure portal.</span></span>
2.  <span data-ttu-id="e6920-115">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e6920-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3.  <span data-ttu-id="e6920-116">**[Intune]** ブレードで、**[モバイル アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6920-116">On the **Intune** blade, choose **Mobile apps**.</span></span>
4.  <span data-ttu-id="e6920-117">**モバイル アプリ**ワークロード、選択**アプリ**で、**管理**グループ。</span><span class="sxs-lookup"><span data-stu-id="e6920-117">In the **Mobile apps** workload, choose **Apps** in the **Manage** group.</span></span> <span data-ttu-id="e6920-118">**[追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="e6920-118">Choose **Add**.</span></span>
5.  <span data-ttu-id="e6920-119">**アプリの追加**ブレードで、選択**Office 365** > **macOS**です。</span><span class="sxs-lookup"><span data-stu-id="e6920-119">On the **Add App** blade, choose **Office 365** > **macOS**.</span></span>
6.  <span data-ttu-id="e6920-120">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6920-120">Select **Add**.</span></span>

## <a name="configure-the-app-suite"></a><span data-ttu-id="e6920-121">アプリ スイートの構成</span><span class="sxs-lookup"><span data-stu-id="e6920-121">Configure the app suite</span></span>

<span data-ttu-id="e6920-122">アプリのスイートに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6920-122">Provide information about the app suite.</span></span> <span data-ttu-id="e6920-123">この情報は、アプリ スイートを Intune で識別したり、ユーザーが会社のポータル サイト アプリで探したりする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e6920-123">This information helps you to identify it in Intune, and also helps users to find it in the Company Portal app.</span></span>

1.  <span data-ttu-id="e6920-124">**[アプリの追加]** ブレードで、**[アプリ スイートの情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6920-124">On the **Add App** blade, choose **App Suite Information**.</span></span>
2.  <span data-ttu-id="e6920-125">次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6920-125">Specify the following information:</span></span>
    - <span data-ttu-id="e6920-126">**[スイート名]** - 会社のポータルに表示される、アプリ スイートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6920-126">**Suite Name** - Enter the name of the app suite as it is displayed in the company portal.</span></span> <span data-ttu-id="e6920-127">使用するスイート名はすべて一意にします。</span><span class="sxs-lookup"><span data-stu-id="e6920-127">Make sure all suite names that you use are unique.</span></span> <span data-ttu-id="e6920-128">同じアプリ スイート名が 2 つ存在する場合、会社のポータルではそのアプリのいずれかのみがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6920-128">If the same app suite name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="e6920-129">**[スイートの説明]** - アプリ スイートの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6920-129">**Suite Description** - Enter a description for the app suite.</span></span>
    - <span data-ttu-id="e6920-130">**パブリッシャー** -パブリッシャーとしてマイクロソフトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6920-130">**Publisher** - Microsoft appears as the publisher.</span></span>
    - <span data-ttu-id="e6920-131">**[カテゴリ]** - 必要に応じて、1 つ以上の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6920-131">**Category** - Optionally, select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="e6920-132">この操作を行うと、会社のポータルを閲覧するときに、ユーザーがアプリ スイートを探しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="e6920-132">This makes it easier for users to find the app suite when they browse the company portal.</span></span>
    - <span data-ttu-id="e6920-133">**これは会社のポータルでおすすめアプリとして表示**-これは、アプリのスイート目立つように表示、会社のポータルのメイン ページで、ユーザーがアプリを参照するとき。</span><span class="sxs-lookup"><span data-stu-id="e6920-133">**Display this as a featured app in the Company Portal** - This will display the app suite prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="e6920-134">**[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6920-134">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="e6920-135">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6920-135">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="e6920-136">**[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6920-136">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="e6920-137">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6920-137">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="e6920-138">**開発者**-開発者として、Microsoft が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6920-138">**Developer** - Microsoft appears as the developer.</span></span>
    - <span data-ttu-id="e6920-139">**所有者**-所有者として Microsoft が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6920-139">**Owner** - Microsoft appears as the owner.</span></span>
    - <span data-ttu-id="e6920-140">**[メモ]** - このアプリに関連付けるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="e6920-140">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="e6920-141">**[アイコンのアップロード]** - ユーザーが会社のポータルを参照するときに、アプリに表示されるアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e6920-141">**Upload Icon** - Upload an icon that is displayed with the app when users browse the company portal.</span></span>
3.  <span data-ttu-id="e6920-142">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6920-142">Select **OK**.</span></span> <span data-ttu-id="e6920-143">1 つのエントリとして、アプリの一覧で、スイートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6920-143">The suite appears in the list of apps as a single entry.</span></span>

## <a name="configure-app-assignments"></a><span data-ttu-id="e6920-144">アプリの割り当てを構成します。</span><span class="sxs-lookup"><span data-stu-id="e6920-144">Configure app assignments</span></span>

<span data-ttu-id="e6920-145">この手順では、アプリのスイートの割り当てを構成します。</span><span class="sxs-lookup"><span data-stu-id="e6920-145">In this step, configure the assignments for the app suite.</span></span> <span data-ttu-id="e6920-146">使用可能なアプリの種類は近日に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e6920-146">Note that the available app type is coming soon.</span></span>

1.  <span data-ttu-id="e6920-147">アプリの一覧でアプリのスイートを選択し、選択**割り当て**です。</span><span class="sxs-lookup"><span data-stu-id="e6920-147">Select the app suite in the list of apps, and select **Assignments**.</span></span>
2.  <span data-ttu-id="e6920-148">選択**グループを選択して**です。</span><span class="sxs-lookup"><span data-stu-id="e6920-148">Choose **Select groups**.</span></span>
3.  <span data-ttu-id="e6920-149">スイートを選択したグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e6920-149">Assign the suite to the groups you choose.</span></span> <span data-ttu-id="e6920-150">詳細については、「[How to assign apps to groups with Microsoft Intune (Microsoft Intune を使ってアプリをグループに割り当てる方法)](/intune/apps-deploy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6920-150">For more information, see [How to assign apps to groups with Microsoft Intune](/intune/apps-deploy).</span></span>
4.  <span data-ttu-id="e6920-151">各グループを選択する**インストールが必要**です。</span><span class="sxs-lookup"><span data-stu-id="e6920-151">For each group, you select **Require Install**.</span></span>
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. <span data-ttu-id="e6920-152">選択**保存**の割り当てをコミットします。</span><span class="sxs-lookup"><span data-stu-id="e6920-152">Select **Save** to commit your assignments.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6920-153">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e6920-153">Next steps</span></span>

<span data-ttu-id="e6920-154">Windows 10 デバイスに Office 365 アプリを追加する方法については、次を参照してください。 [Office 365 ProPlus 2016 アプリを Microsoft Intune で Windows 10 デバイスに割り当てる方法](/intune/apps-add-office365)です。</span><span class="sxs-lookup"><span data-stu-id="e6920-154">To learn about adding Office 365 apps to Windows 10 device, see [How to assign Office 365 ProPlus 2016 apps to Windows 10 devices with Microsoft Intune](/intune/apps-add-office365).</span></span>
