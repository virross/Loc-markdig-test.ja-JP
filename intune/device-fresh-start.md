---
title: "Intune が稼働する Windows 10 デバイスのリセット"
titlesuffix: Azure portal
description: "[新たに開始] を使用して、Intune が稼働する Windows 10 PC をリセットする方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff6198cb42d5c96ed4e4c4e0009a8bbd6f6a0dec
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a><span data-ttu-id="7e238-103">[新たに開始] を使用して Intune が稼働する Windows 10 デバイスをリセットする</span><span class="sxs-lookup"><span data-stu-id="7e238-103">Use Fresh Start to reset Windows 10 devices with Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="7e238-104">**[新たに開始]** デバイス アクションを実行すると、Creators Update が稼働する Windows 10 PC にインストールされているすべてのアプリが削除され、PC が Windows の最新バージョンに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="7e238-104">The **Fresh Start** device action removes any apps that were installed on a Windows 10 PC running the Creators Update, then automatically updates the PC to the latest version of Windows.</span></span>
<span data-ttu-id="7e238-105">この機能は、新しい PC に付属することの多い事前インストール済み (OEM) アプリを削除するのに使うことができます。</span><span class="sxs-lookup"><span data-stu-id="7e238-105">This can be used to help remove pre-installed (OEM) apps that are often delivered with a new PC.</span></span> <span data-ttu-id="7e238-106">このデバイス アクションを発行するときにユーザー データを保持するかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7e238-106">You can configure if user data is retained when this device action is issued.</span></span> <span data-ttu-id="7e238-107">この場合、アプリと設定は削除されますが、ユーザーのホーム フォルダーの内容は保持されます。</span><span class="sxs-lookup"><span data-stu-id="7e238-107">In this case, apps and settings are removed, but the contents of the users Home folder are retained.</span></span>

## <a name="how-to-use-fresh-start"></a><span data-ttu-id="7e238-108">新たに開始の使用方法</span><span class="sxs-lookup"><span data-stu-id="7e238-108">How to use Fresh Start</span></span>

1. <span data-ttu-id="7e238-109">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e238-109">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="7e238-110">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7e238-110">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="7e238-111">**[Intune]** ブレードで、**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e238-111">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="7e238-112">**[デバイスとグループ]** ブレードで、**[すべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e238-112">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="7e238-113">管理するデバイスの一覧から Windows 10 デスクトップ デバイスを選択し、その後 **[新たに開始]** デバイス リモート アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e238-113">From the list of devices you manage, choose a Windows 10 desktop device, and then choose the **Fresh Start** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7e238-114">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7e238-114">Next steps</span></span>

<span data-ttu-id="7e238-115">実行したアクションの状態を確認するには、**[デバイスとグループ]** ブレードで **[デバイス アクション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e238-115">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>

