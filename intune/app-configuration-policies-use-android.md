---
title: "管理対象の Android デバイス用アプリ構成ポリシーを追加する | Microsoft Docs"
titlesuffix: Azure portal
description: "アプリ構成ポリシーを使用して、実行時に構成データを Android for Work アプリに提供する方法について説明します。"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c60ed578c02a2b07b6c7c57067c3a3f37f2f6e42
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>管理対象の Android デバイス用アプリ構成ポリシーを追加する

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune のアプリ構成ポリシーを使用して、ユーザーが Android for Work アプリを実行するときに設定を指定します。 これらのポリシーをユーザーとデバイスに直接割り当てないでください。 代わりに、ポリシーをアプリに関連付け、そのアプリを割り当てます。 ポリシー設定は、アプリがポリシーをチェックするとき (通常はアプリの初回実行時) に使用されます。

> [!Note]  
> アプリ構成をサポートしていないアプリもあります。 ビルドされたアプリでアプリ構成ポリシーがサポートされているかどうかについては、アプリの開発者にお問い合わせください。

1. Azure ポータルにサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。
3. **[モバイル アプリ]** ワークロードを選択します。
4. **[管理]** グループの **[アプリ構成ポリシー]** を選択し、**[追加]** を選択します。
5. 次の詳細を設定します。
    - **名前**  
      Azure Portal に表示されるプロファイルの名前。
    - **説明**  
      Azure Portal に表示されるプロファイルの説明。
    - **デバイス登録の種類**  
      **[管理対象デバイス]** を選択します。
6. **[プラットフォーム]** に **[Android]** を選択します。
7. **[関連アプリ]** を選択し、アプリ構成ポリシーを定義するアプリを選択します。 承認して Intune に同期した Android for Work アプリの一覧から選択します。
8. **[構成設定]** を選択します。 以下を使用して構成を設定できます。
    - [構成デザイナー](#Use-the-configuration-designer)
    - [JSON エディター](#Enter-the-JSON-editor)
9. **[OK]** を選択してから、**[追加]** を選択します。

## <a name="use-the-configuration-designer"></a>構成デザイナーを使用する

Intune に登録されているデバイスかどうかにかかわらず、アプリには構成デザイナーを使用できます。 デザイナーでは、特定の構成キーと値を構成できます。 各値のデータ型も指定する必要があります。

構成の各キーと値について、以下を設定します。

  - **構成キー**  
     特定の設定構成を一意に識別するキー。
  - **値の型**  
    構成値のデータ型。 整数型、実数型、文字列型、またはブール型があります。
  - **構成値**  
    構成の値。 

## <a name="enter-the-json-editor"></a>JSON エディターの入力

構成デザイナーでは構成できないアプリの構成設定もあります (バンドル タイプの構成設定など)。 このような値には JSON エディターを使用する必要があります。 設定は、アプリのインストール時に自動で行われます。

1. **[構成設定の形式]** で、**[Enter JSON editor]\(JSON エディターを使用する\)** を選択します。
2. エディターでは、構成設定の JSON 値を定義できます。 **[Download JSON template]\(JSON テンプレートをダウンロードする\)** を選択して、構成に使用できるサンプル ファイルをダウンロードできます。
3. **[OK]** を選択してから、**[追加]** を選択します。

ポリシーが作成され、ポリシーの一覧ブレードに表示されます。

割り当てたアプリをデバイスで実行すると、アプリ構成ポリシーで構成した設定を使用して実行されます。

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>アプリのアクセス許可の状態を事前に構成する

Android デバイス機能にアクセスするためのアプリのアクセス許可を事前に構成することもできます。 既定では、場所やデバイス カメラへのアクセスなど、デバイスのアクセス許可を必要とする Android アプリは、アクセス許可の承諾または拒否をユーザーに求めます。 たとえば、アプリでデバイスのマイクが使用される場合、ユーザーは、そのマイクを使用するアクセス許可をアプリに付与するように求められます。

1. Azure ポータルにサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。
3. **[Mobile Apps]** を選択します。 **[管理]** の下で、**[アプリ構成ポリシー]** を選択してから **[追加]** を選択します。
4. 次の詳細を設定します。
    - **名前**。 Azure Portal に表示されるプロファイルの名前。
    - **説明**。 Azure Portal に表示されるプロファイルの説明。
    - **プラットフォーム**。 **[Android]** を選択します。
    - **デバイス登録の種類**。 **[管理対象デバイス]** があらかじめ選択されています。
5. **[関連アプリ]** を選択し、構成ポリシーを定義するアプリを選択します。 承認して Intune に同期した Android for Work アプリの一覧から選択します。
6. **[アクセス許可]** を選択し、**[追加]** を選択します。
7. 使用できるアプリのアクセス許可の一覧から選択し、**[OK]** を選択します。
8. このポリシーに付与するアクセス許可ごとにオプションを選択します。
    - **プロンプト**。 承諾または拒否をユーザーに求める
    - **自動許可**。 ユーザーに通知することなく自動的に承諾します。
    - **自動拒否**。 ユーザーに通知することなく自動的に拒否します。
9. アプリ構成ポリシーを割り当てるには、アプリ構成ポリシーを選択して、**[割り当て]**、**[グループの選択]** の順に選択します。
10. 割り当てるユーザー グループを選び、**[選択]** をクリックします。
11. **[保存]** を選択して、ポリシーを割り当てます。

## <a name="next-steps"></a>次の手順

アプリの[割り当て](apps-deploy.md)と[監視](apps-monitor.md)に進みます。

