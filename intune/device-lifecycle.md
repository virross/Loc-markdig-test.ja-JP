---
title: "MDM ライフサイクルの概要"
description: "登録、構成から始まり最終的に使用中止となるデバイスのライフサイクル管理において Intune がどのように役立つか紹介します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6051fa7-133f-4712-86a5-e5f5bc5ab3c7
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b91b8bf7508b7589f5ba5922cec8df576445cf27
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="overview-of-the-mobile-device-management-mdm-lifecycle"></a>モバイル デバイス管理 (MDM) ライフサイクルの概要

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

管理するすべてのデバイスには、*ライフサイクル*と呼ばれるものがあります。 Intune は、登録から始まり、構成と保護を経て、不要になったデバイスの使用中止まで、ライフサイクルの管理に役立ちます。

![デバイスのライフサイクル](./media/device-lifecycle.png "Intune デバイスのライフサイクル")

## <a name="enroll"></a>登録
今日のモバイル デバイス管理 (MDM) 戦略では、さまざまな携帯電話、タブレット、PC (iOS、Android、Windows、Mac OS X) を扱っています。 デバイスを管理できる必要がある場合 (一般には企業所有デバイス)、最初の手順として、[デバイスの登録をセットアップ](device-enrollment.md) ([クラシック ポータル](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)) します。 Windows PC については、Intune (MDM) を使用して登録するか、または [Intune クライアント ソフトウェアをインストールする](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune)ことで、管理することもできます。

## <a name="configure"></a>構成
デバイスを登録することは、最初の手順にすぎません。 Intune で用意されているあらゆるサービスを利用し、デバイスがセキュリティで保護され企業の標準に準拠するように保証するには、さまざまなポリシーから選択することができます。 これにより、管理対象のデバイスの動作のほぼすべての側面を構成できます。 たとえば、会社のデータが格納されているデバイスに対してユーザーはパスワードを使用する必要がありますか? パスワードを設定できます。 企業 Wi-Fi を備えていますか? 自動的に構成することができます。 使用できる構成オプションの種類を次に示します。

- [**デバイス構成**](device-profiles.md) ([クラシック ポータル](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies))。 このポリシーでは、管理するデバイスの機能を構成できます。 たとえば、Windows Phone でパスワードの使用を求めたり、iPhone でカメラの使用を無効にしたりすることが可能です。
- [**会社のリソースへのアクセス**](device-profiles.md) ([クラシック ポータル](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune))。 ユーザーが自分の個人用デバイスから自分の作業にアクセスできるようにする場合、これには課題が伴う場合があります。 たとえば、会社の電子メールへのアクセスを必要とするすべてのデバイスが正しく構成されていることを確認するにはどうしますか。 ユーザーが複雑な設定を知らなくても VPN 接続を使用して社内ネットワークにアクセスできるかどうかはどのように確認できますか? Intune では、共通の企業リソースにアクセスするように管理対象デバイスを自動的に構成することにより、この作業負荷を軽減することができます。
- [**Windows PC の管理ポリシー (Intune クライアント ソフトウェアを使用)**](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client)。 Windows PC を Intune に登録するとほとんどのデバイス管理機能を利用できますが、Intune では引き続き Intune クライアント ソフトウェアによる Windows PC の管理をサポートします。 PC で実行できるタスクの一部について情報が必要な場合は、ここから始めてください。

## <a name="protect"></a>保護
最新の IT 世界で、不正アクセスからデバイスを保護することは、実施しなければならない最も重要なタスクの 1 つです。 デバイス ライフサイクルの**構成**ステップの項目に加えて、Intune では管理対象のデバイスを不正なアクセスまたは悪意のある攻撃から保護するのに役立つ次の機能も提供されます。
- [**多要素認証**](/intune-classic/deploy-use/protect-your-devices-with-microsoft-intune)。 追加の認証層をユーザー サインインに追加すると、デバイスの安全性をさらに強化するのに役立ちます。 多くのデバイスで、ユーザーがアクセスできるようになるまでに電話またはテキスト メッセージなどの第 2 レベルの認証が必要となる多要素認証がサポートされています。
- [**Windows Hello for Business の設定**](windows-hello.md) ([クラシック ポータル](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune))。 Windows Hello for Business は、ユーザーが*ジェスチャ* (フィンガープリントや Windows Hello など) を使用して、パスワードなしでサインインできるようにするサインインの代替方法です。
- [**Windows PC を保護するためのポリシー (Intune クライアント ソフトウェアを使用)**](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)。 Intune クライアント ソフトウェアを使用して Windows PC を管理する場合は、更新する PC に対する Endpoint Protection、ソフトウェア更新プログラム、および Windows ファイアウォールの設定を制御するためのポリシーを利用できます。

## <a name="retire"></a>インベントリから削除
デバイスを紛失したり盗まれたりしたとき、デバイスの交換が必要なとき、またはユーザーが別の職場に移動になったときには、通常デバイスを[削除またはワイプ](device-management.md) ([クラシック ポータル](/intune-classic/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune)) します。 それを行うには、デバイスをリセットする、デバイスを管理から削除する、またはデバイス上の企業データをワイプするなど、さまざまな方法があります。
