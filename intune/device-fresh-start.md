---
title: "Intune が稼働する Windows 10 デバイスのリセット"
titlesuffix: Azure portal
description: "[新たに開始] を使用して、Intune が稼働する Windows 10 PC をリセットする方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 503780de384521bfae2ca8e22bdbae1b60d3a64d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>[新たに開始] を使用して Intune が稼働する Windows 10 デバイスをリセットする


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**[新たに開始]** デバイス アクションを実行すると、Creators Update が稼働する Windows 10 PC にインストールされているすべてのアプリが削除され、PC が Windows の最新バージョンに自動的に更新されます。
この機能は、新しい PC に付属することの多い事前インストール済み (OEM) アプリを削除するのに使うことができます。 このデバイス アクションを発行するときにユーザー データを保持するかどうかを構成できます。 この場合、アプリと設定は削除されますが、ユーザーのホーム フォルダーの内容は保持されます。

## <a name="how-to-use-fresh-start"></a>新たに開始の使用方法

1. Azure Portal にサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[デバイス]** を選択します。
4. **[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。
5. 管理するデバイスの一覧から Windows 10 デスクトップ デバイスを選択し、その後 **[新たに開始]** デバイス リモート アクションを選択します。

## <a name="next-steps"></a>次の手順

実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。

