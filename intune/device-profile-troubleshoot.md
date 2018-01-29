---
title: "Microsoft Intune のデバイス プロファイルに関するトラブルシューティング"
titlesuffix: Azure portal
description: "Intune デバイス プロファイルの問題が解決できずに困っている場合は、このトピックに従って問題を解決してください。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4aaa25bb36b0125350e3ab8b25e7e8ba89626c3f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="troubleshooting-device-profiles-in-microsoft-intune"></a><span data-ttu-id="29604-103">Microsoft Intune のデバイス プロファイルに関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="29604-103">Troubleshooting device profiles in Microsoft Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="29604-104">このトピックに記載されている情報は、Intune デバイス プロファイルに関する一般的な問題のトラブルシューティングに活用できます。</span><span class="sxs-lookup"><span data-stu-id="29604-104">The information in this topic can be used to help you troubleshoot common issues around Intune device profiles.</span></span>

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a><span data-ttu-id="29604-105">既存の Wi-Fi プロファイルでパスワードやパスフレーズを変更すると、ユーザーに新しいプロファイルが与えられません。</span><span class="sxs-lookup"><span data-stu-id="29604-105">Why doesn't a user get a new profile when changing a password or passphrase on an existing Wi-Fi profile?</span></span> 
<span data-ttu-id="29604-106">企業の Wi-Fi プロファイルを作成し、それをグループに展開し、パスワードを変更し、プロファイルを保存した場合、ユーザーに新しいプロファイルの取得を求めることがあります。</span><span class="sxs-lookup"><span data-stu-id="29604-106">When you create a corporate Wi-Fi profile, deploy the profile to a group, change the password, and save the profile, you might expect the user gets the new profile.</span></span> <span data-ttu-id="29604-107">しかしながら、新しいプロファイルがユーザーに与えられないことがあります。</span><span class="sxs-lookup"><span data-stu-id="29604-107">However, the user might not get the new profile.</span></span> 

<span data-ttu-id="29604-108">この問題を軽減するのには、企業 Wi-Fi にエラーが発生した場合、ユーザーがゲスト Wi-Fi にフォールバックするようにゲスト Wi-Fi を設定しておきます。</span><span class="sxs-lookup"><span data-stu-id="29604-108">To mitigate this issue, make sure you have a guest Wi-Fi set up such that the user falls back to the guest Wi-Fi if the corporate Wi-Fi fails.</span></span> <span data-ttu-id="29604-109">自動接続設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29604-109">The automatically connect setting needs to be enabled.</span></span> <span data-ttu-id="29604-110">このゲスト Wi-Fi プロファイルはすべてのユーザーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29604-110">This guest Wi-Fi profile needs to be deployed to all users.</span></span>

<span data-ttu-id="29604-111">その他のベスト プラクティス:</span><span class="sxs-lookup"><span data-stu-id="29604-111">There are some additional best practices that you can follow:</span></span>
- <span data-ttu-id="29604-112">接続先の Wi-Fi ネットワークはパスワードまたはパスフレーズを受け取るため、Wi-Fi ルーターに直接接続できます。</span><span class="sxs-lookup"><span data-stu-id="29604-112">Since the Wi-Fi network you're connecting to takes a password or passphrase, make sure you can connect to the Wi-Fi router directly.</span></span> <span data-ttu-id="29604-113">iOS デバイスでテストできます。</span><span class="sxs-lookup"><span data-stu-id="29604-113">You can test with an iOS device.</span></span>
- <span data-ttu-id="29604-114">Wi-Fi エンドポイント (Wi-Fi ルーター) に正常に接続されたら、SSID と使用した資格情報 (パスワードまたはパスフレーズ) をメモします。</span><span class="sxs-lookup"><span data-stu-id="29604-114">After you successfully connect to the Wi-Fi endpoint (Wi-Fi router,) note the SSID and the credential used (this is the password or passphrase.)</span></span>
- <span data-ttu-id="29604-115">事前共有キー フィールドに SSID と資格情報 (パスワードまたはパスフレーズ) を入力します。</span><span class="sxs-lookup"><span data-stu-id="29604-115">Enter the SSID and credential (password or passphrase) in the Pre-Shared Key field.</span></span> 
- <span data-ttu-id="29604-116">ユーザー数が限られているテスト グループに展開します。IT チームに限定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29604-116">Deploy to a test group which has limited number of users, preferably only the IT team.</span></span> 
- <span data-ttu-id="29604-117">iOS デバイスを Intune に同期します。</span><span class="sxs-lookup"><span data-stu-id="29604-117">Sync your iOS device to Intune.</span></span> <span data-ttu-id="29604-118">登録していない場合、登録します。</span><span class="sxs-lookup"><span data-stu-id="29604-118">Enroll if you haven’t already enrolled.</span></span> 
- <span data-ttu-id="29604-119">(最初の手順で説明した) 同じ Wi-Fi エンドポイントへの接続をもう一度テストします。</span><span class="sxs-lookup"><span data-stu-id="29604-119">Test connecting to the same Wi-Fi endpoint (as mentioned in the first step) again.</span></span>
- <span data-ttu-id="29604-120">より大きなグループにロールアウトし、最後には、展開が求められる組織の全ユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="29604-120">Roll out to larger groups and eventually to all expected users in your organization.</span></span> 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a><span data-ttu-id="29604-121">モバイル デバイスが割り当て後にポリシーまたはアプリを取得するのにどれくらいの時間がかかりますか。</span><span class="sxs-lookup"><span data-stu-id="29604-121">How long does it take for mobile devices to get a policy or apps after they have been assigned?</span></span>
<span data-ttu-id="29604-122">ポリシーまたはアプリが割り当てられると、Intune はデバイスに対して、Intune サービスにチェックインする必要があることをすぐに通知し始めます。</span><span class="sxs-lookup"><span data-stu-id="29604-122">When a policy or an app is assigned, Intune immediately begins attempting to notify the device that it should check in with the Intune service.</span></span> <span data-ttu-id="29604-123">これにかかる時間は通常 5 分未満です。</span><span class="sxs-lookup"><span data-stu-id="29604-123">This typically takes less than five minutes.</span></span>

<span data-ttu-id="29604-124">最初の通知が送信された後、デバイスがチェックインしてポリシーを取得しない場合、Intune はさらに 3 回試行します。</span><span class="sxs-lookup"><span data-stu-id="29604-124">If a device doesn't check in to get the policy after the first notification is sent, Intune makes three more attempts.</span></span>  <span data-ttu-id="29604-125">デバイスがオフライン (たとえば、デバイスの電源がオフである、ネットワークに接続されていない) の場合、通知を受信していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29604-125">If the device is offline (for example, it is turned off or not connected to a network), it might not receive the notifications.</span></span> <span data-ttu-id="29604-126">この場合、デバイスは次回のスケジュールされた Intune サービスへのチェックインでポリシーを取得することになります。チェックイン頻度は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29604-126">In this case, the device will get the policy on its next scheduled check-in with the Intune service as follows:</span></span>

- <span data-ttu-id="29604-127">iOS と macOS: 6 時間ごと</span><span class="sxs-lookup"><span data-stu-id="29604-127">iOS and macOS: Every 6 hours.</span></span>
- <span data-ttu-id="29604-128">Android: 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="29604-128">Android: Every 8 hours.</span></span>
- <span data-ttu-id="29604-129">Windows Phone: 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="29604-129">Windows Phone: Every 8 hours.</span></span>
- <span data-ttu-id="29604-130">デバイスとして登録された Windows 8.1 および Windows 10 PC: 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="29604-130">Windows 8.1 and Windows 10 PCs enrolled as devices: Every 8 hours.</span></span>

<span data-ttu-id="29604-131">登録してすぐのデバイスでは、チェックイン頻度が高くなります。頻度は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29604-131">If the device has just enrolled, the check-in frequency will be more frequent, as follows:</span></span>

- <span data-ttu-id="29604-132">iOS と macOS: 6 時間まで 15 分ごと、その後 6 時間ごと</span><span class="sxs-lookup"><span data-stu-id="29604-132">iOS and macOS: Every 15 minutes for 6 hours, and then every 6 hours.</span></span>
- <span data-ttu-id="29604-133">Android: 15 分まで 3 分ごと、その後の 2 時間は 15 分ごと、その後 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="29604-133">Android: Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours.</span></span>
- <span data-ttu-id="29604-134">Windows Phone: 15 分まで 5 分ごと、その後の 2 時間は 15 分ごと、その後 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="29604-134">Windows Phone: Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours.</span></span>
- <span data-ttu-id="29604-135">デバイスとして登録された Windows PC: 30 分まで 3 分ごと、その後 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="29604-135">Windows PCs enrolled as devices: Every 3 minutes for 30 minutes, and then every 8 hours.</span></span>

<span data-ttu-id="29604-136">また、ユーザーはポータル サイト アプリを起動し、デバイスを同期して、いつでもすぐにポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="29604-136">Users can also open the Company Portal app and sync the device to immediately check for the policy anytime.</span></span>

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a><span data-ttu-id="29604-137">どのような操作を行うと Intune は通知をデバイスにすぐに送信しますか。</span><span class="sxs-lookup"><span data-stu-id="29604-137">What actions cause Intune to immediately send a notification to a device?</span></span>
<span data-ttu-id="29604-138">デバイスは、チェックインを指示する通知を受け取ったとき、または定期的にスケジュールされたチェックイン時に Intune にチェックインします。</span><span class="sxs-lookup"><span data-stu-id="29604-138">Devices check in with Intune either when they receive a notification that tells them to check in or during their regularly scheduled check-in.</span></span>  <span data-ttu-id="29604-139">ワイプ、ロック、パスコードのリセット、アプリの割り当て、プロファイルの割り当て (Wi-Fi、VPN、メールなど)、ポリシーの割り当てなどの操作で具体的にデバイスまたはユーザーを対象とする場合、Intune は、デバイスが Intune サービスにチェックインしてこれらの更新プログラムを受信するよう指示する通知をすぐに開始します。</span><span class="sxs-lookup"><span data-stu-id="29604-139">When you target a device or user specifically with an action such as a wipe, lock, passcode reset, app assignment, profile assignment (Wi-Fi, VPN, email, etc.), or policy assignment, Intune will immediately begin trying to notify the device that it should check in with the Intune service to receive these updates.</span></span>

<span data-ttu-id="29604-140">ポータル サイトの連絡先情報の修正など、他の変更ではデバイスへの通知はすぐに行われません。</span><span class="sxs-lookup"><span data-stu-id="29604-140">Other changes, such as revising the contact information in the company portal, do not cause an immediate notification to devices.</span></span>

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a><span data-ttu-id="29604-141">複数のポリシーが同じユーザーまたはデバイスに割り当てられる場合、どの設定が適用されるのかどうすればわかりますか。</span><span class="sxs-lookup"><span data-stu-id="29604-141">If multiple policies are assigned to the same user or device, how do I know which settings will get applied?</span></span>
<span data-ttu-id="29604-142">2 つ以上のポリシーが同じユーザーまたはデバイスに割り当てられる場合、適用される設定の評価は個々の設定レベルで行われます。</span><span class="sxs-lookup"><span data-stu-id="29604-142">When two or more policies are assigned to the same user or device, the evaluation for which setting is applied happens at the individual setting level:</span></span>

-   <span data-ttu-id="29604-143">コンプライアンス ポリシー設定は常に構成ポリシー設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="29604-143">Compliance policy settings always have precedence over configuration policy settings.</span></span>

-   <span data-ttu-id="29604-144">異なるコンプライアンス ポリシーの同じ設定について評価する場合、最も制限の厳しいコンプライアンス ポリシー設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="29604-144">The most restrictive compliance policy setting is applied if it is evaluated against the same setting in a different compliance policy.</span></span>

-   <span data-ttu-id="29604-145">構成ポリシーの設定が別の構成ポリシーの設定と競合する場合、Azure Portal にその競合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="29604-145">If a configuration policy setting conflicts with a setting in a different configuration policy, this conflict will be displayed in the Azure portal.</span></span> <span data-ttu-id="29604-146">このような競合は手動で解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29604-146">You must manually resolve such conflicts.</span></span>

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a><span data-ttu-id="29604-147">アプリ保護ポリシー同士が競合している場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="29604-147">What happens when app protection policies conflict with each other?</span></span> <span data-ttu-id="29604-148">どのポリシーがアプリに適用されますか。</span><span class="sxs-lookup"><span data-stu-id="29604-148">Which one will be applied to the app?</span></span>
<span data-ttu-id="29604-149">競合している値は、(リセットする前の PIN の試行で使用するような) 番号入力フィールドを除き、アプリ保護ポリシーで使用可能な最も制限の厳しい設定になっています。</span><span class="sxs-lookup"><span data-stu-id="29604-149">Conflict values are the most restrictive settings available in an app protection policy, except for the number entry fields (like PIN attempts before reset).</span></span>  <span data-ttu-id="29604-150">番号入力フィールドは、推奨設定のオプションを使用することでコンソールで MAM ポリシーを作成した場合と同じ値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="29604-150">The number entry fields will be set the same as the values, as if you created a MAM policy in the console by using the recommended settings option.</span></span>

<span data-ttu-id="29604-151">競合は、2 つのプロファイル設定が同じ場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="29604-151">Conflicts occur when two profile settings are the same.</span></span>  <span data-ttu-id="29604-152">たとえば、コピー/貼り付けの設定以外は同じ MAM ポリシーを 2 つ構成したとします。</span><span class="sxs-lookup"><span data-stu-id="29604-152">For example, you configured two MAM policies that are identical except for the copy/paste setting.</span></span>  <span data-ttu-id="29604-153">この場合、コピー/貼り付けの設定は最も厳しい値になりますが、残りの設定は構成したとおりに適用されます。</span><span class="sxs-lookup"><span data-stu-id="29604-153">In this scenario, the copy/paste setting will be set to the most restrictive value, but the rest of the settings will be applied as configured.</span></span>

<span data-ttu-id="29604-154">1 つのプロファイルをアプリに割り当て、このプロファイルが有効になった後、2 つ目のプロファイルを割り当てると、2 つ目のプロファイルは競合の状態になりますが、最初のプロファイルは優先され、適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="29604-154">If one profile is assignedd to the app and takes effect, and then a second one is assigned, the first one will take precedence and stay applied, while the second shows in conflict.</span></span> <span data-ttu-id="29604-155">両方が同時に適用される (優先されるプロファイルがない) 場合は、両方が競合の状態になります。</span><span class="sxs-lookup"><span data-stu-id="29604-155">If they are both applied at the same time, meaning that there is no preceding profile, then they will both be in conflict.</span></span> <span data-ttu-id="29604-156">競合する設定は、最も制限の厳しい値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="29604-156">Any conflicting settings will be set to the most restrictive values.</span></span>

## <a name="what-happens-when-ios-custom-policies-conflict"></a><span data-ttu-id="29604-157">iOS カスタム ポリシーが競合するとどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="29604-157">What happens when iOS custom policies conflict?</span></span>
<span data-ttu-id="29604-158">Intune は Apple 構成ファイルのペイロードまたはカスタム Open Mobile Alliance Uniform Resource Identifier (OMA-URI) プロファイルを評価しません。</span><span class="sxs-lookup"><span data-stu-id="29604-158">Intune does not evaluate the payload of Apple Configuration files or a custom Open Mobile Alliance Uniform Resource Identifier (OMA-URI) profile.</span></span> <span data-ttu-id="29604-159">配信メカニズムとしてのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="29604-159">It merely serves as the delivery mechanism.</span></span>

<span data-ttu-id="29604-160">カスタム プロファイルを割り当てるときは、構成した設定がコンプライアンス、構成、または他のカスタム プロファイルと競合していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="29604-160">When you assign a custom profile, ensure that the configured settings do not conflict with compliance, configuration, or other custom policies.</span></span> <span data-ttu-id="29604-161">設定が競合しているカスタム プロファイルの場合、設定が適用される順序はランダムになります。</span><span class="sxs-lookup"><span data-stu-id="29604-161">In the case of a custom profile with settings conflicts, the order in which settings are applied is random.</span></span>

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a><span data-ttu-id="29604-162">プロファイルが削除された場合または適用できなくなった場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="29604-162">What happens when a profile is deleted or no longer applicable?</span></span>
<span data-ttu-id="29604-163">プロファイルを削除した場合やプロファイルを割り当てたグループからデバイスを削除した場合は、次のリストに従ってプロファイルと設定がデバイスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="29604-163">When you delete a profile, or you remove a device from a group to which a profile was assigned, the profile and settings will be removed from the device according to the following lists.</span></span>

### <a name="enrolled-devices"></a><span data-ttu-id="29604-164">[登録済みデバイス]</span><span class="sxs-lookup"><span data-stu-id="29604-164">Enrolled devices</span></span>

- <span data-ttu-id="29604-165">Wi-Fi、VPN、証明書、電子メールのプロファイル: これらのプロファイルは、すべてのサポートされる登録デバイスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="29604-165">Wi-Fi, VPN, certificate, and email profiles: These profiles are removed from all supported enrolled devices.</span></span>
- <span data-ttu-id="29604-166">他のすべてのプロファイルの種類:</span><span class="sxs-lookup"><span data-stu-id="29604-166">All other profile types:</span></span>
    - <span data-ttu-id="29604-167">**Windows および Android デバイス**: 設定はデバイスから削除されません。</span><span class="sxs-lookup"><span data-stu-id="29604-167">**Windows and Android devices**: Settings are not removed from the device.</span></span>
    - <span data-ttu-id="29604-168">**Windows Phone 8.1 デバイス**: 次の設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="29604-168">**Windows Phone 8.1 devices**: The following settings are removed:</span></span>
        - <span data-ttu-id="29604-169">モバイル デバイスのロックを解除するパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="29604-169">Require a password to unlock mobile devices</span></span>
        - <span data-ttu-id="29604-170">単純なパスワードを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-170">Allow simple passwords</span></span>
        - <span data-ttu-id="29604-171">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="29604-171">Minimum password length</span></span>
        - <span data-ttu-id="29604-172">必要なパスワードの種類</span><span class="sxs-lookup"><span data-stu-id="29604-172">Required password type</span></span>
        - <span data-ttu-id="29604-173">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="29604-173">Password expiration (days)</span></span>
        - <span data-ttu-id="29604-174">パスワードの履歴を記憶する</span><span class="sxs-lookup"><span data-stu-id="29604-174">Remember password history</span></span>
        - <span data-ttu-id="29604-175">デバイスをワイプするまでの連続サインイン エラーの数</span><span class="sxs-lookup"><span data-stu-id="29604-175">Number of repeated sign-in failures to allow before the device is wiped</span></span>
        - <span data-ttu-id="29604-176">パスワードが必要になるまでの非アクティブ状態の時間 (分)</span><span class="sxs-lookup"><span data-stu-id="29604-176">Minutes of inactivity before password is required</span></span>
        - <span data-ttu-id="29604-177">必要なパスワードの種類 - 文字セットの最小数</span><span class="sxs-lookup"><span data-stu-id="29604-177">Required password type – minimum number of character sets</span></span>
        - <span data-ttu-id="29604-178">カメラを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-178">Allow camera</span></span>
        - <span data-ttu-id="29604-179">モバイル デバイスの暗号化を要求する</span><span class="sxs-lookup"><span data-stu-id="29604-179">Require encryption on mobile device</span></span>
        - <span data-ttu-id="29604-180">リムーバブル記憶域を許可する</span><span class="sxs-lookup"><span data-stu-id="29604-180">Allow removable storage</span></span>
        - <span data-ttu-id="29604-181">Web ブラウザーを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-181">Allow web browser</span></span>
        - <span data-ttu-id="29604-182">アプリケーション ストアを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-182">Allow application store</span></span>
        - <span data-ttu-id="29604-183">画面のキャプチャを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-183">Allow screen capture</span></span>
        - <span data-ttu-id="29604-184">位置情報を許可する</span><span class="sxs-lookup"><span data-stu-id="29604-184">Allow geolocation</span></span>
        - <span data-ttu-id="29604-185">Microsoft アカウントを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-185">Allow Microsoft account</span></span>
        - <span data-ttu-id="29604-186">コピーと貼り付けを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-186">Allow copy and paste</span></span>
        - <span data-ttu-id="29604-187">Wi-Fi テザリングを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-187">Allow Wi-Fi tethering</span></span>
        - <span data-ttu-id="29604-188">無料 Wi-Fi スポットへの自動接続を許可する</span><span class="sxs-lookup"><span data-stu-id="29604-188">Allow automatic connection to free Wi-Fi hotspots</span></span>
        - <span data-ttu-id="29604-189">Wi-Fi スポットの報告を許可する</span><span class="sxs-lookup"><span data-stu-id="29604-189">Allow Wi-Fi hotspot reporting</span></span>
        - <span data-ttu-id="29604-190">工場出荷時のリセットを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-190">Allow factory reset</span></span>
        - <span data-ttu-id="29604-191">Bluetooth を許可する</span><span class="sxs-lookup"><span data-stu-id="29604-191">Allow Bluetooth</span></span>
        - <span data-ttu-id="29604-192">NFC を許可する</span><span class="sxs-lookup"><span data-stu-id="29604-192">Allow NFC</span></span>
        - <span data-ttu-id="29604-193">Wi-Fi を許可する</span><span class="sxs-lookup"><span data-stu-id="29604-193">Allow Wi-Fi</span></span>

    - <span data-ttu-id="29604-194">**iOS**: 次を除き、すべての設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="29604-194">**iOS**: All settings are removed, except:</span></span>
        - <span data-ttu-id="29604-195">音声通話ローミングを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-195">Allow voice roaming</span></span>
        - <span data-ttu-id="29604-196">データ ローミングを許可する</span><span class="sxs-lookup"><span data-stu-id="29604-196">Allow data roaming</span></span>
        - <span data-ttu-id="29604-197">ローミング中の自動同期を許可する</span><span class="sxs-lookup"><span data-stu-id="29604-197">Allow automatic synchronization while roaming</span></span>

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a><span data-ttu-id="29604-198">デバイス制限プロファイルを変更しましたが、変更内容が適用されていません</span><span class="sxs-lookup"><span data-stu-id="29604-198">I changed a device restriction profile, but the changes haven't taken effect</span></span>
<span data-ttu-id="29604-199">Windows Phone デバイスから、MDM または EAS で設定されたセキュリティ ポリシーのセキュリティを一度設定した後に緩くすることはできません。</span><span class="sxs-lookup"><span data-stu-id="29604-199">Windows Phone devices do not allow security policies set via MDM or EAS to be reduced in security once you've set them.</span></span> <span data-ttu-id="29604-200">たとえば、 **パスワードの最小文字数** を 8 に設定し、次に 4 に減らしてみます。</span><span class="sxs-lookup"><span data-stu-id="29604-200">For example, you set a **Minimum number of character password** to 8  then try to reduce it to 4.</span></span> <span data-ttu-id="29604-201">より制限の厳しいプロファイルが、デバイスに既に適用されています。</span><span class="sxs-lookup"><span data-stu-id="29604-201">The more restrictive profile has already been applied to the device.</span></span>

<span data-ttu-id="29604-202">プロファイルを安全度の低い値に変更する場合、デバイスのプラットフォームによっては、セキュリティ ポリシーをリセットしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="29604-202">Depending on the device platform, if you want to change the profile to a less secure value you may need to reset security policies.</span></span>
<span data-ttu-id="29604-203">たとえば、Windows で、デスクトップを右からスワイプして、**[チャーム]** バーを開き、**[設定]** &gt; **[コントロール パネル]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="29604-203">For example, in Windows,  on the desktop swipe in from right to open the **Charms** bar and choose  **Settings** &gt; **Control Panel**.</span></span>  <span data-ttu-id="29604-204">**[ユーザー アカウント]** アプレットを選択します。</span><span class="sxs-lookup"><span data-stu-id="29604-204">Select the **User Accounts** applet.</span></span>
<span data-ttu-id="29604-205">左側のナビゲーション メニューの下部に、 **[セキュリティ ポリシーのリセット]** リンクがあります。</span><span class="sxs-lookup"><span data-stu-id="29604-205">In the left hand navigation menu, there is a **Reset Security Policies** link at the bottom.</span></span> <span data-ttu-id="29604-206">このリンクを選択し、**[ポリシーのリセット]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="29604-206">Choose it and then choose the **Reset Policies** button.</span></span>
<span data-ttu-id="29604-207">Android、Windows Phone 8.1 以降、iOS などのその他の MDM デバイスでは、制限の緩いプロファイルを適用するにはいったんデバイスを削除して、サービスに再登録しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="29604-207">Other MDM devices, such as Android, Windows Phone 8.1 and later, and iOS, may need to be retired and re-enrolled back into the service for you to be able to apply a less restrictive profile.</span></span>


### <a name="next-steps"></a><span data-ttu-id="29604-208">次の手順</span><span class="sxs-lookup"><span data-stu-id="29604-208">Next steps</span></span>
<span data-ttu-id="29604-209">このトラブルシューティング情報を使っても問題が解決しない場合は、「[Microsoft Intune のサポートを受ける方法](get-support.md)」の説明に従って Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29604-209">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](get-support.md).</span></span>