---
title: "Android デバイス向けの Intune VPN 設定"
titlesuffix: Azure portal
description: "Android デバイスでの VPN 接続の構成に使用できる Intune 設定について説明します"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 455d8f83e04bf72938316b9511e4898df9652808
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a><span data-ttu-id="8b714-103">Microsoft Intune での Android デバイス向けの VPN 設定</span><span class="sxs-lookup"><span data-stu-id="8b714-103">VPN settings for Android devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="8b714-104">Intune 管理者は、次のプラットフォーム向けの VPN 設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="8b714-104">As an Intune admin, you can configure VPN settings for the following platforms:</span></span>

- [<span data-ttu-id="8b714-105">Android</span><span class="sxs-lookup"><span data-stu-id="8b714-105">Android</span></span>](#android-vpn-settings)
- [<span data-ttu-id="8b714-106">Android for Work</span><span class="sxs-lookup"><span data-stu-id="8b714-106">Android for Work</span></span>](#android-for-work-vpn-settings)

<span data-ttu-id="8b714-107">選択する設定によっては、以下の一覧に記載されている値の一部を構成できない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8b714-107">Depending on the settings you choose, not all values listed below are configurable.</span></span>

## <a name="android-vpn-settings"></a><span data-ttu-id="8b714-108">Android の VPN 設定</span><span class="sxs-lookup"><span data-stu-id="8b714-108">Android VPN settings</span></span>
<span data-ttu-id="8b714-109">**[接続名]** - この接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b714-109">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="8b714-110">エンド ユーザーがデバイスで利用可能な VPN 接続の一覧を参照するときに、この名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b714-110">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="8b714-111">**[IP アドレスまたは FQDN]** - デバイスが接続する VPN サーバーの IP アドレスまたは完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b714-111">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="8b714-112">例: **192.168.1.1**、**vpn.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="8b714-112">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="8b714-113">**[認証方法]** - VPN サーバーに対するデバイスの認証方法として、以下のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b714-113">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="8b714-114">**[証明書]** - 接続を認証するために事前に作成した SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b714-114">**Certificates** - Select a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="8b714-115">証明書プロファイルの詳細については、[証明書の構成方法](certificates-configure.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b714-115">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="8b714-116">**[ユーザー名とパスワード]** - エンド ユーザーは VPN サーバーにログインするためにユーザー名とパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b714-116">**Username and password** - End users must supply a user name and password to log into the VPN server.</span></span>
- <span data-ttu-id="8b714-117">**[接続の種類]** - 以下のベンダーの一覧から VPN 接続の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b714-117">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="8b714-118">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="8b714-118">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="8b714-119">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="8b714-119">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="8b714-120">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="8b714-120">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="8b714-121">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="8b714-121">**F5 Edge Client**</span></span>
    - <span data-ttu-id="8b714-122">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="8b714-122">**Pulse Secure**</span></span>
    - <span data-ttu-id="8b714-123">**Citrix**</span><span class="sxs-lookup"><span data-stu-id="8b714-123">**Citrix**</span></span>

- <span data-ttu-id="8b714-124">**[指紋]** (Check Point Capsule VPN のみ) - 信頼できる VPN サーバーであることを確認するために使用される文字列を指定します (たとえば、"Contoso 指紋コード")。</span><span class="sxs-lookup"><span data-stu-id="8b714-124">**Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted.</span></span> <span data-ttu-id="8b714-125">指紋をクライアントに送信することにより、クライアントは、接続するときに同じ指紋を示すすべてのサーバーを信頼します。</span><span class="sxs-lookup"><span data-stu-id="8b714-125">A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting.</span></span> <span data-ttu-id="8b714-126">デバイスにまだ指紋がない場合、接続先の VPN サーバーを信頼するように促すメッセージと共にその指紋が表示されます (ユーザーは手動で指紋を検証し、接続先を信頼することを選択する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="8b714-126">If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint (The user manually verifies the fingerprint and chooses trust to connect).</span></span>
- <span data-ttu-id="8b714-127">**[Citrix VPN 属性に対してキーと値を入力します]** (Citrix のみ) - VPN 接続のプロパティを構成するために、Citrix から提供されたキーと値のペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="8b714-127">**Enter key and value pairs for the Citrix VPN attributes** (Citrix only) - Enter key and value pairs, provided by Citrix, to configure the properties of the VPN connection.</span></span>

## <a name="android-for-work-vpn-settings"></a><span data-ttu-id="8b714-128">Android for Work の VPN 設定</span><span class="sxs-lookup"><span data-stu-id="8b714-128">Android for Work VPN settings</span></span>

<span data-ttu-id="8b714-129">**[接続名]** - この接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8b714-129">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="8b714-130">エンド ユーザーがデバイスで利用可能な VPN 接続の一覧を参照するときに、この名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b714-130">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="8b714-131">**[IP アドレスまたは FQDN]** - デバイスが接続する VPN サーバーの IP アドレスまたは完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b714-131">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="8b714-132">例: **192.168.1.1**、**vpn.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="8b714-132">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="8b714-133">**[認証方法]** - VPN サーバーに対するデバイスの認証方法として、以下のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b714-133">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="8b714-134">**[証明書]** - 接続を認証するために事前に作成した SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b714-134">**Certificates** - Select a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="8b714-135">証明書プロファイルの詳細については、[証明書の構成方法](certificates-configure.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b714-135">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="8b714-136">**[ユーザー名とパスワード]** - エンド ユーザーは VPN サーバーにログインするためにユーザー名とパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b714-136">**Username and password** - End users must supply a user name and password to log into the VPN server.</span></span>
- <span data-ttu-id="8b714-137">**[接続の種類]** - 以下のベンダーの一覧から VPN 接続の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b714-137">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="8b714-138">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="8b714-138">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="8b714-139">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="8b714-139">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="8b714-140">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="8b714-140">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="8b714-141">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="8b714-141">**F5 Edge Client**</span></span>
    - <span data-ttu-id="8b714-142">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="8b714-142">**Pulse Secure**</span></span>

- <span data-ttu-id="8b714-143">**分割トンネリング** - 他のトラフィックがインターネットを使用しているときに、特定の Web トラフィックが VPN 接続を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8b714-143">**Split tunneling** - Enable to let certain web traffic use the VPN connection when the VPN while other traffic uses the internet.</span></span> <span data-ttu-id="8b714-144">VPN がアクティブな場合にすべてのトラフィックで VPN を使用するには、この設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8b714-144">Disable this setting if you want all traffic to use the VPN when active.</span></span>
