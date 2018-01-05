---
title: "Azure で Intune を使用して Windows デバイスを管理する際の考慮事項"
description: "Azure で Intune を使用して、組織の Windows デバイスを管理する際の考慮事項です。"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f4018f505626b05dc84be509ca1e42cefff94b90
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a><span data-ttu-id="33786-103">Azure コンソールと従来の Intune PC クライアントでの Intune</span><span class="sxs-lookup"><span data-stu-id="33786-103">Intune on Azure console and legacy Intune PC Client</span></span>

<span data-ttu-id="33786-104">Intune は最近、Azure ベースの SaaS アプリケーション サービス アーキテクチャに移行しました。</span><span class="sxs-lookup"><span data-stu-id="33786-104">Intune recently moved to an Azure-based SaaS application service architecture.</span></span> <span data-ttu-id="33786-105">Azure はスケール、容量、およびパフォーマンスの面で大幅に改善されています。</span><span class="sxs-lookup"><span data-stu-id="33786-105">Azure provides significant improvements in scale, capacity, and performance.</span></span> <span data-ttu-id="33786-106">この移行により、Intune の管理エクスペリエンスが強化され、Azure Portal のワークフローが最適化されています。</span><span class="sxs-lookup"><span data-stu-id="33786-106">This transition also offers enhanced Intune admin experiences and optimized workflows in the Azure portal.</span></span> 

<span data-ttu-id="33786-107">Azure で Intune を使用して組織の Windows デバイスを管理する場合、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="33786-107">When using Intune on Azure to manage your organization’s Windows devices, consider the following points:</span></span>

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a><span data-ttu-id="33786-108">従来の PC クライアント機能が使用できるのは Silverlight コンソールのみです。</span><span class="sxs-lookup"><span data-stu-id="33786-108">Legacy PC Client features are only available in the Silverlight console</span></span>

<span data-ttu-id="33786-109">Intune PC クライアント管理ワークフローでは [Silverlight ベースの Intune 管理コンソール](https://manage.microsoft.com/)が使用されており、次のような影響があります。</span><span class="sxs-lookup"><span data-stu-id="33786-109">The Intune PC Client management workflows use the [Silverlight-based Intune Admin Console](https://manage.microsoft.com/), which has the following consequences:</span></span>

- <span data-ttu-id="33786-110">Intune PC クライアントを使用する非グループ化管理タスクのすべてで Silverlight コンソールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33786-110">For all non-grouping management tasks using the Intune PC Client, you must use the Silverlight console.</span></span>
- <span data-ttu-id="33786-111">グループを管理する場合、[Azure Portal で Intune](https://portal.azure.com/) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33786-111">When managing groups, you must use the [Intune on Azure portal](https://portal.azure.com/).</span></span> <span data-ttu-id="33786-112">Intune では従来の Intune グループの代わりに Azure AD グループを使用するようになったため、この要件が存在します。</span><span class="sxs-lookup"><span data-stu-id="33786-112">This requirement exists because Intune now uses Azure AD Groups instead of legacy Intune Groups.</span></span> 

<span data-ttu-id="33786-113">Azure AD グループへの切り替えのために、Silverlight コンソール ダッシュボード ビューで "グループ ベース" のフィルター処理が若干変わりました。</span><span class="sxs-lookup"><span data-stu-id="33786-113">Because of the switch to Azure AD Groups, “group-based” filtering in the Silverlight console dashboard views has changed slightly.</span></span> <span data-ttu-id="33786-114">更新された Silverlight UI でフィルター処理を行うには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="33786-114">To filter in the updated Silverlight UI, follow these steps:</span></span>

1. <span data-ttu-id="33786-115">ビューを選択します。</span><span class="sxs-lookup"><span data-stu-id="33786-115">Select a view.</span></span>
2. <span data-ttu-id="33786-116">**[フィルター]** ボックスで、フィルター処理の基準となるグループの名前を入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="33786-116">In the **Filters** box, enter the name of the group that you want to filter by and press enter.</span></span> <span data-ttu-id="33786-117">これにより、リスト ビューがその特定グループ内のデバイスにフィルターされます。</span><span class="sxs-lookup"><span data-stu-id="33786-117">This will filter the list view to the devices in that particular group.</span></span>

   ![](media/intune_on_azure/image01.png)

## <a name="manage-windows-10-devices-by-using-mdm"></a><span data-ttu-id="33786-118">MDM を使用した Windows 10 デバイスの管理</span><span class="sxs-lookup"><span data-stu-id="33786-118">Manage Windows 10 devices by using MDM</span></span>

<span data-ttu-id="33786-119">従来の Intune PC クライアントを使用する代わりに、[Windows 10 デバイスを管理するモバイル デバイス管理 (MDM)](https://docs.microsoft.com/intune/device-restrictions-windows-10) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33786-119">We recommend that you use [Mobile Device Management (MDM) to manage your Windows 10 devices](https://docs.microsoft.com/intune/device-restrictions-windows-10) instead of using the legacy Intune PC client.</span></span> <span data-ttu-id="33786-120">MDM を使用した Windows 10 デバイスの管理機能は、Azure Portal 上の Intune で提供されています。</span><span class="sxs-lookup"><span data-stu-id="33786-120">The ability to manage Windows 10 via MDM is available in the Intune on Azure portal.</span></span> <span data-ttu-id="33786-121">Windows 10 の MDM には、従来の Intune PC クライアントでは提供されていない、多くの新しい管理およびセキュリティ機能があります。</span><span class="sxs-lookup"><span data-stu-id="33786-121">Windows 10 MDM provides many new management and security capabilities that are not available via the legacy Intune PC client.</span></span>

## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a><span data-ttu-id="33786-122">Intune PC クライアントを使用した Windows 7 の管理の継続</span><span class="sxs-lookup"><span data-stu-id="33786-122">Continue to manage Windows 7 by using Intune PC Client</span></span>

<span data-ttu-id="33786-123">MDM を使用して管理できない Windows 7 では、Silverlight コンソールのみで、既存の Intune PC クライアント機能のサポートが継続されます。</span><span class="sxs-lookup"><span data-stu-id="33786-123">For Windows 7, which can’t be managed by using MDM, we will continue to support existing Intune PC Client capabilities in the Silverlight console only.</span></span> <span data-ttu-id="33786-124">Windows 10 にアップグレードする場合、MDM 管理への移行を検討してください。</span><span class="sxs-lookup"><span data-stu-id="33786-124">Consider migrating to MDM management when you upgrade to Windows 10.</span></span>

## <a name="mdm-capabilities"></a><span data-ttu-id="33786-125">MDM の機能</span><span class="sxs-lookup"><span data-stu-id="33786-125">MDM Capabilities</span></span>

<span data-ttu-id="33786-126">PC クライアントと MDM 機能の詳細な比較については、[Windows PC をコンピューターやモバイル デバイスとして管理する場合の比較](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="33786-126">For a detailed comparison between PC Client and MDM capabilities, see [Compare managing Windows PCs as computers or mobile devices](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).</span></span> <span data-ttu-id="33786-127">MDM の更新プログラムにより、MDM に登録されている Windows 10 デバイスに、Win 32 アプリ用のオプションの評価を含む新しい管理機能が引き続き組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="33786-127">MDM updates will continue to bring new management capabilities to MDM-enrolled, Windows 10 devices, inclusive of evaluating options for Win 32 apps.</span></span> <span data-ttu-id="33786-128">サービスへの最新リリースの追加については、「[新機能](https://docs.microsoft.com/intune/whats-new)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="33786-128">View the [What’s New](https://docs.microsoft.com/intune/whats-new) for the latest release additions to the service.</span></span>

## <a name="switch-from-pc-client-to-mdm"></a><span data-ttu-id="33786-129">PC クライアントから MDM への切り替え</span><span class="sxs-lookup"><span data-stu-id="33786-129">Switch from PC Client to MDM</span></span>

<span data-ttu-id="33786-130">Intune PC クライアントでの Windows 10 デバイス管理から MDM での管理に切り替えるには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="33786-130">To switch from managing Windows 10 devices with the Intune PC Client to managing with MDM, follow these steps:</span></span>

1. <span data-ttu-id="33786-131">Silverlight コンソールで、**選択的ワイプ**を実行して PC クライアントからデバイスを登録解除します。</span><span class="sxs-lookup"><span data-stu-id="33786-131">In the Silverlight console, perform a **Selective wipe** to un-enroll the device from the PC Client.</span></span>
  ![](media/intune_on_azure/image02.png)
2. <span data-ttu-id="33786-132">[MDM (および/または Azure AD Join)](https://docs.microsoft.com/intune/windows-enroll) を使用してデバイスを再登録します。</span><span class="sxs-lookup"><span data-stu-id="33786-132">Re-enroll the device by using [MDM (and/or Azure AD Join)](https://docs.microsoft.com/intune/windows-enroll).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="33786-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="33786-133">Next steps</span></span>
[<span data-ttu-id="33786-134">Windows デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="33786-134">Enroll Windows devices</span></span>](https://docs.microsoft.com/intune/windows-enroll)

 
