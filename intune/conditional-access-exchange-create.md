---
title: "Exchange On-Premises の条件付きアクセス ポリシーを作成して割り当てる"
titlesuffix: Azure portal
description: "Intune で Exchange On-Premises と従来の Exchange Online Dedicated の条件付きアクセスを構成します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0605bb94c2f9875396cdcdd74685eb8ceb3c2bdc
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-create-and-assign-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune"></a><span data-ttu-id="1f1b5-103">Microsoft Intune で Exchange On-Premises と従来の Exchange Online Dedicated の条件付きアクセス ポリシーを作成して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="1f1b5-103">How to create and assign a conditional access policy for Exchange on-premises and legacy Exchange Online Dedicated in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1f1b5-104">このトピックでは、デバイスのコンプライアンスに基づいて Exchange On-premises の条件付きアクセスを構成するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-104">This topic walks you through the process of configuring conditional access for Exchange on-premises based on device compliance.</span></span>

<span data-ttu-id="1f1b5-105">Exchange Online Dedicated 環境を使用していて、それが新しい構成であるか既存の構成であるかを確認する必要がある場合は、アカウント マネージャーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-105">If you have an Exchange Online Dedicated environment and need to find out whether it is in the new or the legacy configuration, please contact your account manager.</span></span> <span data-ttu-id="1f1b5-106">Exchange On-premises または従来の Exchange Online Dedicated 環境への電子メール アクセスを制御するには、Intune で Exchange On-premises の条件付きアクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-106">To control email access to Exchange on-premises or to your legacy Exchange Online Dedicated environment, configure conditional access to Exchange on-premises in Intune.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1f1b5-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="1f1b5-107">Before you begin</span></span>

<span data-ttu-id="1f1b5-108">条件付きアクセスを構成する前に、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-108">Before you can configure conditional access, verify the following:</span></span>

- <span data-ttu-id="1f1b5-109">Exchange のバージョンは、**Exchange 2010 SP1 以降**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-109">Your Exchange version must be **Exchange 2010 SP1 or later**.</span></span> <span data-ttu-id="1f1b5-110">Exchange Server クライアント アクセス サーバー (CAS) アレイがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-110">Exchange server Client Access Server (CAS) array is supported.</span></span>

- <span data-ttu-id="1f1b5-111">[Exchange Active Sync On-Premises Exchange Connector](exchange-connector-install.md) を使用する必要があります。これは、Intune を Exchange On-Premises に接続します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-111">You must use the [Exchange Active Sync on-premises Exchange connector](exchange-connector-install.md), which connects Intune to on-premises Exchange.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="1f1b5-112">On-Premises Exchange Connector は、Intune テナントに固有であり、他のテナントでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-112">The on-premises Exchange connector is specific to your Intune tenant and cannot be used with any other tenant.</span></span> <span data-ttu-id="1f1b5-113">また、テナントの Exchange Connector は **1 台のコンピューターにのみ**インストールされるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-113">You should also ensure that the exchange connector for your tenant is installed **on only one machine**.</span></span>

- <span data-ttu-id="1f1b5-114">このコネクタは、Exchange サーバーと通信できる任意のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-114">The connector can be installed on any machine as long as that machine is able to communicate with the Exchange server.</span></span>

- <span data-ttu-id="1f1b5-115">このコネクタは、**Exchange CAS 環境**をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-115">The connector supports **Exchange CAS environment**.</span></span> <span data-ttu-id="1f1b5-116">必要であれば、このコネクタを Exchange CAS サーバーに直接インストールすることは技術的に可能ですが、サーバーの負荷が増加するため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-116">You can technically install the connector on the Exchange CAS server directly if you wish to, but it is not recommended, as it will increase the load on the server.</span></span> <span data-ttu-id="1f1b5-117">コネクタを構成するときには、Exchange CAS サーバーのいずれかと通信するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-117">When configuring the connector, you must set it up to communicate to one of the Exchange CAS servers.</span></span>

- <span data-ttu-id="1f1b5-118">**Exchange ActiveSync** は、証明書ベースの認証またはユーザーの資格情報のエントリで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-118">**Exchange ActiveSync** must be configured with certificate based authentication, or user credential entry.</span></span>

- <span data-ttu-id="1f1b5-119">条件付きアクセス ポリシーを構成してユーザーに適用すると、ユーザーが電子メールに接続するには、使用する**デバイス**が以下の条件を満たさなくてはならなくなります。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-119">When conditional access policies are configured and targeted to a user, before a user can connect to their email, the **device** they use must be:</span></span>
    - <span data-ttu-id="1f1b5-120">Intune に**登録**されているか、ドメインに参加している PC である。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-120">Either **enrolled** with Intune or is a domain joined PC.</span></span>
    - <span data-ttu-id="1f1b5-121">**Azure Active Directory に登録されている**。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-121">**Registered in Azure Active Directory**.</span></span> <span data-ttu-id="1f1b5-122">また、クライアントの Exchange ActiveSync ID を Azure Active Directory に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-122">Additionally, the client Exchange ActiveSync ID must be registered with Azure Active Directory.</span></span>
<br></br>
- <span data-ttu-id="1f1b5-123">AAD DRS は、Intune や Office 365 のお客様に対して自動的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-123">AAD DRS will be activated automatically for Intune and Office 365 customers.</span></span> <span data-ttu-id="1f1b5-124">ADFS Device Registration Service をデプロイ済みのお客様には、オンプレミスの Active Directory で登録されたデバイスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-124">Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory.</span></span> <span data-ttu-id="1f1b5-125">**これは、Windows PC と Windows Phone デバイスには適用されません。**</span><span class="sxs-lookup"><span data-stu-id="1f1b5-125">**This does not apply to Windows PCs and Windows Phone devices**.</span></span>

- <span data-ttu-id="1f1b5-126">そのデバイスに展開されているデバイス コンプライアンス ポリシーに**準拠**している。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-126">**Compliant** with device compliance policies deployed to that device.</span></span>

- <span data-ttu-id="1f1b5-127">デバイスが条件付きアクセス設定を満たしていない場合、ユーザーのログイン時に、次のいずれかのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-127">If the device does not meet conditional access settings, the user is presented with one of the following messages when they log in:</span></span>
    - <span data-ttu-id="1f1b5-128">デバイスが Intune に登録されていない、または Azure Active Directory に登録されていない場合は、ポータル サイト アプリのインストール、デバイスの登録、電子メールのアクティブ化の手順が示されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-128">If the device is not enrolled with Intune, or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app, enroll the device, and activate email.</span></span> <span data-ttu-id="1f1b5-129">また、このプロセスによって、デバイスの Exchange ActiveSync ID が Azure Active Directory のデバイス レコードに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-129">This process also associates the device's Exchange ActiveSync ID with the device record in Azure Active Directory.</span></span>
    - <span data-ttu-id="1f1b5-130">デバイスが準拠していない場合は、Intune のポータル サイト Web サイトまたはポータル サイト アプリにユーザーを誘導するメッセージが表示されます。このポータルで、ユーザーは問題とその解決方法に関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-130">If the device is not compliant, a message is displayed that directs the user to the Intune Company Portal website, or the Company Portal app where they can find information about the problem and how to remediate it.</span></span>

### <a name="support-for-mobile-devices"></a><span data-ttu-id="1f1b5-131">モバイル デバイスのサポート</span><span class="sxs-lookup"><span data-stu-id="1f1b5-131">Support for mobile devices</span></span>

- <span data-ttu-id="1f1b5-132">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="1f1b5-132">Windows Phone 8.1 and later</span></span>
- <span data-ttu-id="1f1b5-133">iOS のネイティブ電子メール アプリ。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-133">Native email app on iOS.</span></span>
- <span data-ttu-id="1f1b5-134">Android 4 以降での EAS メール クライアント (Gmail など)。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-134">EAS mail clients such as Gmail on Android 4 or later.</span></span>
- <span data-ttu-id="1f1b5-135">EAS メール クライアント **Android for Work デバイス:** Android for Work デバイスでは、**仕事用プロファイル**の **Gmail** アプリと **Nine Work** アプリのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-135">EAS mail clients **Android for Work devices:** Only **Gmail** and **Nine Work** apps in the **work profile** are supported on Android for Work devices.</span></span> <span data-ttu-id="1f1b5-136">条件付きアクセスが Android for Work で動作するには、Gmail アプリまたは Nine Work アプリ用の電子メール プロファイルを展開する必要があります。また、必要なインストールとしてそのアプリを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-136">For conditional access to work with Android for Work, you must deploy an email profile for the Gmail or Nine Work app, and also deploy those apps as a required install.</span></span>

> [!NOTE]
> <span data-ttu-id="1f1b5-137">Android と iOS の Microsoft Outlook アプリはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-137">Microsoft Outlook app for Android and iOS is not supported.</span></span> <span data-ttu-id="1f1b5-138">Android for Work は現在、Intune テナント全体にロールアウトされているところであり、今後数か月にわたりこの作業が行われます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-138">Android for Work is currently being rolled out across Intune tenants over the next few months.</span></span>

### <a name="support-for-pcs"></a><span data-ttu-id="1f1b5-139">PC のサポート</span><span class="sxs-lookup"><span data-stu-id="1f1b5-139">Support for PCs</span></span>

<span data-ttu-id="1f1b5-140">Windows 8.1 以降用のネイティブ **メール** アプリケーション (Intune に登録されている場合)</span><span class="sxs-lookup"><span data-stu-id="1f1b5-140">The native **Mail** application on Windows 8.1 and later (when enrolled with Intune)</span></span>


## <a name="configure-exchange-on-premises-access"></a><span data-ttu-id="1f1b5-141">Exchange On-premises アクセスの構成</span><span class="sxs-lookup"><span data-stu-id="1f1b5-141">Configure Exchange on-premises access</span></span>

1. <span data-ttu-id="1f1b5-142">[Azure Portal](https://portal.azure.com/) に移動し、Intune 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-142">Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.</span></span>

2. <span data-ttu-id="1f1b5-143">正常にサインインすると、**Azure ダッシュボード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-143">After you've successfully signed in, you see the **Azure Dashboard**.</span></span>

3. <span data-ttu-id="1f1b5-144">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-144">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

4. <span data-ttu-id="1f1b5-145">**[Intune]** を選ぶと、**Intune ダッシュボード**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-145">Choose **Intune**, you see the **Intune Dashboard**.</span></span>

5. <span data-ttu-id="1f1b5-146">**[オンプレミス アクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-146">Choose **On-Premise Access**, then choose</span></span>

6. <span data-ttu-id="1f1b5-147">**[On-premises]** ブレードには、条件付きアクセス ポリシーの状態と、その影響を受けるデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-147">The **On-premises** blade shows the status of the conditional access policy and the devices that are affected by it.</span></span>

7. <span data-ttu-id="1f1b5-148">**[管理]** で、**[Exchange On-Premises のアクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-148">Under **Manage**, choose **Exchange on-premises access**.</span></span>

8. <span data-ttu-id="1f1b5-149">**[Exchange On-premises のアクセス]** ブレードで **[はい]** を選択し、Exchange On-premises アクセス制御を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-149">On the **Exchange on-premises access** blade, choose **Yes** to enable Exchange on-premises access control.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f1b5-150">Exchange Active Sync On-Premises Connector を構成していない場合、このオプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-150">If you have not configured the Exchange Active Sync on-premises connector, this option will be disabled.</span></span>  <span data-ttu-id="1f1b5-151">Exchange On-premises の条件付きアクセスを有効にするには、このコネクタをインストールして構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-151">You must first install and configure this connector before enabling conditional access for Exchange on-premises.</span></span> <span data-ttu-id="1f1b5-152">詳細については、[Intune On-premises Exchange Connector のインストール](exchange-connector-install.md)に関するページを参照してください</span><span class="sxs-lookup"><span data-stu-id="1f1b5-152">For more details, see [Install the Intune On-premises Exchange Connector](exchange-connector-install.md)</span></span>

9. <span data-ttu-id="1f1b5-153">**[割り当て]** で、**[組み込まれたグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-153">Under **Assignment**, choose **Groups Included**.</span></span>  <span data-ttu-id="1f1b5-154">条件付きアクセスが適用されているセキュリティ ユーザー グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-154">Use the security user group that should have conditional access applied to it.</span></span> <span data-ttu-id="1f1b5-155">これによりユーザーは自分のデバイスを Intune に登録し、コンプライアンス プロファイルに準拠する必要ができます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-155">This would require the users to enroll their devices in Intune and be compliant with the compliance profiles.</span></span>

10. <span data-ttu-id="1f1b5-156">特定のユーザー グループを除外するには、**[除外されたグループ]** を選択し、デバイスの登録とコンプライアンスから除外するユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-156">If you want to exclude a certain groups of users, you can do so by choosing **Groups Excluded** and selecting a user group that you want to be exempt from requiring device enrollment and compliance.</span></span>

11. <span data-ttu-id="1f1b5-157">**[設定]** で **[ユーザーへの通知]** を選択して、既定の電子メール メッセージを変更します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-157">Under **Settings**, choose **User notifications** to modify the default email message.</span></span> <span data-ttu-id="1f1b5-158">このメッセージは、準拠していないデバイスでユーザーが Exchange On-premises にアクセスしようとしたときに送信されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-158">This message is sent to users if their device is not compliant and they want to access Exchange on-premises.</span></span> <span data-ttu-id="1f1b5-159">メッセージ テンプレートでは、マークアップ言語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-159">The message template uses Markup language.</span></span>  <span data-ttu-id="1f1b5-160">また入力しながら、メッセージがどのように表示されるかもプレビュー表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-160">You will also see the preview of how the message looks as you type.</span></span>
    > [!TIP]
    > <span data-ttu-id="1f1b5-161">マークアップ言語の詳細については、Wikipedia の[こちらの記事](https://en.wikipedia.org/wiki/Markup_language)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-161">To learn more about Markup language see this Wikipedia [article](https://en.wikipedia.org/wiki/Markup_language).</span></span>

12. <span data-ttu-id="1f1b5-162">次の 2 つの手順に従って、**[Advanced Exchange Active Sync access settings (Exchange Active Sync アクセスの詳細設定)]** ブレードで、Intune で管理されていないデバイスからのアクセスに対して既定のグローバル ルールを設定するか、プラットフォームレベルのルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-162">On the **Advanced Exchange Active Sync access settings** blade, set the global default rule for access from devices that are not managed by Intune, and for platform-level rules as described in the next two steps.</span></span>

13. <span data-ttu-id="1f1b5-163">条件付きアクセスまたは他のルールの影響を受けないデバイスについては、デバイスによる Exchange へのアクセスを許可するかブロックするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-163">For a device that is not affected by conditional access or other rules, you can choose to allow it to access Exchange, or block it.</span></span>
    - <span data-ttu-id="1f1b5-164">アクセスを許可するように設定した場合、すべてのデバイスが Exchange On-premises に直ちにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-164">When you set this to allow access, all devices will be able to access Exchange on-premises immediately.</span></span>  <span data-ttu-id="1f1b5-165">**[組み込まれたグループ]** のユーザーのデバイスについては、そのデバイスが後でコンプライアンス ポリシーに非準拠と評価されたり、Intune に登録されていなかったりするとブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-165">Devices that belong to the users in the **Groups Included**, are blocked if they are subsequently evaluated as not compliant with the compliant policies or not enrolled in Intune.</span></span>
    - <span data-ttu-id="1f1b5-166">アクセスをブロックするように設定した場合、最初はすべてのデバイスが直ちに Exchange On-premises にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-166">When you set this to block access, all devices will be immediately blocked from accessing Exchange on-premises initially.</span></span>  <span data-ttu-id="1f1b5-167">**[組み込まれたグループ]** のユーザーのデバイスについては、そのデバイスが Intune に登録され、準拠と評価されると許可されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-167">Devices that belong to users in the **Groups Included** will get access once the device is enrolled in Intune and is evaluated as compliant.</span></span> <span data-ttu-id="1f1b5-168">Samsung KNOX Standard が実行されていない Android デバイスは、この設定をサポートしていないため常にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-168">On Android devices that do not run Samsung KNOX standard will always be blocked as they do not support this setting.</span></span>
    <br></br>
14. <span data-ttu-id="1f1b5-169">**[デバイス プラットフォームの例外]** で、**[追加]** を選択してプラットフォームを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-169">Under **Device platform exceptions**, choose **Add** to specify the platforms.</span></span> <span data-ttu-id="1f1b5-170">**[管理対象外デバイス アクセス]** 設定が "**ブロック済み**" に設定されている場合は、ブロックに対してプラットフォーム例外があっても、登録済みの準拠デバイスは許可されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-170">If the **unmanaged device access** setting is set to **blocked**, devices that are enrolled and compliant will be allowed even if there is a platform exception to block.</span></span> <span data-ttu-id="1f1b5-171">**[OK]** を選択して、設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-171">Choose **Ok** to save the settings.</span></span>

15. <span data-ttu-id="1f1b5-172">**[On-premises]** ブレードで **[保存]** をクリックして、条件付きアクセス ポリシーを保存します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-172">On the **On-premises** blade, click **Save** to save the conditional access policy.</span></span>

## <a name="create-azure-ad-conditional-access-policies-in-intune"></a><span data-ttu-id="1f1b5-173">Intune で Azure AD の条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1f1b5-173">Create Azure AD Conditional access policies in Intune</span></span>

<span data-ttu-id="1f1b5-174">Intune 1704 リリース以降では、管理者は Intune Azure Portal から Azure AD の条件付きアクセス ポリシーを作成できます。Azure と Intune のワークロードを切り替える必要がなくて便利です。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-174">Beginning with Intune 1704 release, admins can create Azure AD conditional access policies from the Intune Azure portal, which gives convenience so you don't need to switch between the Azure and Intune workloads.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f1b5-175">Intune Azure Portal から Azure AD の条件付きアクセス ポリシーを作成するには、Azure AD Premium ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-175">You need to have an Azure AD Premium license to create Azure AD conditional access policies from the Intune Azure portal.</span></span>

### <a name="to-create-azure-ad-conditional-access-policy"></a><span data-ttu-id="1f1b5-176">Azure AD 条件付きアクセス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="1f1b5-176">To create Azure AD conditional access policy</span></span>

1. <span data-ttu-id="1f1b5-177">**Intune ダッシュボード**で、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-177">In the **Intune Dashboard**, choose **Conditional access**.</span></span>

2. <span data-ttu-id="1f1b5-178">**[ポリシー]** ブレードで、**[新しいポリシー]** を選択し、新しい Azure AD 条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f1b5-178">In the **Policies** blade, choose **New policy** to create your new Azure AD conditional access policy.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f1b5-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f1b5-179">See also</span></span>

[<span data-ttu-id="1f1b5-180">Azure Active Directory の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="1f1b5-180">Conditional Access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
