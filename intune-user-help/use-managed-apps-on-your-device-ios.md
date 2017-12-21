---
title: "iOS デバイスで管理対象アプリを使用する | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3232c5c1-cb9f-45ca-806f-7e74eeb3533e
searchScope: User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 8c3d9285408f2cfa394ed31ec36fcaea47306eb5
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="use-managed-apps-on-your-ios-device"></a><span data-ttu-id="f85a0-102">iOS デバイスで管理対象アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="f85a0-102">Use managed apps on your iOS device</span></span>

<span data-ttu-id="f85a0-103">管理対象アプリとは、そのアプリでアクセス可能な会社のデータを保護できるよう会社のサポートがセットアップ可能なアプリです。</span><span class="sxs-lookup"><span data-stu-id="f85a0-103">Managed apps are apps that your company support can set up to help protect company data that you can access in that app.</span></span> <span data-ttu-id="f85a0-104">管理対象アプリ内の会社のデータに iOS デバイスでアクセスする場合、アプリの動作が予期したものとは少し異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f85a0-104">When you access company data in a managed app on your iOS device, you may notice that the app works a little differently than what you expect.</span></span> <span data-ttu-id="f85a0-105">たとえば、保護された会社のデータをコピーして貼り付けできない、またはそのデータを特定の場所に保存できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f85a0-105">For example, you might not be able to copy and paste protected company data, or you might not be able to save that data to certain locations.</span></span>

<span data-ttu-id="f85a0-106">また、異なる管理対象アプリがデバイス上で連携して動作し、会社のデータを保護しながら、日常のタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f85a0-106">Different managed apps can also work together on your device to allow you to do your daily tasks, while keeping corporate data protected.</span></span> <span data-ttu-id="f85a0-107">たとえば、1 つの管理対象アプリで会社のファイルを開き、別の管理対象アプリでそのファイルを表示する必要がある場合、ファイルを表示できるようにする管理対象アプリが自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="f85a0-107">For example, if you open a company file in one managed app, and another managed app is required to view that file, the managed app that allows you to view the file opens automatically.</span></span> <span data-ttu-id="f85a0-108">必要なアプリが使用できない場合、管理されているドキュメント内からドキュメントを開くまたは Web リンクにアクセスするなどの特定の操作が行えない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f85a0-108">If a required app is not available, certain actions, like opening a document or accessing a web link from within a managed document, might not be available.</span></span>

<span data-ttu-id="f85a0-109">管理対象アプリで会社のデータにアクセスすると、開こうとしているアプリが管理されていることを通知する以下のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f85a0-109">When you access company data in a managed app, you see a message like the one below, which lets you know that the app you are opening is managed.</span></span>

![managed-apps-message-ios](./media/managed-apps-message.png)

### <a name="how-do-i-get-managed-apps"></a><span data-ttu-id="f85a0-111">管理対象アプリを取得する方法</span><span class="sxs-lookup"><span data-stu-id="f85a0-111">How do I get managed apps?</span></span>
<span data-ttu-id="f85a0-112">管理対象アプリはいくつかの方法で取得できます。</span><span class="sxs-lookup"><span data-stu-id="f85a0-112">You get managed apps in a couple of different ways:</span></span>

-   <span data-ttu-id="f85a0-113">デバイスが Microsoft Intune に登録されるときに、ポータル サイト アプリまたはポータル Web サイトからアプリをインストールするか、または会社のサポートがアプリをデバイスにインストールする場合があります。</span><span class="sxs-lookup"><span data-stu-id="f85a0-113">When your device is enrolled in Microsoft Intune, you either install the app from your Company Portal app or Company Portal website, or your company support might install it on your device.</span></span> <span data-ttu-id="f85a0-114">登録については、「[Intune に iOS デバイスを登録する](enroll-your-device-in-intune-ios.md)」または「[Intune に macOS デバイスを登録する](enroll-your-device-in-intune-macos.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f85a0-114">To learn about enrolling, see [Enroll your iOS device in Intune](enroll-your-device-in-intune-ios.md) or [Enroll your macOS device in Intune](enroll-your-device-in-intune-macos.md).</span></span>

-   <span data-ttu-id="f85a0-115">アプリ ストアからアプリをインストールし、Intune で管理されている会社のユーザー アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="f85a0-115">You install an app from the App Store, and then sign in with your corporate user account that is managed by Intune.</span></span>

<span data-ttu-id="f85a0-116">会社のサポートは、ユーザーがインストールするアプリ用に複数のライセンスを購入している場合があります。</span><span class="sxs-lookup"><span data-stu-id="f85a0-116">Your company support might sometimes purchase multiple licenses for an app you install.</span></span> <span data-ttu-id="f85a0-117">Apple Volume Purchase Program 契約の同意を求めるメッセージが表示された場合、これは正常であり、同意することができます。</span><span class="sxs-lookup"><span data-stu-id="f85a0-117">If you see a message asking you to accept the Apple Volume Purchase Program agreement, this is normal, and you can accept it.</span></span> <span data-ttu-id="f85a0-118">同意しない場合は、アプリをインストールすることができません。</span><span class="sxs-lookup"><span data-stu-id="f85a0-118">If you don’t accept it, you won’t be able to install the app.</span></span>

### <a name="what-can-my-company-support-manage-in-an-app"></a><span data-ttu-id="f85a0-119">会社のサポートがアプリで管理できるもの</span><span class="sxs-lookup"><span data-stu-id="f85a0-119">What can my company support manage in an app?</span></span>
<span data-ttu-id="f85a0-120">以下は、会社のサポートがアプリで管理でき、デバイス上での会社データとのやり取りに影響するオプションの例です。</span><span class="sxs-lookup"><span data-stu-id="f85a0-120">Here are some examples of options that your company support can manage in an app, and that can affect your interactions with company data on your device:</span></span>

-   <span data-ttu-id="f85a0-121">特定の web サイトへのアクセス</span><span class="sxs-lookup"><span data-stu-id="f85a0-121">Access to specific websites</span></span>

-   <span data-ttu-id="f85a0-122">アプリケーション間のデータ転送</span><span class="sxs-lookup"><span data-stu-id="f85a0-122">Transfers of data between apps</span></span>

-   <span data-ttu-id="f85a0-123">ファイルの保存</span><span class="sxs-lookup"><span data-stu-id="f85a0-123">Saving files</span></span>

-   <span data-ttu-id="f85a0-124">コピーと貼り付けの操作</span><span class="sxs-lookup"><span data-stu-id="f85a0-124">Copy and paste operations</span></span>

-   <span data-ttu-id="f85a0-125">暗証番号 (pin) のアクセスの要件</span><span class="sxs-lookup"><span data-stu-id="f85a0-125">PIN access requirements</span></span>

-   <span data-ttu-id="f85a0-126">会社の資格情報を使用したサインイン</span><span class="sxs-lookup"><span data-stu-id="f85a0-126">Your sign in, using company credentials</span></span>

-   <span data-ttu-id="f85a0-127">クラウドへのバックアップ機能</span><span class="sxs-lookup"><span data-stu-id="f85a0-127">Ability to back up to the cloud</span></span>

-   <span data-ttu-id="f85a0-128">スクリーン ショットを撮る機能</span><span class="sxs-lookup"><span data-stu-id="f85a0-128">Ability to take screenshots</span></span>

-   <span data-ttu-id="f85a0-129">データの暗号化の要件</span><span class="sxs-lookup"><span data-stu-id="f85a0-129">Data encryption requirements</span></span>

<span data-ttu-id="f85a0-130">デバイスの管理対象アプリの詳細については、会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f85a0-130">Contact your company support for more information about the managed apps on your device.</span></span> <span data-ttu-id="f85a0-131">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f85a0-131">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
