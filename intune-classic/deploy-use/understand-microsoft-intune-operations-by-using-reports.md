---
title: "レポートを使用して運用状況を把握する"
description: "組織内のソフトウェア、ハードウェア、およびソフトウェア ライセンスに関するレポートを作成して管理します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 04/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pbala
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 295b442606aa8639176f45850d798a2136802ec6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="understand-microsoft-intune-operations-by-using-reports"></a>Understand Microsoft Intune operations by using reports

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

このトピックの情報を使用して、組織内のソフトウェア、ハードウェア、およびソフトウェア ライセンスに関する情報が記載された Microsoft Intune レポートを作成および管理することができます。

## <a name="using-reports"></a>レポートの使用
Intune レポートには、組織内のソフトウェア、ハードウェア、およびソフトウェア ライセンスに関する情報が表示されます。 レポートは、現在必要なものを確認し、今後の支出を見積もるのに便利です。 **[レポート]** ワークスペースには、レポートの作成と管理を行うツールが用意されています。 

## <a name="report-types"></a>レポートの種類

|レポートの種類|説明|
|---------------|---------------|
|**更新レポート**|組織内のコンピューターでソフトウェアの更新が成功したことを表示します。 また、失敗した更新や保留となった更新、または必要な更新も表示します。 ソフトウェア更新プログラムの詳細については、「[Microsoft Intune でソフトウェア更新プログラムを使用して Windows PC を最新の状態に保つ](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)」を参照してください。|
|**検出されたソフトウェアのレポート**|組織内のコンピューターにインストールされているソフトウェアを表示します。 ソフトウェアのバージョンが含まれます。 ソフトウェア発行者とソフトウェア カテゴリに基づいて、表示される情報をフィルターできます。 一覧の項目に付いている矢印を選択すると、一覧が展開して、更新プログラムの詳細 (更新プログラムがインストールされているコンピューターなど) が表示されます。<br /><br />Intune でコンピューターを削除した場合や、グループ メンバーシップを変更した場合は、検出されたソフトウェアのレポートにその変更が反映されるのに数分かかることがあります。 最も正確なソフトウェア インベントリ データが得られるように、コンピューターをインベントリから削除するかグループ メンバーシップを変更した後、数分待ってからこれらのコンピューターを含む検出されたソフトウェア レポートを実行してください。|
|**コンピューター インベントリ レポート**|組織内で管理されているコンピューターに関する情報が表示されます。 このレポートは、ハードウェアの購入計画をたてるときや、組織のユーザーが必要としているハードウェアを確認するときに使用します。 管理されたコンピューターの使用の詳細については、「[Microsoft Intune を使用して Windows PC を管理する](manage-windows-pcs-with-microsoft-intune.md)」を参照してください。|
|**モバイル デバイスのインベントリ レポート**|組織内のモバイル デバイスに関する情報が表示されます。 グループ、デバイスが脱獄またはルート化されているかどうか、オペレーティング システムに基づいて、表示される情報をフィルターできます。|
|**ライセンスの購入レポート**|選択したライセンス グループにあるすべてのライセンス済みソフトウェアのタイトルが、そのライセンス契約に基づいて表示されます。 ソフトウェアのライセンス情報が 24 時間以上更新されていない場合は、ライセンス レポートを生成するときに更新されます。 ライセンス レポートには、使用中のソフトウェア タイトルの数が正確に表示されているわけではありません。また、ライセンス レポートが契約の条項に準拠している証拠になることもありません。 レポートは、組織でライセンスに関する決定を下すときの参考情報を得る手段です。 Microsoft ボリューム ライセンスの対象になり得る製品が、Intune によって検出されない可能性もあります。 次のフィルターを使用できます。<br /><br />**すべての契約**: Intune で管理されているすべてのライセンス済み製品が表示されます。<br /><br />**ボリューム ライセンス契約**: ボリューム ライセンス サービス センター (VLSC) 対象のソフトウェア製品だけが表示されます。<br /><br />**その他のソフトウェア ライセンス契約**: VLSC 以外で管理されているソフトウェア製品が表示されます。|
|**ライセンスのインストール レポート**|VLSC に従って、組織内のコンピューターにインストールされているソフトウェアと現在のライセンス契約の範囲を比較します。 次のフィルターがあります。<br /><br />**すべての契約**: Intune で管理されているすべてのライセンス済み製品が表示されます。<br /><br />**ボリューム ライセンス契約**: VLSC 対象のソフトウェア製品だけが表示されます。<br /><br />**その他のソフトウェア ライセンス契約**: VLSC 以外で管理されているソフトウェア製品が表示されます。|
|**使用条件のレポート**|デプロイした使用条件にユーザーが同意しているかどうかと、同意したバージョンが表示されます。 デプロイした使用条件に同意したユーザーを最大 10 名まで表示できます。また、デプロイした特定の使用条件の同意状況を表示することもできます。|
|**非準拠アプリのレポート**|準拠アプリおよび非準拠アプリ一覧のアプリをインストールしたユーザーに関する情報が表示されます。 このレポートを使用して、会社のアプリ ポリシーに準拠していないユーザーとデバイスを見つけることができます。|
|**証明書の準拠レポート**|SCEP または PKCS #12 (.PFX) を介してユーザーとデバイスに発行された証明書が表示されます。 このレポートを使用して、発行済み、期限切れ、および失効済みの証明書を見つけることができます。|
|**デバイス履歴のレポート**|インベントリからの削除、ワイプ、および削除操作の履歴ログを表示します。 このレポートを使用して過去にデバイス上で操作を開始したユーザーを確認します。|
|**正常性構成レポート**|モバイル デバイスの正常性を表示します。|
|**Mac OS X ハードウェア レポート**|選んだグループに登録されているすべての Mac OS X デバイスのハードウェアの詳細を表示します。 これらのデバイスから収集されたハードウェア インベントリについては、「[Microsoft Intune でインベントリを使用してデバイスを把握する](understand-your-devices-with-inventory-in-microsoft-intune.md)」を参照してください。|
|**Mac OS X ソフトウェア レポート**|選んだグループ内のすべての Mac OS X デバイスにインストールされているソフトウェアを表示します。 このレポートには、バンドル ID としてのソフトウェアの名前、短縮版の名前 (またはフレンドリ名)、バージョン、およびソフトウェアがインストールされたデバイスの数が一覧表示されます。|
|**Windows 情報保護レポート**|管理しているデバイスでの Windows 情報保護 (WIP) の操作に関する情報が表示されます。|
|**正常性構成レポート**|管理しているデバイスについて Windows 正常性構成証明サービスによって報告された情報が表示されます。|

## <a name="to-create-a-report"></a>レポートを作成するには

1.  Intune 管理コンソールで、**[レポート]** を選択します。 次に、前の表に記載されている通り、生成するレポートの種類を選択します。

2.  **[新しいレポートの作成]** ページで、既定値をそのまま使用するか、カスタマイズして、レポートで返される結果をフィルター処理します。 たとえば、Microsoft が発行したソフトウェアだけを検出されたソフトウェアのレポートに表示するように選択できます。

3.  **[レポートの表示]** を選択して、新しいウィンドウでレポートを開きます。

表示されている任意の列でレポートを並べ替えるには、列見出しを選択します。 また、一部のレポートでは、一覧の項目を展開して詳細情報を表示することができます。

## <a name="more-report-actions"></a>その他のレポート操作
レポートでは、次の操作もサポートされています。

|操作|詳細情報|
|----------|--------------------|
|**印刷**|開いているレポートの印刷アイコンを選択し、指示に従います。|
|**エクスポート**|開いているレポートのエクスポート アイコンを選択し、指示に従います。 コンマ区切り値 (.csv) または HTML 形式にレポートをエクスポートできます。|
|**保存**|**[新しいレポートの作成]** ページで、各ユーザーは最大 100 レポートを保存できます。 要件に応じたレポート パラメーターを構成し、**[保存]**を選択するか、別の名前を使用する場合は **[名前を付けて保存]** を選択します。|
|**読み込み**|以前に保存したレポート パラメーターを取得する場合は、**[新しいレポートの作成]** ページで **[読み込み]** を選択します。|
|**削除**|**[レポート]** ワークスペースで、目的のレポートの種類を選択して **[読み込み]** を選択します。 次に、レポートの一覧で、レポートの横にある削除 (x) アイコンを選択します。|


