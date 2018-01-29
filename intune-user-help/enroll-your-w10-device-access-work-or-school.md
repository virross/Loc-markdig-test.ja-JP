---
title: "Intune に Windows 10 デバイスを登録する | Microsoft Docs"
description: "Intune に Windows 10 1607 以降のデバイスを登録する"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: efcdb85a8192040967778f9efb69117c110751d5
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="enroll-your-windows-10-device-in-intune"></a><span data-ttu-id="21fcf-103">Intune に Windows 10 デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="21fcf-103">Enroll your Windows 10 device in Intune</span></span>

> [!NOTE]
> <span data-ttu-id="21fcf-104">Windows 10 はあらゆる種類のデバイスで動作します。</span><span class="sxs-lookup"><span data-stu-id="21fcf-104">Windows 10 works across all types of devices.</span></span> <span data-ttu-id="21fcf-105">デスクトップ、スマートフォン、タブレットのいずれを使用している場合でも、このページの画像とは少し違う部分があるかもしれませんが、手順は同じです。</span><span class="sxs-lookup"><span data-stu-id="21fcf-105">Whether you're using a desktop, phone, or tablet, the steps you follow are the same - even if they look slightly different from the images on this page.</span></span>

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Windows-Enrollment/player]

1. <span data-ttu-id="21fcf-106">**[スタート]** メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="21fcf-106">Go to **Start**.</span></span>

   - <span data-ttu-id="21fcf-107">**Windows 10 デスクトップ** デバイスを使用している場合は、**[スタート] メニュー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="21fcf-107">If you are on a **Windows 10 desktop** device, go to the **Start menu**.</span></span>
   - <span data-ttu-id="21fcf-108">**Windows 10 Mobile** デバイスを使用している場合は、**[スタート]** 画面に移動し、スワイプして **[すべてのアプリ]** リストを表示します。</span><span class="sxs-lookup"><span data-stu-id="21fcf-108">If you are on a **Windows 10 Mobile** device, go to the **Start screen**, then swipe to the **All Apps** list.</span></span>

2. <span data-ttu-id="21fcf-109">検索バーで「設定」を検索して、Windows の **[設定]** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="21fcf-109">Open the Windows **Settings** app by searching for "settings" in the search bar.</span></span>

3. <span data-ttu-id="21fcf-110">**[アカウント]** > **[職場または学校にアクセスする]** > **[接続]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="21fcf-110">Select **Accounts** > **Access work or school** > **Connect**.</span></span>

    ![[職場または学校にアクセスする] アカウントの選択](./media/w10-enroll-rs1-connect-to-work-or-school.png)

4. <span data-ttu-id="21fcf-112">職場または学校の電子メール アドレスを入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21fcf-112">Enter your work or school email address, and then select **Next**.</span></span>

   ![職場または学校のアカウントを入力します。](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

5. <span data-ttu-id="21fcf-114">職場または学校のアカウントで Intune にサインインします。</span><span class="sxs-lookup"><span data-stu-id="21fcf-114">Sign in to Intune with your work or school account.</span></span>

    ![職場または学校のアカウントを追加する](./media/w10-enroll-rs1-enter-your-credentials.png)

    <span data-ttu-id="21fcf-116">会社または学校がデバイスを登録していることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21fcf-116">You’ll see a message indicating that your company or school is registering your device.</span></span>

6. <span data-ttu-id="21fcf-117">「**準備が完了しました!**」という画面が表示されたら、</span><span class="sxs-lookup"><span data-stu-id="21fcf-117">When you see the **You’re all set!**</span></span> <span data-ttu-id="21fcf-118">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21fcf-118">screen, select **Close**.</span></span> <span data-ttu-id="21fcf-119">以上で完了です。</span><span class="sxs-lookup"><span data-stu-id="21fcf-119">You’re done.</span></span>

   !["準備が完了しました" という画面で [閉じる] を](./media/w10-enroll-rs1-youre-all-set.png)

7. <span data-ttu-id="21fcf-122">接続が適切なことを再確認する場合は、**[設定]** に戻ります。すると、職場または学校のアカウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21fcf-122">If you want to double-check that your connection looks right, go back to **Settings**, where you should now see your work or school account listed.</span></span>

    ![接続が正しくセットアップされたことを確認する](./media/w10-enroll-rs1-validate-successful-enrollment.png)

<span data-ttu-id="21fcf-124">前の手順を実行しても職場または学校の電子メール アカウントとファイルにまだアクセスできない場合は、「[[職場または学校にアクセスする] が表示されている場合のトラブルシューティング手順](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school)」に従ってください。</span><span class="sxs-lookup"><span data-stu-id="21fcf-124">If you followed the previous steps, but still can’t access your work or school email account and files, follow the steps in [Troubleshooting steps to follow if you see Access work or school](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).</span></span>
