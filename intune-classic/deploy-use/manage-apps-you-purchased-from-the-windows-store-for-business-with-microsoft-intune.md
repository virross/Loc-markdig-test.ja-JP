---
title: "ビジネス向け Microsoft ストア アプリの管理"
description: "Intune コンソールからボリューム購入したアプリを管理および展開する場合に、Microsoft Intune をビジネス向け Microsoft ストアに接続する"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d176ab55225bd5ba2cb89a533f6b82b862f3a3c4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a><span data-ttu-id="b97c9-103">ビジネス向け Microsoft ストアから購入したアプリを Microsoft Intune で管理する</span><span class="sxs-lookup"><span data-stu-id="b97c9-103">Manage apps you purchased from the Microsoft Store for Business with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b97c9-104">[ビジネス向け Microsoft ストア](https://www.microsoft.com/business-store)では、組織用のアプリを見つけて、個別または大量に購入することができます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-104">The [Microsoft Store for Business](https://www.microsoft.com/business-store) gives you a place to find and purchase apps for your organization, individually, or in volume.</span></span> <span data-ttu-id="b97c9-105">Microsoft Intune にストアを接続することで、Intune コンソールから大量購入アプリを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-105">By connecting the store to Microsoft Intune, you can manage volume-purchased apps from the Intune console.</span></span> <span data-ttu-id="b97c9-106">たとえば、</span><span class="sxs-lookup"><span data-stu-id="b97c9-106">For example:</span></span>
* <span data-ttu-id="b97c9-107">ストアから購入したアプリの一覧を Intune に同期することができます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-107">You can synchronize the list of apps you have purchased from the store with Intune.</span></span>
* <span data-ttu-id="b97c9-108">同期されているアプリは Intune 管理コンソールに表示され、他のアプリと同様に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-108">Apps that are synchronized appear in the Intune administration console, and you can deploy these like any other apps.</span></span>
* <span data-ttu-id="b97c9-109">使用可能なライセンス数、および Intune 管理コンソールで使用中のライセンス数を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-109">You can track how many licenses are available, and how many are being used in the Intune administration console.</span></span>
* <span data-ttu-id="b97c9-110">使用可能なライセンス数が不足している場合、Intune はアプリの展開とインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="b97c9-110">Intune blocks deployment and installation of apps if there are an insufficient number of licenses available.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="b97c9-111">開始する前に</span><span class="sxs-lookup"><span data-stu-id="b97c9-111">Before you start</span></span>
<span data-ttu-id="b97c9-112">ビジネス向け Microsoft ストアからアプリを同期して展開する前に、以下のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b97c9-112">Review the following information before you start syncing and deploying apps from the Microsoft Store for Business:</span></span>
* <span data-ttu-id="b97c9-113">組織のモバイル デバイス管理機関として Intune を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97c9-113">You must configure Intune as the mobile device management authority for your organization.</span></span> <span data-ttu-id="b97c9-114">詳細については、「[Intune でデバイスを登録するための前提条件](prerequisites-for-enrollment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97c9-114">For more information, see [Prerequisites for enrolling devices in Microsoft Intune](prerequisites-for-enrollment.md).</span></span>
* <span data-ttu-id="b97c9-115">ビジネス向け Microsoft ストアのアカウントにサインアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97c9-115">You must have signed up for an account on the Microsoft Store for Business.</span></span>
* <span data-ttu-id="b97c9-116">Intune に Windows ビジネス ストア アカウントを関連付けた後で別のアカウントに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b97c9-116">Once you have associated a Windows Business Store account with Intune, you cannot change to a different account in the future.</span></span>
* <span data-ttu-id="b97c9-117">Intune に対して、ストアから購入したアプリを手動で追加したり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b97c9-117">Apps purchased from the store cannot be manually added to or deleted from Intune.</span></span> <span data-ttu-id="b97c9-118">ビジネス向け Microsoft ストアとの同期のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="b97c9-118">They can only be synchronized with the Microsoft Store for Business.</span></span>
* <span data-ttu-id="b97c9-119">Intune は、ビジネス向け Microsoft ストアから購入したオンライン ライセンスされたアプリのみを同期します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-119">Intune synchronizes only online licensed apps you have purchased from the Microsoft Store for Business.</span></span>
* <span data-ttu-id="b97c9-120">この機能を使用するには、デバイスが Active Directory Domain Services またはワークプレースに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97c9-120">Devices must be joined to Active Directory Domain Services, or workplace-joined, to use this capability.</span></span>
* <span data-ttu-id="b97c9-121">登録デバイスは、1511 リリースの Windows 10 を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97c9-121">Enrolled devices must be using the 1511 release of Windows 10.</span></span>

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a><span data-ttu-id="b97c9-122">Intune にビジネス向け Microsoft ストア アカウントを関連付ける</span><span class="sxs-lookup"><span data-stu-id="b97c9-122">Associate your Microsoft Store for Business account with Intune</span></span>
<span data-ttu-id="b97c9-123">Intune コンソールで同期を有効にする前に、以下の手順に従って、Intune を管理ツールとして使用するようにストア アカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97c9-123">Before you enable synchronization in the Intune console, you must configure your store account to use Intune as a management tool:</span></span>
1. <span data-ttu-id="b97c9-124">Intune へのサインインに使用したものと同じテナント アカウントを使用して、ビジネス ストアにサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-124">Ensure that you sign into the Business Store using the same tenant account you use to sign into Intune.</span></span>
2. <span data-ttu-id="b97c9-125">ビジネス ストアで、**[設定]** > **[管理ツール]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-125">In the Business Store, choose **Settings** > **Management tools**.</span></span>
3. <span data-ttu-id="b97c9-126">[管理ツール] ページで、**[管理ツールの追加]** を選択し、**[Microsoft Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-126">On the Management tools page, choose **Add a management tool**, and choose **Microsoft Intune**.</span></span>

> [!NOTE]
> <span data-ttu-id="b97c9-127">ビジネス向け Microsoft ストアのアプリを展開するために複数の管理ツールを使用する場合、これまでは、ビジネス向け Microsoft ストアにはそのうちの 1 つしか関連付けることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="b97c9-127">If you are using more than one management tool to deploy Microsoft Store for Business apps, previously, you could only associate one of these with the Microsoft Store for Business.</span></span> <span data-ttu-id="b97c9-128">これからは、複数のツール (Intune や Configuration Manager など) をストアに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-128">You can now associate multiple management tools with the store, for example, Intune and Configuration Manager.</span></span>

<span data-ttu-id="b97c9-129">これで、作業を続行し、Intune コンソールで同期を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-129">You can now continue, and set up synchronization in the Intune console.</span></span>

## <a name="configure-synchronization"></a><span data-ttu-id="b97c9-130">同期を構成する</span><span class="sxs-lookup"><span data-stu-id="b97c9-130">Configure synchronization</span></span>

1. <span data-ttu-id="b97c9-131">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-131">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.</span></span>
2. <span data-ttu-id="b97c9-132">**[管理]** ワークスペースで、**[モバイル デバイス管理]** > **[Windows]** の順に展開し、**[ビジネス向けストア]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-132">In the **Administration** workspace, expand **Mobile Device Management** > **Windows**, and then choose **Store for Business**.</span></span>
3. <span data-ttu-id="b97c9-133">**[ビジネス向け Microsoft ストア]** ページで、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b97c9-133">On the **Microsoft Store for Business** page, do the following:</span></span>
 * <span data-ttu-id="b97c9-134">ビジネス向け Microsoft ストアにまだサインアップしていない場合は、サインアップ用のリンクをクリックしてサインアップを行います。</span><span class="sxs-lookup"><span data-stu-id="b97c9-134">If you haven't already done so, click the link to sign-up for the Microsoft Store for Business.</span></span>
 * <span data-ttu-id="b97c9-135">サインアップしたら、**[同期の構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-135">Once you are signed-up, choose **Configure Sync**.</span></span>
4. <span data-ttu-id="b97c9-136">**[ビジネス向け Microsoft ストア アプリの同期の構成]** ダイアログ ボックスで、**[ビジネス向け Microsoft ストアの同期を有効にする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-136">In the **Configure Microsoft Store for Business app sync** dialog box, select **Enable Microsoft Store for Business sync**.</span></span>
5. <span data-ttu-id="b97c9-137">**[言語]** ドロップダウン リストで、Intune コンソールで表示するビジネス向け Microsoft ストアのアプリに使用する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-137">From the **Language** drop-down list, choose the language in which apps from the Microsoft Store for Business will be displayed in the Intune console.</span></span> <span data-ttu-id="b97c9-138">アプリは、どの言語を使用して表示するかに関係なく、使用可能なエンド ユーザーの言語でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-138">Regardless of the language in which they are displayed, they will be installed in the end user's language when available.</span></span>
6. <span data-ttu-id="b97c9-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b97c9-139">Click **OK**.</span></span>

## <a name="synchronize-apps"></a><span data-ttu-id="b97c9-140">アプリを同期する</span><span class="sxs-lookup"><span data-stu-id="b97c9-140">Synchronize apps</span></span>

1. <span data-ttu-id="b97c9-141">**[ビジネス向け Microsoft ストア]** ページで、**[今すぐ同期]** を選択し、ストアから購入したアプリと Intune を同期します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-141">On the **Microsoft Store for Business** page, choose **Sync now** to synchronize the apps you've purchased from the store with Intune.</span></span>
2. <span data-ttu-id="b97c9-142">**[アプリ]** ワークスペースで、**[アプリ]** > **[ボリューム購入アプリ]** の順に選択し、展開可能なアプリを表示して、購入したアプリが正しくインポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-142">In the **Apps** workspace, choose **Apps** > **Volume-Purchased Apps** to view the apps you can deploy, and to verify that your purchased apps were imported correctly.</span></span> <span data-ttu-id="b97c9-143">このノードのアプリは、所有しているライセンスの合計数と、使用可能なライセンスの数と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-143">The apps in this node are displayed with the total number of licenses you own, and the number of licenses you have available.</span></span>
<span data-ttu-id="b97c9-144">たとえば、ビジネス向け Microsoft ストアから会社のポータル アプリ (オンライン ライセンス) を購入し、Intune コンソールに同期してから、それを必要な Windows 10 デバイスに必要なアプリとして展開できます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-144">For example, you can purchase the Company Portal app (online licensed) from the Microsoft Store for Business, sync it to the Intune console and then deploy this as a required app in to the required Windows 10 devices.</span></span> 


## <a name="deploy-apps"></a><span data-ttu-id="b97c9-145">アプリの展開</span><span class="sxs-lookup"><span data-stu-id="b97c9-145">Deploy apps</span></span>

<span data-ttu-id="b97c9-146">他の Intune アプリを展開する場合と同じように、ストアからアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="b97c9-146">You deploy apps from the store in the same way you deploy any other Intune app.</span></span> <span data-ttu-id="b97c9-147">詳細については、「[Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md)」 (Microsoft Intune でアプリを展開する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97c9-147">For more information, see [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span>
<span data-ttu-id="b97c9-148">ビジネス向け Microsoft ストア アプリを展開すると、アプリをインストールする各ユーザーによってライセンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-148">When you deploy a Microsoft Store for Business app, a license is used by each user who installs the app.</span></span> <span data-ttu-id="b97c9-149">展開されたアプリに対して使用可能なライセンスをすべて使用すると、それ以上コピーを展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="b97c9-149">If you use all of the available licenses for a deployed app, you will not be able to deploy any more copies.</span></span> <span data-ttu-id="b97c9-150">以下のいずれかの操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97c9-150">You must take one of the following actions:</span></span>
* <span data-ttu-id="b97c9-151">一部のデバイスからアプリをアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="b97c9-151">Uninstall the app from some devices.</span></span>
* <span data-ttu-id="b97c9-152">現在の展開の範囲を絞り、十分なライセンスがあるユーザーのみを対象にする。</span><span class="sxs-lookup"><span data-stu-id="b97c9-152">Reduce the scope of the current deployment to target only the users you have sufficient licenses for.</span></span>
* <span data-ttu-id="b97c9-153">ビジネス向け Microsoft ストアからアプリのコピーをさらに購入する。</span><span class="sxs-lookup"><span data-stu-id="b97c9-153">Buy more copies of the app from the Microsoft Store for Business.</span></span>

> [!Important]
> <span data-ttu-id="b97c9-154">展開されたアプリは、最初にデバイスを登録したユーザーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="b97c9-154">Deployed apps are only available to the user who originally enrolled the device.</span></span> <span data-ttu-id="b97c9-155">他のユーザーは、そのアプリにアクセスすることができません。</span><span class="sxs-lookup"><span data-stu-id="b97c9-155">No other users can access the app.</span></span>


### <a name="see-also"></a><span data-ttu-id="b97c9-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="b97c9-156">See also</span></span>
[<span data-ttu-id="b97c9-157">Microsoft Intune でモバイル デバイスのアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="b97c9-157">Add apps for mobile devices in Microsoft Intune</span></span>](add-apps-for-mobile-devices-in-microsoft-intune.md)
