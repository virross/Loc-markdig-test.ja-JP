---
title: "ポリシーとアプリを展開する"
description: "ポリシー設定を有効にし、デバイスが管理に登録されたらすぐに適用されるアプリを展開することができます。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2d63450736391b5064a7e20ac57588cdc82f9068
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="create-policies-and-publish-apps"></a><span data-ttu-id="44cca-103">ポリシーを作成してアプリを発行する</span><span class="sxs-lookup"><span data-stu-id="44cca-103">Create policies and publish apps</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="44cca-104">このトピックでは、Intune 管理者がポリシーを作成し、アプリを発行した後、管理対象デバイスにデプロイする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="44cca-104">This topic tells Intune administrators how they can create policies and publish apps that they can then deploy to managed devices.</span></span>

<span data-ttu-id="44cca-105">Intune へのアプリの登録を開始する前に、ポリシー設定とアプリを有効にします。アプリは、デバイスが管理対象になるとすぐに展開されます。</span><span class="sxs-lookup"><span data-stu-id="44cca-105">Before you start enrolling apps into Intune, you can enable policy settings and apps that will be deployed as soon as those devices come into management.</span></span> <span data-ttu-id="44cca-106">モバイル デバイスのセキュリティ設定を制御したり、コンピューターの Windows ファイアウォールや Endpoint Protection の設定を管理したり、アプリケーションを展開したりする作業は、Intune のポリシー設定を使用して効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="44cca-106">Intune policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications.</span></span> <span data-ttu-id="44cca-107">ポリシーを構成し、アプリを追加して展開し、Intune に登録されたらすぐにデバイスが設定とアプリを受信するようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="44cca-107">You can configure policy, add apps, and deploy those apps so that devices receive settings and apps as soon as they enroll in Intune.</span></span>

<span data-ttu-id="44cca-108">ポリシーとアプリはプラットフォームに固有です。</span><span class="sxs-lookup"><span data-stu-id="44cca-108">Policies and apps are platform-specific.</span></span>

## <a name="manage-device-settings"></a><span data-ttu-id="44cca-109">デバイス設定の管理</span><span class="sxs-lookup"><span data-stu-id="44cca-109">Manage device settings</span></span>

 <span data-ttu-id="44cca-110">デバイス ポリシー設定は、プラットフォームごとに構成され、管理されます。</span><span class="sxs-lookup"><span data-stu-id="44cca-110">Device policy settings are configured and managed on a per-platform basis.</span></span> <span data-ttu-id="44cca-111">次のリンクは、それぞれのプラットフォームで使用できる設定の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="44cca-111">The following links provide lists of available settings for their respective platforms:</span></span>

- [<span data-ttu-id="44cca-112">Android</span><span class="sxs-lookup"><span data-stu-id="44cca-112">iOS</span></span>](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="44cca-113">Android および Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="44cca-113">Android and Samsung KNOX Standard</span></span>](/intune-classic/deploy-use/android-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="44cca-114">Android for Work</span><span class="sxs-lookup"><span data-stu-id="44cca-114">Android for Work</span></span>](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="44cca-115">Windows 10 (PC とモバイル)</span><span class="sxs-lookup"><span data-stu-id="44cca-115">Windows 10  (PC and mobile)</span></span>](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="44cca-116">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="44cca-116">Windows 8.1</span></span>](/intune-classic/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="44cca-117">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="44cca-117">Windows Phone 8.1</span></span>](/intune-classic/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="44cca-118">Windows チーム</span><span class="sxs-lookup"><span data-stu-id="44cca-118">Windows Team</span></span>](/intune-classic/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="44cca-119">Intune クライアント ソフトウェアを実行している Windows PC</span><span class="sxs-lookup"><span data-stu-id="44cca-119">Windows PCs running Intune software client</span></span>](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

<span data-ttu-id="44cca-120">詳細については、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44cca-120">You can learn more about how to [Manage settings and features on your devices with Microsoft Intune policies](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).</span></span>

## <a name="add-and-deploy-apps"></a><span data-ttu-id="44cca-121">アプリを追加して展開する</span><span class="sxs-lookup"><span data-stu-id="44cca-121">Add and deploy apps</span></span>

<span data-ttu-id="44cca-122">Intune にアプリを追加した後で、次の 2 つの方法で管理対象アプリに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="44cca-122">You can add apps to Intune and then deploy them to managed devices in two ways:</span></span>
- <span data-ttu-id="44cca-123">**必須のインストール** - アプリを自動的に管理対象デバイスにインストールします。</span><span class="sxs-lookup"><span data-stu-id="44cca-123">**Required install** - Apps automatically installs the app to managed devices</span></span>
- <span data-ttu-id="44cca-124">**利用可能なインストール** - ユーザーがデバイスにインストールするかどうかを選択できるように、Intune ポータル サイトにアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44cca-124">**Available install** - Apps appear in the Intune Company Portal so that users can choose whether to install them on their devices</span></span>

### <a name="add-apps"></a><span data-ttu-id="44cca-125">アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="44cca-125">Add apps</span></span>

<span data-ttu-id="44cca-126">まず、次のいずれかの方法で、アプリを Intune で使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="44cca-126">First you must make apps available in Intune by one of the following methods:</span></span>
- [<span data-ttu-id="44cca-127">登録デバイスのアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="44cca-127">Add apps for enrolled devices</span></span>](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [<span data-ttu-id="44cca-128">Intune ソフトウェア クライアント PC のアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="44cca-128">Add apps for Intune software client PCs</span></span>](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a><span data-ttu-id="44cca-129">アプリの展開</span><span class="sxs-lookup"><span data-stu-id="44cca-129">Deploy apps</span></span>

<span data-ttu-id="44cca-130">これで、アプリが Intune で使用できるようになりました。管理対象デバイスに展開できます。</span><span class="sxs-lookup"><span data-stu-id="44cca-130">Now that the app is availabile in Intune, you can deploy it to managed devices:</span></span>
- [<span data-ttu-id="44cca-131">デバイスにアプリを展開する</span><span class="sxs-lookup"><span data-stu-id="44cca-131">Deploy apps to devices</span></span>](/intune-classic/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- <span data-ttu-id="44cca-132">以下のボリューム購入アプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="44cca-132">Deploy volume-purchased apps:</span></span>
  - [<span data-ttu-id="44cca-133">iOS - ボリューム購入プログラム</span><span class="sxs-lookup"><span data-stu-id="44cca-133">iOS - Volume-purchase Program</span></span>](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
  - [<span data-ttu-id="44cca-134">ビジネス向け Microsoft ストア</span><span class="sxs-lookup"><span data-stu-id="44cca-134">Microsoft Store for Business</span></span>](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
  - [<span data-ttu-id="44cca-135">Android for Work</span><span class="sxs-lookup"><span data-stu-id="44cca-135">Android for Work</span></span>](/intune-classic/deploy-use/android-for-work-apps)

    <span data-ttu-id="44cca-136">展開用にアプリを構成したら、[アプリを構成](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)できます。</span><span class="sxs-lookup"><span data-stu-id="44cca-136">Once you have configured apps for deployment you can [configure apps](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).</span></span>

> [!div class="step-by-step"]
> 
> <span data-ttu-id="44cca-137">[&larr;**ユーザーとデバイスを整理する**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**ポータル サイトをカスタマイズする** &rarr;](/intune/company-portal-customize)</span><span class="sxs-lookup"><span data-stu-id="44cca-137">[&larr; **Organize users and devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Customize Company Portal** &rarr;](/intune/company-portal-customize)</span></span>  
