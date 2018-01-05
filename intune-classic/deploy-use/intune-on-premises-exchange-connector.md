---
title: "オンプレミス EAS 用の Exchange Connector"
description: "Connector ツールを使用して、Exchange ActiveSync MDM 用に、Intune 管理コンソールと社内の Exchange Server 間の通信を有効にします。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41ff4212-a6f5-4374-8731-631f7560cff1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: aa452f015eee7f50f2709983d04710e0e4be4e64
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="install-the-intune-on-premises-exchange-connector"></a>Intune の内部設置型 Exchange Connector のインストール

[!INCLUDE[classic-portal](../includes/classic-portal.md)]


モバイル デバイスのメールボックスをホストする Exchange Server と Microsoft Intune が通信できるように接続をセットアップするには、Intune 管理コンソールで内部設置型 Exchange Connector をダウンロードして構成する必要があります。 Intune は、サブスクリプションごとに任意の種類の Exchange Connector 接続を 1 つだけサポートします。

## <a name="on-premises-exchange-connector-requirements"></a>内部設置型 Exchange Connector の要件
以下の表に、内部設置型 Exchange Connector をインストールするコンピューターの要件を示します。


|要件|詳細情報|
|---------------|--------------------|
|Operating systems|Intune は、Windows Server 2008 SP2 64 ビット、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 の任意のエディションを実行しているコンピューター上の内部設置型 Exchange Connector をサポートします。<br /><br />Server Core インストールでは、Connector はサポートされません。|
|Microsoft Exchange|内部設置型 Connector には、Microsoft Exchange 2010 SP1 以降または従来の Exchange Online Dedicated が必要です。 Exchange Online Dedicated 環境が**新しい**構成か**従来の**構成かを確認するには、アカウント マネージャーに問い合わせてください。|
|モバイル デバイス管理機関| [モバイル デバイス管理機関を Intune に設定します](prerequisites-for-enrollment.md#step-2-set-mdm-authority)。|
|ハードウェア|コネクタをインストールするコンピューターには、1.6 GHz の CPU と 2 GB の RAM と 10 GB の空きディスク容量が必要です。|/intune/users-permissions-add
|Active Directory の同期|Connector を使用して Intune を Exchange Server に接続するには、[Active Directory の同期をセットアップ](/intune/users-permissions-add)して、ローカル ユーザーとセキュリティ グループが Azure Active Directory のインスタンスと同期されるようにする必要があります。|
|その他のソフトウェア|コネクタをホストするコンピューターに、Microsoft .NET Framework 4.5 および Windows PowerShell 2.0 の完全インストールがインストールされている必要があります。|
|ネットワーク|コネクタをインストールするコンピューターは、Exchange Server をホストするドメインと信頼関係があるドメインに参加している必要があります。<br /><br />コンピューターは、ポート 80 と 443 でファイアウォールとプロキシ サーバー経由で Intune サービスにアクセスできるように構成する必要があります。 Intune によって使用されるドメインには、manage.microsoft.com、&#42;manage.microsoft.com、および &#42;.manage.microsoft.com が含まれます。|


### <a name="exchange-cmdlet-requirements"></a>Exchange コマンドレットの要件

Intune Exchange Connector が使用する Active Directory ユーザー アカウントを作成する必要があります。 アカウントには、次の必須の Windows PowerShell Exchange コマンドレットを実行するための権限が必要です。


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox、Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy、Set-ActiveSyncMailboxPolicy、New-ActiveSyncMailboxPolicy、Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule、Set-ActiveSyncDeviceAccessRule、New-ActiveSyncDeviceAccessRule、Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice、Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>内部設置型 Exchange Connector ソフトウェア インストール パッケージのダウンロード

1. 内部設置型 Exchange Connector のサポートされている Windows Server オペレーティング システムで、Exchange Server を使用するライセンスを持つ Exchange テナント内の管理者であるユーザー アカウントを使用して、[Microsoft Intune 管理コンソール](https://manage.microsoft.com) (https://manage.microsoft.com) を開きます。
![[Exchange 接続のセットアップ] を開く](../media/ExchangeConnector.gif)

2.  ワークスペースのショートカット ウィンドウで **[管理]**>**[モバイル デバイス管理]** > **[Microsoft Exchange]**>**[Exchange 接続のセットアップ]** の順に選択します。

3.  **[Exchange 接続のセットアップ]** ページで **[On-Premises Connector のダウンロード]** を選びます。

4.  内部設置型 Exchange Connector は、開いたり保存したりできる圧縮 (.zip) フォルダーに含まれています。 **[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** を選んで、圧縮フォルダーを安全な場所に保存します。

> [!IMPORTANT]
> オンプレミス Exchange Connector フォルダー内のファイルの名前を変更したり、ファイルを移動したりしないでください。 フォルダーの内容を移動したり、名前を変更したりすると、インストールが失敗します。

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Intune の内部設置型 Exchange Connector のインストールと構成
次の手順を実行して、Intune の内部設置型 Exchange Connector をインストールします。 内部設置型 Exchange Connector は、Intune サブスクリプション 1 つで 1 台のコンピューターに 1 回だけインストールできます。 内部設置型 Exchange Connector をもう 1 つ構成しようとすると、新しい接続で元の接続が置き換えられます。

1. 内部設置型 Connector のサポートされているオペレーティング システムで、**Exchange_Connector_Setup.zip** を安全な場所に抽出します。

2. ファイルが抽出されたら、抽出されたフォルダーを開き、**Exchange_Connector_Setup.exe** をダブルクリックして内部設置型 Exchange Connector をインストールします。

   > [!IMPORTANT]
   > 抽出先のフォルダーが安全な場所にない場合は、内部設置型 Connector をインストールした後で、**WindowsIntune.accountcert** という証明書ファイルを削除してください。

3. **[Microsoft Intune Exchange Connector]** ダイアログ ボックスで、**[内部設置型 Microsoft Exchange Server]** または **[ホストされた Microsoft Exchange Server]** を選択します。

   ![Exchange サーバーの種類の選択](../media/IntuneSA1dconfigureExchConnector.png)

   内部設置型 Exchange Server の場合、**クライアント アクセス サーバー** ロールをホストする Exchange サーバーのサーバー名または完全修飾ドメイン名を指定します。

   ホスト型 Exchange Server の場合、Exchange Server のアドレスを指定します。 ホスト型 Exchange サーバーの URL を見つけるには:

   1. Office 365 の Outlook Web App を開きます。

   2. 左上の **?**  アイコンを選択し、**[バージョン情報]** を選択します。

   3. **[POP 外部サーバー]** の値を探します。

   4. **[プロキシ サーバー]** を選んで、ホスト型 Exchange サーバーのプロキシ サーバー設定を指定します。
       1. **[モバイル デバイス情報を同期するときにプロキシ サーバーを使用する]**を選択します。

       2. サーバーへのアクセスに使用する **[プロキシ サーバー名]** と **[ポート番号]** を入力します。

       3. プロキシ サーバーにアクセスできるユーザーの資格情報を指定する必要がある場合は、**[資格情報を使用してプロキシ サーバーに接続する]** を選択します。 次に、**ドメイン\ユーザー**と**パスワード**を入力します。

       4. **[OK]** を選びます。

   5. **[ユーザー (ドメイン\ユーザー)]** フィールドと **[パスワード]** フィールドに、Exchange Server への接続に必要な資格情報を入力します。

   6.  ユーザーの Exchange Server メールボックスに通知を送信するために必要な管理資格情報を指定します。 これらの通知は、Intune で条件付きアクセス ポリシーにより構成できます。

       自動検出サービスと Exchange Web Services が Exchange クライアント アクセス サーバーで構成されていることを確認します。 詳細については、「[クライアント アクセス サーバー](https://technet.microsoft.com/library/dd298114.aspx)」を参照してください。

   7.  **[パスワード]** フィールドに、このアカウントで Intune から Exchange Server にアクセスするのに必要なパスワードを入力します。

   8. **[接続]**を選びます。

接続が構成されるまでに数分かかることがあります。

接続の構成中、Exchange Connector にインターネットへのアクセスに必要なプロキシの設定が保存されます。 プロキシの設定を変更した場合は、Exchange Connector に更新されたプロキシ設定が適用されるように、Exchange Connector を構成し直す必要があります。

Exchange Connector が接続をセットアップすると、Exchange Connector で管理されているユーザーに関連付けられたモバイル デバイスが自動的に同期されて、Exchange Connector に追加されます。 この同期が完了するまで時間がかかる場合があります。

> [!NOTE]
> 内部設置型 Exchange Connector をインストールし、いずれかの時点で Exchange 接続を削除した場合、インストールされていたコンピューターから内部設置型 Exchange Connector をアンインストールする必要があります。

## <a name="validate-the-exchange-connection"></a>Exchange 接続を確認する

Exchange Connector を正常に構成したら、接続のステータスと前回の成功した同期の試行を表示できます。 [Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理者]** ワークスペースを選択します。 **[モバイル デバイス管理]** で **[Microsoft Exchange]** を選択して、**[Exchange の接続情報]** に表示される設定内容の詳細を確認します。


また、前回いつ同期が完了したかも確認することができます。
