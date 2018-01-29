---
title: "オンプレミス EAS 用の Exchange Connector"
description: "Connector ツールを使用して、Exchange ActiveSync MDM 用に、Intune 管理コンソールと社内の Exchange Server 間の通信を有効にします。"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41ff4212-a6f5-4374-8731-631f7560cff1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: dfc2101bed60dad6a430470c32b28cae08894351
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="install-the-intune-on-premises-exchange-connector"></a><span data-ttu-id="938c5-103">Intune の内部設置型 Exchange Connector のインストール</span><span class="sxs-lookup"><span data-stu-id="938c5-103">Install the Intune On-premises Exchange Connector</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="938c5-104">モバイル デバイスのメールボックスをホストする Exchange Server と Microsoft Intune が通信できるように接続をセットアップするには、Intune 管理コンソールで内部設置型 Exchange Connector をダウンロードして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="938c5-104">To set up a connection that enables Microsoft Intune to communicate with the Exchange Server that hosts the mailboxes for the mobile devices, you must download and configure the On-premises Exchange Connector from the Intune administration console.</span></span> <span data-ttu-id="938c5-105">Intune は、サブスクリプションごとに任意の種類の Exchange Connector 接続を 1 つだけサポートします。</span><span class="sxs-lookup"><span data-stu-id="938c5-105">Intune only supports one Exchange Connector connection of any type per subscription.</span></span>

## <a name="on-premises-exchange-connector-requirements"></a><span data-ttu-id="938c5-106">内部設置型 Exchange Connector の要件</span><span class="sxs-lookup"><span data-stu-id="938c5-106">On-premises Exchange Connector requirements</span></span>
<span data-ttu-id="938c5-107">以下の表に、内部設置型 Exchange Connector をインストールするコンピューターの要件を示します。</span><span class="sxs-lookup"><span data-stu-id="938c5-107">The following table lists the requirements for the computer on which you install the On-premises Exchange Connector.</span></span>


|            <span data-ttu-id="938c5-108">要件</span><span class="sxs-lookup"><span data-stu-id="938c5-108">Requirement</span></span>             |                                                                                                                                                                                                        <span data-ttu-id="938c5-109">詳細情報</span><span class="sxs-lookup"><span data-stu-id="938c5-109">More information</span></span>                                                                                                                                                                                                        |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         <span data-ttu-id="938c5-110">Operating systems</span><span class="sxs-lookup"><span data-stu-id="938c5-110">Operating systems</span></span>          |                                                                          <span data-ttu-id="938c5-111">Intune は、Windows Server 2008 SP2 64 ビット、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 の任意のエディションを実行しているコンピューター上の内部設置型 Exchange Connector をサポートします。</span><span class="sxs-lookup"><span data-stu-id="938c5-111">Intune supports the On-premises Exchange Connector on a computer that runs any edition of Windows Server 2008 SP2 64-bit, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2.</span></span><br /><br /><span data-ttu-id="938c5-112">Server Core インストールでは、Connector はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="938c5-112">The Connector is not supported on any Server Core installation.</span></span>                                                                          |
|         <span data-ttu-id="938c5-113">Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="938c5-113">Microsoft Exchange</span></span>         |                                                                           <span data-ttu-id="938c5-114">内部設置型 Connector には、Microsoft Exchange 2010 SP1 以降または従来の Exchange Online Dedicated が必要です。</span><span class="sxs-lookup"><span data-stu-id="938c5-114">On-premises Connectors require Microsoft Exchange 2010 SP1 or later or legacy Exchange Online Dedicated.</span></span> <span data-ttu-id="938c5-115">Exchange Online Dedicated 環境が<strong>新しい</strong>構成か<strong>従来の</strong>構成かを確認するには、アカウント マネージャーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="938c5-115">To determine if your Exchange Online Dedicated environment is in the <strong>new</strong> or <strong>legacy</strong> configuration, contact your account manager.</span></span>                                                                           |
| <span data-ttu-id="938c5-116">モバイル デバイス管理機関</span><span class="sxs-lookup"><span data-stu-id="938c5-116">Mobile device management authority</span></span> |                                                                                                                                                       <span data-ttu-id="938c5-117">[モバイル デバイス管理機関を Intune に設定します](prerequisites-for-enrollment.md#step-2-set-mdm-authority)。</span><span class="sxs-lookup"><span data-stu-id="938c5-117">[Set the mobile device management authority to Intune](prerequisites-for-enrollment.md#step-2-set-mdm-authority).</span></span>                                                                                                                                                        |
|              <span data-ttu-id="938c5-118">ハードウェア</span><span class="sxs-lookup"><span data-stu-id="938c5-118">Hardware</span></span>              |                                                                                                                                                     <span data-ttu-id="938c5-119">コネクタをインストールするコンピューターには、1.6 GHz の CPU と 2 GB の RAM と 10 GB の空きディスク容量が必要です。</span><span class="sxs-lookup"><span data-stu-id="938c5-119">The computer on which you install the connector requires a 1.6 GHz CPU with 2 GB of RAM and 10 GB of free disk space.</span></span>                                                                                                                                                      |
|  <span data-ttu-id="938c5-120">Active Directory の同期</span><span class="sxs-lookup"><span data-stu-id="938c5-120">Active Directory synchronization</span></span>  |                                                                             <span data-ttu-id="938c5-121">Connector を使用して Intune を Exchange Server に接続するには、[Active Directory の同期をセットアップ](/intune/users-permissions-add)して、ローカル ユーザーとセキュリティ グループが Azure Active Directory のインスタンスと同期されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="938c5-121">Before you can use Connector to connect Intune to your Exchange Server, you must [set up Active Directory synchronization](/intune/users-permissions-add) so that your local users and security groups are synchronized with your instance of Azure Active Directory.</span></span>                                                                              |
|        <span data-ttu-id="938c5-122">その他のソフトウェア</span><span class="sxs-lookup"><span data-stu-id="938c5-122">Additional software</span></span>         |                                                                                                                                           <span data-ttu-id="938c5-123">コネクタをホストするコンピューターに、Microsoft .NET Framework 4.5 および Windows PowerShell 2.0 の完全インストールがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="938c5-123">A full installation of Microsoft .NET Framework 4.5 and Windows PowerShell 2.0 must be installed on the computer that hosts the connector.</span></span>                                                                                                                                           |
|              <span data-ttu-id="938c5-124">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="938c5-124">Network</span></span>               | <span data-ttu-id="938c5-125">コネクタをインストールするコンピューターは、Exchange Server をホストするドメインと信頼関係があるドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="938c5-125">The computer on which you install the connector must be in a domain that has a trust relationship to the domain that hosts your Exchange Server.</span></span><br /><br /><span data-ttu-id="938c5-126">コンピューターは、ポート 80 と 443 でファイアウォールとプロキシ サーバー経由で Intune サービスにアクセスできるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="938c5-126">The computer requires configurations to enable it to access the Intune service through firewalls and proxy servers over Ports 80 and 443.</span></span> <span data-ttu-id="938c5-127">Intune によって使用されるドメインには、manage.microsoft.com、&#42;manage.microsoft.com、および &#42;.manage.microsoft.com が含まれます。</span><span class="sxs-lookup"><span data-stu-id="938c5-127">Domains that are used by Intune include manage.microsoft.com, &#42;manage.microsoft.com, and &#42;.manage.microsoft.com.</span></span> |

### <a name="exchange-cmdlet-requirements"></a><span data-ttu-id="938c5-128">Exchange コマンドレットの要件</span><span class="sxs-lookup"><span data-stu-id="938c5-128">Exchange cmdlet requirements</span></span>

<span data-ttu-id="938c5-129">Intune Exchange Connector が使用する Active Directory ユーザー アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="938c5-129">You must create an Active Directory user account that is used by the Intune Exchange Connector.</span></span> <span data-ttu-id="938c5-130">アカウントには、次の必須の Windows PowerShell Exchange コマンドレットを実行するための権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="938c5-130">The account must have permission to run the following required Windows PowerShell Exchange cmdlets:</span></span>


 -   <span data-ttu-id="938c5-131">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span><span class="sxs-lookup"><span data-stu-id="938c5-131">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span></span>
 -   <span data-ttu-id="938c5-132">Get-CasMailbox、Set-CasMailbox</span><span class="sxs-lookup"><span data-stu-id="938c5-132">Get-CasMailbox, Set-CasMailbox</span></span>
 -   <span data-ttu-id="938c5-133">Get-ActiveSyncMailboxPolicy、Set-ActiveSyncMailboxPolicy、New-ActiveSyncMailboxPolicy、Remove-ActiveSyncMailboxPolicy</span><span class="sxs-lookup"><span data-stu-id="938c5-133">Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy</span></span>
 -   <span data-ttu-id="938c5-134">Get-ActiveSyncDeviceAccessRule、Set-ActiveSyncDeviceAccessRule、New-ActiveSyncDeviceAccessRule、Remove-ActiveSyncDeviceAccessRule</span><span class="sxs-lookup"><span data-stu-id="938c5-134">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span></span>
 -   <span data-ttu-id="938c5-135">Get-ActiveSyncDeviceStatistics</span><span class="sxs-lookup"><span data-stu-id="938c5-135">Get-ActiveSyncDeviceStatistics</span></span>
 -   <span data-ttu-id="938c5-136">Get-ActiveSyncDevice</span><span class="sxs-lookup"><span data-stu-id="938c5-136">Get-ActiveSyncDevice</span></span>
 -   <span data-ttu-id="938c5-137">Get-ExchangeServer</span><span class="sxs-lookup"><span data-stu-id="938c5-137">Get-ExchangeServer</span></span>
 -   <span data-ttu-id="938c5-138">Get-ActiveSyncDeviceClass</span><span class="sxs-lookup"><span data-stu-id="938c5-138">Get-ActiveSyncDeviceClass</span></span>
 -   <span data-ttu-id="938c5-139">Get-Recipient</span><span class="sxs-lookup"><span data-stu-id="938c5-139">Get-Recipient</span></span>
 -   <span data-ttu-id="938c5-140">Clear-ActiveSyncDevice、Remove-ActiveSyncDevice</span><span class="sxs-lookup"><span data-stu-id="938c5-140">Clear-ActiveSyncDevice, Remove-ActiveSyncDevice</span></span>
 -   <span data-ttu-id="938c5-141">Set-ADServerSettings</span><span class="sxs-lookup"><span data-stu-id="938c5-141">Set-ADServerSettings</span></span>
 -   <span data-ttu-id="938c5-142">Get-Command</span><span class="sxs-lookup"><span data-stu-id="938c5-142">Get-Command</span></span>

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a><span data-ttu-id="938c5-143">内部設置型 Exchange Connector ソフトウェア インストール パッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="938c5-143">Download the On-premises Exchange Connector software installation package</span></span>

1. <span data-ttu-id="938c5-144">内部設置型 Exchange Connector のサポートされている Windows Server オペレーティング システムで、Exchange Server を使用するライセンスを持つ Exchange テナント内の管理者であるユーザー アカウントを使用して、[Microsoft Intune 管理コンソール](https://manage.microsoft.com) (https://manage.microsoft.com) を開きます。</span><span class="sxs-lookup"><span data-stu-id="938c5-144">On a supported Windows Server operating system for the On-premises Exchange Connector, open the [Microsoft Intune administration console](https://manage.microsoft.com) (https://manage.microsoft.com) with a user account that is an administrator in the Exchange tenant and that has a license to use Exchange Server.</span></span>
<span data-ttu-id="938c5-145">![[Exchange 接続のセットアップ] を開く](../media/ExchangeConnector.gif)</span><span class="sxs-lookup"><span data-stu-id="938c5-145">![Open set up Exchange Connection](../media/ExchangeConnector.gif)</span></span>

2.  <span data-ttu-id="938c5-146">ワークスペースのショートカット ウィンドウで **[管理]**>**[モバイル デバイス管理]** > **[Microsoft Exchange]**>**[Exchange 接続のセットアップ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="938c5-146">In the workspace shortcuts pane, choose **Admin**>**Mobile Device Management** > **Microsoft Exchange**>**Setup Exchange Connection**.</span></span>

3.  <span data-ttu-id="938c5-147">**[Exchange 接続のセットアップ]** ページで **[On-Premises Connector のダウンロード]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="938c5-147">On the **Setup Exchange Connection** page, choose **Download On-Premises Connector**.</span></span>

4.  <span data-ttu-id="938c5-148">内部設置型 Exchange Connector は、開いたり保存したりできる圧縮 (.zip) フォルダーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="938c5-148">The On-premises Exchange Connector is contained in a compressed (.zip) folder that can be opened or saved.</span></span> <span data-ttu-id="938c5-149">**[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** を選んで、圧縮フォルダーを安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="938c5-149">In the **File Download** dialog box, choose **Save** to store the compressed folder to a secure location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="938c5-150">オンプレミス Exchange Connector フォルダー内のファイルの名前を変更したり、ファイルを移動したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="938c5-150">Do not rename or move the files that are in the On-premises Exchange Connector folder.</span></span> <span data-ttu-id="938c5-151">フォルダーの内容を移動したり、名前を変更したりすると、インストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="938c5-151">Moving or renaming the folder's contents will cause the installation to fail.</span></span>

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a><span data-ttu-id="938c5-152">Intune の内部設置型 Exchange Connector のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="938c5-152">Install and configure the Intune On-premises Exchange Connector</span></span>
<span data-ttu-id="938c5-153">次の手順を実行して、Intune の内部設置型 Exchange Connector をインストールします。</span><span class="sxs-lookup"><span data-stu-id="938c5-153">Perform the following steps to install the Intune On-premises Exchange Connector.</span></span> <span data-ttu-id="938c5-154">内部設置型 Exchange Connector は、Intune サブスクリプション 1 つで 1 台のコンピューターに 1 回だけインストールできます。</span><span class="sxs-lookup"><span data-stu-id="938c5-154">The On-premises Exchange Connector can only be installed once per Intune subscription, and only on one computer.</span></span> <span data-ttu-id="938c5-155">内部設置型 Exchange Connector をもう 1 つ構成しようとすると、新しい接続で元の接続が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="938c5-155">If you try to configure an additional On-premises Exchange Connector, the new connection will replace the original one.</span></span>

1. <span data-ttu-id="938c5-156">内部設置型 Connector のサポートされているオペレーティング システムで、**Exchange_Connector_Setup.zip** を安全な場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="938c5-156">On a supported operating system for the On-premises Connector, extract the files in **Exchange_Connector_Setup.zip** to a secure location.</span></span>

2. <span data-ttu-id="938c5-157">ファイルが抽出されたら、抽出されたフォルダーを開き、**Exchange_Connector_Setup.exe** をダブルクリックして内部設置型 Exchange Connector をインストールします。</span><span class="sxs-lookup"><span data-stu-id="938c5-157">After the files are extracted, open the extracted folder and double-click **Exchange_Connector_Setup.exe** to install the On-premises Exchange Connector.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="938c5-158">抽出先のフォルダーが安全な場所にない場合は、内部設置型 Connector をインストールした後で、**WindowsIntune.accountcert** という証明書ファイルを削除してください。</span><span class="sxs-lookup"><span data-stu-id="938c5-158">If the destination folder is not a secure location, you should delete the certificate file **WindowsIntune.accountcert** after you install the On-premises Connector.</span></span>

3. <span data-ttu-id="938c5-159">**[Microsoft Intune Exchange Connector]** ダイアログ ボックスで、**[内部設置型 Microsoft Exchange Server]** または **[ホストされた Microsoft Exchange Server]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="938c5-159">In the **Microsoft Intune Exchange Connector** dialog box, select either **On-premises Microsoft Exchange Server** or **Hosted Microsoft Exchange Server**.</span></span>

   ![Exchange サーバーの種類の選択](../media/IntuneSA1dconfigureExchConnector.png)

   <span data-ttu-id="938c5-161">内部設置型 Exchange Server の場合、**クライアント アクセス サーバー** ロールをホストする Exchange サーバーのサーバー名または完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="938c5-161">For an On-premises Exchange server, provide either the server name or the fully-qualified domain name of the Exchange server that hosts the **Client Access Server** role.</span></span>

   <span data-ttu-id="938c5-162">ホスト型 Exchange Server の場合、Exchange Server のアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="938c5-162">For a hosted Exchange server, provide the Exchange server address.</span></span> <span data-ttu-id="938c5-163">ホスト型 Exchange サーバーの URL を見つけるには:</span><span class="sxs-lookup"><span data-stu-id="938c5-163">To find the hosted Exchange server URL:</span></span>

   1. <span data-ttu-id="938c5-164">Office 365 の Outlook Web App を開きます。</span><span class="sxs-lookup"><span data-stu-id="938c5-164">Open the Outlook Web App for Office 365.</span></span>

   2. <span data-ttu-id="938c5-165">左上の **?** </span><span class="sxs-lookup"><span data-stu-id="938c5-165">Choose the **?**</span></span> <span data-ttu-id="938c5-166">アイコンを選択し、**[バージョン情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="938c5-166">icon at the upper left, and then select **About**.</span></span>

   3. <span data-ttu-id="938c5-167">**[POP 外部サーバー]** の値を探します。</span><span class="sxs-lookup"><span data-stu-id="938c5-167">Locate the **POP External Server** value.</span></span>

   4. <span data-ttu-id="938c5-168">**[プロキシ サーバー]** を選んで、ホスト型 Exchange サーバーのプロキシ サーバー設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="938c5-168">Choose **Proxy Server** to specify proxy server settings for your hosted Exchange server.</span></span>
       1. <span data-ttu-id="938c5-169">**[モバイル デバイス情報を同期するときにプロキシ サーバーを使用する]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="938c5-169">Select **Use a proxy server when synchronizing mobile device information**.</span></span>

       2. <span data-ttu-id="938c5-170">サーバーへのアクセスに使用する **[プロキシ サーバー名]** と **[ポート番号]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="938c5-170">Enter the **proxy server name** and the **port number** to be used to access the server.</span></span>

       3. <span data-ttu-id="938c5-171">プロキシ サーバーにアクセスできるユーザーの資格情報を指定する必要がある場合は、**[資格情報を使用してプロキシ サーバーに接続する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="938c5-171">If it's necessary to provide user credentials to access the proxy server, select **Use credentials to connect to the proxy server**.</span></span> <span data-ttu-id="938c5-172">次に、**ドメイン\ユーザー**と**パスワード**を入力します。</span><span class="sxs-lookup"><span data-stu-id="938c5-172">Then enter the **domain\user** and the **password**.</span></span>

       4. <span data-ttu-id="938c5-173">**[OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="938c5-173">Choose **OK**.</span></span>

   5. <span data-ttu-id="938c5-174">**[ユーザー (ドメイン\ユーザー)]** フィールドと **[パスワード]** フィールドに、Exchange Server への接続に必要な資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="938c5-174">In the **User (Domain\user)** and **Password** fields, enter the credentials that are necessary to connect to your Exchange server.</span></span>

   6.  <span data-ttu-id="938c5-175">ユーザーの Exchange Server メールボックスに通知を送信するために必要な管理資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="938c5-175">Provide the necessary administrative credentials to send notifications to a user’s Exchange Server mailbox.</span></span> <span data-ttu-id="938c5-176">これらの通知は、Intune で条件付きアクセス ポリシーにより構成できます。</span><span class="sxs-lookup"><span data-stu-id="938c5-176">You can configure these notifications with Conditional Access policies in Intune.</span></span>

       <span data-ttu-id="938c5-177">自動検出サービスと Exchange Web Services が Exchange クライアント アクセス サーバーで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="938c5-177">Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server.</span></span> <span data-ttu-id="938c5-178">詳細については、「[クライアント アクセス サーバー](https://technet.microsoft.com/library/dd298114.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="938c5-178">For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).</span></span>

   7.  <span data-ttu-id="938c5-179">**[パスワード]** フィールドに、このアカウントで Intune から Exchange Server にアクセスするのに必要なパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="938c5-179">In the **Password** field, provide the password for this account to enable Intune to access the Exchange Server.</span></span>

   8. <span data-ttu-id="938c5-180">**[接続]**を選びます。</span><span class="sxs-lookup"><span data-stu-id="938c5-180">Choose **Connect**.</span></span>

<span data-ttu-id="938c5-181">接続が構成されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="938c5-181">It might take a few minutes for the connection to be configured.</span></span>

<span data-ttu-id="938c5-182">接続の構成中、Exchange Connector にインターネットへのアクセスに必要なプロキシの設定が保存されます。</span><span class="sxs-lookup"><span data-stu-id="938c5-182">During configuration, the Exchange Connector stores your proxy settings to enable access to the Internet.</span></span> <span data-ttu-id="938c5-183">プロキシの設定を変更した場合は、Exchange Connector に更新されたプロキシ設定が適用されるように、Exchange Connector を構成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="938c5-183">If your proxy settings change, you will have to reconfigure the Exchange Connector to apply the updated proxy settings to the Exchange Connector.</span></span>

<span data-ttu-id="938c5-184">Exchange Connector が接続をセットアップすると、Exchange Connector で管理されているユーザーに関連付けられたモバイル デバイスが自動的に同期されて、Exchange Connector に追加されます。</span><span class="sxs-lookup"><span data-stu-id="938c5-184">After the Exchange Connector sets up the connection, mobile devices that are associated with users that are managed in Exchange Connector are automatically synchronized and added to the Exchange Connector.</span></span> <span data-ttu-id="938c5-185">この同期が完了するまで時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="938c5-185">This synchronization might take some time to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="938c5-186">内部設置型 Exchange Connector をインストールし、いずれかの時点で Exchange 接続を削除した場合、インストールされていたコンピューターから内部設置型 Exchange Connector をアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="938c5-186">If you have installed the On-premises Exchange Connector, and if at some point you delete the Exchange connection, you must uninstall the On-premises Exchange Connector from the computer onto which it was installed.</span></span>

## <a name="validate-the-exchange-connection"></a><span data-ttu-id="938c5-187">Exchange 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="938c5-187">Validate the Exchange connection</span></span>

<span data-ttu-id="938c5-188">Exchange Connector を正常に構成したら、接続のステータスと前回の成功した同期の試行を表示できます。</span><span class="sxs-lookup"><span data-stu-id="938c5-188">After you have successfully configured the Exchange Connector, you can view the status of the connection and the last successful synchronization attempt.</span></span> <span data-ttu-id="938c5-189">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理者]** ワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="938c5-189">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose the **ADMIN** workspace.</span></span> <span data-ttu-id="938c5-190">**[モバイル デバイス管理]** で **[Microsoft Exchange]** を選択して、**[Exchange の接続情報]** に表示される設定内容の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="938c5-190">Under **Mobile Device Management**, choose **Microsoft Exchange**, and then validate that the details you provided appear under **Exchange Connection Information**.</span></span>


<span data-ttu-id="938c5-191">また、前回いつ同期が完了したかも確認することができます。</span><span class="sxs-lookup"><span data-stu-id="938c5-191">You can also check the time and date of the last successful synchronization attempt.</span></span>
