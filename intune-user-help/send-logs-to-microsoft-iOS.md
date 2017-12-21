---
title: "iOS ログを Microsoft 開発者に送信する | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 733a590e-836f-4941-bfd9-6ae53ba25e06
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 082acce8d82d50be28e0328c76e63c4440608983
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="send-logs-to-the-company-portal-developers-for-ios-devices"></a><span data-ttu-id="eb643-102">ログを iOS デバイス向けポータル サイトの開発者に送信する | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="eb643-102">Send logs to the Company Portal developers for iOS devices</span></span>

<span data-ttu-id="eb643-103">ポータル サイト アプリが、予期せず終了することがあります。</span><span class="sxs-lookup"><span data-stu-id="eb643-103">Sometimes the Company Portal app may close unexpectedly.</span></span> <span data-ttu-id="eb643-104">これは、マイクロソフトがお客様の操作性を向上させ、このような問題が今後発生しないようにするために、アプリの開発者がお客様からのご意見を待ち望んでいる問題です。</span><span class="sxs-lookup"><span data-stu-id="eb643-104">This is an issue that the app developers want to hear about, as it can help us make it work better for you and prevent this kind of thing from happening in the future.</span></span> <span data-ttu-id="eb643-105">この情報は、デバイスの _diagnostic log_ という名前の特殊なドキュメントに保存されています。</span><span class="sxs-lookup"><span data-stu-id="eb643-105">This information is kept on your device in a special document called a _diagnostic log_.</span></span>

<span data-ttu-id="eb643-106">この問題が発生した場合、ポータル サイト チームは根本原因を探し、診断するための情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="eb643-106">If this is happening to you, the Company Portal team needs some information to try and diagnose the root cause.</span></span> <span data-ttu-id="eb643-107">ここで実行する必要がある操作は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eb643-107">Here’s what we need you to do:</span></span>

1.  <span data-ttu-id="eb643-108">問題の再現を試みてください。</span><span class="sxs-lookup"><span data-stu-id="eb643-108">Attempt to make the issue happen again.</span></span> <span data-ttu-id="eb643-109">できなくても問題ありませんが、再現できると次の手順が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="eb643-109">It’s ok if you can’t, but it might make the next step easier if you can.</span></span>
2.  <span data-ttu-id="eb643-110">__[設定]__  >  __[プライバシー]__  >  __[Diagnostics & Usage (診断情報と使用状況)]__  >  __[Diagnostics & Usage Data (診断情報と使用状況データ)]__ に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb643-110">Go to __Settings__ > __Privacy__ > __Diagnostics & Usage__ > __Diagnostics & Usage Data__.</span></span> <span data-ttu-id="eb643-111">これは、クラッシュから一般的な使用パターンまで、発生したアプリ アクティビティの一覧です。個人情報は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="eb643-111">This is a list of app activities that have happened, ranging from crashes to general usage patterns, and it does not contain any personal information.</span></span> <span data-ttu-id="eb643-112">この一覧は、最も新しいものから順番に表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb643-112">This list is organized from most recent to oldest.</span></span> <span data-ttu-id="eb643-113">この問題を再現できなかった場合、これが、このページのアプリ アクティビティの一覧に表示される最初の項目になります。</span><span class="sxs-lookup"><span data-stu-id="eb643-113">If you were able to reproduce the issue, this should be the first item that appears on the list of app activity on this page.</span></span> <span data-ttu-id="eb643-114">問題を再現できなかった場合、"ポータル サイト" で始まる最初の項目が見つかるまで下へスクロールし、見つかったらタップして開きます。</span><span class="sxs-lookup"><span data-stu-id="eb643-114">If you were unable to reproduce the issue, scroll down until you find the first item that begins with “Company Portal”, then tap it to open it.</span></span>
3.  <span data-ttu-id="eb643-115">キーを押したまま、レポート内のすべてのテキストが選択されるまで、小さい青いドットを上下にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="eb643-115">Press and hold, then drag the little blue dots up and down until all of the text in the report has been selected.</span></span> <span data-ttu-id="eb643-116">ポップアップ メニューの __[コピー]__ をタップします。</span><span class="sxs-lookup"><span data-stu-id="eb643-116">Tap __Copy__ in the popup menu.</span></span>
4.  <span data-ttu-id="eb643-117">電子メール アプリを開き、電子メールの本文にその内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="eb643-117">Open your email app, and paste that content into the body of the email.</span></span> <span data-ttu-id="eb643-118">電子メールを <a href="mailto:IntuneCPiOSfeedback@microsoft.com?subject=My Company Portal App Closed Unexpectedly&body=Press and hold, then paste your copied Company Portal app logs here.">IntuneCPiOSfeedback@microsoft.com</a> に送信します。</span><span class="sxs-lookup"><span data-stu-id="eb643-118">Send that email to <a href="mailto:IntuneCPiOSfeedback@microsoft.com?subject=My Company Portal App Closed Unexpectedly&body=Press and hold, then paste your copied Company Portal app logs here.">IntuneCPiOSfeedback@microsoft.com</a>.</span></span>

<span data-ttu-id="eb643-119">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="eb643-119">Still need help?</span></span> <span data-ttu-id="eb643-120">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="eb643-120">Contact your company support.</span></span> <span data-ttu-id="eb643-121">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="eb643-121">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
