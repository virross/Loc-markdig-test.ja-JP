---
title: "Intune で iOS デバイスのユーザーをログアウトする"
titlesuffix: Azure portal
description: "Intune で iOS デバイスの現在のユーザーをログアウトする方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f8907eff47b87fa0e4266c213b750357db172695
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a><span data-ttu-id="aa37b-103">Intune で管理される iOS デバイスの現在のユーザーをログアウトする</span><span class="sxs-lookup"><span data-stu-id="aa37b-103">Logout the current user on Intune-managed iOS devices</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="aa37b-104">**[現在のユーザーのログアウト]** アクションにより、[iOS 教育プロファイル](education-settings-configure-ios.md)を使用して iOS Classroom アプリを管理するように構成されている共有の iPad デバイスから現在のユーザーがログアウトします。</span><span class="sxs-lookup"><span data-stu-id="aa37b-104">The **Logout current user** action logs out the current user on a shared iPad device that is configured to manage the iOS Classroom app using an [iOS education profile](education-settings-configure-ios.md).</span></span> 

## <a name="supported-platforms"></a><span data-ttu-id="aa37b-105">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="aa37b-105">Supported platforms</span></span>

- <span data-ttu-id="aa37b-106">Windows - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="aa37b-106">Windows - Not supported</span></span>
- <span data-ttu-id="aa37b-107">Windows Phone - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="aa37b-107">Windows Phone - Not supported</span></span>
- <span data-ttu-id="aa37b-108">iOS - iOS 9.3 以降 (共有 iPad デバイスのみ) でサポートされています</span><span class="sxs-lookup"><span data-stu-id="aa37b-108">iOS - Supported on iOS 9.3 and later (shared iPad devices only)</span></span>
- <span data-ttu-id="aa37b-109">macOS - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="aa37b-109">macOS - Not supported</span></span>
- <span data-ttu-id="aa37b-110">Android - サポートされていません</span><span class="sxs-lookup"><span data-stu-id="aa37b-110">Android - Not supported</span></span>

## <a name="how-to-logout-the-current-user"></a><span data-ttu-id="aa37b-111">現在のユーザーをログアウトする方法</span><span class="sxs-lookup"><span data-stu-id="aa37b-111">How to logout the current user</span></span>

1.  <span data-ttu-id="aa37b-112">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="aa37b-112">Sign into the Azure portal.</span></span>
2.  <span data-ttu-id="aa37b-113">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="aa37b-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3.  <span data-ttu-id="aa37b-114">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa37b-114">On the **Intune** blade, choose **Devices**.</span></span>
4.  <span data-ttu-id="aa37b-115">**[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa37b-115">On the **Devices and groups** blade, choose **All devices**.</span></span>
5.  <span data-ttu-id="aa37b-116">管理するデバイスの一覧から iOS デバイスを選択して、**[現在のユーザーのログアウト]** のデバイス リモート アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="aa37b-116">From the list of devices you manage, choose an iOS device, and then choose the **Logout current user** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aa37b-117">次の手順</span><span class="sxs-lookup"><span data-stu-id="aa37b-117">Next steps</span></span>

<span data-ttu-id="aa37b-118">実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa37b-118">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
