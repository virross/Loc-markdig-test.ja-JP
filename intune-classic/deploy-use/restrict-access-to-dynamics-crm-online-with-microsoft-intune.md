---
title: "Dynamics CRM Online を保護する"
description: "条件付きアクセスで Dynamics CRM Online へのアクセスを保護および制御します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e285f3f7c68e9e6b0477e6a8af99f678aa1fe980
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="protect-access-to-dynamics-crm-online-with-intune"></a><span data-ttu-id="3fe8f-103">Intune で Dynamics CRM Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="3fe8f-103">Protect access to Dynamics CRM Online with Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="3fe8f-104">Microsoft Intune の条件付きアクセスを使用して、iOS および Android デバイスから Microsoft Dynamics CRM Online へのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-104">You can control access to Microsoft Dynamics CRM Online from iOS and Android devices by using Microsoft Intune conditional access.</span></span>  <span data-ttu-id="3fe8f-105">Intune の条件付きアクセスには、次の 2 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-105">Intune conditional access has two components:</span></span>
* <span data-ttu-id="3fe8f-106">[デバイス コンプライアンス ポリシー](introduction-to-device-compliance-policies-in-microsoft-intune.md)。準拠したデバイスと見なされるには、このポリシーに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-106">A [device compliance policy](introduction-to-device-compliance-policies-in-microsoft-intune.md) that the device must comply with in order to be considered compliant.</span></span>
* <span data-ttu-id="3fe8f-107">[条件付きアクセス ポリシー](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)。デバイスがサービスにアクセスするために満たす必要のある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-107">A [conditional access policy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) where you specify the conditions that the device must meet in order to access the service.</span></span>

<span data-ttu-id="3fe8f-108">条件付きアクセスの動作の詳細については、「[Microsoft Intune で電子メール、Office 365、およびその他のサービスへのアクセスを制限する](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)」という記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-108">To learn more about how conditional access works, read the [protect access to email, 0365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fe8f-109">条件付きアクセスを展開するには、Intune および Azure Active Directory Premium のサブスクリプションが必要です。ユーザーに両方のライセンスが付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-109">To deploy conditional access, you must have subscriptions for Intune and Azure Active Directory Premium, and users must be licensed for both products.</span></span> <span data-ttu-id="3fe8f-110">**Enterprise Mobility + Security (EMS) のサブスクリプション**には、Intune および Azure Active Directory Premium のサブスクリプションが両方とも含まれます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-110">The **Enterprise Mobility + Security (EMS) subscription** includes both Intune and Azure Active Directory Premium subscriptions.</span></span> <span data-ttu-id="3fe8f-111">詳細については、「[Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing)」 (Enterprise Mobility の価格) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-111">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing).</span></span> <span data-ttu-id="3fe8f-112">EMS のサブスクリプションを持っていない場合は、Azure Active Directory Premium のサブスクリプションを取得できます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-112">If you don't have the EMS subscription, you can get a subscription for Azure Active Directory Premium.</span></span> <span data-ttu-id="3fe8f-113">「[Azure Active Directory の価格](https://azure.microsoft.com/pricing/details/active-directory/)」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-113">See the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

<span data-ttu-id="3fe8f-114">対象となるユーザーがデバイスで Dynamics CRM アプリを使用しようとすると、次の評価が行われます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-114">When a targeted user attempts to use the Dynamics CRM app on their device, the following evaluation occurs:</span></span>

![図は、デバイスがサービスへのアクセスを許可されているか、またはブロックされているかを決定するために使用する判断ポイントを示しています](../media/mdm-ca-dynamics-crm-flow-diagram.png)

<span data-ttu-id="3fe8f-116">Dynamics CRM Online にアクセスするデバイスは、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-116">The device that needs access to Dynamics CRM Online must be:</span></span>
* <span data-ttu-id="3fe8f-117">**Android** デバイスまたは **iOS** デバイスである。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-117">An **Android** or **iOS** device.</span></span>
* <span data-ttu-id="3fe8f-118">Intune に**登録**されている。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-118">**Enrolled** with Intune.</span></span>
* <span data-ttu-id="3fe8f-119">展開されているすべての Intune コンプライアンス ポリシーに**準拠**している。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-119">**Compliant** with any deployed Intune compliance policies.</span></span>

<span data-ttu-id="3fe8f-120">デバイスの状態は Azure Active Directory に格納され、指定した条件に基づいて、アクセスが許可されたりブロックされたりします。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-120">The device state is stored in Azure Active Directory, which grants or blocks access based on the conditions that you specify.</span></span>

<span data-ttu-id="3fe8f-121">条件が満たされない場合、ユーザーにはサインイン時に以下のうちのいずれかのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-121">If a condition is not met, the user is presented with one of the following messages when they sign in:</span></span>
* <span data-ttu-id="3fe8f-122">デバイスが Intune または Azure Active Directory に登録されていない場合は、会社ポータルのアプリをインストールおよび登録する手順を含むメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-122">If the device is not enrolled with Intune or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>
* <span data-ttu-id="3fe8f-123">デバイスが準拠していない場合は、Microsoft Intune のポータル Web サイトまたはポータル サイト アプリにユーザーを誘導するメッセージが表示されます。このポータルで、ユーザーは問題とその解決方法に関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-123">If the device is not compliant, a message is displayed that directs the user to the Microsoft Intune Company Portal website or Company Portal app, where they can find information about the problem and how to remediate it.</span></span>

## <a name="configure-conditional-access-for-dynamics-crm-online"></a><span data-ttu-id="3fe8f-124">Dynamics CRM Online の条件付きアクセスの構成</span><span class="sxs-lookup"><span data-stu-id="3fe8f-124">Configure conditional access for Dynamics CRM Online</span></span>  
### <a name="step-1-configure-active-directory-security-groups"></a><span data-ttu-id="3fe8f-125">手順 1. Active Directory セキュリティ グループを構成する</span><span class="sxs-lookup"><span data-stu-id="3fe8f-125">Step 1: Configure Active Directory security groups</span></span>

<span data-ttu-id="3fe8f-126">開始する前に、条件付きアクセス ポリシーの Azure Active Directory セキュリティ グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-126">Before you start, configure Azure Active Directory security groups for the conditional access policy.</span></span> <span data-ttu-id="3fe8f-127">これらのグループは、**Office 365 管理センター**で構成できます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-127">You can configure these groups in the **Office 365 admin center**.</span></span> <span data-ttu-id="3fe8f-128">これらのグループは、ユーザーをポリシーの対象とするか、または除外するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-128">You use these groups to target or exempt users from the policy.</span></span> <span data-ttu-id="3fe8f-129">ユーザーがポリシーの対象となる場合、ユーザーに使用される各デバイスがリソースにアクセスするには、ポリシーを遵守している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-129">When a user is targeted by a policy, each device they use must be compliant in order to access resources.</span></span>

<span data-ttu-id="3fe8f-130">Dynamics CRM ポリシーに使用する 2 つのグループの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-130">You can specify two group types to use for the Dynamics CRM policy:</span></span>
* <span data-ttu-id="3fe8f-131">**対象グループ**。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-131">**Targeted groups**.</span></span> <span data-ttu-id="3fe8f-132">ポリシーを適用するユーザーのグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-132">Contains groups of users that the policy applies to.</span></span>
* <span data-ttu-id="3fe8f-133">**例外グループ**。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-133">**Exempted groups**.</span></span> <span data-ttu-id="3fe8f-134">ポリシーから除外されるユーザーのグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-134">Contains groups of users that are exempt from the policy.</span></span>

<span data-ttu-id="3fe8f-135">ユーザーが両方のグループに含まれている場合は、ポリシーから除外されます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-135">If a user is in both groups, they are exempt from the policy.</span></span>

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a><span data-ttu-id="3fe8f-136">手順 2. コンプライアンス ポリシーを構成し、展開する</span><span class="sxs-lookup"><span data-stu-id="3fe8f-136">Step 2: Configure and deploy a compliance policy</span></span>
<span data-ttu-id="3fe8f-137">コンプライアンス ポリシーを[作成](create-a-device-compliance-policy-in-microsoft-intune.md)し、ポリシーによって影響を受けるすべてのデバイスに[展開](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-137">[Create](create-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) it to all devices that will be affected by the policy.</span></span> <span data-ttu-id="3fe8f-138">これは、対象グループ内のユーザーによって使用されるすべてのデバイスです。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-138">These are all the devices that are used by the users in the Targeted groups.</span></span>

> [!NOTE]
> <span data-ttu-id="3fe8f-139">コンプライアンス ポリシーは Intune グループに展開されますが、条件付きアクセス ポリシーは、Azure Active Directory セキュリティ グループを対象とします。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-139">While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fe8f-140">コンプライアンス ポリシーを展開していない場合は、デバイスがポリシーに準拠しているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-140">If you have not deployed a compliance policy, the devices will be treated as compliant.</span></span>

<span data-ttu-id="3fe8f-141">準備ができたら、手順 3 に進みます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-141">When you are ready, continue to Step 3.</span></span>
### <a name="step-3-configure-the-dynamics-crm-policy"></a><span data-ttu-id="3fe8f-142">手順 3: Dynamics CRM ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="3fe8f-142">Step 3: Configure the Dynamics CRM policy</span></span>
<span data-ttu-id="3fe8f-143">次に、管理デバイスおよび準拠デバイスのみが Dynamics CRM にアクセスできるように必要なポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-143">Next, configure the policy to require that only managed and compliant devices can access Dynamics CRM.</span></span> <span data-ttu-id="3fe8f-144">このポリシーは、Azure Active Directory に格納されます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-144">This policy will be stored in Azure Active Directory.</span></span>

1.  <span data-ttu-id="3fe8f-145">Intune 管理コンソールで、**[ポリシー]、[条件付きアクセス]、[Dynamics CRM Online ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-145">In the Intune administration console, choose **Policy > Conditional Access > Dynamics CRM Online Policy**.</span></span>

  ![Dynamics CRM Online の条件付きアクセス ポリシー ページのスクリーンショット](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2.  <span data-ttu-id="3fe8f-147">**[条件付きアクセス ポリシーを有効にする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-147">Choose the **Enable conditional access** policy.</span></span>
3.  <span data-ttu-id="3fe8f-148">**[アプリケーション アクセス]** で、条件付きアクセス ポリシーを適用する対象を次のように選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-148">Under **Application access**, you can choose to apply conditional access policy to:</span></span>
  * <span data-ttu-id="3fe8f-149">**iOS**</span><span class="sxs-lookup"><span data-stu-id="3fe8f-149">**iOS**</span></span>
  * <span data-ttu-id="3fe8f-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="3fe8f-150">**Android**</span></span>
4.  <span data-ttu-id="3fe8f-151">**[対象グループ]**で、**[変更]** を選択して、ポリシーを適用する Azure Active Directory セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-151">Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy will apply to.</span></span> <span data-ttu-id="3fe8f-152">すべてのユーザーを対象にすることも、選んだユーザーのグループのみを対象にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-152">You can choose to target this to all users or just a select group of users.</span></span>
5.  <span data-ttu-id="3fe8f-153">**[例外グループ]**で、必要に応じて **[変更]** を選択して、このポリシーから除外する Azure Active Directory セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-153">Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.</span></span>
6.  <span data-ttu-id="3fe8f-154">終了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-154">When you are done, choose **Save**.</span></span>

<span data-ttu-id="3fe8f-155">これで、Dynamics CRM の条件付きアクセスの構成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-155">You have now configured conditional access for Dynamics CRM.</span></span> <span data-ttu-id="3fe8f-156">条件付きアクセス ポリシーを展開する必要はありません。直ちに有効になります。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-156">You do not have to deploy the conditional access policy—it takes effect immediately.</span></span>
##  <a name="monitor-the-compliance-and-conditional-access-policies"></a><span data-ttu-id="3fe8f-157">コンプライアンスと条件付きアクセス ポリシーを監視する</span><span class="sxs-lookup"><span data-stu-id="3fe8f-157">Monitor the compliance and conditional access policies</span></span>

<span data-ttu-id="3fe8f-158">**[グループ]** ワークスペースで、デバイスの条件付きアクセスの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-158">In the **Groups** workspace, you can view the conditional access status of your devices.</span></span>

<span data-ttu-id="3fe8f-159">モバイル デバイス グループを選択し、**[デバイス]** タブで、次の **[フィルター]**のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-159">Choose any mobile device group and then, on the **Devices** tab, choose one of the following **Filters**:</span></span>
* <span data-ttu-id="3fe8f-160">**AAD に登録されていないデバイス**。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-160">**Devices that are not registered with AAD**.</span></span> <span data-ttu-id="3fe8f-161">これらのデバイスは Dynamics CRM からブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-161">These devices are blocked from Dynamics CRM.</span></span>
* <span data-ttu-id="3fe8f-162">**準拠していないデバイス**。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-162">**Devices that are not compliant**.</span></span> <span data-ttu-id="3fe8f-163">これらのデバイスは Dynamics CRM からブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-163">These devices are blocked from Dynamics CRM.</span></span>
* <span data-ttu-id="3fe8f-164">**AAD に登録され、準拠しているデバイス**。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-164">**Devices that are registered with AAD and compliant**.</span></span> <span data-ttu-id="3fe8f-165">これらのデバイスで Dynamics CRM にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3fe8f-165">These devices can access Dynamics CRM.</span></span>

##  <a name="next-steps"></a><span data-ttu-id="3fe8f-166">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3fe8f-166">Next steps</span></span>
* [<span data-ttu-id="3fe8f-167">Exchange Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="3fe8f-167">Protect access to Exchange Online</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)

* [<span data-ttu-id="3fe8f-168">Exchange On-Premises へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="3fe8f-168">Protect access to Exchange on-premises</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
* [<span data-ttu-id="3fe8f-169">SharePoint Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="3fe8f-169">Protect access to SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

* [<span data-ttu-id="3fe8f-170">Skype for Business Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="3fe8f-170">Protect access to Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
