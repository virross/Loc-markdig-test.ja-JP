---
title: "Exchange で管理されているモバイル デバイスのワイプ"
description: "Microsoft Intune では、Exchange ActiveSync (EAS) と Intune Exchange Connector を使って管理されているモバイル デバイスをワイプまたはリセットすることができます"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 753e5e9dac7199dff18d110808524f05aa669036
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a><span data-ttu-id="8bfb5-103">Wipe for [Exchange]-managed mobile devices</span><span class="sxs-lookup"><span data-stu-id="8bfb5-103">Wipe for Exchange-managed mobile devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="8bfb5-104">Microsoft Intune では、Exchange ActiveSync (EAS) と Intune Exchange Connector を使って管理されているモバイル デバイスをワイプまたはリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="8bfb5-104">Microsoft Intune allows you to wipe or reset mobile devices that are managed using Exchange ActiveSync (EAS) with the Intune Exchange Connector.</span></span> <span data-ttu-id="8bfb5-105">次の表に、Exchange ActiveSync で利用できるインベントリからのワイプ機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="8bfb5-105">The following table describes the wipe capabilities available through Exchange ActiveSync:</span></span>


|      <span data-ttu-id="8bfb5-106">ワイプの種類</span><span class="sxs-lookup"><span data-stu-id="8bfb5-106">Type of wipe</span></span>       |              <span data-ttu-id="8bfb5-107">Windows 8.1 および Windows RT 8.1</span><span class="sxs-lookup"><span data-stu-id="8bfb5-107">Windows 8.1 and Windows RT 8.1</span></span>              |                            <span data-ttu-id="8bfb5-108">iOS</span><span class="sxs-lookup"><span data-stu-id="8bfb5-108">iOS</span></span>                             |                          <span data-ttu-id="8bfb5-109">Android</span><span class="sxs-lookup"><span data-stu-id="8bfb5-109">Android</span></span>                          |
|-------------------------|----------------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|        <span data-ttu-id="8bfb5-110">フル ワイプ</span><span class="sxs-lookup"><span data-stu-id="8bfb5-110">Full wipe</span></span>        |          <span data-ttu-id="8bfb5-111">メール アカウントとキャッシュ済みメールを削除します。</span><span class="sxs-lookup"><span data-stu-id="8bfb5-111">Removes mail account and cached mail.</span></span>           |                      <span data-ttu-id="8bfb5-112">出荷時の設定に戻します。</span><span class="sxs-lookup"><span data-stu-id="8bfb5-112">XFactory reset.</span></span>                       |                      <span data-ttu-id="8bfb5-113">出荷時の設定に戻します。</span><span class="sxs-lookup"><span data-stu-id="8bfb5-113">Factory reset.</span></span>                       |
|  <span data-ttu-id="8bfb5-114">選択的なワイプ/電子メール</span><span class="sxs-lookup"><span data-stu-id="8bfb5-114">Selective wipe/email</span></span>   |                  <span data-ttu-id="8bfb5-115">電子メール アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="8bfb5-115">Removes email account.</span></span>                  |                       <span data-ttu-id="8bfb5-116">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8bfb5-116">Not supported.</span></span>                       |                      <span data-ttu-id="8bfb5-117">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8bfb5-117">Not supported.</span></span>                       |
| <span data-ttu-id="8bfb5-118">選択的なワイプ/ポリシー</span><span class="sxs-lookup"><span data-stu-id="8bfb5-118">Selective wipe/policies</span></span> | <span data-ttu-id="8bfb5-119">ポリシーの強制は削除されますが、設定は変更されません</span><span class="sxs-lookup"><span data-stu-id="8bfb5-119">Policy enforcement removed, but settings are not changed</span></span> | <span data-ttu-id="8bfb5-120">ポリシーの強制は削除されますが、設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="8bfb5-120">XPolicy enforcement removed, but settings are not changed.</span></span> | <span data-ttu-id="8bfb5-121">ポリシーの強制は削除されますが、設定は変更されません</span><span class="sxs-lookup"><span data-stu-id="8bfb5-121">Policy enforcement removed, but settings are not changed.</span></span> |

