---
title: "Windows デバイスを手動で同期する | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1c1ade50ff6a458633598d2788d176dd79cbfebd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="sync-your-windows-device-manually"></a><span data-ttu-id="688a2-102">Windows デバイスを手動で同期する</span><span class="sxs-lookup"><span data-stu-id="688a2-102">Sync your Windows device manually</span></span>

<span data-ttu-id="688a2-103">Windows デバイスにアプリをインストールしようとしたとき、予想より長くかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="688a2-103">Sometimes trying to install an app on your Windows device may take longer than you think it should.</span></span> <span data-ttu-id="688a2-104">その場合は、手動で Windows デバイスの同期を試みることができます。</span><span class="sxs-lookup"><span data-stu-id="688a2-104">If this happens, you can try to manually sync your Windows device.</span></span> <span data-ttu-id="688a2-105">同期すると、インストールが速くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="688a2-105">Syncing may help speed up the installation.</span></span>

> [!Note]
> <span data-ttu-id="688a2-106">低速のネットワークを使っている場合、または同時に多数のデバイスにコンテンツをダウンロードする場合は、アプリのインストールに少し時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="688a2-106">Apps could take awhile to install if you are on a network with slower speeds or higher amounts of devices downloading content at the same time.</span></span>

<span data-ttu-id="688a2-107">次のバージョンの Windows は手動で同期できます。</span><span class="sxs-lookup"><span data-stu-id="688a2-107">The following versions of Windows can sync manually.</span></span> <span data-ttu-id="688a2-108">残念ながら、他のバージョンの Windows をデバイスが使っている場合は、手動同期を開始できません。</span><span class="sxs-lookup"><span data-stu-id="688a2-108">Unfortunately, if your device is using a different version of Windows, you can't start a manual sync.</span></span>

* [<span data-ttu-id="688a2-109">Windows 10 Desktop を同期する</span><span class="sxs-lookup"><span data-stu-id="688a2-109">Sync Windows 10 desktop</span></span>](#windows-10-desktop)
* [<span data-ttu-id="688a2-110">Windows 10 Mobile を同期する</span><span class="sxs-lookup"><span data-stu-id="688a2-110">Sync Windows 10 Mobile</span></span>](#windows-10-mobile)
* [<span data-ttu-id="688a2-111">Windows Phone 8.1 を同期する</span><span class="sxs-lookup"><span data-stu-id="688a2-111">Sync Windows Phone 8.1</span></span>](#windows-phone-81)

## <a name="windows-10-desktop"></a><span data-ttu-id="688a2-112">Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="688a2-112">Windows 10 desktop</span></span>
<span data-ttu-id="688a2-113">Windows 10 には複数のバージョンがあるため、2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="688a2-113">There is more than one version of Windows 10, so there are two sets of steps.</span></span> <span data-ttu-id="688a2-114">スクリーンショットを確認し、お使いのデバイスの表示画面に近い方の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="688a2-114">To figure out which steps to use, look at the screenshots, and then follow the steps that look like what you see on your device.</span></span>

1. <span data-ttu-id="688a2-115">**[スタート]** ボタンを選択し、**[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-115">Choose the **Start** button, and then choose **Settings**.</span></span>

    ![[スタート] ボタン](./media/win10pc-sync-1-start-button.png)

2. <span data-ttu-id="688a2-117">**[設定]** ページで、**[アカウント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="688a2-117">On the **Settings** page, choose **Accounts**.</span></span>

    ![[設定] ページの [アカウント] の選択](./media/win10pc-sync-2-settings-accounts.png)

3. <span data-ttu-id="688a2-119">次の 2 つの画面を見て、お使いのデバイスの表示画面に似ている方をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="688a2-119">Look at the next two screens, and find the one that looks like the one you see on your device.</span></span> <span data-ttu-id="688a2-120">お使いのデバイスの表示画面に対応する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="688a2-120">Follow the steps that go with the screen that you see on your device.</span></span>

    <span data-ttu-id="688a2-121">[職場または学校にアクセスする] の画面が表示されている場合は、「[[職場または学校にアクセスする] が表示されている場合の手順](#steps-to-follow-if-you-see-access-work-or-school)」にある指示に従います。</span><span class="sxs-lookup"><span data-stu-id="688a2-121">If you see this screen, which shows "Access work or school," follow the instructions in [Steps to follow if you see Access work or school](#steps-to-follow-if-you-see-access-work-or-school).</span></span>

    ![[職場または学校にアクセスする] が表示されている場合の同期手順](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    <span data-ttu-id="688a2-123">[職場のアクセス] の画面が表示されている場合は、「[[職場のアクセス] が表示されている場合の手順](#steps-to-follow-if-you-see-work-access)」にある指示に従います。</span><span class="sxs-lookup"><span data-stu-id="688a2-123">If you see this screen, which shows "Work access," follow the steps in [Steps to follow if you see Work access](#steps-to-follow-if-you-see-work-access).</span></span>

    ![アカウントの種類として職場のアクセスを選択する](./media/win10pc-sync-3-work-access.png)

### <a name="steps-to-follow-if-you-see-access-work-or-school"></a><span data-ttu-id="688a2-125">[職場または学校にアクセスする] が表示されている場合の手順</span><span class="sxs-lookup"><span data-stu-id="688a2-125">Steps to follow if you see Access work or school</span></span>

1. <span data-ttu-id="688a2-126">**[アカウント]** ページで、**[職場または学校にアクセスする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-126">On the **Accounts** page, choose **Access work or school**.</span></span>

    ![[職場または学校にアクセスする] を選択する](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. <span data-ttu-id="688a2-128">職場または学校のアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-128">Choose your work or school account.</span></span> <span data-ttu-id="688a2-129">会社のサポートが行った設定に応じて、以下に示す例のような 2 種類のアカウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="688a2-129">Depending on how your company support has set things up, you might see two accounts that look similar to the example shown below.</span></span> <span data-ttu-id="688a2-130">1 つのアカウントの横にはブリーフケースがあり、もう 1 つのアカウントの横には Microsoft のロゴがあります。</span><span class="sxs-lookup"><span data-stu-id="688a2-130">One account has a briefcase next to it, and the other has the Microsoft logo next to it.</span></span>

    - <span data-ttu-id="688a2-131">ブリーフケースが表示されているアカウントがある場合はそれを選択し、その下に **[情報]** ボタンが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="688a2-131">If you see the account with the briefcase, select it, and look for an **Info** button under it.</span></span>
    - <span data-ttu-id="688a2-132">Microsoft のロゴが表示されているアカウントしかない場合はそのアカウントを選択して、その下に **[情報]** ボタンが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="688a2-132">If you see only the account with the Microsoft logo, select the account, and look for an **Info** button under it.</span></span>

    ![ブリーフケースまたは Microsoft のロゴの横にあるアカウント名を選択する](./media/win10pc-rs1-sync-info-button.png)

3. <span data-ttu-id="688a2-134">**[情報]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-134">Choose the **Info** button.</span></span> <span data-ttu-id="688a2-135">次の例のようなダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="688a2-135">A dialog opens that looks similar to the example below.</span></span>

    ![ブリーフケースまたは Microsoft のロゴの横にあるアカウント名を選択する](./media/win10pc-rs1-sync-button.png)

4. <span data-ttu-id="688a2-137">**[同期]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-137">Choose the **Sync** button.</span></span> <span data-ttu-id="688a2-138">デバイスと Intune が同期されます。</span><span class="sxs-lookup"><span data-stu-id="688a2-138">Your device will be synced with Intune.</span></span>

### <a name="steps-to-follow-if-you-see-work-access"></a><span data-ttu-id="688a2-139">[職場のアクセス] が表示されている場合の手順</span><span class="sxs-lookup"><span data-stu-id="688a2-139">Steps to follow if you see Work access</span></span>

1. <span data-ttu-id="688a2-140">**[アカウント]** ページで、**[職場のアクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-140">On the **Accounts** page, choose **Work access**.</span></span>

    ![アカウントの種類として職場のアクセスを選択する](./media/win10pc-sync-3-work-access.png)

2. <span data-ttu-id="688a2-142">**[Enroll in to device management]** (デバイス管理に登録する) セクションで、会社名を選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-142">Under the section **Enroll in to device management**, choose the name of your company.</span></span>

    ![デバイス管理の会社名の選択](./media/win10pc-sync-4-tap-com-name.png)

3. <span data-ttu-id="688a2-144">**[同期]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-144">Choose the **Sync** button.</span></span>

    ![[同期] ボタンの選択](./media/win10pc-sync-5-tap-sync.png)

   <span data-ttu-id="688a2-146">同期が完了するまで、このボタンは灰色表示になります。</span><span class="sxs-lookup"><span data-stu-id="688a2-146">The button becomes grayed out until the sync is finished.</span></span>

### <a name="windows-10-mobile"></a><span data-ttu-id="688a2-147">[Windows] 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="688a2-147">Windows 10 Mobile</span></span>
<span data-ttu-id="688a2-148">アプリのインストールを高速化するために Windows 10 Mobile デバイスを手動で同期するには:</span><span class="sxs-lookup"><span data-stu-id="688a2-148">To manually sync your Windows 10 Mobile device to speed up a slow app installation:</span></span>

   1. <span data-ttu-id="688a2-149">**[すべてのアプリ]** > **[設定]** > **[アカウント]** の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="688a2-149">Go to **All apps** > **Settings** > **Accounts**.</span></span>

       ![[設定] 画面の [アカウント] の選択](./media/win10m-sync-1-settings-accounts.png)

   2. <span data-ttu-id="688a2-151">**[職場のアクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-151">Choose **Work access**.</span></span>

       ![アカウントの種類として職場のアクセスを選択する](./media/win10m-sync-2-work-access.png)

   3. <span data-ttu-id="688a2-153">**[デバイス管理に登録する]** で、会社名を選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-153">Under **Enroll in to device management**, choose your company name.</span></span>

       ![デバイス管理の会社名の選択](./media/win10m-sync-3-tap-comp-name.png)

   4. <span data-ttu-id="688a2-155">**[同期]** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-155">Choose the **Sync** icon.</span></span>

       ![[同期] アイコンの選択](./media/win10m-sync-4-tap-sync.png)

       <span data-ttu-id="688a2-157">画面の上部に、"アカウントを同期中" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="688a2-157">The message “We’re synching your account” appears at the top of the screen.</span></span> <span data-ttu-id="688a2-158">同期が完了するまで、**[同期]** ボタンは灰色表示になります。</span><span class="sxs-lookup"><span data-stu-id="688a2-158">The **Sync** button is grayed out until your device finishes syncing.</span></span>

## <a name="windows-phone-81"></a><span data-ttu-id="688a2-159">Windows Phone 8。1</span><span class="sxs-lookup"><span data-stu-id="688a2-159">Windows Phone 8.1</span></span>
<span data-ttu-id="688a2-160">アプリのインストールを高速化するために Windows Phone 8.1 デバイスを手動で同期するには:</span><span class="sxs-lookup"><span data-stu-id="688a2-160">To manually sync your Windows Phone 8.1 device to speed up a slow app installation:</span></span>

1. <span data-ttu-id="688a2-161">**[すべてのアプリ]** > **[設定]** > **[会社アカウント]** の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="688a2-161">Go to **All apps** > **Settings** > **workplace**.</span></span>

    ![設定の一覧](./media/wp81-1-sync-settings-workplace.png)

2. <span data-ttu-id="688a2-163">会社名を選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-163">Choose the name of your company.</span></span>

    ![職場のアカウントの会社名の選択](./media/wp81-2-sync-tap-compname.png)

3. <span data-ttu-id="688a2-165">**[同期]** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="688a2-165">Choose the **Sync** icon.</span></span>

    ![[同期] アイコンの選択](./media/wp81-3-sync-tap-sync-button.png)

   <span data-ttu-id="688a2-167">デバイスで同期が完了するまでの間、画面の上部に、"アカウントを同期中" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="688a2-167">The message “We’re synching your account” appears at the top of the screen until your device finishes syncing.</span></span>

<span data-ttu-id="688a2-168">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="688a2-168">Still need help?</span></span> <span data-ttu-id="688a2-169">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="688a2-169">Contact your company support.</span></span> <span data-ttu-id="688a2-170">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="688a2-170">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
