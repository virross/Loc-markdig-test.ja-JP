---
title: "アプリを Android for Work デバイスに展開する"
description: "このトピックでは、Google Play for Work ストアから Android for Work デバイスにアプリを同期してから展開します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 63eea7c63e628aeb0fa8b6f131fb01eeb511c0c9
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a><span data-ttu-id="91f63-103">Intune を使用してアプリを Android for Work デバイスを展開する方法</span><span class="sxs-lookup"><span data-stu-id="91f63-103">How to deploy apps to Android for Work devices with Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="91f63-104">Android for Work デバイスにアプリを展開する方法は、標準の Android デバイスに展開する場合と異なります。</span><span class="sxs-lookup"><span data-stu-id="91f63-104">You deploy apps to Android for Work devices in a different way than you deploy them to standard Android devices.</span></span> <span data-ttu-id="91f63-105">Android for Work 用にインストールするすべてのアプリは、Google Play for Work ストアから入手します。</span><span class="sxs-lookup"><span data-stu-id="91f63-105">All apps you install for Android for Work come from the Google Play for Work store.</span></span> <span data-ttu-id="91f63-106">ストアにログオンし、目的のアプリを検索し、アプリを承認します。</span><span class="sxs-lookup"><span data-stu-id="91f63-106">You log on to the store, browse for the apps you want, and approve them.</span></span>
<span data-ttu-id="91f63-107">承認したアプリは、Intune コンソールの **[ボリューム購入アプリ]** ノードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="91f63-107">The app then appears in the **Volume-Purchased Apps** node of the Intune console.</span></span> <span data-ttu-id="91f63-108">ここでアプリの展開を管理する方法は、他のアプリを展開する方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="91f63-108">From here, you can manage deployment of the app in the same way you would deploy any other app.</span></span>

<span data-ttu-id="91f63-109">また、独自の基幹業務 (LOB) アプリを作成している場合は、そのアプリを次のように展開できます。</span><span class="sxs-lookup"><span data-stu-id="91f63-109">Additionally, if you have created your own line of business (LOB) apps, you can deploy them as follows:</span></span>
- <span data-ttu-id="91f63-110">Google Developer アカウントにサインアップして、Google Play ストアの非公開領域にアプリを公開する。</span><span class="sxs-lookup"><span data-stu-id="91f63-110">Sign up for a Google Developer account, which lets you publish apps to a private area in the Google Play store.</span></span>
- <span data-ttu-id="91f63-111">そのアプリを Intune と同期する。</span><span class="sxs-lookup"><span data-stu-id="91f63-111">Synchronize the apps with Intune.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="91f63-112">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="91f63-112">Before you start</span></span>

<span data-ttu-id="91f63-113">Intune コンソールの **[管理者]** タブで連携して動作するように、Intune と Android for Work を構成します。</span><span class="sxs-lookup"><span data-stu-id="91f63-113">Make sure you have configured Intune and Android for Work to work together in the **Admin** tab of the Intune console.</span></span>

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a><span data-ttu-id="91f63-114">Google Play for Work ストアのアプリを同期する</span><span class="sxs-lookup"><span data-stu-id="91f63-114">Synchronize an app from the Google Play for Work store</span></span>


1. <span data-ttu-id="91f63-115">[Google Play for Work ストア](https://play.google.com/work)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="91f63-115">Go to the [Google Play for Work store](https://play.google.com/work).</span></span> <span data-ttu-id="91f63-116">Intune と Android for Work 間の接続を構成するときに使用したものと同じアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="91f63-116">Sign in with the same account you used to configure the connection between Intune and Android for Work.</span></span>
2. <span data-ttu-id="91f63-117">Intune を使用して展開するアプリをストアで検索します。</span><span class="sxs-lookup"><span data-stu-id="91f63-117">Search the store for the app you want to deploy using Intune.</span></span>
3. <span data-ttu-id="91f63-118">選択するアプリのページで、**[承認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="91f63-118">On the page for the app you chose, choose **Approve**.</span></span> <span data-ttu-id="91f63-119">この例では、Microsoft Excel アプリを選択しました。</span><span class="sxs-lookup"><span data-stu-id="91f63-119">In this example, you have chosen the Microsoft Excel app.</span></span><br>
  <span data-ttu-id="91f63-120">![アプリの例を承認します。](media/approve.png)</span><span class="sxs-lookup"><span data-stu-id="91f63-120">![Approve app example](media/approve.png)</span></span>
4. <span data-ttu-id="91f63-121">多様な操作を実行するアクセス許可をアプリに付与するように求めるウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="91f63-121">A window for the app opens asking you to give permissions for the app to perform various operations.</span></span> <span data-ttu-id="91f63-122">続行するには、**[承認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="91f63-122">Choose **Approve** to continue.</span></span><br>
  <span data-ttu-id="91f63-123">![アプリのアクセス許可の例を承認します。](media/approve-app-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="91f63-123">![Approve app permissions example](media/approve-app-permissions.png)</span></span>
5. <span data-ttu-id="91f63-124">アプリは承認され、IT 管理者コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="91f63-124">The app is approved and displays in your IT admin console.</span></span>

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a><span data-ttu-id="91f63-125">Google Play for Work ストアから基幹業務アプリを公開し、同期する</span><span class="sxs-lookup"><span data-stu-id="91f63-125">Publish, then synchronize, a line-of-business app from the Google Play for Work store</span></span>

1. <span data-ttu-id="91f63-126">Google Play Developer Console で、[play.google.com/apps/publish](https://play.google.com/apps/publish) を開きます。</span><span class="sxs-lookup"><span data-stu-id="91f63-126">Go to the Google Play Developer Console, [play.google.com/apps/publish](https://play.google.com/apps/publish).</span></span>
2. <span data-ttu-id="91f63-127">Intune と Android for Work 間の接続を構成するときに使用したものと同じアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="91f63-127">Sign in with the same account you used to configure the connection between Intune and Android for Work.</span></span> <span data-ttu-id="91f63-128">初めてサインインする場合は、Google Developer プログラムに登録し、料金を払ってメンバーになる必要があります。</span><span class="sxs-lookup"><span data-stu-id="91f63-128">If you are signing in for the first time, you must register, and pay a fee to become a member of the Google Developer program.</span></span>
3. <span data-ttu-id="91f63-129">コンソールで、**[Add new application]** (新しいアプリケーションの追加) を選択します。</span><span class="sxs-lookup"><span data-stu-id="91f63-129">In the console, choose **Add new application**.</span></span>
4. <span data-ttu-id="91f63-130">アプリをアップロードし、アプリに関する情報を提供する方法は、アプリを Google Play ストアに公開する方法と同じです。</span><span class="sxs-lookup"><span data-stu-id="91f63-130">You upload and provide information about your app in the same way as you publish any app to the Google Play store.</span></span> <span data-ttu-id="91f63-131">ただし、**[Only make this application available to my organization (<*organization name*>)]\(このアプリケーションを自分の組織 (<組織名>) のみが入手できるようにする\) の設定を選択する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="91f63-131">However, you must select the setting **Only make this application available to my organization (<*organization name*>)**:</span></span><br>
  <span data-ttu-id="91f63-132">![アプリを組織に利用できるようにのみオプション](media/restrict.png)</span><span class="sxs-lookup"><span data-stu-id="91f63-132">![Option to only make app available to your organization](media/restrict.png)</span></span><br>
<span data-ttu-id="91f63-133">この操作により、自分の組織のみがアプリを入手でき、公開されている Google Play ストアでは入手できないようになります。</span><span class="sxs-lookup"><span data-stu-id="91f63-133">This operation ensures that the app is only available to your organization, and is not available in the public Google Play store.</span></span>
<span data-ttu-id="91f63-134">Android アプリのアップロードと公開の詳細については、[Google Developer Console のヘルプ](https://support.google.com/googleplay/android-developer/answer/113469)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91f63-134">For more information about how to upload and publish Android apps, see the [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469).</span></span>
5. <span data-ttu-id="91f63-135">アプリを公開したら、[Google Play for Work ストア](https://play.google.com/work)にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="91f63-135">Once you have published your app, go to the [Google Play for Work store](https://play.google.com/work).</span></span> <span data-ttu-id="91f63-136">Intune と Android for Work 間の接続を構成するときに使用したものと同じアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="91f63-136">Sign in with the same account you used to configure the connection between Intune and Android for Work.</span></span>
6. <span data-ttu-id="91f63-137">ストアの **[アプリ]** ノードに、公開したアプリが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="91f63-137">In the **Apps** node of the store, verify you can see the app you have published.</span></span> <span data-ttu-id="91f63-138">Intune と同期するように自動的に承認されます。</span><span class="sxs-lookup"><span data-stu-id="91f63-138">It is automatically approved to synchronize with Intune.</span></span>

## <a name="deploy-an-android-for-work-app"></a><span data-ttu-id="91f63-139">Android for Work アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="91f63-139">Deploy an Android for Work app</span></span>

<span data-ttu-id="91f63-140">ストアのアプリを承認しても、**[アプリ]** ワークスペースの **[ボリューム購入アプリ]** ノードに表示されない場合は、次の手順で強制的に即時に同期します。</span><span class="sxs-lookup"><span data-stu-id="91f63-140">If you approved an app from the store and don't see it in the **Volume-Purchased Apps** node of the **Apps** workspace, force an immediate sync as follows:</span></span>

1. <span data-ttu-id="91f63-141">[Intune 管理コンソール](https://manage.microsoft.com)で、**[管理]** > **[モバイル デバイス管理]** > **[Android for Work]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="91f63-141">In the [Intune administrator console](https://manage.microsoft.com), choose **Admin** > **Mobile Device Management** > **Android for Work**.</span></span>
2. <span data-ttu-id="91f63-142">**[Android for Work モバイル デバイス管理のセットアップ]** ページで、**[今すぐ同期]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="91f63-142">On the **Android for Work Mobile Device Management Setup** page, choose **Sync Now**.</span></span>
3. <span data-ttu-id="91f63-143">ページには、前回の同期の時刻と状態も表示されます。</span><span class="sxs-lookup"><span data-stu-id="91f63-143">The page also displays the time and status of the last sync.</span></span>

<span data-ttu-id="91f63-144">アプリが **[アプリ]** ワークスペースの **[ボリューム購入アプリ]** ノードに表示される場合は、[他のアプリと同様の方法でアプリを展開](deploy-apps-in-microsoft-intune.md)できます。</span><span class="sxs-lookup"><span data-stu-id="91f63-144">When the app is displayed in the **Volume-Purchased Apps** node of the **Apps** workspace, you can [deploy it just like you would do with any other app](deploy-apps-in-microsoft-intune.md).</span></span> <span data-ttu-id="91f63-145">ユーザーのグループに対してのみアプリを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="91f63-145">You can deploy the app to groups of users only.</span></span> <span data-ttu-id="91f63-146">現在、**[必須]** アクションと **[アンインストール]** アクションのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="91f63-146">Currently, you can only select the **Required** and **Uninstall** actions.</span></span>

<span data-ttu-id="91f63-147">アプリを **[使用可能]** としてデプロイできるため、新しいグループ化とターゲット化エクスペリエンスを適用できます。</span><span class="sxs-lookup"><span data-stu-id="91f63-147">The ability to deploy an app as **Available** applies the new grouping and targeting experience.</span></span> <span data-ttu-id="91f63-148">この機能はリリース後、新しくプロビジョニングされた Intune サービス アカウントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="91f63-148">Newly provisioned Intune service accounts can use this feature upon release.</span></span> <span data-ttu-id="91f63-149">既存の Intune ユーザーは、テナントが Intune Azure ポータルに移行した後に、この機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="91f63-149">Existing Intune customers can use this feature once their tenant has been migrated to the Intune Azure portal.</span></span> <span data-ttu-id="91f63-150">既存のユーザーは、試用の Intune アカウントを作成して、テナントが移行されるまでの間にこの機能を検討しテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="91f63-150">Existing customers can create a trial Intune account to plan for and test this feature until their tenant has been migrated.</span></span>

<span data-ttu-id="91f63-151">アプリを展開すると、アプリは対象のデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="91f63-151">After you deploy the app, it will be installed on the devices you targeted.</span></span> <span data-ttu-id="91f63-152">デバイスのユーザーは、承認を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="91f63-152">The user of the device is not asked for approval.</span></span>

## <a name="manage-app-permissions"></a><span data-ttu-id="91f63-153">アプリのアクセス許可の管理</span><span class="sxs-lookup"><span data-stu-id="91f63-153">Manage app permissions</span></span>
<span data-ttu-id="91f63-154">Android for Work では、Intune にアプリを同期してユーザーにデプロイする前に、Google が管理する Web コンソールの Play でアプリを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91f63-154">Android for Work requires you approve apps in Google's managed Play web console before syncing them to Intune and deploying them to your users.</span></span>  <span data-ttu-id="91f63-155">Android for Work により、これらのアプリがユーザーのデバイスに通知なしで自動的にプッシュできるようになるため、ユーザー全員に代わってアプリへのアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91f63-155">Because Android for Work allows you to silently and automatically push these apps to users' devices, you must accept the app's permissions on behalf of all your users.</span></span>  <span data-ttu-id="91f63-156">エンド ユーザーがインストールする際はアプリのアクセス許可に関する表示が行われないため、これらのアクセス許可について学習し、理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91f63-156">End users do not see any app permissions when they install, so it's important that you read and understand these permissions.</span></span>

<span data-ttu-id="91f63-157">アプリ開発者がアプリの新しいバージョンを公開する際、以前のバージョンのアクセスを許可していても、新しいバージョンのアクセスは自動的に許可されません。</span><span class="sxs-lookup"><span data-stu-id="91f63-157">When an app developer publishes a new version of the app with updated permissions, those permissions are not automatically accepted, even if you've approved the previous permissions.</span></span> <span data-ttu-id="91f63-158">以前のバージョンのアプリを実行しているデバイスでも使用できますが、新しいアクセス許可が承認されるまでアプリはアップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="91f63-158">Devices that run the old version of the app can still use it, but the app is not upgraded until the new permissions are approved.</span></span> <span data-ttu-id="91f63-159">アプリをインストールしていないデバイスでは、アプリの新しくアクセス許可を承認するまでアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="91f63-159">Devices without the app installed cannot install the app until you approve the app's new permissions.</span></span>

### <a name="how-to-update-app-permissions"></a><span data-ttu-id="91f63-160">アプリのアクセス許可を更新する方法</span><span class="sxs-lookup"><span data-stu-id="91f63-160">How to update app permissions</span></span>

<span data-ttu-id="91f63-161">管理対象の Google Play コンソールに定期的にアクセスして、新しいアクセス許可があるかどうか確認してください。</span><span class="sxs-lookup"><span data-stu-id="91f63-161">Periodically visit the managed Google Play console to check for new permissions.</span></span> <span data-ttu-id="91f63-162">承認済みのアプリに新しいアクセス許可が必要な場合は、Google Play を構成して、自分や他のユーザーあてに電子メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="91f63-162">You can configure Google Play to send you or others an e-mail when new permissions are required for an approved app.</span></span> <span data-ttu-id="91f63-163">アプリを割り当ててもデバイスにインストールされていない場合は、まだ許可していないアクセス許可が新しくあるかどうかを、次の手順で確認します。</span><span class="sxs-lookup"><span data-stu-id="91f63-163">If you assign an app and observe it isn't installed on devices, check for new permissions with the following steps:</span></span>

1. <span data-ttu-id="91f63-164">http://play.google.com/work にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="91f63-164">Visit http://play.google.com/work</span></span>
2. <span data-ttu-id="91f63-165">アプリを公開して承認する際に使用した Google アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="91f63-165">Sign in with the Google account you used to publish and approve the apps.</span></span>
3. <span data-ttu-id="91f63-166">**[更新]** タブにアクセスして、更新が必要なアプリがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="91f63-166">Visit the **Updates** tab to see if any apps require an update.</span></span>  <span data-ttu-id="91f63-167">一覧にあるアプリには新しいアクセス許可が必要で、アクセス許可が適用されるまでアプリは割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="91f63-167">Any listed apps require new permissions and do not assign until they are applied.</span></span>  

<span data-ttu-id="91f63-168">あるいは、Google Play を構成することで、アプリごとにアクセス許可を自動的に再許可できます。</span><span class="sxs-lookup"><span data-stu-id="91f63-168">Alternatively, you can configure Google Play to automatically reapprove app permissions on a per app basis.</span></span> 