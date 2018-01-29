---
title: "アプリのプロビジョニング プロファイル"
titlesuffix: Azure portal
description: "Intune には、有効期限が近づいているアプリを持つデバイスに新しいプロビジョニング プロファイルを事前に割り当てるツールが用意されています。\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce66677bfec48e9a5b69e23be67e2e172edc33d5
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="use-ios-mobile-provisioning-profiles-to-prevent-your-apps-from-expiring"></a><span data-ttu-id="fe7d8-103">iOS モバイル プロビジョニング プロファイルを使用して、アプリが期限切れにならないようにする</span><span class="sxs-lookup"><span data-stu-id="fe7d8-103">Use iOS mobile provisioning profiles to prevent your apps from expiring</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a><span data-ttu-id="fe7d8-104">概要</span><span class="sxs-lookup"><span data-stu-id="fe7d8-104">Introduction</span></span>

<span data-ttu-id="fe7d8-105">iPhone および iPad に割り当てられた Apple iOS 基幹業務アプリは、含まれるプロビジョニング プロファイルおよび証明書で署名されたコードで構築されます。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-105">Apple iOS line of business apps that are assigned to iPhones and iPads are built with an included provisioning profile and code that is signed with a certificate.</span></span> <span data-ttu-id="fe7d8-106">アプリを実行すると、iOS は iOS アプリの整合性を確認し、プロビジョニング プロファイルで定義されたポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-106">When the app is run, iOS confirms the integrity of the iOS app and enforces policies that are defined by the provisioning profile.</span></span> <span data-ttu-id="fe7d8-107">次の検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-107">The following validations happen:</span></span>

- <span data-ttu-id="fe7d8-108">**インストール ファイルの整合性** - iOS は、アプリの詳細と、エンタープライズ署名証明書の公開キーを比較します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-108">**Installation file integrity** - iOS compares the app's details with the enterprise signing certificate's public key.</span></span> <span data-ttu-id="fe7d8-109">これらが異なる場合はアプリの内容が変更されている可能性があり、アプリは実行を許可されません。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-109">If they differ, the app's content might have changed, and the app will not be allowed to run.</span></span>
- <span data-ttu-id="fe7d8-110">**機能の強制** - iOS は、アプリのインストール (.ipa) ファイルに含まれる、(個々の開発者プロビジョニング プロファイルではなく) エンタープライズ プロビジョニング プロファイルからアプリの機能の適用を試行します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-110">**Capabilities enforcement** - iOS attempts to enforce the app's capabilities from the enterprise provisioning profile (not individual developer provisioning profiles) that are in the app installation (.ipa) file.</span></span>


<span data-ttu-id="fe7d8-111">アプリの署名に使用するエンタープライズ署名証明書は、通常 3 年間は継続します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-111">The enterprise signing certificate that you use to sign apps typically lasts for three years.</span></span> <span data-ttu-id="fe7d8-112">ただし、プロビジョニング プロファイルは 1 年後に期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-112">However, the provisioning profile expires after a year.</span></span> <span data-ttu-id="fe7d8-113">証明書が有効である期間中、Intune には、有効期限が近づいているアプリを持つデバイスに新しいプロビジョニング プロファイルを事前に割り当てるツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-113">While the certificate is still valid, Intune gives you the tools to proactively assign a new provisioning profile to devices that have apps that are nearing expiry.</span></span>
<span data-ttu-id="fe7d8-114">証明書の期限が切れると、新しい証明書を使用してアプリを再び署名して、新しい証明書のキーを持つ新しいプロビジョニング プロファイルを埋め込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-114">After the certificate expires, you must sign the app again with a new certificate and embed a new provisioning profile with the key of the new certificate.</span></span>


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a><span data-ttu-id="fe7d8-115">iOS モバイル アプリ プロビジョニング プロファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="fe7d8-115">How to create an iOS mobile app provisioning profile</span></span>

1. <span data-ttu-id="fe7d8-116">Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="fe7d8-117">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-117">Choose **More Services** > **Monitoring +Management** > **Intune**.</span></span>
3. <span data-ttu-id="fe7d8-118">**[Intune]** ブレードで、**[モバイル アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-118">On the **Intune** blade, choose **Mobile apps**.</span></span>
1.  <span data-ttu-id="fe7d8-119">**[Mobile Apps]** ワークロードで、**[管理]**、**[iOS プロビジョニング プロファイル]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-119">In the **Mobile apps** workload, choose **Manage** > **iOS provisioning profiles**.</span></span>
2.  <span data-ttu-id="fe7d8-120">プロファイルの一覧ブレードで、**[プロファイルの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-120">In the list of profiles blade, choose **Create profile**.</span></span>
3. <span data-ttu-id="fe7d8-121">**[プロファイルの作成]** ブレードで、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-121">In the **Create profile** blade, configure the following values:</span></span>
    - <span data-ttu-id="fe7d8-122">**名前** - このモバイル プロビジョニング プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-122">**Name** - Provide a name for this mobile provisioning profile.</span></span>
    - <span data-ttu-id="fe7d8-123">**説明** - 必要に応じて、ポリシーの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-123">**Description** - Optionally, provide a description for the policy.</span></span>
    - <span data-ttu-id="fe7d8-124">**プロファイル ファイルのアップロード** - **[インポート]** を選択し、Apple Developer Web サイトからダウンロードした Apple モバイル構成プロファイル ファイル (拡張子 **.mobileprovision**) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-124">**Upload profile file** - Choose **Import**, and then choose an Apple Mobile Configuration Profile file (with the extension **.mobileprovision**) that you downloaded from the Apple Developer website.</span></span>
4. <span data-ttu-id="fe7d8-125">終了したら、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-125">When you are done, choose **Create**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe7d8-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="fe7d8-126">Next steps</span></span>

<span data-ttu-id="fe7d8-127">必要な iOS デバイスにプロファイルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-127">Assign the profile to the required iOS devices.</span></span> <span data-ttu-id="fe7d8-128">詳細については、「[デバイス プロファイルを割り当てる方法](device-profile-assign.md)」の手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe7d8-128">For more information, use the steps in [How to assign device profiles](device-profile-assign.md).</span></span>
