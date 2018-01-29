---
title: "Exchange Online 用の Exchange Connector"
description: "Exchange ActiveSync モバイル デバイス管理 (MDM) をサポートするために、Intune を Office 365 Exchange サービスに接続する。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7f24c81096ed6081c10a3f26d6cd1a85b82f12e6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a><span data-ttu-id="272de-103">Exchange Online 用の Intune Service to Service Connector の構成</span><span class="sxs-lookup"><span data-stu-id="272de-103">Configure the Intune service to service connector for Exchange Online</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="272de-104">Microsoft Intune と Exchange Online サービスまたは新しい Exchange Online Dedicated サービスを接続するには、この情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="272de-104">Use this information to connect Microsoft Intune and Exchange Online or the new Exchange Online Dedicated service.</span></span> <span data-ttu-id="272de-105">Exchange Online Dedicated 環境が**新しい**バージョンか**従来の**バージョンかを確認するには、アカウント マネージャーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="272de-105">To determine whether your Exchange Online Dedicated environment is the **new** or **legacy** version, contact your account manager.</span></span> <span data-ttu-id="272de-106">Intune は、サブスクリプションごとに任意の種類の Exchange Connector 接続を 1 つだけサポートします。</span><span class="sxs-lookup"><span data-stu-id="272de-106">Intune only supports one Exchange connector connection of any type per subscription.</span></span>

## <a name="service-to-service-connector-requirements"></a><span data-ttu-id="272de-107">Service to Service Connector の要件</span><span class="sxs-lookup"><span data-stu-id="272de-107">Service to Service Connector requirements</span></span>
<span data-ttu-id="272de-108">**Service to Service Connector** は、Exchange Online または Exchange Online Dedicated のみをサポートします。また、オンプレミス インフラストラクチャの要件はありません。</span><span class="sxs-lookup"><span data-stu-id="272de-108">The **Service to Service Connector** supports only Exchange Online or Exchange Online Dedicated and has no requirements for on-premises infrastructure.</span></span>


|              <span data-ttu-id="272de-109">要件</span><span class="sxs-lookup"><span data-stu-id="272de-109">Requirement</span></span>               |                                                                                                            <span data-ttu-id="272de-110">詳細情報</span><span class="sxs-lookup"><span data-stu-id="272de-110">More information</span></span>                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="272de-111">Exchange Online が構成済みで実行中である</span><span class="sxs-lookup"><span data-stu-id="272de-111">Exchange Online configured and running</span></span> |                                                                                 [<span data-ttu-id="272de-112">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="272de-112">Exchange Online</span></span>](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   <span data-ttu-id="272de-113">モバイル デバイス管理機関</span><span class="sxs-lookup"><span data-stu-id="272de-113">Mobile device management authority</span></span>   |                                                       [<span data-ttu-id="272de-114">モバイル デバイスの管理機関を Microsoft Intune に設定します。</span><span class="sxs-lookup"><span data-stu-id="272de-114">Set the mobile device management authority to Microsoft Intune</span></span>](prerequisites-for-enrollment.md#step-2-set-mdm-authority)                                                       |
|       <span data-ttu-id="272de-115">Microsoft Exchange のバージョン</span><span class="sxs-lookup"><span data-stu-id="272de-115">Microsoft Exchange version</span></span>       |                                                                                      <span data-ttu-id="272de-116">Exchange Online サービスまたは新しい Exchange Online Dedicated サービス</span><span class="sxs-lookup"><span data-stu-id="272de-116">Exchange Online or the new Exchange Online Dedicated service</span></span>                                                                                      |
|    <span data-ttu-id="272de-117">Active Directory の同期</span><span class="sxs-lookup"><span data-stu-id="272de-117">Active Directory synchronization</span></span>    | <span data-ttu-id="272de-118">Intune Connector を使用できるようにするには、[Active Directory の同期をセットアップ](/intune/users-permissions-add)して、ローカル ユーザーとセキュリティ グループが Azure Active Directory のインスタンスと同期されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="272de-118">Before you can use the Intune Connector, you must [set up Active Directory synchronization](/intune/users-permissions-add) so that your local users and security groups are synchronized with your instance of Azure Active Directory.</span></span> |

### <a name="exchange-cmdlet-requirements"></a><span data-ttu-id="272de-119">Exchange コマンドレットの要件</span><span class="sxs-lookup"><span data-stu-id="272de-119">Exchange cmdlet requirements</span></span>

<span data-ttu-id="272de-120">Intune Exchange Connector が使用する Exchange Online ユーザー アカウントも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="272de-120">You must also create an Exchange Online user account that is used by the Intune Exchange Connector.</span></span> <span data-ttu-id="272de-121">このアカウントは、Intune 管理コンソールを使用し、次の必要な Windows PowerShell Exchange コマンドレットを実行するアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="272de-121">The account must have permission to use the Intune administration console and to run the following required Windows PowerShell Exchange cmdlets:</span></span>

 - <span data-ttu-id="272de-122">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span><span class="sxs-lookup"><span data-stu-id="272de-122">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span></span>
 - <span data-ttu-id="272de-123">Get-MobileDeviceMailboxPolicy、Set-MobileDeviceMailboxPolicy、New-MobileDeviceMailboxPolicy、Remove-MobileDeviceMailboxPolicy</span><span class="sxs-lookup"><span data-stu-id="272de-123">Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy</span></span>
 - <span data-ttu-id="272de-124">Get-ActiveSyncDeviceAccessRule、Set-ActiveSyncDeviceAccessRule、New-ActiveSyncDeviceAccessRule、Remove-ActiveSyncDeviceAccessRule</span><span class="sxs-lookup"><span data-stu-id="272de-124">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span></span>
 - <span data-ttu-id="272de-125">Get-MobileDeviceStatistics</span><span class="sxs-lookup"><span data-stu-id="272de-125">Get-MobileDeviceStatistics</span></span>
 - <span data-ttu-id="272de-126">Get-MobileDevice</span><span class="sxs-lookup"><span data-stu-id="272de-126">Get-MobileDevice</span></span>
 - <span data-ttu-id="272de-127">Get-ActiveSyncDeviceClass</span><span class="sxs-lookup"><span data-stu-id="272de-127">Get-ActiveSyncDeviceClass</span></span>

## <a name="set-up-the-service-to-service-connector"></a><span data-ttu-id="272de-128">Service to Service Connector を設定します。</span><span class="sxs-lookup"><span data-stu-id="272de-128">Set up the Service to Service Connector</span></span>

1. <span data-ttu-id="272de-129">Exchange 管理者権限と[上記](#exchange-cmdlet-requirements)のコマンドレットのアクセス許可を持つユーザー アカウントで、[Microsoft Intune 管理コンソール](https://manage.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="272de-129">Open the [Microsoft Intune administration console](https://manage.microsoft.com) with a user account that has Exchange admin rights and permissions for the cmdlets [described earlier](#exchange-cmdlet-requirements).</span></span> <span data-ttu-id="272de-130">Microsoft Intune は、現在サインインしているユーザーの電子メール アドレスを使用して、接続をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="272de-130">Microsoft Intune uses the email address of the currently signed-in user to set up the connection.</span></span>

2.  <span data-ttu-id="272de-131">ワークスペースのショートカット ウィンドウで **[管理]** > **[モバイル デバイス管理]** > **[Microsoft Exchange]** > **[Exchange 接続のセットアップ]** の順に進みます。</span><span class="sxs-lookup"><span data-stu-id="272de-131">In the workspace shortcuts pane, choose **ADMIN**>**Mobile Device Management** > **Microsoft Exchange** > **Set Up Exchange Connection**.</span></span>
<span data-ttu-id="272de-132">![Service To Service Connector のセットアップページ](../media/intunesa5cservicetoserviceconnector.png)</span><span class="sxs-lookup"><span data-stu-id="272de-132">![Set up service to service connector page](../media/intunesa5cservicetoserviceconnector.png)</span></span>

3.  <span data-ttu-id="272de-133">**[Exchange 接続のセットアップ]** ページで **[Service To Service Connector のセットアップ]**を選びます。</span><span class="sxs-lookup"><span data-stu-id="272de-133">On the **Set Up Exchange Connection** page, choose **Set Up Service to Service Connector**.</span></span>


<span data-ttu-id="272de-134">Service to Service Connector は自動的に構成され、Exchange Online 環境または新しい Exchange Online Dedicated 環境と同期されます。</span><span class="sxs-lookup"><span data-stu-id="272de-134">The Service to Service Connector automatically configures and synchronizes your Exchange Online or new Exchange Online Dedicated environment.</span></span>

## <a name="validate-your-exchange-connection"></a><span data-ttu-id="272de-135">Exchange 接続の確認</span><span class="sxs-lookup"><span data-stu-id="272de-135">Validate your Exchange connection</span></span>

<span data-ttu-id="272de-136">Exchange Connector を正常に構成した後で、[Microsoft Intune 管理コンソール](https://manage.microsoft.com)に進みます。</span><span class="sxs-lookup"><span data-stu-id="272de-136">After you have successfully configured the Exchange Connector, go to the [Microsoft Intune administration console](https://manage.microsoft.com).</span></span> <span data-ttu-id="272de-137">**[管理]** > **[モバイル デバイス管理]** > **[Microsoft Exchange]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="272de-137">Choose **Admin**> **Mobile Device Management** > **Microsoft Exchange**.</span></span> <span data-ttu-id="272de-138">入力した詳細が **[Exchange の接続情報]** の下に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="272de-138">Then validate that the details you provided appear under **Exchange Connection Information**.</span></span>

<span data-ttu-id="272de-139">また、前回いつ同期が完了したかも確認することができます。</span><span class="sxs-lookup"><span data-stu-id="272de-139">You can also check the time and date of the last successful synchronization attempt.</span></span>
