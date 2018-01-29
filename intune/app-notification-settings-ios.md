---
title: "Intune を使用した iOS デバイス向けのアプリ通知設定"
titlesuffix: Azure portal
description: "iOS デバイスでアプリからの通知を制御するために使用できる設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f5b7c1c5d2286bbf14d82e4c09895c520177fdb6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="intune-app-notifications-settings-for-ios-devices"></a><span data-ttu-id="6fa98-103">Intune を使用した iOS デバイス向けのアプリ通知設定</span><span class="sxs-lookup"><span data-stu-id="6fa98-103">Intune app notifications settings for iOS devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="6fa98-104">デバイスにインストールされているアプリが通知を送信する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6fa98-104">Lets you configure how apps installed on a device send notifications.</span></span> <span data-ttu-id="6fa98-105">これらの設定は、iOS 9.3 以降を実行している監視対象のデバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6fa98-105">These settings support supervised devices running iOS 9.3 and later.</span></span>

## <a name="configure-settings"></a><span data-ttu-id="6fa98-106">設定の構成</span><span class="sxs-lookup"><span data-stu-id="6fa98-106">Configure settings</span></span>

1. <span data-ttu-id="6fa98-107">[デバイス機能] ブレードで、**[アプリの通知 (監視のみ)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-107">On the Device features blade, choose **App Notifications (supervised only)**.</span></span>
2. <span data-ttu-id="6fa98-108">**[アプリの通知]** ブレードで、**[追加]** を選択し、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-108">On the **App Notifications** blade, choose **Add**, and then configure the following values:</span></span>
    - <span data-ttu-id="6fa98-109">**[アプリ バンドル ID]** - 構成するアプリの**アプリ バンドル ID** を入力します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-109">**App bundle ID** - Enter the **App Bundle ID** of the app you want to configure.</span></span> <span data-ttu-id="6fa98-110">詳細については、このトピックで後述する「**組み込み iOS アプリのバンドル ID リファレンス**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6fa98-110">See **Bundle ID reference for built-in iOS apps** later in this topic for help.</span></span>
    - <span data-ttu-id="6fa98-111">**[アプリ名]** - 構成するアプリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-111">**App name** - Enter the name of the app you want to configure.</span></span> <span data-ttu-id="6fa98-112">この名前はデバイスでは表示されず、一覧のアプリを識別するために使われます。</span><span class="sxs-lookup"><span data-stu-id="6fa98-112">This name is not displayed on the device and is used to help you identify the app in the list.</span></span>
    - <span data-ttu-id="6fa98-113">**[発行元]** - 構成するアプリの発行元を入力します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-113">**Publisher** - Enter the publisher of the app you want to configure.</span></span> <span data-ttu-id="6fa98-114">発行元はデバイスでは表示されず、一覧のアプリを識別するためにのみ使われます。</span><span class="sxs-lookup"><span data-stu-id="6fa98-114">The publisher name is not displayed on the device, and is used only to help you identify the app in the list.</span></span>
    - <span data-ttu-id="6fa98-115">**[通知]** - アプリがデバイスに通知を送信するのを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6fa98-115">**Notifications** - Enable or disable the app from sending notifications to the device.</span></span> <span data-ttu-id="6fa98-116">この設定を無効にすると、次の設定も無効になります。</span><span class="sxs-lookup"><span data-stu-id="6fa98-116">If you disable this setting, the following settings are also disabled.</span></span>
        - <span data-ttu-id="6fa98-117">**[通知センターに表示する]** - この設定を有効にすると、アプリがデバイスの通知センターに通知を表示することを許可します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-117">**Show in Notification Center** - Enable this setting to allow the app to show notifications in the device Notification Center.</span></span>
        - <span data-ttu-id="6fa98-118">**[ロック画面に表示する]** - この設定を有効にすると、アプリからの通知がデバイスのロック画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fa98-118">**Show in Lock Screen** - Enable this setting to see notifications from the app on the device lock screen.</span></span>
        - <span data-ttu-id="6fa98-119">**[アラートの種類]** - デバイスのロックが解除されたときの通知の種類を、次から選びます。</span><span class="sxs-lookup"><span data-stu-id="6fa98-119">**Alert type** - Select the type of notification you want when the device is unlocked from:</span></span>
            - <span data-ttu-id="6fa98-120">**[なし]** - 通知は表示されません。</span><span class="sxs-lookup"><span data-stu-id="6fa98-120">**None** - No notification is displayed.</span></span>
            - <span data-ttu-id="6fa98-121">**[バナー]** - 通知を示すバナーが短時間表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fa98-121">**Banner** - A banner is briefly displayed showing the notification.</span></span>
            - <span data-ttu-id="6fa98-122">**[モーダル]** - 通知が表示され、ユーザーはデバイスの使用を続ける前に、手動でこの通知を消す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa98-122">**Modal** - The notification is displayed and the user must manually dismiss it before you can continue to use the device.</span></span>
        - <span data-ttu-id="6fa98-123">**[アプリ アイコンのバッジ]** - この設定を有効にすると、アプリが通知を送信したことを示すバッジがアプリ アイコンに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6fa98-123">**Badge on app icon** - Enable this setting to add a badge to the app icon to indicate the app sent a notification.</span></span>
        - <span data-ttu-id="6fa98-124">**[サウンド]** - この設定を有効にすると、通知の配信時にサウンドを再生します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-124">**Sounds** - Enable this setting to play a sound when a notification is delivered.</span></span>
3. <span data-ttu-id="6fa98-125">必要な数のアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-125">Continue to add as many apps as you need.</span></span> <span data-ttu-id="6fa98-126">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-126">When you are finished, choose **OK**.</span></span>
4. <span data-ttu-id="6fa98-127">**[プロファイルの作成]** ブレードに戻るまで **[OK]** を選択し、ブレードに戻ったら **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6fa98-127">Choose **OK** until you return to the **Create Profile** blade, then choose **Create**.</span></span> 


## <a name="bundle-id-reference-for-built-in-ios-apps"></a><span data-ttu-id="6fa98-128">組み込み iOS アプリのバンドル ID リファレンス</span><span class="sxs-lookup"><span data-stu-id="6fa98-128">Bundle ID reference for built-in iOS apps</span></span>

<span data-ttu-id="6fa98-129">この一覧は、一般的な組み込み iOS アプリのバンドル ID を示しています。</span><span class="sxs-lookup"><span data-stu-id="6fa98-129">This list shows the bundle ID of some common built-in iOS apps.</span></span> <span data-ttu-id="6fa98-130">他のアプリのバンドル ID を調べるには、ソフトウェア ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6fa98-130">To find the bundle ID of other apps, contact your software vendor.</span></span> 

|||
|-|-|
|<span data-ttu-id="6fa98-131">アプリ名</span><span class="sxs-lookup"><span data-stu-id="6fa98-131">App name</span></span>|<span data-ttu-id="6fa98-132">バンドル ID</span><span class="sxs-lookup"><span data-stu-id="6fa98-132">BundleID</span></span>|
|<span data-ttu-id="6fa98-133">アプリ ストア</span><span class="sxs-lookup"><span data-stu-id="6fa98-133">App Store</span></span>|<span data-ttu-id="6fa98-134">com.apple.AppStore</span><span class="sxs-lookup"><span data-stu-id="6fa98-134">com.apple.AppStore</span></span>|
|<span data-ttu-id="6fa98-135">計算機</span><span class="sxs-lookup"><span data-stu-id="6fa98-135">Calculator</span></span>|<span data-ttu-id="6fa98-136">com.apple.calculator</span><span class="sxs-lookup"><span data-stu-id="6fa98-136">com.apple.calculator</span></span>|
|<span data-ttu-id="6fa98-137">予定表</span><span class="sxs-lookup"><span data-stu-id="6fa98-137">Calendar</span></span>|<span data-ttu-id="6fa98-138">com.apple.mobilecal</span><span class="sxs-lookup"><span data-stu-id="6fa98-138">com.apple.mobilecal</span></span>|
|<span data-ttu-id="6fa98-139">カメラ</span><span class="sxs-lookup"><span data-stu-id="6fa98-139">Camera</span></span>|<span data-ttu-id="6fa98-140">com.apple.camera</span><span class="sxs-lookup"><span data-stu-id="6fa98-140">com.apple.camera</span></span>|
|<span data-ttu-id="6fa98-141">時計</span><span class="sxs-lookup"><span data-stu-id="6fa98-141">Clock</span></span>|<span data-ttu-id="6fa98-142">com.apple.mobiletimer</span><span class="sxs-lookup"><span data-stu-id="6fa98-142">com.apple.mobiletimer</span></span>|
|<span data-ttu-id="6fa98-143">コンパス</span><span class="sxs-lookup"><span data-stu-id="6fa98-143">Compass</span></span>|<span data-ttu-id="6fa98-144">com.apple.compass</span><span class="sxs-lookup"><span data-stu-id="6fa98-144">com.apple.compass</span></span>|
|<span data-ttu-id="6fa98-145">連絡先</span><span class="sxs-lookup"><span data-stu-id="6fa98-145">Contacts</span></span>|<span data-ttu-id="6fa98-146">com.apple.MobileAddressBook</span><span class="sxs-lookup"><span data-stu-id="6fa98-146">com.apple.MobileAddressBook</span></span>|
|<span data-ttu-id="6fa98-147">FaceTime</span><span class="sxs-lookup"><span data-stu-id="6fa98-147">FaceTime</span></span>|<span data-ttu-id="6fa98-148">com.apple.facetime</span><span class="sxs-lookup"><span data-stu-id="6fa98-148">com.apple.facetime</span></span>|
|<span data-ttu-id="6fa98-149">友達を探す</span><span class="sxs-lookup"><span data-stu-id="6fa98-149">Find Friends</span></span>|<span data-ttu-id="6fa98-150">com.apple.mobileme.fmf1</span><span class="sxs-lookup"><span data-stu-id="6fa98-150">com.apple.mobileme.fmf1</span></span>|
|<span data-ttu-id="6fa98-151">Find iPhone</span><span class="sxs-lookup"><span data-stu-id="6fa98-151">Find iPhone</span></span>|<span data-ttu-id="6fa98-152">com.apple.mobileme.fmip1</span><span class="sxs-lookup"><span data-stu-id="6fa98-152">com.apple.mobileme.fmip1</span></span>|
|<span data-ttu-id="6fa98-153">Game Center</span><span class="sxs-lookup"><span data-stu-id="6fa98-153">Game Center</span></span>|<span data-ttu-id="6fa98-154">com.apple.gamecenter</span><span class="sxs-lookup"><span data-stu-id="6fa98-154">com.apple.gamecenter</span></span>|
|<span data-ttu-id="6fa98-155">GarageBand</span><span class="sxs-lookup"><span data-stu-id="6fa98-155">GarageBand</span></span>|<span data-ttu-id="6fa98-156">com.apple.mobilegarageband</span><span class="sxs-lookup"><span data-stu-id="6fa98-156">com.apple.mobilegarageband</span></span>|
|<span data-ttu-id="6fa98-157">正常性</span><span class="sxs-lookup"><span data-stu-id="6fa98-157">Health</span></span>|<span data-ttu-id="6fa98-158">com.apple.Health</span><span class="sxs-lookup"><span data-stu-id="6fa98-158">com.apple.Health</span></span>|
|<span data-ttu-id="6fa98-159">iBooks</span><span class="sxs-lookup"><span data-stu-id="6fa98-159">iBooks</span></span>|<span data-ttu-id="6fa98-160">com.apple.iBooks</span><span class="sxs-lookup"><span data-stu-id="6fa98-160">com.apple.iBooks</span></span>|
|<span data-ttu-id="6fa98-161">iTunes Store</span><span class="sxs-lookup"><span data-stu-id="6fa98-161">iTunes Store</span></span>|<span data-ttu-id="6fa98-162">com.apple.MobileStore</span><span class="sxs-lookup"><span data-stu-id="6fa98-162">com.apple.MobileStore</span></span>|
|<span data-ttu-id="6fa98-163">iTunes U</span><span class="sxs-lookup"><span data-stu-id="6fa98-163">iTunes U</span></span>|<span data-ttu-id="6fa98-164">com.apple.itunesu</span><span class="sxs-lookup"><span data-stu-id="6fa98-164">com.apple.itunesu</span></span>|
|<span data-ttu-id="6fa98-165">Keynote</span><span class="sxs-lookup"><span data-stu-id="6fa98-165">Keynote</span></span>|<span data-ttu-id="6fa98-166">com.apple.Keynote</span><span class="sxs-lookup"><span data-stu-id="6fa98-166">com.apple.Keynote</span></span>|
|<span data-ttu-id="6fa98-167">メール</span><span class="sxs-lookup"><span data-stu-id="6fa98-167">Mail</span></span>|<span data-ttu-id="6fa98-168">com.apple.mobilemail</span><span class="sxs-lookup"><span data-stu-id="6fa98-168">com.apple.mobilemail</span></span>|
|<span data-ttu-id="6fa98-169">マップ</span><span class="sxs-lookup"><span data-stu-id="6fa98-169">Maps</span></span>|<span data-ttu-id="6fa98-170">com.apple.Maps</span><span class="sxs-lookup"><span data-stu-id="6fa98-170">com.apple.Maps</span></span>|
|<span data-ttu-id="6fa98-171">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6fa98-171">Messages</span></span>|<span data-ttu-id="6fa98-172">com.apple.MobileSMS</span><span class="sxs-lookup"><span data-stu-id="6fa98-172">com.apple.MobileSMS</span></span>|
|<span data-ttu-id="6fa98-173">ミュージック</span><span class="sxs-lookup"><span data-stu-id="6fa98-173">Music</span></span>|<span data-ttu-id="6fa98-174">com.apple.Music</span><span class="sxs-lookup"><span data-stu-id="6fa98-174">com.apple.Music</span></span>|
|<span data-ttu-id="6fa98-175">News</span><span class="sxs-lookup"><span data-stu-id="6fa98-175">News</span></span>|<span data-ttu-id="6fa98-176">com.apple.news</span><span class="sxs-lookup"><span data-stu-id="6fa98-176">com.apple.news</span></span>|
|<span data-ttu-id="6fa98-177">注</span><span class="sxs-lookup"><span data-stu-id="6fa98-177">Notes</span></span>|<span data-ttu-id="6fa98-178">com.apple.mobilenotes</span><span class="sxs-lookup"><span data-stu-id="6fa98-178">com.apple.mobilenotes</span></span>|
|<span data-ttu-id="6fa98-179">数字</span><span class="sxs-lookup"><span data-stu-id="6fa98-179">Numbers</span></span>|<span data-ttu-id="6fa98-180">com.apple.Numbers</span><span class="sxs-lookup"><span data-stu-id="6fa98-180">com.apple.Numbers</span></span>|
|<span data-ttu-id="6fa98-181">ページ</span><span class="sxs-lookup"><span data-stu-id="6fa98-181">Pages</span></span>|<span data-ttu-id="6fa98-182">com.apple.Pages</span><span class="sxs-lookup"><span data-stu-id="6fa98-182">com.apple.Pages</span></span>|
|<span data-ttu-id="6fa98-183">Photo Booth</span><span class="sxs-lookup"><span data-stu-id="6fa98-183">Photo Booth</span></span>|<span data-ttu-id="6fa98-184">com.apple.Photo-Booth</span><span class="sxs-lookup"><span data-stu-id="6fa98-184">com.apple.Photo-Booth</span></span>|
|<span data-ttu-id="6fa98-185">写真</span><span class="sxs-lookup"><span data-stu-id="6fa98-185">Photos</span></span>|<span data-ttu-id="6fa98-186">com.apple.mobileslideshow</span><span class="sxs-lookup"><span data-stu-id="6fa98-186">com.apple.mobileslideshow</span></span>|
|<span data-ttu-id="6fa98-187">Podcast</span><span class="sxs-lookup"><span data-stu-id="6fa98-187">Podcasts</span></span>|<span data-ttu-id="6fa98-188">com.apple.podcasts</span><span class="sxs-lookup"><span data-stu-id="6fa98-188">com.apple.podcasts</span></span>|
|<span data-ttu-id="6fa98-189">リマインダー</span><span class="sxs-lookup"><span data-stu-id="6fa98-189">Reminders</span></span>|<span data-ttu-id="6fa98-190">com.apple.reminders</span><span class="sxs-lookup"><span data-stu-id="6fa98-190">com.apple.reminders</span></span>|
|<span data-ttu-id="6fa98-191">Safari</span><span class="sxs-lookup"><span data-stu-id="6fa98-191">Safari</span></span>|<span data-ttu-id="6fa98-192">com.apple.mobilesafari</span><span class="sxs-lookup"><span data-stu-id="6fa98-192">com.apple.mobilesafari</span></span>|
|<span data-ttu-id="6fa98-193">Settings</span><span class="sxs-lookup"><span data-stu-id="6fa98-193">Settings</span></span>|<span data-ttu-id="6fa98-194">com.apple.Preferences</span><span class="sxs-lookup"><span data-stu-id="6fa98-194">com.apple.Preferences</span></span>|
|<span data-ttu-id="6fa98-195">株価</span><span class="sxs-lookup"><span data-stu-id="6fa98-195">Stocks</span></span>|<span data-ttu-id="6fa98-196">com.apple.stocks</span><span class="sxs-lookup"><span data-stu-id="6fa98-196">com.apple.stocks</span></span>|
|<span data-ttu-id="6fa98-197">ヒント</span><span class="sxs-lookup"><span data-stu-id="6fa98-197">Tips</span></span>|<span data-ttu-id="6fa98-198">com.apple.tips</span><span class="sxs-lookup"><span data-stu-id="6fa98-198">com.apple.tips</span></span>|
|<span data-ttu-id="6fa98-199">ビデオ</span><span class="sxs-lookup"><span data-stu-id="6fa98-199">Videos</span></span>|<span data-ttu-id="6fa98-200">com.apple.videos</span><span class="sxs-lookup"><span data-stu-id="6fa98-200">com.apple.videos</span></span>|
|<span data-ttu-id="6fa98-201">VoiceMemos</span><span class="sxs-lookup"><span data-stu-id="6fa98-201">VoiceMemos</span></span>|<span data-ttu-id="6fa98-202">com.apple.VoiceMemos</span><span class="sxs-lookup"><span data-stu-id="6fa98-202">com.apple.VoiceMemos</span></span>|
|<span data-ttu-id="6fa98-203">Wallet</span><span class="sxs-lookup"><span data-stu-id="6fa98-203">Wallet</span></span>|<span data-ttu-id="6fa98-204">com.apple.Passbook</span><span class="sxs-lookup"><span data-stu-id="6fa98-204">com.apple.Passbook</span></span>|
|<span data-ttu-id="6fa98-205">視聴する</span><span class="sxs-lookup"><span data-stu-id="6fa98-205">Watch</span></span>|<span data-ttu-id="6fa98-206">com.apple.Bridge</span><span class="sxs-lookup"><span data-stu-id="6fa98-206">com.apple.Bridge</span></span>|
|<span data-ttu-id="6fa98-207">天気</span><span class="sxs-lookup"><span data-stu-id="6fa98-207">Weather</span></span>|<span data-ttu-id="6fa98-208">com.apple.weather</span><span class="sxs-lookup"><span data-stu-id="6fa98-208">com.apple.weather</span></span>|

## <a name="next-steps"></a><span data-ttu-id="6fa98-209">次の手順</span><span class="sxs-lookup"><span data-stu-id="6fa98-209">Next steps</span></span>

<span data-ttu-id="6fa98-210">選択したグループにデバイス プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6fa98-210">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="6fa98-211">詳しくは、「[デバイス プロファイルを割り当てる方法](device-profile-assign.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6fa98-211">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
