---
title: "Power BI で OData フィードからレポートを作成する | Microsoft Docs"
description: "Power BI Desktop と Intune データ ウェアハウス API の対話型フィルターを使って、ツリーマップの視覚化を作成します。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1e0ffcaa2ff8bd9e622c1d27f27564bd78df0276
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="create-a-report-from-the-odata-feed-with-power-bi"></a><span data-ttu-id="d1a55-104">Power BI で OData フィードからレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="d1a55-104">Create a report from the OData feed with Power BI</span></span>

<span data-ttu-id="d1a55-105">このチュートリアルでは、Power BI Desktop と対話型フィルターを使って、ツリーマップの視覚化を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-105">In this tutorial, you're going to create a treemap visualization using Power BI Desktop with an interactive filter.</span></span> <span data-ttu-id="d1a55-106">たとえば、CFO がデバイスの全体的な分布を会社所有デバイスと個人デバイスで比較したいような場合です。</span><span class="sxs-lookup"><span data-stu-id="d1a55-106">For example, your CFO might like to how the overall distribution of devices compares to just company owned to personal devices.</span></span> <span data-ttu-id="d1a55-107">ツリーマップを使用すると、デバイスの種類の合計数に関する洞察が得られます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-107">The treemap provides insight into the total number of device types.</span></span> <span data-ttu-id="d1a55-108">会社所有または個人所有の iOS、Android、Windows デバイスの数がわかります。</span><span class="sxs-lookup"><span data-stu-id="d1a55-108">You can review the number of iOS, Android, and Windows devices that are either company owned or personally owned.</span></span>

### <a name="overview-of-creating-the-chart"></a><span data-ttu-id="d1a55-109">グラフ作成の概要</span><span class="sxs-lookup"><span data-stu-id="d1a55-109">Overview of creating the chart</span></span>

<span data-ttu-id="d1a55-110">このグラフを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-110">To create this chart, you will:</span></span>
1. <span data-ttu-id="d1a55-111">まだの場合は Power BI Desktop をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-111">Install Power BI Desktop if you don't already have it.</span></span>
2. <span data-ttu-id="d1a55-112">Intune データ ウェアハウス データ モデルに接続し、モデルの現在のデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-112">Connect to the Intune Data Warehouse data model and retrieve current data for the model.</span></span>
3. <span data-ttu-id="d1a55-113">データ モデル間のリレーションシップを作成または管理します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-113">Create or manage the data model relationships.</span></span>
4. <span data-ttu-id="d1a55-114">**デバイス** テーブルのデータでグラフを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-114">Create the chart with data from the **devices** table.</span></span>
5. <span data-ttu-id="d1a55-115">対話型フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-115">Create an interactive filter.</span></span>
6. <span data-ttu-id="d1a55-116">完成したグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-116">View the finished chart.</span></span>

### <a name="a-note-about-tables-and-entities"></a><span data-ttu-id="d1a55-117">テーブルとエンティティに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="d1a55-117">A note about tables and entities</span></span>

<span data-ttu-id="d1a55-118">Power BI でテーブルを処理します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-118">You work with tables in Power BI.</span></span> <span data-ttu-id="d1a55-119">テーブルにはデータ フィールドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-119">A table contains data fields.</span></span> <span data-ttu-id="d1a55-120">各データ フィールドにはデータ型があります。</span><span class="sxs-lookup"><span data-stu-id="d1a55-120">Each data field has a data type.</span></span> <span data-ttu-id="d1a55-121">フィールドには、そのデータ型のデータのみを格納できます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-121">The field can only contain data of the data type.</span></span> <span data-ttu-id="d1a55-122">データ型は、数値、文字列、日付などです。</span><span class="sxs-lookup"><span data-stu-id="d1a55-122">Data types are numbers, text, dates, and so on.</span></span> <span data-ttu-id="d1a55-123">Power BI のテーブルには、モデルを読み込むときにテナントから最近の履歴データが入力されます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-123">The tables in Power BI fill with recent historical data from your tenant when you load the model.</span></span> <span data-ttu-id="d1a55-124">個々のデータは時間と共に変化しますが、テーブルの構造は、基になっているデータ モデルが更新されない限り変わりません。</span><span class="sxs-lookup"><span data-stu-id="d1a55-124">Although the specific data changes with time, the table structure won't change unless the underlying data model is updated.</span></span>

<span data-ttu-id="d1a55-125">"_エンティティ_" と "_テーブル_" という用語が混同される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1a55-125">You may be confused by the use of the term _entity_ and _table_.</span></span> <span data-ttu-id="d1a55-126">データ モデルには、OData フィードを使ってアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-126">The data model is accessible through an OData feed.</span></span> <span data-ttu-id="d1a55-127">Power BI でテーブルと呼ばれるコンテナーが、OData ではエンティティと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-127">In the universe of the OData, the containers that are called tables in Power BI are called entities.</span></span> <span data-ttu-id="d1a55-128">これらの用語はどちらも、データを保持する同じものを指しています。</span><span class="sxs-lookup"><span data-stu-id="d1a55-128">These terms both refer to the same thing that holds your data.</span></span>

## <a name="install-power-bi-desktop"></a><span data-ttu-id="d1a55-129">Power BI Desktop をインストールする</span><span class="sxs-lookup"><span data-stu-id="d1a55-129">Install Power BI Desktop</span></span>

<span data-ttu-id="d1a55-130">最新バージョンの Power BI Desktop をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-130">Install the latest version of Power BI Desktop.</span></span> <span data-ttu-id="d1a55-131">Power BI Desktop は [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-131">You can download Power BI Desktop from: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)</span></span>

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a><span data-ttu-id="d1a55-132">テナントの Intune データ ウェアハウスの OData フィードに接続する</span><span class="sxs-lookup"><span data-stu-id="d1a55-132">Connect to the OData feed for the Intune Data Warehouse for your tenant</span></span>

> [!Note]  
> <span data-ttu-id="d1a55-133">Intune の**レポート**に対するアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1a55-133">You need permission to **Reports** in Intune.</span></span> <span data-ttu-id="d1a55-134">詳細については、「[承認](reports-api-url.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1a55-134">For more information, see [Authorization](reports-api-url.md).</span></span>

1. <span data-ttu-id="d1a55-135">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-135">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="d1a55-136">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-136">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="d1a55-137">**[Intune データ ウェアハウス]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-137">Open the **Intune Data Warehouse** blade.</span></span>
4. <span data-ttu-id="d1a55-138">カスタム フィードの URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-138">Copy the custom feed URL.</span></span> <span data-ttu-id="d1a55-139">例: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`</span><span class="sxs-lookup"><span data-stu-id="d1a55-139">For example: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`</span></span>
5. <span data-ttu-id="d1a55-140">Power BI Desktop を開きます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-140">Open Power BI Desktop.</span></span>
6. <span data-ttu-id="d1a55-141">**[データの取得]** > **[Odata フィード]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-141">Choose **Get Data** > **Odata feed**.</span></span>
7. <span data-ttu-id="d1a55-142">**[OData フィード]** ウィンドウの [URL] ボックスにカスタム フィードの URL を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-142">Paste the custom feed URL into the URL box in the **OData feed** window.</span></span>
8. <span data-ttu-id="d1a55-143">**[基本]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-143">Select **Basic**.</span></span>

    ![OData フィード](media/reports-create-01-odatafeed.png)

9. <span data-ttu-id="d1a55-145">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-145">Select **OK**.</span></span>
10. <span data-ttu-id="d1a55-146">**[組織のアカウント]** を選択し、Intune の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-146">Select **Organization account**, and then sign in with your Intune credentials.</span></span> 

    ![組織のアカウントの資格情報](media/reports-create-02-org-account.png)

11. <span data-ttu-id="d1a55-148">**[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-148">Select **Connect**.</span></span> <span data-ttu-id="d1a55-149">ナビゲーターが開き、Intune データ ウェアハウスのテーブルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-149">The Navigator will open and show you the list of tables in the Intune Data Warehouse.</span></span> 

    ![ナビゲーター](media/reports-create-02-loadentities.png)

12. <span data-ttu-id="d1a55-151">**devices** テーブルと **ownerTypes** テーブルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-151">Select the **devices** and the **ownerTypes** tables.</span></span>  <span data-ttu-id="d1a55-152">**[読み込み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-152">Select **Load**.</span></span> <span data-ttu-id="d1a55-153">Power BI がモデルにデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-153">Power BI loads data to the model.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="d1a55-154">リレーションシップを作成する</span><span class="sxs-lookup"><span data-stu-id="d1a55-154">Create a relationship</span></span> 

<span data-ttu-id="d1a55-155">複数のテーブルをインポートして、1 つのテーブル内のデータだけでなく、複数のテーブルの関連するデータを分析することができます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-155">You can import multiple tables to analyze not just the data in a single table but related data across tables.</span></span>  <span data-ttu-id="d1a55-156">PowerBI には**自動検出**と呼ばれる機能があり、リレーションシップの自動的な検索と作成を試みます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-156">PowerBI has a feature called **autodetect** that attempts to find and create relationships for you.</span></span> <span data-ttu-id="d1a55-157">データ ウェアハウスのテーブルは、PowerBI の自動検出が機能するように作成されています。</span><span class="sxs-lookup"><span data-stu-id="d1a55-157">The tables in the Data Warehouse have been built to work with PowerBI's autodetect feature.</span></span> <span data-ttu-id="d1a55-158">ただし、PowerBI がリレーションシップを自動的に検索しない場合でも、リレーションシップを管理することは可能です。</span><span class="sxs-lookup"><span data-stu-id="d1a55-158">However, even if PowerBI doesn't automatically find the relationships you still manage the relationships.</span></span>

![リレーションシップを管理する](media/reports-create-03-managerelationships.png)

1. <span data-ttu-id="d1a55-160">**[リレーションシップの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-160">Select **Manage Relationships**.</span></span>
2. <span data-ttu-id="d1a55-161">PowerBI でリレーションシップがまだ検出されていない場合は、**[自動検出]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-161">Select **Autodetect...** if PowerBI has not already detected the relationships.</span></span>  
<span data-ttu-id="d1a55-162">リレーションシップの追加元と宛先の列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-162">The relationship is displayed in a From column to a To column.</span></span> <span data-ttu-id="d1a55-163">この例では、**devices** テーブルのデータ フィールド **ownerTypeKey** が、**ownerTypes** テーブルのデータ フィールド **ownerTypeKey** にリンクしています。</span><span class="sxs-lookup"><span data-stu-id="d1a55-163">In this example, the data field **ownerTypeKey** in the **devices** table links to the data field **ownerTypeKey** in the **ownerTypes** table.</span></span> <span data-ttu-id="d1a55-164">リレーションシップを使って、**devices** テーブルのデバイス種類コードの一般的な名前を調べます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-164">You use the relationship to look up plain name of the device type code in the **devices** table.</span></span>

## <a name="create-a-treemap-visualization"></a><span data-ttu-id="d1a55-165">ツリーマップ視覚化を作成する</span><span class="sxs-lookup"><span data-stu-id="d1a55-165">Create a treemap visualization</span></span>

<span data-ttu-id="d1a55-166">ツリーマップ グラフには、ボックス内のボックスとして階層データが示されます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-166">A treemap chart shows hierarchical data as boxes with in boxes.</span></span> <span data-ttu-id="d1a55-167">階層の各分岐は、サブ分岐を示す小さいボックスが含まれているボックスです。</span><span class="sxs-lookup"><span data-stu-id="d1a55-167">Each branch of the hierarchy is a box contains smaller boxes showing subbranches.</span></span> <span data-ttu-id="d1a55-168">Power BI Desktop を使用して、Intune データのツリーマップを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-168">You can use Power BI desktop to create a treemap of your Intune data.</span></span>

![視覚化 > ツリーマップ](media/reports-create-03-treemap.png)

1. <span data-ttu-id="d1a55-170">グラフの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-170">Select a chart type.</span></span> <span data-ttu-id="d1a55-171">**[Treemap]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-171">Select **Treemap**.</span></span>
2. <span data-ttu-id="d1a55-172">データ モデルで、**devices** テーブルを探します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-172">In the data model, find the **devices** table.</span></span>
3. <span data-ttu-id="d1a55-173">**devices テーブル**を展開し、**[フィールド]** パネルで **manufacturer** データ フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-173">Expand the **devices table** and select the **manufacturer** data field in the **Fields** panel.</span></span>
4. <span data-ttu-id="d1a55-174">**manufacturer** データ フィールドをレポート キャンバスのツリーマップ グラフにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-174">Drag the **manufacturer** data field to the Treemap chart on the report canvas.</span></span>
5. <span data-ttu-id="d1a55-175">**devices** テーブルの **deviceKey** データ フィールドを、**[視覚化]** ウィンドウの **[値]** セクションにドラッグして、**[データ フィールドをここにドラッグ]** ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-175">Drag the **deviceKey** data field from the **devices** table to the **Values** section under the **Visualizations** pane and drop on the box labeled **Drag data field here**.</span></span>  
<span data-ttu-id="d1a55-176">組織内のデバイスの製造元の分布を示すビジュアルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-176">You now have a visual that shows us the distribution of manufacturers of devices within your organization.</span></span>

![ツリーマップとデータ](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a><span data-ttu-id="d1a55-178">フィルターを追加する</span><span class="sxs-lookup"><span data-stu-id="d1a55-178">Add a filter</span></span>

<span data-ttu-id="d1a55-179">アプリを使った追加の質問に回答できるように、ツリーマップにフィルターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d1a55-179">You can add a filter to your treemap so that you can answer additional questions using your app.</span></span> 

1. <span data-ttu-id="d1a55-180">レポート キャンバスを選択し、**[視覚化]** の**スライサー アイコン** (![ツリーマップとデータ](media/reports-create-slicer.png)) を選択してフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-180">Select the report canvas, and then select the **Slicer icon** ( ![Treemap with data](media/reports-create-slicer.png) ) under **Visualizations** to add a filter.</span></span>
2. <span data-ttu-id="d1a55-181">**ownerTypes** テーブルを探し、**ownerTypeName** データ フィールドを **[視覚化]** パネルの **[フィルター]** セクションにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-181">Find the **ownerTypes** table and drag the **ownerTypeName** data field under the **Filters** section in the **Visualizations** panel.</span></span>  
   <span data-ttu-id="d1a55-182">devices テーブルに、デバイスが会社所有か個人所有かを示すコードを含む **OwnerTypeKey** データ フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="d1a55-182">Under the devices table, there's a data field called **OwnerTypeKey** that contains a code as to whether a device is company-owned or personal.</span></span> <span data-ttu-id="d1a55-183">このフィルターにはフレンドリー名を表示したいので、**ownerTypes** テーブルを探し、**ownerTypeName** をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d1a55-183">Since you would like to show friendly names in this filter, look for the **ownerTypes** table and drag the **ownerTypeName**.</span></span> <span data-ttu-id="d1a55-184">これは、データ モデルがテーブル間のリレーションシップをサポートする方法の例です。</span><span class="sxs-lookup"><span data-stu-id="d1a55-184">This is an example of how the data model supports relationships between tables.</span></span>

![ツリーマップとフィルター](media/reports-create-08_ownertype.png)

<span data-ttu-id="d1a55-186">会社所有デバイスと個人所有デバイスを切り替えて分布の違いを見ることができる対話型フィルターができました。</span><span class="sxs-lookup"><span data-stu-id="d1a55-186">You now have an interactive filter that can be used to toggle between company owned and personally owned devices to see how the distribution changes.</span></span>

1. <span data-ttu-id="d1a55-187">会社所有デバイスの分布を表示するには **Company** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-187">Select **Company** to see that the company owned device distribution.</span></span>
2. <span data-ttu-id="d1a55-188">個人所有デバイスを表示するには **Personal** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a55-188">Select **Personal** to see the personally owned devices.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1a55-189">次の手順</span><span class="sxs-lookup"><span data-stu-id="d1a55-189">Next steps</span></span>

 - <span data-ttu-id="d1a55-190">Power BI のドキュメントで、Power BI Desktop での[リレーションシップの作成と管理](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/)についてさらに学習してください。</span><span class="sxs-lookup"><span data-stu-id="d1a55-190">Learn more about [creating and managing relationships](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) in the Power BI Desktop in the Power BI documentation.</span></span>
 - <span data-ttu-id="d1a55-191">[Intune データ ウェアハウス モデル](https://docs.microsoft.com/intune/reports-ref-data-model)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d1a55-191">Consult the [Intune Data Warehouse Model](https://docs.microsoft.com/intune/reports-ref-data-model).</span></span>