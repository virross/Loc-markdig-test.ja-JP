---
title: "Intune での iOS アクティベーション ロックをバイパスする"
titlesuffix: Azure portal
description: "Intune を使用して、iOS アクティベーション ロックをバイパスし、ロックされたデバイスにアクセスする方法を説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/22/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3cd1c7d68cba09c3483cd346772e9791d66c490
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a><span data-ttu-id="9ea74-103">Intune で、監視されている iOS デバイス上のアクティベーション ロックをバイパスする</span><span class="sxs-lookup"><span data-stu-id="9ea74-103">Bypass Activation Lock on Supervised iOS devices with Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="9ea74-104">Microsoft Intune では、iOS 8.0 以降向けの iPhone を探すアプリの機能である iOS のアクティブ化ロックを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-104">Microsoft Intune can help you manage iOS Activation Lock, a feature of the Find My iPhone app for iOS 8.0 and later devices.</span></span> <span data-ttu-id="9ea74-105">iPhone を探すアプリをユーザーがデバイスで開くと、アクティブ化ロックが自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="9ea74-105">Activation Lock is enabled automatically when a user opens the Find My iPhone app on a device.</span></span> <span data-ttu-id="9ea74-106">有効になると、ユーザーの Apple ID とパスワードを入力しない限り、以下の操作を実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9ea74-106">After it is enabled, the user's Apple ID and password must be entered before anyone can:</span></span>

- <span data-ttu-id="9ea74-107">iPhone を探すアプリをオフにする</span><span class="sxs-lookup"><span data-stu-id="9ea74-107">Turn off Find My iPhone</span></span>
- <span data-ttu-id="9ea74-108">デバイスを消去する</span><span class="sxs-lookup"><span data-stu-id="9ea74-108">Erase the device</span></span>
- <span data-ttu-id="9ea74-109">ディスクを再アクティブ化する</span><span class="sxs-lookup"><span data-stu-id="9ea74-109">Reactivate the device</span></span>

## <a name="how-activation-lock-affects-you"></a><span data-ttu-id="9ea74-110">アクティブ化ロックの影響</span><span class="sxs-lookup"><span data-stu-id="9ea74-110">How Activation Lock affects you</span></span>

<span data-ttu-id="9ea74-111">アクティベーション ロックにより、iOS デバイスをセキュリティで保護でき、紛失や盗難にあったデバイスが戻ってくる可能性が高まりますが、この機能は IT 管理者にさまざまな課題をもたらすことがあります。</span><span class="sxs-lookup"><span data-stu-id="9ea74-111">While Activation Lock helps secure iOS devices and improves the chances of recovering a lost or stolen device, this capability can present you, as an IT admin, with a number of challenges.</span></span> <span data-ttu-id="9ea74-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9ea74-112">For example:</span></span>

- <span data-ttu-id="9ea74-113">あるユーザーがデバイスでアクティブ化ロックを設定します。</span><span class="sxs-lookup"><span data-stu-id="9ea74-113">A user sets up Activation Lock on a device.</span></span> <span data-ttu-id="9ea74-114">その後、そのユーザーが退職し、デバイスを返却します。</span><span class="sxs-lookup"><span data-stu-id="9ea74-114">The user then leaves the company and returns the device.</span></span> <span data-ttu-id="9ea74-115">ユーザーの Apple ID とパスワードがわからなければ、デバイスを再アクティブ化する方法がありません。</span><span class="sxs-lookup"><span data-stu-id="9ea74-115">Without the user's Apple ID and password, there is no way to reactivate the device.</span></span>
- <span data-ttu-id="9ea74-116">アクティベーション ロックが有効になっているすべてのデバイスのレポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="9ea74-116">You need a report of all devices that have Activation Lock enabled.</span></span>
- <span data-ttu-id="9ea74-117">組織でデバイスを更新するときに、一部のデバイスを別の部門に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ea74-117">You want to reassign some devices to a different department during a device refresh in your organization.</span></span> <span data-ttu-id="9ea74-118">その際に再割り当てできるのは、アクティベーション ロックが有効になっていないデバイスに限られます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-118">You can only reassign devices that do not have Activation Lock enabled.</span></span>

<span data-ttu-id="9ea74-119">こうした問題を解決するために、Apple は iOS 7.1 でアクティブ化ロックのバイパスを導入しました。</span><span class="sxs-lookup"><span data-stu-id="9ea74-119">To help solve these problems, Apple introduced Activation Lock bypass in iOS 7.1.</span></span> <span data-ttu-id="9ea74-120">アクティベーション ロックのバイパスにより、ユーザーの Apple ID とパスワードがなくても、監視対象のデバイスのアクティベーション ロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-120">Activation Lock bypass lets you remove the Activation Lock from supervised devices without the user's Apple ID and password.</span></span> <span data-ttu-id="9ea74-121">監視対象のデバイスでは、デバイス固有のアクティブ化ロックのバイパス コードを生成できます。このコードは、Apple のアクティブ化サーバーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-121">Supervised devices can generate a device-specific Activation Lock bypass code, which is stored on Apple's activation server.</span></span>

>[!TIP]
><span data-ttu-id="9ea74-122">iOS デバイスの監視モードでは、Apple Configurator を使用して、デバイスをロックダウンし、特定のビジネス目的に必要な機能のみに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-122">Supervised mode for iOS devices lets you use Apple Configurator to lock down a device and limit functionality to specific business purposes.</span></span> <span data-ttu-id="9ea74-123">監視モードは、会社所有のデバイス専用の機能です。</span><span class="sxs-lookup"><span data-stu-id="9ea74-123">Supervised mode is used only for corporate-owned devices.</span></span>

<span data-ttu-id="9ea74-124">アクティベーション ロックについては、[Apple の Web サイト](https://support.apple.com/HT201365)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9ea74-124">You can read more about Activation Lock on [Apple's web site](https://support.apple.com/HT201365).</span></span>

## <a name="how-intune-helps-you-manage-activation-lock"></a><span data-ttu-id="9ea74-125">Intune でアクティブ化ロックを管理する方法</span><span class="sxs-lookup"><span data-stu-id="9ea74-125">How Intune helps you manage Activation Lock</span></span>
<span data-ttu-id="9ea74-126">Intune では、iOS 8.0 以降を実行している監視対象デバイスのアクティブ化ロックの状態を要求できます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-126">Intune can request the Activation Lock status of supervised devices that run iOS 8.0 and later.</span></span> <span data-ttu-id="9ea74-127">監視対象のデバイスのみの場合、Intune では、アクティベーション ロックのバイパス コードを取得し、直接デバイスに発行できます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-127">For supervised devices only, Intune can retrieve the Activation Lock bypass code and directly issue it to the device.</span></span> <span data-ttu-id="9ea74-128">デバイスがワイプされている場合は、空のユーザー名とコードをパスワードとして使用し、デバイスに直接アクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-128">If the device has been wiped, you can directly access the device by using a blank user name and the code as the password.</span></span>

<span data-ttu-id="9ea74-129">**Intune を使用してアクティベーション ロックを管理するビジネス上の利点は次のとおりです。**</span><span class="sxs-lookup"><span data-stu-id="9ea74-129">**The business benefits of using Intune to manage Activation Lock are:**</span></span>

- <span data-ttu-id="9ea74-130">ユーザーが iPhone を探すアプリのセキュリティ上のメリットを受けることができる。</span><span class="sxs-lookup"><span data-stu-id="9ea74-130">The user gets the security benefits of the Find My iPhone app.</span></span>
- <span data-ttu-id="9ea74-131">デバイスを再利用する必要がある場合に、デバイスをインベントリから削除することや、ロック解除できることを把握したうえで、ユーザーが業務を遂行できるようにすることができる。</span><span class="sxs-lookup"><span data-stu-id="9ea74-131">You can enable users to do their work and know that when a device needs to be repurposed, you can retire or unlock it.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="9ea74-132">開始する前に</span><span class="sxs-lookup"><span data-stu-id="9ea74-132">Before you start</span></span>
<span data-ttu-id="9ea74-133">デバイスのアクティベーション ロックをバイパスするには、次の手順に従って先にそれを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ea74-133">Before you can bypass Activation Lock on devices, you must enable it by following these instructions:</span></span>

1. <span data-ttu-id="9ea74-134">[デバイスの制限設定を構成する方法](/intune-azure/configure-devices/how-to-configure-device-restrictions)に関するページにある情報を使用して、iOS 用の Intune デバイス制限プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="9ea74-134">Configure an Intune device restriction profile for iOS using the information in [How to configure device restriction settings](/intune-azure/configure-devices/how-to-configure-device-restrictions).</span></span>
2. <span data-ttu-id="9ea74-135">[iOS のデバイス制限設定](device-restrictions-ios.md)の **[全般]** 設定で、**[アクティベーション ロック]** オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9ea74-135">In the [device restriction settings for iOS](device-restrictions-ios.md), under the **General** settings, enable the option **Activation Lock**.</span></span>
3. <span data-ttu-id="9ea74-136">プロファイルを保存し、アクティベーション ロックのバイパスを管理するデバイスに[割り当て](device-profile-assign.md)ます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-136">Save the profile, and then [assign it](device-profile-assign.md) to the devices on which you want to manage Activation Lock bypass.</span></span>


## <a name="how-to-use-activation-lock-bypass"></a><span data-ttu-id="9ea74-137">アクティベーション ロックのバイパスの使用方法</span><span class="sxs-lookup"><span data-stu-id="9ea74-137">How to use Activation Lock bypass</span></span>

>[!IMPORTANT]
><span data-ttu-id="9ea74-138">デバイスでアクティベーション ロックをバイパスした後で、iPhone を探すアプリを開くと、新しいアクティベーション ロックが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-138">After you bypass the Activation Lock on a device, if the Find My iPhone app is opened, a new Activation Lock is automatically applied.</span></span> <span data-ttu-id="9ea74-139">そのため、**デバイスが実際に手元にある状態で、この手順を実行してください。**</span><span class="sxs-lookup"><span data-stu-id="9ea74-139">Because of this, **you should be in physical possession of the device before you follow this procedure**.</span></span>

<span data-ttu-id="9ea74-140">Intune の **[アクティブ化ロックのバイパス]** のリモート デバイス操作では、ユーザーの Apple ID とパスワードを使用せずに iOS デバイスのアクティベーション ロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="9ea74-140">The Intune **Bypass Activation Lock** remote device action removes the activation lock from an iOS device without the user’s Apple ID and password.</span></span> <span data-ttu-id="9ea74-141">アクティブ化ロックをバイパスした後に iPhone を探すアプリを起動すると、デバイスのアクティブ化ロックが再度有効になります。</span><span class="sxs-lookup"><span data-stu-id="9ea74-141">Once you bypass the activation lock, the device turns on activation lock again when the Find My iPhone app launches.</span></span> <span data-ttu-id="9ea74-142">デバイスに物理的にアクセスできる場合にのみアクティブ化ロックをバイパスしてください。</span><span class="sxs-lookup"><span data-stu-id="9ea74-142">Only bypass the activation lock if you have physical access to the device.</span></span>

1. <span data-ttu-id="9ea74-143">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9ea74-143">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="9ea74-144">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea74-144">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="9ea74-145">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea74-145">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="9ea74-146">**[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea74-146">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="9ea74-147">管理するデバイスの一覧から監視対象の iOS デバイスを選択し、その後 **[アクティブ化ロックのバイパス]** デバイス リモート操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ea74-147">From the list of devices you manage, choose a supervised iOS device, and then choose the **Bypass Activation Lock** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ea74-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="9ea74-148">Next steps</span></span>

<span data-ttu-id="9ea74-149">**[デバイスの管理]** ワークロード内のデバイスの詳細ページで、ロック解除要求の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9ea74-149">You can examine the status of the unlock request on the details page for the device in the **Manage devices** workload.</span></span>
