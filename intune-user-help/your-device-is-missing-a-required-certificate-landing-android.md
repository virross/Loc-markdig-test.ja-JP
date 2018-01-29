---
title: "デバイスに必要な証明書がない | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d5c2b5202b0ac69d18dff5b12be3c04f60062dee
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="your-device-is-missing-a-required-certificate"></a><span data-ttu-id="5a63a-102">デバイスに必要な証明書がない</span><span class="sxs-lookup"><span data-stu-id="5a63a-102">Your device is missing a required certificate</span></span>

## <a name="whats-a-certificate"></a><span data-ttu-id="5a63a-103">証明書について</span><span class="sxs-lookup"><span data-stu-id="5a63a-103">What's a certificate?</span></span>

<span data-ttu-id="5a63a-104">[暗号化](https://technet.microsoft.com/library/cc962030.aspx)は、情報にセキュリティ保護を提供する技術です。</span><span class="sxs-lookup"><span data-stu-id="5a63a-104">[Cryptography](https://technet.microsoft.com/library/cc962030.aspx) is the science of providing security for information.</span></span> <span data-ttu-id="5a63a-105">従来、暗号化は、コード化されたメッセージを渡して[通信の機密性が保たれるようにする](https://technet.microsoft.com/library/cc962019.aspx)ために使用されてきました。</span><span class="sxs-lookup"><span data-stu-id="5a63a-105">Traditionally, cryptography has been used to pass coded messages to [ensure that communication is kept secret](https://technet.microsoft.com/library/cc962019.aspx).</span></span> <span data-ttu-id="5a63a-106">最も単純な形式の暗号化では、文字を置き換えるか入れ替えることで、コード化されたメッセージを読み取り不可能にするか、スクランブル化するか、隠しています。</span><span class="sxs-lookup"><span data-stu-id="5a63a-106">In its simpliest form, cryptography substitutes or transposes letters to create a coded message into an unreadable, scrambled, or hidden message.</span></span> <span data-ttu-id="5a63a-107">デコード キー、つまり_証明書_を持つユーザーのみが、コード化されたメッセージを元の読み取り可能な形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="5a63a-107">Only someone with a decoding key, or _certificate_, can convert the coded message back into its original, readable form.</span></span> <span data-ttu-id="5a63a-108">Android デバイスでは、Intune で証明書を使用して、デバイスと組織のリソース (電子メールやドキュメントなど) 間の無線通信が安全に行われるようにします。</span><span class="sxs-lookup"><span data-stu-id="5a63a-108">Your Android device uses certificates with Intune to make sure that communications between your device and your organizational resources, such as email and documents, are kept safe from one end, through the air, to the other.</span></span>

## <a name="fixing-certificate-issues"></a><span data-ttu-id="5a63a-109">証明書の問題の修正</span><span class="sxs-lookup"><span data-stu-id="5a63a-109">Fixing certificate issues</span></span>

<span data-ttu-id="5a63a-110">Android デバイスが Intune に登録されておらず、会社のサポートが必要とする特定の証明書がない場合は、ポータル サイト アプリにサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5a63a-110">If your Android device isn’t enrolled in Intune, and it’s missing a certain certificate that is required by your company support, you won’t be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="5a63a-111">サインインしようとすると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a63a-111">When you try to sign in, you'll see the following message:</span></span>

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

<span data-ttu-id="5a63a-113">まず実行すべき手順は、[デバイスに通常プレインストールされている証明書が不足](your-device-is-missing-a-preinstalled-certificate-android.md)しているかどうかを確認することです。</span><span class="sxs-lookup"><span data-stu-id="5a63a-113">The first step you should try is to see if your device is [missing a certificate that usually comes preinstalled on it](your-device-is-missing-a-preinstalled-certificate-android.md).</span></span>

<span data-ttu-id="5a63a-114">この手順で解決しない場合、会社のサポートから、[追加のセキュリティのために 2 番目の証明書をインストールするよう要求される](your-device-is-missing-an-IT-required-certificate-android.md)ことがあります。</span><span class="sxs-lookup"><span data-stu-id="5a63a-114">If this doesn't work, your company support could [require you to install a second certificate for additional security](your-device-is-missing-an-IT-required-certificate-android.md).</span></span>

<span data-ttu-id="5a63a-115">サポートが必要な場合は、</span><span class="sxs-lookup"><span data-stu-id="5a63a-115">Still need help?</span></span> <span data-ttu-id="5a63a-116">社内サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="5a63a-116">Contact your company support.</span></span> <span data-ttu-id="5a63a-117">連絡先情報については、[ポータル サイト Web サイト](https://portal.manage.microsoft.com#HelpDeskDialog)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="5a63a-117">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
