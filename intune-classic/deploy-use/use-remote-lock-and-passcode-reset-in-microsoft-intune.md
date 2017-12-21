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
ms.openlocfilehash: 5aebc95de05a588ceb99614a56a740fd8be1bb6a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a><span data-ttu-id="a4fa5-103">リモート ロックとパスコードのリセットによってデバイスを保護する</span><span class="sxs-lookup"><span data-stu-id="a4fa5-103">Help protect your devices with remote lock and passcode reset</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="a4fa5-104">Microsoft Intune には、リモート ロック機能とパスコードのリセット機能が備わっています。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-104">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span>

## <a name="lock-a-device-remotely"></a><span data-ttu-id="a4fa5-105">デバイスのリモート ロック</span><span class="sxs-lookup"><span data-stu-id="a4fa5-105">Lock a device remotely</span></span>
<span data-ttu-id="a4fa5-106">ユーザーがデバイスを紛失した場合は、リモートでデバイスをロックできます。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-106">If a user loses a device, you can lock the device remotely.</span></span> <span data-ttu-id="a4fa5-107">リモート ロックを利用するには、PIN またはパスコードをデバイスに設定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-107">The device must already have a PIN or passcode set on it before you can use remote lock.</span></span>

<span data-ttu-id="a4fa5-108">次の表に、各モバイル プラットフォームのリモート ロックの動作を示します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-108">The following table lists how remote lock works on different mobile platforms.</span></span>

|<span data-ttu-id="a4fa5-109">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="a4fa5-109">Platform</span></span>|<span data-ttu-id="a4fa5-110">リモート ロック</span><span class="sxs-lookup"><span data-stu-id="a4fa5-110">Remote lock</span></span>|
|------------|---------------|
|<span data-ttu-id="a4fa5-111">macOS</span><span class="sxs-lookup"><span data-stu-id="a4fa5-111">macOS</span></span>|<span data-ttu-id="a4fa5-112">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="a4fa5-112">Not supported</span></span>|
|<span data-ttu-id="a4fa5-113">iOS</span><span class="sxs-lookup"><span data-stu-id="a4fa5-113">iOS</span></span>|<span data-ttu-id="a4fa5-114">サポートされています</span><span class="sxs-lookup"><span data-stu-id="a4fa5-114">Supported</span></span>|
|<span data-ttu-id="a4fa5-115">Android</span><span class="sxs-lookup"><span data-stu-id="a4fa5-115">Android</span></span>|<span data-ttu-id="a4fa5-116">サポート</span><span class="sxs-lookup"><span data-stu-id="a4fa5-116">Supported</span></span>|
|<span data-ttu-id="a4fa5-117">Android for Work</span><span class="sxs-lookup"><span data-stu-id="a4fa5-117">Android for Work</span></span>|<span data-ttu-id="a4fa5-118">サポート</span><span class="sxs-lookup"><span data-stu-id="a4fa5-118">Supported</span></span>|
|<span data-ttu-id="a4fa5-119">Windows 10 (モバイル)</span><span class="sxs-lookup"><span data-stu-id="a4fa5-119">Windows 10 (mobile)</span></span>|<span data-ttu-id="a4fa5-120">サポート</span><span class="sxs-lookup"><span data-stu-id="a4fa5-120">Supported</span></span>|
|<span data-ttu-id="a4fa5-121">Windows 10 (デスクトップ)</span><span class="sxs-lookup"><span data-stu-id="a4fa5-121">Windows 10 (desktop)</span></span>|<span data-ttu-id="a4fa5-122">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="a4fa5-122">Not supported</span></span>|
|<span data-ttu-id="a4fa5-123">Windows Phone 8 および Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="a4fa5-123">Windows Phone 8 and Windows Phone 8.1</span></span>|<span data-ttu-id="a4fa5-124">サポート</span><span class="sxs-lookup"><span data-stu-id="a4fa5-124">Supported</span></span>|
|<span data-ttu-id="a4fa5-125">Windows RT 8.1 および Windows RT</span><span class="sxs-lookup"><span data-stu-id="a4fa5-125">Windows RT 8.1 and Windows RT</span></span>|<span data-ttu-id="a4fa5-126">デバイスの現在のユーザーが、デバイスを登録したユーザーと同じ場合にはサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-126">Supported if the current user of the device is the same user who enrolled the device.</span></span>|
|<span data-ttu-id="a4fa5-127">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a4fa5-127">Windows 8.1</span></span>|<span data-ttu-id="a4fa5-128">デバイスの現在のユーザーが、デバイスを登録したユーザーと同じ場合にはサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-128">Supported if the current user of the device is the same user who enrolled the device.</span></span>|

<span data-ttu-id="a4fa5-129">リモート ロックは、Intune ソフトウェア クライアントに登録されている Windows PC ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-129">Remote lock is not supported for Windows PCs enrolled with the Intune software client.</span></span>

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a><span data-ttu-id="a4fa5-130">Intune コンソールを使用してモバイル デバイスをリモートでロックする</span><span class="sxs-lookup"><span data-stu-id="a4fa5-130">Lock a mobile device remotely through the Intune console</span></span>

1.  <span data-ttu-id="a4fa5-131">[Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** &gt; **[すべてのデバイス]** &gt; **[すべてのモバイル デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-131">In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.</span></span>

2.  <span data-ttu-id="a4fa5-132">Intune に登録されているデバイスの場合は **[ダイレクト管理されているすべてのデバイス]**、それ以外の場合は **[Exchange ActiveSync で管理されているすべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-132">Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a4fa5-133">各ユーザーのデバイスを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-133">You can also navigate to a device by user.</span></span> <span data-ttu-id="a4fa5-134">**[すべてのユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-134">Choose **All Users**.</span></span> <span data-ttu-id="a4fa5-135">ユーザーの [プロパティ] ページで、**[デバイス]** を選択して、ロックするモバイル デバイスの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-135">On the user's properties page, choose **Devices**, and then choose the name of the mobile device you want to lock.</span></span>

3.  <span data-ttu-id="a4fa5-136">一覧で、ロックするデバイスを選択します (複数も可)。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-136">In the list, choose the device or devices that you want to lock.</span></span> <span data-ttu-id="a4fa5-137">タスク バーで、**[リモート タスク]** をクリックして、**[リモート ロック]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-137">On the taskbar, choose **Remote Tasks** and select **Remote Lock**.</span></span>

## <a name="reset-the-passcode-on-a-device"></a><span data-ttu-id="a4fa5-138">デバイスのパスコードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-138">Reset the passcode on a device</span></span>
<span data-ttu-id="a4fa5-139">ユーザーがパスコードを忘れた場合、デバイスからパスコードを削除したり、デバイスに新しい一時的なパスコードを強制したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-139">If a user forgets a passcode, you can help by removing the passcode from a device or by forcing a new temporary passcode on a device.</span></span> <span data-ttu-id="a4fa5-140">以下の表は、各モバイル プラットフォームでパスコードをリセットしたときの動作です。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-140">The following table lists how passcode reset works on different mobile platforms.</span></span>

|<span data-ttu-id="a4fa5-141">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="a4fa5-141">Platform</span></span>|<span data-ttu-id="a4fa5-142">パスコードのリセット</span><span class="sxs-lookup"><span data-stu-id="a4fa5-142">Passcode reset</span></span>|
|------------|------------------|
|<span data-ttu-id="a4fa5-143">macOS</span><span class="sxs-lookup"><span data-stu-id="a4fa5-143">macOS</span></span>|<span data-ttu-id="a4fa5-144">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="a4fa5-144">Not supported</span></span>|
|<span data-ttu-id="a4fa5-145">iOS</span><span class="sxs-lookup"><span data-stu-id="a4fa5-145">iOS</span></span>|<span data-ttu-id="a4fa5-146">デバイスからパスコードをクリアする場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-146">Supported for clearing the passcode from a device.</span></span> <span data-ttu-id="a4fa5-147">新しい一時的なパスコードは作成されません。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-147">Does not create a new temporary passcode.</span></span>|
|<span data-ttu-id="a4fa5-148">Android</span><span class="sxs-lookup"><span data-stu-id="a4fa5-148">Android</span></span>|<span data-ttu-id="a4fa5-149">Android 7.0 より前のバージョンでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-149">Supported on versions earlier than Android 7.0.</span></span> <span data-ttu-id="a4fa5-150">一時的なパスコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-150">Creates a temporary passcode.</span></span>|
|<span data-ttu-id="a4fa5-151">Android for Work</span><span class="sxs-lookup"><span data-stu-id="a4fa5-151">Android for Work</span></span>|<span data-ttu-id="a4fa5-152">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="a4fa5-152">Not supported</span></span>|
|<span data-ttu-id="a4fa5-153">Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="a4fa5-153">Windows 10 mobile</span></span>|<span data-ttu-id="a4fa5-154">Azure AD に参加している、Windows 10 Creator バージョン以降のモバイル デバイスでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-154">Supported for Windows 10 Creator version and later mobile devices that are Azure AD joined.</span></span>|
|<span data-ttu-id="a4fa5-155">Windows Phone 8 および Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="a4fa5-155">Windows Phone 8 and Windows Phone 8.1</span></span>|<span data-ttu-id="a4fa5-156">サポート</span><span class="sxs-lookup"><span data-stu-id="a4fa5-156">Supported</span></span>|
|<span data-ttu-id="a4fa5-157">Windows RT 8.1</span><span class="sxs-lookup"><span data-stu-id="a4fa5-157">Windows RT 8.1</span></span>|<span data-ttu-id="a4fa5-158">サポートされません</span><span class="sxs-lookup"><span data-stu-id="a4fa5-158">Not Supported</span></span>|
|<span data-ttu-id="a4fa5-159">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a4fa5-159">Windows 8.1</span></span>|<span data-ttu-id="a4fa5-160">サポートされません</span><span class="sxs-lookup"><span data-stu-id="a4fa5-160">Not Supported</span></span>|
|<span data-ttu-id="a4fa5-161">Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="a4fa5-161">Windows 10 desktop</span></span>|<span data-ttu-id="a4fa5-162">サポートされません</span><span class="sxs-lookup"><span data-stu-id="a4fa5-162">Not Supported</span></span>|

<span data-ttu-id="a4fa5-163">パスコード リセットは、Intune ソフトウェア クライアントに登録されている Windows PC ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-163">Passcode reset is not supported for Windows PCs enrolled with the Intune software client.</span></span>

### <a name="reset-a-passcode"></a><span data-ttu-id="a4fa5-164">パスコードのリセット</span><span class="sxs-lookup"><span data-stu-id="a4fa5-164">Reset a passcode</span></span>

1.  <span data-ttu-id="a4fa5-165">[Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** &gt; **[すべてのデバイス]** &gt; **[すべてのモバイル デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-165">In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.</span></span>

2.  <span data-ttu-id="a4fa5-166">Intune に登録されているデバイスの場合は **[ダイレクト管理されているすべてのデバイス]**、それ以外の場合は **[Exchange ActiveSync で管理されているすべてのデバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-166">Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a4fa5-167">各ユーザーのデバイスを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-167">You can also navigate to a device by user.</span></span> <span data-ttu-id="a4fa5-168">**[すべてのユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-168">Click **All Users**.</span></span> <span data-ttu-id="a4fa5-169">ユーザーの [プロパティ] ページで、**[デバイス]** をクリックして、ワイプするモバイル デバイスの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-169">On the user's properties page, click **Devices**, and then click the name of the mobile device you want to wipe.</span></span>

3.  <span data-ttu-id="a4fa5-170">一覧で、ロックするデバイスを選択します (複数も可)。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-170">In the list, choose the device or devices that you want to lock.</span></span> <span data-ttu-id="a4fa5-171">タスク バーで、**[リモート タスク]** をクリックして、**[パスコードのリセット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fa5-171">On the taskbar, choose **Remote Tasks** and select **Passcode Reset**.</span></span>


### <a name="see-also"></a><span data-ttu-id="a4fa5-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4fa5-172">See also</span></span>
<span data-ttu-id="a4fa5-173">[デバイスをインベントリから削除する](retire-devices-from-microsoft-intune-management.md)および[Windows のデバイス データ管理の選択的ワイプ](http://technet.microsoft.com/library/dn486874.aspx)</span><span class="sxs-lookup"><span data-stu-id="a4fa5-173">[Retire devices](retire-devices-from-microsoft-intune-management.md) and [Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx)</span></span>
