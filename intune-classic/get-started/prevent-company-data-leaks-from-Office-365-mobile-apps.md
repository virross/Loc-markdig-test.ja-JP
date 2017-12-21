---
title: "Office 365 モバイル アプリから会社のデータが漏えいすることを防止する"
description: "Intune を使用して、Office 365 モバイル アプリやその他の基幹業務 (LOB) アプリから会社のデータが漏洩することを防止するために役立つモバイル アプリ管理 (MAM) ポリシーを使用して、組織のデータをセキュリティで保護できます。"
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a1b792148371d61132b5c5d7f16be6c3eb2d2355
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a><span data-ttu-id="d85a0-103">クイック スタート ガイド: Office 365 モバイル アプリから会社のデータが漏洩することを防止する</span><span class="sxs-lookup"><span data-stu-id="d85a0-103">Quick Start Guide: Prevent company data leaks from Office 365 mobile apps</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="d85a0-104">Microsoft Intune では、Office 365 モバイル アプリやその他の基幹業務 (LOB) アプリから会社のデータが漏洩することを防止するために役立つモバイル アプリケーション管理 (MAM) ポリシーを使用して、組織のデータをセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="d85a0-104">Microsoft Intune can help you secure your organization’s data using mobile application management (MAM) policies that help prevent company data leaks from Office 365 mobile apps or other line of business (LOB) apps.</span></span> <span data-ttu-id="d85a0-105">Intune MAM ポリシーは、エンドユーザーによる Intune モバイル デバイス管理 (MDM) へのデバイスの登録なしで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d85a0-105">Intune MAM policies can be used without requiring end users to enroll their devices in Intune mobile device management (MDM).</span></span> <span data-ttu-id="d85a0-106">したがって、Microsoft MDM ソリューション (Intune、Configuration Manager、または EAS) に BYOD iOS または Android モバイル デバイスを登録しないユーザーがいる場合でも、エンド ユーザーのデバイスの管理なしで会社のデータを保護することができます。また、Microsoft 以外の MDM ソリューションを既に使用している場合は、Intune で会社のデータ セキュリティを強化できます。</span><span class="sxs-lookup"><span data-stu-id="d85a0-106">So, if you have users who do not want to enroll their BYOD iOS or Android mobile devices into a Microsoft MDM solution (Intune, Configuration Manager, or EAS), you want to protect corporate data without managing end users devices, or you are already using a non-Microsoft MDM solution, Intune can help you increase your company’s data security.</span></span>   

## <a name="is-this-quick-start-guide-right-for-me"></a><span data-ttu-id="d85a0-107">このクイック スタート ガイドの対象読者</span><span class="sxs-lookup"><span data-stu-id="d85a0-107">Is this quick start guide right for me?</span></span>
<span data-ttu-id="d85a0-108">iOS および Android デバイスをモバイル デバイス管理 (MDM) ソリューションに登録せずに Office 365 および LOB アプリ データにアクセスすることをエンド ユーザーに許可するが、エンド ユーザーが何を実行でき、何を実行できないか (個人のアプリへのデータのコピーや貼り付けなど) を制御したいと考えていますか。</span><span class="sxs-lookup"><span data-stu-id="d85a0-108">Would you like to allow your end users to access your Office 365 and LOB app data on their iOS and Android devices without requiring device enrollment in a Mobile Device Management (MDM) solution, but still control what they can or cannot do with that data such as copying and pasting it onto personal apps?</span></span>

<span data-ttu-id="d85a0-109">そう考えているのであれば、Microsoft Intune を使用して、iOS と Android 上の Office 365 モバイル アプリに適用する MAM ポリシー (切り取り/コピー/貼り付け制限、[名前を付けて保存] の使用不可、PIN 要件の設定など) を設定し、MAM 保護対象データをリモートで削除できます。</span><span class="sxs-lookup"><span data-stu-id="d85a0-109">If yes, Microsoft Intune allows you to set MAM policies for Office 365 mobile apps on iOS and Android, including cut/copy/paste restrictions, preventing ‘save-as’, setting PIN requirements, and the ability to remotely wipe MAM protected data.</span></span>  <span data-ttu-id="d85a0-110">これによって、MDM ソリューションへのデバイスの登録をユーザーに要求しなくても会社のデータを保護することができ、Office モバイル アプリの優れたエンド ユーザー エクスペリエンスを維持できます。</span><span class="sxs-lookup"><span data-stu-id="d85a0-110">This protects company data without requiring users to enroll their devices into an MDM solution while maintaining a great end-user experience with Office mobile apps.</span></span>

## <a name="how-do-i-do-it"></a><span data-ttu-id="d85a0-111">実行方法</span><span class="sxs-lookup"><span data-stu-id="d85a0-111">How do I do it?</span></span>
1.  <span data-ttu-id="d85a0-112">[Intune モバイル アプリケーション管理 (MAM)](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) がどのように機能するかについて、その基本を理解します。</span><span class="sxs-lookup"><span data-stu-id="d85a0-112">Get a basic understanding of [how Intune mobile application management (MAM)](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) works.</span></span>
2.  <span data-ttu-id="d85a0-113">Azure ポータルで [MAM ポリシーを作成する前に実行する必要があること](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)を確認します。</span><span class="sxs-lookup"><span data-stu-id="d85a0-113">Find out [what you need to do before you can create MAM policies](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) in the Azure portal.</span></span>
3.  <span data-ttu-id="d85a0-114">Intune で [MAM ポリシーを作成して展開](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)します。</span><span class="sxs-lookup"><span data-stu-id="d85a0-114">[Create and deploy MAM policies](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) with Intune.</span></span>

### <a name="additional-information"></a><span data-ttu-id="d85a0-115">追加情報:</span><span class="sxs-lookup"><span data-stu-id="d85a0-115">Additional information:</span></span>
- <span data-ttu-id="d85a0-116">MAM 対応アプリでの[エンド ユーザー エクスペリエンス](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="d85a0-116">[End user experience](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) using MAM enabled apps.</span></span>
- [<span data-ttu-id="d85a0-117">Intune で MAM 用に LOB アプリを準備する</span><span class="sxs-lookup"><span data-stu-id="d85a0-117">Prepare LOB apps for MAM with Intune</span></span>](/intune/apps-prepare-mobile-application-management)
- <span data-ttu-id="d85a0-118"><a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank"> Microsoft Intune アプリケーション パートナー一覧 &rarr;</a> MAM 対応アプリの提供</span><span class="sxs-lookup"><span data-stu-id="d85a0-118"><a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank"> List of Microsoft Intune application partners &rarr;</a> providing MAM-enabled apps.</span></span>

## <a name="what-should-i-do-next"></a><span data-ttu-id="d85a0-119">次にすべきこと</span><span class="sxs-lookup"><span data-stu-id="d85a0-119">What should I do next?</span></span>
[<span data-ttu-id="d85a0-120">Microsoft MDM 以外のソリューションから Microsoft Intune に移行する</span><span class="sxs-lookup"><span data-stu-id="d85a0-120">Migrate from a non-Microsoft MDM solution to Microsoft Intune</span></span>](/intune-classic/deploy-use/migrate-to-intune)

[<span data-ttu-id="d85a0-121">Intune MDM にデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="d85a0-121">Enroll devices into Intune MDM</span></span>](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
