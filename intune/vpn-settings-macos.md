---
title: "macOS デバイス向けの Intune VPN 設定"
titlesuffix: Azure portal
description: "macOS デバイスでの VPN 接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45af33023468bdb396c8bf54c53266e67323aff5
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="vpn-settings-for-macos-devices-in-microsoft-intune"></a><span data-ttu-id="820e2-103">Microsoft Intune での macOS デバイス向けの VPN 設定</span><span class="sxs-lookup"><span data-stu-id="820e2-103">VPN settings for macOS devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="820e2-104">選択する設定によっては、以下の一覧に記載されている値の一部を構成できない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="820e2-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <a name="base-vpn-settings"></a><span data-ttu-id="820e2-105">**基本 VPN 設定**</span><span class="sxs-lookup"><span data-stu-id="820e2-105">**Base VPN settings**</span></span>

<span data-ttu-id="820e2-106">**[接続名]** - この接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="820e2-106">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="820e2-107">エンド ユーザーがデバイスで利用可能な VPN 接続の一覧を参照するときに、この名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="820e2-107">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="820e2-108">**[IP アドレスまたは FQDN]** - デバイスが接続する VPN サーバーの IP アドレスまたは完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="820e2-108">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="820e2-109">例: **192.168.1.1**、**vpn.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="820e2-109">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="820e2-110">**[認証方法]** - VPN サーバーに対するデバイスの認証方法として、以下のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="820e2-110">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="820e2-111">**[証明書]** - **[認証証明書]** で、接続を認証するために事前に作成した SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="820e2-111">**Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="820e2-112">証明書プロファイルの詳細については、[証明書の構成方法](certificates-configure.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="820e2-112">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="820e2-113">**[ユーザー名とパスワード]** - エンド ユーザーは VPN サーバーにログインするためにユーザー名とパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="820e2-113">**Username and password** - End users must supply a username and password to log into the VPN server.</span></span>
- <span data-ttu-id="820e2-114">**[接続の種類]** - 以下のベンダーの一覧から VPN 接続の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="820e2-114">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="820e2-115">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="820e2-115">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="820e2-116">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="820e2-116">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="820e2-117">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="820e2-117">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="820e2-118">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="820e2-118">**F5 Edge Client**</span></span>
    - <span data-ttu-id="820e2-119">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="820e2-119">**Pulse Secure**</span></span>
    - <span data-ttu-id="820e2-120">**Custom VPN**</span><span class="sxs-lookup"><span data-stu-id="820e2-120">**Custom VPN**</span></span>
- <span data-ttu-id="820e2-121">**[分割トンネリング]** - このオプションを **[有効]** または **[無効]** にします。これを有効にすると、使用する接続をトラフィックに応じてデバイスが判断するようになります。</span><span class="sxs-lookup"><span data-stu-id="820e2-121">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="820e2-122">たとえば、ホテルにいるユーザーは、業務ファイルへのアクセスに VPN 接続を使用しますが、通常の Web 閲覧にはホテルの標準ネットワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="820e2-122">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](apps-deploy.md). --->

## <a name="custom-vpn-settings"></a><span data-ttu-id="820e2-123">カスタム VPN 設定</span><span class="sxs-lookup"><span data-stu-id="820e2-123">Custom VPN settings</span></span>

<span data-ttu-id="820e2-124">**[カスタム VPN]** を選択した場合は、以下の追加設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="820e2-124">If you selected **Custom VPN**, configure these further settings:</span></span>

- <span data-ttu-id="820e2-125">**[VPN 識別子]** - これは使用している VPN アプリの識別子であり、VPN プロバイダーから提供されます。</span><span class="sxs-lookup"><span data-stu-id="820e2-125">**VPN identifier** This is an identifier for the VPN app you are using, and is supplied by your VPN provider.</span></span>
- <span data-ttu-id="820e2-126">**[カスタム VPN 属性に対してキーと値を入力します]** - VPN 接続をカスタマイズする**キー**と**値**を追加またはインポートします。</span><span class="sxs-lookup"><span data-stu-id="820e2-126">**Enter key and value pairs for the custom VPN attributes** Add or import **Keys** and **Values** that customize your VPN connection.</span></span> <span data-ttu-id="820e2-127">これらの値も、通常は VPN プロバイダーから提供されます。</span><span class="sxs-lookup"><span data-stu-id="820e2-127">Again, these values are typically supplied by your VPN provider.</span></span>


## <a name="proxy-settings"></a><span data-ttu-id="820e2-128">プロキシの設定</span><span class="sxs-lookup"><span data-stu-id="820e2-128">Proxy settings</span></span>

- <span data-ttu-id="820e2-129">**[自動構成スクリプト]** - ファイルを使用してプロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="820e2-129">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="820e2-130">構成ファイルが格納されている**プロキシ サーバーの URL** を入力します (たとえば、**http://proxy.contoso.com**)。</span><span class="sxs-lookup"><span data-stu-id="820e2-130">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="820e2-131">**[アドレス]** - プロキシ サーバーのアドレスを (IP アドレスとして) 入力します。</span><span class="sxs-lookup"><span data-stu-id="820e2-131">**Address** - Enter the proxy server address (as an IP address).</span></span>
- <span data-ttu-id="820e2-132">**[ポート番号]** - プロキシ サーバーに関連付けられているポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="820e2-132">**Port number** - Enter the port number associated with the proxy server.</span></span>
