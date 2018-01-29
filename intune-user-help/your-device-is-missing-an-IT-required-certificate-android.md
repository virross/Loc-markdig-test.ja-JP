---
title: "デバイスに証明書がない | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0ba4cbb-ef0a-4335-86bf-f1d006867fa2
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 7a93acc7ba7d590260f4e267ced8e03d47021b31
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="your-android-device-is-missing-a-certificate-required-by-your-company-support"></a><span data-ttu-id="f149f-102">Android デバイスに、会社のサポートが必要とする証明書がありません</span><span class="sxs-lookup"><span data-stu-id="f149f-102">Your Android device is missing a certificate required by your company support</span></span>

<span data-ttu-id="f149f-103">デバイスが Intune に登録されておらず、会社のサポートが必要とする特定の証明書がない場合は、ポータル サイト アプリにサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f149f-103">If your device isn’t enrolled in Intune, and it’s missing a certain certificate that is required by your company support, you won’t be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="f149f-104">サインインしようとすると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f149f-104">When you try to sign in, you'll see the following message:</span></span>

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

<span data-ttu-id="f149f-106">この問題を解決し、必要な証明書を取得するために、次の 2 つの主な手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f149f-106">To fix this issue and get the required certificate, there are two main steps that you'll need to do:</span></span>

- <span data-ttu-id="f149f-107">会社または学校の PC を確認し、欠落している証明書を特定します。</span><span class="sxs-lookup"><span data-stu-id="f149f-107">Identify the missing certificate by looking on a company or school PC.</span></span>
- <span data-ttu-id="f149f-108">デバイスを使用して、欠落している証明書をインターネットからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f149f-108">Use your device to download the missing certificate from the Internet.</span></span>

## <a name="identify-the-missing-certificate-by-looking-on-a-company-or-school-pc"></a><span data-ttu-id="f149f-109">欠落している証明書を会社または学校の PC で確認し、特定する</span><span class="sxs-lookup"><span data-stu-id="f149f-109">Identify the missing certificate by looking on a company or school PC</span></span>

1. <span data-ttu-id="f149f-110">PC で、Internet Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="f149f-110">On a PC, open Internet Explorer.</span></span> <span data-ttu-id="f149f-111">この目的に使用する PC をお持ちでない場合は、会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f149f-111">If you don't have a PC to use for this purpose, contact your company support.</span></span> <span data-ttu-id="f149f-112">会社のサポートの連絡先情報については、[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f149f-112">For your company support's contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>

2. <span data-ttu-id="f149f-113">[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)に移動して、職場や学校の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f149f-113">Go to the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog), and sign in using your work or school credentials.</span></span>

3. <span data-ttu-id="f149f-114">ブラウザーのアドレス バーの右端で、下のスクリーンショットのような、南京錠のような記号をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f149f-114">At the far right of the browser's address bar, choose the symbol that looks like a padlock, as shown in the following screenshot.</span></span>

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

    <span data-ttu-id="f149f-116">南京錠の記号が表示されない場合は作業を停止し、会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f149f-116">If you don't see the padlock symbol, stop and contact your company support.</span></span> <span data-ttu-id="f149f-117">このロックは、安全にサインインされていることを意味するため、その記号が表示されるまで作業を続行しないでください。</span><span class="sxs-lookup"><span data-stu-id="f149f-117">The lock means that you are securely signed in, so you should not proceed unless you see that symbol.</span></span>

4. <span data-ttu-id="f149f-118">**[View certificates]** (証明書の表示) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f149f-118">Choose **View certificates**.</span></span>

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. <span data-ttu-id="f149f-120">**[証明書]** ダイアログ ボックスで **[Certification path]** (証明パス) タブを選択し、インターネットから取得する必要がある証明書を特定します。</span><span class="sxs-lookup"><span data-stu-id="f149f-120">In the **Certificate** dialog box, choose the **Certification path** tab, and then identify the certificate that you need to get from the Internet.</span></span> <span data-ttu-id="f149f-121">必要な証明書の名前は、上記の例のスクリーン ショットで強調表示されている場所と同じ位置にあります。</span><span class="sxs-lookup"><span data-stu-id="f149f-121">The name of the certificate that you need will be in the same position as the one that is highlighted in the previous example screenshot.</span></span>

## <a name="download-and-install-the-missing-certificate-on-your-android-mobile-device"></a><span data-ttu-id="f149f-122">Android モバイル デバイスで欠落している証明書をダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="f149f-122">Download and install the missing certificate on your Android mobile device</span></span>

1. <span data-ttu-id="f149f-123">Bing や Google のような検索エンジンを使用して、前のセクションで特定した、欠落している証明書の名前を検索します。</span><span class="sxs-lookup"><span data-stu-id="f149f-123">Using a search engine like Bing or Google, search for the name of the missing certificate that you identified in the previous section.</span></span> <span data-ttu-id="f149f-124">証明書の「拡張子」は、それぞれ ".crt" または ".pem" などのように異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f149f-124">The certificate may end in different "extensions," like ".crt" or ".pem", etc.</span></span>

2. <span data-ttu-id="f149f-125">ルート証明書を Web サイトからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f149f-125">Download the root certificate from the website.</span></span>

3. <span data-ttu-id="f149f-126">証明書をダウンロードした後、デバイスの上部から下にドラッグして通知を開き、通知の一覧にある証明書の名前をタップします。</span><span class="sxs-lookup"><span data-stu-id="f149f-126">After the certificate downloads, drag down from the top of your device to open your notifications, and then tap the name of the certificate in the list of notifications.</span></span>

4. <span data-ttu-id="f149f-127">次のスクリーンショットのような **[Name the Certificate]** (証明書の名前指定) ダイアログ ボックスで、既定の証明書名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f149f-127">In the **Name the Certificate** dialog box shown in the following screenshot, accept the default certificate name.</span></span>

5. <span data-ttu-id="f149f-128">**[認証情報の使用]** が **[VPN とアプリ]** に設定されていることを確認し、**[OK]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="f149f-128">Ensure that **Credential Use** is set to **Used for VPN and apps**, and then tap **OK**.</span></span>

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. <span data-ttu-id="f149f-130">会社のポータル アプリを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f149f-130">Close the Company Portal app.</span></span>

7. <span data-ttu-id="f149f-131">会社のポータル アプリをもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="f149f-131">Reopen the Company Portal app.</span></span> <span data-ttu-id="f149f-132">これで、会社のポータル アプリにサインインできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f149f-132">You should now be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="f149f-133">サポートが必要な場合は、会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f149f-133">If you need help, contact your company support.</span></span>

<span data-ttu-id="f149f-134">上のような "証明書が見つかりません" というメッセージが表示されたが、この手順を既に実行している場合、別の証明書が存在する可能性があります。会社のサポートにそのインストールを依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f149f-134">If you see the same "missing certificate" message as the one shown previously, and you have already followed the procedure, there is probably still another certificate that your company support will need to help you install.</span></span> <span data-ttu-id="f149f-135">サポートを得る場合は、[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)で入手できる連絡先情報を使用して、会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f149f-135">Contact your company support for help using contact information available at the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
