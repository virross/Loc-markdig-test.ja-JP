---
title: "データ暗号化で会社のデータを保護する"
description: "このガイドでは、モバイル アプリでポリシーを使用してパスコードとデータ暗号化を強制することによりデータ損失から会社を保護する方法を説明します。"
keywords: "暗号化, PIN, データ"
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 97e8c89101a4e14d83216102ac6178b2d127e949
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="quick-start-guide-protect-company-data-with-data-encryption"></a><span data-ttu-id="fc49a-104">クイック スタート ガイド: データの暗号化により会社のデータを保護する</span><span class="sxs-lookup"><span data-stu-id="fc49a-104">Quick Start Guide: Protect company data with data encryption</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="fc49a-105">Microsoft Intune は、次のようなさまざまな方法で Office モバイル アプリからデータ損失を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fc49a-105">Microsoft Intune can help you prevent data loss from Office mobile apps in a variety of ways, including:</span></span>
- <span data-ttu-id="fc49a-106">IOS および Android で提供される最高レベルのデバイス暗号化で企業のデータを暗号化。</span><span class="sxs-lookup"><span data-stu-id="fc49a-106">By encrypting corporate data with the highest level of device encryption provided by iOS and Android.</span></span>
- <span data-ttu-id="fc49a-107">プライバシーや法的要件のためにモバイル デバイス管理ソリューションに登録できない IOS および Android デバイス。</span><span class="sxs-lookup"><span data-stu-id="fc49a-107">On iOS and Android devices that, because of privacy or legal requirements, cannot be enrolled in a mobile device management solution.</span></span>

<span data-ttu-id="fc49a-108">Microsoft Intune は、iOS または Android モバイル デバイスを完全なモバイル デバイス管理に登録することなく Office モバイル アプリからのデータ損失を回避して Office 365 (O365) データを保護するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fc49a-108">Microsoft Intune can also help you prevent data loss from Office mobile apps and secure Office 365 (O365) data without having to enroll iOS or Android mobile devices in full mobile device management.</span></span> <span data-ttu-id="fc49a-109">管理対象モバイル デバイスにサード パーティ製のモバイル デバイス管理ソリューションを使用している場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="fc49a-109">This is true even if you use a third-party mobile device management solution to managed mobile devices.</span></span>

## <a name="is-this-quick-start-guide-right-for-me"></a><span data-ttu-id="fc49a-110">このクイック スタート ガイドの対象読者</span><span class="sxs-lookup"><span data-stu-id="fc49a-110">Is this quick start guide right for me?</span></span>
<span data-ttu-id="fc49a-111">次の前提条件を満たしている場合、このクイック スタート ガイドは適切なリソースです。</span><span class="sxs-lookup"><span data-stu-id="fc49a-111">This quick start guide is a good resource if you meet the following prerequisites:</span></span>
- <span data-ttu-id="fc49a-112">O365 ライセンスを既に使用しているか、使用するために入手してあり、Office モバイル アプリを管理している。</span><span class="sxs-lookup"><span data-stu-id="fc49a-112">You already use or have O365 licenses that you want to use and you manage Office mobile apps.</span></span>
- <span data-ttu-id="fc49a-113">IOS または Android で Office モバイル アプリを使用する予定である。</span><span class="sxs-lookup"><span data-stu-id="fc49a-113">You are planning to use Office mobile apps on iOS or Android.</span></span>
- <span data-ttu-id="fc49a-114">Microsoft または Microsoft 以外の何らかのモバイル デバイス管理ソリューションを使用している。</span><span class="sxs-lookup"><span data-stu-id="fc49a-114">You use any mobile device management solution - Microsoft or non-Microsoft.</span></span> <span data-ttu-id="fc49a-115">法的な規則のためにモバイル デバイス管理ソリューションを使用できない場合は、このガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fc49a-115">If you cannot use a mobile device management solution because of statutory rules, this guide is something that you can use.</span></span>

> [!NOTE]
> <span data-ttu-id="fc49a-116">Windows は、まだ Office モバイル アプリに対してサポートされているプラットフォームではありません。</span><span class="sxs-lookup"><span data-stu-id="fc49a-116">Windows is not yet a supported platform for Office mobile apps.</span></span> <span data-ttu-id="fc49a-117">登録不要のモバイル アプリケーション管理は、まだオンプレミスの Exchange または SharePoint と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="fc49a-117">Mobile application management without enrollment is not yet compatible with Exchange or SharePoint on-premise.</span></span> <span data-ttu-id="fc49a-118">保護できるのはオンライン バージョンでホストされているデータだけです。</span><span class="sxs-lookup"><span data-stu-id="fc49a-118">You can only protect data hosted in online versions.</span></span>

<span data-ttu-id="fc49a-119">このガイドでは、デバイス管理ソリューションへの完全な登録を必要とせずに、機密データにアクセスするために従業員が使用しているモバイル アプリでポリシーを使用してパスコードとデータ暗号化を強制することにより、データ損失から会社を保護する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="fc49a-119">This guide can help you protect your company from data loss by forcing passcodes and data encryption using policies on the mobile apps that your employees use to access sensitive data, without requiring full enrollment in any device management solution.</span></span> <span data-ttu-id="fc49a-120">Microsoft Intune では、[iOS](https://products.office.com/mobile/office-mobile-apps-for-ios) および [Android](https://products.office.com/mobile/office-mobile-apps-for-android) 用の Office モバイル アプリにモバイル アプリケーション管理 (MAM) ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="fc49a-120">Microsoft Intune allows you to set mobile application management (MAM) policies on Office mobile apps for [iOS](https://products.office.com/mobile/office-mobile-apps-for-ios) and [Android](https://products.office.com/mobile/office-mobile-apps-for-android).</span></span> <span data-ttu-id="fc49a-121">これにより、モバイル デバイス管理ソリューションへのデバイスの登録をユーザーに要求しなくても O365 のデータを保護することができ、Office モバイル アプリの優れたエンド ユーザー エクスペリエンスを維持できます。</span><span class="sxs-lookup"><span data-stu-id="fc49a-121">This approach protects O365 data without requiring users to enroll their devices into a mobile device management solution while also maintaining a great end-user experience with Office mobile apps.</span></span>

## <a name="how-do-i-do-it"></a><span data-ttu-id="fc49a-122">実行方法</span><span class="sxs-lookup"><span data-stu-id="fc49a-122">How do I do it?</span></span>
1.  [<span data-ttu-id="fc49a-123">アプリ データを保護する方法を確認する</span><span class="sxs-lookup"><span data-stu-id="fc49a-123">Review how you can protect app data</span></span>](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
2.  [<span data-ttu-id="fc49a-124">モバイル アプリ管理ポリシーを構成する準備</span><span class="sxs-lookup"><span data-stu-id="fc49a-124">Get ready to configure mobile app management policies</span></span>](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
3.  [<span data-ttu-id="fc49a-125">モバイル アプリ管理ポリシーの作成および展開</span><span class="sxs-lookup"><span data-stu-id="fc49a-125">Create and deploy mobile app management policies</span></span>](/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <a name="additional-information"></a><span data-ttu-id="fc49a-126">追加情報:</span><span class="sxs-lookup"><span data-stu-id="fc49a-126">Additional information:</span></span>
- [<span data-ttu-id="fc49a-127">Microsoft Intune での MAM 対応アプリのエンド ユーザー エクスペリエンスについて確認します。</span><span class="sxs-lookup"><span data-stu-id="fc49a-127">Find out about the end user experience for MAM enabled apps with Microsoft Intune.</span></span>](/intune-classic/eploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)
- [<span data-ttu-id="fc49a-128">Microsoft Intune によるモバイル アプリケーション管理のためにアプリを準備する方法を決めます。</span><span class="sxs-lookup"><span data-stu-id="fc49a-128">Decide how to prepare apps for mobile application management with Microsoft Intune.</span></span>](/intune/apps-prepare-mobile-application-management)
- [<span data-ttu-id="fc49a-129">Microsoft Intune アプリケーション パートナー一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="fc49a-129">View the list of Microsoft Intune application partners</span></span>](https://www.microsoft.com/cloud-platform/microsoft-intune-partners)
