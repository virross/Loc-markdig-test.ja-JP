---
title: "Intune 用アプリ構成ポリシー | Microsoft Docs"
titlesuffix: Azure portal
description: "Intune 用アプリ構成ポリシーを使用する方法について説明します。"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 727bf031a9e8a4c761d8d7b0c1d2737398a0fb7e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="app-configuration-policies-for-intune"></a><span data-ttu-id="9b4eb-103">Intune 用アプリ構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="9b4eb-103">App configuration policies for Intune</span></span>

<span data-ttu-id="9b4eb-104">ユーザーが Microsoft Intune でアプリ構成ポリシーと共に iOS または Android アプリを実行するときの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-104">Supply settings when users run an iOS or Android app with app configuration policies in Microsoft Intune.</span></span> <span data-ttu-id="9b4eb-105">たとえば、アプリは次の内容を指定することをユーザーに要求することがあります。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-105">For example, an app might require users to specify:</span></span>

- <span data-ttu-id="9b4eb-106">カスタム ポート番号。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-106">A custom port number.</span></span>
- <span data-ttu-id="9b4eb-107">言語設定。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-107">Language settings.</span></span>
- <span data-ttu-id="9b4eb-108">セキュリティ設定。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-108">Security settings.</span></span>
- <span data-ttu-id="9b4eb-109">会社のロゴなどのブランドの設定。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-109">Branding settings such as a company logo.</span></span>

<span data-ttu-id="9b4eb-110">ユーザーがこれらの設定を誤って入力すると、ヘルプ デスクの負荷が増加し、新しいアプリの採用が遅くなる可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-110">If users enter these settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="9b4eb-111">アプリ構成ポリシーを使用すると、ユーザーがアプリを実行する前にこれらの設定をポリシー内のユーザーに割り当てることができるため、上記の問題を排除するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-111">App configuration policies can help you eliminate these problems by letting you assign these settings to users in a policy before they run the app.</span></span> <span data-ttu-id="9b4eb-112">設定が自動的に指定されるため、ユーザーの操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-112">The settings are then supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="9b4eb-113">これらのポリシーをユーザーとデバイスに直接割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-113">You do not assign these policies directly to users and devices.</span></span> <span data-ttu-id="9b4eb-114">代わりに、ポリシーをアプリに関連付け、そのアプリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-114">Instead, you associate a policy with an app, and then assign the app.</span></span> <span data-ttu-id="9b4eb-115">ポリシー設定は、アプリがポリシーを確認する際に (通常は初めて実行したときに) 必ず使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-115">The policy settings are used whenever the app checks for them (typically, the first time it is run).</span></span>

<span data-ttu-id="9b4eb-116">Intune でアプリ構成を使用する方法には 2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-116">You have two options for how to use app configurations with Intune:</span></span>
 - <span data-ttu-id="9b4eb-117">**管理対象デバイス**</span><span class="sxs-lookup"><span data-stu-id="9b4eb-117">**Managed devices**</span></span>  
   <span data-ttu-id="9b4eb-118">デバイスは、Intune で MDM (モバイル デバイス管理) プロバイダーとして管理されます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-118">The device is managed by Intune as the mobile device management (MDM) provider.</span></span>
 - <span data-ttu-id="9b4eb-119">**管理対象アプリ**</span><span class="sxs-lookup"><span data-stu-id="9b4eb-119">**Managed apps**</span></span>  
   <span data-ttu-id="9b4eb-120">アプリはデバイスの登録なしで管理されます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-120">An app is managed without device enrollment.</span></span>

## <a name="apps-that-support-app-configuration"></a><span data-ttu-id="9b4eb-121">アプリ構成をサポートするアプリ</span><span class="sxs-lookup"><span data-stu-id="9b4eb-121">Apps that support app configuration</span></span>

<span data-ttu-id="9b4eb-122">サポートするアプリにアプリ構成ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-122">You can use app configuration polices for apps that support it.</span></span> <span data-ttu-id="9b4eb-123">Intune でアプリ構成をサポートするには、アプリ構成の使用をサポートするようにアプリが記述されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-123">To support app configuration in Intune, apps must have been written to support the use of app configurations.</span></span> <span data-ttu-id="9b4eb-124">詳細については、アプリのベンダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-124">Consult your app vendor for details.</span></span>

<span data-ttu-id="9b4eb-125">Intune App SDK をアプリに組み込むか、アプリの開発後にラップして、基幹業務アプリを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-125">You can prepare your line-of-business apps by either incorporating the Intune App SDK into the app, or wrapping the app after it is developed.</span></span> <span data-ttu-id="9b4eb-126">iOS と Android の両方で使用可能な Intune App SDK で、Intune アプリ保護ポリシーに対してご使用のアプリを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-126">The Intune App SDK, available for both iOS and Android, enables your app for Intune app protection policies.</span></span> <span data-ttu-id="9b4eb-127">アプリの開発者が必要なコード変更が最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-127">It strives to minimize the amount of code changes required from the app developer.</span></span> <span data-ttu-id="9b4eb-128">詳細については、「[Intune App SDK の概要](app-sdk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-128">For more information, see the [Intune App SDK overview](app-sdk.md).</span></span>

## <a name="graph-api-support-for-app-configuration"></a><span data-ttu-id="9b4eb-129">Graph API のアプリ構成のサポート</span><span class="sxs-lookup"><span data-stu-id="9b4eb-129">Graph API support for app configuration</span></span>

<span data-ttu-id="9b4eb-130">アプリ構成タスクは、Graph API でも実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-130">Additionally, you can use Graph API to accomplish app configuration tasks.</span></span> <span data-ttu-id="9b4eb-131">詳細については、[Graph API のリファレンスの MAM を対象とした構成](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-131">For details, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9b4eb-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="9b4eb-132">Next steps</span></span>

### <a name="managed-devices"></a><span data-ttu-id="9b4eb-133">管理対象デバイス</span><span class="sxs-lookup"><span data-stu-id="9b4eb-133">Managed devices</span></span>

 - <span data-ttu-id="9b4eb-134">iOS デバイスでアプリ構成を使用する方法について学びます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-134">Learn how to use app configuration with your iOS devices.</span></span>  <span data-ttu-id="9b4eb-135">「[管理対象の iOS デバイス用アプリ構成ポリシーを追加する](app-configuration-policies-use-ios.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-135">See [ Add app configuration policies for managed iOS devices](app-configuration-policies-use-ios.md).</span></span>
 - <span data-ttu-id="9b4eb-136">Android デバイスにアプリ構成を使用する方法について学びます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-136">Learn how to use app configuration with your Android devices.</span></span>  <span data-ttu-id="9b4eb-137">「[管理対象の Android デバイス用アプリ構成ポリシーを追加する](app-configuration-policies-use-android.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-137">See [Add app configuration policies for managed Android devices](app-configuration-policies-use-android.md).</span></span>

### <a name="managed-apps"></a><span data-ttu-id="9b4eb-138">Managed apps</span><span class="sxs-lookup"><span data-stu-id="9b4eb-138">Managed apps</span></span>

 - <span data-ttu-id="9b4eb-139">管理対象アプリにアプリ構成を使用する方法について学びます。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-139">Learn how to use app configuration with managed apps.</span></span> <span data-ttu-id="9b4eb-140">「[デバイス登録なしで管理対象アプリ用アプリ構成ポリシーを追加する](app-configuration-policies-managed-app.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4eb-140">See [Add app configuration policies for managed apps without device enrollment](app-configuration-policies-managed-app.md).</span></span>