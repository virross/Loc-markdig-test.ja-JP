---
title: "Intune を使用した iOS デバイス向けの AirPlay 設定"
titlesuffix: Azure portal
description: "Intune を使用して、iOS デバイスを AirPlay 対応デバイスに自動接続する方法について説明します。"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9a1472d86a0a25e35ef26be1c579ff491437676b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="intune-airplay-settings-for-ios-devices"></a><span data-ttu-id="6a1ad-103">Intune を使用した iOS デバイス向けの AirPlay 設定</span><span class="sxs-lookup"><span data-stu-id="6a1ad-103">Intune AirPlay settings for iOS devices</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="6a1ad-104">これらの設定を使用すると、管理する iOS デバイスをネットワーク上の AirPlay 対応デバイス (Apple TV など) に接続することができます。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-104">Use these settings to help connect iOS devices you manage to AirPlay compatible devices (like Apple TVs) on your network.</span></span>
<span data-ttu-id="6a1ad-105">この機能を使用して、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-105">With this capability you can:</span></span>

- <span data-ttu-id="6a1ad-106">**デバイスとパスワードの一覧の構成** - ユーザーが、範囲内にある AirPlay デバイスに自動的に接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-106">**Configure a device and password list** - Let users automatically connect to AirPlay devices that are in range.</span></span> <span data-ttu-id="6a1ad-107">AirPlay デバイスの名前とパスワードを使用して、AirPlay デバイスをプロビジョニングします。これにより、ユーザーが接続するときに、AirPlay デバイスの名前とパスワードを指定する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-107">Provision them with the name and password of AirPlay devices so that they don't need to supply it when they connect.</span></span>
- <span data-ttu-id="6a1ad-108">**許可された出力先の構成** - AirPlay デバイスの一覧を (デバイス ID を使用して) 構成します。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-108">**Configure allowed destinations** - Configure a list of AirPlay devices (by device ID).</span></span> <span data-ttu-id="6a1ad-109">エンド ユーザーには一覧を作成したデバイスだけ(監視対象のデバイスのみ) が表示され、そのデバイスにのみ接続できます。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-109">End users can only see and connect to the devices you list (for supervised devices only).</span></span>

## <a name="get-started"></a><span data-ttu-id="6a1ad-110">作業開始</span><span class="sxs-lookup"><span data-stu-id="6a1ad-110">Get started</span></span>

1. <span data-ttu-id="6a1ad-111">**[デバイス機能]** ブレードで **[AirPlay]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-111">On the **Device features** blade, choose **AirPlay**.</span></span>
2. <span data-ttu-id="6a1ad-112">**[AirPlay]** ブレードで、次の操作の一方または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-112">On the **AirPlay** blade, choose one or both of the following actions:</span></span>

## <a name="configure-a-device-and-password-list"></a><span data-ttu-id="6a1ad-113">デバイスとパスワードの一覧を構成する</span><span class="sxs-lookup"><span data-stu-id="6a1ad-113">Configure a device and password list</span></span>

1. <span data-ttu-id="6a1ad-114">**[パスワード]** ブレードで、Airplay デバイス (例: **Contoso Apple TV**) の**デバイス名**と**パスワード**を入力します。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-114">On the **Passwords** blade, enter the **Device Name** and **Password** of an AirPlay device, for example **Contoso Apple TV**.</span></span>
2. <span data-ttu-id="6a1ad-115">デバイスの詳細を入力したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-115">After entering the device details, click **Add**.</span></span> <span data-ttu-id="6a1ad-116">**[デバイス名]** の一覧にデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-116">The device appears in the **Device Name** list.</span></span>
3. <span data-ttu-id="6a1ad-117">デバイスの追加を続けます。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-117">Continue to add devices.</span></span> <span data-ttu-id="6a1ad-118">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-118">When you are finished, choose **OK**.</span></span>


## <a name="configure-allowed-destinations"></a><span data-ttu-id="6a1ad-119">許可された出力先を構成する</span><span class="sxs-lookup"><span data-stu-id="6a1ad-119">Configure allowed destinations</span></span>

1. <span data-ttu-id="6a1ad-120">**[Allowed destinations (supervised only)]\(許可された出力先 (監視のみ)\)** ブレードで、AirPlay デバイスの**デバイス ID** を入力します (例: 52:46:CD:51:83:4C)。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-120">On the **Allowed destinations (supervised only)** blade, enter the **Device ID** of an AirPlay device, for example 52:46:CD:51:83:4C.</span></span>
2. <span data-ttu-id="6a1ad-121">デバイス ID を入力したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-121">After entering the device ID, click **Add**.</span></span> <span data-ttu-id="6a1ad-122">**[デバイス ID]** 一覧に ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-122">The ID appears in the **Device ID** list.</span></span>
3. <span data-ttu-id="6a1ad-123">デバイスの追加を続けます。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-123">Continue to add devices.</span></span> <span data-ttu-id="6a1ad-124">終了したら **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-124">When you are finished, choose **OK**.</span></span>

<span data-ttu-id="6a1ad-125">コンマ区切り値 (csv) ファイルから、デバイスとパスワード、および許可された出力先をインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-125">You can also import device and passwords, and allowed destinations from a comma-separated values (csv) file.</span></span>


## <a name="next-steps"></a><span data-ttu-id="6a1ad-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="6a1ad-126">Next steps</span></span>

<span data-ttu-id="6a1ad-127">選択したグループにデバイス プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-127">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="6a1ad-128">詳しくは、「[デバイス プロファイルを割り当てる方法](device-profile-assign.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6a1ad-128">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>

