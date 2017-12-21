---
title: "Intune に Windows 10 デバイスを登録する | Microsoft Docs"
description: "Intune に Windows 10 1511 デバイスを登録する"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 43b738b7-6a56-498a-a433-112da5104876
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 3c110bab95cbdb7c0dbe3fbe47d34b4cad5aaf07
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-your-windows-10-device-in-intune"></a><span data-ttu-id="38e99-103">Intune に Windows 10 デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="38e99-103">Enroll your Windows 10 device in Intune</span></span>

  > [!NOTE]
  > <span data-ttu-id="38e99-104">Windows 10 はあらゆる種類のデバイスで動作します。</span><span class="sxs-lookup"><span data-stu-id="38e99-104">Windows 10 works across all types of devices.</span></span> <span data-ttu-id="38e99-105">デスクトップ、スマートフォン、タブレットのいずれを使用している場合でも、このページの画像とは少し違う部分があるかもしれませんが、手順は同じです。</span><span class="sxs-lookup"><span data-stu-id="38e99-105">Whether you're using a desktop, phone, or tablet, the steps you follow are the same - even if they look slightly different from the images on this page.</span></span>

1.  <span data-ttu-id="38e99-106">**[スタート]** メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="38e99-106">Go to **Start**.</span></span>

  - <span data-ttu-id="38e99-107">**Windows 10 デスクトップ** デバイスを使用している場合は、**[スタート] メニュー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="38e99-107">If you are on a **Windows 10 desktop** device, go to the **Start menu**.</span></span>
  - <span data-ttu-id="38e99-108">**Windows 10 Mobile** デバイスを使用している場合は、**[スタート]** 画面に移動し、スワイプして **[すべてのアプリ]** リストを表示します。</span><span class="sxs-lookup"><span data-stu-id="38e99-108">If you are on a **Windows 10 Mobile** device, go to the **Start screen**, then swipe to the **All Apps** list.</span></span>

2. <span data-ttu-id="38e99-109">検索バーで「設定」を検索して、Windows の **[設定]** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="38e99-109">Open the Windows **Settings** app by searching for "settings" in the search bar.</span></span>

3. <span data-ttu-id="38e99-110">**[アカウント]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38e99-110">Select **Accounts**.</span></span>

    ![[設定] と [アカウント] に移動する](./media/W10-enroll-1-settings-accounts.png)

4. <span data-ttu-id="38e99-112">**[お使いのアカウント]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38e99-112">Select **Your account**.</span></span>

    ![[お使いのアカウント] を選択する](./media/W10-enroll-2-accounts-your-account.png)

5. <span data-ttu-id="38e99-114">**[職場または学校アカウントを追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38e99-114">Select **Add a work or school account**.</span></span>

    ![[職場または学校アカウントを追加] を選択する](./media/w10-enroll-3-add-work-school-acct.png)

6. <span data-ttu-id="38e99-116">職場または学校の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="38e99-116">Sign in with your work or school credentials.</span></span>

    ![サインイン](./media/W10-enroll-4-sign-in.png)

<span data-ttu-id="38e99-118">それでも職場または学校の電子メール、ファイルなどのデータにアクセスできない場合は、</span><span class="sxs-lookup"><span data-stu-id="38e99-118">Still can't access your work or school email, files, or other data?</span></span> <span data-ttu-id="38e99-119">「[[お使いのアカウント] が表示されている場合のトラブルシューティング手順](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account)」を参照してアクセスを解決してください。</span><span class="sxs-lookup"><span data-stu-id="38e99-119">Try to fix your access by [troubleshooting issues with your account](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account).</span></span> <span data-ttu-id="38e99-120">それでも解決しない場合は、会社のサポートにサポートを依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38e99-120">If it still doesn't work, you'll need to contact your company support for further help.</span></span>

<span data-ttu-id="38e99-121">会社のサポートのサポートを受けるには、ポータル サイト アプリに表示されている連絡先情報を使用するのが簡単です。ポータル サイト アプリでは、日常の作業に推奨されるアプリや必要なアプリを探してダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="38e99-121">An easy way to get help from your company support is through the contact information available in the Company Portal app, which also lets you find and download recommended and required apps for your daily work.</span></span> <span data-ttu-id="38e99-122">デバイスにはポータル サイト アプリが既にインストールされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38e99-122">It's possible that you already have the Company Portal app installed on your device.</span></span> <span data-ttu-id="38e99-123">[__すべてのアプリ__] リストで [__ポータル サイト__] を探すのが簡単な確認方法です。</span><span class="sxs-lookup"><span data-stu-id="38e99-123">A quick way to check is to look for __Company Portal__ in your __All apps__ list.</span></span>

<span data-ttu-id="38e99-124">アプリの一覧で、[ポータル サイト] が表示されない場合は、次の手順に従ってインストールします。</span><span class="sxs-lookup"><span data-stu-id="38e99-124">If you don't see the Company Portal in your list of apps, follow these steps to install it.</span></span>

1. <span data-ttu-id="38e99-125">**[スタート]** > **[ストア]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="38e99-125">Select **Start** > **Store**.</span></span>

2. <span data-ttu-id="38e99-126">**[検索]** を選択し、「**ポータル サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="38e99-126">Select **Search**, and then type **company portal**.</span></span>

3. <span data-ttu-id="38e99-127">結果のリストで、**[ポータル サイト]** > **[インストール]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="38e99-127">In the list of results, select **Company Portal** > **Install**.</span></span>

4. <span data-ttu-id="38e99-128">**[インストール]** または **[無料]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38e99-128">Select either **Install** or **Free**.</span></span> <span data-ttu-id="38e99-129">これら 2 つのオプションに違いはありません。表示される選択肢は、組織がポータル サイト アプリを設定した方法によって変わります。</span><span class="sxs-lookup"><span data-stu-id="38e99-129">There is no difference between these two options for you; the choice that is shown depends on how your organization set up the Company Portal app.</span></span>
