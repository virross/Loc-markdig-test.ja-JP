---
title: "Cisco ISE でネットワークへのアクセスを保護する"
description: "Cisco ISE で制御されている Wi-Fi および VPN にアクセスする前に、デバイスが登録されポリシーに準拠するように、Intune で Cisco ISE を使用します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 90f91988c947739f51ee2130bd5c47052a11ac42
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="using-cisco-ise-with-microsoft-intune"></a><span data-ttu-id="23bcc-103">Microsoft Intune で Cisco ISE を使用する</span><span class="sxs-lookup"><span data-stu-id="23bcc-103">Using Cisco ISE with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="23bcc-104">Intune を Cisco Identity Services Engine (ISE) と統合すると、Intune のデバイス登録と準拠の状態を使用して、ISE 環境内でネットワーク ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-104">Intune integration with Cisco Identity Services Engine (ISE) allows you to author network policies in your ISE environment by using the Intune device-enrollment and compliance state.</span></span> <span data-ttu-id="23bcc-105">これらのポリシーを使用すると、会社のネットワークへのアクセスが、Intune で管理され Intune ポリシーに準拠しているデバイスに制限されるように処理することができます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-105">You can use these policies to ensure that access to your company network is restricted to devices that are managed by Intune and compliant with Intune policies.</span></span>

## <a name="configuration-steps"></a><span data-ttu-id="23bcc-106">構成手順</span><span class="sxs-lookup"><span data-stu-id="23bcc-106">Configuration steps</span></span>

<span data-ttu-id="23bcc-107">この統合を有効にするために、Intune テナントでセットアップを行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="23bcc-107">To enable this integration, you don’t need to do any setup in your Intune tenant.</span></span> <span data-ttu-id="23bcc-108">Intune テナントにアクセスするアクセス許可を、Cisco ISE サーバーに与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="23bcc-108">You will need to provide permissions to your Cisco ISE server to access your Intune tenant.</span></span> <span data-ttu-id="23bcc-109">これを行った後、セットアップの残りの部分は Cisco ISE サーバーで行われます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-109">After that's done, the rest of the setup happens in your Cisco ISE server.</span></span> <span data-ttu-id="23bcc-110">この記事では、Intune テナントにアクセスする権限を持つ ISE サーバーを提供する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-110">This article gives you instructions on providing your ISE server with permissions to access your Intune tenant.</span></span>

### <a name="step-1-manage-the-certificates"></a><span data-ttu-id="23bcc-111">手順 1: 証明書を管理する</span><span class="sxs-lookup"><span data-stu-id="23bcc-111">Step 1: Manage the certificates</span></span>
<span data-ttu-id="23bcc-112">Azure Active Directory (Azure AD) のコンソールから証明書をエクスポートし、それを ISE コンソールの信頼された証明書ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-112">Export the certificate from the Azure Active Directory (Azure AD) console, then import it into the Trusted Certificates store of the ISE console:</span></span>

#### <a name="internet-explorer-11"></a><span data-ttu-id="23bcc-113">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="23bcc-113">Internet Explorer 11</span></span>


   <span data-ttu-id="23bcc-114">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-114">a.</span></span> <span data-ttu-id="23bcc-115">管理者として Internet Explorer を実行して、Azure AD コンソールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-115">Run Internet Explorer as an administrator, and sign in to the Azure AD console.</span></span>

   <span data-ttu-id="23bcc-116">b.</span><span class="sxs-lookup"><span data-stu-id="23bcc-116">b.</span></span> <span data-ttu-id="23bcc-117">アドレス バーでロック アイコンを選択して、**[証明書の表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-117">Choose the lock icon in the address bar and choose **View certificates**.</span></span>

   <span data-ttu-id="23bcc-118">c.</span><span class="sxs-lookup"><span data-stu-id="23bcc-118">c.</span></span> <span data-ttu-id="23bcc-119">証明書のプロパティの **[詳細]** タブで、**[ファイルにコピー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-119">On the **Details** tab of the certificate properties, choose **Copy to file**.</span></span>

   <span data-ttu-id="23bcc-120">d.</span><span class="sxs-lookup"><span data-stu-id="23bcc-120">d.</span></span> <span data-ttu-id="23bcc-121">**証明書のエクスポート ウィザードの** [ようこそ] ページで、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-121">In the **Certificate export wizard** welcome page, choose **Next**.</span></span>

   <span data-ttu-id="23bcc-122">e.</span><span class="sxs-lookup"><span data-stu-id="23bcc-122">e.</span></span> <span data-ttu-id="23bcc-123">**[エクスポート ファイル形式]** ページで、既定値の **[DER encoded binary X.509 (.CER)]** のままにして、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-123">On the **Export file format** page, leave the default, **DER encoded binary x.509 (.CER)**, and choose **Next**.</span></span>  

   <span data-ttu-id="23bcc-124">f.</span><span class="sxs-lookup"><span data-stu-id="23bcc-124">f.</span></span> <span data-ttu-id="23bcc-125">**[エクスポートするファイル]** ページで、**[参照]** をクリックして、ファイルを保存する場所を選択し、ファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-125">On the **File to export** page, choose **Browse** to pick a location in which to save the file, and provide a file name.</span></span> <span data-ttu-id="23bcc-126">エクスポートするファイルを選択するのと似ていますが、実際にエクスポートする証明書が保存されるファイルに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-126">Though it seems like you’re picking a file to export, you’re actually naming the file that the exported certificate will be saved to.</span></span> <span data-ttu-id="23bcc-127">**[次へ]** &gt; **[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-127">Choose **Next** &gt; **Finish**.</span></span>

   <span data-ttu-id="23bcc-128">g.</span><span class="sxs-lookup"><span data-stu-id="23bcc-128">g.</span></span> <span data-ttu-id="23bcc-129">ISE コンソール内から、Intune 証明書 (エクスポートしたファイル) を **[信頼できる証明書]** にインポートします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-129">From within the ISE console, import the Intune certificate (the file you exported) into the  **Trusted Certificates** store.</span></span>

#### <a name="safari"></a><span data-ttu-id="23bcc-130">Safari</span><span class="sxs-lookup"><span data-stu-id="23bcc-130">Safari</span></span>

 <span data-ttu-id="23bcc-131">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-131">a.</span></span> <span data-ttu-id="23bcc-132">Azure AD コンソールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-132">Sign in to the Azure AD console.</span></span>

<span data-ttu-id="23bcc-133">b.</span><span class="sxs-lookup"><span data-stu-id="23bcc-133">b.</span></span> <span data-ttu-id="23bcc-134">ロック アイコン &gt; **[詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-134">Choose the lock icon &gt;  **More information**.</span></span>

   <span data-ttu-id="23bcc-135">c.</span><span class="sxs-lookup"><span data-stu-id="23bcc-135">c.</span></span> <span data-ttu-id="23bcc-136">**[証明書の表示]** &gt; **[詳細]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-136">Choose **View certificate** &gt; **Details**.</span></span>

   <span data-ttu-id="23bcc-137">d.</span><span class="sxs-lookup"><span data-stu-id="23bcc-137">d.</span></span> <span data-ttu-id="23bcc-138">証明書を選択し、**[エクスポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-138">Choose the certificate, and then choose **Export**.</span></span> 

   <span data-ttu-id="23bcc-139">e.</span><span class="sxs-lookup"><span data-stu-id="23bcc-139">e.</span></span> <span data-ttu-id="23bcc-140">ISE コンソール内から、Intune 証明書 (エクスポートしたファイル) を **[信頼できる証明書]** にインポートします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-140">From within the ISE console, import the Intune certificate (the file you exported) into the  **Trusted Certificates** store.</span></span>

> [!IMPORTANT]
>
> <span data-ttu-id="23bcc-141">証明書の有効期限が切れた場合、新しい証明書をエクスポートしてインポートする必要があるため、証明書の有効期限を確認します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-141">Check the expiration date of the certificate, as you will have to export and import a new certificate when this one expires.</span></span>


### <a name="obtain-a-self-signed-cert-from-ise"></a><span data-ttu-id="23bcc-142">ISE からの自己署名証明書の取得</span><span class="sxs-lookup"><span data-stu-id="23bcc-142">Obtain a self-signed cert from ISE</span></span> 

1. <span data-ttu-id="23bcc-143">ISE コンソールで、**[Administration]** (管理)  > **[Certificates]** (証明書)  > **[System Certificates]** (システム証明書)  > **[Generate Self Signed Certificate]** (自己署名証明書の生成) の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-143">In the ISE console, go to **Administration** > **Certificates** > **System Certificates** > **Generate Self Signed Certificate**.</span></span>  
2. <span data-ttu-id="23bcc-144">自己署名証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-144">Export the self-signed certificate.</span></span>
3. <span data-ttu-id="23bcc-145">テキスト エディターで、次のようにエクスポートした証明書を編集します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-145">In a text editor, edit the exported certificate:</span></span>

   - <span data-ttu-id="23bcc-146">**-----BEGIN CERTIFICATE-----** を削除する</span><span class="sxs-lookup"><span data-stu-id="23bcc-146">Delete **-----BEGIN CERTIFICATE-----**</span></span>
   - <span data-ttu-id="23bcc-147">**-----END CERTIFICATE-----** を削除する</span><span class="sxs-lookup"><span data-stu-id="23bcc-147">Delete **-----END CERTIFICATE-----**</span></span>
 
<span data-ttu-id="23bcc-148">すべてのテキストが単一行であることを確認する</span><span class="sxs-lookup"><span data-stu-id="23bcc-148">Ensure all of the text is a single line</span></span>


### <a name="step-2-create-an-app-for-ise-in-your-azure-ad-tenant"></a><span data-ttu-id="23bcc-149">手順 2: Azure AD テナントで ISE のアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="23bcc-149">Step 2: Create an app for ISE in your Azure AD tenant</span></span>
1. <span data-ttu-id="23bcc-150">Azure AD コンソールで、**[アプリケーション]** > **[アプリケーションの追加]** > **[組織で開発中のアプリケーションを追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-150">In the Azure AD console, choose **Applications** > **Add an Application** > **Add an application my organization is developing**.</span></span>
2. <span data-ttu-id="23bcc-151">アプリの名前と URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-151">Provide a name and a URL for the app.</span></span> <span data-ttu-id="23bcc-152">URL は、会社の Web サイトである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="23bcc-152">The URL could be your company website.</span></span>
3. <span data-ttu-id="23bcc-153">アプリ マニフェスト (JSON ファイル) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-153">Download the app manifest (a JSON file).</span></span>
4. <span data-ttu-id="23bcc-154">マニフェストの JSON ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-154">Edit the manifest JSON file.</span></span> <span data-ttu-id="23bcc-155">**[keyCredentials]** と呼ばれる設定で、手順 1 で編集した証明書のテキストを設定値として指定します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-155">In the setting called **keyCredentials**, provide the edited certificate text from Step 1 as the setting value.</span></span>
5. <span data-ttu-id="23bcc-156">名前を変更しないで、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-156">Save the file without changing its name.</span></span>
6. <span data-ttu-id="23bcc-157">Microsoft Graph と Microsoft Intune API へのアクセス許可を持つアプリを指定します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-157">Provide your app with permissions to Microsoft Graph and the Microsoft Intune API.</span></span>

   <span data-ttu-id="23bcc-158">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-158">a.</span></span> <span data-ttu-id="23bcc-159">Microsoft Graph の場合は、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-159">For Microsoft Graph, choose the following:</span></span>
    - <span data-ttu-id="23bcc-160">**アプリケーションのアクセス許可**: ディレクトリ データの読み取り</span><span class="sxs-lookup"><span data-stu-id="23bcc-160">**Application permissions**: Read directory data</span></span>
    - <span data-ttu-id="23bcc-161">**委任されたアクセス許可**:</span><span class="sxs-lookup"><span data-stu-id="23bcc-161">**Delegated permissions**:</span></span>
        - <span data-ttu-id="23bcc-162">ユーザーのデータへの常時アクセス</span><span class="sxs-lookup"><span data-stu-id="23bcc-162">Access user’s data anytime</span></span>
        - <span data-ttu-id="23bcc-163">ユーザーのサインイン</span><span class="sxs-lookup"><span data-stu-id="23bcc-163">Sign users in</span></span>

   <span data-ttu-id="23bcc-164">b.</span><span class="sxs-lookup"><span data-stu-id="23bcc-164">b.</span></span> <span data-ttu-id="23bcc-165">Microsoft Intune API では、**[アプリケーションのアクセス許可]** で、**[Intune からデバイスの状態とコンプライアンスを所得する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-165">For the Microsoft Intune API, in **Application permissions**, choose **Get device state and compliance from Intune**.</span></span>

7. <span data-ttu-id="23bcc-166">**[エンドポイントの表示]** を選択して、ISE 設定の構成で使用する次の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-166">Choose **View Endpoints** and copy the following values for use in configuring ISE settings:</span></span>

|<span data-ttu-id="23bcc-167">Azure AD ポータルでの値</span><span class="sxs-lookup"><span data-stu-id="23bcc-167">Value in Azure AD portal</span></span>|<span data-ttu-id="23bcc-168">ISE ポータルの対応フィールド</span><span class="sxs-lookup"><span data-stu-id="23bcc-168">Corresponding field in ISE portal</span></span>|
|-------------------|---------------------------------|
|<span data-ttu-id="23bcc-169">Microsoft Azure AD Graph API エンドポイント</span><span class="sxs-lookup"><span data-stu-id="23bcc-169">Microsoft Azure AD Graph API endpoint</span></span>|<span data-ttu-id="23bcc-170">自動検出 URL</span><span class="sxs-lookup"><span data-stu-id="23bcc-170">Auto Discovery URL</span></span>|
|<span data-ttu-id="23bcc-171">OAuth 2.0 トークン エンドポイント</span><span class="sxs-lookup"><span data-stu-id="23bcc-171">Oauth 2.0 Token endpoint</span></span>|<span data-ttu-id="23bcc-172">トークン発行 URL</span><span class="sxs-lookup"><span data-stu-id="23bcc-172">Token Issuing URL</span></span>|
|<span data-ttu-id="23bcc-173">クライアント ID でコードを更新する</span><span class="sxs-lookup"><span data-stu-id="23bcc-173">Update your code with your Client ID</span></span>|<span data-ttu-id="23bcc-174">クライアント ID</span><span class="sxs-lookup"><span data-stu-id="23bcc-174">Client ID</span></span>|

### <a name="step-4-upload-the-self-signed-certificate-from-ise-into-the-ise-app-you-created-in-azure-ad"></a><span data-ttu-id="23bcc-175">手順 4: 自己署名証明書を ISE から、Azure AD で作成した ISE アプリにアップロードする</span><span class="sxs-lookup"><span data-stu-id="23bcc-175">Step 4: Upload the self-signed certificate from ISE into the ISE app you created in Azure AD</span></span>
1. <span data-ttu-id="23bcc-176">.cer X509 公開証明書ファイルから、base64 でエンコードされた証明書値と拇印を取得します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-176">Get the base64 encoded cert value and thumbprint from a .cer X509 public cert file.</span></span> <span data-ttu-id="23bcc-177">この例では PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-177">This example uses PowerShell:</span></span>
   
      
      <span data-ttu-id="23bcc-178">$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()</span><span class="sxs-lookup"><span data-stu-id="23bcc-178">$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()</span></span>
 
    <span data-ttu-id="23bcc-179">次の手順で使用する $base64Thumbprint、$base64Value、および $keyid の値を格納します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-179">Store the values for $base64Thumbprint, $base64Value and $keyid, to be used in the next step.</span></span>
2. <span data-ttu-id="23bcc-180">マニフェスト ファイルを介して証明書をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-180">Upload the certificate through the manifest file.</span></span> <span data-ttu-id="23bcc-181">Azure [管理ポータル](https://manage.windowsazure.com)にログインする</span><span class="sxs-lookup"><span data-stu-id="23bcc-181">Log in to the [Azure Management Portal](https://manage.windowsazure.com)</span></span>
3. <span data-ttu-id="23bcc-182">Azure AD スナップインで、X.509 証明書を使用して構成するアプリケーションを検索します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-182">In to the Azure AD snap-in find the application that you want to configure with an X.509 certificate.</span></span>
4. <span data-ttu-id="23bcc-183">アプリケーション マニフェスト ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-183">Download the application manifest file.</span></span> 
5. <span data-ttu-id="23bcc-184">空の “KeyCredentials”: [], プロパティを次の JSON に置換します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-184">Replace the empty “KeyCredentials”: [], property with the following JSON.</span></span>  <span data-ttu-id="23bcc-185">KeyCredentials 複合型の詳細については、「[Entity and complex type reference](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType)」 (エンティティおよび複合型参照) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23bcc-185">The KeyCredentials complex type is documented in[Entity and complex type reference](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType).</span></span>

 
    <span data-ttu-id="23bcc-186">“keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2.</span><span class="sxs-lookup"><span data-stu-id="23bcc-186">“keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2.</span></span> 
     <span data-ttu-id="23bcc-187">],</span><span class="sxs-lookup"><span data-stu-id="23bcc-187">],</span></span> 
 
<span data-ttu-id="23bcc-188">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-188">For example:</span></span>
 
    “keyCredentials“: [
    {
    “customKeyIdentifier“: “ieF43L8nkyw/PEHjWvj+PkWebXk=”,
    “keyId“: “2d6d849e-3e9e-46cd-b5ed-0f9e30d078cc”,
    “type”: “AsymmetricX509Cert”,
    “usage”: “Verify”,
    “value”: “MIICWjCCAgSgAwIBA***omitted for brevity***qoD4dmgJqZmXDfFyQ”
    }
    ],
 
6. <span data-ttu-id="23bcc-189">アプリケーション マニフェスト ファイルに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-189">Save the change to the application manifest file.</span></span>
7. <span data-ttu-id="23bcc-190">編集したアプリケーションのマニフェスト ファイルを、Azure 管理ポータルを介してアップロードします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-190">Upload the edited application manifest file through the Azure management mortal.</span></span>
8. <span data-ttu-id="23bcc-191">省略可能: アプリケーションに X.509 証明書が存在しているかどうか確認するために、もう一度、マニフェストをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="23bcc-191">Optional:  Download the manifest again, to check that your X.509 cert is present on the application.</span></span>

>[!NOTE]
>
> <span data-ttu-id="23bcc-192">KeyCredentials はコレクションであるため、ロール オーバー シナリオ用に複数の X.509 証明書をアップロードすることも、侵害シナリオで証明書を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-192">KeyCredentials is a collection, so you can upload multiple X.509 certificates for rollover scenarios, or delete certficates in compromise scenarios.</span></span>


### <a name="step-4-configure-ise-settings"></a><span data-ttu-id="23bcc-193">手順 4: ISE 設定を構成する</span><span class="sxs-lookup"><span data-stu-id="23bcc-193">Step 4: Configure ISE Settings</span></span>
<span data-ttu-id="23bcc-194">ISE 管理コンソールで、次の設定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-194">In the ISE admin console, provide these setting values:</span></span>
  - <span data-ttu-id="23bcc-195">**サーバーの種類**: Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="23bcc-195">**Server Type**: Mobile Device Manager</span></span>
  - <span data-ttu-id="23bcc-196">**認証の種類**: OAuth – クライアントの資格情報</span><span class="sxs-lookup"><span data-stu-id="23bcc-196">**Authentication type**: OAuth – Client Credentials</span></span>
  - <span data-ttu-id="23bcc-197">**自動検出**: はい</span><span class="sxs-lookup"><span data-stu-id="23bcc-197">**Auto Discovery**: Yes</span></span>
  - <span data-ttu-id="23bcc-198">**自動検出 URL**: *手順 1 の値を入力します。*</span><span class="sxs-lookup"><span data-stu-id="23bcc-198">**Auto Discover URL**: *Enter the value from Step 1.*</span></span>
  - <span data-ttu-id="23bcc-199">**クライアント ID**: *手順 1 の値を入力します。*</span><span class="sxs-lookup"><span data-stu-id="23bcc-199">**Client ID**: *Enter the value from Step 1.*</span></span>
  - <span data-ttu-id="23bcc-200">**トークンの発行 URL**: *手順 1. の値を入力します。*</span><span class="sxs-lookup"><span data-stu-id="23bcc-200">**Token issuing URL**: *Enter the value from Step 1.*</span></span>



## <a name="information-shared-between-your-intune-tenant-and-your-cisco-ise-server"></a><span data-ttu-id="23bcc-201">Intune テナントと Cisco ISE サーバー間で共有される情報</span><span class="sxs-lookup"><span data-stu-id="23bcc-201">Information shared between your Intune tenant and your Cisco ISE server</span></span>
<span data-ttu-id="23bcc-202">次の表には、Intune テナントと Intune によって管理されるデバイス用の Cisco ISE サーバー間で共有される情報を一覧します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-202">This table lists the information that is shared between your Intune tenant and your Cisco ISE server for devices that are managed by Intune.</span></span>

|<span data-ttu-id="23bcc-203">プロパティ</span><span class="sxs-lookup"><span data-stu-id="23bcc-203">Property</span></span>|  <span data-ttu-id="23bcc-204">説明</span><span class="sxs-lookup"><span data-stu-id="23bcc-204">Description</span></span>|
|---------------|------------------------------------------------------------|
|<span data-ttu-id="23bcc-205">complianceState</span><span class="sxs-lookup"><span data-stu-id="23bcc-205">complianceState</span></span>|<span data-ttu-id="23bcc-206">デバイスが準拠か非準拠かを示す true または false の文字列。</span><span class="sxs-lookup"><span data-stu-id="23bcc-206">The true or false string that indicates whether the device is compliant or noncompliant.</span></span>|
|<span data-ttu-id="23bcc-207">isManaged</span><span class="sxs-lookup"><span data-stu-id="23bcc-207">isManaged</span></span>|<span data-ttu-id="23bcc-208">クライアントが Intune で管理されるかどうかを示す true または false の文字列。</span><span class="sxs-lookup"><span data-stu-id="23bcc-208">The true or false string that indicates whether the client is managed by Intune or not.</span></span>|
|<span data-ttu-id="23bcc-209">macAddress</span><span class="sxs-lookup"><span data-stu-id="23bcc-209">macAddress</span></span>|<span data-ttu-id="23bcc-210">デバイスの MAC アドレス。</span><span class="sxs-lookup"><span data-stu-id="23bcc-210">The MAC address of the device.</span></span>|
|<span data-ttu-id="23bcc-211">serialNumber</span><span class="sxs-lookup"><span data-stu-id="23bcc-211">serialNumber</span></span>|<span data-ttu-id="23bcc-212">デバイスのシリアル番号。</span><span class="sxs-lookup"><span data-stu-id="23bcc-212">The serial number of the device.</span></span> <span data-ttu-id="23bcc-213">iOS デバイスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-213">It applies only to iOS devices.</span></span>|
|<span data-ttu-id="23bcc-214">imei</span><span class="sxs-lookup"><span data-stu-id="23bcc-214">imei</span></span>|<span data-ttu-id="23bcc-215">IMEI (15 桁の 10 進数: 14 桁とチェック ディジット) または IMEISV (16 桁) 番号には、デバイスの製造元、モデル、およびシリアル番号の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="23bcc-215">The IMEI (15 decimal digits: 14 digits plus a check digit) or IMEISV (16 digits) number includes information on the origin, model, and serial number of the device.</span></span> <span data-ttu-id="23bcc-216">この番号の構造は、3GPP TS 23.003 で指定されます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-216">The structure of this number is specified in 3GPP TS 23.003.</span></span> <span data-ttu-id="23bcc-217">SIM カードのあるデバイスのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-217">It applies only to devices with SIM cards.</span></span>|
|<span data-ttu-id="23bcc-218">udid</span><span class="sxs-lookup"><span data-stu-id="23bcc-218">udid</span></span>|<span data-ttu-id="23bcc-219">一意のデバイス ID。40 個の文字と数字から成ります。</span><span class="sxs-lookup"><span data-stu-id="23bcc-219">The Unique Device Identifier, which is a sequence of 40 letters and numbers.</span></span> <span data-ttu-id="23bcc-220">これは、iOS デバイスに固有です。</span><span class="sxs-lookup"><span data-stu-id="23bcc-220">It is specific to iOS devices.</span></span>|
|<span data-ttu-id="23bcc-221">meid</span><span class="sxs-lookup"><span data-stu-id="23bcc-221">meid</span></span>|<span data-ttu-id="23bcc-222">モバイル デバイス ID。CDMA モバイル ステーション装置の物理パーツを識別するグローバル一意識別番号です。</span><span class="sxs-lookup"><span data-stu-id="23bcc-222">The mobile equipment identifier, which is a globally unique number that identifies a physical piece of CDMA mobile station equipment.</span></span> <span data-ttu-id="23bcc-223">値の形式は、3GPP2 レポート S. R0048 によって定義されています。</span><span class="sxs-lookup"><span data-stu-id="23bcc-223">The number format is defined by the 3GPP2 report S. R0048.</span></span> <span data-ttu-id="23bcc-224">ただし、IMEI のように見えますが、実際には 16 進数です。</span><span class="sxs-lookup"><span data-stu-id="23bcc-224">However, in practical terms, it can be seen as an IMEI, but with hexadecimal digits.</span></span> <span data-ttu-id="23bcc-225">MEID は 56 ビット長 (14 桁の 16 進数) です。</span><span class="sxs-lookup"><span data-stu-id="23bcc-225">An MEID is 56 bits long (14 hex digits).</span></span> <span data-ttu-id="23bcc-226">8 ビットの地域コード (RR)、24 ビットの製造元コード、24 ビットの製造元によって割り当てられたシリアル番号を含む、3 つのフィールドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-226">It consists of three fields, including an 8-bit regional code (RR), a 24-bit manufacturer code, and a 24-bit manufacturer-assigned serial number.</span></span>|
|<span data-ttu-id="23bcc-227">osVersion</span><span class="sxs-lookup"><span data-stu-id="23bcc-227">osVersion</span></span>|<span data-ttu-id="23bcc-228">デバイスのオペレーティング システムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="23bcc-228">The operating system version for the device.</span></span>
|<span data-ttu-id="23bcc-229">対象となるのは、モデル</span><span class="sxs-lookup"><span data-stu-id="23bcc-229">model</span></span>|<span data-ttu-id="23bcc-230">デバイスのモデル。</span><span class="sxs-lookup"><span data-stu-id="23bcc-230">The device model.</span></span>
|<span data-ttu-id="23bcc-231">manufacturer</span><span class="sxs-lookup"><span data-stu-id="23bcc-231">manufacturer</span></span>|<span data-ttu-id="23bcc-232">デバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="23bcc-232">The device manufacturer.</span></span>
|<span data-ttu-id="23bcc-233">azureDeviceId</span><span class="sxs-lookup"><span data-stu-id="23bcc-233">azureDeviceId</span></span>|<span data-ttu-id="23bcc-234">Azure AD に社内参加した後のデバイス ID。</span><span class="sxs-lookup"><span data-stu-id="23bcc-234">The device ID after it has workplace joined with Azure AD.</span></span> <span data-ttu-id="23bcc-235">参加していないデバイスの場合は空の GUID です。</span><span class="sxs-lookup"><span data-stu-id="23bcc-235">It is an empty GUID for devices that are not joined.</span></span>|
|<span data-ttu-id="23bcc-236">lastContactTimeUtc</span><span class="sxs-lookup"><span data-stu-id="23bcc-236">lastContactTimeUtc</span></span>|<span data-ttu-id="23bcc-237">デバイスが Intune の管理サービスで最後に確認された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="23bcc-237">The date and time when the device last checked in with the Intune management service.</span></span>


## <a name="user-experience"></a><span data-ttu-id="23bcc-238">ユーザー側の表示と操作</span><span class="sxs-lookup"><span data-stu-id="23bcc-238">User experience</span></span>

<span data-ttu-id="23bcc-239">ユーザーが登録したデバイスを使用してリソースにアクセスしようとすると、次のように、登録するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-239">When a user attempts to access resources by using an unenrolled device, they receive a prompt to enroll, such as the one shown here:</span></span>

![登録プロンプトの例](../media/cisco-ise-user-iphone.png)

<span data-ttu-id="23bcc-241">ユーザーが登録を選択すると、Intune の登録プロセスにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="23bcc-241">When a user chooses to enroll, they are redirected to the Intune enrollment process.</span></span> <span data-ttu-id="23bcc-242">次のトピックでは、Intune のユーザー登録エクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="23bcc-242">The user enrollment experience for Intune is described in these topics:</span></span>

- [<span data-ttu-id="23bcc-243">Intune に Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="23bcc-243">Enroll your Android device in Intune</span></span>](/intune-user-help/enroll-your-device-in-Intune-android)</br>
- [<span data-ttu-id="23bcc-244">Intune に iOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="23bcc-244">Enroll your iOS device in Intune</span></span>](/intune-user-help/enroll-your-device-in-intune-ios)</br>
- [<span data-ttu-id="23bcc-245">Intune に Mac OS X デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="23bcc-245">Enroll your Mac OS X device in Intune</span></span>](/intune-user-help/enroll-your-device-in-intune-mac-os-x)</br>
- [<span data-ttu-id="23bcc-246">Intune に Windows デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="23bcc-246">Enroll your Windows device in Intune</span></span>](/intune-user-help/enroll-your-device-in-intune-windows)</br>

<span data-ttu-id="23bcc-247">また、ユーザー エクスペリエンスのためにカスタマイズされたガイダンスを作成できる、[ダウンロード可能な一連の登録手順](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a)もあります。</span><span class="sxs-lookup"><span data-stu-id="23bcc-247">There is also a [downloadable set of enrollment instructions](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) that you can use to create customized guidance for your user experience.</span></span>


### <a name="see-also"></a><span data-ttu-id="23bcc-248">関連項目</span><span class="sxs-lookup"><span data-stu-id="23bcc-248">See also</span></span>

[<span data-ttu-id="23bcc-249">Cisco Identity Services Engine 管理者ガイド、リリース 2.1</span><span class="sxs-lookup"><span data-stu-id="23bcc-249">Cisco Identity Services Engine Administrator Guide, Release 2.1</span></span>](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)
