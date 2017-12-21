---
title: "Intune にレガシ macOS デバイスを登録する | Microsoft Docs"
description: "Intune に macOS デバイスを登録する方法について説明します"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope: User help
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: f46d9cc4fad54415aeea8deaf1b8daa0c274c1dc
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-your-legacy-macos-device-in-intune"></a><span data-ttu-id="0fd55-104">Intune にレガシ macOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="0fd55-104">Enroll your legacy macOS device in Intune</span></span>

<span data-ttu-id="0fd55-105">以下の手順は、OS X Yosemite 10.10 以前の macOS デバイス向けです。</span><span class="sxs-lookup"><span data-stu-id="0fd55-105">These instructions will work for macOS devices on OS X Yosemite 10.10 and previous.</span></span> <span data-ttu-id="0fd55-106">新しいバージョンの macOS での macOS デバイスの登録手順については、[こちら](enroll-your-device-in-intune-macos-cp.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fd55-106">You can find instructions for enrolling macOS devices on newer versions of macOS [here](enroll-your-device-in-intune-macos-cp.md).</span></span>

<span data-ttu-id="0fd55-107">組織のアプリ、データ、リソースにアクセスできれば、業務を遂行することができます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-107">Getting access to your organization’s apps, data, and resources makes it possible for you to do your job.</span></span> <span data-ttu-id="0fd55-108">仕事に macOS デバイスを使用している場合、そのためには__管理プロファイル__をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fd55-108">If you're using a macOS device at work, this means installing a __Management Profile__.</span></span> <span data-ttu-id="0fd55-109">管理プロファイルは会社のサポートによってセットアップされるファイルにすぎず、設定とアクセス情報を Mac に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-109">This is simply a file set up by your company support that loads settings and access information onto your Mac.</span></span> <span data-ttu-id="0fd55-110">詳細については、</span><span class="sxs-lookup"><span data-stu-id="0fd55-110">Want to know more?</span></span> <span data-ttu-id="0fd55-111">[ポータル サイト アプリをインストールし、Intune にデバイスを登録するとどうなるか](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0fd55-111">Find out [what happens when you install the Company Portal app and enroll your device in Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)</span></span>

1. <span data-ttu-id="0fd55-112">__Dock__ で __Safari__ を起動し、新しいウィンドウを開いてから、[会社のポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)を開きます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-112">On your __Dock__, find __Safari__ and open a new window, then open the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
2. <span data-ttu-id="0fd55-113">職場や学校のアカウントで会社のポータル Web サイトにログインします。</span><span class="sxs-lookup"><span data-stu-id="0fd55-113">Log into the Company Portal website with your work or school account.</span></span>

  [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. <span data-ttu-id="0fd55-114">ログインした後、ページの左上隅の **[メニュー]** をクリックして、**[デバイス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-114">After logging in, click on the **Menu** in the top left corner of the page and select **My Devices**.</span></span>

 ![アプリをまだインストールできないことと、下に [デバイス] ボタンが示されている Web ポータルのランディング ページのスクリーンショット。](./media/macOS_enroll_001_landing_page.png)

4. <span data-ttu-id="0fd55-116">__[デバイス]__ ページには、登録済みのデバイスのリスト、またはバナーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-116">On the __My Devices__ page, you will either see a list of enrolled devices or simply a banner.</span></span> <span data-ttu-id="0fd55-117">デバイスが既に登録されている場合や macOS などの場合は表示内容が異なります。</span><span class="sxs-lookup"><span data-stu-id="0fd55-117">This depends on if you already have a device enrolled, macOS or otherwise.</span></span> <span data-ttu-id="0fd55-118">リストされていないデバイスを登録するには、[__If your device is listed, tap here to identify it.You can also tap here to enroll your device if it is not listed. (デバイスがリストに表示されている場合は、ここをタップして特定してください。リストに含まれていない場合は、ここをタップするとデバイスを登録できます)__] という内容のバナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0fd55-118">To enroll a device that is not listed, select the banner that says __If your device is listed, tap here to identify it. You can also tap here to enroll your device if it is not listed__.</span></span> <span data-ttu-id="0fd55-119">登録済みデバイスがない場合は、バナーに **[登録されているデバイスはありません。ここをタップしてこのデバイスを登録してください。]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-119">If you don't have any enrolled devices, the banner will read **You don't have any devices enrolled. Enroll this one by tapping here.**</span></span>

  ![リスト表示されていないデバイスの登録または不明なデバイスの識別を求めるバナーの上に 2 つの不明なデバイスが示された、[デバイス] ページのスクリーンショット。](./media/macOS_enroll_002_tap_here_banner.png)

5. <span data-ttu-id="0fd55-121">__このデバイスを特定または登録する__理由についての簡単な説明がポップアップ ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-121">A popup window will appear with a brief explanation of why you are going to __Identify or enroll this device__.</span></span> <span data-ttu-id="0fd55-122">それを確認した後、__[登録]__ をクリックして続けます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-122">Review this, then click __Enroll__ to proceed.</span></span>

 ![このデバイスの macOS の特定または登録](./media/macOS_enroll_003_IDenroll_popup.png)

6. <span data-ttu-id="0fd55-124">別のポップアップ ウィンドウが開き、__このデバイスを登録__した場合についての簡単な説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-124">A second popup window will appear with a brief explanation of what will happen when you __Enroll this device__.</span></span> <span data-ttu-id="0fd55-125">それを確認した後、__[インストール]__ をクリックして続けます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-125">Review this, then click __Install__ to proceed.</span></span>

 ![このデバイスの macOS を登録する](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > <span data-ttu-id="0fd55-127">Intune は、ユーザーのコンピューターにアクセスして、そのデバイスが組織のリソースにアクセスしても十分に安全であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fd55-127">Intune needs access to your computer to make sure that your device is secure enough to access your organization's resources.</span></span> <span data-ttu-id="0fd55-128">「[ポータル サイト アプリをインストールし、Intune に iOS または Mac OS X デバイスを登録するとどうなりますか](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0fd55-128">Find out [what happens when you enroll your device in Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).</span></span>

7. <span data-ttu-id="0fd55-129">__[システム環境設定]__ が開き、__"管理プロファイル" をインストール__するかどうかの確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-129">__System Preferences__ will open, and ask you if you want to __Install "Management Profile"?__</span></span> <span data-ttu-id="0fd55-130">__[インストール]__ をクリックして続行するか、__[プロファイルの表示]__ をクリックして詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="0fd55-130">Click __Install__ to proceed, or get more details by clicking __Show Profile__.</span></span>

 ![管理プロファイルをインストールする](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. <span data-ttu-id="0fd55-132">macOS のポップアップ ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-132">A macOS popup window will appear.</span></span> <span data-ttu-id="0fd55-133">使用するコンピューターの __[ユーザー名]__ と __[パスワード]__ を入力して __[OK]__ をクリックし、変更を行うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0fd55-133">Confirm that you want to make changes by providing your computer's __User Name__ and __Password__, then clicking __OK__.</span></span> <span data-ttu-id="0fd55-134">これにより、管理プロファイルが Mac にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-134">This will install the management profile onto your Mac.</span></span>

 ![macOS のプロファイル インストール ポップアップ](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. <span data-ttu-id="0fd55-136">プロファイルの詳細または__インストール__の確認についての追加メッセージが Mac から表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0fd55-136">You may see some additional messages from your Mac with more details about the profile, or whether you're sure that you want to __Install__.</span></span> <span data-ttu-id="0fd55-137">__[続行]__ および __[インストール]__ をクリックして処理を続けます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-137">Click __Continue__ and __Install__ through these to proceed.</span></span> <span data-ttu-id="0fd55-138">インストールが終了すると、新しくインストールした__管理プロファイル__を __[デバイス プロファイル]__ の一覧で確認できます。</span><span class="sxs-lookup"><span data-stu-id="0fd55-138">Once the installation finishes, you will be able to view your newly-installed __Management Profile__ in the list of __Device Profiles__.</span></span>

 ![インストールされた macOS プロファイル](./media/macOS_enroll_007_sysprefs_installed_profile.png)

<span data-ttu-id="0fd55-140">一部のプロファイルが**未確認**と表示されることがあります。プロファイルが会社提供のものである場合、これは正常です。</span><span class="sxs-lookup"><span data-stu-id="0fd55-140">Some profiles may say that they're **Unverified**; as long as they're from your company, this is normal.</span></span>

<span data-ttu-id="0fd55-141">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="0fd55-141">Still need help?</span></span> <span data-ttu-id="0fd55-142">会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="0fd55-142">Check in with your company support.</span></span> <span data-ttu-id="0fd55-143">連絡先の情報は、[会社のポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)でわかります。</span><span class="sxs-lookup"><span data-stu-id="0fd55-143">You can find their contact information on the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
