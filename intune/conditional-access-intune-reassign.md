---
title: "条件付きアクセス ポリシーを Intune クラシック ポータルから Azure Portal に移行する"
titlesuffix: Azure portal
description: "条件付きアクセス ポリシーを Intune クラシック ポータルから Azure Portal に移行します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bf047b37ee49fc632ee0aecda96d389e67d68b9
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a><span data-ttu-id="82cdd-103">条件付きアクセス ポリシーを Intune クラシック ポータルから Azure Portal に再割り当てする</span><span class="sxs-lookup"><span data-stu-id="82cdd-103">Reassign conditional access policies from Intune classic portal to the Azure portal</span></span>

<span data-ttu-id="82cdd-104">新しい Azure Portal 以降の条件付きアクセスは、アプリケーションごとの複数のポリシーと詳細なカスタマイズ機能のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-104">Starting in the new Azure portal, conditional access offers support for multiple policies per application, along with more customizability.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="82cdd-105">始める前に</span><span class="sxs-lookup"><span data-stu-id="82cdd-105">Before you begin</span></span>

<span data-ttu-id="82cdd-106">Azure Portal に移行する準備ができた場合、このトピックの手順に従って、Intune クラシック ポータルで作成した条件付きアクセス ポリシーの再割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-106">If you’re ready to move to the Azure portal, follow the steps in this topic to reassign the conditional access policies you previously created in the Intune classic portal:</span></span>

- <span data-ttu-id="82cdd-107">前に作成した条件付きアクセス ポリシーを収集し、後で再割り当てを行う必要がある設定を把握できるようにします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-107">Gather the conditional access policies previously created, so you know what settings you need to reassign later.</span></span>

- <span data-ttu-id="82cdd-108">このトピックの手順に従って、Azure Portal でポリシーを再作成します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-108">Follow the steps in this topic to re-create these policies in the Azure portal.</span></span>

- <span data-ttu-id="82cdd-109">Azure Portal で新しいポリシーが意図したとおりに動作することを確認した後、Intune クラシック ポータルで条件付きポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-109">Disable the conditional policies in the Intune classic portal, after you have verified that the new policies are working as expected in the Azure portal.</span></span>
<br /><br />
    - <span data-ttu-id="82cdd-110">Intune クラシック ポータルで条件付きアクセス ポリシーを**無効にする前に**、新しいポリシーへのユーザー移行方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-110">**Before you disable** the conditional access policies in the Intune classic portal, plan how you'll move users over to the new policy.</span></span> <span data-ttu-id="82cdd-111">これには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-111">There are two approaches:</span></span>
<br /><br />
        - <span data-ttu-id="82cdd-112">**同じ包含グループを使って Azure Portal で作成されたポリシーを適用し、新しい除外グループを作成して Intune クラシック ポータルによって適用されたポリシーで使います**。</span><span class="sxs-lookup"><span data-stu-id="82cdd-112">**Use the same inclusion group to apply policies created in the Azure portal, and create a new exemption group to use with the policies applied by the Intune classic portal**.</span></span>
            - <span data-ttu-id="82cdd-113">クラシック ポータルで指定されている除外グループにユーザーを段階的に移動します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-113">Gradually move some users into the exemption group specified in the classic portal.</span></span> <span data-ttu-id="82cdd-114">これにより、Intune クラシック ポータルの対象になっているポリシーが適用されないようにします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-114">This prevents the policies targeted by the Intune classic portal from being applied.</span></span> <span data-ttu-id="82cdd-115">Intune クラシック ポータルで適用されていたポリシーに加えて、Azure Portal の同じユーザー グループを対象に作成されたポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-115">The policies created and targeted to the same user group in the Azure portal are applied, in addition to the ones applied in the Intune classic portal.</span></span> 
<br /><br />
        - <span data-ttu-id="82cdd-116">**Azure Portal の条件付きアクセス ポリシーを対象とする新しいグループを作成します**。</span><span class="sxs-lookup"><span data-stu-id="82cdd-116">**Create a new group to target the conditional access policies in the Azure portal**.</span></span> <span data-ttu-id="82cdd-117">この方法を選んだ場合、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-117">If you choose this approach, you need to do the following:</span></span>
            - <span data-ttu-id="82cdd-118">Intune クラシック ポータルで条件付きアクセス ポリシーの対象になっていたセキュリティ グループからユーザーを段階的に削除します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-118">Gradually remove users from the security groups that have conditional access policies targeted to them in the Intune classic portal.</span></span>
            - <span data-ttu-id="82cdd-119">これらのユーザーに対して新しいポリシーが動作することを確認した後、Intune クラシック ポータルでポリシーを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-119">After you have confirmed the new policy is working for those users, you can disable the policy in the Intune classic portal.</span></span> 
<br /><br />
- <span data-ttu-id="82cdd-120">Intune クラシック ポータルで Exchange Active Sync (EAS) を使うように条件付きアクセス ポリシーの設定を構成してあった場合は、[このトピックの手順](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients)を参照して、**Azure Portal で EAS 条件付きアクセス ポリシーの設定の再割り当て**を行います。</span><span class="sxs-lookup"><span data-stu-id="82cdd-120">If you have your conditional access policy settings configured to use Exchange ActiveSync (EAS) in the Intune classic portal, see the [instructions in this topic](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) to **reassign EAS conditional access policy settings in the Azure portal**.</span></span>

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a><span data-ttu-id="82cdd-121">Intune クラシック ポータルでデバイス ベースの条件付きアクセス ポリシーを確認するには</span><span class="sxs-lookup"><span data-stu-id="82cdd-121">To verify your device-based conditional access policies in the Intune classic portal</span></span>

1.  <span data-ttu-id="82cdd-122">[Intune クラシック ポータル](https://manage.microsoft.com)に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-122">Go to the [Intune classic portal](https://manage.microsoft.com), and sign in with your credentials.</span></span>

2.  <span data-ttu-id="82cdd-123">左側のメニューから **[ポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-123">Choose **Policy** from the left menu.</span></span>

3.  <span data-ttu-id="82cdd-124">**[条件付きアクセス]** を選んだ後、条件付きアクセス ポリシーを作成した対象の Microsoft クラウド サービス (Exchange Online、SharePoint Online など) を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-124">Choose **Conditional access**, and then select the Microsoft cloud service (for example, Exchange Online or SharePoint Online) you created a conditional access policy for.</span></span>

4.  <span data-ttu-id="82cdd-125">条件付きアクセスの設定を記録し、それを参考にして、Azure Portal で同じ条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-125">Take note of your conditional access settings, and refer to these when you create the same conditional access policies in the Azure portal.</span></span>

### <a name="app-and-device-based-conditional-access-policies-working-together"></a><span data-ttu-id="82cdd-126">連携するアプリ ベースとデバイス ベースの条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="82cdd-126">App and device-based conditional access policies working together</span></span>

<span data-ttu-id="82cdd-127">Azure Portal の **[Intune アプリ保護]** ブレードで、管理者は、Intune アプリ保護ポリシーをサポートするアプリのみが会社リソースへのアクセスを許可されるように、アプリ ベースの条件付きルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-127">The **Intune App Protection** blade in the Azure portal enables admins to set app-based conditional rules so that only apps that support the Intune app protection policies are allowed access to corporate resources.</span></span> <span data-ttu-id="82cdd-128">アプリ ベースの条件付きアクセス ポリシーとデバイス ベースの条件付きアクセス ポリシーを併用することができます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-128">You can choose to overlap these app-based conditional access policies by using device-based conditional access policies.</span></span> <span data-ttu-id="82cdd-129">デバイス ベースとアプリ ベースの条件付きポリシーを組み合わせることも (論理 AND)、どちらか一方だけを提供することも (論理 OR) できます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-129">You can combine the device-based and app-based conditional policies (logical AND), or you can provide either option (logical OR).</span></span> <span data-ttu-id="82cdd-130">条件付きアクセス ポリシーの要件に応じて次のようになります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-130">If your conditional access policy requirements are to:</span></span>

- <span data-ttu-id="82cdd-131">準拠したデバイスが必要、**かつ**、承認されたアプリを使用。</span><span class="sxs-lookup"><span data-stu-id="82cdd-131">Require a compliant device **AND** use the approved app.</span></span>
    - <span data-ttu-id="82cdd-132">[Azure Active Directory の条件付きアクセス ブレード](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)と [Intune のアプリ保護ブレード](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0)を使って、条件付きアクセス ポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-132">You should set your conditional access policy by using the [Azure Active Directory conditional access blade](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) and the [Intune App Protection blade](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).</span></span>
<br /><br />
- <span data-ttu-id="82cdd-133">準拠したデバイスが必要、**または**、承認されたアプリを使用。</span><span class="sxs-lookup"><span data-stu-id="82cdd-133">Require a compliant device **OR** use the approved app.</span></span>
    - <span data-ttu-id="82cdd-134">[Intune クラシック ポータル](https://manage.microsoft.com)と [Intune のアプリ保護ブレード](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0)を使って、条件付きアクセス ポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-134">You should set your conditional access policy by using the [Intune classic portal](https://manage.microsoft.com) and the [Intune App Protection blade](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).</span></span>

> [!TIP] 
> <span data-ttu-id="82cdd-135">このトピックでは、Intune クラシック ポータルと Azure Portal のユーザー エクスペリエンスを比較するスクリーンショットを示します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-135">This topic provides screenshots comparing the user experience in both the Intune classic portal and the Azure portal.</span></span>

## <a name="reassign-intune-device-based-conditional-access-policies"></a><span data-ttu-id="82cdd-136">Intune のデバイス ベース条件付きアクセス ポリシーの再割り当てを行う</span><span class="sxs-lookup"><span data-stu-id="82cdd-136">Reassign Intune device-based conditional access policies</span></span>

1. <span data-ttu-id="82cdd-137">[Azure Portal の [条件付きアクセス]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-137">Go to [Conditional access in the Azure portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies), and sign in with your credentials.</span></span>

2. <span data-ttu-id="82cdd-138">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-138">Choose **New policy**.</span></span>

3. <span data-ttu-id="82cdd-139">ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-139">Provide a name for the policy.</span></span>

4. <span data-ttu-id="82cdd-140">**[割り当て]** セクションで、新しい条件付きアクセス ポリシーの対象として **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-140">Under the **Assignments section**, choose **Users and groups** to target the new conditional access policy.</span></span>
    
    ![Intune ポータルと Azure Portal のユーザー グループ UI の比較](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="82cdd-142">Azure Portal で行う選択は、クラシック ポータルに対して行った選択と対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-142">The selection you make for the Azure portal should correspond to the selection you made for the Classic portal.</span></span> <span data-ttu-id="82cdd-143">たとえば、Intune クラシック ポータルですべてのユーザーを選んだ場合は、Azure Portal でも **[すべてのユーザー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-143">For example, if you have all users selected in the Intune classic portal, select **All users** in the Azure portal.</span></span> <span data-ttu-id="82cdd-144">さらに、Intune クラシック ポータルで **[除外グループ]** オプションを選んだ場合は、Azure Portal でもそのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-144">Additionally, if you’ve chosen the **Exempt groups** option in the Intune classic portal, also exclude those select groups in the Azure portal.</span></span>

5. <span data-ttu-id="82cdd-145">グループを選んだ後、**[選択]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-145">After you choose your group, click **Select**, and then click **Done**.</span></span>

6. <span data-ttu-id="82cdd-146">**[割り当て]** セクションで **[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-146">Under the **Assignments** section, choose **Cloud apps**.</span></span>

7. <span data-ttu-id="82cdd-147">**[クラウド アプリ]** ブレードで、**[アプリを選択]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-147">On the **Cloud apps** blade, choose **Select apps**.</span></span>

8. <span data-ttu-id="82cdd-148">新しい条件付きアクセス ポリシーを適用するアプリを選び、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-148">Choose the app you want to apply the new conditional access policy to, and click **Select**.</span></span>

9. <span data-ttu-id="82cdd-149">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-149">Click **Done**.</span></span>

    ![Intune ポータルと Azure Portal のクラウド アプリ UI の比較](./media/reassign-ca-3.png)

    > [!TIP] 
    > <span data-ttu-id="82cdd-151">同じポリシーを複数のアプリに適用してある場合は、Azure Portal では 1 つのポリシーに統合することを検討します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-151">If you have multiple apps with the same policy, consider consolidating them into a single policy in the Azure portal.</span></span>

10. <span data-ttu-id="82cdd-152">**[割り当て]** セクションで **[条件]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-152">Under the **Assignments** section, choose **Conditions**.</span></span>

11. <span data-ttu-id="82cdd-153">**[条件]** ブレードで **[デバイス プラットフォーム]** を選び、該当するデバイス プラットフォームを選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-153">On the **Conditions** blade, choose **Device platforms**, and then choose the applicable device platforms.</span></span>

12. <span data-ttu-id="82cdd-154">デバイス プラットフォームの選択が終わったら、**[完了]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-154">When you are finished choosing the device platforms, click **Done** twice.</span></span>

    ![Intune ポータルと Azure Portal のデバイス プラットフォーム UI の比較](./media/reassign-ca-4.png)

    > [!TIP] 
    > <span data-ttu-id="82cdd-156">Intune クラシック ポータルで個別のプラットフォームを選択してあった場合は、Azure Portal でも個別のプラットフォームを選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-156">If you have chosen individual platforms in the Intune classic portal, choose the individual platforms in the Azure portal.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="82cdd-157">後で Windows に対するドメイン参加または準拠オプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-157">You can specify the domain join or compliant options for Windows later.</span></span>

13. <span data-ttu-id="82cdd-158">**[割り当て]** セクションで **[条件]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-158">Under the **Assignments** section, choose **Conditions**.</span></span>

14. <span data-ttu-id="82cdd-159">**[条件]** ブレードで **[クライアント アプリ]** を選び、該当するクライアント アプリを選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-159">On the **Conditions** blade, choose **Client apps**, and then choose the applicable client app.</span></span>

15. <span data-ttu-id="82cdd-160">クライアント アプリの選択が終わったら、**[完了]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-160">When you have finished choosing the client app, click **Done** twice.</span></span>

    ![Intune ポータルと Azure Portal のクライアント アプリ UI の比較](./media/reassign-ca-6.png)

16. <span data-ttu-id="82cdd-162">Intune クラシック ポータルでブラウザーの設定を選択していた場合は、Azure Portal で **[ブラウザー]** と **[モバイル アプリとデスクトップ クライアント]** の両方を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-162">If you have chosen the browser settings in the Intune classic portal, select both **Browser** and **Mobile apps and desktop clients** in the Azure portal.</span></span> <span data-ttu-id="82cdd-163">Intune クラシック ポータルでブラウザーの設定を選択していなかった場合は、**[モバイル アプリとデスクトップ クライアント]** だけを選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-163">In case you have not chosen the browser settings in the Intune classic portal, choose **Mobile apps and desktop clients** only.</span></span> 

17. <span data-ttu-id="82cdd-164">**[アクセス制御]** セクションで **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-164">Under the **Access controls** section, choose **Grant**.</span></span>

18. <span data-ttu-id="82cdd-165">**[Grant Access Controls]\(アクセス制御の許可\)** で **[デバイスは準拠としてマーク済みである必要があります]** をオンにし、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-165">Under **Grant Access Controls**, choose **Require device to be marked as compliant**, and then click **Select**.</span></span>

19. <span data-ttu-id="82cdd-166">ドメインに参加している Windows デバイスを要求するポリシーがあり、Intune に登録された準拠している Windows デバイスも許可する場合は、**[ドメインに参加しているデバイスが必要です]** および **[デバイスは準拠としてマーク済みである必要があります]** と共に **[選択したコントロールのいずれかが必要]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-166">If you have a policy to require domain joined Windows devices, and you also allow Intune-enrolled and compliant Windows devices, choose **Require domain joined device** and **Require device to be marked as compliant**, along with **Require one of the selected controls**.</span></span>

20. <span data-ttu-id="82cdd-167">Intune に登録された準拠している Windows デバイスを許可しない場合は、現在のポリシーから Windows ポリシーを除外します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-167">If you do not allow Intune enrolled and compliant Windows devices, exempt the Windows policy from the current policy.</span></span> <span data-ttu-id="82cdd-168">その後、**[デバイス プラットフォーム]** を **[Windows]** に設定したポリシーを別に作成し、他の条件は上記と同じように設定して、**[Grant Access Controls]\(アクセス制御の許可\)** で **[ドメインに参加しているデバイスが必要です]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-168">Then create a separate policy with **Device platforms** set to **Windows**, include the other conditions as set per above, and choose **Require domain joined device** under **Grant Access Controls**.</span></span>

21. <span data-ttu-id="82cdd-169">**[新規]** 条件付きアクセス ポリシー ブレードで、**[ポリシーを有効にする]** をオンにして、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-169">On the **New** conditional access policy blade, turn on the **Enable policy** toggle, and then click **Create**.</span></span>

    ![Intune ポータルと Azure Portal の条件付きアクセス ポリシー有効化 UI の比較](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a><span data-ttu-id="82cdd-171">EAS クライアントに対する Intune のデバイス ベースの条件付きアクセス ポリシーの再割り当てを行う</span><span class="sxs-lookup"><span data-stu-id="82cdd-171">Reassign Intune device-based conditional access policies for EAS clients</span></span>

<span data-ttu-id="82cdd-172">Intune クラシック ポータルで Exchange Online のポリシーの一部として Exchange Active Sync の設定を構成していた場合は、Azure Portal で 2 番目の条件付きアクセス ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-172">If you have configured Exchange ActiveSync settings as part of an Exchange Online policy in the Intune classic portal, you need to create a second conditional access policy in the Azure portal.</span></span>

1. <span data-ttu-id="82cdd-173">[Azure Portal の [条件付きアクセス]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-173">Go to [Conditional access in the Azure portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies), and sign in with your credentials.</span></span>

2. <span data-ttu-id="82cdd-174">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-174">Choose **New policy**.</span></span>

3. <span data-ttu-id="82cdd-175">ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="82cdd-175">Provide a name for the policy.</span></span>

4. <span data-ttu-id="82cdd-176">**[割り当て]** セクションで、新しい条件付きアクセス ポリシーの対象として **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-176">Under the **Assignments** section, choose **Users and groups** to target the new conditional access policy.</span></span>

    ![Intune ポータルと Azure Portal のユーザー グループ UI の比較](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="82cdd-178">Azure Portal で行う選択は、Azure Portal に対して行った選択と対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-178">The selection you make for the Azure portal should correspond to the selection you made for the Azure portal.</span></span> <span data-ttu-id="82cdd-179">たとえば、Intune クラシック ポータルですべてのユーザーを選んだ場合は、Azure Portal でも **[すべてのユーザー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-179">For example, if you have all users selected in the Intune classic portal, select **All users** in the Azure portal.</span></span> <span data-ttu-id="82cdd-180">さらに、Intune クラシック ポータルで **[除外グループ]** オプションを選んだ場合は、Azure Portal でもそのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-180">Additionally, if you’ve chosen the **Exempt groups** option in the Intune classic portal, also exclude those select groups in the Azure portal.</span></span>

5. <span data-ttu-id="82cdd-181">グループを選んだ後、**[選択]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-181">After you choose your group, click **Select**, and then click **Done**.</span></span>

6. <span data-ttu-id="82cdd-182">**[割り当て]** セクションで **[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-182">Under the **Assignments** section, choose **Cloud apps**.</span></span>

7. <span data-ttu-id="82cdd-183">**[クラウド アプリ]** ブレードで、**[アプリの選択]** をクリックし、**[Exchange Online]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-183">On the **Cloud apps** blade, click **Select apps**, and choose **Exchange Online**.</span></span> <span data-ttu-id="82cdd-184">その後、**[選択]**、**[完了]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-184">Then click **Select** and **Done**.</span></span>

    ![Intune ポータルと Azure Portal のクラウド アプリ UI の比較](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="82cdd-186">EAS クライアントの条件付きアクセス ポリシーに他のクラウド アプリを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="82cdd-186">Conditional access policies for EAS clients cannot include any other cloud app.</span></span>

8. <span data-ttu-id="82cdd-187">**[条件]** ブレードで **[クライアント アプリ]** を選び、該当するクライアント アプリを選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-187">On the **Conditions** blade, choose **Client apps**, and then choose the applicable client app.</span></span> <span data-ttu-id="82cdd-188">Intune でサポートされていないクライアントのブロックを選択してあった場合は、**[サポートされているプラットフォームのみにポリシーを適用する]** オプションを使います。</span><span class="sxs-lookup"><span data-stu-id="82cdd-188">If you have chosen to block clients that aren’t supported by Intune, use the **Apply policy only to supported platforms** option.</span></span>

    ![Intune ポータルと Azure Portal のクライアント アプリ UI の比較](./media/reassign-ca-15.png)

9. <span data-ttu-id="82cdd-190">クライアント アプリの選択が終わったら、**[完了]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-190">When you have finished choosing the client app, click **Done** twice.</span></span>

10. <span data-ttu-id="82cdd-191">**[アクセス制御]** セクションで **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-191">Under the **Access controls** section, choose **Grant**.</span></span>

11. <span data-ttu-id="82cdd-192">**[Grant Access Controls]\(アクセス制御の許可\)** で **[デバイスは準拠としてマーク済みである必要があります]** をオンにし、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-192">Under **Grant Access Controls**, choose **Require device to be marked as compliant**, and then click **Select**.</span></span>

    ![Intune ポータルと Azure Portal のアクセス許可 UI の比較](./media/reassign-ca-16.png)

12. <span data-ttu-id="82cdd-194">**[新規]** 条件付きアクセス ポリシー ブレードで、**[ポリシーを有効にする]** をオンにして、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-194">On the **New** conditional access policy blade, turn on the **Enable policy** toggle, and then click **Create**.</span></span>

    ![Intune ポータルと Azure Portal の条件付きアクセス ポリシー有効化 UI の比較](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a><span data-ttu-id="82cdd-196">Intune クラシック ポータルで条件付きアクセス ポリシーを無効にする</span><span class="sxs-lookup"><span data-stu-id="82cdd-196">Disable conditional access policies in the Intune classic portal</span></span>

<span data-ttu-id="82cdd-197">Azure Portal で条件付きアクセス ポリシーの再割り当てを行った後は、Intune クラシック ポータルで以前に作成した条件付きアクセス ポリシーを段階的に無効にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="82cdd-197">After you have reassigned your conditional access policies in the Azure portal, it's important to gradually disable the conditional access policies previously created in the Intune classic portal.</span></span> <span data-ttu-id="82cdd-198">さらに、同じセキュリティ グループを使って、Azure Portal で作成した条件付きアクセス ポリシーを適用することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="82cdd-198">Additionally, you might need to use the same security group to apply the conditional access policies created in the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="82cdd-199">Intune クラシック ポータルで条件付きアクセス ポリシーを無効にする前に、このトピックの「[始める前に](#before-you-begin)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82cdd-199">Before disabling your conditional access policies in the Intune classic portal, see the [Before you begin](#before-you-begin) section at the beginning of this topic.</span></span>

### <a name="to-disable-the-conditional-access-policies"></a><span data-ttu-id="82cdd-200">条件付きアクセス ポリシーを無効にするには</span><span class="sxs-lookup"><span data-stu-id="82cdd-200">To disable the conditional access policies</span></span>

1.  <span data-ttu-id="82cdd-201">[Intune クラシック ポータル](https://manage.microsoft.com)に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-201">Go to the [Intune classic portal](https://manage.microsoft.com), and sign in with your credentials.</span></span>

2.  <span data-ttu-id="82cdd-202">左側のメニューから **[ポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-202">Choose **Policy** from the left menu.</span></span>

3.  <span data-ttu-id="82cdd-203">**[条件付きアクセス]** を選んだ後、条件付きアクセス ポリシーを作成した対象の Microsoft クラウド サービス (Exchange Online、SharePoint Online など) を選びます。</span><span class="sxs-lookup"><span data-stu-id="82cdd-203">Choose **Conditional access**, and then select the Microsoft cloud service (for example, Exchange Online or SharePoint Online) that you created a conditional access policy for.</span></span>

4.  <span data-ttu-id="82cdd-204">**[条件付きアクセス ポリシーを有効にする]** オプションをオフにした後、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82cdd-204">Uncheck the option **Enable conditional access policy**, and then click **Save**.</span></span>

    ![Intune クラシック ポータルで条件付きアクセス ポリシーを無効にする](./media/reassign-ca-18.png)

## <a name="see-also"></a><span data-ttu-id="82cdd-206">関連項目</span><span class="sxs-lookup"><span data-stu-id="82cdd-206">See also</span></span>

- [<span data-ttu-id="82cdd-207">Intune での条件付きアクセスの一般的な使用方法</span><span class="sxs-lookup"><span data-stu-id="82cdd-207">Common ways to use conditional access with Intune</span></span>](conditional-access-intune-common-ways-use.md)
- [<span data-ttu-id="82cdd-208">Intune でのアプリ ベースの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="82cdd-208">app-based conditional access with Intune</span></span>](app-based-conditional-access-intune.md)
- [<span data-ttu-id="82cdd-209">Azure Active Directory の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="82cdd-209">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
