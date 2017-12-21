---
title: "暗号化を使用して Android デバイスを保護する方法 | Microsoft Docs"
description: "Android デバイスを保護する"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 8ad13a8534f142ec97fc15759bf863e04c36d266
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-protect-your-android-device-using-encryption"></a><span data-ttu-id="e11b1-103">暗号化を使用して Android デバイスを保護する方法</span><span class="sxs-lookup"><span data-stu-id="e11b1-103">How to protect your Android device using encryption</span></span>

<span data-ttu-id="e11b1-104">デバイスを暗号化するときに、承認されていないユーザーがアクセスできないように保護コード層でデバイスに関する情報をラップします。</span><span class="sxs-lookup"><span data-stu-id="e11b1-104">When you encrypt a device, you are wrapping the information on it in a layer of protective code that prevents unauthorized people from accessing it.</span></span> <span data-ttu-id="e11b1-105">ユーザーの情報を確実にセキュリティで保護するために、組織ではまず、企業のファイル、電子メール、またはデータにアクセスする前にユーザーに Android デバイスを暗号化するよう求める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e11b1-105">As a step towards making sure your information is secured, your organization is requiring you to encrypt your Android device before you can access company files, email, or data.</span></span>

> [!Note]
> <span data-ttu-id="e11b1-106">Huawei 製や Vivo および OPPO 製の特定の Android デバイスは暗号化できません。</span><span class="sxs-lookup"><span data-stu-id="e11b1-106">Certain Android devices, including some made by Huawei and those made by Vivo and OPPO, cannot be encrypted.</span></span> <span data-ttu-id="e11b1-107">詳細については、[こちら](your-device-appears-encrypted-but-cp-says-otherwise-android.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e11b1-107">Find out more [here](your-device-appears-encrypted-but-cp-says-otherwise-android.md).</span></span>

<span data-ttu-id="e11b1-108">電話の登録を解除しても、暗号化は維持されます。</span><span class="sxs-lookup"><span data-stu-id="e11b1-108">If you unenroll your phone, it will remain encrypted.</span></span>

1.  <span data-ttu-id="e11b1-109">デバイスの画面ロック PIN またはパスワードが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e11b1-109">Ensure that a screen lock PIN or password has been set for your device.</span></span>

2.  <span data-ttu-id="e11b1-110">**[設定]** で、**[セキュリティ]** > **[Encrypt Device]\(デバイスの暗号化\)** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e11b1-110">In **Settings**, choose **Security** > **Encrypt Device**.</span></span>
    <span data-ttu-id="e11b1-111">(一部の電話では、"暗号化" オプションを表示するために、**[ストレージ]** > **[ストレージの暗号化]** または **[ストレージ]** > **[画面のロックとセキュリティ]** > **[他のセキュリティ設定]** の順に選択する必要があります。)</span><span class="sxs-lookup"><span data-stu-id="e11b1-111">(On some phones, you’ll need to choose **Storage** > **Storage encryption** or **Storage** > **Lock screen and security** > **Other security settings** to find the "Encrypt" option).</span></span>

3.  <span data-ttu-id="e11b1-112">画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e11b1-112">Follow the onscreen instructions.</span></span> <span data-ttu-id="e11b1-113">暗号化が行われている間、デバイスが何度か再起動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e11b1-113">During encryption, your device might restart several times.</span></span>

### <a name="what-to-do-if-you-have-issues"></a><span data-ttu-id="e11b1-114">問題がある場合の対処方法</span><span class="sxs-lookup"><span data-stu-id="e11b1-114">What to do if you have issues</span></span>
<span data-ttu-id="e11b1-115">**問題**: デバイスに既に暗号化を適用していますが、次のいずれかの状態に遭遇しました。</span><span class="sxs-lookup"><span data-stu-id="e11b1-115">**Issue**: You have already encrypted your device, and you see one of the following:</span></span>

- <span data-ttu-id="e11b1-116">暗号化ボタンが無効です。</span><span class="sxs-lookup"><span data-stu-id="e11b1-116">The encryption button is disabled.</span></span>
- <span data-ttu-id="e11b1-117">暗号化が必要であるというメッセージが引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="e11b1-117">You see a message saying that you still need to encrypt.</span></span>
- <span data-ttu-id="e11b1-118">ポータル サイト アプリを使用しようとすると、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e11b1-118">You get errors when trying to use the Company Portal app.</span></span>

<span data-ttu-id="e11b1-119">**対処方法**</span><span class="sxs-lookup"><span data-stu-id="e11b1-119">**Things to try**</span></span>

- <span data-ttu-id="e11b1-120">デバイスが課金され、接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e11b1-120">Make sure that your device is charged and plugged in.</span></span>
- <span data-ttu-id="e11b1-121">デバイスで PIN やパスワードが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e11b1-121">Make sure that you've set a PIN or password on your device.</span></span>
- <span data-ttu-id="e11b1-122">デバイスに PIN またはパスワードを既に設定してある場合は、次の手順を試してみます。会社のサポートがデバイスのセキュリティを強化する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e11b1-122">If you've already set a PIN or password on your device, try the following steps, which your company support might require to make your device more secure.</span></span> <span data-ttu-id="e11b1-123">Android デバイスの種類により、手順で表示されるメニュー名が若干異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="e11b1-123">The menu names that you see might be slightly different from the ones in the steps, depending on the type of Android device you have.</span></span>

    1. <span data-ttu-id="e11b1-124">**[設定]** > **[ロック画面とセキュリティ]** > **[画面のロック]** の順に進みます。</span><span class="sxs-lookup"><span data-stu-id="e11b1-124">Go to **Settings** > **Lock Screen and Security** > **Screen lock**.</span></span> <span data-ttu-id="e11b1-125">現在の PIN またはパスワードを確認します。</span><span class="sxs-lookup"><span data-stu-id="e11b1-125">Confirm your current PIN or password.</span></span>

    2. <span data-ttu-id="e11b1-126">**[Choose screen lock]** (画面のロックの選択) 画面で、使用する画面ロックの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="e11b1-126">On the **Choose screen lock** screen, choose the type of screen lock you want to use.</span></span> 

    3. <span data-ttu-id="e11b1-127">画面のロックを選択したら、**[ロック画面とセキュリティ]** 画面に戻り、**[安全な起動]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e11b1-127">After you've chosen your screen lock, go back to the **Lock Screen and Security** screen and select **Secure Startup**.</span></span> 
    
    4. <span data-ttu-id="e11b1-128">**[安全な起動]** 画面で、**[Require PIN to start device]\(デバイスの起動に PIN が必要\)** をタップし、**[続行]** をタップします。</span><span class="sxs-lookup"><span data-stu-id="e11b1-128">On the **Secure startup** screen, tap **Require PIN to start device**, and tap **Continue**.</span></span>

    5. <span data-ttu-id="e11b1-129">PIN を選択し (前に入力したものと同じものを入力できます)、**[Confirm your PIN]** (PIN の確認) をタップします。</span><span class="sxs-lookup"><span data-stu-id="e11b1-129">Choose a PIN (you can enter the same one that you entered previously), and tap **Confirm your PIN**.</span></span>

    6. <span data-ttu-id="e11b1-130">ポータル サイト アプリを開き、デバイスを選択して、**[Check Compliance]** (ポリシー準拠状況の確認) をタップします。</span><span class="sxs-lookup"><span data-stu-id="e11b1-130">Open the Company Portal app, select your device, and tap **Check Compliance**.</span></span>

<span data-ttu-id="e11b1-131">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="e11b1-131">Still need help?</span></span> <span data-ttu-id="e11b1-132">会社のサポートに問い合わせるか (連絡先情報については[ポータル Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください)、または <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android チーム</a>にご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="e11b1-132">Contact your company support (check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) for contact information), or write the <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android team</a>.</span></span>
