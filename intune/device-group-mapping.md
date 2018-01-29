---
title: "Intune でデバイス カテゴリを使用する方法"
titleSuffix: Azure portal
description: "Intune でデバイスを登録するときにユーザーが選択できるデバイス カテゴリを使用する方法について説明します。\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 85dc67911bb53e258faf6d5ccadcf03d88fa4a0d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="map-device-groups"></a><span data-ttu-id="c294c-103">デバイス グループをマップする</span><span class="sxs-lookup"><span data-stu-id="c294c-103">Map device groups</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="c294c-104">Microsoft Intune のデバイス カテゴリを使用して、ユーザー定義のカテゴリに基づいてデバイスを自動的にグループに追加することで、デバイスの管理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="c294c-104">Use Microsoft Intune device categories to automatically add devices to groups based on categories that you define, in order to make it easier for you to manage those devices.</span></span>

<span data-ttu-id="c294c-105">デバイス カテゴリでは、次のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="c294c-105">Device categories use the following workflow:</span></span>
1. <span data-ttu-id="c294c-106">デバイス登録時の選択肢として表示するカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="c294c-106">Create categories that users will choose from when they enroll their device</span></span>
3. <span data-ttu-id="c294c-107">iOS デバイスと Android デバイスのエンド ユーザーがデバイスを登録する場合、構成されているカテゴリの一覧からカテゴリを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c294c-107">When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured.</span></span> <span data-ttu-id="c294c-108">Windows デバイスにカテゴリを割り当てるには、エンド ユーザーはポータル サイトを使用する必要があります (詳細については、このトピックの「**デバイス グループの構成後**」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="c294c-108">To assign a category to a Windows device, end users must use the Company Portal website (see **After you configure device groups** in this topic for more details).</span></span>
4. <span data-ttu-id="c294c-109">次に、ポリシーとアプリをグループに展開します。</span><span class="sxs-lookup"><span data-stu-id="c294c-109">You can then deploy policies and apps to these groups.</span></span>

<span data-ttu-id="c294c-110">次のように、任意のデバイス カテゴリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c294c-110">You can create any device categories you want, for example:</span></span>
- <span data-ttu-id="c294c-111">販売時点管理デバイス</span><span class="sxs-lookup"><span data-stu-id="c294c-111">Point of sale device</span></span>
- <span data-ttu-id="c294c-112">デモンストレーション デバイス</span><span class="sxs-lookup"><span data-stu-id="c294c-112">Demonstration device</span></span>
- <span data-ttu-id="c294c-113">営業</span><span class="sxs-lookup"><span data-stu-id="c294c-113">Sales</span></span>
- <span data-ttu-id="c294c-114">アカウンティング</span><span class="sxs-lookup"><span data-stu-id="c294c-114">Accounting</span></span>
- <span data-ttu-id="c294c-115">Manager</span><span class="sxs-lookup"><span data-stu-id="c294c-115">Manager</span></span>

## <a name="how-to-configure-device-categories"></a><span data-ttu-id="c294c-116">デバイス カテゴリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c294c-116">How to configure device categories</span></span>

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a><span data-ttu-id="c294c-117">手順 1 - Azure Portal の [Intune] ブレードでデバイス カテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="c294c-117">Step 1 - Create device categories in the Intune blade of the Azure portal</span></span>
1. <span data-ttu-id="c294c-118">Azure Portal で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c294c-118">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="c294c-119">**[Intune]** ブレードで、**[デバイスの登録]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c294c-119">On the **Intune** blade, choose **Device Enrollment**.</span></span>
3. <span data-ttu-id="c294c-120">**[デバイスの登録]** ブレードで、**[デバイス カテゴリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c294c-120">On the **Device Enrollment** blade, choose **Device Categories**.</span></span>
4. <span data-ttu-id="c294c-121">**[デバイス カテゴリ]** ページで、**[作成]** を選択して、新しいカテゴリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c294c-121">On the **Device Categories** page, choose **Create** to add a new category.</span></span>
5. <span data-ttu-id="c294c-122">次のブレードで、新しいカテゴリの**名前**と省略可能な**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="c294c-122">On the next blade, enter a **Name** for the new category, and an optional **Description**.</span></span>
6. <span data-ttu-id="c294c-123">完了したら **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c294c-123">When you are done, click **Create**.</span></span> <span data-ttu-id="c294c-124">作成したカテゴリがカテゴリの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c294c-124">You’ll see the category you just created in the list of categories.</span></span>

<span data-ttu-id="c294c-125">デバイス カテゴリ名は、手順 2 で Azure Active Directory セキュリティ グループを作成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="c294c-125">You'll use the device category name when you create Azure Active Directory security groups in step 2.</span></span>

### <a name="step-2---create-azure-active-directory-security-groups"></a><span data-ttu-id="c294c-126">手順 2 - Azure Active Directory セキュリティ グループを作成する</span><span class="sxs-lookup"><span data-stu-id="c294c-126">Step 2 - Create Azure Active Directory security groups</span></span>
<span data-ttu-id="c294c-127">この手順では、デバイス カテゴリとデバイス カテゴリ名に基づいて、Azure ポータルで動的グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c294c-127">In this step, you'll create dynamic groups in the Azure portal based on the device category and device category name.</span></span>

<span data-ttu-id="c294c-128">次に進む前に、Azure Active Directory ドキュメントのトピック「[属性を利用した高度なルールの作成](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c294c-128">To continue, refer to the topic [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in the Azure Active Directory documentation.</span></span>

<span data-ttu-id="c294c-129">このセクションの情報を参考にして、**deviceCategory** 属性を使用して高度なルールのデバイス グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c294c-129">Use the information in this section to create a device group with an advanced rule using the **deviceCategory** attribute.</span></span> <span data-ttu-id="c294c-130">例: (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")</span><span class="sxs-lookup"><span data-stu-id="c294c-130">For example (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")</span></span>

<span data-ttu-id="c294c-131">デバイス グループを構成し、ユーザーがデバイスを登録すると、構成したカテゴリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c294c-131">After you configure device groups, and users enroll their device, they are presented with a list of the categories you configured.</span></span> <span data-ttu-id="c294c-132">ユーザーがカテゴリを選択して登録を完了すると、選択したカテゴリに対応する Active Directory セキュリティ グループにデバイスが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c294c-132">After they choose a category and finish enrollment, their device is added to the Active Directory security group that corresponds with the category they chose.</span></span>

### <a name="how-to-view-the-categories-of-devices-you-manage"></a><span data-ttu-id="c294c-133">管理対象デバイスのカテゴリを表示する方法</span><span class="sxs-lookup"><span data-stu-id="c294c-133">How to view the categories of devices you manage</span></span>

1.  <span data-ttu-id="c294c-134">Azure Portal で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c294c-134">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2. <span data-ttu-id="c294c-135">Azure Portal の [Intune] ブレードで、**[デバイスとグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c294c-135">In the Intune blade of the Azure portal, choose **Devices and Groups**.</span></span>

3.  <span data-ttu-id="c294c-136">**[管理]** の **[すべてのデバイス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c294c-136">Under **Manage**, click **All devices**.</span></span>

4.  <span data-ttu-id="c294c-137">デバイスの一覧の **[カテゴリ]** 列を確認します。</span><span class="sxs-lookup"><span data-stu-id="c294c-137">In the list of devices, examine the **Category** column.</span></span>

<span data-ttu-id="c294c-138">**[カテゴリ]** 列が表示されていない場合は、**[列]** をクリックし、一覧から**[カテゴリ]** を選択して、**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c294c-138">If the **Category** column isn’t displayed, click **Columns**, choose **Category** from the list, and then click **Apply**.</span></span>

### <a name="to-change-the-category-of-a-device"></a><span data-ttu-id="c294c-139">デバイスのカテゴリを変更するには</span><span class="sxs-lookup"><span data-stu-id="c294c-139">To change the category of a device</span></span>

1. <span data-ttu-id="c294c-140">Azure Portal で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c294c-140">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="c294c-141">**[Intune]** ブレードで、**[デバイスとグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c294c-141">On the **Intune** blade, choose **Devices & Groups**.</span></span>
4. <span data-ttu-id="c294c-142">**[デバイスとグループ]** ブレードで、**[管理]** > **[すべてのデバイス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c294c-142">On the **Devices and Groups** blade, choose **Manage** > **All devices**.</span></span>
5. <span data-ttu-id="c294c-143">デバイスの一覧で目的のデバイスを選択し、デバイスのプロパティ ブレードで、**[管理]** > **[プロパティ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c294c-143">In the list of devices, choose the device you want, then, on the device properties blade, choose **Manage** > **Properties**.</span></span>
6. <span data-ttu-id="c294c-144">次のブレードで、選択したデバイスの **[デバイス カテゴリ]** を、以前に構成したカテゴリ名のいずれかに変更できます。</span><span class="sxs-lookup"><span data-stu-id="c294c-144">On the next blade, you can change the **Device category** of the selected device to any of the category names you previously configured.</span></span>

## <a name="after-you-configure-device-groups"></a><span data-ttu-id="c294c-145">デバイス グループの構成後</span><span class="sxs-lookup"><span data-stu-id="c294c-145">After you configure device groups</span></span>

<span data-ttu-id="c294c-146">iOS デバイスと Android デバイスのエンド ユーザーがデバイスを登録する場合、構成されているカテゴリの一覧からカテゴリを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c294c-146">When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured.</span></span> <span data-ttu-id="c294c-147">ユーザーがカテゴリを選択して登録を完了すると、選択したカテゴリに対応する Intune デバイス グループまたは Active Directory セキュリティ グループにデバイスが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c294c-147">After they choose a category and finish enrollment, their device is added to the Intune device group, or Active Directory security group that corresponds with the category they chose.</span></span>

<span data-ttu-id="c294c-148">プラットフォームにかかわらず、エンド ユーザーはデバイスを登録した後いつでも portal.manage.microsoft.com にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c294c-148">Regardless of platform, your end users can always go to portal.manage.microsoft.com after enrolling the device.</span></span> <span data-ttu-id="c294c-149">ポータル サイト Web サイトにアクセスし、**[デバイス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c294c-149">Have the user access the Company Portal website and go to **My Devices**.</span></span> <span data-ttu-id="c294c-150">ページに表示されている登録済みデバイスを選び、次にカテゴリを選びます。</span><span class="sxs-lookup"><span data-stu-id="c294c-150">They can choose an enrolled device listed on the page, then select a category.</span></span>

<span data-ttu-id="c294c-151">カテゴリを選択すると、作成済みの対応するグループにデバイスが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c294c-151">After choosing a category, the device is automatically added to the corresponding group you created.</span></span> <span data-ttu-id="c294c-152">カテゴリを構成する前にデバイスが既に登録されている場合は、エンド ユーザーにはデバイスに関する通知がポータル サイトに表示され、次回ユーザーが iOS または Android でポータル サイト アプリにアクセスするときに、カテゴリの選択を求められます。</span><span class="sxs-lookup"><span data-stu-id="c294c-152">If a device is already enrolled before you configure categories, the end user will see a notification about the device on the Company Portal website, and will be asked to select a category the next time they access the Company Portal app on iOS or Android.</span></span>

## <a name="further-information"></a><span data-ttu-id="c294c-153">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c294c-153">Further information</span></span>
- <span data-ttu-id="c294c-154">Azure Portal でデバイス カテゴリを編集できますが、これを行った場合は、そのカテゴリを参照するすべての Azure Active Directory セキュリティ グループを手動で更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c294c-154">You can edit a device category in the Azure Portal, but if you do this, you must manually update any Azure Active Directory Security groups that reference this category.</span></span>

- <span data-ttu-id="c294c-155">カテゴリを削除すると、そのカテゴリに割り当てられていたすべてのデバイスのカテゴリ名が "**未割り当て**" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="c294c-155">If you delete a category, any devices that were assigned to it will subsequently display the category name **Unassigned**.</span></span>
