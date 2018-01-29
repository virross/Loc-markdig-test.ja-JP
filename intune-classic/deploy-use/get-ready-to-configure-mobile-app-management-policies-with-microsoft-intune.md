---
title: "MAM ポリシーの前提条件"
description: "このトピックでは、モバイル アプリ管理ポリシーを作成する前にユーザーを設定するための前提条件について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 87ba375906d115a4d543f8a37f822d94ccc0debd
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="get-ready-to-configure-app-protection-policies-in-the-azure-portal"></a><span data-ttu-id="0b5d7-103">Azure ポータルでアプリ保護ポリシーを構成する準備をする</span><span class="sxs-lookup"><span data-stu-id="0b5d7-103">Get ready to configure app protection policies in the Azure portal</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="0b5d7-104">このトピックでは、Azure ポータルでアプリ保護ポリシーを作成する**前に**完了しておく必要がある前提条件と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-104">This topic describes the prerequisites and the steps you must complete **before** you can create app protection policies in the Azure portal.</span></span>

<span data-ttu-id="0b5d7-105">Intune アプリ保護ポリシーで会社のデータを守る方法については、[アプリ保護ポリシーを使用したアプリとデータの保護](protect-apps-and-data-with-microsoft-intune.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-105">To understand how Intune app protection policies can protect your company data, see [Protect apps and data using app protection policies](protect-apps-and-data-with-microsoft-intune.md).</span></span>

## <a name="what-is-the-azure-portal"></a><span data-ttu-id="0b5d7-106">Azure ポータルとは?</span><span class="sxs-lookup"><span data-stu-id="0b5d7-106">What is the Azure portal?</span></span>

<span data-ttu-id="0b5d7-107">Azure ポータルはアプリ保護ポリシーを作成するための新しい管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-107">The Azure portal is the new admin console for creating app protection policies.</span></span> <span data-ttu-id="0b5d7-108">Azure Portal では、次の MAM シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-108">It supports the following MAM scenarios:</span></span>
- <span data-ttu-id="0b5d7-109">Intune に登録されたデバイス</span><span class="sxs-lookup"><span data-stu-id="0b5d7-109">Devices that are enrolled in Intune</span></span>
- <span data-ttu-id="0b5d7-110">別のモバイル デバイス管理 (MDM) ソリューションによって管理されるデバイス</span><span class="sxs-lookup"><span data-stu-id="0b5d7-110">Devices that are managed by another Mobile Device Management (MDM) solution</span></span>
- <span data-ttu-id="0b5d7-111">MDM ソリューションで管理されないデバイス (BYOD)</span><span class="sxs-lookup"><span data-stu-id="0b5d7-111">Devices that are not managed by any MDM solution (BYOD)</span></span>

<span data-ttu-id="0b5d7-112">現在のところ、**Intune 管理者コンソール**と **Azure ポータル**の両方でアプリ保護ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-112">Currently, both the **Intune administrator console** and the **Azure portal** enable you to configure app protection policies.</span></span>  <span data-ttu-id="0b5d7-113">次の点を考慮します。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-113">Consider the following:</span></span>

* <span data-ttu-id="0b5d7-114">**Azure Portal**  で作成するポリシーは、上記の**すべての MAM シナリオ**でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-114">The policies that you create on the **Azure portal** are supported for **all MAM scenarios** that are listed previously.</span></span> <span data-ttu-id="0b5d7-115">**Intune 管理者コンソール**は、**Intune で登録し、管理するデバイス**のポリシー作成にのみ対応しています。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-115">The **Intune administrator console** only supports creating policies for **devices that are enrolled and managed by Intune**.</span></span>

* <span data-ttu-id="0b5d7-116">**新しい設定**は **Azure ポータル**にのみ追加できるため、一部のアプリ ポリシー設定は Intune 管理者コンソールに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-116">You might not see all app policy settings in the Intune administrator console because **new settings** can only be added to the **Azure portal**.</span></span>

* <span data-ttu-id="0b5d7-117">Intune 管理コンソールと Azure ポータルの**両方**でアプリ保護ポリシーを作成した場合、**Azure ポータルのポリシーがアプリに適用され、ユーザーにデプロイされます**。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-117">If you create app protection policies in **both** the Intune admin console and the Azure portal, the policy in the **Azure portal is applied to the apps and deployed to users**.</span></span>
    * <span data-ttu-id="0b5d7-118">Intune 管理コンソールで作成したアプリ保護ポリシーを Azure ポータルにインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-118">App protection policies that are created in the Intune admin console cannot be imported into the Azure portal.</span></span>  <span data-ttu-id="0b5d7-119">Azure ポータルでアプリ保護ポリシーを作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-119">The app protection policies must be re-created in the Azure portal.</span></span>


* <span data-ttu-id="0b5d7-120">アプリやアプリ構成ポリシーの展開などの、**他のアプリ管理機能**は、現在のところ、**Intune 管理コンソール**でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-120">Other **app management features**, such as deploying apps and app configuration policies, are currently only available in the **Intune administrator console**.</span></span>


<span data-ttu-id="0b5d7-121">初めて Azure ポータルを使用する場合は、[Azure ポータルの Microsoft Intune アプリ保護ポリシー対応](azure-portal-for-microsoft-intune-mam-policies.md)に関する記事で Azure ポータルの基本をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-121">If you are new to the Azure portal, read [Azure portal for Microsoft Intune app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) to get the basics of using the Azure portal.</span></span>

<span data-ttu-id="0b5d7-122">Intune 管理コンソールでアプリ ポリシーを作成する方法については、[Microsoft Intune コンソールでのアプリ保護ポリシーの構成とデプロイ](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-122">For instructions about how to create an app policy on the Intune admin console, see [Configure and deploy app protection policies in the Microsoft Intune console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).</span></span>


##  <a name="supported-platforms"></a><span data-ttu-id="0b5d7-123">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="0b5d7-123">Supported platforms</span></span>
- <span data-ttu-id="0b5d7-124">iOS 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="0b5d7-124">iOS 8.1 or later</span></span>
- <span data-ttu-id="0b5d7-125">Android 4 以降</span><span class="sxs-lookup"><span data-stu-id="0b5d7-125">Android 4 or later</span></span>
- <span data-ttu-id="0b5d7-126">Windows 10</span><span class="sxs-lookup"><span data-stu-id="0b5d7-126">Windows 10</span></span>

>[!NOTE]
><span data-ttu-id="0b5d7-127">バージョン 1703 より、アプリの保護ポリシーを、MAM に登録シナリオなしで Windows 10 デバイスに対して定義することができます。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-127">Beginning with version 1703, app protection policies can be defined for Windows 10 devices in the MAM without enrollment scenario.</span></span> <span data-ttu-id="0b5d7-128">詳細については、「[Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)」 (Windows 情報保護 (WIP) を使用してエンタープライズ データを保護する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-128">For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>

##  <a name="supported-apps"></a><span data-ttu-id="0b5d7-129">サポートされているアプリ</span><span class="sxs-lookup"><span data-stu-id="0b5d7-129">Supported apps</span></span>
* <span data-ttu-id="0b5d7-130">**Microsoft アプリ:** これらのアプリには Intune App SDK が組み込まれているので、アプリ保護ポリシーを適用する前に必要な処理はありません。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-130">**Microsoft apps:** These apps have the Intune App SDK built in and require no further processing before you apply app protection policies.</span></span>
<span data-ttu-id="0b5d7-131">サポートされている Microsoft アプリの完全な一覧については、Microsoft Intune アプリケーション パートナー ページの [Microsoft Intune モバイル アプリケーション ギャラリー](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-131">To see the full list of supported Microsoft apps, go to the [Microsoft Intune mobile application gallery](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) on the Microsoft Intune application partners page.</span></span> <span data-ttu-id="0b5d7-132">アプリをクリックし、サポートされるシナリオ、プラットフォーム、アプリのマルチ ID 対応について確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-132">Click an app to see the supported scenarios and platforms, and to see whether the app supports multiple identities.</span></span>

* <span data-ttu-id="0b5d7-133">**社内で構築した基幹業務アプリ:** アプリ保護ポリシーを適用する前に、Intune App SDK を含めるようにアプリを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-133">**Your organization's line-of-business apps:** You must prepare these apps to include the Intune App SDK before you can apply app protection policies.</span></span>

  * <span data-ttu-id="0b5d7-134">Intune で管理されているデバイスについては、「[Decide how to prepare apps for MAM](/intune/apps-prepare-mobile-application-management)」 (MAM 用にアプリを準備する方法を決める) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-134">For devices that are managed by Intune, see [Decide how to prepare apps for MAM](/intune/apps-prepare-mobile-application-management).</span></span>

  * <span data-ttu-id="0b5d7-135">従業員が所有するデバイスなど管理対象ではないデバイスや、別のモバイル デバイス管理ソリューションで管理されているデバイスの場合は、「[Microsoft Intune に登録されていないデバイスの基幹業務アプリとデータを保護する](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-135">For devices that are not managed (such as employee-owned devices), or for devices that are managed by another mobile device management solution, see [Protect line-of-business apps and data on devices not enrolled in Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0b5d7-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="0b5d7-136">Prerequisites</span></span>

- <span data-ttu-id="0b5d7-137">**Microsoft Intune サブスクリプション**。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-137">**A Microsoft Intune subscription**.</span></span> <span data-ttu-id="0b5d7-138">アプリ保護ポリシーが適用されているアプリを入手するには、Intune ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-138">Users need Intune licenses to get apps that have app protection policies.</span></span>
  <span data-ttu-id="0b5d7-139">デバイスを管理するために現在 Intune を使用している場合、既に Intune サブスクリプションを所有していることになります。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-139">You   already have an Intune subscription if you are currently using Intune to manage your devices.</span></span> <span data-ttu-id="0b5d7-140">Enterprise Mobility Suite (EMS) ライセンスを購入している場合も、Intune サブスクリプションを所有しています。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-140">You also have an Intune subscription if you have purchased an Enterprise Mobility Suite (EMS) license.</span></span> <span data-ttu-id="0b5d7-141">MAM 機能を調べるために Intune を試してみる場合は、試用アカウントを [Microsoft Intune Web ページ](https://www.microsoft.com/server-cloud/products/microsoft-intune/)から取得できます。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-141">If you are trying Intune to check out the MAM capabilities, you can get a trial account on the [Microsoft Intune page](https://www.microsoft.com/server-cloud/products/microsoft-intune/).</span></span>

  <span data-ttu-id="0b5d7-142">自分が Intune サブスクリプションを所有しているかどうかを確認するには、Office ポータルの**課金情報**のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-142">To verify if you have an Intune subscription, in the Office portal, go to the **Billing** page.</span></span>  <span data-ttu-id="0b5d7-143">サブスクリプションを所有している場合は、Intune が **Active** になっているはずです。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-143">If you have a subscription, you should see Intune as **Active** in the subscriptions.</span></span>

- <span data-ttu-id="0b5d7-144">**Office 365 サブスクリプション**。これは、以下で必要となります。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-144">**An Office 365 subscription**, which is required for the following:</span></span>

  - <span data-ttu-id="0b5d7-145">複数の ID をサポートするアプリにアプリ保護ポリシーを適用する。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-145">To apply app protection policies to apps with multiple-identity support.</span></span>

  - <span data-ttu-id="0b5d7-146">SharePoint Online および Exchange Online 作業アカウントを作成する。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-146">To create SharePoint Online and Exchange Online work accounts.</span></span> <span data-ttu-id="0b5d7-147">Exchange On-Premises と SharePoint On-Premises はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-147">Exchange on-premises and SharePoint on-premises are not supported.</span></span>

- <span data-ttu-id="0b5d7-148">**Skype for Business Online の先進認証の設定**。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-148">**Skype for Business Online setup for modern authentication**.</span></span> <span data-ttu-id="0b5d7-149">詳細については、「[Enable modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)」 (先進認証の有効化) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-149">For more information, see [Enable modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>


- <span data-ttu-id="0b5d7-150">ユーザーを作成するための Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-150">Azure Active Directory (Azure AD) to create users.</span></span> <span data-ttu-id="0b5d7-151">Azure AD では、ユーザーがアプリを開いて作業用の資格情報を入力するときに、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-151">Azure AD authenticates users when they open the app and enter their work credentials.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b5d7-152">ユーザー グループは Azure AD で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-152">User groups must be set up in Azure AD.</span></span> <span data-ttu-id="0b5d7-153">Azure ポータルで Intune ユーザー グループを利用してアプリ保護ポリシーをデプロイすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-153">Intune user groups cannot be used to deploy app protection policies in the Azure portal.</span></span>

### <a name="create-users-and-assign-microsoft-intune-licenses"></a><span data-ttu-id="0b5d7-154">ユーザーの作成と Microsoft Intune ライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="0b5d7-154">Create users and assign Microsoft Intune licenses</span></span>

1.  <span data-ttu-id="0b5d7-155">管理者資格情報で [Office ポータル](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-155">Sign in to the [Office portal](https://portal.office.com) with your admin credentials.</span></span>

2.  <span data-ttu-id="0b5d7-156">[Intune の評価ガイド](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune)の、**Intune の 30 日間評価版の完了手順**のセクションにある説明に従ってユーザーを追加して、Intune ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-156">Add users as described in the **Steps to complete a 30-day evaluation of Intune** section of the [Intune evaluation guide](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune), and then assign Intune licenses.</span></span> <span data-ttu-id="0b5d7-157">ユーザーが Office ポータル、Azure AD ポータル、Azure ポータルにアクセスできるようにするには、**全体管理者ロール**をユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-157">To give a user the ability to access the Office portal, the Azure AD portal, and the Azure  portal, assign the **Global administrator** role to the user.</span></span>

5.  <span data-ttu-id="0b5d7-158">アプリ保護ポリシーは、Azure Active Directory のユーザー グループにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-158">App protection policies are deployed to user groups in Azure Active Directory.</span></span> <span data-ttu-id="0b5d7-159">アプリ保護ポリシーのユーザー グループを作成するには、「[評価版のサブスクリプションのユーザーとデバイスを編成するグループを作成する](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3)」の「**ユーザー グループを作成する**」セクションの説明にあるようにユーザー グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-159">To create user groups for your app protection policies, create a user group as described in the **Create a user group** section of [Create groups to organize evaluation subscription users and devices](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).</span></span>

### <a name="assign-roles-to-non-global-admin-users"></a><span data-ttu-id="0b5d7-160">グローバル管理者でないユーザーにロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0b5d7-160">Assign roles to non-global admin users</span></span>

<span data-ttu-id="0b5d7-161">全体管理者には [Azure ポータル](https://portal.azure.com)へのアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-161">Global administrators have access to the [Azure portal](https://portal.azure.com).</span></span>  <span data-ttu-id="0b5d7-162">グローバル管理者ではないユーザーもポリシーを構成して他のモバイル アプリ管理タスクを実行できるようにする場合は、「[Azure サブスクリプション リソースへのアクセスをロールの割り当てによって管理する](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/)」の記事をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="0b5d7-162">If you want users who are not global administrators to be able to configure policies and do other mobile app management tasks, check the [Use role assignments to manage access to your Azure subscription resources](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/) article.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0b5d7-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="0b5d7-163">Next steps</span></span>
[<span data-ttu-id="0b5d7-164">Microsoft Intune でのアプリ保護ポリシーの作成とデプロイ</span><span class="sxs-lookup"><span data-stu-id="0b5d7-164">Create and deploy app protection policies with Microsoft Intune</span></span>](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
