---
title: "登録されていないデバイスで LOB アプリを保護する"
description: "このトピックでは、データの損失を防ぐことができるモバイル アプリケーション管理ポリシーを適用できるように、カスタム基幹業務アプリを準備する方法について説明します。"
keywords: 
author: mattbriggs
ms.author: mabriggs
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0fbc7ae1937aff60e8e494df06ee2c30e2fe8855
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="protect-line-of-business-apps-and-data-on-devices-that-are-not-enrolled-in-microsoft-intune"></a><span data-ttu-id="e6fef-103">Microsoft Intune に登録されていないデバイスの基幹業務アプリとデータを保護する</span><span class="sxs-lookup"><span data-stu-id="e6fef-103">Protect line-of-business apps and data on devices that are not enrolled in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e6fef-104">モバイル アプリケーション管理 (MAM) ポリシーでは、会社のデータを保護するために、会社データが漏洩する可能性があるアクションを制限し、アプリ PIN などのデータ アクセス要件を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-104">Mobile application management (MAM) policies help protect company data by restricting actions that could leak company data and by enforcing data access requirements, such as an app PIN.</span></span> <span data-ttu-id="e6fef-105">MAM ポリシーを iOS または Android の基幹業務アプリに適用するには、最初に Microsoft Intune アプリ ラッピング ツールを使用してアプリをラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6fef-105">To apply MAM policies to iOS and Android line-of-business apps, you must first wrap the app with the Microsoft Intune App Wrapping Tool.</span></span> <span data-ttu-id="e6fef-106">アプリ ラッピングは、モバイル アプリを何も変更することなく管理レイヤーを適用するプロセスで、モバイル アプリはユーザーに配布されます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-106">App wrapping is the process of applying a management layer to a mobile app without requiring any changes to it and distribute it to your users.</span></span>  

<span data-ttu-id="e6fef-107">このトピックでは、**従業員が所有している管理外のデバイス**からアクセスするアプリと、**サード パーティ製のモバイル デバイス管理 (MDM) ソリューション**で管理されているデバイスに MAM ポリシーを適用する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-107">This topic explains the steps that are required to apply MAM policies for apps that users access on **employee-owned devices that are not managed** and devices that are managed by a **third-party mobile device management (MDM) solution**.</span></span>  <span data-ttu-id="e6fef-108">**Intune MDM に登録されているデバイス**で実行されている基幹業務アプリを準備するには、「[Microsoft Intune によるモバイル アプリケーション管理のためにアプリを準備する方法を決める](/intune/apps-prepare-mobile-application-management)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e6fef-108">To prepare your line-of-business apps that run on **devices that are enrolled in Intune MDM**, see [Decide how to prepare apps for mobile application management with Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span></span>


##  <a name="step-1-prepare-the-app"></a><span data-ttu-id="e6fef-109">手順 1: アプリを準備する</span><span class="sxs-lookup"><span data-stu-id="e6fef-109">Step 1: Prepare the app</span></span>

<span data-ttu-id="e6fef-110">MAM ポリシーをアプリに適用する前に、まず Microsoft Intune アプリ ラッピング ツール ([iOS](/intune/app-wrapper-prepare-ios) 用、[Android](/intune/app-wrapper-prepare-android) 用) を使用してアプリをラップする必要があります。あるいは、[Intune アプリ SDK](/intune/app-sdk) を利用し、Intune アプリ保護機能を手動で統合します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-110">Before you can apply MAM policies to an app, you must first wrap the app by using the Microsoft Intune App Wrapping Tool for [iOS](/intune/app-wrapper-prepare-ios), [Android](/intune/app-wrapper-prepare-android), or use the [Intune App SDK](/intune/app-sdk) to manually integrate Intune app protection features.</span></span>

<span data-ttu-id="e6fef-111">アプリ ラッピング ツールと SDK の比較については、「[Microsoft Intune によるモバイル アプリケーション管理のためにアプリを準備する方法を決める](/intune/apps-prepare-mobile-application-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6fef-111">For more information on using the App Wrapping Tool vs. the SDK, see [Decide how to prepare apps for mobile application management with Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span></span>

## <a name="step-2-add-the-app"></a><span data-ttu-id="e6fef-112">手順 2: アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="e6fef-112">Step 2: Add the app</span></span>

<span data-ttu-id="e6fef-113">MAM ポリシーと基幹業務アプリを関連付けるには、次の手順を使用して Intune のサブスクリプションとテナントにアプリの詳細を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6fef-113">To associate your line-of-business app with MAM policies, you must add the app details to your Intune subscription/tenant by using the following steps:</span></span>

1. <span data-ttu-id="e6fef-114">[Azure Portal](https://portal.azure.com/) で **[Intune モバイル アプリケーション管理]**、**[設定]** に進み、**[基幹業務アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-114">In the [Azure portal](https://portal.azure.com/), go to **Intune mobile application management** > **Settings**, and choose **Line-of-business apps**.</span></span>

   ![基幹業務オプションを示す [設定] ブレードのスクリーン ショット](../media/mam-azure-portal-lob-on-settings.png)

2. <span data-ttu-id="e6fef-116">**[基幹業務アプリ]** ブレードで、**[カスタム アプリの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-116">On the **Line-of-business-apps** blade, choose **Add a custom app**.</span></span>

   ![[カスタム アプリの追加] ボタンが上部に示された [基幹業務アプリ] ブレードのスクリーンショット](../media/mam-azure-portal-add-lob-app-action.png)
3. <span data-ttu-id="e6fef-118">アプリの名前、[アプリ ID] フィールドにバンドル ID、プラットフォーム (iOS または Android) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-118">Provide a name for the app, the bundle identifier in the App Identifier field, and the platform (iOS or Android).</span></span>

   ![[カスタム アプリの追加] ブレードのスクリーン ショット](../media/mam-azure-portal-add-app-details.png)

   <span data-ttu-id="e6fef-120">この手順で、アプリは一意のものとして一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-120">This step helps create a unique listing of your app.</span></span> <span data-ttu-id="e6fef-121">アプリは、次の手順で説明するように、テナントの MAM ポリシーの対象アプリの一覧にも表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="e6fef-121">The app will also be displayed in the list of Targeted apps for a MAM policy for your tenant, as described in the next step.</span></span>

## <a name="step-3-apply-mam-policies"></a><span data-ttu-id="e6fef-122">手順 3: MAM ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="e6fef-122">Step 3: Apply MAM policies</span></span>
<span data-ttu-id="e6fef-123">サービスにアプリのメタデータがアップロードされると、アプリはアプリ一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-123">After the app metadata is uploaded to the service, the app shows up in the list of apps.</span></span> <span data-ttu-id="e6fef-124">[新しいポリシーまたは既存のポリシーを作成し](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)、手順 2. で追加した基幹業務アプリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-124">You can now [create a new policy or use an existing policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md), and apply it to the line-of-business app that you added in step 2.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e6fef-125">ラップされたアプリを使用するユーザーに対して、MAM ポリシーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6fef-125">You must target the MAM policy to the users who are going to use the wrapped app.</span></span>  <span data-ttu-id="e6fef-126">このポリシーを展開されていないユーザーは、アプリを使用できません。</span><span class="sxs-lookup"><span data-stu-id="e6fef-126">Users who don’t have this policy deployed to them won't be able to use the app.</span></span>


  ![新しい基幹業務アプリが示された [対象アプリ] 一覧が示されたブレードのスクリーンショット](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a><span data-ttu-id="e6fef-128">手順 4: アプリを配布する</span><span class="sxs-lookup"><span data-stu-id="e6fef-128">Step 4: Distribute the app</span></span>
<span data-ttu-id="e6fef-129">アプリはユーザーに、次の方法で配布できます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-129">You can deploy apps to your users in the following ways:</span></span>
* <span data-ttu-id="e6fef-130">デバイスがサード パーティ製の MDM ソリューションに登録されている場合、MDM ソリューションを介してアプリを配布できます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-130">For devices that are enrolled in a third-party MDM solution, you can distribute the apps through your MDM solution.</span></span>
* <span data-ttu-id="e6fef-131">デバイスが MDM ソリューションで管理されていない場合には、カスタム ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e6fef-131">For devices that aren't managed by any MDM solution, you need a custom solution.</span></span> <span data-ttu-id="e6fef-132">ユーザーは自分のデバイスにアプリをダウンロードしてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6fef-132">Users must download and install the app on their device.</span></span>

## <a name="change-the-metadata"></a><span data-ttu-id="e6fef-133">メタデータを変更する</span><span class="sxs-lookup"><span data-stu-id="e6fef-133">Change the metadata</span></span>
<span data-ttu-id="e6fef-134">アプリ名、バンドル ID などのアプリの詳細を変更する必要がある場合、[アプリを削除し](#remove-apps)、それに新しいメタデータを[追加](#step-2-add-the-app)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6fef-134">If you need to change the app details, like the name of the app or the bundle identifier, you must [remove the app](#remove-apps) and [add it](#step-2-add-the-app) with the new metadata.</span></span>

##  <a name="remove-apps"></a><span data-ttu-id="e6fef-135">アプリを削除する</span><span class="sxs-lookup"><span data-stu-id="e6fef-135">Remove apps</span></span>
<span data-ttu-id="e6fef-136">アプリの一覧から基幹業務アプリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-136">You can remove a line-of-business app from the app list.</span></span> <span data-ttu-id="e6fef-137">これを行うと、アプリは一覧から削除され、MAM ポリシーとの関連付けが削除されますが、ユーザーのデバイスからアプリが削除されたり、アンインストールされたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="e6fef-137">This will remove the app from the list and will remove the association with MAM policies, but will not remove or uninstall the app from the user’s device.</span></span>  

1. <span data-ttu-id="e6fef-138">[Azure Portal](https://portal.azure.com/) の **[Intune モバイル アプリケーション管理]**、**[設定]** に進みます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-138">In the [Azure portal](https://portal.azure.com/), go to **Intune mobile app management** > **Settings**.</span></span> <span data-ttu-id="e6fef-139">**[設定]** ブレードで、**[基幹業務]** を選択し、既存のアプリの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-139">On the **Settings** blade, choose **Line-of-business** to open the list of existing apps.</span></span>  
2. <span data-ttu-id="e6fef-140">削除するアプリを選択し、**(...) のコンテキスト** メニューを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-140">Choose the app that you want to remove, and choose the **(…) context** menu.</span></span>

   ![省略記号がある基幹業務アプリのブレードのスクリーンショット](../media/mam-azure-portal-lob-context-menu.png)
3. <span data-ttu-id="e6fef-142">**[アプリケーションの削除]** を選択しアプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="e6fef-142">Choose **Delete Application** to delete the app.</span></span>

   ![[アプリケーションの削除] オプションがある基幹業務ブレードのスクリーンショット](../media/mam-azure-portal-delete-app.png)

   <span data-ttu-id="e6fef-144">これによって、基幹業務アプリの一覧と MAM ポリシーの対象アプリ一覧からアプリは削除されます。</span><span class="sxs-lookup"><span data-stu-id="e6fef-144">This will remove apps from the list of line-of-business apps and the Targeted list of apps in the MAM policy.</span></span>
