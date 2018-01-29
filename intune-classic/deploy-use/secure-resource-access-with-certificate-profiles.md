---
title: "リソース アクセス用の証明書プロファイル"
description: "各ユーザーのデバイスにインストールされている証明書で、VPN、Wi-Fi、および電子メール アクセスを保護します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ccfd69579832c553dc1416c21ca93b85cd93cd78
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="secure-resource-access-with-certificate-profiles-in-microsoft-intune"></a><span data-ttu-id="b5510-103">Secure resource access with certificate profiles in Microsoft Intune (Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する)</span><span class="sxs-lookup"><span data-stu-id="b5510-103">Secure resource access with certificate profiles in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b5510-104">VPN、Wi-Fi、または電子メール プロファイル経由でユーザーが企業リソースへアクセスできるようにする場合、各ユーザー デバイスにインストールされている証明書を使用してこのアクセスを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="b5510-104">When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can secure the access by using a certificate that is installed on each user device.</span></span> <span data-ttu-id="b5510-105">そのしくみは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b5510-105">Here's how it works:</span></span>

1. <span data-ttu-id="b5510-106">「[SCEP の証明書インフラストラクチャを構成する](configure-certificate-infrastructure-for-scep.md)」および「[PFX の証明書インフラストラクチャを構成する](configure-certificate-infrastructure-for-pfx.md)」の説明に従って、適切な証明書インフラストラクチャを構成します。</span><span class="sxs-lookup"><span data-stu-id="b5510-106">Make sure you have the right certificate infrastructure in place, as described in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) and [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md).</span></span>

2. <span data-ttu-id="b5510-107">各デバイスにルート証明書または中間証明機関 (CA) 証明書をインストールして、デバイスが CA の正当性を認識できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b5510-107">Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA.</span></span> <span data-ttu-id="b5510-108">これを行うには、**信頼された証明書プロファイル**を作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="b5510-108">To do this, create and deploy a **Trusted Certificate Profile**.</span></span> <span data-ttu-id="b5510-109">このプロファイルを展開すると、Intune で管理しているデバイスがルート証明書を要求して受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b5510-109">When you deploy this profile, the devices that you manage with Intune will request and receive the root certificate.</span></span> <span data-ttu-id="b5510-110">プラットフォームごとに別個のプロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5510-110">You have to create a separate profile for each platform.</span></span> <span data-ttu-id="b5510-111">**信頼された証明書プロファイル**は、次のプラットフォーム用に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5510-111">The **Trusted Certificate Profile** is available for these platforms:</span></span>
   -  <span data-ttu-id="b5510-112">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="b5510-112">iOS 8.0 and later</span></span>
   -  <span data-ttu-id="b5510-113">Mac OS X 10.9 以降</span><span class="sxs-lookup"><span data-stu-id="b5510-113">Mac OS X 10.9 and later</span></span>
   -  <span data-ttu-id="b5510-114">Android 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="b5510-114">Android 4.0 and later</span></span>
   -  <span data-ttu-id="b5510-115">Android for Work</span><span class="sxs-lookup"><span data-stu-id="b5510-115">Android for Work</span></span>
   -  <span data-ttu-id="b5510-116">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="b5510-116">Windows 8.1 and later</span></span>
   -  <span data-ttu-id="b5510-117">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="b5510-117">Windows Phone 8.1 and later</span></span>

3. <span data-ttu-id="b5510-118">「[Intune 証明書プロファイルを構成する](configure-intune-certificate-profiles.md)」の説明に従って、デバイスが VPN、Wi-Fi、電子メールによるアクセスの認証に使用する証明書を要求するように、証明書プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5510-118">Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access, as described in [Configure Intune certificate profiles](configure-intune-certificate-profiles.md).</span></span> <span data-ttu-id="b5510-119">次のプラットフォームを実行するデバイスに対しては、**PKCS #12 (.PFX) 証明書プロファイル***または* **SCEP 証明書プロファイル**を作成して展開できます。</span><span class="sxs-lookup"><span data-stu-id="b5510-119">You can create and deploy a **PKCS #12 (.PFX) Certificate Profile** *or* a **SCEP Certificate Profile** for devices running these platforms:</span></span>

   -  <span data-ttu-id="b5510-120">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="b5510-120">iOS 8.0 and later</span></span>
   -  <span data-ttu-id="b5510-121">Android 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="b5510-121">Android 4.0 and later</span></span>
   -  <span data-ttu-id="b5510-122">Android for Work</span><span class="sxs-lookup"><span data-stu-id="b5510-122">Android for Work</span></span>
   -  <span data-ttu-id="b5510-123">Windows 10 (Desktop および Mobile) 以降</span><span class="sxs-lookup"><span data-stu-id="b5510-123">Windows 10 (desktop and mobile) and later</span></span>

   <span data-ttu-id="b5510-124">次のプラットフォームを実行するデバイスに対しては、**SCEP 証明書プロファイル**を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5510-124">Use a **SCEP Certificate Profile** for devices running these platforms:</span></span>
    -   <span data-ttu-id="b5510-125">Mac OS X 10.9 以降</span><span class="sxs-lookup"><span data-stu-id="b5510-125">Mac OS X 10.9 and later</span></span>
    -   <span data-ttu-id="b5510-126">Windows Phone 8。1</span><span class="sxs-lookup"><span data-stu-id="b5510-126">Windows Phone 8.1</span></span>

<span data-ttu-id="b5510-127">プラットフォームごとに別個のプロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5510-127">You must create a separate profile for each platform.</span></span> <span data-ttu-id="b5510-128">プロファイルを作成したら、それを既に作成済みの**信頼されたルート証明書プロファイル**に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="b5510-128">When you create the profile, associate it with the **Trusted Root Certificate Profile** that you've already created.</span></span>

> [!NOTE]           
> - <span data-ttu-id="b5510-129">エンタープライズ証明機関がない場合は、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5510-129">If you don't have an Enterprise Certification Authority, you must create one.</span></span>
>- <span data-ttu-id="b5510-130">デバイス プラットフォームに基づいて Simplified Certificate Enrollment Protocol (SCEP) プロファイルを使用することにした場合は、ネットワーク デバイス登録サービス (NDES) サーバーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5510-130">If you decide, based on your device platforms, to use the Simplified Certificate Enrollment Protocol (SCEP) profile, you'll also need to configure a Network Device Enrollment Service (NDES) server.</span></span>
>-  <span data-ttu-id="b5510-131">SCEP プロファイルと .PFX プロファイルのどちらを使用する場合でも、Microsoft Intune 証明書コネクタをダウンロードして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5510-131">Whether you plan to use SCEP or .PFX profiles, you must download and configure the Microsoft Intune Certificate Connector.</span></span>
>-  <span data-ttu-id="b5510-132">すべての必須サービスの構成方法については、「[SCEP の証明書インフラストラクチャを構成する](configure-certificate-infrastructure-for-scep.md)」と「[PFX の証明書インフラストラクチャを構成する](configure-certificate-infrastructure-for-pfx.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5510-132">Learn how to configure all of the required services in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) or [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md).</span></span>

### <a name="next-steps"></a><span data-ttu-id="b5510-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="b5510-133">Next steps</span></span>
- [<span data-ttu-id="b5510-134">SCEP の証明書インフラストラクチャを構成する</span><span class="sxs-lookup"><span data-stu-id="b5510-134">Configure certificate infrastructure for SCEP</span></span>](configure-certificate-infrastructure-for-scep.md)
- [<span data-ttu-id="b5510-135">PFX の証明書インフラストラクチャを構成する</span><span class="sxs-lookup"><span data-stu-id="b5510-135">Configure certificate infrastructure for PFX</span></span>](configure-certificate-infrastructure-for-pfx.md)
- [<span data-ttu-id="b5510-136">Intune 証明書プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="b5510-136">Configure Intune certificate profiles</span></span>](configure-intune-certificate-profiles.md)
