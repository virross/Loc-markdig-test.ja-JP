---
title: "Android for Work のセットアップ"
description: "Microsoft Intune を使用して Android for Work デバイスのモバイル デバイス管理 (MDM) を有効にします。"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: b47b9b4c995c40f6a2c4a5dccf4eb367dacc4a9d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enable-enrollment-of-android-for-work-devices"></a><span data-ttu-id="75d99-103">Android for Work デバイスの登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="75d99-103">Enable enrollment of Android for Work devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="75d99-104">Android for Work デバイスの管理を有効にするには、Android for Work バインディングを Intune に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75d99-104">To enable management of Android for Work devices, you must add an Android for Work binding to Intune.</span></span> <span data-ttu-id="75d99-105">Android for Work をサポートするデバイスで、以前に Android デバイスとして登録していたデバイスを登録するには、デバイスの登録を解除してから、再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75d99-105">To enroll devices that support Android for Work but were previously enrolled as regular Android devices, the devices must be unenrolled and then re-enrolled.</span></span>

## <a name="add-android-for-work-binding-for-intune"></a><span data-ttu-id="75d99-106">Intune 用に Android for Work のバインディングを追加する</span><span class="sxs-lookup"><span data-stu-id="75d99-106">Add Android for Work Binding for Intune</span></span>

1. <span data-ttu-id="75d99-107">**Intune をセットアップする**</span><span class="sxs-lookup"><span data-stu-id="75d99-107">**Set up Intune**</span></span><br>
<span data-ttu-id="75d99-108">**Microsoft Intune** を[モバイル デバイス管理機関に設定](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment)して、MDM の設定を行うことにより、モバイル デバイス管理を準備します (この作業をまだ行っていない場合)。</span><span class="sxs-lookup"><span data-stu-id="75d99-108">If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment) as **Microsoft Intune** and setting up MDM.</span></span>

2. <span data-ttu-id="75d99-109">**Android for Work のバインディングを構成する**</span><span class="sxs-lookup"><span data-stu-id="75d99-109">**Configure Android for Work binding**</span></span><br>
    <span data-ttu-id="75d99-110">Intune 管理者として [Microsoft Intune 管理コンソール](https://manage.microsoft.com)を開き、**[管理]** &gt; **[モバイル デバイス管理]** &gt; **[Android for Work]** の順に選択し、 **[構成]** をクリックして Google Play の Android for Work Web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="75d99-110">As an Intune administrator, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **Android for Work**, and click **Configure** to open Google Play's Android for Work website.</span></span> <span data-ttu-id="75d99-111">この操作で、ブラウザーの新しいタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="75d99-111">This will open in a new tab in your browser.</span></span>

3. <span data-ttu-id="75d99-112">**Google にログインする**</span><span class="sxs-lookup"><span data-stu-id="75d99-112">**Log in to Google**</span></span><br>
   <span data-ttu-id="75d99-113">Google のサインイン ページで、このテナントのすべての Android for Work 管理タスクに関連付ける Google アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="75d99-113">On Google's sign-in page, enter the Google account that will be associated with all Android for Work management tasks for this tenant.</span></span> <span data-ttu-id="75d99-114">これは、お客様の組織の IT 管理者が Play for Work コンソールでアプリを管理および公開するときに共有する Google アカウントです。</span><span class="sxs-lookup"><span data-stu-id="75d99-114">This is the Google account shared among your organization's IT admins that used to manage and publish apps in the Play for Work console.</span></span>

4. <span data-ttu-id="75d99-115">**組織の詳細を指定する**</span><span class="sxs-lookup"><span data-stu-id="75d99-115">**Provide organization details**</span></span><br>
   <span data-ttu-id="75d99-116">**[組織名]** に会社名を入力します。</span><span class="sxs-lookup"><span data-stu-id="75d99-116">Provide your company's name for the **Organization name**.</span></span> <span data-ttu-id="75d99-117">**エンタープライズ モビリティ管理 (EMM) プロバイダー**の場合、*Microsoft Intune* と表示されます。</span><span class="sxs-lookup"><span data-stu-id="75d99-117">For **Enterprise mobility management (EMM) provider**, *Microsoft Intune* should be displayed.</span></span> <span data-ttu-id="75d99-118">Android for Work の使用条件に同意し、**[確認]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75d99-118">Agree to the Android for Work agreement, and then click **Confirm**.</span></span> <span data-ttu-id="75d99-119">要求が処理されます。</span><span class="sxs-lookup"><span data-stu-id="75d99-119">Your request will be processed.</span></span>

## <a name="specify-android-for-work-enrollment-settings"></a><span data-ttu-id="75d99-120">Android for Work 登録設定を指定する</span><span class="sxs-lookup"><span data-stu-id="75d99-120">Specify Android for Work Enrollment Settings</span></span>
   <span data-ttu-id="75d99-121">Android for Work は、特定の Android デバイスでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="75d99-121">Android for Work is only supported on certain Android devices.</span></span> <span data-ttu-id="75d99-122">Google の [Android for Work の要件](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window")に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75d99-122">See Google's [Android for Work requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").</span></span>  <span data-ttu-id="75d99-123">Android for Work をサポートするデバイスは、従来の Android 管理もサポートします。</span><span class="sxs-lookup"><span data-stu-id="75d99-123">Any device that supports Android for Work will also support conventional Android management.</span></span>  <span data-ttu-id="75d99-124">Intune では、Android for Work をサポートするデバイスの管理方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="75d99-124">Intune lets you specify how devices that support Android for Work should be managed:</span></span>

   - <span data-ttu-id="75d99-125">**[すべてのデバイスを Android として管理する]** - Android for Work をサポートするデバイスを含め、すべて Android デバイスを従来の Android デバイスとして登録します。</span><span class="sxs-lookup"><span data-stu-id="75d99-125">**Manage all devices as Android** - All Android devices, including devices that support Android for Work, will be enrolled as conventional Android devices.</span></span>
   - <span data-ttu-id="75d99-126">**[サポートされるデバイスを Android for Work として管理する]** - Android for Work をサポートするすべてのデバイスが Android for Work デバイスとして登録されます。</span><span class="sxs-lookup"><span data-stu-id="75d99-126">**Manage supported devices as Android for Work** - All devices that support Android for Work are enrolled as Android for Work devices.</span></span> <span data-ttu-id="75d99-127">Android for Work をサポートしないすべての Android デバイスは、従来の Android デバイスとして登録されます。</span><span class="sxs-lookup"><span data-stu-id="75d99-127">Any Android device that does not support Android for Work is enrolled as a conventional Android device.</span></span>
   - <span data-ttu-id="75d99-128">**[Manage supported devices for users only in these user groups as Android for Work (ユーザー グループのユーザーについてのみ、サポートされるデバイスを Android for Work として管理する)]** - Android for Work の管理を特定のユーザーのみを対象にします。</span><span class="sxs-lookup"><span data-stu-id="75d99-128">**Manage supported devices for users only in these user groups as Android for Work** - Lets you target Android for Work management to a limited set of users.</span></span> <span data-ttu-id="75d99-129">Android for Work をサポートするデバイスを登録した、選択したグループのメンバーのみが、Android for Work デバイスとして登録されます。</span><span class="sxs-lookup"><span data-stu-id="75d99-129">Only members of the selected groups who enroll a device that supports Android for Work are enrolled as Android for Work devices.</span></span> <span data-ttu-id="75d99-130">その他すべてのデバイスは Android デバイスとして登録されます。</span><span class="sxs-lookup"><span data-stu-id="75d99-130">All others are enrolled as Android devices.</span></span> <span data-ttu-id="75d99-131">これは Android for Work のパイロット中に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="75d99-131">This is useful during Android for Work pilots.</span></span>

## <a name="next-steps-for-android-for-work"></a><span data-ttu-id="75d99-132">Android for Work の次の手順</span><span class="sxs-lookup"><span data-stu-id="75d99-132">Next steps for Android for Work</span></span>
<span data-ttu-id="75d99-133">Android for Work のバインディングと設定を構成したら、次を実行できます。</span><span class="sxs-lookup"><span data-stu-id="75d99-133">After configuring the Android for Work binding and settings, you can do the following:</span></span>
- [<span data-ttu-id="75d99-134">Android for Work アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="75d99-134">Deploy Android for Work apps</span></span>](android-for-work-apps.md)
- [<span data-ttu-id="75d99-135">Android for Work 構成ポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="75d99-135">Add Android for Work configuration policies</span></span>](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a><span data-ttu-id="75d99-136">Android for Work 管理者アカウントのバインドを解除する</span><span class="sxs-lookup"><span data-stu-id="75d99-136">Unbinding your Android for Work administrative account</span></span>

<span data-ttu-id="75d99-137">Android for Work の登録と管理を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="75d99-137">You can turn off Android for Work enrollment and management.</span></span> <span data-ttu-id="75d99-138">Intune の管理コンソールで **[バインドの解除]** をクリックすると、登録されているすべての Android for Work デバイスの登録が削除され、Android for Work アカウントと Intune 間の関係が削除されます。</span><span class="sxs-lookup"><span data-stu-id="75d99-138">Clicking **Unbind** in the Intune administration console removes all enrolled Android for Work devices from enrollment and removes the relationship between the Android for Work account and Intune.</span></span>

### <a name="how-to-unbind-an-android-for-work-account"></a><span data-ttu-id="75d99-139">Android for Work アカウントのバインドを解除する方法</span><span class="sxs-lookup"><span data-stu-id="75d99-139">How to unbind an Android for Work account</span></span>

1. <span data-ttu-id="75d99-140">**Android for Work のバインドを解除する**</span><span class="sxs-lookup"><span data-stu-id="75d99-140">**Unbind Android for Work binding**</span></span><br>
    <span data-ttu-id="75d99-141">管理者として [Microsoft Intune 管理コンソール](https://manage.microsoft.com)を開き、**[管理]** &gt; **[モバイル デバイス管理]** &gt; **[Android for Work]** の順に選択し、**[バインドの解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75d99-141">As an administrative user, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **Android for Work**, and click **Unbind**.</span></span>

2. <span data-ttu-id="75d99-142">**Android for Work のバインドの削除に同意する**</span><span class="sxs-lookup"><span data-stu-id="75d99-142">**Agree to delete Android for Work binding**</span></span><br>
  <span data-ttu-id="75d99-143">**[はい]** をクリックしてバインドを削除し、Intune からすべての Android for Work デバイスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="75d99-143">Click **Yes** to delete the binding and unenroll all Android for Work devices from Intune.</span></span>
