---
title: "Windows Hello for Business を使用する方法"
titleSuffix: Azure portal
description: "管理されたデバイスで Windows Hello for Business の使用を制御するポリシーを作成する方法について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 541be8b8-8668-41be-afce-3f3e08c12191
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01300ac9532d74921de48987678b984a99a7abc8
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-windows-hello-for-business"></a><span data-ttu-id="fff00-103">Windows Hello for Business を使用する</span><span class="sxs-lookup"><span data-stu-id="fff00-103">Use Windows Hello for Business</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="fff00-104">Windows Hello for Business （旧称 Microsoft Passport for Work） と Microsoft Intune を統合できます。Windows Hello for Business は Active Directory や Azure Active Directory アカウントを使った代替サインイン方法であり、パスワード、スマート カード、または仮想スマート カードに置き換わるものです。</span><span class="sxs-lookup"><span data-stu-id="fff00-104">Microsoft Intune integrates with Windows Hello for Business (formerly Microsoft Passport for Work), an alternative sign-in method that uses Active Directory or an Azure Active Directory account to replace a password, smart card, or a virtual smart card.</span></span>

<span data-ttu-id="fff00-105">Hello for Business を使用すると、パスワードの代わりに*ユーザー ジェスチャ*を使用してサインインできます。</span><span class="sxs-lookup"><span data-stu-id="fff00-105">Hello for Business lets you use a *user gesture* to sign in, instead of a password.</span></span> <span data-ttu-id="fff00-106">ユーザー ジェスチャには、単純な暗証番号 (PIN)、Windows Hello などの生体認証、または指紋リーダーなどの外部のデバイスがあります。</span><span class="sxs-lookup"><span data-stu-id="fff00-106">A user gesture might be a simple PIN, biometric authentication such as Windows Hello, or an external device such as a fingerprint reader.</span></span>

<span data-ttu-id="fff00-107">Intune と Hello for Business の統合には 2 通りの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fff00-107">Intune integrates with Hello for Business in two ways:</span></span>

-   <span data-ttu-id="fff00-108">Intune ポリシーを使って、ユーザーがサインインに使用できるジェスチャと使用できないジェスチャを制御できます。</span><span class="sxs-lookup"><span data-stu-id="fff00-108">You can use an Intune policy to control which gestures users can and cannot use to sign in.</span></span>

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> <span data-ttu-id="fff00-109">Anniversary Update バージョンより前の Windows 10 のデスクトップおよびモバイルでは、リソースの認証に使用可能な 2 つの異なる PIN を設定することができました。</span><span class="sxs-lookup"><span data-stu-id="fff00-109">In Windows 10 desktop and mobile versions prior to the Anniversary Update, you could set two different PINS that could be used to authenticate to resources:</span></span>
> - <span data-ttu-id="fff00-110">**デバイス PIN**: デバイスのロック解除とクラウド リソースへの接続に使用できました。</span><span class="sxs-lookup"><span data-stu-id="fff00-110">The **device PIN** could be used to unlock the device and connect to cloud resources.</span></span>
> - <span data-ttu-id="fff00-111">**勤務先 PIN**: ユーザーの個人用デバイス (BYOD) 上の Azure AD リソースへのアクセスに使用されていました。</span><span class="sxs-lookup"><span data-stu-id="fff00-111">The **work PIN** was used to access Azure AD resources on user’s personal devices (BYOD).</span></span>
> 
> <span data-ttu-id="fff00-112">Anniversary Update では、これら 2 つの PIN が 1 つのデバイス PIN にまとめられました。</span><span class="sxs-lookup"><span data-stu-id="fff00-112">In the Anniversary Update, these two PINS were merged into one single device PIN.</span></span>
> <span data-ttu-id="fff00-113">デバイス PIN の制御用に設定済みの Intune の構成ポリシー、さらに構成済みの Windows Hello for Business ポリシーの両方により、この新しい PIN の値が設定されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fff00-113">Any Intune configuration policies you set to control the device PIN, and additionally, any Windows Hello for Business policies you configured, now both set this new PIN value.</span></span>
> <span data-ttu-id="fff00-114">両方の種類のポリシーをデバイス PIN の制御用に設定している場合、Windows Hello for Business が Windows 10 デスクトップおよびモバイル デバイスの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fff00-114">If you have set both policy types to control the PIN, the Windows Hello for Business policy will be applied on both Windows 10 desktop and mobile devices.</span></span>
> <span data-ttu-id="fff00-115">ポリシーの競合を解消して PIN ポリシーが適切に適用されるようにするために、構成ポリシーの設定に合わせて Windows Hello for Business ポリシーを更新し、ユーザーにポータル サイト アプリでデバイスを同期するように伝えてください。</span><span class="sxs-lookup"><span data-stu-id="fff00-115">To ensure policy conflicts are resolved and that the PIN policy is applied correctly, update your Windows Hello for Business Policy to match the settings in your configuration policy, and ask your users to sync their devices in the Company Portal app.</span></span>



## <a name="create-a-windows-hello-for-business-policy"></a><span data-ttu-id="fff00-116">Windows Hello for Business のポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="fff00-116">Create a Windows Hello for Business policy</span></span>

1. <span data-ttu-id="fff00-117">Azure Portal で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-117">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2. <span data-ttu-id="fff00-118">[Intune] ブレードで **[デバイスの登録]** を選択してから、**[管理]** > **[Windows Hello for Business]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-118">On the Intune blade, choose **Enroll devices**, and then choose **Manage** > **Windows Hello for Business**.</span></span>

3. <span data-ttu-id="fff00-119">開いたブレードで、**[既定]** 設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-119">On the blade that opens, choose the **Default** settings.</span></span>

4. <span data-ttu-id="fff00-120">**[すべてのユーザー]** ブレードで、**[プロパティ]** をクリックし、Windows Hello for Business 設定の**名前**と省略可能な**説明**を入力します。</span><span class="sxs-lookup"><span data-stu-id="fff00-120">On the **All Users** blade, click **Properties** and then enter a **Name** and optional **Description** for the Windows Hello for Business settings.</span></span>

5. <span data-ttu-id="fff00-121">**[すべてのユーザー]** ブレードで、**[設定]** をクリックし、**[Windows Hello for Business の構成]** で以下を選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-121">On the **All Users** blade, click **Settings** and then choose from the following for **Configure Windows Hello for Business**:</span></span>

    - <span data-ttu-id="fff00-122">**Disabled**。</span><span class="sxs-lookup"><span data-stu-id="fff00-122">**Disabled**.</span></span> <span data-ttu-id="fff00-123">Windows Hello for Business を使用しない場合は、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-123">If you don't want to use Windows Hello for Business, select this setting.</span></span> <span data-ttu-id="fff00-124">画面上の他のすべての設定が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="fff00-124">All other settings on the screen are then unavailable.</span></span>
    - <span data-ttu-id="fff00-125">**Enabled**。</span><span class="sxs-lookup"><span data-stu-id="fff00-125">**Enabled**.</span></span> <span data-ttu-id="fff00-126">Windows Hello for Business の設定を構成する場合は、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-126">Select this setting if you want to configure Windows Hello for Business settings.</span></span>
    - <span data-ttu-id="fff00-127">**[Not configured]** (未構成)。</span><span class="sxs-lookup"><span data-stu-id="fff00-127">**Not configured**.</span></span> <span data-ttu-id="fff00-128">Windows Hello for Business の設定の制御に Intune を使用しない場合は、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-128">Select this setting if you don't want to use Intune to control Windows Hello for Business settings.</span></span> <span data-ttu-id="fff00-129">Windows 10 デバイス上の既存の Windows Hello for Business の設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="fff00-129">Any existing Windows Hello for Business settings on Windows 10 devices will not be changed.</span></span> <span data-ttu-id="fff00-130">ブレード上の他のすべての設定が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="fff00-130">All other settings on the blade are unavailable.</span></span>

6. <span data-ttu-id="fff00-131">前の手順で **[有効]** を選択した場合は、すべての登録済みの Windows 10 デバイスと Windows 10 モバイル デバイスに適用される必須設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fff00-131">If you selected **Enabled** in the previous step, configure the required settings that will be applied to all enrolled Windows 10 and Windows 10 Mobile devices.</span></span>

   - <span data-ttu-id="fff00-132">**[トラステッド プラットフォーム モジュール (TPM) の使用]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-132">**Use a Trusted Platform Module (TPM)**.</span></span> <span data-ttu-id="fff00-133">TPM チップは、追加のデータのセキュリティ層を提供します。</span><span class="sxs-lookup"><span data-stu-id="fff00-133">A TPM chip provides an additional layer of data security.</span></span><br><span data-ttu-id="fff00-134">次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-134">Choose one of the following values:</span></span>

     - <span data-ttu-id="fff00-135">**[必須]** (既定)。</span><span class="sxs-lookup"><span data-stu-id="fff00-135">**Required** (default).</span></span> <span data-ttu-id="fff00-136">アクセス可能な TPM を装備したデバイスのみが Windows Hello for Business をプロビジョニングできます。</span><span class="sxs-lookup"><span data-stu-id="fff00-136">Only devices with an accessible TPM can provision Windows Hello for Business.</span></span>
     - <span data-ttu-id="fff00-137">**[優先]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-137">**Preferred**.</span></span> <span data-ttu-id="fff00-138">デバイスは最初に TPM を使用しようとします。</span><span class="sxs-lookup"><span data-stu-id="fff00-138">Devices first attempt to use a TPM.</span></span> <span data-ttu-id="fff00-139">これが使用できない場合、ソフトウェアの暗号化を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fff00-139">If this is not available, they can use software encryption.</span></span>

   - <span data-ttu-id="fff00-140">**[最小 PIN サイズを必要とする]**/**[最大 PIN サイズを必要とする]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-140">**Require minimum PIN length**/**Require maximum PIN length**.</span></span> <span data-ttu-id="fff00-141">サインインをセキュリティで保護するために指定する PIN の最小長と最大長を使用するようにデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="fff00-141">Configures devices to use the minimum and maximum PIN lengths that you specify to help ensure secure sign-in.</span></span> <span data-ttu-id="fff00-142">既定の PIN の長さは 6 文字ですが、最小長を 4 文字にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fff00-142">The default PIN length is 6 characters, but you can enforce a minimum length of 4 characters.</span></span> <span data-ttu-id="fff00-143">PIN の最大長は 127 文字です。</span><span class="sxs-lookup"><span data-stu-id="fff00-143">The maximum PIN length is 127 characters.</span></span>

   - <span data-ttu-id="fff00-144">**[PIN での小文字の使用を必要とする]**/**[PIN での大文字の使用を必要とする]**/**[Require special characters in PIN]** (PIN での特殊文字の使用を必要とする)。</span><span class="sxs-lookup"><span data-stu-id="fff00-144">**Require lowercase letters in PIN**/**Require uppercase letters in PIN**/**Require special characters in PIN**.</span></span> <span data-ttu-id="fff00-145">大文字、小文字、特殊文字を PIN で使用するように要求することで、PIN をより強力にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fff00-145">You can enforce a stronger PIN by requiring the use of uppercase letters, lowercase letters, and special characters in the PIN.</span></span> <span data-ttu-id="fff00-146">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-146">Choose from:</span></span>

     - <span data-ttu-id="fff00-147">**[許可]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-147">**Allowed**.</span></span> <span data-ttu-id="fff00-148">ユーザーは PIN で文字を使用できますが、使用は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="fff00-148">Users can use the character type in their PIN, but it is not mandatory.</span></span>
    
     - <span data-ttu-id="fff00-149">**[必須]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-149">**Required**.</span></span> <span data-ttu-id="fff00-150">ユーザーは PIN に文字を 1 文字以上含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fff00-150">Users must include at least one of the character types in their PIN.</span></span> <span data-ttu-id="fff00-151">たとえば、一般的なのは、少なくとも 1 つの大文字と 1 つの特殊文字の使用を要求する方法です。</span><span class="sxs-lookup"><span data-stu-id="fff00-151">For example, it's common practice to require at least one uppercase letter and one special character.</span></span>

     - <span data-ttu-id="fff00-152">**[許可しない]** (既定)。</span><span class="sxs-lookup"><span data-stu-id="fff00-152">**Not allowed** (default).</span></span> <span data-ttu-id="fff00-153">ユーザーは、これらの文字を PIN で使用することができません </span><span class="sxs-lookup"><span data-stu-id="fff00-153">Users must not use these character types in their PIN.</span></span> <span data-ttu-id="fff00-154">(これは、この設定を構成していない場合の動作でもあります)。</span><span class="sxs-lookup"><span data-stu-id="fff00-154">(This is also the behavior if the setting is not configured.)</span></span><br><span data-ttu-id="fff00-155">特殊文字には次のものが含まれます。**! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**</span><span class="sxs-lookup"><span data-stu-id="fff00-155">Special characters include: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**</span></span>

   - <span data-ttu-id="fff00-156">**[PIN の有効期間 (日)]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-156">**PIN expiration (days)**.</span></span> <span data-ttu-id="fff00-157">その期間が経過したらユーザーが PIN を変更する必要がある有効期間を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fff00-157">It's a good practice to specify an expiration period for a PIN, after which users must change it.</span></span> <span data-ttu-id="fff00-158">既定は 41 日です。</span><span class="sxs-lookup"><span data-stu-id="fff00-158">The default is 41 days.</span></span>

   - <span data-ttu-id="fff00-159">**[PIN の履歴を保存]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-159">**Remember PIN history**.</span></span> <span data-ttu-id="fff00-160">以前に使用した PIN の再利用を制限します。</span><span class="sxs-lookup"><span data-stu-id="fff00-160">Restricts the reuse of previously used PINs.</span></span> <span data-ttu-id="fff00-161">既定では、直近 5 回の PIN を再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fff00-161">By default, the last 5 PINs cannot be reused.</span></span>

   - <span data-ttu-id="fff00-162">**[生体認証を許可]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-162">**Allow biometric authentication**.</span></span> <span data-ttu-id="fff00-163">Windows Hello for Business の PIN の代わりとして、顔認識や指紋などの生体認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fff00-163">Enables biometric authentication, such as facial recognition or fingerprint, as an alternative to a PIN for Windows Hello for Business.</span></span> <span data-ttu-id="fff00-164">ユーザーは、生体認証に失敗した場合のために、Work の PIN も設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fff00-164">Users must still configure a work PIN in case biometric authentication fails.</span></span> <span data-ttu-id="fff00-165">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="fff00-165">Choose from:</span></span>

     - <span data-ttu-id="fff00-166">**[はい]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-166">**Yes**.</span></span> <span data-ttu-id="fff00-167">Windows Hello for Business で生体認証が使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="fff00-167">Windows Hello for Business allows biometric authentication.</span></span>
     - <span data-ttu-id="fff00-168">**[いいえ]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-168">**No**.</span></span> <span data-ttu-id="fff00-169">Windows Hello for Business で生体認証を利用できません (すべてのアカウントの種類が対象)。</span><span class="sxs-lookup"><span data-stu-id="fff00-169">Windows Hello for Business prevents biometric authentication (for all account types).</span></span>

   - <span data-ttu-id="fff00-170">**[拡張スプーフィング対策が使用可能な場合は使用する]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-170">**Use enhanced anti-spoofing, when available**.</span></span> <span data-ttu-id="fff00-171">Windows Hello のスプーフィング対策機能 (例: 実際の顔の代わりに写真の顔を検出する) をサポートしているデバイスで、その機能を使用するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="fff00-171">Configures whether the anti-spoofing features of Windows Hello are used on devices that support it (for example, detecting a photograph of a face instead of a real face).</span></span><br><span data-ttu-id="fff00-172">**[はい]** に設定されている場合、Windows のすべてのユーザーは、サポートされている場合に顔の特徴のスプーフィング対策を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fff00-172">If this is set to **Yes**, Windows requires all users to use anti-spoofing for facial features when that is supported.</span></span>

   - <span data-ttu-id="fff00-173">**[電話によるサインインの使用]**。</span><span class="sxs-lookup"><span data-stu-id="fff00-173">**Use phone sign-in**.</span></span> <span data-ttu-id="fff00-174">このオプションが **[はい]** に設定されている場合、ユーザーはデスクトップ コンピューターの認証にポータブル コンパニオン デバイスとして機能するリモートの Passport を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fff00-174">If this option is set to **Yes**, users can use a remote passport to serve as a portable companion device for desktop computer authentication.</span></span> <span data-ttu-id="fff00-175">デスクトップ コンピューターは Azure Active Directory に参加している必要があり、コンパニオン デバイスでは Windows Hello for Business の PIN を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fff00-175">The desktop computer must be Azure Active Directory joined, and the companion device must be configured with a Windows Hello for Business PIN.</span></span>


## <a name="further-information"></a><span data-ttu-id="fff00-176">詳細情報</span><span class="sxs-lookup"><span data-stu-id="fff00-176">Further information</span></span>
<span data-ttu-id="fff00-177">Microsoft Passport について詳しくは、Windows 10 ドキュメントの[こちらのガイド](https://technet.microsoft.com/library/mt589441.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fff00-177">For more information about Microsoft Passport, see [the guide](https://technet.microsoft.com/library/mt589441.aspx) in the Windows 10 documentation.</span></span>
