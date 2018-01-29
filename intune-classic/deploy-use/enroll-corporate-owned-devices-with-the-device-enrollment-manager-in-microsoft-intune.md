---
title: "デバイス登録マネージャーを使用して登録する"
description: "デバイス登録マネージャー (DEM) アカウントでは、1 つのユーザー アカウントで企業所有の多数の共有モバイル デバイスを管理できます。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 161777cfae5bdfa68726cca344ce0d7e24737642
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a><span data-ttu-id="e24c9-103">Microsoft Intune のデバイス登録マネージャーを使用した企業所有デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="e24c9-103">Enroll corporate-owned devices with the device enrollment manager in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e24c9-104">組織は Intune を使用して、単一のユーザー アカウントで多数のモバイル デバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-104">Organizations can use Intune to manage large numbers of mobile devices with a single user account.</span></span> <span data-ttu-id="e24c9-105">*デバイス登録マネージャー (DEM)* アカウントは、最大で 1,000 台のデバイスを登録できる特別なユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="e24c9-105">The *device enrollment manager* (DEM) account is a special user account that can enroll up to 1,000 devices.</span></span> <span data-ttu-id="e24c9-106">既存のユーザーを DEM アカウントに追加し、特別な DEM 機能を与えます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-106">You add existing users to the DEM account to give them the special DEM capabilities.</span></span> <span data-ttu-id="e24c9-107">登録される各デバイスは 1 つのライセンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-107">Each enrolled device uses a single license.</span></span> <span data-ttu-id="e24c9-108">このアカウントで登録したデバイスは、個人用 ("BYOD") デバイスではなく共有デバイス (つまり、ユーザー アフィニティなし) として使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e24c9-108">We recommend that you use devices enrolled through this account as shared devices (that is, with no user affinity) rather than personal ("BYOD") devices.</span></span>  

<span data-ttu-id="e24c9-109">ユーザーをデバイス登録マネージャーとして追加するには、そのユーザーが Azure Portal に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e24c9-109">Users must exist in the Azure portal to be added as device enrollment managers.</span></span> <span data-ttu-id="e24c9-110">最適なセキュリティのために、DEM ユーザーを Intune 管理にも指定することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="e24c9-110">For optimal security, the DEM user should not also be an Intune admin.</span></span>

>[!NOTE]
><span data-ttu-id="e24c9-111">DEM の登録方法は、[Apple Configurator セットアップ アシスタント](ios-setup-assistant-enrollment-in-microsoft-intune.md)、[直接登録](ios-direct-enrollment-in-microsoft-intune.md)、または [DEP の登録方法](ios-device-enrollment-program-in-microsoft-intune.md)と同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-111">The DEM enrollment method can't be used with the [Apple Configurator Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) or [direct enrollment](ios-direct-enrollment-in-microsoft-intune.md), or the [DEP enrollment method](ios-device-enrollment-program-in-microsoft-intune.md).</span></span>

## <a name="example-of-a-device-enrollment-manager-scenario"></a><span data-ttu-id="e24c9-112">デバイス登録マネージャーのシナリオの例</span><span class="sxs-lookup"><span data-stu-id="e24c9-112">Example of a device enrollment manager scenario</span></span>

<span data-ttu-id="e24c9-113">あるレストランで、接客担当スタッフが販売時点管理に使い、調理担当スタッフがオーダーのモニターに使う POS タブレットが 50 台必要になりました。</span><span class="sxs-lookup"><span data-stu-id="e24c9-113">A restaurant wants to provide 50 point-of-sale tablets for its wait staff, and order monitors for its kitchen staff.</span></span> <span data-ttu-id="e24c9-114">従業員は、会社のデータにアクセスしたり、ユーザーとしてサインインしたりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-114">The employees never need to access company data or sign in as users.</span></span> <span data-ttu-id="e24c9-115">Intune 管理者はデバイス登録マネージャー アカウントを作成し、レストランの監督者を DEM アカウントに追加し、DEM の機能を与えます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-115">The Intune admin creates a device enrollment manager account and adds a restaurant supervisor to the DEM account, in effect giving that supervisor DEM capabilities.</span></span> <span data-ttu-id="e24c9-116">これで監督者は DEM の資格情報を利用し、50 台のタブレット デバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-116">The supervisor can now enroll the 50 tablets devices by using the DEM credentials.</span></span>

<span data-ttu-id="e24c9-117">Intune コンソール内のユーザーのみがデバイス登録マネージャーになることができます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-117">Only users in the Intune console can be device enrollment managers.</span></span> <span data-ttu-id="e24c9-118">デバイス登録マネージャーのユーザーを Intune 管理者にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-118">The device enrollment manager user cannot be an Intune admin.</span></span>

<span data-ttu-id="e24c9-119">DEM ユーザーができること:</span><span class="sxs-lookup"><span data-stu-id="e24c9-119">The DEM user can:</span></span>

-   <span data-ttu-id="e24c9-120">Intune に最大 1,000 台のデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="e24c9-120">Enroll up to 1000 devices in Intune</span></span>
-   <span data-ttu-id="e24c9-121">会社のポータル アプリを使用して会社のアプリを取得する</span><span class="sxs-lookup"><span data-stu-id="e24c9-121">Use the Company Portal app to get company apps</span></span>
-   <span data-ttu-id="e24c9-122">タブレットにロール固有のアプリを展開することで、会社データへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="e24c9-122">Configure access to company data by deploying role-specific apps to the tablets</span></span>

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a><span data-ttu-id="e24c9-123">DEM アカウントで登録されるデバイスの制限事項</span><span class="sxs-lookup"><span data-stu-id="e24c9-123">Limitations of devices that are enrolled with a DEM account</span></span>

<span data-ttu-id="e24c9-124">デバイス登録マネージャー アカウントを使用して登録されているデバイスには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="e24c9-124">Devices that are enrolled with a device enrollment manager account have the following limitations:</span></span>

  - <span data-ttu-id="e24c9-125">具体的なデバイス "ユーザー" は存在しません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-125">There is no specific device "user."</span></span> <span data-ttu-id="e24c9-126">そのため、電子メールや会社のデータへのアクセスがありません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-126">Therefore, there is no email or company data access.</span></span> <span data-ttu-id="e24c9-127">ただし、VPN などを使用してデバイス アプリからデータにアクセスすることはできます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-127">However VPN, for example, could still be used to provide device apps with access to data.</span></span>

  - <span data-ttu-id="e24c9-128">シナリオはユーザーごとになるため、条件付きアクセスはありません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-128">There is no conditional access because these are per-user scenarios.</span></span>

  - <span data-ttu-id="e24c9-129">DEM ユーザーは、会社ポータルを使用して、デバイス自体で DEM 登録のデバイスを登録解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-129">The DEM user can't unenroll DEM-enrolled devices on the device itself by using the Company Portal.</span></span> <span data-ttu-id="e24c9-130">Intune 管理者にはこの機能が与えられますが、DEM ユーザーはこの機能を使用できません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-130">The Intune admin has this capability, but the DEM user does not.</span></span>

  - <span data-ttu-id="e24c9-131">ポータル サイト アプリまたは Web サイトには、ローカルのデバイスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-131">Only the local device appears in the Company Portal app or website.</span></span>

  - <span data-ttu-id="e24c9-132">アプリ管理のための Apple ID 要件がユーザー単位になるため、ユーザーは Apple Volume Purchase Program (VPP) アプリを利用できません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-132">Users can't use Apple Volume Purchase Program (VPP) apps because of per-user Apple ID requirements for app management.</span></span>

  - <span data-ttu-id="e24c9-133">(iOS のみ) DEM を利用して iOS デバイスを登録する場合、Apple Configurator またはデバイス登録プログラム (DEP) を利用してデバイスを登録することはできません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-133">(iOS only) If you use DEM to enroll iOS devices, you can't use the Apple Configurator or Apple Device Enrollment Program (DEP) to enroll devices.</span></span>

> [!NOTE]
> <span data-ttu-id="e24c9-134">デバイス登録マネージャーで管理されているデバイスに会社のアプリを展開するには、ポータル サイト アプリを**必須のインストール**としてデバイス登録マネージャーのユーザー アカウントに展開します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-134">To deploy company apps to devices that are managed by the device enrollment manager, deploy the Company Portal app as a **Required Install** to the device enrollment manager's user account.</span></span>
> <span data-ttu-id="e24c9-135">パフォーマンスを改善するために、DEM デバイスでポータル サイト アプリを表示すると、ローカル デバイスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-135">To improve performance, viewing the Company Portal app on a DEM device shows only the local device.</span></span> <span data-ttu-id="e24c9-136">その他の DEM デバイスのリモート管理は、Intune 管理コンソールからのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-136">Remote management of other DEM devices can only be done from the Intune admin console.</span></span>


## <a name="add-a-device-enrollment-manager"></a><span data-ttu-id="e24c9-137">デバイス登録マネージャーの追加</span><span class="sxs-lookup"><span data-stu-id="e24c9-137">Add a device enrollment manager</span></span>

1. <span data-ttu-id="e24c9-138">DEM アカウントに追加するユーザーが既に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-138">Ensure that the user that you want to add to the DEM account already exists.</span></span> <span data-ttu-id="e24c9-139">ユーザーを追加する必要がある場合、[Office 365 ポータル](https://go.microsoft.com/fwlink/p/?LinkId=698854)にサインインし、「[Office 365 にユーザーを個別に、またはまとめて追加する - 管理者向けヘルプ](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-139">If you need to add the user, sign in to the [Office 365 portal](https://go.microsoft.com/fwlink/p/?LinkId=698854), and follow the steps in [Add users individually or in bulk to the Office 365 portal](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

2. <span data-ttu-id="e24c9-140">管理者の資格情報を使用して、[Microsoft Intune 管理コンソール](https://manage.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e24c9-140">Sign in to the [Microsoft Intune administration console](https://manage.microsoft.com) with your admin credentials.</span></span>

3. <span data-ttu-id="e24c9-141">ナビゲーション ウィンドウで、**[管理]**、**[管理者の管理]** の順に選択し、**[デバイス登録マネージャー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-141">In the navigation pane, choose **Admin**, go to **Administrator Management**, and select **Device Enrollment Manager**.</span></span> <span data-ttu-id="e24c9-142">**[デバイス登録マネージャー]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-142">The **Device Enrollment Managers** page opens.</span></span>

4. <span data-ttu-id="e24c9-143">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-143">Choose **Add…**.</span></span> <span data-ttu-id="e24c9-144">**[デバイス登録マネージャーの追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-144">The **Add Device Enrollment Manager** dialog box opens.</span></span>

5. <span data-ttu-id="e24c9-145">Intune アカウントを **[ユーザー ID]** に入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-145">Enter the **User ID** of the Intune account, and then choose **OK**.</span></span>

   <span data-ttu-id="e24c9-146">これで、DEM ユーザーが、BYOD シナリオの場合にエンド ユーザーがポータル サイトで実行する際と同じ手順で、モバイル デバイスを登録できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e24c9-146">The DEM user can now enroll mobile devices by using the same procedure that an end user uses for a BYOD scenario in the Company Portal.</span></span> <span data-ttu-id="e24c9-147">マネージャーであるエンド ユーザーは、ポータル サイト アプリをインストールし、DEM の資格情報を使用して最大 1,000 台のデバイスを登録することができます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-147">The manager end user can install the Company Portal app and enroll the device using her DEM credentials on up to 1000 devices.</span></span> <span data-ttu-id="e24c9-148">プラットフォーム別のエンドユーザー登録手順については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e24c9-148">For the end-user enrollment steps for each platform, see:</span></span>

   - [<span data-ttu-id="e24c9-149">Intune に iOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="e24c9-149">Enroll your iOS device in Intune</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)
   - [<span data-ttu-id="e24c9-150">Intune に macOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="e24c9-150">Enroll your macOS device in Intune</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)
   - [<span data-ttu-id="e24c9-151">Intune に Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="e24c9-151">Enroll your Android device in Intune</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)
   - [<span data-ttu-id="e24c9-152">Intune に Windows デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="e24c9-152">Enroll your Windows device in Intune</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)

## <a name="delete-a-device-enrollment-manager-from-intune"></a><span data-ttu-id="e24c9-153">Intune からのデバイス登録マネージャーの削除</span><span class="sxs-lookup"><span data-stu-id="e24c9-153">Delete a device enrollment manager from Intune</span></span>

1.  <span data-ttu-id="e24c9-154">管理者の資格情報を使用して、[Microsoft Intune 管理ポータル](https://manage.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e24c9-154">Sign in to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials.</span></span>

2.  <span data-ttu-id="e24c9-155">ナビゲーション ウィンドウで、**[管理]**、**[管理者の管理]** の順に選択し、**[デバイス登録マネージャー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-155">In the navigation pane, choose **Admin**, go to **Administrator Management**, and select **Device Enrollment Manager**.</span></span> <span data-ttu-id="e24c9-156">**[デバイス登録マネージャー]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-156">The **Device Enrollment Managers** page opens.</span></span>

3.  <span data-ttu-id="e24c9-157">削除するデバイス登録マネージャーの **[ユーザー]** を選択し、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-157">Select the device enrollment manager **User** that you want to delete, and then choose **Delete**.</span></span> <span data-ttu-id="e24c9-158">このユーザーは Intune から削除されません。このユーザーが管理するデバイスは Intune で登録されたままになります。</span><span class="sxs-lookup"><span data-stu-id="e24c9-158">This user won’t be deleted from Intune, and the devices this user manages will remain enrolled in Intune.</span></span> <span data-ttu-id="e24c9-159">デバイス登録マネージャーを削除することにより、Intune でユーザーがデバイスをそれ以上追加できないようにします。</span><span class="sxs-lookup"><span data-stu-id="e24c9-159">Deleting a device enrollment manager prevents that user from enrolling more devices in Intune.</span></span>

4.  <span data-ttu-id="e24c9-160">**[はい]** を選択して、デバイス登録マネージャーを削除することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e24c9-160">Choose **Yes** to confirm that you want to delete the device enrollment manager.</span></span>

<span data-ttu-id="e24c9-161">デバイス登録マネージャーを削除していも、登録済みのデバイスに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-161">Deleting a device enrollment manager does not affect enrolled devices.</span></span> <span data-ttu-id="e24c9-162">デバイス登録マネージャーを削除した場合:</span><span class="sxs-lookup"><span data-stu-id="e24c9-162">When a device enrollment manager is deleted:</span></span>

-   <span data-ttu-id="e24c9-163">登録済みデバイスに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-163">No enrolled devices are affected.</span></span>

-   <span data-ttu-id="e24c9-164">登録済みデバイスは引き続き完全に管理されます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-164">Enrolled devices continue to be fully managed.</span></span>

-   <span data-ttu-id="e24c9-165">削除されたデバイス登録マネージャー アカウントの資格情報は有効なままなので、ポータル サイトにサインインしてアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e24c9-165">The deleted device enrollment manager account credentials remain valid to sign in to the Company Portal to access apps.</span></span>

-   <span data-ttu-id="e24c9-166">削除されたデバイス登録マネージャー アカウントの資格情報では、デバイスのワイプとインベントリからの削除を実行できません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-166">The deleted device enrollment manager account credentials still cannot wipe or retire devices.</span></span>

-   <span data-ttu-id="e24c9-167">削除されたデバイス登録マネージャー アカウントと登録済みデバイスの関係は残りますが、追加のデバイスは登録できません。</span><span class="sxs-lookup"><span data-stu-id="e24c9-167">The deleted device enrollment manager account’s relationship to enrolled devices remains, but no additional devices can be enrolled.</span></span>
