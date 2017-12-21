---
title: "アプリを Microsoft Intune に追加する方法"
titlesuffix: Azure portal
description: "この手順では、Intune にアプリを追加して、ユーザーとデバイスに割り当てられる状態にします。 \""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 108f789f16304498cf54387326d112353bf70aa2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a><span data-ttu-id="4e5f8-104">アプリを Microsoft Intune に追加する方法</span><span class="sxs-lookup"><span data-stu-id="4e5f8-104">How to add an app to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="4e5f8-105">ユーザー用アプリを管理して割り当てるには、そのアプリを Intune に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-105">Before you can manage and assign apps for your users, you must add them to Intune.</span></span> <span data-ttu-id="4e5f8-106">Intune ではさまざまな種類のアプリがサポートされ、オプションは種類ごとに異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-106">Intune supports a wide range of different app types, and the options might be different for each type.</span></span>

<span data-ttu-id="4e5f8-107">Intune では、以下の種類のアプリを追加して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-107">Intune lets you add and assign these app types:</span></span>

![Intune でサポートされているアプリの種類](./media/app-types.png)

<span data-ttu-id="4e5f8-109">次のプラットフォームがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-109">The following platforms are supported.</span></span>

- <span data-ttu-id="4e5f8-110">Android ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-110">Android store apps</span></span>
- <span data-ttu-id="4e5f8-111">Android 基幹業務 (LOB) アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-111">Android line-of-business (LOB) apps</span></span>
- <span data-ttu-id="4e5f8-112">iOS ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-112">iOS store apps</span></span>
- <span data-ttu-id="4e5f8-113">iOS 基幹業務 (LOB) アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-113">iOS line-of-business (LOB) apps</span></span>
- <span data-ttu-id="4e5f8-114">Web アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-114">Web apps</span></span>
- <span data-ttu-id="4e5f8-115">Windows Phone 8.1 ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-115">Windows Phone 8.1 store apps</span></span>
- <span data-ttu-id="4e5f8-116">Windows Phone 基幹業務アプリ (.xap ファイル)</span><span class="sxs-lookup"><span data-stu-id="4e5f8-116">Windows Phone line-of-business apps (.xap files)</span></span>
- <span data-ttu-id="4e5f8-117">Windows ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-117">Windows store apps</span></span>
- <span data-ttu-id="4e5f8-118">Windows 基幹業務アプリ (.msi ファイルのみ)</span><span class="sxs-lookup"><span data-stu-id="4e5f8-118">Windows line-of-business apps (.msi files only)</span></span>

>[!TIP]
> <span data-ttu-id="4e5f8-119">基幹業務 (LOB) アプリは、アプリ ストアからではなく、アプリのインストール ファイルからインストールするアプリです。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-119">A line-of-business (or LOB) app is one that you do not install from an app store, but install from the app installation file.</span></span> <span data-ttu-id="4e5f8-120">たとえば、iOS LOB アプリをインストールするには、アプリケーションのアーカイブ ファイル (拡張子 .ipa) を追加します。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-120">For example, to install an iOS LOB app, you add the application archive file (with the extension .ipa).</span></span> <span data-ttu-id="4e5f8-121">これらは通常、社内で作成したアプリです。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-121">These are typically apps you have written in-house.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="4e5f8-122">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="4e5f8-122">Before you start</span></span>

<span data-ttu-id="4e5f8-123">アプリの追加と割り当てを始める前に、次の点を検討してください。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-123">Consider the following points before you begin to add and assign apps.</span></span>

- <span data-ttu-id="4e5f8-124">ストアからアプリを追加して割り当てる場合、エンド ユーザーがそのアプリをインストールするには、そのストアのアカウントをエンド ユーザーが用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-124">When you add and assign an app from a store, end users must have an account with that store in order to be able to install the app.</span></span>
- <span data-ttu-id="4e5f8-125">割り当てるアプリまたは項目は、組み込みの iOS アプリに依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-125">Some apps or items you assign might be dependent on built-in iOS apps.</span></span> <span data-ttu-id="4e5f8-126">たとえば、iOS ストアからブックを割り当てる場合は、デバイス上に iBooks アプリが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-126">For example, if you assign a book from the iOS store, then the iBooks app must be present on the device.</span></span> <span data-ttu-id="4e5f8-127">iBooks の組み込みアプリを削除した場合は、Intune を使用してそれを元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-127">If you have removed the iBooks built-in app, you cannot use Intune to reinstate it.</span></span>

## <a name="cloud-storage-space"></a><span data-ttu-id="4e5f8-128">クラウドの記憶域の容量</span><span class="sxs-lookup"><span data-stu-id="4e5f8-128">Cloud storage space</span></span>
<span data-ttu-id="4e5f8-129">ソフトウェア インストーラーのインストールの種類を使用して作成したすべてのアプリ (たとえば、基幹業務アプリ) は、パッケージ化され、Intune クラウドの記憶域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-129">All apps that you create by using the software installer installation type (for example, a line-of-business app) are packaged and uploaded to Intune cloud storage.</span></span> <span data-ttu-id="4e5f8-130">Intune の試用版サブスクリプションでは、管理対象のアプリと更新プログラムの保管用として、2 ギガバイト (GB) 分のクラウドの記憶域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-130">A trial subscription of Intune includes 2 gigabytes (GB) of cloud-based storage that is used to store managed apps and updates.</span></span> <span data-ttu-id="4e5f8-131">完全版のサブスクリプションには、20 GB の記憶領域が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-131">A full subscription includes 20 GB of storage space.</span></span>

<span data-ttu-id="4e5f8-132">Intune の追加ストレージは、当初の購入方法を使用して購入できます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-132">You can purchase additional storage for Intune using your original purchase method.</span></span>  <span data-ttu-id="4e5f8-133">請求書やクレジット カードでお支払いの場合は、[サブスクリプション管理ポータル](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-133">If you paid by invoice or credit card, visit the [Subscription Management portal](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).</span></span>  <span data-ttu-id="4e5f8-134">それ以外の場合は、パートナーまたは営業担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-134">Otherwise, contact your partner or sales associate.</span></span>

<span data-ttu-id="4e5f8-135">クラウドの記憶域の容量の要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-135">Requirements for cloud storage space are as follows:</span></span>

-   <span data-ttu-id="4e5f8-136">すべてのアプリのインストール ファイルは、同じフォルダーにある必要がある。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-136">All app installation files must be in the same folder.</span></span>
-   <span data-ttu-id="4e5f8-137">アップロードするファイルの最大ファイルサイズは 2 GB。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-137">The maximum file size for any file that you upload is 2 GB.</span></span>

## <a name="how-to-create-and-edit-categories-for-apps"></a><span data-ttu-id="4e5f8-138">アプリのカテゴリを作成して編集する方法</span><span class="sxs-lookup"><span data-stu-id="4e5f8-138">How to create and edit categories for apps</span></span>

<span data-ttu-id="4e5f8-139">ユーザーがポータル サイトでアプリを見つけやすいように、そのアプリをカテゴリを使って並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-139">App categories can be used to help you sort apps to make them easier for users to find in the company portal.</span></span> <span data-ttu-id="4e5f8-140">アプリには、**デベロッパー アプリ**、**通信アプリ**など、1 つ以上のカテゴリを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-140">You can assign one or more categories to an app, for example, **Developer apps**, or **Communication apps**.</span></span>
<span data-ttu-id="4e5f8-141">アプリを Intune に追加するときに、必要なカテゴリを選択するためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-141">When you add an app to Intune, you are given the option to select the category you want.</span></span> <span data-ttu-id="4e5f8-142">プラットフォーム固有のトピックを使用してアプリを追加し、カテゴリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-142">Use the platform-specific topics to add an app, and assign categories.</span></span> <span data-ttu-id="4e5f8-143">独自のカテゴリを作成して編集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-143">To create and edit your own categories, use the following procedure:</span></span>

1. <span data-ttu-id="4e5f8-144">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-144">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="4e5f8-145">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-145">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="4e5f8-146">**[Intune]** ブレードで、**[モバイル アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-146">On the **Intune** blade, choose **Mobile apps**.</span></span>
4. <span data-ttu-id="4e5f8-147">**[モバイル アプリ]** ワークロードで、**[セットアップ]** > **[アプリのカテゴリ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-147">In the **Mobile apps** workload, choose **Setup** > **App categories**.</span></span>
5. <span data-ttu-id="4e5f8-148">**[アプリのカテゴリ]** ブレードで、現在のカテゴリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-148">On the **App categories** blade, a list of the current categories is shown.</span></span> <span data-ttu-id="4e5f8-149">次の操作のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-149">Choose one of the following actions:</span></span>
    - <span data-ttu-id="4e5f8-150">**[カテゴリの作成]** - **[Create category (カテゴリの作成)]** ブレードで、新しいカテゴリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-150">**Create a category** - On the **Create category** blade, enter a name for the new category.</span></span> <span data-ttu-id="4e5f8-151">名前を入力できる言語は 1 つのみです。Intune では翻訳されません。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-151">Names can be entered in one language only, and are not translated by Intune.</span></span> <span data-ttu-id="4e5f8-152">完了したら **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-152">When you are done, click **Create**.</span></span>
    - <span data-ttu-id="4e5f8-153">**[カテゴリの編集]** - 一覧の任意のカテゴリについては、"**...**" を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-153">**Edit a category** - For any category in the list, choose '**...**'.</span></span> <span data-ttu-id="4e5f8-154">**[プロパティ]** ブレードで、カテゴリの新しい名前を入力するか、カテゴリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-154">On the **Properties** blade, you can enter a new name for the category, or delete the category.</span></span>


## <a name="apps-added-automatically-by-intune"></a><span data-ttu-id="4e5f8-155">Intune によって自動的に追加されるアプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-155">Apps added automatically by Intune</span></span>

<span data-ttu-id="4e5f8-156">以前は、Intune に簡単に割り当てができる組み込みのアプリが多数含まれていました。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-156">Previously, Intune contained a number of built-in apps that you could quickly assign.</span></span> <span data-ttu-id="4e5f8-157">お客様からのフィードバックに基づき、この一覧を削除しました。組み込みのアプリは今後表示されません。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-157">Based on your feedback, we have removed this list, and you will no longer see built-in apps.</span></span>
<span data-ttu-id="4e5f8-158">ただし、組み込みのすべてのアプリが既に割り当てられている場合、そのアプリはアプリの一覧に引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-158">However, if you have already assigned any built-in apps, these will still be visible in the list of apps.</span></span> <span data-ttu-id="4e5f8-159">これらのアプリの割り当ては必要に応じて続行することができます。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-159">You can continue to assign these apps as required.</span></span>
<span data-ttu-id="4e5f8-160">今後のリリースでは、Azure Portal から組み込みのアプリをより簡単に選択して割り当てる方法を追加する予定です。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-160">In a later release, we plan to add an easier method to select and assign built-in apps from the Azure portal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e5f8-161">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-161">Next steps</span></span>

<span data-ttu-id="4e5f8-162">次のトピックのいずれかを選択して、各プラットフォーム用のアプリを Intune に追加する方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4e5f8-162">Choose one of the following topics to find out how to add apps for each platform to Intune:</span></span>

- [<span data-ttu-id="4e5f8-163">Android ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-163">Android store apps</span></span>](store-apps-android.md)
- [<span data-ttu-id="4e5f8-164">Android LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-164">Android LOB apps</span></span>](lob-apps-android.md)
- [<span data-ttu-id="4e5f8-165">iOS ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-165">iOS store apps</span></span>](store-apps-ios.md)
- [<span data-ttu-id="4e5f8-166">iOS LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-166">iOS LOB apps</span></span>](lob-apps-ios.md)
- [<span data-ttu-id="4e5f8-167">Web アプリ (すべてのプラットフォーム)</span><span class="sxs-lookup"><span data-stu-id="4e5f8-167">Web apps (for all platforms)</span></span>](web-app.md)
- [<span data-ttu-id="4e5f8-168">Windows Phone 8.1 ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-168">Windows Phone 8.1 store apps</span></span>](store-apps-windows-phone-8-1.md)
- [<span data-ttu-id="4e5f8-169">Windows Phone LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-169">Windows Phone LOB apps</span></span>](lob-apps-windows-phone.md)
- [<span data-ttu-id="4e5f8-170">Windows ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-170">Windows store apps</span></span>](store-apps-windows.md)
- [<span data-ttu-id="4e5f8-171">Windows LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-171">Windows LOB app</span></span>](lob-apps-windows.md)
- [<span data-ttu-id="4e5f8-172">Windows 10 用の Office 365 アプリ</span><span class="sxs-lookup"><span data-stu-id="4e5f8-172">Office 365 apps for Windows 10</span></span>](apps-add-office365.md)

