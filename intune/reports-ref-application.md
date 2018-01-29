---
title: "アプリケーション | Microsoft Docs"
description: "Intune データ ウェアハウス API にあるエンティティ コレクションのアプリケーション カテゴリのための参照トピック。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 09778d0b7ec208b64f9575713123c725dcd63695
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="reference-for-application-entities"></a><span data-ttu-id="32d93-104">アプリケーション エンティティのリファレンス</span><span class="sxs-lookup"><span data-stu-id="32d93-104">Reference for application entities</span></span>

<span data-ttu-id="32d93-105">**アプリケーション** カテゴリには、次のような情報を追跡記録するモバイル デバイスのエンティティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="32d93-105">The **Application** category contains entities for mobile devices that track information such as:</span></span>

  -  <span data-ttu-id="32d93-106">アプリのバージョン</span><span class="sxs-lookup"><span data-stu-id="32d93-106">Versions of an app</span></span>
  -  <span data-ttu-id="32d93-107">アプリのインストール ソース</span><span class="sxs-lookup"><span data-stu-id="32d93-107">Installation source of an app</span></span>
  -  <span data-ttu-id="32d93-108">アプリを作成した開発者の種類</span><span class="sxs-lookup"><span data-stu-id="32d93-108">Type of developers who created an app</span></span>
  -  <span data-ttu-id="32d93-109">**sidecar** や **desktop** など、アプリの管理対象ソフトウェアの種類</span><span class="sxs-lookup"><span data-stu-id="32d93-109">Managed software types for an app, for example **sidecar** or **desktop**</span></span>
  -  <span data-ttu-id="32d93-110">アプリのボリューム購入プログラム (VPP) 状態</span><span class="sxs-lookup"><span data-stu-id="32d93-110">Volume Purchasing Program (VPP) state of an app</span></span>

## <a name="apprevision"></a><span data-ttu-id="32d93-111">AppRevision</span><span class="sxs-lookup"><span data-stu-id="32d93-111">AppRevision</span></span>

<span data-ttu-id="32d93-112">**AppRevision** エンティティは、アプリのバージョンをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="32d93-112">The **AppRevision** entity lists all the versions of apps.</span></span>

| <span data-ttu-id="32d93-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32d93-113">Property</span></span>  | <span data-ttu-id="32d93-114">説明</span><span class="sxs-lookup"><span data-stu-id="32d93-114">Description</span></span> | <span data-ttu-id="32d93-115">例</span><span class="sxs-lookup"><span data-stu-id="32d93-115">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="32d93-116">AppKey</span><span class="sxs-lookup"><span data-stu-id="32d93-116">AppKey</span></span> |<span data-ttu-id="32d93-117">アプリを示す一意識別子。</span><span class="sxs-lookup"><span data-stu-id="32d93-117">Unique identifier of the App.</span></span> |<span data-ttu-id="32d93-118">123</span><span class="sxs-lookup"><span data-stu-id="32d93-118">123</span></span> |
| <span data-ttu-id="32d93-119">ApplicationId</span><span class="sxs-lookup"><span data-stu-id="32d93-119">ApplicationId</span></span> |<span data-ttu-id="32d93-120">アプリを示す一意識別子 - AppKey に似ていますが、このキーはナチュラルです。</span><span class="sxs-lookup"><span data-stu-id="32d93-120">Unique identifier of the App - similar to AppKey, but this key is a natural.</span></span> |<span data-ttu-id="32d93-121">b66bc706-ffff-7437-0340-032819502773</span><span class="sxs-lookup"><span data-stu-id="32d93-121">b66bc706-ffff-7437-0340-032819502773</span></span> |
| <span data-ttu-id="32d93-122">リビジョン</span><span class="sxs-lookup"><span data-stu-id="32d93-122">Revision</span></span> |<span data-ttu-id="32d93-123">バイナリのアップロード中に管理者が挙げたバージョン。</span><span class="sxs-lookup"><span data-stu-id="32d93-123">The version as mentioned by admin during uploading of the binary.</span></span> |<span data-ttu-id="32d93-124">2</span><span class="sxs-lookup"><span data-stu-id="32d93-124">2</span></span> |
| <span data-ttu-id="32d93-125">タイトル</span><span class="sxs-lookup"><span data-stu-id="32d93-125">Title</span></span> |<span data-ttu-id="32d93-126">アプリのタイトル。</span><span class="sxs-lookup"><span data-stu-id="32d93-126">Title of the app.</span></span> |<span data-ttu-id="32d93-127">Excel</span><span class="sxs-lookup"><span data-stu-id="32d93-127">Excel</span></span> |
| <span data-ttu-id="32d93-128">発行者</span><span class="sxs-lookup"><span data-stu-id="32d93-128">Publisher</span></span> |<span data-ttu-id="32d93-129">アプリの発行者。</span><span class="sxs-lookup"><span data-stu-id="32d93-129">Publisher of the app.</span></span> |<span data-ttu-id="32d93-130">Microsoft</span><span class="sxs-lookup"><span data-stu-id="32d93-130">Microsoft</span></span> |
| <span data-ttu-id="32d93-131">UploadState</span><span class="sxs-lookup"><span data-stu-id="32d93-131">UploadState</span></span> |<span data-ttu-id="32d93-132">アプリのアップロード状態。</span><span class="sxs-lookup"><span data-stu-id="32d93-132">Upload state of the app.</span></span> |<span data-ttu-id="32d93-133">1</span><span class="sxs-lookup"><span data-stu-id="32d93-133">1</span></span> |
| <span data-ttu-id="32d93-134">AppTypeKey</span><span class="sxs-lookup"><span data-stu-id="32d93-134">AppTypeKey</span></span> |<span data-ttu-id="32d93-135">AppType の参照 (次のセクションに説明あり)</span><span class="sxs-lookup"><span data-stu-id="32d93-135">Reference to AppType described in the following section.</span></span> | |
| <span data-ttu-id="32d93-136">VppProgramTypeKey</span><span class="sxs-lookup"><span data-stu-id="32d93-136">VppProgramTypeKey</span></span> |<span data-ttu-id="32d93-137">VppProgramType の参照 (下に説明あり)。</span><span class="sxs-lookup"><span data-stu-id="32d93-137">Reference to VppProgramType described below.</span></span> | |
| <span data-ttu-id="32d93-138">CreationTime</span><span class="sxs-lookup"><span data-stu-id="32d93-138">CreationTime</span></span> |<span data-ttu-id="32d93-139">このリビジョンが作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="32d93-139">The time when this revision was created.</span></span> |<span data-ttu-id="32d93-140">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="32d93-140">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="32d93-141">ModifiedTime</span><span class="sxs-lookup"><span data-stu-id="32d93-141">ModifiedTime</span></span> |<span data-ttu-id="32d93-142">このリビジョンに関連する事項が最後に変更された時刻。</span><span class="sxs-lookup"><span data-stu-id="32d93-142">Last time anything related to this revision was changed.</span></span> |<span data-ttu-id="32d93-143">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="32d93-143">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="32d93-144">Size</span><span class="sxs-lookup"><span data-stu-id="32d93-144">Size</span></span> |<span data-ttu-id="32d93-145">バイナリのサイズ。</span><span class="sxs-lookup"><span data-stu-id="32d93-145">Size of the binary.</span></span> | |
| <span data-ttu-id="32d93-146">StartDateInclusiveUTC</span><span class="sxs-lookup"><span data-stu-id="32d93-146">StartDateInclusiveUTC</span></span> |<span data-ttu-id="32d93-147">このアプリ リビジョンがデータ ウェアハウスで作成されたときの UTC 日時。</span><span class="sxs-lookup"><span data-stu-id="32d93-147">Date and time in UTC when this App revision was created in the data warehouse.</span></span> |<span data-ttu-id="32d93-148">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="32d93-148">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="32d93-149">EndDateExclusiveUTC</span><span class="sxs-lookup"><span data-stu-id="32d93-149">EndDateExclusiveUTC</span></span> |<span data-ttu-id="32d93-150">このアプリ リビジョンが推奨されなくなったときの UTC 日時。</span><span class="sxs-lookup"><span data-stu-id="32d93-150">Date and time in UTC when this app revision became obsolete.</span></span> |<span data-ttu-id="32d93-151">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="32d93-151">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="32d93-152">IsCurrent</span><span class="sxs-lookup"><span data-stu-id="32d93-152">IsCurrent</span></span> |<span data-ttu-id="32d93-153">データ ウェアハウスにおいて、このアプリ バージョンが現行のものであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="32d93-153">Indicates whether this App version is current or not in the data warehouse.</span></span> |<span data-ttu-id="32d93-154">真/偽</span><span class="sxs-lookup"><span data-stu-id="32d93-154">True/False</span></span> |
| <span data-ttu-id="32d93-155">RowLastModifiedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="32d93-155">RowLastModifiedDateTimeUTC</span></span> |<span data-ttu-id="32d93-156">このアプリ バージョンがデータ ウェアハウスで最後に変更されたときの UTC 日時。</span><span class="sxs-lookup"><span data-stu-id="32d93-156">Date and time in UTC when this app version was last modified in the data warehouse.</span></span> |<span data-ttu-id="32d93-157">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="32d93-157">11/23/2016 12:00:00 AM</span></span> |

## <a name="apptypes"></a><span data-ttu-id="32d93-158">AppTypes</span><span class="sxs-lookup"><span data-stu-id="32d93-158">AppTypes</span></span>

<span data-ttu-id="32d93-159">**AppTypes** エンティティは、アプリのインストール ソースを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="32d93-159">The **AppTypes** entity lists the installation source of an app.</span></span>

| <span data-ttu-id="32d93-160">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32d93-160">Property</span></span>  | <span data-ttu-id="32d93-161">説明</span><span class="sxs-lookup"><span data-stu-id="32d93-161">Description</span></span> |
|---------|------------|
| <span data-ttu-id="32d93-162">AppTypeID</span><span class="sxs-lookup"><span data-stu-id="32d93-162">AppTypeID</span></span> |<span data-ttu-id="32d93-163">種類の ID</span><span class="sxs-lookup"><span data-stu-id="32d93-163">Id for the type</span></span> |
| <span data-ttu-id="32d93-164">AppTypeKey</span><span class="sxs-lookup"><span data-stu-id="32d93-164">AppTypeKey</span></span> |<span data-ttu-id="32d93-165">キーの代理キー</span><span class="sxs-lookup"><span data-stu-id="32d93-165">Surrogate key for the key</span></span> |
| <span data-ttu-id="32d93-166">AppTypeName</span><span class="sxs-lookup"><span data-stu-id="32d93-166">AppTypeName</span></span> |<span data-ttu-id="32d93-167">アプリの種類</span><span class="sxs-lookup"><span data-stu-id="32d93-167">App type</span></span> |

### <a name="example"></a><span data-ttu-id="32d93-168">例</span><span class="sxs-lookup"><span data-stu-id="32d93-168">Example</span></span>

| <span data-ttu-id="32d93-169">AppTypeID</span><span class="sxs-lookup"><span data-stu-id="32d93-169">AppTypeID</span></span>  | <span data-ttu-id="32d93-170">名前</span><span class="sxs-lookup"><span data-stu-id="32d93-170">Name</span></span> | <span data-ttu-id="32d93-171">説明</span><span class="sxs-lookup"><span data-stu-id="32d93-171">Description</span></span> |
|---------|------------|--------|
| <span data-ttu-id="32d93-172">0</span><span class="sxs-lookup"><span data-stu-id="32d93-172">0</span></span> |<span data-ttu-id="32d93-173">Android ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="32d93-173">Android store app</span></span> | <span data-ttu-id="32d93-174">Android ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-174">An Android store app.</span></span> |
| <span data-ttu-id="32d93-175">1</span><span class="sxs-lookup"><span data-stu-id="32d93-175">1</span></span> |<span data-ttu-id="32d93-176">Android LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="32d93-176">Android LOB app</span></span> | <span data-ttu-id="32d93-177">Android の基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-177">An Android line-of-business app.</span></span> |
| <span data-ttu-id="32d93-178">2</span><span class="sxs-lookup"><span data-stu-id="32d93-178">2</span></span> |<span data-ttu-id="32d93-179">管理対象 Android ストア アプリ (MAM)</span><span class="sxs-lookup"><span data-stu-id="32d93-179">Managed Android store app (MAM)</span></span> | <span data-ttu-id="32d93-180">管理を有効にしている Android ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-180">An Android store app that has management enabled.</span></span> |
| <span data-ttu-id="32d93-181">3</span><span class="sxs-lookup"><span data-stu-id="32d93-181">3</span></span> |<span data-ttu-id="32d93-182">iOS ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="32d93-182">iOS store app</span></span> | <span data-ttu-id="32d93-183">iOS ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-183">An iOS store app.</span></span> |
| <span data-ttu-id="32d93-184">4</span><span class="sxs-lookup"><span data-stu-id="32d93-184">4</span></span> |<span data-ttu-id="32d93-185">iOS LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="32d93-185">iOS LOB app</span></span> | <span data-ttu-id="32d93-186">iOS の基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-186">An iOS line-of-business app.</span></span> |
| <span data-ttu-id="32d93-187">5</span><span class="sxs-lookup"><span data-stu-id="32d93-187">5</span></span> |<span data-ttu-id="32d93-188">管理対象 iOS ストア アプリ (MAM)</span><span class="sxs-lookup"><span data-stu-id="32d93-188">Managed iOS store app (MAM?)</span></span> | <span data-ttu-id="32d93-189">管理を有効にしている iOS ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-189">An iOSstore app that is management enabled.</span></span> |
| <span data-ttu-id="32d93-190">6</span><span class="sxs-lookup"><span data-stu-id="32d93-190">6</span></span> |<span data-ttu-id="32d93-191">O365 Pro Plus Suite</span><span class="sxs-lookup"><span data-stu-id="32d93-191">O365 Pro Plus Suite</span></span> | <span data-ttu-id="32d93-192">Office 365 Pro Plus Suite for Windows 10。</span><span class="sxs-lookup"><span data-stu-id="32d93-192">The Office 365 Pro Plus Suite for Windows 10.</span></span> |
| <span data-ttu-id="32d93-193">7</span><span class="sxs-lookup"><span data-stu-id="32d93-193">7</span></span> |<span data-ttu-id="32d93-194">Web アプリ</span><span class="sxs-lookup"><span data-stu-id="32d93-194">Web app</span></span> | <span data-ttu-id="32d93-195">Web アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-195">A web app.</span></span> |
| <span data-ttu-id="32d93-196">8</span><span class="sxs-lookup"><span data-stu-id="32d93-196">8</span></span> |<span data-ttu-id="32d93-197">Windows Phone 8.1 ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="32d93-197">Windows Phone 8.1 store app</span></span> | <span data-ttu-id="32d93-198">Windows Phone 8.1 ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-198">A Windows phone 8.1 store app.</span></span> |
| <span data-ttu-id="32d93-199">9</span><span class="sxs-lookup"><span data-stu-id="32d93-199">9</span></span> |<span data-ttu-id="32d93-200">Windows ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="32d93-200">Windows store app</span></span> | <span data-ttu-id="32d93-201">Windows ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-201">A Windows store app.</span></span> |
| <span data-ttu-id="32d93-202">10</span><span class="sxs-lookup"><span data-stu-id="32d93-202">10</span></span> |<span data-ttu-id="32d93-203">Windows LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="32d93-203">Windows LOB apps</span></span> | <span data-ttu-id="32d93-204">Windows AppX 基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-204">A Windows AppX line-of-business app.</span></span> |
| <span data-ttu-id="32d93-205">11</span><span class="sxs-lookup"><span data-stu-id="32d93-205">11</span></span> |<span data-ttu-id="32d93-206">Windows Mobile MSI</span><span class="sxs-lookup"><span data-stu-id="32d93-206">Windows Mobile MSI</span></span> | <span data-ttu-id="32d93-207">MSI の基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-207">An MSI line-of-business app.</span></span> |
| <span data-ttu-id="32d93-208">12</span><span class="sxs-lookup"><span data-stu-id="32d93-208">12</span></span> |<span data-ttu-id="32d93-209">Windows Phone LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="32d93-209">Windows Phone LOB app</span></span> | <span data-ttu-id="32d93-210">Windows Phone 基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="32d93-210">A Windows phone line-of-business app.</span></span> |


## <a name="vppprogramtypes"></a><span data-ttu-id="32d93-211">VppProgramTypes</span><span class="sxs-lookup"><span data-stu-id="32d93-211">VppProgramTypes</span></span>

<span data-ttu-id="32d93-212">**VppProgramTypes** エンティティは、アプリの VPP プログラムの種類を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="32d93-212">The **VppProgramTypes** entity lists possible VPP program types for an app.</span></span>

| <span data-ttu-id="32d93-213">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32d93-213">Property</span></span>  | <span data-ttu-id="32d93-214">説明</span><span class="sxs-lookup"><span data-stu-id="32d93-214">Description</span></span> |
|---------|------------|
| <span data-ttu-id="32d93-215">VppProgramTypeID</span><span class="sxs-lookup"><span data-stu-id="32d93-215">VppProgramTypeID</span></span> | <span data-ttu-id="32d93-216">種類の ID。</span><span class="sxs-lookup"><span data-stu-id="32d93-216">ID for the type.</span></span> |
| <span data-ttu-id="32d93-217">VppProgramTypeKey</span><span class="sxs-lookup"><span data-stu-id="32d93-217">VppProgramTypeKey</span></span> | <span data-ttu-id="32d93-218">キーの代理キー。</span><span class="sxs-lookup"><span data-stu-id="32d93-218">Surrogate key for the key.</span></span> |
| <span data-ttu-id="32d93-219">VppProgramTypeName</span><span class="sxs-lookup"><span data-stu-id="32d93-219">VppProgramTypeName</span></span> | <span data-ttu-id="32d93-220">VPP プログラムの種類。</span><span class="sxs-lookup"><span data-stu-id="32d93-220">VPP Program type.</span></span> |

### <a name="example"></a><span data-ttu-id="32d93-221">例</span><span class="sxs-lookup"><span data-stu-id="32d93-221">Example</span></span>

| <span data-ttu-id="32d93-222">VppProgramID</span><span class="sxs-lookup"><span data-stu-id="32d93-222">VppProgramID</span></span>  | <span data-ttu-id="32d93-223">名前</span><span class="sxs-lookup"><span data-stu-id="32d93-223">Name</span></span> | <span data-ttu-id="32d93-224">説明</span><span class="sxs-lookup"><span data-stu-id="32d93-224">Description</span></span> |
|---------|------------|--------|
| <span data-ttu-id="32d93-225">3DDA2474-470B-4503-9830-2665C21C1945</span><span class="sxs-lookup"><span data-stu-id="32d93-225">3DDA2474-470B-4503-9830-2665C21C1945</span></span> | <span data-ttu-id="32d93-226">Microsoft</span><span class="sxs-lookup"><span data-stu-id="32d93-226">Microsoft</span></span> | <span data-ttu-id="32d93-227">Microsoft の VPP プログラム。</span><span class="sxs-lookup"><span data-stu-id="32d93-227">Microsoft's VPP program.</span></span> |
| <span data-ttu-id="32d93-228">00000000-0000-0000-0000-000000000000</span><span class="sxs-lookup"><span data-stu-id="32d93-228">00000000-0000-0000-0000-000000000000</span></span> | <span data-ttu-id="32d93-229">まだ利用できません</span><span class="sxs-lookup"><span data-stu-id="32d93-229">Not Yet Available</span></span> | <span data-ttu-id="32d93-230">既定値、VPP なし。</span><span class="sxs-lookup"><span data-stu-id="32d93-230">Default value, No VPP.</span></span> |
| <span data-ttu-id="32d93-231">B54814E0-68EA-4BA4-8088-B5AAB58E737B</span><span class="sxs-lookup"><span data-stu-id="32d93-231">B54814E0-68EA-4BA4-8088-B5AAB58E737B</span></span> | <span data-ttu-id="32d93-232">Apple</span><span class="sxs-lookup"><span data-stu-id="32d93-232">Apple</span></span> | <span data-ttu-id="32d93-233">Apple の VPP プログラム。</span><span class="sxs-lookup"><span data-stu-id="32d93-233">Apple's VPP program.</span></span> |



## <a name="applicationinventory"></a><span data-ttu-id="32d93-234">ApplicationInventory</span><span class="sxs-lookup"><span data-stu-id="32d93-234">ApplicationInventory</span></span>

<span data-ttu-id="32d93-235">**ApplicationInventory** エンティティには、インベントリ回収時にデバイスで検出されたアプリケーションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="32d93-235">The **ApplicationInventory** entity lists the applications found on the device at the time of inventory collection.</span></span>

| <span data-ttu-id="32d93-236">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32d93-236">Property</span></span>  | <span data-ttu-id="32d93-237">説明</span><span class="sxs-lookup"><span data-stu-id="32d93-237">Description</span></span> |
|---------|------------|
| <span data-ttu-id="32d93-238">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="32d93-238">DeviceKey</span></span> | <span data-ttu-id="32d93-239">これは、Intune デバイス ID が含まれるデバイス テーブルの参照です。</span><span class="sxs-lookup"><span data-stu-id="32d93-239">This is a reference to the Device table which contains the Intune device ID.</span></span> |
| <span data-ttu-id="32d93-240">DateKey</span><span class="sxs-lookup"><span data-stu-id="32d93-240">DateKey</span></span> | <span data-ttu-id="32d93-241">日付テーブルの参照であり、インベントリの日を示します。</span><span class="sxs-lookup"><span data-stu-id="32d93-241">Reference to date table indicating the day of inventory.</span></span> |
| <span data-ttu-id="32d93-242">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="32d93-242">ApplicationName</span></span> | <span data-ttu-id="32d93-243">アプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="32d93-243">The application name.</span></span> |
| <span data-ttu-id="32d93-244">ApplicationVersion</span><span class="sxs-lookup"><span data-stu-id="32d93-244">ApplicationVersion</span></span> | <span data-ttu-id="32d93-245">アプリケーションのバージョン。</span><span class="sxs-lookup"><span data-stu-id="32d93-245">Version of the application.</span></span> |
| <span data-ttu-id="32d93-246">BundleSize</span><span class="sxs-lookup"><span data-stu-id="32d93-246">BundleSize</span></span> | <span data-ttu-id="32d93-247">アプリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="32d93-247">The size of the app in bytes.</span></span> |

## <a name="mobileappinstallstate"></a><span data-ttu-id="32d93-248">MobileAppInstallState</span><span class="sxs-lookup"><span data-stu-id="32d93-248">MobileAppInstallState</span></span>

<span data-ttu-id="32d93-249">**MobileAppInstallState** エンティティは、デバイス、ユーザーまたはその両方を含むグループに割り当てられた後のモバイル アプリケーションのインストール状態を表します。</span><span class="sxs-lookup"><span data-stu-id="32d93-249">The **MobileAppInstallState** entity represents the install state for a mobile application after it has been assigned to a group containing devices, users or both.</span></span>

| <span data-ttu-id="32d93-250">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32d93-250">Property</span></span> | <span data-ttu-id="32d93-251">説明</span><span class="sxs-lookup"><span data-stu-id="32d93-251">Description</span></span> |
|---|---|
| <span data-ttu-id="32d93-252">AppInstallStateKey</span><span class="sxs-lookup"><span data-stu-id="32d93-252">AppInstallStateKey</span></span> | <span data-ttu-id="32d93-253">アカウントにおけるアプリのインストール状態の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="32d93-253">The unique ID of the app install state for your account.</span></span> |
| <span data-ttu-id="32d93-254">AppInstallState</span><span class="sxs-lookup"><span data-stu-id="32d93-254">AppInstallState</span></span> | <span data-ttu-id="32d93-255">アプリのインストール状態の列挙値。</span><span class="sxs-lookup"><span data-stu-id="32d93-255">Enum value of the app install state.</span></span> |
| <span data-ttu-id="32d93-256">AppInstallStateName</span><span class="sxs-lookup"><span data-stu-id="32d93-256">AppInstallStateName</span></span> | <span data-ttu-id="32d93-257">アプリのインストール状態の名前。</span><span class="sxs-lookup"><span data-stu-id="32d93-257">Name of the app install state.</span></span> |

## <a name="mobileappdeviceuserinstallstatus"></a><span data-ttu-id="32d93-258">MobileAppDeviceUserInstallStatus</span><span class="sxs-lookup"><span data-stu-id="32d93-258">MobileAppDeviceUserInstallStatus</span></span>

<span data-ttu-id="32d93-259">**MobileAppDeviceUserInstallStatus** は、特定のデバイスとユーザーのモバイル アプリのインストール状態を表します。</span><span class="sxs-lookup"><span data-stu-id="32d93-259">The **MobileAppDeviceUserInstallStatus** represents a mobile app install status for a given device and user.</span></span>


|      <span data-ttu-id="32d93-260">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32d93-260">Property</span></span>      |                                                         <span data-ttu-id="32d93-261">説明</span><span class="sxs-lookup"><span data-stu-id="32d93-261">Description</span></span>                                                         |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------|
|      <span data-ttu-id="32d93-262">DateKey</span><span class="sxs-lookup"><span data-stu-id="32d93-262">DateKey</span></span>       |                                  <span data-ttu-id="32d93-263">アプリのインストール状態が記録されたときの日付のキー。</span><span class="sxs-lookup"><span data-stu-id="32d93-263">Key of the date when the app install status was recorded.</span></span>                                  |
|       <span data-ttu-id="32d93-264">AppKey</span><span class="sxs-lookup"><span data-stu-id="32d93-264">AppKey</span></span>       |                             <span data-ttu-id="32d93-265">AppRevision のインスタンスの識別に使用する、モバイル アプリのキー。</span><span class="sxs-lookup"><span data-stu-id="32d93-265">Key of the mobile app used to identify an instance of AppRevision.</span></span>                              |
|     <span data-ttu-id="32d93-266">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="32d93-266">DeviceKey</span></span>      |                              <span data-ttu-id="32d93-267">Device のインスタンスの識別に使用する、対象デバイスのキー。</span><span class="sxs-lookup"><span data-stu-id="32d93-267">Key of a targeted device used to identify an instance of Device.</span></span>                               |
|      <span data-ttu-id="32d93-268">UserKey</span><span class="sxs-lookup"><span data-stu-id="32d93-268">UserKey</span></span>       |                                <span data-ttu-id="32d93-269">User のインスタンスの識別に使用する、対象ユーザーのキー。</span><span class="sxs-lookup"><span data-stu-id="32d93-269">Key of a targeted user used to identify an instance of User.</span></span>                                 |
| <span data-ttu-id="32d93-270">AppInstallStateKey</span><span class="sxs-lookup"><span data-stu-id="32d93-270">AppInstallStateKey</span></span> |                     <span data-ttu-id="32d93-271">MobileAppInstallState のインスタンスの識別に使用する、アプリのインストール状態のキー。</span><span class="sxs-lookup"><span data-stu-id="32d93-271">Key of the app install state used to identify an instance of MobileAppInstallState.</span></span>                     |
|     <span data-ttu-id="32d93-272">エラー コード</span><span class="sxs-lookup"><span data-stu-id="32d93-272">ErrorCode</span></span>      | <span data-ttu-id="32d93-273">アプリのインストーラー、モバイル プラットフォーム、またはアプリのインストールと関わりがあるサービスによって返されるエラー コード。</span><span class="sxs-lookup"><span data-stu-id="32d93-273">The error code returned by the app installer, the mobile platform or the service pertaining to the installation of the app.</span></span> |

