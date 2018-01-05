---
title: "PFX の証明書インフラストラクチャを構成する"
description: ".PFX 証明書プロファイルを作成および展開します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7ff3a035f82be7d13b80ac5b7a2db039cc004e4f
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="configure-certificate-infrastructure"></a><span data-ttu-id="9ced9-103">証明書インフラストラクチャを構成する</span><span class="sxs-lookup"><span data-stu-id="9ced9-103">Configure certificate infrastructure</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="9ced9-104">このトピックでは、.PFX 証明書プロファイルを作成して展開するために必要なものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-104">This topic describes what you need in order to create and deploy .PFX certificate profiles.</span></span>

<span data-ttu-id="9ced9-105">組織で証明書ベースの認証を行うには、エンタープライズ証明機関が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ced9-105">To do any certificate-based authentication in your organization, you need an Enterprise Certification Authority.</span></span>

<span data-ttu-id="9ced9-106">.PFX 証明書プロファイルを使用するには、エンタープライズ証明機関に加えて次のものも必要です。</span><span class="sxs-lookup"><span data-stu-id="9ced9-106">To use .PFX Certificate profiles, in addition to the Enterprise Certification Authority, you  also need:</span></span>

-   <span data-ttu-id="9ced9-107">証明機関と通信できるコンピューターまたは証明機関コンピューター自体を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-107">A computer that can communicate with the Certification Authority, or you can use the Certification Authority computer itself.</span></span>

-  <span data-ttu-id="9ced9-108">証明機関と通信できるコンピューターで実行する Intune 証明書コネクタ。</span><span class="sxs-lookup"><span data-stu-id="9ced9-108">The Intune Certificate Connector, which runs on the computer that can communicate with the Certification Authority.</span></span>

## <a name="on-premises-infrastructure-description"></a><span data-ttu-id="9ced9-109">オンプレミス インフラストラクチャの説明</span><span class="sxs-lookup"><span data-stu-id="9ced9-109">On-premises infrastructure description</span></span>


- <span data-ttu-id="9ced9-110">**Active Directory ドメイン**: このセクションで示されているすべてのサーバー (Web アプリケーション プロキシ サーバーを除く) は、Active Directory ドメインに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ced9-110">**Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.</span></span>

- <span data-ttu-id="9ced9-111">**証明機関**: Windows Server 2008 R2 以降の Enterprise エディションで実行するエンタープライズ証明機関 (CA) が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ced9-111">**Certification Authority**: An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="9ced9-112">スタンドアロン CA はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9ced9-112">A Standalone CA is not supported.</span></span> <span data-ttu-id="9ced9-113">証明機関をセットアップする方法の詳細については、 [証明機関のインストールに関するページ](http://technet.microsoft.com/library/jj125375.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ced9-113">For instructions on how to set up a Certification Authority, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).</span></span>
   <span data-ttu-id="9ced9-114">CA が Windows Server 2008 R2 を搭載している場合は、 [KB2483564 の修正プログラムをインストール](http://support.microsoft.com/kb/2483564/)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ced9-114">If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).</span></span>

- <span data-ttu-id="9ced9-115">**証明機関と通信できるコンピューター**: 証明機関コンピューター自体を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-115">**Computer that can communicate with Certification Authority**: Alternatively, use the Certification Authority computer itself.</span></span>
- <span data-ttu-id="9ced9-116">**Microsoft Intune 証明書コネクタ**: Intune 管理コンソールを使用して**証明書コネクタ** インストーラー (**ndesconnectorssetup.exe**) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9ced9-116">**Microsoft Intune Certificate Connector**: You use the Intune admin console to download the **Certificate Connector** installer (**ndesconnectorssetup.exe**).</span></span> <span data-ttu-id="9ced9-117">これにより、証明書コネクタをインストールするコンピューターで **ndesconnectorssetup.exe** を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-117">Then you can run **ndesconnectorssetup.exe** on the computer where you want to install the Certificate Connector.</span></span> <span data-ttu-id="9ced9-118">.PFX 証明書プロファイルの場合は、証明機関と通信するコンピューターに証明書コネクタをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9ced9-118">For .PFX Certificate profiles, install the Certificate Connector on the computer that communicates with the Certification Authority.</span></span>
- <span data-ttu-id="9ced9-119">**Web アプリケーション プロキシ サーバー** (省略可能): Web アプリケーション プロキシ (WAP) サーバーとして Windows Server 2012 R2 以降を実行しているサーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-119">**Web Application Proxy server** (optional): You can use a server that runs Windows Server 2012 R2 or later as a Web Application Proxy (WAP) server.</span></span> <span data-ttu-id="9ced9-120">この構成は:</span><span class="sxs-lookup"><span data-stu-id="9ced9-120">This configuration:</span></span>
   -  <span data-ttu-id="9ced9-121">デバイスはインターネット接続を使用して証明書を受信できます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-121">Allows devices to receive certificates using an Internet connection.</span></span>
   -  <span data-ttu-id="9ced9-122">デバイスがインターネット接続経由で証明書を受信して更新する場合のセキュリティ推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="9ced9-122">Is a security recommendation when devices connect through the Internet to receive and renew certificates.</span></span>

  > [!NOTE]           
  > -    <span data-ttu-id="9ced9-123">WAP をホストするサーバーは、ネットワーク デバイス登録サービス (NDES) で使用される長い URL のサポートを有効にする[更新プログラムをインストールする](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ced9-123">The server that hosts WAP [must install an update](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service (NDES).</span></span> <span data-ttu-id="9ced9-124">この更新プログラムは、 [2014 年 12 月の更新プログラムのロールアップ](http://support.microsoft.com/kb/3013769)に含まれます。または、 [KB3011135](http://support.microsoft.com/kb/3011135)から個別に入手できます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-124">This update is included with the [December 2014 update rollup](http://support.microsoft.com/kb/3013769), or individually from [KB3011135](http://support.microsoft.com/kb/3011135).</span></span>
  >-  <span data-ttu-id="9ced9-125">また、WAP をホストするサーバーが、外部クライアントに公開される名前と一致する SSL 証明書を持ち、NDES サーバーで使用される SSL 証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ced9-125">Also, the server that hosts WAP must have an SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server.</span></span> <span data-ttu-id="9ced9-126">これらの証明書を使用すると、WAP サーバーはクライアントからの SSL 接続を終了し、NDES サーバーへの新しい SSL 接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-126">These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.</span></span>
   <span data-ttu-id="9ced9-127">WAP の証明書については、「[内部アプリケーションの公開のために Web アプリケーション プロキシをインストールおよび構成する](https://technet.microsoft.com/library/dn383650.aspx)」の**証明書の計画**に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ced9-127">For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx).</span></span> <span data-ttu-id="9ced9-128">WAP サーバーの一般的な情報については、「[Web アプリケーション プロキシの使用](http://technet.microsoft.com/library/dn584113.aspx)」を参照してください。|</span><span class="sxs-lookup"><span data-stu-id="9ced9-128">For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|</span></span>


### <a name="certificates-and-templates"></a><span data-ttu-id="9ced9-129">証明書とテンプレート</span><span class="sxs-lookup"><span data-stu-id="9ced9-129">Certificates and Templates</span></span>

|<span data-ttu-id="9ced9-130">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9ced9-130">Object</span></span>|<span data-ttu-id="9ced9-131">説明</span><span class="sxs-lookup"><span data-stu-id="9ced9-131">Details</span></span>|
|----------|-----------|
|<span data-ttu-id="9ced9-132">**証明書テンプレート**</span><span class="sxs-lookup"><span data-stu-id="9ced9-132">**Certificate Template**</span></span>|<span data-ttu-id="9ced9-133">発行元 CA でこのテンプレートを構成します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-133">You configure this template on your issuing CA.</span></span>|
|<span data-ttu-id="9ced9-134">**信頼されたルート CA 証明書**</span><span class="sxs-lookup"><span data-stu-id="9ced9-134">**Trusted Root CA certificate**</span></span>|<span data-ttu-id="9ced9-135">これを発行元 CA または発行元 CA を信頼するデバイスから **.cer** ファイルとしてエクスポートし、信頼された CA 証明書プロファイルを使用してデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-135">You export this as a **.cer** file from the issuing CA or any device which trusts the issuing CA, and deploy it to devices by using the Trusted CA certificate profile.</span></span><br /><br /><span data-ttu-id="9ced9-136">オペレーティング システムのプラットフォームごとに 1 つの信頼されたルート CA 証明書を使用し、作成する各信頼されたルート証明書プロファイルに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-136">You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.</span></span><br /><br /><span data-ttu-id="9ced9-137">必要に応じて、信頼されたルート CA 証明書を追加して使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-137">You can use additional Trusted Root CA certificates when needed.</span></span> <span data-ttu-id="9ced9-138">ルート CA 証明書を追加する局面としては、Wi-Fi アクセス ポイント用のサーバー認証証明書に署名する CA の信頼性を担保する必要がある場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-138">For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.</span></span>|


## <a name="configure-your-infrastructure"></a><span data-ttu-id="9ced9-139">インフラストラクチャを構成する</span><span class="sxs-lookup"><span data-stu-id="9ced9-139">Configure your infrastructure</span></span>
<span data-ttu-id="9ced9-140">証明書プロファイルを構成するには、次のタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ced9-140">Before you can configure certificate profiles, you must complete the following tasks.</span></span> <span data-ttu-id="9ced9-141">以下のタスクには、Windows Server 2012 R2 と Active Directory 証明書サービス (ADCS) についての知識が必要となります。</span><span class="sxs-lookup"><span data-stu-id="9ced9-141">These tasks require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):</span></span>

- <span data-ttu-id="9ced9-142">**タスク 1** - 証明機関で証明書テンプレートを構成する。</span><span class="sxs-lookup"><span data-stu-id="9ced9-142">**Task 1** - Configure certificate templates on the certification authority.</span></span>
- <span data-ttu-id="9ced9-143">**タスク 2** - Intune 証明書コネクタを有効にし、インストールし、構成する。</span><span class="sxs-lookup"><span data-stu-id="9ced9-143">**Task 2** - Enable, install, and configure the Intune Certificate Connector.</span></span>

### <a name="task-1---configure-certificate-templates-on-the-certification-authority"></a><span data-ttu-id="9ced9-144">タスク 1 - 証明機関で証明書テンプレートを構成する</span><span class="sxs-lookup"><span data-stu-id="9ced9-144">Task 1 - Configure certificate templates on the certification authority</span></span>
<span data-ttu-id="9ced9-145">このタスクでは、証明書テンプレートを公開します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-145">In this task, you will publish the certificate template.</span></span>

##### <a name="to-configure-the-certification-authority"></a><span data-ttu-id="9ced9-146">証明機関を構成するには</span><span class="sxs-lookup"><span data-stu-id="9ced9-146">To configure the certification authority</span></span>

1.  <span data-ttu-id="9ced9-147">発行元 CA で、証明書テンプレート スナップインを使用して、新しいカスタム テンプレートを作成するか、または .PFX で使用するために (ユーザー テンプレートのように) 既存のテンプレートをコピーして、編集します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-147">On the issuing CA, use the Certificate Templates snap-in to create a new custom template, or copy and edit an existing template (like the User template), for use with .PFX.</span></span>

    <span data-ttu-id="9ced9-148">テンプレートには以下を含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ced9-148">The template must include the following:</span></span>

    -   <span data-ttu-id="9ced9-149">テンプレートのわかりやすい **テンプレート表示名** を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-149">Specify a friendly **Template display name** for the template.</span></span>

    -   <span data-ttu-id="9ced9-150">**[サブジェクト名]** タブで **[要求に含まれる]** を選択します</span><span class="sxs-lookup"><span data-stu-id="9ced9-150">On the **Subject Name** tab, select **Supply in the request**.</span></span> 

    -   <span data-ttu-id="9ced9-151">**[拡張]** タブで、**[アプリケーション ポリシーの説明]** に **[クライアント認証]** が含まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-151">On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="9ced9-152">iOS および Mac OS X の証明書テンプレートの場合、**[拡張]** タブで、**[キー使用法]** を編集し、**[署名は発行元の証明である]** がオンになっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-152">For iOS and Mac OS X certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure that **Signature is proof of origin** is not selected.</span></span>

2.  <span data-ttu-id="9ced9-153">**[一般]** タブでテンプレートの **[有効期間]** を確認します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-153">Review the **Validity period** on the **General** tab of the template.</span></span> <span data-ttu-id="9ced9-154">既定では、Intune はテンプレートで構成されている値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-154">By default, Intune uses the value configured in the template.</span></span> <span data-ttu-id="9ced9-155">ただし、要求元が異なる値を指定できるように CA を構成できます。異なる値は、Intune 管理者コンソールから設定できます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-155">However, you have the option to configure the CA to allow the requester to specify a different value, which you can then set from within the Intune Administrator console.</span></span> <span data-ttu-id="9ced9-156">常にテンプレートの値を使用する場合は、この手順の残りの部分をスキップします。</span><span class="sxs-lookup"><span data-stu-id="9ced9-156">If you want to always use the value in the template, skip the remainder of this step.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9ced9-157">iOS および Mac OS X プラットフォームは、他の構成に関係なく、常にテンプレートで設定される値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-157">The iOS and Mac OS X platforms always uses the value set in the template, regardless of other configurations you make.</span></span>

    <span data-ttu-id="9ced9-158">要求元が有効期間を指定できるように CA を構成するには、CA で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-158">To configure the CA to allow the requester to specify the validity period, run the following commands on the CA:</span></span>

    <span data-ttu-id="9ced9-159">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-159">a.</span></span>  <span data-ttu-id="9ced9-160">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span><span class="sxs-lookup"><span data-stu-id="9ced9-160">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span></span>

    <span data-ttu-id="9ced9-161">b.</span><span class="sxs-lookup"><span data-stu-id="9ced9-161">b.</span></span>  <span data-ttu-id="9ced9-162">**net stop certsvc**</span><span class="sxs-lookup"><span data-stu-id="9ced9-162">**net stop certsvc**</span></span>

    <span data-ttu-id="9ced9-163">c.</span><span class="sxs-lookup"><span data-stu-id="9ced9-163">c.</span></span>  <span data-ttu-id="9ced9-164">**net start certsvc**</span><span class="sxs-lookup"><span data-stu-id="9ced9-164">**net start certsvc**</span></span>

3.  <span data-ttu-id="9ced9-165">発行元 CA で、証明機関スナップインを使用して証明書テンプレートを発行します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-165">On the issuing CA, use the Certification Authority snap-in to publish the certificate template.</span></span>

    <span data-ttu-id="9ced9-166">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-166">a.</span></span>  <span data-ttu-id="9ced9-167">**[証明書テンプレート]** ノードを選択し、**[アクション]** -&gt; **[新規]** &gt; **[発行する証明書テンプレート]** の順にクリックして、手順 2. で作成したテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-167">Select the **Certificate Templates** node, click **Action**-&gt; **New** &gt; **Certificate Template to Issue**, and then select the template you created in step 2.</span></span>

    <span data-ttu-id="9ced9-168">b.</span><span class="sxs-lookup"><span data-stu-id="9ced9-168">b.</span></span>  <span data-ttu-id="9ced9-169">**[証明書テンプレート]** フォルダーに表示されることで、テンプレートが発行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-169">Validate that the template published by viewing it under the **Certificate Templates** folder.</span></span>

4.  <span data-ttu-id="9ced9-170">CA コンピューターで、Intune 証明書コネクタをホストするコンピューターが、.PFX プロファイルの作成で使用するテンプレートにアクセスできるように、登録アクセス許可を持つことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-170">On the CA computer, ensure that the computer that hosts the Intune Certificate Connector has enroll permission, so that it can access the template used in creating the .PFX profile.</span></span> <span data-ttu-id="9ced9-171">CA コンピューター プロパティの **[セキュリティ]** タブでそのアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-171">Set that permission on the **Security** tab of the CA computer properties.</span></span>

### <a name="task-2---enable-install-and-configure-the-intune-certificate-connector"></a><span data-ttu-id="9ced9-172">タスク 2 - Intune 証明書コネクタを有効にし、インストールし、構成する</span><span class="sxs-lookup"><span data-stu-id="9ced9-172">Task 2 - Enable, install, and configure the Intune Certificate Connector</span></span>
<span data-ttu-id="9ced9-173">このタスクでは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="9ced9-173">In this task you will:</span></span>

<span data-ttu-id="9ced9-174">証明書コネクタをダウンロードし、インストールして、構成します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-174">Download, install, and configure the Certificate Connector.</span></span>

##### <a name="to-enable-support-for-the-certificate-connector"></a><span data-ttu-id="9ced9-175">証明書コネクタのサポートを有効にするには</span><span class="sxs-lookup"><span data-stu-id="9ced9-175">To enable support for the Certificate Connector</span></span>

1.  <span data-ttu-id="9ced9-176">[Intune の管理コンソール](https://manage.microsoft.com)を開き、**[管理者]** &gt; **[証明書コネクタ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-176">Open the [Intune administration console](https://manage.microsoft.com), and choose **Admin** &gt; **Certificate Connector**.</span></span>

2.  <span data-ttu-id="9ced9-177">**[On-premises Certificate Connector の構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-177">Choose **Configure On-Premises Certificate Connector**.</span></span>

3.  <span data-ttu-id="9ced9-178">**[証明書コネクタを有効にする]**を選択し、 **[OK]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-178">Select **Enable Certificate Connector**, and then choose **OK**.</span></span>

##### <a name="to-download-install-and-configure-the-certificate-connector"></a><span data-ttu-id="9ced9-179">証明書コネクタをダウンロードし、インストールして、構成するには</span><span class="sxs-lookup"><span data-stu-id="9ced9-179">To download, install, and configure the Certificate Connector</span></span>

1. <span data-ttu-id="9ced9-180">[Intune の管理コンソール](https://manage.microsoft.com)を開き、**[管理者]** &gt; **[モバイル デバイス管理]** &gt; **[証明書コネクタ]** &gt; **[証明書コネクタのダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-180">Open the [Intune administration console](https://manage.microsoft.com), and then choose **Admin** &gt; **Mobile Device Management** &gt; **Certificate Connector** &gt; **Download Certificate Connector**.</span></span>

2. <span data-ttu-id="9ced9-181">ダウンロードが完了したら、ダウンロードされたインストーラー (**ndesconnectorssetup.exe**) を実行します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-181">After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**).</span></span>

   <span data-ttu-id="9ced9-182">証明機関と接続できるコンピューターでインストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-182">Run the installer on the computer that is able to connect with the Certification Authority.</span></span> <span data-ttu-id="9ced9-183">[.PFX の配布] オプションを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-183">Choose the .PFX Distribution option, and then choose **Install**.</span></span> <span data-ttu-id="9ced9-184">インストールが完了したら、「[Configure certificate profiles](configure-intune-certificate-profiles.md)」 (証明書プロファイルを構成する) の説明に従って、証明書プロファイルを作成して続行します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-184">When the installation has completed, continue by creating a certificate profile as described in [Configure certificate profiles](configure-intune-certificate-profiles.md).</span></span>

   <!-- Not sure about step 3 below -->

3. <span data-ttu-id="9ced9-185">証明書コネクタのクライアント証明書の入力を求められたら、**[選択]** を選択し、タスク 3 でインストールした**クライアント認証**証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-185">When prompted for the client certificate for the Certificate Connector, choose **Select**, and select the **client authentication** certificate you installed in Task 3.</span></span>

   <span data-ttu-id="9ced9-186">クライアント認証証明書を選択した後、**[Microsoft Intune 証明書コネクタのクライアント証明書]** 画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="9ced9-186">After you select the client authentication certificate, you are returned to the **Client Certificate for Microsoft Intune Certificate Connector** surface.</span></span> <span data-ttu-id="9ced9-187">選択した証明書は表示されませんが、**[次へ]** を選択してその証明書のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-187">Although the certificate you selected is not shown, choose **Next** to view the properties of that certificate.</span></span> <span data-ttu-id="9ced9-188">**[次へ]** を選択して、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-188">Then choose **Next**, and then **Install**.</span></span>

4. <span data-ttu-id="9ced9-189">ウィザードが完了した後、ウィザードを閉じる前に、**[証明書コネクタの UI を起動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ced9-189">After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.</span></span>

   > [!TIP]
   > <span data-ttu-id="9ced9-190">証明書コネクタの UI を起動する前にウィザードを閉じた場合は、次のコマンドを実行して再び開くことができます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-190">If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:</span></span>
   >
   > <span data-ttu-id="9ced9-191">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span><span class="sxs-lookup"><span data-stu-id="9ced9-191">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span></span>

5. <span data-ttu-id="9ced9-192">**証明書コネクタ** UI で:</span><span class="sxs-lookup"><span data-stu-id="9ced9-192">In the **Certificate Connector** UI:</span></span>

   <span data-ttu-id="9ced9-193">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-193">a.</span></span> <span data-ttu-id="9ced9-194">**[サインイン]** を選択し、Intune サービス管理者の資格情報、またはグローバル管理アクセス許可を持つテナント管理者の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-194">Choose **Sign In** and enter your Intune service administrator credentials, or credentials for a tenant administrator with the global administration permission.</span></span>

   <span data-ttu-id="9ced9-195">b.</span><span class="sxs-lookup"><span data-stu-id="9ced9-195">b.</span></span> <span data-ttu-id="9ced9-196">**[詳細設定]** タブを選択し、発行元 CA で**証明書の発行と管理**アクセス許可を持つアカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-196">Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority.</span></span>

   <span data-ttu-id="9ced9-197">c.</span><span class="sxs-lookup"><span data-stu-id="9ced9-197">c.</span></span> <span data-ttu-id="9ced9-198">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-198">Choose **Apply**.</span></span>

   <span data-ttu-id="9ced9-199">これで、証明書コネクタ UI を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="9ced9-199">You can now close the Certificate Connector UI.</span></span>

6. <span data-ttu-id="9ced9-200">コマンド プロンプトを開き、**services.msc** を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-200">Open a command prompt and type **services.msc**.</span></span> <span data-ttu-id="9ced9-201">**[Enter]** キーを押し、**[Intune コネクタ サービス]** を右クリックして、**[再起動]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ced9-201">Then press **Enter**, right-click the **Intune Connector Service**, and choose **Restart**.</span></span>


### <a name="next-steps"></a><span data-ttu-id="9ced9-202">次の手順</span><span class="sxs-lookup"><span data-stu-id="9ced9-202">Next steps</span></span>
<span data-ttu-id="9ced9-203">これで、「[Configure certificate profiles (証明書プロファイルを構成する)](Configure-Intune-certificate-profiles.md)」の説明に従って証明書プロファイルを構成する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="9ced9-203">You are now ready to set up certificate profiles, as described in [Configure certificate profiles](Configure-Intune-certificate-profiles.md).</span></span>
