---
title: "Intune で SCEP 証明書を構成して管理する"
titlesuffix: Azure portal
description: "インフラストラクチャを構成してから、Intune SCEP 証明書プロファイルを作成して割り当てる方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d567d85f-e4ee-458e-bef7-6e275467efce
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36c495767d41c83c1393d837a808961ed9868bed
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="configure-and-manage-scep-certificates-with-intune"></a><span data-ttu-id="572c1-103">Intune で SCEP 証明書を構成して管理する</span><span class="sxs-lookup"><span data-stu-id="572c1-103">Configure and manage SCEP certificates with Intune</span></span>
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="572c1-104">このトピックでは、インフラストラクチャを構成してから、Intune で SCEP (Simple Certificate Enrollment Protocol) 証明書プロファイルを作成して割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="572c1-104">This topic shows how to configure your infrastructure, then create and assign Simple Certificate Enrollment Protocol (SCEP) certificate profiles with Intune.</span></span>

## <a name="configure-on-premises-infrastructure"></a><span data-ttu-id="572c1-105">オンプレミス インフラストラクチャを構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-105">Configure on-premises infrastructure</span></span>

-    <span data-ttu-id="572c1-106">**Active Directory ドメイン**: このセクションで示されているすべてのサーバー (Web アプリケーション プロキシ サーバーを除く) は、Active Directory ドメインに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-106">**Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.</span></span>

-  <span data-ttu-id="572c1-107">**証明機関** (CA): Windows Server 2008 R2 以降の Enterprise エディションで実行するエンタープライズ証明機関 (CA) が必要です。</span><span class="sxs-lookup"><span data-stu-id="572c1-107">**Certification Authority** (CA): An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="572c1-108">スタンドアロン CA はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="572c1-108">A Standalone CA is not supported.</span></span> <span data-ttu-id="572c1-109">詳細については、「[Install the Certification Authority (証明機関のインストール)](http://technet.microsoft.com/library/jj125375.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="572c1-109">For details, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).</span></span>
    <span data-ttu-id="572c1-110">CA が Windows Server 2008 R2 を搭載している場合は、 [KB2483564 の修正プログラムをインストール](http://support.microsoft.com/kb/2483564/)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-110">If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).</span></span>

-  <span data-ttu-id="572c1-111">**NDES サーバー**: Windows Server 2012 R2 以降を実行しているサーバーに、ネットワーク デバイス登録サービス (NDES) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-111">**NDES Server**: On a server that runs Windows Server 2012 R2 or later, you must set up the Network Device Enrollment Service (NDES).</span></span> <span data-ttu-id="572c1-112">エンタープライズ CA も実行しているサーバーで Intune を実行する場合には、ネットワーク デバイス登録サービスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="572c1-112">Intune does not support using NDES when it runs on a server that also runs the Enterprise CA.</span></span> <span data-ttu-id="572c1-113">ネットワーク デバイス登録サービスをホストするための Windows Server 2012 R2 の構成方法については、「[ネットワーク デバイス登録サービスのガイダンス](http://technet.microsoft.com/library/hh831498.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="572c1-113">See [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) for instructions on how to configure Windows Server 2012 R2 to host the Network Device Enrollment Service.</span></span>
<span data-ttu-id="572c1-114">NDES サーバーは、CA をホストしているドメインに参加する必要があります。CA と同じサーバーに置くことはできません。</span><span class="sxs-lookup"><span data-stu-id="572c1-114">The NDES server must be domain joined to the domain that hosts the CA, and not be on the same server as the CA.</span></span> <span data-ttu-id="572c1-115">別個のフォレスト、分離ネットワーク、内部ドメインで NDES サーバーを展開する方法については、「[ポリシー モジュールとネットワーク デバイス登録サービスの使用](https://technet.microsoft.com/library/dn473016.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="572c1-115">More information about deploying the NDES server in a separate forest, isolated network, or internal domain can be found in [Using a Policy Module with the Network Device Enrollment Service](https://technet.microsoft.com/library/dn473016.aspx).</span></span>

-  <span data-ttu-id="572c1-116">**Microsoft Intune Certificate Connector**: Azure Portal を使用して **Certificate Connector** インストーラー (**ndesconnectorssetup.exe**) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="572c1-116">**Microsoft Intune Certificate Connector**: Use the Azure portal to download the **Certificate Connector** installer (**ndesconnectorssetup.exe**).</span></span> <span data-ttu-id="572c1-117">これにより、証明書コネクタをインストールするコンピューターで **ndesconnectorssetup.exe** を実行できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-117">Then you can run **ndesconnectorssetup.exe** on the computer where you want to install the Certificate Connector.</span></span> 
-  <span data-ttu-id="572c1-118">**Web アプリケーション プロキシ サーバー** (省略可能): Web アプリケーション プロキシ (WAP) サーバーとして Windows Server 2012 R2 以降を実行しているサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="572c1-118">**Web Application Proxy Server** (optional): Use a server that runs Windows Server 2012 R2  or later as a Web Application Proxy (WAP) server.</span></span> <span data-ttu-id="572c1-119">この構成は:</span><span class="sxs-lookup"><span data-stu-id="572c1-119">This configuration:</span></span>
    -  <span data-ttu-id="572c1-120">デバイスはインターネット接続を使用して証明書を受信できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-120">Allows devices to receive certificates using an Internet connection.</span></span>
    -  <span data-ttu-id="572c1-121">デバイスがインターネット接続経由で証明書を受信して更新する場合のセキュリティ推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="572c1-121">Is a security recommendation when devices connect through the Internet to receive and renew certificates.</span></span>

 > [!NOTE]           
> -    <span data-ttu-id="572c1-122">WAP をホストするサーバーは、ネットワーク デバイス登録サービスで使用される長い URL のサポートを有効にする [更新プログラムをインストールする](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-122">The server that hosts WAP [must install an update](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service.</span></span> <span data-ttu-id="572c1-123">この更新プログラムは、 [2014 年 12 月の更新プログラムのロールアップ](http://support.microsoft.com/kb/3013769)に含まれます。または、 [KB3011135](http://support.microsoft.com/kb/3011135)から個別に入手できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-123">This update is included with the [December 2014 update rollup](http://support.microsoft.com/kb/3013769), or individually from [KB3011135](http://support.microsoft.com/kb/3011135).</span></span>
>-  <span data-ttu-id="572c1-124">また、WAP をホストするサーバーが、外部クライアントに公開される名前と一致する SSL 証明書を持ち、NDES サーバーで使用される SSL 証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-124">Also, the server that hosts WAP must have an SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server.</span></span> <span data-ttu-id="572c1-125">これらの証明書を使用すると、WAP サーバーはクライアントからの SSL 接続を終了し、NDES サーバーへの新しい SSL 接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-125">These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.</span></span>
    <span data-ttu-id="572c1-126">WAP の証明書については、「[内部アプリケーションの公開のために Web アプリケーション プロキシをインストールおよび構成する](https://technet.microsoft.com/library/dn383650.aspx)」の**証明書の計画**に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="572c1-126">For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx).</span></span> <span data-ttu-id="572c1-127">WAP サーバーの一般的な情報については、「[Web アプリケーション プロキシの使用](http://technet.microsoft.com/library/dn584113.aspx)」を参照してください。|</span><span class="sxs-lookup"><span data-stu-id="572c1-127">For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|</span></span>

### <a name="network-requirements"></a><span data-ttu-id="572c1-128">ネットワークの要件</span><span class="sxs-lookup"><span data-stu-id="572c1-128">Network requirements</span></span>

<span data-ttu-id="572c1-129">インターネットから境界ネットワークまでを範囲として、インターネット上のあらゆるホスト/IP アドレスから NDES サーバーへの送信にポート 443 を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="572c1-129">From the Internet to perimeter network, allow port 443 from all hosts/IP addresses on the internet to the NDES server.</span></span>

<span data-ttu-id="572c1-130">境界ネットワークから信頼されたネットワークまでを範囲として、ドメイン参加 NDES サーバーのドメイン アクセスに必要なすべてのポートとプロトコルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="572c1-130">From the perimeter network to trusted network, allow all ports and protocols needed for domain access on the domain-joined NDES server.</span></span> <span data-ttu-id="572c1-131">NDES サーバーは、証明書サーバー、DNS サーバー、構成マネージャー サーバー、ドメイン コントローラーへのアクセス許可を必要とします。</span><span class="sxs-lookup"><span data-stu-id="572c1-131">The NDES server needs access to the certificate servers, DNS servers, Configuration Manager servers, and domain controllers.</span></span>

<span data-ttu-id="572c1-132">NDES サーバーは、[Azure AD アプリケーション プロキシ](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/)、[Web アクセス プロキシ](https://technet.microsoft.com/library/dn584107.aspx)、サード パーティ製のプロキシなどのプロキシを通じて公開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="572c1-132">We recommend publishing the NDES server through a proxy, such as the [Azure AD application proxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx), or a third-party proxy.</span></span>


### <a name="certificates-and-templates"></a><span data-ttu-id="572c1-133">証明書とテンプレート</span><span class="sxs-lookup"><span data-stu-id="572c1-133">Certificates and templates</span></span>

|<span data-ttu-id="572c1-134">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="572c1-134">Object</span></span>|<span data-ttu-id="572c1-135">説明</span><span class="sxs-lookup"><span data-stu-id="572c1-135">Details</span></span>|
|----------|-----------|
|<span data-ttu-id="572c1-136">**証明書テンプレート**</span><span class="sxs-lookup"><span data-stu-id="572c1-136">**Certificate Template**</span></span>|<span data-ttu-id="572c1-137">発行元 CA でこのテンプレートを構成します。</span><span class="sxs-lookup"><span data-stu-id="572c1-137">Configure this template on your issuing CA.</span></span>|
|<span data-ttu-id="572c1-138">**クライアント認証証明書**</span><span class="sxs-lookup"><span data-stu-id="572c1-138">**Client authentication certificate**</span></span>|<span data-ttu-id="572c1-139">発行元 CA またはパブリック CA から要求されます。この証明書を NDES サーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-139">Requested from your issuing CA or public CA; you install this certificate on the NDES Server.</span></span>|
|<span data-ttu-id="572c1-140">**サーバー認証証明書**</span><span class="sxs-lookup"><span data-stu-id="572c1-140">**Server authentication certificate**</span></span>|<span data-ttu-id="572c1-141">発行元 CA またはパブリック CA から要求されます。この SSL 証明書をインストールし NDES サーバーの IIS にバインドします。</span><span class="sxs-lookup"><span data-stu-id="572c1-141">Requested from your issuing CA or public CA; you install and bind this SSL certificate in IIS on the NDES server.</span></span>|
|<span data-ttu-id="572c1-142">**信頼されたルート CA 証明書**</span><span class="sxs-lookup"><span data-stu-id="572c1-142">**Trusted Root CA certificate**</span></span>|<span data-ttu-id="572c1-143">この証明書をルート CA またはルート CA を信頼するデバイスから **.cer** ファイルとしてエクスポートし、信頼された CA 証明書プロファイルを使用してデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="572c1-143">You export this certificate as a **.cer** file from the root CA or any device that trusts the root CA, and assign it to devices by using the Trusted CA certificate profile.</span></span><br /><br /><span data-ttu-id="572c1-144">オペレーティング システムのプラットフォームごとに 1 つの信頼されたルート CA 証明書を使用し、作成する各信頼されたルート証明書プロファイルに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="572c1-144">You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.</span></span><br /><br /><span data-ttu-id="572c1-145">必要に応じて、信頼されたルート CA 証明書を追加して使用できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-145">You can use additional Trusted Root CA certificates when needed.</span></span> <span data-ttu-id="572c1-146">ルート CA 証明書を追加する局面としては、Wi-Fi アクセス ポイント用のサーバー認証証明書に署名する CA の信頼性を担保する必要がある場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="572c1-146">For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.</span></span>|

### <a name="accounts"></a><span data-ttu-id="572c1-147">アカウント</span><span class="sxs-lookup"><span data-stu-id="572c1-147">Accounts</span></span>

|<span data-ttu-id="572c1-148">名前</span><span class="sxs-lookup"><span data-stu-id="572c1-148">Name</span></span>|<span data-ttu-id="572c1-149">説明</span><span class="sxs-lookup"><span data-stu-id="572c1-149">Details</span></span>|
|--------|-----------|
|<span data-ttu-id="572c1-150">**NDES サービス アカウント**</span><span class="sxs-lookup"><span data-stu-id="572c1-150">**NDES service account**</span></span>|<span data-ttu-id="572c1-151">NDES サービス アカウントとして使用するドメイン ユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-151">Specify a domain user account to use as the NDES Service account.</span></span>|

## <a name="configure-your-infrastructure"></a><span data-ttu-id="572c1-152">インフラストラクチャを構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-152">Configure your infrastructure</span></span>
<span data-ttu-id="572c1-153">証明書プロファイルを構成する前に、次のタスクを行う必要があります。これには、Windows Server 2012 R2 および Active Directory 証明書サービス (ADCS) の知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="572c1-153">Before you can configure certificate profiles you must complete the following tasks, which require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):</span></span>

<span data-ttu-id="572c1-154">**手順 1**: NDES サービス アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="572c1-154">**Step 1**: Create an NDES service account</span></span>

<span data-ttu-id="572c1-155">**手順 2**: 証明機関で証明書テンプレートを構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-155">**Step 2**: Configure certificate templates on the certification authority</span></span>

<span data-ttu-id="572c1-156">**手順 3**: NDES サーバーで前提条件を構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-156">**Step 3**: Configure prerequisites on the NDES server</span></span>

<span data-ttu-id="572c1-157">**手順 4**: Intune で使用するための NDES を構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-157">**Step 4**: Configure NDES for use with Intune</span></span>

<span data-ttu-id="572c1-158">**手順 5**: Intune Certificate Connector を有効にし、インストールし、構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-158">**Step 5**: Enable, install, and configure the Intune Certificate Connector</span></span>

#### <a name="step-1---create-an-ndes-service-account"></a><span data-ttu-id="572c1-159">手順 1 - NDES サービス アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="572c1-159">Step 1 - Create an NDES service account</span></span>

<span data-ttu-id="572c1-160">NDES サービス アカウントとして使用するドメイン ユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="572c1-160">Create a domain user account to use as the NDES service account.</span></span> <span data-ttu-id="572c1-161">NDES をインストールして構成する前に、発行元 CA でテンプレートを構成するときに、このアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-161">You specify this account when you configure templates on the issuing CA before you install and configure NDES.</span></span> <span data-ttu-id="572c1-162">既定の権限である、**ローカル ログオン**、**サービスとしてログオン**、**バッチ ジョブとしてログオン**などの権限がユーザーに付与されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="572c1-162">Make sure the user has the default rights, **Logon Locally**, **Logon as a Service** and **Logon as a batch job** rights.</span></span> <span data-ttu-id="572c1-163">ポリシーを強化し、これらの権限を無効にしている組織もあります。</span><span class="sxs-lookup"><span data-stu-id="572c1-163">Some organizations have hardening policies that disable those rights.</span></span>

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a><span data-ttu-id="572c1-164">手順 2 - 証明機関で証明書テンプレートを構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-164">Step 2 - Configure certificate templates on the certification authority</span></span>
<span data-ttu-id="572c1-165">このタスクでは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="572c1-165">In this task you:</span></span>

-   <span data-ttu-id="572c1-166">NDES の証明書テンプレートを構成します</span><span class="sxs-lookup"><span data-stu-id="572c1-166">Configure a certificate template for NDES</span></span>

-   <span data-ttu-id="572c1-167">NDES に証明書テンプレートを発行します</span><span class="sxs-lookup"><span data-stu-id="572c1-167">Publish the certificate template for NDES</span></span>

##### <a name="to-configure-the-certification-authority"></a><span data-ttu-id="572c1-168">証明機関を構成するには</span><span class="sxs-lookup"><span data-stu-id="572c1-168">To configure the certification authority</span></span>

1.  <span data-ttu-id="572c1-169">エンタープライズ管理者としてログオンします。</span><span class="sxs-lookup"><span data-stu-id="572c1-169">Log on as an enterprise administrator.</span></span>

2.  <span data-ttu-id="572c1-170">発行元 CA で、証明書テンプレート スナップインを使用して、新しいカスタム テンプレートを作成するか、または既存のテンプレートをコピーして NDES で使用するために (ユーザー テンプレートのように) 既存のテンプレートを編集します。</span><span class="sxs-lookup"><span data-stu-id="572c1-170">On the issuing CA, use the Certificate Templates snap-in to create a new custom template or copy an existing template and then edit an existing template (like the User template), for use with NDES.</span></span>

    >[!NOTE]
    > <span data-ttu-id="572c1-171">NDES 証明書テンプレートは、v2 証明書テンプレートを基盤とする必要があります (Windows 2003 の互換性あり)。</span><span class="sxs-lookup"><span data-stu-id="572c1-171">The NDES certificate template must be based off a v2 Certificate Template (with Windows 2003 compatibility).</span></span>

    <span data-ttu-id="572c1-172">テンプレートには次の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="572c1-172">The template must have the following configurations:</span></span>

    -   <span data-ttu-id="572c1-173">テンプレートのわかりやすい **テンプレート表示名** を指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-173">Specify a friendly **Template display name** for the template.</span></span>

    -   <span data-ttu-id="572c1-174">**[サブジェクト名]** タブで **[要求に含まれる]** を選択します</span><span class="sxs-lookup"><span data-stu-id="572c1-174">On the **Subject Name** tab, select **Supply in the request**.</span></span> <span data-ttu-id="572c1-175">(セキュリティが NDES の Intune ポリシー モジュールによって適用されます)。</span><span class="sxs-lookup"><span data-stu-id="572c1-175">(Security is enforced by the Intune policy module for NDES).</span></span>

    -   <span data-ttu-id="572c1-176">**[拡張]** タブで、**[アプリケーション ポリシーの説明]** に **[クライアント認証]** が含まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="572c1-176">On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="572c1-177">iOS および macOS の証明書テンプレートの場合、**[拡張]** タブで、**[キー使用法]** を編集し、**[署名は発行元の証明である]** がオンになっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="572c1-177">For iOS and macOS certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure **Signature is proof of origin** is not selected.</span></span>

    -   <span data-ttu-id="572c1-178">**[セキュリティ]** タブで、NDES サービス アカウントを追加し、テンプレートへの **[登録]** アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="572c1-178">On the **Security** tab, add the NDES service account, and give it **Enroll** permissions to the template.</span></span> <span data-ttu-id="572c1-179">SCEP プロファイルを作成する Intune 管理者は、SCEP プロファイルの作成時にテンプレートを閲覧できるように、**読み取り**権限を必要とします。</span><span class="sxs-lookup"><span data-stu-id="572c1-179">Intune admins who create SCEP profiles require **Read** rights so that they can browse to the template when creating SCEP profiles.</span></span>

    > [!NOTE]
    > <span data-ttu-id="572c1-180">証明書を失効させるには、証明書プロファイルで使用されている証明書テンプレートごとに*証明書の発行および管理*の権限が NDES サービス アカウントに必要です。</span><span class="sxs-lookup"><span data-stu-id="572c1-180">To revoke certificates the NDES service account needs *Issue and Manage Certificates* rights for each certificate template used by a certificate profile.</span></span>

3.  <span data-ttu-id="572c1-181">**[一般]** タブでテンプレートの **[有効期間]** を確認します。</span><span class="sxs-lookup"><span data-stu-id="572c1-181">Review the **Validity period** on the **General** tab of the template.</span></span> <span data-ttu-id="572c1-182">既定では、Intune はテンプレートで構成されている値を使用します。</span><span class="sxs-lookup"><span data-stu-id="572c1-182">By default, Intune uses the value configured in the template.</span></span> <span data-ttu-id="572c1-183">ただし、要求元が異なる値を指定できるように CA を構成できます。異なる値は、Intune 管理者コンソールから設定できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-183">However, you have the option to configure the CA to allow the requester to specify a different value, which you can then set from within the Intune Administrator console.</span></span> <span data-ttu-id="572c1-184">常にテンプレートの値を使用する場合は、この手順の残りの部分をスキップします。</span><span class="sxs-lookup"><span data-stu-id="572c1-184">If you want to always use the value in the template, skip the remainder of this step.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="572c1-185">iOS および macOS は、他の構成に関係なく、常にテンプレートで設定される値を使用します。</span><span class="sxs-lookup"><span data-stu-id="572c1-185">iOS and macOS always use the value set in the template regardless of other configurations you make.</span></span>

<span data-ttu-id="572c1-186">次は、サンプル テンプレート構成のスクリーンショットです。</span><span class="sxs-lookup"><span data-stu-id="572c1-186">Here are screenshots of an example template configuration.</span></span>

![テンプレート、[要求処理] タブ](.\media\scep_ndes_request_handling.png)

![テンプレート、[サブジェクト名] タブ](.\media\scep_ndes_subject_name.jpg)

![テンプレート、[セキュリティ] タブ](.\media\scep_ndes_security.jpg)

![テンプレート、[拡張] タブ](.\media\scep_ndes_extensions.jpg)

![テンプレート、[発行要件] タブ](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > <span data-ttu-id="572c1-192">アプリケーション ポリシーの場合、必要なアプリケーション ポリシーのみを追加します。</span><span class="sxs-lookup"><span data-stu-id="572c1-192">For Application Policies, only add the application policies required.</span></span> <span data-ttu-id="572c1-193">セキュリティ管理者の選択を確定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-193">Confirm your choices with your security admins.</span></span>



<span data-ttu-id="572c1-194">要求元が有効期間を指定できるように CA を構成するには、</span><span class="sxs-lookup"><span data-stu-id="572c1-194">To configure the CA to allow the requester to specify the validity period:</span></span>

1. <span data-ttu-id="572c1-195">CA で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="572c1-195">On the CA run the following commands:</span></span>
    - <span data-ttu-id="572c1-196">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span><span class="sxs-lookup"><span data-stu-id="572c1-196">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span></span>
    - <span data-ttu-id="572c1-197">**net stop certsvc**</span><span class="sxs-lookup"><span data-stu-id="572c1-197">**net stop certsvc**</span></span>
    - <span data-ttu-id="572c1-198">**net start certsvc**</span><span class="sxs-lookup"><span data-stu-id="572c1-198">**net start certsvc**</span></span>
2. <span data-ttu-id="572c1-199">発行元 CA で、証明機関スナップインを使用して証明書テンプレートを発行します。</span><span class="sxs-lookup"><span data-stu-id="572c1-199">On the issuing CA, use the Certification Authority snap-in to publish the certificate template.</span></span>
    <span data-ttu-id="572c1-200">**[証明書テンプレート]** ノードを選択し、**[アクション]** -&gt; **[新規]** &gt; **[発行する証明書テンプレート]** の順にクリックして、手順 2. で作成したテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-200">Select the **Certificate Templates** node, click **Action**-&gt; **New** &gt; **Certificate Template to Issue**, and then select the template you created in step 2.</span></span>
3. <span data-ttu-id="572c1-201">**[証明書テンプレート]** フォルダーに表示されることで、テンプレートが発行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="572c1-201">Validate that the template published by viewing it under the **Certificate Templates** folder.</span></span>


#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a><span data-ttu-id="572c1-202">手順 3 - NDES サーバーで前提条件を構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-202">Step 3 - Configure prerequisites on the NDES server</span></span>
<span data-ttu-id="572c1-203">このタスクでは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="572c1-203">In this task you:</span></span>

-   <span data-ttu-id="572c1-204">Windows サーバーに NDES を追加し、NDES をサポートするように IIS を構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-204">Add NDES to a Windows Server and configure IIS to support NDES</span></span>

-   <span data-ttu-id="572c1-205">NDES サービス アカウントを IIS_IUSR グループに追加します</span><span class="sxs-lookup"><span data-stu-id="572c1-205">Add the NDES Service account to the IIS_IUSR group</span></span>

-   <span data-ttu-id="572c1-206">NDES サービス アカウントの SPN を設定します</span><span class="sxs-lookup"><span data-stu-id="572c1-206">Set the SPN for the NDES Service account</span></span>




   1.  <span data-ttu-id="572c1-207">NDES をホストするサーバーに**エンタープライズ管理者**としてログインし、[役割と機能の追加ウィザード](https://technet.microsoft.com/library/hh831809.aspx)を使用して NDES をインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-207">On the server that hosts NDES, log on as an **Enterprise Administrator**, and then use the [Add Roles and Features Wizard](https://technet.microsoft.com/library/hh831809.aspx) to install NDES:</span></span>

    1.  <span data-ttu-id="572c1-208">ウィザードで、**[Active Directory 証明書サービス]** を選択して AD CS 役割サービスにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="572c1-208">In the Wizard, select **Active Directory Certificate Services** to gain access to the AD CS Role Services.</span></span> <span data-ttu-id="572c1-209">**[ネットワーク デバイス登録サービス]** をオンにし、**[証明機関]** をオフにして、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="572c1-209">Select the **Network Device Enrollment Service**, uncheck **Certification Authority**, and then complete the wizard.</span></span>

        > [!TIP]
        > <span data-ttu-id="572c1-210">ウィザードの **[インストールの進行状況]** ページでは、**[閉じる]** をクリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="572c1-210">On the **Installation progress** page of the wizard, do not click **Close**.</span></span> <span data-ttu-id="572c1-211">代わりに、**[対象サーバーに Active Directory 証明書サービスを構成する]** のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="572c1-211">Instead, click the link for **Configure Active Directory Certificate Services on the destination server**.</span></span> <span data-ttu-id="572c1-212">これにより、次のタスクで使用する **[AD CS の構成]** ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="572c1-212">This opens the **AD CS Configuration** wizard that you use for the next task.</span></span> <span data-ttu-id="572c1-213">[AD CS の構成] が開いた後は、役割と機能の追加ウィザードを閉じてかまいません。</span><span class="sxs-lookup"><span data-stu-id="572c1-213">After AD CS Configuration opens, you can close the Add Roles and Features wizard.</span></span>

    2.  <span data-ttu-id="572c1-214">NDES がサーバーに追加されるときに、ウィザードは IIS もインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-214">When NDES is added to the server, the wizard also installs IIS.</span></span> <span data-ttu-id="572c1-215">IIS が次の構成であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="572c1-215">Ensure IIS has the following configurations:</span></span>

        -   <span data-ttu-id="572c1-216">**[Web サーバー]** &gt; **[セキュリティ]** &gt; **[要求のフィルタリング]**</span><span class="sxs-lookup"><span data-stu-id="572c1-216">**Web Server** &gt; **Security** &gt; **Request Filtering**</span></span>

        -   <span data-ttu-id="572c1-217">**[Web サーバー]** &gt; **[アプリケーション開発]** &gt; **[ASP.NET 3.5]**。</span><span class="sxs-lookup"><span data-stu-id="572c1-217">**Web Server** &gt; **Application Development** &gt; **ASP.NET 3.5**.</span></span> <span data-ttu-id="572c1-218">ASP.NET 3.5 をインストールすると、.NET Framework 3.5 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="572c1-218">Installing ASP.NET 3.5 installs .NET Framework 3.5.</span></span> <span data-ttu-id="572c1-219">.NET Framework 3.5 をインストールするとき、**[.NET Framework 3.5]** のコア機能および **[HTTP アクティブ化]** の両方をインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-219">When installing .NET Framework 3.5, install both the core **.NET Framework 3.5** feature and **HTTP Activation**.</span></span>

        -   <span data-ttu-id="572c1-220">**[Web サーバー]** &gt; **[アプリケーション開発]** &gt; **[ASP.NET 4.5]**。</span><span class="sxs-lookup"><span data-stu-id="572c1-220">**Web Server** &gt; **Application Development** &gt; **ASP.NET 4.5**.</span></span> <span data-ttu-id="572c1-221">ASP.NET 4.5 をインストールすると、.NET Framework 4.5 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="572c1-221">Installing ASP.NET 4.5 installs .NET Framework 4.5.</span></span> <span data-ttu-id="572c1-222">.NET Framework 4.5 をインストールする際に、**[.NET Framework 4.5]** のコア機能、**[ASP.NET 4.5]**、および **[WCF サービス]** &gt; **[HTTP アクティブ化]** 機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-222">When installing .NET Framework 4.5, install the core **.NET Framework 4.5** feature, **ASP.NET 4.5**, and the **WCF Services** &gt; **HTTP Activation** feature.</span></span>

        -   <span data-ttu-id="572c1-223">**[管理ツール]** &gt; **[IIS 6 と互換性のある管理]** &gt; **[IIS 6 メタベース互換]**</span><span class="sxs-lookup"><span data-stu-id="572c1-223">**Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 Metabase Compatibility**</span></span>

        -   <span data-ttu-id="572c1-224">**[管理ツール]** &gt; **[IIS 6 と互換性のある管理]** &gt; **[IIS 6 WMI 互換性]**</span><span class="sxs-lookup"><span data-stu-id="572c1-224">**Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 WMI Compatibility**</span></span>

  2.  <span data-ttu-id="572c1-225">サーバーで、**IIS_IUSR** グループのメンバーとして NDES サービス アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="572c1-225">On the server, add the NDES service account as a member of the **IIS_IUSR** group.</span></span>

   3.  <span data-ttu-id="572c1-226">管理者特権のコマンド プロンプトで、次のコマンドを実行して、NDES サービス アカウントの SPN を設定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-226">In an elevated command prompt, run the following command to set the SPN of the NDES Service account:</span></span>

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   <span data-ttu-id="572c1-227">たとえば、NDES サーバーの名前が **Server01**、ドメインが **Contoso.com**、サービス アカウントが **NDESService**の場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="572c1-227">For example, if your NDES Server is named **Server01**, your domain is **Contoso.com**, and the service account is **NDESService**, use:</span></span>

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a><span data-ttu-id="572c1-228">手順 4 - Intune で使用するための NDES を構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-228">Step 4 - Configure NDES for use with Intune</span></span>
<span data-ttu-id="572c1-229">このタスクでは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="572c1-229">In this task you:</span></span>

-   <span data-ttu-id="572c1-230">発行元 CA で使用するための NDES を構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-230">Configure NDES for use with the issuing CA</span></span>

-   <span data-ttu-id="572c1-231">IIS でサーバー認証 (SSL) 証明書をバインドします</span><span class="sxs-lookup"><span data-stu-id="572c1-231">Bind the server authentication (SSL) certificate in IIS</span></span>

-   <span data-ttu-id="572c1-232">IIS で要求フィルター処理を構成します</span><span class="sxs-lookup"><span data-stu-id="572c1-232">Configure Request Filtering in IIS</span></span>


1.  <span data-ttu-id="572c1-233">NDES サーバーで AD CS 構成ウィザードを開き、次の構成を行います。</span><span class="sxs-lookup"><span data-stu-id="572c1-233">On the NDES Server, open the AD CS Configuration wizard and then make the following configurations:</span></span>

    > [!TIP]
    > <span data-ttu-id="572c1-234">前のタスクでリンクをクリックした場合、このウィザードは既に開いています。</span><span class="sxs-lookup"><span data-stu-id="572c1-234">If you clicked the link in the previous task, this wizard is already open.</span></span> <span data-ttu-id="572c1-235">それ以外の場合、サーバー マネージャーを開いて Active Directory 証明書サービスの展開後構成にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="572c1-235">Otherwise, open Server Manager to access the post-deployment configuration for Active Directory Certificate Services.</span></span>

    -   <span data-ttu-id="572c1-236">**[役割サービス]** ページで、**[ネットワーク デバイス登録サービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-236">On the **Role Services** Page, select the **Network Device Enrollment Service**.</span></span>

    -   <span data-ttu-id="572c1-237">**[NDES のサービス アカウント]** ページで、NDES サービス アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-237">On the **Service Account for NDES** page, specify the NDES Service Account.</span></span>

    -   <span data-ttu-id="572c1-238">**[NDES 用の CA]** ページで、**[選択]** をクリックし、証明書テンプレートを構成した発行元 CA を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-238">On the **CA for NDES** page, click **Select**, and then select the issuing CA where you configured the certificate template.</span></span>

    -   <span data-ttu-id="572c1-239">**[NDES の暗号化]** ページで、会社の要件を満たすキーの長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-239">On the **Cryptography for NDES** page, set the key length to meet your company requirements.</span></span>

    <span data-ttu-id="572c1-240">**[確認]** ページで、**[構成]** をクリックしてウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="572c1-240">On the **Confirmation** page, click **Configure** to complete the wizard.</span></span>

2.  <span data-ttu-id="572c1-241">ウィザードが完了した後、NDES サーバーで次のレジストリ キーを編集します。</span><span class="sxs-lookup"><span data-stu-id="572c1-241">After the wizard completes, edit the following registry key on the NDES Server:</span></span>

    -   <span data-ttu-id="572c1-242">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**</span><span class="sxs-lookup"><span data-stu-id="572c1-242">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**</span></span>

    <span data-ttu-id="572c1-243">このキーを編集するには、**[要求の処理]** タブで証明書テンプレートの **[目的]** を確認し、既存のデータを、タスク 1 で指定した (テンプレートの表示名ではなく) 証明書テンプレートの名前に置き換えることによって、レジストリの対応するエントリを編集します。</span><span class="sxs-lookup"><span data-stu-id="572c1-243">To edit this key, identify the certificate template's **Purpose**, as found on its **Request Handling** tab, and then edit the corresponding entry in the registry by replacing the existing data with the name of the certificate template (not the display name of the template) that you specified in Task 1.</span></span> <span data-ttu-id="572c1-244">次の表では、証明書テンプレートの目的とレジストリの値の対応を示します。</span><span class="sxs-lookup"><span data-stu-id="572c1-244">The following table maps the certificate template purpose to the values in the registry:</span></span>

    |<span data-ttu-id="572c1-245">証明書テンプレートの目的 ([要求の処理] タブ)</span><span class="sxs-lookup"><span data-stu-id="572c1-245">Certificate template Purpose (On the Request Handling tab)</span></span>|<span data-ttu-id="572c1-246">編集するレジストリ値</span><span class="sxs-lookup"><span data-stu-id="572c1-246">Registry value to edit</span></span>|<span data-ttu-id="572c1-247">SCEP プロファイルについて Intune 管理コンソールに表示される値</span><span class="sxs-lookup"><span data-stu-id="572c1-247">Value seen in the Intune admin console for the SCEP profile</span></span>|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |<span data-ttu-id="572c1-248">署名</span><span class="sxs-lookup"><span data-stu-id="572c1-248">Signature</span></span>|<span data-ttu-id="572c1-249">SignatureTemplate</span><span class="sxs-lookup"><span data-stu-id="572c1-249">SignatureTemplate</span></span>|<span data-ttu-id="572c1-250">デジタル署名</span><span class="sxs-lookup"><span data-stu-id="572c1-250">Digital Signature</span></span>|
    |<span data-ttu-id="572c1-251">暗号化</span><span class="sxs-lookup"><span data-stu-id="572c1-251">Encryption</span></span>|<span data-ttu-id="572c1-252">EncryptionTemplate</span><span class="sxs-lookup"><span data-stu-id="572c1-252">EncryptionTemplate</span></span>|<span data-ttu-id="572c1-253">キーの暗号化</span><span class="sxs-lookup"><span data-stu-id="572c1-253">Key Encipherment</span></span>|
    |<span data-ttu-id="572c1-254">署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="572c1-254">Signature and encryption</span></span>|<span data-ttu-id="572c1-255">GeneralPurposeTemplate</span><span class="sxs-lookup"><span data-stu-id="572c1-255">GeneralPurposeTemplate</span></span>|<span data-ttu-id="572c1-256">キーの暗号化</span><span class="sxs-lookup"><span data-stu-id="572c1-256">Key Encipherment</span></span><br /><br /><span data-ttu-id="572c1-257">デジタル署名</span><span class="sxs-lookup"><span data-stu-id="572c1-257">Digital Signature</span></span>|
    <span data-ttu-id="572c1-258">たとえば、証明書テンプレートの目的が **[暗号化]** の場合、 **EncryptionTemplate** の値を証明書テンプレートの名前に編集します。</span><span class="sxs-lookup"><span data-stu-id="572c1-258">For example, if the Purpose of your certificate template is **Encryption**, then edit the **EncryptionTemplate** value to be the name of your certificate template.</span></span>

3. <span data-ttu-id="572c1-259">NDES サーバーは、長い URL (クエリ) を受け取ります。2 つのレジストリ エントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-259">The NDES server receives long URLs (queries), which require that you add two registry entries:</span></span>

    |<span data-ttu-id="572c1-260">場所</span><span class="sxs-lookup"><span data-stu-id="572c1-260">Location</span></span>|<span data-ttu-id="572c1-261">値</span><span class="sxs-lookup"><span data-stu-id="572c1-261">Value</span></span>|<span data-ttu-id="572c1-262">型</span><span class="sxs-lookup"><span data-stu-id="572c1-262">Type</span></span>|<span data-ttu-id="572c1-263">データ</span><span class="sxs-lookup"><span data-stu-id="572c1-263">Data</span></span>|
    |-------|-----|----|----|
    |<span data-ttu-id="572c1-264">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span><span class="sxs-lookup"><span data-stu-id="572c1-264">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span></span>|<span data-ttu-id="572c1-265">MaxFieldLength</span><span class="sxs-lookup"><span data-stu-id="572c1-265">MaxFieldLength</span></span>|<span data-ttu-id="572c1-266">DWORD</span><span class="sxs-lookup"><span data-stu-id="572c1-266">DWORD</span></span>|<span data-ttu-id="572c1-267">65534 (10 進数)</span><span class="sxs-lookup"><span data-stu-id="572c1-267">65534 (decimal)</span></span>|
    |<span data-ttu-id="572c1-268">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span><span class="sxs-lookup"><span data-stu-id="572c1-268">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span></span>|<span data-ttu-id="572c1-269">MaxRequestBytes</span><span class="sxs-lookup"><span data-stu-id="572c1-269">MaxRequestBytes</span></span>|<span data-ttu-id="572c1-270">DWORD</span><span class="sxs-lookup"><span data-stu-id="572c1-270">DWORD</span></span>|<span data-ttu-id="572c1-271">65534 (10 進数)</span><span class="sxs-lookup"><span data-stu-id="572c1-271">65534 (decimal)</span></span>|


4. <span data-ttu-id="572c1-272">IIS マネージャーで、**[既定の Web サイト]**  ->  **[要求のフィルタリング]**  ->  **[機能設定の編集]** の順に選択し、**[URL の最大長]** と **[クエリ文字列の最大長]** を図のように *65534* に変更します。</span><span class="sxs-lookup"><span data-stu-id="572c1-272">In IIS manager, select **Default Web Site** -> **Request Filtering** -> **Edit Feature Setting**, and change the **Maximum URL length** and **Maximum query string** to *65534*, as shown.</span></span>

    ![IIS の URL とクエリの最大長](.\media\SCEP_IIS_max_URL.png)

5.  <span data-ttu-id="572c1-274">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="572c1-274">Restart the server.</span></span> <span data-ttu-id="572c1-275">サーバーで実行されている **iisreset** は、これらの変更をファイナライズするために十分ではないでしょう。</span><span class="sxs-lookup"><span data-stu-id="572c1-275">Running **iisreset** on the server is not sufficient to finalize these changes.</span></span>
6. <span data-ttu-id="572c1-276">http://*FQDN*/certsrv/mscep/mscep.dll に移動します。</span><span class="sxs-lookup"><span data-stu-id="572c1-276">Browse to http://*FQDN*/certsrv/mscep/mscep.dll.</span></span> <span data-ttu-id="572c1-277">次のような NDES ページが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="572c1-277">You should see an NDES page similar to this:</span></span>

    ![NDES のテスト](.\media\SCEP_NDES_URL.png)

    <span data-ttu-id="572c1-279">「**503 サービスを利用できません**」が表示された場合、イベント ビューアを確認します。</span><span class="sxs-lookup"><span data-stu-id="572c1-279">If you get a **503 Service unavailable**, check the event viewer.</span></span> <span data-ttu-id="572c1-280">おそらくは、NDES ユーザーに権限がないため、アプリケーション プールが停止しているでしょう。</span><span class="sxs-lookup"><span data-stu-id="572c1-280">It's likely that the application pool is stopped due to a missing right for the NDES user.</span></span> <span data-ttu-id="572c1-281">それらの権限に関する説明はタスク 1 にあります。</span><span class="sxs-lookup"><span data-stu-id="572c1-281">Those rights are described in Task 1.</span></span>

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a><span data-ttu-id="572c1-282">NDES サーバーで証明書をインストールしてバインドするには</span><span class="sxs-lookup"><span data-stu-id="572c1-282">To Install and bind certificates on the NDES Server</span></span>

1.  <span data-ttu-id="572c1-283">NDES サーバーで、内部 CA またはパブリック CA に **サーバー認証** 証明書を要求してインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-283">On your NDES Server, request and install a **server authentication** certificate from your internal CA or public CA.</span></span> <span data-ttu-id="572c1-284">その後、この SSL 証明書を IIS でバインドします。</span><span class="sxs-lookup"><span data-stu-id="572c1-284">You then bind this SSL certificate in IIS.</span></span>

    > [!TIP]
    > <span data-ttu-id="572c1-285">IIS で SSL 証明書をバインドした後、クライアント認証証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-285">After you bind the SSL certificate in IIS, install a client authentication certificate.</span></span> <span data-ttu-id="572c1-286">この証明書は、NDES サーバーによって信頼されている CA によって発行できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-286">This certificate can be issued by any CA that is trusted by the NDES Server.</span></span> <span data-ttu-id="572c1-287">最善の方法ではありませんが、証明書にサーバーとクライアント両方の EKU (Enhance Key Usage) がある場合は、同じ証明書をサーバー認証とクライアント認証の両方に使用できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-287">Although it is not a best practice, you can use the same certificate for both server and client authentication as long as the certificate has both Enhance Key Usages (EKUs).</span></span> <span data-ttu-id="572c1-288">これらの認証証明書については、次の手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="572c1-288">Review the following steps for information about these authentication certificates.</span></span>

    1.  <span data-ttu-id="572c1-289">サーバー認証証明書を取得した後、 **IIS マネージャー**を開き、**[接続]** ウィンドウで **[既定の Web サイト]** を選択し、**[操作]** ウィンドウの **[バインド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572c1-289">After you obtain the server authentication certificate, open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then click **Bindings** in the **Actions** pane.</span></span>

    2.  <span data-ttu-id="572c1-290">**[追加]** をクリックし、**[種類]** を **[https]** に設定して、ポートが **443**であることを確認します</span><span class="sxs-lookup"><span data-stu-id="572c1-290">Click **Add**, set **Type** to **https**, and then ensure the port is **443**.</span></span> <span data-ttu-id="572c1-291">(スタンドアロン Intune の場合はポート 443 のみがサポートされます)。</span><span class="sxs-lookup"><span data-stu-id="572c1-291">(Only port 443 is supported for standalone Intune.</span></span>

    3.  <span data-ttu-id="572c1-292">**[SSL 証明書]** で、サーバー認証証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-292">For **SSL certificate**, specify the server authentication certificate.</span></span>

        > [!NOTE]
        > <span data-ttu-id="572c1-293">NDES サーバーが 1 つのネットワーク アドレスに対して外部名と内部名の両方を使用している場合、サーバー認証証明書の **[サブジェクト名]** は外部パブリック サーバー名、**[サブジェクトの別名]** は内部サーバー名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-293">If the NDES server uses both an external and internal name for a single network address, the server authentication certificate must have a **Subject Name** with an external public server name, and a **Subject Alternative Name** that includes the internal server name.</span></span>

2.  <span data-ttu-id="572c1-294">NDES サーバーで、内部 CA またはパブリック CA に **クライアント認証** 証明書を要求してインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-294">On your NDES Server, request and install a **client authentication** certificate from your internal CA, or a public certificate authority.</span></span> <span data-ttu-id="572c1-295">証明書に両方の機能がある場合、これはサーバー認証証明書と同じ証明書でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="572c1-295">This can be the same certificate as the server authentication certificate if that certificate has both capabilities.</span></span>

    <span data-ttu-id="572c1-296">クライアント認証証明書には次のプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="572c1-296">The client authentication certificate must have the following properties:</span></span>

    <span data-ttu-id="572c1-297">**[拡張キー使用法]** - **[クライアント認証]** を含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-297">**Enhanced Key Usage** - This must include **Client Authentication**.</span></span>

    <span data-ttu-id="572c1-298">**[サブジェクト名]** - 証明書をインストールするサーバー (NDES サーバー) の DNS 名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-298">**Subject Name** - This must be equal to the DNS name of the server where you are installing the certificate (the NDES Server).</span></span>

##### <a name="to-configure-iis-request-filtering"></a><span data-ttu-id="572c1-299">IIS 要求フィルタリングを構成するには</span><span class="sxs-lookup"><span data-stu-id="572c1-299">To configure IIS request filtering</span></span>

1.  <span data-ttu-id="572c1-300">NDES サーバーで **IIS マネージャー**を開き、**[接続]** ウィンドウの **[既定の Web サイト]** を選択し、**[要求のフィルタリング]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="572c1-300">On the NDES Server open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then open **Request Filtering**.</span></span>

2.  <span data-ttu-id="572c1-301">**[機能設定の編集]** をクリックし、次のように値を設定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-301">Click **Edit Feature Settings**, and then set the  values:</span></span>

    <span data-ttu-id="572c1-302">**[クエリ文字列の最大長 (バイト)]** = **65534**</span><span class="sxs-lookup"><span data-stu-id="572c1-302">**query string (Bytes)** = **65534**</span></span>

    <span data-ttu-id="572c1-303">**URL の最大長 (バイト)** = **65534**</span><span class="sxs-lookup"><span data-stu-id="572c1-303">**Maximum URL length (Bytes)** = **65534**</span></span>

3.  <span data-ttu-id="572c1-304">次のレジストリ キーを確認します。</span><span class="sxs-lookup"><span data-stu-id="572c1-304">Review the following registry key:</span></span>

    <span data-ttu-id="572c1-305">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**</span><span class="sxs-lookup"><span data-stu-id="572c1-305">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**</span></span>

    <span data-ttu-id="572c1-306">次の値が DWORD エントリとして設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="572c1-306">Ensure the following values are set as DWORD entries:</span></span>

    <span data-ttu-id="572c1-307">名前: **MaxFieldLength**、10 進数値 **65534**</span><span class="sxs-lookup"><span data-stu-id="572c1-307">Name: **MaxFieldLength**, with a decimal value of **65534**</span></span>

    <span data-ttu-id="572c1-308">名前: **MaxRequestBytes**、10 進数値 **65534**</span><span class="sxs-lookup"><span data-stu-id="572c1-308">Name: **MaxRequestBytes**, with a decimal value of **65534**</span></span>

4. <span data-ttu-id="572c1-309">NDES サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="572c1-309">Reboot the NDES server.</span></span> <span data-ttu-id="572c1-310">サーバーは証明書コネクタをサポートする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="572c1-310">The server is now ready to support the Certificate Connector.</span></span>

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a><span data-ttu-id="572c1-311">手順 5 - Intune Certificate Connector を有効にし、インストールし、構成する</span><span class="sxs-lookup"><span data-stu-id="572c1-311">Step 5 - Enable, install, and configure the Intune certificate connector</span></span>
<span data-ttu-id="572c1-312">このタスクでは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="572c1-312">In this task you:</span></span>

- <span data-ttu-id="572c1-313">Intune で NDES のサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="572c1-313">Enable support for NDES in Intune.</span></span>
- <span data-ttu-id="572c1-314">自分の環境のサーバーで証明書コネクタをダウンロードし、インストールして、構成します。</span><span class="sxs-lookup"><span data-stu-id="572c1-314">Download, install, and configure the Certificate Connector on a server in your environment.</span></span> <span data-ttu-id="572c1-315">高可用性をサポートするために、さまざまなサーバーに複数の証明書コネクタをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="572c1-315">To support high availability, you can install multiple Certificate Connectors on different servers.</span></span>

##### <a name="to-download-install-and-configure-the-certificate-connector"></a><span data-ttu-id="572c1-316">証明書コネクタをダウンロードし、インストールして、構成するには</span><span class="sxs-lookup"><span data-stu-id="572c1-316">To download, install, and configure the certificate connector</span></span>
![ConnectorDownload](./media/certificates-download-connector.png)   
 
1. <span data-ttu-id="572c1-318">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="572c1-318">Sign into the Azure portal.</span></span> 
2. <span data-ttu-id="572c1-319">**[その他のサービス]**  >  **[監視 + 管理]**  >  **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-319">Select **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="572c1-320">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-320">On the **Intune** blade, select **Device Configuration**.</span></span>
4. <span data-ttu-id="572c1-321">**[デバイス構成]** ブレードで **[証明機関]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-321">On the **Device Configuration** blade, select **Certification Authority**.</span></span>
5. <span data-ttu-id="572c1-322">**[追加]** をクリックして、**[Download Connector file]\(コネクタ ファイルのダウンロード\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-322">Click **Add** and select **Download Connector file**.</span></span> <span data-ttu-id="572c1-323">インストールするサーバーからアクセスできる場所にダウンロードしたものを保存します。</span><span class="sxs-lookup"><span data-stu-id="572c1-323">Save the download to a location where you can access it from the server where you are going to install it.</span></span> 
6.  <span data-ttu-id="572c1-324">ダウンロードが完了したら、ダウンロードしたインストーラー (**ndesconnectorssetup.exe**) を Windows Server 2012 R2 サーバーで実行します。</span><span class="sxs-lookup"><span data-stu-id="572c1-324">After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**) on a Windows Server 2012 R2 server.</span></span> <span data-ttu-id="572c1-325">インストーラーは、NDES のポリシー モジュールと CRP Web サービスもインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-325">The installer also installs the policy module for NDES and the CRP Web Service.</span></span> <span data-ttu-id="572c1-326">(CRP Web サービス CertificateRegistrationSvc は IIS のアプリケーションとして実行されます)。</span><span class="sxs-lookup"><span data-stu-id="572c1-326">(The CRP Web Service, CertificateRegistrationSvc, runs as an application in IIS.)</span></span>

    > [!NOTE]
    > <span data-ttu-id="572c1-327">スタンドアロン Intune の NDES をインストールする場合、CRP サービスは証明書コネクタと共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="572c1-327">When you install NDES for standalone Intune, the CRP service automatically installs with the Certificate Connector.</span></span> <span data-ttu-id="572c1-328">構成マネージャーで Intune を使用する場合は、証明書登録ポイントを別のサイト システムの役割としてインストールします。</span><span class="sxs-lookup"><span data-stu-id="572c1-328">When you use Intune with Configuration Manager, you install the Certificate Registration Point as a separate site system role.</span></span>

3.  <span data-ttu-id="572c1-329">証明書コネクタのクライアント証明書の入力を求められたら、**[選択]** を選択し、タスク 3 で NDES サーバーにインストールした**クライアント認証**証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-329">When prompted for the client certificate for the Certificate Connector, choose **Select**, and select the **client authentication** certificate you installed on your NDES Server in Task 3.</span></span>

    <span data-ttu-id="572c1-330">クライアント認証証明書を選択した後、**[Microsoft Intune 証明書コネクタのクライアント証明書]** 画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="572c1-330">After you select the client authentication certificate, you are returned to the **Client Certificate for Microsoft Intune Certificate Connector** surface.</span></span> <span data-ttu-id="572c1-331">選択した証明書は表示されませんが、**[次へ]** をクリックしてその証明書のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="572c1-331">Although the certificate you selected is not shown, click **Next** to view the properties of that certificate.</span></span> <span data-ttu-id="572c1-332">次に、**[次へ]** をクリックし、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572c1-332">Then click **Next**, and then click **Install**.</span></span>

4.  <span data-ttu-id="572c1-333">ウィザードが完了した後、ウィザードを閉じる前に、**[証明書コネクタの UI を起動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572c1-333">After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.</span></span>

    > [!TIP]
    > <span data-ttu-id="572c1-334">証明書コネクタの UI を起動する前にウィザードを閉じた場合は、次のコマンドを実行して再び開くことができます。</span><span class="sxs-lookup"><span data-stu-id="572c1-334">If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:</span></span>
    >
    > <span data-ttu-id="572c1-335">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span><span class="sxs-lookup"><span data-stu-id="572c1-335">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span></span>

5.  <span data-ttu-id="572c1-336">**証明書コネクタ** UI で:</span><span class="sxs-lookup"><span data-stu-id="572c1-336">In the **Certificate Connector** UI:</span></span>

    <span data-ttu-id="572c1-337">**[サインイン]** をクリックし、Intune サービス管理者の資格情報、またはグローバル管理アクセス許可を持つテナント管理者の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="572c1-337">Click **Sign In** and enter your Intune service administrator credentials, or credentials for a tenant administrator with the global administration permission.</span></span>

    <span data-ttu-id="572c1-338">組織でプロキシ サーバーを使用していて、NDES サーバーがインターネットにアクセスするためにプロキシが必要な場合は、**[プロキシ サーバーを使用する]** をクリックし、接続するためのプロキシ サーバーの名前、ポート、およびアカウント資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-338">If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.</span></span>

    <span data-ttu-id="572c1-339">**[詳細設定]** タブを選択し、発行元 CA で **証明書の発行と管理** アクセス許可を持つアカウントの資格情報を指定して、**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572c1-339">Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority, and then click **Apply**.</span></span>

    <span data-ttu-id="572c1-340">これで、証明書コネクタ UI を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="572c1-340">You can now close the Certificate Connector UI.</span></span>

6.  <span data-ttu-id="572c1-341">コマンド プロンプトを開き、「**services.msc**」と入力して **Enter** キーを押し、**Intune Connector Service** を右クリックして **[再起動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572c1-341">Open a command prompt and type **services.msc**, and then press **Enter**, right-click the **Intune Connector Service**, and then click **Restart**.</span></span>

<span data-ttu-id="572c1-342">サービスが実行していることを確認するには、ブラウザーを開き、次の URL を入力します。 **403** エラーが返る必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-342">To validate that the service is running, open a browser and enter the following URL, which should return a **403** error:</span></span>

<span data-ttu-id="572c1-343">**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**</span><span class="sxs-lookup"><span data-stu-id="572c1-343">**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**</span></span>

## <a name="how-to-create-a-scep-certificate-profile"></a><span data-ttu-id="572c1-344">SCEP 証明書プロファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="572c1-344">How to create a SCEP certificate profile</span></span>

1. <span data-ttu-id="572c1-345">Azure Portal で、**[デバイスの構成]** ワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-345">In the Azure portal, select the **Configure devices** workload.</span></span>
2. <span data-ttu-id="572c1-346">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-346">On the **Device Configuration** blade, select **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="572c1-347">[プロファイル] ブレードで、**[プロファイルの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-347">On the profiles blade, select **Create Profile**.</span></span>
4. <span data-ttu-id="572c1-348">**[プロファイルを作成します]** ブレードで、SCEP 証明書プロファイルの**名前**と**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="572c1-348">On the **Create Profile** blade, enter a **Name** and **Description** for the SCEP certificate profile.</span></span>
5. <span data-ttu-id="572c1-349">**[プラットフォーム]** ドロップダウン リストで、この SCEP 証明書のデバイス プラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-349">From the **Platform** drop-down list, select the device platform for this SCEP certificate.</span></span> <span data-ttu-id="572c1-350">現時点では、デバイスの制限設定に対応している次のいずれかのプラットフォームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-350">Currently, you can select one of the following platforms for device restriction settings:</span></span>
    - <span data-ttu-id="572c1-351">**Android**</span><span class="sxs-lookup"><span data-stu-id="572c1-351">**Android**</span></span>
    - <span data-ttu-id="572c1-352">**iOS**</span><span class="sxs-lookup"><span data-stu-id="572c1-352">**iOS**</span></span>
    - <span data-ttu-id="572c1-353">**macOS**</span><span class="sxs-lookup"><span data-stu-id="572c1-353">**macOS**</span></span>
    - <span data-ttu-id="572c1-354">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="572c1-354">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="572c1-355">**Windows 8.1 以降**</span><span class="sxs-lookup"><span data-stu-id="572c1-355">**Windows 8.1 and later**</span></span>
    - <span data-ttu-id="572c1-356">**Windows 10 以降**</span><span class="sxs-lookup"><span data-stu-id="572c1-356">**Windows 10 and later**</span></span>
6. <span data-ttu-id="572c1-357">**[プロファイルの種類]** ドロップダウン リストで、**[SCEP 証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-357">From the **Profile** type drop-down list, select **SCEP certificate**.</span></span>
7. <span data-ttu-id="572c1-358">**[SCEP 証明書]** ブレードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="572c1-358">On the **SCEP Certificate** blade, configure the following settings:</span></span>
    - <span data-ttu-id="572c1-359">**[証明書の有効期間]** - 発行元 CA で **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** コマンドを実行してカスタム有効期間を設定できるようにした場合は、証明書が失効するまでの期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-359">**Certificate validity period** - If you have run the **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** command on the issuing CA, which allows a custom validity period, you can specify the amount of remaining time before the certificate expires.</span></span><br><span data-ttu-id="572c1-360">指定した証明書テンプレートの有効期限よりも小さい値を指定できますが、大きい値は指定できません。</span><span class="sxs-lookup"><span data-stu-id="572c1-360">You can specify a value that is lower than the validity period in the specified certificate template, but not higher.</span></span> <span data-ttu-id="572c1-361">たとえば、証明書テンプレートで証明書の有効期限が 2 年になっている場合は、この値を 1 年することはできますが、5 年にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="572c1-361">For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years.</span></span> <span data-ttu-id="572c1-362">また、発行元の CA の証明書の残りの有効期限よりも小さい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-362">The value must also be lower than the remaining validity period of the issuing CA's certificate.</span></span> 
    - <span data-ttu-id="572c1-363">**[キー格納プロバイダー (KSP)]** (Windows Phone 8.1、Windows 8.1、Windows 10) - 証明書のキーを格納する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-363">**Key storage provider (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) - Specify where the key to the certificate is stored.</span></span> <span data-ttu-id="572c1-364">次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-364">Choose from one of the following values:</span></span>
        - <span data-ttu-id="572c1-365">**トラステッド プラットフォーム モジュール (TPM) KSP が存在する場合は TPM KSP に登録する (それ以外はソフトウェア KSP に登録する)**</span><span class="sxs-lookup"><span data-stu-id="572c1-365">**Enroll to Trusted Platform Module (TPM) KSP if present, otherwise Software KSP**</span></span>
        - <span data-ttu-id="572c1-366">**トラステッド プラットフォーム モジュール (TPM) KSP に登録する (それ以外は失敗)**</span><span class="sxs-lookup"><span data-stu-id="572c1-366">**Enroll to Trusted Platform Module (TPM) KSP, otherwise fail**</span></span>
        - <span data-ttu-id="572c1-367">**Passport に登録する、それ以外は失敗 (Windows 10 以降)**</span><span class="sxs-lookup"><span data-stu-id="572c1-367">**Enroll to Passport, otherwise fail (Windows 10 and later)**</span></span>
        - <span data-ttu-id="572c1-368">**ソフトウェア KSP に登録する**</span><span class="sxs-lookup"><span data-stu-id="572c1-368">**Enroll to Software KSP**</span></span>
    - <span data-ttu-id="572c1-369">**[サブジェクト名の形式]** - 一覧から、Intune が証明書要求のサブジェクト名をどのように自動生成するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-369">**Subject name format** - From the list, select how Intune automatically creates the subject name in the certificate request.</span></span> <span data-ttu-id="572c1-370">証明書がユーザー用の場合、サブジェクト名にユーザーのメール アドレスを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="572c1-370">If the certificate is for a user, you can also include the user's email address in the subject name.</span></span> <span data-ttu-id="572c1-371">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-371">Choose from:</span></span>
        - <span data-ttu-id="572c1-372">**未構成**</span><span class="sxs-lookup"><span data-stu-id="572c1-372">**Not configured**</span></span>
        - <span data-ttu-id="572c1-373">**共通名**</span><span class="sxs-lookup"><span data-stu-id="572c1-373">**Common name**</span></span>
        - <span data-ttu-id="572c1-374">**電子メールを含む共通名**</span><span class="sxs-lookup"><span data-stu-id="572c1-374">**Common name including email**</span></span>
        - <span data-ttu-id="572c1-375">**電子メールとしての共通名**</span><span class="sxs-lookup"><span data-stu-id="572c1-375">**Common name as email**</span></span>
        - <span data-ttu-id="572c1-376">**IMEI (International Mobile Equipment Identity)**</span><span class="sxs-lookup"><span data-stu-id="572c1-376">**IMEI (International Mobile Equipment Identity)**</span></span>
        - <span data-ttu-id="572c1-377">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="572c1-377">**Serial number**</span></span>
        - <span data-ttu-id="572c1-378">**カスタム**- このオプションを選択すると、別のドロップダウン フィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="572c1-378">**Custom** - When you select this option, another drop-down field is displayed.</span></span> <span data-ttu-id="572c1-379">このフィールドを使用して、カスタムのサブジェクト名の形式を入力します。</span><span class="sxs-lookup"><span data-stu-id="572c1-379">You use this field to enter a custom subject name format.</span></span> <span data-ttu-id="572c1-380">カスタム形式でサポートされている 2 つの変数は、**共通名 (CN)** と**電子メール (E)** です。</span><span class="sxs-lookup"><span data-stu-id="572c1-380">The two variables supported for the custom format are **Common Name (CN)** and **Email (E)**.</span></span> <span data-ttu-id="572c1-381">これらの変数と静的文字列の 1 つ以上の組み合わせを使用することで、**CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** のようなカスタムのサブジェクト名の形式を作成できます。この例では、CN と E 変数に加えて、組織単位、組織、市区町村、州、および国の値の文字列を使用してサブジェクト名形式を作成しています。</span><span class="sxs-lookup"><span data-stu-id="572c1-381">By using a combination of one or many of these variables and static strings, you can create a custom subject name format, like this one: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** In this example, you created a subject name format that, in addition to the CN and E variables, uses strings for Organizational Unit, Organization, Location, State, and Country values.</span></span> <span data-ttu-id="572c1-382">[このトピック](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx)では、**CertStrToName** 関数とこの関数でサポートされる文字列について説明しています。</span><span class="sxs-lookup"><span data-stu-id="572c1-382">[This topic](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) shows the **CertStrToName** function and its supported strings.</span></span>
        
    - <span data-ttu-id="572c1-383">**[サブジェクトの別名]** - Intune が証明書要求のサブジェクトの別名 (SAN) をどのように自動生成するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-383">**Subject alternative name** - Specify how Intune automatically creates the values for the subject alternative name (SAN) in the certificate request.</span></span> <span data-ttu-id="572c1-384">たとえば、ユーザー証明書の種類を選択した場合は、サブジェクトの別名にユーザー プリンシパル名 (UPN) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="572c1-384">For example, if you selected a user certificate type, you can include the user principal name (UPN) in the subject alternative name.</span></span> <span data-ttu-id="572c1-385">クライアント証明書を Windows ポリシー サーバーでの認証に使用する場合は、サブジェクトの別名を UPN に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-385">If the client certificate is used to authenticate to a Network Policy Server, you must set the subject alternative name to the UPN.</span></span> 
    - <span data-ttu-id="572c1-386">**[キー使用法]** - 証明書のキー使用法のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-386">**Key usage** - Specify key usage options for the certificate.</span></span> <span data-ttu-id="572c1-387">次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-387">You can choose from the following options:</span></span> 
        - <span data-ttu-id="572c1-388">**キーの暗号化:** キーが暗号化されている場合だけキーを交換できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-388">**Key encipherment:** Allow key exchange only when the key is encrypted.</span></span> 
        - <span data-ttu-id="572c1-389">**デジタル署名:** キーがデジタル署名で保護されている場合だけ、キーを交換できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-389">**Digital signature:** Allow key exchange only when a digital signature helps protect the key.</span></span> 
    - <span data-ttu-id="572c1-390">**[キー サイズ (ビット)]** - キーに含まれるビット数を選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-390">**Key size (bits)** - Select the number of bits that is contained in the key.</span></span> 
    - <span data-ttu-id="572c1-391">**[ハッシュ アルゴリズム]** (Android、Windows Phone 8.1、Windows 8.1、Windows 10) - この証明書で使用するハッシュ アルゴリズムの種類を 1 つ選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-391">**Hash algorithm** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) - Select one of the available hash algorithm types to use with this certificate.</span></span> <span data-ttu-id="572c1-392">接続しているデバイスをサポートするセキュリティの最も強力なレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-392">Select the strongest level of security that the connecting devices support.</span></span> 
    - <span data-ttu-id="572c1-393">**[ルート証明書]** - 既に構成してユーザーまたはデバイスに割り当てているルート CA 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="572c1-393">**Root Certificate** - Choose a root CA certificate profile that you have previously configured and assigned to the user or device.</span></span> <span data-ttu-id="572c1-394">この CA 証明書は、この証明書プロファイルで構成している証明書を発行する CA のルート証明書である必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-394">This CA certificate must be the root certificate for the CA that issues the certificate that you are configuring in this certificate profile.</span></span> 
    - <span data-ttu-id="572c1-395">**[拡張キー使用法]** - **[追加]** を選択して、証明書の使用目的に対応する値を追加します。</span><span class="sxs-lookup"><span data-stu-id="572c1-395">**Extended key usage** - Select **Add** to add values for the certificate's intended purpose.</span></span> <span data-ttu-id="572c1-396">ほとんどの場合、ユーザーまたはデバイスがサーバーに対して認証できるように、証明書には **[クライアント認証]** が必要です。</span><span class="sxs-lookup"><span data-stu-id="572c1-396">In most cases, the certificate requires **Client Authentication** so that the user or device can authenticate to a server.</span></span> <span data-ttu-id="572c1-397">ただし、必要に応じてその他のキー使用法を追加できます。</span><span class="sxs-lookup"><span data-stu-id="572c1-397">However, you can add any other key usages as required.</span></span> 
    - <span data-ttu-id="572c1-398">**登録設定**</span><span class="sxs-lookup"><span data-stu-id="572c1-398">**Enrollment Settings**</span></span>
        - <span data-ttu-id="572c1-399">**[更新しきい値 (%)]** - 証明書の有効期間の残りがどの程度 (%) になったら、デバイスが更新を要求するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-399">**Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.</span></span>
        - <span data-ttu-id="572c1-400">**[SCEP サーバーの URL]** - SCEP 経由で証明書を発行する NDES サーバーの URL を 1 つまたは複数指定します。</span><span class="sxs-lookup"><span data-stu-id="572c1-400">**SCEP Server URLs** - Specify one or more URLs for the NDES Servers that issues certificates via SCEP.</span></span> 
8. <span data-ttu-id="572c1-401">完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572c1-401">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="572c1-402">プロファイルが作成され、プロファイルの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="572c1-402">The profile is created and appears on the profiles list blade.</span></span>

## <a name="how-to-assign-the-certificate-profile"></a><span data-ttu-id="572c1-403">証明書プロファイルを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="572c1-403">How to assign the certificate profile</span></span>

<span data-ttu-id="572c1-404">証明書プロファイルをグループに割り当てる前に、次の点を考慮します。</span><span class="sxs-lookup"><span data-stu-id="572c1-404">Consider the following before you assign certificate profiles to groups:</span></span>

- <span data-ttu-id="572c1-405">証明書プロファイルをグループに割り当てるときに、信頼された CA 証明書プロファイルの証明書ファイルは、デバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="572c1-405">When you assign certificate profiles to groups, the certificate file from the Trusted CA certificate profile is installed on the device.</span></span> <span data-ttu-id="572c1-406">デバイスは、SCEP 証明書プロファイルを使用してデバイスによる証明書要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="572c1-406">The device uses the SCEP certificate profile to create a certificate request by the device.</span></span>
- <span data-ttu-id="572c1-407">証明書プロファイルは、プロファイルを作成するときに使用するプラットフォームを実行しているデバイスのみにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="572c1-407">Certificate profiles install only on devices running the platform you use when you created the profile.</span></span>
- <span data-ttu-id="572c1-408">ユーザー コレクションまたはデバイス コレクションに証明書プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="572c1-408">You can assign certificate profiles to user collections or to device collections.</span></span>
- <span data-ttu-id="572c1-409">デバイス登録後すぐに証明書をデバイスに公開するには、証明書プロファイルをデバイス グループではなくユーザー グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="572c1-409">To publish a certificate to a device quickly after the device enrolls, assign the certificate profile to a user group rather than to a device group.</span></span> <span data-ttu-id="572c1-410">デバイス グループに割り当てた場合は、デバイスがポリシーを受け取る前に、デバイスの登録を完全に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="572c1-410">If you assign to a device group, a full device registration is required before the device receives policies.</span></span>
- <span data-ttu-id="572c1-411">各プロファイルは個別に割り当てますが、信頼されたルート CA と、SCEP または PKCS プロファイルを割り当てる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="572c1-411">Although you assign each profile separately, you also need to assign the Trusted Root CA and the SCEP or PKCS profile.</span></span> <span data-ttu-id="572c1-412">そうしないと、SCEP または PKCS 証明書ポリシーは失敗します。</span><span class="sxs-lookup"><span data-stu-id="572c1-412">Otherwise, the SCEP or PKCS certificate policy fails.</span></span>

<span data-ttu-id="572c1-413">プロファイルを割り当てる方法については、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="572c1-413">For information about how to assign profiles, see [How to assign device profiles](device-profile-assign.md).</span></span>

