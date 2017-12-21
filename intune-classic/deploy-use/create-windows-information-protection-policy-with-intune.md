---
title: "Intune で Windows 情報保護 (WIP) アプリ保護ポリシーを作成して展開する"
description: "Intune で WIP アプリ保護ポリシーを作成して展開します"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 9/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51e53e28-5c34-4d0f-a4b1-6390a337514c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1f42dd68e8f504a1f84d9158f8c16cfe25d1e1b7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a><span data-ttu-id="a0bfe-103">Intune で Windows 情報保護 (WIP) アプリ保護ポリシーを作成して展開する</span><span class="sxs-lookup"><span data-stu-id="a0bfe-103">Create and deploy Windows Information Protection (WIP) app protection policy with Intune</span></span>

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

<span data-ttu-id="a0bfe-104">Intune 1704 リリース以降では、登録なしのモバイル アプリケーション管理 (MAM) シナリオの Windows 10 でアプリ保護ポリシーを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-104">Beginning with Intune 1704 release, you can use app protection policies with Windows 10 in the mobile application management (MAM) without enrollment scenario.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a0bfe-105">始める前に</span><span class="sxs-lookup"><span data-stu-id="a0bfe-105">Before you begin</span></span>

<span data-ttu-id="a0bfe-106">WIP ポリシーを追加するときのいくつかの概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-106">Let’s talk about a few concepts when adding a WIP policy.</span></span>

### <a name="list-of-allowed-and-exempt-apps"></a><span data-ttu-id="a0bfe-107">許可されているアプリと適用から除外されるアプリの一覧</span><span class="sxs-lookup"><span data-stu-id="a0bfe-107">List of Allowed and Exempt apps</span></span>

-   <span data-ttu-id="a0bfe-108">**[許可されているアプリ]**: このポリシーに準拠する必要があるアプリです。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-108">**Allowed apps:** These are the apps that need to adhere to this policy.</span></span>

-   <span data-ttu-id="a0bfe-109">**[適用から除外されるアプリ]**: これらのアプリはこのポリシーから除外され、制限なしに企業データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-109">**Exempt apps:** These apps are exempt from this policy and can access corporate data without restrictions.</span></span>

### <a name="types-of-apps"></a><span data-ttu-id="a0bfe-110">アプリの種類</span><span class="sxs-lookup"><span data-stu-id="a0bfe-110">Types of apps</span></span>

-   <span data-ttu-id="a0bfe-111">**[おすすめのアプリ]:** 管理者がポリシーに簡単にインポートできるようにあらかじめ設定されている (ほとんどは Microsoft Office) アプリの一覧です。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-111">**Recommended apps:** a pre-populated list of (mostly Microsoft Office) apps that allow admins easily import into policy.</span></span>

-   <span data-ttu-id="a0bfe-112">**[ストア アプリ]:** 管理者は、Windows ストアからポリシーに任意のアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-112">**Store apps:** Admin can add any app from the Windows store to policy.</span></span>

-   <span data-ttu-id="a0bfe-113">**[Windows desktop apps (Windows デスクトップ アプリ)]:** 管理者は従来の Windows デスクトップ アプリをポリシーに追加できます (exe、dll など)。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-113">**Windows desktop apps:** Admin can add any traditional Windows desktop apps to the policy (e.g. exe, dll, etc.)</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="a0bfe-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="a0bfe-114">Pre-requisites</span></span>

<span data-ttu-id="a0bfe-115">WIP アプリ保護ポリシーを作成する前に、MAM プロバイダーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-115">You need to configure the MAM provider before you can create a WIP app protection policy.</span></span>

-   <span data-ttu-id="a0bfe-116">[Intune で MAM プロバイダーを構成する方法](/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10)を理解します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-116">Learn more about [how to configure your MAM provider with Intune](/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10).</span></span>

<span data-ttu-id="a0bfe-117">さらに、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-117">Additionally, you need to have the following:</span></span>

-   <span data-ttu-id="a0bfe-118">[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) ライセンス。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-118">[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) license.</span></span>
-   [<span data-ttu-id="a0bfe-119">Windows Creators Update</span><span class="sxs-lookup"><span data-stu-id="a0bfe-119">Windows Creators Update</span></span>](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> <span data-ttu-id="a0bfe-120">WIP は複数の ID をサポートしていません。存在できる管理対象 ID は一度に 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-120">WIP does not support multi-identity, only one managed identity can exist at a time.</span></span>

## <a name="to-add-a-wip-policy"></a><span data-ttu-id="a0bfe-121">WIP ポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="a0bfe-121">To add a WIP policy</span></span>

<span data-ttu-id="a0bfe-122">組織で Intune を設定した後は、[Azure Portal](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) を使用して WIP 固有のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-122">After you set up Intune in your organization, you can create a WIP-specific policy through the [Azure portal](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).</span></span>

1.  <span data-ttu-id="a0bfe-123">**Intune モバイル アプリケーション管理ダッシュボード**に移動し、**[すべての設定]** を選び、**[アプリに関するポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-123">Go to the **Intune mobile application management dashboard**, choose **All settings**, and then choose **App policy**.</span></span>

2.  <span data-ttu-id="a0bfe-124">**[アプリに関するポリシー]** ブレードで **[ポリシーの追加]** を選び、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-124">In the **App policy** blade, choose **Add a policy**, then enter the following values:</span></span>

    <span data-ttu-id="a0bfe-125">a.</span><span class="sxs-lookup"><span data-stu-id="a0bfe-125">a.</span></span>  <span data-ttu-id="a0bfe-126">**[名前]:** (必須) 新しいポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-126">**Name:** Type a name (required) for your new policy.</span></span>

    <span data-ttu-id="a0bfe-127">b.</span><span class="sxs-lookup"><span data-stu-id="a0bfe-127">b.</span></span>  <span data-ttu-id="a0bfe-128">**[説明]:** 必要に応じて説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-128">**Description:** Type an optional description.</span></span>

    <span data-ttu-id="a0bfe-129">c.</span><span class="sxs-lookup"><span data-stu-id="a0bfe-129">c.</span></span>  <span data-ttu-id="a0bfe-130">**[プラットフォーム]:** アプリ保護ポリシーのサポート対象プラットフォームとして **[Windows 10]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-130">**Platform:** Choose **Windows 10** as the supported platform for your app protection policy.</span></span>

    <span data-ttu-id="a0bfe-131">d.</span><span class="sxs-lookup"><span data-stu-id="a0bfe-131">d.</span></span>  <span data-ttu-id="a0bfe-132">**[登録の状態]:** ポリシーの登録状態として、**[未登録]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-132">**Enrollment state:** Choose **Without enrollment** as the enrollment state for your policy.</span></span>

3.  <span data-ttu-id="a0bfe-133">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-133">Choose **Create**.</span></span> <span data-ttu-id="a0bfe-134">ポリシーが作成されて、**[アプリに関するポリシー]** ブレードのテーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-134">The policy is created and appears in the table on the **App Policy** blade.</span></span>

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a><span data-ttu-id="a0bfe-135">おすすめのアプリを許可されているアプリの一覧に追加するには</span><span class="sxs-lookup"><span data-stu-id="a0bfe-135">To add recommended apps to your Allowed apps list</span></span>

1.  <span data-ttu-id="a0bfe-136">**[アプリに関するポリシー]** ブレードでポリシーの名前を選び、**[ポリシーの追加]** ブレードで **[許可されているアプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-136">From the **App policy** blade, choose the name of your policy, then choose **Allowed apps** from the **Add a policy** blade.</span></span> <span data-ttu-id="a0bfe-137">**[許可されているアプリ]** ブレードが開き、このアプリ保護ポリシーの一覧に既に含まれているすべてのアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-137">The **Allowed apps** blade opens, showing you all apps that are already included in the list for this app protection policy.</span></span>

2.  <span data-ttu-id="a0bfe-138">**[許可されているアプリ]** ブレードで、**[アプリの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-138">From the **Allowed apps** blade, choose **Add apps**.</span></span> <span data-ttu-id="a0bfe-139">**[アプリの追加]** ブレードが開き、この一覧に含まれるすべてのアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-139">The **Add apps** blade opens, showing you all apps that are part of this list.</span></span>

3.  <span data-ttu-id="a0bfe-140">企業データへのアクセスを許可する各アプリを選択し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-140">Select each app you want to access your corporate data, and then choose **OK**.</span></span> <span data-ttu-id="a0bfe-141">**[許可されているアプリ]** ブレードが更新され、選択したすべてのアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-141">The **Allowed apps** blade gets updated showing you all selected apps.</span></span>

## <a name="add-a-store-app-to-your-allowed-apps-list"></a><span data-ttu-id="a0bfe-142">許可されているアプリの一覧にストア アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="a0bfe-142">Add a Store app to your Allowed apps list</span></span>

<span data-ttu-id="a0bfe-143">**ストア アプリを追加するには**</span><span class="sxs-lookup"><span data-stu-id="a0bfe-143">**To add a Store app**</span></span>

1.  <span data-ttu-id="a0bfe-144">**[アプリに関するポリシー]** ブレードで、ポリシーの名前を選び、このアプリ保護ポリシーの一覧に既に含まれているすべてのアプリが表示されるメニューから **[許可されているアプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-144">From the **App policy** blade, choose the name of your policy, then choose **Allowed apps** from the menu that appears showing all apps that are already included in the list for this app protection policy.</span></span>

2.  <span data-ttu-id="a0bfe-145">**[許可されているアプリ]** ブレードで、**[アプリの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-145">From the **Allowed apps** blade, choose **Add apps**.</span></span>

3.  <span data-ttu-id="a0bfe-146">**[アプリの追加]** ブレードで、ドロップダウン リストから **[ストア アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-146">On the **Add apps** blade, choose **Store apps** from the dropdown list.</span></span> <span data-ttu-id="a0bfe-147">ブレードが変化し、**パブリッシャー**とアプリの**名前**を追加するためのボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-147">The blade changes to show boxes for you to add a **publisher** and app **name**.</span></span>

4.  <span data-ttu-id="a0bfe-148">アプリの名前とパブリッシャーの名前を入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-148">Type the name of the app and the name of its publisher, and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a0bfe-149">たとえば、**パブリッシャー**には「*CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US*」と、製品の**名前**には「*Microsoft.MicrosoftAppForWindows*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-149">Here’s an app example, where the **Publisher** is *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US* and the Product **name** is *Microsoft.MicrosoftAppForWindows*.</span></span>

5.  <span data-ttu-id="a0bfe-150">フィールドに情報を入力した後、**[OK]** を選択して **[許可されているアプリ]** の一覧にアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-150">After you’ve entered the info into the fields, choose **OK** to add the app to your **Allowed apps** list.</span></span>

> [!NOTE]
> <span data-ttu-id="a0bfe-151">同時に複数のストア アプリを追加するには、アプリ行の末尾にあるメニュー **[...]** をクリックし、アプリの追加を続けます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-151">To add multiple Store apps at the same time, you can click the menu **(…)** at the end of the app row, then continue to add more apps.</span></span> <span data-ttu-id="a0bfe-152">終了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-152">Once you’re done, choose **OK**.</span></span>

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a><span data-ttu-id="a0bfe-153">許可されているアプリの一覧にデスクトップ アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="a0bfe-153">Add a Desktop app to your Allowed apps list</span></span>

<span data-ttu-id="a0bfe-154">**デスクトップ アプリを追加するには**</span><span class="sxs-lookup"><span data-stu-id="a0bfe-154">**To add a Desktop app**</span></span>

1.  <span data-ttu-id="a0bfe-155">**[アプリに関するポリシー]** ブレードでポリシーの名前を選び、**[許可されているアプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-155">From the **App policy** blade, choose the name of your policy, and then choose **Allowed apps.**</span></span> <span data-ttu-id="a0bfe-156">**[許可されているアプリ]** ブレードが開き、このアプリ保護ポリシーの一覧に既に含まれているすべてのアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-156">The **Allowed apps** blade opens showing you all apps that are already included in the list for this app protection policy.</span></span>

2.  <span data-ttu-id="a0bfe-157">**[許可されているアプリ]** ブレードで、**[アプリの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-157">From the **Allowed apps** blade, choose **Add apps**.</span></span>

3.  <span data-ttu-id="a0bfe-158">**[アプリの追加]** ブレードで、ドロップダウン リストから **[デスクトップ アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-158">On the **Add apps** blade, choose **Desktop apps** from the drop-down list.</span></span>

4.  <span data-ttu-id="a0bfe-159">フィールドに情報を入力した後、**[OK]** を選択して **[許可されているアプリ]** の一覧にアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-159">After you entered the info into the fields, choose **OK** to add the app to your **Allowed apps** list.</span></span>

> [!NOTE]
> <span data-ttu-id="a0bfe-160">同時に複数の**デスクトップ アプリ**を追加するには、アプリ行の末尾にあるメニュー **[...]** をクリックし、アプリの追加を続けます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-160">To add multiple **Desktop apps** at the same time, you can click the menu **(…)** at the end of the app row, then continue to add more apps.</span></span> <span data-ttu-id="a0bfe-161">終了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-161">Once you’re done, choose **OK**.</span></span>

## <a name="windows-information-protection-wip-learning"></a><span data-ttu-id="a0bfe-162">Windows 情報保護 (WIP) の学習</span><span class="sxs-lookup"><span data-stu-id="a0bfe-162">Windows Information Protection (WIP) Learning</span></span>

<span data-ttu-id="a0bfe-163">WIP で保護するアプリを追加した後は、**[WIP の学習]** を使って保護モードを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-163">After you add the apps you want to protect with WIP, you need to apply a protection mode by using **WIP Learning**.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="a0bfe-164">始める前に</span><span class="sxs-lookup"><span data-stu-id="a0bfe-164">Before you begin</span></span>

<span data-ttu-id="a0bfe-165">Windows 情報保護 (WIP) の学習は、管理者が WIP の不明アプリを監視できるレポートです。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-165">Windows Information Protection (WIP) Learning is a report that allows admins to monitor their WIP unknown apps.</span></span> <span data-ttu-id="a0bfe-166">不明アプリは、組織の IT 部門によって展開されていないアプリです。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-166">The unknown apps are the ones not deployed by your organization’s IT department.</span></span> <span data-ttu-id="a0bfe-167">管理者は、"上書きの非表示" モードで WIP を適用する前に、レポートからこのようなアプリをエクスポートして WIP ポリシーに追加することで、生産性への影響を回避できます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-167">The admin can export these apps from the report and add them to their WIP policies to avoid productivity disruption before they enforce WIP in “Hide Override” mode.</span></span>

<span data-ttu-id="a0bfe-168">最初は **[サイレント]** または **[上書きの許可]** を使用し、許可されているアプリの一覧に適切なアプリが含まれる小規模なグループで確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-168">We recommend that you start with **Silent** or **Allow Overrides** while verifying with a small group that you have the right apps on your allowed apps list.</span></span> <span data-ttu-id="a0bfe-169">それが済んだ後、最終的な適用ポリシーである **[上書きの非表示]** に変更できます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-169">After you're done, you can change to your final enforcement policy, **Hide Overrides**.</span></span>

#### <a name="what-the-protection-modes-are"></a><span data-ttu-id="a0bfe-170">保護モードの種類</span><span class="sxs-lookup"><span data-stu-id="a0bfe-170">What the protection modes are?</span></span>

- <span data-ttu-id="a0bfe-171">**上書きの非表示:**</span><span class="sxs-lookup"><span data-stu-id="a0bfe-171">**Hide Overrides:**</span></span>
    - <span data-ttu-id="a0bfe-172">WIP は不適切なデータ共有行為を検索し、ユーザーが操作を完了できないようにします。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-172">WIP looks for inappropriate data sharing practices and stops the user from completing the action.</span></span>
    - <span data-ttu-id="a0bfe-173">これには、会社で保護されていないアプリ間での情報の共有や、組織外の他のユーザーやデバイス間での会社データの共有などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-173">This can include sharing info across non-corporate-protected apps, and sharing corporate data between other people and devices outside of your organization.</span></span>
<br></br>

- <span data-ttu-id="a0bfe-174">**上書きの許可:**</span><span class="sxs-lookup"><span data-stu-id="a0bfe-174">**Allow Overrides:**</span></span>
    - <span data-ttu-id="a0bfe-175">WIP は不適切なデータ共有を検索し、ユーザーが危険なことを行うと警告します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-175">WIP looks for inappropriate data sharing, warning users if they do something deemed potentially unsafe.</span></span>
    - <span data-ttu-id="a0bfe-176">ただし、このモードでは、ユーザーはポリシーを上書きしてデータを共有することができ、その操作は監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-176">However, this mode lets the user override the policy and share the data, logging the action to your audit log.</span></span>
<br></br>
- <span data-ttu-id="a0bfe-177">**サイレント:**</span><span class="sxs-lookup"><span data-stu-id="a0bfe-177">**Silent:**</span></span>
    - <span data-ttu-id="a0bfe-178">WIP はサイレントで実行し、不適切なデータ共有をログに記録します。"上書きの許可" モードでは従業員にメッセージが表示された行為もブロックしません。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-178">WIP runs silently, logging inappropriate data sharing, without blocking anything that would’ve been prompted for employee interaction while in Allow Override mode.</span></span>
    - <span data-ttu-id="a0bfe-179">ネットワーク リソースや WIP で保護されたデータへのアプリによる不適切なアクセスの試みなど、許可されていない操作は停止されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-179">Unallowed actions, like apps inappropriately trying to access a network resource or WIP-protected data, are still stopped.</span></span>
<br></br>
- <span data-ttu-id="a0bfe-180">**オフ (非推奨):**</span><span class="sxs-lookup"><span data-stu-id="a0bfe-180">**Off (not recommended):**</span></span>
    - <span data-ttu-id="a0bfe-181">WIP は無効になり、データの保護または監査には役立ちません。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-181">WIP is turned off and doesn't help to protect or audit your data.</span></span>
    - <span data-ttu-id="a0bfe-182">WIP を無効にすると、ローカルに接続されたドライブ上の WIP でタグ付けされたファイルを復号化する試みが行われます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-182">After you turn off WIP, an attempt is made to decrypt any WIP-tagged files on the locally attached drives.</span></span> <span data-ttu-id="a0bfe-183">WIP 保護を有効に戻しても、以前の復号化およびポリシーの情報は自動的に再適用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-183">Be aware that your previous decryption and policy info isn’t automatically reapplied if you turn WIP protection back on.</span></span>

### <a name="to-add-a-protection-mode"></a><span data-ttu-id="a0bfe-184">保護モードを追加するには</span><span class="sxs-lookup"><span data-stu-id="a0bfe-184">To add a protection mode</span></span>

1.  <span data-ttu-id="a0bfe-185">**[アプリに関するポリシー]** ブレードでポリシーの名前を選んだ後、**[ポリシーの追加]** ブレードで **[必須の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-185">From the **App policy** blade, choose the name of your policy, then click **Required settings** from the **Add Policy** blade.</span></span>

    ![学習モードのスクリーンショット](../media/AppManagement/learning-mode-sc1.png)

1.  <span data-ttu-id="a0bfe-187">**[保存]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-187">Choose **Save**.</span></span>

### <a name="to-use-wip-learning"></a><span data-ttu-id="a0bfe-188">WIP の学習を使うには</span><span class="sxs-lookup"><span data-stu-id="a0bfe-188">To use WIP Learning</span></span>

1. <span data-ttu-id="a0bfe-189">Azure ダッシュボードに移動します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-189">Go to the Azure Dashboard.</span></span>

2. <span data-ttu-id="a0bfe-190">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-190">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="a0bfe-191">**[Intune]** を選んで **Intune ダッシュボード**を開き、**[モバイル アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-191">Choose **Intune**, the **Intune dashboard** opens, choose **Mobile Apps**.</span></span>

4. <span data-ttu-id="a0bfe-192">**[モニター]** セクションで **[WIP の学習]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-192">Choose **WIP Learning** under **Monitor** section.</span></span> <span data-ttu-id="a0bfe-193">WIP の学習によって記録された不明アプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-193">You see the unknown apps logged by the WIP Learning.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0bfe-194">WIP の学習のログ レポートにアプリが表示されたら、それをアプリ保護ポリシーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-194">Once you have the apps showing up in the WIP Learning logging report, you can them into your app protection policies.</span></span>

## <a name="to-deploy-your-wip-app-protection-policy"></a><span data-ttu-id="a0bfe-195">WIP アプリ保護ポリシーを展開するには</span><span class="sxs-lookup"><span data-stu-id="a0bfe-195">To deploy your WIP app protection policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0bfe-196">これは、登録なしのモバイル アプリケーション管理 (MAM) シナリオの WIP に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-196">This applies for WIP with mobile application management (MAM) without enrollment scenario.</span></span>

<span data-ttu-id="a0bfe-197">WIP アプリ保護ポリシーを作成した後、MAM を使ってポリシーを組織に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-197">After you created your WIP app protection policy, you need to deploy it to your organization using MAM.</span></span>

1.  <span data-ttu-id="a0bfe-198">**[アプリに関するポリシー]** ブレードで新しく作成したアプリ保護ポリシーを選択し、**[ユーザー グループ]** を選んで、**[ユーザー グループの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-198">On the **App policy** blade, choose your newly-created app protection policy, choose **User groups**, then choose **Add user group**.</span></span>

    <span data-ttu-id="a0bfe-199">Azure Active Directory 内のすべてのセキュリティ グループで構成されるユーザー グループの一覧が、**[ユーザー グループの追加]** ブレードで開きます。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-199">A list of user groups, made up of all the security groups in your Azure Active Directory, opens in the **Add user group** blade.</span></span>

1.  <span data-ttu-id="a0bfe-200">ポリシーを適用するグループを選び、**[選択]** をクリックしてポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="a0bfe-200">Choose the group you want your policy to apply to, then click **Select** to deploy the policy.</span></span>
