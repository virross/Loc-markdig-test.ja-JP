---
title: "アプリの概要"
titlesuffix: Azure portal
description: "社員が仕事を行えるように、アプリを見つけ、デバイスに追加します。"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89f3585b97bd1a074b45af815792ec4949215aab
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-adding-apps"></a><span data-ttu-id="370c5-103">アプリ追加の概要</span><span class="sxs-lookup"><span data-stu-id="370c5-103">Get started with adding apps</span></span>

<span data-ttu-id="370c5-104">Intune では、いくつかの方法で企業デバイスにアプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="370c5-104">Intune supports a few different ways for you to deploy apps to your corporate devices:</span></span>

* <span data-ttu-id="370c5-105">**ソフトウェア インストーラー**: ユーザーのデバイスにダウンロードされたファイルをアップロードします</span><span class="sxs-lookup"><span data-stu-id="370c5-105">**Software installers**: where you upload a file that is downloaded to your users' devices</span></span>
* <span data-ttu-id="370c5-106">__外部リンク__: パブリック アプリ ストアのアプリや Web アプリを持っている場合</span><span class="sxs-lookup"><span data-stu-id="370c5-106">__External links__: for when you have an app in a public app store or a webapp</span></span>
* <span data-ttu-id="370c5-107">**管理対象アプリ**: アプリ ストアで入手できるアプリに適用される付加的なモバイル アプリ管理を必要とする iOS デバイスの場合</span><span class="sxs-lookup"><span data-stu-id="370c5-107">**Managed apps**: for iOS devices where you need additional mobile application management applied to apps available in the App Store</span></span>

<span data-ttu-id="370c5-108">パブリック ストア アプリを割り当てることで、迅速なアプリケーション展開方法の 1 つを行います。</span><span class="sxs-lookup"><span data-stu-id="370c5-108">You’re going to go through one of the quicker application deployment methods by assigning a public store app.</span></span>

## <a name="how-do-i-assign-a-public-store-app"></a><span data-ttu-id="370c5-109">パブリック ストア アプリを割り当てる場合の操作方法</span><span class="sxs-lookup"><span data-stu-id="370c5-109">How do I assign a public store app?</span></span>

1. <span data-ttu-id="370c5-110">[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="370c5-110">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="370c5-111">**[リソースの検索]** を利用し、**[Intune]** を探します。</span><span class="sxs-lookup"><span data-stu-id="370c5-111">Using **Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="370c5-112">**[モバイル アプリ]** を選択し、**[アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="370c5-112">Select **Mobile Apps**, then select **Apps**.</span></span>
4. <span data-ttu-id="370c5-113">**[追加]** を選択し、**[アプリの種類]** として **[ストア アプリ]** の **[iOS]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="370c5-113">Select **Add**, then select **iOS** under **Store app** as the **App type**.</span></span>
5. <span data-ttu-id="370c5-114">**[アプリの選択]** を選んで、**[アプリ ストアを検索します]** ブレードを表示します。</span><span class="sxs-lookup"><span data-stu-id="370c5-114">Choose **Select app** to display the **Search the App Store** blade.</span></span>
6. <span data-ttu-id="370c5-115">テキスト ボックスで、デバイスに割り当てるアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="370c5-115">In the text box, search for an app to assign to the device.</span></span> <span data-ttu-id="370c5-116">アプリを選び、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370c5-116">Choose the app, then click **Select**.</span></span>
7. <span data-ttu-id="370c5-117">**[アプリの追加]** ブレードで、**[アプリ情報]** を選択し、すべてのアプリ情報に入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="370c5-117">In the **Add app** blade, select **App information**, then make sure that all of the app information populated.</span></span> <span data-ttu-id="370c5-118">このアプリの整理に役立つように他の任意詳細を追加できます。**所有者**、**メモ**、**開発者**、会社のプライバシー ポリシーの**プライバシー URL** などです。</span><span class="sxs-lookup"><span data-stu-id="370c5-118">You can add other optional details to help you organize this app, like **Owner**, **Notes**, **Developer**, and a **Privacy URL** for your company’s privacy policy.</span></span>
8. <span data-ttu-id="370c5-119">**[会社のポータルでおすすめアプリとして表示します]** に **[はい]** が選ばれていることを確認し、**[OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="370c5-119">Make sure that you’ve selected **Yes** for **Display this as a featured app in the Company Portal**, then select **OK**.</span></span>
9. <span data-ttu-id="370c5-120">**[アプリの追加]** ブレードで **[追加]** を選んで、アプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="370c5-120">Select **Add** from the **Add app** blade to add the app.</span></span> <span data-ttu-id="370c5-121">そのアプリの **[概要]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="370c5-121">This will take you to that app’s **Overview**.</span></span> <span data-ttu-id="370c5-122">**[割り当て]** を選択し、**[グループの選択]** をクリックしてそれをテスト グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="370c5-122">Choose **Assignments**, then click **Select groups** to assign it to your test group.</span></span> <span data-ttu-id="370c5-123">そのアプリをダウンロード**可能**にします。</span><span class="sxs-lookup"><span data-stu-id="370c5-123">Make the app **Available** for download.</span></span> <span data-ttu-id="370c5-124">これでテスト デバイスにそのアプリが**おすすめアプリ**として表示されます。</span><span class="sxs-lookup"><span data-stu-id="370c5-124">The app should then appear as a **Featured App** on your test device.</span></span>

## <a name="learn-more"></a><span data-ttu-id="370c5-125">詳細情報</span><span class="sxs-lookup"><span data-stu-id="370c5-125">Learn more</span></span>

* [<span data-ttu-id="370c5-126">Intune によるアプリ管理とは</span><span class="sxs-lookup"><span data-stu-id="370c5-126">What is app management with Intune?</span></span>](app-management.md)
* [<span data-ttu-id="370c5-127">アプリのライフサイクルの概要</span><span class="sxs-lookup"><span data-stu-id="370c5-127">Overview of the app lifecycle</span></span>](app-lifecycle.md)
* [<span data-ttu-id="370c5-128">アプリ保護ポリシーとは</span><span class="sxs-lookup"><span data-stu-id="370c5-128">What are app protection policies?</span></span>](app-protection-policy.md)
