---
title: "アプリを展開する方法"
description: "このトピックの情報を使用して、Microsoft Intune でアプリを展開できます。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d147a53f283470feda83a66d3668aacc566cb81
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="deploy-apps-in-microsoft-intune"></a>Deploy apps in Microsoft Intune (Microsoft Intune でアプリを展開する)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

このトピックの情報を使用して、Microsoft Intune でアプリを展開できます。


## <a name="deploy-an-app"></a>アプリを展開する
この手順では、選択したデバイスまたはユーザーのグループにアプリを展開します。

### <a name="to-deploy-an-app"></a>アプリを展開するには

1. [Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[アプリ]** &gt; **[アプリ]** の順にクリックし、管理するアプリの一覧を表示します。

2.  展開するアプリを選択し、**[展開の管理]** をクリックします。

3.  *[&lt;アプリ名&gt;]* ダイアログ ボックスで、**[グループの選択]** ページで、アプリを展開するユーザー グループまたはデバイス グループを選択します。

4.  **[展開アクション]** ページで、次を構成します。

    - **承認** - 展開の詳細を選択します。
        - **[必須]** (インストール必須)
        - **[使用可能]** (必要に応じて、ユーザーは会社のポータルからインストールします)
        - **[該当なし]** (アプリは会社のポータルにはインストールされていないか、表示されません)
        - **[アンインストール]** (アプリは対象となるデバイスからアンインストールされます)
    - **期限** - 必要なインストールに対し、アプリをいつ展開するかを選択します。 定義済みの値から選択するか、**[カスタム]** を選択し、独自の期限を構成できます。

5. 展開するアプリがモバイル アプリケーション管理ポリシーで構成できる場合、**[モバイル アプリの管理]** ページが表示されます。 このページで、このアプリに関連付けるモバイル アプリケーションの管理ポリシーを選択します。

    [モバイル アプリケーション管理ポリシーに対応する Microsoft アプリを確認してください。](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)

6. 展開するアプリに Intune VPN プロファイルとの互換性がある場合、**[VPN プロファイル]** ページが表示されます。 このページで、展開した VPN プロファイルに iOS アプリを関連付けることができます。 アプリを起動すると、VPN 接続が自動的に開きます。 VPN プロファイルを使用できるようにするには、**アプリごとの VPN** プロファイル設定を有効にする必要があります。
 プロファイルをアプリと関連付ける方法に関する情報など、VPN プロファイルを構成する方法については、「[Microsoft Intune での VPN 接続](vpn-connections-in-microsoft-intune.md)」をご覧ください。

<!---
>[!TIP]
>If an end user previously installed an iOS app and you now deploy it with a deployment action of **Available**, Intune will automatically begin to manage that app with no further action required by you, or the end-user.
--->

## <a name="example"></a>例

この例では、アプリを **[使用可能]** として iOS デバイスに展開します。
ユーザーのデバイスでポータル サイトにアプリが表示され、そこからアプリをインストールできます。

たとえば、このスクリーンショットでは、**[外部リンク]** インストール タイプとカスタム アイコンを使用して Bing for iOS アプリを展開しています。 **[このアプリをポータル サイトでおすすめアプリとして強調表示する]** オプションが選択されています。  
![iOS の使用可能アプリ](./media/available-install-on-iOS.png)

アプリを **[必須]** として iOS デバイスに展開した場合は、アプリがインストール可能になったことを知らせる通知がユーザーに届きます。 たとえば、このスクリーンショットでは、種類が **[アプリ ストアの管理されている iOS アプリ]** のインストールで Work Folders for iOS アプリが展開されました。  
![iOS の必須アプリ](./media/iOS-Required-install.PNG)

## <a name="next-steps"></a>次のステップ

アプリケーションを展開した後、その進行状況を監視できます。 詳細については、「[Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md)」 (Microsoft Intune でアプリを監視する) を参照してください。
