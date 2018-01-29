---
title: "iOS アプリ間のデータ転送を管理する"
description: "このトピックを使用すると、iOS の開く機能とモバイル アプリ管理ポリシーを使用してアプリ間のデータ転送を管理する方法を把握できます。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e93ae942a9d207623b084f5008b77accaa68ad00
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="manage-data-transfer-between-ios-apps-with-microsoft-intune"></a><span data-ttu-id="820d5-103">Microsoft Intune を使用して iOS アプリ間のデータ転送を管理する</span><span class="sxs-lookup"><span data-stu-id="820d5-103">Manage data transfer between iOS apps with Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="manage-ios-apps"></a><span data-ttu-id="820d5-104">iOS アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="820d5-104">Manage iOS apps</span></span>
<span data-ttu-id="820d5-105">会社データの保護には、ファイル転送を管理対象のアプリに限定する処理も含まれます。</span><span class="sxs-lookup"><span data-stu-id="820d5-105">Protecting your company data includes making sure that file transfers are restricted to apps that are managed by you.</span></span>  <span data-ttu-id="820d5-106">iOS アプリは次の方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="820d5-106">You can manage iOS apps in the following ways:</span></span>

-   <span data-ttu-id="820d5-107">アプリ (**ポリシーで管理されている**アプリと呼ばれます) のアプリ保護ポリシーを構成して、会社データの損失を回避します。</span><span class="sxs-lookup"><span data-stu-id="820d5-107">Prevent company data loss  by configuring an app protection policy for the apps, which we will refer to as **policy-managed**  apps.</span></span>

-   <span data-ttu-id="820d5-108">また、アプリは **MDM チャネル**から展開して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="820d5-108">You can also deploy and manage apps through the **MDM channel**.</span></span>  <span data-ttu-id="820d5-109">これには、デバイスが MDM ソリューションに登録されていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="820d5-109">This requires that the devices are enrolled in the MDM solution.</span></span> <span data-ttu-id="820d5-110">これらは**ポリシーで管理されている**アプリであるか、またはその他の管理対象アプリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="820d5-110">These can be **policy-managed**  apps or other managed  apps.</span></span>

<span data-ttu-id="820d5-111">iOS デバイスの **Open In Management** 機能を使用すると、**MDM チャネル**を使用して展開されているアプリ間でのみファイル転送が行われるよう制限できます。</span><span class="sxs-lookup"><span data-stu-id="820d5-111">The **Open-in management** feature for iOS devices can limit file transfers between apps that are deployed through the **MDM channel**.</span></span> <span data-ttu-id="820d5-112">Open In Management の制限は、構成設定で設定され、MDM ソリューションを使用して展開されます。</span><span class="sxs-lookup"><span data-stu-id="820d5-112">Open-in management restrictions are set in configuration settings and deployed using your MDM solution.</span></span>  <span data-ttu-id="820d5-113">展開されているアプリをユーザーがインストールすると、管理者が設定した制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="820d5-113">When the user installs the deployed app, the restrictions you set are applied.</span></span>

##  <a name="manage-data-transfer-between-ios-apps"></a><span data-ttu-id="820d5-114">iOS アプリ間のデータ転送を管理する</span><span class="sxs-lookup"><span data-stu-id="820d5-114">Manage data transfer between iOS apps</span></span>
<span data-ttu-id="820d5-115">アプリ保護ポリシーは、iOS の **Open in Management** 機能と共に使用して、以下のように会社データを保護できます。</span><span class="sxs-lookup"><span data-stu-id="820d5-115">App protection policies can be used with the iOS **Open in management** feature to protect company data in the following ways:</span></span>

-   <span data-ttu-id="820d5-116">**MDM ソリューションで管理されていない従業員所有のデバイス:** [アプリ保護ポリシー設定](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)を **[Allow app to transfer data to only managed apps (アプリで管理対象アプリへのデータ転送のみ許可する)]** に設定できます。</span><span class="sxs-lookup"><span data-stu-id="820d5-116">**Employee-owned devices not managed by any MDM solution:** You can set the [app protection policy setting](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) to **Allow app to transfer data to only managed apps**.</span></span> <span data-ttu-id="820d5-117">保護されたファイルをポリシーで管理されていないアプリで開くと、エンドユーザーはファイルを読み取れません。</span><span class="sxs-lookup"><span data-stu-id="820d5-117">When the end user opens a protected file in an app that is not policy-managed, the file is unreadable.</span></span>

-   <span data-ttu-id="820d5-118">**Intune で管理されているデバイス:** Intune で登録したデバイスの場合、アプリ保護ポリシーを使用するアプリと、Intune で展開された管理対象の他の iOS アプリの間で自動的にデータを転送できるようになります。</span><span class="sxs-lookup"><span data-stu-id="820d5-118">**Devices managed by Intune:** For devices enrolled in Intune, data transfer between apps with app protection policies and other managed iOS apps deployed through Intune is allowed automatically.</span></span> <span data-ttu-id="820d5-119">アプリ保護ポリシーを使用するアプリ間でデータを転送できるようにするには、**[Allow app to transfer data to only managed apps (アプリで管理対象アプリへのデータ転送のみ許可する)]** 設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="820d5-119">To allow data transfer between apps with app protection policies, enable the **Allow app to transfer data to only managed apps** setting.</span></span> <span data-ttu-id="820d5-120">**Open in Management** 機能を使用して、Intune で展開されているアプリ間のデータ転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="820d5-120">You can use the **Open in management** feature to control data transfer between apps that are deployed through Intune.</span></span>   

-   <span data-ttu-id="820d5-121">**サード パーティの MDM ソリューションで管理されているデバイス:** iOS の **Open In Management** 機能を使用して、データ転送が管理対象のアプリに対してのみ行われるよう制限できます。</span><span class="sxs-lookup"><span data-stu-id="820d5-121">**Devices managed by a third party MDM solution:** You can restrict data transfer to only managed apps by using the iOS **Open in management** feature.</span></span>
<span data-ttu-id="820d5-122">サードパーティの MDM ソリューションを使用して展開するアプリを、Intune で構成したアプリ保護ポリシーとも関連付けるには、[ユーザー UPN 設定の構成](#configure-user-upn-setting-for-third-party-emm)チュートリアルに従ってユーザー UPN 設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="820d5-122">To make sure that apps that you deploy using your third party MDM solution are also associated with the app protection policies you have configured in Intune, you must configure the user UPN setting as described in the [Configure user UPN setting](#configure-user-upn-setting-for-third-party-emm) walkthrough.</span></span>  <span data-ttu-id="820d5-123">アプリがユーザー UPN 設定を使用して展開されている場合、エンド ユーザーが職場アカウントを使用してサインインすると、アプリ保護ポリシーがアプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="820d5-123">When apps are deployed with the user UPN setting, the app protection policies are applied to the app when the end user signs-in using their work account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="820d5-124">ユーザー UPN 設定は、サード パーティの MDM によって管理されるデバイスに展開されたアプリに対してのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="820d5-124">The user UPN setting is only required for apps deployed to devices managed by a third-party MDM.</span></span>  <span data-ttu-id="820d5-125">Intune の管理対象デバイスの場合は、この設定は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="820d5-125">For Intune-managed devices, this setting is not required.</span></span>

## <a name="configure-user-upn-setting-for-third-party-emm"></a><span data-ttu-id="820d5-126">サードパーティ EMM のユーザー UPN 設定を構成する</span><span class="sxs-lookup"><span data-stu-id="820d5-126">Configure user UPN setting for third-party EMM</span></span>
<span data-ttu-id="820d5-127">ユーザー UPN 設定の構成は、サード パーティの EMM ソリューションによって管理されているデバイスに**必要**となります。</span><span class="sxs-lookup"><span data-stu-id="820d5-127">Configuring the user UPN setting is **required** for devices that are managed by a third-party EMM solution.</span></span> <span data-ttu-id="820d5-128">以下に示す手順では、UPN 設定の一般的な構成方法と、その結果として得られるエンドユーザー エクスペリエンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="820d5-128">The procedure described below is a general flow on how to configure the UPN setting and the resulting end user experience:</span></span>


1. <span data-ttu-id="820d5-129">Azure ポータルで、iOS プラットフォームの[アプリ保護ポリシーを構成します](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="820d5-129">In the Azure portal, [configure an app protection policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) for iOS platform.</span></span> <span data-ttu-id="820d5-130">企業の要件に合わせてポリシー設定を構成し、このポリシーを使用するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="820d5-130">Configure policy settings per your company requirements and select the apps that should have this policy.</span></span>

2. <span data-ttu-id="820d5-131">次の汎用化された手順を使用して、**サードパーティの MDM ソリューションで**管理するアプリとメール プロファイルをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="820d5-131">Deploy the apps and the email profile that you want managed **through your third-party MDM solution** using the generalized steps below.</span></span> <span data-ttu-id="820d5-132">このエクスペリエンスは例 1 でも取り上げています。</span><span class="sxs-lookup"><span data-stu-id="820d5-132">This experience is also covered by Example 1.</span></span>

   1. <span data-ttu-id="820d5-133">次のアプリ構成設定でアプリをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="820d5-133">Deploy the app  with the following app configuration settings:</span></span>

      <span data-ttu-id="820d5-134">**キー** = IntuneMAMUPN、**値** = <username@company.com></span><span class="sxs-lookup"><span data-stu-id="820d5-134">**key** = IntuneMAMUPN,  **value** = <username@company.com></span></span>

      <span data-ttu-id="820d5-135">例: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]</span><span class="sxs-lookup"><span data-stu-id="820d5-135">Example: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]</span></span>

   2. <span data-ttu-id="820d5-136">登録済みデバイスに、サードパーティの MDM プロバイダーを使用して Open in management ポリシーをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="820d5-136">Deploy the Open in management policy using your third-party MDM provider to enrolled devices.</span></span>


### <a name="example-1-admin-experience-in-third-party-mdm-console"></a><span data-ttu-id="820d5-137">例 1: サードパーティ MDM コンソールの管理エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="820d5-137">Example 1: Admin experience in third-party MDM console</span></span>

1. <span data-ttu-id="820d5-138">サードパーティ MDM プロバイダーの管理コンソールに移動します。</span><span class="sxs-lookup"><span data-stu-id="820d5-138">Go to the admin console of your third-party MDM provider.</span></span> <span data-ttu-id="820d5-139">登録済みの iOS デバイスにアプリケーション構成設定をデプロイするコンソールのセクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="820d5-139">Go to the section of the console in which you deploy application configuration settings to enrolled iOS devices.</span></span>

2. <span data-ttu-id="820d5-140">[アプリケーションの構成] セクションで、次の設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="820d5-140">In the Application Configuration section, enter the following setting:</span></span>

   <span data-ttu-id="820d5-141">**キー** = IntuneMAMUPN、**値** = <username@company.com></span><span class="sxs-lookup"><span data-stu-id="820d5-141">**key** = IntuneMAMUPN,  **value** = <username@company.com></span></span>

   <span data-ttu-id="820d5-142">キー/値ペアの正確な構文は、サード パーティ MDM プロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="820d5-142">The exact syntax of the key/value pair may differ based on your third-party MDM provider.</span></span> <span data-ttu-id="820d5-143">次の表は、サードパーティ MDM プロバイダーの例と、キー/値ペアに入力する必要のある正確な値を示します。</span><span class="sxs-lookup"><span data-stu-id="820d5-143">The table below shows examples of third-party MDM providers and the exact values you should enter for the key/value pair.</span></span>

|<span data-ttu-id="820d5-144">サードパーティ MDM プロバイダー</span><span class="sxs-lookup"><span data-stu-id="820d5-144">Third-party MDM provider</span></span>| <span data-ttu-id="820d5-145">Configuration キー</span><span class="sxs-lookup"><span data-stu-id="820d5-145">Configuration Key</span></span> | <span data-ttu-id="820d5-146">値の種類</span><span class="sxs-lookup"><span data-stu-id="820d5-146">Value Type</span></span> | <span data-ttu-id="820d5-147">構成値</span><span class="sxs-lookup"><span data-stu-id="820d5-147">Configuration Value</span></span>|
| ------- | ---- | ---- | ---- |
| <span data-ttu-id="820d5-148">VMware AirWatch</span><span class="sxs-lookup"><span data-stu-id="820d5-148">VMware AirWatch</span></span> | <span data-ttu-id="820d5-149">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="820d5-149">IntuneMAMUPN</span></span> | <span data-ttu-id="820d5-150">文字列型</span><span class="sxs-lookup"><span data-stu-id="820d5-150">String</span></span> | <span data-ttu-id="820d5-151">{UserPrincipalName}</span><span class="sxs-lookup"><span data-stu-id="820d5-151">{UserPrincipalName}</span></span>|
| <span data-ttu-id="820d5-152">MobileIron Core</span><span class="sxs-lookup"><span data-stu-id="820d5-152">MobileIron Core</span></span> | <span data-ttu-id="820d5-153">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="820d5-153">IntuneMAMUPN</span></span> | <span data-ttu-id="820d5-154">文字列型</span><span class="sxs-lookup"><span data-stu-id="820d5-154">String</span></span> | <span data-ttu-id="820d5-155">$EMAIL$  **または**  $USER_UPN$</span><span class="sxs-lookup"><span data-stu-id="820d5-155">$EMAIL$ **or** $USER_UPN$</span></span> |
| <span data-ttu-id="820d5-156">MobileIron Cloud</span><span class="sxs-lookup"><span data-stu-id="820d5-156">MobileIron Cloud</span></span> | <span data-ttu-id="820d5-157">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="820d5-157">IntuneMAMUPN</span></span> | <span data-ttu-id="820d5-158">文字列型</span><span class="sxs-lookup"><span data-stu-id="820d5-158">String</span></span> | <span data-ttu-id="820d5-159">${userUPN} **または** ${userEmailAddress}</span><span class="sxs-lookup"><span data-stu-id="820d5-159">${userUPN} **or** ${userEmailAddress}</span></span> |
| <span data-ttu-id="820d5-160">ManageEngine Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="820d5-160">ManageEngine Mobile Device Manager</span></span> | <span data-ttu-id="820d5-161">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="820d5-161">IntuneMAMUPN</span></span> | <span data-ttu-id="820d5-162">文字列型</span><span class="sxs-lookup"><span data-stu-id="820d5-162">String</span></span> | <span data-ttu-id="820d5-163">%upn%</span><span class="sxs-lookup"><span data-stu-id="820d5-163">%upn%</span></span> |

### <a name="example-2-end-user-experience"></a><span data-ttu-id="820d5-164">例 2: エンドユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="820d5-164">Example 2: End-user experience</span></span>

1.  <span data-ttu-id="820d5-165">エンド ユーザーは、デバイスに Microsoft Word アプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="820d5-165">End user installs Microsoft Word app on the device.</span></span>

2.  <span data-ttu-id="820d5-166">エンド ユーザーが管理対象のネイティブ メール アプリを起動して、自分の電子メールにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="820d5-166">End user launches the managed native email app to access their email.</span></span>

3.  <span data-ttu-id="820d5-167">エンド ユーザーがネイティブ メールから Microsoft Word でドキュメントを開こうとします。</span><span class="sxs-lookup"><span data-stu-id="820d5-167">End user tries to open document from native mail in Microsoft Word.</span></span>

4.  <span data-ttu-id="820d5-168">Word アプリが起動するとき、エンド ユーザーは職場アカウントを使用してログインするよう求められます。</span><span class="sxs-lookup"><span data-stu-id="820d5-168">When the Word app launches, the end user is prompted to log in using their work account.</span></span>  <span data-ttu-id="820d5-169">プロンプトが表示されたときにエンド ユーザーが入力するこの職場アカウントは、Microsoft Word アプリのアプリ構成設定で構成し、指定したアカウントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="820d5-169">This work account the end user enters when prompted should match account you specified in the configured in the app configuration settings for the Microsoft Word app.</span></span>

    > [!NOTE]
    > <span data-ttu-id="820d5-170">エンド ユーザーは、私用で Word アプリを使用するときに、個人の作業に使用し、アプリ保護ポリシーの影響を受けない個人アカウントを Word に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="820d5-170">The end user can add other personal accounts to Word to do their personal work and not be affected by the app protection policies when using the Word app in a personal context.</span></span>

5.  <span data-ttu-id="820d5-171">ログインが成功すると、アプリの保護ポリシー設定が Word アプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="820d5-171">When the login is successful, the app protection policy settings are applied to the Word app.</span></span>

6.  <span data-ttu-id="820d5-172">これでファイル転送が成功し、ドキュメントにはアプリで企業 ID のタグが付けられます。</span><span class="sxs-lookup"><span data-stu-id="820d5-172">Now the file transfer has succeeded and the document is tagged as corporate identity in the app.</span></span> <span data-ttu-id="820d5-173">また、ファイルが作業コンテキスト内で処理されるときには、ポリシー設定が適切に適用されます。</span><span class="sxs-lookup"><span data-stu-id="820d5-173">In addition, the file is treated in a work context and the policy settings are applied accordingly.</span></span>

### <a name="validate-user-upn-setting-for-third-party-emm"></a><span data-ttu-id="820d5-174">サードパーティ EMM のユーザー UPN 設定を検証する</span><span class="sxs-lookup"><span data-stu-id="820d5-174">Validate user UPN setting for third-party EMM</span></span>

<span data-ttu-id="820d5-175">ユーザー UPN 設定を構成した後で、iOS アプリが Intune アプリ保護ポリシーを受信して準拠できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="820d5-175">After configuring the user UPN setting, you should validate the iOS app's ability to receive and comply to Intune app protection policy.</span></span>

<span data-ttu-id="820d5-176">たとえば、**Require app PIN** ポリシー設定はデバイスで簡単に視覚的にテストできます。</span><span class="sxs-lookup"><span data-stu-id="820d5-176">For example, the **Require app PIN** policy setting is easy to visually test on a device.</span></span> <span data-ttu-id="820d5-177">ポリシー設定が **[はい]** に設定されている場合、エンド ユーザーが会社のデータにアクセスしようとしたときに PIN の設定または入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="820d5-177">If the policy setting is set to **Yes**, the end user should see a prompt to set or enter a PIN when attempting to access company data.</span></span>

<span data-ttu-id="820d5-178">まず、[アプリ保護ポリシーを作成し、iOS アプリにデプロイ](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)します。</span><span class="sxs-lookup"><span data-stu-id="820d5-178">First,  [create and deploy an app protection policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) to the iOS app.</span></span> <span data-ttu-id="820d5-179">アプリ保護ポリシーをテストする方法について詳しくは、「[Validate app protection policies](validate-mobile-application-management.md)」(アプリ保護ポリシーの検証) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="820d5-179">See [Validate app protection policies](validate-mobile-application-management.md) for more information on how to test app protection policy.</span></span>



### <a name="see-also"></a><span data-ttu-id="820d5-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="820d5-180">See also</span></span>
[<span data-ttu-id="820d5-181">Microsoft Intune でアプリ保護ポリシーを使用してアプリ データを保護する</span><span class="sxs-lookup"><span data-stu-id="820d5-181">Protect app data using app protection policies with Microsoft Intune</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
