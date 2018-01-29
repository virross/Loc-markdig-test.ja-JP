---
title: "Android デバイスで管理対象アプリを使用する | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed10a62c-b026-4ad3-ac41-641933522df2
searchScope:
- User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 95c058cea88764be30d692831993f21f2423e2cb
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-managed-apps-on-your-android-device"></a><span data-ttu-id="a7509-102">Android デバイスで管理対象アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="a7509-102">Use managed apps on your Android device</span></span>

<span data-ttu-id="a7509-103">管理対象アプリとは、そのアプリでアクセス可能な会社のデータを保護できるよう会社のサポートがセットアップ可能なアプリです。</span><span class="sxs-lookup"><span data-stu-id="a7509-103">Managed apps are apps that your company support can set up to help protect company data that you can access in that app.</span></span> <span data-ttu-id="a7509-104">管理対象アプリ内の会社のデータに Android デバイスでアクセスする場合、アプリの動作が予期したものとは少し異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7509-104">When you access company data in a managed app on your Android device, you may notice that the app works a little differently than what you expect.</span></span> <span data-ttu-id="a7509-105">たとえば、保護された会社のデータをコピーして貼り付けできない、またはそのデータを特定の場所に保存できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7509-105">For example, you might not be able to copy and paste protected company data, or you might not be able to save that data to certain locations.</span></span>

<span data-ttu-id="a7509-106">また、異なる管理対象アプリがデバイス上で連携して動作し、会社のデータを保護しながら、日常のタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7509-106">Different managed apps can also work together on your device to allow you to do your daily tasks, while keeping corporate data protected.</span></span> <span data-ttu-id="a7509-107">たとえば、1 つの管理対象アプリで会社のファイルを開き、別の管理対象アプリでそのファイルを表示する必要がある場合、ファイルを表示できるようにする管理対象アプリが自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="a7509-107">For example, if you open a company file in one managed app, and another managed app is required to view that file, the managed app that allows you to view the file opens automatically.</span></span> <span data-ttu-id="a7509-108">必要なアプリが使用できない場合、管理されているドキュメント内からドキュメントを開くまたは Web リンクにアクセスするなどの特定の操作が行えない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7509-108">If a required app is not available, certain actions, like opening a document or accessing a web link from within a managed document, might not be available.</span></span>

<span data-ttu-id="a7509-109">管理対象アプリで会社のデータにアクセスすると、開こうとしているアプリが管理されていることを通知する以下のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7509-109">When you access company data in a managed app, you see a message like the one below, which lets you know that the app you are opening is managed.</span></span>

![open-managed-apps-message](./media/managed-apps-message.png)

## <a name="how-do-i-get-managed-apps"></a><span data-ttu-id="a7509-111">管理対象アプリを取得する方法</span><span class="sxs-lookup"><span data-stu-id="a7509-111">How do I get managed apps?</span></span>
<span data-ttu-id="a7509-112">管理対象アプリはいくつかの方法で取得できます。</span><span class="sxs-lookup"><span data-stu-id="a7509-112">You get managed apps in a couple of different ways:</span></span>

-   <span data-ttu-id="a7509-113">デバイスが Microsoft Intune に登録されるときに、ポータル サイト アプリまたはポータル Web サイトからアプリをインストールするか、または会社のサポートがアプリをデバイスにインストールする場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7509-113">When your device is enrolled in Microsoft Intune, you either install the app from your Company Portal app or Company Portal website, or your company support might install it on your device.</span></span> <span data-ttu-id="a7509-114">登録については、「[Intune にデバイスを登録する](enroll-your-device-in-Intune-android.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a7509-114">To learn about enrolling, see [Enroll your device in Intune](enroll-your-device-in-Intune-android.md).</span></span>

-   <span data-ttu-id="a7509-115">Play ストアからアプリをインストールし、Intune で管理されている会社のユーザー アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="a7509-115">You install an app from the Play Store, and then sign in with your corporate user account that is managed by Intune.</span></span>

## <a name="what-can-my-company-support-manage-in-an-app"></a><span data-ttu-id="a7509-116">会社のサポートがアプリで管理できるもの</span><span class="sxs-lookup"><span data-stu-id="a7509-116">What can my company support manage in an app?</span></span>
<span data-ttu-id="a7509-117">以下は、会社のサポートがアプリで管理でき、デバイス上での会社データとのやり取りに影響するオプションの例です。</span><span class="sxs-lookup"><span data-stu-id="a7509-117">Here are some examples of options that your company support can manage in an app, and that can affect your interactions with company data on your device:</span></span>

-   <span data-ttu-id="a7509-118">特定の web サイトへのアクセス</span><span class="sxs-lookup"><span data-stu-id="a7509-118">Access to specific websites</span></span>

-   <span data-ttu-id="a7509-119">アプリケーション間のデータ転送</span><span class="sxs-lookup"><span data-stu-id="a7509-119">Transfers of data between apps</span></span>

-   <span data-ttu-id="a7509-120">ファイルの保存</span><span class="sxs-lookup"><span data-stu-id="a7509-120">Saving files</span></span>

-   <span data-ttu-id="a7509-121">コピーと貼り付けの操作</span><span class="sxs-lookup"><span data-stu-id="a7509-121">Copy and paste operations</span></span>

-   <span data-ttu-id="a7509-122">暗証番号 (pin) のアクセスの要件</span><span class="sxs-lookup"><span data-stu-id="a7509-122">PIN access requirements</span></span>

-   <span data-ttu-id="a7509-123">会社の資格情報を使用したサインイン</span><span class="sxs-lookup"><span data-stu-id="a7509-123">Your sign in, using company credentials</span></span>

-   <span data-ttu-id="a7509-124">クラウドへのバックアップ機能</span><span class="sxs-lookup"><span data-stu-id="a7509-124">Ability to back up to the cloud</span></span>

-   <span data-ttu-id="a7509-125">スクリーン ショットを撮る機能</span><span class="sxs-lookup"><span data-stu-id="a7509-125">Ability to take screenshots</span></span>

-   <span data-ttu-id="a7509-126">データの暗号化の要件</span><span class="sxs-lookup"><span data-stu-id="a7509-126">Data encryption requirements</span></span>

<span data-ttu-id="a7509-127">IT 部門が管理する可能性のある一般的なアプリを以下にいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="a7509-127">Some common apps that your IT department might manage are:</span></span>

-   <span data-ttu-id="a7509-128">Intune Managed Browser</span><span class="sxs-lookup"><span data-stu-id="a7509-128">Intune Managed Browser</span></span>

-   <span data-ttu-id="a7509-129">Intune Image Viewer</span><span class="sxs-lookup"><span data-stu-id="a7509-129">Intune image Viewer</span></span>

-   <span data-ttu-id="a7509-130">Intune PDF Viewer</span><span class="sxs-lookup"><span data-stu-id="a7509-130">Intune PDF Viewer</span></span>

-   <span data-ttu-id="a7509-131">Intune AV Player</span><span class="sxs-lookup"><span data-stu-id="a7509-131">Intune AV player</span></span>

-   <span data-ttu-id="a7509-132">Microsoft Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a7509-132">Microsoft Word, Excel, and PowerPoint</span></span>

<span data-ttu-id="a7509-133">デバイスの管理対象アプリの詳細については、会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="a7509-133">Contact your company support for more information about the managed apps on your device.</span></span> <span data-ttu-id="a7509-134">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="a7509-134">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
