---
title: "企業所有の iOS デバイスの登録"
description: "Apple Device Enrollment Program (DEP) または Apple Configurator を使用した企業所有の iOS デバイスの登録"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1478d163f917f421e57e6192e373e994a0274769
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-corporate-owned-ios-devices-in-microsoft-intune"></a><span data-ttu-id="efb27-103">Microsoft Intune での企業所有の iOS デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="efb27-103">Enroll corporate-owned iOS devices in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="efb27-104">Microsoft Intune は、Mac コンピューターで実行される Apple Device Enrollment Program (DEP) または [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) ツールによる、企業所有の iOS デバイスの登録をサポートします。</span><span class="sxs-lookup"><span data-stu-id="efb27-104">Microsoft Intune supports the enrollment of corporate-owned iOS devices through the Apple Device Enrollment Program (DEP) or the [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer.</span></span>

<span data-ttu-id="efb27-105">**前提条件:** [Apple Push Notification Service 証明書](set-up-ios-and-mac-management-with-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="efb27-105">**Prerequisite:** An [Apple Push Notification service  certificate](set-up-ios-and-mac-management-with-microsoft-intune.md)</span></span>

<span data-ttu-id="efb27-106">企業登録対象の iOS デバイスは、次の 3 つの方法のいずれかを使用して登録することができます。</span><span class="sxs-lookup"><span data-stu-id="efb27-106">You can enroll corporate-enrolled iOS devices by using one of three methods:</span></span>

- <span data-ttu-id="efb27-107">Apple Configurator (セットアップ アシスタントまたは直接登録を使用)</span><span class="sxs-lookup"><span data-stu-id="efb27-107">Apple Configurator, using either Setup Assistant or direct enrollment</span></span>
- <span data-ttu-id="efb27-108">デバイス登録プログラム</span><span class="sxs-lookup"><span data-stu-id="efb27-108">Device enrollment program</span></span>
- <span data-ttu-id="efb27-109">ポータル サイト アプリ</span><span class="sxs-lookup"><span data-stu-id="efb27-109">Company Portal app</span></span>

>[!NOTE]
><span data-ttu-id="efb27-110">Apple Configurator とデバイス登録プログラムの登録方法は、[デバイス登録マネージャー](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)の方法と同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="efb27-110">The Apple Configurator and Device Enrollment Program enrollment methods can't be used with the [device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) method.</span></span>

<span data-ttu-id="efb27-111">既定では、すべての iOS デバイスを Intune に登録することができます。</span><span class="sxs-lookup"><span data-stu-id="efb27-111">By default, all iOS devices are allowed to enroll in Intune.</span></span> <span data-ttu-id="efb27-112">個人または会社所有のデバイスの登録をブロックするには、管理者資格情報を使用して [Microsoft Intune 管理ポータル](https://manage.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="efb27-112">To block personal or corporate-owned devices from enrolling, sign to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials.</span></span> <span data-ttu-id="efb27-113">**[管理]** > **[モバイル デバイス管理]** > **[登録ルール]** の順に選択し、該当するオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="efb27-113">Choose **Admin** > **Mobile Device Management** > **Enrollment Rules** and then clear the applicable options.</span></span>

## <a name="use-apple-configurator"></a><span data-ttu-id="efb27-114">Apple Configurator を使用する場合</span><span class="sxs-lookup"><span data-stu-id="efb27-114">Use Apple Configurator</span></span>

<span data-ttu-id="efb27-115">会社の登録プロファイルをエクスポートし、Apple Configurator を実行している Mac にモバイル デバイスを接続することで、iOS デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="efb27-115">You can enroll iOS devices by exporting a Corporate Enrollment profile and then connecting those mobile devices to a Mac that is running Apple Configurator.</span></span> <span data-ttu-id="efb27-116">Apple Configurator では、2 つの形式の登録がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="efb27-116">Apple Configurator supports two forms of enrollment:</span></span>

- <span data-ttu-id="efb27-117">**セットアップ アシスタントを使用した登録**: デバイスを出荷時の設定に戻し、デバイスの新しいユーザーがセットアップできるようにします。</span><span class="sxs-lookup"><span data-stu-id="efb27-117">**Setup Assistant enrollment**: Resets the device to factory settings and prepares it for setup by the device's new user.</span></span> <span data-ttu-id="efb27-118">この方法では、管理者は [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) を実行している Mac コンピューターに iOS デバイスを USB で接続して、登録を事前構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-118">This method requires the admin to connect the iOS device through USB to a Mac computer running [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) to preconfigure the enrollment.</span></span> <span data-ttu-id="efb27-119">その後、デバイスをユーザーに配布し、ユーザーがセットアップ アシスタント プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="efb27-119">Devices are then delivered to their users, who run the Setup Assistant process.</span></span> <span data-ttu-id="efb27-120">このプロセスで、デバイスを職場または学校の資格情報で構成し、登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="efb27-120">This process configures the device with their work or school credentials and completes the enrollment process.</span></span> <span data-ttu-id="efb27-121">詳しくは、[Apple Configurator とセットアップ アシスタントを使用した iOS デバイスの登録](ios-setup-assistant-enrollment-in-microsoft-intune.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb27-121">For more information, see [Enroll iOS devices using Apple Configurator and Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md).</span></span>

- <span data-ttu-id="efb27-122">**直接登録** - デバイスの準備で使用する Apple Configurator 準拠ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="efb27-122">**Direct enrollment**: Creates an Apple Configurator–compliant file for use during device preparation.</span></span> <span data-ttu-id="efb27-123">登録対象デバイスは出荷時の設定に戻されませんが、ユーザーの関連付け情報は含まれません。</span><span class="sxs-lookup"><span data-stu-id="efb27-123">The enrolled device isn’t factory reset, but it has no user affiliation.</span></span> <span data-ttu-id="efb27-124">この方法では、管理者は [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) を実行している Mac コンピューターに iOS デバイスを USB で接続して、デバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-124">This method requires the admin to connect the iOS device through USB to a Mac computer running [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) to enroll the device.</span></span> <span data-ttu-id="efb27-125">詳しくは、[Apple Configurator の直接登録を使用した iOS デバイスの登録](ios-direct-enrollment-in-microsoft-intune.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb27-125">For more information, see [Enroll iOS devices using Apple Configurator Direct Enrollment](ios-direct-enrollment-in-microsoft-intune.md).</span></span>

## <a name="use-the-device-enrollment-program-dep"></a><span data-ttu-id="efb27-126">Device Enrollment Program (DEP) のサポートを使用する場合</span><span class="sxs-lookup"><span data-stu-id="efb27-126">Use the Device Enrollment Program (DEP)</span></span>
<span data-ttu-id="efb27-127">DEP では、DEP を通じて購入したデバイスに "無線で" 登録プロファイルが展開されます。</span><span class="sxs-lookup"><span data-stu-id="efb27-127">DEP deploys an enrollment profile “over the air” to devices that are purchased through DEP.</span></span> <span data-ttu-id="efb27-128">ユーザーがデバイスでセットアップ アシスタントを実行すると、デバイスが Intune に登録されます。</span><span class="sxs-lookup"><span data-stu-id="efb27-128">When a user runs Setup Assistant on the device, the device is enrolled in Intune.</span></span> <span data-ttu-id="efb27-129">詳しくは、[Device Enrollment Program による iOS デバイスの登録](ios-device-enrollment-program-in-microsoft-intune.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb27-129">For more information, see [Enroll Device Enrollment Program iOS devices](ios-device-enrollment-program-in-microsoft-intune.md).</span></span>

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a><span data-ttu-id="efb27-130">DEP または Apple Configurator で登録されたデバイスでのポータル サイトの使用</span><span class="sxs-lookup"><span data-stu-id="efb27-130">Use the Company Portal on DEP-enrolled or Apple Configurator-enrolled devices</span></span>

<span data-ttu-id="efb27-131">ユーザー アフィニティが構成されたデバイスでは、ポータル サイト アプリをインストールして実行し、アプリをダウンロードしてデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="efb27-131">Devices that are configured with user affinity can install and run the Company Portal app to download apps and manage devices.</span></span> <span data-ttu-id="efb27-132">ユーザーは、デバイスを受け取った後、セットアップ アシスタントを完了してポータル サイト アプリをインストールするために、いくつもの追加の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-132">After users receive their devices, they must complete a number of additional steps to complete the Setup Assistant and install the Company Portal app.</span></span>

<span data-ttu-id="efb27-133">以下をサポートするには、ユーザー アフィニティが必要です。</span><span class="sxs-lookup"><span data-stu-id="efb27-133">User affinity is required to support the following:</span></span>
  - <span data-ttu-id="efb27-134">モバイル アプリケーション管理 (MAM) アプリ</span><span class="sxs-lookup"><span data-stu-id="efb27-134">Mobile application management (MAM) apps</span></span>
  - <span data-ttu-id="efb27-135">電子メールと会社データへの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="efb27-135">Conditional access to email and company data</span></span>
  - <span data-ttu-id="efb27-136">ポータル サイト アプリ</span><span class="sxs-lookup"><span data-stu-id="efb27-136">Company Portal app</span></span>

<span data-ttu-id="efb27-137">**ユーザー アフィニティありで企業所有 iOS デバイスを登録する方法**</span><span class="sxs-lookup"><span data-stu-id="efb27-137">**How users enroll corporate-owned iOS devices with user affinity**</span></span>
1. <span data-ttu-id="efb27-138">ユーザーは、デバイスの電源をオンにすると、セットアップ アシスタントを完了するように求められます。</span><span class="sxs-lookup"><span data-stu-id="efb27-138">When users turn on their device, they are prompted to complete the Setup Assistant.</span></span> <span data-ttu-id="efb27-139">セットアップ中にユーザーは資格情報を要求されます。</span><span class="sxs-lookup"><span data-stu-id="efb27-139">During setup, users are prompted for their credentials.</span></span> <span data-ttu-id="efb27-140">Intune のサブスクリプションに関連付けられている資格情報 (つまり一意の個人名または UPN) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-140">They must use the credentials (i.e. the unique personal name or UPN) that are associated with their subscription in Intune.</span></span>

2. <span data-ttu-id="efb27-141">セットアップ中にユーザーは Apple ID を要求されます。</span><span class="sxs-lookup"><span data-stu-id="efb27-141">During setup, users are prompted for an Apple ID.</span></span> <span data-ttu-id="efb27-142">デバイスでポータル サイトをインストールできるように、Apple ID を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-142">They must provide an Apple ID to allow the device to install the Company Portal.</span></span> <span data-ttu-id="efb27-143">この ID は、セットアップの完了後に iOS の設定メニューから入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="efb27-143">They can also provide the ID from the iOS settings menu after setup is finished.</span></span>

3. <span data-ttu-id="efb27-144">セットアップが完了したら、iOS デバイスで App Store からポータル サイト アプリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-144">After completing setup, the iOS device must install the Company Portal app from the App Store.</span></span>

4. <span data-ttu-id="efb27-145">これでユーザーは、デバイスを設定するときに使用した UPN を使用して、ポータル サイトにサインインできるようになります。</span><span class="sxs-lookup"><span data-stu-id="efb27-145">The user can now sign in to the Company Portal by using the UPN that they used when setting up the device.</span></span>

5. <span data-ttu-id="efb27-146">ユーザーはログインすると、デバイスを登録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="efb27-146">After logging in, the user is prompted to enroll their device.</span></span> <span data-ttu-id="efb27-147">最初の手順は、デバイスを指定することです。</span><span class="sxs-lookup"><span data-stu-id="efb27-147">The first step is to identify their device.</span></span> <span data-ttu-id="efb27-148">アプリには、ユーザーの Intune アカウントに割り当てられている企業登録済みの iOS デバイスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb27-148">The app presents a list of iOS devices that have already been corporate enrolled and assigned to the user’s Intune account.</span></span> <span data-ttu-id="efb27-149">一致するデバイスを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-149">They should choose the matching device.</span></span>

  <span data-ttu-id="efb27-150">ユーザーのデバイスがまだ企業登録済みでない場合は、**[新しいデバイス]** を選択して標準の登録フローを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-150">If this device is not already corporate enrolled, they should choose **new device** to continue with the standard enrollment flow.</span></span>

6. <span data-ttu-id="efb27-151">次の画面で、ユーザーは、新しいデバイスのシリアル番号を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-151">On the next screen, the user must confirm the serial number of the new device.</span></span> <span data-ttu-id="efb27-152">シリアル番号は、**[シリアル番号を確認]** リンクをタップして設定アプリを起動すると確認できます。</span><span class="sxs-lookup"><span data-stu-id="efb27-152">The user can tap the link **confirm the Serial Number** to launch the Settings app to verify the serial number.</span></span> <span data-ttu-id="efb27-153">その後、ポータル サイト アプリにシリアル番号の最後の 4 文字を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-153">The user must then enter the last four characters of the serial number into the Company Portal app.</span></span>

  <span data-ttu-id="efb27-154">この手順では、デバイスが Intune に登録されている会社のデバイスであることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="efb27-154">This step verifies that the device is the corporate device enrolled in Intune.</span></span> <span data-ttu-id="efb27-155">デバイスのシリアル番号が一致しない場合は、間違ったデバイスが選択されています。</span><span class="sxs-lookup"><span data-stu-id="efb27-155">If the serial number on the device does not match, the wrong device was selected.</span></span> <span data-ttu-id="efb27-156">その場合は、前の画面に戻って、別のデバイスを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-156">The user should go back to the previous screen and select a different device.</span></span>

7. <span data-ttu-id="efb27-157">シリアル番号が確認されると、ポータル サイト アプリはポータル サイトの Web サイトにリダイレクトされ、登録の最終処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="efb27-157">After the serial number is verified, the Company Portal app redirects to the Company Portal website to finalize enrollment.</span></span> <span data-ttu-id="efb27-158">Web サイトでは、ユーザーにアプリに戻るように促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb27-158">Then the website prompts the user to return to the app.</span></span>

8. <span data-ttu-id="efb27-159">これで登録が完了します。</span><span class="sxs-lookup"><span data-stu-id="efb27-159">Enrollment is now complete.</span></span> <span data-ttu-id="efb27-160">これで、このデバイスのすべての機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="efb27-160">The user can now use this device with the full set of capabilities.</span></span>

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a><span data-ttu-id="efb27-161">ユーザー アフィニティなしの企業所有の管理対象デバイスについて</span><span class="sxs-lookup"><span data-stu-id="efb27-161">About corporate-owned managed devices with no user affinity</span></span>

<span data-ttu-id="efb27-162">ユーザー アフィニティなしで構成されているデバイスではポータル サイトはサポートされません。そのようなデバイスにはポータル サイト アプリをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="efb27-162">Devices that are configured with no user affinity do not support the Company Portal and should not have the app installed.</span></span> <span data-ttu-id="efb27-163">会社ポータルは、会社の資格情報を持ち、カスタマイズされた企業リソース (電子メールなど) へのアクセスを必要とするユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="efb27-163">The Company Portal is designed for users who have corporate credentials and require access to personalized corporate resources (e.g. email).</span></span> <span data-ttu-id="efb27-164">ユーザー アフィニティなしで登録されたデバイスは、専用ユーザー サインインのためのデバイスではありません。</span><span class="sxs-lookup"><span data-stu-id="efb27-164">Devices that are enrolled with no user affinity are not intended to have a dedicated user sign in.</span></span> <span data-ttu-id="efb27-165">ユーザー アフィニティなしで登録されているデバイスの一般的な使用例としては、キオスクや販売時点管理 (POS)、共有ユーティリティのデバイスがあります。</span><span class="sxs-lookup"><span data-stu-id="efb27-165">Kiosk, point of sale (POS), or shared-utility devices are typical use cases for devices that are enrolled with no user affinity.</span></span>

<span data-ttu-id="efb27-166">ユーザー アフィニティが必要な場合は、デバイスを登録する前に、デバイスの登録プロファイルで **[ユーザー アフィニティ]** が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="efb27-166">If user affinity is required, be sure that the device’s enrollment profile has **User Affinity** selected before enrolling the device.</span></span> <span data-ttu-id="efb27-167">デバイスのアフィニティの状態を変更するには、デバイスをインベントリから削除してから再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb27-167">To change the affinity status on a device, you must retire the device and reenroll it.</span></span>



### <a name="see-also"></a><span data-ttu-id="efb27-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="efb27-168">See also</span></span>
[<span data-ttu-id="efb27-169">Microsoft Intune でデバイスを登録するための前提条件</span><span class="sxs-lookup"><span data-stu-id="efb27-169">Prerequisites for enrolling devices in Microsoft Intune</span></span>](prerequisites-for-enrollment.md)
