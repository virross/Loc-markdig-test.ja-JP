---
title: "Microsoft Intune のデバイス プロファイルとは"
titlesuffix: Azure portal
description: "Intune デバイス プロファイルについて、またプロファイルを用いて組織内でデバイスを管理および保護する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e27f48aee7552486da166de3cb38e213e55a5a4a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="what-are-microsoft-intune-device-profiles"></a><span data-ttu-id="07463-103">Microsoft Intune のデバイス プロファイルとは</span><span class="sxs-lookup"><span data-stu-id="07463-103">What are Microsoft Intune device profiles?</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="07463-104">Microsoft Intune の **[デバイスの構成]** ワークロードを使用して、管理対象とするすべてのデバイスの設定と機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="07463-104">Use the Microsoft Intune **Device configuration** workload to manage settings and features on all of the devices you manage.</span></span> <span data-ttu-id="07463-105">ほとんどの場合、このワークロードを使用してデバイス プロファイルを作成します。これにより、デバイスであらゆる種類の機能を管理および制御することができます。</span><span class="sxs-lookup"><span data-stu-id="07463-105">You mostly use this workload to create device profiles, which let you manage and control a whole range of different features and functionality on devices.</span></span>

<span data-ttu-id="07463-106">このワークロードを開くと、以下のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07463-106">When you open this workload, you see the following options:</span></span>

- <span data-ttu-id="07463-107">**[概要]** - このページには、ユーザーとデバイスに割り当てたデバイス構成を監視するのに役立つ状態およびレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07463-107">**Overview** - This page gives you status and reports that help you monitor device configurations that you have assigned to users and devices.</span></span>
- <span data-ttu-id="07463-108">**[管理] > [プロファイル]** - このセクションでは、デバイス構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="07463-108">**Manage Profiles** - This section is where you go to create device configuration profiles.</span></span> <span data-ttu-id="07463-109">作成できるすべてのプロファイルの種類については、このトピックで後述する一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07463-109">You can find a list all the profile types you can create later in this topic.</span></span>
- <span data-ttu-id="07463-110">**[セットアップ] > [証明機関]** - このワークフローでは、Intune 証明書プロファイルの構成に必要な手順が説明されています。</span><span class="sxs-lookup"><span data-stu-id="07463-110">**Setup Certificate Authority** - This workflow walks you though the steps required to configure Intune certificate profiles.</span></span>

## <a name="getting-started"></a><span data-ttu-id="07463-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="07463-111">Getting started</span></span>

<span data-ttu-id="07463-112">デバイス プロファイルを作成するためのワークフローには、プロファイルごとの違いはありません。</span><span class="sxs-lookup"><span data-stu-id="07463-112">The workflow for creating device profiles is similar for all profiles.</span></span> <span data-ttu-id="07463-113">Microsoft Intune のデバイス構成プロファイルの詳細については、[こちら](device-profile-create.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07463-113">Read [How to create Microsoft Intune device configuration profiles](device-profile-create.md) for information.</span></span> <span data-ttu-id="07463-114">その後は、各種プロファイル向けの設定の具体的な作成方法について読み進めてください。</span><span class="sxs-lookup"><span data-stu-id="07463-114">Then read on for specific information about creating settings for each profile type.</span></span>

<span data-ttu-id="07463-115">以下に挙げるデバイスの機能を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="07463-115">You can manage the following capabilities on your devices:</span></span>

## <a name="device-features"></a><span data-ttu-id="07463-116">デバイスの機能</span><span class="sxs-lookup"><span data-stu-id="07463-116">Device features</span></span>

<span data-ttu-id="07463-117">デバイス機能では、AirPrint、通知、共有デバイス構成など、iOS デバイスと macOS デバイスの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="07463-117">Device features let you control features on iOS and macOS devices like AirPrint, notifications, and shared device configurations.</span></span>
<span data-ttu-id="07463-118">詳細については、「[How to configure device feature settings in Microsoft Intune](device-features-configure.md)」 (Microsoft Intune でデバイスの機能設定を構成する方法) で iOS と macOS のサポートに関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07463-118">For more information, see [How to configure device feature settings](device-features-configure.md) Supports: iOS and macOS.</span></span>

## <a name="device-restrictions"></a><span data-ttu-id="07463-119">デバイスの制限</span><span class="sxs-lookup"><span data-stu-id="07463-119">Device restrictions</span></span>
<span data-ttu-id="07463-120">デバイスの制限では、セキュリティ、ハードウェア、データ共有設定を含む広範なカテゴリにわたって、管理対象のさまざまなデバイス設定を制御できます。</span><span class="sxs-lookup"><span data-stu-id="07463-120">Device restrictions let you control many settings on devices you manage across categories including security, hardware, and data sharing settings.</span></span> <span data-ttu-id="07463-121">たとえば、iOS デバイスのユーザーがデバイスのカメラにアクセスできないようにするデバイスの制限プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="07463-121">For example, you could create a device restriction profile that prevents users of iOS devices from accessing the device camera.</span></span>
<span data-ttu-id="07463-122">詳細については、[デバイス制限設定の構成方法](device-restrictions-configure.md)に関するページを参照してください。サポート対象: Android、iOS、macOS、Windows 10、Windows 10 Team。</span><span class="sxs-lookup"><span data-stu-id="07463-122">For more information, see [How to configure device restriction settings](device-restrictions-configure.md) Supports: Android, iOS, macOS, Windows 10, and Windows 10 Team.</span></span>

## <a name="email"></a><span data-ttu-id="07463-123">電子メール</span><span class="sxs-lookup"><span data-stu-id="07463-123">Email</span></span>
<span data-ttu-id="07463-124">電子メール プロファイルを使用すると、管理対象とするデバイスの Exchange ActiveSync 電子メール設定の作成、割り当て、監視を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="07463-124">Email profiles let you create, assign, and monitor Exchange ActiveSync email settings on devices you manage.</span></span> <span data-ttu-id="07463-125">電子メール プロファイルにより、一貫性の確保とサポート負荷の軽減が可能になり、エンド ユーザーは自分では何の設定もせずに個人デバイスで会社の電子メールにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="07463-125">Email profiles help ensure consistency, reduce support calls, and let end-users access company email on their personal devices without any required setup on their part.</span></span>
<span data-ttu-id="07463-126">詳細については、[電子メール設定の構成方法](email-settings-configure.md)に関するページを参照してください。サポート対象: Android、iOS、Windows Phone 8.1、Windows 10。</span><span class="sxs-lookup"><span data-stu-id="07463-126">For more information, see [How to configure email settings](email-settings-configure.md) Supports: Android, iOS, Windows Phone 8.1, and Windows 10.</span></span>

## <a name="wi-fi"></a><span data-ttu-id="07463-127">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="07463-127">Wi-Fi</span></span>
<span data-ttu-id="07463-128">Wi-Fi プロファイルを使用すると、ワイヤレス ネットワーク設定を組織内のユーザーとデバイスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="07463-128">Use Wi-Fi profiles to assign wireless network settings to users and devices in your organization.</span></span> <span data-ttu-id="07463-129">Wi-Fi プロファイルを割り当てると、ユーザーはプロファイルを構成することなく、会社の Wi-Fi にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="07463-129">When you assign a Wi-Fi profile, your users get access to your corporate Wi-Fi without having to configure it themselves.</span></span>
<span data-ttu-id="07463-130">詳細については、[Wi-Fi 設定の構成方法](wi-fi-settings-configure.md)に関するページを参照してください。サポート対象: Android、iOS、macOS、Windows 8.1 (インポートのみ)。</span><span class="sxs-lookup"><span data-stu-id="07463-130">For more information, see [How to configure Wi-Fi settings](wi-fi-settings-configure.md) Supports: Android, iOS, macOS, and Windows 8.1 (import only).</span></span>

## <a name="vpn"></a><span data-ttu-id="07463-131">VPN</span><span class="sxs-lookup"><span data-stu-id="07463-131">VPN</span></span>
<span data-ttu-id="07463-132">仮想プライベート ネットワーク (VPN) を使用すると、会社のユーザーが社内ネットワークにリモート アクセスする際にセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="07463-132">Virtual private networks (VPNs) give your users secure remote access to your company network.</span></span> <span data-ttu-id="07463-133">デバイスは、VPN 接続プロファイルを使用して、VPN サーバーとの接続を開始します。</span><span class="sxs-lookup"><span data-stu-id="07463-133">Devices use a VPN connection profile to initiate a connection with the VPN server.</span></span> <span data-ttu-id="07463-134">VPN プロファイルを組織内のユーザーとデバイスに割り当てることで、社内ネットワークに簡単かつ安全に接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="07463-134">Assign VPN profiles to users and devices in your organization, so they can easily and securely connect to the network.</span></span>
<span data-ttu-id="07463-135">詳細については、[VPN 設定の構成方法](vpn-settings-configure.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07463-135">For more information, see [How to configure VPN settings](vpn-settings-configure.md).</span></span>
<span data-ttu-id="07463-136">サポート対象: Android、iOS、macOS、Windows Phone 8.1、Windows 8.1、Windows 10。</span><span class="sxs-lookup"><span data-stu-id="07463-136">Supports: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1, and Windows 10.</span></span>

## <a name="education"></a><span data-ttu-id="07463-137">教育</span><span class="sxs-lookup"><span data-stu-id="07463-137">Education</span></span>
<span data-ttu-id="07463-138">Windows テスト アプリのオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="07463-138">Lets you configure options for the Windows Take a Test app.</span></span> <span data-ttu-id="07463-139">これらのオプションを構成するとき、テストが完了するまで他のアプリをデバイスで実行できません。</span><span class="sxs-lookup"><span data-stu-id="07463-139">When you configure these options, no other apps can run on the device until the test is complete.</span></span>
<span data-ttu-id="07463-140">詳細については、[教育設定の構成方法](education-settings-configure.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07463-140">For more information, see [How to configure education settings](education-settings-configure.md)</span></span>

## <a name="certificates"></a><span data-ttu-id="07463-141">証明書</span><span class="sxs-lookup"><span data-stu-id="07463-141">Certificates</span></span>
<span data-ttu-id="07463-142">この種類のプロファイルでは、デバイスに割り当てて Wi-Fi、VPN、電子メール プロファイルの認証に利用できる、信頼済み証明書、SCEP 証明書、PKCS 証明書を構成できます。</span><span class="sxs-lookup"><span data-stu-id="07463-142">This profile type lets you configure trusted, SCEP, and PKCS certificates that can be assigned to devices and used to authenticate Wi-Fi, VPN, and email profiles.</span></span>
<span data-ttu-id="07463-143">詳細については、[証明書の構成方法](certificates-configure.md)に関するページを参照してください。サポート対象: Android、iOS、Windows Phone 8.1、Windows 8.1、Windows 10。</span><span class="sxs-lookup"><span data-stu-id="07463-143">For more information, see [How to configure certificates](certificates-configure.md) Supports: Android, iOS, Windows Phone 8.1, Windows 8.1, and Windows 10.</span></span>

## <a name="edition-upgrade"></a><span data-ttu-id="07463-144">エディションのアップグレード</span><span class="sxs-lookup"><span data-stu-id="07463-144">Edition upgrade</span></span>
<span data-ttu-id="07463-145">この種類のプロファイルを使用して、Windows 10 のいずれかのバージョンを実行するデバイスを自動的に新しいエディションにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="07463-145">This profile type lets you automatically upgrade devices that run some versions of Windows 10 to a newer edition.</span></span>
<span data-ttu-id="07463-146">詳細については、[Windows 10 エディションのアップグレードを構成する方法](edition-upgrade-configure-windows-10.md)に関するページを参照してください。サポート対象: Windows 10 のみ。</span><span class="sxs-lookup"><span data-stu-id="07463-146">For more information, see [How to configure Windows 10 edition upgrades](edition-upgrade-configure-windows-10.md) Supports: Windows 10 only.</span></span>

## <a name="endpoint-protection"></a><span data-ttu-id="07463-147">Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="07463-147">Endpoint protection</span></span>
<span data-ttu-id="07463-148">この種類のプロファイルでは、Windows 10 デバイスの BitLocker と Windows Defender の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="07463-148">This profile type lets you configure BitLocker and Windows Defender settings for Windows 10 devices.</span></span>
<span data-ttu-id="07463-149">詳細については、[Windows 10 での Endpoint Protection 設定](endpoint-protection-windows-10.md)に関するページを参照してください。サポート対象: Windows 10 のみ。</span><span class="sxs-lookup"><span data-stu-id="07463-149">For more information, see [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md) Supports: Windows 10 only.</span></span>

## <a name="windows-information-protection"></a><span data-ttu-id="07463-150">Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="07463-150">Windows Information Protection</span></span>
<span data-ttu-id="07463-151">Windows 情報保護はデータ漏えいの防止に役立ち、それ以外の目的で従業員のエクスペリエンスを妨げることはありません。</span><span class="sxs-lookup"><span data-stu-id="07463-151">Windows Information Protection helps to protect against data leakage without otherwise interfering with the employee experience.</span></span> <span data-ttu-id="07463-152">また、企業が所有するデバイスと従業員が作業のために持ち込む個人用デバイスでもエンタープライズ アプリとデータを偶発的なデータ漏えいから保護します。既存の環境や他のアプリを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="07463-152">It also helps to protect enterprise apps and data against accidental data leaks on enterprise-owned devices and personal devices that employees bring to work without requiring changes to your environment or other apps.</span></span>
<span data-ttu-id="07463-153">詳細については、[Windows 情報保護の構成方法](windows-information-protection-configure.md)に関するページを参照してください。サポート対象: Windows 10 のみ。</span><span class="sxs-lookup"><span data-stu-id="07463-153">For more information, see [How to configure Windows Information Protection](windows-information-protection-configure.md) Supports: Windows 10 only.</span></span>

## <a name="custom"></a><span data-ttu-id="07463-154">カスタム</span><span class="sxs-lookup"><span data-stu-id="07463-154">Custom</span></span>
<span data-ttu-id="07463-155">カスタム設定により、Intune に組み込まれていないデバイス設定を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="07463-155">Custom settings let you assign device settings that are not built-into Intune.</span></span> <span data-ttu-id="07463-156">たとえば、Android デバイスでは、デバイスを構成する OMA-URI 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="07463-156">For example, on Android devices, you can specify OMA-URI values that configure the device.</span></span> <span data-ttu-id="07463-157">iOS デバイスの場合は、Apple Configurator で作成した構成ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="07463-157">For iOS devices, you can import a configuration file you created in the Apple Configurator.</span></span>
<span data-ttu-id="07463-158">詳細については、[カスタム設定の構成方法](custom-settings-configure.md)に関するページを参照してください。サポート対象: Android、iOS、macOS、Windows Phone 8.1。</span><span class="sxs-lookup"><span data-stu-id="07463-158">For more information, see [How to configure custom settings](custom-settings-configure.md) Supports: Android, iOS, macOS, and Windows Phone 8.1.</span></span>

## <a name="next-steps"></a><span data-ttu-id="07463-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="07463-159">Next steps</span></span>
<span data-ttu-id="07463-160">一覧からいずれかの種類のプロファイルを選択して、デバイスの構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="07463-160">Choose one of the profile types from the list to get started configuring devices.</span></span>
