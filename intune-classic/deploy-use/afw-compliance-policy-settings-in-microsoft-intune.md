---
title: "Android for Work のコンプライアンス設定"
description: "このトピックでは、Android for Work と互換性のある Android デバイスのデバイス コンプライアンス ポリシーの設定について説明します。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5c0a5ed4c5a8d5f4020b56c27a4436511eca1663
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a><span data-ttu-id="ee449-103">Microsoft Intune での Android for Work デバイス向けのコンプライアンス ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="ee449-103">Compliance policy settings for Android for Work devices in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ee449-104">このトピックで説明するポリシー設定は、Android for Work デバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ee449-104">The policy settings described in this topic apply to Android for Work devices.</span></span>

<span data-ttu-id="ee449-105">その他のプラットフォームに関する情報を探している場合は、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ee449-105">If you are looking for information about other platforms, select one of the following:</span></span>
> [!div class="op_single_selector"]
> - [Android 向けのコンプライアンス ポリシー設定](android-compliance-policy-settings-in-microsoft-intune.md)
> - [iOS デバイス向けのコンプライアンス ポリシー設定](ios-compliance-policy-settings-in-microsoft-intune.md)
> - [Windows デバイス向けのコンプライアンス ポリシー設定](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a><span data-ttu-id="ee449-109">システム セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="ee449-109">System security settings</span></span>
### <a name="password"></a><span data-ttu-id="ee449-110">パスワード</span><span class="sxs-lookup"><span data-stu-id="ee449-110">Password</span></span>
- <span data-ttu-id="ee449-111">**モバイル デバイスのロック解除にパスワードを必要とする:** デバイスにアクセスするユーザーにパスワードを入力するよう求める場合は、**[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ee449-111">**Require a password to unlock mobile devices:** Set this to **Yes** to require users to enter a password before they can access their device.</span></span>

-  <span data-ttu-id="ee449-112">**パスワードの最小文字数:** ユーザーのパスワードに含まれている必要がある数字または文字の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee449-112">**Minimum password length:** Specify the minimum number of digits or characters that the user’s password must contain.</span></span>

- <span data-ttu-id="ee449-113">**パスワードの品質:** 指定したパスワード要件が、デバイスに構成されているかどうかをこの設定で検出します。</span><span class="sxs-lookup"><span data-stu-id="ee449-113">**Password quality:** This setting detects if the password requirements you specify is configured on the device.</span></span> <span data-ttu-id="ee449-114">この設定を有効にすると、Android デバイスで特定のパスワード要件を構成することが必須になります。</span><span class="sxs-lookup"><span data-stu-id="ee449-114">Enable this setting to require that users configure certain password requirements for Android devices.</span></span> <span data-ttu-id="ee449-115">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="ee449-115">Choose from:</span></span>
  -   <span data-ttu-id="ee449-116">**低レベルのバイオメトリック セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="ee449-116">**Low security biometric**</span></span>
  - <span data-ttu-id="ee449-117">**必須**</span><span class="sxs-lookup"><span data-stu-id="ee449-117">**Required**</span></span>
  -   <span data-ttu-id="ee449-118">**最小数の数字**</span><span class="sxs-lookup"><span data-stu-id="ee449-118">**At least numeric**</span></span>
  -   <span data-ttu-id="ee449-119">**最小数の英字**</span><span class="sxs-lookup"><span data-stu-id="ee449-119">**At least alphabetic**</span></span>
  -   <span data-ttu-id="ee449-120">**最小数の英数字**</span><span class="sxs-lookup"><span data-stu-id="ee449-120">**At least alphanumeric**</span></span>
  -   <span data-ttu-id="ee449-121">**英数字と記号**</span><span class="sxs-lookup"><span data-stu-id="ee449-121">**Alphanumeric with symbols**</span></span>

- <span data-ttu-id="ee449-122">**デバイスの画面がロックされるまでの非アクティブな時間 (分):** ユーザーがパスワードを再入力しなければならなくなるまでのアイドル時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee449-122">**Minutes of inactivity before password is required:**  Specifies the idle time before the user must re-enter their password.</span></span>

- <span data-ttu-id="ee449-123">**パスワードの有効期限 (日数):** 新しいパスワードの作成が必要となるまでのユーザーのパスワードの有効日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee449-123">**Password expiration (days):** Select the number of days before the user’s password expires and they must create a new one.</span></span>

- <span data-ttu-id="ee449-124">**パスワードの履歴を記憶する:** この設定を **[前のパスワードの再利用を防止]** と組み合わせて使用することで、以前使用されていたパスワードをユーザーが作成することを制限します。</span><span class="sxs-lookup"><span data-stu-id="ee449-124">**Remember password history:** Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>

- <span data-ttu-id="ee449-125">**前のパスワードの再利用を防止:** **[パスワードの履歴を保存する]** が選択されている場合は、再利用できない、以前に使用されていたパスワードの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee449-125">**Prevent reuse of previous passwords:** If **Remember password history** is selected, specify the number of previously used passwords that cannot be re-used.</span></span>

- <span data-ttu-id="ee449-126">**デバイスがアイドル状態から戻るときにパスワードを必須とする:** この設定は、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee449-126">**Require a password when the device returns from an idle state:** This setting should be used together with the in the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="ee449-127">エンドユーザーは、**[デバイスの画面がロックされるまでの非アクティブな時間 (分)]** 設定で指定された時間非アクティブの状態が続いたデバイスにアクセスしようとすると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ee449-127">The end-users are prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <a name="encryption"></a><span data-ttu-id="ee449-128">暗号化</span><span class="sxs-lookup"><span data-stu-id="ee449-128">Encryption</span></span>
- <span data-ttu-id="ee449-129">**モバイル デバイスで暗号化を必要とする:** Android for Work デバイスは暗号化が適用されるので、この設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ee449-129">**Require encryption on mobile device:** You don't have to configure this setting since Android for Work devices enforce encryption.</span></span>

## <a name="device-health-and-security-settings"></a><span data-ttu-id="ee449-130">デバイスの正常性とセキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="ee449-130">Device health and security settings</span></span>

- <span data-ttu-id="ee449-131">**デバイスの脱獄または root 化を認めない:** この設定を有効にした場合、脱獄デバイスは非準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="ee449-131">**Device must not be jailbroken or rooted:** If you enable this setting, jailbroken devices will be evaluated as noncompliant.</span></span>
- <span data-ttu-id="ee449-132">**デバイスで提供元不明のアプリのインストールを禁止することを必須にする:** Android for Work デバイスでは、不明なソースからのインストールが常に制限されるので、この設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ee449-132">**Require that devices prevent installation of apps from unknown sources:** You do not have to configure this setting as Android for Work devices always restrict installation from unknown sources.</span></span> <span data-ttu-id="ee449-133">。</span><span class="sxs-lookup"><span data-stu-id="ee449-133">.</span></span>  

- <span data-ttu-id="ee449-134">**USB デバッグの無効化を必須にする**: Android for Work デバイスでは、USB デバッグは無効にされているので、この設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ee449-134">**Require that USB debugging is  disabled**: You do not have to configure this settings as USB debugging is already disabled on Android for Work devices.</span></span>

- <span data-ttu-id="ee449-135">**最低限の Android セキュリティ パッチ レベル**: この設定を使用して、Android の修正プログラムの最小レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee449-135">**Minimum Android security patch level**: Use this setting to specify the minimum Android patch level.</span></span>  <span data-ttu-id="ee449-136">修正プログラムがこのレベルに達していないデバイスは非対応になります。</span><span class="sxs-lookup"><span data-stu-id="ee449-136">Devices that are not at least at this patch level will be noncompliant.</span></span> <span data-ttu-id="ee449-137">日付は YYYY-MM-DD の形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee449-137">The date must be specified the format: YYYY-MM-DD.</span></span>
- <span data-ttu-id="ee449-138">**デバイス脅威保護を有効にすることを必須とする**: この設定は、デバイス脅威保護ソリューションからのリスク評価をコンプライアンスの条件とする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="ee449-138">**Require device threat protection to be enabled**: Use this setting to take the risk assessment from the device threat protection solution as a condition for compliance.</span></span> <span data-ttu-id="ee449-139">最大許容脅威レベルとして次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ee449-139">Select the maximum allowed threat level, which is one of the following:</span></span>

  - <span data-ttu-id="ee449-140">**[なし (セキュリティ保護)]**: これはセキュリティ上最も安全です。</span><span class="sxs-lookup"><span data-stu-id="ee449-140">**None (secured)** This is the most secure.</span></span> <span data-ttu-id="ee449-141">デバイスにはいかなる脅威も存在できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ee449-141">This means that the device cannot have any threats.</span></span> <span data-ttu-id="ee449-142">デバイスで何らかのレベルの脅威が検出された場合、非準拠と評価されます。</span><span class="sxs-lookup"><span data-stu-id="ee449-142">If the device is detected as having any level of threats, it will be evaluated as non-compliant.</span></span>
  - <span data-ttu-id="ee449-143">**[低]**: 存在する脅威が低レベルの場合のみ、デバイスは準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="ee449-143">**Low:** Device is evaluated as compliant if only low level threats are present.</span></span> <span data-ttu-id="ee449-144">低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。</span><span class="sxs-lookup"><span data-stu-id="ee449-144">Anything higher puts the device in a non-compliant status.</span></span>
  - <span data-ttu-id="ee449-145">**[中]**: デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="ee449-145">**Medium:** Device is evaluated as compliant if the threats that are present on the device are low or medium level.</span></span> <span data-ttu-id="ee449-146">デバイスで高レベルの脅威が検出された場合は、非準拠と判定されます。</span><span class="sxs-lookup"><span data-stu-id="ee449-146">If the device is detected to have high level threats, it is determined as non-compliant.</span></span>
  - <span data-ttu-id="ee449-147">**[高]**: 最も安全性の低い状態です。</span><span class="sxs-lookup"><span data-stu-id="ee449-147">**High:** This is the least secure.</span></span> <span data-ttu-id="ee449-148">基本的にすべての脅威レベルが許容されるため、通常、このソリューションはレポートを目的とした場合にのみ役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="ee449-148">Essentially, this allows all threat levels, and perhaps only useful if you using this solution only for reporting purposes.</span></span>

  <span data-ttu-id="ee449-149">詳細については、「[Intune での Lookout デバイス コンプライアンス ポリシーの作成](create-lookout-device-compliance-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee449-149">For more details, see [Create device compliance policy](create-lookout-device-compliance-policy.md).</span></span>

## <a name="device-property-settings"></a><span data-ttu-id="ee449-150">デバイスのプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="ee449-150">Device property settings</span></span>
- <span data-ttu-id="ee449-151">**必要な最小 OS バージョン**: デバイスが最小オペレーティング システム (OS) バージョンの要件を満たしていない場合、非準拠として報告されます。</span><span class="sxs-lookup"><span data-stu-id="ee449-151">**Minimum OS required:** When a device does not meet the minimum operating system (OS) version requirement, it is reported as noncompliant.</span></span>
  <span data-ttu-id="ee449-152">アップグレード方法に関する情報のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee449-152">A link with information on how to upgrade is displayed.</span></span> <span data-ttu-id="ee449-153">エンド ユーザーは、デバイスのアップグレードを行うことを選択できます。アップグレード後は、会社のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ee449-153">The end-user can choose to upgrade their device after which they can access company resources.</span></span>

- <span data-ttu-id="ee449-154">**許可される最大 OS バージョン**: ルールに指定されたものより新しいバージョンのオペレーティング システム (OS) がデバイスで使用されている場合、会社のリソースへのアクセスがブロックされ、IT 管理者に問い合わせることをユーザーに促すメッセージが表示されます。対象のオペレーティング システム バージョンを許可するようにルールが変更されるまで、このデバイスを使用して会社のリソースへのアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ee449-154">**Maximum OS version allowed:** When a device is using an operating system (OS) version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in the rule to allow the operating system version, this device cannot be used to access company resources.</span></span>
