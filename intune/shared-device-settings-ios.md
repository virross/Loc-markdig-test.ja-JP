---
title: "iOS 用 Intune 共有デバイス構成設定"
titlesuffix: Azure portal
description: "iOS デバイスのロック画面に情報を表示するために使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1f9256594493aeebda9ab65e3df269ea7acaca5b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a><span data-ttu-id="6cb9d-103">iOS デバイスのロック画面にメッセージを表示するための共有デバイス構成設定</span><span class="sxs-lookup"><span data-stu-id="6cb9d-103">Shared device configuration settings to display messages on the iOS device lock screen</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="6cb9d-104">共有デバイス構成設定では、ログイン ウィンドウやロック画面に表示する任意のテキストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-104">Shared device configuration settings let you specify optional text displayed on the login window and lock screen.</span></span> <span data-ttu-id="6cb9d-105">たとえば、"忘れ物として見つけた場合の返却先" メッセージや資産タグなどを入力できます。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-105">For example, you can enter an "If Lost, Return to" message and Asset Tag Information.</span></span> 

>[!IMPORTANT]
> <span data-ttu-id="6cb9d-106">この機能は、iOS 9.3 以降を実行している監視対象デバイスでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-106">This capability is supported on supervised devices running iOS 9.3 and later.</span></span>

## <a name="create-shared-device-settings"></a><span data-ttu-id="6cb9d-107">共有デバイス設定を作成する</span><span class="sxs-lookup"><span data-stu-id="6cb9d-107">Create shared device settings</span></span>

1. <span data-ttu-id="6cb9d-108">**[デバイス機能]** ブレードで、**[共有デバイスの構成 (監視のみ)]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-108">On the **Device features** blade, choose **Shared Device Configuration (supervised only)**.</span></span>
2. <span data-ttu-id="6cb9d-109">**[共有デバイスの構成 (監視のみ)]** ブレードで、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-109">On the **Shared Device Configuration (supervised only)** blade, configure the following settings:</span></span>
    - <span data-ttu-id="6cb9d-110">**[資産タグ情報]** - デバイスの資産タグに関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-110">**Asset tag information** - Enter information about the asset tag of the device.</span></span> <span data-ttu-id="6cb9d-111">例: **Contoso Corp によって所有されている**。入力した情報は、このプロファイルを割り当てるすべてのデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-111">For example: **Owned by Contoso Corp**. The information you enter is applied to all devices you assign this profile to.</span></span>
    - <span data-ttu-id="6cb9d-112">**[ロック画面の脚注]** - デバイスの紛失または盗難時に、返却に役立つようなメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-112">**Lock screen footnote** - If the device is lost or stolen, enter a note that might help get the device returned.</span></span> <span data-ttu-id="6cb9d-113">例: **拾った方はこの番号 (xxx-xxx-xxx) にご連絡ください**。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-113">For example: **If found, call 'number'**.</span></span>
3. <span data-ttu-id="6cb9d-114">完了したら、**[プロファイルの作成]** ブレードに戻るまで **[OK]** を選択し、ブレードに戻ったら **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-114">When you are finished, choose **OK** until you return to the **Create Profile** blade, then choose **Create**.</span></span> 


## <a name="next-steps"></a><span data-ttu-id="6cb9d-115">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6cb9d-115">Next steps</span></span>

<span data-ttu-id="6cb9d-116">選択したグループにデバイス プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-116">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="6cb9d-117">詳しくは、「[デバイス プロファイルを割り当てる方法](device-profile-assign.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6cb9d-117">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
