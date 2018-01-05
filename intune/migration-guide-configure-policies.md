---
title: "Intune 移行中にデバイス コンプライアンス ポリシーとアプリ管理ポリシーを構成する"
description: "この記事では、Intune 移行中にデバイスのコンプライアンス ポリシーとアプリ管理ポリシーを構成するために必要な手順について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: b75368bb8a1172444036b5bd695a4ec36cd9727c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="configure-device-compliance-and-app-management-policies"></a><span data-ttu-id="9748d-103">デバイス コンプライアンス ポリシーとアプリ管理ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="9748d-103">Configure device compliance and app management policies</span></span>

<span data-ttu-id="9748d-104">Intune 移行時の主な目標は、すべてのデバイスが Intune に登録されてポリシーに準拠することです。</span><span class="sxs-lookup"><span data-stu-id="9748d-104">The main goal when migrating to Intune is to have all devices enrolled in Intune and compliant with its policies.</span></span> <span data-ttu-id="9748d-105">デバイス ポリシーは企業が所有する単一ユーザーのデバイスの管理だけでなく、個人用 (BYOD) デバイスや共有デバイス (キオスク、店頭端末機器、教室で複数の学生が共有するタブレットなど)、またユーザーレス デバイス (iOS のみ) の管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9748d-105">Device policies not only help you to manage corporate-owned single-user devices, but also personal (BYOD), and shared devices such as kiosks, point-of-sales machines, tablets shared by multiple students in a classroom, or user-less devices (iOS only).</span></span>

<span data-ttu-id="9748d-106">デバイス プラットフォームごとに設定は異なりますが、Intune デバイス ポリシーは次のモバイル デバイス管理機能を提供することで、それぞれのデバイス プラットフォームで動作します。</span><span class="sxs-lookup"><span data-stu-id="9748d-106">Each device platform may offer different settings, but Intune device policies work with each device platform by providing the following mobile device management capabilities:</span></span>

-   <span data-ttu-id="9748d-107">各ユーザーが登録するデバイス数の制限。</span><span class="sxs-lookup"><span data-stu-id="9748d-107">Regulate numbers of devices each user enrolls.</span></span>

-   <span data-ttu-id="9748d-108">デバイスの設定 (デバイス レベルの暗号化、パスワードの文字数、カメラの使用など) の管理。</span><span class="sxs-lookup"><span data-stu-id="9748d-108">Manage devices settings (for example, device-level encryption, password length, camera usage).</span></span>

-   <span data-ttu-id="9748d-109">アプリ、電子メール プロファイル、VPN プロファイルなどの提供。</span><span class="sxs-lookup"><span data-stu-id="9748d-109">Deliver apps, email profiles, VPN profiles, and so on.</span></span>

-   <span data-ttu-id="9748d-110">セキュリティ コンプライアンス ポリシーのデバイス レベルの基準の評価。</span><span class="sxs-lookup"><span data-stu-id="9748d-110">Evaluate device-level criteria for security compliance policies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9748d-111">デバイス管理ポリシーは、個々のデバイスやユーザーに直接割り当てられるわけではなく、ユーザー グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9748d-111">Device management policies are not assigned directly to individual devices or users, but instead are assigned to user groups.</span></span> <span data-ttu-id="9748d-112">ユーザー グループにポリシーが直接適用されることにより、ユーザーのデバイスにポリシーが適用されます。あるいはデバイス グループにポリシーが適用されることにより、グループのメンバーにポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9748d-112">The policies may be directly applied to a user group, and thereby to the user's device, or the policies may be applied to a device group, and thereby to group members.</span></span>

## <a name="task-list-for-device-compliance-policies"></a><span data-ttu-id="9748d-113">デバイス コンプライアンス ポリシーのタスク一覧</span><span class="sxs-lookup"><span data-stu-id="9748d-113">Task list for device compliance policies</span></span>

### <a name="task-1-add-device-groups-optional"></a><span data-ttu-id="9748d-114">タスク 1: デバイス グループを追加する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="9748d-114">Task 1: Add device groups (optional)</span></span>

<span data-ttu-id="9748d-115">ユーザー ID ではなくデバイス ID に基づいて管理タスクを実行する必要がある場合に、デバイス グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9748d-115">You can create device groups when you need to perform administrative tasks based on device identity instead of user identity.</span></span>

<span data-ttu-id="9748d-116">デバイス グループは、専用ユーザーがいないデバイス (キオスク デバイス、交代勤務従業員が共有するデバイス、または特定の場所に割り当てられたデバイスなど) の管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9748d-116">Device groups are useful for managing devices that do not have dedicated users, such as kiosk devices, devices shared by shift workers, or devices assigned to a specific location.</span></span>

<span data-ttu-id="9748d-117">デバイスを登録する前にデバイス グループを構成しておくと、デバイス カテゴリを使って、登録時にデバイスをグループに自動的に参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="9748d-117">By configuring device groups ahead of device enrollment, you can use device categories to automatically join devices to groups upon enrollment.</span></span> <span data-ttu-id="9748d-118">その後、デバイスはグループのデバイス ポリシーを自動的に受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9748d-118">Then they will receive their group’s device policies automatically.</span></span> <span data-ttu-id="9748d-119">「[グループの概要](groups-get-started.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9748d-119">[Get started with groups](groups-get-started.md).</span></span>

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a><span data-ttu-id="9748d-120">タスク 2: リソース アクセス プロファイル (Wi-Fi、VPN、および電子メールの証明書) を使用する</span><span class="sxs-lookup"><span data-stu-id="9748d-120">Task 2: Use resource access profiles (Wi-Fi, VPN, and email certificates)</span></span>

<span data-ttu-id="9748d-121">リソース アクセス プロファイルは、登録されたデバイスに証明書とアクセス構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="9748d-121">Resource access profiles supply certificates and access configurations to enrolled devices.</span></span> <span data-ttu-id="9748d-122">証明書ベースの認証を使っている場合は、[証明書を構成](certificates-configure.md)します。</span><span class="sxs-lookup"><span data-stu-id="9748d-122">If you are using certificate-based authentication, [configure certificates](certificates-configure.md).</span></span>

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a><span data-ttu-id="9748d-123">タスク 3: デバイス構成プロファイルを作成して展開する</span><span class="sxs-lookup"><span data-stu-id="9748d-123">Task 3: Create and deploy device configuration profiles</span></span>

<span data-ttu-id="9748d-124">デバイス構成プロファイルを作成して、デバイス レベルの設定 (カメラの無効化、アプリ ストア、単一アプリ モードの構成、ホーム画面など) を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9748d-124">You need to create a device configuration profile to enforce device-level settings, for example: disable camera, app-store, configure single-app mode, home screen, and so on.</span></span> <span data-ttu-id="9748d-125">デバイス プロファイルについては、[こちら](device-profiles.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9748d-125">Learn about [device profiles](device-profiles.md).</span></span>

####  <a name="directly-import-ios-configuration-profiles-optional"></a><span data-ttu-id="9748d-126">iOS 構成プロファイルを直接インポートする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="9748d-126">Directly import iOS configuration profiles (optional)</span></span>

-   <span data-ttu-id="9748d-127">**Apple Configurator iOS プロファイル (iOS 7.1 以降):** 既存の MDM ソリューションで Apple Configurator プロファイル (.mobileconfig ファイル) を使用している場合、Intune ではカスタムの構成ポリシーとして、このプロファイルを直接インポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="9748d-127">**Apple Configurator iOS profiles (iOS 7.1 and later):** If your existing MDM solution uses Apple Configurator profiles (.mobileconfig files), Intune can directly import them as custom configuration policies.</span></span>

-   <span data-ttu-id="9748d-128">**iOS モバイル アプリケーション構成ポリシー:** 既存の MDM ソリューションで iOS モバイル アプリケーション構成ポリシーを使用している場合、Apple によりプロパティ一覧で指定された XML 形式を満たす限り、Intune はこのポリシーを直接インポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="9748d-128">**iOS Mobile Application Configuration policies:** If your existing MDM solution uses iOS Mobile Application Configuration policies, Intune can directly import them as long as they meet the XML format specified by Apple for property lists.</span></span>

- <span data-ttu-id="9748d-129">iOS のカスタム ポリシーを追加する方法は[こちら](custom-settings-ios.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9748d-129">Learn how to add a custom policy for [iOS](custom-settings-ios.md).</span></span>

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a><span data-ttu-id="9748d-130">タスク 4: デバイス コンプライアンス ポリシーを作成して展開する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="9748d-130">Task 4: Create and deploy device compliance policies (optional)</span></span>

<span data-ttu-id="9748d-131">デバイス コンプライアンス ポリシーはセキュリティ指向の設定を評価し、デバイスが会社の基準に準拠しているかどうかを示すレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="9748d-131">Device compliance policies evaluate security-oriented settings, and provide reporting that shows whether the devices are compliant with corporate standards or not.</span></span> <span data-ttu-id="9748d-132">設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9748d-132">Such settings include:</span></span>

-   <span data-ttu-id="9748d-133">PIN の長さ</span><span class="sxs-lookup"><span data-stu-id="9748d-133">PIN length</span></span>

-   <span data-ttu-id="9748d-134">脱獄状態</span><span class="sxs-lookup"><span data-stu-id="9748d-134">Jail-broken status</span></span>

-   <span data-ttu-id="9748d-135">OS のバージョン</span><span class="sxs-lookup"><span data-stu-id="9748d-135">OS version</span></span>

<span data-ttu-id="9748d-136">デバイス コンプライアンス設定に関する他のリソースは次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9748d-136">See additional resources for device compliance settings:</span></span>

-   <span data-ttu-id="9748d-137">デバイス コンプライアンス ポリシーは、[こちら](device-compliance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9748d-137">Learn about [device compliance policies](device-compliance.md).</span></span>

-   <span data-ttu-id="9748d-138">デバイス コンプライアンス ポリシーの作成方法は、[こちら](device-compliance-get-started.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9748d-138">Learn [how to create a device compliance policy](device-compliance-get-started.md).</span></span>

### <a name="task-5-publish-and-deploy-apps"></a><span data-ttu-id="9748d-139">タスク 5: アプリを公開して展開する</span><span class="sxs-lookup"><span data-stu-id="9748d-139">Task 5: Publish and deploy apps</span></span>

<span data-ttu-id="9748d-140">Intune MDM を使用する場合は、アプリの自動インストールを要求するか、ポータル サイトでアプリを使用できるようにすることで、アプリを提供できます。</span><span class="sxs-lookup"><span data-stu-id="9748d-140">When using Intune MDM, you can supply apps by either requiring their automatic installation, or making them available in the Company Portal.</span></span>

-   <span data-ttu-id="9748d-141">[アプリを追加する方法](apps-add.md)。</span><span class="sxs-lookup"><span data-stu-id="9748d-141">[How to add apps](apps-add.md).</span></span>

-   <span data-ttu-id="9748d-142">[アプリを展開する方法](apps-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="9748d-142">[How to deploy apps](apps-deploy.md).</span></span>

### <a name="task-6-enable-device-enrollment"></a><span data-ttu-id="9748d-143">タスク 6: デバイスの登録を可能にする</span><span class="sxs-lookup"><span data-stu-id="9748d-143">Task 6: Enable device enrollment</span></span>

<span data-ttu-id="9748d-144">デバイスを管理するには、デバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9748d-144">Device enrollment is necessary to manage the device.</span></span> <span data-ttu-id="9748d-145">企業所有およびユーザー個人のデバイスの登録を準備する方法については、[こちら](device-enrollment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9748d-145">Learn [how to get ready to enroll corporate-owned and user personal's devices](device-enrollment.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9748d-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="9748d-146">Next steps</span></span>

<span data-ttu-id="9748d-147">[アプリ保護ポリシーを構成する (省略可能)](migration-guide-app-protection-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9748d-147">[Configure app protection policies (optional)](migration-guide-app-protection-policies.md).</span></span>
