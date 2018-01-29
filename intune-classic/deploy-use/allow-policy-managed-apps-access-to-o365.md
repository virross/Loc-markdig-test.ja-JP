---
title: "アプリ ベースの O365 に対する条件付きアクセス"
description: "MAM CA を利用して、O365 サービスに対してアクセス権を持つアプリを制御する方法の概念について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e09c962f5e4c79d1555ecae912e79937d638718
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a><span data-ttu-id="56d7f-103">Intune アプリ保護ポリシーをサポートするモバイル アプリのみが Office 365 サービスにアクセスできるようにする</span><span class="sxs-lookup"><span data-stu-id="56d7f-103">Allow only mobile apps that support Intune app protection policies to access Office 365 services</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="56d7f-104">[Intune アプリ保護ポリシー](protect-apps-and-data-with-microsoft-intune.md)を使用すると、Intune の管理対象に登録されているデバイス上の会社のデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="56d7f-104">[Intune app protection policies](protect-apps-and-data-with-microsoft-intune.md) help protect your company data on devices that are enrolled for management in Intune.</span></span> <span data-ttu-id="56d7f-105">**Intune の監視対象に登録されていない従業員が所有するデバイス**に対して、アプリ保護ポリシーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="56d7f-105">You can also use app protection policies on **employee owned devices that are not enrolled for management in Intune**.</span></span>  <span data-ttu-id="56d7f-106">この場合、デバイスを管理しなくても、会社のデータとリソースが保護されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56d7f-106">In this case, even though you don't manage the device, you still need to make sure that your company data and resources is protected.</span></span> <span data-ttu-id="56d7f-107">MAM とアプリ ベースの条件付きアクセスを使用すると、Exchange Online などの Office 365 サービスにアクセスするための Intune アプリ保護ポリシーをサポートするモバイル アプリのみに許可するポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="56d7f-107">Using app-based conditional access with MAM, you can create a policy that allows only mobile apps that support Intune app protection policies to access O365 services like Exchange Online.</span></span>

<span data-ttu-id="56d7f-108">たとえば、Exchange Online へのアクセスを **Microsoft Outlook アプリ**のみに許可すると、**Exchange Online** からから電子メールを取得するように Intune MAM ポリシーのデータ保護を受けていない **iOS と Android の組み込み電子メール アプリをブロックできます**。</span><span class="sxs-lookup"><span data-stu-id="56d7f-108">For example, by only allowing the **Microsoft Outlook app** to access Exchange Online, you can **block the built-in mail apps on iOS and Android**, which don't have the data protection from Intune MAM policies to get email from **Exchange Online**.</span></span> <span data-ttu-id="56d7f-109">あるいは Intune MAM サポートのないモバイル アプリの **SharePoint Online** へのアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="56d7f-109">Or you can block mobile apps that don’t have Intune MAM support from accessing **SharePoint Online**.</span></span>

<span data-ttu-id="56d7f-110">次の図は、アプリ ベースの条件付きアクセス ポリシーがアクセスを許可するかブロックするかを決定するために使用するフローです。![アクセスを許可するかブロックするかを決定するための多様な条件を示す図](../media/mam-ca-decision-flow_simple.png)。</span><span class="sxs-lookup"><span data-stu-id="56d7f-110">The diagram below illustrates the flow used by app-based conditional access policies to determine when to allow or block access: ![Diagram that shows the various criteria included to determine whether to allow or block access ](../media/mam-ca-decision-flow_simple.png).</span></span>

<span data-ttu-id="56d7f-111">図に使用されている省略語の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56d7f-111">Description of the abbreviations used in the diagrams:</span></span>
* <span data-ttu-id="56d7f-112">**CP**: ポータル サイト アプリ</span><span class="sxs-lookup"><span data-stu-id="56d7f-112">**CP**: Company Portal app</span></span>
* <span data-ttu-id="56d7f-113">**AA**: Azure Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="56d7f-113">**AA**: Azure Authenticator app</span></span>
* <span data-ttu-id="56d7f-114">**AAD**: Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="56d7f-114">**AAD**: Azure Active Directory</span></span>
* <span data-ttu-id="56d7f-115">**EAS**: Exchange Active Sync</span><span class="sxs-lookup"><span data-stu-id="56d7f-115">**EAS**: Exchange Active Sync</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56d7f-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="56d7f-116">Prerequisites</span></span>
<span data-ttu-id="56d7f-117">アプリ ベースの条件付きアクセス ポリシーを作成する**前に**、**Enterprise Mobility + Security または Azure Active Directory Premium サブスクリプション**を用意する必要があります。また、ユーザーに EMS または Azure AD のライセンスが付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="56d7f-117">**Before** you create an app-based conditional access policy, you must have an **Enterprise Mobility + Security or an Azure Active Directory premium subscription**, and the users must be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="56d7f-118">詳細については、「[Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing)」 (Enterprise Mobility の価格) ページまたは「[Azure Active Directory の価格](https://azure.microsoft.com/pricing/details/active-directory/)」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d7f-118">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>


## <a name="supported-apps"></a><span data-ttu-id="56d7f-119">サポートされているアプリ</span><span class="sxs-lookup"><span data-stu-id="56d7f-119">Supported apps</span></span>
<span data-ttu-id="56d7f-120">**Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="56d7f-120">**Exchange Online**:</span></span>
* <span data-ttu-id="56d7f-121">Android 用と iOS 用 **Microsoft Outlook**</span><span class="sxs-lookup"><span data-stu-id="56d7f-121">**Microsoft Outlook** for Android and iOS.</span></span>

<span data-ttu-id="56d7f-122">**SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="56d7f-122">**SharePoint Online**</span></span>
* <span data-ttu-id="56d7f-123">iOS 用と Android 用の Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="56d7f-123">Microsoft Word for iOS and Android</span></span>
* <span data-ttu-id="56d7f-124">iOS 用と Android 用の Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="56d7f-124">Microsoft Excel for iOS and Android</span></span>
* <span data-ttu-id="56d7f-125">iOS 用と Android 用の Microsoft PowerPoint</span><span class="sxs-lookup"><span data-stu-id="56d7f-125">Microsoft PowerPoint for iOS and Android</span></span>
* <span data-ttu-id="56d7f-126">iOS 用と Android 用の Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="56d7f-126">Microsoft OneDrive for Business for iOS and Android</span></span>
* <span data-ttu-id="56d7f-127">iOS 用の Microsoft OneNote</span><span class="sxs-lookup"><span data-stu-id="56d7f-127">Microsoft OneNote for iOS</span></span>

>[!IMPORTANT]
><span data-ttu-id="56d7f-128">Android デバイスでは、OneDrive アプリまたは Outlook アプリのいずれかにログインして、最初にデバイス登録を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56d7f-128">For Android devices, the initial device registration must be done by logging into either the OneDrive app, or the Outlook app.</span></span> <span data-ttu-id="56d7f-129">Android 用の OneNote アプリは、登録なしでの MAM をまだサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="56d7f-129">The OneNote app for Android does not yet support MAM without enrollment.</span></span>

<span data-ttu-id="56d7f-130">アプリ ベースの条件付きアクセス ポリシーが設定されたアプリのユーザー エクスペリエンスの詳細については、[アプリと MAM CA を使用する場合の結果](use-apps-with-mam-ca.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="56d7f-130">To learn about the user experience with an app that has app-based conditional access policies, see [What to expect when using an app with MAM CA](use-apps-with-mam-ca.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="56d7f-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="56d7f-131">Next steps</span></span>
[<span data-ttu-id="56d7f-132">MAM アプリ用の Exchange Online ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="56d7f-132">Create an Exchange Online Policy for MAM apps</span></span>](mam-ca-for-exchange-online.md)

[<span data-ttu-id="56d7f-133">MAM アプリ用の SharePoint Online ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="56d7f-133">Create a SharePoint Online Policy for MAM apps</span></span>](mam-ca-for-sharepoint-online.md)

[<span data-ttu-id="56d7f-134">最新の認証を使用していないアプリをブロックする</span><span class="sxs-lookup"><span data-stu-id="56d7f-134">Block apps that do not have modern authentication</span></span>](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a><span data-ttu-id="56d7f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="56d7f-135">See also</span></span>

[<span data-ttu-id="56d7f-136">アプリ保護ポリシーを使用したアプリ データの保護</span><span class="sxs-lookup"><span data-stu-id="56d7f-136">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
