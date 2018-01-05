---
title: "アプリ管理とは"
titlesuffix: Azure portal
description: "このトピックでは、Microsoft Intune を使用したアプリ管理についての基本を説明します。\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5a1cbd6fc3244686c1f5a1db3e4365e615662f0e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="what-is-microsoft-intune-app-management"></a><span data-ttu-id="313c8-103">Microsoft Intune アプリの管理とは</span><span class="sxs-lookup"><span data-stu-id="313c8-103">What is Microsoft Intune app management?</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<span data-ttu-id="313c8-104">IT 管理者は、エンド ユーザーのために、業務に必要なアプリへのアクセス手段を確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="313c8-104">As an IT admin, you are responsible for making sure that your end users have access to the apps they need to do their work.</span></span> <span data-ttu-id="313c8-105">これは、以下の理由により、困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="313c8-105">This can be a challenge because:</span></span>
- <span data-ttu-id="313c8-106">さまざまなデバイス プラットフォームとアプリの種類が存在する。</span><span class="sxs-lookup"><span data-stu-id="313c8-106">There are a wide range of device platforms and app types.</span></span>
- <span data-ttu-id="313c8-107">会社のデバイスやユーザー所有のデバイスで、アプリの管理が必要になる場合がある。</span><span class="sxs-lookup"><span data-stu-id="313c8-107">You might need to manage apps on company devices and users own devices.</span></span>
- <span data-ttu-id="313c8-108">社内のネットワークとデータの安全性を確保する必要がある。</span><span class="sxs-lookup"><span data-stu-id="313c8-108">You must ensure your network, and your data remain secure.</span></span>

<span data-ttu-id="313c8-109">また、Intune に登録されていないデバイスでアプリの割り当てと管理を行うことも必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="313c8-109">Additionally, you might want to assign, and manage apps on devices that are not enrolled with Intune.</span></span>

<span data-ttu-id="313c8-110">Intune では、必要なデバイスで必要なアプリを利用できるように、さまざまな機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="313c8-110">Intune offers a range of capabilities to help you get the apps you need, on the devices you want.</span></span>

## <a name="app-management-capabilities-by-platform"></a><span data-ttu-id="313c8-111">プラットフォーム別のアプリ管理機能</span><span class="sxs-lookup"><span data-stu-id="313c8-111">App management capabilities by platform</span></span>

||||||
|-|-|-|-|-|
|&nbsp; |<span data-ttu-id="313c8-112">Android</span><span class="sxs-lookup"><span data-stu-id="313c8-112">Android</span></span>|<span data-ttu-id="313c8-113">iOS</span><span class="sxs-lookup"><span data-stu-id="313c8-113">iOS</span></span>|<span data-ttu-id="313c8-114">Windows Phone 8。1</span><span class="sxs-lookup"><span data-stu-id="313c8-114">Windows Phone 8.1</span></span>|<span data-ttu-id="313c8-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="313c8-115">Windows 10</span></span>|
|<span data-ttu-id="313c8-116">デバイスとユーザーにアプリを追加して割り当てる</span><span class="sxs-lookup"><span data-stu-id="313c8-116">Add and assign apps to devices and users</span></span>|<span data-ttu-id="313c8-117">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-117">Yes</span></span>|<span data-ttu-id="313c8-118">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-118">Yes</span></span>|<span data-ttu-id="313c8-119">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-119">Yes</span></span>|<span data-ttu-id="313c8-120">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-120">Yes</span></span>|
|<span data-ttu-id="313c8-121">Intune に登録されていないデバイスにアプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="313c8-121">Assign apps to devices not enrolled with Intune</span></span>|<span data-ttu-id="313c8-122">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-122">Yes</span></span>|<span data-ttu-id="313c8-123">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-123">Yes</span></span>|<span data-ttu-id="313c8-124">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-124">No</span></span>|<span data-ttu-id="313c8-125">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-125">No</span></span>|
|<span data-ttu-id="313c8-126">アプリ構成ポリシーを使用してアプリのスタートアップ動作を制御する</span><span class="sxs-lookup"><span data-stu-id="313c8-126">Use app configuration policies to control the startup behavior of apps</span></span>|<span data-ttu-id="313c8-127">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-127">No</span></span>|<span data-ttu-id="313c8-128">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-128">Yes</span></span>|<span data-ttu-id="313c8-129">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-129">No</span></span>|<span data-ttu-id="313c8-130">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-130">No</span></span>|
|<span data-ttu-id="313c8-131">モバイル アプリ プロビジョニング ポリシーを使用して期限切れのアプリを更新する</span><span class="sxs-lookup"><span data-stu-id="313c8-131">Use mobile app provisioning policies to renew expired apps</span></span>|<span data-ttu-id="313c8-132">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-132">No</span></span>|<span data-ttu-id="313c8-133">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-133">Yes</span></span>|<span data-ttu-id="313c8-134">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-134">No</span></span>|<span data-ttu-id="313c8-135">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-135">No</span></span>|
|<span data-ttu-id="313c8-136">アプリ保護ポリシーでアプリ内の会社のデータを保護する</span><span class="sxs-lookup"><span data-stu-id="313c8-136">Protect company data in apps with app protection policies</span></span>|<span data-ttu-id="313c8-137">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-137">Yes</span></span>|<span data-ttu-id="313c8-138">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-138">Yes</span></span>|<span data-ttu-id="313c8-139">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-139">No</span></span>|<span data-ttu-id="313c8-140">×<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="313c8-140">No<sup>1</sup></span></span>|
|<span data-ttu-id="313c8-141">インストール済みのアプリから会社のデータのみを削除する (アプリの選択的ワイプ)</span><span class="sxs-lookup"><span data-stu-id="313c8-141">Remove only corporate data from an installed app (App selective wipe)</span></span>|<span data-ttu-id="313c8-142">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-142">Yes</span></span>|<span data-ttu-id="313c8-143">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-143">Yes</span></span>|<span data-ttu-id="313c8-144">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-144">Yes</span></span>|<span data-ttu-id="313c8-145">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-145">Yes</span></span>|
|<span data-ttu-id="313c8-146">アプリの割り当てを監視する</span><span class="sxs-lookup"><span data-stu-id="313c8-146">Monitor app assignments</span></span>|<span data-ttu-id="313c8-147">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-147">Yes</span></span>|<span data-ttu-id="313c8-148">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-148">Yes</span></span>|<span data-ttu-id="313c8-149">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-149">Yes</span></span>|<span data-ttu-id="313c8-150">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-150">Yes</span></span>|
|<span data-ttu-id="313c8-151">アプリ ストアからのボリューム購入アプリを割り当てて追跡する</span><span class="sxs-lookup"><span data-stu-id="313c8-151">Assign and track volume-purchased apps from an app store</span></span>|<span data-ttu-id="313c8-152">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-152">No</span></span>|<span data-ttu-id="313c8-153">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-153">No</span></span>|<span data-ttu-id="313c8-154">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-154">No</span></span>|<span data-ttu-id="313c8-155">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-155">Yes</span></span>|
|<span data-ttu-id="313c8-156">デバイスへのアプリのインストールを強制する (必須)<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="313c8-156">Mandatory install of apps on devices (Required)<sup>2</sup></span></span>|<span data-ttu-id="313c8-157">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-157">Yes</span></span>|<span data-ttu-id="313c8-158">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-158">Yes</span></span>|<span data-ttu-id="313c8-159">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-159">Yes</span></span>|<span data-ttu-id="313c8-160">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-160">Yes</span></span>|
|<span data-ttu-id="313c8-161">会社のポータルからデバイスへのオプション インストール (利用可能なインストール)</span><span class="sxs-lookup"><span data-stu-id="313c8-161">Optional installation on devices from the Company Portal (Available install)</span></span>|<span data-ttu-id="313c8-162">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-162">Yes</span></span>|<span data-ttu-id="313c8-163">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-163">Yes</span></span>|<span data-ttu-id="313c8-164">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-164">Yes</span></span>|<span data-ttu-id="313c8-165">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-165">Yes</span></span>|
|<span data-ttu-id="313c8-166">Web 上のアプリへのインストール ショートカット (Web クリップ)</span><span class="sxs-lookup"><span data-stu-id="313c8-166">Install shortcut to an app on the web (web clip)</span></span>|<span data-ttu-id="313c8-167">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-167">Yes</span></span>|<span data-ttu-id="313c8-168">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-168">Yes</span></span>|<span data-ttu-id="313c8-169">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-169">Yes</span></span>|<span data-ttu-id="313c8-170">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-170">Yes</span></span>|
|<span data-ttu-id="313c8-171">社内 (基幹業務) アプリ</span><span class="sxs-lookup"><span data-stu-id="313c8-171">In-house (line-of-business) apps</span></span>|<span data-ttu-id="313c8-172">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-172">Yes</span></span>|<span data-ttu-id="313c8-173">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-173">Yes</span></span>|<span data-ttu-id="313c8-174">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-174">No</span></span>|<span data-ttu-id="313c8-175">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="313c8-175">No</span></span>|
|<span data-ttu-id="313c8-176">ストアからのアプリ</span><span class="sxs-lookup"><span data-stu-id="313c8-176">Apps from a store</span></span>|<span data-ttu-id="313c8-177">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-177">Yes</span></span>|<span data-ttu-id="313c8-178">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-178">Yes</span></span>|<span data-ttu-id="313c8-179">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-179">Yes</span></span>|<span data-ttu-id="313c8-180">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-180">Yes</span></span>|
|<span data-ttu-id="313c8-181">アプリを更新する</span><span class="sxs-lookup"><span data-stu-id="313c8-181">Update apps</span></span>|<span data-ttu-id="313c8-182">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-182">Yes</span></span>|<span data-ttu-id="313c8-183">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-183">Yes</span></span>|<span data-ttu-id="313c8-184">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-184">Yes</span></span>|<span data-ttu-id="313c8-185">はい</span><span class="sxs-lookup"><span data-stu-id="313c8-185">Yes</span></span>|

<span data-ttu-id="313c8-186"><sup>1</sup> Windows 10 を実行しているデバイスでアプリを保護するには、[Windows 情報保護](windows-information-protection-configure.md)の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="313c8-186"><sup>1</sup> Consider using [Windows Information Protection](windows-information-protection-configure.md) to protect apps on devices that run Windows 10.</span></span>

<span data-ttu-id="313c8-187"><sup>2</sup> Intune のみで管理されているデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="313c8-187"><sup>2</sup>Applies to devices managed by Intune only.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="313c8-188">開始する方法</span><span class="sxs-lookup"><span data-stu-id="313c8-188">How to get started</span></span>

<span data-ttu-id="313c8-189">アプリに関連するものは、ほとんどが **[Mobile Apps]** ワークロード内にあり、以下の手順でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="313c8-189">You can find most things app-related in the **Mobile Apps** workload that you can access as follows:</span></span>

1. <span data-ttu-id="313c8-190">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="313c8-190">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="313c8-191">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="313c8-191">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="313c8-192">**[Intune]** ブレードで、**[モバイル アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="313c8-192">On the **Intune** blade, choose **Mobile apps**.</span></span>

    ![[モバイル アプリ] ワークロード](./media/apps-workload.png)

### <a name="manage"></a><span data-ttu-id="313c8-194">コンピューターの</span><span class="sxs-lookup"><span data-stu-id="313c8-194">Manage</span></span>
- <span data-ttu-id="313c8-195">**[アプリ]** - ほとんどのアプリをこのノードで追加、割り当て、監視します。</span><span class="sxs-lookup"><span data-stu-id="313c8-195">**Apps** - This node is where you add, assign, and monitor most of your apps.</span></span>
    - [<span data-ttu-id="313c8-196">アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="313c8-196">Add apps</span></span>](apps-add.md)
    - [<span data-ttu-id="313c8-197">アプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="313c8-197">Assign apps</span></span>](apps-deploy.md)
    - [<span data-ttu-id="313c8-198">アプリの監視</span><span class="sxs-lookup"><span data-stu-id="313c8-198">Monitor apps</span></span>](apps-monitor.md)
- <span data-ttu-id="313c8-199">**[アプリの構成ポリシー]** - ユーザーがアプリを実行するときに必要となる可能性がある設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="313c8-199">**App configuration policies** - App configuration policies let you supply settings that might be required when a user runs an app.</span></span>
    - [<span data-ttu-id="313c8-200">iOS アプリ構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="313c8-200">iOS app configuration policies</span></span>](app-configuration-policies-use-ios.md)
    - [<span data-ttu-id="313c8-201">Android アプリ構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="313c8-201">Android app configuration policies</span></span>](app-configuration-policies-use-android.md)
- <span data-ttu-id="313c8-202">**[アプリ保護ポリシー]** - アプリに設定を関連付けて、アプリで使用する会社のデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="313c8-202">**App protection policies** - Lets you associate settings with an app to help protect the company data it uses.</span></span> <span data-ttu-id="313c8-203">たとえば、アプリの機能による他のアプリとの通信を制限することや、会社のアプリにアクセスしようとするユーザーに PIN の入力を求めることができます。</span><span class="sxs-lookup"><span data-stu-id="313c8-203">For example, you might restrict the capabilities of an app to communicate with other apps, or require the user to enter a PIN to access a company app.</span></span>
    - [<span data-ttu-id="313c8-204">アプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="313c8-204">App protection policies</span></span>](app-protection-policies.md)
- <span data-ttu-id="313c8-205">**[アプリの選択的ワイプ]** - 選択したユーザーのデバイスから会社のデータのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="313c8-205">**App selective wipe** - Remove only corporate data from a users device you select.</span></span>
    - [<span data-ttu-id="313c8-206">アプリの選択的ワイプ</span><span class="sxs-lookup"><span data-stu-id="313c8-206">App selective wipe</span></span>](apps-selective-wipe.md)
- <span data-ttu-id="313c8-207">**[iOS プロビジョニング プロファイル]** - iOS アプリには、プロビジョニング プロファイルと、証明書によって署名されたコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="313c8-207">**iOS provisioning profiles** - iOS apps include a provisioning profile and code that is signed by a certificate.</span></span> <span data-ttu-id="313c8-208">証明書の期限が切れると、アプリを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="313c8-208">When the certificate expires, the app can no longer be run.</span></span> <span data-ttu-id="313c8-209">Intune には、有効期限が近づいているアプリを持つデバイスに新しいプロビジョニング プロファイルのポリシーを事前に割り当てるツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="313c8-209">Intune gives you the tools to proactively assign a new provisioning profile policy to devices that have apps that are nearing expiry.</span></span>
    - [<span data-ttu-id="313c8-210">iOS アプリ プロビジョニング プロファイル</span><span class="sxs-lookup"><span data-stu-id="313c8-210">iOS app provisioning profiles</span></span>](app-provisioning-profile-ios.md)

### <a name="monitor"></a><span data-ttu-id="313c8-211">モニター</span><span class="sxs-lookup"><span data-stu-id="313c8-211">Monitor</span></span>
- <span data-ttu-id="313c8-212">**[ライセンスされたアプリ]** - アプリ ストアからのボリューム購入アプリの表示、割り当て、監視を行います。</span><span class="sxs-lookup"><span data-stu-id="313c8-212">**Licensed Apps** - View, assign, and monitor volume-purchased apps from the app stores.</span></span>
    - [<span data-ttu-id="313c8-213">ビジネス向け Microsoft ストアのボリューム購入アプリ</span><span class="sxs-lookup"><span data-stu-id="313c8-213">Microsoft Store for Business volume-purchased apps</span></span>](windows-store-for-business.md)
- <span data-ttu-id="313c8-214">**[検出されたアプリ]** - Intune によって割り当てられ、デバイスにインストールされたすべてのアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="313c8-214">**Discovered Apps** - Shows all apps that were assigned by Intune, and installed on a device.</span></span>
- <span data-ttu-id="313c8-215">**[アプリ インストールの状態]** - 作成したアプリの割り当て状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="313c8-215">**App Install Status** - Shows the status of an app assignment you created.</span></span>
- <span data-ttu-id="313c8-216">**[アプリの保護状態]** - 選択したユーザーのアプリ保護ポリシーの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="313c8-216">**App protection status** - Shows the status of an app protection policy for a user you select.</span></span>

<span data-ttu-id="313c8-217">詳細については、[アプリの監視](apps-monitor.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="313c8-217">For details, see [Monitor apps](apps-monitor.md)</span></span>

### <a name="setup"></a><span data-ttu-id="313c8-218">Setup</span><span class="sxs-lookup"><span data-stu-id="313c8-218">Setup</span></span>
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- <span data-ttu-id="313c8-219">**[ビジネス向け Microsoft ストア]** - ビジネス向け Microsoft ストアとの統合を設定します。</span><span class="sxs-lookup"><span data-stu-id="313c8-219">**Microsoft Store for Business** - Set up integration to the Microsoft Store for Business.</span></span> <span data-ttu-id="313c8-220">その後、購入済みのアプリケーションを Intune に同期して割り当て、ライセンスの使用状況を追跡できるようになります。</span><span class="sxs-lookup"><span data-stu-id="313c8-220">Afterwards, you can synchronize purchased applications to Intune, assign them, and track your license usage.</span></span>
    - [<span data-ttu-id="313c8-221">ビジネス向け Microsoft ストアのボリューム購入アプリ</span><span class="sxs-lookup"><span data-stu-id="313c8-221">Microsoft Store for Business volume-purchased apps</span></span>](windows-store-for-business.md)
- <span data-ttu-id="313c8-222">**[ポータル サイトのブランド化]** - 会社のポータルをカスタマイズして会社のブランドを付与します。</span><span class="sxs-lookup"><span data-stu-id="313c8-222">**Company Portal branding** - Customize the Company Portal to give it your company branding.</span></span>
    - [<span data-ttu-id="313c8-223">会社のポータルの構成</span><span class="sxs-lookup"><span data-stu-id="313c8-223">Company portal configuration</span></span>](company-portal-app.md)
