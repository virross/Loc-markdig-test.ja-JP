---
title: "日付 - Intune データ ウェアハウス | Microsoft Docs"
description: "Intune データ ウェアハウス API のエンティティ コレクションの日付カテゴリに関するリファレンス トピック。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6B4BC650-62F7-4049-9DE4-CDECB579B58F
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93d0f08697c8ee17ff44d599cb7b1bb262daa7ee
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-date-entity"></a><span data-ttu-id="59156-104">Date エンティティのリファレンス</span><span class="sxs-lookup"><span data-stu-id="59156-104">Reference for Date entity</span></span>

<span data-ttu-id="59156-105">**日付**カテゴリには、データ モデルの日付参照の定義に使用される **Date** エンティティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="59156-105">The **Date** category contains the **Date** entity used to define date references in the data model.</span></span>

<span data-ttu-id="59156-106">**日付**</span><span class="sxs-lookup"><span data-stu-id="59156-106">**Date**</span></span>

<span data-ttu-id="59156-107">**Date** エンティティは、複数のデータ ウェアハウス エンティティ全体で参照される日付を示します。</span><span class="sxs-lookup"><span data-stu-id="59156-107">The **Date** entity represents dates that are referenced across multiple data warehouse entities.</span></span>

| <span data-ttu-id="59156-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="59156-108">Property</span></span>  | <span data-ttu-id="59156-109">説明</span><span class="sxs-lookup"><span data-stu-id="59156-109">Description</span></span> | <span data-ttu-id="59156-110">例</span><span class="sxs-lookup"><span data-stu-id="59156-110">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="59156-111">DateKey</span><span class="sxs-lookup"><span data-stu-id="59156-111">DateKey</span></span> | <span data-ttu-id="59156-112">データ ウェアハウス内のこの日付を示す一意識別子。</span><span class="sxs-lookup"><span data-stu-id="59156-112">Unique identifier for this date in the data warehouse.</span></span> | <span data-ttu-id="59156-113">20160703</span><span class="sxs-lookup"><span data-stu-id="59156-113">20160703</span></span> |
| <span data-ttu-id="59156-114">FullDate</span><span class="sxs-lookup"><span data-stu-id="59156-114">FullDate</span></span> | <span data-ttu-id="59156-115">この日付を完全な日時形式で表した日付。</span><span class="sxs-lookup"><span data-stu-id="59156-115">This date represented in full Date/Time format.</span></span> | <span data-ttu-id="59156-116">7/3/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="59156-116">7/3/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="59156-117">DayOfWeek</span><span class="sxs-lookup"><span data-stu-id="59156-117">DayOfWeek</span></span> | <span data-ttu-id="59156-118">曜日</span><span class="sxs-lookup"><span data-stu-id="59156-118">Day of week</span></span> | <span data-ttu-id="59156-119">1</span><span class="sxs-lookup"><span data-stu-id="59156-119">1</span></span> |
| <span data-ttu-id="59156-120">DayOfMonth</span><span class="sxs-lookup"><span data-stu-id="59156-120">DayOfMonth</span></span> | <span data-ttu-id="59156-121">月の日付</span><span class="sxs-lookup"><span data-stu-id="59156-121">Day of month</span></span> | <span data-ttu-id="59156-122">3</span><span class="sxs-lookup"><span data-stu-id="59156-122">3</span></span> |
| <span data-ttu-id="59156-123">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="59156-123">DayOfYear</span></span> | <span data-ttu-id="59156-124">年の通算日</span><span class="sxs-lookup"><span data-stu-id="59156-124">Day of year</span></span> | <span data-ttu-id="59156-125">185</span><span class="sxs-lookup"><span data-stu-id="59156-125">185</span></span> |
| <span data-ttu-id="59156-126">WeekOfYear</span><span class="sxs-lookup"><span data-stu-id="59156-126">WeekOfYear</span></span> | <span data-ttu-id="59156-127">年の通算週</span><span class="sxs-lookup"><span data-stu-id="59156-127">Week of year</span></span> | <span data-ttu-id="59156-128">28</span><span class="sxs-lookup"><span data-stu-id="59156-128">28</span></span> |
| <span data-ttu-id="59156-129">MonthOfYear</span><span class="sxs-lookup"><span data-stu-id="59156-129">MonthOfYear</span></span> | <span data-ttu-id="59156-130">月</span><span class="sxs-lookup"><span data-stu-id="59156-130">Month of the year</span></span> | <span data-ttu-id="59156-131">7</span><span class="sxs-lookup"><span data-stu-id="59156-131">7</span></span> |
| <span data-ttu-id="59156-132">CalendarQuarter</span><span class="sxs-lookup"><span data-stu-id="59156-132">CalendarQuarter</span></span> | <span data-ttu-id="59156-133">カレンダーの四半期</span><span class="sxs-lookup"><span data-stu-id="59156-133">Calendar quarter</span></span> | <span data-ttu-id="59156-134">3</span><span class="sxs-lookup"><span data-stu-id="59156-134">3</span></span> |
| <span data-ttu-id="59156-135">CalendarYear</span><span class="sxs-lookup"><span data-stu-id="59156-135">CalendarYear</span></span> | <span data-ttu-id="59156-136">カレンダーの年</span><span class="sxs-lookup"><span data-stu-id="59156-136">Calendar year</span></span> | <span data-ttu-id="59156-137">2016</span><span class="sxs-lookup"><span data-stu-id="59156-137">2016</span></span> |
| <span data-ttu-id="59156-138">DateKey</span><span class="sxs-lookup"><span data-stu-id="59156-138">DateKey</span></span> | <span data-ttu-id="59156-139">データ ウェアハウス内のこの日付を示す一意識別子。</span><span class="sxs-lookup"><span data-stu-id="59156-139">Unique identifier for this date in the data warehouse.</span></span> | <span data-ttu-id="59156-140">20160703</span><span class="sxs-lookup"><span data-stu-id="59156-140">20160703</span></span> |
| <span data-ttu-id="59156-141">FullDate</span><span class="sxs-lookup"><span data-stu-id="59156-141">FullDate</span></span> | <span data-ttu-id="59156-142">この日付を完全な日時形式で表した日付。</span><span class="sxs-lookup"><span data-stu-id="59156-142">This date represented in full Date/Time format.</span></span> | <span data-ttu-id="59156-143">7/3/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="59156-143">7/3/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="59156-144">DayOfWeek</span><span class="sxs-lookup"><span data-stu-id="59156-144">DayOfWeek</span></span> | <span data-ttu-id="59156-145">曜日</span><span class="sxs-lookup"><span data-stu-id="59156-145">Day of week</span></span> | <span data-ttu-id="59156-146">1</span><span class="sxs-lookup"><span data-stu-id="59156-146">1</span></span> |
| <span data-ttu-id="59156-147">DayOfMonth</span><span class="sxs-lookup"><span data-stu-id="59156-147">DayOfMonth</span></span> | <span data-ttu-id="59156-148">月の日付</span><span class="sxs-lookup"><span data-stu-id="59156-148">Day of month</span></span> | <span data-ttu-id="59156-149">3</span><span class="sxs-lookup"><span data-stu-id="59156-149">3</span></span> |
| <span data-ttu-id="59156-150">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="59156-150">DayOfYear</span></span> | <span data-ttu-id="59156-151">年の通算日</span><span class="sxs-lookup"><span data-stu-id="59156-151">Day of year</span></span> | <span data-ttu-id="59156-152">185</span><span class="sxs-lookup"><span data-stu-id="59156-152">185</span></span> |
| <span data-ttu-id="59156-153">WeekOfYear</span><span class="sxs-lookup"><span data-stu-id="59156-153">WeekOfYear</span></span> | <span data-ttu-id="59156-154">年の通算週</span><span class="sxs-lookup"><span data-stu-id="59156-154">Week of year</span></span> | <span data-ttu-id="59156-155">28</span><span class="sxs-lookup"><span data-stu-id="59156-155">28</span></span> |
| <span data-ttu-id="59156-156">MonthOfYear</span><span class="sxs-lookup"><span data-stu-id="59156-156">MonthOfYear</span></span> | <span data-ttu-id="59156-157">月</span><span class="sxs-lookup"><span data-stu-id="59156-157">Month of the year</span></span> | <span data-ttu-id="59156-158">7</span><span class="sxs-lookup"><span data-stu-id="59156-158">7</span></span> |
| <span data-ttu-id="59156-159">CalendarQuarter</span><span class="sxs-lookup"><span data-stu-id="59156-159">CalendarQuarter</span></span> | <span data-ttu-id="59156-160">カレンダーの四半期</span><span class="sxs-lookup"><span data-stu-id="59156-160">Calendar quarter</span></span> | <span data-ttu-id="59156-161">3</span><span class="sxs-lookup"><span data-stu-id="59156-161">3</span></span> |
| <span data-ttu-id="59156-162">CalendarYear</span><span class="sxs-lookup"><span data-stu-id="59156-162">CalendarYear</span></span> | <span data-ttu-id="59156-163">カレンダーの年</span><span class="sxs-lookup"><span data-stu-id="59156-163">Calendar year</span></span> | <span data-ttu-id="59156-164">2016</span><span class="sxs-lookup"><span data-stu-id="59156-164">2016</span></span> |
