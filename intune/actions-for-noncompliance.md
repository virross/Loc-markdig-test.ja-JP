---
title: "Intune へのコンプライアンス非対応に対するアクション"
titleSuffix: Intune on Azure
description: "Intune へのコンプライアンス非対応のアクションを作成する方法について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a7f2fe87f2098418c9816f1e3cf0d96f62319469
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="automate-actions-for-noncompliance"></a><span data-ttu-id="e47bf-103">コンプライアンス非対応に対するアクションを自動化する</span><span class="sxs-lookup"><span data-stu-id="e47bf-103">Automate actions for noncompliance</span></span>

<span data-ttu-id="e47bf-104">**コンプライアンス非対応に対するアクション**では、コンプライアンス ポリシーの条件を満たしていない、コンプライアンス非対応のデバイスに適用されるアクションを時刻順に構成できます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-104">The **actions for non-compliance** allow you to configure a time-ordered sequence of actions that are applied to devices that don't meet the compliance policy criteria.</span></span> <span data-ttu-id="e47bf-105">既定では、コンプライアンス ポリシーの条件を満たしていないデバイスが検出されると、Intune がそのデバイスを直ちにコンプライアンス非対応としてマーク付けし、Azure AD 条件付きアクセスがそのデバイスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="e47bf-105">By default, when a device is detected to not meet the compliance policy criteria, Intune immediately marks it as non-compliant, then Azure AD Conditional Access blocks the device.</span></span> <span data-ttu-id="e47bf-106">**コンプライアンス非対応に対するアクション**を使用すると、デバイスがコンプライアンスに非準拠の場合の対処方法をより柔軟に決定できます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-106">The **actions for non-compliance** give you more flexibility to decide what to do when a device is not compliant.</span></span> <span data-ttu-id="e47bf-107">たとえば、デバイスをすぐにブロックしないで、ユーザーにコンプライアンスに対応するための猶予時間を与えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-107">For example, you can decide to not block the device immediately, then give the user a grace period to be compliant.</span></span>

<span data-ttu-id="e47bf-108">アクションには 2 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="e47bf-108">There are two types of actions:</span></span>

-   <span data-ttu-id="e47bf-109">**電子メールよるエンド ユーザーへの通知**: エンド ユーザーに送信する前に、電子メール通知をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-109">**Notify end-users via e-mail**: You can customize your email notification before sending it to the end user.</span></span> <span data-ttu-id="e47bf-110">Intune は、受信者、件名、および会社のロゴ、および連絡先情報を含む、メッセージ本文のカスタマイズを提供します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-110">Intune provides customization of the recipients, subject, and message body, including company logo, and contact information.</span></span>

-   <span data-ttu-id="e47bf-111">**デバイスをコンプライアンス非対応としてマーク付け**: 何日後にデバイスをコンプライアンス非対応としてマーク付けするか、スケジュールを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-111">**Mark device non-compliant**: You can determine a schedule in number of days after the device should be marked not compliant.</span></span> <span data-ttu-id="e47bf-112">これは、すぐに行うこともできますが、デバイスをコンプライアンス対応にするための猶予期間をユーザーに与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-112">This can be immediately, but you can also give the user a grace period to be compliant with your device compliance policies.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e47bf-113">始める前に</span><span class="sxs-lookup"><span data-stu-id="e47bf-113">Before you begin</span></span>

<span data-ttu-id="e47bf-114">コンプライアンス非対応に対するアクションを設定するには、少なくとも 1 つのデバイス コンプライアンス ポリシーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e47bf-114">You need to have at least one device compliance policy created to set up actions for non-compliance.</span></span>

-   <span data-ttu-id="e47bf-115">以下に関してのデバイス コンプライアンス ポリシーの作成方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-115">Learn how to create a device compliance policy for:</span></span>

    -   [<span data-ttu-id="e47bf-116">Android</span><span class="sxs-lookup"><span data-stu-id="e47bf-116">Android</span></span>](compliance-policy-create-android.md)

    -   [<span data-ttu-id="e47bf-117">Android for Work</span><span class="sxs-lookup"><span data-stu-id="e47bf-117">Android for Work</span></span>](compliance-policy-create-android-for-work.md)

    -   [<span data-ttu-id="e47bf-118">iOS</span><span class="sxs-lookup"><span data-stu-id="e47bf-118">iOS</span></span>](compliance-policy-create-ios.md)
    
    -   [<span data-ttu-id="e47bf-119">macOS</span><span class="sxs-lookup"><span data-stu-id="e47bf-119">macOS</span></span>](compliance-policy-create-mac-os.md)

    -   [<span data-ttu-id="e47bf-120">Windows</span><span class="sxs-lookup"><span data-stu-id="e47bf-120">Windows</span></span>](compliance-policy-create-windows.md)

<span data-ttu-id="e47bf-121">デバイス コンプライアンス ポリシーを使用して、デバイスの企業リソースの使用をブロックすることを計画した場合、Azure AD 条件付きアクセス設定の準備を整える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e47bf-121">You need to have Azure AD conditional access set up ready when planning to use device compliance policies to block devices from using corporate resources.</span></span>

- <span data-ttu-id="e47bf-122">詳しくは、[EMS 条件付きアクセスの設定方法](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e47bf-122">Learn [how to setup EMS conditional access](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).</span></span>

<span data-ttu-id="e47bf-123">また、通知メッセージ テンプレートを作成しておく必要もあります。</span><span class="sxs-lookup"><span data-stu-id="e47bf-123">Additionally, you need to have a notification message template created.</span></span> <span data-ttu-id="e47bf-124">この通知メッセージ テンプレートは、ユーザーに電子メールを送信する、コンプライアンス非対応に対するアクションを作成するこの後のプロセスで使用します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-124">The notification message template is used later in the process of creating actions for non-compliance to send e-mail to your users.</span></span>

### <a name="to-create-a-notification-message-template"></a><span data-ttu-id="e47bf-125">通知メッセージ テンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="e47bf-125">To create a notification message template</span></span>

1. <span data-ttu-id="e47bf-126">[Azure Portal の Intune](https://portal.azure.com) に移動し、Intune 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="e47bf-126">Go to the [Intune on Azure portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span>

2. <span data-ttu-id="e47bf-127">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-127">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="e47bf-128">**[Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-128">Choose **Intune**</span></span>

4. <span data-ttu-id="e47bf-129">**[デバイスのポリシー準拠]** を選択し、**[管理]** セクションで **[通知]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-129">Choose **Device compliance**, then choose **Notifications** under the **Manage** section.</span></span>

5. <span data-ttu-id="e47bf-130">**[通知の作成]** を選択し、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-130">Choose **Create notification**, then enter the following:</span></span>

    <span data-ttu-id="e47bf-131">a.</span><span class="sxs-lookup"><span data-stu-id="e47bf-131">a.</span></span>  <span data-ttu-id="e47bf-132">名前</span><span class="sxs-lookup"><span data-stu-id="e47bf-132">Name</span></span>

    <span data-ttu-id="e47bf-133">b.</span><span class="sxs-lookup"><span data-stu-id="e47bf-133">b.</span></span>  <span data-ttu-id="e47bf-134">サブジェクト</span><span class="sxs-lookup"><span data-stu-id="e47bf-134">Subject</span></span>

    <span data-ttu-id="e47bf-135">c.</span><span class="sxs-lookup"><span data-stu-id="e47bf-135">c.</span></span>  <span data-ttu-id="e47bf-136">メッセージ</span><span class="sxs-lookup"><span data-stu-id="e47bf-136">Message</span></span>

    <span data-ttu-id="e47bf-137">d.</span><span class="sxs-lookup"><span data-stu-id="e47bf-137">d.</span></span>  <span data-ttu-id="e47bf-138">電子メール ヘッダー – 会社のロゴを含める</span><span class="sxs-lookup"><span data-stu-id="e47bf-138">E-mail header – Include company logo</span></span>

    <span data-ttu-id="e47bf-139">e.</span><span class="sxs-lookup"><span data-stu-id="e47bf-139">e.</span></span>  <span data-ttu-id="e47bf-140">電子メール フッター – 会社名を含める</span><span class="sxs-lookup"><span data-stu-id="e47bf-140">E-mail footer – Include company name</span></span>

    <span data-ttu-id="e47bf-141">f.</span><span class="sxs-lookup"><span data-stu-id="e47bf-141">f.</span></span>  <span data-ttu-id="e47bf-142">電子メール フッター – 連絡先情報を含める</span><span class="sxs-lookup"><span data-stu-id="e47bf-142">E-mail footer – Include contact information</span></span>

![通知メッセージ テンプレートの例](./media/actionsfornoncompliance-1.PNG)

<span data-ttu-id="e47bf-144">情報の追加が完了したら、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-144">Once you're done adding the information, choose **Create**.</span></span> <span data-ttu-id="e47bf-145">通知メッセージ テンプレートが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e47bf-145">The Notification message template is available for use.</span></span>

> [!NOTE] 
> <span data-ttu-id="e47bf-146">また、以前に作成した通知テンプレートを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-146">You can also edit a Notification template previously created.</span></span>

## <a name="to-create-actions-for-non-compliance"></a><span data-ttu-id="e47bf-147">コンプライアンス非対応に対するアクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="e47bf-147">To create actions for non-compliance</span></span>

> [!TIP]
> <span data-ttu-id="e47bf-148">既定では、Intune はコンプライアンス非対応セクションのアクションで事前定義されている 1 つのアクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-148">By default, Intune provides one action pre-defined in the actions for noncompliance section.</span></span> <span data-ttu-id="e47bf-149">これは、デバイスのコンプライアンス ポリシーの条件を満たしていないことが検出された後に、デバイスを非準拠としてマークする操作です。</span><span class="sxs-lookup"><span data-stu-id="e47bf-149">This is the action to mark the device as not compliant after is detected to not meet your device compliance policy criteria.</span></span> <span data-ttu-id="e47bf-150">検出されてからデバイスを非準拠としてマーク付けするまでの期間をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-150">You can customize how long after the detection the device gets marked not compliant.</span></span> <span data-ttu-id="e47bf-151">このアクションを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e47bf-151">This action cannot be removed.</span></span>

<span data-ttu-id="e47bf-152">新しいデバイスのコンプライアンス ポリシーを作成するとき、または既存のデバイスのコンプライアンス ポリシーを編集するときに、アクションを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-152">You can add an action by the time you’re creating a new device compliance policy or by editing an existing device compliance policy.</span></span>

1.  <span data-ttu-id="e47bf-153">Intune ワークロードで、**[デバイスのポリシー準拠]** ブレードの **[管理]** セクションで **[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-153">In the Intune workload, from the **Device compliance policies** blade, choose **Policies** under the **Manage** section.</span></span>

2.  <span data-ttu-id="e47bf-154">デバイス コンプライアンス ポリシーをクリックして選択してから、**[管理]** セクションで **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-154">Choose a device compliance policy by clicking on it, then choose **Properties** under the **Manage** section.</span></span>

3.  <span data-ttu-id="e47bf-155">**デバイス コンプライアンス ポリシーのプロパティ** ブレードが開いたら、**[コンプライアンス非対応に対するアクション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-155">The **device compliance policy properties** blade opens, choose **Actions for noncompliance**.</span></span>

4.  <span data-ttu-id="e47bf-156">コンプライアンス非対応に対するアクションのブレードが開いたら、**[追加]** を選択して、アクション パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-156">The Actions for noncompliance blade opens, choose **Add** to specify action parameters.</span></span> <span data-ttu-id="e47bf-157">以前に作成したメッセージ テンプレート、追加の受信者、および猶予期間のスケジュールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-157">You can choose the message template previously created, additional recipients, and the grace period schedule.</span></span> <span data-ttu-id="e47bf-158">スケジュールで日数 (0 - 365) を指定して、条件付きアクセス ポリシーを強制的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-158">You can specify the number of days (0 to 365) on the schedule, then you can enforce the conditional access policies.</span></span> <span data-ttu-id="e47bf-159">日数 **[0]** を指定した場合、デバイスがデバイス コンプライアンス ポリシーに準拠しなくなると、条件付きアクセスにより企業リソースへのアクセスが**直ちに**ブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-159">If you specify **0** number of days, this means conditional access must **immediately** block access to corporate resources once the devices are non-compliant with device compliance policies.</span></span>

5.  <span data-ttu-id="e47bf-160">情報の追加が完了したら、**[追加]**、**[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e47bf-160">Once you're done adding your information, choose **Add**, then **OK**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e47bf-161">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e47bf-161">Next steps</span></span>

<span data-ttu-id="e47bf-162">デバイス コンプライアンス ブレードで使用可能なレポートを実行して、デバイス コンプライアンスのアクティビティを監視できます。</span><span class="sxs-lookup"><span data-stu-id="e47bf-162">You can monitor the device compliance activity by running the reports available in the device compliance blade.</span></span> <span data-ttu-id="e47bf-163">詳細については、「[Intune でデバイス コンプライアンスを監視する方法](device-compliance-monitor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e47bf-163">Learn more [how to monitor device compliance with Intune](device-compliance-monitor.md)</span></span>

