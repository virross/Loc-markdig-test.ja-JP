---
title: "アプリ保護ポリシー付きの Android アプリ"
titlesuffix: Azure portal
description: "このトピックでは、アプリ保護ポリシーを使用して Android アプリを管理するときの注意点について説明します。\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d269f4200560c3d903b9da3d92c021ffb03a78e8
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a><span data-ttu-id="6505c-103">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="6505c-103">What to expect when your Android app is managed by app protection policies</span></span> 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="6505c-104">このトピックでは、アプリ保護ポリシーを使用する場合のアプリのユーザー エクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6505c-104">This topic describes the user experience for apps with app protection policies.</span></span> <span data-ttu-id="6505c-105">アプリ保護ポリシーが適用されるのは、作業アカウントを使用してアプリにアクセスしたり、会社の OneDrive 事業拠点に格納されたファイルにアクセスしたりするなどのワーク コンテキストでアプリが使用される場合に限定されます。</span><span class="sxs-lookup"><span data-stu-id="6505c-105">App protection polices are applied only when apps are used in the work context: like accessing apps using your work account, or accessing files stored in your company OneDrive business location.</span></span>
##  <a name="accessing-apps"></a><span data-ttu-id="6505c-106">アプリへのアクセス</span><span class="sxs-lookup"><span data-stu-id="6505c-106">Accessing apps</span></span>

<span data-ttu-id="6505c-107">Android デバイス上のアプリ保護ポリシーに関連付けられたすべてのアプリでポータル サイト アプリが必要です。</span><span class="sxs-lookup"><span data-stu-id="6505c-107">The Company Portal app is required for all apps associated with app protection policies on Android devices.</span></span>

<span data-ttu-id="6505c-108">Intune に登録されていないデバイスの場合は、ポータル サイト アプリをデバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6505c-108">For devices not enrolled in Intune, the Company Portal app must be installed on the device.</span></span> <span data-ttu-id="6505c-109">ただし、ユーザーはアプリ保護ポリシーによって管理されるアプリが使用できるようになるまで、ポータル サイト アプリの起動またはサインインを行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6505c-109">However, user does not have to launch  or sign into the Company Portal app before they can use apps managed by app protection policies.</span></span>
<span data-ttu-id="6505c-110">ポータル サイト アプリは、セキュリティで保護された場所にあるデータを Intune で共有するための手段となります。したがって、このアプリは、デバイスが Intune に登録されていない場合でも必要です。</span><span class="sxs-lookup"><span data-stu-id="6505c-110">The Company Portal app is a way for Intune to share data in a secure location, hence this is a requirement even if the device is not enrolled in Intune.</span></span>


##  <a name="using-apps-with-multi-identity-support"></a><span data-ttu-id="6505c-111">複数の ID を使用するアプリのサポート</span><span class="sxs-lookup"><span data-stu-id="6505c-111">Using apps with multi-identity support</span></span>

<span data-ttu-id="6505c-112">アプリ保護ポリシーはアプリがワーク コンテキストで使用されている場合にのみ適用されます。そのため、ワーク コンテキストとパーソナル コンテキストでは、アプリの動作に違いが見られることがあります。</span><span class="sxs-lookup"><span data-stu-id="6505c-112">App protection polices are only applied in the work context when using the app, so you may see different app behaviors depending on the context: work or personal.</span></span>

<span data-ttu-id="6505c-113">複数の ID をサポートするアプリに対しては、Intune は、エンドユーザーがアプリをワーク コンテキストで使用している場合にのみアプリ保護ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6505c-113">For apps that support multi-identity, Intune only applies the app protection policies when the end-user is using the app in the work context.</span></span>  <span data-ttu-id="6505c-114">たとえば、エンドユーザーが職場のデータにアクセスすると、暗証番号 (PIN) を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6505c-114">For example, the end-user will get a PIN prompt when accessing work data.</span></span>  <span data-ttu-id="6505c-115">**Outlook アプリ** の場合、エンドユーザーにはアプリの起動時に、暗証番号 (PIN) の入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6505c-115">For the **Outlook app**, the end-user is prompted for a PIN on launching the app.</span></span> <span data-ttu-id="6505c-116">**OneDrive アプリ** の場合は、エンドユーザーが作業アカウントを入力すると、同様のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6505c-116">For the **OneDrive app**, this happens when the end-user types in the work account.</span></span>  <span data-ttu-id="6505c-117">Microsoft **Word**、**PowerPoint*、**Excel** の場合は、エンドユーザーが会社の OneDrive for Business 拠点に保存されたドキュメントにアクセスすると、同様のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6505c-117">For Microsoft **Word**, **PowerPoint*, and **Excel**, this happens when the end-user accesses documents stored in the company OneDrive for Business location.</span></span>
##  <a name="managing-user-accounts-on-the-device"></a><span data-ttu-id="6505c-118">デバイスのユーザー アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="6505c-118">Managing user accounts on the device</span></span>

<span data-ttu-id="6505c-119">Intune では、アプリ保護ポリシーをデバイスごとに 1 つのユーザー アカウントのみに展開することがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6505c-119">Intune only supports deploying app protection policies to only one user account per device.</span></span>

* <span data-ttu-id="6505c-120">2 つ目のユーザーがデバイスでブロックされるかどうかは、使用中のアプリによって決まります。</span><span class="sxs-lookup"><span data-stu-id="6505c-120">Depending on the app that you are using, the second user may or may not be blocked on the device.</span></span> <span data-ttu-id="6505c-121">ただし、どの場合でも、ポリシーの影響を受けるのは、アプリ保護ポリシーが適用される最初のユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="6505c-121">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>

  * <span data-ttu-id="6505c-122">**Microsoft Word**、**Excel**、**PowerPoint** では、2 つ目のユーザー アカウントがブロックされることはありませんが、2 つ目のユーザー アカウントがアプリ保護ポリシーの影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="6505c-122">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>

  * <span data-ttu-id="6505c-123">**OneDrive アプリと Outlook アプリ**では、作業アカウントは 1 つだけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6505c-123">For **OneDrive and Outlook apps**, you can only use one work account.</span></span>  <span data-ttu-id="6505c-124">作業アカウントを複数追加しようとしても、これらのアプリでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6505c-124">Adding multiple work accounts are blocked on these apps.</span></span>  <span data-ttu-id="6505c-125">ただし、デバイス上のユーザーを削除して、別のユーザーを追加することはできます。</span><span class="sxs-lookup"><span data-stu-id="6505c-125">You can however, remove a user and add a different user on the device.</span></span>


* <span data-ttu-id="6505c-126">アプリ保護ポリシーを展開する前にデバイスに複数の既存のユーザー アカウントがある場合は、アプリ保護ポリシーが展開される最初のアカウントが Intune アプリ保護ポリシーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="6505c-126">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies is deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="6505c-127">次のサンプル シナリオを読んで、複数のユーザー アカウントがどのように処理されるかを深く理解してください。</span><span class="sxs-lookup"><span data-stu-id="6505c-127">Read the example scenario below to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="6505c-128">ユーザー A は、**会社 X** と会社 **会社 Y** という 2 つの会社で働いています。ユーザー A は各会社の作業アカウントを持っており、どちらの会社も Intune を使用してアプリ保護ポリシーを展開しています。</span><span class="sxs-lookup"><span data-stu-id="6505c-128">User A works for two companies - **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="6505c-129">**会社 X** は、**会社 Y** の**前に**アプリ保護ポリシーを展開しています。アプリ保護ポリシーは、**会社 X** に関連付けられたアカウントに適用され、会社 Y に関連付けられたアカウントには適用されません。会社 Y に関連付けられたユーザー アカウントをアプリ保護ポリシーで管理する場合は、会社 X に関連付けられたユーザー アカウントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6505c-129">**Company X** deploys app protection policies **before** **Company Y**. The account associated with **Company X** will get the app protection policy, but not the account associated with Company Y. If you want the user account associated with Company Y to be managed by the app protection policies, you must remove the user account associated with Company X.</span></span>
### <a name="adding-a-second-account"></a><span data-ttu-id="6505c-130">2 つ目のアカウントの追加</span><span class="sxs-lookup"><span data-stu-id="6505c-130">Adding a second account</span></span>
####  <a name="android"></a><span data-ttu-id="6505c-131">Android</span><span class="sxs-lookup"><span data-stu-id="6505c-131">Android</span></span>
<span data-ttu-id="6505c-132">Android デバイスを使用している場合は、既存のアカウントを削除して新しいアカウントを追加する手順を示すブロック メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6505c-132">If you are using an Android device, you may see a blocking message with instructions to remove the existing account and add a new one.</span></span>  <span data-ttu-id="6505c-133">既存のアカウントを削除するには、**[設定] &gt; [全般] &gt; [アプリケーション マネージャー] &gt; [会社のポータル] の順に選択し、[データのクリア] を選びます**。</span><span class="sxs-lookup"><span data-stu-id="6505c-133">To remove the existing account, go to **Settings  &gt;General &gt; Application Manager &gt;Company Portal and select "Clear Data"**.</span></span>

![エラー メッセージとアカウントの削除手順のスクリーンショット](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a><span data-ttu-id="6505c-135">Azure Information Protection アプリ (旧称: Rights Management 共有アプリ) でメディア ファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="6505c-135">Viewing media files with the Azure Information Protection app (previously known as Rights Management sharing app)</span></span>
<span data-ttu-id="6505c-136">Android デバイスで会社の AV、PDF、および画像ファイルを表示するには、[Azure Information Protection アプリ](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer)を使用します。</span><span class="sxs-lookup"><span data-stu-id="6505c-136">To view company AV, PDF, and image files on Android devices, use the [Azure Information Protection app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).</span></span>

<span data-ttu-id="6505c-137">このアプリは、Google Play ストアからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6505c-137">Download this app from the  Google Play store.</span></span>  

<span data-ttu-id="6505c-138">次のファイルの種類がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6505c-138">The following filetypes are supported:</span></span>

* <span data-ttu-id="6505c-139">**音声:** AAC LC、HE-AACv1 (AAC+)、HE-AACv2 (enhanced AAC+)、AAC ELD (enhanced low delay AAC)、AMR-NB、AMR-WB、FLAC、MP3、MIDI、Ogg Vorbis、PCM/WAVE。</span><span class="sxs-lookup"><span data-stu-id="6505c-139">**Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.</span></span>
* <span data-ttu-id="6505c-140">**ビデオ:** H.263、H.264 AVC、MPEG-4 SP、VP8。</span><span class="sxs-lookup"><span data-stu-id="6505c-140">**Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.</span></span>
* <span data-ttu-id="6505c-141">**画像:** jpg、pjpg、png、ppng、bmp、pbmp、gif、pgif、jpeg、pjpeg。</span><span class="sxs-lookup"><span data-stu-id="6505c-141">**Image:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.</span></span>
* <span data-ttu-id="6505c-142">**ドキュメント:** PDF、PPDF</span><span class="sxs-lookup"><span data-stu-id="6505c-142">**Documents:** PDF, PPDF</span></span>

------------

|<span data-ttu-id="6505c-143">**pfile**</span><span class="sxs-lookup"><span data-stu-id="6505c-143">**pfile**</span></span>|<span data-ttu-id="6505c-144">**テキスト**</span><span class="sxs-lookup"><span data-stu-id="6505c-144">**text**</span></span>|
|----|----|
|<span data-ttu-id="6505c-145">pfile は、保護するファイル向けの汎用的な "ラッパー" 形式です。暗号化されたコンテンツと Azure Information Protection ライセンスをカプセル化し、任意のファイルの種類を保護できます。</span><span class="sxs-lookup"><span data-stu-id="6505c-145">Pfile is a generic “wrapper” format for protected files that encapsulates the encrypted content and the Azure Information Protection licenses and can be used to protect any file type.</span></span>|<span data-ttu-id="6505c-146">XML、CSV などのテキスト ファイルは、保護されているときでもアプリで開いて表示できます。</span><span class="sxs-lookup"><span data-stu-id="6505c-146">Text files, including XML, CSV, etc. can be opened for viewing in the app even when they are protected.</span></span> <span data-ttu-id="6505c-147">ファイルの種類: txt、ptxt、csv、pcsv、log、plog、xml、pxml。</span><span class="sxs-lookup"><span data-stu-id="6505c-147">File types: txt, ptxt, csv, pcsv, log, plog, xml, pxml.</span></span>|

---------------
## <a name="next-steps"></a><span data-ttu-id="6505c-148">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6505c-148">Next steps</span></span>
[<span data-ttu-id="6505c-149">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="6505c-149">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a><span data-ttu-id="6505c-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="6505c-150">See also</span></span>
[<span data-ttu-id="6505c-151">Microsoft Intune でのアプリ保護ポリシーの作成と展開</span><span class="sxs-lookup"><span data-stu-id="6505c-151">Create and deploy app protection policies with Microsoft Intune</span></span>](app-protection-policies.md)
