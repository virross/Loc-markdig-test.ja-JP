---
title: "Intune の概要"
titlesuffix: Azure portal
description: "簡単な一連の実地演習をこなし、Intune について学習します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b72021c802feb925bfc38b84c1e1b7cab35546a0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="what-can-intune-do-for-my-company"></a><span data-ttu-id="3ae0d-103">Intune が会社のためにできることとは。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-103">What can Intune do for my company?</span></span>

<span data-ttu-id="3ae0d-104">Intune はクラウドベースのエンタープライズ モビリティ管理 (EMM) サービスであり、会社のデータを守りながら、社員に生産的に働いてもらうことができます。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-104">Intune is a cloud-based enterprise mobility management (EMM) service that helps enable your workforce to be productive while keeping your corporate data protected.</span></span>

![Microsoft Intune の概要的アーキテクチャ図](/intune/media/intunearchitecture.svg)

<span data-ttu-id="3ae0d-106">モバイル デバイスの管理は大変な仕事になりうると理解されています。会社のためにさまざまな決定を行う必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-106">We understand that getting started with managing mobile devices can be difficult, since there are many different decisions that you'll need to make on behalf of your company.</span></span> <span data-ttu-id="3ae0d-107">以下の演習ではいくつかの作業を行い、Intune で会社のリソースを守る方法について理解します。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-107">These exercises take you through some tasks that help you understand how Intune can be used to protect your company resources.</span></span>

## <a name="what-are-the-exercises"></a><span data-ttu-id="3ae0d-108">演習の内容</span><span class="sxs-lookup"><span data-stu-id="3ae0d-108">What are the exercises?</span></span>

<span data-ttu-id="3ae0d-109">ページの左側にある目次を利用し、意図された順番で__入門__実地演習をこなします。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-109">You can follow the intended order of the __Getting Started__ hands-on activities using the table of contents on the left side of the page.</span></span> <span data-ttu-id="3ae0d-110">作業内容:</span><span class="sxs-lookup"><span data-stu-id="3ae0d-110">These tasks are:</span></span>

* <span data-ttu-id="3ae0d-111">[Azure 使用の概要](get-started-azure.md) - Azure Portal の構造とページ レイアウトの変更方法について理解します。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-111">[Get started with using Azure](get-started-azure.md) - Understand the anatomy of the Azure portal and how to make changes to the page you see.</span></span>
* <span data-ttu-id="3ae0d-112">[ユーザー管理の概要](get-started-users.md) - Intune にユーザーを追加し、モバイル デバイスで会社のリソースにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-112">[Get started with managing users](get-started-users.md) - Add a user to Intune to allow them to access company resources on mobile devices.</span></span>
* <span data-ttu-id="3ae0d-113">[グループの概要](get-started-groups.md) - ユーザーをグループにまとめ、ユーザーがアクセスできるポリシーやアプリの管理を簡単にします。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-113">[Get started with groups](get-started-groups.md) - Organize users into groups to make it easier to manage the policies and apps that they can access.</span></span>
* <span data-ttu-id="3ae0d-114">[ポリシーの概要](get-started-policies.md) - ユーザーが自分のデバイスで許可のない操作を行うことを禁止する目的でポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-114">[Get started with policies](get-started-policies.md) - Create policies to prevent users from doing unauthorized things with their devices.</span></span>
* <span data-ttu-id="3ae0d-115">[デバイス登録の概要](get-started-enroll.md) - iOS デバイスの登録手順を最初から最後まで行い、登録方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-115">[Get started enrolling devices](get-started-enroll.md) - Learn the enrollment experience by going through a full enrollment experience of an iOS device.</span></span>
* <span data-ttu-id="3ae0d-116">[アプリ追加の概要](get-started-apps.md) - 社員が仕事を行えるように、アプリを見つけ、デバイスに追加します。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-116">[Get started with adding apps](get-started-apps.md) - Find and add apps to devices to make it possible for your employees to get work done.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ae0d-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="3ae0d-117">Prerequisites</span></span>

<span data-ttu-id="3ae0d-118">始める前に、Intune の管理者/テナント アカウントを有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-118">Before you start, you must have an Intune admin and tenant account activated.</span></span> <span data-ttu-id="3ae0d-119">アカウントは[ここ](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20)で新規登録できます。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-119">You can sign up for those accounts [here](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).</span></span> <span data-ttu-id="3ae0d-120">現行のサブスクライバーも、ライブ テナントで以上の作業を完了できます。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-120">Current subscribers can also complete these activities in your live tenant.</span></span> <span data-ttu-id="3ae0d-121">これらの概要の記事では、テスト デバイスで作業することを前提とします。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-121">These getting started articles assume that you're working on test devices.</span></span>

<span data-ttu-id="3ae0d-122">また、すべての入門タスクを完了するためには、自分が組織のグローバル管理者になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-122">You also need to make sure that you are the global admin for your organization to complete all of the Get Started tasks.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ae0d-123">次の手順</span><span class="sxs-lookup"><span data-stu-id="3ae0d-123">Next steps</span></span>

<span data-ttu-id="3ae0d-124">[Azure 使用の概要](get-started-azure.md) - Azure Portal の構造とページ レイアウトの変更方法について理解します。</span><span class="sxs-lookup"><span data-stu-id="3ae0d-124">[Get started with using Azure](get-started-azure.md) - Understand the anatomy of the Azure portal and how to make changes to the page you see.</span></span>

## <a name="learn-more"></a><span data-ttu-id="3ae0d-125">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3ae0d-125">Learn more</span></span>

* [<span data-ttu-id="3ae0d-126">Intune とは</span><span class="sxs-lookup"><span data-stu-id="3ae0d-126">What is Intune?</span></span>](introduction-intune.md)
* [<span data-ttu-id="3ae0d-127">Azure Portal とは</span><span class="sxs-lookup"><span data-stu-id="3ae0d-127">What is the Azure portal?</span></span>](what-is-intune.md)
* [<span data-ttu-id="3ae0d-128">デバイスとアプリのライフサイクル</span><span class="sxs-lookup"><span data-stu-id="3ae0d-128">Device and app lifecycles</span></span>](introduction-device-app-lifecycles.md)
