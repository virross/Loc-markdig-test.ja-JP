---
title: "iOS デバイス向けの Intune VPN 設定"
titlesuffix: Azure portal
description: "iOS デバイスでの VPN 接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 936990786316403f4d7adecc934bd946d845a753
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="vpn-settings-for-ios-devices-in-microsoft-intune"></a><span data-ttu-id="15784-103">Microsoft Intune での iOS デバイス向けの VPN 設定</span><span class="sxs-lookup"><span data-stu-id="15784-103">VPN settings for iOS devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="15784-104">選択した設定によっては、次の一覧に記載されている値の一部を構成できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="15784-104">Depending on the settings you choose, not all values in the following list are configurable.</span></span>

## <a name="base-vpn-settings"></a><span data-ttu-id="15784-105">基本 VPN 設定</span><span class="sxs-lookup"><span data-stu-id="15784-105">Base VPN settings</span></span>


<span data-ttu-id="15784-106">**[接続名]** - この接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="15784-106">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="15784-107">エンド ユーザーがデバイスで利用可能な VPN 接続の一覧を参照するときに、この名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="15784-107">End users see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="15784-108">**[IP アドレスまたは FQDN]** - デバイスが接続する VPN サーバーの IP アドレスまたは完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="15784-108">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices connect to.</span></span> <span data-ttu-id="15784-109">例: **192.168.1.1**、**vpn.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="15784-109">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="15784-110">**[認証方法]** - VPN サーバーに対するデバイスの認証方法として、以下のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="15784-110">**Authentication method** - Choose how devices authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="15784-111">**[証明書]** - **[認証証明書]** で、接続を認証するために事前に作成した SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="15784-111">**Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="15784-112">証明書プロファイルの詳細については、[証明書の構成方法](certificates-configure.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15784-112">For more information about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="15784-113">**[ユーザー名とパスワード]** - エンド ユーザーは VPN サーバーにログインするためにユーザー名とパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15784-113">**Username and password** - End users must supply a username and password to log in to the VPN server.</span></span>
- <span data-ttu-id="15784-114">**[接続の種類]** - 以下のベンダーの一覧から VPN 接続の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="15784-114">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="15784-115">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="15784-115">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="15784-116">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="15784-116">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="15784-117">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="15784-117">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="15784-118">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="15784-118">**F5 Edge Client**</span></span>
    - <span data-ttu-id="15784-119">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="15784-119">**Pulse Secure**</span></span>
    - <span data-ttu-id="15784-120">**Cisco (IPSec)**</span><span class="sxs-lookup"><span data-stu-id="15784-120">**Cisco (IPSec)**</span></span>
    - <span data-ttu-id="15784-121">**Citrix**</span><span class="sxs-lookup"><span data-stu-id="15784-121">**Citrix**</span></span>
    - <span data-ttu-id="15784-122">**Custom VPN**</span><span class="sxs-lookup"><span data-stu-id="15784-122">**Custom VPN**</span></span>
- <span data-ttu-id="15784-123">**[分割トンネリング]**  -  このオプションを **[有効]** または **[無効]** にします。これを有効にすると、使用する接続をトラフィックに応じてデバイスが判断するようになります。</span><span class="sxs-lookup"><span data-stu-id="15784-123">**Split tunneling** - **Enable** or **Disable** this option, which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="15784-124">たとえば、ホテルにいるユーザーは、業務ファイルへのアクセスに VPN 接続を使用しますが、通常の Web 閲覧にはホテルの標準ネットワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="15784-124">For example, a user in a hotel uses the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>


## <a name="custom-vpn-settings"></a><span data-ttu-id="15784-125">カスタム VPN 設定</span><span class="sxs-lookup"><span data-stu-id="15784-125">Custom VPN settings</span></span>

<span data-ttu-id="15784-126">接続の種類として **[カスタム VPN]** を選択した場合は、以下の追加設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="15784-126">If you selected **Custom VPN** as the connection type, configure these further settings:</span></span>

- <span data-ttu-id="15784-127">**[VPN 識別子]** - これは使用している VPN アプリの識別子であり、VPN プロバイダーから提供されます。</span><span class="sxs-lookup"><span data-stu-id="15784-127">**VPN identifier** This is an identifier for the VPN app you are using, and is supplied by your VPN provider.</span></span>
- <span data-ttu-id="15784-128">**[カスタム VPN 属性に対してキーと値を入力します]** - VPN 接続をカスタマイズする**キー**と**値**を追加またはインポートします。</span><span class="sxs-lookup"><span data-stu-id="15784-128">**Enter key and value pairs for the custom VPN attributes** Add or import **Keys** and **Values** that customize your VPN connection.</span></span> <span data-ttu-id="15784-129">これらの値も、通常は VPN プロバイダーから提供されます。</span><span class="sxs-lookup"><span data-stu-id="15784-129">Again, these values are typically supplied by your VPN provider.</span></span>

## <a name="apps-per-app-vpn-settings"></a><span data-ttu-id="15784-130">アプリ (アプリごとの VPN) 設定</span><span class="sxs-lookup"><span data-stu-id="15784-130">Apps (per-app VPN) settings</span></span>

- <span data-ttu-id="15784-131">**[アプリごとの VPN]** - Safari ブラウザーからのアクセス時に VPN 接続を有効にする URL が必要な場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="15784-131">**Per-app VPN** - Enable this option if you want to URLs that enable the VPN connection when they are visited from the Safari browser.</span></span> <span data-ttu-id="15784-132">これを構成するには、基本 VPN 設定の認証方法として **[証明書]** を選択している必要があります。</span><span class="sxs-lookup"><span data-stu-id="15784-132">To configure this, you must have selected **Certificates** as the authentication method in the base VPN settings.</span></span>
- <span data-ttu-id="15784-133">**[Safari ブラウザーを使用しているときに VPN 接続を有効にする URL を指定します]** - [追加] をクリックして 1 つ以上の Web サイト URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="15784-133">**URLs that enable the VPN connection while using the Safari browser** - Click add to add one or more web site URLs.</span></span> <span data-ttu-id="15784-134">これらの URL にアクセスすると、VPN 接続が有効になります。</span><span class="sxs-lookup"><span data-stu-id="15784-134">When these URLs are visited, the VPN connection is enabled.</span></span>

- <span data-ttu-id="15784-135">**[On-demand rules (オンデマンド ルール)]** - この設定を使用すると、VPN 接続が開始されるタイミングを制御する条件付き規則を構成できます。</span><span class="sxs-lookup"><span data-stu-id="15784-135">**On-demand rules** - This lets you configure conditional rules that control when the VPN connection is initiated.</span></span> <span data-ttu-id="15784-136">たとえば、デバイスが会社の Wi-Fi ネットワークに接続されていない場合にのみ VPN 接続を使用するというような条件を作成できます。</span><span class="sxs-lookup"><span data-stu-id="15784-136">For example, you could create a condition where the VPN connection is only used when a device is not connected to one of your company Wi-Fi networks.</span></span> <span data-ttu-id="15784-137">また、指定した DNS 検索ドメインにデバイスがアクセスできない場合には VPN 接続を開始しないといった条件を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="15784-137">Alternatively, you could create a condition where, if a device cannot access a DNS search domain you specify, then the VPN connection is not initiated.</span></span>

    - <span data-ttu-id="15784-138">**[SSID または DNS 検索ドメイン]** - この条件でワイヤレス ネットワークの **SSID** を使用するか、**DNS 検索ドメイン**を使用するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="15784-138">**SSIDs or DNS search domains** - Select whether this condition uses wireless network **SSIDs**, or **DNS search domains**.</span></span> <span data-ttu-id="15784-139">1 つ以上の SSID または検索ドメインを構成するには、[追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="15784-139">Choose Add to configure one or more SSIDs or search domains.</span></span>
    - <span data-ttu-id="15784-140">**[URL 文字列プローブ]** - 必要に応じて、規則によってテストとして使用する URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="15784-140">**URL string probe** - Optionally, provide a URL that the rule uses as a test.</span></span> <span data-ttu-id="15784-141">このプロファイルがインストールされているデバイスがリダイレクトなしでこの URL にアクセスできる場合は、VPN 接続が開始され、デバイスがターゲット URL に接続されます。</span><span class="sxs-lookup"><span data-stu-id="15784-141">If the device on which this profile is installed is able to access this URL without redirection, the VPN connection is initiated and the device connects to the target URL.</span></span> <span data-ttu-id="15784-142">ユーザーには、URL 文字列プローブ サイトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="15784-142">The user will not see the URL string probe site.</span></span> <span data-ttu-id="15784-143">URL 文字列プローブの例としては、VPN への接続前にデバイスのポリシー準拠を確認する監査 Web サーバーのアドレスがあります。</span><span class="sxs-lookup"><span data-stu-id="15784-143">An example of a URL string probe is the address of an auditing Web server that checks device compliance before connecting the VPN.</span></span> <span data-ttu-id="15784-144">別の例としては、デバイスを VPN 経由でターゲット URL に接続する前に、サイトに接続する VPN の機能をテストする URL があります。</span><span class="sxs-lookup"><span data-stu-id="15784-144">Another possibility is that the URL tests the ability of the VPN to connect to a site before connecting the device to the target URL through the VPN.</span></span>
    - <span data-ttu-id="15784-145">**[ドメインのアクション]** - 以下のいずれかの項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="15784-145">**Domain action** - Choose one of the following items:</span></span>
        - <span data-ttu-id="15784-146">[必要な場合に接続する]</span><span class="sxs-lookup"><span data-stu-id="15784-146">Connect if needed -</span></span> 
        - <span data-ttu-id="15784-147">[接続しない]</span><span class="sxs-lookup"><span data-stu-id="15784-147">Never connect -</span></span> 
    - <span data-ttu-id="15784-148">**[アクション]** - 以下のいずれかの項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="15784-148">**Action** - Choose one of the following items:</span></span>
        - <span data-ttu-id="15784-149">[接続]</span><span class="sxs-lookup"><span data-stu-id="15784-149">Connect -</span></span> 
        - <span data-ttu-id="15784-150">[接続の評価]</span><span class="sxs-lookup"><span data-stu-id="15784-150">Evaluate connection -</span></span> 
        - <span data-ttu-id="15784-151">[無視]</span><span class="sxs-lookup"><span data-stu-id="15784-151">Ignore -</span></span> 
        - <span data-ttu-id="15784-152">[切断]</span><span class="sxs-lookup"><span data-stu-id="15784-152">Disconnect -</span></span> 


## <a name="proxy-settings"></a><span data-ttu-id="15784-153">プロキシの設定</span><span class="sxs-lookup"><span data-stu-id="15784-153">Proxy settings</span></span>

- <span data-ttu-id="15784-154">**[自動構成スクリプト]** - ファイルを使用してプロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="15784-154">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="15784-155">構成ファイルが格納されている**プロキシ サーバーの URL** を入力します (たとえば、**http://proxy.contoso.com**)。</span><span class="sxs-lookup"><span data-stu-id="15784-155">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="15784-156">**[アドレス]** - プロキシ サーバーのアドレスを (IP アドレスとして) 入力します。</span><span class="sxs-lookup"><span data-stu-id="15784-156">**Address** - Enter the proxy server address (as an IP address).</span></span>
- <span data-ttu-id="15784-157">**[ポート番号]** - プロキシ サーバーに関連付けられているポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="15784-157">**Port number** - Enter the port number associated with the proxy server.</span></span>