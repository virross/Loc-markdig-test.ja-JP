---
title: "ボリューム購入アプリを管理する"
description: "Intune を使用して、アプリ ストアからボリューム購入したアプリを管理する方法について説明します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 674c8f4c-00be-4c69-85b7-cf7bdaa71c94
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9b23100e1b609574733cbba3d9c8b25d61ad15ec
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="manage-volume-purchased-apps-using-microsoft-intune"></a><span data-ttu-id="a97f1-103">Microsoft Intune を使用してボリューム購入アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="a97f1-103">Manage volume-purchased apps using Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="a97f1-104">一部のアプリ ストアでは、社内で実行するアプリの複数のライセンスを購入できます。</span><span class="sxs-lookup"><span data-stu-id="a97f1-104">Some app stores give you the ability to purchase multiple licenses for an app that you want to run in your company.</span></span> <span data-ttu-id="a97f1-105">これは、購入したアプリの複数コピーを追跡する管理オーバーヘッドを削減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a97f1-105">This helps you reduce the administrative overhead of tracking multiple purchased copies of apps.</span></span>

<span data-ttu-id="a97f1-106">Microsoft Intune では、このようなプログラムを通じて購入したアプリを管理するために、アプリ ストアからライセンス情報をインポートし、使用したライセンスの数を追跡し、所有しているより多くのアプリをインストールできないようにします。</span><span class="sxs-lookup"><span data-stu-id="a97f1-106">Microsoft Intune helps you manage apps that you purchased through such a program by importing the license information from the app store, tracking how many of the licenses you have used, and preventing you from installing more copies of the app than you own.</span></span>

## <a name="which-types-of-apps-can-you-manage"></a><span data-ttu-id="a97f1-107">管理できるアプリの種類</span><span class="sxs-lookup"><span data-stu-id="a97f1-107">Which types of apps can you manage?</span></span>

<span data-ttu-id="a97f1-108">Intune では、iOS アプリ ストアとビジネス向け Microsoft ストアからボリューム購入したアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a97f1-108">With Intune, you can manage apps that you purchased in volume from the iOS app store, and the Microsoft Store for Business.</span></span>
<span data-ttu-id="a97f1-109">各ストアからライセンスを購入したアプリを管理する方法については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a97f1-109">To discover how to manage licensed apps from each store, choose one of the topics below:</span></span>

- [<span data-ttu-id="a97f1-110">iOS のボリューム購入アプリの管理</span><span class="sxs-lookup"><span data-stu-id="a97f1-110">Manage iOS volume-purchased apps</span></span>](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md)
- [<span data-ttu-id="a97f1-111">ビジネス向け Microsoft ストアからボリューム購入したアプリの管理</span><span class="sxs-lookup"><span data-stu-id="a97f1-111">Manage volume-purchased apps from the Microsoft Store for Business</span></span>](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md)
