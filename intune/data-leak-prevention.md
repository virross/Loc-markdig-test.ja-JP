---
title: "管理されていないデバイスでのデータ漏洩の防止"
description: "デバイス上での企業データへのアクセスを許可し、データ漏洩を防ぎます。"
keywords: "データ保護 漏洩の防止 デバイス O365 Office 365"
author: arob98
manager: angrobe
ms.date: 09/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1512c3a-3bbd-4111-a0df-c874a0a335df
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ddaa5bc2f2f8ed8b75296fdea826649a9cef125a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="prevent-data-leaks-on-non-managed-devices"></a><span data-ttu-id="b8701-104">管理されていないデバイスでのデータ漏洩の防止</span><span class="sxs-lookup"><span data-stu-id="b8701-104">Prevent data leaks on non-managed devices</span></span>

<span data-ttu-id="b8701-105">Office 365 でホストされている会社のデータへのアクセスを許可すると、意図的または偶発的なデータ漏洩のリスクなしでユーザーがデータを共有したり保存したりする方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="b8701-105">If you allow access to company data hosted by Office 365, you can control how users share and save data without risking intentional or accidental data leaks.</span></span> <span data-ttu-id="b8701-106">Microsoft Intune は、ユーザーが所有するデバイス上の会社データの保護のために設定するアプリの保護ポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="b8701-106">Microsoft Intune provides app protection policies that you set to secure you company data on user-owned devices.</span></span> <span data-ttu-id="b8701-107">デバイスを Intune サービスに登録する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b8701-107">The devices do not need to be enrolled in the Intune service.</span></span> 

<span data-ttu-id="b8701-108">Intune で設定されたアプリの保護ポリシーは、Microsoft 以外のデバイス管理ソリューションで管理されるデバイスでも動作します。</span><span class="sxs-lookup"><span data-stu-id="b8701-108">App protection policies set up with Intune also work on devices managed with a non-Microsoft device management solution.</span></span> <span data-ttu-id="b8701-109">IT 部門によって管理されるのは会社のデータのみで、デバイス上の個人データは管理されません。</span><span class="sxs-lookup"><span data-stu-id="b8701-109">The personal data on the devices is not touched; only company data is managed by the IT department.</span></span> 

<span data-ttu-id="b8701-110">Windows、iOS、Android が実行されているデバイスの Office モバイル アプリにアプリの保護ポリシーを設定して会社のデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="b8701-110">You can set app protection policies for Office mobile apps on devices running Windows, iOS, or Android to protect company data.</span></span> <span data-ttu-id="b8701-111">これらのポリシーにより、アプリベースの PIN や会社のデータの暗号化などのポリシー設定だけでなく、ユーザーが管理対象/管理対象外のアプリ間で切り取り、コピー、貼り付け、名前を付けて保存の機能を使用する方法を制限するための詳細な設定もできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8701-111">These policies let you set policies such as app-based PIN or company data encryption, or more advanced settings to restrict how you cut, copy, paste, and save-as features are used by users between managed and unmanaged apps.</span></span> <span data-ttu-id="b8701-112">ユーザーがデバイスを登録していなくても、会社のデータをリモートでワイプすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b8701-112">You can also remotely wipe company data without requiring users enroll devices.</span></span> 

<span data-ttu-id="b8701-113">Intune アプリの保護ポリシーは、デバイスの管理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="b8701-113">Intune app protection policies are independent of device management.</span></span> <span data-ttu-id="b8701-114">アプリの保護ポリシーにより、Intune で管理されるデバイスでも管理されないデバイスでも、さらには Microsoft 以外の MDM ソリューションで管理されるデバイスでも、Office モバイル アプリを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8701-114">App protection policies let you manage Office mobile apps on both unmanaged and Intune-managed devices, as well as device managed by non-Microsoft MDM solutions.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="b8701-115">始める前に</span><span class="sxs-lookup"><span data-stu-id="b8701-115">Before you begin</span></span>

<span data-ttu-id="b8701-116">次の行動計画は、次の要件を満たすことで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8701-116">The following action plan can be used when you meet the following requirements:</span></span>
* <span data-ttu-id="b8701-117">会社が、クラウドに安全に移行する準備ができている。</span><span class="sxs-lookup"><span data-stu-id="b8701-117">Your company is ready to transition securely to the cloud.</span></span>
* <span data-ttu-id="b8701-118">会社が Office 365 Exchange Online、SharePoint Online、OneDrive for Business、または Yammer を使用している。</span><span class="sxs-lookup"><span data-stu-id="b8701-118">Your company uses Office 365 Exchange Online, SharePoint Online, OneDrive for Business, or Yammer.</span></span>
* <span data-ttu-id="b8701-119">会社が Microsoft 365、Enterprise Mobility + Security (EMS)、または Azure Information Protection のライセンスを持っている。</span><span class="sxs-lookup"><span data-stu-id="b8701-119">Your company has licenses for Microsoft 365, Enterprise Mobility + Security (EMS), or Azure Information Protection.</span></span>
* <span data-ttu-id="b8701-120">会社が会社所有の、または個人所有の Windows、iOS、Android デバイスから会社のデータへのアクセスをユーザーに許可している。</span><span class="sxs-lookup"><span data-stu-id="b8701-120">Your company allows users to access company data from company-owned or personally-owned Windows, iOS, or Android devices.</span></span> 
* <span data-ttu-id="b8701-121">会社がデバイス管理サービスで個人所有のデバイスの登録を求めていない。</span><span class="sxs-lookup"><span data-stu-id="b8701-121">Your company does not want to require enrollment of personally-owned devices in a device management service.</span></span> 

## <a name="action-plan"></a><span data-ttu-id="b8701-122">行動計画</span><span class="sxs-lookup"><span data-stu-id="b8701-122">Action plan</span></span>

<span data-ttu-id="b8701-123">iOS および Android デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="b8701-123">For iOS and Android devices:</span></span> 

1. <span data-ttu-id="b8701-124">[アプリ保護ポリシー](app-protection-policy.md)のしくみをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="b8701-124">Learn how [app protection policies](app-protection-policy.md) work.</span></span>
2. <span data-ttu-id="b8701-125">Office モバイル アプリで[アプリ保護ポリシーを作成して展開する](app-protection-policies.md)方法をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="b8701-125">Learn how to [create and deploy app protection policies](app-protection-policies.md) for Office mobile apps.</span></span> 
3. <span data-ttu-id="b8701-126">作成して展開した[アプリ保護ポリシーを監視](app-protection-policies-monitor.md)します。</span><span class="sxs-lookup"><span data-stu-id="b8701-126">[Monitor the app protection policies](app-protection-policies-monitor.md) that you create and deploy.</span></span> 

<span data-ttu-id="b8701-127">Windows 10 デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="b8701-127">For Windows 10 devices:</span></span> 

1. <span data-ttu-id="b8701-128">[Windows 情報保護 (WIP) のしくみ](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="b8701-128">Learn [how Windows Information Protection (WIP) works](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span> 
2. <span data-ttu-id="b8701-129">[Windows 10 用のアプリ保護ポリシー](app-protection-policies-configure-windows-10.md)を構成する準備をします。</span><span class="sxs-lookup"><span data-stu-id="b8701-129">Get ready to configure [app protection policies for Windows 10](app-protection-policies-configure-windows-10.md).</span></span>
3. <span data-ttu-id="b8701-130">[Intune で WIP アプリ保護ポリシーを作成して展開します](windows-information-protection-policy-create.md)。</span><span class="sxs-lookup"><span data-stu-id="b8701-130">[Create and deploy WIP app protection policies with Intune](windows-information-protection-policy-create.md).</span></span>

## <a name="what-to-tell-employees-and-students"></a><span data-ttu-id="b8701-131">社員や学生に伝えること</span><span class="sxs-lookup"><span data-stu-id="b8701-131">What to tell employees and students</span></span>

<span data-ttu-id="b8701-132">必要に応じて、追加情報を提供する次のリンクを共有してください。</span><span class="sxs-lookup"><span data-stu-id="b8701-132">As appropriate, share the following links to provide additional information:</span></span> 
* [<span data-ttu-id="b8701-133">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="b8701-133">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)
* [<span data-ttu-id="b8701-134">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="b8701-134">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md) 

## <a name="next-steps"></a><span data-ttu-id="b8701-135">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b8701-135">Next steps</span></span>

<span data-ttu-id="b8701-136">EMS または Office 365 のさまざまなシナリオを有効にする支援をご希望ですか?</span><span class="sxs-lookup"><span data-stu-id="b8701-136">Want help enabling this or other EMS or Office 365 scenarios?</span></span> <span data-ttu-id="b8701-137">Microsoft 365、Enterprise Mobility + Security、または Azure Active Directory Premium のライセンスを 150 以上お持ちでしたら、[FastTrack の特典](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program)をご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="b8701-137">If you have at least 150 licenses for Microsoft 365, Enterprise Mobility + Security, or Azure Active Directory Premium, use your [FastTrack benefits](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program).</span></span> 