---
title: "Windows 10 用の Intune Endpoint Protection 設定"
titlesuffix: Azure portal
description: "Windows 10 デバイスで Endpoint Protection 設定 ( BitLocker など) を制御するのに使用できる Intune 設定について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bebfe6ea4248d8ac9b5dc86dc52acb6ef5404b1c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Microsoft Intune での Windows 10 以降用の Endpoint Protection 設定

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Endpoint Protection プロファイルを使用すると、Windows 10 デバイス上で BitLocker や Windows Defender のようなセキュリティ機能を制御することができます。

このトピックでは、Endpoint Protection プロファイルを作成する方法について説明します。

> [!Note]
> これらの設定は、Windows 10 の Home および Professional Edition ではサポートされていません。

## <a name="create-an-endpoint-protection-profile"></a>Endpoint Protection プロファイルを作成する

1. Azure Portal にサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[デバイス構成]** を選択します。
2. **[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。
3. [プロファイル] ブレードで、**[プロファイルを作成します]** を選択します。
4. **[プロファイルを作成します]** ブレードで、デバイスの機能プロファイルの**名前**と**説明**を入力します。
5. **[プラットフォーム]** ドロップダウン リストで、**[Windows 10 以降]** を選択します。
6. **[プロファイルの種類]** ドロップダウン リストで、**[Endpoint Protection]** を選択します。
7. **[Windows 暗号化]** ブレードで、目的の設定を構成します。 各設定の機能については、このトピックで詳細を説明します。 終了したら **[OK]** を選択します。
8. **[プロファイルの作成]** ブレードに進み、**[作成]** を選択します。

プロファイルが作成され、プロファイルの一覧ブレードに表示されます。

## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen 設定

- **アプリとファイルの SmartScreen** - ファイルやアプリの実行のために Windows SmartScreen を有効にします。
- **未確認ファイルの実行** - Windows SmartScreen で検証されていないファイルをエンド ユーザーが実行する行為を禁止します。

## <a name="windows-encryption-settings"></a>Windows 暗号化設定

### <a name="windows-settings"></a>Windows の設定

- **デバイスの暗号化が必須 (デスクトップのみ)** - 有効にすると、デバイスの暗号化を有効にするように求められます。 さらに、別のプロバイダーによる暗号化が有効になっていないことを確認するように求められます。 別の暗号化方式がアクティブになっている場合に Windows の暗号化を有効にすると、デバイスが不安定になる可能性があります。
- **メモリ カードの暗号化が必須 (モバイルのみ)** - デバイスで使用するリムーバブル メモリ カードを暗号化するには、この設定を有効にします。


### <a name="bitlocker-base-settings"></a>BitLocker の基本設定

- **暗号化方法の構成** - オペレーティング システム、データ、およびリムーバブル ドライブ用の暗号化アルゴリズムを構成するには、この設定を有効にします。
    - **オペレーティング システム ドライブの暗号化** - オペレーティング システム ドライブ用の暗号化の方法を選択します。 XTS-AES アルゴリズムの使用をお勧めします。
    - **固定データ ドライブの暗号化** - 固定 (組み込み) のデータ ドライブ用の暗号化の方法を選択します。 XTS-AES アルゴリズムの使用をお勧めします。
    - **リムーバブル データドライブの暗号化** - リムーバブル データ ドライブ用の暗号化の方法を選択します。 Windows 10 を実行していないデバイスでリムーバブル ドライブを使用する場合は、AES-CBC アルゴリズムの使用をお勧めします。


### <a name="bitlocker-os-drive-settings"></a>BitLocker OS ドライブ設定

- **スタートアップ時に追加の認証を要求する** -
    - **互換性のない TPM チップでの BitLocker** -
    - **TPM スタートアップ** - TPM チップを許可するか、許可しないか、または必須とするかを構成します。
    - **TPM スタートアップ PIN** - TPM チップ搭載のスタートアップ PIN の使用を許可するか、許可しないか、または必須とするかを構成します。
    - **TPM スタートアップ キー** - TPM チップ搭載のスタートアップ キーの使用を許可するか、許可しないか、または必須とするかを構成します。
    - **TPM スタートアップ キーと PIN** - TPM チップ搭載のスタートアップ キーおよび PIN の使用を許可するか、許可しないか、または必須とするかを構成します。
- **最小 PIN サイズ** - TPM スタートアップ PIN の最小長を構成するには、この設定を有効にします。
    - **最小文字数** - スタートアップ PIN に必要な文字数を入力します。有効な値は **4**-**20** の範囲となります。
- **OS ドライブの回復を有効にする** - 必要なスタートアップ情報が利用できない場合に BitLocker で保護されたオペレーティング システム ドライブを回復する方法を制御するには、この設定を有効にします。
    - **証明書ベースのデータ回復エージェント** - BitLocker で保護されているオペレーティング システム ドライブでデータ回復エージェントを使用できるようにする場合は、この設定を有効にします。
    - **ユーザーによる回復パスワードの作成** - 48 桁の回復パスワードの生成をユーザーに許可するか、必須にするか、あるいは許可しないかを構成します。
    - **ユーザーによる回復キーの作成** - 256 ビットの回復キーの生成をユーザーに許可するか、必須にするか、あるいは許可しないかを構成します。
    - **BitLocker セットアップ ウィザードで回復オプションを非表示にする** - ユーザーが BitLocker を有効にした場合に、回復オプションをユーザーに表示しない、または回復オプションの変更をユーザーに許可しないためには、この設定を有効にします。
    - **BitLocker 回復情報を AD DS に保存する** - Active Directory の BitLocker 回復情報の保存を有効にします。
    - **AD DS への BitLocker 回復情報の保存を構成する** - BitLocker 回復情報のどの部分を Active Directory に格納するかを構成します。 次の中から選択します。
        - **回復パスワードとキー パッケージをバックアップする**
        - **回復パスワードのみバックアップする**
    - **BitLocker を有効にする前に回復情報が AD DS に保存される必要がある** - デバイスがドメインに不参加であり、かつ BitLocker 回復情報が Active Directory に正常に保存されていない場合、ユーザーが BitLocker を有効にするのを阻止するには、この設定を有効にします。
- **プリブート回復メッセージと URL を有効にする** - ブート前のキー回復画面に表示されるメッセージと URL を構成するには、この設定を有効にします。
    - **プリブート回復メッセージ** - プリブート回復メッセージをユーザーに表示する方法を構成します。 次の中から選択します。
        - **既定の回復メッセージと URL を使用する**
        - **空の回復メッセージと URL を使用する**
        - **カスタム回復メッセージを使用する**
        - **カスタム回復 URL を使用する**


### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker 固定データ ドライブの設定

- **BitLocker によって保護されていない固定データ ドライブへの書き込みアクセスを拒否する** - 有効にした場合、固定データ ドライブまたは組み込みデータ ドライブへの書き込みを可能にするには、該当するすべてのドライブで BitLocker 保護を有効にする必要があります。
- **固定ドライブの回復を有効にする** - 必要なスタートアップ情報が利用できない場合に BitLocker で保護された固定ドライブを回復する方法を制御するには、この設定を有効にします。
    - **データ回復エージェント** - BitLocker で保護されている固定ドライブでデータ回復エージェントを使用する場合は、この設定を有効にします。
    - **ユーザーによる回復パスワードの作成** - 48 桁の回復パスワードの生成をユーザーに許可するか、必須にするか、あるいは許可しないかを構成します。  
    - **ユーザーによる回復キーの作成** - 256 ビットの回復キーの生成をユーザーに許可するか、必須にするか、あるいは許可しないかを構成します。
    - **BitLocker セットアップ ウィザードで回復オプションを非表示にする** - ユーザーが BitLocker を有効にした場合に、回復オプションをユーザーに表示しない、または回復オプションの変更をユーザーに許可しないためには、この設定を有効にします。
    - **BitLocker 回復情報を AD DS に保存する** - Active Directory の BitLocker 回復情報の保存を有効にします。
    - **AD DS への BitLocker 回復情報の保存を構成する** - BitLocker 回復情報のどの部分を Active Directory に格納するかを構成します。 次の中から選択します。
        - **回復パスワードとキー パッケージをバックアップする**
        - **回復パスワードのみバックアップする**
    - **BitLocker を有効にする前に回復情報が AD DS に保存される必要がある** - デバイスがドメインに不参加であり、かつ BitLocker 回復情報が Active Directory に正常に保存されていない場合、ユーザーが BitLocker を有効にするのを阻止するには、この設定を有効にします。


### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker リムーバブル データ ドライブの設定

- **BitLocker によって保護されていないリムーバブル データ ドライブへの書き込みアクセスを拒否する** - BitLocker 暗号化がリムーバブル ストレージ ドライブに必要かどうかを指定します。
    - **別の組織で構成されたデバイスへの書き込みアクセスをブロックする** - 別の組織に属しているリムーバブル データ ドライブへの書き込みを可能にするかどうかを指定します。



## <a name="next-steps"></a>次の手順

このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。
