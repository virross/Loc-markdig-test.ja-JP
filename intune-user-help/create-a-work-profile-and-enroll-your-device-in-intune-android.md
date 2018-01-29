---
title: "仕事用プロファイルを使用するデバイスの登録 | Microsoft Docs"
description: "仕事用プロファイルを使用して Android デバイスの安全性を高める方法。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 33ffff16-0280-43bf-87b3-74ddf4439bfa
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 03d413784fc004f13953a740745a95ae91c8c445
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="create-a-work-profile-and-enroll-your-device-in-intune"></a><span data-ttu-id="24502-103">Intune での仕事用プロファイルの作成とデバイスの登録</span><span class="sxs-lookup"><span data-stu-id="24502-103">Create a work profile and enroll your device in Intune</span></span>

<span data-ttu-id="24502-104">自分の Android デバイスを登録すると、会社のメール、アプリ、その他の作業データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="24502-104">Enrolling your Android device gives you access to company email, apps, and other work data.</span></span> <span data-ttu-id="24502-105">登録の一環として、仕事用のプロファイルを設定します。これはデバイス上の個人データと仕事のデータを分けるものです。</span><span class="sxs-lookup"><span data-stu-id="24502-105">As part of enrollment, you set up a work profile, which separates the personal data on your device from your work data.</span></span>

<span data-ttu-id="24502-106">会社のサポートは、仕事のデータが含まれる仕事用のプロファイルのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="24502-106">Your company support can manage only the work profile, which contains your work data.</span></span> <span data-ttu-id="24502-107">会社のサポートは、デバイス上の個人情報を管理できません。</span><span class="sxs-lookup"><span data-stu-id="24502-107">Your company support cannot manage the personal data on your device.</span></span> <span data-ttu-id="24502-108">詳細については、「[仕事用プロファイルを作成するとどうなりますか](what-happens-when-you-create-a-work-profile-android.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24502-108">Find out more about [what happens when you create a work profile](what-happens-when-you-create-a-work-profile-android.md).</span></span>

<span data-ttu-id="24502-109">仕事用プロファイルを作成するには:</span><span class="sxs-lookup"><span data-stu-id="24502-109">To create a work profile:</span></span>

1.  <span data-ttu-id="24502-110">Android ポータル サイトの **[ようこそ]** 画面で、**[サインイン]** をタップし、職場または学校アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="24502-110">On the Android Company Portal **Welcome** screen, tap **Sign in**, and then sign in with your work or school account.</span></span> <span data-ttu-id="24502-111">この無料アプリをまだインストールしていない場合は、[Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) からダウンロードし、インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="24502-111">If you haven't installed the free app yet, download and install it from [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).</span></span>

    ![Android ポータル サイト アプリの [ようこそ] 画面](./media/and-enroll-0-welcome-screen.png)

2. <span data-ttu-id="24502-113">**[会社アクセスのセットアップ]** 画面で、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="24502-113">On the **Company Access Setup** screen, tap **CONTINUE**.</span></span>

    ![[会社アクセスのセットアップ] 画面](/intune/media/android_cp_enroll_01_1709_new.png)

3.  <span data-ttu-id="24502-115">**[Why create a work profile?]** (仕事用プロファイルを作成する理由) 画面で機能を確認し、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="24502-115">On the **Why create a work profile?** screen, read about what you'll be able to do, and then tap **CONTINUE**.</span></span>

    ![仕事用プロファイルを作成する理由](./media/andr-afw-why-create-a-work-profile.png)

4.  <span data-ttu-id="24502-117">会社のサポートがユーザーのデバイスに関して確認できる情報と確認できない情報について確認し、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="24502-117">Review a list of what your company support can and can't see on your device, and tap **CONTINUE**.</span></span>

    ![会社のサポートがデバイスに関して確認できる情報と確認できない情報](/intune/media/android_cp_enroll_02_after_1710.png)

5.  <span data-ttu-id="24502-119">**[What's next?]\(次のステップ\)** 画面で、登録中に行う内容を確認し、**[登録]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="24502-119">On the **What's next?** screen, read about what happens during enrollment, and then tap **ENROLL**.</span></span>

    ![[次のステップ] 画面](/intune/media/android_work_cp_enroll_03_after_1710.png)

6. <span data-ttu-id="24502-121">**[Set up work profile]** (仕事用プロファイルのセットアップ) 画面で **[次へ]** をタップして、ポータル サイト アプリから仕事用プロファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="24502-121">On the **Set up work profile** screen, tap **NEXT** to let the Company Portal app access the work profile.</span></span>

    ![仕事用プロファイルに対するアクセス権をポータル サイト アプリに付与する](./media/andr-afw-tap-next-to-set-up-work-profile.png)

7. <span data-ttu-id="24502-123">仕事用プロファイルの作成時に会社のサポートができることを説明する Google 画面を確認し、**[OK]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="24502-123">Review the Google screen that describes what your company support can do when you create a work profile, and then tap **OK**.</span></span>

    ![仕事用プロファイルに関する Google の情報を確認する](./media/andr-afw-google-screen-what-it-can-do.png)

    <span data-ttu-id="24502-125">"仕事用プロファイルのセットアップ" と "デバイスの登録" に関するメッセージがいくつか表示されます。</span><span class="sxs-lookup"><span data-stu-id="24502-125">You'll see a couple of messages that say "Setting up your work profile" and "Enrolling your device."</span></span>

8. <span data-ttu-id="24502-126">**[まだ途中です]** の</span><span class="sxs-lookup"><span data-stu-id="24502-126">On the **You're Halfway There!**</span></span> <span data-ttu-id="24502-127">画面で数秒待つと、ポータル サイト アプリが開きます。</span><span class="sxs-lookup"><span data-stu-id="24502-127">screen, wait a few seconds until the Company Portal app opens.</span></span>

    ![バッジが付いたポータル サイト アプリをタップする](./media/andr-afw-tap-work-badged-company-portal-icon2.png)

9. <span data-ttu-id="24502-129">Android ポータル サイトの **[ようこそ]** 画面で、**[サインイン]** をタップし、このプロセスの最初の段階で利用した、職場または学校アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="24502-129">On the Android Company Portal **Welcome** screen, tap **Sign in**, and then sign in with the same work or school account that you used to sign in earlier in this process.</span></span>

10. <span data-ttu-id="24502-130">**[会社アクセスのセットアップ]** 画面で仕事用プロファイルのセットアップが完了したことを確認し、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="24502-130">On the **Company Access Setup** screen, note that your Work Profile Setup is now complete, and then tap **CONTINUE**.</span></span>

    ![仕事用プロファイルが完了したことが表示されている [会社アクセスのセットアップ]](./media/andr-afw-work-profile-now-set-up.png)

    <span data-ttu-id="24502-132">"デバイスを登録しています" というメッセージが短時間表示されます。</span><span class="sxs-lookup"><span data-stu-id="24502-132">You'll briefly see the message "Enrolling your device."</span></span>

11. <span data-ttu-id="24502-133">**[準備が完了しました]** 画面に、</span><span class="sxs-lookup"><span data-stu-id="24502-133">When the **You're all set!**</span></span> <span data-ttu-id="24502-134">すべてのセットアップが正常に完了したことが表示されたら、**[完了]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="24502-134">screen shows that everything has been set up correctly, tap **DONE**.</span></span>

    ![仕事用プロファイルと登録が完了したことが表示されている [会社アクセスのセットアップ]](/intune/media/android_work_cp_enroll_04_after_1710.png)

    <span data-ttu-id="24502-136">これで Play Store for Work から会社のアプリを入手できます。</span><span class="sxs-lookup"><span data-stu-id="24502-136">You can now get company apps from the Play Store for Work.</span></span>

    ![Play Store for Work アプリ ページ](./media/andr-afw-tap-work-play-store-icon.png)

<span data-ttu-id="24502-138">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="24502-138">Still need help?</span></span> <span data-ttu-id="24502-139">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="24502-139">Contact your company support.</span></span> <span data-ttu-id="24502-140">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="24502-140">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
