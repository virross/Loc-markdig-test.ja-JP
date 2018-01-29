---
title: "Android for Work 用のコンプライアンス ポリシーの作成"
titleSuffix: Azure portal
description: "Android for Work デバイス用のコンプライアンス ポリシーの作成方法について説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 67d2db4240d05e87f1784f32f42965527c9559a8
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a><span data-ttu-id="ed6d0-103">Intune で Android for Work デバイス用のデバイス コンプライアンス ポリシーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ed6d0-103">How to create a device compliance policy for Android for Work devices in Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="ed6d0-104">コンプライアンス ポリシーは、プラットフォームごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-104">Compliance policies are created for each platform.</span></span>  <span data-ttu-id="ed6d0-105">また、Azure Portal でコンプライアンス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-105">You can create a compliance policy in the Azure portal.</span></span> <span data-ttu-id="ed6d0-106">コンプライアンス ポリシーの詳細については、[デバイスのコンプライアンス](device-compliance.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-106">To learn more about what compliance policy is see [What is  device compliance ](device-compliance.md) topic.</span></span> <span data-ttu-id="ed6d0-107">コンプライアンス ポリシーを作成する前に対応する必要がある前提条件については、[デバイス コンプライアンスの概要](device-compliance-get-started.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-107">To learn about the prerequisites that you need to address before creating a compliance policy see [Get started with device compliance](device-compliance-get-started.md) topic.</span></span>

<span data-ttu-id="ed6d0-108">次の表では、条件付きアクセス ポリシーとコンプライアンス ポリシーを使用する場合に非準拠設定をどのように管理するかについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-108">The table below describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.</span></span>

--------------------------

|<span data-ttu-id="ed6d0-109">**ポリシー設定**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-109">**policy setting**</span></span>| <span data-ttu-id="ed6d0-110">**Android for Work**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-110">**Android for Work**</span></span> |
| --- | --- |
| <span data-ttu-id="ed6d0-111">**PIN またはパスワードの構成**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-111">**PIN or password configuration**</span></span> |  <span data-ttu-id="ed6d0-112">検疫済み</span><span class="sxs-lookup"><span data-stu-id="ed6d0-112">Quarantined</span></span> |
| <span data-ttu-id="ed6d0-113">**デバイスの暗号化**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-113">**Device encryption**</span></span> |  <span data-ttu-id="ed6d0-114">検疫済み</span><span class="sxs-lookup"><span data-stu-id="ed6d0-114">Quarantined</span></span> |
| <span data-ttu-id="ed6d0-115">**脱獄またはルート化されたデバイス**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-115">**Jailbroken or rooted device**</span></span> | <span data-ttu-id="ed6d0-116">検疫済み (設定ではありません)</span><span class="sxs-lookup"><span data-stu-id="ed6d0-116">Quarantined (not a setting)</span></span> |
| <span data-ttu-id="ed6d0-117">**電子メールのプロファイル**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-117">**email profile**</span></span> | <span data-ttu-id="ed6d0-118">適用できません</span><span class="sxs-lookup"><span data-stu-id="ed6d0-118">Not applicable</span></span> |
| <span data-ttu-id="ed6d0-119">**最小 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-119">**Minimum OS version**</span></span> | <span data-ttu-id="ed6d0-120">検疫済み</span><span class="sxs-lookup"><span data-stu-id="ed6d0-120">Quarantined</span></span> |
| <span data-ttu-id="ed6d0-121">**最大 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-121">**Maximum OS version**</span></span> | <span data-ttu-id="ed6d0-122">検疫済み</span><span class="sxs-lookup"><span data-stu-id="ed6d0-122">Quarantined</span></span> |
| <span data-ttu-id="ed6d0-123">**Windows 正常性構成証明書**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-123">**Windows health attestation**</span></span> |<span data-ttu-id="ed6d0-124">適用できません</span><span class="sxs-lookup"><span data-stu-id="ed6d0-124">Not applicable</span></span> |

<span data-ttu-id="ed6d0-125">**修復** = デバイス オペレーティング システムによって準拠が強制されます </span><span class="sxs-lookup"><span data-stu-id="ed6d0-125">**Remediated** = The device operating system enforces compliance.</span></span> <span data-ttu-id="ed6d0-126">(たとえば、ユーザーは PIN を設定するように強制されます)。+</span><span class="sxs-lookup"><span data-stu-id="ed6d0-126">(For example, the user is forced to set a PIN.)+</span></span>

<span data-ttu-id="ed6d0-127">**検疫済み** = デバイス オペレーティング システムによって準拠が強制されません </span><span class="sxs-lookup"><span data-stu-id="ed6d0-127">**Quarantined** = The device operating system does not enforce compliance.</span></span> <span data-ttu-id="ed6d0-128">(たとえば、Android デバイスでは、ユーザーはデバイスの暗号化を強制されません)。デバイスが準拠していない場合、次のアクションが行われます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-128">(For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:</span></span>

- <span data-ttu-id="ed6d0-129">ユーザーに条件付きアクセス ポリシーを適用すると、デバイスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-129">The device is blocked if a conditional access policy applies to the user.</span></span>
- <span data-ttu-id="ed6d0-130">ポータル サイトは、コンプライアンスの問題をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-130">The company portal notifies the user about any compliance problems.</span></span>

## <a name="create-a-compliance-policy-in-the-azure-portal"></a><span data-ttu-id="ed6d0-131">Azure Portal でコンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ed6d0-131">Create a compliance policy in the Azure portal</span></span>

1. <span data-ttu-id="ed6d0-132">**[Intune]** ブレードで、**[デバイス コンプライアンスの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-132">From the **Intune** blade, choose **Set Device compliance**.</span></span> <span data-ttu-id="ed6d0-133">**[管理]** で **[All device compliance policies (すべてのデバイス コンプライアンス ポリシー)]**、**[作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-133">Under **Manage**, choose **All device compliance policies** and choose **Create**.</span></span>
2. <span data-ttu-id="ed6d0-134">名前と説明を入力し、このポリシーを適用するプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-134">Type a name, description and choose the platform that you want this policy to apply to.</span></span>
3. <span data-ttu-id="ed6d0-135">**[コンプライアンス要件]** を選択し、ここで **[セキュリティ]**、**[デバイスのヘルス]**、**[デバイスのプロパティ]** の設定を指定します。終了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-135">Choose **Compliance requirements** to specify the **Security**, **Device health**, and **Device property** settings here, When you are done, choose **Ok**.</span></span>

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a><span data-ttu-id="ed6d0-136">ユーザー グループを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ed6d0-136">Assign user groups</span></span>

<span data-ttu-id="ed6d0-137">コンプライアンス ポリシーをユーザーに割り当てるには、構成したポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-137">To assign a compliance policy to users, choose a policy that you have configured.</span></span> <span data-ttu-id="ed6d0-138">既存のポリシーは、**[コンプライアンス ポリシー]** ブレードで確認できます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-138">Existing policies can be found in the **Compliance –policy** blade.</span></span>

1. <span data-ttu-id="ed6d0-139">ユーザーに割り当てるポリシーを選択し、**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-139">Choose the policy you want to assign to users and choose **Assignments**.</span></span> <span data-ttu-id="ed6d0-140">これにより表示されたブレードで、**[Azure Active Directory セキュリティ グループ]** を選択し、ポリシーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-140">This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.</span></span>
2. <span data-ttu-id="ed6d0-141">**[グループの選択]** を選択すると、ブレードが開き、Azure AD セキュリティ グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-141">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span>  <span data-ttu-id="ed6d0-142">**[選択]** を選択すると、ポリシーがユーザーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-142">Choosing **Select**  deploys the policy to users.</span></span>

<span data-ttu-id="ed6d0-143">ポリシーがユーザーに適用されました。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-143">You have applied the policy to users.</span></span>  <span data-ttu-id="ed6d0-144">ポリシーの対象となっているユーザーが使用しているデバイスは、コンプライアンスについて評価されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-144">The devices used by the users who are targeted by the policy will be evaluated for compliance.</span></span>

<!--- ##  Compliance policy settings--->

## <a name="system-security-settings"></a><span data-ttu-id="ed6d0-145">システム セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="ed6d0-145">System security settings</span></span>

### <a name="password"></a><span data-ttu-id="ed6d0-146">パスワード</span><span class="sxs-lookup"><span data-stu-id="ed6d0-146">Password</span></span>

- <span data-ttu-id="ed6d0-147">**モバイル デバイスのロック解除にパスワードを必要とする:** デバイスにアクセスするユーザーにパスワードを入力するよう求める場合は、**[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-147">**Require a password to unlock mobile devices:** Set this to **Yes** to require users to enter a password before they can access their device.</span></span>
- <span data-ttu-id="ed6d0-148">**[パスワードの最小文字数]:** パスワードに含まれている必要がある数字または文字の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-148">**Minimum password length:** Specify the minimum number of digits or characters that the password must contain.</span></span>
- <span data-ttu-id="ed6d0-149">**パスワードの品質:** 指定したパスワード要件が、デバイスに構成されているかどうかをこの設定で検出します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-149">**Password quality:** This setting detects if the password requirements you specify is configured on the device.</span></span> <span data-ttu-id="ed6d0-150">この設定を有効にすると、Android デバイスで特定のパスワード要件を構成することが必須になります。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-150">Enable this setting to require that users configure certain password requirements for Android devices.</span></span> <span data-ttu-id="ed6d0-151">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-151">Choose from:</span></span>
  - <span data-ttu-id="ed6d0-152">**低レベルのバイオメトリック セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-152">**Low security biometric**</span></span>
  - <span data-ttu-id="ed6d0-153">**必須**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-153">**Required**</span></span>
  - <span data-ttu-id="ed6d0-154">**最小数の数字**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-154">**At least numeric**</span></span>
  - <span data-ttu-id="ed6d0-155">**最小数の英字**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-155">**At least alphabetic**</span></span>
  - <span data-ttu-id="ed6d0-156">**最小数の英数字**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-156">**At least alphanumeric**</span></span>
  - <span data-ttu-id="ed6d0-157">**英数字と記号**</span><span class="sxs-lookup"><span data-stu-id="ed6d0-157">**Alphanumeric with symbols**</span></span>
- <span data-ttu-id="ed6d0-158">**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]:** ユーザーがパスワードを再入力しなければならなくなるまでのアイドル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-158">**Minutes of inactivity before password is required:** Specifies the idle time before the user must re-enter their password.</span></span>
- <span data-ttu-id="ed6d0-159">**[パスワードの有効期限 (日数)]:** 新しいパスワードの作成が必要となるまでのユーザーのパスワードの有効日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-159">**Password expiration (days):** Select the number of days before the user&#39;s password expires and they must create a new one.</span></span>
- <span data-ttu-id="ed6d0-160">**パスワードの履歴を記憶する:** この設定を **[前のパスワードの再利用を防止]** と組み合わせて使用することで、以前使用されていたパスワードをユーザーが作成することを制限します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-160">**Remember password history:** Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>
- <span data-ttu-id="ed6d0-161">**前のパスワードの再利用を防止:** **[パスワードの履歴を保存する]** が選択されている場合は、再利用できない、以前に使用されていたパスワードの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-161">**Prevent reuse of previous passwords:** If **Remember password history** is selected, specify the number of previously used passwords that cannot be re-used.</span></span>
- <span data-ttu-id="ed6d0-162">**デバイスがアイドル状態から戻るときにパスワードを必須とする:** この設定は、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-162">**Require a password when the device returns from an idle state:** This setting should be used together with the in the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="ed6d0-163">エンドユーザーは、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定で指定された時間非アクティブの状態が続いたデバイスにアクセスしようとすると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-163">The end-users are prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>


### <a name="encryption"></a><span data-ttu-id="ed6d0-164">暗号化</span><span class="sxs-lookup"><span data-stu-id="ed6d0-164">Encryption</span></span>

- <span data-ttu-id="ed6d0-165">**モバイル デバイスで暗号化を必要とする:** Android for Work デバイスは暗号化が適用されるので、この設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-165">**Require encryption on mobile device:** You don't have to configure this setting since Android for Work devices enforce encryption.</span></span>


## <a name="device-health-and-security-settings"></a><span data-ttu-id="ed6d0-166">デバイスの正常性とセキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="ed6d0-166">Device health and security settings</span></span>

- <span data-ttu-id="ed6d0-167">**デバイスの脱獄または root 化を認めない:** この設定を有効にした場合、脱獄デバイスは非準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-167">**Device must not be jailbroken or rooted:** If you enable this setting, jailbroken devices will be evaluated as noncompliant.</span></span>
- <span data-ttu-id="ed6d0-168">**デバイスで提供元不明のアプリのインストールを禁止することを必須にする:** Android for Work デバイスでは、不明なソースからのインストールが常に制限されるので、この設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-168">**Require that devices prevent installation of apps from unknown sources:** You do not have to configure this setting as Android for Work devices always restrict installation from unknown sources.</span></span> <span data-ttu-id="ed6d0-169">。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-169">.</span></span>
- <span data-ttu-id="ed6d0-170">**[USB デバッグの無効化を必須にする]**: Android for Work デバイスでは、USB デバッグは無効にされているので、この設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-170">**Require that USB debugging is disabled** : You do not have to configure this settings as USB debugging is already disabled on Android for Work devices.</span></span>
- <span data-ttu-id="ed6d0-171">**最低限の Android セキュリティ パッチ レベル**: この設定を使用して、Android の修正プログラムの最小レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-171">**Minimum Android security patch level**: Use this setting to specify the minimum Android patch level.</span></span> <span data-ttu-id="ed6d0-172">修正プログラムがこのレベルに達していないデバイスは非対応になります。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-172">Devices that are not at least at this patch level will be noncompliant.</span></span> <span data-ttu-id="ed6d0-173">日付は YYYY-MM-DD の形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-173">The date must be specified the format: YYYY-MM-DD.</span></span>
- <span data-ttu-id="ed6d0-174">**[デバイス脅威保護を有効にすることを必須とする]**: この設定は、Lookout MTP ソリューションからのリスク評価をコンプライアンスの条件とする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-174">**Require device threat protection to be enabled** : Use this setting to take the risk assessment from the Lookout MTP solution as a condition for compliance.</span></span> <span data-ttu-id="ed6d0-175">最大許容脅威レベルとして次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-175">Select the maximum allowed threat level, which is one of the following:</span></span>
  - <span data-ttu-id="ed6d0-176">**[なし (セキュリティ保護)]**: これはセキュリティ上最も安全です。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-176">**None (secured)** This is the most secure.</span></span> <span data-ttu-id="ed6d0-177">デバイスにはいかなる脅威も存在できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-177">This means that the device cannot have any threats.</span></span> <span data-ttu-id="ed6d0-178">デバイスで何らかのレベルの脅威が検出された場合、非準拠と評価されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-178">If the device is detected as having any level of threats, it will be evaluated as non-compliant.</span></span>
  - <span data-ttu-id="ed6d0-179">**[低]**: 存在する脅威が低レベルの場合のみ、デバイスは準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-179">**Low:** Device is evaluated as compliant if only low level threats are present.</span></span> <span data-ttu-id="ed6d0-180">低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-180">Anything higher puts the device in a non-compliant status.</span></span>
  - <span data-ttu-id="ed6d0-181">**[中]**: デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-181">**Medium:** Device is evaluated as compliant if the threats that are present on the device are low or medium level.</span></span> <span data-ttu-id="ed6d0-182">デバイスで高レベルの脅威が検出された場合は、非準拠と判定されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-182">If the device is detected to have high level threats, it is determined as non-compliant.</span></span>
  - <span data-ttu-id="ed6d0-183">**[高]**: 最も安全性の低い状態です。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-183">**High:** This is the least secure.</span></span> <span data-ttu-id="ed6d0-184">基本的にすべての脅威レベルが許容されるため、通常、このソリューションはレポートを目的とした場合にのみ役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-184">Essentially, this allows all threat levels, and perhaps only useful if you using this solution only for reporting purposes.</span></span>

<span data-ttu-id="ed6d0-185">詳細については、「[コンプライアンス ポリシーでデバイスの脅威防御ルールを有効にする](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-185">For more details, see [Enable device threat protection rule in the compliance policy](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy).</span></span>

## <a name="device-property-settings"></a><span data-ttu-id="ed6d0-186">デバイスのプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="ed6d0-186">Device property settings</span></span>

- <span data-ttu-id="ed6d0-187">**必要な最小 OS バージョン:** デバイスが最小 OS バージョンの要件を満たしていない場合、非準拠として報告されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-187">**Minimum OS required:** When a device does not meet the minimum OS version requirement, it is reported as noncompliant.</span></span> <span data-ttu-id="ed6d0-188">アップグレード方法に関する情報のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-188">A link with information on how to upgrade is displayed.</span></span> <span data-ttu-id="ed6d0-189">エンド ユーザーは、デバイスのアップグレードを行うことを選択できます。アップグレード後は、会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-189">The end-user can choose to upgrade their device after which they can access company resources.</span></span>
- <span data-ttu-id="ed6d0-190">**許可される最大 OS バージョン:** ルールに指定された OS バージョンより新しいバージョンの OS がデバイスで使用されている場合、会社のリソースへのアクセスがブロックされ、IT 管理者に問い合わせることをユーザーに促すメッセージが表示されます。対象の OS バージョンを許可するようにルールが変更されるまで、このデバイスを使用して会社のリソースへのアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ed6d0-190">**Maximum OS version allowed:** When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.</span></span>

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
