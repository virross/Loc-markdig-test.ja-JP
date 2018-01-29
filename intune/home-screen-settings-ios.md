---
title: "Intune を使用した iOS デバイス向けのホーム画面のレイアウト設定"
titlesuffix: Azure portal
description: "iOS デバイスのホーム画面と Dock のカスタマイズに使用できる設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6fe58c81c9854ec8a703308fa1b9223d9603d212
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="intune-home-screen-layout-settings-for-ios-devices"></a><span data-ttu-id="456ef-103">Intune を使用した iOS デバイス向けのホーム画面のレイアウト設定</span><span class="sxs-lookup"><span data-stu-id="456ef-103">Intune Home screen layout settings for iOS devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="456ef-104">これらの設定を使用すると、iOS の Dock とホーム画面で、アプリとフォルダーのレイアウトを構成できます。</span><span class="sxs-lookup"><span data-stu-id="456ef-104">Use these settings to configure the layout of apps and folders on the dock and Home screen of iOS.</span></span>

<span data-ttu-id="456ef-105">プロファイルを割り当てる iOS デバイスは、監視モードで、iOS 9.3 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="456ef-105">iOS devices to which you assign the profile must be in supervised mode and running iOS 9.3 or later.</span></span>

1. <span data-ttu-id="456ef-106">**[デバイス機能]** ブレードで、**[ホーム画面レイアウト (監視モードのみ)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="456ef-106">On the **Device features** blades choose **Home Screen Layout (supervised only)**.</span></span>
2. <span data-ttu-id="456ef-107">**[ホーム画面レイアウト (監視モードのみ)]** ブレードで、**Dock** または**ページ**のどちらのレイアウトを構成するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="456ef-107">On the **Home Screen Layout (supervised only)** blade, choose whether you want to configure the **Dock**, or **Pages** layouts.</span></span>

## <a name="add-items-to-the-dock"></a><span data-ttu-id="456ef-108">Dock にアイテムを追加する</span><span class="sxs-lookup"><span data-stu-id="456ef-108">Add items to the dock</span></span>

<span data-ttu-id="456ef-109">**[Dock]** ブレードで、iOS 画面の Dock に最大 6 つのアイテムまたはフォルダーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="456ef-109">On the **Dock** blade, you can add up to six items or folders to the dock of the iOS screen.</span></span> <span data-ttu-id="456ef-110">ただし、多くのデバイスではサポートされるアイテム数は少なく、たとえば iPhone では最大で 4 つのアイテムがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="456ef-110">However, many devices support fewer items; for example, iPhone devices support up to four items.</span></span> <span data-ttu-id="456ef-111">この場合、構成した最初の 4 つのアイテムのみがデバイスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="456ef-111">In this case, only the first four items you configured are displayed on the device.</span></span>

1. <span data-ttu-id="456ef-112">**[追加]** を選択してアイテムを Dock に追加します。</span><span class="sxs-lookup"><span data-stu-id="456ef-112">Choose **Add** to add an item to the dock.</span></span>
2. <span data-ttu-id="456ef-113">**[行の追加]** ブレードで、**アプリ**または**フォルダー**のどちらを追加するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="456ef-113">On the **Add Row** blade, choose whether you want to add an **App**, or a **Folder**.</span></span>
3. <span data-ttu-id="456ef-114">このトピックの情報を使って、Dock に表示するアプリとフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="456ef-114">Using the information in this topic, configure the apps and folders you want to appear in the dock.</span></span>
4. <span data-ttu-id="456ef-115">アイテムの追加を続けます。</span><span class="sxs-lookup"><span data-stu-id="456ef-115">Continue to add items.</span></span> <span data-ttu-id="456ef-116">完了したら、**[プロファイルの作成]** ブレードに戻るまで、各ブレードで **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="456ef-116">When you are finished, click **OK** on each blade until you return to the **Create Profile** blade.</span></span> <span data-ttu-id="456ef-117">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="456ef-117">Choose **Create**.</span></span>

>[!TIP]
> <span data-ttu-id="456ef-118">ホーム画面とページの一覧でアイテムをドラッグ & ドロップして、順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="456ef-118">You can drag and drop items in any Home screen and pages lists to reorder them.</span></span> 

### <a name="example"></a><span data-ttu-id="456ef-119">例</span><span class="sxs-lookup"><span data-stu-id="456ef-119">Example</span></span>

<span data-ttu-id="456ef-120">この例では、Dock 画面に Safari、メール、および株価アプリのみが表示されるように構成しました。</span><span class="sxs-lookup"><span data-stu-id="456ef-120">In this example, you've configured the dock screen to show only the Safari, Mail, and Stocks apps.</span></span> <span data-ttu-id="456ef-121">次の画像では、メール アプリが選択され、そのプロパティが表示されています。</span><span class="sxs-lookup"><span data-stu-id="456ef-121">In the following image, the Mail app is selected to illustrate its properties:</span></span>

![iOS Dock 設定のサンプル](http://i.imgur.com/FfFiUcP.png)

<span data-ttu-id="456ef-123">iPhone にポリシーを割り当てると、結果は次のスクリーンショットのような Dock になります。</span><span class="sxs-lookup"><span data-stu-id="456ef-123">When you assign the policy to an iPhone, the result is a dock that looks similar to this screenshot:</span></span>

![iPhone の iOS Dock のレイアウト サンプル](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a><span data-ttu-id="456ef-125">ホーム画面ページを追加する</span><span class="sxs-lookup"><span data-stu-id="456ef-125">Add Home screen pages</span></span>

<span data-ttu-id="456ef-126">ホーム画面に表示するページと、各ページに表示されるアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="456ef-126">Add the pages you want to appear on the home screen, and the apps that appear on each page.</span></span> <span data-ttu-id="456ef-127">ページに追加したアプリは、一覧で指定した順序で左から右に配置されます。</span><span class="sxs-lookup"><span data-stu-id="456ef-127">Apps that you add to a page are arranged from left to right, in the order they are specified in the list.</span></span> <span data-ttu-id="456ef-128">1 つのページに収まるよりも多くのアプリを追加すると、残りのアプリは次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="456ef-128">If you add more apps than can fit on a page, the apps are moved to a subsequent page.</span></span>


1. <span data-ttu-id="456ef-129">**[ページ]** ブレードで **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="456ef-129">On the **Pages** blade, choose **Add**.</span></span>
2. <span data-ttu-id="456ef-130">**[行の追加]** ブレードで、**ページ名**を入力します。</span><span class="sxs-lookup"><span data-stu-id="456ef-130">On the **Add Row** blade, enter a **Page name**.</span></span> <span data-ttu-id="456ef-131">この名前は Azure Portal での参照用に使われ、iOS デバイスでは*表示されません*。</span><span class="sxs-lookup"><span data-stu-id="456ef-131">This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.</span></span>
3. <span data-ttu-id="456ef-132">**[追加]** を選択し、ページに**アプリ**または**フォルダー**のどちらを追加するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="456ef-132">Choose **Add**, then choose whether you want to add an **App**, or a **Folder** to the page.</span></span>
4. <span data-ttu-id="456ef-133">このトピックの情報を使って、ページに表示するアプリとフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="456ef-133">Using the information in this topic, configure the apps and folders you want to appear on the page.</span></span>

### <a name="example"></a><span data-ttu-id="456ef-134">例</span><span class="sxs-lookup"><span data-stu-id="456ef-134">Example</span></span>

<span data-ttu-id="456ef-135">この例では、**Contoso** という名前の新しいページを構成しています。</span><span class="sxs-lookup"><span data-stu-id="456ef-135">In this example, you've configured a new page named **Contoso**.</span></span> <span data-ttu-id="456ef-136">ページには、"友達を探す" と "設定" アプリのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="456ef-136">The page shows only the Find Friends, and Settings apps.</span></span> <span data-ttu-id="456ef-137">次の画像では、設定アプリが選択され、そのプロパティが表示されています。</span><span class="sxs-lookup"><span data-stu-id="456ef-137">In the following image, the Settings app is selected to illustrate its properties:</span></span>

![iOS ホーム画面の設定例](http://i.imgur.com/Jc2OxyX.png)

<span data-ttu-id="456ef-139">iPhone にポリシーを割り当てると、結果は次のスクリーンショットのようなページになります。</span><span class="sxs-lookup"><span data-stu-id="456ef-139">When you assign the policy to an iPhone, the result is a page that looks similar to this screenshot:</span></span>

![ホーム画面が変更された iOS デバイス](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a><span data-ttu-id="456ef-141">アプリを一覧に追加する方法</span><span class="sxs-lookup"><span data-stu-id="456ef-141">How to add an app to the list</span></span>

1. <span data-ttu-id="456ef-142">**[アプリ名]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="456ef-142">Enter the **App Name**.</span></span> <span data-ttu-id="456ef-143">この名前は Azure Portal での参照用に使われ、iOS デバイスでは*表示されません*。</span><span class="sxs-lookup"><span data-stu-id="456ef-143">This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.</span></span>
2. <span data-ttu-id="456ef-144">表示するアプリの **[アプリ バンドル ID]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="456ef-144">Enter the **App Bundle ID** of the app you want to display.</span></span> <span data-ttu-id="456ef-145">詳細については、このトピックで後述する「**組み込み iOS アプリのバンドル ID リファレンス**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="456ef-145">See **Bundle ID reference for built-in iOS apps** later in this topic for help.</span></span>
3. <span data-ttu-id="456ef-146">**[OK]** をクリックして、アイテムを引き続き追加します。デバイスの Dock には最大 **6** 個、デバイスのページには最大 **60** 個までアイテムを追加できます。</span><span class="sxs-lookup"><span data-stu-id="456ef-146">Click **OK**, then continue to add items, up to a maximum of **6** for the device dock, and **60** for a device page.</span></span>
4. <span data-ttu-id="456ef-147">操作が完了したら、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="456ef-147">When you are finished, click **OK**.</span></span>

## <a name="how-to-add-a-folder-to-the-list"></a><span data-ttu-id="456ef-148">フォルダーを一覧に追加する方法</span><span class="sxs-lookup"><span data-stu-id="456ef-148">How to add a folder to the list</span></span>

<span data-ttu-id="456ef-149">フォルダー内のページに追加したアプリは、一覧で指定した順序で左から右に配置されます。</span><span class="sxs-lookup"><span data-stu-id="456ef-149">Apps that you add to a page in a folder are arranged from left to right, in the order they are specified in the list.</span></span> <span data-ttu-id="456ef-150">1 つのページに収まるよりも多くのアプリを追加すると、残りのアプリは次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="456ef-150">If you add more apps than can fit on a page, the apps are moved to a subsequent page.</span></span>

1. <span data-ttu-id="456ef-151">**[フォルダー名]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="456ef-151">Enter the **Folder name**.</span></span> <span data-ttu-id="456ef-152">この名前は、デバイスでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="456ef-152">This name is displayed to users on their device.</span></span>
2. <span data-ttu-id="456ef-153">**[追加]** を選択してフォルダー内にページを作成します。</span><span class="sxs-lookup"><span data-stu-id="456ef-153">Choose **Add** to create a page in the folder.</span></span> <span data-ttu-id="456ef-154">最大 20 ページまで追加できます。</span><span class="sxs-lookup"><span data-stu-id="456ef-154">You can add up to 20 pages.</span></span>
3. <span data-ttu-id="456ef-155">**[行の追加]** ブレードで、ページの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="456ef-155">On the **Add Row** blade, enter a name for the page.</span></span> <span data-ttu-id="456ef-156">この名前は Azure Portal での参照用に使われ、iOS デバイスでは*表示されません*。</span><span class="sxs-lookup"><span data-stu-id="456ef-156">This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.</span></span>
3. <span data-ttu-id="456ef-157">**[アプリ名]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="456ef-157">Enter the **App Name**.</span></span> <span data-ttu-id="456ef-158">この名前は Azure Portal での参照用に使われ、iOS デバイスでは*表示されません*。</span><span class="sxs-lookup"><span data-stu-id="456ef-158">This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.</span></span>
2. <span data-ttu-id="456ef-159">表示するアプリの **[アプリ バンドル ID]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="456ef-159">Enter the **App Bundle ID** of the app you want to display.</span></span> <span data-ttu-id="456ef-160">詳細については、「**アプリを一覧に追加する方法**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="456ef-160">See **How to add an app to the list** for help.</span></span>
3. <span data-ttu-id="456ef-161">**[追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="456ef-161">Choose **Add**.</span></span> <span data-ttu-id="456ef-162">最大 60 アイテムまで追加できます。</span><span class="sxs-lookup"><span data-stu-id="456ef-162">You can add up to 60 items.</span></span>
4. <span data-ttu-id="456ef-163">操作が完了したら、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="456ef-163">When you are finished, click **OK**.</span></span>


## <a name="bundle-id-reference-for-built-in-ios-apps"></a><span data-ttu-id="456ef-164">組み込み iOS アプリのバンドル ID リファレンス</span><span class="sxs-lookup"><span data-stu-id="456ef-164">Bundle ID reference for built-in iOS apps</span></span>

<span data-ttu-id="456ef-165">この一覧は、一般的な組み込み iOS アプリのバンドル ID を示しています。</span><span class="sxs-lookup"><span data-stu-id="456ef-165">This list shows the bundle ID of some common built-in iOS apps.</span></span> <span data-ttu-id="456ef-166">他のアプリのバンドル ID を調べるには、ソフトウェア ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="456ef-166">To find the bundle ID of other apps, contact your software vendor.</span></span> 

|||
|-|-|
|<span data-ttu-id="456ef-167">アプリ名</span><span class="sxs-lookup"><span data-stu-id="456ef-167">App name</span></span>|<span data-ttu-id="456ef-168">バンドル ID</span><span class="sxs-lookup"><span data-stu-id="456ef-168">BundleID</span></span>|
|<span data-ttu-id="456ef-169">アプリ ストア</span><span class="sxs-lookup"><span data-stu-id="456ef-169">App Store</span></span>|<span data-ttu-id="456ef-170">com.apple.AppStore</span><span class="sxs-lookup"><span data-stu-id="456ef-170">com.apple.AppStore</span></span>|
|<span data-ttu-id="456ef-171">計算機</span><span class="sxs-lookup"><span data-stu-id="456ef-171">Calculator</span></span>|<span data-ttu-id="456ef-172">com.apple.calculator</span><span class="sxs-lookup"><span data-stu-id="456ef-172">com.apple.calculator</span></span>|
|<span data-ttu-id="456ef-173">予定表</span><span class="sxs-lookup"><span data-stu-id="456ef-173">Calendar</span></span>|<span data-ttu-id="456ef-174">com.apple.mobilecal</span><span class="sxs-lookup"><span data-stu-id="456ef-174">com.apple.mobilecal</span></span>|
|<span data-ttu-id="456ef-175">カメラ</span><span class="sxs-lookup"><span data-stu-id="456ef-175">Camera</span></span>|<span data-ttu-id="456ef-176">com.apple.camera</span><span class="sxs-lookup"><span data-stu-id="456ef-176">com.apple.camera</span></span>|
|<span data-ttu-id="456ef-177">時計</span><span class="sxs-lookup"><span data-stu-id="456ef-177">Clock</span></span>|<span data-ttu-id="456ef-178">com.apple.mobiletimer</span><span class="sxs-lookup"><span data-stu-id="456ef-178">com.apple.mobiletimer</span></span>|
|<span data-ttu-id="456ef-179">コンパス</span><span class="sxs-lookup"><span data-stu-id="456ef-179">Compass</span></span>|<span data-ttu-id="456ef-180">com.apple.compass</span><span class="sxs-lookup"><span data-stu-id="456ef-180">com.apple.compass</span></span>|
|<span data-ttu-id="456ef-181">連絡先</span><span class="sxs-lookup"><span data-stu-id="456ef-181">Contacts</span></span>|<span data-ttu-id="456ef-182">com.apple.MobileAddressBook</span><span class="sxs-lookup"><span data-stu-id="456ef-182">com.apple.MobileAddressBook</span></span>|
|<span data-ttu-id="456ef-183">FaceTime</span><span class="sxs-lookup"><span data-stu-id="456ef-183">FaceTime</span></span>|<span data-ttu-id="456ef-184">com.apple.facetime</span><span class="sxs-lookup"><span data-stu-id="456ef-184">com.apple.facetime</span></span>|
|<span data-ttu-id="456ef-185">友達を探す</span><span class="sxs-lookup"><span data-stu-id="456ef-185">Find Friends</span></span>|<span data-ttu-id="456ef-186">com.apple.mobileme.fmf1</span><span class="sxs-lookup"><span data-stu-id="456ef-186">com.apple.mobileme.fmf1</span></span>|
|<span data-ttu-id="456ef-187">Find iPhone</span><span class="sxs-lookup"><span data-stu-id="456ef-187">Find iPhone</span></span>|<span data-ttu-id="456ef-188">com.apple.mobileme.fmip1</span><span class="sxs-lookup"><span data-stu-id="456ef-188">com.apple.mobileme.fmip1</span></span>|
|<span data-ttu-id="456ef-189">Game Center</span><span class="sxs-lookup"><span data-stu-id="456ef-189">Game Center</span></span>|<span data-ttu-id="456ef-190">com.apple.gamecenter</span><span class="sxs-lookup"><span data-stu-id="456ef-190">com.apple.gamecenter</span></span>|
|<span data-ttu-id="456ef-191">GarageBand</span><span class="sxs-lookup"><span data-stu-id="456ef-191">GarageBand</span></span>|<span data-ttu-id="456ef-192">com.apple.mobilegarageband</span><span class="sxs-lookup"><span data-stu-id="456ef-192">com.apple.mobilegarageband</span></span>|
|<span data-ttu-id="456ef-193">正常性</span><span class="sxs-lookup"><span data-stu-id="456ef-193">Health</span></span>|<span data-ttu-id="456ef-194">com.apple.Health</span><span class="sxs-lookup"><span data-stu-id="456ef-194">com.apple.Health</span></span>|
|<span data-ttu-id="456ef-195">iBooks</span><span class="sxs-lookup"><span data-stu-id="456ef-195">iBooks</span></span>|<span data-ttu-id="456ef-196">com.apple.iBooks</span><span class="sxs-lookup"><span data-stu-id="456ef-196">com.apple.iBooks</span></span>|
|<span data-ttu-id="456ef-197">iTunes Store</span><span class="sxs-lookup"><span data-stu-id="456ef-197">iTunes Store</span></span>|<span data-ttu-id="456ef-198">com.apple.MobileStore</span><span class="sxs-lookup"><span data-stu-id="456ef-198">com.apple.MobileStore</span></span>|
|<span data-ttu-id="456ef-199">iTunes U</span><span class="sxs-lookup"><span data-stu-id="456ef-199">iTunes U</span></span>|<span data-ttu-id="456ef-200">com.apple.itunesu</span><span class="sxs-lookup"><span data-stu-id="456ef-200">com.apple.itunesu</span></span>|
|<span data-ttu-id="456ef-201">Keynote</span><span class="sxs-lookup"><span data-stu-id="456ef-201">Keynote</span></span>|<span data-ttu-id="456ef-202">com.apple.Keynote</span><span class="sxs-lookup"><span data-stu-id="456ef-202">com.apple.Keynote</span></span>|
|<span data-ttu-id="456ef-203">メール</span><span class="sxs-lookup"><span data-stu-id="456ef-203">Mail</span></span>|<span data-ttu-id="456ef-204">com.apple.mobilemail</span><span class="sxs-lookup"><span data-stu-id="456ef-204">com.apple.mobilemail</span></span>|
|<span data-ttu-id="456ef-205">マップ</span><span class="sxs-lookup"><span data-stu-id="456ef-205">Maps</span></span>|<span data-ttu-id="456ef-206">com.apple.Maps</span><span class="sxs-lookup"><span data-stu-id="456ef-206">com.apple.Maps</span></span>|
|<span data-ttu-id="456ef-207">メッセージ</span><span class="sxs-lookup"><span data-stu-id="456ef-207">Messages</span></span>|<span data-ttu-id="456ef-208">com.apple.MobileSMS</span><span class="sxs-lookup"><span data-stu-id="456ef-208">com.apple.MobileSMS</span></span>|
|<span data-ttu-id="456ef-209">ミュージック</span><span class="sxs-lookup"><span data-stu-id="456ef-209">Music</span></span>|<span data-ttu-id="456ef-210">com.apple.Music</span><span class="sxs-lookup"><span data-stu-id="456ef-210">com.apple.Music</span></span>|
|<span data-ttu-id="456ef-211">News</span><span class="sxs-lookup"><span data-stu-id="456ef-211">News</span></span>|<span data-ttu-id="456ef-212">com.apple.news</span><span class="sxs-lookup"><span data-stu-id="456ef-212">com.apple.news</span></span>|
|<span data-ttu-id="456ef-213">注</span><span class="sxs-lookup"><span data-stu-id="456ef-213">Notes</span></span>|<span data-ttu-id="456ef-214">com.apple.mobilenotes</span><span class="sxs-lookup"><span data-stu-id="456ef-214">com.apple.mobilenotes</span></span>|
|<span data-ttu-id="456ef-215">数字</span><span class="sxs-lookup"><span data-stu-id="456ef-215">Numbers</span></span>|<span data-ttu-id="456ef-216">com.apple.Numbers</span><span class="sxs-lookup"><span data-stu-id="456ef-216">com.apple.Numbers</span></span>|
|<span data-ttu-id="456ef-217">ページ</span><span class="sxs-lookup"><span data-stu-id="456ef-217">Pages</span></span>|<span data-ttu-id="456ef-218">com.apple.Pages</span><span class="sxs-lookup"><span data-stu-id="456ef-218">com.apple.Pages</span></span>|
|<span data-ttu-id="456ef-219">Photo Booth</span><span class="sxs-lookup"><span data-stu-id="456ef-219">Photo Booth</span></span>|<span data-ttu-id="456ef-220">com.apple.Photo-Booth</span><span class="sxs-lookup"><span data-stu-id="456ef-220">com.apple.Photo-Booth</span></span>|
|<span data-ttu-id="456ef-221">写真</span><span class="sxs-lookup"><span data-stu-id="456ef-221">Photos</span></span>|<span data-ttu-id="456ef-222">com.apple.mobileslideshow</span><span class="sxs-lookup"><span data-stu-id="456ef-222">com.apple.mobileslideshow</span></span>|
|<span data-ttu-id="456ef-223">Podcast</span><span class="sxs-lookup"><span data-stu-id="456ef-223">Podcasts</span></span>|<span data-ttu-id="456ef-224">com.apple.podcasts</span><span class="sxs-lookup"><span data-stu-id="456ef-224">com.apple.podcasts</span></span>|
|<span data-ttu-id="456ef-225">リマインダー</span><span class="sxs-lookup"><span data-stu-id="456ef-225">Reminders</span></span>|<span data-ttu-id="456ef-226">com.apple.reminders</span><span class="sxs-lookup"><span data-stu-id="456ef-226">com.apple.reminders</span></span>|
|<span data-ttu-id="456ef-227">Safari</span><span class="sxs-lookup"><span data-stu-id="456ef-227">Safari</span></span>|<span data-ttu-id="456ef-228">com.apple.mobilesafari</span><span class="sxs-lookup"><span data-stu-id="456ef-228">com.apple.mobilesafari</span></span>|
|<span data-ttu-id="456ef-229">Settings</span><span class="sxs-lookup"><span data-stu-id="456ef-229">Settings</span></span>|<span data-ttu-id="456ef-230">com.apple.Preferences</span><span class="sxs-lookup"><span data-stu-id="456ef-230">com.apple.Preferences</span></span>|
|<span data-ttu-id="456ef-231">株価</span><span class="sxs-lookup"><span data-stu-id="456ef-231">Stocks</span></span>|<span data-ttu-id="456ef-232">com.apple.stocks</span><span class="sxs-lookup"><span data-stu-id="456ef-232">com.apple.stocks</span></span>|
|<span data-ttu-id="456ef-233">ヒント</span><span class="sxs-lookup"><span data-stu-id="456ef-233">Tips</span></span>|<span data-ttu-id="456ef-234">com.apple.tips</span><span class="sxs-lookup"><span data-stu-id="456ef-234">com.apple.tips</span></span>|
|<span data-ttu-id="456ef-235">ビデオ</span><span class="sxs-lookup"><span data-stu-id="456ef-235">Videos</span></span>|<span data-ttu-id="456ef-236">com.apple.videos</span><span class="sxs-lookup"><span data-stu-id="456ef-236">com.apple.videos</span></span>|
|<span data-ttu-id="456ef-237">VoiceMemos</span><span class="sxs-lookup"><span data-stu-id="456ef-237">VoiceMemos</span></span>|<span data-ttu-id="456ef-238">com.apple.VoiceMemos</span><span class="sxs-lookup"><span data-stu-id="456ef-238">com.apple.VoiceMemos</span></span>|
|<span data-ttu-id="456ef-239">Wallet</span><span class="sxs-lookup"><span data-stu-id="456ef-239">Wallet</span></span>|<span data-ttu-id="456ef-240">com.apple.Passbook</span><span class="sxs-lookup"><span data-stu-id="456ef-240">com.apple.Passbook</span></span>|
|<span data-ttu-id="456ef-241">視聴する</span><span class="sxs-lookup"><span data-stu-id="456ef-241">Watch</span></span>|<span data-ttu-id="456ef-242">com.apple.Bridge</span><span class="sxs-lookup"><span data-stu-id="456ef-242">com.apple.Bridge</span></span>|
|<span data-ttu-id="456ef-243">天気</span><span class="sxs-lookup"><span data-stu-id="456ef-243">Weather</span></span>|<span data-ttu-id="456ef-244">com.apple.weather</span><span class="sxs-lookup"><span data-stu-id="456ef-244">com.apple.weather</span></span>|


## <a name="next-steps"></a><span data-ttu-id="456ef-245">次の手順</span><span class="sxs-lookup"><span data-stu-id="456ef-245">Next steps</span></span>

<span data-ttu-id="456ef-246">選択したグループにデバイス プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="456ef-246">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="456ef-247">詳しくは、「[デバイス プロファイルを割り当てる方法](device-profile-assign.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="456ef-247">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
