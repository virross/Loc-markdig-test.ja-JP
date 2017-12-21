---
title: "Intune での条件付きアクセス"
titlesuffix: Azure portal
description: "会社のリソースにアクセスするためにユーザーとデバイスが満たす必要のある条件を Microsoft Intune で定義する方法について説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6e2deb008b63fd9e9e9f37674c81745a0c8ccb04
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="whats-conditional-access"></a>条件付きアクセスとは

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

このトピックでは、Enterprise Mobility + Security (EMS) に適用される条件付きアクセスについて説明し、さらに Intune での条件付きアクセスの一般的なシナリオについても取り上げます。

Enterprise Mobility + Security (EMS) 条件付きアクセスはスタンドアロン製品ではありませんが、EMS の一部であるすべてのサービスと製品にかかわるソリューションです。 細かいアクセス制御を提供することで会社のデータをセキュリティで保護し、任意の場所と任意のデバイスで最適な仕事ができるエクスペリエンスをユーザーに提供します。

場所、デバイス、ユーザーの状態、アプリケーションの機密度に基づいて、会社のデータへのアクセスを制限する条件を定義できます。

> [!NOTE] 
> 条件付きアクセスは、その機能を[Office 365 サービス](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/)にも拡張しています。

![条件付きアクセスのアーキテクチャ ダイアグラム](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Intune での条件付きアクセス

Intune では、モバイル デバイスのコンプライアンスとアプリ管理ポリシーを追加し、EMS 条件付きアクセスのソリューションをサポートします。

![EMS 使用時の Intune と条件付きアクセス](./media/intune-with-ca-1.png)

Intune での条件付きアクセスの使用方法

-   **デバイスに基づく条件付きアクセス**

    -   Exchange On-Premises の条件付きアクセス

    -   ネットワーク アクセス制御に基づいた条件付きアクセス

    -   デバイスのリスクに基づいた条件付きアクセス

    -   Windows PC の条件付きアクセス

        -   企業所有

        -   Bring Your Own Device (BYOD)

-   **アプリベースの条件付きアクセス**

## <a name="next-steps"></a>次のステップ

[Intune での条件付きアクセスの一般的な使用方法](conditional-access-intune-common-ways-use.md)
