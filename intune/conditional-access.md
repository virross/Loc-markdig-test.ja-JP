---
title: "Intune での条件付きアクセス"
titlesuffix: Azure portal
description: "会社のリソースにアクセスするためにユーザーとデバイスが満たす必要のある条件を Microsoft Intune で定義する方法について説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6e2deb008b63fd9e9e9f37674c81745a0c8ccb04
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="whats-conditional-access"></a><span data-ttu-id="1e494-103">条件付きアクセスとは</span><span class="sxs-lookup"><span data-stu-id="1e494-103">What's conditional access?</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1e494-104">このトピックでは、Enterprise Mobility + Security (EMS) に適用される条件付きアクセスについて説明し、さらに Intune での条件付きアクセスの一般的なシナリオについても取り上げます。</span><span class="sxs-lookup"><span data-stu-id="1e494-104">This topic describes Conditional access as it applies to Enterprise Mobility + Security (EMS), and follows that with Conditional access common scenarios when using Intune.</span></span>

<span data-ttu-id="1e494-105">Enterprise Mobility + Security (EMS) 条件付きアクセスはスタンドアロン製品ではありませんが、EMS の一部であるすべてのサービスと製品にかかわるソリューションです。</span><span class="sxs-lookup"><span data-stu-id="1e494-105">Enterprise Mobility + Security (EMS) Conditional Access is not a standalone product, it’s a solution that takes part on all services and products that are part of the EMS.</span></span> <span data-ttu-id="1e494-106">細かいアクセス制御を提供することで会社のデータをセキュリティで保護し、任意の場所と任意のデバイスで最適な仕事ができるエクスペリエンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="1e494-106">It provides granular access control to keep your corporate data secure, while giving users an experience that allows them to do their best work from any device, and from any location.</span></span>

<span data-ttu-id="1e494-107">場所、デバイス、ユーザーの状態、アプリケーションの機密度に基づいて、会社のデータへのアクセスを制限する条件を定義できます。</span><span class="sxs-lookup"><span data-stu-id="1e494-107">You can define conditions that gate access to your corporate data based on location, device, user state, and application sensitivity.</span></span>

> [!NOTE] 
> <span data-ttu-id="1e494-108">条件付きアクセスは、その機能を[Office 365 サービス](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/)にも拡張しています。</span><span class="sxs-lookup"><span data-stu-id="1e494-108">Conditional Access also extends its capabilities to [Office 365 services](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).</span></span>

![条件付きアクセスのアーキテクチャ ダイアグラム](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a><span data-ttu-id="1e494-110">Intune での条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="1e494-110">Conditional access with Intune</span></span>

<span data-ttu-id="1e494-111">Intune では、モバイル デバイスのコンプライアンスとアプリ管理ポリシーを追加し、EMS 条件付きアクセスのソリューションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1e494-111">Intune adds mobile device compliance and app management policies to support the EMS Conditional Access solution.</span></span>

![EMS 使用時の Intune と条件付きアクセス](./media/intune-with-ca-1.png)

<span data-ttu-id="1e494-113">Intune での条件付きアクセスの使用方法</span><span class="sxs-lookup"><span data-stu-id="1e494-113">Ways to use conditional access with Intune:</span></span>

-   <span data-ttu-id="1e494-114">**デバイスに基づく条件付きアクセス**</span><span class="sxs-lookup"><span data-stu-id="1e494-114">**Device-based conditional access**</span></span>

    -   <span data-ttu-id="1e494-115">Exchange On-Premises の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="1e494-115">Conditional access for Exchange on-premises</span></span>

    -   <span data-ttu-id="1e494-116">ネットワーク アクセス制御に基づいた条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="1e494-116">Conditional access based on network access control</span></span>

    -   <span data-ttu-id="1e494-117">デバイスのリスクに基づいた条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="1e494-117">Conditional access based on device risk</span></span>

    -   <span data-ttu-id="1e494-118">Windows PC の条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="1e494-118">Conditional access for Windows PCs</span></span>

        -   <span data-ttu-id="1e494-119">企業所有</span><span class="sxs-lookup"><span data-stu-id="1e494-119">Corporate-owned</span></span>

        -   <span data-ttu-id="1e494-120">Bring Your Own Device (BYOD)</span><span class="sxs-lookup"><span data-stu-id="1e494-120">Bring your own device (BYOD)</span></span>

-   <span data-ttu-id="1e494-121">**アプリベースの条件付きアクセス**</span><span class="sxs-lookup"><span data-stu-id="1e494-121">**App-based conditional access**</span></span>

## <a name="next-steps"></a><span data-ttu-id="1e494-122">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1e494-122">Next steps</span></span>

[<span data-ttu-id="1e494-123">Intune での条件付きアクセスの一般的な使用方法</span><span class="sxs-lookup"><span data-stu-id="1e494-123">Common ways to use conditional access with Intune</span></span>](conditional-access-intune-common-ways-use.md)
