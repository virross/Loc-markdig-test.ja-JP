---
title: "PC クライアント ソフトウェアをインストールする"
description: "このガイドは、Microsoft Intune クライアント ソフトウェアによって、Windows PC を管理させる場合に役立ちます。"
keywords: 
author: nathbarn
ms.author: nathbarn
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64c11e53-8d64-41b9-9550-4b4e395e8c52
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9316f78155b38f74765a353186a29dc90afce547
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="install-the-intune-software-client-on-windows-pcs"></a><span data-ttu-id="87d6f-103">Windows PC に Intune ソフトウェア クライアントをインストールする</span><span class="sxs-lookup"><span data-stu-id="87d6f-103">Install the Intune software client on Windows PCs</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="87d6f-104">Intune クライアント ソフトウェアをインストールして Windows PC を登録します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-104">Windows PCs can be enrolled by installing the Intune client software.</span></span> <span data-ttu-id="87d6f-105">Intune クライアント ソフトウェアは、次の方法を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-105">The Intune client software can be installed by using the following methods:</span></span>

- <span data-ttu-id="87d6f-106">IT 管理者の場合、次のうちいずれか 1 つの方法でインストール: 手動インストール、グループ ポリシーを使用したインストール、またはディスク イメージに含まれるインストール</span><span class="sxs-lookup"><span data-stu-id="87d6f-106">By the IT admin, using one of these methods: manual installation, Group Policy, or installation included in a disk image</span></span>

- <span data-ttu-id="87d6f-107">エンド ユーザーの場合: クライアント ソフトウェアを手動でインストール</span><span class="sxs-lookup"><span data-stu-id="87d6f-107">By end users, who manually install the client software</span></span>

<span data-ttu-id="87d6f-108">Intune クライアント ソフトウェアには、Intune 管理で PC を登録するために必要な最小限のソフトウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-108">The Intune client software contains the minimum software necessary to enroll the PC in Intune management.</span></span> <span data-ttu-id="87d6f-109">PC の登録後、Intune クライアント ソフトウェアは、PC の管理に必要な完全版クライアント ソフトウェアをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-109">After a PC has been enrolled, the Intune client software then downloads the full client software required for PC management.</span></span>

<span data-ttu-id="87d6f-110">このようにダウンロードを分割することで、ネットワークの帯域幅への影響が抑えられ、PC を Intune に最初に登録するのに要する時間が最短になります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-110">This series of downloads reduces the impact on the network's bandwidth and minimizes the time required to initially enroll the PC in Intune.</span></span> <span data-ttu-id="87d6f-111">また、2 回目のダウンロードが完了した後、クライアントで最新のソフトウェアが利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-111">It also ensures that the client has the most recent software available after the second download has finished.</span></span>

<span data-ttu-id="87d6f-112">1 つの Intune ライセンスで、最大 5 台の PC に Intune クライアント ソフトウェアをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-112">One Intune license allows the installation of the Intune client software on up to five PCs.</span></span>

## <a name="download-the-intune-client-software"></a><span data-ttu-id="87d6f-113">Intune クライアント ソフトウェアのダウンロード</span><span class="sxs-lookup"><span data-stu-id="87d6f-113">Download the Intune client software</span></span>

<span data-ttu-id="87d6f-114">ユーザー自身が Intune クライアント ソフトウェアをインストールする場合を除き、すべての方法で、IT 管理者が初めにソフトウェアをダウンロードし、その後エンド ユーザーに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-114">All methods, except those in which users install the Intune client software themselves, require that IT admins download the software first so that it can be subsequently deployed to end users.</span></span>

1.  <span data-ttu-id="87d6f-115">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[管理]** &gt; **[クライアント ソフトウェアのダウンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-115">In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Client Software Download**.</span></span>

  ![Intune PC クライアントのダウンロード](../media/pc-sa-client-download.png)

2. <span data-ttu-id="87d6f-117">**[クライアント ソフトウェアのダウンロード]** ページで、**[クライアント ソフトウェアのダウンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-117">On the **Client Software Download** page, click **Download Client Software**.</span></span> <span data-ttu-id="87d6f-118">ソフトウェアが含まれている **Microsoft_Intune_Setup.zip** パッケージをネットワーク上のセキュリティで保護された場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-118">Then save the **Microsoft_Intune_Setup.zip** package that contains the software to a secure location on your network.</span></span>

  <span data-ttu-id="87d6f-119">Intune クライアント ソフトウェアのインストール パッケージにはお客様のアカウントに固有の情報が含まれており、これらの情報は埋め込み証明書に記載されています。</span><span class="sxs-lookup"><span data-stu-id="87d6f-119">The Intune client software installation package contains unique and specific information, which is available through an embedded certificate, about your account.</span></span> <span data-ttu-id="87d6f-120">許可されていないユーザーがインストール パッケージにアクセスした場合は、埋め込み証明書に示されているアカウントに PC を登録できることになり、会社のリソースへのアクセスが行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-120">If unauthorized users gain access to the installation package, they can enroll PCs to the account that is represented by its embedded certificate and might gain access to company resources.</span></span>

3. <span data-ttu-id="87d6f-121">インストール パッケージの内容をネットワーク上の安全な場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-121">Extract the contents of the installation package to the secure location on your network.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="87d6f-122">抽出した **ACCOUNTCERT** ファイルを削除したり、名前を変更したりすると、クライアント ソフトウェアをインストールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-122">Do not rename or remove the **ACCOUNTCERT** file that is extracted, or the client software installation will fail.</span></span>

## <a name="deploy-the-client-software-manually"></a><span data-ttu-id="87d6f-123">クライアント ソフトウェアを手動で展開する</span><span class="sxs-lookup"><span data-stu-id="87d6f-123">Deploy the client software manually</span></span>

<span data-ttu-id="87d6f-124">クライアント ソフトウェアをインストールするコンピューターで、クライアント ソフトウェアのインストール ファイルが存在するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-124">On the computer(s) on which the client software is going to be installed, go to the folder where the client software installation files are located.</span></span> <span data-ttu-id="87d6f-125">**Microsoft_Intune_Setup.exe** を実行して、クライアント ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-125">Then run **Microsoft_Intune_Setup.exe** to install the client software.</span></span>

> [!NOTE]
> <span data-ttu-id="87d6f-126">クライアント PC のタスク バーに表示されるアイコンにマウスをポイントすると、インストールの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-126">The status of the installation is displayed when you hover over the icon in the taskbar on the client PC.</span></span>

## <a name="deploy-the-client-software-by-using-group-policy"></a><span data-ttu-id="87d6f-127">グループ ポリシーを使ってクライアント ソフトウェアを展開する</span><span class="sxs-lookup"><span data-stu-id="87d6f-127">Deploy the client software by using Group Policy</span></span>

1.  <span data-ttu-id="87d6f-128">**Microsoft_Intune_Setup.exe** と **MicrosoftIntune.accountcert** というファイルを含むフォルダーで、次のコマンドを実行して、32 ビットおよび 64 ビット コンピューター用の Windows インストーラーベースのインストール プログラムを抽出します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-128">In the folder that contains the files **Microsoft_Intune_Setup.exe** and **MicrosoftIntune.accountcert**, run the following command to extract the Windows Installer-based installation programs for 32-bit and 64-bit computers:</span></span>

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  <span data-ttu-id="87d6f-129">**Microsoft_Intune_x86.msi** ファイル、**Microsoft_Intune_x64.msi** ファイル、および **MicrosoftIntune.accountcert** ファイルを、クライアント ソフトウェアをインストールする予定のすべてのコンピューターからアクセスできるネットワーク上の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-129">Copy the **Microsoft_Intune_x86.msi** file, the **Microsoft_Intune_x64.msi** file, and the **MicrosoftIntune.accountcert** file to a network location that can be accessed by all computers on which the client software is going to be installed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="87d6f-130">ファイルの名前を変更すると、クライアント ソフトウェアをインストールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-130">Do not separate or rename the files or the client software installation will fail.</span></span>

3.  <span data-ttu-id="87d6f-131">グループ ポリシーを使用して、ネットワーク上のコンピューターにソフトウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-131">Use Group Policy to deploy the software to computers on your network.</span></span>

    <span data-ttu-id="87d6f-132">グループ ポリシーを使用してソフトウェアを自動的に展開する方法の詳細については、「[初心者向けのグループ ポリシー](https://technet.microsoft.com/library/hh147307.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87d6f-132">For more information about how to use Group Policy to automatically deploy software, see [Group Policy for Beginners](https://technet.microsoft.com/library/hh147307.aspx).</span></span>

## <a name="deploy-the-client-software-as-part-of-an-image"></a><span data-ttu-id="87d6f-133">システム イメージの一部としてクライアント ソフトウェアを展開する</span><span class="sxs-lookup"><span data-stu-id="87d6f-133">Deploy the client software as part of an image</span></span>
<span data-ttu-id="87d6f-134">Intune クライアント ソフトウェアは、次の手順に従って、オペレーティング システム イメージの一部としてコンピューターに展開できます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-134">You can deploy the Intune client software to computers as part of an operating system image by using the following procedure as a guide:</span></span>

1.  <span data-ttu-id="87d6f-135">クライアント インストール ファイルの **Microsoft_Intune_Setup.exe** と **MicrosoftIntune.accountcert** を、基準コンピューターの **%Systemdrive%\Temp\Microsoft_Intune_Setup** フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-135">Copy the client installation files, **Microsoft_Intune_Setup.exe** and **MicrosoftIntune.accountcert**, to the **%Systemdrive%\Temp\Microsoft_Intune_Setup** folder on the reference computer.</span></span>

2.  <span data-ttu-id="87d6f-136">次のコマンドを **SetupComplete.cmd** スクリプトに追加して、 **WindowsIntuneEnrollPending** レジストリのエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-136">Create the **WindowsIntuneEnrollPending** registry entry by adding the following command to the **SetupComplete.cmd** script:</span></span>

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  <span data-ttu-id="87d6f-137">**setupcomplete.cmd** に次のコマンドを追加して、/PrepareEnroll コマンド ライン引数を使用して登録パッケージが実行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-137">Add the following command to **setupcomplete.cmd** to run the enrollment package with the /PrepareEnroll command-line argument:</span></span>

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > <span data-ttu-id="87d6f-138">**SetupComplete.cmd** スクリプトを使用すると、ユーザーがサインオンする前に、Windows セットアップによってシステムを変更できます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-138">The **SetupComplete.cmd** script enables Windows Setup to make modifications to the system before a user signs on.</span></span> <span data-ttu-id="87d6f-139">**/PrepareEnroll** というコマンド ライン引数は、Windows セットアップの実行後に、対象のコンピューターが Intune に自動的に登録されるようにする引数です。</span><span class="sxs-lookup"><span data-stu-id="87d6f-139">The **/PrepareEnroll** command-line argument prepares a targeted computer to be automatically enrolled in Intune after Windows Setup finishes.</span></span>

4.  <span data-ttu-id="87d6f-140">**SetupComplete.cmd** を、基準コンピューターの **%Windir%\Setup\Scripts** フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-140">Put **SetupComplete.cmd** in the **%Windir%\Setup\Scripts** folder on the reference computer.</span></span>

5.  <span data-ttu-id="87d6f-141">基準コンピューターのイメージをキャプチャして、対象のコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-141">Capture an image of the reference computer and then deploy this to targeted computers.</span></span>

    <span data-ttu-id="87d6f-142">対象のコンピューターで Windows セットアップの実行が完了し、コンピューターが再起動すると、 **WindowsIntuneEnrollPending** レジストリ キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-142">When the targeted computer restarts at the completion of Windows Setup, the **WindowsIntuneEnrollPending** registry key is created.</span></span> <span data-ttu-id="87d6f-143">登録パッケージによって、コンピューターが登録されたかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-143">The enrollment package checks to see if the computer is enrolled.</span></span> <span data-ttu-id="87d6f-144">登録されている場合は、何も行われません。</span><span class="sxs-lookup"><span data-stu-id="87d6f-144">If the computer is enrolled, no further action is taken.</span></span> <span data-ttu-id="87d6f-145">登録されていない場合は、Microsoft Intune への自動登録タスクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-145">If the computer is not enrolled, the enrollment package creates a Microsoft Intune Automatic Enrollment Task.</span></span>

    <span data-ttu-id="87d6f-146">スケジュールに従って、次回の自動登録タスクが実行されると、 **indowsIntuneEnrollPending** レジストリ値が存在するかどうかがチェックされ、対象の PC が Intune に登録されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-146">When the automatic enrollment task runs at the next scheduled time, it checks the existence of the **WindowsIntuneEnrollPending** registry value, and it tries to enroll the targeted PC in Intune.</span></span> <span data-ttu-id="87d6f-147">登録できなかった場合は、このタスクが次回実行されるときに登録されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-147">If the enrollment fails for any reason, the enrollment is retried the next time the task runs.</span></span> <span data-ttu-id="87d6f-148">再試行は 1 か月間継続されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-148">The retries continue for a month.</span></span>

    <span data-ttu-id="87d6f-149">登録が正常に完了するか、1 か月後に (どちらか早い方)、対象のコンピューターから Intune への自動登録タスク、**WindowsIntuneEnrollPending** レジストリ値、およびアカウント証明書が削除されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-149">The Intune Automatic Enrollment Task, the **WindowsIntuneEnrollPending** registry value, and the account certificate are deleted from the targeted computer either when the enrollment is successful or after a month (whichever comes first).</span></span>

## <a name="instruct-users-to-self-enroll"></a><span data-ttu-id="87d6f-150">自分で登録するユーザーへの指示</span><span class="sxs-lookup"><span data-stu-id="87d6f-150">Instruct users to self-enroll</span></span>

<span data-ttu-id="87d6f-151">ユーザーは、[ポータル Web サイト](https://portal.manage.microsoft.com)に移動して、Intune クライアント ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-151">Users install the Intune client software by going to the [Company Portal website](https://portal.manage.microsoft.com).</span></span> <span data-ttu-id="87d6f-152">Web ポータルでユーザーに対して実際に表示される情報は、アカウントの MDM 機関およびユーザーの PC の OS プラットフォーム/バージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-152">The exact information that users see in the web portal varies, depending on your account's MDM Authority and the OS platform/version of the user's PC.</span></span>

<span data-ttu-id="87d6f-153">ユーザーに Intune ライセンスが割り当てられていない場合や、組織の MDM 機関が Intune に設定されていない場合、ユーザーには登録するためのオプションが表示されません。</span><span class="sxs-lookup"><span data-stu-id="87d6f-153">If users haven't been assigned an Intune license or if the organization's MDM Authority hasn't been set to Intune, users aren't shown any options to enroll.</span></span>

<span data-ttu-id="87d6f-154">ユーザーに Intune ライセンスが割り当てられており、組織の MDM 機関が Intune に設定されている場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-154">If users have been assigned an Intune license, and the organization's MDM Authority has been set to Intune:</span></span>

- <span data-ttu-id="87d6f-155">Windows 7 または Windows 8 PC のユーザーには、組織に一意の PC クライアント ソフトウェアをダウンロードし、インストールして Intune に登録するオプションのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-155">Windows 7 or Windows 8 PC users are shown ONLY the option to enroll to Intune by downloading and installing the PC client software that is unique to their organization.</span></span>

- <span data-ttu-id="87d6f-156">Windows 10 または Windows 8.1 PC のユーザーには、次の 2 つの登録オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-156">Windows 10 or Windows 8.1 PC users are shown two enrollment options:</span></span>

  -  <span data-ttu-id="87d6f-157">**PC をモバイル デバイスとして登録**: ユーザーは **[登録方法を表示]** ボタンを選択します。そうすると、PC をモバイル デバイスとして登録する方法の手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-157">**Enroll PC as a mobile device**: Users choose the **Find Out How to Enroll** button and are taken to instructions on how to enroll their PC as a mobile device.</span></span> <span data-ttu-id="87d6f-158">MDM 登録は既定の推奨登録オプションと見なされるため、このボタンは目立つように表示されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-158">This button is prominently displayed, because MDM enrollment is considered to be the default and preferred enrollment option.</span></span> <span data-ttu-id="87d6f-159">ただし、ここでは MDM オプションは適用されません。クライアント ソフトウェア インストールについてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-159">However, the MDM option is not applicable to this topic, which covers only the client software installation.</span></span>
  - <span data-ttu-id="87d6f-160">**Intune クライアント ソフトウェアを使用して PC を登録**: ユーザーに **[ダウンロードするには、ここをクリックします]** のリンクを選択するように指示する必要があります。ユーザーは、このリンクを選択してクライアント ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-160">**Enroll PC using the Intune client software**: You'll need to tell your users to select the **Click here to download it** link, which takes them through the client software installation.</span></span>

<span data-ttu-id="87d6f-161">次の表に、オプションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-161">The following table summarizes the options.</span></span>

  ![プラットフォームごとの既定の登録オプション](../media/default-enrollment-options-table.png)

<span data-ttu-id="87d6f-163">次のスクリーンショットは、ソフトウェア クライアントを使用してデバイスを登録する場合に、ユーザーに表示される内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="87d6f-163">The following screenshots show what users see as they enroll their devices using the software client.</span></span>

<span data-ttu-id="87d6f-164">最初に、デバイスを特定または登録するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-164">Users are first prompted to identify or to enroll their device.</span></span>

  ![デバイスの特定または登録](../media/identify-device-or-enroll.png)

<span data-ttu-id="87d6f-166">ユーザーに PC クライアント ソフトウェアをインストールさせるには、**[ダウンロードするには、ここをクリックします]** リンクを選択するように指示する必要があります。このリンクを選択すると、ユーザーは PC クライアント ソフトウェアをダウンロードできます。その際に、インストール プロセスが示されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-166">To have your users install the PC client software, you'll need to tell them to select the **Click here to download it** link, which enables users to download the PC client software and takes them through the installation process.</span></span> <span data-ttu-id="87d6f-167">**[登録方法を表示]** ボタンをクリックすると、MDM 登録を使用する登録方法に関するドキュメントが表示されます。これは、ソフトウェア クライアントの手順とは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="87d6f-167">The **Find out how to enroll** button takes users to documentation about how to enroll using MDM enrollment, which is not relevant to these software client instructions.</span></span>

  ![[ダウンロードするには、ここをクリックします] リンクの選択](../media/enroll-your-windows-device.png)

<span data-ttu-id="87d6f-169">ユーザーがリンクをクリックすると、**[ソフトウェアのダウンロード]** ボタンが表示されます。これを選択して、PC クライアント ソフトウェアのインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-169">When users click the link, they see a **Download Software** button, which they select to start the PC client software installation.</span></span>

  ![[ソフトウェアのダウンロード] ボタンの選択](../media/download-pc-client-software.png)

<span data-ttu-id="87d6f-171">その後、会社の資格情報を使用してサインインするよう求められます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-171">Users are then asked to sign in with their corporate credentials.</span></span>

  ![資格情報を使用してサインイン](../media/sign-in-to-intune.png)

<span data-ttu-id="87d6f-173">インストールのウェルカム ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-173">Users are taken to the Welcome page for the installation.</span></span>

  ![PC クライアント インストールのウェルカム ページ](../media/welcome-to-pc-agent-install-wizard.png)

<span data-ttu-id="87d6f-175">**[次へ]** を選択すると、インストールが開始されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-175">Users choose **Next**, and the installation starts.</span></span>

  ![PC クライアント インストールのウェルカム ページ](../media/welcome-to-pc-agent-install-wizard.png)

<span data-ttu-id="87d6f-177">インストールが完了したら、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-177">When the installation completes, users choose **Finish**.</span></span>

  ![PC クライアント インストールの完了](../media/completed-the-setup-wizard.png)

<span data-ttu-id="87d6f-179">Intune PC クライアント ソフトウェアを使用して既に登録されている PC をモバイル デバイスとして登録しようとすると、次のエラー画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-179">If users try to enroll their PC as a mobile device after having already enrolled using the Intune PC client software, they see the following error screen.</span></span>

  ![PC が既に登録されている場合に表示される画面](../media/page-shown-if-pc-already-enrolled.png)

## <a name="monitor-and-validate-successful-client-deployment"></a><span data-ttu-id="87d6f-181">クライアントの正常展開の監視と確認</span><span class="sxs-lookup"><span data-stu-id="87d6f-181">Monitor and validate successful client deployment</span></span>
<span data-ttu-id="87d6f-182">次のいずれかの手順を使用して、クライアントの正常展開を監視および確認できます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-182">Use one of the following procedures to help you monitor and validate successful client deployment.</span></span>

### <a name="to-verify-the-installation-of-the-client-software-from-the-microsoft-intune-administrator-console"></a><span data-ttu-id="87d6f-183">Microsoft Intune 管理コンソールでクライアント ソフトウェアのインストールを確認するには</span><span class="sxs-lookup"><span data-stu-id="87d6f-183">To verify the installation of the client software from the Microsoft Intune administrator console</span></span>

1.  <span data-ttu-id="87d6f-184">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[グループ]** &gt; **[すべてのデバイス]** &gt; **[すべてのコンピューター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-184">In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** &gt; **All Computers**.</span></span>

2.  <span data-ttu-id="87d6f-185">一覧内で、Intune と通信しているコンピューターを見つけるか、または、**[デバイスの検索]** ボックスにコンピューターの名前 (または名前の一部) を入力して、特定の管理対象コンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-185">In the list, find the computers that are communicating with Intune, or search for a specific managed computer by typing the computer name (or any part of the name) in the **Search devices** box.</span></span>

3.  <span data-ttu-id="87d6f-186">コンソールの下部ウィンドウに表示されるコンピューターの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-186">Examine the status of the computer in the bottom pane of the console.</span></span> <span data-ttu-id="87d6f-187">エラーがあれば解決します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-187">Resolve any errors.</span></span>

### <a name="to-create-a-computer-inventory-report-to-display-all-enrolled-computers"></a><span data-ttu-id="87d6f-188">登録されているすべてのコンピューターを表示する、コンピューターのインベントリ レポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="87d6f-188">To create a computer inventory report to display all enrolled computers</span></span>

1.  <span data-ttu-id="87d6f-189">[Microsoft Intune 管理コンソール](https://manage.microsoft.com/)で、**[レポート]** &gt; **[コンピューター インベントリ レポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-189">In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Reports** &gt; **Computer Inventory Reports**.</span></span>

2.  <span data-ttu-id="87d6f-190">**[新しいレポートの作成]** ページで、(フィルターを適用しない場合は) すべてのフィールドを既定値のままにして、**[レポートの表示]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87d6f-190">On the **Create New Report** page, leave the default values in all fields (unless you want to apply filters), and then click **View Report**.</span></span>

3.  <span data-ttu-id="87d6f-191">新しいウィンドウで **[コンピューター インベントリ レポート]** ページが開き、Intune に登録されているすべてのコンピューターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-191">The **Computer Inventory Report** page opens in a new window that displays all computers that are successfully enrolled in Intune.</span></span>

    > [!TIP]
    > <span data-ttu-id="87d6f-192">レポートの列見出しをクリックすると、列の内容で一覧が並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-192">Click any column heading in the report to sort the list by the contents of that column.</span></span>

## <a name="uninstall-the-windows-client-software"></a><span data-ttu-id="87d6f-193">Windows クライアント ソフトウェアをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="87d6f-193">Uninstall the Windows client software</span></span>

<span data-ttu-id="87d6f-194">Windows クライアント ソフトウェアは 2 通りの方法で登録解除できます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-194">There are two ways to unenroll the Windows client software:</span></span>

- <span data-ttu-id="87d6f-195">Intune 管理コンソールから (推奨される方法)</span><span class="sxs-lookup"><span data-stu-id="87d6f-195">From the Intune admin console (recommended method)</span></span>
- <span data-ttu-id="87d6f-196">クライアントのコマンド プロンプトから</span><span class="sxs-lookup"><span data-stu-id="87d6f-196">From a command prompt on the client</span></span>

### <a name="unenroll-by-using-the-intune-admin-console"></a><span data-ttu-id="87d6f-197">Intune 管理コンソールを使用して登録解除する</span><span class="sxs-lookup"><span data-stu-id="87d6f-197">Unenroll by using the Intune admin console</span></span>

<span data-ttu-id="87d6f-198">Intune 管理コンソールを使用してソフトウェア クライアントの登録を解除するには、**[グループ]**、**[すべてのコンピューター]**、**[デバイス]** の順に進みます。</span><span class="sxs-lookup"><span data-stu-id="87d6f-198">To unenroll the software client by using the Intune admin console, go to **Groups** > **All Computers** > **Devices**.</span></span> <span data-ttu-id="87d6f-199">クライアントを右クリックし、**[インベントリからの削除/ワイプ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-199">Right-click the client, and select **Retire/Wipe**.</span></span>

### <a name="unenroll-by-using-a-command-prompt-on-the-client"></a><span data-ttu-id="87d6f-200">クライアントでコマンド プロンプトを使用して登録解除する</span><span class="sxs-lookup"><span data-stu-id="87d6f-200">Unenroll by using a command prompt on the client</span></span>

<span data-ttu-id="87d6f-201">管理者特権のコマンド プロンプトで、次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-201">Using an elevated command prompt, run one of the following commands.</span></span>

<span data-ttu-id="87d6f-202">**方法 1**:</span><span class="sxs-lookup"><span data-stu-id="87d6f-202">**Method 1**:</span></span>

    "C:\Program Files\Microsoft\OnlineManagement\Common\ProvisioningUtil.exe" /UninstallAgents /MicrosoftIntune

<span data-ttu-id="87d6f-203">**方法 2**</span><span class="sxs-lookup"><span data-stu-id="87d6f-203">**Method 2**</span></span><br><span data-ttu-id="87d6f-204">Windows のすべての SKU でこれらのエージェントがすべてインストールされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="87d6f-204">Note that all of these agents are installed on every SKU of Windows:</span></span>

    wmic product where name="Microsoft Endpoint Protection Management Components" call uninstall<br>
    wmic product where name="Microsoft Intune Notification Service" call uninstall<br>
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall<br>
    wmic product where name="Microsoft Online Management Policy Agent" call uninstall<br>
    wmic product where name="Microsoft Policy Platform" call uninstall<br>
    wmic product where name="Microsoft Security Client" call uninstall<br>
    wmic product where name="Microsoft Online Management Client" call uninstall<br>
    wmic product where name="Microsoft Online Management Client Service" call uninstall<br>
    wmic product where name="Microsoft Easy Assist v2" call uninstall<br>
    wmic product where name="Microsoft Intune Monitoring Agent" call uninstall<br>
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall<br>
    wmic product where name="Windows Firewall Configuration Provider" call uninstall<br>
    wmic product where name="Microsoft Intune Center" call uninstall<br>
    wmic product where name="Microsoft Online Management Update Manager" call uninstall<br>
    wmic product where name="Microsoft Online Management Agent Installer" call uninstall<br>
    wmic product where name="Microsoft Intune" call uninstall<br>
    wmic product where name="Windows Endpoint Protection Management Components" call uninstall<br>
    wmic product where name="Windows Intune Notification Service" call uninstall<br>
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall<br>
    wmic product where name="Windows Online Management Policy Agent" call uninstall<br>
    wmic product where name="Windows Policy Platform" call uninstall<br>
    wmic product where name="Windows Security Client" call uninstall<br>
    wmic product where name="Windows Online Management Client" call uninstall<br>
    wmic product where name="Windows Online Management Client Service" call uninstall<br>
    wmic product where name="Windows Easy Assist v2" call uninstall<br>
    wmic product where name="Windows Intune Monitoring Agent" call uninstall<br>
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall<br>
    wmic product where name="Windows Firewall Configuration Provider" call uninstall<br>
    wmic product where name="Windows Intune Center" call uninstall<br>
    wmic product where name="Windows Online Management Update Manager" call uninstall<br>
    wmic product where name="Windows Online Management Agent Installer" call uninstall<br>
    wmic product where name="Windows Intune" call uninstall

> [!TIP]
> <span data-ttu-id="87d6f-205">クライアントの登録を解除すると、関連するクライアントの無効になったサーバー側レコードが残ります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-205">Client unenrollment will leave a stale sever-side record for the affected client.</span></span> <span data-ttu-id="87d6f-206">登録解除プロセスは非同期です。9 つのエージェントをアンインストールする場合、完了に最大 30 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-206">The unenrollment process is asynchronous, and there are nine agents to uninstall, so it may take up to 30 mins to complete.</span></span>

### <a name="check-the-unenrollment-status"></a><span data-ttu-id="87d6f-207">登録解除状態を確認する</span><span class="sxs-lookup"><span data-stu-id="87d6f-207">Check the unenrollment status</span></span>

<span data-ttu-id="87d6f-208">"%ProgramFiles%\Microsoft\OnlineManagement" を確認し、次のディレクトリのみが左に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-208">Check "%ProgramFiles%\Microsoft\OnlineManagement" and ensure that only the following directories are shown on the left:</span></span>

- <span data-ttu-id="87d6f-209">AgentInstaller</span><span class="sxs-lookup"><span data-stu-id="87d6f-209">AgentInstaller</span></span>
- <span data-ttu-id="87d6f-210">ログ</span><span class="sxs-lookup"><span data-stu-id="87d6f-210">Logs</span></span>
- <span data-ttu-id="87d6f-211">Updates</span><span class="sxs-lookup"><span data-stu-id="87d6f-211">Updates</span></span>
- <span data-ttu-id="87d6f-212">共通</span><span class="sxs-lookup"><span data-stu-id="87d6f-212">Common</span></span>

### <a name="remove-the-onlinemanagement-folder"></a><span data-ttu-id="87d6f-213">OnlineManagement フォルダーを削除する</span><span class="sxs-lookup"><span data-stu-id="87d6f-213">Remove the OnlineManagement folder</span></span>

<span data-ttu-id="87d6f-214">登録解除プロセスでは、OnlineManagement フォルダーが削除されません。</span><span class="sxs-lookup"><span data-stu-id="87d6f-214">The unenrollment process does not remove the OnlineManagement folder.</span></span> <span data-ttu-id="87d6f-215">アンインストール後、30 分待ち、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-215">Wait 30 minutes after the uninstall, and then run this command.</span></span> <span data-ttu-id="87d6f-216">30 分待たずに実行した場合、アンインストールの状態がわからなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="87d6f-216">If you run it too soon, the uninstall could be left in an unknown state.</span></span> <span data-ttu-id="87d6f-217">フォルダーを削除するには、プロンプトを管理者特権で開き、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="87d6f-217">To remove the folder, start an elevated prompt and run:</span></span>

    "rd /s /q %ProgramFiles%\Microsoft\OnlineManagement".

### <a name="next-steps"></a><span data-ttu-id="87d6f-218">次のステップ</span><span class="sxs-lookup"><span data-stu-id="87d6f-218">Next steps</span></span>
<span data-ttu-id="87d6f-219">[Microsoft Intune を使用して Windows PC を管理する](manage-windows-pcs-with-microsoft-intune.md)
[Microsoft Intune でのクライアント セットアップのトラブルシューティング](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="87d6f-219">[Manage Windows PCs with Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)
[Troubleshoot client setup](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)</span></span>
