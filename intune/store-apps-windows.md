---
title: "Windows ストア アプリを Intune に追加する方法"
titleSuffix: Azure portal
description: "Windows ストア アプリを Intune に追加する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b037ea7a57ae0b99aa8099f6afe8505c86aad2d2
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Windows ストア アプリを Microsoft Intune に追加する方法

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Azure Portal にサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[アプリの管理]** を選択します。
4. **[モバイル アプリ]** ワークロードで、**[管理]** > **[アプリ]** の順に選択します。
5. アプリの一覧の上にある **[追加]** を選択します。
6. **[アプリの追加]** ブレードで、**[アプリ情報]** を選択します。
7. **[アプリの編集]** ブレードで、以下の情報を構成します。 構成が終わったら、**[追加]** をクリックします。 選択したアプリによっては、このブレード内の一部の値が自動的に入力されている場合があります。
    - **[アプリ名]** - アプリの名前を入力します。この名前は会社のポータルに表示されます。 使用するアプリ名はすべて一意にします。 同じアプリ名が 2 つ存在する場合、会社のポータルではそのいずれかのみがユーザーに表示されます。
    - **[アプリの説明]** - アプリの説明を入力します。 これは会社のポータルでユーザーに表示されます。
    - **[発行元]** - アプリの発行元の名前を入力します。
    - **[アプリ ストア URL]** - 作成するアプリのアプリ ストア URL を入力します。
    - **[オペレーティング システムの最小要件]** - アプリをインストールできる最小限のオペレーティング システム バージョンを一覧から選択します。 これよりも前のオペレーティング システムがアプリの割り当て先デバイスにインストールされている場合、そのアプリはインストールされません。
    - **[カテゴリ]** (省略可能) - 1 つ以上の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。 会社のポータルを閲覧するとき、ユーザーにとってアプリを探すのが簡単になります。
    - **[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。
    - **[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。 この URL は会社のポータルでユーザーに表示されます。
    - **[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。 この URL は会社のポータルでユーザーに表示されます。
    - **[開発者]** - 必要に応じて、アプリ開発者の名前を入力します。
    - **[所有者]** - 必要に応じて、このアプリの所有者の名前 ("**人事部**" など) を入力します。
    - **[メモ]** - このアプリに関連付けるメモを入力します。
    - **[アップロード アイコン]** - アプリに関連付けるアイコンをアップロードします。 ユーザーが会社のポータルを参照するとき、アプリにこのアイコンが表示されます。
8. 構成が終了したら、**[アプリの追加]** ブレードで、**[保存]** を選択します。

作成したアプリはアプリの一覧に表示され、選択したグループに割り当てることができるようになります。 詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。

## <a name="manually-assign-windows-10-company-portal-app"></a>Windows 10 ポータル サイト アプリの手動割り当て
エンド ユーザーは Microsoft ストアからポータル サイト アプリをインストールすることで、デバイスを管理し、アプリをインストールすることができます。 ただし、ビジネスでポータル サイト アプリを割り当てる必要がある場合は、Intune をビジネス向け Microsoft ストアと統合していない場合でも、Intune から直接 Windows 10 ポータル サイト アプリを手動で割り当てることができます。

 > [!NOTE]
 > このオプションでは、アプリの更新プログラムがリリースされるたびに、手動更新を割り当てる必要があります。

1. [ビジネス向け Microsoft ストア](https://www.microsoft.com/business-store)のアカウントにログインし、ポータル サイト アプリの**オフライン ライセンス** バージョンを取得します。  
2. アプリが取得されたら、**[インベントリ]** ページでアプリを選択します。  
3. **プラットフォーム**として **[Windows 10 all devices (Windows 10 のすべてのデバイス)]** を選択し、適切な**アーキテクチャ**を選択してダウンロードします。 このアプリは、アプリ ライセンス ファイルを必要としません。
![ダウンロードする Windows 10 のすべてのデバイスと Architecture X86 Package のイメージ](./media/Win10CP-all-devices.png)
4. [必要なフレームワーク] の下のすべてのパッケージをダウンロードします。 x86、x64、および ARM アーキテクチャ用に実行する必要があります。次に示すように、合計 9 個のパッケージのダウンロードが必要になる場合があります。

![ダウンロードする依存関係ファイルのイメージ ](./media/Win10CP-dependent-files.png)
5. ポータル サイト アプリを Intune にアップロードする前に、パッケージを次のように構成してフォルダー (C:&#92;ポータル サイトなど) を作成します。
   1. C:\ポータル サイトにポータル サイト パッケージを配置します。 また、この場所に依存関係サブフォルダーも作成します。  
   ![APPXBUN ファイルと共に保存された依存関係フォルダーのイメージ](./media/Win10CP-Dependencies-save.png)
   2. 依存関係フォルダーに 9 つの依存関係パッケージを配置します。  
   依存関係がこの形式で配置されていないと、Intune はパッケージのアップロード時にこれらを認識、アップロードすることができます、次のエラーでアップロードが失敗します。  
   ![このソフトウェア インストーラーに関する Windows アプリの依存関係がアプリケーション フォルダー内で見つかりませんでした。 このアプリケーションの作成と割り当てを続行できますが、不明な Windows アプリの依存関係が提供されるまでは実行されません。](./media/Win10CP-error-message.png)
6. Intune に戻り、ポータル サイト アプリを新しいアプリとしてアップロードします。 これを必要なアプリとして対象の一連のターゲット ユーザーに割り当てます。  

Intune がユニバーサル アプリ用に依存関係をどのように処理するかについて詳しくは、「[Deploying an appxbundle with dependencies via Microsoft Intune MDM (Microsoft Intune MDM 経由で依存関係を使用して appxbundle を展開する)](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/)」ご覧ください。  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>ユーザーがストアから古いアプリを既にインストールしている場合に、ユーザーのデバイスのポータル サイトを更新する方法
貴社のユーザーがストアから Windows 8.1 または Windows Phone 8.1 ポータル サイト アプリを既にインストールしている場合は、お客様またはお客様のユーザーが特に操作を行わなくても新しいバージョンに自動的に更新されます。 更新が実行されない場合は、デバイスでストア アプリの自動更新を有効にしているかどうかをユーザーに確認してください。   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>サイドロードした Windows 8.1 のポータル サイト アプリを Windows 10 のポータル サイト アプリにアップグレードする方法
推奨される移行パスとして、割り当てアクションを "アンインストール" に設定して、Windows 8.1 ポータル サイト アプリの割り当てを削除します。 これが完了したら、上記のいずれかのオプションを使用して、Windows 10 ポータル サイト アプリを割り当てできるようになります。  

アプリをサイドロードする必要があり、Symantec 証明書で署名せずに Windows 8.1 ポータル サイトを割り当てた場合は、上の Intune セクションから直接、割り当てに関する手順に従ってアップグレードを完了します。

アプリをサイドロードする必要があり、Symantec コード署名証明書で Windows 8.1 ポータル サイトに署名し割り当てた場合は、以下のセクションの手順に従ってください。  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>署名およびサイドロードした Windows Phone 8.1 ポータル サイト アプリまたは Windows 8.1 ポータル サイト アプリを Windows 10 ポータル サイト アプリにアップグレードする方法
推奨される移行パスとして、割り当てアクションを "アンインストール" に設定して、Windows Phone 8.1 ポータル サイト アプリまたは Windows 8.1 ポータル サイト アプリの既存の割り当てを削除します。 これが完了したら、通常どおり Windows 10 ポータル サイト アプリを割り当てできるようになります。  

これ以外の場合は、アップグレードのパスが確実に考慮されるように Windows 10 ポータル サイト アプリを適切に更新し、署名する必要があります。  

この方法で Windows 10 ポータル サイト アプリに署名し割り当てた場合、ストアで入手可能になった新しいアプリの更新プログラムごとにこのプロセスを繰り返す必要があります。 ストアが更新されたときに、アプリは自動的に更新されません。  

この場合のアプリへの署名および割り当て方法は、次のとおりです。

1. Microsoft Intune Windows 10 ポータル サイト アプリの署名スクリプトを [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) からダウンロードします。  このスクリプトでは、Windows SDK for Windows 10 をホスト コンピューターにインストールする必要があります。 Windows SDK for Windows 10 をダウンロードするには、[https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) にアクセスします。
2. 上記の説明のように、ビジネス向け Microsoft ストアから Windows 10 ポータル サイト アプリをダウンロードします。  
3. スクリプト ヘッダーに記載された入力パラメーターを使用してスクリプトを実行し、Windows 10 ポータル サイト アプリに署名します (以下に抜粋)。 スクリプトに依存関係を渡す必要はありません。 依存関係は、アプリが Intune 管理コンソールにアップロードされる場合にのみ必要です。

|パラメーター | 説明|
| ------------- | ------------- |
|InputWin10AppxBundle |ソース appxbundle ファイルが配置されるパス |
|OutputWin10AppxBundle |署名された appxbundle ファイルの出力パス  Win81Appx Windows 8.1 または Windows Phone 8.1 ポータル サイト (.APPX) ファイルが配置されるパス|
|PfxFilePath |Symantec エンタープライズ モバイル コード署名証明書 (.PFX) ファイルへのパス |
|PfxPassword| Symantec エンタープライズ モバイル コード署名証明書のパスワード |
|PublisherId |エンタープライズの発行者 ID 指定しない場合、Symantec エンタープライズ モバイル コード署名証明書の 'Subject' フィールドが使用されます。|
|SdkPath | Windows SDK for Windows 10 のルート フォルダーへのパス この引数は省略可能で、既定値は ${env:ProgramFiles(x86)}\Windows Kits\10 です。|

実行が終了したら、スクリプトにより Windows 10 ポータル サイト アプリの署名されたバージョンが出力されます。 その後、アプリの署名されたバージョンを Intune 経由で LOB アプリとして割り当てることができます。これにより、現在割り当てられているバージョンがこの新しいアプリにアップグレードされます。  
