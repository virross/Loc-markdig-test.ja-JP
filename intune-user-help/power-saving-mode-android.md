---
title: "電力の最適化が電子メール アクセスを妨げる |Microsoft ドキュメント"
description: "Android で電子メールを受け取るために電力の最適化をオフにする方法について説明します。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57c
searchScope: User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 9564ad8700e88e33e6eba806037c743caf455158
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="outlook-wont-sync-managed-email-when-battery-optimization-for-android-is-turned-on"></a><span data-ttu-id="fbced-103">Android のバッテリー最適化が有効になっていると Outlook が管理対象電子メールを同期しない</span><span class="sxs-lookup"><span data-stu-id="fbced-103">Outlook won't sync managed email when battery optimization for Android is turned on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fbced-104">ユーザーからの報告件数が増えているため、この問題についてここで説明します。</span><span class="sxs-lookup"><span data-stu-id="fbced-104">This issue is documented here because we have been receiving an increased number of customer reports about it.</span></span> <span data-ttu-id="fbced-105">ここで説明する手順を実行してもこの問題が発生する場合は、[会社のサポート](https://portal.manage.microsoft.com#HelpDeskDialog)にさらに支援を依頼してください。</span><span class="sxs-lookup"><span data-stu-id="fbced-105">If you continue to experience this issue after you have taken these steps, contact [your company support](https://portal.manage.microsoft.com#HelpDeskDialog) for additional help.</span></span>

<span data-ttu-id="fbced-106">Intune にデバイスを登録すると、会社のリソースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="fbced-106">Enrolling your device in Intune lets you get access to company resources.</span></span> <span data-ttu-id="fbced-107">最も一般的なリソースの 1 つはメール アクセスです。</span><span class="sxs-lookup"><span data-stu-id="fbced-107">One of the most common resources is email access.</span></span> <span data-ttu-id="fbced-108">Android デバイス用 Outlook によるメール アクセスでの問題は、バッテリー最適化を有効にすると発生します。</span><span class="sxs-lookup"><span data-stu-id="fbced-108">An issue that we have seen with accessing email through Outlook for Android devices has been when battery optimization is turned on.</span></span> <span data-ttu-id="fbced-109">デバイスのバッテリーをできるだけ長く持たせるため、バッテリー最適化が自動的に有効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbced-109">Battery optimization may turn on automatically to try to help your device stay powered on for as long as possible.</span></span> <span data-ttu-id="fbced-110">バッテリー最適化は、メールの自動ダウンロードの停止を試みるため、バッテリーの維持に部分的には効果があります。</span><span class="sxs-lookup"><span data-stu-id="fbced-110">Battery optimization is partially able to help you this way because it tries to stop automatic email downloads.</span></span>

<span data-ttu-id="fbced-111">Microsoft Intune チームはこの問題の解決に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="fbced-111">The Microsoft Intune team is actively working on a solution for this issue.</span></span> <span data-ttu-id="fbced-112">デバイスが省電力モードになるのを防ぐ方法の 1 つは、バッテリーの残量を 30% より高く維持することです。</span><span class="sxs-lookup"><span data-stu-id="fbced-112">One way to prevent the device from entering low power mode is by making sure the battery maintains a charge of greater than 30%.</span></span> <span data-ttu-id="fbced-113">省電力モードになったときに問題が発生しないようにするには、バッテリーの最適化と省電力設定の影響を受けるアプリの一覧からポータル サイトと Outlook を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbced-113">To stop the issue from happening when you enter low power mode, you must remove the Company Portal and Outlook from the list of apps that are affected by battery optimization and power saving settings.</span></span>

<span data-ttu-id="fbced-114">多くの製造元によって多くの Android デバイスが製造されています。</span><span class="sxs-lookup"><span data-stu-id="fbced-114">There are many Android devices that are made by many manufacturers.</span></span> <span data-ttu-id="fbced-115">すべてのデバイスについて、必要な手順を正確に記すことはできません。</span><span class="sxs-lookup"><span data-stu-id="fbced-115">We cannot document the exact steps you need to take for every device.</span></span> <span data-ttu-id="fbced-116">この操作は、システム設定だけで済むことも、特定の製造元に固有の設定も必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="fbced-116">You may need to take this action in just your system settings or also in certain manufacturer-specific settings.</span></span> <span data-ttu-id="fbced-117">Android デバイスでこの問題を解決できる方法の一般的な例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="fbced-117">We have provided some common examples of how you can resolve this issue on Android devices.</span></span>

## <a name="unmodified-android-devices"></a><span data-ttu-id="fbced-118">変更されていない Android デバイス</span><span class="sxs-lookup"><span data-stu-id="fbced-118">Unmodified Android devices</span></span>

<span data-ttu-id="fbced-119">多くの製造元は、Android デバイスに変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="fbced-119">Many manufacturers add modifications to their Android devices.</span></span> <span data-ttu-id="fbced-120">これにより、テーマや通知など、デバイスと対話する特定の方法が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbced-120">This can change certain ways you interact with the device, like themes and notifications.</span></span> <span data-ttu-id="fbced-121">Google は、通常、この種の変更を携帯電話に対して行うことはありません。</span><span class="sxs-lookup"><span data-stu-id="fbced-121">Google generally does not make these types of modifications to their phones.</span></span> <span data-ttu-id="fbced-122">たとえば、Android 7.0 以降を搭載した Google Pixel デバイスでは、以下の手順でバッテリー最適化からこれらのアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="fbced-122">For example, on a Google Pixel device with Android 7.0 or higher, you would follow these steps to remove these apps from battery optimization:</span></span>

1. <span data-ttu-id="fbced-123">**[設定]**を開きます。</span><span class="sxs-lookup"><span data-stu-id="fbced-123">Open **Settings**.</span></span>
2. <span data-ttu-id="fbced-124">**[Battery\(バッテリー\)]** > **[More\(詳細\)]** > **[Battery optimization\(バッテリーの最適化\)]** の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="fbced-124">Tap **Battery** > **More** > **Battery optimization**.</span></span>
3. <span data-ttu-id="fbced-125">下向きの矢印をタップし、**[Not optimized\(最適化しない\)]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="fbced-125">Tap the down arrow, then **Not optimized**.</span></span>
4. <span data-ttu-id="fbced-126">ポータル サイト アプリと Outlook アプリを選び、バッテリーの最適化をオフにします。</span><span class="sxs-lookup"><span data-stu-id="fbced-126">Select the Company Portal and Outlook apps, and turn off battery optimization.</span></span>

## <a name="samsung-devices"></a><span data-ttu-id="fbced-127">Samsung デバイス</span><span class="sxs-lookup"><span data-stu-id="fbced-127">Samsung devices</span></span>

<span data-ttu-id="fbced-128">Android 7.0 以降を搭載した Samsung デバイスなどの他のタイプの Android デバイスでは、Outlook アプリとポータル サイト アプリをバッテリー最適化から削除する手順が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbced-128">For other types of Android devices, such as Samsung devices with Android 7.0 or higher, you would have to follow different steps to remove the Outlook and Company Portal apps from battery optimization.</span></span>

1. <span data-ttu-id="fbced-129">**[設定]**を開きます。</span><span class="sxs-lookup"><span data-stu-id="fbced-129">Open **Settings**.</span></span>
2. <span data-ttu-id="fbced-130">**[Menu (…)\(メニュー (...)\)]** > **[Special access\(特殊なアクセス\)]** > **[Optimize battery usage\(バッテリー使用の最適化\)]** の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="fbced-130">Tap **Menu (…)** > **Special access** > **Optimize battery usage**.</span></span>
3. <span data-ttu-id="fbced-131">ドロップダウンから **[All apps\(すべてのアプリ\)]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="fbced-131">Select **All apps** from the dropdown.</span></span>
4. <span data-ttu-id="fbced-132">ポータル サイト アプリと Outlook アプリの隣のトグルを **[オフ]** にして、バッテリーの最適化をオフにします。</span><span class="sxs-lookup"><span data-stu-id="fbced-132">Turn **Off** the toggle next to the Company Portal and Outlook apps to turn off battery optimization.</span></span>

<span data-ttu-id="fbced-133">さらに、古いバージョンの Android を搭載した Samsung デバイスを使っている場合は、以下の手順で省電力モードからこれらのアプリを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbced-133">In addition, if you are using a Samsung device that has a lower version of Android, you would need to follow these steps to remove these apps from power saving mode.</span></span>

1. <span data-ttu-id="fbced-134">**[設定]**を開きます。</span><span class="sxs-lookup"><span data-stu-id="fbced-134">Open **Settings**.</span></span>
2. <span data-ttu-id="fbced-135">**[Device maintenance\(デバイスの保守\)]** > **[Battery\(バッテリー\)]** > **[Unmonitored apps\(監視しないアプリ\)]** の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="fbced-135">Tap **Device maintenance** > **Battery** > **Unmonitored apps**.</span></span>
3. <span data-ttu-id="fbced-136">**[Add apps\(アプリの追加\)]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="fbced-136">Tap **Add apps**.</span></span>
4. <span data-ttu-id="fbced-137">ポータル サイト アプリと Outlook アプリを選び、**[Done\(完了\)]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="fbced-137">Select the Company Portal and Outlook apps, and tap **Done**.</span></span>

## <a name="oneplus-devices"></a><span data-ttu-id="fbced-138">OnePlus デバイス</span><span class="sxs-lookup"><span data-stu-id="fbced-138">OnePlus devices</span></span>

<span data-ttu-id="fbced-139">これらの設定を探す方法のもう 1 つの例は、システム設定を検索することです。</span><span class="sxs-lookup"><span data-stu-id="fbced-139">Another example of a different way to locate these settings is through searching in the system settings.</span></span> <span data-ttu-id="fbced-140">たとえば、Android 7.1.1 を搭載した OnePlus 3 では次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fbced-140">For example, on a OnePlus 3 with Android 7.1.1, you would follow these steps:</span></span> 

1. <span data-ttu-id="fbced-141">**[System Settings\(システム設定\)]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="fbced-141">Open **System Settings**.</span></span> 
2. <span data-ttu-id="fbced-142">**[検索]** ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="fbced-142">Tap the **Search** button.</span></span> <span data-ttu-id="fbced-143">画面の右上にある虫眼鏡のようなボタンです。</span><span class="sxs-lookup"><span data-stu-id="fbced-143">This looks like a magnifying glass at the top right of the screen.</span></span> 
3. <span data-ttu-id="fbced-144">検索に「**battery optimization\(バッテリーの最適化\)**」と入力し、表示される **[設定]** 画面で **[Battery Optimization\(バッテリーの最適化\)]** オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="fbced-144">Type **battery optimization** into search, then select the **Battery Optimization** option on the **Settings** screen that appears.</span></span> 
4. <span data-ttu-id="fbced-145">**[Battery\(バッテリー\)]** > **[Battery optimization\(バッテリーの最適化\)]** の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="fbced-145">Tap **Battery** > **Battery optimization**.</span></span>
5. <span data-ttu-id="fbced-146">ポータル サイト アプリと Outlook アプリを選び、**[Don't optimize\(最適化しない\)]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="fbced-146">Select the Company Portal and Outlook apps, then select **Don't optimize**.</span></span> <span data-ttu-id="fbced-147">**[完了]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="fbced-147">Tap **Done**.</span></span>

<!--On a OnePlus 5 device with Android 7.1.1, you would follow these steps to remove these apps from battery optimization:
1. Open **Settings**.
2. Tap **Battery** > **Battery optimization**.
3. Select the Company Portal and Outlook apps, then select **Don’t optimize**. Tap **Done**.-->

<span data-ttu-id="fbced-148">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="fbced-148">Still need help?</span></span> <span data-ttu-id="fbced-149">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="fbced-149">Contact your company support.</span></span> <span data-ttu-id="fbced-150">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="fbced-150">For their contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
