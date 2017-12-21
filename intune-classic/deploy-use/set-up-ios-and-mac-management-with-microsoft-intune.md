---
title: Set up iOS and Mac management
description: "Microsoft Intune で、iPad や iPhone だけでなく Mac OS X デバイスを含む iOS デバイスのモバイル デバイス管理 (MDM) を有効にします。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d07d9acb2956d99c0ee613d603b820d58f40f247
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-ios-and-mac-device-management"></a><span data-ttu-id="670f1-103">iOS および Mac のデバイス管理をセットアップする</span><span class="sxs-lookup"><span data-stu-id="670f1-103">Set up iOS and Mac device management</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="670f1-104">Intune では、iPad、iPhone、および macOS デバイスのモバイル デバイス管理 (MDM) が有効になり、会社の電子メールおよびアプリへのアクセス権がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="670f1-104">Intune enables mobile device management (MDM) of iPads, iPhones, and macOS devices and gives users access to company email and apps.</span></span> <span data-ttu-id="670f1-105">Intune で iOS および Mac デバイスを管理するには、Apple Push Notification サービス (APNs) 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="670f1-105">An Apple Push Notification service (APNs) certificate is required for Intune to manage iOS and Mac devices.</span></span> <span data-ttu-id="670f1-106">証明書を Intune に追加すると、ユーザーがポータル サイト アプリをインストールして自分のデバイスを登録できます。または管理者が[企業所有の iOS デバイス管理](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="670f1-106">After the certificate is added to Intune, users can install the Company Portal app to enroll their devices, or the admin can set up [corporate-owned iOS device management](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span></span>

1.  <span data-ttu-id="670f1-107">**Intune をセットアップする**</span><span class="sxs-lookup"><span data-stu-id="670f1-107">**Set up Intune**</span></span><br>
    <span data-ttu-id="670f1-108">**Microsoft Intune** を[モバイル デバイス管理機関に設定](prerequisites-for-enrollment.md#step-2-set-mdm-authority)して、MDM の設定を行うことにより、モバイル デバイス管理を準備します (この作業をまだ行っていない場合)。</span><span class="sxs-lookup"><span data-stu-id="670f1-108">If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#step-2-set-mdm-authority) as **Microsoft Intune** and setting up MDM.</span></span>

2.  <span data-ttu-id="670f1-109">**証明書署名要求を取得する**</span><span class="sxs-lookup"><span data-stu-id="670f1-109">**Get a certificate signing request**</span></span><br>
    <span data-ttu-id="670f1-110">管理者として [Microsoft Intune 管理コンソール](https://manage.microsoft.com)を開き、**[管理]** &gt; **[モバイル デバイス管理]** &gt;**[iOS および Mac OS X]** &gt; **[APNs 証明書のアップロード]** の順に移動して、**[APNs 証明書要求のダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="670f1-110">As an administrative user, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Download the APNs certificate request**.</span></span> <span data-ttu-id="670f1-111">証明書署名要求 (.csr) ファイルをローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="670f1-111">Save the certificate signing request (.csr) file locally.</span></span> <span data-ttu-id="670f1-112">.csr ファイルは、Apple Push Certificates Portal からの信頼関係証明書を要求するために使用します。</span><span class="sxs-lookup"><span data-stu-id="670f1-112">The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.</span></span>

    ![[APNs 証明書のアップロード] ダイアログ ボックス](../media/Intune-iOS-enrollment-with-apns.png)

3.  <span data-ttu-id="670f1-114">**Apple Push Notification サービス証明書を取得する**</span><span class="sxs-lookup"><span data-stu-id="670f1-114">**Get an Apple Push Notification service certificate**</span></span><br>
    <span data-ttu-id="670f1-115">[Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844) に移動します。会社の Apple ID でサインインし、.csr ファイルを使用して APNs 証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="670f1-115">Go to the [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844), and sign in with your company Apple ID to create the APNs certificate by using the .csr file.</span></span> <span data-ttu-id="670f1-116">Apple Push Certificate Portal で **[Upload]** (アップロード) を選択すると、APNs に使用できない .json ファイルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="670f1-116">After choosing **Upload** on Apple's Push Certificate Portal, you will receive a .json file that cannot be used for APNs.</span></span> <span data-ttu-id="670f1-117">ダウンロードが完了したら、Apple Push Certificates Portal に戻り、**[Certificates for Third-Party Servers]** (サード パーティのサーバーの証明書) で、**[Download]** (ダウンロード) を選択します。</span><span class="sxs-lookup"><span data-stu-id="670f1-117">Complete the download, return to the Apple Push Certificates Portal for **Certificates for Third-Party Servers**, and then choose **Download**.</span></span>

    <span data-ttu-id="670f1-118">APNs (.pem) 証明書をダウンロードして、ファイルをローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="670f1-118">Download the APNs (.pem) certificate, and save the file locally.</span></span>

    > [!NOTE]
    > <span data-ttu-id="670f1-119">この APNs 証明書は毎年 (置き換えではなく) 更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="670f1-119">Every year, you need to renew (not replace) this APNs certificate.</span></span> <span data-ttu-id="670f1-120">この同じ Apple ID を使用して Apple の Push Certificate Portal にサインインし、証明書を更新して、このトピックの同じ手順を使用して証明書をダウンロードし、Intune にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="670f1-120">Use this same Apple ID to sign in to Apple's Push Certificate Portal to renew the certificate, and then use the same instructions in this topic to download the certificate, and then upload it to Intune.</span></span>

4.  <span data-ttu-id="670f1-121">**APNs 証明書を Intune に追加する**</span><span class="sxs-lookup"><span data-stu-id="670f1-121">**Add the APNs certificate to Intune**</span></span><br>
    <span data-ttu-id="670f1-122">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理]** &gt; **[モバイル デバイス管理]** &gt; **[iOS および Mac OS X]** &gt; **[APNs 証明書のアップロード]** の順に移動して、**[APNs 証明書のアップロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="670f1-122">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Upload the APNs certificate**.</span></span> <span data-ttu-id="670f1-123">証明書 (.pem) ファイルに移動し、**[開く]** を選択して、**Apple ID** を入力します。</span><span class="sxs-lookup"><span data-stu-id="670f1-123">Go to the certificate (.pem) file, choose **Open**, and then enter your **Apple ID**.</span></span> <span data-ttu-id="670f1-124">この APNs 証明書を使用して、Intune はモバイル デバイスを登録し、登録したモバイル デバイスにポリシーを適用して iOS デバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="670f1-124">With the APNs certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.</span></span>

5.  <span data-ttu-id="670f1-125">**デバイスを登録して会社のリソースへのアクセスを取得する方法をユーザーに知らせる**</span><span class="sxs-lookup"><span data-stu-id="670f1-125">**Tell your users how to enroll their devices to get access to company resources.**</span></span>

    <span data-ttu-id="670f1-126">エンドユーザー用の登録手順については、「[Intune に iOS デバイスを登録する](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)」および「[Intune に macOS デバイスを登録する](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="670f1-126">For end-user enrollment instructions, see [Enroll your iOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) and [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span></span> <span data-ttu-id="670f1-127">登録プロセスでは、登録により可能になる操作、および IT 管理者が見ることのできるデバイス上のデータと見られないデータについての説明が行われます。</span><span class="sxs-lookup"><span data-stu-id="670f1-127">The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.</span></span>

    <span data-ttu-id="670f1-128">その他のエンドユーザー タスクの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="670f1-128">For information about other end-user tasks, see these articles:</span></span>
    - [<span data-ttu-id="670f1-129">Microsoft Intune を使用したエンドユーザー エクスペリエンスに関するリソース</span><span class="sxs-lookup"><span data-stu-id="670f1-129">Resources about the end-user experience with Microsoft Intune</span></span>](/intune/end-user-educate)
    - [<span data-ttu-id="670f1-130">IOS および Mac デバイス向けのエンド ユーザー ガイダンス</span><span class="sxs-lookup"><span data-stu-id="670f1-130">End user guidance for iOS and Mac devices</span></span>](https://docs.microsoft.com/intune-user-help/using-your-ios-or-macOS-device-with-intune)

<span data-ttu-id="670f1-131">会社または組織でユーザーのために iOS デバイスを購入した場合は、それらのデバイスも[会社所有の iOS デバイス](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)として管理対象に登録できます。</span><span class="sxs-lookup"><span data-stu-id="670f1-131">If your company or organization buys iOS devices for users, those devices can also be enrolled for management as [company-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span></span>

### <a name="see-also"></a><span data-ttu-id="670f1-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="670f1-132">See Also</span></span>
[<span data-ttu-id="670f1-133">Microsoft Intune で登録するための前提条件</span><span class="sxs-lookup"><span data-stu-id="670f1-133">Prerequisites for enrollment with Microsoft Intune</span></span>](prerequisites-for-enrollment.md)
