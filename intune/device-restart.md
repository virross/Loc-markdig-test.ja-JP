---
title: "Intune でデバイスをリモートで再起動する"
titlesuffix: Azure portal
description: "デバイスの再起動アクションを使用して、デバイスをリモートで再起動する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9e20740c1890faabec7e2e1155007a21d4b090b2
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="remotely-restart-devices-with-intune"></a><span data-ttu-id="d1a25-103">Intune でデバイスをリモートで再起動する</span><span class="sxs-lookup"><span data-stu-id="d1a25-103">Remotely restart devices with Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="d1a25-104">**[再起動]** デバイス アクションでは、選択したデバイスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="d1a25-104">The **Restart** device action causes the device you choose to be restarted.</span></span> <span data-ttu-id="d1a25-105">デバイスの所有者には再起動の自動通知が行われないため、作業内容が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1a25-105">The device owner is not automatically notified of the restart, therefore might lose work.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="d1a25-106">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="d1a25-106">Supported platforms</span></span>

- <span data-ttu-id="d1a25-107">Windows - Windows 8.1 以降でサポートされています</span><span class="sxs-lookup"><span data-stu-id="d1a25-107">Windows - Supported on Windows 8.1 and later</span></span>
- <span data-ttu-id="d1a25-108">Windows Phone - Windows Phone 8.1 以降でサポートされています</span><span class="sxs-lookup"><span data-stu-id="d1a25-108">Windows Phone - Supported on Windows Phone 8.1 and later</span></span>
- <span data-ttu-id="d1a25-109">iOS - サポートされています</span><span class="sxs-lookup"><span data-stu-id="d1a25-109">iOS - Supported</span></span>

    > [!Note]  
    > <span data-ttu-id="d1a25-110">このコマンドは、監視されているデバイスと**デバイス ロック** アクセス権を要求します。</span><span class="sxs-lookup"><span data-stu-id="d1a25-110">This command requires a supervised devices and the **Device Lock** access right.</span></span> <span data-ttu-id="d1a25-111">デバイスがすぐに再起動します。</span><span class="sxs-lookup"><span data-stu-id="d1a25-111">The device restarts immediately.</span></span> <span data-ttu-id="d1a25-112">パスコードでロックされている iOS デバイスが再起動後に Wi-Fi ネットワークに再び参加することはありません。再起動後、サーバーと通信できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d1a25-112">Passcode-locked iOS devices will not rejoin a Wi-Fi network after restart; after restart, they may not be able to communicate with the server.</span></span>
- <span data-ttu-id="d1a25-113">macOS - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="d1a25-113">macOS - Not supported</span></span>
- <span data-ttu-id="d1a25-114">Android - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="d1a25-114">Android - Not supported</span></span>

## <a name="how-to-restart-a-device"></a><span data-ttu-id="d1a25-115">デバイスを再起動する方法</span><span class="sxs-lookup"><span data-stu-id="d1a25-115">How to restart a device</span></span>

1. <span data-ttu-id="d1a25-116">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d1a25-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="d1a25-117">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a25-117">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="d1a25-118">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a25-118">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="d1a25-119">**[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a25-119">on the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="d1a25-120">管理するデバイスの一覧からデバイスを選択し、その後**[再起動]** デバイス リモート アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a25-120">From the list of devices you manage, choose a device, and then choose the **Restart** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1a25-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="d1a25-121">Next steps</span></span>

<span data-ttu-id="d1a25-122">実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a25-122">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
