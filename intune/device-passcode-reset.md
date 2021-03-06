---
title: "Intune でデバイスのパスコードをリセットして削除する"
titlesuffix: Azure portal
description: "Intune で管理するデバイスのパスコードをリセットして削除する方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 591939c50ef093235b8b63589476012b69f204e1
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Intune で管理するデバイスのパスコードをリセットして削除する


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

この記事では、*削除*と*リセット*という用語は同じ意味で使用されます。

**[パスコードの削除]** アクションは、デバイスの新しいパスコードを生成します。新しいパスコードは、[<*デバイス名*> **概要**] ブレードに表示されます。

## <a name="supported-platforms"></a>サポートされているプラットフォーム

- Windows - サポートされていません
- Windows Phone - Windows Phone 8.1 から Azure AD に参加していない Windows 10 Creators Update まで、Windows 10 Creators Update 以降でサポートされています
- iOS - サポートされています
- macOS - サポートされていません
- Android - Android 7 より前の Android バージョンでサポートされています。 Android for Work はサポートされていません。

## <a name="how-to-reset-a-passcode"></a>パスコードをリセットする方法

1. Azure Portal にサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[デバイス]** を選択します。
4. **[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。
5. 管理するデバイスの一覧からデバイスを選択し、その後 **[パスコードの削除]** デバイス リモート アクションを選択します。

## <a name="next-steps"></a>次の手順

実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。
