---
title: "Skype for Business Online を保護する"
description: "条件付きアクセスを使って、Skype for Business Online へのアクセスを保護および制御します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 656015e489d978b705442f71a98921fe126bb1e2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="protect-access-to-skype-for-business-online-with-microsoft-intune"></a><span data-ttu-id="33faa-103">Microsoft Intune で Skype for Business Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="33faa-103">Protect access to Skype for Business Online with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="33faa-104">**Skype for Business Online** の条件付きアクセス ポリシーを使って、Skype for Business Online へのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="33faa-104">You can use a conditional access policy for **Skype for Business Online** to control access to Skype for Business Online.</span></span>
<span data-ttu-id="33faa-105">条件付きアクセスには、2 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="33faa-105">Conditional access has two components:</span></span>
- <span data-ttu-id="33faa-106">デバイス コンプライアンス ポリシー。準拠したデバイスと見なされるには、このポリシーに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="33faa-106">A device compliance policy that the device must comply with in order to be considered compliant.</span></span>
- <span data-ttu-id="33faa-107">条件付きアクセス ポリシー。デバイスがサービスにアクセスするために満たす必要のある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="33faa-107">A conditional access policy where you specify the conditions that the device must meet in order for you to access the service.</span></span>
<span data-ttu-id="33faa-108">条件付きアクセスの動作の詳細については、「[電子メールと O365 サービスへのアクセスを保護する](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="33faa-108">To learn more about how conditional access works, read the [Protect access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

<span data-ttu-id="33faa-109">対象となるユーザーがデバイスで Skype for Business Online を使用しようとすると、次の評価が行われます。</span><span class="sxs-lookup"><span data-stu-id="33faa-109">When a targeted user attempts to use Skype for Business Online on their device, the following evaluation occurs:</span></span>

![デバイスに Skype for Business Online へのアクセスを許可するかブロックするかを判断する決定ポイントを示す図](../media/ConditionalAccess_SkypeforBusiness.png)

<span data-ttu-id="33faa-111">Skype for Business Online の条件付きアクセス ポリシーを構成する**前に**、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="33faa-111">**Before** configuring a conditional access policy for Skype for Business Online, you must:</span></span>
- <span data-ttu-id="33faa-112">**Skype for Business Online サブスクリプション**を取得し、Skype for Business Online のライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="33faa-112">Have a **Skype for Business Online subscription** and assign the Skype for Business Online license to users.</span></span>
- <span data-ttu-id="33faa-113">**Enterprise Mobility + Security (EMS) サブスクリプション**または **Azure Active Directory (Azure AD) Premium サブスクリプション**を取得します。ユーザーに EMS または Azure AD のライセンスを付与します。</span><span class="sxs-lookup"><span data-stu-id="33faa-113">Have an **Enterprise Mobility + Security (EMS) subscription** or an **Azure Active Directory (Azure AD) Premium subscription**, and have users be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="33faa-114">詳細については、「[Enterprise Mobility pricing](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing)」 (Enterprise Mobility の価格) または「[Azure Active Directory の価格](https://azure.microsoft.com/pricing/details/active-directory/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33faa-114">For more details, see [Enterprise Mobility pricing](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

-   <span data-ttu-id="33faa-115">Skype for Business Online で[先進認証を有効](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)にします。</span><span class="sxs-lookup"><span data-stu-id="33faa-115">[Enable modern authentication](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune) for Skype for Business Online.</span></span>
-  <span data-ttu-id="33faa-116">すべてのエンド ユーザーに **Skype for Business Online** を使わせます。</span><span class="sxs-lookup"><span data-stu-id="33faa-116">Have all your users using **Skype for Business Online**.</span></span> <span data-ttu-id="33faa-117">展開に Skype for Business Online とオンプレミスの Skype for Business の両方が含まれる場合は、ユーザーに条件付きアクセス ポリシーが適用されません。</span><span class="sxs-lookup"><span data-stu-id="33faa-117">If you have a deployment with both Skype for Business Online and Skype for Business on-premises, the conditional access policy will not be applied to users.</span></span>

<span data-ttu-id="33faa-118">Skype for Business Online にアクセスするデバイスは、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="33faa-118">The device that needs access to Skype for Business Online must:</span></span>

-   <span data-ttu-id="33faa-119">**Android** デバイスまたは **iOS** デバイスである。</span><span class="sxs-lookup"><span data-stu-id="33faa-119">Be an **Android** or **iOS** device.</span></span>

-   <span data-ttu-id="33faa-120">Intune に**登録**されている。</span><span class="sxs-lookup"><span data-stu-id="33faa-120">Be **enrolled** with Intune.</span></span>

-   <span data-ttu-id="33faa-121">展開されているすべての Intune コンプライアンス ポリシーに**準拠**している。</span><span class="sxs-lookup"><span data-stu-id="33faa-121">Be **compliant** with any deployed Intune compliance policies.</span></span>


<span data-ttu-id="33faa-122">デバイスの状態は Azure Active Directory に格納され、指定した条件に基づいて、アクセスが許可されたりブロックされたりします。</span><span class="sxs-lookup"><span data-stu-id="33faa-122">The device state is stored in Azure Active Directory, which grants or blocks access based on the conditions that you specify.</span></span>

<span data-ttu-id="33faa-123">条件が満たされない場合、ユーザーにはサインイン時に以下のうちのいずれかのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33faa-123">If a condition is not met, the user is presented with one of the following messages when they sign in:</span></span>

-   <span data-ttu-id="33faa-124">デバイスが Intune または Azure Active Directory に登録されていない場合は、会社ポータルのアプリをインストールおよび登録する手順を含むメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33faa-124">If the device is not enrolled with Intune or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>

-   <span data-ttu-id="33faa-125">デバイスがポリシーに準拠していない場合は、ユーザーを Intune ポータル サイト Web サイトやポータル サイト アプリに導くメッセージが表示されます。このポータルで、問題とその修正方法に関する情報を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="33faa-125">If the device is not compliant, a message is displayed that directs the user to the Intune Company Portal website or Company Portal app, where they can find information about the problem and how to fix it.</span></span>

## <a name="configure-conditional-access-for-skype-for-business-online"></a><span data-ttu-id="33faa-126">Skype for Business Online の条件付きアクセスの構成</span><span class="sxs-lookup"><span data-stu-id="33faa-126">Configure conditional access for Skype for Business Online</span></span>

### <a name="step-1-configure-azure-active-directory-security-groups"></a><span data-ttu-id="33faa-127">手順 1. Azure Active Directory セキュリティ グループを構成する</span><span class="sxs-lookup"><span data-stu-id="33faa-127">Step 1: Configure Azure Active Directory security groups</span></span>
<span data-ttu-id="33faa-128">開始する前に、条件付きアクセス ポリシーの Azure Active Directory セキュリティ グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="33faa-128">Before you start, configure Azure Active Directory security groups for the conditional access policy.</span></span> <span data-ttu-id="33faa-129">これらのグループは、**Office 365 管理センター**で構成できます。</span><span class="sxs-lookup"><span data-stu-id="33faa-129">You can configure these groups in the **Office 365 admin center**.</span></span> <span data-ttu-id="33faa-130">これらのグループは、ユーザーをポリシーの対象とするか、または除外するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="33faa-130">These groups will be used to target or exempt users from the policy.</span></span> <span data-ttu-id="33faa-131">ユーザーがポリシーの対象となる場合、ユーザーに使用される各デバイスがリソースにアクセスするには、ポリシーを遵守している必要があります。</span><span class="sxs-lookup"><span data-stu-id="33faa-131">When a user is targeted by the policy, each device they use must be compliant in order to access resources.</span></span>

<span data-ttu-id="33faa-132">Skype for Business ポリシーに対して使用する 2 つのグループの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="33faa-132">You can specify two group types to use for the Skype for Business policy:</span></span>

-   <span data-ttu-id="33faa-133">**対象グループ**: ポリシーを適用するユーザーのグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="33faa-133">**Targeted groups**: Contains groups of users that the policy applies to.</span></span>

-   <span data-ttu-id="33faa-134">**例外グループ**: ポリシーから除外されるユーザーのグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="33faa-134">**Exempted groups**: Contains groups of users that are exempt from the policy.</span></span>

<span data-ttu-id="33faa-135">ユーザーが両方のグループに含まれている場合は、ポリシーから除外されます。</span><span class="sxs-lookup"><span data-stu-id="33faa-135">If a user is in both groups, they will be exempt from the policy.</span></span>

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a><span data-ttu-id="33faa-136">手順 2. コンプライアンス ポリシーを構成し、展開する</span><span class="sxs-lookup"><span data-stu-id="33faa-136">Step 2: Configure and deploy a compliance policy</span></span>
<span data-ttu-id="33faa-137">コンプライアンス ポリシーを[作成](create-a-device-compliance-policy-in-microsoft-intune.md)し、ポリシーによって影響を受けるすべてのデバイスに[展開](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)します。</span><span class="sxs-lookup"><span data-stu-id="33faa-137">[Create](create-a-device-compliance-policy-in-microsoft-intune.md) and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy to all devices that will be affected by the policy.</span></span> <span data-ttu-id="33faa-138">これは、**対象グループ**内のユーザーによって使用されるすべてのデバイスです。</span><span class="sxs-lookup"><span data-stu-id="33faa-138">These will be all the devices that are used by the users in the **Targeted groups**.</span></span>

> [!NOTE]
> <span data-ttu-id="33faa-139">コンプライアンス ポリシーは Intune グループに展開されますが、条件付きアクセス ポリシーは、Azure Active Directory セキュリティ グループを対象とします。</span><span class="sxs-lookup"><span data-stu-id="33faa-139">While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="33faa-140">コンプライアンス ポリシーを展開していない場合は、デバイスがポリシーに準拠しているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="33faa-140">If you haven't deployed a compliance policy, the devices will be treated as compliant.</span></span>

<span data-ttu-id="33faa-141">準備ができたら、**手順 3** に進みます。</span><span class="sxs-lookup"><span data-stu-id="33faa-141">When you're ready, continue to **Step 3**.</span></span>

### <a name="step-3-configure-the-skype-for-business-online-policy"></a><span data-ttu-id="33faa-142">手順 3. Skype for Business Online ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="33faa-142">Step 3: Configure the Skype for Business Online policy</span></span>
<span data-ttu-id="33faa-143">次に、管理デバイスおよび準拠デバイスのみが Skype for Business Online にアクセスできるように要求するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="33faa-143">Next, configure the policy to require that only managed and compliant devices can access Skype for Business Online.</span></span> <span data-ttu-id="33faa-144">このポリシーは、Azure Active Directory に格納されます。</span><span class="sxs-lookup"><span data-stu-id="33faa-144">This policy will be stored in Azure Active Directory.</span></span>

1.  <span data-ttu-id="33faa-145">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** > **[条件付きアクセス]** > **[Skype for Business Online ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="33faa-145">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Conditional Access** > **Skype for Business Online Policy**.</span></span>

  ![Skype for Business Online の条件付きアクセス ポリシー ページのスクリーンショット](./media/conditional_access_SFBPolicy.png)

2.  <span data-ttu-id="33faa-147">**[条件付きアクセス ポリシーを有効にする]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="33faa-147">Choose **Enable conditional access policy**.</span></span>

3.  <span data-ttu-id="33faa-148">**[アプリケーション アクセス]** で、条件付きアクセス ポリシーを適用する対象を次のように選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="33faa-148">Under **Application access**, you can choose to apply conditional access policy to:</span></span>

    -   <span data-ttu-id="33faa-149">**iOS**</span><span class="sxs-lookup"><span data-stu-id="33faa-149">**iOS**</span></span>

    -   <span data-ttu-id="33faa-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="33faa-150">**Android**</span></span>

4.  <span data-ttu-id="33faa-151">**[対象グループ]**で、**[変更]** を選択して、ポリシーを適用する Azure Active Directory セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="33faa-151">Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy will apply to.</span></span> <span data-ttu-id="33faa-152">すべてのユーザーを対象にすることも、選んだユーザーのグループのみを対象にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="33faa-152">You can choose to target this to all users or just a select group of users.</span></span>

5.  <span data-ttu-id="33faa-153">**[例外グループ]**で、必要に応じて **[変更]** を選択して、このポリシーから除外する Azure Active Directory セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="33faa-153">Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.</span></span>

6.  <span data-ttu-id="33faa-154">終了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33faa-154">When you're done, choose **Save**.</span></span>

<span data-ttu-id="33faa-155">これで、Skype for Business Online の条件付きアクセスの構成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="33faa-155">You have now configured conditional access for Skype for Business Online.</span></span> <span data-ttu-id="33faa-156">条件付きアクセス ポリシーを展開する必要はありません。直ちに有効になります。</span><span class="sxs-lookup"><span data-stu-id="33faa-156">You don't have to deploy the conditional access policy—it takes effect immediately.</span></span>


## <a name="monitor-the-compliance-and-conditional-access-policies"></a><span data-ttu-id="33faa-157">コンプライアンスと条件付きアクセス ポリシーを監視する</span><span class="sxs-lookup"><span data-stu-id="33faa-157">Monitor the compliance and conditional access policies</span></span>
<span data-ttu-id="33faa-158">**[グループ]** ワークスペースで、デバイスの条件付きアクセスの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="33faa-158">In the **Groups** workspace, you can view the conditional access status of your devices.</span></span>

<span data-ttu-id="33faa-159">任意のモバイル デバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="33faa-159">Select any mobile device group.</span></span> <span data-ttu-id="33faa-160">次に、**[デバイス]** タブで、次のいずれかの **[フィルター]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33faa-160">Then, on the **Devices** tab, choose one of the following **Filters**:</span></span>

* <span data-ttu-id="33faa-161">**AAD に登録されていないデバイス**: これらのデバイスは Skype for Business Online からブロックされます。</span><span class="sxs-lookup"><span data-stu-id="33faa-161">**Devices that are not registered with AAD**: These devices are blocked from Skype for Business Online.</span></span>

* <span data-ttu-id="33faa-162">**準拠していないデバイス**: これらのデバイスは Skype for Business Online からブロックされます。</span><span class="sxs-lookup"><span data-stu-id="33faa-162">**Devices that are not compliant**: These devices are blocked from Skype for Business Online.</span></span>

* <span data-ttu-id="33faa-163">**AAD に登録され、準拠しているデバイス**: これらのデバイスは、Skype for Business Online にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="33faa-163">**Devices that are registered with AAD and compliant**: These devices can access Skype for Business Online.</span></span>
