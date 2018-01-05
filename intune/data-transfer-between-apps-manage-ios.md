---
title: "iOS アプリ間のデータ転送を管理する"
titlesuffix: Azure portal
description: "このトピックを使用すると、iOS の Open-in 機能とモバイル アプリ管理ポリシーを使用してアプリ間のデータ転送を管理する方法を理解できます。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bbc1ae638b4e18d3b8bf0614da4016e5be1f2cf8
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-manage-data-transfer-between-ios-apps"></a><span data-ttu-id="df605-103">iOS アプリ間のデータ転送を管理する方法</span><span class="sxs-lookup"><span data-stu-id="df605-103">How to manage data transfer between iOS apps</span></span>
## <a name="manage-ios-apps"></a><span data-ttu-id="df605-104">iOS アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="df605-104">Manage iOS apps</span></span>
<span data-ttu-id="df605-105">会社データの保護には、ファイル転送を管理対象のアプリに限定する処理も含まれます。</span><span class="sxs-lookup"><span data-stu-id="df605-105">Protecting your company data includes making sure that file transfers are restricted to apps that are managed by you.</span></span>  <span data-ttu-id="df605-106">iOS アプリは次の方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="df605-106">You can manage iOS apps in the following ways:</span></span>

-   <span data-ttu-id="df605-107">アプリ (**ポリシーで管理されている**アプリと呼ばれます) のアプリ保護ポリシーを構成して、会社データの損失を回避します。</span><span class="sxs-lookup"><span data-stu-id="df605-107">Prevent company data loss  by configuring an app protection policy for the apps, which we will refer to as **policy-managed**  apps.</span></span> <span data-ttu-id="df605-108">[アプリ保護ポリシーで管理できるすべての Intune 対応アプリに関するページ](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df605-108">See [all the Intune-enlightened apps you can manage with app protection policy](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)</span></span>

-   <span data-ttu-id="df605-109">また、アプリは **MDM チャネル**から展開して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="df605-109">You can also deploy and manage apps through the **MDM channel**.</span></span>  <span data-ttu-id="df605-110">これには、デバイスが MDM ソリューションに登録されていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="df605-110">This requires that the devices are enrolled in the MDM solution.</span></span> <span data-ttu-id="df605-111">これらは**ポリシーで管理されている**アプリであるか、またはその他の管理対象アプリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="df605-111">These can be **policy-managed**  apps or other managed  apps.</span></span>

<span data-ttu-id="df605-112">iOS デバイスの **Open In Management** 機能を使用すると、**MDM チャネル**を使用して展開されているアプリ間でのみファイル転送が行われるよう制限できます。</span><span class="sxs-lookup"><span data-stu-id="df605-112">The **Open in management** feature for iOS devices can limit file transfers between apps that are deployed through the **MDM channel**.</span></span> <span data-ttu-id="df605-113">Open In Management の制限は、構成設定で設定され、MDM ソリューションを使用して展開されます。</span><span class="sxs-lookup"><span data-stu-id="df605-113">Open in management restrictions are set in configuration settings and deployed using your MDM solution.</span></span>  <span data-ttu-id="df605-114">展開されているアプリをユーザーがインストールすると、管理者が設定した制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="df605-114">When the user installs the deployed app, the restrictions you set are applied.</span></span>

##  <a name="using-app-protection-with-ios-apps"></a><span data-ttu-id="df605-115">iOS アプリでのアプリ保護の使用</span><span class="sxs-lookup"><span data-stu-id="df605-115">Using app protection with iOS apps</span></span>
<span data-ttu-id="df605-116">アプリ保護ポリシーは、iOS の **Open in Management** 機能と共に使用して、以下のように会社データを保護できます。</span><span class="sxs-lookup"><span data-stu-id="df605-116">App protection policies can be used with the iOS **Open in management** feature to protect company data in the following ways:</span></span>

-   <span data-ttu-id="df605-117">**MDM ソリューションで管理されていない従業員所有のデバイス:** アプリ保護ポリシー設定を **[Allow app to transfer data to only Policy Managed apps]\(アプリでポリシー管理型アプリへのデータ転送のみ許可する\)** に設定できます。</span><span class="sxs-lookup"><span data-stu-id="df605-117">**Employee owned devices not managed by any MDM solution:** You can set the app protection policy settings to **Allow app to transfer data to only Policy Managed apps**.</span></span> <span data-ttu-id="df605-118">ポリシー管理型アプリで Open-In 動作を行うと、その他のポリシー管理型アプリのみが共有対象のオプションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="df605-118">The Open-In behavior in a Policy Managed app will only present other Policy Managed apps as an option for sharing.</span></span> <span data-ttu-id="df605-119">ネイティブ メールで、ユーザーが OneDrive からポリシー保護ファイルを添付ファイルとして送信すると、そのファイルは読み取り不能になります。</span><span class="sxs-lookup"><span data-stu-id="df605-119">If a user tries to send a policy protected file as an attachment from OneDrive in the native mail, that file will be unreadable.</span></span>

-   <span data-ttu-id="df605-120">**Intune で管理されているデバイス:** Intune で登録したデバイスの場合、アプリ保護ポリシーを使用するアプリと、Intune で展開された管理対象の他の iOS アプリの間で自動的にデータを転送できるようになります。</span><span class="sxs-lookup"><span data-stu-id="df605-120">**Devices managed by Intune:** For devices enrolled in Intune, data transfer between apps with app protection policies and other managed iOS apps deployed through Intune is allowed  automatically.</span></span> <span data-ttu-id="df605-121">アプリ保護ポリシーを使用するアプリ間でデータを転送できるようにするには、**[Allow app to transfer data to only managed apps (アプリで管理対象アプリへのデータ転送のみ許可する)]** 設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="df605-121">To allow data transfer between apps with app protection policies, enable the **Allow app to transfer data to only managed apps** setting.</span></span> <span data-ttu-id="df605-122">**Open in Management** 機能を使用して、Intune で展開されているアプリ間のデータ転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="df605-122">You can use the **Open in management** feature to control data transfer between apps that are deployed through Intune.</span></span>   

-   <span data-ttu-id="df605-123">**サード パーティの MDM ソリューションで管理されているデバイス:** iOS の **Open In Management** 機能を使用して、データ転送が管理対象のアプリに対してのみ行われるよう制限できます。</span><span class="sxs-lookup"><span data-stu-id="df605-123">**Devices managed by a third party MDM solution:** You can restrict data transfer to only managed apps by using the iOS **Open in management** feature.</span></span>
<span data-ttu-id="df605-124">サードパーティの MDM ソリューションを使用して展開するアプリを、Intune で構成したアプリ保護ポリシーとも関連付けるには、[ユーザー UPN 設定の構成](#configure-user-upn-setting-for-third-party-emm)チュートリアルに従ってユーザー UPN 設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df605-124">To make sure that apps that you deploy using your third party MDM solution are also associated with the app protection policies you have configured in Intune, you must configure the user UPN setting as described in the [Configure user UPN setting](#configure-user-upn-setting-for-third-party-emm) walkthrough.</span></span>  <span data-ttu-id="df605-125">アプリがユーザー UPN 設定を使用して展開されている場合、エンド ユーザーが職場アカウントを使用してサインインすると、アプリ保護ポリシーがアプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="df605-125">When apps are deployed with the user UPN setting, the app protection policies are applied to the app when the end user signs-in using their work account.</span></span>

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a><span data-ttu-id="df605-126">Microsoft Intune またはサード パーティ EMM のユーザー UPN 設定を構成する</span><span class="sxs-lookup"><span data-stu-id="df605-126">Configure user UPN setting for Microsoft Intune or third-party EMM</span></span>
<span data-ttu-id="df605-127">ユーザー UPN 設定の構成は、Intune またはサード パーティの EMM ソリューションによって管理されているデバイスに**必要**となります。</span><span class="sxs-lookup"><span data-stu-id="df605-127">Configuring the user UPN setting is **required** for devices that are managed by Intune or a third-party EMM solution.</span></span> <span data-ttu-id="df605-128">以下に示す手順では、UPN 設定の一般的な構成方法と、その結果として得られるエンドユーザー エクスペリエンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="df605-128">The procedure described below is a general flow on how to configure the UPN setting and the resulting end user experience:</span></span>

1.  <span data-ttu-id="df605-129">[Azure Portal](https://portal.azure.com) で、iOS 用の[アプリ保護ポリシーを作成して割り当て](app-protection-policies.md)ます。</span><span class="sxs-lookup"><span data-stu-id="df605-129">In the [Azure portal](https://portal.azure.com), [create and assign an app protection policy](app-protection-policies.md) for iOS.</span></span> <span data-ttu-id="df605-130">企業の要件に合わせてポリシー設定を構成し、このポリシーを使う iOS アプリを選びます。</span><span class="sxs-lookup"><span data-stu-id="df605-130">Configure policy settings per your company requirements and select the iOS apps that should have this policy.</span></span>

2.  <span data-ttu-id="df605-131">次の汎用化された手順を使用して、Intune またはサード パーティの MDM ソリューションで管理するアプリとメール プロファイルをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="df605-131">Deploy the apps and the email profile that you want managed through Intune or your third-party MDM solution using the generalized steps below.</span></span> <span data-ttu-id="df605-132">このエクスペリエンスは例 1 でも取り上げています。</span><span class="sxs-lookup"><span data-stu-id="df605-132">This experience is also covered by Example 1.</span></span>

3.  <span data-ttu-id="df605-133">次のアプリ構成設定でアプリをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="df605-133">Deploy the app  with the following app configuration settings:</span></span>

      <span data-ttu-id="df605-134">**キー** = IntuneMAMUPN、**値** = <username@company.com></span><span class="sxs-lookup"><span data-stu-id="df605-134">**key** = IntuneMAMUPN,  **value** = <username@company.com></span></span>

      <span data-ttu-id="df605-135">例: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]</span><span class="sxs-lookup"><span data-stu-id="df605-135">Example: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]</span></span>

4.  <span data-ttu-id="df605-136">登録済みデバイスに、Intune またはサード パーティの MDM プロバイダーを使用して **Open in management** ポリシーをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="df605-136">Deploy the **Open in management** policy using Intune or your third-party MDM provider to enrolled devices.</span></span>


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a><span data-ttu-id="df605-137">例 1: Intune またはサード パーティ MDM コンソールの管理エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="df605-137">Example 1: Admin experience in Intune or third-party MDM console</span></span>

1. <span data-ttu-id="df605-138">Intune またはサード パーティ MDM プロバイダーの管理コンソールに移動します。</span><span class="sxs-lookup"><span data-stu-id="df605-138">Go to the admin console of Intune or your third-party MDM provider.</span></span> <span data-ttu-id="df605-139">登録済みの iOS デバイスにアプリケーション構成設定をデプロイするコンソールのセクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="df605-139">Go to the section of the console in which you deploy application configuration settings to enrolled iOS devices.</span></span>

2. <span data-ttu-id="df605-140">[アプリケーションの構成] セクションで、次の設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="df605-140">In the Application Configuration section, enter the following setting:</span></span>

   <span data-ttu-id="df605-141">**キー** = IntuneMAMUPN、**値** = <username@company.com></span><span class="sxs-lookup"><span data-stu-id="df605-141">**key** = IntuneMAMUPN,  **value** = <username@company.com></span></span>

   <span data-ttu-id="df605-142">キー/値ペアの正確な構文は、サード パーティ MDM プロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="df605-142">The exact syntax of the key/value pair may differ based on your third-party MDM provider.</span></span> <span data-ttu-id="df605-143">次の表は、サードパーティ MDM プロバイダーの例と、キー/値ペアに入力する必要のある正確な値を示します。</span><span class="sxs-lookup"><span data-stu-id="df605-143">The table below shows examples of third-party MDM providers and the exact values you should enter for the key/value pair.</span></span>

|<span data-ttu-id="df605-144">サードパーティ MDM プロバイダー</span><span class="sxs-lookup"><span data-stu-id="df605-144">Third-party MDM provider</span></span>| <span data-ttu-id="df605-145">Configuration キー</span><span class="sxs-lookup"><span data-stu-id="df605-145">Configuration Key</span></span> | <span data-ttu-id="df605-146">値の種類</span><span class="sxs-lookup"><span data-stu-id="df605-146">Value Type</span></span> | <span data-ttu-id="df605-147">構成値</span><span class="sxs-lookup"><span data-stu-id="df605-147">Configuration Value</span></span>|
| ------- | ---- | ---- | ---- |
|<span data-ttu-id="df605-148">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="df605-148">Microsoft Intune</span></span>| <span data-ttu-id="df605-149">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="df605-149">IntuneMAMUPN</span></span> | <span data-ttu-id="df605-150">文字列型</span><span class="sxs-lookup"><span data-stu-id="df605-150">String</span></span> | <span data-ttu-id="df605-151">{UserPrincipalName}</span><span class="sxs-lookup"><span data-stu-id="df605-151">{UserPrincipalName}</span></span>|
|<span data-ttu-id="df605-152">VMware AirWatch</span><span class="sxs-lookup"><span data-stu-id="df605-152">VMware AirWatch</span></span>| <span data-ttu-id="df605-153">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="df605-153">IntuneMAMUPN</span></span> | <span data-ttu-id="df605-154">文字列型</span><span class="sxs-lookup"><span data-stu-id="df605-154">String</span></span> | <span data-ttu-id="df605-155">{UserPrincipalName}</span><span class="sxs-lookup"><span data-stu-id="df605-155">{UserPrincipalName}</span></span>|
|<span data-ttu-id="df605-156">MobileIron</span><span class="sxs-lookup"><span data-stu-id="df605-156">MobileIron</span></span> | <span data-ttu-id="df605-157">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="df605-157">IntuneMAMUPN</span></span> | <span data-ttu-id="df605-158">文字列型</span><span class="sxs-lookup"><span data-stu-id="df605-158">String</span></span> | <span data-ttu-id="df605-159">${userUPN} **または** ${userEmailAddress}</span><span class="sxs-lookup"><span data-stu-id="df605-159">${userUPN} **or** ${userEmailAddress}</span></span> |


### <a name="example-2-end-user-experience"></a><span data-ttu-id="df605-160">例 2: エンドユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="df605-160">Example 2: End-user experience</span></span>

1.  <span data-ttu-id="df605-161">エンド ユーザーは、デバイスに Microsoft Word アプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="df605-161">End user installs Microsoft Word app on the device.</span></span>

2.  <span data-ttu-id="df605-162">エンド ユーザーが管理対象のネイティブ メール アプリを起動して、自分の電子メールにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="df605-162">End user launches the managed native email app to access their email.</span></span>

3.  <span data-ttu-id="df605-163">エンド ユーザーがネイティブ メールから Microsoft Word でドキュメントを開こうとします。</span><span class="sxs-lookup"><span data-stu-id="df605-163">End user tries to open document from native mail in Microsoft Word.</span></span>

4.  <span data-ttu-id="df605-164">Word アプリが起動するとき、エンド ユーザーは職場アカウントを使用してログインするよう求められます。</span><span class="sxs-lookup"><span data-stu-id="df605-164">When the Word app launches, the end user is prompted to log in using their work account.</span></span>  <span data-ttu-id="df605-165">プロンプトが表示されたときにエンド ユーザーが入力するこの職場アカウントは、Microsoft Word アプリのアプリ構成設定で構成し、指定したアカウントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df605-165">This work account the end user enters when prompted should match account you specified in the configured in the app configuration settings for the Microsoft Word app.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df605-166">エンド ユーザーは、私用で Word アプリを使用するときに、個人の作業に使用し、アプリ保護ポリシーの影響を受けない個人アカウントを Word に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="df605-166">The end user can add other personal accounts to Word to do their personal work and not be affected by the app protection policies when using the Word app in a personal context.</span></span>

5.  <span data-ttu-id="df605-167">ログインが成功すると、アプリの保護ポリシー設定が Word アプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="df605-167">When the login is successful, the app protection policy settings are applied to the Word app.</span></span>

6.  <span data-ttu-id="df605-168">これでデータ転送が成功し、ドキュメントにはアプリで企業 ID のタグが付けられます。</span><span class="sxs-lookup"><span data-stu-id="df605-168">Now the data transfer succeeds and the document is tagged with a corporate identity in the app.</span></span> <span data-ttu-id="df605-169">また、データが作業コンテキスト内で処理されるときには、ポリシー設定が適切に適用されます。</span><span class="sxs-lookup"><span data-stu-id="df605-169">In addition, the data is treated in a work context and the policy settings are applied accordingly.</span></span>

### <a name="validate-user-upn-setting-for-third-party-emm"></a><span data-ttu-id="df605-170">サードパーティ EMM のユーザー UPN 設定を検証する</span><span class="sxs-lookup"><span data-stu-id="df605-170">Validate user UPN setting for third-party EMM</span></span>

<span data-ttu-id="df605-171">ユーザー UPN 設定を構成した後で、iOS アプリが Intune アプリ保護ポリシーを受信して準拠できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df605-171">After configuring the user UPN setting, you should validate the iOS app's ability to receive and comply to Intune app protection policy.</span></span>

<span data-ttu-id="df605-172">たとえば、**Require app PIN** ポリシー設定はデバイスで簡単に視覚的にテストできます。</span><span class="sxs-lookup"><span data-stu-id="df605-172">For example, the **Require app PIN** policy setting is easy to visually test on a device.</span></span> <span data-ttu-id="df605-173">ポリシー設定が **[はい]** に設定されている場合、エンド ユーザーが会社のデータにアクセスしようとしたときに PIN の設定または入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df605-173">If the policy setting is set to **Yes**, the end user should see a prompt to set or enter a PIN when attempting to access company data.</span></span>

<span data-ttu-id="df605-174">まず、[アプリ保護ポリシーを作成し、iOS アプリに割り当て](app-protection-policies.md)ます。</span><span class="sxs-lookup"><span data-stu-id="df605-174">First,  [create and assign an app protection policy](app-protection-policies.md) to the iOS app.</span></span> <span data-ttu-id="df605-175">アプリ保護ポリシーをテストする方法について詳しくは、「[アプリ保護ポリシーを確認する](app-protection-policies-validate.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df605-175">See [Validate app protection policies](app-protection-policies-validate.md) for more information on how to test app protection policy.</span></span>


### <a name="see-also"></a><span data-ttu-id="df605-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="df605-176">See also</span></span>
[<span data-ttu-id="df605-177">Intune アプリ保護ポリシーとは</span><span class="sxs-lookup"><span data-stu-id="df605-177">What is Intune app protection policy</span></span>](app-protection-policy.md)
