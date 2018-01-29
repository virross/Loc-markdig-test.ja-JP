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
ms.openlocfilehash: cc8d775eec58d55eec83ccdb6687d0451d3a4dfc
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="user-device-association"></a><span data-ttu-id="cec7e-104">ユーザー デバイスの関連付け</span><span class="sxs-lookup"><span data-stu-id="cec7e-104">User Device Association</span></span>

<span data-ttu-id="cec7e-105">**UserDeviceAssociation** エンティティには、組織内のユーザー デバイスの関連付けが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cec7e-105">The **UserDeviceAssociation** entity contains user device associations in your organization.</span></span>


|        <span data-ttu-id="cec7e-106">名前</span><span class="sxs-lookup"><span data-stu-id="cec7e-106">Name</span></span>        |                                           <span data-ttu-id="cec7e-107">説明</span><span class="sxs-lookup"><span data-stu-id="cec7e-107">Description</span></span>                                            |        <span data-ttu-id="cec7e-108">例</span><span class="sxs-lookup"><span data-stu-id="cec7e-108">Example</span></span>         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      <span data-ttu-id="cec7e-109">UserKey</span><span class="sxs-lookup"><span data-stu-id="cec7e-109">UserKey</span></span>       |              <span data-ttu-id="cec7e-110">データ ウェアハウス内のユーザーを示す一意識別子</span><span class="sxs-lookup"><span data-stu-id="cec7e-110">Unique identifier of the user in the data warehouse.</span></span> <span data-ttu-id="cec7e-111">(代理キー)。</span><span class="sxs-lookup"><span data-stu-id="cec7e-111">(Surrogate key).</span></span>               |          <span data-ttu-id="cec7e-112">123</span><span class="sxs-lookup"><span data-stu-id="cec7e-112">123</span></span>           |
|     <span data-ttu-id="cec7e-113">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="cec7e-113">DeviceKey</span></span>      |                      <span data-ttu-id="cec7e-114">データ ウェアハウス内のデバイスを示す一意識別子。</span><span class="sxs-lookup"><span data-stu-id="cec7e-114">Unique identifier of the device in the data warehouse.</span></span>                      |          <span data-ttu-id="cec7e-115">123</span><span class="sxs-lookup"><span data-stu-id="cec7e-115">123</span></span>           |
| <span data-ttu-id="cec7e-116">CreatedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="cec7e-116">CreatedDateTimeUTC</span></span> |           <span data-ttu-id="cec7e-117">ユーザー デバイスの関連付けが作成されたときの日時。</span><span class="sxs-lookup"><span data-stu-id="cec7e-117">Date and time when the user device association was created.</span></span> <span data-ttu-id="cec7e-118">UTC 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="cec7e-118">Uses UTC format.</span></span>           | <span data-ttu-id="cec7e-119">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="cec7e-119">11/23/2016 12:00:00 AM</span></span> |
|     <span data-ttu-id="cec7e-120">IsDeleted</span><span class="sxs-lookup"><span data-stu-id="cec7e-120">IsDeleted</span></span>      | <span data-ttu-id="cec7e-121">ユーザーがそのデバイスを登録解除し、その関連付けが最新でなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="cec7e-121">Indicates that the user unenrolled that device, and that the association is not current anymore.</span></span> |       <span data-ttu-id="cec7e-122">真/偽</span><span class="sxs-lookup"><span data-stu-id="cec7e-122">True/False</span></span>       |
|  <span data-ttu-id="cec7e-123">EndedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="cec7e-123">EndedDateTimeUTC</span></span>  |              <span data-ttu-id="cec7e-124">IsDeleted が <strong>True</strong> に変更されたときの日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="cec7e-124">Date and time in UTC when IsDeleted changed to <strong>True</strong>.</span></span>               | <span data-ttu-id="cec7e-125">06/23/2017 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="cec7e-125">06/23/2017 12:00:00 AM</span></span> |

