---
title: "証明書プロファイルを構成する"
description: "Intune 証明書プロファイルを作成する方法について説明します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cc04768fd7835597ba87c746884f4976403cbdd5
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="configure-intune-certificate-profiles"></a><span data-ttu-id="af734-103">Intune 証明書プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="af734-103">Configure Intune certificate profiles</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="af734-104">「[SCEP の証明書インフラストラクチャを構成する](configure-certificate-infrastructure-for-scep.md)」または「[PFX の証明書インフラストラクチャを構成する](configure-certificate-infrastructure-for-pfx.md)」の説明に従ってインフラストラクチャおよび証明書を構成した後、証明書プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="af734-104">After you've configured your infrastructure and certificates as described in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) or [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md), you can create certificate profiles.</span></span> <span data-ttu-id="af734-105">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="af734-105">Here's the process:</span></span>

- <span data-ttu-id="af734-106">**タスク 1** - 信頼されたルート CA 証明書をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="af734-106">**Task 1**: Export the Trusted Root CA certificate</span></span>
- <span data-ttu-id="af734-107">**タスク 2** - 信頼された証明書プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="af734-107">**Task 2**: Create Trusted certificate profiles</span></span>
- <span data-ttu-id="af734-108">**タスク 3** - 2 種類の証明書プロファイルのいずれかを作成する:</span><span class="sxs-lookup"><span data-stu-id="af734-108">**Task 3**: Create one of two certificate profile types:</span></span>
  - <span data-ttu-id="af734-109">SCEP 証明書プロファイル</span><span class="sxs-lookup"><span data-stu-id="af734-109">SCEP certificate profiles</span></span>
  - <span data-ttu-id="af734-110">.PFX 証明書プロファイル</span><span class="sxs-lookup"><span data-stu-id="af734-110">.PFX certificate profiles</span></span>

## <a name="task-1-export-the-trusted-root-ca-certificate"></a><span data-ttu-id="af734-111">**タスク 1** - 信頼されたルート CA 証明書をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="af734-111">**Task 1**: Export the Trusted Root CA certificate</span></span>
<span data-ttu-id="af734-112">発行元 CA または発行元 CA を信頼するデバイスから、信頼されたルート証明機関 (CA) 証明書を **.cer** ファイルとしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="af734-112">Export the Trusted Root Certification Authorities (CA) certificate as a **.cer** file from the issuing CA, or from any device that trusts your issuing CA.</span></span> <span data-ttu-id="af734-113">秘密キーをエクスポートしないでください。</span><span class="sxs-lookup"><span data-stu-id="af734-113">Do not export the private key.</span></span>

<span data-ttu-id="af734-114">信頼された証明書プロファイルを構成するときにこの証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="af734-114">You'll import this certificate when you set up a Trusted certificate profile.</span></span>

## <a name="task-2-create-trusted-certificate-profiles"></a><span data-ttu-id="af734-115">**タスク 2** - 信頼された証明書プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="af734-115">**Task 2**: Create Trusted certificate profiles</span></span>
<span data-ttu-id="af734-116">Simple Certificate Enrollment Protocol (SCEP) または PKCS #12 (.PFX) 証明書プロファイルを作成する前に、信頼された証明書プロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af734-116">You must create a Trusted certificate profile before you can create a Simple Certificate Enrollment Protocol (SCEP) or a PKCS #12 (.PFX) certificate profile.</span></span> <span data-ttu-id="af734-117">モバイル デバイス プラットフォームごとに、信頼された証明書プロファイルと、SCEP または .PFX プロファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="af734-117">You need a Trusted certificate profile and an SCEP or .PFX profile for each mobile device platform.</span></span>

### <a name="to-create-a-trusted-certificate-profile"></a><span data-ttu-id="af734-118">信頼された証明書プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="af734-118">To create a Trusted certificate profile</span></span>

1.  <span data-ttu-id="af734-119">[Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[ポリシーの追加]** を選択し、デバイスのプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="af734-119">In the [Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy**, and choose a device platform.</span></span> <span data-ttu-id="af734-120">次のデバイスについて信頼済み証明書プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="af734-120">You can create a trusted certificate profile for these devices:</span></span>

-  <span data-ttu-id="af734-121">Android 4 以降</span><span class="sxs-lookup"><span data-stu-id="af734-121">Android 4 and later</span></span>

-  <span data-ttu-id="af734-122">Android for Work</span><span class="sxs-lookup"><span data-stu-id="af734-122">Android for Work</span></span>

-  <span data-ttu-id="af734-123">iOS 7.1 以降</span><span class="sxs-lookup"><span data-stu-id="af734-123">iOS 7.1 and later</span></span>

-  <span data-ttu-id="af734-124">Mac OS X 10.9 以降</span><span class="sxs-lookup"><span data-stu-id="af734-124">Mac OS X 10.9 and later</span></span>

-  <span data-ttu-id="af734-125">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="af734-125">Windows 8.1 and later</span></span>

-  <span data-ttu-id="af734-126">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="af734-126">Windows Phone 8.1 and later</span></span>

2.  <span data-ttu-id="af734-127">**信頼済み証明書プロファイル** ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="af734-127">Add a **Trusted Certificate Profile** policy.</span></span>

    <span data-ttu-id="af734-128">詳しくは、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="af734-128">Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

3.  <span data-ttu-id="af734-129">要求された情報を入力して、Android、iOS、Mac OS X、Windows 8.1、または Windows Phone 8.1 用の信頼された証明書プロファイルの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="af734-129">Enter the requested information to configure the Trusted certificate profile settings for Android, iOS, Mac OS X, Windows 8.1, or Windows Phone 8.1.</span></span>
4.  <span data-ttu-id="af734-130">**[証明書ファイル]** 設定で、発行元 CA からエクスポートした信頼されたルート CA 証明書 (.cer ファイル) をインポートします。</span><span class="sxs-lookup"><span data-stu-id="af734-130">In the **Certificate file** setting, import the Trusted Root CA certificate (.cer file) that you exported from your issuing CA.</span></span> <span data-ttu-id="af734-131">**[保存先ストア]** 設定は、Windows 8.1 以降を実行中のデバイスで、1 つ以上の証明書ストアを持っているデバイスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="af734-131">The **Destination store** setting applies only to devices running Windows 8.1 and later, and only if the device has more than one certificate store.</span></span>

4.  <span data-ttu-id="af734-132">**[ポリシーの保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af734-132">Choose **Save Policy**.</span></span>

<span data-ttu-id="af734-133">新しいポリシーが **[ポリシー]** ワークスペースに表示されます。</span><span class="sxs-lookup"><span data-stu-id="af734-133">The new policy is shown in the **Policy** workspace.</span></span> <span data-ttu-id="af734-134">これでデプロイが可能になりました。</span><span class="sxs-lookup"><span data-stu-id="af734-134">Now you can deploy it.</span></span>

> [!NOTE]
>
> <span data-ttu-id="af734-135">Android デバイスと Android for Work デバイスでは、サードパーティにより信頼できる証明書がインストールされたことを知らせる通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af734-135">Android and Android for Work devices will display a notice that a third party has installed a trusted certificate.</span></span>


## <a name="task-3-create-scep-or-pfx-certificate-profiles"></a><span data-ttu-id="af734-136">**タスク 3** – SCEP または .PFX 証明書プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="af734-136">**Task 3**: Create SCEP or .PFX certificate profiles</span></span>
<span data-ttu-id="af734-137">信頼された CA 証明書プロファイルを作成した後、使用する各プラットフォーム用の SCEP または .PFX 証明書プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="af734-137">After you create a Trusted CA certificate profile, create SCEP or .PFX certificate profiles for each platform you want to use.</span></span> <span data-ttu-id="af734-138">SCEP 証明書プロファイルを作成するときは、その同じプラットフォームに対する信頼された証明書プロファイルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af734-138">When you create an SCEP certificate profile, you must specify a Trusted certificate profile for that same platform.</span></span> <span data-ttu-id="af734-139">これにより 2 つの証明書プロファイルがリンクされますが、それでも各プロファイルを個別にデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af734-139">This links the two certificate profiles, but you still must deploy each profile separately.</span></span>

### <a name="to-create-an-scep-certificate-profile"></a><span data-ttu-id="af734-140">SCEP 証明書プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="af734-140">To create an SCEP certificate profile</span></span>

1.  <span data-ttu-id="af734-141">[Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[ポリシーの追加]** を選択し、デバイスのプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="af734-141">In the [Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy** and choose a device platform.</span></span>  <span data-ttu-id="af734-142">次のデバイスについて SCEP 証明書プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="af734-142">You can create a SCEP certificate profile for these devices:</span></span>

-  <span data-ttu-id="af734-143">Android 4 以降</span><span class="sxs-lookup"><span data-stu-id="af734-143">Android 4 and later</span></span>

-  <span data-ttu-id="af734-144">Android for Work</span><span class="sxs-lookup"><span data-stu-id="af734-144">Android for Work</span></span>

-  <span data-ttu-id="af734-145">iOS 7.1 以降</span><span class="sxs-lookup"><span data-stu-id="af734-145">iOS 7.1 and later</span></span>

-  <span data-ttu-id="af734-146">Mac OS X 10.9 以降</span><span class="sxs-lookup"><span data-stu-id="af734-146">Mac OS X 10.9 and later</span></span>

-  <span data-ttu-id="af734-147">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="af734-147">Windows 8.1 and later</span></span>

-  <span data-ttu-id="af734-148">Windows Phone 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="af734-148">Windows Phone 8.1 and later</span></span>

2. <span data-ttu-id="af734-149">**SCEP 証明書プロファイル** ポリシーを追加します</span><span class="sxs-lookup"><span data-stu-id="af734-149">Add a **SCEP Certificate Profile** policy</span></span>

   <span data-ttu-id="af734-150">詳しくは、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="af734-150">Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

3. <span data-ttu-id="af734-151">プロファイル構成ページの指示に従って、SCEP 証明書プロファイル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="af734-151">Follow the instructions on the profile configuration page to configure the SCEP certificate profile settings.</span></span>
   > [!NOTE]
   > 
   > <span data-ttu-id="af734-152">**[サブジェクト名の形式]** で、**[カスタム]** を選択してサブジェクト名のカスタム形式を入力します (iOS のプロファイルのみ)。</span><span class="sxs-lookup"><span data-stu-id="af734-152">Under **Subject name format**, select **Custom** to enter a custom subject name format (in iOS profiles, only).</span></span>
   > 
   > <span data-ttu-id="af734-153">カスタム形式で現在サポートされている 2 つの変数は、`Common Name (CN)` と `Email (E)` です。</span><span class="sxs-lookup"><span data-stu-id="af734-153">The two variables currently supported for the custom format are `Common Name (CN)` and `Email (E)`.</span></span> <span data-ttu-id="af734-154">これらの変数と静的文字列の組み合わせを使用することで、このようなサブジェクト名のカスタム形式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="af734-154">By using a combination of these variables and static strings, you can create a custom subject name format, like this one:</span></span>
   > 
   >     <span data-ttu-id="af734-155">CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US</span><span class="sxs-lookup"><span data-stu-id="af734-155">CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US</span></span>
   > 
   > <span data-ttu-id="af734-156">この例では、管理者は `CN` と `E` の変数に加えて、組織単位、組織、市区町村、州、および国の値の文字列を使用してサブジェクト名形式を作成しています。</span><span class="sxs-lookup"><span data-stu-id="af734-156">In this example, the admin created a subject name format that, in addition to the `CN` and `E` variables, uses strings for Organizational Unit, Organization, Location, State, and Country values.</span></span> <span data-ttu-id="af734-157">「[CertStrToName 関数](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx)」で、サポートされる文字列を一覧にしています。</span><span class="sxs-lookup"><span data-stu-id="af734-157">[CertStrToName function](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) lists supported strings.</span></span>

4. <span data-ttu-id="af734-158">**[ポリシーの保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af734-158">Choose **Save Policy**.</span></span>

<span data-ttu-id="af734-159">新しいポリシーが **[ポリシー]** ワークスペースに表示されます。</span><span class="sxs-lookup"><span data-stu-id="af734-159">The new policy is shown in the **Policy** workspace.</span></span> <span data-ttu-id="af734-160">これでデプロイが可能になりました。</span><span class="sxs-lookup"><span data-stu-id="af734-160">Now you can deploy it.</span></span>

### <a name="to-create-a-pfx-certificate-profile"></a><span data-ttu-id="af734-161">.PFX 証明書プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="af734-161">To create a .PFX certificate profile</span></span>

1. <span data-ttu-id="af734-162">[Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[ポリシーの追加]** を選択し、デバイスのプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="af734-162">In the [Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy**, and choose a device platform.</span></span> <span data-ttu-id="af734-163">次のデバイスについては、.PFX 証明書がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af734-163">.PFX certificates are supported for:</span></span>
   - <span data-ttu-id="af734-164">Android 4 以降</span><span class="sxs-lookup"><span data-stu-id="af734-164">Android 4 and later</span></span>
   - <span data-ttu-id="af734-165">Android for Work</span><span class="sxs-lookup"><span data-stu-id="af734-165">Android for Work</span></span>
   - <span data-ttu-id="af734-166">Windows 10 以降</span><span class="sxs-lookup"><span data-stu-id="af734-166">Windows 10 and later</span></span>
   - <span data-ttu-id="af734-167">Windows Phone 10 以降</span><span class="sxs-lookup"><span data-stu-id="af734-167">Windows Phone 10 and later</span></span>
   - <span data-ttu-id="af734-168">iOS 8.0 以降)</span><span class="sxs-lookup"><span data-stu-id="af734-168">iOS 8.0 and later)</span></span>    


2. <span data-ttu-id="af734-169">**.PFX 証明書プロファイル** ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="af734-169">Add a **.PFX Certificate Profile** policy.</span></span>
     <span data-ttu-id="af734-170">詳しくは、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="af734-170">Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>
3. <span data-ttu-id="af734-171">ポリシー フォームで要求されている情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="af734-171">Enter the information requested on the policy form.</span></span>
4. <span data-ttu-id="af734-172">**[ポリシーの保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af734-172">Choose **Save Policy**.</span></span>

<span data-ttu-id="af734-173">新しいポリシーが **[ポリシー]** ワークスペースに表示されます。</span><span class="sxs-lookup"><span data-stu-id="af734-173">The new policy is shown in the **Policy** workspace.</span></span> <span data-ttu-id="af734-174">これでデプロイが可能になりました。</span><span class="sxs-lookup"><span data-stu-id="af734-174">Now you can deploy it.</span></span>

## <a name="deploy-certificate-profiles"></a><span data-ttu-id="af734-175">証明書プロファイルを展開する</span><span class="sxs-lookup"><span data-stu-id="af734-175">Deploy certificate profiles</span></span>
<span data-ttu-id="af734-176">証明書プロファイルをデプロイするときに、信頼された CA 証明書プロファイルの証明書ファイルは、デバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="af734-176">When you deploy certificate profiles, the certificate file from the Trusted CA certificate profile is installed on the device.</span></span> <span data-ttu-id="af734-177">デバイスは、SCEP または .PFX 証明書プロファイルを使用してデバイスによる証明書要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="af734-177">The device uses the SCEP or .PFX certificate profile to create a certificate request by the device.</span></span>

<span data-ttu-id="af734-178">証明書プロファイルは、プロファイルを作成するときに使用するプラットフォームを実行しているデバイスのみにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="af734-178">Certificate profiles install only on devices running the platform you use when you create the profile.</span></span>

-   <span data-ttu-id="af734-179">ユーザー コレクションまたはデバイス コレクションに証明書プロファイルをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="af734-179">You can deploy certificate profiles to user collections or to device collections.</span></span>

    > [!TIP]
    > <span data-ttu-id="af734-180">デバイス登録後すぐに証明書をデバイスに公開するには、証明書プロファイルをデバイス グループではなくユーザー グループにデプロイします。</span><span class="sxs-lookup"><span data-stu-id="af734-180">To publish a certificate to a device quickly after the device enrolls, deploy the certificate profile to a user group rather than to a device group.</span></span> <span data-ttu-id="af734-181">デバイス グループにデプロイした場合は、デバイスがポリシーを受け取る前に、デバイスの登録を完全に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="af734-181">If you deploy to a device group, a full device registration is required before the device receives policies.</span></span>

-   <span data-ttu-id="af734-182">各プロファイルは個別にデプロイしますが、信頼されたルート CA と、SCEP または .PFX プロファイルをデプロイする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="af734-182">Although you deploy each profile separately, you also need to deploy the Trusted Root CA and the SCEP or .PFX profile.</span></span> <span data-ttu-id="af734-183">そうしないと、SCEP または .PFX 証明書ポリシーは失敗します。</span><span class="sxs-lookup"><span data-stu-id="af734-183">Otherwise, the SCEP or .PFX certificate policy will fail.</span></span>

<span data-ttu-id="af734-184">Intune の他のポリシーをデプロイするのと同じ方法で、証明書プロファイルをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="af734-184">Deploy certificate profiles the same way you deploy other policies for Intune:</span></span>

1.  <span data-ttu-id="af734-185">**[ポリシー]** ワークスペースで、展開するポリシーを選び、**[展開の管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="af734-185">In the **Policy** workspace, select the policy you want to deploy, and then choose **Manage Deployment**.</span></span>
2.  <span data-ttu-id="af734-186">**[展開の管理]** ダイアログ ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="af734-186">In the **Manage Deployment** dialog box:</span></span>
    -   <span data-ttu-id="af734-187">**ポリシーをデプロイするには**、ポリシーをデプロイする 1 つ以上のグループを選択して、**[追加]**&gt;**[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="af734-187">**To deploy the policy**, select one or more groups to deploy the policy to, and then choose **Add** &gt; **OK**.</span></span>
    -   <span data-ttu-id="af734-188">**ポリシーをデプロイせずにダイアログ ボックスを閉じるには**、**[キャンセル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af734-188">**To close the dialog box without deploying it**, choose **Cancel**.</span></span>

<span data-ttu-id="af734-189">デプロイ済みポリシーを選択すると、ポリシー一覧の下部にデプロイについての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af734-189">When you select a deployed policy, you can see more information about the deployment in the lower part of the list of policies.</span></span>

### <a name="next-steps"></a><span data-ttu-id="af734-190">次の手順</span><span class="sxs-lookup"><span data-stu-id="af734-190">Next steps</span></span>

<span data-ttu-id="af734-191">次に、証明書を使用して、電子メール、Wi-Fi、VPN プロファイルをセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="af734-191">Next, learn how to use certificates to help secure email, Wi-Fi, and VPN profiles.</span></span>

-  [<span data-ttu-id="af734-192">電子メール プロファイルを使用して会社の電子メールへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="af734-192">Configure access to corporate email using email profiles</span></span>](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [<span data-ttu-id="af734-193">Microsoft Intune での Wi-Fi 接続</span><span class="sxs-lookup"><span data-stu-id="af734-193">Wi-Fi connections in Microsoft Intune</span></span>](wi-fi-connections-in-microsoft-intune.md)
-  [<span data-ttu-id="af734-194">Microsoft Intune での VPN 接続</span><span class="sxs-lookup"><span data-stu-id="af734-194">VPN connections in Microsoft Intune</span></span>](vpn-connections-in-microsoft-intune.md)
