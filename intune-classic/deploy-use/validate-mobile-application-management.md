---
title: "MAM 設定を確認する"
description: "このトピックでは、MAM ポリシーが正しく設定され、想定通りに動作するかをテストし、確認する方法を説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.custom: intune-classic
ms.openlocfilehash: fcb58f91fac727475a611f613db236384899d209
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="validating-your-mobile-application-management-setup"></a><span data-ttu-id="cac69-103">モバイル アプリケーション管理のセットアップの検証</span><span class="sxs-lookup"><span data-stu-id="cac69-103">Validating your mobile application management setup</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="cac69-104">このトピックでは、モバイル アプリケーション管理 (MAM) を設定した後の問題の確認について説明します。</span><span class="sxs-lookup"><span data-stu-id="cac69-104">This topic provides information on checking for issues after you set up mobile application management (MAM).</span></span> <span data-ttu-id="cac69-105">このガイドは、Azure Portal の MAM ポリシーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cac69-105">This guidance applies to MAM policies in the Azure portal.</span></span>

### <a name="checking-for-symptoms"></a><span data-ttu-id="cac69-106">現象の確認</span><span class="sxs-lookup"><span data-stu-id="cac69-106">Checking for symptoms</span></span>
<span data-ttu-id="cac69-107">MAM はデータ保護ツールであるため、ユーザーが問題を報告しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cac69-107">Users are unlikely to report issues since MAM is a data protection tool.</span></span> <span data-ttu-id="cac69-108">MAM の構成に問題がある場合でも、MAM がない場合と同じようにユーザーはアクセスに制限を受けず、問題が発生していることに気付かない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cac69-108">If there is a problem with the MAM configuration the user will have unrestricted access, as they would have without MAM, and would not be aware that there is an issue.</span></span> <span data-ttu-id="cac69-109">このため、MAM の制限を意図的にテストできるユーザーの小規模なグループに MAM ポリシーをパイロット運用して、MAM 構成を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cac69-109">For this reason we recommend that you validate your MAM configuration by piloting your MAM policies with a small group of users who can deliberately test the MAM restrictions.</span></span>


### <a name="what-to-check"></a><span data-ttu-id="cac69-110">確認項目</span><span class="sxs-lookup"><span data-stu-id="cac69-110">What to check</span></span>

<span data-ttu-id="cac69-111">テストの結果、MAM ポリシーの動作が予想通りではない場合は、以下の内容を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cac69-111">If testing shows that your MAM policy behavior is not as anticipated, we recommend that you check the following:</span></span>

- <span data-ttu-id="cac69-112">ユーザーは MAM のライセンスを取得していますか。</span><span class="sxs-lookup"><span data-stu-id="cac69-112">Are the users licensed for MAM?</span></span>
- <span data-ttu-id="cac69-113">ユーザーは O365 のライセンスを取得していますか。</span><span class="sxs-lookup"><span data-stu-id="cac69-113">Are the users licensed for O365?</span></span>
- <span data-ttu-id="cac69-114">各ユーザーの MAM アプリの状態。</span><span class="sxs-lookup"><span data-stu-id="cac69-114">The status of each of the users' MAM apps.</span></span> <span data-ttu-id="cac69-115">アプリの状態は、**[確認済み]** か **[未確認]** のはずです。</span><span class="sxs-lookup"><span data-stu-id="cac69-115">The possible statuses for the apps are **Checked in** and **Not checked in**.</span></span>

#### <a name="user-mam-status"></a><span data-ttu-id="cac69-116">ユーザーの MAM の状態</span><span class="sxs-lookup"><span data-stu-id="cac69-116">User MAM status</span></span>
1. <span data-ttu-id="cac69-117">Azure Portal で、**[Intune mobile application management (Intune モバイル アプリケーション管理)]** > **[設定]** > **[アプリ管理]** > **[すべての設定]** > **[App reporting by user (ユーザーによるアプリ レポート)]** > **[ユーザー]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cac69-117">In the Azure portal choose **Intune mobile application management** > **settings** > **app management** > **All settings** > **App reporting by user** > **users**.</span></span>

2. <span data-ttu-id="cac69-118">一覧からユーザーを選択または検索し、ユーザーを選択して、**[ユーザーの選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cac69-118">Choose a user from the list or search for and choose a user, then choose **Select user**.</span></span> <span data-ttu-id="cac69-119">**アプリ レポート**列の最上部で、ユーザーが MAM のライセンスを取得しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="cac69-119">At the top of the **App reporting** column you will see whether the user is licensed for MAM.</span></span> <span data-ttu-id="cac69-120">その下に、ユーザーが O365 のライセンスを取得しているかどうか、またすべてのユーザーのデバイスのアプリの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cac69-120">Below that you will see whether the user is licensed for O365 and the app status for all of the user's devices.</span></span>

![MAM のアプリの状態](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a><span data-ttu-id="cac69-122">対処</span><span class="sxs-lookup"><span data-stu-id="cac69-122">What to do</span></span>
<span data-ttu-id="cac69-123">ユーザーの状態に基づいて実行するアクションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cac69-123">Here are the actions to take based on the user status:</span></span>

- <span data-ttu-id="cac69-124">ユーザーが MAM のライセンスを取得していない場合、「[Intune のライセンスを管理する](/intune/setup-steps)」の説明に従って、ユーザーに Intune のライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cac69-124">If the user is not licensed for MAM, assign an Intune license to the user as described in [Manage Intune licenses](/intune/setup-steps).</span></span>
- <span data-ttu-id="cac69-125">ユーザーが O365 のライセンスを取得していない場合、ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cac69-125">If the user is not licensed for O365 obtain a license for the user.</span></span>
- <span data-ttu-id="cac69-126">ユーザーのアプリが **[未確認]** として一覧表示される場合、そのアプリの MAM ポリシーを正しく構成したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="cac69-126">If a user's app is listed as **Not checked in**, check if you've correctly configured a MAM policy for that app.</span></span>
- <span data-ttu-id="cac69-127">MAM ポリシーを適用するすべてのユーザーに、これらの条件が適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cac69-127">Ensure that these conditions are applied across all users to which you want MAM policies to apply.</span></span>

### <a name="see-also"></a><span data-ttu-id="cac69-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="cac69-128">See also</span></span>
[<span data-ttu-id="cac69-129">Microsoft Intune でのモバイル アプリ管理ポリシーの作成および展開</span><span class="sxs-lookup"><span data-stu-id="cac69-129">Get ready to configure mobile app management policies with Microsoft Intune</span></span>](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[<span data-ttu-id="cac69-130">Microsoft Intune でモバイル アプリケーション管理ポリシーを使用してデータを保護する</span><span class="sxs-lookup"><span data-stu-id="cac69-130">Protect app data using mobile app management policies with Microsoft Intune</span></span>](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
