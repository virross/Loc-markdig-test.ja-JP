---
title: "アプリを更新する"
description: "新しいバージョンが必要な場合は、このトピックに含まれるアプリを更新する方法を参照してください。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b8495c50a040e6c6a7fe7777b9e415333088b5ac
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="update-apps-using-microsoft-intune"></a><span data-ttu-id="dd6e4-103">Microsoft Intune を使用してアプリを更新する</span><span class="sxs-lookup"><span data-stu-id="dd6e4-103">Update apps using Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="dd6e4-104">Microsoft Intune は、アプリの更新プログラムを管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-104">Microsoft Intune can help you manage app updates.</span></span> <span data-ttu-id="dd6e4-105">新しいバージョンが必要な場合は、このトピックに含まれるアプリを更新する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-105">Use the information in this topic to understand how to update apps when a new version is required.</span></span>

## <a name="how-to-update-apps"></a><span data-ttu-id="dd6e4-106">アプリを更新する方法</span><span class="sxs-lookup"><span data-stu-id="dd6e4-106">How to update apps</span></span>
<span data-ttu-id="dd6e4-107">展開しているアプリの新しいバージョンがリリースされるときに、Intune によって、新しいバージョンのアプリケーションを更新し、展開することができます。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-107">When a new version of an app that you've deployed is released, Intune lets you update and deploy the newer version of the app.</span></span> <span data-ttu-id="dd6e4-108">展開のみを同じアプリの新しいバージョン (同じ識別子を使用) に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-108">You can only replace a deployment with a newer version of the same app (that has the same identifier).</span></span> <span data-ttu-id="dd6e4-109">アプリの更新プログラムを使用して、別のアプリ パッケージで展開を更新することはできません。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-109">You cannot use app updates to update a deployment with a different app package.</span></span>

### <a name="app-identifiers"></a><span data-ttu-id="dd6e4-110">アプリ識別子</span><span class="sxs-lookup"><span data-stu-id="dd6e4-110">App identifiers</span></span>
<span data-ttu-id="dd6e4-111">アプリ識別子は、アプリを一意に識別するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-111">The app identifier is a property that uniquely identifies an app.</span></span> <span data-ttu-id="dd6e4-112">同じ識別子を持つアプリの複数のコピーをインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-112">You cannot install multiple copies of an app with the same identifier.</span></span> <span data-ttu-id="dd6e4-113">次に、アプリ ID の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-113">Following are some examples of app identifiers:</span></span>

- <span data-ttu-id="dd6e4-114">**iOS** - バンドル ID (例: com.microsoft.excel)</span><span class="sxs-lookup"><span data-stu-id="dd6e4-114">**iOS** - Bundle ID (for example: com.microsoft.excel)</span></span>
- <span data-ttu-id="dd6e4-115">**Android** - パッケージ ID (例: com.microsoft.excel)</span><span class="sxs-lookup"><span data-stu-id="dd6e4-115">**Android** - Package ID (for example: com.microsoft.excel)</span></span>
- <span data-ttu-id="dd6e4-116">**Windows Phone** - (xap インストーラー) 製品 ID (GUID) を使用</span><span class="sxs-lookup"><span data-stu-id="dd6e4-116">**Windows Phone** - (xap installer) use Product ID (GUID)</span></span>
- <span data-ttu-id="dd6e4-117">**Windows** - (appx/appxbundle) パッケージの完全名を使用</span><span class="sxs-lookup"><span data-stu-id="dd6e4-117">**Windows** - (appx/appxbundle), use the Package Full Name</span></span>



> [!IMPORTANT]
> <span data-ttu-id="dd6e4-118">**[必須のインストール]** の展開アクションでアプリを展開し、その後、展開アクションを **[利用可能なインストール]** に変更した場合、アプリの更新プログラムは、展開を変更する前にアプリをインストールしたデバイスに自動的にインストールされません。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-118">When you deploy an app with a deployment action of **Required install** and later change the deployment action to **Available install**, updates to the app are not automatically installed on devices that installed the app before the deployment change was made.</span></span> <span data-ttu-id="dd6e4-119">この問題を解決するには、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-119">To fix this issue, you can do the following:</span></span>
>
> -   <span data-ttu-id="dd6e4-120">デバイスのユーザーに対して、ポータル サイトに移動し、インストールされているアプリを選択し、**[インストール]** を選択するように指示します。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-120">Have the user of the device go to the company portal, select the installed app, and then choose **Install**.</span></span>
> -   <span data-ttu-id="dd6e4-121">展開アクションを **[アンインストール]** に変更します。アプリがアンインストールされた後で、**[利用可能なインストール]** の展開アクションでアプリを再展開します。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-121">Change the deployment action to **Uninstall**, and after the app has been uninstalled, redeploy the app with a deployment action of **Available install**.</span></span>

### <a name="to-update-an-app"></a><span data-ttu-id="dd6e4-122">アプリを更新するには</span><span class="sxs-lookup"><span data-stu-id="dd6e4-122">To update an app</span></span>

1.  <span data-ttu-id="dd6e4-123">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[アプリ]** &gt; **[アプリ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-123">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.</span></span>

2.  <span data-ttu-id="dd6e4-124">**[アプリ]** ボックスの一覧で、更新するアプリを選択し、**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-124">From the **Apps** list, select the app you want to update, and then choose **Edit**.</span></span>

3.  <span data-ttu-id="dd6e4-125">**ソフトウェアの編集** ウィザードで、新しいアプリ パッケージの詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-125">In the **Edit Software** wizard, supply any new details for the app package.</span></span>

4.  <span data-ttu-id="dd6e4-126">終了したら、**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-126">When you are finished, choose **Update**.</span></span>

<span data-ttu-id="dd6e4-127">次回デバイスが利用可能なアプリを確認するときに、アプリが自動的に最新バージョンに更新されます。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-127">When devices next check for available apps, the app will be automatically updated to the latest version.</span></span>
<span data-ttu-id="dd6e4-128">アプリをアプリ パッケージ (基幹業務アプリ) からインストールした場合、アプリに同じ ID が与えられている限り、必須の展開と利用可能な展開の両方に対してアプリが自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-128">For apps installed from an app package (line of business apps), the app will be upgraded automatically for both required and available deployments, as long as the app has the same identifier.</span></span>

<span data-ttu-id="dd6e4-129">アプリがストア リンクとして展開されている場合、アプリの取得元であるストアにより更新が管理されます。</span><span class="sxs-lookup"><span data-stu-id="dd6e4-129">For apps deployed as a link to a store, the update is managed by the store from which the app originates.</span></span>
