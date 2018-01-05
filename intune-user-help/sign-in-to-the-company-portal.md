---
title: "ポータル サイト アプリにサインインする方法 | Microsoft Docs"
description: "複数のプラットフォームでポータル サイト アプリにサインインする方法を確認します。"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: fc8dd1c9d549d2ecbd7eabb7c34589c02ac327e4
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="how-do-i-sign-in-to-the-company-portal-app---user-story-1132123--"></a><span data-ttu-id="12e25-103">ポータル サイト アプリにサインインするには</span><span class="sxs-lookup"><span data-stu-id="12e25-103">How do I sign in to the Company Portal app?</span></span> <!--User Story 1132123-->

<span data-ttu-id="12e25-104">電子メールやビジネス アプリなどの会社のリソースにアクセスする場合、ポータル サイト アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="12e25-104">You use the Company Portal app to access your company resources, like email and business apps.</span></span> <span data-ttu-id="12e25-105">ポータル サイトにサインインする方法は主に 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="12e25-105">There are two main ways that you can sign in to the Company Portal:</span></span>

* <span data-ttu-id="12e25-106">会社の電子メール アドレスとパスワードを使用する</span><span class="sxs-lookup"><span data-stu-id="12e25-106">Using your work email address and password</span></span>
* <span data-ttu-id="12e25-107">別のデバイスからサインインする</span><span class="sxs-lookup"><span data-stu-id="12e25-107">Signing in from another device</span></span>

<span data-ttu-id="12e25-108">次の画像は iOS のものですが、Android や Windows デバイスでもプロセスはほとんど同じです。</span><span class="sxs-lookup"><span data-stu-id="12e25-108">Even though the following pictures are for iOS, the process is virtually identical for your Android and Windows devices.</span></span>

## <a name="signing-in-with-your-email-address-and-password"></a><span data-ttu-id="12e25-109">電子メール アドレスとパスワードを使用したサインイン</span><span class="sxs-lookup"><span data-stu-id="12e25-109">Signing in with your email address and password</span></span>

1. <span data-ttu-id="12e25-110">お使いのデバイスでポータル サイト アプリを開いて、**[サインイン]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="12e25-110">Open the Company Portal app on your device and tap **Sign in**.</span></span>

   ![Web サイトのイメージ図の前にユーザーのアイコンが表示されたポータル サイトのサインイン ページ。](/intune/media/cp_ios_aad_signin_after_1704_001.png)

   <span data-ttu-id="12e25-114">ポータル サイト アプリがない場合は、</span><span class="sxs-lookup"><span data-stu-id="12e25-114">Don't have the Company Portal app?</span></span> <span data-ttu-id="12e25-115">[iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) または [Android](install-the-company-portal-app-android.md) でのインストールおよびダウンロード方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="12e25-115">Find out how to install and download it for [iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) or [Android](install-the-company-portal-app-android.md).</span></span>

2. <span data-ttu-id="12e25-116">**職場または学校アカウント**を入力します。</span><span class="sxs-lookup"><span data-stu-id="12e25-116">Enter your **Work or school account**.</span></span>

   ![画面は同じですが電子メールとパスワードではなく、電子メールのみを入力するように要求されます。](/intune/media/cp_ios_aad_signin_after_1704_002.png)

3. <span data-ttu-id="12e25-118">電子メール アドレスが承認されるまで待ってから、パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="12e25-118">Wait a moment for your email address to be accepted, then enter your password.</span></span>

   ![電子メールが承認されると、パスワードの入力が要求されます。](/intune/media/cp_ios_aad_signin_after_1704_003.png)

4. <span data-ttu-id="12e25-120">ポータル サイトでログインが承認されたら、サインインし、会社のリソースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="12e25-120">Once the Company Portal accepts your login, it signs you in and you can begin to access your company resources.</span></span>   

   ![認証プロセスが終了すると、ポータル サイト アプリはサインインを行い、読み込みバーが表示されます。](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="signing-in-with-certificate-based-authentication"></a><span data-ttu-id="12e25-122">証明書ベースの認証によるサインイン</span><span class="sxs-lookup"><span data-stu-id="12e25-122">Signing in with certificate-based authentication</span></span>

1.  <span data-ttu-id="12e25-123">デバイス上でポータル サイト アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="12e25-123">Open the Company Portal app on your device.</span></span>

2.  <span data-ttu-id="12e25-124">**職場または学校アカウント**を入力します。</span><span class="sxs-lookup"><span data-stu-id="12e25-124">Enter your **Work or school account**.</span></span>

3.  <span data-ttu-id="12e25-125">**[Sign in with a certificate]\(証明書を使用してサインイン\)** をタップします。</span><span class="sxs-lookup"><span data-stu-id="12e25-125">Tap the **Sign in with a certificate** link.</span></span>

4.  <span data-ttu-id="12e25-126">**[続行]** をタップして証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="12e25-126">Tap **Continue** to use the certificate.</span></span>

## <a name="signing-in-from-another-device"></a><span data-ttu-id="12e25-127">別のデバイスからサインインする</span><span class="sxs-lookup"><span data-stu-id="12e25-127">Signing in from another device</span></span>

<span data-ttu-id="12e25-128">会社のリソースへのサインインにパスワードを使用しない場合は、適切なアクセス レベルを持つ適切なユーザーであることを確認するために別のデバイスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="12e25-128">If you do not use a password to sign in to your company resources, you might use another device as the way to confirm you're the right person with the right levels of access.</span></span> <span data-ttu-id="12e25-129">会社がコンピューターへのアクセスにスマートカードを使用している場合は、別のデバイスを使用してサインインしなければならない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12e25-129">If your company uses smartcards to access your computers, it's likely that you have to sign in using another device.</span></span>

1. <span data-ttu-id="12e25-130">電子メール アドレスを入力する代わりに、電子メールのテキスト ボックスの下にある **[別のデバイスからサインインする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="12e25-130">Instead of entering in your email address, select the **Sign in from another device** link underneath the email text box.</span></span>

   ![Web サイトのイメージ図の前にユーザーのアイコンが表示されたポータル サイトのサインイン ページ。](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

2. <span data-ttu-id="12e25-134">ポータル サイトにサインインするための、一意のワンタイム コードを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="12e25-134">You receive a unique, one-time code to sign in to the Company Portal.</span></span>

   ![会社のコンピューターから固有のパスワードで aka.ms/devicelogin ページにアクセスし、コードを使用してサインインするように指示されます。](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

3. <span data-ttu-id="12e25-136">他のデバイスでブラウザーを開き、[https://aka.ms/devicelogin](https://aka.ms/devicelogin) に移動して、コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="12e25-136">On your other device, open your browser and go to [https://aka.ms/devicelogin](https://aka.ms/devicelogin) to enter the code.</span></span>

   ![ポータル サイト アプリの画像ではなく会社のコンピューターのブラウザーの画像です。](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. <span data-ttu-id="12e25-139">**[デバイス ログイン]** ページでコードが確認されたら、__[続行]__ を選択して、別のデバイスでのポータル サイトのサインインを許可します。</span><span class="sxs-lookup"><span data-stu-id="12e25-139">Once the **Device Login** page verifies the code, select __Continue__ to allow the Company Portal to sign in on your other device.</span></span>

   ![固有のコードをフィールドに入力すると、[デバイス ログイン] サイトから、Intune ポータル サイトがサインインを許可してよい適切なアプリであることを確認されます。](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. <span data-ttu-id="12e25-141">コードが確認されたら、ウィンドウを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="12e25-141">Once the code is verified, you can close the window.</span></span>

   ![デバイスでポータル サイト アプリへのログインが完了したことと、このページを閉じることができることを示す確認ページ。](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. <span data-ttu-id="12e25-143">元のデバイスで、ポータル サイト アプリのサインインが開始します。</span><span class="sxs-lookup"><span data-stu-id="12e25-143">On your original device, the Company Portal app begins signing in.</span></span>

   ![認証プロセスが終了すると、ポータル サイト アプリはサインインを行い、進捗を示す読み込みバーが表示されます。](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

<span data-ttu-id="12e25-145">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="12e25-145">Still need help?</span></span> <span data-ttu-id="12e25-146">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="12e25-146">Contact your company support.</span></span> <span data-ttu-id="12e25-147">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="12e25-147">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
