---
title: "Intune でのアプリ ベースの条件付きアクセス"
description: "Intune でのアプリ ベースの条件付きアクセスがどのように機能するのかについて、その概念を説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 21a027e0acd81d919b402128202e4a70a6788173
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="app-based-conditional-access-with-intune"></a><span data-ttu-id="f6f7a-103">Intune でのアプリ ベースの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="f6f7a-103">App-based conditional access with Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="f6f7a-104">[Intune アプリ保護ポリシー](app-protection-policy.md)を使用すると、Intune に登録されているデバイス上の会社のデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-104">[Intune app protection policies](app-protection-policy.md) help protect your company data on devices that are enrolled into Intune.</span></span> <span data-ttu-id="f6f7a-105">Intune での管理対象に登録されていない従業員所有のデバイスでも、アプリ保護ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-105">You can also use app protection policies on employee owned devices that are not enrolled for management in Intune.</span></span> <span data-ttu-id="f6f7a-106">この場合、会社はデバイスを管理しなくても、会社のデータとリソースが保護されるようにする必要はあります。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-106">In this case, even though your company doesn't manage the device, you still need to make sure that company data and resources are protected.</span></span>

<span data-ttu-id="f6f7a-107">アプリ ベースの条件付きアクセスとモバイル アプリ管理は、Intune アプリ保護ポリシーをサポートするモバイル アプリのみが Exchange Online やその他の Office 365 サービスにアクセスできるようにすることで、セキュリティ層を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-107">App-based conditional access and mobile app management add a security layer by making sure only mobile apps that support Intune app protection policies can access Exchange online and other Office 365 services.</span></span>

> [!NOTE]
> <span data-ttu-id="f6f7a-108">管理対象アプリは、アプリ保護ポリシーが適用されたアプリであり、Intune で管理できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-108">A managed app is an app that has app protection policies applied to it, and can be managed by Intune.</span></span>

<span data-ttu-id="f6f7a-109">Microsoft Outlook アプリのみが Exchange Online にアクセスできるようにすると、iOS や Android 上の組み込みメール アプリをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-109">You can block the built-in mail apps on iOS and Android when you allow only the Microsoft Outlook app to access Exchange Online.</span></span> <span data-ttu-id="f6f7a-110">また、Intune アプリ保護ポリシーを適用していないアプリが SharePoint Online にアクセスするのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-110">Additionally, you can block apps that don’t have Intune app protection policies applied from accessing SharePoint Online.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6f7a-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6f7a-111">Prerequisites</span></span>
<span data-ttu-id="f6f7a-112">アプリ ベースの条件付きアクセス ポリシーを作成するには、以下を保有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-112">Before you create an app-based conditional access policy, you must have:</span></span>

- <span data-ttu-id="f6f7a-113">**Enterprise Mobility + Security (EMS)** または **Azure Active Directory (AD) Premium サブスクリプション**</span><span class="sxs-lookup"><span data-stu-id="f6f7a-113">**Enterprise Mobility + Security (EMS)** or an **Azure Active Directory (AD) Premium subscription**</span></span>
- <span data-ttu-id="f6f7a-114">ユーザーは、EMS または Azure AD のライセンスを取得している必要があります</span><span class="sxs-lookup"><span data-stu-id="f6f7a-114">Users must be licensed for EMS or Azure AD</span></span>

<span data-ttu-id="f6f7a-115">詳細については、「[Enterprise Mobility pricing](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing)」(Enterprise Mobility の価格) または「[Azure Active Directory の価格](https://azure.microsoft.com/pricing/details/active-directory/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-115">For more information, see [Enterprise Mobility pricing ](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

## <a name="supported-apps"></a><span data-ttu-id="f6f7a-116">サポートされているアプリ</span><span class="sxs-lookup"><span data-stu-id="f6f7a-116">Supported apps</span></span>

<span data-ttu-id="f6f7a-117">アプリ ベースの条件付きアクセスをサポートしているアプリのリストについては、「[Azure Active Directory の条件付きアクセスに関するテクニカル リファレンス」のドキュメント](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-117">A list of apps that support app-based conditional access can be found in the [Azure Active Directory conditional access technical reference documentation.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)</span></span>

<span data-ttu-id="f6f7a-118">アプリ ベースの条件付きアクセスは[基幹業務 (LOB) アプリもサポート](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication)していますが、LOB アプリが [Office 365 の先進認証](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a)を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-118">App-based conditional access [also supports line-of-business (LOB) apps](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), but these apps need to use [Office 365 modern authentication](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a).</span></span>

## <a name="how-app-based-conditional-access-works"></a><span data-ttu-id="f6f7a-119">アプリ ベースの条件付きアクセスのしくみ</span><span class="sxs-lookup"><span data-stu-id="f6f7a-119">How app-based conditional access works</span></span>

<span data-ttu-id="f6f7a-120">この例では、管理者は Outlook アプリにアプリ保護ポリシーを適用し、その後、会社の電子メールへのアクセス時に使用できるアプリの承認済みリストに Outlook アプリを追加する条件付きアクセス ルールを適用しています。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-120">In this example, the admin has applied app protection policies to the Outlook app followed by a conditional access rule that adds the Outlook app to an approved list of apps that can be used when accessing corporate e-mail.</span></span>

> [!NOTE]
> <span data-ttu-id="f6f7a-121">下のフローチャートの構造は、他の管理対象アプリでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-121">The flowchart structure below can be used for other managed apps.</span></span>

![Intune フローチャートを使用したアプリ ベースの条件付きアクセス](./media/ca-intune-common-ways-3.png)

1. <span data-ttu-id="f6f7a-123">ユーザーは、Outlook アプリから Azure AD の認証を試みます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-123">The user tries to authenticate to Azure AD from the Outlook app.</span></span>

2. <span data-ttu-id="f6f7a-124">ユーザーは、初回認証時、ブローカー アプリのインストールのためにアプリ ストアにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-124">The user gets redirected to the app store to install a broker app when trying to authenticate for the first time.</span></span> <span data-ttu-id="f6f7a-125">ブローカー アプリは、iOS の場合は Microsoft Authenticator、Android デバイスの場合は Microsoft ポータル サイトになります。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-125">The broker app can be either the Microsoft Authenticator for iOS, or the Microsoft Company portal for Android devices.</span></span>

   <span data-ttu-id="f6f7a-126">ユーザーがネイティブの電子メール アプリを使おうとすると、アプリ ストアにリダイレクトされ、その後 Outlook アプリのインストールにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-126">If users try to use a native e-mail app, they’ll be redirected to the app store to then install the Outlook app.</span></span>

3. <span data-ttu-id="f6f7a-127">ブローカー アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-127">The broker app gets installed on the device.</span></span>

4. <span data-ttu-id="f6f7a-128">ブローカー アプリが、Azure AD にデバイス レコードを作成する Azure AD 登録プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-128">The broker app starts the Azure AD registration process which creates a device record in Azure AD.</span></span> <span data-ttu-id="f6f7a-129">これは、モバイル デバイス管理 (MDM) の登録プロセスとは異なりますが、条件付きアクセス ポリシーをデバイスに適用するためにこのレコードが必要となります。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-129">This is not the same as the mobile device management (MDM) enrollment process, but this record is necessary so the conditional access policies can be enforced on the device.</span></span>

5. <span data-ttu-id="f6f7a-130">ブローカー アプリがアプリの ID を確認します。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-130">The broker app verifies the identity of the app.</span></span> <span data-ttu-id="f6f7a-131">セキュリティ層があるため、ブローカー アプリはユーザーによるアプリの使用が認証されているかどうかを検証できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-131">There’s a security layer so the broker app can validate if the app is authorized to be used by the user.</span></span>

6. <span data-ttu-id="f6f7a-132">ブローカー アプリが、ポリシーの承認済みリストに登録されているかどうかをチェックするユーザー認証プロセスの一部として、App Client ID を Azure AD に送信します。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-132">The broker app sends the App Client ID to Azure AD as part of the user authentication process to check if it’s in the policy approved list.</span></span>

7. <span data-ttu-id="f6f7a-133">Azure AD が、ポリシーの承認済みリストに基づいて、ユーザーによるアプリの認証と使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-133">Azure AD allows the user to authenticate and use the app based on the policy approved list.</span></span> <span data-ttu-id="f6f7a-134">アプリがリストに登録されていない場合、Azure AD はそのアプリへのアクセスを拒否します。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-134">If the app is not on the list, Azure AD denies access to the app.</span></span>

8. <span data-ttu-id="f6f7a-135">Outlook アプリが Outlook クラウド サービスと通信して、Exchange Online との通信を開始します。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-135">The Outlook app communicates with Outlook Cloud Service to initiate communication with Exchange Online.</span></span>

9. <span data-ttu-id="f6f7a-136">Outlook クラウド サービスが Azure AD と通信して、ユーザーの Exchange Online サービス アクセス トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-136">Outlook Cloud Service communicates with Azure AD to retrieve Exchange Online service access token for the user.</span></span>

10. <span data-ttu-id="f6f7a-137">Outlook アプリが Exchange Online と通信して、ユーザーの会社の電子メールを取得します。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-137">The Outlook app communicates with Exchange Online to retrieve the user's corporate e-mail.</span></span>

11. <span data-ttu-id="f6f7a-138">会社の電子メールは、ユーザーのメールボックスに配信されています。</span><span class="sxs-lookup"><span data-stu-id="f6f7a-138">Corporate e-mail is delivered to the user's mailbox.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6f7a-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="f6f7a-139">Next steps</span></span>
[<span data-ttu-id="f6f7a-140">アプリベースの条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f6f7a-140">Create an app-based conditional access policy</span></span>](app-based-conditional-access-intune-create.md)

[<span data-ttu-id="f6f7a-141">最新の認証を使用していないアプリをブロックする</span><span class="sxs-lookup"><span data-stu-id="f6f7a-141">Block apps that do not have modern authentication</span></span>](app-modern-authentication-block.md)
