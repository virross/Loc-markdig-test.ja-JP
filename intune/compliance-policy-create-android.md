---
title: "Android 用のコンプライアンス ポリシーの作成方法"
titleSuffix: Azure portal
description: "Android デバイス用のコンプライアンス ポリシーの作成方法について説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f2e641aca167db259cd1cc60d46d5f6fbbe3dde9
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-devices-in-intune"></a><span data-ttu-id="4dcbc-103">Intune で Android デバイス用のデバイス コンプライアンス ポリシーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="4dcbc-103">How to create a device compliance policy for Android devices in Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="4dcbc-104">デバイス コンプライアンス ポリシーはプラットフォームごとに、Intune Azure Portal で作成します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-104">Device compliance policies are created for each platform form the Intune Azure portal.</span></span> 

- <span data-ttu-id="4dcbc-105">コンプライアンス ポリシーの詳細については、[デバイスのコンプライアンス](device-compliance.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-105">To learn more about what compliance policy is see [What is a device compliance](device-compliance.md) topic.</span></span>
- <span data-ttu-id="4dcbc-106">コンプライアンス ポリシーを作成する前に対応する必要がある前提条件については、[デバイス コンプライアンスの概要](device-compliance-get-started.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-106">To learn about the prerequisites that you need to address before creating a compliance policy see [Get started with device compliance](device-compliance-get-started.md) topic.</span></span>

## <a name="to-create-a-device-compliance-policy"></a><span data-ttu-id="4dcbc-107">デバイス コンプライアンス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="4dcbc-107">To create a device compliance policy</span></span>

1. <span data-ttu-id="4dcbc-108">**[Intune]** ブレードで、**[デバイス コンプライアンスの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-108">From the **Intune** blade, choose **Set Device compliance**.</span></span> <span data-ttu-id="4dcbc-109">**[管理]** で **[All device compliance policies (すべてのデバイス コンプライアンス ポリシー)]**、**[作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-109">Under **Manage**, choose **All device compliance policies**, and choose **Create**.</span></span>
2. <span data-ttu-id="4dcbc-110">名前と説明を入力し、このポリシーを適用するプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-110">Type a name, description and choose the platform that you want this policy to apply to.</span></span>
3. <span data-ttu-id="4dcbc-111">**[コンプライアンス要件]** を選択し、**[セキュリティ]**、**[デバイスのヘルス]**、**[デバイスのプロパティ]** の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-111">Choose **Compliance requirements** to specify the **Security**, **Device health**, and **Device property** settings.</span></span> <span data-ttu-id="4dcbc-112">終了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-112">When you are done, choose **OK**.</span></span>

<!-- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.-->

## <a name="to-assign-user-groups"></a><span data-ttu-id="4dcbc-113">ユーザー グループを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="4dcbc-113">To assign user groups</span></span>

<span data-ttu-id="4dcbc-114">コンプライアンス ポリシーをユーザーに割り当てるには、構成したポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-114">To assign a compliance policy to users, choose a policy that you have configured.</span></span> <span data-ttu-id="4dcbc-115">既存のポリシーは、**[コンプライアンス ポリシー]** ブレードで確認できます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-115">Existing policies can be found in the **Compliance –policies** blade.</span></span>

1. <span data-ttu-id="4dcbc-116">ポリシーを選択し、**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-116">Choose the policy and choose **Assignments**.</span></span> <span data-ttu-id="4dcbc-117">これにより表示されたブレードで、**[Azure Active Directory セキュリティ グループ]** を選択し、ポリシーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-117">This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.</span></span>
2. <span data-ttu-id="4dcbc-118">**[グループの選択]** を選択すると、ブレードが開き、Azure AD セキュリティ グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-118">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span> <span data-ttu-id="4dcbc-119">ここで、Azure Active Directory 内にあるセキュリティ グループを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-119">Here you can find the security groups in your Azure Active Directory.</span></span>  <span data-ttu-id="4dcbc-120">このポリシーを適用するユーザー グループを選択し、**[選択]** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-120">You can select the user groups you want this policy to apply to and choose **Select**.</span></span> <span data-ttu-id="4dcbc-121">**[選択]** を選択すると、ポリシーがユーザーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-121">Choosing **Select**  deploys the policy to users.</span></span>

<span data-ttu-id="4dcbc-122">ポリシーがユーザーに適用されました。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-122">You have applied the policy to users.</span></span>  <span data-ttu-id="4dcbc-123">ポリシーの対象となっているユーザーが使用しているデバイスは、コンプライアンスについて評価されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-123">The devices used by the users who are targeted by the policy will be evaluated for compliance.</span></span>

<!---##  Compliance policy settings--->

## <a name="device-health-and-security-settings"></a><span data-ttu-id="4dcbc-124">デバイスの正常性とセキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="4dcbc-124">Device health and security settings</span></span>

- <span data-ttu-id="4dcbc-125">**[デバイスの脱獄または root 化を認めない]**: この設定を有効にした場合、脱獄デバイスは非準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-125">**Device must not be jailbroken or rooted** : If you enable this setting, jailbroken devices will be evaluated as noncompliant.</span></span>
- <span data-ttu-id="4dcbc-126">**[デバイスが提供元不明のアプリのインストールを禁止する必要がある (Android 4.0 以上)]**: **[セキュリティ]** > **[提供元不明のアプリ]** が有効になっているデバイスをブロックするには、この設定を有効にして **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-126">**Require that devices prevent installation of apps from unknown sources (Android 4.0 or later)**: To block devices that have **Security** >; **Unknown sources** enabled on the device, enable this setting and set it to **Yes**.</span></span>

### <a name="important"></a><span data-ttu-id="4dcbc-127">重要</span><span class="sxs-lookup"><span data-stu-id="4dcbc-127">Important</span></span>

<span data-ttu-id="4dcbc-128">サイドローディング アプリケーションでは **[提供元不明のアプリ]** の設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-128">Side-loading applications require that the **Unknown sources** setting is enabled.</span></span> <span data-ttu-id="4dcbc-129">デバイスで Android アプリをサイドローディングしていない場合のみ、このコンプライアンス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-129">Enforce this compliance policy only if you are not side-loading Android apps on devices.</span></span>

- <span data-ttu-id="4dcbc-130">**USB のデバッグが無効になっている必要がある (Android 4.2 以降)**: この設定は、デバイス上の USB のデバッグ オプションの検出が有効になっているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-130">**Require that USB debugging is disabled (Android 4.2 or later)**: This setting specifies whether to detect the USB debugging option on the device is enabled.</span></span>
- <span data-ttu-id="4dcbc-131">**デバイスがセキュリティ上の脅威を検出するためにデバイスのスキャンを有効にしている必要がある (Android 4.2 ～ 4.4)**: この設定は、デバイスで **[アプリの確認]** 機能を有効にすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-131">**Require devices have enabled Scan device for security threats (Android 4.2-4.4)**: This setting specifies that the **Verify apps** feature is enabled on the device.</span></span>
- <span data-ttu-id="4dcbc-132">**Android のセキュリティ修正プログラムの最小レベル (Android 6.0 以降)**: この設定を使用して、Android の修正プログラムの最小レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-132">**Minimum Android security patch level (Android 6.0 or later)**: Use this setting to specify the minimum Android patch level.</span></span> <span data-ttu-id="4dcbc-133">修正プログラムがこのレベルに達していないデバイスは非対応になります。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-133">Devices that are not at least at this patch level will be noncompliant.</span></span> <span data-ttu-id="4dcbc-134">日付は YYYY-MM-DD の形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-134">The date must be specified in the format YYYY-MM-DD.</span></span>
- <span data-ttu-id="4dcbc-135">**[デバイス脅威保護を有効にすることを必須とする]**: この設定は、Lookout MTP ソリューションからのリスク評価をコンプライアンスの条件とする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-135">**Require device threat protection to be enabled** : Use this setting to take the risk assessment from the Lookout MTP solution as a condition for compliance.</span></span> <span data-ttu-id="4dcbc-136">最大許容脅威レベルとして次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-136">Choose the maximum allowed threat level, which is one of the following:</span></span>
  - <span data-ttu-id="4dcbc-137">**[None (secured)]** (なし (セキュリティ保護あり)): これはセキュリティ上最も安全です。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-137">**None (secured)**: This is the most secure.</span></span> <span data-ttu-id="4dcbc-138">デバイスにはいかなる脅威も存在できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-138">This means that the device cannot have any threats.</span></span> <span data-ttu-id="4dcbc-139">デバイスで何らかのレベルの脅威が検出された場合、非準拠と評価されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-139">If the device is detected as having any level of threats, it will be evaluated as noncompliant.</span></span>
  - <span data-ttu-id="4dcbc-140">**[低]**: 存在する脅威が低レベルの場合のみ、デバイスは準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-140">**Low** : The device is evaluated as compliant if only low-level threats are present.</span></span> <span data-ttu-id="4dcbc-141">低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-141">Anything higher puts the device in a noncompliant status.</span></span>
  - <span data-ttu-id="4dcbc-142">**[中]**: デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-142">**Medium** : The device is evaluated as compliant if the threats that are present on the device are low or medium level.</span></span> <span data-ttu-id="4dcbc-143">デバイスで高レベルの脅威が検出された場合は、非準拠と判定されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-143">If the device is detected to have high-level threats, it is determined to be noncompliant.</span></span>
  - <span data-ttu-id="4dcbc-144">**[高]**: 最も安全性の低い状態です。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-144">**High** : This is the least secure.</span></span> <span data-ttu-id="4dcbc-145">基本的に、すべての脅威レベルが許容されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-145">Essentially, this allows all threat levels.</span></span> <span data-ttu-id="4dcbc-146">レポート目的でこのソリューションを利用する場合であれば、便利かもしれません。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-146">Perhaps it is useful if you are using this solution only for reporting purposes.</span></span>

<span data-ttu-id="4dcbc-147">詳細については、「[コンプライアンス ポリシーでデバイスの脅威防御ルールを有効にする](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-147">For more details, see [Enable device threat protection rule in the compliance policy](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy).</span></span>

## <a name="system-security-settings"></a><span data-ttu-id="4dcbc-148">システム セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="4dcbc-148">System security settings</span></span>

### <a name="password"></a><span data-ttu-id="4dcbc-149">パスワード</span><span class="sxs-lookup"><span data-stu-id="4dcbc-149">Password</span></span>

- <span data-ttu-id="4dcbc-150">**[モバイル デバイスのロック解除にパスワードを必要とする]**: デバイスにアクセスするユーザーにパスワードを入力するよう求める場合は、**[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-150">**Require a password to unlock mobile devices** : Set this to **Yes** to require users to enter a password before they can access their device.</span></span>
- <span data-ttu-id="4dcbc-151">**[パスワードの最小文字数]**: ユーザーのパスワードに必要な数字または文字の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-151">**Minimum password length** : Specify the minimum number of digits or characters that the user&#39;s password must have.</span></span>
- <span data-ttu-id="4dcbc-152">**[パスワードの品質]**: 指定したパスワード要件が、デバイスに構成されているかどうかをこの設定で検出します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-152">**Password quality** : This setting detects if the password requirements that you specify are set up on the device.</span></span> <span data-ttu-id="4dcbc-153">この設定を有効にすると、Android デバイスで特定のパスワード要件を満たすことが必須になります。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-153">Enable this setting to require that users meet certain password requirements for Android devices.</span></span> <span data-ttu-id="4dcbc-154">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-154">Choose from:</span></span>
  - <span data-ttu-id="4dcbc-155">**低レベルのバイオメトリック セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-155">**Low security biometric**</span></span>
  - <span data-ttu-id="4dcbc-156">**必須**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-156">**Required**</span></span>
  - <span data-ttu-id="4dcbc-157">**最小数の数字**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-157">**At least numeric**</span></span>
  - <span data-ttu-id="4dcbc-158">**最小数の英字**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-158">**At least alphabetic**</span></span>
  - <span data-ttu-id="4dcbc-159">**最小数の英数字**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-159">**At least alphanumeric**</span></span>
  - <span data-ttu-id="4dcbc-160">**英数字と記号**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-160">**Alphanumeric with symbols**</span></span>
- <span data-ttu-id="4dcbc-161">**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]**: ユーザーがパスワードを再入力しなければならなくなるまでのアイドル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-161">**Minutes of inactivity before password is required** : Specify the idle time before the user must reenter their password.</span></span>
- <span data-ttu-id="4dcbc-162">**[パスワードの有効期限 (日数)]**: 新しいパスワードの作成が必要となるまでのパスワードの有効日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-162">**Password expiration (days)**: Select the number of days before the password expires and they must create a new one.</span></span>
- <span data-ttu-id="4dcbc-163">**[パスワードの履歴を記憶する]**: この設定を **[前のパスワードの再利用を防止]** と共に使用することで、以前使用されていたパスワードをユーザーが作成することを制限します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-163">**Remember password history** : Use this setting together with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>
- <span data-ttu-id="4dcbc-164">**[前のパスワードの再利用を防止]**: **[パスワードの履歴を保存する]** が選択されている場合は、再利用できない、以前に使用されていたパスワードの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-164">**Prevent reuse of previous passwords** : If you selected **Remember password history** , specify the number of previously used passwords that cannot be reused.</span></span>
- <span data-ttu-id="4dcbc-165">**[デバイスがアイドル状態から戻るときにパスワードを必須とする]**: この設定は、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-165">**Require a password when the device returns from an idle state** : Use this setting together with the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="4dcbc-166">ユーザーは、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定で指定された時間非アクティブの状態が続いたデバイスにアクセスしようとすると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-166">The user is prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <a name="encryption"></a><span data-ttu-id="4dcbc-167">暗号化</span><span class="sxs-lookup"><span data-stu-id="4dcbc-167">Encryption</span></span>

- <span data-ttu-id="4dcbc-168">**[モバイル デバイスで暗号化を必要とする]**: リソースに接続するためにデバイスの暗号化を必要とする場合は、**[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-168">**Require encryption on mobile device** : Set this to **Yes** to require devices to be encrypted in order to connect to resources.</span></span> <span data-ttu-id="4dcbc-169">**[モバイル デバイスのロック解除にパスワードを必要とする]** 設定を選択すると、デバイスは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-169">Devices are encrypted when you choose the setting **Require a password to unlock mobile devices**.</span></span>

## <a name="device-property-settings"></a><span data-ttu-id="4dcbc-170">デバイスのプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="4dcbc-170">Device property settings</span></span>

- <span data-ttu-id="4dcbc-171">**[必要な最小 OS バージョン]**: デバイスが最小 OS バージョンの要件を満たしていない場合、非準拠として報告されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-171">**Minimum OS required** : When a device does not meet the minimum OS version requirement, it is reported as noncompliant.</span></span> <span data-ttu-id="4dcbc-172">アップグレード方法に関する情報のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-172">A link with information on how to upgrade is shown.</span></span> <span data-ttu-id="4dcbc-173">ユーザーは、デバイスのアップグレードを行うことを選択できます。アップグレード後は、会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-173">The user can choose to upgrade their device, after which they can access company resources.</span></span>
- <span data-ttu-id="4dcbc-174">**[許可される最大 OS バージョン]**: ルールに指定された OS バージョンより新しいバージョンの OS がデバイスで使用されている場合、会社のリソースへのアクセスがブロックされ、IT 管理者に問い合わせることをユーザーに促すメッセージが表示されます。対象の OS バージョンを許可するようにルールが変更されるまで、このデバイスを使用して会社のリソースへのアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-174">**Maximum OS version allowed** : When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rules to allow the OS version, this device cannot be used to access company resources.</span></span>

## <a name="how-non-compliant-settings-work-with-conditional-access-policies"></a><span data-ttu-id="4dcbc-175">条件付きアクセス ポリシーを使用したコンプライアンス非対応設定の機能</span><span class="sxs-lookup"><span data-stu-id="4dcbc-175">How non-compliant settings work with conditional access policies?</span></span>

<span data-ttu-id="4dcbc-176">次の表では、条件付きアクセス ポリシーとコンプライアンス ポリシーを使用する場合に非準拠設定をどのように管理するかについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-176">The table below describes how non-compliant settings are managed when a compliance policy is used with a conditional access policy.</span></span>

--------------------

|<span data-ttu-id="4dcbc-177">**ポリシー設定**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-177">**Policy setting**</span></span>| <span data-ttu-id="4dcbc-178">**Android 4.0 以降、Samsung Knox Standard 4.0 以降**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-178">**Android 4.0 and later, Samsung Knox Standard 4.0 and later**</span></span> |
| --- | ----|
| <span data-ttu-id="4dcbc-179">**PIN またはパスワードの構成**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-179">**PIN or password configuration**</span></span> |  <span data-ttu-id="4dcbc-180">検疫済み</span><span class="sxs-lookup"><span data-stu-id="4dcbc-180">Quarantined</span></span> |
| <span data-ttu-id="4dcbc-181">**デバイスの暗号化**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-181">**Device encryption**</span></span> | <span data-ttu-id="4dcbc-182">検疫済み</span><span class="sxs-lookup"><span data-stu-id="4dcbc-182">Quarantined</span></span> |
| <span data-ttu-id="4dcbc-183">**脱獄またはルート化されたデバイス**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-183">**Jailbroken or rooted device**</span></span> | <span data-ttu-id="4dcbc-184">検疫済み (設定ではありません)</span><span class="sxs-lookup"><span data-stu-id="4dcbc-184">Quarantined (not a setting)</span></span> |
| <span data-ttu-id="4dcbc-185">**電子メールのプロファイル**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-185">**email profile**</span></span> | <span data-ttu-id="4dcbc-186">適用できません</span><span class="sxs-lookup"><span data-stu-id="4dcbc-186">Not applicable</span></span> |
| <span data-ttu-id="4dcbc-187">**最小 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-187">**Minimum OS version**</span></span> | <span data-ttu-id="4dcbc-188">検疫済み</span><span class="sxs-lookup"><span data-stu-id="4dcbc-188">Quarantined</span></span> |
| <span data-ttu-id="4dcbc-189">**最大 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-189">**Maximum OS version**</span></span> |   <span data-ttu-id="4dcbc-190">検疫済み</span><span class="sxs-lookup"><span data-stu-id="4dcbc-190">Quarantined</span></span> |
| <span data-ttu-id="4dcbc-191">**Windows 正常性構成証明書**</span><span class="sxs-lookup"><span data-stu-id="4dcbc-191">**Windows health attestation**</span></span> | <span data-ttu-id="4dcbc-192">適用できません</span><span class="sxs-lookup"><span data-stu-id="4dcbc-192">Not applicable</span></span> |

--------------------------

<span data-ttu-id="4dcbc-193">**修復** = デバイス オペレーティング システムによって準拠が強制されます </span><span class="sxs-lookup"><span data-stu-id="4dcbc-193">**Remediated** = The device operating system enforces compliance.</span></span> <span data-ttu-id="4dcbc-194">(たとえば、ユーザーは PIN を設定するように強制されます)。+</span><span class="sxs-lookup"><span data-stu-id="4dcbc-194">(For example, the user is forced to set a PIN.)+</span></span>

<span data-ttu-id="4dcbc-195">**検疫済み** = デバイス オペレーティング システムによって準拠が強制されません </span><span class="sxs-lookup"><span data-stu-id="4dcbc-195">**Quarantined** = The device operating system does not enforce compliance.</span></span> <span data-ttu-id="4dcbc-196">(たとえば、Android デバイスでは、ユーザーはデバイスの暗号化を強制されません)。デバイスが準拠していない場合、次のアクションが行われます。+</span><span class="sxs-lookup"><span data-stu-id="4dcbc-196">(For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:+</span></span>

- <span data-ttu-id="4dcbc-197">ユーザーに条件付きアクセス ポリシーを適用すると、デバイスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-197">The device is blocked if a conditional access policy applies to the user.</span></span>
- <span data-ttu-id="4dcbc-198">ポータル サイトは、コンプライアンスの問題をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="4dcbc-198">The company portal notifies the user about any compliance problems.</span></span>

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
