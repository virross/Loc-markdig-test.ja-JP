---
title: "構成ポリシー リファレンス"
description: "このトピックの情報は、デバイスの管理に使用する必要がある Microsoft Intune ポリシーを判断するのに役立ちます。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 201fe732153a1ff2958b2139b416f89d67826aad
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="microsoft-intune-configuration-policy-reference"></a>Microsoft Intune の構成ポリシー リファレンス

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

このトピックの情報は、デバイスの管理に使用する必要がある Microsoft Intune 構成ポリシーを判断するのに役立ちます。

> [!TIP]
> ポリシーの使用方法の詳細については、「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)」を参照してください。


## <a name="android-configuration-policies"></a>Android 構成ポリシー

|ポリシー名|使用するタイミング|
|---------------|------------------------|
|**カスタム構成 (Android 4 以降、Samsung KNOX Standard 4.0 以降)**<br><br>**カスタム構成 (Android for Work)**|デバイスの機能を制御するために使用できる、Wi-Fi 設定などの Open Mobile Alliance Uniform Resource Identifier (OMA-URI) の設定を展開します。 これは、必要な設定が構成ポリシーで使用できない場合に役立ちます。<br /><br />詳細については、「[Microsoft Intune の Android および Samsung KNOX 構成ポリシー設定](android-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**電子メール プロファイル (Samsung KNOX Standard 4.0 以降)**<br><br>**電子メール プロファイル (Android for Work - Gmail)**<br><br>**電子メール プロファイル (Android for Work - Nine Work)**|管理対象デバイスで Exchange ActiveSync 電子メール設定を作成、展開、および監視します。 これにより、ユーザー側で特別な設定を行わなくても、各自が個人用端末で会社の電子メールにアクセスできます。<br /><br />詳細については、「[Microsoft Intune で電子メール プロファイルを使用して会社の電子メールへのアクセスを構成にする](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)」を参照してください。|
|**全般構成 (Android 4 以降、Samsung KNOX Standard 4.0 以降)**<br><br>**全般構成 (Android for Work)**|モバイル デバイスのセキュリティと機能の設定を構成します。<br />準拠アプリまたは非準拠アプリを指定し、それらのアプリが使用された場合にレポートします。<br />特定の機能のみが動作するようにデバイスをロックするキオスク モードを構成して、たとえば、デバイスでアプリを 1 つだけ実行できるようにしたり、音量ボタンを無効にしたりします。<br /><br />詳細については、「[Microsoft Intune の Android および Samsung KNOX 構成ポリシー設定](android-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**PKCS #12 (.PFX) 証明書プロファイル (Android 4 以降)**<br><br>**PKCS #12 (.PFX) 証明書プロファイル (Android for Work)**|このプロファイルは、デバイス証明書要求のための .PFX 設定を作成して展開する場合に使用します。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**SCEP 証明書プロファイル (Android 4 以降)**<br><br>**SCEP 証明書プロファイル (Android for Work)**|Simple Certificate Enrollment Protocol 証明書を構成します。これを信頼できるモバイル デバイスの証明書と共に使用してモバイル デバイスを認証して、モバイル デバイスが Wi-Fi プロファイルおよび VPN プロファイルによって構成されたネットワーク リソースにアクセスできるようにします。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**信頼できる証明書プロファイル (Android 4 以降)**<br><br>**信頼済み証明書プロファイル (Android for Work)**|信頼できるモバイル デバイスの証明書を構成します。これを使用してモバイル デバイスを認証して、モバイル デバイスが Wi-Fi プロファイルおよび VPN プロファイルによって構成されたネットワーク リソースにアクセスできるようにします。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**VPN プロファイル (Android 4 以降)**<br><br>**VPN プロファイル (Android for Work)**|ユーザーがモバイル デバイスから企業ネットワークにアクセスする際にセキュリティ保護を提供する設定を構成および展開します。 これらの設定を展開することで、会社へのエンド ユーザーの接続が簡単になります。<br /><br />詳細については、「[Microsoft Intune での VPN 接続](vpn-connections-in-microsoft-intune.md)」を参照してください。|
|**Wi-Fi プロファイル (Android 4 以降)**<br><br>**Wi-Fi プロファイル (Android for Work)**|ワイヤレス ネットワーク設定を構成して組織のユーザーに展開します。 これらの設定を展開することで、ワイヤレス ネットワークへのエンド ユーザーの接続が簡単になります。<br /><br />詳細については、「[Microsoft Intune での Wi-Fi 接続](wi-fi-connections-in-microsoft-intune.md)」を参照してください。|
|**モバイル アプリ構成ポリシー (Android for Work)**|モバイル アプリ構成ポリシーを使用すると、ユーザーが Android for Work アプリを実行している場合に必要となる可能性のある設定を自動的に提供できます。<br /><br />詳細については、「[Microsoft Intune でのモバイル アプリ構成ポリシーを使用した Android for Work アプリの構成](afw-app-configuration-policy.md)」を参照してください。

## <a name="ios-configuration-policies"></a>iOS 構成ポリシー

|ポリシー名|使用するタイミング|
|---------------|------------------------|
|**カスタム構成 (iOS 8.0 以降)**|Apple Configurator を使用して作成した構成プロファイルを iOS デバイスに展開します。 これは、必要な設定が構成ポリシーで使用できない場合に役立ちます。<br /><br />詳細については、「[Microsoft Intune の iOS ポリシー設定](ios-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**電子メール プロファイル (iOS 8.0 以降)**|管理対象デバイスで Exchange ActiveSync 電子メール設定を作成、展開、および監視します。 これにより、ユーザー側で特別な設定を行わなくても、各自が個人用端末で会社の電子メールにアクセスできます。<br /><br />詳細については、「[Microsoft Intune で電子メール プロファイルを使用して会社の電子メールへのアクセスを構成にする](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)」を参照してください。|
|**全般構成 (iOS 8.0 以降)**|モバイル デバイスのセキュリティと機能の設定を構成します。<br />準拠アプリまたは非準拠アプリを指定し、それらのアプリが使用された場合にレポートします。<br />特定の機能のみが動作するようにデバイスをロックするキオスク モードを構成して、たとえば、デバイスでアプリを 1 つだけ実行できるようにしたり、音量ボタンを無効にしたりします。<br /><br />詳細については、「[Microsoft Intune の iOS ポリシー設定](ios-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**モバイル アプリ構成ポリシー (iOS 8.0 以降)**|モバイル アプリ構成ポリシーを使用すると、ユーザーが iOS アプリを実行している場合に必要となる可能性のある設定を自動的に提供できます。<br /><br />詳細については、「[Microsoft Intune のモバイル アプリ構成ポリシーを使用した iOS アプリの構成](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md)」を参照してください。|
|**モバイル プロビジョニング プロファイル ポリシー (iOS 8.0 以降)**|Apple iOS 基幹業務モバイル アプリは、プロビジョニング プロファイルを含み、証明書で署名されたコードと共に構築されます。 iOS デバイスでアプリを実行すると、iOS により iOS アプリの整合性の確認と、プロビジョニング プロファイルで定義されたポリシーの施行が行われます。<br><br>アプリの署名に使用するエンタープライズ署名証明書は、通常 3 年間は継続します。 ただし、プロビジョニング プロファイルは 1 年後に期限が切れます。 このポリシーは、証明書はまだ有効だがアプリの有効期限が近づいているデバイスに新しいプロビジョニング プロファイルのポリシーを事前に展開するために使用します。<br><br>詳細については、「[iOS モバイル プロビジョニング プロファイルのポリシーを使用して、アプリが期限切れにならないようにする](ios-mobile-app-provisioning-profiles.md)」を参照してください。|
|**PKCS #12 (.PFX) 証明書プロファイル (iOS 8.0 以降)**|このプロファイルは、デバイス証明書要求のための .PFX 設定を作成して展開する場合に使用します。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**SCEP 証明書プロファイル (iOS 8.0 以降)**|Simple Certificate Enrollment Protocol 証明書を構成します。これを信頼できるモバイル デバイスの証明書と共に使用してモバイル デバイスを認証して、モバイル デバイスが Wi-Fi プロファイルおよび VPN プロファイルによって構成されたネットワーク リソースにアクセスできるようにします。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**信頼できる証明書プロファイル (iOS 8.0 以降)**|信頼できるモバイル デバイスの証明書を構成します。これを使用してモバイル デバイスを認証して、モバイル デバイスが Wi-Fi プロファイルおよび VPN プロファイルによって構成されたネットワーク リソースにアクセスできるようにします。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**VPN プロファイル (iOS 8.0 以降)**|ユーザーがモバイル デバイスから企業ネットワークにアクセスする際にセキュリティ保護を提供する設定を構成および展開します。 これらの設定を展開することで、会社へのエンド ユーザーの接続が簡単になります。<br /><br />詳細については、「[Microsoft Intune での VPN 接続](vpn-connections-in-microsoft-intune.md)」を参照してください。|
|**Wi-Fi プロファイル (iOS 8.0 以降)**|ワイヤレス ネットワーク設定を構成して組織のユーザーに展開します。 これらの設定を展開することで、ワイヤレス ネットワークへのエンド ユーザーの接続が簡単になります。<br /><br />詳細については、「[Microsoft Intune での Wi-Fi 接続](wi-fi-connections-in-microsoft-intune.md)」を参照してください。|


## <a name="mac-os-x-configuration-policies"></a>Mac OS X 構成ポリシー

|ポリシー名|使用するタイミング|
|---------------|------------------------|
|**カスタム構成 (Mac OS X 10.9 以降)**|Apple Configurator を使用して作成した構成プロファイルを Mac コンピューターに展開します。 これは、必要な設定が構成ポリシーで使用できない場合に役立ちます。<br /><br />詳細については、「[Microsoft Intune の Mac OS X 構成ポリシー設定](mac-os-x-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**一般構成 (Mac OS X 10.9 以降)**|モバイル デバイスのセキュリティと機能の設定を構成します。<br />準拠アプリまたは非準拠アプリを指定し、それらのアプリが使用された場合にレポートします。<br /><br />詳細については、「[Microsoft Intune の Mac OS X 構成ポリシー設定](mac-os-x-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**SCEP 証明書プロファイル (Mac OS X 10.9 以降)**|Simple Certificate Enrollment Protocol 証明書を構成します。これを信頼できるモバイル デバイスの証明書と共に使用してモバイル デバイスを認証して、モバイル デバイスが Wi-Fi プロファイルおよび VPN プロファイルによって構成されたネットワーク リソースにアクセスできるようにします。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**信頼できる証明書プロファイル (Mac OS X 10.9 以降)**|信頼できるモバイル デバイスの証明書を構成します。これを使用してモバイル デバイスを認証して、モバイル デバイスが Wi-Fi プロファイルおよび VPN プロファイルによって構成されたネットワーク リソースにアクセスできるようにします。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**VPN プロファイル (Mac OS X 10.9 以降)**|ユーザーがモバイル デバイスから企業ネットワークにアクセスする際にセキュリティ保護を提供する設定を構成および展開します。 これらの設定を展開することで、会社へのエンド ユーザーの接続が簡単になります。<br /><br />詳細については、「[Microsoft Intune での VPN 接続](vpn-connections-in-microsoft-intune.md)」を参照してください。|
|**Wi-Fi プロファイル (Mac OS X 10.9 以降)**|ワイヤレス ネットワーク設定を構成して組織のユーザーに展開します。 これらの設定を展開することで、ワイヤレス ネットワークへのエンド ユーザーの接続が簡単になります。<br /><br />詳細については、「[Microsoft Intune での Wi-Fi 接続](wi-fi-connections-in-microsoft-intune.md)」を参照してください。|

## <a name="windows-configuration-policies"></a>Windows 構成ポリシー
Windows Phone と登録されている Windows デバイスのみに適用されます。

|ポリシー名|使用するタイミング|
|---------------|------------------------|
|**カスタム構成 (Windows 10 デスクトップおよび Windows 10 Mobile 以降)**|デバイスの機能を制御するために使用できる OMA-URI 設定を展開します。 これは、必要な設定が構成ポリシーで使用できない場合に役立ちます。<br />    詳細については、「[Microsoft Intune の Windows 10 ポリシー設定](windows-10-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**カスタム構成 (Windows Phone 8.1 以降)**|デバイスの機能を制御するために使用できる OMA-URI 設定を展開します。 これは、必要な設定が構成ポリシーで使用できない場合に役立ちます。<br /><br />詳細については、「[Microsoft Intune の Windows Phone 8.1 ポリシー設定](windows-phone-8-1-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**エディションのアップグレード ポリシー (Windows 10 Desktop 以降)**<br><br>**エディションのアップグレード ポリシー (Windows 10 Holographic 以降)**<br><br>**エディションのアップグレード ポリシー (Windows 10 Mobile 以降)**|Windows 10 デバイスを新しいバージョンに更新するために使用されるライセンスまたはプロダクト キーの情報を含むポリシーを構成して展開します。<br><br>詳細については、「[Microsoft Intune のエディションのアップグレード ポリシー設定](edition-upgrade-policy-settings-in-microsoft-intune.md)」を参照してください。|  
|**電子メール プロファイル (Windows Phone 8.1 以降)**<br /><br />**電子メール プロファイル (Windows 10 デスクトップおよび Windows 10 Mobile 以降)**|管理対象デバイスで Exchange ActiveSync 電子メール設定を作成、展開、および監視します。 これにより、ユーザー側で特別な設定を行わなくても、各自が個人用端末で会社の電子メールにアクセスできます。<br /><br />詳細については、「[Microsoft Intune で電子メール プロファイルを使用して会社の電子メールへのアクセスを構成にする](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)」を参照してください。|
|**全般構成 (Windows 10 デスクトップおよび Windows 10 Mobile 以降)**|登録されている Windows 10 デスクトップおよび Windows 10 Mobile デバイスのモバイル デバイスのセキュリティと機能の設定を構成します。<br /><br />詳細については、「[Microsoft Intune の Windows 10 ポリシー設定](windows-10-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**全般構成 (Windows 10 Team 以降)**|登録されている Windows 10 Team デバイス (たとえば、Surface Hub デバイス) のためにデバイスのセキュリティと機能の設定を構成します。<br /><br />詳細については、「[Microsoft Intune の Windows Team 構成ポリシー設定](windows-team-configuration-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**全般構成 (Windows 8.1 以降)**|登録されている Windows デバイスのモバイル デバイスのセキュリティと機能の設定を構成します。<br /><br />詳細については、「[Windows policy settings in Microsoft Intune](windows-configuration-policy-settings-in-microsoft-intune.md)」 (Microsoft Intune の Windows ポリシー設定) を参照してください。|
|**全般構成 (Windows Phone 8.1 以降)**|モバイル デバイスのセキュリティと機能の設定を構成します。<br />ユーザーが使用できるアプリや使用できないアプリを指定して、非準拠アプリがインストールまたは使用されるのを防ぎます。<br /><br />詳細については、「[Microsoft Intune の Windows Phone 8.1 ポリシー設定](windows-phone-8-1-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**PKCS #12 (.PFX) 証明書プロファイル (Windows 10 デスクトップおよび Windows 10 Mobile 以降)**|このプロファイルは、デバイス証明書要求のための .PFX 設定を作成して展開する場合に使用します。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**SCEP 証明書プロファイル (Windows 8.1 以降)**<br /><br />**SCEP 証明書プロファイル (Windows Phone 8.1 以降)**|Simple Certificate Enrollment Protocol 証明書を構成します。これを信頼できるモバイル デバイスの証明書と共に使用してモバイル デバイスを認証して、モバイル デバイスが Wi-Fi プロファイルおよび VPN プロファイルによって構成されたネットワーク リソースにアクセスできるようにします。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**信頼できる証明書プロファイル (Windows 8.1 以降)**<br /><br />**信頼できる証明書プロファイル (Windows Phone 8.1 以降)**|信頼できるモバイル デバイスの証明書を構成します。これを使用してモバイル デバイスを認証して、モバイル デバイスが Wi-Fi プロファイルおよび VPN プロファイルによって構成されたネットワーク リソースにアクセスできるようにします。<br /><br />詳細については、「[Microsoft Intune の証明書プロファイルでリソースへのアクセスを保護する](secure-resource-access-with-certificate-profiles.md)」を参照してください。|
|**VPN プロファイル (Windows 10 デスクトップおよび Windows 10 Mobile 以降)**<br /><br />**VPN プロファイル (Windows 8.1 以降)**<br /><br />**VPN プロファイル (Windows Phone 8.1 以降)**|ユーザーがモバイル デバイスから企業ネットワークにアクセスする際にセキュリティ保護を提供する設定を構成および展開します。 これらの設定を展開することで、会社へのエンド ユーザーの接続が簡単になります。<br /><br />詳細については、「[Microsoft Intune での VPN 接続](vpn-connections-in-microsoft-intune.md)」を参照してください。|
|**Wi-Fi インポート**|以前にファイルにエクスポートした Windows Wi-Fi の構成をインポートして展開します。<br /><br />詳細については、「[Microsoft Intune での Wi-Fi 接続](wi-fi-connections-in-microsoft-intune.md)」を参照してください。|
|**Windows 情報保護**<br>(旧エンタープライズ データ保護)|企業内に従業員所有デバイスが増加するのに従い、企業のコントロールが届かない電子メール、ソーシャル メディア、パブリック クラウドなどのアプリやサービスを介して偶発的にデータが漏えいするリスクも増大しています。 たとえば、従業員が個人用の電子メール アカウントから最新のエンジニアリング画像を送信したり、製品情報をコピーしてツイートに貼り付けたり、作成中の営業レポートをパブリック クラウドの記憶域に保存したりするときなどです。<br><br>Windows 情報保護は、この潜在的なデータ漏えいの防止に役立ちます。それ以外の場合は従業員のエクスペリエンスを妨げることはありません。 また、企業が所有するデバイスと従業員が作業のために持ち込む個人用デバイスでもエンタープライズ アプリとデータを偶発的なデータ漏えいから保護します。既存の環境や他のアプリを変更する必要はありません。<br><br>この Intune ポリシーは、Windows 情報保護によって保護されているアプリ、エンタープライズ ネットワークの場所、保護レベル、および暗号化設定の一覧を管理します。<br><br>詳細については、「[Protect your enterprise data using Windows Information Protection (Windows 情報保護を使用してエンタープライズ データを保護する)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-edp)」を参照してください。|


## <a name="software-policies"></a>ソフトウェア ポリシー

|ポリシー名|使用するタイミング|
|---------------|------------------------|
|**管理対象ブラウザーのポリシー (Android 4 以降)**<br /><br />**Managed Browser のポリシー (iOS 8.0 以降)**|ユーザーが Managed Browser アプリを使用する場合に、アクセスできる Web サイトとアクセスできない Web サイトを指定します。<br /><br />詳細については、「[Microsoft Intune と Managed Browser のポリシーを使用したインターネット アクセスの管理](manage-internet-access-using-managed-browser-policies.md)」を参照してください。|
|**モバイル アプリケーション管理 (Android 4 以降)**<br /><br />**モバイル アプリケーション管理ポリシー (iOS 8.0 以降)**|展開するアプリの機能を変更することで、アプリが企業のコンプライアンスとセキュリティ ポリシーに従うようにすることができます。 たとえば、制限付きアプリでの切り取り、コピー、および貼り付け操作を制限することや、Managed Browser 内ですべての Web リンクを開くようにアプリを構成することができます。<br /><br />詳細については、「[Microsoft Intune でモバイル アプリケーション管理ポリシーを使用してデータを保護する](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)」を参照してください。|

## <a name="common-mobile-device-settings"></a>一般的なモバイル デバイスの設定

|ポリシー名|使用するタイミング|
|---------------|------------------------|
|**Exchange ActiveSync ポリシー**|Exchange ActiveSync で管理されているデバイスのモバイル デバイスのセキュリティと機能の設定を構成します。<br /><br />詳細については、「[Microsoft Intune の Exchange ActiveSync ポリシー設定](exchange-activesync-policy-settings-in-microsoft-intune.md)」を参照してください。|
|**モバイル デバイスのセキュリティ ポリシー**|<ul><li>モバイル デバイス (すべてのプラットフォーム) の設定を構成します。次の項目が含まれます。<br /><br /><ul><li>セキュリティ</li><li>暗号化</li><li>システム</li><li>電子メール</li><li>アプリケーション</li></ul></li></ul>

> [!IMPORTANT]
> Microsoft Intune では、デバイス プラットフォームごとに**構成ポリシー**が分割されました。それらのポリシーには、使用可能な最新の設定が含まれています。 引き続きモバイル デバイスのセキュリティ ポリシーを使用でき、既存の展開も機能します。ただし、できるだけ早く新しい構成ポリシーに移行することを計画してください。<br />詳細については、「[Microsoft Intune のモバイル デバイス セキュリティ ポリシー設定](mobile-device-security-policy-settings-in-microsoft-intune.md)」を参照してください。

## <a name="policies-for-windows-pcs-managed-by-the-intune-software-client"></a>Intune ソフトウェア クライアントによって管理されている Windows PC のポリシー

|ポリシー名|使用するタイミング|
|---------------|------------------------|
|**Microsoft Intune エージェントの設定**|コンピューターの Intune PC クライアントを構成します。次の設定が含まれます。<br /><br />-   Endpoint Protection<br />-   ソフトウェア更新プログラム<br />-   ポリシー チェックのスケジュール<br /><br />この種のポリシーは、デバイスのグループにのみ展開できます。<br /><br />Intune クライアントは、**[更新プログラムおよびアプリケーションの自動検出頻度]** 設定に従って、新しいポリシーや更新されたポリシーをダウンロードします。既定値は 8 時間です。 いつでも、コンピューターのポリシーの更新を強制的に実行できます。<br /><br />詳細については、「[Microsoft Intune でソフトウェア更新プログラムを使用して Windows PC を最新の状態に保つ](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)」を参照してください。|
|**Microsoft Intune Center の設定**|Microsoft Intune Center に表示される管理対象コンピューターの詳細を構成します。<br /><br />この種のポリシーは、デバイスのグループにのみ展開できます。<br /><br />詳細については、「[Microsoft Intune コンピューター クライアントを使用した一般的な Windows PC 管理タスク](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)」を参照してください。|
|**Windows ファイアウォールの設定**|コンピューターでの一般的なネットワーク通信用の Windows ファイアウォールの設定と例外を構成します。次の項目が含まれます。<br /><br />-   BranchCache<br />-   リモート アシスタンス<br />-   メディア共有<br /><br />この種のポリシーは、デバイスのグループにのみ展開できます。<br /><br />詳細については、「[Microsoft Intune の Endpoint Protection を使用して Windows PC を保護する](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)」を参照してください。|

### <a name="see-also"></a>関連項目

[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
