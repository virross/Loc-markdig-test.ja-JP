---
title: "ポータル Web サイトからパスコードをリセットする方法 | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: adea1458421332aac8341d0a2159412669437a54
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a><span data-ttu-id="f27d1-102">ポータル サイト Web サイトからデバイスのパスコードをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="f27d1-102">How to reset your device passcode from the Company Portal website</span></span>

<span data-ttu-id="f27d1-103">Intune に登録したデバイスの PIN またはパスワードを紛失した場合は、[ポータル サイト web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)からリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-103">If you lose your device PIN or password for a device that you have enrolled in Intune, you can use the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) to reset it.</span></span> <span data-ttu-id="f27d1-104">会社のポータル Web サイトを使用すると、Intune に登録したコンピューターとデバイスを管理し、会社のポータル アプリを使用する場合とほぼ同じタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-104">You can use the Company Portal website to manage computers and devices that you have enrolled in Intune and to do most of the same tasks that you can do when you use your Company Portal app.</span></span>

> [!NOTE]
> <span data-ttu-id="f27d1-105">会社に登録されたデバイスを使用している場合、ポータル サイト Web サイトに [パスコードのリセット] ボタンが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="f27d1-105">It's possible that you won't see the Reset Passcode button on the Company Portal website if you use a corporate enrolled device.</span></span> <span data-ttu-id="f27d1-106">表示されない場合は、会社のサポートにパスコードのリセットを依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f27d1-106">If you do not, you'll need to contact your company support to reset the passcode for you.</span></span>

<span data-ttu-id="f27d1-107">パスコードをリセットするには:</span><span class="sxs-lookup"><span data-stu-id="f27d1-107">To reset your passcode:</span></span>

1.  <span data-ttu-id="f27d1-108">[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)で、__メニュー__ ボタン ![3 つの横棒が並行に積み上げられている、メニュー ボタンの小さな画像](/intune/media/CP_hamburger_menu.png) をタップしてから、__[デバイス]__ を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27d1-108">On the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog), tap the __menu__ button ![A small image of the menu button, three horizontal bars stacked in parallel.](/intune/media/CP_hamburger_menu.png), then select __My Devices__.</span></span>

2. <span data-ttu-id="f27d1-109">__[デバイス]__ ページで、パスコードをリセットするデバイスの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f27d1-109">On the __My Devices__ page, select the name of the device whose passcode you want to reset.</span></span>

  ![リスト表示されていないデバイスの登録または不明なデバイスの識別を求めるバナーの上に 2 つの不明なデバイスが示された、[デバイス] ページのスクリーンショット。](./media/macOS_enroll_002_tap_here_banner.png)

3.  <span data-ttu-id="f27d1-111">デバイスがポップアップ ウィンドウに開きます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-111">The device will open in a popup window.</span></span> <span data-ttu-id="f27d1-112">**[パスコードのリセット]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f27d1-112">Select the **Reset Passcode** button.</span></span>

    ![<span data-ttu-id="f27d1-113">[名前の変更]、[削除]、[デバイスのリセット]、[パスコードのリセット]、[リモート ロック] を含む、ポータル Web サイト上の選択されたデバイスに対するすべてのオプション。</span><span class="sxs-lookup"><span data-stu-id="f27d1-113">All options for a selected device on the Company Portal website, including Rename, Remove, Reset Device, Reset Passcode, and Remote Lock.</span></span> ](./media/iwp-screen-with-all-options.png)

4.  <span data-ttu-id="f27d1-114">パスコードをリセットすることと、リセット後にデバイスからサインアウトすることの確認を求めるバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-114">A banner will appear asking you to confirm that you want to reset your passcode, and that your device will sign you out after it does this.</span></span> <span data-ttu-id="f27d1-115">再度サインインするには、5 分間待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="f27d1-115">You will then need to wait 5 minutes before signing in again.</span></span>

  ![デバイスのパスコードのリセットとユーザーのログアウトに関する警告が示されている、リセットのパスコード バナー。ユーザー入力用のボタンは、[サインアウト] と [キャンセル] です。](./media/iwp-reset-passcode-popup.png)

5.  <span data-ttu-id="f27d1-117">**[サインアウト]** を選択すると、デバイスのパスコードが削除されることを知らせる最終メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-117">Select **Sign out**, and you will receive one final message letting you know about the removal of the passcode from the device.</span></span> <span data-ttu-id="f27d1-118">デバイスを携帯しない場合は、パスコードを削除しないでください。削除すると、デバイスに物理的にアクセスできるユーザーは誰でも、デバイス上のほとんどの (個人または会社の) 情報にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f27d1-118">If you do not have the device with you, do not remove the passcode, as whomever has physical access to the device will be able to access most of the information on it - personal or corporate.</span></span> 

  ![デバイスのパスコードのリセットとデバイスからのパスコードの削除に関する警告が示されている、2 番目のリセットのパスコード バナー。](./media/iwp-reset-passcode-2nd-popup.png)

  <span data-ttu-id="f27d1-121">デバイスによってパスコードの種類が異なります。</span><span class="sxs-lookup"><span data-stu-id="f27d1-121">Different devices have different types of passcodes.</span></span>

  <span data-ttu-id="f27d1-122">**Android**: 既存のパスコードが削除され、文字と数字の両方で仮のパスコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-122">**Android**: Removes the existing passcode and creates a temporary passcode with both letters and numbers</span></span> 
  
  > [!NOTE]
  > <span data-ttu-id="f27d1-123">Android 7.0 以降のデバイスのパスコードはリセットできません。</span><span class="sxs-lookup"><span data-stu-id="f27d1-123">You cannot reset the passcode for devices with Android 7.0 and later.</span></span> <span data-ttu-id="f27d1-124">そのようなデバイスでパスコードを忘れた場合は、工場出荷時の設定にリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f27d1-124">You must reset these devices to factory settings if you forget your passcode.</span></span>

  <span data-ttu-id="f27d1-125">**iOS**: 既存のパスコードが削除されます。一時パスコードは作成されません。</span><span class="sxs-lookup"><span data-stu-id="f27d1-125">**iOS**: Removes the existing passcode and does not create a temporary passcode.</span></span> <span data-ttu-id="f27d1-126">Touch ID 指紋スキャナーでデバイスを開いたり、商品を購入したりしている場合、Touch ID をもう一度設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f27d1-126">If you're using the Touch ID fingerprint         scanner for opening your device or making purchases, you'll need to set it up again.</span></span>

  <span data-ttu-id="f27d1-127">**Windows 10 Mobile**: 既存のパスコードが削除され、文字と数字の両方で仮のパスコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-127">**Windows 10 Mobile**: Removes the existing passcode and creates a temporary passcode with both letters and numbers.</span></span> <span data-ttu-id="f27d1-128">Windows Hello 顔認識でログインしている場合、その機能を引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-128">If you're        using Windows Hello facial recognition to log in, it will still be supported.</span></span>
    
  <span data-ttu-id="f27d1-129">**Windows Phone 8.1**: 既存のパスコードが削除され、数字で仮のパスコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-129">**Windows Phone 8.1**: Removes the existing passcode and creates a temporary passcode with numbers</span></span>

  <span data-ttu-id="f27d1-130">Android および Windows デバイスの場合は、一時パスワードが **[デバイスの詳細]** に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-130">For Android and Windows devices, the temporary password will appear in the **Device Details**.</span></span> 

6.  <span data-ttu-id="f27d1-131">デバイスのロックを解除したら、新しいパスコードを設定するか、デバイスの **[設定]** で一時パスコードを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f27d1-131">Unlock your device and set a new passcode, or change the temporary passcode by going to your device **Settings**.</span></span>

<span data-ttu-id="f27d1-132">パスコードが正常にリセットされたことを確認する通知を表示するには、ポータル サイト Web サイトの右上にある通知フラグをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f27d1-132">To see a notification confirming that your password was reset successfully, click the notification flag at the top right of the Company Portal website.</span></span>

<span data-ttu-id="f27d1-133">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="f27d1-133">Still need help?</span></span> <span data-ttu-id="f27d1-134">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f27d1-134">Contact your company support.</span></span> <span data-ttu-id="f27d1-135">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f27d1-135">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
