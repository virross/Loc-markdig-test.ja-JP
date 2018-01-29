---
title: "Windows Phone の基幹業務アプリを Intune に追加する方法"
titlesuffix: Azure portal
description: "Windows Phone の基幹業務アプリを Intune に追加する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8342b753771235b045a0f89452c142772016321e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="e6ff4-103">Windows Phone の基幹業務 (LOB) アプリを Microsoft Intune に追加する方法</span><span class="sxs-lookup"><span data-stu-id="e6ff4-103">How to add Windows Phone line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="e6ff4-104">手順 1 - ソフトウェアのセットアップ ファイルを指定する</span><span class="sxs-lookup"><span data-stu-id="e6ff4-104">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="e6ff4-105">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-105">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="e6ff4-106">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-106">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="e6ff4-107">**[Intune]** ブレードで、**[アプリの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-107">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="e6ff4-108">**[モバイル アプリ]** ワークロードで、**[管理]** > **[アプリ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-108">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="e6ff4-109">アプリの一覧の上にある **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-109">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="e6ff4-110">**[アプリの追加]** ブレードで、**[基幹業務アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-110">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="e6ff4-111">手順 2 - アプリのパッケージ ファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="e6ff4-111">Step 2 - Configure the app package file</span></span>

1. <span data-ttu-id="e6ff4-112">**[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-112">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="e6ff4-113">**[アプリのパッケージ ファイル]** ブレードで、参照ボタンを選択し、拡張子 **.xap** が付いた Windows Phone インストール ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-113">On the **App package** file blade, choose the browse button, and select a Windows Phone installation file with the extension, **.xap**.</span></span>
3. <span data-ttu-id="e6ff4-114">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-114">When you are finished, choose **OK**.</span></span>


## <a name="step-3---configure-app-information"></a><span data-ttu-id="e6ff4-115">手順 3 - アプリ情報を構成する</span><span class="sxs-lookup"><span data-stu-id="e6ff4-115">Step 3 - Configure app information</span></span>

1. <span data-ttu-id="e6ff4-116">**[アプリの追加]** ブレードで、**アプリケーション パッケージ** ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-116">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="e6ff4-117">**[アプリ情報]** ブレードで、アプリの情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-117">On the **App information** blade, configure the app information.</span></span> <span data-ttu-id="e6ff4-118">選択したアプリによっては、このブレード内の一部の値が自動的に入力されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-118">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="e6ff4-119">**[名前]** - アプリの名前を入力します。この名前は会社のポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-119">**Name** - Enter the name of the app as it is displayed in the company portal.</span></span> <span data-ttu-id="e6ff4-120">使用するアプリ名はすべて一意にします。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-120">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="e6ff4-121">同じアプリ名が 2 つ存在する場合、会社のポータルではそのいずれかのみがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-121">If the same app name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="e6ff4-122">**説明** - アプリの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-122">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="e6ff4-123">説明はポータル サイトでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-123">The description is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="e6ff4-124">**[発行元]** - アプリの発行元の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-124">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="e6ff4-125">**[カテゴリ]** - 1 つまたは複数の組み込みアプリ カテゴリ、または作成したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-125">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="e6ff4-126">カテゴリを使うと、会社のポータルを閲覧するとき、ユーザーにとってアプリを探すのが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-126">Using categories makes it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="e6ff4-127">**[会社のポータルでおすすめアプリとして表示します]** - ユーザーがアプリを探す際に、会社のポータルのメイン ページでアプリを目立つように表示します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-127">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="e6ff4-128">**[情報 URL]** - 必要に応じて、このアプリに関する情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-128">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="e6ff4-129">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-129">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="e6ff4-130">**[プライバシー URL]** - 必要に応じて、このアプリのプライバシー情報が含まれる Web サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-130">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="e6ff4-131">この URL は会社のポータルでユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-131">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="e6ff4-132">**[開発者]** - 必要に応じて、アプリ開発者の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-132">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="e6ff4-133">**[所有者]** - 必要に応じて、このアプリの所有者の名前 ("**人事部**" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-133">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="e6ff4-134">**[メモ]** - このアプリに関連付けるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-134">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="e6ff4-135">**[ロゴ]** - アプリに関連付けるアイコンをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-135">**Logo** - Upload an icon that is associated with the app.</span></span> <span data-ttu-id="e6ff4-136">ユーザーが会社のポータルを参照するとき、アプリにこのアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-136">This icon is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="e6ff4-137">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-137">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="e6ff4-138">手順 4. - 完了</span><span class="sxs-lookup"><span data-stu-id="e6ff4-138">Step 4 - Finish up</span></span>

1. <span data-ttu-id="e6ff4-139">**[アプリの追加]** ブレードで、構成した情報が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-139">On the **Add app** blade, verify that you configured the information correctly.</span></span>
2. <span data-ttu-id="e6ff4-140">**[追加]** を選択して、アプリを Intune にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-140">Choose **Add**, to upload the app to Intune.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6ff4-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="e6ff4-141">Next steps</span></span>

<span data-ttu-id="e6ff4-142">作成したアプリがアプリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-142">The app you have created is displayed in the apps list.</span></span> <span data-ttu-id="e6ff4-143">選択したグループにアプリを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-143">You can now assign it to the groups you choose.</span></span> <span data-ttu-id="e6ff4-144">詳細については、[アプリをグループに割り当てる方法](apps-deploy.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-144">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

<span data-ttu-id="e6ff4-145">アプリのプロパティと割り当てを監視する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-145">Learn more about the ways in which you can monitor the properties and assignment of your app.</span></span> <span data-ttu-id="e6ff4-146">詳細については、「[アプリ情報と割り当てを監視する方法](apps-monitor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-146">For more information, see [How to monitor app information and assignments](apps-monitor.md).</span></span>

<span data-ttu-id="e6ff4-147">Intune におけるアプリのコンテキストについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-147">Learn more about the context of your app in Intune.</span></span> <span data-ttu-id="e6ff4-148">詳細については、「[デバイスとアプリのライフサイクルの概要](introduction-device-app-lifecycles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6ff4-148">For more information, see [Overview of device and app lifecycles](introduction-device-app-lifecycles.md)</span></span>
