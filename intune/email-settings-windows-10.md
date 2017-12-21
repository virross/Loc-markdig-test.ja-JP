---
title: "Windows 10 デバイス向けの Intune 電子メール設定"
titleSuffix: Azure portal
description: "Windows 10 デバイスで電子メール接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ffafbd0-4b5d-4c86-a46b-611f9b7a58e5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6a6d079772584c414117359317c86177daeac561
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="email-profile-settings-for-windows-10-devices-in-microsoft-intune"></a><span data-ttu-id="0b6df-103">Microsoft Intune での Windows 10 デバイス向けの電子メール プロファイル設定</span><span class="sxs-lookup"><span data-stu-id="0b6df-103">Email profile settings for Windows 10 devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



- <span data-ttu-id="0b6df-104">**[電子メール サーバー]** - Exchange サーバーのホスト名。</span><span class="sxs-lookup"><span data-stu-id="0b6df-104">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="0b6df-105">**[アカウント名]** - ユーザーのデバイスに表示される電子メール アカウントの表示名。</span><span class="sxs-lookup"><span data-stu-id="0b6df-105">**Account name** - The display name for the email account as it will appear to users on their devices.</span></span>
- <span data-ttu-id="0b6df-106">**[AAD からのユーザー名の属性]** - この電子メール プロファイルのユーザー名を生成するために使用される Active Directory (AD) または Azure AD の属性です。</span><span class="sxs-lookup"><span data-stu-id="0b6df-106">**Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="0b6df-107">**プライマリ SMTP アドレス** (**user1@contoso.com** など) または**ユーザー プリンシパル名** (**user1**、**user1@contoso.com** など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b6df-107">Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.</span></span>
- <span data-ttu-id="0b6df-108">**[AAD からのメール アドレス属性]** - 各デバイスでユーザーの電子メール アドレスを生成する方法。</span><span class="sxs-lookup"><span data-stu-id="0b6df-108">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="0b6df-109">Exchange へのログインにプライマリ SMTP アドレスを使用する場合は **[プライマリ SMTP アドレス]** を選択し、完全プリンシパル名を電子メール アドレスとして使用する場合は **[ユーザー プリンシパル名]** を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b6df-109">Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>


## <a name="security-settings"></a><span data-ttu-id="0b6df-110">セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="0b6df-110">Security settings</span></span>

- <span data-ttu-id="0b6df-111">**[SSL]** - 電子メールの送受信および Exchange サーバーとの通信に、SSL (Secure Sockets Layer) 通信を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b6df-111">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>



## <a name="synchronization-settings"></a><span data-ttu-id="0b6df-112">同期設定</span><span class="sxs-lookup"><span data-stu-id="0b6df-112">Synchronization settings</span></span>

- <span data-ttu-id="0b6df-113">**[同期するメールの量]** - 同期する電子メールの日数を選択するか、利用可能なすべての電子メールを同期する場合は **[無制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b6df-113">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="0b6df-114">**[同期スケジュール]** - デバイスが Exchange サーバーからデータを同期するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b6df-114">**Sync schedule** - Select the schedule by which devices will synchronize data from the Exchange server.</span></span> <span data-ttu-id="0b6df-115">**[メッセージが到着したとき]** を選択すると、電子メールが届いたらすぐにデータが同期されます。**[手動]** を選択した場合は、デバイスのユーザーが同期を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b6df-115">You can also select **As Messages arrive**, which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.</span></span>

## <a name="content-sync-settings"></a><span data-ttu-id="0b6df-116">コンテンツ同期設定</span><span class="sxs-lookup"><span data-stu-id="0b6df-116">Content sync settings</span></span>

- <span data-ttu-id="0b6df-117">**[同期するコンテンツの種類]** - デバイスに同期するコンテンツの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b6df-117">**Content type to sync** - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="0b6df-118">**連絡先**</span><span class="sxs-lookup"><span data-stu-id="0b6df-118">**Contacts**</span></span>
    - <span data-ttu-id="0b6df-119">**カレンダー**</span><span class="sxs-lookup"><span data-stu-id="0b6df-119">**Calendar**</span></span>
    - <span data-ttu-id="0b6df-120">**タスク**</span><span class="sxs-lookup"><span data-stu-id="0b6df-120">**Tasks**</span></span>
