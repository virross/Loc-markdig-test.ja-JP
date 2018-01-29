---
title: "Intune との Lookout 統合を設定する"
titlesuffix: Azure portal
description: "Intune を使用した Lookout サブスクリプションの設定"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4d3cfbe10b88baeef3164191516482c40046bf09
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="set-up-your-lookout-mobile-threat-defense-integration-with-intune"></a><span data-ttu-id="289dd-103">Intune との Lookout Mobile Threat Defense 統合を設定する</span><span class="sxs-lookup"><span data-stu-id="289dd-103">Set up your Lookout Mobile Threat Defense integration with Intune</span></span>

<span data-ttu-id="289dd-104">Lookout Mobile Threat Defense のサブスクリプションを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="289dd-104">The following steps are required to set up Lookout Mobile Threat Defense subscription:</span></span>

| #        |<span data-ttu-id="289dd-105">手順</span><span class="sxs-lookup"><span data-stu-id="289dd-105">Step</span></span>  |
| ------------- |:-------------|
| <span data-ttu-id="289dd-106">1</span><span class="sxs-lookup"><span data-stu-id="289dd-106">1</span></span> | [<span data-ttu-id="289dd-107">Azure AD の情報を収集する</span><span class="sxs-lookup"><span data-stu-id="289dd-107">Collect Azure AD information</span></span>](#collect-azure-ad-information) |
| <span data-ttu-id="289dd-108">2</span><span class="sxs-lookup"><span data-stu-id="289dd-108">2</span></span> | [<span data-ttu-id="289dd-109">サブスクリプションを構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-109">Configure your subscription</span></span>](#configure-your-subscription) |
| <span data-ttu-id="289dd-110">3</span><span class="sxs-lookup"><span data-stu-id="289dd-110">3</span></span> | [<span data-ttu-id="289dd-111">登録グループを構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-111">Configure enrollment groups</span></span>](#configure-enrollment-groups) |
| <span data-ttu-id="289dd-112">4</span><span class="sxs-lookup"><span data-stu-id="289dd-112">4</span></span> | [<span data-ttu-id="289dd-113">状態の同期を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-113">Configure state sync</span></span>](#configure-state-sync) |
| <span data-ttu-id="289dd-114">5</span><span class="sxs-lookup"><span data-stu-id="289dd-114">5</span></span> | [<span data-ttu-id="289dd-115">エラー レポートの電子メール受信者情報を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-115">Configure error report email recipient information</span></span>](#configure-error-report-email-recipient-information) |
| <span data-ttu-id="289dd-116">6</span><span class="sxs-lookup"><span data-stu-id="289dd-116">6</span></span> | [<span data-ttu-id="289dd-117">登録設定を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-117">Configure enrollment settings</span></span>](#configure-enrollment-settings) |
| <span data-ttu-id="289dd-118">7</span><span class="sxs-lookup"><span data-stu-id="289dd-118">7</span></span> | [<span data-ttu-id="289dd-119">電子メールの通知を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-119">Configure email notifications</span></span>](#configure-email-notifications) |
| <span data-ttu-id="289dd-120">8</span><span class="sxs-lookup"><span data-stu-id="289dd-120">8</span></span> | [<span data-ttu-id="289dd-121">脅威の分類を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-121">Configure threat classification</span></span>](#configure-threat-classification) |
| <span data-ttu-id="289dd-122">9</span><span class="sxs-lookup"><span data-stu-id="289dd-122">9</span></span> | [<span data-ttu-id="289dd-123">登録を監視する</span><span class="sxs-lookup"><span data-stu-id="289dd-123">Watching enrollment</span></span>](#watching-enrollment) |

> [!IMPORTANT]
> <span data-ttu-id="289dd-124">Azure AD と Intune の統合に、Azure AD と関連付けられていない既存の Lookout Mobile Endpoint Security テナントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="289dd-124">An existing Lookout Mobile Endpoint Security tenant that is not already associated with your Azure AD tenant cannot be used for the integration with Azure AD and Intune.</span></span> <span data-ttu-id="289dd-125">新しい Lookout Mobile Endpoint Security テナントを作成するように、Lookout のサポートに依頼してください。</span><span class="sxs-lookup"><span data-stu-id="289dd-125">Contact Lookout support to create a new Lookout Mobile Endpoint Security tenant.</span></span> <span data-ttu-id="289dd-126">Azure AD ユーザーの追加にはこの新しいテナントを使用してください。</span><span class="sxs-lookup"><span data-stu-id="289dd-126">Use the new tenant to onboard your Azure AD users.</span></span>

## <a name="collect-azure-ad-information"></a><span data-ttu-id="289dd-127">Azure AD の情報を収集する</span><span class="sxs-lookup"><span data-stu-id="289dd-127">Collect Azure AD information</span></span>
<span data-ttu-id="289dd-128">Lookout を Intune に統合するために、Lookout Mobility Endpoint Security テナントが Azure AD サブスクリプションに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="289dd-128">Your Lookout Mobility Endpoint Security tenant will be associated with your Azure AD subscription to integrate Lookout with Intune.</span></span> <span data-ttu-id="289dd-129">Lookout Mobile Threat Defense サービスのサブスクリプションを有効にするには、Lookout のサポート (enterprisesupport@lookout.com) に次の情報を伝えてください。</span><span class="sxs-lookup"><span data-stu-id="289dd-129">To enable your Lookout Mobile Threat Defense service subscription, Lookout support (enterprisesupport@lookout.com) needs the following information:</span></span>

* <span data-ttu-id="289dd-130">**Azure AD テナント ID**</span><span class="sxs-lookup"><span data-stu-id="289dd-130">**Azure AD Tenant ID**</span></span>
* <span data-ttu-id="289dd-131">Lookout コンソールへの**フル** アクセス用の **Azure AD グループ オブジェクト ID**</span><span class="sxs-lookup"><span data-stu-id="289dd-131">**Azure AD Group Object ID** for **full** Lookout console access</span></span>
* <span data-ttu-id="289dd-132">Lookout コンソールへの**制限付き**アクセス用の **Azure AD グループ オブジェクト ID** (省略可能)</span><span class="sxs-lookup"><span data-stu-id="289dd-132">**Azure AD Group Object ID** for **restricted** Lookout console access (optional)</span></span>

<span data-ttu-id="289dd-133">次の手順に従って、Lookout サポート チームに提供する必要のある情報を収集してください。</span><span class="sxs-lookup"><span data-stu-id="289dd-133">Use the following steps to gather the information you need to give to the Lookout support team.</span></span>

1. <span data-ttu-id="289dd-134">[Azure Portal](https://portal.azure.com) にサインインして、サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="289dd-134">Sign in to the [Azure portal](https://portal.azure.com) and select your subscription.</span></span> 

2. <span data-ttu-id="289dd-135">サブスクリプションの名前を選択すると、表示される URL にサブスクリプション ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="289dd-135">When you choose the name of your subscription, the resulting URL includes the subscription ID.</span></span>  <span data-ttu-id="289dd-136">サブスクリプション ID を検索する際に問題が生じた場合は、サブスクリプション ID の検索方法に関するヒントが記載されているこちらの [Microsoft サポート記事](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="289dd-136">If you have any issues finding your subscription ID, see this [Microsoft support article](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b) for tips on finding your subscription ID.</span></span>

3. <span data-ttu-id="289dd-137">Azure AD のグループ ID を確認します。</span><span class="sxs-lookup"><span data-stu-id="289dd-137">Find your Azure AD Group ID.</span></span> <span data-ttu-id="289dd-138">Lookout コンソールでは、次の 2 つのレベルのアクセスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="289dd-138">The Lookout console supports 2 levels of access:</span></span>  
   * <span data-ttu-id="289dd-139">**フル アクセス:** Azure AD の管理者は、フル アクセス権を持つユーザーのグループを作成できるだけでなく、必要に応じて制限付きアクセス権を持つユーザーのグループも作成できます。</span><span class="sxs-lookup"><span data-stu-id="289dd-139">**Full Access:** The Azure AD admin can create a group for users that will have Full Access and optionally create a group for users that will have Restricted Access.</span></span>  <span data-ttu-id="289dd-140">これらのグループのユーザーだけが、**Lookout コンソール**にログインできます。</span><span class="sxs-lookup"><span data-stu-id="289dd-140">Only users in these groups will be able to login to the **Lookout console**.</span></span>
   * <span data-ttu-id="289dd-141">**制限付きアクセス:** このグループのユーザーは、Lookout コンソールの構成と登録に関するモジュールにはアクセスできません。Lookout コンソールの**セキュリティ ポリシー** モジュールには読み取り専用でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="289dd-141">**Restricted Access:** The users in this group will have no access to several configuration and enrollment related modules of the Lookout console, and have read-only access to the **Security Policy** module of the Lookout console.</span></span>  

     > [!TIP] 
     > <span data-ttu-id="289dd-142">アクセス許可の詳細については、Lookout Web サイトの[こちらの記事](https://personal.support.lookout.com/hc/articles/114094105653)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="289dd-142">For more details on the permissions, read [this article](https://personal.support.lookout.com/hc/articles/114094105653) on the Lookout website.</span></span>

     > [!NOTE] 
     > <span data-ttu-id="289dd-143">**グループ オブジェクト ID** は、**Azure AD 管理ポータル**のグループの**プロパティ** ページにあります。</span><span class="sxs-lookup"><span data-stu-id="289dd-143">The **Group Object ID** is on the **Properties** page of the group in the **Azure AD management portal**.</span></span>

4. <span data-ttu-id="289dd-144">この情報を収集した後で、Lookout のサポート (メール: enterprisesupport@lookout.com) にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="289dd-144">Once you have gathered this information, contact Lookout support (email: enterprisesupport@lookout.com).</span></span> <span data-ttu-id="289dd-145">Lookout のサポート担当者は、お客様の連絡窓口となっている方と協力し、収集された情報を使用してサブスクリプションの登録と Lookout Enterprise アカウントの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="289dd-145">Lookout Support will work with your primary contact to onboard your subscription and create your Lookout Enterprise account, using the information that you collected.</span></span>

## <a name="configure-your-subscription"></a><span data-ttu-id="289dd-146">サブスクリプションを構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-146">Configure your subscription</span></span>

1. <span data-ttu-id="289dd-147">ログイン url へのリンクで、会社の第一連絡先担当者に Lookout から電子メールを送信 Lookout サポートには、Lookout エンタープライズ アカウントが作成されたら、:<https://aad.lookout.com/les?action=consent>です。</span><span class="sxs-lookup"><span data-stu-id="289dd-147">After Lookout support creates your Lookout Enterprise account, an email from Lookout is sent to the primary contact for your company with a link to the login url:<https://aad.lookout.com/les?action=consent>.</span></span>

2. <span data-ttu-id="289dd-148">Lookout コンソールに初めてログインする場合、グローバル管理者の Azure AD ロールを持つユーザー アカウントを使用し、Azure AD テナントを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="289dd-148">The first login to the Lookout console must be by with a user account with the Azure AD role of Global Admin to register your Azure AD tenant.</span></span> <span data-ttu-id="289dd-149">以降のサインインにこのレベルの Azure AD 特権は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="289dd-149">Later, sign in doesn't this level of Azure AD privilege.</span></span> <span data-ttu-id="289dd-150">同意ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="289dd-150">A consent page is displayed.</span></span> <span data-ttu-id="289dd-151">**[同意]** を選んで登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="289dd-151">Choose **Accept** to complete the registration.</span></span> <span data-ttu-id="289dd-152">承諾して同意すると、Lookout コンソールが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="289dd-152">Once you have accepted and consented, you are redirected to the Lookout Console.</span></span>

   ![Lookout コンソールの初回ログイン ページのスクリーンショット](./media/lookout_mtp_initial_login.png)
   > [!NOTE] 
   > <span data-ttu-id="289dd-154">ログインで問題が発生した場合は、「[Lookout と Intune の統合に関するトラブルシューティング](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="289dd-154">See [troubleshooting Lookout integration](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration) for help with login problems.</span></span>

3. <span data-ttu-id="289dd-155">[Lookout コンソール](https://aad.lookout.com)で **[System]** (システム) モジュールから **[Connectors]\** (コネクタ) タブを選択し、**[Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="289dd-155">In the [Lookout Console](https://aad.lookout.com), from the **System** module, choose the **Connectors** tab, and select **Intune**.</span></span>

   ![Lookout コンソールの 「Connectors」\ (コネクタ) タブが開き [Intune] オプションが強調されている状態のスクリーンショット](./media/lookout_mtp_setup-intune-connector.png)

4. <span data-ttu-id="289dd-157">**[Connectors]\(コネクタ)** > **[Connection Settings]\(接続設定)** を選択し、**[Heartbeat Frequency]\(ハートビート頻度)** を分単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="289dd-157">Go **Connectors** > **Connection Settings** and specify the **Heartbeat Frequency** in minutes.</span></span>

   ![ハートビート周期が構成されている接続設定タブのスクリーンショット](./media/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a><span data-ttu-id="289dd-159">登録グループを構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-159">Configure enrollment groups</span></span>
1. <span data-ttu-id="289dd-160">ベスト プラクティスとして、Lookout の統合をテストする少数のユーザーを含む Azure AD セキュリティ グループを [Azure AD 管理ポータル](https://manage.windowsazure.com)に作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="289dd-160">As a best practice, create an Azure AD security group in the [Azure AD management portal](https://manage.windowsazure.com) containing a small number of users to test Lookout integration.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="289dd-161">Azure AD の登録グループに属するユーザーが有する、Lookout のサポートを受け Intune に登録されているデバイスのうち、識別されてサポートされているものはすべて、Lookout MTD コンソールでのアクティブ化の対象になります。</span><span class="sxs-lookup"><span data-stu-id="289dd-161">All the Lookout-supported, Intune-enrolled devices of users in an enrollment group in Azure AD that are identified and supported are enrolled and eligible for activation in Lookout MTD console.</span></span>

2. <span data-ttu-id="289dd-162">[Lookout コンソール](https://aad.lookout.com)の **[System]**\(システム) モジュールで、**[Connectors]**\(コネクタ) タブを選択し、**[Enrollment Management]**\(登録管理) を選択し、Lookout に登録するデバイスのユーザー セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="289dd-162">In the [Lookout Console](https://aad.lookout.com), from the **System** module, choose the **Connectors** tab, and select **Enrollment Management** to define a set of users whose devices should be enrolled with Lookout.</span></span> <span data-ttu-id="289dd-163">Azure AD セキュリティ グループの登録の **[表示名]** を追加します。</span><span class="sxs-lookup"><span data-stu-id="289dd-163">Add the Azure AD security group **Display Name** for enrollment.</span></span>

    ![Intune コネクタ登録ページのスクリーンショット](./media/lookout-mtp-enrollment.png)

    >[!IMPORTANT]
    > <span data-ttu-id="289dd-165">Azure ポータルのセキュリティ グループの **[プロパティ]** に表示される **[表示名]** は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="289dd-165">The  **Display Name** is case sensitive as shown the in the **Properties** of the security group in the Azure portal.</span></span> <span data-ttu-id="289dd-166">次の画像のように、セキュリティ グループの **[表示名]** は大文字と小文字が混在していますが、タイトルはすべて小文字です。</span><span class="sxs-lookup"><span data-stu-id="289dd-166">As shown in the image below, the **Display Name** of the security group is camel case while the title is all lower case.</span></span> <span data-ttu-id="289dd-167">Lookout コンソールでは、セキュリティ グループの **[表示名]** の大文字/小文字と一致させます。</span><span class="sxs-lookup"><span data-stu-id="289dd-167">In the Lookout console match the **Display Name** case for the security group.</span></span>
    ><span data-ttu-id="289dd-168">![Azure Portal の Azure Active Directory サービスの [プロパティ] ページのスクリーンショット](./media/aad-group-display-name.png)</span><span class="sxs-lookup"><span data-stu-id="289dd-168">![screenshot of the Azure portal, Azure Active Directory service, properties page](./media/aad-group-display-name.png)</span></span>

    >[!NOTE] 
    ><span data-ttu-id="289dd-169">新しいデバイスをチェックする間隔には、既定値 (5 分) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="289dd-169">The best practice is to use the default (5 minutes) for the increment of time to check for new devices.</span></span> <span data-ttu-id="289dd-170">現時点での制限事項、**Lookout はグループの表示名を検証できません:** Azure Portal の **[表示名]** フィールドが Azure AD セキュリティ グループと厳密に一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="289dd-170">Current limitations, **Lookout cannot validate group display names:** Ensure the **DISPLAY NAME** field in the Azure portal exactly matches the Azure AD security group.</span></span> <span data-ttu-id="289dd-171">**入れ子のグループを作成することはできません:** Lookout で使用する Azure AD セキュリティ グループには、ユーザーのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="289dd-171">**Creating nest groups is not supported:**  Azure AD security groups used in Lookout must contain users only.</span></span> <span data-ttu-id="289dd-172">他のグループを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="289dd-172">They cannot contain other groups.</span></span>

3.  <span data-ttu-id="289dd-173">グループを追加して、次にサポートされるデバイスでユーザーが Lookout for Work アプリを開いたときに、そのデバイスが Lookout でアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="289dd-173">Once a group is added, the next time a user opens the Lookout for Work app on their supported device, the device is activated in Lookout.</span></span>

4.  <span data-ttu-id="289dd-174">結果に問題がなければ、他のユーザー グループまで登録を広げます。</span><span class="sxs-lookup"><span data-stu-id="289dd-174">Once you are satisfied with your results, extend enrollment to additional user groups.</span></span>

## <a name="configure-state-sync"></a><span data-ttu-id="289dd-175">状態の同期を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-175">Configure state sync</span></span>
<span data-ttu-id="289dd-176">**[State Sync]** (状態同期) オプションで、Intune に送信する必要があるデータの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="289dd-176">In the **State Sync** option, specify the type of data that should be sent to Intune.</span></span>  <span data-ttu-id="289dd-177">Lookout と Intune の統合が正常に動作するには、デバイスの状態と脅威の状態の両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="289dd-177">Both device status and threat status are required for the Lookout Intune integration to work correctly.</span></span> <span data-ttu-id="289dd-178">これらの設定は既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="289dd-178">These settings are enabled by default.</span></span>

## <a name="configure-error-report-email-recipient-information"></a><span data-ttu-id="289dd-179">エラー レポートの電子メール受信者情報を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-179">Configure error report email recipient information</span></span>
<span data-ttu-id="289dd-180">**[Error Management]** (エラー管理) オプションで、エラー レポートを受け取る電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="289dd-180">In the **Error Management** option, enter the email address that should receive the error reports.</span></span>

![Intune コネクタ エラー管理ページのスクリーンショット](./media/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a><span data-ttu-id="289dd-182">登録設定を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-182">Configure enrollment settings</span></span>
<span data-ttu-id="289dd-183">**[System]**\ (モジュール) の **[Connectors]**\ (コネクタ) ページで、デバイスが切断されたと判断されるまでの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="289dd-183">In the **System** module, on the **Connectors** page, specify the number of days before a device is considered as disconnected.</span></span>  <span data-ttu-id="289dd-184">切断されたデバイスは非準拠と見なされ、Intune の条件付きアクセス ポリシーに基づいて会社のアプリケーションにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="289dd-184">Disconnected devices are considered as non-compliant and will be blocked from accessing your company applications based on the Intune conditional access policies.</span></span> <span data-ttu-id="289dd-185">1 から 90 日の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="289dd-185">You can specify values between 1 and 90 days.</span></span>

![Lookout 登録設定](./media/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a><span data-ttu-id="289dd-187">電子メールの通知を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-187">Configure email notifications</span></span>
<span data-ttu-id="289dd-188">脅威に関する電子メール通知を受け取りたい場合は、通知を受け取るユーザー アカウントで [Lookout コンソール](https://aad.lookout.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="289dd-188">If you want to receive email alerts for threats, sign in to the [Lookout console](https://aad.lookout.com) with the user account that should receive notifications.</span></span> <span data-ttu-id="289dd-189">**[System]** (システム) モジュールの **[Preferences]** (基本設定) タブで、通知が必要な脅威レベルを選択して、**[ON]** (オン) に設定します。</span><span class="sxs-lookup"><span data-stu-id="289dd-189">On the **Preferences** tab of the **System** module, choose the threat levels that should  notifications and set them to **ON**.</span></span> <span data-ttu-id="289dd-190">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="289dd-190">Save your changes.</span></span>

<span data-ttu-id="289dd-191">![ユーザー アカウントが表示された基本設定ページのスクリーンショット](./media/lookout-mtp-email-notifications.png) 電子メール通知を受け取る必要がなくなった場合は、通知を **[OFF]** (オフ) に設定して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="289dd-191">![screenshot of the preferences page with the user account displayed](./media/lookout-mtp-email-notifications.png) If you no longer want to receive email notifications, set the notifications to **OFF** and save your changes.</span></span>

### <a name="configure-threat-classification"></a><span data-ttu-id="289dd-192">脅威の分類を構成する</span><span class="sxs-lookup"><span data-stu-id="289dd-192">Configure threat classification</span></span>
<span data-ttu-id="289dd-193">Lookout Mobile Threat Defense によって、さまざまな種類のモバイルの脅威が分類されます。</span><span class="sxs-lookup"><span data-stu-id="289dd-193">Lookout Mobile Threat Defense classifies mobile threats of various types.</span></span> <span data-ttu-id="289dd-194">[Lookout の脅威の分類](http://personal.support.lookout.com/hc/articles/114094130693)には、既定のリスク レベルが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="289dd-194">The [Lookout threat classifications](http://personal.support.lookout.com/hc/articles/114094130693) have default risk levels associated with them.</span></span> <span data-ttu-id="289dd-195">これらは会社の要件に合わせていつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="289dd-195">These can be changed at any time to suit your company requirements.</span></span>

![脅威と分類を示すポリシー ページのスクリーンショット](./media/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> <span data-ttu-id="289dd-197">リスク レベルは、Mobile Threat Defense における重要な要素の 1 つです。デバイスのコンプライアンスは、これらのリスク レベルに従って実行時に計算されるためです。</span><span class="sxs-lookup"><span data-stu-id="289dd-197">Risk levels are an important aspect of Mobile Threat Defense because the Intune integration calculates device compliance according to these risk levels at runtime.</span></span> <span data-ttu-id="289dd-198">Intune 管理者が設定するポリシーのルールに従って、デバイスはアクティブな脅威の最低レベルが**高**、**中**、または**低**の場合に非準拠と判断されます。</span><span class="sxs-lookup"><span data-stu-id="289dd-198">The Intune administrator sets a rule in policy to identify a device as non-compliant if the device has an active threat with a minimum level of **High**, **Medium**, or **Low**.</span></span> <span data-ttu-id="289dd-199">Mobile Threat Defense での脅威分類ポリシーは、Intune でのデバイスのコンプライアンス計算に直接影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="289dd-199">The threat classification policy in Lookout Mobile Threat Defense directly drives the device compliance calculation in Intune.</span></span>

## <a name="watching-enrollment"></a><span data-ttu-id="289dd-200">登録を監視する</span><span class="sxs-lookup"><span data-stu-id="289dd-200">Watching enrollment</span></span>
<span data-ttu-id="289dd-201">セットアップが完了すると、Mobile Threat Defense は Azure AD のポーリングを開始し、指定された登録グループに対応するデバイスを探します。</span><span class="sxs-lookup"><span data-stu-id="289dd-201">Once the setup is complete, Lookout Mobile Threat Defense starts to poll Azure AD for devices that correspond to the specified enrollment groups.</span></span>  <span data-ttu-id="289dd-202">登録されたデバイスに関する情報は、「Devices」 (デバイス) モジュールで確認できます。</span><span class="sxs-lookup"><span data-stu-id="289dd-202">You can find information about the devices enrolled on the Devices module.</span></span>  <span data-ttu-id="289dd-203">デバイスの初期状態は保留中と表示されます。</span><span class="sxs-lookup"><span data-stu-id="289dd-203">The initial status for devices is shown as pending.</span></span>  <span data-ttu-id="289dd-204">Lookout for Work アプリがデバイスでインストールされたり、オープンになったり、アクティブ化されたりすると、デバイスの状態が変わります。</span><span class="sxs-lookup"><span data-stu-id="289dd-204">The device status changes once the Lookout for Work app is installed, opened, and activated on the device.</span></span>  <span data-ttu-id="289dd-205">Lookout for Work アプリをデバイスにプッシュする方法の詳細については、[「Add Lookout for work apps with Intune」](mtd-apps-ios-app-configuration-policy-add-assign.md) (Intune で Lookout for Work アプリを追加する) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="289dd-205">For details on how to get the Lookout for Work app pushed to the device, see the [Add Lookout for work apps with Intune](mtd-apps-ios-app-configuration-policy-add-assign.md) topic.</span></span>

## <a name="next-steps"></a><span data-ttu-id="289dd-206">次の手順</span><span class="sxs-lookup"><span data-stu-id="289dd-206">Next steps</span></span>

[<span data-ttu-id="289dd-207">Lookout アプリを設定する</span><span class="sxs-lookup"><span data-stu-id="289dd-207">Set up Lookout apps</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)
