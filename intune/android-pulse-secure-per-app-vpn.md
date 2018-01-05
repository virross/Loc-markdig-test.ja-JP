---
title: "Android - Pulse Secure 用のアプリ別の VPN プロファイル"
titlesuffix: Azure portal
description: "Intune で管理する Android デバイス用にアプリごとの VPN プロファイルを作成する方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5319913c16710d9a2076e629d8ff57894f95f139
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Microsoft Intune のカスタム プロファイルを使って、Android デバイス用にアプリごとの VPN プロファイルを作成する

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune で管理する、アプリごとの VPN プロファイルを Android 5.0 以降のデバイスに作成できます。 最初に、Pulse Secure 接続の種類を使用する VPN プロファイルを作成します。 次に、特定のアプリと VPN プロファイルを関連付けるカスタム構成ポリシーを作成します。

Android デバイスまたはユーザー グループにポリシーを割り当てた後、ユーザーは PulseSecure VPN を開始します。 その後 PulseSecure は、指定されたアプリからのトラフィックのみに OpenVPN 接続の使用を許可します。

> [!NOTE]
>
> このプロファイルに対しては Pulse Secure 接続タイプのみがサポートされます。


## <a name="step-1-create-a-vpn-profile"></a>手順 1: VPN プロファイルを作成する


1. Azure Portal にサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[デバイス構成]** を選択します。
2. **[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。
2. プロファイルの一覧ブレードで、**[プロファイルを作成します]** を選択します。
3. **[プロファイルを作成します]** ブレードで、VPN プロファイルの**名前**と省略可能な**説明**を入力します。
4. **[プラットフォーム]** ドロップダウン リストで、**[Android]** を選択します。
5. **[プロファイルの種類]** ドロップダウン リストで、**[VPN]** を選択します。
3. **[設定]** > **[構成]** の順に選択し、[VPN 設定を構成する方法](vpn-settings-configure.md)に関する記事および [Android デバイス用の Intune VPN 設定](vpn-settings-android.md)に関する記事の設定に従って VPN プロファイルを構成します。

VPN プロファイルの作成時に指定した**接続名**の値を書き留めてください。 この名前は次の手順で必要になります。 たとえば、**MyAppVpnProfile** です。

## <a name="step-2-create-a-custom-configuration-policy"></a>手順 2: カスタム構成ポリシーを作成する

1. Azure Portal にサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[デバイス構成]** を選択します。
2. **[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。
3. [プロファイル] ブレードで、**[プロファイルを作成します]** をクリックします。
4. **[プロファイルを作成します]** ブレードで、カスタム プロファイルの**名前**と**説明**を入力します。
5. **[プラットフォーム]** ドロップダウン リストで、**[Android]** を選択します。
6. **[プロファイルの種類]** ドロップダウン リストで、**[カスタム]** を選択します。
7. **[設定]** > **[構成]** の順に選択します。
3. **[OMA-URI のカスタム設定]** ブレードで、**[追加]** を選択します。
    - 設定の名前を入力します。
    - **[データ型]** に **[文字列]** を指定します。
    - **[OMA-URI]** には、**./Vendor/MSFT/VPN/Profile/*Name*/PackageList** の文字列を指定します。ここの *Name* は手順 1 でメモした VPN プロファイル名です。 この例では、文字列は **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList** になります。
    - **[値]** には、プロファイルと関連付けるセミコロンで区切られたパッケージの一覧を入力します。 たとえば、Excel と Google Chrome ブラウザーで VPN 接続を使用するには、「**com.microsoft.office.excel;com.android.chrome**」と入力します。

![Android のアプリごとの VPN カスタム ポリシーの例](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>アプリの一覧をブラックリストまたはホワイトリストとして設定する (省略可能)
  **BLACKLIST** 値を使用すると、VPN 接続を使用*できない*アプリの一覧を指定できます。 その他のすべてのアプリは、VPN 経由で接続します。
または、**WHITELIST** 値を使用して、VPN 接続を使用*できる*アプリの一覧を指定することもできます。 一覧に含まれないアプリは、VPN 経由で接続しません。
  1.    **[OMA-URI のカスタム設定]** ブレードで、**[追加]** を選択します。
  2.    設定の名前を入力します。
  3.    **[データ型]** に **[文字列]** を指定します。
  4.    **[OMA-URI]** には、**./Vendor/MSFT/VPN/Profile/*Name*/Mode** の文字列を使用します。ここの *Name* は手順 1 でメモした VPN プロファイル名です。 この例では、文字列は **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode** になります。
  5.    **[値]** には、「**BLACKLIST**」または「**WHITELIST**」と入力します。



## <a name="step-3-assign-both-policies"></a>手順 3: 両方のポリシーを割り当てる

[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事の指示に従って、必要なユーザーまたはデバイスに両方のプロファイルを割り当てます。
