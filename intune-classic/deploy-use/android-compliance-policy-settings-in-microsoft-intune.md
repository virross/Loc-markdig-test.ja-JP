---
title: "Android 向けのコンプライアンス ポリシー設定"
description: "このトピックでは、Android デバイスのデバイス コンプライアンス ポリシーの設定について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d87a432008a5d6ce9f0a531061a8bbbb6a4ff6d
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="compliance-policy-settings-for-android-devices-in-microsoft-intune"></a><span data-ttu-id="035ee-103">Microsoft Intune での Android デバイス向けのコンプライアンス ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="035ee-103">Compliance policy settings for Android devices in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="035ee-104">このトピックで説明するポリシー設定は、Android 4.0 以降または Samsung KNOX 4.0 を実行しているデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="035ee-104">The policy settings described in this topic apply to devices that are running Android 4.0 and later or Samsung KNOX 4.0 and later.</span></span>

<span data-ttu-id="035ee-105">その他のプラットフォームに関する情報を探している場合は、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="035ee-105">If you're looking for information about other platforms, select one of the following:</span></span>
> [!div class="op_single_selector"]
> - [iOS デバイス向けのコンプライアンス ポリシー設定](ios-compliance-policy-settings-in-microsoft-intune.md)
> - [Windows デバイス向けのコンプライアンス ポリシー設定](windows-compliance-policy-settings-in-microsoft-intune.md)
> - [Android for Work デバイス向けのコンプライアンス ポリシー設定](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a><span data-ttu-id="035ee-109">システム セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="035ee-109">System security settings</span></span>
### <a name="password"></a><span data-ttu-id="035ee-110">パスワード</span><span class="sxs-lookup"><span data-stu-id="035ee-110">Password</span></span>
- <span data-ttu-id="035ee-111">**モバイル デバイスのロック解除にパスワードを必要とする**: デバイスにアクセスするユーザーにパスワードを入力するよう求める場合は、**[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="035ee-111">**Require a password to unlock mobile devices**: Set this to **Yes** to require users to enter a password before they can access their device.</span></span>

-  <span data-ttu-id="035ee-112">**パスワードの最小文字数**: ユーザーのパスワードに含まれている必要がある数字または文字の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="035ee-112">**Minimum password length**: Specify the minimum number of digits or characters that the user’s password must have.</span></span>

- <span data-ttu-id="035ee-113">**パスワードの品質**: 指定したパスワード要件が、デバイスに構成されているかどうかをこの設定で検出します。</span><span class="sxs-lookup"><span data-stu-id="035ee-113">**Password quality**: This setting detects if the password requirements that you specify are set up on the device.</span></span> <span data-ttu-id="035ee-114">この設定を有効にすると、Android デバイスで特定のパスワード要件を満たすことが必須になります。</span><span class="sxs-lookup"><span data-stu-id="035ee-114">Enable this setting to require that users meet certain password requirements for Android devices.</span></span> <span data-ttu-id="035ee-115">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="035ee-115">Choose from:</span></span>

  -   <span data-ttu-id="035ee-116">**低レベルのバイオメトリック セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="035ee-116">**Low security biometric**</span></span>
  -   <span data-ttu-id="035ee-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="035ee-117">**Required**</span></span>
  -   <span data-ttu-id="035ee-118">**最小数の数字**</span><span class="sxs-lookup"><span data-stu-id="035ee-118">**At least numeric**</span></span>
  -   <span data-ttu-id="035ee-119">**最小数の英字**</span><span class="sxs-lookup"><span data-stu-id="035ee-119">**At least alphabetic**</span></span>
  -   <span data-ttu-id="035ee-120">**最小数の英数字**</span><span class="sxs-lookup"><span data-stu-id="035ee-120">**At least alphanumeric**</span></span>
  -   <span data-ttu-id="035ee-121">**英数字と記号**</span><span class="sxs-lookup"><span data-stu-id="035ee-121">**Alphanumeric with symbols**</span></span>

- <span data-ttu-id="035ee-122">**デバイスの画面がロックされるまでの非アクティブな時間 (分):** ユーザーがパスワードを再入力しなければならなくなるまでのアイドル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="035ee-122">**Minutes of inactivity before password is required:**  Specify the idle time before the user must re-enter their password.</span></span>

- <span data-ttu-id="035ee-123">**パスワードの有効期限 (日数)**: 新しいパスワードの作成が必要となるまでのユーザーのパスワードの有効日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="035ee-123">**Password expiration (days)**: Select the number of days before the user’s password expires and they must create a new one.</span></span>

- <span data-ttu-id="035ee-124">**パスワードの履歴を記憶する**: この設定を **[前のパスワードの再利用を防止]** と共に使用することで、以前使用されていたパスワードをユーザーが作成することを制限します。</span><span class="sxs-lookup"><span data-stu-id="035ee-124">**Remember password history**: Use this setting together with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>

- <span data-ttu-id="035ee-125">**前のパスワードの再利用を防止:** 再利用できない、以前に使用されていたパスワードの数を指定します (**[パスワードの履歴を保存する]** が選択されている場合)。</span><span class="sxs-lookup"><span data-stu-id="035ee-125">**Prevent reuse of previous passwords:** Specify the number of previously used passwords that cannot be re-used (if **Remember password history** is selected).</span></span>

- <span data-ttu-id="035ee-126">**デバイスがアイドル状態から戻るときにパスワードを必須とする**: **[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="035ee-126">**Require a password when the device returns from an idle state:** Use together with the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="035ee-127">ユーザーは、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定で指定された時間非アクティブの状態が続いたデバイスにアクセスしようとすると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="035ee-127">Users are prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <a name="encryption"></a><span data-ttu-id="035ee-128">暗号化</span><span class="sxs-lookup"><span data-stu-id="035ee-128">Encryption</span></span>
- <span data-ttu-id="035ee-129">**モバイル デバイスで暗号化を必要とする**: リソースに接続するためにデバイスの暗号化を必要とする場合は、**[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="035ee-129">**Require encryption on mobile device:** Set this to **Yes** to require devices to be encrypted to be able connect to resources.</span></span> <span data-ttu-id="035ee-130">**[モバイル デバイスのロック解除にパスワードを必要とする]** 設定を構成すると、デバイスは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="035ee-130">Devices are encrypted when you configure the setting **Require a password to unlock mobile devices**.</span></span>

## <a name="device-health-and-security-settings"></a><span data-ttu-id="035ee-131">デバイスの正常性とセキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="035ee-131">Device health and security settings</span></span>

- <span data-ttu-id="035ee-132">**デバイスの脱獄または root 化を認めない**: この設定を有効にした場合、脱獄デバイスは非準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="035ee-132">**Device must not be jailbroken or rooted:** If you enable this setting, jailbroken devices are evaluated as noncompliant.</span></span>
- <span data-ttu-id="035ee-133">**デバイスが提供元不明のアプリのインストールを禁止する必要がある (Android 4.0 以降)**: **[セキュリティ] > [提供元不明のアプリ]** が有効になっているデバイスをブロックするには、この設定を有効にして **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="035ee-133">**Require that devices prevent installation of apps from unknown sources (Android 4.0 or later)**: To block devices that have **Security > Unknown sources** enabled on the device, enable this setting and set it to **Yes**.</span></span>  

>[!IMPORTANT]
>サイドローディング アプリケーションでは **[提供元不明のアプリ]** の設定を有効にする必要があります。 デバイスで Android アプリをサイドローディングしていない場合のみ、このコンプライアンス ポリシーを適用します。

- <span data-ttu-id="035ee-136">**USB のデバッグが無効になっている必要がある (Android 4.2 以降)**: デバイス上の USB のデバッグ オプションの検出が有効になっているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="035ee-136">**Require that USB debugging is  disabled (Android 4.2 or later)**: Specify whether to detect if the USB debugging option on the device is enabled.</span></span>
- <span data-ttu-id="035ee-137">**デバイスがセキュリティ上の脅威を検出するためにデバイスのスキャンを有効にしている必要がある (Android 4.2 ～ 4.4)**: デバイスで **[アプリの確認]** 機能を有効にすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="035ee-137">**Require devices have enabled Scan device for security threats (Android 4.2-4.4)**: Specify that the **Verify apps** feature is enabled on the device.</span></span>
- <span data-ttu-id="035ee-138">**Android のセキュリティ修正プログラムの最小レベル (Android 6.0 以降)**: Android の修正プログラムの最小レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="035ee-138">**Minimum Android security patch level (Android 6.0 or later)**: Specify the minimum Android patch level.</span></span>  <span data-ttu-id="035ee-139">修正プログラムがこのレベルに達していないデバイスは非対応になります。</span><span class="sxs-lookup"><span data-stu-id="035ee-139">Devices that are not at least at this patch level will be noncompliant.</span></span> <span data-ttu-id="035ee-140">日付は YYYY-MM-DD の形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="035ee-140">The date must be specified in this format: YYYY-MM-DD.</span></span>
- <span data-ttu-id="035ee-141">**デバイス脅威保護を有効にすることを必須とする**: この設定は、Lookout MTP ソリューションからのリスク評価をコンプライアンスの条件とする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="035ee-141">**Require device threat protection to be enabled**: Use this setting to take the risk assessment from the Lookout MTP solution as a condition for compliance.</span></span> <span data-ttu-id="035ee-142">最大許容脅威レベルとして次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="035ee-142">Select the maximum allowed threat level, which is one of the following:</span></span>

  - <span data-ttu-id="035ee-143">**[なし (セキュリティ保護)]**: これはセキュリティ上最も安全です。</span><span class="sxs-lookup"><span data-stu-id="035ee-143">**None (secured)** This is the most secure.</span></span> <span data-ttu-id="035ee-144">デバイスにはいかなる脅威も存在できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="035ee-144">This means that the device cannot have any threats.</span></span> <span data-ttu-id="035ee-145">デバイスで何らかの脅威が検出された場合、非準拠と評価されます。</span><span class="sxs-lookup"><span data-stu-id="035ee-145">If the device is detected as having any threats, it is evaluated as noncompliant.</span></span>
  - <span data-ttu-id="035ee-146">**[低]**: 存在する脅威が低レベルの場合のみ、デバイスは準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="035ee-146">**Low:** The device is evaluated as compliant if only low-level threats are present.</span></span> <span data-ttu-id="035ee-147">低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。</span><span class="sxs-lookup"><span data-stu-id="035ee-147">Anything higher puts the device in noncompliant status.</span></span>
  - <span data-ttu-id="035ee-148">**[中]**: デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="035ee-148">**Medium:** The device is evaluated as compliant if the threats that are present on the device are low- or medium-level.</span></span> <span data-ttu-id="035ee-149">デバイスで高レベルの脅威が検出された場合は、非準拠と判定されます。</span><span class="sxs-lookup"><span data-stu-id="035ee-149">If high-level threats are detected on the device, it is determined to be noncompliant.</span></span>
  - <span data-ttu-id="035ee-150">**[高]**: 最も安全性の低い状態です。</span><span class="sxs-lookup"><span data-stu-id="035ee-150">**High:** This is the least secure.</span></span> <span data-ttu-id="035ee-151">基本的にすべての脅威レベルが許容されるため、通常、このソリューションはレポートを目的とした場合にのみ役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="035ee-151">Essentially this allows all threat levels, which is perhaps only useful if you using this solution only for reporting purposes.</span></span>

  <span data-ttu-id="035ee-152">詳細については、「[Intune での Lookout デバイス コンプライアンス ポリシーの作成](create-lookout-device-compliance-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="035ee-152">For more details, see [Create Lookout device compliance policy](create-lookout-device-compliance-policy.md).</span></span>

## <a name="device-property-settings"></a><span data-ttu-id="035ee-153">デバイスのプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="035ee-153">Device property settings</span></span>

- <span data-ttu-id="035ee-154">**必要な最小 OS バージョン**: デバイスが最小 OS バージョンの要件を満たしていない場合、非準拠として報告されます。</span><span class="sxs-lookup"><span data-stu-id="035ee-154">**Minimum OS required:** When  a device doesn't meet the minimum OS version requirement, it is reported as noncompliant.</span></span>
  <span data-ttu-id="035ee-155">アップグレード方法に関する情報のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="035ee-155">A link with information about how to upgrade is displayed.</span></span> <span data-ttu-id="035ee-156">ユーザーは、デバイスのアップグレードを行うことを選択できます。アップグレード後は、会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="035ee-156">The user can choose to upgrade their device, after which they can access company resources.</span></span>

- <span data-ttu-id="035ee-157">**許可される最大 OS バージョン**: ルールに指定された OS バージョンより新しいバージョンの OS がデバイスで使用されている場合、会社のリソースへのアクセスがブロックされ、IT 管理者に問い合わせることをユーザーに促すメッセージが表示されます。対象の OS バージョンを許可するようにルールが変更されるまで、このデバイスを使用して会社のリソースへのアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="035ee-157">**Maximum OS version allowed:** When a device is using an OS version that's later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until the rule changes to allow the OS version, this device cannot be used to access company resources.</span></span>
