---
title: "紛失した iOS デバイスを Intune で検索する"
titlesuffix: Azure portal
description: "紛失したまたは盗まれた iOS デバイスを Intune で検索する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9d03555e91a9e759e62b829576a0d39f957ab430
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a><span data-ttu-id="2345d-103">紛失したまたは盗まれた iOS デバイスを Intune で検索する</span><span class="sxs-lookup"><span data-stu-id="2345d-103">Locate lost or stolen iOS devices with Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="2345d-104">この**[デバイスを検索する]** デバイス アクションは、紛失したまたは盗まれた iOS デバイスの場所をマップに表示します。</span><span class="sxs-lookup"><span data-stu-id="2345d-104">The **Locate Device** device action displays the location of a lost or stolen iOS device on a map.</span></span> <span data-ttu-id="2345d-105">会社所有の iOS デバイスを DEP で登録し、監視モードに設定している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2345d-105">The device must be a corporate-owned iOS device, enrolled through DEP, that is in supervised mode.</span></span> <span data-ttu-id="2345d-106">このアクションを使用するには、デバイスが[紛失モード](/intune-azure/manage-devices/lost-mode.md)に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2345d-106">Before you use this action, the device must have been placed into [lost mode](/intune-azure/manage-devices/lost-mode.md).</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="2345d-107">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="2345d-107">Supported platforms</span></span>

- <span data-ttu-id="2345d-108">Windows - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="2345d-108">Windows - Not supported</span></span>
- <span data-ttu-id="2345d-109">Windows Phone - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="2345d-109">Windows Phone - Not supported</span></span>
- <span data-ttu-id="2345d-110">iOS - 監視されている企業所有の iOS 9.3 以降 (紛失モード) でサポートされています</span><span class="sxs-lookup"><span data-stu-id="2345d-110">iOS - Supported on iOS 9.3 and later (in Lost mode), supervised, and corp owned</span></span>
- <span data-ttu-id="2345d-111">macOS - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="2345d-111">macOS - Not supported</span></span>
- <span data-ttu-id="2345d-112">Android - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="2345d-112">Android - Not supported</span></span>

## <a name="how-to-locate-a-lost-or-stolen-device"></a><span data-ttu-id="2345d-113">紛失または盗難にあったデバイスを見つける方法</span><span class="sxs-lookup"><span data-stu-id="2345d-113">How to locate a lost or stolen device</span></span>

1. <span data-ttu-id="2345d-114">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2345d-114">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="2345d-115">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2345d-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="2345d-116">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2345d-116">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="2345d-117">**[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2345d-117">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="2345d-118">管理するデバイスの一覧から iOS デバイスを選択し、その後**[デバイスを検索する]** リモート アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2345d-118">From the list of devices you manage, choose an iOS device, and then choose the **Locate Device** remote action.</span></span>
6. <span data-ttu-id="2345d-119">デバイスの位置が特定されると、その場所が **[デバイスを探索する]** ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2345d-119">After the device has been located, it's location is displayed on the **Locate device** blade.</span></span>
    <span data-ttu-id="2345d-120">![[デバイスを検索する] ブレード](./media/locate-device.png)</span><span class="sxs-lookup"><span data-stu-id="2345d-120">![Locate device blade](./media/locate-device.png)</span></span>

>[!NOTE]
><span data-ttu-id="2345d-121">プライバシーのために、マップでズームインできる距離は制限されています。</span><span class="sxs-lookup"><span data-stu-id="2345d-121">For privacy purposes, the distance you can zoom into the map is limited.</span></span>

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a><span data-ttu-id="2345d-122">紛失モードとデバイスを探索するアクションのセキュリティおよびプライバシー情報</span><span class="sxs-lookup"><span data-stu-id="2345d-122">Security and privacy information for the lost mode and locate device actions</span></span>
- <span data-ttu-id="2345d-123">このアクションを有効にするまで、デバイスの位置情報は Intune に送信されません。</span><span class="sxs-lookup"><span data-stu-id="2345d-123">No device location information is sent to Intune until you turn this action on.</span></span>
- <span data-ttu-id="2345d-124">デバイスを探索するアクションを使用した場合、デバイスの緯度と経度の座標が Intune に送信され、Azure Portal に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2345d-124">When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.</span></span>
- <span data-ttu-id="2345d-125">データは 24 時間保管されてから、削除されます。</span><span class="sxs-lookup"><span data-stu-id="2345d-125">The data is stored for 24 hours, then removed.</span></span> <span data-ttu-id="2345d-126">位置データを手動で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2345d-126">You cannot manually remove the location data.</span></span>
- <span data-ttu-id="2345d-127">位置データは、保管中も、転送中も暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="2345d-127">Location data is encrypted, both while stored, and while being transmitted.</span></span>
- <span data-ttu-id="2345d-128">紛失モードを構成する場合、ロック画面に表示するメッセージの入力時に、デバイスを見つけた人がデバイスを返すのに役立つ情報を含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2345d-128">When you configure lost mode, we recommend that the message you enter to display on the lock screen includes information that helps someone who finds the device to return it.</span></span>


## <a name="next-steps"></a><span data-ttu-id="2345d-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="2345d-129">Next steps</span></span>

<span data-ttu-id="2345d-130">実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2345d-130">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>