---
title: "Android と Android for Work デバイスの Intune 電子メール設定"
titleSuffix: Azure portal
description: "Android デバイスでの電子メール接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c50f1cd58557f877d4eaea0f76ecd0c371b3da1d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="email-profile-settings-for-android--devices-in-microsoft-intune"></a><span data-ttu-id="cf7ed-103">Microsoft Intune での Android デバイス向けの電子メール プロファイル設定</span><span class="sxs-lookup"><span data-stu-id="cf7ed-103">Email profile settings for Android  devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="cf7ed-104">Intune 管理者は、次の Android デバイスに対して電子メール設定の作成と割り当てができます。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-104">As an Intune admin, you can create and assign email settings to the following Android devices:</span></span>
- [<span data-ttu-id="cf7ed-105">Android Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="cf7ed-105">Android Samsung KNOX Standard</span></span>](#android-samsung-knox-standard-email-settings)
- [<span data-ttu-id="cf7ed-106">Android for Work</span><span class="sxs-lookup"><span data-stu-id="cf7ed-106">Android for Work</span></span>](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a><span data-ttu-id="cf7ed-107">Android Samsung KNOX Standard の電子メール設定</span><span class="sxs-lookup"><span data-stu-id="cf7ed-107">Android Samsung KNOX Standard email settings</span></span>
- <span data-ttu-id="cf7ed-108">**[電子メール サーバー]** - Exchange サーバーのホスト名。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-108">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="cf7ed-109">**[アカウント名]** - ユーザーのデバイスに表示される電子メール アカウントの表示名。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-109">**Account name** - The display name for the email account as it appears to users on their devices.</span></span>
- <span data-ttu-id="cf7ed-110">**[AAD からのユーザー名の属性]** - この名前は Active Directory (AD) または Azure AD の属性で、この電子メール プロファイルのユーザー名の生成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-110">**Username attribute from AAD** - This name is the attribute in Active Directory (AD) or Azure AD used to generate the username for this email profile.</span></span> <span data-ttu-id="cf7ed-111">**プライマリ SMTP アドレス** (user1@contoso.com など) または**ユーザー プリンシパル名** (user1、user1@contoso.com など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-111">Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.</span></span>
- <span data-ttu-id="cf7ed-112">**[AAD からのメール アドレス属性]** - 各デバイスでユーザーの電子メール アドレスを生成する方法。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-112">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="cf7ed-113">Exchange へのログインにプライマリ SMTP アドレスを使用する場合は **[プライマリ SMTP アドレス]** を選択し、完全プリンシパル名を電子メール アドレスとして使用する場合は **[ユーザー プリンシパル名]** を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-113">Select **Primary SMTP Address** to use the primary SMTP address to log in to Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>
- <span data-ttu-id="cf7ed-114">**[認証方法]** - 電子メール プロファイルで使用する認証方法として、**[ユーザー名とパスワード]** または **[証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-114">**Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.</span></span>
    - <span data-ttu-id="cf7ed-115">**[証明書]** を選択した場合は、Exchange 接続の認証のために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-115">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.</span></span>

### <a name="security-settings"></a><span data-ttu-id="cf7ed-116">セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="cf7ed-116">Security settings</span></span>

- <span data-ttu-id="cf7ed-117">**[SSL]** - 電子メールの送受信および Exchange サーバーとの通信に、SSL (Secure Sockets Layer) 通信を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-117">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>
- <span data-ttu-id="cf7ed-118">**[S/MIME]** - S/MIME 暗号化を使用して電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-118">**S/MIME** - Send outgoing email using S/MIME encryption.</span></span>
    - <span data-ttu-id="cf7ed-119">**[証明書]** を選択した場合は、Exchange 接続の認証のために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-119">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.</span></span>

### <a name="synchronization-settings"></a><span data-ttu-id="cf7ed-120">同期設定</span><span class="sxs-lookup"><span data-stu-id="cf7ed-120">Synchronization settings</span></span>

- <span data-ttu-id="cf7ed-121">**[同期するメールの量]** - 同期する電子メールの日数を選択するか、利用可能なすべての電子メールを同期する場合は **[無制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-121">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="cf7ed-122">**[同期スケジュール]** - デバイスが Exchange サーバーからデータを同期するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-122">**Sync schedule** - Select the schedule by which devices synchronize data from the Exchange server.</span></span> <span data-ttu-id="cf7ed-123">**[メッセージの着信時]** を選択すると、電子メールの着信時にデータが同期されます。**[手動]** を選択した場合は、デバイスのユーザーが同期を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-123">You can also select **As Messages arrive**, which synchronizes data when it arrives, or **Manual**, where the user of the device must initiate the synchronization.</span></span>

### <a name="content-sync-settings"></a><span data-ttu-id="cf7ed-124">コンテンツ同期設定</span><span class="sxs-lookup"><span data-stu-id="cf7ed-124">Content sync settings</span></span>

- <span data-ttu-id="cf7ed-125">**[同期するコンテンツの種類]** - デバイスに同期するコンテンツの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-125">**Content type to sync** - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="cf7ed-126">**連絡先**</span><span class="sxs-lookup"><span data-stu-id="cf7ed-126">**Contacts**</span></span>
    - <span data-ttu-id="cf7ed-127">**カレンダー**</span><span class="sxs-lookup"><span data-stu-id="cf7ed-127">**Calendar**</span></span>
    - <span data-ttu-id="cf7ed-128">**タスク**</span><span class="sxs-lookup"><span data-stu-id="cf7ed-128">**Tasks**</span></span>

## <a name="android-for-work-email-settings"></a><span data-ttu-id="cf7ed-129">Android for Work の電子メール設定</span><span class="sxs-lookup"><span data-stu-id="cf7ed-129">Android for Work email settings</span></span>

- <span data-ttu-id="cf7ed-130">**[メール アプリ]** - **[Gmail]** または **[Nine Work]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-130">**Email app** - Select either **Gmail** or **Nine Work**</span></span>
- <span data-ttu-id="cf7ed-131">**[電子メール サーバー]** - Exchange サーバーのホスト名。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-131">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="cf7ed-132">**[AAD からのユーザー名の属性]** - この名前は Active Directory (AD) または Azure AD の属性で、この電子メール プロファイルのユーザー名の生成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-132">**Username attribute from AAD** - This name is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="cf7ed-133">**プライマリ SMTP アドレス** (user1@contoso.com など) または**ユーザー プリンシパル名** (user1、user1@contoso.com など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-133">Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.</span></span>
- <span data-ttu-id="cf7ed-134">**[AAD からのメール アドレス属性]** - 各デバイスでユーザーの電子メール アドレスを生成する方法。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-134">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="cf7ed-135">**[ユーザー プリンシパル名]**  を選択して電子メール アドレスとして完全プリンシパル名を使用するか、**[ユーザー名]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-135">Select **User Principal Name** to use the full principal name as the email address or **User name**.</span></span>
- <span data-ttu-id="cf7ed-136">**[認証方法]** - 電子メール プロファイルで使用する認証方法として、**[ユーザー名とパスワード]** または **[証明書]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-136">**Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.</span></span>
    - <span data-ttu-id="cf7ed-137">**[証明書]** を選択した場合は、Exchange 接続の認証のために事前に作成しておいたクライアント SCEP または PKCS 証明書プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-137">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.</span></span>
- <span data-ttu-id="cf7ed-138">**[SSL]** - 電子メールの送受信および Exchange サーバーとの通信に、SSL (Secure Sockets Layer) 通信を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-138">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>
- <span data-ttu-id="cf7ed-139">**[同期するメールの量]** - 同期する電子メールの日数を選択するか、利用可能なすべての電子メールを同期する場合は **[無制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-139">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="cf7ed-140">**[同期するコンテンツの種類]** (Nine Work のみ) - デバイスに同期するコンテンツの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf7ed-140">**Content type to sync** (Nine Work only) - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="cf7ed-141">**連絡先**</span><span class="sxs-lookup"><span data-stu-id="cf7ed-141">**Contacts**</span></span>
    - <span data-ttu-id="cf7ed-142">**カレンダー**</span><span class="sxs-lookup"><span data-stu-id="cf7ed-142">**Calendar**</span></span>
    - <span data-ttu-id="cf7ed-143">**タスク**</span><span class="sxs-lookup"><span data-stu-id="cf7ed-143">**Tasks**</span></span>
