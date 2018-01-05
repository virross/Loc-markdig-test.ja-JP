---
title: "Azure Active Directory シングル サインオンを使用するように Skycure を構成する"
description: "Azure Active Directory シングル サインオン (SSO) を使用するように Skycure を構成する"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 34d5d359-5c7c-4225-a205-8ce890b6f890
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 790a687aba5e28cd9d6e5266b77365e00d8d0cd0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a><span data-ttu-id="e0d54-103">Azure Active Directory シングル サインオン (SSO) を使用するように Skycure を構成する</span><span class="sxs-lookup"><span data-stu-id="e0d54-103">Configure Skycure to use Azure Active Directory Single Sign On (SSO)</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e0d54-104">Azure AD SSO は、Intune と Skycure の統合時に利用されます。</span><span class="sxs-lookup"><span data-stu-id="e0d54-104">Azure AD SSO is used when you integrate Intune with Skycure.</span></span> <span data-ttu-id="e0d54-105">主な利点:</span><span class="sxs-lookup"><span data-stu-id="e0d54-105">Here are the main benefits:</span></span>

-   <span data-ttu-id="e0d54-106">**管理者**は同じ資格情報を利用できます。Microsoft ポータル (Intune、Azure) と Skycure 管理コンソールでログイン/ログアウトするたびに資格情報を入力する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="e0d54-106">**Admins** can use the same credentials without having to type it again every time they log in and out from the Microsoft portals (Intune, Azure) and Skycure Management console.</span></span>

-   <span data-ttu-id="e0d54-107">**エンドユーザー**は同じ Azure AD 資格情報を利用できます。Skycure アプリでログイン/ログアウトするたびに資格情報を入力する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="e0d54-107">**End-users** can use the same Azure AD credentials without having to type it again every time they log in and out from the Skycure apps.</span></span>

<span data-ttu-id="e0d54-108">Skycure と Azure Active Directory シングル サインオン (SSO) を統合する手順を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e0d54-108">Below are the steps to integrate Skycure with Azure Active Directory Single Sign On (SSO).</span></span>

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a><span data-ttu-id="e0d54-109">Azure Active Directory テナント ID を取得するには</span><span class="sxs-lookup"><span data-stu-id="e0d54-109">To retrieve the Azure Active Directory Tenant ID</span></span>

<span data-ttu-id="e0d54-110">Azure AD テナント ID を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0d54-110">You need to retrieve the Azure AD Tenant ID.</span></span>

1.  <span data-ttu-id="e0d54-111">[Azure Portal](https://portal.azure.com/) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="e0d54-111">Go to the [Azure portal](https://portal.azure.com/) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="e0d54-112">**ダッシュボード**が表示されたら、**[Azure Active Directory]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0d54-112">You can see the **Dashboard,** choose **Azure Active Directory**.</span></span>

![Azure AD ダッシュボード](../media/mtp/skycure-sso-1.png)

1.  <span data-ttu-id="e0d54-114">**[Azure Active Directory]** ブレードが開いたら、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0d54-114">The **Azure Active Directory** blade opens, choose **Properties**.</span></span>

![Azure AD の [プロパティ] ブレード](../media/mtp/skycure-sso-2.png)

1.  <span data-ttu-id="e0d54-116">Azure Active Directory の **[プロパティ]** ブレードの **[テナント ディレクトリ ID]** で **[コピー]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0d54-116">Click on the **Copy icon** under the **Tenant Directory ID** at **Azure Active Directory Properties** blade.</span></span>

> <span data-ttu-id="e0d54-117">後で使用できるように、コピーしたディレクトリ ID 値をテキスト ファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e0d54-117">Paste the copied Directory ID value in a text file so you can use it later.</span></span> <span data-ttu-id="e0d54-118">ディレクトリ ID 値は、後で、Skycure と Intune の統合プロセスで必要になります。</span><span class="sxs-lookup"><span data-stu-id="e0d54-118">The Directory ID value will be required later in the Skycure and Intune integration process.</span></span>

![Azure AD ダッシュボード](../media/mtp/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a><span data-ttu-id="e0d54-120">Azure Active Directory との通信を Skycure に許可する</span><span class="sxs-lookup"><span data-stu-id="e0d54-120">Allow Skycure to communicate with Azure Active Directory</span></span>

1.  <span data-ttu-id="e0d54-121">ブラウザーに下の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0d54-121">Enter the below URL in your browser.</span></span> <span data-ttu-id="e0d54-122">**DIRECTORY_ID** の代わりに、前にテキスト ファイルにコピーした Azure Active Directory テナント ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0d54-122">Instead of **DIRECTORY_ID**, enter your Azure Active Directory Tenant ID previously copied to the text file.</span></span>

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  <span data-ttu-id="e0d54-123">Azure Active Directory の資格情報を使用してログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0d54-123">You need to login using your Azure Active Directory credentials.</span></span> <span data-ttu-id="e0d54-124">**[同意する]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="e0d54-124">Click **Accept** to continue.</span></span>

![Azure AD ログイン ページ](../media/mtp/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a><span data-ttu-id="e0d54-126">Skycure の Azure AD セキュリティ グループを作成する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="e0d54-126">Create an Azure AD Security group for Skycure (optional)</span></span>

<span data-ttu-id="e0d54-127">Skycure を実行しているユーザーを含む専用ユーザー グループを作成すると便利です (Skycure ユーザーなど)。</span><span class="sxs-lookup"><span data-stu-id="e0d54-127">You might want to create a dedicated user group which contain users running Skycure (e.g Skycure users).</span></span> <span data-ttu-id="e0d54-128">レポートで Skycure アクティビティを分析するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="e0d54-128">This can be helpful when analyzing Skycure activity through the reports.</span></span>

-   <span data-ttu-id="e0d54-129">詳細については、「[Azure Active Directory でグループを作成し、メンバーを追加する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0d54-129">Learn more [how to create a group and add members in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span></span>

> [!NOTE] 
> <span data-ttu-id="e0d54-130">また、既存の Azure AD セキュリティ グループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0d54-130">You can also use an existing Azure AD security group.</span></span>

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a><span data-ttu-id="e0d54-131">Intune と Skycure を統合するように Azure AD アカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="e0d54-131">Configure the Azure AD account to integrate Intune with Skycure</span></span>

1.  <span data-ttu-id="e0d54-132">[Skycure 管理コンソール](https://aad.skycure.com/)から、前にテキスト ファイルに保存した Azure Active Directory テナント ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0d54-132">From the [Skycure Management Console](https://aad.skycure.com/), enter the Azure Active Directory Tenant ID previously saved in the text file.</span></span>

![Skycure 管理コンソールの Azure AD テナント ID フィールド](../media/mtp/skycure-sso-5.png)

> [!IMPORTANT] 
> <span data-ttu-id="e0d54-134">Skycure は Azure AD に問い合わせ、Azure AD テナント ID が存在するかどうかを確認します。存在することがわかると、管理者は次の手順である基本セットアップに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="e0d54-134">Skycure validates if the Azure AD Tenant ID exists by querying Azure AD, once Skycure finds it, the admin can proceed to next step, which is the Basic setup.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e0d54-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="e0d54-135">Next steps</span></span>

[<span data-ttu-id="e0d54-136">Skycure iOS アプリ構成ポリシーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e0d54-136">Download Skycure iOS app configuration policy</span></span>](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)
