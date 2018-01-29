---
title: "Windows Phone 8.1 デバイス向けの Intune VPN 設定"
titleSuffix: Azure portal
description: "Windows Phone 8.1 デバイスの VPN 接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6d4af72815f36678ae6de9be3039ab6dcf2899e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="vpn-settings-for-windows-phone-81-devices-in-microsoft-intune"></a><span data-ttu-id="3f8fa-103">Microsoft Intune での Windows Phone 8.1 デバイス向けの VPN 設定</span><span class="sxs-lookup"><span data-stu-id="3f8fa-103">VPN settings for Windows Phone 8.1 devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="3f8fa-104">選択する設定によっては、以下の一覧に記載されている値の一部を構成できない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <a name="base-vpn-settings"></a><span data-ttu-id="3f8fa-105">基本 VPN 設定</span><span class="sxs-lookup"><span data-stu-id="3f8fa-105">Base VPN settings</span></span>

- <span data-ttu-id="3f8fa-106">**[Apply all settings to Windows Phone 8.1 only (すべての設定を Windows Phone 8.1 のみに適用する)]** - これは、Intune クラシック ポータルで構成できる設定です。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-106">**Apply all settings to Windows Phone 8.1 only** - This is a setting you can configure in the Intune classic portal.</span></span> <span data-ttu-id="3f8fa-107">Azure Portal では、この設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-107">In the Azure portal, this setting cannot be changed.</span></span> <span data-ttu-id="3f8fa-108">これを **[構成済み]** に設定すると、すべての設定が Windows Phone 8.1 デバイスのみに適用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-108">If this is set to **Configured**, any settings will only be applied to Windows Phone 8.1 devices.</span></span> <span data-ttu-id="3f8fa-109">**[未構成]** に設定されている場合、これらの設定は Windows 10 Mobile デバイスにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-109">If set to **Not Configured**, these settings will also apply to Windows 10 Mobile devices.</span></span>
- <span data-ttu-id="3f8fa-110">**[接続名]** - この接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-110">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="3f8fa-111">エンド ユーザーがデバイスで利用可能な VPN 接続の一覧を参照するときに、この名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-111">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="3f8fa-112">**[認証方法]** - VPN サーバーに対するデバイスの認証方法として、以下のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-112">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="3f8fa-113">**[証明書]** - **[認証証明書]** で、接続を認証するために事前に作成した SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-113">**Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="3f8fa-114">証明書プロファイルの詳細については、[証明書の構成方法](certificates-configure.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-114">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="3f8fa-115">**[ユーザー名とパスワード]** - エンド ユーザーは VPN サーバーにログインするためにユーザー名とパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-115">**Username and password** - End users must supply a username and password to log into the VPN server.</span></span>
- <span data-ttu-id="3f8fa-116">**[サーバー]** - デバイスの接続先とする 1 台以上の VPN サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-116">**Servers** - Add one or more VPN servers that devices will connect to.</span></span>
    - <span data-ttu-id="3f8fa-117">**[追加]** - **[行の追加]** ブレードが開き、以下の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-117">**Add** - Opens the **Add Row** blade where you can specify the following information:</span></span>
        - <span data-ttu-id="3f8fa-118">**[説明]** - **Contoso VPN サーバー**のような、サーバーを表す名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-118">**Description** - Specify a descriptive name for the server like **Contoso VPN server**.</span></span>
        - <span data-ttu-id="3f8fa-119">**[IP アドレスまたは FQDN]** - デバイスが接続する VPN サーバーの IP アドレスまたは完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-119">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="3f8fa-120">例: **192.168.1.1**、**vpn.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-120">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
        - <span data-ttu-id="3f8fa-121">**[既定のサーバー]** - このサーバーを、デバイスで接続を確立するために使用する既定のサーバーとして有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-121">**Default server** - Enables this server as the default server that devices will use to establish the connection.</span></span> <span data-ttu-id="3f8fa-122">既定のサーバーとして設定するサーバーの数は 1 台のみにしてください。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-122">Make sure to set only one server as the default.</span></span>
    - <span data-ttu-id="3f8fa-123">**[インポート]** - 説明、IP アドレスまたは FQDN、既定のサーバーという形式でまとめられた、コンマ区切りのサーバーのリストを含むファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-123">**Import** - Browse to a file containing a comma-separated list of servers in the format description, IP address or FQDN, Default server.</span></span> <span data-ttu-id="3f8fa-124">**[OK]** を選択すると、これらが **[サーバー]** リストにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-124">Choose **OK** to import these into the **Servers** list.</span></span>
    - <span data-ttu-id="3f8fa-125">**[エクスポート]** - サーバーのリストをコンマ区切り値 (csv) ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-125">**Export** - Exports the list of servers to a comma-separated-values (csv) file.</span></span>

- <span data-ttu-id="3f8fa-126">**[会社の Wi-Fi ネットワークでは VPN を使用しない]** - デバイスが会社の Wi-Fi ネットワークに接続されている場合に VPN 接続を使用しないように指定するには、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-126">**Bypass VPN on company Wi-Fi network** - Enable this option to specify that the VPN connection will not be used when the device is connected to the company Wi-Fi network.</span></span>
- <span data-ttu-id="3f8fa-127">**[自宅の Wi-Fi ネットワークでは VPN を使用しない]** - デバイスが自宅の Wi-Fi ネットワークに接続されている場合に VPN 接続を使用しないように指定するには、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-127">**Bypass VPN on home Wi-Fi network** - Enable this option to specify that the VPN connection will not be used when the device is connected to a home Wi-Fi network.</span></span>

- <span data-ttu-id="3f8fa-128">**[接続の種類]** - 以下のベンダーの一覧から VPN 接続の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-128">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="3f8fa-129">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="3f8fa-129">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="3f8fa-130">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="3f8fa-130">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="3f8fa-131">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="3f8fa-131">**F5 Edge Client**</span></span>
    - <span data-ttu-id="3f8fa-132">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="3f8fa-132">**Pulse Secure**</span></span>

- <span data-ttu-id="3f8fa-133">**[ログイン グループまたはドメイン]** (Dell SonicWALL Mobile Connect のみ) - 接続先のログイン グループまたはドメインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-133">**Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.</span></span>
- <span data-ttu-id="3f8fa-134">**[ロール]** (Pulse Secure のみ) - この接続に対するアクセス権を持つユーザー ロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-134">**Role** (Pulse Secure only) - Specify the name of the user role that has access to this connection.</span></span> <span data-ttu-id="3f8fa-135">ユーザー ロールを使用して、個人の設定とオプションを定義し、特定のアクセス機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-135">A user role defines personal settings and options, and it enables or disables certain access features.</span></span>
- <span data-ttu-id="3f8fa-136">**[領域]** (Pulse Secure のみ) - 使用する認証領域の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-136">**Realm** (Pulse Secure only) - Specify the name of the authentication realm that you want to use.</span></span> <span data-ttu-id="3f8fa-137">認証領域とは、接続の種類が [Pulse Secure] の場合に使用される認証リソースのグループを表します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-137">An authentication realm is a grouping of authentication resources that the Pulse Secure connection type uses.</span></span>

- <span data-ttu-id="3f8fa-138">**[DNS サフィックス検索一覧]** - 1 つ以上の DNS サフィックスを**追加**します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-138">**DNS suffix search list** - **Add** one or more DNS suffices.</span></span> <span data-ttu-id="3f8fa-139">短い名前を使用して Web サイトに接続するときに、指定した各 DNS サフィックスが検索されます。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-139">Each DNS suffix that you specify will be searched when connecting to a website by using a short name.</span></span> <span data-ttu-id="3f8fa-140">たとえば、**domain1.contoso.com** と **domain2.contoso.com** の DNS サフィックスを指定して URL **http://mywebsite** にアクセスすると、URL **http://mywebsite.domain1.contoso.com** と **http://mywebsite.domain2.contoso.com** が検索されます。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-140">For example, specify the DNS suffixes **domain1.contoso.com** and **domain2.contoso.com**, visit the URL **http://mywebsite**, and the URLs **http://mywebsite.domain1.contoso.com** and **http://mywebsite.domain2.contoso.com will be searched**.</span></span>

- <span data-ttu-id="3f8fa-141">**[カスタム XML]** - VPN 接続を構成する任意のカスタム XML コマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-141">**Custom XML** - Specify any custom XML commands that configure the VPN connection.</span></span>

    <span data-ttu-id="3f8fa-142">**Pulse Secure の例:**</span><span class="sxs-lookup"><span data-stu-id="3f8fa-142">**Example for Pulse Secure:**</span></span>

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

<span data-ttu-id="3f8fa-143">**CheckPoint Mobile VPN の例:**</span><span class="sxs-lookup"><span data-stu-id="3f8fa-143">**Example for CheckPoint Mobile VPN:**</span></span>

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

<span data-ttu-id="3f8fa-144">**Dell SonicWALL Mobile Connect の例:**</span><span class="sxs-lookup"><span data-stu-id="3f8fa-144">**Example for Dell SonicWALL Mobile Connect:**</span></span>
```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

<span data-ttu-id="3f8fa-145">**F5 Edge Client の例:**</span><span class="sxs-lookup"><span data-stu-id="3f8fa-145">**Example for F5 Edge Client:**</span></span>
```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

<span data-ttu-id="3f8fa-146">カスタムの XML コマンドの記述方法については、各製造元の VPN に関するマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-146">Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.</span></span>

- <span data-ttu-id="3f8fa-147">**[分割トンネリング]** - このオプションを **[有効]** または **[無効]** にします。これを有効にすると、使用する接続をトラフィックに応じてデバイスが判断するようになります。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-147">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="3f8fa-148">たとえば、ホテルにいるユーザーは、業務ファイルへのアクセスに VPN 接続を使用しますが、通常の Web 閲覧にはホテルの標準ネットワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-148">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>




## <a name="proxy-settings"></a><span data-ttu-id="3f8fa-149">プロキシの設定</span><span class="sxs-lookup"><span data-stu-id="3f8fa-149">Proxy settings</span></span>

- <span data-ttu-id="3f8fa-150">**[自動的にプロキシ設定を検出する]** - VPN サーバーが接続にプロキシ サーバーを必要とする場合は、デバイスで接続の設定を自動的に検出するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-150">**Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings.</span></span> <span data-ttu-id="3f8fa-151">詳細については、Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-151">For more information, see your Windows Server documentation.</span></span>
- <span data-ttu-id="3f8fa-152">**[自動構成スクリプト]** - ファイルを使用してプロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-152">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="3f8fa-153">構成ファイルが格納されている**プロキシ サーバーの URL** を入力します (たとえば、**http://proxy.contoso.com**)。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-153">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="3f8fa-154">**[プロキシ サーバーを使用する]** - プロキシ サーバーの設定を手動で入力する場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-154">**Use proxy server** - Enable this option if you want to manually enter the proxy server settings.</span></span>
    - <span data-ttu-id="3f8fa-155">**[アドレス]** - プロキシ サーバーのアドレスを (IP アドレスとして) 入力します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-155">**Address** - Enter the proxy server address (as an IP address).</span></span>
    - <span data-ttu-id="3f8fa-156">**[ポート番号]** - プロキシ サーバーに関連付けられているポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-156">**Port number** - Enter the port number associated with the proxy server.</span></span>
- <span data-ttu-id="3f8fa-157">**[ローカル アドレスにはプロキシ サーバーを使用しない]** - VPN サーバーが接続にプロキシ サーバーを必要とする場合、指定したローカル アドレスに対してプロキシ サーバーを使用しないようにするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-157">**Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</span></span> <span data-ttu-id="3f8fa-158">詳細については、Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f8fa-158">For more information, see your Windows Server documentation.</span></span>
