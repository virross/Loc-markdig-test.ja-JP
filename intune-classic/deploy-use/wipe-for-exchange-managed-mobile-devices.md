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
ms.openlocfilehash: 86055646c4ece4b50a557539e24112d33e98c9bc
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a><span data-ttu-id="1a924-103">Wipe for [Exchange]-managed mobile devices</span><span class="sxs-lookup"><span data-stu-id="1a924-103">Wipe for Exchange-managed mobile devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1a924-104">Microsoft Intune では、Exchange ActiveSync (EAS) と Intune Exchange Connector を使って管理されているモバイル デバイスをワイプまたはリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a924-104">Microsoft Intune allows you to wipe or reset mobile devices that are managed using Exchange ActiveSync (EAS) with the Intune Exchange Connector.</span></span> <span data-ttu-id="1a924-105">次の表に、Exchange ActiveSync で利用できるインベントリからのワイプ機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="1a924-105">The following table describes the wipe capabilities available through Exchange ActiveSync:</span></span>


|<span data-ttu-id="1a924-106">ワイプの種類</span><span class="sxs-lookup"><span data-stu-id="1a924-106">Type of wipe</span></span>|<span data-ttu-id="1a924-107">Windows 8.1 および Windows RT 8.1</span><span class="sxs-lookup"><span data-stu-id="1a924-107">Windows 8.1 and Windows RT 8.1</span></span>|<span data-ttu-id="1a924-108">iOS</span><span class="sxs-lookup"><span data-stu-id="1a924-108">iOS</span></span>|<span data-ttu-id="1a924-109">Android</span><span class="sxs-lookup"><span data-stu-id="1a924-109">Android</span></span>|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|<span data-ttu-id="1a924-110">フル ワイプ</span><span class="sxs-lookup"><span data-stu-id="1a924-110">Full wipe</span></span>|<span data-ttu-id="1a924-111">メール アカウントとキャッシュ済みメールを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a924-111">Removes mail account and cached mail.</span></span>|<span data-ttu-id="1a924-112">出荷時の設定に戻します。</span><span class="sxs-lookup"><span data-stu-id="1a924-112">XFactory reset.</span></span>|<span data-ttu-id="1a924-113">出荷時の設定に戻します。</span><span class="sxs-lookup"><span data-stu-id="1a924-113">Factory reset.</span></span>|
|<span data-ttu-id="1a924-114">選択的なワイプ/電子メール</span><span class="sxs-lookup"><span data-stu-id="1a924-114">Selective wipe/email</span></span>|<span data-ttu-id="1a924-115">電子メール アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a924-115">Removes email account.</span></span>|<span data-ttu-id="1a924-116">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a924-116">Not supported.</span></span>|<span data-ttu-id="1a924-117">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a924-117">Not supported.</span></span>|
|<span data-ttu-id="1a924-118">選択的なワイプ/ポリシー</span><span class="sxs-lookup"><span data-stu-id="1a924-118">Selective wipe/policies</span></span>|<span data-ttu-id="1a924-119">ポリシーの強制は削除されますが、設定は変更されません</span><span class="sxs-lookup"><span data-stu-id="1a924-119">Policy enforcement removed, but settings are not changed</span></span>|<span data-ttu-id="1a924-120">ポリシーの強制は削除されますが、設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="1a924-120">XPolicy enforcement removed, but settings are not changed.</span></span>|<span data-ttu-id="1a924-121">ポリシーの強制は削除されますが、設定は変更されません</span><span class="sxs-lookup"><span data-stu-id="1a924-121">Policy enforcement removed, but settings are not changed.</span></span>|

