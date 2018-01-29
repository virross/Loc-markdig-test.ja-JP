---
title: "Intune で PKCS 証明書を構成して管理する"
titleSuffix: Intune on Azure
description: "Intune で PKCS 証明書を作成して割り当てます。"
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2731ba102c6a10fa417f43f8f2cd359204f51cbe
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2018
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a><span data-ttu-id="0e316-103">Intune で PKCS 証明書を構成して管理する</span><span class="sxs-lookup"><span data-stu-id="0e316-103">Configure and manage PKCS certificates with Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a><span data-ttu-id="0e316-104">要件</span><span class="sxs-lookup"><span data-stu-id="0e316-104">Requirements</span></span>

<span data-ttu-id="0e316-105">Intune でPKCS 証明書を使用するには、次のようなインフラストラクチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="0e316-105">To use PKCS certificates with Intune, you must have the following infrastructure:</span></span>

* <span data-ttu-id="0e316-106">構成済みの既存の Active Directory Domain Services (AD DS) ドメイン。</span><span class="sxs-lookup"><span data-stu-id="0e316-106">An existing Active Directory Domain Services (AD DS) domain configured.</span></span>
 
  <span data-ttu-id="0e316-107">AD DS のインストールや構成の方法の詳細については、「[AD DS の設計と計画](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning)」の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0e316-107">If you need more information about how to install and configure AD DS see the article [AD DS Design and Planning](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).</span></span>

* <span data-ttu-id="0e316-108">構成済みの既存のエンタープライズ証明機関 (CA)。</span><span class="sxs-lookup"><span data-stu-id="0e316-108">An existing Enterprise Certification Authority (CA) configured.</span></span>

  <span data-ttu-id="0e316-109">Active Directory 証明書サービス (AD CS) のインストールや構成の方法の詳細が必要な場合は、「[Active Directory 証明書サービス ステップ バイ ステップ ガイド](https://technet.microsoft.com/library/cc772393)」の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0e316-109">If you need more information about how to install and configure Active Directory Certificate Services (AD CS) see the article [Active Directory Certificate Services Step-by-Step Guide](https://technet.microsoft.com/library/cc772393).</span></span>

  > [!WARNING]
  > <span data-ttu-id="0e316-110">Intune ではスタンドアロン CA ではなく、エンタープライズ証明機関 (CA) の AD CS を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e316-110">Intune requires you to run AD CS with an Enterprise Certification Authority (CA), not a Standalone CA.</span></span>

* <span data-ttu-id="0e316-111">エンタープライズ CA に接続されているクライアント。</span><span class="sxs-lookup"><span data-stu-id="0e316-111">A client that has connectivity to the Enterprise CA.</span></span>
* <span data-ttu-id="0e316-112">エンタープライズ CA のルート証明書のエクスポートされたコピーです。</span><span class="sxs-lookup"><span data-stu-id="0e316-112">An exported copy of your root certificate from your Enterprise CA.</span></span>
* <span data-ttu-id="0e316-113">Intune ポータルからダウンロードされた Microsoft Intune Certificate Connector (NDESConnectorSetup.exe)。</span><span class="sxs-lookup"><span data-stu-id="0e316-113">The Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) downloaded from your Intune Portal.</span></span>
* <span data-ttu-id="0e316-114">Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) をホスト可能な Windows Server。</span><span class="sxs-lookup"><span data-stu-id="0e316-114">A Windows Server available to host the Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).</span></span>

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a><span data-ttu-id="0e316-115">エンタープライズ CA からルート証明書をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0e316-115">Export the root certificate from the Enterprise CA</span></span>

<span data-ttu-id="0e316-116">VPN、WiFi、およびその他のリソースの認証には、各デバイスにルート CA 証明書または中間 CA 証明書が必要となります。</span><span class="sxs-lookup"><span data-stu-id="0e316-116">You need a root or intermediate CA certificate on each device for authentication with VPN, WiFi, and other resources.</span></span> <span data-ttu-id="0e316-117">次の手順では、エンタープライズ CA から必要な証明書を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e316-117">The following steps explain how to get the required certificate from your Enterprise CA.</span></span>

1. <span data-ttu-id="0e316-118">管理特権があるアカウントでエンタープライズ CA にログインします。</span><span class="sxs-lookup"><span data-stu-id="0e316-118">Log in to your Enterprise CA with an account that has administrative privileges.</span></span>
2. <span data-ttu-id="0e316-119">コマンド プロンプトを管理者として開きます。</span><span class="sxs-lookup"><span data-stu-id="0e316-119">Open a command prompt as an administrator.</span></span>
3. <span data-ttu-id="0e316-120">あとでアクセスできる場所にルート CA 証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="0e316-120">Export the Root CA Certificate to a location where you can access it later.</span></span>

   <span data-ttu-id="0e316-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0e316-121">For example:</span></span>

4. <span data-ttu-id="0e316-122">ウィザードが完了した後、ウィザードを閉じる前に、**[証明書コネクタの UI を起動]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e316-122">After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.</span></span>

   `certutil -ca.cert certnew.cer`

   <span data-ttu-id="0e316-123">詳細については、[証明書を管理するための Certutil タスク](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0e316-123">For more information, see [Certutil tasks for managing certificates](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).</span></span>

## <a name="configure-certificate-templates-on-the-certification-authority"></a><span data-ttu-id="0e316-124">証明機関で証明書テンプレートを構成する</span><span class="sxs-lookup"><span data-stu-id="0e316-124">Configure certificate templates on the certification authority</span></span>

1. <span data-ttu-id="0e316-125">管理特権があるアカウントでエンタープライズ CA にログインします。</span><span class="sxs-lookup"><span data-stu-id="0e316-125">Log in to your Enterprise CA with an account that has administrative privileges.</span></span>
2. <span data-ttu-id="0e316-126">**[証明機関]** コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e316-126">Open the **Certification Authority** console.</span></span>
3. <span data-ttu-id="0e316-127">**[証明書テンプレート]** を右クリックして、**[管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e316-127">Right-click **Certificate Templates** and choose **Manage**.</span></span>
4. <span data-ttu-id="0e316-128">[**ユーザー**証明書テンプレート] に移動して右クリックし、**[テンプレートの複製]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e316-128">Locate the **User** certificate template, right-click it and choose **Duplicate Template**.</span></span> <span data-ttu-id="0e316-129">**[新しいテンプレートのプロパティ]** ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="0e316-129">A window opens, **Properties of New Template**.</span></span>
5. <span data-ttu-id="0e316-130">**[互換性]** タブで次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-130">On the **Compatibility** tab</span></span>
   * <span data-ttu-id="0e316-131">**[証明機関]** に**[Windows Server 2008 R2]** を設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-131">Set **Certification Authority** to **Windows Server 2008 R2**</span></span>
   * <span data-ttu-id="0e316-132">**[証明書の受信者]** に**[Windows 7 / Server 2008 R2]** を設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-132">Set **Certificate recipient** to **Windows 7 / Server 2008 R2**</span></span>
6. <span data-ttu-id="0e316-133">**[全般]** タブで次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-133">On the **General** tab:</span></span>
   * <span data-ttu-id="0e316-134">**[テンプレート表示名]** にわかりやすい名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-134">Set **Template display name** to something meaningful to you.</span></span>

   > [!WARNING]
   > <span data-ttu-id="0e316-135">既定では、**[テンプレート名]** は **[テンプレート表示名]** (*スペースなし*) と同じです。</span><span class="sxs-lookup"><span data-stu-id="0e316-135">**Template name** by default is the same as **Template display name** with *no spaces*.</span></span> <span data-ttu-id="0e316-136">後で使用するために、テンプレート名をメモします。</span><span class="sxs-lookup"><span data-stu-id="0e316-136">Note the template name for later use.</span></span>

7. <span data-ttu-id="0e316-137">**[要求処理]** タブで **[プライベート キーのエクスポートを許可する]** ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0e316-137">On the **Request Handling** tab, check the **Allow private key to be exported** box.</span></span>
8. <span data-ttu-id="0e316-138">**[暗号化]** タブで、**[最小キー サイズ]** が 2048 に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e316-138">On the **Cryptography** tab, confirm that the **Minimum key size** is set to 2048.</span></span>
9. <span data-ttu-id="0e316-139">**[サブジェクト名]** タブで、**[要求に含まれる]** ラジオ ボタンをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0e316-139">On the **Subject Name** tab, choose the radio button **Supply in the request**.</span></span>
10. <span data-ttu-id="0e316-140">**[拡張子]** タブで、**[アプリケーション ポリシー]** に暗号化ファイル システム、セキュリティで保護された電子メール、および クライアント認証が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e316-140">On the **Extensions** tab, confirm that you see Encrypting File System, Secure Email, and Client Authentication under **Application Policies**.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="0e316-141">iOS および macOS の証明書テンプレートの場合、**[拡張]** タブで、**[キー使用法]** を編集し、**[署名は発行元の証明である]** がオンになっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e316-141">For iOS and macOS certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure that **Signature is proof of origin** is not selected.</span></span>

11. <span data-ttu-id="0e316-142">**[セキュリティ]** タブで、Microsoft Intune Certificate Connector をインストールするサーバーのコンピューター アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="0e316-142">On the **Security** tab, add the Computer Account for the server where you install the Microsoft Intune Certificate Connector.</span></span>
    * <span data-ttu-id="0e316-143">このアカウントに、**読み取り**と**登録**のアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0e316-143">Allow this account **Read** and **Enroll** permissions.</span></span>
12. <span data-ttu-id="0e316-144">**[適用]** をクリックし、**[OK]** をクリックして証明書テンプレートを保存します。</span><span class="sxs-lookup"><span data-stu-id="0e316-144">Click **Apply**, then click **OK** to save the certificate template.</span></span>
13. <span data-ttu-id="0e316-145">**証明書テンプレート コンソール**を閉じます。</span><span class="sxs-lookup"><span data-stu-id="0e316-145">Close the **Certificate Templates Console**.</span></span>
14. <span data-ttu-id="0e316-146">**[証明機関]** コンソールで **[証明書テンプレート]** を右クリックして **[新規作成]** をクリックし、**[発行する証明書テンプレート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e316-146">From the **Certification Authority** console, right-click **Certificate Templates**, **New**, **Certificate Template to Issue**.</span></span>
    * <span data-ttu-id="0e316-147">上記の手順で作成したテンプレートを選択して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e316-147">Choose the template that you created in the preceding steps and click **OK**.</span></span>
15. <span data-ttu-id="0e316-148">Intune に登録されたデバイスとユーザーに代わって証明書を管理するサーバーの場合、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0e316-148">For the server to manage certificates on behalf of Intune enrolled devices and users, follow these steps:</span></span>

    <span data-ttu-id="0e316-149">」を参照します。</span><span class="sxs-lookup"><span data-stu-id="0e316-149">a.</span></span> <span data-ttu-id="0e316-150">証明機関を右クリックして、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e316-150">Right-click the Certification Authority, choose **Properties**.</span></span>

    <span data-ttu-id="0e316-151">b.</span><span class="sxs-lookup"><span data-stu-id="0e316-151">b.</span></span> <span data-ttu-id="0e316-152">[セキュリティ] タブで、Microsoft Intune Certificate Connector を実行するサーバーのコンピューター アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="0e316-152">On the security tab, add the Computer account of the server where you run the Microsoft Intune Certificate Connector.</span></span>
      * <span data-ttu-id="0e316-153">このコンピューター アカウントに、**証明書の発行と管理**と**証明書の要求**のアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="0e316-153">Grant **Issue and Manage Certificates** and **Request Certificates** Allow permissions to the computer account.</span></span>
16. <span data-ttu-id="0e316-154">エンタープライズ CA からログアウトします。</span><span class="sxs-lookup"><span data-stu-id="0e316-154">Log out of the Enterprise CA.</span></span>

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a><span data-ttu-id="0e316-155">Microsoft Intune Certificate Connector のダウンロード、インストール、および構成</span><span class="sxs-lookup"><span data-stu-id="0e316-155">Download install and configure the Microsoft Intune Certificate Connector</span></span>

<span data-ttu-id="0e316-156">![ConnectorDownload][ConnectorDownload]</span><span class="sxs-lookup"><span data-stu-id="0e316-156">![ConnectorDownload][ConnectorDownload]</span></span>

1. <span data-ttu-id="0e316-157">Azure Portal で、**[その他のサービス]** > **[監視 + 管理]** > **[Intune]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0e316-157">In the Azure portal, select **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="0e316-158">**[Intune]** ブレードで、**[デバイス構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e316-158">On the **Intune** blade, select **Device Configuration**.</span></span> 
3. <span data-ttu-id="0e316-159">**[デバイス構成]** ブレードで **[証明機関]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e316-159">On the **Device Configuration** blade, select **Certification Authority**.</span></span> 
4. <span data-ttu-id="0e316-160">**[追加]** をクリックして、**[Download Connector file]\(コネクタ ファイルのダウンロード\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e316-160">Click **Add** and select **Download Connector file**.</span></span> <span data-ttu-id="0e316-161">インストールするサーバーからアクセスできる場所にダウンロードしたものを保存します。</span><span class="sxs-lookup"><span data-stu-id="0e316-161">Save the download to a location where you can access it from the server where you are going to install it.</span></span> 
5.  <span data-ttu-id="0e316-162">Microsoft Intune Certificate Connector をインストールするサーバーにログインします。</span><span class="sxs-lookup"><span data-stu-id="0e316-162">Log in to the server where you will install the Microsoft Intune Certificate Connector.</span></span>
6.  <span data-ttu-id="0e316-163">インストーラーを実行し、既定の場所を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0e316-163">Run the installer and accept the default location.</span></span> <span data-ttu-id="0e316-164">コネクタが C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0e316-164">It installs the connector to C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.</span></span>
    1. <span data-ttu-id="0e316-165">[インストーラー オプション] ページで、**[PFX 配布]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e316-165">On the Installer Options page chose **PFX Distribution** and click **Next**.</span></span>
    2. <span data-ttu-id="0e316-166">**[インストール]** をクリックして、インストールが完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="0e316-166">Click **Install** and wait for installation to complete.</span></span>
    3. <span data-ttu-id="0e316-167">[完了] ページで、**[Intune コネクタの起動]** のラベルの付いたボックスをオンにして、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e316-167">On the Completion page, check the box labeled **Launch Intune Connector** and click **Finish**.</span></span>
7.  <span data-ttu-id="0e316-168">[NDES コネクタ] ウィンドウが開いて、**[登録]** タブが表示されます。Intune への接続を有効にするには、**[サインイン]** をクリックして、管理アクセス許可を持つアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-168">The NDES Connector window should now open to the **Enrollment** tab. To enable the connection to Intune, click **Sign In** and provide an account with administrative permissions.</span></span>
8.  <span data-ttu-id="0e316-169">**[詳細設定]** タブで、**[Use this computer's SYSTEM account]\(このコンピューターのシステム アカウントを使用する\)** (既定値) ラジオ ボタンをオンのままにします。</span><span class="sxs-lookup"><span data-stu-id="0e316-169">On the **Advanced** tab, you can leave the radio button **Use this computer's SYSTEM account (default)** selected.</span></span>
9.  <span data-ttu-id="0e316-170">**[適用]** をクリックしてから、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e316-170">Click **Apply** then **Close**.</span></span>
10. <span data-ttu-id="0e316-171">Azure Portal に戻ります。</span><span class="sxs-lookup"><span data-stu-id="0e316-171">Now go back on the Azure portal.</span></span> <span data-ttu-id="0e316-172">数分後、**[Intune]** > **[デバイス構成]** > **[証明機関]** の **[接続の状態]** に、緑のチェック マークと **[アクティブ]** という語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e316-172">After a few minutes, you should see a green check mark and the word **Active** under **Connection status** in **Intune** > **Device Configuration** > **Certification Authority**.</span></span> <span data-ttu-id="0e316-173">これにより、コネクタ サーバーが Intune と通信できることが確認できます。</span><span class="sxs-lookup"><span data-stu-id="0e316-173">This confirmation lets you know that your connector server can communicate with Intune.</span></span>


## <a name="create-a-device-configuration-profile"></a><span data-ttu-id="0e316-174">デバイス構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="0e316-174">Create a device configuration profile</span></span>

1. <span data-ttu-id="0e316-175">[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0e316-175">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="0e316-176">**[Intune]**、**[デバイス構成]**、**[プロファイル]** と移動して、**[プロファイルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e316-176">Navigate to **Intune**, **Device configuration**, **Profiles**, and click **Create profile**.</span></span>

   <span data-ttu-id="0e316-177">![NavigateIntune][NavigateIntune]</span><span class="sxs-lookup"><span data-stu-id="0e316-177">![NavigateIntune][NavigateIntune]</span></span>

3. <span data-ttu-id="0e316-178">次の情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-178">Populate the following information:</span></span>
   * <span data-ttu-id="0e316-179">プロファイルの**名前**</span><span class="sxs-lookup"><span data-stu-id="0e316-179">**Name** for the profile</span></span>
   * <span data-ttu-id="0e316-180">オプションで説明を設定</span><span class="sxs-lookup"><span data-stu-id="0e316-180">Optionally set a description</span></span>
   * <span data-ttu-id="0e316-181">プロファイルをデプロイする**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0e316-181">**Platform** to deploy the profile to</span></span>
   * <span data-ttu-id="0e316-182">**[プロファイルの種類]** に**[信頼済み証明書]** を設定</span><span class="sxs-lookup"><span data-stu-id="0e316-182">Set **Profile type** to **Trusted certificate**</span></span>
4. <span data-ttu-id="0e316-183">**[設定]** に移動して、以前エクスポートした .cer ファイルのルート CA 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-183">Navigate to **Settings** and provide the .cer file Root CA Certificate exported previously.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0e316-184">**手順 3** で選択したプラットフォームに応じて、証明書の**保存先ストア**を選択するオプションが使用できる場合と使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e316-184">Depending on the Platform you chose in **Step 3** you may or may not have an option to choose the **Destination store** for the certificate.</span></span>

   <span data-ttu-id="0e316-185">![ProfileSettings][ProfileSettings]</span><span class="sxs-lookup"><span data-stu-id="0e316-185">![ProfileSettings][ProfileSettings]</span></span>

5. <span data-ttu-id="0e316-186">**[OK]** をクリックしてから **[作成]** をクリックし、プロファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0e316-186">Click **OK** then **Create** to save your profile.</span></span>
6. <span data-ttu-id="0e316-187">1 つ以上のデバイスに新しいプロファイルを割り当てる場合は、「[Microsoft Intune のデバイス プロファイルを割り当てる方法](device-profile-assign.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0e316-187">To assign the new profile to one or more devices see [How to assign Microsoft Intune device profiles](device-profile-assign.md).</span></span>

## <a name="create-a-pkcs-certificate-profile"></a><span data-ttu-id="0e316-188">PKCS 証明書プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="0e316-188">Create a PKCS Certificate profile</span></span>

1. <span data-ttu-id="0e316-189">[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0e316-189">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="0e316-190">**[Intune]**、**[デバイス構成]**、**[プロファイル]** と移動して、**[プロファイルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e316-190">Navigate to **Intune**, **Device configuration**, **Profiles**, and click **Create profile**.</span></span>
3. <span data-ttu-id="0e316-191">次の情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-191">Populate the following information:</span></span>
   * <span data-ttu-id="0e316-192">プロファイルの**名前**</span><span class="sxs-lookup"><span data-stu-id="0e316-192">**Name** for the profile</span></span>
   * <span data-ttu-id="0e316-193">オプションで説明を設定</span><span class="sxs-lookup"><span data-stu-id="0e316-193">Optionally set a description</span></span>
   * <span data-ttu-id="0e316-194">プロファイルをデプロイする**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0e316-194">**Platform** to deploy the profile to</span></span>
   * <span data-ttu-id="0e316-195">**[プロファイルの種類]** に **[PKCS 証明書]** を設定</span><span class="sxs-lookup"><span data-stu-id="0e316-195">Set **Profile type** to **PKCS Certificate**</span></span>
4. <span data-ttu-id="0e316-196">**[設定]** に移動して、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0e316-196">Navigate to **Settings** and provide the following information:</span></span>
   * <span data-ttu-id="0e316-197">**更新しきい値 (%)** - 推奨値は 20% です。</span><span class="sxs-lookup"><span data-stu-id="0e316-197">**Renewal threshold (%)** - Recommended is 20%.</span></span>
   * <span data-ttu-id="0e316-198">**証明書の有効期間** - 証明書テンプレートを変更していない場合には、このオプションには 1 年を設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-198">**Certificate validity period** - If you did not change the certificate template this option should be set to one year.</span></span>
   * <span data-ttu-id="0e316-199">**証明機関** - このオプションは、エンタープライズ CA の内部完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="0e316-199">**Certification authority** - This option is the internal fully qualified domain name (FQDN) of your Enterprise CA.</span></span>
   * <span data-ttu-id="0e316-200">**証明機関名** - このオプションは、エンタープライズ CA の名前で、前の項目とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e316-200">**Certification authority name** - This option is the name of your Enterprise CA and may be different than the previous item.</span></span>
   * <span data-ttu-id="0e316-201">**証明書テンプレート名** - このオプションは、先ほど作成したテンプレートの名前です。</span><span class="sxs-lookup"><span data-stu-id="0e316-201">**Certificate template name** - This option is the name of the template created earlier.</span></span> <span data-ttu-id="0e316-202">既定では、**[テンプレート名]** は **[テンプレート表示名]** (*スペースなし*) と同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0e316-202">Remember **Template name** by default is the same as **Template display name** with *no spaces*.</span></span>
   * <span data-ttu-id="0e316-203">**サブジェクト名の形式** - 特に指定がない限り、このオプションは**共通名**に設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-203">**Subject name format** - Set this option to **Common name** unless otherwise required.</span></span>
   * <span data-ttu-id="0e316-204">**サブジェクトの別名** - 特に指定がない限り、このオプションは**ユーザー プリンシパル名 (UPN)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="0e316-204">**Subject alternative name** - Set this option to **User principal name (UPN)** unless otherwise required.</span></span>
   * <span data-ttu-id="0e316-205">**拡張キー使用法** - 前のセクション「**証明機関で証明書テンプレートを構成する**」の手順 10 で既定の設定を使用している限り、選択ボックスから次の**定義済みの値**を追加します。</span><span class="sxs-lookup"><span data-stu-id="0e316-205">**Extended key usage** - As long as you used the default settings in Step 10 in the preceding section **Configure certificate templates on the certification authority**, add the following **Predefined values** from the selection box:</span></span>
      * <span data-ttu-id="0e316-206">**任意の目的**</span><span class="sxs-lookup"><span data-stu-id="0e316-206">**Any Purpose**</span></span>
      * <span data-ttu-id="0e316-207">**クライアント認証**</span><span class="sxs-lookup"><span data-stu-id="0e316-207">**Client Authentication**</span></span>
      * <span data-ttu-id="0e316-208">**セキュリティで保護された電子メール**</span><span class="sxs-lookup"><span data-stu-id="0e316-208">**Secure Email**</span></span>
   * <span data-ttu-id="0e316-209">**ルート証明書** - (Android プロファイル用) このオプションは、前のセクション「[エンタープライズ CA からルート証明書をエクスポートする](#export-the-root-certificate-from-the-enterprise-ca)」の手順 3 でエクスポートした .cer ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0e316-209">**Root Certificate** - (For Android Profiles) This option is the .cer file exported in Step 3 under the previous section [Export the root certificate from the Enterprise CA](#export-the-root-certificate-from-the-enterprise-ca).</span></span>

5. <span data-ttu-id="0e316-210">**[OK]** をクリックしてから **[作成]** をクリックし、プロファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0e316-210">Click **OK**, then click **Create** to save your profile.</span></span>
6. <span data-ttu-id="0e316-211">1 つ以上のデバイスに新しいプロファイルを割り当てる場合は、「[Microsoft Intune のデバイス プロファイルを割り当てる方法](device-profile-assign.md)」の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0e316-211">To assign the new profile to one or more devices, see the article [How to assign Microsoft Intune device profiles](device-profile-assign.md).</span></span>


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Azure Portal で Intune に移動して信頼された証明書用の新しいプロファイルを作成する"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "プロファイルを作成して信頼された証明書をアップロードする"
[ConnectorDownload]: ./media/certificates-download-connector.png "Azure Portal から Certificate Connector をダウンロードする"  
