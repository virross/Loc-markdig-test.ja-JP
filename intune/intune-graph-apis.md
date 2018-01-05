---
title: "Azure AD を使用して Intune Graph API にアクセスする方法"
description: "アプリで Azure AD を使用して Intune Graph API にアクセスするために必要な手順について説明します"
keywords: "intune graphapi c# powershell アクセス許可の役割"
author: vhorne
manager: angrobe
ms.author: victorh
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 79A67342-C06D-4D20-A447-678A6CB8D70A
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f03898fde9ce7d90bb8dee862247cb768af6c4c8
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-use-azure-ad-to-access-the-intune-graph-api"></a><span data-ttu-id="c5674-104">Azure AD を使用して Intune Graph API にアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="c5674-104">How to use Azure AD to access the Intune Graph API</span></span>

<span data-ttu-id="c5674-105">[Microsoft Graph API](https://developer.microsoft.com/graph/) が Microsoft Intune に対応し、固有の API とアクセス許可の役割を利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c5674-105">The [Microsoft Graph API](https://developer.microsoft.com/graph/) now supports Microsoft Intune with specific APIs and permission roles.</span></span>  <span data-ttu-id="c5674-106">Graph API は、認証とアクセスの制御に Azure Active Directory (Azure AD) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5674-106">The Graph API uses Azure Active Directory (Azure AD) for authentication and access control.</span></span>  
<span data-ttu-id="c5674-107">Intune Graph API へのアクセスには以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="c5674-107">Access to the Intune Graph API requires:</span></span>

- <span data-ttu-id="c5674-108">アプリケーション ID と、</span><span class="sxs-lookup"><span data-stu-id="c5674-108">An application ID with:</span></span>

    - <span data-ttu-id="c5674-109">Azure AD および Graph API を呼び出すアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="c5674-109">Permission to call Azure AD and Graph APIs.</span></span>
    - <span data-ttu-id="c5674-110">特定のアプリケーション タスクに関連したアクセス許可スコープ。</span><span class="sxs-lookup"><span data-stu-id="c5674-110">Permission scopes relevant to the specific application tasks.</span></span>

- <span data-ttu-id="c5674-111">ユーザー資格情報と、</span><span class="sxs-lookup"><span data-stu-id="c5674-111">User credentials with:</span></span>

    - <span data-ttu-id="c5674-112">アプリケーションに関連付けられている Azure AD テナントへのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="c5674-112">Permission to access the Azure AD tenant associated with the application.</span></span>
    - <span data-ttu-id="c5674-113">アプリケーションのアクセス許可スコープをサポートするために必要な役割のアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="c5674-113">Role permissions required to support the application permission scopes.</span></span>

- <span data-ttu-id="c5674-114">Azure テナントのアプリケーション タスク実行に必要なアクセス許可をアプリに付与するエンド ユーザー。</span><span class="sxs-lookup"><span data-stu-id="c5674-114">The end user to grant permission to the app to perform applications tasks for their Azure tenant.</span></span>

<span data-ttu-id="c5674-115">この記事の内容:</span><span class="sxs-lookup"><span data-stu-id="c5674-115">This article:</span></span>

- <span data-ttu-id="c5674-116">Graph API と関連するアクセス許可の役割にアクセスできるアプリケーションを登録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5674-116">Shows how to register an application with access to the Graph API and relevant permission roles.</span></span>

- <span data-ttu-id="c5674-117">Intune Graph API のアクセス許可の役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5674-117">Describes the Intune Graph API permission roles.</span></span>

- <span data-ttu-id="c5674-118">C# および PowerShell の Intune Graph API 認証例を提供します。</span><span class="sxs-lookup"><span data-stu-id="c5674-118">Provides Intune Graph API authentication examples for C# and PowerShell.</span></span>

- <span data-ttu-id="c5674-119">複数のテナントをサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5674-119">Describes how to support multiple tenants</span></span>

<span data-ttu-id="c5674-120">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5674-120">To learn more, see:</span></span>

- [<span data-ttu-id="c5674-121">OAuth 2.0 と Azure Active Directory を使用した Web アプリケーションへのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="c5674-121">Authorize access to web applications using OAuth 2.0 and Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)
- [<span data-ttu-id="c5674-122">Azure AD 認証の概要</span><span class="sxs-lookup"><span data-stu-id="c5674-122">Getting start with Azure AD authentication</span></span>](https://www.visualstudio.com/docs/integrate/get-started/auth/oauth)
- [<span data-ttu-id="c5674-123">Azure Active Directory とアプリケーションの統合</span><span class="sxs-lookup"><span data-stu-id="c5674-123">Integrating applications with Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)
- [<span data-ttu-id="c5674-124">OAuth 2.0 について知る</span><span class="sxs-lookup"><span data-stu-id="c5674-124">Understand OAuth 2.0</span></span>](https://oauth.net/2/)

## <a name="register-apps-to-use-graph-api"></a><span data-ttu-id="c5674-125">Graph API を使用するアプリを登録する</span><span class="sxs-lookup"><span data-stu-id="c5674-125">Register apps to use Graph API</span></span>

<span data-ttu-id="c5674-126">Graph API を使用するアプリを登録するには、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="c5674-126">To register an app to use Graph API:</span></span>

1.  <span data-ttu-id="c5674-127">管理者資格情報を使って、[Azure Portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c5674-127">Sign into [the Azure portal](https://portal.azure.com) using administrative credentials.</span></span>

    <span data-ttu-id="c5674-128">必要に応じて、次を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c5674-128">As appropriate, you may use:</span></span>
    - <span data-ttu-id="c5674-129">テナントの管理者アカウント。</span><span class="sxs-lookup"><span data-stu-id="c5674-129">The tenant admin account.</span></span>
    - <span data-ttu-id="c5674-130">**[ユーザーはアプリケーションを登録できる]** の設定が有効になっている、テナントのユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="c5674-130">A tenant user account with the **Users can register applications** setting enabled.</span></span>

2.  <span data-ttu-id="c5674-131">メニューで、**[Azure Active Directory]** &gt; **[アプリの登録]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-131">From the menu, choose **Azure Active Directory** &gt; **App Registrations**.</span></span>

    <img src="./media/azure-ad-app-reg.png" width="157" height="170" alt="The App registrations menu command" />

3.  <span data-ttu-id="c5674-132">**[新しいアプリケーションの登録]** を選択して新しいアプリケーションを作成するか、または既存のアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-132">Either choose **New application registration** to create a new application or choose an existing application.</span></span>  <span data-ttu-id="c5674-133">(既存のアプリケーションを選択した場合は、次の手順をスキップします。)</span><span class="sxs-lookup"><span data-stu-id="c5674-133">(If you choose an existing application, skip the next step.)</span></span>

4.  <span data-ttu-id="c5674-134">**[作成]** ブレードで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5674-134">On the **Create** blade, specify the following:</span></span>

    1.  <span data-ttu-id="c5674-135">アプリケーションの **[名前]**\(ユーザーがサインインするときに表示されます\)。</span><span class="sxs-lookup"><span data-stu-id="c5674-135">A **Name** for the application (displayed when users sign in).</span></span>

    2.  <span data-ttu-id="c5674-136">**[アプリケーションの種類]** と **[リダイレクト URI]** の値。</span><span class="sxs-lookup"><span data-stu-id="c5674-136">The **Application type** and **Redirect URI** values.</span></span>

        <span data-ttu-id="c5674-137">これらは要件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c5674-137">These vary according to your requirements.</span></span> <span data-ttu-id="c5674-138">たとえば Azure AD [Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL) を使用している場合、**[アプリケーションの種類]** は `Native` に、**[リダイレクト URI]** は `urn:ietf:wg:oauth:2.0:oob` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c5674-138">For example, if you're using an Azure AD [Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL), set **Application Type** to `Native` and **Redirect URI** to `urn:ietf:wg:oauth:2.0:oob`.</span></span>

        <img src="media/azure-ad-app-new.png" width="209" height="140" alt="New app properties and values" />

        <span data-ttu-id="c5674-139">詳細については、「[Azure AD の認証シナリオ](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c5674-139">To learn more, see [Authentication Scenarios for Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span></span>

5.  <span data-ttu-id="c5674-140">[アプリケーション] ブレードで、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="c5674-140">From the application blade:</span></span>

    1.  <span data-ttu-id="c5674-141">**[アプリケーション ID]** の値をメモします。</span><span class="sxs-lookup"><span data-stu-id="c5674-141">Note the **Application ID** value.</span></span>

    2.  <span data-ttu-id="c5674-142">**[設定]** &gt; **[API アクセス]** &gt; **[必要なアクセス許可]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-142">Choose **Settings** &gt; **API access** &gt; **Required permissions**.</span></span>

    <img src="media/azure-ad-req-perm.png" width="483" height="186" alt="The Required permissions setting" />

6.  <span data-ttu-id="c5674-143">**[必要なアクセス許可]** ブレードで、**[追加]** &gt; **[API アクセスの追加]** &gt; **[API を選択します]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-143">From the **Required Permissions** blade, choose **Add** &gt; **Add API access** &gt; **Select an API**.</span></span>

    <img src="media/azure-ad-add-graph.png" width="436" height="140" alt="The Microsoft Graph setting" />

7.  <span data-ttu-id="c5674-144">**[API を選択します]** ブレードで、**[Microsoft Graph]** &gt; **[選択]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-144">From the **Select an API** blade, choose **Microsoft Graph** &gt; **Select**.</span></span>  <span data-ttu-id="c5674-145">**[アクセスの有効化]** ブレードが開き、アプリケーションで使用できるアクセス許可スコープが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5674-145">The **Enable access** blade opens and lists permission scopes available to your application.</span></span>

    <img src="media/azure-ad-perm-scopes.png" width="489" height="248" alt="Intune Graph API permission scopes" />

    <span data-ttu-id="c5674-146">関連する名前の左側にチェックを入れ、アプリに必要な役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-146">Choose the roles required for your app by placing a checkmark to the left of the relevant names.</span></span>  <span data-ttu-id="c5674-147">Intune に固有のアクセス許可スコープの詳細については、「[Intune permission scopes (Intune のアクセス許可スコープ)](#user-content-intune-permission-scopes)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c5674-147">To learn about specific Intune permission scopes, see [Intune permission scopes](#user-content-intune-permission-scopes).</span></span>  <span data-ttu-id="c5674-148">Graph API の他のアクセス許可スコープの詳細については、「[Microsoft Graph のアクセス許可のリファレンス](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c5674-148">To learn about other Graph API permission scopes, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>

    <span data-ttu-id="c5674-149">最善の結果を得るには、アプリケーションの実装に必要な最小限の役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-149">For best results, choose the fewest roles needed to implement your application.</span></span>

    <span data-ttu-id="c5674-150">完了したら、**[選択]** と **[完了]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c5674-150">When finished, choose **Select** and **Done** to save you changes.</span></span>

<span data-ttu-id="c5674-151">この時点で、次も実行できます。</span><span class="sxs-lookup"><span data-stu-id="c5674-151">At this point, you may also:</span></span>

- <span data-ttu-id="c5674-152">すべてのテナント アカウントに、資格情報を入力せずにアプリを使用するアクセス許可を付与することを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-152">Choose to grant permission for all tenant accounts to use the app without providing credentials.</span></span>  

    <span data-ttu-id="c5674-153">これを実行するには、**[アクセス許可の付与]** を選択し、確認プロンプトに同意します。</span><span class="sxs-lookup"><span data-stu-id="c5674-153">To do so, choose **Grant permissions** and accept the confirmation prompt.</span></span>

    <span data-ttu-id="c5674-154">初めてアプリケーションを実行すると、選択した役割を実行できるアクセス許可をアプリに付与するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c5674-154">When you run the application for the first time, you're prompted to grant the app permission to perform the selected roles.</span></span>

    <img src="media/azure-ad-grant-perm.png" width="351" height="162" alt="The Grant permissions button" />

- <span data-ttu-id="c5674-155">テナントの外部ユーザーがアプリを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c5674-155">Make the app available to users outside your tenant.</span></span>  <span data-ttu-id="c5674-156">(これは通常、複数のテナント/組織をサポートするパートナーにのみ必要です。)</span><span class="sxs-lookup"><span data-stu-id="c5674-156">(This is typically only required for partners supporting multiple tenants/organizations.)</span></span>  

    <span data-ttu-id="c5674-157">これを実行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c5674-157">To do so:</span></span>

  1. <span data-ttu-id="c5674-158">[アプリケーション] ブレードで **[マニフェスト]** を選択すると、**[マニフェストの編集]** ブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="c5674-158">Choose **Manifest** from the application blade, which opens the **Edit Manifest** blade.</span></span>

     <img src="media/azure-ad-edit-mft.png" width="295" height="114" alt="The Edit manifest blade" />

  2. <span data-ttu-id="c5674-159">`availableToOtherTenants` 設定の値を `true` に変更します。</span><span class="sxs-lookup"><span data-stu-id="c5674-159">Change the value of the `availableToOtherTenants` setting to `true`.</span></span>

  3. <span data-ttu-id="c5674-160">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c5674-160">Save your changes.</span></span>

## <a name="intune-permission-scopes"></a><span data-ttu-id="c5674-161">Intune のアクセス許可スコープ</span><span class="sxs-lookup"><span data-stu-id="c5674-161">Intune permission scopes</span></span>

<span data-ttu-id="c5674-162">Azure AD と Graph API では、アクセス許可スコープを使用して企業リソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="c5674-162">Azure AD and the Graph API use permission scopes to control access to corporate resources.</span></span>  

<span data-ttu-id="c5674-163">アクセス許可スコープ (_OAuth スコープ_とも呼ばれます) は、特定の Intune エンティティとそのプロパティへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="c5674-163">Permission scopes (also called the _OAuth scopes_) control access to specific Intune entities and their properties.</span></span> <span data-ttu-id="c5674-164">このセクションでは、Intune Graph API の機能に対するアクセス許可スコープの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5674-164">This section summarizes the permission scopes for Intune Graph API features.</span></span>

<span data-ttu-id="c5674-165">詳細については、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c5674-165">To learn more:</span></span>
- [<span data-ttu-id="c5674-166">Azure AD 認証</span><span class="sxs-lookup"><span data-stu-id="c5674-166">Azure AD authentication</span></span>](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)
- [<span data-ttu-id="c5674-167">アプリケーションのアクセス許可スコープ</span><span class="sxs-lookup"><span data-stu-id="c5674-167">Application permission scopes</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-scopes)

<span data-ttu-id="c5674-168">Graph API へのアクセス許可を付与する場合は、次のスコープを指定して Intune の機能へのアクセスを制御できます。次の表に、Intune Graph API のアクセス許可スコープをまとめています。</span><span class="sxs-lookup"><span data-stu-id="c5674-168">When you grant permission to the Graph API, you can specify the following scopes to control access to Intune features: The following table summarizes the Intune Graph API permission scopes.</span></span>  <span data-ttu-id="c5674-169">1 番目の列には Azure Portal に表示される機能名を示し、2 番目の列にはアクセス許可スコープ名を掲載しています。</span><span class="sxs-lookup"><span data-stu-id="c5674-169">The first column shows the name of the feature as displayed in the Azure portal and the second column provides the permission scope name.</span></span>

<span data-ttu-id="c5674-170">_[アクセスを有効にする]_ 設定</span><span class="sxs-lookup"><span data-stu-id="c5674-170">_Enable Access_ setting</span></span> | <span data-ttu-id="c5674-171">スコープ名</span><span class="sxs-lookup"><span data-stu-id="c5674-171">Scope name</span></span>
:--|:--
<span data-ttu-id="c5674-172">__Microsoft Intune デバイスでユーザーに影響を与えるリモート操作を実行する__</span><span class="sxs-lookup"><span data-stu-id="c5674-172">__Perform user-impacting remote actions on Microsoft Intune devices__</span></span> | [<span data-ttu-id="c5674-173">DeviceManagementManagedDevices.PrivilegedOperations.All</span><span class="sxs-lookup"><span data-stu-id="c5674-173">DeviceManagementManagedDevices.PrivilegedOperations.All</span></span>](#user-content-mgd-po)
<span data-ttu-id="c5674-174">__Microsoft Intune デバイスの読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-174">__Read and write Microsoft Intune devices__</span></span> | [<span data-ttu-id="c5674-175">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-175">DeviceManagementManagedDevices.ReadWrite.All</span></span>](#mgd-rw)
<span data-ttu-id="c5674-176">__Microsoft Intune デバイスの読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-176">__Read Microsoft Intune devices__</span></span> | [<span data-ttu-id="c5674-177">DeviceManagementManagedDevices.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-177">DeviceManagementManagedDevices.Read.All</span></span>](#mgd-ro)
<span data-ttu-id="c5674-178">__Microsoft Intune RBAC の設定の読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-178">__Read and write Microsoft Intune RBAC settings__</span></span> | [<span data-ttu-id="c5674-179">DeviceManagementRBAC.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-179">DeviceManagementRBAC.ReadWrite.All</span></span>](#rac-rw)
<span data-ttu-id="c5674-180">__Microsoft Intune RBAC の設定の読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-180">__Read Microsoft Intune RBAC settings__</span></span> | [<span data-ttu-id="c5674-181">DeviceManagementRBAC.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-181">DeviceManagementRBAC.Read.All</span></span>](#rac=ro)
<span data-ttu-id="c5674-182">__Microsoft Intune アプリの読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-182">__Read and write Microsoft Intune apps__</span></span> | [<span data-ttu-id="c5674-183">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-183">DeviceManagementApps.ReadWrite.All</span></span>](#app-rw)
<span data-ttu-id="c5674-184">__Microsoft Intune アプリの読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-184">__Read Microsoft Intune apps__</span></span> | [<span data-ttu-id="c5674-185">DeviceManagementApps.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-185">DeviceManagementApps.Read.All</span></span>](#app-ro)
<span data-ttu-id="c5674-186">__Microsoft Intune のデバイスの構成とポリシーの読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-186">__Read and write Microsoft Intune Device Configuration and Policies__</span></span> | [<span data-ttu-id="c5674-187">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-187">DeviceManagementConfiguration.ReadWrite.All</span></span>](#cfg-rw)
<span data-ttu-id="c5674-188">__Microsoft Intune のデバイスの構成とポリシーの読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-188">__Read Microsoft Intune Device Configuration and Policies__</span></span> | [<span data-ttu-id="c5674-189">DeviceManagementConfiguration.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-189">DeviceManagementConfiguration.Read.All</span></span>](#cfg-ro)
<span data-ttu-id="c5674-190">__Microsoft Intune の構成の読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-190">__Read and write Microsoft Intune configuration__</span></span> | [<span data-ttu-id="c5674-191">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-191">DeviceManagementServiceConfig.ReadWrite.All</span></span>](#svc-rw)
<span data-ttu-id="c5674-192">__Microsoft Intune の構成の読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-192">__Read Microsoft Intune configuration__</span></span> | [<span data-ttu-id="c5674-193">DeviceManagementServiceConfig.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-193">DeviceManagementServiceConfig.Read.All</span></span>](#svc-ra)

<span data-ttu-id="c5674-194">表は、Azure Portal に表示される順序で設定を一覧表示しています。</span><span class="sxs-lookup"><span data-stu-id="c5674-194">The table lists the settings as they appear in the Azure portal.</span></span> <span data-ttu-id="c5674-195">次のセクションでは、スコープについてアルファベット順に説明します。</span><span class="sxs-lookup"><span data-stu-id="c5674-195">The following sections describe the scopes in alphabetical order.</span></span>

<span data-ttu-id="c5674-196">この時点では、Intune のすべてのアクセス許可スコープに管理者のアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="c5674-196">At this time, all Intune permission scopes require administrator access.</span></span>  <span data-ttu-id="c5674-197">つまり、Intune Graph API のリソースにアクセスするアプリまたはスクリプトを実行する場合は、対応する資格情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="c5674-197">This means you need corresponding credentials when running apps or scripts that access Intune Graph API resources.</span></span>

### <a name="app-ro"></a><span data-ttu-id="c5674-198">DeviceManagementApps.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-198">DeviceManagementApps.Read.All</span></span>

- <span data-ttu-id="c5674-199">**[アクセスを有効にする]** 設定: __Microsoft Intune アプリの読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-199">**Enable Access** setting: __Read Microsoft Intune apps__</span></span>

- <span data-ttu-id="c5674-200">次のエンティティのプロパティとステータスへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-200">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="c5674-201">モバイル アプリ</span><span class="sxs-lookup"><span data-stu-id="c5674-201">Mobile Apps</span></span>
    - <span data-ttu-id="c5674-202">モバイル アプリ カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c5674-202">Mobile App Categories</span></span>
    - <span data-ttu-id="c5674-203">アプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="c5674-203">App Protection Policies</span></span>
    - <span data-ttu-id="c5674-204">アプリの構成</span><span class="sxs-lookup"><span data-stu-id="c5674-204">App Configurations</span></span>

### <a name="app-rw"></a><span data-ttu-id="c5674-205">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-205">DeviceManagementApps.ReadWrite.All</span></span>

- <span data-ttu-id="c5674-206">**[アクセスを有効にする]** 設定: __Microsoft Intune アプリの読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-206">**Enable Access** setting: __Read and write Microsoft Intune apps__</span></span>

- <span data-ttu-id="c5674-207">__DeviceManagementApps.Read.All__ と同じ操作を許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-207">Allows the same operations as __DeviceManagementApps.Read.All__</span></span>

- <span data-ttu-id="c5674-208">また、次のエンティティに対する変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-208">Also permits changes to the following entities:</span></span>

    - <span data-ttu-id="c5674-209">モバイル アプリ</span><span class="sxs-lookup"><span data-stu-id="c5674-209">Mobile Apps</span></span>
    - <span data-ttu-id="c5674-210">モバイル アプリ カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c5674-210">Mobile App Categories</span></span>
    - <span data-ttu-id="c5674-211">アプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="c5674-211">App Protection Policies</span></span>
    - <span data-ttu-id="c5674-212">アプリの構成</span><span class="sxs-lookup"><span data-stu-id="c5674-212">App Configurations</span></span>

### <a name="cfg-ro"></a><span data-ttu-id="c5674-213">DeviceManagementConfiguration.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-213">DeviceManagementConfiguration.Read.All</span></span>

- <span data-ttu-id="c5674-214">**[アクセスを有効にする]** 設定: __Microsoft Intune のデバイスの構成とポリシーの読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-214">**Enable Access** setting: __Read Microsoft Intune device configuration and policies__</span></span>

- <span data-ttu-id="c5674-215">次のエンティティのプロパティとステータスへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-215">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="c5674-216">デバイス構成</span><span class="sxs-lookup"><span data-stu-id="c5674-216">Device Configuration</span></span>
    - <span data-ttu-id="c5674-217">デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="c5674-217">Device Compliance Policy</span></span>
    - <span data-ttu-id="c5674-218">通知メッセージ</span><span class="sxs-lookup"><span data-stu-id="c5674-218">Notification Messages</span></span>

### <a name="cfg-ra"></a><span data-ttu-id="c5674-219">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-219">DeviceManagementConfiguration.ReadWrite.All</span></span>

- <span data-ttu-id="c5674-220">**[アクセスを有効にする]** 設定: __Microsoft Intune のデバイスの構成とポリシーの読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-220">**Enable Access** setting: __Read and write Microsoft Intune device configuration and policies__</span></span>

- <span data-ttu-id="c5674-221">__DeviceManagementConfiguration.Read.All__ と同じ操作を許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-221">Allows the same operations as __DeviceManagementConfiguration.Read.All__</span></span>

- <span data-ttu-id="c5674-222">また、アプリでは次のエンティティを作成、割り当て、削除、および変更できます。</span><span class="sxs-lookup"><span data-stu-id="c5674-222">Apps can also create, assign, delete, and change the following entities:</span></span>
    - <span data-ttu-id="c5674-223">デバイス構成</span><span class="sxs-lookup"><span data-stu-id="c5674-223">Device Configuration</span></span>
    - <span data-ttu-id="c5674-224">デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="c5674-224">Device Compliance Policy</span></span>
    - <span data-ttu-id="c5674-225">通知メッセージ</span><span class="sxs-lookup"><span data-stu-id="c5674-225">Notification Messages</span></span>

### <a name="mgd-po"></a><span data-ttu-id="c5674-226">DeviceManagementManagedDevices.PrivilegedOperations.All</span><span class="sxs-lookup"><span data-stu-id="c5674-226">DeviceManagementManagedDevices.PrivilegedOperations.All</span></span>

- <span data-ttu-id="c5674-227">**[アクセスを有効にする]** 設定: __Microsoft Intune デバイスでユーザーに影響を与えるリモート操作を実行する__</span><span class="sxs-lookup"><span data-stu-id="c5674-227">**Enable Access** setting: __Perform user-impacting remote actions on Microsoft Intune devices__</span></span>

- <span data-ttu-id="c5674-228">管理されたデバイスへの次のリモート操作を許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-228">Permits the following remote actions on a managed device:</span></span>
    - <span data-ttu-id="c5674-229">インベントリから削除</span><span class="sxs-lookup"><span data-stu-id="c5674-229">Retire</span></span>
    - <span data-ttu-id="c5674-230">ワイプ</span><span class="sxs-lookup"><span data-stu-id="c5674-230">Wipe</span></span>
    - <span data-ttu-id="c5674-231">パスコードのリセット/復旧</span><span class="sxs-lookup"><span data-stu-id="c5674-231">Reset/Recover Passcode</span></span>
    - <span data-ttu-id="c5674-232">リモート ロック</span><span class="sxs-lookup"><span data-stu-id="c5674-232">Remote Lock</span></span>
    - <span data-ttu-id="c5674-233">紛失モードの有効/無効</span><span class="sxs-lookup"><span data-stu-id="c5674-233">Enable/Disable Lost Mode</span></span>
    - <span data-ttu-id="c5674-234">PC のクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="c5674-234">Clean PC</span></span>
    - <span data-ttu-id="c5674-235">再起動</span><span class="sxs-lookup"><span data-stu-id="c5674-235">Reboot</span></span>
    - <span data-ttu-id="c5674-236">共有デバイスからのユーザーの削除</span><span class="sxs-lookup"><span data-stu-id="c5674-236">Delete User from Shared Device</span></span>

### <a name="mgd-ro"></a><span data-ttu-id="c5674-237">DeviceManagementManagedDevices.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-237">DeviceManagementManagedDevices.Read.All</span></span>

- <span data-ttu-id="c5674-238">**[アクセスを有効にする]** 設定: __Microsoft Intune デバイスの読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-238">**Enable Access** setting: __Read Microsoft Intune devices__</span></span>

- <span data-ttu-id="c5674-239">次のエンティティのプロパティとステータスへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-239">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="c5674-240">管理されたデバイス</span><span class="sxs-lookup"><span data-stu-id="c5674-240">Managed Device</span></span>
    - <span data-ttu-id="c5674-241">デバイスのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="c5674-241">Device Category</span></span>
    - <span data-ttu-id="c5674-242">検出されたアプリ</span><span class="sxs-lookup"><span data-stu-id="c5674-242">Detected App</span></span>
    - <span data-ttu-id="c5674-243">リモート操作</span><span class="sxs-lookup"><span data-stu-id="c5674-243">Remote actions</span></span>
    - <span data-ttu-id="c5674-244">マルウェア情報</span><span class="sxs-lookup"><span data-stu-id="c5674-244">Malware information</span></span>

### <a name="mgd-rw"></a><span data-ttu-id="c5674-245">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-245">DeviceManagementManagedDevices.ReadWrite.All</span></span>

- <span data-ttu-id="c5674-246">**[アクセスを有効にする]** 設定: __Microsoft Intune デバイスの読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-246">**Enable Access** setting: __Read and write Microsoft Intune devices__</span></span>

- <span data-ttu-id="c5674-247">__DeviceManagementManagedDevices.Read.All__ と同じ操作を許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-247">Allows the same operations as __DeviceManagementManagedDevices.Read.All__</span></span>

- <span data-ttu-id="c5674-248">また、アプリでは次のエンティティを作成、削除、変更できます。</span><span class="sxs-lookup"><span data-stu-id="c5674-248">Apps can also create, delete, and change the following entities:</span></span>
    - <span data-ttu-id="c5674-249">管理されたデバイス</span><span class="sxs-lookup"><span data-stu-id="c5674-249">Managed Device</span></span>
    - <span data-ttu-id="c5674-250">デバイスのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="c5674-250">Device Category</span></span>

- <span data-ttu-id="c5674-251">次のリモート操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="c5674-251">The following remote actions are also allowed:</span></span>
    - <span data-ttu-id="c5674-252">デバイスの検索</span><span class="sxs-lookup"><span data-stu-id="c5674-252">Locate devices</span></span>
    - <span data-ttu-id="c5674-253">アクティベーション ロックのバイパス</span><span class="sxs-lookup"><span data-stu-id="c5674-253">Bypass activation lock</span></span>
    - <span data-ttu-id="c5674-254">リモート アシスタンスの要求</span><span class="sxs-lookup"><span data-stu-id="c5674-254">Request remote assistance</span></span>

### <a name="rac-ro"></a><span data-ttu-id="c5674-255">DeviceManagementRBAC.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-255">DeviceManagementRBAC.Read.All</span></span>

- <span data-ttu-id="c5674-256">**[アクセスを有効にする]** 設定: __Microsoft Intune RBAC の設定の読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-256">**Enable Access** setting: __Read Microsoft Intune RBAC settings__</span></span>

- <span data-ttu-id="c5674-257">次のエンティティのプロパティとステータスへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-257">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="c5674-258">ロールの割り当て</span><span class="sxs-lookup"><span data-stu-id="c5674-258">Role Assignments</span></span>
    - <span data-ttu-id="c5674-259">ロールの定義</span><span class="sxs-lookup"><span data-stu-id="c5674-259">Role Definitions</span></span>
    - <span data-ttu-id="c5674-260">リソースの操作</span><span class="sxs-lookup"><span data-stu-id="c5674-260">Resource Operations</span></span>

### <a name="rac-rw"></a><span data-ttu-id="c5674-261">DeviceManagementRBAC.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-261">DeviceManagementRBAC.ReadWrite.All</span></span>

- <span data-ttu-id="c5674-262">**[アクセスを有効にする]** 設定: __Microsoft Intune RBAC の設定の読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-262">**Enable Access** setting: __Read and write Microsoft Intune RBAC settings__</span></span>

- <span data-ttu-id="c5674-263">__DeviceManagementRBAC.Read.All__ と同じ操作を許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-263">Allows the same operations as __DeviceManagementRBAC.Read.All__</span></span>

- <span data-ttu-id="c5674-264">また、アプリでは次のエンティティを作成、割り当て、削除、および変更できます。</span><span class="sxs-lookup"><span data-stu-id="c5674-264">Apps can also create, assign, delete, and change the following entities:</span></span>
    - <span data-ttu-id="c5674-265">ロールの割り当て</span><span class="sxs-lookup"><span data-stu-id="c5674-265">Role Assignments</span></span>
    - <span data-ttu-id="c5674-266">ロールの定義</span><span class="sxs-lookup"><span data-stu-id="c5674-266">Role Definitions</span></span>

### <a name="svc-ro"></a><span data-ttu-id="c5674-267">DeviceManagementServiceConfig.Read.All</span><span class="sxs-lookup"><span data-stu-id="c5674-267">DeviceManagementServiceConfig.Read.All</span></span>

- <span data-ttu-id="c5674-268">**[アクセスを有効にする]** 設定: __Microsoft Intune の構成の読み取り__</span><span class="sxs-lookup"><span data-stu-id="c5674-268">**Enable Access** setting: __Read Microsoft Intune configuration__</span></span>

- <span data-ttu-id="c5674-269">次のエンティティのプロパティとステータスへの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-269">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="c5674-270">デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="c5674-270">Device Enrollment</span></span>
    - <span data-ttu-id="c5674-271">Apple Push Notification 証明書</span><span class="sxs-lookup"><span data-stu-id="c5674-271">Apple Push Notification Certificate</span></span>
    - <span data-ttu-id="c5674-272">Apple Device Enrollment Program</span><span class="sxs-lookup"><span data-stu-id="c5674-272">Apple Device Enrollment Program</span></span>
    - <span data-ttu-id="c5674-273">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="c5674-273">Apple Volume Purchase Program</span></span>
    - <span data-ttu-id="c5674-274">Exchange Connector</span><span class="sxs-lookup"><span data-stu-id="c5674-274">Exchange Connector</span></span>
    - <span data-ttu-id="c5674-275">使用条件</span><span class="sxs-lookup"><span data-stu-id="c5674-275">Terms and Conditions</span></span>
    - <span data-ttu-id="c5674-276">通信経費管理</span><span class="sxs-lookup"><span data-stu-id="c5674-276">Telecoms Expense Management</span></span>
    - <span data-ttu-id="c5674-277">クラウド PKI</span><span class="sxs-lookup"><span data-stu-id="c5674-277">Cloud PKI</span></span>
    - <span data-ttu-id="c5674-278">ブランド化</span><span class="sxs-lookup"><span data-stu-id="c5674-278">Branding</span></span>
    - <span data-ttu-id="c5674-279">Mobile Threat Defense</span><span class="sxs-lookup"><span data-stu-id="c5674-279">Mobile Threat Defense</span></span>

### <a name="svc-rw"></a><span data-ttu-id="c5674-280">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c5674-280">DeviceManagementServiceConfig.ReadWrite.All</span></span>

- <span data-ttu-id="c5674-281">**[アクセスを有効にする]** 設定: __Microsoft Intune の構成の読み取りおよび書き込み__</span><span class="sxs-lookup"><span data-stu-id="c5674-281">**Enable Access** setting: __Read and write Microsoft Intune configuration__</span></span>

- <span data-ttu-id="c5674-282">DeviceManagementServiceConfig.Read.All と同じ操作を許可します。</span><span class="sxs-lookup"><span data-stu-id="c5674-282">Allows the same operations as DeviceManagementServiceConfig.Read.All_</span></span>

- <span data-ttu-id="c5674-283">また、アプリでは Intune の次の機能を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c5674-283">Apps can also configure the following Intune features:</span></span>
    - <span data-ttu-id="c5674-284">デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="c5674-284">Device Enrollment</span></span>
    - <span data-ttu-id="c5674-285">Apple Push Notification 証明書</span><span class="sxs-lookup"><span data-stu-id="c5674-285">Apple Push Notification Certificate</span></span>
    - <span data-ttu-id="c5674-286">Apple Device Enrollment Program</span><span class="sxs-lookup"><span data-stu-id="c5674-286">Apple Device Enrollment Program</span></span>
    - <span data-ttu-id="c5674-287">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="c5674-287">Apple Volume Purchase Program</span></span>
    - <span data-ttu-id="c5674-288">Exchange Connector</span><span class="sxs-lookup"><span data-stu-id="c5674-288">Exchange Connector</span></span>
    - <span data-ttu-id="c5674-289">使用条件</span><span class="sxs-lookup"><span data-stu-id="c5674-289">Terms and Conditions</span></span>
    - <span data-ttu-id="c5674-290">通信経費管理</span><span class="sxs-lookup"><span data-stu-id="c5674-290">Telecoms Expense Management</span></span>
    - <span data-ttu-id="c5674-291">クラウド PKI</span><span class="sxs-lookup"><span data-stu-id="c5674-291">Cloud PKI</span></span>
    - <span data-ttu-id="c5674-292">ブランド化</span><span class="sxs-lookup"><span data-stu-id="c5674-292">Branding</span></span>
    - <span data-ttu-id="c5674-293">Mobile Threat Defense</span><span class="sxs-lookup"><span data-stu-id="c5674-293">Mobile Threat Defense</span></span>

## <a name="azure-ad-authentication-examples"></a><span data-ttu-id="c5674-294">Azure AD 認証の例</span><span class="sxs-lookup"><span data-stu-id="c5674-294">Azure AD authentication examples</span></span>

<span data-ttu-id="c5674-295">このセクションでは、Azure AD を C# プロジェクトや PowerShell プロジェクトに組み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5674-295">This section shows how to incorporate Azure AD into your C# and PowerShell projects.</span></span>

<span data-ttu-id="c5674-296">それぞれの例で、少なくとも前述のアクセス許可スコープ `DeviceManagementManagedDevices.Read.All` を持つアプリケーション ID を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5674-296">In each example, you'll need to specify an application ID that has at least the `DeviceManagementManagedDevices.Read.All` permission scope (discussed earlier).</span></span>

<span data-ttu-id="c5674-297">いずれかの例をテストすると、次のような HTTP ステータス 403 (禁止されています) のエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c5674-297">When testing either example, you may receive HTTP status 403 (Forbidden) errors similar to the following:</span></span>

``` javascript
{
  "error": {
    "code": "Forbidden",
    "message": "Application is not authorized to perform this operation - Operation ID " +
       "(for customer support): 00000000-0000-0000-0000-000000000000 - " +
       "Activity ID: cc7fa3b3-bb25-420b-bfb2-1498e598ba43 - " +
       "Url: https://example.manage.microsoft.com/" +
       "Service/Resource/RESTendpoint?" +
       "api-version=2017-03-06 - CustomApiErrorPhrase: ",
    "innerError": {
      "request-id": "00000000-0000-0000-0000-000000000000",
      "date": "1980-01-0112:00:00"
    }
  }
}
```

<span data-ttu-id="c5674-298">この場合は、次の点を確認します。</span><span class="sxs-lookup"><span data-stu-id="c5674-298">If this happens, verify that:</span></span>

- <span data-ttu-id="c5674-299">Graph API とアクセス許可スコープ `DeviceManagementManagedDevices.Read.All` の使用が承認されたアプリケーション ID に更新している。</span><span class="sxs-lookup"><span data-stu-id="c5674-299">You've updated the application ID to one authorized to use the Graph API and the `DeviceManagementManagedDevices.Read.All` permission scope.</span></span>

- <span data-ttu-id="c5674-300">テナントの資格情報は、管理機能をサポートしている。</span><span class="sxs-lookup"><span data-stu-id="c5674-300">Your tenant credentials support administrative functions.</span></span>

- <span data-ttu-id="c5674-301">表示されているサンプルと同様のコードを使用している。</span><span class="sxs-lookup"><span data-stu-id="c5674-301">Your code is similar to the displayed samples.</span></span>


### <a name="authenticate-azure-ad-in-c"></a><span data-ttu-id="c5674-302">Azure AD の認証 (C\#)</span><span class="sxs-lookup"><span data-stu-id="c5674-302">Authenticate Azure AD in C\#</span></span>

<span data-ttu-id="c5674-303">この例では、C# を使用して、Intune アカウントに関連付けられているデバイスの一覧を取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="c5674-303">This example shows how to use C# to retrieve a list of devices associated with your Intune account.</span></span>

1.  <span data-ttu-id="c5674-304">Visual Studio を起動して、新しい Visual C# コンソール アプリ (.NET Framework) プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5674-304">Start Visual Studio and then create a new Visual C# Console app (.NET Framework) project.</span></span>

2.  <span data-ttu-id="c5674-305">プロジェクトの名前を入力し、必要に応じて他の詳細情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c5674-305">Enter a name for your project and provide other details as desired.</span></span>

    <img src="media/aad-auth-cpp-new-console.png" width="624" height="433" alt="Creating a C# console app project in Visual Studio"  />

3.  <span data-ttu-id="c5674-306">ソリューション エクスプローラーを使用して、プロジェクトに Microsoft ADAL NuGet パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="c5674-306">Use the Solution Explorer to add the Microsoft ADAL NuGet package to the project.</span></span>

    1.  <span data-ttu-id="c5674-307">ソリューション エクスプローラーを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c5674-307">Right-click the Solution Explorer.</span></span>
    2.  <span data-ttu-id="c5674-308">**[NuGet パッケージの管理...]** </span><span class="sxs-lookup"><span data-stu-id="c5674-308">Choose **Manage NuGet Packages…**</span></span> <span data-ttu-id="c5674-309">&gt; **[参照]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-309">&gt; **Browse**.</span></span>
    3.  <span data-ttu-id="c5674-310">`Microsoft.IdentityModel.Clients.ActiveDirectory` を選択して、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-310">Select `Microsoft.IdentityModel.Clients.ActiveDirectory` and then choose **Install**.</span></span>

    <img src="media/aad-auth-cpp-install-package.png" width="624" height="458" alt="Selecting the Azure AD identity model module" />

4.  <span data-ttu-id="c5674-311">**Program.cs** の先頭に、次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c5674-311">Add the following statements to the top of **Program.cs**:</span></span>

    ``` csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;</p>
    using System.Net.Http;
    ```

5.  <span data-ttu-id="c5674-312">Authorization ヘッダーを作成するメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="c5674-312">Add a method to create the authorization header:</span></span>

    ``` csharp
    private static async Task<string> GetAuthorizationHeader()
    {
        string applicationId = "<Your Application ID>";
        string authority = "https://login.microsoftonline.com/common/";
        Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
        AuthenticationContext context = new AuthenticationContext(authority);
        AuthenticationResult result = await context.AcquireTokenAsync(
            "https://graph.microsoft.com",
            applicationId, redirectUri,
            new PlatformParameters(PromptBehavior.Auto));
        return result.CreateAuthorizationHeader();
    ```

    <span data-ttu-id="c5674-313">前述のとおり、`application_ID` の値を、少なくともアクセス許可スコープ `DeviceManagementManagedDevices.Read.All` が付与されたものと一致するように変更してください。</span><span class="sxs-lookup"><span data-stu-id="c5674-313">Remember to change the value of `application_ID` to match one granted at least the `DeviceManagementManagedDevices.Read.All` permission scope, as described earlier.</span></span>

6. <span data-ttu-id="c5674-314">デバイスの一覧を取得するメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="c5674-314">Add a method to retrieve the list of devices:</span></span>

    ``` csharp
    private static async Task<string> GetMyManagedDevices()
    {
        string authHeader = await GetAuthorizationHeader();
        HttpClient graphClient = new HttpClient();
        graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
        return await graphClient.GetStringAsync(
            "https://graph.microsoft.com/beta/me/managedDevices");
    }
    ```

7.  <span data-ttu-id="c5674-315">**Main** を **GetMyManagedDevices** を呼び出すように更新します。</span><span class="sxs-lookup"><span data-stu-id="c5674-315">Update **Main** to call **GetMyManagedDevices**:</span></span>

    ``` csharp
    string devices = GetMyManagedDevices().GetAwaiter().GetResult();
    Console.WriteLine(devices);
    ```

8.  <span data-ttu-id="c5674-316">プログラムをコンパイルし、実行します。</span><span class="sxs-lookup"><span data-stu-id="c5674-316">Compile and run your program.</span></span>  

<span data-ttu-id="c5674-317">初めてプログラムを実行すると、2 つのプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5674-317">When you first run your program, you should receive two prompts.</span></span>  <span data-ttu-id="c5674-318">1 つ目は資格情報を要求し、2 つ目は `managedDevices` 要求に対するアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c5674-318">The first requests your credentials and the second grants permissions for the `managedDevices` request.</span></span>  

<span data-ttu-id="c5674-319">参考までに、完成したプログラムを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c5674-319">For reference, here's the completed program:</span></span>

``` csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System;
using System.Net.Http;
using System.Threading.Tasks;

namespace IntuneGraphExample
{
    class Program
    {
        static void Main(string[] args)
        {
            string devices = GetMyManagedDevices().GetAwaiter().GetResult();
            Console.WriteLine(devices);
        }

        private static async Task<string> GetAuthorizationHeader()
        {
            string applicationId = "<Your Application ID>";
            string authority = "https://login.microsoftonline.com/common/";
            Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
            AuthenticationContext context = new AuthenticationContext(authority);
            AuthenticationResult result = await context.AcquireTokenAsync("https://graph.microsoft.com", applicationId, redirectUri, new PlatformParameters(PromptBehavior.Auto));
            return result.CreateAuthorizationHeader();
        }

        private static async Task<string> GetMyManagedDevices()
        {
            string authHeader = await GetAuthorizationHeader();
            HttpClient graphClient = new HttpClient();
            graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
            return await graphClient.GetStringAsync("https://graph.microsoft.com/beta/me/managedDevices");
        }
    }
}
```

### <a name="authenticate-azure-ad-powershell"></a><span data-ttu-id="c5674-320">Azure AD の認証 (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c5674-320">Authenticate Azure AD (PowerShell)</span></span>

<span data-ttu-id="c5674-321">次の PowerShell スクリプトでは、認証のために AzureAD PowerShell モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5674-321">The following PowerShell script uses the AzureAD PowerShell module for authentication.</span></span>  <span data-ttu-id="c5674-322">詳細については、「[Azure Active Directory PowerShell Version 2 (Azure Active Directory PowerShell バージョン 2)](https://docs.microsoft.co/powershell/azure/install-adv2?view=azureadps-2.0)」と「[Intune PowerShell examples (Intune PowerShell の例)](https://github.com/microsoftgraph/powershell-intune-samples)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c5674-322">To learn more, see [Azure Active Directory PowerShell Version 2](https://docs.microsoft.co/powershell/azure/install-adv2?view=azureadps-2.0) and the [Intune PowerShell examples](https://github.com/microsoftgraph/powershell-intune-samples).</span></span>

<span data-ttu-id="c5674-323">この例では、`$clientID` の値を、有効なアプリケーション ID と一致するように更新します。</span><span class="sxs-lookup"><span data-stu-id="c5674-323">In this example, update the value of `$clientID` to match a valid application ID.</span></span>

``` powershell
function Get-AuthToken {
    [cmdletbinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        $User
    )

    $userUpn = New-Object "System.Net.Mail.MailAddress" -ArgumentList $User
    $tenant = $userUpn.Host

    Write-Host "Checking for AzureAD module..."

    $AadModule = Get-Module -Name "AzureAD" -ListAvailable
    if ($AadModule -eq $null) {
        Write-Host "AzureAD PowerShell module not found, looking for AzureADPreview"
        $AadModule = Get-Module -Name "AzureADPreview" -ListAvailable
    }

    if ($AadModule -eq $null) {
        write-host
        write-host "AzureAD Powershell module not installed..." -f Red
        write-host "Install by running 'Install-Module AzureAD' or 'Install-Module AzureADPreview' from an elevated PowerShell prompt" -f Yellow
        write-host "Script can't continue..." -f Red
        write-host
        exit
    }

    # Getting path to ActiveDirectory Assemblies
    # If the module count is greater than 1 find the latest version

    if ($AadModule.count -gt 1) {
        $Latest_Version = ($AadModule | select version | Sort-Object)[-1]
        $aadModule = $AadModule | ? { $_.version -eq $Latest_Version.version }
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    else {
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    [System.Reflection.Assembly]::LoadFrom($adal) | Out-Null
    [System.Reflection.Assembly]::LoadFrom($adalforms) | Out-Null

    $clientId = "<Your Application ID>"
    $redirectUri = "urn:ietf:wg:oauth:2.0:oob"
    $resourceAppIdURI = "https://graph.microsoft.com"
    $authority = "https://login.microsoftonline.com/$Tenant"

    try {
        $authContext = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext" -ArgumentList $authority
        # https://msdn.microsoft.com/library/azure/microsoft.identitymodel.clients.activedirectory.promptbehavior.aspx
        # Change the prompt behaviour to force credentials each time: Auto, Always, Never, RefreshSession
        $platformParameters = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.PlatformParameters" -ArgumentList "Auto"
        $userId = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.UserIdentifier" -ArgumentList ($User, "OptionalDisplayableId")
        $authResult = $authContext.AcquireTokenAsync($resourceAppIdURI, $clientId, $redirectUri, $platformParameters, $userId).Result
        # If the accesstoken is valid then create the authentication header
        if ($authResult.AccessToken) {
            # Creating header for Authorization token
            $authHeader = @{
                'Content-Type' = 'application/json'
                'Authorization' = "Bearer " + $authResult.AccessToken
                'ExpiresOn' = $authResult.ExpiresOn
            }
            return $authHeader
        }
        else {
            Write-Host
            Write-Host "Authorization Access Token is null, please re-run authentication..." -ForegroundColor Red
            Write-Host
            break
        }
    }
    catch {
        write-host $_.Exception.Message -f Red
        write-host $_.Exception.ItemName -f Red
        write-host
        break
    }   
}

$authToken = Get-AuthToken -User "<Your AAD Username>"

try {
    $uri = "https://graph.microsoft.com/beta/me/managedDevices"
    Write-Verbose $uri
    (Invoke-RestMethod -Uri $uri –Headers $authToken –Method Get).Value
}
catch {
    $ex = $_.Exception
    $errorResponse = $ex.Response.GetResponseStream()
    $reader = New-Object System.IO.StreamReader($errorResponse)
    $reader.BaseStream.Position = 0
    $reader.DiscardBufferedData()
    $responseBody = $reader.ReadToEnd();
    Write-Host "Response content:`n$responseBody" -f Red
    Write-Error "Request to $Uri failed with HTTP Status $($ex.Response.StatusCode) $($ex.Response.StatusDescription)"
    write-host
    break
}
```

## <a name="support-multiple-tenants-and-partners"></a><span data-ttu-id="c5674-324">複数のテナントとパートナーのサポート</span><span class="sxs-lookup"><span data-stu-id="c5674-324">Support multiple tenants and partners</span></span>

<span data-ttu-id="c5674-325">独自の Azure AD テナントがある組織をサポートする組織の場合、それぞれのテナントでアプリケーションを使用するようにクライアントを許可する必要があることがあります。</span><span class="sxs-lookup"><span data-stu-id="c5674-325">If your organization supports organizations with their own Azure AD tenants, you may want to permit your clients to use your application with their respective tenants.</span></span>

<span data-ttu-id="c5674-326">これを実行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c5674-326">To do so:</span></span>

1.  <span data-ttu-id="c5674-327">対象の Azure AD テナントに、クライアントのアカウントが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5674-327">Verify that the client account exists in the target Azure AD tenant.</span></span>

2.  <span data-ttu-id="c5674-328">テナント アカウントが、ユーザーによるアプリケーションの登録を許可していることを確認します (**ユーザー設定** をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="c5674-328">Verify that your tenant account allows users to register applications (see **User settings**).</span></span>

3.  <span data-ttu-id="c5674-329">各テナント間のリレーションシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="c5674-329">Establish a relationship between each tenant.</span></span>  

    <span data-ttu-id="c5674-330">そのためには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5674-330">To do so, either:</span></span>

    <span data-ttu-id="c5674-331">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="c5674-331">a.</span></span> <span data-ttu-id="c5674-332">[Microsoft Partner Center](https://partnercenter.microsoft.com/) を使用して、クライアントとそのメール アドレスのリレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="c5674-332">Use the [Microsoft Partner Center](https://partnercenter.microsoft.com/) to define a relationship with your client and their email address.</span></span>

    <span data-ttu-id="c5674-333">b.</span><span class="sxs-lookup"><span data-stu-id="c5674-333">b.</span></span> <span data-ttu-id="c5674-334">ユーザーを招待して、テナントのゲストにします。</span><span class="sxs-lookup"><span data-stu-id="c5674-334">Invite the user to become a guest of your tenant.</span></span>

<span data-ttu-id="c5674-335">ユーザーを招待してテナントのゲストにするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5674-335">To invite the user to be a guest of your tenant:</span></span>

1.  <span data-ttu-id="c5674-336">**[クイック タスク]** パネルで、**[ゲスト ユーザーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-336">Choose **Add a guest user** from the **Quick tasks** panel.</span></span>

    <img src="media/azure-ad-add-guest.png" width="448" height="138" alt="Use Quick Tasks to add a guest user" />

2.  <span data-ttu-id="c5674-337">クライアントのメール アドレスを入力し、(必要に応じて) 招待状に個人的なメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="c5674-337">Enter the client's email address and (optionally) add a personalized message for the invite.</span></span>

    <img src="media/azure-ad-guest-invite.png" width="203" height="106" alt="Inviting an external user as a guest" />

3.  <span data-ttu-id="c5674-338">**[招待する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5674-338">Choose **Invite**.</span></span>

<span data-ttu-id="c5674-339">これにより、ユーザーに招待状が送信されます。</span><span class="sxs-lookup"><span data-stu-id="c5674-339">This sends an invite to the user.</span></span>

   <img src="media/aad-multiple-tenant-invitation.png" width="624" height="523" alt="A sample guest invitation" />

   <span data-ttu-id="c5674-340">ユーザーは **[開始]** リンクを選択して、招待を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5674-340">The user needs to choose the **Get Started** link to accept your invitation.</span></span>

<span data-ttu-id="c5674-341">リレーションシップが確立されると (または招待が承諾されると)、**[ディレクトリ ロール]** にユーザー アカウントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c5674-341">When the relationship is established (or your invitation has been accepted), add the user account to the **Directory role**.</span></span>

<span data-ttu-id="c5674-342">必要に応じて、そのほかのロールにユーザーを追加するようにします。</span><span class="sxs-lookup"><span data-stu-id="c5674-342">Remember to add the user to other roles as needed.</span></span> <span data-ttu-id="c5674-343">たとえば、ユーザーに Intune の設定の管理を許可する場合、ユーザーは **[グローバル管理者]** または **[Intune サービス管理者]** のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5674-343">For example, to allow the user to manage Intune settings, they need to be either a **Global Administrator** or an **Intune Service administrator**.</span></span>

<span data-ttu-id="c5674-344">また、</span><span class="sxs-lookup"><span data-stu-id="c5674-344">Also:</span></span>

- <span data-ttu-id="c5674-345">http://portal.office.com を使用して、ユーザー アカウントに Intune のライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c5674-345">Use http://portal.office.com to assign an Intune license to your user account.</span></span>

- <span data-ttu-id="c5674-346">自身ではなく、クライアントの Azure AD テナントのドメインに対する認証のためにアプリケーション コードを更新します。</span><span class="sxs-lookup"><span data-stu-id="c5674-346">Update application code to authenticate to the client's Azure AD tenant domain, rather than your own.</span></span>

    <span data-ttu-id="c5674-347">たとえば、自身のテナントのドメインが `contosopartner.onmicrosoft.com`、クライアントのテナントのドメインが `northwind.onmicrosoft.com` で、クライアントのテナントを認証するためにコードを更新するとします。</span><span class="sxs-lookup"><span data-stu-id="c5674-347">For example, suppose your tenant domain is `contosopartner.onmicrosoft.com` and your client's tenant domain is `northwind.onmicrosoft.com`, you would update your code to authenticate to your client's tenant.</span></span>

    <span data-ttu-id="c5674-348">先ほどの例に基づき C# アプリケーションでこれを実行するには、変数 `authority` の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="c5674-348">To do so in a C# application based on the earlier example, you'd change the value of the `authority` variable:</span></span>

    ``` csharp
    string authority = "https://login.microsoftonline.com/common/";
    ```

    <span data-ttu-id="c5674-349">を</span><span class="sxs-lookup"><span data-stu-id="c5674-349">to</span></span>

    ``` csharp
    string authority = "https://login.microsoftonline.com/northwind.onmicrosoft.com/";
    ```
