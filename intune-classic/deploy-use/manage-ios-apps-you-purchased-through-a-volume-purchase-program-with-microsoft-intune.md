---
title: "ボリューム購入した iOS アプリを管理する"
description: "Intune は、アプリ ストアからライセンス情報をインポートし、使用したライセンスの数を追跡し、所有しているより多くのアプリをインストールできないようにすることで、Apple からボリューム購入したアプリを管理するために使用します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b4a946dd16d03c41c3a07da1dd39781a8ff98f1f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a><span data-ttu-id="f4c53-103">Volume Purchase Program で購入した iOS アプリを Microsoft Intune を使って管理する</span><span class="sxs-lookup"><span data-stu-id="f4c53-103">Manage iOS apps you purchased through a volume-purchase program with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f4c53-104">iOS アプリ ストアでは、社内で実行するアプリの複数のライセンスを購入できます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-104">The iOS app store lets you purchase multiple licenses for an app that you want to run in your company.</span></span> <span data-ttu-id="f4c53-105">これは、購入したアプリの複数コピーを追跡する管理オーバーヘッドを削減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-105">This helps you reduce the administrative overhead of tracking multiple purchased copies of apps.</span></span>

<span data-ttu-id="f4c53-106">Microsoft Intune では、このプログラムを通じて購入したアプリを管理するために、アプリ ストアからライセンス情報をインポートし、使用したライセンスの数を追跡し、所有しているより多くのアプリをインストールできないようにします。</span><span class="sxs-lookup"><span data-stu-id="f4c53-106">Microsoft Intune helps you manage apps that you purchased through this program by importing the license information from the app store, tracking how many of the licenses you have used, and preventing you from installing more copies of the app than you own.</span></span>

> [!Important]
> <span data-ttu-id="f4c53-107">現在、Intune は、iOS Volume Purchase Program for Business (VPP) アプリ ライセンスをユーザーとデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-107">Currently, Intune assigns iOS Volume Purchase Program for Business (VPP) app licenses to users and devices.</span></span> <span data-ttu-id="f4c53-108">そのため、ユーザーは、アプリをインストールするために Apple ID のパスワードを入力することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4c53-108">Because of this, users may have to enter their Apple ID password to install the app.</span></span>

## <a name="manage-volume-purchased-apps-for-ios-devices"></a><span data-ttu-id="f4c53-109">iOS デバイス用のボリューム購入アプリの管理</span><span class="sxs-lookup"><span data-stu-id="f4c53-109">Manage volume-purchased apps for iOS devices</span></span>
<span data-ttu-id="f4c53-110">iOS アプリの複数のライセンスを購入するには、[Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) を利用します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-110">You purchase multiple licenses for iOS apps through the [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/).</span></span> <span data-ttu-id="f4c53-111">このためには、Apple Web サイトから Apple VPP アカウントをセットアップし、Apple VPP トークンの Intune へのアップロードを行います。</span><span class="sxs-lookup"><span data-stu-id="f4c53-111">This involves setting up an Apple VPP account from the Apple website and uploading the Apple VPP token to Intune.</span></span>  <span data-ttu-id="f4c53-112">その後、ボリューム購入情報を Intune と同期し、ボリューム購入アプリの使用を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-112">You can then synchronize your volume purchase information with Intune and track your volume-purchased app use.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="f4c53-113">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="f4c53-113">Before you start</span></span>
<span data-ttu-id="f4c53-114">開始する前に、Apple から VPP トークンを取得し、これを Intune アカウントにアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c53-114">Before you start, you'll need to get a VPP token from Apple and upload this to your Intune account.</span></span> <span data-ttu-id="f4c53-115">さらに、次の点を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c53-115">Additionally, you should understand the following:</span></span>

* <span data-ttu-id="f4c53-116">Intune は最大 256 VPP トークンの追加をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f4c53-116">Intune supports adding up to 256 VPP tokens.</span></span>
* <span data-ttu-id="f4c53-117">以前に異なる製品で VPP トークンを使用していた場合は、Intune で使用するための新しい VPP トークンを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c53-117">If you previously used a VPP token with a different product, you must generate a new one to use with Intune.</span></span>
* <span data-ttu-id="f4c53-118">各トークンは、1 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="f4c53-118">Each token is valid for one year.</span></span>
* <span data-ttu-id="f4c53-119">既定では、Intune は 1 日に 2 回、Apple VPP サービスと同期します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-119">By default, Intune syncs with the Apple VPP service twice a day.</span></span> <span data-ttu-id="f4c53-120">いつでも手動での同期を開始できます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-120">You can start a manual sync at any time.</span></span>
* <span data-ttu-id="f4c53-121">Intune に VPP トークンをインポートした後、同じトークンを他のデバイス管理ソリューションにインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f4c53-121">After you have imported the VPP token to Intune, do not import the same token to any other device management solution.</span></span> <span data-ttu-id="f4c53-122">これを行うと、ライセンスの割り当てとユーザー レコードが失われる恐れがあります。</span><span class="sxs-lookup"><span data-stu-id="f4c53-122">Doing so might result in the loss of license assignment and user records.</span></span>
* <span data-ttu-id="f4c53-123">Intune で iOS VPP の使用を開始する前に、他のモバイル デバイス管理 (MDM) ベンダーで作成された既存の VPP ユーザー アカウントを削除してください。</span><span class="sxs-lookup"><span data-stu-id="f4c53-123">Before you start to use iOS VPP with Intune, remove any existing VPP user accounts created with other mobile device management (MDM) vendors.</span></span> <span data-ttu-id="f4c53-124">Intune は、セキュリティ対策として、そのようなユーザー アカウントを Intune と同期しません。</span><span class="sxs-lookup"><span data-stu-id="f4c53-124">Intune will not synchronize those user accounts into Intune as a security measure.</span></span> <span data-ttu-id="f4c53-125">Intune は、Intune によって作成された Apple VPP サービスからのデータのみを同期します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-125">Intune will only synchronize data from the Apple VPP service that Intune created.</span></span>
* <span data-ttu-id="f4c53-126">デバイスのユーザー アフィニティが構成されている場合、Device Enrollment Protocol (DEP) を使用して登録されたユーザーのデバイスにのみ iOS VPP アプリを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-126">You can only deploy iOS VPP apps to user's devices that were enrolled using the Device Enrollment Protocol (DEP) if user affinity for the device is configured.</span></span>

## <a name="to-get-and-upload-an-apple-vpp-token"></a><span data-ttu-id="f4c53-127">Apple VPP トークンを取得およびアップロードするには</span><span class="sxs-lookup"><span data-stu-id="f4c53-127">To get and upload an Apple VPP token</span></span>

1.  <span data-ttu-id="f4c53-128">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理者]** &gt; **[iOS および Mac OS X]**&gt;**、[Volume Purchase Program]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-128">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **iOS and Mac OS X** &gt;  **Volume Purchase Program**.</span></span>

2.  <span data-ttu-id="f4c53-129">**[Apple VPP アカウント]** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-129">Choose the **Apple VPP Account** link.</span></span> <span data-ttu-id="f4c53-130">サインアップしていない場合は、Volume Purchase Program for Business にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="f4c53-130">If you haven't already, sign up for the Volume Purchase Program for Business.</span></span> <span data-ttu-id="f4c53-131">サインアップした後、アカウントの Apple VPP トークンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f4c53-131">After you sign up, download the Apple VPP token for your account.</span></span>

3.  <span data-ttu-id="f4c53-132">Intune コンソールの **[Apple Volume Purchase Program (VPP) の管理]** ページで、**[VPP トークンのアップロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-132">On the **Manage Apple Volume Purchase Program (VPP)** page of the Intune console, choose **Upload the VPP token**.</span></span>

4.  <span data-ttu-id="f4c53-133">**[VPP トークンのアップロード]** ダイアログ ボックスで、VPP トークンの名前と Apple ID を入力または貼り付けて、**[アップロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-133">In the **Upload the VPP token** dialog box, enter or paste the VPP token name and your Apple ID, and then choose **Upload**.</span></span>

5.  <span data-ttu-id="f4c53-134">警告ダイアログ ボックスで、後で異なる VPP アカウントに変更できないことを理解していることを示すボックスをオンにして、**[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-134">In the warning dialog box, check the box to indicate that you understand that you can't change to a different VPP account later, and then choose **Yes**.</span></span>

<span data-ttu-id="f4c53-135">**[Volume Purchase Program]** ページに、Apple VPP トークンに関する情報として、最終更新時刻や有効期限、Intune との最終同期時刻などが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-135">On the **Volume Purchase Program** page, you can now view information about the Apple VPP token, including when it was last updated, when it will expire, and when it was last synchronized with Intune.</span></span>

<span data-ttu-id="f4c53-136">**[今すぐ同期]** を選択すると、いつでも、Apple が保持しているデータと Intune を同期することができます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-136">You can synchronize the data held by Apple with Intune at any time by choosing **Sync now**.</span></span>

## <a name="to-deploy-a-volume-purchased-app"></a><span data-ttu-id="f4c53-137">ボリューム購入アプリを展開するには</span><span class="sxs-lookup"><span data-stu-id="f4c53-137">To deploy a volume-purchased app</span></span>

1.  <span data-ttu-id="f4c53-138">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[アプリ]** &gt; **[アプリ]** &gt; **[ボリューム購入されたアプリ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-138">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps** &gt; **Volume-Purchased Apps**.</span></span> <span data-ttu-id="f4c53-139">この一覧には、Apple VPP サービスから同期されたアプリがすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-139">This list shows all apps that were synchronized from the Apple VPP service.</span></span>

2.  <span data-ttu-id="f4c53-140">展開するアプリを選択し、**[展開の管理]** を選択して、「[Microsoft Intune でアプリを展開する](deploy-apps-in-microsoft-intune.md)」トピックの手順に従って、アプリのアップロード、作成、展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-140">Choose the app that you want to deploy, choose **Manage Deployment**, and then use the instructions in the [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) topic to finish uploading, creation, and deployment of the app.</span></span>

> [!TIP]
> <span data-ttu-id="f4c53-141">**[必須]** の展開操作を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c53-141">You must choose a deployment action of **Required**.</span></span> <span data-ttu-id="f4c53-142">使用可能なインストールは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f4c53-142">Available installations are not currently supported.</span></span> <span data-ttu-id="f4c53-143">さらに、アプリを展開できるのはユーザー グループに対してだけです。</span><span class="sxs-lookup"><span data-stu-id="f4c53-143">Additionally, you can only deploy the app to user groups.</span></span>

<span data-ttu-id="f4c53-144">アプリを **[必須]** インストールとして展開すると、アプリをインストールする各ユーザーがライセンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-144">When you deploy the app as a **Required** installation, each user who installs the app uses a license.</span></span>

<span data-ttu-id="f4c53-145">ライセンスを再利用するには、展開アクションを **[アンインストール]** に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c53-145">To reclaim a license, you must change the deployment action to **Uninstall**.</span></span> <span data-ttu-id="f4c53-146">アプリをアンインストールすると、ライセンスは回収されます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-146">The license will be reclaimed after the app is uninstalled.</span></span>

<span data-ttu-id="f4c53-147">対象となるデバイスを持つユーザーが初めて VPP アプリをインストールしようとすると、Apple Volume Purchase Program に参加するように求められます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-147">When a user with an eligible device first tries to install a VPP app, they will be asked to join the Apple Volume Purchase program.</span></span> <span data-ttu-id="f4c53-148">アプリのインストールを実行する前に、このプログラムに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c53-148">They must do this before the app installation proceeds.</span></span>

<span data-ttu-id="f4c53-149">それ以上使用できるライセンスがない場合、展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4c53-149">If there are no more licenses available, the deployment will fail.</span></span>

## <a name="to-monitor-apple-vpp-apps"></a><span data-ttu-id="f4c53-150">Apple VPP アプリを監視するには</span><span class="sxs-lookup"><span data-stu-id="f4c53-150">To monitor Apple VPP apps</span></span>
<span data-ttu-id="f4c53-151">**[ボリューム購入されたアプリ]** ノードの **[アプリ]** ワークスペースを使って、展開されている VPP アプリおよび使われているライセンスの数を監視できます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-151">You can monitor which VPP apps have been deployed, and how many licenses are used, from the **Apps** workspace in the **Volume-Purchased Apps** node.</span></span>

> [!TIP]
> <span data-ttu-id="f4c53-152">また、アプリの **[フィルター]** を使って、各アプリのインストールの状態を調べることもできます。</span><span class="sxs-lookup"><span data-stu-id="f4c53-152">You can also use app **Filters** to examine the status of each app installation.</span></span>

### <a name="see-also"></a><span data-ttu-id="f4c53-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4c53-153">See also</span></span>
[<span data-ttu-id="f4c53-154">Microsoft Intune でアプリを展開する</span><span class="sxs-lookup"><span data-stu-id="f4c53-154">Deploy apps in Microsoft Intune</span></span>](deploy-apps-in-microsoft-intune.md)
