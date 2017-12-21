---
title: "Intune を使用してデバイスを管理する"
titleSuffix: Intune on Azure
description: "Intune で管理するデバイスを確認し、そのデバイスで各種操作を実行する方法について説明します。\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0686b3ece3a929cb06a29f4e58046872b70ec926
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="what-is-microsoft-intune-device-management"></a><span data-ttu-id="01398-103">Microsoft Intune デバイスの管理とは</span><span class="sxs-lookup"><span data-stu-id="01398-103">What is Microsoft Intune device management?</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="01398-104">IT 管理者はデータをリスクから保護しながら、エンド ユーザーが自分の作業に必要なリソースが管理されたデバイスから提供されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01398-104">As an IT admin, you must ensure that managed devices are providing the resources your end users need to do their work while protecting that data from risk.</span></span>

<span data-ttu-id="01398-105">**[デバイス]** ワークロードでは、管理対象のデバイスについての情報が得られ、そのデバイスでリモート タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="01398-105">The **Devices** workload gives you insights into the devices you manage, and lets you perform remote tasks on those devices.</span></span> <span data-ttu-id="01398-106">このワークロードにアクセスするには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="01398-106">To access the workload:</span></span>

1. <span data-ttu-id="01398-107">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="01398-107">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="01398-108">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="01398-108">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="01398-109">**[Intune]** で、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01398-109">In **Intune**, choose **Devices**.</span></span>
4. <span data-ttu-id="01398-110">次のデバイスに関する情報を確認して、リモート デバイスの操作を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="01398-110">You can view information about devices and perform the remote device actions as follows:</span></span>
    - <span data-ttu-id="01398-111">**[概要]** - 管理可能な登録済みデバイスのスナップショット。</span><span class="sxs-lookup"><span data-stu-id="01398-111">**Overview** - A snapshot of the enrolled devices you can manage.</span></span>
    - <span data-ttu-id="01398-112">**[すべてのデバイス]** - 管理する登録済みデバイスの一覧。</span><span class="sxs-lookup"><span data-stu-id="01398-112">**All devices** - A list of the enrolled devices you manage.</span></span> <span data-ttu-id="01398-113">表示する情報を絞り込むには、**[フィルター]** または **[列]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01398-113">Choose **Filter** or **Columns** to refine the information displayed.</span></span> <span data-ttu-id="01398-114">[デバイス インベントリを表示する](device-inventory.md)には、デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="01398-114">Select a device to [view device inventory](device-inventory.md).</span></span>
    - <span data-ttu-id="01398-115">**[Azure AD デバイス]** - Azure Active Directory (AD) に登録されている、または参加しているデバイスの一覧。</span><span class="sxs-lookup"><span data-stu-id="01398-115">**Azure AD devices** - A list of the devices registered or joined with Azure Active Directory (AD).</span></span> <span data-ttu-id="01398-116">Azure AD のデバイス管理の概要については、[こちら](https://docs.microsoft.com/azure/active-directory/device-management-introduction)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01398-116">Learn more about [Azure AD device management](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
    - <span data-ttu-id="01398-117">**[デバイス アクション]** - アクション、その状態、アクションを開始したユーザー、時刻などの、デバイスに実行されたリモート アクションの履歴。</span><span class="sxs-lookup"><span data-stu-id="01398-117">**Device actions** - A history of the remote actions performed on devices including the action, its status, who initiated the action, and the time.</span></span>

    ![デバイス アクションの監視](./media/monitor-device-actions.png)

    - <span data-ttu-id="01398-119">**[TeamViewer]** - TeamViewer サービスを使用すると、Intune で管理されている Android デバイスのユーザーが、IT 管理者からリモート アシスタンスを受けられるようになります。</span><span class="sxs-lookup"><span data-stu-id="01398-119">**TeamViewer** - TeamViewer service allows users of Intune-managed Android devices to get remote assistance from their IT administrator.</span></span> <span data-ttu-id="01398-120">TeamViewer については、[こちら](device-profile-android-teamviewer.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01398-120">Learn more about [TeamViewer](device-profile-android-teamviewer.md).</span></span>

## <a name="available-device-actions"></a><span data-ttu-id="01398-121">行えるデバイス アクション</span><span class="sxs-lookup"><span data-stu-id="01398-121">Available device actions</span></span>
<span data-ttu-id="01398-122">表示されるアクションは、デバイス プラットフォームやデバイスの構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="01398-122">The actions available depend on the device platform, and the configuration of the device.</span></span>

- [<span data-ttu-id="01398-123">デバイス インベントリを表示する</span><span class="sxs-lookup"><span data-stu-id="01398-123">View device inventory</span></span>](device-inventory.md)
- <span data-ttu-id="01398-124">以下のリモート デバイス アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="01398-124">Perform remote device actions:</span></span>
    - [<span data-ttu-id="01398-125">会社データの削除</span><span class="sxs-lookup"><span data-stu-id="01398-125">Remove company data</span></span>](devices-wipe.md#remove-company-data)
    - [<span data-ttu-id="01398-126">出荷時の設定に戻す</span><span class="sxs-lookup"><span data-stu-id="01398-126">Factory reset</span></span>](devices-wipe.md#factory-reset)
    - [<span data-ttu-id="01398-127">リモート ロック</span><span class="sxs-lookup"><span data-stu-id="01398-127">Remote lock</span></span>](device-remote-lock.md)
    - [<span data-ttu-id="01398-128">パスコードのリセット</span><span class="sxs-lookup"><span data-stu-id="01398-128">Reset passcode</span></span>](device-passcode-reset.md)
    - <span data-ttu-id="01398-129">[アクティブ化ロックをバイパスする](device-activation-lock-bypass.md) (iOS のみ)</span><span class="sxs-lookup"><span data-stu-id="01398-129">[Bypass Activation Lock](device-activation-lock-bypass.md) (iOS only)</span></span>
    - <span data-ttu-id="01398-130">[新たに開始](device-fresh-start.md) (Windows のみ)</span><span class="sxs-lookup"><span data-stu-id="01398-130">[Fresh Start](device-fresh-start.md) (Windows only)</span></span>
    - <span data-ttu-id="01398-131">[紛失モード](device-lost-mode.md) (iOS のみ)</span><span class="sxs-lookup"><span data-stu-id="01398-131">[Lost mode](device-lost-mode.md) (iOS only)</span></span>
    - <span data-ttu-id="01398-132">[デバイスを検索する](device-locate.md) (iOS のみ)</span><span class="sxs-lookup"><span data-stu-id="01398-132">[Locate device](device-locate.md) (iOS only)</span></span>
    - <span data-ttu-id="01398-133">[再起動](device-restart.md) (Windows のみ)</span><span class="sxs-lookup"><span data-stu-id="01398-133">[Restart](device-restart.md) (Windows only)</span></span>
    - [<span data-ttu-id="01398-134">Windows 10 の PIN のリセット</span><span class="sxs-lookup"><span data-stu-id="01398-134">Windows 10 PIN reset</span></span>](device-windows-pin-reset.md)
    - [<span data-ttu-id="01398-135">Android のリモート コントロール</span><span class="sxs-lookup"><span data-stu-id="01398-135">Remote control for Android</span></span>](device-profile-android-teamviewer.md)
    - [<span data-ttu-id="01398-136">同期デバイス</span><span class="sxs-lookup"><span data-stu-id="01398-136">Synchronize device</span></span>](device-sync.md)


## <a name="next-steps"></a><span data-ttu-id="01398-137">次のステップ</span><span class="sxs-lookup"><span data-stu-id="01398-137">Next steps</span></span>

- <span data-ttu-id="01398-138">管理しているデバイスで実行されているアクションの状態を確認するには、**[デバイス アクション]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="01398-138">Choose **Device Actions** to see the status of actions taken on devices you manage.</span></span>
