---
title: "企業所有のデバイスの管理"
description: "企業所有のデバイスを、デバイスの種類、購入方法、組織のニーズに応じて、さまざまな方法で登録します。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 852c69fe1b6a718154e17a6f0a87fe6cac3c81f2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-corporate-owned-devices-by-using-intune"></a><span data-ttu-id="6cee3-103">Intune を使用して企業所有のデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="6cee3-103">Enroll corporate-owned devices by using Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="6cee3-104">組織所有または企業所有のデバイスを登録し、デバイスの種類、デバイスの購入方法、組織のニーズに応じて、さまざまな方法により Intune で管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-104">You can enroll organization-owned or corporate-owned devices to manage with Intune in a variety of ways, depending on the type of device, how the device was purchased, and the needs of the organization.</span></span> <span data-ttu-id="6cee3-105">また、ポータル サイト アプリをインストールし、"Bring Your Own Device" (BYOD) シナリオのように、企業所有のデバイスを登録して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-105">You also can install the Company Portal app to enroll and manage corporate-owned devices, like in a "bring your own device" (BYOD) scenario.</span></span>

<span data-ttu-id="6cee3-106">既定では、すべてのプラットフォーム用のデバイスを Intune に登録することができます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-106">By default, devices for all platforms are allowed to enroll in Intune.</span></span> <span data-ttu-id="6cee3-107">デバイスの登録をブロックするには、管理者資格情報を使用して [Microsoft Intune 管理ポータル](https://manage.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6cee3-107">To block devices from enrolling, sign to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials.</span></span> <span data-ttu-id="6cee3-108">**[管理]** > **[モバイル デバイス管理]** > **[登録ルール]** の順に選択し、登録をブロックするプラットフォームの該当するチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="6cee3-108">Choose **Admin** > **Mobile Device Management** > **Enrollment Rules** and then clear the applicable check boxes for the platforms that you want to block.</span></span>

## <a name="enroll-corporate-owned-ios-devices"></a><span data-ttu-id="6cee3-109">企業所有の iOS デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="6cee3-109">Enroll corporate-owned iOS devices</span></span>

<span data-ttu-id="6cee3-110">企業所有デバイスの登録方法は、"Choose Your Own Device" (CYOD) シナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="6cee3-110">Corporate-owned device enrollment methods are a good choice for "choose your own device" (CYOD) scenarios.</span></span> <span data-ttu-id="6cee3-111">CYOD 環境では、組織はユーザーが選択したデバイスに対する支払いと管理を行います。</span><span class="sxs-lookup"><span data-stu-id="6cee3-111">In a CYOD environment, the organization pays for a device that the user selects, and the organization manages the device.</span></span>

<span data-ttu-id="6cee3-112">ユーザーが複数の iOS デバイスから選択できるようにすれば、登録を事前に構成できるため、デバイスはユーザーが初めてオンにした時点から Intune で管理されます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-112">If you offer users iOS devices to choose from, you can preconfigure enrollment so that the device is managed with Intune from the first time the user turns it on.</span></span> <span data-ttu-id="6cee3-113">Intune は、[Apple のデバイス登録プログラム (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) による登録、または Mac コンピューター上の Apple Configurator ツールを使用した[直接](ios-direct-enrollment-in-microsoft-intune.md)登録、または[セットアップ アシスタント](ios-setup-assistant-enrollment-in-microsoft-intune.md)による登録をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6cee3-113">Intune supports enrollment via the [Apple Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md), or by using the Apple Configurator tool on a Mac computer for [direct](ios-direct-enrollment-in-microsoft-intune.md) or [Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) enrollment.</span></span>

<span data-ttu-id="6cee3-114">企業所有の iOS デバイスの登録方法については、[こちら](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cee3-114">Learn how to [enroll corporate-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span></span>

## <a name="create-a-device-enrollment-manager-account"></a><span data-ttu-id="6cee3-115">デバイス登録マネージャー アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="6cee3-115">Create a device enrollment manager account</span></span>

<span data-ttu-id="6cee3-116">Intune で単一のユーザー デバイス登録マネージャー (DEM) アカウントを作成し、組織の多数のモバイル デバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-116">You can create a single-user device enrollment manager (DEM) account in Intune to manage a large number of mobile devices for your organization.</span></span> <span data-ttu-id="6cee3-117">DEM アカウントを作成すると、指定されたアカウント マネージャーは、標準ユーザーが登録できる 15 台を超えるデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-117">After you create a DEM account, a designated account manager can enroll more than the 15 devices that a standard user can enroll.</span></span>

<span data-ttu-id="6cee3-118">DEM アカウントを使用すれば、単一の特定ユーザーが使用していないデバイスのみを登録することできます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-118">You can use a DEM account to enroll only devices that aren't used by a single, specific user.</span></span> <span data-ttu-id="6cee3-119">この種のデバイスは、POS アプリやユーティリティ アプリなどには適していますが、電子メールや会社のリソースにアクセスする必要があるユーザーには適していません。</span><span class="sxs-lookup"><span data-stu-id="6cee3-119">Those types of devices are good for point-of-sale or utility apps, for example, but not for users who need to access email or company resources.</span></span>

<span data-ttu-id="6cee3-120">[DEM アカウントを使用して企業所有のデバイスを登録する方法については、こちら](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cee3-120">Learn how to [enroll corporate-owned devices by using a DEM account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).</span></span>

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a><span data-ttu-id="6cee3-121">企業所有の Windows 10 Enterprise デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="6cee3-121">Enroll corporate-owned Windows 10 Enterprise devices</span></span>

<span data-ttu-id="6cee3-122">組織で Azure Active Directory Premium または Microsoft Enterprise Mobility Suite を使用している場合は、[Windows 10 Enterprise デバイスを登録](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)できます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-122">If you use Azure Active Directory Premium or Microsoft Enterprise Mobility Suite in your organization, you can [enroll Windows 10 Enterprise devices](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview).</span></span> <span data-ttu-id="6cee3-123">ユーザーがデバイスで職場または学校アカウントを追加すると、デバイスは自動的に "企業所有" としてタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-123">When a user adds a work or school account on a device, the device is automatically tagged as "corporate-owned."</span></span>

## <a name="import-imei-numbers"></a><span data-ttu-id="6cee3-124">IMEI 番号のインポート</span><span class="sxs-lookup"><span data-stu-id="6cee3-124">Import IMEI numbers</span></span>

<span data-ttu-id="6cee3-125">多くのモバイル デバイス製造元が、デバイスに IMEI (International Mobile Equipment Identity) という一意の番号を使用しています。</span><span class="sxs-lookup"><span data-stu-id="6cee3-125">Many mobile device manufacturers use a unique number called an International Mobile Equipment Identity (IMEI) on their devices.</span></span> <span data-ttu-id="6cee3-126">組織が所有するデバイスの IMEI 番号をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-126">You can import IMEI numbers for devices that your organization owns.</span></span> <span data-ttu-id="6cee3-127">デバイスが Intune の管理対象になると、企業所有のデバイスとしてタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-127">When the device becomes managed by Intune, it's tagged as a corporate-owned device.</span></span>

<span data-ttu-id="6cee3-128">IMEI 番号を使用して企業所有のデバイスにタグを付ける方法については、[こちら](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cee3-128">Learn how to [tag corporate-owned devices by using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).</span></span>

## <a name="identify-a-device-as-corporate-owned"></a><span data-ttu-id="6cee3-129">デバイスの企業所有としての識別</span><span class="sxs-lookup"><span data-stu-id="6cee3-129">Identify a device as corporate-owned</span></span>

<span data-ttu-id="6cee3-130">Intune は、次のいずれかの条件を満たす場合、デバイスを "企業" と認識します。</span><span class="sxs-lookup"><span data-stu-id="6cee3-130">Intune recognizes a device as "corporate" when any of the following conditions are true:</span></span>

 - <span data-ttu-id="6cee3-131">デバイスが [DEM アカウントを使用して登録](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)されている (すべてのプラットフォーム)。</span><span class="sxs-lookup"><span data-stu-id="6cee3-131">The device was [enrolled by using a DEM account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (all platforms).</span></span>
 - <span data-ttu-id="6cee3-132">デバイスが [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) または [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) を使用して登録されている (iOS のみ)。</span><span class="sxs-lookup"><span data-stu-id="6cee3-132">The device was enrolled by using the [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) or [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (iOS only).</span></span>
 - <span data-ttu-id="6cee3-133">デバイスの製造元が [IMEI 番号を使用してデバイスを事前に宣言している](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (IMEI 番号を使用するすべてのプラットフォーム)。</span><span class="sxs-lookup"><span data-stu-id="6cee3-133">The device manufacturer [predeclared the device by using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (all platforms with IMEI numbers).</span></span>
 - <span data-ttu-id="6cee3-134">デバイスが [Azure Active Directory または Enterprise Mobility Suite に Windows 10 Enterprise デバイスとして](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)登録されている (Windows 10 のみ)。</span><span class="sxs-lookup"><span data-stu-id="6cee3-134">The device is registered in [Azure Active Directory or Enterprise Mobility Suite as a Windows 10 Enterprise device](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (Windows 10 only).</span></span>

<span data-ttu-id="6cee3-135">デバイスに企業とタグが付けられると、管理コンソールのそのデバイス レコードの **[所有権]** 列に **[企業]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="6cee3-135">When a device is tagged as corporate, you see **Corporate** in the **Ownership** column for that device record in the administrator console.</span></span> 
