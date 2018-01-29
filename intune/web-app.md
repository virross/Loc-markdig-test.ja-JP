---
title: "Web アプリを Intune に追加する方法"
titleSuffix: Azure portal
description: "Web アプリを Intune に追加する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ebe4b31c85e0c0bc88f49d28e28ea7eac191951f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Web アプリを Microsoft Intune に追加する方法

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

管理し、ユーザーのアプリを割り当てることができます、前に、アプリを Intune に追加する必要があります。 Intune では、Web アプリなど、さまざまなアプリの種類がサポートされています。

> [!Note]
> Web アプリは、Android for Work デバイスではサポートされていません。

次の手順では web 上のアプリへのショートカットとしてアプリを Intune に追加することを許可します。

1. Azure Portal にサインインします。
2. **[More resources]\(その他のリソース\)** で、**[Intune]** を検索して選択します。
3. **[Microsoft Intune]** ブレードで、**[モバイル アプリ]** を選択します。
4. **[モバイル アプリ]** ブレードで、**[アプリ]** を選択します。
5. アプリの一覧の上にある **[追加]** を選択します。 **追加アプリ**ブレードが表示されます。
6. **[アプリの追加]** ブレードで、**[アプリの種類]** ドロップダウン リストから **[Web アプリ]** という種類を選択します。
7. **[構成]** オプションを選択して **[アプリ情報]** ブレードを表示します。
8. **[アプリ情報]** ブレードで、以下の情報を追加します。
    - **名前** - アプリの名前を入力します。この名前は会社のポータルに表示されます。
    - **説明** - アプリの説明を入力します。 これは会社のポータルでエンド ユーザーに表示されます。
    - **[発行元]** - このアプリの発行元の名前を入力します。
    - **[アプリ URL]** - 割り当てるアプリをホストする Web サイトの URL を入力します。
    - **[カテゴリ]** (省略可能) - 1 つ以上の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。 会社のポータルを閲覧するとき、ユーザーにとってアプリを探すのが簡単になります。
    - **[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。
    - **[このリンクを開くには Managed Browser が必要です]** - Web サイトまたは Web アプリへのリンクをユーザーに割り当てると、ユーザーは Intune Managed Browser でのみリンクを開くことができるようになります。 このブラウザーをデバイスにインストールする必要があります。
    - **ロゴ**-は、アプリに関連付けられるロゴをアップロードします。 これは、ユーザーがポータル サイトを参照すると、アプリに表示されるロゴです。
9. 完了したら、**[情報の追加]** ブレードで、**[OK]** を選択します。
10. 次に、**[アプリの追加]** ブレードで **[追加]** を選択します。

作成したアプリはアプリの一覧に表示され、選択したグループに割り当てることができるようになります。 詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。