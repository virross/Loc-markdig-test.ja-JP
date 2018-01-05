---
title: "ユーザーの概要"
titlesuffix: Azure portal
description: "Intune にユーザーを追加し、モバイル デバイスで会社のリソースにアクセスできるようにします。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4d7ff6b4943d6cba05b9c7909882de6515ae7ce9
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="get-started-with-managing-users"></a><span data-ttu-id="fd4d7-103">ユーザー管理の概要</span><span class="sxs-lookup"><span data-stu-id="fd4d7-103">Get started with managing users</span></span>

<span data-ttu-id="fd4d7-104">組織のさまざまな人間について考えてください。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-104">Think about all the different people in your organization.</span></span> <span data-ttu-id="fd4d7-105">会社のデータを利用するすべての人間が Intune でデータにアクセスするためにユーザーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-105">Every one of them that uses company data will need a user to manage access to it in Intune.</span></span>

## <a name="how-do-i-create-a-user"></a><span data-ttu-id="fd4d7-106">ユーザーの作成方法</span><span class="sxs-lookup"><span data-stu-id="fd4d7-106">How do I create a user?</span></span>

1. <span data-ttu-id="fd4d7-107">[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-107">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="fd4d7-108">**[リソースの検索]** を利用し、**[Intune]** を探します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-108">Using **Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="fd4d7-109">**[Microsoft Intune]** ブレードを開いたら、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-109">Once you've opened the **Microsoft Intune** blade, select **Users**.</span></span> <span data-ttu-id="fd4d7-110">**[すべてのユーザー]** ページで、**[+ 新しいユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-110">On the **All Users** page, select **+ New user**.</span></span>
4. <span data-ttu-id="fd4d7-111">**名前**や**ユーザー名**など、ユーザーの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-111">Enter details for the user, such as **Name** and **User name**.</span></span> <span data-ttu-id="fd4d7-112">ユーザー名のドメイン名の部分は初回の既定ドメイン名である “contoso.onmicrosoft.com” か、“contoso.com” など、検証済みの非フェデレーション ドメイン名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-112">The domain name portion of the user name must either be the initial default domain name “contoso.onmicrosoft.com” domain name, or a verified, non-federated domain name such as “contoso.com.”</span></span>
5. <span data-ttu-id="fd4d7-113">**[グループ]** の下で、ユーザーを追加するテスト グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-113">Under **Groups**, choose the test group to add the user to.</span></span>
6. <span data-ttu-id="fd4d7-114">テスト デバイスにログオンするときに利用できるように、自動生成されたユーザー パスワードを保存します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-114">Save the automatically generated user password so that you can use it to log in to a test device.</span></span> <span data-ttu-id="fd4d7-115">このパスワードをユーザーに与える必要があります。パスワードを与えられたユーザーは、自分が覚えられるように普通のパスワードに変更できます。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-115">You must give this password to users so that they can change it to a normal password that they can remember.</span></span>
7. <span data-ttu-id="fd4d7-116">**[ユーザー]** ブレードで、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-116">On the **User** blade, select **Create**.</span></span>

## <a name="assigning-licenses-to-users"></a><span data-ttu-id="fd4d7-117">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="fd4d7-117">Assigning licenses to users</span></span>

<span data-ttu-id="fd4d7-118">ユーザーを作成したら、[Office 365 ポータル](http://go.microsoft.com/fwlink/p/?LinkId=698854)を利用し、Intune ライセンスをそのユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-118">After you've created a user, you need to use the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) to assign an Intune license to that user.</span></span> <span data-ttu-id="fd4d7-119">ライセンスを割り当てないと、ユーザーは自分のデバイスを管理に登録できません。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-119">Without assigning them a license, they can't enroll their device into management.</span></span>

1. <span data-ttu-id="fd4d7-120">Intune にサインインしたときに使用したものと同じ資格情報で [Office 365 ポータル](http://go.microsoft.com/fwlink/p/?LinkId=698854)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-120">Sign in to the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) with the same credentials you used to sign in to Intune.</span></span>
2. <span data-ttu-id="fd4d7-121">**[ユーザー]** > **[アクティブなユーザー]** の順に選択し、前に作成したユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-121">Select **Users** > **Active Users**, then select the user you previously created.</span></span>
3. <span data-ttu-id="fd4d7-122">すべてのユーザーの情報が読み込まれるまでしばらくの間待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-122">You may need to wait a moment for all of the user's information to load.</span></span> <span data-ttu-id="fd4d7-123">読み込まれたら、ユーザーの **[製品ライセンス]** の **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-123">Once it loads, select **Edit** for the user's **Product licenses**.</span></span>
4. <span data-ttu-id="fd4d7-124">ユーザーに **[場所]** を割り当て、Intune を **[オン]** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-124">Assign the user a **Location**, then switch Intune to **on**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fd4d7-125">このとき、このユーザーのライセンスの 1 つが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-125">This uses one of your licenses for this user.</span></span> <span data-ttu-id="fd4d7-126">ライブ環境を利用している場合、後でこのライセンスの使用をオフにし、実際のユーザーに再度割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-126">If you are using your live environment, you can turn off using this license later to reassign it to a real user.</span></span>

5. <span data-ttu-id="fd4d7-127">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-127">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fd4d7-128">次の手順</span><span class="sxs-lookup"><span data-stu-id="fd4d7-128">Next steps</span></span>

<span data-ttu-id="fd4d7-129">[グループの概要](get-started-groups.md) - ユーザーをグループにまとめ、ユーザーがアクセスできるポリシーやアプリの管理を簡単にします。</span><span class="sxs-lookup"><span data-stu-id="fd4d7-129">[Get started with groups](get-started-groups.md) - Organize users into groups to make it easier to manage the policies and apps that they can access.</span></span>
