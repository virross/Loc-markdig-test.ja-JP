---
title: "Intune との Check Point SandBlast Mobile コネクタ"
titlesuffix: Azure portal
description: "Check Point SandBlast と Intune の統合"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3f4a51ed34ee0ed8364d2d5ae68526a82412665
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a><span data-ttu-id="9a017-103">Intune との Check Point SandBlast Mobile Threat Defense コネクタ</span><span class="sxs-lookup"><span data-stu-id="9a017-103">Check Point SandBlast Mobile Threat Defense connector with Intune</span></span>

<span data-ttu-id="9a017-104">Microsoft Intune に統合された Mobile Threat Defense ソリューションであるチェック ポイントの SandBlast Mobile によって実行されるリスク評価に基づき、条件付きアクセスを利用し、モバイル デバイスから会社のリソースへのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="9a017-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Check Point SandBlast Mobile, a mobile threat defense solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="9a017-105">リスクは、チェック ポイントの SandBlast Mobile アプリを実行するデバイスから収集される製品利用統計情報に基づいて評価されます。</span><span class="sxs-lookup"><span data-stu-id="9a017-105">Risk is assessed based on telemetry collected from devices running the Check Point SandBlast Mobile app.</span></span>

<span data-ttu-id="9a017-106">Intune デバイス コンプライアンス ポリシーで有効にした Check Point SandBlast Mobile リスク評価に基づき、条件付きアクセスのポリシーを構成できます。Intune デバイス コンプライアンス ポリシーは、検出された脅威に基づき、非準拠デバイスから企業リソースへのアクセスを許可したり、拒否したりするために利用できます。</span><span class="sxs-lookup"><span data-stu-id="9a017-106">You can configure conditional access policies based on Check Point SandBlast Mobile risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a><span data-ttu-id="9a017-107">Intune と Check Point SandBlast Mobile を利用し、会社のリソースをどのように保護しますか?</span><span class="sxs-lookup"><span data-stu-id="9a017-107">How do Intune and Check Point SandBlast Mobile help protect your company resources?</span></span>

<span data-ttu-id="9a017-108">Android および iOS 向け Check Point Sandblast Mobile アプリは、ファイル システム、ネットワーク スタック、デバイスとアプリケーションの製品利用統計情報を可能な限り記録し、Check Point SandBlast クラウド サービスにテレメトリ データを送信し、モバイル デバイスの脅威に対するリスクを評価します。</span><span class="sxs-lookup"><span data-stu-id="9a017-108">Check Point Sandblast Mobile app for Android and iOS captures file system, network stack, device and application telemetry where available, then sends the telemetry data to the Check Point SandBlast cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="9a017-109">Intune デバイス コンプライアンス ポリシーには、Check Point SandBlast リスク評価に基づく、Check Point SandBlast Mobile Threat Defense のルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a017-109">The Intune device compliance policy includes a rule for Check Point SandBlast Mobile Threat Defense, which is based on the Check Point SandBlast risk assessment.</span></span> <span data-ttu-id="9a017-110">このルールを有効にすると、Intune は、有効にされたポリシーに基づいてデバイスの準拠状態を評価します。</span><span class="sxs-lookup"><span data-stu-id="9a017-110">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span> <span data-ttu-id="9a017-111">デバイスが準拠していないことが判明した場合、ユーザーは Exchange Online や SharePoint Online などの会社リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9a017-111">If the device is found non-compliant, users are blocked access to corporate resources like Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="9a017-112">また、ユーザーは、デバイスにインストールされている Check Point SandBlast Mobile アプリから、問題を解決して会社リソースへのアクセスを回復するための案内を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9a017-112">Users also receive guidance from the Check Point SandBlast mobile app installed in their devices to resolve the issue and regain access to corporate resources.</span></span>

<!-- ## Sample scenarios

Here are some common scenarios:

### Control access based on threats from malicious apps

When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:

-   Connecting to corporate e-mail

-   Syncing corporate files with the OneDrive for Work app

-   Accessing company apps

**Block when malicious apps are detected:**

![Check Point MTD block when malicious apps are detected](./media/checkpoint-MTD-2.PNG)

**Access granted on remediation:**

![Check Point MTD access granted](./media/checkpoint-MTD-3.PNG)

### Control access based on threat to network

Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.

**Block network access through Wi-Fi:**

![Check Point MTD block network access through Wi-Fi](./media/checkpoint-MTD-4.PNG)

**Access granted on remediation:**

![Check Point MTD Wi-Fi access granted](./media/checkpoint-MTD-5.PNG)

### Control access to SharePoint Online based on threat to network

Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

![Check Point MTD block SharePoint Online access](./media/checkpoint-MTD-6.PNG)

**Access granted on remediation:**

![Check Point MTD SharePoint Online access granted](./media/checkpoint-MTD-7.PNG)

## Supported platforms

-   **Android 4.1 and later**

-   **iOS 8 and later**

## Pre-requisites

-   Azure Active Directory Premium

-   Microsoft Intune subscription

-   Check Point SandBlast Mobile Threat Defense subscription
    -   See [CheckPoint SandBlast website](https://www.checkpoint.com/) for more information.

## Next steps

- [Integrate CheckPoint SandBlast with Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [Set up CheckPoint SandBlast Mobile app](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Create CheckPoint SandBlast Mobile device compliance policy](mtd-device-compliance-policy-create.md)

- [Enable CheckPoint SandBlast Mobile MTD connector](mtd-connector-enable.md)
