---
title: "Lookout Mobile Threat Defense コネクター"
description: "Lookout Mobile Threat Defense コネクターと Intune を使用して、デバイス、ネットワーク、アプリケーションのリスクを基にして会社のリソースへのアクセスを保護します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70fe5087dabae5d2eb7b3e60c3e716d3f0e927f8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a><span data-ttu-id="97378-103">Lookout Mobile Threat Defense コネクターと Intune</span><span class="sxs-lookup"><span data-stu-id="97378-103">Lookout Mobile Threat Defense connector with Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="97378-104">Microsoft Intune に統合された Mobile Threat Defense ソリューションである Lookout によって実行されるリスク評価に基づいて、モバイル デバイスから会社のリソースへのアクセスを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="97378-104">You can control mobile device access to corporate resources based on risk assessment conducted by Lookout, a Mobile Threat Defense solution integrated with Microsoft Intune.</span></span> <span data-ttu-id="97378-105">リスクは、Lookout サービスによりデバイスから収集される次のような製品利用統計情報に基づいて評価されます。</span><span class="sxs-lookup"><span data-stu-id="97378-105">Risk is assessed based on telemetry collected from devices by the Lookout service including:</span></span>
- <span data-ttu-id="97378-106">オペレーティング システムの脆弱性</span><span class="sxs-lookup"><span data-stu-id="97378-106">Operating system vulnerabilities</span></span>
- <span data-ttu-id="97378-107">インストールされた悪意のあるアプリ</span><span class="sxs-lookup"><span data-stu-id="97378-107">Malicious apps installed</span></span>
- <span data-ttu-id="97378-108">悪意のあるネットワーク プロファイル</span><span class="sxs-lookup"><span data-stu-id="97378-108">Malicious network profiles</span></span>

<span data-ttu-id="97378-109">Intune コンプライアンス ポリシーにより有効になった Lookout のリスク評価に基づいて条件付きアクセス ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="97378-109">You can  configure conditional access policies based on Lookout's risk assessment enabled through Intune compliance policies.</span></span> <span data-ttu-id="97378-110">設定により、検出された脅威に基づいて非準拠デバイスを許可したり、ブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="97378-110">Settings let you allow or block non-compliant devices based on detected threats.</span></span>

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a><span data-ttu-id="97378-111">Intune および Lookout の Mobile Threat Defense は会社リソースの保護にどのように役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="97378-111">How do Intune and Lookout Mobile Threat Defense help protect company resources?</span></span>
<span data-ttu-id="97378-112">Lookout のモバイル アプリ、**Lookout for work** は、モバイル デバイスにインストールされ、実行されます。</span><span class="sxs-lookup"><span data-stu-id="97378-112">Lookout’s mobile app, **Lookout for work**, is installed and run on mobile devices.</span></span> <span data-ttu-id="97378-113">このアプリは、利用できる場合、ファイル システム、ネットワーク スタック、デバイスとアプリケーションの製品利用統計情報を記録し、Lookout クラウド サービスに送信し、モバイル デバイスの脅威に対するリスクを評価します。</span><span class="sxs-lookup"><span data-stu-id="97378-113">This app captures file system, network stack, and device and application telemetry where available, then sends it to the Lookout cloud service to assess the device's risk for mobile threats.</span></span> <span data-ttu-id="97378-114">Lookout コンソールでは、要件に合わせ、脅威に対するリスク レベルの分類を変更できます。</span><span class="sxs-lookup"><span data-stu-id="97378-114">You can change risk level classifications for threats in the Lookout console to suit your requirements.</span></span>  

<span data-ttu-id="97378-115">Intune のコンプライアンス ポリシーには、Lookout のリスク評価に基づく Lookout Mobile Threat Defense のルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="97378-115">The compliance policy in Intune includes a rule for Lookout Mobile Threat Defense based on Lookout risk assessment.</span></span> <span data-ttu-id="97378-116">このルールを有効にすると、Intune は、有効にされたポリシーに基づいてデバイスの準拠状態を評価します。</span><span class="sxs-lookup"><span data-stu-id="97378-116">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="97378-117">デバイスが準拠していないことが判明した場合、Exchange Online や SharePoint Online などのリソースに対するアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="97378-117">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online can blocked.</span></span> <span data-ttu-id="97378-118">ブロックされたデバイスのユーザーには、問題を解決し、アクセスを回復するための手順が与えられます。</span><span class="sxs-lookup"><span data-stu-id="97378-118">Users on blocked devices receive a steps to resolve the issue and regain access.</span></span> <span data-ttu-id="97378-119">ガイダンスは Lookout for work アプリから起動されます。</span><span class="sxs-lookup"><span data-stu-id="97378-119">Guidance is launched from the Lookout for work app.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="97378-120">サポートされているプラットフォーム:</span><span class="sxs-lookup"><span data-stu-id="97378-120">Supported platforms:</span></span>
<span data-ttu-id="97378-121">Intune に登録するとき、Lookout では次のプラットフォームがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="97378-121">The following platforms are supported for Lookout when enrolled in Intune:</span></span>
* <span data-ttu-id="97378-122">**Android 4.1 以降**</span><span class="sxs-lookup"><span data-stu-id="97378-122">**Android 4.1 and later**</span></span>
* <span data-ttu-id="97378-123">**iOS 8 以降** プラットフォームと言語サポートの詳細については、[Lookout Web サイト](https://personal.support.lookout.com/hc/articles/114094140253)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97378-123">**iOS 8 and later** For additional information about platform and language support, visit the [Lookout website](https://personal.support.lookout.com/hc/articles/114094140253).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97378-124">前提条件:</span><span class="sxs-lookup"><span data-stu-id="97378-124">Prerequisites:</span></span>
* <span data-ttu-id="97378-125">Microsoft Intune サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="97378-125">Microsoft Intune subscription</span></span>
* <span data-ttu-id="97378-126">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="97378-126">Azure Active Directory</span></span>
* <span data-ttu-id="97378-127">Lookout Mobile EndPoint Security エンタープライズ サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="97378-127">Lookout Mobile Endpoint Security enterprise subscription</span></span>  

<span data-ttu-id="97378-128">詳細については、「[Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97378-128">For more information, see [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="97378-129">サンプル事例</span><span class="sxs-lookup"><span data-stu-id="97378-129">Sample scenarios</span></span>
<span data-ttu-id="97378-130">一般的なシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="97378-130">Following are some common scenarios:</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="97378-131">悪意のあるアプリの脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="97378-131">Control access based on threats from malicious apps</span></span>
<span data-ttu-id="97378-132">マルウェアなどの悪意のあるアプリがデバイスで検出されると、脅威が解決されるまで、デバイスで次の行為が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="97378-132">When malicious apps such as malware are detected on devices, you can block devices from the following until the threat is resolved:</span></span>
* <span data-ttu-id="97378-133">会社の電子メールに接続する</span><span class="sxs-lookup"><span data-stu-id="97378-133">Connecting to corporate e-mail</span></span>
* <span data-ttu-id="97378-134">OneDrive for Work アプリを使用して会社のファイルを同期する</span><span class="sxs-lookup"><span data-stu-id="97378-134">Syncing corporate files with the OneDrive for Work app</span></span>
* <span data-ttu-id="97378-135">会社のアプリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="97378-135">Accessing company apps</span></span>

<span data-ttu-id="97378-136">**悪意のあるアプリが検出されたときのブロック:**
![悪意のあるアプリが検出されたことからデバイスが非準拠状態と判断された場合に、アクセスをブロックする条件付きアクセス ポリシーを示す図](../media/mtp/malicious-apps-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="97378-136">**Block when malicious apps are detected:**
![diagram showing conditional access policy blocking access when device is determined to be non-compliant due to malicious apps on the device](../media/mtp/malicious-apps-blocked.png)</span></span>

<span data-ttu-id="97378-137">**修復時に付与されるアクセス権:**</span><span class="sxs-lookup"><span data-stu-id="97378-137">**Access granted on remediation:**</span></span>

![修復後、デバイスが準拠状態にあると判断された場合にアクセス権を付与する条件付きアクセス ポリシーを示す図](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="97378-139">ネットワークに対する脅威に基づいてアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="97378-139">Control access based on threat to network</span></span>
<span data-ttu-id="97378-140">Man-in-the-middle 攻撃など、ネットワークに対する脅威を検出し、デバイスのリスクに基づいて WiFi ネットワークへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="97378-140">Detect threats to your network such as Man-in-the-middle attacks and protect access to WiFi networks based on the device risk.</span></span>

<span data-ttu-id="97378-141">**WiFi 経由でネットワークにアクセスする行為のブロック:**
![ネットワークの脅威に基づいて WiFi アクセスをブロックする条件付きアクセスを示す図](../media/mtp/network-wifi-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="97378-141">**Block network access through WiFi:**
![diagram showing conditional access blocking WiFi access based on network threats](../media/mtp/network-wifi-blocked.png)</span></span>

<span data-ttu-id="97378-142">**修復後、アクセスが与えられる:**</span><span class="sxs-lookup"><span data-stu-id="97378-142">**Access granted on remediation:**</span></span>

![脅威の修復時にアクセスを許可する条件付きアクセスを示す図](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="97378-144">ネットワークに対する脅威に基づいて SharePoint Online へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="97378-144">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="97378-145">Man-in-the-middle 攻撃など、ネットワークに対する脅威を検出し、デバイスのリスクに基づいて会社内のファイルの同期を阻止します。</span><span class="sxs-lookup"><span data-stu-id="97378-145">Detect threats to your network such as Man-in-the-middle attacks, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="97378-146">**ネットワークの脅威が検出されたときに SharePoint Online をブロック:**</span><span class="sxs-lookup"><span data-stu-id="97378-146">**Block SharePoint Online when network threats are detected:**</span></span>

![検出した脅威に基づいて SharePoint Online へのデバイスのアクセスをブロックする条件付きアクセスを示す図](../media/mtp/network-spo-blocked.png)


<span data-ttu-id="97378-148">**修復後、アクセスが与えられる:**</span><span class="sxs-lookup"><span data-stu-id="97378-148">**Access granted on remediation:**</span></span>

![ネットワークの脅威が修復された後でアクセスを許可する条件付きアクセスを示す図](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a><span data-ttu-id="97378-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="97378-150">Next steps</span></span>
<span data-ttu-id="97378-151">このソリューションを実装するために実行する必要がある主な手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="97378-151">Here are the main steps you must do to implement this solution:</span></span>
1.  [<span data-ttu-id="97378-152">Lookout サブスクリプションを設定する</span><span class="sxs-lookup"><span data-stu-id="97378-152">Set up your Lookout subscription</span></span>](setup-your-lookout-mtd-subscription.md)
2.  [<span data-ttu-id="97378-153">Intune で Lookout Mobile Threat Defense を有効にする</span><span class="sxs-lookup"><span data-stu-id="97378-153">Enable Lookout Mobile Threat Defense in Intune</span></span>](enable-lookout-mtd-connection.md)
3.  [<span data-ttu-id="97378-154">Lookout Mobile Threat Defense アプリを構成し、展開する</span><span class="sxs-lookup"><span data-stu-id="97378-154">Configure and deploy Lookout Mobile Threat Defense app</span></span>](configure-deploy-lookout-for-work-app.md)
4.  [<span data-ttu-id="97378-155">Lookout デバイス コンプライアンス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="97378-155">Configure Lookout device compliance policy</span></span>](create-lookout-device-compliance-policy.md)
5.  [<span data-ttu-id="97378-156">Lookout Mobile Threat Defense 統合の問題を解決する</span><span class="sxs-lookup"><span data-stu-id="97378-156">Troubleshoot Lookout Mobile Threat Defense integration</span></span>](/intune-classic/troubleshoot/device-threat-protection-troubleshooting)
