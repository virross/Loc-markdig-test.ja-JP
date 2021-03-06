---
title: "VPN 接続"
description: "組織内のユーザーとデバイスに VPN 設定を展開するには、VPN プロファイルを使用します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e22b4e65a4e943075eb0363c625d73c417c13462
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="vpn-connections-in-microsoft-intune"></a>VPN connections in Microsoft Intune (Microsoft Intune での VPN 接続)

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

仮想プライベート ネットワーク (VPN) を使用すると、会社のユーザーが社内ネットワークにリモート アクセスする際にセキュリティで保護することができます。 デバイスは、*VPN 接続プロファイル*を使用して VPN サーバーとの接続を開始します。 Microsoft Intune の *VPN プロファイル*を使用して、VPN 設定を組織内のユーザーとデバイスに展開し、社内ネットワークに簡単かつ安全に接続できるようにします。

たとえば、すべての iOS デバイスに対して、企業ネットワーク上のファイル共有に接続するために必要な設定をプロビジョニングするとします。 企業ネットワークに接続するために必要な設定を含む VPN プロファイルを作成し、そのプロファイルを iOS デバイスを使用しているすべてのユーザーに展開します。 使用できるネットワークの一覧に VPN 接続が表示されるので、ユーザーは最小限の労力で接続できます。

次の種類のデバイスに対して VPN プロファイルを構成できます。

* Android 4 以降が実行されているデバイス
* Android for Work デバイス
* iOS 8.0 以降を実行するデバイス
* Mac OS X 10.9 以降を実行するデバイス
* Windows 8.1 以降を実行する登録済みのデバイス
* Windows Phone 8.1 以降が実行されているデバイス
* Windows 10 デスクトップまたは Windows 10 Mobile が実行されているデバイス

VPN プロファイルの構成オプションは、選択したデバイスの種類によって異なります。

## <a name="vpn-connection-types"></a>VPN 接続の種類

Intune では、次の接続の種類を使用する VPN プロファイルを作成できます。


接続の種類 |iOS および Mac OS X  |Android と Android for Work|Windows 8.1|Windows RT 8.1|Windows Phone 8。1|Windows 10 デスクトップおよび Windows 10 Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|はい |はい   |[いいえ]    |[いいえ]  |[いいえ]    | ○ (OMA-URI、Windows 10 Mobile のみ)|     
Cisco (IPsec)|はい |はい   |[いいえ]  |[いいえ]  |[いいえ] | [いいえ]|
Citrix|はい |○ (Android のみ)   |[いいえ]  |[いいえ]  |[いいえ] | [いいえ]|
Pulse Secure|はい  |はい |はい   |はい  |はい| はい|        
F5 Edge Client|はい |はい |はい |はい  |   はい |  はい|   
Dell SonicWALL Mobile Connect|はい |はい |はい |はい |はい |はい|         
CheckPoint Mobile VPN|はい |はい |はい |はい|はい|はい|
Microsoft SSL (SSTP)|[いいえ] |[いいえ] |[いいえ] |[いいえ]|[いいえ]|VPNv1 OMA-URI*|
Microsoft 自動|[いいえ] |[いいえ] |[いいえ] |[いいえ]|○ (OMA-URI)|はい|
IKEv2|iOS カスタム プロファイル|[いいえ] |[いいえ] |[いいえ]|○ (OMA-URI)|はい|
PPTP|iOS カスタム プロファイル|[いいえ] |[いいえ] |[いいえ]|[いいえ]|はい|
L2TP|iOS カスタム プロファイル|[いいえ] |[いいえ] |[いいえ]|○ (OMA-URI)|はい|

\* Windows 10 用に使用できるその他の設定を使用しない場合。

> [!IMPORTANT]
> デバイスにデプロイされた VPN プロファイルを使用する前に、プロファイル用の該当する VPN アプリをインストールする必要があります。 「[Microsoft Intune でアプリを展開する](deploy-apps-in-microsoft-intune.md)」の情報を参考にして、Intune を使って該当するアプリを展開してください。  

 「[VPN プロファイルのカスタム構成](create-custom-vpn-profiles.md)」では、URI 設定を使用してカスタム VPN プロファイルを作成する方法について説明されています。     

## <a name="methods-of-securing-vpn-profiles"></a>VPN プロファイルをセキュリティで保護する方法

VPN プロファイルは、さまざまな製造元から提供される多くの異なる接続の種類およびプロトコルに対応しています。 これらの接続は、通常、次の 2 つの方法のどちらかを使用してセキュリティで保護されます。

### <a name="certificates"></a>証明書

VPN プロファイルを作成するときに、Intune で事前に作成した SCEP または .PFX の証明書プロファイルを選択します。 これは ID 証明書と呼ばれます。 ユーザーのデバイスが接続を許可されていることを示すために作成した信頼済み証明書プロファイル (または、*ルート証明書*) に対して認証を行うために使用されます。 信頼できる証明書は、VPN 接続を認証するコンピューター (通常は VPN サーバー) に展開されます。

Intune で証明書プロファイルを作成および使用する方法の詳細については、「[証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。

### <a name="user-name-and-password"></a>ユーザー名とパスワード

ユーザーは、ユーザー名とパスワードを提供することにより、VPN サーバーに対して認証を行います。

## <a name="create-a-vpn-profile"></a>VPN プロファイルの作成

1. [Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]**  >  **[ポリシーの追加]** を選択します。
2. 関連するデバイスの種類を展開して、新しいポリシーのテンプレートを選び、そのデバイスの VPN プロファイルを選びます。
    * **VPN プロファイル (Android 4 以降)**
    * **VPN プロファイル (Android for Work)**
    * **VPN プロファイル (iOS 8.0 以降)**
    * **VPN プロファイル (Mac OS X 10.9 以降)**
    * **VPN プロファイル (Windows 8.1 以降)**
    * **VPN プロファイル (Windows Phone 8.1 以降)**
    * **VPN プロファイル (Windows 10 デスクトップおよび Windows 10 Mobile 以降)**

   カスタム VPN プロファイル ポリシーのみを作成および展開できます。 推奨設定はありません。

> [!Note]
> Android for Work デバイス用の VPN プロファイルを使用すると、デバイスの仕事用プロファイルにインストールされているアプリに対してのみ VPN 接続が有効になります。
>
> VPN 接続の一部の種類では、Android for Work デバイス用にアプリごとの VPN をサポートし、さらに Intune によって配布されるアプリに対してアプリごとの VPN を有効にすることができます。  

3. 次の表を参考に、VPN プロファイル設定を構成してください。

|                                                    設定の名前                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                     詳細情報                                                                                                                                                                                                                                                                                                                                                                                                                     |
|---------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                <strong>名前</strong>                                                |                                                                                                                                                                                                                                                                                                                                                                                  Intune コンソールで VPN プロファイルを識別するための一意の名前を入力します。                                                                                                                                                                                                                                                                                                                                                                                  |
|                                            <strong>説明</strong>                                             |                                                                                                                                                                                                                                                                                                                                                               VPN プロファイルの概要を示す簡単な説明と、VPN プロファイルを見つけるのに役立つその他の関連情報を入力します。                                                                                                                                                                                                                                                                                                                                                                |
|                              <strong>(ユーザーに表示する) VPN 接続名</strong>                              |                                                                                                                                                                                                                                                                                                                                                           VPN プロファイルの名前を指定します。 これは、ユーザーのデバイスで利用可能な VPN 接続の一覧に表示される名前です。                                                                                                                                                                                                                                                                                                                                                            |
|                                          <strong>接続の種類</strong>                                           |                                                                                                                                                                                                                                                     VPN プロファイルで使用する接続の種類を <strong>[Cisco AnyConnect]</strong> (Windows 8.1 または Windows Phone 8.1 では使用できません)、<strong>[Pulse Secure]</strong>、<strong>[Citrix]</strong>、<strong>[F5 Edge Client]</strong>、<strong>[Dell SonicWALL Mobile Connect]</strong>、<strong>[CheckPoint Mobile VPN]</strong> の中から選択します。                                                                                                                                                                                                                                                     |
|                                       <strong>VPN サーバーの説明</strong>                                       |                                                                                                                                                                                                                                                                                 デバイスが接続する VPN サーバーの説明を指定します。 例: <strong>Contoso VPN サーバー</strong>。 接続の種類が <strong>[F5 Edge Client]</strong> の場合、<strong>[サーバーの一覧]</strong> フィールドを使用して、サーバーの説明と IP アドレスの一覧を指定します。                                                                                                                                                                                                                                                                                  |
|                                     <strong>サーバーの IP アドレスまたは FQDN</strong>                                      |                                                                                                                                                                                                                                                   デバイスが接続する VPN サーバーの IP アドレスまたは完全修飾ドメイン名を指定します。 例: <strong>192.168.1.1</strong>、<strong>vpn.contoso.com</strong>。接続の種類が <strong>[F5 Edge Client]</strong> の場合、<strong>[サーバーの一覧]</strong> フィールドを使用して、サーバーの説明と IP アドレスの一覧を指定します。                                                                                                                                                                                                                                                    |
|                                            <strong>サーバーの一覧</strong>                                             |                                                                                                                                                                                                                                                                                              <strong>[追加]</strong> を選択して、VPN 接続に使用する新しい VPN サーバーを追加します。 また、接続の既定のサーバーを指定することもできます。 このオプションは、接続の種類が <strong>[F5 Edge Client]</strong> の場合にのみ表示されます。                                                                                                                                                                                                                                                                                              |
|                        <strong>VPN 接続を介してすべてのネットワーク トラフィックを送信する</strong>                         |                                                                                                                                                                                                                                  このオプションを選択した場合、すべてのネットワーク トラフィックが VPN 接続を介して送信されます。 このオプションを選択しない場合、クライアントは、サード パーティの VPN サーバーへの接続で分割トンネリングのルートを動的にネゴシエートします。 企業ネットワークへの接続だけが VPN トンネル経由で送信されます。 インターネット上のリソースに接続するときは、VPN トンネリングは使用されません。                                                                                                                                                                                                                                   |
|                                       <strong>認証方法</strong>                                        |                                                                                                                                                                                                                                                           VPN 接続で使用する認証方法を選択します: <strong>[証明書]</strong> または <strong>[ユーザー名とパスワード]</strong> (<strong>[ユーザー名とパスワード]</strong> は、接続の種類が [Cisco AnyConnect] の場合は使用できません)。<strong>[認証方法]</strong> オプションは、Windows 8.1 では使用できません。                                                                                                                                                                                                                                                            |
|                            <strong>ログオンのたびにユーザーの資格情報を記憶する</strong>                             |                                                                                                                                                                                                                                                                                                                                             ユーザーの資格情報を記憶し、接続が確立されるたびにユーザーが資格情報を入力する必要を省くには、このオプションを選択します。                                                                                                                                                                                                                                                                                                                                             |
|            <strong>クライアント認証用のクライアント証明書 (ID 証明書) を選択する</strong>            |                                                                                                                                                                                                                        事前に作成した、VPN 接続の認証に使用するクライアント SCEP 証明書を選択します。 Intune で証明書プロファイルを使用する方法の詳細については、[証明書プロファイルを使用したリソースへのアクセスのセキュリティ保護](secure-resource-access-with-certificate-profiles.md)に関する記事を参照してください。 このオプションは、認証方法が <strong>[証明書]</strong> の場合にのみ表示されます。                                                                                                                                                                                                                        |
|                                                <strong>ロール</strong>                                                |                                                                                                                                                                                                                                                                             この接続に対するアクセス権を持つユーザー ロールの名前を指定します。 ユーザー ロールを使用して、個人の設定とオプションを定義し、特定のアクセス機能を有効または無効にします。 このオプションは、接続の種類が <strong>[Pulse Secure]</strong> または <strong>[Citrix]</strong> の場合にのみ表示されます。                                                                                                                                                                                                                                                                             |
|                                               <strong>領域</strong>                                                |                                                                                                                                                                                                                                                                      使用する認証領域の名前を指定します。 認証領域とは、接続の種類が [Pulse Secure] または [Citrix] の場合に使用される認証リソースのグループを表します。 このオプションは、接続の種類が <strong>[Pulse Secure]</strong> または <strong>[Citrix]</strong> の場合にのみ表示されます。                                                                                                                                                                                                                                                                      |
|                                       <strong>ログイン グループまたはドメイン</strong>                                        |                                                                                                                                                                                                                                                                                                                                   接続するログイン グループまたはドメインの名前を指定します。 このオプションは、接続の種類が <strong>[Dell SonicWALL Mobile Connect]</strong> の場合にのみ表示されます。                                                                                                                                                                                                                                                                                                                                   |
|                                            <strong>指紋</strong>                                             |                                                                                                                   VPN サーバーが信頼できることを確認するために使用する文字列を指定します (たとえば、"Contoso 指紋コード")。 指紋をクライアントに送信することにより、クライアントは、接続するときに同じ指紋を示すすべてのサーバーを信頼します。 デバイスにまだ指紋が設定されていない場合、デバイスは指紋を表示すると共に、接続先の VPN サーバーを信頼するようにユーザーを促します (ユーザーは手動で指紋を検証し、<strong>[信頼する]</strong> を選択して接続します)。このオプションは、接続の種類が <strong>[CheckPoint Mobile VPN]</strong> の場合にのみ表示されます。                                                                                                                    |
|                                            <strong>アプリ VPN ごと</strong>                                             |                                                                                                                                                                                                                                                           VPN 接続を iOS または Mac OS X アプリに関連付けて、アプリを実行すると接続が開かれるようにする場合は、このオプションを選びます。 ソフトウェアを展開するときに VPN プロファイルをアプリに関連付けることができます。 詳細については、「[Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md)」 (Microsoft Intune でアプリを展開する) を参照してください。                                                                                                                                                                                                                                                            |
|                                           <strong>オンデマンド VPN</strong>                                            |                                                                                                                                                                                                                                                                                                                                      iOS 8.0 以降のデバイスではオンデマンド VPN を設定することができます。 この設定手順は、「[iOS デバイス向けのオンデマンド VPN](#on-demand-vpn-for-ios-devices)」に記載されています。                                                                                                                                                                                                                                                                                                                                       |
|    <strong>プロキシ設定を自動的に検出する</strong> (iOS、Mac OS X、Windows 8.1、Windows Phone 8.1 のみ)    |                                                                                                                                                                                                                                                                                                                      VPN サーバーが接続にプロキシ サーバーを必要とする場合は、デバイスで接続の設定を自動的に検出するかどうかを指定します。 詳細については、Windows Server のマニュアルを参照してください。                                                                                                                                                                                                                                                                                                                       |
|    <strong>自動構成スクリプトを使用する</strong> (iOS、Mac OS X、Windows 8.1、Windows Phone 8.1 のみ)     |                                                                                                                                                                                                                                                                                   VPN サーバーが接続にプロキシ サーバーを必要とする場合は、自動構成スクリプトを使用して設定を定義し、設定が含まれているファイルへの URL を指定するかどうかを指定します。 詳細については、Windows Server のマニュアルを参照してください。                                                                                                                                                                                                                                                                                   |
|             <strong>プロキシ サーバーを使用する</strong> (iOS、Mac OS X、Windows 8.1、Windows Phone 8.1 のみ)              |                                                                                                                                                                                                                                                                                                                    VPN サーバーが接続にプロキシ サーバーを必要とする場合は、このオプションを選択し、プロキシ サーバーのアドレスとポート番号を指定します。 詳細については、Windows Server のマニュアルを参照してください。                                                                                                                                                                                                                                                                                                                     |
| <strong>ローカル アドレスのプロキシ設定をバイパスする</strong> (iOS、Mac OS X、Windows 8.1、Windows Phone 8.1 のみ) |                                                                                                                                                                                                                                                                                                             VPN サーバーが接続にプロキシ サーバーを必要とする場合、指定したローカル アドレスに対してプロキシ サーバーを使用しないようにするには、このオプションを選択します。 詳細については、Windows Server のマニュアルを参照してください。                                                                                                                                                                                                                                                                                                              |
|                <strong>カスタム XML</strong> (Windows 8.1 以降および Windows Phone 8.1 以降)                 | VPN 接続を構成するカスタムの XML コマンドを指定します。 <strong>[Pulse Secure]</strong> の例: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;。 <strong>[CheckPoint Mobile VPN]</strong> の例: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;。 <strong>[Dell SonicWALL Mobile Connect]</strong> の例: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;。 <strong>[F5 Edge Client]</strong> の例: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential/&gt;&lt;/f5-vpn-conf&gt;。 カスタムの XML コマンドの記述方法については、各製造元の VPN に関するマニュアルを参照してください。 |
|                          <strong>DNS サフィックス検索一覧</strong> (Windows Phone 8.1 のみ)                           |                                                                                                                                                                                             各行に 1 つずつ DNS サフィックスを指定します。 短い名前を使用して Web サイトに接続するときに、指定した各 DNS サフィックスが検索されます。 たとえば、<strong>domain1.contoso.com</strong> と <strong>domain2.contoso.com</strong> の DNS サフィックスを指定して URL <strong>http://mywebsite</strong> にアクセスすると、URL <strong>http://mywebsite.domain1.contoso.com</strong> と <strong>http://mywebsite.domain2.contoso.com</strong> が検索されます。                                                                                                                                                                                              |
|            <strong>企業の Wi-Fi ネットワークに接続しているときは VPN をバイパスする</strong> (Windows Phone 8.1 のみ)             |                                                                                                                                                                                                                                                                                                                                                            デバイスが企業の Wi-Fi ネットワークに接続しているときは VPN 接続を使用しないことを指定するには、このオプションを選択します。                                                                                                                                                                                                                                                                                                                                                             |
|              <strong>家庭の Wi-Fi ネットワークに接続しているときは VPN をバイパスする</strong> (Windows Phone 8.1 のみ)              |                                                                                                                                                                                                                                                                                                                                                               デバイスが家庭の Wi-Fi ネットワークに接続しているときは VPN 接続を使用しないことを指定するには、このオプションを選択します。                                                                                                                                                                                                                                                                                                                                                               |

次の追加の設定は、Windows 10 デスクトップおよび Mobile デバイスで利用可能です。


|              設定の名前              |                                                                                                                                                                     詳細情報                                                                                                                                                                     |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <strong>ネットワーク トラフィック規則</strong> | VPN 接続に対して有効にするプロトコル、ローカルおよびリモートのポート、およびアドレス範囲を設定します。 ネットワーク トラフィック規則を作成しない場合は、すべてのプロトコル、ポート、およびアドレス範囲が有効になります。 規則を作成すると、その規則で指定したプロトコル、ポート、およびアドレス範囲だけが、VPN 接続で使用されます。 |
|        <strong>ルート</strong>         |                                                                                                                                                     VPN 接続を使用するルートを選択します。                                                                                                                                                     |
|      <strong>DNS サーバー</strong>      |                                                                                                                                接続が確立された後に VPN 接続で使用する DNS サーバーを選択します。                                                                                                                                 |
|    <strong>関連付けられているアプリ</strong>    |                                                           VPN 接続を自動的に使用するアプリの一覧を指定します。 アプリ ID は、アプリの種類によって決まります。 ユニバーサル アプリの場合、パッケージのファミリ名を指定します。 デスクトップ アプリの場合、アプリのファイル パスを指定します。                                                           |

> [!IMPORTANT]
> アプリごとの VPN の構成で使用するためにコンパイルするアプリのすべてのリストをセキュリティで保護することをお勧めします。 承認されていないユーザーが変更したリストをアプリごとの VPN アプリ リストにインポートすると、アクセス権のないアプリへの VPN アクセスが承認される可能性があります。 アプリ リストをセキュリティで保護する 1 つの方法は、アクセス制御リスト (ACL) を使用することです。

企業の境界設定を使用する必要がある例として、次のような状況が考えられます。 リモート デスクトップ用のみに VPN を有効にする場合、プロトコル番号 27 のトラフィックを外部ポート 3996 で許可するネットワーク トラフィック規則を作成します。 これにより、その他のトラフィックでは、VPN が使用されません。

また、使用している VPN 接続の種類では、分割トンネリングにおけるトラフィックの処理方法の定義が許可されていない場合にも、企業の境界のルート定義が役立ちます。 この場合は、**[ルート]** を使用して VPN を使用するルートを一覧表示できます。

Windows 10 デバイスの VPN の使用を特定のアプリのみに制限するには、カスタム OMA-URI 設定を作成します。

**[ポリシー]** ワークスペースの **[構成ポリシー]** ノードに新しいポリシーが表示されます。

### <a name="on-demand-vpn-for-ios-devices"></a>iOS デバイス向けのオンデマンド VPN
iOS 8.0 以降のデバイスではオンデマンド VPN を構成することができます。

> [!NOTE]
>  
> アプリごとの VPN とオンデマンド VPN を同じポリシーで使用することはできません。

1. ポリシーの構成ページで、**[この VPN 接続に関するオンデマンド ルール]** を見つけます。 列のラベルには **[一致]** (ルールによって確認される条件)、および **[アクション]** (条件が一致した場合にポリシーによってトリガーされるアクション) があります。
2. **[追加]** を選択してルールを作成します。 ルールで設定可能な一致条件には 2 つの種類があります。 ルールごとに構成できるのはこれらの種類のうち 1 つのみです。
   - **SSID** - ワイヤレス ネットワークを参照します。
   - **DNS 検索ドメイン** - 完全修飾名 (*team. corp.contoso.com* など) を使用するか、*contoso.com* などのドメイン (*.contoso.com* を使用するのと同等) を使用できます。
3. オプション: URL 文字列プローブ (ルールによってテストとして使用される URL) を入力します。 このプロファイルがインストールされているデバイスがリダイレクトなしでこの URL にアクセスできる場合は、VPN が確立され、デバイスが接続先の URL に接続されます。 ユーザーには、URL 文字列プローブ サイトは表示されません。 URL 文字列プローブの例としては、VPN への接続前にデバイスのポリシー準拠を確認する監査 Web サーバーのアドレスがあります。 別の例としては、デバイスを VPN 経由でターゲット URL に接続する前に、サイトに接続する VPN の機能をテストする URL があります。
4. 次のアクションのうちいずれかを選択します。
   - **接続**
   - **[接続の評価]**: 次の 3 種類の設定があります。a.  **[ドメインのアクション]** - **[必要な場合に接続する]** または **[接続しない]** を選択します。b.  **[ドメインのコンマ区切りリスト]** - これは、**[ドメインのアクション]** で **[必要な場合に接続する]** を選択した場合にのみ構成します。c.  **[必要な URL 文字列プローブ]** - HTTP または HTTPS (優先) URL (*https://vpntestprobe.contoso.com* など)。ルールにより、このアドレスからの応答があるかどうかが確認されます。 応答がなく、**[ドメインのアクション]** が **[必要に応じて接続]** の場合は、VPN がトリガーされます。
      
     > [!TIP]
     >
     >このアクションは、たとえば企業のネットワークの一部のサイトで直接または VPN 経由の企業ネットワーク接続が必要であり、その他のサイトではこうした接続を必要としない場合に使うことがあります。 **[ドメインのコンマ区切りリスト]** に *corp.contoso.com* を追加した場合、**[必要な場合に接続する]** を選択してから、そのネットワーク内で VPN が必要となる可能性のある特定のサイト (*sharepoint.corp.contoso.com* など) を追加できます。その後、ルールによって *vpntestprobe.contoso.com* にアクセス可能かどうかがチェックされます。 アクセスできない場合は、SharePoint サイト用に VPN がトリガーされます。
   - **[無視]** - これを選択した場合、VPN 接続は変化しません。 VPN が接続されている場合は接続されたままとなり、接続されていない場合は接続されないままになります。 たとえば、すべての社内 Web サイトで VPN に接続するが、そのうちいずれかの社内サイトは、デバイスが実際に企業ネットワークに接続されている場合にのみアクセスできるようにするルールを作成するとします。 この場合、該当のサイトに対して無視ルールを作成します。
   - **[切断]** - 条件が一致した場合、VPN からデバイスを切断します。 たとえば、会社のワイヤレス ネットワークを **[SSIDs (SSID)]** フィールドに追加してから、デバイスがそれらのネットワークのいずれかに接続するときに VPN からデバイスを切断するルールを作成できます。

ドメイン固有のルールは、すべてのドメインを対象とするルールより前に評価されます。


## <a name="deploy-the-policy"></a>ポリシーの展開

1.  **[ポリシー]** ワークスペースで、展開するポリシーを選び、**[展開の管理]** を選びます。

2.  **[展開の管理]** ダイアログ ボックスで、次の操作を実行します。

    -   ポリシーを展開するには、ポリシーを展開する対象となる 1 つ以上のグループを選択して、**[追加]** &gt; **[OK]** の順に選択します。

    -   ポリシーを展開せずにダイアログ ボックスを閉じるには、**[キャンセル]** を選択します。


展開が成功すると、VPN 接続の一覧で指定した VPN 接続の名前がユーザーのデバイスに表示されます。

**[ポリシー]** ワークスペースの **[概要]** ページに表示されるステータスの概要とアラートを見ると、注意が必要なポリシーの問題を識別できます。 ステータスの概要は [ダッシュボード] ワークスペースにも表示されます。
