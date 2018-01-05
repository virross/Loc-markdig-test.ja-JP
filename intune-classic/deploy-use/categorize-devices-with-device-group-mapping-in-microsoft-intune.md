---
title: "デバイス グループ マッピングを使用してデバイスを分類する"
description: "Microsoft Intune のデバイス グループ マッピングを使用して、ユーザー定義のカテゴリにデバイスをグループ化することで、それらのデバイスの管理が容易になります。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 961472fd91442954ac349d59d334f5ddfac13855
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="categorize-devices-with-device-group-mapping-in-microsoft-intune"></a><span data-ttu-id="456a3-103">Microsoft Intune でデバイス グループのマッピングを使用してデバイスを分類する</span><span class="sxs-lookup"><span data-stu-id="456a3-103">Categorize devices with device group mapping in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="456a3-104">Microsoft Intune の**デバイス グループ マッピング**を使用して、ユーザー定義のカテゴリに基づいてデバイスを自動的にグループに追加することで、デバイスの管理が容易になります。</span><span class="sxs-lookup"><span data-stu-id="456a3-104">Use Microsoft Intune **device group mapping** to automatically add devices to groups based on categories that you define, in order to make it easier for you to manage those devices.</span></span> 

<span data-ttu-id="456a3-105">デバイス グループ マッピングでは、次のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="456a3-105">Device group mapping uses the following workflow:</span></span>
1. <span data-ttu-id="456a3-106">デバイス登録時の選択肢として表示するカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="456a3-106">Create categories that users will choose from when they enroll their device</span></span>
2. <span data-ttu-id="456a3-107">使用するカテゴリごとに、グループを作成するか、既存のグループを使用します。</span><span class="sxs-lookup"><span data-stu-id="456a3-107">You create groups, or use existing groups for each category you want to use.</span></span> <span data-ttu-id="456a3-108">使用している Intune のバージョンに応じて、Intune グループまたは Azure Active Directory セキュリティ グループの場合があります。</span><span class="sxs-lookup"><span data-stu-id="456a3-108">Depending on the version of Intune you are using, these will either be Intune groups, or Azure Active Directory security groups.</span></span>
2. <span data-ttu-id="456a3-109">作成したデバイス グループに選択したカテゴリを対応付けるルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="456a3-109">You configure rules that map the category you choose to the device group you created.</span></span>
3. <span data-ttu-id="456a3-110">iOS デバイスと Android デバイスのエンド ユーザーがデバイスを登録する場合、構成されているカテゴリの一覧からカテゴリを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="456a3-110">When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured.</span></span> <span data-ttu-id="456a3-111">Windows デバイスにカテゴリを割り当てるには、エンド ユーザーはポータル サイトを使用する必要があります (詳細については、このトピックの「**デバイス グループの構成後**」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="456a3-111">To assign a category to a Windows device, end users must use the Company Portal website (see **After you configure device groups** in this topic for more details).</span></span>
4. <span data-ttu-id="456a3-112">次に、ポリシーとアプリをグループに展開します。</span><span class="sxs-lookup"><span data-stu-id="456a3-112">You can then deploy policies and apps to these groups.</span></span>

<span data-ttu-id="456a3-113">次のように、任意のデバイス カテゴリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="456a3-113">You can create any device categories you want, for example:</span></span>
* <span data-ttu-id="456a3-114">販売時点管理デバイス</span><span class="sxs-lookup"><span data-stu-id="456a3-114">Point of sale device</span></span>
* <span data-ttu-id="456a3-115">デモンストレーション デバイス</span><span class="sxs-lookup"><span data-stu-id="456a3-115">Demonstration device</span></span>
* <span data-ttu-id="456a3-116">営業</span><span class="sxs-lookup"><span data-stu-id="456a3-116">Sales</span></span>
* <span data-ttu-id="456a3-117">アカウンティング</span><span class="sxs-lookup"><span data-stu-id="456a3-117">Accounting</span></span>
* <span data-ttu-id="456a3-118">Manager</span><span class="sxs-lookup"><span data-stu-id="456a3-118">Manager</span></span>

## <a name="important-information-about-a-change-in-group-management-for-intune"></a><span data-ttu-id="456a3-119">Intune のグループ管理の変更に関する重要な情報</span><span class="sxs-lookup"><span data-stu-id="456a3-119">Important information about a change in group management for Intune</span></span>

<span data-ttu-id="456a3-120">お客様のフィードバックに基づいて、Enterprise Mobility + Security 全体のグループ化およびターゲット設定を統合する作業を進めています。</span><span class="sxs-lookup"><span data-stu-id="456a3-120">Based on your feedback, we are in the process of unifying the grouping and targeting experience across Enterprise Mobility + Security.</span></span> <span data-ttu-id="456a3-121">そのため、間もなく Intune のグループを Azure Active Directory ベースのセキュリティ グループに変換します。</span><span class="sxs-lookup"><span data-stu-id="456a3-121">For this reason, we will soon be converting Intune groups to Azure Active Directory-based security groups.</span></span> <span data-ttu-id="456a3-122">この変更後は、Intune を使用してグループを作成しません。</span><span class="sxs-lookup"><span data-stu-id="456a3-122">After this change, you will no longer create groups using Intune.</span></span> <span data-ttu-id="456a3-123">代わりに、Azure ポータルでグループを作成するようになります。</span><span class="sxs-lookup"><span data-stu-id="456a3-123">Instead, you'll create them in the Azure portal.</span></span> <span data-ttu-id="456a3-124">この変更は段階的に行う予定です。変更内容の詳細とタイムラインについては、[このトピック](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="456a3-124">This change will happen on a gradual basis and you can read full details about this change, and its timeline in [this topic](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span></span>

### <a name="which-procedure-in-this-topic-should-you-use-to-configure-device-group-mapping"></a><span data-ttu-id="456a3-125">デバイス グループ マッピングを構成する際にこのトピックで使用する手順</span><span class="sxs-lookup"><span data-stu-id="456a3-125">Which procedure in this topic should you use to configure device group mapping?</span></span>

<span data-ttu-id="456a3-126">Azure Active Directory ベースのセキュリティ グループは段階的に実装されるため、使用する手順を特定するには、[Intune 管理コンソール](https://manage.microsoft.com)の **[グループ]** ワークスペースを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="456a3-126">Due to the phased implementation of Azure Active Directory-based security groups, you must open the **Groups** workspace in the [Intune administration console](https://manage.microsoft.com) to identify which procedure to use:</span></span>

-  <span data-ttu-id="456a3-127">Azure ポータルへのリンクが表示される場合、Intune グループが使用されなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="456a3-127">If you see a link to the Azure portal, then you are no longer using Intune groups.</span></span> <span data-ttu-id="456a3-128">後述する「[デバイス グループ マッピングの構成方法 (Azure Active Directory グループ)](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="456a3-128">Follow the [How to configure device group mapping for Azure Active Directory groups](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups) procedure below.</span></span>
-  <span data-ttu-id="456a3-129">Azure ポータルへのリンクが表示されない場合、まだ Intune グループが使用されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="456a3-129">If you do not see a link to the Azure portal, then you are still using Intune groups.</span></span> <span data-ttu-id="456a3-130">後述する「[デバイス グループ マッピングの構成方法 (Intune グループ)](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="456a3-130">Follow the [How to configure device group mapping for Intune groups](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups) procedure below.</span></span>

## <a name="how-to-configure-device-group-mapping-for-intune-groups"></a><span data-ttu-id="456a3-131">デバイス グループ マッピングの構成方法 (Intune グループ)</span><span class="sxs-lookup"><span data-stu-id="456a3-131">How to configure device group mapping for Intune groups</span></span>
1. <span data-ttu-id="456a3-132">使用するデバイス カテゴリごとに、Intune のデバイス グループを作成するか、既存のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="456a3-132">For each device category you want to use, create an Intune device group, or identify an existing group.</span></span> <span data-ttu-id="456a3-133">グループの作成方法については、「[Microsoft Intune でユーザーとデバイスの管理にグループを使用する](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="456a3-133">For information about how to create groups, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span></span>
2. <span data-ttu-id="456a3-134">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="456a3-134">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.</span></span>
3. <span data-ttu-id="456a3-135">**[管理]** ワークスペースで、**[モバイル デバイス管理]** を展開してから、**[デバイス グループ マッピング]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="456a3-135">In the **Administration** workspace, expand **Mobile Device Management**, and then choose **Device Group Mapping**.</span></span>
4. <span data-ttu-id="456a3-136">**[デバイス グループ マッピング]** ページで、デバイス グループ マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="456a3-136">On the **Device Group Mapping** page, enable device group mapping.</span></span>
5. <span data-ttu-id="456a3-137">**[追加]** を選択し、新しいマッピング ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="456a3-137">Choose **Add** to create a new mapping rule.</span></span>
6. <span data-ttu-id="456a3-138">**[デバイス グループ マッピング ルールの追加]** ダイアログ ボックスで、作成するカテゴリの名前を入力し、このカテゴリをマップするデバイスのコレクションをドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="456a3-138">In the **Add device group mapping rule** dialog box, enter the name of the category you want to create and then, from the drop-down list, choose the device collection you want to map this category to.</span></span> <span data-ttu-id="456a3-139">選択が完了したら、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="456a3-139">Choose **Add** when you are done.</span></span>
7. <span data-ttu-id="456a3-140">カテゴリとグループの追加が完了したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="456a3-140">When you have finished adding categories and groups, choose **Save**.</span></span>



## <a name="how-to-configure-device-group-mapping-for-azure-active-directory-groups"></a><span data-ttu-id="456a3-141">デバイス グループ マッピングの構成方法 (Azure Active Directory グループ)</span><span class="sxs-lookup"><span data-stu-id="456a3-141">How to configure device group mapping for Azure Active Directory groups</span></span>

### <a name="step-1---create-device-categories-in-the-intune-administration-console"></a><span data-ttu-id="456a3-142">手順 1 - Intune 管理コンソールでデバイス カテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="456a3-142">Step 1 - Create device categories in the Intune administration console</span></span>
1. <span data-ttu-id="456a3-143">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="456a3-143">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.</span></span>
2. <span data-ttu-id="456a3-144">**[管理]** ワークスペースで、**[モバイル デバイス管理]** を展開してから、**[デバイス カテゴリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="456a3-144">In the **Administration** workspace, expand **Mobile Device Management**, and then choose **Device Categories**.</span></span>
3. <span data-ttu-id="456a3-145">**[デバイス カテゴリ]** ページには、デバイス カテゴリを構成できる一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="456a3-145">On the **Device Categories** page, you'll see a list where you can configure device categories:</span></span> 
4. <span data-ttu-id="456a3-146">名前を入力し、**[追加]** をクリックすると、新しいデバイス カテゴリとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="456a3-146">You can enter a name, then click **Add**, to add it as a new device category.</span></span>
5. <span data-ttu-id="456a3-147">カテゴリを選択し、**[削除]** をクリックして削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="456a3-147">Additionally, you can select a category and then **Delete** it.</span></span>

<span data-ttu-id="456a3-148">デバイス カテゴリ名は、手順 2 で Azure Active Directory セキュリティ グループを作成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="456a3-148">You'll use the device category name when you create Azure Active Directory security groups in step 2.</span></span>

### <a name="step-2---create-azure-active-directory-security-groups"></a><span data-ttu-id="456a3-149">手順 2 - Azure Active Directory セキュリティ グループを作成する</span><span class="sxs-lookup"><span data-stu-id="456a3-149">Step 2 - Create Azure Active Directory security groups</span></span>

<span data-ttu-id="456a3-150">この手順では、デバイス カテゴリとデバイス カテゴリ名に基づいて、Azure ポータルで動的グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="456a3-150">In this step, you'll create dynamic groups in the Azure portal based on the device category and device category name.</span></span>

<span data-ttu-id="456a3-151">次に進む前に、Azure Active Directory ドキュメントのトピック「[属性を利用した高度なルールの作成](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="456a3-151">To continue, refer to the topic [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in the Azure Active Directory documentation.</span></span>
<span data-ttu-id="456a3-152">このトピックの情報を参考にして、**deviceCategory** 属性を使用して高度なルールのデバイス グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="456a3-152">Use the information in this topic to create a device group with an advanced rule using the **deviceCategory** attribute.</span></span>
<span data-ttu-id="456a3-153">たとえば、次のようなグループを作成します。(**device.deviceCategory -eq** "<*Intune 管理コンソールで確認したデバイス カテゴリ名*>")</span><span class="sxs-lookup"><span data-stu-id="456a3-153">For example (**device.deviceCategory -eq** "<*the device category name you got from the Intune administration console*>")</span></span>


## <a name="after-you-configure-device-groups"></a><span data-ttu-id="456a3-154">デバイス グループの構成後</span><span class="sxs-lookup"><span data-stu-id="456a3-154">After you configure device groups</span></span>

<span data-ttu-id="456a3-155">iOS デバイスと Android デバイスのエンド ユーザーがデバイスを登録する場合、構成されているカテゴリの一覧からカテゴリを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="456a3-155">When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured.</span></span> <span data-ttu-id="456a3-156">ユーザーがカテゴリを選択して登録を完了すると、選択したカテゴリに対応する Intune デバイス グループまたは Active Directory セキュリティ グループにデバイスが追加されます。</span><span class="sxs-lookup"><span data-stu-id="456a3-156">After they choose a category and finish enrollment, their device is added to the Intune device group, or Active Directory security group that corresponds with the category they chose.</span></span>

<span data-ttu-id="456a3-157">Windows デバイスにカテゴリを割り当てるには、エンド ユーザーは、デバイスを登録した後、ポータル サイト (portal.manage.microsoft.com) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="456a3-157">To assign a category to a Windows device, end users must use the Company Portal website (portal.manage.microsoft.com) after enrolling the device.</span></span> <span data-ttu-id="456a3-158">Windows デバイスで Web サイトにアクセスし、**[メニュー]**   >  **[デバイス]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="456a3-158">On a Windows device, access the website and go to **Menu** > **My Devices**.</span></span> <span data-ttu-id="456a3-159">ページに表示されている登録済みデバイスを選択し、次にカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="456a3-159">Choose an enrolled device listed on the page, then select a category.</span></span> 

<span data-ttu-id="456a3-160">カテゴリを選択すると、作成済みの対応するグループにデバイスが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="456a3-160">After choosing a category, the device is automatically added to the corresponding group you created.</span></span> <span data-ttu-id="456a3-161">カテゴリを構成する前にデバイスが既に登録されている場合は、エンド ユーザーにはデバイスに関する通知がポータル サイトに表示され、次回ユーザーが iOS または Android でポータル サイト アプリにアクセスするときに、カテゴリの選択を求められます。</span><span class="sxs-lookup"><span data-stu-id="456a3-161">If a device is already enrolled before you configure categories, the end user will see a notification about the device on the Company Portal website, and will be asked to select a category the next time they access the Company Portal app on iOS or Android.</span></span>



### <a name="see-also"></a><span data-ttu-id="456a3-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="456a3-162">See also</span></span>
[<span data-ttu-id="456a3-163">Microsoft Intune でユーザーとデバイスの管理にグループを使用する</span><span class="sxs-lookup"><span data-stu-id="456a3-163">Use groups to manage users and devices with Microsoft Intune</span></span>](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
