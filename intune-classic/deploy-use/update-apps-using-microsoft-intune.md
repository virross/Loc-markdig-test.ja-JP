---
title: "アプリを更新する"
description: "新しいバージョンが必要な場合は、このトピックに含まれるアプリを更新する方法を参照してください。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b8495c50a040e6c6a7fe7777b9e415333088b5ac
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="update-apps-using-microsoft-intune"></a>Microsoft Intune を使用してアプリを更新する

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune は、アプリの更新プログラムを管理するのに役立ちます。 新しいバージョンが必要な場合は、このトピックに含まれるアプリを更新する方法を参照してください。

## <a name="how-to-update-apps"></a>アプリを更新する方法
展開しているアプリの新しいバージョンがリリースされるときに、Intune によって、新しいバージョンのアプリケーションを更新し、展開することができます。 展開のみを同じアプリの新しいバージョン (同じ識別子を使用) に置き換えることができます。 アプリの更新プログラムを使用して、別のアプリ パッケージで展開を更新することはできません。

### <a name="app-identifiers"></a>アプリ識別子
アプリ識別子は、アプリを一意に識別するプロパティです。 同じ識別子を持つアプリの複数のコピーをインストールすることはできません。 次に、アプリ ID の例をいくつか示します。

- **iOS** - バンドル ID (例: com.microsoft.excel)
- **Android** - パッケージ ID (例: com.microsoft.excel)
- **Windows Phone** - (xap インストーラー) 製品 ID (GUID) を使用
- **Windows** - (appx/appxbundle) パッケージの完全名を使用



> [!IMPORTANT]
> **[必須のインストール]** の展開アクションでアプリを展開し、その後、展開アクションを **[利用可能なインストール]** に変更した場合、アプリの更新プログラムは、展開を変更する前にアプリをインストールしたデバイスに自動的にインストールされません。 この問題を解決するには、次のことを行います。
>
> -   デバイスのユーザーに対して、ポータル サイトに移動し、インストールされているアプリを選択し、**[インストール]** を選択するように指示します。
> -   展開アクションを **[アンインストール]** に変更します。アプリがアンインストールされた後で、**[利用可能なインストール]** の展開アクションでアプリを再展開します。

### <a name="to-update-an-app"></a>アプリを更新するには

1.  [Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[アプリ]** &gt; **[アプリ]** の順に選びます。

2.  **[アプリ]** ボックスの一覧で、更新するアプリを選択し、**[編集]** を選択します。

3.  **ソフトウェアの編集** ウィザードで、新しいアプリ パッケージの詳細を指定します。

4.  終了したら、**[更新]** を選択します。

次回デバイスが利用可能なアプリを確認するときに、アプリが自動的に最新バージョンに更新されます。
アプリをアプリ パッケージ (基幹業務アプリ) からインストールした場合、アプリに同じ ID が与えられている限り、必須の展開と利用可能な展開の両方に対してアプリが自動的にアップグレードされます。

アプリがストア リンクとして展開されている場合、アプリの取得元であるストアにより更新が管理されます。
