---
title: "Windows PC をインベントリから削除する"
description: "Intune で管理されている Windows PC をインベントリから削除する方法。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99dc86bf20a50710cf1661702d46a3124861a619
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="retire-a-windows-pc"></a><span data-ttu-id="30360-103">Windows PC をインベントリから削除する</span><span class="sxs-lookup"><span data-stu-id="30360-103">Retire a Windows PC</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="30360-104">Intune ソフトウェア クライアントを実行して PC として管理しているデスクトップは、次の手順でインベントリから削除します。</span><span class="sxs-lookup"><span data-stu-id="30360-104">Use the following steps to retire desktops that you are managing as PCs by running the Intune software client on them.</span></span> <span data-ttu-id="30360-105">PC をインベントリから削除すると、Intune 管理から除外されます。</span><span class="sxs-lookup"><span data-stu-id="30360-105">When you retire a PC, it removes it from Intune management.</span></span> <span data-ttu-id="30360-106">Intune から PC をリセットし、工場出荷時の設定に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="30360-106">You cannot factory reset a PC from Intune to set it back to its original factory settings.</span></span>

1.  <span data-ttu-id="30360-107">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** &gt; **[すべてのデバイス]** (または、インベントリから削除する PC が含まれる別のグループ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="30360-107">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC you want to retire).</span></span>

2.  <span data-ttu-id="30360-108">削除するデバイスを選択し、**[インベントリからの削除/ワイプ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30360-108">Select the devices you want to retire, and then choose **Retire/Wipe**.</span></span>

<span data-ttu-id="30360-109">PC を Intune に再登録する場合は、「[Microsoft Intune を使用して Windows PC クライアントをインストールする](install-the-windows-pc-client-with-microsoft-intune.md)」を参照して、その PC にソフトウェア クライアントを再度インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="30360-109">To re-enroll a PC into Intune, reinstall the software client on the PC using guidance in [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).</span></span>

<span data-ttu-id="30360-110">PC が Intune に接続できない場合、**[ダッシュボード]** ワークスペースにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30360-110">If a PC cannot connect to Intune, a message is displayed in the **Dashboard** workspace.</span></span>

<span data-ttu-id="30360-111">PC をインベントリから削除した場合:</span><span class="sxs-lookup"><span data-stu-id="30360-111">When you retire a PC:</span></span>

-   <span data-ttu-id="30360-112">PC は Intune の管理とインベントリから削除され、そのコンピューターに関連付けられていたライセンスは再利用できます。</span><span class="sxs-lookup"><span data-stu-id="30360-112">It is removed from the Intune management and inventory, and the license associated with the PC is made available for re-use.</span></span> <span data-ttu-id="30360-113">削除/ワイプを行うと、PC から Intune ソフトウェア クライアントが削除されますが、アプリまたはデータは削除されません。</span><span class="sxs-lookup"><span data-stu-id="30360-113">Retire/Wipe removes the Intune software client but does not remove apps or data from the PC.</span></span> <span data-ttu-id="30360-114">削除すると、PC でフル ワイプは実行されません。</span><span class="sxs-lookup"><span data-stu-id="30360-114">This retirement does not perform a full wipe on the PC.</span></span>

-   <span data-ttu-id="30360-115">そのコンピューターの状態は、Intune コンソールに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="30360-115">Its status no longer displays in the Intune console.</span></span>

-   <span data-ttu-id="30360-116">Intune によって、PC からソフトウェア クライアントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="30360-116">Intune removes the software client from the PC.</span></span> <span data-ttu-id="30360-117">PC が Intune サービスに接続していない場合、ソフトウェア クライアントは、次に接続したときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="30360-117">If the PC is not connected to the Intune service, the software client will be removed next time it connects.</span></span>

-   <span data-ttu-id="30360-118">PC から Microsoft Intune Endpoint Protection が削除されます。</span><span class="sxs-lookup"><span data-stu-id="30360-118">Microsoft Intune Endpoint Protection is removed from the PC.</span></span> <span data-ttu-id="30360-119">PC に他のエンドポイント保護アプリケーションがインストールされ、無効になっている場合は、Microsoft Intune Endpoint Protection が削除された後で、そのアプリケーションを再び有効にして、PC を保護できます。</span><span class="sxs-lookup"><span data-stu-id="30360-119">If the PC has another endpoint application installed and it is disabled, that application can be re-enabled after Microsoft Intune Endpoint Protection is removed to ensure that your PC are protected.</span></span>

-   <span data-ttu-id="30360-120">すべてのポリシーが PC から削除され、ポリシーによって設定された値は変更されます。</span><span class="sxs-lookup"><span data-stu-id="30360-120">Any policies are removed from the PC and the values that were set by the policy will be changed.</span></span>

-   <span data-ttu-id="30360-121">PC は、ソフトウェアの更新プログラムや、マルウェアの定義の更新を Intune サービスから受信しなくなります。</span><span class="sxs-lookup"><span data-stu-id="30360-121">The PC no longer receives software updates or malware definition updates from the Intune service.</span></span>

-   <span data-ttu-id="30360-122">PC がどのように構成されているかによって異なりますが、Windows Server Update Services、Windows Update、または Microsoft Update を使用して、引き続き更新プログラムを受信できます。</span><span class="sxs-lookup"><span data-stu-id="30360-122">Depending on how they are configured, retired PC can continue to receive updates by using Windows Server Update Services, Windows Update, or Microsoft Update.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="30360-123">クライアント ソフトウェアがグループ ポリシー オブジェクト (GPO) を使用してインストールされている場合、ソフトウェアが再インストールされることを防ぐため、クライアント ソフトウェアを削除する前に、グループ ポリシー オブジェクト (GPO) を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30360-123">If the client software was installed by using a Group Policy Object (GPO), you must remove the Group Policy Object (GPO) before you can remove the client software to prevent the software from being reinstalled.</span></span>

    <span data-ttu-id="30360-124">Endpoint Protection クライアントのアンインストールに失敗する場合は、「[Endpoint Protection に関するトラブルシューティング](/intune-classic/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune)」で詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="30360-124">If the Endpoint Protection client fails to uninstall, read [Troubleshoot Endpoint Protection](/intune-classic/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) for more help.</span></span>

### <a name="see-also"></a><span data-ttu-id="30360-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="30360-125">See also</span></span>

[<span data-ttu-id="30360-126">Intune ソフトウェア クライアントを使用した一般的な Windows PC 管理タスク</span><span class="sxs-lookup"><span data-stu-id="30360-126">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)