---
title: "アラートによる通知 | Microsoft Docs"
description: "アラートを使用し、Microsoft Intune で何が起こっているかを常に把握する方法の詳細。"
keywords: 
author: nathbarn
ms.author: angrobe
manager: angrobe
ms.date: 8/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft intune
ms.technology: 
ms.assetid: 396ea714 0433 4bd5 a934 8d0b477f28e4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune classic
ms.openlocfilehash: b704cb944340f7d53baf26ceec34d9d53d06f77f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
#  <a name="use-alerts-to-get-notified-by-microsoft-intune"></a><span data-ttu-id="f922c-103">アラートを使用して Microsoft Intune から通知を受ける</span><span class="sxs-lookup"><span data-stu-id="f922c-103">Use alerts to get notified by Microsoft Intune</span></span>

[!INCLUDE [classic portal](../includes/classic-portal.md)]

<span data-ttu-id="f922c-104">アラートを使用すると、Microsoft Intune で何が起こっているかを常に把握しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="f922c-104">Alerts keep you in touch with what's happening in Microsoft Intune.</span></span> <span data-ttu-id="f922c-105">たとえば、アラートによって次のようなイベントを通知できます。</span><span class="sxs-lookup"><span data-stu-id="f922c-105">For example, alerts can notify you about the following events:</span></span>
- <span data-ttu-id="f922c-106">モバイル デバイスの管理に影響を与える Exchange Connector の問題</span><span class="sxs-lookup"><span data-stu-id="f922c-106">A problem with the Exchange Connector which affects mobile device management</span></span>
- <span data-ttu-id="f922c-107">コンピューターでのマルウェアの検出</span><span class="sxs-lookup"><span data-stu-id="f922c-107">Malware was found on a computer</span></span>
- <span data-ttu-id="f922c-108">2 つの Intune ポリシー間の競合の検出</span><span class="sxs-lookup"><span data-stu-id="f922c-108">A conflict between two Intune policies was detected</span></span>
- <span data-ttu-id="f922c-109">Intune ソフトウェア クライアントの展開の失敗</span><span class="sxs-lookup"><span data-stu-id="f922c-109">An Intune software client deployment fails</span></span>

## <a name="how-alerts-work"></a><span data-ttu-id="f922c-110">アラートの動作</span><span class="sxs-lookup"><span data-stu-id="f922c-110">How alerts work</span></span>

<span data-ttu-id="f922c-111">アラートは、**アラートの種類**に基づいて生成されます。これは、Intune に組み込まれた構成済みの規則のセットです。</span><span class="sxs-lookup"><span data-stu-id="f922c-111">Alerts are generated based on **alert types**, a set of preconfigured rules built into Intune.</span></span> <span data-ttu-id="f922c-112">たとえば、**"クラウドの記憶域の空き領域が 10% 以下です"** という種類のアラートは、クラウドにアプリを格納する領域が不足している場合に生成されます。</span><span class="sxs-lookup"><span data-stu-id="f922c-112">For example, the alert type, **Cloud storage has 10% or less free space**, alerts you when you are running out of space to store your apps in the cloud.</span></span> <span data-ttu-id="f922c-113">アラートの種類ごとに、アラートの種類を有効または無効にしたり、プロパティを構成したりできます。</span><span class="sxs-lookup"><span data-stu-id="f922c-113">You can enable or disable alert types and configure properties for each alert type.</span></span> <span data-ttu-id="f922c-114">たとえば、このアラートの種類では、次の項目を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f922c-114">For example, using the above alert type, you can configure:</span></span>

- <span data-ttu-id="f922c-115">**状態:** アラートの種類が有効か無効か</span><span class="sxs-lookup"><span data-stu-id="f922c-115">**State:** Whether this alert type is enabled or disabled</span></span>
- <span data-ttu-id="f922c-116">**重要度:** アラートがどの程度深刻であるか</span><span class="sxs-lookup"><span data-stu-id="f922c-116">**Severity:** How serious is this alert?</span></span>

|<span data-ttu-id="f922c-117">重大度</span><span class="sxs-lookup"><span data-stu-id="f922c-117">Severity</span></span>|<span data-ttu-id="f922c-118">説明</span><span class="sxs-lookup"><span data-stu-id="f922c-118">Details</span></span>|
|--|---|
|<span data-ttu-id="f922c-119">**重大なアラート**</span><span class="sxs-lookup"><span data-stu-id="f922c-119">**Critical alert**</span></span>|<span data-ttu-id="f922c-120">コンピューターでマルウェアが検出された場合など、できるだけ早く調査する必要がある重大な問題であることを示します。</span><span class="sxs-lookup"><span data-stu-id="f922c-120">Indicates a serious issue that you should investigate as soon as possible, for example, if malware was detected on a computer.</span></span>|
|<span data-ttu-id="f922c-121">**警告アラート**</span><span class="sxs-lookup"><span data-stu-id="f922c-121">**Warning alert**</span></span>|<span data-ttu-id="f922c-122">セキュリティ更新プログラムのインストールを待機している場合など、現在のところ深刻な問題ではないものの、注意を怠ると重大な問題につながる可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f922c-122">Indicates an issue that isn't currently serious but might become serious if you don't attend to it, for example, security updates are waiting to be installed.</span></span>|
|<span data-ttu-id="f922c-123">**情報案内アラート**</span><span class="sxs-lookup"><span data-stu-id="f922c-123">**Informational alert**</span></span>|<span data-ttu-id="f922c-124">Exchange Connector の新しいバージョンが利用可能になった場合など、作業に対する重要度が比較的低い情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f922c-124">Indicates information that isn't critical to your operations, for example, a new version of the Exchange Connector is available.</span></span>|

<span data-ttu-id="f922c-125">他のアラートの種類では、アラートを生成する前に問題の影響を受けるデバイス数の割合など、異なる項目を構成できる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f922c-125">Other alert types might have different items that you can configure, like the percentage of devices that must be affected by an issue before an alert is generated.</span></span>

<span data-ttu-id="f922c-126">**アラートの種類の条件が満たされると、アラートが生成され、Intune 管理コンソールに表示されます。**</span><span class="sxs-lookup"><span data-stu-id="f922c-126">**When the criteria in an alert type is met, an alert is generated and shown in the Intune admin console.**</span></span>

<span data-ttu-id="f922c-127">また、アラートが生成されたときに電子メールで通知するよう Intune を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f922c-127">Additionally, you can configure Intune to notify you by email when an alert is generated.</span></span>

## <a name="set-up-alerts"></a><span data-ttu-id="f922c-128">アラートを設定する</span><span class="sxs-lookup"><span data-stu-id="f922c-128">Set up alerts</span></span>

<span data-ttu-id="f922c-129">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理]** &gt; **[アラートと通知]** の順に選択し、次のいずれかのタスクを選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-129">In the [Microsoft Intune admin console](https://manage.microsoft.com), choose **Admin** &gt; **Alerts and Notifications**, and then choose one of the following tasks:</span></span>

|<span data-ttu-id="f922c-130">作業</span><span class="sxs-lookup"><span data-stu-id="f922c-130">Task</span></span>|<span data-ttu-id="f922c-131">説明</span><span class="sxs-lookup"><span data-stu-id="f922c-131">Description</span></span>|
|---|------|
|<span data-ttu-id="f922c-132">**アラートの種類**</span><span class="sxs-lookup"><span data-stu-id="f922c-132">**Alert Types**</span></span>|<span data-ttu-id="f922c-133">構成するアラートの種類を選択し、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="f922c-133">Choose the alert type that you want to configure, and then do one of the following:</span></span><br /><br /><span data-ttu-id="f922c-134">**[構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-134">Choose **Configure**.</span></span> <span data-ttu-id="f922c-135">**[アラートの種類の構成]** ダイアログ ボックスで目的の設定を構成し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-135">In the **Configure Alert Type** dialog box, configure the settings that you want, and then choose **OK**.</span></span><br /><br /><span data-ttu-id="f922c-136">アラートを **[有効]** または **[無効]** にします。</span><span class="sxs-lookup"><span data-stu-id="f922c-136">**Enable** or **Disable** the alert.</span></span><br /><br /><span data-ttu-id="f922c-137">**[アラートの種類]** ノードを展開し、カテゴリを選択して、そのカテゴリに含まれるアラートの種類のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="f922c-137">Expand the **Alert Types** node, and choose a category to view only the alert types in that category.</span></span>|
|<span data-ttu-id="f922c-138">**受信者**</span><span class="sxs-lookup"><span data-stu-id="f922c-138">**Recipients**</span></span>|<span data-ttu-id="f922c-139">**[追加]** を選択して、セットアップした電子メール通知を受信する新しい電子メール アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="f922c-139">Choose **Add** to add a new email address that will receive the email notifications that you set up.</span></span><br /><br /><span data-ttu-id="f922c-140">既存の受信者を **編集** または **削除** することもできます。</span><span class="sxs-lookup"><span data-stu-id="f922c-140">You can also **Edit** or **Delete** existing recipients.</span></span><br /><br /><span data-ttu-id="f922c-141">また、通知を受信するには、**[通知規則]** でこの電子メール アドレスを受信者として追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f922c-141">To receive notifications, you must also add this email address as a recipient under **Notification Rules**.</span></span>|
|<span data-ttu-id="f922c-142">**通知規則**</span><span class="sxs-lookup"><span data-stu-id="f922c-142">**Notification Rules**</span></span>|<span data-ttu-id="f922c-143">電子メール アラートの送信先を定義する規則を構成します。</span><span class="sxs-lookup"><span data-stu-id="f922c-143">Configures rules that define who an email alert will be sent to.</span></span> <span data-ttu-id="f922c-144">次のいずれかの方法で行います。</span><span class="sxs-lookup"><span data-stu-id="f922c-144">You can either:</span></span><br /><br /><span data-ttu-id="f922c-145">**既存の規則を選択する**。規則を選択し、**[受信者の選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-145">**Choose an existing rule**   Choose a rule, and then choose **Select Recipients**.</span></span> <span data-ttu-id="f922c-146">この規則を満たすアラートが生成されたときに電子メールを受信するすべての受信者を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f922c-146">You can then select all recipients who will receive an email when an alert that fulfills this rule is generated.</span></span><br /><br /><span data-ttu-id="f922c-147">**新しい規則を作成する**。規則の名前を入力し、規則に適用するアラートのカテゴリとアラートの重要度、規則を適用するデバイス グループ、およびアラートが生成されたときに電子メールを受信するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-147">**Create a new rule**   enter a name for the rule, select the alert categories and alert severity that apply to the rules, select the device groups that the rule applies to, and select the users who will receive an email when an alert is generated.</span></span><br /><br /><span data-ttu-id="f922c-148">既存の規則を **有効**または **無効**にしたり、 **編集**または **削除** したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f922c-148">You can also **Enable**, **Disable**, **Edit**, or **Delete** an existing rule.</span></span>|

## <a name="working-with-alerts"></a><span data-ttu-id="f922c-149">アラートの操作</span><span class="sxs-lookup"><span data-stu-id="f922c-149">Working with alerts</span></span>

<span data-ttu-id="f922c-150">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)でアラートを表示するには、**[アラート]** を選択して、表示するアラートの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-150">To view alerts in the [Microsoft Intune admin console](https://manage.microsoft.com), choose **Alerts**, and then the type of alert to view.</span></span>

<span data-ttu-id="f922c-151">Intune の管理コンソールからアラートを操作するときには、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f922c-151">Use the following options to help you work with alerts from the Intune admin console.</span></span>

|<span data-ttu-id="f922c-152">オプション</span><span class="sxs-lookup"><span data-stu-id="f922c-152">Option</span></span>|<span data-ttu-id="f922c-153">説明</span><span class="sxs-lookup"><span data-stu-id="f922c-153">Description</span></span>|
|-----|----|
|<span data-ttu-id="f922c-154">**アクティブなアラートの表示**</span><span class="sxs-lookup"><span data-stu-id="f922c-154">**View active alerts**</span></span>|<span data-ttu-id="f922c-155">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-155">Choose one of:</span></span><br /><br /><span data-ttu-id="f922c-156">**アラートの概要を表示する**。**[ダッシュボード]** ワークスペースで、上位のエラーが [アラート] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f922c-156">**View an alert summary**   In the **Dashboard** workspace, the top errors are shown in the Alerts pane.</span></span> <span data-ttu-id="f922c-157">ウィンドウを選択すると、さらに詳しい情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f922c-157">Choose the pane to see more detailed information.</span></span><br /><br /><span data-ttu-id="f922c-158">また、 **[アラート]** ワークスペースの **[概要]** ページにもアラートの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f922c-158">Additionally, you can view an alert summary on the **Overview** page of the **Alerts** workspace.</span></span><br /><br /><span data-ttu-id="f922c-159">**アラートをすべて表示する**。**[アラート]** ワークスペースで **[すべてのアラート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-159">**View all alerts**   In the **Alerts** workspace, choose **All Alerts**.</span></span>|
|<span data-ttu-id="f922c-160">**通知の表示**</span><span class="sxs-lookup"><span data-stu-id="f922c-160">**View notices**</span></span>|<span data-ttu-id="f922c-161">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-161">Choose one of:</span></span><br /><br /><span data-ttu-id="f922c-162">**[ダッシュボード]** ワークスペースで、**[通知]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-162">In the **Dashboard** workspace, choose **Notices**.</span></span><br /><br /><span data-ttu-id="f922c-163">**[アラート]** ワークスペースで、**[すべてのアラート]** &gt; **[通知]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-163">In the **Alerts** workspace, choose **All Alerts** &gt; **Notices**.</span></span>|
|<span data-ttu-id="f922c-164">**アラートを閉じる**</span><span class="sxs-lookup"><span data-stu-id="f922c-164">**Close an alert**</span></span>|<span data-ttu-id="f922c-165">アラートの一覧で、閉じるアラートを選択し、**[アラートを閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-165">In the list of alerts, choose the alert to close, and then choose **Close Alert**.</span></span><br /><br /><span data-ttu-id="f922c-166">閉じられたアラートは、90 日後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="f922c-166">Closed alerts are permanently deleted after 90 days.</span></span>|
|<span data-ttu-id="f922c-167">**閉じたアラートの再有効化**</span><span class="sxs-lookup"><span data-stu-id="f922c-167">**Reactivate a closed alert**</span></span>|<span data-ttu-id="f922c-168">アラートの一覧で、**[フィルター]** ドロップダウンを **[終了]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="f922c-168">In the list of alerts, set the **Filters** drop down to **Closed**.</span></span><br /><br /><span data-ttu-id="f922c-169">閉じられたアラートの一覧で、再有効化するアラートを選択し、**[アラートの再有効化]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f922c-169">In the list of closed alerts, select the alert that you want to reactivate, and then choose **Reactivate Alert**.</span></span>|

<span data-ttu-id="f922c-170">Intune のアラートは 30 日間、または次の条件が満たされるまで有効です。</span><span class="sxs-lookup"><span data-stu-id="f922c-170">Intune alerts remain active for 30 days or until:</span></span>

- <span data-ttu-id="f922c-171">アラートの原因となった問題が解決された。</span><span class="sxs-lookup"><span data-stu-id="f922c-171">The issue that caused the alert is fixed.</span></span>
- <span data-ttu-id="f922c-172">手動でアラートが閉じられた。</span><span class="sxs-lookup"><span data-stu-id="f922c-172">The alert is manually closed.</span></span>

<span data-ttu-id="f922c-173">閉じられたアラートは、終了から 30 日間は再有効化できます。</span><span class="sxs-lookup"><span data-stu-id="f922c-173">Closed alerts can be reactivated for 30 days after closing.</span></span> <span data-ttu-id="f922c-174">30 日後、閉じられたアラートと無効なアラートが Intune から削除されます。</span><span class="sxs-lookup"><span data-stu-id="f922c-174">After 30 days, closed and inactive alerts are removed from Intune.</span></span>

> [!TIP]
> <span data-ttu-id="f922c-175">異なるオペレーティング システムを実行しているデバイスで同じアラートが生成された場合、アラートの一覧に同じアラートの複数のバージョンが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f922c-175">If the same alert is generated by devices that run different operating systems, you might see multiple versions of the same alert in the alerts list.</span></span>
