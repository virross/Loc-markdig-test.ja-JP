---
title: "Android デバイス向けの Intune Wi-Fi 設定"
titleSuffix: Azure portal
description: "Intune での Android デバイスと Android for Work デバイスの Wi-fi 接続設定の構成について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c74aa485618840176c7b88af5f123523b07c4480
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="wi-fi-settings-for-android-and-android-for-work-devices-in-microsoft-intune"></a><span data-ttu-id="a2cbc-103">Microsoft Intune での Android デバイスと Android for Work デバイスの Wi-fi 設定</span><span class="sxs-lookup"><span data-stu-id="a2cbc-103">Wi-Fi settings for Android and Android for Work devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a><span data-ttu-id="a2cbc-104">基本プロファイルとエンタープライズ プロファイル向けの Wi-Fi 設定</span><span class="sxs-lookup"><span data-stu-id="a2cbc-104">Wi-Fi settings for basic and enterprise profiles</span></span>

<span data-ttu-id="a2cbc-105">次の Wi-fi 設定は、Android デバイスと Android for Work デバイスの両方で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-105">The following Wi-Fi settings are available for both Android and Android for Work devices:</span></span>

- <span data-ttu-id="a2cbc-106">**[ネットワーク名]** - この Wi-Fi 接続の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-106">**Network name** - Enter a name for this Wi-Fi connection.</span></span> <span data-ttu-id="a2cbc-107">これは、ユーザーがデバイスで利用可能な接続の一覧を参照しているときに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-107">This is the name that users will see when they browse the list of available connections on their device.</span></span>
- <span data-ttu-id="a2cbc-108">**[SSID]** - サービス セット識別子の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-108">**SSID** - Short for service set identifier.</span></span> <span data-ttu-id="a2cbc-109">これは、デバイスの接続先となるワイヤレス ネットワークの実際の名前です。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-109">This is the real name of the wireless network that devices will connect to.</span></span> <span data-ttu-id="a2cbc-110">ただし、ユーザーが接続を選択したときにユーザーに表示されるのは、作成した上記のネットワーク名のみです。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-110">However, users only see the network name you created above when they choose the connection.</span></span>
- <span data-ttu-id="a2cbc-111">**[自動的に接続する]** - デバイスがこのネットワークの範囲内にある場合に必ず、デバイス接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-111">**Connect automatically** - Makes the device connect whenever it is in the range of this network.</span></span>
- <span data-ttu-id="a2cbc-112">**[非公開のネットワーク]** - デバイス上の使用可能なネットワークの一覧にこのネットワークが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-112">**Hidden network** - Prevents this network from being shown in the list of available networks on the device.</span></span>


## <a name="wi-fi-settings-for-enterprise-profiles-only"></a><span data-ttu-id="a2cbc-113">エンタープライズ プロファイルのみを対象とした Wi-Fi 設定</span><span class="sxs-lookup"><span data-stu-id="a2cbc-113">Wi-Fi settings for enterprise profiles only</span></span>

- <span data-ttu-id="a2cbc-114">**[EAP の種類]** - 次の中から、セキュリティで保護されたワイヤレス接続の認証に使用される拡張認証プロトコル (EAP) の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-114">**EAP type** - Choose the Extensible Authentication Protocol (EAP) type used to authenticate secured wireless connections from:</span></span>
    - <span data-ttu-id="a2cbc-115">**EAP-TLS**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-115">**EAP-TLS**</span></span>
    - <span data-ttu-id="a2cbc-116">**EAP-TTLS**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-116">**EAP-TTLS**</span></span>
    - <span data-ttu-id="a2cbc-117">**PEAP**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-117">**PEAP**</span></span>

### <a name="further-options-when-you-choose-an-eap-type"></a><span data-ttu-id="a2cbc-118">EAP の種類を選択したときの詳細オプション</span><span class="sxs-lookup"><span data-stu-id="a2cbc-118">Further options when you choose an EAP type</span></span>

#### <a name="server-trust"></a><span data-ttu-id="a2cbc-119">サーバー信頼</span><span class="sxs-lookup"><span data-stu-id="a2cbc-119">Server Trust</span></span>



|<span data-ttu-id="a2cbc-120">設定の名前</span><span class="sxs-lookup"><span data-stu-id="a2cbc-120">Setting name</span></span>|<span data-ttu-id="a2cbc-121">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a2cbc-121">More information</span></span>|<span data-ttu-id="a2cbc-122">次の場合に使用</span><span class="sxs-lookup"><span data-stu-id="a2cbc-122">Use when</span></span>|
|-------------|---------------|-----------|
|<span data-ttu-id="a2cbc-123">**証明書のサーバー名**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-123">**Certificate server names**</span></span>|<span data-ttu-id="a2cbc-124">信頼された証明機関 (CA) によって発行された証明書で使用される 1 つ以上の共通名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-124">Specify one or more common names used in the certificates issued by your trusted certificate authority (CA).</span></span> <span data-ttu-id="a2cbc-125">この情報を指定すると、この Wi-Fi ネットワークに接続したときに、エンド ユーザーのデバイスに表示される動的な信頼ダイアログをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-125">If you provide this information, you can bypass the dynamic trust dialog that is displayed on end users devices when they connect to this Wi-Fi network.</span></span>|<span data-ttu-id="a2cbc-126">EAP の種類が **EAP-TLS** または **EAP-TTLS**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-126">EAP type is **EAP-TLS** or **EAP-TTLS**</span></span>|
|<span data-ttu-id="a2cbc-127">**サーバー検証のためのルート証明書**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-127">**Root certificate for server validation**</span></span>|<span data-ttu-id="a2cbc-128">接続の認証に使用される信頼されたルート証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-128">Choose the trusted root certificate profile used to authenticate the connection.</span></span> |<span data-ttu-id="a2cbc-129">EAP の種類が **EAP-TLS**、**EAP-TTLS**、または **PEAP**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-129">EAP type is **EAP-TLS**, **EAP-TTLS**, or **PEAP**</span></span>|
|<span data-ttu-id="a2cbc-130">**ID プライバシー (外部 ID)**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-130">**Identity privacy (outer identity)**</span></span>|<span data-ttu-id="a2cbc-131">EAP ID 要求への応答で送信されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-131">Specify the text sent in response to an EAP identity request.</span></span> <span data-ttu-id="a2cbc-132">このテキストには任意の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-132">This text can be any value.</span></span> <span data-ttu-id="a2cbc-133">認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-133">During authentication, this anonymous identity is initially sent, and then followed by the real identification sent in a secure tunnel.</span></span>|<span data-ttu-id="a2cbc-134">EAP の種類が **PEAP**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-134">EAP type is **PEAP**</span></span>|


#### <a name="client-authentication"></a><span data-ttu-id="a2cbc-135">クライアント認証</span><span class="sxs-lookup"><span data-stu-id="a2cbc-135">Client Authentication</span></span>


|<span data-ttu-id="a2cbc-136">設定の名前</span><span class="sxs-lookup"><span data-stu-id="a2cbc-136">Setting name</span></span>|<span data-ttu-id="a2cbc-137">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a2cbc-137">More information</span></span>|<span data-ttu-id="a2cbc-138">次の場合に使用</span><span class="sxs-lookup"><span data-stu-id="a2cbc-138">Use when</span></span>|
|----------|--------------|----------|
|<span data-ttu-id="a2cbc-139">**クライアント認証に使用するクライアント証明書 (ID 証明書)**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-139">**Client certificate for client authentication (Identity certificate)**</span></span>|<span data-ttu-id="a2cbc-140">接続の認証に使用される SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-140">Choose the SCEP or PKCS certificate profile used to authenticate the connection.</span></span>|<span data-ttu-id="a2cbc-141">EAP の種類が **EAP-TLS**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-141">EAP type is **EAP-TLS**</span></span>|
|<span data-ttu-id="a2cbc-142">**認証方法**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-142">**Authentication method**</span></span>|<span data-ttu-id="a2cbc-143">次の中から、接続の認証方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-143">Select the authentication method for the connection:</span></span><br><span data-ttu-id="a2cbc-144">- **証明書**: ID 証明書であるクライアント証明書がサーバーに提供した、SCEP または PKCS を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-144">- **Certificates** to select the SCEP or PKCS the client certificate that is the identity certificate presented to the server.</span></span><br><br><span data-ttu-id="a2cbc-145">- **ユーザー名とパスワード**: 認証用の別の方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-145">- **Username and Password** to specify a different method for authentication.</span></span> <br><br><span data-ttu-id="a2cbc-146">**[ユーザー名とパスワード]** を選択した場合は、次を構成します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-146">If you selected **Username and Password**, configure:</span></span><br><br><span data-ttu-id="a2cbc-147">-  **EAP 以外の方法 (内部 ID)**: 次の中から接続を認証する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-147">-  **Non-EAP method (inner identity)**, then select how you will authenticate the connection from:</span></span><br><span data-ttu-id="a2cbc-148">- **なし**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-148">- **None**</span></span><br><span data-ttu-id="a2cbc-149">- **暗号化されていないパスワード (PAP)**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-149">- **Unencrypted password (PAP)**</span></span><br><span data-ttu-id="a2cbc-150">- **チャレンジ ハンドシェイク認証プロトコル (CHAP)**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-150">- **Challenge Handshake Authentication Protocol (CHAP)**</span></span><br><span data-ttu-id="a2cbc-151">- **Microsoft CHAP (MS-CHAP)**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-151">- **Microsoft CHAP (MS-CHAP)**</span></span><br><span data-ttu-id="a2cbc-152">- **Microsoft CHAP バージョン 2 (MS-CHAP v2)**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-152">- **Microsoft CHAP Version 2 (MS-CHAP v2)**</span></span><br><span data-ttu-id="a2cbc-153">使用できるオプションは、選択した EAP の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-153">The available options depend on the EAP type you selected.</span></span><br><br><span data-ttu-id="a2cbc-154">**および**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-154">**and**</span></span><br><br><span data-ttu-id="a2cbc-155">- **[ID プライバシー (外部 ID)]** - EAP ID 要求への応答で送信されるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-155">- **Identity privacy (outer identity)** - Specify the text sent in response to an EAP identity request.</span></span> <span data-ttu-id="a2cbc-156">このテキストには任意の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-156">This text can be any value.</span></span> <span data-ttu-id="a2cbc-157">認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-157">During authentication, this anonymous identity is initially sent, and then followed by the real identification sent in a secure tunnel.</span></span>|<span data-ttu-id="a2cbc-158">EAP の種類が **EAP-TTLS** または **PEAP**</span><span class="sxs-lookup"><span data-stu-id="a2cbc-158">EAP type is **EAP-TTLS** or **PEAP**</span></span>|
