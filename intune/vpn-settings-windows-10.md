---
title: "Windows 10 デバイス向けの Intune の VPN 設定"
titlesuffix: Azure portal
description: "Windows 10 デバイスで VPN 接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ced6a9620d0f4f12aba1d329cbf22f6b17622ae7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a><span data-ttu-id="7904b-103">Microsoft Intune での Windows 10 デバイス向けの VPN 設定</span><span class="sxs-lookup"><span data-stu-id="7904b-103">VPN settings for Windows 10 devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="7904b-104">選択する設定によっては、以下の一覧に記載されている値の一部を構成できない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7904b-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>


## <a name="base-vpn-settings"></a><span data-ttu-id="7904b-105">基本 VPN 設定</span><span class="sxs-lookup"><span data-stu-id="7904b-105">Base VPN settings</span></span>


- <span data-ttu-id="7904b-106">**[接続名]** - この接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7904b-106">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="7904b-107">エンド ユーザーがデバイスで利用可能な VPN 接続の一覧を参照するときに、この名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7904b-107">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="7904b-108">**[サーバー]** - デバイスの接続先とする 1 台以上の VPN サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="7904b-108">**Servers** - Add one or more VPN servers that devices will connect to.</span></span>
    - <span data-ttu-id="7904b-109">**[追加]** - **[行の追加]** ブレードが開き、以下の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7904b-109">**Add** - Opens the **Add Row** blade where you can specify the following information:</span></span>
        - <span data-ttu-id="7904b-110">**[説明]** - **Contoso VPN サーバー**のような、サーバーを表す名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-110">**Description** - Specify a descriptive name for the server like **Contoso VPN server**.</span></span>
        - <span data-ttu-id="7904b-111">**[IP アドレスまたは FQDN]** - デバイスが接続する VPN サーバーの IP アドレスまたは完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-111">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="7904b-112">例: **192.168.1.1**、**vpn.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="7904b-112">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
        - <span data-ttu-id="7904b-113">**[既定のサーバー]** - このサーバーを、デバイスで接続を確立するために使用する既定のサーバーとして有効にします。</span><span class="sxs-lookup"><span data-stu-id="7904b-113">**Default server** - Enables this server as the default server that devices will use to establish the connection.</span></span> <span data-ttu-id="7904b-114">既定のサーバーとして設定するサーバーの数は 1 台のみにしてください。</span><span class="sxs-lookup"><span data-stu-id="7904b-114">Make sure to set only one server as the default.</span></span>
    - <span data-ttu-id="7904b-115">**[インポート]** - 説明、IP アドレスまたは FQDN、既定のサーバーという形式でまとめられた、コンマ区切りのサーバーのリストを含むファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="7904b-115">**Import** - Browse to a file containing a comma-separated list of servers in the format description, IP address or FQDN, Default server.</span></span> <span data-ttu-id="7904b-116">**[OK]** を選択すると、これらが **[サーバー]** リストにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="7904b-116">Choose **OK** to import these into the **Servers** list.</span></span>
    - <span data-ttu-id="7904b-117">**[エクスポート]** - サーバーのリストをコンマ区切り値 (csv) ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7904b-117">**Export** - Exports the list of servers to a comma-separated-values (csv) file.</span></span>

<span data-ttu-id="7904b-118">**[接続の種類]** - 以下のベンダーの一覧から VPN 接続の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="7904b-118">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
- <span data-ttu-id="7904b-119">**Automatic**</span><span class="sxs-lookup"><span data-stu-id="7904b-119">**Automatic**</span></span>
- <span data-ttu-id="7904b-120">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="7904b-120">**Check Point Capsule VPN**</span></span>
- <span data-ttu-id="7904b-121">**Citrix VPN**</span><span class="sxs-lookup"><span data-stu-id="7904b-121">**Citrix VPN**</span></span>
- <span data-ttu-id="7904b-122">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="7904b-122">**Dell SonicWALL Mobile Connect**</span></span>
- <span data-ttu-id="7904b-123">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="7904b-123">**F5 Edge Client**</span></span>
- <span data-ttu-id="7904b-124">**IKEv2**</span><span class="sxs-lookup"><span data-stu-id="7904b-124">**IKEv2**</span></span>
- <span data-ttu-id="7904b-125">**L2TP**</span><span class="sxs-lookup"><span data-stu-id="7904b-125">**L2TP**</span></span>
- <span data-ttu-id="7904b-126">**PPTP**</span><span class="sxs-lookup"><span data-stu-id="7904b-126">**PPTP**</span></span>
- <span data-ttu-id="7904b-127">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="7904b-127">**Pulse Secure**</span></span>


<span data-ttu-id="7904b-128">**[ログイン グループまたはドメイン]** (Dell SonicWALL Mobile Connect のみ) - 接続先のログイン グループまたはドメインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-128">**Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.</span></span>

<span data-ttu-id="7904b-129">**[カスタム XML]**/**[EAP XML]** - VPN 接続を構成する任意のカスタム XML コマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-129">**Custom XML**/**EAP XML** - Specify any custom XML commands that configure the VPN connection.</span></span>

<span data-ttu-id="7904b-130">**Pulse Secure の例:**</span><span class="sxs-lookup"><span data-stu-id="7904b-130">**Example for Pulse Secure:**</span></span>

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

<span data-ttu-id="7904b-131">**CheckPoint Mobile VPN の例:**</span><span class="sxs-lookup"><span data-stu-id="7904b-131">**Example for CheckPoint Mobile VPN:**</span></span>

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

<span data-ttu-id="7904b-132">**Dell SonicWALL Mobile Connect の例:**</span><span class="sxs-lookup"><span data-stu-id="7904b-132">**Example for Dell SonicWALL Mobile Connect:**</span></span>

```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

<span data-ttu-id="7904b-133">**F5 Edge Client の例:**</span><span class="sxs-lookup"><span data-stu-id="7904b-133">**Example for F5 Edge Client:**</span></span>

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

<span data-ttu-id="7904b-134">カスタムの XML コマンドの記述方法については、各製造元の VPN に関するマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7904b-134">Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.</span></span>

<span data-ttu-id="7904b-135">**[分割トンネリング]** - このオプションを **[有効]** または **[無効]** にします。これを有効にすると、使用する接続をトラフィックに応じてデバイスが判断するようになります。</span><span class="sxs-lookup"><span data-stu-id="7904b-135">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="7904b-136">たとえば、ホテルにいるユーザーは、業務ファイルへのアクセスに VPN 接続を使用しますが、通常の Web 閲覧にはホテルの標準ネットワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="7904b-136">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>
- <span data-ttu-id="7904b-137">**[この VPN 接続の分割トンネリング ルート]** - サードパーティ VPN プロバイダー用のオプション ルートを追加します。</span><span class="sxs-lookup"><span data-stu-id="7904b-137">**Split tunneling routes for this VPN connection** - Add optional routes for third-party VPN providers.</span></span> <span data-ttu-id="7904b-138">各ルートの宛先プレフィックスとプレフィックス サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-138">Specify a destination prefix, and a prefix size for each.</span></span>

## <a name="apps-and-traffic-rules"></a><span data-ttu-id="7904b-139">アプリとトラフィックの規則</span><span class="sxs-lookup"><span data-stu-id="7904b-139">Apps and Traffic Rules</span></span>

<span data-ttu-id="7904b-140">**[これらのアプリへの VPN 接続を制限する]** - 指定したアプリでのみ VPN 接続を使用したい場合にこのオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7904b-140">**Restrict VPN connection to these apps** - Enable this option if you only want apps you specify to use the VPN connection.</span></span>
<span data-ttu-id="7904b-141">**[関連付けられているアプリ]** - 自動的に VPN 接続を使用するアプリのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-141">**Associated Apps** - Provide a list of apps that will automatically use the VPN connection.</span></span> <span data-ttu-id="7904b-142">アプリ ID は、アプリの種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="7904b-142">The type of app will determine the app identifier.</span></span> <span data-ttu-id="7904b-143">ユニバーサル アプリの場合、パッケージのファミリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-143">For a universal app, provide the package family name.</span></span> <span data-ttu-id="7904b-144">デスクトップ アプリの場合、アプリのファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-144">For a desktop app, provide the file path of the app.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7904b-145">アプリごとの VPN の構成で使用するためにコンパイルするアプリのすべてのリストをセキュリティで保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7904b-145">We recommend that you secure all lists of apps that you compile for use in configuration of per-app VPN.</span></span> <span data-ttu-id="7904b-146">承認されていないユーザーが変更したリストをアプリごとの VPN アプリ リストにインポートすると、アクセス権のないアプリへの VPN アクセスが承認される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7904b-146">If an unauthorized user modifies your list and you import it into the per-app VPN app list, you will potentially authorize VPN access to apps that should not have access.</span></span> <span data-ttu-id="7904b-147">アプリ リストをセキュリティで保護する 1 つの方法は、アクセス制御リスト (ACL) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="7904b-147">One way you can secure app lists is by using an access control list (ACL).</span></span>

<span data-ttu-id="7904b-148">**[この VPN 接続のネットワーク トラフィック規則]** - VPN 接続に対して有効にするプロトコル、ローカル ポートとリモート ポート、アドレス範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="7904b-148">**Network traffic rules for this VPN connection** - Select which protocols, and which local and remote port and address ranges, will be enabled for the VPN connection.</span></span> <span data-ttu-id="7904b-149">ネットワーク トラフィック規則を作成しない場合は、すべてのプロトコル、ポート、およびアドレス範囲が有効になります。</span><span class="sxs-lookup"><span data-stu-id="7904b-149">If you do not create a network traffic rule, all protocols, ports, and address ranges are enabled.</span></span> <span data-ttu-id="7904b-150">規則を作成すると、その規則で指定したプロトコル、ポート、およびアドレス範囲だけが、VPN 接続で使用されます。</span><span class="sxs-lookup"><span data-stu-id="7904b-150">After you create a rule, the VPN connection will use only the protocols, ports, and address ranges that you specify in that rule.</span></span>


## <a name="conditional-access"></a><span data-ttu-id="7904b-151">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="7904b-151">Conditional Access</span></span>

<span data-ttu-id="7904b-152">**この VPN 接続の条件付きアクセス** - クライアントからのデバイス コンプライアンス フローを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7904b-152">**Conditional access for this VPN connection** - Enables device compliance flow from the client.</span></span> <span data-ttu-id="7904b-153">有効にすると、VPN クライアントは Azure Active Directory と通信し、認証に使用する証明書の取得を試行します。</span><span class="sxs-lookup"><span data-stu-id="7904b-153">When enabled, the VPN client will attempt to communicate with Azure Active Directory to get a certificate to use for authentication.</span></span> <span data-ttu-id="7904b-154">証明書認証を利用するには、VPN を設定する必要があります。VPN サーバーは、Azure Active Directory が返すサーバーを信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7904b-154">The VPN should be set up to use certificate authentication, and the VPN server must trust the server returned by Azure Active Directory.</span></span>

<span data-ttu-id="7904b-155">**代替証明書によるシングル サインオン (SSO)** - デバイス コンプライアンスの場合、Kerberos 認証のために、VPN 認証証明書とは異なる証明書を利用します。</span><span class="sxs-lookup"><span data-stu-id="7904b-155">**Single sign-on (SSO) with alternate certificate** - For device compliance, use a certificate different from the VPN authentication certificate for Kerberos authentication.</span></span> <span data-ttu-id="7904b-156">次の設定で証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-156">Specify the certificate with the following settings:</span></span> 

- <span data-ttu-id="7904b-157">**拡張キー使用法** - 拡張キー使用法 (EKU) の名前。</span><span class="sxs-lookup"><span data-stu-id="7904b-157">**Extended key usage** - Name for extended key usage (EKU).</span></span>
- <span data-ttu-id="7904b-158">**オブジェクト識別子** - EKU のオブジェクト識別子。</span><span class="sxs-lookup"><span data-stu-id="7904b-158">**Object Identifier** - Object identifier for EKU.</span></span>
- <span data-ttu-id="7904b-159">**発行者ハッシュ** - SSO 証明書のサムプリント。</span><span class="sxs-lookup"><span data-stu-id="7904b-159">**Issuer hash** - Thumbprint for SSO certificate.</span></span>

## <a name="dns-settings"></a><span data-ttu-id="7904b-160">DNS の設定</span><span class="sxs-lookup"><span data-stu-id="7904b-160">DNS Settings</span></span>

<span data-ttu-id="7904b-161">**[この VPN 接続の DNS 名と DNS サーバー]** - 接続が確立された後に VPN 接続で使用する DNS サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7904b-161">**DNS names and servers for this VPN connection** - Select which DNS servers the VPN connection will use after the connection is established.</span></span>
<span data-ttu-id="7904b-162">サーバーごとに、</span><span class="sxs-lookup"><span data-stu-id="7904b-162">For each server.</span></span> <span data-ttu-id="7904b-163">次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-163">specify:</span></span>
- <span data-ttu-id="7904b-164">**[DNS 名]**</span><span class="sxs-lookup"><span data-stu-id="7904b-164">**DNS Name**</span></span>
- <span data-ttu-id="7904b-165">**[DNS サーバー]**</span><span class="sxs-lookup"><span data-stu-id="7904b-165">**DNS Server**</span></span>
- <span data-ttu-id="7904b-166">**[プロキシ]**</span><span class="sxs-lookup"><span data-stu-id="7904b-166">**Proxy**</span></span>

## <a name="proxy-settings"></a><span data-ttu-id="7904b-167">プロキシの設定</span><span class="sxs-lookup"><span data-stu-id="7904b-167">Proxy settings</span></span>

- <span data-ttu-id="7904b-168">**[自動的にプロキシ設定を検出する]** - VPN サーバーが接続にプロキシ サーバーを必要とする場合は、デバイスで接続の設定を自動的に検出するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7904b-168">**Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings.</span></span> <span data-ttu-id="7904b-169">詳細については、Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7904b-169">For more information, see your Windows Server documentation.</span></span>
- <span data-ttu-id="7904b-170">**[自動構成スクリプト]** - ファイルを使用してプロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7904b-170">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="7904b-171">構成ファイルが格納されている**プロキシ サーバーの URL** を入力します (たとえば、**http://proxy.contoso.com**)。</span><span class="sxs-lookup"><span data-stu-id="7904b-171">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="7904b-172">**[プロキシ サーバーを使用する]** - プロキシ サーバーの設定を手動で入力する場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7904b-172">**Use proxy server** - Enable this option if you want to manually enter the proxy server settings.</span></span>
    - <span data-ttu-id="7904b-173">**[アドレス]** - プロキシ サーバーのアドレスを (IP アドレスとして) 入力します。</span><span class="sxs-lookup"><span data-stu-id="7904b-173">**Address** - Enter the proxy server address (as an IP address).</span></span>
    - <span data-ttu-id="7904b-174">**[ポート番号]** - プロキシ サーバーに関連付けられているポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="7904b-174">**Port number** - Enter the port number associated with the proxy server.</span></span>
- <span data-ttu-id="7904b-175">**[ローカル アドレスにはプロキシ サーバーを使用しない]** - VPN サーバーが接続にプロキシ サーバーを必要とする場合、指定したローカル アドレスに対してプロキシ サーバーを使用しないようにするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7904b-175">**Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</span></span> <span data-ttu-id="7904b-176">詳細については、Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7904b-176">For more information, see your Windows Server documentation.</span></span>
