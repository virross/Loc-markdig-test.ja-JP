---
title: "Windows ユーザーがアプリを入手する方法"
description: "ユーザーが Windows アプリを使用できるようにするための方法"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e471fed8-19f0-4b37-aaa2-65f28a6b4794
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4bee575ef95b418dd5fe670ef5c7e2985f9bc8d5
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-your-windows-users-get-their-apps"></a><span data-ttu-id="ab754-103">Windows ユーザーがアプリを入手する方法</span><span class="sxs-lookup"><span data-stu-id="ab754-103">How your Windows users get their apps</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="ab754-104">Microsoft Intune を通して配布したアプリをユーザーがどこでどのように取得するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ab754-104">Use this information to understand how and where your users get the apps that you distribute through Microsoft Intune.</span></span>

<span data-ttu-id="ab754-105">**必要なアプリ**は、管理者によって必要とされ、必要最小限のユーザー操作でデバイスにインストールされるアプリです (プラットフォームによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="ab754-105">**Required apps** are required by the administrator and that are installed on the device with minimal user involvement, depending on the platform.</span></span>

<span data-ttu-id="ab754-106">**使用可能なアプリ**は、ポータル サイト アプリの一覧に表示され、ユーザーがインストールを選択できるアプリです。</span><span class="sxs-lookup"><span data-stu-id="ab754-106">**Available apps** are provided in the Company Portal app list and that a user might choose to install.</span></span>

<span data-ttu-id="ab754-107">**管理対象のアプリ**は、ポリシーによって管理でき、Intune によって "ラップ" されているか、Intune アプリ ソフトウェア開発キット (SDK) で構築されています。</span><span class="sxs-lookup"><span data-stu-id="ab754-107">**Managed apps** can be managed through policies and that have been "wrapped" by Intune or have been built with the Intune App Software Development Kit (SDK).</span></span> <span data-ttu-id="ab754-108">これらのアプリは Intune によって管理することができます。また、これらのアプリにはアプリ保護ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="ab754-108">These apps can be managed by Intune, and app protection policies can be applied to them.</span></span>

<span data-ttu-id="ab754-109">**管理対象外のアプリ**は、ポリシーによって管理でき、Intune によってラップされていないアプリまたは Intune アプリ SDK を組み込んでいないアプリです。</span><span class="sxs-lookup"><span data-stu-id="ab754-109">**Unmanaged apps** can be managed through policies and that have not been wrapped by Intune or that do not incorporate the Intune App SDK.</span></span> <span data-ttu-id="ab754-110">アプリ保護にアプリケーション ポリシーを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab754-110">App protection policies cannot be applied to these apps.</span></span>

### <a name="see-also"></a><span data-ttu-id="ab754-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab754-111">See also</span></span>
<span data-ttu-id="ab754-112">[Android ユーザーがアプリを入手する方法](end-user-apps-android.md)
[iOS ユーザーがアプリを入手する方法](end-user-apps-android.md)</span><span class="sxs-lookup"><span data-stu-id="ab754-112">[How your Android users get their apps](end-user-apps-android.md)
[How your iOS users get their apps](end-user-apps-android.md)</span></span>