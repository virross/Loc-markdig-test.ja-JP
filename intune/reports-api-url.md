---
title: "Intune データ ウェアハウス API エンドポイント | Microsoft Docs"
description: "リファレンス トピックでは API URL 構造について説明します。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 09e2e6ed94fcd96857b77e60bb2e617587c3b3f2
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="intune-data-warehouse-api-endpoint"></a><span data-ttu-id="65b69-104">Intune データ ウェアハウス API エンドポイント</span><span class="sxs-lookup"><span data-stu-id="65b69-104">Intune Data Warehouse API endpoint</span></span>

<span data-ttu-id="65b69-105">特定のロールベースのアクセス制御と Azure Active Directory 資格情報を使用するアカウントに、Intune データ ウェアハウス API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="65b69-105">You can use the Intune Data Warehouse API with an account with specific role-based access controls and Azure AD credentials.</span></span> <span data-ttu-id="65b69-106">次に、OAuth 2.0 を使用して Azure AD に対して REST クライアントを承認します。</span><span class="sxs-lookup"><span data-stu-id="65b69-106">You will then authorize your REST client with Azure AD using OAuth 2.0.</span></span> <span data-ttu-id="65b69-107">最後に、データ ウェアハウス リソースを呼び出すことができる有効な URL を形成します。</span><span class="sxs-lookup"><span data-stu-id="65b69-107">And finally, you will form a meaningful URL to call a data warehouse resource.</span></span>

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a><span data-ttu-id="65b69-108">承認</span><span class="sxs-lookup"><span data-stu-id="65b69-108">Authorization</span></span>

<span data-ttu-id="65b69-109">Azure Active Directory (Azure AD) では、OAuth 2.0 を使用して Azure AD テナントの Web アプリケーションと Web API へのアクセスを承認できます。</span><span class="sxs-lookup"><span data-stu-id="65b69-109">Azure Active Directory (Azure AD) uses OAuth 2.0 to enable you to authorize access to web applications and web APIs in your Azure AD tenant.</span></span> <span data-ttu-id="65b69-110">このガイドは言語に依存していません。いずれのオープンソース ライブラリも使用せずに、HTTP メッセージを送受信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65b69-110">This guide is language independent, and describes how to send and receive HTTP messages without using any of our open-source libraries.</span></span> <span data-ttu-id="65b69-111">OAuth 2.0 承認コード フローについては、OAuth 2.0 仕様の[セクション 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65b69-111">The OAuth 2.0 authorization code flow is described in [section 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) of the OAuth 2.0 specification.</span></span>

<span data-ttu-id="65b69-112">詳細については、「[OAuth 2.0 と Azure Active Directory を使用した Web アプリケーションへのアクセスの承認](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65b69-112">For more information, see [Authorize access to web applications using OAuth 2.0 and Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).</span></span>

## <a name="api-url-structure"></a><span data-ttu-id="65b69-113">API URL 構造</span><span class="sxs-lookup"><span data-stu-id="65b69-113">API URL structure</span></span>

<span data-ttu-id="65b69-114">データ ウェアハウス API エンドポイントは、各セットのエンティティを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="65b69-114">The Data Warehouse API endpoints read the entities for each set.</span></span> <span data-ttu-id="65b69-115">API は、**GET** HTTP 動詞と、クエリ オプションのサブセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="65b69-115">The API supports a **GET** HTTP verb, and a subset of query options.</span></span>

<span data-ttu-id="65b69-116">Intune の URL は、次の書式を使用しています。</span><span class="sxs-lookup"><span data-stu-id="65b69-116">The URL for Intune uses the following format:</span></span>  
<span data-ttu-id="65b69-117">https://fef.{<strong><em>location</em></strong>}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{<strong><em>entity-collection</em></strong>}?api-version={<strong><em>api-version</em></strong>}</span><span class="sxs-lookup"><span data-stu-id="65b69-117">https://fef.{<strong><em>location</em></strong>}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{<strong><em>entity-collection</em></strong>}?api-version={<strong><em>api-version</em></strong>}</span></span>

<span data-ttu-id="65b69-118">URL には、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="65b69-118">The URL contains the following elements:</span></span>

| <span data-ttu-id="65b69-119">要素</span><span class="sxs-lookup"><span data-stu-id="65b69-119">Element</span></span> | <span data-ttu-id="65b69-120">例</span><span class="sxs-lookup"><span data-stu-id="65b69-120">Example</span></span> | <span data-ttu-id="65b69-121">説明</span><span class="sxs-lookup"><span data-stu-id="65b69-121">Description</span></span> |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="65b69-122">location</span><span class="sxs-lookup"><span data-stu-id="65b69-122">location</span></span> | <span data-ttu-id="65b69-123">msua06</span><span class="sxs-lookup"><span data-stu-id="65b69-123">msua06</span></span> | <span data-ttu-id="65b69-124">Azure Portal でデータ ウェアハウス API ブレードを表示すると、ベース URL を確認できます。</span><span class="sxs-lookup"><span data-stu-id="65b69-124">The base URL can be found by viewing the Data Warehouse API blade in the Azure portal.</span></span> |
| <span data-ttu-id="65b69-125">entity-collection</span><span class="sxs-lookup"><span data-stu-id="65b69-125">entity-collection</span></span> | <span data-ttu-id="65b69-126">dates</span><span class="sxs-lookup"><span data-stu-id="65b69-126">dates</span></span> | <span data-ttu-id="65b69-127">OData エンティティ コレクションの名前。</span><span class="sxs-lookup"><span data-stu-id="65b69-127">The name of the OData entity collection.</span></span> <span data-ttu-id="65b69-128">データ モデルのコレクションとエンティティの詳細については、「[Data Model](reports-ref-data-model.md)」(データ モデル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65b69-128">For more information on collections and entities in the data model, see [Data Model](reports-ref-data-model.md).</span></span> |
| <span data-ttu-id="65b69-129">api-version</span><span class="sxs-lookup"><span data-stu-id="65b69-129">api-version</span></span> | <span data-ttu-id="65b69-130">beta</span><span class="sxs-lookup"><span data-stu-id="65b69-130">beta</span></span> | <span data-ttu-id="65b69-131">Version はアクセスする API のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="65b69-131">Version is the version of the API to access.</span></span> <span data-ttu-id="65b69-132">詳細については、「[API のバージョン情報](#API-version-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65b69-132">For more information, see [Version](#API-version-information).</span></span> |


## <a name="api-version-information"></a><span data-ttu-id="65b69-133">API のバージョン情報</span><span class="sxs-lookup"><span data-stu-id="65b69-133">API version information</span></span>

<span data-ttu-id="65b69-134">API の現在のバージョンは `beta` です。</span><span class="sxs-lookup"><span data-stu-id="65b69-134">The current version of the API is: `beta`.</span></span> 

## <a name="odata-query-options"></a><span data-ttu-id="65b69-135">OData クエリのオプション</span><span class="sxs-lookup"><span data-stu-id="65b69-135">OData query options</span></span>

<span data-ttu-id="65b69-136">現在のバージョンは、OData クエリ パラメーター `$filter, $orderby, $select, $skip,` と `$top` をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="65b69-136">The current version supports the following OData query parameters: `$filter, $orderby, $select, $skip,` and `$top`.</span></span>