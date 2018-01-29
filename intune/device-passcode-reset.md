---
title: "Intune でデバイスのパスコードをリセットして削除する"
titlesuffix: Azure portal
description: "Intune で管理するデバイスのパスコードをリセットして削除する方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 591939c50ef093235b8b63589476012b69f204e1
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a><span data-ttu-id="b92be-103">Intune で管理するデバイスのパスコードをリセットして削除する</span><span class="sxs-lookup"><span data-stu-id="b92be-103">Reset and remove the passcode on Intune-managed devices</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b92be-104">この記事では、*削除*と*リセット*という用語は同じ意味で使用されます。</span><span class="sxs-lookup"><span data-stu-id="b92be-104">The terms *remove* and *reset* are used interchangeably in this article.</span></span>

<span data-ttu-id="b92be-105">**[パスコードの削除]** アクションは、デバイスの新しいパスコードを生成します。新しいパスコードは、[<*デバイス名*> **概要**] ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b92be-105">The **Remove passcode** action generates a new passcode for the device, which is displayed on the <*device name*> **Overview** blade.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="b92be-106">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="b92be-106">Supported platforms</span></span>

- <span data-ttu-id="b92be-107">Windows - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="b92be-107">Windows - Not supported</span></span>
- <span data-ttu-id="b92be-108">Windows Phone - Windows Phone 8.1 から Azure AD に参加していない Windows 10 Creators Update まで、Windows 10 Creators Update 以降でサポートされています</span><span class="sxs-lookup"><span data-stu-id="b92be-108">Windows Phone - Supported on Windows Phone 8.1 to Windows 10 Creators update not Azure AD joined, Windows 10 Creators Update and later</span></span>
- <span data-ttu-id="b92be-109">iOS - サポートされています</span><span class="sxs-lookup"><span data-stu-id="b92be-109">iOS - Supported</span></span>
- <span data-ttu-id="b92be-110">macOS - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="b92be-110">macOS - Not supported</span></span>
- <span data-ttu-id="b92be-111">Android - Android 7 より前の Android バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b92be-111">Android - Supported on Android versions earlier than Android 7.</span></span> <span data-ttu-id="b92be-112">Android for Work はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b92be-112">Android for Work is not supported.</span></span>

## <a name="how-to-reset-a-passcode"></a><span data-ttu-id="b92be-113">パスコードをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="b92be-113">How to reset a passcode</span></span>

1. <span data-ttu-id="b92be-114">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b92be-114">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b92be-115">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b92be-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="b92be-116">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b92be-116">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="b92be-117">**[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b92be-117">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="b92be-118">管理するデバイスの一覧からデバイスを選択し、その後 **[パスコードの削除]** デバイス リモート アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b92be-118">From the list of devices you manage, choose a device, and then choose the **Remove passcode** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b92be-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="b92be-119">Next steps</span></span>

<span data-ttu-id="b92be-120">実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b92be-120">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
