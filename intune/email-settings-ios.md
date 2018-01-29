---
title: "iOS デバイス向けの Intune 電子メール設定"
titleSuffix: Azure portal
description: "iOS デバイスでの電子メール接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff590506f1549b42554f75dc6f9f1ef29e7f728c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="email-profile-settings-for-ios-devices-in-microsoft-intune"></a><span data-ttu-id="dbc24-103">Microsoft Intune での iOS デバイス向けの電子メール プロファイル設定</span><span class="sxs-lookup"><span data-stu-id="dbc24-103">Email profile settings for iOS devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

- <span data-ttu-id="dbc24-104">**[電子メール サーバー]** - Exchange サーバーのホスト名。</span><span class="sxs-lookup"><span data-stu-id="dbc24-104">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="dbc24-105">**[アカウント名]** - ユーザーのデバイスに表示される電子メール アカウントの表示名。</span><span class="sxs-lookup"><span data-stu-id="dbc24-105">**Account name** - The display name for the email account as it will appear to users on their devices.</span></span>
- <span data-ttu-id="dbc24-106">**[AAD からのユーザー名の属性]** - この電子メール プロファイルのユーザー名を生成するために使用される Active Directory (AD) または Azure AD の属性です。</span><span class="sxs-lookup"><span data-stu-id="dbc24-106">**Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="dbc24-107">**プライマリ SMTP アドレス** (**user1@contoso.com** など) または**ユーザー プリンシパル名** (**user1**、**user1@contoso.com** など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbc24-107">Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.</span></span>
- <span data-ttu-id="dbc24-108">**[AAD からのメール アドレス属性]** - 各デバイスでユーザーの電子メール アドレスを生成する方法。</span><span class="sxs-lookup"><span data-stu-id="dbc24-108">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="dbc24-109">Exchange へのログインにプライマリ SMTP アドレスを使用する場合は **[プライマリ SMTP アドレス]** を選択し、完全プリンシパル名を電子メール アドレスとして使用する場合は **[ユーザー プリンシパル名]** を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc24-109">Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>
- <span data-ttu-id="dbc24-110">**[認証方法]** - 電子メール プロファイルで使用する認証方法として、**[ユーザー名とパスワード]** または **[証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbc24-110">**Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.</span></span>
    - <span data-ttu-id="dbc24-111">**[証明書]** を選択した場合は、Exchange 接続の認証に使用するために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbc24-111">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that will be used to authenticate the Exchange connection.</span></span>
- <span data-ttu-id="dbc24-112">**[SSL]** - 電子メールの送受信および Exchange サーバーとの通信に、SSL (Secure Sockets Layer) 通信を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc24-112">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>
- <span data-ttu-id="dbc24-113">**[S/MIME]** - S/MIME 署名を使用して送信メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="dbc24-113">**S/MIME** - Send outgoing email using S/MIME signing.</span></span>
    - <span data-ttu-id="dbc24-114">**[証明書]** を選択した場合は、Exchange 接続の認証に使用するために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbc24-114">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that will be used to authenticate the Exchange connection.</span></span>
- <span data-ttu-id="dbc24-115">**[同期するメールの量]** - 同期する電子メールの日数を選択するか、利用可能なすべての電子メールを同期する場合は **[無制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbc24-115">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="dbc24-116">**[他の電子メール アカウントにメッセージを移動することを許可する]** - デバイスで構成されている複数のアカウント間で、ユーザーが電子メール メッセージを移動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dbc24-116">**Allow messages to be moved to other email accounts** - This allows users to move email messages between different accounts they have configured on their device.</span></span>
- <span data-ttu-id="dbc24-117">**[サード パーティ アプリケーションから電子メールを送信できるようにする]** - 電子メールを送信するための既定のアカウントとしてこのプロファイルを選択することをユーザーに許可し、(たとえば、ファイルを電子メールに添付する目的で) ネイティブの電子メール アプリで電子メールを開くことをサードパーティ製アプリに許可します。</span><span class="sxs-lookup"><span data-stu-id="dbc24-117">**Allow email to be sent from third party applications** - Allow the user to select this profile as the default account for sending email, and allow third-party applications to open email in the native email app, for example, to attach files to email.</span></span>
- <span data-ttu-id="dbc24-118">**[最近使用した電子メール アドレスを同期する]** - この機能を使用すると、ユーザーは、デバイスで最近使用された電子メール アドレスのリストをサーバーと同期できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dbc24-118">**Synchronize recently used email addresses** - This feature allows users to synchronize the list of email addresses that have been recently used on the device with the server.</span></span>
