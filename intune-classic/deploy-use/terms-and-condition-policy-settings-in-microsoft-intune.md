---
title: "使用条件ポリシー設定"
description: "Intune の使用条件をユーザー グループに展開すると、登録、会社のリソースへのアクセス、ポータル サイト アプリの使用によるデバイスとユーザーへの影響を説明できます。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4e241f888bbe50c01e834ed0dc55a2223de511db
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="terms-and-condition-policy-settings-in-microsoft-intune"></a><span data-ttu-id="d4983-103">Microsoft Intune の使用条件ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="d4983-103">Terms and condition policy settings in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="d4983-104">Intune の使用条件をユーザー グループに展開すると、登録、会社のリソースへのアクセス、ポータル サイト アプリによるデバイスとユーザーへの影響を説明できます。</span><span class="sxs-lookup"><span data-stu-id="d4983-104">You can deploy Intune terms and conditions to user groups to explain how enrollment, access to work resources, and the Company Portal app affect devices and users.</span></span> <span data-ttu-id="d4983-105">ユーザーは、会社のポータルを使用して登録したり作業にアクセスしたりする前に、使用条件に同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4983-105">Users must accept the terms and conditions before they can use the Company Portal to enroll and access their work.</span></span>

<span data-ttu-id="d4983-106">さまざまな使用条件を含む複数のポリシーを作成して展開できます。</span><span class="sxs-lookup"><span data-stu-id="d4983-106">You can create and deploy multiple policies containing different terms and conditions.</span></span> <span data-ttu-id="d4983-107">また、同じ使用条件のさまざまな言語のバージョンを作成し、適切なグループに展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4983-107">You can also produce versions of the same terms and conditions in different languages and then deploy these to their appropriate groups.</span></span>

## <a name="create-a-terms-and-conditions-policy"></a><span data-ttu-id="d4983-108">使用条件ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="d4983-108">Create a terms and conditions policy</span></span>

1.  <span data-ttu-id="d4983-109">[Microsoft Intune の管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[使用条件]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4983-109">In the [Microsoft Intune administration console](https://manage.microsoft.com) click **Policy** &gt; **Terms and Conditions**.</span></span>

    ![使用条件ポリシーのスクリーンショット](./media/pol-sa-terms-conditions.png)

2.  <span data-ttu-id="d4983-111">**[追加]** をクリックし、新しい使用条件ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4983-111">Click **Add** to create a new terms and conditions policy.</span></span>

    <span data-ttu-id="d4983-112">既存のポリシーを**編集**または**削除**することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4983-112">You can also **Edit** or **Delete** an existing policy.</span></span>

3.  <span data-ttu-id="d4983-113">**[使用条件の作成]** ページで、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4983-113">On the **Create Terms and Conditions** page, specify the following information:</span></span>

    -   <span data-ttu-id="d4983-114">**[名前]**&mdash;Intune コンソールに表示される、一意のポリシー名。</span><span class="sxs-lookup"><span data-stu-id="d4983-114">**Name**&mdash;A unique policy name displayed in the Intune console.</span></span>

    -   <span data-ttu-id="d4983-115">**[説明]**&mdash;Intune コンソールでポリシーを識別するための詳細。</span><span class="sxs-lookup"><span data-stu-id="d4983-115">**Description**&mdash;Details that help you identify the policy in the Intune console.</span></span>

    -   <span data-ttu-id="d4983-116">**[タイトル]**&mdash;ポータル サイトに表示されるタイトル。</span><span class="sxs-lookup"><span data-stu-id="d4983-116">**Title**&mdash;The title users see in the company portal.</span></span>

    -   <span data-ttu-id="d4983-117">**[ユーザーによる同意の意味を説明するテキスト]**&mdash;ユーザーに表示される同意に関するラベル。</span><span class="sxs-lookup"><span data-stu-id="d4983-117">**Text to explain what it means if the user accepts**&mdash;The label users see regarding acceptance.</span></span> <span data-ttu-id="d4983-118">例: "使用条件に同意します。"</span><span class="sxs-lookup"><span data-stu-id="d4983-118">For example, “I agree to the terms and conditions.”</span></span>

4.  <span data-ttu-id="d4983-119">操作が完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4983-119">When you are finished, click **Save**.</span></span> <span data-ttu-id="d4983-120">新しいポリシーが**[ポリシー]** ワークスペースの **[使用条件]** ノードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4983-120">The new policy is displayed in the **Terms and Conditions** node of the **Policy** workspace.</span></span>

## <a name="deploy-a-terms-and-conditions-policy"></a><span data-ttu-id="d4983-121">使用条件ポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="d4983-121">Deploy a terms and conditions policy</span></span>

1.  <span data-ttu-id="d4983-122">[Microsoft Intune の管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[使用条件]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4983-122">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Terms and Conditions**.</span></span>

2.  <span data-ttu-id="d4983-123">**[使用条件ポリシー]** の一覧で、展開するポリシーを選び、**[展開の管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4983-123">In the **Terms and Conditions Policies** list, select the policy you want to deploy, and then click **Manage Deployment**.</span></span>

3.  <span data-ttu-id="d4983-124">**[展開の管理]** ダイアログ ボックスで、ポリシーを展開するユーザー グループを選び、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4983-124">In the **Manage Deployment** dialog box, select the user groups you will deploy the policy to, and then click **OK**.</span></span>

    <span data-ttu-id="d4983-125">対象ユーザーがポータル サイトにアクセスすると、Intune では、展開した使用条件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4983-125">When targeted users access the company portal, Intune displays the terms and conditions you deployed.</span></span> <span data-ttu-id="d4983-126">ユーザーは、これらの使用条件に同意しないと、会社のリソースへのアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d4983-126">Users must accept these terms before they can gain access to company resources.</span></span>

## <a name="monitor-a-terms-and-conditions-policy"></a><span data-ttu-id="d4983-127">使用条件ポリシーの監視</span><span class="sxs-lookup"><span data-stu-id="d4983-127">Monitor a terms and conditions policy</span></span>

1.  <span data-ttu-id="d4983-128">[Microsoft Intune の管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[使用条件]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4983-128">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Terms and Conditions**.</span></span>

2.  <span data-ttu-id="d4983-129">**[新しいレポートの作成]** ウィンドウで、**[レポートの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4983-129">In the **Create New Report** window, click **View Report**.</span></span> <span data-ttu-id="d4983-130">展開した使用条件に同意したユーザーの詳細を示すレポートが開きます。</span><span class="sxs-lookup"><span data-stu-id="d4983-130">The report will open detailing which users have accepted the terms and conditions you deployed.</span></span>

### <a name="updates-and-version-control-for-terms-and-conditions"></a><span data-ttu-id="d4983-131">使用条件の更新およびバージョン管理</span><span class="sxs-lookup"><span data-stu-id="d4983-131">Updates and version control for terms and conditions</span></span>
<span data-ttu-id="d4983-132">既存の使用条件ポリシーを編集するときは、ポリシーを展開するときの動作を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d4983-132">When you edit an existing terms and conditions policy, you can choose which behavior occurs when you deploy the policy.</span></span> <span data-ttu-id="d4983-133">既存の使用条件ポリシーを更新するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d4983-133">Use the following procedure to help you update existing terms and conditions policies.</span></span>

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a><span data-ttu-id="d4983-134">使用条件の複数のバージョンを使用する</span><span class="sxs-lookup"><span data-stu-id="d4983-134">Work with multiple versions of terms and conditions</span></span>

1.  <span data-ttu-id="d4983-135">[Microsoft Intune の管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[使用条件]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4983-135">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Terms and Conditions**.</span></span>

2.  <span data-ttu-id="d4983-136">編集する使用条件ポリシーを選んで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4983-136">Select the terms and conditions policy that you want to edit, and then click **Edit**.</span></span>

3.  <span data-ttu-id="d4983-137">**[使用条件の編集]** ページで、必要な編集を加えて、この新しいバージョンですべてのユーザーに使用条件への同意を求めるか、新しいユーザーのみに新しいバージョンの使用条件を表示するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4983-137">On the **Edit Terms and Conditions** page, make any required edits, and then specify whether this new version requires all users to accept the terms and conditions, or if only new users will see the new version.</span></span>

    <span data-ttu-id="d4983-138">使用条件ポリシーに対して重要な変更を行うときは常にバージョン番号を大きくし、同意を求めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4983-138">We recommend that you increase the version number and require acceptance any time you make significant changes to your terms and conditions policy.</span></span> <span data-ttu-id="d4983-139">誤植の修正や書式設定の変更などを行った場合は、現在のバージョン番号をそのままにします。</span><span class="sxs-lookup"><span data-stu-id="d4983-139">Keep the current version number if you are fixing typos or changing formatting, for example.</span></span>

### <a name="see-also"></a><span data-ttu-id="d4983-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4983-140">See also</span></span>
[<span data-ttu-id="d4983-141">Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する</span><span class="sxs-lookup"><span data-stu-id="d4983-141">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
