---
title: "Intune のライセンスを割り当てる"
description: "Intune サブスクリプションのユーザーにライセンスを割り当てます"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1548d55e90fd8bdf22b3949c54bb2eeef5033a7f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="assign-intune-licenses-to-your-user-accounts"></a><span data-ttu-id="2d997-103">ユーザー アカウントに Intune のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2d997-103">Assign Intune licenses to your user accounts</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="2d997-104">ユーザーを手動で追加する場合も、オンプレミスの Active Directory から同期する場合も、まず各ユーザーに Intune のライセンスを割り当ててから、Intune にデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d997-104">Whether you manually add users or synchronize from your on-premises Active Directory, you must first assign each user an Intune license before users can enroll their devices in Intune.</span></span>

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a><span data-ttu-id="2d997-105">Office 365 管理センターで、Intune のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2d997-105">Assign an Intune license in the Office 365 Admin center</span></span>

<span data-ttu-id="2d997-106">[Office 365 ポータル](http://go.microsoft.com/fwlink/p/?LinkId=698854)を使用して、手動でクラウドベースのユーザーを追加し、クラウドベースのユーザー アカウントと、オンプレミスの Active Directory から Azure AD に同期されているアカウントの両方にライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2d997-106">You can use the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) to manually add cloud-based users and assign licenses to both cloud-based user accounts and accounts synchronized from your on-premises Active Directory to Azure AD.</span></span>

1.  <span data-ttu-id="2d997-107">テナント管理者の資格情報を使用して [Office 365 ポータル](http://go.microsoft.com/fwlink/p/?LinkId=698854)にサインインした後、**[ユーザー]** > **[アクティブ ユーザー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2d997-107">Sign in to the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) using your tenant administrator credentials, and then choose **Users** > **Active Users**.</span></span>

2.  <span data-ttu-id="2d997-108">Intune ユーザー ライセンスを割り当てるユーザー アカウントを選択し、**[製品ライセンス]** > **[編集]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2d997-108">Select the user account that you want to assign an Intune user license to, and then choose **Product licenses** > **Edit**.</span></span>

3.  <span data-ttu-id="2d997-109">**Intune** または **Enterprise Mobility + Security** を **[オン]** に切り替えて、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d997-109">Toggle **Intune** or **Enterprise Mobility + Security** to **On**, and choose **Save**.</span></span>

  ![Office 365 ポータルの製品ライセンス割り当ての画像。](./media/office-assign-license.png)

4. <span data-ttu-id="2d997-111">ユーザー アカウントが、サービスを使用してデバイスを管理に登録するために必要なアクセス許可を持つようになります。</span><span class="sxs-lookup"><span data-stu-id="2d997-111">The user account now has the permissions needed to use the service and enroll devices into management.</span></span>

> [!NOTE]
> <span data-ttu-id="2d997-112">デバイスを登録すると、管理コンソールにユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d997-112">Users will appear in the Admin console only after they have enrolled a device.</span></span> <span data-ttu-id="2d997-113">また、編集するユーザーのグループを一度に選択して、選択したすべてのユーザーに対してライセンスを追加したり交換することができます。</span><span class="sxs-lookup"><span data-stu-id="2d997-113">Also, you can select a group of users to edit at once,  either selecting to add or replace a license for all selected users.</span></span>

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a><span data-ttu-id="2d997-114">School Data Sync を使って Intune for Education のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2d997-114">Use School Data Sync to assign licenses to users in Intune for Education</span></span>
<span data-ttu-id="2d997-115">教育組織の場合、School Data Sync (SDS) を使用して Intune for Education のライセンスを同期されたユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2d997-115">If you are an educational organization, you can use School Data Sync (SDS) to assign Intune for Education licenses to synced users.</span></span> <span data-ttu-id="2d997-116">SDS プロファイルを設定するときに、Intune for Education のチェック ボックスをオンにするだけです。</span><span class="sxs-lookup"><span data-stu-id="2d997-116">Just choose the Intune for Education checkbox when you're setting up your SDS profile.</span></span>  

![SDS プロファイル設定の画像](./media/i4e-sds-profile-setup-setting.png)

<span data-ttu-id="2d997-118">Intune for Education のライセンスを割り当てるときは、Intune A Direct のライセンスも割り当てられることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2d997-118">When you assign an Intune for Education license, make sure that Intune A Direct license is also assigned.</span></span>

![製品ライセンス設定の画像](./media/i4e-set-licenses.png)

<span data-ttu-id="2d997-120">SDS について詳しくは、「[School Data Sync と Classroom の概要](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d997-120">See this [overview of School Data Sync](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US) to learn more about SDS.</span></span>

## <a name="how-user-and-device-licenses-affect-access-to-services"></a><span data-ttu-id="2d997-121">ユーザー ライセンスとデバイス ライセンスがサービスへのアクセスに与える影響</span><span class="sxs-lookup"><span data-stu-id="2d997-121">How user and device licenses affect access to services</span></span>
* <span data-ttu-id="2d997-122">ユーザー ソフトウェア ライセンスが割り当てられた各**ユーザー**は、オンライン サービスと関連するソフトウェア (System Center ソフトウェアを含む) にアクセスしてそれらを使用し、複数のアプリケーションと最大 15 台のデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2d997-122">Each **user** that you assign a user software license to may access and use the online services and related software (including System Center software) to manage applications and up to 15 devices.</span></span>
* <span data-ttu-id="2d997-123">デバイス ソフトウェア ライセンスが割り当てられた各**デバイス**は、オンライン サービスと関連するソフトウェア (System Center ソフトウェアを含む) にアクセスしてそれらを使用することができます。使用するユーザー数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="2d997-123">Each **device** that you assign a device software license to may access and use the online services and related software (including System Center software) for use by any number of users.</span></span>
* <span data-ttu-id="2d997-124">デバイスが 2 人以上のユーザーによって使用される場合は、各デバイスにデバイス ソフトウェア ライセンス、またはすべてのユーザーにユーザー ソフトウェア ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2d997-124">If a device is used by more than one user, each requires a device software license or all users require a user software license.</span></span>

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a><span data-ttu-id="2d997-125">PowerShell を使用して、EMS ユーザー ライセンスを選択的に管理する</span><span class="sxs-lookup"><span data-stu-id="2d997-125">Use PowerShell to selectively manage EMS user licenses</span></span>
<span data-ttu-id="2d997-126">Microsoft Enterprise Mobility + Security (旧 Enterprise Mobility Suite) を使用している組織には、EMS パッケージの Azure Active Directory Premium または Intune サービスのみを必要とするユーザーがいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d997-126">Organizations that use Microsoft Enterprise Mobility + Security (formerly Enterprise Mobility Suite) might have users who only require Azure Active Directory Premium or Intune services in the EMS package.</span></span> <span data-ttu-id="2d997-127">[Azure Active Directory PowerShell コマンドレット](https://msdn.microsoft.com/library/jj151815.aspx)を使用して、いずれかのサービスまたはサービスのサブセットを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2d997-127">You can assign one or a subset of services using [Azure Active Directory PowerShell cmdlets](https://msdn.microsoft.com/library/jj151815.aspx).</span></span>

<span data-ttu-id="2d997-128">EMS サービスのユーザー ライセンスを選択的に割り当てるには、[Azure Active Directory Module for Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) がインストールされているコンピューターで管理者として PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="2d997-128">To selectively assign user licenses for EMS services, open PowerShell as an administrator on a computer with the [Azure Active Directory Module for Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installed.</span></span> <span data-ttu-id="2d997-129">PowerShell は、ローカル コンピューターまたは ADFS サーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2d997-129">You can install PowerShell on a local computer or on an ADFS server.</span></span>

<span data-ttu-id="2d997-130">目的のサービス プランにのみ適用される新しいライセンス SKU 定義を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d997-130">You must create a new license SKU definition that applies only to the desired service plans.</span></span> <span data-ttu-id="2d997-131">これを行うには、適用しないプランを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d997-131">To do this, disable the plans you don’t want to apply.</span></span> <span data-ttu-id="2d997-132">たとえば、Intune ライセンスを割り当てないライセンス SKU 定義を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2d997-132">For example, you might create a license SKU definition that does not assign an Intune license.</span></span> <span data-ttu-id="2d997-133">利用できるサービスの一覧を確認するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="2d997-133">To see a list of available services, type:</span></span>

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

<span data-ttu-id="2d997-134">次のコマンドを実行すると、Intune サービス プランを除外できます。</span><span class="sxs-lookup"><span data-stu-id="2d997-134">You can run the following command to exclude the Intune service plan.</span></span> <span data-ttu-id="2d997-135">同じメソッドを使用して、セキュリティ グループ全体に展開することや、より詳細なフィルターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2d997-135">You can use the same method to expand to an entire security group or you can use more granular filters.</span></span>

<span data-ttu-id="2d997-136">**例 1**</span><span class="sxs-lookup"><span data-stu-id="2d997-136">**Example 1**</span></span><br>
<span data-ttu-id="2d997-137">コマンド ラインで、新しいユーザーを作成し、ライセンスに含まれる Intune を有効にせずに EMS ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2d997-137">Create a new user on the command line and assign an EMS license without enabling the Intune portion of the license:</span></span>

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


<span data-ttu-id="2d997-138">次のコマンドで確認します。</span><span class="sxs-lookup"><span data-stu-id="2d997-138">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

<span data-ttu-id="2d997-139">**例 2**</span><span class="sxs-lookup"><span data-stu-id="2d997-139">**Example 2**</span></span><br>
<span data-ttu-id="2d997-140">ライセンスが既に割り当てられているユーザーに対して、EMS ライセンスに含まれる Intune を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d997-140">Disable the Intune portion of EMS license for a user that is already assigned with a license:</span></span>

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

<span data-ttu-id="2d997-141">次のコマンドで確認します。</span><span class="sxs-lookup"><span data-stu-id="2d997-141">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)
