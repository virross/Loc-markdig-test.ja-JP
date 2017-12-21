---
title: "Microsoft Intune の使用条件の設定"
titlesuffix: Azure portal
description: "Intune 用ポータル サイトでユーザーに表示する使用条件を設定します。 "
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4842bf766659ebedd89035a8b13521ca63e2f3a4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="ensure-users-accept-company-terms-for-access"></a><span data-ttu-id="653c8-103">ユーザーにアクセス関連の会社条項に同意させる</span><span class="sxs-lookup"><span data-stu-id="653c8-103">Ensure users accept company terms for access</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="653c8-104">Intune 管理者は、ユーザーが会社の使用条件に同意しないと、ポータル サイトで自分のデバイスの登録や会社のアプリや電子メールなどのリソースへのアクセスができないという要件を設定できます。</span><span class="sxs-lookup"><span data-stu-id="653c8-104">As an Intune admin, you can require that users accept your company's terms and conditions before they can use the Company Portal to enroll their devices and access resources like company apps and email.</span></span> <span data-ttu-id="653c8-105">使用条件の構成は任意です。</span><span class="sxs-lookup"><span data-stu-id="653c8-105">Configuration of terms and conditions is optional.</span></span>

<span data-ttu-id="653c8-106">複数の条件セットを作成し、異なるグループに割り当てることができます。それにより、たとえば、さまざまな言語をサポートします。</span><span class="sxs-lookup"><span data-stu-id="653c8-106">You can create multiple sets of terms and assign them to different groups, such as to support different languages.</span></span>

## <a name="create-terms-and-conditions"></a><span data-ttu-id="653c8-107">使用条件を作成する</span><span class="sxs-lookup"><span data-stu-id="653c8-107">Create terms and conditions</span></span>
<span data-ttu-id="653c8-108">次の手順で使用条件を作成します。</span><span class="sxs-lookup"><span data-stu-id="653c8-108">Complete these steps to create terms and conditions.</span></span> <span data-ttu-id="653c8-109">表示名と説明は管理目的で使用されます。条件のプロパティはポータル サイトでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="653c8-109">The display name and description are for administrative use while terms properties are displayed to users in the Company Portal.</span></span>

1. <span data-ttu-id="653c8-110">Azure Portal で **[デバイスの登録]** を選択し、**[使用条件]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-110">In the Azure portal, choose **Device enrollment**, and then choose **Terms and Conditions**.</span></span>
2. <span data-ttu-id="653c8-111">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-111">Select **Create**.</span></span>
<span data-ttu-id="653c8-112">![Azure Portal のスクリーンショット。使用条件の [作成] ボタンを確認できます。](media/terms-create-terms.png)</span><span class="sxs-lookup"><span data-stu-id="653c8-112">![Screenshot of the Azure portal showing Create button for terms and conditions](media/terms-create-terms.png)</span></span>
3. <span data-ttu-id="653c8-113">ブレードを展開し、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="653c8-113">On the expanded blade, specify the following information:</span></span>

   - <span data-ttu-id="653c8-114">**[表示名]**: Azure Portal における条件の名前。</span><span class="sxs-lookup"><span data-stu-id="653c8-114">**Display name**: The name for the terms in the Azure portal.</span></span> <span data-ttu-id="653c8-115">ユーザーにはこの名前は表示されません。</span><span class="sxs-lookup"><span data-stu-id="653c8-115">Users don't see this name.</span></span>

   - <span data-ttu-id="653c8-116">**[説明]**: Azure Portal でこの条件セットの識別に役立つ任意の説明。</span><span class="sxs-lookup"><span data-stu-id="653c8-116">**Description**: Optional details that help you identify this set of terms in the Azure portal.</span></span>

4. <span data-ttu-id="653c8-117">[Define terms of use (使用条件の定義)] の横にある矢印を選択し、[使用条件] ブレードを開いて、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="653c8-117">Select the arrow next to Define terms of use to open the Terms and Conditions blade, and then enter the following information:</span></span>

   ![エンド ユーザーの使用条件の同意画面と条件の概要のスクリーンショット](./media/terms-summary-create.png)

   - <span data-ttu-id="653c8-119">**[タイトル]**: ポータル サイトで **[概要]** の上に表示される使用条件の名前。</span><span class="sxs-lookup"><span data-stu-id="653c8-119">**Title**: The name for your terms that users see in the Company Portal above the **Summary**.</span></span>
   - <span data-ttu-id="653c8-120">**[使用条件の概要]**: 使用条件に対するユーザーの同意が意味することを説明するテキスト。</span><span class="sxs-lookup"><span data-stu-id="653c8-120">**Summary of Terms**: Text that explains what it means when users accept the terms.</span></span> <span data-ttu-id="653c8-121">たとえば、「デバイスを登録すると、Contoso が定めている利用規約に同意することになります。</span><span class="sxs-lookup"><span data-stu-id="653c8-121">For example, "By enrolling your device, you are agreeing to the terms of use set out by Contoso.</span></span> <span data-ttu-id="653c8-122">条件をよく読んでから続行してください。」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="653c8-122">Read the terms carefully before proceeding."</span></span>
   - <span data-ttu-id="653c8-123">**[使用条件]**: ユーザーに確認と承諾または拒否を求める使用条件。</span><span class="sxs-lookup"><span data-stu-id="653c8-123">**Terms and Conditions**: The terms and conditions that users see and must either accept or reject.</span></span>

5. <span data-ttu-id="653c8-124">**[OK]** を選択し、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-124">Select **Ok** and then select **Create**.</span></span>

## <a name="see-how-terms-are-displayed-to-your-users"></a><span data-ttu-id="653c8-125">ユーザーにどのように条項が表示されるか確認する</span><span class="sxs-lookup"><span data-stu-id="653c8-125">See how terms are displayed to your users</span></span>
<span data-ttu-id="653c8-126">次の例は、管理コンソールとポータル サイトに表示される **[タイトル]** と **[使用条件の概要]** です。</span><span class="sxs-lookup"><span data-stu-id="653c8-126">The following example shows the **Title** and **Summary of Terms** in the admin console and Company Portal.</span></span>

![管理コンソールとポータル サイトに表示されるタイトルと使用条件の概要のスクリーンショット。](./media/terms-summary-terms.png)

<span data-ttu-id="653c8-128">次の例は、管理コンソールとポータル サイトに表示される使用条件です。</span><span class="sxs-lookup"><span data-stu-id="653c8-128">The following example shows the terms and conditions in the admin console and the Company Portal.</span></span>

![管理コンソールとポータル サイトに表示される使用条件のスクリーンショット。](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a><span data-ttu-id="653c8-130">使用条件を割り当てる</span><span class="sxs-lookup"><span data-stu-id="653c8-130">Assign terms and conditions</span></span>

<span data-ttu-id="653c8-131">ポータル サイトを利用する前に承諾を求めるユーザー グループに使用条件を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="653c8-131">You can assign terms and conditions to groups of user who must accept them before using the Company Portal.</span></span>

1. <span data-ttu-id="653c8-132">Azure Portal で **[デバイスの登録]** を選択し、**[使用条件]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-132">In the Azure portal, choose **Device enrollment**, and then choose **Terms and Conditions**.</span></span>
2. <span data-ttu-id="653c8-133">使用条件の一覧で、割り当てる条件を選択し、**[割り当てられたグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-133">In the list of terms and conditions, select the terms you want to assign, and then select **Assigned Groups**.</span></span>
<span data-ttu-id="653c8-134">![Azure Portal の [グループの割り当て] ブレードのスクリーンショット。使用条件割り当てのための [グループの選択] ボタンと [選択] ボタンを確認できます。](media/terms-assign-groups.png)</span><span class="sxs-lookup"><span data-stu-id="653c8-134">![Screenshot of the Azure portal's Assign Group blade showing Select Group button and Select button for terms and conditions assignment](media/terms-assign-groups.png)</span></span>
3. <span data-ttu-id="653c8-135">**[グループの選択]** ボタンをクリックし、**[グループの選択]** ブレードで条件を割り当てるグループを選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="653c8-135">Click the **Select Group** button and in the **Select Groups** blade, select the groups you want to assign the terms, and then click **Select**.</span></span> <span data-ttu-id="653c8-136">動的なグループには使用条件を割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="653c8-136">Dynamic groups cannot be assigned Terms and Conditions.</span></span>
4. <span data-ttu-id="653c8-137">**[割り当てられたグループ]** ブレードで、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="653c8-137">In the **Assigned Groups** blade, click **Save**.</span></span>  <span data-ttu-id="653c8-138">これで使用条件が選択したグループのユーザーに割り当てられました。</span><span class="sxs-lookup"><span data-stu-id="653c8-138">The terms and conditions are now assigned to users in the selected groups.</span></span> <span data-ttu-id="653c8-139">次回ポータル サイトにアクセスしたとき、条件の承諾がユーザーに求められます。</span><span class="sxs-lookup"><span data-stu-id="653c8-139">Users will be prompted to accept terms the next time they access the company portal.</span></span> <span data-ttu-id="653c8-140">使用条件に同意する必要があるのは一度のみです。</span><span class="sxs-lookup"><span data-stu-id="653c8-140">The terms and conditions only need to be accepted once.</span></span> <span data-ttu-id="653c8-141">複数のデバイスを持つユーザーは、各デバイスで同意する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="653c8-141">Users with multiple devices don't have to accept on each device.</span></span>


## <a name="monitor-terms-and-conditions"></a><span data-ttu-id="653c8-142">使用条件の監視</span><span class="sxs-lookup"><span data-stu-id="653c8-142">Monitor terms and conditions</span></span>

1. <span data-ttu-id="653c8-143">Azure Portal で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-143">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span> <span data-ttu-id="653c8-144">[Intune] ブレードで **[デバイスの登録]** を選択し、**[使用条件]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-144">On the Intune blade, choose **Device enrollment**, and then choose **Terms and Conditions**.</span></span>
2. <span data-ttu-id="653c8-145">使用条件の一覧で、承諾を表示する条件を選択し、**[同意の状態]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-145">In the list of terms and conditions, select the terms you want to view acceptance for, and then select **Acceptance Statuses**.</span></span>

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a><span data-ttu-id="653c8-146">使用条件の複数のバージョンを使用する</span><span class="sxs-lookup"><span data-stu-id="653c8-146">Work with multiple versions of terms and conditions</span></span>
<span data-ttu-id="653c8-147">使用条件を編集し、そのバージョンを管理できます。</span><span class="sxs-lookup"><span data-stu-id="653c8-147">You can edit your terms and conditions and manage their versions.</span></span> <span data-ttu-id="653c8-148">使用条件に対して重要な変更を加えるときは常にバージョン番号を大きくし、同意を求めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="653c8-148">We recommend that you increase the version number and require acceptance any time you make significant changes to your terms and conditions.</span></span> <span data-ttu-id="653c8-149">誤植の修正や書式設定の変更などを行った場合は、現在のバージョン番号をそのままにします。</span><span class="sxs-lookup"><span data-stu-id="653c8-149">Keep the current version number if, for example, you are fixing typos or changing formatting.</span></span>

1. <span data-ttu-id="653c8-150">Azure Portal で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-150">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2. <span data-ttu-id="653c8-151">[Intune] ブレードで、**[デバイスの登録]** を選択し、**[使用条件]** を選択し、変更する使用条件を選択し、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-151">On the Intune blade, choose **Device enrollment**,  choose **Terms and Conditions**, select the terms and conditions you want to modify, and then select **Properties**.</span></span>

4. <span data-ttu-id="653c8-152">**[プロパティ]** ブレードで、**[使用条件]** を選択し、必要に応じて **[タイトル]**、**[使用条件の概要]**、**[使用条件]** を変更します。</span><span class="sxs-lookup"><span data-stu-id="653c8-152">On the **Properties** blade, select **Terms and Conditions** and then modify the **Title**, **Summary of Terms**, and **Terms and Conditions** as needed.</span></span> <span data-ttu-id="653c8-153">変更を加えた結果、ユーザーが新しい条件を承諾する必要が生じた場合は、**[ユーザーに対してもう一度同意を求めて、バージョン番号を {0} に上げます]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="653c8-153">If the changes you made make it necessary for users to reaccept the new terms, click **Require users to re-accept, and increment the version number to**</span></span>

4.  <span data-ttu-id="653c8-154">**[OK]** を選択し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="653c8-154">Select **OK** and then select **Save**.</span></span>

<span data-ttu-id="653c8-155">ユーザーは、更新された使用条件に 1 回だけ同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="653c8-155">Users only have to accept updated terms and conditions once.</span></span> <span data-ttu-id="653c8-156">複数のデバイスを持つユーザーは、各デバイスで使用条件に同意する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="653c8-156">Users with multiple devices don't have to accept terms and conditions on each device.</span></span>
