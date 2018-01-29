---
title: "EMS での BYOD に関する技術の決定事項"
description: "BYOD を有効にし、Microsoft Enterprise Mobility + Security で企業のデータを保護するための、技術に関する重要な決定事項です。"
keywords: 
author: 
ms.author: pfetty
manager: angrobe
ms.date: 12/8/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.openlocfilehash: d0823a94273baf578c2d665177fc3df73948b7b0
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="technology-decisions-for-enabling-byod-with-microsoft-enterprise-mobility--security-ems"></a><span data-ttu-id="f6431-103">Microsoft Enterprise Mobility + Security (EMS) で BYOD を有効にするための技術の決定事項</span><span class="sxs-lookup"><span data-stu-id="f6431-103">Technology decisions for enabling BYOD with Microsoft Enterprise Mobility + Security (EMS)</span></span>

<span data-ttu-id="f6431-104">従業員が自分のデバイスを使ってリモートで作業できるようにする戦略を開発するときは (BYOD)、BYOD を有効にして企業データを保護するためのシナリオで重要な決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6431-104">As you develop your strategy to enable employees to work remotely on their own devices (BYOD), you need to make key decisions in the scenarios to enable BYOD and how to protect your corporate data.</span></span> <span data-ttu-id="f6431-105">幸い、EMS では包括的なソリューション セットにおいて必要なすべての機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="f6431-105">Fortunately, EMS offers all of the capabilities you need in a comprehensive set of solutions.</span></span>  

<span data-ttu-id="f6431-106">このトピックでは、企業の電子メールへの BYOD アクセスを有効にする簡単なユース ケースを使って説明します。</span><span class="sxs-lookup"><span data-stu-id="f6431-106">In this topic, we examine the simple use case of enabling BYOD access to corporate email.</span></span> <span data-ttu-id="f6431-107">デバイス全体とアプリケーションだけのどちらを管理する必要があるかに注目します。いずれも完全に有効な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="f6431-107">We’ll focus on whether or not you need to manage the entire device or just the applications, both of which are completely valid choices.</span></span>

## <a name="assumptions"></a><span data-ttu-id="f6431-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="f6431-108">Assumptions</span></span>
* <span data-ttu-id="f6431-109">Azure Active Directory と Microsoft Intune についての基本的な知識があること</span><span class="sxs-lookup"><span data-stu-id="f6431-109">You have basic knowledge of Azure Active Directory and Microsoft Intune</span></span>
* <span data-ttu-id="f6431-110">メール アカウントが Exchange Online でホストされていること</span><span class="sxs-lookup"><span data-stu-id="f6431-110">Your email accounts are hosted in Exchange Online</span></span>

## <a name="common-reasons-to-manage-the-device-mdm"></a><span data-ttu-id="f6431-111">デバイスを管理する場合の一般的な理由 (MDM)</span><span class="sxs-lookup"><span data-stu-id="f6431-111">Common reasons to manage the device (MDM)</span></span>
<span data-ttu-id="f6431-112">Exchange Online に[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) ポリシーを展開することで、デバイス管理へのデバイスの登録をユーザーに簡単に促すことができます。</span><span class="sxs-lookup"><span data-stu-id="f6431-112">You can easily drive users to enroll their devices into device management by deploying a [conditional access](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) policy on Exchange Online.</span></span> <span data-ttu-id="f6431-113">個人デバイスの管理が必要な理由としては次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="f6431-113">Here are the reasons you might want to manage personal devices:</span></span>

<span data-ttu-id="f6431-114">**WiFi/VPN** – ユーザーが生産性を向上させる企業接続プロファイルを必要としている場合は、シームレスに構成できます。</span><span class="sxs-lookup"><span data-stu-id="f6431-114">**WiFi/VPN** – If your users need a corporate connectivity profile to be productive, this can be seamlessly configured.</span></span>

<span data-ttu-id="f6431-115">**アプリケーション** – ユーザーのデバイスにアプリのセットをプッシュする必要がある場合は、シームレスに配信できます。</span><span class="sxs-lookup"><span data-stu-id="f6431-115">**Applications** – If your users need a set of apps to be pushed to their device, these can be seamlessly delivered.</span></span> <span data-ttu-id="f6431-116">これには、Mobile Threat Defense アプリのようなセキュリティのために必要なアプリケーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f6431-116">This includes applications that you might require for security purposes, like a Mobile Threat Defense app.</span></span>

<span data-ttu-id="f6431-117">**コンプライアンス** – 組織によっては、特定の MDM 制御が求められる規制や他のポリシーに準拠することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6431-117">**Compliance** – Some organizations need to comply with regulatory or other policies that call out specific MDM controls.</span></span> <span data-ttu-id="f6431-118">たとえば、MDM では、デバイス全体を暗号化したり、デバイス上のすべてのアプリのレポートを生成したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6431-118">For example, you need MDM to encrypt the entire device or to produce a report of all apps on the device.</span></span>

## <a name="common-reasons-to-only-manage-the-apps-mam"></a><span data-ttu-id="f6431-119">アプリのみを管理する場合の一般的な理由 (MAM)</span><span class="sxs-lookup"><span data-stu-id="f6431-119">Common reasons to only manage the apps (MAM)</span></span>
<span data-ttu-id="f6431-120">MDM を行わない MAM は、BYOD をサポートする組織で非常によく利用されています。</span><span class="sxs-lookup"><span data-stu-id="f6431-120">MAM without MDM is very popular for organizations that support BYOD.</span></span> <span data-ttu-id="f6431-121">Exchange Online に条件付きアクセス ポリシーを展開することで、Outlook Mobile (MAM 保護をサポートします) からメールにアクセスするようユーザーに促すことができます。</span><span class="sxs-lookup"><span data-stu-id="f6431-121">You can drive users to access email from Outlook Mobile (which supports MAM protections) by deploying a conditional access policy om Exchange Online.</span></span> <span data-ttu-id="f6431-122">個人デバイスのアプリのみの管理が必要な理由としては次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="f6431-122">Here are the reasons you might want to only manage apps on personal devices:</span></span>

<span data-ttu-id="f6431-123">**ユーザー エクスペリエンス** – MDM の登録には (プラットフォームにより表示される) 多くの警告プロンプトが伴うため、ユーザーが個人のデバイスでメールにアクセスすることをあきらめるという結論に達してしまうことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="f6431-123">**User experience** – MDM enrollment includes many warning prompts (enforced by the platform) that often result in the user deciding they would rather not access their email on their personal device after all.</span></span> <span data-ttu-id="f6431-124">MAM で表示されるユーザーへの警告はずっと少なく、MAM による保護が適用されていることを伝えるポップアップが 1 回表示されるだけです。</span><span class="sxs-lookup"><span data-stu-id="f6431-124">MAM is much less alarming to users, as they simply get a pop-up one time to let them know MAM protections are in place.</span></span>

<span data-ttu-id="f6431-125">**コンプライアンス** – 組織によっては、個人デバイスでの管理機能を少なくすることを求めるポリシーに準拠することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6431-125">**Compliance** – Some organizations need to comply with policies that require less management capabilities on personal devices.</span></span> <span data-ttu-id="f6431-126">たとえば、MAM ではアプリから企業データを削除することだけができるのに対し、MDM ではデバイスからすべてのデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="f6431-126">For example, MAM is only able to remove corporate data from the apps, as opposed to MDM which is able to remove all data from the device.</span></span>

![モバイル デバイスでのデバイス管理とアプリ管理を比較した図](./media/byod-app-device-mgmt.png)

<span data-ttu-id="f6431-128">詳しくは、[デバイス管理とアプリ管理のライフサイクルに関するページ](introduction-device-app-lifecycles.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6431-128">Learn more about [device management and app management lifecycles](introduction-device-app-lifecycles.md).</span></span>

## <a name="mdm-vs-mam-capability-comparison"></a><span data-ttu-id="f6431-129">MDM と MAM の機能の比較</span><span class="sxs-lookup"><span data-stu-id="f6431-129">MDM vs MAM capability comparison</span></span>
<span data-ttu-id="f6431-130">既に説明したように、条件付きアクセスを使うと、デバイスの登録、または Outlook Mobile などの管理されたアプリの使用を、ユーザーに促すことができます。</span><span class="sxs-lookup"><span data-stu-id="f6431-130">As already mentioned, conditional access can drive a user to enroll their device or use a managed app like Outlook Mobile.</span></span> <span data-ttu-id="f6431-131">いずれの場合も、次のような他の多くの条件を適用できます。</span><span class="sxs-lookup"><span data-stu-id="f6431-131">Many other conditions can be applied in either case, including:</span></span>

* <span data-ttu-id="f6431-132">アクセスを試みているユーザー</span><span class="sxs-lookup"><span data-stu-id="f6431-132">Which user is attempting the access</span></span>
* <span data-ttu-id="f6431-133">信頼できる場所かどうか</span><span class="sxs-lookup"><span data-stu-id="f6431-133">Whether the location is trusted or untrusted</span></span>
*   <span data-ttu-id="f6431-134">サインイン リスク レベル</span><span class="sxs-lookup"><span data-stu-id="f6431-134">Sign-in risk level</span></span>
* <span data-ttu-id="f6431-135">デバイスのプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="f6431-135">Device platform</span></span>

<span data-ttu-id="f6431-136">それでも、多くの組織で心配されている特定のリスクが発生することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="f6431-136">Still, many organizations often have specific risks they’re concerned about.</span></span>  <span data-ttu-id="f6431-137">次の表は、一般的な懸念事項と、それらにする MDM と MAM の対応の比較をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="f6431-137">The table below lists the common concerns and MDM vs MAM response to that concern.</span></span>

| <span data-ttu-id="f6431-138">懸念事項</span><span class="sxs-lookup"><span data-stu-id="f6431-138">Concern</span></span>   |   <span data-ttu-id="f6431-139">MDM</span><span class="sxs-lookup"><span data-stu-id="f6431-139">MDM</span></span>  |   <span data-ttu-id="f6431-140">MAM</span><span class="sxs-lookup"><span data-stu-id="f6431-140">MAM</span></span>  |
|------------|--------|--------|
|<span data-ttu-id="f6431-141">許可されていないデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="f6431-141">Unauthorized data access</span></span> | <span data-ttu-id="f6431-142">グループ メンバーシップを要求</span><span class="sxs-lookup"><span data-stu-id="f6431-142">Require group membership</span></span> | <span data-ttu-id="f6431-143">グループ メンバーシップを要求</span><span class="sxs-lookup"><span data-stu-id="f6431-143">Require group membership</span></span> |
|<span data-ttu-id="f6431-144">許可されていないデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="f6431-144">Unauthorized data access</span></span> | <span data-ttu-id="f6431-145">デバイスの登録を要求</span><span class="sxs-lookup"><span data-stu-id="f6431-145">Require device enrollment</span></span> | <span data-ttu-id="f6431-146">保護されたアプリを要求</span><span class="sxs-lookup"><span data-stu-id="f6431-146">Require protected app</span></span> |
|<span data-ttu-id="f6431-147">許可されていないデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="f6431-147">Unauthorized data access</span></span> | <span data-ttu-id="f6431-148">特定の場所を要求</span><span class="sxs-lookup"><span data-stu-id="f6431-148">Require specific location</span></span> | <span data-ttu-id="f6431-149">特定の場所を要求</span><span class="sxs-lookup"><span data-stu-id="f6431-149">Require specific location</span></span> |
| | | |
|<span data-ttu-id="f6431-150">侵害されたユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="f6431-150">Compromised user account</span></span>| <span data-ttu-id="f6431-151">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="f6431-151">Require MFA</span></span> | <span data-ttu-id="f6431-152">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="f6431-152">Require MFA</span></span>|
|<span data-ttu-id="f6431-153">侵害されたユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="f6431-153">Compromised user account</span></span> | <span data-ttu-id="f6431-154">リスクの高いユーザーをブロック</span><span class="sxs-lookup"><span data-stu-id="f6431-154">Block high risk users</span></span> | <span data-ttu-id="f6431-155">リスクの高いユーザーをブロック</span><span class="sxs-lookup"><span data-stu-id="f6431-155">Block high risk users</span></span> |
|<span data-ttu-id="f6431-156">侵害されたユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="f6431-156">Compromised user account</span></span> | <span data-ttu-id="f6431-157">デバイス PIN</span><span class="sxs-lookup"><span data-stu-id="f6431-157">Device PIN</span></span> | <span data-ttu-id="f6431-158">アプリ PIN</span><span class="sxs-lookup"><span data-stu-id="f6431-158">App PIN</span></span> |
| | | |
| <span data-ttu-id="f6431-159">侵害されたデバイスまたはアプリ</span><span class="sxs-lookup"><span data-stu-id="f6431-159">Compromised device or app</span></span> | <span data-ttu-id="f6431-160">準拠しているデバイスを要求</span><span class="sxs-lookup"><span data-stu-id="f6431-160">Require a compliant device</span></span> | <span data-ttu-id="f6431-161">アプリ起動時の脱獄チェック</span><span class="sxs-lookup"><span data-stu-id="f6431-161">Jailbreak check on app launch</span></span> |
| <span data-ttu-id="f6431-162">侵害されたデバイスまたはアプリ</span><span class="sxs-lookup"><span data-stu-id="f6431-162">Compromised device or app</span></span> | <span data-ttu-id="f6431-163">デバイス データの暗号化</span><span class="sxs-lookup"><span data-stu-id="f6431-163">Encrypt device data</span></span> | <span data-ttu-id="f6431-164">[アプリ データの暗号化]</span><span class="sxs-lookup"><span data-stu-id="f6431-164">Encrypt app data</span></span> |
| | | |
|<span data-ttu-id="f6431-165">デバイスの紛失または盗難</span><span class="sxs-lookup"><span data-stu-id="f6431-165">Lost or stolen device</span></span> | <span data-ttu-id="f6431-166">すべてのデバイス データを削除</span><span class="sxs-lookup"><span data-stu-id="f6431-166">Remove all device data</span></span> | <span data-ttu-id="f6431-167">すべてのアプリ データを削除</span><span class="sxs-lookup"><span data-stu-id="f6431-167">Remove all app data</span></span>|
| | | |
| <span data-ttu-id="f6431-168">セキュリティで保護されていない場所への偶発的なデータの共有または保存</span><span class="sxs-lookup"><span data-stu-id="f6431-168">Accidental data sharing or saving to unsecured locations</span></span> | <span data-ttu-id="f6431-169">デバイスのデータのバックアップを制限</span><span class="sxs-lookup"><span data-stu-id="f6431-169">Restrict device data backups</span></span> | <span data-ttu-id="f6431-170">切り取り/コピー/貼り付けを制限</span><span class="sxs-lookup"><span data-stu-id="f6431-170">Restrict cut/copy/paste</span></span>|
| <span data-ttu-id="f6431-171">セキュリティで保護されていない場所への偶発的なデータの共有または保存</span><span class="sxs-lookup"><span data-stu-id="f6431-171">Accidental data sharing or saving to unsecured locations</span></span> | <span data-ttu-id="f6431-172">名前を指定した保存を制限</span><span class="sxs-lookup"><span data-stu-id="f6431-172">Restrict save-as</span></span> | <span data-ttu-id="f6431-173">名前を指定した保存を制限</span><span class="sxs-lookup"><span data-stu-id="f6431-173">Restrict save-as</span></span> |
|<span data-ttu-id="f6431-174">セキュリティで保護されていない場所への偶発的なデータの共有または保存</span><span class="sxs-lookup"><span data-stu-id="f6431-174">Accidental data sharing or saving to unsecured locations</span></span> | <span data-ttu-id="f6431-175">印刷を無効にする</span><span class="sxs-lookup"><span data-stu-id="f6431-175">Disable printing</span></span> | <span data-ttu-id="f6431-176">該当なし</span><span class="sxs-lookup"><span data-stu-id="f6431-176">n/a</span></span>|

## <a name="next-steps"></a><span data-ttu-id="f6431-177">次の手順</span><span class="sxs-lookup"><span data-stu-id="f6431-177">Next steps</span></span>
<span data-ttu-id="f6431-178">デバイス管理、アプリ管理、またはこれらの組み合わせに注目し、組織で BYOD を有効にするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f6431-178">Now it’s time to decide if you are going to enable BYOD in your organization by focusing on device management, app management, or a combination of the two.</span></span> <span data-ttu-id="f6431-179">実装を選択するのはユーザーですが、Azure AD の ID およびセキュリティ機能を利用できるのでいずれにしても安心です。</span><span class="sxs-lookup"><span data-stu-id="f6431-179">The implementation choice is yours, where you can rest assured that the identity and security features available with Azure AD will be available regardless.</span></span>

<span data-ttu-id="f6431-180">次のレベルの計画について詳しくは、Intune の[計画ガイド](planning-guide.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6431-180">Use the Intune [Planning Guide](planning-guide.md) to map out your next level of planning.</span></span>
