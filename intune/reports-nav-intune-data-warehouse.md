---
title: "Intune データ ウェアハウス API | Microsoft Docs"
description: "API を使用して、企業のモバイル環境を分析するレポートを構築することができます。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a0d6bcb4ccac3563dd642ec0ad621645b7053dea
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
#  <a name="intune-data-warehouse-api"></a><span data-ttu-id="05504-104">Intune データ ウェアハウス API</span><span class="sxs-lookup"><span data-stu-id="05504-104">Intune Data Warehouse API</span></span>

<span data-ttu-id="05504-105">Intune データ ウェアハウス API を使用すると、コンピューターで読み取ることができる Intune データにアクセスし、普段使用する分析ツールに利用することができます。</span><span class="sxs-lookup"><span data-stu-id="05504-105">The Intune Data Warehouse API lets you access your Intune data in a machine-readable format for use in your favorite analytics tool.</span></span> <span data-ttu-id="05504-106">API を使用して、企業のモバイル環境を分析するレポートを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="05504-106">You can use the API to build reports that provide insight into your enterprise mobile environment.</span></span> <span data-ttu-id="05504-107">API では OData プロトコルを使用しています。OData プロトコルは次の標準のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="05504-107">The API uses the OData protocol, which follows standard patterns for:</span></span>

  -   <span data-ttu-id="05504-108">要求および応答のヘッダー</span><span class="sxs-lookup"><span data-stu-id="05504-108">Request and response headers</span></span>
  -   <span data-ttu-id="05504-109">状態コード</span><span class="sxs-lookup"><span data-stu-id="05504-109">Status codes</span></span>
  -   <span data-ttu-id="05504-110">HTTP メソッド</span><span class="sxs-lookup"><span data-stu-id="05504-110">HTTP methods</span></span>
  -   <span data-ttu-id="05504-111">URL の表記規則</span><span class="sxs-lookup"><span data-stu-id="05504-111">URL conventions</span></span>
  -   <span data-ttu-id="05504-112">メディアの種類</span><span class="sxs-lookup"><span data-stu-id="05504-112">Media types</span></span>
  -   <span data-ttu-id="05504-113">ペイロード形式</span><span class="sxs-lookup"><span data-stu-id="05504-113">Payload formats</span></span>
  -   <span data-ttu-id="05504-114">クエリ オプション</span><span class="sxs-lookup"><span data-stu-id="05504-114">Query options</span></span>

<span data-ttu-id="05504-115">OData (Open Data Protocol) は、RESTful API を構築し、使用する際のベスト プラクティスが定義されている Organization for the Advancement of Structured Information Standards (OASIS) 標準です。</span><span class="sxs-lookup"><span data-stu-id="05504-115">The OData (Open Data Protocol) is an Organization for the Advancement of Structured Information Standards (OASIS) standard that defines the best practice for building and consuming RESTful APIs.</span></span> <span data-ttu-id="05504-116">Intune データ ウェアハウスでは、OData バージョン 4.0 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="05504-116">The Intune Data Warehouse uses OData version 4.0.</span></span>

<span data-ttu-id="05504-117">この参照セクションでは、エンドポイント、サポートされる HTTP メソッド、戻り値のペイロードの形式、Intune データ ウェアハウス データ モデルのドキュメントの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="05504-117">This reference section provides an overview of endpoints, supported HTTP methods, return payload formats, and documentation of the Intune Data Warehouse data model.</span></span>

> [!Important]  
> <span data-ttu-id="05504-118">データ ウェアハウスの最新機能については、ベータ バージョンを使用して試すことができます。</span><span class="sxs-lookup"><span data-stu-id="05504-118">You can try out the latest functionality of the Data Warehouse by using the beta version.</span></span> <span data-ttu-id="05504-119">ベータ バージョンを使用するには、URL にクエリ パラメーター `api-version=beta` を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="05504-119">To use the beta version, your URL must contain the query parameter `api-version=beta`.</span></span> <span data-ttu-id="05504-120">ベータ バージョンは、サポートされるサービスとして一般公開される前の機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="05504-120">The beta version offers features before they are made generally available as a supported service.</span></span> <span data-ttu-id="05504-121">Intune に新しい機能が追加されると、ベータ バージョンの動作とデータ コントラクトが変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05504-121">As Intune adds new features, the beta version may change behavior and data contracts.</span></span> <span data-ttu-id="05504-122">カスタム コードまたはレポート ツールがベータ バージョンに依存していると、今後の更新プログラムで使用できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05504-122">Any custom code or reporting tools dependent on the beta version may break with ongoing updates.</span></span> <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

## <a name="odata-custom-client"></a><span data-ttu-id="05504-123">OData カスタム クライアント</span><span class="sxs-lookup"><span data-stu-id="05504-123">OData custom client</span></span>

<span data-ttu-id="05504-124">RESTful エンドポイント経由で Intune データ ウェアハウスのデータ モデルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="05504-124">You can access the Intune Data Warehouse data model through RESTful endpoints.</span></span> <span data-ttu-id="05504-125">データにアクセスするには、OAuth 2.0 を利用し、Azure Active Directory (Azure AD) でクライアントを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05504-125">To gain access to your data, your client must authorize with Azure Active Directory (Azure AD) using OAuth 2.0.</span></span> <span data-ttu-id="05504-126">最初に Azure で Web アプリとクライアント アプリを設定し、クライアントにアクセス許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="05504-126">You first set up a web app and a client app in Azure, grant permissions to the client.</span></span> <span data-ttu-id="05504-127">ローカル クライアントに承認が与えられ、データ ウェアハウスのエンドポイントと通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="05504-127">Your local client gets authorization and can then communicate with the Data Warehouse endpoints.</span></span>

<span data-ttu-id="05504-128">詳細については、「[REST クライアントを使用してのデータ ウェアハウス API からのデータの取得](reports-proc-data-rest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05504-128">For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md)</span></span>

> [!Note]  
> <span data-ttu-id="05504-129">コードのサンプルは、Github の [GitHub Intune データ ウェアハウス リポジトリ](https://github.com/Microsoft/Intune-Data-Warehouse)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="05504-129">You can access the [GitHub Intune Data Warehouse repo](https://github.com/Microsoft/Intune-Data-Warehouse) on Github for code samples.</span></span>

## <a name="interacting-with-the-api"></a><span data-ttu-id="05504-130">API との対話</span><span class="sxs-lookup"><span data-stu-id="05504-130">Interacting with the API</span></span>

<span data-ttu-id="05504-131">API を使用するには Azure AD による承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="05504-131">The API requires authorization with Azure AD.</span></span> <span data-ttu-id="05504-132">Azure AD は OAuth 2.0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="05504-132">Azure AD uses OAuth 2.0.</span></span> <span data-ttu-id="05504-133">承認が完了すると、HTTP GET 動詞を使用し、公開されているエンティティ コレクションに接続して、API からデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="05504-133">Once authorized, you can get data from the API using an HTTP GET verb and contacting the exposed entity collections.</span></span> <span data-ttu-id="05504-134">詳細については、次のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="05504-134">For details see:</span></span>

 -  [<span data-ttu-id="05504-135">承認</span><span class="sxs-lookup"><span data-stu-id="05504-135">Authorization</span></span>](reports-api-url.md)
 -  [<span data-ttu-id="05504-136">API URL 構造</span><span class="sxs-lookup"><span data-stu-id="05504-136">API URL Structure</span></span>](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a><span data-ttu-id="05504-137">Intune データ ウェアハウスのデータ モデル</span><span class="sxs-lookup"><span data-stu-id="05504-137">Intune Data Warehouse data model</span></span>

<span data-ttu-id="05504-138">OData で抽象データ モデルとプロトコルを定義し、任意のデータ ソースが公開している情報に任意のクライアントがアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="05504-138">OData defines an abstract data model and a protocol that let any client access information exposed by any data source.</span></span> <span data-ttu-id="05504-139">データ モデルのドキュメント トピックでは、Intune データ ウェアハウス データ モデルの名前空間、エンティティ、リターン オブジェクトについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="05504-139">The data model documentation topic contains an explanation of the namespaces, entities, and return objects in the Intune Data Warehouse data model.</span></span> <span data-ttu-id="05504-140">詳細については、「[Data Warehouse Data Model](reports-ref-data-model.md)」(データ ウェアハウスのデータ モデル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05504-140">For more information, see [Data Warehouse Data Model](reports-ref-data-model.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="05504-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="05504-141">Next steps</span></span>

<span data-ttu-id="05504-142">「[Azure AD の認証シナリオ](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios)」を読んで、Azure AD の操作についてさらに詳しく学習します。</span><span class="sxs-lookup"><span data-stu-id="05504-142">Learn more about working with Azure AD by reading the [Authentication Scenarios for Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span></span>

<span data-ttu-id="05504-143">[odata.org](http://www.odata.org) で OData のリソースを探します。</span><span class="sxs-lookup"><span data-stu-id="05504-143">Find OData resources at [odata.org](http://www.odata.org).</span></span>
  
<span data-ttu-id="05504-144">「[OData Version 4.0] (http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)」で OData Version 4.0 標準を確認します</span><span class="sxs-lookup"><span data-stu-id="05504-144">Review the OData Version 4.0 standard at [OData Version 4.0] (http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)</span></span>  
