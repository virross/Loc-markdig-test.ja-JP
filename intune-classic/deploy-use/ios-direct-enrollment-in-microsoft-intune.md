---
title: "iOS デバイスを直接登録する"
description: "Apple Configurator ツールを使用して、企業所有の iOS デバイスを Mac コンピューターに USB で接続し、定義済みのポリシーで直接登録する。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e295aaa16828206685acf9a461eaa953478d772e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="directly-enroll-ios-devices-by-using-apple-configurator"></a><span data-ttu-id="e42d1-103">Apple Configurator を使用した iOS デバイスの直接登録</span><span class="sxs-lookup"><span data-stu-id="e42d1-103">Directly enroll iOS devices by using Apple Configurator</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e42d1-104">Intune は、Mac コンピューターで実行される [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) ツールを使用した、企業所有の iOS デバイスの登録をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e42d1-104">Intune supports the enrollment of corporate-owned iOS devices by using the [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer.</span></span> <span data-ttu-id="e42d1-105">このプロセスはデバイスを工場出荷時の設定に戻さず、定義済みのポリシーでデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-105">This process does not factory-reset the device and enrolls the device with a predefined policy.</span></span> <span data-ttu-id="e42d1-106">この方法は、**ユーザー アフィニティなし**になっているデバイス向けであり、iOS デバイスを Mac コンピューターに USB 接続して、会社の登録をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e42d1-106">This method is for devices with **No user affinity** and requires you to USB-connect the iOS device to a Mac computer to set up corporate enrollment.</span></span>

<span data-ttu-id="e42d1-107">iOS デバイスを直接登録する場合は、デバイスのシリアル番号を取得しなくてもデバイスを登録することができます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-107">When you're directly enrolling iOS devices, you can enroll a device without acquiring the device's serial number.</span></span> <span data-ttu-id="e42d1-108">登録時に Intune がデバイス名をキャプチャする前に、デバイスを識別するための名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-108">You can also name the device for identification purposes before Intune captures the device name during enrollment.</span></span> <span data-ttu-id="e42d1-109">会社のポータル アプリは、直接登録されているデバイスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e42d1-109">The Company Portal app is not supported for directly enrolled devices.</span></span> <span data-ttu-id="e42d1-110">このガイドでは、Mac コンピューターで Apple Configurator 2.0 を使用していることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="e42d1-110">This guidance assumes you are using Apple Configurator 2.0 on a Mac computer.</span></span>

>[!NOTE]
><span data-ttu-id="e42d1-111">この登録方法は、[デバイス登録マネージャー](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)の方法と同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e42d1-111">This enrollment method can't be used with the [device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) method.</span></span>

1. <span data-ttu-id="e42d1-112">まだ定義していない場合は、Apple Configurator を使用して、iOS デバイス用のデバイス登録プロファイルを作成してください。</span><span class="sxs-lookup"><span data-stu-id="e42d1-112">If you haven't already, create a device enrollment profile for iOS devices enrolled through Apple Configurator.</span></span> <span data-ttu-id="e42d1-113">デバイス登録プロファイルで、デバイスに適用する設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-113">A device enrollment profile defines the settings applied to devices.</span></span>

   1. <span data-ttu-id="e42d1-114">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[業務用デバイスの登録]** の順に選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-114">In the [Microsoft Intune administration console](https://manage.microsoft.com) go to **Policy** &gt; **Corporate Device Enrollment**, and then choose **Add**.</span></span>

      ![[デバイス登録プロファイルの作成] ページ](../media/pol-sa-corp-enroll.png)

   2. <span data-ttu-id="e42d1-116">デバイス プロファイルの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-116">Enter details for the device profiles:</span></span>

      - <span data-ttu-id="e42d1-117">**名前**: デバイス登録プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-117">**Name**: Name of the device enrollment profile.</span></span> <span data-ttu-id="e42d1-118">この機能はユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e42d1-118">Not visible to users.</span></span>

      - <span data-ttu-id="e42d1-119">**説明**: デバイス登録プロファイルの説明。</span><span class="sxs-lookup"><span data-stu-id="e42d1-119">**Description**: Description of the device enrollment profile.</span></span> <span data-ttu-id="e42d1-120">この機能はユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e42d1-120">Not visible to users.</span></span>

      - <span data-ttu-id="e42d1-121">**ユーザーへの関連付け**: デバイスの登録方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-121">**User affiliation**: Specifies how devices are enrolled.</span></span> <span data-ttu-id="e42d1-122">直接登録では、**[ユーザー アフィニティがありません]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-122">For Direct Enrollment, choose **No user affinity**.</span></span>

      - <span data-ttu-id="e42d1-123">**デバイス グループの事前割り当て**: このプロファイルを使用するすべてのデバイスが最初にこのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-123">**Device group pre-assignment**: All devices that have this profile will initially belong to this group.</span></span> <span data-ttu-id="e42d1-124">登録後にデバイスの再割り当てができます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-124">You can reassign devices after enrollment.</span></span>

        [!INCLUDE [groups deprecated](../includes/group-deprecation.md)]


   3. <span data-ttu-id="e42d1-125">**[プロファイルの保存]** を選択してプロファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-125">Choose **Save Profile** to add the profile.</span></span>

2. <span data-ttu-id="e42d1-126">iOS デバイスに展開するプロファイルを .mobileconfig としてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e42d1-126">Export a profile as .mobileconfig to deploy to iOS devices:</span></span>

   1.   <span data-ttu-id="e42d1-127">作成したデバイス プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-127">Select the device profile that you created.</span></span>

   2.   <span data-ttu-id="e42d1-128">タスク バーの **[エクスポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-128">Choose **Export** in the taskbar.</span></span>

   3.   <span data-ttu-id="e42d1-129">**[プロファイルのダウンロード]** を選択し、ダウンロードした .mobileconfig ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-129">Choose **Download profile** and save the downloaded .mobileconfig file.</span></span>

3. <span data-ttu-id="e42d1-130">ダウンロードした .mobileconfig ファイルを Mac コンピューターにコピーして、ファイルを転送します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-130">Transfer the file by copying the downloaded .mobileconfig file to a Mac computer.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e42d1-131">登録プロファイルの URL は、エクスポートしたときから 2 週間有効です。</span><span class="sxs-lookup"><span data-stu-id="e42d1-131">The enrollment profile URL is valid for two weeks from when it is exported.</span></span> <span data-ttu-id="e42d1-132">2 週間後、セットアップ アシスタントで iOS デバイスを登録するには、新しい登録プロファイルの URL をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e42d1-132">After two weeks, you must export a new enrollment profile URL to enroll iOS devices with Setup Assistant.</span></span>

4. <span data-ttu-id="e42d1-133">Apple Configurator を使用してデバイスを準備します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-133">Prepare the device with Apple Configurator.</span></span> <span data-ttu-id="e42d1-134">モバイル デバイスを管理するために、iOS デバイスを Mac コンピューターに接続および登録します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-134">iOS devices are connected to the Mac computer and enrolled for mobile device management.</span></span>

   1.  <span data-ttu-id="e42d1-135">Mac コンピューターで **Apple Configurator 2.0** を開きます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-135">On a Mac computer, open **Apple Configurator 2.0**.</span></span>

   2.  <span data-ttu-id="e42d1-136">iOS デバイスを USB ケーブルで Mac コンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-136">Connect the iOS device to the Mac computer with a USB cord.</span></span> <span data-ttu-id="e42d1-137">デバイスの検出時にそのデバイス用に開かれた**写真**、**iTunes**、およびその他のアプリを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-137">Close **Photos**, **iTunes**, and other apps that open for the device when the device is detected.</span></span>

   3.  <span data-ttu-id="e42d1-138">Apple Configurator で、接続された iOS デバイスを選択し、**[追加]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-138">In Apple Configurator, choose the connected iOS device, and then choose the **Add** button.</span></span> <span data-ttu-id="e42d1-139">デバイスに追加できるオプションがドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-139">Options that can be added to the device appear in the drop-down list.</span></span> <span data-ttu-id="e42d1-140">**[プロファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-140">Choose **Profiles**.</span></span>

   4.  <span data-ttu-id="e42d1-141">ファイル ピッカーを使用して、Intune からエクスポートした .mobileconfig ファイルを選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-141">Use the file picker to select the .mobileconfig file that you exported from Intune, and then choose **Add**.</span></span> <span data-ttu-id="e42d1-142">プロファイルがデバイスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e42d1-142">The profile is added to the device.</span></span>  <span data-ttu-id="e42d1-143">デバイスが**監視対象外**である場合は、インストール時にデバイスの承認が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e42d1-143">If the device is **Unsupervised**, the installation will require acceptance on the device.</span></span>

5. <span data-ttu-id="e42d1-144">iOS デバイスにプロファイルをインストールする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="e42d1-144">You are ready to install the profile on the iOS device.</span></span> <span data-ttu-id="e42d1-145">デバイスでセットアップ アシスタントが既に完了し、使用する準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e42d1-145">The device must have already completed the Setup Assistant and be ready to use.</span></span> <span data-ttu-id="e42d1-146">登録のためにアプリの展開が必要な場合は、アプリの展開時に Apple ID で App Store にサインインする必要があるため、デバイスに Apple ID が設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e42d1-146">If enrollment entails app deployments, the device should have an Apple ID set up because the app deployments will require that you have an Apple ID signed in for the App Store.</span></span>

   1.  <span data-ttu-id="e42d1-147">iOS デバイスのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-147">Unlock the iOS device.</span></span>

   2.  <span data-ttu-id="e42d1-148">**[管理プロファイル]** の **[プロファイルのインストール]** ダイアログ ボックスで、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-148">In the **Install profile** dialog box for **Management profile**,  choose **Install**.</span></span>

   3.  <span data-ttu-id="e42d1-149">必要に応じて、**[デバイスのパスコード]** または **[Apple ID]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-149">Provide **Device Passcode** or **Apple ID**, if required.</span></span>

   4.  <span data-ttu-id="e42d1-150">**[警告]** を受け入れ、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-150">Accept the **Warning**, and choose **Install**.</span></span>

   5.  <span data-ttu-id="e42d1-151">**[リモート警告]** を受け入れ、**[信頼]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-151">Accept the **Remote Warning**, and choose **Trust**.</span></span>

   6.  <span data-ttu-id="e42d1-152">**[インストール完了]** ボックスでプロファイルが **[インストール済み]** であることを確認したら、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-152">When the **Profile Installed** box confirms the profile as **Installed**, choose **Done**.</span></span>

6. <span data-ttu-id="e42d1-153">IOS デバイスで開く**設定**に進み**全般** &gt; **デバイス管理** &gt; **管理プロファイル**.</span><span class="sxs-lookup"><span data-stu-id="e42d1-153">On the iOS device, open **Settings** and go to **General** &gt; **Device Management** &gt; **Management Profile**.</span></span> <span data-ttu-id="e42d1-154">プロファイルのインストールが一覧に表示されていることを確認し、iOS のポリシー制限とインストールされているアプリを確認します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-154">Confirm that the profile installation is listed, and check the iOS policy restrictions and installed apps.</span></span> <span data-ttu-id="e42d1-155">ポリシー制限とアプリがデバイスに表示されるまでに、最大 10 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e42d1-155">Policy restrictions and apps might take up to 10 minutes to appear on the device.</span></span>

7. <span data-ttu-id="e42d1-156">デバイスを配布します。</span><span class="sxs-lookup"><span data-stu-id="e42d1-156">Distribute devices.</span></span> <span data-ttu-id="e42d1-157">これで、iOS デバイスが Intune に登録され、管理対象になりました。</span><span class="sxs-lookup"><span data-stu-id="e42d1-157">The iOS device is now enrolled with Intune and managed.</span></span>
