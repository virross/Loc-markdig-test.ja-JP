---
title: "Exchange Online への電子メールを保護する"
description: "条件付きアクセスで Exchange Online の会社電子メールへのアクセスを保護および制御します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8cb9ac65d2708fba000d125fbab7c4181d463c82
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="protect-email-access-to-exchange-online-and-new-exchange-online-dedicated-with-intune"></a><span data-ttu-id="df159-103">Intune で Exchange Online と新しい Exchange Online Dedicated への電子メール アクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="df159-103">Protect email access to Exchange Online and new Exchange Online Dedicated with Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="df159-104">Microsoft Intune を使用して、Exchange Online または Exchange Online Dedicated の条件付きアクセスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="df159-104">You can configure conditional access for Exchange Online or Exchange Online Dedicated by using Microsoft Intune.</span></span> <span data-ttu-id="df159-105">条件付きアクセスの動作の詳細については、[電子メール、O365、およびその他のサービスへのアクセスを保護する](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df159-105">To learn more about how conditional access works, read the [Protect access to email, O365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

> [!NOTE]
><span data-ttu-id="df159-106">Exchange Online Dedicated 環境を使用していて、それが新しい構成であるか既存の構成であるかを確認する必要がある場合は、アカウント マネージャーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="df159-106">If you have an Exchange Online Dedicated environment and need to find out whether it's in the new or the legacy configuration, contact your account manager.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="df159-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="df159-107">Before you begin</span></span>

<span data-ttu-id="df159-108">条件付きアクセスを構成するには</span><span class="sxs-lookup"><span data-stu-id="df159-108">To configure conditional access, you must:</span></span>

-   <span data-ttu-id="df159-109">**Exchange Online を含む Office 365 サブスクリプション (E3 など)** を取得します。ユーザーには Exchange Online のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="df159-109">Have an **Office 365 subscription that includes Exchange Online (such as E3)**, and users must be licensed for Exchange Online.</span></span>

- <span data-ttu-id="df159-110">**Enterprise Mobility + Security (EMS) サブスクリプション**または **Azure Active Directory (Azure AD) Premium サブスクリプション**を取得します。ユーザーに EMS または Azure AD のライセンスが付与される必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-110">Have an **Enterprise Mobility + Security (EMS) subscription** or an **Azure Active Directory (Azure AD) Premium subscription**, and users must be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="df159-111">詳細については、「[Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing)」 (Enterprise Mobility の価格) ページまたは「[Azure Active Directory の価格](https://azure.microsoft.com/pricing/details/active-directory/)」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df159-111">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

-  <span data-ttu-id="df159-112">オプションの **Intune Service to Service Connector** の構成を検討します。これによって Intune が Exchange Online に接続され、Intune コンソールを使ってデバイス情報を管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="df159-112">Consider configuring the optional **Intune service-to-service connector**, which connects Intune to Exchange Online and helps you manage device information through the Intune console.</span></span> <span data-ttu-id="df159-113">コンプライアンス ポリシーまたは条件付きアクセス ポリシーを使用するうえでコネクタを使用する必要はありませんが、条件付きアクセスの影響を評価するためのレポートの実行に必要です。</span><span class="sxs-lookup"><span data-stu-id="df159-113">You don't need to use the connector to use compliance policies or conditional access policies—but it's required to run reports that help evaluate the impact of conditional access.</span></span>
    -  <span data-ttu-id="df159-114">詳細については、[Intune Service to Service Connector](intune-service-to-service-exchange-connector.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df159-114">Learn more about the [Intune service-to-service connector](intune-service-to-service-exchange-connector.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="df159-115">Exchange Online と Exchange On-Premises の両方で条件付きアクセスを使用する場合は、Intune Service to Service Connector を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="df159-115">Do not configure the Intune service-to-service connector if you intend to use conditional access for both Exchange Online and Exchange on-premises.</span></span>

### <a name="device-compliance-requirements"></a><span data-ttu-id="df159-116">デバイス コンプライアンスの要件</span><span class="sxs-lookup"><span data-stu-id="df159-116">Device compliance requirements</span></span>

<span data-ttu-id="df159-117">条件付きアクセス ポリシーを構成してユーザーに適用すると、ユーザーが電子メールに接続するには、使用する**デバイス**が以下の条件を満たさなくてはならなくなります。</span><span class="sxs-lookup"><span data-stu-id="df159-117">When you configure conditional access policies and target them to a user, before a user can connect to their email, the **device** they use must be:</span></span>

-   <span data-ttu-id="df159-118">ドメインに参加している PC であるか、または Intune に**登録**されていること。</span><span class="sxs-lookup"><span data-stu-id="df159-118">A domain-joined PC or **enrolled** with Intune.</span></span>

-  <span data-ttu-id="df159-119">**Azure Active Directory に登録されている**。</span><span class="sxs-lookup"><span data-stu-id="df159-119">**Registered in Azure Active Directory**.</span></span> <span data-ttu-id="df159-120">この登録は、デバイスが Intune に登録されると自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="df159-120">This happens automatically when the device is enrolled with Intune.</span></span> <span data-ttu-id="df159-121">また、クライアントの Exchange ActiveSync ID を Azure Active Directory に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-121">Additionally, the client Exchange ActiveSync ID must be registered with Azure Active Directory.</span></span>

  <span data-ttu-id="df159-122">Azure Active Directory Device Registration サービスは、Intune や Office 365 のお客様に対して自動的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="df159-122">The Azure Active Directory Device Registration service is activated automatically for Intune and Office 365 customers.</span></span> <span data-ttu-id="df159-123">ADFS Device Registration Service をデプロイ済みのお客様には、オンプレミスの Active Directory で登録されたデバイスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="df159-123">Customers who have already deployed the ADFS Device Registration service will not see registered devices in on-premises Active Directory.</span></span>

-   <span data-ttu-id="df159-124">そのデバイス、またはオンプレミス ドメインに参加しているドメインに展開された Intune コンプライアンス ポリシーに**準拠**していること。</span><span class="sxs-lookup"><span data-stu-id="df159-124">**Compliant** with any Intune compliance policies that are deployed to that device or domain joined to an on-premises domain.</span></span>

### <a name="when-the-device-is-not-compliant"></a><span data-ttu-id="df159-125">デバイスが準拠していない場合</span><span class="sxs-lookup"><span data-stu-id="df159-125">When the device is not compliant</span></span>

<span data-ttu-id="df159-126">条件付きアクセス ポリシーが満たされない場合、デバイスはすぐに検疫され、ユーザーは電子メールを受信し、サインイン時に次のいずれかの検疫通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df159-126">If a conditional access policy isn't met, the device gets immediately quarantined, and the user receives an e-mail and sees one of the following quarantine notifications when they sign in:</span></span>

- <span data-ttu-id="df159-127">デバイスが Intune に登録されていない、または Azure Active Directory に登録されていない場合は、メッセージが表示され、ポータル サイト アプリのインストール、デバイスの登録、および電子メールのアクティブ化の手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="df159-127">If the device isn't enrolled with Intune or isn't registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app, enroll the device, and activate email.</span></span> <span data-ttu-id="df159-128">また、このプロセスによって、デバイスの Exchange ActiveSync ID が Azure Active Directory のレコードに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="df159-128">This process also associates the device’s Exchange ActiveSync ID with the record in Azure Active Directory.</span></span>

-   <span data-ttu-id="df159-129">デバイスがコンプライアンス ポリシーのルールに準拠していないと評価された場合は、ユーザーを Intune ポータル サイト Web サイトまたはポータル サイト アプリに導くメッセージが表示されます。このポータルで、問題とその修復方法に関する情報を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="df159-129">If the device is evaluated as not compliant with the compliance policy rules, the user is directed to the Intune Company Portal website or the Company Portal app, where they can find information about the problem and how to remediate it.</span></span>

### <a name="how-conditional-access-works-with-exchange-online"></a><span data-ttu-id="df159-130">Exchange Online での条件付きアクセスのしくみ</span><span class="sxs-lookup"><span data-stu-id="df159-130">How conditional access works with Exchange Online</span></span>

<span data-ttu-id="df159-131">次の図は、Exchange Online の条件付きアクセス ポリシーで使用されるフローを示します。</span><span class="sxs-lookup"><span data-stu-id="df159-131">The following diagram illustrates the flow that is used by conditional access policies for Exchange Online.</span></span>

![デバイスのアクセスを許可するかブロックするかを判断する決定ポイントを示す図](../media/ConditionalAccess8-1.png)

## <a name="support-for-mobile-devices"></a><span data-ttu-id="df159-133">モバイル デバイスのサポート</span><span class="sxs-lookup"><span data-stu-id="df159-133">Support for mobile devices</span></span>
<span data-ttu-id="df159-134">**Outlook** およびその他の**先進認証を使用するアプリ**から Exchange Online の電子メールへのアクセスを保護できます。</span><span class="sxs-lookup"><span data-stu-id="df159-134">You can protect access to Exchange Online email from **Outlook** and other **apps that use modern authentication**.</span></span> <span data-ttu-id="df159-135">次のものがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="df159-135">The following are supported:</span></span>

- <span data-ttu-id="df159-136">Android 4.0 以降、Samsung KNOX Standard 4.0 以降、Android for Work</span><span class="sxs-lookup"><span data-stu-id="df159-136">Android 4.0 and later, Samsung Knox Standard 4.0 and later, and Android for Work</span></span>
- <span data-ttu-id="df159-137">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="df159-137">iOS 8.0 and later</span></span>

<span data-ttu-id="df159-138">**先進認証**では、Active Directory Authentication Library (ADAL) ベースのサインインが Microsoft Office クライアントに導入されます。</span><span class="sxs-lookup"><span data-stu-id="df159-138">**Modern authentication** brings sign-in based on Active Directory Authentication Library (ADAL) to Microsoft Office clients.</span></span>

-   <span data-ttu-id="df159-139">ADAL ベースの認証を使用すると、Office クライアントでブラウザー ベースの認証 (パッシブ認証とも呼ばれます) を利用できます。</span><span class="sxs-lookup"><span data-stu-id="df159-139">The ADAL-based authentication enables Office clients to engage in browser-based authentication (also known as passive authentication).</span></span> <span data-ttu-id="df159-140">認証するときに、ユーザーはサインイン Web ページに転送されます。</span><span class="sxs-lookup"><span data-stu-id="df159-140">To authenticate, a user is directed to a sign-in web page.</span></span>
-   <span data-ttu-id="df159-141">この新しいサインイン方法によって、**多要素認証**や**証明書ベースの認証**などのより強力なセキュリティを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="df159-141">This new sign-in method enables better security like **multi-factor authentication** and **certificate-based authentication**.</span></span> <span data-ttu-id="df159-142">詳細については、「[How modern authentication works](https://support.office.com/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517)」 (先進認証の動作) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df159-142">For more detailed information, see [How modern authentication works](https://support.office.com/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517).</span></span> <span data-ttu-id="df159-143">最新ではない認証プロトコルをブロックするように ADFS 要求規則を設定できます。</span><span class="sxs-lookup"><span data-stu-id="df159-143">You can set up ADFS claim rules to block non-modern authentication protocols.</span></span> <span data-ttu-id="df159-144">詳しい手順は、[シナリオ 3: ブラウザー ベースのアプリケーションを除く Office 365 への外部アクセスをすべてブロックする方法](https://technet.microsoft.com/library/dn592182.aspx)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df159-144">Detailed instructions are provided in [Scenario 3: Block all access to O365 except browser-based applications](https://technet.microsoft.com/library/dn592182.aspx).</span></span>

<span data-ttu-id="df159-145">**iOS** と **Android** デバイス上のブラウザーからユーザーがアクセスした場合、Exchange Online の **Outlook Web Access (OWA)** へのアクセスを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="df159-145">You can protect access to **Outlook Web Access (OWA)** on Exchange Online when a user accesses it from a browser on **iOS** and **Android** devices.</span></span> <span data-ttu-id="df159-146">準拠デバイスでサポートされているブラウザーからのアクセスのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="df159-146">Access is only allowed from supported browsers on compliant devices:</span></span>

* <span data-ttu-id="df159-147">Safari (iOS)</span><span class="sxs-lookup"><span data-stu-id="df159-147">Safari (iOS)</span></span>
* <span data-ttu-id="df159-148">Chrome (Android)</span><span class="sxs-lookup"><span data-stu-id="df159-148">Chrome (Android)</span></span>
* <span data-ttu-id="df159-149">Intune Managed Browser (iOS、Android 5.0 以降)</span><span class="sxs-lookup"><span data-stu-id="df159-149">Intune Managed Browser (iOS, Android 5.0 and later)</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="df159-150">**サポートされていないブラウザーはブロックされます**。</span><span class="sxs-lookup"><span data-stu-id="df159-150">**Unsupported browsers are blocked**.</span></span>

<span data-ttu-id="df159-151">**iOS 用と Android 用 OWA アプリケーションでは、最新の認証がサポートされていないため、最新の認証を使用しないように変更することができます。OWA アプリケーションからのアクセスは、ADFS 要求規則を使用してブロックする必要があります。**</span><span class="sxs-lookup"><span data-stu-id="df159-151">**The OWA app for iOS and Android can be modified not to use modern authentication, and it isn't supported. Access from the OWA app must be blocked through ADFS claim rules.**</span></span>


<span data-ttu-id="df159-152">以下のプラットフォームの組み込み **Exchange ActiveSync 電子メール クライアント**による Exchange 電子メールへのアクセスを保護できます。</span><span class="sxs-lookup"><span data-stu-id="df159-152">You can protect access to Exchange email from the built-in **Exchange ActiveSync email client** on the following platforms:</span></span>

- <span data-ttu-id="df159-153">Android 4.0 以降、Samsung Knox Standard 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="df159-153">Android 4.0 and later, Samsung Knox Standard 4.0 and later</span></span>

- <span data-ttu-id="df159-154">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="df159-154">iOS 8.0 and later</span></span>

- <span data-ttu-id="df159-155">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="df159-155">Windows Phone 8.1 and later</span></span>

## <a name="support-for-pcs"></a><span data-ttu-id="df159-156">PC のサポート</span><span class="sxs-lookup"><span data-stu-id="df159-156">Support for PCs</span></span>

<span data-ttu-id="df159-157">PC が Office デスクトップ アプリケーションを実行して **Exchange Online** と **SharePoint Online** にアクセスする場合、次の要件を満たす PC に対して条件付きアクセスをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="df159-157">You can set up conditional access for PCs that run Office desktop applications to access **Exchange Online** and **SharePoint Online** for PCs that meet the following requirements:</span></span>

-   <span data-ttu-id="df159-158">Windows 7.0、Windows 8.1、または Windows 10 を実行している PC であること。</span><span class="sxs-lookup"><span data-stu-id="df159-158">The PC must be running Windows 7.0, Windows 8.1, or Windows 10.</span></span>

  >[!NOTE]
  > <span data-ttu-id="df159-159">Windows 10 を搭載した PC で条件付きアクセスを使用するには、Windows 10 Anniversary Update で PC を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-159">To use conditional access with Windows 10 PCs, you must update those PCs with the Windows 10 Anniversary Update.</span></span>

  <span data-ttu-id="df159-160">ドメインに参加しているか、コンプライアンス ポリシーのルールに準拠している PC であること。</span><span class="sxs-lookup"><span data-stu-id="df159-160">The PC must either be domain joined or compliant with the compliance policy rules.</span></span>

  <span data-ttu-id="df159-161">準拠していると見なされるためには、PC が Intune に登録済みで、ポリシーに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-161">In order to be considered compliant, the PC must be enrolled in Intune and comply with the policies.</span></span>

  <span data-ttu-id="df159-162">ドメインに参加する PC の場合、Azure Active Directory に[デバイスを自動的に登録](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/)するための条件付きアクセスを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-162">For domain-joined PCs, you must set up conditional access to [automatically register the device](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) with Azure Active Directory.</span></span>

  >[!NOTE]
    ><span data-ttu-id="df159-163">Intune コンピューター クライアントを実行する PC では、条件付きアクセスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="df159-163">Conditional access isn't supported on PCs that are running the Intune computer client.</span></span>

-   <span data-ttu-id="df159-164">[Office 365 の先進認証が有効化](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a)されていて、最新の Office 更新プログラムがすべて適用されていること。</span><span class="sxs-lookup"><span data-stu-id="df159-164">[Office 365 modern authentication must be enabled](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) and have all the latest Office updates.</span></span>

    <span data-ttu-id="df159-165">先進認証では、Active Directory Authentication Library (ADAL) ベースのサインインが Office 2013/Windows クライアントに導入されます。</span><span class="sxs-lookup"><span data-stu-id="df159-165">Modern authentication brings sign-in based on Active Directory Authentication Library (ADAL) to Office 2013/Windows clients.</span></span> <span data-ttu-id="df159-166">この方法によって、**多要素認証**や**証明書ベースの認証**などのより強力なセキュリティを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="df159-166">It enables better security like **multi-factor authentication** and **certificate-based authentication**.</span></span>

-   <span data-ttu-id="df159-167">最新ではない認証プロトコルをブロックするように ADFS 要求規則が設定されます。</span><span class="sxs-lookup"><span data-stu-id="df159-167">ADFS claim rules are set up to block non-modern authentication protocols.</span></span> <span data-ttu-id="df159-168">詳しい手順は、[シナリオ 3: ブラウザー ベースのアプリケーションを除く Office 365 への外部アクセスをすべてブロックする方法](https://technet.microsoft.com/library/dn592182.aspx)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df159-168">Detailed instructions are provided in [Scenario 3: Block all access to O365 except browser based applications](https://technet.microsoft.com/library/dn592182.aspx).</span></span>

## <a name="configure-conditional-access"></a><span data-ttu-id="df159-169">条件付きアクセスの構成</span><span class="sxs-lookup"><span data-stu-id="df159-169">Configure conditional access</span></span>
### <a name="step-1-configure-and-deploy-a-compliance-policy"></a><span data-ttu-id="df159-170">手順 1: コンプライアンス ポリシーを構成し、展開する</span><span class="sxs-lookup"><span data-stu-id="df159-170">Step 1: Configure and deploy a compliance policy</span></span>
<span data-ttu-id="df159-171">条件付きアクセス ポリシーを適用するユーザー グループに対しては、コンプライアンス ポリシーも[作成](create-a-device-compliance-policy-in-microsoft-intune.md)して[展開](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-171">Make sure you [create](create-a-device-compliance-policy-in-microsoft-intune.md) and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy to the user groups that will also get the conditional access policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="df159-172">コンプライアンス ポリシーを展開していない場合、デバイスはポリシーに準拠していると見なされ、Exchange へのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="df159-172">If you haven't deployed a compliance policy, the devices are considered compliant and are allowed access to Exchange.</span></span>

### <a name="step-2-evaluate-the-effect-of-the-conditional-access-policy"></a><span data-ttu-id="df159-173">手順 2: 条件付きアクセス ポリシーの効果を評価する</span><span class="sxs-lookup"><span data-stu-id="df159-173">Step 2: Evaluate the effect of the conditional access policy</span></span>
<span data-ttu-id="df159-174">**モバイル デバイスのインベントリ レポート**を使用して、条件付きアクセス ポリシーを構成した後に Exchange へのアクセスがブロックされるデバイスを特定できます。</span><span class="sxs-lookup"><span data-stu-id="df159-174">You can use the **Mobile Device Inventory Reports** to identify the devices that might be blocked from accessing Exchange after you configure the conditional access policy.</span></span>

<span data-ttu-id="df159-175">これを行うには、[Microsoft Intune Service to Service Connector](intune-service-to-service-exchange-connector.md) を使って、Intune と Exchange の間の接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="df159-175">To do this, configure a connection between Intune and Exchange by using the [Microsoft Intune service-to-service connector](intune-service-to-service-exchange-connector.md).</span></span>
1.  <span data-ttu-id="df159-176">**[レポート]**、**[モバイル デバイスのインベントリ レポート]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="df159-176">Navigate to **Reports** > **Mobile Device Inventory Reports**.</span></span>
<span data-ttu-id="df159-177">![[モバイル デバイスのインベントリ レポート] ページのスクリーンショット](../media/IntuneSA2bMobileDeviceInventoryReport.png)</span><span class="sxs-lookup"><span data-stu-id="df159-177">![Screenshot of the Mobile Device Inventory Reports page](../media/IntuneSA2bMobileDeviceInventoryReport.png)</span></span>

2.  <span data-ttu-id="df159-178">レポート パラメーターで、評価する Intune グループを選択し、必要に応じて、ポリシーを適用するデバイス プラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="df159-178">In the report parameters, select the Intune group that you want to evaluate and, if required, the device platforms that the policy will apply to.</span></span>
3.  <span data-ttu-id="df159-179">組織のニーズを満たす条件を選択したら、**[レポートの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df159-179">After you’ve selected the criteria that meets your organization’s needs, choose **View Report**.</span></span>
<span data-ttu-id="df159-180">レポート ビューアが新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="df159-180">The Report Viewer opens in a new window.</span></span>
<span data-ttu-id="df159-181">![モバイル デバイスのインベントリ レポートのサンプルのスクリーンショット](../media/IntuneSA2cViewReport.PNG)</span><span class="sxs-lookup"><span data-stu-id="df159-181">![Screenshot of an sample mobile device inventory report](../media/IntuneSA2cViewReport.PNG)</span></span>

<span data-ttu-id="df159-182">レポートを実行した後、ユーザーをブロックするかどうかを判断するために、次の 4 つの列を調べます。</span><span class="sxs-lookup"><span data-stu-id="df159-182">After you run the report, examine these four columns to determine whether a user will be blocked:</span></span>

-   <span data-ttu-id="df159-183">**[管理チャネル]**: デバイスが Intune、Exchange ActiveSync、またはその両方のいずれによって管理されているかを示します。</span><span class="sxs-lookup"><span data-stu-id="df159-183">**Management Channel**: Indicates whether the device is managed by Intune, Exchange ActiveSync, or both.</span></span>

-   <span data-ttu-id="df159-184">**[AAD に登録済み]**: デバイスが Azure Active Directory に登録されているかどうかを示します (社内参加と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="df159-184">**AAD Registered**: Indicates whether the device is registered with Azure Active Directory (known as Workplace Join).</span></span>

-   <span data-ttu-id="df159-185">**[準拠]**: デバイスが、展開したコンプライアンス ポリシーに準拠しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="df159-185">**Compliant**: Indicates whether the device is compliant with any compliance policies that you deployed.</span></span>

-   <span data-ttu-id="df159-186">**[Exchange ActiveSync ID]**: iOS および Android デバイスで、Exchange ActiveSync ID が Azure Active Directory のデバイス登録レコードに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-186">**Exchange ActiveSync ID**: iOS and Android devices are required to have their Exchange ActiveSync ID associated with the device registration record in Azure Active Directory.</span></span> <span data-ttu-id="df159-187">これは、ユーザーが検疫メールで **[電子メールのアクティブ化]** のリンクを選択したときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="df159-187">This happens when a user chooses the **Activate Email** link in the quarantine email.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df159-188">Windows Phone デバイスは、常にこの列の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="df159-188">Windows Phone devices always display a value in this column.</span></span>

<span data-ttu-id="df159-189">対象グループの一部であるデバイスは、列の値が以下の表に示されている値と一致しない限り、Exchange にアクセスできないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df159-189">Devices that are part of a targeted group are blocked from accessing Exchange unless the column values match those listed in the following table:</span></span>

--------------------------
|<span data-ttu-id="df159-190">管理チャネル</span><span class="sxs-lookup"><span data-stu-id="df159-190">Management Channel</span></span>|<span data-ttu-id="df159-191">AAD に登録済み</span><span class="sxs-lookup"><span data-stu-id="df159-191">AAD Registered</span></span>|<span data-ttu-id="df159-192">準拠</span><span class="sxs-lookup"><span data-stu-id="df159-192">Compliant</span></span>|<span data-ttu-id="df159-193">Exchange ActiveSync ID</span><span class="sxs-lookup"><span data-stu-id="df159-193">Exchange ActiveSync ID</span></span>|<span data-ttu-id="df159-194">結果の動作</span><span class="sxs-lookup"><span data-stu-id="df159-194">Resulting action</span></span>|
|----------------------|------------------|-------------|--------------------------|--------------------|
|<span data-ttu-id="df159-195">**Microsoft Intune および Exchange ActiveSync による管理の対象**</span><span class="sxs-lookup"><span data-stu-id="df159-195">**Managed by Microsoft Intune and Exchange ActiveSync**</span></span>|<span data-ttu-id="df159-196">○</span><span class="sxs-lookup"><span data-stu-id="df159-196">Yes</span></span>|<span data-ttu-id="df159-197">○</span><span class="sxs-lookup"><span data-stu-id="df159-197">Yes</span></span>|<span data-ttu-id="df159-198">値が表示される</span><span class="sxs-lookup"><span data-stu-id="df159-198">A value is displayed</span></span>|<span data-ttu-id="df159-199">電子メール アクセスが許可される</span><span class="sxs-lookup"><span data-stu-id="df159-199">Email access is allowed</span></span>|
|<span data-ttu-id="df159-200">その他の値</span><span class="sxs-lookup"><span data-stu-id="df159-200">Any other value</span></span>|<span data-ttu-id="df159-201">いいえ</span><span class="sxs-lookup"><span data-stu-id="df159-201">No</span></span>|<span data-ttu-id="df159-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="df159-202">No</span></span>|<span data-ttu-id="df159-203">値が表示されない</span><span class="sxs-lookup"><span data-stu-id="df159-203">No value is displayed</span></span>|<span data-ttu-id="df159-204">電子メール アクセスがブロックされる</span><span class="sxs-lookup"><span data-stu-id="df159-204">Email access is blocked</span></span>|
----------------------
<span data-ttu-id="df159-205">レポートの内容をエクスポートし、**[メール アドレス]** 列を使って、ブロックされることをユーザーに通知できます。</span><span class="sxs-lookup"><span data-stu-id="df159-205">You can export the contents of the report and use the **Email Address** column to tell your users that they will be blocked.</span></span>

### <a name="step-3-configure-user-groups-for-the-conditional-access-policy"></a><span data-ttu-id="df159-206">手順 3: 条件付きアクセス ポリシーのユーザー グループを構成する</span><span class="sxs-lookup"><span data-stu-id="df159-206">Step 3: Configure user groups for the conditional access policy</span></span>
<span data-ttu-id="df159-207">条件付きアクセス ポリシーは、さまざまな Azure Active Directory セキュリティ グループのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="df159-207">Conditional access policies are targeted to different Azure Active Directory security groups of users.</span></span> <span data-ttu-id="df159-208">また、条件付きアクセス ポリシーから特定のユーザー グループを除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="df159-208">You can also exempt certain user groups from a conditional access policy.</span></span> <span data-ttu-id="df159-209">ユーザーがポリシーの対象となる場合、ユーザーに使用される各デバイスが電子メールにアクセスするには、ポリシーを遵守している必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-209">When a user is targeted by a policy, each device that they use must be compliant in order to access email.</span></span>

<span data-ttu-id="df159-210">これらのグループは、**Office 365 管理センター**または **Intune アカウント ポータル**で構成できます。</span><span class="sxs-lookup"><span data-stu-id="df159-210">You can configure these groups in the **Office 365 admin center** or in the **Intune account portal**.</span></span>

<span data-ttu-id="df159-211">各ポリシーには、次の 2 つのグループの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="df159-211">You can specify two group types in each policy:</span></span>

-   <span data-ttu-id="df159-212">**対象グループ**: ポリシーが適用されるユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="df159-212">**Targeted groups**: User groups that the policy is applied to.</span></span>

-   <span data-ttu-id="df159-213">**例外グループ**: ポリシーから除外されるユーザー グループ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="df159-213">**Exempted groups**: User groups that are exempt from the policy (optional).</span></span>

<span data-ttu-id="df159-214">ユーザーが両方のグループに含まれている場合は、ポリシーから除外されます。</span><span class="sxs-lookup"><span data-stu-id="df159-214">If a user is in both groups, they are exempt from the policy.</span></span>

<span data-ttu-id="df159-215">条件付きアクセス ポリシーの対象となるグループだけが評価されます。</span><span class="sxs-lookup"><span data-stu-id="df159-215">Only the groups that are targeted by the conditional access policy are evaluated.</span></span>

### <a name="step-4-configure-the-conditional-access-policy"></a><span data-ttu-id="df159-216">手順 4: 条件付きアクセス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="df159-216">Step 4: Configure the conditional access policy</span></span>

>[!NOTE]
> <span data-ttu-id="df159-217">Azure AD 管理コンソールでは、条件付きアクセス ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="df159-217">You can also create a conditional access policy in the Azure AD management console.</span></span> <span data-ttu-id="df159-218">Azure AD 管理コンソールを使用すると、Intune デバイスの条件付きアクセス ポリシー (Azure AD では**デバイスベースの条件付きアクセス ポリシー**と呼ばれている) に加えて、多要素認証など、他の条件付きアクセス ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="df159-218">The Azure AD management console lets you create an Intune device conditional access policy (referred to as the **device-based conditional access policy** in Azure AD), in addition to other conditional access policies like multi-factor authentication.</span></span>

><span data-ttu-id="df159-219">Azure AD がサポートするサード パーティ製の Enterprise アプリ (Salesforce や Box など) に条件付きアクセス ポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="df159-219">You can also set conditional access policies for third-party enterprise apps that Azure AD supports, like Salesforce and Box.</span></span> <span data-ttu-id="df159-220">詳細については、「[Azure Active Directory に接続されたアプリケーションのアクセスを制御する Azure Active Directory デバイス ベースの条件付きアクセス ポリシーを設定する方法](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df159-220">For more details, see [How to set Azure Active Directory device-based conditional access policy for access control to Azure Active Directory-connected applications](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).</span></span>


1.  <span data-ttu-id="df159-221">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** > **[条件付きアクセス]** > **[Exchange Online ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="df159-221">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Conditional Access** > **Exchange Online Policy**.</span></span>

2.  <span data-ttu-id="df159-222">**[Exchange Online ポリシー]** ページで、**[Exchange Online の条件付きアクセス ポリシーを有効にする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df159-222">On the **Exchange Online Policy** page, choose **Enable conditional access policy for Exchange Online**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df159-223">コンプライアンス ポリシーを展開していない場合は、デバイスがポリシーに準拠しているものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="df159-223">If you haven't deployed a compliance policy, devices are treated as compliant.</span></span>
    >
    > <span data-ttu-id="df159-224">コンプライアンスの状態に関係なく、ポリシーの対象となっているすべてのユーザーがデバイスを Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-224">Regardless of the compliance state, all users who are targeted by the policy are required to enroll their devices with Intune.</span></span>

3.  <span data-ttu-id="df159-225">**[アプリケーション アクセス]** では、先進認証を使用するアプリに対して、ポリシーを適用するプラットフォームを選択する方法が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="df159-225">Under **Application access**, for apps that use modern authentication, you have two ways of choosing which platforms the policy should apply to.</span></span> <span data-ttu-id="df159-226">サポートされているプラットフォームは、Android、iOS、Windows、および Windows Phone です。</span><span class="sxs-lookup"><span data-stu-id="df159-226">Supported platforms include Android, iOS, Windows, and Windows Phone.</span></span>

    -   <span data-ttu-id="df159-227">**すべてのプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="df159-227">**All platforms**</span></span>

        <span data-ttu-id="df159-228">**Exchange Online** にアクセスするために使用するデバイスはすべて、Intune に登録され、またポリシーに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-228">This requires that any device that is used to access **Exchange Online** is enrolled in Intune and compliant with the policies.</span></span> <span data-ttu-id="df159-229">**先進認証**を使っているすべてのクライアント アプリケーションに、条件付きアクセス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="df159-229">Any client application that uses **modern authentication** is subject to the conditional access policy.</span></span> <span data-ttu-id="df159-230">プラットフォームが現在 Intune でサポートされていない場合、**Exchange Online** へのアクセスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df159-230">If the platform is currently not supported by Intune, access to **Exchange Online** is blocked.</span></span>

        <span data-ttu-id="df159-231">**[すべてのプラットフォーム]** オプションを選択することは、クライアント アプリケーションから報告されたプラットフォームでない限り、Azure Active Directory がすべての認証要求にこのポリシーを適用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="df159-231">Selecting the **All platforms** option means that Azure Active Directory applies this policy to all authentication requests, regardless of the platform that is reported by the client application.</span></span> <span data-ttu-id="df159-232">次の場合を除いて、すべてのプラットフォームが登録されて準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-232">All platforms are required to enroll and become compliant, except for:</span></span>
        *   <span data-ttu-id="df159-233">Windows デバイスが登録されて準拠している必要があるか、またはオンプレミスの Active Directory でドメインに参加している (一方または両方)</span><span class="sxs-lookup"><span data-stu-id="df159-233">Windows devices, which are required to be enrolled and compliant, domain joined with on-premises Active Directory, or both.</span></span>
        * <span data-ttu-id="df159-234">Mac OS などのサポートされていないプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="df159-234">Unsupported platforms like Mac OS.</span></span> <span data-ttu-id="df159-235">ただし、これらのプラットフォームからの最新の認証を使用しているアプリは、それでもブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df159-235">However, apps that use modern authentication coming from these platforms is still blocked.</span></span>

    -   <span data-ttu-id="df159-236">**特定のプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="df159-236">**Specific platforms**</span></span>

         <span data-ttu-id="df159-237">指定したデバイス プラットフォームで**先進認証**を使用しているすべてのクライアント アプリに条件付きアクセス ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="df159-237">The conditional access policy applies to any client app that is using **modern authentication** on the device platforms that you specify.</span></span>

4. <span data-ttu-id="df159-238">**Outlook Web Access (OWA)** で、サポートされているブラウザー (Safari (iOS)、Chrome (Android)) を通じてのみ、Exchange Online へのアクセスを許可することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="df159-238">Under **Outlook Web Access (OWA)**, you can choose to allow access to Exchange Online only through the supported browsers: Safari (iOS) and Chrome (Android).</span></span> <span data-ttu-id="df159-239">その他のブラウザーからのアクセスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df159-239">Access from other browsers is blocked.</span></span> <span data-ttu-id="df159-240">Outlook のアプリケーションのアクセス用に選択した同じプラットフォームの制限も、ここに適用されます。</span><span class="sxs-lookup"><span data-stu-id="df159-240">The same platform restrictions that you selected for Application access for Outlook also apply here.</span></span>

  <span data-ttu-id="df159-241">**Android** デバイスで、ユーザーはブラウザー アクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-241">On **Android** devices, users must enable browser access.</span></span> <span data-ttu-id="df159-242">この操作を行うには、次のようにエンドユーザーが、登録されるデバイスで **ブラウザー アクセスを有効にする** オプションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-242">To do this, the user must enable the **Enable Browser Access** option on the enrolled device as follows:</span></span>
  1.    <span data-ttu-id="df159-243">**ポータル サイト** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="df159-243">Open the **Company Portal app**.</span></span>
  2.    <span data-ttu-id="df159-244">省略記号 [...] またはハードウェアのメニュー ボタンから、**[設定]** ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="df159-244">Go to the **Settings** page from the ellipsis (…) or the hardware menu button.</span></span>
  3.    <span data-ttu-id="df159-245">**[ブラウザー アクセスを有効にする]** ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="df159-245">Press the **Enable Browser Access** button.</span></span>
  4.    <span data-ttu-id="df159-246">Chrome ブラウザーで Office 365 からサインアウトして、Chrome を再起動します。</span><span class="sxs-lookup"><span data-stu-id="df159-246">In the Chrome browser, sign out of Office 365 and restart Chrome.</span></span>

  <span data-ttu-id="df159-247">**iOS** および **Android** プラットフォームでは、サービスにアクセスするために使用するデバイスを識別するために、Azure Active Directory はデバイスにトランスポート層セキュリティ (TLS) 証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="df159-247">On **iOS** and **Android** platforms, to identify the device that is used to access the service, Azure Active Directory issues a Transport Layer Security (TLS) certificate to the device.</span></span> <span data-ttu-id="df159-248">デバイスには、次のスクリーン ショットに示すように、証明書を選択するユーザーに対してプロンプトで証明書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df159-248">The device displays the certificate with a prompt to the user to select the certificate, as shown in the following screenshots.</span></span> <span data-ttu-id="df159-249">ユーザーは、ブラウザーを使用し続けるには、まずこの証明書を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-249">The user must select this certificate before they can continue to use the browser.</span></span>

  <span data-ttu-id="df159-250">**iOS**</span><span class="sxs-lookup"><span data-stu-id="df159-250">**iOS**</span></span>

  ![iPad での証明書プロンプトのスクリーンショット](../media/mdm-browser-ca-ios-cert-prompt.png)

  <span data-ttu-id="df159-252">**Android**</span><span class="sxs-lookup"><span data-stu-id="df159-252">**Android**</span></span>

  ![Android デバイス上の証明書プロンプトのスクリーンショット](../media/mdm-browser-ca-android-cert-prompt.png)

5.  <span data-ttu-id="df159-254">**[Exchange ActiveSync アプリ]** では、非準拠のデバイスから Exchange Online へのアクセスをブロックするよう選択できます。</span><span class="sxs-lookup"><span data-stu-id="df159-254">Under **Exchange ActiveSync apps**, you can choose to block noncompliant devices from accessing Exchange Online.</span></span> <span data-ttu-id="df159-255">また、サポートされているプラットフォームを実行していないデバイスに対して、電子メールへのアクセスを許可するかブロックするかを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="df159-255">You can also select whether to allow or block access to email when the device isn't running a supported platform.</span></span> <span data-ttu-id="df159-256">サポートされているプラットフォームは、Android、iOS、Windows、および Windows Phone です。</span><span class="sxs-lookup"><span data-stu-id="df159-256">Supported platforms include Android, iOS, Windows, and Windows Phone.</span></span>

 <span data-ttu-id="df159-257">**Android for Work** デバイスの Exchange Active Sync アプリ:</span><span class="sxs-lookup"><span data-stu-id="df159-257">Exchange Active Sync apps on **Android for Work** devices:</span></span>
 -  <span data-ttu-id="df159-258">Android for Work デバイスでは、**仕事用プロファイル**の **Gmail** アプリと **Nine Work** アプリのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="df159-258">Only **Gmail** and **Nine Work** apps in the **work profile** are supported on Android for Work devices.</span></span> <span data-ttu-id="df159-259">条件付きアクセスが Android for Work デバイスで動作するには、Gmail アプリまたは Nine Work アプリ用の電子メール プロファイルを展開する必要があります。また、**必要な**インストールとして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df159-259">For conditional access to work on Android for Work devices, you must deploy an email profile for the Gmail or Nine Work app, and also deploy it as a **required** installation.</span></span>

6.  <span data-ttu-id="df159-260">**[対象グループ]** で、ポリシーを適用するユーザーの Active Directory セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="df159-260">Under **Targeted Groups**, select the Active Directory security groups of users that the policy applies to.</span></span> <span data-ttu-id="df159-261">すべてのユーザーと、ユーザー グループの選択した一覧のどちらを対象にするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="df159-261">You can either choose to target all users or a selected list of user groups.</span></span>
<span data-ttu-id="df159-262">![対象グループと例外グループのオプションを表示した Exchange Online の条件付きアクセス ポリシー ページのスクリーンショット](../media/IntuneSA5eTargetedExemptedGroups.PNG)</span><span class="sxs-lookup"><span data-stu-id="df159-262">![Screenshot of the Exchange Online conditional access policy page that shows the Targeted and Exempted group options](../media/IntuneSA5eTargetedExemptedGroups.PNG)</span></span>
    > [!NOTE]
    > <span data-ttu-id="df159-263">**対象グループ**に含まれているユーザーについては、Exchange のルールとポリシーが Intune のポリシーに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="df159-263">For users that are in the **Targeted groups**, the Intune polices replace Exchange rules and policies.</span></span>
    >
    > <span data-ttu-id="df159-264">次の場合にのみ、Exchange の許可、ブロック、検疫のルールと、Exchange のポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="df159-264">Exchange only enforces the Exchange allow, block, and quarantine rules, and Exchange policies if:</span></span>
    >
    > -   <span data-ttu-id="df159-265">ユーザーが Intune のライセンスを取得していない。</span><span class="sxs-lookup"><span data-stu-id="df159-265">A user isn't licensed for Intune.</span></span>
    > -   <span data-ttu-id="df159-266">ユーザーが Intune のライセンスを取得しているが、条件付きアクセス ポリシーの対象となるどのセキュリティ グループにも属していない。</span><span class="sxs-lookup"><span data-stu-id="df159-266">A user is licensed for Intune, but the user doesn't belong to any security groups that are targeted in the conditional access policy.</span></span>

6.  <span data-ttu-id="df159-267">**[例外グループ]** で、このポリシーから除外するユーザーの Active Directory セキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="df159-267">Under **Exempted Groups**, select the Active Directory security groups of users that are exempt from this policy.</span></span> <span data-ttu-id="df159-268">ユーザーが対象グループと例外グループの両方に属している場合、ユーザーはポリシーから除外されます。</span><span class="sxs-lookup"><span data-stu-id="df159-268">If a user is in both the targeted and exempted groups, they are exempt from the policy.</span></span>

7.  <span data-ttu-id="df159-269">終了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df159-269">When you're done, choose **Save**.</span></span>

-   <span data-ttu-id="df159-270">条件付きアクセス ポリシーを展開する必要はありません。直ちに有効になります。</span><span class="sxs-lookup"><span data-stu-id="df159-270">You don't have to deploy the conditional access policy—it takes effect immediately.</span></span>

-   <span data-ttu-id="df159-271">ユーザーが電子メール アカウントを作成すると、デバイスはすぐにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df159-271">After a user creates an email account, the device is blocked immediately.</span></span>

-   <span data-ttu-id="df159-272">ブロックされたユーザーがデバイスを Intune に登録し、非準拠の問題を修正すると、メールのアクセスは 2 分以内でブロック解除されます。</span><span class="sxs-lookup"><span data-stu-id="df159-272">If a blocked user enrolls the device with Intune and fixes any noncompliance issues, email access is unblocked within two minutes.</span></span>

-   <span data-ttu-id="df159-273">ユーザーがデバイスの登録を解除した場合、メールは約 6 時間後にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df159-273">If the user unenrolls their device, email is blocked after around six hours.</span></span>

<span data-ttu-id="df159-274">**デバイスのアクセスを保護する条件付きアクセス ポリシーの構成方法を示したシナリオの例**を見るには、[電子メール アクセスの保護のシナリオ例](restrict-email-access-example-scenarios.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df159-274">To see some **example scenarios of how you would configure a conditional access policy to protect device access**, see [Protect email access example scenarios](restrict-email-access-example-scenarios.md).</span></span>

## <a name="monitor-the-compliance-and-conditional-access-policies"></a><span data-ttu-id="df159-275">コンプライアンスと条件付きアクセス ポリシーを監視する</span><span class="sxs-lookup"><span data-stu-id="df159-275">Monitor the compliance and conditional access policies</span></span>

#### <a name="to-view-devices-that-are-blocked-from-exchange"></a><span data-ttu-id="df159-276">Exchange からブロックされているデバイスを表示するには</span><span class="sxs-lookup"><span data-stu-id="df159-276">To view devices that are blocked from Exchange</span></span>

<span data-ttu-id="df159-277">Intune ダッシュボードで、**[Exchange からブロックされているデバイス]** タイルを選択します。ブロックされているデバイスの数と詳細情報へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df159-277">On the Intune dashboard, choose the **Blocked Devices from Exchange** tile to show the number of blocked devices and links to more information.</span></span>
<span data-ttu-id="df159-278">![Exchange へのアクセスがブロックされているデバイスの数を表示した Intune ダッシュボードのスクリーンショット](../media/IntuneSA6BlockedDevices.PNG)</span><span class="sxs-lookup"><span data-stu-id="df159-278">![Screenshot of the Intune dashboard showing the number of devices that are blocked from accessing Exchange](../media/IntuneSA6BlockedDevices.PNG)</span></span>

## <a name="next-steps"></a><span data-ttu-id="df159-279">次のステップ</span><span class="sxs-lookup"><span data-stu-id="df159-279">Next steps</span></span>
- [<span data-ttu-id="df159-280">SharePoint Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="df159-280">Protect access to SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

- [<span data-ttu-id="df159-281">Skype for Business Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="df159-281">Protect access to Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
