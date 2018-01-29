---
title: "会社のサポートに Windows 10 デバイスのログを送信する | Microsoft Docs"
description: "Intune に Windows 10 1511 デバイスを登録する"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 038747fb-5b52-47c4-a2b6-f9218da4cfe1
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 815d50b556b5b179cd29090b55877943b50a105f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="send-logs-to-your-company-support-from-the-settings-app-for-windows-10"></a><span data-ttu-id="a1ca5-103">会社のサポートに、設定アプリから Windows 10 のログを送信する</span><span class="sxs-lookup"><span data-stu-id="a1ca5-103">Send logs to your company support from the Settings app for Windows 10</span></span>

<span data-ttu-id="a1ca5-104">会社で管理している Windows 10 デバイスを使用している間にエラーが発生した場合は、会社のサポートによる問題のトラブルシューティングに役立つように、エラー情報を電子メールで送信できます。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-104">If you get an error while you’re using your Windows 10 device that is managed by your company, you can help your company support troubleshoot the problem by sending them information through email.</span></span> <span data-ttu-id="a1ca5-105">この情報は、デバイスの _diagnostic log_ という名前の特殊なドキュメントに保存されています。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-105">This information is kept on your device in a special document called a _diagnostic log_.</span></span>

1. <span data-ttu-id="a1ca5-106">**[スタート] メニュー**に移動し、**[設定]** ボタンを選択して、**[Windows の設定]** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-106">Open the Windows **Settings** app by going to the **Start menu** and selecting the **Settings** button.</span></span> <span data-ttu-id="a1ca5-107">検索バーで "設定" を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-107">You can also search for "settings" in the search bar.</span></span>
2. <span data-ttu-id="a1ca5-108">**[アカウント]** > **[職場または学校にアクセスする]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-108">Go to **Accounts** > **Access work or school**.</span></span>
3. <span data-ttu-id="a1ca5-109">[管理ログ ファイルのエクスポート] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-109">Select "Export your management log files."</span></span>

   ![[関連設定] の下にエクスポートのオプションが表示された [職場または学校にアクセスする] 画面。](./media/w10-export-logs.png)

4. <span data-ttu-id="a1ca5-111">ログが **C:\Users\Public\Public Documents\MDMDiagnostics** に保存されます。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-111">The logs will be saved in **C:\Users\Public\Public Documents\MDMDiagnostics**.</span></span> <span data-ttu-id="a1ca5-112">2 つのファイルが作成されます。1 つはログ自体、もう 1 つは特殊なドキュメントで、管理者は Microsoft Excel などの別のプログラムでログを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-112">Two files will be created: one is the log itself, and the other is a special document that allows your admin to review the logs in different programs, like Microsoft Excel.</span></span> <span data-ttu-id="a1ca5-113">これらのファイル両方を電子メールに添付し、その電子メールを管理者に送信します。これを複数回行う場合は、単純に、ログが作成された日からファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-113">Attach both of these files to an email and send that email to your admin. If you do this more than once, simply choose the files from the day you created the logs.</span></span> 

<span data-ttu-id="a1ca5-114">また、[ポータル サイト アプリからのログ](send-logs-to-your-it-admin-cp-windows.md)を送信して、問題が見つかったときに会社のサポートがトラブルシューティングしやすくする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-114">You may also need to send [logs from the Company Portal app](send-logs-to-your-it-admin-cp-windows.md) to give your company support more help in trying to troubleshoot any issues they may find.</span></span> 

<span data-ttu-id="a1ca5-115">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="a1ca5-115">Still need help?</span></span> <span data-ttu-id="a1ca5-116">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-116">Contact your company support.</span></span> <span data-ttu-id="a1ca5-117">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-117">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
