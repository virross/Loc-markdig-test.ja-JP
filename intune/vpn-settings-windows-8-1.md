---
title: "Windows 8.1 デバイス向けの Intune の VPN 設定"
titleSuffix: Azure portal
description: "Windows 8.1 デバイスで VPN 接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eea15acd0e873a147b5f90fca095b028e78ed8b9
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="vpn-settings-for-windows-81-devices-in-microsoft-intune"></a><span data-ttu-id="63f9b-103">Microsoft Intune での Windows 8.1 デバイス向けの VPN 設定</span><span class="sxs-lookup"><span data-stu-id="63f9b-103">VPN settings for Windows 8.1 devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="63f9b-104">選択する設定によっては、以下の一覧に記載されている値の一部を構成できない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="63f9b-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <a name="base-vpn-settings"></a><span data-ttu-id="63f9b-105">基本 VPN 設定</span><span class="sxs-lookup"><span data-stu-id="63f9b-105">Base VPN settings</span></span>


- <span data-ttu-id="63f9b-106">**[Apply all settings to Windows 8.1 only (すべての設定を Windows 8.1 のみに適用する)]** - これは、Intune クラシック ポータルで構成できる設定です。</span><span class="sxs-lookup"><span data-stu-id="63f9b-106">**Apply all settings to Windows 8.1 only** - This is a setting you can configure in the Intune classic portal.</span></span> <span data-ttu-id="63f9b-107">Azure Portal では、この設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="63f9b-107">In the Azure portal, this setting cannot be changed.</span></span> <span data-ttu-id="63f9b-108">これを **[構成済み]** に設定すると、すべての設定が Windows 8.1 デバイスのみに適用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="63f9b-108">If this is set to **Configured**, any settings will only be applied to Windows 8.1 devices.</span></span> <span data-ttu-id="63f9b-109">**[未構成]** に設定されている場合、これらの設定は Windows 10 デバイスにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="63f9b-109">If set to **Not Configured**, these settings will also apply to Windows 10 devices.</span></span>
- <span data-ttu-id="63f9b-110">**[接続名]** - この接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-110">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="63f9b-111">エンド ユーザーがデバイスで利用可能な VPN 接続の一覧を参照するときに、この名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63f9b-111">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="63f9b-112">**[サーバー]** - デバイスの接続先とする 1 台以上の VPN サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-112">**Servers** - Add one or more VPN servers that devices will connect to.</span></span>
    - <span data-ttu-id="63f9b-113">**[追加]** - **[行の追加]** ブレードが開き、以下の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="63f9b-113">**Add** - Opens the **Add Row** blade where you can specify the following information:</span></span>
        - <span data-ttu-id="63f9b-114">**[説明]** - **Contoso VPN サーバー**のような、サーバーを表す名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-114">**Description** - Specify a descriptive name for the server like **Contoso VPN server**.</span></span>
        - <span data-ttu-id="63f9b-115">**[IP アドレスまたは FQDN]** - デバイスが接続する VPN サーバーの IP アドレスまたは完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-115">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="63f9b-116">例: **192.168.1.1**、**vpn.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="63f9b-116">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
        - <span data-ttu-id="63f9b-117">**[既定のサーバー]** - このサーバーを、デバイスで接続を確立するために使用する既定のサーバーとして有効にします。</span><span class="sxs-lookup"><span data-stu-id="63f9b-117">**Default server** - Enables this server as the default server that devices will use to establish the connection.</span></span> <span data-ttu-id="63f9b-118">既定のサーバーとして設定するサーバーの数は 1 台のみにしてください。</span><span class="sxs-lookup"><span data-stu-id="63f9b-118">Make sure to set only one server as the default.</span></span>
    - <span data-ttu-id="63f9b-119">**[インポート]** - 説明、IP アドレスまたは FQDN、既定のサーバーという形式でまとめられた、コンマ区切りのサーバーのリストを含むファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-119">**Import** - Browse to a file containing a comma-seperated list of servers in the format description, IP address or FQDN, Default server.</span></span> <span data-ttu-id="63f9b-120">**[OK]** を選択すると、これらが **[サーバー]** リストにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="63f9b-120">Choose **OK** to import these into the **Servers** list.</span></span>
    - <span data-ttu-id="63f9b-121">**[エクスポート]** - サーバーのリストをコンマ区切り値 (csv) ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="63f9b-121">**Export** - Exports the list of servers to a comma-seperated-values (csv) file.</span></span>

- <span data-ttu-id="63f9b-122">**[接続の種類]** - 以下のベンダーの一覧から VPN 接続の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-122">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
- <span data-ttu-id="63f9b-123">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="63f9b-123">**Check Point Capsule VPN**</span></span>
- <span data-ttu-id="63f9b-124">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="63f9b-124">**Dell SonicWALL Mobile Connect**</span></span>
- <span data-ttu-id="63f9b-125">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="63f9b-125">**F5 Edge Client**</span></span>
- <span data-ttu-id="63f9b-126">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="63f9b-126">**Pulse Secure**</span></span>

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- <span data-ttu-id="63f9b-127">**[ログイン グループまたはドメイン]** (Dell SonicWALL Mobile Connect のみ) - 接続先のログイン グループまたはドメインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-127">**Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.</span></span>

- <span data-ttu-id="63f9b-128">**[ロール]** (Pulse Secure のみ) - この接続に対するアクセス権を持つユーザー ロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-128">**Role** (Pulse Secure only) - Specify the name of the user role that has access to this connection.</span></span> <span data-ttu-id="63f9b-129">ユーザー ロールを使用して、個人の設定とオプションを定義し、特定のアクセス機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="63f9b-129">A user role defines personal settings and options, and it enables or disables certain access features.</span></span>

- <span data-ttu-id="63f9b-130">**[領域]** (Pulse Secure のみ) - 使用する認証領域の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-130">**Realm** (Pulse Secure only) - Specify the name of the authentication realm that you want to use.</span></span> <span data-ttu-id="63f9b-131">認証領域とは、接続の種類が [Pulse Secure] の場合に使用される認証リソースのグループを表します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-131">An authentication realm is a grouping of authentication resources that the Pulse Secure connection type uses.</span></span>


- <span data-ttu-id="63f9b-132">**[カスタム XML]** - VPN 接続を構成する任意のカスタム XML コマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-132">**Custom XML** - Specify any custom XML commands that configure the VPN connection.</span></span>

<span data-ttu-id="63f9b-133">**Pulse Secure の例:**</span><span class="sxs-lookup"><span data-stu-id="63f9b-133">**Example for Pulse Secure:**</span></span>

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

<span data-ttu-id="63f9b-134">**CheckPoint Mobile VPN の例:**</span><span class="sxs-lookup"><span data-stu-id="63f9b-134">**Example for CheckPoint Mobile VPN:**</span></span>
```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

<span data-ttu-id="63f9b-135">**Dell SonicWALL Mobile Connect の例:**</span><span class="sxs-lookup"><span data-stu-id="63f9b-135">**Example for Dell SonicWALL Mobile Connect:**</span></span>
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

<span data-ttu-id="63f9b-136">**F5 Edge Client の例:**</span><span class="sxs-lookup"><span data-stu-id="63f9b-136">**Example for F5 Edge Client:**</span></span>

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

<span data-ttu-id="63f9b-137">カスタムの XML コマンドの記述方法については、各製造元の VPN に関するマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f9b-137">Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.</span></span>


## <a name="proxy-settings"></a><span data-ttu-id="63f9b-138">プロキシの設定</span><span class="sxs-lookup"><span data-stu-id="63f9b-138">Proxy settings</span></span>

- <span data-ttu-id="63f9b-139">**[自動的にプロキシ設定を検出する]** - VPN サーバーが接続にプロキシ サーバーを必要とする場合は、デバイスで接続の設定を自動的に検出するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-139">**Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings.</span></span> <span data-ttu-id="63f9b-140">詳細については、Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f9b-140">For more information, see your Windows Server documentation.</span></span>
- <span data-ttu-id="63f9b-141">**[自動構成スクリプト]** - ファイルを使用してプロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-141">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="63f9b-142">構成ファイルが格納されている**プロキシ サーバーの URL** を入力します (たとえば、**http://proxy.contoso.com**)。</span><span class="sxs-lookup"><span data-stu-id="63f9b-142">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="63f9b-143">**[プロキシ サーバーを使用する]** - プロキシ サーバーの設定を手動で入力する場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="63f9b-143">**Use proxy server** - Enable this option if you want to manually enter the proxy server settings.</span></span>
    - <span data-ttu-id="63f9b-144">**[アドレス]** - プロキシ サーバーのアドレスを (IP アドレスとして) 入力します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-144">**Address** - Enter the proxy server address (as an IP address).</span></span>
    - <span data-ttu-id="63f9b-145">**[ポート番号]** - プロキシ サーバーに関連付けられているポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-145">**Port number** - Enter the port number associated with the proxy server.</span></span>
- <span data-ttu-id="63f9b-146">**[ローカル アドレスにはプロキシ サーバーを使用しない]** - VPN サーバーが接続にプロキシ サーバーを必要とする場合、指定したローカル アドレスに対してプロキシ サーバーを使用しないようにするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="63f9b-146">**Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</span></span> <span data-ttu-id="63f9b-147">詳細については、Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f9b-147">For more information, see your Windows Server documentation.</span></span>
