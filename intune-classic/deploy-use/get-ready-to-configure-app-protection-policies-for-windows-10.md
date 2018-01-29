---
title: "Windows 10 用のアプリ保護ポリシーを構成する準備をする"
description: "Azure AD でモバイル アプリケーション管理 (MAM) プロバイダーをセットアップします"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 274145893ced95da940d8060736330698e1df16d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a><span data-ttu-id="769a3-103">Windows 10 用のアプリ保護ポリシーを構成する準備をする</span><span class="sxs-lookup"><span data-stu-id="769a3-103">Get ready to configure app protection policies for Windows 10</span></span>

[!INCLUDE [note for both-portals](../includes/note-for-both-portals.md)]

<span data-ttu-id="769a3-104">Windows 10 のアプリ保護ポリシーを作成する前に、Azure AD でモバイル アプリケーション管理 (MAM) プロバイダーを設定することにより、Windows 10 用に MAM を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="769a3-104">Before creating a Windows 10 app protection policy using, you need to enable mobile application management (MAM) for Windows 10 by setting up the MAM provider in Azure AD.</span></span> <span data-ttu-id="769a3-105">この構成を行うことで、Intune で新しい Windows 情報保護 (WIP) ポリシーを作成するときに、登録状態を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="769a3-105">This configuration allows you to define the enrollment state when creating a new Windows Information Protection (WIP) policy with Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="769a3-106">登録状態には、MAM またはモバイル デバイス管理 (MDM) のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="769a3-106">The enrollment state can be either MAM or mobile device management (MDM).</span></span>

## <a name="to-configure-the-mam-provider"></a><span data-ttu-id="769a3-107">MAM プロバイダーを構成するには</span><span class="sxs-lookup"><span data-stu-id="769a3-107">To configure the MAM provider</span></span>

1.  <span data-ttu-id="769a3-108">[Azure Portal](https://portal.azure.com/) に移動し、Intune 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="769a3-108">Go to the [Azure portal](https://portal.azure.com/) and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="769a3-109">左側のメニューで、**[Azure Active Directory]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="769a3-109">From the left menu, choose **Azure Active Directory**.</span></span>

    ![MAM プロバイダーの構成](../media/AppManagement/mam-provider-sc-1.png)

3.  <span data-ttu-id="769a3-111">**[Azure AD]** ブレードが開くので、**[モビリティ (MDM および MAM)]** を選択し、**[Microsoft Intune]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="769a3-111">**Azure AD** blade opens, choose **Mobility (MDM and MAM)**, then click **Microsoft Intune**.</span></span>

    ![モビリティ MDM および MAM](../media/AppManagement/mam-provider-sc-2.png)

4.  <span data-ttu-id="769a3-113">構成ブレードが開くので、**[既定の MAM URL を復元する]** を最初に選んでから、以下を構成します。</span><span class="sxs-lookup"><span data-stu-id="769a3-113">The configure blade opens, choose **Restore default MAM URLs** first, then configure the following:</span></span>

    <span data-ttu-id="769a3-114">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="769a3-114">a.</span></span>  <span data-ttu-id="769a3-115">[MAM ユーザー スコープ]: MAM を使って、Windows 10 デバイスを使う特定のユーザー グループまたはすべてのユーザーの企業データを保護できます。</span><span class="sxs-lookup"><span data-stu-id="769a3-115">MAM user scope: You can use MAM to protect corporate data on specific group of users that use Windows 10 devices or all users.</span></span>

    <span data-ttu-id="769a3-116">b.</span><span class="sxs-lookup"><span data-stu-id="769a3-116">b.</span></span>  <span data-ttu-id="769a3-117">[MAM 使用条件 URL]: MAM サービスの使用条件エンドポイントの URL です。</span><span class="sxs-lookup"><span data-stu-id="769a3-117">MAM terms of use URL: The URL of the terms of use endpoint of the MAM service.</span></span> <span data-ttu-id="769a3-118">これは、MAM サービスの使用条件をエンドユーザーに表示するために使います。</span><span class="sxs-lookup"><span data-stu-id="769a3-118">This is used to display the term of MAM service to end-users.</span></span>

    <span data-ttu-id="769a3-119">c.</span><span class="sxs-lookup"><span data-stu-id="769a3-119">c.</span></span>  <span data-ttu-id="769a3-120">[MAM 探索 URL]: アプリ保護ポリシーを適用する必要があるときにデバイスが探索する URL です。</span><span class="sxs-lookup"><span data-stu-id="769a3-120">MAM discovery URL: This the URL devices seek when they need to apply app protection policies.</span></span>

    <span data-ttu-id="769a3-121">d.</span><span class="sxs-lookup"><span data-stu-id="769a3-121">d.</span></span>  <span data-ttu-id="769a3-122">[MAM 準拠 URL]:</span><span class="sxs-lookup"><span data-stu-id="769a3-122">MAM compliance URL:</span></span>

5.  <span data-ttu-id="769a3-123">これらの設定を構成した後、**[保存]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="769a3-123">Once you configure these settings, choose **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="769a3-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="769a3-124">Next steps</span></span>

[<span data-ttu-id="769a3-125">WIP アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="769a3-125">Create a WIP app protection policy</span></span>](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)
