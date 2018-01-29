---
title: "管理対象の業務用アプリのデータをワイプする"
description: "リモートでデバイスから会社のデータを選択的に削除する方法について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4b3211f581da83f7de571150cfae9d277cc4107e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="wipe-company-app-data-with-intune-mam"></a>業務用アプリのデータを Intune MAM でワイプする

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

デバイスが紛失や盗難にあった場合、または従業員が離職した場合、会社のアプリのデータがデバイスから削除されたことを確認する必要があります。 ただし、個人のデータをデバイスから削除するのは好ましくありません。そのデバイスの所有者が従業員である場合はなおさらです。

会社のアプリ データを選択して削除するには、このトピックの手順を使用してワイプ要求を作成します。 ワイプ要求の完了後、次にデバイス上でアプリが実行されると、そのアプリから会社のデータが削除されます。

>[!IMPORTANT]
> アプリケーションからネイティブ アドレス帳に直接同期された連絡先が削除されます。 ネイティブ アドレス帳から別の外部ソースに同期された連絡先はワイプできません。 現在、これは Microsoft Outlook アプリにのみ適用されます。

## <a name="create-a-wipe-request"></a>ワイプ要求の作成

1.  [Azure ポータル](https://portal.azure.com)にサインインします。

2.  **[その他のサービス]** を選択し、フィルター ボックスに「**Intune**」と入力して、**[Intune App Protection (Intune アプリ保護)]** を選択します。 [Intune モバイル アプリケーション管理] ブレードが開きます。

    ![[新しいワイプ要求] ブレードのスクリーンショット](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  **[設定]** ブレードで、**[ワイプ要求]** をクリックします。

3.  **[新しいワイプ要求]** を選択します。 **[新しいワイプ要求]** ブレードが開きます。

    ![[新しいワイプ要求] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  **[ユーザー]** を選択して **[ユーザー]** ブレードを開き、アプリ データをワイプするユーザーを選びます。

5.  **[デバイス]** を選択します。 これにより **[デバイス]** ブレードが開き、選択したユーザーに関連付けられているデバイスの一覧が表示されます。また、このブレードには 2 つの列があり、デバイス名 (ユーザーによって定義されるフレンドリ名) とデバイスの種類 (デバイスのプラットフォーム) が示されます。 ワイプするデバイスを選びます。

6.  **[新しいワイプ要求]** ブレードに戻ります。 **[OK]** を選択してワイプ要求を行います。 

サービスでは、デバイス上の保護されているアプリごとにワイプ要求が作成および追跡され、そのワイプ要求にはユーザーが関連付けられています。

>[!NOTE]
> [Intune モバイル アプリケーション管理] ブレードで **[ワイプ要求]** タイルをクリックして、**ワイプ要求**を作成することもできます。

## <a name="monitor-your-wipe-requests"></a>ワイプ要求を監視する

ワイプ要求の全体的状態、保留中の要求の数、失敗の数がまとめてある概要レポートを設定できます。 さらに詳しい情報が必要な場合、次の手順を実行します。

1.  [Intune モバイル アプリケーション管理] ブレードで **[ワイプ要求]** タイルをクリックします。

2.  **[ワイプ要求]** ブレードで、**[ワイプ要求]** タイルを選択し、**[ワイプ要求]** ブレードを開きます。

3.  **[ワイプ要求]** ブレードでは、要求をユーザー別にグループ化して一覧表示できます。 ワイプ要求はデバイスで実行されている保護アプリごとに作成されるため、1 ユーザーに対する要求が複数ある場合があります。 状態は、ワイプ要求が **[保留中]**、**[失敗]**、または **[成功]**のいずれかであることを示します。

    ![[新しいワイプ要求] ブレードのスクリーンショット](../media/AppManagement/wipe-request-status-1.png)

さらに、デバイス名とそのデバイスの種類を確認することもできます。これは、レポートを読み取るときに役に立つことがあります。

>[!IMPORTANT]
> ワイプを実行するにはユーザーがアプリを開く必要があるため、ワイプには要求後最大で 30 分かかる場合があります。

## <a name="delete-a-wipe-request"></a>ワイプ要求の削除

[保留中] 状態のワイプは、手動で削除するまで表示されます。  ワイプ要求を手動で削除するには、次の手順を実行します

1.  [Intune モバイル アプリケーション管理] ブレードで **[ワイプ要求]** タイルをクリックします。

2.  **[ワイプ要求]** ブレードで、**[ワイプ要求]** タイルを選択し、**[ワイプ要求]** ブレードを開きます。

3.  削除するワイプ要求を右クリックし、**[Delete wipe request (ワイプ要求の削除)]** を選択します。

    ![[新しいワイプ要求] ブレードのスクリーンショット](../media/AppManagement/delete-wipe-request.png)

4.  削除を確認するメッセージが表示されたら、**[はい]** または **[いいえ]** を選択し、**[OK]** をクリックします。


### <a name="see-also"></a>関連項目
[モバイル アプリケーション管理ポリシーを使用してデータを保護する](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Azure Portal の使用](azure-portal-for-microsoft-intune-mam-policies.md)
