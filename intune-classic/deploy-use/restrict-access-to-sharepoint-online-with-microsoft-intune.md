---
title: "SharePoint Online を保護する"
description: "条件付きアクセスを使って、SharePoint Online の会社データへのアクセスを保護および制御します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ae08653d2390805c75ec6acd2c6b640bad9a51b2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="protect-access-to-sharepoint-online-with-microsoft-intune"></a><span data-ttu-id="4e52d-103">Microsoft Intune で SharePoint Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="4e52d-103">Protect access to SharePoint Online with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4e52d-104">Microsoft Intune の条件付きアクセスを使って、SharePoint Online 上にあるファイルへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-104">Use Microsoft Intune conditional access to control access to files that are located on SharePoint Online.</span></span>
<span data-ttu-id="4e52d-105">条件付きアクセスには、2 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-105">Conditional access has two components:</span></span>
- <span data-ttu-id="4e52d-106">デバイス コンプライアンス ポリシー。準拠したデバイスと見なされるには、このポリシーに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-106">A device compliance policy that the device must comply with in order to be considered compliant.</span></span>
- <span data-ttu-id="4e52d-107">条件付きアクセス ポリシー。デバイスがサービスにアクセスするために満たす必要のある条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-107">A conditional access policy where you specify the conditions that the device must meet in order to access the service.</span></span>
<span data-ttu-id="4e52d-108">条件付きアクセスの動作の詳細については、[電子メール、O365、およびその他のサービスへのアクセスを保護する](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)に関するトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e52d-108">To learn more about how conditional access works, read the [Protect access to email, O365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) topic.</span></span>

<span data-ttu-id="4e52d-109">コンプライアンス ポリシーと条件付きアクセス ポリシーを、ユーザーに対して展開します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-109">You deploy the compliance and conditional access policies to users.</span></span> <span data-ttu-id="4e52d-110">ユーザーがサービスへのアクセスに使うすべてのデバイスは、ポリシーによってコンプライアンスをチェックされます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-110">Any device that a user uses to access the services is checked for compliance with the policies.</span></span>

<span data-ttu-id="4e52d-111">ユーザーが、デバイスで OneDrive などのサポートされているアプリを使ってファイルに接続しようとすると、次の評価が行われます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-111">When a user attempts to connect to a file by using a supported app such as OneDrive on their device, the following evaluation occurs:</span></span>

![デバイスに SharePoint へのアクセスを許可するかブロックするかを判断する決定ポイントを示す図](../media/ConditionalAccess8-6.png)


<span data-ttu-id="4e52d-113">SharePoint Online の条件付きアクセス ポリシーを構成する**前に**、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-113">**Before** configuring a conditional access policy for SharePoint Online, you must:</span></span>
- <span data-ttu-id="4e52d-114">**SharePoint Online サブスクリプション**を取得します。ユーザーには SharePoint Online のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4e52d-114">Have a **SharePoint Online subscription**, and users must be licensed for SharePoint Online.</span></span>
- <span data-ttu-id="4e52d-115">**Enterprise Mobility + Security (EMS) サブスクリプション**または **Azure Active Directory (Azure AD) Premium サブスクリプション**を取得します。ユーザーに EMS または Azure AD のライセンスが付与される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-115">Have an **Enterprise Mobility + Security (EMS) subscription** or an **Azure Active Directory (Azure AD) Premium subscription**, and users must be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="4e52d-116">詳細については、「[Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing)」 (Enterprise Mobility の価格) ページまたは「[Azure Active Directory の価格](https://azure.microsoft.com/pricing/details/active-directory/)」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e52d-116">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>


  <span data-ttu-id="4e52d-117">必要なファイルに接続するには、デバイスが次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-117">To connect to the required files, a device must be:</span></span>
-   <span data-ttu-id="4e52d-118">Intune に**登録**されているか、ドメインに参加する PC である。</span><span class="sxs-lookup"><span data-stu-id="4e52d-118">**Enrolled** with Intune or a domain-joined PC.</span></span>

-   <span data-ttu-id="4e52d-119">Azure Active Directory に**登録**されている (デバイスが Intune に登録されている場合は、自動的に登録されます)。</span><span class="sxs-lookup"><span data-stu-id="4e52d-119">**Registered** in Azure Active Directory (this happens automatically when the device is enrolled with Intune).</span></span>


-   <span data-ttu-id="4e52d-120">展開されているすべての Intune コンプライアンス ポリシーに**準拠**している。</span><span class="sxs-lookup"><span data-stu-id="4e52d-120">**Compliant** with any deployed Intune compliance policies.</span></span>

<span data-ttu-id="4e52d-121">デバイスの状態は、Azure Active Directory に格納され、指定した条件に基づいて、ファイルへのアクセスが許可されたりブロックされたりします。</span><span class="sxs-lookup"><span data-stu-id="4e52d-121">The device state is stored in Azure Active Directory, which grants or blocks access to the files, based on the conditions that you specify.</span></span>

<span data-ttu-id="4e52d-122">条件が満たされない場合、ユーザーにはサインイン時に以下のうちのいずれかのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-122">If a condition isn't met, the user sees one of the following messages when they sign in:</span></span>

-   <span data-ttu-id="4e52d-123">デバイスが Intune に登録されていない、または Azure Active Directory に登録されていない場合は、メッセージが表示され、ポータル サイト アプリのインストールと登録の手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-123">If the device isn't enrolled with Intune or isn't registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>

-   <span data-ttu-id="4e52d-124">デバイスがポリシーに準拠していない場合は、ユーザーを Intune ポータル サイト Web サイトに導くメッセージが表示されます。このポータルで、問題とその修復方法に関する情報を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-124">If the device isn't compliant, a message is displayed that directs the user to the Intune Company Portal website, where they can find information about the problem and how to remediate it.</span></span>

<span data-ttu-id="4e52d-125">**条件付きアクセスは外部共有に適用されません**。</span><span class="sxs-lookup"><span data-stu-id="4e52d-125">**Conditional access doesn't apply to external sharing**.</span></span> <span data-ttu-id="4e52d-126">テナントまたはサイト コレクションで外部共有を使用しない方法については、「[SharePoint Online 環境の外部共有を管理する](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e52d-126">To learn how to prevent external sharing in your tenant or site collection, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85).</span></span>

>[!NOTE]
><span data-ttu-id="4e52d-127">SharePoint Online で条件付きアクセスを有効にする場合は、[Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/library/dn917451.aspx) のトピックの説明に従って、一覧にあるドメインを無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4e52d-127">If you enable conditional access for SharePoint Online, we recommend that you disable the domain on the list, as described in the [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/library/dn917451.aspx) topic.</span></span>  

## <a name="support-for-mobile-devices"></a><span data-ttu-id="4e52d-128">モバイル デバイスのサポート</span><span class="sxs-lookup"><span data-stu-id="4e52d-128">Support for mobile devices</span></span>
<span data-ttu-id="4e52d-129">次のものがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4e52d-129">The following are supported:</span></span>
- <span data-ttu-id="4e52d-130">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="4e52d-130">iOS 8.0 and later</span></span>
- <span data-ttu-id="4e52d-131">Android 4.0 以降、Samsung Knox Standard 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="4e52d-131">Android 4.0 and later, Samsung Knox Standard 4.0 or later</span></span>
- <span data-ttu-id="4e52d-132">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="4e52d-132">Windows Phone 8.1 and later</span></span>

<span data-ttu-id="4e52d-133">**iOS** デバイスや **Android** デバイスがブラウザーからアクセスした場合、SharePoint Online へのアクセスを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-133">You can protect access to SharePoint Online when **iOS** and **Android** devices access it from a browser.</span></span> <span data-ttu-id="4e52d-134">準拠デバイスでサポートされているブラウザーからのアクセスのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-134">Access is only allowed from supported browsers on compliant devices:</span></span>
* <span data-ttu-id="4e52d-135">Safari (iOS)</span><span class="sxs-lookup"><span data-stu-id="4e52d-135">Safari (iOS)</span></span>
* <span data-ttu-id="4e52d-136">Chrome (Android)</span><span class="sxs-lookup"><span data-stu-id="4e52d-136">Chrome (Android)</span></span>
* <span data-ttu-id="4e52d-137">Intune Managed Browser (iOS および Android 5.0 以降)</span><span class="sxs-lookup"><span data-stu-id="4e52d-137">Intune Managed Browser (iOS and Android 5.0 and later)</span></span>

<span data-ttu-id="4e52d-138">**サポートされていないブラウザーはブロックされます**。</span><span class="sxs-lookup"><span data-stu-id="4e52d-138">**Unsupported browsers are blocked**.</span></span>

## <a name="support-for-pcs"></a><span data-ttu-id="4e52d-139">PC のサポート</span><span class="sxs-lookup"><span data-stu-id="4e52d-139">Support for PCs</span></span>
<span data-ttu-id="4e52d-140">次のものがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4e52d-140">The following are supported:</span></span>
- <span data-ttu-id="4e52d-141">Windows 8.1 以降 (PC が Intune に登録されている場合)</span><span class="sxs-lookup"><span data-stu-id="4e52d-141">Windows 8.1 and later (when PCs are enrolled with Intune)</span></span>
- <span data-ttu-id="4e52d-142">Windows 7.0、Windows 8.1、または Windows 10 (PC がドメインに参加している場合)</span><span class="sxs-lookup"><span data-stu-id="4e52d-142">Windows 7.0, Windows 8.1, or Windows 10 (when PCs are domain joined),</span></span>
> [!NOTE]
><span data-ttu-id="4e52d-143">Windows 10 を搭載した PC で条件付きアクセスを使用するには、Windows 10 Anniversary Update で PC を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-143">To use conditional access with Windows 10 PCs, you must update those PCs with the Windows 10 Anniversary Update.</span></span>

  - <span data-ttu-id="4e52d-144">ドメインに参加している PC の場合、Azure Active Directory に[自動的に登録](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/)するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-144">You must set up domain-joined PCs to [automatically register](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) with Azure Active Directory.</span></span> <span data-ttu-id="4e52d-145">Azure AD Device Registration サービスは、Intune や Office 365 のお客様に対して自動的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-145">The Azure AD Device Registration service will be activated automatically for Intune and Office 365 customers.</span></span> <span data-ttu-id="4e52d-146">ADFS Device Registration Service をデプロイ済みのお客様には、オンプレミスの Active Directory で登録されたデバイスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4e52d-146">Customers who have already deployed the ADFS Device Registration service will not see registered devices in on-premises Active Directory.</span></span>

  - <span data-ttu-id="4e52d-147">ドメインへの参加を要求するようにポリシーを設定していて、PC がドメインに参加していない場合は、IT 管理者に連絡するようにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-147">If the policy is set to require a domain join and the PC isn't domain joined, a message is displayed to contact the IT admin.</span></span>

  - <span data-ttu-id="4e52d-148">ドメインへの参加または準拠を要求するようにポリシーを設定していて、PC がいずれかの要件を満たしていない場合は、ポータル サイト アプリをインストールして登録する方法についての手順が示されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-148">If the policy is set to require a domain join or compliance, and the PC doesn't meet either requirement, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>
  >[!NOTE]
  ><span data-ttu-id="4e52d-149">Intune コンピューター クライアントを実行する PC では、条件付きアクセスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4e52d-149">Conditional access is not supported on PCs that are running the Intune computer client.</span></span>

<span data-ttu-id="4e52d-150">[Office 365 の先進認証が有効化](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a)されていて、最新の Office 更新プログラムがすべて適用されていること。</span><span class="sxs-lookup"><span data-stu-id="4e52d-150">[Office 365 modern authentication must be enabled](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) and have all the latest Office updates.</span></span>

<span data-ttu-id="4e52d-151">先進認証により、Active Directory Authentication Library (ADAL) に基づくサインインが Office 2013 Windows クライアントに導入され、**多要素認証**や**証明書ベースの認証**などのより強力なセキュリティを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-151">Modern authentication brings sign-in based on Active Directory Authentication Library (ADAL) to Office 2013 Windows clients and enables better security, like **multi-factor authentication** and **certificate-based authentication**.</span></span>


## <a name="configure-conditional-access-for-sharepoint-online"></a><span data-ttu-id="4e52d-152">SharePoint Online の条件付きアクセスの構成</span><span class="sxs-lookup"><span data-stu-id="4e52d-152">Configure conditional access for SharePoint Online</span></span>

### <a name="step-1-configure-active-directory-security-groups"></a><span data-ttu-id="4e52d-153">手順 1. Active Directory セキュリティ グループを構成する</span><span class="sxs-lookup"><span data-stu-id="4e52d-153">Step 1: Configure Active Directory security groups</span></span>
<span data-ttu-id="4e52d-154">開始する前に、条件付きアクセス ポリシーの Azure Active Directory セキュリティ グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-154">Before you start, configure Azure Active Directory security groups for the conditional access policy.</span></span> <span data-ttu-id="4e52d-155">これらのグループは、**Office 365 管理センター**または **Intune アカウント ポータル**で構成できます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-155">You can configure these groups in the **Office 365 admin center** or in the **Intune account portal**.</span></span> <span data-ttu-id="4e52d-156">これらのグループは、ユーザーをポリシーの対象とするか、または除外するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-156">You use these groups to target or exempt users from the policy.</span></span> <span data-ttu-id="4e52d-157">ユーザーがポリシーの対象となる場合、ユーザーに使用される各デバイスがリソースにアクセスするには、ポリシーを遵守している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-157">When a user is targeted by a policy, each device that they use must be compliant in order to access resources.</span></span>

<span data-ttu-id="4e52d-158">SharePoint Online ポリシーには、次の 2 つのグループの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-158">You can specify two group types in a SharePoint Online policy:</span></span>

-   <span data-ttu-id="4e52d-159">**対象グループ**: ポリシーを適用するユーザーのグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-159">**Targeted groups**: Contains groups of users that the policy applies to.</span></span>

-   <span data-ttu-id="4e52d-160">**例外グループ**: ポリシーから除外されるユーザーのグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-160">**Exempted groups**: Contains groups of users that are exempt from the policy.</span></span>

<span data-ttu-id="4e52d-161">ユーザーが両方のグループに含まれている場合は、ポリシーから除外されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-161">If a user is in both groups, they are exempt from the policy.</span></span>

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a><span data-ttu-id="4e52d-162">手順 2. コンプライアンス ポリシーを構成し、展開する</span><span class="sxs-lookup"><span data-stu-id="4e52d-162">Step 2: Configure and deploy a compliance policy</span></span>
<span data-ttu-id="4e52d-163">まだ行っていない場合は、コンプライアンス ポリシーを作成し、SharePoint Online ポリシーの対象となるユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-163">If you haven't already done so, create a compliance policy, and deploy it to the users that the SharePoint Online policy targets.</span></span>

> [!NOTE]
> <span data-ttu-id="4e52d-164">コンプライアンス ポリシーは Intune グループに展開されますが、条件付きアクセス ポリシーは、Azure Active Directory セキュリティ グループを対象とします。</span><span class="sxs-lookup"><span data-stu-id="4e52d-164">While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.</span></span>

<span data-ttu-id="4e52d-165">コンプライアンス ポリシーを構成する方法の詳細については、「[コンプライアンス ポリシーの作成](create-a-device-compliance-policy-in-microsoft-intune.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e52d-165">For details about how to configure the compliance policy, see [Create a compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e52d-166">コンプライアンス ポリシーを展開していない場合は、デバイスがポリシーに準拠しているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-166">If you haven't deployed a compliance policy, the devices are treated as compliant.</span></span>

<span data-ttu-id="4e52d-167">準備ができたら、**手順 3** に進みます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-167">When you're ready, continue to **Step 3**.</span></span>

### <a name="step-3-configure-the-sharepoint-online-policy"></a><span data-ttu-id="4e52d-168">手順 3. SharePoint Online ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="4e52d-168">Step 3: Configure the SharePoint Online policy</span></span>
<span data-ttu-id="4e52d-169">次に、管理デバイスおよび準拠デバイスのみが SharePoint Online にアクセスできるように要求するポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-169">Next, configure the policy to require that only managed and compliant devices can access SharePoint Online.</span></span> <span data-ttu-id="4e52d-170">このポリシーは、Azure Active Directory に格納されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-170">This policy is stored in Azure Active Directory.</span></span>

#### <a name="bkmk_spopolicy"></a>

>[!NOTE]
> <span data-ttu-id="4e52d-171">Azure AD 管理コンソールで、Intune デバイスの条件付きアクセス ポリシーを作成することもできます (このようなポリシーは、Azure AD の**デバイス ベースの条件付きアクセス ポリシー**と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="4e52d-171">You can also create a conditional access policy for Intune devices in the Azure AD management console (the policy is referred to as the **device-based conditional access policy** in Azure AD).</span></span> <span data-ttu-id="4e52d-172">さらに、多要素認証のような他の条件付きアクセス ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-172">In addition, you can create other conditional access policies like multi-factor authentication.</span></span> <span data-ttu-id="4e52d-173">Azure AD がサポートするサード パーティ製の Enterprise アプリ (Salesforce や Box など) に条件付きアクセス ポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-173">You can also set conditional access policies for third-party enterprise apps that Azure AD supports, like Salesforce and Box.</span></span> <span data-ttu-id="4e52d-174">詳細については、「[Azure Active Directory に接続されたアプリケーションのアクセスを制御する Azure Active Directory デバイス ベースの条件付きアクセス ポリシーを設定する方法](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e52d-174">For more details, see [How to set Azure Active Directory device-based conditional access policy for access control to Azure Active Directory connected applications](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).</span></span>


1.  <span data-ttu-id="4e52d-175">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** > **[条件付きアクセス]** > **[SharePoint Online ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-175">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Conditional Access** > **SharePoint Online Policy**.</span></span>
<span data-ttu-id="4e52d-176">![SharePoint Online ポリシー ページのスクリーンショット](../media/mdm-ca-spo-policy-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="4e52d-176">![Screenshot of the SharePoint Online Policy page](../media/mdm-ca-spo-policy-configuration.png)</span></span>

2.  <span data-ttu-id="4e52d-177">**[SharePoint Online の条件付きアクセス ポリシーを有効にする]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="4e52d-177">Select **Enable conditional access policy for SharePoint Online**.</span></span>

3.  <span data-ttu-id="4e52d-178">**[アプリケーション アクセス]** で、条件付きアクセス ポリシーを適用する対象を次のように選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-178">Under **Application access**, you can choose to apply the conditional access policy to:</span></span>

    -   <span data-ttu-id="4e52d-179">**すべてのプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="4e52d-179">**All platforms**</span></span>

        <span data-ttu-id="4e52d-180">**SharePoint Online** にアクセスするために使用するデバイスはすべて、Intune に登録され、またポリシーに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-180">This requires that any device used to access **SharePoint Online** is enrolled in Intune and is compliant with the policies.</span></span> <span data-ttu-id="4e52d-181">**先進認証**を使っているすべてのクライアント アプリケーションに、条件付きアクセス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-181">Any client application that uses **modern authentication** is subject to the conditional access policy.</span></span> <span data-ttu-id="4e52d-182">プラットフォームが現在 Intune でサポートされていない場合、**SharePoint Online** へのアクセスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-182">If the platform isn't currently supported by Intune, access to **SharePoint Online** is blocked.</span></span>

        <span data-ttu-id="4e52d-183">**[すべてのプラットフォーム]** オプションを選択することは、クライアント アプリケーションから報告されたプラットフォームでない限り、Azure Active Directory がすべての認証要求にこのポリシーを適用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-183">Selecting the **All platforms** option means that Azure Active Directory applies this policy to all authentication requests, regardless of the platform that is reported by the client application.</span></span> <span data-ttu-id="4e52d-184">次の場合を除いて、すべてのプラットフォームが登録されて準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-184">All platforms are required to be enrolled and become compliant, except for:</span></span>
        *   <span data-ttu-id="4e52d-185">Windows デバイスが登録されて準拠している必要があるか、またはオンプレミスの Active Directory でドメインに参加している (一方または両方)</span><span class="sxs-lookup"><span data-stu-id="4e52d-185">Windows devices, which are required to be enrolled and compliant, domain joined with on-premises Active Directory, or both.</span></span>
        * <span data-ttu-id="4e52d-186">Mac などのサポートされていないプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="4e52d-186">Unsupported platforms like Mac.</span></span> <span data-ttu-id="4e52d-187">ただし、これらのプラットフォームからの最新の認証を使用しているアプリは、それでもブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-187">However, apps using modern authentication that come from these platforms are still blocked.</span></span>

    -   <span data-ttu-id="4e52d-188">**特定のプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="4e52d-188">**Specific platforms**</span></span>

         <span data-ttu-id="4e52d-189">指定したプラットフォームで先進認証を使用しているすべてのクライアント アプリに条件付きアクセス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-189">The conditional access policy applies to any client app that is using modern authentication on the platforms that you specify.</span></span>

     <span data-ttu-id="4e52d-190">Windows PC の場合は、ドメインに参加しているか、または Intune に登録されてポリシーに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-190">For Windows PCs, a PC must either be domain joined, or enrolled with Intune and compliant.</span></span> <span data-ttu-id="4e52d-191">以下の要件を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-191">You can set the following requirements:</span></span>

     -   <span data-ttu-id="4e52d-192">**デバイスはドメインに参加しているか準拠デバイスである必要があります。**</span><span class="sxs-lookup"><span data-stu-id="4e52d-192">**Devices must be domain joined or compliant.**</span></span> <span data-ttu-id="4e52d-193">PC に、ドメインに参加しているか、Intune で設定されたポリシーに準拠していることを求める場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-193">Choose this option to require that PCs must either be domain joined or compliant with the policies that are set in Intune.</span></span> <span data-ttu-id="4e52d-194">PC がどちらの要件も満たさない場合、ユーザーはデバイスを Intune に登録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-194">If a PC doesn't meet either of these requirements, the user is prompted to enroll the device with Intune.</span></span>

     -   <span data-ttu-id="4e52d-195">**デバイスは準拠デバイスである必要があります**</span><span class="sxs-lookup"><span data-stu-id="4e52d-195">**Devices must be compliant.**</span></span> <span data-ttu-id="4e52d-196">このオプションを選択した場合、PC は Intune に登録され、ポリシーに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-196">Choose this option to require that PCs must be enrolled in Intune and compliant.</span></span> <span data-ttu-id="4e52d-197">PC を登録していない場合は、登録する方法についての手順を示したメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-197">If a PC isn't enrolled, a message with instructions on how to enroll is displayed.</span></span>

4.   <span data-ttu-id="4e52d-198">SharePoint Online と OneDrive for Business への **[ブラウザー アクセス]** では、サポートされているブラウザー (Safari (iOS)、Chrome (Android)) を通じてのみ、Exchange Online へのアクセスを許可することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-198">Under **Browser access** to SharePoint Online and OneDrive for Business, you can choose to allow access to Exchange Online only through the supported browsers: Safari (iOS) and Chrome (Android).</span></span> <span data-ttu-id="4e52d-199">その他のブラウザーからのアクセスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-199">Access from other browsers is blocked.</span></span> <span data-ttu-id="4e52d-200">OneDrive のアプリケーションのアクセス用に選択した同じプラットフォームの制限が、ここにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-200">The same platform restrictions that you selected for Application access for OneDrive also apply here.</span></span>

  <span data-ttu-id="4e52d-201">**Android** デバイスで、ユーザーはブラウザー アクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-201">On **Android** devices, users must enable browser access.</span></span> <span data-ttu-id="4e52d-202">この操作を行うには、次のようにユーザーが、登録されるデバイスで **[ブラウザー アクセスを有効にする]** オプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-202">To do this, a user must choose the **Enable Browser Access** option on the enrolled device as follows:</span></span>
  1.    <span data-ttu-id="4e52d-203">**ポータル サイト** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-203">Open the **Company Portal** app.</span></span>
  2.    <span data-ttu-id="4e52d-204">省略記号 [...] またはハードウェアのメニュー ボタンから、**[設定]** ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-204">Go to the **Settings** page from the ellipsis (…) or hardware menu button.</span></span>
  3.    <span data-ttu-id="4e52d-205">**[ブラウザー アクセスを有効にする]** ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-205">Press the **Enable Browser Access** button.</span></span>
  4.    <span data-ttu-id="4e52d-206">Chrome ブラウザーで Office 365 からサインアウトして、Chrome を再起動します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-206">In the Chrome browser, sign out of Office 365 and restart Chrome.</span></span>

  <span data-ttu-id="4e52d-207">**iOS** および **Android** プラットフォームでは、サービスにアクセスするために使用するデバイスを識別するために、Azure Active Directory はデバイスにトランスポート層セキュリティ (TLS) 証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-207">On **iOS** and **Android** platforms, to identify the device that is used to access the service, Azure Active Directory issues a Transport Layer Security (TLS) certificate to the device.</span></span> <span data-ttu-id="4e52d-208">デバイスには、次のスクリーン ショットに示すように、証明書を選択するユーザーに対してプロンプトで証明書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-208">The device displays the certificate with a prompt to the user to select the certificate, as shown in the following screenshots.</span></span> <span data-ttu-id="4e52d-209">ユーザーは、ブラウザーを使用するには、まずこの証明書を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-209">The user must select this certificate before they can use the browser.</span></span>

  <span data-ttu-id="4e52d-210">**iOS**</span><span class="sxs-lookup"><span data-stu-id="4e52d-210">**iOS**</span></span>

  ![iPad での証明書プロンプトのスクリーンショット](../media/mdm-browser-ca-ios-cert-prompt.png)

  <span data-ttu-id="4e52d-212">**Android**</span><span class="sxs-lookup"><span data-stu-id="4e52d-212">**Android**</span></span>

  ![Android デバイス上の証明書プロンプトのスクリーンショット](../media/mdm-browser-ca-android-cert-prompt.png)
5.  <span data-ttu-id="4e52d-214">**[対象グループ]**で、**[変更]** を選択して、ポリシーを適用する Azure Active Directory セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-214">Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy applies to.</span></span> <span data-ttu-id="4e52d-215">すべてのユーザーを対象にすることも、選んだユーザーのグループのみを対象にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-215">You can choose to target this to all users or just a select group of users.</span></span>

6.  <span data-ttu-id="4e52d-216">**[例外グループ]**で、必要に応じて **[変更]** を選択して、このポリシーから除外する Azure Active Directory セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-216">Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.</span></span>

7.  <span data-ttu-id="4e52d-217">終了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-217">When you're done, choose **Save**.</span></span>

<span data-ttu-id="4e52d-218">条件付きアクセス ポリシーを展開する必要はありません。直ちに有効になります。</span><span class="sxs-lookup"><span data-stu-id="4e52d-218">You don't have to deploy the conditional access policy—it takes effect immediately.</span></span>

### <a name="step-4-monitor-the-compliance-and-conditional-access-policies"></a><span data-ttu-id="4e52d-219">手順 4. コンプライアンスと条件付きアクセス ポリシーを監視する</span><span class="sxs-lookup"><span data-stu-id="4e52d-219">Step 4: Monitor the compliance and conditional access policies</span></span>
<span data-ttu-id="4e52d-220">**[グループ]** ワークスペースで、デバイスの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-220">In the **Groups** workspace, you can view the status of your devices.</span></span>

<span data-ttu-id="4e52d-221">任意のモバイル デバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-221">Select any mobile device group.</span></span> <span data-ttu-id="4e52d-222">次に、**[デバイス]** タブで、次のいずれかの **[フィルター]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e52d-222">Then, on the **Devices** tab, choose one of the following **Filters**:</span></span>

-   <span data-ttu-id="4e52d-223">**AAD に登録されていないデバイス**。</span><span class="sxs-lookup"><span data-stu-id="4e52d-223">**Devices that are not registered with AAD**.</span></span> <span data-ttu-id="4e52d-224">これらのデバイスは SharePoint Online からブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-224">These devices are blocked from SharePoint Online.</span></span>

-   <span data-ttu-id="4e52d-225">**準拠していないデバイス**。</span><span class="sxs-lookup"><span data-stu-id="4e52d-225">**Devices that are not compliant**.</span></span> <span data-ttu-id="4e52d-226">これらのデバイスは SharePoint Online からブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-226">These devices are blocked from SharePoint Online.</span></span>

-   <span data-ttu-id="4e52d-227">**AAD に登録され、準拠しているデバイス**。</span><span class="sxs-lookup"><span data-stu-id="4e52d-227">**Devices that are registered with AAD and compliant**.</span></span> <span data-ttu-id="4e52d-228">これらのデバイスは SharePoint Online にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4e52d-228">These devices can access SharePoint Online.</span></span>

### <a name="see-also"></a><span data-ttu-id="4e52d-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e52d-229">See also</span></span>
[<span data-ttu-id="4e52d-230">Microsoft Intune を使用して電子メールおよび O365 サービスへのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="4e52d-230">Protect access to email and O365 services with Microsoft Intune</span></span>](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
