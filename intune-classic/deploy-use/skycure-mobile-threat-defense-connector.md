---
title: "Skycure Mobile Threat Defense コネクター"
description: "Skycure Mobile Threat Defense コネクターと Intune を使用して、デバイス、ネットワーク、アプリケーションのリスクを基にして会社のリソースへのアクセスを保護します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3b77cc3ffd2c5f0ce5d9fc5f57e64a7c69ce130d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="skycure-mobile-threat-defense-connector"></a><span data-ttu-id="1b680-103">Skycure Mobile Threat Defense コネクター</span><span class="sxs-lookup"><span data-stu-id="1b680-103">Skycure Mobile Threat Defense connector</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1b680-104">Microsoft Intune に統合されたモバイル脅威保護ソリューションである Skycure によって実行されるリスク評価に基づき、条件付きアクセスを利用し、モバイル デバイスから会社のリソースへのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="1b680-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Skycure, a mobile threat defense solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="1b680-105">リスクは、Skycure を実行するデバイスから収集される製品利用統計情報に基づいて以下のとおり評価されます。</span><span class="sxs-lookup"><span data-stu-id="1b680-105">Risk is assessed based on telemetry collected from devices running Skycure, including:</span></span>

-   <span data-ttu-id="1b680-106">物理的防御</span><span class="sxs-lookup"><span data-stu-id="1b680-106">Physical defense</span></span>

-   <span data-ttu-id="1b680-107">ネットワーク防御</span><span class="sxs-lookup"><span data-stu-id="1b680-107">Network defense</span></span>

-   <span data-ttu-id="1b680-108">アプリケーション防御</span><span class="sxs-lookup"><span data-stu-id="1b680-108">Application defense</span></span>

-   <span data-ttu-id="1b680-109">脆弱性防御</span><span class="sxs-lookup"><span data-stu-id="1b680-109">Vulnerabilities defense</span></span>

<span data-ttu-id="1b680-110">Intune デバイス コンプライアンス ポリシーで有効にした Skycure リスク評価に基づき、条件付きアクセスのポリシーを構成できます。Intune デバイス コンプライアンス ポリシーは、検出された脅威に基づき、非準拠デバイスから企業リソースへのアクセスを許可したり、拒否したりするために利用できます。</span><span class="sxs-lookup"><span data-stu-id="1b680-110">You can configure conditional access policies based on Skycure risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a><span data-ttu-id="1b680-111">Intune と Skycure を利用し、会社のリソースをどのように保護しますか?</span><span class="sxs-lookup"><span data-stu-id="1b680-111">How do Intune and Skycure help protect your company resources?</span></span>

<span data-ttu-id="1b680-112">Android または iOS 向け Skycure モバイル アプリは、ファイル システム、ネットワーク スタック、デバイスとアプリケーションの製品利用統計情報を可能な限り記録し、Skycure クラウド サービスに送信し、モバイル デバイスの脅威に対するリスクを評価します。</span><span class="sxs-lookup"><span data-stu-id="1b680-112">Skycure mobile app for Android or iOS captures file system, network stack, device and application telemetry where available, then sends it to the Skycure cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="1b680-113">Intune デバイス コンプライアンス ポリシーには、Skycure リスク評価に基づく、Skycure モバイル脅威防御のルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b680-113">The Intune device compliance policy includes a rule for Skycure mobile threat defense, which is based on the Skycure risk assessment.</span></span> <span data-ttu-id="1b680-114">このルールを有効にすると、Intune は、有効にされたポリシーに基づいてデバイスの準拠状態を評価します。</span><span class="sxs-lookup"><span data-stu-id="1b680-114">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="1b680-115">デバイスが準拠していないことが判明した場合、Exchange Online や SharePoint Online などのリソースに対するアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1b680-115">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online are blocked.</span></span> <span data-ttu-id="1b680-116">デバイスがブロックされたユーザーには Skycure モバイル アプリから手引きが届きます。それを見て問題を解決し、企業リソースへのアクセスを回復できます。</span><span class="sxs-lookup"><span data-stu-id="1b680-116">Users on blocked devices receive guidance from the Skycure mobile app to resolve the issue and regain access to corporate resources.</span></span>

<span data-ttu-id="1b680-117">Intune では、Skycure との統合に 2 つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="1b680-117">Intune supports two modes of integration with Skycure:</span></span>

-   <span data-ttu-id="1b680-118">**基本セットアップ**は読み取り専用モードであり、Skycure は Intune のデバイスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1b680-118">**Basic setup** which is a read only mode that allows Skycure visibility for devices in Intune.</span></span>

-   <span data-ttu-id="1b680-119">**完全統合**の場合、Skycure から、デバイスのリスクとセキュリティ インシデントの詳細を Intune に報告できます。</span><span class="sxs-lookup"><span data-stu-id="1b680-119">**Full integration** which allows Skycure to report device risk and security incident details to Intune.</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="1b680-120">サンプル事例</span><span class="sxs-lookup"><span data-stu-id="1b680-120">Sample scenarios</span></span>

<span data-ttu-id="1b680-121">一般的なシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1b680-121">Here are some common scenarios:</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="1b680-122">悪意のあるアプリの脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="1b680-122">Control access based on threats from malicious apps</span></span>

<span data-ttu-id="1b680-123">マルウェアなどの悪意のあるアプリがデバイスで検出されると、脅威が解決されるまで、デバイスで次の行為が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="1b680-123">When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:</span></span>

-   <span data-ttu-id="1b680-124">会社の電子メールに接続する</span><span class="sxs-lookup"><span data-stu-id="1b680-124">Connecting to corporate e-mail</span></span>

-   <span data-ttu-id="1b680-125">OneDrive for Work アプリを使用して会社のファイルを同期する</span><span class="sxs-lookup"><span data-stu-id="1b680-125">Syncing corporate files with the OneDrive for Work app</span></span>

-   <span data-ttu-id="1b680-126">会社のアプリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="1b680-126">Accessing company apps</span></span>

<span data-ttu-id="1b680-127">**悪意のあるアプリが検出されたときにブロックする:**</span><span class="sxs-lookup"><span data-stu-id="1b680-127">**Block when malicious apps are detected:**</span></span>

![検出された悪意のあるアプリ](../media/mtp/skycure-arch-1.png)

<span data-ttu-id="1b680-129">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="1b680-129">**Access granted on remediation:**</span></span>

![悪意のあるアプリの検出、アクセス権](../media/mtp/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="1b680-131">ネットワークに対する脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="1b680-131">Control access based on threat to network</span></span>

<span data-ttu-id="1b680-132">ネットワークで **Man-in-the-middle** のような脅威を検出し、デバイスのリスクに基づいて Wi-Fi ネットワークへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="1b680-132">Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.</span></span>

<span data-ttu-id="1b680-133">**Wi-Fi 経由のネットワーク アクセスをブロックする:**</span><span class="sxs-lookup"><span data-stu-id="1b680-133">**Block network access through Wi-Fi:**</span></span>

![Wi-Fi 経由のネットワーク アクセスをブロックする](../media/mtp/skycure-arch-3.png)

<span data-ttu-id="1b680-135">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="1b680-135">**Access granted on remediation:**</span></span>

![修復するとアクセス権が付与される](../media/mtp/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="1b680-137">ネットワークに対する脅威に基づいて SharePoint Online へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="1b680-137">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="1b680-138">ネットワークで **Man-in-the-middle** のような脅威を検出し、デバイスのリスクに基づいて会社内のファイルの同期を阻止します。</span><span class="sxs-lookup"><span data-stu-id="1b680-138">Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="1b680-139">**ネットワークの脅威が検出されたときに SharePoint Online をブロック:**</span><span class="sxs-lookup"><span data-stu-id="1b680-139">**Block SharePoint Online when network threats are detected:**</span></span>

![ネットワークの脅威が検出されたときに SharePoint Online をブロック](../media/mtp/skycure-arch-5.png)

<span data-ttu-id="1b680-141">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="1b680-141">**Access granted on remediation:**</span></span>

![SharePoint で修復時にアクセス権を付与する例](../media/mtp/skycure-arch-6.png)

## <a name="supported-platforms"></a><span data-ttu-id="1b680-143">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="1b680-143">Supported platforms</span></span>

-   <span data-ttu-id="1b680-144">**Android 4.1 以降**</span><span class="sxs-lookup"><span data-stu-id="1b680-144">**Android 4.1 and later**</span></span>

-   <span data-ttu-id="1b680-145">**iOS 8 以降**</span><span class="sxs-lookup"><span data-stu-id="1b680-145">**iOS 8 and later**</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="1b680-146">前提条件</span><span class="sxs-lookup"><span data-stu-id="1b680-146">Pre-requisites</span></span>

-   <span data-ttu-id="1b680-147">Azure Active Directory Premium</span><span class="sxs-lookup"><span data-stu-id="1b680-147">Azure Active Directory Premium</span></span>

-   <span data-ttu-id="1b680-148">Microsoft Intune サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="1b680-148">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="1b680-149">Skycure Mobile Threat Defense サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="1b680-149">Skycure Mobile Threat Defense subscription</span></span>

<span data-ttu-id="1b680-150">詳細については、[Skycure Web サイト](https://www.skycure.com/skycure-microsoft-integration/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b680-150">For more information, check [Skycure website](https://www.skycure.com/skycure-microsoft-integration/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1b680-151">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1b680-151">Next steps</span></span>

<span data-ttu-id="1b680-152">Intune と Skycure の統合は次の手順で行います。</span><span class="sxs-lookup"><span data-stu-id="1b680-152">Here are the steps you need to complete to integrate Intune with Skycure:</span></span>

1.  [<span data-ttu-id="1b680-153">Azure Active Directory シングル サインオン (SSO) を使用するように Skycure を構成する</span><span class="sxs-lookup"><span data-stu-id="1b680-153">Configure Skycure to use Azure Active Directory Single Sign On (SS)</span></span>](/intune-classic/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [<span data-ttu-id="1b680-154">Skycure iOS アプリ構成ポリシーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="1b680-154">Download Skycure iOS app configuration policy</span></span>](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [<span data-ttu-id="1b680-155">Skycure アプリ、Microsoft Authenticator、iOS アプリ構成ポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="1b680-155">Add Skycure apps, Microsoft Authenticator and iOS app configuration policy</span></span>](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [<span data-ttu-id="1b680-156">Skycure アプリ、Microsoft Authenticator、iOS アプリ構成ポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="1b680-156">Deploy Skycure apps, Microsoft Authenticator and iOS app configuration policy</span></span>](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [<span data-ttu-id="1b680-157">Skycure と Intune の統合をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1b680-157">Set up Skycure integration with Intune</span></span>](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [<span data-ttu-id="1b680-158">Intune で Skycure Mobile Threat Defense を有効にする</span><span class="sxs-lookup"><span data-stu-id="1b680-158">Enable Skycure Mobile Threat Defense in Intune</span></span>](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [<span data-ttu-id="1b680-159">Intune で Skycure Mobile Threat Defense コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1b680-159">Create Skycure Mobile Threat Defense compliance policy in Intune</span></span>](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
