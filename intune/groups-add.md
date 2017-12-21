---
title: "Intune で登録制限を設定する"
titlesuffix: Azure portal
description: "Intune でプラットフォームごとに登録を制限し、デバイス登録の上限数を設定します。 \""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ddf5cc624685e684973b0e4ee85de609845f3bd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="add-groups-in-intune"></a><span data-ttu-id="a350f-104">Intune でグループを追加する</span><span class="sxs-lookup"><span data-stu-id="a350f-104">Add groups in Intune</span></span>
<span data-ttu-id="a350f-105">Intune では、デバイスとユーザーの管理に Azure Active Directory (AD) のグループを使用します。</span><span class="sxs-lookup"><span data-stu-id="a350f-105">Intune uses Azure Active Directory (AD) groups to manage devices and users.</span></span> <span data-ttu-id="a350f-106">Intune 管理者は、組織のニーズに合ったグループをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="a350f-106">As an Intune admin, you can set up groups to suit your organizational needs.</span></span> <span data-ttu-id="a350f-107">地理的な場所、部門、ハードウェアの特性ごとにグループを作成して、ユーザーまたはデバイスを整理します。</span><span class="sxs-lookup"><span data-stu-id="a350f-107">Create groups to organize users or devices by geographic location, department, or hardware characteristics.</span></span> <span data-ttu-id="a350f-108">大規模なタスクを管理するには、グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="a350f-108">Use groups to manage tasks at scale.</span></span> <span data-ttu-id="a350f-109">多数のユーザーにポリシーを設定したり、一連のデバイスにアプリを展開したりする場合などです。</span><span class="sxs-lookup"><span data-stu-id="a350f-109">For example, you can set policies for many users or  deploy apps to a set of devices.</span></span>

<span data-ttu-id="a350f-110">このトピックでは、Intune で使用するグループを追加する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a350f-110">This topic explains how to add groups for use in Intune.</span></span>

<span data-ttu-id="a350f-111">次の種類のグループを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a350f-111">You can add the following types of groups:</span></span>
- <span data-ttu-id="a350f-112">**[割り当てられたグループ]**: ユーザーまたはデバイスを静的なグループに手動で追加します。</span><span class="sxs-lookup"><span data-stu-id="a350f-112">**Assigned groups** - Manually add users or devices into a static group</span></span>
- <span data-ttu-id="a350f-113">**[Dynamic groups]\(動的グループ\)**: (Azure Active Directory Premium を使用) 単純なまたは高度な規則のいずれかを使って、動的にユーザーまたはデバイス グループのいずれかを構築します</span><span class="sxs-lookup"><span data-stu-id="a350f-113">**Dynamic groups** - (Using Azure Active Directory Premium) Let you dynamically build either user or device groups defined with either simple or advanced rules</span></span>

## <a name="add-a-new-group"></a><span data-ttu-id="a350f-114">新しいグループを追加する</span><span class="sxs-lookup"><span data-stu-id="a350f-114">Add a new group</span></span>

<span data-ttu-id="a350f-115">新しいグループを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a350f-115">Use the following steps to create a new group.</span></span>
1. <span data-ttu-id="a350f-116">Azure Portal で **[グループ]** に進み、**[All groups]/(すべてのグループ)/** ブレードで **[新しいグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a350f-116">In the Azure portal, go **Groups** and then choose **New group** in the **All groups** blade.</span></span>
  <span data-ttu-id="a350f-117">![[新しいグループ] が選択された Azure Portal のスクリーンショット](./media/groups-add-new.png)</span><span class="sxs-lookup"><span data-stu-id="a350f-117">![Screenshot of the Azure portal with New Group selected](./media/groups-add-new.png)</span></span>
2. <span data-ttu-id="a350f-118">新しいグループの **[名前]** と **[説明]** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a350f-118">Specify the **Name** and **Description** of the new group.</span></span> <span data-ttu-id="a350f-119">これらのプロパティは、管理ポータルのみに表示され、ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="a350f-119">These properties only appear in the management portal and are not displayed to users.</span></span>

3. <span data-ttu-id="a350f-120">**[メンバーシップの種類]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a350f-120">Choose **Membership type**:</span></span>
  - <span data-ttu-id="a350f-121">手動で割り当てられたメンバーからグループを作成するには、**[割り当て済み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a350f-121">**Assigned** to create group with manually assigned members.</span></span> <span data-ttu-id="a350f-122">詳細については、「[Azure Active Directory でグループを作成し、メンバーを追加する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a350f-122">Learn more about [Azure AD assigned groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span></span>
  - <span data-ttu-id="a350f-123">**[Dynamic query]/(動的クエリ)/** で定義したユーザー グループを作成するには、**[動的なユーザー]** を使用します。</span><span class="sxs-lookup"><span data-stu-id="a350f-123">**Dynamic User** to create a user group defined with a **Dynamic query**.</span></span>
  - <span data-ttu-id="a350f-124">**[Dynamic query]/(動的クエリ)/** で定義したデバイス グループを作成するには、**[Dynamic Device]/(動的なデバイス)/** を使用します。</span><span class="sxs-lookup"><span data-stu-id="a350f-124">**Dynamic Device** to create a device group defined with a **Dynamic query**.</span></span>

  ![[名前]、[説明]、[メンバーシップの種類]、[Office の機能を有効にしますか?] および [メンバー] がある Intune グループ プロパティのスクリーンショット](./media/groups-add-properties.png)

  <span data-ttu-id="a350f-126">Azure AD では、メンバーシップを定義するルールを使用して動的なグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a350f-126">Azure AD lets you create dynamic groups based on rules that define membership.</span></span> <span data-ttu-id="a350f-127">属性を使用した動的グループを作成する方法については、[こちら](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a350f-127">Learn to [create attribute-based dynamic groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

4. <span data-ttu-id="a350f-128">**[Office の機能を有効にしますか?]** を選択すると、ユーザー グループのメンバーに共有 Office 365 アプリへのアクセスを付与できます。</span><span class="sxs-lookup"><span data-stu-id="a350f-128">You can select **Enable Office features** to give user group members access to shared Office 365 apps.</span></span> <span data-ttu-id="a350f-129">詳細については、「[Office 365 グループの概要](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a350f-129">Learn more about [Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>
5. <span data-ttu-id="a350f-130">**[作成]** を選択し、新しいグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="a350f-130">Choose **Create** to add the new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="a350f-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="a350f-131">See also</span></span>
- [<span data-ttu-id="a350f-132">Azure Active Directory のグループによるリソースへのアクセス管理</span><span class="sxs-lookup"><span data-stu-id="a350f-132">Manage access to resources with Azure Active Directory groups</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [<span data-ttu-id="a350f-133">Azure Portal での Intune クラシック グループ</span><span class="sxs-lookup"><span data-stu-id="a350f-133">Intune classic groups in the Azure portal</span></span>](groups-get-started.md)
