---
title: "オンプレミス EAS を Intune と接続する Exchange Connector のセットアップ"
titleSuffix: Azure portal
description: "コネクタ ツールを使って Intune とオンプレミス Exchange Server との通信を有効にする"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9650afefc8ba0ba782e95b28feaaf1aaceea8d7f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a><span data-ttu-id="e0467-103">Microsoft Intune Azure で Intune のオンプレミス Exchange Connector をセットアップする</span><span class="sxs-lookup"><span data-stu-id="e0467-103">Set up the Intune on-premises Exchange Connector in Microsoft Intune Azure</span></span>

<span data-ttu-id="e0467-104">オンプレミス Exchange Server 環境では、オンプレミス Exchange Connector で Intune を使用して、デバイスが Intune に登録されていて Intune のデバイス コンプライアンス ポリシーに準拠しているかどうかに基づき、デバイスのオンプレミス Exchange のメールボックスへのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e0467-104">On-premises Exchange Server environments can use the Intune on-premises Exchange connector to manage devices access to on-premises Exchange mailboxes based on whether or not the devices are enrolled into Intune and compliant with Intune device compliance policies.</span></span> <span data-ttu-id="e0467-105">オンプレミス Exchange Connector はまた、Exchange Active Sync (EAS) の既存のレコードを Intune と同期することによって、オンプレミス Exchange Server に接続するモバイル デバイスを検出します。</span><span class="sxs-lookup"><span data-stu-id="e0467-105">The on-premises Exchange connector is also responsible for discovering mobile devices that connect to on-premises Exchange Servers by synchronizing the existing Exchange Active Sync (EAS) record with Intune.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0467-106">Intune は、サブスクリプションごとに任意の種類のオンプレミス Exchange Connector 接続を 1 つだけサポートします。</span><span class="sxs-lookup"><span data-stu-id="e0467-106">Intune only supports one on-premises Exchange Connector connection of any type per subscription.</span></span>

<span data-ttu-id="e0467-107">オンプレミス Exchange Server と通信するために Microsoft Intune を有効にする接続を設定するには、次の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0467-107">To set up a connection that enables Microsoft Intune to communicate with the on-premises Exchange Server, you need to follow the steps below:</span></span>

1.  <span data-ttu-id="e0467-108">Azure Portal から、Intune のオンプレミス Exchange Connector をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e0467-108">Download the Intune on-premises Exchange Connector from the Azure portal.</span></span>
2.  <span data-ttu-id="e0467-109">Intune のオンプレミス Exchange Connector をインストールし、構成します。</span><span class="sxs-lookup"><span data-stu-id="e0467-109">Install and configure the Intune on-premises Exchange connector.</span></span>
3.  <span data-ttu-id="e0467-110">Exchange 接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="e0467-110">Validate the Exchange connection.</span></span>

## <a name="on-premises-exchange-connector-requirements"></a><span data-ttu-id="e0467-111">内部設置型 Exchange Connector の要件</span><span class="sxs-lookup"><span data-stu-id="e0467-111">On-premises Exchange Connector requirements</span></span>
<span data-ttu-id="e0467-112">以下の表に、内部設置型 Exchange Connector をインストールするコンピューターの要件を示します。</span><span class="sxs-lookup"><span data-stu-id="e0467-112">The following table lists the requirements for the computer on which you install the On-premises Exchange Connector.</span></span>

|<span data-ttu-id="e0467-113">要件</span><span class="sxs-lookup"><span data-stu-id="e0467-113">Requirement</span></span>|<span data-ttu-id="e0467-114">説明</span><span class="sxs-lookup"><span data-stu-id="e0467-114">More information</span></span>|
|---------------|--------------------|
|<span data-ttu-id="e0467-115">Operating systems</span><span class="sxs-lookup"><span data-stu-id="e0467-115">Operating systems</span></span>|<span data-ttu-id="e0467-116">Intune は、Windows Server 2008 SP2 64 ビット、Windows Server 2008 R2、Windows Server 2012、または Windows Server 2012 R2 の任意のエディションを実行しているコンピューター上の内部設置型 Exchange Connector をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e0467-116">Intune supports the On-premises Exchange Connector on a computer that runs any edition of Windows Server 2008 SP2 64-bit, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2.</span></span><br /><br /><span data-ttu-id="e0467-117">Server Core インストールでは、Connector はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e0467-117">The Connector is not supported on any Server Core installation.</span></span>|
|<span data-ttu-id="e0467-118">Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="e0467-118">Microsoft Exchange</span></span>|<span data-ttu-id="e0467-119">内部設置型 Connector には、Microsoft Exchange 2010 SP1 以降または従来の Exchange Online Dedicated が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0467-119">On-premises Connectors require Microsoft Exchange 2010 SP1 or later or legacy Exchange Online Dedicated.</span></span> <span data-ttu-id="e0467-120">Exchange Online Dedicated 環境が**新しい**構成か**従来の**構成かを確認するには、アカウント マネージャーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="e0467-120">To determine if your Exchange Online Dedicated environment is in the **new** or **legacy** configuration, contact your account manager.</span></span>|
|<span data-ttu-id="e0467-121">モバイル デバイス管理機関</span><span class="sxs-lookup"><span data-stu-id="e0467-121">Mobile device management authority</span></span>| <span data-ttu-id="e0467-122">[モバイル デバイス管理機関を Intune に設定します](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="e0467-122">[Set the mobile device management authority to Intune](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).</span></span>|
|<span data-ttu-id="e0467-123">ハードウェア</span><span class="sxs-lookup"><span data-stu-id="e0467-123">Hardware</span></span>|<span data-ttu-id="e0467-124">コネクタをインストールするコンピューターには、1.6 GHz の CPU と 2 GB の RAM と 10 GB の空きディスク容量が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0467-124">The computer on which you install the connector requires a 1.6 GHz CPU with 2 GB of RAM and 10 GB of free disk space.</span></span>|<span data-ttu-id="e0467-125">users-add.md</span><span class="sxs-lookup"><span data-stu-id="e0467-125">users-add.md</span></span>
|<span data-ttu-id="e0467-126">Active Directory の同期</span><span class="sxs-lookup"><span data-stu-id="e0467-126">Active Directory synchronization</span></span>|<span data-ttu-id="e0467-127">Connector を使用して Intune を Exchange Server に接続するには、[Active Directory の同期をセットアップ](users-add.md)して、ローカル ユーザーとセキュリティ グループが Azure Active Directory のインスタンスと同期されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0467-127">Before you can use Connector to connect Intune to your Exchange Server, you must [set up Active Directory synchronization](users-add.md) so that your local users and security groups are synchronized with your instance of Azure Active Directory.</span></span>|
|<span data-ttu-id="e0467-128">その他のソフトウェア</span><span class="sxs-lookup"><span data-stu-id="e0467-128">Additional software</span></span>|<span data-ttu-id="e0467-129">コネクタをホストするコンピューターに、Microsoft .NET Framework 4.5 および Windows PowerShell 2.0 の完全インストールがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0467-129">A full installation of Microsoft .NET Framework 4.5 and Windows PowerShell 2.0 must be installed on the computer that hosts the connector.</span></span>|
|<span data-ttu-id="e0467-130">Network (ネットワーク)</span><span class="sxs-lookup"><span data-stu-id="e0467-130">Network</span></span>|<span data-ttu-id="e0467-131">コネクタをインストールするコンピューターは、Exchange Server をホストするドメインと信頼関係があるドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0467-131">The computer on which you install the connector must be in a domain that has a trust relationship to the domain that hosts your Exchange Server.</span></span><br /><br /><span data-ttu-id="e0467-132">コンピューターは、ポート 80 と 443 でファイアウォールとプロキシ サーバー経由で Intune サービスにアクセスできるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0467-132">The computer requires configurations to enable it to access the Intune service through firewalls and proxy servers over Ports 80 and 443.</span></span> <span data-ttu-id="e0467-133">Intune によって使用されるドメインには、manage.microsoft.com、&#42;manage.microsoft.com、および &#42;.manage.microsoft.com が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0467-133">Domains that are used by Intune include manage.microsoft.com, &#42;manage.microsoft.com, and &#42;.manage.microsoft.com.</span></span>|


### <a name="exchange-cmdlet-requirements"></a><span data-ttu-id="e0467-134">Exchange コマンドレットの要件</span><span class="sxs-lookup"><span data-stu-id="e0467-134">Exchange cmdlet requirements</span></span>

<span data-ttu-id="e0467-135">Intune Exchange Connector が使用する Active Directory ユーザー アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0467-135">You must create an Active Directory user account that is used by the Intune Exchange Connector.</span></span> <span data-ttu-id="e0467-136">アカウントには、次の必須の Windows PowerShell Exchange コマンドレットを実行するための権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0467-136">The account must have permission to run the following required Windows PowerShell Exchange cmdlets:</span></span>


 -   <span data-ttu-id="e0467-137">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span><span class="sxs-lookup"><span data-stu-id="e0467-137">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span></span>
 -   <span data-ttu-id="e0467-138">Get-CasMailbox、Set-CasMailbox</span><span class="sxs-lookup"><span data-stu-id="e0467-138">Get-CasMailbox, Set-CasMailbox</span></span>
 -   <span data-ttu-id="e0467-139">Get-ActiveSyncMailboxPolicy、Set-ActiveSyncMailboxPolicy、New-ActiveSyncMailboxPolicy、Remove-ActiveSyncMailboxPolicy</span><span class="sxs-lookup"><span data-stu-id="e0467-139">Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy</span></span>
 -   <span data-ttu-id="e0467-140">Get-ActiveSyncDeviceAccessRule、Set-ActiveSyncDeviceAccessRule、New-ActiveSyncDeviceAccessRule、Remove-ActiveSyncDeviceAccessRule</span><span class="sxs-lookup"><span data-stu-id="e0467-140">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span></span>
 -   <span data-ttu-id="e0467-141">Get-ActiveSyncDeviceStatistics</span><span class="sxs-lookup"><span data-stu-id="e0467-141">Get-ActiveSyncDeviceStatistics</span></span>
 -   <span data-ttu-id="e0467-142">Get-ActiveSyncDevice</span><span class="sxs-lookup"><span data-stu-id="e0467-142">Get-ActiveSyncDevice</span></span>
 -   <span data-ttu-id="e0467-143">Get-ExchangeServer</span><span class="sxs-lookup"><span data-stu-id="e0467-143">Get-ExchangeServer</span></span>
 -   <span data-ttu-id="e0467-144">Get-ActiveSyncDeviceClass</span><span class="sxs-lookup"><span data-stu-id="e0467-144">Get-ActiveSyncDeviceClass</span></span>
 -   <span data-ttu-id="e0467-145">Get-Recipient</span><span class="sxs-lookup"><span data-stu-id="e0467-145">Get-Recipient</span></span>
 -   <span data-ttu-id="e0467-146">Clear-ActiveSyncDevice、Remove-ActiveSyncDevice</span><span class="sxs-lookup"><span data-stu-id="e0467-146">Clear-ActiveSyncDevice, Remove-ActiveSyncDevice</span></span>
 -   <span data-ttu-id="e0467-147">Set-ADServerSettings</span><span class="sxs-lookup"><span data-stu-id="e0467-147">Set-ADServerSettings</span></span>
 -   <span data-ttu-id="e0467-148">Get-Command</span><span class="sxs-lookup"><span data-stu-id="e0467-148">Get-Command</span></span>

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a><span data-ttu-id="e0467-149">内部設置型 Exchange Connector ソフトウェア インストール パッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="e0467-149">Download the On-premises Exchange Connector software installation package</span></span>

1. <span data-ttu-id="e0467-150">オンプレミス Exchange Connector のサポートされている Windows Server オペレーティング システムで、Exchange Server を使用するライセンスを持つオンプレミス Exchange Server 内の管理者であるユーザー アカウントを使用して、[Azure Portal](http://portal.azure.com) を開きサインインします。</span><span class="sxs-lookup"><span data-stu-id="e0467-150">On a supported Windows Server operating system for the On-premises Exchange Connector, open the [Azure portal](http://portal.azure.com) and sign in with a user account that is an administrator in the on-premises Exchange server, and that has a license to use Exchange Server.</span></span>

2. <span data-ttu-id="e0467-151">左側のメニューから **[その他のサービス]** を選択し、テキスト ボックス フィルターに「**Intune**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e0467-151">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="e0467-152">**[Intune]** を選択して Intune ダッシュボードを開き、**[オンプレミス アクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0467-152">Choose **Intune**, the Intune Dashboard opens, choose **On-premises access**.</span></span>

4. <span data-ttu-id="e0467-153">**[オンプレミス アクセス - Exchange ActiveSync のコネクタ]** ブレードで、**[セットアップ]** セクションから **[オンプレミス コネクタをダウンロードします]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0467-153">On the **On-premises access - Exchange ActiveSync connector** blade, from the **Setup** section, choose **Download the on-premises connector**.</span></span>

5.  <span data-ttu-id="e0467-154">内部設置型 Exchange Connector は、開いたり保存したりできる圧縮 (.zip) フォルダーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0467-154">The On-premises Exchange Connector is contained in a compressed (.zip) folder that can be opened or saved.</span></span> <span data-ttu-id="e0467-155">**[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** を選んで、圧縮フォルダーを安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="e0467-155">In the **File Download** dialog box, choose **Save** to store the compressed folder to a secure location.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e0467-156">オンプレミス Exchange Connector フォルダー内のファイルの名前を変更したり、ファイルを移動したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="e0467-156">Do not rename or move the files that are in the on-premises Exchange Connector folder.</span></span> <span data-ttu-id="e0467-157">フォルダーの内容を移動したり、名前を変更したりすると、Exchange Connector のインストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="e0467-157">Moving or renaming the folder's contents will cause the Exchange Connector installation to fail.</span></span>

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a><span data-ttu-id="e0467-158">Intune の内部設置型 Exchange Connector のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="e0467-158">Install and configure the Intune On-premises Exchange Connector</span></span>
<span data-ttu-id="e0467-159">次の手順を実行して、Intune の内部設置型 Exchange Connector をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e0467-159">Perform the following steps to install the Intune On-premises Exchange Connector.</span></span> <span data-ttu-id="e0467-160">内部設置型 Exchange Connector は、Intune サブスクリプション 1 つで 1 台のコンピューターに 1 回だけインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e0467-160">The On-premises Exchange Connector can only be installed once per Intune subscription, and only on one computer.</span></span> <span data-ttu-id="e0467-161">内部設置型 Exchange Connector をもう 1 つ構成しようとすると、新しい接続で元の接続が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e0467-161">If you try to configure an additional On-premises Exchange Connector, the new connection will replace the original one.</span></span>

1.  <span data-ttu-id="e0467-162">内部設置型 Connector のサポートされているオペレーティング システムで、**Exchange_Connector_Setup.zip** を安全な場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="e0467-162">On a supported operating system for the On-premises Connector, extract the files in **Exchange_Connector_Setup.zip** to a secure location.</span></span>

2.  <span data-ttu-id="e0467-163">ファイルが抽出されたら、抽出されたフォルダーを開き、**Exchange_Connector_Setup.exe** をダブルクリックして内部設置型 Exchange Connector をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e0467-163">After the files are extracted, open the extracted folder and double-click **Exchange_Connector_Setup.exe** to install the On-premises Exchange Connector.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e0467-164">抽出先のフォルダーが安全な場所にない場合は、内部設置型 Connector をインストールした後で、**WindowsIntune.accountcert** という証明書ファイルを削除してください。</span><span class="sxs-lookup"><span data-stu-id="e0467-164">If the destination folder is not a secure location, you should delete the certificate file **WindowsIntune.accountcert** after you install the On-premises Connector.</span></span>

3.  <span data-ttu-id="e0467-165">**[Microsoft Intune Exchange Connector]** ダイアログ ボックスで、**[内部設置型 Microsoft Exchange Server]** または **[ホストされた Microsoft Exchange Server]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0467-165">In the **Microsoft Intune Exchange Connector** dialog box, select either **On-premises Microsoft Exchange Server** or **Hosted Microsoft Exchange Server**.</span></span>

  ![Exchange サーバーの種類の選択](./media/intune-sa-exchange-connector-config.png)

  <span data-ttu-id="e0467-167">内部設置型 Exchange Server の場合、**クライアント アクセス サーバー** ロールをホストする Exchange サーバーのサーバー名または完全修飾ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0467-167">For an On-premises Exchange server, provide either the server name or the fully-qualified domain name of the Exchange server that hosts the **Client Access Server** role.</span></span>

  <span data-ttu-id="e0467-168">ホスト型 Exchange Server の場合、Exchange Server のアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0467-168">For a hosted Exchange server, provide the Exchange server address.</span></span> <span data-ttu-id="e0467-169">ホスト型 Exchange サーバーの URL を見つけるには:</span><span class="sxs-lookup"><span data-stu-id="e0467-169">To find the hosted Exchange server URL:</span></span>

    1. <span data-ttu-id="e0467-170">Office 365 の Outlook Web App を開きます。</span><span class="sxs-lookup"><span data-stu-id="e0467-170">Open the Outlook Web App for Office 365.</span></span>

    2. <span data-ttu-id="e0467-171">左上の **?** </span><span class="sxs-lookup"><span data-stu-id="e0467-171">Choose the **?**</span></span> <span data-ttu-id="e0467-172">アイコンを選択し、**[バージョン情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0467-172">icon at the upper left, and then select **About**.</span></span>

    3. <span data-ttu-id="e0467-173">**[POP 外部サーバー]** の値を探します。</span><span class="sxs-lookup"><span data-stu-id="e0467-173">Locate the **POP External Server** value.</span></span>

    4. <span data-ttu-id="e0467-174">**[プロキシ サーバー]** を選んで、ホスト型 Exchange サーバーのプロキシ サーバー設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0467-174">Choose **Proxy Server** to specify proxy server settings for your hosted Exchange server.</span></span>
        1. <span data-ttu-id="e0467-175">**[モバイル デバイス情報を同期するときにプロキシ サーバーを使用する]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0467-175">Select **Use a proxy server when synchronizing mobile device information**.</span></span>

        2. <span data-ttu-id="e0467-176">サーバーへのアクセスに使用する **[プロキシ サーバー名]** と **[ポート番号]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0467-176">Enter the **proxy server name** and the **port number** to be used to access the server.</span></span>

        3. <span data-ttu-id="e0467-177">プロキシ サーバーにアクセスできるユーザーの資格情報を指定する必要がある場合は、**[資格情報を使用してプロキシ サーバーに接続する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0467-177">If it's necessary to provide user credentials to access the proxy server, select **Use credentials to connect to the proxy server**.</span></span> <span data-ttu-id="e0467-178">次に、**ドメイン\ユーザー**と**パスワード**を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0467-178">Then enter the **domain\user** and the **password**.</span></span>

        4. <span data-ttu-id="e0467-179">**[OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="e0467-179">Choose **OK**.</span></span>

    5. <span data-ttu-id="e0467-180">**[ユーザー (ドメイン\ユーザー)]** フィールドと **[パスワード]** フィールドに、Exchange Server への接続に必要な資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0467-180">In the **User (Domain\user)** and **Password** fields, enter the credentials that are necessary to connect to your Exchange server.</span></span>

    6.  <span data-ttu-id="e0467-181">ユーザーの Exchange Server メールボックスに通知を送信するために必要な管理資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0467-181">Provide the necessary administrative credentials to send notifications to a user’s Exchange Server mailbox.</span></span> <span data-ttu-id="e0467-182">これらの通知は、Intune で条件付きアクセス ポリシーにより構成できます。</span><span class="sxs-lookup"><span data-stu-id="e0467-182">You can configure these notifications with Conditional Access policies in Intune.</span></span>

        <span data-ttu-id="e0467-183">自動検出サービスと Exchange Web Services が Exchange クライアント アクセス サーバーで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0467-183">Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server.</span></span> <span data-ttu-id="e0467-184">詳細については、「[クライアント アクセス サーバー](https://technet.microsoft.com/library/dd298114.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0467-184">For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).</span></span>

    7.  <span data-ttu-id="e0467-185">**[パスワード]** フィールドに、このアカウントで Intune から Exchange Server にアクセスするのに必要なパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e0467-185">In the **Password** field, provide the password for this account to enable Intune to access the Exchange Server.</span></span>

    8. <span data-ttu-id="e0467-186">**[接続]**を選びます。</span><span class="sxs-lookup"><span data-stu-id="e0467-186">Choose **Connect**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e0467-187">接続が構成されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e0467-187">It might take a few minutes for the connection to be configured.</span></span>

<span data-ttu-id="e0467-188">接続の構成中、Exchange Connector にインターネットへのアクセスに必要なプロキシの設定が保存されます。</span><span class="sxs-lookup"><span data-stu-id="e0467-188">During configuration, the Exchange Connector stores your proxy settings to enable access to the Internet.</span></span> <span data-ttu-id="e0467-189">プロキシの設定を変更した場合は、Exchange Connector に更新されたプロキシ設定が適用されるように、Exchange Connector を構成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0467-189">If your proxy settings change, you will have to reconfigure the Exchange Connector to apply the updated proxy settings to the Exchange Connector.</span></span>

<span data-ttu-id="e0467-190">Exchange Connector が接続をセットアップすると、Exchange Connector で管理されているユーザーに関連付けられたモバイル デバイスが自動的に同期されて、Exchange Connector に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e0467-190">After the Exchange Connector sets up the connection, mobile devices that are associated with users that are managed in Exchange Connector are automatically synchronized and added to the Exchange Connector.</span></span> <span data-ttu-id="e0467-191">この同期が完了するまで時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0467-191">This synchronization might take some time to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="e0467-192">内部設置型 Exchange Connector をインストールし、いずれかの時点で Exchange 接続を削除した場合、インストールされていたコンピューターから内部設置型 Exchange Connector をアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0467-192">If you have installed the On-premises Exchange Connector, and if at some point you delete the Exchange connection, you must uninstall the On-premises Exchange Connector from the computer onto which it was installed.</span></span>

## <a name="on-premises-exchange-connector-high-availability-support"></a><span data-ttu-id="e0467-193">内部設置型 Exchange connector の高可用性のサポート</span><span class="sxs-lookup"><span data-stu-id="e0467-193">On-premises Exchange connector high availability support</span></span> 
<span data-ttu-id="e0467-194">Exchange connector には、指定された CA を使用して Exchange への接続が作成された後、コネクタは他の CASs を探索する権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="e0467-194">After the Exchange connector creates a connection to Exchange using the specified CAS, the connector has the ability to discovery other CASs.</span></span> <span data-ttu-id="e0467-195">プライマリの CA が使用できなくなった場合、コネクタはフェールオーバー別の CA に場合は、使用可能なプライマリ CA までできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0467-195">If the primary CAS becomes unavailable, the connector will failover to another CAS, if available, until the primary CAS becomes available.</span></span> <span data-ttu-id="e0467-196">この機能は既定でオンにします。</span><span class="sxs-lookup"><span data-stu-id="e0467-196">This feature is on by default.</span></span> <span data-ttu-id="e0467-197">次の手順を使用して、この機能を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e0467-197">You can turn this feature off by using the following procedure:</span></span>
1. <span data-ttu-id="e0467-198">Exchange Connector がインストールされているサーバー上には、%*ProgramData*%\Microsoft\Windows Intune Exchange Connector です。</span><span class="sxs-lookup"><span data-stu-id="e0467-198">On the server where the Exchange Connector is installed, go to %*ProgramData*%\Microsoft\Windows Intune Exchange Connector.</span></span> 
2. <span data-ttu-id="e0467-199">テキスト エディターを使用してを開く**OnPremisesExchangeConnectorServiceConfiguration.xml**です。</span><span class="sxs-lookup"><span data-stu-id="e0467-199">Using a text editor, open **OnPremisesExchangeConnectorServiceConfiguration.xml**.</span></span>
3. <span data-ttu-id="e0467-200">変更&lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt;に&lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt;機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e0467-200">Change &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; to &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt; to disable the feature.</span></span>    


## <a name="monitor-the-exchange-connector-activity"></a><span data-ttu-id="e0467-201">Exchange Connector アクティビティを監視する</span><span class="sxs-lookup"><span data-stu-id="e0467-201">Monitor the Exchange connector activity</span></span>

<span data-ttu-id="e0467-202">Exchange Connector を正常に構成したら、接続のステータスと前回の成功した同期の試行を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e0467-202">After you have successfully configured the Exchange Connector, you can view the status of the connection and the last successful synchronization attempt.</span></span> <span data-ttu-id="e0467-203">Exchange Connector 接続を確認するには、以下のことを行います。</span><span class="sxs-lookup"><span data-stu-id="e0467-203">To validate the Exchange Connector connection:</span></span>

1. <span data-ttu-id="e0467-204">Intune ダッシュボードで、**[オンプレミス アクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0467-204">On the Intune Dashboard, choose **On-premises access**.</span></span>
2. <span data-ttu-id="e0467-205">**[管理]** で、**[Exchange On-Premises のアクセス]** を選択して接続状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="e0467-205">Under **Manage**, select **Exchange on-premises access** to verify the connection status.</span></span>

<span data-ttu-id="e0467-206">また、前回いつ同期が完了したかも確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e0467-206">You can also check the time and date of the last successful synchronization attempt.</span></span>

### <a name="system-center-operations-manager-scom-management-pack"></a><span data-ttu-id="e0467-207">System Center Operations Manager (SCOM) 管理パック</span><span class="sxs-lookup"><span data-stu-id="e0467-207">System Center Operations Manager (SCOM) management pack</span></span>

<span data-ttu-id="e0467-208">Intune 1710 リリース以降では、[Exchange Connector および Intune の SCOM 管理パック](https://www.microsoft.com/en-us/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0467-208">Beginning with the Intune 1710 release, you can use the [SCOM management pack for Exchange connector and Intune](https://www.microsoft.com/en-us/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True).</span></span> <span data-ttu-id="e0467-209">問題のトラブルシューティングを行う必要がある場合、これにより別の方法で Exchange Connector を監視できます。</span><span class="sxs-lookup"><span data-stu-id="e0467-209">This gives you different ways of monitoring the Exchange connector when you need to troubleshoot issues.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e0467-210">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e0467-210">Next steps</span></span>
[<span data-ttu-id="e0467-211">Exchange On-premises の条件付きアクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e0467-211">Create a conditional access policy for Exchange on-premises</span></span>](conditional-access-exchange-create.md)