---
title: "管理対象の Android デバイス用アプリ構成ポリシーを追加する | Microsoft Docs"
titlesuffix: Azure portal
description: "アプリ構成ポリシーを使用して、実行時に構成データを Android for Work アプリに提供する方法について説明します。"
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c60ed578c02a2b07b6c7c57067c3a3f37f2f6e42
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a><span data-ttu-id="de5e9-103">管理対象の Android デバイス用アプリ構成ポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="de5e9-103">Add app configuration policies for managed Android devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="de5e9-104">Microsoft Intune のアプリ構成ポリシーを使用して、ユーザーが Android for Work アプリを実行するときに設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-104">Use app configuration policies in Microsoft Intune to supply settings when users run an Android for Work app.</span></span> <span data-ttu-id="de5e9-105">これらのポリシーをユーザーとデバイスに直接割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="de5e9-105">You do not assign these policies directly to users and devices.</span></span> <span data-ttu-id="de5e9-106">代わりに、ポリシーをアプリに関連付け、そのアプリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-106">Instead, you associate a policy with an app, and then assign the app.</span></span> <span data-ttu-id="de5e9-107">ポリシー設定は、アプリがポリシーをチェックするとき (通常はアプリの初回実行時) に使用されます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-107">The policy settings are used when the app checks for them, typically the first time it is run.</span></span>

> [!Note]  
> <span data-ttu-id="de5e9-108">アプリ構成をサポートしていないアプリもあります。</span><span class="sxs-lookup"><span data-stu-id="de5e9-108">Not every app supports app configuration.</span></span> <span data-ttu-id="de5e9-109">ビルドされたアプリでアプリ構成ポリシーがサポートされているかどうかについては、アプリの開発者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="de5e9-109">Check with the app developer to see whether they have built their app to support app configuration policies.</span></span>

1. <span data-ttu-id="de5e9-110">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="de5e9-110">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="de5e9-111">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-111">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="de5e9-112">**[モバイル アプリ]** ワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-112">Choose the **Mobile apps** workload.</span></span>
4. <span data-ttu-id="de5e9-113">**[管理]** グループの **[アプリ構成ポリシー]** を選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-113">Choose **App configuration policies** in the **Manage** group, and then choose **Add**.</span></span>
5. <span data-ttu-id="de5e9-114">次の詳細を設定します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-114">Set the following details:</span></span>
    - <span data-ttu-id="de5e9-115">**名前**</span><span class="sxs-lookup"><span data-stu-id="de5e9-115">**Name**</span></span>  
      <span data-ttu-id="de5e9-116">Azure Portal に表示されるプロファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="de5e9-116">The name of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="de5e9-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="de5e9-117">**Description**</span></span>  
      <span data-ttu-id="de5e9-118">Azure Portal に表示されるプロファイルの説明。</span><span class="sxs-lookup"><span data-stu-id="de5e9-118">The  description of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="de5e9-119">**デバイス登録の種類**</span><span class="sxs-lookup"><span data-stu-id="de5e9-119">**Device enrollment type**</span></span>  
      <span data-ttu-id="de5e9-120">**[管理対象デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-120">Choose **Managed devices**.</span></span>
6. <span data-ttu-id="de5e9-121">**[プラットフォーム]** に **[Android]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-121">Select **Android** for **Platform**.</span></span>
7. <span data-ttu-id="de5e9-122">**[関連アプリ]** を選択し、アプリ構成ポリシーを定義するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-122">Select **Associated App** to choose the app for which you want to define an  app configuration policy.</span></span> <span data-ttu-id="de5e9-123">承認して Intune に同期した Android for Work アプリの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-123">Select from the list of Android for Work apps that you have approved and synchronized with Intune.</span></span>
8. <span data-ttu-id="de5e9-124">**[構成設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-124">Select **Configuration settings**.</span></span> <span data-ttu-id="de5e9-125">以下を使用して構成を設定できます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-125">You can set configurations by using:</span></span>
    - [<span data-ttu-id="de5e9-126">構成デザイナー</span><span class="sxs-lookup"><span data-stu-id="de5e9-126">Configuration designer</span></span>](#Use-the-configuration-designer)
    - [<span data-ttu-id="de5e9-127">JSON エディター</span><span class="sxs-lookup"><span data-stu-id="de5e9-127">JSON editor</span></span>](#Enter-the-JSON-editor)
9. <span data-ttu-id="de5e9-128">**[OK]** を選択してから、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-128">Choose **OK**, and then choose **Add**.</span></span>

## <a name="use-the-configuration-designer"></a><span data-ttu-id="de5e9-129">構成デザイナーを使用する</span><span class="sxs-lookup"><span data-stu-id="de5e9-129">Use the configuration designer</span></span>

<span data-ttu-id="de5e9-130">Intune に登録されているデバイスかどうかにかかわらず、アプリには構成デザイナーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-130">You can use the configuration designer for apps on devices that are enrolled or not enrolled in Intune.</span></span> <span data-ttu-id="de5e9-131">デザイナーでは、特定の構成キーと値を構成できます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-131">The designer lets you configure specific configuration keys and values.</span></span> <span data-ttu-id="de5e9-132">各値のデータ型も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de5e9-132">You must also specify the data type for each value.</span></span>

<span data-ttu-id="de5e9-133">構成の各キーと値について、以下を設定します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-133">For each key and value in the configuration, set:</span></span>

  - <span data-ttu-id="de5e9-134">**構成キー**</span><span class="sxs-lookup"><span data-stu-id="de5e9-134">**Configuration key**</span></span>  
     <span data-ttu-id="de5e9-135">特定の設定構成を一意に識別するキー。</span><span class="sxs-lookup"><span data-stu-id="de5e9-135">The key that uniquely identifies the specific setting configuration.</span></span>
  - <span data-ttu-id="de5e9-136">**値の型**</span><span class="sxs-lookup"><span data-stu-id="de5e9-136">**Value type**</span></span>  
    <span data-ttu-id="de5e9-137">構成値のデータ型。</span><span class="sxs-lookup"><span data-stu-id="de5e9-137">The data type of the configuration value.</span></span> <span data-ttu-id="de5e9-138">整数型、実数型、文字列型、またはブール型があります。</span><span class="sxs-lookup"><span data-stu-id="de5e9-138">Types include Integer, Real, String, or Boolean.</span></span>
  - <span data-ttu-id="de5e9-139">**構成値**</span><span class="sxs-lookup"><span data-stu-id="de5e9-139">**Configuration value**</span></span>  
    <span data-ttu-id="de5e9-140">構成の値。</span><span class="sxs-lookup"><span data-stu-id="de5e9-140">The value for the configuration.</span></span> 

## <a name="enter-the-json-editor"></a><span data-ttu-id="de5e9-141">JSON エディターの入力</span><span class="sxs-lookup"><span data-stu-id="de5e9-141">Enter the JSON editor</span></span>

<span data-ttu-id="de5e9-142">構成デザイナーでは構成できないアプリの構成設定もあります (バンドル タイプの構成設定など)。</span><span class="sxs-lookup"><span data-stu-id="de5e9-142">Some configuration settings on apps (such as those with Bundle types) cannot be configured with the configuration designer.</span></span> <span data-ttu-id="de5e9-143">このような値には JSON エディターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de5e9-143">You need to use the JSON editor for those values.</span></span> <span data-ttu-id="de5e9-144">設定は、アプリのインストール時に自動で行われます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-144">Settings are supplied to apps automatically when the app is installed.</span></span>

1. <span data-ttu-id="de5e9-145">**[構成設定の形式]** で、**[Enter JSON editor]\(JSON エディターを使用する\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-145">For **Configuration settings format**, select **Enter JSON editor**.</span></span>
2. <span data-ttu-id="de5e9-146">エディターでは、構成設定の JSON 値を定義できます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-146">In the editor, you can define JSON values for configuration settings.</span></span> <span data-ttu-id="de5e9-147">**[Download JSON template]\(JSON テンプレートをダウンロードする\)** を選択して、構成に使用できるサンプル ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-147">You can choose **Download JSON template** to download a sample file that you can then configure.</span></span>
3. <span data-ttu-id="de5e9-148">**[OK]** を選択してから、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-148">Choose **OK**, and then choose **Add**.</span></span>

<span data-ttu-id="de5e9-149">ポリシーが作成され、ポリシーの一覧ブレードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-149">The policy is created and appears on the policies list blade.</span></span>

<span data-ttu-id="de5e9-150">割り当てたアプリをデバイスで実行すると、アプリ構成ポリシーで構成した設定を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-150">When the assigned app is run on a device, it runs with the settings that you configured in the app configuration policy.</span></span>

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a><span data-ttu-id="de5e9-151">アプリのアクセス許可の状態を事前に構成する</span><span class="sxs-lookup"><span data-stu-id="de5e9-151">Preconfigure the permissions grant state for apps</span></span>

<span data-ttu-id="de5e9-152">Android デバイス機能にアクセスするためのアプリのアクセス許可を事前に構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-152">You can also preconfigure permission for apps to access Android device features.</span></span> <span data-ttu-id="de5e9-153">既定では、場所やデバイス カメラへのアクセスなど、デバイスのアクセス許可を必要とする Android アプリは、アクセス許可の承諾または拒否をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-153">By default, Android apps that require device permissions—such as access to location or the device camera—prompt users to accept or deny permissions.</span></span> <span data-ttu-id="de5e9-154">たとえば、アプリでデバイスのマイクが使用される場合、ユーザーは、そのマイクを使用するアクセス許可をアプリに付与するように求められます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-154">For example, if an app uses the device's microphone, the user is prompted to grant the app permission to use the microphone.</span></span>

1. <span data-ttu-id="de5e9-155">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="de5e9-155">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="de5e9-156">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-156">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="de5e9-157">**[Mobile Apps]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-157">Choose **Mobile apps**.</span></span> <span data-ttu-id="de5e9-158">**[管理]** の下で、**[アプリ構成ポリシー]** を選択してから **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-158">Under **Manage**, choose **App configuration policies**, and then choose **Add**.</span></span>
4. <span data-ttu-id="de5e9-159">次の詳細を設定します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-159">Set the following details:</span></span>
    - <span data-ttu-id="de5e9-160">**名前**。</span><span class="sxs-lookup"><span data-stu-id="de5e9-160">**Name**.</span></span> <span data-ttu-id="de5e9-161">Azure Portal に表示されるプロファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="de5e9-161">The name of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="de5e9-162">**説明**。</span><span class="sxs-lookup"><span data-stu-id="de5e9-162">**Description**.</span></span> <span data-ttu-id="de5e9-163">Azure Portal に表示されるプロファイルの説明。</span><span class="sxs-lookup"><span data-stu-id="de5e9-163">The  description of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="de5e9-164">**プラットフォーム**。</span><span class="sxs-lookup"><span data-stu-id="de5e9-164">**Platform**.</span></span> <span data-ttu-id="de5e9-165">**[Android]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-165">Select **Android**.</span></span>
    - <span data-ttu-id="de5e9-166">**デバイス登録の種類**。</span><span class="sxs-lookup"><span data-stu-id="de5e9-166">**Device enrollment type**.</span></span> <span data-ttu-id="de5e9-167">**[管理対象デバイス]** があらかじめ選択されています。</span><span class="sxs-lookup"><span data-stu-id="de5e9-167">**Managed devices** is pre-selected for you.</span></span>
5. <span data-ttu-id="de5e9-168">**[関連アプリ]** を選択し、構成ポリシーを定義するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-168">Select **Associated App** to choose the app for which you want to define a configuration policy.</span></span> <span data-ttu-id="de5e9-169">承認して Intune に同期した Android for Work アプリの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-169">Select from the list of Android for Work apps that you have approved and synchronized with Intune.</span></span>
6. <span data-ttu-id="de5e9-170">**[アクセス許可]** を選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-170">Select **Permissions** and then choose **Add**.</span></span>
7. <span data-ttu-id="de5e9-171">使用できるアプリのアクセス許可の一覧から選択し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-171">Select from the list of available app permissions and then choose **OK**.</span></span>
8. <span data-ttu-id="de5e9-172">このポリシーに付与するアクセス許可ごとにオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-172">Select an option for each permission to grant with this policy:</span></span>
    - <span data-ttu-id="de5e9-173">**プロンプト**。</span><span class="sxs-lookup"><span data-stu-id="de5e9-173">**Prompt**.</span></span> <span data-ttu-id="de5e9-174">承諾または拒否をユーザーに求める</span><span class="sxs-lookup"><span data-stu-id="de5e9-174">Prompt the user to accept or deny.</span></span>
    - <span data-ttu-id="de5e9-175">**自動許可**。</span><span class="sxs-lookup"><span data-stu-id="de5e9-175">**Auto grant**.</span></span> <span data-ttu-id="de5e9-176">ユーザーに通知することなく自動的に承諾します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-176">Automatically approve without notifying the user.</span></span>
    - <span data-ttu-id="de5e9-177">**自動拒否**。</span><span class="sxs-lookup"><span data-stu-id="de5e9-177">**Auto deny**.</span></span> <span data-ttu-id="de5e9-178">ユーザーに通知することなく自動的に拒否します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-178">Automatically deny without notifying the user.</span></span>
9. <span data-ttu-id="de5e9-179">アプリ構成ポリシーを割り当てるには、アプリ構成ポリシーを選択して、**[割り当て]**、**[グループの選択]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="de5e9-179">To assign the app configuration policy, select the app configuration policy, select **Assignment**, and then select **Select groups**.</span></span>
10. <span data-ttu-id="de5e9-180">割り当てるユーザー グループを選び、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de5e9-180">Select the user groups to assign, and then choose **Select**.</span></span>
11. <span data-ttu-id="de5e9-181">**[保存]** を選択して、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-181">Choose **Save** to assign the policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de5e9-182">次の手順</span><span class="sxs-lookup"><span data-stu-id="de5e9-182">Next steps</span></span>

<span data-ttu-id="de5e9-183">アプリの[割り当て](apps-deploy.md)と[監視](apps-monitor.md)に進みます。</span><span class="sxs-lookup"><span data-stu-id="de5e9-183">Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app.</span></span>

