---
title: "ユーザーとデバイスを編成するグループを作成する"
description: "Intune サブスクリプションのユーザーとグループを作成します"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 24ab124a7c8724fb41684b5d1ae9564c6f83dc60
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="create-groups-to-organize-users-and-devices"></a><span data-ttu-id="5ccaf-103">ユーザーとデバイスを編成するグループを作成する</span><span class="sxs-lookup"><span data-stu-id="5ccaf-103">Create groups to organize users and devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="5ccaf-104">このトピックでは、管理者が Intune でユーザーのグループを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-104">This topic tells administrators how they can create groups of users in Intune.</span></span>

<span data-ttu-id="5ccaf-105">Intune の [グループ] を使用すると、デバイスとユーザーを柔軟に管理できます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-105">Groups in Intune give you great flexibility for managing your devices and users.</span></span> <span data-ttu-id="5ccaf-106">グループは、組織ごとのニーズ (地理的位置、部門、ハードウェアの特性など) に合わせて設定できます。一連のユーザーに対するポリシーの展開から、一連のデバイスに対するアプリケーションの展開まで、まざまな管理タスクをそれらのグループを使って実行することができます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-106">You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a wide variety of administrative tasks, from deploying policies for a set of users to deploying applications to a set of devices.</span></span>

## <a name="group-management-moving-to-azure-ad"></a><span data-ttu-id="5ccaf-107">Azure AD へのグループ管理の移行</span><span class="sxs-lookup"><span data-stu-id="5ccaf-107">Group management moving to Azure AD</span></span>

<span data-ttu-id="5ccaf-108">**2016 年 11 月以降**、Azure Active Directory (AD) ポータルでは新しいアカウントでユーザーとデバイス グループが管理されます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-108">**Starting in November 2016**, new accounts will manage user and device groups in the Azure Active Directory (AD) portal.</span></span> <span data-ttu-id="5ccaf-109">2016 年 12 月には、Intune 製品チームは既存顧客の新しい Azure AD ベースのグループ管理操作環境への移行を開始します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-109">In December 2016, the Intune product team will begin to migrate existing customers to the new Azure AD-based group management experience.</span></span> <span data-ttu-id="5ccaf-110">すべてのユーザーおよびデバイス グループは、Azure AD セキュリティ グループに移行されます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-110">All user and device groups will be migrated to Azure AD security groups.</span></span> <span data-ttu-id="5ccaf-111">お客様の日常業務への影響を最小限に抑えることができ、お客様のユーザーに影響がないものと予想されるまで、移行は開始されません。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-111">We won’t start migrations until we can minimize any effect on your day-to-day work, and when we expect there will be no effect on your users.</span></span> <span data-ttu-id="5ccaf-112">また、アカウント移行前にはお客様にご連絡します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-112">We also will give you notice before we migrate your account.</span></span>


>[!IMPORTANT]
>
><span data-ttu-id="5ccaf-113">Intune ポータルでグループ ワークスペースを開いたときに、Azure Active Directory ポータルへのリンクと共に、"**Intune ユーザー グループは、Azure Active Directory のグループとして管理されるようになりました**" というメッセージが表示された場合は、Intune でのグループ管理に*新しい* Azure AD セキュリティ グループのアプローチが既に使用されています。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-113">If you open the Groups workspace in the Intune portal and see **Intune user groups are now managed as groups in Azure Active Directory** with a link to the Azure Active Directory portal, then you are already using the *new* Azure AD security groups approach to group management in Intune.</span></span> <span data-ttu-id="5ccaf-114">グループの作成方法の詳細については、「[Azure Active Directory でのグループの管理](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-114">To learn how to create groups, see [Managing groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span></span>
>
><span data-ttu-id="5ccaf-115">Azure AD ポータルへのリンクが表示されない場合は、グループ管理にはまだ Intune ポータルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-115">If you do not see the link to the Azure AD portal, you are still using the Intune portal for groups management.</span></span>

## <a name="group-management-in-the-intune-portal"></a><span data-ttu-id="5ccaf-116">Intune ポータルでのグループ管理</span><span class="sxs-lookup"><span data-stu-id="5ccaf-116">Group management in the Intune portal</span></span>

<span data-ttu-id="5ccaf-117">デバイスとユーザー グループは両方とも Intune 管理コンソールの [グループ] ワークスペースで作成します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-117">Device and user groups are both created in the GROUPS workspace of the Intune administration console.</span></span>

![管理コンソールの [グループ] ワークスペース](./media/groups.png)


> [!TIP]
> <span data-ttu-id="5ccaf-119">グループの使用方法の詳細については、「[Microsoft Intune でユーザーとデバイスの管理にグループを使用する](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-119">To learn more about using groups, see [Use groups to manage users and devices with Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span></span>


## <a name="create-a-device-group"></a><span data-ttu-id="5ccaf-120">デバイス グループを作成する</span><span class="sxs-lookup"><span data-stu-id="5ccaf-120">Create a device group</span></span>
<span data-ttu-id="5ccaf-121">デバイス グループは、アプリや更新プログラムの展開のほか、各種機能の構成に使用します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-121">Use device groups to deploy apps and updates, and configure other features.</span></span> <span data-ttu-id="5ccaf-122">たとえば、"My Devices" というグループを設定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-122">For example, set up a "My Devices" group using the following steps:</span></span>

1.  <span data-ttu-id="5ccaf-123">[Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** > **[概要]** > **[グループの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-123">In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** > **Overview** > **Create Group**.</span></span>

2.  <span data-ttu-id="5ccaf-124">**[グループ名]** に「My Devices」と入力し、親グループ一覧から、**[すべてのデバイス]** を選択して、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-124">For the **Group name**, type “My Devices” and, from the parent group list, select **All Devices**, and then choose **Next**.</span></span>

3.  <span data-ttu-id="5ccaf-125">**[メンバーシップの基準の定義]** ページで、 **[すべてのデバイス]** を選択して、グループにモバイル デバイスとコンピューターの両方が含まれることを示します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-125">On the **Define Membership Criteria** page, select **All devices** to indicate that the group includes both mobile devices and computers.</span></span>

4.  <span data-ttu-id="5ccaf-126">**[ダイレクト メンバーシップの定義]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-126">On the **Define Direct Membership** page, choose **Next**.</span></span> <span data-ttu-id="5ccaf-127">以前作成したグループに一部のデバイスが含まれていなかった場合、ここでデバイスを指定して、新しいグループに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-127">If you previously created a group that did not include all devices, and you wanted to add specific devices to your new group, you can do that here.</span></span>

5.  <span data-ttu-id="5ccaf-128">**[概要]** ページで、実行する操作を確認し、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-128">On the **Summary** page, review the actions that will be taken, and then choose **Finish**.</span></span>

<span data-ttu-id="5ccaf-129">新しく作成したグループは、**[グループ]** 一覧の **[グループ]** ワークスペースにある **[すべてのデバイス]** の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-129">You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Devices**.</span></span> <span data-ttu-id="5ccaf-130">ここから、グループを編集または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-130">From here, you can also edit or delete the group.</span></span>

## <a name="create-a-user-group"></a><span data-ttu-id="5ccaf-131">ユーザー グループを作成する</span><span class="sxs-lookup"><span data-stu-id="5ccaf-131">Create a user group</span></span>
<span data-ttu-id="5ccaf-132">ソフトウェアやデバイスのポリシーは、ユーザー グループを使用して展開します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-132">Use user groups to deploy software and device policies.</span></span> <span data-ttu-id="5ccaf-133">たとえば、"Intune Users" というグループを設定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-133">For example, set up an "Intune Users" group using the following steps:</span></span>

1.  <span data-ttu-id="5ccaf-134">[Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** > **[概要]** > **[グループの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-134">In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** > **Overview** > **Create Group**.</span></span>

2.  <span data-ttu-id="5ccaf-135">**[グループ名]** に「Intune Users」と入力し、親グループ一覧から、**[すべてのユーザー]** を選択して、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-135">For the **Group name**, type “Intune Users” and, from the parent group list, select **All Users**, and then choose **Next**.</span></span>

3.  <span data-ttu-id="5ccaf-136">**[メンバーシップの基準の定義]** ページで、 **[グループのメンバーシップ]** を **[親グループのすべてのユーザー]**に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-136">On the **Define Membership Criteria** page, set **Start group membership with** to **All users in the Parent group**.</span></span>

4.  <span data-ttu-id="5ccaf-137">**[メンバーを除外するセキュリティ グループ]** の横の **[参照]** を選択し、**[Company Administrator]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-137">Beside **Exclude members from these security groups**, choose **Browse** and then select **Company Administrator**.</span></span> <span data-ttu-id="5ccaf-138">この除外設定により、Company Administrator アカウント (またはテナント管理者) に影響することなく、Intune Users グループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-138">This exclusion lets you manage the Intune Users group without affecting the Company Administrator account (also known as the tenant administrator).</span></span>

5.  <span data-ttu-id="5ccaf-139">**[ダイレクト メンバーシップの定義]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-139">On the **Define Direct Membership** page, choose **Next**.</span></span> <span data-ttu-id="5ccaf-140">ここでは何も操作する必要はありません。Company Administrator を除いて、Intune Users グループにすべてのユーザーを含めるからです。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-140">You don’t need to do anything here because you want the Intune Users group to include all users, except for the Company Administrator.</span></span>

6.  <span data-ttu-id="5ccaf-141">**[概要]** ページで、実行する操作を確認し、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-141">On the **Summary** page, review the actions that will be taken, and then choose **Finish**.</span></span>

<span data-ttu-id="5ccaf-142">新しく作成したグループは、**[グループ]** 一覧の **[グループ]** ワークスペースにある **[すべてのユーザー]** の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-142">You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Users**.</span></span> <span data-ttu-id="5ccaf-143">ここから、グループを編集または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ccaf-143">From here, you can also edit or delete the group.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="5ccaf-144">/intune/licenses-assign [&larr; **Intune のライセンスを管理する**](/intune/licenses-assign) [**ポリシーとアプリを作成する** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)</span><span class="sxs-lookup"><span data-stu-id="5ccaf-144">/intune/licenses-assign [&larr; **Manage Intune licenses**](/intune/licenses-assign)       [**Create policies and apps** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)</span></span>  
