---
title: "Intune データ ウェアハウスを使用する | Microsoft Docs"
description: "Intune データ ウェアハウスを使用して、社内のモバイル環境を分析できるレポートを構築します。"
keywords: "Intune データ ウェアハウス"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 44d3322801c25dfa2816f3ebf80d21a7a75b294c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-the-intune-data-warehouse"></a><span data-ttu-id="958c8-104">Intune データ ウェアハウスを使用する</span><span class="sxs-lookup"><span data-stu-id="958c8-104">Use the Intune Data Warehouse</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="958c8-105">Intune データ ウェアハウスを使用して、社内のモバイル環境を分析できるレポートを構築します。</span><span class="sxs-lookup"><span data-stu-id="958c8-105">Use the Intune Data Warehouse to build reports that provide insight into your enterprise mobile environment.</span></span> <span data-ttu-id="958c8-106">たとえば、次のようなレポートがあります。</span><span class="sxs-lookup"><span data-stu-id="958c8-106">For example, some of the reports include:</span></span>
-   <span data-ttu-id="958c8-107">ライセンス購入の最適化に利用できる Intune に登録されているユーザーの傾向</span><span class="sxs-lookup"><span data-stu-id="958c8-107">Trend of users enrolling in Intune so you can optimize your license purchases</span></span>
-   <span data-ttu-id="958c8-108">モバイル デバイスの状態を確認できるアプリと OS バージョンの内訳</span><span class="sxs-lookup"><span data-stu-id="958c8-108">App and OS versions breakdown so you can review that status of mobile devices</span></span>
-   <span data-ttu-id="958c8-109">ポリシーの更新をスムーズにロールアウトできる登録とデバイス コンプライアンスの傾向</span><span class="sxs-lookup"><span data-stu-id="958c8-109">Enrollment and device compliance trends so you can smoothly roll out policy updates</span></span>

<span data-ttu-id="958c8-110">データ ウェアハウスを使用すると、モバイル環境について Azure Portal よりも詳細な情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="958c8-110">The Data Warehouse provides you access to more information about your mobile environment than the Azure portal.</span></span> <span data-ttu-id="958c8-111">Intune データ ウェアハウスでは、次の情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="958c8-111">With the Intune Data Warehouse you can access:</span></span>

  -  <span data-ttu-id="958c8-112">Intune の履歴データ</span><span class="sxs-lookup"><span data-stu-id="958c8-112">Historical Intune data</span></span>
  -  <span data-ttu-id="958c8-113">日単位の更新データ</span><span class="sxs-lookup"><span data-stu-id="958c8-113">Data refreshed on a daily cadence</span></span>
  -  <span data-ttu-id="958c8-114">OData 標準を使用するデータ モデル</span><span class="sxs-lookup"><span data-stu-id="958c8-114">A data model using the OData standard</span></span>

> [!Note]
> <span data-ttu-id="958c8-115">System Center Configuration Manager と Microsoft Intune でハイブリッド モバイル デバイス管理 (MDM) を使用している場合は、SCCM からデータを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="958c8-115">If you are a using hybrid mobile device management (MDM) with System Center Configuration Manager and Microsoft Intune, you want to retrieve your data from SCCM.</span></span> <span data-ttu-id="958c8-116">Intune データが含まれるのは Intune データ ウェアハウスのみです。</span><span class="sxs-lookup"><span data-stu-id="958c8-116">The Intune Data Warehouse only contains Intune data.</span></span> <span data-ttu-id="958c8-117">カスタム レポートには SCCM Power BI ダッシュボードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="958c8-117">You can use an SCCM Power BI dashboard for your custom reports.</span></span> <span data-ttu-id="958c8-118">詳細については、「[Announcing the Power BI solution template for System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template)」(System Center Configuration Manager 用 Power BI ソリューション テンプレートの発表) と</span><span class="sxs-lookup"><span data-stu-id="958c8-118">For more information, see "[Announcing the Power BI solution template for System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template)."</span></span> <span data-ttu-id="958c8-119">「[Create a Power BI report and dashboard](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard)」(Power BI レポートとダッシュボードの作成) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958c8-119">and "[Create a Power BI report and dashboard](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard)."</span></span>


> [!Important]  
> <span data-ttu-id="958c8-120">データ ウェアハウスの最新機能については、ベータ バージョンを使用して試すことができます。</span><span class="sxs-lookup"><span data-stu-id="958c8-120">You can try out the latest functionality of the Data Warehouse by using the beta version.</span></span> <span data-ttu-id="958c8-121">ベータ バージョンを使用するには、URL にクエリ パラメーター `api-version=beta` を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="958c8-121">To use the beta version, your URL must contain the query parameter `api-version=beta`.</span></span> <span data-ttu-id="958c8-122">ベータ バージョンは、サポートされるサービスとして一般公開される前の機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="958c8-122">The beta version offers features before they are made generally available as a supported service.</span></span> <span data-ttu-id="958c8-123">Intune に新しい機能が追加されると、ベータ バージョンの動作とデータ コントラクトが変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="958c8-123">As Intune adds new features, the beta version may change behavior and data contracts.</span></span> <span data-ttu-id="958c8-124">カスタム コードまたはレポート ツールがベータ バージョンに依存していると、今後の更新プログラムで使用できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="958c8-124">Any custom code or reporting tools dependent on the beta version may break with ongoing updates.</span></span>

<span data-ttu-id="958c8-125">**次のステップ**</span><span class="sxs-lookup"><span data-stu-id="958c8-125">**Next steps**</span></span>

- <span data-ttu-id="958c8-126">リンクを取得し、Power BI を使用して分析します。</span><span class="sxs-lookup"><span data-stu-id="958c8-126">Get a link and use Power BI to get insight.</span></span> <span data-ttu-id="958c8-127">手順については、「[Connect to the Intune Data Warehouse with Power BI](reports-proc-get-a-link-powerbi.md)」(Power BI で Intune データ ウェアハウスに接続する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958c8-127">For instructions, see [Connect to the Intune Data Warehouse with Power BI](reports-proc-get-a-link-powerbi.md).</span></span>
- <span data-ttu-id="958c8-128">リンクを使用して Power BI でカスタム レポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="958c8-128">With your link, create a custom report with Power BI.</span></span> <span data-ttu-id="958c8-129">方法は、「[Power BI で OData フィードからレポートを作成する](reports-proc-create-with-odata.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958c8-129">For instructions, see [Create a report from the OData feed with Power BI](reports-proc-create-with-odata.md).</span></span>
- <span data-ttu-id="958c8-130">Intune データ ウェアハウス API、データ モデル、エンティティ間の関係の詳細については、<!-- , and an example of creating a custom client to retrieve data,-->「[Intune データ ウェアハウス API](reports-nav-intune-data-warehouse.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958c8-130">Get more information about the Intune Data Warehouse API, the data model, and relationships between entities<!-- , and an example of creating a custom client to retrieve data,--> see [Intune Data Warehouse API](reports-nav-intune-data-warehouse.md).</span></span>