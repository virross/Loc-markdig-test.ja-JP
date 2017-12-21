---
title: "Intune の基本的なセットアップ"
description: "この記事では、Microsoft Intune のセットアップに必要な手順について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 9ea12f3707b830f0e3426526a7ae91d176d6e809
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="basic-setup"></a><span data-ttu-id="400d5-103">基本的なセットアップ</span><span class="sxs-lookup"><span data-stu-id="400d5-103">Basic setup</span></span>

<span data-ttu-id="400d5-104">環境を評価した後、Intune をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="400d5-104">After you assess your environment, it’s time to set up Intune.</span></span>

## <a name="external-dependencies-for-an-intune-deployment"></a><span data-ttu-id="400d5-105">Intune の展開に関する外部依存関係</span><span class="sxs-lookup"><span data-stu-id="400d5-105">External dependencies for an Intune deployment</span></span>

### <a name="identity"></a><span data-ttu-id="400d5-106">ID</span><span class="sxs-lookup"><span data-stu-id="400d5-106">Identity</span></span>

<span data-ttu-id="400d5-107">Intune では、ID プロバイダーおよびユーザー グループ化のプロバイダーとして Azure Active Directory (Azure AD) が必要です。</span><span class="sxs-lookup"><span data-stu-id="400d5-107">Intune requires Azure Active Directory (AAD) as the identity and user grouping provider.</span></span> <span data-ttu-id="400d5-108">詳細については、下記のリンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="400d5-108">Learn more about:</span></span>

-  [<span data-ttu-id="400d5-109">ID の要件</span><span class="sxs-lookup"><span data-stu-id="400d5-109">Identity requirements</span></span>](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   [<span data-ttu-id="400d5-110">ディレクトリ同期の要件</span><span class="sxs-lookup"><span data-stu-id="400d5-110">Directory synchronization requirements</span></span>](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   [<span data-ttu-id="400d5-111">多要素認証 (MFA) の要件</span><span class="sxs-lookup"><span data-stu-id="400d5-111">Multi-factor authentication (MFA) requirements</span></span>](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

-   [<span data-ttu-id="400d5-112">ユーザー グループとデバイス グループの計画</span><span class="sxs-lookup"><span data-stu-id="400d5-112">Planning your user and device groups</span></span>](users-add.md)

-   [<span data-ttu-id="400d5-113">ユーザー グループとデバイス グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="400d5-113">How to create user and device groups</span></span>](groups-get-started.md)

<span data-ttu-id="400d5-114">組織が Office 365 を既に使っている場合は、Intune でも同じ Azure Active Directory 環境を使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="400d5-114">If your organization is already using Office 365, Intune must use the same Azure Active Directory environment.</span></span>

### <a name="pki-optional"></a><span data-ttu-id="400d5-115">PKI (省略可能)</span><span class="sxs-lookup"><span data-stu-id="400d5-115">PKI (optional)</span></span>

<span data-ttu-id="400d5-116">VPN、Wi-Fi、または Intune でのメール プロファイルで証明書ベースの認証を使うことを計画している場合は、サポートされる [PKI インフラストラクチャが存在](certificates-configure.md)し、証明書プロファイルを作成して展開する準備ができていることを、確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="400d5-116">If you're planning to use certificate-based authentication for VPN, Wi-Fi, or e-mail profiles with Intune, you’ll need to make sure that you have a supported [PKI infrastructure in place](certificates-configure.md), ready to create and deploy certificate profiles.</span></span> <span data-ttu-id="400d5-117">Intune で証明書を構成する方法の詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="400d5-117">Learn more about configuring certificates in Intune:</span></span>

-   <span data-ttu-id="400d5-118">[SCEP 用の証明書インフラストラクチャを構成する方法](/intune/certificates-scep-configure)についてはこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="400d5-118">[How to configure the certificate infrastructure for SCEP](/intune/certificates-scep-configure)</span></span>

-   <span data-ttu-id="400d5-119">[PFX 用の証明書インフラストラクチャを構成する方法](/intune/certficates-pfx-configure)についてはこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="400d5-119">[How to configure the certificate infrastructure for PFX](/intune/certficates-pfx-configure).</span></span>


## <a name="task-list-for-an-intune-setup"></a><span data-ttu-id="400d5-120">Intune セットアップのタスク一覧</span><span class="sxs-lookup"><span data-stu-id="400d5-120">Task list for an Intune setup</span></span>

### <a name="task-1-intune-subscription"></a><span data-ttu-id="400d5-121">タスク 1: Intune のサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="400d5-121">Task 1: Intune subscription</span></span>

<span data-ttu-id="400d5-122">Intune に移行するには、Intune サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="400d5-122">Before you can migrate to Intune, you first need an Intune subscription.</span></span>

-   <span data-ttu-id="400d5-123">次の手順を説明する、[こちらのページ](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="400d5-123">You can visit [this page](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), which gives you instructions on how to:</span></span>

    -   <span data-ttu-id="400d5-124">新しい AAD テナントにリンクされた新しい Intune サブスクリプションを作成する。</span><span class="sxs-lookup"><span data-stu-id="400d5-124">Create a new Intune subscription linked to a new AAD tenant.</span></span>

    -   <span data-ttu-id="400d5-125">既存の AAD テナントにサインインして、Intune サブスクリプションをリンクする。</span><span class="sxs-lookup"><span data-stu-id="400d5-125">Link the Intune subscription by signing into an existing AAD tenant.</span></span>

### <a name="task-2-assign-intune-user-licenses"></a><span data-ttu-id="400d5-126">タスク 2: Intune ユーザー ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="400d5-126">Task 2: Assign Intune user licenses</span></span>

-   <span data-ttu-id="400d5-127">Intune ユーザー ライセンスを割り当てる方法については、[こちら](licenses-assign.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="400d5-127">Learn [how to assign Intune user licenses](licenses-assign.md).</span></span>

-   <span data-ttu-id="400d5-128">新しい Azure Active Directory テナントを作成した場合は、[新しいユーザーを作成したり、オンプレミスの Active Directory (AD) からユーザーを同期する方法](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="400d5-128">If you have created a new Azure Active Directory tenant, learn [how to create new users or sync user from your on-premises Active Directory (AD).](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span></span>

### <a name="task-3-set-your-mdm-authority-to-intune"></a><span data-ttu-id="400d5-129">タスク 3: MDM 機関を Intune に設定する</span><span class="sxs-lookup"><span data-stu-id="400d5-129">Task 3: Set your MDM authority to Intune</span></span>

<span data-ttu-id="400d5-130">Intune は、Azure Portal や Configuration Manager の Current Branch コンソールから管理できます。</span><span class="sxs-lookup"><span data-stu-id="400d5-130">Intune can be managed through the Azure portal or the Configuration Manager Current Branch console.</span></span> <span data-ttu-id="400d5-131">Configuration Manager の現在のブランチの展開と Intune を統合する必要がある場合を除き、Intune は [Azure Portal](https://portal.azure.com) から管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="400d5-131">Unless you need to integrate Intune with a Configuration Manager Current Branch deployment, we recommend that you manage Intune from the [Azure portal](https://portal.azure.com).</span></span>

<span data-ttu-id="400d5-132">MDM 機関を **Intune** に設定して、Intune Azure Portal を有効にします。</span><span class="sxs-lookup"><span data-stu-id="400d5-132">Set your MDM authority to **Intune** to enable the Intune Azure portal.</span></span> <span data-ttu-id="400d5-133">異なる MDM 機関を使用すると、Intune は代替の Microsoft 管理コンソールに MDM 管理を転送します。</span><span class="sxs-lookup"><span data-stu-id="400d5-133">Using a different MDM authority allows Intune to transfer MDM management to alternate Microsoft management consoles.</span></span> <span data-ttu-id="400d5-134">このようなケースは一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="400d5-134">These cases are uncommon.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="400d5-135">モバイル デバイス管理を Intune に初めて転送する場合は、MDM 機関を Intune に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="400d5-135">If you are transferring your mobile device management to Intune for the first time, you should set the MDM authority to Intune.</span></span>

<span data-ttu-id="400d5-136">モバイル管理機関を設定する方法については、[こちら](mdm-authority-set.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="400d5-136">Learn [how to set the mobile management authority](mdm-authority-set.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="400d5-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="400d5-137">Next step</span></span>

<span data-ttu-id="400d5-138">[デバイスおよびアプリの管理ポリシー](migration-guide-configure-policies.md)を構成します。</span><span class="sxs-lookup"><span data-stu-id="400d5-138">Configure [device and app management policies](migration-guide-configure-policies.md).</span></span>
