---
title: "Intune で Mobile Threat Defense コネクタを有効にする"
titlesuffix: Azure portal
description: "Intune で Mobile Threat Defense コネクタを有効にします。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2808eb3751ee0187f7b58091fc3c3ad3fcbb3229
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="enable-mobile-threat-defense-in-intune"></a><span data-ttu-id="47145-103">Intune で Mobile Threat Defense を有効にする</span><span class="sxs-lookup"><span data-stu-id="47145-103">Enable Mobile Threat Defense in Intune</span></span>

> [!NOTE] 
> <span data-ttu-id="47145-104">このトピックは、すべての Mobile Threat Defense パートナーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="47145-104">This topic applies to all Mobile Threat Defense partners.</span></span>

<span data-ttu-id="47145-105">Intune で Mobile Threat Defense (MTD) 接続を有効にするには、MTD パートナー コンソールで Intune コネクタが構成済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="47145-105">To enable the Mobile Threat Defense (MTD) connection in Intune, you should have already configured the Intune Connector in the MTD partner console.</span></span>

## <a name="to-enable-the-mtd-connector"></a><span data-ttu-id="47145-106">MTD コネクタを有効にするには</span><span class="sxs-lookup"><span data-stu-id="47145-106">To enable the MTD connector</span></span>

1. <span data-ttu-id="47145-107">[Azure Portal](https://portal.azure.com) に移動し、Intune 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="47145-107">Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span> <span data-ttu-id="47145-108">正常にサインインすると、**Azure ダッシュボード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="47145-108">After you've successfully signed in, you see the **Azure Dashboard**.</span></span>

2. <span data-ttu-id="47145-109">**Azure ダッシュボード**で、左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="47145-109">On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="47145-110">**[Intune]** を選択すると、**Intune ダッシュボード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="47145-110">Choose **Intune**, the **Intune Dashboard** opens.</span></span>

4. <span data-ttu-id="47145-111">**Intune ダッシュ ボード**で、**[デバイスのポリシー準拠]** を選択し、**[セットアップ]** セクションで **[Mobile Threat Defense]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="47145-111">On the **Intune Dashboard**, choose **Device compliance**, then choose **Mobile Threat Defense** under the **Setup** section.</span></span>

5. <span data-ttu-id="47145-112">**[Mobile Threat Defense]** ブレードで、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="47145-112">On the **Mobile Threat Defense** blade, choose **Add**.</span></span>

6. <span data-ttu-id="47145-113">**[セットアップする Mobile Threat Defense コネクタ]** として、ドロップダウン リストから MTD ソリューションを選択します。</span><span class="sxs-lookup"><span data-stu-id="47145-113">Choose your MTD solution as the **Mobile Threat Defense connector to setup** from the drop-down list.</span></span>

    ![Intune Azure Portal での MTD のセットアップ](./media/enable-mtd-connector-1.png)

7. <span data-ttu-id="47145-115">組織の要件に応じてトグルのオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="47145-115">Enable the toggle options according to your organization's requirements.</span></span>

## <a name="mtd-toggle-options"></a><span data-ttu-id="47145-116">MTD トグル オプション</span><span class="sxs-lookup"><span data-stu-id="47145-116">MTD toggle options</span></span>

<span data-ttu-id="47145-117">組織の要件に従って、有効にすべき MTD トグル オプションを決定できます。</span><span class="sxs-lookup"><span data-stu-id="47145-117">You can decide which MTD toggle options you need to enable according to your organization's requirements.</span></span> <span data-ttu-id="47145-118">詳細を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="47145-118">Here's more details:</span></span>

- <span data-ttu-id="47145-119">**[Connect Android 4.1+ devices to [MTD partner name] for Work MTD]\(Android 4.1+ デバイスを [MTD パートナー名] for Work MTD に接続する\)**: このオプションを有効にすると、Android 4.1+ デバイスはセキュリティ上のリスクを Intune に報告します。</span><span class="sxs-lookup"><span data-stu-id="47145-119">**Connect Android 4.1+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.</span></span>
    - <span data-ttu-id="47145-120">**[データが受信されない場合、非準拠としてマークする]**: Intune がこのプラットフォーム上のデバイスに関するデータを MTD パートナーから受信しない場合は、そのデバイスを非準拠とみなします。</span><span class="sxs-lookup"><span data-stu-id="47145-120">**Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.</span></span>
<br></br>
- <span data-ttu-id="47145-121">**[Connect iOS 8.0+ devices to [MTD partner name] for Work MTD]\(iOS 8.0+ デバイスを [MTD パートナー名] for Work MTD に接続する\)**: このオプションを有効にすると、Android 4.1+ デバイスはセキュリティ上のリスクを Intune に報告します。</span><span class="sxs-lookup"><span data-stu-id="47145-121">**Connect iOS 8.0+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.</span></span>
    - <span data-ttu-id="47145-122">**[データが受信されない場合、非準拠としてマークする]**: Intune がこのプラットフォーム上のデバイスに関するデータを MTD パートナーから受信しない場合は、そのデバイスを非準拠とみなします。</span><span class="sxs-lookup"><span data-stu-id="47145-122">**Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.</span></span>
<br></br>
- <span data-ttu-id="47145-123">**[サポートされていない OS バージョンをブロックする]**: デバイスがサポートされる最低バージョン以前のオペレーティング システムを実行している場合は、ブロックします。</span><span class="sxs-lookup"><span data-stu-id="47145-123">**Block unsupported OS versions**: Block if the device is running an operating system less than the minimum supported version.</span></span>

- <span data-ttu-id="47145-124">**[パートナーが無応答になるまでの日数]**: 接続が失われたためにパートナーが応答していないと Intune が判断するまでの、非アクティブ状態の日数。</span><span class="sxs-lookup"><span data-stu-id="47145-124">**Number of days until partner is unresponsive**: Number of days of inactivity before Intune considers teh partner to be unresponsive because the connection is lost.</span></span> <span data-ttu-id="47145-125">Intune は、応答しない MTD パートナーのコンプライアンス対応状態を無視します。</span><span class="sxs-lookup"><span data-stu-id="47145-125">Intune ignores compliance state for unresponsive MTD partners.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="47145-126">MTD アプリは、デバイス コンプライアンスと条件付きアクセス ポリシー ルールを作成する前に、追加して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="47145-126">You must add and assign the MTD apps before creating the device compliance and the conditional access policy rules.</span></span> <span data-ttu-id="47145-127">これにより、MTD アプリはエンド ユーザーがインストールできる状態になり、アプリをインストールするとエンド ユーザーは電子メールや他の会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="47145-127">This ensures that the MTD app is ready and available for end users to install before they can get access to email or other company resources.</span></span>

> [!TIP]
> <span data-ttu-id="47145-128">[Mobile Threat Defense] ブレードで、**[接続の状態]** や、Intune と MTD パートナー間の **[最終同期]** 時刻を確認できます。</span><span class="sxs-lookup"><span data-stu-id="47145-128">You can see the **Connection status** and the **Last synchronized** time between Intune and the MTD partner from the Mobile Threat Defense blade.</span></span>
