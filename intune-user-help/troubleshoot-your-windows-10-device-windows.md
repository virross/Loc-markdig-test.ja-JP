---
title: "Windows 10 デバイスの登録に関するトラブルシューティング | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ab630b6-47ff-443b-a2a5-be23388bcea7
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 8724983e268582db80f0e6c70042b25981e7e633
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="troubleshoot-your-windows-10-device-enrollment"></a><span data-ttu-id="cf6a4-102">Windows 10 デバイスの登録に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cf6a4-102">Troubleshoot your Windows 10 device enrollment</span></span>
<span data-ttu-id="cf6a4-103">「[Intune に Windows 10 Mobile または Windows 10 デスクトップ デバイスを登録する](enroll-your-w10-phone-or-w10-pc-windows.md)」の手順を完了しても職場または学校の電子メールやファイルにアクセスできない場合は、次のトラブルシューティング手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-103">If you followed the steps in [Enroll your Windows 10 Mobile or Windows 10 desktop device in Intune](enroll-your-w10-phone-or-w10-pc-windows.md), but you still can’t access your work or school email and files, try these troubleshooting steps.</span></span>

1.  <span data-ttu-id="cf6a4-104">次の 2 つの画面を見て、お使いのデバイスの表示画面に似ている方をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-104">Look at the next two screens, and find the one that looks like what you see on your device.</span></span> <span data-ttu-id="cf6a4-105">お使いのデバイスの表示画面に対応する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-105">Follow the steps that go with the screen you see on your device.</span></span>

    <span data-ttu-id="cf6a4-106">次の画面が表示されている場合は、「[[Access work or school (職場または学校へのアクセス)] が表示されている場合のトラブルシューティング手順](#troubleshooting-steps-to-follow-if-you-see-access-work-or-school)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-106">If you see this screen, follow the steps in [Troubleshooting steps to follow if you see Access work or school](#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).</span></span>

    ![settings-accounts-access-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    <span data-ttu-id="cf6a4-108">次の画面が表示されている場合は、「[[お使いのアカウント] が表示されている場合のトラブルシューティング手順](#troubleshooting-steps-to-follow-if-you-see-your-account)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-108">If you see this screen, follow the steps in [Troubleshooting steps to follow if you see Your account](#troubleshooting-steps-to-follow-if-you-see-your-account).</span></span>

    ![settings-accounts-your-account](./media/W10-enroll-2-accounts-your-account.png)

## <a name="troubleshooting-steps-to-follow-if-you-see-access-work-or-school"></a><span data-ttu-id="cf6a4-110">[職場または学校にアクセスする] が表示される場合のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="cf6a4-110">Troubleshooting steps to follow if you see "Access work or school"</span></span>

1. <span data-ttu-id="cf6a4-111">上記の手順を実行しても職場または学校の電子メールやファイルにアクセスできない場合は、**[Access work or school (職場または学校へのアクセス)]** に戻ります。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-111">If you followed the steps above, but you still can’t access your work or school email and files, go back to **Access work or school**.</span></span>

2. <span data-ttu-id="cf6a4-112">以下のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-112">Do one of the following:</span></span>

   - <span data-ttu-id="cf6a4-113">次の画像のような接続が表示される場合は、その接続をタップして、[管理]、[情報]、[切断] の各オプションが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-113">If you see a connection that looks similar to the image below, tap it, and then check that you see the Manage, Info and Disconnect options.</span></span> <span data-ttu-id="cf6a4-114">これらのオプションが表示される場合は、登録および接続は完了しています。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-114">If you see these option, you’re now enrolled and connected.</span></span>

     ![validate-successful-enrollment](./media/w10-enroll-rs1-validate-successful-enrollment.png)

   - <span data-ttu-id="cf6a4-116">上に示した接続情報が表示されない場合、または接続情報は表示されるが一部のオプションが表示されない場合は、**[接続]** をタップし、職場または学校の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-116">If you don’t see the connection information shown above, or you do see it, but it’s missing some of the options, tap **Connect**, and then sign in with your work or school credentials.</span></span> <span data-ttu-id="cf6a4-117">これで接続が完了します。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-117">You should now be connected.</span></span>

## <a name="troubleshooting-steps-to-follow-if-you-see-your-account"></a><span data-ttu-id="cf6a4-118">[お使いのアカウント] が表示される場合のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="cf6a4-118">Troubleshooting steps to follow if you see "Your account"</span></span>

<span data-ttu-id="cf6a4-119">上記の手順を実行しても、職場または学校の電子メールやファイルなどのデータにアクセスできない場合は、**[アカウント]** に戻り、**[職場のアクセス]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-119">If you followed the steps above, but still can't access your work or school email, files, and other data, go back to **Accounts**, and tap **Work access**.</span></span>

- <span data-ttu-id="cf6a4-120">職場または学校のアカウントが表示された場合は、正常に</span><span class="sxs-lookup"><span data-stu-id="cf6a4-120">If you see your work or school account, congratulations.</span></span> <span data-ttu-id="cf6a4-121">接続されています。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-121">You’re connected.</span></span>

- <span data-ttu-id="cf6a4-122">職場または学校のアカウントが表示されない場合は、**[接続]** をタップしてから、職場または学校の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-122">If you don’t see your work or school account, tap **Connect**, and then sign in with your work or school credentials.</span></span>

## <a name="troubleshooting-steps-to-follow-if-you-see-set-up-a-work-or-school-account"></a><span data-ttu-id="cf6a4-123">[職場または学校アカウントの設定] が表示される場合のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="cf6a4-123">Troubleshooting steps to follow if you see "Set up a work or school account"</span></span>

<span data-ttu-id="cf6a4-124">"__入力されたユーザー名と一致する管理エンドポイントを自動検出できませんでした。ユーザー名を確認して、やり直してください。管理エンドポイントの URL がわかっている場合は、それを入力してください。__" というメッセージが表示される場合は、ユーザー名とパスワードを再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-124">If you see a message that says __We couldn't auto-discover a management endpoint matching the username entered. Please check your username and try again. If you know the URL to your management endpoint, please enter it.__, then you should try to re-enter your username and password.</span></span> <span data-ttu-id="cf6a4-125">それでもうまくいかない場合は、**[管理エンドポイント]** ボックスに入力する必要のある Web サイトの会社のサポートに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-125">If it still doesn't work, you should check with your company support for the website that you need to provide in the **Management endpoint** text box.</span></span> <span data-ttu-id="cf6a4-126">これは、**www.yourcompany.onmicrosoft.com** のような Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-126">This is a website that probably looks like **www.yourcompany.onmicrosoft.com**.</span></span>

<span data-ttu-id="cf6a4-127">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="cf6a4-127">Still need help?</span></span> <span data-ttu-id="cf6a4-128">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-128">Contact your company support.</span></span> <span data-ttu-id="cf6a4-129">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="cf6a4-129">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
