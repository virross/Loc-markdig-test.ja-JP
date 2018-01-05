---
title: "ポリシーを使用してデバイスの設定を管理する"
description: "Intune を使用して、管理する登録デバイスの設定と機能を制御するポリシーを作成して展開します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b105d8e610efe558c99d50eb8097f27d3708397c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="manage-settings-and-features-on-your-devices-with-microsoft-intune-policies"></a><span data-ttu-id="e5c84-103">Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する</span><span class="sxs-lookup"><span data-stu-id="e5c84-103">Manage settings and features on your devices with Microsoft Intune policies</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e5c84-104">Microsoft Intune の*ポリシー*は、モバイル デバイスとコンピューターの機能を制御する設定のグループです。</span><span class="sxs-lookup"><span data-stu-id="e5c84-104">Microsoft Intune *policies* are groups of settings that control features on mobile devices and computers.</span></span> <span data-ttu-id="e5c84-105">ポリシーは、推奨設定やカスタム設定を含むテンプレートを使用することで作成し、デバイスまたはユーザー グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-105">You create policies by using templates that contain recommended or custom settings, and then you deploy them to device or user groups.</span></span>

## <a name="types-of-policies"></a><span data-ttu-id="e5c84-106">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="e5c84-106">Types of policies</span></span>

<span data-ttu-id="e5c84-107">Intune のポリシーは以下のカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-107">Intune policies fall into the following categories.</span></span> <span data-ttu-id="e5c84-108">使用するカテゴリは、ポリシーの作成方法と展開方法に影響があります。</span><span class="sxs-lookup"><span data-stu-id="e5c84-108">The category that you use affects how you create and deploy the policy.</span></span>


- <span data-ttu-id="e5c84-109">**構成ポリシー:** デバイスのセキュリティ設定と機能を管理するために一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-109">**Configuration policies**: These are commonly used to manage security settings and features on your devices.</span></span> <span data-ttu-id="e5c84-110">ポリシーの作成方法と展開方法、使用できる設定については、このトピックの情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-110">Use the information in this topic to learn about how to create and deploy these policies and to explore the available settings.</span></span>
- <span data-ttu-id="e5c84-111">**デバイス コンプライアンス ポリシー:** デバイスが条件付きアクセス ポリシーによって "準拠している" と見なされるために遵守する必要がある規則および設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-111">**Device compliance policies**: These define the rules and settings that a device must comply with in order to be considered compliant by conditional access polices.</span></span> <span data-ttu-id="e5c84-112">コンプライアンス ポリシーを使用して、条件付きアクセスとは別に、デバイスのコンプライアンスを監視および修復することもできます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-112">You can also use compliance policies to monitor and remediate  the compliance of devices independent of conditional access.</span></span>
<span data-ttu-id="e5c84-113">詳細については、「[Microsoft Intune のデバイス コンプライアンス ポリシー](introduction-to-device-compliance-policies-in-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-113">For details, see [Device compliance policies in Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).</span></span>
- <span data-ttu-id="e5c84-114">**条件付きアクセス ポリシー:** 指定する条件に基づいて電子メールおよびその他のサービスをセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-114">**Conditional access polices**: These policies help you secure email and other services, depending on conditions that you specify.</span></span>
<span data-ttu-id="e5c84-115">詳細については、「[Microsoft Intune を使用して電子メールおよび O365 サービスへのアクセスを制限する](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-115">For details, see [Restrict access to email and O365 services with Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span></span>
- <span data-ttu-id="e5c84-116">**会社のデバイスの登録ポリシー:** 会社のデバイスの登録ポリシーについては、「[Microsoft Intune を使用した iOS および Mac の管理のセットアップ](set-up-ios-and-mac-management-with-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-116">**Corporate device enrollment policies**: For information about corporate device enrollment policies, see [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md).</span></span>
- <span data-ttu-id="e5c84-117">**リソース アクセス ポリシー:** これらのポリシーを使用すると、ユーザーはどこにいても仕事を確実に遂行するために必要なファイルとリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-117">**Resource access policies**: These policies work together to help your users gain access to the files and resources that they need to do their work successfully, wherever they are.</span></span>
<span data-ttu-id="e5c84-118">詳細については、「[Microsoft Intune を使用して、会社のリソースへのアクセスを有効にする](enable-access-to-company-resources-with-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-118">For details, see [Enable access to company resources with Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md).</span></span>


<span data-ttu-id="e5c84-119">Intune ポリシーの一覧については、「[Microsoft Intune policy reference (Microsoft Intune ポリシー リファレンス)](microsoft-intune-policy-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-119">For a complete list of Intune policies, see [Microsoft Intune policy reference](microsoft-intune-policy-reference.md).</span></span>

## <a name="create-a-configuration-policy"></a><span data-ttu-id="e5c84-120">構成ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e5c84-120">Create a configuration policy</span></span>

1.  <span data-ttu-id="e5c84-121">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[ポリシー]、** &gt; **[構成ポリシー]** &gt; **[追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-121">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Policy** &gt; **Configuration Policies** &gt; **Add**.</span></span>

2.  <span data-ttu-id="e5c84-122">作成するポリシーを選択します。ポリシーの推奨設定 (使用可能な場合。この設定は後で変更できます) を使用するか、独自の設定でカスタム ポリシーを作成するか選びます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-122">Choose the policy that you want, choose to use the recommended settings for the policy (if available; you can change these settings later), or choose to create a custom policy with your own settings.</span></span>

    > [!TIP]
    > <span data-ttu-id="e5c84-123">適切なポリシーを選択する方法については、「[Microsoft Intune ポリシー リファレンス](microsoft-intune-policy-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-123">For help choosing the right policy, see the [Microsoft Intune policy reference](microsoft-intune-policy-reference.md).</span></span>

3.  <span data-ttu-id="e5c84-124">準備ができたら、 **[ポリシーを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-124">When you are ready, choose **Create Policy**.</span></span>

4.  <span data-ttu-id="e5c84-125">**[ポリシーを作成する]** ページで、ポリシーの名前とオプションの説明を構成します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-125">On the **Create Policy** page, configure a name and optional description for the policy.</span></span>

5.  <span data-ttu-id="e5c84-126">必要なポリシー設定を構成して、**[ポリシーの保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-126">Configure the required policy settings, and then choose **Save Policy**.</span></span>

    <span data-ttu-id="e5c84-127">ポリシー設定の詳細については、次の一覧から使用するポリシーの種類を選択してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-127">If you need help with any policy settings, choose your policy type from the following list:</span></span>

    - [<span data-ttu-id="e5c84-128">iOS デバイス向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-128">Settings for iOS devices</span></span>](ios-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-129">Android デバイス向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-129">Settings for Android devices</span></span>](android-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-130">Android for Work デバイス向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-130">Settings for Android for Work devices</span></span>](android-for-work-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-131">Windows 8 および Windows 8.1 デバイス向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-131">Settings for Windows 8 and Windows 8.1 devices</span></span>](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-132">Windows Phone 8.1 デバイス向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-132">Settings for Windows Phone 8.1 devices</span></span>](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-133">Windows 10 デスクトップおよびモバイル デバイス向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-133">Settings for Windows 10 desktop and mobile devices</span></span>](windows-10-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-134">Windows チーム デバイス向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-134">Settings for Windows Team devices</span></span>](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-135">Windows エディション アップグレード向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-135">Settings for Windows edition upgrade</span></span>](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-136">Mac OS X デバイスの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-136">Settings for Mac OS X devices</span></span>](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-137">Exchange ActiveSync 向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-137">Settings for Exchange ActiveSync</span></span>](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-138">使用条件ポリシー向けの設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-138">Settings for the terms and conditions policy</span></span>](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [<span data-ttu-id="e5c84-139">モバイル デバイス (レガシ) 向けの全般設定</span><span class="sxs-lookup"><span data-stu-id="e5c84-139">General settings for mobile devices (legacy)</span></span>](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  <span data-ttu-id="e5c84-140">確認ダイアログ ボックスで、**[はい]** を選択してポリシーをすぐに展開するか、**[いいえ]** を選択して展開せずにポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-140">In the confirmation dialog box, choose **Yes** to deploy the policy now, or choose **No** to create the policy without deploying it.</span></span>

<span data-ttu-id="e5c84-141">**[ポリシー]** ワークスペースの各種ポリシーについてのセクションを参照し、新しいポリシーを表示して編集します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-141">You can view and edit the new policy by browsing through the sections for each policy type in the **Policy** workspace.</span></span>

<span data-ttu-id="e5c84-142">推奨設定を使用するポリシーを作成する場合、新しいポリシーの名前は、テンプレート名と、日付、時刻の組み合わせになります。</span><span class="sxs-lookup"><span data-stu-id="e5c84-142">When you create a policy that uses the recommended settings, the name of the new policy is a combination of the template name, date, and time.</span></span> <span data-ttu-id="e5c84-143">ポリシーを編集するときに、名前は、編集した時間と日付で更新されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-143">When you edit the policy, the name is updated with the time and date of the edit.</span></span>

<span data-ttu-id="e5c84-144">ポリシーを作成したら、通常 1 つ以上のユーザー グループまたはデバイスにポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-144">After you create a policy, you will typically want to deploy it to one or more groups of users or devices.</span></span>

> [!TIP]
> <span data-ttu-id="e5c84-145">すべての種類のポリシーを展開するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e5c84-145">You don't deploy all policy types.</span></span> <span data-ttu-id="e5c84-146">たとえば、モバイル アプリケーション管理 (MAM) ポリシーは展開されません。</span><span class="sxs-lookup"><span data-stu-id="e5c84-146">For example, the mobile application management (MAM) policy is not deployed.</span></span> <span data-ttu-id="e5c84-147">代わりに、この種類のポリシーはアプリに関連付けられ、このアプリが展開されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-147">This policy type is instead associated with an app, which you then deploy.</span></span>

## <a name="deploy-a-configuration-policy"></a><span data-ttu-id="e5c84-148">構成ポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="e5c84-148">Deploy a configuration policy</span></span>

1.  <span data-ttu-id="e5c84-149">**[ポリシー]** ワークスペースで、展開するポリシーを選び、**[展開の管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-149">In the **Policy** workspace, select the policy that you want to deploy, and then choose **Manage Deployment**.</span></span>

2.  <span data-ttu-id="e5c84-150">**[展開の管理]** ダイアログ ボックスで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-150">In the **Manage Deployment** dialog box:</span></span>

    -   <span data-ttu-id="e5c84-151">ポリシーを展開するには、ポリシーを展開する対象となる 1 つ以上のグループを選択して、**[追加]** &gt; **[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-151">To deploy the policy, select one or more groups to which you want to deploy the policy, and then choose **Add** &gt; **OK**.</span></span>

    -   <span data-ttu-id="e5c84-152">ポリシーを展開せずにダイアログ ボックスを閉じるには、**[キャンセル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-152">To close the dialog box without deploying the policy, choose **Cancel**.</span></span>

<span data-ttu-id="e5c84-153">展開済みポリシーを選択すると、ポリシー一覧の下部に展開についての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-153">When you select a deployed policy, you can view further information about the deployment in the lower part of the policies list.</span></span>

## <a name="manage-policies"></a><span data-ttu-id="e5c84-154">ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="e5c84-154">Manage policies</span></span>

1.  <span data-ttu-id="e5c84-155">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[ポリシー]** を選択し、管理するポリシーを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-155">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Policy**, and then browse to and select the policy that you want to manage.</span></span>

2.  <span data-ttu-id="e5c84-156">次のアクションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-156">Select one of the following actions:</span></span>

- <span data-ttu-id="e5c84-157">**編集** - 選択したポリシーのプロパティを開き、変更できます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-157">**Edit**: Open the properties for the selected policy so that you can make changes.</span></span>
- <span data-ttu-id="e5c84-158">**削除** - 選択したポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-158">**Delete**: Delete the selected policy.</span></span><br><span data-ttu-id="e5c84-159">ポリシーを削除すると、展開先のすべてのグループから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-159">When you delete a policy, it is removed from all groups to which it was deployed.</span></span>
- <span data-ttu-id="e5c84-160">**展開の管理** - ポリシーを展開するグループを選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-160">**Manage Deployment**: Select the group that you want to deploy the policy to, and then choose **Add**.</span></span>


## <a name="frequently-asked-questions-about-intune-policies"></a><span data-ttu-id="e5c84-161">Intune ポリシーについてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="e5c84-161">Frequently asked questions about Intune policies</span></span>

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-deployed"></a><span data-ttu-id="e5c84-162">モバイル デバイスが展開後にポリシーまたはアプリを取得するのにどれくらいの時間がかかりますか。</span><span class="sxs-lookup"><span data-stu-id="e5c84-162">How long does it take for mobile devices to get a policy or apps after they have been deployed?</span></span>
<span data-ttu-id="e5c84-163">ポリシーまたはアプリが展開されると、Intune はデバイスに対して、Intune サービスにチェックインする必要があることをすぐに通知し始めます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-163">When a policy or an app is deployed, Intune immediately begins attempting to notify the device that it should check in with the Intune service.</span></span> <span data-ttu-id="e5c84-164">これにかかる時間は通常 5 分未満です。</span><span class="sxs-lookup"><span data-stu-id="e5c84-164">This typically takes less than five minutes.</span></span>

<span data-ttu-id="e5c84-165">最初の通知が送信された後、デバイスがチェックインしてポリシーを取得しない場合、Intune はさらに 3 回試行します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-165">If a device doesn't check in to get the policy after the first notification is sent, Intune makes three more attempts.</span></span>  <span data-ttu-id="e5c84-166">デバイスがオフライン (たとえば、デバイスの電源がオフである、ネットワークに接続されていない) の場合、通知を受信していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e5c84-166">If the device is offline (for example, it is turned off or not connected to a network), it might not receive the notifications.</span></span> <span data-ttu-id="e5c84-167">この場合、デバイスは次回のスケジュールされた Intune サービスへのチェックインでポリシーを取得することになります。チェックイン頻度は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5c84-167">In this case, the device will get the policy on its next scheduled check-in with the Intune service as follows:</span></span>

- <span data-ttu-id="e5c84-168">iOS と Mac OS X: 6 時間ごと</span><span class="sxs-lookup"><span data-stu-id="e5c84-168">iOS and Mac OS X: Every 6 hours.</span></span>
- <span data-ttu-id="e5c84-169">Android: 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="e5c84-169">Android: Every 8 hours.</span></span>
- <span data-ttu-id="e5c84-170">Windows Phone: 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="e5c84-170">Windows Phone: Every 8 hours.</span></span>
- <span data-ttu-id="e5c84-171">デバイスとして登録された Windows 8.1 および Windows 10 PC: 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="e5c84-171">Windows 8.1 and Windows 10 PCs enrolled as devices: Every 8 hours.</span></span>

<span data-ttu-id="e5c84-172">登録してすぐのデバイスでは、チェックイン頻度が高くなります。頻度は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5c84-172">If the device has just enrolled, the check-in frequency will be more frequent, as follows:</span></span>

- <span data-ttu-id="e5c84-173">iOS と Mac OS X: 6 時間まで 15 分ごと、その後 6 時間ごと</span><span class="sxs-lookup"><span data-stu-id="e5c84-173">iOS and Mac OS X: Every 15 minutes for 6 hours, and then every 6 hours.</span></span>
- <span data-ttu-id="e5c84-174">Android: 15 分まで 3 分ごと、その後の 2 時間は 15 分ごと、その後 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="e5c84-174">Android: Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours.</span></span>
- <span data-ttu-id="e5c84-175">Windows Phone: 15 分まで 5 分ごと、その後の 2 時間は 15 分ごと、その後 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="e5c84-175">Windows Phone: Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours.</span></span>
- <span data-ttu-id="e5c84-176">デバイスとして登録された Windows PC: 30 分まで 3 分ごと、その後 8 時間ごと</span><span class="sxs-lookup"><span data-stu-id="e5c84-176">Windows PCs enrolled as devices: Every 3 minutes for 30 minutes, and then every 8 hours.</span></span>

<span data-ttu-id="e5c84-177">また、ユーザーはポータル サイト アプリを起動し、デバイスを同期して、いつでもすぐにポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-177">Users can also open the Company Portal app and sync the device to immediately check for the policy anytime.</span></span>

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a><span data-ttu-id="e5c84-178">どのような操作を行うと Intune は通知をデバイスにすぐに送信しますか。</span><span class="sxs-lookup"><span data-stu-id="e5c84-178">What actions cause Intune to immediately send a notification to a device?</span></span>
<span data-ttu-id="e5c84-179">デバイスは、チェックインを指示する通知を受け取ったとき、または定期的にスケジュールされたチェックイン時に Intune にチェックインします。</span><span class="sxs-lookup"><span data-stu-id="e5c84-179">Devices check in with Intune either when they receive a notification that tells them to check in or during their regularly scheduled check-in.</span></span>  <span data-ttu-id="e5c84-180">ワイプ、ロック、パスコードのリセット、アプリの展開、プロファイルの展開 (Wi-Fi、VPN、メールなど)、ポリシーの展開などの操作で具体的にデバイスまたはユーザーを対象とする場合、Intune は、デバイスが Intune サービスにチェックインしてこれらの更新プログラムを受信するよう指示する通知をすぐに開始します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-180">When you target a device or user specifically with an action such as a wipe, lock, passcode reset, app deployment, profile deployment (Wi-Fi, VPN, email, etc.), or policy deployment, Intune will immediately begin trying to notify the device that it should check in with the Intune service to receive these updates.</span></span>

<span data-ttu-id="e5c84-181">ポータル サイトの連絡先情報の修正など、他の変更ではデバイスへの通知はすぐに行われません。</span><span class="sxs-lookup"><span data-stu-id="e5c84-181">Other changes, such as revising the contact information in the company portal, do not cause an immediate notification to devices.</span></span>

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a><span data-ttu-id="e5c84-182">複数のポリシーが同じユーザーまたはデバイスに展開される場合、どの設定が適用されるのかどうすればわかりますか。</span><span class="sxs-lookup"><span data-stu-id="e5c84-182">If multiple policies are deployed to the same user or device, how do I know which settings will get applied?</span></span>
<span data-ttu-id="e5c84-183">2 つ以上のポリシーが同じユーザーまたはデバイスに展開される場合、適用される設定の評価は個々の設定レベルで行われます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-183">When two or more policies are deployed to the same user or device, the evaluation for which setting is applied happens at the individual setting level:</span></span>

-   <span data-ttu-id="e5c84-184">コンプライアンス ポリシー設定は常に構成ポリシー設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-184">Compliance policy settings always have precedence over configuration policy settings.</span></span>

-   <span data-ttu-id="e5c84-185">異なるコンプライアンス ポリシーの同じ設定について評価する場合、最も制限の厳しいコンプライアンス ポリシー設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-185">The most restrictive compliance policy setting is applied if it is evaluated against the same setting in a different compliance policy.</span></span>

-   <span data-ttu-id="e5c84-186">構成ポリシーの設定が別の構成ポリシーの設定と競合する場合、Intune コンソールにその競合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-186">If a configuration policy setting conflicts with a setting in a different configuration policy, this conflict will be displayed in the Intune console.</span></span> <span data-ttu-id="e5c84-187">このような競合は手動で解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5c84-187">You must manually resolve such conflicts.</span></span>

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a><span data-ttu-id="e5c84-188">モバイル アプリケーション管理ポリシーが互いに競合する場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="e5c84-188">What happens when mobile application management policies conflict with each other?</span></span> <span data-ttu-id="e5c84-189">どのポリシーがアプリに適用されますか。</span><span class="sxs-lookup"><span data-stu-id="e5c84-189">Which one will be applied to the app?</span></span>
<span data-ttu-id="e5c84-190">競合している値は、(リセットする前の PIN の試行で使用するような) 番号入力フィールドを除き、MAM ポリシーで使用可能な最も制限の厳しい設定になっています。</span><span class="sxs-lookup"><span data-stu-id="e5c84-190">Conflict values are the most restrictive settings available in a MAM policy, except for the number entry fields (like PIN attempts before reset).</span></span>  <span data-ttu-id="e5c84-191">番号入力フィールドは、推奨設定のオプションを使用することでコンソールで MAM ポリシーを作成した場合と同じ値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-191">The number entry fields will be set the same as the values, as if you created a MAM policy in the console by using the recommended settings option.</span></span>

<span data-ttu-id="e5c84-192">競合は、2 つのポリシー設定が同じ場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-192">Conflicts occur when two policy settings are the same.</span></span>  <span data-ttu-id="e5c84-193">たとえば、コピー/貼り付けの設定以外は同じ MAM ポリシーを 2 つ構成したとします。</span><span class="sxs-lookup"><span data-stu-id="e5c84-193">For example, you configured two MAM policies that are identical except for the copy/paste setting.</span></span>  <span data-ttu-id="e5c84-194">この場合、コピー/貼り付けの設定は最も厳しい値になりますが、残りの設定は構成したとおりに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-194">In this scenario, the copy/paste setting will be set to the most restrictive value, but the rest of the settings will be applied as configured.</span></span>

<span data-ttu-id="e5c84-195">1 つのポリシーをアプリに展開し、このポリシーが有効になった後、2 つ目のポリシーを展開すると、2 つ目のポリシーは競合の状態になりますが、最初のポリシーは優先され、適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="e5c84-195">If one policy is deployed to the app and takes effect, and then a second one is deployed, the first one will take precedence and stay applied, while the second shows in conflict.</span></span> <span data-ttu-id="e5c84-196">両方を同時に適用する (優先されるポリシーがない) 場合は、両方が競合の状態になります。</span><span class="sxs-lookup"><span data-stu-id="e5c84-196">If they are both applied at the same time, meaning that there is no preceding policy, then they will both be in conflict.</span></span> <span data-ttu-id="e5c84-197">競合する設定は、最も制限の厳しい値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-197">Any conflicting settings will be set to the most restrictive values.</span></span>

### <a name="what-happens-when-ios-custom-policies-conflict"></a><span data-ttu-id="e5c84-198">iOS カスタム ポリシーが競合するとどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="e5c84-198">What happens when iOS custom policies conflict?</span></span>
<span data-ttu-id="e5c84-199">Intune は Apple 構成ファイルのペイロードまたはカスタム Open Mobile Alliance Uniform Resource Identifier (OMA-URI) ポリシーを評価しません。</span><span class="sxs-lookup"><span data-stu-id="e5c84-199">Intune does not evaluate the payload of Apple Configuration files or a custom Open Mobile Alliance Uniform Resource Identifier (OMA-URI) policy.</span></span> <span data-ttu-id="e5c84-200">配信メカニズムとしてのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-200">It merely serves as the delivery mechanism.</span></span>

<span data-ttu-id="e5c84-201">カスタム ポリシーを展開するときは、構成した設定がコンプライアンス、構成、または他のカスタム ポリシーと競合していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-201">When you deploy a custom policy, ensure that the configured settings do not conflict with compliance, configuration, or other custom policies.</span></span> <span data-ttu-id="e5c84-202">設定が競合しているカスタム ポリシーの場合、設定が適用される順序はランダムになります。</span><span class="sxs-lookup"><span data-stu-id="e5c84-202">In the case of a custom policy with settings conflicts, the order in which settings are applied is random.</span></span>

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a><span data-ttu-id="e5c84-203">ポリシーが削除された場合または適用できなくなった場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="e5c84-203">What happens when a policy is deleted or no longer applicable?</span></span>
<span data-ttu-id="e5c84-204">ポリシーを削除した場合やポリシーを展開したグループからデバイスを削除した場合は、次のリストに従ってポリシーと設定がデバイスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-204">When you delete a policy, or you remove a device from a group to which a policy was deployed, the policy and settings will be removed from the device according to the following lists.</span></span>

#### <a name="enrolled-devices"></a><span data-ttu-id="e5c84-205">[登録済みデバイス]</span><span class="sxs-lookup"><span data-stu-id="e5c84-205">Enrolled devices</span></span>

- <span data-ttu-id="e5c84-206">Wi-Fi、VPN、証明書、電子メールのプロファイル: これらのプロファイルは、すべてのサポートされる登録デバイスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-206">Wi-Fi, VPN, certificate, and email profiles: These profiles are removed from all supported enrolled devices.</span></span>
- <span data-ttu-id="e5c84-207">その他のすべてのポリシーの種類:</span><span class="sxs-lookup"><span data-stu-id="e5c84-207">All other policy types:</span></span>
    - <span data-ttu-id="e5c84-208">**Windows および Android デバイス**: 設定はデバイスから削除されません。</span><span class="sxs-lookup"><span data-stu-id="e5c84-208">**Windows and Android devices**: Settings are not removed from the device.</span></span>
    - <span data-ttu-id="e5c84-209">**Windows Phone 8.1 デバイス**: 次の設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-209">**Windows Phone 8.1 devices**: The following settings are removed:</span></span>
        - <span data-ttu-id="e5c84-210">モバイル デバイスのロックを解除するパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="e5c84-210">Require a password to unlock mobile devices</span></span>
        - <span data-ttu-id="e5c84-211">単純なパスワードを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-211">Allow simple passwords</span></span>
        - <span data-ttu-id="e5c84-212">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="e5c84-212">Minimum password length</span></span>
        - <span data-ttu-id="e5c84-213">必要なパスワードの種類</span><span class="sxs-lookup"><span data-stu-id="e5c84-213">Required password type</span></span>
        - <span data-ttu-id="e5c84-214">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="e5c84-214">Password expiration (days)</span></span>
        - <span data-ttu-id="e5c84-215">パスワードの履歴を記憶する</span><span class="sxs-lookup"><span data-stu-id="e5c84-215">Remember password history</span></span>
        - <span data-ttu-id="e5c84-216">デバイスをワイプするまでの連続サインイン エラーの数</span><span class="sxs-lookup"><span data-stu-id="e5c84-216">Number of repeated sign-in failures to allow before the device is wiped</span></span>
        - <span data-ttu-id="e5c84-217">パスワードが必要になるまでの非アクティブ状態の時間 (分)</span><span class="sxs-lookup"><span data-stu-id="e5c84-217">Minutes of inactivity before password is required</span></span>
        - <span data-ttu-id="e5c84-218">必要なパスワードの種類 - 文字セットの最小数</span><span class="sxs-lookup"><span data-stu-id="e5c84-218">Required password type – minimum number of character sets</span></span>
        - <span data-ttu-id="e5c84-219">カメラを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-219">Allow camera</span></span>
        - <span data-ttu-id="e5c84-220">モバイル デバイスの暗号化を要求する</span><span class="sxs-lookup"><span data-stu-id="e5c84-220">Require encryption on mobile device</span></span>
        - <span data-ttu-id="e5c84-221">リムーバブル記憶域を許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-221">Allow removable storage</span></span>
        - <span data-ttu-id="e5c84-222">Web ブラウザーを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-222">Allow web browser</span></span>
        - <span data-ttu-id="e5c84-223">アプリケーション ストアを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-223">Allow application store</span></span>
        - <span data-ttu-id="e5c84-224">画面のキャプチャを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-224">Allow screen capture</span></span>
        - <span data-ttu-id="e5c84-225">位置情報を許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-225">Allow geolocation</span></span>
        - <span data-ttu-id="e5c84-226">Microsoft アカウントを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-226">Allow Microsoft account</span></span>
        - <span data-ttu-id="e5c84-227">コピーと貼り付けを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-227">Allow copy and paste</span></span>
        - <span data-ttu-id="e5c84-228">Wi-Fi テザリングを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-228">Allow Wi-Fi tethering</span></span>
        - <span data-ttu-id="e5c84-229">無料 Wi-Fi スポットへの自動接続を許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-229">Allow automatic connection to free Wi-Fi hotspots</span></span>
        - <span data-ttu-id="e5c84-230">Wi-Fi スポットの報告を許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-230">Allow Wi-Fi hotspot reporting</span></span>
        - <span data-ttu-id="e5c84-231">工場出荷時のリセットを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-231">Allow factory reset</span></span>
        - <span data-ttu-id="e5c84-232">Bluetooth を許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-232">Allow Bluetooth</span></span>
        - <span data-ttu-id="e5c84-233">NFC を許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-233">Allow NFC</span></span>
        - <span data-ttu-id="e5c84-234">Wi-Fi を許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-234">Allow Wi-Fi</span></span>

    - <span data-ttu-id="e5c84-235">**iOS**: 次を除き、すべての設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-235">**iOS**: All settings are removed, except:</span></span>
        - <span data-ttu-id="e5c84-236">音声通話ローミングを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-236">Allow voice roaming</span></span>
        - <span data-ttu-id="e5c84-237">データ ローミングを許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-237">Allow data roaming</span></span>
        - <span data-ttu-id="e5c84-238">ローミング中の自動同期を許可する</span><span class="sxs-lookup"><span data-stu-id="e5c84-238">Allow automatic synchronization while roaming</span></span>

#### <a name="windows-pcs-running-the-intune-client-software"></a><span data-ttu-id="e5c84-239">Intune クライアント ソフトウェアを実行している Windows PC</span><span class="sxs-lookup"><span data-stu-id="e5c84-239">Windows PCs running the Intune client software</span></span>

- <span data-ttu-id="e5c84-240">**Endpoint Protection 設定**: 設定は、推奨値に復元されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-240">**Endpoint Protection settings**: Settings are restored to their recommended values.</span></span> <span data-ttu-id="e5c84-241">例外は、**[Microsoft Active Protection Service に参加する]** の設定だけで、既定値は **[いいえ]** です。</span><span class="sxs-lookup"><span data-stu-id="e5c84-241">The only exception is the **Join Microsoft Active Protection Service** setting, for which the default value is **No**.</span></span> <span data-ttu-id="e5c84-242">詳細については、「[Microsoft Intune の Endpoint Protection を使用して Windows PC を保護する](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-242">For details, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).</span></span>
- <span data-ttu-id="e5c84-243">**ソフトウェアの更新プログラムの設定**: 設定は、オペレーティング システムの既定の状態にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-243">**Software updates settings**: Settings are reset to the default state for the operating system.</span></span> <span data-ttu-id="e5c84-244">詳細については、「[Microsoft Intune でソフトウェア更新プログラムを使用して Windows PC を最新の状態に保つ](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-244">For details, see [Keep Windows PCs up to date with software updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).</span></span>
- <span data-ttu-id="e5c84-245">**Microsoft Intune Center の設定**: ポリシーで構成されたサポートの連絡先情報は、すべてコンピューターから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-245">**Microsoft Intune Center settings**: Any support contact information that was configured by the policy is deleted from computers.</span></span>
- <span data-ttu-id="e5c84-246">**Windows ファイアウォールの設定**: 設定は、コンピューターのオペレーティング システムの既定にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="e5c84-246">**Windows Firewall settings**: Settings are reset to the default for the computer operating system.</span></span> <span data-ttu-id="e5c84-247">詳細については、「[Microsoft Intune の Endpoint Protection を使用して Windows PC を保護する](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-247">For details, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).</span></span>


### <a name="how-can-i-refresh-the-policies-on-a-device-to-ensure-that-they-are-current-applies-to-windows-pcs-running-the-intune-client-software-only"></a><span data-ttu-id="e5c84-248">どうしたらデバイスのポリシーを更新して最新の状態に保つことができますか (Intune クライアント ソフトウェアを実行している Windows PC にのみ適用されます)。</span><span class="sxs-lookup"><span data-stu-id="e5c84-248">How can I refresh the policies on a device to ensure that they are current (applies to Windows PCs running the Intune client software only)?</span></span>

1.  <span data-ttu-id="e5c84-249">任意のデバイス グループで、ポリシーを更新するデバイスを選択して、**[リモート タスク]** &gt; **[ポリシーの更新]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-249">In any device group, select the devices on which you want to refresh the policies, and then choose **Remote Tasks** &gt; **Refresh Policies**.</span></span>
2.  <span data-ttu-id="e5c84-250">Intune 管理コンソールの右下にある **[リモート タスク]** を選択し、タスクの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="e5c84-250">Choose **Remote Tasks** in the lower-right corner of the Intune administration console to check the task status.</span></span>

### <a name="where-can-i-find-help-troubleshooting-policies"></a><span data-ttu-id="e5c84-251">ポリシーのトラブルシューティングのヘルプはどこにありますか?</span><span class="sxs-lookup"><span data-stu-id="e5c84-251">Where can I find help troubleshooting policies?</span></span>

<span data-ttu-id="e5c84-252">「[Microsoft Intune のポリシーのトラブルシューティング](/intune-classic/troubleshoot/troubleshoot-policies-in-microsoft-intune)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e5c84-252">See [Troubleshoot policies in Microsoft Intune](/intune-classic/troubleshoot/troubleshoot-policies-in-microsoft-intune).</span></span>
