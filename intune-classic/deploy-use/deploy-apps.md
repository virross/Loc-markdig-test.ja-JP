---
title: "アプリの展開"
description: "このトピックでは、Intune を使用してアプリの展開を開始する前に理解する必要がある概念について説明します。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 654f84c93e6ca41f902b36f62a184ea820dc4ba6
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="deploy-apps-with-microsoft-intune"></a><span data-ttu-id="6f8ab-103">Microsoft Intune を使用してアプリを展開する</span><span class="sxs-lookup"><span data-stu-id="6f8ab-103">Deploy apps with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="6f8ab-104">このトピックでは、Microsoft Intune を使用してアプリの展開を開始する前に理解する必要がある概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-104">This topic explains some of the concepts you need to understand before you start deploying apps with Microsoft Intune.</span></span>


## <a name="app-deployment-actions"></a><span data-ttu-id="6f8ab-105">アプリの展開操作</span><span class="sxs-lookup"><span data-stu-id="6f8ab-105">App deployment actions</span></span>
<span data-ttu-id="6f8ab-106">アプリを展開する場合は、次のような展開操作のいずれかから選択できます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-106">When you deploy apps, you can choose from one of the following deployment actions:</span></span>

-   <span data-ttu-id="6f8ab-107">**必須のインストール** – ユーザーの介入なしで、デバイス上にアプリがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-107">**Required install** – The app is installed onto the device with no user intervention required.</span></span>

    > [!TIP]
    > <span data-ttu-id="6f8ab-108">監視モードになっていない iOS デバイスと、すべての Android デバイスで、ユーザーはアプリ オファーを受け入れてからインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-108">For iOS devices that are not in supervised mode, and for all Android devices, the user must accept the app offer before it is installed.</span></span>
    >
    >  <span data-ttu-id="6f8ab-109">必須のインストールとして展開されたアプリをユーザーがアンインストールした場合、Intune は、次回のインベントリ サイクル (7 日おきに実行される) でアプリを自動的に再インストールします。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-109">If a user uninstalls an app that you deployed as a required install, Intune automatically reinstalls the app after the next inventory cycle, which typically occurs every seven days.</span></span>

-   <span data-ttu-id="6f8ab-110">**利用可能なインストール** – ポータル サイトにアプリが表示され、ユーザーがオンデマンドでこれをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-110">**Available install** – The app is displayed in the company portal, and users can install it on demand.</span></span>

-   <span data-ttu-id="6f8ab-111">**アンインストール** – デバイスからアプリがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-111">**Uninstall** – The app is uninstalled from the device.</span></span>

-   <span data-ttu-id="6f8ab-112">**該当なし** – アプリはポータル サイトに表示されず、どのデバイスにもインストールされません。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-112">**Not applicable** – The app is not displayed in the company portal and is not installed on any devices.</span></span>

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a><span data-ttu-id="6f8ab-113">各インストーラーの種類で利用できる展開アクションを理解する</span><span class="sxs-lookup"><span data-stu-id="6f8ab-113">Understand which deployment actions are available for each installer type</span></span>

|<span data-ttu-id="6f8ab-114">インストーラーの種類</span><span class="sxs-lookup"><span data-stu-id="6f8ab-114">Installer type</span></span>|<span data-ttu-id="6f8ab-115">必須のインストール</span><span class="sxs-lookup"><span data-stu-id="6f8ab-115">Required install</span></span>|<span data-ttu-id="6f8ab-116">利用可能なインストール</span><span class="sxs-lookup"><span data-stu-id="6f8ab-116">Available install</span></span>|<span data-ttu-id="6f8ab-117">[アンインストール]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-117">Uninstall</span></span>|<span data-ttu-id="6f8ab-118">適用できません</span><span class="sxs-lookup"><span data-stu-id="6f8ab-118">Not applicable</span></span>|
|------------------|--------------------|---------------------|-------------|------------------|
|<span data-ttu-id="6f8ab-119">Windows アプリケーション パッケージ (ユーザー グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-119">Windows app package (deployed to a user group)</span></span>|<span data-ttu-id="6f8ab-120">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-120">Yes</span></span>|<span data-ttu-id="6f8ab-121">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-121">Yes</span></span>|<span data-ttu-id="6f8ab-122">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-122">Yes</span></span>|<span data-ttu-id="6f8ab-123">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-123">Yes</span></span>|
|<span data-ttu-id="6f8ab-124">Windows アプリ パッケージ (デバイス グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-124">Windows app package (deployed to a device group)</span></span>|<span data-ttu-id="6f8ab-125">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-125">Yes</span></span>|<span data-ttu-id="6f8ab-126">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-126">No</span></span>|<span data-ttu-id="6f8ab-127">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-127">Yes</span></span>|<span data-ttu-id="6f8ab-128">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-128">Yes</span></span>|
|<span data-ttu-id="6f8ab-129">モバイル デバイス用アプリケーション パッケージ (ユーザー グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-129">App package for mobile devices (deployed to a user group)</span></span>|<span data-ttu-id="6f8ab-130">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-130">Yes</span></span>|<span data-ttu-id="6f8ab-131">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-131">Yes</span></span>|<span data-ttu-id="6f8ab-132">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-132">Yes</span></span>|<span data-ttu-id="6f8ab-133">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-133">Yes</span></span>|
|<span data-ttu-id="6f8ab-134">モバイル デバイス用アプリケーション パッケージ (デバイス グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-134">App package for mobile devices (deployed to a device group)</span></span>|<span data-ttu-id="6f8ab-135">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-135">Yes</span></span>|<span data-ttu-id="6f8ab-136">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-136">No</span></span>|<span data-ttu-id="6f8ab-137">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-137">Yes</span></span>|<span data-ttu-id="6f8ab-138">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-138">Yes</span></span>|
|<span data-ttu-id="6f8ab-139">Windows インストーラー (ユーザー グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-139">Windows Installer (deployed to a user group)</span></span>|<span data-ttu-id="6f8ab-140">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-140">No</span></span>|<span data-ttu-id="6f8ab-141">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-141">Yes</span></span>|<span data-ttu-id="6f8ab-142">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-142">No</span></span>|<span data-ttu-id="6f8ab-143">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-143">Yes</span></span>|
|<span data-ttu-id="6f8ab-144">Windows インストーラー (デバイス グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-144">Windows Installer (deployed to a device group)</span></span>|<span data-ttu-id="6f8ab-145">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-145">Yes</span></span>|<span data-ttu-id="6f8ab-146">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-146">No</span></span>|<span data-ttu-id="6f8ab-147">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-147">Yes</span></span>|<span data-ttu-id="6f8ab-148">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-148">Yes</span></span>|
|<span data-ttu-id="6f8ab-149">外部のリンク (ユーザー グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-149">External link (deployed to a user group)</span></span>|<span data-ttu-id="6f8ab-150">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-150">No</span></span>|<span data-ttu-id="6f8ab-151">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-151">Yes</span></span>|<span data-ttu-id="6f8ab-152">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-152">No</span></span>|<span data-ttu-id="6f8ab-153">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-153">Yes</span></span>|
|<span data-ttu-id="6f8ab-154">外部のリンク (デバイス グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-154">External link (deployed to a device group)</span></span>|<span data-ttu-id="6f8ab-155">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-155">No</span></span>|<span data-ttu-id="6f8ab-156">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-156">No</span></span>|<span data-ttu-id="6f8ab-157">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-157">No</span></span>|<span data-ttu-id="6f8ab-158">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-158">No</span></span>|
|<span data-ttu-id="6f8ab-159">App Store の管理対象 iOS アプリケーション (ユーザー グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-159">Managed iOS app from the app store (deployed to a user group)</span></span>|<span data-ttu-id="6f8ab-160">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-160">Yes</span></span>|<span data-ttu-id="6f8ab-161">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-161">Yes</span></span>|<span data-ttu-id="6f8ab-162">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-162">Yes</span></span>|<span data-ttu-id="6f8ab-163">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-163">Yes</span></span>|
|<span data-ttu-id="6f8ab-164">App Store の管理対象 iOS アプリケーション (デバイス グループに展開)</span><span class="sxs-lookup"><span data-stu-id="6f8ab-164">Managed iOS app from the app store (deployed to a device group)</span></span>|<span data-ttu-id="6f8ab-165">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-165">Yes</span></span>|<span data-ttu-id="6f8ab-166">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="6f8ab-166">No</span></span>|<span data-ttu-id="6f8ab-167">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-167">Yes</span></span>|<span data-ttu-id="6f8ab-168">はい</span><span class="sxs-lookup"><span data-stu-id="6f8ab-168">Yes</span></span>|

> [!TIP]
> <span data-ttu-id="6f8ab-169">アプリを展開するときに、ユーザーとデバイス グループの両方を選択した場合、アプリは **[利用可能なインストール]** としてのみ展開できます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-169">When you deploy apps, if you select both user and device groups, you can only deploy the app as an **Available install**.</span></span>

## <a name="deployment-conflicts"></a><span data-ttu-id="6f8ab-170">展開の競合</span><span class="sxs-lookup"><span data-stu-id="6f8ab-170">Deployment conflicts</span></span>
<span data-ttu-id="6f8ab-171">同じ展開操作によって 2 回の展開を行うと、1 つのデバイスで受信され、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-171">When two deployments with the same deployment action are received by a device, the following rules apply:</span></span>

-   <span data-ttu-id="6f8ab-172">デバイス グループへの展開はユーザー グループへの展開より優先されます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-172">Deployments to a device group take precedence over deployments to a user group.</span></span> <span data-ttu-id="6f8ab-173">ただし、**利用可能**な展開のアクションでユーザー グループにアプリを展開し、同じアプリをデバイス グループに、**該当なし**の展開操作で展開すると、このアプリは、ユーザーがポータル サイトからインストールできるようになります。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-173">However, if an app is deployed to a user group with a deployment action of **Available**, and the same app is also deployed to a device group with a deployment action of **Not Applicable**, the app will be made available in the company portal for users to install.</span></span>

-   <span data-ttu-id="6f8ab-174">インストール操作はアンインストール操作よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-174">An install action takes precedence over an uninstall action.</span></span>

-   <span data-ttu-id="6f8ab-175">1 つのデバイスで、必須のインストールと利用可能なインストールを受信した場合は、この 2 つの操作が組み合わされます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-175">If both a required and an available install are received by a device, the actions are combined.</span></span> <span data-ttu-id="6f8ab-176">別の言い方をすると、ユーザーは利用可能なアプリを必須のインストールが開始する前にポータル サイトからインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6f8ab-176">In other words, the user can install the available app from the company portal before the required install begins.</span></span>


## <a name="next-steps"></a><span data-ttu-id="6f8ab-177">次の手順</span><span class="sxs-lookup"><span data-stu-id="6f8ab-177">Next steps</span></span>

<span data-ttu-id="6f8ab-178">[Microsoft Intune でアプリを展開する](deploy-apps-in-microsoft-intune.md)方法を知る</span><span class="sxs-lookup"><span data-stu-id="6f8ab-178">Learn how to [deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span>
