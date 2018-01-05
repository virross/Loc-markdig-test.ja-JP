---
title: "Lookout Mobile Threat Defense コネクターと Intune"
titlesuffix: Azure portal
description: "Lookout Mobile Threat Defense コネクタと Intune の設定"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2c13aa920358526deddcdb912833217c88f27371
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a><span data-ttu-id="c28c7-103">Lookout Mobile Threat Defense コネクターと Intune</span><span class="sxs-lookup"><span data-stu-id="c28c7-103">Lookout Mobile Threat Defense connector with Intune</span></span>

<span data-ttu-id="c28c7-104">Microsoft Intune に統合された Mobile Threat Defense ソリューションである Lookout によって実行されるリスク評価に基づいて、モバイル デバイスから会社のリソースへのアクセスを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-104">You can control mobile device access to corporate resources based on risk assessment conducted by Lookout, a Mobile Threat Defense solution integrated with Microsoft Intune.</span></span> <span data-ttu-id="c28c7-105">リスクは、Lookout サービスによりデバイスから収集される次のような製品利用統計情報に基づいて評価されます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-105">Risk is assessed based on telemetry collected from devices by the Lookout service including:</span></span>
- <span data-ttu-id="c28c7-106">オペレーティング システムの脆弱性</span><span class="sxs-lookup"><span data-stu-id="c28c7-106">Operating system vulnerabilities</span></span>
- <span data-ttu-id="c28c7-107">インストールされた悪意のあるアプリ</span><span class="sxs-lookup"><span data-stu-id="c28c7-107">Malicious apps installed</span></span>
- <span data-ttu-id="c28c7-108">悪意のあるネットワーク プロファイル</span><span class="sxs-lookup"><span data-stu-id="c28c7-108">Malicious network profiles</span></span>

<span data-ttu-id="c28c7-109">Intune コンプライアンス ポリシーにより有効になった Lookout のリスク評価に基づいて条件付きアクセス ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-109">You can configure conditional access policies based on Lookout's risk assessment enabled through Intune compliance policies.</span></span> <span data-ttu-id="c28c7-110">設定により、検出された脅威に基づいて非準拠デバイスを許可したり、ブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-110">Settings let you allow or block non-compliant devices based on detected threats.</span></span>

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a><span data-ttu-id="c28c7-111">Intune および Lookout の Mobile Threat Defense は会社リソースの保護にどのように役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="c28c7-111">How do Intune and Lookout Mobile Threat Defense help protect company resources?</span></span>
<span data-ttu-id="c28c7-112">Lookout のモバイル アプリ、**Lookout for work** は、モバイル デバイスにインストールされ、実行されます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-112">Lookout’s mobile app, **Lookout for work**, is installed and run on mobile devices.</span></span> <span data-ttu-id="c28c7-113">このアプリは、利用できる場合、ファイル システム、ネットワーク スタック、デバイスとアプリケーションの製品利用統計情報を記録し、Lookout クラウド サービスに送信し、モバイル デバイスの脅威に対するリスクを評価します。</span><span class="sxs-lookup"><span data-stu-id="c28c7-113">This app captures file system, network stack, and device and application telemetry where available, then sends it to the Lookout cloud service to assess the device's risk for mobile threats.</span></span> <span data-ttu-id="c28c7-114">Lookout コンソールでは、要件に合わせ、脅威に対するリスク レベルの分類を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-114">You can change risk level classifications for threats in the Lookout console to suit your requirements.</span></span>  

<span data-ttu-id="c28c7-115">Intune のコンプライアンス ポリシーには、Lookout のリスク評価に基づく Lookout Mobile Threat Defense のルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c28c7-115">The compliance policy in Intune includes a rule for Lookout Mobile Threat Defense based on Lookout risk assessment.</span></span> <span data-ttu-id="c28c7-116">このルールを有効にすると、Intune は、有効にされたポリシーに基づいてデバイスの準拠状態を評価します。</span><span class="sxs-lookup"><span data-stu-id="c28c7-116">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="c28c7-117">デバイスが準拠していないことが判明した場合、Exchange Online や SharePoint Online などのリソースに対するアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-117">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online can blocked.</span></span> <span data-ttu-id="c28c7-118">ブロックされたデバイスのユーザーには、問題を解決し、アクセスを回復するための手順が与えられます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-118">Users on blocked devices receive a steps to resolve the issue and regain access.</span></span> <span data-ttu-id="c28c7-119">ガイダンスは Lookout for work アプリから起動されます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-119">Guidance is launched from the Lookout for work app.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="c28c7-120">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="c28c7-120">Supported platforms</span></span>
<span data-ttu-id="c28c7-121">Intune に登録するとき、Lookout では次のプラットフォームがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-121">The following platforms are supported for Lookout when enrolled in Intune:</span></span>
* <span data-ttu-id="c28c7-122">**Android 4.1 以降**</span><span class="sxs-lookup"><span data-stu-id="c28c7-122">**Android 4.1 and later**</span></span>
* <span data-ttu-id="c28c7-123">**iOS 8 以降** プラットフォームと言語サポートの詳細については、[Lookout Web サイト](https://personal.support.lookout.com/hc/articles/114094140253)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c28c7-123">**iOS 8 and later** For additional information about platform and language support, visit the [Lookout website](https://personal.support.lookout.com/hc/articles/114094140253).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c28c7-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="c28c7-124">Prerequisites</span></span>
* <span data-ttu-id="c28c7-125">Microsoft Intune サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="c28c7-125">Microsoft Intune subscription</span></span>
* <span data-ttu-id="c28c7-126">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c28c7-126">Azure Active Directory</span></span>
* <span data-ttu-id="c28c7-127">Lookout Mobile EndPoint Security エンタープライズ サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="c28c7-127">Lookout Mobile Endpoint Security enterprise subscription</span></span>  

<span data-ttu-id="c28c7-128">詳細については、「[Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c28c7-128">For more information, see [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="c28c7-129">サンプル事例</span><span class="sxs-lookup"><span data-stu-id="c28c7-129">Sample scenarios</span></span>

<span data-ttu-id="c28c7-130">Intune で Lookout Mobile Threat Defense を使用する場合の一般的なシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c28c7-130">Here are the common scenarios when using Lookout Mobile Threat Defense with Intune.</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="c28c7-131">悪意のあるアプリの脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="c28c7-131">Control access based on threats from malicious apps</span></span>
<span data-ttu-id="c28c7-132">マルウェアなどの悪意のあるアプリがデバイスで検出されると、脅威が解決されるまで、デバイスで次の行為が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="c28c7-132">When malicious apps such as malware are detected on devices, you can block devices from the following until the threat is resolved:</span></span>
* <span data-ttu-id="c28c7-133">会社の電子メールに接続する</span><span class="sxs-lookup"><span data-stu-id="c28c7-133">Connecting to corporate e-mail</span></span>
* <span data-ttu-id="c28c7-134">OneDrive for Work アプリを使用して会社のファイルを同期する</span><span class="sxs-lookup"><span data-stu-id="c28c7-134">Syncing corporate files with the OneDrive for Work app</span></span>
* <span data-ttu-id="c28c7-135">会社のアプリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="c28c7-135">Accessing company apps</span></span>

<span data-ttu-id="c28c7-136">**悪意のあるアプリが検出されたときにブロックする:**</span><span class="sxs-lookup"><span data-stu-id="c28c7-136">**Block when malicious apps are detected:**</span></span>

![悪意のあるアプリに起因し、デバイスが非準拠として見なされたときにアクセスを禁止する条件付きアクセス ポリシーの図](./media/malicious-apps-blocked.png)

<span data-ttu-id="c28c7-138">**修復後、アクセスが与えられる:**</span><span class="sxs-lookup"><span data-stu-id="c28c7-138">**Access granted on remediation:**</span></span>

![修復後、デバイスが準拠状態にあると判断された場合にアクセス権を付与する条件付きアクセス ポリシーを示す図](./media/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="c28c7-140">ネットワークに対する脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="c28c7-140">Control access based on threat to network</span></span>
<span data-ttu-id="c28c7-141">Man-in-the-middle 攻撃など、ネットワークに対する脅威を検出し、デバイスのリスクに基づいて WiFi ネットワークへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="c28c7-141">Detect threats to your network such as man-in-the-middle attacks and protect access to WiFi networks based on the device risk.</span></span>

<span data-ttu-id="c28c7-142">**Wi-Fi 経由のネットワーク アクセスをブロックする:**</span><span class="sxs-lookup"><span data-stu-id="c28c7-142">**Block network access through WiFi:**</span></span>

![ネットワークの脅威に基づいて WiFi アクセスを禁止する条件付きアクセスの図](./media/network-wifi-blocked.png)

<span data-ttu-id="c28c7-144">**修復後、アクセスが与えられる:**</span><span class="sxs-lookup"><span data-stu-id="c28c7-144">**Access granted on remediation:**</span></span>

![脅威の修復時にアクセスを許可する条件付きアクセスを示す図](./media/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="c28c7-146">ネットワークに対する脅威に基づいて SharePoint Online へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="c28c7-146">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="c28c7-147">Man-in-the-middle 攻撃など、ネットワークに対する脅威を検出し、デバイスのリスクに基づいて会社内のファイルの同期を阻止します。</span><span class="sxs-lookup"><span data-stu-id="c28c7-147">Detect threats to your network such as Man-in-the-middle attacks, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="c28c7-148">**ネットワークの脅威が検出されたときに SharePoint Online をブロック:**</span><span class="sxs-lookup"><span data-stu-id="c28c7-148">**Block SharePoint Online when network threats are detected:**</span></span>

![検出した脅威に基づいて SharePoint Online へのデバイスのアクセスをブロックする条件付きアクセスを示す図](./media/network-spo-blocked.png)


<span data-ttu-id="c28c7-150">**修復後、アクセスが与えられる:**</span><span class="sxs-lookup"><span data-stu-id="c28c7-150">**Access granted on remediation:**</span></span>

![ネットワークの脅威が修復された後でアクセスを許可する条件付きアクセスを示す図](./media/network-spo-unblocked.png)

## <a name="next-steps"></a><span data-ttu-id="c28c7-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="c28c7-152">Next steps</span></span>
<span data-ttu-id="c28c7-153">このソリューションを実装するために実行する必要がある主な手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c28c7-153">Here are the main steps you must do to implement this solution:</span></span>
1.  [<span data-ttu-id="c28c7-154">Lookout 統合を設定する</span><span class="sxs-lookup"><span data-stu-id="c28c7-154">Set up your Lookout integration</span></span>](lookout-mtd-connector-integration.md)
2.  [<span data-ttu-id="c28c7-155">Intune で Lookout Mobile Threat Defense を有効にする</span><span class="sxs-lookup"><span data-stu-id="c28c7-155">Enable Lookout Mobile Threat Defense in Intune</span></span>](mtd-connector-enable.md)
3.  [<span data-ttu-id="c28c7-156">Lookout for Work アプリを追加して割り当てる</span><span class="sxs-lookup"><span data-stu-id="c28c7-156">Add and assign the Lookout for Work app</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)
4.  [<span data-ttu-id="c28c7-157">Lookout デバイス コンプライアンス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c28c7-157">Configure Lookout device compliance policy</span></span>](mtd-device-compliance-policy-create.md)
