---
title: "Microsoft Intune でデバイスを保護する"
description: "不正アクセスなどの脅威からのデバイス保護に Intune が役立つ方法のいくつかについて説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 946f925fa6e5f9a6003fb911c4b283d7497bf279
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="protect-devices-with-microsoft-intune"></a><span data-ttu-id="ff6d4-103">Microsoft Intune でデバイスを保護する</span><span class="sxs-lookup"><span data-stu-id="ff6d4-103">Protect devices with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ff6d4-104">Microsoft Intune では、管理するデバイスを保護するための機能とそれらのデバイスに格納されたデータをセットで提供します。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-104">Microsoft Intune offers a full set of capabilities to help you protect the devices you manage, and the data stored on those devices.</span></span> <span data-ttu-id="ff6d4-105">このトピックではこれらの機能の基本とその詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-105">Read this topic to learn the basics of these capabilities and to find out how to learn more.</span></span>

## <a name="general-ways-to-protect-all-devices"></a><span data-ttu-id="ff6d4-106">すべてのデバイスを保護する一般的な方法</span><span class="sxs-lookup"><span data-stu-id="ff6d4-106">General ways to protect all devices</span></span>

### <a name="device-configuration"></a><span data-ttu-id="ff6d4-107">デバイス構成</span><span class="sxs-lookup"><span data-stu-id="ff6d4-107">Device configuration</span></span>
<span data-ttu-id="ff6d4-108">Intune [構成ポリシー](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)は、さまざまな設定と機能を制御することでデバイスを保護および構成する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-108">Intune [configuration policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md), help you protect and configure devices by controlling a multitude of settings and features.</span></span> <span data-ttu-id="ff6d4-109">たとえば、</span><span class="sxs-lookup"><span data-stu-id="ff6d4-109">For example:</span></span>
- <span data-ttu-id="ff6d4-110">カメラや Bluetooth などのデバイス上のハードウェア機能の使用を制限できます。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-110">You can restrict use of hardware features on the device such as the camera, or Bluetooth.</span></span>
- <span data-ttu-id="ff6d4-111">準拠アプリと非準拠アプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-111">You can configure compliant and noncompliant apps.</span></span> <span data-ttu-id="ff6d4-112">非準拠アプリがインストールされている場合に警告します (一部のプラットフォームでは、インストールを実際にブロックできます)。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-112">You will be alerted if a noncompliant app is installed (and some platforms can actually block the install).</span></span>

### <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a><span data-ttu-id="ff6d4-113">ユーザーがデバイスからロックアウトされるときにパスコードをリセットする</span><span class="sxs-lookup"><span data-stu-id="ff6d4-113">Reset passcodes when users are locked out of their devices</span></span>
<span data-ttu-id="ff6d4-114">モバイル デバイス上の会社のデータを保護するには、まず、デバイスを使用するためのパスコードが必要になるため、場合によっては、[パスコードをリセットする](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)か、従業員がパスコードをリセットできるようにする必要があります。そのためには、パスコードを削除するか、リモートで一時パスコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-114">Since the first step in protecting company data on mobile devices is to require a passcode to use the device, sometimes you have to [reset a passcode](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) or help an employee do so, either by removing the passcode or setting a temporary passcode remotely.</span></span> <span data-ttu-id="ff6d4-115">デバイスをなくしたか、盗難に遭った場合、[デバイスをリモート ロック](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-115">You can also [lock a device remotely](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) if it is lost or stolen.</span></span>

### <a name="retire-devices-and-remove-data"></a><span data-ttu-id="ff6d4-116">デバイスを削除して、データを削除する</span><span class="sxs-lookup"><span data-stu-id="ff6d4-116">Retire devices and remove data</span></span>
<span data-ttu-id="ff6d4-117">デバイスを [Intune 管理対象から削除](retire-devices-from-microsoft-intune-management.md)する必要がある場合に (ユーザーが退職する、またはデバイスが紛失や盗難にあった場合など)、そのデバイスからデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-117">When a device needs to be [removed from Intune management](retire-devices-from-microsoft-intune-management.md) (for example, a user leaves, or the device is lost or stolen), it's likely that you will want to remove data from that device.</span></span> <span data-ttu-id="ff6d4-118">Intune は、企業データの安全を確保するさまざまな方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-118">Intune provides a range of methods to ensure your company data remains secure.</span></span>

### <a name="require-devices-to-be-compliant"></a><span data-ttu-id="ff6d4-119">準拠デバイスである必要がある</span><span class="sxs-lookup"><span data-stu-id="ff6d4-119">Require devices to be compliant</span></span>
<span data-ttu-id="ff6d4-120">Intune は [デバイス コンプライアンス ポリシー](introduction-to-device-compliance-policies-in-microsoft-intune.md) を特徴としているため、指定する規則に準拠していないデバイスを評価 (場合によっては修復) できます。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-120">Intune features [device compliance policies](introduction-to-device-compliance-policies-in-microsoft-intune.md) that let you evaluate (and in some cases remediate) devices that are not compliant with rules you specify.</span></span> <span data-ttu-id="ff6d4-121">たとえば、脱獄している iOS デバイスや、デバイスが暗号化されているかどうか、または正常性証明書サービスによって Windows 10 デバイスを正常と報告するかどうかについて報告できます。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-121">For example, you can report about iOS devices that are jailbroken, whether devices are encrypted, or whether Windows 10 devices are reported as healthy by the Health Attestation Service.</span></span>

### <a name="protect-apps-and-the-data-they-use"></a><span data-ttu-id="ff6d4-122">アプリと使用しているデータを保護する</span><span class="sxs-lookup"><span data-stu-id="ff6d4-122">Protect apps and the data they use</span></span>
<span data-ttu-id="ff6d4-123">Intune では、アプリとそのデータを保護するのに役立つ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-123">Intune gives you a range of features to help you protect apps and their data.</span></span> <span data-ttu-id="ff6d4-124">たとえば、モバイル アプリケーション管理 (MAM) ポリシーが、保護されているアプリからデータをバックアップされないようにし、他のアプリへのコピーや貼り付けを制限し、アプリへのアクセスに暗証番号 (PIN) を要求します。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-124">For example, mobile application management (MAM) policies can prevent data from being backed up from a protected app, restrict copy and paste to other apps, require a PIN to access an app, and more.</span></span> <span data-ttu-id="ff6d4-125">アプリの保護の詳細については、「[Microsoft Intune でアプリとデータを保護する](protect-apps-and-data-with-microsoft-intune.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-125">For more details about protecting apps, see [Protect apps and data with Microsoft Intune](protect-apps-and-data-with-microsoft-intune.md)</span></span>

### <a name="add-an-additional-layer-of-protection-to-devices"></a><span data-ttu-id="ff6d4-126">デバイスに保護層を追加する</span><span class="sxs-lookup"><span data-stu-id="ff6d4-126">Add an additional layer of protection to devices</span></span>
<span data-ttu-id="ff6d4-127">[多要素認証 (MFA)](multi-factor-authentication-azure-active-directory.md) は、ネットワーク上のデバイスのユーザーを認証するより安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-127">[Multi-factor authentication (MFA)](multi-factor-authentication-azure-active-directory.md) is a more secure way of authenticating the users of devices on the network.</span></span>  <span data-ttu-id="ff6d4-128">MFA を使用すると、ユーザーは、ユーザー名とパスワード以外に、電話やテキスト メッセージを使用して本人であることを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-128">With MFA, users need to confirm their identity beyond user name and password, through a phone call, or text message.</span></span>

## <a name="further-capabilities-for-windows-devices"></a><span data-ttu-id="ff6d4-129">Windows デバイスの他の機能</span><span class="sxs-lookup"><span data-stu-id="ff6d4-129">Further capabilities for Windows devices</span></span>

### <a name="control-windows-hello-for-business-settings-on-windows-devices"></a><span data-ttu-id="ff6d4-130">Windows デバイスで Windows Hello for Business の設定を制御する</span><span class="sxs-lookup"><span data-stu-id="ff6d4-130">Control Windows Hello for Business settings on Windows devices</span></span>
<span data-ttu-id="ff6d4-131">Intune は、[Windows Hello for Business](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (旧 Microsoft Passport) と統合でき、パスワード、スマート カード、または仮想スマート カードの代わりに Active Directory または Azure Active Directory アカウントを使った Windows 10 以降の代替サインイン方法です。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-131">Intune lets you integrate with [Windows Hello for Business](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (formerly Microsoft Passport) which is an alternative sign-in method for Windows 10 and later that uses Active Directory, or an Azure Active Directory account to replace a password, smart card, or virtual smart card.</span></span>

## <a name="further-capabilities-for-ios-devices"></a><span data-ttu-id="ff6d4-132">iOS デバイスの他の機能</span><span class="sxs-lookup"><span data-stu-id="ff6d4-132">Further capabilities for iOS devices</span></span>

### <a name="bypass-activation-lock-on-ios-devices"></a><span data-ttu-id="ff6d4-133">iOS デバイスのアクティブ化ロックをバイパスする</span><span class="sxs-lookup"><span data-stu-id="ff6d4-133">Bypass Activation Lock on iOS devices</span></span>
<span data-ttu-id="ff6d4-134">アクティブ化ロックは、デバイスを消去または再アクティブ化する前に、Apple ID とパスワードの入力を要求することでユーザー デバイスを保護するのに役立つ機能です。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-134">Activation Lock is a feature that help protect users' devices by requiring their Apple ID and password to be entered before anyone can erase, or reactivate the device.</span></span> <span data-ttu-id="ff6d4-135">ただし、これが問題につながる場合があります。たとえば、ユーザーがロックを解除しないまま会社を退職した場合です。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-135">However, this can lead to problems, for example if the user leaves the company without removing the lock.</span></span> <span data-ttu-id="ff6d4-136">[iOS のアクティベーション ロックのバイパス](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md)は、監視下 iOS デバイスのロックを解除して、デバイスを再割り当てしたり、消去したりできるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-136">[iOS Activation Lock bypass](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) can help by removing the lock from supervised iOS devices allowing you to reallocate, or erase them.</span></span>



## <a name="protect-windows-pcs-managed-with-the-intune-client"></a><span data-ttu-id="ff6d4-137">Intune クライアントで管理されている Windows PC を保護する</span><span class="sxs-lookup"><span data-stu-id="ff6d4-137">Protect Windows PCs managed with the Intune client</span></span>
<span data-ttu-id="ff6d4-138">Intune は引き続き、ユーザーは登録しないが、Intune コンピューター クライアント ソフトウェアで管理する Windows PC のセキュリティ ポリシーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-138">Intune continues to support security policies for Windows PCs that you don't enroll, but manage with the Intune computer client software.</span></span> <span data-ttu-id="ff6d4-139">これらのポリシーで Windows PC をセキュリティ保護する方法については、「[Use policies to help protect Windows PCs that run the Intune client software (Intune クライアント ソフトウェアを搭載した Windows PC の保護に有用なポリシーを使用する)](policies-to-protect-windows-pcs-in-microsoft-intune.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-139">To find out how these policies can help you secure your Windows PCs, see [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md).</span></span>
