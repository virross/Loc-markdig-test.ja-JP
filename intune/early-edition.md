---
title: "初期エディション"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f4e661d1b50d7bf7dc0867ed11cec865b04bbdac
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="the-early-edition-for-microsoft-intune---december-2017"></a><span data-ttu-id="2901c-102">Microsoft Intune の初期エディション - 2017 年 12 月</span><span class="sxs-lookup"><span data-stu-id="2901c-102">The early edition for Microsoft Intune - December 2017</span></span>

<span data-ttu-id="2901c-103">**初期エディション**では、Microsoft Intune の今後のリリースで予定されている新機能の一覧を提供しています。</span><span class="sxs-lookup"><span data-stu-id="2901c-103">The **early edition** provides a list of features that are coming in upcoming releases of Microsoft Intune.</span></span> <span data-ttu-id="2901c-104">ここに記載されている情報は、限られた範囲について開示されたものであり、また今後変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2901c-104">This information is provided on a limited basis and is subject to change.</span></span> <span data-ttu-id="2901c-105">社外ではこの情報を共有しないでください。</span><span class="sxs-lookup"><span data-stu-id="2901c-105">Do not share this information outside of your company.</span></span> <span data-ttu-id="2901c-106">ここに挙げられている機能は、発売日に間に合わない可能性があり、その場合は将来のリリースを待たなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2901c-106">Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release.</span></span> <span data-ttu-id="2901c-107">正式なリリースに向けてパイロット (フライト) テスト中の機能もあります。</span><span class="sxs-lookup"><span data-stu-id="2901c-107">Other features are being tested in a pilot (flighting) to ensure they're customer-ready.</span></span> <span data-ttu-id="2901c-108">ご不明な点や懸念される事項がある場合は、Microsoft 製品グループにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="2901c-108">Reach out to your Microsoft product group contact if you have any questions or concerns.</span></span>

<span data-ttu-id="2901c-109">このページは定期的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-109">This page is updated periodically.</span></span> <span data-ttu-id="2901c-110">適宜確認してください。</span><span class="sxs-lookup"><span data-stu-id="2901c-110">Check back for additional updates.</span></span>

> [!Note]
><span data-ttu-id="2901c-111">Intune に関して以下の機能が現在開発されています。</span><span class="sxs-lookup"><span data-stu-id="2901c-111">The following changes are under development for Intune.</span></span> <span data-ttu-id="2901c-112">最新のハイブリッド機能の詳細については、[ハイブリッド環境の新機能に関するページ](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2901c-112">For more information about new hybrid features, check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).</span></span>

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices 
-->


## <a name="intune-in-the-azure-portal"></a><span data-ttu-id="2901c-113">Azure Portal での Intune</span><span class="sxs-lookup"><span data-stu-id="2901c-113">Intune in the Azure portal</span></span>

### <a name="app-protection-policies-----679615---"></a><span data-ttu-id="2901c-114">アプリ保護ポリシー  <!-- 679615 --></span><span class="sxs-lookup"><span data-stu-id="2901c-114">App Protection Policies  <!-- 679615 --></span></span>
<span data-ttu-id="2901c-115">Intune App Protection ポリシーは、既定のグローバル ポリシーを作成し、テナント全体のすべてのユーザーに保護をすばやく適用する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="2901c-115">Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.</span></span>

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a><span data-ttu-id="2901c-116">iOS Volume-Purchase Program アプリの取り消し  <!-- 820863 --></span><span class="sxs-lookup"><span data-stu-id="2901c-116">Revoking iOS Volume-Purchase Program apps  <!-- 820863 --></span></span>
<span data-ttu-id="2901c-117">1 つ以上の iOS Volume-Purchase Program (VPP) アプリがインストールされた特定のデバイスでは、そのデバイスで関連付けられているデバイス ベース アプリのライセンスを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="2901c-117">For a given device that has one or more iOS Volume-Purchase Program (VPP) apps, you will be able to revoke the associated device based app license for the device.</span></span> <span data-ttu-id="2901c-118">アプリのライセンスを取り消しても、関連する VPP アプリがデバイスからアンインストールされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2901c-118">Revoking an app license will not uninstall the related VPP app from the device.</span></span> <span data-ttu-id="2901c-119">VPP アプリをアンインストールするには、割り当てアクションを **[アンインストール]** に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2901c-119">To uninstall a VPP app, you must change the assignment action to **Uninstall**.</span></span> <span data-ttu-id="2901c-120">詳細については、「[Volume Purchase Program で購入した iOS アプリを Microsoft Intune で管理する方法](vpp-apps-ios.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2901c-120">For more information, see [How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune](vpp-apps-ios.md).</span></span>

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a><span data-ttu-id="2901c-121">iOS Volume Purchasing Program トークンのライセンスの取り消し <!-- 820870 --></span><span class="sxs-lookup"><span data-stu-id="2901c-121">Revoke licenses for an iOS Volume Purchasing Program token <!-- 820870 --></span></span>
<span data-ttu-id="2901c-122">特定の VPP トークンのすべての iOS Volume Purchasing Program (VPP) アプリのライセンスを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="2901c-122">You will be able to revoke the license of all iOS Volume Purchasing Program (VPP) apps for a given VPP Token.</span></span>

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a><span data-ttu-id="2901c-123">ネットワーク アクセス制御 (NAC) デバイス チェックイン レポート <!-- 1232250 --></span><span class="sxs-lookup"><span data-stu-id="2901c-123">Network Access Control (NAC) device check-in reporting  <!-- 1232250 --></span></span>
<span data-ttu-id="2901c-124">この変更の前には、IT 管理者は NAC で管理されているデバイスが NAC ソリューションと通信しているかどうかを Intune 側から判断することができませんでした。</span><span class="sxs-lookup"><span data-stu-id="2901c-124">Before this change, IT admins couldn't determine from the Intune side whether a NAC-managed device was communicating with their NAC solution or not.</span></span> <span data-ttu-id="2901c-125">NAC で管理されているデバイスが NAC ソリューションと通信していない場合、そのデバイスは NAC ソリューションに非準拠のデバイスとみなされます。そのため、NAC で管理されているデバイスは NAC ソリューション自体にブロックされ、その後デバイスの準拠状態に依存する条件付きアクセス ポリシーによってブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2901c-125">When a NAC-managed device isn't communicating with their NAC solution, the device is considered non-compliant by the NAC solution, and therefore blocked by the NAC solution itself and subsequently blocked by conditional access policies that rely on the device compliance state.</span></span>

<span data-ttu-id="2901c-126">今回の変更により、IT 管理者はどの NAC で管理されているデバイスが NAC ソリューションと正常に通信したかを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2901c-126">With this change, IT admins can see which NAC-managed devices have successfully communicated with their NAC solution or not.</span></span> <span data-ttu-id="2901c-127">この新機能は、Intune 内のデバイス準拠ワークロードに配置された 2 つの新しい監視機能で構成され、次のように統計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-127">This new capability consists of two new monitoring functions located in the Device compliance workload within Intune, the statistics are shown as below:</span></span>
- <span data-ttu-id="2901c-128">**過去 1 時間の NAC 呼び出しの平均**</span><span class="sxs-lookup"><span data-stu-id="2901c-128">**Average NAC calls in the last hour**</span></span>
- <span data-ttu-id="2901c-129">**最後の NAC 受信要求 (日付/時刻)**</span><span class="sxs-lookup"><span data-stu-id="2901c-129">**Last NAC incoming request (date/time)**</span></span>

### <a name="new-ios-device-action------1244701---"></a><span data-ttu-id="2901c-130">新しい iOS デバイス アクション <!-- 1244701 --></span><span class="sxs-lookup"><span data-stu-id="2901c-130">New iOS device action   <!-- 1244701 --></span></span>
<span data-ttu-id="2901c-131">iOS 10.3 監視下のデバイスをシャット ダウンできます。</span><span class="sxs-lookup"><span data-stu-id="2901c-131">You can shut down iOS 10.3 supervised devices.</span></span> <span data-ttu-id="2901c-132">このアクションでは、エンド ユーザーへの警告なしにデバイスが即時シャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="2901c-132">This action shuts down the device immediately without warning to the end user.</span></span> <span data-ttu-id="2901c-133">**シャット ダウン (監視モードのみ)** アクションは、**デバイス** ワークロードでデバイスを選択した場合に、デバイス プロパティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-133">The **Shut down (supervised only)** action can be found at the device properties when you select a device in the **Device** workload.</span></span>


### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a><span data-ttu-id="2901c-134">Intune で、アカウントの移動操作が使用できるようになりました。<!-- 1573558, 1579830 --></span><span class="sxs-lookup"><span data-stu-id="2901c-134">Intune now provides the Account Move operation  <!-- 1573558, 1579830 --></span></span>
<span data-ttu-id="2901c-135">**アカウントの移動**を行うと、Azure スケール ユニット (ASU) 間でテナントが移動します。</span><span class="sxs-lookup"><span data-stu-id="2901c-135">The **Account Move** migrates a tenant from one Azure Scale Unit (ASU) to another.</span></span> <span data-ttu-id="2901c-136">お客様が Intune サポート チームに連絡してアカウントの移動をリクエストする、お客様が開始するシナリオと、Microsoft でバックエンドでのサービスの調整が必要な、Microsoft 主導のシナリオの両方で**アカウントの移動**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2901c-136">The **Account Move** can be used for both customer-initiated scenarios, when you call the Intune support team requesting it, and it can also be a Microsoft-driven scenario where Microsoft needs to make adjustments to the service in the back-end.</span></span> <span data-ttu-id="2901c-137">**アカウントの移動**中は、テナントは読み取り専用モード (ROM) になります。</span><span class="sxs-lookup"><span data-stu-id="2901c-137">During the **Account Move**, the tenant enters in read-only mode (ROM).</span></span> <span data-ttu-id="2901c-138">ROM 期間中は、デバイスの登録や名前変更、コンプライアンス状態の更新などのサービス操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="2901c-138">Service operations like enrolling, renaming devices, updating compliance status will fail during the ROM period.</span></span>




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a><span data-ttu-id="2901c-139">組み込み型のアプリを利用し、iOS デバイスまたは Android デバイスに Office 365 モバイル アプリを割り当てる <!-- 1332318 --></span><span class="sxs-lookup"><span data-stu-id="2901c-139">Assign Office 365 mobile apps to iOS and Android devices using built-in app type <!-- 1332318 --></span></span>
<span data-ttu-id="2901c-140">**組み込み**型のアプリであれば、Office 365 アプリを作成し、管理している iOS または Android デバイスに割り当てることが簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="2901c-140">The **Built-in** app type will make it easier for you to create and assign Office 365 apps to the iOS and Android devices that you manage.</span></span> <span data-ttu-id="2901c-141">これらのアプリには、Word、Excel、PowerPoint、OneDrive などの 0365 アプリがあります。</span><span class="sxs-lookup"><span data-stu-id="2901c-141">These apps include 0365 apps such as Word, Excel, PowerPoint, and OneDrive.</span></span> <span data-ttu-id="2901c-142">アプリの種類に特定のアプリを割り当て、アプリ情報構成を編集できます。</span><span class="sxs-lookup"><span data-stu-id="2901c-142">You can assign specific apps to the app type and edit the app information configuration.</span></span>


### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a><span data-ttu-id="2901c-143">iOS ストア アプリに関して、割り当て競合の解決が変更されました <!-- 1480316 --></span><span class="sxs-lookup"><span data-stu-id="2901c-143">Assignment conflict resolution has changed for iOS store apps <!-- 1480316 --></span></span>
<span data-ttu-id="2901c-144">iOS ストア アプリの入手可能性に関して、変更の影響をエンド ユーザーが受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2901c-144">End users might experience a change in the availability of iOS store apps.</span></span> <span data-ttu-id="2901c-145">現在のところ、**[Required and Available]\(必須で利用可能\)** と **[適用できません]** で競合する 2 つのグループに割り当てられているアプリは **[Required and Available]\(必須で利用可能\)** に解決されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-145">Currently, an app that has been assigned to two groups with a conflict between **Required and Available** and **Not Applicable**, resolves to **Required and Available**.</span></span> <span data-ttu-id="2901c-146">今回の変更で、このような競合が発生していたアプリが **[適用できません]** に解決されるようになります。</span><span class="sxs-lookup"><span data-stu-id="2901c-146">With the change, an app experiencing this conflict resolves to **Not Applicable**.</span></span>

<span data-ttu-id="2901c-147">この変更は、アプリの意図が異なる複数のグループに 1 つのアプリが割り当てられるときの混乱に対処するものです。</span><span class="sxs-lookup"><span data-stu-id="2901c-147">The change addresses the confusion when one app is assigned to multiple groups with different app intents.</span></span>

<span data-ttu-id="2901c-148">11 月のサービス リリースの前に Information Worker Portal とポータル サイトでアプリを利用できるようにする場合、2 つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="2901c-148">If you would like to have your app available in the Information Worker Portal and the Company Portal before the November service release, you have two options:</span></span>

1. <span data-ttu-id="2901c-149">グループの **[適用できません]** 割り当てを削除します。</span><span class="sxs-lookup"><span data-stu-id="2901c-149">Remove the **Not Applicable** assignment for your group.</span></span>
2. <span data-ttu-id="2901c-150">**[Required and Available]\(必須で利用可能\)** が割り当てられているメンバーが含まれない新しいグループを作成し、そのグループに **[適用できません]** を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2901c-150">Create a new group that does not include members with **Required and Available** intent assigned and assign that group as **Not Applicable**.</span></span>

<span data-ttu-id="2901c-151">詳細については、「[How to assign apps to groups with Microsoft Intune](apps-deploy.md)」 (Microsoft Intune を使ってアプリをグループに割り当てる方法) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2901c-151">For more information, see, [How to assign apps to groups with Microsoft Intune](apps-deploy.md).</span></span>

> [!Note]
> <span data-ttu-id="2901c-152">リリース後、Intune クラシック コンソールでは、Mobile Device Management (MDM) アプリ割り当てを表示したり、変更したりできなくなります。</span><span class="sxs-lookup"><span data-stu-id="2901c-152">After the release you will no longer be able to view or modify Mobile Device Management (MDM) app assignments in the Intune classic console.</span></span> <span data-ttu-id="2901c-153">ただし、Azure コンソールまたは Intune Graph API を利用してアプリを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2901c-153">However, you can use Azure console or the Intune Graph API to make your app assignments.</span></span>

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a><span data-ttu-id="2901c-154">Android デバイスとは別に Android for Work デバイスを管理する <!-- 1490731 --></span><span class="sxs-lookup"><span data-stu-id="2901c-154">Manage Android for Work devices independently from Android devices <!-- 1490731 --></span></span>
<span data-ttu-id="2901c-155">Intune は、Android プラットフォームに依存することなく、Android for Work デバイスの登録を管理できます。</span><span class="sxs-lookup"><span data-stu-id="2901c-155">Intune will support managing enrollment of Android for Work devices independently from the Android platform.</span></span> <span data-ttu-id="2901c-156">この設定は、**[デバイスの登録]**、**[登録制限]**、**[デバイスの種類の制限]** で管理されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-156">These settings are managed under **Device Enrollment** > **Enrollment restrictions** > **Device Type Restrictions**.</span></span> <span data-ttu-id="2901c-157">(以前の場所は **[デバイス登録]**、**[Android for Work への登録]**、**[Android for Work の登録設定]** でした。)</span><span class="sxs-lookup"><span data-stu-id="2901c-157">(They were previously located under **Device Enrollment** > **Android for Work Enrollment** > **Android for Work Enrollment Settings**.)</span></span>

<span data-ttu-id="2901c-158">既定では、Android for Work デバイス設定は Android デバイスの設定と同じになります。</span><span class="sxs-lookup"><span data-stu-id="2901c-158">By default, your Android for Work devices settings will be the same as your settings for your Android devices.</span></span> <span data-ttu-id="2901c-159">ただし、Android for Work 設定を変更した後は、同じではなくなります。</span><span class="sxs-lookup"><span data-stu-id="2901c-159">However, after you change your Android for Work settings that will no longer be the case.</span></span>
 
<span data-ttu-id="2901c-160">個人の Android for Work 登録をブロックした場合、会社の Android デバイスのみを Android for Work として登録できます。</span><span class="sxs-lookup"><span data-stu-id="2901c-160">If you block personal Android for Work enrollment, only corporate Android devices can enroll as Android for Work.</span></span>

<span data-ttu-id="2901c-161">新しい設定を使用する場合、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="2901c-161">When working with the new settings, consider the following:</span></span>

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a><span data-ttu-id="2901c-162">以前に Android for Work 登録をオンボードしたことがない</span><span class="sxs-lookup"><span data-stu-id="2901c-162">If you have never previously onboarded Android for Work enrollment</span></span>
<span data-ttu-id="2901c-163">新しい Android for Work プラットフォームは、既定の [デバイスの種類の制限] でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2901c-163">The new Android for Work platform is blocked in the default Device Type Restrictions.</span></span> <span data-ttu-id="2901c-164">この機能をオンボードした後は、デバイスを Android for Work に登録できます。</span><span class="sxs-lookup"><span data-stu-id="2901c-164">After you onboard the feature, you can allow devices to enroll with Android for Work.</span></span> <span data-ttu-id="2901c-165">そのためには、既定値を変更するか、新しい [デバイスの種類の制限] を作成して既定の [デバイスの種類の制限] に代えます。</span><span class="sxs-lookup"><span data-stu-id="2901c-165">To do so, change the default or create a new Device Type Restriction to supersede the default Device Type Restriction.</span></span>

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a><span data-ttu-id="2901c-166">Android for Work 登録をオンボードした</span><span class="sxs-lookup"><span data-stu-id="2901c-166">If you have onboarded Android for Work enrollment</span></span>
<span data-ttu-id="2901c-167">以前にオンボードしている場合、状況は選んだ設定によって変わります。</span><span class="sxs-lookup"><span data-stu-id="2901c-167">If you’ve previously onboarded, your situation depends on the setting you chose:</span></span>

| <span data-ttu-id="2901c-168">Setting</span><span class="sxs-lookup"><span data-stu-id="2901c-168">Setting</span></span> | <span data-ttu-id="2901c-169">既定の [デバイスの種類の制限] の Android for Work の状態</span><span class="sxs-lookup"><span data-stu-id="2901c-169">Android for Work status in default Device Type Restriction</span></span> | <span data-ttu-id="2901c-170">注</span><span class="sxs-lookup"><span data-stu-id="2901c-170">Notes</span></span> |
| --- | --- | --- |
| <span data-ttu-id="2901c-171">**すべてのデバイスを Android として管理する**</span><span class="sxs-lookup"><span data-stu-id="2901c-171">**Manage all devices as Android**</span></span> | <span data-ttu-id="2901c-172">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="2901c-172">Blocked</span></span> | <span data-ttu-id="2901c-173">すべての Android デバイスを Android for Work なしで登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2901c-173">All Android devices must enroll without Android for Work.</span></span> |
| <span data-ttu-id="2901c-174">**サポートされているデバイスを Android for Work として管理する**</span><span class="sxs-lookup"><span data-stu-id="2901c-174">**Manage supported devices as Android for Work**</span></span> | <span data-ttu-id="2901c-175">許可済み</span><span class="sxs-lookup"><span data-stu-id="2901c-175">Allowed</span></span> | <span data-ttu-id="2901c-176">Android for Work 対応のすべての Android デバイスを Android for Work に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2901c-176">All Android devices that support Android for Work must enroll with Android for Work.</span></span> |
| <span data-ttu-id="2901c-177">**これらのグループに所属するユーザーのサポートされているデバイスのみを Android for Work として管理する**</span><span class="sxs-lookup"><span data-stu-id="2901c-177">**Manage supported devices for users only in these groups as Android for Work**</span></span> | <span data-ttu-id="2901c-178">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="2901c-178">Blocked</span></span> | <span data-ttu-id="2901c-179">既定値をオーバーライドする別個の [デバイスの種類の制限] ポリシーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="2901c-179">A separate Device Type Restriction policy was created to override the default.</span></span> <span data-ttu-id="2901c-180">このポリシーによって、以前に選択したグループで Android for Work 登録が許可されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-180">This policy defines the groups you previously selected to allow Android for Work enrollment.</span></span> <span data-ttu-id="2901c-181">選択されたグループ内のユーザーには、Android for Work デバイスの登録が引き続き許可されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-181">Users within the selected groups will continue to be allowed to enroll their Android for Work devices.</span></span> <span data-ttu-id="2901c-182">その他すべてのユーザーには、Android for Work の登録が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-182">All other users are restricted from enrolling with Android for Work.</span></span> |

<span data-ttu-id="2901c-183">いずれの場合でも、意図した規制が維持されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-183">In all cases, your intended regulation is preserved.</span></span> <span data-ttu-id="2901c-184">自分の環境で Android for Work のグローバル許可またはグループ別許可を維持するための操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2901c-184">No action is required on your part to maintain the global or per-group allowance of Android for Work in your environment.</span></span>

<span data-ttu-id="2901c-185">以上の変更は 11 月の更新をもってロールアウトが開始されます。ただし、自分のアカウントでは実行に時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="2901c-185">These changes will begin rollout with the November update, but may take time to execute on your account.</span></span> <span data-ttu-id="2901c-186">変更が自分のアカウントに適用されると、Office 365 ポータルで確認通知が届きます。</span><span class="sxs-lookup"><span data-stu-id="2901c-186">You will receive a confirmation notification in the Office 365 portal when these changes are effective for your account.</span></span>


### <a name="configure-an-ios-app-pin----1586774---"></a><span data-ttu-id="2901c-187">iOS アプリ PIN を構成する <!-- 1586774 --></span><span class="sxs-lookup"><span data-stu-id="2901c-187">Configure an iOS app PIN <!-- 1586774 --></span></span>
<span data-ttu-id="2901c-188">間もなく、対象の iOS アプリで PIN を要求できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2901c-188">Soon you will be able to require a PIN for targeted iOS apps.</span></span> <span data-ttu-id="2901c-189">Azure Portal で PIN 要件と有効期限 (日数) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="2901c-189">You can configure the PIN requirement and expiration date in days through the Azure portal.</span></span> <span data-ttu-id="2901c-190">必須にすると、iOS アプリにアクセスする前に、新しい PIN を設定して使用するようにユーザーが要求されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-190">When required, a user will be required to set and use a new PIN before getting access to an iOS app.</span></span> <span data-ttu-id="2901c-191">Intune App SDK によるアプリ保護を有効にしている iOS アプリでのみこの機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2901c-191">Only iOS apps that have app protection enabled with the Intune App SDK will support this feature.</span></span>


<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a><span data-ttu-id="2901c-192">Azure Active Directory の Web サイトでは、Intune Managed Browser アプリを要求し、Managed Browser (パブリック プレビュー) に対するシングル サインオンをサポートすることができる <!-- 710595 --></span><span class="sxs-lookup"><span data-stu-id="2901c-192">Azure Active Directory web sites can require the Intune Managed Browser App and support Single Sign-On for the Managed Browser (Public Preview) <!-- 710595 --></span></span>   
<span data-ttu-id="2901c-193">Azure Active Directory (Azure AD) を使っている場合、モバイル デバイスでの Web サイトへのアクセスを、Intune Managed Browser アプリに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="2901c-193">Using Azure Active Directory (Azure AD), you will be able to restrict access to web sites on mobile devices to the Intune Managed Browser app.</span></span> <span data-ttu-id="2901c-194">Managed Browser では、Web サイトのデータは安全性を維持され、エンド ユーザーの個人データと分離されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-194">In the managed browser, web site data will remain secure and separate from end-user personal data.</span></span> <span data-ttu-id="2901c-195">さらに、Managed Browser は、Azure AD によって保護されているサイトに対するシングル サインオン機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2901c-195">In addition, the Managed Browser will support Single Sign-On capabilities for sites protected by Azure AD.</span></span> <span data-ttu-id="2901c-196">Managed Browser にサインインすると、または Intune によって管理されている別のアプリでデバイスの Managed Browser を使うと、ユーザーが資格情報を入力しなくても、Managed Browser は Azure AD によって保護されている会社サイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2901c-196">Signing in to the Managed Browser, or using the Managed Browser on a device with another app managed by Intune, allows the Managed Browser to access corporate sites protected by Azure AD without the user having to enter their credentials.</span></span> <span data-ttu-id="2901c-197">この機能は、Outlook Web Access (OWA) や SharePoint Online などのサイトだけでなく、Azure App プロキシ経由でアクセスされるイントラネット リソースのような他の企業サイトにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-197">This functionality applies to sites like Outlook Web Access (OWA) and SharePoint Online, as well as other corporate sites like intranet resources accessed through the Azure App Proxy.</span></span>


<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a><span data-ttu-id="2901c-198">Windows 10 エディション アップグレード ポリシーのサポート <!-- 903672(archived), 1119689 --></span><span class="sxs-lookup"><span data-stu-id="2901c-198">Support for Windows 10 edition upgrade policy   <!-- 903672(archived), 1119689 --></span></span>  
<span data-ttu-id="2901c-199">Windows 10 デバイスを Windows 10 Education、Windows 10 Education N、Windows 10 Professional、Windows 10 Professional N、Windows 10 Professional Education、Windows 10 Professional Education N にアップグレードする Windows 10 エディション アップグレード ポリシーを作成できます。Windows 10 エディション アップグレードの詳細については、[Windows 10 エディションのアップグレードを構成する方法](edition-upgrade-configure-windows-10.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2901c-199">You will be able to create a Windows 10 edition upgrade policy that upgrades Windows 10 devices to Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education, and Windows 10 Professional Education N. For details about Windows 10 edition upgrades, see [How to configure Windows 10 edition upgrades](edition-upgrade-configure-windows-10.md).</span></span>




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a><span data-ttu-id="2901c-200">Lookout の Android for Work サポート <!-- 1087312 --></span><span class="sxs-lookup"><span data-stu-id="2901c-200">Android for Work support for Lookout <!-- 1087312 --></span></span>   
<span data-ttu-id="2901c-201">Lookout を備えた Intune コネクタでは、Lookout for Work アプリの使用時、Android for Work デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2901c-201">Intune connector with Lookout will support Android for Work devices when using the Lookout for Work app.</span></span> <span data-ttu-id="2901c-202">コンテナーの内外に Lookout アプリを展開できるようになる予定です。</span><span class="sxs-lookup"><span data-stu-id="2901c-202">You are able to deploy the Lookout app inside or outside the container.</span></span>

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a><span data-ttu-id="2901c-203">Intune App Protection と Citrix MDX 開発ツール<!-- 709185 --></span><span class="sxs-lookup"><span data-stu-id="2901c-203">Intune App Protection and Citrix MDX Development Tools <!-- 709185 --></span></span>
<span data-ttu-id="2901c-204">Citrix XenMobile MDX と Microsoft Intune を組み合わせ、デバイスとアプリを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2901c-204">You can manage devices and apps with a combination of Citrix XenMobile MDX and Microsoft Intune.</span></span> <span data-ttu-id="2901c-205">これにより、Citrix の mVPN テクノロジを使用し、Intune アプリの保護ポリシーでアプリを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2901c-205">This allows you to manage apps with Intune app protection policy while using Citrix’s mVPN technology.</span></span>

<span data-ttu-id="2901c-206">Citrix の MDX mVPN テクノロジとの統合を可能にする iOS および Android 用の Intune アプリ ラッピング ツールと Intune アプリ SDK を含むコード リポジトリを見つけることができるはずです。</span><span class="sxs-lookup"><span data-stu-id="2901c-206">You are able to find a code repository that contains the Intune App Wrapping Tool and Intune App SDK for iOS and Android, integrating with Citrix MDX mVPN technology.</span></span>




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a><span data-ttu-id="2901c-207">新しいポータル サイト アプリへの macOS ユーザーのリダイレクト<!--1380728--></span><span class="sxs-lookup"><span data-stu-id="2901c-207">Redirecting macOS users to our new Company Portal app <!--1380728--></span></span>   
<span data-ttu-id="2901c-208">エンド ユーザーは、ポータル サイトの Web サイトにログインして macOS デバイスを登録するとき、プロセスを完了するために macOS 用の新しいポータル サイト アプリをダウンロードするように指示されます。</span><span class="sxs-lookup"><span data-stu-id="2901c-208">When an end user logs into the Company Portal website to enroll their macOS device, they will be directed to download the new Company Portal app for macOS to complete the process.</span></span> <span data-ttu-id="2901c-209">これは、OS X El Capitan 10.11 以降を使っている macOS デバイスの場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="2901c-209">This occurs for macOS devices using OS X El Capitan 10.11 or above.</span></span> 



<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a><span data-ttu-id="2901c-210">iOS および Android <!-- 1374196 --> 用の Intune Managed Browser のサポート</span><span class="sxs-lookup"><span data-stu-id="2901c-210">Intune Managed Browser support for iOS and Android <!-- 1374196 --></span></span>
<span data-ttu-id="2901c-211">2017 年 10 月の時点で、Android アプリで使用する Intune Managed Browser アプリは、Android 4.4 以降を実行しているデバイスのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2901c-211">As of October 2017, the Intune Managed Browser app on Android app will support only devices running Android 4.4 and later.</span></span> <span data-ttu-id="2901c-212">iOS の Intune Managed Browser アプリは、iOS 9.0 以降を実行しているデバイスのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2901c-212">The Intune Managed Browser app on iOS will support only devices running iOS 9.0 and later.</span></span> <span data-ttu-id="2901c-213">以前のバージョンの Android および iOS は、Managed Browser の使用を続けることができますが、新しいバージョンのアプリをインストールすることはできません。また、アプリのすべての機能にアクセスできるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="2901c-213">Earlier versions of Android and iOS will be able to continue using the Managed Browser, but will be unable to install new versions of the app and might not be able to access all of the app capabilities.</span></span> <span data-ttu-id="2901c-214">サポートされるオペレーティング システム バージョンにこれらのデバイスを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2901c-214">We encourage you to update these devices to a supported operating system version.</span></span>


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a><span data-ttu-id="2901c-215">ユーザーが登録できるデバイスの最大数に達したときのエラー メッセージの向上<!-- 1270370 --></span><span class="sxs-lookup"><span data-stu-id="2901c-215">Improved error message for when a user reaches the maximum number of devices allowed to enroll <!-- 1270370 --></span></span>
<span data-ttu-id="2901c-216">エンドユーザーに一般的なエラー メッセージでなく、「IT 管理者が許可している数よりも多くのデバイスが登録されています。登録したデバイスを削除するか、IT 管理者に支援を求めてください。」という分かりやすい、実践的なエラー メッセージが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2901c-216">Instead of a generic error message, end users see a friendly, actionable error message: "You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin."</span></span>




## <a name="notices"></a><span data-ttu-id="2901c-217">通知</span><span class="sxs-lookup"><span data-stu-id="2901c-217">Notices</span></span>

<span data-ttu-id="2901c-218">現在のところ、アクティブな通知はありません。</span><span class="sxs-lookup"><span data-stu-id="2901c-218">There are no active notices at this time.</span></span>




### <a name="see-also"></a><span data-ttu-id="2901c-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="2901c-219">See also</span></span>
<span data-ttu-id="2901c-220">最近の開発状況について詳しくは、「[Microsoft Intune の新機能](whats-new.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2901c-220">See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.</span></span>
