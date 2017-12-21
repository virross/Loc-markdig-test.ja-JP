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
ms.openlocfilehash: e80758f0fc96394a4f1c474037b7584fa39b1678
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-application-entities"></a><span data-ttu-id="97b31-104">アプリケーション エンティティのリファレンス</span><span class="sxs-lookup"><span data-stu-id="97b31-104">Reference for application entities</span></span>

<span data-ttu-id="97b31-105">**アプリケーション** カテゴリには、次のような情報を追跡記録するモバイル デバイスのエンティティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="97b31-105">The **Application** category contains entities for mobile devices that track information such as:</span></span>

  -  <span data-ttu-id="97b31-106">アプリのバージョン</span><span class="sxs-lookup"><span data-stu-id="97b31-106">Versions of an app</span></span>
  -  <span data-ttu-id="97b31-107">アプリのインストール ソース</span><span class="sxs-lookup"><span data-stu-id="97b31-107">Installation source of an app</span></span>
  -  <span data-ttu-id="97b31-108">アプリを作成した開発者の種類</span><span class="sxs-lookup"><span data-stu-id="97b31-108">Type of developers who created an app</span></span>
  -  <span data-ttu-id="97b31-109">**sidecar** や **desktop** など、アプリの管理対象ソフトウェアの種類</span><span class="sxs-lookup"><span data-stu-id="97b31-109">Managed software types for an app, for example **sidecar** or **desktop**</span></span>
  -  <span data-ttu-id="97b31-110">アプリのボリューム購入プログラム (VPP) 状態</span><span class="sxs-lookup"><span data-stu-id="97b31-110">Volume Purchasing Program (VPP) state of an app</span></span>

## <a name="apprevision"></a><span data-ttu-id="97b31-111">AppRevision</span><span class="sxs-lookup"><span data-stu-id="97b31-111">AppRevision</span></span>

<span data-ttu-id="97b31-112">**AppRevision** エンティティは、アプリのバージョンをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="97b31-112">The **AppRevision** entity lists all the versions of apps.</span></span>

| <span data-ttu-id="97b31-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97b31-113">Property</span></span>  | <span data-ttu-id="97b31-114">説明</span><span class="sxs-lookup"><span data-stu-id="97b31-114">Description</span></span> | <span data-ttu-id="97b31-115">例</span><span class="sxs-lookup"><span data-stu-id="97b31-115">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="97b31-116">AppKey</span><span class="sxs-lookup"><span data-stu-id="97b31-116">AppKey</span></span> |<span data-ttu-id="97b31-117">アプリを示す一意識別子。</span><span class="sxs-lookup"><span data-stu-id="97b31-117">Unique identifier of the App.</span></span> |<span data-ttu-id="97b31-118">123</span><span class="sxs-lookup"><span data-stu-id="97b31-118">123</span></span> |
| <span data-ttu-id="97b31-119">ApplicationId</span><span class="sxs-lookup"><span data-stu-id="97b31-119">ApplicationId</span></span> |<span data-ttu-id="97b31-120">アプリを示す一意識別子 - AppKey に似ていますが、このキーはナチュラルです。</span><span class="sxs-lookup"><span data-stu-id="97b31-120">Unique identifier of the App - similar to AppKey, but this key is a natural.</span></span> |<span data-ttu-id="97b31-121">b66bc706-ffff-7437-0340-032819502773</span><span class="sxs-lookup"><span data-stu-id="97b31-121">b66bc706-ffff-7437-0340-032819502773</span></span> |
| <span data-ttu-id="97b31-122">リビジョン</span><span class="sxs-lookup"><span data-stu-id="97b31-122">Revision</span></span> |<span data-ttu-id="97b31-123">バイナリのアップロード中に管理者が挙げたバージョン。</span><span class="sxs-lookup"><span data-stu-id="97b31-123">The version as mentioned by admin during uploading of the binary.</span></span> |<span data-ttu-id="97b31-124">2</span><span class="sxs-lookup"><span data-stu-id="97b31-124">2</span></span> |
| <span data-ttu-id="97b31-125">タイトル</span><span class="sxs-lookup"><span data-stu-id="97b31-125">Title</span></span> |<span data-ttu-id="97b31-126">アプリのタイトル。</span><span class="sxs-lookup"><span data-stu-id="97b31-126">Title of the app.</span></span> |<span data-ttu-id="97b31-127">Excel</span><span class="sxs-lookup"><span data-stu-id="97b31-127">Excel</span></span> |
| <span data-ttu-id="97b31-128">発行者</span><span class="sxs-lookup"><span data-stu-id="97b31-128">Publisher</span></span> |<span data-ttu-id="97b31-129">アプリの発行者。</span><span class="sxs-lookup"><span data-stu-id="97b31-129">Publisher of the app.</span></span> |<span data-ttu-id="97b31-130">Microsoft</span><span class="sxs-lookup"><span data-stu-id="97b31-130">Microsoft</span></span> |
| <span data-ttu-id="97b31-131">UploadState</span><span class="sxs-lookup"><span data-stu-id="97b31-131">UploadState</span></span> |<span data-ttu-id="97b31-132">アプリのアップロード状態。</span><span class="sxs-lookup"><span data-stu-id="97b31-132">Upload state of the app.</span></span> |<span data-ttu-id="97b31-133">1</span><span class="sxs-lookup"><span data-stu-id="97b31-133">1</span></span> |
| <span data-ttu-id="97b31-134">AppTypeKey</span><span class="sxs-lookup"><span data-stu-id="97b31-134">AppTypeKey</span></span> |<span data-ttu-id="97b31-135">AppType の参照 (次のセクションに説明あり)</span><span class="sxs-lookup"><span data-stu-id="97b31-135">Reference to AppType described in the following section.</span></span> | |
| <span data-ttu-id="97b31-136">VppProgramTypeKey</span><span class="sxs-lookup"><span data-stu-id="97b31-136">VppProgramTypeKey</span></span> |<span data-ttu-id="97b31-137">VppProgramType の参照 (下に説明あり)。</span><span class="sxs-lookup"><span data-stu-id="97b31-137">Reference to VppProgramType described below.</span></span> | |
| <span data-ttu-id="97b31-138">CreationTime</span><span class="sxs-lookup"><span data-stu-id="97b31-138">CreationTime</span></span> |<span data-ttu-id="97b31-139">このリビジョンが作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="97b31-139">The time when this revision was created.</span></span> |<span data-ttu-id="97b31-140">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="97b31-140">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="97b31-141">ModifiedTime</span><span class="sxs-lookup"><span data-stu-id="97b31-141">ModifiedTime</span></span> |<span data-ttu-id="97b31-142">このリビジョンに関連する事項が最後に変更された時刻。</span><span class="sxs-lookup"><span data-stu-id="97b31-142">Last time anything related to this revision was changed.</span></span> |<span data-ttu-id="97b31-143">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="97b31-143">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="97b31-144">Size</span><span class="sxs-lookup"><span data-stu-id="97b31-144">Size</span></span> |<span data-ttu-id="97b31-145">バイナリのサイズ。</span><span class="sxs-lookup"><span data-stu-id="97b31-145">Size of the binary.</span></span> | |
| <span data-ttu-id="97b31-146">StartDateInclusiveUTC</span><span class="sxs-lookup"><span data-stu-id="97b31-146">StartDateInclusiveUTC</span></span> |<span data-ttu-id="97b31-147">このアプリ リビジョンがデータ ウェアハウスで作成されたときの UTC 日時。</span><span class="sxs-lookup"><span data-stu-id="97b31-147">Date and time in UTC when this App revision was created in the data warehouse.</span></span> |<span data-ttu-id="97b31-148">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="97b31-148">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="97b31-149">EndDateExclusiveUTC</span><span class="sxs-lookup"><span data-stu-id="97b31-149">EndDateExclusiveUTC</span></span> |<span data-ttu-id="97b31-150">このアプリ リビジョンが推奨されなくなったときの UTC 日時。</span><span class="sxs-lookup"><span data-stu-id="97b31-150">Date and time in UTC when this app revision became obsolete.</span></span> |<span data-ttu-id="97b31-151">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="97b31-151">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="97b31-152">IsCurrent</span><span class="sxs-lookup"><span data-stu-id="97b31-152">IsCurrent</span></span> |<span data-ttu-id="97b31-153">データ ウェアハウスにおいて、このアプリ バージョンが現行のものであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="97b31-153">Indicates whether this App version is current or not in the data warehouse.</span></span> |<span data-ttu-id="97b31-154">真/偽</span><span class="sxs-lookup"><span data-stu-id="97b31-154">True/False</span></span> |
| <span data-ttu-id="97b31-155">RowLastModifiedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="97b31-155">RowLastModifiedDateTimeUTC</span></span> |<span data-ttu-id="97b31-156">このアプリ バージョンがデータ ウェアハウスで最後に変更されたときの UTC 日時。</span><span class="sxs-lookup"><span data-stu-id="97b31-156">Date and time in UTC when this app version was last modified in the data warehouse.</span></span> |<span data-ttu-id="97b31-157">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="97b31-157">11/23/2016 12:00:00 AM</span></span> |

## <a name="apptypes"></a><span data-ttu-id="97b31-158">AppTypes</span><span class="sxs-lookup"><span data-stu-id="97b31-158">AppTypes</span></span>

<span data-ttu-id="97b31-159">**AppTypes** エンティティは、アプリのインストール ソースを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="97b31-159">The **AppTypes** entity lists the installation source of an app.</span></span>

| <span data-ttu-id="97b31-160">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97b31-160">Property</span></span>  | <span data-ttu-id="97b31-161">説明</span><span class="sxs-lookup"><span data-stu-id="97b31-161">Description</span></span> |
|---------|------------|
| <span data-ttu-id="97b31-162">AppTypeID</span><span class="sxs-lookup"><span data-stu-id="97b31-162">AppTypeID</span></span> |<span data-ttu-id="97b31-163">種類の ID</span><span class="sxs-lookup"><span data-stu-id="97b31-163">Id for the type</span></span> |
| <span data-ttu-id="97b31-164">AppTypeKey</span><span class="sxs-lookup"><span data-stu-id="97b31-164">AppTypeKey</span></span> |<span data-ttu-id="97b31-165">キーの代理キー</span><span class="sxs-lookup"><span data-stu-id="97b31-165">Surrogate key for the key</span></span> |
| <span data-ttu-id="97b31-166">AppTypeName</span><span class="sxs-lookup"><span data-stu-id="97b31-166">AppTypeName</span></span> |<span data-ttu-id="97b31-167">アプリの種類</span><span class="sxs-lookup"><span data-stu-id="97b31-167">App type</span></span> |

### <a name="example"></a><span data-ttu-id="97b31-168">例</span><span class="sxs-lookup"><span data-stu-id="97b31-168">Example</span></span>

| <span data-ttu-id="97b31-169">AppTypeID</span><span class="sxs-lookup"><span data-stu-id="97b31-169">AppTypeID</span></span>  | <span data-ttu-id="97b31-170">名前</span><span class="sxs-lookup"><span data-stu-id="97b31-170">Name</span></span> | <span data-ttu-id="97b31-171">説明</span><span class="sxs-lookup"><span data-stu-id="97b31-171">Description</span></span> |
|---------|------------|--------|
| <span data-ttu-id="97b31-172">0</span><span class="sxs-lookup"><span data-stu-id="97b31-172">0</span></span> |<span data-ttu-id="97b31-173">Android ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="97b31-173">Android store app</span></span> | <span data-ttu-id="97b31-174">Android ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-174">An Android store app.</span></span> |
| <span data-ttu-id="97b31-175">1</span><span class="sxs-lookup"><span data-stu-id="97b31-175">1</span></span> |<span data-ttu-id="97b31-176">Android LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="97b31-176">Android LOB app</span></span> | <span data-ttu-id="97b31-177">Android の基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-177">An Android line-of-business app.</span></span> |
| <span data-ttu-id="97b31-178">2</span><span class="sxs-lookup"><span data-stu-id="97b31-178">2</span></span> |<span data-ttu-id="97b31-179">管理対象 Android ストア アプリ (MAM)</span><span class="sxs-lookup"><span data-stu-id="97b31-179">Managed Android store app (MAM)</span></span> | <span data-ttu-id="97b31-180">管理を有効にしている Android ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-180">An Android store app that has management enabled.</span></span> |
| <span data-ttu-id="97b31-181">3</span><span class="sxs-lookup"><span data-stu-id="97b31-181">3</span></span> |<span data-ttu-id="97b31-182">iOS ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="97b31-182">iOS store app</span></span> | <span data-ttu-id="97b31-183">iOS ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-183">An iOS store app.</span></span> |
| <span data-ttu-id="97b31-184">4</span><span class="sxs-lookup"><span data-stu-id="97b31-184">4</span></span> |<span data-ttu-id="97b31-185">iOS LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="97b31-185">iOS LOB app</span></span> | <span data-ttu-id="97b31-186">iOS の基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-186">An iOS line-of-business app.</span></span> |
| <span data-ttu-id="97b31-187">5</span><span class="sxs-lookup"><span data-stu-id="97b31-187">5</span></span> |<span data-ttu-id="97b31-188">管理対象 iOS ストア アプリ (MAM)</span><span class="sxs-lookup"><span data-stu-id="97b31-188">Managed iOS store app (MAM?)</span></span> | <span data-ttu-id="97b31-189">管理を有効にしている iOS ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-189">An iOSstore app that is management enabled.</span></span> |
| <span data-ttu-id="97b31-190">6</span><span class="sxs-lookup"><span data-stu-id="97b31-190">6</span></span> |<span data-ttu-id="97b31-191">O365 Pro Plus Suite</span><span class="sxs-lookup"><span data-stu-id="97b31-191">O365 Pro Plus Suite</span></span> | <span data-ttu-id="97b31-192">Office 365 Pro Plus Suite for Windows 10。</span><span class="sxs-lookup"><span data-stu-id="97b31-192">The Office 365 Pro Plus Suite for Windows 10.</span></span> |
| <span data-ttu-id="97b31-193">7</span><span class="sxs-lookup"><span data-stu-id="97b31-193">7</span></span> |<span data-ttu-id="97b31-194">Web アプリ</span><span class="sxs-lookup"><span data-stu-id="97b31-194">Web app</span></span> | <span data-ttu-id="97b31-195">Web アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-195">A web app.</span></span> |
| <span data-ttu-id="97b31-196">8</span><span class="sxs-lookup"><span data-stu-id="97b31-196">8</span></span> |<span data-ttu-id="97b31-197">Windows Phone 8.1 ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="97b31-197">Windows Phone 8.1 store app</span></span> | <span data-ttu-id="97b31-198">Windows Phone 8.1 ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-198">A Windows phone 8.1 store app.</span></span> |
| <span data-ttu-id="97b31-199">9</span><span class="sxs-lookup"><span data-stu-id="97b31-199">9</span></span> |<span data-ttu-id="97b31-200">Windows ストア アプリ</span><span class="sxs-lookup"><span data-stu-id="97b31-200">Windows store app</span></span> | <span data-ttu-id="97b31-201">Windows ストア アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-201">A Windows store app.</span></span> |
| <span data-ttu-id="97b31-202">10</span><span class="sxs-lookup"><span data-stu-id="97b31-202">10</span></span> |<span data-ttu-id="97b31-203">Windows LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="97b31-203">Windows LOB apps</span></span> | <span data-ttu-id="97b31-204">Windows AppX 基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-204">A Windows AppX line-of-business app.</span></span> |
| <span data-ttu-id="97b31-205">11</span><span class="sxs-lookup"><span data-stu-id="97b31-205">11</span></span> |<span data-ttu-id="97b31-206">Windows Mobile MSI</span><span class="sxs-lookup"><span data-stu-id="97b31-206">Windows Mobile MSI</span></span> | <span data-ttu-id="97b31-207">MSI の基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-207">An MSI line-of-business app.</span></span> |
| <span data-ttu-id="97b31-208">12</span><span class="sxs-lookup"><span data-stu-id="97b31-208">12</span></span> |<span data-ttu-id="97b31-209">Windows Phone LOB アプリ</span><span class="sxs-lookup"><span data-stu-id="97b31-209">Windows Phone LOB app</span></span> | <span data-ttu-id="97b31-210">Windows Phone 基幹業務アプリ。</span><span class="sxs-lookup"><span data-stu-id="97b31-210">A Windows phone line-of-business app.</span></span> |


## <a name="vppprogramtypes"></a><span data-ttu-id="97b31-211">VppProgramTypes</span><span class="sxs-lookup"><span data-stu-id="97b31-211">VppProgramTypes</span></span>

<span data-ttu-id="97b31-212">**VppProgramTypes** エンティティは、アプリの VPP プログラムの種類を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="97b31-212">The **VppProgramTypes** entity lists possible VPP program types for an app.</span></span>

| <span data-ttu-id="97b31-213">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97b31-213">Property</span></span>  | <span data-ttu-id="97b31-214">説明</span><span class="sxs-lookup"><span data-stu-id="97b31-214">Description</span></span> |
|---------|------------|
| <span data-ttu-id="97b31-215">VppProgramTypeID</span><span class="sxs-lookup"><span data-stu-id="97b31-215">VppProgramTypeID</span></span> | <span data-ttu-id="97b31-216">種類の ID。</span><span class="sxs-lookup"><span data-stu-id="97b31-216">ID for the type.</span></span> |
| <span data-ttu-id="97b31-217">VppProgramTypeKey</span><span class="sxs-lookup"><span data-stu-id="97b31-217">VppProgramTypeKey</span></span> | <span data-ttu-id="97b31-218">キーの代理キー。</span><span class="sxs-lookup"><span data-stu-id="97b31-218">Surrogate key for the key.</span></span> |
| <span data-ttu-id="97b31-219">VppProgramTypeName</span><span class="sxs-lookup"><span data-stu-id="97b31-219">VppProgramTypeName</span></span> | <span data-ttu-id="97b31-220">VPP プログラムの種類。</span><span class="sxs-lookup"><span data-stu-id="97b31-220">VPP Program type.</span></span> |

### <a name="example"></a><span data-ttu-id="97b31-221">例</span><span class="sxs-lookup"><span data-stu-id="97b31-221">Example</span></span>

| <span data-ttu-id="97b31-222">VppProgramID</span><span class="sxs-lookup"><span data-stu-id="97b31-222">VppProgramID</span></span>  | <span data-ttu-id="97b31-223">名前</span><span class="sxs-lookup"><span data-stu-id="97b31-223">Name</span></span> | <span data-ttu-id="97b31-224">説明</span><span class="sxs-lookup"><span data-stu-id="97b31-224">Description</span></span> |
|---------|------------|--------|
| <span data-ttu-id="97b31-225">3DDA2474-470B-4503-9830-2665C21C1945</span><span class="sxs-lookup"><span data-stu-id="97b31-225">3DDA2474-470B-4503-9830-2665C21C1945</span></span> | <span data-ttu-id="97b31-226">Microsoft</span><span class="sxs-lookup"><span data-stu-id="97b31-226">Microsoft</span></span> | <span data-ttu-id="97b31-227">Microsoft の VPP プログラム。</span><span class="sxs-lookup"><span data-stu-id="97b31-227">Microsoft's VPP program.</span></span> |
| <span data-ttu-id="97b31-228">00000000-0000-0000-0000-000000000000</span><span class="sxs-lookup"><span data-stu-id="97b31-228">00000000-0000-0000-0000-000000000000</span></span> | <span data-ttu-id="97b31-229">まだ利用できません</span><span class="sxs-lookup"><span data-stu-id="97b31-229">Not Yet Available</span></span> | <span data-ttu-id="97b31-230">既定値、VPP なし。</span><span class="sxs-lookup"><span data-stu-id="97b31-230">Default value, No VPP.</span></span> |
| <span data-ttu-id="97b31-231">B54814E0-68EA-4BA4-8088-B5AAB58E737B</span><span class="sxs-lookup"><span data-stu-id="97b31-231">B54814E0-68EA-4BA4-8088-B5AAB58E737B</span></span> | <span data-ttu-id="97b31-232">Apple</span><span class="sxs-lookup"><span data-stu-id="97b31-232">Apple</span></span> | <span data-ttu-id="97b31-233">Apple の VPP プログラム。</span><span class="sxs-lookup"><span data-stu-id="97b31-233">Apple's VPP program.</span></span> |



## <a name="applicationinventory"></a><span data-ttu-id="97b31-234">ApplicationInventory</span><span class="sxs-lookup"><span data-stu-id="97b31-234">ApplicationInventory</span></span>

<span data-ttu-id="97b31-235">**ApplicationInventory** エンティティには、インベントリ回収時にデバイスで検出されたアプリケーションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="97b31-235">The **ApplicationInventory** entity lists the applications found on the device at the time of inventory collection.</span></span>

| <span data-ttu-id="97b31-236">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97b31-236">Property</span></span>  | <span data-ttu-id="97b31-237">説明</span><span class="sxs-lookup"><span data-stu-id="97b31-237">Description</span></span> |
|---------|------------|
| <span data-ttu-id="97b31-238">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="97b31-238">DeviceKey</span></span> | <span data-ttu-id="97b31-239">これは、Intune デバイス ID が含まれるデバイス テーブルの参照です。</span><span class="sxs-lookup"><span data-stu-id="97b31-239">This is a reference to the Device table which contains the Intune device ID.</span></span> |
| <span data-ttu-id="97b31-240">DateKey</span><span class="sxs-lookup"><span data-stu-id="97b31-240">DateKey</span></span> | <span data-ttu-id="97b31-241">日付テーブルの参照であり、インベントリの日を示します。</span><span class="sxs-lookup"><span data-stu-id="97b31-241">Reference to date table indicating the day of inventory.</span></span> |
| <span data-ttu-id="97b31-242">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="97b31-242">ApplicationName</span></span> | <span data-ttu-id="97b31-243">アプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="97b31-243">The application name.</span></span> |
| <span data-ttu-id="97b31-244">ApplicationVersion</span><span class="sxs-lookup"><span data-stu-id="97b31-244">ApplicationVersion</span></span> | <span data-ttu-id="97b31-245">アプリケーションのバージョン。</span><span class="sxs-lookup"><span data-stu-id="97b31-245">Version of the application.</span></span> |
| <span data-ttu-id="97b31-246">BundleSize</span><span class="sxs-lookup"><span data-stu-id="97b31-246">BundleSize</span></span> | <span data-ttu-id="97b31-247">アプリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="97b31-247">The size of the app in bytes.</span></span> |

## <a name="mobileappinstallstate"></a><span data-ttu-id="97b31-248">MobileAppInstallState</span><span class="sxs-lookup"><span data-stu-id="97b31-248">MobileAppInstallState</span></span>

<span data-ttu-id="97b31-249">**MobileAppInstallState**エンティティは、デバイス、ユーザーまたはその両方を含むグループに割り当てられた後に、モバイル アプリケーションのインストール状態を表します。</span><span class="sxs-lookup"><span data-stu-id="97b31-249">The **MobileAppInstallState** entity represents the install state for a mobile application after it has been assigned to a group containing devices, users or both.</span></span>

| <span data-ttu-id="97b31-250">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97b31-250">Property</span></span> | <span data-ttu-id="97b31-251">説明</span><span class="sxs-lookup"><span data-stu-id="97b31-251">Description</span></span> |
|---|---|
| <span data-ttu-id="97b31-252">AppInstallStateKey</span><span class="sxs-lookup"><span data-stu-id="97b31-252">AppInstallStateKey</span></span> | <span data-ttu-id="97b31-253">アプリの一意の ID は、アカウントの状態をインストールします。</span><span class="sxs-lookup"><span data-stu-id="97b31-253">The unique ID of the app install state for your account.</span></span> |
| <span data-ttu-id="97b31-254">AppInstallState</span><span class="sxs-lookup"><span data-stu-id="97b31-254">AppInstallState</span></span> | <span data-ttu-id="97b31-255">アプリの列挙値は、状態をインストールします。</span><span class="sxs-lookup"><span data-stu-id="97b31-255">Enum value of the app install state.</span></span> |
| <span data-ttu-id="97b31-256">AppInstallStateName</span><span class="sxs-lookup"><span data-stu-id="97b31-256">AppInstallStateName</span></span> | <span data-ttu-id="97b31-257">アプリのインストール状態の名前です。</span><span class="sxs-lookup"><span data-stu-id="97b31-257">Name of the app install state.</span></span> |

## <a name="mobileappdeviceuserinstallstatus"></a><span data-ttu-id="97b31-258">MobileAppDeviceUserInstallStatus</span><span class="sxs-lookup"><span data-stu-id="97b31-258">MobileAppDeviceUserInstallStatus</span></span>

<span data-ttu-id="97b31-259">**MobileAppDeviceUserInstallStatus**特定のデバイスとユーザーのモバイル アプリのインストール状態を表します。</span><span class="sxs-lookup"><span data-stu-id="97b31-259">The **MobileAppDeviceUserInstallStatus** represents a mobile app install status for a given device and user.</span></span>

| <span data-ttu-id="97b31-260">プロパティ</span><span class="sxs-lookup"><span data-stu-id="97b31-260">Property</span></span> | <span data-ttu-id="97b31-261">説明</span><span class="sxs-lookup"><span data-stu-id="97b31-261">Description</span></span> |
|---|---|
| <span data-ttu-id="97b31-262">DateKey</span><span class="sxs-lookup"><span data-stu-id="97b31-262">DateKey</span></span> | <span data-ttu-id="97b31-263">アプリが状態をインストールするときに日付のキーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="97b31-263">Key of the date when the app install status was recorded.</span></span> |
| <span data-ttu-id="97b31-264">AppKey</span><span class="sxs-lookup"><span data-stu-id="97b31-264">AppKey</span></span> | <span data-ttu-id="97b31-265">AppRevision のインスタンスを識別するために使用するモバイル アプリのキー。</span><span class="sxs-lookup"><span data-stu-id="97b31-265">Key of the mobile app used to identify an instance of AppRevision.</span></span> |
| <span data-ttu-id="97b31-266">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="97b31-266">DeviceKey</span></span> | <span data-ttu-id="97b31-267">デバイスのインスタンスを識別するための対象となるデバイスのキー。</span><span class="sxs-lookup"><span data-stu-id="97b31-267">Key of a targeted device used to identify an instance of Device.</span></span> |
| <span data-ttu-id="97b31-268">UserKey</span><span class="sxs-lookup"><span data-stu-id="97b31-268">UserKey</span></span> | <span data-ttu-id="97b31-269">ユーザーのインスタンスを識別するために使用する対象となるユーザーのキー。</span><span class="sxs-lookup"><span data-stu-id="97b31-269">Key of a targeted user used to identify an instance of User.</span></span> |
|<span data-ttu-id="97b31-270">AppInstallStateKey</span><span class="sxs-lookup"><span data-stu-id="97b31-270">AppInstallStateKey</span></span> | <span data-ttu-id="97b31-271">アプリのキーは、MobileAppInstallState のインスタンスを識別するために使用状態をインストールします。</span><span class="sxs-lookup"><span data-stu-id="97b31-271">Key of the app install state used to identify an instance of MobileAppInstallState.</span></span> |
| <span data-ttu-id="97b31-272">エラー コード</span><span class="sxs-lookup"><span data-stu-id="97b31-272">ErrorCode</span></span> | <span data-ttu-id="97b31-273">アプリのインストーラー、モバイル プラットフォームまたはアプリのインストールに関連するサービスによって返されたエラー コード。</span><span class="sxs-lookup"><span data-stu-id="97b31-273">The error code returned by the app installer, the mobile platform or the service pertaining to the installation of the app.</span></span> |
