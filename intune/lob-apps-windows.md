---
title: "Windows の基幹業務アプリを Intune に追加する方法"
titlesuffix: Azure portal
description: "Windows の基幹業務アプリを Intune に追加する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41cdebfc3cd9072519df8e538617bdb29609d4e1
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="d04db-103">Windows の基幹業務 (LOB) アプリを Microsoft Intune に追加する方法</span><span class="sxs-lookup"><span data-stu-id="d04db-103">How to add Windows line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="d04db-104">手順 1 - ソフトウェアのセットアップ ファイルを指定する</span><span class="sxs-lookup"><span data-stu-id="d04db-104">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="d04db-105">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="d04db-105">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="d04db-106">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-106">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="d04db-107">**[Intune]** ブレードで、**[アプリの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-107">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="d04db-108">**[モバイル アプリ]** ワークロードで、**[管理]** > **[アプリ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-108">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="d04db-109">アプリの一覧の上にある **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-109">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="d04db-110">**[アプリの追加]** ブレードで、**[基幹業務アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-110">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="d04db-111">手順 2 - アプリのパッケージ ファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="d04db-111">Step 2 - Configure the app package file</span></span>

1. <span data-ttu-id="d04db-112">**[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-112">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="d04db-113">**[アプリのパッケージ ファイル]** ブレードで、参照ボタンを選択し、拡張子 **.msi**、**.appx**、または **.appxbundle** が付いた Windows インストール ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-113">On the **App package** file blade, choose the browse button, and select a Windows installation file with the extension **.msi**, **.appx**, or **.appxbundle**.</span></span>
3. <span data-ttu-id="d04db-114">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-114">When you are finished, choose **OK**.</span></span>


## <a name="step-3---configure-app-information"></a><span data-ttu-id="d04db-115">手順 3 - アプリ情報を構成する</span><span class="sxs-lookup"><span data-stu-id="d04db-115">Step 3 - Configure app information</span></span>

1. <span data-ttu-id="d04db-116">**[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-116">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="d04db-117">**[アプリ情報]** ブレードで、次の情報を構成します (このブレードの値の一部は、自動的に入力されている場合があります)。</span><span class="sxs-lookup"><span data-stu-id="d04db-117">On the **App information** blade, configure the following information (some of the values in this blade might be automatically filled-in):</span></span>
    - <span data-ttu-id="d04db-118">**[名前]** - アプリの名前を入力します。この名前は会社のポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d04db-118">**Name** - Enter the name of the app as it is displayed in the company portal.</span></span> <span data-ttu-id="d04db-119">使用するアプリ名はすべて一意にします。</span><span class="sxs-lookup"><span data-stu-id="d04db-119">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="d04db-120">同じアプリ名が 2 つ存在する場合、会社のポータルではそのいずれかのみがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d04db-120">If the same app name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="d04db-121">**説明** - アプリの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="d04db-121">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="d04db-122">説明はポータル サイトでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d04db-122">The description is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="d04db-123">**[発行元]** - アプリの発行元の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d04db-123">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="d04db-124">**[カテゴリ]** - 1 つまたは複数の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-124">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="d04db-125">アプリをカテゴリに分けると、会社のポータルを閲覧するとき、ユーザーにとってアプリを探すのが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d04db-125">Categorizing apps makes it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="d04db-126">**[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。</span><span class="sxs-lookup"><span data-stu-id="d04db-126">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="d04db-127">**[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d04db-127">**Information URL** - Optionally, enter the URL of a website that contains information about the app.</span></span> <span data-ttu-id="d04db-128">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d04db-128">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="d04db-129">**[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="d04db-129">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for the app.</span></span> <span data-ttu-id="d04db-130">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d04db-130">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="d04db-131">**[コマンド ライン引数]** - 必要に応じて、実行時に .msi ファイルに適用するコマンド ライン引数を入力します (**/q** など)。</span><span class="sxs-lookup"><span data-stu-id="d04db-131">**Command-line arguments** - Optionally, enter any command-line arguments that you want to apply to the .msi file when it runs, like **/q**.</span></span>
    - <span data-ttu-id="d04db-132">**[開発者]** - 必要に応じて、アプリ開発者の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d04db-132">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="d04db-133">**[所有者]** - 必要に応じて、このアプリの所有者の名前 ("**人事部**" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d04db-133">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="d04db-134">**[メモ]** - このアプリに関連付けるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="d04db-134">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="d04db-135">**[ロゴ]** - アプリに関連付けるアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d04db-135">**Logo** - Upload an icon that is associated with the app.</span></span> <span data-ttu-id="d04db-136">ユーザーが会社のポータルを参照するとき、アプリにアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d04db-136">The icon is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="d04db-137">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d04db-137">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="d04db-138">手順 4. - 完了</span><span class="sxs-lookup"><span data-stu-id="d04db-138">Step 4 - Finish up</span></span>

1. <span data-ttu-id="d04db-139">**[アプリの追加]** ブレードで、構成したアプリ情報が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d04db-139">On the **Add app** blade, verify you configured the app information correctly.</span></span>
2. <span data-ttu-id="d04db-140">**[追加]** を選択して、アプリを Intune にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d04db-140">Choose **Add**, to upload the app to Intune.</span></span>

## <a name="step-5---update-a-line-of-business-app"></a><span data-ttu-id="d04db-141">手順 5 - 基幹業務アプリの更新</span><span class="sxs-lookup"><span data-stu-id="d04db-141">Step 5 - Update a line of business app</span></span>

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="next-steps"></a><span data-ttu-id="d04db-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="d04db-142">Next steps</span></span>

<span data-ttu-id="d04db-143">作成したアプリがアプリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d04db-143">The app you have created is displayed in the apps list.</span></span> <span data-ttu-id="d04db-144">選択したグループにアプリを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d04db-144">You can now assign it to the groups you choose.</span></span> <span data-ttu-id="d04db-145">詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d04db-145">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

<span data-ttu-id="d04db-146">アプリのプロパティと割り当てを監視する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d04db-146">Learn more about the ways in which you can monitor the properties and assignment of your app.</span></span> <span data-ttu-id="d04db-147">詳細については、「[アプリ情報と割り当てを監視する方法](apps-monitor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d04db-147">For more information, see [How to monitor app information and assignments](apps-monitor.md).</span></span>

<span data-ttu-id="d04db-148">Intune におけるアプリのコンテキストについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d04db-148">Learn more about the context of your app in Intune.</span></span> <span data-ttu-id="d04db-149">詳細については、「[デバイスとアプリのライフサイクルの概要](introduction-device-app-lifecycles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d04db-149">For more information, see [Overview of device and app lifecycles](introduction-device-app-lifecycles.md)</span></span>