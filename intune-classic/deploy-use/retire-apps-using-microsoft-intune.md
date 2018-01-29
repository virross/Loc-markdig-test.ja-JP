---
title: "アプリをインベントリから削除する"
description: "Intune を使用してアプリを削除またはアンインストールする方法について説明します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a3fadf497e5db147d12ecf1e32343e94222c65e9
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="retire-apps-using-microsoft-intune"></a><span data-ttu-id="fe04e-103">Microsoft Intune を使用してアプリをインベントリから削除する</span><span class="sxs-lookup"><span data-stu-id="fe04e-103">Retire apps using Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="fe04e-104">アプリをインベントリから削除するには、アプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="fe04e-104">To retire an app, you simply uninstall it.</span></span> <span data-ttu-id="fe04e-105">Intune を使用してアプリを展開および管理すると、そのアプリをアンインストールするプロセスは、モバイル デバイスと Windows PC の両方で同じになります。</span><span class="sxs-lookup"><span data-stu-id="fe04e-105">When you deploy and manage apps with Intune, the process for uninstalling the app is the same for both mobile devices and Windows PCs.</span></span> <span data-ttu-id="fe04e-106">そのアプリでは、この手順が成功するようにアンインストール処理がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fe04e-106">The app must support the uninstallation process for this procedure to succeed.</span></span>

## <a name="uninstall-an-app"></a><span data-ttu-id="fe04e-107">アプリをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="fe04e-107">Uninstall an app</span></span>

1.  <span data-ttu-id="fe04e-108">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[アプリ]** &gt; **[アプリ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="fe04e-108">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.</span></span>

2.  <span data-ttu-id="fe04e-109">アンインストールする (既に展開した) アプリを選択し、**[展開の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe04e-109">Select the app you want to uninstall (one that has been previously deployed), and then choose **Manage Deployment**.</span></span>

3.  <span data-ttu-id="fe04e-110">**[展開アクション]** ページで、 **[承認]** 列の **[アンインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe04e-110">On the **Deployment Action** page, select **Uninstall** from the **Approval** column.</span></span>

<span data-ttu-id="fe04e-111">デバイスまたはコンピューターで次にアプリが確認されるときに、そのアプリはアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="fe04e-111">When the device or computer next checks for apps, the app will be uninstalled.</span></span>

### <a name="see-also"></a><span data-ttu-id="fe04e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe04e-112">See also</span></span>
[<span data-ttu-id="fe04e-113">Microsoft Intune でアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="fe04e-113">Add apps in Microsoft Intune</span></span>](add-apps.md)
