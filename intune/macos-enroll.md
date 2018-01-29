---
title: "Intune で macOS デバイスを登録する"
titlesuffix: Azure portal
description: "Intune で macOS デバイスを登録する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cae0244864420c57d2348dd127a3593a1d1c9ad4
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="enroll-macos-devices-in-intune"></a><span data-ttu-id="1a887-103">Intune で macOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="1a887-103">Enroll macOS devices in Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1a887-104">Intune では、macOS デバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="1a887-104">Intune enables you to manage macOS devices.</span></span> <span data-ttu-id="1a887-105">デバイスの管理を有効にするには、[ポータル Web サイト](http://portal.manage.microsoft.com)に移動し、画面の指示に従ってデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a887-105">To enable device management, your users must enroll their devices by going to the [Company Portal website](http://portal.manage.microsoft.com), and following the prompts.</span></span> <span data-ttu-id="1a887-106">macOS デバイスを管理下に置いたら、[macOS デバイスのカスタム設定を作成](custom-settings-macos.md)できます。</span><span class="sxs-lookup"><span data-stu-id="1a887-106">Once macOS devices are under management, you can [create custom settings for macOS devices](custom-settings-macos.md).</span></span> <span data-ttu-id="1a887-107">その他の機能は近日公開予定です。</span><span class="sxs-lookup"><span data-stu-id="1a887-107">More capabilities are coming soon.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1a887-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="1a887-108">Prerequisites</span></span>

<span data-ttu-id="1a887-109">macOS デバイスの登録を設定する前に、以下の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a887-109">Complete the following prerequisites before setting up macOS device enrollment:</span></span>

- [<span data-ttu-id="1a887-110">ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="1a887-110">Configure domains</span></span>](custom-domain-name-configure.md)
- [<span data-ttu-id="1a887-111">MDM 機関を設定する</span><span class="sxs-lookup"><span data-stu-id="1a887-111">Set the MDM Authority</span></span>](mdm-authority-set.md)
- [<span data-ttu-id="1a887-112">グループの作成</span><span class="sxs-lookup"><span data-stu-id="1a887-112">Create groups</span></span>](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [<span data-ttu-id="1a887-113">ポータル サイト アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="1a887-113">Configure the Company Portal</span></span>](company-portal-app.md)
- <span data-ttu-id="1a887-114">[Office 365 ポータル](http://go.microsoft.com/fwlink/p/?LinkId=698854)でユーザー ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1a887-114">Assign user licenses in the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)</span></span>
- [<span data-ttu-id="1a887-115">Apple MDM プッシュ証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="1a887-115">Get an Apple MDM push certificate</span></span>](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a><span data-ttu-id="1a887-116">macOS の登録を設定する</span><span class="sxs-lookup"><span data-stu-id="1a887-116">Set up macOS enrollment</span></span>

<span data-ttu-id="1a887-117">Intune では、既定で macOS デバイスの登録が既に許可されています。</span><span class="sxs-lookup"><span data-stu-id="1a887-117">By default, Intune already allows enrollment of macOS devices.</span></span>

<span data-ttu-id="1a887-118">macOS デバイスの登録をブロックする場合は、「[Set device type restrictions](enrollment-restrictions-set.md)」 (デバイスの種類の制限を設定する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a887-118">To block macOS devices from enrollment, see [Set device type restrictions](enrollment-restrictions-set.md).</span></span>

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a><span data-ttu-id="1a887-119">デバイスを登録して会社のリソースにアクセスする方法をユーザーに知らせる</span><span class="sxs-lookup"><span data-stu-id="1a887-119">Tell your users how to enroll their devices to access company resources</span></span>

<span data-ttu-id="1a887-120">エンド ユーザーに対して、[ポータル Web サイト](http://portal.manage.microsoft.com)に移動し、画面の指示に従ってデバイスを登録するように指示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a887-120">You'll need to tell your end users to go to the [Company Portal website](http://portal.manage.microsoft.com), and follow the prompts to enroll their devices.</span></span> <span data-ttu-id="1a887-121">オンライン登録の手順 (「[Intune に macOS デバイスを登録する](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)」) へのリンクを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a887-121">You can also send them a link to online enrollment steps: [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span></span>

<span data-ttu-id="1a887-122">その他のエンドユーザー タスクの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a887-122">For information about other end-user tasks, see these articles:</span></span>

- [<span data-ttu-id="1a887-123">Microsoft Intune を使用したエンドユーザー エクスペリエンスに関するリソース</span><span class="sxs-lookup"><span data-stu-id="1a887-123">Resources about the end-user experience with Microsoft Intune</span></span>](end-user-educate.md)
- [<span data-ttu-id="1a887-124">iOS デバイスまたは macOS デバイスを Intune で使用する</span><span class="sxs-lookup"><span data-stu-id="1a887-124">Using your iOS or macOS device with Intune</span></span>](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)
