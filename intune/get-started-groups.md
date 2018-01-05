---
title: "グループの概要"
titleSuffix: Azure portal
description: "ユーザーをグループにまとめ、ユーザーがアクセスできるポリシーやアプリの管理を簡単にします。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6d176a3331f52e6d9faadf356792503266a0b73f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-groups"></a><span data-ttu-id="b9832-103">グループの概要</span><span class="sxs-lookup"><span data-stu-id="b9832-103">Get started with groups</span></span>

<span data-ttu-id="b9832-104">グループは、ユーザーを管理し、会社のリソースに社員がアクセスする行為を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9832-104">Groups are used to manage your users, and control your employees' access to your company resources.</span></span> <span data-ttu-id="b9832-105">リソースはディレクトリに含まれますが、SaaS アプリや SharePoint サイトなど、外部リソースの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b9832-105">These resources can be part of your directory or can be external resources, like SaaS apps or SharePoint sites.</span></span>

<span data-ttu-id="b9832-106">Microsoft Intune は Azure Active Directory (Azure AD) を利用し、会社のリソースへのアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="b9832-106">Microsoft Intune uses Azure Active Directory (Azure AD) to manage access to company resources.</span></span> <span data-ttu-id="b9832-107">このアクセスは、ディレクトリのロールを使用して制御されます。</span><span class="sxs-lookup"><span data-stu-id="b9832-107">This access is controlled using roles in the directory.</span></span> <span data-ttu-id="b9832-108">次に Intune でモバイル デバイスに関してこのアクセスが管理されます。該当グループのメンバーであれば、リソースへのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="b9832-108">Intune then manages this access for mobile devices, which allows members of that group to access resources.</span></span>

## <a name="how-do-i-create-a-group"></a><span data-ttu-id="b9832-109">グループの作成方法</span><span class="sxs-lookup"><span data-stu-id="b9832-109">How do I create a group?</span></span>

1. <span data-ttu-id="b9832-110">[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b9832-110">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="b9832-111">**[リソースの検索]** を利用し、**[Intune]** を探します。</span><span class="sxs-lookup"><span data-stu-id="b9832-111">Using **Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="b9832-112">**[Microsoft Intune]** ブレードを開いたら、**[グループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9832-112">Once you've opened the **Microsoft Intune** blade, select **Groups**.</span></span>
4. <span data-ttu-id="b9832-113">**[ユーザーとグループ - すべてのグループ]** ブレードで、**[新しいグループ]** コマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="b9832-113">On the **Users and groups – All groups** blade, select the **New group** command.</span></span>
5. <span data-ttu-id="b9832-114">**[グループ]** ブレードで、グループの**名前**と**説明**を追加します。</span><span class="sxs-lookup"><span data-stu-id="b9832-114">On the **Group** blade, add a **Name** and **Description** for the group.</span></span>
6. <span data-ttu-id="b9832-115">**[メンバーシップの種類]** に **[割り当て済み]** を設定します。</span><span class="sxs-lookup"><span data-stu-id="b9832-115">Set the **Membership type** as **Assigned**.</span></span> <span data-ttu-id="b9832-116">テスト グループに対して **Office 機能は有効にしないでください**。</span><span class="sxs-lookup"><span data-stu-id="b9832-116">Do not **Enable Office features** for the test group.</span></span>
7. <span data-ttu-id="b9832-117">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9832-117">Click **Create**.</span></span>

<span data-ttu-id="b9832-118">グループが作成されたら、**[すべてのグループ]** の一覧に表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="b9832-118">If you've successfully created a group, it should appear in the list of **All groups**.</span></span> <span data-ttu-id="b9832-119">表示されない場合、別のグループを作成してみてください。</span><span class="sxs-lookup"><span data-stu-id="b9832-119">If it doesn't appear there, try to create another group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9832-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="b9832-120">Next steps</span></span>

<span data-ttu-id="b9832-121">[ポリシーの概要](get-started-policies.md) - ユーザーが自分のデバイスで許可のない操作を行うことを禁止する目的でポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b9832-121">[Get started with policies](get-started-policies.md) - Create policies to prevent users from doing unauthorized things with their devices.</span></span>

## <a name="learn-more"></a><span data-ttu-id="b9832-122">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b9832-122">Learn more</span></span>

* [<span data-ttu-id="b9832-123">Intune でグループを利用し、登録制限を設定する</span><span class="sxs-lookup"><span data-stu-id="b9832-123">Set enrollment restrictions using groups in Intune</span></span>](groups-add.md)
* [<span data-ttu-id="b9832-124">Azure Active Directory でグループを利用し、会社のリソースへのアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="b9832-124">Manage access to company resources using groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
