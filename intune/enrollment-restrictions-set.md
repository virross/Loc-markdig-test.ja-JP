---
title: "Intune で登録制限を設定する"
titlesuffix: Azure portal
description: "Intune でプラットフォームごとに登録を制限し、デバイス登録の上限数を設定します。 \""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef3ef89edd3d433575287d2338f7eb37ba22297c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="set-enrollment-restrictions"></a><span data-ttu-id="43166-104">登録制限を設定する</span><span class="sxs-lookup"><span data-stu-id="43166-104">Set enrollment restrictions</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="43166-105">ユーザーは Intune 管理者として、Intune での管理に登録できるデバイスの数と種類を定義した登録の制限を作成し管理することができます。</span><span class="sxs-lookup"><span data-stu-id="43166-105">As an Intune administrator, you can create and manage enrollment restrictions which define the number and types of devices that can enroll into management with Intune.</span></span> <span data-ttu-id="43166-106">制限を複数作成して、さまざまなユーザー グループに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="43166-106">You can create multiple restrictions and apply them to different user groups.</span></span> <span data-ttu-id="43166-107">さまざまな制限を作成した場合は、[優先度](#change-enrollment-restriction-priority)を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="43166-107">You can set the [priority order](#change-enrollment-restriction-priority) for your different restrictions.</span></span>

>[!NOTE]
><span data-ttu-id="43166-108">登録の制限はセキュリティ機能ではありません。</span><span class="sxs-lookup"><span data-stu-id="43166-108">Enrollment restrictions are not security features.</span></span> <span data-ttu-id="43166-109">侵害されたデバイスでは特徴が正しく示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="43166-109">Compromised devices can misrepresent their character.</span></span> <span data-ttu-id="43166-110">これらの制限は、悪意のないユーザーにとって最善の防御策となります。</span><span class="sxs-lookup"><span data-stu-id="43166-110">These restrictions are a best-effort barrier for non-malicious users.</span></span>

>[!NOTE]
><span data-ttu-id="43166-111">以下で説明している、グループに割り当てられた登録制限と優先順位の機能は、Intune の顧客ベース全体にロールアウトしている過程にあります。</span><span class="sxs-lookup"><span data-stu-id="43166-111">The group-assigned enrollment restriction and priority functionality mentioned below are in the process of being rolled out across the Intune customer base.</span></span> <span data-ttu-id="43166-112">このロールアウトが完了するまで、グループと優先順位の機能にアクセスできないことがあります。</span><span class="sxs-lookup"><span data-stu-id="43166-112">Until this roll out is complete, you might not have access to the group and priority features.</span></span> 

<span data-ttu-id="43166-113">具体的に作成できる登録の制限には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="43166-113">The specific enrollment restrictions that you can create include:</span></span>

- <span data-ttu-id="43166-114">登録されるデバイスの最大数</span><span class="sxs-lookup"><span data-stu-id="43166-114">Maximum number of enrolled devices</span></span>
- <span data-ttu-id="43166-115">登録できるデバイスのプラットフォーム:</span><span class="sxs-lookup"><span data-stu-id="43166-115">Device platforms that can enroll:</span></span>
  - <span data-ttu-id="43166-116">Android</span><span class="sxs-lookup"><span data-stu-id="43166-116">Android</span></span>
  - <span data-ttu-id="43166-117">Android for Work</span><span class="sxs-lookup"><span data-stu-id="43166-117">Android for Work</span></span>
  - <span data-ttu-id="43166-118">iOS</span><span class="sxs-lookup"><span data-stu-id="43166-118">iOS</span></span>
  - <span data-ttu-id="43166-119">macOS</span><span class="sxs-lookup"><span data-stu-id="43166-119">macOS</span></span>
  - <span data-ttu-id="43166-120">Windows</span><span class="sxs-lookup"><span data-stu-id="43166-120">Windows</span></span>
- <span data-ttu-id="43166-121">iOS、Android、Android for Work、Windows (Windows 10 バージョンのみ使用可能。Windows 8.1 が許可される場合、これは空白のままにする) のプラットフォーム オペレーティング システム バージョン</span><span class="sxs-lookup"><span data-stu-id="43166-121">Platform operating system version for iOS, Android, Android for Work, and Windows (only Windows 10 versions may be used, leave this blank if Windows 8.1 is allowed)</span></span>
  - <span data-ttu-id="43166-122">最小バージョン</span><span class="sxs-lookup"><span data-stu-id="43166-122">Minimum version</span></span>
  - <span data-ttu-id="43166-123">最大バージョン</span><span class="sxs-lookup"><span data-stu-id="43166-123">Maximum version</span></span>
- <span data-ttu-id="43166-124">個人所有デバイスの制限 (iOS、Android、Android for Work、macOS のみ)</span><span class="sxs-lookup"><span data-stu-id="43166-124">Restrict personally owned devices (iOS, Android, Android for Work, macOS only)</span></span>

## <a name="default-restrictions"></a><span data-ttu-id="43166-125">既定の制限</span><span class="sxs-lookup"><span data-stu-id="43166-125">Default restrictions</span></span>

<span data-ttu-id="43166-126">デバイスの種類とデバイス数の両方の登録制限には、既定の制限が提供されています。</span><span class="sxs-lookup"><span data-stu-id="43166-126">Default restrictions are automatically provided for both device type and device limit enrollment restrictions.</span></span> <span data-ttu-id="43166-127">既定の制限のオプションは変更することができます。</span><span class="sxs-lookup"><span data-stu-id="43166-127">You can change the options for the defaults.</span></span> <span data-ttu-id="43166-128">既定の制限は、すべてのユーザー登録とユーザーなし登録に適用されます。</span><span class="sxs-lookup"><span data-stu-id="43166-128">Default restrictions apply to all user and userless enrollments.</span></span> <span data-ttu-id="43166-129">このような既定の制限を上書きするには、優先度の高い新しい制限を作成します。</span><span class="sxs-lookup"><span data-stu-id="43166-129">You can override these defaults by creating new restrictions with higher priorities.</span></span>

## <a name="create-a-restriction"></a><span data-ttu-id="43166-130">制限を作成する</span><span class="sxs-lookup"><span data-stu-id="43166-130">Create a restriction</span></span>

1. <span data-ttu-id="43166-131">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="43166-131">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="43166-132">**[その他のサービス]** を選択し、**Intune** を検索し、**[Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-132">Choose **More Services**, search for **Intune**, and then choose **Intune**.</span></span>
3. <span data-ttu-id="43166-133">**[デバイスの登録]** > **[登録の制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-133">Choose **Device enrollment** > **Enrollment restrictions**.</span></span>
4. <span data-ttu-id="43166-134">**[制限の作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-134">Choose **Create restriction**.</span></span>
5. <span data-ttu-id="43166-135">制限に名前付け、説明を加えます。</span><span class="sxs-lookup"><span data-stu-id="43166-135">Give the restriction a name and description.</span></span>
6. <span data-ttu-id="43166-136">**[制限の種類]** を選択し、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43166-136">Choose a **Restriction type** and then click **Create**.</span></span>
7. <span data-ttu-id="43166-137">デバイスの上限数の制限については、**[デバイスの上限数]** をクリックして、ユーザーが登録できるデバイスの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="43166-137">For device limit restrictions, click **Device limit** to set the maximum number of devices that a user can enroll.</span></span>
8. <span data-ttu-id="43166-138">デバイスの種類の制限については、**[プラットフォーム]**、**[プラットフォーム構成]** の順にクリックして、各種のプラットフォームおよびバージョンを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="43166-138">For device type restrictions, click **Platforms** and **Platform configurations** to allow or block various platforms and versions.</span></span>
9. <span data-ttu-id="43166-139">**[割り当て]** > **[+ グループの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43166-139">Click **Assignments** > **+ Select groups**.</span></span>
10. <span data-ttu-id="43166-140">**[グループの選択]** で、1 つまたは複数のグループを選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43166-140">Under **Select groups**, select one or more groups, and then click **Select**.</span></span> <span data-ttu-id="43166-141">制限が割り当てられたグループに対してのみ、制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="43166-141">The restriction only applies to groups to which it is assigned.</span></span> <span data-ttu-id="43166-142">少なくとも 1 つのグループに割り当てていない限り、制限は何も影響しません。</span><span class="sxs-lookup"><span data-stu-id="43166-142">If you don't assign a restriction to at least one group, it won't have any effect.</span></span>
11. <span data-ttu-id="43166-143">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43166-143">Click **Save**.</span></span>
12. <span data-ttu-id="43166-144">既定値の制限のすぐ上の優先度を持つ新しい制限が作成されます。</span><span class="sxs-lookup"><span data-stu-id="43166-144">The new restriction is created with a priority just above the default.</span></span> <span data-ttu-id="43166-145">[優先度は変更](#change-enrollment-restriction-priority)することができます。</span><span class="sxs-lookup"><span data-stu-id="43166-145">You can [change the priority](#change-enrollment-restriction-priority).</span></span>

## <a name="set-device-type-restrictions"></a><span data-ttu-id="43166-146">デバイスの種類の制限を設定する</span><span class="sxs-lookup"><span data-stu-id="43166-146">Set device type restrictions</span></span>

<span data-ttu-id="43166-147">デバイスの種類の制限に対する設定は、次の手順で変更することができます。</span><span class="sxs-lookup"><span data-stu-id="43166-147">You can change the settings for a device type restriction by following these steps:</span></span>

1. <span data-ttu-id="43166-148">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="43166-148">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="43166-149">**[その他のサービス]** を選択し、**Intune** を検索し、**[Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-149">Choose **More Services**, search for **Intune**, and then choose **Intune**.</span></span>
3. <span data-ttu-id="43166-150">**[デバイスの登録]** > **[登録の制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-150">Choose **Device enrollment** > **Enrollment restrictions**.</span></span>
4. <span data-ttu-id="43166-151">**[デバイスの種類の制限]** で、設定する制限を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-151">Under **Device Type Restrictions**, choose the restriction that you want to set.</span></span>
5. <span data-ttu-id="43166-152">制限の名前 (既定の制限の場合は**[すべてのユーザー]**) で、**[プラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-152">Under the restriction name (**All Users** for the default restriction), select **Platforms**.</span></span> <span data-ttu-id="43166-153">一覧されたプラットフォームごとに、**[許可]** または **[ブロック]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-153">Choose **Allow** or **Block** for each platform listed.</span></span>
6. <span data-ttu-id="43166-154">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43166-154">Click **Save**.</span></span>
7. <span data-ttu-id="43166-155">制限の名前 (既定の制限の場合は **[すべてのユーザー]**) で、**[プラットフォーム構成]** を選択し、一覧されたプラットフォームの最小および最大の **[バージョン]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-155">Under the restriction name (**All Users** for the default restriction), select **Platform Configurations** and select the minimum and maximum **Versions** for the platforms listed.</span></span> <span data-ttu-id="43166-156">サポートされているバージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="43166-156">Supported versions include:</span></span>
   - <span data-ttu-id="43166-157">Android および Android for Work は、major.minor.rev.build をサポートします。</span><span class="sxs-lookup"><span data-stu-id="43166-157">Android and Android for Work support major.minor.rev.build.</span></span>
   - <span data-ttu-id="43166-158">iOS では major.minor.rev がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="43166-158">iOS supports major.minor.rev.</span></span>
   - <span data-ttu-id="43166-159">Windows では major.minor.rev.build がサポートされます (Windows 10 の場合のみ)。</span><span class="sxs-lookup"><span data-stu-id="43166-159">Windows supports major.minor.rev.build for Windows 10 only.</span></span>
   <span data-ttu-id="43166-160">オペレーティング システムのバージョンは、Device Enrollment Program、Apple School Manager、または Apple Configurator アプリを使用して登録する Apple デバイスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="43166-160">Operating system versions don't apply to Apple devices enrolling with Device Enrollment Program, Apple School Manager, or the Apple Configurator app.</span></span> 
8. <span data-ttu-id="43166-161">一覧されているプラットフォームごとに、**個人所有**のデバイスを**許可**するか**ブロック**するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="43166-161">Specify whether to **Allow** or **Block** **Personally owned** devices for each platform listed.</span></span>

    ![個人所有設定の構成を示す既定デバイス プラットフォーム構成のデバイス制限ワークスペースのスクリーンショット。](media/device-restrictions-platform-configurations.png)
9. <span data-ttu-id="43166-163">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43166-163">Click **Save**.</span></span>

>[!NOTE]
>- <span data-ttu-id="43166-164">個人所有の Android デバイスの登録をブロックした場合でも、個人所有の Android for Work デバイスは登録できます。</span><span class="sxs-lookup"><span data-stu-id="43166-164">If you block personally owned Android devices from enrollment, personally owned Android for Work devices can still enroll.</span></span>
>- <span data-ttu-id="43166-165">既定では、Android for Work デバイス設定は Android デバイスの設定と同じになります。</span><span class="sxs-lookup"><span data-stu-id="43166-165">By default, your Android for Work devices settings will be the same as your settings for your Android devices.</span></span> <span data-ttu-id="43166-166">ただし、Android for Work 設定を変更した後は、同じではなくなります。</span><span class="sxs-lookup"><span data-stu-id="43166-166">However, after you change your Android for Work settings that will no longer be the case.</span></span>
>- <span data-ttu-id="43166-167">個人の Android for Work 登録をブロックした場合、会社の Android デバイスのみを Android for Work として登録できます。</span><span class="sxs-lookup"><span data-stu-id="43166-167">If you block personal Android for Work enrollment, only corporate Android devices can enroll as Android for Work.</span></span>

## <a name="set-device-limit-restrictions"></a><span data-ttu-id="43166-168">デバイス数の制限を設定する</span><span class="sxs-lookup"><span data-stu-id="43166-168">Set device limit restrictions</span></span>

<span data-ttu-id="43166-169">デバイス数の制限の設定は、次の手順に従って変更できます。</span><span class="sxs-lookup"><span data-stu-id="43166-169">You can change the settings for a device limit restriction by following these steps:</span></span>

1. <span data-ttu-id="43166-170">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="43166-170">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="43166-171">**[その他のサービス]** を選択し、**Intune** を検索し、**[Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-171">Choose **More Services**, search for **Intune**, and then choose **Intune**.</span></span>
3. <span data-ttu-id="43166-172">**[デバイスの登録]** > **[登録の制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-172">Choose **Device enrollment** > **Enrollment restrictions**.</span></span>
4. <span data-ttu-id="43166-173">**[デバイス数の制限]** で、設定する制限を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-173">Under **Device Limit Restrictions**, choose the restriction that you want to set.</span></span>
5. <span data-ttu-id="43166-174">**[デバイスの上限数]** を選択し、ドロップダウン リストで、ユーザーが登録できるデバイスの最大数を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-174">Choose **Device Limit** and then, in the drop-down list, select the maximum number of devices a user can enroll.</span></span>
    <span data-ttu-id="43166-175">![[デバイス数の制限] ブレードのスクリーンショット。](./media/device-restrictions-limit.png)</span><span class="sxs-lookup"><span data-stu-id="43166-175">![Screenshot of the device limit restrictions blade with the device limit restrictions.](./media/device-restrictions-limit.png)</span></span>
6. <span data-ttu-id="43166-176">**[Save]**(保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43166-176">Click **Save**.</span></span>

## <a name="change-enrollment-restriction-priority"></a><span data-ttu-id="43166-177">登録制限の優先度を変更する</span><span class="sxs-lookup"><span data-stu-id="43166-177">Change enrollment restriction priority</span></span>

<span data-ttu-id="43166-178">優先度は、制限が割り当てられた複数のグループにユーザーが存在する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="43166-178">Priority is used when a user exists in multiple groups that are assigned restrictions.</span></span> <span data-ttu-id="43166-179">ユーザーは、自分が属するグループに割り当てられている最も高い優先度の制限からのみ影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="43166-179">Users are subject only to the highest priority restriction assigned to a group that they are in.</span></span> <span data-ttu-id="43166-180">たとえば、Joe が優先度 5 の制限に割り当てられたグループ A と優先度 2 の制限に割り当てられたグループ B に属しているとします。</span><span class="sxs-lookup"><span data-stu-id="43166-180">For example, Joe is in a group A assigned to priority 5 restrictions and group B assigned to priority 2 restrictions.</span></span> <span data-ttu-id="43166-181">Joe は優先度 2 の制限からのみ影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="43166-181">Joe is only subject to the priority 2 restrictions.</span></span> 

<span data-ttu-id="43166-182">制限を作成するとき、作成される制限は、リスト上で既定の制限のすぐ上に追加されます。</span><span class="sxs-lookup"><span data-stu-id="43166-182">When you create a restriction, it is added to the list just above the default.</span></span>

<span data-ttu-id="43166-183">デバイスの登録には、デバイスの種類の制限とデバイス数の制限の両方に対する既定の制限が含まれます。</span><span class="sxs-lookup"><span data-stu-id="43166-183">Device enrollment includes default restrictions for both device type and device limit restrictions.</span></span> <span data-ttu-id="43166-184">この 2 つの制限は、より高い優先度の制限で上書きされない限り、すべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="43166-184">These two restrictions apply to all users unless they are overridden by higher-priority restrictions.</span></span> 

<span data-ttu-id="43166-185">既定以外の制限の優先度は、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="43166-185">You can change the priority of any non-default restriction.</span></span> 

<span data-ttu-id="43166-186">**制限の優先度を変更するには**</span><span class="sxs-lookup"><span data-stu-id="43166-186">**To change restriction priority**</span></span>

1. <span data-ttu-id="43166-187">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="43166-187">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="43166-188">**[その他のサービス]** を選択し、**Intune** を検索し、**[Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-188">Choose **More Services**, search for **Intune**, and then choose **Intune**.</span></span>
3. <span data-ttu-id="43166-189">**[デバイスの登録]** > **[登録の制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43166-189">Choose **Device enrollment** > **Enrollment restrictions**.</span></span>
4. <span data-ttu-id="43166-190">優先度リスト内の制限にマウス ポインタを移動させます。</span><span class="sxs-lookup"><span data-stu-id="43166-190">Hover over the restriction in the priority list.</span></span>
5. <span data-ttu-id="43166-191">3 つの縦向きドットを使用して、リスト内の目的の位置に優先度をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="43166-191">Using the three vertical dots, drag the priority to the desired position in the list.</span></span>





