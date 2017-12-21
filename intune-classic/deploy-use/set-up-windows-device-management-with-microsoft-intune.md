---
title: "Microsoft Intune を使用して Windows デバイスの管理をセットアップする"
description: "Microsoft Intune で Windows デバイスのモバイル デバイス管理 (MDM) を有効にします。"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bf95093d9cfe3a7066779ca21c47e32ea7c57bb3
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-windows-device-management"></a><span data-ttu-id="19175-103">Windows デバイスの管理をセットアップする</span><span class="sxs-lookup"><span data-stu-id="19175-103">Set up Windows device management</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="19175-104">このトピックは IT 管理者がユーザーの Windows の登録を簡略化する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="19175-104">This topic helps IT administrators simplify Windows enrollment for their users.</span></span>  <span data-ttu-id="19175-105">Windows デバイスは追加の手順なしに登録できますが、ユーザーのため、登録をより簡単にすることができます。</span><span class="sxs-lookup"><span data-stu-id="19175-105">Windows devices can be enrolled without any additional steps, but you can make enrollment easier for users.</span></span>

<span data-ttu-id="19175-106">Windows デバイスの登録を簡略化する方法は、次の 2 つの要素によって決まります。</span><span class="sxs-lookup"><span data-stu-id="19175-106">Two factors determine how you can simplify Windows device enrollment:</span></span>
- <span data-ttu-id="19175-107">**Azure Active Directory Premium を使用していますか?**</span><span class="sxs-lookup"><span data-stu-id="19175-107">**Do you use Azure Active Directory Premium?**</span></span> <br><span data-ttu-id="19175-108">[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) は、Enterprise Mobility + Security およびその他のライセンス プランに付属します。</span><span class="sxs-lookup"><span data-stu-id="19175-108">[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) is included with Enterprise Mobility + Security and other licensing plans.</span></span>
- <span data-ttu-id="19175-109">**どのバージョンの Windows クライアントが登録されますか?**</span><span class="sxs-lookup"><span data-stu-id="19175-109">**What versions of Windows clients will enroll?**</span></span> <br><span data-ttu-id="19175-110">Windows 10 デバイスは、職場または学校のアカウントを追加すると自動的に登録できます。</span><span class="sxs-lookup"><span data-stu-id="19175-110">Windows 10 devices can automatically enroll by adding a work or school account.</span></span> <span data-ttu-id="19175-111">以前のバージョンでは、会社ポータル アプリを使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19175-111">Earlier versions must enroll using the Company Portal app.</span></span>

||<span data-ttu-id="19175-112">**Azure AD Premium**</span><span class="sxs-lookup"><span data-stu-id="19175-112">**Azure AD Premium**</span></span>|<span data-ttu-id="19175-113">**その他の AD**</span><span class="sxs-lookup"><span data-stu-id="19175-113">**Other AD**</span></span>|
|----------|---------------|---------------|  
|<span data-ttu-id="19175-114">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="19175-114">**Windows 10**</span></span>|[<span data-ttu-id="19175-115">自動登録</span><span class="sxs-lookup"><span data-stu-id="19175-115">Automatic enrollment</span></span>](#enable-windows-10-automatic-enrollment) |[<span data-ttu-id="19175-116">ユーザー登録</span><span class="sxs-lookup"><span data-stu-id="19175-116">User enrollment</span></span>](#enable-windows-enrollment-without-automatic-enrollment)|
|<span data-ttu-id="19175-117">**以前の Windows バージョン**</span><span class="sxs-lookup"><span data-stu-id="19175-117">**Earlier Windows versions**</span></span>|[<span data-ttu-id="19175-118">ユーザー登録</span><span class="sxs-lookup"><span data-stu-id="19175-118">User enrollment</span></span>](#enable-windows-enrollment-without-automatic-enrollment)|[<span data-ttu-id="19175-119">ユーザー登録</span><span class="sxs-lookup"><span data-stu-id="19175-119">User enrollment</span></span>](#enable-windows-enrollment-without-automatic-enrollment)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a><span data-ttu-id="19175-120">自動登録なしの Windows 登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="19175-120">Enable Windows enrollment without automatic enrollment</span></span>
<span data-ttu-id="19175-121">Azure AD Premium の自動登録なしで、ユーザー自身にデバイスを登録させることができます。</span><span class="sxs-lookup"><span data-stu-id="19175-121">You can let users enroll their devices without Azure AD Premium automatic enrollment.</span></span> <span data-ttu-id="19175-122">ライセンスを割り当てると、ユーザーは、職場のアカウントを個人所有のデバイスに追加するか、会社所有のデバイスを Azure AD に参加させた後に登録を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="19175-122">Once you assign licenses, users can enroll after adding their work account to their personally-owned devices or joining their corporate-owned devices to your Azure AD.</span></span> <span data-ttu-id="19175-123">DNS エイリアス (CNAME レコード タイプ) を作成すると、ユーザーがデバイスを簡単に登録できるようになります。</span><span class="sxs-lookup"><span data-stu-id="19175-123">Creating a DNS alias (CNAME record type) makes it easier for users to enroll their devices.</span></span> <span data-ttu-id="19175-124">DNS の CNAME リソース レコードを作成すると、ユーザーは Intune サーバー名を入力することなく Intune に接続して登録できるようになります。</span><span class="sxs-lookup"><span data-stu-id="19175-124">If you create DNS CNAME resource records, users connect and enroll in Intune without having to enter the Intune server name.</span></span>

<span data-ttu-id="19175-125">**手順 1: CNAME を作成する** (省略可能)</span><span class="sxs-lookup"><span data-stu-id="19175-125">**Step 1: Create CNAMEs** (optional)</span></span><br>
<span data-ttu-id="19175-126">会社のドメインの CNAME DNS リソース レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="19175-126">Create CNAME DNS resource records for your company’s domain.</span></span> <span data-ttu-id="19175-127">たとえば、会社の Web サイトが contoso.com の場合、EnterpriseEnrollment.contoso.com を enterpriseenrollment-s.manage.microsoft.com にリダイレクトする CNAME を DNS に作成します。</span><span class="sxs-lookup"><span data-stu-id="19175-127">For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to enterpriseenrollment-s.manage.microsoft.com.</span></span>

<span data-ttu-id="19175-128">CNAME DNS エントリの作成は省略可能ですが、CNAME レコードにより登録が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="19175-128">Although creating CNAME DNS entries is optional, CNAME records make enrollment easier for users.</span></span> <span data-ttu-id="19175-129">CNAME レコードの登録が見つからない場合、ユーザーは手動で MDM サーバー名 enrollment.manage.microsoft.com を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="19175-129">If no enrollment CNAME record is found, users are prompted to manually enter the MDM server name, enrollment.manage.microsoft.com.</span></span>

<span data-ttu-id="19175-130">検証済みドメインが複数ある場合、ドメインごとに CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="19175-130">If there is more than one verified domain, create a CNAME record for each domain.</span></span> <span data-ttu-id="19175-131">CNAME リソース レコードには次の情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="19175-131">The CNAME resource records must contain the following information:</span></span>

<span data-ttu-id="19175-132">CNAME リソース レコードには次の情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="19175-132">CNAME resource records must have the following information:</span></span>

|<span data-ttu-id="19175-133">種類:</span><span class="sxs-lookup"><span data-stu-id="19175-133">TYPE</span></span>|<span data-ttu-id="19175-134">ホスト名</span><span class="sxs-lookup"><span data-stu-id="19175-134">Host name</span></span>|<span data-ttu-id="19175-135">指定先</span><span class="sxs-lookup"><span data-stu-id="19175-135">Points to</span></span>|<span data-ttu-id="19175-136">TTL</span><span class="sxs-lookup"><span data-stu-id="19175-136">TTL</span></span>|
|--------|-------------|-------------|-------|
|<span data-ttu-id="19175-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="19175-137">CNAME</span></span>|<span data-ttu-id="19175-138">EnterpriseEnrollment.company_domain.com</span><span class="sxs-lookup"><span data-stu-id="19175-138">EnterpriseEnrollment.company_domain.com</span></span>|<span data-ttu-id="19175-139">EnterpriseEnrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="19175-139">EnterpriseEnrollment-s.manage.microsoft.com</span></span> |<span data-ttu-id="19175-140">1 時間</span><span class="sxs-lookup"><span data-stu-id="19175-140">1 Hour</span></span>|
|<span data-ttu-id="19175-141">CNAME</span><span class="sxs-lookup"><span data-stu-id="19175-141">CNAME</span></span>|<span data-ttu-id="19175-142">EnterpriseRegistration.company_domain.com</span><span class="sxs-lookup"><span data-stu-id="19175-142">EnterpriseRegistration.company_domain.com</span></span>|<span data-ttu-id="19175-143">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="19175-143">EnterpriseRegistration.windows.net</span></span>|<span data-ttu-id="19175-144">1 時間</span><span class="sxs-lookup"><span data-stu-id="19175-144">1 Hour</span></span>|

<span data-ttu-id="19175-145">`EnterpriseEnrollment-s.manage.microsoft.com` – Intune サービスへのリダイレクトと電子メールのドメイン名によるドメイン認識をサポートします</span><span class="sxs-lookup"><span data-stu-id="19175-145">`EnterpriseEnrollment-s.manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name</span></span>

<span data-ttu-id="19175-146">会社でユーザーの資格情報に複数のドメインを使用する場合は、各ドメインに CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="19175-146">If your company uses multiple domains for user credentials, create CNAME records for each domain.</span></span>

<span data-ttu-id="19175-147">たとえば、会社の Web サイトが contoso.com の場合、EnterpriseEnrollment.contoso.com を EnterpriseEnrollment-s.manage.microsoft.com にリダイレクトする CNAME を DNS に作成します。DNS レコードの変更が反映されるまでには、最大で 72 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="19175-147">For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to EnterpriseEnrollment-s.manage.microsoft.com. Changes to DNS records might take up to 72 hours to propagate.</span></span> <span data-ttu-id="19175-148">DNS レコードの変更が反映されるまで、Intune で DNS の変更を確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="19175-148">You cannot verify the DNS change in Intune until the DNS record propagates.</span></span>

<span data-ttu-id="19175-149">**手順 2: CNAME を確認する** (省略可能)</span><span class="sxs-lookup"><span data-stu-id="19175-149">**Step 2: Verify CNAME** (optional)</span></span><br>
<span data-ttu-id="19175-150">[Intune 管理コンソール](https://manage.microsoft.com)で、**[管理]** &gt; **[モバイル デバイス管理]** &gt; **[Windows]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="19175-150">In the [Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **Mobile Device Management** &gt; **Windows**.</span></span> <span data-ttu-id="19175-151">**[検証済みドメイン名の指定]** ボックスに会社の Web サイトの検証済みドメインの URL を入力し、**[自動検出のテスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="19175-151">Enter the URL of the verified domain of the company website in the **Specify a verified domain name** box, and then choose **Test Auto-Detection**.</span></span>

## <a name="tell-users-how-to-enroll-windows-devices"></a><span data-ttu-id="19175-152">Windows デバイスの登録方法をユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="19175-152">Tell users how to enroll Windows devices</span></span>
<span data-ttu-id="19175-153">ユーザーに、Windows デバイスを登録する方法とデバイスが管理されるとどうなるかを伝えます。</span><span class="sxs-lookup"><span data-stu-id="19175-153">Tell your users how to enroll their Windows devices and what to expect after they're brought into management.</span></span>
<span data-ttu-id="19175-154">エンドユーザー用の登録手順については、「[Intune に Windows デバイスを登録する](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19175-154">For end-user enrollment instructions, see [Enroll your Windows device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows).</span></span> <span data-ttu-id="19175-155">また、ユーザーには、[IT 管理者がユーザーのデバイスに関して確認できる情報](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows)に関するページを案内してください。</span><span class="sxs-lookup"><span data-stu-id="19175-155">You can also send users to [What can my IT admin see on my device](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).</span></span>

<span data-ttu-id="19175-156">エンドユーザー タスクの詳細については、「[Microsoft Intune を使用したエンドユーザー エクスペリエンスに関するリソース](/intune/end-user-educate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19175-156">For more information about end-user tasks, see [Resources about the end-user experience with Microsoft Intune](/intune/end-user-educate).</span></span>

### <a name="see-also"></a><span data-ttu-id="19175-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="19175-157">See also</span></span>
[<span data-ttu-id="19175-158">Microsoft Intune でデバイスを登録するための前提条件</span><span class="sxs-lookup"><span data-stu-id="19175-158">Prerequisites for enrolling devices in Microsoft Intune</span></span>](prerequisites-for-enrollment.md)
