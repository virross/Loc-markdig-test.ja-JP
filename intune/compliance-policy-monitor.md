---
title: "Intune デバイスのコンプライアンス対応ポリシーの監視"
titlesuffix: Azure portal
description: "デバイスのコンプライアンス対応ポリシーを監視する方法について説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 503d1dd2-a647-4aea-bf48-55319a3dd8a7
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4b293ff41af58d4ab41a8477219939b13ffe361c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="monitor-intune-device-compliance-policies"></a>Intune デバイスのコンプライアンス対応ポリシーの監視

コンプライアンス対応レポートを使用すると、管理者は組織内のデバイスのコンプライアンス対応の状況を分析して、組織内のユーザーがコンプライアンス関連の問題に直面したときに迅速にトラブルシューティングすることができます。 デバイスの総合的なコンプライアンスの状態、設定別のコンプライアンスの状態、およびポリシー別のコンプライアンスの状態に関する情報を表示し、個々のデバイスにドリルダウンして、デバイスに影響を与える特定の設定やポリシーを表示することができます。

## <a name="before-you-begin"></a>始める前に

次の手順に従って、Azure ポータルで **Intune Device compliance dashboard (Intune デバイス コンプライアンス ダッシュボード)** を見つけます。

1.  [Azure Portal](https://portal.azure.com) に移動し、Intune 資格情報でサインインします。

2.  左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。

3.  **[Intune]** &gt; **[デバイスのポリシー準拠]** &gt; **[概要]** の順に選択すると、**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** が開きます。

> [!IMPORTANT] 
> デバイスのコンプライアンス ポリシーを受け取るには、Intune にデバイスを登録する必要があります。

## <a name="device-compliance-dashboard"></a>デバイス コンプライアンス ダッシュボード

**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** で、デバイスのコンプライアンス ポリシーの状態を監視できます。このダッシュボードでは、組織内のデバイスのコンプライアンスの状況を表示するさまざまなタイル内で多数のレポートを使用できます。 表示できるレポートは、次のとおりです。

-   全体的なデバイスのコンプライアンス対応の集計

-   ポリシーごとのデバイスのコンプライアンス対応

-   設定ごとのデバイスのコンプライアンス対応

![デバイス コンプライアンス ダッシュボード](./media/idc-1.png)

また、個々のデバイスに適用される特定のコンプライアンス ポリシーおよび設定や、デバイスのこれらの設定ごとのコンプライアンスの最終状態を表示することもできます。

### <a name="overall-device-compliance-aggregate-report"></a>全体的なデバイスのコンプライアンス対応集計レポート

Intune に登録されたすべてのデバイスの集約されたコンプライアンス対応状態を示すドーナツ グラフです。 デバイスのコンプライアンス対応状態は、Intune と Azure Active Directory の 2 つの異なるデータベースで保持されます。 デバイスのコンプライアンス対応ポリシーの詳細は、次のとおりです。

-   **準拠**: デバイスに管理者が適用対象とするデバイス コンプライアンス ポリシーが 1 つ以上適切に適用されています。

-   **非準拠:** 管理者またはユーザーが適用対象とするデバイス コンプライアンス ポリシーの設定の 1 つ以上の適用に失敗し、管理者が適用対象とするポリシーに準拠していません。

-   **猶予期間:** デバイスは 1 つ以上のデバイス コンプライアンス ポリシー設定を持つことを管理者によって指定されているものの、ユーザーがまだポリシーを適用していないことを示します。つまり、デバイスは非準拠ですが、管理者が定義した猶予期間にあります。

    -   コンプライアンス非対応のデバイスのアクションの詳細は次のとおりです。

-   **同期されていないデバイス:** 次のいずれかの理由により、デバイスがデバイス コンプライアンス ポリシーの状態の報告に失敗しています。

    -   **不明**: デバイスが何らかの理由でオフラインか、Intune または Azure AD との通信に失敗しています。

    -   **エラー**: デバイスが Intune および Azure AD との通信に失敗し、何らかの理由でエラー メッセージを受信しました。

> [!IMPORTANT] 
> Intune に登録されていないが、デバイス コンプライアンス ポリシーの適用対象となっているデバイスは、**[準拠]** バケットでこのレポートに含まれます。

#### <a name="drill-down-option"></a>ドリルダウン オプション

**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** で、[デバイスのポリシー準拠] タイルをクリックして、デバイス コンプライアンス ポリシーの対象となっている各デバイスの特定の**準拠状態**、**ユーザーの電子メール エイリアス**、**デバイス モデル**、および**場所**の詳細な情報を表示できます。

![デバイス コンプライアンス ダッシュボードでのドリルダウン](./media/idc-2.png)

特定のユーザーの詳細情報が必要な場合は、ユーザーの電子メール エイリアスを入力して、デバイスのポリシー準拠チャート レポートをフィルターできます。

![デバイス コンプライアンス ダッシュボードの特定のユーザー](./media/idc-3.png)

また、デバイスのポリシー準拠チャートでさまざまなコンプライアンス対応状態をクリックして、ユーザーのデバイス コンプライアンス ポリシー状態の詳細を表示することもできます。

![デバイス コンプライアンス ダッシュボードのさまざまな状態](./media/idc-4.png)

#### <a name="filter"></a>フィルター

**[フィルター]** ボタンをクリックすると、次のオプションを示すフィルターのフライアウトが表示されます。

-   モデル

    -   テキストボックスで文字列を無料で検索できます
<br></br>
-   プラットフォーム

    -   Android

    -   iOS

    -   Mac OS

    -   Windows

    -   Windows Phone

-   状態

    -   準拠

    -   非準拠

    -   猶予時間中

    -   Unknown

    -   エラー

**[更新]** ボタンをクリックすると、フライアウトが閉じ、選択したフィルター条件に従って結果が更新されます。

##### <a name="device-details"></a>デバイスの詳細

デバイスをクリックすると、選択したデバイスで**デバイス ブレード**が開きます。 ここに、そのデバイスに適用されているデバイス コンプライアンス ポリシー設定の詳細が示されます。

![デバイス コンプライアンス ダッシュボード](./media/idc-6.png)

デバイス ポリシーの設定自体をクリックすると、管理者が適用対象にしたデバイス コンプライアンス設定で指定されたデバイス コンプライアンス ポリシー名を確認できます。

![デバイス コンプライアンス設定の名前](./media/idc-7.png)

### <a name="per-policy-device-compliance-report"></a>ポリシーごとのデバイスのコンプライアンス対応レポート

このレポートは、コンプライアンス ポリシー ビューごとに、各コンプライアンス対応状態のデバイスの合計数を示します。 **[Policy compliance (ポリシー準拠)]** タイルは、**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** で利用でき、管理者が以前に作成したすべてのポリシー、ポリシーが適用されているプラットフォーム、準拠デバイスの数、および非準拠デバイスの数が表示されます。

![ポリシーごとのデバイスのコンプライアンス対応レポート](./media/idc-8.png)

[Policy compliance (ポリシー準拠)] タイルをクリックし、いずれかのデバイス コンプライアンス ポリシーをクリックすると、そのデバイス コンプライアンス ポリシーの対象にした各デバイスの**準拠状態**、**ユーザーの電子メール エイリアス**、**デバイス モデル**、および**場所**の詳細な情報を表示できます。

![[Policy compliance (ポリシー準拠)] タイル](./media/idc-9.png)

### <a name="per-setting-device-compliance-report"></a>設定ごとのデバイスのコンプライアンス対応レポート

このレポートでは、コンプライアンス設定ごとの、各コンプライアンス対応状態のデバイスの合計数を表示できます。 **[設定コンプライアンス]** タイルは、**Device compliance dashboard (デバイス コンプライアンス ダッシュボード)** で利用でき、管理者が以前に作成したすべてのデバイス コンプライアンス ポリシーのすべてのデバイス コンプライアンス ポリシー設定、ポリシー設定が適用されたプラットフォーム、および非準拠デバイスの数が表示されます。

![設定ごとのデバイスのコンプライアンス対応レポート](./media/idc-10.png)

[コンプライアンスの設定] タイルをクリックし、いずれかのデバイス コンプライアンス ポリシー設定をクリックすると、そのデバイス コンプライアンス ポリシー設定の対象にした各デバイスの**準拠状態**、**ユーザーの電子メール エイリアス**、**デバイス モデル**、および**場所**の詳細な情報を表示できます。

![[コンプライアンスの設定] タイル](./media/idc-11.png)
