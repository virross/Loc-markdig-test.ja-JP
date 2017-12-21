---
title: "デバイス登録の概要"
titlesuffix: Azure portal
description: "iOS デバイスの登録手順を最初から最後まで行い、登録方法を学習します。"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d80ec63cd501ebb4b6779a54002a98c65e851cc5
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-enrolling-devices"></a><span data-ttu-id="d1e54-103">デバイス登録の概要</span><span class="sxs-lookup"><span data-stu-id="d1e54-103">Get started enrolling devices</span></span>

<span data-ttu-id="d1e54-104">Microsoft Intune は、会社のデータを保護した状態で、従業員がモバイル デバイスを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-104">Microsoft Intune helps you enable your workforce with mobile devices while keeping your corporate data protected.</span></span> <span data-ttu-id="d1e54-105">エンド ユーザーは管理コンソールではなく、自分のデバイスで Intune を操作するため、登録に慣れていることが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="d1e54-105">Since your end users will interact with Intune on their devices rather than in the admin console, you want to make sure that you are fluent with the enrollment experience.</span></span> <span data-ttu-id="d1e54-106">この方法では、よく練られて作られたコンプライアンス ポリシーと自分の経験を結合し、ユーザーの視点で見ることができます。</span><span class="sxs-lookup"><span data-stu-id="d1e54-106">This way, you can combine well-crafted compliance policies with your experience to show empathy for your users.</span></span> <span data-ttu-id="d1e54-107">これは特に重要なことです。管理者に表示される情報がユーザーに伝えられるためです。</span><span class="sxs-lookup"><span data-stu-id="d1e54-107">This is especially important because your users will know exactly what information that you as an admin can see:</span></span>

| <span data-ttu-id="d1e54-108">IT 管理者が確認できないもの</span><span class="sxs-lookup"><span data-stu-id="d1e54-108">What IT cannot see</span></span> | <span data-ttu-id="d1e54-109">IT 管理者が確認できるもの</span><span class="sxs-lookup"><span data-stu-id="d1e54-109">What IT can see</span></span> |
|---|---|
| <span data-ttu-id="d1e54-110">通話と Web 閲覧の履歴</span><span class="sxs-lookup"><span data-stu-id="d1e54-110">Calling and web browsing history</span></span> | <span data-ttu-id="d1e54-111">モデル</span><span class="sxs-lookup"><span data-stu-id="d1e54-111">Model</span></span> |
| <span data-ttu-id="d1e54-112">場所</span><span class="sxs-lookup"><span data-stu-id="d1e54-112">Location</span></span> | <span data-ttu-id="d1e54-113">シリアル番号</span><span class="sxs-lookup"><span data-stu-id="d1e54-113">Serial number</span></span> |
| <span data-ttu-id="d1e54-114">個人の電子メール</span><span class="sxs-lookup"><span data-stu-id="d1e54-114">Personal email</span></span> | <span data-ttu-id="d1e54-115">オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="d1e54-115">Operating system version</span></span> |
| <span data-ttu-id="d1e54-116">テキスト メッセージ</span><span class="sxs-lookup"><span data-stu-id="d1e54-116">Text messages</span></span> | <span data-ttu-id="d1e54-117">アプリ名</span><span class="sxs-lookup"><span data-stu-id="d1e54-117">App names</span></span> |
| <span data-ttu-id="d1e54-118">連絡先</span><span class="sxs-lookup"><span data-stu-id="d1e54-118">Contacts</span></span> | <span data-ttu-id="d1e54-119">Owner</span><span class="sxs-lookup"><span data-stu-id="d1e54-119">Owner</span></span> |
| <span data-ttu-id="d1e54-120">個人アカウントのパスワード</span><span class="sxs-lookup"><span data-stu-id="d1e54-120">Passwords to your personal accounts</span></span> | <span data-ttu-id="d1e54-121">デバイス名</span><span class="sxs-lookup"><span data-stu-id="d1e54-121">Device name</span></span> |
| <span data-ttu-id="d1e54-122">予定表のイベント</span><span class="sxs-lookup"><span data-stu-id="d1e54-122">Calendar events</span></span> | <span data-ttu-id="d1e54-123">製造元 (Apple 製以外のデバイスの場合)</span><span class="sxs-lookup"><span data-stu-id="d1e54-123">Manufacturer (for devices not made by Apple)</span></span> |
| <span data-ttu-id="d1e54-124">フォト アプリやカメラ ロールの内容を含む、画像</span><span class="sxs-lookup"><span data-stu-id="d1e54-124">Pictures, including what's in the photos app or camera roll</span></span> | <span data-ttu-id="d1e54-125">電話番号 (仕事用デバイスの場合は全桁。</span><span class="sxs-lookup"><span data-stu-id="d1e54-125">Phone number (for work devices, the whole number.</span></span> <span data-ttu-id="d1e54-126">個人のデバイスの場合は下 4 桁のみ。)</span><span class="sxs-lookup"><span data-stu-id="d1e54-126">For personal devices, just the last four digits.)</span></span> |

## <a name="how-do-i-enroll-a-device"></a><span data-ttu-id="d1e54-127">デバイスはどのように登録しますか。</span><span class="sxs-lookup"><span data-stu-id="d1e54-127">How do I enroll a device?</span></span>

<span data-ttu-id="d1e54-128">多くのエンド ユーザーにとって、企業リソースへのアクセスにあたり、最初にデバイス登録が求められます。</span><span class="sxs-lookup"><span data-stu-id="d1e54-128">Enrolling a device is the first experience that many end users will have with accessing corporate resources.</span></span> <span data-ttu-id="d1e54-129">[この過程を理解](end-user-educate.md)しておけば、面倒な操作が楽になります。</span><span class="sxs-lookup"><span data-stu-id="d1e54-129">[Understanding that experience](end-user-educate.md) can help make a potentially unpleasant experience into a better one.</span></span>

1. <span data-ttu-id="d1e54-130">**App Store** を開き、**Intune ポータル サイト**を探します。</span><span class="sxs-lookup"><span data-stu-id="d1e54-130">Open the **App Store** and search for **Intune Company Portal**.</span></span>
2. <span data-ttu-id="d1e54-131">**Microsoft Intune ポータル サイト アプリ**をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-131">Download the **Microsoft Intune Company Portal** app.</span></span>
3. <span data-ttu-id="d1e54-132">**ポータル サイト** アプリを開き、テスト ユーザーのメール アドレスとパスワードを入力し、**[サインイン]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-132">Open the **Company Portal** app, enter your test user’s email address and password, then tap **Sign in**.</span></span>
4. <span data-ttu-id="d1e54-133">一時パスワードを新しいパスワードに変更します。</span><span class="sxs-lookup"><span data-stu-id="d1e54-133">Update the temporary password to a new one.</span></span>
5. <span data-ttu-id="d1e54-134">**[会社アクセスのセットアップ]** ページで、**[デバイスの登録]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-134">On the **Company Access Setup** page, tap **Device Enrollment**.</span></span>
6. <span data-ttu-id="d1e54-135">**[デバイスを登録する理由]** ページで、デバイスを登録すると可能になる操作についての説明を確認した後、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-135">On the **Why enroll your device?** page, read about what a user can do when they enroll their device, then tap **Continue**.</span></span>
7. <span data-ttu-id="d1e54-136">登録時にユーザーに与えられるアクセスの一覧を確認し、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-136">Review a list of what access a user gets when they enroll, then tap **Continue**.</span></span>
8. <span data-ttu-id="d1e54-137">IT 管理者がデバイスでできることとできないことを確認し、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-137">Review what IT admins can and can’t see on a device, then tap **Continue**.</span></span>
9. <span data-ttu-id="d1e54-138">**[次に行うこと]** ページで、登録中に行う内容を確認し、**[登録]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-138">On the **What comes next** page, read about what happens during enrollment, then tap **Enroll**.</span></span>
10. <span data-ttu-id="d1e54-139">**[プロファイルのインストール]** ページで **[インストール]** をタップし、入力が求められた場合、デバイスのパスコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d1e54-139">On the **Install Profile** page, tap **Install**, then enter the device passcode if prompted.</span></span>
11. <span data-ttu-id="d1e54-140">**[インストール]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-140">Tap **Install**.</span></span>
12. <span data-ttu-id="d1e54-141">**[インストール]** をもう一度タップすると、警告を読んだことになります。</span><span class="sxs-lookup"><span data-stu-id="d1e54-141">Tap **Install** again to indicate that you’ve read the warning.</span></span>
13. <span data-ttu-id="d1e54-142">**[警告]** ポップアップで、**[信頼する]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-142">On the **Warning** popup, tap **Trust**.</span></span>
14. <span data-ttu-id="d1e54-143">プロファイルのインストールが完了したことを示す画面に変わったら、**[完了]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-143">When the screen changes to show that the profile has finished installing, tap **Done**.</span></span>
15. <span data-ttu-id="d1e54-144">“デバイスの登録中” メッセージが画面に表示され、続いてデバイスが正常に登録されたことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1e54-144">An “Enrolling device” message shows on the screen, then shows that the device has successfully enrolled.</span></span> <span data-ttu-id="d1e54-145">ポータル サイトでページを開くように求めるポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1e54-145">A popup will appear asking to open the page in the Company Portal.</span></span> <span data-ttu-id="d1e54-146">**[開く]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="d1e54-146">Tap **Open**.</span></span>
16. <span data-ttu-id="d1e54-147">**[会社アクセスのセットアップ]** 画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="d1e54-147">You return to the **Company Access Setup** screen.</span></span> <span data-ttu-id="d1e54-148">テスト ポリシーを設定していない場合、デバイスがポリシー準拠として表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d1e54-148">If you have no test policies set up, then the device should appear compliant.</span></span> <span data-ttu-id="d1e54-149">テスト ポリシーがない場合、**[デバイスのポリシー準拠]** をタップすると、デバイスを安全にするために行わなければならないことがあると表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1e54-149">If you have any test policies, then tapping **Device Compliance** will show that there are things that need to be done to make the device secure.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1e54-150">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d1e54-150">Next steps</span></span>

<span data-ttu-id="d1e54-151">[アプリ追加の概要](get-started-apps.md) - 社員が仕事を行えるように、アプリを見つけ、デバイスに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1e54-151">[Get started with adding apps](get-started-apps.md) - Find and add apps to devices to make it possible for your employees to get work done.</span></span>

## <a name="learn-more"></a><span data-ttu-id="d1e54-152">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d1e54-152">Learn more</span></span>

* [<span data-ttu-id="d1e54-153">Intune の登録オプション</span><span class="sxs-lookup"><span data-stu-id="d1e54-153">Enrollment options for Intune</span></span>](enrollment-options.md)
* [<span data-ttu-id="d1e54-154">Intune で個人デバイスの持ち込みを有効にする</span><span class="sxs-lookup"><span data-stu-id="d1e54-154">Enable bring your own device with Intune</span></span>](byod-enable.md)
* [<span data-ttu-id="d1e54-155">登録とデバイス管理についてエンド ユーザーに指導する</span><span class="sxs-lookup"><span data-stu-id="d1e54-155">Educating your end users about enrollment and device management</span></span>](end-user-educate.md)
