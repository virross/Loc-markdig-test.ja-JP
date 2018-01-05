---
title: "iOS デバイス向けのコンプライアンス ポリシー設定"
description: "このトピックでは、iOS デバイスのコンプライアンス ポリシーで設定できるルールと設定について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7b715e9f950db712dbd632ad360aed62a1922ac2
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="compliance-policy-settings-for-ios-devices-in-microsoft-intune"></a><span data-ttu-id="bf567-103">Microsoft Intune での iOS デバイス向けのコンプライアンス ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="bf567-103">Compliance policy settings for iOS devices in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="bf567-104">このトピックで説明するポリシー設定は、iOS 8.0 以降を実行しているデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bf567-104">The policy settings described in this topic apply to devices running iOS 8.0 and later.</span></span>

<span data-ttu-id="bf567-105">その他のプラットフォームに関する情報を探している場合は、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf567-105">If you are looking for information about other platforms, select one of the following:</span></span>
> [!div class="op_single_selector"]
> - [Android デバイス向けのコンプライアンス ポリシー設定](android-compliance-policy-settings-in-microsoft-intune.md)
> - [Android for Work 向けのコンプライアンス ポリシー設定](afw-compliance-policy-settings-in-microsoft-intune.md)
> - [Windows デバイス向けのコンプライアンス ポリシー設定](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a><span data-ttu-id="bf567-109">システム セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="bf567-109">System security settings</span></span>
### <a name="password"></a><span data-ttu-id="bf567-110">パスワード</span><span class="sxs-lookup"><span data-stu-id="bf567-110">Password</span></span>
- <span data-ttu-id="bf567-111">**モバイル デバイスのロック解除にパスワードを必要とする:** デバイスにアクセスするユーザーにパスワードを入力するよう求める場合は、**[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="bf567-111">**Require a password to unlock mobile devices**: Set this to **Yes** to require the user to enter a password before they can access their device.</span></span> <span data-ttu-id="bf567-112">パスワードを使用する iOS デバイスは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="bf567-112">iOS devices that use a password are encrypted.</span></span>

- <span data-ttu-id="bf567-113">**単純なパスワードを許可する:** これを **[はい]** に設定すると、ユーザーは単純なパスワード (**1234**、**1111** など) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="bf567-113">**Allow simple passwords**: Set this to **Yes** to let the user create a simple password like **1234** or **1111**.</span></span>

-  <span data-ttu-id="bf567-114">**パスワードの最小文字数**: ユーザーのパスワードに含まれている必要がある数字または文字の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf567-114">**Minimum password length**: Specify the minimum number of digits or characters that the user’s password must have.</span></span>

- <span data-ttu-id="bf567-115">**必要なパスワードの種類**: ユーザーが **[英数字]** パスワードまたは **[数字]** パスワードのどちらを作成する必要があるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf567-115">**Required password type**: Specify whether the user must create an **Alphanumeric** password or a **Numeric** password.</span></span>

- <span data-ttu-id="bf567-116">**文字セットの最小数**: **[必要なパスワードの種類]** を **[英数字]** に設定した場合、この設定を使用して、パスワードに含める必要がある文字セットの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf567-116">**Minimum number of character sets**: If you set **Required password type** to **Alphanumeric**, use this setting to specify the minimum number of character sets that the password must have.</span></span> <span data-ttu-id="bf567-117">次の 4 つの文字セットがあります。</span><span class="sxs-lookup"><span data-stu-id="bf567-117">The four character sets are:</span></span>
  -   <span data-ttu-id="bf567-118">小文字</span><span class="sxs-lookup"><span data-stu-id="bf567-118">Lowercase letters</span></span>
  -   <span data-ttu-id="bf567-119">大文字</span><span class="sxs-lookup"><span data-stu-id="bf567-119">Uppercase letters</span></span>
  -   <span data-ttu-id="bf567-120">記号</span><span class="sxs-lookup"><span data-stu-id="bf567-120">Symbols</span></span>
  -   <span data-ttu-id="bf567-121">数字</span><span class="sxs-lookup"><span data-stu-id="bf567-121">Numbers</span></span>

  <span data-ttu-id="bf567-122">大きな数値を設定すると、ユーザーはより複雑なパスワードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf567-122">Setting a higher number will require the user to create a password that is more complex.</span></span>

  <span data-ttu-id="bf567-123">iOS デバイスの場合、この設定はパスワードに含める必要がある特殊文字 (たとえば、**!**、**#**、**&amp;**) の数を示します。</span><span class="sxs-lookup"><span data-stu-id="bf567-123">For iOS devices, this setting refers to the number of special characters (for example, **!**, **#**, **&amp;**) that must be included in the password.</span></span>

- <span data-ttu-id="bf567-124">**デバイスの画面がロックされるまでの非アクティブな時間 (分)**: ユーザーがパスワードを再入力しなければならなくなるまでのアイドル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf567-124">**Minutes of inactivity before password is required**:  Specify the idle time before the user must reenter their password.</span></span>

- <span data-ttu-id="bf567-125">**パスワードの有効期限 (日数)**: 新しいパスワードの作成が必要となるまでのユーザーのパスワードの有効日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf567-125">**Password expiration (days)**: Select the number of days before the user’s password expires and they must create a new one.</span></span>

- <span data-ttu-id="bf567-126">**パスワードの履歴を記憶する**: この設定を **[前のパスワードの再利用を防止]** と組み合わせて使用することで、以前使用されていたパスワードをユーザーが作成することを制限します。</span><span class="sxs-lookup"><span data-stu-id="bf567-126">**Remember password history**: Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>

- <span data-ttu-id="bf567-127">**前のパスワードの再利用を防止**: **[パスワードの履歴を保存する]** が選択されている場合は、再利用できない、以前に使用されていたパスワードの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf567-127">**Prevent reuse of previous passwords**: If you selected **Remember password history**, specify the number of previously used passwords that cannot be reused.</span></span>

- <span data-ttu-id="bf567-128">**デバイスがアイドル状態から戻るときにパスワードを必須とする**: この設定は、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定と組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="bf567-128">**Require a password when the device returns from an idle state**: Use this setting together with the in the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="bf567-129">ユーザーは、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定で指定された時間非アクティブの状態が続いたデバイスにアクセスしようとすると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="bf567-129">The user is prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <a name="email-profile"></a><span data-ttu-id="bf567-130">電子メールのプロファイル</span><span class="sxs-lookup"><span data-stu-id="bf567-130">Email profile</span></span>
- <span data-ttu-id="bf567-131">**電子メール アカウントを Intune で管理する**: このオプションを **[はい]** に設定すると、デバイスは、デバイスに展開された電子メール プロファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf567-131">**Email account must be managed by Intune**: When this option is set to **Yes**, the device must use the email profile deployed to the device.</span></span> <span data-ttu-id="bf567-132">デバイスは、次の状況で非準拠とみなされます。</span><span class="sxs-lookup"><span data-stu-id="bf567-132">The device is considered noncompliant in the following situations:</span></span>
  - <span data-ttu-id="bf567-133">電子メール プロファイルが、コンプライアンス ポリシーの対象となるユーザー グループ以外のユーザー グループに展開されている。</span><span class="sxs-lookup"><span data-stu-id="bf567-133">The email profile is deployed to a user group other than the user group that the compliance policy targets.</span></span>
  - <span data-ttu-id="bf567-134">デバイスに展開された Intune 電子メール プロファイルと一致するメール アカウントが、ユーザーによってデバイスに既にセットアップされている。</span><span class="sxs-lookup"><span data-stu-id="bf567-134">The user has already set up an email account on the device that matches the Intune email profile deployed to the device.</span></span> <span data-ttu-id="bf567-135">Intune では、ユーザーがプロビジョニングしたプロファイルを上書きできないので、結果としてそのプロファイルを管理できません。</span><span class="sxs-lookup"><span data-stu-id="bf567-135">Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it.</span></span> <span data-ttu-id="bf567-136">コンプライアンスを確保するには、ユーザーが既存の電子メール設定を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf567-136">To ensure compliance, the user must remove the existing email settings.</span></span> <span data-ttu-id="bf567-137">これにより、Intune は管理対象の電子メール プロファイルをインストールできるようになります。</span><span class="sxs-lookup"><span data-stu-id="bf567-137">Then, Intune can install the managed email profile.</span></span>

- <span data-ttu-id="bf567-138">**Intune によって管理される必要のある電子メール プロファイルを選択する**: **[電子メールアカウントは Intune によって管理される必要がある]** が設定されている場合は、**[選択]** を選択して Intune 電子メール プロファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf567-138">**Select the email profile that must be managed by Intune**: If the **Email account must be managed by Intune** setting is selected, choose **Select** to specify the Intune email profile.</span></span> <span data-ttu-id="bf567-139">電子メール プロファイルは、デバイス上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf567-139">The email profile must be present on the device.</span></span>

     <span data-ttu-id="bf567-140">電子メール プロファイルの詳細については、「[Microsoft Intune で電子メール プロファイルを使用して会社の電子メールへのアクセスを構成にする](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf567-140">For details about email profiles, see [Configure access to corporate email using email profiles with Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).</span></span>

## <a name="device-health-settings"></a><span data-ttu-id="bf567-141">デバイスのヘルスの設定</span><span class="sxs-lookup"><span data-stu-id="bf567-141">Device health settings</span></span>

- <span data-ttu-id="bf567-142">**デバイスの脱獄または root 化を認めない:** この設定を有効にした場合、脱獄デバイスは準拠しません。</span><span class="sxs-lookup"><span data-stu-id="bf567-142">**Device must not be jailbroken or rooted**: If you enable this setting, jailbroken devices will not be compliant.</span></span>

##  <a name="device-properties"></a><span data-ttu-id="bf567-143">デバイスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="bf567-143">Device properties</span></span>
- <span data-ttu-id="bf567-144">**必要な最小 OS バージョン**: デバイスが最小 OS バージョンの要件を満たしていない場合、非準拠として報告されます。</span><span class="sxs-lookup"><span data-stu-id="bf567-144">**Minimum OS required**: When a device does not meet the minimum OS version requirement, it is reported as noncompliant.</span></span>
<span data-ttu-id="bf567-145">アップグレード方法に関する情報のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf567-145">A link with information on how to upgrade appears.</span></span> <span data-ttu-id="bf567-146">ユーザーは、そのデバイスのアップグレードを行うことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bf567-146">The user can choose to upgrade their device.</span></span> <span data-ttu-id="bf567-147">その後、会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bf567-147">After that, they can access company resources.</span></span>

- <span data-ttu-id="bf567-148">**許可される最大 OS バージョン**: ルールに指定された OS バージョンより新しいバージョンの OS がデバイスで使用されている場合、会社のリソースへのアクセスがブロックされ、IT 管理者に問い合わせることをユーザーに促すメッセージが表示されます。対象の OS バージョンを許可するようにルールが変更されるまで、このデバイスを使用して会社のリソースへのアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bf567-148">**Maximum OS version allowed**: When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.</span></span>
