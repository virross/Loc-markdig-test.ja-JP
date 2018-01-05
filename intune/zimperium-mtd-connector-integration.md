---
title: "Zimperium を Intune と統合する"
titleSuffix: Intune on Azure
description: "Intune を Zimperium と統合する"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b4adb2db14c2e1c83be8e7b3644944c1910cb97
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="integrate-zimperium-with-intune"></a><span data-ttu-id="a867c-103">Zimperium を Intune と統合する</span><span class="sxs-lookup"><span data-stu-id="a867c-103">Integrate Zimperium with Intune</span></span>

<span data-ttu-id="a867c-104">Zimperium Mobile Threat Defense ソリューションを Intune と統合するには、以下の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a867c-104">You need to follow the steps below to integrate the Zimperium Mobile Threat Defense solution with Intune.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a867c-105">始める前に</span><span class="sxs-lookup"><span data-stu-id="a867c-105">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="a867c-106">[Zimperium MTD コンソール](https://staging2-console.zimperium.com)で、以下の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a867c-106">The steps below need to be taken in the [Zimperium MTD console](https://staging2-console.zimperium.com).</span></span>

<span data-ttu-id="a867c-107">Zimperium と Intune の統合を始める前に、次のものがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a867c-107">Before starting the process of integrating Zimperium with Intune, make sure you have the following:</span></span>

-   <span data-ttu-id="a867c-108">Microsoft Intune サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="a867c-108">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="a867c-109">次のアクセス許可を付与する Azure Active Directory 管理者資格情報:</span><span class="sxs-lookup"><span data-stu-id="a867c-109">Azure Active Directory admin credentials to grant the following permissions:</span></span>

    -   <span data-ttu-id="a867c-110">サインインしてユーザー プロファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="a867c-110">Sign in and read user profile</span></span>

    -   <span data-ttu-id="a867c-111">サインインしたユーザーとしてディレクトリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="a867c-111">Access the directory as the signed-in user</span></span>

    -   <span data-ttu-id="a867c-112">ディレクトリ データの読み込み</span><span class="sxs-lookup"><span data-stu-id="a867c-112">Read directory data</span></span>

    -   <span data-ttu-id="a867c-113">Intune にデバイス情報を送信する</span><span class="sxs-lookup"><span data-stu-id="a867c-113">Send device information to Intune</span></span>

-   <span data-ttu-id="a867c-114">Zimperium MTD コンソールにアクセスするための管理者資格情報。</span><span class="sxs-lookup"><span data-stu-id="a867c-114">Admin credentials to access Zimperium MTD console.</span></span>

### <a name="zimperium-app-authorization"></a><span data-ttu-id="a867c-115">Zimperium アプリの承認</span><span class="sxs-lookup"><span data-stu-id="a867c-115">Zimperium app authorization</span></span>

<span data-ttu-id="a867c-116">Zimperium アプリ承認プロセスは以下で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a867c-116">The Zimperium app authorization process consists of the following:</span></span>

-   <span data-ttu-id="a867c-117">Zimperium サービスがデバイスの正常性状態に関する情報を Intune に通知できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a867c-117">Allow the Zimperium service to communicate information related to device health state back to Intune.</span></span>

-   <span data-ttu-id="a867c-118">Zimperium は、Azure AD 登録グループ メンバーシップと同期してデバイスのデータベースを設定します。</span><span class="sxs-lookup"><span data-stu-id="a867c-118">Zimperium syncs with Azure AD Enrollment Group membership to populate its device’s database.</span></span>

-   <span data-ttu-id="a867c-119">Zimperium 管理者コンソールが Azure AD シングル サインオン (SSO) を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a867c-119">Allow Zimperium admin console to use Azure AD Single Sign On (SSO).</span></span>

-   <span data-ttu-id="a867c-120">Zimperium アプリが Azure AD SSO を使用してサインインできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a867c-120">Allow the Zimperium app to sign in using Azure AD SSO.</span></span>

## <a name="to-set-up-zimperium-integration"></a><span data-ttu-id="a867c-121">Zimperium の統合を設定するには</span><span class="sxs-lookup"><span data-stu-id="a867c-121">To set up Zimperium integration</span></span>

1.  <span data-ttu-id="a867c-122">[Zimperium MTD コンソール](https://staging2-console.zimperium.com)に移動し、資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a867c-122">Go to [Zimperium MTD console](https://staging2-console.zimperium.com) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="a867c-123">左のメニューから **[Management]\(管理\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a867c-123">Choose **Management** from the left menu.</span></span>

3.  <span data-ttu-id="a867c-124">**[MDM settings]\(MDM の設定\)** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a867c-124">Choose the **MDM settings** tab.</span></span>

4.  <span data-ttu-id="a867c-125">**[Add MDM]\(MDM の追加\)** を選択し、**[MDM provider]\(MDM プロバイダー\)** 一覧から **[Microsoft Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a867c-125">Choose **Add MDM,** then select **Microsoft Intune** from the **MDM provider** list.</span></span>

5.  <span data-ttu-id="a867c-126">Microsoft Intune を MDM サービスとして設定すると、**[Microsoft Intune Configuration]\(Microsoft Intune 構成\)** ウィンドウが開くので、**[Zimperium zConsole]** と **[zIPS iOS and Android apps]\(zIPS iOS および Android アプリ\)** オプションのそれぞれに **[Add Azure Active Directory]\(Azure Active Directory 追加\)** を選択します。これらのオプションは Zimperium が Azure AD シングル サインオンを使用して Intune および Azure AD と通信することを承認するものです。</span><span class="sxs-lookup"><span data-stu-id="a867c-126">Once you set Microsoft Intune as the MDM service, the **Microsoft Intune Configuration** window pops up, choose the **Add Azure Active Directory** for each option: **Zimperium zConsole**, **zIPS iOS and Android apps** to authorize Zimperium to communicate with Intune and Azure AD through Azure AD Single Sign-On.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a867c-127">Intune との統合プロセスを完了するには、Zimperium zConsole、zIPS iOS および Android アプリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a867c-127">You must add the Zimperium zConsole, zIPS iOS and Android apps to complete to the integration process with Intune.</span></span>

6.  <span data-ttu-id="a867c-128">**[Accept\(承認\)]** を選択して、Zimperium アプリが Intune および Azure Active Directory と通信することを承認します。</span><span class="sxs-lookup"><span data-stu-id="a867c-128">Choose **Accept** to authorize the Zimperium app to communicate with Intune and Azure Active Directory.</span></span>

7.  <span data-ttu-id="a867c-129">**[Zimperium zConsole]** および **[zIPS iOS and Android]\(zIPS および Android\)** アプリを Azure AD に追加したら、Zimperium が Azure AD セキュリティ グループとそのサービスを同期できるように Azure AD セキュリティ グループを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a867c-129">Once you added the **Zimperium zConsole** and the **zIPS iOS and Android** apps to Azure AD, you need to add the Azure AD security groups so Zimperium can synchronize the Azure AD security group with its service.</span></span>

8.  <span data-ttu-id="a867c-130">**[Finish]\(完了\)** を選択して構成を保存し、最初の Azure AD セキュリティ グループの同期を開始します。</span><span class="sxs-lookup"><span data-stu-id="a867c-130">Choose **Finish** to save the configuration and start the first Azure AD security group synchronization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a867c-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="a867c-131">Next steps</span></span>

-   [<span data-ttu-id="a867c-132">Zimperium アプリを設定する</span><span class="sxs-lookup"><span data-stu-id="a867c-132">Set up Zimperium apps</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)
