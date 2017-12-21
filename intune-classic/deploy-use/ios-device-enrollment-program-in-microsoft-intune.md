---
title: "iOS デバイスの Apple DEP 管理"
description: "Apple デバイスを管理するために、iOS Device Enrollment Program (DEP) を通じて購入した iOS デバイスを登録する登録プロファイルを \"無線\" で展開します。"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0a990e1214cb5822ebead6b3e8ccd852d0ad2b14
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-corporate-owned-device-enrollment-program-ios-devices"></a><span data-ttu-id="e2b4a-103">会社所有のデバイス登録プログラムによる iOS デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="e2b4a-103">Enroll corporate-owned Device Enrollment Program iOS devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e2b4a-104">Microsoft Intune は、"無線" で Device Enrollment Program (DEP) を通じて購入した iOS デバイスを登録する登録プロファイルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-104">Microsoft Intune can deploy an enrollment profile that enrolls iOS devices that were bought through the Device Enrollment Program (DEP) “over the air.”</span></span> <span data-ttu-id="e2b4a-105">登録パッケージには、デバイスのセットアップ アシスタント オプションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-105">The enrollment package can include setup assistant options for the device.</span></span>

>[!NOTE]
><span data-ttu-id="e2b4a-106">DEP 登録は、[デバイス登録マネージャー](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)の方法と同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-106">DEP enrollment can't be used with the [device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) method.</span></span>
><span data-ttu-id="e2b4a-107">また、ユーザーがポータル サイト アプリなどを使用して iOS デバイスを登録し、デバイスのシリアル番号がインポートされて DEP プロファイルが割り当てられると、このデバイスは Intune から登録が解除されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-107">Also, if users enroll iOS devices (i.e. using the Company Portal app) and those devices' serial numbers are then imported and assigned a DEP profile, the device will be unenrolled from Intune.</span></span>

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-dep-management"></a><span data-ttu-id="e2b4a-108">Apple DEP 管理を使用して iOS デバイスを登録する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="e2b4a-108">Prerequisites for enrolling iOS devices by using Apple DEP management</span></span>

- [<span data-ttu-id="e2b4a-109">APNs 証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="e2b4a-109">Install an APNs certificate</span></span>](set-up-ios-and-mac-management-with-microsoft-intune.md)

- <span data-ttu-id="e2b4a-110">組織は Apple DEP に参加し、そのプログラムでデバイスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-110">Your organization must join Apple DEP and get devices through that program.</span></span> <span data-ttu-id="e2b4a-111">そのプロセスの詳細については、  [https://deploy.apple.com](https://deploy.apple.com)を参照してください。このプログラムの利点には、各デバイスをコンピューターに USB ケーブルを使用して接続することなく、デバイスを楽に設定できる点があります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-111">Details of that process are available at:  [https://deploy.apple.com](https://deploy.apple.com). Advantages of the program include hands-free setup of devices without using a USB cable to connect each device to a computer.</span></span>

- <span data-ttu-id="e2b4a-112">DEP に企業所有の iOS デバイスを登録するには、Apple の DEP トークンが必要です。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-112">Before you can enroll corporate-owned iOS devices with DEP, you need a DEP token from Apple.</span></span> <span data-ttu-id="e2b4a-113">このトークンにより、Intune は企業所有の DEP 参加デバイスに関する情報を同期できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-113">This token lets Intune sync information about DEP-participating devices that your corporation owns.</span></span> <span data-ttu-id="e2b4a-114">また、Intune は Apple への登録プロファイルのアップロードを実行して、デバイスをそれらのプロファイルに割り当てられるようになります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-114">It also permits Intune to perform Enrollment Profile uploads to Apple and to assign devices to those profiles.</span></span>

## <a name="steps-to-enroll-ios-devices-by-using-apple-dep-management"></a><span data-ttu-id="e2b4a-115">Apple DEP 管理を使用して iOS デバイスを登録する手順</span><span class="sxs-lookup"><span data-stu-id="e2b4a-115">Steps to enroll iOS devices by using Apple DEP management</span></span>

<span data-ttu-id="e2b4a-116">次の手順では、Apple DEP 管理を使用して iOS デバイスを登録するための準備方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-116">The following steps explain how to enroll iOS devices on "day 0" by using Apple DEP management.</span></span> <span data-ttu-id="e2b4a-117">組織でデバイスが追加および削除された場合、以下に示すように、シリアル番号の追加や削除など、いくつかの手順を繰り返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-117">As devices are added and removed from your organization, you will likely repeat some of these steps, such as adding or removing serial numbers, as described below.</span></span>

### <a name="get-an-encryption-key"></a><span data-ttu-id="e2b4a-118">暗号化キーを取得する</span><span class="sxs-lookup"><span data-stu-id="e2b4a-118">Get an Encryption Key</span></span>

1. <span data-ttu-id="e2b4a-119">管理者ユーザーとして、[Microsoft Intune の管理コンソール](https://manage.microsoft.com)を開き、**[管理]** &gt; **[モバイル デバイス管理]** &gt; **[iOS]** &gt; **[デバイス登録プログラム]** の順に移動して、**[暗号化キーのダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-119">As an administrative user, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Admin** &gt; **Mobile Device Management** &gt; **iOS** &gt; **Device Enrollment Program**, and then choose **Download Encryption Key**.</span></span>

2. <span data-ttu-id="e2b4a-120">暗号化キー (.pem) ファイルをローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-120">Save the encryption key (.pem) file locally.</span></span> <span data-ttu-id="e2b4a-121">.pem ファイルは、Apple Device Enrollment Program ポータルから信頼関係証明書を要求するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-121">The .pem file is used to request a trust-relationship certificate from the Apple Device Enrollment Program portal.</span></span>

![Device Enrollment Program のトークンの更新](../media/dev-sa-ios-dep.png)

### <a name="get-a-device-enrollment-program-token"></a><span data-ttu-id="e2b4a-123">Device Enrollment Program のトークンを取得する</span><span class="sxs-lookup"><span data-stu-id="e2b4a-123">Get a Device Enrollment Program token</span></span>

1. <span data-ttu-id="e2b4a-124">[Device Enrollment Program ポータル](https://deploy.apple.com) (https://deploy.apple.com) に移動し、会社の Apple ID でサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-124">Go to the [Device Enrollment Program Portal](https://deploy.apple.com) (https://deploy.apple.com), and sign in with your company Apple ID.</span></span> <span data-ttu-id="e2b4a-125">この Apple ID は、将来 DEP トークンを更新するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-125">This Apple ID must be used later to renew your DEP token.</span></span>

2.  <span data-ttu-id="e2b4a-126">デバイス登録プログラム ポータルで、**[デバイス登録プログラム]** &gt; **[サーバーの管理]** の順に移動して、**[MDM サーバーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-126">In the Device Enrollment Program Portal, go to **Device Enrollment Program** &gt; **Manage Servers**, and then choose **Add MDM Server**.</span></span>

3.  <span data-ttu-id="e2b4a-127">**MDM サーバー名**を入力し、**[Next]** (次へ) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-127">Enter the **MDM Server Name**, and then choose **Next**.</span></span> <span data-ttu-id="e2b4a-128">サーバー名は、自分がモバイル デバイス管理 (MDM) サーバーを識別できるようにするための名前です。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-128">The server name is for your reference to identify the mobile device management (MDM) server.</span></span> <span data-ttu-id="e2b4a-129">Microsoft Intune サーバーの名前または URL ではありません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-129">It is not the name or URL of the Microsoft Intune server.</span></span>

4.  <span data-ttu-id="e2b4a-130">**[Add &lt;ServerName&gt;]** ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-130">The **Add &lt;ServerName&gt;** dialog box opens.</span></span> <span data-ttu-id="e2b4a-131">**[Choose File]** (ファイルを選択) をクリックして</span><span class="sxs-lookup"><span data-stu-id="e2b4a-131">Choose **Choose File…**</span></span> <span data-ttu-id="e2b4a-132">.pem ファイルをアップロードし、**[Next]** (次へ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-132">to upload the .pem file, and then choose **Next**.</span></span>

5.  <span data-ttu-id="e2b4a-133">**[Add &lt;ServerName&gt;]** (<サーバー名> の追加) ダイアログ ボックスに、**[Your Server Token]** (サーバー トークン) リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-133">The **Add &lt;ServerName&gt;** dialog box shows a **Your Server Token** link.</span></span> <span data-ttu-id="e2b4a-134">サーバー トークン (.p7m) ファイルをコンピューターにダウンロードした後、**[Done]** (完了) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-134">Download the server token (.p7m) file to your computer, and then choose **Done**.</span></span>

   <span data-ttu-id="e2b4a-135">この証明書 (.p7m) ファイルは、Intune と Apple の Device Enrollment Program サーバーとの間に信頼関係を確立するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-135">This certificate (.p7m) file is used to establish a trust relationship between Intune and Apple’s Device Enrollment Program servers.</span></span>

### <a name="add-the-dep-token-to-intune"></a><span data-ttu-id="e2b4a-136">Intune に DEP トークンを追加する</span><span class="sxs-lookup"><span data-stu-id="e2b4a-136">Add the DEP token to Intune</span></span>

1. <span data-ttu-id="e2b4a-137">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[管理]** &gt; **[モバイル デバイス管理]** &gt; **[iOS]** &gt; **[デバイス登録プログラム]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-137">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Admin** &gt; **Mobile Device Management** &gt; **iOS** &gt; **Device Enrollment Program**.</span></span>

2. <span data-ttu-id="e2b4a-138">**[DEP トークンをアップロードする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-138">Choose **Upload the DEP Token**.</span></span> <span data-ttu-id="e2b4a-139">証明書 (.p7m) ファイルを**参照**し、**Apple ID** を入力して、**[アップロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-139">**Browse** to the certificate (.p7m) file, enter your **Apple ID**, and then choose **Upload**.</span></span>

### <a name="add-the-corporate-device-enrollment-policy"></a><span data-ttu-id="e2b4a-140">業務用デバイスの登録ポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="e2b4a-140">Add the Corporate Device Enrollment Policy</span></span>

1. <span data-ttu-id="e2b4a-141">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[業務用デバイスの登録]** の順に選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-141">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Policy** &gt; **Corporate Device Enrollment**, and then choose **Add**.</span></span>

2. <span data-ttu-id="e2b4a-142">**[名前]** や **[説明]** などの **[全般]** の各項目を入力し、次のように、プロファイルに割り当てられているデバイスにユーザー アフィニティがあるか、グループに属するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-142">Provide **General** details including **Name** and **Description**, and specify whether devices assigned to the profile have user affinity or belong to a group:</span></span>

   - <span data-ttu-id="e2b4a-143">**ユーザー アフィニティを要求する**: 初回セットアップ時にデバイスをユーザーに関連付ける必要があります。その後、デバイスはそのユーザーとして企業のデータやメールにアクセスすることが許可されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-143">**Prompt for user affinity**: The device must be affiliated with a user during initial setup before it can be permitted to access company data and email as that user.</span></span> <span data-ttu-id="e2b4a-144">ユーザーに属し、ポータル サイトを使用する必要がある (つまりアプリをインストールする必要がある) DEP 管理対象のデバイスの場合、**[ユーザー アフィニティ]** を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-144">**User affinity** should be set up for DEP-managed devices that belong to users and need to use the company portal (that is, to install apps).</span></span> <span data-ttu-id="e2b4a-145">多要素認証 (MFA) は、ユーザー アフィニティを使用して DEP デバイスに登録しているときに動作しません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-145">Multifactor authentication (MFA) doesn't work during enrollment on DEP devices with user affinity.</span></span> <span data-ttu-id="e2b4a-146">DEP デバイスに登録が完了すると、MFA は期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-146">After enrollment, MFA works as expected on these devices.</span></span> <span data-ttu-id="e2b4a-147">最初にサインインするときにパスワードを変更する必要がある新しいユーザーには、DEP デバイスの登録時にプロンプトを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-147">New users who are required to change their password when they first sign in cannot be prompted during enrollment on DEP devices.</span></span> <span data-ttu-id="e2b4a-148">さらに、パスワードの有効期限が切れているユーザーには、DEP 登録時にパスワードのリセットは求められません。このユーザーは別のデバイスからパスワードをリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-148">Additionally, users whose passwords have expired won't be prompted to reset their password during DEP enrollment and must reset the password from a different device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="e2b4a-149">ユーザー アフィニティが設定された DEP でユーザー トークンを要求するには、[WS-Trust 1.3 Username/Mixed エンドポイント](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints)を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-149">DEP with user affinity requires [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints) to be enabled to request user token.</span></span> <span data-ttu-id="e2b4a-150">WS-Trust 1.3 について詳しくは、[こちら](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-150">[Learn more about WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).</span></span>

   - <span data-ttu-id="e2b4a-151">**ユーザー アフィニティがありません**: デバイスは、ユーザーと関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-151">**No user affinity**: The device is not affiliated with a user.</span></span> <span data-ttu-id="e2b4a-152">このデバイス関連付け情報を使用すると、ローカルのユーザー データにアクセスしなくてもタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-152">Use this affiliation for devices that do tasks without accessing local user data.</span></span> <span data-ttu-id="e2b4a-153">基幹業務アプリのインストールに使用されるポータル サイト アプリなど、ユーザー アフィリエーションが必要なアプリは機能しません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-153">Apps that require user affiliation, including the Company Portal app that is used to install line-of-business apps, won’t work.</span></span>

   <span data-ttu-id="e2b4a-154">**デバイスを次のグループに割り当てる**こともできます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-154">You can also **Assign devices to the following group**.</span></span> <span data-ttu-id="e2b4a-155">**[選択...]** を選択して、グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-155">Choose **Select...** to choose a group.</span></span>

   > [!Important]
   > <span data-ttu-id="e2b4a-156">グループの割り当てが Intune から Azure Active Directory に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-156">Group assignments are moving from Intune to Azure Active Directory.</span></span> <span data-ttu-id="e2b4a-157">Intune アカウントで適用可能な更新プログラムが受信されると、**[デバイスを次のグループに割り当てる]** オプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-157">Once your Intune account receives the applicable update, you won't see the **Assign devices to the following group** option.</span></span> <span data-ttu-id="e2b4a-158">[詳細については、ここをクリック](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments)してください。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-158">[Learn more](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).</span></span>

3. <span data-ttu-id="e2b4a-159">**[このポリシーのデバイス登録プログラムの設定を構成します]** を有効にして DEP をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-159">Enable **Configure Device Enrollment Program settings for this policy** to support DEP.</span></span>

      ![[セットアップ アシスタント] ウィンドウ](../media/pol-sa-corp-enroll.png)

   <span data-ttu-id="e2b4a-161">次の設定を DEP 管理対象デバイスに使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-161">The following settings are available for DEP-managed devices:</span></span>

   - <span data-ttu-id="e2b4a-162">**部門** - アクティブ化中にユーザーが **[構成について]** をタップすると表示されます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-162">**Department** - Appears when users tap **About Configuration** during activation</span></span>
   - <span data-ttu-id="e2b4a-163">**サポート電話番号** - アクティブ化中にユーザーが **[ヘルプが必要ですか]** ボタンをクリックすると表示されます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-163">**Support phone number** - Appears when the user clicks the **Need Help** button during activation</span></span>
   - <span data-ttu-id="e2b4a-164">**準備モード** - アクティブ化中に設定し、デバイスの工場出荷時設定以外では変更できません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-164">**Preparation mode** - Set during activation and cannot be changed without factory resetting the device:</span></span>
       - <span data-ttu-id="e2b4a-165">**監督解除済み** - 管理機能が制限されます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-165">**Unsupervised** - Limited management capabilities</span></span>
       - <span data-ttu-id="e2b4a-166">**監督下** - より多くの管理オプションが使用可能になり、既定で [アクティブ化ロック] は無効になります</span><span class="sxs-lookup"><span data-stu-id="e2b4a-166">**Supervised** - Enables more management options and disables Activation Lock by default</span></span>
   - <span data-ttu-id="e2b4a-167">**デバイスへの登録プロファイルのロック** - アクティブ化中に設定し、デバイスの工場出荷時設定以外では変更できません</span><span class="sxs-lookup"><span data-stu-id="e2b4a-167">**Lock enrollment profile to device** - Set during activation and cannot be changed without a factory reset</span></span>
       - <span data-ttu-id="e2b4a-168">**無効** - **[設定]** メニューから管理プロファイルを削除できます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-168">**Disable** - Allows the management profile to be removed from the **Settings** menu</span></span>
       - <span data-ttu-id="e2b4a-169">**有効** - (**[準備モード]**  =  **[監督下]** にする必要があります) 管理プロファイルを削除する iOS 設定メニューのオプションを無効にします</span><span class="sxs-lookup"><span data-stu-id="e2b4a-169">**Enable** - (Requires **Preparation Mode** = **Supervised**) Disables the iOS Settings menu option to remove the management profile</span></span>
   - <span data-ttu-id="e2b4a-170">**セットアップ アシスタントのオプション** - これらの省略可能な設定は、後で iOS の **[設定]** メニューで設定できます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-170">**Setup Assistant Options** - These optional settings can be set up later in the iOS **Settings** menu.</span></span>
        - <span data-ttu-id="e2b4a-171">**パスコード** - アクティブ化時にパスコードの入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-171">**Passcode** - Prompt for passcode during activation.</span></span> <span data-ttu-id="e2b4a-172">デバイスがセキュリティで保護される場合や、他の何らかの方法 (デバイスを 1 つのアプリに制限するキオスク モードなど) でアクセスが制御されている場合を除き、パスコードは常に必須にしてください</span><span class="sxs-lookup"><span data-stu-id="e2b4a-172">Always require a passcode unless the device will be secured or have access controlled in some other manner (that is, kiosk mode that restricts the device to one app)</span></span>
       - <span data-ttu-id="e2b4a-173">**位置情報サービス** - 有効にすると、アクティブ化時に、セットアップ アシスタントによってサービスがプロンプトされます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-173">**Location Services** - If enabled, Setup Assistant prompts for the service during activation</span></span>
       - <span data-ttu-id="e2b4a-174">**復元** - 有効にすると、アクティブ化時に、セットアップ アシスタントによって iCloud バックアップがプロンプトされます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-174">**Restore** - If enabled, Setup Assistant prompts for iCloud backup during activation</span></span>
       - <span data-ttu-id="e2b4a-175">**Apple ID** - 有効にして、Intune で ID を指定せずにアプリをインストールしようとすると、Apple ID の入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-175">**Apple ID** - If enabled, iOS will prompt users for an Apple ID when Intune attempts to install an app without an ID.</span></span> <span data-ttu-id="e2b4a-176">Intune でインストールされるアプリを含め、iOS App Store アプリをダウンロードする際に Apple ID が必須になります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-176">An Apple ID is required to download iOS App Store apps, including those installed by Intune.</span></span>
       - <span data-ttu-id="e2b4a-177">**使用条件** - 有効にすると、アクティブ化時に、セットアップ アシスタントによって Apple の使用条件に同意するように求められます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-177">**Terms and Conditions** - If enabled, Setup Assistant prompts users to accept Apple's terms and conditions during activation</span></span>
       - <span data-ttu-id="e2b4a-178">**タッチ ID** - 有効にすると、アクティブ化時に、セットアップ アシスタントによってこのサービスがプロンプトされます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-178">**Touch ID** - If enabled, Setup Assistant prompts for this service during activation</span></span>
       - <span data-ttu-id="e2b4a-179">**Apple Pay** - 有効にすると、アクティブ化時に、セットアップ アシスタントによってこのサービスがプロンプトされます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-179">**Apple Pay** - If enabled, Setup Assistant prompts for this service during activation</span></span>
       - <span data-ttu-id="e2b4a-180">**ズーム** - 有効にすると、アクティブ化時に、セットアップ アシスタントによってこのサービスがプロンプトされます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-180">**Zoom** - If enabled, Setup Assistant prompts for this service during activation</span></span>
       - <span data-ttu-id="e2b4a-181">**Siri** - 有効にすると、アクティブ化時に、セットアップ アシスタントによってこのサービスがプロンプトされます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-181">**Siri** - If enabled, Setup Assistant prompts for this service during activation</span></span>
       - <span data-ttu-id="e2b4a-182">**Apple に診断データを送信する** - 有効にすると、アクティブ化時に、セットアップ アシスタントによってこのサービスがプロンプトされます</span><span class="sxs-lookup"><span data-stu-id="e2b4a-182">**Send diagnostic data to Apple** - If enabled, Setup Assistant prompts for this service during activation</span></span>
   -  <span data-ttu-id="e2b4a-183">**追加の Apple Configurator の管理を有効にします** - Apple Configurator 経由で iTunes または管理とファイルが同期されないようにするには、**[許可しない]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-183">**Enable additional Apple Configurator management** - Set to **Disallow** to prevent syncing files with iTunes or management via Apple Configurator.</span></span> <span data-ttu-id="e2b4a-184">**[許可しない]** を使用して証明書ありまたは証明書なしの手動の展開を許可するのではなく、[許可しない] を選択して、Apple Configurator からその他の構成をエクスポートし、Intune 経由でカスタム iOS 構成プロファイルとして展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-184">It's a good idea to choose **Disallow**, export further configurations from Apple Configurator, and then deploy as a Custom iOS configuration profile via Intune instead of using this setting to allow manual deployment with or without a certificate.</span></span>
       - <span data-ttu-id="e2b4a-185">**許可しない** - デバイスの USB 経由の通信を禁止します (ペアリングを無効にします)</span><span class="sxs-lookup"><span data-stu-id="e2b4a-185">**Disallow** - Prevents the device from communicating via USB (disables pairing)</span></span>
       - <span data-ttu-id="e2b4a-186">**許可する** - デバイスに PC または Mac との USB 接続での通信を許可します</span><span class="sxs-lookup"><span data-stu-id="e2b4a-186">**Allow** - Allows a device to communicate via USB connection for any PC or Mac</span></span>
       - <span data-ttu-id="e2b4a-187">**証明書が必要** - 登録プロファイルにインポートされた証明書を使用した Mac とのペアリングを許可します</span><span class="sxs-lookup"><span data-stu-id="e2b4a-187">**Require certificate** - Allows pairing with a Mac with a certificate imported to the enrollment profile</span></span>

### <a name="assign-the-profile-to-devices"></a><span data-ttu-id="e2b4a-188">デバイスにプロファイルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e2b4a-188">Assign the profile to devices</span></span>

1. <span data-ttu-id="e2b4a-189">[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[ポリシー]** &gt; **[業務用デバイスの登録]** の順に移動し、**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-189">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Policy** &gt; **Corporate Device Enrollment**, and then choose **Assign**.</span></span>

2. <span data-ttu-id="e2b4a-190">作成したプロファイルを割り当てるデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-190">Choose the devices to which you want to assign the profile that you created.</span></span> <span data-ttu-id="e2b4a-191">**[すべてのデバイス]** を選択することも、特定のデバイスを選択することもできます。その後、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-191">You can choose **All devices** or select specific devices, and then select **Add**.</span></span>

> [!Important]
> <span data-ttu-id="e2b4a-192">現在、Intune では "既定の" デバイス登録プロファイルを指定できます。つまり、新しいシリアル番号は、Apple DEP サービスと同期するときに、その既定のプロファイルに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-192">Currently, Intune lets you designate a "default" device enrollment profile," which means that new serial numbers are automatically assigned to that default profile when you synchronize new serial numbers with the Apple DEP service.</span></span> <span data-ttu-id="e2b4a-193">今後、新しい Azure Portal にテナントが移行された場合、既定のプロファイルを設定し、そのプロファイルにシリアル番号を自動で割り当てられなくなります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-193">When your tenant is migrated to the new Azure portal in the near future, you will no longer be able to set a default profile and have serial numbers be automatically assigned to that profile.</span></span> <span data-ttu-id="e2b4a-194">したがって、ユーザーが自分でシリアル番号を特定のプロファイルに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-194">Instead, you will have to assign serial numbers to a specific profile.</span></span> [<span data-ttu-id="e2b4a-195">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e2b4a-195">Learn more</span></span>](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios)

### <a name="assign-dep-devices-for-management"></a><span data-ttu-id="e2b4a-196">管理対象の DEP デバイスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e2b4a-196">Assign DEP Devices for Management</span></span>

1. <span data-ttu-id="e2b4a-197">[Device Enrollment Program ポータル](https://deploy.apple.com) (https://deploy.apple.com) に移動し、会社の Apple ID でサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-197">Go to the [Device Enrollment Program Portal](https://deploy.apple.com) (https://deploy.apple.com) and sign in with your company Apple ID.</span></span>

2. <span data-ttu-id="e2b4a-198">**[Deployment Program]** (展開プログラム) &gt; **[Device Enrollment Program]** (デバイス登録プログラム) &gt; **[Manage Devices]** (デバイスの管理) の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-198">Go to  **Deployment Program** &gt; **Device Enrollment Program** &gt; **Manage Devices**.</span></span>

3. <span data-ttu-id="e2b4a-199">**デバイスの選択**方法を指定し、デバイス情報を入力して、デバイスの **シリアル番号**、 **注文番号**、または **CSV ファイルのアップロード**で詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-199">Specify how you will **Choose Devices**, provide device information and specify details by device **Serial Number**, **Order Number**, or **Upload CSV File**.</span></span>

4. <span data-ttu-id="e2b4a-200">**[Assign to Server]** (サーバーに割り当てる) を選択し、Microsoft Intune に指定した &lt;ServerName&gt; を選択して、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-200">Choose **Assign to Server** and choose the &lt;ServerName&gt; specified for Microsoft Intune, and then choose **OK**.</span></span>

### <a name="synchronize-dep-managed-devices"></a><span data-ttu-id="e2b4a-201">DEP 管理対象デバイスを同期する</span><span class="sxs-lookup"><span data-stu-id="e2b4a-201">Synchronize DEP-Managed Devices</span></span>

<span data-ttu-id="e2b4a-202">この手順では、デバイスを Apple DEP サービスと同期し、そのデバイスが Intune コンソールに表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-202">This step synchronizes devices with the Apple DEP Service, and makes the devices appear in the Intune console.</span></span>

1. <span data-ttu-id="e2b4a-203">管理者ユーザーとして、[Microsoft Intune の管理コンソール](https://manage.microsoft.com)を開き、**[管理]** &gt; **[モバイル デバイス管理]** &gt; **[iOS]** &gt; **[デバイス登録プログラム]** の順に移動して、**[今すぐ同期]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-203">As an administrative user, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Admin** &gt; **Mobile Device Management** &gt; **iOS** &gt; **Device Enrollment Program**, and then choose **Sync now**.</span></span> <span data-ttu-id="e2b4a-204">同期要求が Apple に送信されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-204">A sync request is sent to Apple.</span></span>

2. <span data-ttu-id="e2b4a-205">同期後に DEP 管理対象デバイスを表示するには、[Microsoft Intune 管理コンソール](https://manage.microsoft.com)で、**[グループ]** &gt; **[すべてのデバイス]** &gt; **[会社の事前登録済みデバイス]** &gt; **[iOS シリアル番号を使用]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-205">To see DEP-managed devices after synchronization, in the [Microsoft Intune administration console](https://manage.microsoft.com) go to **Groups** &gt; **All Devices** &gt; **Corporate Pre-enrolled devices** &gt; **By iOS Serial Number**.</span></span> <span data-ttu-id="e2b4a-206">デバイスの電源を入れ、セットアップ アシスタントを実行して、デバイスを登録するまで、**[iOS シリアル番号を使用]** ワークスペースには管理対象デバイスの **[状態]** が "未接続" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-206">In the **By iOS Serial Number** workspace, the **State** for managed devices reads “Not contacted” until the device is powered on and runs the Setup Assistant to enroll the device.</span></span>

   <span data-ttu-id="e2b4a-207">許容される DEP トラフィックについての Apple の規約に準拠するため、Intune では次の制限が課せられます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-207">To comply with Apple’s terms for acceptable DEP traffic, Intune imposes the following restrictions:</span></span>

   - <span data-ttu-id="e2b4a-208">完全な DEP 同期は 7 日ごとに 1 回以上実行できません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-208">A full DEP sync can run no more than once every seven days.</span></span> <span data-ttu-id="e2b4a-209">完全同期時に、Intune は Apple が Intune に割り当てたすべてのシリアル番号を、シリアルが以前に同期されているかどうかに関係なく更新します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-209">During a full sync, Intune refreshes every serial number that Apple has assigned to Intune whether the serial has previously been synced or not.</span></span> <span data-ttu-id="e2b4a-210">前回の完全同期の 7 日以内に完全同期が試みられると、Intune は Intune にまだ一覧表示されていないシリアル番号のみを更新します。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-210">If a full sync is attempted within seven days of the previous full sync, Intune only refreshes serial numbers that are not already listed in Intune.</span></span>

   - <span data-ttu-id="e2b4a-211">すべての同期要求は、完了までに 10 分与えられます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-211">Any sync request is given 10 minutes to finish.</span></span> <span data-ttu-id="e2b4a-212">この時間中または要求が成功するまで、**[同期]** ボタンは無効にされます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-212">During this time or until the request succeeds, the **Sync** button is disabled.</span></span>

### <a name="distribute-devices-to-users"></a><span data-ttu-id="e2b4a-213">デバイスをユーザーに配布する</span><span class="sxs-lookup"><span data-stu-id="e2b4a-213">Distribute devices to users</span></span>

<span data-ttu-id="e2b4a-214">これで、会社が所有するデバイスをユーザーに配布できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-214">Your corporate-owned devices can now be distributed to users.</span></span> <span data-ttu-id="e2b4a-215">iOS デバイスの電源をオンにすると、iOS デバイスが Intune の管理対象として登録されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-215">When an iOS device is turned on it will be enrolled for management by Intune.</span></span> <span data-ttu-id="e2b4a-216">DEP 管理対象デバイスに、ユーザー デバイスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-216">The user device limit applies to DEP-managed devices.</span></span>

>[!NOTE]
><span data-ttu-id="e2b4a-217">DEP デバイスを登録しようとしてデバイスの制限を超えた場合、登録は失敗しますがユーザーへの警告はありません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-217">If a user attempts to enroll a DEP device but has exceeded her device limit, enrollment will fail silently without warning the user.</span></span>

## <a name="changes-to-intune-group-assignments"></a><span data-ttu-id="e2b4a-218">Intune グループ割り当ての変更</span><span class="sxs-lookup"><span data-stu-id="e2b4a-218">Changes to Intune group assignments</span></span>

<span data-ttu-id="e2b4a-219">2017 年 4 月から、デバイス グループの管理は Azure Active Directory に移行されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-219">Starting in April 2017, device group management is moving to Azure Active Directory.</span></span> <span data-ttu-id="e2b4a-220">Azure Active Directory グループに切り替えた後は、グループの割り当ては企業の登録プロファイルのオプションに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-220">After the transition to Azure Active Directory groups, group assignment will not appear in the Corporate Enrollment Profile options.</span></span> <span data-ttu-id="e2b4a-221">この変更は数か月間にわたりロールアウトされるため、変更はすぐに表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-221">Because this change will roll out over a series of months, you might not see the change right away.</span></span> <span data-ttu-id="e2b4a-222">新しいポータルに移動した後、会社の登録プロファイルの名前に基づいて動的なデバイス グループの割り当てを定義できます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-222">After moving to the new portal, dynamic device group assignments can be defined based on the Corporate Enrollment Profile names.</span></span>

<span data-ttu-id="e2b4a-223">移行時に、業務用デバイスの登録プロファイルで事前に割り当てられている Intune デバイス グループごとに、業務用デバイスの登録プロファイルの名前に基づいて、Azure AD に対応する動的デバイス グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-223">Upon migration, for every Intune device group pre-assigned by a Corporate Device Enrollment profile, a corresponding dynamic device group will be created in Azure AD based on the Corporate Device Enrollment profile’s name.</span></span> <span data-ttu-id="e2b4a-224">新しいプロファイル名のフォーマットは、*EnrollmentProfile:&lt;関連付けられているプロファイルの名前&gt;* です。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-224">New profile names have the format *EnrollmentProfile:&lt;name of associated profile&gt;*.</span></span> <span data-ttu-id="e2b4a-225">このプロセスにより、デバイス グループに既に割り当てられているデバイスが、ポリシーおよびデプロイされたアプリと共にグループに自動的に登録されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-225">This process ensures that devices that are assigned to a device group already will automatically enroll in the group with policy and apps deployed.</span></span>

<span data-ttu-id="e2b4a-226">この自動グループ作成は、グループの移行中に 1 回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-226">This automatic group creation happens only once, during groups migration.</span></span> <span data-ttu-id="e2b4a-227">移行後は、Intune 管理者が Azure Portal を使用してグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-227">After migration, Intune admins must create groups using the Azure portal.</span></span> <span data-ttu-id="e2b4a-228">会社所有の iOS デバイスの登録に与える影響の詳細については、「[Changes to Automatic Grouping for Corporate Pre-enrolled iOS Devices](https://blogs.technet.microsoft.com/intunesupport/2017/04/19/changes-to-automatic-grouping-for-corporate-pre-enrolled-ios-devices/)(会社の事前登録済み iOS デバイスに対する自動グループ化の変更)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-228">For details about how this affects company-owned iOS device enrollment, see [Changes to Automatic Grouping for Corporate Pre-enrolled iOS Devices](https://blogs.technet.microsoft.com/intunesupport/2017/04/19/changes-to-automatic-grouping-for-corporate-pre-enrolled-ios-devices/).</span></span>

<span data-ttu-id="e2b4a-229">[Azure Active Directory グループの詳細について学習する](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)こともできます。</span><span class="sxs-lookup"><span data-stu-id="e2b4a-229">You can also [Learn more about Azure Active Directory groups](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).</span></span>

### <a name="see-also"></a><span data-ttu-id="e2b4a-230">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2b4a-230">See also</span></span>
[<span data-ttu-id="e2b4a-231">デバイスを登録するための前提条件</span><span class="sxs-lookup"><span data-stu-id="e2b4a-231">Prerequisites for enrolling devices</span></span>](prerequisites-for-enrollment.md)