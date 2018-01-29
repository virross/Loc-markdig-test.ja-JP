---
title: "PFX の証明書インフラストラクチャを構成する"
description: ".PFX 証明書プロファイルを作成および展開します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9227a85f194ba5553f41f3d27236372c342f4034
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="configure-certificate-infrastructure"></a>証明書インフラストラクチャを構成する

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

このトピックでは、.PFX 証明書プロファイルを作成して展開するために必要なものについて説明します。

組織で証明書ベースの認証を行うには、エンタープライズ証明機関が必要です。

.PFX 証明書プロファイルを使用するには、エンタープライズ証明機関に加えて次のものも必要です。

-   証明機関と通信できるコンピューターまたは証明機関コンピューター自体を使用します。

-  証明機関と通信できるコンピューターで実行する Intune 証明書コネクタ。

## <a name="on-premises-infrastructure-description"></a>オンプレミス インフラストラクチャの説明


- **Active Directory ドメイン**: このセクションで示されているすべてのサーバー (Web アプリケーション プロキシ サーバーを除く) は、Active Directory ドメインに参加する必要があります。

- **証明機関**: Windows Server 2008 R2 以降の Enterprise エディションで実行するエンタープライズ証明機関 (CA) が必要です。 スタンドアロン CA はサポートされません。 証明機関をセットアップする方法の詳細については、 [証明機関のインストールに関するページ](http://technet.microsoft.com/library/jj125375.aspx)を参照してください。
   CA が Windows Server 2008 R2 を搭載している場合は、 [KB2483564 の修正プログラムをインストール](http://support.microsoft.com/kb/2483564/)する必要があります。

- **証明機関と通信できるコンピューター**: 証明機関コンピューター自体を使用することもできます。
- **Microsoft Intune 証明書コネクタ**: Intune 管理コンソールを使用して**証明書コネクタ** インストーラー (**ndesconnectorssetup.exe**) をダウンロードします。 これにより、証明書コネクタをインストールするコンピューターで **ndesconnectorssetup.exe** を実行できます。 .PFX 証明書プロファイルの場合は、証明機関と通信するコンピューターに証明書コネクタをインストールします。
- **Web アプリケーション プロキシ サーバー** (省略可能): Web アプリケーション プロキシ (WAP) サーバーとして Windows Server 2012 R2 以降を実行しているサーバーを使用できます。 この構成は:
   -  デバイスはインターネット接続を使用して証明書を受信できます。
   -  デバイスがインターネット接続経由で証明書を受信して更新する場合のセキュリティ推奨事項です。

  > [!NOTE]           
  > -    WAP をホストするサーバーは、ネットワーク デバイス登録サービス (NDES) で使用される長い URL のサポートを有効にする[更新プログラムをインストールする](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) 必要があります。 この更新プログラムは、 [2014 年 12 月の更新プログラムのロールアップ](http://support.microsoft.com/kb/3013769)に含まれます。または、 [KB3011135](http://support.microsoft.com/kb/3011135)から個別に入手できます。
  >-  また、WAP をホストするサーバーが、外部クライアントに公開される名前と一致する SSL 証明書を持ち、NDES サーバーで使用される SSL 証明書を信頼する必要があります。 これらの証明書を使用すると、WAP サーバーはクライアントからの SSL 接続を終了し、NDES サーバーへの新しい SSL 接続を作成できます。
   WAP の証明書については、「[内部アプリケーションの公開のために Web アプリケーション プロキシをインストールおよび構成する](https://technet.microsoft.com/library/dn383650.aspx)」の**証明書の計画**に関するセクションを参照してください。 WAP サーバーの一般的な情報については、「[Web アプリケーション プロキシの使用](http://technet.microsoft.com/library/dn584113.aspx)」を参照してください。|


### <a name="certificates-and-templates"></a>証明書とテンプレート

|オブジェクト|説明|
|----------|-----------|
|**証明書テンプレート**|発行元 CA でこのテンプレートを構成します。|
|**信頼されたルート CA 証明書**|これを発行元 CA または発行元 CA を信頼するデバイスから **.cer** ファイルとしてエクスポートし、信頼された CA 証明書プロファイルを使用してデバイスに展開します。<br /><br />オペレーティング システムのプラットフォームごとに 1 つの信頼されたルート CA 証明書を使用し、作成する各信頼されたルート証明書プロファイルに関連付けます。<br /><br />必要に応じて、信頼されたルート CA 証明書を追加して使用できます。 ルート CA 証明書を追加する局面としては、Wi-Fi アクセス ポイント用のサーバー認証証明書に署名する CA の信頼性を担保する必要がある場合などが考えられます。|


## <a name="configure-your-infrastructure"></a>インフラストラクチャを構成する
証明書プロファイルを構成するには、次のタスクを完了する必要があります。 以下のタスクには、Windows Server 2012 R2 と Active Directory 証明書サービス (ADCS) についての知識が必要となります。

- **タスク 1** - 証明機関で証明書テンプレートを構成する。
- **タスク 2** - Intune 証明書コネクタを有効にし、インストールし、構成する。

### <a name="task-1---configure-certificate-templates-on-the-certification-authority"></a>タスク 1 - 証明機関で証明書テンプレートを構成する
このタスクでは、証明書テンプレートを公開します。

##### <a name="to-configure-the-certification-authority"></a>証明機関を構成するには

1.  発行元 CA で、証明書テンプレート スナップインを使用して、新しいカスタム テンプレートを作成するか、または .PFX で使用するために (ユーザー テンプレートのように) 既存のテンプレートをコピーして、編集します。

    テンプレートには以下を含む必要があります。

    -   テンプレートのわかりやすい **テンプレート表示名** を指定します。

    -   **[サブジェクト名]** タブで **[要求に含まれる]** を選択します 

    -   **[拡張]** タブで、**[アプリケーション ポリシーの説明]** に **[クライアント認証]** が含まれることを確認します。

        > [!IMPORTANT]
        > iOS および Mac OS X の証明書テンプレートの場合、**[拡張]** タブで、**[キー使用法]** を編集し、**[署名は発行元の証明である]** がオンになっていないことを確認します。

2.  **[一般]** タブでテンプレートの **[有効期間]** を確認します。 既定では、Intune はテンプレートで構成されている値を使用します。 ただし、要求元が異なる値を指定できるように CA を構成できます。異なる値は、Intune 管理者コンソールから設定できます。 常にテンプレートの値を使用する場合は、この手順の残りの部分をスキップします。

    > [!IMPORTANT]
    > iOS および Mac OS X プラットフォームは、他の構成に関係なく、常にテンプレートで設定される値を使用します。

    要求元が有効期間を指定できるように CA を構成するには、CA で次のコマンドを実行します。

    」を参照します。  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  発行元 CA で、証明機関スナップインを使用して証明書テンプレートを発行します。

    」を参照します。  **[証明書テンプレート]** ノードを選択し、**[アクション]** -&gt; **[新規]** &gt; **[発行する証明書テンプレート]** の順にクリックして、手順 2. で作成したテンプレートを選択します。

    b.  **[証明書テンプレート]** フォルダーに表示されることで、テンプレートが発行されたことを確認します。

4.  CA コンピューターで、Intune 証明書コネクタをホストするコンピューターが、.PFX プロファイルの作成で使用するテンプレートにアクセスできるように、登録アクセス許可を持つことを確認します。 CA コンピューター プロパティの **[セキュリティ]** タブでそのアクセス許可を設定します。

### <a name="task-2---enable-install-and-configure-the-intune-certificate-connector"></a>タスク 2 - Intune 証明書コネクタを有効にし、インストールし、構成する
このタスクでは次のことを行います。

証明書コネクタをダウンロードし、インストールして、構成します。

##### <a name="to-enable-support-for-the-certificate-connector"></a>証明書コネクタのサポートを有効にするには

1.  [Intune の管理コンソール](https://manage.microsoft.com)を開き、**[管理者]** &gt; **[証明書コネクタ]** の順に選択します。

2.  **[On-premises Certificate Connector の構成]** を選択します。

3.  **[証明書コネクタを有効にする]**を選択し、 **[OK]**を選択します。

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>証明書コネクタをダウンロードし、インストールして、構成するには

1. [Intune の管理コンソール](https://manage.microsoft.com)を開き、**[管理者]** &gt; **[モバイル デバイス管理]** &gt; **[証明書コネクタ]** &gt; **[証明書コネクタのダウンロード]** を選択します。

2. ダウンロードが完了したら、ダウンロードされたインストーラー (**ndesconnectorssetup.exe**) を実行します。

   証明機関と接続できるコンピューターでインストーラーを実行します。 [.PFX の配布] オプションを選択し、**[インストール]** を選択します。 インストールが完了したら、「[Configure certificate profiles](configure-intune-certificate-profiles.md)」 (証明書プロファイルを構成する) の説明に従って、証明書プロファイルを作成して続行します。

   <!-- Not sure about step 3 below -->

3. 証明書コネクタのクライアント証明書の入力を求められたら、**[選択]** を選択し、タスク 3 でインストールした**クライアント認証**証明書を選択します。

   クライアント認証証明書を選択した後、**[Microsoft Intune 証明書コネクタのクライアント証明書]** 画面に戻ります。 選択した証明書は表示されませんが、**[次へ]** を選択してその証明書のプロパティを表示します。 **[次へ]** を選択して、**[インストール]** を選択します。

4. ウィザードが完了した後、ウィザードを閉じる前に、**[証明書コネクタの UI を起動]** をクリックします。

   > [!TIP]
   > 証明書コネクタの UI を起動する前にウィザードを閉じた場合は、次のコマンドを実行して再び開くことができます。
   >
   > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5. **証明書コネクタ** UI で:

   」を参照します。 **[サインイン]** を選択し、Intune サービス管理者の資格情報、またはグローバル管理アクセス許可を持つテナント管理者の資格情報を入力します。

   b. **[詳細設定]** タブを選択し、発行元 CA で**証明書の発行と管理**アクセス許可を持つアカウントの資格情報を指定します。

   c. **[適用]** を選択します。

   これで、証明書コネクタ UI を閉じることができます。

6. コマンド プロンプトを開き、**services.msc** を入力します。 **[Enter]** キーを押し、**[Intune コネクタ サービス]** を右クリックして、**[再起動]** を選択します。


### <a name="next-steps"></a>次の手順
これで、「[Configure certificate profiles (証明書プロファイルを構成する)](Configure-Intune-certificate-profiles.md)」の説明に従って証明書プロファイルを構成する準備が整いました。
