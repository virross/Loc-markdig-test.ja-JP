---
title: "Intune で証明書を構成する方法"
titlesuffix: Azure portal
description: "Wi-Fi や VPN などの接続をセキュリティで保護するのに役立つ証明書を、Intune を使用して作成し、割り当てる方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9c74ee1daf6602a4958d9955c3955b465495e013
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-certificates-in-microsoft-intune"></a><span data-ttu-id="c3b70-103">Microsoft Intune で証明書を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c3b70-103">How to configure certificates in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="c3b70-104">VPN、Wi-Fi、または電子メール プロファイル経由でユーザーが企業リソースへアクセスできるようにする場合、証明書を使用してこれらの接続を認証することができます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-104">When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can authenticate these connections by using certificates.</span></span> <span data-ttu-id="c3b70-105">証明書を使用する場合は、接続の認証にユーザー名とパスワードを入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c3b70-105">You don't need to enter user names and passwords to authenticate connections when you use certificates.</span></span>

<span data-ttu-id="c3b70-106">Intune を使用して、管理するデバイスに証明書を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-106">You can use Intune to assign these certificates to devices you manage.</span></span> <span data-ttu-id="c3b70-107">Intune では、次の種類の証明書の割り当てと管理がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c3b70-107">Intune supports assigning and managing these certificate types:</span></span>

- <span data-ttu-id="c3b70-108">Simple Certificate Enrollment Protocol (SCEP)</span><span class="sxs-lookup"><span data-stu-id="c3b70-108">Simple Certificate Enrollment Protocol (SCEP)</span></span>
- <span data-ttu-id="c3b70-109">PKCS#12 (または PFX)</span><span class="sxs-lookup"><span data-stu-id="c3b70-109">PKCS#12 (or PFX)</span></span>

<span data-ttu-id="c3b70-110">これらの証明書の種類には、それぞれ独自の前提条件とインフラストラクチャの要件があります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-110">Each of these certificate types has its own prerequisites and infrastructure requirements.</span></span>

## <a name="general-workflow"></a><span data-ttu-id="c3b70-111">一般的なワークフロー</span><span class="sxs-lookup"><span data-stu-id="c3b70-111">General workflow</span></span>

1. <span data-ttu-id="c3b70-112">適切な証明書インフラストラクチャを構成します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-112">Ensure you have the right certificate infrastructure in place.</span></span> <span data-ttu-id="c3b70-113">[SCEP 証明書](certificates-scep-configure.md)および [PKCS 証明書](certficates-pfx-configure.md)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-113">You can use [SCEP certificates](certificates-scep-configure.md), and [PKCS certificates](certficates-pfx-configure.md).</span></span>
2. <span data-ttu-id="c3b70-114">各デバイスにルート証明書または中間証明機関 (CA) 証明書をインストールして、デバイスが CA の正当性を認識できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c3b70-114">Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA.</span></span> <span data-ttu-id="c3b70-115">これを行うには、**信頼された証明書プロファイル**を作成して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-115">To do this, create and assign a **trusted certificate profile**.</span></span> <span data-ttu-id="c3b70-116">このプロファイルを割り当てると、Intune で管理しているデバイスがルート証明書を要求して受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-116">When you assign this profile, the devices that you manage with Intune request and receive the root certificate.</span></span> <span data-ttu-id="c3b70-117">プラットフォームごとに別個のプロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-117">You must create a separate profile for each platform.</span></span> <span data-ttu-id="c3b70-118">信頼された証明書プロファイルは、次のプラットフォーム用に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-118">Trusted certificate profiles are available for these platforms:</span></span>
    - <span data-ttu-id="c3b70-119">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-119">iOS 8.0 and later</span></span>
    - <span data-ttu-id="c3b70-120">macOS 10.9 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-120">macOS 10.9 and later</span></span>
    - <span data-ttu-id="c3b70-121">Android 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-121">Android 4.0 and later</span></span>
    - <span data-ttu-id="c3b70-122">Android for Work</span><span class="sxs-lookup"><span data-stu-id="c3b70-122">Android for Work</span></span>
    - <span data-ttu-id="c3b70-123">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-123">Windows 8.1 and later</span></span>
    - <span data-ttu-id="c3b70-124">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-124">Windows Phone 8.1 and later</span></span>
    - <span data-ttu-id="c3b70-125">Windows 10 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-125">Windows 10 and later</span></span>
3. <span data-ttu-id="c3b70-126">デバイスが VPN、Wi-Fi、電子メールによるアクセスの認証に使用する証明書を要求するように、証明書プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-126">Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access.</span></span>

   <span data-ttu-id="c3b70-127">次のプラットフォームを実行するデバイスに対しては、**PKCS** または **SCEP** 証明書プロファイルを作成し、割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-127">You can create and assign a **PKCS** or **SCEP** certificate profile for devices running these platforms:</span></span>

   - <span data-ttu-id="c3b70-128">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-128">iOS 8.0 and later</span></span>
   - <span data-ttu-id="c3b70-129">Android 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-129">Android 4.0 and later</span></span>
   - <span data-ttu-id="c3b70-130">Android for Work</span><span class="sxs-lookup"><span data-stu-id="c3b70-130">Android for Work</span></span>
   - <span data-ttu-id="c3b70-131">Windows 10 (Desktop および Mobile) 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-131">Windows 10 (desktop and mobile) and later</span></span>

   <span data-ttu-id="c3b70-132">次のプラットフォームを実行するデバイスの場合は、**SCEP** 証明書プロファイルを使用できるだけです。</span><span class="sxs-lookup"><span data-stu-id="c3b70-132">You can only use a **SCEP** certificate profile for devices running these platforms:</span></span>

   - <span data-ttu-id="c3b70-133">macOS 10.9 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-133">macOS 10.9 and later</span></span>
   - <span data-ttu-id="c3b70-134">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="c3b70-134">Windows Phone 8.1 and later</span></span>

<span data-ttu-id="c3b70-135">デバイス プラットフォームごとに別個のプロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-135">You must create a separate profile for each device platform.</span></span> <span data-ttu-id="c3b70-136">プロファイルを作成したら、それを既に作成済みの信頼されたルート証明書プロファイルに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-136">When you create the profile, associate it with the trusted root certificate profile that you've already created.</span></span>

### <a name="further-considerations"></a><span data-ttu-id="c3b70-137">その他の注意事項</span><span class="sxs-lookup"><span data-stu-id="c3b70-137">Further considerations</span></span>

- <span data-ttu-id="c3b70-138">エンタープライズ証明機関がない場合は、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-138">If you don't have an Enterprise Certification Authority, you must create one.</span></span>
- <span data-ttu-id="c3b70-139">また、SCEP プロファイルを使用する場合は、ネットワーク デバイス登録サービス (NDES) サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-139">You also need to configure a Network Device Enrollment Service (NDES) server if you use SCEP profiles.</span></span>
- <span data-ttu-id="c3b70-140">SCEP プロファイルと PKCS プロファイルのどちらを使用する場合でも、Microsoft Intune 証明書コネクタをダウンロードして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-140">Whether you plan to use SCEP or PKCS profiles, you must download and configure the Microsoft Intune Certificate Connector.</span></span>


## <a name="step-1-configure-your-certificate-infrastructure"></a><span data-ttu-id="c3b70-141">手順 1- 証明書インフラストラクチャを構成する</span><span class="sxs-lookup"><span data-stu-id="c3b70-141">Step 1: Configure your certificate infrastructure</span></span>

<span data-ttu-id="c3b70-142">インフラストラクチャの構成については、証明書プロファイルの種類に応じて次のトピックのいずれかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3b70-142">See one of the following topics for help configuring the infrastructure for each type of certificate profile:</span></span>

- [<span data-ttu-id="c3b70-143">Intune で SCEP 証明書を構成して管理する</span><span class="sxs-lookup"><span data-stu-id="c3b70-143">Configure and manage SCEP certificates with Intune</span></span>](certificates-scep-configure.md)
- [<span data-ttu-id="c3b70-144">Intune で PKCS 証明書を構成して管理する</span><span class="sxs-lookup"><span data-stu-id="c3b70-144">Configure and manage PKCS certificates with Intune</span></span>](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a><span data-ttu-id="c3b70-145">手順 2 - 信頼されたルート CA 証明書をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="c3b70-145">Step 2: Export your trusted root CA certificate</span></span>

<span data-ttu-id="c3b70-146">発行元 CA または発行元 CA を信頼するデバイスから、信頼されたルート証明機関 (CA) 証明書を **.cer** ファイルとしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c3b70-146">Export the Trusted Root Certification Authorities (CA) certificate as a **.cer** file from the issuing CA, or from any device that trusts your issuing CA.</span></span> <span data-ttu-id="c3b70-147">秘密キーをエクスポートしないでください。</span><span class="sxs-lookup"><span data-stu-id="c3b70-147">Do not export the private key.</span></span>

<span data-ttu-id="c3b70-148">信頼された証明書プロファイルを構成するときにこの証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="c3b70-148">You import this certificate when you set up a trusted certificate profile.</span></span>

## <a name="step-3-create-trusted-certificate-profiles"></a><span data-ttu-id="c3b70-149">手順 3 - 信頼された証明書プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="c3b70-149">Step 3: Create trusted certificate profiles</span></span>
<span data-ttu-id="c3b70-150">SCEP または PKCS 証明書プロファイルを作成する前に、信頼された証明書プロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-150">You must create a trusted certificate profile before you can create a SCEP or PKCS certificate profile.</span></span> <span data-ttu-id="c3b70-151">デバイス プラットフォームごとに、信頼された証明書プロファイルと、SCEP または PKCS プロファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3b70-151">You need a trusted certificate profile and a SCEP or PKCS profile for each device platform.</span></span> <span data-ttu-id="c3b70-152">信頼された証明書を作成するフローは、各デバイス プラットフォームで同様です。</span><span class="sxs-lookup"><span data-stu-id="c3b70-152">The flow for creating trusted certificates is similar for each device platform.</span></span>

### <a name="to-create-a-trusted-certificate-profile"></a><span data-ttu-id="c3b70-153">信頼された証明書プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="c3b70-153">To create a trusted certificate profile</span></span>

1. <span data-ttu-id="c3b70-154">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c3b70-154">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="c3b70-155">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-155">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="c3b70-156">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-156">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="c3b70-157">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-157">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="c3b70-158">[プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-158">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="c3b70-159">**[プロファイルを作成します]** ブレードで、信頼された証明書プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-159">On the **Create Profile** blade, enter a **Name** and **Description** for the trusted certificate profile.</span></span>
5. <span data-ttu-id="c3b70-160">**[プラットフォーム]** ドロップダウン リストで、この信頼された証明書のデバイス プラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-160">From the **Platform** drop-down list, select the device platform for this trusted certificate.</span></span> <span data-ttu-id="c3b70-161">現時点では、証明書設定に対応している次のいずれかのプラットフォームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-161">Currently, you can choose one of the following platforms for certificate settings:</span></span>
    - <span data-ttu-id="c3b70-162">**Android**</span><span class="sxs-lookup"><span data-stu-id="c3b70-162">**Android**</span></span>
    - <span data-ttu-id="c3b70-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="c3b70-163">**iOS**</span></span>
    - <span data-ttu-id="c3b70-164">**macOS**</span><span class="sxs-lookup"><span data-stu-id="c3b70-164">**macOS**</span></span>
    - <span data-ttu-id="c3b70-165">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="c3b70-165">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="c3b70-166">**Windows 8.1 以降**</span><span class="sxs-lookup"><span data-stu-id="c3b70-166">**Windows 8.1 and later**</span></span>
    - <span data-ttu-id="c3b70-167">**Windows 10 以降**</span><span class="sxs-lookup"><span data-stu-id="c3b70-167">**Windows 10 and later**</span></span>
6. <span data-ttu-id="c3b70-168">**[プロファイルの種類]** ドロップダウン リストで、**[信頼済み証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-168">From the **Profile type** drop-down list, choose **Trusted certificate**.</span></span>
7. <span data-ttu-id="c3b70-169">タスク 1 で保存した証明書を参照し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3b70-169">Browse to the certificate you saved in task 1, then click **OK**.</span></span>
8. <span data-ttu-id="c3b70-170">Windows 8.1 および Windows 10 デバイスの場合のみ、信頼された証明書の**保存先ストア**を以下から選択します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-170">For Windows 8.1 and Windows 10 devices only, select the **Destination Store** for the trusted certificate from:</span></span>
    - <span data-ttu-id="c3b70-171">**コンピューター証明書ストア - ルート**</span><span class="sxs-lookup"><span data-stu-id="c3b70-171">**Computer certificate store - Root**</span></span>
    - <span data-ttu-id="c3b70-172">**コンピューター証明書ストア - 中間**</span><span class="sxs-lookup"><span data-stu-id="c3b70-172">**Computer certificate store - Intermediate**</span></span>
    - <span data-ttu-id="c3b70-173">**ユーザー証明書ストア - 中間**</span><span class="sxs-lookup"><span data-stu-id="c3b70-173">**User certificate store - Intermediate**</span></span>
8. <span data-ttu-id="c3b70-174">完了したら、**[OK]** をクリックし、**[プロファイルの作成]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3b70-174">When you're done, choose **OK**, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="c3b70-175">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-175">The profile is created and appears on the profiles list blade.</span></span>

<span data-ttu-id="c3b70-176">このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3b70-176">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>


> [!Note]
> <span data-ttu-id="c3b70-177">Android デバイスでは、サードパーティにより信頼できる証明書がインストールされたことを知らせる通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3b70-177">Android devices display a notice that a third party has installed a trusted certificate.</span></span>

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a><span data-ttu-id="c3b70-178">手順 4 – SCEP または PKCS 証明書プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="c3b70-178">Step 4: Create SCEP or PKCS certificate profiles</span></span>

<span data-ttu-id="c3b70-179">各種類の証明書プロファイルの構成と割り当てについては、次のトピックのいずれかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3b70-179">See one of the following topics for help configuring and assigning each type of certificate profile:</span></span>

- [<span data-ttu-id="c3b70-180">Intune で SCEP 証明書を構成して管理する</span><span class="sxs-lookup"><span data-stu-id="c3b70-180">Configure and manage SCEP certificates with Intune</span></span>](certificates-scep-configure.md)
- [<span data-ttu-id="c3b70-181">Intune で PKCS 証明書を構成して管理する</span><span class="sxs-lookup"><span data-stu-id="c3b70-181">Configure and manage PKCS certificates with Intune</span></span>](certficates-pfx-configure.md)

<span data-ttu-id="c3b70-182">信頼された証明書プロファイルを作成した後、使用する各プラットフォーム用の SCEP または PKCS 証明書プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3b70-182">After you create a trusted certificate profile, create SCEP or PKCS certificate profiles for each platform you want to use.</span></span> <span data-ttu-id="c3b70-183">SCEP 証明書プロファイルを作成するときは、その同じプラットフォームに対する信頼された証明書プロファイルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-183">When you create a SCEP certificate profile, you must specify a trusted certificate profile for that same platform.</span></span> <span data-ttu-id="c3b70-184">これにより 2 つの証明書プロファイルがリンクされますが、それでも各プロファイルを個別に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b70-184">This links the two certificate profiles, but you still must assign each profile separately.</span></span>


## <a name="next-steps"></a><span data-ttu-id="c3b70-185">次の手順</span><span class="sxs-lookup"><span data-stu-id="c3b70-185">Next steps</span></span>
<span data-ttu-id="c3b70-186">デバイス プロファイルを割り当てる方法に関する一般的な情報については、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3b70-186">See [How to assign device profiles](device-profile-assign.md) for general information about how to assign device profiles.</span></span>
