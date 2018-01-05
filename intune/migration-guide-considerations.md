---
title: "移行において特に考慮すべき事項"
description: "この記事では、移行キャンペーンを開始する前の特別な移行に関する考慮事項を示します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 7ff1180275fddc7f0d6ef957c4680d7c34ad471e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="special-migration-considerations"></a><span data-ttu-id="3c584-103">移行において特に考慮すべき事項</span><span class="sxs-lookup"><span data-stu-id="3c584-103">Special migration considerations</span></span>

<span data-ttu-id="3c584-104">既存の MDM プロバイダー環境に応じて該当する可能性のある、移行において特に考慮すべき事項があります。</span><span class="sxs-lookup"><span data-stu-id="3c584-104">There are special migration considerations which may apply depending on your existing MDM provider environment.</span></span>

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a><span data-ttu-id="3c584-105">Apple の Device Enrollment Program (DEP) を出荷時の設定に戻す</span><span class="sxs-lookup"><span data-stu-id="3c584-105">Factory reset for Apple’s Device Enrollment Program (DEP)</span></span>

<span data-ttu-id="3c584-106">Apple の Device Enrollment Program (DEP) のデバイス構成は、エンド ユーザーが削除できない設定になっています。</span><span class="sxs-lookup"><span data-stu-id="3c584-106">The Apple Device Enrollment Program (DEP) sets device configurations that cannot be removed by the end user.</span></span> <span data-ttu-id="3c584-107">DEP の高度な管理機能を保持するには、デバイスを出荷時の設定にリセットして既定の (新品の) 状態に戻してから、Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c584-107">To retain the advanced management features of DEP, the device must be returned to the out-of-box (new) state by a factory reset to enroll it into Intune.</span></span>

<span data-ttu-id="3c584-108">DEP の使用を続行して Intune でデバイスを管理するには、[Device Enrollment Program で iOS デバイスの登録をセットアップします](device-enrollment-program-enroll-ios.md)。</span><span class="sxs-lookup"><span data-stu-id="3c584-108">To continue using DEP to manage the devices in Intune, [set up iOS device enrollment with Device Enrollment Program](device-enrollment-program-enroll-ios.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="3c584-109">次の手順</span><span class="sxs-lookup"><span data-stu-id="3c584-109">Next steps</span></span>

[<span data-ttu-id="3c584-110">フェーズ 2: 移行のキャンペーン</span><span class="sxs-lookup"><span data-stu-id="3c584-110">Phase 2: Migration campaign</span></span>](migration-guide-campaign.md)
