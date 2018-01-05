---
title: "アプリ保護ポリシーを作成して展開する"
titleSuffix: Azure portal
description: "Intune のアプリ保護ポリシーが、管理するアプリによって使用される会社のデータを保護するうえでどのように役立つかについて説明します。\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47b3051e2cdeabd36115f48e0987fd162bdf3b77
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-create-and-assign-app-protection-policies"></a><span data-ttu-id="f101e-103">アプリ保護ポリシーを作成して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="f101e-103">How to create and assign app protection policies</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a><span data-ttu-id="f101e-104">始める前に</span><span class="sxs-lookup"><span data-stu-id="f101e-104">Before you begin</span></span>

<span data-ttu-id="f101e-105">Intune クラシック ポータルでの手順については、[アプリ保護ポリシーを作成する方法](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f101e-105">If you're looking for instructions in the Intune classic portal, see [how to create app protection policies](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).</span></span>

<span data-ttu-id="f101e-106">アプリ保護ポリシーは、場合によっては Intune で管理できないデバイスで実行されているアプリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="f101e-106">App protection policies can be applied to apps running on devices that may or may not be managed by Intune.</span></span> <span data-ttu-id="f101e-107">アプリ保護ポリシーのしくみと Intune のアプリ保護ポリシーでサポートされるシナリオの詳細については、[Microsoft Intune のアプリ保護ポリシー](app-protection-policy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f101e-107">For a more detailed description of how app protection policies work and the scenarios supported by Intune app protection policies, see [What is Microsoft Intune app protection policies](app-protection-policy.md).</span></span>

<span data-ttu-id="f101e-108">MAM でサポートされるアプリの一覧については、[MAM アプリの一覧](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f101e-108">If you're looking for a list of MAM supported apps, see [MAM apps list](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).</span></span>

##  <a name="create-an-app-protection-policy"></a><span data-ttu-id="f101e-109">アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f101e-109">Create an app protection policy</span></span>
1. <span data-ttu-id="f101e-110">**[モバイル アプリ]** ワークロードで、**[管理]** > **[アプリ保護ポリシー]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="f101e-110">In the **Mobile apps** workload, choose **Manage** > **App protection policies**.</span></span>

2. <span data-ttu-id="f101e-111">これにより、**[アプリ保護ポリシー]** ブレードが開き、ここで新しいポリシーを作成したり、既存のポリシーを編集したりできます。</span><span class="sxs-lookup"><span data-stu-id="f101e-111">This opens the **App protection policies** blade, where you'll create new policies and edit existing policies.</span></span> <span data-ttu-id="f101e-112">**[ポリシーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-112">Choose **Add a policy**.</span></span>

   ![[ポリシーの追加] ブレードのスクリーンショット](./media/app-protection-add-policy.png)

3. <span data-ttu-id="f101e-114">ポリシーの名前を入力して簡単な説明を追加し、iOS または Android 用のポリシーを作成するプラットフォームの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-114">Type a name for the policy, add a brief description, and select the platform type to create a policy for iOS or Android.</span></span> <span data-ttu-id="f101e-115">プラットフォームごとに複数のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f101e-115">You can create more than one policy for each platform.</span></span>

4. <span data-ttu-id="f101e-116">**[アプリ]** を選択して **[アプリ] ブレード** を開くと、使用可能なアプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f101e-116">Choose **Apps** to open the **Apps blade**, where a list of available apps is displayed.</span></span> <span data-ttu-id="f101e-117">一覧から、作成するポリシーに関連付けるアプリを 1 つまたは複数選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-117">Select one or more apps from the list that you want to associate with the policy that you are creating.</span></span> <span data-ttu-id="f101e-118">アプリを選択したら、**[アプリ]** ブレードの下部にある **[選択]** を選択して、選択内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f101e-118">Once you have selected the apps, choose **Select** at the bottom of the **Apps** blade to save your selection.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f101e-119">ポリシーを作成するには、少なくとも 1 つのアプリを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f101e-119">You must select at least one app to create a policy.</span></span>

5. <span data-ttu-id="f101e-120">**[ポリシーの追加] ブレード**で、**[必要な設定の構成]** を選択し、[ポリシー設定] ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="f101e-120">On the **Add a policy blade**, choose **Configure required settings** to open the policy settings blade.</span></span>

   <span data-ttu-id="f101e-121">ポリシー設定には、**[データ再配置]** と **[アクセス]** の 2 つのカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="f101e-121">There are two categories of policy settings, **Data relocation** and **Access**.</span></span>  <span data-ttu-id="f101e-122">データ再配置ポリシーは、アプリとの間のデータ移動に適用可能ですが、作業コンテキストでエンド ユーザーがアプリにアクセスする方法は、アクセス ポリシーによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f101e-122">Data relocation policies are applicable to data movement in and out of the apps, while the access polices determine how the end user accesses the apps in a work context.</span></span>
   <span data-ttu-id="f101e-123">ユーザーが開始できるように、ポリシー設定には既定値が入力されています。</span><span class="sxs-lookup"><span data-stu-id="f101e-123">To get you started, the policy settings have default values.</span></span> <span data-ttu-id="f101e-124">既定値が要件を満たす場合は、変更を加える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f101e-124">You do not have to make any changes if the default values meet your requirements.</span></span>

   > [!TIP]
   > <span data-ttu-id="f101e-125">これらのポリシー設定は、作業コンテキストでアプリを使用する場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f101e-125">These policy settings are enforced only when using apps in the work context.</span></span>  <span data-ttu-id="f101e-126">エンド ユーザーが、個人のタスクを実行するためにアプリを使用する場合、これらのポリシーによって設定が影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="f101e-126">When the end user uses the app to do a personal task, they will not be affected by these policies.</span></span>



6. <span data-ttu-id="f101e-127">**[OK]** を選択して、この構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="f101e-127">Choose **OK** to save this configuration.</span></span> <span data-ttu-id="f101e-128">これにより、 **[ポリシーの追加]** ブレードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="f101e-128">You are now back in the **Add a policy** blade.</span></span> <span data-ttu-id="f101e-129">**[作成]** を選択してポリシーを作成し、設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="f101e-129">Choose **Create** to create the policy and save your settings.</span></span>


<span data-ttu-id="f101e-130">前の手順の説明に従ってポリシーの作成が完了した時点では、ポリシーはユーザーに展開されません。</span><span class="sxs-lookup"><span data-stu-id="f101e-130">When you finish creating a policy as described in the previous procedure, it is not deployed to any users.</span></span> <span data-ttu-id="f101e-131">ポリシーを展開するには、次のセクションの「ユーザーへのポリシーの展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f101e-131">To deploy a policy, see the following section, "Deploy a policy to users."</span></span>

## <a name="deploy-a-policy-to-users"></a><span data-ttu-id="f101e-132">ユーザーへのポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="f101e-132">Deploy a policy to users</span></span>

1. <span data-ttu-id="f101e-133">**[ポリシー]** ブレードで **[ユーザー グループ]** を選択して、**[ユーザー グループ]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="f101e-133">In the **Policy** blade, choose  **User groups**, which opens the **User groups** blade.</span></span> <span data-ttu-id="f101e-134">**[ユーザー グループ]** ブレードで **[ユーザー グループの追加]** を選択して、**[ユーザー グループの追加]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="f101e-134">Choose **Add user group** in the **User groups** blade to open the **Add user group** blade.</span></span>

   ![[ユーザー グループの追加] メニュー オプションが強調表示されている [ユーザー グループ] ブレードのスクリーンショット](./media/app-protection-policy-add-users.png)

2. <span data-ttu-id="f101e-136">ユーザー グループの一覧が、 **[ユーザー グループの追加]** ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f101e-136">A list of user groups is displayed on the **Add user group** blade.</span></span> <span data-ttu-id="f101e-137">これは、 **Azure Active Directory**内にあるすべてのセキュリティ グループの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f101e-137">This is a list of all the security groups in your **Azure Active Directory**.</span></span> <span data-ttu-id="f101e-138">このポリシーを適用するユーザー グループを選択し、**[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-138">Select the user groups you want this policy to apply to, and then choose **Select**.</span></span> <span data-ttu-id="f101e-139">**[選択]** を選択すると、ポリシーがユーザーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="f101e-139">Choosing **Select**, deploys the policy to users.</span></span>
   <span data-ttu-id="f101e-140">![Azure Active Directory ユーザーの一覧を示している [ユーザー グループの追加] ブレードのスクリーンショット](./media/azure-ad-user-group-list.png)</span><span class="sxs-lookup"><span data-stu-id="f101e-140">![Screenshot of the Add user group blade showing the list of Azure Active Directory users](./media/azure-ad-user-group-list.png)</span></span>

<span data-ttu-id="f101e-141">これで、作成したポリシーはユーザーに展開されました。</span><span class="sxs-lookup"><span data-stu-id="f101e-141">You have now created a policy and deployed it to users.</span></span>

<span data-ttu-id="f101e-142">Microsoft Intune ライセンスが割り当てられているユーザーのみが、このポリシーの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="f101e-142">Only users with Microsoft Intune licenses assigned to them are affected by the policy.</span></span> <span data-ttu-id="f101e-143">選択したセキュリティ グループ内のユーザーのうち、Microsoft Intune ライセンスが割り当てられていないユーザーは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="f101e-143">Users who are in the security group that you selected who don’t have a Microsoft Intune license assigned to them are not affected.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="f101e-144">Intune を使用し、Configuration Manager によって iOS デバイスと Android デバイスを管理する場合、このポリシーは、選択したグループ直下のユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f101e-144">If you are using Intune with Configuration Manager to manage your iOS and Android devices, the policy is only applied to the users directly in the group that you selected.</span></span> <span data-ttu-id="f101e-145">選択したグループ内にネストされた子グループのメンバーは、影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="f101e-145">Members of child groups nested within the group you selected are not affected.</span></span>

<span data-ttu-id="f101e-146">エンド ユーザーは App Store または Google Play からアプリをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f101e-146">End users can download the apps from the App store or Google Play.</span></span> <span data-ttu-id="f101e-147">詳細については、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f101e-147">For more information, see:</span></span>
* [<span data-ttu-id="f101e-148">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="f101e-148">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
* [<span data-ttu-id="f101e-149">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="f101e-149">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a><span data-ttu-id="f101e-150">既存のポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="f101e-150">Change existing policies</span></span>
<span data-ttu-id="f101e-151">既存のポリシーを編集して、対象ユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="f101e-151">You can edit an existing policy and apply it to the targeted users.</span></span> <span data-ttu-id="f101e-152">ただし、既存のポリシーを変更する場合、アプリに既にサインインしているユーザーには、8 時間にわたって変更が表示されません。</span><span class="sxs-lookup"><span data-stu-id="f101e-152">However, when you change existing policies,  users who are already signed  in to the apps won’t see the changes for an 8-hour period.</span></span>

<span data-ttu-id="f101e-153">変更の効果をすぐに確認するには、エンド ユーザーはアプリをログアウトし、もう一度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f101e-153">To see the effect of the changes immediately, the end user will have to log out of the app, and sign back in.</span></span>

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a><span data-ttu-id="f101e-154">ポリシーに関連付けられているアプリの一覧を変更するには</span><span class="sxs-lookup"><span data-stu-id="f101e-154">To change the list of apps associated with the policy</span></span>

1.  <span data-ttu-id="f101e-155">**[アプリ ポリシー]** ブレードで、変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-155">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="f101e-156">これにより、選択したポリシーに固有のブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="f101e-156">This opens a blade specific to the policy you just selected.</span></span>

2.  <span data-ttu-id="f101e-157">ポリシー ブレードで **[対象アプリ]** をクリックし、アプリの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="f101e-157">In the policy blade, choose **Targeted apps** to open the list of apps.</span></span>

3.  <span data-ttu-id="f101e-158">一覧からアプリを削除または追加し、**[保存]** アイコンを選択して変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f101e-158">Remove or add apps from the list and choose the **Save** icon to save your changes.</span></span>

### <a name="to-change-the-list-of-user-groups"></a><span data-ttu-id="f101e-159">ユーザー グループの一覧を変更するには</span><span class="sxs-lookup"><span data-stu-id="f101e-159">To change the list of user groups</span></span>

1.  <span data-ttu-id="f101e-160">**[アプリ ポリシー]** ブレードで、変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-160">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="f101e-161">これにより、選択したポリシーに固有のブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="f101e-161">This opens the blade specific to the policy you selected.</span></span>

2.  <span data-ttu-id="f101e-162">ポリシー ブレードで **[ユーザー グループ]** をクリックして **[ユーザー グループ]** ブレードを開きます。このブレードには、このポリシーが設定された現在のユーザー グループの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f101e-162">In the policy blade, choose **User groups** to open the **User group** blade that shows the list of current user groups who have this policy.</span></span>

3.  <span data-ttu-id="f101e-163">ポリシーに新しいユーザー グループを追加するには、**[ユーザー グループの追加]** を選択し、ユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-163">To add a new user group to the policy, choose **Add user group**, and select the user group.</span></span> <span data-ttu-id="f101e-164">**[選択]** を選択して、選択したグループにポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="f101e-164">Choose **Select** to deploy the policy to the group you selected.</span></span>

4.  <span data-ttu-id="f101e-165">ユーザー グループを削除するには、削除するユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-165">To delete a user group, highlight the user group you want to remove.</span></span> <span data-ttu-id="f101e-166">省略記号 (...) を選択し、**[削除]** を選択してユーザー グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="f101e-166">Then choose the ellipses (…), and choose **Delete** to remove the user group.</span></span>
  <span data-ttu-id="f101e-167">![[削除] オプションが表示されたスクリーンショット](./media/app-protection-policy-delete-user.png)</span><span class="sxs-lookup"><span data-stu-id="f101e-167">![Screenshot showing Delete option ](./media/app-protection-policy-delete-user.png)</span></span>

### <a name="to-change-policy-settings"></a><span data-ttu-id="f101e-168">ポリシー設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="f101e-168">To change policy settings</span></span>

1.  <span data-ttu-id="f101e-169">**[アプリ ポリシー]** ブレードで、変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-169">In the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="f101e-170">これにより、選択したポリシーに固有のブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="f101e-170">This opens a blade specific to the policy you just selected.</span></span>


2.  <span data-ttu-id="f101e-171">**[ポリシー設定]** をクリックして **[ポリシー設定]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="f101e-171">Choose **Policy settings** to open the **Policy settings** blade.</span></span>

3.  <span data-ttu-id="f101e-172">設定を変更し、**[保存]** アイコンを選択して変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f101e-172">Change the settings, and choose the **Save** icon to save your changes.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="f101e-173">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="f101e-173">Policy settings</span></span>
<span data-ttu-id="f101e-174">iOS と Android 用のポリシー設定の完全な一覧を表示するには、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f101e-174">To see a full list of the policy settings for iOS and Android, select one of the following:</span></span>

- [<span data-ttu-id="f101e-175">iOS ポリシー</span><span class="sxs-lookup"><span data-stu-id="f101e-175">iOS policies</span></span>](app-protection-policy-settings-ios.md)
- [<span data-ttu-id="f101e-176">Android ポリシー</span><span class="sxs-lookup"><span data-stu-id="f101e-176">Android policies</span></span>](app-protection-policy-settings-android.md)

## <a name="next-steps"></a><span data-ttu-id="f101e-177">次の手順</span><span class="sxs-lookup"><span data-stu-id="f101e-177">Next steps</span></span>
[<span data-ttu-id="f101e-178">コンプライアンスとユーザーの状態を監視する</span><span class="sxs-lookup"><span data-stu-id="f101e-178">Monitor compliance and user status</span></span>](app-protection-policies-monitor.md)

### <a name="see-also"></a><span data-ttu-id="f101e-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="f101e-179">See also</span></span>
* [<span data-ttu-id="f101e-180">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="f101e-180">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
* [<span data-ttu-id="f101e-181">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="f101e-181">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)
