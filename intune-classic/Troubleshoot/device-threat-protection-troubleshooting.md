---
title: "Lookout の統合に関するトラブルシューティング"
description: "このトピックでは、Lookout の統合で発生することが多い問題のトラブルシューティングについて説明します"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 50f34aab2b4f8f2adddb45055f54bb155b24c0ec
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="troubleshoot-lookout-integration-with-intune"></a><span data-ttu-id="79c0f-103">Lookout と Intune の統合に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="79c0f-103">Troubleshoot Lookout Integration with Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="79c0f-104">このトピックでは、Lookout Mobile Threat Protection (MTP) のセットアップで発生する可能性がある一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-104">This topic describes some common issues you may encounter with your Lookout mobile threat protection (MTP) setup.</span></span>

<span data-ttu-id="79c0f-105">**ログイン エラー**</span><span class="sxs-lookup"><span data-stu-id="79c0f-105">**Login errors**</span></span>

## <a name="403-errors"></a><span data-ttu-id="79c0f-106">403 エラー</span><span class="sxs-lookup"><span data-stu-id="79c0f-106">403 errors</span></span>
<span data-ttu-id="79c0f-107">[Lookout MTP コンソール](https://aad.lookout.com)にログインするときに、403 エラー "**サービスにアクセスする権限がありません**" が発生します。これは、指定したユーザー名が、Lookout MTP アクセス用に構成されている Azure Active Directory (AD) グループのメンバーではない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="79c0f-107">When you log in to the [Lookout MTP console](https://aad.lookout.com) you see a 403 error:  **you are not authorized to access the service**  This can happen when the specified username is not a member of the Azure Active Directory (AD) group configured to access Lookout MTP.</span></span>

<span data-ttu-id="79c0f-108">Lookout MTP は、構成されている Azure AD グループのユーザーのみに、サービスへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-108">Lookout MTP only allows users from a configured Azure AD group to access the service.</span></span> <span data-ttu-id="79c0f-109">Lookout MTP へのアクセス権を持つように構成されているグループを確認するには、Lookout のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="79c0f-109">To determine which group is configured with access to Lookout MTP, contact Lookout Support:</span></span>

* <span data-ttu-id="79c0f-110">電子メール: enterprisesupport@lookout.com</span><span class="sxs-lookup"><span data-stu-id="79c0f-110">Email: enterprisesupport@lookout.com</span></span>
* <span data-ttu-id="79c0f-111">[MTP コンソール](http://aad.lookout.com)にログインして、**[Support]** (サポート) モジュールに移動します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-111">Login to the  [MTP  Console](http://aad.lookout.com), and navigate to the **Support** module.</span></span>
* <span data-ttu-id="79c0f-112">https://enterprise.support.lookout.com/hc/requests にアクセスしてサポートを要求します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-112">Go to: https://enterprise.support.lookout.com/hc/requests and make a support request.</span></span>

## <a name="unable-to-sign-in"></a><span data-ttu-id="79c0f-113">サインインできない</span><span class="sxs-lookup"><span data-stu-id="79c0f-113">Unable to sign in</span></span>
<span data-ttu-id="79c0f-114">Azure AD グローバル管理者ユーザーが初期 Lookout セットアップを受け入れていない場合、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79c0f-114">You see the following error when the Azure AD global admin user has not accepted the initial Lookout setup.</span></span>

![サインイン エラーを示す Lookout ログイン画面のスクリーンショット](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

<span data-ttu-id="79c0f-116">この問題を解決するには、グローバル管理者ユーザーが https://aad.lookout.com/les?action=consent にログインし、セットアップを開始するためのメッセージを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c0f-116">To resolve this issue, the global admin user must login to  https://aad.lookout.com/les?action=consent and accept the prompt to initiate the set up.</span></span> <span data-ttu-id="79c0f-117">詳細については、「[Lookout MTP でサブスクリプションをセットアップする](../deploy-use/setup-your-lookout-mtd-subscription.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79c0f-117">More detailed information can be found in  [Set up your subscription with Lookout MTP](../deploy-use/setup-your-lookout-mtd-subscription.md) topic</span></span>

<span data-ttu-id="79c0f-118">**デバイスの状態の問題**</span><span class="sxs-lookup"><span data-stu-id="79c0f-118">**Device status issues**</span></span>

## <a name="device-missing-from-lookout-device-list"></a><span data-ttu-id="79c0f-119">Lookout のデバイス リストにデバイスがない</span><span class="sxs-lookup"><span data-stu-id="79c0f-119">Device missing from Lookout device list</span></span>

<span data-ttu-id="79c0f-120">この問題は、次のいずれかのシナリオで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79c0f-120">This could happen in either of the following scenarios:</span></span>
* <span data-ttu-id="79c0f-121">デバイスのユーザーが、**Lookout MTP コンソール**で指定されている**登録グループ**に含まれません。</span><span class="sxs-lookup"><span data-stu-id="79c0f-121">The device user is not in the **Enrollment Group** specified in the **Lookout MTP Console**.</span></span>  <span data-ttu-id="79c0f-122">[Lookout コンソール](http://aad.lookout.com)で、**[System]** (システム) > **[Intune Connector]** (Intune コネクタ) > **[Enrollment Management]** (登録管理) に移動します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-122">In the [Lookout console](http://aad.lookout.com), go **System** > **Intune Connector** > **Enrollment Management**.</span></span>  <span data-ttu-id="79c0f-123">登録用に構成されている Azure AD グループを確認し、デバイスのユーザーがいずれかの Azure AD グループのメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-123">Review the Azure AD groups configured for enrollment and verify that the device user is part of one of the Azure AD groups.</span></span>  <span data-ttu-id="79c0f-124">ユーザーが登録グループに追加されてから、デバイスが Lookout MTP コンソールの **[Devices]** (デバイス) モジュールに表示されるまでに、最大で構成されているポーリング間隔 (既定値は 5 分) だけかかります。</span><span class="sxs-lookup"><span data-stu-id="79c0f-124">Once a user is added to the enrollment group, it can take up to the configured polling interval, 5 minutes by default, for the device to appear in the **Devices** module of the Lookout MTP console.</span></span>
* <span data-ttu-id="79c0f-125">デバイスが Lookout MTP でサポートされていない場合。</span><span class="sxs-lookup"><span data-stu-id="79c0f-125">If the device is unsupported by Lookout MTP.</span></span>  <span data-ttu-id="79c0f-126">サポートされていないデバイスは、Lookout MTP コンソールのコネクタ設定の **[Managed Devices]** (管理対象デバイス) セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="79c0f-126">Devices that are unsupported will appear in the **Managed Devices** section of the connector settings on the Lookout MTP Console.</span></span>

### <a name="device-reported-as-pending"></a><span data-ttu-id="79c0f-127">デバイスが**保留中**として報告される</span><span class="sxs-lookup"><span data-stu-id="79c0f-127">Device reported as **pending**</span></span>

<span data-ttu-id="79c0f-128">エンド ユーザーが Lookout for Work アプリを開かずに **[Activate]** (アクティブ化) ボタンをタップした場合、デバイスは **[Pending]** (保留中) と表示されます。</span><span class="sxs-lookup"><span data-stu-id="79c0f-128">A device is shown as  **Pending** if the end user has not opened the Lookout for work app and tapped the  **Activate** button.</span></span> <span data-ttu-id="79c0f-129">Lookout for Work アプリでのデバイスのアクティブ化の詳細については、「[Android デバイスで Lookout for Work のインストールを求められる](http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)」または「[iOS デバイスで Lookout for Work のインストールを求められる](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-ios)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79c0f-129">For more details on the device activation with Lookout for work app, see [You are prompted to install Lookout for Work on your Android device](http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android) or [You are prompted to install Lookout for Work on your iOS device](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-ios)</span></span>

## <a name="device-whos-active-but-has-no-device-id"></a><span data-ttu-id="79c0f-130">デバイスはアクティブであるがデバイス ID がない</span><span class="sxs-lookup"><span data-stu-id="79c0f-130">Device whos active, but has no device ID</span></span>
<span data-ttu-id="79c0f-131">Lookout MTP コンソールでアクティブなデバイスにデバイス ID が表示されない場合は、デバイスのユーザーが登録グループに含まれません。</span><span class="sxs-lookup"><span data-stu-id="79c0f-131">In the Lookout MTP console, if an active device has no device ID then the device user is not in the enrollment group.</span></span> <span data-ttu-id="79c0f-132">デバイスのユーザーが登録グループから削除された場合、または登録グループが削除された場合、デバイスはこの状態になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79c0f-132">A device can get into this state is if the device user has been removed from the enrollment group or the enrollment group has been removed.</span></span>

<span data-ttu-id="79c0f-133">[Lookout コンソール](http://aad.lookout.com)で、**[System]** (システム) > **[Intune Connector]** (Intune コネクタ) > **[Enrollment]** (登録) に移動し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-133">In the [Lookout console](http://aad.lookout.com), go **System** > **Intune Connector** > **Enrollment** and review the settings.</span></span>  <span data-ttu-id="79c0f-134">Azure AD グループを確認し、デバイスのユーザーがいずれかの Azure AD グループのメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-134">Review the Azure AD groups and verify that the device useris part of one of the Azure AD groups.</span></span>

<span data-ttu-id="79c0f-135">デバイスがこの状態にある間、Lookout は検出された脅威をユーザーに通知し続けますが、Intune には脅威情報を送信しません。</span><span class="sxs-lookup"><span data-stu-id="79c0f-135">While a device is in this state, Lookout will continue to notify the user of any threats detected, but will not send any threat information to Intune.</span></span>

## <a name="device-reported-as-disconnected"></a><span data-ttu-id="79c0f-136">デバイスが**切断**として報告される</span><span class="sxs-lookup"><span data-stu-id="79c0f-136">Device reported as **disconnected**</span></span>

<span data-ttu-id="79c0f-137">**[Disconnected]** (切断) は、構成されている間隔 (既定は 30 日、最短 7 日) の期間内にデバイスが Lookout MTP と同期されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-137">**Disconnected** means the device hasn't synced with Lookout MTP in the configured interval, 30 days by default with a minimum of 7 days.</span></span> <span data-ttu-id="79c0f-138">ポータル サイト アプリまたは Lookout for Work アプリがデバイスにありません。</span><span class="sxs-lookup"><span data-stu-id="79c0f-138">Either the Company Portal app or the Lookout for Work app is missing from the device.</span></span> <span data-ttu-id="79c0f-139">アプリを再インストールすると、この問題は解決します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-139">Reinstalling the apps should resolve this issue.</span></span> <span data-ttu-id="79c0f-140">ユーザーが Lookout for Work を開いてアプリをアクティブ化すると、デバイスは Lookout MTP および Intune と再同期します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-140">When the user opens Lookout for Work and activates the app, the device resyncs with Lookout MTP and Intune.</span></span>

### <a name="forcing-a-device-sync"></a><span data-ttu-id="79c0f-141">デバイスの強制同期</span><span class="sxs-lookup"><span data-stu-id="79c0f-141">Forcing a device sync</span></span>
<span data-ttu-id="79c0f-142">Lookout MTP コンソールの **[Devices]** (デバイス) モジュールで、管理者はデバイスを選択して削除できます。</span><span class="sxs-lookup"><span data-stu-id="79c0f-142">From the **Devices** module of the Lookout MTP console, the administrator can select the device and choose to delete it.</span></span>   <span data-ttu-id="79c0f-143">次にデバイス所有者が Lookout for Work アプリを開いて **[Activate]** (アクティブ化) をタップすると、デバイスの状態は完全に再同期されます。</span><span class="sxs-lookup"><span data-stu-id="79c0f-143">The next time the device owner opens the Lookout for Work app and taps **Activate**, the device state will do a full resync.</span></span>

## <a name="device-has-a-new-user"></a><span data-ttu-id="79c0f-144">デバイスに新しいユーザーがいる</span><span class="sxs-lookup"><span data-stu-id="79c0f-144">Device has a new user</span></span>
<span data-ttu-id="79c0f-145">デバイスをワイプし、新しいユーザーに登録を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c0f-145">You should wipe the device and ask the new user to enroll.</span></span>  <span data-ttu-id="79c0f-146">[Intune 管理者コンソール](https://manage.microsoft.com)でデバイスを選択して右クリックし、**[インベントリからの削除/ワイプ]** を選択してデバイスを管理から削除します。</span><span class="sxs-lookup"><span data-stu-id="79c0f-146">From the [Intune administrator console](https://manage.microsoft.com), select the device, right click, and choose **Retire/Wipe** to remove the device from management.</span></span> <span data-ttu-id="79c0f-147">デバイスをインベントリから削除した後は、デバイスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="79c0f-147">After retiring the device you can delete it.</span></span>

![Intune 管理者コンソールのデバイス モジュールの [インベントリからの削除/ワイプ] オプションが表示されたスクリーンショット](../media/mtp/mtp-retire-device-intune-console.png)

<span data-ttu-id="79c0f-149">または、[Lookout コンソール](http://aad.lookout.com)の **[Devices]** (デバイス) モジュールで **[Delete]** (削除) を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="79c0f-149">You can also go to the **Devices** module of the [Lookout console](http://aad.lookout.com) and choose **Delete**.</span></span>

<span data-ttu-id="79c0f-150">新しいユーザーが Lookout MTP 登録グループのメンバーである場合、Azure AD がデバイスを新しいユーザーに関連付けるとデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79c0f-150">If the new user is in an  Lookout MTP enrollment group, the device will appear once Azure AD associates the device with the new user.</span></span>

## <a name="compliance-remediation-workflows"></a><span data-ttu-id="79c0f-151">コンプライアンス修復のワークフロー</span><span class="sxs-lookup"><span data-stu-id="79c0f-151">Compliance remediation workflows</span></span>
- [<span data-ttu-id="79c0f-152">Android デバイスで Lookout for Work のインストールを求められる</span><span class="sxs-lookup"><span data-stu-id="79c0f-152">You are prompted to install Lookout for Work on your Android device</span></span>]( http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)
- [<span data-ttu-id="79c0f-153">Android デバイスで Lookout for Work が検出した脅威を解決する必要がある</span><span class="sxs-lookup"><span data-stu-id="79c0f-153">You need to resolve a threat that Lookout for Work found on your Android device</span></span>](http://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [<span data-ttu-id="79c0f-154">iOS デバイスで Lookout for Work が検出した脅威を解決する必要がある</span><span class="sxs-lookup"><span data-stu-id="79c0f-154">You need to resolve a threat that Lookout for Work found on your iOS device</span></span>](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <a name="see-also"></a><span data-ttu-id="79c0f-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="79c0f-155">See also</span></span>
[<span data-ttu-id="79c0f-156">Lookout MTP でサブスクリプションをセットアップする</span><span class="sxs-lookup"><span data-stu-id="79c0f-156">Set up you subscription with Lookout MTP</span></span>](/intune-classic/deploy-use/set-up-your-subscription-with-lookout-mtp)
