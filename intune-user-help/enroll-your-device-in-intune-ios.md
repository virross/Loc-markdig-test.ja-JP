---
title: "会社のリソースへのアクセスを設定する | Microsoft Docs"
description: "iOS デバイスを Intune で管理する方法について説明します"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 7e1ff77fef9e084000938022fb36217b21279c28
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-access-to-your-company-resources"></a><span data-ttu-id="efdf6-103">会社のリソースへのアクセスを設定する</span><span class="sxs-lookup"><span data-stu-id="efdf6-103">Set up access to your company resources</span></span>

<span data-ttu-id="efdf6-104">お客様の会社には、電子メール、ファイル、ネットワークなど、たくさんの機密情報があります。</span><span class="sxs-lookup"><span data-stu-id="efdf6-104">Your company has lots of proprietary information, from email, to files, networks, and more.</span></span> <span data-ttu-id="efdf6-105">お客様が iOS デバイスからそれらの情報にアクセスする場合に、会社は Microsoft Intune を使用して、情報を保護できます。</span><span class="sxs-lookup"><span data-stu-id="efdf6-105">Your company is using Microsoft Intune to help protect that information when you access it from your iOS device.</span></span> <span data-ttu-id="efdf6-106">これにより、会社はそれらのリソースを管理してより安全に保つことができ、お客様は作業するのにお好きなデバイスを使用する自由が得られます。</span><span class="sxs-lookup"><span data-stu-id="efdf6-106">This lets them manage those resources, keep them more secure, and give you the freedom to use your preferred device to get your work done.</span></span>

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player]

> [!NOTE]
> <span data-ttu-id="efdf6-107">メール アプリで会社の電子メールにアクセスしようとしている場合は、セキュリティを保つためにデバイスの管理を求められる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="efdf6-107">If you're trying to access company email in the Mail app, it's likely that you were prompted to manage your device to keep it secure.</span></span> <span data-ttu-id="efdf6-108">iOS デバイスから電子メールやその他の会社リソースにアクセスするには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="efdf6-108">Follow the instructions below to get access to your email and other company resources on your iOS device.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="efdf6-109">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="efdf6-109">Before you start</span></span>

- <span data-ttu-id="efdf6-110">開始したら、プロセス全体を完了するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="efdf6-110">Make sure that you finish the entire process once you start.</span></span> <span data-ttu-id="efdf6-111">通常、数分以上一時停止すると進行状況が停止し、やり直しが必要になります。</span><span class="sxs-lookup"><span data-stu-id="efdf6-111">Pausing for more than a few minutes usually stops your progress and requires you to start over.</span></span>
- <span data-ttu-id="efdf6-112">このプロセスが失敗した場合は、ポータル サイト アプリに戻り、やり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="efdf6-112">If this process should fail, you need to return to the Company Portal app to try again.</span></span>
- <span data-ttu-id="efdf6-113">Wi-Fi が使えており、お使いのデバイス上で Safari が動作していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="efdf6-113">Make sure that your Wi-Fi is working, and that Safari works on your device.</span></span>
- <span data-ttu-id="efdf6-114">[Intune ポータル サイト アプリ](install-and-sign-in-to-the-intune-company-portal-app-ios.md)をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-114">Download and install the [Intune Company Portal app](install-and-sign-in-to-the-intune-company-portal-app-ios.md).</span></span>


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a><span data-ttu-id="efdf6-115">ポータル サイト アプリを使用して会社のリソースへのアクセスを設定する</span><span class="sxs-lookup"><span data-stu-id="efdf6-115">Using the Company Portal app to set up access to company resources</span></span>

|<span data-ttu-id="efdf6-116">表示される内容</span><span class="sxs-lookup"><span data-stu-id="efdf6-116">What you see</span></span>|<span data-ttu-id="efdf6-117">説明</span><span class="sxs-lookup"><span data-stu-id="efdf6-117">Explanation</span></span>|
|---|---|
|![下部に [サインイン] ボタンがある、ポータル サイトのサインイン画面。](./media/ios-0-cp-enroll-1711.png)|<span data-ttu-id="efdf6-119">ポータル サイト アプリを開いて、**[サインイン]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-119">Open the Company Portal app and tap **Sign in**.</span></span>|
|![Azure AD サインイン プロンプト。](./media/ios-0a-cp-enroll-1711.png)|<span data-ttu-id="efdf6-121">会社の電子メール アドレスを入力し、**[次へ]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-121">Enter your company email address, then tap **Next**.</span></span>|
|![Azure AD パスワード プロンプト。](./media/ios-0b-cp-enroll-1711.png)|<span data-ttu-id="efdf6-123">パスワードを入力し、**[サインイン]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-123">Enter your password, then tap **Sign in**.</span></span>|
|![[Loading company resources]\(会社のリソースを読み込んでいます\) スプラッシュ スクリーン。](./media/ios-1-cp-enroll-1711.png)|<span data-ttu-id="efdf6-125">読み込まれるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="efdf6-125">Wait for this to load.</span></span>|
|![使用条件。](./media/ios-2-cp-enroll-1711.png)|<span data-ttu-id="efdf6-127">使用条件を読み、**すべて同意**します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-127">Read and **Accept All** of the Terms and Conditions.</span></span>|
|![[会社アクセスのセットアップ] 画面。](./media/ios-3-cp-enroll-1711.png)|<span data-ttu-id="efdf6-130">**[開始]** をタップして、お使いのデバイスから会社のリソースへアクセスできるようにするプロセスを始めます。</span><span class="sxs-lookup"><span data-stu-id="efdf6-130">Tap on **Begin** to begin the process of making your device able to access company resources.</span></span> <span data-ttu-id="efdf6-131">これを今すぐ行うことができない場合は、プロセスを **[延期]** できますが、その場合は電子メールやドキュメントなどを取得できません。</span><span class="sxs-lookup"><span data-stu-id="efdf6-131">If you can't do this right now, you can **Postpone** the process, but it means you won't be able to get email, documents, and more.</span></span>|
|![[What can my company see]\(会社で表示できるリソース\) 画面。](./media/ios-4-cp-enroll-1711.png)|<span data-ttu-id="efdf6-133">下部のリンクをタップして、会社で表示できるリソースの **[詳細情報]** を確認できます。</span><span class="sxs-lookup"><span data-stu-id="efdf6-133">You can **Learn more** about what your company can see by tapping the link at the bottom.</span></span> <span data-ttu-id="efdf6-134">それ以外の場合は、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-134">Otherwise, tap **Continue**.</span></span>|
|![[次のステップ] 画面。](./media/ios-5-cp-enroll-1711.png)|<span data-ttu-id="efdf6-136">この画面では、セットアップ時に何が行われるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-136">This screen walks you through what's happening in the setup.</span></span> <span data-ttu-id="efdf6-137">このプロセスを完了するには、Safari、設定アプリおよびポータル サイト アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-137">You'll spend time in Safari, the Settings app and the Company Portal app to complete this process.</span></span> <span data-ttu-id="efdf6-138">**[次へ]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-138">Tap **Next**.</span></span>|
|![[次のステップ] で [次へ] をタップした後の読み込み画面。](./media/ios-6-cp-enroll-1711.png)||
|![登録を行うため、Safari に切り替わります。](./media/ios-7-cp-enroll-1711.png)|<span data-ttu-id="efdf6-141">お使いのデバイスの管理情報を取得するため、Safari に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="efdf6-141">You're sent to Safari to get management information for your device.</span></span>|
|![設定アプリの起動を要求するシステム プロンプト。](./media/ios-8-cp-enroll-1711.png)|<span data-ttu-id="efdf6-143">**[許可]** をタップして設定アプリを開き、構成プロファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-143">Tap **Allow** to open the Settings app to download the configuration profile.</span></span> <span data-ttu-id="efdf6-144">これをインストールして、会社が企業の情報をお使いのデバイスで管理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-144">You install this to let your company manage corporate information on your device.</span></span>|
|![設定で開いたプロファイル。](./media/ios-9-cp-enroll-1711.png)|<span data-ttu-id="efdf6-146">**[インストール]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-146">Tap **Install**.</span></span>|
|![画面の下部にある [Installing profile]\(プロファイルのインストール\) モーダル ダイアログ。](./media/ios-10-cp-enroll-1711.png)|<span data-ttu-id="efdf6-148">**[インストール]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-148">Tap **Install**.</span></span>|
|![[Profile is installing]\(プロファイルをインストールしています\) 読み込み画面。](./media/ios-11-cp-enroll-1711.png)|<span data-ttu-id="efdf6-150">読み込まれるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="efdf6-150">Wait for this to load.</span></span>|
|![[プロファイル管理] 警告画面。](./media/ios-12-cp-enroll-1711.png)|<span data-ttu-id="efdf6-152">Apple によって書かれたこの警告は、管理下のデバイスで行うことができる操作の種類の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-152">This warning, written by Apple, lets you know more about what types of actions could be taken on a device under management.</span></span> <span data-ttu-id="efdf6-153">詳しくは、[会社が確認できる情報](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="efdf6-153">Find out more about [what information your company can see](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).</span></span>|
|![リモート管理の信頼について質問するシステム プロンプト。](./media/ios-13-cp-enroll-1711.png)|<span data-ttu-id="efdf6-155">**[信頼する]** をタップして、お使いのデバイスで会社が企業の情報および設定の管理を行うことを許可します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-155">Tap **Trust** to allow your company to manage corporate information and settings on your device.</span></span>|
|![[Profile finishing installing]\(プロファイルのインストールを終了しています\) 読み込み画面。](./media/ios-14-cp-enroll-1711.png)|<span data-ttu-id="efdf6-157">読み込まれるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="efdf6-157">Wait for this to load.</span></span>|
|![[Profile installed]\(プロファイルがインストールされました\) 画面。](./media/ios-15-cp-enroll-1711.png)|<span data-ttu-id="efdf6-159">プロファイルがインストールされ、もうじきデバイスの企業の情報と設定が管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="efdf6-159">Your profile is installed and your device's corporate information and settings are much closer to being managed.</span></span>|
|![登録を行うため、Safari に切り替わります。](./media/ios-16-cp-enroll-1711.png)|<span data-ttu-id="efdf6-161">お使いのデバイスの管理情報の取得を終了するため、Safari に再び切り替わります。</span><span class="sxs-lookup"><span data-stu-id="efdf6-161">You're sent back to Safari to finish getting management information for your device.</span></span> |
|![ポータル サイトを開くシステム プロンプト。](./media/ios-17-cp-enroll-1711.png)|<span data-ttu-id="efdf6-163">**[開く]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-163">Tap **Open**.</span></span>|
|![[Loading company resources]\(会社のリソースを読み込んでいます\) 画面。](./media/ios-18-cp-enroll-1711.png)|<span data-ttu-id="efdf6-165">読み込まれるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="efdf6-165">Wait for this to load.</span></span>|
|![ポータル サイト アプリでデバイス カテゴリを選択します。](./media/ios-19-cp-enroll-1711.png)|<span data-ttu-id="efdf6-167">お使いのデバイスに最も適したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-167">Select the best category for your device.</span></span> <span data-ttu-id="efdf6-168">これは、通常、デバイスの所有者や、普段使用する場所に関連します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-168">This usually has to do with who owns the device, or where it's located most of the time.</span></span>|
|![カテゴリ選択。](./media/ios-20-cp-enroll-1711.png)||
|![デバイス管理が正常に行われました。設定を更新する必要があります。](./media/ios-21-cp-enroll-1711.png)|<span data-ttu-id="efdf6-171">デバイスを管理する処理が正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="efdf6-171">You've successfully gotten your device managed.</span></span> <span data-ttu-id="efdf6-172">パスワードの長さなど、会社が更新を必要とする追加の設定がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="efdf6-172">There are likely still settings, like the length of your password, that your company may need you to update.</span></span> <span data-ttu-id="efdf6-173">**[続行]** をタップして続行します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-173">Tap **Continue** to proceed.</span></span>|
|![デバイス設定を確認しています。](./media/ios-22-cp-enroll-1711.png)|<span data-ttu-id="efdf6-175">ポータル サイトは、更新を必要とする設定があるかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-175">Company Portal will check to see if any of your settings need to be updated.</span></span>|
|![設定の確認が終了しましたが、OS バージョンが正しくありません](./media/ios-23-cp-enroll-1711.png)|<span data-ttu-id="efdf6-177">ポータル サイトでは、設定に関する問題を解決する方法の指示が提供されます。</span><span class="sxs-lookup"><span data-stu-id="efdf6-177">Company Portal will provide instructions on how you can fix any issues with your settings.</span></span> <span data-ttu-id="efdf6-178">問題の修正が完了したら、**[Check Settings]\(設定の確認\)** をタップします。</span><span class="sxs-lookup"><span data-stu-id="efdf6-178">Once you finish fixing the issues, tap **Check Settings**.</span></span>|
|![[Confirming device settings]\(デバイス設定を確認しています\) 読み込み画面。](./media/ios-24-cp-enroll-1711.png)|<span data-ttu-id="efdf6-180">デバイスは、設定が会社のリソースにアクセスするのに十分安全であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="efdf6-180">Your device will check to see if your settings are secure enough to access company resources.</span></span>|
|![正常に登録され更新された設定](./media/ios-25-cp-enroll-1711.png)|<span data-ttu-id="efdf6-182">これで終了です。</span><span class="sxs-lookup"><span data-stu-id="efdf6-182">Congratulations!</span></span> <span data-ttu-id="efdf6-183">これでデバイスが Intune に登録されました。</span><span class="sxs-lookup"><span data-stu-id="efdf6-183">Your device is now enrolled in Intune.</span></span>|

> [!Note]
> <span data-ttu-id="efdf6-184">デバイスを完全に管理する前に、完了する必要のある手順がさらにいくつかある場合があります。</span><span class="sxs-lookup"><span data-stu-id="efdf6-184">You may have a few more steps to complete before your device is fully managed.</span></span> <span data-ttu-id="efdf6-185">詳しくは、[通信費管理を使ったデバイスの登録](enroll-your-device-with-telecom-expense-management-ios.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="efdf6-185">Find out more about [enrolling your device using telecom expense management](enroll-your-device-with-telecom-expense-management-ios.md).</span></span> <span data-ttu-id="efdf6-186">組織が Apple の Device Enrollment Program を使っている場合は、[こちら](enroll-your-device-dep-ios.md)で詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="efdf6-186">If your organization is using Apple's Device Enrollment Program, find out more [here](enroll-your-device-dep-ios.md).</span></span>

<span data-ttu-id="efdf6-187">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="efdf6-187">Still need help?</span></span> <span data-ttu-id="efdf6-188">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="efdf6-188">Contact your company support.</span></span> <span data-ttu-id="efdf6-189">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="efdf6-189">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
