---
title: "Intune に Windows Phone 8.1 デバイスを登録する | Microsoft Docs"
description: "Intune に Windows Phone 8.1 デバイスを登録する方法について説明します"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a120c3d-d520-4d48-ae4c-3338ca4e7bde
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 30980072cfb1c98ab7755206b24497a356ebfff3
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-your-windows-phone-81-device-in-intune"></a><span data-ttu-id="ece5d-103">Intune に Windows Phone 8.1 デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="ece5d-103">Enroll your Windows Phone 8.1 device in Intune</span></span>

<span data-ttu-id="ece5d-104">職場または学校が Microsoft Intune を使用している場合は、お使いのデバイスを登録して、会社の電子メール、ファイル、またその他のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ece5d-104">If your company or school uses Microsoft Intune, you can enroll your devices to get access to company email, files, and other resources.</span></span> <span data-ttu-id="ece5d-105">デバイスを登録すると、組織は会社のデータをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="ece5d-105">When you enroll your devices, your organization can keep corporate data secure.</span></span> <span data-ttu-id="ece5d-106">登録の詳細については、「[ポータル サイト アプリをインストールし、Intune にデバイスを登録するとどうなるか](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md)」と[会社のサポートがユーザーのデバイスに関して確認できる情報と確認できない情報](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ece5d-106">To learn more about enrollment, see [What happens if you install the Company Portal app and enroll your device in Intune?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) and [What your company support can and can't see on your device](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).</span></span>


<span data-ttu-id="ece5d-107">Intune に Phone 8.1 デバイスを登録するには、自分の職場または学校に当てはまる手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ece5d-107">To enroll your Phone 8.1 device in Intune, follow the instructions that apply to your company or school:</span></span>

-   [<span data-ttu-id="ece5d-108">会社で Microsoft ストアからポータル サイトを使用できるようにする場合</span><span class="sxs-lookup"><span data-stu-id="ece5d-108">If your company lets you use the Company Portal from the Microsoft Store</span></span>](#if-your-company-lets-you-use-the-company-portal-from-the-windows-store)

-   [<span data-ttu-id="ece5d-109">Windows Phone から Microsoft ストアへのアクセスが許可されていない場合、または Microsoft アカウントを所有していない場合</span><span class="sxs-lookup"><span data-stu-id="ece5d-109">If you are not allowed to access the Microsoft Store from your Windows Phone, or if you do not have a Microsoft Account</span></span>](#if-you-are-not-allowed-to-access-the-windows-store-from-your-windows-phone-or-if-you-do-not-have-a-microsoft-account)

## <a name="if-your-company-lets-you-use-the-company-portal-from-the-microsoft-store"></a><span data-ttu-id="ece5d-110">会社で Microsoft ストアからポータル サイトを使用できる場合</span><span class="sxs-lookup"><span data-stu-id="ece5d-110">If your company lets you use the Company Portal from the Microsoft Store</span></span>
<span data-ttu-id="ece5d-111">ポータル サイト アプリをデバイスにインストールします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-111">Install the Company Portal app on your device:</span></span>

1.  <span data-ttu-id="ece5d-112">**[スタート]** &gt; **[ストア]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-112">Tap **Start** &gt; **Store**.</span></span>

2.  <span data-ttu-id="ece5d-113">**[検索]** をタップし、「**ポータル サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ece5d-113">Tap **Search**, and then type **company portal**.</span></span>

3.  <span data-ttu-id="ece5d-114">結果の一覧で、**[ポータル サイト]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-114">In the list of results, tap **Company Portal**.</span></span>

    ![会社のポータルの検索結果](./media/WP81-1-CP-search-store-v2.png)

4.  <span data-ttu-id="ece5d-116">**[ポータル サイト]** &gt; **[インストール]** を順にタップします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-116">Tap **Company Portal**  &gt; **Install**.</span></span>

    ![ポータル サイトのインストール](./media/WP81-2-CP-install-v2.png)

<span data-ttu-id="ece5d-118">デバイスを登録するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ece5d-118">Enroll your device:</span></span>

1.  <span data-ttu-id="ece5d-119">デバイスで、**Microsoft Intune ポータル サイト** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="ece5d-119">On the device, open the **Microsoft Intune Company Portal** app.</span></span>

2.  <span data-ttu-id="ece5d-120">資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ece5d-120">Provide your credentials.</span></span> <span data-ttu-id="ece5d-121">会社の使用条件に同意するように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ece5d-121">You may be asked to accept your company’s Terms and Conditions, if applicable.</span></span>

3.  <span data-ttu-id="ece5d-122">**[マイ デバイス]** までスワイプします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-122">Swipe to **My Devices**.</span></span>

4.  <span data-ttu-id="ece5d-123">**[このデバイスを登録または特定するには、タップしてください]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-123">Tap **Tap to enroll or identify this device**.</span></span>

    ![[このデバイスを登録または特定するには、タップしてください] 画面](./media/WP81-enroll-1-swipe-my-devices.png)

5.  <span data-ttu-id="ece5d-125">**[このデバイスの登録]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-125">Tap **Enroll this device**.</span></span>

    ![[このデバイスの登録] 画面](./media/WP81-enroll-2-enroll-this-device.png)

6.  <span data-ttu-id="ece5d-127">**[アカウントの追加]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-127">Tap **Add account**.</span></span>

    ![[ワークプレース] 設定画面](./media/WP81-enroll-3-workplace-add-acct.png)

7.  <span data-ttu-id="ece5d-129">要求された追加情報を入力し、**[サインイン]** をタップして、登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="ece5d-129">Enter more information as requested, and then tap **sign in** to finish the enrollment.</span></span> <span data-ttu-id="ece5d-130">**[設定]** &gt; **[ワークプレース]** ページに社内アカウントが表示されているはずです。</span><span class="sxs-lookup"><span data-stu-id="ece5d-130">You should now see your workplace account listed on the **Settings** &gt; **Workplace** page.</span></span>

    ![追加されたアカウントの画面](./media/WP81-enroll-4-account-added.png)

## <a name="if-you-are-not-allowed-to-access-the-microsoft-store-from-your-windows-phone-or-if-you-do-not-have-a-microsoft-account"></a><span data-ttu-id="ece5d-132">Windows Phone から Microsoft ストアへのアクセスが許可されていない場合、または Microsoft アカウントを所有していない場合</span><span class="sxs-lookup"><span data-stu-id="ece5d-132">If you are not allowed to access the Microsoft Store from your Windows Phone or if you do not have a Microsoft Account</span></span>

1.  <span data-ttu-id="ece5d-133">**[設定]** &gt; **[社内]** の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-133">Tap  **Settings** &gt; **workplace**.</span></span>

2.  <span data-ttu-id="ece5d-134">**[アカウントの追加]** をタップし、仕事用アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-134">Tap **add account**, and then sign in using your work account.</span></span>

3.  <span data-ttu-id="ece5d-135">要求された追加情報を入力し、**[サインイン]** をタップして、登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="ece5d-135">Enter more information as requested, and then tap **sign in** to finish the enrollment.</span></span>

4.  <span data-ttu-id="ece5d-136">会社のアプリまたはハブをインストールするように求められたら、関連するボックスがオンになっていることを確認し、**[完了]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="ece5d-136">If prompted to install the company app or Hub, make sure the relevant box is checked, and then tap **done**.</span></span>

<span data-ttu-id="ece5d-137">会社のサポートによって、登録時に Intune ポータル サイトがインストールされるようにセットアップされている場合は、その Intune ポータル サイトがアプリの一覧に表示されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="ece5d-137">If your company support has set up the Company Portal to be installed during enrollment, you will see the Company Portal appear in your app list.</span></span>

<span data-ttu-id="ece5d-138">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="ece5d-138">Still need help?</span></span> <span data-ttu-id="ece5d-139">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ece5d-139">Contact your company support.</span></span> <span data-ttu-id="ece5d-140">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="ece5d-140">For their contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
