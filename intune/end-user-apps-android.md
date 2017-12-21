---
title: "Android ユーザーがアプリを入手する方法"
description: "エンド ユーザーが Android アプリを入手する方法"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 056e11814d3e92462c8451df2f1df36fc6037e38
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-your-android-users-get-their-apps"></a><span data-ttu-id="fc30a-103">Android ユーザーがアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="fc30a-103">How your Android users get their apps</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="fc30a-104">Microsoft Intune を通して配布したアプリを Android エンド ユーザーがどこでどのように取得するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fc30a-104">Use this information to understand how and where your Android end users get the apps that you distribute through Microsoft Intune.</span></span> <span data-ttu-id="fc30a-105">この情報はデバイスの種類 (Android ネイティブ デバイスや Samsung Knox Standard デバイス) によって異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fc30a-105">The information can vary by device type (native Android devices or Samsung Knox Standard devices).</span></span>

## <a name="native-non-samsung-knox-standard-android-devices"></a><span data-ttu-id="fc30a-106">ネイティブ (Samsung KNOX Standard 以外) Android デバイス</span><span class="sxs-lookup"><span data-stu-id="fc30a-106">Native (non-Samsung Knox Standard) Android devices</span></span>

| <span data-ttu-id="fc30a-107">アプリの種類</span><span class="sxs-lookup"><span data-stu-id="fc30a-107">App type</span></span> | <span data-ttu-id="fc30a-108">基幹業務 (LOB) アプリ</span><span class="sxs-lookup"><span data-stu-id="fc30a-108">Line-of-business (LOB) apps</span></span> | <span data-ttu-id="fc30a-109">Play ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="fc30a-109">Play Store apps</span></span>  |
| ------------- |-------------| -----|
| <span data-ttu-id="fc30a-110">Available apps</span><span class="sxs-lookup"><span data-stu-id="fc30a-110">Available apps</span></span>      | <span data-ttu-id="fc30a-111">ポータル サイトで **[インストール]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="fc30a-111">Users tap **install** in the Company Portal.</span></span> <span data-ttu-id="fc30a-112">通知が表示されます。この通知をタップしてインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="fc30a-112">A notification appears, which users then tap to start the installation.</span></span> <span data-ttu-id="fc30a-113">インストールが成功すると、通知は表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="fc30a-113">After the installation is successful, the notification disappears.</span></span> | <span data-ttu-id="fc30a-114">ポータル サイトでアプリをタップすると、Play ストアでアプリのページが表示され、インストールを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="fc30a-114">Users tap the app in the Company Portal and are taken to an app page in the Play Store, where they can start the installation.</span></span>|
| <span data-ttu-id="fc30a-115">Required apps</span><span class="sxs-lookup"><span data-stu-id="fc30a-115">Required apps</span></span>      | <span data-ttu-id="fc30a-116">アプリをインストールする必要があることを示す通知が表示されます。この通知は非表示にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fc30a-116">Users are shown a notification, which they cannot dismiss, indicating that they need to install an app.</span></span> <span data-ttu-id="fc30a-117">通知をタップしてインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="fc30a-117">Users tap the notification to start the installation.</span></span> <span data-ttu-id="fc30a-118">インストールが成功すると、通知は表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="fc30a-118">After the installation is successful, the notification disappears.</span></span>    | <span data-ttu-id="fc30a-119">アプリをインストールする必要があることを示す通知が表示されます。この通知は非表示にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fc30a-119">Users are shown a notification, which they cannot dismiss, indicating that they need to install an app.</span></span> <span data-ttu-id="fc30a-120">通知をタップすると、Play ストアのアプリのページが表示され、インストールを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="fc30a-120">Users tap the notification and are taken to an app page in the Play Store, where they can start the installation.</span></span> <span data-ttu-id="fc30a-121">インストールが成功すると、通知は表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="fc30a-121">After the installation is successful, the notification disappears.</span></span> |

<span data-ttu-id="fc30a-122">[LOB アプリ](lob-apps-android.md)をインストールするには、エンド ユーザーは、不明なソースからのインストールを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc30a-122">Your end users need to allow installation from unknown sources in order to install [LOB apps](lob-apps-android.md).</span></span> <span data-ttu-id="fc30a-123">通常、設定には 2 つの場所があります。</span><span class="sxs-lookup"><span data-stu-id="fc30a-123">These are normally found in two different places:</span></span>

* <span data-ttu-id="fc30a-124">**Android 7.1.2 以前**: **[設定]** > **[セキュリティ]** > **[不明なソース]**</span><span class="sxs-lookup"><span data-stu-id="fc30a-124">**Android 7.1.2 and lower**: **Settings** > **Security** > **Unknown sources**</span></span>
* <span data-ttu-id="fc30a-125">**Android 8.0 以降**: **[設定]** > **[Apps & notifications]\(アプリと通知\)** > **[Special app access]\(特別なアプリ アクセス\)** > **[Install unknown apps]\(不明なアプリのインストール\)** > **[ポータル サイト]** > **[Allow from this source]\(このソースからは許可する\)**</span><span class="sxs-lookup"><span data-stu-id="fc30a-125">**Android 8.0 and above**: **Settings** > **Apps & notifications** > **Special app access** > **Install unknown apps** > **Company Portal** > **Allow from this source**</span></span>

<span data-ttu-id="fc30a-126">許可が必要になった場合、ポータル サイト アプリがエンド ユーザーに通知し、該当する設定画面まで直接誘導します。</span><span class="sxs-lookup"><span data-stu-id="fc30a-126">If this occurs, the Company Portal app will inform and directly guide the end user to the appropriate setting.</span></span> 


## <a name="samsung-knox-standard-android-devices"></a><span data-ttu-id="fc30a-127">Samsung KNOX Standard Android デバイス</span><span class="sxs-lookup"><span data-stu-id="fc30a-127">Samsung Knox Standard Android devices</span></span>

| <span data-ttu-id="fc30a-128">アプリの種類</span><span class="sxs-lookup"><span data-stu-id="fc30a-128">App type</span></span> | <span data-ttu-id="fc30a-129">基幹業務 (LOB) アプリ</span><span class="sxs-lookup"><span data-stu-id="fc30a-129">Line-of-business (LOB) apps</span></span> | <span data-ttu-id="fc30a-130">Play ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="fc30a-130">Play Store apps</span></span>  |
| ------------- |-------------| -----|
| <span data-ttu-id="fc30a-131">Available apps</span><span class="sxs-lookup"><span data-stu-id="fc30a-131">Available apps</span></span>      | <span data-ttu-id="fc30a-132">ポータル サイトで **[インストール]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="fc30a-132">Users tap **install** in the Company Portal.</span></span> <span data-ttu-id="fc30a-133">アプリがインストールされます。ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="fc30a-133">The app installs without further user intervention.</span></span> | <span data-ttu-id="fc30a-134">ポータル サイトでアプリをタップすると、Play ストアでアプリのページが表示され、インストールを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="fc30a-134">Users tap the app in the Company Portal and are taken to an app page in the Play Store, where they can start the installation.</span></span>|
| <span data-ttu-id="fc30a-135">Required apps</span><span class="sxs-lookup"><span data-stu-id="fc30a-135">Required apps</span></span>      | <span data-ttu-id="fc30a-136">アプリがインストールされます。ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="fc30a-136">The app is installed without any user intervention.</span></span>    | <span data-ttu-id="fc30a-137">アプリをインストールする必要があることを示す通知が表示されます。この通知は非表示にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fc30a-137">Users are shown a notification, which they cannot dismiss, indicating that they need to install an app.</span></span> <span data-ttu-id="fc30a-138">通知をタップすると、Play ストアのアプリのページが表示され、インストールを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="fc30a-138">Users tap the notification and are taken to an app page in the Play Store, where they can start the installation.</span></span> <span data-ttu-id="fc30a-139">インストールが成功すると、通知は表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="fc30a-139">After the installation is successful, the notification disappears.</span></span> |

<span data-ttu-id="fc30a-140">アプリは、以下に示すように管理することも管理外にすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="fc30a-140">Apps can be managed or unmanaged, as described below.</span></span> <span data-ttu-id="fc30a-141">アプリを管理するプロセスは、すべての種類の Android デバイスで共通です。</span><span class="sxs-lookup"><span data-stu-id="fc30a-141">The process of making apps managed is the same for all types of Android devices.</span></span>

<span data-ttu-id="fc30a-142">**管理対象のアプリ** - ポリシーで管理できるアプリです。</span><span class="sxs-lookup"><span data-stu-id="fc30a-142">**Managed apps** - These are apps that can be managed through policies.</span></span> <span data-ttu-id="fc30a-143">Intune で "ラップ" されているか、Intune App SDK で構築されています。</span><span class="sxs-lookup"><span data-stu-id="fc30a-143">They have been "wrapped" by Intune or built with the Intune App SDK.</span></span> <span data-ttu-id="fc30a-144">これらのアプリは Intune によって管理することができます。また、これらのアプリにはアプリケーション ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="fc30a-144">These apps can be managed by Intune, and application policies can be applied to them.</span></span>

<span data-ttu-id="fc30a-145">**管理対象外のアプリ** - ポリシーで管理できないアプリです。</span><span class="sxs-lookup"><span data-stu-id="fc30a-145">**Unmanaged apps** - These are apps that cannot be managed through policies.</span></span> <span data-ttu-id="fc30a-146">Intune によってラップされていないか、Intune アプリ SDK を組み込んでいません。</span><span class="sxs-lookup"><span data-stu-id="fc30a-146">They have not been wrapped by Intune or do not incorporate the Intune App SDK.</span></span> <span data-ttu-id="fc30a-147">これらのアプリにアプリケーション ポリシーを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fc30a-147">Application policies cannot be applied to these apps.</span></span>

### <a name="see-also"></a><span data-ttu-id="fc30a-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc30a-148">See also</span></span>
[<span data-ttu-id="fc30a-149">Microsoft Intune でアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="fc30a-149">Add apps with Microsoft Intune</span></span>](apps-add.md)

[<span data-ttu-id="fc30a-150">iOS ユーザーがアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="fc30a-150">How your iOS users get their apps</span></span>](end-user-apps-ios.md)

[<span data-ttu-id="fc30a-151">Windows ユーザーがアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="fc30a-151">How your Windows users get their apps</span></span>](end-user-apps-windows.md)
