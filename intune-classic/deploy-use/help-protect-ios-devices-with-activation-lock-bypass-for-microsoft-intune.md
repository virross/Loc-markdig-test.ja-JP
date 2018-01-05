---
title: "デバイスでの iOS アクティブ化ロックを管理する"
description: "Microsoft Intune では、iOS 7.1 以降向けの iPhone を探すアプリの機能である iOS のアクティブ化ロックを管理できます。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0cdc029fc439707fb42f7aff66b4739bf542ca33
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune"></a><span data-ttu-id="3e519-103">Microsoft Intune でアクティブ化ロックのバイパスを使用して iOS デバイスを保護する</span><span class="sxs-lookup"><span data-stu-id="3e519-103">Help protect iOS devices with Activation Lock bypass for Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="3e519-104">Microsoft Intune では、iOS 8.0 以降向けの iPhone を探すアプリの機能である iOS のアクティブ化ロックを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3e519-104">Microsoft Intune can help you manage iOS Activation Lock, a feature of the Find My iPhone app for iOS 8.0 and later devices.</span></span> <span data-ttu-id="3e519-105">iPhone を探すアプリをユーザーがデバイスで開くと、アクティブ化ロックが自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="3e519-105">Activation Lock is enabled automatically when a user opens the Find My iPhone app on a device.</span></span> <span data-ttu-id="3e519-106">有効になると、ユーザーの Apple ID とパスワードを入力しない限り、以下の操作を実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3e519-106">After it is enabled, the user's Apple ID and password must be entered before anyone can:</span></span> 

-   <span data-ttu-id="3e519-107">iPhone を探すアプリをオフにする</span><span class="sxs-lookup"><span data-stu-id="3e519-107">Turn off Find My iPhone</span></span>

-   <span data-ttu-id="3e519-108">デバイスを消去する</span><span class="sxs-lookup"><span data-stu-id="3e519-108">Erase the device</span></span>

-   <span data-ttu-id="3e519-109">ディスクを再アクティブ化する</span><span class="sxs-lookup"><span data-stu-id="3e519-109">Reactivate the device</span></span>

## <a name="how-activation-lock-affects-you"></a><span data-ttu-id="3e519-110">アクティブ化ロックの影響</span><span class="sxs-lookup"><span data-stu-id="3e519-110">How Activation Lock affects you</span></span>
<span data-ttu-id="3e519-111">アクティベーション ロックにより、iOS デバイスをセキュリティで保護でき、紛失や盗難にあったデバイスが戻ってくる可能性が高まりますが、この機能は IT 管理者にさまざまな課題をもたらすことがあります。</span><span class="sxs-lookup"><span data-stu-id="3e519-111">While Activation Lock helps secure iOS devices and improves the chances of recovering a lost or stolen device, this capability can present you, as an IT admin, with a number of challenges.</span></span> <span data-ttu-id="3e519-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3e519-112">For example:</span></span>

-   <span data-ttu-id="3e519-113">あるユーザーがデバイスでアクティブ化ロックを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e519-113">A user sets up Activation Lock on a device.</span></span> <span data-ttu-id="3e519-114">その後、そのユーザーが退職し、デバイスを返却します。</span><span class="sxs-lookup"><span data-stu-id="3e519-114">The user then leaves the company and returns the device.</span></span> <span data-ttu-id="3e519-115">ユーザーの Apple ID とパスワードがわからなければ、デバイスを再アクティブ化する方法がありません。</span><span class="sxs-lookup"><span data-stu-id="3e519-115">Without the user's Apple ID and password, there is no way to reactivate the device.</span></span>

-   <span data-ttu-id="3e519-116">アクティベーション ロックが有効になっているすべてのデバイスのレポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="3e519-116">You need a report of all devices that have Activation Lock enabled.</span></span>

-   <span data-ttu-id="3e519-117">組織でデバイスを更新するときに、一部のデバイスを別の部門に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e519-117">You want to reassign some devices to a different department during a device refresh in your organization.</span></span> <span data-ttu-id="3e519-118">その際に再割り当てできるのは、アクティベーション ロックが有効になっていないデバイスに限られます。</span><span class="sxs-lookup"><span data-stu-id="3e519-118">You can only reassign devices that do not have Activation Lock enabled.</span></span>

<span data-ttu-id="3e519-119">こうした問題を解決するために、Apple は iOS 7.1 でアクティブ化ロックのバイパスを導入しました。</span><span class="sxs-lookup"><span data-stu-id="3e519-119">To help solve these problems, Apple introduced Activation Lock bypass in iOS 7.1.</span></span> <span data-ttu-id="3e519-120">この機能により、ユーザーの Apple ID とパスワードがなくても、監視対象のデバイスのアクティブ化ロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="3e519-120">This lets you remove the Activation Lock from supervised devices without the user's Apple ID and password.</span></span> <span data-ttu-id="3e519-121">監視対象のデバイスでは、デバイス固有のアクティブ化ロックのバイパス コードを生成できます。このコードは、Apple のアクティブ化サーバーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3e519-121">Supervised devices can generate a device-specific Activation Lock bypass code, which is stored on Apple's activation server.</span></span>

> [!TIP]
> <span data-ttu-id="3e519-122">iOS デバイスの監視モードでは、Apple Configurator を使用して、デバイスをロックダウンし、特定のビジネス目的に必要な機能のみに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="3e519-122">Supervised mode for iOS devices lets you use Apple Configurator to lock down a device and limit functionality to specific business purposes.</span></span> <span data-ttu-id="3e519-123">監視モードは、通常、会社所有のデバイス専用の機能です。</span><span class="sxs-lookup"><span data-stu-id="3e519-123">Supervised mode is generally only for corporate-owned devices.</span></span>

<span data-ttu-id="3e519-124">アクティベーション ロックについては、 [こちら](https://support.apple.com/en-us/HT201365)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e519-124">You can read more about Activation Lock [here](https://support.apple.com/en-us/HT201365).</span></span>

## <a name="how-intune-helps-you-manage-activation-lock"></a><span data-ttu-id="3e519-125">Intune でアクティブ化ロックを管理する方法</span><span class="sxs-lookup"><span data-stu-id="3e519-125">How Intune helps you manage Activation Lock</span></span>
<span data-ttu-id="3e519-126">Intune では、iOS 8.0 以降を実行している監視対象デバイスのアクティブ化ロックの状態を要求できます。</span><span class="sxs-lookup"><span data-stu-id="3e519-126">Intune can request the Activation Lock status of supervised devices that run iOS 8.0 and later.</span></span> <span data-ttu-id="3e519-127">監視対象のデバイスのみの場合、Intune では、アクティベーション ロックのバイパス コードを取得し、直接デバイスに発行できます。</span><span class="sxs-lookup"><span data-stu-id="3e519-127">For supervised devices only, Intune can retrieve the Activation Lock bypass code and directly issue it to the device.</span></span> <span data-ttu-id="3e519-128">デバイスがワイプされている場合は、空のユーザー名とコードをパスワードとして使用し、デバイスに直接アクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e519-128">If the device has been wiped, you can directly access the device by using a blank user name and the code as the password.</span></span>

<span data-ttu-id="3e519-129">**この機能には、ビジネス上、次のメリットがあります。**</span><span class="sxs-lookup"><span data-stu-id="3e519-129">**The business benefits of this are**:</span></span>

-   <span data-ttu-id="3e519-130">ユーザーが iPhone を探すアプリのセキュリティ上のメリットを受けることができる。</span><span class="sxs-lookup"><span data-stu-id="3e519-130">The user gets the security benefits of the Find My iPhone app.</span></span>

-   <span data-ttu-id="3e519-131">デバイスを再利用する必要がある場合に、デバイスをインベントリから削除することや、ロック解除できることを把握したうえで、ユーザーが業務を遂行できるようにすることができる。</span><span class="sxs-lookup"><span data-stu-id="3e519-131">You can enable users to do their work and know that when a device needs to be re-purposed, you can retire or unlock it.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="3e519-132">開始する前に</span><span class="sxs-lookup"><span data-stu-id="3e519-132">Before you start</span></span>

<span data-ttu-id="3e519-133">デバイスのアクティブ化ロックをバイパスするには、先にそれを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e519-133">Before you can bypass Activation Lock on devices, you must enable it first.</span></span> <span data-ttu-id="3e519-134">このためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3e519-134">To do this:</span></span>

1. <span data-ttu-id="3e519-135">「[Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理する](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)」の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e519-135">Use the information in the topic [Manage settings and features on your devices with Microsoft Intune policies](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).</span></span>
2. <span data-ttu-id="3e519-136">設定ページの **[登録]** セクションで、**[デバイスが監視モードの場合にアクティブ化ロックを許可する]** を **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3e519-136">In the **Enrollment** section, of the settings page, configure the setting **Allow Activation Lock when the device is in supervised mode** to **Yes**.</span></span>
3. <span data-ttu-id="3e519-137">ポリシーを保存し、アクティブ化ロックのバイパスを管理するデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="3e519-137">Save the policy, and deploy it to the devices on which you want to manage Activation Lock bypass.</span></span>

## <a name="how-to-use-activation-lock-bypass-from-the-intune-admin-console"></a><span data-ttu-id="3e519-138">Intune 管理コンソールからアクティブ化ロックのバイパスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="3e519-138">How to use Activation Lock bypass from the Intune admin console</span></span>
> [!IMPORTANT]
> <span data-ttu-id="3e519-139">デバイスでアクティブ化ロックをバイパスした後で、iPhone を探すアプリを開くと、新しいアクティブ化ロックが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e519-139">After you bypass the Activation Lock on a device, a new Activation Lock is automatically applied if the Find My iPhone app is opened.</span></span> <span data-ttu-id="3e519-140">そのため、**デバイスが実際に手元にある状態で、この手順を実行してください。**</span><span class="sxs-lookup"><span data-stu-id="3e519-140">Because of this, **you should be in physical possession of the device before you follow this procedure**.</span></span>

1.  <span data-ttu-id="3e519-141">[Microsoft Intune の管理コンソール](https://manage.microsoft.com)で、**[グループ]** &gt; **[すべてのデバイス]** &gt; **[すべての企業所有のデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e519-141">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Groups** &gt; **All Devices** &gt; **All Corporate-owned Devices**.</span></span>

2.  <span data-ttu-id="3e519-142">アクティブ化ロックをバイパスするデバイスを選びます。</span><span class="sxs-lookup"><span data-stu-id="3e519-142">Select the device whose Activation Lock you want to bypass.</span></span> <span data-ttu-id="3e519-143">**[アクティブ化ロックのバイパス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="3e519-143">Choose **Activation Lock Bypass**.</span></span>

3.  <span data-ttu-id="3e519-144">警告メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e519-144">Read the warning message.</span></span> <span data-ttu-id="3e519-145">**[はい]** を選んで、先に進みます。</span><span class="sxs-lookup"><span data-stu-id="3e519-145">Choose **Yes** to proceed.</span></span>

<span data-ttu-id="3e519-146">デバイスの詳細ページでロック解除要求の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3e519-146">You can examine the status of the unlock request on the details page for the device.</span></span>

## <a name="how-to-see-which-devices-are-using-activation-lock"></a><span data-ttu-id="3e519-147">アクティブ化ロックを使用しているデバイスを確認する方法</span><span class="sxs-lookup"><span data-stu-id="3e519-147">How to see which devices are using Activation Lock</span></span>
<span data-ttu-id="3e519-148">アクティブ化ロックを使用しているデバイスは、次の 2 つの方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="3e519-148">You can see which devices are using Activation Lock in two ways:</span></span>

-   <span data-ttu-id="3e519-149">**モバイル デバイスのインベントリ レポート**を実行する。</span><span class="sxs-lookup"><span data-stu-id="3e519-149">Run the **Mobile Device Inventory Reports**.</span></span> <span data-ttu-id="3e519-150">このレポートには、**[アクティブ化ロックの状態]** と **[監督下]** という、デバイスの状態を示す列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e519-150">This report displays the **Activation Lock Status** and **Supervised** columns to indicate the state of devices.</span></span> <span data-ttu-id="3e519-151">**[監督下]** の値には、**[はい]** または **[いいえ]**があります。**[アクティブ化ロックの状態]** の値には、以下があります。</span><span class="sxs-lookup"><span data-stu-id="3e519-151">The values for **Supervised** are **Yes** or **No**, and the values for **Activation Lock Status** are:</span></span>

    -   <span data-ttu-id="3e519-152">バイパス コードありで有効</span><span class="sxs-lookup"><span data-stu-id="3e519-152">Enabled with bypass code</span></span>

    -   <span data-ttu-id="3e519-153">バイパス コードなしで有効 (デバイスは監視対象外)</span><span class="sxs-lookup"><span data-stu-id="3e519-153">Enabled without bypass code (device is not supervised)</span></span>

    -   <span data-ttu-id="3e519-154">バイパス コードなしで有効 (デバイスにアクセス不可)</span><span class="sxs-lookup"><span data-stu-id="3e519-154">Enabled without bypass code (device cannot be reached)</span></span>

    -   <span data-ttu-id="3e519-155">無効</span><span class="sxs-lookup"><span data-stu-id="3e519-155">Not enabled</span></span>

    <span data-ttu-id="3e519-156">iOS 8.0 以降を実行していないデバイスの場合、**[アクティブ化ロックの状態]** ボックスは空白になります。</span><span class="sxs-lookup"><span data-stu-id="3e519-156">The **Activation Lock Status** box is blank for devices that do not run iOS 8.0 or later.</span></span>

-   <span data-ttu-id="3e519-157">デバイスの詳細ウィンドウでアクティブ化ロックの状態を確認するには、グループ ビューでデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e519-157">Select a device in a groups view to see the Activation Lock status in the device details pane.</span></span>

    <span data-ttu-id="3e519-158">**[会社が所有しているすべてのデバイス]** ノードでデバイスを選んだ場合、そのデバイスでアクティブ化ロックが有効になっていると、バイパス コードも表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e519-158">If you select a device in the **All Corporate-owned Devices** node and Activation Lock is enabled for the device, you can also see the bypass code.</span></span> <span data-ttu-id="3e519-159">このコードを使用して、アクティブ化ロックのバイパスを手動で発行できます。</span><span class="sxs-lookup"><span data-stu-id="3e519-159">This code can be used to manually issue an Activation Lock bypass.</span></span>

    > [!IMPORTANT]
    ><span data-ttu-id="3e519-160">Intune は、アクティブ化ロックのために 7 日おきにデバイスからインベントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="3e519-160">Intune takes inventory from devices for Activation Lock every seven days.</span></span> <span data-ttu-id="3e519-161">このため、Intune コンソールで、デバイスとアクティブ化ロックのステータスがすぐに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e519-161">Because of this, devices might not immediately be displayed with their Activation Lock status in the Intune console.</span></span>


### <a name="see-also"></a><span data-ttu-id="3e519-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e519-162">See also</span></span>
<span data-ttu-id="3e519-163">[デバイスをインベントリから削除する](retire-devices-from-microsoft-intune-management.md)
[リモート ロックとパスコードのリセットによってデバイスを保護する](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="3e519-163">[Retire devices](retire-devices-from-microsoft-intune-management.md)
[Help protect your devices with remote lock and passcode reset](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)</span></span>
