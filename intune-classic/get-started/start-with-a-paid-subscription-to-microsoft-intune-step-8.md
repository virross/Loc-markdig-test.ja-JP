---
title: "デバイスの登録を可能にする"
description: "MDM 機関を設定し、iOS、Windows、Android、および Mac の各デバイスの登録を有効にします。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 002e5fce15be54be6f03c9853cbc2ca0df6d10e2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enable-enrollment-for-mobile-devices"></a><span data-ttu-id="1a20a-103">モバイル デバイスの登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="1a20a-103">Enable enrollment for mobile devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1a20a-104">このトピックでは、Intune 管理者がモバイル デバイスの登録を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a20a-104">This topic describes how an Intune administrator can enable mobile device enrollment.</span></span> <span data-ttu-id="1a20a-105">電話で Intune の使用する際のヘルプについては、[管理デバイスを使用した作業の完了](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a20a-105">For help using Intune on your phone, see [using managed devices to get work done](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).</span></span>

<span data-ttu-id="1a20a-106">Intune でモバイル デバイス管理をセットアップするには、まず、*モバイル デバイス管理機関*を設定する必要があります。この機関は、アカウントに関連付けられているデバイスを管理できるサービスを特定します。</span><span class="sxs-lookup"><span data-stu-id="1a20a-106">To set up mobile device management with Intune, you must first set the *mobile device management authority*, which identifies the service that can manage devices associated with your account.</span></span> <span data-ttu-id="1a20a-107">このガイダンスでは、System Center Configuration Manager ではなく、Intune サービスを使用することを想定します。</span><span class="sxs-lookup"><span data-stu-id="1a20a-107">This guidance assumes you will use the Intune service instead of System Center Configuration Manager.</span></span> <span data-ttu-id="1a20a-108">MDM 機関を設定したら、デバイス プラットフォームの管理を有効にし、デバイスをポータル サイト アプリに登録できます。</span><span class="sxs-lookup"><span data-stu-id="1a20a-108">Once the MDM authority is set, you can enable management for device platforms, and enroll your devices with the Company Portal app.</span></span>

## <a name="enable-device-enrollment"></a><span data-ttu-id="1a20a-109">デバイスの登録を可能にする</span><span class="sxs-lookup"><span data-stu-id="1a20a-109">Enable device enrollment</span></span>

1. <span data-ttu-id="1a20a-110">**Intune をモバイル デバイス管理機関にする** [Intune 管理コンソール](https://manage.microsoft.com/)で、**[管理者]** > **[モバイル デバイス管理]** の順に選択し、**[タスク]** で **[MDM 機関の設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a20a-110">**Make Intune your mobile device management authority** In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** > **Mobile Device Management**, and then choose **Set MDM Authority** under **Tasks**.</span></span>  

2. <span data-ttu-id="1a20a-111">MDM 機関ダイアログ ボックスで **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a20a-111">Choose **Yes** in the MDM Authority dialog box.</span></span>

    ![管理コンソール。](../media/intune-mdm-authority.png)

## <a name="choose-how-to-enroll-devices"></a><span data-ttu-id="1a20a-114">デバイスの登録方法の選択</span><span class="sxs-lookup"><span data-stu-id="1a20a-114">Choose how to enroll devices</span></span>

<span data-ttu-id="1a20a-115">Intune では、会社の要件に応じて、さまざまな方法でデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1a20a-115">Intune can manage devices in a variety of ways depending upon your company's requirements.</span></span> <span data-ttu-id="1a20a-116">使用できる登録シナリオは "Bring Your Own Device" (BYOD)、企業所有デバイス、"Choose Your Own Device" (CYOD)、およびキオスク モード デバイスです。</span><span class="sxs-lookup"><span data-stu-id="1a20a-116">"Bring your own device" (BYOD), corpoarte-owned devices, "choose your own device" (CYOD), and kiosk-mode devices are just a few available enrollment scenarios.</span></span>

<span data-ttu-id="1a20a-117">以下の手順に従って、[デバイスの登録方法を選択](choose-how-to-enroll-devices1.md)します。</span><span class="sxs-lookup"><span data-stu-id="1a20a-117">Follow these steps to [Choose how to enroll devices](choose-how-to-enroll-devices1.md).</span></span>

## <a name="enable-mdm-for-your-device-platform"></a><span data-ttu-id="1a20a-118">デバイス プラットフォームの MDM を有効にする</span><span class="sxs-lookup"><span data-stu-id="1a20a-118">Enable MDM for your device platform</span></span>
<span data-ttu-id="1a20a-119">プラットフォーム プロバイダーと Intune テナント間の関係を確立して、iOS、Mac、および Android for Work デバイスの登録を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a20a-119">Enrollment must be enabled for iOS, Mac, and Android for Work devices establishing a relationship between the platform provider and your Intune tenant.</span></span> <span data-ttu-id="1a20a-120">Windows および Android デバイスには追加の手順は必要ありませんが、Windows デバイスの場合、特別な DNS レジストリ エントリを作成して、ユーザーのデバイス登録を簡略化することができます。</span><span class="sxs-lookup"><span data-stu-id="1a20a-120">Windows and Android devices do not require additional steps, but for Windows devices you can simplify device enrollment for your users by creating a special DNS registry entry.</span></span>

<span data-ttu-id="1a20a-121">管理対象のデバイス プラットフォームに対してデバイス管理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1a20a-121">Enable device enrollment for the device platform you want to manage.</span></span> <span data-ttu-id="1a20a-122">要件はプラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1a20a-122">Depending on your platform, different requirements are needed:</span></span>

- [<span data-ttu-id="1a20a-123">iOS と macOS</span><span class="sxs-lookup"><span data-stu-id="1a20a-123">iOS and macOS</span></span>](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [<span data-ttu-id="1a20a-124">Windows 10 および Windows Phone</span><span class="sxs-lookup"><span data-stu-id="1a20a-124">Window 10 and Windows Phone</span></span>](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- <span data-ttu-id="1a20a-125">[Window PC](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (Intune ソフトウェア クライアント)</span><span class="sxs-lookup"><span data-stu-id="1a20a-125">[Window PC](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (Intune software client)</span></span>
- [<span data-ttu-id="1a20a-126">Android for Work</span><span class="sxs-lookup"><span data-stu-id="1a20a-126">Android for Work</span></span>](/intune-classic/deploy-use/set-up-android-for-work)

<span data-ttu-id="1a20a-127">登録が有効になったら、ユーザーは自分のデバイスにポータル サイト アプリをダウンロードして、デバイス登録プロセスを完了できます。</span><span class="sxs-lookup"><span data-stu-id="1a20a-127">Once enrollment is enabled, users can download the Company Portal app to their device and complete the device enrollment process.</span></span>

### <a name="enable-company-owned-device-enrollment"></a><span data-ttu-id="1a20a-128">会社所有のデバイス登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="1a20a-128">Enable company-owned device enrollment</span></span>
<span data-ttu-id="1a20a-129">次のような、[会社所有のデバイス登録](/intune-classic/deploy-use/manage-corporate-owned-devices)シナリオを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1a20a-129">You can also enable a variety of [company-owned device enrollment](/intune-classic/deploy-use/manage-corporate-owned-devices) scenarios including:</span></span>
- [<span data-ttu-id="1a20a-130">Apple Device Enrollment Program</span><span class="sxs-lookup"><span data-stu-id="1a20a-130">Apple Device Enrollment Program</span></span>](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [<span data-ttu-id="1a20a-131">Apple Configurator セットアップ アシスタントでの登録</span><span class="sxs-lookup"><span data-stu-id="1a20a-131">Apple Configurator Setup Assistant enrollment</span></span>](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [<span data-ttu-id="1a20a-132">Apple Configurator の直接登録</span><span class="sxs-lookup"><span data-stu-id="1a20a-132">Apple Configurator direct enrollment</span></span>](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [<span data-ttu-id="1a20a-133">デバイス登録マネージャー</span><span class="sxs-lookup"><span data-stu-id="1a20a-133">Device Enrollment Manager</span></span>](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a><span data-ttu-id="1a20a-134">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1a20a-134">Next steps</span></span>
<span data-ttu-id="1a20a-135">これで終了です。</span><span class="sxs-lookup"><span data-stu-id="1a20a-135">Congratulations!</span></span> <span data-ttu-id="1a20a-136">*Intune のクイック スタート ガイド*の最後の手順が完了しました。</span><span class="sxs-lookup"><span data-stu-id="1a20a-136">You have just completed the last step of the *Intune quick start guide*.</span></span> <span data-ttu-id="1a20a-137">これで初期構成が完了したので、追加の MDM 機能の有効化を検討できます。</span><span class="sxs-lookup"><span data-stu-id="1a20a-137">Now that your initial configuration is complete, you can consider enabling additional MDM functionality.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1a20a-138">[&larr; **デバイスを登録する**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**構成後のタスク** &rarr;](.\post-configuration-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="1a20a-138">[&larr; **Enroll devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Post-configuration tasks** &rarr;](.\post-configuration-tasks.md)</span></span>  
