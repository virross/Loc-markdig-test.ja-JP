---
title: "iOS の紛失モードを Intune でアクティブ化する"
titlesuffix: Azure portal
description: "Intune を使用して、紛失したまたは盗まれた iOS デバイスの紛失モードをアクティブ化する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5f16bd212c7a23d847da0929933fbd4b497099d0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a><span data-ttu-id="05619-103">iOS デバイスの紛失モードをアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="05619-103">Activate lost mode on iOS devices</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="05619-104">**紛失モード**のデバイス アクションを使用すると、紛失したまたは盗まれた iOS デバイスの紛失モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="05619-104">The **Lost mode** device action helps you enable lost mode on lost or stolen iOS devices.</span></span> <span data-ttu-id="05619-105">このモードでは、デバイスのロック画面に表示されるメッセージと電話番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="05619-105">This mode lets you specify a message and a phone number that is displayed on the lock screen of the device.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="05619-106">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="05619-106">Supported platforms</span></span>

- <span data-ttu-id="05619-107">Windows - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="05619-107">Windows - Not supported</span></span>
- <span data-ttu-id="05619-108">Windows Phone - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="05619-108">Windows Phone - Not supported</span></span>
- <span data-ttu-id="05619-109">iOS - 監視されている企業所有の iOS 9.3 以降でサポートされています</span><span class="sxs-lookup"><span data-stu-id="05619-109">iOS - Supported on iOS 9.3 and later, supervised, and corp owned</span></span>
- <span data-ttu-id="05619-110">macOS - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="05619-110">macOS - Not supported</span></span>
- <span data-ttu-id="05619-111">Android - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="05619-111">Android - Not supported</span></span>

## <a name="how-to-activate-lost-mode"></a><span data-ttu-id="05619-112">紛失モードをアクティブにする方法</span><span class="sxs-lookup"><span data-stu-id="05619-112">How to activate lost mode</span></span>

1. <span data-ttu-id="05619-113">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="05619-113">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="05619-114">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="05619-114">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="05619-115">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="05619-115">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="05619-116">**[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="05619-116">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="05619-117">管理するデバイスの一覧から iOS デバイスを選択し、**[紛失モード]** のリモート アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="05619-117">From the list of devices you manage, choose an iOS device, and then choose the **Lost mode** remote action.</span></span>
6. <span data-ttu-id="05619-118">**[紛失モード]** ブレードで、紛失モードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="05619-118">On the **Lost mode** blade, enable lost mode.</span></span> <span data-ttu-id="05619-119">次に、表示するメッセージを入力し、必要に応じて連絡先の電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="05619-119">Then, enter the message to be displayed, and optionally, a contact phone number.</span></span>
7. <span data-ttu-id="05619-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05619-120">Click **OK**.</span></span>

<span data-ttu-id="05619-121">紛失モードを有効にすると、デバイスのすべての利用がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="05619-121">When you enable lost mode, you block all use of the device.</span></span> <span data-ttu-id="05619-122">エンド ユーザーは、紛失モードを無効にするまでデバイスにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="05619-122">The end user cannot access the device until you disable lost mode.</span></span> <span data-ttu-id="05619-123">紛失モードを有効にした場合、**[デバイスを検索する]** アクションを使って、デバイスの場所を検索できます。</span><span class="sxs-lookup"><span data-stu-id="05619-123">While lost mode is enabled, you can use the **Locate device** action to find out where the device is.</span></span>
<span data-ttu-id="05619-124">紛失モードを使用するには、デバイスが監視モードにある企業所有の iOS デバイスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="05619-124">To use lost mode, the device must be a corporate-owned iOS device that is in supervised mode.</span></span>

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a><span data-ttu-id="05619-125">紛失モードとデバイスを探索するアクションのセキュリティおよびプライバシー情報</span><span class="sxs-lookup"><span data-stu-id="05619-125">Security and privacy information for the lost mode and locate device actions</span></span>
- <span data-ttu-id="05619-126">このアクションを有効にするまで、デバイスの位置情報は Intune に送信されません。</span><span class="sxs-lookup"><span data-stu-id="05619-126">No device location information is sent to Intune until you turn on this action.</span></span>
- <span data-ttu-id="05619-127">デバイスを探索するアクションを使用した場合、デバイスの緯度と経度の座標が Intune に送信され、Azure Portal に表示されます。</span><span class="sxs-lookup"><span data-stu-id="05619-127">When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.</span></span>
- <span data-ttu-id="05619-128">データは 24 時間保管されてから、削除されます。</span><span class="sxs-lookup"><span data-stu-id="05619-128">The data is stored for 24 hours, then removed.</span></span> <span data-ttu-id="05619-129">位置データを手動で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="05619-129">You cannot manually remove the location data.</span></span>
- <span data-ttu-id="05619-130">位置データは、保管中も、転送中も暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="05619-130">Location data is encrypted, both while stored, and while being transmitted.</span></span>
- <span data-ttu-id="05619-131">ロック画面に表示するメッセージの入力時に、デバイスを見つけた人がデバイスを返すのに役立つ情報を含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05619-131">We recommend that the message you enter to display on the lock screen includes information that helps someone who finds the device to return it.</span></span>

## <a name="next-steps"></a><span data-ttu-id="05619-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="05619-132">Next steps</span></span>

<span data-ttu-id="05619-133">実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="05619-133">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>

