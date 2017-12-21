---
title: "使用条件を拒否した場合にデバイスの登録を解除する | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope: User help
ROBOTS: 
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 779e822c7b04a9839495d5d5c8c4687a0340d9af
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="unenroll-your-device-if-you-declined-terms-of-use"></a><span data-ttu-id="e4b17-102">"利用規約" を拒否した場合にデバイスの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="e4b17-102">Unenroll your device if you declined "Terms of Use"</span></span>

<span data-ttu-id="e4b17-103">Android デバイスの登録を解除する方法として最も良いのは、利用規約を受け入れ、ポータル サイト アプリにサインインしてから、[こちらの手順](unenroll-your-device-from-intune-android.md)を使用して登録を解除する方法です。</span><span class="sxs-lookup"><span data-stu-id="e4b17-103">The best way to unenroll your Android device is to accept the terms of use, sign in to the Company Portal app, and then use [these instructions](unenroll-your-device-from-intune-android.md) to unenroll.</span></span> <span data-ttu-id="e4b17-104">ただし、ポータル サイト アプリへのサインインの試行中に利用規約を拒否した場合は、次回以降、ポータル サイト アプリにサインインできなくなるため、デバイスの登録を解除するときは次の "回避策" の手順を実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4b17-104">However, if you declined the terms of use while trying to sign in to the Company Portal app, you are prevented from signing in to the Company Portal app on future tries, so you need to use these "workaround" instructions to unenroll your device.</span></span>

<span data-ttu-id="e4b17-105">ポータル サイト アプリをアンインストールすると、Intune からそのデバイスの登録も解除されます。</span><span class="sxs-lookup"><span data-stu-id="e4b17-105">When you uninstall the Company Portal app, you are also unenrolling your device from Intune.</span></span> <span data-ttu-id="e4b17-106">デバイスは会社のリソースにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="e4b17-106">Your device will no longer be able to access company resources.</span></span> <span data-ttu-id="e4b17-107">登録解除した場合の詳細については、「[Intune からデバイスの登録を解除するとどうなるか](what-happens-if-you-unenroll-your-device-from-intune-android.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b17-107">For more about what happens when you unenroll, see [What happens if you unenroll your device from Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md).</span></span>

<span data-ttu-id="e4b17-108">会社のポータル アプリをアンインストールするには、最初に **[Device administrators]** 設定に進み、**[会社のポータル]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="e4b17-108">Before you can uninstall the Company Portal app, you have to go to the **Device administrators** setting, and turn off **Company Portal**.</span></span> <span data-ttu-id="e4b17-109">使用している Android デバイスによっては、手順が多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4b17-109">The steps may differ a little, depending on which Android device you have.</span></span>

<span data-ttu-id="e4b17-110">Intune からデバイスの登録を解除し、会社のポータル アプリをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="e4b17-110">To unenroll your device from Intune and uninstall the Company Portal app:</span></span>

1.  <span data-ttu-id="e4b17-111">**[設定]** &gt; **[セキュリティ &amp; 画面のロック]** &gt;**[デバイス管理者]** の順に進みます。</span><span class="sxs-lookup"><span data-stu-id="e4b17-111">Go to **Settings** &gt; **Security &amp; Screen Lock** &gt; **Device administrators**.</span></span>

    <span data-ttu-id="e4b17-112">この手順は、デバイスの登録を解除したらすぐに実行します。</span><span class="sxs-lookup"><span data-stu-id="e4b17-112">Completing this step immediately unenrolls your device.</span></span>

2.  <span data-ttu-id="e4b17-113">**[会社のポータル]** の横のチェック ボックスの選択を解除 (オフに) します。</span><span class="sxs-lookup"><span data-stu-id="e4b17-113">Uncheck the box next to, or turn off, **Company Portal**.</span></span>

    <span data-ttu-id="e4b17-114">これで、会社のポータル アプリをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e4b17-114">You can now uninstall the Company Portal app.</span></span>

<span data-ttu-id="e4b17-115">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="e4b17-115">Still need help?</span></span> <span data-ttu-id="e4b17-116">会社のサポートに問い合わせるか (連絡先情報については[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください)、または <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android チーム</a>にご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="e4b17-116">Contact your company support (check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) for contact information), or write the <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android team</a>.</span></span>
