---
title: "ボリューム購入した iOS 電子ブックの管理"
titlesuffix: Azure portal
description: "iOS ストアからボリューム購入したブックを Intune に同期し、その使用状況を管理および追跡する方法について説明します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1c819364266c2bf3f0cf088508da735d0e7696ff
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-manage-ios-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a><span data-ttu-id="0bdd3-103">Volume Purchase Program で購入した iOS 電子ブックを Microsoft Intune で管理する方法</span><span class="sxs-lookup"><span data-stu-id="0bdd3-103">How to manage iOS eBooks you purchased through a volume-purchase program with Microsoft Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="0bdd3-104">Apple Volume Purchase Program (VPP) では、社内のユーザーに配布するブックの複数ライセンスを購入できます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-104">The Apple Volume Purchase Program (VPP) lets you purchase multiple licenses for a book that you want to distribute to users in your company.</span></span> <span data-ttu-id="0bdd3-105">ブックは Business Store または Education Store から配布できます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-105">You can distribute books from the Business, or Education stores.</span></span>

<span data-ttu-id="0bdd3-106">Microsoft Intune では、このプログラムを通して購入したブックを同期および管理し、割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-106">Microsoft Intune helps you synchronize, manage, and assign books that you purchased through this program.</span></span> <span data-ttu-id="0bdd3-107">ストアからライセンス情報をインポートし、使用したライセンスの数を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-107">You can import license information from the store and track how many of the licenses you have used.</span></span>

<span data-ttu-id="0bdd3-108">ブックを管理する手順は、[VPP アプリを管理する](vpp-apps-ios.md)手順とほぼ同様です。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-108">The procedures to manage books are similar to [managing VPP apps](vpp-apps-ios.md).</span></span>

## <a name="manage-volume-purchased-books-for-ios-devices"></a><span data-ttu-id="0bdd3-109">iOS デバイス用のボリューム購入ブックの管理</span><span class="sxs-lookup"><span data-stu-id="0bdd3-109">Manage volume-purchased books for iOS devices</span></span>
<span data-ttu-id="0bdd3-110">iOS ブックの複数のライセンスを購入するには、[ビジネス向け Apple Volume Purchase Program](http://www.apple.com/business/vpp/) または [教育向け Apple Volume Purchase Program](http://volume.itunes.apple.com/us/store) を利用します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-110">You buy multiple licenses for iOS books through the [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) or the [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store).</span></span> <span data-ttu-id="0bdd3-111">このためには、Apple Web サイトから Apple VPP アカウントをセットアップし、Apple VPP トークンを Intune にアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-111">This process involves setting up an Apple VPP account from the Apple website and uploading the Apple VPP token to Intune.</span></span>  <span data-ttu-id="0bdd3-112">その後、ボリューム購入情報を Intune に同期し、ボリューム購入ブックの使用状況を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-112">You can then synchronize your volume purchase information with Intune and track your volume-purchased book use.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="0bdd3-113">開始する前に</span><span class="sxs-lookup"><span data-stu-id="0bdd3-113">Before you start</span></span>
<span data-ttu-id="0bdd3-114">開始する前に、Apple から VPP トークンを取得し、これを Intune アカウントにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-114">Before you start, get a VPP token from Apple and upload it to your Intune account.</span></span> <span data-ttu-id="0bdd3-115">補足:</span><span class="sxs-lookup"><span data-stu-id="0bdd3-115">Additionally:</span></span>

* <span data-ttu-id="0bdd3-116">Intune アカウントに関連付けられる VPP トークンは、最大 256 個です。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-116">You can associate up to 256 VPP tokens with your Intune account.</span></span>
* <span data-ttu-id="0bdd3-117">以前に異なる製品で VPP トークンを使用していた場合は、Intune で使用するための新しい VPP トークンを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-117">If you previously used a VPP token with a different product, you must generate a new one to use with Intune.</span></span>
* <span data-ttu-id="0bdd3-118">各トークンは、1 年間有効です。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-118">Each token is valid for one year.</span></span>
* <span data-ttu-id="0bdd3-119">既定では、Intune は 1 日に 2 回、Apple VPP サービスと同期します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-119">By default, Intune syncs with the Apple VPP service twice a day.</span></span> <span data-ttu-id="0bdd3-120">いつでも手動での同期を開始できます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-120">You can start a manual sync at any time.</span></span>
* <span data-ttu-id="0bdd3-121">Intune に VPP トークンをインポートした後、同じトークンを他のデバイス管理ソリューションにインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-121">After you have imported the VPP token to Intune, do not import the same token to any other device management solution.</span></span> <span data-ttu-id="0bdd3-122">これを行うと、ライセンスの割り当てとユーザー レコードが失われる恐れがあります。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-122">Doing so might result in the loss of license assignment and user records.</span></span>
* <span data-ttu-id="0bdd3-123">Intune で iOS ブックの使用を開始する前に、他のモバイル デバイス管理 (MDM) ベンダーで作成された既存の VPP ユーザー アカウントを削除してください。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-123">Before you start to use iOS books with Intune, remove any existing VPP user accounts created with other mobile device management (MDM) vendors.</span></span> <span data-ttu-id="0bdd3-124">Intune では、セキュリティ対策として、そのようなユーザー アカウントは Intune と同期されません。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-124">Intune does not synchronize those user accounts into Intune as a security measure.</span></span> <span data-ttu-id="0bdd3-125">Intune では、Intune で作成された Apple VPP サービスからのデータのみが同期されます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-125">Intune synchronizes only data from the Apple VPP service that Intune created.</span></span>
* <span data-ttu-id="0bdd3-126">デバイスに本を割り当てる場合、そのデバイスには、組み込みの iBooks アプリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-126">When you assign a book to a device, that device must have the built-in iBooks app installed.</span></span> <span data-ttu-id="0bdd3-127">そうでない場合は、エンド ユーザーがブックを読むには、アプリを再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-127">If it is not, the end user must reinstall the app before they can read the book.</span></span> <span data-ttu-id="0bdd3-128">現時点では、Intune を使用して、削除された組み込みのアプリを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-128">You cannot currently use Intune to restore removed built-in apps.</span></span>
* <span data-ttu-id="0bdd3-129">Apple Volume Purchase Program サイトから実行できるのは、ブックの割り当てのみです。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-129">You can only assign books from the Apple Volume Purchase Program site.</span></span> <span data-ttu-id="0bdd3-130">社内で作成したブックをアップロードしてから割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-130">You cannot upload, then assign books you created in-house.</span></span>
* <span data-ttu-id="0bdd3-131">現時点では、アプリと同じようにブックをエンド ユーザー カテゴリに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-131">You cannot currently assign books to end-user categories in the same way as you do apps.</span></span>
* <span data-ttu-id="0bdd3-132">一度ブックを割り当てると、その後ライセンスを再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-132">You cannot reclaim a license once the book is assigned.</span></span>
* <span data-ttu-id="0bdd3-133">対象となるデバイスを持つユーザーが初めて VPP ブックをインストールしようとすると、ブックをインストールする前に Apple Volume Purchase Program に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-133">When a user with an eligible device first tries to install a VPP book, they must join the Apple Volume Purchase program before they can install a book.</span></span> <span data-ttu-id="0bdd3-134">管理対象の Apple ID を使用して、セキュリティ グループにライセンスを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-134">You can also assign licenses to security groups with managed Apple IDs.</span></span> <span data-ttu-id="0bdd3-135">このようにする場合、ユーザーはブックをインストールする際に Apple ID を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-135">If you do this, then users are not prompted for their Apple ID when a book is installed.</span></span>

## <a name="to-get-and-upload-an-apple-vpp-token"></a><span data-ttu-id="0bdd3-136">Apple VPP トークンを取得およびアップロードするには</span><span class="sxs-lookup"><span data-stu-id="0bdd3-136">To get and upload an Apple VPP token</span></span>

1. <span data-ttu-id="0bdd3-137">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-137">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="0bdd3-138">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-138">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="0bdd3-139">**[Intune]** ブレードで、**[モバイル アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-139">On the **Intune** blade, choose **Mobile apps**.</span></span>
1.  <span data-ttu-id="0bdd3-140">**[Mobile Apps]** ワークロードで、**[セットアップ]** > **[iOS VPP トークン]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-140">In the **Mobile Apps** workload, choose **Setup** > **iOS VPP Tokens**.</span></span>
2.  <span data-ttu-id="0bdd3-141">VPP トークンの一覧ブレードで、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-141">On the list of VPP tokens blade, click **Add**.</span></span>
3.  <span data-ttu-id="0bdd3-142">**[新しい VPP トークン]** ブレードで、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-142">On the **New VPP Token** blade, specify the following information:</span></span>
    - <span data-ttu-id="0bdd3-143">**[VPP トークン ファイル]** - Volume Purchase Program for Business または Volume Purchase Program for Education にサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-143">**VPP token file** - Ensure you have signed for the Volume Purchase Program for Business or the Volume Purchase Program for Education.</span></span> <span data-ttu-id="0bdd3-144">次に、アカウントの Apple VPP トークンをダウンロードし、ここでそのトークンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-144">Then, download the Apple VPP token for your account and select it here.</span></span>
    - <span data-ttu-id="0bdd3-145">**[Apple ID]** - Volume Purchase Program に関連付けられているアカウントの Apple ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-145">**Apple ID** - Enter the Apple ID of the account associated with the volume-purchase program.</span></span>
    - <span data-ttu-id="0bdd3-146">**[VPP アカウントの種類]** - **[ビジネス]** または **[教育]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-146">**Type of VPP account** - Choose from **Business** or **Education**.</span></span>
4. <span data-ttu-id="0bdd3-147">終了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-147">When you are done, click **Upload**.</span></span>

<span data-ttu-id="0bdd3-148">トークンがトークンの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-148">The token is displayed in the list of tokens blade.</span></span>


<span data-ttu-id="0bdd3-149">**[今すぐ同期]** を選択すると、いつでも、Apple が保持しているデータと Intune を同期することができます。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-149">You can synchronize the data held by Apple with Intune at any time by choosing **Sync now**.</span></span>

## <a name="to-assign-a-volume-purchased-app"></a><span data-ttu-id="0bdd3-150">ボリューム購入アプリを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="0bdd3-150">To assign a volume-purchased app</span></span>

1. <span data-ttu-id="0bdd3-151">**[電子ブック]** ワークロードで、**[管理]** > **[すべての電子ブック]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-151">In the **eBooks** workload, choose **Manage** > **All eBooks**.</span></span>
2. <span data-ttu-id="0bdd3-152">ブックの一覧ブレードで、割り当てるブックを選択し、**[...]**、**[グループの割り当て]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-152">On the list of books blade, choose the book you want to assign, and then choose '**...**' > **Assign Groups**.</span></span>
3. <span data-ttu-id="0bdd3-153">**[<*ブック名*> - 割り当てられたグループ]** ブレードで、**[管理]** > **[割り当てられたグループ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-153">On the <*book name*> - **Groups Assigned** blade, choose **Manage** > **Groups Assigned**.</span></span>
4. <span data-ttu-id="0bdd3-154">**[グループの割り当て]** を選択し、**[グループの選択]** ブレードで、ブックを割り当てる Azure AD ユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-154">Choose **Assign Groups** then, on the **Select groups** blade, choose the Azure AD user groups to which you want to assign the book.</span></span> <span data-ttu-id="0bdd3-155">現時点では、デバイス グループはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-155">Device groups are currently not supported.</span></span>
<span data-ttu-id="0bdd3-156">割り当て操作として **[利用可能]** または **[必須]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-156">Choose an assignment action of **Available**, or **Required**.</span></span> 
5. <span data-ttu-id="0bdd3-157">完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-157">Once you are done, choose **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0bdd3-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="0bdd3-158">Next steps</span></span>

<span data-ttu-id="0bdd3-159">ブックの割り当てを監視するのに役立つ情報については、[アプリを監視する方法](apps-monitor.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bdd3-159">See [How to monitor apps](apps-monitor.md) for information to help you monitor book assignments.</span></span>






