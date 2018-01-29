---
title: "Exchange On-premises への電子メールを保護する"
description: "条件付きアクセスで Exchange On-premises の会社電子メールへのアクセスを保護および制御します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9c3af93382c61476b3293ccd2e68f96f3992f099
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="protect-email-access-to-exchange-on-premises-and-legacy-exchange-online-dedicated-with-intune"></a><span data-ttu-id="8f86e-103">Intune で Exchange On-premises と従来の Exchange Online Dedicated への電子メール アクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="8f86e-103">Protect email access to Exchange on-premises and legacy Exchange Online Dedicated with Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="8f86e-104">Microsoft Intune を使用して、Exchange On-premises または従来の Exchange Online Dedicated への電子メール アクセスを制御するように条件付きアクセスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-104">You can configure conditional access control email access to Exchange on-premises or to legacy Exchange Online Dedicated by using Microsoft Intune.</span></span>
<span data-ttu-id="8f86e-105">条件付きアクセスの動作の詳細については、「[電子メールと O365 サービスへのアクセスを保護する](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f86e-105">To learn more about how conditional access works, read the [Protect access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

> [!NOTE]
> <span data-ttu-id="8f86e-106">Exchange Online Dedicated 環境を使用していて、それが新しい構成であるか既存の構成であるかを確認する必要がある場合は、アカウント マネージャーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8f86e-106">If you have an Exchange Online Dedicated environment and need to find out whether it's in the new or the legacy configuration, contact your account manager.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8f86e-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="8f86e-107">Before you begin</span></span>

<span data-ttu-id="8f86e-108">以下のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f86e-108">Make sure to verify the following:</span></span>

-   <span data-ttu-id="8f86e-109">Exchange のバージョンは、**Exchange 2010 以降**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-109">Your Exchange version must be **Exchange 2010 or later**.</span></span> <span data-ttu-id="8f86e-110">Exchange Server クライアント アクセス サーバー (CAS) アレイがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8f86e-110">Exchange Server Client Access Server (CAS) arrays are supported.</span></span>

-   <span data-ttu-id="8f86e-111">Intune を Exchange On-premises に接続するために、[Intune On-Premises Exchange Connector](intune-on-premises-exchange-connector.md) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-111">You must use the [Intune on-premises Exchange connector](intune-on-premises-exchange-connector.md), which connects Intune to Exchange on-premises.</span></span> <span data-ttu-id="8f86e-112">これにより、Intune コンソールでデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-112">This lets you manage devices through the Intune console.</span></span>

    -   <span data-ttu-id="8f86e-113">Intune コンソールで利用可能な On-Premises Exchange Connector は、Intune テナントに固有であり、他のテナントでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8f86e-113">The on-premises Exchange connector that is available to you in the Intune console is specific to your Intune tenant and can't be used with any other tenant.</span></span> <span data-ttu-id="8f86e-114">また、テナントの Exchange Connector は **1 台のコンピューターにのみ**インストールすることが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-114">We recommend that you also ensure that the Exchange connector for your tenant is installed **on only one machine**.</span></span>

        <span data-ttu-id="8f86e-115">コネクタは Intune 管理コンソールからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-115">You can download the connector from the Intune admin console.</span></span> <span data-ttu-id="8f86e-116">On-Premises Exchange Connector の構成方法に関するチュートリアルについては、[オンプレミスまたはホスト型 Exchange に対する On-Premises Exchange Connector の構成](intune-on-premises-exchange-connector.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f86e-116">For a walkthrough on how to configure the on-premises Exchange connector, see [configure Exchange on-premises connector for on-premises or hosted Exchange](intune-on-premises-exchange-connector.md).</span></span>

    -   <span data-ttu-id="8f86e-117">このコネクタは、Exchange サーバーと通信できるあらゆるコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-117">You can install the connector on any machine as long as that machine can communicate with the Exchange server.</span></span>

    -   <span data-ttu-id="8f86e-118">このコネクタは、**Exchange CAS 環境**をサポートします。</span><span class="sxs-lookup"><span data-stu-id="8f86e-118">The connector supports the **Exchange CAS environment**.</span></span> <span data-ttu-id="8f86e-119">Exchange CAS サーバーにコネクタを直接インストールすることも技術的には可能です。</span><span class="sxs-lookup"><span data-stu-id="8f86e-119">You can technically install the connector on the Exchange CAS server directly if you want to.</span></span> <span data-ttu-id="8f86e-120">ただし、サーバーの負荷が増えるため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="8f86e-120">However, we don't recommend it because it increases the load on the server.</span></span> <span data-ttu-id="8f86e-121">コネクタを構成するときには、Exchange CAS サーバーのいずれかと通信するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-121">When you configure the connector, you must set it up to communicate with one of the Exchange CAS servers.</span></span>

-   <span data-ttu-id="8f86e-122">**Exchange ActiveSync** は、証明書ベースの認証またはユーザーの資格情報のエントリで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-122">You must configure **Exchange ActiveSync** with certificate-based authentication or user credential entry.</span></span>

### <a name="device-compliance-requirements"></a><span data-ttu-id="8f86e-123">デバイス コンプライアンスの要件</span><span class="sxs-lookup"><span data-stu-id="8f86e-123">Device compliance requirements</span></span>

<span data-ttu-id="8f86e-124">条件付きアクセス ポリシーを構成してユーザーに適用すると、ユーザーが電子メールに接続するには、使用する**デバイス**が以下の条件を満たさなくてはならなくなります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-124">When you configure conditional access policies and target them to a user, before a user can connect to their email, the **device** they use must be:</span></span>

- <span data-ttu-id="8f86e-125">ドメインに参加している PC であるか、Intune に**登録**されている。</span><span class="sxs-lookup"><span data-stu-id="8f86e-125">Either a domain-joined PC or **enrolled** with Intune.</span></span>

- <span data-ttu-id="8f86e-126">**Azure Active Directory に登録されている**。</span><span class="sxs-lookup"><span data-stu-id="8f86e-126">**Registered in Azure Active Directory**.</span></span> <span data-ttu-id="8f86e-127">また、クライアントの Exchange ActiveSync ID を Azure Active Directory に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-127">Additionally, the client Exchange ActiveSync ID must be registered with Azure Active Directory.</span></span>

  <span data-ttu-id="8f86e-128">Azure Active Directory Device Registration サービスは、Intune や Office 365 のお客様に対して自動的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-128">The Azure Active Directory Device Registration service is activated automatically for Intune and Office 365 customers.</span></span> <span data-ttu-id="8f86e-129">ADFS Device Registration Service をデプロイ済みのお客様には、オンプレミスの Active Directory で登録されたデバイスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="8f86e-129">Customers who have already deployed the ADFS Device Registration service will not see registered devices in on-premises Active Directory.</span></span> <span data-ttu-id="8f86e-130">**これは、Windows PC と Windows Phone デバイスには適用されません。**</span><span class="sxs-lookup"><span data-stu-id="8f86e-130">**This does not apply to Windows PCs and Windows Phone devices**.</span></span>

- <span data-ttu-id="8f86e-131">そのデバイスに展開されているすべての Intune コンプライアンス ポリシーに**準拠**している。</span><span class="sxs-lookup"><span data-stu-id="8f86e-131">**Compliant** with any Intune compliance policies that are deployed to that device.</span></span>

### <a name="how-conditional-access-works-with-exchange-on-premises"></a><span data-ttu-id="8f86e-132">Exchange On-Premises での条件付きアクセスのしくみ</span><span class="sxs-lookup"><span data-stu-id="8f86e-132">How conditional access works with Exchange on-premises</span></span>

<span data-ttu-id="8f86e-133">次の図は、Exchange On-premises の条件付きアクセス ポリシーでデバイスを許可するかブロックするかを評価するフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="8f86e-133">The following diagram illustrates the flow that conditional access policies for Exchange on-premises use to evaluate whether to allow or block devices.</span></span>

![デバイスに Exchange On-premises へのアクセスを許可するかブロックするかを判断する決定ポイントを示す図](../media/ConditionalAccess8-2.png)

<span data-ttu-id="8f86e-135">条件付きアクセス ポリシーが満たされない場合は、デバイスがブロックされてから 10 分経過すると、ユーザーはサインイン時に次のいずれかの検疫メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-135">If a conditional access policy isn't met, there is a 10 minute window between the device being blocked and the user receiving one of the following quarantine messages when they sign in:</span></span>

- <span data-ttu-id="8f86e-136">デバイスが Intune に登録されていない、または Azure Active Directory に登録されていない場合は、メッセージが表示され、ポータル サイト アプリのインストール、デバイスの登録、および電子メールのアクティブ化の手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-136">If the device isn't enrolled with Intune or isn't registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app, enroll the device, and activate email.</span></span> <span data-ttu-id="8f86e-137">また、このプロセスによって、デバイスの Exchange ActiveSync ID が Azure Active Directory のデバイス レコードに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-137">This process also associates the device’s Exchange ActiveSync ID with the device record in Azure Active Directory.</span></span>

-   <span data-ttu-id="8f86e-138">デバイスが準拠していない場合は、Intune のポータル サイト Web サイトまたはポータル サイト アプリにユーザーを誘導するメッセージが表示されます。このポータルで、ユーザーは問題とその解決方法に関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-138">If the device isn't compliant, a message is displayed that directs the user to the Intune Company Portal website or the Company Portal app, where they can find information about the problem and how to remediate it.</span></span>

## <a name="support-for-mobile-devices"></a><span data-ttu-id="8f86e-139">モバイル デバイスのサポート</span><span class="sxs-lookup"><span data-stu-id="8f86e-139">Support for mobile devices</span></span>
<span data-ttu-id="8f86e-140">次のものがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8f86e-140">The following are supported:</span></span>
-   <span data-ttu-id="8f86e-141">Windows Phone 8.1 以降。</span><span class="sxs-lookup"><span data-stu-id="8f86e-141">Windows Phone 8.1 and later.</span></span>

-   <span data-ttu-id="8f86e-142">iOS のネイティブ電子メール アプリ。</span><span class="sxs-lookup"><span data-stu-id="8f86e-142">The native email app on iOS.</span></span>

-   <span data-ttu-id="8f86e-143">Android 4 以降での Exchange ActiveSync メール クライアント (Gmail など)。</span><span class="sxs-lookup"><span data-stu-id="8f86e-143">Exchange ActiveSync mail clients, such as Gmail on Android 4 or later.</span></span>
-   <span data-ttu-id="8f86e-144">Exchange ActiveSync メール クライアント **Android for Work デバイス:** Android for Work デバイスでは、**仕事用プロファイル**の **Gmail** アプリと **Nine Work** アプリのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8f86e-144">Exchange ActiveSync mail clients on **Android for Work devices**: Only **Gmail** and **Nine Work** apps in the **work profile** are supported on Android for Work devices.</span></span> <span data-ttu-id="8f86e-145">条件付きアクセスが Android for Work で動作するには、Gmail アプリまたは Nine Work アプリ用の電子メール プロファイルを展開する必要があります。また、必要なインストールとしてそのアプリを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-145">For conditional access to work with Android for Work, you must deploy an email profile for the Gmail or Nine Work app, and also deploy those apps as a required installation.</span></span> 

> [!NOTE]
> <span data-ttu-id="8f86e-146">Android と iOS の Microsoft Outlook アプリはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8f86e-146">The Microsoft Outlook app for Android and iOS isn't supported.</span></span>

## <a name="support-for-pcs"></a><span data-ttu-id="8f86e-147">PC のサポート</span><span class="sxs-lookup"><span data-stu-id="8f86e-147">Support for PCs</span></span>
<span data-ttu-id="8f86e-148">次がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8f86e-148">The following is supported:</span></span>
-   <span data-ttu-id="8f86e-149">Windows 8.1 以降用の**メール** アプリケーション (PC が Intune に登録されている場合)。</span><span class="sxs-lookup"><span data-stu-id="8f86e-149">The **Mail** application on Windows 8.1 and later (when the PC is enrolled with Intune).</span></span>

##  <a name="configure-a-conditional-access-policy"></a><span data-ttu-id="8f86e-150">条件付きアクセス ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="8f86e-150">Configure a conditional access policy</span></span>

1. <span data-ttu-id="8f86e-151">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** > **[条件付きアクセス]** > **[Exchange On-premises ポリシー]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f86e-151">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Conditional Access** > **Exchange on-premises policy**.</span></span>
   <span data-ttu-id="8f86e-152">![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)</span><span class="sxs-lookup"><span data-stu-id="8f86e-152">![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)</span></span>

2. <span data-ttu-id="8f86e-153">必要な設定でポリシーを構成します。![Exchange On-premises ポリシー ページのスクリーンショット](../media/IntuneSA5bExchangeOnPremPolicy.png)</span><span class="sxs-lookup"><span data-stu-id="8f86e-153">Configure the policy with the settings that you require: ![Screenshot of the Exchange on-premises policy page](../media/IntuneSA5bExchangeOnPremPolicy.png)</span></span>

   - <span data-ttu-id="8f86e-154">**[デバイスが Microsoft Intune に準拠していない場合や、登録されていない場合に、電子メール アプリから Exchange Online へのアクセスをブロックします]:** このオプションを選択すると、Intune で管理されていないデバイスまたはコンプライアンス ポリシーに準拠していないデバイスは、Exchange サービスへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-154">**Block email apps from accessing Exchange on-premises if the device isn't compliant or isn't enrolled with Microsoft Intune**: When you select this option, devices that aren't managed by Intune or aren't compliant with a compliance policy are blocked from accessing Exchange services.</span></span>

   - <span data-ttu-id="8f86e-155">**[既定のルールを無視 - 登録された準拠デバイスが常に Exchange にアクセスできるようにする]:** このオプションをオンにすると、Intune に登録され、コンプライアンス ポリシーに準拠しているデバイスは Exchange へのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-155">**Default rule override - Always allow enrolled and compliant devices to access Exchange**: When you select this option, devices that are enrolled in Intune and are compliant with the compliance policies are allowed to access Exchange.</span></span>
     <span data-ttu-id="8f86e-156">このルールは**既定のルール**に優先します。つまり、アクセスを検疫またはブロックする**既定のルール**を設定した場合でも、登録された準拠デバイスは引き続き Exchange にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-156">This rule overrides the **Default Rule**, which means that even if you set the **Default Rule** to quarantine or block access, enrolled and compliant devices are still able to access Exchange.</span></span>

   - <span data-ttu-id="8f86e-157">**[対象グループ]:** Exchange にアクセスするにはデバイスを Intune に登録する必要がある Intune ユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f86e-157">**Targeted Groups**: Select the Intune user groups that must enroll their device with Intune before they can access Exchange.</span></span>

   - <span data-ttu-id="8f86e-158">**[例外グループ]:** 条件付きアクセス ポリシーから除外される Intune ユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f86e-158">**Exempted Groups**: Select the Intune user groups that are exempt from the conditional access policy.</span></span> <span data-ttu-id="8f86e-159">この一覧に指定されたユーザーは、同時に **[対象グループ]** の一覧に指定されている場合でも除外されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-159">Users in this list are exempt even if they're also in the **Targeted Groups** list.</span></span>

   - <span data-ttu-id="8f86e-160">**[プラットフォーム例外]:** **[ルールの追加]** を選択して、指定したモバイル デバイスのファミリとモデルのアクセス レベルを定義するルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="8f86e-160">**Platform Exceptions**: Choose **Add Rule** to configure a rule that defines access levels for specified mobile device families and models.</span></span> <span data-ttu-id="8f86e-161">任意の種類のデバイスを使用できるので、Intune でサポートされていないデバイスの種類を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-161">Because these devices can be of any type, you can also configure device types that aren't supported by Intune.</span></span>

   - <span data-ttu-id="8f86e-162">**[既定のルール]:** 他のどのルールにも含まれていないデバイスの場合、Exchange へのアクセスの許可、Exchange へのアクセスのブロック、検疫のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-162">**Default Rule**: For a device that isn't covered by any of the other rules, you can choose to allow it to access Exchange, block it, or quarantine it.</span></span> <span data-ttu-id="8f86e-163">登録された準拠デバイスに対してアクセスを許可するルールを設定すると、iOS、Windows、および Samsung KNOX のデバイスには電子メールへのアクセス権が自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-163">When you set the rule to allow access, for devices that are enrolled and compliant, email access is granted automatically for iOS, Windows, and Samsung KNOX devices.</span></span> <span data-ttu-id="8f86e-164">ユーザーは自分の電子メールを取得するために何もプロセスを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f86e-164">The user doesn't have to go through any process to get their email.</span></span>
     - <span data-ttu-id="8f86e-165">Samsung KNOX を実行していない Android デバイスの場合、ユーザーには、電子メールにアクセスする前に、登録とコンプライアンスの確認方法に関するチュートリアルを含む検疫電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-165">On Android devices that don't run Samsung KNOX, users get a quarantine email, which includes a guided walkthrough to verify enrollment and compliance before they can access email.</span></span> <span data-ttu-id="8f86e-166">アクセスをブロックするか、デバイスを検疫するルールを設定すると、Intune に登録済みであるかどうかに関係なく、すべてのデバイスが Exchange にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-166">If you set the rule to block access or quarantine devices, all devices are blocked from getting access to Exchange, regardless of whether they're already enrolled in Intune or not.</span></span> <span data-ttu-id="8f86e-167">登録および準拠デバイスがこのルールに影響されるのを防ぐためには、**[既定ルールの上書き]** ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8f86e-167">To prevent enrolled and compliant devices from being affected by this rule, check the **Default Rule Override** box.</span></span>
       >[!TIP]
       ><span data-ttu-id="8f86e-168">電子メールへのアクセスを許可する前にすべてのデバイスをブロックする場合は、アクセスのブロック ルールまたは検疫ルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f86e-168">If your intention is to first block all devices before granting access to email, choose the Block access rule or the Quarantine rule.</span></span> <span data-ttu-id="8f86e-169">既定のルールはすべてのデバイスの種類に適用されるので、プラットフォームの例外として構成されているデバイスの種類や Intune でサポートされていないデバイスの種類も影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-169">The default rule applies to all device types—so device types that you configure as platform exceptions that aren't supported by Intune are also affected.</span></span>

   - <span data-ttu-id="8f86e-170">**[ユーザー通知]:** Exchange から送信される通知電子メールの他に、デバイスのブロック解除の手順が記載された電子メールが Intune によって送信されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-170">**User Notification**: In addition to the notification email that Exchange sends, Intune sends an email that contains steps to unblock the device.</span></span> <span data-ttu-id="8f86e-171">この既定のメッセージは、ニーズに合わせてカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-171">You can edit the default message to customize it to your needs.</span></span> <span data-ttu-id="8f86e-172">修復手順が記載されている Intune 通知電子メールが届く前にユーザーのデバイスがブロックされた場合 (このメールはユーザーの Exchange 受信トレイに送信されます)、ブロックされていないデバイスや、Exchange にアクセスする別の方法を使用して、メッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-172">In the event that the user’s device is blocked before they receive the Intune notification email that contains remediation instructions (this email is delivered to the user’s Exchange mailbox), they can use an unblocked device or another method to access Exchange and view the message.</span></span>
     - <span data-ttu-id="8f86e-173">これは特に**既定のルール**がブロックまたは検疫に設定されている場合に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-173">This is especially true when the **Default Rule** is set to block or quarantine.</span></span> <span data-ttu-id="8f86e-174">この場合、ユーザーはアプリ ストアに移動し、Microsoft ポータル サイト アプリをダウンロードして、デバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-174">In this case, the user has to go to their app store, download the Microsoft Company Portal app, and enroll their device.</span></span> <span data-ttu-id="8f86e-175">これは iOS、Windows、および Samsung KNOX デバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-175">This is applicable to iOS, Windows, and Samsung KNOX devices.</span></span> <span data-ttu-id="8f86e-176">Samsung KNOX を実行していないデバイスの場合は、代替の電子メール アカウントに検疫電子メールを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-176">For devices that don't run Samsung KNOX, you need to send the quarantine email to an alternate email account.</span></span> <span data-ttu-id="8f86e-177">ユーザーはブロックされたデバイスにこの電子メールをコピーして、登録とコンプライアンス プロセスを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-177">The user has to copy the email to their blocked device to complete the enrollment and compliance process.</span></span>
       > [!NOTE]
       > <span data-ttu-id="8f86e-178">Exchange が通知電子メールを送信できるようにするには、通知電子メールの送信に使用されるアカウントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-178">In order for Exchange to be able to send the notification email, you must specify the account that is used to send the notification email.</span></span>
       >
       > <span data-ttu-id="8f86e-179">詳細については、[オンプレミスまたはホスト型 Exchange に対する Exchange On-Premises Connector の構成](intune-on-premises-exchange-connector.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f86e-179">For details, see [Configure Exchange on-premises connector for on-premises or hosted Exchange](intune-on-premises-exchange-connector.md).</span></span>

3. <span data-ttu-id="8f86e-180">終了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f86e-180">When you're done, choose **Save**.</span></span>

-   <span data-ttu-id="8f86e-181">条件付きアクセス ポリシーを展開する必要はありません。直ちに有効になります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-181">You don't have to deploy the conditional access policy—it takes effect immediately.</span></span>

-   <span data-ttu-id="8f86e-182">ユーザーが Exchange ActiveSync のプロファイルを設定してからデバイスがブロックされるまでに、1 ～ 3 時間かかる場合があります (Intune で管理されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="8f86e-182">After a user sets up an Exchange ActiveSync profile, it might take from one to three hours for the device to be blocked (if it isn't managed by Intune).</span></span>

-   <span data-ttu-id="8f86e-183">ブロックされたユーザーがデバイスを Intune に登録し、非準拠の問題を修正すると、メールのアクセスは 2 分以内でブロック解除されます。</span><span class="sxs-lookup"><span data-stu-id="8f86e-183">If a blocked user then enrolls the device with Intune and remediates noncompliance, email access will be unblocked within two minutes.</span></span>

-   <span data-ttu-id="8f86e-184">ユーザーが Intune から登録解除した場合、デバイスがブロックされるまでに 1 ～ 3 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f86e-184">If the user unenrolls from Intune, it might take from one to three hours for the device to be blocked.</span></span>

<span data-ttu-id="8f86e-185">**デバイスのアクセスを保護する条件付きアクセス ポリシーの構成方法を示したシナリオの例[を見るには、](restrict-email-access-example-scenarios.md)電子メール アクセスの保護のシナリオ例**をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f86e-185">**To see some example scenarios of how you would configure a conditional access policy to protect device access, see [Protect email access example scenarios](restrict-email-access-example-scenarios.md).**</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f86e-186">次の手順</span><span class="sxs-lookup"><span data-stu-id="8f86e-186">Next steps</span></span>
-   [<span data-ttu-id="8f86e-187">SharePoint Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="8f86e-187">Protect access to SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

-   [<span data-ttu-id="8f86e-188">Skype for Business Online へのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="8f86e-188">Protect access to Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
