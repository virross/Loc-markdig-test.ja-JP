---
title: "Microsoft Intune で iOS デバイスにアプリごとの VPN を設定する"
titleSuffix: Intune on Azure
description: "管理対象のどのアプリが Intune で管理される iOS デバイスで VPN を使用できるかを指定します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/5/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c883ab2b96618502be20583908a4caa52ac5432b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-per-app-vpn-in-microsoft-intune-for-ios-devices"></a><span data-ttu-id="0d4de-103">Microsoft Intune で iOS デバイスにアプリごとの VPN を設定する</span><span class="sxs-lookup"><span data-stu-id="0d4de-103">Set up Per-App VPN in Microsoft Intune for iOS devices</span></span>

<span data-ttu-id="0d4de-104">管理対象のどのアプリが Intune で管理される iOS デバイスで仮想プライベート ネットワーク (VPN) を使用できるかを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-104">You can specify which managed apps can use your Virtual Private Network (VPN) on Intune managed iOS devices.</span></span> <span data-ttu-id="0d4de-105">Intune でアプリごとの VPN を指定すると、エンド ユーザーが会社のドキュメントにアクセスするときに自動的に VPN を通して接続します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-105">When you specify a Per-APP VPN in Intune, an end user automatically connects through your VPN when accessing corporate documents.</span></span>

## <a name="prerequisites-for-the-per-app-vpn"></a><span data-ttu-id="0d4de-106">アプリごとの VPN の前提条件</span><span class="sxs-lookup"><span data-stu-id="0d4de-106">Prerequisites for the Per-App VPN</span></span>

<span data-ttu-id="0d4de-107">身元を証明するため、VPN サーバーはデバイスによってプロンプトなしに受け入れられる必要がある証明書を提示します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-107">To prove its identity, the VPN server presents the certificate that must be accepted without a prompt by the device.</span></span> <span data-ttu-id="0d4de-108">証明書の自動承認を確実に行うため、証明機関 (CA) によって発行された VPN サーバーのルート証明書を含む、信頼済み証明書プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-108">To ensure the automatic approval of the certificate, create a trusted certificate profile that contains the VPN server's root certificate issued by the Certificate Authority (CA).</span></span> 

<span data-ttu-id="0d4de-109">証明書をエクスポートし、CA を追加します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-109">Export the certificate and add the CA.</span></span>

1. <span data-ttu-id="0d4de-110">VPN サーバーの管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-110">Open the administration console on your VPN server.</span></span>
2. <span data-ttu-id="0d4de-111">VPN サーバーが証明書ベースの認証を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-111">Verify that your VPN server uses Certificate-based Authentication.</span></span> 
3. <span data-ttu-id="0d4de-112">信頼されたルート証明書ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-112">Export the trusted root certificate file.</span></span> <span data-ttu-id="0d4de-113">拡張子は .cer で、信頼済み証明書プロファイルの作成時にこのファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-113">It has a .cer extension, and you add it when creating a trusted certificate profile.</span></span>
4. <span data-ttu-id="0d4de-114">VPN サーバーへの認証用に証明書を発行した CA の名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-114">Add the name of the CA that issued the certificate for authentication to the VPN server.</span></span>
    <span data-ttu-id="0d4de-115">デバイスによって提示される CA が VPN サーバーの信頼された証明機関リストのいずれかの CA と一致する場合、VPN サーバーによるデバイスの認証が成功します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-115">If the CA presented by the device matches one of the CAs in the Trusted CA list on the VPN server, then the VPN server successfully authenticates the device.</span></span>

## <a name="create-a--group-for-your-vpn-users"></a><span data-ttu-id="0d4de-116">VPN ユーザーのグループを作成する</span><span class="sxs-lookup"><span data-stu-id="0d4de-116">Create a  group for your VPN users</span></span>

<span data-ttu-id="0d4de-117">アプリごとの VPN にアクセスできるメンバーが含まれるように、Azure Active Directory (Azure AD) でグループを作成するか既存のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-117">Create or choose an existing group in Azure Active Directory (Azure AD) to contain the members who have access to the per-App VPN.</span></span>

1. <span data-ttu-id="0d4de-118">Azure ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-118">Open the Azure portal.</span></span> <span data-ttu-id="0d4de-119">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-119">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="0d4de-120">**[グループ]** を選択し、**[新しいグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-120">Choose **Groups** and click **New group**.</span></span>
3. <span data-ttu-id="0d4de-121">グループの **[名前]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-121">Type the **Name** of the group.</span></span> 
4. <span data-ttu-id="0d4de-122">グループの **[説明]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-122">Type the **Description** of the group.</span></span> 
5. <span data-ttu-id="0d4de-123">**[メンバーシップの種類]** に **[割り当て済み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-123">Select **Assigned** for the **Membership type**.</span></span>
6. <span data-ttu-id="0d4de-124">**[Office の機能を有効にしますか]** に **[いいえ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-124">Select **No** for **Enable Office features**.</span></span>
7. <span data-ttu-id="0d4de-125">**[メンバー]** ブレードで、名前またはメール アドレスで VPN ユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-125">Search for the VPN users by name or email address in the **Members** blade.</span></span>
8. <span data-ttu-id="0d4de-126">各ユーザーを選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-126">Select each user and click **Select**.</span></span>
9. <span data-ttu-id="0d4de-127">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-127">Click **Create**</span></span>

## <a name="create-a-trusted-certificate-profile"></a><span data-ttu-id="0d4de-128">信頼済み証明書プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="0d4de-128">Create a trusted certificate profile</span></span>

<span data-ttu-id="0d4de-129">CA によって発行された VPN サーバーのルート証明書を、Intune で作成されたプロファイルにインポートします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-129">Import the VPN server's root certificate issued by the CA into a profile created in Intune.</span></span> <span data-ttu-id="0d4de-130">信頼済み証明書プロファイルから iOS デバイスに、VPN サーバーが提示する CA を自動的に信頼するように指示します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-130">The trusted certificate profile instructs the iOS device to automatically trust the CA that the VPN server presents.</span></span>

1. <span data-ttu-id="0d4de-131">Azure ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-131">Open the Azure portal.</span></span> <span data-ttu-id="0d4de-132">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-132">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="0d4de-133">**[デバイス構成]** を選択して、**[プロファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-133">Choose **Device configuration**, and then click **Profiles**.</span></span>
3. <span data-ttu-id="0d4de-134">**[+ プロファイルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-134">Click **+ Create profile**.</span></span> <span data-ttu-id="0d4de-135">**[プロファイルの作成]** で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-135">In **Create profile**:</span></span>
    1. <span data-ttu-id="0d4de-136">**[名前]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-136">Type the **Name**.</span></span>
    2. <span data-ttu-id="0d4de-137">**[説明]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-137">Type the **Description**.</span></span>
    3. <span data-ttu-id="0d4de-138">**[プラットフォーム]** に **[iOS]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-138">Select **iOS** for the **Platform**.</span></span>
    4. <span data-ttu-id="0d4de-139">**[プロファイルの種類]** に **[信頼できる証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-139">Select **Trusted certificate** for the **Profile type**.</span></span>
4. <span data-ttu-id="0d4de-140">フォルダー アイコンをクリックし、VPN 管理コンソールからエクスポートした VPN 証明書 (.cer ファイル) を参照します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-140">Click the folder icon and browse to your VPN certificate (.cer file) that you exported from your VPN administration console.</span></span> <span data-ttu-id="0d4de-141">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-141">Click OK</span></span>
5. <span data-ttu-id="0d4de-142">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-142">Click **Create**.</span></span>

    ![信頼済み証明書プロファイルを作成する](media\vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a><span data-ttu-id="0d4de-144">SCEP 証明書プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="0d4de-144">Create a SCEP certificate profile</span></span>

<span data-ttu-id="0d4de-145">信頼済みルート証明書プロファイルにより、iOS が VPN サーバーを自動的に信頼できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0d4de-145">The trusted root certificate profile allows the iOS to automatically trust the VPN Server.</span></span> <span data-ttu-id="0d4de-146">SCEP 証明書は、iOS の VPN クライアントから VPN サーバーに資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-146">The SCEP certificate provides credentials from the iOS VPN client to the VPN server.</span></span> <span data-ttu-id="0d4de-147">この証明書により、iOS デバイスのユーザーにユーザー名とパスワードを求めることなく自動的にデバイスが認証できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0d4de-147">The certificate allows the device to silently authenticate without prompting the iOS devise user for a username and password.</span></span> 

1. <span data-ttu-id="0d4de-148">Azure ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-148">Open the Azure portal.</span></span> <span data-ttu-id="0d4de-149">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-149">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span> 
2. <span data-ttu-id="0d4de-150">**[デバイス構成]** を選択して、**[プロファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-150">Choose **Device configuration**, and then click **Profiles**.</span></span>
3. <span data-ttu-id="0d4de-151">**[+ プロファイルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-151">Click **+ Create profile**.</span></span> <span data-ttu-id="0d4de-152">**[プロファイルの作成]** で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-152">In **Create profile**:</span></span>
    1. <span data-ttu-id="0d4de-153">**[名前]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-153">Type the **Name**.</span></span>
    2. <span data-ttu-id="0d4de-154">**[説明]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-154">Type the **Description**.</span></span>
    3. <span data-ttu-id="0d4de-155">**[プラットフォーム]** に **[iOS]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-155">Select **iOS** for the **Platform**.</span></span>
    4. <span data-ttu-id="0d4de-156">**[プロファイルの種類]** に **[SCEP 証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-156">Select **SCEP certificate** for the **Profile type**.</span></span>
4. <span data-ttu-id="0d4de-157">**[証明書の有効期間]** に **[年]** を選択して、`2` を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-157">Select **Years** and type `2` for **Certificate validity period**.</span></span>
5. <span data-ttu-id="0d4de-158">**[サブジェクト名の形式]** に **[共通名]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-158">Select **Common name** for **Subject name format**.</span></span>
6. <span data-ttu-id="0d4de-159">**[サブジェクトの別名]** に **[ユーザー プリンシパル名 (UPN)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-159">Select **User principle name (UPN)** for **Subject alternative name**.</span></span>
7. <span data-ttu-id="0d4de-160">**[キー使用法]** に **[デジタル署名]** および **[キーの暗号化]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-160">Select **Digital signature** and **Key encipherment** for **Key usage**.</span></span>
8. <span data-ttu-id="0d4de-161">**[キー サイズ (ビット)]** に **[2048]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-161">Select **2048** for **Key size (bits)**.</span></span>
9. <span data-ttu-id="0d4de-162">ルート証明書をクリックし、SCEP 証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-162">Click Root Certificate and select a SCEP certificate.</span></span> <span data-ttu-id="0d4de-163">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-163">Click **OK**.</span></span>
10. <span data-ttu-id="0d4de-164">**[拡張キー使用法]** の **[名前]** に `Client Authentication` を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-164">Type `Client Authentication` in **Name** for **Extended key usage**.</span></span>
11. <span data-ttu-id="0d4de-165">**[オブジェクト識別子]** に `1.3.6.1.5.5.7.3.2`を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-165">Type `1.3.6.1.5.5.7.3.2` in **Object Identifier**.</span></span>
12. <span data-ttu-id="0d4de-166">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-166">Click **Add**.</span></span>
13. <span data-ttu-id="0d4de-167">***サーバーの URL*** を入力して、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-167">Type the ***Server URL*** and click **Add**.</span></span>
14. <span data-ttu-id="0d4de-168">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-168">Click **OK**.</span></span>
15. <span data-ttu-id="0d4de-169">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-169">Click **Create**.</span></span>

    ![SCEP 証明書プロファイルを作成する](media\vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a><span data-ttu-id="0d4de-171">アプリごとの VPN プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="0d4de-171">Create a Per-App VPN profile</span></span>

<span data-ttu-id="0d4de-172">VPN プロファイルには、クライアントの資格情報を含む SCEP 証明書、VPN への接続情報、iOS アプリケーションがアプリごとの VPN 機能を使用できるようにする、アプリごとの VPN フラグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d4de-172">The VPN profile contains the SCEP certificate carrying the client credentials, the connection information to the VPN, and the Per APP VPN flag to enable the Per App VPN feature for use by the iOS application.</span></span>

1. <span data-ttu-id="0d4de-173">Azure ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-173">Open the Azure portal.</span></span> <span data-ttu-id="0d4de-174">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-174">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="0d4de-175">**[デバイス構成]** を選択して、**[プロファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-175">Choose **Device configuration**, and then click **Profiles**.</span></span>
3. <span data-ttu-id="0d4de-176">**[+ プロファイルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-176">Click **+ Create profile**.</span></span> <span data-ttu-id="0d4de-177">**[プロファイルの作成]** で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-177">In **Create profile**:</span></span>
    1. <span data-ttu-id="0d4de-178">**[名前]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-178">Type the **Name**.</span></span>
    2. <span data-ttu-id="0d4de-179">**[説明]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-179">Type the **Description**.</span></span>
    3. <span data-ttu-id="0d4de-180">**[プラットフォーム]** に **[iOS]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-180">Select **iOS** for the **Platform**.</span></span>
    4. <span data-ttu-id="0d4de-181">**[プロファイルの種類]** に **[VPN]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-181">Select **VPN** for the **Profile type**.</span></span>
4. <span data-ttu-id="0d4de-182">**[基本 VPN]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-182">Select **Base VPN**.</span></span> <span data-ttu-id="0d4de-183">**[基本 VPN]** で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-183">In **Base VPN**:</span></span>
    1. <span data-ttu-id="0d4de-184">**[接続名]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-184">Type the **Connection name**.</span></span>
    2. <span data-ttu-id="0d4de-185">**[IP アドレスまたは FQDN]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-185">Type the **IP address or FQDN**.</span></span>
    3. <span data-ttu-id="0d4de-186">**[認証方法]** に **[証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-186">Select **Certificates** for the **Authentication method**.</span></span>
    4. <span data-ttu-id="0d4de-187">**[認証証明書]** で SCEP 証明書を選択して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-187">Select the SCEP certificate under **Authentication certificate** and click **OK**.</span></span>
    5. <span data-ttu-id="0d4de-188">**[接続の種類]** に VPN を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-188">Select your VPN for the **Connection type**.</span></span>
    6. <span data-ttu-id="0d4de-189">必要に応じて、VPN の属性を構成します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-189">If necessary, configure the attributes for your VPN.</span></span>
    7. <span data-ttu-id="0d4de-190">**[分割トンネリング]** に [無効化] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-190">Select for **Disable Split** tunneling.</span></span>
5. <span data-ttu-id="0d4de-191">**[自動 VPN]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-191">Click **Automatic VPN**.</span></span> <span data-ttu-id="0d4de-192">**[自動 VPN]** で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-192">In **Automatic VPN**:</span></span>
    1. <span data-ttu-id="0d4de-193">**[自動 VPN の種類]** に **[アプリごとの VPN]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-193">Select **Per-App VPN** for the **Type of automatic VPN**.</span></span>
    2. <span data-ttu-id="0d4de-194">VPN の URL を入力して、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-194">Type the URL for the VPN and click **Add**.</span></span>
    3. <span data-ttu-id="0d4de-195">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-195">Click **OK**.</span></span>
6. <span data-ttu-id="0d4de-196">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-196">Click **OK**.</span></span>
7. <span data-ttu-id="0d4de-197">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-197">Click **Create**.</span></span>

    ![アプリごとの VPN プロファイルを作成する](media\vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a><span data-ttu-id="0d4de-199">アプリと VPN プロファイルを関連付ける</span><span class="sxs-lookup"><span data-stu-id="0d4de-199">Associate an app with the VPN profile</span></span>

<span data-ttu-id="0d4de-200">VPN プロファイルを追加した後、アプリと Azure AD グループをプロファイルに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-200">After adding your VPN profile, associate the app and Azure AD group to the profile.</span></span>

1. <span data-ttu-id="0d4de-201">Azure ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-201">Open the Azure portal.</span></span> <span data-ttu-id="0d4de-202">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-202">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="0d4de-203">**[Mobile Apps]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-203">Choose **Mobile Apps**.</span></span>
3. <span data-ttu-id="0d4de-204">**[アプリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-204">Click **Apps**.</span></span>
4. <span data-ttu-id="0d4de-205">アプリの一覧からアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-205">Select the app from the list of apps.</span></span>
5. <span data-ttu-id="0d4de-206">**[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-206">Click **Assignments.**</span></span>
6. <span data-ttu-id="0d4de-207">**[グループの選択]** をクリックして、前に定義したグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-207">Click **Select groups**, select the group you defined earlier.</span></span> <span data-ttu-id="0d4de-208">**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-208">Click **Select**.</span></span>
7. <span data-ttu-id="0d4de-209">**[割り当て]** ブレードの **[種類]** に **[必須]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-209">Select **Required** for the **Type** in the **Assignments** blade.</span></span>
8. <span data-ttu-id="0d4de-210">**[VPNS]** に VPN 定義を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-210">Select your VPN definition for the **VPNS**.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="0d4de-211">VPN 定義が値を取得するまで、1 分程度かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d4de-211">Sometimes the VPN definition takes up to a minute to retrieve the value.</span></span> <span data-ttu-id="0d4de-212">3 - 5 分間待ってから、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-212">Wait for 3-5 minutes before your click **Save**.</span></span>

9. <span data-ttu-id="0d4de-213">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-213">Click **Save**.</span></span>

    ![アプリと VPN を関連付ける](media\vpn-per-app-app-to-vpn.png)

## <a name="verify-the-connection-on-the-ios-device"></a><span data-ttu-id="0d4de-215">iOS デバイスでの接続を確認する</span><span class="sxs-lookup"><span data-stu-id="0d4de-215">Verify the connection on the iOS device</span></span>

<span data-ttu-id="0d4de-216">アプリと関連付けられたアプリごとの VPN 設定で、デバイスからの接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-216">With your Per-App VPN set-up and associated with your app, verify the connection works from a device.</span></span>

### <a name="before-you-attempt-to-connect"></a><span data-ttu-id="0d4de-217">接続を試行する前に</span><span class="sxs-lookup"><span data-stu-id="0d4de-217">Before you attempt to connect</span></span>

 - <span data-ttu-id="0d4de-218">iOS 7 以降を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-218">Make sure you’re running iOS 7 or later.</span></span>
 - <span data-ttu-id="0d4de-219">同じユーザーのグループに、前述の*すべての*ポリシーを展開しておきます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-219">Make sure you deploy *all* of the above mentioned policies to the same group of users.</span></span> <span data-ttu-id="0d4de-220">展開されていないと、アプリごとの VPN がほぼ確実に中断します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-220">Failure to do so will most definitely break the Per-App VPN experience.</span></span>  
 - <span data-ttu-id="0d4de-221">サポートされているサード パーティ製 VPN アプリがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-221">Makes sure you have the supported third-party VPN app installed.</span></span> <span data-ttu-id="0d4de-222">次の VPN アプリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0d4de-222">The following VPN apps are supported:</span></span>
    - <span data-ttu-id="0d4de-223">Pulse Secure</span><span class="sxs-lookup"><span data-stu-id="0d4de-223">Pulse Secure</span></span>
    - <span data-ttu-id="0d4de-224">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="0d4de-224">Checkpoint</span></span>
    - <span data-ttu-id="0d4de-225">F5</span><span class="sxs-lookup"><span data-stu-id="0d4de-225">F5</span></span>
    - <span data-ttu-id="0d4de-226">SonicWall</span><span class="sxs-lookup"><span data-stu-id="0d4de-226">SonicWall</span></span>

### <a name="connect-using-the-per-app-vpn"></a><span data-ttu-id="0d4de-227">アプリごとの VPN を使用して接続する</span><span class="sxs-lookup"><span data-stu-id="0d4de-227">Connect using the Per-App VPN</span></span>

<span data-ttu-id="0d4de-228">VPN を選択したり、資格情報を入力したりせずに接続されるゼロタッチ操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-228">Verify the zero-touch experience by connecting without having to select the VPN or type your credentials.</span></span> <span data-ttu-id="0d4de-229">ゼロタッチ操作とは、次のような意味です。</span><span class="sxs-lookup"><span data-stu-id="0d4de-229">The zero-touch experience means:</span></span>

 - <span data-ttu-id="0d4de-230">デバイスから VPN サーバーを信頼するように求められません。</span><span class="sxs-lookup"><span data-stu-id="0d4de-230">The device does not ask you to trust the VPN server.</span></span> <span data-ttu-id="0d4de-231">つまり、**[Dynamic Trust]\(動的な信頼\)** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d4de-231">That is, you do see the **Dynamic Trust** dialog box.</span></span>
 - <span data-ttu-id="0d4de-232">資格情報を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0d4de-232">You do not have to type credentials.</span></span>
 - <span data-ttu-id="0d4de-233">[接続] ボタンをタップすると、VPN に接続します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-233">You are connected to the VPN after tapping the connect button.</span></span>

<span data-ttu-id="0d4de-234">iOS デバイスで接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-234">Verify the connection on an iOS device.</span></span>

1. <span data-ttu-id="0d4de-235">VPN アプリをタップします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-235">Tap the VPN app.</span></span>
2. <span data-ttu-id="0d4de-236">**[接続]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="0d4de-236">Tap on **Connect**.</span></span>  
<span data-ttu-id="0d4de-237">VPN は、余分なプロンプトを表示せずに正常に接続します。</span><span class="sxs-lookup"><span data-stu-id="0d4de-237">The VPN successfully connects without any extra prompts.</span></span>

<!-- ## Troubleshooting the Per-App VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a><span data-ttu-id="0d4de-238">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0d4de-238">Next steps</span></span>

- <span data-ttu-id="0d4de-239">iOS 設定を確認するには、「[Microsoft Intune での iOS デバイス向けの VPN 設定](vpn-settings-ios.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d4de-239">To review iOS settings, see [VPN settings for iOS devices in Microsoft Intune](vpn-settings-ios.md).</span></span>
-  <span data-ttu-id="0d4de-240">VPN の設定と Intune の詳細については、「[Microsoft Intune で VPN の設定を構成する方法](vpn-settings-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d4de-240">To learn more about VPN setting and Intune, see [How to configure VPN settings in Microsoft Intune](vpn-settings-configure.md).</span></span>