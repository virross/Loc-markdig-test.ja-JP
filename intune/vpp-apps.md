---
title: "Intune によるボリューム購入アプリとブックの管理"
titlesuffix: Azure portal
description: "Intune を使用して、ストアからのボリューム購入アプリとブックの使用状況を管理および監視する方法について説明します。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 85b07f57-661a-4bc8-87d2-7b446d5cf4d6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aad49f436a73687fc76fe8ee3c1d46ebde468c3c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="manage-volume-purchased-apps-and-books-with-microsoft-intune"></a><span data-ttu-id="609ea-103">Microsoft Intune によるボリューム購入アプリとブックの管理</span><span class="sxs-lookup"><span data-stu-id="609ea-103">Manage volume-purchased apps and books with Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a><span data-ttu-id="609ea-104">概要</span><span class="sxs-lookup"><span data-stu-id="609ea-104">Introduction</span></span>

<span data-ttu-id="609ea-105">一部のアプリ ストアでは、社内で使用するアプリやブックの複数のライセンスを購入できます。</span><span class="sxs-lookup"><span data-stu-id="609ea-105">Some app stores give you the ability to purchase multiple licenses for an app or books that you want to use in your company.</span></span> <span data-ttu-id="609ea-106">ライセンスの一括購入は、購入したアプリとブックの複数コピーを追跡する管理オーバーヘッドを削減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="609ea-106">Buying licenses in bulk can help you reduce the administrative overhead of tracking multiple purchased copies of apps and books.</span></span>

<span data-ttu-id="609ea-107">Microsoft Intune を使用することで、このようなプログラムを通じて購入したアプリとブックを管理できます。</span><span class="sxs-lookup"><span data-stu-id="609ea-107">Microsoft Intune helps you manage apps and books that you purchased through such a program.</span></span> <span data-ttu-id="609ea-108">ストアからライセンス情報をインポートし、使用したライセンスの数を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="609ea-108">You import license information from the store, and track how many licenses you have used.</span></span> <span data-ttu-id="609ea-109">このプロセスにより、所有している数より多くのアプリまたはブックのコピーがインストールされないようにできます。</span><span class="sxs-lookup"><span data-stu-id="609ea-109">This process helps to ensure that you don't install more copies of the app or book than you own.</span></span>

## <a name="which-types-of-apps-and-books-can-you-manage"></a><span data-ttu-id="609ea-110">管理できるアプリとブックの種類</span><span class="sxs-lookup"><span data-stu-id="609ea-110">Which types of apps and books can you manage?</span></span>

<span data-ttu-id="609ea-111">Intune では、iOS ストアからボリューム購入したアプリとブックを管理し、ビジネス向け Microsoft ストアからボリューム購入したアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="609ea-111">With Intune, you can manage apps and books that you purchased in volume from the iOS store, and manage apps that you purchased from the Microsoft Store for Business.</span></span> <span data-ttu-id="609ea-112">各ストアからライセンスを購入したアプリを管理する方法については、次のトピックのいずれかをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="609ea-112">To discover how to manage licensed apps from each store, choose one of the following topics:</span></span>

- [<span data-ttu-id="609ea-113">iOS のボリューム購入アプリの管理</span><span class="sxs-lookup"><span data-stu-id="609ea-113">Manage iOS volume-purchased apps</span></span>](vpp-apps-ios.md)
- [<span data-ttu-id="609ea-114">ビジネス向け Microsoft ストアからボリューム購入したアプリの管理</span><span class="sxs-lookup"><span data-stu-id="609ea-114">Manage volume-purchased apps from the Microsoft Store for Business</span></span>](windows-store-for-business.md)
- [<span data-ttu-id="609ea-115">Volume Purchase Program で購入した iOS 電子ブックを Microsoft Intune で管理する方法</span><span class="sxs-lookup"><span data-stu-id="609ea-115">How to manage iOS eBooks</span></span>](vpp-ebooks-ios.md)
