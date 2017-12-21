---
title: "iOS デバイス向けの Intune Wi-Fi 設定"
titleSuffix: Azure portal
description: "iOS デバイスで Wi-Fi 接続を構成するために使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89229a5e-3421-4221-a62f-fa800620cc0d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da4d6cf5c9863e2c471c3e6d3b119dce614528ce
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune での iOS デバイス向けの Wi-Fi 設定

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>基本プロファイルとエンタープライズ プロファイル向けの Wi-Fi 設定

- **[ネットワーク名]** - この Wi-Fi 接続の名前を入力します。 これは、ユーザーがデバイスで利用可能な接続の一覧を参照しているときに表示される名前です。
- **[SSID]** - サービス セット識別子の短縮形です。 これは、デバイスの接続先となるワイヤレス ネットワークの実際の名前です。 ただし、ユーザーが接続を選択したときにユーザーに表示されるのは、作成した上記のネットワーク名のみです。
- **[自動的に接続する]** - デバイスがこのネットワークの範囲内にある場合に必ず、デバイス接続を確立します。
- **[非公開のネットワーク]** - デバイス上の使用可能なネットワークの一覧にこのネットワークが表示されないようにします。
- **[プロキシ設定]** - 次から選択します。
    - **[なし]** - プロキシ設定は構成されません。
    - **[手動]** - **プロキシ サーバーのアドレス**を (IP アドレスとして) 入力します。これは**ポート番号**に関連付けられています。
    - **[自動]** - ファイルを使用してプロキシ サーバーを構成します。 構成ファイルが格納されている**プロキシ サーバーの URL** を入力します (たとえば、**http://proxy.contoso.com**)。

## <a name="wi-fi-settings-for-basic-profiles-only"></a>基本プロファイルのみを対象とした Wi-Fi 設定

- **[セキュリティの種類]** - Wi-Fi ネットワークへの認証に使用するセキュリティ プロトコルを選択します。
    - **[オープン (認証なし)]** - このオプションは、ネットワークがセキュリティで保護されていない場合にのみ使用します。
    - **WPA/WPA2 - 個人用**
    - **4**

## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>エンタープライズ プロファイルのみを対象とした Wi-Fi 設定

- **[EAP の種類]** - 次の中から、セキュリティで保護されたワイヤレス接続の認証に使用される拡張認証プロトコル (EAP) の種類を選択します。
    - **EAP-FAST**
    - **EAP-SIM**
    - **EAP-TLS**
    - **EAP-TTLS**
    - **LEAP**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>EAP の種類を選択したときの詳細オプション


|設定の名前|詳細情報|次の場合に使用|
|--------------|-------------|----------|
|**Protected Access Credential (PAC) の設定**|Protected Access Credential を使用してクライアントと認証サーバーとの間で認証済みトンネルを確立する場合に選択します 次のいずれかを選択します。<br>- **[PAC の使用]** - "既存の PAC ファイルを使用" が使用されます (存在する場合)。<br>- **[PAC の使用とプロビジョニング]** - PAC ファイルをデバイスにプロビジョニングします。<br>- **[匿名による PAC のプロビジョニング]** - PAC ファイルをデバイスにプロビジョニングして、サーバーを認証せずに PAC ファイルを確実にプロビジョニングします。|EAP の種類が **EAP-FAST**|

#### <a name="server-trust"></a>サーバー信頼


|設定の名前|詳細情報|次の場合に使用|
|--------------|-------------|----------|
|**証明書のサーバー名**|信頼された証明機関 (CA) によって発行された証明書で使用される 1 つ以上の共通名を指定します。 この情報を指定すると、この Wi-Fi ネットワークに接続したときに、エンド ユーザーのデバイスに表示される動的な信頼ダイアログをバイパスできます。|EAP の種類が **EAP-TLS**、**EAP-TTLS**、または **PEAP**。|
|**サーバー検証のためのルート証明書**|接続の認証に使用される信頼されたルート証明書プロファイルを選択します。 |EAP の種類が **EAP-TLS**、**EAP-TTLS**、または **PEAP**|
|**ID プライバシー (外部 ID)**|EAP ID 要求への応答で送信されるテキストを指定します。 このテキストには任意の値を指定できます。 認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。|EAP の種類が **PEAP**|


#### <a name="client-authentication"></a>クライアント認証


|設定の名前|詳細情報|次の場合に使用|
|--------------|-------------|----------|
|**クライアント認証に使用するクライアント証明書 (ID 証明書)**|接続の認証に使用される SCEP または PKCS 証明書プロファイルを選択します。|EAP の種類が **EAP-TLS**|
|**認証方法**|次の中から、接続の認証方法を選択します。<br>- **証明書**: ID 証明書であるクライアント証明書がサーバーに提供した、SCEP または PKCS を選択します。<br><br>- **ユーザー名とパスワード**: 認証用の別の方法を指定します。 <br><br>**[ユーザー名とパスワード]** を選択した場合は、次を構成します。<br><br>-  **EAP 以外の方法 (内部 ID)**: 次の中から接続を認証する方法を選択します。<br>- **なし**<br>- **暗号化されていないパスワード (PAP)**<br>- **チャレンジ ハンドシェイク認証プロトコル (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP バージョン 2 (MS-CHAP v2)**<br>使用できるオプションは、選択した EAP の種類によって異なります。<br><br>**および**<br><br>- **[ID プライバシー (外部 ID)]** - EAP ID 要求への応答で送信されるテキストを指定します。 このテキストには任意の値を指定できます。 認証時に、この匿名の ID が最初に送信され、その後、セキュリティで保護されたトンネルで実際の ID が送信されます。|EAP の種類が **EAP-TTLS** または *
