---
title: "Intune データ ウェアハウスの変更ログ | Microsoft Docs"
description: "Intune のデータ ウェアハウス API の変更一覧。"
keywords: "Intune データ ウェアハウス"
author: erikre
ms.author: mabrigg
manager: erikre
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0d2625cda3fad8683571059d4ed5f75d6c7ae122
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a><span data-ttu-id="87f33-104">Intune データ ウェアハウス API の変更ログ</span><span class="sxs-lookup"><span data-stu-id="87f33-104">Change log for the Intune Data Warehouse API</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="87f33-105">常に Intune データ ウェアハウスの最新の更新プログラムをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="87f33-105">Keep current on updates to the Intune Data Warehouse.</span></span>

## <a name="1710"></a><span data-ttu-id="87f33-106">1710</span><span class="sxs-lookup"><span data-stu-id="87f33-106">1710</span></span>
<span data-ttu-id="87f33-107">_リリース日: 2017 年 11 月_</span><span class="sxs-lookup"><span data-stu-id="87f33-107">_Released November  2017_</span></span>

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a><span data-ttu-id="87f33-108">現在のユーザーという名前の新しいエンティティ コレクションは、現在アクティブなユーザー データに限られています <!-- 1544273 --></span><span class="sxs-lookup"><span data-stu-id="87f33-108">A new entity collection named Current User is limited to currently active user data <!-- 1544273 --></span></span>

<span data-ttu-id="87f33-109">**ユーザー**エンティティのコレクションには、社内で割り当てられたライセンスを持つすべての Azure Active Directory (Azure AD) ユーザーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="87f33-109">The **Users** entity collection contains all the Azure Active Directory (Azure AD) users with assigned licenses in your enterprise.</span></span> <span data-ttu-id="87f33-110">これらのレコードには、ユーザーが削除されている場合でも、データ コレクション期間中のユーザーの状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="87f33-110">These records include user states during the data collection period, even if the user has been removed.</span></span> <span data-ttu-id="87f33-111">たとえば、ユーザーが Intune に追加され、過去 1 か月の過程で削除されたとします。</span><span class="sxs-lookup"><span data-stu-id="87f33-111">For example, a user may be added to Intune and then removed during the course of the last month.</span></span> <span data-ttu-id="87f33-112">このユーザーがレポートの時点では存在しない一方で、ユーザーと状態はデータに存在します。</span><span class="sxs-lookup"><span data-stu-id="87f33-112">While this user is not present at the time of the report, the user and state are present in the data.</span></span> <span data-ttu-id="87f33-113">データ内のユーザーの履歴における存在の期間を示すレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="87f33-113">You could create a report that would show the duration of the user's historic presence in your data.</span></span>

<span data-ttu-id="87f33-114">これに対し、新しい**現在のユーザー** エンティティ コレクションには、削除されていないユーザーのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="87f33-114">In contrast, the new **Current User** entity collection only contains users who have not been removed.</span></span> <span data-ttu-id="87f33-115">**現在のユーザー** エンティティ コレクションには、現在アクティブなユーザーのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="87f33-115">The **Current User** entity collection only contains currently active users.</span></span> <span data-ttu-id="87f33-116">**現在のユーザー** エンティティ コレクションの詳細については、「[現在のユーザー エンティティのリファレンス](reports-ref-current-user.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="87f33-116">For information about the **current user** entity collection, see [Reference for current user entity](reports-ref-current-user.md).</span></span>

## <a name="1709"></a><span data-ttu-id="87f33-117">1709</span><span class="sxs-lookup"><span data-stu-id="87f33-117">1709</span></span>
<span data-ttu-id="87f33-118">_リリース日: 2017 年 10 月_</span><span class="sxs-lookup"><span data-stu-id="87f33-118">_Released October  2017_</span></span>

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a><span data-ttu-id="87f33-119">Intune データ ウェアハウスのデータ モデルに追加されたユーザー デバイス関連付けエンティティ コレクション <!-- 1187917 --></span><span class="sxs-lookup"><span data-stu-id="87f33-119">User device association entity collection added to Intune Data Warehouse data model <!-- 1187917 --></span></span>

<span data-ttu-id="87f33-120">ユーザーとデバイスのエンティティ コレクションを関連付けるユーザー デバイス関連付け情報を使って、レポートやデータの視覚エフェクトを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="87f33-120">You can now build reports and data visualizations using the user device association information that associates user and device entity collections.</span></span> <span data-ttu-id="87f33-121">このデータ モデルは、OData エンドポイントを使うか、カスタム クライアントを開発すると、[Data Warehouse Intune]\(データ ウェアハウス Intune\) ページから取得した Power BI ファイル (PBIX) を使ってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="87f33-121">The data model can be accessed through the Power BI file (PBIX) retrieved from the Data Warehouse Intune page, through the OData endpoint, or by developing a custom client.</span></span> <span data-ttu-id="87f33-122">詳細については、「[ユーザー デバイスの関連付け](reports-ref-user-device.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="87f33-122">For more information, see the [User Device Association](reports-ref-user-device.md).</span></span>

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a><span data-ttu-id="87f33-123">データ ウェアハウス データ モデルの新しいエンティティ <!-- 1479526 --><!-- --></span><span class="sxs-lookup"><span data-stu-id="87f33-123">New entities in the in Data Warehouse data model <!-- 1479526 --><!-- --></span></span>

 - <span data-ttu-id="87f33-124">[**UserDeviceAssociation**](reports-ref-user-device.md) というエンティティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="87f33-124">The entity, [**UserDeviceAssociation**](reports-ref-user-device.md), added.</span></span> <span data-ttu-id="87f33-125">**UserDeviceAssociation** には、組織内のユーザー デバイスの関連付けが含まれています。</span><span class="sxs-lookup"><span data-stu-id="87f33-125">**UserDeviceAssociation** contains user device associations in your organization.</span></span> <span data-ttu-id="87f33-126">ユーザーとデバイスのエンティティ コレクションを関連付けるユーザー デバイス関連付け情報を使って、レポートやデータの視覚エフェクトを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="87f33-126">You can now build reports and data visualizations using the user device association information that associates user and device entity collections.</span></span>  
 - <span data-ttu-id="87f33-127">[**IntuneManagementExtension**](reports-ref-intunemanagementextension.md) というエンティティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="87f33-127">The entity, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), added.</span></span> <span data-ttu-id="87f33-128">**IntuneManagementExtension** には、バージョンやインストール状態などの情報を追跡するモバイル デバイスのエンティティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="87f33-128">**IntuneManagementExtension** contains entities for mobile devices that track information such as version and installation status.</span></span>

## <a name="next-steps"></a><span data-ttu-id="87f33-129">次のステップ</span><span class="sxs-lookup"><span data-stu-id="87f33-129">Next steps</span></span>
 - <span data-ttu-id="87f33-130">[週ごとにまとめた Intune の新機能](whats-new.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f33-130">Learn [what’s new each week in Intune](whats-new.md).</span></span> <span data-ttu-id="87f33-131">今後の変更、サービスに関する重要なお知らせ、過去のリリースに関する情報も確認できます。</span><span class="sxs-lookup"><span data-stu-id="87f33-131">You can also find out about upcoming changes, important notices about the service, and information about past releases.</span></span>
 - <span data-ttu-id="87f33-132">[Microsoft Intune のブログ](http://go.microsoft.com/fwlink/?LinkID=273882)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f33-132">Read the [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882).</span></span>
