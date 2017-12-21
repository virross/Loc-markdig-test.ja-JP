---
title: "Intune で Google Play Protect コンプライアンスを有効にする"
titleSuffix: Azure portal
description: "Android デバイス用のコンプライアンス ポリシーを作成して Google Play Protect を有効にする方法について説明します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d610bc338c1bcf81ed3bc71f1357e001914c5877
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a><span data-ttu-id="6512d-103">デバイスのコンプライアンス ポリシーを作成して Google Play Protect を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="6512d-103">How to create a device compliance policy to enable Google Play Protect</span></span>

<span data-ttu-id="6512d-104">Android プラットフォーム用に新しいコンプライアンス ポリシーを作成して、Google Play Protect (GPP) コンプライアンスをチェックすることができます。</span><span class="sxs-lookup"><span data-stu-id="6512d-104">You can create a new compliance policy for the Android platform to check for Google Play Protect (GPP) compliance.</span></span>

<span data-ttu-id="6512d-105">これらの設定を必要とするコンプライアンス ポリシーは、Android ユーザーまたはデバイスのグループを対象にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6512d-105">The compliance policy that requires these settings can then be targeted to a group of Android users or devices.</span></span> <span data-ttu-id="6512d-106">デバイスでこれらの設定が有効になっていない場合は、コンプライアンスの対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="6512d-106">If a device does not have these settings enabled, it falls out of compliance.</span></span>

## <a name="create-a-compliance-policy"></a><span data-ttu-id="6512d-107">コンプライアンス ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="6512d-107">Create a compliance policy</span></span>

1. <span data-ttu-id="6512d-108">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6512d-108">Sign in to the Azure portal.</span></span> <span data-ttu-id="6512d-109">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6512d-109">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
2. <span data-ttu-id="6512d-110">**[グループの管理]** で **[デバイスのポリシー準拠]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6512d-110">Choose **Device compliance** in the **Manage** group.</span></span> 
3. <span data-ttu-id="6512d-111">**[ポリシー]**、**[ポリシーを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6512d-111">Choose **Policies**, and choose **Create Policy**.</span></span>
4. <span data-ttu-id="6512d-112">**[ポリシー名]** と **[説明]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="6512d-112">Type the policy **Name** and **Description**.</span></span>
5. <span data-ttu-id="6512d-113">[プラットフォーム] に **[Android]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6512d-113">Select **Android** for the Platform.</span></span>
6. <span data-ttu-id="6512d-114">**[設定]** > **[デバイスの正常性]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6512d-114">Choose **Settings** > **Device Health**.</span></span>
7. <span data-ttu-id="6512d-115">**[Google Play Protect]** 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6512d-115">Configure the **Google Play Protect** settings.</span></span>
8. <span data-ttu-id="6512d-116">[Google Play Protect] 設定が完了したら、**[セキュリティ]** および **[デバイスのプロパティ]** 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6512d-116">When you have set the Google Play Protect settings, specify the **Security** and **Device property** settings.</span></span> <span data-ttu-id="6512d-117">終了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6512d-117">When you are done, choose **OK**.</span></span>

## <a name="configure-the-google-play-protect-settings"></a><span data-ttu-id="6512d-118">Google Play Protect 設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6512d-118">Configure the Google Play Protect settings</span></span>

 - <span data-ttu-id="6512d-119">**Google Play 開発者サービスが構成されています**</span><span class="sxs-lookup"><span data-stu-id="6512d-119">**Google Play Services is configured**</span></span>  
   <span data-ttu-id="6512d-120">Google Play 開発者サービス アプリがインストールされ、有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6512d-120">Require that the Google Play services app is installed and enabled.</span></span> <span data-ttu-id="6512d-121">Google Play 開発者サービスはセキュリティ更新プログラムを許可し、Google の認定デバイスの多くのセキュリティ機能に対してベースレベルの依存関係となっています。</span><span class="sxs-lookup"><span data-stu-id="6512d-121">Google Play services allows security updates and is a base-level dependency for many security features on certified-Google devices.</span></span>
 - <span data-ttu-id="6512d-122">**最新のセキュリティ プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="6512d-122">**Up-to-date security provider**</span></span>  
   <span data-ttu-id="6512d-123">最新のセキュリティ プロバイダーが既知の脆弱性からデバイスを保護できるようになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6512d-123">Require that an up-to-date security provider can protect a device from known vulnerabilities.</span></span>
 - <span data-ttu-id="6512d-124">**アプリの脅威のスキャン**</span><span class="sxs-lookup"><span data-stu-id="6512d-124">**Threat scan on apps**</span></span>  
   <span data-ttu-id="6512d-125">Android の **[アプリの確認]** 機能が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6512d-125">Require that the Android **Verify Apps** feature is enabled.</span></span>
    > [!Note]  
    > <span data-ttu-id="6512d-126">従来の Android プラットフォームでは、この機能はコンプライアンス設定です。</span><span class="sxs-lookup"><span data-stu-id="6512d-126">On the legacy Android platform, this feature is a compliance setting.</span></span> <span data-ttu-id="6512d-127">Intune では、デバイス レベルでこの設定が有効になっているかどうかのみを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6512d-127">Intune can only check whether this setting is enabled at the device level.</span></span> <span data-ttu-id="6512d-128">作業プロファイルがあるデバイス (従来の Android for Work) では、この設定は構成ポリシー設定として存在しています。</span><span class="sxs-lookup"><span data-stu-id="6512d-128">On devices with work profiles, formerly Android for Work, this setting can be found as a configuration policy setting.</span></span> <span data-ttu-id="6512d-129">これにより、管理者はデバイスの設定を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="6512d-129">This allows administrators to enable the setting for a device.</span></span>

    <span data-ttu-id="6512d-130">企業で、Android 作業プロファイルを使用する場合は、登録されているデバイスに対して **[アプリの脅威のスキャン]** を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="6512d-130">If your enterprise uses Android work profiles, you can enabled **Threat scan on apps** for your enrolled devices.</span></span> <span data-ttu-id="6512d-131">デバイス プロファイルを作成し、システム セキュリティ設定を要求します。</span><span class="sxs-lookup"><span data-stu-id="6512d-131">Establish a device profile and require the system security setting.</span></span> <span data-ttu-id="6512d-132">詳細については、「[Microsoft Intune での Android for Work デバイスの制限設定](device-restrictions-android-for-work.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6512d-132">For more information, see [Android for Work device restriction settings in Microsoft Intune](device-restrictions-android-for-work.md).</span></span>

 - <span data-ttu-id="6512d-133">**SafetyNet デバイスの構成証明**</span><span class="sxs-lookup"><span data-stu-id="6512d-133">**SafetyNet device attestation**</span></span>  
   <span data-ttu-id="6512d-134">満たす必要がある SafetyNet デバイス構成証明の整合性のレベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="6512d-134">Set the level of SafetyNet device attestation integrity that must be met.</span></span> <span data-ttu-id="6512d-135">レベルには、**[未構成]**、**[Check basic integrity]\(基本的な整合性のチェック\)**、**[Check basic integrity & certified devices]\(基本的な整合性と認定デバイスのチェック\)** があります。</span><span class="sxs-lookup"><span data-stu-id="6512d-135">Levels include **Not configured**, **Check basic integrity**, and **Check basic integrity & certified devices**.</span></span>




## <a name="next-steps"></a><span data-ttu-id="6512d-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6512d-136">Next steps</span></span>

<span data-ttu-id="6512d-137">Intune のデバイス コンプライアンス ポリシーの詳細については、「[Intune のデバイス コンプライアンス ポリシーの概要](device-compliance-get-started.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6512d-137">To learn more about working with Intune device compliance policies, see [Get started with Intune device compliance policies](device-compliance-get-started.md).</span></span>