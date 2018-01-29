---
title: "セットアップ アシスタントを使用した iOS デバイスの登録"
description: "Apple Configurator ツールを使用して企業所有の iOS デバイスを登録し、デバイスを工場出荷時の設定にリセットして、セットアップ アシスタントを実行する準備をします。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6b9033007df1418900ebf77d87e30478ad5393cf
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a><span data-ttu-id="4bed3-103">Apple Configurator でセットアップ アシスタントを使用して iOS デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="4bed3-103">Enroll iOS devices with Apple Configurator by using Setup Assistant</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4bed3-104">Intune は、Mac コンピューターで実行される [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) を使用した、会社所有の iOS デバイスの登録をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4bed3-104">Intune supports the enrollment of corporate-owned iOS devices using [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) running on a Mac computer.</span></span> <span data-ttu-id="4bed3-105">このプロセスではデバイスを工場出荷時の設定にリセットし、セットアップ アシスタントを実行してデバイスの新しいユーザー用に会社のポリシーをインストールするための準備を行います。</span><span class="sxs-lookup"><span data-stu-id="4bed3-105">This process resets the device to factory settings and prepares it to run Setup Assistant, installing the company's policies for the device’s new user.</span></span>

>[!NOTE]
><span data-ttu-id="4bed3-106">この登録方法は、[デバイス登録マネージャー](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)の方法と同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4bed3-106">This enrollment method can't be used with the [device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) method.</span></span>

<span data-ttu-id="4bed3-107">Apple Configurator を使用して、iOS デバイスを工場出荷時の設定にリセットし、デバイスの新しいユーザー用にセットアップするための準備を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-107">Using Apple Configurator, you can reset an iOS device to factory settings and prepare it to be set up for the device’s new user.</span></span> <span data-ttu-id="4bed3-108">この方法では、USB を使用して iOS デバイスを Mac コンピューターに接続し、会社の登録をセットアップする必要があります。この方法では、Apple Configurator 2.0 の使用を想定しています。</span><span class="sxs-lookup"><span data-stu-id="4bed3-108">This method requires you to connect the iOS device to a Mac computer via USB to set up corporate enrollment, and it assumes you are using Apple Configurator 2.0.</span></span> <span data-ttu-id="4bed3-109">ほとんどのシナリオでは、Intune ポータル サイト アプリを有効にするため、iOS デバイスに適用されるポリシーに**ユーザー アフィニティ**が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-109">Most scenarios require that the policy applied to the iOS device include **user affinity** to enable the Intune Company Portal app.</span></span>

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-configurator-with-setup-assistant"></a><span data-ttu-id="4bed3-110">Apple Configurator とセットアップ アシスタント使用して iOS デバイスを登録する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="4bed3-110">Prerequisites for enrolling iOS devices by using Apple Configurator with Setup Assistant</span></span>

- [<span data-ttu-id="4bed3-111">APNs 証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="4bed3-111">Install an APNs certificate</span></span>](set-up-ios-and-mac-management-with-microsoft-intune.md)

- <span data-ttu-id="4bed3-112">iOS デバイスに物理的にアクセスできることを確認する &mdash; デバイスを、パスワードで保護されていない工場出荷時の設定にリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-112">Ensure that you have physical access to iOS devices&mdash;devices must be reset to factory settings without password protection</span></span>

- <span data-ttu-id="4bed3-113">デバイスのシリアル番号を取得する &mdash; [iOS シリアル番号を取得する方法](https://support.apple.com/HT204308)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bed3-113">Get device serial numbers&mdash;see [How to get an iOS serial number](https://support.apple.com/HT204308)</span></span>

- <span data-ttu-id="4bed3-114">USB 接続ケーブルを手元に置いておく。</span><span class="sxs-lookup"><span data-stu-id="4bed3-114">Have USB connection cables on hand</span></span>

- <span data-ttu-id="4bed3-115">[Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) がインストールされている Mac コンピューターを用意する。</span><span class="sxs-lookup"><span data-stu-id="4bed3-115">Have a Mac computer with [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)</span></span>


## <a name="steps-to-enroll-ios-devices-by-using-apple-configurator-with-setup-assistant"></a><span data-ttu-id="4bed3-116">Apple Configurator とセットアップ アシスタント使用して iOS デバイスを登録する手順</span><span class="sxs-lookup"><span data-stu-id="4bed3-116">Steps to enroll iOS devices by using Apple Configurator with Setup Assistant</span></span>

<span data-ttu-id="4bed3-117">次の手順では、Apple Configurator とセットアップ アシスタントを使用して iOS デバイスを登録するための準備方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-117">The following steps explain how to enroll iOS devices on "day 0" by using Apple Configurator with Setup Assistant.</span></span> <span data-ttu-id="4bed3-118">組織でデバイスが追加および削除された場合、以下に示すように、シリアル番号の追加や削除など、いくつかの手順を繰り返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-118">As devices are added and removed from your organization, you will likely repeat some of these steps, such as adding or removing serial numbers, as described below.</span></span>

### <a name="create-mobile-device-groups-optional"></a><span data-ttu-id="4bed3-119">モバイル デバイス グループを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="4bed3-119">Create mobile device groups (optional)</span></span>

<span data-ttu-id="4bed3-120">企業でデバイスの管理を容易にするためにモバイル デバイス グループが必要な場合は、必要に応じてこれらのグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-120">If your business requires mobile device groups to help manage devices, you can optionally create those groups.</span></span> <span data-ttu-id="4bed3-121">詳細については、「[Microsoft Intune でユーザーとデバイスの管理にグループを使用する](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bed3-121">To learn more, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span></span>

### <a name="create-a-profile-for-devices"></a><span data-ttu-id="4bed3-122">デバイスのプロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4bed3-122">Create a profile for devices</span></span>

<span data-ttu-id="4bed3-123">デバイス登録プロファイルで、デバイスのグループに適用する設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-123">A device enrollment profile defines the settings applied to a group of devices.</span></span>

1. <span data-ttu-id="4bed3-124">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[業務用デバイスの登録]** の順に選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-124">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Policy** &gt; **Corporate Device Enrollment**, and then choose **Add**.</span></span>

   ![デバイス登録プロファイルの作成](../media/pol-sa-corp-enroll.png)

2. <span data-ttu-id="4bed3-126">デバイス プロファイルの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-126">Enter details for the device profiles:</span></span>

   -   <span data-ttu-id="4bed3-127">**名前** &mdash; デバイス登録プロファイルの名前 (ユーザーには表示されません)。</span><span class="sxs-lookup"><span data-stu-id="4bed3-127">**Name**&mdash;The name of the device enrollment profile (not visible to users).</span></span>

   -   <span data-ttu-id="4bed3-128">**説明** &mdash; デバイス登録プロファイルの説明 (ユーザーには表示されません)。</span><span class="sxs-lookup"><span data-stu-id="4bed3-128">**Description**&mdash;A description of the device enrollment profile (not visible to users).</span></span>

   -   <span data-ttu-id="4bed3-129">**登録の詳細** &mdash; デバイスの登録方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-129">**Enrollment Details**&mdash;Specifies how devices are enrolled.</span></span>

       -   <span data-ttu-id="4bed3-130">**ユーザー アフィニティを要求する** &mdash; 初回セットアップ時にデバイスをユーザーに関連付ける必要があります。その後、デバイスは企業のデータや電子メールにアクセスすることが許可されます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-130">**Prompt for user affinity**&mdash;The device must be affiliated with a user during initial setup and can then be permitted to access company data and email.</span></span> <span data-ttu-id="4bed3-131">ユーザーに属し、アプリのインストールなどサービスのポータル サイトを使用する必要がある管理対象のデバイスの場合、**ユーザー アフィニティ**をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-131">**User affinity** should be set up for managed devices that belong to users and need to use the company portal for services like installing apps.</span></span>

       -   <span data-ttu-id="4bed3-132">**ユーザー アフィニティがありません** &mdash; デバイスは、ユーザーと関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="4bed3-132">**No user affinity**&mdash;The device is not affiliated with a user.</span></span> <span data-ttu-id="4bed3-133">このデバイス関連付け情報を使用すると、ローカルのユーザー データにアクセスしなくてもタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-133">Use this affiliation for devices that perform tasks without accessing local user data.</span></span> <span data-ttu-id="4bed3-134">ユーザー アフィリエーションが必要なアプリ (基幹業務アプリのインストールに使用されるポータル サイト アプリを含む) は機能しません。</span><span class="sxs-lookup"><span data-stu-id="4bed3-134">Apps requiring user affiliation (including the Company Portal app used for installing line-of-business apps) won’t work.</span></span>

   -   <span data-ttu-id="4bed3-135">**デバイス グループの事前割り当て** &mdash; このプロファイルで展開されているすべてのデバイスは最初にこのグループに属します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-135">**Device group pre-assignment**&mdash;All devices deployed with this profile will initially belong to this group.</span></span> <span data-ttu-id="4bed3-136">登録後にデバイスの再割り当てができます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-136">You can reassign devices after enrollment.</span></span>

   > [!Important]
   > <span data-ttu-id="4bed3-137">グループの割り当てが Intune から Azure Active Directory に移動します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-137">Group assignments are moving from Intune to Azure Active Directory.</span></span> <span data-ttu-id="4bed3-138">Intune アカウントで適用可能な更新プログラムが受信されると、**[デバイスを次のグループに割り当てる]** オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4bed3-138">Once your Intune account receives the applicable update, you won't see the **Assign devices to the following group** option.</span></span> <span data-ttu-id="4bed3-139">[詳細については、ここをクリック](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments)してください。</span><span class="sxs-lookup"><span data-stu-id="4bed3-139">[Learn more](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).</span></span>

   -  <span data-ttu-id="4bed3-140">**Device Enrollment Program** &mdash; セットアップ アシスタントの登録では、Apple Device Enrollment Program (DEP) を使用できません。</span><span class="sxs-lookup"><span data-stu-id="4bed3-140">**Device Enrollment Program**&mdash;The Apple Device Enrollment Program (DEP) cannot be used with Setup Assistant enrollment.</span></span> <span data-ttu-id="4bed3-141">このトグルが**オフ**に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4bed3-141">Ensure that the toggle is set to **off**.</span></span>

3. <span data-ttu-id="4bed3-142">**[プロファイルの保存]** を選択してプロファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-142">Choose **Save Profile** to add the profile.</span></span>

### <a name="add-ios-devices-to-enroll-with-setup-assistant"></a><span data-ttu-id="4bed3-143">セットアップ アシスタントに登録する iOS デバイスを追加する</span><span class="sxs-lookup"><span data-stu-id="4bed3-143">Add iOS devices to enroll with Setup Assistant</span></span>

1. <span data-ttu-id="4bed3-144">[Microsoft Intune の管理コンソール](https://manage.microsoft.com)で、**[グループ]**&gt;**[すべてのデバイス]**&gt;**[会社が所有しているすべてのデバイス]**&gt;**[すべてのデバイス]** の順に移動し、**[デバイスの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-144">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Groups** &gt; **All Devices** &gt; **All Corporate-owned Devices** &gt; **All Devices**, and then choose **Add devices**.</span></span>

   <span data-ttu-id="4bed3-145">デバイスの追加方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-145">You can add devices in two ways:</span></span>

   ![[デバイスの追加] ダイアログ ボックス](../media/pol-SA-enroll-iOS-SetupAssistant.png)

   - <span data-ttu-id="4bed3-147">**シリアル番号が含まれている CSV ファイルをアップロード** &mdash; .csv ファイル 1 つあたりデバイス 5,000 個または 5 MB を上限とする、2 つの列を持つヘッダーなしのコンマ区切り値 (.csv) リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-147">**Upload a CSV file containing serial numbers**&mdash;Create a comma-separated value (.csv) list of two columns without a header, limited to 5,000 devices or 5 MB per .csv file.</span></span>

     |||
     |-|-|
     |<span data-ttu-id="4bed3-148">&lt;シリアル 1&gt;</span><span class="sxs-lookup"><span data-stu-id="4bed3-148">&lt;Serial #1&gt;</span></span>|<span data-ttu-id="4bed3-149">&lt;デバイス 1 の詳細&gt;</span><span class="sxs-lookup"><span data-stu-id="4bed3-149">&lt;Device #1 Details&gt;</span></span>|
     |<span data-ttu-id="4bed3-150">&lt;シリアル 2&gt;</span><span class="sxs-lookup"><span data-stu-id="4bed3-150">&lt;Serial#2&gt;</span></span>|<span data-ttu-id="4bed3-151">&lt;デバイス 2 の詳細&gt;</span><span class="sxs-lookup"><span data-stu-id="4bed3-151">&lt;Device #2 Details&gt;</span></span>|

   <span data-ttu-id="4bed3-152">この .csv ファイルをテキスト エディターで開くと、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-152">When viewed in a text editor, this .csv file appears as:</span></span>

    ```
    0000000,PO 1234
    111111111,PO 1234
    ```

   -  <span data-ttu-id="4bed3-153">**デバイスの詳細を手動で追加** &mdash; 最大 15 台のデバイスのシリアル番号とメモまたは詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-153">**Manually add device details**&mdash;Enter the serial number and any notes or details for up to 15 devices.</span></span>

   <span data-ttu-id="4bed3-154">**[デバイスの確認]** ウィンドウで、シリアル番号を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-154">On the **Review Devices** pane, you can confirm the serial numbers.</span></span> <span data-ttu-id="4bed3-155">再度インポートするシリアル番号の**詳細**を上書きするかどうかを決定することもできます。あるいは、**[上書き]** チェック ボックスをオフにして、現在の詳細を保持することもできます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-155">You can also decide whether to overwrite the **Details** for serial numbers that are being imported again, or you can uncheck the **Overwrite** box to preserve the Current details.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4bed3-156">既存の Intune 管理者コンソールでは、管理者はアップロードされた CSV から関連する詳細をそのまま使用し、個々のシリアル番号の既存の詳細を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-156">In the existing Intune administrator console, admins can accept associated details from an uploaded CSV and overwrite the existing details for individual serial numbers.</span></span> <span data-ttu-id="4bed3-157">新しい Azure Portal では、単にすべてのシリアル番号の詳細を上書きするか、すべてのシリアル番号の新しい詳細を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-157">In the new Azure portal, you’ll only be able to overwrite the details for all serial numbers or to ignore new details for all serial numbers.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4bed3-158">後で Intune 管理対象から会社所有のデバイスを除外する場合は、**[会社の事前登録済みデバイス]** の **[iOS シリアル番号を使用]** デバイス グループに移動し、Intune からデバイスのシリアル番号を削除して、デバイスの登録を無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-158">If you want to remove corporate-owned devices from Intune management later, you might need to go to **By iOS Serial Number** device group under **Corporate Pre-enrolled devices** and remove the device serial number from Intune in order to disable device enrollment.</span></span> <span data-ttu-id="4bed3-159">シリアル番号の削除時またはその前後に Intune がディザスター リカバリー手順を実行した場合、アクティブなデバイスのシリアル番号のみがそのグループ内に存在していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-159">If Intune performs a disaster recovery procedure on or around the time you remove serial numbers, you'll need to verify that only active devices’ serial numbers are present in that group.</span></span>

2. <span data-ttu-id="4bed3-160">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-160">Choose **Next**.</span></span>

3. <span data-ttu-id="4bed3-161">登録するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-161">Select the devices to enroll.</span></span> <span data-ttu-id="4bed3-162">既に登録されているか、他の方法によって登録済みのシリアル番号はインポートできません。</span><span class="sxs-lookup"><span data-stu-id="4bed3-162">Serial numbers already enrolled or enrolled by other means cannot be imported.</span></span> <span data-ttu-id="4bed3-163">**[次へ]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-163">Choose **Next** to continue.</span></span>

### <a name="assign-a-profile"></a><span data-ttu-id="4bed3-164">プロファイルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4bed3-164">Assign a profile</span></span>

<span data-ttu-id="4bed3-165">使用できるプロファイルのリストから、追加するデバイスに割り当てるプロファイルを指定し、**[登録プロファイルの詳細]** を確認し、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-165">Specify the profile to assign to added devices from the list of available profiles, review the **Enrollment profile details**, and then choose **Finish**.</span></span> <span data-ttu-id="4bed3-166">手動で追加したデバイスは、任意の登録プロファイルに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-166">Manually added devices can be assigned to any enrollment profile.</span></span>

> [!Important]
> <span data-ttu-id="4bed3-167">現在、Intune では "既定の" デバイス登録プロファイルを指定できます。つまり、新しいシリアル番号は、Apple サービスと同期するときに、その既定のプロファイルに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-167">Currently, Intune let you designate a "default" device enrollment profile," which means that new serial numbers are automatically assigned to that default profile when you synchronize new serial numbers with the Apple service.</span></span> <span data-ttu-id="4bed3-168">今後、新しい Azure Portal にテナントが移行された場合、既定のプロファイルを設定し、そのプロファイルにシリアル番号を自動で割り当てられなくなります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-168">When your tenant is migrated to the new Azure portal in the near future, you will no longer be able to set a default profile and have serial numbers be automatically assigned to that profile.</span></span> <span data-ttu-id="4bed3-169">したがって、ユーザーが自分でシリアル番号をプロファイルに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-169">Instead, you will have to assign serial numbers to a profile.</span></span> [<span data-ttu-id="4bed3-170">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4bed3-170">Learn more</span></span>](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios)

### <a name="export-a-profile-to-deploy-to-ios-devices"></a><span data-ttu-id="4bed3-171">iOS デバイスに展開するプロファイルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="4bed3-171">Export a profile to deploy to iOS devices</span></span>

1. <span data-ttu-id="4bed3-172">[Microsoft Intune の管理コンソール](https://manage.microsoft.com)で、**[ポリシー]**&gt;**[業務用デバイスの登録]** の順に進み、モバイル デバイスに展開するデバイス プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-172">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Policy** &gt; **Corporate Device Enrollment**, and then select the device profile to deploy to mobile devices.</span></span>

2. <span data-ttu-id="4bed3-173">タスク バーの **[エクスポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-173">Choose **Export** in the taskbar.</span></span> <span data-ttu-id="4bed3-174">**プロファイルの URL**をコピーおよび保存します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-174">Copy and save the **Profile URL**.</span></span> <span data-ttu-id="4bed3-175">Apple Configurator を使用してこれを後でアップロードして、iOS デバイスで使用する Intune プロファイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-175">You will upload it in Apple Configurator later to define the Intune profile used by iOS devices.</span></span>

   <span data-ttu-id="4bed3-176">iOS デバイスで使用される Intune プロファイルを定義するには、以下の手順で Apple Configurator を使用して Apple サービスにこのプロファイル URL をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="4bed3-176">You will upload this profile URL to the Apple service using Apple Configurator in the following procedure to define the Intune profile used by iOS devices.</span></span>

### <a name="prepare-the-device-with-apple-configurator"></a><span data-ttu-id="4bed3-177">Apple Configurator を使用してデバイスを準備する</span><span class="sxs-lookup"><span data-stu-id="4bed3-177">Prepare the device with Apple Configurator</span></span>

<span data-ttu-id="4bed3-178">モバイル デバイスを管理するために、iOS デバイスを Mac コンピューターに接続および登録します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-178">iOS devices are connected to the Mac computer and enrolled for mobile device management.</span></span>

1. <span data-ttu-id="4bed3-179">Mac コンピューターで **Apple Configurator 2** を開きます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-179">On a Mac computer, open **Apple Configurator 2**.</span></span> <span data-ttu-id="4bed3-180">メニュー バーで、**[Apple Configurator 2]** を選択し、**[基本設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-180">In the menu bar, choose **Apple Configurator 2**, and then choose **Preferences**.</span></span>

   > [!WARNING]
   > <span data-ttu-id="4bed3-181">デバイスは、登録プロセス中に、出荷時の構成にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-181">The devices will be reset to factory configurations during the enrollment process.</span></span> <span data-ttu-id="4bed3-182">ベスト プラクティスとして、デバイスをリセットし、オンにします。</span><span class="sxs-lookup"><span data-stu-id="4bed3-182">As a best practice, reset the device and turn it on.</span></span> <span data-ttu-id="4bed3-183">デバイスを接続するときはデバイスの **[こんにちは]** 画面を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bed3-183">Devices should be at the **Hello** screen when you connect the device.</span></span>

2. <span data-ttu-id="4bed3-184">基本設定ウィンドウで **[サーバー]** を選択し、プラス記号 (+) を選択して MDM サーバー ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-184">In the preferences pane, select **Servers** and choose the plus symbol (+) to launch the MDM Server wizard.</span></span> <span data-ttu-id="4bed3-185">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-185">Choose **Next**.</span></span>

3. <span data-ttu-id="4bed3-186">「Microsoft Intune での iOS デバイスのセットアップ アシスタントを使用した登録」の MDM サーバーの**ホスト名または URL** と**登録 URL** を入力します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-186">Enter the **Hostname or URL** and **enrollment URL** for the MDM server under Setup Assistant enrollment for iOS devices with Microsoft Intune.</span></span> <span data-ttu-id="4bed3-187">登録 URL には、Intune からエクスポートされた登録プロファイル URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-187">For the Enrollment URL, enter the enrollment profile URL exported from Intune.</span></span> <span data-ttu-id="4bed3-188">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-188">Choose **Next**.</span></span>  

   <span data-ttu-id="4bed3-189">"サーバー URL が検証されていない" ことを示す警告は、無視して構いません。</span><span class="sxs-lookup"><span data-stu-id="4bed3-189">You can safely disregard a warning stating "server URL is not verified."</span></span> <span data-ttu-id="4bed3-190">操作を続行するには、ウィザードが完了するまで **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-190">To continue, choose **Next** until the wizard is finished.</span></span>

4. <span data-ttu-id="4bed3-191">USB アダプターを使用して iOS モバイル デバイスを Mac コンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-191">Connect the iOS mobile devices to the Mac computer with a USB adapter.</span></span>

   > [!WARNING]
   > <span data-ttu-id="4bed3-192">デバイスは、登録プロセス中に、出荷時の構成にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-192">The devices will be reset to factory configurations during the enrollment process.</span></span> <span data-ttu-id="4bed3-193">ベスト プラクティスとして、デバイスをリセットし、オンにします。</span><span class="sxs-lookup"><span data-stu-id="4bed3-193">As a best practice, reset the device and turn it on.</span></span> <span data-ttu-id="4bed3-194">セットアップ アシスタントを開始するとデバイスに **[こんにちは]** 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4bed3-194">Devices should be at the **Hello** screen when you start Setup Assistant.</span></span>

5. <span data-ttu-id="4bed3-195">**[準備]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-195">Choose **Prepare**.</span></span> <span data-ttu-id="4bed3-196">[iOS デバイスを準備] ウィンドウで、**[手動]** を選択してから **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-196">On the Prepare iOS Device pane, select **Manual** and then choose **Next**.</span></span>

6. <span data-ttu-id="4bed3-197">[MDM サーバーに登録] ウィンドウで、作成したサーバーの名前を選択してから **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-197">On the Enroll in MDM Server pane, select the server name you created, and then choose **Next**.</span></span>

7. <span data-ttu-id="4bed3-198">[デバイスを監視] ウィンドウで、監視レベルを選択してから **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-198">On the Supervise Devices pane, select the level of supervision, and then choose **Next**.</span></span>

8. <span data-ttu-id="4bed3-199">[組織を作成] ウィンドウで、**[組織]** を選択するか、新しい組織を作成して **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-199">On the Create an Organization pane, choose the **Organization** or create a new organization, and then choose **Next**.</span></span>

9. <span data-ttu-id="4bed3-200">[iOS 設定アシスタントを構成] ウィンドウで、ユーザーに表示する手順を選択し、**[準備]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-200">On the Configure iOS Setup Assistant pane, choose the steps to be presented to the user, and then choose **Prepare**.</span></span> <span data-ttu-id="4bed3-201">メッセージが表示されたら、認証して信頼の設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-201">If prompted, authenticate to update trust settings.</span></span>  

10. <span data-ttu-id="4bed3-202">iOS デバイスの準備が完了したら、USB ケーブルを取り外します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-202">When the iOS device finishes preparing, disconnect the USB cable.</span></span>  

### <a name="distribute-devices"></a><span data-ttu-id="4bed3-203">デバイスを配布する</span><span class="sxs-lookup"><span data-stu-id="4bed3-203">Distribute devices</span></span>

<span data-ttu-id="4bed3-204">これで、デバイスを企業登録できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4bed3-204">The devices are now ready for corporate enrollment.</span></span> <span data-ttu-id="4bed3-205">デバイスをオフにし、ユーザーにデバイスを配布します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-205">Turn off the devices and distribute them to users.</span></span> <span data-ttu-id="4bed3-206">ユーザーがデバイスをオンにすると、セットアップ アシスタントが起動します。</span><span class="sxs-lookup"><span data-stu-id="4bed3-206">When users turn on their devices, Setup Assistant will start.</span></span>



### <a name="see-also"></a><span data-ttu-id="4bed3-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bed3-207">See also</span></span>
[<span data-ttu-id="4bed3-208">デバイスを登録するための前提条件</span><span class="sxs-lookup"><span data-stu-id="4bed3-208">Prerequisites for enrolling devices</span></span>](prerequisites-for-enrollment.md)
