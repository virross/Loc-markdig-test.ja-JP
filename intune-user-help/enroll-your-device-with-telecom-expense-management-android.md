---
title: "Intune 通信費管理サービスに Android デバイスを登録する"
description: "通信費管理サービスに Android デバイスを登録する方法について説明します。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 26aa3698-7e4d-453a-8852-ab75e72b6485
searchScope:
- User help
ROBOTS: 
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: c0fd638fe486c3ff253dd239012ce1d99a9eca82
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="enroll-your-android-device-in-telecom-expense-management"></a><span data-ttu-id="63f58-103">通信費管理サービスに Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="63f58-103">Enroll your Android device in telecom expense management</span></span>

<span data-ttu-id="63f58-104">データおよび音声プランが許容範囲内で使用されていることを確認するために、通信費管理ソフトウェアを使用している組織もあります。</span><span class="sxs-lookup"><span data-stu-id="63f58-104">Your organization may be using telecom expense management software to ensure that their data and voice plans are being used within acceptable limits.</span></span> <span data-ttu-id="63f58-105">デバイスの登録後、そのデバイスに最適なカテゴリを選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="63f58-105">Once you have completed enrolling your device, you will then be prompted to select the best category for that device.</span></span>

![iOS デバイス上の "デバイスの最適なカテゴリの選択" 画面のスクリーンショット。](./media/and-enroll-11-tem-select-best-category.png)

<span data-ttu-id="63f58-108">適切なオプションを選択すると、Google Play Store の [__Datalert__](https://play.google.com/store/apps/details?id=fr.memobox.databox) アプリをインストールするように通知されます。</span><span class="sxs-lookup"><span data-stu-id="63f58-108">Select the appropriate option, and you will receive a notification to install the [__Datalert__](https://play.google.com/store/apps/details?id=fr.memobox.databox) app from the Google Play Store.</span></span> <span data-ttu-id="63f58-109">Datalert アプリを使用すると、組織のデータ使用量を測定できます。</span><span class="sxs-lookup"><span data-stu-id="63f58-109">The Datalert app is how your organization can measure data usage.</span></span> <span data-ttu-id="63f58-110">組織で職場または学校の登録オプションが構成されている場合は、職場または学校のアカウントを使用してログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63f58-110">If your organization has configured the work or school enrollment option, you will be required to log in with your work or school account.</span></span> <span data-ttu-id="63f58-111">これが有効になっていない場合は、電話番号などの情報を入力し、コードを使用してデバイスを確認して、アプリから Datalert サービスに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63f58-111">If this hasn't been enabled, you will need to provide information such as your phone number and verify your device using a code to enroll into the Datalert service from the app.</span></span>

<span data-ttu-id="63f58-112">画面の右上隅にある __[次へ]__ の矢印をタップして進みます。</span><span class="sxs-lookup"><span data-stu-id="63f58-112">Tap the __next__ arrow at the top right corner of the screen to proceed.</span></span> <span data-ttu-id="63f58-113">会社のサポートから、__職場または学校の Microsoft アカウント__、または__電話番号__のいずれかを使用してサインインするように指示されます。</span><span class="sxs-lookup"><span data-stu-id="63f58-113">Your company support should tell you whether you'll sign in with your __Microsoft work or school account__ or to use your __phone number__.</span></span>

  ![Datalert アプリの [ようこそ] 画面のスクリーンショット。Datalert でデータ プランを最大限に活用する方法に関する簡単な説明のあと、次の画面に移動するように求められます。](./media/and-enroll-12-tem-datalert-setup.png)

## <a name="enroll-into-datalert-using-your-microsoft-work-or-school-account"></a><span data-ttu-id="63f58-115">職場または学校の Microsoft アカウントを使用して Datalert に登録する</span><span class="sxs-lookup"><span data-stu-id="63f58-115">Enroll into Datalert using your Microsoft work or school account</span></span>

1. <span data-ttu-id="63f58-116">__[Enroll with Microsoft account]\(Microsoft アカウントでの登録)__ を選択します。</span><span class="sxs-lookup"><span data-stu-id="63f58-116">Select __Enroll with Microsoft account__.</span></span>

   ![Datalert アプリの [設定] 画面の画像。Microsoft Office 365 アカウントと Intune サブスクリプションがある場合は、画面の上半分でデバイスを登録するための [電話番号] フィールドが提供され、画面の下半分で "Microsoft アカウントでの登録" が提供されます。](./media/and-enroll-12a-tem-datalert-enroll-msft-account.png)

2. <span data-ttu-id="63f58-118">利用可能なアカウントから職場または学校のアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="63f58-118">Choose your work or school account from the available accounts.</span></span> <span data-ttu-id="63f58-119">自分のアカウントが一覧にない場合は、**[アカウントの追加]** ボタンを使用してアカウントにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="63f58-119">If your account is not listed, you can sign in to it using the **Add account** button.</span></span>

   ![サンプル アカウントと [アカウントの追加] ボタンを示す "アカウントの選択" 画面のスクリーンショット。](./media/and-enroll-12b-tem-datalert-enroll-select-msft-account.png)

3. <span data-ttu-id="63f58-121">しばらくの間 Datalert セットアップが実行され、完了します。</span><span class="sxs-lookup"><span data-stu-id="63f58-121">Datalert setup will work for a few moments, then should complete.</span></span> <span data-ttu-id="63f58-122">完了したら __[完了]__ をタップします。</span><span class="sxs-lookup"><span data-stu-id="63f58-122">Tap __Finish__ when it completes.</span></span>

## <a name="enroll-into-datalert-using-your-phone-number"></a><span data-ttu-id="63f58-123">電話番号を使用して Datalert に登録する</span><span class="sxs-lookup"><span data-stu-id="63f58-123">Enroll into Datalert using your phone number</span></span>

1. <span data-ttu-id="63f58-124">デバイスの電話番号を提供します。</span><span class="sxs-lookup"><span data-stu-id="63f58-124">Provide your device's phone number.</span></span>

   ![Datalert アプリが電話番号を要求している画面のスクリーンショット。](./media/and-enroll-13-tem-datalert-phone-number.png)

2. <span data-ttu-id="63f58-126">次に SMS メッセージで確認コードを受信します。</span><span class="sxs-lookup"><span data-stu-id="63f58-126">You will then receive a verification code through an SMS message.</span></span> <span data-ttu-id="63f58-127">コードを入力して __[OK]__ をタップします。</span><span class="sxs-lookup"><span data-stu-id="63f58-127">Provide the code and tap __OK__.</span></span>

   ![Datalert アプリが SMS 確認コードを要求している画面のスクリーンショット。](./media/and-enroll-14-tem-datalert-sms.png)

3. <span data-ttu-id="63f58-129">確認コードを入力すると、Datalert のセットアップが完了します。</span><span class="sxs-lookup"><span data-stu-id="63f58-129">Once you've provided the verification code, Datalert setup will complete.</span></span> <span data-ttu-id="63f58-130">__[完了]__ をタップすると、Datalert アプリからデータを監視できるようになります。</span><span class="sxs-lookup"><span data-stu-id="63f58-130">Tap __Finish__ and you will be able to monitor your data from the Datalert app.</span></span>

   ![Datalert アプリが当日分のデータ使用状況を監視している画面のスクリーンショット。](./media/and-enroll-15-tem-datalert-monitoring-active.png)

<span data-ttu-id="63f58-132">登録が完了すると、Datalert アプリでデータ使用量が表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="63f58-132">Once you've enrolled, you will begin to see your data usage in the Datalert app.</span></span>

<span data-ttu-id="63f58-133">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="63f58-133">Still need help?</span></span> <span data-ttu-id="63f58-134">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="63f58-134">Contact your company support.</span></span> <span data-ttu-id="63f58-135">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="63f58-135">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
