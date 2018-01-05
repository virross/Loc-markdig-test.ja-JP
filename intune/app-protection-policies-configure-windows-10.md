---
title: "Windows 10 用のアプリ保護ポリシーを構成する準備をする"
titlesuffix: Azure portal
description: "Azure AD でモバイル アプリケーション管理 (MAM) プロバイダーをセットアップします"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91e26256d220ba70e5ad6daa3910d34eea8bb5ed
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a><span data-ttu-id="0d6f0-103">Windows 10 用のアプリ保護ポリシーを構成する準備をする</span><span class="sxs-lookup"><span data-stu-id="0d6f0-103">Get ready to configure app protection policies for Windows 10</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="0d6f0-104">Azure AD で MAM プロバイダーを設定して、Windows 10 用モバイル アプリケーション管理 (MAM) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-104">Enable mobile application management (MAM) for Windows 10 by setting the MAM provider in Azure AD.</span></span> <span data-ttu-id="0d6f0-105">Azure AD で MAM プロバイダーを設定することで、Intune で新しい Windows 情報保護 (WIP) ポリシーを作成するときに、登録状態を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-105">Setting a MAM provider in Azure AD allows you to define the enrollment state when creating a new Windows Information Protection (WIP) policy with Intune.</span></span> <span data-ttu-id="0d6f0-106">登録状態には、MAM またはモバイル デバイス管理 (MDM) のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-106">The enrollment state can be either MAM or mobile device management (MDM).</span></span>

> [!NOTE]
> <span data-ttu-id="0d6f0-107">MAM の登録状態を持つデバイスは、Azure AD に参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-107">Devices with a MAM enrollment state are required to be Azure AD joined.</span></span>

## <a name="to-configure-the-mam-provider"></a><span data-ttu-id="0d6f0-108">MAM プロバイダーを構成するには</span><span class="sxs-lookup"><span data-stu-id="0d6f0-108">To configure the MAM provider</span></span>

1. <span data-ttu-id="0d6f0-109">Azure Portal にサインインして、**[Azure Active Directory]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-109">Sign in to the Azure portal, and choose **Azure Active Directory.**</span></span>

2. <span data-ttu-id="0d6f0-110">**[管理]** グループで **[モビリティ (MDM および MAM)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-110">Choose **Mobility (MDM and MAM)** in the **Manage** group.</span></span>

3. <span data-ttu-id="0d6f0-111">**[Microsoft Intune]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-111">Click **Microsoft Intune**.</span></span>

4. <span data-ttu-id="0d6f0-112">**[構成]** ブレードの **[既定の MAM URL を復元する]** グループで設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-112">Configure the settings in the  **Restore default MAM URLs** group on the **Configure** blade.</span></span>

    <span data-ttu-id="0d6f0-113">**MAM ユーザー スコープ**</span><span class="sxs-lookup"><span data-stu-id="0d6f0-113">**MAM user scope**</span></span>  
      <span data-ttu-id="0d6f0-114">MAM の自動登録を使用して、従業員の Windows デバイス上のエンタープライズ データを管理します。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-114">Use MAM auto-enrollment to manage enterprise data on your employees' Windows devices.</span></span> <span data-ttu-id="0d6f0-115">MAM 自動登録は、Bring Your Own Device シナリオ向けに構成されます。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-115">MAM auto-enrollment will be configured for bring your own device scenarios.</span></span><ul><li><span data-ttu-id="0d6f0-116">**なし**</span><span class="sxs-lookup"><span data-stu-id="0d6f0-116">**None**</span></span><br><span data-ttu-id="0d6f0-117">MAM にすべてのユーザーを登録する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-117">Select if all users can be enrolled in MAM.</span></span></li><li><span data-ttu-id="0d6f0-118">**一部**</span><span class="sxs-lookup"><span data-stu-id="0d6f0-118">**Some**</span></span><br><span data-ttu-id="0d6f0-119">MAM に登録するユーザーが含まれる Azure AD グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-119">Select Azure AD groups that contain users who will be enrolled in MAM.</span></span></li><li><span data-ttu-id="0d6f0-120">**すべて**</span><span class="sxs-lookup"><span data-stu-id="0d6f0-120">**All**</span></span><br><span data-ttu-id="0d6f0-121">MAM にすべてのユーザーを登録する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-121">Select if all users can be enrolled in MAM.</span></span></li></ul>

    <span data-ttu-id="0d6f0-122">**MAM 使用条件 URL**</span><span class="sxs-lookup"><span data-stu-id="0d6f0-122">**MAM terms of use URL**</span></span>  
     <span data-ttu-id="0d6f0-123">MAM サービスの使用条件エンドポイントの URL です。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-123">The URL of the terms of use endpoint of the MAM service.</span></span> <span data-ttu-id="0d6f0-124">使用条件エンドポイントを使用して、管理対象のデバイスを登録する前に、エンド ユーザーにサービス利用規約を表示できます。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-124">The terms-of-use endpoint is used to display the terms of service to end-users before enrolling their devices for management.</span></span> <span data-ttu-id="0d6f0-125">使用条件のテキストは、モバイル デバイスに適用されるポリシーについてユーザーに案内します。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-125">The terms-of-use text informs users about the policies enforced on the mobile device.</span></span>

    <span data-ttu-id="0d6f0-126">**MAM 探索 URL**</span><span class="sxs-lookup"><span data-stu-id="0d6f0-126">**MAM discovery URL**</span></span>  
    <span data-ttu-id="0d6f0-127">MAM サービスの登録エンドポイントの URL です。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-127">The URL of the enrollment endpoint of the MAM service.</span></span> <span data-ttu-id="0d6f0-128">登録エンドポイントを使用して、MAM サービスによる管理の対象となるデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-128">The enrollment endpoint is used to enroll devices for management with the MAM service.</span></span>

    <span data-ttu-id="0d6f0-129">**MAM 準拠 URL**</span><span class="sxs-lookup"><span data-stu-id="0d6f0-129">**MAM compliance URL**</span></span>  
      <span data-ttu-id="0d6f0-130">MAM サービスの準拠エンドポイントの URL です。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-130">The URL of the compliance endpoint of the MAM service.</span></span> <span data-ttu-id="0d6f0-131">準拠していないデバイスからユーザーがリソースにアクセスしようとして拒否された場合は、準拠 URL へのリンクがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-131">When a user is denied access to a resource from a non-compliant device, a link to the compliance URL is displayed to the user.</span></span> <span data-ttu-id="0d6f0-132">ユーザーは MAM サービスによってホストされるこの URL にアクセスすることで、デバイスが準拠していないと見なされる理由を知ることができます。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-132">Users can navigate to this URL hosted by the MAM service, in order to understand why their device is considered non-compliant.</span></span> <span data-ttu-id="0d6f0-133">また、ユーザーはセルフサービス修復を開始してデバイスを準拠した状態にしてから、リソースへのアクセスを続行することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-133">Users can also initiate self-service remediation so their device becomes compliant and they can continue to access resources.</span></span>

5.  <span data-ttu-id="0d6f0-134">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d6f0-134">Click **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0d6f0-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="0d6f0-135">Next steps</span></span>

[<span data-ttu-id="0d6f0-136">WIP アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0d6f0-136">Create a WIP app protection policy</span></span>](windows-information-protection-policy-create.md)
