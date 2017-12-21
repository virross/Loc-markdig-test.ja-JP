---
title: "Exchange On-Premises および Exchange Online の条件付きアクセス コンプライアンスを監視する"
titlesuffix: Azure portal
description: "Intune Azure ポータルを使用して、Exchange On-Premises および Exchange Online の条件付きアクセス コンプライアンスを監視します"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: be0c1cef0dd6562feb54724edbf8ae22072e3d95
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a><span data-ttu-id="800d6-103">Intune で Exchange On-Premises および Exchange Online の条件付きアクセス コンプライアンスを監視する</span><span class="sxs-lookup"><span data-stu-id="800d6-103">Monitor conditional access compliance for on-premises Exchange and Exchange Online in Intune</span></span>

<span data-ttu-id="800d6-104">Intune 1704 リリース以降では、管理者は、内部設置型 Exchange Connector またはサービス間コネクタ (Exchange Online Connector) を使って、Intune と同期化される Exchange ActiveSync デバイス レコードに関するレポート情報を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="800d6-104">Beginning with Intune 1704 release, admins can see reporting information related to Exchange ActiveSync device records that are synchronized with Intune through either the on-premises Exchange Connector or the Intune service-to-service connector (Exchange Online connector).</span></span> <span data-ttu-id="800d6-105">条件付きアクセス コンプライアンス レポートでは、さまざまな同期状態のデバイスの概要が提供されます。</span><span class="sxs-lookup"><span data-stu-id="800d6-105">The conditional access compliance reporting provides a summary of devices with different synchronization states:</span></span>

-   <span data-ttu-id="800d6-106">**許可**</span><span class="sxs-lookup"><span data-stu-id="800d6-106">**Allow**</span></span>

-   <span data-ttu-id="800d6-107">**ブロック**</span><span class="sxs-lookup"><span data-stu-id="800d6-107">**Block**</span></span>

-   <span data-ttu-id="800d6-108">**検疫**</span><span class="sxs-lookup"><span data-stu-id="800d6-108">**Quarantine**</span></span>

## <a name="to-monitor-conditional-access-compliance"></a><span data-ttu-id="800d6-109">条件付きアクセス コンプライアンスを監視するには</span><span class="sxs-lookup"><span data-stu-id="800d6-109">To monitor conditional access compliance</span></span>

1.  <span data-ttu-id="800d6-110">[Azure Portal](https://portal.azure.com/) に移動し、Intune の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="800d6-110">Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="800d6-111">正常にサインインすると、**Azure ダッシュボード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="800d6-111">After you've successfully signed in, you see the **Azure Dashboard**.</span></span>

3.  <span data-ttu-id="800d6-112">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="800d6-112">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

4.  <span data-ttu-id="800d6-113">**[Intune]** を選択すると、**Intune ダッシュボード**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="800d6-113">Choose **Intune**, you see the **Intune Dashboard**.</span></span>

5.  <span data-ttu-id="800d6-114">**[条件付きアクセス]** を選択し、**[概要]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="800d6-114">Choose **Conditional Access**, then choose **Overview**.</span></span>

6.  <span data-ttu-id="800d6-115">チャートの 3 つの領域 (**[ブロック済み]**、**[検疫]**、または **[許可]**) のいずれかを選び、条件付きアクセス コンプライアンス レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="800d6-115">Choose one of the three areas (**Blocked**, **Quarantine** or **Allowed**) on the chart to view your conditional access compliance reporting.</span></span>

    ![条件付きアクセス ダッシュボード](./media/CA-reporting-intune-1.png)

<span data-ttu-id="800d6-117">3 つの領域のいずれかを選ぶと、許可、ブロック、または検疫されているデバイスについての詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="800d6-117">Once you choose one of three areas, you can see more details about devices being allowed, blocked or quarantined.</span></span>

<span data-ttu-id="800d6-118">特定のデバイスにドリルダウンしてさらに詳細な情報を見ることもできます。</span><span class="sxs-lookup"><span data-stu-id="800d6-118">You can also drill down in specific devices to see more details.</span></span> <span data-ttu-id="800d6-119">たとえば、次の図で選ばれているデバイスはブロックされています。</span><span class="sxs-lookup"><span data-stu-id="800d6-119">For example, the device chosen on the image below is blocked.</span></span> <span data-ttu-id="800d6-120">Intune では、条件付きアクセス コンプライアンス レポート ブレードから企業データを削除できます。</span><span class="sxs-lookup"><span data-stu-id="800d6-120">Intune gives you the option of removing corporate data from the conditional access compliance report blade.</span></span>

![条件付きアクセス デバイス詳細レポート](./media/CA-reporting-intune-3.png)

<span data-ttu-id="800d6-122">デバイスの詳細ブレードでは、さらに情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="800d6-122">At the device details blade, you can see more information:</span></span>

-   <span data-ttu-id="800d6-123">**[概要]:** OS のバージョン、デバイス モデル、所有権、シリアル番号、デバイスの製造元、電話番号、デバイスの最終チェックイン日時など、デバイスのプロパティを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="800d6-123">**Overview:** You can see device properties like: OS version, device model, ownership, serial number, device manufacturer, phone number and last time the device checked in.</span></span>

-   <span data-ttu-id="800d6-124">**[プロパティ]:** デバイスの所有権 (個人または企業) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="800d6-124">**Properties:** You can set the device ownership (Personal or Corporate).</span></span>

-   <span data-ttu-id="800d6-125">**[ハードウェア]:** [概要] の情報に加えて、ストレージの詳細 (合計容量と空き容量)、システム エンクロージャ、ネットワークの詳細、ネットワーク サービス、およびその他の条件付きアクセスのブロックの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="800d6-125">**Hardware:** It provides the information you see on the Overview, and also storage details (total space and free space), system enclosure, network details, network service, and more conditional access blocking details.</span></span>

-   <span data-ttu-id="800d6-126">**[検出されたアプリ]:** デバイスにインストールされているすべてのアプリケーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="800d6-126">**Discovered Apps:** It shows all applications installed at your device.</span></span> <span data-ttu-id="800d6-127">インストールされているアプリの一覧を .CSV 形式にエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="800d6-127">You can also export the list of installed apps to .CSV format.</span></span>

-   <span data-ttu-id="800d6-128">**[ポリシー準拠状況]:** すべてのデバイス コンプライアンス ポリシーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="800d6-128">**Compliance:** It shows all device compliance policy details.</span></span>

-   <span data-ttu-id="800d6-129">**[デバイス構成]:** すべてのデバイス構成の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="800d6-129">**Device Configuration:** It shows all device configuration details.</span></span>

-   <span data-ttu-id="800d6-130">**[Exchange へのアクセス]:** 条件付きアクセス ポリシーを適用した後のデバイスの状態についてさらに詳しく確認できます。</span><span class="sxs-lookup"><span data-stu-id="800d6-130">**Exchange Access:** Here you can learn more about the device state after applying conditional access policies.</span></span>
