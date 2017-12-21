---
title: "Android for Work デバイスへのアプリの割り当て"
titlesuffix: Azure portal
description: "このトピックでは、Google Play for Work ストアから Android for Work デバイスにアプリを同期してから割り当てます。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 803f1475a220e52a0f7d8a41d58f0a5337ff6555
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a><span data-ttu-id="df9a1-103">Intune を使用してアプリを Android for Work デバイスに割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="df9a1-103">How to assign apps to Android for Work devices with Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="df9a1-104">Android for Work デバイスにアプリを割り当てる方法は、標準の Android デバイスに割り当てる場合と異なります。</span><span class="sxs-lookup"><span data-stu-id="df9a1-104">You assign apps to Android for Work devices in a different way than you assign them to standard Android devices.</span></span> <span data-ttu-id="df9a1-105">Android for Work 用にインストールするすべてのアプリは、Google Play for Work ストアから入手します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-105">All apps you install for Android for Work come from the Google Play for Work store.</span></span> <span data-ttu-id="df9a1-106">ストアにログオンし、目的のアプリを検索し、アプリを承認します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-106">You log on to the store, browse for the apps you want, and approve them.</span></span>
<span data-ttu-id="df9a1-107">Azure Portal の **[ライセンスされたアプリ]** ノードにアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-107">The app then appears in the **Licensed apps** node of the Azure portal.</span></span> <span data-ttu-id="df9a1-108">ここでアプリの割り当てを管理する方法は、他のアプリを割り当てる方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="df9a1-108">From here, you can manage assignment of the app in the same way you would assign any other app.</span></span>

<span data-ttu-id="df9a1-109">また、独自の基幹業務 (LOB) アプリを作成している場合は、以下の手順でアプリを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-109">Additionally, if you have created your own line of business (LOB) apps, you can assign them as follows:</span></span>
- <span data-ttu-id="df9a1-110">Google Play ストアの非公開領域にアプリを公開できる Google Developer アカウントにサインアップする。</span><span class="sxs-lookup"><span data-stu-id="df9a1-110">Sign up for a Google Developer account that lets you publish apps to a private area in the Google Play store.</span></span>
- <span data-ttu-id="df9a1-111">そのアプリを Intune と同期する。</span><span class="sxs-lookup"><span data-stu-id="df9a1-111">Synchronize the apps with Intune.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="df9a1-112">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="df9a1-112">Before you start</span></span>

<span data-ttu-id="df9a1-113">Intune と Android for Work が Azure Portal の **[デバイスの登録]** ワークロードで連携するように構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-113">Make sure you have configured Intune and Android for Work to work together in the **Device enrollment** workload of the Azure portal.</span></span>

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a><span data-ttu-id="df9a1-114">Google Play for Work ストアのアプリを同期する</span><span class="sxs-lookup"><span data-stu-id="df9a1-114">Synchronize an app from the Google Play for Work store</span></span>

1. <span data-ttu-id="df9a1-115">[Google Play for Work ストア](https://play.google.com/work)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="df9a1-115">Go to the [Google Play for Work store](https://play.google.com/work).</span></span> <span data-ttu-id="df9a1-116">Intune と Android for Work 間の接続を構成するときに使用したものと同じアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="df9a1-116">Sign in with the same account you used to configure the connection between Intune and Android for Work.</span></span>
2. <span data-ttu-id="df9a1-117">Intune を使用して割り当てるアプリをストアで検索します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-117">Search the store for the app you want to assign using Intune.</span></span>
3. <span data-ttu-id="df9a1-118">選択するアプリのページで、**[承認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-118">On the page for the app you chose, choose **Approve**.</span></span> <span data-ttu-id="df9a1-119">この例では、Microsoft Excel アプリを選択しました。</span><span class="sxs-lookup"><span data-stu-id="df9a1-119">In this example, you have chosen the Microsoft Excel app.</span></span><br>
  <span data-ttu-id="df9a1-120">![アプリの例を承認します。](media/approve.png)</span><span class="sxs-lookup"><span data-stu-id="df9a1-120">![Approve app example](media/approve.png)</span></span>
4. <span data-ttu-id="df9a1-121">多様な操作を実行するアクセス許可をアプリに付与するように求めるウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-121">A window for the app opens asking you to give permissions for the app to perform various operations.</span></span> <span data-ttu-id="df9a1-122">続行するには、**[承認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-122">Choose **Approve** to continue.</span></span><br>
  <span data-ttu-id="df9a1-123">![アプリのアクセス許可の例を承認します。](media/approve-app-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="df9a1-123">![Approve app permissions example](media/approve-app-permissions.png)</span></span>
5. <span data-ttu-id="df9a1-124">アプリは承認され、IT 管理者コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-124">The app is approved and displays in your IT admin console.</span></span>

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a><span data-ttu-id="df9a1-125">Google Play for Work ストアから基幹業務アプリを公開し、同期する</span><span class="sxs-lookup"><span data-stu-id="df9a1-125">Publish, then synchronize, a line-of-business app from the Google Play for Work store</span></span>

1. <span data-ttu-id="df9a1-126">Google Play Developer Console で、[play.google.com/apps/publish](https://play.google.com/apps/publish) を開きます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-126">Go to the Google Play Developer Console, [play.google.com/apps/publish](https://play.google.com/apps/publish).</span></span>
2. <span data-ttu-id="df9a1-127">Intune と Android for Work 間の接続を構成するときに使用したものと同じアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="df9a1-127">Sign in with the same account you used to configure the connection between Intune and Android for Work.</span></span> <span data-ttu-id="df9a1-128">初めてサインインする場合は、Google Developer プログラムに登録し、料金を払ってメンバーになる必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9a1-128">If you are signing in for the first time, you must register, and pay a fee to become a member of the Google Developer program.</span></span>
3. <span data-ttu-id="df9a1-129">コンソールで、**[Add new application]** (新しいアプリケーションの追加) を選択します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-129">In the console, choose **Add new application**.</span></span>
4. <span data-ttu-id="df9a1-130">アプリをアップロードし、アプリに関する情報を提供する方法は、アプリを Google Play ストアに公開する方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="df9a1-130">You upload and provide information about your app in the same way as you publish any app to the Google Play store.</span></span> <span data-ttu-id="df9a1-131">ただし、**[Only make this application available to my organization (<*organization name*>)]\(このアプリケーションを自分の組織 (<組織名>) のみが入手できるようにする\) の設定を選択する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="df9a1-131">However, you must select the setting **Only make this application available to my organization (<*organization name*>)**:</span></span><br>
  <span data-ttu-id="df9a1-132">![アプリを組織に利用できるようにのみオプション](media/restrict.png)</span><span class="sxs-lookup"><span data-stu-id="df9a1-132">![Option to only make app available to your organization](media/restrict.png)</span></span><br>
<span data-ttu-id="df9a1-133">この操作により、自分の組織のみがアプリを入手でき、公開されている Google Play ストアでは入手できないようになります。</span><span class="sxs-lookup"><span data-stu-id="df9a1-133">This operation ensures that the app is only available to your organization, and is not available in the public Google Play store.</span></span>
<span data-ttu-id="df9a1-134">Android アプリのアップロードと公開の詳細については、[Google Developer Console のヘルプ](https://support.google.com/googleplay/android-developer/answer/113469)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df9a1-134">For more information about how to upload and publish Android apps, see the [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469).</span></span>
5. <span data-ttu-id="df9a1-135">アプリを公開したら、[Google Play for Work ストア](https://play.google.com/work)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="df9a1-135">Once you have published your app, go to the [Google Play for Work store](https://play.google.com/work).</span></span> <span data-ttu-id="df9a1-136">Intune と Android for Work 間の接続を構成するときに使用したものと同じアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="df9a1-136">Sign in with the same account you used to configure the connection between Intune and Android for Work.</span></span>
6. <span data-ttu-id="df9a1-137">ストアの **[アプリ]** ノードに、公開したアプリが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-137">In the **Apps** node of the store, verify you can see the app you have published.</span></span> <span data-ttu-id="df9a1-138">アプリは自動的に承認され、Intune と同期されます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-138">The app is automatically approved to be synchronized with Intune.</span></span>

## <a name="assign-an-android-for-work-app"></a><span data-ttu-id="df9a1-139">Android for Work アプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="df9a1-139">Assign an Android for Work app</span></span>

<span data-ttu-id="df9a1-140">ストアのアプリを承認しても、**[モバイル アプリ]** ワークロードの **[ライセンスされたアプリ]** ノードに表示されない場合は、次の手順で強制的に即時に同期します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-140">If you have approved an app from the store and don't see it in the **Licensed apps** node of the **Mobile apps** workload, force an immediate sync as follows:</span></span>

1. <span data-ttu-id="df9a1-141">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="df9a1-141">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="df9a1-142">**[Intune]** ブレードで、**[モバイル アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-142">On the **Intune** blade, choose **Mobile apps**.</span></span>
3. <span data-ttu-id="df9a1-143">**[モバイル アプリ]** ワークロードで、**[セットアップ]** > **[Android for Work]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-143">In the **Mobile apps** workload, choose **Setup** > **Android for Work**.</span></span>
4. <span data-ttu-id="df9a1-144">[Android for Work] ブレードです、**[今すぐ同期]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-144">On the Android for Work blade, choose **Sync Now**.</span></span>
5. <span data-ttu-id="df9a1-145">ページには、前回の同期の時刻と状態も表示されます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-145">The page also displays the time and status of the last sync.</span></span>

<span data-ttu-id="df9a1-146">アプリが **[モバイル アプリ]** ワークロードの **[ライセンスされたアプリ]** ノードに表示される場合は、[他のアプリの割り当てと同様の方法でアプリを割り当てることができます](/intune-azure/manage-apps/deploy-apps)。</span><span class="sxs-lookup"><span data-stu-id="df9a1-146">When the app is displayed in the **Licensed apps** node of the **Mobile apps** workload, you can [assign it just like you would assign any other app](/intune-azure/manage-apps/deploy-apps).</span></span> <span data-ttu-id="df9a1-147">ユーザーのグループに対してのみアプリを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-147">You can assign the app to groups of users only.</span></span>

<span data-ttu-id="df9a1-148">アプリを割り当てると、アプリは対象のデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-148">After you assign the app, it will be installed on the devices you targeted.</span></span> <span data-ttu-id="df9a1-149">デバイスのユーザーがインストールの承認を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="df9a1-149">The user of the device is not asked to approve the installation.</span></span>

## <a name="manage-android-for-work-app-permissions"></a><span data-ttu-id="df9a1-150">Android for Work アプリのアクセス許可の管理</span><span class="sxs-lookup"><span data-stu-id="df9a1-150">Manage Android for Work app permissions</span></span>
<span data-ttu-id="df9a1-151">Android for Work では、Intune にアプリを同期してユーザーに割り当てる前に、Google が管理する Web コンソールの Play でアプリを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9a1-151">Android for Work requires you approve apps in Google's managed Play web console before syncing them to Intune and assigning them to your users.</span></span>  <span data-ttu-id="df9a1-152">Android for Work により、これらのアプリがユーザーのデバイスに通知なしで自動的にプッシュできるようになるため、ユーザー全員に代わってアプリへのアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9a1-152">Because Android for Work allows you to silently and automatically push these apps to users' devices, you must accept the app's permissions on behalf of all your users.</span></span>  <span data-ttu-id="df9a1-153">エンド ユーザーがインストールする際はアプリのアクセス許可に関する表示が行われないため、これらのアクセス許可について学習し、理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df9a1-153">End users do not see any app permissions when they install, so it's important that you read and understand these permissions.</span></span>

<span data-ttu-id="df9a1-154">アプリ開発者がアプリの新しいバージョンを公開する際、以前のバージョンのアクセスを許可していても、新しいバージョンのアクセスは自動的に許可されません。</span><span class="sxs-lookup"><span data-stu-id="df9a1-154">When an app developer publishes a new version of the app with updated permissions, those permissions are not automatically accepted, even if you've approved the previous permissions.</span></span> <span data-ttu-id="df9a1-155">古いバージョンのアプリを実行しているデバイスは、そのアプリを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-155">Devices that run the old version of the app can still use it.</span></span> <span data-ttu-id="df9a1-156">ただし、新しいアクセス許可が承認されるまで、アプリはアップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="df9a1-156">However, the app is not upgraded until the new permissions are approved.</span></span> <span data-ttu-id="df9a1-157">アプリをインストールしていないデバイスでは、アプリの新しいアクセス許可を承認するまで、アプリをインストールしません。</span><span class="sxs-lookup"><span data-stu-id="df9a1-157">Devices without the app installed do not install the app until you approve the app's new permissions.</span></span>

### <a name="how-to-update-app-permissions"></a><span data-ttu-id="df9a1-158">アプリのアクセス許可を更新する方法</span><span class="sxs-lookup"><span data-stu-id="df9a1-158">How to update app permissions</span></span>

<span data-ttu-id="df9a1-159">管理対象の Google Play コンソールに定期的にアクセスして、新しいアクセス許可があるかどうか確認してください。</span><span class="sxs-lookup"><span data-stu-id="df9a1-159">Periodically visit the managed Google Play console to check for new permissions.</span></span> <span data-ttu-id="df9a1-160">承認済みのアプリに新しいアクセス許可が必要な場合は、Google Play を構成して、自分や他のユーザーあてに電子メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-160">You can configure Google Play to send you or others an e-mail when new permissions are required for an approved app.</span></span> <span data-ttu-id="df9a1-161">アプリを割り当ててもデバイスにインストールされていない場合は、まだ許可していないアクセス許可が新しくあるかどうかを、次の手順で確認します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-161">If you assign an app and observe it isn't installed on devices, check for new permissions with the following steps:</span></span>

1. <span data-ttu-id="df9a1-162">http://play.google.com/work にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="df9a1-162">Visit http://play.google.com/work</span></span>
2. <span data-ttu-id="df9a1-163">アプリを公開して承認する際に使用した Google アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="df9a1-163">Sign in with the Google account you used to publish and approve the apps.</span></span>
3. <span data-ttu-id="df9a1-164">**[更新]** タブにアクセスして、更新が必要なアプリがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="df9a1-164">Visit the **Updates** tab to see if any apps require an update.</span></span>  <span data-ttu-id="df9a1-165">一覧にあるアプリでは新しいアクセス許可が必要で、それらが適用されるまで割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="df9a1-165">Any listed apps require new permissions and are not assigned until they are applied.</span></span>  

<span data-ttu-id="df9a1-166">あるいは、Google Play を構成することで、アプリごとにアクセス許可を自動的に再許可できます。</span><span class="sxs-lookup"><span data-stu-id="df9a1-166">Alternatively, you can configure Google Play to automatically reapprove app permissions on a per app basis.</span></span> 



