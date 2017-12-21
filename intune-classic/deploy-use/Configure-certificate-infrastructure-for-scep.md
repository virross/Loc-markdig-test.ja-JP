---
title: "SCEP の証明書インフラストラクチャを構成する"
description: "SCEP 証明書プロファイルを作成および展開するためのインフラストラクチャ。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ae137ae-34e5-4a45-950c-983de831270f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 76b57636b446f7ec4e00c52511df3722a15618a3
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="configure-certificate-infrastructure-for-scep"></a><span data-ttu-id="e5b2f-103">SCEP の証明書インフラストラクチャを構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-103">Configure certificate infrastructure for SCEP</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e5b2f-104">このトピックでは、SCEP 証明書プロファイルを作成して展開するために必要なインフラストラクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-104">This topic describes what infrastructure you need in order to create and deploy SCEP certificate profiles.</span></span>

### <a name="on-premises-infrastructure"></a><span data-ttu-id="e5b2f-105">内部設置型インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="e5b2f-105">On-premises infrastructure</span></span>

-    <span data-ttu-id="e5b2f-106">**Active Directory ドメイン**: このセクションで示されているすべてのサーバー (Web アプリケーション プロキシ サーバーを除く) は、Active Directory ドメインに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-106">**Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.</span></span>

-  <span data-ttu-id="e5b2f-107">**証明機関** (CA): Windows Server 2008 R2 以降の Enterprise エディションで実行するエンタープライズ証明機関 (CA) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-107">**Certification Authority** (CA): An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="e5b2f-108">スタンドアロン CA はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-108">A Standalone CA is not supported.</span></span> <span data-ttu-id="e5b2f-109">証明機関をセットアップする方法の詳細については、 [証明機関のインストールに関するページ](http://technet.microsoft.com/library/jj125375.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-109">For instructions on how to set up a Certification Authority, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).</span></span>
    <span data-ttu-id="e5b2f-110">CA が Windows Server 2008 R2 を搭載している場合は、 [KB2483564 の修正プログラムをインストール](http://support.microsoft.com/kb/2483564/)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-110">If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).</span></span>
<span data-ttu-id="e5b2f-111">I</span><span class="sxs-lookup"><span data-stu-id="e5b2f-111">I</span></span>
-  <span data-ttu-id="e5b2f-112">**NDES サーバー**: Windows Server 2012 R2 以降を実行しているサーバーに、ネットワーク デバイス登録サービス (NDES) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-112">**NDES Server**: On a server that runs Windows Server 2012 R2 or later, you must set up the Network Device Enrollment Service (NDES).</span></span> <span data-ttu-id="e5b2f-113">エンタープライズ CA も実行しているサーバーで Intune を実行する場合には、ネットワーク デバイス登録サービスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-113">Intune does not support using NDES when it runs on a server that also runs the Enterprise CA.</span></span> <span data-ttu-id="e5b2f-114">ネットワーク デバイス登録サービスをホストするための Windows Server 2012 R2 の構成方法については、「[ネットワーク デバイス登録サービスのガイダンス](http://technet.microsoft.com/library/hh831498.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-114">See [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) for instructions on how to configure Windows Server 2012 R2 to host the Network Device Enrollment Service.</span></span> <span data-ttu-id="e5b2f-115">NDES サーバーは、CA をホストしているドメインに参加する必要があります。CA と同じサーバーに置くことはできません。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-115">The NDES server must be domain joined to the domain that hosts the CA, and not be on the same server as the CA.</span></span> <span data-ttu-id="e5b2f-116">別個のフォレスト、分離ネットワーク、内部ドメインで NDES サーバーを展開する方法については、「[ポリシー モジュールとネットワーク デバイス登録サービスの使用](https://technet.microsoft.com/library/dn473016.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-116">More information about deploying the NDES server in a separate forest, isolated network or internal domain can be found in [Using a Policy Module with the Network Device Enrollment Service](https://technet.microsoft.com/library/dn473016.aspx).</span></span>

-  <span data-ttu-id="e5b2f-117">**Microsoft Intune 証明書コネクタ**: Intune 管理コンソールを使用して**証明書コネクタ** インストーラー (**ndesconnectorssetup.exe**) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-117">**Microsoft Intune Certificate Connector**: You use the Intune admin console to download the **Certificate Connector** installer (**ndesconnectorssetup.exe**).</span></span> <span data-ttu-id="e5b2f-118">これにより、証明書コネクタをインストールするコンピューターで **ndesconnectorssetup.exe** を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-118">Then you can run **ndesconnectorssetup.exe** on the computer where you want to install the Certificate Connector.</span></span>
-  <span data-ttu-id="e5b2f-119">**Web アプリケーション プロキシ サーバー** (省略可能): Web アプリケーション プロキシ (WAP) サーバーとして Windows Server 2012 R2 以降を実行しているサーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-119">**Web Application Proxy Server** (optional): You can use a server that runs Windows Server 2012 R2  or later as a Web Application Proxy (WAP) server.</span></span> <span data-ttu-id="e5b2f-120">この構成は:</span><span class="sxs-lookup"><span data-stu-id="e5b2f-120">This configuration:</span></span>
    -  <span data-ttu-id="e5b2f-121">デバイスはインターネット接続を使用して証明書を受信できます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-121">Allows devices to receive certificates using an Internet connection.</span></span>
    -  <span data-ttu-id="e5b2f-122">デバイスがインターネット接続経由で証明書を受信して更新する場合のセキュリティ推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-122">Is a security recommendation when devices connect through the Internet to receive and renew certificates.</span></span>

 > [!NOTE]           
> -    <span data-ttu-id="e5b2f-123">WAP をホストするサーバーは、ネットワーク デバイス登録サービスで使用される長い URL のサポートを有効にする [更新プログラムをインストールする](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-123">The server that hosts WAP [must install an update](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service.</span></span> <span data-ttu-id="e5b2f-124">この更新プログラムは、 [2014 年 12 月の更新プログラムのロールアップ](https://support.microsoft.com/kb/3013769)に含まれます。または、 [KB3011135](https://support.microsoft.com/kb/3011135)から個別に入手できます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-124">This update is included with the [December 2014 update rollup](https://support.microsoft.com/kb/3013769), or individually from [KB3011135](https://support.microsoft.com/kb/3011135).</span></span>
>-  <span data-ttu-id="e5b2f-125">また、WAP をホストするサーバーが、外部クライアントに公開される名前と一致する SSL 証明書を持ち、NDES サーバーで使用される SSL 証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-125">Also, the server that hosts WAP must have a SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server.</span></span> <span data-ttu-id="e5b2f-126">これらの証明書を使用すると、WAP サーバーはクライアントからの SSL 接続を終了し、NDES サーバーへの新しい SSL 接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-126">These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.</span></span>
    <span data-ttu-id="e5b2f-127">WAP の証明書については、「[内部アプリケーションの公開のために Web アプリケーション プロキシをインストールおよび構成する](https://technet.microsoft.com/library/dn383650.aspx)」の**証明書の計画**に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-127">For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx).</span></span> <span data-ttu-id="e5b2f-128">WAP サーバーの一般的な情報については、「[Web アプリケーション プロキシの使用](http://technet.microsoft.com/library/dn584113.aspx)」を参照してください。|</span><span class="sxs-lookup"><span data-stu-id="e5b2f-128">For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|</span></span>

### <a name="network-requirements"></a><span data-ttu-id="e5b2f-129">ネットワークの要件</span><span class="sxs-lookup"><span data-stu-id="e5b2f-129">Network requirements</span></span>

<span data-ttu-id="e5b2f-130">インターネットから境界ネットワークまでを範囲として、インターネット上のあらゆるホスト/IP アドレスから NDES サーバーへの送信にポート 443 を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-130">From the Internet to perimeter network, allow port 443 from all hosts/IP addresses on the internet to the NDES server.</span></span>

<span data-ttu-id="e5b2f-131">境界ネットワークから信頼されたネットワークまでを範囲として、ドメイン参加 NDES サーバーのドメイン アクセスに必要なすべてのポートとプロトコルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-131">From the perimeter network to trusted network, allow all ports and protocols needed for domain access on the domain-joined NDES server.</span></span> <span data-ttu-id="e5b2f-132">NDES サーバーは、証明書サーバー、DNS サーバー、構成マネージャー サーバー、ドメイン コントローラーへのアクセス許可を必要とします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-132">The NDES server needs access to the certificate servers, DNS servers, Configuration Manager servers and domain controllers.</span></span>

<span data-ttu-id="e5b2f-133">NDES サーバーは、[Azure AD アプリケーション プロキシ](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/)、[Web アクセス プロキシ](https://technet.microsoft.com/library/dn584107.aspx)、サード パーティ製のプロキシなどのプロキシを通じて公開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-133">We recommend publishing the NDES server through a proxy, such as the [Azure AD application proxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx), or a third-party proxy.</span></span>


### <a name="BKMK_CertsAndTemplates"></a><span data-ttu-id="e5b2f-134">証明書とテンプレート</span><span class="sxs-lookup"><span data-stu-id="e5b2f-134">Certificates and Templates</span></span>

|<span data-ttu-id="e5b2f-135">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e5b2f-135">Object</span></span>|<span data-ttu-id="e5b2f-136">説明</span><span class="sxs-lookup"><span data-stu-id="e5b2f-136">Details</span></span>|
|----------|-----------|
|<span data-ttu-id="e5b2f-137">**証明書テンプレート**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-137">**Certificate Template**</span></span>|<span data-ttu-id="e5b2f-138">発行元 CA でこのテンプレートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-138">You configure this template on your issuing CA.</span></span>|
|<span data-ttu-id="e5b2f-139">**クライアント認証証明書**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-139">**Client authentication certificate**</span></span>|<span data-ttu-id="e5b2f-140">発行元 CA またはパブリック CA から要求されます。この証明書を NDES サーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-140">Requested from your issuing CA or public CA, you install this certificate on the NDES Server.</span></span>|
|<span data-ttu-id="e5b2f-141">**サーバー認証証明書**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-141">**Server authentication certificate**</span></span>|<span data-ttu-id="e5b2f-142">発行元 CA またはパブリック CA から要求されます。この SSL 証明書をインストールし NDES サーバーの IIS にバインドします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-142">Requested from your issuing CA or public CA, you install and bind this SSL certificate in IIS on the NDES server.</span></span>|
|<span data-ttu-id="e5b2f-143">**信頼されたルート CA 証明書**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-143">**Trusted Root CA certificate**</span></span>|<span data-ttu-id="e5b2f-144">これをルート CA またはルート CA を信頼するデバイスから **.cer** ファイルとしてエクスポートし、信頼された CA 証明書プロファイルを使用してデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-144">You export this as a **.cer** file from the root CA or any device which trusts the root CA, and deploy it to devices by using the Trusted CA certificate profile.</span></span><br /><br /><span data-ttu-id="e5b2f-145">オペレーティング システムのプラットフォームごとに 1 つの信頼されたルート CA 証明書を使用し、作成する各信頼されたルート証明書プロファイルに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-145">You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.</span></span><br /><br /><span data-ttu-id="e5b2f-146">必要に応じて、信頼されたルート CA 証明書を追加して使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-146">You can use additional Trusted Root CA certificates when needed.</span></span> <span data-ttu-id="e5b2f-147">ルート CA 証明書を追加する局面としては、Wi-Fi アクセス ポイント用のサーバー認証証明書に署名する CA の信頼性を担保する必要がある場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-147">For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.</span></span>|

### <a name="BKMK_Accounts"></a><span data-ttu-id="e5b2f-148">アカウント</span><span class="sxs-lookup"><span data-stu-id="e5b2f-148">Accounts</span></span>

|<span data-ttu-id="e5b2f-149">名前</span><span class="sxs-lookup"><span data-stu-id="e5b2f-149">Name</span></span>|<span data-ttu-id="e5b2f-150">説明</span><span class="sxs-lookup"><span data-stu-id="e5b2f-150">Details</span></span>|
|--------|-----------|
|<span data-ttu-id="e5b2f-151">**NDES サービス アカウント**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-151">**NDES service account**</span></span>|<span data-ttu-id="e5b2f-152">NDES サービス アカウントとして使用するドメイン ユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-152">You specify a domain user account to use as the NDES Service account.</span></span>|

## <a name="BKMK_ConfigureInfrastructure"></a><span data-ttu-id="e5b2f-153">インフラストラクチャを構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-153">Configure your infrastructure</span></span>
<span data-ttu-id="e5b2f-154">証明書プロファイルを構成する前に、次のタスクを行う必要があります。これには、Windows Server 2012 R2 および Active Directory 証明書サービス (ADCS) の知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-154">Before you can configure certificate profiles you must complete the following tasks, which require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):</span></span>

<span data-ttu-id="e5b2f-155">**タスク 1**: NDES サービス アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-155">**Task 1**: Create an NDES service account</span></span>

<span data-ttu-id="e5b2f-156">**タスク 2**: 証明機関で証明書テンプレートを構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-156">**Task 2**: Configure certificate templates on the certification authority</span></span>

<span data-ttu-id="e5b2f-157">**タスク 3**: NDES サーバーで前提条件を構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-157">**Task 3**: Configure prerequisites on the NDES server</span></span>

<span data-ttu-id="e5b2f-158">**タスク 4**: Intune で使用するための NDES を構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-158">**Task 4**: Configure NDES for use with Intune</span></span>

<span data-ttu-id="e5b2f-159">**タスク 5**: Intune 証明書コネクタを有効にし、インストールし、構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-159">**Task 5**: Enable, install, and configure the Intune Certificate Connector</span></span>

### <a name="task-1---create-an-ndes-service-account"></a><span data-ttu-id="e5b2f-160">タスク 1 - NDES サービス アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-160">Task 1 - Create an NDES service account</span></span>

<span data-ttu-id="e5b2f-161">NDES サービス アカウントとして使用するドメイン ユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-161">Create a domain user account to use as the NDES service account.</span></span> <span data-ttu-id="e5b2f-162">NDES をインストールして構成する前に、発行元 CA でテンプレートを構成するときに、このアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-162">You will specify this account when you configure templates on the issuing CA before you install and configure NDES.</span></span> <span data-ttu-id="e5b2f-163">ユーザーに既定の権限、**ローカル ログオン**の権限、**サービスとしてログオン**の権限、**バッチ ジョブとしてログオン**の権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-163">Make sure the user has the default rights, **Logon Localy**, **Logon as a Service** and **Logon as a batch job** rights.</span></span> <span data-ttu-id="e5b2f-164">ポリシーを強化し、これらの権限を無効にしている組織もあります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-164">Some organizations have hardening policies that disable those rights.</span></span>




### <a name="task-2---configure-certificate-templates-on-the-certification-authority"></a><span data-ttu-id="e5b2f-165">タスク 2 - 証明機関で証明書テンプレートを構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-165">Task 2 - Configure certificate templates on the certification authority</span></span>
<span data-ttu-id="e5b2f-166">このタスクでは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-166">In this task you will:</span></span>

-   <span data-ttu-id="e5b2f-167">NDES の証明書テンプレートを構成します</span><span class="sxs-lookup"><span data-stu-id="e5b2f-167">Configure a certificate template for NDES</span></span>

-   <span data-ttu-id="e5b2f-168">NDES に証明書テンプレートを発行します</span><span class="sxs-lookup"><span data-stu-id="e5b2f-168">Publish the certificate template for NDES</span></span>

##### <a name="to-configure-the-certification-authority"></a><span data-ttu-id="e5b2f-169">証明機関を構成するには</span><span class="sxs-lookup"><span data-stu-id="e5b2f-169">To configure the certification authority</span></span>

1.  <span data-ttu-id="e5b2f-170">エンタープライズ管理者としてログオンします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-170">Log on as an enterprise administrator.</span></span>

2.  <span data-ttu-id="e5b2f-171">発行元 CA で、証明書テンプレート スナップインを使用して、新しいカスタム テンプレートを作成するか、または既存のテンプレートをコピーして NDES で使用するために (ユーザー テンプレートのように) 既存のテンプレートを編集します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-171">On the issuing CA, use the Certificate Templates snap-in to create a new custom template or copy an existing template and then edit an existing template (like the User template), for use with NDES.</span></span>

    <span data-ttu-id="e5b2f-172">テンプレートには次の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-172">The template must have the following configurations:</span></span>

    -   <span data-ttu-id="e5b2f-173">テンプレートのわかりやすい **テンプレート表示名** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-173">Specify a friendly **Template display name** for the template.</span></span>

    -   <span data-ttu-id="e5b2f-174">**[サブジェクト名]** タブで **[要求に含まれる]** を選択します</span><span class="sxs-lookup"><span data-stu-id="e5b2f-174">On the **Subject Name** tab, select **Supply in the request**.</span></span> <span data-ttu-id="e5b2f-175">(セキュリティが NDES の Intune ポリシー モジュールによって適用されます)。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-175">(Security is enforced by the Intune policy module for NDES).</span></span>

    -   <span data-ttu-id="e5b2f-176">**[拡張]** タブで、**[アプリケーション ポリシーの説明]** に **[クライアント認証]** が含まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-176">On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="e5b2f-177">iOS および Mac OS X の証明書テンプレートの場合、**[拡張]** タブで、**[キー使用法]** を編集し、**[署名は発行元の証明である]** がオンになっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-177">For iOS and Mac OS X certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure **Signature is proof of origin** is not selected.</span></span>

    -   <span data-ttu-id="e5b2f-178">**[セキュリティ]** タブで、NDES サービス アカウントを追加し、テンプレートへの **[登録]** アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-178">On the **Security** tab, add the NDES service account, and give it **Enroll** permissions to the template.</span></span> <span data-ttu-id="e5b2f-179">SCEP プロファイルを作成する Intune 管理者は、SCEP プロファイルの作成時にテンプレートを閲覧できるように、**読み取り**権限を必要とします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-179">Intune admins who will create SCEP profiles require **Read** rights so that they can browse to the template when creating SCEP profiles.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e5b2f-180">証明書を失効させるには、証明書プロファイルで使用されている証明書テンプレートごとに*証明書の発行および管理*の権限が NDES サービス アカウントに必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-180">To revoke certificates the NDES service account needs *Issue and Manage Certificates* rights for each certificate template used by a certificate profile.</span></span>

3.  <span data-ttu-id="e5b2f-181">**[一般]** タブでテンプレートの **[有効期間]** を確認します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-181">Review the **Validity period** on the **General** tab of the template.</span></span> <span data-ttu-id="e5b2f-182">既定では、Intune はテンプレートで構成されている値を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-182">By default, Intune uses the value configured in the template.</span></span> <span data-ttu-id="e5b2f-183">ただし、要求元が異なる値を指定できるように CA を構成できます。異なる値は、Intune 管理者コンソールから設定できます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-183">However, you have the option to configure the CA to allow the requester to specify a different value, which you can then set from within the Intune Administrator console.</span></span> <span data-ttu-id="e5b2f-184">常にテンプレートの値を使用する場合は、この手順の残りの部分をスキップします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-184">If you want to always use the value in the template, skip the remainder of this step.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e5b2f-185">iOS および Mac OS X プラットフォームは、他の構成に関係なく、常にテンプレートで設定される値を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-185">The iOS and Mac OS X platforms always uses the value set in the template regardless of other configurations you make.</span></span>

<span data-ttu-id="e5b2f-186">次は、サンプル テンプレート構成のスクリーンショットです。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-186">Here are screenshots of an example template configuration.</span></span>

![テンプレート、[要求処理] タブ](..\media\scep_ndes_request_handling.png)

![テンプレート、[サブジェクト名] タブ](..\media\scep_ndes_subject_name.jpg)

![テンプレート、[セキュリティ] タブ](..\media\scep_ndes_security.jpg)

![テンプレート、[拡張] タブ](..\media\scep_ndes_extensions.jpg)

![テンプレート、[発行要件] タブ](..\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > <span data-ttu-id="e5b2f-192">アプリケーション ポリシー (4 番目のスクリーン ショット) の場合、必要なアプリケーション ポリシーのみを追加します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-192">For Application Policies (in the 4th screenshot), only add the application policies required.</span></span> <span data-ttu-id="e5b2f-193">セキュリティ管理者の選択を確定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-193">Confirm your choices with your security admins.</span></span>



<span data-ttu-id="e5b2f-194">要求元が有効期間を指定できるように CA を構成するには、CA で次のコマンド実行します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-194">To configure the CA to allow the requester to specify the validity period, on the CA run the following commands:</span></span>

   1.  <span data-ttu-id="e5b2f-195">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-195">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span></span>
   2.  <span data-ttu-id="e5b2f-196">**net stop certsvc**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-196">**net stop certsvc**</span></span>

   3.  <span data-ttu-id="e5b2f-197">**net start certsvc**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-197">**net start certsvc**</span></span>

4.  <span data-ttu-id="e5b2f-198">発行元 CA で、証明機関スナップインを使用して証明書テンプレートを発行します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-198">On the issuing CA, use the Certification Authority snap-in to publish the certificate template.</span></span>

    1.  <span data-ttu-id="e5b2f-199">**[証明書テンプレート]** ノードを選択し、**[アクション]** -&gt; **[新規]** &gt; **[発行する証明書テンプレート]** の順にクリックして、手順 2. で作成したテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-199">Select the **Certificate Templates** node, click **Action**-&gt; **New** &gt; **Certificate Template to Issue**, and then select the template you created in step 2.</span></span>

    2.  <span data-ttu-id="e5b2f-200">**[証明書テンプレート]** フォルダーに表示されることで、テンプレートが発行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-200">Validate that the template published by viewing it under the **Certificate Templates** folder.</span></span>


### <a name="task-3---configure-prerequisites-on-the-ndes-server"></a><span data-ttu-id="e5b2f-201">タスク 3 - NDES サーバーで前提条件を構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-201">Task 3 - Configure prerequisites on the NDES server</span></span>
<span data-ttu-id="e5b2f-202">このタスクでは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-202">In this task you will:</span></span>

-   <span data-ttu-id="e5b2f-203">Windows サーバーに NDES を追加し、NDES をサポートするように IIS を構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-203">Add NDES to a Windows Server and configure IIS to support NDES</span></span>

-   <span data-ttu-id="e5b2f-204">NDES サービス アカウントを IIS_IUSR グループに追加します</span><span class="sxs-lookup"><span data-stu-id="e5b2f-204">Add the NDES Service account to the IIS_IUSR group</span></span>

-   <span data-ttu-id="e5b2f-205">NDES サービス アカウントの SPN を設定します</span><span class="sxs-lookup"><span data-stu-id="e5b2f-205">Set the SPN for the NDES Service account</span></span>




   1.  <span data-ttu-id="e5b2f-206">NDES をホストするサーバーに **エンタープライズ管理者**としてログインし、 [役割と機能の追加ウィザード](https://technet.microsoft.com/library/hh831809.aspx) を使用して NDES をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-206">On the server that will hosts NDES, you must log on as a an **Enterprise Administrator**, and then use the [Add Roles and Features Wizard](https://technet.microsoft.com/library/hh831809.aspx) to install NDES:</span></span>

    1.  <span data-ttu-id="e5b2f-207">ウィザードで、**[Active Directory 証明書サービス]** を選択して AD CS 役割サービスにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-207">In the Wizard, select **Active Directory Certificate Services** to gain access to the AD CS Role Services.</span></span> <span data-ttu-id="e5b2f-208">**[ネットワーク デバイス登録サービス]** をオンにし、**[証明機関]** をオフにして、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-208">Select the **Network Device Enrollment Service**, uncheck **Certification Authority**, and then complete the wizard.</span></span>

        > [!TIP]
        > <span data-ttu-id="e5b2f-209">ウィザードの **[インストールの進行状況]** ページでは、**[閉じる]** をクリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-209">On the **Installation progress** page of the wizard, do not click **Close**.</span></span> <span data-ttu-id="e5b2f-210">代わりに、**[対象サーバーに Active Directory 証明書サービスを構成する]** のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-210">Instead, click the link for **Configure Active Directory Certificate Services on the destination server**.</span></span> <span data-ttu-id="e5b2f-211">これにより、次のタスクで使用する **[AD CS の構成]** ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-211">This opens the **AD CS Configuration** wizard that you use for the next task.</span></span> <span data-ttu-id="e5b2f-212">[AD CS の構成] が開いた後は、役割と機能の追加ウィザードを閉じてかまいません。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-212">After AD CS Configuration opens, you can close the Add Roles and Features wizard.</span></span>

    2.  <span data-ttu-id="e5b2f-213">NDES がサーバーに追加されるときに、ウィザードは IIS もインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-213">When NDES is added to the server, the wizard also installs IIS.</span></span> <span data-ttu-id="e5b2f-214">IIS が次の構成であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-214">Ensure IIS has the following configurations:</span></span>

        -   <span data-ttu-id="e5b2f-215">**[Web サーバー]** &gt; **[セキュリティ]** &gt; **[要求のフィルタリング]**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-215">**Web Server** &gt; **Security** &gt; **Request Filtering**</span></span>

        -   <span data-ttu-id="e5b2f-216">**[Web サーバー]** &gt; **[アプリケーション開発]** &gt; **[ASP.NET 3.5]**。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-216">**Web Server** &gt; **Application Development** &gt; **ASP.NET 3.5**.</span></span> <span data-ttu-id="e5b2f-217">ASP.NET 3.5 をインストールすると、.NET Framework 3.5 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-217">Installing ASP.NET 3.5 will install .NET Framework 3.5.</span></span> <span data-ttu-id="e5b2f-218">.NET Framework 3.5 をインストールするとき、**[.NET Framework 3.5]** のコア機能および **[HTTP アクティブ化]** の両方をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-218">When installing .NET Framework 3.5, install both the core **.NET Framework 3.5** feature and **HTTP Activation**.</span></span>

        -   <span data-ttu-id="e5b2f-219">**[Web サーバー]** &gt; **[アプリケーション開発]** &gt; **[ASP.NET 4.5]**。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-219">**Web Server** &gt; **Application Development** &gt; **ASP.NET 4.5**.</span></span> <span data-ttu-id="e5b2f-220">ASP.NET 4.5 をインストールすると、.NET Framework 4.5 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-220">Installing ASP.NET 4.5 will install .NET Framework 4.5.</span></span> <span data-ttu-id="e5b2f-221">.NET Framework 4.5 をインストールする際に、**[.NET Framework 4.5]** のコア機能、**[ASP.NET 4.5]**、および **[WCF サービス]** &gt; **[HTTP アクティブ化]** 機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-221">When installing .NET Framework 4.5, install the core **.NET Framework 4.5** feature, **ASP.NET 4.5**, and the **WCF Services** &gt; **HTTP Activation** feature.</span></span>

        -   <span data-ttu-id="e5b2f-222">**[管理ツール]** &gt; **[IIS 6 と互換性のある管理]** &gt; **[IIS 6 メタベース互換]**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-222">**Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 Metabase Compatibility**</span></span>

        -   <span data-ttu-id="e5b2f-223">**[管理ツール]** &gt; **[IIS 6 と互換性のある管理]** &gt; **[IIS 6 WMI 互換性]**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-223">**Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 WMI Compatibility**</span></span>

  2.  <span data-ttu-id="e5b2f-224">サーバーで、**IIS_IUSR** グループのメンバーとして NDES サービス アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-224">On the server, add the NDES service account as a member of the **IIS_IUSR** group.</span></span>

   3.  <span data-ttu-id="e5b2f-225">管理者特権のコマンド プロンプトで、次のコマンドを実行して、NDES サービス アカウントの SPN を設定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-225">In an elevated command prompt, run the following command to set the SPN of the NDES Service account:</span></span>

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   <span data-ttu-id="e5b2f-226">たとえば、NDES サーバーの名前が **Server01**、ドメインが **Contoso.com**、サービス アカウントが **NDESService**の場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-226">For example, if your NDES Server is named **Server01**, your domain is **Contoso.com**, and the service account is **NDESService**, use:</span></span>

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

### <a name="task-4---configure-ndes-for-use-with-intune"></a><span data-ttu-id="e5b2f-227">タスク 4 - Intune で使用するための NDES を構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-227">Task 4 - Configure NDES for use with Intune</span></span>
<span data-ttu-id="e5b2f-228">このタスクでは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-228">In this task you will:</span></span>

-   <span data-ttu-id="e5b2f-229">発行元 CA で使用するための NDES を構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-229">Configure NDES for use with the issuing CA</span></span>

-   <span data-ttu-id="e5b2f-230">IIS でサーバー認証 (SSL) 証明書をバインドします</span><span class="sxs-lookup"><span data-stu-id="e5b2f-230">Bind the server authentication (SSL) certificate in IIS</span></span>

-   <span data-ttu-id="e5b2f-231">IIS で要求フィルター処理を構成します</span><span class="sxs-lookup"><span data-stu-id="e5b2f-231">Configure Request Filtering in IIS</span></span>

##### <a name="to-configure-ndes-for-use-with-intune"></a><span data-ttu-id="e5b2f-232">Intune で使用するための NDES を構成するには</span><span class="sxs-lookup"><span data-stu-id="e5b2f-232">To configure NDES for use with Intune</span></span>

1.  <span data-ttu-id="e5b2f-233">NDES サーバーで AD CS 構成ウィザードを開き、次の構成を行います。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-233">On the NDES Server, open the AD CS Configuration wizard and then make the following configurations.</span></span>

    > [!TIP]
    > <span data-ttu-id="e5b2f-234">前のタスクでリンクをクリックした場合、このウィザードは既に開いています。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-234">If you clicked the link in the previous task, this wizard is already open.</span></span> <span data-ttu-id="e5b2f-235">それ以外の場合、サーバー マネージャーを開いて Active Directory 証明書サービスの展開後構成にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-235">Otherwise, open Server Manager to access the post-deployment configuration for Active Directory Certificate Services.</span></span>

    -   <span data-ttu-id="e5b2f-236">**[役割サービス]** ページで、**[ネットワーク デバイス登録サービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-236">On the **Role Services** Page, select the **Network Device Enrollment Service**.</span></span>

    -   <span data-ttu-id="e5b2f-237">**[NDES のサービス アカウント]** ページで、NDES サービス アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-237">On the **Service Account for NDES** page, specify the NDES Service Account.</span></span>

    -   <span data-ttu-id="e5b2f-238">**[NDES 用の CA]** ページで、**[選択]** をクリックし、証明書テンプレートを構成した発行元 CA を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-238">On the **CA for NDES** page, click **Select**, and then select the issuing CA where you configured the certificate template.</span></span>

    -   <span data-ttu-id="e5b2f-239">**[NDES の暗号化]** ページで、会社の要件を満たすキーの長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-239">On the **Cryptography for NDES** page, set the key length to meet your company requirements.</span></span>

    <span data-ttu-id="e5b2f-240">**[確認]** ページで、**[構成]** をクリックしてウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-240">On the **Confirmation** page, click **Configure** to complete the wizard.</span></span>

2.  <span data-ttu-id="e5b2f-241">ウィザードが完了した後、NDES サーバーで次のレジストリ キーを編集します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-241">After the wizard completes, edit the following registry key on the NDES Server:</span></span>

    -   <span data-ttu-id="e5b2f-242">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-242">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**</span></span>

    <span data-ttu-id="e5b2f-243">このキーを編集するには、**[要求の処理]** タブで証明書テンプレートの **[目的]** を確認し、既存のデータを、タスク 1 で指定した (テンプレートの表示名ではなく) 証明書テンプレートの名前に置き換えることによって、レジストリの対応するエントリを編集します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-243">To edit this key, identify the certificate template's **Purpose**, as found on its **Request Handling** tab, and then edit the corresponding entry in the registry by replacing the existing data with the name of the certificate template (not the display name of the template) that you specified in Task 1.</span></span> <span data-ttu-id="e5b2f-244">次の表では、証明書テンプレートの目的とレジストリの値の対応を示します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-244">The following table maps the certificate template purpose to the values in the registry:</span></span>

    |<span data-ttu-id="e5b2f-245">証明書テンプレートの目的 ([要求の処理] タブ)</span><span class="sxs-lookup"><span data-stu-id="e5b2f-245">Certificate template Purpose (On the Request Handling tab)</span></span>|<span data-ttu-id="e5b2f-246">編集するレジストリ値</span><span class="sxs-lookup"><span data-stu-id="e5b2f-246">Registry value to edit</span></span>|<span data-ttu-id="e5b2f-247">SCEP プロファイルについて Intune 管理コンソールに表示される値</span><span class="sxs-lookup"><span data-stu-id="e5b2f-247">Value seen in the Intune admin console for the SCEP profile</span></span>|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |<span data-ttu-id="e5b2f-248">署名</span><span class="sxs-lookup"><span data-stu-id="e5b2f-248">Signature</span></span>|<span data-ttu-id="e5b2f-249">SignatureTemplate</span><span class="sxs-lookup"><span data-stu-id="e5b2f-249">SignatureTemplate</span></span>|<span data-ttu-id="e5b2f-250">デジタル署名</span><span class="sxs-lookup"><span data-stu-id="e5b2f-250">Digital Signature</span></span>|
    |<span data-ttu-id="e5b2f-251">暗号化</span><span class="sxs-lookup"><span data-stu-id="e5b2f-251">Encryption</span></span>|<span data-ttu-id="e5b2f-252">EncryptionTemplate</span><span class="sxs-lookup"><span data-stu-id="e5b2f-252">EncryptionTemplate</span></span>|<span data-ttu-id="e5b2f-253">キーの暗号化</span><span class="sxs-lookup"><span data-stu-id="e5b2f-253">Key Encipherment</span></span>|
    |<span data-ttu-id="e5b2f-254">署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="e5b2f-254">Signature and encryption</span></span>|<span data-ttu-id="e5b2f-255">GeneralPurposeTemplate</span><span class="sxs-lookup"><span data-stu-id="e5b2f-255">GeneralPurposeTemplate</span></span>|<span data-ttu-id="e5b2f-256">キーの暗号化</span><span class="sxs-lookup"><span data-stu-id="e5b2f-256">Key Encipherment</span></span><br /><br /><span data-ttu-id="e5b2f-257">デジタル署名</span><span class="sxs-lookup"><span data-stu-id="e5b2f-257">Digital Signature</span></span>|
    <span data-ttu-id="e5b2f-258">たとえば、証明書テンプレートの目的が **[暗号化]** の場合、 **EncryptionTemplate** の値を証明書テンプレートの名前に編集します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-258">For example, if the Purpose of your certificate template is **Encryption**, then edit the **EncryptionTemplate** value to be the name of your certificate template.</span></span>

3. <span data-ttu-id="e5b2f-259">NDES サーバーは、非常に長い URL (クエリ) を受け取ります。2 つのレジストリ エントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-259">The NDES server will receive very long URL’s (queries), which require that you add two registry entries:</span></span>

    |<span data-ttu-id="e5b2f-260">場所</span><span class="sxs-lookup"><span data-stu-id="e5b2f-260">Location</span></span>|<span data-ttu-id="e5b2f-261">値</span><span class="sxs-lookup"><span data-stu-id="e5b2f-261">Value</span></span>|<span data-ttu-id="e5b2f-262">型</span><span class="sxs-lookup"><span data-stu-id="e5b2f-262">Type</span></span>|<span data-ttu-id="e5b2f-263">データ</span><span class="sxs-lookup"><span data-stu-id="e5b2f-263">Data</span></span>|
    |-------|-----|----|----|
    |<span data-ttu-id="e5b2f-264">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span><span class="sxs-lookup"><span data-stu-id="e5b2f-264">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span></span>|<span data-ttu-id="e5b2f-265">MaxFieldLength</span><span class="sxs-lookup"><span data-stu-id="e5b2f-265">MaxFieldLength</span></span>|<span data-ttu-id="e5b2f-266">DWORD</span><span class="sxs-lookup"><span data-stu-id="e5b2f-266">DWORD</span></span>|<span data-ttu-id="e5b2f-267">65534 (10 進数)</span><span class="sxs-lookup"><span data-stu-id="e5b2f-267">65534 (decimal)</span></span>|
    |<span data-ttu-id="e5b2f-268">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span><span class="sxs-lookup"><span data-stu-id="e5b2f-268">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span></span>|<span data-ttu-id="e5b2f-269">MaxRequestBytes</span><span class="sxs-lookup"><span data-stu-id="e5b2f-269">MaxRequestBytes</span></span>|<span data-ttu-id="e5b2f-270">DWORD</span><span class="sxs-lookup"><span data-stu-id="e5b2f-270">DWORD</span></span>|<span data-ttu-id="e5b2f-271">65534 (10 進数)</span><span class="sxs-lookup"><span data-stu-id="e5b2f-271">65534 (decimal)</span></span>|


4. <span data-ttu-id="e5b2f-272">IIS マネージャーで、**[既定の Web サイト]**  ->  **[要求のフィルタリング]**  ->  **[機能設定の編集]** の順に選択し、**[URL の最大長]** と **[クエリ文字列の最大長]** を図のように *65534* に変更します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-272">In IIS manager, choose **Default Web Site** -> **Request Filtering** -> **Edit Feature Setting**, and change the **Maximum URL length** and **Maximum query string** to *65534*, as shown.</span></span>

    ![IIS の URL とクエリの最大長](..\media\SCEP_IIS_max_URL.png)

5.  <span data-ttu-id="e5b2f-274">サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-274">Restart the server.</span></span> <span data-ttu-id="e5b2f-275">サーバーで実行されている **iisreset** は、これらの変更をファイナライズするために十分ではないでしょう。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-275">Running **iisreset** on the server will not be sufficient to finalize these changes.</span></span>
6. <span data-ttu-id="e5b2f-276">http://*FQDN*/certsrv/mscep/mscep.dll に移動します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-276">Browse to http://*FQDN*/certsrv/mscep/mscep.dll.</span></span> <span data-ttu-id="e5b2f-277">次のような NDES ページが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-277">You should see an NDES page similar to this:</span></span>

    ![NDES のテスト](..\media\SCEP_NDES_URL.png)

    <span data-ttu-id="e5b2f-279">**[503 サービスを利用できません]** が表示された場合、イベントビューアを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-279">If you get a **503 Service unavailable**, check the eventviewer.</span></span> <span data-ttu-id="e5b2f-280">おそらくは、NDES ユーザーに権限がないため、アプリケーション プールが停止しているでしょう。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-280">It's likely that the application pool is stopped due to a missing right for the NDES user.</span></span> <span data-ttu-id="e5b2f-281">それらの権限に関する説明はタスク 1 にあります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-281">Those rights are described in Task 1.</span></span>

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a><span data-ttu-id="e5b2f-282">NDES サーバーで証明書をインストールしてバインドするには</span><span class="sxs-lookup"><span data-stu-id="e5b2f-282">To Install and bind certificates on the NDES Server</span></span>

1.  <span data-ttu-id="e5b2f-283">NDES サーバーで、内部 CA またはパブリック CA に **サーバー認証** 証明書を要求してインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-283">On your NDES Server, request and install a **server authentication** certificate from your internal CA or public CA.</span></span> <span data-ttu-id="e5b2f-284">その後、この SSL 証明書を IIS でバインドします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-284">You will then bind this SSL certificate in IIS.</span></span>

    > [!TIP]
    > <span data-ttu-id="e5b2f-285">IIS で SSL 証明書をバインドした後、クライアント認証証明書もインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-285">After you bind the SSL certificate in IIS, you will also install a client authentication certificate.</span></span> <span data-ttu-id="e5b2f-286">この証明書は、NDES サーバーによって信頼されている CA によって発行できます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-286">This certificate can be issued by any CA that is trusted by the NDES Server.</span></span> <span data-ttu-id="e5b2f-287">最善の方法ではありませんが、証明書にサーバーとクライアント両方の EKU (Enhance Key Usage) がある場合は、同じ証明書をサーバー認証とクライアント認証の両方に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-287">Although it is not a best practice, you can use the same certificate for both server and client authentication as long as the certificate has both Enhance Key Usages (EKU’s).</span></span> <span data-ttu-id="e5b2f-288">これらの認証証明書については、次の手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-288">Review the following steps for information about these authentication certificates.</span></span>

    1.  <span data-ttu-id="e5b2f-289">サーバー認証証明書を取得した後、 **IIS マネージャー**を開き、**[接続]** ウィンドウで **[既定の Web サイト]** を選択し、**[操作]** ウィンドウの **[バインド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-289">After you obtain the server authentication certificate, open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then click **Bindings** in the **Actions** pane.</span></span>

    2.  <span data-ttu-id="e5b2f-290">**[追加]** をクリックし、**[種類]** を **[https]** に設定して、ポートが **443**であることを確認します</span><span class="sxs-lookup"><span data-stu-id="e5b2f-290">Click **Add**, set **Type** to **https**, and then ensure the port is **443**.</span></span> <span data-ttu-id="e5b2f-291">(スタンドアロン Intune の場合はポート 443 のみがサポートされます)。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-291">(Only port 443 is supported for standalone Intune.</span></span>

    3.  <span data-ttu-id="e5b2f-292">**[SSL 証明書]** で、サーバー認証証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-292">For **SSL certificate**, specify the server authentication certificate.</span></span>

        > [!NOTE]
        > <span data-ttu-id="e5b2f-293">NDES サーバーが 1 つのネットワーク アドレスに対して外部名と内部名の両方を使用している場合、サーバー認証証明書の **[サブジェクト名]** は外部パブリック サーバー名、**[サブジェクトの別名]** は内部サーバー名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-293">If the NDES server uses both an external and internal name for a single network address, the server authentication certificate must have a **Subject Name** with an external public server name, and a **Subject Alternative Name** that includes the internal server name.</span></span>

2.  <span data-ttu-id="e5b2f-294">NDES サーバーで、内部 CA またはパブリック CA に **クライアント認証** 証明書を要求してインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-294">On your NDES Server, request and install a **client authentication** certificate from your internal CA, or a public certificate authority.</span></span> <span data-ttu-id="e5b2f-295">証明書に両方の機能がある場合、これはサーバー認証証明書と同じ証明書でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-295">This can be the same certificate as the server authentication certificate if that certificate has both capabilities.</span></span>

    <span data-ttu-id="e5b2f-296">クライアント認証証明書には次のプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-296">The client authentication certificate must have the following properties:</span></span>

    <span data-ttu-id="e5b2f-297">**[拡張キー使用法]** - **[クライアント認証]** を含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-297">**Enhanced Key Usage** - This must include **Client Authentication**.</span></span>

    <span data-ttu-id="e5b2f-298">**[サブジェクト名]** - 証明書をインストールするサーバー (NDES サーバー) の DNS 名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-298">**Subject Name** - This must be equal to the DNS name of the server where you are installing the certificate (the NDES Server).</span></span>

##### <a name="to-configure-iis-request-filtering"></a><span data-ttu-id="e5b2f-299">IIS 要求フィルタリングを構成するには</span><span class="sxs-lookup"><span data-stu-id="e5b2f-299">To configure IIS Request Filtering</span></span>

1.  <span data-ttu-id="e5b2f-300">NDES サーバーで **IIS マネージャー**を開き、**[接続]** ウィンドウの **[既定の Web サイト]** を選択し、**[要求のフィルタリング]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-300">On the NDES Server open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then open **Request Filtering**.</span></span>

2.  <span data-ttu-id="e5b2f-301">**[機能設定の編集]** をクリックし、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-301">Click **Edit Feature Settings**, and then set the following:</span></span>

    <span data-ttu-id="e5b2f-302">**[クエリ文字列の最大長 (バイト)]** = **65534**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-302">**query string (Bytes)** = **65534**</span></span>

    <span data-ttu-id="e5b2f-303">**URL の最大長 (バイト)** = **65534**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-303">**Maximum URL length (Bytes)** = **65534**</span></span>

3.  <span data-ttu-id="e5b2f-304">次のレジストリ キーを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-304">Review the following registry key:</span></span>

    <span data-ttu-id="e5b2f-305">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-305">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**</span></span>

    <span data-ttu-id="e5b2f-306">次の値が DWORD エントリとして設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-306">Ensure the following values are set as DWORD entries:</span></span>

    <span data-ttu-id="e5b2f-307">名前: **MaxFieldLength**、10 進数値 **65534**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-307">Name: **MaxFieldLength**, with a decimal value of **65534**</span></span>

    <span data-ttu-id="e5b2f-308">名前: **MaxRequestBytes**、10 進数値 **65534**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-308">Name: **MaxRequestBytes**, with a decimal value of **65534**</span></span>

4.  <span data-ttu-id="e5b2f-309">NDES サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-309">Reboot the NDES server.</span></span> <span data-ttu-id="e5b2f-310">サーバーは証明書コネクタをサポートする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-310">The server is now ready to support the Certificate Connector.</span></span>

### <a name="task-5---enable-install-and-configure-the-intune-certificate-connector"></a><span data-ttu-id="e5b2f-311">タスク 5 - Intune 証明書コネクタを有効にし、インストールし、構成する</span><span class="sxs-lookup"><span data-stu-id="e5b2f-311">Task 5 - Enable, install, and configure the Intune Certificate Connector</span></span>
<span data-ttu-id="e5b2f-312">このタスクでは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-312">In this task you will:</span></span>

<span data-ttu-id="e5b2f-313">Intune で NDES のサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-313">Enable support for NDES in Intune.</span></span>

<span data-ttu-id="e5b2f-314">NDES サーバーで証明書コネクタをダウンロードし、インストールし、構成します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-314">Download, install, and configure the Certificate Connector on the NDES Server.</span></span>

##### <a name="to-enable-support-for-the-certificate-connector"></a><span data-ttu-id="e5b2f-315">証明書コネクタのサポートを有効にするには</span><span class="sxs-lookup"><span data-stu-id="e5b2f-315">To enable support for the Certificate Connector</span></span>

1.  <span data-ttu-id="e5b2f-316">[Intune 管理コンソール](https://manage.microsoft.com)を開き、**[管理者]** &gt; **[証明書コネクタ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-316">Open the [Intune administration console](https://manage.microsoft.com), click **Admin** &gt; **Certificate Connector**.</span></span>

2.  <span data-ttu-id="e5b2f-317">**[On-premises Certificate Connector の構成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-317">Click **Configure On-Premises Certificate Connector**.</span></span>

3.  <span data-ttu-id="e5b2f-318">**[証明書コネクタを有効にする]**を選択し、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-318">Select **Enable Certificate Connector**, and then click **OK**.</span></span>

##### <a name="to-download-install-and-configure-the-certificate-connector"></a><span data-ttu-id="e5b2f-319">証明書コネクタをダウンロードし、インストールして、構成するには</span><span class="sxs-lookup"><span data-stu-id="e5b2f-319">To download, install and configure the Certificate Connector</span></span>

1.  <span data-ttu-id="e5b2f-320">[Intune の管理コンソール](https://manage.microsoft.com)を開き、**[管理者]** &gt; **[モバイル デバイス管理]** &gt; **[証明書コネクタ]** &gt; **[証明書コネクタのダウンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-320">Open the [Intune administration console](https://manage.microsoft.com), and then click **Admin** &gt; **Mobile Device Management** &gt; **Certificate Connector** &gt; **Download Certificate Connector**.</span></span>

2.  <span data-ttu-id="e5b2f-321">ダウンロードが完了したら、ダウンロードしたインストーラー (**ndesconnectorssetup.exe**) を Windows Server 2012 R2 サーバーで実行します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-321">After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**) on a Windows Server 2012 R2 server.</span></span> <span data-ttu-id="e5b2f-322">インストーラーは、NDES のポリシー モジュールと CRP Web サービスもインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-322">The installer also installs the policy module for NDES and the CRP Web Service.</span></span> <span data-ttu-id="e5b2f-323">(CRP Web サービス CertificateRegistrationSvc は IIS のアプリケーションとして実行されます)。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-323">(The CRP Web Service, CertificateRegistrationSvc, runs as an application in IIS.)</span></span>

    > [!NOTE]
    > <span data-ttu-id="e5b2f-324">スタンドアロン Intune の NDES をインストールする場合、CRP サービスは証明書コネクタと共に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-324">When you install NDES for standalone Intune, the CRP service automatically installs with the Certificate Connector.</span></span> <span data-ttu-id="e5b2f-325">構成マネージャーで Intune を使用する場合は、証明書登録ポイントを別のサイト システムの役割としてインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-325">When you use Intune with Configuration Manager, you install the Certificate Registration Point as a separate site system role.</span></span>

3.  <span data-ttu-id="e5b2f-326">証明書コネクタのクライアント証明書の入力を求められたら、**[選択]** をクリックし、タスク 3 で NDES サーバーにインストールした **クライアント認証** 証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-326">When prompted for the client certificate for the Certificate Connector, click **Select**, and select the **client authentication** certificate you installed on your NDES Server in Task 3.</span></span>

    <span data-ttu-id="e5b2f-327">クライアント認証証明書を選択した後、**[Microsoft Intune 証明書コネクタのクライアント証明書]** 画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-327">After you select the client authentication certificate, you are returned to the **Client Certificate for Microsoft Intune Certificate Connector** surface.</span></span> <span data-ttu-id="e5b2f-328">選択した証明書は表示されませんが、**[次へ]** をクリックしてその証明書のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-328">Although the certificate you selected is not shown, click **Next** to view the properties of that certificate.</span></span> <span data-ttu-id="e5b2f-329">次に、**[次へ]** をクリックし、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-329">Then click **Next**, and then click **Install**.</span></span>

4.  <span data-ttu-id="e5b2f-330">ウィザードが完了した後、ウィザードを閉じる前に、**[証明書コネクタの UI を起動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-330">After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.</span></span>

    > [!TIP]
    > <span data-ttu-id="e5b2f-331">証明書コネクタの UI を起動する前にウィザードを閉じた場合は、次のコマンドを実行して再び開くことができます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-331">If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:</span></span>
    >
    > <span data-ttu-id="e5b2f-332">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-332">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span></span>

5.  <span data-ttu-id="e5b2f-333">**証明書コネクタ** UI で:</span><span class="sxs-lookup"><span data-stu-id="e5b2f-333">In the **Certificate Connector** UI:</span></span>

    <span data-ttu-id="e5b2f-334">**[サインイン]** をクリックし、Intune サービス管理者の資格情報、またはグローバル管理アクセス許可を持つテナント管理者の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-334">Click **Sign In** and enter your Intune service administrator credentials, or credentials for a tenant administrator with the global administration permission.</span></span>

    <span data-ttu-id="e5b2f-335">組織でプロキシ サーバーを使用していて、NDES サーバーがインターネットにアクセスするためにプロキシが必要な場合は、**[プロキシ サーバーを使用する]** をクリックし、接続するためのプロキシ サーバーの名前、ポート、およびアカウント資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-335">If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.</span></span>

    <span data-ttu-id="e5b2f-336">**[詳細設定]** タブを選択し、発行元 CA で **証明書の発行と管理** アクセス許可を持つアカウントの資格情報を指定して、**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-336">Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority, and then click **Apply**.</span></span>

    <span data-ttu-id="e5b2f-337">これで、証明書コネクタ UI を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-337">You can now close the Certificate Connector UI.</span></span>

6.  <span data-ttu-id="e5b2f-338">コマンド プロンプトを開き、「**services.msc**」と入力して **Enter** キーを押し、**Intune Connector Service** を右クリックして **[再起動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-338">Open a command prompt and type **services.msc**, and then press **Enter**, right-click the **Intune Connector Service**, and then click **Restart**.</span></span>

<span data-ttu-id="e5b2f-339">サービスが実行していることを確認するには、ブラウザーを開き、次の URL を入力します。 **403** エラーが返る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-339">To validate that the service is running, open a browser and enter the following URL, which should return a **403** error:</span></span>

<span data-ttu-id="e5b2f-340">**https://&lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**</span><span class="sxs-lookup"><span data-stu-id="e5b2f-340">**https:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**</span></span>

## <a name="next-steps"></a><span data-ttu-id="e5b2f-341">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e5b2f-341">Next steps</span></span>
<span data-ttu-id="e5b2f-342">これで、「[Configure certificate profiles](Configure-Intune-certificate-profiles.md)」 (証明書プロファイルを構成する) の説明に従って証明書プロファイルを構成する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="e5b2f-342">You are now ready to configure certificate profiles, as described in [Configure certificate profiles](Configure-Intune-certificate-profiles.md).</span></span>