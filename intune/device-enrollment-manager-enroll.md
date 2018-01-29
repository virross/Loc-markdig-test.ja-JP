---
title: "デバイスの登録 - デバイス登録マネージャー"
titlesuffix: Azure portal
description: "デバイス登録マネージャー アカウントを使用してデバイスを Intune に登録します。 \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 12f3f1141a504a8f26c870eae01e6cf09f23375c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="enroll-devices-using-device-enrollment-manager"></a><span data-ttu-id="08506-104">デバイス登録マネージャーを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="08506-104">Enroll devices using device enrollment manager</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="08506-105">組織は Intune を使用して、単一のユーザー アカウントで多数のモバイル デバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="08506-105">Organizations can use Intune to manage large numbers of mobile devices with a single user account.</span></span> <span data-ttu-id="08506-106">*デバイス登録マネージャー (DEM)* アカウントは、最大で 1,000 台のデバイスを登録できる特別なユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="08506-106">The *device enrollment manager* (DEM) account is a special user account that can enroll up to 1,000 devices.</span></span> <span data-ttu-id="08506-107">既存のユーザーを DEM アカウントに追加し、特別な DEM 機能を与えます。</span><span class="sxs-lookup"><span data-stu-id="08506-107">You add existing users to the DEM account to give them the special DEM capabilities.</span></span> <span data-ttu-id="08506-108">登録される各デバイスは 1 つのライセンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="08506-108">Each enrolled device uses a single license.</span></span> <span data-ttu-id="08506-109">このアカウントで登録したデバイスは、個人用 ("BYOD") デバイスではなく共有デバイスとして使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="08506-109">We recommend that you use devices enrolled through this account as shared devices rather than personal ("BYOD") devices.</span></span>  

<span data-ttu-id="08506-110">ユーザーをデバイス登録マネージャーとして追加するには、そのユーザーが Azure Portal に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08506-110">Users must exist in the Azure portal to be added as device enrollment managers.</span></span> <span data-ttu-id="08506-111">最適なセキュリティのために、DEM ユーザーを Intune 管理にも指定することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="08506-111">For optimal security, the DEM user should not also be an Intune admin.</span></span>

>[!NOTE]
><span data-ttu-id="08506-112">DEM による登録方法は、[Apple Configurator とセットアップ アシスタント](apple-configurator-setup-assistant-enroll-ios.md)、[Apple Configurator と直接登録](apple-configurator-direct-enroll-ios.md)、[Apple School Manager (ASM)](apple-school-manager-set-up-ios.md)、または [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) という他の登録方法と一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="08506-112">The DEM enrollment method can't be used with these other enrollment methods: [Apple Configurator with Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator with direct enrollment](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md), or [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md).</span></span>

## <a name="example-of-a-device-enrollment-manager-scenario"></a><span data-ttu-id="08506-113">デバイス登録マネージャーのシナリオの例</span><span class="sxs-lookup"><span data-stu-id="08506-113">Example of a device enrollment manager scenario</span></span>

<span data-ttu-id="08506-114">あるレストランで、接客担当スタッフが販売時点管理に使い、調理担当スタッフがオーダーのモニターに使う POS タブレットが 50 台必要になりました。</span><span class="sxs-lookup"><span data-stu-id="08506-114">A restaurant wants to provide 50 point-of-sale tablets for its wait staff, and order monitors for its kitchen staff.</span></span> <span data-ttu-id="08506-115">従業員は、会社のデータにアクセスしたり、ユーザーとしてサインインしたりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="08506-115">The employees never need to access company data or sign in as users.</span></span> <span data-ttu-id="08506-116">Intune 管理者はデバイス登録マネージャー アカウントを作成し、レストランの監督者を DEM アカウントに追加し、DEM の機能を与えます。</span><span class="sxs-lookup"><span data-stu-id="08506-116">The Intune admin creates a device enrollment manager account and adds a restaurant supervisor to the DEM account, in effect giving that supervisor DEM capabilities.</span></span> <span data-ttu-id="08506-117">これで監督者は DEM の資格情報を利用し、50 台のタブレット デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="08506-117">The supervisor can now enroll the 50 tablets devices by using the DEM credentials.</span></span>

<span data-ttu-id="08506-118">Azure Portal 内のユーザーのみがデバイス登録マネージャーになることができます。</span><span class="sxs-lookup"><span data-stu-id="08506-118">Only users in the Azure portal can be device enrollment managers.</span></span> <span data-ttu-id="08506-119">デバイス登録マネージャーのユーザーを Intune 管理者にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="08506-119">The device enrollment manager user cannot be an Intune admin.</span></span>

<span data-ttu-id="08506-120">DEM ユーザーができること:</span><span class="sxs-lookup"><span data-stu-id="08506-120">The DEM user can:</span></span>

-   <span data-ttu-id="08506-121">Intune に最大 1,000 台のデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="08506-121">Enroll up to 1000 devices in Intune</span></span>
-   <span data-ttu-id="08506-122">ポータル サイトにサインインして会社のアプリを取得する</span><span class="sxs-lookup"><span data-stu-id="08506-122">Sign in to the Company Portal to get company apps</span></span>
-   <span data-ttu-id="08506-123">タブレットにロール固有のアプリを展開することで、会社データへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="08506-123">Configure access to company data by deploying role-specific apps to the tablets</span></span>

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a><span data-ttu-id="08506-124">DEM アカウントで登録されるデバイスの制限事項</span><span class="sxs-lookup"><span data-stu-id="08506-124">Limitations of devices that are enrolled with a DEM account</span></span>

<span data-ttu-id="08506-125">デバイス登録マネージャー アカウントを使用して登録されているデバイスには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="08506-125">Devices that are enrolled with a device enrollment manager account have the following limitations:</span></span>

  - <span data-ttu-id="08506-126">ユーザーごとのアクセスはできません。</span><span class="sxs-lookup"><span data-stu-id="08506-126">No per-user access.</span></span> <span data-ttu-id="08506-127">デバイスには割り当てられたユーザーがないため、電子メールや会社のデータ アクセスがありません。</span><span class="sxs-lookup"><span data-stu-id="08506-127">Because devices don't have an assigned user, the device has no email or company data access.</span></span> <span data-ttu-id="08506-128">VPN 構成などを使用すれば、デバイス アプリがデータにアクセスすることはできます。</span><span class="sxs-lookup"><span data-stu-id="08506-128">VPN configurations, for example, could still be used to provide device apps with access to data.</span></span>
  - <span data-ttu-id="08506-129">これらのシナリオはユーザーごとであるため、条件付きのアクセスはできません。</span><span class="sxs-lookup"><span data-stu-id="08506-129">No conditional access because these scenarios are per-user.</span></span>
  - <span data-ttu-id="08506-130">DEM ユーザーは、会社ポータルを使用して、デバイス自体で DEM 登録のデバイスを登録解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="08506-130">The DEM user can't unenroll DEM-enrolled devices on the device itself by using the Company Portal.</span></span> <span data-ttu-id="08506-131">Intune 管理者はこれができますが、DEM ユーザーはできません。</span><span class="sxs-lookup"><span data-stu-id="08506-131">The Intune admin can do this, but the DEM user does not.</span></span>
  - <span data-ttu-id="08506-132">ポータル サイト アプリまたは Web サイトには、ローカルのデバイスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08506-132">Only the local device appears in the Company Portal app or website.</span></span>
  - <span data-ttu-id="08506-133">アプリ管理のための Apple ID 要件がユーザー単位になるため、ユーザーは Apple Volume Purchase Program (VPP) アプリを利用できません。</span><span class="sxs-lookup"><span data-stu-id="08506-133">Users can't use Apple Volume Purchase Program (VPP) apps because of per-user Apple ID requirements for app management.</span></span>
  - <span data-ttu-id="08506-134">(iOS のみ) DEM を利用して iOS デバイスを登録する場合は、Apple Configurator、Apple Device Enrollment Program (DEP)、または Apple School Manager (ASM) を利用してデバイスを登録することはできません。</span><span class="sxs-lookup"><span data-stu-id="08506-134">(iOS only) If you use DEM to enroll iOS devices, you can't use the Apple Configurator, Apple Device Enrollment Program (DEP), or Apple School Manager (ASM) to enroll devices.</span></span>
  - <span data-ttu-id="08506-135">(Android のみ) 1 つの DEM アカウントに登録できる Android for Work デバイスの数は限られています。</span><span class="sxs-lookup"><span data-stu-id="08506-135">(Android only) There is a limit to the amount of Android for Work devices that can be enrolled with a single DEM account.</span></span> <span data-ttu-id="08506-136">DEM アカウントごとに最大 10 台の Android の仕事用プロファイル デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="08506-136">A maximum of ten Android work profile devices may be enrolled per DEM account.</span></span> <span data-ttu-id="08506-137">この制限は、従来の Android の登録には適用されません。</span><span class="sxs-lookup"><span data-stu-id="08506-137">This limitation does not apply to legacy Android enrollment.</span></span>
  - <span data-ttu-id="08506-138">各デバイスには、デバイスのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="08506-138">Each device requires a device license.</span></span> <span data-ttu-id="08506-139">[ユーザーとデバイスのライセンス](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services)の詳細についてはこちらです。</span><span class="sxs-lookup"><span data-stu-id="08506-139">Learn more about [user and device licenses](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).</span></span>


> [!NOTE]
> <span data-ttu-id="08506-140">デバイス登録マネージャーで管理されているデバイスに会社のアプリを展開するには、ポータル サイト アプリを**必須のインストール**としてデバイス登録マネージャーのユーザー アカウントに展開します。</span><span class="sxs-lookup"><span data-stu-id="08506-140">To deploy company apps to devices that are managed by the device enrollment manager, deploy the Company Portal app as a **Required Install** to the device enrollment manager's user account.</span></span>
> <span data-ttu-id="08506-141">パフォーマンスを改善するために、DEM デバイスでポータル サイト アプリを表示すると、ローカル デバイスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08506-141">To improve performance, viewing the Company Portal app on a DEM device shows only the local device.</span></span> <span data-ttu-id="08506-142">その他の DEM デバイスのリモート管理は、Intune 管理コンソールからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="08506-142">Remote management of other DEM devices can only be done from the Intune admin console.</span></span>


## <a name="add-a-device-enrollment-manager"></a><span data-ttu-id="08506-143">デバイス登録マネージャーの追加</span><span class="sxs-lookup"><span data-stu-id="08506-143">Add a device enrollment manager</span></span>

1.  <span data-ttu-id="08506-144">Azure Portal で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08506-144">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2.  <span data-ttu-id="08506-145">[Intune] ブレードで **[デバイスの登録]** を選択し、**[デバイス登録マネージャー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08506-145">On the Intune blade, choose **Enroll devices**, and then choose **Device Enrollment Managers**.</span></span>

3.  <span data-ttu-id="08506-146">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08506-146">Select **Add**.</span></span>

4.  <span data-ttu-id="08506-147">**[ユーザーの追加]** ブレードで、DEM ユーザーのユーザー プリンシパル名を入力し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08506-147">On the **Add User** blade, enter a user principal name for the DEM user, and select **Add**.</span></span> <span data-ttu-id="08506-148">DEM ユーザーが DEM ユーザーの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="08506-148">The DEM user is added to the list of DEM users.</span></span>

## <a name="permissions-for-dem"></a><span data-ttu-id="08506-149">DEM のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="08506-149">Permissions for DEM</span></span>

<span data-ttu-id="08506-150">DEM 登録タスクを実行するには、グローバル管理者または Intune サービス管理者の Azure AD ロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="08506-150">Global or Intune Service Administrator Azure AD roles are required to perform DEM enrollment tasks.</span></span> <span data-ttu-id="08506-151">また、これらのロールは、カスタムのユーザー ロールに一覧表示され使用可能である RBAC のアクセス許可に関係なく、すべての DEM ユーザーを表示するのに必要です。</span><span class="sxs-lookup"><span data-stu-id="08506-151">These roles are also required to see all DEM users despite RBAC permissions being listed and available under the custom User role.</span></span> <span data-ttu-id="08506-152">グローバル管理者または Intune サービス管理者のロールが割り当てられていないユーザーで、デバイス登録マネージャー ロールの読み取りアクセス許可を持つユーザーは、自分が作成した DEM ユーザーのみ表示できます。</span><span class="sxs-lookup"><span data-stu-id="08506-152">A user without Global administrator or Intune Service administrator role assigned, but who has read permissions for the Device Enrollment Managers role, can only see the DEM users they created.</span></span> <span data-ttu-id="08506-153">これらの機能の RBAC ロールのサポートについては、今後発表される予定です。</span><span class="sxs-lookup"><span data-stu-id="08506-153">RBAC role support for these features will be announced in the future.</span></span>

<span data-ttu-id="08506-154">ユーザーにグローバル管理者または Intune サービス管理者のロールが割り当てられていないが、デバイス登録マネージャー ロールが割り当てられていてその読み取りアクセス許可を持っているという場合は、そのユーザー自身が作成した DEM ユーザーのみ表示できます。</span><span class="sxs-lookup"><span data-stu-id="08506-154">If a user does not have Global administrator or Intune Service administrator role assigned to them but has read permissions enabled for the Device Enrollment Managers role assigned to them, they’ll only be able to see the DEM users they have created.</span></span>

## <a name="remove-a-device-enrollment-manager"></a><span data-ttu-id="08506-155">デバイス登録マネージャーの削除</span><span class="sxs-lookup"><span data-stu-id="08506-155">Remove a device enrollment manager</span></span>

<span data-ttu-id="08506-156">デバイス登録マネージャーを削除しても、登録済みのデバイスに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="08506-156">Removing a device enrollment manager does not affect enrolled devices.</span></span> <span data-ttu-id="08506-157">デバイス登録マネージャーを削除した場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="08506-157">When a device enrollment manager is removed:</span></span>

-   <span data-ttu-id="08506-158">登録済みデバイスは影響を受けず、引き続き完全に管理されます。</span><span class="sxs-lookup"><span data-stu-id="08506-158">Enrolled devices are unaffected and continue to be fully managed.</span></span>
-   <span data-ttu-id="08506-159">削除されたデバイス登録マネージャー アカウントの資格情報は有効なままです。</span><span class="sxs-lookup"><span data-stu-id="08506-159">The removed device enrollment manager account credentials remain valid.</span></span>
-   <span data-ttu-id="08506-160">削除されたデバイス登録マネージャーでは、デバイスのワイプとインベントリからの削除を実行できません。</span><span class="sxs-lookup"><span data-stu-id="08506-160">The removed device enrollment manager still cannot wipe or retire devices.</span></span>
-   <span data-ttu-id="08506-161">削除されたデバイス登録マネージャーは、Intune 管理者によって構成されたデバイスを、ユーザーあたりの上限数まで登録することのみできます。</span><span class="sxs-lookup"><span data-stu-id="08506-161">The removed device enrollment manager can only enroll a number of devices up to the per-user limit configured by the Intune admin.</span></span>

<span data-ttu-id="08506-162">**デバイス登録マネージャーを削除するには**</span><span class="sxs-lookup"><span data-stu-id="08506-162">**To remove a device enrollment manager**</span></span>

1. <span data-ttu-id="08506-163">Azure Portal で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="08506-163">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="08506-164">[Intune] ブレードで **[デバイスの登録]** を選択し、**[デバイス登録マネージャー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08506-164">On the Intune blade, choose **Enroll devices**, and then choose **Device Enrollment Managers**.</span></span>
3. <span data-ttu-id="08506-165">**[デバイス登録マネージャー]** ブレードで、DEM ユーザーを右クリックし、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08506-165">On the **Device Enrollment Managers** blade, right-click the DEM user, and select **Remove**.</span></span>

## <a name="view-the-properties-of-a-device-enrollment-manager"></a><span data-ttu-id="08506-166">デバイス登録マネージャーのプロパティの表示</span><span class="sxs-lookup"><span data-stu-id="08506-166">View the properties of a device enrollment manager</span></span>

1. <span data-ttu-id="08506-167">Azure Portal で **[デバイスの登録]**、**[デバイス登録マネージャー]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="08506-167">In the Azure portal, choose **Device enrollment**, and then choose **Device Enrollment Managers**.</span></span>
2. <span data-ttu-id="08506-168">**[デバイス登録マネージャー]** ブレードで、DEM ユーザーを右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="08506-168">On the **Device Enrollment Managers** blade, right-click the DEM user, and select **Properties**.</span></span>
