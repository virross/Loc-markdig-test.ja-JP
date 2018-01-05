---
title: "Check Point SandBlast と Intune の統合をセットアップする"
titlesuffix: Azure portal
description: "Check Point SandBlast と Intune の統合をセットアップします"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a4560ab65ecd1d30492ae2a1a2f136511195c674
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="integrate-check-point-sandblast-mobile-with-intune"></a><span data-ttu-id="1cfce-103">Check Point SandBlast Mobile と Intune を統合します</span><span class="sxs-lookup"><span data-stu-id="1cfce-103">Integrate Check Point SandBlast Mobile with Intune</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1cfce-104">始める前に</span><span class="sxs-lookup"><span data-stu-id="1cfce-104">Before you begin</span></span>

> [!NOTE] 
> <span data-ttu-id="1cfce-105">以下の手順は、[Check Point SandBlast Mobile MTD コンソール](https://intune-4.eu1.locsec.net/)で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cfce-105">The steps below need to be taken in the [Check Point SandBlast Mobile MTD console](https://intune-4.eu1.locsec.net/).</span></span>

<span data-ttu-id="1cfce-106">Check Point SandBlast Mobile と Intune の統合を始める前に、次のものがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1cfce-106">Before starting the process of integrating Check Point SandBlast Mobile with Intune, make sure you have the following:</span></span>

-   <span data-ttu-id="1cfce-107">Microsoft Intune サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="1cfce-107">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="1cfce-108">次のアクセス許可を付与する Azure Active Directory 管理者資格情報:</span><span class="sxs-lookup"><span data-stu-id="1cfce-108">Azure Active Directory admin credentials to grant the following permissions:</span></span>

    -   <span data-ttu-id="1cfce-109">サインインしてユーザー プロファイルを読み取る</span><span class="sxs-lookup"><span data-stu-id="1cfce-109">Sign in and read user profile</span></span>

    -   <span data-ttu-id="1cfce-110">サインインしたユーザーとしてディレクトリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="1cfce-110">Access the directory as the signed-in user</span></span>

    -   <span data-ttu-id="1cfce-111">ディレクトリ データの読み込み</span><span class="sxs-lookup"><span data-stu-id="1cfce-111">Read directory data</span></span>

    -   <span data-ttu-id="1cfce-112">Intune にデバイス情報を送信する</span><span class="sxs-lookup"><span data-stu-id="1cfce-112">Send device information to Intune</span></span>

-   <span data-ttu-id="1cfce-113">Check Point SandBlast Mobile MTD コンソールにアクセスするための管理者資格情報</span><span class="sxs-lookup"><span data-stu-id="1cfce-113">Admin credentials to access Check Point SandBlast Mobile MTD console.</span></span>

### <a name="check-point-sandblast-app-authorization"></a><span data-ttu-id="1cfce-114">Check Point SandBlast アプリの承認</span><span class="sxs-lookup"><span data-stu-id="1cfce-114">Check Point SandBlast app authorization</span></span>

<span data-ttu-id="1cfce-115">Check Point SandBlast アプリ承認プロセスは以下で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1cfce-115">The Check Point SandBlast app authorization process consists of the following:</span></span>

-   <span data-ttu-id="1cfce-116">Check Point SandBlast Mobile サービスがデバイスの正常性状態に関する情報を Intune に通知できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1cfce-116">Allow the Check Point SandBlast Mobile service to communicate information related to device health state back to Intune.</span></span>

-   <span data-ttu-id="1cfce-117">Check Point SandBlast Mobile は、Azure AD 登録グループ メンバーシップと同期してデバイスのデータベースを設定します。</span><span class="sxs-lookup"><span data-stu-id="1cfce-117">CheckPoint SandBlast Mobile syncs with Azure AD Enrollment Group membership to populate its device’s database.</span></span>

-   <span data-ttu-id="1cfce-118">Check Point SandBlast 管理者コンソールが Azure AD シングル サインオン (SSO) を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1cfce-118">Allow Check Point SandBlast admin console to use Azure AD Single Sign On (SSO).</span></span>

-   <span data-ttu-id="1cfce-119">Check Point SandBlast Mobile アプリが Azure AD SSO を使ってサインインできるようにします。</span><span class="sxs-lookup"><span data-stu-id="1cfce-119">Allow the Check Point SandBlast Mobile app to sign in using Azure AD SSO.</span></span>

## <a name="to-set-up-check-point-sandblast-mobile-integration"></a><span data-ttu-id="1cfce-120">Check Point SandBlast Mobile の統合をセットアップするには</span><span class="sxs-lookup"><span data-stu-id="1cfce-120">To set up Check Point SandBlast Mobile integration</span></span>

1.  <span data-ttu-id="1cfce-121">[Check Point SandBlast Mobile MTD コンソール](https://intune-4.eu1.locsec.net/)に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="1cfce-121">Go to [Check Point SandBlast Mobile MTD console](https://intune-4.eu1.locsec.net/) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="1cfce-122">**[設定]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cfce-122">Click on the **Settings** tab.</span></span>

3.  <span data-ttu-id="1cfce-123">**[Device management\(デバイス管理\)]**、**[設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1cfce-123">Choose **Device management**, then **Settings**.</span></span>

4.  <span data-ttu-id="1cfce-124">**[MDM Service\(MDM サービス\)]** ドロップダウン リストから **[Microsoft Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cfce-124">Choose **Microsoft Intune** from the **MDM Service** drop-down list.</span></span>

5.  <span data-ttu-id="1cfce-125">Microsoft Intune を MDM サービスとして設定するとポップアップする **[Microsoft Intune Configuration\(Microsoft Intune の構成\)]** ウィンドウで、各デバイス プラットフォーム (iOS、Android、Windows) の **[Add to my organization\(組織に追加する\)]** を選択して、Check Point SandBlast Mobile が Intune および Azure AD と通信することを承認します。</span><span class="sxs-lookup"><span data-stu-id="1cfce-125">Once you set Microsoft Intune as the MDM Service, the **Microsoft Intune Configuration** window pops up, choose the **Add to my organization** for each device platform: iOS, Android and Windows to authorize Check Point SandBlast Mobile to communicate with Intune and Azure AD.</span></span>

    ![Check Point MTD Intune の構成](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="1cfce-127">次の手順に進むには、すべてのデバイス プラットフォームを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cfce-127">You must add all device platforms to proceed to the next step.</span></span>

6.  <span data-ttu-id="1cfce-128">**[Accept\(承認\)]** を選択して、Check Point SandBlast Mobile アプリが Intune および Azure Active Directory と通信することを承認します。</span><span class="sxs-lookup"><span data-stu-id="1cfce-128">Choose **Accept** to authorize the Check Point SandBlast Mobile app to communicate with Intune and Azure Active Directory.</span></span>

7.  <span data-ttu-id="1cfce-129">すべてのデバイス プラットフォームを有効にした後、Azure AD セキュリティ グループを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cfce-129">Once you enabled all device platforms, you need to enter the Azure AD security group.</span></span>

8.  <span data-ttu-id="1cfce-130">**[Verify\(確認\)]** を選択し、Azure AD セキュリティ グループが正常に検証された後、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cfce-130">Choose **Verify**, once the Azure AD security group is successfully verified, choose **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1cfce-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="1cfce-131">Next steps</span></span>

- [<span data-ttu-id="1cfce-132">Check Point SandBlast Mobile アプリをセットアップする</span><span class="sxs-lookup"><span data-stu-id="1cfce-132">Set up Check Point SandBlast Mobile apps</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)