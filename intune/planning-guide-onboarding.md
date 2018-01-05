---
title: "Intune の導入プロセス"
description: "この記事では、Intune クラウド専用ソリューションを環境に導入するときに考慮するべき事項について詳しく説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6286a0a844cf1d9e665ed29d1eba7fb25876a8e6
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="implement-your-intune-plan"></a><span data-ttu-id="df35c-103">Intune の計画を実装する</span><span class="sxs-lookup"><span data-stu-id="df35c-103">Implement your Intune plan</span></span>

<span data-ttu-id="df35c-104">導入フェーズでは、Intune を運用環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="df35c-104">During the onboarding phase, you deploy Intune into your production environment.</span></span> <span data-ttu-id="df35c-105">この実装プロセスでは、[ユース ケースの要件](planning-guide-requirements.md)に基づいて Intune と外部依存関係 (必要な場合) を設定し、構成します。</span><span class="sxs-lookup"><span data-stu-id="df35c-105">The implementation process consists of setting up and configuring Intune and external dependencies (if required) based on your [use-case requirements](planning-guide-requirements.md).</span></span>

<span data-ttu-id="df35c-106">次のセクションでは、要件や大まかな作業分類など、Intune 実装プロセスの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="df35c-106">The following section provides an overview of the Intune implementation process that includes requirements and high-level tasks.</span></span>

## <a name="intune-requirements"></a><span data-ttu-id="df35c-107">Intune 要件</span><span class="sxs-lookup"><span data-stu-id="df35c-107">Intune requirements</span></span>

<span data-ttu-id="df35c-108">Intune スタンドアロンの主な要件は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="df35c-108">The main Intune standalone requirements are:</span></span>

-   <span data-ttu-id="df35c-109">Enterprise Mobility + Security (EMS)/Intune のサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="df35c-109">Enterprise Mobility + Security (EMS)/Intune subscription</span></span>

-   <span data-ttu-id="df35c-110">Office 365 サブスクリプション (Office アプリとアプリ保護ポリシー管理アプリ用)</span><span class="sxs-lookup"><span data-stu-id="df35c-110">Office 365 subscription (for Office apps and app-protection-policy managed apps)</span></span>

-   <span data-ttu-id="df35c-111">Apple APNs 証明書 (iOS デバイス プラットフォーム管理を有効にします)</span><span class="sxs-lookup"><span data-stu-id="df35c-111">Apple APNs Certificate (to enable iOS device platform management)</span></span>

-   <span data-ttu-id="df35c-112">Azure AD Connect (ディレクトリ同期用)</span><span class="sxs-lookup"><span data-stu-id="df35c-112">Azure AD Connect (for directory synchronization)</span></span>

-   <span data-ttu-id="df35c-113">Intune On-Premises Connector for Exchange (必要な場合、Exchange On-Premises の条件付きアクセス用)</span><span class="sxs-lookup"><span data-stu-id="df35c-113">Intune On-Premises Connector for Exchange (for conditional access for Exchange On-Premises, if needed)</span></span>

-   <span data-ttu-id="df35c-114">Intune Certificate Connector (必要な場合、SCEP 証明書展開用)</span><span class="sxs-lookup"><span data-stu-id="df35c-114">Intune Certificate Connector (for SCEP certificate deployment, if needed)</span></span>

>[!TIP]
> <span data-ttu-id="df35c-115">Intune で管理できるデバイスの完全な一覧については、[サポートされるデバイス](supported-devices-browsers.md)の一覧をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-115">See the list of [supported devices](supported-devices-browsers.md) for a complete list of devices you can manage with Intune.</span></span>

## <a name="intune-implementation-process"></a><span data-ttu-id="df35c-116">Intune 実装プロセス</span><span class="sxs-lookup"><span data-stu-id="df35c-116">Intune implementation process</span></span>

<span data-ttu-id="df35c-117">Intune の展開の実装に関しては、13 の個別タスクが識別されています。</span><span class="sxs-lookup"><span data-stu-id="df35c-117">We've identified 13 discrete tasks for implementing an Intune deployment.</span></span> <span data-ttu-id="df35c-118">ビジネス要件、既存のインフラストラクチャ、およびデバイス管理戦略によっては、一部のタスクは既に完了している場合があります。</span><span class="sxs-lookup"><span data-stu-id="df35c-118">Depending on your business requirements, existing infrastructure, and device management strategy, some of these tasks may already be finished.</span></span> <span data-ttu-id="df35c-119">タスクによっては計画に適用されないものもあります。</span><span class="sxs-lookup"><span data-stu-id="df35c-119">Others may not apply to your plan.</span></span>

### <a name="task-1-get-an-intune-subscription"></a><span data-ttu-id="df35c-120">タスク 1: Intune サブスクリプションを入手する</span><span class="sxs-lookup"><span data-stu-id="df35c-120">Task 1: Get an Intune subscription</span></span>

<span data-ttu-id="df35c-121">前の Intune 要件セクションで示されているように、EMS または Intune のサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="df35c-121">As indicated in the Intune requirements section above, you need an EMS or Intune subscription.</span></span> <span data-ttu-id="df35c-122">組織がどちらも持っていない場合、Microsoft または組織の Microsoft アカウント チームに問い合わせ、Enterprise Mobility + Security (EMS) または Intune の購入に関心があることを伝えてください。</span><span class="sxs-lookup"><span data-stu-id="df35c-122">If your organization does not have one, contact Microsoft or your Microsoft account team regarding your interest in purchasing Enterprise Mobility + Security (EMS) or Intune.</span></span>

-   <span data-ttu-id="df35c-123">Microsoft Intune の購入方法については[こちら](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-123">Learn more about [how to buy Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).</span></span>

### <a name="task-2-add-office-365-subscription"></a><span data-ttu-id="df35c-124">作業 2: Office 365 サブスクリプションを追加する</span><span class="sxs-lookup"><span data-stu-id="df35c-124">Task 2: Add Office 365 subscription</span></span>

<span data-ttu-id="df35c-125">この手順は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="df35c-125">This step is optional.</span></span> <span data-ttu-id="df35c-126">Exchange Online を使い、アプリ保護ポリシーで Office モバイル アプリを管理する予定の場合は、Office 365 のサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="df35c-126">You need an Office 365 subscription if you plan to use Exchange Online and manage Office mobile apps with app protection policies.</span></span> <span data-ttu-id="df35c-127">組織が Office 365 サブスクリプションを持っていない場合、Microsoft または組織の Microsoft アカウント チームに問い合わせ、Office 365 の購入に関心があることを伝えてください。</span><span class="sxs-lookup"><span data-stu-id="df35c-127">If your organization does not have an Office 365 subscription, contact Microsoft or your Microsoft account team regarding your interest in purchasing Office 365.</span></span>

-   <span data-ttu-id="df35c-128">Office 365 の購入方法については[ここ](https://products.office.com/business/compare-office-365-for-business-plans)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-128">Learn more about [how to buy Office 365](https://products.office.com/business/compare-office-365-for-business-plans).</span></span>

### <a name="task-3-add-users-groups-in-azure-ad"></a><span data-ttu-id="df35c-129">作業 3: Azure AD にユーザー グループを追加する</span><span class="sxs-lookup"><span data-stu-id="df35c-129">Task 3: Add users groups in Azure AD</span></span>

<span data-ttu-id="df35c-130">Intune 展開のユース ケース シナリオや要件によっては、Active Directory または Azure Active Directory にユーザーやセキュリティのグループを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df35c-130">You may need to add users or security groups in Active Directory or Azure Active Directory based on your Intune deployment use-case scenarios and requirements.</span></span> <span data-ttu-id="df35c-131">Active Directory または Azure Active Directory で現在のユーザー グループとセキュリティ グループを確認し、ニーズが完全に満たされているかどうか判断します。</span><span class="sxs-lookup"><span data-stu-id="df35c-131">Review your current users and security groups in Active Directory or Azure Active Directory and determine if they fully meet your needs.</span></span> <span data-ttu-id="df35c-132">新しいユーザーとセキュリティ グループを追加するときは、Active Directory で追加し、Azure AD Connect を使って Azure Active Directory と同期することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df35c-132">When adding new users and security groups, we recommend adding them in Active Directory and synchronizing with Azure Active Directory using Azure AD Connect.</span></span>


- <span data-ttu-id="df35c-133">Intune にユーザーまたはグループを追加する方法については、[ここ](users-permissions-add.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-133">Learn more about [how to add users/groups in Intune](users-permissions-add.md).</span></span>
  <!---why not send them to the AAD connect topic? Question out to Andre: https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect--->



### <a name="task-4-assign-intune-and-office-365-user-licenses"></a><span data-ttu-id="df35c-134">作業 4: Intune と Office 365 のユーザー ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="df35c-134">Task 4: Assign Intune and Office 365 user licenses</span></span>

<span data-ttu-id="df35c-135">EMS/Intune や Office 365 の展開の対象になるすべてのユーザーに、ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="df35c-135">All users you target for EMS/Intune and Office 365 rollout need to have a license assigned to them.</span></span> <span data-ttu-id="df35c-136">EMS/Intune と Office 365 のライセンスの割り当ては、Office 365 管理センター ポータルで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="df35c-136">You can assign EMS/Intune and Office 365 licenses in the Office 365 Admin Center Portal.</span></span>

-   <span data-ttu-id="df35c-137">Intune ライセンスの割り当て方法については[ここ](licenses-assign.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-137">Learn more about [how to assign Intune licenses](licenses-assign.md).</span></span>

### <a name="task-5-set-mobile-device-management-authority-to-intune"></a><span data-ttu-id="df35c-138">作業 5: モバイル デバイス管理機関を Intune に設定する</span><span class="sxs-lookup"><span data-stu-id="df35c-138">Task 5: Set mobile device management authority to Intune</span></span>

<span data-ttu-id="df35c-139">Intune でデバイスの設定、構成、管理、登録を始める前に、デバイス管理機関を Intune に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df35c-139">Before you can begin to set up, configure, manage and enroll devices using Intune, you must set the device management authority to Intune.</span></span>

-   <span data-ttu-id="df35c-140">詳しくは、[モバイル デバイス管理機関を設定する方法](mdm-authority-set.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-140">Learn more about [how to set the device management authority](mdm-authority-set.md).</span></span>

### <a name="task-6-enable-device-platforms"></a><span data-ttu-id="df35c-141">タスク 6: デバイス プラットフォームを有効にする</span><span class="sxs-lookup"><span data-stu-id="df35c-141">Task 6: Enable device platforms</span></span>

<span data-ttu-id="df35c-142">既定では、Apple デバイス (iOS と Mac) を除く、ほとんどのデバイス プラットフォームが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="df35c-142">By default, most device platforms are enabled except for Apple devices (iOS and Mac).</span></span> <span data-ttu-id="df35c-143">iOS デバイスを Intune で登録し、管理するには、デバイス プラットフォームを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df35c-143">Before iOS devices can be enrolled and managed in Intune, the device platform must be enabled.</span></span> <span data-ttu-id="df35c-144">そのためには、MDM プッシュ証明書を作成し、Intune に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df35c-144">To do so, you need to create an MDM Push certificate, and add it to Intune.</span></span>

-   <span data-ttu-id="df35c-145">詳しくは、[Apple デバイスの登録を有効にする方法](apple-mdm-push-certificate-get.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-145">Learn more about [how to enable Apple devices for enrollment](apple-mdm-push-certificate-get.md).</span></span>

### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a><span data-ttu-id="df35c-146">作業 7: 使用条件ポリシーを追加し、展開する</span><span class="sxs-lookup"><span data-stu-id="df35c-146">Task 7: Add and deploy terms and conditions policies</span></span>

<span data-ttu-id="df35c-147">Intune は使用条件ポリシーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="df35c-147">Intune supports terms and conditions policies.</span></span> <span data-ttu-id="df35c-148">Intune 展開のユース ケースと要件に基づき、使用条件ポリシーを適宜追加し、対象グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="df35c-148">Add terms and conditions policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="df35c-149">使用条件ポリシーの追加と展開方法の詳細については、[ここ](terms-and-conditions-create.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-149">Learn more about [how to add and deploy terms and condition policies](terms-and-conditions-create.md).</span></span>

### <a name="task-8-add-and-deploy-configuration-policies"></a><span data-ttu-id="df35c-150">作業 8: 構成ポリシーを追加し、展開する</span><span class="sxs-lookup"><span data-stu-id="df35c-150">Task 8: Add and deploy configuration policies</span></span>

<span data-ttu-id="df35c-151">Intune では、標準とカスタムの 2 種類の構成ポリシーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="df35c-151">Intune supports two types of configuration policies, general and custom.</span></span> <span data-ttu-id="df35c-152">Intune 展開のユース ケースと要件に基づき、構成ポリシーを適宜追加し、対象グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="df35c-152">Add the configuration policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="df35c-153">構成ポリシーの追加と展開方法の詳細については、[ここ](device-profiles.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-153">Learn more about [how to add and deploy configuration policies](device-profiles.md).</span></span>

### <a name="task-9-add-and-deploy-resource-profiles"></a><span data-ttu-id="df35c-154">作業 9: リソース プロファイルを追加し、展開する</span><span class="sxs-lookup"><span data-stu-id="df35c-154">Task 9: Add and deploy resource profiles</span></span>

<span data-ttu-id="df35c-155">Intune は、メール、Wi-Fi、VPN のプロファイルに対応しています。</span><span class="sxs-lookup"><span data-stu-id="df35c-155">Intune supports email, Wi-Fi, and VPN profiles.</span></span> <span data-ttu-id="df35c-156">Intune 展開のユース ケースと要件に基づき、プロファイルを適宜追加し、対象グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="df35c-156">Add these profiles as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="df35c-157">詳しくは、[Intune で会社のリソースへのアクセスを有効にする方法](device-profiles.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-157">Learn more about [how to enable access to company resources with Intune](device-profiles.md).</span></span>

### <a name="task-10-add-and-deploy-apps"></a><span data-ttu-id="df35c-158">作業 10: アプリを追加して展開する</span><span class="sxs-lookup"><span data-stu-id="df35c-158">Task 10: Add and deploy apps</span></span>

<span data-ttu-id="df35c-159">Intune は、Web アプリ、基幹業務アプリ、パブリック ストア アプリの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="df35c-159">Intune supports the deployment of web, line-of-business, and public Store apps.</span></span> <span data-ttu-id="df35c-160">また、アプリ保護ポリシーと関連付けることで、Intune SDK を統合しているアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="df35c-160">You can also manage apps that have integrated the Intune SDK by associating them with app protection policies.</span></span> <span data-ttu-id="df35c-161">Intune 展開のユース ケースと要件に基づき、アプリを適宜追加し、対象グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="df35c-161">Add apps as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="df35c-162">詳しくは、[アプリの追加と展開](app-management.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-162">Learn more about [adding and deploying apps](app-management.md).</span></span>

### <a name="task-11-add-and-deploy-compliance-policies"></a><span data-ttu-id="df35c-163">作業 11: コンプライアンス ポリシーを追加し、展開する</span><span class="sxs-lookup"><span data-stu-id="df35c-163">Task 11: Add and deploy compliance policies</span></span>

<span data-ttu-id="df35c-164">Intune はコンプライアンス ポリシーに対応しています。</span><span class="sxs-lookup"><span data-stu-id="df35c-164">Intune supports compliance policies.</span></span> <span data-ttu-id="df35c-165">Intune 展開のユース ケースと要件に基づき、コンプライアンス ポリシーを適宜追加し、対象グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="df35c-165">Add compliance policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="df35c-166">コンプライアンス ポリシーの詳細については、[ここ](device-compliance.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-166">Learn more about [compliance policies](device-compliance.md).</span></span>

### <a name="task-12-enable-conditional-access-policies"></a><span data-ttu-id="df35c-167">作業 12: 条件付きアクセス ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="df35c-167">Task 12: Enable conditional access policies</span></span>

<span data-ttu-id="df35c-168">Intune は、Exchange Online、Exchange オンプレミス、SharePoint Online、Skype for Business Online、Dynamics CRM Online の条件付きアクセスに対応しています。</span><span class="sxs-lookup"><span data-stu-id="df35c-168">Intune supports conditional access for Exchange Online, Exchange on-premises, SharePoint Online, Skype for Business Online, and Dynamics CRM Online.</span></span> <span data-ttu-id="df35c-169">Intune 展開のユース ケースと要件に基づき、条件付きアクセスを有効にして構成します。</span><span class="sxs-lookup"><span data-stu-id="df35c-169">Enable and configure conditional access as appropriate based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="df35c-170">条件付きアクセスの詳細については、[ここ](conditional-access.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-170">Learn more about [conditional access](conditional-access.md).</span></span>

### <a name="task-13-enroll-devices"></a><span data-ttu-id="df35c-171">作業 13: デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="df35c-171">Task 13: Enroll devices</span></span>

<span data-ttu-id="df35c-172">Intune は、iOS、Mac OS、Android、Windows デスクトップ、Windows モバイル デバイス プラットフォームに対応しています。</span><span class="sxs-lookup"><span data-stu-id="df35c-172">Intune supports iOS, Mac OS, Android, Windows desktop, and Windows mobile device platforms.</span></span> <span data-ttu-id="df35c-173">Intune 展開のユース ケースと要件に基づき、モバイル デバイス プラットフォームを適宜登録します。</span><span class="sxs-lookup"><span data-stu-id="df35c-173">Enroll mobile device platforms as appropriate based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="df35c-174">デバイスの登録方法については[ここ](device-enrollment.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-174">Learn more about [how to enroll devices](device-enrollment.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="df35c-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="df35c-175">Next steps</span></span>

<span data-ttu-id="df35c-176">Intune 実装プロセスの詳細については、この [Microsoft Virtual Academy Intune セッション モジュール](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-176">Check out this [Microsoft Virtual Academy Intune session module](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408) for more information on the Intune implementation process.</span></span>


<span data-ttu-id="df35c-177">[Intune 展開のテストと検証](planning-guide-test-validation.md)に関するガイダンスをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df35c-177">See guidance on [testing and validating your Intune deployment](planning-guide-test-validation.md).</span></span>
