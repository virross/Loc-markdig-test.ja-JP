---
title: "IntuneManagementExtension エンティティ | Microsoft Docs"
description: "Intune データ ウェアハウス API にあるエンティティ コレクションの IntuneManagementExtension エンティティ カテゴリのための参照トピック。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3889d9772784322659a73ea2f0996b7b8a699b55
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="reference-for-intune-management-extension"></a>Intune 管理拡張のリファレンス

**IntuneManagementExtension** カテゴリには、次のような情報を追跡するモバイル デバイスのエンティティが含まれています。

  -  IntuneManagementExtension のバージョン
  -  IntuneManagementExtension のインストール状態

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

**IntuneManagementExtensionVersion** エンティティは、IntuneManagementExtension で使用されるすべてのバージョンを一覧表示します。

| プロパティ  | 説明 | 例 |
|---------|------------|--------|
| ExtensionVersionKey |IntuneManagementExtension バージョンの一意識別子。 | 1 |
| ExtensionVersion |4 桁のバージョン番号。 |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

**IntuneManagementExtensionHealthState** は、IntuneManagementExtension の考えられるすべてのヘルス状態を一覧表示します。

| プロパティ  | 説明 | 例 |
|---------|------------|--------|
| ExtensionStateKey |ヘルス状態の一意識別子。 | 2 |
| ExtensionState |IntuneManagementExtension のヘルス状態。 | Healthy |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

**IntuneManagementExtension** は、1 日あたりの各 Windows 10 デバイスでの IntuneManagementExtension ヘルスを一覧表示します。
過去 60 日間のデータが保持されます。 


| プロパティ  | 説明 | 例 |
|---------|------------|--------|
| DateKey |日付の一意識別子。 | 123 |
| TenantKey |テナントの一意識別子。 | 456 |
| DeviceKey |デバイスの一意識別子。 | 789 |
| ExtensionVersionKey |IntuneManagementExtension バージョンの一意識別子。 | 1 |
| ExtensionStateKey|ヘルス状態の一意識別子。 | 2 |
