---
title: "条件付きアクセスを利用してエンド ユーザーの導入を推進する"
description: "この記事では、条件付きアクセスを利用して Intune 登録を推進する方法を詳しく説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 7a9c3bef955239ad653a9ca45c55c533be36c5ce
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a><span data-ttu-id="f2dcd-103">条件付きアクセスを利用してエンド ユーザーの導入を推進する</span><span class="sxs-lookup"><span data-stu-id="f2dcd-103">Drive end-user adoption with conditional access</span></span>

<span data-ttu-id="f2dcd-104">Intune で条件付きアクセス機能を有効にする (未登録のデバイスの電子メールをブロックするなど) ことにより、登録とコンプライアンスを推進できますが、移行の成功において必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-104">Enabling conditional access features with Intune, such as blocking email for unenrolled devices, can help drive enrollment and compliance but they are not required for a migration to be successful.</span></span> <span data-ttu-id="f2dcd-105">移行の成功は、移行導入の目標とセキュリティ要件によって決まります。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-105">Your migration adoption goals and security requirements should dictate the success.</span></span>

## <a name="migration-campaign-with-conditional-access"></a><span data-ttu-id="f2dcd-106">条件付きアクセスを使用した移行キャンペーン</span><span class="sxs-lookup"><span data-stu-id="f2dcd-106">Migration campaign with conditional access</span></span>

<span data-ttu-id="f2dcd-107">条件付きアクセスを使用して移行キャンペーンを強化するための一般的な方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-107">Here is a typical approach to enhancing a migration campaign with conditional access:</span></span>

1.  <span data-ttu-id="f2dcd-108">以前の MDM プロバイダーからの移行が必要なユーザーを除くすべてのユーザーに対して条件付きアクセス規則が適用されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-108">Set conditional access rules to be enforced for all users but specifically exclude the users who need to migrate from the old MDM provider.</span></span> <span data-ttu-id="f2dcd-109">条件付きアクセスから除外されたすべてのユーザーで構成された、Azure AD ユーザー グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-109">You can create an Azure AD user group with all conditional access excluded users.</span></span>

2.  <span data-ttu-id="f2dcd-110">ユーザーの移行が済んだら、条件付きアクセスから除外されたグループから削除します。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-110">As users migrate, remove them from the conditional access exclusion group.</span></span>

3.  <span data-ttu-id="f2dcd-111">移行が完了したら、Intune がアクセスを許可する場合を除き、既定では条件付きアクセス ポリシーによってアクセスがブロックされるように構成します。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-111">After migration completes, configure all conditional access policies to block by default unless Intune allows access.</span></span>

### <a name="advantages"></a><span data-ttu-id="f2dcd-112">長所</span><span class="sxs-lookup"><span data-stu-id="f2dcd-112">Advantages</span></span>

-   <span data-ttu-id="f2dcd-113">新しいユーザー アカウントや、以前のソリューションで管理されなかったユーザー アカウントに対するアクセス制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-113">Provides access control for new user accounts or user account who were not managed by the previous solution.</span></span>

-   <span data-ttu-id="f2dcd-114">以前のソリューションのユーザーに対して、移行の猶予期間が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-114">Provides grace period for users of previous solution to migration.</span></span>

-   <span data-ttu-id="f2dcd-115">生産性の低下を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-115">Minimizes loss of productivity</span></span>

### <a name="disadvantages"></a><span data-ttu-id="f2dcd-116">短所</span><span class="sxs-lookup"><span data-stu-id="f2dcd-116">Disadvantages</span></span>

-   <span data-ttu-id="f2dcd-117">条件付きアクセスが有効になるまでは、以前のソリューションのユーザーが管理されていないデバイスを使用してリソースにアクセスする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-117">Users of previous solution could potentially access resources using unmanaged devices until conditional access is enabled for those users.</span></span>


<span data-ttu-id="f2dcd-118">数多くの方法のうち 1 つを紹介します。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-118">This is one approach among many.</span></span> <span data-ttu-id="f2dcd-119">すべてのフェーズで登録の指示を行うまでは条件付きアクセスを延期する簡単なプロセスを選択するか、最初から条件付きアクセスを適用して、すべてのアクセスにおいて完全な準拠を要求する厳格なプロセスを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-119">You may choose a simpler process that defers all conditional access until after every phase has been instructed to enroll, or a stricter process that enforces conditional access from the very beginning and requires full compliance for all access.</span></span>

-   <span data-ttu-id="f2dcd-120">条件付きアクセスの詳細については、[ここ](conditional-access.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-120">Learn more about [conditional access](conditional-access.md).</span></span>

## <a name="task-list-for-conditional-access"></a><span data-ttu-id="f2dcd-121">条件付きアクセスのタスク一覧</span><span class="sxs-lookup"><span data-stu-id="f2dcd-121">Task list for conditional access</span></span>

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a><span data-ttu-id="f2dcd-122">タスク 1: 条件付きアクセスを実装する方法の決定</span><span class="sxs-lookup"><span data-stu-id="f2dcd-122">Task 1: Decide how you are going to implement conditional access</span></span>

<span data-ttu-id="f2dcd-123">[条件付きアクセスの一般的な使用方法](conditional-access-intune-common-ways-use.md)。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-123">[Common ways to use conditional access](conditional-access-intune-common-ways-use.md).</span></span>

### <a name="task-2-set-up-intune-conditional-access"></a><span data-ttu-id="f2dcd-124">タスク 2: Intune の条件付きアクセスのセットアップ</span><span class="sxs-lookup"><span data-stu-id="f2dcd-124">Task 2: Set up Intune conditional access</span></span>

<span data-ttu-id="f2dcd-125">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-125">Choose one of the following options:</span></span>

-   [<span data-ttu-id="f2dcd-126">Azure Active Directory の条件付きアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="f2dcd-126">Configure conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [<span data-ttu-id="f2dcd-127">Intune で On-Premises Exchange Connector をインストールする</span><span class="sxs-lookup"><span data-stu-id="f2dcd-127">Install on-premises Exchange connector with Intune</span></span>](exchange-connector-install.md)

-   [<span data-ttu-id="f2dcd-128">Exchange Online のアプリベースの条件付きアクセス ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="f2dcd-128">Set up app-based conditional access policies for Exchange Online</span></span>](app-based-conditional-access-intune-create.md)

-   [<span data-ttu-id="f2dcd-129">SharePoint Online のアプリベースの条件付きアクセス ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="f2dcd-129">Set up app-based conditional access policies for SharePoint Online</span></span>](app-based-conditional-access-intune-create.md)

-   [<span data-ttu-id="f2dcd-130">先進認証 (ADAL) を使用していないアプリをブロックする</span><span class="sxs-lookup"><span data-stu-id="f2dcd-130">Block apps that do not use modern authentication (ADAL)</span></span>](app-modern-authentication-block.md)

## <a name="next-steps"></a><span data-ttu-id="f2dcd-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="f2dcd-131">Next steps</span></span>

<span data-ttu-id="f2dcd-132">[一般的な移行サイクル](migration-guide-cycle.md)について学習します。</span><span class="sxs-lookup"><span data-stu-id="f2dcd-132">Learn about the [typical migration cycle](migration-guide-cycle.md).</span></span>
