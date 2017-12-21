---
title: "Intune を使用した Zimperium MTD コネクタ"
titleSuffix: Intune on Azure
description: "Zimperium コネクタと Intune の統合"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 78214293a66784d4bc05e441c2c1cdbf718b0a9a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a><span data-ttu-id="d98cf-103">Zimperium Mobile Threat Defense コネクタと Intune</span><span class="sxs-lookup"><span data-stu-id="d98cf-103">Zimperium Mobile Threat Defense connector with Intune</span></span>

<span data-ttu-id="d98cf-104">Microsoft Intune に統合された Mobile Threat Defense (MTD) ソリューションである Zimperium によって実行されるリスク評価に基づき、条件付きアクセスを利用し、モバイル デバイスから会社のリソースへのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d98cf-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Zimperium, a Mobile Threat Defense (MTD) solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="d98cf-105">リスクは、Zimperium アプリを実行するデバイスから収集される製品利用統計情報に基づいて評価されます。</span><span class="sxs-lookup"><span data-stu-id="d98cf-105">Risk is assessed based on telemetry collected from devices running the Zimperium app.</span></span>

<span data-ttu-id="d98cf-106">Intune デバイス コンプライアンス ポリシーで有効にした Zimperium リスク評価に基づき、条件付きアクセスのポリシーを構成できます。Intune デバイス コンプライアンス ポリシーは、検出された脅威に基づき、非準拠デバイスから企業リソースへのアクセスを許可したり、拒否したりするために利用できます。</span><span class="sxs-lookup"><span data-stu-id="d98cf-106">You can configure conditional access policies based on Zimperium risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a><span data-ttu-id="d98cf-107">Intune と Zimperium を利用し、会社のリソースをどのように保護しますか?</span><span class="sxs-lookup"><span data-stu-id="d98cf-107">How do Intune and Zimperium help protect your company resources?</span></span>

<span data-ttu-id="d98cf-108">Android および iOS 向け Zimperium アプリは、ファイル システム、ネットワーク スタック、デバイスとアプリケーションの製品利用統計情報を可能な限り記録し、Zimperium クラウド サービスにテレメトリ データを送信し、モバイル デバイスの脅威に対するリスクを評価します。</span><span class="sxs-lookup"><span data-stu-id="d98cf-108">Zimperium app for Android and iOS captures file system, network stack, device and application telemetry where available, then sends the telemetry data to the Zimperium cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="d98cf-109">Intune デバイス コンプライアンス ポリシーには、Zimperium リスク評価に基づく、Zimperium Mobile Threat Defense のルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d98cf-109">The Intune device compliance policy includes a rule for Zimperium Mobile Threat Defense, which is based on the Zimperium risk assessment.</span></span> <span data-ttu-id="d98cf-110">このルールを有効にすると、Intune は、有効にされたポリシーに基づいてデバイスの準拠状態を評価します。</span><span class="sxs-lookup"><span data-stu-id="d98cf-110">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span> <span data-ttu-id="d98cf-111">デバイスが準拠していないことが判明した場合、ユーザーは Exchange Online や SharePoint Online などの会社リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d98cf-111">If the device is found non-compliant, users are blocked access to corporate resources like Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="d98cf-112">また、ユーザーは、デバイスにインストールされている Zimperium アプリから、問題を解決して会社リソースへのアクセスを回復するための案内を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d98cf-112">Users also receive guidance from the Zimperium app installed in their devices to resolve the issue and regain access to corporate resources.</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="d98cf-113">サンプル事例</span><span class="sxs-lookup"><span data-stu-id="d98cf-113">Sample scenarios</span></span>

<span data-ttu-id="d98cf-114">Intune と Zimperium を統合する場合のシナリオのいくつかを、下記で参照してください。</span><span class="sxs-lookup"><span data-stu-id="d98cf-114">See below a few scenarios when integrating Zimperium with Intune:</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="d98cf-115">悪意のあるアプリの脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="d98cf-115">Control access based on threats from malicious apps</span></span>

<span data-ttu-id="d98cf-116">マルウェアなどの悪意のあるアプリがデバイスで検出されると、脅威が解決されるまで、デバイスで次の行為が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="d98cf-116">When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:</span></span>

-   <span data-ttu-id="d98cf-117">会社の電子メールに接続する</span><span class="sxs-lookup"><span data-stu-id="d98cf-117">Connecting to corporate e-mail</span></span>

-   <span data-ttu-id="d98cf-118">OneDrive for Work アプリを使用して会社のファイルを同期する</span><span class="sxs-lookup"><span data-stu-id="d98cf-118">Syncing corporate files with the OneDrive for Work app</span></span>

-   <span data-ttu-id="d98cf-119">会社のアプリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="d98cf-119">Accessing company apps</span></span>

<span data-ttu-id="d98cf-120">**悪意のあるアプリが検出されたときにブロックする:**</span><span class="sxs-lookup"><span data-stu-id="d98cf-120">**Block when malicious apps are detected:**</span></span>

![検出された悪意のあるアプリ](./media/Maliciousapps_blocked_Zimperium.png)

<span data-ttu-id="d98cf-122">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="d98cf-122">**Access granted on remediation:**</span></span>

![悪意のあるアプリの検出、アクセス権](./media/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="d98cf-124">ネットワークに対する脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="d98cf-124">Control access based on threat to network</span></span>

<span data-ttu-id="d98cf-125">ネットワークで **Man-in-the-middle** のような脅威を検出し、デバイスのリスクに基づいて Wi-Fi ネットワークへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="d98cf-125">Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.</span></span>

<span data-ttu-id="d98cf-126">**Wi-Fi 経由のネットワーク アクセスをブロックする:**</span><span class="sxs-lookup"><span data-stu-id="d98cf-126">**Block network access through Wi-Fi:**</span></span>

![Wi-Fi 経由のネットワーク アクセスをブロックする](./media/network_wifi_blocked_Zimperium.png)

<span data-ttu-id="d98cf-128">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="d98cf-128">**Access granted on remediation:**</span></span>

![修復するとアクセス権が付与される](./media/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="d98cf-130">ネットワークに対する脅威に基づいて SharePoint Online へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="d98cf-130">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="d98cf-131">ネットワークで **Man-in-the-middle** のような脅威を検出し、デバイスのリスクに基づいて会社内のファイルの同期を阻止します。</span><span class="sxs-lookup"><span data-stu-id="d98cf-131">Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="d98cf-132">**ネットワークの脅威が検出されたときに SharePoint Online をブロック:**</span><span class="sxs-lookup"><span data-stu-id="d98cf-132">**Block SharePoint Online when network threats are detected:**</span></span>

![ネットワークの脅威が検出されたときに SharePoint Online をブロック](./media/network_spo_blocked_Zimperium.png)

<span data-ttu-id="d98cf-134">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="d98cf-134">**Access granted on remediation:**</span></span>

![SharePoint で修復時にアクセス権を付与する例](./media/network_spo_unblocked_Zimperium.png)

## <a name="supported-platforms"></a><span data-ttu-id="d98cf-136">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="d98cf-136">Supported platforms</span></span>

-   <span data-ttu-id="d98cf-137">**Android 4.1 以降**</span><span class="sxs-lookup"><span data-stu-id="d98cf-137">**Android 4.1 and later**</span></span>

-   <span data-ttu-id="d98cf-138">**iOS 8 以降**</span><span class="sxs-lookup"><span data-stu-id="d98cf-138">**iOS 8 and later**</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d98cf-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="d98cf-139">Prerequisites</span></span>

-   <span data-ttu-id="d98cf-140">Azure Active Directory Premium</span><span class="sxs-lookup"><span data-stu-id="d98cf-140">Azure Active Directory Premium</span></span>

-   <span data-ttu-id="d98cf-141">Microsoft Intune サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="d98cf-141">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="d98cf-142">Zimperium Mobile Threat Defense サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="d98cf-142">Zimperium Mobile Threat Defense subscription</span></span>

    -   <span data-ttu-id="d98cf-143">詳細については、[Zimperium Web サイト](https://www.zimperium.com/zips-mobile-ips)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d98cf-143">See [Zimperium website](https://www.zimperium.com/zips-mobile-ips) for more information.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d98cf-144">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d98cf-144">Next steps</span></span>

- [<span data-ttu-id="d98cf-145">Zimperium を Intune と統合する</span><span class="sxs-lookup"><span data-stu-id="d98cf-145">Integrate Zimperium with Intune</span></span>](zimperium-mtd-connector-integration.md)

- [<span data-ttu-id="d98cf-146">Zimperium アプリを設定する</span><span class="sxs-lookup"><span data-stu-id="d98cf-146">Set up Zimperium apps</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [<span data-ttu-id="d98cf-147">Zimperium デバイス コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d98cf-147">Create Zimperium device compliance policy</span></span>](mtd-device-compliance-policy-create.md)

- [<span data-ttu-id="d98cf-148">Zimperium MTD コネクタを有効にする</span><span class="sxs-lookup"><span data-stu-id="d98cf-148">Enable Zimperium MTD connector</span></span>](mtd-connector-enable.md)
