---
title: "iOS ストア アプリを Intune に追加する方法 | Microsoft Docs"
titlesuffix: Azure portal
description: "iOS ストア アプリを Intune に追加する方法について説明します。\""
keywords: Intune
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4c5d18f217659c9be59c116670fbf92a6d1b2ab4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a><span data-ttu-id="f2742-104">iOS ストア アプリを Microsoft Intune に追加する方法</span><span class="sxs-lookup"><span data-stu-id="f2742-104">How to add iOS store apps to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<span data-ttu-id="f2742-105">このトピックの情報を使って、Intune に iOS ストア アプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f2742-105">Use the information in this topic to help you add iOS store apps to Intune.</span></span>

>[!NOTE]
><span data-ttu-id="f2742-106">iOS デバイスのユーザーは Stocks や Maps などの一部の iOS 組み込みアプリを削除できますが、Intune を使ってこれらのアプリを再展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2742-106">While users of iOS devices can remove some of the built-in iOS apps like Stocks, and Maps, you cannot use Intune to redeploy those apps.</span></span> <span data-ttu-id="f2742-107">エンド ユーザーがこれらのアプリを削除した場合は、アプリ ストアから手動で再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2742-107">If end users delete these apps, they must go to the app store, and manually re install them.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="f2742-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="f2742-108">Before you start</span></span>

<span data-ttu-id="f2742-109">アプリ ストアで無料になっている場合にのみ、この方法でアプリを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f2742-109">You can only assign apps using this method if they are free of charge in the app store.</span></span> <span data-ttu-id="f2742-110">Intune を利用し、有料のアプリを割り当てる場合、[iOS ボリューム購入プログラム](vpp-apps-ios.md)の利用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="f2742-110">If you want to assign paid apps using Intune, consider using the [iOS volume-purchase program](vpp-apps-ios.md).</span></span>


## <a name="step-1---search-for-the-app-in-the-store"></a><span data-ttu-id="f2742-111">手順 1 - ストアでアプリを検索する</span><span class="sxs-lookup"><span data-stu-id="f2742-111">Step 1 - Search for the app in the store</span></span>

1. <span data-ttu-id="f2742-112">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="f2742-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="f2742-113">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="f2742-114">**[Intune]** ブレードで、**[アプリの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-114">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="f2742-115">**[モバイル アプリ]** ワークロードで、**[管理]** > [アプリ] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-115">In the **Mobile apps** workload, choose **Manage** > Apps.</span></span>
5. <span data-ttu-id="f2742-116">アプリの一覧の上にある **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-116">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="f2742-117">**[アプリの追加]** ブレードで、**[アプリ ストアを検索します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-117">In the **Add App** blade, choose **Search the App Store**.</span></span>
7. <span data-ttu-id="f2742-118">**[Apple App Store]** ブレードで、アプリ ストアの国のロケールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-118">In the **Apple App Store** blade, select the App store country locale.</span></span>
8. <span data-ttu-id="f2742-119">検索ボックスに名前 (または名前の一部) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-119">Type the name (or part of the name) in the search box.</span></span> <span data-ttu-id="f2742-120">Intune がストアを検索し、関連する結果の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="f2742-120">Intune searches the store and return a list of relevant results.</span></span>
9. <span data-ttu-id="f2742-121">一覧から目的のアプリを選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2742-121">From the list, choose the app you want, then click **OK**.</span></span>

## <a name="step-2---configure-app-information"></a><span data-ttu-id="f2742-122">手順 2 - アプリ情報を構成する</span><span class="sxs-lookup"><span data-stu-id="f2742-122">Step 2 - Configure app information</span></span>

1. <span data-ttu-id="f2742-123">**[アプリの追加]** ブレードで、**[アプリ情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-123">In the **Add App** blade, choose **App Information**.</span></span>
2. <span data-ttu-id="f2742-124">**[アプリの編集]** ブレードで、アプリの情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="f2742-124">In the **Edit App** blade, configure the app information.</span></span> <span data-ttu-id="f2742-125">構成が終わったら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2742-125">Once you are done, click **Add**.</span></span> <span data-ttu-id="f2742-126">選択したアプリによっては、このブレード内の一部の値が自動的に入力されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2742-126">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
- <span data-ttu-id="f2742-127">**名前** -- ポータル サイトに表示するアプリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-127">**Name** -- Type the name of the app for display in the company portal.</span></span> <span data-ttu-id="f2742-128">使用するアプリ名はすべて一意にします。</span><span class="sxs-lookup"><span data-stu-id="f2742-128">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="f2742-129">同じアプリ名が 2 つ存在する場合、ポータル サイトではそのいずれかのみがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2742-129">If the same app name exists twice, the company portal displays only one of the apps to users.</span></span>
- <span data-ttu-id="f2742-130">**説明** -- ポータル サイトでユーザーに表示するアプリの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-130">**Description** -- Type a description for the app to displayed to users in the company portal.</span></span>
- <span data-ttu-id="f2742-131">**発行元** -- アプリの発行元の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-131">**Publisher** -- Type the name of the publisher of the app.</span></span>
- <span data-ttu-id="f2742-132">**アプリ ストアの URL** -- 作成するアプリのアプリ ストア URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-132">**Appstore URL** -- Type the app store URL of the app you want to create.</span></span>
- <span data-ttu-id="f2742-133">**Store country/region (ストアの国/地域)** -- アプリ ストアの国のロケールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-133">**Store country/region** -- Select the App store country locale.</span></span>
- <span data-ttu-id="f2742-134">**オペレーティング システムの最小要件** -- リストから、アプリをインストールできる最小限のオペレーティング システム バージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-134">**Minimum operating system** -- From the list, choose the minimum operating system version on which the app can be installed.</span></span> <span data-ttu-id="f2742-135">これよりも前のオペレーティング システムのデバイスには、アプリはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="f2742-135">The app will not be installed on a device with an earlier operating system.</span></span>
- <span data-ttu-id="f2742-136">**適用可能なデバイスの種類** -- リストから、アプリで使用されているデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-136">**Applicable device type** -- From the list, choose the devices that are used by the App.</span></span>
- <span data-ttu-id="f2742-137">**カテゴリ** (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="f2742-137">**Category** (optional).</span></span> <span data-ttu-id="f2742-138">1 つ以上の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-138">Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="f2742-139">カテゴリを使用すれば、ユーザーはポータル サイトを参照する際にアプリを見つけやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f2742-139">Categories make it easier for users to find the app when they browse the company portal.</span></span>
- <span data-ttu-id="f2742-140">**会社のポータルでおすすめアプリとして表示します** -- ユーザーがアプリを参照する際に、ポータル サイトのメイン ページでアプリを目立つように表示します。</span><span class="sxs-lookup"><span data-stu-id="f2742-140">**Display this as a featured app in the Company Portal** -- Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
- <span data-ttu-id="f2742-141">**情報 URL** -- 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-141">**Information URL** -- Optionally, type the URL of a website that contains information about this app.</span></span> <span data-ttu-id="f2742-142">この URL はポータル サイトでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2742-142">The URL displays to users in the company portal.</span></span>
- <span data-ttu-id="f2742-143">**プライバシー URL** -- 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-143">**Privacy URL** -- Optionally, type the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="f2742-144">この URL はポータル サイトでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2742-144">The URL displays to users in the company portal.</span></span>
- <span data-ttu-id="f2742-145">**開発者** -- 必要に応じて、アプリ開発者の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-145">**Developer** -- Optionally, type the name of the app developer.</span></span> <span data-ttu-id="f2742-146">このフィールドは管理者にのみ表示され、エンド ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="f2742-146">This field is only visible an administrator and will not be visible to end-users.</span></span>
- <span data-ttu-id="f2742-147">**所有者** -- 必要に応じて、このアプリの所有者の名前 (**人事部**など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-147">**Owner** -- Optionally, type a name for the owner of this app, for example, **HR department**.</span></span>  <span data-ttu-id="f2742-148">このフィールドは管理者にのみ表示され、エンド ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="f2742-148">This field is only visible an administrator and will not be visible to end-users.</span></span>
- <span data-ttu-id="f2742-149">**メモ** -- このアプリに関連付けるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="f2742-149">**Notes** -- Type any notes you would like to associate with this app.</span></span> <span data-ttu-id="f2742-150">このフィールドは管理者にのみ表示され、エンド ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="f2742-150">This field is only visible an administrator and will not be visible to end-users.</span></span>
- <span data-ttu-id="f2742-151">**ロゴ** -- アプリに関連付けるアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f2742-151">**Logo** -- Upload an icon that is associated with the app.</span></span> <span data-ttu-id="f2742-152">ユーザーが会社のポータルを参照するとき、アプリにアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2742-152">The icon is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="f2742-153">完了したら、**[アプリの追加]** ブレードで、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2742-153">When you are done, on the **Add App** blade, choose **OK**.</span></span>

<span data-ttu-id="f2742-154">作成したアプリはアプリの一覧に表示され、選択したグループに割り当てることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="f2742-154">The app you have created displays in the apps list, where you can assign it to the groups you choose.</span></span> <span data-ttu-id="f2742-155">詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2742-155">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>
