---
title: "リモート ロックとパスコードのリセット"
description: "Intune には、リモート ロック機能とパスコードのリセット機能の両方が備わっています。"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.custom: intune-classic
ms.openlocfilehash: fc1cad418904de335b434a3726e2772d0558b303
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a><span data-ttu-id="41f1f-103">リモート ロックとパスコードのリセットによってデバイスを保護する</span><span class="sxs-lookup"><span data-stu-id="41f1f-103">Help protect your devices with remote lock and passcode reset</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="41f1f-104">Microsoft Intune には、リモート ロック機能とパスコードのリセット機能が備わっています。</span><span class="sxs-lookup"><span data-stu-id="41f1f-104">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span>

## <a name="lock-a-device-remotely"></a><span data-ttu-id="41f1f-105">デバイスのリモート ロック</span><span class="sxs-lookup"><span data-stu-id="41f1f-105">Lock a device remotely</span></span>
<span data-ttu-id="41f1f-106">ユーザーがデバイスを紛失した場合は、リモートでデバイスをロックできます。</span><span class="sxs-lookup"><span data-stu-id="41f1f-106">If a user loses a device, you can lock the device remotely.</span></span> <span data-ttu-id="41f1f-107">リモート ロックを利用するには、PIN またはパスコードをデバイスに設定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="41f1f-107">The device must already have a PIN or passcode set on it before you can use remote lock.</span></span>

<span data-ttu-id="41f1f-108">次の表に、各モバイル プラットフォームのリモート ロックの動作を示します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-108">The following table lists how remote lock works on different mobile platforms.</span></span>

|<span data-ttu-id="41f1f-109">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="41f1f-109">Platform</span></span>|<span data-ttu-id="41f1f-110">リモート ロック</span><span class="sxs-lookup"><span data-stu-id="41f1f-110">Remote lock</span></span>|
|------------|---------------|
|<span data-ttu-id="41f1f-111">macOS</span><span class="sxs-lookup"><span data-stu-id="41f1f-111">macOS</span></span>|<span data-ttu-id="41f1f-112">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="41f1f-112">Not supported</span></span>|
|<span data-ttu-id="41f1f-113">iOS</span><span class="sxs-lookup"><span data-stu-id="41f1f-113">iOS</span></span>|<span data-ttu-id="41f1f-114">サポートされています</span><span class="sxs-lookup"><span data-stu-id="41f1f-114">Supported</span></span>|
|<span data-ttu-id="41f1f-115">Android</span><span class="sxs-lookup"><span data-stu-id="41f1f-115">Android</span></span>|<span data-ttu-id="41f1f-116">サポート</span><span class="sxs-lookup"><span data-stu-id="41f1f-116">Supported</span></span>|
|<span data-ttu-id="41f1f-117">Android for Work</span><span class="sxs-lookup"><span data-stu-id="41f1f-117">Android for Work</span></span>|<span data-ttu-id="41f1f-118">サポート</span><span class="sxs-lookup"><span data-stu-id="41f1f-118">Supported</span></span>|
|<span data-ttu-id="41f1f-119">Windows 10 (モバイル)</span><span class="sxs-lookup"><span data-stu-id="41f1f-119">Windows 10 (mobile)</span></span>|<span data-ttu-id="41f1f-120">サポート</span><span class="sxs-lookup"><span data-stu-id="41f1f-120">Supported</span></span>|
|<span data-ttu-id="41f1f-121">Windows 10 (デスクトップ)</span><span class="sxs-lookup"><span data-stu-id="41f1f-121">Windows 10 (desktop)</span></span>|<span data-ttu-id="41f1f-122">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="41f1f-122">Not supported</span></span>|
|<span data-ttu-id="41f1f-123">Windows Phone 8 および Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="41f1f-123">Windows Phone 8 and Windows Phone 8.1</span></span>|<span data-ttu-id="41f1f-124">サポート</span><span class="sxs-lookup"><span data-stu-id="41f1f-124">Supported</span></span>|
|<span data-ttu-id="41f1f-125">Windows RT 8.1 および Windows RT</span><span class="sxs-lookup"><span data-stu-id="41f1f-125">Windows RT 8.1 and Windows RT</span></span>|<span data-ttu-id="41f1f-126">デバイスの現在のユーザーが、デバイスを登録したユーザーと同じ場合にはサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41f1f-126">Supported if the current user of the device is the same user who enrolled the device.</span></span>|
|<span data-ttu-id="41f1f-127">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="41f1f-127">Windows 8.1</span></span>|<span data-ttu-id="41f1f-128">デバイスの現在のユーザーが、デバイスを登録したユーザーと同じ場合にはサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41f1f-128">Supported if the current user of the device is the same user who enrolled the device.</span></span>|

<span data-ttu-id="41f1f-129">リモート ロックは、Intune ソフトウェア クライアントに登録されている Windows PC ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="41f1f-129">Remote lock is not supported for Windows PCs enrolled with the Intune software client.</span></span>

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a><span data-ttu-id="41f1f-130">Intune コンソールを使用してモバイル デバイスをリモートでロックする</span><span class="sxs-lookup"><span data-stu-id="41f1f-130">Lock a mobile device remotely through the Intune console</span></span>

1.  <span data-ttu-id="41f1f-131">[Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** &gt; **[すべてのデバイス]** &gt; **[すべてのモバイル デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-131">In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.</span></span>

2.  <span data-ttu-id="41f1f-132">Intune に登録されているデバイスの場合は **[ダイレクト管理されているすべてのデバイス]**、それ以外の場合は **[Exchange ActiveSync で管理されているすべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-132">Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.</span></span>

    > [!TIP]
    > <span data-ttu-id="41f1f-133">各ユーザーのデバイスを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="41f1f-133">You can also navigate to a device by user.</span></span> <span data-ttu-id="41f1f-134">**[すべてのユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-134">Choose **All Users**.</span></span> <span data-ttu-id="41f1f-135">ユーザーの [プロパティ] ページで、**[デバイス]** を選択して、ロックするモバイル デバイスの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-135">On the user's properties page, choose **Devices**, and then choose the name of the mobile device you want to lock.</span></span>

3.  <span data-ttu-id="41f1f-136">一覧で、ロックするデバイスを選択します (複数も可)。</span><span class="sxs-lookup"><span data-stu-id="41f1f-136">In the list, choose the device or devices that you want to lock.</span></span> <span data-ttu-id="41f1f-137">タスク バーで、**[リモート タスク]** をクリックして、**[リモート ロック]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-137">On the taskbar, choose **Remote Tasks** and select **Remote Lock**.</span></span>

## <a name="reset-the-passcode-on-a-device"></a><span data-ttu-id="41f1f-138">デバイスのパスコードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="41f1f-138">Reset the passcode on a device</span></span>
<span data-ttu-id="41f1f-139">ユーザーがパスコードを忘れた場合、デバイスからパスコードを削除したり、デバイスに新しい一時的なパスコードを強制したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="41f1f-139">If a user forgets a passcode, you can help by removing the passcode from a device or by forcing a new temporary passcode on a device.</span></span> <span data-ttu-id="41f1f-140">以下の表は、各モバイル プラットフォームでパスコードをリセットしたときの動作です。</span><span class="sxs-lookup"><span data-stu-id="41f1f-140">The following table lists how passcode reset works on different mobile platforms.</span></span>

|<span data-ttu-id="41f1f-141">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="41f1f-141">Platform</span></span>|<span data-ttu-id="41f1f-142">パスコードのリセット</span><span class="sxs-lookup"><span data-stu-id="41f1f-142">Passcode reset</span></span>|
|------------|------------------|
|<span data-ttu-id="41f1f-143">macOS</span><span class="sxs-lookup"><span data-stu-id="41f1f-143">macOS</span></span>|<span data-ttu-id="41f1f-144">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="41f1f-144">Not supported</span></span>|
|<span data-ttu-id="41f1f-145">iOS</span><span class="sxs-lookup"><span data-stu-id="41f1f-145">iOS</span></span>|<span data-ttu-id="41f1f-146">デバイスからパスコードをクリアする場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41f1f-146">Supported for clearing the passcode from a device.</span></span> <span data-ttu-id="41f1f-147">新しい一時的なパスコードは作成されません。</span><span class="sxs-lookup"><span data-stu-id="41f1f-147">Does not create a new temporary passcode.</span></span>|
|<span data-ttu-id="41f1f-148">Android</span><span class="sxs-lookup"><span data-stu-id="41f1f-148">Android</span></span>|<span data-ttu-id="41f1f-149">Android 7.0 より前のバージョンでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41f1f-149">Supported on versions earlier than Android 7.0.</span></span> <span data-ttu-id="41f1f-150">一時的なパスコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-150">Creates a temporary passcode.</span></span>|
|<span data-ttu-id="41f1f-151">Android for Work</span><span class="sxs-lookup"><span data-stu-id="41f1f-151">Android for Work</span></span>|<span data-ttu-id="41f1f-152">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="41f1f-152">Not supported</span></span>|
|<span data-ttu-id="41f1f-153">Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="41f1f-153">Windows 10 mobile</span></span>|<span data-ttu-id="41f1f-154">Azure AD に参加している、Windows 10 Creator バージョン以降のモバイル デバイスでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41f1f-154">Supported for Windows 10 Creator version and later mobile devices that are Azure AD joined.</span></span>|
|<span data-ttu-id="41f1f-155">Windows Phone 8 および Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="41f1f-155">Windows Phone 8 and Windows Phone 8.1</span></span>|<span data-ttu-id="41f1f-156">サポート</span><span class="sxs-lookup"><span data-stu-id="41f1f-156">Supported</span></span>|
|<span data-ttu-id="41f1f-157">Windows RT 8.1</span><span class="sxs-lookup"><span data-stu-id="41f1f-157">Windows RT 8.1</span></span>|<span data-ttu-id="41f1f-158">サポートされません</span><span class="sxs-lookup"><span data-stu-id="41f1f-158">Not Supported</span></span>|
|<span data-ttu-id="41f1f-159">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="41f1f-159">Windows 8.1</span></span>|<span data-ttu-id="41f1f-160">サポートされません</span><span class="sxs-lookup"><span data-stu-id="41f1f-160">Not Supported</span></span>|
|<span data-ttu-id="41f1f-161">Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="41f1f-161">Windows 10 desktop</span></span>|<span data-ttu-id="41f1f-162">サポートされません</span><span class="sxs-lookup"><span data-stu-id="41f1f-162">Not Supported</span></span>|

<span data-ttu-id="41f1f-163">パスコード リセットは、Intune ソフトウェア クライアントに登録されている Windows PC ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="41f1f-163">Passcode reset is not supported for Windows PCs enrolled with the Intune software client.</span></span>

### <a name="reset-a-passcode"></a><span data-ttu-id="41f1f-164">パスコードのリセット</span><span class="sxs-lookup"><span data-stu-id="41f1f-164">Reset a passcode</span></span>

1.  <span data-ttu-id="41f1f-165">[Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** &gt; **[すべてのデバイス]** &gt; **[すべてのモバイル デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-165">In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.</span></span>

2.  <span data-ttu-id="41f1f-166">Intune に登録されているデバイスの場合は **[ダイレクト管理されているすべてのデバイス]**、それ以外の場合は **[Exchange ActiveSync で管理されているすべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-166">Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.</span></span>

    > [!TIP]
    > <span data-ttu-id="41f1f-167">各ユーザーのデバイスを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="41f1f-167">You can also navigate to a device by user.</span></span> <span data-ttu-id="41f1f-168">**[すべてのユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41f1f-168">Click **All Users**.</span></span> <span data-ttu-id="41f1f-169">ユーザーの [プロパティ] ページで、**[デバイス]** をクリックして、ワイプするモバイル デバイスの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41f1f-169">On the user's properties page, click **Devices**, and then click the name of the mobile device you want to wipe.</span></span>

3.  <span data-ttu-id="41f1f-170">一覧で、ロックするデバイスを選択します (複数も可)。</span><span class="sxs-lookup"><span data-stu-id="41f1f-170">In the list, choose the device or devices that you want to lock.</span></span> <span data-ttu-id="41f1f-171">タスク バーで、**[リモート タスク]** をクリックして、**[パスコードのリセット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41f1f-171">On the taskbar, choose **Remote Tasks** and select **Passcode Reset**.</span></span>


### <a name="see-also"></a><span data-ttu-id="41f1f-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="41f1f-172">See also</span></span>
<span data-ttu-id="41f1f-173">[デバイスをインベントリから削除する](retire-devices-from-microsoft-intune-management.md)および[Windows のデバイス データ管理の選択的ワイプ](http://technet.microsoft.com/library/dn486874.aspx)</span><span class="sxs-lookup"><span data-stu-id="41f1f-173">[Retire devices](retire-devices-from-microsoft-intune-management.md) and [Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx)</span></span>
