---
title: "Windows 10 の Intune デバイス制限設定"
titlesuffix: Azure portal
description: "Windows 10 デバイスでデバイスの設定と機能を制御するために使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0dd4bd3052fcdb26193bb935dae729eab8d19f1e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune での Windows 10 以降のデバイスの制限設定

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>全般
- **[画面キャプチャ (モバイルのみ)]** - ユーザーがデバイスの画面を画像としてキャプチャできるようにします。
- **[コピー/貼り付け (モバイルのみ)]** - デバイス上のアプリ間でのコピー/貼り付け操作を許可します。
- **[手動での登録解除]** - ユーザーがデバイスから会社アカウントを手動で削除できるようにします。
- **[ルート証明書の手動インストール (モバイルのみ)]** - ユーザーがルート証明書と中間 CAP 証明書を手動でインストールしないようにします。
- **[診断データの送信]** - 指定できる値は次のとおりです。
    - **[なし]** - データは Microsoft に送信されません。
    - **[基本]** - 一部の情報のみを Microsoft に送信します。
    - **[拡張]** - より詳細な診断データを Microsoft に送信します。
    - **[フル]** - [拡張] で送信されるデータに加えて、デバイスの状態に関する追加データを送信します。
- **[カメラ]** - デバイス上のカメラの使用を許可またはブロックします。
- **[OneDrive のファイル同期]** - デバイスによる OneDrive へのファイル同期をブロックします。
- **[リムーバブル記憶域]** - SD カードなどの外部記憶装置をデバイスで使用できるようにするかどうかを指定します。
- **[位置情報]** - デバイスが位置情報サービスの情報を使用できるかどうかを指定します。
- **[インターネット共有]** - デバイスでインターネット接続の共有を使用できるようにします。
- **[電話のリセット]** - ユーザーがデバイスを工場出荷時設定にリセットできるかどうかを制御します。
- **[USB 接続 (モバイルのみ)]** - デバイスが USB 接続を介して外部記憶装置にアクセスできるかどうかを制御します。
- **[盗難防止モード (モバイルのみ)]** - Windows の盗難防止モードを有効にするかどうかを構成します。
- **[Cortana]** - Cortana による音声アシスタントを有効または無効にします。
- **[音声録音 (モバイルのみ)]** - デバイスのボイス レコーダーの使用を許可またはブロックします。
- **[デバイス名の変更]** - エンド ユーザーがデバイスの名前を変更することを防止します (Windows 10 Mobile のみ)。
- **[プロビジョニング パッケージを追加する]** - プロビジョニング パッケージをインストールするランタイム構成エージェントをブロックします。
- **[プロビジョニング パッケージを削除する]** - プロビジョニング パッケージを削除するランタイム構成エージェントをブロックします。
- **[デバイスの検出]** - 他のデバイスからのデバイスの検出をブロックします。
- **[タスク スイッチャー (モバイルのみ)]** - デバイス上のタスク スイッチャーをブロックします。
- **[SIM カードのエラー ダイアログ (モバイルのみ)]** - SIM カードが検出されない場合のデバイスでのエラー メッセージ表示をブロックします。
  <!--- **Automatic redeployment** - Allows users with administrative rights to delete all user data and settings using **CTRL + Win + R** at the device lock screen. The device is automatically reconfigured and reenrolled into management. -->


## <a name="password"></a>パスワード
-   **[パスワード]** - エンド ユーザーがデバイスにアクセスする際にパスワードの入力を要求します。
    -   **[必要なパスワードの種類]** - パスワードを数字のみにするか、英数字にするかを指定します。
    -   **[パスワードの最小文字数]** - Windows 10 Mobile のみに適用されます。
    -   **[デバイスがワイプされるまでのサインイン失敗回数]** - Windows 10 を実行しているデバイス: デバイスで BitLocker が有効になっている場合は、指定した回数分サインインに失敗すると、BitLocker 回復モードになります。 デバイスの BitLocker が有効でない場合は、この設定は適用されません。
Windows 10 Mobile を実行しているデバイス: 指定した回数分サインインに失敗すると、デバイスがワイプされます。
    -   **[画面がロックされるまでの非アクティブな最長時間 (分)]** - デバイスのアイドル状態が許容される時間を指定します。この時間を超えると、画面はロックされます。
    -   **[パスワードの有効期限 (日数)]** - デバイスのパスワードを設定後、変更が必要になるまでの日数を指定します。
    -   **[Prevent reuse of previous passwords]\(前のパスワードを再利用できないようにする\)** - デバイスで記憶される、以前に使用したパスワードの数を指定します。
    -   **[デバイスがアイドル状態から戻るときにパスワードを必須にする (モバイルのみ)]** - ユーザーがデバイスのロックを解除するときにパスワードの入力を必須にします (Windows 10 Mobile のみ)。
    -   **[単純なパスワード]** - 単純なパスワードの使用を許可します (1111、1234 など)。 この設定は、Windows ピクチャ パスワードの使用も許可またはブロックします。
-   **[暗号化]** - 対象デバイスの暗号化を有効にします。

## <a name="personalization"></a>個人設定

-   **[デスクトップの背景画像の URL (デスクトップのみ)]** - Windows のデスクトップの壁紙として使用する、PNG、JPG、または JPEG 形式の画像への URL を指定します。 ユーザーがこれを変更することはできません。

## <a name="privacy"></a>プライバシー

-   **[入力個人設定]** – Cortana、ディクテーション、Microsoft ストア アプリでのクラウドベースの音声入力サービスの使用を許可しません。 これらのサービスを許可する場合、Microsoft はサービス向上のために音声データを収集することがあります。
-   **[ペアリングとプライバシーに関するユーザーの同意プロンプトの自動受け入れ]** – アプリの実行時にペアリングとプライバシーに関する同意メッセージを自動的に受け入れることを Windows に許可します。


## <a name="locked-screen-experience"></a>ロック画面


-   **[アクション センターの通知 (モバイルのみ)]** - デバイス ロック画面にアクション センターの通知を表示させます (Windows 10 Mobile のみ)。
-   **[ロック画面の画像の URL (デスクトップのみ)]** - Windows のロック画面の壁紙として使用する、PNG、JPG、または JPEG 形式の画像への URL を指定します。 ユーザーがこれを変更することはできません。
-   **[ユーザーが構成可能なスクリーン タイムアウト (モバイルのみ)]** – 時間の構成をユーザーに許可します。 
-   **[ロック画面での Cortana (デスクトップのみ)]** – デバイスがロック画面になっているとき、Cortana の操作をユーザーに許可しません (Windows 10 デスクトップのみ)。
-   **[ロック画面でのトースト通知]** – デバイス ロック画面でアラート メッセージの表示をブロックします。
-   **[スクリーン タイムアウト (モバイルのみ)]** - 画面ロック後、画面がオフになるまでの時間を秒単位で指定します。



## <a name="app-store"></a>アプリ ストア

-   **[App store (モバイルのみ)]** - Windows 10 Mobile デバイスでのアプリ ストアの使用を許可またはブロックします。
-   **[ストア アプリの自動更新]** - Microsoft ストアからインストールされたアプリの自動更新を許可します。
-   **[信頼できるアプリのインストール]** - 信頼済み証明書で署名されたアプリのサイドロードを許可します。
-   **[開発者によるロック解除]** - サイドロードしたアプリのエンド ユーザーによる変更を許可するなど、Windows 開発者の設定を許可します。
-   **[共有ユーザー アプリ データ]** - 同じデバイス上の異なるユーザー間でのデータの共有をアプリに許可します。
-   **[プライベート ストアのみを使用します]** - これを有効にすると、エンド ユーザーがプライベート ストアからアプリをダウンロードすることのみ許可します。
-   **[ストアから配信されたアプリの起動]** - デバイスにプレインストールされた、または Microsoft ストアからダウンロードされたすべてのアプリを無効にするのに使用します。
-   **[システム ボリューム上でアプリ データをインストールします]** - アプリがデバイスのシステム ボリューム上にデータを格納しないようにします。
-   **[システム ドライブ上でアプリをインストールします]** - アプリがデバイスのシステム ドライブ上にデータを格納しないようにします。
-   **[ゲーム録画 (デスクトップのみ)]** - ゲームの録画とブロードキャストを許可するかどうか設定します。
-   **[Apps from store only]\(ストアからのアプリのみ\)** - ユーザーがアプリ ストア以外の場所からアプリをインストールできるかどうかを構成します。



## <a name="edge-browser"></a>Microsoft Edge ブラウザー

-   **[Microsoft Edge ブラウザー (モバイルのみ)]** - デバイスで Edge Web ブラウザーを使用できるようにします。
-   **[アドレス バーのドロップダウン (デスクトップのみ)]** – これを使用すると、Edge でドロップダウン リストの入力候補表示が停止します。 Edge と Microsoft サービスの間のネットワーク帯域幅が最小に抑えられます。
-   **[Microsoft のブラウザー間でお気に入りを同期する (デスクトップのみ)]** – Internet Explorer と Edge の間でお気に入りを同期することを Windows に許可します。
-   **[トラッキング拒否ヘッダーを送信する]** - ユーザーがアクセスする Web サイトに Do Not Track ヘッダーを送信するように、Microsoft Edge ブラウザーを構成します。
-   **[Cookie]** - ブラウザーがインターネット Cookie をデバイスに保存するように設定します。
-   **[JavaScript]** - JavaScript などのスクリプトを Microsoft Edge ブラウザーで実行できるようにします。
-   **[ポップアップ]** - ブラウザー内のポップアップ ウィンドウをブロックします (Windows 10 デスクトップのみ適用)。
-   **[検索候補]** - 検索語句を入力したときに、検索エンジンからサイトが提案されるようになります。
-   **[Internet Explorer にイントラネット トラフィックを送信する]** - ユーザーが Internet Explorer でイントラネット Web サイトを開けるようにします (Windows 10 デスクトップのみ)。
-   **[オートフィル]** - ユーザーがブラウザーのオートコンプリートの設定を変更できるようにします (Windows 10 デスクトップのみ)。
-   **[パスワード マネージャー]** - Microsoft Edge Password Manager 機能を有効または無効にします。
-   **[エンタープライズ モードのサイト一覧の場所]** - エンタープライズ モードで開く Web サイトの一覧を検索する場所を指定します。 ユーザーは、この一覧を編集できません。<br>(Windows 10 デスクトップのみ)。
-   **[開発者ツール]** - エンド ユーザーが Microsoft Edge 開発者ツールを開くことを防止します。
-   **[拡張機能]** - エンド ユーザーがデバイスに Microsoft Edge 拡張機能をインストールすることを許可します。
-   **[InPrivate 閲覧]** - エンド ユーザーが InPrivate 閲覧セッションを開くことを防止します。
-   **[初回実行ページを表示する]** – Edge の初回実行時に紹介ページの表示を停止します。
    -   **[初回実行の URL]** – ユーザーが初めて Edge を実行したときに表示されるページの URL を指定します (Windows 10 Mobile のみ)。
-   **[ホームページ]** - Edge ブラウザーのホームページとして使用するサイトの一覧を追加します (デスクトップのみ)。
-   **[スタート ページに対する変更内容]** – Edge を開いたときに表示されるスタート ページの変更をユーザーに許可します。 ホームページ設定を使用し、Edge 起動時に開くページまたはページ リストを作成します。
-   **[About Flags へのアクセスをブロック]** - エンド ユーザーが Microsoft Edge で開発者と実験用の設定を含む about:flags ページにアクセスするのを防止します。
-   **[WebRtc localhost IP アドレス]** - Web RTC プロトコルを使用して電話するときにユーザーの localhost IP アドレスが表示されないようにします。
-   **[既定の検索エンジン]** - 使用する既定の検索エンジンを指定します。 エンド ユーザーはこの値をいつでも変更できます。
-   **[終了時に閲覧データをクリアする]** – ユーザーが Edge を終了すると、履歴と閲覧データが消去されます。
-   **[ライブ タイル データの収集]** – ユーザーが Edge からスタート メニューにサイトをピン留めするとき、Windows がライブ タイルから情報を収集する行為を停止します。

## <a name="edge-browser-smartscreen"></a>Edge ブラウザーの SmartScreen

-   **[SmartScreen]** - 不正な Web サイトをブロックする SmartScreen を有効または無効にします。
-   **[SmartScreen のプロンプトの上書き]** - 悪意がある可能性のある Web サイトに関する SmartScreen フィルターの警告をエンド ユーザーがバイパスすることを許可します。
-   **[ファイルに関する SmartScreen プロンプトの無視]** - 悪意がある可能性のあるファイルのダウンロードに関する SmartScreen フィルターの警告をエンド ユーザーがバイパスすることを許可します。

## <a name="search"></a>検索
- **[セーフ サーチ (モバイルのみ)]** - Cortana が検索結果でアダルト コンテンツをフィルター処理する方法を制御します。 **[高]**、**[中程度]** を選択するか、エンド ユーザーが独自の設定を選択するのを許可します。

## <a name="cloud-and-storage"></a>クラウドとストレージ
-   **[Microsoft アカウント]** - ユーザーがデバイスに Microsoft アカウントを関連付けられるようにします。
-   **[Microsoft 以外のアカウント]** - Microsoft アカウントに関連付けられていないデバイスに、ユーザーが電子メール アカウントを追加できるようにします。
-   **[Microsoft アカウントの設定の同期]** - Microsoft アカウントに関連付けられたデバイスとアプリの設定をデバイス間で同期できるようにします。

## <a name="cellular-and-connectivity"></a>携帯ネットワークと接続性

-   **[携帯データ ネットワーク チャネル]** – 携帯ネットワークに接続しているとき、Web 閲覧など、ユーザーのデータ使用を停止します。 
-   **[データ ローミング]** - データへのアクセス中にネットワーク間のローミングを許可します。
-   **[移動体通信ネットワーク経由の VPN]** - 移動体通信ネットワークに接続したときに、デバイスが VPN 接続にアクセスできるようにするかどうかを制御します。
-   **[移動体通信ネットワーク経由の VPN ローミング]** - 移動体通信ネットワークでのローミング中に、デバイスが VPN 接続にアクセスできるようにするかどうかを制御します。
-   **[Bluetooth]** - ユーザーがデバイスの Bluetooth を有効にして構成できるようにするかどうかを制御します。
-   **[Bluetooth の検出可能性]** - その他の Bluetooth 対応デバイスにより、デバイスが検出されるようにします。
-   **[Bluetooth の事前ペアリング]** – ホスト デバイスと自動的にペアリングするように特定の Bluetooth デバイスを構成できます。
-   **[Bluetooth 広告]** - デバイスが Bluetooth 経由で広告を受信できるようにします。
-   **[接続されているデバイスのサービス]** – 接続されているデバイスのサービスを許可するかどうかを選択できます。他の Bluetooth デバイスの検出と接続が有効になります。
-   **[NFC]** - ユーザーがデバイス上で近距離無線通信機能を有効にして構成できるようにします。
-   **[Wi-Fi]** - ユーザーがデバイスで Wi-Fi を有効にして構成できるようにします (Windows 10 Mobile のみ)。
-   **[自動的に Wi-Fi ホットスポットに接続します]** - デバイスが無料の Wi-Fi ホットスポットに自動的に接続し、接続の使用条件に自動的に同意するようにします。
-   **[Wi-Fi の手動設定]** - ユーザーが独自に Wi-Fi 接続を構成できるようにするか、Wi-Fi プロファイルで構成された接続のみを使用できるようにするかを制御します (Windows 10 Mobile のみ)。
-   **[Wi-Fi スキャンの間隔]** - デバイスが Wi-Fi ネットワークをスキャンする頻度を指定します。 1 (頻度が最も多い) から 500 (頻度が最も少ない) までの値を指定できます。
-   **[Bluetooth を使用できるサービス]** – 許可される Bluetooth のサービスとプロファイルの一覧を 16 進数文字列で指定します。


## <a name="control-panel-and-settings"></a>コントロール パネルと設定

-   **[設定アプリ]** - Windows の設定アプリへのアクセスをブロックします。
    -   **[システム]** - 設定アプリのシステム領域へのアクセスをブロックします。
        -   **[電源とスリープの設定の変更 (デスクトップのみ)]** - エンド ユーザーがデバイスの電源とスリープの設定を変更することを防止します。
    -   **[デバイス]** - 設定アプリのデバイス領域へのアクセスをブロックします。
    -   **ネットワークとインターネット**-、設定アプリのネットワークとインターネットの領域へのアクセスをブロックします。
    -   **[個人用設定]** - 設定アプリの個人用設定の領域へのアクセスをブロックします。
    -   **[アカウント]** - 設定アプリのアカウント領域へのアクセスをブロックします。
    -   **[時刻と言語]** - 設定アプリの時刻と言語の領域へのアクセスをブロックします。
        -   **[システム時刻の変更]** - エンド ユーザーがデバイスの日付と時刻を変更することを防止します。
        -   **[地域の設定の変更 (デスクトップのみ)]** - エンド ユーザーがデバイスの地域設定を変更することを防止します。
        -   **[言語設定の変更 (デスクトップのみ)]** - エンド ユーザーがデバイスの言語設定を変更することを防止します。
    -   **[ゲーム]** - 設定でゲーム アプリへのアクセスをブロックします。
    -   **[簡単操作]** - 設定アプリの簡単操作の領域へのアクセスをブロックします。
    -   **[プライバシー]** - 設定アプリのプライバシー領域へのアクセスをブロックします。
    -   **[更新とセキュリティ]** - 設定アプリの更新とセキュリティの領域へのアクセスをブロックします。

## <a name="kiosk"></a>キオスク

-   **[キオスク モード]** - ポリシーによってサポートされる[キオスク モード](https://docs.microsoft.com/en-us/windows/configuration/kiosk-shared-pc)の種類を識別します。  次のオプションがあります。

      - **[未構成]** (既定) - このポリシーでは、キオスク モードが有効になりません。 
      - **[シングル アプリ キオスク]** - このプロファイルでは、デバイスがシングル アプリ キオスクとして有効になります。
      - **[マルチ アプリ キオスク]** - このプロファイルでは、デバイスがマルチ アプリ キオスクとして有効になります。

    シングル アプリ キオスクに必要な設定:

      - **[ユーザー アカウント]** - (デバイスの) ローカル ユーザー アカウントか、キオスク アプリに関連付けられている Azure AD アカウント ログインを指定します。  Azure AD ドメインに参加しているアカウントについては、`domain\\username@tenant.org` の形式でアカウントを指定します。

         公共の場におけるデバイスについては、認可アクティビティを禁止するために最小特権のアカウントを使用します。  

      - **アプリのアプリケーション ユーザー モデル ID (AUMID)** - キオスク アプリの AUMID を指定します。  詳細については、「[Find the Application User Model ID of an installed app](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app)」 (インストール済みアプリのアプリケーション ユーザー モデル ID を見つける) を参照してください。

    マルチ アプリ キオスクには、キオスク構成が必要です。  **[追加]** ボタンを使用してキオスク構成を作成するか、既存の構成を選びます。

    マルチ アプリ キオスク構成に含まれる設定:

    - **[キオスク構成名]** - 特定の構成の識別に使用されるフレンドリ名。

    - 1 つまたは複数の**キオスク アプリ**の構成要素:

        - **アプリの種類**。キオスク アプリの種類を指定します。  サポートされる値には次のものが含まれます。   

            - **Win32 アプリ** - 従来のデスクトップ アプリ。  (デバイスに関しては、実行可能ファイルの完全修飾パス名が必要です。)

            - **UWP アプリ** - ユニバーサル Windows アプリ。  [アプリの AUMID](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) が必要です。

        - **アプリ識別子** - 実行可能ファイル (Win32 アプリ) または[アプリの AUMID](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP アプリ) の完全修飾パス名を指定します。

    - **タスク バー**は、タスク バーがキオスクに表示されるか (**[有効]**)、非表示になるか (**[未構成]**) が示されます。

    - **[スタート メニューのレイアウト]** - アプリを [[スタート] メニューに表示する](https://docs.microsoft.com/en-us/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)方法を説明する XML ファイルを指定します。

    - **[割り当てられたユーザー]** - キオスク構成に関連付けられている 1 つまたは複数のユーザー アカウントを指定します。  アカウントは、デバイスのローカル アカウントか、キオスク アプリに関連付けられている Azure AD アカウント ログインになります。  ドメイン参加のアカウントを `domain\\username@tenant.org` 形式で指定します。

## <a name="defender"></a>Defender

- **[リアルタイム監視]** - マルウェアやスパイウェアなど、望ましくないソフトウェアについてのリアルタイム スキャンを有効にします。
- **[動作の監視]** - デバイス上で特定の既知のパターンで行われる疑わしい動作を、Defender がチェックできるようにします。
- **[ネットワーク検査システム (NIS)]** - NIS は、ネットワークベースのエクスプロイトからデバイスを守るために役立ちます。 Microsoft Endpoint Protection Center にある既知の脆弱性の署名を使用して、悪意のあるトラフィックを検出してブロックします。
- **[すべてのダウンロードをスキャンする]** - Defender がインターネットからダウンロードされたすべてのファイルをスキャンするかどうかを制御します。
- **[Microsoft Web ブラウザーに読み込まれたスクリプトをスキャンする]** - Internet Explorer で使用されるスクリプトを Defender がスキャンできるようにします。
- **[Defender へのエンド ユーザー アクセス]** - Windows Defender ユーザー インターフェイスをエンド ユーザーに対して非表示にするかどうかを制御します。
  この設定の変更は、エンド ユーザーの PC が次に再起動されたときに有効になります。
- **[署名更新間隔 (時単位)]** - Defender が新しいシグネチャ ファイルをチェックする間隔を指定します。
- **[ファイルとプログラムのアクティビティを監視する]** - デバイス上のファイルとプログラムのアクティビティの監視を Defender に許可します。
- **[検疫済みマルウェアを削除するまでの日数]** - 指定した日数の間、Defender で解決済みマルウェアの追跡を続けられるようにし、以前に影響を受けたデバイスを手動でチェックできるようにします。 日数を **0** に設定すると、マルウェアは検疫フォルダーに残り、自動的に削除されなくなります。
- **[スキャン中の CPU 使用率の制限]** - スキャンに使用できる CPU の使用率を制限できるようにします (**1** ～ **100**)。
- **[アーカイブ ファイルをスキャンする]** - Zip ファイルや Cab ファイルなどのアーカイブ済みのファイルを Defender がスキャンできるようにします。
- **[受信メール メッセージをスキャンする]** - デバイスに届いた電子メール メッセージを Defender が直ちにスキャンできるようにします。
- **[フル スキャン中に、リムーバブル ドライブをスキャンする]** - Defender が USB メモリなどのリムーバブル ドライブをスキャンできるようにします。
- **[フル スキャン中に、マップされたネットワーク ドライブをスキャンする]** - マップ済みネットワーク ドライブ上のファイルを Defender がスキャンできるようにします。<br>ドライブ上のファイルが読み取り専用である場合、Defender は検出したマルウェアを一切削除できません。
- **[ネットワーク フォルダーから開いたファイルをスキャンする]** - 共有ネットワーク ドライブ上のファイルを Defender がスキャンできるようにします (UNC パスからアクセスされたファイルなど)。
  ドライブ上のファイルが読み取り専用である場合、Defender は検出したマルウェアを一切削除できません。
- **[クラウド保護]** - 管理対象のデバイスからマルウェアのアクティビティに関する情報が Microsoft Active Protection Service に送信されるのを許可またはブロックします。 この情報は、将来的に本サービスの品質向上を目的として使用されます。
- **[サンプルを送信する前にユーザーに確認メッセージを表示する]** - 悪意の有無を判断するために詳しい分析が必要なファイルを Microsoft に自動的に送信するかどうかを制御します。
- **[毎日のクイック スキャンを実行する時刻]** - 選択した時刻に毎日実行されるクイック スキャンのスケジュールを設定できます。
- **[実行するシステム スキャンの種類]** - システム スキャンのスケジュールを設定したときに実行されるスキャンのレベルを指定できます。
- **[望ましくない可能性のあるアプリケーションを検出する]** – 望ましくない可能性のあるアプリケーションが Windows で検出されたときの保護レベルを選択します。
      - **ブロック**
      - **監査** 望ましくない可能性があるアプリの詳細については、[このトピック](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus)をご覧ください。
- **検出されたマルウェアの脅威に対するアクション** – Defender が検出した脅威のレベル (低、中、高、重大) ごとに Defender にとらせる措置を指定するにはこのオプションを有効にします。 可能な措置:
  -   **消去**
  -   **検疫**
  -   **削除**
  -   **許可**
  -   **ユーザー定義**
  -   **ブロック**



## <a name="defender-exclusions"></a>Defender の除外

-   **[スキャンおよびリアルタイム保護から除外するファイルとフォルダー]** - **C:\Path** や **%ProgramFiles%\Path\filename.exe** などのファイルやフォルダーを、除外リストに 1 つ以上追加します。 これらのファイルとフォルダーは、リアルタイムまたはスケジュールされたスキャンの対象外となります。
-   **[スキャンおよびリアルタイム保護から除外するファイル拡張子]** - **jpg** や **txt** などのファイル拡張子を除外リストに 1 つ以上追加します。 これらの拡張子が付いたファイルは、リアルタイムまたはスケジュールされたスキャンの対象外となります。
-   **[スキャンとリアルタイム保護から除外するプロセス]** - **.exe**、**.com**、**.scr** などの種類のプロセスを除外リストに 1 つ以上追加します。 これらのプロセスはリアルタイム スキャンや定期スキャンには含まれません。


## <a name="network-proxy"></a>ネットワーク プロキシ

-   **[自動的にプロキシ設定を検出する]** - 有効にすると、デバイスは PAC スクリプトのパスを検索します。
-   **[プロキシ スクリプトを使う]** - PAC スクリプトへのパスを指定してプロキシ サーバーを構成する場合は、このオプションを選択します。
    -   **[セットアップ スクリプトのアドレスの URL]** - プロキシ サーバーの構成に使用する PAC スクリプトの URL を入力します。
-   **[手動プロキシ サーバーを使う]** - プロキシ サーバーの情報を手動で指定する場合は、このオプションを選択します。
    -   **[アドレス]** - プロキシ サーバーの名前または IP アドレスを入力します。
    -   **[ポート番号]** - プロキシ サーバーのポート番号を入力します。
    -   **[プロキシの例外]** - プロキシ サーバーを使用してはいけない URL を入力します。 各項目の区切りにはセミコロンを使用します。
    -   **[ローカル アドレスにはプロキシ サーバーを使わない]** - イントラネットでローカル アドレスのプロキシ サーバーを使用しない場合、このオプションを有効にします。


## <a name="windows-spotlight"></a>Windows スポットライト


- **Windows スポットライト** - この設定を使用し、Windows 10 デバイスですべての Windows スポットライト機能をブロックします。 この設定をブロックすると、次の設定は利用できません。
    - **[ロック画面の Windows スポットライト]** – Windows スポットライトで、デバイス ロック画面の情報表示を停止します。
    - **[Windows スポットライトでのサード パーティのおすすめ]** – Windows スポットライトで、Microsoft が発行していないコンテンツの提案を停止します。
    - **[コンシューマー向けの機能]** - スタート メニューの提案、メンバーシップ通知などのコンシューマー機能をブロックできます。
    - **[Windows のヒント]** - Windows でポップアップのヒントの表示をブロックできます。
    - **[アクション センターの Windows スポットライト]** – 新しいアプリやセキュリティ コンテンツなど、Windows アクション センターの Windows スポットライト提案表示を停止します。
    - **[Windows スポットライトのパーソナル化]** – Windows スポットライトで、デバイスの使用状況に基づいて結果をパーソナル化することを停止します。
    - **[Windows へようこそのエクスペリエンス]** – 新機能や更新機能に関する情報をユーザーに表示する [Windows へようこそ] をブロックします。


## <a name="projection"></a>プロジェクション

- **[ワイヤレス ディスプレイ レシーバーからのユーザー入力]** - ワイヤレス ディスプレイ レシーバーからのユーザー入力をブロックします。
- **[この PC へのプロジェクション]** - 他のデバイスがプロジェクション用にこの PC を検出しないようにします。
- **[ペアリングには PIN が必要]** - プロジェクション デバイスに接続するときに PIN が必要です。

## <a name="start"></a>開始

- **[タスク バーからアプリをピン解除する]** - ユーザーがアプリをスタート メニューからピン解除しないようにします。
- **[[スタート] の [ドキュメント]]** - Windows のスタート メニューにある [ドキュメント] フォルダーを表示または非表示にします。
- **[[スタート] の [ダウンロード]]** - Windows のスタート メニューにある [ダウンロード] フォルダーを表示または非表示にします。
- **[[スタート] の [エクスプローラー]]** - Windows のスタート メニューにある [エクスプローラー] を表示または非表示にします。
- **[[スタート] の [ホームグループ]]** - Windows のスタート メニューにある [ホームグループ] フォルダーを表示または非表示にします。
- **[[スタート] の [ミュージック]]** - Windows のスタート メニューにある [ミュージック] フォルダーを表示または非表示にします。
- **[[スタート] の [ネットワーク]]** - Windows のスタート メニューにある [ネットワーク] フォルダーを表示または非表示にします。
- **[[スタート] の [個人用フォルダー]]** - Windows のスタート メニューにある個人用フォルダーを表示または非表示にします。
- **[[スタート] の [ピクチャ]]** - Windows のスタート メニューにあるピクチャのフォルダーを表示または非表示にします。
- **[[スタート] の [設定]]** - Windows のスタート メニューにある設定アプリを表示または非表示にします。
- **[[スタート] の [ビデオ]]** - Windows のスタート メニューにあるビデオのフォルダーを表示または非表示にします。
