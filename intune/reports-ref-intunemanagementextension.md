---
title: "IntuneManagementExtension エンティティ | Microsoft Docs"
description: "Intune データ ウェアハウス API にあるエンティティ コレクションの IntuneManagementExtension エンティティ カテゴリのための参照トピック。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 76b7b58a7d530ae0c4b60891fe3b1fb1108f2ee8
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="reference-for-intune-management-extension"></a><span data-ttu-id="da664-104">Intune 管理拡張のリファレンス</span><span class="sxs-lookup"><span data-stu-id="da664-104">Reference for Intune Management Extension</span></span>

<span data-ttu-id="da664-105">**IntuneManagementExtension** カテゴリには、次のような情報を追跡するモバイル デバイスのエンティティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="da664-105">The **IntuneManagementExtension** category contains entities for mobile devices that track information such as:</span></span>

  -  <span data-ttu-id="da664-106">IntuneManagementExtension のバージョン</span><span class="sxs-lookup"><span data-stu-id="da664-106">Versions of an IntuneManagementExtension</span></span>
  -  <span data-ttu-id="da664-107">IntuneManagementExtension のインストール状態</span><span class="sxs-lookup"><span data-stu-id="da664-107">Installation status of an IntuneManagementExtension</span></span>

## <a name="intunemanagementextensionversion"></a><span data-ttu-id="da664-108">IntuneManagementExtensionVersion</span><span class="sxs-lookup"><span data-stu-id="da664-108">IntuneManagementExtensionVersion</span></span>

<span data-ttu-id="da664-109">**IntuneManagementExtensionVersion** エンティティは、IntuneManagementExtension で使用されるすべてのバージョンを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="da664-109">The **IntuneManagementExtensionVersion** entity lists all the versions used by IntuneManagementExtension.</span></span>

| <span data-ttu-id="da664-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="da664-110">Property</span></span>  | <span data-ttu-id="da664-111">説明</span><span class="sxs-lookup"><span data-stu-id="da664-111">Description</span></span> | <span data-ttu-id="da664-112">例</span><span class="sxs-lookup"><span data-stu-id="da664-112">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="da664-113">ExtensionVersionKey</span><span class="sxs-lookup"><span data-stu-id="da664-113">ExtensionVersionKey</span></span> |<span data-ttu-id="da664-114">IntuneManagementExtension バージョンの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="da664-114">Unique identifier of the IntuneManagementExtension version.</span></span> | <span data-ttu-id="da664-115">1</span><span class="sxs-lookup"><span data-stu-id="da664-115">1</span></span> |
| <span data-ttu-id="da664-116">ExtensionVersion</span><span class="sxs-lookup"><span data-stu-id="da664-116">ExtensionVersion</span></span> |<span data-ttu-id="da664-117">4 桁のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="da664-117">The 4 digit version number.</span></span> |<span data-ttu-id="da664-118">1.0.2.0</span><span class="sxs-lookup"><span data-stu-id="da664-118">1.0.2.0</span></span> |

## <a name="intunemanagementextensionhealthstate"></a><span data-ttu-id="da664-119">IntuneManagementExtensionHealthState</span><span class="sxs-lookup"><span data-stu-id="da664-119">IntuneManagementExtensionHealthState</span></span>

<span data-ttu-id="da664-120">**IntuneManagementExtensionHealthState** は、IntuneManagementExtension の考えられるすべてのヘルス状態を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="da664-120">The **IntuneManagementExtensionHealthState** lists all possible health states of the IntuneManagementExtension.</span></span>

| <span data-ttu-id="da664-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="da664-121">Property</span></span>  | <span data-ttu-id="da664-122">説明</span><span class="sxs-lookup"><span data-stu-id="da664-122">Description</span></span> | <span data-ttu-id="da664-123">例</span><span class="sxs-lookup"><span data-stu-id="da664-123">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="da664-124">ExtensionStateKey</span><span class="sxs-lookup"><span data-stu-id="da664-124">ExtensionStateKey</span></span> |<span data-ttu-id="da664-125">ヘルス状態の一意識別子。</span><span class="sxs-lookup"><span data-stu-id="da664-125">Unique identifier of health state.</span></span> | <span data-ttu-id="da664-126">2</span><span class="sxs-lookup"><span data-stu-id="da664-126">2</span></span> |
| <span data-ttu-id="da664-127">ExtensionState</span><span class="sxs-lookup"><span data-stu-id="da664-127">ExtensionState</span></span> |<span data-ttu-id="da664-128">IntuneManagementExtension のヘルス状態。</span><span class="sxs-lookup"><span data-stu-id="da664-128">Health state of a IntuneManagementExtension.</span></span> | <span data-ttu-id="da664-129">Healthy</span><span class="sxs-lookup"><span data-stu-id="da664-129">Healthy</span></span> |

## <a name="intunemanagementextension"></a><span data-ttu-id="da664-130">IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="da664-130">IntuneManagementExtension</span></span>

<span data-ttu-id="da664-131">**IntuneManagementExtension** は、1 日あたりの各 Windows 10 デバイスでの IntuneManagementExtension ヘルスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="da664-131">The **IntuneManagementExtension** lists the IntuneManagementExtension health on each Windows 10 device per day.</span></span>
<span data-ttu-id="da664-132">過去 60 日間のデータが保持されます。</span><span class="sxs-lookup"><span data-stu-id="da664-132">The data is retained for the last 60 days.</span></span> 


|      <span data-ttu-id="da664-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="da664-133">Property</span></span>       |                         <span data-ttu-id="da664-134">説明</span><span class="sxs-lookup"><span data-stu-id="da664-134">Description</span></span>                         | <span data-ttu-id="da664-135">例</span><span class="sxs-lookup"><span data-stu-id="da664-135">Example</span></span> |
|---------------------|-------------------------------------------------------------|---------|
|       <span data-ttu-id="da664-136">DateKey</span><span class="sxs-lookup"><span data-stu-id="da664-136">DateKey</span></span>       |               <span data-ttu-id="da664-137">日付の一意識別子。</span><span class="sxs-lookup"><span data-stu-id="da664-137">Unique identifier of the Date.</span></span>                |   <span data-ttu-id="da664-138">123</span><span class="sxs-lookup"><span data-stu-id="da664-138">123</span></span>   |
|      <span data-ttu-id="da664-139">TenantKey</span><span class="sxs-lookup"><span data-stu-id="da664-139">TenantKey</span></span>      |              <span data-ttu-id="da664-140">テナントの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="da664-140">Unique identifier of the Tenant.</span></span>               |   <span data-ttu-id="da664-141">456</span><span class="sxs-lookup"><span data-stu-id="da664-141">456</span></span>   |
|      <span data-ttu-id="da664-142">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="da664-142">DeviceKey</span></span>      |              <span data-ttu-id="da664-143">デバイスの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="da664-143">Unique identifier of the Device.</span></span>               |   <span data-ttu-id="da664-144">789</span><span class="sxs-lookup"><span data-stu-id="da664-144">789</span></span>   |
| <span data-ttu-id="da664-145">ExtensionVersionKey</span><span class="sxs-lookup"><span data-stu-id="da664-145">ExtensionVersionKey</span></span> | <span data-ttu-id="da664-146">IntuneManagementExtension バージョンの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="da664-146">Unique identifier of the IntuneManagementExtension version.</span></span> |    <span data-ttu-id="da664-147">1</span><span class="sxs-lookup"><span data-stu-id="da664-147">1</span></span>    |
|  <span data-ttu-id="da664-148">ExtensionStateKey</span><span class="sxs-lookup"><span data-stu-id="da664-148">ExtensionStateKey</span></span>  |             <span data-ttu-id="da664-149">ヘルス状態の一意識別子。</span><span class="sxs-lookup"><span data-stu-id="da664-149">Unique identifier of health state.</span></span>              |    <span data-ttu-id="da664-150">2</span><span class="sxs-lookup"><span data-stu-id="da664-150">2</span></span>    |

