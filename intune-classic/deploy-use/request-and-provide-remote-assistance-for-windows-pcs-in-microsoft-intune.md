---
title: "Windows PC のリモート アシスタンス要求と提供"
description: "PC として管理されている Windows デスクトップにリモート アシスタントを提供し、PC をリモートで起動するためにエンドユーザーまたは IT 監理者が行う手順について説明します。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2654491-5144-408a-a45a-644eb91ac1bb
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 776fffed98a7fb8c9d38547f8782a2e25f562eff
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="request-and-provide-remote-assistance-for-windows-pcs"></a><span data-ttu-id="3f700-103">Windows PC のリモート アシスタンス要求と提供</span><span class="sxs-lookup"><span data-stu-id="3f700-103">Request and provide remote assistance for Windows PCs</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]


<span data-ttu-id="3f700-104">このトピックの情報は、Intune ソフトウェア クライアントを使用して PC として管理している Windows デスクトップにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f700-104">The information in this topic applies only to Windows desktops that you are managing as PCs by using the Intune software client.</span></span>

<span data-ttu-id="3f700-105">Intune では別売りの [TeamViewer](https://www.teamviewer.com) ソフトウェアを利用し、Intune ソフトウェア クライアントを実行するユーザーにリモート アシスタンス ヘルプを与えます。</span><span class="sxs-lookup"><span data-stu-id="3f700-105">Intune can use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running the Intune software client.</span></span> <span data-ttu-id="3f700-106">ユーザーが Microsoft Intune Center のヘルプを要求すると、通知が届きます。要求を承諾し、アシスタンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="3f700-106">When a user requests help from the Microsoft Intune Center, you are informed by an alert, can accept the request, and then provide assistance.</span></span> <span data-ttu-id="3f700-107">この機能は Intune の既存の Windows リモート アシスタンス機能に換わるものです。</span><span class="sxs-lookup"><span data-stu-id="3f700-107">This functionality replaces the existing Windows Remote Assistance functionality in Intune.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="3f700-108">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="3f700-108">Before you start</span></span>

<span data-ttu-id="3f700-109">リモート アシスタンス要求の確立または応答を開始する前に、次の前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f700-109">Before you begin to establish and to respond to remote assistance requests, ensure that the following prerequisites are in place:</span></span>

- <span data-ttu-id="3f700-110">TeamViewer Web サイトにログインするために、[TeamViewer アカウントにサインアップ](https://login.teamviewer.com/LogOn#register)している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f700-110">You must have [signed up for a TeamViewer account](https://login.teamviewer.com/LogOn#register) to log in to the TeamViewer website.</span></span>
- <span data-ttu-id="3f700-111">管理する Windows PC を [Windows ソフトウェア クライアントで管理](manage-windows-pcs-with-microsoft-intune.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f700-111">Windows PCs that you want to administer must be [managed by the Windows software client](manage-windows-pcs-with-microsoft-intune.md)</span></span>
- <span data-ttu-id="3f700-112">Intune でサポートされているすべての Windows PC オペレーティング システムを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3f700-112">All Windows PC operating systems supported by Intune can be administered.</span></span>

## <a name="configure-the-teamviewer-connector"></a><span data-ttu-id="3f700-113">TeamViewer Connector を構成する</span><span class="sxs-lookup"><span data-stu-id="3f700-113">Configure the TeamViewer Connector</span></span>

1. <span data-ttu-id="3f700-114">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-114">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.</span></span>
2. <span data-ttu-id="3f700-115">**[管理者]** ワークスペースで、**[TeamViewer]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-115">In the **Admin** workspace, choose **TeamViewer**.</span></span>
3. <span data-ttu-id="3f700-116">**[TeamViewer]** ページの **[TeamViewer Connector]** で、**[有効化]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-116">On the **TeamViewer** page, under **TeamViewer Connector**, choose **Enable**.</span></span>
4. <span data-ttu-id="3f700-117">**[TeamViewer の有効化]** ダイアログ ボックスで、ライセンス条項を **[承諾]** します。</span><span class="sxs-lookup"><span data-stu-id="3f700-117">In the **Enable TeamViewer** dialog box, view, then **Accept** the license terms.</span></span> <span data-ttu-id="3f700-118">TeamViewer ライセンスをまだ所有していない場合、**[TeamViewer ライセンスの購入]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-118">If you don't already own a TeamViewer license, choose **Purchase a TeamViewer license**.</span></span>
5. <span data-ttu-id="3f700-119">TeamViewer ブラウザー ウィンドウが開いたら、TeamViewer 資格情報でサイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3f700-119">After the TeamViewer browser window opens, sign into the site with your TeamViewer credentials.</span></span>
6. <span data-ttu-id="3f700-120">TeamViewer サイトで、Intune で TeamViewer に接続するためのオプションを読み、承諾します。</span><span class="sxs-lookup"><span data-stu-id="3f700-120">On the TeamViewer site, read, then accept the options to allow Intune to connect with TeamViewer.</span></span>
7. <span data-ttu-id="3f700-121">Intune コンソールで、**[TeamViewer Connector]** アイテムに **[有効]** が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f700-121">In the Intune console, verify that the **TeamViewer Connector** item shows as **Enabled**.</span></span>


## <a name="open-a-remote-assistance-request-end-user"></a><span data-ttu-id="3f700-122">リモート アシスタンス要求を登録する (エンド ユーザー)</span><span class="sxs-lookup"><span data-stu-id="3f700-122">Open a remote assistance request (end user)</span></span>

1. <span data-ttu-id="3f700-123">クライアント Windows PC で、**[Microsoft Intune Center]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f700-123">On a client Windows PC, open the **Microsoft Intune Center**.</span></span>
2. <span data-ttu-id="3f700-124">**[リモート アシスタンス]** で、**[リモート アシスタンスの要求]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-124">Under **Remote Assistance**, choose **Request Remote Assistance**.</span></span>
3. <span data-ttu-id="3f700-125">要求を承認すると (下図参照)、クライアントで TeamViewer が開きます。</span><span class="sxs-lookup"><span data-stu-id="3f700-125">After you approve the request (see below), TeamViewer opens on the client.</span></span> <span data-ttu-id="3f700-126">Web ブラウザーが TeamViewer アプリケーションを開こうとしているというメッセージが表示されたら、ユーザーはそれを承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f700-126">The user must accept any messages indicating that the web browser is trying to open the TeamViewer application.</span></span>
4. <span data-ttu-id="3f700-127">ユーザーには、管理者がユーザーの PC を操作してよいのか尋ねるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f700-127">The user sees a message asking if you can control their PC.</span></span> <span data-ttu-id="3f700-128">続行するには、ユーザーはメッセージを承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f700-128">They must accept this message to continue.</span></span>
5. <span data-ttu-id="3f700-129">リモート アシスタンス セッション中、管理者が接続されていることを示すウィンドウがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f700-129">During the remote assistance session, the user sees a window that shows them you are connected.</span></span> <span data-ttu-id="3f700-130">ユーザーがこのウィンドウを閉じると、リモート セッションが終了します。</span><span class="sxs-lookup"><span data-stu-id="3f700-130">If they close this window, the remote session ends.</span></span>

## <a name="respond-to-a-remote-assistance-request"></a><span data-ttu-id="3f700-131">リモート アシスタンス要求に応答する</span><span class="sxs-lookup"><span data-stu-id="3f700-131">Respond to a remote assistance request</span></span>

1. <span data-ttu-id="3f700-132">ユーザーがリモート アシスタンス要求を送信すると、**[アラート]** ワークスペースの **[管理]**  >  **[リモート アシスタンス]** に要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f700-132">When a user submits a remote assistance request, you can view it in the **Alerts** workspace, under **Monitoring** > **Remote Assistance**.</span></span> <span data-ttu-id="3f700-133">たとえば、</span><span class="sxs-lookup"><span data-stu-id="3f700-133">For example:</span></span>
> ![リモート アシスタンス要求のスクリーンショット](./media/team-viewer.png)

<br><span data-ttu-id="3f700-135">未応答のまま 4 時間以上経過すると、要求は削除されます。</span><span class="sxs-lookup"><span data-stu-id="3f700-135">If a request goes unanswered for more than 4 hours, it is removed.</span></span>
2. <span data-ttu-id="3f700-136">要求を承諾するには、**[要求を承認してリモート アシスタンスを開始する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-136">To accept the request, choose **Approve request and launch Remote Assistance**.</span></span>
3. <span data-ttu-id="3f700-137">**[リモート アシスタンスの新しい要求が保留中]** ダイアログ ボックスで、**[リモート アシスタンスの要求を受け入れる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-137">In the **A New Remote Assistance Request is Pending** dialog box, choose **Accept the remote assistance request**.</span></span> <span data-ttu-id="3f700-138">まだインストールされていない場合、TeamViewer は PC に必要なアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3f700-138">If it's not already installed, TeamViewer will install any necessary apps on your PC.</span></span>
4. <span data-ttu-id="3f700-139">TeamViewer は、管理者がエンド ユーザーの PC を操作することをエンド ユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3f700-139">TeamViewer then notifies the end user that you want to take control of their PC.</span></span> <span data-ttu-id="3f700-140">ユーザーがこの要求を承諾すると、TeamViewer ウィンドウが開き、管理者は PC を操作できます。</span><span class="sxs-lookup"><span data-stu-id="3f700-140">After the user has accepted the request, the TeamViewer windows opens, and you can control the PC.</span></span>

<span data-ttu-id="3f700-141">リモート アシスタンス セッション中、リモート PC を操作するためのあらゆる TeamViewer コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f700-141">While in a remote assistance session, you can use all available TeamViewer commands to control the remote PC.</span></span> <span data-ttu-id="3f700-142">コマンドの詳細については、TeamViewer Web サイトから [[リモート コントロールのマニュアル]](http://www.teamviewer.com/en/support/documents/) をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="3f700-142">For help with these commands, download the [Manual for remote control](http://www.teamviewer.com/en/support/documents/) from the TeamViewer website.</span></span>

## <a name="close-the-remote-assistance-session"></a><span data-ttu-id="3f700-143">リモート アシスタンス セッションを閉じる</span><span class="sxs-lookup"><span data-stu-id="3f700-143">Close the remote assistance session</span></span>

<span data-ttu-id="3f700-144">**[TeamViewer]** ウィンドウの **[アクション]** メニューから **[セッションの終了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-144">From the **Actions** menu of the **TeamViewer** window, choose **End Session**.</span></span>

## <a name="remotely-restart-a-windows-pc"></a><span data-ttu-id="3f700-145">Windows PC をリモートで再起動する</span><span class="sxs-lookup"><span data-stu-id="3f700-145">Remotely restart a Windows PC</span></span>
<span data-ttu-id="3f700-146">問題を解決するためにユーザーをサポートする際、ユーザーの PC のリモート再起動が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f700-146">When helping your users with issues, you might need to remotely restart their PC from time to time.</span></span> <span data-ttu-id="3f700-147">次の手順で Windows PC をリモート再起動します。</span><span class="sxs-lookup"><span data-stu-id="3f700-147">Use the following steps to remotely restart a Windows PC.</span></span>

1.  <span data-ttu-id="3f700-148">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** &gt; **[すべてのデバイス]** (または、再起動する PC が含まれる別のグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-148">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC you want to restart).</span></span>

2.  <span data-ttu-id="3f700-149">1 つまたは複数の PC を選択し、**[リモート タスク]** &gt; **[コンピューターの再起動]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-149">Select one or more PCs, and then choose **Remote Tasks** &gt; **Restart Computer**.</span></span>

3.  <span data-ttu-id="3f700-150">タスクの状態を表示するには、ページの右下隅にある **[リモート タスク]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f700-150">To view the task status, choose **Remote Tasks** in the bottom right corner of the page.</span></span>

4.  <span data-ttu-id="3f700-151">**[タスクの状態]** ダイアログ ボックスで、現在のリモート タスク、タスクの状態、デバイス名、発生したエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f700-151">In the **Task Status** dialog box, review the current remote tasks, task status, device name, and any reported errors.</span></span>

### <a name="see-also"></a><span data-ttu-id="3f700-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f700-152">See also</span></span>

[<span data-ttu-id="3f700-153">Intune ソフトウェア クライアントを使用した一般的な Windows PC 管理タスク</span><span class="sxs-lookup"><span data-stu-id="3f700-153">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)