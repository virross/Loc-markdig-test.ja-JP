---
title: "Intune 通信費管理サービスに iOS デバイスを登録する"
description: "通信費管理サービスに iOS デバイスを登録する方法について説明します。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d8c6372-f2ce-4558-8886-1d7c1966699c
searchScope: User help
ROBOTS: 
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 13f284c62e1232a560ec9e5186de4055d616ef3a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-your-ios-device-in-telecom-expense-management"></a><span data-ttu-id="1f385-103">通信費管理サービスに iOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="1f385-103">Enroll your iOS device in telecom expense management</span></span>

<span data-ttu-id="1f385-104">データおよび音声プランが許容範囲内で使用されていることを確認するために、通信費管理ソフトウェアを使用している組織もあります。</span><span class="sxs-lookup"><span data-stu-id="1f385-104">Your organization may be using telecom expense management software to ensure that their data and voice plans are being used within acceptable limits.</span></span> <span data-ttu-id="1f385-105">デバイスの登録後、そのデバイスに最適なカテゴリを選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="1f385-105">Once you have completed enrolling your device, you will then be prompted select the best category for that device.</span></span>

  ![iOS デバイス上の "デバイスの最適なカテゴリの選択" 画面のスクリーンショット。](./media/ios-enroll-10-tem-select-best-category.png)

<span data-ttu-id="1f385-108">適切なオプションを選択すると、App Store から [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8) アプリをインストールするように通知されます。</span><span class="sxs-lookup"><span data-stu-id="1f385-108">Select the appropriate option, and you will receive a notification to install the [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8) app from the App Store.</span></span> <span data-ttu-id="1f385-109">Datalert アプリを使用すると、組織のデータ使用量を測定できます。</span><span class="sxs-lookup"><span data-stu-id="1f385-109">The Datalert app is how your organization can measure data usage.</span></span> <span data-ttu-id="1f385-110">組織で Microsoft の職場または学校の登録オプションが構成されている場合は、職場または学校のアカウントでログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f385-110">If your organization has configured the Microsoft work or school enrollment option, you will be required to log in with your work or school account.</span></span> <span data-ttu-id="1f385-111">これが有効になっていない場合は、電話番号などの情報を入力し、コードを使用してデバイスを確認して、アプリから Datalert サービスに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f385-111">If this hasn't been enabled, you will need to provide information such as your phone number and verify your device using a code to enroll into the Datalert service from the app.</span></span>

  ![Datalert アプリの [ようこそ] 画面のスクリーンショット。Datalert でデータ プランを最大限に活用する方法に関する簡単な説明のあと、次の画面に移動するように求められます。](./media/ios-enroll-11-tem-datalert-setup.png)

## <a name="enroll-into-datalert-using-your-microsoft-work-or-school-account"></a><span data-ttu-id="1f385-113">職場または学校の Microsoft アカウントを使用して Datalert に登録する</span><span class="sxs-lookup"><span data-stu-id="1f385-113">Enroll into Datalert using your Microsoft work or school account</span></span>

> [!NOTE]
> <span data-ttu-id="1f385-114">この方法で登録するには、お使いの電話に [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) アプリがインストールされアクティブになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f385-114">You need to have the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) app installed and active on your phone to enroll this way.</span></span>

1. <span data-ttu-id="1f385-115">__[Enroll with Microsoft account]\(Microsoft アカウントでの登録)__ を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f385-115">Select __Enroll with Microsoft account__.</span></span>

  ![Datalert アプリの [設定] 画面の画像。画面の上半分ではデバイスを登録するための[電話番号] フィールドが提供され、Microsoft Office 365 アカウントと Intune サブスクリプションがある場合は、画面下部で "Microsoft アカウントでの登録" が提供されます。](./media/ios-enroll-11a-tem-datalert-enroll-msft-account.png)

2. <span data-ttu-id="1f385-117">__"Datalert" が "Authenticator" を開こうとしている__、という通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1f385-117">You'll receive a notification that __"Datalert" wants to open "Authenticator"__.</span></span> <span data-ttu-id="1f385-118">__[開く]__ を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f385-118">Select __Open__.</span></span>

  ![Datalert アプリの要求で認証アプリを開くことを求めるポップアップ画面のイメージ。](./media/ios-enroll-11b-tem-datalert-open-authenticator.png)

3. <span data-ttu-id="1f385-120">__Microsoft の学校または職場のアカウント__ でサインインします。</span><span class="sxs-lookup"><span data-stu-id="1f385-120">Sign in with your __Microsoft school or work account__.</span></span> <span data-ttu-id="1f385-121">しばらくの間 Datalert セットアップが実行され、完了します。</span><span class="sxs-lookup"><span data-stu-id="1f385-121">Datalert setup will work for a few moments, then should complete.</span></span> <span data-ttu-id="1f385-122">完了したら __[完了]__ をタップします。</span><span class="sxs-lookup"><span data-stu-id="1f385-122">Tap __Finish__ when it completes.</span></span>

## <a name="enroll-into-datalert-using-your-phone-number"></a><span data-ttu-id="1f385-123">電話番号を使用して Datalert に登録する</span><span class="sxs-lookup"><span data-stu-id="1f385-123">Enroll into Datalert using your phone number</span></span>

1. <span data-ttu-id="1f385-124">デバイスの電話番号を提供します。</span><span class="sxs-lookup"><span data-stu-id="1f385-124">Provide your device's phone number.</span></span>

  ![Datalert アプリが電話番号を要求している画面のスクリーンショット。](./media/ios-enroll-12-tem-datalert-phone-number.png)

2. <span data-ttu-id="1f385-126">次に SMS メッセージで確認コードを受信します。</span><span class="sxs-lookup"><span data-stu-id="1f385-126">You will then receive a verification code through an SMS message.</span></span> <span data-ttu-id="1f385-127">コードを入力して __[OK]__ をタップします。</span><span class="sxs-lookup"><span data-stu-id="1f385-127">Provide the code and tap __OK__.</span></span>

  ![Datalert アプリが SMS 確認コードを要求している画面のスクリーンショット。](./media/ios-enroll-13-tem-datalert-sms.png)

3. <span data-ttu-id="1f385-129">確認コードを入力すると、Datalert のセットアップが完了します。</span><span class="sxs-lookup"><span data-stu-id="1f385-129">Once you've provided the verification code, Datalert setup will complete.</span></span> <span data-ttu-id="1f385-130">__[完了]__ をタップすると、Datalert アプリからデータを監視できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1f385-130">Tap __Finish__ and you will be able to monitor your data from the Datalert app.</span></span>

  ![Datalert アプリが当日分のデータ使用状況を監視している画面のスクリーンショット。](./media/ios-enroll-14-tem-datalert-monitoring-active.png)

<span data-ttu-id="1f385-132">登録が完了すると、Datalert アプリでデータ使用量が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="1f385-132">Once you've enrolled, you will begin to see your data usage in the Datalert app.</span></span>

<span data-ttu-id="1f385-133">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="1f385-133">Still need help?</span></span> <span data-ttu-id="1f385-134">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1f385-134">Contact your company support.</span></span> <span data-ttu-id="1f385-135">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="1f385-135">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
