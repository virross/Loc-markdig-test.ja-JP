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
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d6bd59800b13539558fbf56afab9fe5293f3e5bd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a><span data-ttu-id="c911d-102">電話に通常インストールされている証明書が Android デバイスにない</span><span class="sxs-lookup"><span data-stu-id="c911d-102">Your Android device is missing a certificate that usually comes installed on your phone</span></span>

<span data-ttu-id="c911d-103">デバイスが Intune に登録されておらず、電話に通常インストールされる証明書がない場合は、ポータル サイト アプリにサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c911d-103">If your device isn’t enrolled in Intune, and it’s missing a certificate that usually comes installed on your phone, you won’t be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="c911d-104">サインインしようとすると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c911d-104">When you try to sign in, you’ll see the following message:</span></span>

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

<span data-ttu-id="c911d-106">この問題は、必要な証明書を [Digicert の証明書ページ](https://www.digicert.com/digicert-root-certificates.htm)から取得することで解決できます。</span><span class="sxs-lookup"><span data-stu-id="c911d-106">You can fix this issue by getting the required certificate from [Digicert's certificate page](https://www.digicert.com/digicert-root-certificates.htm).</span></span>

1. <span data-ttu-id="c911d-107">__Baltimore CyberTrust Root__ 証明書を見つけてダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c911d-107">Find and download the __Baltimore CyberTrust Root__ certificate.</span></span> <span data-ttu-id="c911d-108">直接[こちら](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt)からダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c911d-108">You can also download it directly from [here](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).</span></span>

2. <span data-ttu-id="c911d-109">画面の上から下へドラッグして最近の通知の一覧を表示し、**[BaltimoreCyberTrustRoot.crt]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="c911d-109">Drag down from the top of the screen to display the list of your recent notifications, and tap **BaltimoreCyberTrustRoot.crt**.</span></span>

3. <span data-ttu-id="c911d-110">デバイスに**証明書の命名**を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c911d-110">Your device will ask you to **Name the Certificate**.</span></span> <span data-ttu-id="c911d-111">表示された既定の証明書名を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="c911d-111">Do not change the default certificate name that appears.</span></span>

4. <span data-ttu-id="c911d-112">**[認証情報の使用]** が **[VPN とアプリ]** に設定されていることを確認し、**[OK]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="c911d-112">Ensure that **Credential Use** is set to **Used for VPN and apps**, and then tap **OK**.</span></span>

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. <span data-ttu-id="c911d-114">ブラウザーとポータル サイト アプリを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c911d-114">Close your browser and the Company Portal app.</span></span>

6. <span data-ttu-id="c911d-115">会社のポータル アプリをもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="c911d-115">Reopen the Company Portal app.</span></span> <span data-ttu-id="c911d-116">これで、会社のポータル アプリにサインインできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c911d-116">You should now be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="c911d-117">ポータル サイト アプリを使用できるようにならない場合は、[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)に記載の情報を参考に、詳細な手順について会社のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c911d-117">If you still cannot use the Company Portal app, contact your company support using the information provided on the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) for further instructions.</span></span>

>[!NOTE]
> <span data-ttu-id="c911d-118">この証明書をインストールしても問題が解決せず、別の "証明書が見つかりません" というメッセージが表示される場合は、[不足している証明書をインストールする](your-device-is-missing-an-IT-required-certificate-android.md)別の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c911d-118">If installing this certificate doesn't solve the issue, and you see a different "missing certificate" message, you will need to take additional steps to [install the missing certificate](your-device-is-missing-an-IT-required-certificate-android.md).</span></span>

<span data-ttu-id="c911d-119">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="c911d-119">Still need help?</span></span> <span data-ttu-id="c911d-120">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c911d-120">Contact your company support.</span></span> <span data-ttu-id="c911d-121">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="c911d-121">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
