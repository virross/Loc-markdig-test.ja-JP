---
title: "SDK を使用してアプリで MAM を有効にする"
description: "このトピックでは、Intune APP SDK を使用する必要がある理由について概説します。"
keywords: 
author: mattbriggs
ms.author: mabriggs
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 26b00081-7c05-4969-ace1-0585e44d5cd2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 56e288559f5556f08060f80a5f195e93124a9d63
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="use-the-sdk-to-enable-apps-for-mobile-application-management"></a><span data-ttu-id="bdffa-103">Use the SDK to enable apps for mobile application management (アプリでモバイル アプリケーション管理を実行できるよう SDK を使用する)</span><span class="sxs-lookup"><span data-stu-id="bdffa-103">Use the SDK to enable apps for mobile application management</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="bdffa-104">iOS または Android アプリの特定の機能を Intune で管理できるようにするには、Microsoft Intune App SDK を使用します。</span><span class="sxs-lookup"><span data-stu-id="bdffa-104">Use the Microsoft Intune App SDK to let Intune manage certain features of your iOS or Android apps.</span></span> <span data-ttu-id="bdffa-105">Intune での管理に向けた対応化が済んだら、アプリにポリシーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="bdffa-105">After your app is enabled, you can deploy policies to the app.</span></span> <span data-ttu-id="bdffa-106">それらの機能をポリシーから使用することによって、会社のデータが保護されます。</span><span class="sxs-lookup"><span data-stu-id="bdffa-106">These policies use those features to help protect your corporate data.</span></span> <span data-ttu-id="bdffa-107">SDK で実装できる保護には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="bdffa-107">Examples of the types of protections that you can implement with the SDK are:</span></span>

-   <span data-ttu-id="bdffa-108">会社のドキュメントをクラウドにコピーすることを禁止する。</span><span class="sxs-lookup"><span data-stu-id="bdffa-108">Prevent users from copying corporate documents to the cloud.</span></span>

-   <span data-ttu-id="bdffa-109">デバイスに保存するデータの暗号化をアプリに強制する</span><span class="sxs-lookup"><span data-stu-id="bdffa-109">Require encryption of data that the app saves to the device.</span></span>

-   <span data-ttu-id="bdffa-110">管理対象ブラウザーの使用を強制する</span><span class="sxs-lookup"><span data-stu-id="bdffa-110">Enforce the use of a managed browser.</span></span>

-   <span data-ttu-id="bdffa-111">会社のデータをアプリから遠隔消去する</span><span class="sxs-lookup"><span data-stu-id="bdffa-111">Remotely wipe corporate data from the app.</span></span>

<span data-ttu-id="bdffa-112">SDK を使用するためにはアプリのソース コードを書きかえる必要がありますが、SDK の大半の機能は、アプリの動作を変更せずに実装できます。</span><span class="sxs-lookup"><span data-stu-id="bdffa-112">You need access to the app's source code to use the SDK, but you can enable most of the SDK features without having to change the app's behavior.</span></span>

<span data-ttu-id="bdffa-113">SDK の概要については、「[概要](/intune/app-sdk-get-started)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdffa-113">For an overview of the SDK, see the [Overview](/intune/app-sdk-get-started).</span></span>

### <a name="see-also"></a><span data-ttu-id="bdffa-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdffa-114">See also</span></span>
[<span data-ttu-id="bdffa-115">Microsoft Intune によるモバイル アプリケーション管理のためにアプリを準備する方法を決める</span><span class="sxs-lookup"><span data-stu-id="bdffa-115">Decide how to prepare apps for mobile application management with Microsoft Intune</span></span>](/intune/apps-prepare-mobile-application-management)