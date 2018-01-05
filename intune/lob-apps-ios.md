---
title: "iOS の基幹業務アプリを Intune に追加する方法"
titlesuffix: Azure portal
description: "iOS の基幹業務アプリを Intune に追加する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0e64ca5481b86a63b51b9f0b664569e86f1bfbc9
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-add-ios-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="f64b4-103">iOS の基幹業務 (LOB) アプリを Microsoft Intune に追加する方法</span><span class="sxs-lookup"><span data-stu-id="f64b4-103">How to add iOS line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="f64b4-104">このトピックの情報を使って、Intune に iOS 基幹業務アプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f64b4-104">Use the information in this topic to help you add iOS line-of-business apps to Intune.</span></span>

>[!NOTE]
><span data-ttu-id="f64b4-105">iOS デバイスのユーザーは Stocks や Maps などの一部の iOS 組み込みアプリを削除できますが、Intune を使ってこれらのアプリを再展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="f64b4-105">While users of iOS devices can remove some of the built-in iOS apps like Stocks, and Maps, you cannot use Intune to redeploy those apps.</span></span> <span data-ttu-id="f64b4-106">エンド ユーザーがこれらのアプリを削除した場合は、アプリ ストアから手動で再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f64b4-106">If end users delete these apps, they must go to the app store, and manually re install them.</span></span>

## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="f64b4-107">手順 1 - ソフトウェアのセットアップ ファイルを指定する</span><span class="sxs-lookup"><span data-stu-id="f64b4-107">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="f64b4-108">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="f64b4-108">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="f64b4-109">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-109">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="f64b4-110">**[Intune]** ブレードで、**[アプリの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-110">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="f64b4-111">**[モバイル アプリ]** ワークロードで、**[管理]** > **[アプリ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-111">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="f64b4-112">アプリの一覧の上にある **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-112">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="f64b4-113">**[アプリの追加]** ブレードで、**[基幹業務アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-113">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="f64b4-114">手順 2 - アプリのパッケージ ファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="f64b4-114">Step 2 - Configure the app package file</span></span>

1. <span data-ttu-id="f64b4-115">**[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-115">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="f64b4-116">**[アプリケーション パッケージ** ファイル] ブレードで、[参照] ボタンを選択し、拡張子 **.ipa** が付いた iOS インストール ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-116">On the **App package** file blade, choose the browse button, and select an iOS installation file with the extension **.ipa**.</span></span>
3. <span data-ttu-id="f64b4-117">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-117">When you are finished, choose **OK**.</span></span>


## <a name="step-3---configure-app-information"></a><span data-ttu-id="f64b4-118">手順 3 - アプリ情報を構成する</span><span class="sxs-lookup"><span data-stu-id="f64b4-118">Step 3 - Configure app information</span></span>

1. <span data-ttu-id="f64b4-119">**[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-119">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="f64b4-120">**[アプリ情報]** ブレードで、アプリの詳細を追加します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-120">On the **App information** blade, add the details for your app.</span></span> <span data-ttu-id="f64b4-121">選択したアプリによっては、このブレード内の一部の値が自動的に入力されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f64b4-121">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="f64b4-122">**[名前]** - ポータル サイトに表示するアプリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-122">**Name** - Enter the name of the app to be displayed in the company portal.</span></span> <span data-ttu-id="f64b4-123">使用するアプリ名はすべて一意にします。</span><span class="sxs-lookup"><span data-stu-id="f64b4-123">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="f64b4-124">同じアプリ名が 2 つ存在する場合、会社のポータルではそのいずれかのみがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64b4-124">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="f64b4-125">**説明** - ポータル サイトでユーザーに表示するアプリの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-125">**Description** - Enter a description for the app to be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="f64b4-126">**[発行元]** - アプリの発行元の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-126">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="f64b4-127">**[オペレーティング システムの最小要件]** - アプリをインストールできる最小限のオペレーティング システム バージョンを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-127">**Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed.</span></span> <span data-ttu-id="f64b4-128">これよりも前のオペレーティング システムがアプリの割り当て先デバイスにインストールされている場合、そのアプリはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="f64b4-128">If you assign the app to a device with an earlier operating system, it will not be installed.</span></span>
    - <span data-ttu-id="f64b4-129">**[カテゴリ]** - 1 つまたは複数の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-129">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="f64b4-130">この操作を行うと、会社のポータルを閲覧するときに、ユーザーがアプリを探しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f64b4-130">This makes it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="f64b4-131">**[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-131">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="f64b4-132">**[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-132">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="f64b4-133">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64b4-133">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="f64b4-134">**[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-134">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="f64b4-135">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64b4-135">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="f64b4-136">**[開発者]** - 必要に応じて、アプリ開発者の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-136">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="f64b4-137">**[所有者]** - 必要に応じて、このアプリの所有者の名前 ("**人事部**" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-137">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="f64b4-138">**[メモ]** - このアプリに関連付けるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-138">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="f64b4-139">**[ロゴ]** - アプリに関連付けるアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f64b4-139">**Logo** - Upload an icon that is associated with the app.</span></span> <span data-ttu-id="f64b4-140">ユーザーが会社のポータルを参照するとき、アプリにこのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64b4-140">This is the icon that is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="f64b4-141">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-141">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="f64b4-142">手順 4. - 完了</span><span class="sxs-lookup"><span data-stu-id="f64b4-142">Step 4 - Finish up</span></span>

1. <span data-ttu-id="f64b4-143">**[アプリの追加]** ブレードで、アプリの詳細が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-143">On the **Add app** blade, verify that the details for your app is correct.</span></span>
2. <span data-ttu-id="f64b4-144">**[追加]** を選択して、アプリを Intune にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f64b4-144">Choose **Add**, to upload the app to Intune.</span></span>

<span data-ttu-id="f64b4-145">作成したアプリはアプリの一覧に表示され、選択したグループに割り当てることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="f64b4-145">The app you have created appears in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="f64b4-146">詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f64b4-146">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

## <a name="step-5---update-a-line-of-business-app"></a><span data-ttu-id="f64b4-147">手順 5 - 基幹業務アプリの更新</span><span class="sxs-lookup"><span data-stu-id="f64b4-147">Step 5 - Update a line-of-business app</span></span>

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]<span data-ttu-id="f64b4-148"> 注: Intune サービスで新しい IPA ファイルをデバイスへ正常に展開するには、IPA パッケージの Info.plist ファイルの CFBundleVersion 文字列をインクリメントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f64b4-148"> Note: For the Intune service to successfully deploy a new IPA file to the device you must increment the CFBundleVersion string in the Info.plist file in your IPA package.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f64b4-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="f64b4-149">Next steps</span></span>

<span data-ttu-id="f64b4-150">作成したアプリがアプリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64b4-150">The app you have created is displayed in the apps list.</span></span> <span data-ttu-id="f64b4-151">選択したグループにアプリを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f64b4-151">You can now assign it to the groups you choose.</span></span> <span data-ttu-id="f64b4-152">詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f64b4-152">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

<span data-ttu-id="f64b4-153">アプリのプロパティと割り当てを監視する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-153">Learn more about the ways in which you can monitor the properties and assignment of your app.</span></span> <span data-ttu-id="f64b4-154">詳細については、「[アプリ情報と割り当てを監視する方法](apps-monitor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f64b4-154">For more information, see [How to monitor app information and assignments](apps-monitor.md).</span></span>

<span data-ttu-id="f64b4-155">Intune におけるアプリのコンテキストについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f64b4-155">Learn more about the context of your app in Intune.</span></span> <span data-ttu-id="f64b4-156">詳細については、「[デバイスとアプリのライフサイクルの概要](introduction-device-app-lifecycles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f64b4-156">For more information, see [Overview of device and app lifecycles](introduction-device-app-lifecycles.md)</span></span>
