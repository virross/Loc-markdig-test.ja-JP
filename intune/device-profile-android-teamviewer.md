---
title: "TeamViewer を使用してデバイスをリモート管理する方法"
titlesuffix: Azure portal
description: "TeamViewer を使用してデバイスをリモート管理する方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 46e850cdda27444d18354b972d10b0cd02c036d9
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="provide-remote-assistance-for-intune-managed-devices"></a><span data-ttu-id="c7ef0-103">Intune で管理されたデバイスにリモート アシスタンスを提供する</span><span class="sxs-lookup"><span data-stu-id="c7ef0-103">Provide remote assistance for Intune managed devices</span></span>

<span data-ttu-id="c7ef0-104">Intune では、別売りの [TeamViewer](https://www.teamviewer.com) ソフトウェアを使って、管理対象のデバイスのユーザーにリモート アシスタンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-104">Intune can use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to users of devices you manage.</span></span> <span data-ttu-id="c7ef0-105">このトピックの情報を活用して作業を開始してください。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-105">Use the information in this topic to get started.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="c7ef0-106">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="c7ef0-106">Before you start</span></span>

### <a name="supported-devices"></a><span data-ttu-id="c7ef0-107">サポートされるデバイス</span><span class="sxs-lookup"><span data-stu-id="c7ef0-107">Supported devices</span></span>

<span data-ttu-id="c7ef0-108">Intune で管理された Android デバイスと Windows デバイスでは、リモート管理がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-108">Intune-managed Android and Windows devices support remote administration.</span></span>

>[!NOTE]
><span data-ttu-id="c7ef0-109">Windows Holographic (HoloLens)、Windows Team (Surface Hub)、Windows 10 S は、TeamViewer ソフトウェアではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-109">Windows Holographic (HoloLens), Windows Team (Surface Hub) and Windows 10 S are not supported by the TeamViewer software.</span></span> <span data-ttu-id="c7ef0-110">使用してデバイスを管理する必要があります、 [PC クライアント](/intune-classic/deploy-use/pc-management-comparison?toc=/intune/toc.json)Intune クラシック ポータルでします。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-110">You still need to manage devices using the [PC client](/intune-classic/deploy-use/pc-management-comparison?toc=/intune/toc.json) in the Intune classic portal.</span></span>



### <a name="required-permissions"></a><span data-ttu-id="c7ef0-111">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c7ef0-111">Required permissions</span></span>

<span data-ttu-id="c7ef0-112">Azure Portal のユーザーが [Intune ロール](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control)として次のアクセス許可を割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-112">Ensure that the user of the Azure portal has the following permissions assigned to them as an [Intune role](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control):</span></span>
- <span data-ttu-id="c7ef0-113">管理者が TeamViewer Connector の設定を変更できるようにするには、**リモート アシスタンスの更新**のアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-113">To let the admin modify the TeamViewer connector settings, grant the **Update Remote Assistance** permission.</span></span>
- <span data-ttu-id="c7ef0-114">管理者が新しいリモート アシスタンス要求を開始できるようにするには、**リモート アシスタンスの要求**のアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-114">To let the admin initiate a new remote assistance request, grant the **Request Remote Assistance** permission.</span></span> <span data-ttu-id="c7ef0-115">**リモート アシスタンスの要求**のアクセス許可を持つユーザーは、どのユーザーに対してもセッションの開始を要求できます。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-115">Users with the **Request Remote Assistance** permission can request to initiate a session for any user.</span></span> <span data-ttu-id="c7ef0-116">Intune ロールの割り当てスコープによって制限されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-116">They are not limited by any Intune role assignment scope.</span></span> <span data-ttu-id="c7ef0-117">Intune のロールの割り当て範囲によって、リモート アシスタンス要求を開始できるデバイスやユーザーが制限されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-117">Intune role assignment scopes do not limit the devices or users for which Remote Assistance requests can be initiated.</span></span>

>[!NOTE]
><span data-ttu-id="c7ef0-118">TeamViewer を有効にすると、Intune コネクタ用 TeamViewer での TeamViewer セッションの作成、Active Directory データの読み取り、TeamViewer アカウント アクセス トークンの保存を許可することになります。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-118">By enabling TeamViewer, you are allowing the TeamViewer for Intune Connector to create TeamViewer sessions, read Active Directory data, and save the TeamViewer account access token.</span></span>

### <a name="configure-the-intune-teamviewer-connector"></a><span data-ttu-id="c7ef0-119">Intune TeamViewer Connector の構成</span><span class="sxs-lookup"><span data-stu-id="c7ef0-119">Configure the Intune TeamViewer connector</span></span>

<span data-ttu-id="c7ef0-120">デバイスにリモート アシスタンスを提供する前に、以下の手順で Intune TeamViewer コネクタを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-120">Before you can provide remote assistance to devices, you must configure the Intune TeamViewer connector, using the following steps:</span></span>


1. <span data-ttu-id="c7ef0-121">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-121">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="c7ef0-122">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-122">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="c7ef0-123">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-123">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="c7ef0-124">**[デバイスとグループ]** ブレードで、**[セットアップ]** > **[TeamViewer Connector]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-124">On the **Devices and groups** blade, choose **Setup** > **TeamViewer Connector**.</span></span>
5. <span data-ttu-id="c7ef0-125">**[TeamViewer Connector]** ブレードで、**[有効化]** をクリックし、TeamViewer サービス使用許諾契約書を表示して承認します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-125">On the **TeamViewer Connector** blade, click **Enable**, then view and accept the TeamViewer service license agreement.</span></span>
6. <span data-ttu-id="c7ef0-126">**[TeamViewer にログインして承認する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-126">Choose **Log in to TeamViewer & Authorize**.</span></span>
7. <span data-ttu-id="c7ef0-127">TeamViewer サイトの Web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-127">A web page opens to the TeamViewer site.</span></span> <span data-ttu-id="c7ef0-128">TeamViewer ライセンスの資格情報を入力し、**[サインイン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-128">Enter your TeamViewer license credentials, and then click **Sign In**.</span></span>


## <a name="how-to-remotely-administer-a-device"></a><span data-ttu-id="c7ef0-129">デバイスのリモート管理方法</span><span class="sxs-lookup"><span data-stu-id="c7ef0-129">How to remotely administer a device</span></span>

1. <span data-ttu-id="c7ef0-130">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-130">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="c7ef0-131">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-131">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="c7ef0-132">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-132">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="c7ef0-133">**[デバイス]** ブレードで、**[管理]** > **[すべてのデバイス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-133">On the **Devices** blade, choose **Manage** > **All devices**.</span></span>
5. <span data-ttu-id="c7ef0-134">リモート管理するデバイスを選択し、[デバイスのプロパティ] ブレードで **[詳細]** > **[新しいリモート アシスタンス セッション]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-134">Select the device that you want to remotely administer, and then, on the device properties blade, choose **More** > **New Remote Assistance Session**.</span></span>
6. <span data-ttu-id="c7ef0-135">Intune を TeamViewer サービスに接続すると、デバイスの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-135">After Intune connects to the TeamViewer service, you'll see some information about the device.</span></span> <span data-ttu-id="c7ef0-136">**[接続]** を選択して、リモート セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-136">Choose **Connect** to start the remote session.</span></span>

![Android の TeamViewer の例](./media/android-teamviewer.png)

<span data-ttu-id="c7ef0-138">TeamViewer ウィンドウで、さまざまなデバイスのリモート操作 (デバイスのリモート制御など) を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-138">In the TeamViewer window, you can perform a range of remote actions on the device, including remote control of the device.</span></span> <span data-ttu-id="c7ef0-139">実行できる操作の詳細については、[TeamViewer のドキュメント](https://www.teamviewer.com/support/documents/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-139">For full details of the actions you can perform, see the [TeamViewer documentation](https://www.teamviewer.com/support/documents/).</span></span>

<span data-ttu-id="c7ef0-140">設定が完了したら、TeamViewer ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-140">When you are finished, close the TeamViewer window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c7ef0-141">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c7ef0-141">Next steps</span></span>

<span data-ttu-id="c7ef0-142">デバイス上のポータル サイト アプリのアイコンに通知フラグが表示され、エンド ユーザーはアプリを開くと通知を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-142">An end user sees a notification flag on the Company Portal app icon on their device, and also see a notification when they open the app.</span></span> <span data-ttu-id="c7ef0-143">その後、リモート アシスタンス要求を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="c7ef0-143">They can then accept the remote assistance request.</span></span>
