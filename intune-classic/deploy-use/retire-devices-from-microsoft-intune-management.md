---
title: "デバイスをインベントリから削除する"
description: "Intune では、デバイスのポリシーとポータル サイトを削除することによって Intune の管理対象からデバイスを削除する選択的ワイプとフル ワイプの両方をサポートします。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: caa0da3958fe69bbdbc26ba6eb2051a44240ae18
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="retire-devices-from-intune-management"></a><span data-ttu-id="35c7f-103">Intune の管理からデバイスを削除する</span><span class="sxs-lookup"><span data-stu-id="35c7f-103">Retire devices from Intune management</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="35c7f-104">会社所有のデバイスであっても個人所有のデバイスであっても、デバイスを Intune の管理対象から削除することが必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35c7f-104">Whether devices are corporate-owned or personally owned, eventually a managed device needs to be removed from Intune management.</span></span>

<span data-ttu-id="35c7f-105">デバイスが一定期間 Intune サービスに接続されていない場合でも、ユーザーが手動で削除しなければ、Intune からデバイスが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="35c7f-105">Devices are never removed from Intune without your intervention, even if the devices haven't connected to the Intune service for a period of time.</span></span>

<span data-ttu-id="35c7f-106">デバイスの削除が必要になる理由はさまざまです。</span><span class="sxs-lookup"><span data-stu-id="35c7f-106">You might need to retire a device for a variety of reasons:</span></span>

-   <span data-ttu-id="35c7f-107">ユーザーが予定どおりに退社する ("管理された" 退職)</span><span class="sxs-lookup"><span data-stu-id="35c7f-107">User leaves a company in a planned way (“managed” departure)</span></span>
-   <span data-ttu-id="35c7f-108">ユーザーが急に退社する (解雇や辞職など)</span><span class="sxs-lookup"><span data-stu-id="35c7f-108">User leaves abruptly (gets fired, quits, etc.).</span></span>
-   <span data-ttu-id="35c7f-109">デバイスの紛失</span><span class="sxs-lookup"><span data-stu-id="35c7f-109">Loss of device</span></span>
-   <span data-ttu-id="35c7f-110">デバイスの用途変更 (別のユーザーへの移譲、異なる目的での再使用など)</span><span class="sxs-lookup"><span data-stu-id="35c7f-110">Repurpose of a device (move to another user, reuse for a different purpose, etc.)</span></span>

<span data-ttu-id="35c7f-111">モバイル デバイスとして管理されているデバイスで選択的ワイプまたはフル ワイプを実行することも、デバイスをロックしてパスワードをリセットすることもできます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-111">You can do either a selective wipe or a full wipe on a device that's managed as a mobile device, or you can lock a device and reset its password.</span></span> <span data-ttu-id="35c7f-112">デバイスをワイプすると、ユーザーのサブスクリプションを解放して別のデバイスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-112">By wiping the device, you free up the user's subscription to add a different device.</span></span> <span data-ttu-id="35c7f-113">また、Intune クライアント ソフトウェアの管理対象 PC も削除できます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-113">You can also retire PCs that are managed with the Intune client software.</span></span>

## <a name="wipe-data-and-apps-from-devices"></a><span data-ttu-id="35c7f-114">デバイスからデータとアプリをワイプする</span><span class="sxs-lookup"><span data-stu-id="35c7f-114">Wipe data and apps from devices</span></span>
<span data-ttu-id="35c7f-115">選択的ワイプとフル ワイプは、デバイスのポリシーとポータル サイトを削除することによって Intune の管理対象からデバイスを削除します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-115">Both a selective wipe and a full wipe remove the device from Intune management by removing its policy and the company portal.</span></span> <span data-ttu-id="35c7f-116">その結果、デバイスには Microsoft SharePoint、電子メール、Office 365 などの会社リソースへのサインインに必要な資格情報がなくなります。</span><span class="sxs-lookup"><span data-stu-id="35c7f-116">As a result, the device no longer has the necessary credentials to sign in to company resources like Microsoft SharePoint, email, or Office 365.</span></span>

<span data-ttu-id="35c7f-117">[選択的ワイプ](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe)は、デバイス上の個人情報には影響を与えないため、従業員が Intune に個人のデバイスを登録している場合にお勧めの方法です。</span><span class="sxs-lookup"><span data-stu-id="35c7f-117">[Selective wipe](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) is the preferred action for employees who have enrolled their own devices in Intune because it does not affect personal information on the device.</span></span> <span data-ttu-id="35c7f-118">会社のデータだけが削除されます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-118">Only corporate data is removed.</span></span>

<span data-ttu-id="35c7f-119">他の目的に再利用する必要のあるデバイスの場合、デバイスを工場出荷時の既定の設定にリセットする[フル ワイプ](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe)も使用できます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-119">For devices that need to be repurposed, you can also use a [full wipe](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), which resets the device to factory default settings.</span></span>

### <a name="removing-user-licenses-and-managed-devices"></a><span data-ttu-id="35c7f-120">ユーザー ライセンスと管理対象デバイスを削除する</span><span class="sxs-lookup"><span data-stu-id="35c7f-120">Removing user licenses and managed devices</span></span>
<span data-ttu-id="35c7f-121">ユーザー ライセンスを削除する場合は、そのユーザーの登録済みデバイスの登録を停止します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-121">When you remove a user license, that user's enrolled devices cease to be enrolled.</span></span> <span data-ttu-id="35c7f-122">ベスト プラクティスとして、選択的ワイプを使用して、ユーザーの Intune ライセンスを削除する前に、管理対象デバイスから会社のデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c7f-122">As a best practice, you should use selective wipe to remove company data from managed devices before removing the Intune license for a user.</span></span> <span data-ttu-id="35c7f-123">ユーザー ライセンスを削除すると、デバイスをリモート アクションのターゲットにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="35c7f-123">Once you remove the user license, the device cannot be targeted for remote actions.</span></span>

## <a name="to-delete-devices-in-the-azure-active-directory-portal"></a><span data-ttu-id="35c7f-124">Azure Active Directory ポータルでデバイスを削除するには</span><span class="sxs-lookup"><span data-stu-id="35c7f-124">To delete devices in the Azure Active Directory portal</span></span>

1.  <span data-ttu-id="35c7f-125">組織の資格情報で [http://aka.ms/accessaad](http://aka.ms/accessaad) または [https://portal.office.com](https://portal.office.com) にサインインし、**[管理センター]** &gt; **[Azure AD]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-125">Sign in with your organization credentials to [http://aka.ms/accessaad](http://aka.ms/accessaad) or [https://portal.office.com](https://portal.office.com), and then choose **Admin centers** &gt; **Azure AD**.</span></span>

2.  <span data-ttu-id="35c7f-126">組織 ID がない場合は、Azure サブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-126">Create an Azure subscription if you don’t have one.</span></span> <span data-ttu-id="35c7f-127">有料アカウントがある場合、クレジット カードや支払いは不要です。</span><span class="sxs-lookup"><span data-stu-id="35c7f-127">This should not require a credit card or payment if you have a paid account.</span></span> <span data-ttu-id="35c7f-128">**[Register your free Azure Active Directory]** (無料 Azure Active Directory に登録) サブスクリプション リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-128">Choose the **Register your free Azure Active Directory** subscription link.</span></span>

4.  <span data-ttu-id="35c7f-129">**[Active Directory]** を選択し、組織を選択します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-129">Choose **Active Directory**, and then choose your organization.</span></span>

5.  <span data-ttu-id="35c7f-130">**[ユーザー]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-130">Choose the **Users** tab.</span></span>

6.  <span data-ttu-id="35c7f-131">削除するデバイスのユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-131">Choose the user whose devices you want to delete.</span></span>

7.  <span data-ttu-id="35c7f-132">**[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-132">Choose **Devices**.</span></span>

8.  <span data-ttu-id="35c7f-133">対象のデバイスを選択して、**[デバイスの削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-133">Choose the devices as appropriate, and then choose **Delete device**.</span></span> <span data-ttu-id="35c7f-134">Active Directory との次の同期時にデバイスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-134">The device will be deleted the next time it syncs with Active Directory.</span></span> <span data-ttu-id="35c7f-135">通常は 4 時間内に行われます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-135">This typically happens within four hours.</span></span> <span data-ttu-id="35c7f-136">同期の後、デバイスは管理から削除されます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-136">After syncing, the device is removed from management.</span></span> <span data-ttu-id="35c7f-137">これにより、そのユーザーのデバイス制限から 1 つのデバイスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-137">This removes one device from the device limit for this user.</span></span>

## <a name="retire-managed-computers"></a><span data-ttu-id="35c7f-138">管理対象コンピューターを削除する</span><span class="sxs-lookup"><span data-stu-id="35c7f-138">Retire managed computers</span></span>
<span data-ttu-id="35c7f-139">Intune クライアント ソフトウェアによって管理されているコンピューターを、Intune 管理コンソールで管理から削除できます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-139">Computers that Intune client software manages can be removed from management in the Intune admin console.</span></span> <span data-ttu-id="35c7f-140">これにより、コンピューターからのクライアント ソフトウェアのアンインストールと Intune ポリシーの削除も行われます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-140">This also uninstalls the client software and deletes the Intune policy from the computer.</span></span> <span data-ttu-id="35c7f-141">[Intune クライアント ソフトウェアで管理されているコンピューターの削除](retire-a-windows-pc-with-microsoft-intune.md)に関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35c7f-141">See information about [retiring computers managed with the Intune client software](retire-a-windows-pc-with-microsoft-intune.md).</span></span>

## <a name="block-access-a-device"></a><span data-ttu-id="35c7f-142">デバイスへのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="35c7f-142">Block access a device</span></span>
<span data-ttu-id="35c7f-143">デバイスを紛失した場合、または社員が会社所有のハードウェアを返却しないで退職したためにデバイスを削除する必要がある場合は、デバイスの[パスコードをリセットしてリモートでロック](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-143">If a device is lost or when you must retire a device because an employee left your company without returning a company-owned hardware, you can also [passcode reset and remotely lock](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) the device.</span></span> <span data-ttu-id="35c7f-144">これにより、会社の情報の不正使用を防止できます。ただし、デバイスを損失として会計処理することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="35c7f-144">This keeps company information from being misused, although you might have to write the device off as a loss.</span></span>

<span data-ttu-id="35c7f-145">また、その従業員の Intune のユーザー アカウントからライセンスを失効させる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="35c7f-145">You also want to revoke the license from the employee's Intune user account.</span></span> <span data-ttu-id="35c7f-146">これにより、ライセンスが解放され、そのライセンスを新しいユーザー アカウントに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-146">This frees up the license, and you can assign it to a new user account.</span></span>

## <a name="retire-hardware"></a><span data-ttu-id="35c7f-147">ハードウェアをインベントリから削除する</span><span class="sxs-lookup"><span data-stu-id="35c7f-147">Retire hardware</span></span>
<span data-ttu-id="35c7f-148">デバイス自体の寿命が訪れることがあります。</span><span class="sxs-lookup"><span data-stu-id="35c7f-148">Sometimes, it’s the device itself that has reached its end of life.</span></span> <span data-ttu-id="35c7f-149">その場合は、フル ワイプによってデバイスを[工場出荷時の設定にリセット](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)して、すべてのデータを削除し、Intune からデバイスを削除します。</span><span class="sxs-lookup"><span data-stu-id="35c7f-149">In such cases, [resetting it to factory settings](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) with a full wipe removes all data and removes the device from Intune.</span></span> <span data-ttu-id="35c7f-150">その後は、会社のポリシーに従って、ハードウェアを処分できます。</span><span class="sxs-lookup"><span data-stu-id="35c7f-150">Then, you can get rid of the hardware according to your company’s policy.</span></span>

### <a name="see-also"></a><span data-ttu-id="35c7f-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="35c7f-151">See also</span></span>
[<span data-ttu-id="35c7f-152">フル ワイプまたは選択的ワイプを使用してデータを保護する</span><span class="sxs-lookup"><span data-stu-id="35c7f-152">Help protect your data with full or selective wipe</span></span>](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)
