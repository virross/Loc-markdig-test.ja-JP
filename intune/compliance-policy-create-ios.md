---
title: "iOS 用のコンプライアンス ポリシーの作成方法"
titleSuffix: Azure portal
description: "iOS デバイス用のコンプライアンス ポリシーの作成方法について説明します。\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b0fdb06b072c325d30b3e5ee72f1982c5f61849
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune"></a><span data-ttu-id="c6d10-103">Intune で iOS デバイス用のデバイス コンプライアンス ポリシーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="c6d10-103">How to create a device compliance policy for iOS devices in Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="c6d10-104">コンプライアンス ポリシーは、プラットフォームごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-104">Compliance policies are created for each platform.</span></span>  <span data-ttu-id="c6d10-105">また、Azure Portal でコンプライアンス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-105">You can create a compliance policy in the Azure portal.</span></span> <span data-ttu-id="c6d10-106">コンプライアンス ポリシーの詳細については、[デバイスのコンプライアンス](device-compliance.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d10-106">To learn more about what compliance policy is see [what is a device compliance](device-compliance.md) topic.</span></span> <span data-ttu-id="c6d10-107">コンプライアンス ポリシーを作成する前に対応する必要がある前提条件については、[デバイス コンプライアンスの概要](device-compliance-get-started.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d10-107">To learn about the prerequisites that you need to address before creating a compliance policy see [Get started with device compliance](device-compliance-get-started.md) topic.</span></span>

<span data-ttu-id="c6d10-108">次の表では、条件付きアクセス ポリシーとコンプライアンス ポリシーを使用する場合に非準拠設定をどのように管理するかについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="c6d10-108">The table below describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.</span></span>

-------------------------------


| <span data-ttu-id="c6d10-109">**ポリシー設定**</span><span class="sxs-lookup"><span data-stu-id="c6d10-109">**Policy setting**</span></span> | <span data-ttu-id="c6d10-110">**iOS 8.0 以降**</span><span class="sxs-lookup"><span data-stu-id="c6d10-110">**iOS 8.0 and later**</span></span> |
| --- | --- |
| <span data-ttu-id="c6d10-111">**PIN またはパスワードの構成**</span><span class="sxs-lookup"><span data-stu-id="c6d10-111">**PIN or password configuration**</span></span> | <span data-ttu-id="c6d10-112">修復</span><span class="sxs-lookup"><span data-stu-id="c6d10-112">Remediated</span></span> |   
| <span data-ttu-id="c6d10-113">**デバイスの暗号化**</span><span class="sxs-lookup"><span data-stu-id="c6d10-113">**Device encryption**</span></span> | <span data-ttu-id="c6d10-114">修復 (PIN の設定による)</span><span class="sxs-lookup"><span data-stu-id="c6d10-114">Remediated (by setting PIN)</span></span> |
| <span data-ttu-id="c6d10-115">**脱獄またはルート化されたデバイス**</span><span class="sxs-lookup"><span data-stu-id="c6d10-115">**Jailbroken or rooted device**</span></span> | <span data-ttu-id="c6d10-116">検疫済み (設定ではありません)</span><span class="sxs-lookup"><span data-stu-id="c6d10-116">Quarantined (not a setting)</span></span>
| <span data-ttu-id="c6d10-117">**電子メールのプロファイル**</span><span class="sxs-lookup"><span data-stu-id="c6d10-117">**Email profile**</span></span> | <span data-ttu-id="c6d10-118">検疫済み</span><span class="sxs-lookup"><span data-stu-id="c6d10-118">Quarantined</span></span> |
|<span data-ttu-id="c6d10-119">**最小 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="c6d10-119">**Minimum OS version**</span></span> | <span data-ttu-id="c6d10-120">検疫済み</span><span class="sxs-lookup"><span data-stu-id="c6d10-120">Quarantined</span></span> |
| <span data-ttu-id="c6d10-121">**最大 OS バージョン**</span><span class="sxs-lookup"><span data-stu-id="c6d10-121">**Maximum OS version**</span></span> | <span data-ttu-id="c6d10-122">検疫済み</span><span class="sxs-lookup"><span data-stu-id="c6d10-122">Quarantined</span></span> |  
| <span data-ttu-id="c6d10-123">**Windows 正常性構成証明書**</span><span class="sxs-lookup"><span data-stu-id="c6d10-123">**Windows health attestation**</span></span> | <span data-ttu-id="c6d10-124">該当なし</span><span class="sxs-lookup"><span data-stu-id="c6d10-124">Not applicable</span></span> |  
----------------------------


<span data-ttu-id="c6d10-125">**修復** = デバイス オペレーティング システムによって準拠が強制されます </span><span class="sxs-lookup"><span data-stu-id="c6d10-125">**Remediated** = The device operating system enforces compliance.</span></span> <span data-ttu-id="c6d10-126">(たとえば、ユーザーは PIN を設定するように強制されます)。</span><span class="sxs-lookup"><span data-stu-id="c6d10-126">(For example, the user is forced to set a PIN.)</span></span>

<span data-ttu-id="c6d10-127">**検疫済み** = デバイス オペレーティング システムによって準拠が強制されません </span><span class="sxs-lookup"><span data-stu-id="c6d10-127">**Quarantined** = The device operating system does not enforce compliance.</span></span> <span data-ttu-id="c6d10-128">(たとえば、Android デバイスでは、ユーザーはデバイスの暗号化を強制されません)。デバイスが準拠していない場合、次のアクションが行われます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-128">(For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:</span></span>

- <span data-ttu-id="c6d10-129">ユーザーに条件付きアクセス ポリシーを適用すると、デバイスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-129">The device is blocked if a conditional access policy applies to the user.</span></span>
- <span data-ttu-id="c6d10-130">ポータル サイトは、コンプライアンスの問題をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-130">The company portal notifies the user about any compliance problems.</span></span>

## <a name="create-a-compliance-policy-in-the-azure-portal"></a><span data-ttu-id="c6d10-131">Azure Portal でコンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c6d10-131">Create a compliance policy in the Azure portal</span></span>

1. <span data-ttu-id="c6d10-132">**[Intune]** ブレードで、**[デバイス コンプライアンスの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-132">From the **Intune** blade, choose **Set Device compliance**.</span></span> <span data-ttu-id="c6d10-133">**[管理]** で **[All device compliance policies (すべてのデバイス コンプライアンス ポリシー)]**、**[作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-133">Under **Manage**, choose **All device compliance policies** and choose **Create**.</span></span>
2. <span data-ttu-id="c6d10-134">名前と説明を入力し、このポリシーを適用するプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-134">Type a name, description and choose the platform that you want this policy to apply to.</span></span>
3. <span data-ttu-id="c6d10-135">**[コンプライアンス要件]** を選択し、ここで **[セキュリティ]**、**[デバイスのヘルス]**、**[デバイスのプロパティ]** の設定を指定します。終了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-135">Choose **Compliance requirements** to specify the **Security**, **Device health**, and **Device property** settings here, When you are done, choose **Ok**.</span></span>

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a><span data-ttu-id="c6d10-136">ユーザー グループを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6d10-136">Assign user groups</span></span>

<span data-ttu-id="c6d10-137">コンプライアンス ポリシーをユーザーに割り当てるには、構成したポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-137">To assign a compliance policy to users, choose a policy that you have configured.</span></span> <span data-ttu-id="c6d10-138">既存のポリシーは、**[コンプライアンス ポリシー]** ブレードで確認できます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-138">Existing policies can be found in the **Compliance –policies** blade.</span></span>

1. <span data-ttu-id="c6d10-139">ユーザーに割り当てるポリシーを選択し、**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-139">Choose the policy you want to assign to users and choose **Assignments**.</span></span> <span data-ttu-id="c6d10-140">これにより表示されたブレードで、**[Azure Active Directory セキュリティ グループ]** を選択し、ポリシーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-140">This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.</span></span>
2. <span data-ttu-id="c6d10-141">**[グループの選択]** を選択すると、ブレードが開き、Azure AD セキュリティ グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-141">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span>  <span data-ttu-id="c6d10-142">**[選択]** を選択すると、ポリシーがユーザーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-142">Choosing **Select**  deploys the policy to users.</span></span>

<span data-ttu-id="c6d10-143">ポリシーがユーザーに適用されました。</span><span class="sxs-lookup"><span data-stu-id="c6d10-143">You have applied the policy to users.</span></span>  <span data-ttu-id="c6d10-144">ポリシーの対象となっているユーザーが使用しているデバイスは、コンプライアンスについて評価されます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-144">The devices used by the users who are targeted by the policy will be evaluated for compliance.</span></span>

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a><span data-ttu-id="c6d10-145">システム セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="c6d10-145">System security settings</span></span>

### <a name="password"></a><span data-ttu-id="c6d10-146">パスワード</span><span class="sxs-lookup"><span data-stu-id="c6d10-146">Password</span></span>

- <span data-ttu-id="c6d10-147">**[モバイル デバイスのロック解除にパスワードを必要とする]**: デバイスにアクセスするユーザーにパスワードを入力するよう求める場合は、**[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-147">**Require a password to unlock mobile devices** : Set this to **Yes** to require the user to enter a password before they can access their device.</span></span> <span data-ttu-id="c6d10-148">パスワードを使用する iOS デバイスは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-148">iOS devices that use a password are encrypted.</span></span>
- <span data-ttu-id="c6d10-149">**[単純なパスワードを許可する]**: これを **[はい]** に設定すると、ユーザーは単純なパスワード (**1234**、**1111** など) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-149">**Allow simple passwords** : Set this to **Yes** to let the user create a simple password like **1234** or **1111**.</span></span>
- <span data-ttu-id="c6d10-150">**[パスワードの最小文字数]**: パスワードに必要な数字または文字の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-150">**Minimum password length** : Specify the minimum number of digits or characters that the password must have.</span></span>
- <span data-ttu-id="c6d10-151">**[必要なパスワードの種類]**: ユーザーが **[英数字]** パスワードまたは **[数字]** パスワードのどちらを作成する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-151">**Required password type** : Specify whether the user must create an **Alphanumeric** password or a **Numeric** password.</span></span>
- <span data-ttu-id="c6d10-152">**[文字セットの最小数]**: **[必要なパスワードの種類]** を **[英数字]** に設定した場合、この設定を使用して、パスワードに含める必要がある文字セットの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-152">**Minimum number of character sets** : If you set **Required password type** to **Alphanumeric** , use this setting to specify the minimum number of character sets that the password must have.</span></span> <span data-ttu-id="c6d10-153">次の 4 つの文字セットがあります。</span><span class="sxs-lookup"><span data-stu-id="c6d10-153">The four character sets are:</span></span>
  - <span data-ttu-id="c6d10-154">小文字</span><span class="sxs-lookup"><span data-stu-id="c6d10-154">Lowercase letters</span></span>
  - <span data-ttu-id="c6d10-155">大文字</span><span class="sxs-lookup"><span data-stu-id="c6d10-155">Uppercase letters</span></span>
  - <span data-ttu-id="c6d10-156">記号</span><span class="sxs-lookup"><span data-stu-id="c6d10-156">Symbols</span></span>
  - <span data-ttu-id="c6d10-157">数字</span><span class="sxs-lookup"><span data-stu-id="c6d10-157">Numbers</span></span>

<span data-ttu-id="c6d10-158">大きな数値を設定すると、ユーザーはより複雑なパスワードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d10-158">Setting a higher number will require the user to create a password that is more complex.</span></span>

<span data-ttu-id="c6d10-159">iOS デバイスの場合、この設定はパスワードに含める必要がある特殊文字 (たとえば、**!**</span><span class="sxs-lookup"><span data-stu-id="c6d10-159">For iOS devices, this setting refers to the number of special characters (for example, **!**</span></span> <span data-ttu-id="c6d10-160">、**#**、**&amp;**) の数を示します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-160">, **#** , **&amp;** ) that must be included in the password.</span></span>

- <span data-ttu-id="c6d10-161">**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]**: ユーザーがパスワードを再入力しなければならなくなるまでのアイドル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-161">**Minutes of inactivity before password is required** : Specify the idle time before the user must reenter their password.</span></span>
- <span data-ttu-id="c6d10-162">**[パスワードの有効期限 (日数)]**: 新しいパスワードの作成が必要となるまでのパスワードの有効日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-162">**Password expiration (days)**: Select the number of days before the password expires and they must create a new one.</span></span>
- <span data-ttu-id="c6d10-163">**[パスワードの履歴を記憶する]**: この設定を **[前のパスワードの再利用を防止]** と組み合わせて使用することで、以前使用されていたパスワードをユーザーが作成することを制限します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-163">**Remember password history** : Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>
- <span data-ttu-id="c6d10-164">**[前のパスワードの再利用を防止]**: **[パスワードの履歴を保存する]** が選択されている場合は、再利用できない、以前に使用されていたパスワードの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-164">**Prevent reuse of previous passwords** : If you selected **Remember password history** , specify the number of previously used passwords that cannot be reused.</span></span>
- <span data-ttu-id="c6d10-165">**[デバイスがアイドル状態から戻るときにパスワードを必須とする]**: この設定は、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定と組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-165">**Require a password when the device returns from an idle state** : Use this setting together with the in the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="c6d10-166">ユーザーは、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定で指定された時間非アクティブの状態が続いたデバイスにアクセスしようとすると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-166">The user is prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <a name="email-profile"></a><span data-ttu-id="c6d10-167">電子メールのプロファイル</span><span class="sxs-lookup"><span data-stu-id="c6d10-167">Email profile</span></span>

- <span data-ttu-id="c6d10-168">**[電子メール アカウントを Intune で管理する]**: このオプションを **[はい]** に設定すると、デバイスは、デバイスに展開された電子メール プロファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d10-168">**Email account must be managed by Intune** : When this option is set to **Yes** , the device must use the email profile deployed to the device.</span></span> <span data-ttu-id="c6d10-169">デバイスは、次の状況で非準拠とみなされます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-169">The device is considered noncompliant in the following situations:</span></span>
  - <span data-ttu-id="c6d10-170">電子メール プロファイルが、コンプライアンス ポリシーの対象となるユーザー グループ以外のユーザー グループに展開されている。</span><span class="sxs-lookup"><span data-stu-id="c6d10-170">The email profile is deployed to a user group other than the user group that the compliance policy targets.</span></span>
  - <span data-ttu-id="c6d10-171">デバイスに展開された Intune 電子メール プロファイルと一致するメール アカウントが、ユーザーによってデバイスに既にセットアップされている。</span><span class="sxs-lookup"><span data-stu-id="c6d10-171">The user has already set up an email account on the device that matches the Intune email profile deployed to the device.</span></span> <span data-ttu-id="c6d10-172">Intune では、ユーザーがプロビジョニングしたプロファイルを上書きできないので、結果としてそのプロファイルを管理できません。</span><span class="sxs-lookup"><span data-stu-id="c6d10-172">Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it.</span></span> <span data-ttu-id="c6d10-173">コンプライアンスを確保するには、ユーザーが既存の電子メール設定を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d10-173">To ensure compliance, the user must remove the existing email settings.</span></span> <span data-ttu-id="c6d10-174">これにより、Intune は管理対象の電子メール プロファイルをインストールできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c6d10-174">Then, Intune can install the managed email profile.</span></span>
- <span data-ttu-id="c6d10-175">**[Intune によって管理される必要のある電子メール プロファイルを選択する]**: **[電子メールアカウントは Intune によって管理される必要がある]** が設定されている場合は、**[選択]** を選択して Intune 電子メール プロファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d10-175">**Select the email profile that must be managed by Intune** : If the **Email account must be managed by Intune** setting is selected, choose **Select** to specify the Intune email profile.</span></span> <span data-ttu-id="c6d10-176">電子メール プロファイルは、デバイス上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d10-176">The email profile must be present on the device.</span></span>

<span data-ttu-id="c6d10-177">電子メール プロファイルの詳細については、「[Microsoft Intune で電子メール プロファイルを使用して会社の電子メールへのアクセスを構成する](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d10-177">For details about email profile, see [Configure access to corporate email using email profiles with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).</span></span>

## <a name="device-health-settings"></a><span data-ttu-id="c6d10-178">デバイスのヘルスの設定</span><span class="sxs-lookup"><span data-stu-id="c6d10-178">Device health settings</span></span>

- <span data-ttu-id="c6d10-179">**[デバイスの脱獄または root 化を認めない]**: この設定を有効にした場合、脱獄デバイスは準拠しません。</span><span class="sxs-lookup"><span data-stu-id="c6d10-179">**Device must not be jailbroken or rooted** : If you enable this setting, jailbroken devices will not be compliant.</span></span>

## <a name="device-properties"></a><span data-ttu-id="c6d10-180">デバイスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c6d10-180">Device properties</span></span>

- <span data-ttu-id="c6d10-181">**[必要な最小 OS バージョン]**: デバイスが最小 OS バージョンの要件を満たしていない場合、非準拠として報告されます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-181">**Minimum OS required** : When a device does not meet the minimum OS version requirement, it is reported as noncompliant.</span></span> <span data-ttu-id="c6d10-182">アップグレード方法に関する情報のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-182">A link with information on how to upgrade appears.</span></span> <span data-ttu-id="c6d10-183">ユーザーは、そのデバイスのアップグレードを行うことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-183">The user can choose to upgrade their device.</span></span> <span data-ttu-id="c6d10-184">その後、会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c6d10-184">After that, they can access company resources.</span></span>
- <span data-ttu-id="c6d10-185">**[許可される最大 OS バージョン]**: ルールに指定された OS バージョンより新しいバージョンの OS がデバイスで使用されている場合、会社のリソースへのアクセスがブロックされ、IT 管理者に問い合わせることをユーザーに促すメッセージが表示されます。対象の OS バージョンを許可するようにルールが変更されるまで、このデバイスを使用して会社のリソースへのアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c6d10-185">**Maximum OS version allowed** : When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.</span></span>

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
