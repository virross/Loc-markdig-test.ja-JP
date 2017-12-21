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
ms.openlocfilehash: 24baa001c735ff6f9354d8992591c0848ef6fe48
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="retire-apps-using-microsoft-intune"></a><span data-ttu-id="35b48-103">Microsoft Intune を使用してアプリをインベントリから削除する</span><span class="sxs-lookup"><span data-stu-id="35b48-103">Retire apps using Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="35b48-104">アプリをインベントリから削除するには、アプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="35b48-104">To retire an app, you simply uninstall it.</span></span> <span data-ttu-id="35b48-105">Intune を使用してアプリを展開および管理すると、そのアプリをアンインストールするプロセスは、モバイル デバイスと Windows PC の両方で同じになります。</span><span class="sxs-lookup"><span data-stu-id="35b48-105">When you deploy and manage apps with Intune, the process for uninstalling the app is the same for both mobile devices and Windows PCs.</span></span> <span data-ttu-id="35b48-106">そのアプリでは、この手順が成功するようにアンインストール処理がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="35b48-106">The app must support the uninstallation process for this procedure to succeed.</span></span>

## <a name="uninstall-an-app"></a><span data-ttu-id="35b48-107">アプリをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="35b48-107">Uninstall an app</span></span>

1.  <span data-ttu-id="35b48-108">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[アプリ]** &gt; **[アプリ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="35b48-108">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.</span></span>

2.  <span data-ttu-id="35b48-109">アンインストールする (既に展開した) アプリを選択し、**[展開の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35b48-109">Select the app you want to uninstall (one that has been previously deployed), and then choose **Manage Deployment**.</span></span>

3.  <span data-ttu-id="35b48-110">**[展開アクション]** ページで、 **[承認]** 列の **[アンインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35b48-110">On the **Deployment Action** page, select **Uninstall** from the **Approval** column.</span></span>

<span data-ttu-id="35b48-111">デバイスまたはコンピューターで次にアプリが確認されるときに、そのアプリはアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="35b48-111">When the device or computer next checks for apps, the app will be uninstalled.</span></span>

### <a name="see-also"></a><span data-ttu-id="35b48-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="35b48-112">See also</span></span>
[<span data-ttu-id="35b48-113">Microsoft Intune でアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="35b48-113">Add apps in Microsoft Intune</span></span>](add-apps.md)
