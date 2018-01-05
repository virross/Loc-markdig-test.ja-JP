---
title: "Intune に Windows 10 デバイスを登録する | Microsoft Docs"
description: "Intune に Windows 10 のモバイル デバイスまたはデスクトップ デバイスを登録する方法について説明します"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d5c2411d685b6dbe4ad8825fd73394a0fbf5c796
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="enroll-your-windows-10-devices-in-intune"></a><span data-ttu-id="47496-103">Intune に Windows 10 デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="47496-103">Enroll your Windows 10 devices in Intune</span></span>

<span data-ttu-id="47496-104">デバイスを Microsoft Intune に登録すると、Windows 10 デバイスが組織のセキュリティで保護されているデータ (電子メール、ファイル、その他のリソースなど) にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="47496-104">Enrolling your devices into Microsoft Intune allows your Windows 10 devices to get access to your organization’s secure data, including email, files, and other resources.</span></span> <span data-ttu-id="47496-105">対象は Windows 10 Desktop と Windows 10 Mobile デバイスの両方です。</span><span class="sxs-lookup"><span data-stu-id="47496-105">This is true for both Windows 10 desktop and Windows 10 Mobile devices.</span></span> <span data-ttu-id="47496-106">デバイスを登録すると、ユーザーと組織の両方にとってこのアクセスを保護し、職場のデータと個人のデータを分けることができます。</span><span class="sxs-lookup"><span data-stu-id="47496-106">Enrolling your devices helps secure this access for both you and your organization, and helps keep your work data separate from your personal data.</span></span>

<span data-ttu-id="47496-107">詳細については、</span><span class="sxs-lookup"><span data-stu-id="47496-107">Want to know more?</span></span> <span data-ttu-id="47496-108">「[ポータル サイト アプリをインストールし、Intune に Windows デバイスを登録するとどうなりますか](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md)」と「[デバイスを Intune に登録した場合に IT 管理者が確認できるもの](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47496-108">Find out what happens when you [enroll your device in Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) and what that means for the [information on your device](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).</span></span>

## <a name="windows-10-desktop-devices"></a><span data-ttu-id="47496-109">Windows 10 Desktop デバイス</span><span class="sxs-lookup"><span data-stu-id="47496-109">Windows 10 Desktop devices</span></span>

1. <span data-ttu-id="47496-110">**[スタート]** メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="47496-110">Go to **Start**.</span></span>

2. <span data-ttu-id="47496-111">__検索バー__に「PC 情報」と入力し、__[PC 情報]__ を選択します。</span><span class="sxs-lookup"><span data-stu-id="47496-111">Type the phrase "about your PC" into the __search bar__, then select __About your PC__.</span></span>

   ![PC 情報の検索設定](media/searching_for_about_your_pc.png)

3. <span data-ttu-id="47496-113">__[設定]__ には、PC にインストールされている Windows 10 のバージョンに関する情報の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47496-113">In your __Settings__, you will see a list of information about the version of Windows 10 that is installed on your PC.</span></span> <span data-ttu-id="47496-114">一覧の __[バージョン]__ を確認します。</span><span class="sxs-lookup"><span data-stu-id="47496-114">Within this list, locate the __Version__.</span></span>

   ![Windows 10 Desktop の PC 情報](media/settings_about_pc.png)

4. <span data-ttu-id="47496-116">バージョンが __1607 以降__の場合、[こちらの手順](enroll-your-w10-device-access-work-or-school.md)に進みます。</span><span class="sxs-lookup"><span data-stu-id="47496-116">If your version is __1607 or higher__, continue with [these steps](enroll-your-w10-device-access-work-or-school.md).</span></span> <span data-ttu-id="47496-117">バージョンが __1511 以前__の場合、[こちらの手順](enroll-your-w10-device-your-account.md)に進みます。</span><span class="sxs-lookup"><span data-stu-id="47496-117">If your version is __1511 or less__, continue with [these steps](enroll-your-w10-device-your-account.md).</span></span>

## <a name="windows-10-mobile-devices"></a><span data-ttu-id="47496-118">Windows 10 Mobile デバイス</span><span class="sxs-lookup"><span data-stu-id="47496-118">Windows 10 Mobile devices</span></span>        

1.  <span data-ttu-id="47496-119">__[スタート]__ で __[すべてのアプリ]__ をスワイプし、__[設定]__ アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="47496-119">On __Start__, swipe over to the __All apps__ list, then select the __Settings__ app.</span></span>        
2.  <span data-ttu-id="47496-120">__[システム]__、__[バージョン情報]__ の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="47496-120">Tap on __System__ then __About__.</span></span>       
3.  <span data-ttu-id="47496-121">__[デバイス情報]__ の __[詳細情報]__ をタップします。</span><span class="sxs-lookup"><span data-stu-id="47496-121">Under __Device information__, tap __More info__.</span></span> <span data-ttu-id="47496-122">デバイスに関する情報の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47496-122">You will see a list of information about your device.</span></span> <span data-ttu-id="47496-123">一覧の __[バージョン]__ を確認します。</span><span class="sxs-lookup"><span data-stu-id="47496-123">Within this list, locate the __Version__.</span></span>        
4.  <span data-ttu-id="47496-124">バージョンが __1607__ の場合、[こちらの手順](enroll-your-w10-device-access-work-or-school.md)に進みます。</span><span class="sxs-lookup"><span data-stu-id="47496-124">If your version is __1607__, continue with [these steps](enroll-your-w10-device-access-work-or-school.md).</span></span> <span data-ttu-id="47496-125">バージョンが __1511 以前__の場合、[こちらの手順](enroll-your-w10-device-your-account.md)に進みます。</span><span class="sxs-lookup"><span data-stu-id="47496-125">If your version is __1511 or less__, continue with [these steps](enroll-your-w10-device-your-account.md).</span></span>

<span data-ttu-id="47496-126">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="47496-126">Still need help?</span></span> <span data-ttu-id="47496-127">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="47496-127">Contact your company support.</span></span> <span data-ttu-id="47496-128">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="47496-128">For their contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
