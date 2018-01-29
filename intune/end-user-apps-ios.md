---
title: "iOS ユーザーがアプリを入手する方法"
description: "エンド ユーザーが iOS アプリを使用できるようにするための方法"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d831758a19ebbed8a5a8a77984b21033285e8cb5
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-your-ios-users-get-their-apps"></a><span data-ttu-id="55c9c-103">iOS ユーザーがアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="55c9c-103">How your iOS users get their apps</span></span>

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="55c9c-104">Microsoft Intune を通して配布したアプリをエンド ユーザーがどこでどのように取得するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="55c9c-104">Use this information to understand how and where your end users get the apps that you distribute through Microsoft Intune.</span></span>

<span data-ttu-id="55c9c-105">**必要なアプリ** - 管理者が必須に設定しているアプリと、必要最小限のユーザー操作でデバイスにインストールされるアプリです (プラットフォームによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="55c9c-105">**Required apps**--Apps that are required by the admin and that are installed on the device with minimal user involvement, depending on the platform.</span></span>

<span data-ttu-id="55c9c-106">**使用可能なアプリ** - ポータル サイト アプリの一覧に表示されるアプリおよびユーザーが必要に応じてインストールするアプリです。</span><span class="sxs-lookup"><span data-stu-id="55c9c-106">**Available apps**--Apps that are provided in the Company Portal app list and that a user may optionally choose to install.</span></span>

<span data-ttu-id="55c9c-107">**管理対象のアプリ** -- ポリシーによって管理できて、Intune によって "ラップされた" アプリまたは Intune アプリ ソフトウェア開発キット (SDK) で構築されたアプリです。</span><span class="sxs-lookup"><span data-stu-id="55c9c-107">**Managed apps**--Apps that can be managed through policies and that have been "wrapped" by Intune or have been built with the Intune App Software Development Kit (SDK).</span></span> <span data-ttu-id="55c9c-108">これらのアプリは Intune によって管理することができます。また、これらのアプリにはアプリ保護ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="55c9c-108">These apps can be managed by Intune, and app protection policies can be applied to them.</span></span>

<span data-ttu-id="55c9c-109">**管理対象外のアプリ** -- ポリシーによって管理でき、Intune によってラップされていないアプリまたは Intune アプリ SDK を組み込んでいないアプリです。</span><span class="sxs-lookup"><span data-stu-id="55c9c-109">**Unmanaged apps**--Apps that can be managed through policies and that have not been wrapped by Intune or that do not incorporate the Intune App SDK.</span></span> <span data-ttu-id="55c9c-110">これらのアプリにアプリケーション ポリシーを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="55c9c-110">Application policies cannot be applied to these apps.</span></span>

<span data-ttu-id="55c9c-111">Apple の制限により、基幹業務アプリおよび管理対象アプリ ストアのアプリはポータル サイト アプリに表示されません。</span><span class="sxs-lookup"><span data-stu-id="55c9c-111">Apple restrictions prohibit line-of-business and managed App Store apps from being listed in the Company Portal app.</span></span> <span data-ttu-id="55c9c-112">この問題を回避するため、iOS 用ポータル サイト アプリのアプリ タイルでは、次のように、ユーザーは単一の場所 (ポータル サイト Web サイト) のさまざまなビューですべてのアプリを確認できます。</span><span class="sxs-lookup"><span data-stu-id="55c9c-112">To get around this issue, the tiles in the Company Portal app for iOS point users to different views in a single location (the Company Portal website) for all of their apps.</span></span>

<span data-ttu-id="55c9c-113">登録済みユーザーは、ポータル サイト アプリのアプリ画面で、以下のタイルをタップしてアプリを取得します。</span><span class="sxs-lookup"><span data-stu-id="55c9c-113">Enrolled users get their apps by tapping on the following tiles on the Apps screen of the Company Portal app:</span></span>

- <span data-ttu-id="55c9c-114">**[すべてのアプリ]**。[ポータル Web サイト](https://portal.manage.microsoft.com)の [すべて] タブのすべてのアプリのリストをポイントします。</span><span class="sxs-lookup"><span data-stu-id="55c9c-114">**All Apps** points to a list of all apps in the ALL tab of the [Company Portal website](https://portal.manage.microsoft.com).</span></span>

- <span data-ttu-id="55c9c-115">**[おすすめアプリ]**。ポータル Web サイトの [おすすめ] タブを表示します。</span><span class="sxs-lookup"><span data-stu-id="55c9c-115">**Featured Apps** take users to the FEATURED tab of the Company Portal website.</span></span>

- <span data-ttu-id="55c9c-116">**[カテゴリ]**。ポータル Web サイトの [カテゴリ] タブをポイントします。</span><span class="sxs-lookup"><span data-stu-id="55c9c-116">**Categories** points to the CATEGORIES tab of the Company Portal website.</span></span>


![iOS ポータル サイト アプリの画面](./media/ios-cp-app-main-apps-screen.png)

<span data-ttu-id="55c9c-118">アプリを追加し、これらのタイルに配置する方法については、「[Intune に登録されたデバイスのアプリを追加する](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55c9c-118">For information on how to add apps and put them in these tiles, see [Add apps for enrolled devices to Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).</span></span>

### <a name="see-also"></a><span data-ttu-id="55c9c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="55c9c-119">See also</span></span>
[<span data-ttu-id="55c9c-120">Android ユーザーがアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="55c9c-120">How your Android users get their apps</span></span>](end-user-apps-android.md)

[<span data-ttu-id="55c9c-121">Windows ユーザーがアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="55c9c-121">How your Windows users get their apps</span></span>](end-user-apps-windows.md)
