---
title: "MAM ポリシーを作成および展開する"
description: "モバイル アプリ管理ポリシーを作成して展開するには、このトピックのステップ バイ ステップの指示に従ってください。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 53196d7fd237144cbf1098ea877268759423a9ee
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="create-and-deploy-app-protection-policies-with-microsoft-intune"></a><span data-ttu-id="b3cba-103">Microsoft Intune でのアプリ保護ポリシーの作成とデプロイ</span><span class="sxs-lookup"><span data-stu-id="b3cba-103">Create and deploy app protection policies with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b3cba-104">このトピックでは、**Azure ポータル**でアプリ保護ポリシーを作成するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-104">This topic describes the process of creating an app protection policy in the **Azure portal**.</span></span> <span data-ttu-id="b3cba-105">Azure ポータルはアプリ保護ポリシーを作成するための新しい管理コンソールです。このポータルを使用して、アプリ保護ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b3cba-105">The Azure portal is the new admin console for creating app protection policies, and we recommend that you use this portal to create app protection policies.</span></span> <span data-ttu-id="b3cba-106">Azure ポータルでは、次の MAM シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b3cba-106">Azure portal supports the following MAM scenarios:</span></span>

- <span data-ttu-id="b3cba-107">Intune に登録されたデバイス</span><span class="sxs-lookup"><span data-stu-id="b3cba-107">Devices enrolled in Intune.</span></span>
- <span data-ttu-id="b3cba-108">サードパーティの MDM ソリューションで管理されるデバイス</span><span class="sxs-lookup"><span data-stu-id="b3cba-108">Devices managed by a third-party MDM solution.</span></span>
- <span data-ttu-id="b3cba-109">MDM ソリューション (BYOD) で管理されないデバイス</span><span class="sxs-lookup"><span data-stu-id="b3cba-109">Devices that are not managed by any MDM solution (BYOD).</span></span>

>[!IMPORTANT]
<span data-ttu-id="b3cba-110">デバイスの管理に **Intune 管理コンソール**を使用してしている場合は、次のことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b3cba-110">Here are a few considerations if you're using the **Intune admin console** to manage your devices:</span></span>

> * <span data-ttu-id="b3cba-111">[Intune 管理コンソール](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)を使用して Intune に登録したデバイスのアプリをサポートするアプリ保護ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-111">You can create an app protection policy that supports apps for devices enrolled in Intune using the [Intune admin console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).</span></span>
> * <span data-ttu-id="b3cba-112">Intune 管理コンソールで作成したアプリ保護ポリシーを Azure ポータルにインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b3cba-112">App protection policies created in the Intune admin console cannot be imported into the Azure portal.</span></span>  <span data-ttu-id="b3cba-113">Azure ポータルでアプリ保護ポリシーを作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3cba-113">The app protection policies must be re-created in the Azure portal.</span></span>

> * <span data-ttu-id="b3cba-114">Intune 管理コンソールでは、アプリ保護ポリシー設定の一部が表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3cba-114">You may not see all app protection policy settings in the Intune admin console.</span></span> <span data-ttu-id="b3cba-115">Azure ポータルはアプリ保護ポリシーを作成するための新しい管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="b3cba-115">The Azure portal is the new admin console for creating app protection policies.</span></span>

> * <span data-ttu-id="b3cba-116">管理対象アプリをデプロイするには、Intune 管理コンソールでアプリ保護ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3cba-116">To deploy managed apps, you must create a app protection policy in the Intune admin console.</span></span> <span data-ttu-id="b3cba-117">この場合、Intune 管理コンソールと Azure ポータルの両方でアプリ保護ポリシーを作成できます。Intune 管理コンソールはユーザーが管理対象アプリをデプロイできることを確認します。Azure ポータルはすべてのアプリ保護ポリシー設定を備えた新しい管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="b3cba-117">In this case, you may want to create app protection policies in both the Intune admin console and the Azure portal: Intune admin console to make sure you have the ability to deploy managed apps, and the Azure portal because it is the new admin console that has all the app protection policy settings.</span></span>

> * <span data-ttu-id="b3cba-118">Intune 管理コンソールと Azure ポータルの両方でアプリ保護ポリシーを作成した場合は、Azure ポータルで作成されたポリシーがアプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-118">If you create app protection policies on both Intune admin console and Azure portal, the policy that is created in the Azure portal is applied to the apps.</span></span>

<span data-ttu-id="b3cba-119">Android および iOS プラットフォームでサポートされているポリシー設定の一覧を表示するには、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-119">To see a list of policy settings supported for Android and iOS platforms, select one of the following:</span></span>

> [!div class="op_single_selector"]
- [<span data-ttu-id="b3cba-120">iOS ポリシー</span><span class="sxs-lookup"><span data-stu-id="b3cba-120">iOS policies</span></span>](ios-mam-policy-settings.md)
- [<span data-ttu-id="b3cba-121">Android ポリシー</span><span class="sxs-lookup"><span data-stu-id="b3cba-121">Android policies</span></span>](android-mam-policy-settings.md)

- <span data-ttu-id="b3cba-122">アプリ保護ポリシーのしくみと Intune のアプリ保護ポリシーでサポートされるシナリオについて詳しくは、[アプリ保護ポリシーを使用したアプリ データの保護](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b3cba-122">For a more detailed description of how app protection policies work and the scenarios supported by Intune app protection policies, see [protect app data using app protection policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).</span></span>

##  <a name="create-an-app-protection-policy"></a><span data-ttu-id="b3cba-123">アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b3cba-123">Create an app protection policy</span></span>
<span data-ttu-id="b3cba-124">アプリ保護ポリシーは、Azure ポータルで作成されます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-124">App protection policies are created at the Azure Portal.</span></span> <span data-ttu-id="b3cba-125">初めて Azure ポータルを使用する場合は、先に [Azure ポータルの Microsoft Intune アプリ保護ポリシー対応](azure-portal-for-microsoft-intune-mam-policies.md)に関する記事を参照して、Azure ポータルについて理解しておきます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-125">If this is the first time you are using the Azure portal, read [Azure portal for Microsoft Intune app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) to get more familiar with the Azure Portal.</span></span> <span data-ttu-id="b3cba-126">アプリ保護ポリシーを作成する前に、[前提条件とサポート](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)情報をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="b3cba-126">Before creating an app protection policy, review the [pre-requisites and support](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) information.</span></span>

<span data-ttu-id="b3cba-127">アプリ保護ポリシーを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b3cba-127">Follow the steps below to create app protection policies:</span></span>

1. <span data-ttu-id="b3cba-128">[Azure Portal](https://portal.azure.com) に移動し、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-128">Go to the [Azure portal](https://portal.azure.com), and enter your credentials.</span></span>

2. <span data-ttu-id="b3cba-129">**[その他のサービス]** を選択し、"Intune" と入力します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-129">Choose **More Services**, and type "Intune".</span></span>

3. <span data-ttu-id="b3cba-130">**[Intune アプリ保護]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-130">Choose **Intune App Protection**.</span></span>

4. <span data-ttu-id="b3cba-131">**[Intune モバイル アプリケーション管理] &gt; [設定]** を選択して、**[すべての設定]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-131">Choose **Intune mobile application management &gt; Settings** to open the **All Settings** blade.</span></span>

    ![[Intune モバイル アプリケーション管理] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_Mainblade-2.png)

2.  <span data-ttu-id="b3cba-133">**[すべての設定]** ブレードで、**[アプリ ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3cba-133">In the **All Settings** blade, choose **App policy**.</span></span> <span data-ttu-id="b3cba-134">これにより、**[アプリ ポリシー]** ブレードが開き、ここで新しいポリシーを作成や、既存のポリシーの編集ができます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-134">This opens the **App policy** blade, where you'll create new policies and edit existing policies.</span></span> <span data-ttu-id="b3cba-135">**[ポリシーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-135">Choose **Add a policy**.</span></span>

    ![<span data-ttu-id="b3cba-136">[ポリシーの追加] メニュー オプションが強調表示されている [ポリシーの追加] ブレードのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="b3cba-136">Screenshot of the App policy blade with the Add a policy menu option highlighted</span></span> ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  <span data-ttu-id="b3cba-137">ポリシーの名前を入力して簡単な説明を追加し、iOS または Android 用のポリシーを作成するプラットフォームの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-137">Type a name for the policy, add a brief description, and select the platform type to create a policy for iOS or Android.</span></span> <span data-ttu-id="b3cba-138">プラットフォームごとに複数のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-138">You can create more than one policy for each platform.</span></span>

    ![[ポリシーの追加] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  <span data-ttu-id="b3cba-140">**[アプリ]** を選択して **[アプリ] ブレード** を開くと、使用可能なアプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-140">Choose **Apps** to open the **Apps blade**, where a list of available apps is displayed.</span></span> <span data-ttu-id="b3cba-141">一覧から、作成するポリシーに関連付けるアプリを 1 つまたは複数選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-141">Select one or more apps from the list that you want to associate with the policy that you are creating.</span></span> <span data-ttu-id="b3cba-142">アプリを選択したら、**[アプリ]** ブレードの下部にある **[選択]** を選択して、選択内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-142">Once you have selected the apps, choose **Select** at the bottom of the **Apps** blade to save your selection.</span></span>

    > [!IMPORTANT]
    > ポリシーを作成するには、少なくとも 1 つのアプリを選択する必要があります。

5.  <span data-ttu-id="b3cba-144">**[ポリシーの追加] ブレード**で、**[必要な設定の構成]** を選択し、[ポリシー設定] ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-144">On the **Add a policy blade**, choose **Configure required settings** to open the policy settings blade.</span></span>

    <span data-ttu-id="b3cba-145">ポリシー設定には、**[データ再配置]** と **[アクセス]** の 2 つのカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="b3cba-145">There are two categories of policy settings, **Data relocation** and **Access**.</span></span>  <span data-ttu-id="b3cba-146">データ再配置ポリシーは、アプリとの間のデータ移動に適用可能ですが、作業コンテキストでエンド ユーザーがアプリにアクセスする方法は、アクセス ポリシーによって決まります。</span><span class="sxs-lookup"><span data-stu-id="b3cba-146">Data relocation policies are applicable to data movement in and out of the apps, while the access polices determine how the end user accesses the apps in a work context.</span></span>
    <span data-ttu-id="b3cba-147">ユーザーが開始できるように、ポリシー設定には既定値が入力されています。</span><span class="sxs-lookup"><span data-stu-id="b3cba-147">To get you started, the policy settings have default values.</span></span> <span data-ttu-id="b3cba-148">既定値が要件を満たす場合は、変更を加える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b3cba-148">You do not have to make any changes if the default values meet your requirements.</span></span>

    > [!TIP]
    > これらのポリシー設定は、作業コンテキストでアプリを使用する場合にのみ適用されます。  エンド ユーザーが、個人のタスクを実行するためにアプリを使用する場合、これらのポリシーによって設定が影響を受けることはありません。

    ![[ポリシーの追加] ブレードと [設定] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  <span data-ttu-id="b3cba-152">**[OK]** を選択して、この構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-152">Choose **OK** to save this configuration.</span></span> <span data-ttu-id="b3cba-153">これにより、 **[ポリシーの追加]** ブレードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="b3cba-153">You are now back in the **Add a policy** blade.</span></span> <span data-ttu-id="b3cba-154">**[作成]** を選択してポリシーを作成し、設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-154">Choose **Create** to create the policy and save your settings.</span></span>

    ![アプリと設定が構成されていることを示す [ポリシーの追加] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)

<span data-ttu-id="b3cba-156">前の手順の説明に従ってポリシーの作成が完了した時点では、ポリシーはユーザーに展開されません。</span><span class="sxs-lookup"><span data-stu-id="b3cba-156">When you finish creating a policy as described in the previous procedure, it is not deployed to any users.</span></span> <span data-ttu-id="b3cba-157">ポリシーを展開するには、次のセクションの「ユーザーへのポリシーの展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3cba-157">To deploy a policy, see the following section, "Deploy a policy to users."</span></span>

> [!IMPORTANT]
> Intune 管理コンソールでアプリのアプリ保護ポリシーを作成し、Azure ポータルでアプリ保護ポリシーを作成した場合は、Azure ポータルで作成したポリシーが優先されます。 ただし、Intune または Configuration Manager のコンソールのレポート機能では、Intune 管理コンソールから作成されたポリシー設定がレポート対象となります。 たとえば、
>
> -   アプリからのコピーがブロックされている Intune 管理コンソールでアプリ保護ポリシーを作成しました。
> -   アプリからのコピーが許可されている Azure コンソールでアプリ保護ポリシーを作成しました。
> -   これら両方のポリシーを同じアプリに関連付けます。
> -   Azure コンソールから作成したポリシーが優先され、コピーが許可されることになります。
> -   ただし、Intune コンソールのステータスとレポートは、コピーがブロックされているという正しくない情報を示します。

## <a name="line-of-business-lob-apps-optional"></a><span data-ttu-id="b3cba-166">基幹業務 (LOB) アプリ (オプション)</span><span class="sxs-lookup"><span data-stu-id="b3cba-166">Line of Business (LOB) apps (optional)</span></span>

<span data-ttu-id="b3cba-167">Intune 1703 バージョン以降では、新しいアプリ保護ポリシーを作成するときに、LOB アプリを Intune に一般的に追加するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b3cba-167">Beginning with Intune 1703 version, you have the option to generally add LOB apps into Intune when creating a new app protection policy.</span></span> <span data-ttu-id="b3cba-168">この方法では、完全なアプリ展開アクセス許可がなくても、MAM SDK を使って LOB アプリ用のアプリ保護ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-168">This gives you the option to define app protection policies for LOB apps using the MAM SDK without requiring full app deployment permissions.</span></span>
<span data-ttu-id="b3cba-169">/intune/app-sdk-get-started</span><span class="sxs-lookup"><span data-stu-id="b3cba-169">/intune/app-sdk-get-started</span></span>
> [!TIP]
> [Intune App SDK](/intune/app-sdk-get-started) ワークフローの過程で Intune に LOB アプリを追加することもできます。

> [!IMPORTANT]
> ユーザーが MAM アプリ展開用のアクセス許可しか持たず、任意のアプリを Intune に展開できる完全なアプリ展開アクセス許可がない場合は、Intune SDK ワークフローを実行することはできませんが、その場合でも MAM アプリ保護ポリシー作成ワークフローを使って LOB アプリを追加できます。

### <a name="to-add-lob-apps-ios-and-android"></a><span data-ttu-id="b3cba-172">LOB アプリを追加するには (iOS と Android)</span><span class="sxs-lookup"><span data-stu-id="b3cba-172">To add LOB apps (iOS and Android)</span></span>

1.  <span data-ttu-id="b3cba-173">[ポリシーの追加] ブレードで **[アプリ]** の構成を選んで、[アプリ] ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-173">On the Add a policy blade, choose Configure **Apps** to open the Apps blade.</span></span>

    ![MAM の [ポリシーの追加] ブレード](../media/AppManagement/mam-lob-apps-1.png)

2.  <span data-ttu-id="b3cba-175">**[その他のアプリ]** をクリックし、**[バンドル ID]**\(iOS の場合) または **[パッケージ ID]**\(Android の場合) を入力した後、[選択] をクリックして LOB アプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-175">Click **More apps**, then enter the **Bundle ID** (for iOS), **package ID** (for Android), then click Select to add your LOB apps.</span></span>

    ![MAM の [その他のアプリ] ブレード](../media/AppManagement/mam-lob-apps-2.png)

### <a name="to-add-lob-apps-windows"></a><span data-ttu-id="b3cba-177">LOB アプリを追加するには (Windows)</span><span class="sxs-lookup"><span data-stu-id="b3cba-177">To add LOB apps (Windows)</span></span>

> [!IMPORTANT]
> 新しいアプリ保護ポリシーを作成するときは、[プラットフォーム] ドロップダウン リストから [Windows 10] を選ぶ必要があります。

1.  <span data-ttu-id="b3cba-179">[ポリシーの追加] ブレードで、**[許可されたアプリ]** または **[適用から除外されるアプリ]** を選んで、許可するアプリまたは除外するアプリのブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-179">On the Add a policy blade, choose **Allowed apps** or **Exempt apps** to open the Allowed or Exempt apps blade.</span></span>

    > [!NOTE]
    >
    - <span data-ttu-id="b3cba-180">**[許可されたアプリ]**: このポリシーに準拠する必要があるアプリです。</span><span class="sxs-lookup"><span data-stu-id="b3cba-180">**Allowed apps**: These are the apps that need to adhere to this policy.</span></span>
    - <span data-ttu-id="b3cba-181">**[適用から除外されるアプリ]**: これらのアプリはこのポリシーから除外され、制限なしに企業データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-181">**Exempt apps**: These apps are exempt from this policy and can access corporate data without restrictions.</span></span>
<br></br>
2. <span data-ttu-id="b3cba-182">許可するアプリまたは除外するアプリのブレードで、**[アプリの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3cba-182">On Allowed or Exempt apps blade, click **Add apps**.</span></span> <span data-ttu-id="b3cba-183">推奨される Microsoft アプリ、ストア アプリ、またはデスクトップ アプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-183">You can add recommended Microsoft apps, add store or desktop apps.</span></span>

    <span data-ttu-id="b3cba-184">a.</span><span class="sxs-lookup"><span data-stu-id="b3cba-184">a.</span></span>  <span data-ttu-id="b3cba-185">**[おすすめのアプリ]:** 管理者がポリシーに簡単にインポートできるようにあらかじめ設定されている (ほとんどは Office) アプリの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b3cba-185">**Recommended apps:** a pre-populated list of (mostly Office) apps that we let admins easily import into policy.</span></span>

    <span data-ttu-id="b3cba-186">b.</span><span class="sxs-lookup"><span data-stu-id="b3cba-186">b.</span></span>  <span data-ttu-id="b3cba-187">**[ストア アプリ]:** 管理者は、Windows ストアからポリシーに任意のアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-187">**Store apps:** Admin can add any app from the Windows store to policy.</span></span>

    <span data-ttu-id="b3cba-188">c.</span><span class="sxs-lookup"><span data-stu-id="b3cba-188">c.</span></span>  <span data-ttu-id="b3cba-189">**[Windows desktop apps (Windows デスクトップ アプリ)]:** 管理者は従来の Windows デスクトップ アプリをポリシーに追加できます (exe、dll など)。</span><span class="sxs-lookup"><span data-stu-id="b3cba-189">**Windows desktop apps:** Admin can add any traditional Windows desktop apps to the policy (e.g. exe, dll, etc.)</span></span>

## <a name="deploy-a-policy-to-users"></a><span data-ttu-id="b3cba-190">ユーザーへのポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="b3cba-190">Deploy a policy to users</span></span>

1.  <span data-ttu-id="b3cba-191">**[ポリシー]** ブレードで **[ユーザー グループ]** を選択して、**[ユーザー グループ]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-191">In the **Policy** blade, choose  **User groups**, which opens the **User groups** blade.</span></span> <span data-ttu-id="b3cba-192">**[ユーザー グループ]** ブレードで **[ユーザー グループの追加]** を選択して、**[ユーザー グループの追加]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-192">Choose **Add user group** in the **User groups** blade to open the **Add user group** blade.</span></span>

    ![[ユーザー グループの追加] メニュー オプションが強調表示されている [ユーザー グループ] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  <span data-ttu-id="b3cba-194">ユーザー グループの一覧が、 **[ユーザー グループの追加]** ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-194">A list of user groups is displayed on the **Add user group** blade.</span></span> <span data-ttu-id="b3cba-195">これは、 **Azure Active Directory**内にあるすべてのセキュリティ グループの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b3cba-195">This is a list of all the security groups in your **Azure Active Directory**.</span></span> <span data-ttu-id="b3cba-196">このポリシーを適用するユーザー グループを選択し、**[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-196">Select the user groups you want this policy to apply to, and then choose **Select**.</span></span> <span data-ttu-id="b3cba-197">**[選択]** を選択すると、ポリシーがユーザーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-197">Choosing **Select**, deploys the policy to users.</span></span>

    ![Azure Active Directory ユーザーの一覧を示している [ユーザー グループの追加] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    <span data-ttu-id="b3cba-199">これで、作成したポリシーはユーザーに展開されました。</span><span class="sxs-lookup"><span data-stu-id="b3cba-199">You have now created a policy and deployed it to users.</span></span>

<span data-ttu-id="b3cba-200">Intune ライセンスが割り当てられているユーザーのみが、このポリシーの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-200">Only users with Intune licenses assigned to them are affected by the policy.</span></span> <span data-ttu-id="b3cba-201">選択したセキュリティ グループ内のユーザーのうち、Intune ライセンスが割り当てられていないユーザーは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="b3cba-201">Users who are in the security group that you selected who don’t have a Intune license assigned to them are not affected.</span></span>

>[!IMPORTANT]
> Intune を使用し、Configuration Manager によって iOS デバイスと Android デバイスを管理する場合、このポリシーは、選択したグループ直下のユーザーにのみ適用されます。 選択したグループ内にネストされた子グループのメンバーは、影響を受けません。

<span data-ttu-id="b3cba-204">エンド ユーザーは App Store または Google Play からアプリをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-204">End users can download the apps from the App store or Google Play.</span></span> <span data-ttu-id="b3cba-205">詳細については、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b3cba-205">For more information, see:</span></span>
* [<span data-ttu-id="b3cba-206">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="b3cba-206">What to expect when your Android app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-android)
* [<span data-ttu-id="b3cba-207">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="b3cba-207">What to expect when your iOS app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-ios)

##  <a name="change-existing-policies"></a><span data-ttu-id="b3cba-208">既存のポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="b3cba-208">Change existing policies</span></span>
<span data-ttu-id="b3cba-209">既存のポリシーを編集して、対象ユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-209">You can edit an existing policy and apply it to the targeted users.</span></span> <span data-ttu-id="b3cba-210">ただし、既存のポリシーを変更する場合、アプリに既にサインインしているユーザーには、8 時間にわたって変更が表示されません。</span><span class="sxs-lookup"><span data-stu-id="b3cba-210">However, when you change existing policies,  users who are already signed  in to the apps won’t see the changes for an 8-hour period.</span></span>

<span data-ttu-id="b3cba-211">変更の効果をすぐに確認するには、エンド ユーザーはアプリをログアウトし、もう一度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3cba-211">To see the effect of the changes immediately, the end user will have to log out of the app, and sign back in.</span></span>

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a><span data-ttu-id="b3cba-212">ポリシーに関連付けられているアプリの一覧を変更するには</span><span class="sxs-lookup"><span data-stu-id="b3cba-212">To change the list of apps associated with the policy</span></span>

1.  <span data-ttu-id="b3cba-213">**[アプリ ポリシー]** ブレードで、変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-213">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="b3cba-214">これにより、選択したポリシーに固有のブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-214">This opens a blade specific to the policy you just selected.</span></span>

    ![別のブレードで開かれている既存のポリシーのスクリーン ショット](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  <span data-ttu-id="b3cba-216">ポリシー ブレードで **[対象アプリ]** をクリックし、アプリの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-216">In the policy blade, choose **Targeted apps** to open the list of apps.</span></span>

3.  <span data-ttu-id="b3cba-217">一覧からアプリを削除または追加し、**[保存]** アイコンを選択して変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-217">Remove or add apps from the list and choose the **Save** icon to save your changes.</span></span>

### <a name="to-change-the-list-of-user-groups"></a><span data-ttu-id="b3cba-218">ユーザー グループの一覧を変更するには</span><span class="sxs-lookup"><span data-stu-id="b3cba-218">To change the list of user groups</span></span>

1.  <span data-ttu-id="b3cba-219">**[アプリ ポリシー]** ブレードで、変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-219">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="b3cba-220">これにより、選択したポリシーに固有のブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-220">This opens the blade specific to the policy you selected.</span></span>

2.  <span data-ttu-id="b3cba-221">ポリシー ブレードで **[ユーザー グループ]** をクリックして **[ユーザー グループ]** ブレードを開きます。このブレードには、このポリシーが設定された現在のユーザー グループの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-221">In the policy blade, choose **User groups** to open the **User group** blade that shows the list of current user groups who have this policy.</span></span>

3.  <span data-ttu-id="b3cba-222">ポリシーに新しいユーザー グループを追加するには、**[ユーザー グループの追加]** を選択し、ユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-222">To add a new user group to the policy, choose **Add user group**, and select the user group.</span></span> <span data-ttu-id="b3cba-223">**[選択]** を選択して、選択したグループにポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-223">Choose **Select** to deploy the policy to the group you selected.</span></span>

    ![2 人のユーザー グループが選択されている [ユーザー グループの追加] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  <span data-ttu-id="b3cba-225">ユーザー グループを削除するには、削除するユーザー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-225">To delete a user group, highlight the user group you want to remove.</span></span> <span data-ttu-id="b3cba-226">省略記号 (...) を選択し、**[削除]** を選択してユーザー グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-226">Then choose the ellipses (…), and choose **Delete** to remove the user group.</span></span>

    ![<span data-ttu-id="b3cba-227">[削除] オプションが表示されたスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="b3cba-227">Screenshot showing Delete option</span></span> ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <a name="to-change-policy-settings"></a><span data-ttu-id="b3cba-228">ポリシー設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="b3cba-228">To change policy settings</span></span>

1.  <span data-ttu-id="b3cba-229">**[アプリ ポリシー]** ブレードで、変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-229">In the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="b3cba-230">これにより、選択したポリシーに固有のブレードが開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-230">This opens a blade specific to the policy you just selected.</span></span>

    ![<span data-ttu-id="b3cba-231">別のブレードで開かれている既存のポリシーのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="b3cba-231">Screenshot of an existing policy open in a separate blade</span></span> ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  <span data-ttu-id="b3cba-232">**[ポリシー設定]** をクリックして **[ポリシー設定]** ブレードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3cba-232">Choose **Policy settings** to open the **Policy settings** blade.</span></span>

3.  <span data-ttu-id="b3cba-233">設定を変更し、**[保存]** アイコンを選択して変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-233">Change the settings, and choose the **Save** icon to save your changes.</span></span>

    ![上部に [保存] オプションが表示された [ポリシー設定] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <a name="policy-settings"></a><span data-ttu-id="b3cba-235">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="b3cba-235">Policy settings</span></span>
<span data-ttu-id="b3cba-236">iOS と Android 用のポリシー設定の完全な一覧を表示するには、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3cba-236">To see a full list of the policy settings for iOS and Android, select one of the following:</span></span>

> [!div class="op_single_selector"]
- [<span data-ttu-id="b3cba-237">iOS ポリシー</span><span class="sxs-lookup"><span data-stu-id="b3cba-237">iOS policies</span></span>](ios-mam-policy-settings.md)
- [<span data-ttu-id="b3cba-238">Android ポリシー</span><span class="sxs-lookup"><span data-stu-id="b3cba-238">Android policies</span></span>](android-mam-policy-settings.md)

## <a name="next-steps"></a><span data-ttu-id="b3cba-239">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b3cba-239">Next steps</span></span>
[<span data-ttu-id="b3cba-240">コンプライアンスとユーザーの状態を監視する</span><span class="sxs-lookup"><span data-stu-id="b3cba-240">Monitor compliance and user status</span></span>](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <a name="see-also"></a><span data-ttu-id="b3cba-241">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3cba-241">See also</span></span>
* [<span data-ttu-id="b3cba-242">アプリ保護ポリシーを使用して Android アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="b3cba-242">What to expect when your Android app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-android)
* [<span data-ttu-id="b3cba-243">アプリ保護ポリシーを使用して iOS アプリを管理するときの注意点</span><span class="sxs-lookup"><span data-stu-id="b3cba-243">What to expect when your iOS app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-ios)
