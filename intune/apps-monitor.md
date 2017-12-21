---
title: "アプリ情報と割り当てを監視する方法"
titlesuffix: Azure portal
description: "ユーザーまたはデバイスにアプリを割り当てた後は、この情報を参考にして、その状態を監視できます。"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59323e6f3aac63676b7fa2f4724602c3a78e02c0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a><span data-ttu-id="4247d-103">Microsoft Intune でアプリ情報と割り当てを監視する方法</span><span class="sxs-lookup"><span data-stu-id="4247d-103">How to monitor app information and assignments with Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="4247d-104">Intune には、管理しているアプリのプロパティと、割り当ての状態を監視する方法が複数あります。</span><span class="sxs-lookup"><span data-stu-id="4247d-104">Intune provides a number of ways in which you can monitor the properties of apps you manage, as well as their assignment status.</span></span>

1. <span data-ttu-id="4247d-105">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4247d-105">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="4247d-106">**[その他のサービス]** > **[監視 + 管理]** + **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4247d-106">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="4247d-107">**[モバイル アプリ]** ワークロードで、**[管理]** グループの **[アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4247d-107">In the **Mobile Apps** workload, choose **Apps** in the **Manage** group.</span></span>
5. <span data-ttu-id="4247d-108">アプリ ブレードの一覧で、アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="4247d-108">In the list of apps blade, choose an app.</span></span> <span data-ttu-id="4247d-109">[<*アプリ名*> **デバイスのインストール状態]** ブレードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4247d-109">You'll then see the <*app name*> **Device install status** blade.</span></span>

## <a name="app-overview-blade"></a><span data-ttu-id="4247d-110">アプリ概要ブレード</span><span class="sxs-lookup"><span data-stu-id="4247d-110">App overview blade</span></span>

<span data-ttu-id="4247d-111"><*アプリ名*> **[デバイスのインストール状態]** ブレードを使用すると、環境内でのアプリの状態に関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4247d-111">You can use the <*app name*> **Device install status** blade to review details about the status of an app in your environment.</span></span>

### <a name="essentials"></a><span data-ttu-id="4247d-112">Essentials</span><span class="sxs-lookup"><span data-stu-id="4247d-112">Essentials</span></span>

<span data-ttu-id="4247d-113">**[Essentials]** セクションには、アプリに関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4247d-113">The **Essentials** section contains the following information about the app:</span></span>

 - <span data-ttu-id="4247d-114">**発行者**</span><span class="sxs-lookup"><span data-stu-id="4247d-114">**Publisher**</span></span>  
<span data-ttu-id="4247d-115">アプリの発行者。</span><span class="sxs-lookup"><span data-stu-id="4247d-115">Publisher of the app.</span></span>
 - <span data-ttu-id="4247d-116">**オペレーティング システム**</span><span class="sxs-lookup"><span data-stu-id="4247d-116">**Operating system**</span></span>  
<span data-ttu-id="4247d-117">アプリのオペレーティング システム (Windows、iOS、Android など)</span><span class="sxs-lookup"><span data-stu-id="4247d-117">The operating system of the app  (Windows, iOS, Android, etc.)</span></span>
 - <span data-ttu-id="4247d-118">**作成**</span><span class="sxs-lookup"><span data-stu-id="4247d-118">**Create**</span></span>  
<span data-ttu-id="4247d-119">このリビジョンが作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="4247d-119">The time when this revision was created.</span></span>
 - <span data-ttu-id="4247d-120">**割り当て済み**</span><span class="sxs-lookup"><span data-stu-id="4247d-120">**Assigned**</span></span>  
<span data-ttu-id="4247d-121">アプリが割り当てられている場合は **[はい]**、アプリが割り当てられていない場合は **[いいえ]**。</span><span class="sxs-lookup"><span data-stu-id="4247d-121">**Yes** or **No** if the app has been assigned.</span></span>

### <a name="status"></a><span data-ttu-id="4247d-122">状態</span><span class="sxs-lookup"><span data-stu-id="4247d-122">Status</span></span>
<span data-ttu-id="4247d-123">各グラフには、次の状態の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4247d-123">Each graph shows counts for the following status:</span></span>

 - <span data-ttu-id="4247d-124">**インストール済み**</span><span class="sxs-lookup"><span data-stu-id="4247d-124">**Installed**</span></span>  
<span data-ttu-id="4247d-125">インストールされているアプリの数。</span><span class="sxs-lookup"><span data-stu-id="4247d-125">The number of apps installed.</span></span>
 - <span data-ttu-id="4247d-126">**未インストール**</span><span class="sxs-lookup"><span data-stu-id="4247d-126">**Not Installed**</span></span>  
<span data-ttu-id="4247d-127">インストールされていないアプリの数。</span><span class="sxs-lookup"><span data-stu-id="4247d-127">The number of apps not installed.</span></span>
 - <span data-ttu-id="4247d-128">**インストール保留中**</span><span class="sxs-lookup"><span data-stu-id="4247d-128">**Install Pending**</span></span>  
<span data-ttu-id="4247d-129">インストール プロセス中のアプリの数。</span><span class="sxs-lookup"><span data-stu-id="4247d-129">The number of apps in the process of being installed.</span></span>
 - <span data-ttu-id="4247d-130">**失敗**</span><span class="sxs-lookup"><span data-stu-id="4247d-130">**Failed**</span></span>  
<span data-ttu-id="4247d-131">失敗したインストールの数。</span><span class="sxs-lookup"><span data-stu-id="4247d-131">The number of failed installations.</span></span>
 - <span data-ttu-id="4247d-132">**不明**</span><span class="sxs-lookup"><span data-stu-id="4247d-132">**Unknown**</span></span>  
<span data-ttu-id="4247d-133">不明な状態にあるアプリの数。</span><span class="sxs-lookup"><span data-stu-id="4247d-133">The number of apps with an unknown status.</span></span>

### <a name="device-status"></a><span data-ttu-id="4247d-134">デバイスの状態</span><span class="sxs-lookup"><span data-stu-id="4247d-134">Device status</span></span>

<span data-ttu-id="4247d-135">デバイスの状態。</span><span class="sxs-lookup"><span data-stu-id="4247d-135">Device status.</span></span> <span data-ttu-id="4247d-136">デバイス上でのアプリのインストール状態を示すドーナツ グラフ。</span><span class="sxs-lookup"><span data-stu-id="4247d-136">A donut chart that displays the install status of the app on devices.</span></span> <span data-ttu-id="4247d-137">グラフをクリックすると、デバイスの状態に関する詳細の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4247d-137">Click the graph to open a list of details about the device status.</span></span> <span data-ttu-id="4247d-138">詳細テーブルには、次の列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4247d-138">The details table includes the following columns:</span></span>

 - <span data-ttu-id="4247d-139">**デバイス名**</span><span class="sxs-lookup"><span data-stu-id="4247d-139">**Device name**</span></span>  
<span data-ttu-id="4247d-140">デバイスに名前を付けられるプラットフォーム上にあるデバイスの名前。</span><span class="sxs-lookup"><span data-stu-id="4247d-140">Name of the device on platforms that allow naming a device.</span></span> <span data-ttu-id="4247d-141">その他のプラットフォームの場合、Intune がその他のプロパティから名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="4247d-141">On other platforms, Intune creates a name from other properties.</span></span> <span data-ttu-id="4247d-142">この属性は一部のデバイスで利用できません。</span><span class="sxs-lookup"><span data-stu-id="4247d-142">This attribute cannot be available for all devices.</span></span>
 - <span data-ttu-id="4247d-143">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="4247d-143">**User name**</span></span>  
<span data-ttu-id="4247d-144">ユーザーの名前です。</span><span class="sxs-lookup"><span data-stu-id="4247d-144">The name of the user.</span></span>
 - <span data-ttu-id="4247d-145">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="4247d-145">**Platform**</span></span>  
<span data-ttu-id="4247d-146">デバイスのオペレーティング システム (Windows、iOS、Android など)</span><span class="sxs-lookup"><span data-stu-id="4247d-146">The operating system of the device (Windows, iOS, Android, etc.)</span></span>
 - <span data-ttu-id="4247d-147">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="4247d-147">**Version**</span></span>  
<span data-ttu-id="4247d-148">アプリのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="4247d-148">The version number of the app.</span></span> <span data-ttu-id="4247d-149">基幹業務アプリの場合は、アプリの完全なバージョン番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4247d-149">For line-of-business apps the full version number of the app is displayed.</span></span> <span data-ttu-id="4247d-150">バージョン番号 (フル) は、アプリのリリースを特定する番号です。</span><span class="sxs-lookup"><span data-stu-id="4247d-150">The full version number identifies a specific release of the app.</span></span> <span data-ttu-id="4247d-151">この番号は _バージョン_(_ビルド_) の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4247d-151">The number appears as _Version_(_Build_).</span></span> <span data-ttu-id="4247d-152">たとえば、2.2(2.2.17560800) のようになります。</span><span class="sxs-lookup"><span data-stu-id="4247d-152">For example, 2.2(2.2.17560800)</span></span>
 - <span data-ttu-id="4247d-153">**状態**</span><span class="sxs-lookup"><span data-stu-id="4247d-153">**Status**</span></span>  
<span data-ttu-id="4247d-154">アプリの状態。</span><span class="sxs-lookup"><span data-stu-id="4247d-154">The status of the app.</span></span>
 - <span data-ttu-id="4247d-155">**状態の詳細**</span><span class="sxs-lookup"><span data-stu-id="4247d-155">**Status details**</span></span>  
<span data-ttu-id="4247d-156">状態の詳細。</span><span class="sxs-lookup"><span data-stu-id="4247d-156">Details of the status.</span></span>
 - <span data-ttu-id="4247d-157">**最後のチェックイン**</span><span class="sxs-lookup"><span data-stu-id="4247d-157">**Last check-in**</span></span>  
<span data-ttu-id="4247d-158">デバイスが Intune と最後に同期した日付。</span><span class="sxs-lookup"><span data-stu-id="4247d-158">Date of the device last sync with Intune.</span></span>


### <a name="user-status"></a><span data-ttu-id="4247d-159">ユーザーの状態</span><span class="sxs-lookup"><span data-stu-id="4247d-159">User status</span></span>

<span data-ttu-id="4247d-160">ユーザーの状態。</span><span class="sxs-lookup"><span data-stu-id="4247d-160">User status.</span></span> <span data-ttu-id="4247d-161">ユーザーにおけるアプリのインストール状態を示すドーナツ グラフ。</span><span class="sxs-lookup"><span data-stu-id="4247d-161">A donut chart that displays the install status of the app for users.</span></span> <span data-ttu-id="4247d-162">グラフをクリックすると、デバイスの状態に関する詳細の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4247d-162">Click the graph to open a list of details about the device status.</span></span> <span data-ttu-id="4247d-163">詳細テーブルには、次の列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4247d-163">The details table includes the following columns:</span></span>
 - <span data-ttu-id="4247d-164">**名前**</span><span class="sxs-lookup"><span data-stu-id="4247d-164">**Name**</span></span>  
<span data-ttu-id="4247d-165">Azure AD でのユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="4247d-165">The name of the user in Azure AD.</span></span>
 - <span data-ttu-id="4247d-166">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="4247d-166">**User name**</span></span>  
<span data-ttu-id="4247d-167">ユーザーの一意の名前。</span><span class="sxs-lookup"><span data-stu-id="4247d-167">The unique name of the user.</span></span>
 - <span data-ttu-id="4247d-168">**インストール**</span><span class="sxs-lookup"><span data-stu-id="4247d-168">**Installations**</span></span>  
<span data-ttu-id="4247d-169">ユーザーが使用しているアプリのインストールの数。</span><span class="sxs-lookup"><span data-stu-id="4247d-169">Number of apps installs used by the user.</span></span>
 - <span data-ttu-id="4247d-170">**エラー**</span><span class="sxs-lookup"><span data-stu-id="4247d-170">**Failures**</span></span>  
<span data-ttu-id="4247d-171">ユーザーが失敗したインストールの数。</span><span class="sxs-lookup"><span data-stu-id="4247d-171">Number of failed install by the user.</span></span>
 - <span data-ttu-id="4247d-172">**未インストール**</span><span class="sxs-lookup"><span data-stu-id="4247d-172">**Not installed**</span></span>  
<span data-ttu-id="4247d-173">ユーザーがインストールしていないアプリの数。</span><span class="sxs-lookup"><span data-stu-id="4247d-173">Number of apps not installed by the user.</span></span>


## <a name="next-steps"></a><span data-ttu-id="4247d-174">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4247d-174">Next steps</span></span>

<span data-ttu-id="4247d-175">Intune データの操作の詳細については、「[Intune データ ウェアハウスを使用する](reports-nav-create-intune-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4247d-175">To learn more about working with your Intune data, see the [Use the Intune Data Warehouse](reports-nav-create-intune-reports.md).</span></span>