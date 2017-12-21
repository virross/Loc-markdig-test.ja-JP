---
title: "ユーザー デバイスの関連付け - Intune データ ウェアハウス | Microsoft Docs"
description: "Intune のデータ ウェアハウス API の変更一覧。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c47455b0139f7451796257a77859cbd9899a7dd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="user-device-association"></a><span data-ttu-id="5070f-104">ユーザー デバイスの関連付け</span><span class="sxs-lookup"><span data-stu-id="5070f-104">User Device Association</span></span>

<span data-ttu-id="5070f-105">**UserDeviceAssociation** エンティティには、組織内のユーザー デバイスの関連付けが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5070f-105">The **UserDeviceAssociation** entity contains user device associations in your organization.</span></span>

| <span data-ttu-id="5070f-106">名前</span><span class="sxs-lookup"><span data-stu-id="5070f-106">Name</span></span>               | <span data-ttu-id="5070f-107">説明</span><span class="sxs-lookup"><span data-stu-id="5070f-107">Description</span></span>                                                                                      | <span data-ttu-id="5070f-108">例</span><span class="sxs-lookup"><span data-stu-id="5070f-108">Example</span></span>                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| <span data-ttu-id="5070f-109">UserKey</span><span class="sxs-lookup"><span data-stu-id="5070f-109">UserKey</span></span>            | <span data-ttu-id="5070f-110">データ ウェアハウス内のユーザーを示す一意識別子</span><span class="sxs-lookup"><span data-stu-id="5070f-110">Unique identifier of the user in the data warehouse.</span></span> <span data-ttu-id="5070f-111">(代理キー)。</span><span class="sxs-lookup"><span data-stu-id="5070f-111">(Surrogate key).</span></span>                              | <span data-ttu-id="5070f-112">123</span><span class="sxs-lookup"><span data-stu-id="5070f-112">123</span></span>                    |
| <span data-ttu-id="5070f-113">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="5070f-113">DeviceKey</span></span>          | <span data-ttu-id="5070f-114">データ ウェアハウス内のデバイスを示す一意識別子。</span><span class="sxs-lookup"><span data-stu-id="5070f-114">Unique identifier of the device in the data warehouse.</span></span>                                            | <span data-ttu-id="5070f-115">123</span><span class="sxs-lookup"><span data-stu-id="5070f-115">123</span></span>                    |
| <span data-ttu-id="5070f-116">CreatedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="5070f-116">CreatedDateTimeUTC</span></span> | <span data-ttu-id="5070f-117">ユーザー デバイスの関連付けが作成されたときの日時。</span><span class="sxs-lookup"><span data-stu-id="5070f-117">Date and time when the user device association was created.</span></span> <span data-ttu-id="5070f-118">UTC 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="5070f-118">Uses UTC format.</span></span>                                | <span data-ttu-id="5070f-119">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="5070f-119">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="5070f-120">IsDeleted</span><span class="sxs-lookup"><span data-stu-id="5070f-120">IsDeleted</span></span>          | <span data-ttu-id="5070f-121">ユーザーがそのデバイスを登録解除し、その関連付けが最新でなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5070f-121">Indicates that the user unenrolled that device, and that the association is not current anymore.</span></span> | <span data-ttu-id="5070f-122">真/偽</span><span class="sxs-lookup"><span data-stu-id="5070f-122">True/False</span></span>             |
| <span data-ttu-id="5070f-123">EndedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="5070f-123">EndedDateTimeUTC</span></span>   | <span data-ttu-id="5070f-124">IsDeleted が **True** に変更されたときの日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="5070f-124">Date and time in UTC when IsDeleted changed to **True**.</span></span>                                              | <span data-ttu-id="5070f-125">06/23/2017 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="5070f-125">06/23/2017 12:00:00 AM</span></span> |
