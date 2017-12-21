---
title: "アプリとデータを保護する"
description: "このトピックでは、さまざまな Intune の機能と、会社のアプリとデータを保護するために使用可能な機能について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d427d2594d9d5944ca4662d6e6d301299adf85a7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="protect-apps-and-data-with-microsoft-intune"></a><span data-ttu-id="5db8f-103">Microsoft Intune でアプリとデータを保護する</span><span class="sxs-lookup"><span data-stu-id="5db8f-103">Protect apps and data with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="5db8f-104">Intune は、複数のテクノロジ層を介して会社のデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="5db8f-104">Intune protects company data through multiple technology layers.</span></span> <span data-ttu-id="5db8f-105">ID 層では、条件付きアクセスによりサービスへのアクセスを保護します。管理対象のデバイスが条件を満たした場合にのみアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-105">At the identity layer, conditional access protects access to services by only allowing access from managed and compliant devices.</span></span> <span data-ttu-id="5db8f-106">クライアント アプリケーション層では、モバイル アプリ管理 (MAM) がデータ紛失を防止します。保護されていないアプリや記憶域にデータを移動する行為を禁止し、デバイスをなくしたり、盗難に遭ったりした場合、データを消去します。</span><span class="sxs-lookup"><span data-stu-id="5db8f-106">At the client application layer, mobile application management (MAM) protects data loss by preventing data from moving to nonprotected apps or storage locations—and by wiping data when a device is lost or stolen.</span></span> <span data-ttu-id="5db8f-107">これらの 2 つの保護層は合わせて使用し、データをセキュリティで保護し、モバイルの生産性を維持することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-107">We recommend using these two layers of protection together to help secure data while keeping your mobile workforce productive.</span></span>

<span data-ttu-id="5db8f-108">会社のデータを保護するための最初の重要な手順は、条件付きアクセスを導入することです。</span><span class="sxs-lookup"><span data-stu-id="5db8f-108">An important first step to protecting company data is to implement conditional access.</span></span> <span data-ttu-id="5db8f-109">そのために、データ アクセスに使用されるデバイスで強力なパスワードや暗号化などのセキュリティ保護を利用し、脱獄されないようにします。</span><span class="sxs-lookup"><span data-stu-id="5db8f-109">You do this by making sure that devices that are used to access that data are using security protections like strong passwords and encryption, and are not jailbroken.</span></span> <span data-ttu-id="5db8f-110">Intune では、条件を設定できます。その条件をデバイスが満たさないと、会社の電子メールやデータにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5db8f-110">Intune lets you set conditions that the devices have to comply with before they're allowed to access your company email and data.</span></span>

<span data-ttu-id="5db8f-111">[条件付きアクセス](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)は、Intune で設定できる次の 2 つの種類のポリシーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-111">[Conditional access](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) is determined by two types of policies that you can set in Intune:</span></span>
- <span data-ttu-id="5db8f-112">[コンプライアンス ポリシー](introduction-to-device-compliance-policies-in-microsoft-intune.md)を利用し、デバイスのコンプライアンス対応状態を判断します。</span><span class="sxs-lookup"><span data-stu-id="5db8f-112">You use [compliance policies](introduction-to-device-compliance-policies-in-microsoft-intune.md) to determine the compliance of a device.</span></span> <span data-ttu-id="5db8f-113">このポリシーは、次のような設定と条件を評価します。</span><span class="sxs-lookup"><span data-stu-id="5db8f-113">They evaluate settings and conditions like:</span></span>
  - <span data-ttu-id="5db8f-114">PIN とパスワード: ルールを作成してデバイスのロック解除にパスワードを要求したり、パスワードの要件を複雑にしたり、他のパスワード設定を要求したりできます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-114">PINs and passwords: You can create rules to require passwords to unlock a device, for the complexity requirements of the password, and for other password settings.</span></span>
  - <span data-ttu-id="5db8f-115">暗号化: 暗号化されているデバイスへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-115">Encryption: You can restrict access to devices that are encrypted.</span></span>
  - <span data-ttu-id="5db8f-116">デバイスが脱獄またはルート化されていない: Intune は、登録済みのデバイスが脱獄されているかどうかを検出できます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-116">When a device is not jailbroken or rooted: Intune can detect if an enrolled device is jailbroken.</span></span> <span data-ttu-id="5db8f-117">そのようなデバイスからのアクセスをブロックするポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-117">You can set the policy to block access on such devices.</span></span>
- <span data-ttu-id="5db8f-118">Exchange Online や SharePoint Online などの特定のサービスに[条件付きアクセス ポリシー](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)を構成します。</span><span class="sxs-lookup"><span data-stu-id="5db8f-118">You configure [conditional access policies](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) for a particular service, like Exchange Online or SharePoint Online.</span></span> <span data-ttu-id="5db8f-119">各サービスに、これらのポリシーが適用されるユーザーのグループを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-119">For each service, you can define which groups of users these policies should apply to.</span></span> <span data-ttu-id="5db8f-120">たとえば、財務部門のすべてのユーザーに、登録済みの準拠デバイスから会社の電子メールへのアクセスのみを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-120">For example, you can make sure that everyone in the finance department can only access company email from enrolled and compliant devices.</span></span>

<span data-ttu-id="5db8f-121">会社のリソースに対するアクセスをセキュリティで保護することは、会社のデータ保護の最初の手順に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="5db8f-121">Securing access to company resources is just the first step to protecting company data.</span></span> <span data-ttu-id="5db8f-122">デバイスでデータにアクセスした後も、引き続きデータを保護する機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="5db8f-122">You still need the ability to protect data after it's been accessed on the device.</span></span> <span data-ttu-id="5db8f-123">これでデータを他の場所にコピー、移動、保存したり、共有したりできます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-123">The data can now be copied, moved, saved to a different location, or shared.</span></span> <span data-ttu-id="5db8f-124">Intune には次のような一連のルールを作成することでデータ移動を制限する機能があり、この問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="5db8f-124">Intune solves this problem by providing you with the ability to restrict data movement by creating a set of rules like:</span></span>
- <span data-ttu-id="5db8f-125">コピーと貼り付けを禁止します。あるいは、仕事以外でのデータ転送を禁止します。</span><span class="sxs-lookup"><span data-stu-id="5db8f-125">Blocking copy and paste, or preventing data transfer outside of the work context.</span></span>
- <span data-ttu-id="5db8f-126">個人のクラウドの記憶域にバックアップすることと "名前を付けて保存する" ことを防止することを禁止します。</span><span class="sxs-lookup"><span data-stu-id="5db8f-126">Preventing backup to personal cloud storage and preventing "Save as".</span></span>
- <span data-ttu-id="5db8f-127">PIN/パスコードまたは会社の資格情報を要求し、アプリのアクセスをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="5db8f-127">Securing app access by requiring a PIN/passcode or corporate credentials.</span></span>
- <span data-ttu-id="5db8f-128">Web リンクはすべて Intune Managed Browser 内で開きます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-128">Having all web links open within the Intune Managed Browser.</span></span>

<span data-ttu-id="5db8f-129">これらの一連のルールは[モバイル アプリ管理 (MAM) ポリシー](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="5db8f-129">These set of rules are referred to as [mobile application management (MAM) policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).</span></span> <span data-ttu-id="5db8f-130">MAM ポリシーはアプリに適用できます。アプリを実行しているデバイスを自分が管理しているかどうかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="5db8f-130">You can apply MAM policies to apps that are running on devices that might or might not be managed by you.</span></span>  

<span data-ttu-id="5db8f-131">**Intune に登録されている**デバイスや、**他のサード パーティ MDM (モバイル デバイス管理) により登録され、管理されている**デバイス、社員所有のデバイスなどの **MDM ソリューションに登録されていない**デバイスに MAM ポリシーを適用し、会社のデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-131">You can protect your company data by using MAM policies for devices that are **enrolled in Intune**, devices that are **enrolled and managed by another third-party mobile device management (MDM) solution**, or devices that are **not enrolled in any MDM solution**, like employee-owned devices.</span></span>

<span data-ttu-id="5db8f-132">アプリと MAM ポリシーを関連付けるには、アプリに Microsoft Intune App ソフトウェア開発キット (SDK) を組み込む必要があります。あるいは、アプリ ラッピング ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-132">To associate an app with a MAM policy, the app must incorporate the Microsoft Intune App Software Development Kit (SDK), or you can use the App Wrapping Tool.</span></span>

<span data-ttu-id="5db8f-133">Microsoft Office アプリのようなアプリには、Intune アプリ SDK が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="5db8f-133">Apps like Microsoft Office apps have the Intune App SDK built in.</span></span> <span data-ttu-id="5db8f-134">Microsoft Intune アプリケーション パートナー ページの [Microsoft Intune モバイル アプリケーション ギャラリー](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)で、サポートされているアプリの完全な一覧を参照できます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-134">You can see the full list of supported apps in the [Microsoft Intune mobile application gallery](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) on the Microsoft Intune application partners page.</span></span> <span data-ttu-id="5db8f-135">アプリを選択し、サポートされるシナリオ、プラットフォーム、アプリのマルチ ID 対応を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5db8f-135">Choose the app to see the supported scenarios and platforms, and whether the app supports multi-identity.</span></span>

<span data-ttu-id="5db8f-136">[特注の基幹業務アプリ](/intune/apps-prepare-mobile-application-management)で MAM ポリシーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-136">You can also [enable your custom-built line-of-business apps](/intune/apps-prepare-mobile-application-management) to use with MAM policies.</span></span>

<span data-ttu-id="5db8f-137">データ移動を制限するだけでなく、デバイスをなくしたり、盗難に遭ったりした場合、あるいは、ユーザーが退職した場合、[会社のデータを選択消去](wipe-managed-company-app-data-with-microsoft-intune.md)し、個人データだけを残すことができます。</span><span class="sxs-lookup"><span data-stu-id="5db8f-137">In addition to restricting data movement, if a device gets lost or stolen or the user is no longer working with your company, you can [selectively wipe company data](wipe-managed-company-app-data-with-microsoft-intune.md), which leaves only personal data behind.</span></span>