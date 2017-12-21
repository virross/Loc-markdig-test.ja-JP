---
title: "Intune を使用した Skycure コネクタ"
titlesuffix: Azure portal
description: "Skycure コネクタを Intune と統合します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47df2c4a909c397ac5a6c0f736d11344de44736e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="skycure-mobile-threat-defense-connector"></a><span data-ttu-id="0f6eb-103">Skycure Mobile Threat Defense コネクター</span><span class="sxs-lookup"><span data-stu-id="0f6eb-103">Skycure Mobile Threat Defense connector</span></span>

<span data-ttu-id="0f6eb-104">Microsoft Intune に統合されたモバイル脅威保護ソリューションである Skycure によって実行されるリスク評価に基づき、条件付きアクセスを利用し、モバイル デバイスから会社のリソースへのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Skycure, a mobile threat defense solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="0f6eb-105">リスクは、Skycure を実行するデバイスから収集される製品利用統計情報に基づいて以下のとおり評価されます。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-105">Risk is assessed based on telemetry collected from devices running Skycure, including:</span></span>

-   <span data-ttu-id="0f6eb-106">物理的防御</span><span class="sxs-lookup"><span data-stu-id="0f6eb-106">Physical defense</span></span>

-   <span data-ttu-id="0f6eb-107">ネットワーク防御</span><span class="sxs-lookup"><span data-stu-id="0f6eb-107">Network defense</span></span>

-   <span data-ttu-id="0f6eb-108">アプリケーション防御</span><span class="sxs-lookup"><span data-stu-id="0f6eb-108">Application defense</span></span>

-   <span data-ttu-id="0f6eb-109">脆弱性防御</span><span class="sxs-lookup"><span data-stu-id="0f6eb-109">Vulnerabilities defense</span></span>

<span data-ttu-id="0f6eb-110">Intune デバイス コンプライアンス ポリシーで有効にした Skycure リスク評価に基づき、条件付きアクセスのポリシーを構成できます。Intune デバイス コンプライアンス ポリシーは、検出された脅威に基づき、非準拠デバイスから企業リソースへのアクセスを許可したり、拒否したりするために利用できます。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-110">You can configure conditional access policies based on Skycure risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a><span data-ttu-id="0f6eb-111">Intune と Skycure を利用し、会社のリソースをどのように保護しますか?</span><span class="sxs-lookup"><span data-stu-id="0f6eb-111">How do Intune and Skycure help protect your company resources?</span></span>

<span data-ttu-id="0f6eb-112">Android または iOS 向け Skycure モバイル アプリは、ファイル システム、ネットワーク スタック、デバイスとアプリケーションの製品利用統計情報を可能な限り記録し、Skycure クラウド サービスに送信し、モバイル デバイスの脅威に対するリスクを評価します。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-112">Skycure mobile app for Android or iOS captures file system, network stack, device and application telemetry where available, then sends it to the Skycure cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="0f6eb-113">Intune デバイス コンプライアンス ポリシーには、Skycure リスク評価に基づく、Skycure Mobile Threat Defense のルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-113">The Intune device compliance policy includes a rule for Skycure Mobile Threat Defense, which is based on the Skycure risk assessment.</span></span> <span data-ttu-id="0f6eb-114">このルールを有効にすると、Intune は、有効にされたポリシーに基づいてデバイスの準拠状態を評価します。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-114">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="0f6eb-115">デバイスが準拠していないことが判明した場合、Exchange Online や SharePoint Online などのリソースに対するアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-115">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online are blocked.</span></span> <span data-ttu-id="0f6eb-116">デバイスがブロックされたユーザーには Skycure モバイル アプリから手引きが届きます。それを見て問題を解決し、企業リソースへのアクセスを回復できます。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-116">Users on blocked devices receive guidance from the Skycure mobile app to resolve the issue and regain access to corporate resources.</span></span>

<span data-ttu-id="0f6eb-117">Intune では、Skycure との統合に 2 つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-117">Intune supports two modes of integration with Skycure:</span></span>

-   <span data-ttu-id="0f6eb-118">**基本セットアップ**は読み取り専用モードであり、Skycure は Intune のデバイスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-118">**Basic setup** which is a read only mode that allows Skycure visibility for devices in Intune.</span></span>

-   <span data-ttu-id="0f6eb-119">**完全統合**の場合、Skycure から、デバイスのリスクとセキュリティ インシデントの詳細を Intune に報告できます。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-119">**Full integration** which allows Skycure to report device risk and security incident details to Intune.</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="0f6eb-120">サンプル事例</span><span class="sxs-lookup"><span data-stu-id="0f6eb-120">Sample scenarios</span></span>

<span data-ttu-id="0f6eb-121">一般的なシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-121">Here are some common scenarios:</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="0f6eb-122">悪意のあるアプリの脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="0f6eb-122">Control access based on threats from malicious apps</span></span>

<span data-ttu-id="0f6eb-123">マルウェアなどの悪意のあるアプリがデバイスで検出されると、脅威が解決されるまで、デバイスで次の行為が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-123">When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:</span></span>

-   <span data-ttu-id="0f6eb-124">会社の電子メールに接続する</span><span class="sxs-lookup"><span data-stu-id="0f6eb-124">Connecting to corporate e-mail</span></span>

-   <span data-ttu-id="0f6eb-125">OneDrive for Work アプリを使用して会社のファイルを同期する</span><span class="sxs-lookup"><span data-stu-id="0f6eb-125">Syncing corporate files with the OneDrive for Work app</span></span>

-   <span data-ttu-id="0f6eb-126">会社のアプリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="0f6eb-126">Accessing company apps</span></span>

<span data-ttu-id="0f6eb-127">**悪意のあるアプリが検出されたときにブロックする:**</span><span class="sxs-lookup"><span data-stu-id="0f6eb-127">**Block when malicious apps are detected:**</span></span>

![検出された悪意のあるアプリ](./media/skycure-arch-1.png)

<span data-ttu-id="0f6eb-129">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="0f6eb-129">**Access granted on remediation:**</span></span>

![悪意のあるアプリの検出、アクセス権](./media/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="0f6eb-131">ネットワークに対する脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="0f6eb-131">Control access based on threat to network</span></span>

<span data-ttu-id="0f6eb-132">ネットワークで **Man-in-the-middle** のような脅威を検出し、デバイスのリスクに基づいて Wi-Fi ネットワークへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-132">Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.</span></span>

<span data-ttu-id="0f6eb-133">**Wi-Fi 経由のネットワーク アクセスをブロックする:**</span><span class="sxs-lookup"><span data-stu-id="0f6eb-133">**Block network access through Wi-Fi:**</span></span>

![Wi-Fi 経由のネットワーク アクセスをブロックする](./media/skycure-arch-3.png)

<span data-ttu-id="0f6eb-135">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="0f6eb-135">**Access granted on remediation:**</span></span>

![修復するとアクセス権が付与される](./media/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="0f6eb-137">ネットワークに対する脅威に基づいて SharePoint Online へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="0f6eb-137">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="0f6eb-138">ネットワークで **Man-in-the-middle** のような脅威を検出し、デバイスのリスクに基づいて会社内のファイルの同期を阻止します。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-138">Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="0f6eb-139">**ネットワークの脅威が検出されたときに SharePoint Online をブロック:**</span><span class="sxs-lookup"><span data-stu-id="0f6eb-139">**Block SharePoint Online when network threats are detected:**</span></span>

![ネットワークの脅威が検出されたときに SharePoint Online をブロック](./media/skycure-arch-5.png)

<span data-ttu-id="0f6eb-141">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="0f6eb-141">**Access granted on remediation:**</span></span>

![SharePoint で修復時にアクセス権を付与する例](./media/skycure-arch-6.png)

## <a name="supported-platforms"></a><span data-ttu-id="0f6eb-143">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="0f6eb-143">Supported platforms</span></span>

-   <span data-ttu-id="0f6eb-144">**Android 4.1 以降**</span><span class="sxs-lookup"><span data-stu-id="0f6eb-144">**Android 4.1 and later**</span></span>

-   <span data-ttu-id="0f6eb-145">**iOS 8 以降**</span><span class="sxs-lookup"><span data-stu-id="0f6eb-145">**iOS 8 and later**</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="0f6eb-146">前提条件</span><span class="sxs-lookup"><span data-stu-id="0f6eb-146">Pre-requisites</span></span>

-   <span data-ttu-id="0f6eb-147">Azure Active Directory Premium</span><span class="sxs-lookup"><span data-stu-id="0f6eb-147">Azure Active Directory Premium</span></span>

-   <span data-ttu-id="0f6eb-148">Microsoft Intune サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="0f6eb-148">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="0f6eb-149">Skycure Mobile Threat Defense サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="0f6eb-149">Skycure Mobile Threat Defense subscription</span></span>

<span data-ttu-id="0f6eb-150">詳細については、[Skycure Web サイト](https://www.skycure.com/skycure-microsoft-integration/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-150">For more information, check [Skycure website](https://www.skycure.com/skycure-microsoft-integration/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f6eb-151">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0f6eb-151">Next steps</span></span>

<span data-ttu-id="0f6eb-152">Intune と Skycure の統合は次の手順で行います。</span><span class="sxs-lookup"><span data-stu-id="0f6eb-152">Here are the steps you need to complete to integrate Intune with Skycure:</span></span>

- [<span data-ttu-id="0f6eb-153">Skycure と Intune の統合をセットアップする</span><span class="sxs-lookup"><span data-stu-id="0f6eb-153">Set up Skycure integration with Intune</span></span>](skycure-mtd-connector-integration.md)

- [<span data-ttu-id="0f6eb-154">Skycure アプリ、Microsoft Authenticator、iOS アプリ構成ポリシーを追加して割り当てる</span><span class="sxs-lookup"><span data-stu-id="0f6eb-154">Add and assign Skycure apps, Microsoft Authenticator and iOS app configuration policy</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [<span data-ttu-id="0f6eb-155">Intune で Skycure デバイスのコンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0f6eb-155">Create Skycure device compliance policy with Intune</span></span>](mtd-device-compliance-policy-create.md)

- [<span data-ttu-id="0f6eb-156">Intune で Skycure MTD コネクタを有効にする</span><span class="sxs-lookup"><span data-stu-id="0f6eb-156">Enable Skycure MTD connector in Intune</span></span>](mtd-connector-enable.md)
