---
title: "アプリ保護ポリシーを確認する"
titleSuffix: Azure portal
description: "このトピックでは、アプリ保護ポリシーが正しく設定され、想定通りに機能するかどうかをテストおよび検証する方法について説明します。\""
keywords: 
author: erikre
ms.author: erikre
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cc42f01352ffa94a62330f9863b7f97d9df23d78
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a><span data-ttu-id="edb1a-103">アプリ保護ポリシーの設定を検証する方法</span><span class="sxs-lookup"><span data-stu-id="edb1a-103">How to validate your app protection policy setup</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="edb1a-104">このトピックでは、アプリ保護ポリシーを設定した後に問題がないかどうかを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="edb1a-104">This topic provides information on checking for issues after you set up an app protection policy.</span></span> <span data-ttu-id="edb1a-105">このガイドは、Azure Portal のアプリ保護ポリシーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="edb1a-105">This guidance applies to app protection policies in the Azure portal.</span></span>

### <a name="checking-for-symptoms"></a><span data-ttu-id="edb1a-106">現象の確認</span><span class="sxs-lookup"><span data-stu-id="edb1a-106">Checking for symptoms</span></span>
<span data-ttu-id="edb1a-107">アプリ保護はデータ保護ツールであるため、ユーザーが問題を報告することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="edb1a-107">Users are unlikely to report issues since app protection is a data protection tool.</span></span> <span data-ttu-id="edb1a-108">アプリ保護の構成に問題があったとしても、アプリ保護がない場合と同じようにユーザーはアクセスに制限を受けないため、問題が発生していることにも気付きません。</span><span class="sxs-lookup"><span data-stu-id="edb1a-108">If there is a problem with the app protection configuration the user will have unrestricted access, as they would have without app protection, and would not be aware that there is an issue.</span></span> <span data-ttu-id="edb1a-109">このため、アプリ保護の制限を意図的にテストできるユーザーの小規模なグループでアプリ保護ポリシーをパイロット運用して、アプリ保護の構成を検証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="edb1a-109">For this reason we recommend that you validate your app protection configuration by piloting your app protection policies with a small group of users who can deliberately test the app protection restrictions.</span></span>


### <a name="what-to-check"></a><span data-ttu-id="edb1a-110">確認項目</span><span class="sxs-lookup"><span data-stu-id="edb1a-110">What to check</span></span>

<span data-ttu-id="edb1a-111">テストの結果、アプリ保護ポリシーの動作が期待どおりではない場合は、以下の内容を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="edb1a-111">If testing shows that your app protection policy behavior is not as anticipated, we recommend that you check the following:</span></span>

- <span data-ttu-id="edb1a-112">ユーザーはアプリ保護のライセンスを取得していますか。</span><span class="sxs-lookup"><span data-stu-id="edb1a-112">Are the users licensed for app protection?</span></span>
- <span data-ttu-id="edb1a-113">ユーザーは O365 のライセンスを取得していますか。</span><span class="sxs-lookup"><span data-stu-id="edb1a-113">Are the users licensed for O365?</span></span>
- <span data-ttu-id="edb1a-114">各ユーザーのアプリ保護アプリの状態。</span><span class="sxs-lookup"><span data-stu-id="edb1a-114">The status of each of the users' app protection apps.</span></span> <span data-ttu-id="edb1a-115">アプリの状態は、**[確認済み]** か **[未確認]** のはずです。</span><span class="sxs-lookup"><span data-stu-id="edb1a-115">The possible statuses for the apps are **Checked in** and **Not checked in**.</span></span>

#### <a name="user-app-protection-status"></a><span data-ttu-id="edb1a-116">ユーザーのアプリ保護の状態</span><span class="sxs-lookup"><span data-stu-id="edb1a-116">User app protection status</span></span>
1. <span data-ttu-id="edb1a-117">Azure Portal で、**[アプリの管理]** > **[監視]** >  **[アプリ保護ユーザー状態]** > **[ユーザー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="edb1a-117">In the Azure portal choose **Manage apps** > **Monitor** >  **App protection user status** > **users**.</span></span>

2. <span data-ttu-id="edb1a-118">一覧からユーザーを選択または検索し、ユーザーを選択して、**[ユーザーの選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="edb1a-118">Choose a user from the list or search for and choose a user, then choose **Select user**.</span></span> <span data-ttu-id="edb1a-119">**[アプリ レポート]** 列の最上部で、ユーザーがアプリ保護のライセンスを取得しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="edb1a-119">At the top of the **App reporting** column you will see whether the user is licensed for app protection.</span></span> <span data-ttu-id="edb1a-120">その下に、ユーザーが O365 のライセンスを取得しているかどうか、またすべてのユーザーのデバイスのアプリの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="edb1a-120">Below that you will see whether the user is licensed for O365 and the app status for all of the user's devices.</span></span>



### <a name="what-to-do"></a><span data-ttu-id="edb1a-121">対処</span><span class="sxs-lookup"><span data-stu-id="edb1a-121">What to do</span></span>
<span data-ttu-id="edb1a-122">ユーザーの状態に基づいて実行するアクションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="edb1a-122">Here are the actions to take based on the user status:</span></span>

- <span data-ttu-id="edb1a-123">ユーザーがアプリ保護のラインセンスを取得していない場合は、Intune ライセンスをそのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="edb1a-123">If the user is not licensed for app protection, assign an Intune license to the user.</span></span>
- <span data-ttu-id="edb1a-124">ユーザーが O365 のライセンスを取得していない場合、ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="edb1a-124">If the user is not licensed for O365 obtain a license for the user.</span></span>
- <span data-ttu-id="edb1a-125">ユーザーのアプリが **[チェックインされていません]** という状態で一覧に表示される場合は、そのアプリのアプリ保護ポリシーを正しく構成したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="edb1a-125">If a user's app is listed as **Not checked in**, check if you've correctly configured a app protection policy for that app.</span></span>
- <span data-ttu-id="edb1a-126">アプリ保護ポリシーを適用するすべてのユーザーに、これらの条件が適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="edb1a-126">Ensure that these conditions are applied across all users to which you want app protection policies to apply.</span></span>

### <a name="see-also"></a><span data-ttu-id="edb1a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="edb1a-127">See also</span></span>

[<span data-ttu-id="edb1a-128">Intune アプリ保護ポリシーとは</span><span class="sxs-lookup"><span data-stu-id="edb1a-128">What is Intune app protection policy?</span></span>](app-protection-policies.md)
