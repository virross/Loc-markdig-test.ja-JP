---
title: "Windows 10 用のアプリ保護ポリシーを構成する準備をする"
description: "Azure AD でモバイル アプリケーション管理 (MAM) プロバイダーをセットアップします"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c94fe06c186dd33f7497236fc70a2a41f4141d87
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Windows 10 用のアプリ保護ポリシーを構成する準備をする

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Windows 10 のアプリ保護ポリシーを作成する前に、Azure AD でモバイル アプリケーション管理 (MAM) プロバイダーを設定することにより、Windows 10 用に MAM を有効にする必要があります。 この構成を行うことで、Intune で新しい Windows 情報保護 (WIP) ポリシーを作成するときに、登録状態を定義することができます。

> [!NOTE]
> 登録状態には、MAM またはモバイル デバイス管理 (MDM) のいずれかを指定できます。

## <a name="to-configure-the-mam-provider"></a>MAM プロバイダーを構成するには

1.  [Azure Portal](https://portal.azure.com/) に移動し、Intune 資格情報でサインインします。

2.  左側のメニューで、**[Azure Active Directory]** を選択します。

    ![MAM プロバイダーの構成](../media/AppManagement/mam-provider-sc-1.png)

3.  **[Azure AD]** ブレードが開くので、**[モビリティ (MDM および MAM)]** を選択し、**[Microsoft Intune]** をクリックします。

    ![モビリティ MDM および MAM](../media/AppManagement/mam-provider-sc-2.png)

4.  構成ブレードが開くので、**[既定の MAM URL を復元する]** を最初に選んでから、以下を構成します。

    a.  [MAM ユーザー スコープ]: MAM を使って、Windows 10 デバイスを使う特定のユーザー グループまたはすべてのユーザーの企業データを保護できます。

    b.  [MAM 使用条件 URL]: MAM サービスの使用条件エンドポイントの URL です。 これは、MAM サービスの使用条件をエンドユーザーに表示するために使います。

    c.  [MAM 探索 URL]: アプリ保護ポリシーを適用する必要があるときにデバイスが探索する URL です。

    d.  [MAM 準拠 URL]:

5.  これらの設定を構成した後、**[保存]** を選びます。

## <a name="next-steps"></a>次のステップ

[WIP アプリ保護ポリシーを作成する](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)
