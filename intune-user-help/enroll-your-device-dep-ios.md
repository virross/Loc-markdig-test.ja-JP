---
title: "iOS デバイスを Device Enrollment Program に登録する | Microsoft Docs"
description: "Intune で DEP に iOS デバイスを登録する方法について説明します"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f4e7d87e-56d1-43e4-8e88-2f62cf0999e2
searchScope: User help
ROBOTS: 
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 0d469a52c10a3c6080a3e900d55d18d7798bb534
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-your-ios-device-in-intune-with-the-device-enrollment-program"></a><span data-ttu-id="8e1c1-103">Intune で iOS デバイスを Device Enrollment Program に登録する</span><span class="sxs-lookup"><span data-stu-id="8e1c1-103">Enroll your iOS device in Intune with the Device Enrollment Program</span></span>

<span data-ttu-id="8e1c1-104">Device Enrollment Program は、そのままで簡単に iOS デバイスを管理できるユーザー エクスペリエンスを望む会社や組織のために Apple によって提供されています。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-104">The Device Enrollment Program is offered by Apple to companies and organizations that want to make the user experience easier out of the box for managing iOS devices.</span></span> <span data-ttu-id="8e1c1-105">個人所有のデバイスが許可されている会社のユーザーは、このページの手順ではなく、[標準的な iOS 登録手順](enroll-your-device-in-intune-ios.md)に従うだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-105">If your company allowed you to bring your own device, you will simply follow the [regular iOS enrollment steps](enroll-your-device-in-intune-ios.md) rather than the steps on this page.</span></span> <span data-ttu-id="8e1c1-106">会社から Device Enrollment Program の対象になっている iOS デバイスを支給されているユーザーは、以下を読んでください。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-106">Read on if your company provided you with an iOS device and told you that it was part of the Device Enrollment Program.</span></span>

1.  <span data-ttu-id="8e1c1-107">iPad の電源を入れて、最初のいくつかのセットアップ画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-107">Turn on your iPad, and proceed through the first couple of setup screens.</span></span>
2.  <span data-ttu-id="8e1c1-108">**[Language\(言語\)]** を選択した後、デバイスを Wi-Fi に接続します。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-108">After you select your **Language**, connect your device to Wi-Fi.</span></span>
3.  <span data-ttu-id="8e1c1-109">Wi-Fi に接続すると、**[Configuration\(構成\)]** 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-109">Once you’ve connected to Wi-Fi, the **Configuration** screen will appear.</span></span> <span data-ttu-id="8e1c1-110">**[[Your Company] will automatically configure your [iPad/iPhone]\([会社] が [iPad/iPhone] を自動的に構成します\)]** と表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-110">This will say that **[Your Company] will automatically configure your [iPad/iPhone].**</span></span>
4.  <span data-ttu-id="8e1c1-111">会社の**ユーザー名**と**パスワード**でログインします。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-111">Log in with your company **Username** and **Password**.</span></span>
5.  <span data-ttu-id="8e1c1-112">**使用条件**に同意し、診断情報を Apple に送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-112">Agree to the **Terms and Conditions** and decide whether you want to send diagnostic information to Apple.</span></span>
6.  <span data-ttu-id="8e1c1-113">登録が完了すると、他の操作の実行を要求される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-113">Once you complete your enrollment, your device may prompt you to take more actions.</span></span> <span data-ttu-id="8e1c1-114">すべては会社の Intune 管理者によるセットアップに基づいており、メール アクセス用のパスワードの入力、パスコードの設定、アプリケーションのインストールへの同意などです。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-114">Some of these might be entering your password for email access, setup a passcode, agree to application installations all based on what has been setup by your company’s Intune administrator.</span></span>

<span data-ttu-id="8e1c1-115">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="8e1c1-115">Still need help?</span></span> <span data-ttu-id="8e1c1-116">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-116">Contact your company support.</span></span> <span data-ttu-id="8e1c1-117">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="8e1c1-117">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
