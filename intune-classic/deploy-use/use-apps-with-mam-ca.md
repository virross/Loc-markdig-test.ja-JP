---
title: "MAM CA を利用してアプリを使用する"
description: "MAM CA を利用して、O365 サービスに対してアクセス権を持つアプリを制御する方法の概念について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4eebc3c78626b9ef1ddbcef976f5b49cadc4b5ff
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="what-to-expect-when-using-an-app-with-app-based-ca"></a><span data-ttu-id="ebbfa-103">アプリとアプリ ベースの CA を使用する場合の結果</span><span class="sxs-lookup"><span data-stu-id="ebbfa-103">What to expect when using an app with app-based CA</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ebbfa-104">アプリ ベースの CA は、デバイス上に必ずあるブローカー アプリを利用して、承認されたアプリケーションの ID を確認します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-104">App-based CA verifies the identity of the approved application by means of a broker app that must be present on the device:</span></span>
*  <span data-ttu-id="ebbfa-105">**iOS** の場合、**Azure Authenticator アプリ**がブローカー アプリです。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-105">On **iOS**, the **Azure Authenticator app** is the broker app.</span></span>
* <span data-ttu-id="ebbfa-106">**Android** の場合、**Intune ポータル サイト アプリ**がブローカー アプリです。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-106">On **Android**, the **Intune Company Portal app** is the broker app.</span></span> 

<span data-ttu-id="ebbfa-107">OneDrive や Outlook など、アプリ ベースの CA でサポートされているアプリにエンドユーザーが初めてサインインする場合、ブローカー アプリをインストールし、デバイスを Azure AD に登録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-107">End-users signing in for the first time, to an app that is supported by app-based CA, like OneDrive or Outlook, are prompted to install the broker app and register the device with Azure AD.</span></span> <span data-ttu-id="ebbfa-108">Azure AD にデバイスを登録すると (以前は社内参加と呼ばれていました)、トークンの発行先に対してデバイス レコードと証明書が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-108">Device registration in Azure AD (previously known as Workplace Join) will create a device record and certificate against which tokens are issued.</span></span>  <span data-ttu-id="ebbfa-109">これは **MDM の登録**と**同じではありません**。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-109">This is **not** the same as **MDM enrollment**.</span></span> <span data-ttu-id="ebbfa-110">適用される管理プロファイルまたはポリシーはありません。また、デバイスのアプリから取得されるインベントリはありません。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-110">There are no management profiles or policies that are applied, and there is no inventory taken of apps on the device.</span></span>  <span data-ttu-id="ebbfa-111">ブローカー アプリのインストールとデバイスの登録プロセスは、管理対象アプリを初めて使用する場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-111">The process of installing the broker app and registering the device will only happen on the first use of a managed app.</span></span>

<span data-ttu-id="ebbfa-112">次の一覧は、デバイスから直接派生するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-112">The following is a list of properties that are directly derived from the device:</span></span>

* <span data-ttu-id="ebbfa-113">alternativeSecurityIds (Azure Active Directory 証明書の拇印と公開キー ハッシュ)</span><span class="sxs-lookup"><span data-stu-id="ebbfa-113">alternativeSecurityIds (Azure Active Directory Certificate thumbprint and public key hash)</span></span>
* <span data-ttu-id="ebbfa-114">deviceOSType</span><span class="sxs-lookup"><span data-stu-id="ebbfa-114">deviceOSType</span></span>
* <span data-ttu-id="ebbfa-115">deviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="ebbfa-115">deviceOSVersion</span></span>
* <span data-ttu-id="ebbfa-116">displayName</span><span class="sxs-lookup"><span data-stu-id="ebbfa-116">displayName</span></span>

> [!NOTE]
> <span data-ttu-id="ebbfa-117">Android デバイスの場合、</span><span class="sxs-lookup"><span data-stu-id="ebbfa-117">On Android devices:</span></span>
  * <span data-ttu-id="ebbfa-118">デバイスにポータル サイト アプリがインストールされている必要がありますが、エンド ユーザーがアプリにログインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-118">It is required that the Company Portal app is installed on the device, but end-user is not required to log in into app.</span></span>
  * <span data-ttu-id="ebbfa-119">OneDrive または Outlook アプリを使用して、デバイスの登録を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-119">Device registration must be done through the OneDrive or Outlook app.</span></span>

## <a name="to-remove-a-device-from-azure-ad-registration"></a><span data-ttu-id="ebbfa-120">Azure AD の登録からデバイスを削除するには</span><span class="sxs-lookup"><span data-stu-id="ebbfa-120">To remove a device from Azure AD registration.</span></span>
<span data-ttu-id="ebbfa-121">デバイスの登録は、Azure AD 管理コンソールで削除することができます。通常、IT 管理者が削除を実行します。また、エンドユーザーが自分のデバイスで削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-121">You can remove the device registration either through the Azure AD admin console which is typically done by the IT admin.  It can also be done by the end-user on the device itself.</span></span>

* <span data-ttu-id="ebbfa-122">**Azure AD 管理コンソール**: Azure AD 管理コンソール**で、対象のデバイスを削除します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-122">**Azure AD admin console**: In the Azure AD admin console**, delete the device that you want to remove.</span></span>
* <span data-ttu-id="ebbfa-123">**iOS デバイス**: Azure Authenticator アプリを開き、アカウントを左にスワイプし、登録の解除を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-123">**iOS device**: Open the Azure Authenticator app, swipe left on the account, and choose unregister.</span></span>  
* <span data-ttu-id="ebbfa-124">**Android デバイス**: ポータル サイト アプリをアンインストールするか、**[システム設定]** からアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-124">**Android device**: Uninstall the company portal app or remove the account from the **System settings**.</span></span>

## <a name="app-based-ca-with-device-based-ca"></a><span data-ttu-id="ebbfa-125">アプリ ベースの CA とデバイス ベースの CA</span><span class="sxs-lookup"><span data-stu-id="ebbfa-125">App-based CA with Device-based CA</span></span>  

<span data-ttu-id="ebbfa-126">[Intune 管理コンソール](https://manage.microsoft.com)または [Azure AD Premium 管理コンソール] (https://manage.windowsazure.com) で[デバイスのコンプライアンスに基づいて条件付きアクセス](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**デバイス CA**) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-126">You can configure [Conditional access based on device compliance](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**Device CA**) on the [Intune administrator console](https://manage.microsoft.com) or the [Azure AD Premium management console] (https://manage.windowsazure.com).</span></span> <span data-ttu-id="ebbfa-127">デバイス CA を使用する場合、ユーザーが Exchange Online に接続するには、Intune デバイス コンプライアンス ポリシーに準拠している Intune の管理対象デバイス、またはドメインに参加しているコンピューターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-127">Device CA require users to connect to Exchange Online only through Intune-managed  devices that are compliant with the Intune device compliance policy or domain-joined PCs.</span></span>  <span data-ttu-id="ebbfa-128">ユーザーが、アプリ ベースの CA とデバイス CA ポリシー両方の対象である 1 つまたは複数のセキュリティ グループに属している場合、ユーザーは次の 2 つの要件のうち 1 つを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-128">If a user belongs to one or more security groups that are targeted for both app-based CA and Device CA policies, the user must meet one of the two requirements:</span></span>
* <span data-ttu-id="ebbfa-129">サービスへのアクセスに使用されるアプリは、サポートされているモバイル アプリである。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-129">The app used to access the service is a mobile app that is supported by</span></span> 
* <span data-ttu-id="ebbfa-130">アプリを実行するデバイスには、**iOS Authenticator (iOS デバイスの場合)** または**ポータル サイト アプリ (Android デバイスの場合)** がインストールされている。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-130">, and the device that the app is running on, has **iOS Authenticator (for iOS devices)**, or the **Company Portal app (for Android devices)** installed.</span></span>
* <span data-ttu-id="ebbfa-131">サービスへのアクセスに使用されるデバイスは、**Intune の管理対象で Intune のデバイス コンプライアンス ポリシーに準拠している**か、**ドメインに参加しているコンピューター**である。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-131">The device used to access the service is **Intune-managed and compliant** with the Intune device compliance policy, or it is a **domain-joined PC**.</span></span>  <span data-ttu-id="ebbfa-132">わかりやすい例を示します。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-132">Here are some examples to help illustrate this:</span></span>
  * <span data-ttu-id="ebbfa-133">ユーザーが**ネイティブ iOS 電子メール アプリ**から接続する場合、ネイティブ電子メール アプリは アプリ ベースの CA でサポートされていないため、**管理対象で準拠しているデバイス**を使用して接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-133">If a user tries to connect from the **native iOS email app**, he or she will be required to be on a **managed and compliant device** since the native mail app is not supported by app-based CA.</span></span>
  * <span data-ttu-id="ebbfa-134">ユーザーが **Windows Home コンピューター**から接続する場合、**デバイス CA ポリシー**が適用されるので、ドメインに参加しているコンピューターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebbfa-134">If a user tries to connect from a **Windows home PC**, the **Device CA policy** will apply, requiring that the he or she must use a domain-joined PC.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ebbfa-135">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ebbfa-135">Next steps</span></span>
[<span data-ttu-id="ebbfa-136">MAM アプリ用の Exchange Online ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ebbfa-136">Create an Exchange Online Policy for MAM apps</span></span>](mam-ca-for-exchange-online.md)

[<span data-ttu-id="ebbfa-137">最新の認証を使用していないアプリをブロックする</span><span class="sxs-lookup"><span data-stu-id="ebbfa-137">Block apps that do not have modern authentication</span></span>](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a><span data-ttu-id="ebbfa-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebbfa-138">See also</span></span>

[<span data-ttu-id="ebbfa-139">アプリ保護ポリシーを使用したアプリ データの保護</span><span class="sxs-lookup"><span data-stu-id="ebbfa-139">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
