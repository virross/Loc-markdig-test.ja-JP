---
title: "Intune デバイス構成プロファイルを作成する"
titlesuffix: Azure portal
description: "Intune デバイス構成プロファイルを作成する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 309678406dd9f887c0f9ca0ab79c4580421024d1
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Microsoft Intune でデバイス構成プロファイルを作成する方法

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

1. Azure Portal にサインインします。
2. **[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。
3. **[Intune]** ブレードで、**[デバイスの構成]** を選択します。
4. **[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。
5. プロファイルの一覧が表示されているブレードで、**[プロファイルを作成します]** を選択します。
6. **[プロファイルの作成]** ブレードで、次の項目を指定します。
   - **[名前]** - 新しいプロファイルのわかりやすい名前を入力します。
   - **[説明]** - プロファイルの説明を入力します (省略可能)。
   - **[プラットフォーム]** - 作成するプロファイルのプラットフォームの種類を選択します。
   - **[プロファイルの種類]** - 作成するプロファイルの種類を選択します。 選択可能な種類の一覧は、選択したプラットフォームによって異なります。
   - **[設定]** - プロファイルの種類ごとの設定に関する情報については、次のトピックを参照してください。
       -  [デバイス機能設定](device-features-configure.md)
       -  [デバイスの制限設定](device-restrictions-configure.md)
       -  [電子メールの設定](email-settings-configure.md)
       -  [VPN 設定](vpn-settings-configure.md)
       -  [Wi-Fi 設定](wi-fi-settings-configure.md)
       -  [Windows 10 エディションのアップグレード設定](edition-upgrade-configure-windows-10.md)
       -  [証明書の設定](certificates-configure.md)
       -  [Windows 情報保護の設定](windows-information-protection-configure.md)
       -  [教育設定](education-settings-configure.md)
       -  [カスタム設定](custom-settings-configure.md)

     ![デバイス プロファイルの作成](./media/create-device-profile.png)
7. 設定の構成が完了したら、**[プロファイルを作成します]** ブレードで、**[作成]** を選択します。

プロファイルが作成され、プロファイルの一覧ブレードに表示されます。
このプロファイルをグループに割り当てる場合は、[デバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。


### <a name="next-steps"></a>次の手順
デバイス プロファイルを割り当てる方法については、[Microsoft Intune でデバイス プロファイルを割り当てる方法](device-profile-assign.md)に関する記事を参照してください。
