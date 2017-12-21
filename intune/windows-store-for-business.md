---
title: "ビジネス向け Microsoft ストア アプリの管理"
titlesuffix: Azure portal
description: "ビジネス向け Microsoft ストアから取得したアプリを同期して Intune に取り込み、そのアプリを割り当てて追跡します。\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecb5a310e8b869deb493bc5554029d641ba419c3
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a><span data-ttu-id="06bb8-103">ビジネス向け Microsoft ストアから購入したアプリを Microsoft Intune で管理する方法</span><span class="sxs-lookup"><span data-stu-id="06bb8-103">How to manage apps you purchased from the Microsoft Store for Business with Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<span data-ttu-id="06bb8-104">[ビジネス向け Microsoft ストア](https://www.microsoft.com/business-store)では、組織用のアプリを見つけて、個別または大量に購入することができます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-104">The [Microsoft Store for Business](https://www.microsoft.com/business-store) gives you a place to find and purchase apps for your organization, individually, or in volume.</span></span> <span data-ttu-id="06bb8-105">Microsoft Intune にストアを接続することで、Azure Portal からボリューム購入アプリを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-105">By connecting the store to Microsoft Intune, you can manage volume-purchased apps from the Azure portal.</span></span> <span data-ttu-id="06bb8-106">たとえば、</span><span class="sxs-lookup"><span data-stu-id="06bb8-106">For example:</span></span>
* <span data-ttu-id="06bb8-107">ストアから購入したアプリの一覧を Intune に同期することができます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-107">You can synchronize the list of apps you have purchased from the store with Intune.</span></span>
* <span data-ttu-id="06bb8-108">同期されているアプリは Intune 管理コンソールに表示され、他のアプリと同様に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-108">Apps that are synchronized appear in the Intune administration console; you can assign these apps like any other apps.</span></span>
* <span data-ttu-id="06bb8-109">使用可能なライセンス数、および Intune 管理コンソールで使用中のライセンス数を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-109">You can track how many licenses are available, and how many are being used in the Intune administration console.</span></span>
* <span data-ttu-id="06bb8-110">使用可能なライセンス数が不足している場合、Intune はアプリの割り当てとインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="06bb8-110">Intune blocks assignment and installation of apps if there are an insufficient number of licenses available.</span></span>
* <span data-ttu-id="06bb8-111">ユーザーが企業を退社したとき、または管理者がユーザーとユーザー デバイスを削除したときに、ビジネス向け Windows ストアによって管理されているアプリはライセンスを自動的に取り消します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-111">Apps managed by Windows Store for Business will automatically revoke licenses when a user leaves the enterprise, or when the administrator removes the user and the user devices.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="06bb8-112">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="06bb8-112">Before you start</span></span>

<span data-ttu-id="06bb8-113">ビジネス向け Microsoft ストアのアプリを同期して割り当てる前に、以下のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="06bb8-113">Review the following information before you start syncing and assigning apps from the Microsoft Store for Business:</span></span>

- <span data-ttu-id="06bb8-114">組織のモバイル デバイス管理機関として Intune を構成します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-114">Configure Intune as the mobile device management authority for your organization.</span></span>
- <span data-ttu-id="06bb8-115">ビジネス向け Microsoft ストアのアカウントにサインアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="06bb8-115">You must have signed up for an account on the Microsoft Store for Business.</span></span>
- <span data-ttu-id="06bb8-116">Intune に Windows ビジネス ストア アカウントを関連付けた後で別のアカウントに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="06bb8-116">Once you have associated a Windows Business Store account with Intune, you cannot change to a different account in the future.</span></span>
- <span data-ttu-id="06bb8-117">Intune に対して、ストアから購入したアプリを手動で追加したり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="06bb8-117">Apps purchased from the store cannot be manually added to or deleted from Intune.</span></span> <span data-ttu-id="06bb8-118">ビジネス向け Microsoft ストアとの同期のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="06bb8-118">They can only be synchronized with the Microsoft Store for Business.</span></span>
- <span data-ttu-id="06bb8-119">Intune は、ビジネス向け Microsoft ストアから購入したオンラインおよびオフラインのライセンスされたアプリを同期します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-119">Intune synchronizes both online and offline licensed apps you have purchased from the Microsoft Store for Business.</span></span>
- <span data-ttu-id="06bb8-120">Intune には、無料のオフライン アプリのみを同期することができます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-120">Only offline apps that are free of charge can be synced to Intune.</span></span>
- <span data-ttu-id="06bb8-121">この機能を使用するには、デバイスが Active Directory Domain Services またはワークプレースに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="06bb8-121">To use this capability, devices must be joined to Active Directory Domain Services, or workplace-joined.</span></span>
- <span data-ttu-id="06bb8-122">登録デバイスは、1511 リリースの Windows 10 以降を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="06bb8-122">Enrolled devices must be using the 1511 release of Windows 10 or later.</span></span>

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a><span data-ttu-id="06bb8-123">Intune にビジネス向け Microsoft ストア アカウントを関連付ける</span><span class="sxs-lookup"><span data-stu-id="06bb8-123">Associate your Microsoft Store for Business account with Intune</span></span>
<span data-ttu-id="06bb8-124">Intune コンソールで同期を有効にする前に、以下の手順に従って、Intune を管理ツールとして使用するようにストア アカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06bb8-124">Before you enable synchronization in the Intune console, you must configure your store account to use Intune as a management tool:</span></span>
1. <span data-ttu-id="06bb8-125">Intune へのサインインに使用したものと同じテナント アカウントを使用して、ビジネス ストアにサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-125">Ensure that you sign into the Business Store using the same tenant account you use to sign into Intune.</span></span>
2. <span data-ttu-id="06bb8-126">ビジネス ストアで、**[設定]** > **[管理ツール]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-126">In the Business Store, choose **Settings** > **Management tools**.</span></span>
3. <span data-ttu-id="06bb8-127">[管理ツール] ページで、**[管理ツールの追加]** を選択し、**[Microsoft Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-127">On the Management tools page, choose **Add a management tool**, and choose **Microsoft Intune**.</span></span>

> [!NOTE]
> <span data-ttu-id="06bb8-128">これまでは、アプリを割り当てるための管理ツールをビジネス向け Microsoft ストアに 1 つしか関連付けることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="06bb8-128">You could previously only associate one management tool to assign apps with the Microsoft Store for Business.</span></span> <span data-ttu-id="06bb8-129">これからは、複数のツール (Intune や Configuration Manager など) をストアに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-129">You can now associate multiple management tools with the store, for example, Intune and Configuration Manager.</span></span>

<span data-ttu-id="06bb8-130">これで、作業を続行し、Intune コンソールで同期を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-130">You can now continue, and set up synchronization in the Intune console.</span></span>

## <a name="configure-synchronization"></a><span data-ttu-id="06bb8-131">同期を構成する</span><span class="sxs-lookup"><span data-stu-id="06bb8-131">Configure synchronization</span></span>

1. <span data-ttu-id="06bb8-132">Azure ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="06bb8-132">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="06bb8-133">**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-133">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="06bb8-134">**[Intune]** ブレードで、**[モバイル アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-134">On the **Intune** blade, choose **Mobile apps**.</span></span>
1. <span data-ttu-id="06bb8-135">**[モバイル アプリ]** ブレードで、**[セットアップ]** > **[ビジネス向け Microsoft ストア]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-135">On the **Mobile Apps** blade, choose **Setup** > **Microsoft Store for Business**.</span></span>
2. <span data-ttu-id="06bb8-136">**[有効にする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06bb8-136">Click **Enable**.</span></span>
3. <span data-ttu-id="06bb8-137">ビジネス向け Microsoft ストアにまだサインアップしていない場合は、前に詳しく説明したように、サインアップ用のリンクをクリックしてサインアップし、アカウントを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-137">If you haven't already done so, click the link to sign up for the Microsoft Store for Business and associate your account as detailed previously.</span></span>
5. <span data-ttu-id="06bb8-138">**[言語]** ドロップダウン リストで、Azure Portal で表示するビジネス向け Microsoft ストアのアプリに使用する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-138">From the **Language** drop-down list, choose the language in which apps from the Microsoft Store for Business is displayed in the Azure portal.</span></span> <span data-ttu-id="06bb8-139">アプリは、どの言語を使用して表示するかに関係なく、使用可能なエンド ユーザーの言語でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-139">Regardless of the language in which they are displayed, they are installed in the end user's language when available.</span></span>
6. <span data-ttu-id="06bb8-140">**[同期]** をクリックして、Microsoft ストアから購入したアプリを Intune に取り込みます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-140">Click **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

## <a name="synchronize-apps"></a><span data-ttu-id="06bb8-141">アプリを同期する</span><span class="sxs-lookup"><span data-stu-id="06bb8-141">Synchronize apps</span></span>

1. <span data-ttu-id="06bb8-142">**[モバイル アプリ]** ワークロードで、**[セットアップ]** > **[ビジネス向け Microsoft ストア]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-142">In the **Mobile apps** workload, choose **Setup** > **Microsoft Store for Business**.</span></span>
2. <span data-ttu-id="06bb8-143">**[同期]** をクリックして、Microsoft ストアから購入したアプリを Intune に取り込みます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-143">Click **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

## <a name="assign-apps"></a><span data-ttu-id="06bb8-144">アプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="06bb8-144">Assign apps</span></span>

<span data-ttu-id="06bb8-145">他の Intune アプリを割り当てる場合と同じように、ストアからアプリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-145">You assign apps from the store in the same way you assign any other Intune app.</span></span> <span data-ttu-id="06bb8-146">詳細については、「[How to assign apps to groups with Microsoft Intune (Microsoft Intune を使ってアプリをグループに割り当てる方法)](apps-deploy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06bb8-146">For more information, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md).</span></span> <span data-ttu-id="06bb8-147">ただし、**[すべてのアプリ]** ページからではなく、**[ライセンスされたアプリ]** ページからアプリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-147">However, instead of assigning apps from the **All Apps** page, you assign them from the **Licensed Apps** page.</span></span>

<span data-ttu-id="06bb8-148">オフライン アプリの対象は、ユーザー グループ、デバイス グループ、またはユーザーとデバイスのグループとすることができます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-148">Offline apps can be targeted to user groups, device groups, or groups with users and devices.</span></span>
<span data-ttu-id="06bb8-149">オフライン アプリは、デバイス上の特定のユーザーまたはデバイス上のすべてのユーザーに対してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-149">Offline apps can be installed for a specific user on a device or for all users on a device.</span></span> 


<span data-ttu-id="06bb8-150">ビジネス向け Microsoft ストア アプリを割り当てると、アプリをインストールする各ユーザーによってライセンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="06bb8-150">When you assign a Microsoft Store for Business app, a license is used by each user who installs the app.</span></span> <span data-ttu-id="06bb8-151">割り当てられたアプリに対して使用可能なライセンスをすべて使用すると、それ以上コピーを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="06bb8-151">If you use all of the available licenses for an assigned app, you cannot assign any more copies.</span></span> <span data-ttu-id="06bb8-152">次の操作のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="06bb8-152">Take one of the following actions:</span></span>
* <span data-ttu-id="06bb8-153">一部のデバイスからアプリをアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="06bb8-153">Uninstall the app from some devices.</span></span>
* <span data-ttu-id="06bb8-154">現在の割り当ての範囲を絞り、十分なライセンスがあるユーザーのみを対象にする。</span><span class="sxs-lookup"><span data-stu-id="06bb8-154">Reduce the scope of the current assignment, targeting only the users you have sufficient licenses for.</span></span>
* <span data-ttu-id="06bb8-155">ビジネス向け Microsoft ストアからアプリのコピーをさらに購入する。</span><span class="sxs-lookup"><span data-stu-id="06bb8-155">Buy more copies of the app from the Microsoft Store for Business.</span></span>


