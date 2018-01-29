---
title: "Android と Android for Work デバイスの Intune 電子メール設定"
titleSuffix: Azure portal
description: "Android デバイスでの電子メール接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c50f1cd58557f877d4eaea0f76ecd0c371b3da1d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="email-profile-settings-for-android--devices-in-microsoft-intune"></a>Microsoft Intune での Android デバイス向けの電子メール プロファイル設定

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune 管理者は、次の Android デバイスに対して電子メール設定の作成と割り当てができます。
- [Android Samsung KNOX Standard](#android-samsung-knox-standard-email-settings)
- [Android for Work](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a>Android Samsung KNOX Standard の電子メール設定
- **[電子メール サーバー]** - Exchange サーバーのホスト名。
- **[アカウント名]** - ユーザーのデバイスに表示される電子メール アカウントの表示名。
- **[AAD からのユーザー名の属性]** - この名前は Active Directory (AD) または Azure AD の属性で、この電子メール プロファイルのユーザー名の生成に使用されます。 **プライマリ SMTP アドレス** (user1@contoso.com など) または**ユーザー プリンシパル名** (user1、user1@contoso.com など) を選択します。
- **[AAD からのメール アドレス属性]** - 各デバイスでユーザーの電子メール アドレスを生成する方法。 Exchange へのログインにプライマリ SMTP アドレスを使用する場合は **[プライマリ SMTP アドレス]** を選択し、完全プリンシパル名を電子メール アドレスとして使用する場合は **[ユーザー プリンシパル名]** を使用します。
- **[認証方法]** - 電子メール プロファイルで使用する認証方法として、**[ユーザー名とパスワード]** または **[証明書]** を選択します。
    - **[証明書]** を選択した場合は、Exchange 接続の認証のために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。

### <a name="security-settings"></a>セキュリティ設定

- **[SSL]** - 電子メールの送受信および Exchange サーバーとの通信に、SSL (Secure Sockets Layer) 通信を使用します。
- **[S/MIME]** - S/MIME 暗号化を使用して電子メールを送信します。
    - **[証明書]** を選択した場合は、Exchange 接続の認証のために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。

### <a name="synchronization-settings"></a>同期設定

- **[同期するメールの量]** - 同期する電子メールの日数を選択するか、利用可能なすべての電子メールを同期する場合は **[無制限]** を選択します。
- **[同期スケジュール]** - デバイスが Exchange サーバーからデータを同期するスケジュールを選択します。 **[メッセージの着信時]** を選択すると、電子メールの着信時にデータが同期されます。**[手動]** を選択した場合は、デバイスのユーザーが同期を開始する必要があります。

### <a name="content-sync-settings"></a>コンテンツ同期設定

- **[同期するコンテンツの種類]** - デバイスに同期するコンテンツの種類を選択します。
    - **連絡先**
    - **カレンダー**
    - **タスク**

## <a name="android-for-work-email-settings"></a>Android for Work の電子メール設定

- **[メール アプリ]** - **[Gmail]** または **[Nine Work]** を選択します。
- **[電子メール サーバー]** - Exchange サーバーのホスト名。
- **[AAD からのユーザー名の属性]** - この名前は Active Directory (AD) または Azure AD の属性で、この電子メール プロファイルのユーザー名の生成に使用されます。 **プライマリ SMTP アドレス** (user1@contoso.com など) または**ユーザー プリンシパル名** (user1、user1@contoso.com など) を選択します。
- **[AAD からのメール アドレス属性]** - 各デバイスでユーザーの電子メール アドレスを生成する方法。 **[ユーザー プリンシパル名]**  を選択して電子メール アドレスとして完全プリンシパル名を使用するか、**[ユーザー名]** を選択します。
- **[認証方法]** - 電子メール プロファイルで使用する認証方法として、**[ユーザー名とパスワード]** または **[証明書]** を選択します。
    - **[証明書]** を選択した場合は、Exchange 接続の認証のために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。
- **[SSL]** - 電子メールの送受信および Exchange サーバーとの通信に、SSL (Secure Sockets Layer) 通信を使用します。
- **[同期するメールの量]** - 同期する電子メールの日数を選択するか、利用可能なすべての電子メールを同期する場合は **[無制限]** を選択します。
- **[同期するコンテンツの種類]** (Nine Work のみ) - デバイスに同期するコンテンツの種類を選択します。
    - **連絡先**
    - **カレンダー**
    - **タスク**
