---
title: "Intune でデバイス プロファイルを割り当てる方法"
titlesuffix: Azure portal
description: "このトピックでは、作成した Intune デバイス プロファイルをデバイスに割り当てる方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6ab9f8709c13b5efe37b2a4787f3c4803be08b68
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a><span data-ttu-id="b038c-103">Microsoft Intune のデバイス プロファイルを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="b038c-103">How to assign Microsoft Intune device profiles</span></span>

## <a name="assign-a-device-profile"></a><span data-ttu-id="b038c-104">デバイス プロファイルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b038c-104">Assign a device profile</span></span>

1. <span data-ttu-id="b038c-105">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b038c-105">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b038c-106">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b038c-106">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="b038c-107">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b038c-107">On the **Intune** blade, choose **Device configuration**.</span></span>
1. <span data-ttu-id="b038c-108">**[デバイス構成]** ブレードで、**[管理]** > **[プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b038c-108">On the **Device configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="b038c-109">プロファイルの一覧ブレードで、管理するプロファイルを選択し、**[<*プロファイル名*> レポート]** ブレードで、**[管理]** > **[割り当て]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b038c-109">In the list of profiles blade, choose the profile you want to manage, and then, on the <*profile name*> **Reports** blade, choose **Manage** > **Assignments**.</span></span>
3. <span data-ttu-id="b038c-110">次のブレードで、**[含める]** (グループを含める) または **[除外]** (グループを含めなし) を選び、**[グループの選択]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="b038c-110">On the next blade, choose either **Include** (to include groups) or **Exclude** (to exclude groups), then choose **Select groups**.</span></span>
<span data-ttu-id="b038c-111">![プロファイル割り当てに含めるグループまたは除外するグループの選択。](./media/group-include-exclude.png)</span><span class="sxs-lookup"><span data-stu-id="b038c-111">![Include and exclude groups from a profile assignment.](./media/group-include-exclude.png)</span></span>
4. <span data-ttu-id="b038c-112">**[グループの選択]** ブレードで、割り当てに含める Azure AD グループまたは割り当てから除外する Azure AD グループを選びます。</span><span class="sxs-lookup"><span data-stu-id="b038c-112">On the **Select groups** blade, choose the Azure AD groups, which you want to include in, or exclude from the assignment.</span></span> <span data-ttu-id="b038c-113">**Ctrl** キーを押したままにすると、複数のグループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b038c-113">You can hold down the **CTRL** key to select multiple groups.</span></span>
4. <span data-ttu-id="b038c-114">終了したら、**[グループの選択]** ブレードで、**[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b038c-114">When you are done, on the **Select groups** blade, choose **Select**.</span></span>



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a><span data-ttu-id="b038c-115">デバイス プロファイルの割り当てからグループを除外する方法</span><span class="sxs-lookup"><span data-stu-id="b038c-115">How to exclude groups from a device profile assignment</span></span>

<span data-ttu-id="b038c-116">Intune のデバイス構成プロファイルでは、ポリシーの割り当てからグループを除外できます。</span><span class="sxs-lookup"><span data-stu-id="b038c-116">Intune device configuration profiles let you exclude groups from policy assignment.</span></span> <span data-ttu-id="b038c-117">たとえば、**すべての会社ユーザー** グループにデバイス プロファイルを割り当て、ただし**上級管理スタッフ** グループのメンバーは除外する、といったことができます。</span><span class="sxs-lookup"><span data-stu-id="b038c-117">For example, you could assign a device profile to the **All corporate users** group, but exclude any members of the **Senior Management Staff** group.</span></span>

<span data-ttu-id="b038c-118">割り当てからグループを除外する場合は、ユーザー グループのみまたはデバイス グループのみを除外し、両方のグループを組み合わせないでください。</span><span class="sxs-lookup"><span data-stu-id="b038c-118">When you exclude groups from an assignment, exclude only user, or only device groups, not a mixture of groups.</span></span> <span data-ttu-id="b038c-119">Intune は、グループを除外する場合ユーザーとデバイスの関連付けを考慮しません。</span><span class="sxs-lookup"><span data-stu-id="b038c-119">Intune does not take into account any user to device association when excluding groups.</span></span> <span data-ttu-id="b038c-120">ユーザー グループを含めてデバイス グループを除外すると、必要な結果にならない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b038c-120">Including user groups while excluding device groups is unlikely to produce the results you need.</span></span> <span data-ttu-id="b038c-121">両方のグループが混在する場合、またはその他の競合がある場合、包含が除外より優先されます。</span><span class="sxs-lookup"><span data-stu-id="b038c-121">In case where mixed groups are used, or there are other conflicts, inclusion takes precedence over exclusion.</span></span>

<span data-ttu-id="b038c-122">たとえば、キオスク デバイスを除く組織内のすべてのデバイスにデバイス プロファイルを割り当てるものとします。</span><span class="sxs-lookup"><span data-stu-id="b038c-122">For example, you want to assign a device profile to all devices in your organization, except kiosk devices.</span></span> <span data-ttu-id="b038c-123">**すべてのユーザー** グループを含めて、**すべてのデバイス** グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="b038c-123">You include the **All Users** group, but exclude the **All Devices** group.</span></span>

<span data-ttu-id="b038c-124">この場合、すべてのユーザーとそのデバイスにポリシーが割り当てられ、ユーザーのデバイスが**すべてのデバイス** グループに含まれる場合であっても除外されません。</span><span class="sxs-lookup"><span data-stu-id="b038c-124">In this case, all your users and their devices get the policy, even if the user’s device is part of the **All Devices** group.</span></span> 

<span data-ttu-id="b038c-125">除外では、グループの直接のメンバーのみが評価され、ユーザーに関連付けられているデバイスは含まれません。</span><span class="sxs-lookup"><span data-stu-id="b038c-125">Exclusion only evaluates the direct members of the groups, and does not include devices that are associated with a user.</span></span> <span data-ttu-id="b038c-126">ただし、ユーザーのいないデバイスは、**すべてのユーザー** グループへの関連付けがないため、ポリシーを割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="b038c-126">However, devices that don't have a user do not get the policy because they have no association to the **All Users** group.</span></span> 

<span data-ttu-id="b038c-127">**すべてのデバイス**  グループを含めて、**すべてのユーザー** グループを除外すると、すべてのデバイスにポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b038c-127">If you include **All Devices**, but exclude **All Users**, all the devices receive the policy.</span></span> <span data-ttu-id="b038c-128">この場合の目的は、ユーザーが関連付けられているデバイスをこのポリシーから除外することです。</span><span class="sxs-lookup"><span data-stu-id="b038c-128">The intent in this case is to exclude devices that have an associated user from this policy.</span></span> <span data-ttu-id="b038c-129">ただし、除外機能では直接のグループ メンバーのみが比較されるため、意図した結果にはなりません。</span><span class="sxs-lookup"><span data-stu-id="b038c-129">However, it does not because the exclusion feature only compares direct group members.</span></span> 

>[!Tip]
><span data-ttu-id="b038c-130">現在、コンプライアンス ポリシーまたはアプリの割り当てには除外を使用できません。</span><span class="sxs-lookup"><span data-stu-id="b038c-130">Exclusions are not currently available for compliance policies or app assignment.</span></span> <span data-ttu-id="b038c-131">割り当てからメンバーを除外するには、使用可能と適用不可能の割り当てインテントを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="b038c-131">To exclude members from an assignment, you can use the Available, and Not applicable assignment intents.</span></span> <span data-ttu-id="b038c-132">たとえば、アプリを**使用可能**インテントの**すべての会社ユーザー**と、**適用不可能**インテントの**上級管理スタッフ**に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b038c-132">For example, you assign an app to **All corporate users** with the **Available** intent, and to **Senior Management Staff** with the **Not applicable** intent.</span></span> <span data-ttu-id="b038c-133">アプリは、**上級管理スタッフ** グループのユーザーを "*除く*" すべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b038c-133">the app is assigned to all users *except* users in the **Senior Management Staff** group.</span></span> <span data-ttu-id="b038c-134">アプリを**必須**インテントの**すべての会社ユーザー**に割り当てた場合は、**上級管理スタッフ** グループのユーザーは除外されません。</span><span class="sxs-lookup"><span data-stu-id="b038c-134">If you assign the app to **All corporate users** with the **Required** intent, the users in the **Senior Management Staff** group are not excluded.</span></span>
 
    
## <a name="next-steps"></a><span data-ttu-id="b038c-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="b038c-135">Next steps</span></span>
<span data-ttu-id="b038c-136">デバイス プロファイルの割り当てを監視するのに役立つ情報については、[デバイス プロファイルを監視する方法](device-profile-monitor.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b038c-136">See [How to monitor device profiles](device-profile-monitor.md) for information to help you monitor device profile assignments.</span></span>
