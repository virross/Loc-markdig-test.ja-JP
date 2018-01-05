---
title: "管理されたデバイスを Intune でリモートからロックする"
titlesuffix: Azure portal
description: "Intune を使用して管理対象デバイスをリモートからロックする方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8905b97a5912010a2516788a8da66441fc6f89ae
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="remotely-lock-managed-devices-with-intune"></a><span data-ttu-id="77c3c-103">管理されたデバイスを Intune でリモートからロックする</span><span class="sxs-lookup"><span data-stu-id="77c3c-103">Remotely lock managed devices with Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="77c3c-104">**リモート ロック**を使用して、選択したデバイスをロックできます。</span><span class="sxs-lookup"><span data-stu-id="77c3c-104">The **Remote lock** device locks the selected device.</span></span> <span data-ttu-id="77c3c-105">デバイスの所有者は、ロックを解除するためにパスコードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77c3c-105">The device owner must use their passcode to unlock it.</span></span> <span data-ttu-id="77c3c-106">PIN またはパスワードが設定されているデバイスに限り、リモートでロックできます。</span><span class="sxs-lookup"><span data-stu-id="77c3c-106">You can only remotely lock a device that has a PIN or password set.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="77c3c-107">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="77c3c-107">Supported platforms</span></span>

- <span data-ttu-id="77c3c-108">Windows - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="77c3c-108">Windows - Not supported</span></span>
- <span data-ttu-id="77c3c-109">Windows Phone - Windows Phone 8.1 以降でサポートされています</span><span class="sxs-lookup"><span data-stu-id="77c3c-109">Windows Phone - Supported on Windows Phone 8.1 and later</span></span>
- <span data-ttu-id="77c3c-110">iOS - サポートされています</span><span class="sxs-lookup"><span data-stu-id="77c3c-110">iOS - Supported</span></span>
- <span data-ttu-id="77c3c-111">macOS - サポートされています</span><span class="sxs-lookup"><span data-stu-id="77c3c-111">macOS - Supported</span></span>

    > [!Note]  
    > <span data-ttu-id="77c3c-112">6 桁の回復用 PIN を設定します。</span><span class="sxs-lookup"><span data-stu-id="77c3c-112">Set a 6-digit recovery PIN.</span></span> <span data-ttu-id="77c3c-113">ロックされているとき、別のデバイス アクションが送信されるまで、**デバイス概要**ブレードにその PIN が表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c3c-113">When locked, the **Device overview** blade displays the PIN until another device action is sent.</span></span>
- <span data-ttu-id="77c3c-114">Android - サポートされています</span><span class="sxs-lookup"><span data-stu-id="77c3c-114">Android - Supported</span></span>

## <a name="how-to-remote-lock-a-device"></a><span data-ttu-id="77c3c-115">デバイスをリモート ロックする方法</span><span class="sxs-lookup"><span data-stu-id="77c3c-115">How to remote lock a device</span></span>

1. <span data-ttu-id="77c3c-116">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="77c3c-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="77c3c-117">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="77c3c-117">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="77c3c-118">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c3c-118">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="77c3c-119">**[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c3c-119">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="77c3c-120">管理するデバイスの一覧からデバイスを選択し、その後 **[リモート ロック]** デバイス リモート アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c3c-120">From the list of devices you manage, choose a device, and then choose the **Remote lock** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="77c3c-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="77c3c-121">Next steps</span></span>

<span data-ttu-id="77c3c-122">実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c3c-122">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
