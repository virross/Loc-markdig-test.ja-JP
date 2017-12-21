---
title: "デバイス管理を要求せずに Office 365 Exchange Online を保護する"
description: "社員に仕事用メールへのアクセスを与えます。 デバイス管理は必要ありません。"
keywords: "Office 365 Exchange 電子メール アクセス"
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cfd4453fe4b50a111a1f43efcdc6ba6447c46f40
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a><span data-ttu-id="ef3ca-105">デバイス管理を要求せずに Office 365 Exchange Online を保護する</span><span class="sxs-lookup"><span data-stu-id="ef3ca-105">Protect Office 365 Exchange Online without requiring device management</span></span>

<span data-ttu-id="ef3ca-106">デバイス管理システムを構築せずに、職場のメールへのアクセスを社員に与えることができます。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-106">If you want to give employees access to their work email without the overhead of setting up a device management system, you can.</span></span> <span data-ttu-id="ef3ca-107">Intune 経由で Office 365 Exchange Online へのアクセスを与えることができます。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-107">You can give access to Office 365 Exchange Online through Intune.</span></span> <span data-ttu-id="ef3ca-108">必要な手順を完了する前に、Microsoft 365 または Azure Active Directory (プレミアム) と Intune のライセンスがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-108">To complete the necessary steps, confirm you have licenses for Microsoft 365, or Azure Active Directory (premium) and Intune.</span></span> <span data-ttu-id="ef3ca-109">社員には、[サポートされている iOS または Android デバイス](supported-devices-browsers.md)を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-109">Employees need to have a [supported iOS or Android device](supported-devices-browsers.md).</span></span> 

<span data-ttu-id="ef3ca-110">デバイス管理システムを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-110">If you decide to set up a device management system, you can.</span></span> <span data-ttu-id="ef3ca-111">この種類のアプリ保護は、デバイス管理とは独立して動作します。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-111">This type of app protection works independently of device management.</span></span> 

## <a name="action-plan"></a><span data-ttu-id="ef3ca-112">行動計画</span><span class="sxs-lookup"><span data-stu-id="ef3ca-112">Action plan</span></span>

1. <span data-ttu-id="ef3ca-113">[条件付きアクセスについて学習します](conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-113">[Learn about conditional access](conditional-access.md).</span></span> 
2. <span data-ttu-id="ef3ca-114">[アプリベースの条件付きアクセスについて学習します](app-based-conditional-access-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-114">[Learn about app-based conditional access](app-based-conditional-access-intune.md).</span></span>
3. <span data-ttu-id="ef3ca-115">[Exchange Online のアプリベースの条件付きアクセス ポリシーを設定します](app-based-conditional-access-intune-create.md)。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-115">[Set up app-based conditional access policies for Exchange Online](app-based-conditional-access-intune-create.md).</span></span>
4. <span data-ttu-id="ef3ca-116">[管理できないアプリをブロックします](app-modern-authentication-block.md)。特に、Azure Active Directory Authentication Library (ADAL) を使用しないアプリをブロックします。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-116">[Block apps that cannot be managed](app-modern-authentication-block.md), specifically apps that do not use the Azure Active Directory Authentication Library (ADAL).</span></span>
5. <span data-ttu-id="ef3ca-117">(任意) [SharePoint Online のアプリベースの条件付きアクセス ポリシーを設定します](app-based-conditional-access-intune-create.md)。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-117">(Optional) [Set up app-based conditional access policies for SharePoint Online](app-based-conditional-access-intune-create.md).</span></span> <span data-ttu-id="ef3ca-118">このポリシーは、管理できないアプリやセキュリティ対策を施せないアプリから会社のデータへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-118">These policies block access to your company data from apps that cannot be managed and secured.</span></span> <span data-ttu-id="ef3ca-119">このポリシーは、SharePoint モバイルからのアクセスも制限します。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-119">The policies also limit access through SharePoint mobile.</span></span> 

## <a name="what-to-tell-employees-and-students"></a><span data-ttu-id="ef3ca-120">社員や学生に伝えること</span><span class="sxs-lookup"><span data-stu-id="ef3ca-120">What to tell employees and students</span></span>

* <span data-ttu-id="ef3ca-121">Microsoft Outlook または Microsoft SharePoint をダウンロードしてインストールするように社員や学生に伝えます。iOS の場合は Apple App Store を、Android の場合は Google Play Store をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-121">Ask your employees and students to download and install Microsoft Outlook or Microsoft SharePoint for iOS from the Apple App Store or for Android from the Google Play Store.</span></span> 
* <span data-ttu-id="ef3ca-122">最新の認証方法を利用しないアプリへのアクセスを禁止する場合、社員や学生にこの制限のことを知らせます。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-122">If you block access to apps that do not use modern authentication, let the employees and students know of this restriction.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="ef3ca-123">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ef3ca-123">Next steps</span></span>

<span data-ttu-id="ef3ca-124">アプリベースの条件付きアクセスを利用し、会社データのセキュリティを強化しました。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-124">You have used app-based conditional access to increase the security of company data.</span></span> <span data-ttu-id="ef3ca-125">次の手順として、会社データの保護機能を上げる他の方法について学習できます。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-125">As part of next steps, you can learn more about the other ways you can increase the protection of your company's data, including:</span></span> 

* <span data-ttu-id="ef3ca-126">[Active Directory や Azure Active Directory でデバイス コンプライアンス、デバイス リスク、場所、ユーザー属性に基づいて条件付きアクセス](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)を設定します。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-126">Setting up [conditional access based on device compliance, device risk, location, and user attributes in Active Directory and Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).</span></span>  
* <span data-ttu-id="ef3ca-127">アプリ保護ポリシーを設定し、意図的な、あるいは意図しないデータ漏洩から会社のデータを守ります。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-127">Setting up app protection policies to help you protect your company data against intentional or unintentional data leaks.</span></span> 
* <span data-ttu-id="ef3ca-128">Azure Information Protection を活用し、ネットワークの外にある会社データを守ります。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-128">Leveraging Azure Information Protection to protect company data outside your network.</span></span> 

<span data-ttu-id="ef3ca-129">EMS または Office 365 のさまざまなシナリオを有効にする支援をご希望ですか?</span><span class="sxs-lookup"><span data-stu-id="ef3ca-129">Want help enabling this or other EMS or Office 365 scenarios?</span></span> <span data-ttu-id="ef3ca-130">Microsoft 365、Enterprise Mobility + Security、または Azure Active Directory Premium のライセンスを 150 以上お持ちでしたら、[FastTrack の特典](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program)をご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="ef3ca-130">If you have at least 150 licenses for Microsoft 365, Enterprise Mobility + Security, or Azure Active Directory Premium, use your [FastTrack benefits](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program).</span></span> 