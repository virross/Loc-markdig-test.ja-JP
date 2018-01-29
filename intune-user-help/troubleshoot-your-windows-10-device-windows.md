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
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1f63d0010702903c17a6de47a8810a83486da840
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="troubleshoot-your-windows-10-device-enrollment"></a><span data-ttu-id="6197a-102">Windows 10 デバイスの登録に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6197a-102">Troubleshoot your Windows 10 device enrollment</span></span>
<span data-ttu-id="6197a-103">「[Intune に Windows 10 Mobile または Windows 10 デスクトップ デバイスを登録する](enroll-your-w10-phone-or-w10-pc-windows.md)」の手順を完了しても職場または学校の電子メールやファイルにアクセスできない場合は、次のトラブルシューティング手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="6197a-103">If you followed the steps in [Enroll your Windows 10 Mobile or Windows 10 desktop device in Intune](enroll-your-w10-phone-or-w10-pc-windows.md), but you still can’t access your work or school email and files, try these troubleshooting steps.</span></span>

1.  <span data-ttu-id="6197a-104">次の 2 つの画面を見て、お使いのデバイスの表示画面に似ている方をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="6197a-104">Look at the next two screens, and find the one that looks like what you see on your device.</span></span> <span data-ttu-id="6197a-105">お使いのデバイスの表示画面に対応する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6197a-105">Follow the steps that go with the screen you see on your device.</span></span>

    <span data-ttu-id="6197a-106">次の画面が表示されている場合は、「[[Access work or school (職場または学校へのアクセス)] が表示されている場合のトラブルシューティング手順](#troubleshooting-steps-to-follow-if-you-see-access-work-or-school)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6197a-106">If you see this screen, follow the steps in [Troubleshooting steps to follow if you see Access work or school](#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).</span></span>

    ![settings-accounts-access-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    <span data-ttu-id="6197a-108">次の画面が表示されている場合は、「[[お使いのアカウント] が表示されている場合のトラブルシューティング手順](#troubleshooting-steps-to-follow-if-you-see-your-account)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6197a-108">If you see this screen, follow the steps in [Troubleshooting steps to follow if you see Your account](#troubleshooting-steps-to-follow-if-you-see-your-account).</span></span>

    ![settings-accounts-your-account](./media/W10-enroll-2-accounts-your-account.png)

## <a name="troubleshooting-steps-to-follow-if-you-see-access-work-or-school"></a><span data-ttu-id="6197a-110">[職場または学校にアクセスする] が表示される場合のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="6197a-110">Troubleshooting steps to follow if you see "Access work or school"</span></span>

1. <span data-ttu-id="6197a-111">上記の手順を実行しても職場または学校の電子メールやファイルにアクセスできない場合は、**[Access work or school (職場または学校へのアクセス)]** に戻ります。</span><span class="sxs-lookup"><span data-stu-id="6197a-111">If you followed the steps above, but you still can’t access your work or school email and files, go back to **Access work or school**.</span></span>

2. <span data-ttu-id="6197a-112">以下のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="6197a-112">Do one of the following:</span></span>

   - <span data-ttu-id="6197a-113">次の画像のような接続が表示される場合は、その接続をタップして、[管理]、[情報]、[切断] の各オプションが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6197a-113">If you see a connection that looks similar to the image below, tap it, and then check that you see the Manage, Info and Disconnect options.</span></span> <span data-ttu-id="6197a-114">これらのオプションが表示される場合は、登録および接続は完了しています。</span><span class="sxs-lookup"><span data-stu-id="6197a-114">If you see these option, you’re now enrolled and connected.</span></span>

     ![validate-successful-enrollment](./media/w10-enroll-rs1-validate-successful-enrollment.png)

   - <span data-ttu-id="6197a-116">上に示した接続情報が表示されない場合、または接続情報は表示されるが一部のオプションが表示されない場合は、**[接続]** をタップし、職場または学校の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="6197a-116">If you don’t see the connection information shown above, or you do see it, but it’s missing some of the options, tap **Connect**, and then sign in with your work or school credentials.</span></span> <span data-ttu-id="6197a-117">これで接続が完了します。</span><span class="sxs-lookup"><span data-stu-id="6197a-117">You should now be connected.</span></span>

## <a name="troubleshooting-steps-to-follow-if-you-see-your-account"></a><span data-ttu-id="6197a-118">[お使いのアカウント] が表示される場合のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="6197a-118">Troubleshooting steps to follow if you see "Your account"</span></span>

<span data-ttu-id="6197a-119">上記の手順を実行しても、職場または学校の電子メールやファイルなどのデータにアクセスできない場合は、**[アカウント]** に戻り、**[職場のアクセス]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="6197a-119">If you followed the steps above, but still can't access your work or school email, files, and other data, go back to **Accounts**, and tap **Work access**.</span></span>

- <span data-ttu-id="6197a-120">職場または学校のアカウントが表示された場合は、正常に</span><span class="sxs-lookup"><span data-stu-id="6197a-120">If you see your work or school account, congratulations.</span></span> <span data-ttu-id="6197a-121">接続されています。</span><span class="sxs-lookup"><span data-stu-id="6197a-121">You’re connected.</span></span>

- <span data-ttu-id="6197a-122">職場または学校のアカウントが表示されない場合は、**[接続]** をタップしてから、職場または学校の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="6197a-122">If you don’t see your work or school account, tap **Connect**, and then sign in with your work or school credentials.</span></span>

## <a name="troubleshooting-steps-to-follow-if-you-see-set-up-a-work-or-school-account"></a><span data-ttu-id="6197a-123">[職場または学校アカウントの設定] が表示される場合のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="6197a-123">Troubleshooting steps to follow if you see "Set up a work or school account"</span></span>

<span data-ttu-id="6197a-124">"<strong>入力されたユーザー名と一致する管理エンドポイントを自動検出できませんでした。ユーザー名を確認して、やり直してください。管理エンドポイントの URL がわかっている場合は、それを入力してください。</strong>" というメッセージが表示される場合は、ユーザー名とパスワードを再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6197a-124">If you see a message that says <strong>We couldn't auto-discover a management endpoint matching the username entered. Please check your username and try again. If you know the URL to your management endpoint, please enter it.</strong>, then you should try to re-enter your username and password.</span></span> <span data-ttu-id="6197a-125">それでもうまくいかない場合は、<strong>[管理エンドポイント]</strong> ボックスに入力する必要のある Web サイトの会社のサポートに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6197a-125">If it still doesn't work, you should check with your company support for the website that you need to provide in the <strong>Management endpoint</strong> text box.</span></span> <span data-ttu-id="6197a-126">これは、<strong>www.yourcompany.onmicrosoft.com</strong> のような Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="6197a-126">This is a website that probably looks like <strong>www.yourcompany.onmicrosoft.com</strong>.</span></span>

<span data-ttu-id="6197a-127">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="6197a-127">Still need help?</span></span> <span data-ttu-id="6197a-128">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="6197a-128">Contact your company support.</span></span> <span data-ttu-id="6197a-129">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="6197a-129">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
