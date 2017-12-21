---
title: "Intune を使用して iOS デバイスからユーザーを削除する"
titlesuffix: Azure portal
description: "Intune を使用して共有の iOS デバイスからユーザーを削除する方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f16d42406fa7961cc165adcbd1e7c4c7ab5d78b4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a><span data-ttu-id="0004c-103">Intune を使用して共有の iOS デバイスからユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="0004c-103">Remove a user from a shared iOS device with Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="0004c-104">**[ユーザーの削除]** アクションにより、[iOS 教育プロファイル](education-settings-configure-ios.md)を使用して iOS Classroom アプリを管理するように構成されている共有の iPad デバイスのローカル キャッシュからユーザーを選択して削除することができます。</span><span class="sxs-lookup"><span data-stu-id="0004c-104">The **Remove user** action deletes a user you choose from the local cache on a shared iPad device that has been configured to manage the iOS Classroom app with an [iOS education profile](education-settings-configure-ios.md).</span></span> 

## <a name="supported-platforms"></a><span data-ttu-id="0004c-105">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="0004c-105">Supported platforms</span></span>

- <span data-ttu-id="0004c-106">Windows - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="0004c-106">Windows - Not supported</span></span>
- <span data-ttu-id="0004c-107">Windows Phone - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="0004c-107">Windows Phone - Not supported</span></span>
- <span data-ttu-id="0004c-108">iOS - iOS 9.3 以降 (共有 iPad デバイスのみ) でサポートされています</span><span class="sxs-lookup"><span data-stu-id="0004c-108">iOS - Supported on iOS 9.3 and later (shared iPad devices only)</span></span>
- <span data-ttu-id="0004c-109">macOS - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="0004c-109">macOS - Not supported</span></span>
- <span data-ttu-id="0004c-110">Android - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="0004c-110">Android - Not supported</span></span>

## <a name="how-to-remove-a-user"></a><span data-ttu-id="0004c-111">ユーザーを削除する方法</span><span class="sxs-lookup"><span data-stu-id="0004c-111">How to remove a user</span></span>

1. <span data-ttu-id="0004c-112">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="0004c-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="0004c-113">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0004c-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="0004c-114">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0004c-114">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="0004c-115">**[デバイス]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0004c-115">On the **Devices** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="0004c-116">管理するデバイスの一覧で、iOS デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0004c-116">From the list of devices you manage, choose an iOS device.</span></span>
6. <span data-ttu-id="0004c-117">そのデバイスのブレードで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0004c-117">On the blade for that device, choose **Users**.</span></span>
7. <span data-ttu-id="0004c-118">一覧で、削除するユーザーを右クリックして、**[ユーザーの削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0004c-118">From the list, right-click the user you want to remove, and then choose **Remove user**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0004c-119">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0004c-119">Next steps</span></span>

<span data-ttu-id="0004c-120">実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0004c-120">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
