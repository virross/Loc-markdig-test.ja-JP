---
title: "macOS 用のコンプライアンス ポリシーの作成方法"
titleSuffix: Azure portal
description: "macOS デバイス用のコンプライアンス ポリシーの作成方法について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0444183e-f924-4605-96a8-48fdfbc58fd1
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3cf085ff2ee4668ea4c14718719c466bcb982b10
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="create-a-device-compliance-policy-for-macos-devices-with-intune"></a><span data-ttu-id="e92aa-103">Intune で macOS デバイス用のデバイス コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e92aa-103">Create a device compliance policy for macOS devices with Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a><span data-ttu-id="e92aa-104">始める前に</span><span class="sxs-lookup"><span data-stu-id="e92aa-104">Before you begin</span></span>

<span data-ttu-id="e92aa-105">デバイス コンプライアンス ポリシーを作成および割り当てる前に、Intune のデバイス コンプライアンス ポリシーの概念を確認します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-105">Before creating and assigning a device compliance policy, review the Intune device compliance policy concepts.</span></span>

- <span data-ttu-id="e92aa-106">デバイス コンプライアンス ポリシーの詳細については、「[Intune でのデバイス コンプライアンスの概要](device-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e92aa-106">To learn more about device compliance policies, see [get started with device compliance policies](device-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e92aa-107">プラットフォームごとにデバイス コンプライアンス ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e92aa-107">You need to create device compliance policies for each platform.</span></span> <span data-ttu-id="e92aa-108">Intune のデバイス コンプライアンス ポリシー設定は、MDM プロトコルによって公開される設定である、プラットフォームの機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e92aa-108">Intune device compliance policy settings depend on platform capabilities which are settings exposed through the MDM protocol.</span></span>

<span data-ttu-id="e92aa-109">次の表では、条件付きアクセス ポリシーとコンプライアンス ポリシーを使用する場合に非準拠設定をどのように管理するかについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="e92aa-109">The table below describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.</span></span>

-------------------------------


| <span data-ttu-id="e92aa-110">**ポリシー設定**</span><span class="sxs-lookup"><span data-stu-id="e92aa-110">**Policy setting**</span></span> | <span data-ttu-id="e92aa-111">**macOS 10.11 以降**</span><span class="sxs-lookup"><span data-stu-id="e92aa-111">**macOS 10.11 and later**</span></span> |
| --- | --- |
| <span data-ttu-id="e92aa-112">**PIN またはパスワードの構成**</span><span class="sxs-lookup"><span data-stu-id="e92aa-112">**PIN or password configuration**</span></span> | <span data-ttu-id="e92aa-113">修復</span><span class="sxs-lookup"><span data-stu-id="e92aa-113">Remediated</span></span> |   
| <span data-ttu-id="e92aa-114">**デバイスの暗号化**</span><span class="sxs-lookup"><span data-stu-id="e92aa-114">**Device encryption**</span></span> | <span data-ttu-id="e92aa-115">修復 (PIN の設定による)</span><span class="sxs-lookup"><span data-stu-id="e92aa-115">Remediated (by setting PIN)</span></span> |
| <span data-ttu-id="e92aa-116">**電子メールのプロファイル**</span><span class="sxs-lookup"><span data-stu-id="e92aa-116">**Email profile**</span></span> | <span data-ttu-id="e92aa-117">検疫済み</span><span class="sxs-lookup"><span data-stu-id="e92aa-117">Quarantined</span></span> |
|<span data-ttu-id="e92aa-118">**最小 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="e92aa-118">**Minimum OS version**</span></span> | <span data-ttu-id="e92aa-119">検疫済み</span><span class="sxs-lookup"><span data-stu-id="e92aa-119">Quarantined</span></span> |
| <span data-ttu-id="e92aa-120">**最大 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="e92aa-120">**Maximum OS version**</span></span> | <span data-ttu-id="e92aa-121">検疫済み</span><span class="sxs-lookup"><span data-stu-id="e92aa-121">Quarantined</span></span> |  
| <span data-ttu-id="e92aa-122">**Windows 正常性構成証明書**</span><span class="sxs-lookup"><span data-stu-id="e92aa-122">**Windows health attestation**</span></span> | <span data-ttu-id="e92aa-123">該当なし</span><span class="sxs-lookup"><span data-stu-id="e92aa-123">Not applicable</span></span> |  
----------------------------


<span data-ttu-id="e92aa-124">**修復** = デバイス オペレーティング システムによって準拠が強制されます </span><span class="sxs-lookup"><span data-stu-id="e92aa-124">**Remediated** = The device operating system enforces compliance.</span></span> <span data-ttu-id="e92aa-125">(たとえば、ユーザーは PIN を設定するように強制されます)。</span><span class="sxs-lookup"><span data-stu-id="e92aa-125">(For example, the user is forced to set a PIN.)</span></span>

<span data-ttu-id="e92aa-126">**検疫済み** = デバイス オペレーティング システムによって準拠が強制されません </span><span class="sxs-lookup"><span data-stu-id="e92aa-126">**Quarantined** = The device operating system does not enforce compliance.</span></span> <span data-ttu-id="e92aa-127">(たとえば、Android デバイスでは、ユーザーはデバイスの暗号化を強制されません)。デバイスが準拠していない場合、次のアクションが行われます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-127">(For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:</span></span>

- <span data-ttu-id="e92aa-128">ユーザーに条件付きアクセス ポリシーを適用すると、デバイスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-128">The device is blocked if a conditional access policy applies to the user.</span></span>
- <span data-ttu-id="e92aa-129">ポータル サイトは、コンプライアンスの問題をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-129">The company portal notifies the user about any compliance problems.</span></span>

## <a name="macos-compliance-policy-settings"></a><span data-ttu-id="e92aa-130">MacOS のコンプライアンス ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="e92aa-130">MacOS compliance policy settings</span></span>

<span data-ttu-id="e92aa-131">Intune に準拠したデバイスを作成するときに、選択できるさまざまな設定を持つさまざまなカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="e92aa-131">You have different categories with different settings to choose from when creating a new device compliance with Intune:</span></span>

- <span data-ttu-id="e92aa-132">デバイスのヘルス</span><span class="sxs-lookup"><span data-stu-id="e92aa-132">Device Health</span></span>

- <span data-ttu-id="e92aa-133">デバイスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="e92aa-133">Device Properties</span></span>

- <span data-ttu-id="e92aa-134">システム セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e92aa-134">System Security</span></span>

### <a name="device-health"></a><span data-ttu-id="e92aa-135">デバイスのヘルス</span><span class="sxs-lookup"><span data-stu-id="e92aa-135">Device Health</span></span>

- <span data-ttu-id="e92aa-136">**システム整合性の保護を必要とする**: macOS デバイスでシステム整合性の保護が有効になっているかどうかを確認するには、**[必須]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-136">**Require a system integrity protection** : Set this to **Require** to check if your macOS devices have system integrity protection enabled.</span></span>

### <a name="device-properties"></a><span data-ttu-id="e92aa-137">デバイスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="e92aa-137">Device properties</span></span>

- <span data-ttu-id="e92aa-138">**最小 OS バージョン**: デバイスが最小 OS バージョンの要件を満たしていない場合、非準拠として報告されます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-138">**Minimum OS version** : When a device does not meet the minimum OS version requirement, it is reported as noncompliant.</span></span> <span data-ttu-id="e92aa-139">アップグレード方法に関する情報のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-139">A link with information on how to upgrade appears.</span></span> <span data-ttu-id="e92aa-140">ユーザーは、そのデバイスのアップグレードを行うことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-140">The user can choose to upgrade their device.</span></span> <span data-ttu-id="e92aa-141">その後、会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-141">After that, they can access company resources.</span></span>

- <span data-ttu-id="e92aa-142">**最大 OS バージョン**: ルールに指定された OS バージョンより新しいバージョンの OS がデバイスで使用されている場合、会社のリソースへのアクセスがブロックされ、IT 管理者に問い合わせることをユーザーに促すメッセージが表示されます。対象の OS バージョンを許可するようにルールが変更されるまで、このデバイスを使用して会社のリソースへのアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e92aa-142">**Maximum OS version** : When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.</span></span>

### <a name="system-security-settings"></a><span data-ttu-id="e92aa-143">システム セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="e92aa-143">System security settings</span></span>

#### <a name="password"></a><span data-ttu-id="e92aa-144">パスワード</span><span class="sxs-lookup"><span data-stu-id="e92aa-144">Password</span></span>

- <span data-ttu-id="e92aa-145">**モバイル デバイスのロック解除にパスワードを必要とする**: デバイスにアクセスするユーザーにパスワードを入力するよう求める場合は、**[必須]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-145">**Require a password to unlock mobile devices** : Set this to **Require** so users need to enter a password before they can access their device.</span></span>

- <span data-ttu-id="e92aa-146">**単純なパスワード**: これを **[ブロック]** に設定すると、ユーザーは単純なパスワード (**1234**、**1111** など) を作成できません。</span><span class="sxs-lookup"><span data-stu-id="e92aa-146">**Simple passwords** : Set this to **Block** so user can't create a simple password like **1234** or **1111**.</span></span>

- <span data-ttu-id="e92aa-147">**パスワードの最小文字数**: パスワードに必要な数字または文字の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-147">**Minimum password length** : Specify the minimum number of digits or characters that the password must have.</span></span>

- <span data-ttu-id="e92aa-148">**パスワードの種類**: ユーザーが **[英数字]** パスワードまたは **[数字]** パスワードのどちらを作成する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-148">**Password type** : Specify whether the user must create an **Alphanumeric** password or a **Numeric** password.</span></span>

- <span data-ttu-id="e92aa-149">**パスワードでの英数字以外の文字数**: **[必要なパスワードの種類]** を **[英数字]** に設定した場合、この設定を使用して、パスワードに含める必要がある文字セットの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-149">**Number of non-alphanumeric character in password** : If you set **Required password type** to **Alphanumeric** , use this setting to specify the minimum number of character sets that the password must have.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="e92aa-150">大きな数値を設定すると、ユーザーはより複雑なパスワードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e92aa-150">Setting a higher number will require the user to create a password that is more complex.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e92aa-151">macOS デバイスの場合、この設定はパスワードに含める必要がある特殊文字 (たとえば、**!**</span><span class="sxs-lookup"><span data-stu-id="e92aa-151">For macOS devices, this setting refers to the number of special characters (for example, **!**</span></span> <span data-ttu-id="e92aa-152">、**#**、**&amp;**) の数を示します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-152">, **#** , **&amp;** ) that must be included in the password.</span></span>

- <span data-ttu-id="e92aa-153">**デバイスの画面がロックされるまでの非アクティブな最大分数**: ユーザーがパスワードを再入力しなければならなくなるまでのアイドル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-153">**Maximum minutes of inactivity before password is required** : Specify the idle time before the user must reenter their password.</span></span>

- <span data-ttu-id="e92aa-154">**パスワードの有効期限 (日数)**: 新しいパスワードの作成が必要となるまでのパスワードの有効日数 (1 ～ 250 日) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-154">**Password expiration (days)**: Select the number of days (between 1 and 250) before the password expires and they must create a new one.</span></span>

- <span data-ttu-id="e92aa-155">**再利用できないようにする前のパスワードの数** - 何回前までのパスワードを使用できないようにするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-155">**Number of previous passwords to prevent reuse** : Specify the number of previously used passwords that cannot be reused.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e92aa-156">macOS デバイスでパスワードの要件を変更した場合、ユーザーが次にパスワードを変更するまで、要件の変更は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="e92aa-156">When the password requirement is changed on a macOS device it doesn’t take effect until the next time the user changes their password.</span></span> <span data-ttu-id="e92aa-157">たとえば、パスワードの長さの制限を 8 桁に設定し、macOS デバイスの現在のパスワードが 6 桁である場合、次にユーザーがデバイスでパスワードを更新するまで、デバイスは準拠したままの状態になります。</span><span class="sxs-lookup"><span data-stu-id="e92aa-157">For example, if you set the password length restriction to eight digits and the macOS device currently has a 6 digits password, the device remains compliant until the next time the user updates their password on the device.</span></span>

## <a name="to-create-a-device-compliance-policy"></a><span data-ttu-id="e92aa-158">デバイス コンプライアンス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e92aa-158">To create a device compliance policy</span></span>

1. <span data-ttu-id="e92aa-159">[Azure Portal](https://portal.azure.com) に移動し、Intune 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="e92aa-159">Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span>

2. <span data-ttu-id="e92aa-160">正常にサインインすると、**Azure ダッシュボード**を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-160">After you've successfully signed in, you can see the **Azure Dashboard**.</span></span>

3. <span data-ttu-id="e92aa-161">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-161">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

4. <span data-ttu-id="e92aa-162">**[Intune]** を選ぶと、**Intune ダッシュボード**を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-162">Choose **Intune**, you can see the **Intune Dashboard**.</span></span>

5. <span data-ttu-id="e92aa-163">**[デバイスのポリシー準拠]** を選択して、**[管理]** の **[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-163">Choose **Device compliance**, then choose **Policies** under **Manage**.</span></span>

6. <span data-ttu-id="e92aa-164">**[ポリシーの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-164">Choose **Create Policy**.</span></span>

7. <span data-ttu-id="e92aa-165">名前と説明を入力し、このポリシーを適用するプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-165">Type a name, description and choose the platform that you want this policy to apply to.</span></span>

8. <span data-ttu-id="e92aa-166">**[macOS コンプライアンス ポリシー]** ブレードが表示され、デバイス コンプライアンスの設定カテゴリの **[セキュリティ]**、**[デバイスのヘルス]**、および **[デバイス プロパティ]** を選択して、設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-166">The **macOS compliance policy** blade opens, choose the device compliance setting categories **Security**, **Device health**, and **Device property** to specify your settings.</span></span>

10. <span data-ttu-id="e92aa-167">設定を選択したら、各デバイス コンプライアンスの設定カテゴリで **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-167">Once you are done choosing your settings, choose **OK** under each device compliance setting category.</span></span>

11. <span data-ttu-id="e92aa-168">**[OK]**、**[作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-168">Choose **OK**, then choose **Create**.</span></span>

## <a name="assign-user-groups"></a><span data-ttu-id="e92aa-169">ユーザー グループを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e92aa-169">Assign user groups</span></span>

<span data-ttu-id="e92aa-170">コンプライアンス ポリシーをユーザーに割り当てるには、構成したポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-170">To assign a compliance policy to users, choose a policy that you have configured.</span></span> <span data-ttu-id="e92aa-171">既存のポリシーは、**[コンプライアンス ポリシー]** ブレードで確認できます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-171">Existing policies can be found in the **Compliance policies** blade.</span></span>

1. <span data-ttu-id="e92aa-172">ユーザーに割り当てるデバイス コンプライアンス ポリシーを選択し、**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e92aa-172">Choose the device compliance policy you want to assign to users and choose **Assignments**.</span></span> <span data-ttu-id="e92aa-173">これにより表示されたブレードで、**[Azure Active Directory セキュリティ グループ]** を選択し、ポリシーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-173">This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.</span></span>

2. <span data-ttu-id="e92aa-174">**[グループの選択]** を選択すると、ブレードが開き、Azure AD セキュリティ グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-174">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span>

3. <span data-ttu-id="e92aa-175">**[選択]**、**[保存]** の順に選択して、デバイス コンプライアンス ポリシーを Azure AD セキュリティ グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-175">Choose **Select** then **Save** to assign the device compliance policy to Azure AD security groups.</span></span>

4. <span data-ttu-id="e92aa-176">グループへのデバイス コンプライアンス ポリシーの割り当てが完了したら、**[割り当て]** ブレードを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-176">Once you're done assigning the device compliance policy to your groups, you can close the **Assignments** blade.</span></span>

    > [!TIP]
    > <span data-ttu-id="e92aa-177">既定では、デバイスは 8 時間ごとにコンプライアンスを確認しますが、ユーザーは Intune の会社ポータル アプリを使用してこのプロセスを強制できます。</span><span class="sxs-lookup"><span data-stu-id="e92aa-177">By default, devices check for compliance every 8 hours but users can force this process through the Intune company portal app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e92aa-178">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e92aa-178">Next steps</span></span>

[<span data-ttu-id="e92aa-179">Intune デバイスのコンプライアンス対応ポリシーを監視する方法</span><span class="sxs-lookup"><span data-stu-id="e92aa-179">How to monitor device compliance policies</span></span>](compliance-policy-monitor.md)
