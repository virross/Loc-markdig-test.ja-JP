---
title: "デバイスとアプリのライフサイクルの概要"
description: "Intune でのデバイスとアプリのライフサイクルの概要。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38e08253-14a0-4cc4-87be-7b110c12a523
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ae4fffcf9d8d6a801eef1d2bb810810cb3c7047a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="overview-of-device-and-app-lifecycles"></a><span data-ttu-id="14ddb-103">デバイスとアプリのライフサイクルの概要</span><span class="sxs-lookup"><span data-stu-id="14ddb-103">Overview of device and app lifecycles</span></span>

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="14ddb-104">ニーズは組織ごとに異なりますが、他の運用ニーズがどのようなものであっても、すべての組織が継続的に実施する必要のある特定の一般的な手順があります。</span><span class="sxs-lookup"><span data-stu-id="14ddb-104">Although the needs of individual organizations might differ, there are certain common steps that all organizations need to take on an ongoing basis, whatever their other operational needs.</span></span> <span data-ttu-id="14ddb-105">これは 2 つの主なカテゴリにグループ化でき、**ライフサイクル**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="14ddb-105">These can be grouped into two main categories, which are termed **lifecycles**.</span></span> <span data-ttu-id="14ddb-106">展開ライフサイクルは、有効にしようとしているシナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="14ddb-106">The deployment lifecycle you follow depends on the scenario you’re trying to enable.</span></span> <span data-ttu-id="14ddb-107">たとえば、デバイス ライフサイクルとアプリ ライフサイクルのどちらか一方だけが必要なこともあれば、両方とも必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="14ddb-107">For example, you might need only the device lifecycle or the app lifecycle, or you might need both.</span></span>

<span data-ttu-id="14ddb-108">![MDM とアプリのライフサイクル](./media/device-app-lifecycle.png "モバイル デバイスとアプリのライフサイクル")</span><span class="sxs-lookup"><span data-stu-id="14ddb-108">![The MDM and app lifecycle](./media/device-app-lifecycle.png "mobile device and app lifecycles")</span></span>

<span data-ttu-id="14ddb-109">管理のため、すべてのデバイスにはライフサイクルがあります。</span><span class="sxs-lookup"><span data-stu-id="14ddb-109">For management purposes, all devices have a lifecycle.</span></span> <span data-ttu-id="14ddb-110">ライフサイクルは、デバイスを登録すると開始され、デバイスをインベントリから削除するまで続きます。</span><span class="sxs-lookup"><span data-stu-id="14ddb-110">It starts when you enroll the device and extends through its retirement.</span></span> <span data-ttu-id="14ddb-111">[デバイス管理のライフサイクルに関する記事](device-lifecycle.md)では、デバイスを登録する方法、デバイスを構成および保護する方法、管理対象から除外する方法について説明されています。</span><span class="sxs-lookup"><span data-stu-id="14ddb-111">The [device management lifecycle](device-lifecycle.md) walks you through how to enroll the device, how to configure and protect it, and then how to remove it from management.</span></span>

<span data-ttu-id="14ddb-112">同様に、使用するアプリには独自の[アプリ ライフサイクル](app-lifecycle.md)があり、Intune へのアプリの追加から、不要になったときの削除までの、すべての手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="14ddb-112">Similarly, apps you work with have their own [app lifecycle](app-lifecycle.md) that includes steps ranging from adding an app to Intune, all the way through to removing them when they are no longer required.</span></span>
