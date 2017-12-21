---
title: "デバイスのログを回収する"
description: "管理対象デバイスからログを回収する方法について説明します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3696a0c69b2e92b703f6ed3bf580798e49e1bbdb
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="device-logs"></a><span data-ttu-id="4f234-103">デバイス ログ</span><span class="sxs-lookup"><span data-stu-id="4f234-103">Device logs</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4f234-104">トラブルシューティングの一環として、ユーザー デバイスからログを回収することがあります。</span><span class="sxs-lookup"><span data-stu-id="4f234-104">As part of your troubleshooting efforts you might want to collect logs from user devices.</span></span> <span data-ttu-id="4f234-105">そのようなログの回収手順についてここで説明します。</span><span class="sxs-lookup"><span data-stu-id="4f234-105">Instructions for collecting those logs are described here.</span></span> <span data-ttu-id="4f234-106">通常は、デバイスにアクセスしてログを取得するか、ログを集めて送るようにユーザーに要請する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f234-106">Typically you need to access to the device to get these logs or request from the user that they collect the logs and send them to you.</span></span>

### <a name="android-logs"></a><span data-ttu-id="4f234-107">Android のログ</span><span class="sxs-lookup"><span data-stu-id="4f234-107">Android logs</span></span>
<span data-ttu-id="4f234-108">Android ログは *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files* にあります。</span><span class="sxs-lookup"><span data-stu-id="4f234-108">Android logs are located in *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.</span></span>

<span data-ttu-id="4f234-109">新型の Android デバイスなどではこのファイルが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f234-109">Sometimes the files don't appear, especially on newer Android devices.</span></span> <span data-ttu-id="4f234-110">この場合は、ユーザーに Android 用の会社のポータル アプリを開いてもらいます。</span><span class="sxs-lookup"><span data-stu-id="4f234-110">If this happens, have your users open the Company Portal app for Android.</span></span> <span data-ttu-id="4f234-111">その後、**[設定]** > **[ログのコピー]** を選択して、デバイスを再起動してもらいます。</span><span class="sxs-lookup"><span data-stu-id="4f234-111">Then they should choose **Settings**>**Copy Logs** and reboot their device.</span></span>

<span data-ttu-id="4f234-112">ユーザーからデータ ログを送信してもらう方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f234-112">For more information about how your users can send you data logs, see the following articles:</span></span>

- <span data-ttu-id="4f234-113">[詳細ログ記録を使用して、デバイスの問題解決に役立つ情報を IT 管理者に提供する](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): 詳細ログ機能を有効にする方法について説明しています。この機能により、ユーザーのすべてのデータ ログが自動で送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f234-113">[Use Verbose Logging to help your IT admin fix device issues](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): Describes how users turn on Verbose Logging, which sends you all of their data logs automatically.</span></span> <span data-ttu-id="4f234-114">詳細ログは、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4f234-114">By default, Verbose Logging is turned on.</span></span>

- [<span data-ttu-id="4f234-115">電子メールを使用して Android 診断データのログを IT 管理者に送信する</span><span class="sxs-lookup"><span data-stu-id="4f234-115">Send Android diagnostic data logs to your IT admin using email</span></span>](/intune-user-help/send-logs-to-your-it-admin-by-email-android)

- [<span data-ttu-id="4f234-116">診断データのログを USB ケーブルを使用して IT 管理者に送信する</span><span class="sxs-lookup"><span data-stu-id="4f234-116">Send diagnostic data logs to your IT admin using a USB cable</span></span>](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a><span data-ttu-id="4f234-117">iOS ログ</span><span class="sxs-lookup"><span data-stu-id="4f234-117">iOS logs</span></span>

<span data-ttu-id="4f234-118">ユーザーは登録エラーを送信できます。詳細は「[IT 管理者に iOS の登録に関するエラーを送信する](/intune-user-help/send-errors-to-your-it-admin-ios)」にあります。</span><span class="sxs-lookup"><span data-stu-id="4f234-118">Users can send you enrollment errors, as described in [Send iOS enrollment errors to your IT administrator](/intune-user-help/send-errors-to-your-it-admin-ios).</span></span>

<span data-ttu-id="4f234-119">ユーザーは「[ログを iOS デバイス向けポータル サイトの開発者に送信する](/intune-user-help/send-logs-to-microsoft-ios)」に従ってデバイスのログを送信できます。</span><span class="sxs-lookup"><span data-stu-id="4f234-119">Users can send device logs, as described in [Send iOS Device Logs](/intune-user-help/send-logs-to-microsoft-ios).</span></span>

### <a name="mac-os-x-logs"></a><span data-ttu-id="4f234-120">Mac OS X のログ</span><span class="sxs-lookup"><span data-stu-id="4f234-120">Mac OS X logs</span></span>

1. <span data-ttu-id="4f234-121">**[コンソール]** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f234-121">Open the **Console** app.</span></span>
2. <span data-ttu-id="4f234-122">**[ファイル]** で **[system.log]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f234-122">Under **FILES**, choose **system.log**.</span></span>
3. <span data-ttu-id="4f234-123">上部のメニュー バーで、**[ファイル]**  >  **[コピーを保存]** を選択し、</span><span class="sxs-lookup"><span data-stu-id="4f234-123">On the menu bar on the top, choose **File** > **Save a Copy As…**.</span></span> <span data-ttu-id="4f234-124">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="4f234-124">Then save the file.</span></span>

### <a name="windows-phone"></a><span data-ttu-id="4f234-125">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="4f234-125">Windows Phone</span></span>

<span data-ttu-id="4f234-126">Windows Phone の会社のポータル アプリで、ユーザーは省略記号 **[...]** を選択してメニューにアクセスし、**[ログの送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f234-126">In the Windows Phone Company Portal app, users choose the three dots (**…**) to access the menu, and then choose **Send Logs**.</span></span> <span data-ttu-id="4f234-127">このオプションは、会社のポータル アプリへのサインイン前と後のどちらでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="4f234-127">This option is available both before and after signing in to the Company Portal app.</span></span>

### <a name="windows"></a><span data-ttu-id="4f234-128">Windows</span><span class="sxs-lookup"><span data-stu-id="4f234-128">Windows</span></span>

<span data-ttu-id="4f234-129">Windows ポータル サイトの場合、ログは *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState* にあります。</span><span class="sxs-lookup"><span data-stu-id="4f234-129">For the Windows Company Portal, the logs are located in *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.</span></span>
