---
title: "Power BI でデータ ウェアハウスに接続する | Microsoft Docs"
description: "Microsoft Power BI で使用するファイルをダウンロードし、Intune テナントに合わせて動的に生成されるインタラクティブなレポートを読み込むことができます。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4a5cd4e22ed9b1bf5d24c636e4665880b6799e18
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a><span data-ttu-id="b1a19-104">Power BI でデータ ウェアハウスに接続する</span><span class="sxs-lookup"><span data-stu-id="b1a19-104">Connect to the Data Warehouse with Power BI</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b1a19-105">Microsoft Power BI で使用するファイルをダウンロードし、Intune テナントに合わせて動的に生成されるインタラクティブなレポートを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-105">You can download a file for use with Microsoft Power BI that allows you to load interactive, dynamically generated reports for your Intune tenant.</span></span> <span data-ttu-id="b1a19-106">データ ウェアハウス Power BI ファイル (pbix) には、テナントへの接続設定と、次のサンプル レポートとグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1a19-106">The Data Warehouse Power BI file (pbix) contains connection settings to your tenant, and the following sample reports and charts:</span></span>  

  -  <span data-ttu-id="b1a19-107">[デバイス]</span><span class="sxs-lookup"><span data-stu-id="b1a19-107">Devices</span></span>
  -  <span data-ttu-id="b1a19-108">登録</span><span class="sxs-lookup"><span data-stu-id="b1a19-108">Enrollment</span></span>
  -  <span data-ttu-id="b1a19-109">アプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1a19-109">App protection policy</span></span>
  -  <span data-ttu-id="b1a19-110">コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="b1a19-110">Compliance policy</span></span>
  -  <span data-ttu-id="b1a19-111">デバイスの構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="b1a19-111">Device configuration profiles</span></span>
  -  <span data-ttu-id="b1a19-112">ソフトウェア更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b1a19-112">Software updates</span></span>
  -  <span data-ttu-id="b1a19-113">デバイス インベントリ</span><span class="sxs-lookup"><span data-stu-id="b1a19-113">Device inventory logs</span></span>

<span data-ttu-id="b1a19-114">また、登録、コンプライアンス、デバイス構成プロファイル、ソフトウェア更新プログラムの強調表示された傾向も確認できます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-114">There are also trends highlighted for the enrollment, compliance, device configuration profile, and software updates.</span></span> <span data-ttu-id="b1a19-115">サンプル グラフとレポートでは、わかりやすいフィルターをキャンバスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-115">Sample charts and reports apply user-friendly filters to the canvas.</span></span> <span data-ttu-id="b1a19-116">高度なフィルターを使用するには、Power BI Desktop の **[フィルター]** ウィンドウを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-116">To use advanced filters, check out the **Filter** pane in Power BI Desktop.</span></span>

<span data-ttu-id="b1a19-117">Power BI ファイルをダウンロードする方法と、Power BI で OData リンクを使用する方法については、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1a19-117">The following steps show you how to download the Power BI file and how to use the OData link with Power BI.</span></span>

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a><span data-ttu-id="b1a19-118">Power BI をインストールする</span><span class="sxs-lookup"><span data-stu-id="b1a19-118">Install Power BI</span></span>

<span data-ttu-id="b1a19-119">最新バージョンの Power BI Desktop をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b1a19-119">Install the latest version of Power BI Desktop.</span></span> <span data-ttu-id="b1a19-120">Power BI Desktop は [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-120">You can download Power BI Desktop from: [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop)</span></span>

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a><span data-ttu-id="b1a19-121">Power BI ファイル (pbix) を使用してデータとレポートを読み込む</span><span class="sxs-lookup"><span data-stu-id="b1a19-121">Load the data and reports using the Power BI file (pbix)</span></span>

<span data-ttu-id="b1a19-122">Power BI ファイル (pbix) には、テナントの接続情報と、データ ウェアハウス データ モデルに基づいて構築済みのレポートのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1a19-122">The Power BI file (pbix) contains connection information for your tenant and a set of prebuilt reports based on the Data Warehouse data model.</span></span> <span data-ttu-id="b1a19-123">Power BI Desktop でファイルを開き、Azure AD にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b1a19-123">Open the file in Power BI Desktop and sign in to the Azure AD.</span></span> <span data-ttu-id="b1a19-124">レポートでは Intune テナントからデータが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-124">The report loads the data from your Intune tenant.</span></span>

> [!Important]  
> <span data-ttu-id="b1a19-125">各 Power BI ファイル (pbix) は、テナントの場所によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1a19-125">Each Power BI file (pbix) may be different depending on tenant location.</span></span> <span data-ttu-id="b1a19-126">複数の Intune テナントを管理している場合は、必ずそのテナントにログインした状態で Azure Portal からダウンロードしたファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-126">If you are managing multiple Intune tenants, then be sure to use the file downloaded from the Azure portal while logged in to that tenant.</span></span>  

1.  <span data-ttu-id="b1a19-127">Azure Portal にサインインし、**[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-127">Sign in to the Azure portal and choose **Monitoring + Management** > **Intune**.</span></span> <span data-ttu-id="b1a19-128">**Intune** のリソースを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-128">You can also search resources for **Intune**.</span></span>  
2.  <span data-ttu-id="b1a19-129">**[Microsoft Intune データ ウェアハウス API (プレビュー)]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-129">Open the **Microsoft Intune Data Warehouse API (Preview)** blade.</span></span>
3.  <span data-ttu-id="b1a19-130">**[Power BI ファイルのダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-130">Select **Download PowerBI file**.</span></span> <span data-ttu-id="b1a19-131">拡張子が pbix のファイルが、指定した場所にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-131">The file with a (pbix) extension downloads to the location you specified.</span></span>
4.  <span data-ttu-id="b1a19-132">Power BI でファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-132">Open the file with Power BI.</span></span> <span data-ttu-id="b1a19-133">*Intune データ ウェアハウス レポート*が読み込まれますが、テナント データの取得に少し時間がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1a19-133">The *Intune Data Warehouse Reports* loads, but may take a second to get your tenant data.</span></span>
5.  <span data-ttu-id="b1a19-134">**[更新]** を選択してテナント データを読み込み、レポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-134">Select **Refresh** to load your tenant data and review the reports.</span></span>
6.  <span data-ttu-id="b1a19-135">Power BI が Azure Active Directory の資格情報で認証されていない場合は、資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-135">If Power BI has not authenticated with your Azure Active Directory credentials, Power BI prompts you to provide your credentials.</span></span> <span data-ttu-id="b1a19-136">資格情報を選択するときに、認証方法として **[組織アカウント]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-136">When selecting your credentials, choose **Organizational account** as your authentication method.</span></span>

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a><span data-ttu-id="b1a19-137">OData リンクを使用して Power BI でデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="b1a19-137">Load the data in Power BI using the OData link</span></span>

<span data-ttu-id="b1a19-138">Azure AD に対してクライアントが認証されていると、OData URL は、データ ウェアハウス API で、データ モデルをレポート クライアントに公開している RESTful エンドポイントに接続します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-138">With a client authenticated to Azure AD, the OData URL connects to the RESTful endpoint in the Data Warehouse API that exposes the data model to your reporting client.</span></span> <span data-ttu-id="b1a19-139">Power BI Desktop を使用して接続して独自のレポートを作成するするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-139">Follow these instructions to use Power BI Desktop to connect and create your own reports.</span></span> <span data-ttu-id="b1a19-140">OAUTH2.0 認証と OData v4.0 標準をサポートしているクライアントであれば、Power BI Desktop だけでなく、OData URL にお気に入りの分析ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-140">You are not limited to Power BI Desktop, but can use your favorite analytic tool with the OData URL provided the client supports OAUTH2.0 authentication and the OData v4.0 standard.</span></span>

1.  <span data-ttu-id="b1a19-141">Azure Portal にサインインし、**[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-141">Sign in to the Azure portal and choose **Monitoring + Management** > **Intune**.</span></span> <span data-ttu-id="b1a19-142">**Intune** のリソースを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-142">You can also search resources for **Intune**.</span></span>  
2.  <span data-ttu-id="b1a19-143">**[Microsoft Intune データ ウェアハウス API (プレビュー)]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-143">Open the **Microsoft Intune Data Warehouse API (Preview)** blade.</span></span>
3. <span data-ttu-id="b1a19-144">たとえば、`https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta` などのレポート ブレードからカスタム フィード URL を取得します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-144">Retrieve the custom feed URL from the reporting blade, for example `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`</span></span>
4. <span data-ttu-id="b1a19-145">**Power BI Desktop** を開きます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-145">Open **Power BI Desktop**.</span></span>
5. <span data-ttu-id="b1a19-146">**[ホーム]** > **[データの取得]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-146">Choose **Home** > **Get Data**.</span></span> <span data-ttu-id="b1a19-147">**[OData フィード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-147">Select **OData feed**.</span></span>
6. <span data-ttu-id="b1a19-148">**[基本]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-148">Choose **Basic**.</span></span>
7. <span data-ttu-id="b1a19-149">[URL] ボックスに **[OData URL]** を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-149">Type or paste the **OData URL** into the URL box.</span></span>
8. <span data-ttu-id="b1a19-150">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-150">Select **OK**.</span></span>
9. <span data-ttu-id="b1a19-151">Power BI Desktop クライアントからテナントの Azure AD に対して認証されていない場合は、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-151">If you have not authenticated to Azure AD for your tenant from the Power BI desktop client, type your credentials.</span></span> <span data-ttu-id="b1a19-152">データにアクセスするには、OAuth 2.0 を使って Azure Active Directory (Azure AD) で認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1a19-152">To gain access to your data, you must authorize with Azure Active Directory (Azure AD) using OAuth 2.0.</span></span>  
    1.  <span data-ttu-id="b1a19-153">**[組織のアカウント]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-153">Select **Organizational account**.</span></span>  
    2.  <span data-ttu-id="b1a19-154">ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-154">Type your username and password.</span></span>  
    3.  <span data-ttu-id="b1a19-155">**[サインイン]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-155">Select **Sign In.**</span></span>  
    4.  <span data-ttu-id="b1a19-156">**[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-156">Select **Connect**.</span></span>  
10. <span data-ttu-id="b1a19-157">**[読み込み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1a19-157">Select **Load**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b1a19-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="b1a19-158">Next steps</span></span>

<span data-ttu-id="b1a19-159">過去 1 週間に登録されたデバイス数/日など、環境について知りたい情報が見つかります。</span><span class="sxs-lookup"><span data-stu-id="b1a19-159">You can find the answers to questions about your environment such as the number of devices enrolled by day over the last week.</span></span> <span data-ttu-id="b1a19-160">Azure のブレードから取得した Intune データ ウェアハウス Power BI ファイル (pbix) を使用したレポートで、Intune テナントとクライアント数を分析できます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-160">You can gain insight into your Intune tenant and client population using the reports using the Intune Data Warehouse Power BI file (pbix) retrieved from the blade in Azure.</span></span> <span data-ttu-id="b1a19-161">また、Intune には、データを拡張または再利用することができる機能が多数あります。</span><span class="sxs-lookup"><span data-stu-id="b1a19-161">However, Intune provides a number of additional ways to extend or reuse the data.</span></span> <span data-ttu-id="b1a19-162">Power BI と Intune データ ウェアハウス API を使用すると、次のようにさまざまな処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-162">There is a lot more that you can do with Power BI and the Intune Data Warehouse API, for example:</span></span>

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  <span data-ttu-id="b1a19-163">テナント データを整理し、データを基に分析しやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-163">Your tenant data is organized to help you pull insight from your data.</span></span> <span data-ttu-id="b1a19-164">データの整理方法については、「[Data Warehouse Data Model](reports-ref-data-model.md)」(データ ウェアハウス データ モデル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1a19-164">For more information about how the data is organized, see [Data Warehouse Data Model](reports-ref-data-model.md).</span></span>
 -  <span data-ttu-id="b1a19-165">RESTful インターフェイスからデータにアクセスし、データを自分のアプリに組み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="b1a19-165">You can also access the data from a RESTful interface and incorporate the data into your own app.</span></span> <span data-ttu-id="b1a19-166">詳細については、「[REST クライアントを使用してのデータ ウェアハウス API からのデータの取得](reports-proc-data-rest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1a19-166">For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md).</span></span>
