---
title: "Intune のアクティビティの監査ログ"
description: "Intune のアクティビティを記録する監査ログを確認する方法をについてください。"
keywords: 
author: dougeby
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: 30067f60163a644f4347c51c249c25fb3428f8ba
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="audit-logs-for-intune-activities"></a>Intune のアクティビティの監査ログ
監査ログは、Microsoft Intune での変更を生成するアクティビティの記録を提供します。 作成、更新 (編集) を削除し、アクション、またはリモート タスクを割り当てるには、確認できる監査イベントを生成します。 Intune のほとんどのワークロードの監査ログを確認できます。 

## <a name="who-can-access-the-data"></a>データにアクセスできるユーザーですか。
次のアクセス許可を持つユーザーは、監査ログを確認できます。
- グローバル管理者
- Intune サービス管理者
- Intune の役割に割り当てられた管理者**監査データ** - **読み取り**アクセス許可

## <a name="audit-logs-for-intune-workloads"></a>Intune のワークロードの監査ログ
Intune で各ワークロードの監視グループにある監査ログを確認することができます。  
1. サインイン、 [Azure ポータル](https://portal.azure.com)します。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **Intune**ブレードで、監査ログを確認するワークロードを選択します。
4. **監視**ワークロード グループで、選択**監査ログ**です。

## <a name="review-audit-events"></a>監査イベントを確認します。
![監査ログ](./media/monitor-audit-logs.png "監査ログ")

監査ログには、次の項目を表示する既定のリスト ビューがあります。    

- 日付と時刻に見つかった位置の
- (アクター) によって開始されます。
- アクティビティ
- ターゲット
- Category
- 状態

リスト ビュー内の項目をクリックすると、それに関するすべての利用可能な詳細を取得します。

![監査ログ](./media/monitor-audit-log-detail.png "監査ログ")

> [!Note]    
> **(アクター) によって開始された**監査ログの詳細」セクションと実行された場所からアクティビティを実行したユーザーに関する情報を提供します。 たとえば、Azure ポータルで、Intune でアクティビティを実行する**アプリケーション**に常に表示**Microsoft Intune のポータルの拡張機能**と**アプリケーション ID**常に同じ GUID を使用します。 
>    
> **ターゲット**セクションでは、複数のターゲットと変更されたプロパティを一覧表示できます。  


## <a name="filter-audit-events"></a>監査イベントをフィルター処理します。
各ワークロードには、あらかじめ、そのブレードに関連付けられている監査イベントのカテゴリをフィルター処理するメニュー項目があります。 別個のフィルター オプションを使用して、別のカテゴリ、およびそのカテゴリ内のイベントのアクションの詳細を変更できます。 UPN (たとえば、ユーザー アクションをでした) によって検索することができます。 日付の範囲フィルターは、24 時間、7 日間、または 30 日間のオプションを使用します。 既定では、過去 30 日の監査イベントが表示されます。

## <a name="use-graph-api-to-retrieve-audit-events"></a>Graph API を使用して、監査イベントを取得するには
Graph API を使用して、監査イベントの最長 1 年間を取得する方法に関する詳細については、「 [auditEvents を一覧表示](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list)です。