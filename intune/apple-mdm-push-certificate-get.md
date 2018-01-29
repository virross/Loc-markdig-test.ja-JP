---
title: "Apple MDM プッシュ証明書を取得する"
titlesuffix: Azure portal
description: "Intune で iOS デバイスを管理するために Apple MDM プッシュ証明書を取得する手順について説明します。\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5feed0f5aa5bb9f984556b4b75bba7583cea195e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="get-an-apple-mdm-push-certificate"></a><span data-ttu-id="bb53f-103">Apple MDM プッシュ証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="bb53f-103">Get an Apple MDM push certificate</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="bb53f-104">Intune では、iPad、iPhone、および Mac コンピューターのモバイル デバイス管理 (MDM) が有効になり、会社の電子メールおよびアプリへのアクセス権がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="bb53f-104">Intune enables mobile device management (MDM) of iPads, iPhones, and Mac computers and gives users access to company email and apps.</span></span> <span data-ttu-id="bb53f-105">Intune で iOS および Mac デバイスを管理するには、MDM プッシュ証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb53f-105">An MDM Push certificate is required for Intune to manage iOS and Mac devices.</span></span> <span data-ttu-id="bb53f-106">証明書を Intune に追加すると、ユーザーがポータル サイト アプリをインストールして自分のデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="bb53f-106">After you add the certificate to Intune, your users can install the Company Portal app to enroll their devices.</span></span> <span data-ttu-id="bb53f-107">管理者が、Apple の Device Enrollment Program を使用して企業所有の iOS デバイス管理をセットアップしたり、Apple Configurator を使用してデバイスを登録したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bb53f-107">You can also set up corporate-owned iOS device management with Apple's Device Enrollment Program or enroll devices using Apple Configurator, for example.</span></span> <span data-ttu-id="bb53f-108">登録オプションについて詳しくは、「[iOS デバイスの登録方法を選択する](enrollment-method-choose-ios.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bb53f-108">For more information about enrollment options, see [Choose how to enroll iOS devices](enrollment-method-choose-ios.md).</span></span>

## <a name="steps-to-get-your-certificate"></a><span data-ttu-id="bb53f-109">証明書を取得する手順</span><span class="sxs-lookup"><span data-stu-id="bb53f-109">Steps to get your certificate</span></span>
<span data-ttu-id="bb53f-110">Azure Portal で、**[デバイスの登録]**  >  **[Apple の登録]** の順に選択します。次に、**[Apple MDM プッシュ通知証明書]** を選択し、Azure Portal で以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-110">In the Azure portal, choose **Device enrollment** > **Apple Enrollment** **Apple MDM Push Certificate**, and then follow the following steps in the Azure portal.</span></span>

<span data-ttu-id="bb53f-111">**手順 1: Apple MDM プッシュ証明書の作成に必要な Intune 証明書署名要求をダウンロードします。**</span><span class="sxs-lookup"><span data-stu-id="bb53f-111">**Step 1. Download the Intune certificate signing request required to create an Apple MDM push certificate.**</span></span><br>
<span data-ttu-id="bb53f-112">**[CSR のダウンロード]** を選び、要求ファイルをダウンロードしてローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-112">Select **Download your CSR** to download and save the request file locally.</span></span> <span data-ttu-id="bb53f-113">このファイルは、Apple Push Certificates Portal からの信頼関係証明書を要求するために使用します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-113">The file is used to request a trust relationship certificate from the Apple Push Certificates Portal.</span></span>

  ![MDM プッシュが設定されていない MDM プッシュ証明書構成画面のスクリーンショット。](./media/create-mdm-push-certificate.png)

<span data-ttu-id="bb53f-115">**手順 2:Apple MDM プッシュ証明書を取得します。**</span><span class="sxs-lookup"><span data-stu-id="bb53f-115">**Step 2. Create an Apple MDM push certificate.**</span></span><br>
<span data-ttu-id="bb53f-116">**[MDM プッシュ証明書を作成する]** を選択して、Apple Push Certificates Portal に移動します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-116">Select **Create your MDM push Certificate** to go to the Apple Push Certificates Portal.</span></span> <span data-ttu-id="bb53f-117">会社の Apple ID でサインインし、**[証明書の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb53f-117">Sign in with your company Apple ID, and then click **Create a Certificate**.</span></span> <span data-ttu-id="bb53f-118">**[ファイルの選択]**  を選択し、証明書署名要求ファイルを参照して、**[アップロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-118">Select **Choose File** and browse to the certificate signing request file, and then choose **Upload**.</span></span> <span data-ttu-id="bb53f-119">[確認] ページで **[ダウンロード]** を選択して証明書 (.pem) ファイルをダウンロードし、ファイルをローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-119">On the Confirmation page, choose **Download** to the download the certificate (.pem)  file, and save the file locally.</span></span>

> [!NOTE]
> <span data-ttu-id="bb53f-120">証明書は、証明書の作成に使用した Apple ID と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="bb53f-120">The certificate is associated with the Apple ID used to create it.</span></span> <span data-ttu-id="bb53f-121">ベスト プラクティスとして、管理タスクには会社の Apple ID を使用してください。</span><span class="sxs-lookup"><span data-stu-id="bb53f-121">As a best practice, use a company Apple ID for management tasks.</span></span> <span data-ttu-id="bb53f-122">個人の Apple ID は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="bb53f-122">Never use a personal Apple ID.</span></span>

<span data-ttu-id="bb53f-123">**手順 3:Apple MDM プッシュ証明書の作成に使用する Apple ID を入力します。**</span><span class="sxs-lookup"><span data-stu-id="bb53f-123">**Step 3. Enter the Apple ID used to create your Apple MDM push certificate.**</span></span><br>
<span data-ttu-id="bb53f-124">この証明書を更新する場合に備え、この ID をヒントとして記録します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-124">Record this ID as a reminder for when you need to renew this certificate.</span></span>

<span data-ttu-id="bb53f-125">**手順 4:アップロードする Apple MDM プッシュ証明書を参照します。**</span><span class="sxs-lookup"><span data-stu-id="bb53f-125">**Step 4. Browse to your Apple MDM push certificate to upload.**</span></span><br>
<span data-ttu-id="bb53f-126">証明書 (.pem) ファイルに移動し、**[開く]** を選択して、**[アップロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-126">Go to the certificate (.pem) file, choose **Open**, and then choose **Upload**.</span></span> <span data-ttu-id="bb53f-127">プッシュ証明書を使用すると、Intune で Apple デバイスを登録して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="bb53f-127">With the push certificate, Intune can enroll and manage Apple devices.</span></span>

## <a name="renew-apple-mdm-push-certificate"></a><span data-ttu-id="bb53f-128">Apple MDM プッシュ証明書を更新する</span><span class="sxs-lookup"><span data-stu-id="bb53f-128">Renew Apple MDM push certificate</span></span>
<span data-ttu-id="bb53f-129">Apple MDM プッシュ証明書の有効期間は 1 年間です。iOS と macOS のデバイス管理を維持するには毎年更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb53f-129">The Apple MDM push certificate is valid for one year and must be renewed annually to maintain iOS and macOS device management.</span></span> <span data-ttu-id="bb53f-130">証明書の有効期限が切れると、登録されている Apple デバイスに接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bb53f-130">If your certificate expires, enrolled Apple devices cannot be contacted.</span></span>

<span data-ttu-id="bb53f-131">証明書は、証明書の作成に使用した Apple ID と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="bb53f-131">The certificate is associated with the Apple ID used to create it.</span></span> <span data-ttu-id="bb53f-132">MDM プッシュ証明書を更新するには、作成時と同じ Apple ID を使用してください。</span><span class="sxs-lookup"><span data-stu-id="bb53f-132">Renew the MDM push certificate with the same Apple ID used to create it.</span></span>

1. <span data-ttu-id="bb53f-133">Azure Portal で **[デバイスの登録]** > **[Apple の登録]** の順に選び、**[Apple MDM プッシュ通知証明書]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb53f-133">In the Azure portal, choose **Device enrollment** > **Apple Enrollment**, and then choose **Apple MDM Push Certificate**.</span></span>
2. <span data-ttu-id="bb53f-134">**[CSR のダウンロード]** を選び、要求ファイルをダウンロードしてローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-134">Choose **Download your CSR** to download and save the request file locally.</span></span> <span data-ttu-id="bb53f-135">このファイルは、Apple Push Certificates Portal からの信頼関係証明書を要求するために使用します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-135">The file is used to request a trust relationship certificate from the Apple Push Certificates Portal.</span></span>
3. <span data-ttu-id="bb53f-136">更新する証明書を検索し、**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-136">Find the certificate you want to renew and select **Renew**.</span></span>
4. <span data-ttu-id="bb53f-137">**[Renew Push Certificate]\(プッシュ証明書の更新\)** 画面で、今後証明書を識別しやすいようにメモを入力し、**[ファイルの選択]** を選んで、ダウンロードした新しい要求ファイルを参照し、**[アップロード]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="bb53f-137">On the **Renew Push Certificate** screen, provide notes to help you identify the certificate in the future, select **Choose File** to browse to the new requet file you downloaded, and choose **Upload**.</span></span>
5. <span data-ttu-id="bb53f-138">**[確認]** 画面で **[ダウンロード]** を選択し、.pem ファイルをローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-138">On the **Confirmation** screen, select **Download** and save the .pem file locally.</span></span>
6. <span data-ttu-id="bb53f-139">Azure Portal で **[Apple MDM プッシュ証明書]** 参照アイコンを選択し、Apple からダウンロードした .pem ファイルを選択し、**[アップロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb53f-139">In the Azure portal, select the **Apple MDM push certificate** browse icon, select the .pem file downloaded from Apple, and choose **Upload**.</span></span>

<span data-ttu-id="bb53f-140">Apple MDM プッシュ証明書は **[有効]** と表示され、有効期限まで 365 日と表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb53f-140">Your Apple MDM push certificate appears **Active** and has 365 days until expiration.</span></span>
