---
title: "Skycure と Intune の統合をセットアップする"
titlesuffix: Azure portal
description: "Skycure と Microsoft Intune の統合をセットアップします。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d495046a990817e73fcee385b3a1482229aac721
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-the-skycure-integration-with-intune"></a><span data-ttu-id="a4d8f-103">Skycure と Intune の統合をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a4d8f-103">Set up the Skycure integration with Intune</span></span>

<span data-ttu-id="a4d8f-104">シングル サインオン機能を与えるには、Skycure アプリを Azure AD に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-104">You need to add Skycure apps into Azure AD to have Single Sign On capabilities.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a4d8f-105">始める前に</span><span class="sxs-lookup"><span data-stu-id="a4d8f-105">Before you begin</span></span>

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a><span data-ttu-id="a4d8f-106">Intune と Skycure を統合するために使用する Azure AD アカウント</span><span class="sxs-lookup"><span data-stu-id="a4d8f-106">Azure AD account used to integrate Intune and Skycure</span></span>

-   <span data-ttu-id="a4d8f-107">Skycure の基本セットアップ プロセスを開始する前に、[Skycure 管理コンソール](https://aad.skycure.com)で Azure AD アカウントを適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-107">Make sure you have the Azure AD account properly configured in the [Skycure Management console](https://aad.skycure.com), before starting the Skycure Basic setup process.</span></span>

### <a name="full-integration-vs-read-only"></a><span data-ttu-id="a4d8f-108">比較: 完全統合と読み取り専用</span><span class="sxs-lookup"><span data-stu-id="a4d8f-108">Full integration vs. Read-only</span></span>

<span data-ttu-id="a4d8f-109">Skycure では、Intune との統合に 2 つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-109">Skycure supports two modes of integration with Intune:</span></span>

-   <span data-ttu-id="a4d8f-110">**読み取り専用統合 (基本セットアップ):** Azure Active Directory からのデバイスのみが目録を作成し、それらを Skycure コンソールに入力します。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-110">**Read-only integration (Basic setup):** Only inventories devices from Azure Active Directory and populates them in the Skycure console.</span></span>
<br>
    -   <span data-ttu-id="a4d8f-111">Skycure 管理コンソールで **[Report the health and risk of devices to Intune (デバイスの健全性とリスクを Intune に報告する)]** ボックスと **[Also report security incidents to Intune (セキュリティ インシデントも Intune に報告する)]** ボックスが選択されていない場合、統合は読み取り専用となり、Intune でデバイスの状態 (準拠または非準拠) が変化することはありません。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-111">If the **Report the health and risk of devices to Intune**, and **Also report security incidents to Intune** boxes are not selected in the Skycure Management console, the integration is read-only and therefore will never change a devices state (compliant or non-compliant) in Intune.</span></span>
<br></br>
-   <span data-ttu-id="a4d8f-112">**完全統合:** デバイスのリスクとセキュリティ インシデントの詳細を Intune に報告することを Skycure に許可します。Intune は両方のクラウド サービス間で双方向通信を構築します。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-112">**Full integration:** Allows Skycure to report devices on risk and security incident details to Intune, which creates a bi-directional communication between both cloud services.</span></span>

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a><span data-ttu-id="a4d8f-113">Azure AD と Intune で Skycure アプリはどのような方法で使用されますか?</span><span class="sxs-lookup"><span data-stu-id="a4d8f-113">How the Skycure apps are used with Azure AD and Intune?</span></span>

-   <span data-ttu-id="a4d8f-114">**iOS アプリ:** エンドユーザーは iOS アプリを利用し、Azure AD にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-114">**iOS app:** Allows end-users to sign in to Azure AD using an iOS app.</span></span>

-   <span data-ttu-id="a4d8f-115">**Android アプリ:** エンドユーザーは Android アプリを利用し、Azure AD にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-115">**Android app:** Allows end-users to sign in to Azure AD using an Android app.</span></span>

-   <span data-ttu-id="a4d8f-116">**管理アプリ:** これは、Intune とのサービス間通信を可能にする Skycure Azure AD マルチテナント アプリです。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-116">**Management app:** This is the Skycure Azure AD multi-tenant app which enables service-to-service communication with Intune.</span></span>

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a><span data-ttu-id="a4d8f-117">Intune と Skycure の間に読み取り専用の統合を設定するには</span><span class="sxs-lookup"><span data-stu-id="a4d8f-117">To set up the read-only integration between Intune and Skycure</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4d8f-118">Skycure 管理者の資格情報は電子メールですが、そのメールは Azure Active Directory の有効なユーザーに属している必要があります。属していない場合、ログインは失敗します。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-118">The Skycure admin credentials is an e-mail that must belong to a valid user in the Azure Active Directory, otherwise the login will fail.</span></span> <span data-ttu-id="a4d8f-119">Skycure は、シングル サインオン (SSO) を使用して、管理者の認証に Azure Active Directory を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-119">Skycure uses Azure Active Directory to authenticate its admin using Single Sign On (SSO).</span></span>

1.  <span data-ttu-id="a4d8f-120">[Skycure 管理コンソール](https://aad.skycure.com)に進みます。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-120">Go to [Skycure Management Console](https://aad.skycure.com).</span></span>

2.  <span data-ttu-id="a4d8f-121">自分の **Skycure 管理者資格情報**を入力し、**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-121">Enter your **Skycure admin credentials**, then click **Continue**.</span></span>

3.  <span data-ttu-id="a4d8f-122">**[設定]** に進み、**[Intune との統合]** で **[基本セットアップ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-122">Go to **Settings**, choose **Basic Setup** under **Intune Integration**.</span></span>

4.  <span data-ttu-id="a4d8f-123">**[iOS アプリ]** ラベルで、**[Add to Active Directory (Active Directory に追加)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-123">On the **iOS App** label, click on **Add to Active Directory**.</span></span>

    ![Skycure 管理コンソールの iOS アプリ](./media/skycure-setup-1.png)

5.  <span data-ttu-id="a4d8f-125">ログイン ページが開いたら、Intune 資格情報を入力し、**[同意する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-125">Login page opens, enter your Intune credentials, then click **Accept**.</span></span>

    ![iOS アプリの Intune ログイン プロンプト](./media/skycure-setup-2.png)

6.  <span data-ttu-id="a4d8f-127">アプリが Azure AD に追加されると、Skycure 管理コンソールでアプリが Azure AD に追加されたというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-127">Once the app is added into Azure AD, you can see an indication that the app was successfully added into Azure AD on the Skycure Management console.</span></span>

    ![iOS アプリの完了画面](./media/skycure-setup-3.png)

> [!NOTE]
> <span data-ttu-id="a4d8f-129">**Skycure Android** アプリと**管理**アプリで同じプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-129">Repeat the same process for the **Skycure Android** and **Management** apps.</span></span>

### <a name="add-an-azure-ad-security-group-into-skycure"></a><span data-ttu-id="a4d8f-130">Skycure に Azure AD セキュリティ グループを追加する</span><span class="sxs-lookup"><span data-stu-id="a4d8f-130">Add an Azure AD Security group into Skycure</span></span>

<span data-ttu-id="a4d8f-131">Skycure を実行しているすべてのデバイスを含む Azure AD セキュリティ グループを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-131">You need to add an Azure AD security group that contains all devices running Skycure.</span></span>

1.  <span data-ttu-id="a4d8f-132">Skycure を実行しているデバイスのセキュリティ グループをすべて入力し、選択し、**[変更の適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-132">Enter and select all the security groups of devices that are running Skycure, then click on **Apply changes**.</span></span>

    ![セキュリティ グループ Skycure 管理コンソールを構成する](./media/skycure-setup-4.png)

<span data-ttu-id="a4d8f-134">Skycure は、Mobile Threat Defense サービスを実行しているデバイスと Azure AD セキュリティ グループを同期します。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-134">Skycure syncs the devices running its Mobile Threat Defense service with the Azure AD security groups.</span></span>

![Skycure 管理コンソールで完了したセキュリティ グループの構成](./media/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a><span data-ttu-id="a4d8f-136">Intune と Skycure の間に完全統合を設定する</span><span class="sxs-lookup"><span data-stu-id="a4d8f-136">Set up the full integration between Intune and Skycure</span></span>

1.  <span data-ttu-id="a4d8f-137">[Skycure 管理コンソール](https://aad.skycure.com)に進みます。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-137">Go to [Skycure Management Console](https://aad.skycure.com).</span></span>

2.  <span data-ttu-id="a4d8f-138">自分の **Skycure 管理者資格情報**を入力し、**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-138">Enter your **Skycure admin credentials**, then click **Continue**.</span></span>

3.  <span data-ttu-id="a4d8f-139">**[設定]** に進み、**[Intune との統合]** で **[完全統合]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-139">Go to **Settings**, choose **Full Integration** under **Intune Integration**.</span></span>

4.  <span data-ttu-id="a4d8f-140">次の設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-140">Check the following settings:</span></span>

    <span data-ttu-id="a4d8f-141">a.</span><span class="sxs-lookup"><span data-stu-id="a4d8f-141">a.</span></span>  <span data-ttu-id="a4d8f-142">デバイスの健全性とリスクを Intune に報告する</span><span class="sxs-lookup"><span data-stu-id="a4d8f-142">Report the health and risk of device to Intune</span></span>

    <span data-ttu-id="a4d8f-143">b.</span><span class="sxs-lookup"><span data-stu-id="a4d8f-143">b.</span></span>  <span data-ttu-id="a4d8f-144">セキュリティ インシデントも Intune に報告する</span><span class="sxs-lookup"><span data-stu-id="a4d8f-144">Also report security incidents to Intune</span></span>

5.  <span data-ttu-id="a4d8f-145">**[変更の適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-145">Click on **Apply changes**.</span></span>

    ![Skycure の完全統合の完了](./media/skycure-setup-6.png)

## <a name="next-steps"></a><span data-ttu-id="a4d8f-147">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a4d8f-147">Next steps</span></span>

[<span data-ttu-id="a4d8f-148">Skycure アプリを設定する</span><span class="sxs-lookup"><span data-stu-id="a4d8f-148">Set up Skycure apps</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)
