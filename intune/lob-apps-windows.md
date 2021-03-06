---
title: "Windows の基幹業務アプリを Intune に追加する方法"
titlesuffix: Azure portal
description: "Windows の基幹業務アプリを Intune に追加する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41cdebfc3cd9072519df8e538617bdb29609d4e1
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Windows の基幹業務 (LOB) アプリを Microsoft Intune に追加する方法

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="step-1---specify-the-software-setup-file"></a>手順 1 - ソフトウェアのセットアップ ファイルを指定する

1. Azure ポータルにサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[アプリの管理]** を選択します。
4. **[モバイル アプリ]** ワークロードで、**[管理]** > **[アプリ]** の順に選択します。
5. アプリの一覧の上にある **[追加]** を選択します。
6. **[アプリの追加]** ブレードで、**[基幹業務アプリ]** を選択します。

## <a name="step-2---configure-the-app-package-file"></a>手順 2 - アプリのパッケージ ファイルを構成する

1. **[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。
2. **[アプリのパッケージ ファイル]** ブレードで、参照ボタンを選択し、拡張子 **.msi**、**.appx**、または **.appxbundle** が付いた Windows インストール ファイルを選択します。
3. 終了したら **[OK]** を選択します。


## <a name="step-3---configure-app-information"></a>手順 3 - アプリ情報を構成する

1. **[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。
2. **[アプリ情報]** ブレードで、次の情報を構成します (このブレードの値の一部は、自動的に入力されている場合があります)。
    - **[名前]** - アプリの名前を入力します。この名前は会社のポータルに表示されます。 使用するアプリ名はすべて一意にします。 同じアプリ名が 2 つ存在する場合、会社のポータルではそのいずれかのみがユーザーに表示されます。
    - **説明** - アプリの説明を入力します。 説明はポータル サイトでユーザーに表示されます。
    - **[発行元]** - アプリの発行元の名前を入力します。
    - **[カテゴリ]** - 1 つまたは複数の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。 アプリをカテゴリに分けると、会社のポータルを閲覧するとき、ユーザーにとってアプリを探すのが簡単になります。
    - **[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。
    - **[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。 この URL は会社のポータルでユーザーに表示されます。
    - **[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。 この URL は会社のポータルでユーザーに表示されます。
    - **[コマンド ライン引数]** - 必要に応じて、実行時に .msi ファイルに適用するコマンド ライン引数を入力します (**/q** など)。
    - **[開発者]** - 必要に応じて、アプリ開発者の名前を入力します。
    - **[所有者]** - 必要に応じて、このアプリの所有者の名前 ("**人事部**" など) を入力します。
    - **[メモ]** - このアプリに関連付けるメモを入力します。
    - **[ロゴ]** - アプリに関連付けるアイコンをアップロードします。 ユーザーが会社のポータルを参照するとき、アプリにアイコンが表示されます。
3. 終了したら **[OK]** を選択します。

## <a name="step-4---finish-up"></a>手順 4. - 完了

1. **[アプリの追加]** ブレードで、構成したアプリ情報が正しいことを確認します。
2. **[追加]** を選択して、アプリを Intune にアップロードします。

## <a name="step-5---update-a-line-of-business-app"></a>手順 5 - 基幹業務アプリの更新

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="next-steps"></a>次の手順

作成したアプリがアプリの一覧に表示されます。 選択したグループにアプリを割り当てることができます。 詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。

アプリのプロパティと割り当てを監視する方法について説明します。 詳細については、「[アプリ情報と割り当てを監視する方法](apps-monitor.md)」を参照してください。

Intune におけるアプリのコンテキストについて説明します。 詳細については、「[デバイスとアプリのライフサイクルの概要](introduction-device-app-lifecycles.md)」を参照してください。