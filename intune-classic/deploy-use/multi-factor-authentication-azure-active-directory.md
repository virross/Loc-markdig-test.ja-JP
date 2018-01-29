---
title: "Intune へのデバイスの登録での多要素認証"
description: "デバイス登録で Azure AD の多要素認証を要求する方法。"
keywords: 
author: arob98
ms.author: angrobe
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: 940187bf6a7a08132469416a063507f5640b4bd6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a><span data-ttu-id="00bcf-103">Intune へのデバイスの登録での多要素認証</span><span class="sxs-lookup"><span data-stu-id="00bcf-103">Multi-factor authentication for Intune device enrollments</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="00bcf-104">Intune には、デバイス登録用に Azure AD の多要素認証 (MFA) 機能が統合されていて、会社のリソースのセキュリティ保護に利用できます。</span><span class="sxs-lookup"><span data-stu-id="00bcf-104">Intune integrates Azure AD multi-factor authentication (MFA) for device enrollment to help you secure your corporate resources.</span></span>

<span data-ttu-id="00bcf-105">MFA は、次の確認方法のうち 2 つ以上を必須にすることで機能します。</span><span class="sxs-lookup"><span data-stu-id="00bcf-105">MFA works by requiring any two or more of the following verification methods:</span></span> 

- <span data-ttu-id="00bcf-106">ユーザーが知っている情報 (通常はパスワードまたは PIN)。</span><span class="sxs-lookup"><span data-stu-id="00bcf-106">Something you know (typically a password or PIN).</span></span>
- <span data-ttu-id="00bcf-107">ユーザーの所持品 (電話など、容易には複製できない、信頼済みのデバイス)。</span><span class="sxs-lookup"><span data-stu-id="00bcf-107">Something you have (a trusted device that is not easily duplicated, like a phone).</span></span>
- <span data-ttu-id="00bcf-108">ユーザー自身の特性 (生体認証)。</span><span class="sxs-lookup"><span data-stu-id="00bcf-108">Something you are (biometrics).</span></span>

<span data-ttu-id="00bcf-109">MFA は、iOS、Android、Windows 8.1 以上、または Windows Phone 8.1 以上のデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="00bcf-109">MFA is supported for iOS, Android, Windows 8.1 or later, or Windows Phone 8.1 or later devices.</span></span>

> [!NOTE]
> <span data-ttu-id="00bcf-110">以前のバージョンの Configuration Manager (リリース 1610 より前) では、Configuration Manager 管理コンソールに MFA の設定が表示されますが、</span><span class="sxs-lookup"><span data-stu-id="00bcf-110">In older versions of Configuration Manager (earlier than release 1610), you will still see the MFA setting in the Configuration Manager admin console.</span></span> <span data-ttu-id="00bcf-111">Configuration Manager 管理コンソールで MFA を構成しようとしないでください。MFA は機能しません。</span><span class="sxs-lookup"><span data-stu-id="00bcf-111">Do not attempt to configure MFA in the Configuration Manager admin console, as it will not work.</span></span> <span data-ttu-id="00bcf-112">MFA はこのトピックの説明に従って構成してください。</span><span class="sxs-lookup"><span data-stu-id="00bcf-112">Configure MFA as described in this topic.</span></span>

### <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a><span data-ttu-id="00bcf-113">デバイス登録時に多要素認証を要求するように Intune を構成する</span><span class="sxs-lookup"><span data-stu-id="00bcf-113">Configure Intune to require multi-factor authentication at device enrollment</span></span>
<span data-ttu-id="00bcf-114">デバイスの登録時に MFA を要求するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="00bcf-114">To require MFA when a device is enrolled, follow these steps:</span></span>

1. <span data-ttu-id="00bcf-115">管理者資格情報で [Microsoft Azure ポータル](https://manage.windowsazure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="00bcf-115">Sign in to your [Microsoft Azure portal](https://manage.windowsazure.com) with your admin credentials.</span></span>
2. <span data-ttu-id="00bcf-116">テナントを選択します。</span><span class="sxs-lookup"><span data-stu-id="00bcf-116">Choose your tenant.</span></span>
2. <span data-ttu-id="00bcf-117">**[アプリケーション]** タブを選択します。Azure AD のセキュリティ機能を構成できるサービスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00bcf-117">Choose the **applications** tab. You will see a list of services for which you can configure Azure AD security features.</span></span>
3. <span data-ttu-id="00bcf-118">**[Microsoft Intune enrollment (Microsoft Intune 登録)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bcf-118">Choose **Microsoft Intune enrollment**.</span></span>
4. <span data-ttu-id="00bcf-119">**[構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bcf-119">Choose **Configure**.</span></span> 
5. <span data-ttu-id="00bcf-120">**[多要素認証と場所ベースのアクセス規則]** では、次の操作をすることができます。</span><span class="sxs-lookup"><span data-stu-id="00bcf-120">Under **multi-factor authentication and location-based access rules** you can:</span></span>
    
    -  <span data-ttu-id="00bcf-121">アクセス規則の有効化</span><span class="sxs-lookup"><span data-stu-id="00bcf-121">Enable the access rules</span></span>
    -  <span data-ttu-id="00bcf-122">すべてのユーザーまたは特定の Azure セキュリティ グループのどちらに規則を適用するか選択します。</span><span class="sxs-lookup"><span data-stu-id="00bcf-122">Choose whether to apply the rules to all users or to specific Azure AD security groups.</span></span>
    -  <span data-ttu-id="00bcf-123">すべてのデバイスの登録では、多要素認証を要求します。</span><span class="sxs-lookup"><span data-stu-id="00bcf-123">Require multi-factor authentication for enrollment of all devices.</span></span>
    -  <span data-ttu-id="00bcf-124">デバイスが動作していないときの登録では、多要素認証を要求します。</span><span class="sxs-lookup"><span data-stu-id="00bcf-124">Require multi-factor authentication for enrollment when the device is not at work.</span></span>
    -  <span data-ttu-id="00bcf-125">**[Block access to corporate resources (会社のリソースへのアクセスをブロックする)]** を選択して、デバイスが企業ネットワークに接続されていないときはデバイスを登録できないようにします。</span><span class="sxs-lookup"><span data-stu-id="00bcf-125">Choose **Block access to corporate resources** to prevent enrollment of a device when it is not connected to the corporate network.</span></span> 
4. <span data-ttu-id="00bcf-126">**社内ネットワークの場所の定義/編集**へのリンクをクリックして、デバイス登録のネットワーク接続要件を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="00bcf-126">You can also click the link to **define/edit your work network location**, to configure network connectivity requirements for device enrollment.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="00bcf-127">[Microsoft Intune enrollment (Microsoft Intune 登録)] の **[デバイス ベースのアクセス規則]** は構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="00bcf-127">Do not configure **Device based access rules** for Microsoft Intune Enrollment.</span></span>
