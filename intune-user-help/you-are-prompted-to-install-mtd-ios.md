---
title: "iOS デバイスで Mobile Threat Defense をインストールする必要がある | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5b9ee20b-3c4e-4461-86d3-6fd26e7f71a6
searchScope:
- User help
ROBOTS: 
ms.custom: intune-enduser
ms.openlocfilehash: d7943b42289aea984bb0366acc71282f7daccc89
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="install-mobile-threat-defense-on-your-ios-device"></a><span data-ttu-id="80512-102">iOS デバイスに Mobile Threat Defense をインストールする</span><span class="sxs-lookup"><span data-stu-id="80512-102">Install Mobile Threat Defense on your iOS device</span></span>


<span data-ttu-id="80512-103">作業内容にアクセスする前に、会社のサポートから潜在的なセキュリティ脅威を検出してデバイスを保護することができる、Mobile Threat Defense アプリをインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="80512-103">Before you can access your work, your company needs you to install the Mobile Threat Defense app, which helps to protect your device by finding potential security threats.</span></span> <span data-ttu-id="80512-104">IT 管理者の設定によって、デバイスで表示されるプロンプトは異なります。</span><span class="sxs-lookup"><span data-stu-id="80512-104">You might see different prompts on your device, depending on how your IT admin set it up.</span></span>


* [<span data-ttu-id="80512-105">Lookout for Work</span><span class="sxs-lookup"><span data-stu-id="80512-105">Lookout for Work</span></span>](you-are-prompted-to-install-lookout-for-work-ios.md)
* [<span data-ttu-id="80512-106">Symantec Endpoint Protection Mobile</span><span class="sxs-lookup"><span data-stu-id="80512-106">Symantec Endpoint Protection Mobile</span></span>](you-are-prompted-to-install-skycure-ios.md)
* [<span data-ttu-id="80512-107">SandBlast Mobile Protect</span><span class="sxs-lookup"><span data-stu-id="80512-107">SandBlast Mobile Protect</span></span>](you-are-prompted-to-install-sandblast-ios.md)
* [<span data-ttu-id="80512-108">Zimperium zIPS</span><span class="sxs-lookup"><span data-stu-id="80512-108">Zimperium zIPS</span></span>](you-are-prompted-to-install-zips-ios.md)

## <a name="additional-information-your-company-can-see"></a><span data-ttu-id="80512-109">会社が見ることのできる追加情報</span><span class="sxs-lookup"><span data-stu-id="80512-109">Additional information your company can see</span></span>

<span data-ttu-id="80512-110">Mobile Threat Defense は、企業の情報を盗もうとするアプリからデバイスを保護する手段です。</span><span class="sxs-lookup"><span data-stu-id="80512-110">Mobile Threat Defense is a way for companies to make sure that your devices are kept safe from apps that could be trying to steal corporate information.</span></span> <span data-ttu-id="80512-111">この保護を追加するには、デバイスで会社が使っているアプリに関する追加情報を Mobile Threat Defense サービスに報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80512-111">Adding this protection requires extra information to be reported about the apps on your devices to the Mobile Threat Defense service that your company is using.</span></span> <span data-ttu-id="80512-112">会社は、ユーザーの個人用アプリのデータを見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="80512-112">Your company can't see the data in your personal apps.</span></span> <span data-ttu-id="80512-113">Mobile Threat Defense サービスを使用すると、デバイス上のすべてのアプリが[会社が確認できる情報](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)に追加されます。</span><span class="sxs-lookup"><span data-stu-id="80512-113">All of the apps on your device are added to [what your company can see](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) when they use a Mobile Threat Defense service.</span></span> <span data-ttu-id="80512-114">会社が確認できるアプリの部分を次に示します。</span><span class="sxs-lookup"><span data-stu-id="80512-114">These are the parts of the app that your company can see:</span></span>

*   <span data-ttu-id="80512-115">アプリ名</span><span class="sxs-lookup"><span data-stu-id="80512-115">App name</span></span>
* <span data-ttu-id="80512-116">アプリ ID: アプリ ストアでアプリを示す一意名</span><span class="sxs-lookup"><span data-stu-id="80512-116">App ID: the unique name that identifies the app in the App Store</span></span>
*   <span data-ttu-id="80512-117">アプリのバージョンと短いバージョン番号: アプリの特定のリリース番号</span><span class="sxs-lookup"><span data-stu-id="80512-117">App version and short version number: the specific release numbers for an app</span></span>
* <span data-ttu-id="80512-118">アプリのバンドルと動的なサイズ: デバイスでのアプリの使用領域</span><span class="sxs-lookup"><span data-stu-id="80512-118">App bundle and dynamic size: the amount of space an app uses on your device</span></span>
* <span data-ttu-id="80512-119">アプリの有効性: アプリの使用が承認されているかどうか</span><span class="sxs-lookup"><span data-stu-id="80512-119">App validity: whether an app is approved for use</span></span>
*   <span data-ttu-id="80512-120">アプリの管理状態: アプリが会社によって管理されているか、または個人用アプリか</span><span class="sxs-lookup"><span data-stu-id="80512-120">App management state: whether an app is managed by your company or if it is a personal app</span></span>

## <a name="if-the-installation-doesnt-work"></a><span data-ttu-id="80512-121">インストールが機能しない場合</span><span class="sxs-lookup"><span data-stu-id="80512-121">If the installation doesn't work</span></span>

<span data-ttu-id="80512-122">ユーザーが制御できない技術的な問題によりインストールが失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="80512-122">Sometimes installations can fail due to technical issues beyond your control.</span></span> <span data-ttu-id="80512-123">このようなことが起こる場合、社内サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="80512-123">If this happens, contact your company support.</span></span> <span data-ttu-id="80512-124">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="80512-124">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
