---
title: "Windows Phone 8.1 デバイス向けの Intune 電子メール設定"
titleSuffix: Azure portal
description: "Windows Phone 8.1 デバイスでの電子メール接続の構成に使用できる Intune 設定について説明します。\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 352d6bd9-ec8c-439e-be3a-ad3daf307df2
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b87fba767bbb8f31fe56b734c943d257f92c0ab9
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="email-profile-settings-for-windows-phone-81-devices-in-microsoft-intune"></a><span data-ttu-id="782c9-103">Microsoft Intune での Windows Phone 8.1 デバイス向けの電子メール プロファイル設定</span><span class="sxs-lookup"><span data-stu-id="782c9-103">Email profile settings for Windows Phone 8.1 devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

- <span data-ttu-id="782c9-104">**[Apply all settings to Windows Phone 8.1 only (すべての設定を Windows Phone 8.1 のみに適用する)]** - これは、Intune クラシック ポータルで構成できる設定です。</span><span class="sxs-lookup"><span data-stu-id="782c9-104">**Apply all settings to Windows Phone 8.1 only** - This is a setting you can configure in the Intune classic portal.</span></span> <span data-ttu-id="782c9-105">Azure Portal では、この設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="782c9-105">In the Azure portal, this setting cannot be changed.</span></span> <span data-ttu-id="782c9-106">これを **[構成済み]** に設定すると、すべての設定が Windows Phone 8.1 デバイスのみに適用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="782c9-106">If this is set to **Configured**, any settings will only be applied to Windows Phone 8.1 devices.</span></span> <span data-ttu-id="782c9-107">**[未構成]** に設定されている場合、これらの設定は Windows 10 Mobile デバイスにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="782c9-107">If set to **Not Configured**, these settings will also apply to Windows 10 Mobile devices.</span></span>
- <span data-ttu-id="782c9-108">**[電子メール サーバー]** - Exchange サーバーのホスト名。</span><span class="sxs-lookup"><span data-stu-id="782c9-108">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="782c9-109">**[アカウント名]** - ユーザーのデバイスに表示される電子メール アカウントの表示名。</span><span class="sxs-lookup"><span data-stu-id="782c9-109">**Account name** - The display name for the email account as it will appear to users on their devices.</span></span>
- <span data-ttu-id="782c9-110">**[AAD からのユーザー名の属性]** - この電子メール プロファイルのユーザー名を生成するために使用される Active Directory (AD) または Azure AD の属性です。</span><span class="sxs-lookup"><span data-stu-id="782c9-110">**Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="782c9-111">**プライマリ SMTP アドレス** (**user1@contoso.com** など) または**ユーザー プリンシパル名** (**user1**、**user1@contoso.com** など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="782c9-111">Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.</span></span>
- <span data-ttu-id="782c9-112">**[AAD からのメール アドレス属性]** - 各デバイスでユーザーの電子メール アドレスを生成する方法。</span><span class="sxs-lookup"><span data-stu-id="782c9-112">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="782c9-113">Exchange へのログインにプライマリ SMTP アドレスを使用する場合は **[プライマリ SMTP アドレス]** を選択し、完全プリンシパル名を電子メール アドレスとして使用する場合は **[ユーザー プリンシパル名]** を使用します。</span><span class="sxs-lookup"><span data-stu-id="782c9-113">Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>


## <a name="security-settings"></a><span data-ttu-id="782c9-114">セキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="782c9-114">Security settings</span></span>

- <span data-ttu-id="782c9-115">**[SSL]** - 電子メールの送受信および Exchange サーバーとの通信に、SSL (Secure Sockets Layer) 通信を使用します。</span><span class="sxs-lookup"><span data-stu-id="782c9-115">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>



## <a name="synchronization-settings"></a><span data-ttu-id="782c9-116">同期設定</span><span class="sxs-lookup"><span data-stu-id="782c9-116">Synchronization settings</span></span>

- <span data-ttu-id="782c9-117">**[同期するメールの量]** - 同期する電子メールの日数を選択するか、利用可能なすべての電子メールを同期する場合は **[無制限]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="782c9-117">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="782c9-118">**[同期スケジュール]** - デバイスが Exchange サーバーからデータを同期するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="782c9-118">**Sync schedule** - Select the schedule by which devices will synchronize data from the Exchange server.</span></span> <span data-ttu-id="782c9-119">**[メッセージが到着したとき]** を選択すると、電子メールが届いたらすぐにデータが同期されます。**[手動]** を選択した場合は、デバイスのユーザーが同期を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="782c9-119">You can also select **As Messages arrive**, which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.</span></span>

## <a name="content-sync-settings"></a><span data-ttu-id="782c9-120">コンテンツ同期設定</span><span class="sxs-lookup"><span data-stu-id="782c9-120">Content sync settings</span></span>

- <span data-ttu-id="782c9-121">**[同期するコンテンツの種類]** - デバイスに同期するコンテンツの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="782c9-121">**Content type to sync** - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="782c9-122">**連絡先**</span><span class="sxs-lookup"><span data-stu-id="782c9-122">**Contacts**</span></span>
    - <span data-ttu-id="782c9-123">**カレンダー**</span><span class="sxs-lookup"><span data-stu-id="782c9-123">**Calendar**</span></span>
    - <span data-ttu-id="782c9-124">**タスク**</span><span class="sxs-lookup"><span data-stu-id="782c9-124">**Tasks**</span></span>
