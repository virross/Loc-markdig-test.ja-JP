---
title: "Intune で Windows デバイスの登録方法を選択する"
titlesuffix: Azure portal
description: "Microsoft Intune で Windows デバイスの登録を設定する方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 307f4b8d5ba27ce8136569e0c58711f9b1364d93
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-ios-devices-in-intune"></a><span data-ttu-id="6e761-103">Intune で iOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="6e761-103">Enroll iOS devices in Intune</span></span>

<span data-ttu-id="6e761-104">Intune では、iPad および iPhone のモバイル デバイス管理 (MDM) が有効になり、会社の電子メールおよびアプリへのアクセス権がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="6e761-104">Intune enables mobile device management (MDM) of iPads and iPhones to give users access to company email and apps.</span></span>

<span data-ttu-id="6e761-105">Intune 管理者として、iOS デバイスの登録を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6e761-105">As an Intune admin, you can enable enrollment for iOS devices.</span></span> <span data-ttu-id="6e761-106">"Bring Your Own Device" (BYOD) の登録と呼ばれる、個人所有のデバイスをユーザーが登録することを許可できます。</span><span class="sxs-lookup"><span data-stu-id="6e761-106">You can allow users to enroll personally owned devices, known as "bring your own device" (BYOD) enrollment.</span></span> <span data-ttu-id="6e761-107">会社所有デバイスの登録を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6e761-107">You can also enable enrollment of company-owned devices.</span></span>

## <a name="prerequisites-for-ios-enrollment"></a><span data-ttu-id="6e761-108">iOS の登録の前提条件</span><span class="sxs-lookup"><span data-stu-id="6e761-108">Prerequisites for iOS enrollment</span></span>
<span data-ttu-id="6e761-109">iOS デバイスを有効にする前に、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e761-109">Before you can enable iOS devices, complete the following steps:</span></span>
- <span data-ttu-id="6e761-110">[Intune のセットアップ](setup-steps.md) - この手順で、Intune インフラストラクチャをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="6e761-110">[Set up Intune](setup-steps.md) - These steps set up your Intune infrastructure.</span></span> <span data-ttu-id="6e761-111">特に、デバイスの登録には [MDM 機関を設定する](mdm-authority-set.md)必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e761-111">In particular, device enrollment requires that you [set your MDM authority](mdm-authority-set.md).</span></span>
- <span data-ttu-id="6e761-112">[Apple MDM プッシュ通知証明書の取得](apple-mdm-push-certificate-get.md) - Apple では、iOS および macOS デバイスの管理を有効にするために証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="6e761-112">[Get an Apple MDM Push certificate](apple-mdm-push-certificate-get.md) - Apple requires a certificate to enable management of iOS and macOS devices.</span></span>

## <a name="user-owned-ios-devices-byod"></a><span data-ttu-id="6e761-113">ユーザー所有の iOS デバイス (BYOD)</span><span class="sxs-lookup"><span data-stu-id="6e761-113">User-owned iOS devices (BYOD)</span></span>

<span data-ttu-id="6e761-114">Intune 管理のために、ユーザーに個人用デバイスを登録させることができます。これは "Bring Your Own Device" (BYOD) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6e761-114">You can let users enroll their personal devices for Intune management, know as "bring your own device" or BYOD.</span></span> <span data-ttu-id="6e761-115">前提条件を満たし、ユーザーのライセンスを割り当てたら、アプリ ストアから iOS ポータル サイト アプリをダウンロードして、アプリの登録手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6e761-115">Once you've completed the prerequisites and assigned users licenses, they can download the iOS Company Portal app from the App Store, and follow enrollment instructions in the app.</span></span>

## <a name="company-owned-ios-devices"></a><span data-ttu-id="6e761-116">会社所有の iOS デバイス</span><span class="sxs-lookup"><span data-stu-id="6e761-116">Company-owned iOS devices</span></span>
<span data-ttu-id="6e761-117">Intune は、ユーザーのデバイスを購入する組織のため、次の会社所有の iOS デバイスの登録方法をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6e761-117">For organizations that purchase devices for their users, Intune supports the following iOS company-owned device enrollment methods:</span></span>

- <span data-ttu-id="6e761-118">Apple の Device Enrollment Program (DEP)</span><span class="sxs-lookup"><span data-stu-id="6e761-118">Apple's Device Enrollment Program (DEP)</span></span>
- <span data-ttu-id="6e761-119">Apple School Manager</span><span class="sxs-lookup"><span data-stu-id="6e761-119">Apple School Manager</span></span>
- <span data-ttu-id="6e761-120">Apple Configurator セットアップ アシスタントでの登録</span><span class="sxs-lookup"><span data-stu-id="6e761-120">Apple Configurator Setup Assistant enrollment</span></span>
- <span data-ttu-id="6e761-121">Apple Configurator の直接登録</span><span class="sxs-lookup"><span data-stu-id="6e761-121">Apple Configurator direct enrollment</span></span>

<span data-ttu-id="6e761-122">[デバイス登録マネージャー](device-enrollment-manager-enroll.md)のアカウントで会社所有の iOS デバイスを登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e761-122">You can also enroll company-owned iOS devices with a [device enrollment manager](device-enrollment-manager-enroll.md) account.</span></span>

## <a name="device-enrollment-program"></a><span data-ttu-id="6e761-123">デバイス登録プログラム</span><span class="sxs-lookup"><span data-stu-id="6e761-123">Device Enrollment Program</span></span>
<span data-ttu-id="6e761-124">組織は、Apple の Device Enrollment Program (DEP) を通して iOS デバイスを購入できます。</span><span class="sxs-lookup"><span data-stu-id="6e761-124">Organizations can purchase iOS devices through Apple's Device Enrollment Program (DEP).</span></span> <span data-ttu-id="6e761-125">DEP では、登録プロファイルを “無線で” 展開して、デバイスを管理対象として登録できます。</span><span class="sxs-lookup"><span data-stu-id="6e761-125">DEP lets you deploy an enrollment profile “over the air” to bring devices into management.</span></span> <span data-ttu-id="6e761-126">詳細については、[Device Enrollment Program](device-enrollment-program-enroll-ios.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e761-126">Learn more about [Device Enrollment Program](device-enrollment-program-enroll-ios.md).</span></span>

## <a name="apple-school-manager"></a><span data-ttu-id="6e761-127">Apple School Manager</span><span class="sxs-lookup"><span data-stu-id="6e761-127">Apple School Manager</span></span>
<span data-ttu-id="6e761-128">Apple School Manager は、学校向けのデバイス購入と登録プログラムです。</span><span class="sxs-lookup"><span data-stu-id="6e761-128">Apple School Manager is a device purchase and enrollment program for schools.</span></span> <span data-ttu-id="6e761-129">DEP と同様に、プロファイルを展開して管理にデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="6e761-129">Like DEP, you can deploy a profile to enroll devices in management.</span></span> <span data-ttu-id="6e761-130">詳細については、[Apple School Manager](apple-school-manager-set-up-ios.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e761-130">Learn more about [Apple School Manager](apple-school-manager-set-up-ios.md).</span></span>

## <a name="apple-configurator"></a><span data-ttu-id="6e761-131">Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="6e761-131">Apple Configurator</span></span>
<span data-ttu-id="6e761-132">Mac コンピューターで実行している Apple Configurator を使って、iOS デバイスを登録することができます。</span><span class="sxs-lookup"><span data-stu-id="6e761-132">You can enroll iOS devices with Apple Configurator running on a Mac computer.</span></span> <span data-ttu-id="6e761-133">デバイスを準備するには、デバイスを USB 接続して、登録プロファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6e761-133">To prepare devices, you USB-connect them and install an enrollment profile.</span></span> <span data-ttu-id="6e761-134">Apple Configurator では、次の 2 つの方法でデバイスを登録することができます。</span><span class="sxs-lookup"><span data-stu-id="6e761-134">You can enroll devices with Apple Configurator in two ways:</span></span>
- <span data-ttu-id="6e761-135">セットアップ アシスタントの登録 - デバイスを工場出荷時の設定にリセットし、セットアップ アシスタントを実行する準備を行い、デバイスの新しいユーザー用に会社のポリシーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6e761-135">Setup Assistant enrollment - Factory resets the device, prepares it to run Setup Assistant, and installs the company's policies for the device’s new user.</span></span>
- <span data-ttu-id="6e761-136">直接登録 - デバイスを工場出荷時の設定に戻さず、定義済みのポリシーでデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="6e761-136">Direct enrollment - Does not factory-reset the device and enrolls the device with a predefined policy.</span></span> <span data-ttu-id="6e761-137">この方法は、ユーザー アフィニティなしのデバイス向けです。</span><span class="sxs-lookup"><span data-stu-id="6e761-137">This method is for devices with no user affinity.</span></span>

<span data-ttu-id="6e761-138">詳細については、[Apple Configurator の登録](apple-configurator-setup-assistant-enroll-ios.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e761-138">Learn more about [Apple Configurator enrollment](apple-configurator-setup-assistant-enroll-ios.md).</span></span>
