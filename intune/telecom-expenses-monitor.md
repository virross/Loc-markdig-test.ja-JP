---
title: "通信費管理サービスをセットアップする"
titleSuffix: Azure portal
description: "Saaswedo 通信費管理サービスを Intune と統合するように構成します。\""
keywords: Saaswedo
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: af69568df461d992a02800a7e188bf0ca71e51d5
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a><span data-ttu-id="faff1-104">Intune で通信費管理サービスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="faff1-104">Set up a telecom expense management service in Intune</span></span>
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="faff1-105">Intune を使用して、企業所有のモバイル デバイスでのデータの使用から発生する通信費を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="faff1-105">Intune enables you to manage telecom expenses incurred from data usage on corporate-owned mobile devices.</span></span> <span data-ttu-id="faff1-106">この機能を有効にするために、Intune は、サードパーティのソフトウェア開発企業である Saaswedo の Datalert 通信費管理ソリューションと統合されています。</span><span class="sxs-lookup"><span data-stu-id="faff1-106">To enable this capability, Intune has integrated with the third-party software developer Saaswedo’s Datalert telecom expense management solution.</span></span> <span data-ttu-id="faff1-107">Datalert とは、Intune で管理されているデバイスの通信データ使用量を管理し、コストのかかる予想外のデータ超過やローミング超過を防止することができる、リアルタイム通信費管理ソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="faff1-107">Datalert is real-time telecom expense management software that lets you manage telecom data usage and avoid costly and unexpected data and roaming overages for your Intune-managed devices.</span></span>

<span data-ttu-id="faff1-108">Intune と Datalert の統合により、定義済みのしきい値を超えた場合に警告する自動化されたアラートを使用することで、ローミングおよび国内のデータ使用料の上限を一元的に設定、監視、適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="faff1-108">Intune's integration with Datalert enables you to centrally set, monitor and enforce roaming and domestic data usage limits by using automated alerts when the limits exceed defined thresholds.</span></span> <span data-ttu-id="faff1-109">ユーザーがしきい値を超過した場合に、ローミングの無効化を含むさまざまなアクションを個々のエンド ユーザーやそのグループに適用するように、サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="faff1-109">You can configure the service to apply different actions to individuals or groups of end users, including disabling roaming, when users exceed the threshold.</span></span> <span data-ttu-id="faff1-110">Datalert 管理コンソールでは、データ使用量と監視情報を示すレポートが利用できます。</span><span class="sxs-lookup"><span data-stu-id="faff1-110">Reports that provide data usage and monitoring information are available from the Datalert management console.</span></span>

<span data-ttu-id="faff1-111">次の図は、Intune が Datalert とどのように統合されているかを示しています。</span><span class="sxs-lookup"><span data-stu-id="faff1-111">The following diagram shows how Intune integrates with Datalert.</span></span>

  ![Intune と Datalert の統合図](./media/tem-datalert-intune-solution-diagram.png)

<span data-ttu-id="faff1-113">Datalert サービスを Intune で使用するには、Datalert コンソールと Intune で設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="faff1-113">Before you can use the Datalert service with Intune, you need to configure settings in the Datalert console and in Intune.</span></span> <span data-ttu-id="faff1-114">Datalert サービスと Intune の接続を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="faff1-114">The connection must be turned on for the Datalert service and for Intune.</span></span> <span data-ttu-id="faff1-115">Datalert 側の接続が有効になっていても Intune 側が有効になっていない場合、Intune は通信を受け入れますが無視します。</span><span class="sxs-lookup"><span data-stu-id="faff1-115">If the Datalert side of the connection is enabled, but not the Intune side, Intune receives the communication, but ignores it.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="faff1-116">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="faff1-116">Supported platforms</span></span>

- <span data-ttu-id="faff1-117">Samsung KNOX</span><span class="sxs-lookup"><span data-stu-id="faff1-117">Samsung Knox</span></span>
- <span data-ttu-id="faff1-118">iOS 8.0 以降</span><span class="sxs-lookup"><span data-stu-id="faff1-118">iOS 8.0 and later</span></span>

## <a name="prerequisites"></a><span data-ttu-id="faff1-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="faff1-119">Prerequisites</span></span>

- <span data-ttu-id="faff1-120">Microsoft Intune のサブスクリプションおよび Azure Portal へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="faff1-120">A subscription to Microsoft Intune, and access to the Azure portal.</span></span>
- <span data-ttu-id="faff1-121">Datalert 通信費管理サービスのサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="faff1-121">A subscription to the Datalert telecom expense management service</span></span>

## <a name="list-of-telecom-expense-management-providers"></a><span data-ttu-id="faff1-122">通信費管理プロバイダーの一覧</span><span class="sxs-lookup"><span data-stu-id="faff1-122">List of telecom expense management providers</span></span>

<span data-ttu-id="faff1-123">Intune は、現時点で以下の通信費管理プロバイダーと統合されています。</span><span class="sxs-lookup"><span data-stu-id="faff1-123">Intune currently integrates with the following telecom expense management providers:</span></span>

[<span data-ttu-id="faff1-124">Saaswedo Datalert 通信費管理サービス</span><span class="sxs-lookup"><span data-stu-id="faff1-124">Saaswedo Datalert telecom expense management service</span></span>](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a><span data-ttu-id="faff1-125">Intune と Datalert の統合ソリューションをデプロイする</span><span class="sxs-lookup"><span data-stu-id="faff1-125">Deploy the Intune and Datalert integrated solution</span></span>

<span data-ttu-id="faff1-126">開始する前に、Intune および Datalert 通信費管理サービスのサブスクリプションがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="faff1-126">Before you start, make sure that you already have an Intune and a Datalert telecom expense management service subscription.</span></span>

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a><span data-ttu-id="faff1-127">手順 1: Datalert サービスを Microsoft Intune に接続する</span><span class="sxs-lookup"><span data-stu-id="faff1-127">Step 1: Connect the Datalert service to Microsoft Intune</span></span>

1. <span data-ttu-id="faff1-128">管理者資格情報を使用して Datalert 管理コンソールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="faff1-128">Sign into the Datalert management console with your administrator credentials.</span></span>

2. <span data-ttu-id="faff1-129">Datalert 管理コンソールで、**[Settings (設定)]** タブに移動し、さらに **[MDM configuration (MDM の構成)]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="faff1-129">On the Datalert management console, go to the **Settings** tab, and then to **MDM configuration**.</span></span>

3. <span data-ttu-id="faff1-130">**[Unblock (ブロック解除)]** を選択して、ページに設定を入力できるようにします。</span><span class="sxs-lookup"><span data-stu-id="faff1-130">Select **Unblock** to enable you to enter the settings on the page.</span></span>

4. <span data-ttu-id="faff1-131">**[Server MDM (サーバー MDM)]** で、**[Microsoft Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-131">For **Server MDM**, choose **Microsoft Intune**.</span></span>

5. <span data-ttu-id="faff1-132">**[Azure AD domain (Azure AD ドメイン]** に Azure テナント ID を入力し、**[Connection (接続)]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="faff1-132">For **Azure AD domain**, enter your Azure tenant ID, and then select the **Connection** button.</span></span>

    <span data-ttu-id="faff1-133">**[Connection (接続)]** を選択すると、Datalert と Intune の間に既存の接続がないことを確認するために、Datalert サービスによって Intune へのチェックインが行われます。</span><span class="sxs-lookup"><span data-stu-id="faff1-133">Selecting **Connection** makes the Datalert service check in with Intune to ensure that there are no pre-existing Datalert connections with Intune.</span></span> <span data-ttu-id="faff1-134">数秒後に Microsoft ログイン ページが表示され、その後に Datalert Azure 認証が行われます。</span><span class="sxs-lookup"><span data-stu-id="faff1-134">After a few seconds, a Microsoft log-in page appears, followed by the Datalert Azure authentication.</span></span>

6. <span data-ttu-id="faff1-135">Microsoft 認証ページで、**[Accept (同意する)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-135">On the Microsoft authentication page, select **Accept**.</span></span> <span data-ttu-id="faff1-136">Datalert の "Thank you" ページにリダイレクトされ、数秒後にそのページが閉じます。</span><span class="sxs-lookup"><span data-stu-id="faff1-136">You are redirected to a Datalert “thank you” page, which closes after a few seconds.</span></span> <span data-ttu-id="faff1-137">Datalert によって接続が検証され、検証済みの項目一覧の横に緑色のチェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="faff1-137">Datalert validates the connection, and displays green check marks beside a list of items that it validated.</span></span> <span data-ttu-id="faff1-138">検証に失敗した場合は、赤色のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="faff1-138">If the validation fails, you see a message in red.</span></span> <span data-ttu-id="faff1-139">その場合は、Datalert サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="faff1-139">If this happens, contact Datalert Support for help.</span></span>

    <span data-ttu-id="faff1-140">次のスクリーン ショットは、接続に成功した場合に表示されることが期待できる緑色のチェック マークを示しています。</span><span class="sxs-lookup"><span data-stu-id="faff1-140">The following screenshot shows the green check marks that you can expect to see once the connection is successful.</span></span>

   ![接続が成功したことを示している Datalert ページ](./media/tem-mdm-configuration-mdm-server-page.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a><span data-ttu-id="faff1-142">手順 2: 通信費管理機能が Intune でアクティブであることを確認する</span><span class="sxs-lookup"><span data-stu-id="faff1-142">Step 2: Check that the telecom expense management feature is Active in Intune</span></span>

<span data-ttu-id="faff1-143">上記の手順 1 を完了すると、接続が自動的に有効になり、接続状態 **[アクティブ]** が Azure Portal に表示されます。</span><span class="sxs-lookup"><span data-stu-id="faff1-143">After you complete Step 1 above, your connection should be automatically enabled, and a connection status of **Active** should be showing in the Azure portal.</span></span> <span data-ttu-id="faff1-144">次の手順は、**[アクティブ]** 状態を確認する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="faff1-144">These steps show you how to check for the **Active** status.</span></span>

1. <span data-ttu-id="faff1-145">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="faff1-145">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="faff1-146">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-146">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

3. <span data-ttu-id="faff1-147">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-147">On the **Intune** blade, choose **Device configuration**.</span></span>

4. <span data-ttu-id="faff1-148">**[デバイス構成]** ブレードで、**[セットアップ]** > **[通信費管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-148">On the **Device Configuration** blade, choose **Setup** > **Telecom Expense Management**.</span></span>

   <span data-ttu-id="faff1-149">ページの上部に表示されている接続状態が**[アクティブ]** になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="faff1-149">Look for the **Active** connection status at the top of the page.</span></span>

   ![Datalert との接続状態がアクティブであることを示している Azure Portal](./media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a><span data-ttu-id="faff1-151">手順 3: Datalert アプリを企業登録デバイスにデプロイする</span><span class="sxs-lookup"><span data-stu-id="faff1-151">Step 3: Deploy the Datalert app to corporate enrolled devices</span></span>

<span data-ttu-id="faff1-152">企業所有のデバイスからのデータ使用量のみを確実に収集するには、Intune でデバイスのカテゴリを作成した後、Datalert アプリの対象を企業の電話だけにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="faff1-152">To ensure that data usage from only corporate-owned lines is collected, you need to create device categories in Intune, and then target the Datalert app to only corporate phones.</span></span> <span data-ttu-id="faff1-153">次のサブセクションの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="faff1-153">Complete the steps in the following subsections.</span></span>

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a><span data-ttu-id="faff1-154">デバイスのカテゴリと各カテゴリにマップされるデバイス グループを定義する</span><span class="sxs-lookup"><span data-stu-id="faff1-154">Define device categories and device groups mapped to the categories</span></span>

<span data-ttu-id="faff1-155">組織のニーズに従って、少なくとも 2 つのデバイス カテゴリ (たとえば、企業と個人) を作成し、各カテゴリの動的なデバイス グループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="faff1-155">Depending on your organizational needs, you'll need to create at least two device categories (for example, Corporate and Personal) and create dynamic device groups for each category.</span></span> <span data-ttu-id="faff1-156">必要に応じて、組織用のその他のカテゴリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="faff1-156">You can create more categories for your organization, as needed.</span></span>

<span data-ttu-id="faff1-157">これらのカテゴリは、登録時にユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="faff1-157">These categories will be shown to users during enrollment.</span></span> <span data-ttu-id="faff1-158">ユーザーが選択したカテゴリに応じて、登録デバイスは該当するデバイス グループに移動されます。</span><span class="sxs-lookup"><span data-stu-id="faff1-158">Depending on which category users choose, the enrolled device will be moved to the corresponding device group.</span></span> <span data-ttu-id="faff1-159">デバイスのカテゴリを作成する方法の手順については、「[Map devices to groups](device-group-mapping.md)」(デバイスをグループにマップする) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="faff1-159">For steps on how to create device categories, see [Map devices to groups](device-group-mapping.md).</span></span>

  ![[ポリシーの追加] ブレードのスクリーンショット](./media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a><span data-ttu-id="faff1-161">Intune で Datalert アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="faff1-161">Create the Datalert app in Intune</span></span>

<span data-ttu-id="faff1-162">次の手順に従って、プラットフォームごとに、Intune で Datalert アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="faff1-162">Follow these steps to create the Datalert app in Intune for each platform.</span></span> <span data-ttu-id="faff1-163">次の手順では、例として iOS を使用します。</span><span class="sxs-lookup"><span data-stu-id="faff1-163">iOS is used as an example in these steps.</span></span>

1. <span data-ttu-id="faff1-164">Azure Portal の **[Intune]** ブレードで、**[Mobile Apps]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-164">On the **Intune** blade of the Azure portal, choose **Mobile apps**.</span></span>

2. <span data-ttu-id="faff1-165">**[Mobile Apps]** ブレードで、**[管理]**  >  **[アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-165">On the **Mobile apps** blade, choose **Manage** > **Apps**.</span></span>

3. <span data-ttu-id="faff1-166">**[追加]** を選択してアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="faff1-166">Select **Add** to add an app.</span></span>

4. <span data-ttu-id="faff1-167">アプリの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-167">Select the app type.</span></span> <span data-ttu-id="faff1-168">たとえば、iOS の場合は、**[iOS ストア アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-168">For example, for iOS, you would select **iOS Store App**.</span></span>

5. <span data-ttu-id="faff1-169">**[アプリ ストアを検索します]** で、検索ウィンドウに「**Datalert**」と入力して、Datalert アプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="faff1-169">In **Search the App Store**, look for the Datalert app by typing **Datalert** in the search window.</span></span>

6. <span data-ttu-id="faff1-170">**Datalert** アプリを選択し、**[OK]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-170">Select the **Datalert** app, and select **OK**.</span></span>

   ![[ポリシーの追加] ブレードのスクリーンショット](./media/tem-select-app-from-apple-app-store.png)

7. <span data-ttu-id="faff1-172">残りの手順を完了して、IOS 用アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="faff1-172">Complete the remaining steps to create an app for iOS.</span></span>

   ![[ポリシーの追加] ブレードのスクリーンショット](./media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a><span data-ttu-id="faff1-174">Datalert アプリを企業のデバイス グループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="faff1-174">Assign the Datalert app to the corporate device group</span></span>

1. <span data-ttu-id="faff1-175">前の手順で作成した iOS Datalert アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-175">Select the iOS Datalert app that you created in the previous step.</span></span>

2. <span data-ttu-id="faff1-176">**[アプリ]** ブレードで、**[管理]** > **[割り当て]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="faff1-176">On the **Apps** blade, go to **Manage** > **Assignments**.</span></span>

3. <span data-ttu-id="faff1-177">**[グループの選択]** を選択し、企業のデバイス グループを選択する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="faff1-177">Choose **Select groups**, and follow the steps to select the corporate device group.</span></span>

4. <span data-ttu-id="faff1-178">グループにとってアプリのインストールが必須であるか省略可能であるかを選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-178">Choose whether to make the app installation required or optional for the group.</span></span> <span data-ttu-id="faff1-179">次の例のスクリーンショットは、インストールが必須であることを示しています。つまり、ユーザーは、自分のデバイスを登録した後、Datalert アプリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="faff1-179">The following example screenshot shows the installation as required, which means that users must install the Datalert app installation after enrolling their device.</span></span>

   ![[ポリシーの追加] ブレードのスクリーンショット](./media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a><span data-ttu-id="faff1-181">手順 4: 企業が料金を支払う電話回線をDatalert コンソールに追加する</span><span class="sxs-lookup"><span data-stu-id="faff1-181">Step 4: Add corporate paid phone lines to the Datalert console</span></span>

<span data-ttu-id="faff1-182">これで、Intune サービスと Datalert サービスが互いに通信するように構成されました。</span><span class="sxs-lookup"><span data-stu-id="faff1-182">You now have configured the Intune and Datalert services to communicate with each other.</span></span> <span data-ttu-id="faff1-183">次に、企業が料金を支払う電話回線を Datalert コンソールに追加し、携帯データまたはローミング データの使用量違反に対するしきい値と動作を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="faff1-183">You now need to add your corporate paid phone lines to the Datalert console and define thresholds and actions for any cellular or roaming usage violations.</span></span> <span data-ttu-id="faff1-184">企業が料金を支払う電話回線は、手動で Datalert コンソールに追加するか、あるいはデバイスが Intune に登録されたら自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="faff1-184">You can either add corporate paid phone lines to the Datalert console manually or have the lines added automatically after the device is enrolled into Intune.</span></span>

<span data-ttu-id="faff1-185">これらの項目を設定するには、[[Datalert setup for Microsoft Intune (Microsoft Intune 用のDatalert のセットアップ)]](http://www.datalert.fr/microsoft-intune/intune-setup) ページ (http://www.datalert.fr/microsoft-intune/intune-setup) に移動し、**[Settings (設定)]** タブでセットアップ ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="faff1-185">To set these items, go to the [Datalert setup for Microsoft Intune page](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup), and follow the steps in the setup wizard under the **Settings** tab.</span></span>

  ![[ポリシーの追加] ブレードのスクリーンショット](./media/tem-add-phone-lines-to-datalert-console.png)


<span data-ttu-id="faff1-187">これで Datalert サービスがアクティブになってデータ使用量の監視が開始され、デバイスでの構成済み使用量制限を超える携帯データおよびローミング データが無効化されるようになります。</span><span class="sxs-lookup"><span data-stu-id="faff1-187">The Datalert service is now active, and it starts monitoring data usage and disabling cellular and roaming data on devices that exceed the configured usage limits.</span></span>

## <a name="client-enrollment-experience"></a><span data-ttu-id="faff1-188">クライアント登録のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="faff1-188">Client enrollment experience</span></span>
<span data-ttu-id="faff1-189">クライアント登録のエクスペリエンスについては、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="faff1-189">For client enrollment experience see following:</span></span>
-   [<span data-ttu-id="faff1-190">通信費管理サービスに iOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="faff1-190">Enroll your iOS device in telecom expense management</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-   [<span data-ttu-id="faff1-191">通信費管理サービスに Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="faff1-191">Enroll your Android device in telecom expense management</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a><span data-ttu-id="faff1-192">Datalert サービスを無効にする</span><span class="sxs-lookup"><span data-stu-id="faff1-192">Turning off the Datalert service</span></span>

<span data-ttu-id="faff1-193">Azure Portal で Datalert サービスを無効にすると、以下のような影響があります。</span><span class="sxs-lookup"><span data-stu-id="faff1-193">If you disable the Datalert service in the Azure portal:</span></span>

- <span data-ttu-id="faff1-194">過去の使用量制限の違反によってデバイスに適用されたすべてのアクションが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="faff1-194">All of the actions that have been applied to devices, due to past violations of the usage limits, are undone.</span></span>
- <span data-ttu-id="faff1-195">ユーザーによるデータ アクセスとローミングがブロックされなくなります。</span><span class="sxs-lookup"><span data-stu-id="faff1-195">Users are no longer blocked from data access and roaming.</span></span>
- <span data-ttu-id="faff1-196">Intune は引き続きサービスからの信号を受け入れますが、それらを無視するようになります。</span><span class="sxs-lookup"><span data-stu-id="faff1-196">Intune still receives the signals coming from the service, but ignores them.</span></span>

<span data-ttu-id="faff1-197">**サービスを無効にするには**</span><span class="sxs-lookup"><span data-stu-id="faff1-197">**To turn off the service**</span></span>

1. <span data-ttu-id="faff1-198">Azure Portal の **[通信費管理]** ブレードで、**[無効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-198">On the **Telecom Expense Management** blade in the Azure portal, select **Disable**.</span></span>

2. <span data-ttu-id="faff1-199">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="faff1-199">Select **Save**.</span></span>

## <a name="viewing-data-usage-and-roaming-reports"></a><span data-ttu-id="faff1-200">データ使用量およびローミング レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="faff1-200">Viewing data usage and roaming reports</span></span>

<span data-ttu-id="faff1-201">現時点では、Saaswedo の Datalert 管理コンソールでのみデータ使用量のレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="faff1-201">At this time, data usage reporting is available only in Saaswedo’s Datalert management console.</span></span>

<span data-ttu-id="faff1-202">エンドユーザーが Datalert アプリをインストールするための手順はまもなく追加されます。</span><span class="sxs-lookup"><span data-stu-id="faff1-202">The instructions that your end users follow to install the Datalert app will be added soon.</span></span>
