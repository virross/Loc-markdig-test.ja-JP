---
title: "アプリ保護ポリシー付きの Android アプリ"
description: "このトピックでは、アプリ保護ポリシーを使用してアプリを管理するときの注意点について説明します。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6239e34a06069d4834603a48dba0e10f8c00774d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a><span data-ttu-id="098d3-103">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="098d3-103">What to expect when your Android app is managed by app protection policies</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="098d3-104">このトピックでは、アプリ保護ポリシーを使用する場合のアプリのユーザー エクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="098d3-104">This topic describes the user experience for apps with app protection policies.</span></span> <span data-ttu-id="098d3-105">アプリ保護ポリシーが適用されるのは、仕事でアプリが使用される場合に限られます。たとえば、職場のアカウントを使用してアプリにアクセスしたり、会社の OneDrive 事業拠点に格納されたファイルにアクセスしたりする場合です。</span><span class="sxs-lookup"><span data-stu-id="098d3-105">App protection policies are applied only when apps are used in a work context: for example, when the user is accessing apps with a work account or accessing files that are stored in a company OneDrive business location.</span></span>
##  <a name="access-apps"></a><span data-ttu-id="098d3-106">アプリにアクセスする</span><span class="sxs-lookup"><span data-stu-id="098d3-106">Access apps</span></span>

<span data-ttu-id="098d3-107">Android デバイス上のアプリ保護ポリシーに関連付けられたすべてのアプリでポータル サイト アプリが必要です。</span><span class="sxs-lookup"><span data-stu-id="098d3-107">The Company Portal app is required for all apps that are associated with app protection policies on Android devices.</span></span>

<span data-ttu-id="098d3-108">Intune に登録されていないデバイスの場合は、ポータル サイト アプリをデバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="098d3-108">For devices that are not enrolled in Intune, the Company Portal app must be installed on the device.</span></span> <span data-ttu-id="098d3-109">ただし、ユーザーはアプリ保護ポリシーによって管理されるアプリが使用できるようになるまで、ポータル サイト アプリの起動またはサインインを行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="098d3-109">However, the user does not have to launch  or sign into the Company Portal app before they can use apps that are managed by app protection policies.</span></span>

<span data-ttu-id="098d3-110">ポータル サイト アプリは、Intune が安全な場所でデータを共有するための手段となります。</span><span class="sxs-lookup"><span data-stu-id="098d3-110">The Company Portal app is a way for Intune to share data in a secure location.</span></span> <span data-ttu-id="098d3-111">そのため、ポータル サイト アプリは、デバイスが Intune に登録されていない場合でも、アプリ保護ポリシーに関連付けられているすべてのアプリの要件となります。</span><span class="sxs-lookup"><span data-stu-id="098d3-111">Therefore, the Company Portal app is a requirement for all apps that are associated with app protection policies, even if the device is not enrolled in Intune.</span></span>


##  <a name="use-apps-with-multi-identity-support"></a><span data-ttu-id="098d3-112">複数の ID に対応しているアプリを使用する</span><span class="sxs-lookup"><span data-stu-id="098d3-112">Use apps with multi-identity support</span></span>

<span data-ttu-id="098d3-113">アプリ保護ポリシーは仕事関連でのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="098d3-113">App protection polices are only applied in the work context.</span></span> <span data-ttu-id="098d3-114">そのため、仕事で使用する場合と個人的に使用する場合でアプリの動作が異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="098d3-114">Therefore, the app might behave differently depending on whether the context is work or personal.</span></span>

<span data-ttu-id="098d3-115">たとえば、ユーザーが職場のデータにアクセスすると、暗証番号 (PIN) を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="098d3-115">For example, the user gets a PIN prompt when accessing work data.</span></span> <span data-ttu-id="098d3-116">**Outlook アプリ**の場合、ユーザーにはアプリの起動時に、暗証番号 (PIN) の入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="098d3-116">For the **Outlook app**, the user is prompted for a PIN when they launch the app.</span></span> <span data-ttu-id="098d3-117">**OneDrive アプリ**の場合、ユーザーが職場のアカウントを入力するとき、PIN の入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="098d3-117">For the **OneDrive app**, the user is prompted for the pin when they type in the work account.</span></span> <span data-ttu-id="098d3-118">Microsoft **Word**、**PowerPoint**、**Excel** の場合、会社の OneDrive for Business 拠点に保存されているドキュメントにユーザーがアクセスするとき、PIN の入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="098d3-118">For Microsoft **Word**, **PowerPoint**, and **Excel**, the user is prompted for the pin when they access documents that are stored in the company OneDrive for Business location.</span></span>

##  <a name="manage-user-accounts-on-the-device"></a><span data-ttu-id="098d3-119">デバイスのユーザー アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="098d3-119">Manage user accounts on the device</span></span>

<span data-ttu-id="098d3-120">Intune では、アプリ保護ポリシーの展開は、デバイスごとに 1 ユーザー アカウントに限られます。</span><span class="sxs-lookup"><span data-stu-id="098d3-120">Intune  supports the deployment of app protection policies to one user account per device only.</span></span>

* <span data-ttu-id="098d3-121">2 つ目のユーザーがデバイスでブロックされるかどうかは、使用中のアプリによって決まります。</span><span class="sxs-lookup"><span data-stu-id="098d3-121">Depending on the app that you're using, the second user might be blocked on the device.</span></span> <span data-ttu-id="098d3-122">ただし、どの場合でも、ポリシーの影響を受けるのは、アプリ保護ポリシーが適用される最初のユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="098d3-122">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>

  * <span data-ttu-id="098d3-123">**Microsoft Word**、**Excel**、**PowerPoint** では、2 つ目のユーザー アカウントがブロックされることはありませんが、2 つ目のユーザー アカウントがアプリ保護ポリシーの影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="098d3-123">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>

  * <span data-ttu-id="098d3-124">**OneDrive アプリ**と **Outlook アプリ**では、職場のアカウントは 1 つだけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="098d3-124">For **OneDrive** and **Outlook apps**, you can only use one work account.</span></span>  <span data-ttu-id="098d3-125">これらのアプリに複数の職場のアカウントを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="098d3-125">You can't add multiple work accounts for these apps.</span></span>  <span data-ttu-id="098d3-126">ただし、デバイス上のユーザーを削除して、別のユーザーを追加することはできます。</span><span class="sxs-lookup"><span data-stu-id="098d3-126">You can however, remove a user and add a different user on the device.</span></span>


* <span data-ttu-id="098d3-127">アプリ保護ポリシーを展開する前にデバイスに複数の既存のユーザー アカウントがある場合は、アプリ保護ポリシーが展開される最初のアカウントが Intune アプリ保護ポリシーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="098d3-127">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies are deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="098d3-128">次のサンプル シナリオを読んで、複数のユーザー アカウントがどのように処理されるかを深く理解してください。</span><span class="sxs-lookup"><span data-stu-id="098d3-128">Read the following example scenario to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="098d3-129">ユーザー A は、**会社 X** と会社 **会社 Y** という 2 つの会社で働いています。ユーザー A は各会社の作業アカウントを持っており、どちらの会社も Intune を使用してアプリ保護ポリシーを展開しています。</span><span class="sxs-lookup"><span data-stu-id="098d3-129">User A works for two companies—**Company X** and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="098d3-130">**会社 X** は、**会社 Y** の**前に**アプリ保護ポリシーを展開しています。アプリ保護ポリシーは、**会社 X** に関連付けられたアプリ保護ポリシーに適用され、会社 Y に関連付けられたアカウントには適用されません。会社 Y に関連付けられたユーザー アカウントをアプリ保護ポリシーで管理する場合は、会社 X に関連付けられたユーザー アカウントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="098d3-130">**Company X** deploys app protection policies **before** **Company Y**. The account that's associated with **Company X** gets the app protection policy, but not the account that's associated with Company Y. If you want the user account that's associated with Company Y to be managed by the app protection policies, you must remove the user account that's associated with Company X.</span></span>
### <a name="add-a-second-account"></a><span data-ttu-id="098d3-131">2 つ目のアカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="098d3-131">Add a second account</span></span>
####  <a name="android"></a><span data-ttu-id="098d3-132">Android</span><span class="sxs-lookup"><span data-stu-id="098d3-132">Android</span></span>
<span data-ttu-id="098d3-133">Android デバイスを使用している場合は、既存のアカウントを削除して新しいアカウントを追加する手順を示すブロック メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="098d3-133">If you are using an Android device, you might see a blocking message with instructions to remove the existing account and add a new one.</span></span>  <span data-ttu-id="098d3-134">既存のアカウントを削除するには、**[設定]、[全般]、[アプリケーション マネージャー]、[会社のポータル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="098d3-134">To remove the existing account, go to **Settings  &gt;General &gt; Application Manager &gt;Company Portal.**</span></span> <span data-ttu-id="098d3-135">**[データのクリア]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="098d3-135">Then choose **Clear Data**.</span></span>

![エラー メッセージとアカウントの削除手順のスクリーンショット](./media/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a><span data-ttu-id="098d3-137">Azure Information Protection アプリでメディア ファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="098d3-137">View media files with the Azure Information Protection app</span></span>
<span data-ttu-id="098d3-138">Android デバイスで会社の AV、PDF、画像ファイルを表示するには、[Azure Information Protection アプリ](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (以前の Rights Management 共有アプリ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="098d3-138">To view company AV, PDF, and image files on Android devices, use the [Azure Information Protection app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (previously known as the Rights Management sharing app).</span></span>

<span data-ttu-id="098d3-139">このアプリは、Google Play ストアからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="098d3-139">Download this app from the Google Play store.</span></span>  

<span data-ttu-id="098d3-140">次のファイルの種類がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="098d3-140">The following file types are supported:</span></span>

* <span data-ttu-id="098d3-141">**音声:** AAC LC、HE-AACv1 (AAC+)、HE-AACv2 (enhanced AAC+)、AAC ELD (enhanced low delay AAC)、AMR-NB、AMR-WB、FLAC、MP3、MIDI、Ogg Vorbis、PCM/WAVE</span><span class="sxs-lookup"><span data-stu-id="098d3-141">**Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE</span></span>
* <span data-ttu-id="098d3-142">**ビデオ:** H.263、H.264 AVC、MPEG-4 SP、VP8</span><span class="sxs-lookup"><span data-stu-id="098d3-142">**Video:** H.263, H.264 AVC, MPEG-4 SP, VP8</span></span>
* <span data-ttu-id="098d3-143">**画像:** .jpg、.pjpg、.png、.ppng、.bmp、.pbmp、.gif、.pgif、.jpeg、.pjpeg</span><span class="sxs-lookup"><span data-stu-id="098d3-143">**Image:** .jpg, .pjpg, .png, .ppng, .bmp, .pbmp, .gif, .pgif, .jpeg, .pjpeg</span></span>
* <span data-ttu-id="098d3-144">**ドキュメント:** PDF、PPDF</span><span class="sxs-lookup"><span data-stu-id="098d3-144">**Documents:** PDF, PPDF</span></span>


|<span data-ttu-id="098d3-145">**pfile**</span><span class="sxs-lookup"><span data-stu-id="098d3-145">**pfile**</span></span>|<span data-ttu-id="098d3-146">**テキスト**</span><span class="sxs-lookup"><span data-stu-id="098d3-146">**text**</span></span>|
|----|----|
|<span data-ttu-id="098d3-147">pfile は、保護するファイル向けの汎用的な "ラッパー" 形式です。暗号化されたコンテンツと Azure Information Protection ライセンスをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="098d3-147">Pfile is a generic “wrapper” format for protected files that encapsulates the encrypted content and the Azure Information Protection licenses.</span></span> <span data-ttu-id="098d3-148">任意のファイルの種類を保護できます。</span><span class="sxs-lookup"><span data-stu-id="098d3-148">It can be used to protect any file type.</span></span>|<span data-ttu-id="098d3-149">XML、CSV などのテキスト ファイルは、保護されているときでもアプリで開いて表示できます。</span><span class="sxs-lookup"><span data-stu-id="098d3-149">Text files, including XML, CSV, and so on, can be opened for viewing in the app even when they are protected.</span></span> <span data-ttu-id="098d3-150">ファイルの種類: .txt、.ptxt、.csv、.pcsv、.log、.plog、.xml、.pxml。</span><span class="sxs-lookup"><span data-stu-id="098d3-150">File types: .txt, .ptxt, .csv, .pcsv, .log, .plog, .xml, .pxml.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="098d3-151">次のステップ</span><span class="sxs-lookup"><span data-stu-id="098d3-151">Next steps</span></span>
[<span data-ttu-id="098d3-152">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="098d3-152">What to expect when your iOS app is managed by app protection policies</span></span>](end-user-mam-apps-ios.md)
