---
title: "設計の作成"
description: "この記事では、Microsoft Intune のクラウド専用の設計と実装の設計を作成する方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: 
ms.openlocfilehash: d30206644f13c6512917075439cf526053ac2051
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="create-a-design"></a><span data-ttu-id="0413f-103">設計の作成</span><span class="sxs-lookup"><span data-stu-id="0413f-103">Create a design</span></span>

<span data-ttu-id="0413f-104">Intune の設計は、[このガイドの他のセクション](planning-guide.md)で収集した情報と行った決定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0413f-104">Your Intune design is based on the information you collect and decisions you make when completing other [sections of this guide](planning-guide.md).</span></span> <span data-ttu-id="0413f-105">次のものを統合するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0413f-105">It helps you bring together:</span></span>

-   <span data-ttu-id="0413f-106">現在の環境</span><span class="sxs-lookup"><span data-stu-id="0413f-106">The current environment</span></span>

-   <span data-ttu-id="0413f-107">Intune の展開オプション</span><span class="sxs-lookup"><span data-stu-id="0413f-107">Intune deployment options</span></span>

-   <span data-ttu-id="0413f-108">外部依存関係に対する ID の要件</span><span class="sxs-lookup"><span data-stu-id="0413f-108">Identity requirements for external dependencies</span></span>

-   <span data-ttu-id="0413f-109">デバイスのプラットフォームに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="0413f-109">Device platform considerations</span></span>

-   <span data-ttu-id="0413f-110">配布する要件</span><span class="sxs-lookup"><span data-stu-id="0413f-110">Requirements to be delivered</span></span>  

<span data-ttu-id="0413f-111">オンプレミスのインフラストラクチャに関する最低限の要件はあるものの、設計計画があれば、目標、目的、および要件に合った適切なモバイル デバイス管理ソリューションを手に入れるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0413f-111">Although there’s minimal on-premises infrastructure requirements, a design plan is still helpful to make sure you have the right mobile device management solution that meets your goals, objectives, and requirements.</span></span>

<span data-ttu-id="0413f-112">これらの各項目について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0413f-112">Let’s review each of these areas in more detail.</span></span> 

## <a name="record-your-current-environment"></a><span data-ttu-id="0413f-113">現在の環境を記録する</span><span class="sxs-lookup"><span data-stu-id="0413f-113">Record your current environment</span></span>
<span data-ttu-id="0413f-114">また、実装とテストのフェーズで設計に変更が発生することはよくあります。</span><span class="sxs-lookup"><span data-stu-id="0413f-114">Additionally, it’s common to have design changes during the implementation and testing phases.</span></span> <span data-ttu-id="0413f-115">設計計画を使用して、そのような変更が発生した場合に変更の内容とその背後にある論理的根拠を文書化します。</span><span class="sxs-lookup"><span data-stu-id="0413f-115">Use your design plan to document these changes and the rationale behind them as they occur.</span></span>

<span data-ttu-id="0413f-116">現在の環境は設計上の決定に影響を与える可能性があるので、文書化し、Intune の設計に関する他の決定を行うときに参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-116">Your current environment can influence design decisions and should be documented and referenced when you make other Intune design decisions.</span></span> <span data-ttu-id="0413f-117">以下は、現在の環境を記録する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="0413f-117">Below are few examples of how to record the current environment:</span></span>

-   <span data-ttu-id="0413f-118">**クラウド内の ID**</span><span class="sxs-lookup"><span data-stu-id="0413f-118">**Identity in the cloud**</span></span>

    -   <span data-ttu-id="0413f-119">DirSync または Azure Active Directory (Azure AD) Connect を使用しているか</span><span class="sxs-lookup"><span data-stu-id="0413f-119">Do you use DirSync or Azure Active Directory (Azure AD) Connect?</span></span>

    -   <span data-ttu-id="0413f-120">環境がフェデレーションされているか</span><span class="sxs-lookup"><span data-stu-id="0413f-120">Is your environment federated?</span></span>

    -   <span data-ttu-id="0413f-121">多要素認証 (MFA) が有効になっているか</span><span class="sxs-lookup"><span data-stu-id="0413f-121">Is multi-factor authentication (MFA) enabled?</span></span>

-   <span data-ttu-id="0413f-122">**メール環境**</span><span class="sxs-lookup"><span data-stu-id="0413f-122">**Email environment**</span></span>

    -   <span data-ttu-id="0413f-123">Exchange を使っているか</span><span class="sxs-lookup"><span data-stu-id="0413f-123">Do you use Exchange?</span></span> <span data-ttu-id="0413f-124">それはオンプレミスか、クラウドか</span><span class="sxs-lookup"><span data-stu-id="0413f-124">Is it on-premises or in the cloud?</span></span>

    -   <span data-ttu-id="0413f-125">Exchange をクラウドに移行するプロジェクトの途中か</span><span class="sxs-lookup"><span data-stu-id="0413f-125">Are you in the middle of a project to migrate Exchange to the cloud?</span></span>

-   <span data-ttu-id="0413f-126">**現在のモバイル デバイス管理 (MDM) ソリューション**</span><span class="sxs-lookup"><span data-stu-id="0413f-126">**Current mobile device management (MDM) solution**</span></span>

    -   <span data-ttu-id="0413f-127">他の MDM ソリューションを現在使っているか</span><span class="sxs-lookup"><span data-stu-id="0413f-127">Are you currently using other MDM solutions?</span></span>

    -   <span data-ttu-id="0413f-128">会社および BYOD のユース ケース シナリオに対してどのような MDM ソリューションを使っているか</span><span class="sxs-lookup"><span data-stu-id="0413f-128">What MDM solutions are you using for corporate and BYOD use-case scenarios?</span></span>

    -   <span data-ttu-id="0413f-129">どのような機能を使っているか (例: アプリ デバイスの設定、Wi-Fi の構成)</span><span class="sxs-lookup"><span data-stu-id="0413f-129">What capabilities are you using (for example: app device settings, Wi-Fi configurations)?</span></span>

    -   <span data-ttu-id="0413f-130">どのようなデバイス プラットフォームがサポートされているか</span><span class="sxs-lookup"><span data-stu-id="0413f-130">What device platforms are supported?</span></span>

    -   <span data-ttu-id="0413f-131">MDM ソリューションを使っているのはどのようなグループで、ユーザー数はどれくらいか</span><span class="sxs-lookup"><span data-stu-id="0413f-131">What groups and how many users are using the MDM solution?</span></span>

-   <span data-ttu-id="0413f-132">**証明書ソリューション**</span><span class="sxs-lookup"><span data-stu-id="0413f-132">**Certificate solution**</span></span>

    -   <span data-ttu-id="0413f-133">証明書ソリューションを導入しているか</span><span class="sxs-lookup"><span data-stu-id="0413f-133">Have you implemented a certificate solution?</span></span>

    -   <span data-ttu-id="0413f-134">使っている証明書の種類</span><span class="sxs-lookup"><span data-stu-id="0413f-134">What type of certificates do you use?</span></span>

-   <span data-ttu-id="0413f-135">**システム管理**</span><span class="sxs-lookup"><span data-stu-id="0413f-135">**Systems management**</span></span>

    -   <span data-ttu-id="0413f-136">PC およびサーバーの環境をどのように管理しているか</span><span class="sxs-lookup"><span data-stu-id="0413f-136">How are you managing your PC and server environment?</span></span>

    -   <span data-ttu-id="0413f-137">System Center Configuration Manager を使っているか</span><span class="sxs-lookup"><span data-stu-id="0413f-137">Are you using System Center Configuration Manager?</span></span> <span data-ttu-id="0413f-138">サードパーティ製のシステム管理プラットフォームを使っているか</span><span class="sxs-lookup"><span data-stu-id="0413f-138">Are you using a third-party system management platform?</span></span>

-   <span data-ttu-id="0413f-139">**VPN ソリューション**</span><span class="sxs-lookup"><span data-stu-id="0413f-139">**VPN solution**</span></span>

    -   <span data-ttu-id="0413f-140">どのような VPN ソリューションを使っているか</span><span class="sxs-lookup"><span data-stu-id="0413f-140">What is your VPN solution?</span></span>

    -   <span data-ttu-id="0413f-141">会社と BYOD の両方のユース ケース シナリオに使っているか</span><span class="sxs-lookup"><span data-stu-id="0413f-141">Do you use it for both corporate and BYOD use-case scenarios?</span></span>

<span data-ttu-id="0413f-142">現在の MDM 環境を記録するときは、環境に影響を与える可能性がある実施中のプロジェクトまたは他の計画に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-142">Make sure to note any projects or any other plans in place that could affect your environment when recording the current MDM environment.</span></span> <span data-ttu-id="0413f-143">Intune の設計を作成するときに現在の環境を記録する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-143">Below is an example of a way to record the current environment when creating your Intune design:</span></span>

| <span data-ttu-id="0413f-144">**ソリューション項目**</span><span class="sxs-lookup"><span data-stu-id="0413f-144">**Solution area**</span></span> | <span data-ttu-id="0413f-145">**現在の環境**</span><span class="sxs-lookup"><span data-stu-id="0413f-145">**Current environment**</span></span> | <span data-ttu-id="0413f-146">**コメント**</span><span class="sxs-lookup"><span data-stu-id="0413f-146">**Comments**</span></span> |
|---|---|---|
| <span data-ttu-id="0413f-147">**ID**</span><span class="sxs-lookup"><span data-stu-id="0413f-147">**Identity**</span></span> | <span data-ttu-id="0413f-148">Azure AD、Azure AD Connect、フェデレーションなし、MFA なし</span><span class="sxs-lookup"><span data-stu-id="0413f-148">Azure AD, Azure AD Connect, not federated, no MFA</span></span> | <span data-ttu-id="0413f-149">年末まで MFA 有効化プロジェクト実施中</span><span class="sxs-lookup"><span data-stu-id="0413f-149">Project in place to enable MFA by end of year</span></span> |                 
| <span data-ttu-id="0413f-150">**メール環境**</span><span class="sxs-lookup"><span data-stu-id="0413f-150">**Email environment**</span></span> | <span data-ttu-id="0413f-151">オンプレミスの Exchange、Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0413f-151">Exchange on-premises, Exchange online</span></span> | <span data-ttu-id="0413f-152">現在、オンプレミスの Exchange から Exchange Online に移行中。</span><span class="sxs-lookup"><span data-stu-id="0413f-152">Currently migrating from Exchange on-premises to Exchange online.</span></span> <span data-ttu-id="0413f-153">メールボックスの 75% を移行済み。</span><span class="sxs-lookup"><span data-stu-id="0413f-153">75% of mailboxes migrated.</span></span> <span data-ttu-id="0413f-154">残りの 25% は、Intune の試験運用が開始する前に移行される。</span><span class="sxs-lookup"><span data-stu-id="0413f-154">Last 25% will be migrated before Intune Pilot begins.</span></span> |                
| <span data-ttu-id="0413f-155">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="0413f-155">**SharePoint**</span></span> | <span data-ttu-id="0413f-156">オンプレミスの SharePoint</span><span class="sxs-lookup"><span data-stu-id="0413f-156">SharePoint on-premises</span></span> | <span data-ttu-id="0413f-157">SharePoint Online への移行計画はなし</span><span class="sxs-lookup"><span data-stu-id="0413f-157">No plans to move to SharePoint online</span></span> |  
| <span data-ttu-id="0413f-158">**現在の MDM**</span><span class="sxs-lookup"><span data-stu-id="0413f-158">**Current MDM**</span></span> | <span data-ttu-id="0413f-159">Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="0413f-159">Exchange ActiveSync</span></span> |  |
| <span data-ttu-id="0413f-160">**証明書ソリューション**</span><span class="sxs-lookup"><span data-stu-id="0413f-160">**Certificate solution**</span></span> | <span data-ttu-id="0413f-161">Microsoft Server 2012 R2、AD 証明書サービス</span><span class="sxs-lookup"><span data-stu-id="0413f-161">Microsoft Server 2012 R2, AD Certificate Services</span></span> | <span data-ttu-id="0413f-162">Web サイト サーバー用に PKI のみを使用</span><span class="sxs-lookup"><span data-stu-id="0413f-162">Only use PKI for Web Site Servers</span></span> |
| <span data-ttu-id="0413f-163">**システム管理**</span><span class="sxs-lookup"><span data-stu-id="0413f-163">**System Management**</span></span> | <span data-ttu-id="0413f-164">System Center Configuration Manager CB 1606</span><span class="sxs-lookup"><span data-stu-id="0413f-164">System Center Configuration Manager CB 1606</span></span> | <span data-ttu-id="0413f-165">Intune ハイブリッド ソリューションの調査を希望</span><span class="sxs-lookup"><span data-stu-id="0413f-165">Would like to investigate Intune hybrid solution</span></span> |
| <span data-ttu-id="0413f-166">**VPN ソリューション**</span><span class="sxs-lookup"><span data-stu-id="0413f-166">**VPN solution**</span></span> | <span data-ttu-id="0413f-167">Cisco AnyConnect</span><span class="sxs-lookup"><span data-stu-id="0413f-167">Cisco AnyConnect</span></span> |  |


<span data-ttu-id="0413f-168">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して Intune 設計計画を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-168">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to develop your Intune design plan.</span></span>

## <a name="choose-an-intune-deployment-option"></a><span data-ttu-id="0413f-169">Intune の展開オプションを選択する</span><span class="sxs-lookup"><span data-stu-id="0413f-169">Choose an Intune deployment option</span></span>

<span data-ttu-id="0413f-170">Intune には、スタンドアロンとハイブリッドの 2 種類の展開オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0413f-170">Intune offers two deployment options: standalone and hybrid.</span></span> <span data-ttu-id="0413f-171">スタンドアロンとはクラウドで実行されている Intune サービスのことであり、ハイブリッドとは Intune と System Center Configuration Manager が統合されたものです。</span><span class="sxs-lookup"><span data-stu-id="0413f-171">Standalone refers to Intune service running in the cloud, hybrid refers to the integration of Intune with System Center Configuration Manager.</span></span> <span data-ttu-id="0413f-172">このガイドは、基本的にスタンドアロン オプション用です。</span><span class="sxs-lookup"><span data-stu-id="0413f-172">This guide is intended primarily for using the standalone option.</span></span> <span data-ttu-id="0413f-173">[どちらのオプションがビジネス要件に合うかを判断する](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)には、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-173">[Decide which option fits your business requirements](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).</span></span>

## <a name="intune-tenant-location"></a><span data-ttu-id="0413f-174">Intune テナントの場所</span><span class="sxs-lookup"><span data-stu-id="0413f-174">Intune tenant location</span></span>

<span data-ttu-id="0413f-175">世界的に展開している組織の場合、サービスに登録するときにテナントが存在する場所を確実に計画してください。</span><span class="sxs-lookup"><span data-stu-id="0413f-175">If your organization has global presence, make sure to plan where your tenant resides when you subscribe to the service.</span></span> <span data-ttu-id="0413f-176">Intune のサブスクリプションに初めてサインアップするときに国を定義し、以下に示す世界中の地域にマップします。</span><span class="sxs-lookup"><span data-stu-id="0413f-176">The country is defined when you sign up for an Intune subscription for the first time, and map to regions around the world, which are listed below:</span></span>

-   <span data-ttu-id="0413f-177">北米</span><span class="sxs-lookup"><span data-stu-id="0413f-177">North America</span></span>

-   <span data-ttu-id="0413f-178">ヨーロッパ、中東、およびアフリカ</span><span class="sxs-lookup"><span data-stu-id="0413f-178">Europe, Middle East, and Africa</span></span>

-   <span data-ttu-id="0413f-179">アジアおよび太平洋</span><span class="sxs-lookup"><span data-stu-id="0413f-179">Asia and Pacific</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0413f-180">国やテナントの場所を後で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0413f-180">It’s not possible to change the country and tenant location later.</span></span>

## <a name="external-dependencies"></a><span data-ttu-id="0413f-181">外部依存関係</span><span class="sxs-lookup"><span data-stu-id="0413f-181">External dependencies</span></span>

<span data-ttu-id="0413f-182">外部依存関係は Intune とは別のサービスや製品ですが、Intune の必要条件であるか、または Intune と統合される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-182">External dependencies are services and products that are separate from Intune, but are either a requirement of Intune, or might integrate with Intune.</span></span> <span data-ttu-id="0413f-183">外部依存関係の要件およびその構成方法を明らかにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="0413f-183">It’s important to identify requirements for any external dependencies and how to configure them.</span></span> <span data-ttu-id="0413f-184">一般的な外部依存関係の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-184">Some examples of common external dependencies are:</span></span>

-   <span data-ttu-id="0413f-185">ID</span><span class="sxs-lookup"><span data-stu-id="0413f-185">Identity</span></span>

-   <span data-ttu-id="0413f-186">ユーザーとデバイス グループ</span><span class="sxs-lookup"><span data-stu-id="0413f-186">User and device groups</span></span>

-   <span data-ttu-id="0413f-187">公開キー基盤 (PKI)</span><span class="sxs-lookup"><span data-stu-id="0413f-187">Public key infrastructure (PKI)</span></span>

<span data-ttu-id="0413f-188">以下ではこれらの一般的な外部依存関係について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0413f-188">Let’s explore in more detail these common external dependencies below</span></span>

### <a name="identity"></a><span data-ttu-id="0413f-189">ID</span><span class="sxs-lookup"><span data-stu-id="0413f-189">Identity</span></span>

<span data-ttu-id="0413f-190">ID は、組織に属している、デバイスに登録されているユーザーを識別する方法です。</span><span class="sxs-lookup"><span data-stu-id="0413f-190">Identity is how we identify the users who belong to your organization and are enrolling a device.</span></span> <span data-ttu-id="0413f-191">Intune では、ユーザー ID プロバイダーとして Azure Active Directory (Azure AD) が必要です。</span><span class="sxs-lookup"><span data-stu-id="0413f-191">Intune requires Azure Active Directory (Azure AD) as the user identity provider.</span></span> <span data-ttu-id="0413f-192">このサービスを既に使っている場合は、クラウドの既存の ID を利用できます。</span><span class="sxs-lookup"><span data-stu-id="0413f-192">If you already use this service, you can use your existing identity already in the cloud.</span></span> <span data-ttu-id="0413f-193">さらに、オンプレミスのユーザー ID を Microsoft クラウド サービスと同期するには、Azure AD Connect が推奨されるツールです。</span><span class="sxs-lookup"><span data-stu-id="0413f-193">In addition, Azure AD Connect is the recommended tool to synchronize your on-premises user identities with Microsoft cloud services.</span></span> <span data-ttu-id="0413f-194">組織が Office 365 を既に使っている場合は、Intune でも同じ Azure AD 環境を使うことが重要です。</span><span class="sxs-lookup"><span data-stu-id="0413f-194">If your organization is already using Office 365, it’s important for Intune to use the same Azure AD environment.</span></span>

<span data-ttu-id="0413f-195">次に示す Intune の ID 要件に関する詳細情報をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-195">Learn more about the following Intune identity requirements:</span></span>

- <span data-ttu-id="0413f-196">[ID の要件](https://docs.microsoft.com/en-us/azure/active-directory/understand-azure-identity-solutions)については、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-196">[Identity requirements](https://docs.microsoft.com/en-us/azure/active-directory/understand-azure-identity-solutions).</span></span>

- <span data-ttu-id="0413f-197">[ディレクトリ同期の要件](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)については、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-197">[Directory synchronization requirements](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span>

- <span data-ttu-id="0413f-198">[多要素認証の要件](https://docs.microsoft.com/en-us/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)については、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-198">[Multi-factor authentication requirements](https://docs.microsoft.com/en-us/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span></span>

### <a name="user-and-device-groups"></a><span data-ttu-id="0413f-199">ユーザーとデバイス グループ</span><span class="sxs-lookup"><span data-stu-id="0413f-199">User and device groups</span></span>

<span data-ttu-id="0413f-200">ユーザー グループとデバイス グループによって、ポリシー、アプリケーション、プロファイルなどを展開する対象が決まります。</span><span class="sxs-lookup"><span data-stu-id="0413f-200">User and device groups determine the target of a deployment, including policies, applications, and profiles.</span></span> <span data-ttu-id="0413f-201">どのようなユーザー グループとデバイス グループが必要になるかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-201">You need to determine what user and device groups will be required.</span></span>

<span data-ttu-id="0413f-202">すべてのグループをオンプレミスの Active Directory 内に作成してから、Azure AD に同期することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0413f-202">We recommend that you create all groups in the on-premises Active Directory, then synchronize to Azure AD.</span></span> <span data-ttu-id="0413f-203">ユーザー グループとデバイス グループの計画と作成については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0413f-203">Learn more about user and device group planning and creation:</span></span>

-   <span data-ttu-id="0413f-204">[ユーザーとデバイス グループを計画する](users-add.md)</span><span class="sxs-lookup"><span data-stu-id="0413f-204">[Plan your user and device groups](users-add.md).</span></span>

-   <span data-ttu-id="0413f-205">[ユーザー グループとデバイス グループを作成する](groups-add.md)</span><span class="sxs-lookup"><span data-stu-id="0413f-205">[Create user and device groups](groups-add.md).</span></span>

### <a name="public-key-infrastructure-pki"></a><span data-ttu-id="0413f-206">公開キー基盤 (PKI)</span><span class="sxs-lookup"><span data-stu-id="0413f-206">Public key infrastructure (PKI)</span></span>
<span data-ttu-id="0413f-207">公開キー基盤は、サービスに対する認証を安全に行うための証明書をデバイスまたはユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="0413f-207">Public key infrastructure supplies certificates to devices or users to securely authenticate to a service.</span></span> <span data-ttu-id="0413f-208">Intune は、Microsoft PKI インフラストラクチャをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0413f-208">Intune supports a Microsoft PKI infrastructure.</span></span> <span data-ttu-id="0413f-209">デバイスとユーザーの証明書をモバイル デバイスに発行し、証明書ベースの認証要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-209">Device and user certificates can be issued to a mobile device to satisfy certificate-based authentication requirements.</span></span> <span data-ttu-id="0413f-210">証明書を使用する前に、証明書が必要かどうか、ネットワーク インフラストラクチャが証明書ベースの認証をサポートできるかどうか、および既存の環境で証明書が現在使用されているかどうかを、確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-210">Before you use certificates, you need to determine if you need them, if the network infrastructure can support certificate-based authentication, and if certificates are currently used in the existing environment.</span></span>

<span data-ttu-id="0413f-211">VPN、Wi-Fi、または Intune での電子メール プロファイルで証明書を使うことを計画している場合は、サポートされる [PKI インフラストラクチャが存在](certificates-configure.md)し、証明書プロファイルを作成して展開する準備ができていることを、確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-211">If you're planning to use certificates with VPN, Wi-Fi, or e-mail profiles with Intune, make sure you have a supported [PKI infrastructure in place](certificates-configure.md), ready to create and deploy certificate profiles.</span></span>

<span data-ttu-id="0413f-212">さらに、SCEP 証明書を発行する場合は、ネットワーク デバイス登録サービス (NDES) 機能をホストするサーバーおよび通信の実行方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-212">In addition, if SCEP certificates will be issued, you need to determine which server will host the Network Device Enrollment Service (NDES) feature, and how the communication will happen.</span></span>

<span data-ttu-id="0413f-213">詳細については、下記のリンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="0413f-213">Learn more about:</span></span>

-   [<span data-ttu-id="0413f-214">Intune 証明書プロファイルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="0413f-214">How to configure Intune certificate profiles</span></span>](certificates-configure.md)

-   <span data-ttu-id="0413f-215">[SCEP 用の証明書インフラストラクチャを構成する方法](certificates-scep-configure.md)についてはこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-215">[How to configure the certificate infrastructure for SCEP](certificates-scep-configure.md)</span></span>

-   [<span data-ttu-id="0413f-216">PFX 用の証明書インフラストラクチャを構成する方法</span><span class="sxs-lookup"><span data-stu-id="0413f-216">How to configure the certificate infrastructure for PFX</span></span>](certficates-pfx-configure.md)




## <a name="device-platform-considerations"></a><span data-ttu-id="0413f-217">デバイスのプラットフォームに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="0413f-217">Device platform considerations</span></span>

<span data-ttu-id="0413f-218">デバイスの次の側面について詳細に検討し、デバイスを正しく管理する方法を理解してください。</span><span class="sxs-lookup"><span data-stu-id="0413f-218">Take a closer look at the following aspects of your devices to understand how to manage them correctly.</span></span>

-   <span data-ttu-id="0413f-219">サポートされるデバイス プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="0413f-219">Supported device platforms</span></span>

-   <span data-ttu-id="0413f-220">[デバイス]</span><span class="sxs-lookup"><span data-stu-id="0413f-220">Devices</span></span>

-   <span data-ttu-id="0413f-221">デバイスの所有権</span><span class="sxs-lookup"><span data-stu-id="0413f-221">Device ownership</span></span>

-   <span data-ttu-id="0413f-222">一括登録</span><span class="sxs-lookup"><span data-stu-id="0413f-222">Bulk enrollment</span></span>

<span data-ttu-id="0413f-223">これらの項目について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0413f-223">Let’s review these areas in more detail.</span></span>

### <a name="determine-supported-device-platforms"></a><span data-ttu-id="0413f-224">サポートされるデバイス プラットフォームの決定</span><span class="sxs-lookup"><span data-stu-id="0413f-224">Determine supported device platforms</span></span>

<span data-ttu-id="0413f-225">環境内に存在するデバイスを把握し、設計を作成するときにデバイスが Intune によってサポートされるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-225">You need to know what devices will be in the environment and verify whether they are supported or not by Intune when creating your design.</span></span> <span data-ttu-id="0413f-226">Intune は、IOS、Android、Windows の各プラットフォームをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0413f-226">Intune supports iOS, Android, and Windows platforms.</span></span>

<span data-ttu-id="0413f-227">[Intune でサポートされているデバイスの完全な一覧](supported-devices-browsers.md)については、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-227">[Complete list of Intune supported devices](supported-devices-browsers.md).</span></span>

### <a name="devices"></a><span data-ttu-id="0413f-228">[デバイス]</span><span class="sxs-lookup"><span data-stu-id="0413f-228">Devices</span></span>

<span data-ttu-id="0413f-229">Intune は、モバイル デバイスを管理して、企業のデータをセキュリティで保護し、エンド ユーザーがより多くの場所から作業できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0413f-229">Intune manages mobile devices to secure corporate data and allow end users to work from more locations.</span></span> <span data-ttu-id="0413f-230">Intune は多数のデバイス プラットフォームをサポートしているので、組織の設計でサポートされるデバイスおよび OS プラットフォームとバージョンを文書化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0413f-230">Intune supports many device platforms, so we recommend that you document the devices and the OS platforms and the versions that will be supported in your organization’s design.</span></span> <span data-ttu-id="0413f-231">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-231">For example:</span></span>

| <span data-ttu-id="0413f-232">**デバイスのプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0413f-232">**Device platform**</span></span> | <span data-ttu-id="0413f-233">**OS のバージョン**</span><span class="sxs-lookup"><span data-stu-id="0413f-233">**OS Versions**</span></span> |
|:---:|:---:|
| <span data-ttu-id="0413f-234">iOS - iPhone</span><span class="sxs-lookup"><span data-stu-id="0413f-234">iOS - iPhone</span></span> | <span data-ttu-id="0413f-235">9.0 以上</span><span class="sxs-lookup"><span data-stu-id="0413f-235">9.0+</span></span> |                
| <span data-ttu-id="0413f-236">iOS - iPad</span><span class="sxs-lookup"><span data-stu-id="0413f-236">iOS - iPad</span></span> | <span data-ttu-id="0413f-237">8.0 以上</span><span class="sxs-lookup"><span data-stu-id="0413f-237">8.0+</span></span> |               
| <span data-ttu-id="0413f-238">Android – Samsung Knox Standard</span><span class="sxs-lookup"><span data-stu-id="0413f-238">Android – Samsung Knox Standard</span></span> | <span data-ttu-id="0413f-239">4.0 以上</span><span class="sxs-lookup"><span data-stu-id="0413f-239">4.0+</span></span> |
| <span data-ttu-id="0413f-240">Windows 10 タブレット</span><span class="sxs-lookup"><span data-stu-id="0413f-240">Windows 10 tablet</span></span> | <span data-ttu-id="0413f-241">10 以上</span><span class="sxs-lookup"><span data-stu-id="0413f-241">10+</span></span> |


<span data-ttu-id="0413f-242">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)してデバイスの一覧を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-242">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to develop your list of devices.</span></span>
### <a name="device-ownership"></a><span data-ttu-id="0413f-243">デバイスの所有権</span><span class="sxs-lookup"><span data-stu-id="0413f-243">Device ownership</span></span>

<span data-ttu-id="0413f-244">Intune は、企業所有のデバイスと個人のデバイスの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0413f-244">Intune supports both corporate-owned devices and personal devices.</span></span> <span data-ttu-id="0413f-245">デバイス登録マネージャーまたは Device Enrollment Program によって登録されるデバイスは企業所有と見なされます。</span><span class="sxs-lookup"><span data-stu-id="0413f-245">A device is considered corporate-owned if your enroll it by a device enrollment manager, or device enrollment program.</span></span> <span data-ttu-id="0413f-246">たとえば、Apple Device Enrollment Program (DEP) でデバイスを登録し、企業所有とマークして、対象を絞った企業ポリシーとアプリを受け取るデバイス グループに配置できます。</span><span class="sxs-lookup"><span data-stu-id="0413f-246">For example, a device is enrolled with the Apple Device Enrollment Program (DEP), marked as corporate, and placed in a device group that receives targeted corporate policies and apps.</span></span>

<span data-ttu-id="0413f-247">企業と BYOD のユース ケースについて詳しくは、「[セクション 3: ユース ケースのシナリオの要件を決定する](planning-guide-requirements.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-247">Refer to [Section 3: Determine use case scenario requirements](planning-guide-requirements.md) for more information about corporate and BYOD use cases.</span></span>

### <a name="bulk-enrollment"></a><span data-ttu-id="0413f-248">一括登録</span><span class="sxs-lookup"><span data-stu-id="0413f-248">Bulk enrollment</span></span>

 <span data-ttu-id="0413f-249">プラットフォームに応じたさまざまな方法でデバイスを一括登録できます。</span><span class="sxs-lookup"><span data-stu-id="0413f-249">You can enroll devices in bulk in different ways depending on the platform.</span></span> <span data-ttu-id="0413f-250">一括登録が必要な場合は、まず[一括登録方法を決定](device-enrollment.md)し、設計に組み込みます。</span><span class="sxs-lookup"><span data-stu-id="0413f-250">If you require bulk enrollment, first [determine the bulk enrollment method](device-enrollment.md) and incorporate it in to your design.</span></span>

## <a name="feature-requirements"></a><span data-ttu-id="0413f-251">機能の要件</span><span class="sxs-lookup"><span data-stu-id="0413f-251">Feature requirements</span></span>

<span data-ttu-id="0413f-252">以下では、ユース ケース シナリオの要件に対応する次の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="0413f-252">In these sections, we review the following features and capabilities that are aligned with your use case scenario requirements:</span></span>

-   <span data-ttu-id="0413f-253">使用条件ポリシー</span><span class="sxs-lookup"><span data-stu-id="0413f-253">Terms and conditions policies</span></span>

-   <span data-ttu-id="0413f-254">構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="0413f-254">Configuration policies</span></span>

-   <span data-ttu-id="0413f-255">リソース プロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-255">Resource profiles</span></span>

-   <span data-ttu-id="0413f-256">アプリ</span><span class="sxs-lookup"><span data-stu-id="0413f-256">Apps</span></span>

-   <span data-ttu-id="0413f-257">コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="0413f-257">Compliance policy</span></span>

-   <span data-ttu-id="0413f-258">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="0413f-258">Conditional access</span></span>

<span data-ttu-id="0413f-259">これらの各項目について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0413f-259">Let’s review each of these areas in more detail.</span></span>

### <a name="terms-and-conditions-policies"></a><span data-ttu-id="0413f-260">使用条件ポリシー</span><span class="sxs-lookup"><span data-stu-id="0413f-260">Terms and conditions policies</span></span>

<span data-ttu-id="0413f-261">[使用条件](terms-and-conditions-create.md)を使って、デバイスを登録する前にエンド ユーザーが受け入れる必要のあるポリシーまたは条件を説明できます。</span><span class="sxs-lookup"><span data-stu-id="0413f-261">You can use [terms and conditions](terms-and-conditions-create.md) to explain policies or conditions that an end user must accept before they can enroll their device.</span></span> <span data-ttu-id="0413f-262">Intune では、複数の使用条件ポリシーをユーザー グループに追加して展開できます。</span><span class="sxs-lookup"><span data-stu-id="0413f-262">Intune supports the ability to add and deploy multiple terms and conditions policies to user groups.</span></span>

<span data-ttu-id="0413f-263">使用条件ポリシーが必要かどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-263">You need to determine if terms and condition policies are needed.</span></span> <span data-ttu-id="0413f-264">必要な場合は、組織でこの情報を提供する責任者を決定します。</span><span class="sxs-lookup"><span data-stu-id="0413f-264">If so, who will be responsible for providing this information in the organization.</span></span> <span data-ttu-id="0413f-265">使用条件ポリシーを文書化する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-265">An example of how to document the terms and conditions policy is below.</span></span>

| <span data-ttu-id="0413f-266">**使用条件名**</span><span class="sxs-lookup"><span data-stu-id="0413f-266">**Terms and Conditions name**</span></span> | <span data-ttu-id="0413f-267">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="0413f-267">**Use case**</span></span> | <span data-ttu-id="0413f-268">**対象グループ**</span><span class="sxs-lookup"><span data-stu-id="0413f-268">**Targeted group**</span></span> |
|:---:|:---:|:---:|
| <span data-ttu-id="0413f-269">Corporate T&C</span><span class="sxs-lookup"><span data-stu-id="0413f-269">Corporate T&C</span></span> | <span data-ttu-id="0413f-270">企業</span><span class="sxs-lookup"><span data-stu-id="0413f-270">Corporate</span></span> | <span data-ttu-id="0413f-271">企業ユーザー</span><span class="sxs-lookup"><span data-stu-id="0413f-271">Corporate users</span></span> |                 
| <span data-ttu-id="0413f-272">BYOD T&C</span><span class="sxs-lookup"><span data-stu-id="0413f-272">BYOD T&C</span></span> | <span data-ttu-id="0413f-273">BYOD</span><span class="sxs-lookup"><span data-stu-id="0413f-273">BYOD</span></span> | <span data-ttu-id="0413f-274">BYOD ユーザー</span><span class="sxs-lookup"><span data-stu-id="0413f-274">BYOD users</span></span> |                


<span data-ttu-id="0413f-275">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、使用条件をユーザー グループにマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-275">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to map your terms and conditions to your user groups.</span></span>

### <a name="configuration-policies"></a><span data-ttu-id="0413f-276">構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="0413f-276">Configuration policies</span></span>

<span data-ttu-id="0413f-277">構成ポリシーを使用して、デバイスのセキュリティ設定と機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="0413f-277">Use configuration policies to manage security settings and features on a device.</span></span> <span data-ttu-id="0413f-278">構成ポリシーを設計するときは、ユース ケース要件セクションを参照して、Intune デバイスに必要な構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="0413f-278">When designing your configuration policies, refer to the use case requirements section to determine the configurations required for Intune devices.</span></span> <span data-ttu-id="0413f-279">設定とその構成方法を文書化します。</span><span class="sxs-lookup"><span data-stu-id="0413f-279">Document the settings and how they should be configured.</span></span> <span data-ttu-id="0413f-280">また、それらの構成がどのユーザー グループまたはデバイス グループを対象とするかも文書化します。</span><span class="sxs-lookup"><span data-stu-id="0413f-280">Also document which user or device groups they will be targeted to.</span></span>

<span data-ttu-id="0413f-281">プラットフォームごとに少なくとも 1 つの構成ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-281">You should create at least one configuration policy per platform.</span></span> <span data-ttu-id="0413f-282">必要な場合は、プラットフォームごとに複数の構成ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0413f-282">You can create several configuration policies per platform if needed.</span></span> <span data-ttu-id="0413f-283">次に示すのは、異なるプラットフォームとユース ケース シナリオに対して 4 つの異なる構成ポリシーを設計する例です。</span><span class="sxs-lookup"><span data-stu-id="0413f-283">Below is an example of designing four different configuration policies for different platforms and use-case scenarios.</span></span>

| <span data-ttu-id="0413f-284">**ポリシー名**</span><span class="sxs-lookup"><span data-stu-id="0413f-284">**Policy name**</span></span> | <span data-ttu-id="0413f-285">**デバイスのプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0413f-285">**Device platform**</span></span> | <span data-ttu-id="0413f-286">**設定**</span><span class="sxs-lookup"><span data-stu-id="0413f-286">**Settings**</span></span> | <span data-ttu-id="0413f-287">**対象グループ**</span><span class="sxs-lookup"><span data-stu-id="0413f-287">**Target group**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0413f-288">企業 - iOS</span><span class="sxs-lookup"><span data-stu-id="0413f-288">Corporate - iOS</span></span> | <span data-ttu-id="0413f-289">iOS</span><span class="sxs-lookup"><span data-stu-id="0413f-289">iOS</span></span> | <span data-ttu-id="0413f-290">PIN 必要、長さ: 6、クラウド バックアップの制限</span><span class="sxs-lookup"><span data-stu-id="0413f-290">PIN is required, Length: 6, Restrict Cloud Backup</span></span> | <span data-ttu-id="0413f-291">企業デバイス</span><span class="sxs-lookup"><span data-stu-id="0413f-291">Corporate Devices</span></span> |                                                           
| <span data-ttu-id="0413f-292">企業 - Android</span><span class="sxs-lookup"><span data-stu-id="0413f-292">Corporate - Android</span></span> | <span data-ttu-id="0413f-293">Android</span><span class="sxs-lookup"><span data-stu-id="0413f-293">Android</span></span> | <span data-ttu-id="0413f-294">PIN 必要、長さ: 6、クラウド バックアップの制限</span><span class="sxs-lookup"><span data-stu-id="0413f-294">PIN is required, Length: 6, Restrict Cloud Backup</span></span> | <span data-ttu-id="0413f-295">企業デバイス</span><span class="sxs-lookup"><span data-stu-id="0413f-295">Corporate Devices</span></span> |                                                           
| <span data-ttu-id="0413f-296">BYOD – iOS</span><span class="sxs-lookup"><span data-stu-id="0413f-296">BYOD – iOS</span></span>  | <span data-ttu-id="0413f-297">iOS</span><span class="sxs-lookup"><span data-stu-id="0413f-297">iOS</span></span> | <span data-ttu-id="0413f-298">PIN 必要、長さ: 4</span><span class="sxs-lookup"><span data-stu-id="0413f-298">PIN is required, Length: 4</span></span> | <span data-ttu-id="0413f-299">BYOD デバイス</span><span class="sxs-lookup"><span data-stu-id="0413f-299">BYOD devices</span></span> |
| <span data-ttu-id="0413f-300">BYOD – Android</span><span class="sxs-lookup"><span data-stu-id="0413f-300">BYOD – Android</span></span>  | <span data-ttu-id="0413f-301">Android</span><span class="sxs-lookup"><span data-stu-id="0413f-301">Android</span></span> | <span data-ttu-id="0413f-302">PIN 必要、長さ: 4</span><span class="sxs-lookup"><span data-stu-id="0413f-302">PIN is required, Length: 4</span></span> | <span data-ttu-id="0413f-303">BYOD デバイス</span><span class="sxs-lookup"><span data-stu-id="0413f-303">BYOD devices</span></span> |


<span data-ttu-id="0413f-304">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、構成ポリシーのニーズを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-304">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to identify your configuration policy needs.</span></span>

### <a name="profiles"></a><span data-ttu-id="0413f-305">Profiles</span><span class="sxs-lookup"><span data-stu-id="0413f-305">Profiles</span></span>

<span data-ttu-id="0413f-306">プロファイルを使用して、エンド ユーザーが会社データに接続するのを補助します。</span><span class="sxs-lookup"><span data-stu-id="0413f-306">Use profiles to help the end user connect to company data.</span></span> <span data-ttu-id="0413f-307">Intune は、さまざまな種類のプロファイルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0413f-307">Intune supports many types of profiles.</span></span> <span data-ttu-id="0413f-308">ユース ケースと要件を参照して、どのような場合にプロファイルを構成するかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0413f-308">Refer to the use cases and requirements to determine when the profiles will be configured.</span></span> <span data-ttu-id="0413f-309">すべてのデバイス プロファイルは、プラットフォームの種類によって分類され、設計ドキュメントに含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-309">All device profiles are categorized by platform type and should be included in the design documentation.</span></span>

-   <span data-ttu-id="0413f-310">証明書プロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-310">Certificate profiles</span></span>

-   <span data-ttu-id="0413f-311">Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-311">Wi-Fi profile</span></span>

-   <span data-ttu-id="0413f-312">VPN プロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-312">VPN profile</span></span>

-   <span data-ttu-id="0413f-313">電子メールのプロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-313">Email profile</span></span>

<span data-ttu-id="0413f-314">プロファイルの各種類についてさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0413f-314">Let’s review each type of profile in more detail.</span></span>

#### <a name="certificate-profiles"></a><span data-ttu-id="0413f-315">証明書プロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-315">Certificate profiles</span></span>

<span data-ttu-id="0413f-316">証明書プロファイルを使って、Intune はユーザーまたはデバイスに証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="0413f-316">Certificate profiles allow Intune to issue a certificate to a user or device.</span></span> <span data-ttu-id="0413f-317">Intune は以下をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0413f-317">Intune supports the following:</span></span>

-   <span data-ttu-id="0413f-318">Simple Certificate Enrollment Protocol (SCEP)</span><span class="sxs-lookup"><span data-stu-id="0413f-318">Simple Certificate Enrollment Protocol (SCEP)</span></span>

-   <span data-ttu-id="0413f-319">信頼されたルート証明書</span><span class="sxs-lookup"><span data-stu-id="0413f-319">Trusted Root Certificate</span></span>

-   <span data-ttu-id="0413f-320">PFX 証明書</span><span class="sxs-lookup"><span data-stu-id="0413f-320">PFX certificate.</span></span>

<span data-ttu-id="0413f-321">証明書が必要なユーザー グループ、必要な証明書プロファイルの数、証明書を展開するユーザー グループを、文書化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0413f-321">We recommend that you document which user group needs a certificate, how many certificate profiles you need, and which user groups to deploy them to.</span></span>

>[!NOTE]
> <span data-ttu-id="0413f-322">SCEP 証明書には信頼されたルート証明書が必要なので、SCEP 証明書の対象となるすべてのユーザーも信頼されたルート証明書を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-322">Remember that the trusted root certificate is required for the SCEP certificate, so make sure all users targeted for the SCEP certificate also receive a trusted root certificate.</span></span> <span data-ttu-id="0413f-323">SCEP 証明書が必要な場合は、必要な SCEP 証明書テンプレートを設計して文書化します。</span><span class="sxs-lookup"><span data-stu-id="0413f-323">If you need SCEP certificates, design and document what SCEP certificate templates you need.</span></span>

<span data-ttu-id="0413f-324">設計時に証明書を文書化する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-324">Here’s an example how you can document the certificates during the design:</span></span>

| <span data-ttu-id="0413f-325">**種類**</span><span class="sxs-lookup"><span data-stu-id="0413f-325">**Type**</span></span> | <span data-ttu-id="0413f-326">**プロファイル名**</span><span class="sxs-lookup"><span data-stu-id="0413f-326">**Profile name**</span></span> | <span data-ttu-id="0413f-327">**デバイスのプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0413f-327">**Device platform**</span></span> | <span data-ttu-id="0413f-328">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="0413f-328">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0413f-329">ルート CA</span><span class="sxs-lookup"><span data-stu-id="0413f-329">Root CA</span></span> | <span data-ttu-id="0413f-330">企業ルート CA</span><span class="sxs-lookup"><span data-stu-id="0413f-330">Corporate Root CA</span></span> | <span data-ttu-id="0413f-331">Android、iOS、Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="0413f-331">Android, iOS, Windows mobile</span></span> | <span data-ttu-id="0413f-332">企業、BYOD</span><span class="sxs-lookup"><span data-stu-id="0413f-332">Corporate, BYOD</span></span>  |                                                           
| <span data-ttu-id="0413f-333">SCEP</span><span class="sxs-lookup"><span data-stu-id="0413f-333">SCEP</span></span> | <span data-ttu-id="0413f-334">ユーザー証明書</span><span class="sxs-lookup"><span data-stu-id="0413f-334">User Certificate</span></span> | <span data-ttu-id="0413f-335">Android、iOS、Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="0413f-335">Android, iOS, Windows mobile</span></span> | <span data-ttu-id="0413f-336">企業、BYOD</span><span class="sxs-lookup"><span data-stu-id="0413f-336">Corporate, BYOD</span></span> |                                                           


<span data-ttu-id="0413f-337">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、証明書プロファイルのニーズを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-337">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to identify your certificate profile needs.</span></span>

#### <a name="wi-fi-profile"></a><span data-ttu-id="0413f-338">Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-338">Wi-Fi profile</span></span>

<span data-ttu-id="0413f-339">Wi-Fi プロファイルは、モバイル デバイスをワイヤレス ネットワークに自動的に接続するために使われます。</span><span class="sxs-lookup"><span data-stu-id="0413f-339">Wi-Fi profiles are used to automatically connect a mobile device to a wireless network.</span></span> <span data-ttu-id="0413f-340">Intune では、サポートされるすべてのプラットフォームに Wi-Fi プロファイルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="0413f-340">Intune supports deploying Wi-Fi profiles to all supported platforms.</span></span> <span data-ttu-id="0413f-341">詳しくは、「[デバイスを構成すると、会社の Wi-Fi ネットワークに接続できます](wi-fi-settings-configure.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-341">Learn more about [how Intune supports Wi-Fi profiles.](wi-fi-settings-configure.md)</span></span>

<span data-ttu-id="0413f-342">Wi-Fi プロファイルの設計の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-342">Below is an example of a design for a Wi-Fi profile:</span></span>

| <span data-ttu-id="0413f-343">**種類**</span><span class="sxs-lookup"><span data-stu-id="0413f-343">**Type**</span></span> | <span data-ttu-id="0413f-344">**プロファイル名**</span><span class="sxs-lookup"><span data-stu-id="0413f-344">**Profile name**</span></span> | <span data-ttu-id="0413f-345">**デバイスのプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0413f-345">**Device platform**</span></span> | <span data-ttu-id="0413f-346">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="0413f-346">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0413f-347">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0413f-347">Wi-Fi</span></span> | <span data-ttu-id="0413f-348">アジア Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-348">Asia Wi-Fi profile</span></span> | <span data-ttu-id="0413f-349">Android</span><span class="sxs-lookup"><span data-stu-id="0413f-349">Android</span></span> | <span data-ttu-id="0413f-350">企業、BYOD アジア地域</span><span class="sxs-lookup"><span data-stu-id="0413f-350">Corporate, BYOD Asia region</span></span>|                                                           
| <span data-ttu-id="0413f-351">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0413f-351">Wi-Fi</span></span> | <span data-ttu-id="0413f-352">北米 Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-352">North America Wi-Fi profile</span></span> | <span data-ttu-id="0413f-353">Android、iOS、Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="0413f-353">Android, iOS, Windows 10 Mobile</span></span> | <span data-ttu-id="0413f-354">企業、BYOD 北米地域</span><span class="sxs-lookup"><span data-stu-id="0413f-354">Corporate, BYOD North America region</span></span> |                                                           


<span data-ttu-id="0413f-355">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、Wi-Fi プロファイルのニーズを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-355">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to identify your Wi-Fi profile needs.</span></span>

#### <a name="vpn-profile"></a><span data-ttu-id="0413f-356">VPN プロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-356">VPN profile</span></span>

<span data-ttu-id="0413f-357">VPN プロファイルを使うと、ユーザーはリモートの場所からネットワークに安全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0413f-357">VPN profiles let users securely access your network from remote locations.</span></span> <span data-ttu-id="0413f-358">Intune は、ネイティブ モバイル VPN 接続およびサード パーティ ベンダーからの VPN プロファイルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0413f-358">Intune supports VPN profiles from native mobile VPN connections and third-party vendors.</span></span> <span data-ttu-id="0413f-359">詳しくは、「[VPN connections in Microsoft Intune](vpn-settings-configure.md)」 (Microsoft Intune での VPN 接続) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-359">Learn more about [VPN profiles and vendors supported by Intune](vpn-settings-configure.md).</span></span>

<span data-ttu-id="0413f-360">VPN プロファイルの設計を文書化する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-360">Below is an example of documenting the design of a VPN profile.</span></span>

| <span data-ttu-id="0413f-361">**種類**</span><span class="sxs-lookup"><span data-stu-id="0413f-361">**Type**</span></span> | <span data-ttu-id="0413f-362">**プロファイル名**</span><span class="sxs-lookup"><span data-stu-id="0413f-362">**Profile name**</span></span> | <span data-ttu-id="0413f-363">**デバイスのプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0413f-363">**Device platform**</span></span> | <span data-ttu-id="0413f-364">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="0413f-364">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0413f-365">VPN</span><span class="sxs-lookup"><span data-stu-id="0413f-365">VPN</span></span> | <span data-ttu-id="0413f-366">VPN Cisco any connect Profile</span><span class="sxs-lookup"><span data-stu-id="0413f-366">VPN Cisco any connect Profile</span></span> | <span data-ttu-id="0413f-367">Android、iOS、Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="0413f-367">Android, iOS, Windows 10 Mobile</span></span> | <span data-ttu-id="0413f-368">企業、BYOD 北米およびドイツ</span><span class="sxs-lookup"><span data-stu-id="0413f-368">Corporate, BYOD North America and Germany</span></span>|                                                           
| <span data-ttu-id="0413f-369">VPN</span><span class="sxs-lookup"><span data-stu-id="0413f-369">VPN</span></span> | <span data-ttu-id="0413f-370">Pulse Secure</span><span class="sxs-lookup"><span data-stu-id="0413f-370">Pulse Secure</span></span> | <span data-ttu-id="0413f-371">Android</span><span class="sxs-lookup"><span data-stu-id="0413f-371">Android</span></span> | <span data-ttu-id="0413f-372">企業、BYOD アジア地域</span><span class="sxs-lookup"><span data-stu-id="0413f-372">Corporate, BYOD Asia region</span></span> |                                                           


<span data-ttu-id="0413f-373">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、VPN プロファイルのニーズを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-373">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to identify your VPN profile needs.</span></span>
#### <a name="email-profile"></a><span data-ttu-id="0413f-374">電子メールのプロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-374">Email profile</span></span>

<span data-ttu-id="0413f-375">電子メール プロファイルを使うと、メール クライアントを接続情報とメール構成で自動的にセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="0413f-375">Email profiles allow an email client to be automatically set up with connection information and email configuration.</span></span> <span data-ttu-id="0413f-376">Intune は、一部のデバイスで電子メール プロファイルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0413f-376">Intune supports email profiles on some devices.</span></span> <span data-ttu-id="0413f-377">[電子メール プロファイルとサポートされるプラットフォーム](email-settings-configure.md)の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0413f-377">Learn more about [email profiles and what platforms are supported](email-settings-configure.md).</span></span>

<span data-ttu-id="0413f-378">電子メール プロファイルの設計を文書化する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-378">Below is an example of documenting the design of email profiles:</span></span>

| <span data-ttu-id="0413f-379">**種類**</span><span class="sxs-lookup"><span data-stu-id="0413f-379">**Type**</span></span> | <span data-ttu-id="0413f-380">**プロファイル名**</span><span class="sxs-lookup"><span data-stu-id="0413f-380">**Profile name**</span></span> | <span data-ttu-id="0413f-381">**デバイスのプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0413f-381">**Device platform**</span></span> | <span data-ttu-id="0413f-382">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="0413f-382">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0413f-383">電子メールのプロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-383">Email profile</span></span> | <span data-ttu-id="0413f-384">iOS email profile</span><span class="sxs-lookup"><span data-stu-id="0413f-384">iOS email profile</span></span> | <span data-ttu-id="0413f-385">iOS</span><span class="sxs-lookup"><span data-stu-id="0413f-385">iOS</span></span> | <span data-ttu-id="0413f-386">企業 – 情報ワーカー BYOD</span><span class="sxs-lookup"><span data-stu-id="0413f-386">Corporate – Information worker BYOD</span></span> |                                                           
| <span data-ttu-id="0413f-387">電子メールのプロファイル</span><span class="sxs-lookup"><span data-stu-id="0413f-387">Email profile</span></span> | <span data-ttu-id="0413f-388">Android Knox email profile</span><span class="sxs-lookup"><span data-stu-id="0413f-388">Android Knox email profile</span></span> | <span data-ttu-id="0413f-389">Android Knox</span><span class="sxs-lookup"><span data-stu-id="0413f-389">Android Knox</span></span> | <span data-ttu-id="0413f-390">BYOD</span><span class="sxs-lookup"><span data-stu-id="0413f-390">BYOD</span></span> |


<span data-ttu-id="0413f-391">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、電子メール プロファイルのニーズを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-391">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to identify your email profile needs.</span></span>
### <a name="apps"></a><span data-ttu-id="0413f-392">アプリ</span><span class="sxs-lookup"><span data-stu-id="0413f-392">Apps</span></span>

<span data-ttu-id="0413f-393">Intune では、複数の方法でユーザーまたはデバイスにアプリを提供できます。</span><span class="sxs-lookup"><span data-stu-id="0413f-393">You can use Intune to deliver apps to the users or devices in several ways.</span></span> <span data-ttu-id="0413f-394">アプリの種類は、ソフトウェア インストーラー アプリ、パブリック アプリ ストアからのアプリ、外部リンク、管理対象 iOS アプリなどです。</span><span class="sxs-lookup"><span data-stu-id="0413f-394">The type of application includes software installer apps, apps from a public app store, external links, or managed iOS apps.</span></span> <span data-ttu-id="0413f-395">個々のアプリの展開だけでなく、iOS および Windows のボリューム購入プログラムを利用して、ボリューム購入アプリを管理および展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="0413f-395">In addition to individual app deployments, you can manage and deploy volume-purchased apps obtained through the volume-purchase programs for iOS and Windows.</span></span> <span data-ttu-id="0413f-396">詳細については、下記のリンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="0413f-396">Learn more about:</span></span>

-   [<span data-ttu-id="0413f-397">提供できるアプリの種類</span><span class="sxs-lookup"><span data-stu-id="0413f-397">The types of apps you can deliver</span></span>](app-management.md)

-   [<span data-ttu-id="0413f-398">ビジネス向け iOS Volume Purchase Program (VPP)</span><span class="sxs-lookup"><span data-stu-id="0413f-398">iOS Volume Purchase Program for Business (VPP)</span></span>](vpp-apps-ios.md)

-   [<span data-ttu-id="0413f-399">ビジネス向け Windows ストアのアプリ</span><span class="sxs-lookup"><span data-stu-id="0413f-399">Windows Store for Business apps</span></span>](windows-store-for-business.md)

#### <a name="app-type-requirements"></a><span data-ttu-id="0413f-400">アプリの種類の要件</span><span class="sxs-lookup"><span data-stu-id="0413f-400">App type requirements</span></span>

<span data-ttu-id="0413f-401">アプリはユーザーとデバイスに展開できるので、どのアプリケーションを Intune で管理するか決めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0413f-401">Since apps can be deployed to users and devices, we recommend that you decide which applications will be managed by Intune.</span></span> <span data-ttu-id="0413f-402">リストを収集するときは、次の点を確認します。</span><span class="sxs-lookup"><span data-stu-id="0413f-402">While gathering the list, try to answer the following questions:</span></span>

-   <span data-ttu-id="0413f-403">アプリは、クラウド サービスとの統合を必要としますか。</span><span class="sxs-lookup"><span data-stu-id="0413f-403">Do the apps require integration with cloud services?</span></span>

-   <span data-ttu-id="0413f-404">すべてのアプリを BYOD 利用可能にしますか。</span><span class="sxs-lookup"><span data-stu-id="0413f-404">Will all apps be available to BYOD users?</span></span>

-   <span data-ttu-id="0413f-405">これらのアプリに使用できる展開オプションにはどのようなものがありますか。</span><span class="sxs-lookup"><span data-stu-id="0413f-405">What are the deployment options available for these apps?</span></span>

-   <span data-ttu-id="0413f-406">会社では、パートナーの SaaS (サービスとしてのソフトウェア) アプリのデータにアクセスできるようにする必要はありますか。</span><span class="sxs-lookup"><span data-stu-id="0413f-406">Does your company need to provide access to Software-as-a-service (SaaS) apps data for their partners?</span></span>

-   <span data-ttu-id="0413f-407">アプリにはユーザーのデバイスからインターネットでアクセスする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="0413f-407">Do the apps require internet access from user’s devices?</span></span>

-   <span data-ttu-id="0413f-408">アプリは、アプリ ストアで一般に利用可能なものですか、またはカスタム基幹業務 (LOB) アプリですか。</span><span class="sxs-lookup"><span data-stu-id="0413f-408">Are the apps publicly available in an app store, or are they custom line-of-business (LOB) apps?</span></span>


#### <a name="app-protection-policies"></a><span data-ttu-id="0413f-409">アプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="0413f-409">App protection policies</span></span>

<span data-ttu-id="0413f-410">アプリ保護ポリシーは、アプリケーションが企業データを管理する方法を定義することによって、データの損失を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="0413f-410">App protection policies minimize data loss by defining how the application manages the corporate data.</span></span> <span data-ttu-id="0413f-411">Intune は、モバイル アプリ管理で機能するように構築された任意のアプリケーションのアプリ保護ポリシーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0413f-411">Intune supports app protection policies for any application built to function with mobile app management.</span></span> <span data-ttu-id="0413f-412">アプリ保護ポリシーを設計するときは、特定のアプリで会社のデータに設ける制限を決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-412">When you design the app protection policy, you need to decide what restrictions you want to place on corporate data in a given app.</span></span> <span data-ttu-id="0413f-413">[アプリ保護ポリシー](app-protection-policy.md)がどのように機能するか確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0413f-413">We recommend that you review how [app protection policies](app-protection-policy.md) work.</span></span> <span data-ttu-id="0413f-414">既存のアプリケーションおよび必要な保護を文書化する方法の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-414">Below is an example of how to document the existing applications and what protection is needed.</span></span>

| <span data-ttu-id="0413f-415">**アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="0413f-415">**Application**</span></span> | <span data-ttu-id="0413f-416">**目的**</span><span class="sxs-lookup"><span data-stu-id="0413f-416">**Purpose**</span></span> | <span data-ttu-id="0413f-417">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0413f-417">**Platforms**</span></span> | <span data-ttu-id="0413f-418">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="0413f-418">**Use case**</span></span> | <span data-ttu-id="0413f-419">**アプリ保護ポリシー**</span><span class="sxs-lookup"><span data-stu-id="0413f-419">**App protection policy**</span></span> |
|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0413f-420">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="0413f-420">Outlook mobile</span></span>  | <span data-ttu-id="0413f-421">利用可能</span><span class="sxs-lookup"><span data-stu-id="0413f-421">Available</span></span> | <span data-ttu-id="0413f-422">iOS</span><span class="sxs-lookup"><span data-stu-id="0413f-422">iOS</span></span> | <span data-ttu-id="0413f-423">企業 - エグゼクティブ</span><span class="sxs-lookup"><span data-stu-id="0413f-423">Corporate - Executives</span></span> | <span data-ttu-id="0413f-424">脱獄不可、ファイルを暗号化</span><span class="sxs-lookup"><span data-stu-id="0413f-424">Cannot be jail broken, encrypt files</span></span> |                                                         
| <span data-ttu-id="0413f-425">Word</span><span class="sxs-lookup"><span data-stu-id="0413f-425">Word</span></span> | <span data-ttu-id="0413f-426">利用可能</span><span class="sxs-lookup"><span data-stu-id="0413f-426">Available</span></span> | <span data-ttu-id="0413f-427">iOS、Android - Samsung Knox、非 Knox、Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="0413f-427">iOS, Android - Samsung Knox, non-Knox, Windows 10 mobile</span></span> | <span data-ttu-id="0413f-428">企業、BYOD</span><span class="sxs-lookup"><span data-stu-id="0413f-428">Corporate, BYOD</span></span> | <span data-ttu-id="0413f-429">脱獄不可、ファイルを暗号化</span><span class="sxs-lookup"><span data-stu-id="0413f-429">Cannot be jail broken, encrypt files</span></span> |                                                         


<span data-ttu-id="0413f-430">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、アプリ保護ポリシーのニーズを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-430">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to identify your app protection policy needs.</span></span>
#### <a name="compliance-policies"></a><span data-ttu-id="0413f-431">Compliance ポリシー</span><span class="sxs-lookup"><span data-stu-id="0413f-431">Compliance policies</span></span>

<span data-ttu-id="0413f-432">コンプライアンス ポリシーは、デバイスが特定の要件に準拠しているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0413f-432">Compliance policies determine whether a device conforms to certain requirements.</span></span> <span data-ttu-id="0413f-433">Intune では、コンプライアンス ポリシーを使って、デバイスが準拠または非準拠のどちらと見なされるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="0413f-433">Intune uses compliance policies to determine if a device is considered compliant or non-compliant.</span></span> <span data-ttu-id="0413f-434">準拠状態は、企業リソースへのアクセスを制限または許可するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="0413f-434">The compliance status can then be used to restrict or allow access to company resources.</span></span> <span data-ttu-id="0413f-435">条件付きアクセスが必要な場合は、[デバイス コンプライアンス ポリシー](device-compliance.md)を設計することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0413f-435">If conditional access is required, we recommend that you design a [device compliance policy](device-compliance.md).</span></span>

<span data-ttu-id="0413f-436">要件とユース ケースを参照し、必要なデバイス コンプライアンス ポリシーの数、および対象となるユーザー グループを決定します。</span><span class="sxs-lookup"><span data-stu-id="0413f-436">Refer to requirements and use cases to determine how many device compliance policies you need and which user groups are the target user groups.</span></span> <span data-ttu-id="0413f-437">さらに、非準拠と見なされる前に、デバイスがチェックインせずにオフラインでいられる時間を決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-437">Additionally, you need to decide how long a device can be offline without checking in before it’s considered non-compliant.</span></span>

<span data-ttu-id="0413f-438">コンプライアンス ポリシーの設計方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-438">Below is an example of how to design a compliance policy:</span></span>

| <span data-ttu-id="0413f-439">**ポリシー名**</span><span class="sxs-lookup"><span data-stu-id="0413f-439">**Policy name**</span></span> | <span data-ttu-id="0413f-440">**デバイスのプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0413f-440">**Device platform**</span></span> | <span data-ttu-id="0413f-441">**設定**</span><span class="sxs-lookup"><span data-stu-id="0413f-441">**Settings**</span></span> | <span data-ttu-id="0413f-442">**対象グループ**</span><span class="sxs-lookup"><span data-stu-id="0413f-442">**Target group**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0413f-443">コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="0413f-443">Compliance policy</span></span> | <span data-ttu-id="0413f-444">iOS、Android - Samsung Knox、非 Knox、Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="0413f-444">iOS, Android - Samsung Knox, non-Knox, Windows 10 mobile</span></span> | <span data-ttu-id="0413f-445">PIN - 必要、脱獄不可</span><span class="sxs-lookup"><span data-stu-id="0413f-445">PIN - required, cannot be jail broken</span></span> | <span data-ttu-id="0413f-446">企業、BYOD</span><span class="sxs-lookup"><span data-stu-id="0413f-446">Corporate, BYOD</span></span> |


<span data-ttu-id="0413f-447">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、コンプライアンス ポリシーのニーズを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-447">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to identify your compliance policy needs.</span></span>
#### <a name="conditional-access-policies"></a><span data-ttu-id="0413f-448">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="0413f-448">Conditional access policies</span></span>

<span data-ttu-id="0413f-449">条件付きアクセスは、準拠デバイスのみに電子メールやその他の企業リソースへのアクセスを許可するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0413f-449">Conditional access is used to allow only compliant devices to access email and other company resources.</span></span> <span data-ttu-id="0413f-450">Intune は、Enterprise Mobility + Security (EMS) と連携して、企業リソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="0413f-450">Intune works with Enterprise Mobility + Security (EMS) to control access to company resources.</span></span> <span data-ttu-id="0413f-451">条件付きアクセスが必要かどうか、および何をセキュリティで保護する必要があるかを、決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0413f-451">You need to decide if conditional access is required and what must be secured.</span></span> <span data-ttu-id="0413f-452">条件付きアクセスの詳細については、[ここ](conditional-access.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0413f-452">Learn more about [conditional access](conditional-access.md).</span></span>

<span data-ttu-id="0413f-453">オンライン アクセスについては、条件付きアクセス ポリシーの対象となるプラットフォームおよびユーザー グループを決めます。</span><span class="sxs-lookup"><span data-stu-id="0413f-453">For online access, decide what platforms, and user groups will be targeted by conditional access policies.</span></span> <span data-ttu-id="0413f-454">また、Exchange Online またはオンプレミスの Exchange 用の Intune サービス間コネクタをインストールして構成する必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="0413f-454">Also, determine whether you need to install or configure the Intune service-to-service connector for Exchange Online or Exchange on-premises.</span></span> <span data-ttu-id="0413f-455">Intune サービス間コネクタをインストールして構成する方法の詳細については、以下をご覧ください。<!---these links are correct---></span><span class="sxs-lookup"><span data-stu-id="0413f-455">Learn more how to install and configure the Intune service-to-service connectors: <!---these links are correct---></span></span>

-   [<span data-ttu-id="0413f-456">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0413f-456">Exchange Online</span></span>](/intune-classic/deploy-use/intune-service-to-service-exchange-connector)

-   [<span data-ttu-id="0413f-457">Exchange On-premises</span><span class="sxs-lookup"><span data-stu-id="0413f-457">Exchange on-premises</span></span>](exchange-connector-install.md)

<span data-ttu-id="0413f-458">条件付きアクセス ポリシーを文書化する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0413f-458">Here’s an example of how to document conditional access policies:</span></span>

| <span data-ttu-id="0413f-459">**サービス**</span><span class="sxs-lookup"><span data-stu-id="0413f-459">**Service**</span></span> | <span data-ttu-id="0413f-460">**先進認証用プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0413f-460">**Platforms for Modern Authentication**</span></span> | <span data-ttu-id="0413f-461">**基本認証**</span><span class="sxs-lookup"><span data-stu-id="0413f-461">**Basic Authentication**</span></span> | <span data-ttu-id="0413f-462">**ユース ケース**</span><span class="sxs-lookup"><span data-stu-id="0413f-462">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0413f-463">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0413f-463">Exchange online</span></span> | <span data-ttu-id="0413f-464">iOS、Android</span><span class="sxs-lookup"><span data-stu-id="0413f-464">iOS, Android</span></span> | <span data-ttu-id="0413f-465">Intune がサポートするプラットフォームの非準拠デバイスをブロックする</span><span class="sxs-lookup"><span data-stu-id="0413f-465">Block non-compliant devices on platforms supported by Intune</span></span> | <span data-ttu-id="0413f-466">企業、BYOD</span><span class="sxs-lookup"><span data-stu-id="0413f-466">Corporate, BYOD</span></span> |
| <span data-ttu-id="0413f-467">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0413f-467">SharePoint online</span></span> | <span data-ttu-id="0413f-468">iOS、Android</span><span class="sxs-lookup"><span data-stu-id="0413f-468">iOS, Android</span></span> |  | <span data-ttu-id="0413f-469">企業、BYOD</span><span class="sxs-lookup"><span data-stu-id="0413f-469">Corporate, BYOD</span></span> |

<span data-ttu-id="0413f-470">[上記の表のテンプレートをダウンロード](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0)して、条件付きアクセス ポリシーのニーズを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0413f-470">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to identify your conditional access policy needs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0413f-471">次の手順</span><span class="sxs-lookup"><span data-stu-id="0413f-471">Next steps</span></span>

<span data-ttu-id="0413f-472">次のセクションでは、[Intune の実装プロセス](planning-guide-onboarding.md)に関するガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0413f-472">The next section provides guidance on the [Intune implementation process](planning-guide-onboarding.md).</span></span>
