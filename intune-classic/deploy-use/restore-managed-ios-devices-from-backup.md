---
title: "Intune の管理対象 iOS デバイスをバックアップから復元する"
description: "バックアップから復元した後にデバイスを再登録する方法のエンド ユーザー向けガイダンスについて説明します。"
keywords: "復元, 管理, iOS"
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: dc1c81ab3291d5b895c6e81e89d8891d35ee6b1c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="restore-intune-managed-ios-devices-from-backup"></a><span data-ttu-id="1ae4f-104">Intune の管理対象 iOS デバイスをバックアップから復元する</span><span class="sxs-lookup"><span data-stu-id="1ae4f-104">Restore Intune managed iOS devices from backup</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1ae4f-105">ユーザーが新しいデバイスを入手した場合など、管理者またはユーザーがバックアップから iOS デバイスを復元する状況があります。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-105">There will be cases when you or your users will need to restore an iOS device from a backup, such as when a user gets a new device.</span></span> <span data-ttu-id="1ae4f-106">このトピックでは、デバイスの復元後に必要になる可能性がある Intune 管理のセットアップについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-106">This topic explains additional steps that you might have to take to set up Intune management after restoring the device.</span></span>

## <a name="restoring-backups-onto-the-same-device"></a><span data-ttu-id="1ae4f-107">同じデバイスにバックアップを復元する</span><span class="sxs-lookup"><span data-stu-id="1ae4f-107">Restoring backups onto the same device</span></span>

<span data-ttu-id="1ae4f-108">同じデバイスにバックアップを復元する場合、そのデバイスの登録状態も復元されます。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-108">If the backup is being restored onto the same device, then the enrollment state on that device will also be restored.</span></span> <span data-ttu-id="1ae4f-109">追加の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-109">There is no need for additional action.</span></span>

## <a name="restoring-backups-onto-different-devices"></a><span data-ttu-id="1ae4f-110">別のデバイスにバックアップを復元する</span><span class="sxs-lookup"><span data-stu-id="1ae4f-110">Restoring backups onto different devices</span></span>

<span data-ttu-id="1ae4f-111">別のデバイスにバックアップを復元する場合、登録の状態は新しいデバイスに自動的に復元されません。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-111">If the backup is being restored onto a different device, then the enrollment state is not automatically restored on the new device.</span></span> <span data-ttu-id="1ae4f-112">ユーザーはポータル サイト アプリ バージョン 2.1.22 以降で、通常の登録手順に従って [iOS デバイスを Intune に登録する](/intune-user-help/enroll-your-device-in-intune-ios)必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-112">Users need to follow standard enrollment steps in the Company Portal app on app version 2.1.22 or later to [enroll their iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>

> [!NOTE]
> <span data-ttu-id="1ae4f-113">条件付きアクセス ポリシーでエンド ユーザーを対象にしている場合、再登録するまでエンド ユーザーは会社の電子メールにはアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-113">If you’re targeting your end users with conditional access policies, they will not be able to access corporate email until after they re-enroll.</span></span>

> [!TIP]
> <span data-ttu-id="1ae4f-114">ユーザーが通信するには、次のような手順が必要になります。まず、新しいデバイスで登録する場合、ポータル サイト アプリがバージョン 2.1.22 以降であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-114">An example communication for your users could be as follows: To enroll on your new device, make sure that the Company Portal app is on version 2.1.22 or later.</span></span> <span data-ttu-id="1ae4f-115">バージョンを確認するには、ポータル サイト アプリを開き、右上にある [メニュー] ボタンをタップし、[バージョン情報] をタップします。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-115">To check the version, open the Company Portal app, tap the Menu button in the upper right, and then tap About.</span></span> <span data-ttu-id="1ae4f-116">古いバージョンの場合はポータル サイト アプリを終了し、App Store を開きます。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-116">If you are on an earlier version, exit the Company Portal app and open the App Store.</span></span> <span data-ttu-id="1ae4f-117">右下の [更新プログラム] ボタンをタップし、一覧のポータル サイト項目の横にある [更新] ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-117">Tap the Updates button in the bottom right corner, then tap the Update button next to the Company Portal item in the list.</span></span> <span data-ttu-id="1ae4f-118">更新が完了したら、ポータル サイト アプリを起動し、[iOS デバイスを Intune に登録します](/intune-user-help/enroll-your-device-in-intune-ios)。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-118">Once the update completes, launch the Company Portal app and [enroll your iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>

## <a name="resolving-known-issues-with-restores"></a><span data-ttu-id="1ae4f-119">復元に関する既知の問題の解決</span><span class="sxs-lookup"><span data-stu-id="1ae4f-119">Resolving known issues with restores</span></span>

<span data-ttu-id="1ae4f-120">会社のポータル バージョン 2.1.21 以前を使用しているとき、デバイスを復元して、会社のポータル アプリを起動すると、問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-120">Users may experience some difficulty if they restored their device and launched the Company Portal app when they still had Company Portal version 2.1.21 or earlier.</span></span> <span data-ttu-id="1ae4f-121">これらの問題は、ユーザーの状況に適した手順を実行することで対処できます。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-121">These difficulties can be addressed by taking the appropriate steps for the user’s situation.</span></span>

### <a name="for-users-who-will-only-use-their-new-device"></a><span data-ttu-id="1ae4f-122">新しいデバイスのみを使用するユーザーの場合</span><span class="sxs-lookup"><span data-stu-id="1ae4f-122">For users who will only use their new device</span></span>
<span data-ttu-id="1ae4f-123">会社のポータル アプリを起動し、現在のデバイス タイルを選択して __[削除]__ ボタンをタップすることにより、登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-123">Launch the Company Portal app and unenroll by selecting the current device tile and tapping the __Remove__ button.</span></span> <span data-ttu-id="1ae4f-124">削除した後、標準の登録手順に従って、[Intune に iOS デバイスを登録](/intune-user-help/enroll-your-device-in-intune-ios)します。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-124">After removing, follow the standard enrollment steps to [enroll an iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="for-users-who-will-use-both-their-old-and-new-devices"></a><span data-ttu-id="1ae4f-125">新旧両方のデバイスを使用するユーザーの場合</span><span class="sxs-lookup"><span data-stu-id="1ae4f-125">For users who will use both their old and new devices</span></span>
<span data-ttu-id="1ae4f-126">__[設定]__ > __[Safari]__ > __[Clear History and Website Data]__ (履歴と Web サイトのデータをクリア) をタップして、Safari から Cookie を消去します。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-126">Clear cookies from Safari by tapping __Settings__ > __Safari__ > __Clear History and Website Data__.</span></span> <span data-ttu-id="1ae4f-127">消去後、会社のポータル アプリをアンインストールして再インストールし、標準登録手順で [Intune に iOS デバイスを登録](/intune-user-help/enroll-your-device-in-intune-ios)します。</span><span class="sxs-lookup"><span data-stu-id="1ae4f-127">After clearing,  uninstall and reinstall the Company Portal app, then follow the standard enrollment steps to [enroll an iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>
