---
title: "現在のユーザー - Intune データ ウェアハウス |Microsoft ドキュメント"
description: "Intune データ ウェアハウス API のエンティティ コレクションのユーザー カテゴリに関するリファレンス トピック。"
keywords: "Intune データ ウェアハウス"
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cabf39f603ac93a0716594c44174908e7c999e5c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-current-user-entity"></a>現在のユーザー エンティティの参照

**現在のユーザー**カテゴリには、データ モデルでユーザーのプロパティが含まれています。 **現在のユーザー** エンティティ コレクションは、現在アクティブなユーザーに限られています。 エンティティには、現在ライセンスが割り当てられているすべての Azure Active Directory ユーザーが含まれています。 ライセンスは、Intune ライセンス、ハイブリッド ライセンス、または Microsoft Office 365 ライセンスです。 ユーザーが削除された場合、それらが表示されません、現在のユーザー コレクションにします。 ユーザー状態の変更の履歴を含むコレクションについては、「[ユーザー エンティティのリファレンス](reports-ref-user.md)」をご覧ください。


## <a name="current-user"></a>現在のユーザー

**現在のユーザー**エンティティには、企業内の割り当てられたライセンスを持つすべての Azure Active Directory (Azure AD) ユーザーが一覧表示します。

| プロパティ  | 説明 | 例 |
|---------|------------|--------|
| UserKey |データ ウェアハウス内のユーザーを示す一意識別子 - 代理キー。 |123 |
| UserId |ユーザーを示す一意識別子 - UserKey と似ていますが、ナチュラル キーです。 |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |ユーザーの電子メール アドレス。 |John@constoso.com |
| UPN | ユーザーのユーザー プリンシパル名。 | John@constoso.com |
| 表示名 |ユーザーの表示名。 |John |
| IntuneLicensed |ユーザーに Intune のライセンスがあるかどうかを示します。 |真/偽 |
| StartDateInclusiveUTC |このユーザーがデータ ウェアハウスで作成されたときの UTC 日時。 |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |このユーザーがデータ ウェアハウスで最後に変更されたときの UTC 日時。 |11/23/2016 12:00:00 AM |

## <a name="next-steps"></a>次のステップ
 - 使用することができます、**ユーザー**ユーザー データを現在アクティブではないユーザーに展開するエンティティのコレクション。 詳細については、「[ユーザー エンティティのリファレンス](reports-ref-user.md)」をご覧ください。
 - データ ウェアハウスが Intune のユーザーの有効期間を追跡する方法の詳細については、「[Intune データ ウェアハウスのユーザー有効期間の表記](reports-ref-user-timeline.md)」をご覧ください。
