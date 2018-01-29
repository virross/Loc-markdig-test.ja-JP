---
title: "Windows 8.1 または Windows RT 8.1 デバイスを登録する方法 | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28984f26-1070-4f7a-877c-669a59375c0c
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 6ee90b05e52d8c73549e54784177399313f73dcd
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-enroll-your-windows-81-or-windows-rt-81-device-in-intune"></a><span data-ttu-id="14da5-102">Intune に Windows 8.1 または Windows RT 8.1 デバイスを登録する方法</span><span class="sxs-lookup"><span data-stu-id="14da5-102">How to enroll your Windows 8.1 or Windows RT 8.1 device in Intune</span></span>

<span data-ttu-id="14da5-103">職場または学校が Microsoft Intune を使用している場合は、お使いのデバイスを登録して、会社の電子メール、ファイル、またその他のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="14da5-103">If your company or school uses Microsoft Intune, you can enroll your devices to get access to company email, files, and other resources.</span></span> <span data-ttu-id="14da5-104">デバイスを登録すると、組織は会社のデータをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="14da5-104">When you enroll your devices, your organization can keep corporate data secure.</span></span> <span data-ttu-id="14da5-105">登録の詳細については、「[ポータル サイト アプリをインストールし、Intune にデバイスを登録するとどうなるか](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md)」と[会社のサポートがユーザーのデバイスに関して確認できる情報と確認できない情報](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14da5-105">To learn more about enrollment, see [What happens if you install the Company Portal app and enroll your device in Intune?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) and [What your company support can and can't see on your device](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).</span></span>


<span data-ttu-id="14da5-106">Windows 8.1 または Windows RT 8.1 デバイスを登録するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="14da5-106">To enroll your Windows 8.1 or Windows RT 8.1 device:</span></span>

1.  <span data-ttu-id="14da5-107">デバイスで、**[設定]** &gt; **[PC 設定]** &gt; **[ネットワーク]** &gt; **[社内]** の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="14da5-107">On the device, tap **Settings** &gt; **PC Settings** &gt; **Network** &gt; **Workplace**.</span></span>

    ![nav-to-workplace](./media/W81-1-workplacejoin.png)

2.  <span data-ttu-id="14da5-109">必要に応じて、ユーザー ID に職場または学校のメール アドレスを入力し、**[参加]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="14da5-109">Enter your work or school email for the User ID, if required, and then tap **Join**.</span></span>

    <span data-ttu-id="14da5-110">ユーザー ID が必要ない場合は、このデバイスへのサインイン時に入力した電子メール アドレスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="14da5-110">If your user ID is not required,  the email address that you entered when you signed in to this device is used.</span></span>

3.  <span data-ttu-id="14da5-111">職場または学校の電子メールのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="14da5-111">Enter the password for your work or school email.</span></span>

    ![type-password](./media/W81-2-workplacesettings_signin.png)

4.  <span data-ttu-id="14da5-113">**[デバイスの管理をオンにする]** で、**[オンにする]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="14da5-113">Under **Turn on device management**, tap **Turn on**.</span></span>

    ![turn-on-device-management](./media/W81-3-dev-mgt-turn-on.png)

5.  <span data-ttu-id="14da5-115">**[Allow apps and services from company support]\(会社のサポートによるアプリやサービスの管理を許可する\)** ダイアログ ボックスで、**[同意する]** チェック ボックスをオンにし、**[オンにする]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="14da5-115">In the **Allow apps and services from company support** dialog box, check the  **I agree** box, and then tap **Turn on**.</span></span>

    ![turn-on-allow-apps-services](./media/W81-4-agree-allow-apps-services.png)

    <span data-ttu-id="14da5-117">登録に成功すると、次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14da5-117">When you have successfully enrolled, you'll see the following screen.</span></span>

    ![enrollment-complete](./media/W81-5-enrolled-done.png)

<span data-ttu-id="14da5-119">さらに、ポータル サイト アプリをインストールすることもお勧めします。これにより、自分や自分の役割に関連する会社のアプリを簡単に識別して、取得できます。</span><span class="sxs-lookup"><span data-stu-id="14da5-119">We also recommend that you install the Company Portal app, which lets you easily identify and get the company apps that are relevant to you and your role.</span></span> <span data-ttu-id="14da5-120">会社での Intune のセットアップ方法に応じて、ポータル サイト アプリが登録プロセスの一部としてインストールされていることもあります。</span><span class="sxs-lookup"><span data-stu-id="14da5-120">Depending on how your company set up Intune, the Company Portal app may have been installed as part of your enrollment process.</span></span> <span data-ttu-id="14da5-121">アプリがあるかどうかを確認するには、アプリ一覧で、**[ポータル サイト]** を検索します。</span><span class="sxs-lookup"><span data-stu-id="14da5-121">To check if you have the app, look for **Company Portal** in your apps list.</span></span> <span data-ttu-id="14da5-122">アプリの一覧で、[ポータル サイト] が表示されない場合は、次の手順に従ってインストールします。</span><span class="sxs-lookup"><span data-stu-id="14da5-122">If you don't see the Company Portal in your list of apps, follow these steps to install it.</span></span>

1.  <span data-ttu-id="14da5-123">**[スタート]** &gt; **[ストア]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="14da5-123">Tap **Start** &gt; **Store**.</span></span>

2.  <span data-ttu-id="14da5-124">**[検索]** をタップし、「**ポータル サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="14da5-124">Tap **Search**, and then type **company portal**.</span></span>

3.  <span data-ttu-id="14da5-125">結果の一覧で、**[ポータル サイト]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="14da5-125">In the list of results, tap **Company Portal**.</span></span>

4.  <span data-ttu-id="14da5-126">**[インストール]** または **[無料]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="14da5-126">Tap  either **Install** or **Free**.</span></span> <span data-ttu-id="14da5-127">表示されるオプションは、会社がどのようにアプリをセットアップしたかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="14da5-127">The option shown depends on how your company set up the app.</span></span>

<span data-ttu-id="14da5-128">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="14da5-128">Still need help?</span></span> <span data-ttu-id="14da5-129">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="14da5-129">Contact your company support.</span></span> <span data-ttu-id="14da5-130">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="14da5-130">For their contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
