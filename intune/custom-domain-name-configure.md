---
title: "カスタムのドメイン名を構成する"
description: "Intune サブスクリプションのカスタム ドメイン名を追加します"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6ddfa40800bcb0d671ea492ea365bf54ad5fb342
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="configure-a-custom-domain-name"></a><span data-ttu-id="eda58-103">カスタムのドメイン名を構成する</span><span class="sxs-lookup"><span data-stu-id="eda58-103">Configure a custom domain name</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="eda58-104">このトピックでは、管理者が DNS CNAME を作成して、ログオン エクスペリエンスの簡略化とカスタマイズを行う方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="eda58-104">This topic tells administrators how they can create a DNS CNAME to simplify and customize their logon experience.</span></span>

<span data-ttu-id="eda58-105">組織が Intune などの Microsoft クラウド ベース サービスにサインアップすると、**your-domain.onmicrosoft.com** のように Azure Active Directory (AD) でホストされる最初のドメイン名が付与されます。この例では、**your-domain** はサインアップ時に選択したドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="eda58-105">When your organization signs up for a Microsoft cloud-based service like Intune, you're given an initial domain name hosted in Azure Active Directory (AD) that looks like **your-domain.onmicrosoft.com**. In this example, **your-domain** is the domain name that you chose when you signed up.</span></span> <span data-ttu-id="eda58-106">**onmicrosoft.com** はサブスクリプションに追加するアカウントに割り当てられるサフィックスです。</span><span class="sxs-lookup"><span data-stu-id="eda58-106">**onmicrosoft.com** is the suffix assigned to the accounts you add to your subscription.</span></span> <span data-ttu-id="eda58-107">サブスクリプションで提供されるドメイン名ではなく、組織のカスタム ドメインを構成して Intune にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eda58-107">You can configure your organization's custom domain to access Intune instead of the domain name provided with your subscription.</span></span>

<span data-ttu-id="eda58-108">ユーザー アカウントを作成する、またはオンプレミスの Active Directory を同期する前に、.onmicrosoft.com ドメインのみを使用するか、1 つ以上のカスタム ドメイン名を追加するかを決定することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eda58-108">Before you create user accounts or synchronize your on-premises Active Directory, we strongly recommend that you decide whether to use only the .onmicrosoft.com domain or to add one or more of your custom domain names.</span></span> <span data-ttu-id="eda58-109">ユーザー管理を簡単にするために、ユーザーを追加する前にカスタム ドメインを設定します。</span><span class="sxs-lookup"><span data-stu-id="eda58-109">Set up a custom domain before adding users to simplify user management.</span></span> <span data-ttu-id="eda58-110">これにより、ユーザーは他のドメイン リソースへのアクセスに使う資格情報でサインインできます。</span><span class="sxs-lookup"><span data-stu-id="eda58-110">This lets users sign in with the credentials they use to access other domain resources.</span></span>

<span data-ttu-id="eda58-111">Microsoft のクラウドベースのサービスにサブスクライブすると、そのサービスのインスタンスが Microsoft [Azure AD テナント](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)になり、Azure AD によって、クラウドベースのサービスの ID サービスとディレクトリ サービスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="eda58-111">When you subscribe to a cloud-based service from Microsoft, your instance of that service becomes a Microsoft  [Azure AD tenant](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), which provides identity and directory services for your cloud-based service.</span></span> <span data-ttu-id="eda58-112">Intune で組織のカスタム ドメイン名の使用を構成するタスクは、他の Azure AD テナントの場合と同じため、[ドメインの追加](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/)に関する記事の情報と手順を利用できます。</span><span class="sxs-lookup"><span data-stu-id="eda58-112">And, because the tasks to configure Intune to use your organizations custom domain name are the same as for other Azure AD tenants, you can use the information and procedures found in [Add your domain](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).</span></span>

> [!TIP]
> <span data-ttu-id="eda58-113">カスタム ドメインについて詳しくは、「[Azure Active Directory でのカスタム ドメイン名の概念の概要](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eda58-113">To learn more about custom domains, see [Conceptual overview of custom domain names in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).</span></span>

<span data-ttu-id="eda58-114">最初のドメイン名 onmicrosoft.com を変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="eda58-114">You cannot rename or remove the initial onmicrosoft.com domain name.</span></span> <span data-ttu-id="eda58-115">ビジネス ID をクリアにするために、Intune で使われるカスタム ドメイン名を追加、確認、削除することはできます。</span><span class="sxs-lookup"><span data-stu-id="eda58-115">You can add, verify or remove custom domain names used with Intune to keep your business identity clear.</span></span>

## <a name="to-add-and-verify-your-custom-domain"></a><span data-ttu-id="eda58-116">カスタム ドメインを追加して確認するには</span><span class="sxs-lookup"><span data-stu-id="eda58-116">To add and verify your custom domain</span></span>

1. <span data-ttu-id="eda58-117">[Office 365 管理ポータル](https://portal.office.com/Admin/Default.aspx)を開き、管理者アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="eda58-117">Go to [Office 365 management portal](https://portal.office.com/Admin/Default.aspx) and sign into your administrator account.</span></span>

2. <span data-ttu-id="eda58-118">ナビゲーション ウィンドウの **[設定]** &gt; **[ドメイン]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eda58-118">In the navigation pane, choose **Settings** &gt; **Domains**.</span></span>

3. <span data-ttu-id="eda58-119">**[ドメインの追加]** を選択し、カスタム ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="eda58-119">Choose **Add domain**, and type your custom domain name.</span></span>
   <span data-ttu-id="eda58-120">![[設定] > [ドメイン] を選択して新しいドメイン名を追加した Office 365 管理センターのスクリーンショット](./media/domain-custom-add.png)</span><span class="sxs-lookup"><span data-stu-id="eda58-120">![Screenshot of Office 365 Admin Center with Settings > Domains selected and a new domain name being added](./media/domain-custom-add.png)</span></span>
4. <span data-ttu-id="eda58-121">**[ドメインの確認]** ダイアログ ボックスが開き、DNS ホスティング プロバイダーに TXT レコードを作成する値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eda58-121">The **Verify domain** dialog box opens giving you the values to create the TXT record in your DNS hosting provider.</span></span>
    - <span data-ttu-id="eda58-122">**GoDaddy ユーザー**: Office 365 管理ポータルから GoDaddy のログイン ページにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="eda58-122">**GoDaddy users**: Office 365 Management portal redirects you to GoDaddy's login page.</span></span> <span data-ttu-id="eda58-123">資格情報を入力し、ドメインの変更アクセス許可に同意すると、TXT レコードが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="eda58-123">After you enter your credentials and accept the domain change permission agreement, the TXT record is created automatically.</span></span> <span data-ttu-id="eda58-124">または [TXT レコードを作成](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a)できます。</span><span class="sxs-lookup"><span data-stu-id="eda58-124">You can alternatively [create the TXT record](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).</span></span>
    - <span data-ttu-id="eda58-125">**Register.com ユーザー**: この[ステップ バイ ステップの指示](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify)に従って、TXT レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="eda58-125">**Register.com users**: Follow the [step-by-step instructions](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) to create the TXT record.</span></span>

<span data-ttu-id="eda58-126">カスタム ドメインを追加し、確認する手順は、[Azure Active Directory でも実行](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/)できます。</span><span class="sxs-lookup"><span data-stu-id="eda58-126">The steps to add and verify a custom domain can also be [performed in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).</span></span>

<span data-ttu-id="eda58-127">詳しくは、「[Office 365 の最初の onmicrosoft.com ドメインの概要](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="eda58-127">You can learn more [about your initial onmicrosoft.com domain in Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)</span></span>
