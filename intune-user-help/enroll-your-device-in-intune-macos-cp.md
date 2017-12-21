---
title: "ポータル サイトで Intune に macOS デバイスを登録する | Microsoft Docs"
description: "ポータル サイト アプリを利用し、Intune に macOS デバイスを登録する方法について説明します"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope: User help
ROBOTS: 
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 77c87d24834066c6ed58eaf004422490fcb81aa4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a><span data-ttu-id="c9deb-104">ポータル サイト アプリで Intune に macOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="c9deb-104">Enroll your macOS device in Intune with the Company Portal app</span></span>

<span data-ttu-id="c9deb-105">組織のアプリ、データ、リソースにアクセスできれば、業務の遂行が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="c9deb-105">Getting access to your organization’s apps, data, and resources makes it easier for you to do your job.</span></span> <span data-ttu-id="c9deb-106">組織は Intune を利用して[リソースへのアクセスを管理](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md)しています。そのために、macOS 向けポータル サイト アプリをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9deb-106">Your organization is using Intune to [manage access to those resources](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md), which requires you to download the Company Portal app for macOS.</span></span> <span data-ttu-id="c9deb-107">以下の指示は、OS X El Capitan 10.11 以降を搭載した macOS 向けです。</span><span class="sxs-lookup"><span data-stu-id="c9deb-107">These instructions will work for macOS devices on OS X El Capitan 10.11+.</span></span>

> [!NOTE]
> <span data-ttu-id="c9deb-108">以前のバージョンの macOS での macOS デバイスの登録手順については、[こちら](enroll-your-device-in-intune-macos-legacy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9deb-108">You can find instructions for enrolling macOS devices on previous versions of macOS [here](enroll-your-device-in-intune-macos-legacy.md).</span></span>

1. <span data-ttu-id="c9deb-109">__Dock__ で __Safari__ を起動し、新しいウィンドウを開いてから、[会社のポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)を開きます。</span><span class="sxs-lookup"><span data-stu-id="c9deb-109">On your __Dock__, find __Safari__ and open a new window, then open the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>

2. <span data-ttu-id="c9deb-110">職場や学校のアカウントで会社のポータル Web サイトにログインします。</span><span class="sxs-lookup"><span data-stu-id="c9deb-110">Log into the Company Portal website with your work or school account.</span></span>

[!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. <span data-ttu-id="c9deb-111">ログインした後、ページの左上隅の **[メニュー]** をクリックして、**[デバイス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="c9deb-111">After logging in, click on the **Menu** in the top left corner of the page and select **My Devices**.</span></span>

   ![アプリをまだインストールできないことと、下に [デバイス] ボタンが示されている Web ポータルのランディング ページのスクリーンショット。](./media/macOS_enroll_001_landing_page.png)

4. <span data-ttu-id="c9deb-113">__[デバイス]__ ページには、登録済みのデバイスのリスト、またはバナーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9deb-113">On the __My Devices__ page, you will either see a list of enrolled devices or simply a banner.</span></span> <span data-ttu-id="c9deb-114">デバイスが既に登録されている場合や macOS などの場合は表示内容が異なります。</span><span class="sxs-lookup"><span data-stu-id="c9deb-114">This depends on if you already have a device enrolled, macOS or otherwise.</span></span> <span data-ttu-id="c9deb-115">リストされていないデバイスを登録するには、[__If your device is listed, tap here to identify it.You can also tap here to enroll your device if it is not listed. (デバイスがリストに表示されている場合は、ここをタップして特定してください。リストに含まれていない場合は、ここをタップするとデバイスを登録できます)__] という内容のバナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9deb-115">To enroll a device that is not listed, select the banner that says __If your device is listed, tap here to identify it. You can also tap here to enroll your device if it is not listed__.</span></span> <span data-ttu-id="c9deb-116">登録済みデバイスがない場合は、バナーに **[登録されているデバイスはありません。ここをタップしてこのデバイスを登録してください。]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9deb-116">If you don't have any enrolled devices, the banner will read **You don't have any devices enrolled. Enroll this one by tapping here.**</span></span>

    ![リスト表示されていないデバイスの登録または不明なデバイスの識別を求めるバナーの上に 2 つの不明なデバイスが示された、[デバイス] ページのスクリーンショット。](./media/macOS_enroll_002_tap_here_banner.png)

5. <span data-ttu-id="c9deb-118">macOS デバイスにポータル サイト アプリをダウンロードして登録を続行します。</span><span class="sxs-lookup"><span data-stu-id="c9deb-118">Download the Company Portal app to your macOS device to continue enrolling.</span></span>

    ![ユーザーに macOS ポータル サイト アプリのダウンロードを求める通知。](./media/macOS_enroll_IWP_CP_app_notice.png)

6. <span data-ttu-id="c9deb-121">Mac で、ダウンロードした **CompanyPortal.pkg** が安全に開けることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="c9deb-121">Your Mac will check to make sure that the download of **CompanyPortal.pkg** is safe to open.</span></span> <span data-ttu-id="c9deb-122">インストーラーを開き、インストール プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="c9deb-122">Open the installer and go through the install process.</span></span>

7. <span data-ttu-id="c9deb-123">インストーラーが完了したら、**[アプリケーション]** フォルダーまたは**スタート パッド**を開き、**ポータル サイト**を開きます。</span><span class="sxs-lookup"><span data-stu-id="c9deb-123">When the installer has finished, open your **Applications** folder or the **Launchpad**, then open **Company Portal**.</span></span>

8. <span data-ttu-id="c9deb-124">**"CompanyPortal" がインターネットからダウンロードしたアプリケーションであることを伝え、これを開くかどうかを確認するメッセージ**が Mac に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9deb-124">Your Mac will show you a message that says, **"CompanyPortal" is an application downloaded from the Internet. Are you sure you want to open it?**</span></span> <span data-ttu-id="c9deb-125">**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9deb-125">Click **Open**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c9deb-126">Intune は、ユーザーのコンピューターにアクセスして、そのデバイスが組織のリソースにアクセスしても十分に安全であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9deb-126">Intune needs access to your computer to make sure that your device is secure enough to access your organization's resources.</span></span> <span data-ttu-id="c9deb-127">ポータル サイト アプリの起動をコンピューターが拒否した場合、[Gatekeeper をオフに](https://support.apple.com/HT202491)してからアプリを開いてみてください。</span><span class="sxs-lookup"><span data-stu-id="c9deb-127">If your computer refuses to open the Company Portal app, try [turning off Gatekeeper](https://support.apple.com/HT202491) and then opening the app.</span></span>

9. <span data-ttu-id="c9deb-128">ポータル サイト アプリの最初の画面で、ポータル Web サイトへのログインに使用したものと同じ職場または学校のアカウントで**サインイン**するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c9deb-128">The first screen you see in the Company Portal app prompts you to **Sign In** with the same work or school account you used to log in to the Company Portal website.</span></span>

10. <span data-ttu-id="c9deb-129">ポータル サイトはアカウント情報を確認し、**デバイス登録**状況と**デバイス コンプライアンス**状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9deb-129">The Company Portal confirms your account information, then shows you your **Device Enrollment** and **Device Compliance** statuses.</span></span> <span data-ttu-id="c9deb-130">黄色の三角形が表示されますが、これは Mac を職場で使用しても問題がないことを確認するために行わなければならない措置を伝えるものです。</span><span class="sxs-lookup"><span data-stu-id="c9deb-130">There will be yellow triangles letting you know that you have actions you'll need to take to make sure your Mac is safe for use at work.</span></span> <span data-ttu-id="c9deb-131">**[開始]** をクリックし、[デバイスを管理登録](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)します。</span><span class="sxs-lookup"><span data-stu-id="c9deb-131">Click **Begin** to start [enrolling your device into management](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).</span></span>

11. <span data-ttu-id="c9deb-132">Mac は管理登録を開始します。</span><span class="sxs-lookup"><span data-stu-id="c9deb-132">Your Mac will begin enrolling into management.</span></span> <span data-ttu-id="c9deb-133">この間、コンピューターのログイン情報を求められることがあります。</span><span class="sxs-lookup"><span data-stu-id="c9deb-133">You might be prompted to provide your computer's login information during this time.</span></span> <span data-ttu-id="c9deb-134">登録には数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9deb-134">This may take a few minutes to enroll.</span></span> <span data-ttu-id="c9deb-135">この間、コンピューターで他の作業を行っても構いません。</span><span class="sxs-lookup"><span data-stu-id="c9deb-135">During this time, you can do other things on your computer.</span></span> <span data-ttu-id="c9deb-136">会社アクセス設定が完了すると、完了を知らせるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9deb-136">A message appears once you've completed Company Access Setup to let you know you're done.</span></span>

<span data-ttu-id="c9deb-137">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="c9deb-137">Still need help?</span></span> <span data-ttu-id="c9deb-138">会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c9deb-138">Check in with your company support.</span></span> <span data-ttu-id="c9deb-139">連絡先の情報は、[会社のポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)でわかります。</span><span class="sxs-lookup"><span data-stu-id="c9deb-139">You can find their contact information on the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
