---
title: "現在のユーザー - Intune データ ウェアハウス |Microsoft ドキュメント"
description: "Intune データ ウェアハウス API のエンティティ コレクションのユーザー カテゴリに関するリファレンス トピック。"
keywords: "Intune データ ウェアハウス"
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cabf39f603ac93a0716594c44174908e7c999e5c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-current-user-entity"></a><span data-ttu-id="e8626-104">現在のユーザー エンティティの参照</span><span class="sxs-lookup"><span data-stu-id="e8626-104">Reference for Current User entity</span></span>

<span data-ttu-id="e8626-105">**現在のユーザー**カテゴリには、データ モデルでユーザーのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8626-105">The **Current User** category contains user properties in the data model.</span></span> <span data-ttu-id="e8626-106">**現在のユーザー** エンティティ コレクションは、現在アクティブなユーザーに限られています。</span><span class="sxs-lookup"><span data-stu-id="e8626-106">The **Current User** entity collection is limited to currently active users.</span></span> <span data-ttu-id="e8626-107">エンティティには、現在ライセンスが割り当てられているすべての Azure Active Directory ユーザーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8626-107">The entity contains all the Azure Active Directory users that are currently assigned a license.</span></span> <span data-ttu-id="e8626-108">ライセンスは、Intune ライセンス、ハイブリッド ライセンス、または Microsoft Office 365 ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="e8626-108">The license could be an Intune license, a Hybrid license, or a Microsoft Office 365 license.</span></span> <span data-ttu-id="e8626-109">ユーザーが削除された場合、それらが表示されません、現在のユーザー コレクションにします。</span><span class="sxs-lookup"><span data-stu-id="e8626-109">If a user has been removed, they will not be represented in the Current User collection.</span></span> <span data-ttu-id="e8626-110">ユーザー状態の変更の履歴を含むコレクションについては、「[ユーザー エンティティのリファレンス](reports-ref-user.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8626-110">For a collection that contains a history of changes in user state, see [Reference for user entity](reports-ref-user.md).</span></span>


## <a name="current-user"></a><span data-ttu-id="e8626-111">現在のユーザー</span><span class="sxs-lookup"><span data-stu-id="e8626-111">Current User</span></span>

<span data-ttu-id="e8626-112">**現在のユーザー**エンティティには、企業内の割り当てられたライセンスを持つすべての Azure Active Directory (Azure AD) ユーザーが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e8626-112">The **Current User** entity lists all the Azure Active Directory (Azure AD) users with assigned licenses in your enterprise.</span></span>

| <span data-ttu-id="e8626-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e8626-113">Property</span></span>  | <span data-ttu-id="e8626-114">説明</span><span class="sxs-lookup"><span data-stu-id="e8626-114">Description</span></span> | <span data-ttu-id="e8626-115">例</span><span class="sxs-lookup"><span data-stu-id="e8626-115">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="e8626-116">UserKey</span><span class="sxs-lookup"><span data-stu-id="e8626-116">UserKey</span></span> |<span data-ttu-id="e8626-117">データ ウェアハウス内のユーザーを示す一意識別子 - 代理キー。</span><span class="sxs-lookup"><span data-stu-id="e8626-117">Unique identifier of the user in the data warehouse - surrogate key.</span></span> |<span data-ttu-id="e8626-118">123</span><span class="sxs-lookup"><span data-stu-id="e8626-118">123</span></span> |
| <span data-ttu-id="e8626-119">UserId</span><span class="sxs-lookup"><span data-stu-id="e8626-119">UserId</span></span> |<span data-ttu-id="e8626-120">ユーザーを示す一意識別子 - UserKey と似ていますが、ナチュラル キーです。</span><span class="sxs-lookup"><span data-stu-id="e8626-120">Unique identifier of the user  - similar to UserKey, but is a natural key.</span></span> |<span data-ttu-id="e8626-121">b66bc706-ffff-7437-0340-032819502773</span><span class="sxs-lookup"><span data-stu-id="e8626-121">b66bc706-ffff-7437-0340-032819502773</span></span> |
| <span data-ttu-id="e8626-122">UserEmail</span><span class="sxs-lookup"><span data-stu-id="e8626-122">UserEmail</span></span> |<span data-ttu-id="e8626-123">ユーザーの電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="e8626-123">Email address of the user.</span></span> |John@constoso.com |
| <span data-ttu-id="e8626-124">UPN</span><span class="sxs-lookup"><span data-stu-id="e8626-124">UPN</span></span> | <span data-ttu-id="e8626-125">ユーザーのユーザー プリンシパル名。</span><span class="sxs-lookup"><span data-stu-id="e8626-125">User principal name of the user.</span></span> | John@constoso.com |
| <span data-ttu-id="e8626-126">表示名</span><span class="sxs-lookup"><span data-stu-id="e8626-126">DisplayName</span></span> |<span data-ttu-id="e8626-127">ユーザーの表示名。</span><span class="sxs-lookup"><span data-stu-id="e8626-127">Display name of the user.</span></span> |<span data-ttu-id="e8626-128">John</span><span class="sxs-lookup"><span data-stu-id="e8626-128">John</span></span> |
| <span data-ttu-id="e8626-129">IntuneLicensed</span><span class="sxs-lookup"><span data-stu-id="e8626-129">IntuneLicensed</span></span> |<span data-ttu-id="e8626-130">ユーザーに Intune のライセンスがあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e8626-130">Specifies if this user is Intune licensed or not.</span></span> |<span data-ttu-id="e8626-131">真/偽</span><span class="sxs-lookup"><span data-stu-id="e8626-131">True/False</span></span> |
| <span data-ttu-id="e8626-132">StartDateInclusiveUTC</span><span class="sxs-lookup"><span data-stu-id="e8626-132">StartDateInclusiveUTC</span></span> |<span data-ttu-id="e8626-133">このユーザーがデータ ウェアハウスで作成されたときの UTC 日時。</span><span class="sxs-lookup"><span data-stu-id="e8626-133">Date and time in UTC when this user was created in the data warehouse.</span></span> |<span data-ttu-id="e8626-134">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="e8626-134">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="e8626-135">RowLastModifiedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="e8626-135">RowLastModifiedDateTimeUTC</span></span> |<span data-ttu-id="e8626-136">このユーザーがデータ ウェアハウスで最後に変更されたときの UTC 日時。</span><span class="sxs-lookup"><span data-stu-id="e8626-136">Date and time in UTC when this user was last modified in the data warehouse.</span></span> |<span data-ttu-id="e8626-137">11/23/2016 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="e8626-137">11/23/2016 12:00:00 AM</span></span> |

## <a name="next-steps"></a><span data-ttu-id="e8626-138">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e8626-138">Next steps</span></span>
 - <span data-ttu-id="e8626-139">使用することができます、**ユーザー**ユーザー データを現在アクティブではないユーザーに展開するエンティティのコレクション。</span><span class="sxs-lookup"><span data-stu-id="e8626-139">You can use the **Users** entity collection to expand the user data to users who are not currently active.</span></span> <span data-ttu-id="e8626-140">詳細については、「[ユーザー エンティティのリファレンス](reports-ref-user.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8626-140">For more information, see [Reference for user entity](reports-ref-user.md).</span></span>
 - <span data-ttu-id="e8626-141">データ ウェアハウスが Intune のユーザーの有効期間を追跡する方法の詳細については、「[Intune データ ウェアハウスのユーザー有効期間の表記](reports-ref-user-timeline.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e8626-141">Learn more about how the data warehouse tracks a user's lifetime in Intune, see [User lifetime representation in the Intune Data Warehouse](reports-ref-user-timeline.md).</span></span>
