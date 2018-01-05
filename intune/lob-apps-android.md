---
title: "Android の基幹業務アプリを Intune に追加する方法"
titlesuffix: Azure portal
description: "Android の基幹業務アプリを Intune に追加する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 141d0499f055441ff099a5bec1c4ea695f77326c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-add-android-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="98c75-103">Android の基幹業務 (LOB) アプリを Microsoft Intune に追加する方法</span><span class="sxs-lookup"><span data-stu-id="98c75-103">How to add Android line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="98c75-104">手順 1 - ソフトウェアのセットアップ ファイルを指定する</span><span class="sxs-lookup"><span data-stu-id="98c75-104">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="98c75-105">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="98c75-105">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="98c75-106">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-106">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="98c75-107">**[Intune]** ブレードで、**[アプリの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-107">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="98c75-108">**[モバイル アプリ]** ワークロードで、**[管理]** > **[アプリ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-108">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="98c75-109">アプリの一覧の上にある **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-109">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="98c75-110">**[アプリの追加]** ブレードで、**[基幹業務アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-110">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="98c75-111">手順 2 - アプリのパッケージ ファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="98c75-111">Step 2 - Configure the app package file</span></span>

1. <span data-ttu-id="98c75-112">**[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-112">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="98c75-113">**[アプリのパッケージ** ファイル] ブレードで [参照] ボタンを選択し、拡張子が **.apk** の Android インストール ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-113">On the **App package** file blade, choose the browse button, and select an Android installation file with the extension **.apk**.</span></span>
3. <span data-ttu-id="98c75-114">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-114">When you are finished, choose **OK**.</span></span>


## <a name="step-3---configure-app-information"></a><span data-ttu-id="98c75-115">手順 3 - アプリ情報を構成する</span><span class="sxs-lookup"><span data-stu-id="98c75-115">Step 3 - Configure app information</span></span>

1. <span data-ttu-id="98c75-116">**[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-116">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="98c75-117">**[アプリ情報]** ブレードで、アプリの詳細を追加します。</span><span class="sxs-lookup"><span data-stu-id="98c75-117">On the **App information** blade, add the details for your app.</span></span> <span data-ttu-id="98c75-118">選択したアプリによっては、このブレード内の一部の値が自動的に入力されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="98c75-118">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="98c75-119">**[名前]** - ポータル サイトに表示するアプリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c75-119">**Name** - Enter the name of the app to display in the company portal.</span></span> <span data-ttu-id="98c75-120">使用するアプリ名はすべて一意にします。</span><span class="sxs-lookup"><span data-stu-id="98c75-120">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="98c75-121">同じアプリ名が 2 つ存在する場合、会社のポータルではそのいずれかのみがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="98c75-121">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="98c75-122">**説明** - ポータル サイトでユーザーに表示するアプリの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c75-122">**Description** - Enter the description of the app to be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="98c75-123">**[発行元]** - アプリの発行元の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c75-123">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="98c75-124">**[オペレーティング システムの最小要件]** - アプリをインストールできる最小限のオペレーティング システム バージョンを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-124">**Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed.</span></span> <span data-ttu-id="98c75-125">これよりも前のオペレーティング システムがアプリの割り当て先デバイスにインストールされている場合、そのアプリはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="98c75-125">If you assign the app to a device with an earlier operating system, it will not be installed.</span></span>
    - <span data-ttu-id="98c75-126">**[カテゴリ]** - 1 つまたは複数の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-126">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="98c75-127">この操作を行うと、会社のポータルを閲覧するときに、ユーザーがアプリを探しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="98c75-127">This makes it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="98c75-128">**[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。</span><span class="sxs-lookup"><span data-stu-id="98c75-128">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="98c75-129">**[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c75-129">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="98c75-130">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="98c75-130">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="98c75-131">**[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c75-131">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="98c75-132">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="98c75-132">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="98c75-133">**[開発者]** - 必要に応じて、アプリ開発者の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c75-133">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="98c75-134">**[所有者]** - 必要に応じて、このアプリの所有者の名前 ("**人事部**" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="98c75-134">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="98c75-135">**[メモ]** - このアプリに関連付けるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="98c75-135">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="98c75-136">**[ロゴ]** - アプリに関連付けるアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="98c75-136">**Logo** - Upload an icon that is associated with the app.</span></span> <span data-ttu-id="98c75-137">ユーザーが会社のポータルを参照するとき、アプリにこのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="98c75-137">This is the icon that is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="98c75-138">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98c75-138">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="98c75-139">手順 4. - 完了</span><span class="sxs-lookup"><span data-stu-id="98c75-139">Step 4 - Finish up</span></span>

1. <span data-ttu-id="98c75-140">**[アプリの追加]** ブレードで、アプリの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="98c75-140">On the **Add app** blade, verify your app details.</span></span>
2. <span data-ttu-id="98c75-141">**[追加]** を選択して、アプリを Intune にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="98c75-141">Choose **Add**, to upload the app to Intune.</span></span>

<span data-ttu-id="98c75-142">作成したアプリはアプリの一覧に表示され、選択したグループに割り当てることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="98c75-142">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="98c75-143">詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c75-143">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

## <a name="step-5---update-a-line-of-business-app"></a><span data-ttu-id="98c75-144">手順 5 - 基幹業務アプリの更新</span><span class="sxs-lookup"><span data-stu-id="98c75-144">Step 5 - Update a line-of-business app</span></span>

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]<span data-ttu-id="98c75-145"> 注: Intune サービスで新しい APK ファイルをデバイスへ正常に展開するには、APK パッケージの AndroidManifest.xml ファイルの android:versionCode 文字列をインクリメントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c75-145"> Note: For the Intune service to successfully deploy a new APK file to the device you must increment the android:versionCode string in the AndroidManifest.xml file in your APK package</span></span>

## <a name="next-steps"></a><span data-ttu-id="98c75-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="98c75-146">Next steps</span></span>

<span data-ttu-id="98c75-147">作成したアプリがアプリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="98c75-147">The app you have created is displayed in the apps list.</span></span> <span data-ttu-id="98c75-148">選択したグループにアプリを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="98c75-148">You can now assign it to the groups you choose.</span></span> <span data-ttu-id="98c75-149">詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c75-149">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

<span data-ttu-id="98c75-150">アプリのプロパティと割り当てを監視する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98c75-150">Learn more about the ways in which you can monitor the properties and assignment of your app.</span></span> <span data-ttu-id="98c75-151">詳細については、「[アプリ情報と割り当てを監視する方法](apps-monitor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c75-151">For more information, see [How to monitor app information and assignments](apps-monitor.md).</span></span>

<span data-ttu-id="98c75-152">Intune におけるアプリのコンテキストについて説明します。</span><span class="sxs-lookup"><span data-stu-id="98c75-152">Learn more about the context of your app in Intune.</span></span> <span data-ttu-id="98c75-153">詳細については、「[デバイスとアプリのライフサイクルの概要](introduction-device-app-lifecycles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c75-153">For more information, see [Overview of device and app lifecycles](introduction-device-app-lifecycles.md)</span></span>
