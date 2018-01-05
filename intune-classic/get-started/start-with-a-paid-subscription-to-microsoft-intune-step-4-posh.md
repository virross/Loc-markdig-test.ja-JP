---
title: "PowerShell を使用して Intune ライセンスを管理する"
description: "PowerShell を使用して Intune ライセンスを管理します"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2d31c80-c32c-4315-8271-1b0cf9a1f78a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 02973215a9dba6d975e23ca025b04554db8ca7f6
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="manage-intune-licenses-using-powershell"></a><span data-ttu-id="f55b9-103">PowerShell を使用して Intune ライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="f55b9-103">Manage Intune licenses using PowerShell</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f55b9-104">このトピックでは、管理者が PowerShell を使用して Intune のユーザー ライセンスを管理する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f55b9-104">This topic tells administrators how they use PowerShell to manage Intune user licenses.</span></span>

<span data-ttu-id="f55b9-105">Intune サービスにサインインして使用したり、デバイスを管理対象に登録したりするためには、「[Manage Intune licenses (Intune ライセンスの管理)](/intune/licenses-assign)」で説明されているとおり、先に各ユーザーに Intune サブスクリプションのライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f55b9-105">Before users can sign in to use the Intune service or enroll their devices into management, you must first assign each user a license to your Intune subscription, as described in [Manage Intune licenses](/intune/licenses-assign).</span></span> <span data-ttu-id="f55b9-106">ただし、Microsoft Enterprise Mobility + Security を使用している組織には、EMS パッケージの Azure Active Directory Premium または Intune サービスのみを必要とするユーザーがいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f55b9-106">However, organizations that use Microsoft Enterprise Mobility + Security might have users who only require Azure Active Directory Premium or Intune services in the EMS package.</span></span> <span data-ttu-id="f55b9-107">[Azure Active Directory PowerShell コマンドレット](https://msdn.microsoft.com/library/jj151815.aspx)を使用して、いずれかのサービスまたはサービスのサブセットを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f55b9-107">You can assign one or a subset of services using [Azure Active Directory PowerShell cmdlets](https://msdn.microsoft.com/library/jj151815.aspx).</span></span>

<span data-ttu-id="f55b9-108">EMS サービスのユーザー ライセンスを選択的に割り当てるには、[Azure Active Directory Module for Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) がインストールされているコンピューターで管理者として PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="f55b9-108">To selectively assign user licenses for EMS services, open PowerShell as an administrator on a computer with the [Azure Active Directory Module for Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installed.</span></span> <span data-ttu-id="f55b9-109">PowerShell は、ローカル コンピューターまたは ADFS サーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f55b9-109">You can install PowerShell on a local computer or on an ADFS server.</span></span>

<span data-ttu-id="f55b9-110">目的のサービス プランにのみ適用される新しいライセンス SKU 定義を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f55b9-110">You must create a new license SKU definition that applies only to the desired service plans.</span></span> <span data-ttu-id="f55b9-111">これを行うには、適用しないプランを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f55b9-111">To do this, disable the plans you don’t want to apply.</span></span> <span data-ttu-id="f55b9-112">たとえば、Intune ライセンスを割り当てないライセンス SKU 定義を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f55b9-112">For example, you might create a license SKU definition that does not assign an Intune license.</span></span> <span data-ttu-id="f55b9-113">利用できるサービスの一覧を確認するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f55b9-113">To see a list of available services, type:</span></span>

    (Get-MsolAccountSku | Where {$\_.SkuPartNumber -eq "EMS"}).ServiceStatus

<span data-ttu-id="f55b9-114">次のコマンドを実行すると、Intune サービス プランを除外できます。</span><span class="sxs-lookup"><span data-stu-id="f55b9-114">You can run the following command to exclude the Intune service plan.</span></span> <span data-ttu-id="f55b9-115">同じメソッドを使用して、セキュリティ グループ全体に展開することや、より詳細なフィルターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f55b9-115">You can use the same method to expand to an entire security group or you can use more granular filters.</span></span>

<span data-ttu-id="f55b9-116">**例 1** コマンド ラインで、新しいユーザーを作成し、ライセンスに含まれる Intune を有効にせずに EMS ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f55b9-116">**Example 1** Create a new user on the command line and assign an EMS license without enabling the Intune portion of the license:</span></span>

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


<span data-ttu-id="f55b9-117">次のコマンドで確認します。</span><span class="sxs-lookup"><span data-stu-id="f55b9-117">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

<span data-ttu-id="f55b9-118">**例 2** ライセンスが既に割り当てられているユーザーに対して、EMS ライセンスに含まれる Intune を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f55b9-118">**Example 2** Disable the Intune portion of EMS license for a user that is already assigned with a license:</span></span>

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

<span data-ttu-id="f55b9-119">次のコマンドで確認します。</span><span class="sxs-lookup"><span data-stu-id="f55b9-119">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### <a name="next-steps"></a><span data-ttu-id="f55b9-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="f55b9-121">Next steps</span></span>
<span data-ttu-id="f55b9-122">これで終了です。</span><span class="sxs-lookup"><span data-stu-id="f55b9-122">Congratulations!</span></span> <span data-ttu-id="f55b9-123">*Intune のクイック スタート ガイド*の手順 4 が完了しました。</span><span class="sxs-lookup"><span data-stu-id="f55b9-123">You have just completed step 4 of the *Intune quick start guide*.</span></span>
> [!div class="step-by-step"]
> <span data-ttu-id="f55b9-124">(/intune/custom-domain-name-configure) [&larr; **ユーザーを Intune に同期する**](/intune/custom-domain-name-configure) [**ユーザーとデバイスを整理する** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)</span><span class="sxs-lookup"><span data-stu-id="f55b9-124">(/intune/custom-domain-name-configure) [&larr; **Sync users to Intune**](/intune/custom-domain-name-configure)     [**Organize users and devices** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)</span></span>  
