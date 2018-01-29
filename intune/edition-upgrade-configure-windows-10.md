---
title: "Intune で Windows 10 エディションのアップグレードを構成する"
titlesuffix: Azure portal
description: "Intune を使用して、管理対象の Windows 10 デバイスを別のエディションにアップグレードする方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 979bae8fffff211b869e73bf39ae3552fbad9d6d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Microsoft Intune で Windows 10 エディションのアップグレードを構成する方法

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

このトピックでは、Windows 10 エディションのアップグレード プロファイルを構成する方法について説明します。 このプロファイルを使用して、次に挙げる Windows 10 のバージョンのいずれかを実行するデバイスを自動的に別のエディションにアップグレードできます。

- Windows 10 Home
- Windows 10 Holographic
- Windows 10 Mobile


次のアップグレード パスがサポートされます。

- Windows 10 Pro から Windows 10 Enterprise へのアップグレード パス
- Windows 10 Home から Windows 10 Education へのアップグレード パス
- Windows 10 Mobile から Windows 10 Mobile Enterprise へのアップグレード パス
- Windows 10 Holographic windows 10 Holographic for Business


## <a name="before-you-start"></a>開始する前に
デバイスを最新バージョンにアップグレードし始める前に、次のいずれかを用意する必要があります。

- ポリシーで対象とするすべてのデバイスに新しいバージョンの Windows をインストールするための有効なプロダクト キー (Windows 10 Desktop エディションの場合)。 マルティプル アクティベーション キー (MAK)、キー マネジメント サーバー (KMS) キー、またはポリシーで対象とするすべてのデバイスに新しいバージョンの Windows をインストールするためのライセンス情報を含む、Microsoft からのライセンス ファイル (Windows 10 Mobile エディションと Windows 10 Holographic エディションの場合) を使うことができます。
- ポリシーを割り当てる Windows 10 デバイスが、Microsoft Intune に登録されている必要があります。 エディションのアップグレード ポリシーは、Intune PC クライアント ソフトウェアを実行する PC で使用できません。

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>デバイスの制限設定を含むデバイス プロファイルの作成

1. Azure Portal にサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[デバイス構成]** を選択します。
2. **[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。
3. [プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。
4. **[プロファイルを作成します]** ブレードで、エディションのアップグレード プロファイルの**名前**と**説明**を入力します。
5. **[プラットフォーム]** ドロップダウン リストで、**[Windows 10 以降]** を選択します。
6. **[プロファイルの種類]** ドロップダウン リストで、**[エディションのアップグレード]** を選択します。
7. **[エディションのアップグレード]** ブレードで、以下の設定を構成します。
    - **[アップグレードのターゲット エディション]** - 対象のデバイスのアップグレード先となる Windows 10 Desktop、Windows 10 Holographic、または Windows 10 Mobile のバージョンをドロップダウン リストから選びます。
    - **[プロダクト キー]** - Microsoft から取得した、対象とするすべての Windows 10 デスクトップ デバイスをアップグレードするために使用できるプロダクト キーを指定します。<br>プロダクト キーを含むポリシーを作成した後でプロダクト キーを編集することはできません。 これは、セキュリティ上の理由からキーが隠されるためです。 プロダクト キーを変更するには、キー全体を再入力する必要があります。
    - **[ライセンス ファイル]** - **[参照]** を選択し、Microsoft から取得した、対象とするデバイスのアップグレード後の Windows Holographic、または Windows 10 Mobile エディション用のライセンス情報を含むライセンス ファイルを選択します。
8. 完了したら、**[プロファイルを作成します]** ブレードに戻り、**[作成]** をクリックします。

プロファイルが作成され、プロファイルの一覧ブレードに表示されます。

## <a name="next-steps"></a>次の手順

このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。

>[!NOTE]
>後でポリシーの割り当てを削除する場合、デバイス上の Windows のバージョンは元に戻されず、正常に機能を続けます。

